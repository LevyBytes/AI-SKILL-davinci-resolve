# Mask Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Mask Nodes

Here the chapter covers the Mask nodes that Fusion offers.

You can type the abbreviation shown beside each node name into the Select Tool dialog while hunting for tools, and they serve in scripting references too. Throughout this document, treat node trees that show MediaIn nodes in DaVinci Resolve as equivalent to Loader nodes in Fusion Studio, except where stated otherwise.

### Bitmap Mask [Bmp]

### The Bitmap node

### Bitmap Mask Node Introduction

With the Bitmap mask node, images coming from the node tree can serve as masks for nodes and effects. A Bitmap mask may draw on values from any of the image's color, Alpha, hue, saturation, luminance, and auxiliary coverage channels. Nodes can likewise be masked off the Object ID or Material ID of a 3D-rendered image, so long as those channels were baked in at render time. For effect masks the Bitmap mask node isn't needed. For effects masks, the masked node's Common Settings tab carries controls letting you pick which channel of the mask image builds the mask. That said, on certain nodes a Bitmap mask node may still be needed to feed other mask inputs, such as Garbage Mattes and Pre-Masks. Inserting a Bitmap mask node between the mask source and the target node also unlocks extra options you'd otherwise lack when wiring them up directly — combining masks, blurring the mask, or clipping its threshold, for instance.

### Inputs

Within the Node Editor the Bitmap mask node carries two inputs. Input: The orange input takes in a 2D image that the mask gets built from. Effect Mask: The optional blue input looks for a mask shape made from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask into this input and the masks combine. The Paint mode menu over in the Inspector governs how they combine.

### Basic Node Setup

You don't strictly need the Bitmap mask node to feed an image into the effect mask input, yet it surfaces options you can't otherwise reach. It lets you pick channels beyond RGBA for the mask, plus softness and clipping. In the node tree shown below, a Paint menu sitting in the second Bitmap mask node combines the two Bitmap masks, giving you add, subtract, multiply, and further operations on the merged mask.

Bitmap nodes can be chained together for more advanced matte operations.

### Inspector

### Bitmap Mask controls

### Controls Tab

Use the Controls tab to fine-tune how the image wired into the orange input becomes the Bitmap mask. Show View Controls Toggling the Show View Controls checkbox turns the mask's onscreen controls in the viewer on or off. With it off, onscreen controls — center position, polylines, angles, and the rest — stay hidden even while the node is selected. Level The Level control governs how transparent the pixels in the mask channel are. At a value of 1.0 the mask is fully opaque (barring a soft edge). Drop the value and the mask turns partly transparent. That matches what lowering an effect's Blend control does. NOTE: Dropping a mask's level drops the values of every pixel the mask covers in the mask channel. As an example, set a Circle mask over a Rectangle mask, and lowering the Circle mask's level lowers the values of all the mask-channel pixels, even where the Rectangle mask underneath stays opaque.

Filter This control picks the filtering algorithm applied when Soft Edge is added to the mask.

- Box: The quickest option, though quality suffers. Box fits best when you need only a little blur.
- Bartlett: Also called a Pyramid filter, Bartlett strikes a sound balance between speed and quality.
- Multi-box: Pick this filter and the Num Passes slider shows up so you can dial in the quality. With 1 and 2 passes the output matches Box and Bartlett in turn. At 4 passes or more the output is generally on par with Gaussian, faster, and free of edge “ringing.”
- Gaussian: Relying on a genuine Gaussian approximation, the Gaussian filter delivers superb results, though it runs a touch slower than the rest. Occasionally it yields an exceptionally faint edge “ringing” on floating-point pixels.

Soft Edge Drag the Soft Edge slider to blur (feather) the mask through the chosen filter. Raise the value and the edge fades far past the mask's boundaries. Set it to 0.0 for a crisp, well-defined edge. Paint Mode Wiring a mask into the effect mask input brings up the Paint mode menu. Paint mode decides how the incoming mask for the effect mask input merges with the mask the node itself produces.

- Merge: The default across all masks. The new mask merges into the input mask.
- Add: The new mask's values are added onto the input mask's values.
- Subtract: Where they overlap, the new mask's values come off the input mask's values.
- Minimum: Looking at the input mask's values against the new mask, this shows the lowest

(minimum) value.

- Maximum: Looking at the input mask's values against the new mask, this shows the highest

(maximum) value.

- Average: This produces the mean — that is, half the sum — across the new mask and the input mask.
- Multiply: This takes the input mask's values times the new mask's values.
- Replace: Wherever they overlap, the new mask fully supplants the input mask. Spots that

read zero (pure black) in the new mask leave the input mask untouched.

- Invert: Parts of the input mask sitting under the new mask flip; white turns

black and the reverse. Gray spots in the new mask invert partway.

- Copy: This mode throws out the input mask entirely and takes every value from the new mask.
- Ignore: This mode throws out the new mask entirely and takes every value from the input mask.

Invert Tick this checkbox to flip the whole mask. In contrast to the Invert Paint mode, this checkbox acts on every pixel, whether or not the new mask covers them. Fit Input This menu lets you choose how the image source is handled when it doesn't match the dimensions of the mask being generated. In the example below, a 720 x 576 image source (yellow) generates a 1920 x 1080 mask (gray).

Crop: When the image source is smaller than the generated mask, it lands per the X/Y controls, masking off just a slice of the mask. When the image source is larger, it again lands per the X/Y controls and gets cropped at the mask's borders. Stretch: The image source is stretched across X and Y to span the generated mask's full dimensions. That may visibly distort the image source. Inside: The image source scales uniformly until one of its dimensions (X or Y) reaches the inside dimensions of the mask. Based on the relative dimensions of image source and mask background, either the source's width or height may get cropped to meet the matching dimension of the mask. Width: The image source scales uniformly until its width (X) meets the mask's width. Based on the relative dimensions of image source and mask, the source's Y dimension may fall short of the mask's Y dimension, so the source is either cropped in Y or fails to span the mask's height.

Height: The image source scales uniformly until its height (Y) meets the mask's height. Based on the relative dimensions of image source and mask, the source's X-dimension may fall short of the mask's X-dimension, so the source is either cropped in X or fails to span the mask's width.

Outside: The image source scales uniformly until one of its dimensions (X or Y) reaches the outside dimensions of the mask. Based on the relative dimensions of image source and mask, either the source's width or height may get cropped or fall short of the matching mask dimension.

Center X and Y These controls set the placement of the Bitmap mask. Channel The Channel menu sets which Channel of the input image builds the mask. You may pick from the red, green, blue, plus alpha channels; from the hue, luminance, or saturation values; or from the input image's auxiliary coverage channel (where one exists). Threshold Low/High The Threshold range control lets you clip the bitmap image. Raising the low range control clips pixels under the set value to black (0.0). Lowering the high range control pushes pixels above the set value to white (1.0). Use Object/Use Material This control does nothing unless the input image carries a Material or Object ID channel. Switched on, the Object ID and Material ID build a mask off the chosen object or material. Switched off, the ordinary color channels build the mask.

### Common Controls

Image and Settings Tabs Other Mask nodes carry copies of the Inspector's Image and Settings tabs as well. The chapter's closing “The Common Controls” section walks through these shared controls thoroughly.

### B-Spline Mask [BSp]

### The B-Spline node

A B-Spline mask matches a Polygon mask in every way but one. Polygon masks rely on Bézier splines, while this mask node relies on B-Splines. A Bézier spline uses one central point plus two handles to control how its spline segment smooths, whereas a B-Spline needs just a lone point. As a result, a B-Spline shape calls for far fewer control points to build a nicely smoothed form. Right after you add it to a node, the B-Spline mask holds only the Center control, shown onscreen. You add points to the B-Spline by clicking in the viewer. Every fresh point links to the previous one, but rather than the spline passing straight through each control point, B-Spline control points merely influence the spline shape. The control point tugs the spline toward itself to form a smooth curve. As with the Polygon mask tool, the B-Spline mask auto-animates. Dropping this node into the Node Editor sets a keyframe at the current frame. Jump to another frame, alter the shape, and a new keyframe is created, interpolating between the two defined shapes.

### Inputs

The B-Spline mask node carries one effect mask input. Effect Mask: The optional blue input looks for a mask shape made from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask into this input and the masks combine. The Paint mode menu over in the Inspector governs how they combine.

### Basic Node Setup

The B-Spline node can build a single smooth spline shape on its own, or join with other masks to form more involved shapes. Down in the node tree below, the B-Spline mask builds a smooth, curved shape serving as a garbage matte on the Delta Keyer.

A B-Spline node producing a smooth, curved form that serves as a garbage matte

### Inspector

### B-Spline Mask controls

### Controls Tab

The Controls tab helps you refine how the B-Spline looks once you've drawn it in the viewer. Show View Controls The Show View Controls checkbox switches the mask's onscreen controls in the viewer on or off. Disable it and the onscreen controls — center position, polylines, angles, and so on — won't show even with the node selected. Level Level sets the transparency of the pixels in the mask channel. At 1.0 the mask reads fully opaque (save for a soft edge). Lower values render the mask partly transparent. The outcome equals lowering an effect's blend control. NOTE: Dropping a mask's level drops the values of all pixels the mask covers in the mask channel. As an example, place a Circle mask over a Rectangle mask, and lowering the Circle mask's level lowers the values of all of the mask-channel pixels, even though the Rectangle mask below stays opaque. Filter This control picks the filtering algorithm applied when Soft Edge is added to the mask.

- Box: The fastest method, at the cost of quality. Box suits small amounts of blur best.
- Bartlett: Known too as a Pyramid filter, Bartlett offers a fine trade-off between speed and quality.
- Multi-box: Choosing this filter reveals the Num Passes slider so you can govern quality. At 1 and 2 passes, the results equal Box and Bartlett respectively. From 4 passes upward, results tend to rival Gaussian, in less time and without edge “ringing.”
- Gaussian: Built on a true Gaussian approximation, the Gaussian filter produces excellent results, albeit a bit slower than the others. Now and then it leaves an extremely slight edge “ringing” on floating-point pixels.

Soft Edge Reach for the Soft Edge slider to blur (feather) the mask via the chosen filter. Higher values let the edge fade well past the mask's boundaries. A setting of 0.0 yields a crisp, well-defined edge. Border Width The Border Width control tunes how thick the mask's edge is. With the solid checkbox on, the border grows or shrinks the mask. When the mask isn't solid, the mask shape renders as an outline whose width follows the Border Width setting. Paint Mode Wiring a mask into the effect mask input shows the Paint mode menu. Paint mode sets how the mask coming into the effect mask input merges with the mask the node creates.

- Merge: The default for every mask. The new mask merges into the input mask.
- Add: The new mask's values are summed onto the input mask's values.
- Subtract: Throughout the overlapping regions, the new mask's values are deducted from the input mask's values.
- Minimum: Weighing the input mask's values against the new mask, this returns the

lowest (minimum) value.

- Maximum: Weighing the input mask's values against the new mask, this returns the

highest (maximum) value.

- Average: This yields the mean value (half the sum) taken from the new mask together with the input mask.
- Multiply: This multiplies the input mask's values by the new mask's values.
- Replace: Across any overlap, the new mask wholly takes over the input mask. Regions that

are zero (totally black) in the new mask leave the input mask alone.

- Invert: Portions of the input mask the new mask covers get flipped; white becomes

black and vice versa. Gray regions in the new mask flip partway.

- Copy: This mode discards the input mask completely and draws every value from the new mask.
- Ignore: This mode discards the new mask completely and draws every value from the input mask.

Invert Tick this checkbox to flip the entire mask. Unlike the Invert Paint mode, the checkbox touches every pixel, no matter whether the new mask covers them. Solid With the Solid checkbox on, the mask fills in transparent (white) unless inverted. With it off, the spline renders as an outline alone, its thickness governed by the Border Width slider. Center X and Y These controls set the placement of the B-Spline mask.

Size Reach for the Size control to scale the B-Spline effect mask without disturbing the relative behavior of the points that make up the mask, and without dropping a keyframe into the mask animation. X, Y, and Z Rotation Use this trio of controls to set the mask's rotation angle along any axis. Fill Method The Fill Method menu provides two distinct ways to handle overlapping regions of a polyline. Should overlapping segments in a mask be producing unwanted holes, switch this control over from Alternate across to Non Zero Winding. Right-Click Here for Shape Animation By default, the instant a B-Spline mask is created it begins animating. Its first keyframe lands at the current time, and any shape changes at other times will produce new keys. Right-click this label to open a contextual menu offering options for stripping or re-adding animation on the mask, or publishing and connecting the masks.

### Adding Points

Adding Points to a B-Spline effect mask is fairly simple. Right after you drop the node into the Node Editor, no points exist, but the tool sits in Click Append mode. Click once in the viewer at each spot the mask needs a point. Keep clicking to trace out the mask's shape. Once the shape is finished, click the first point once more to close the mask. With the shape closed, the polyline's mode switches to Insert and Modify. From there you can add and tweak extra points on the mask by clicking the spline segments. To lock the mask's shape down and head off accidental edits, set the Polyline mode to Done via the Polyline toolbar or the contextual menu. Adjusting Tension on a B-Spline A control point's tension dictates how smooth a B-Spline is. To tune a B-Spline's control-point tension, select the point in the viewer, hold the W key, and drag the mouse pointer left and right to raise or lower the tension of the curve passing through that point.

### Adjusting Tension on a B-Spline

### B-Spline Toolbar

Select a B-Spline mask in the Node Editor and a toolbar shows above the viewer, its buttons giving quick access to the modes. Rest the pointer on any toolbar button to bring up a tooltip explaining what that button does.

### B-Spline Mask Polygon toolbar

To alter how the toolbar displays, right-click it and pick from the choices in the toolbar's contextual menu. The Polylines section explains in full what the buttons in this toolbar do.

### Common Controls

Image and Settings Tabs Other mask nodes likewise carry copies of the Inspector's Image and Settings tabs. The closing “The Common Controls” section of this chapter explains these shared controls in full.

### Ellipse Mask [Elp]

### The Ellipse node

### Ellipse Mask Node Introduction

The Ellipse mask shines when you're masking round objects. By default it's a circle, but you get independent control over its width, height, and angle, which opens up a broad range of ellipsoidal shapes.

### Inputs

The Ellipse mask node carries one effect mask input. Effect Mask: The optional blue input looks for a mask shape made from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask into this input and the masks combine. The Paint mode menu over in the Inspector governs how they combine.

### Basic Node Setup

The Ellipse mask node comes in handy for building circular masks. Below, the Ellipse mask builds a circular colored shape by carving a circular shape out of a background node.

### Inspector

Ellipse mask node creating a colored circle by masking a background node

### Ellipse Mask controls

### Controls Tab

The Controls tab lets you refine how the ellipse looks once it's drawn in the viewer. Show View Controls The Show View Controls checkbox flips the mask's onscreen controls in the viewer on or off. Switch it off and the onscreen controls — center position, polylines, angles, and more — stay hidden even with the node selected. Level The Level control fixes the transparency of the pixels in the mask channel. At 1.0 the mask comes out fully opaque (unless a soft edge applies). Lower values make the mask partly transparent. This matches lowering an effect's blend control. NOTE: Dropping a mask's level drops the values of all pixels the mask covers in the mask channel. For instance, put a Circle mask over a Rectangle mask, and lowering the Circle mask's level lowers the values of all of the mask-channel pixels, even though the Rectangle mask underneath remains opaque.

Filter This control picks the filtering algorithm applied when Soft Edge is added to the mask.

- Box: The fastest approach, with quality reduced. Box works best for tiny amounts of blur.
- Bartlett: Also termed a Pyramid filter, Bartlett gives a solid balance between speed

and quality.

- Multi-box: Selecting this filter surfaces the Num Passes slider, letting you govern the

quality. At 1 and 2 passes, the output equals Box and Bartlett in turn. At 4 passes and up, the output usually matches Gaussian, in less time and with no edge “ringing.”

- Gaussian: Using a genuine Gaussian approximation, the Gaussian filter renders excellent results, though it lags the other filters a little. From time to time it can yield an extremely slight edge “ringing” on floating-point pixels.

Soft Edge Use the Soft Edge slider to blur (feather) the mask with the chosen filter. Higher values make the edge fade well past the mask's boundaries. A value of 0.0 produces a crisp, well‑defined edge. Border Width The Border Width control adjusts how thick the mask's edge is. With the solid checkbox on, the border fattens or thins the mask. When the mask isn't solid, the mask shape renders as an outline, its width set by the Border Width setting. Paint Mode Wiring a mask into the effect mask input displays the Paint mode menu. Paint mode determines how the mask arriving at the effect mask input merges with the mask the node makes.

- Merge: The default for all masks. The new mask merges into the input mask.
- Add: The new mask's values add onto the input mask's values.
- Subtract: Within the overlapping areas, the new mask's values subtract from the input mask's values.
- Minimum: Comparing the input mask's values with the new mask, this returns the lowest

(minimum) value.

- Maximum: Comparing the input mask's values with the new mask, this returns the highest

(maximum) value.

- Average: This averages (half the sum) the new mask alongside the input mask.
- Multiply: This multiplies the input mask's values by the new mask's values.
- Replace: Across every overlap, the new mask fully replaces the input mask. Regions that

read zero (completely black) in the new mask don't touch the input mask.

- Invert: Areas of the input mask covered by the new mask get flipped; white turns

black and the reverse. Gray areas in the new mask flip partway.

- Copy: This mode discards the input mask outright and uses the new mask for every value.
- Ignore: This mode discards the new mask outright and uses the input mask for every value.

Invert Tick this checkbox to flip the whole mask. Unlike the Invert Paint mode, the checkbox affects every pixel, whether or not the new mask covers them. Solid With the Solid checkbox on, the mask fills to transparent (white) unless inverted. With it off, the spline renders only as an outline whose thickness the Border Width slider controls.

Center X and Y These controls set the placement of the Ellipse mask. Width This control hands you independent command of the ellipse mask's Width. Beyond the slider in the mask's controls, you can drag the width (left or right edge) of the mask interactively in the viewer with the pointer. Whatever you change shows up in this control. Height Height hands you independent command of the ellipse mask's height. Beyond the slider in the mask's controls, you can drag the height (top or bottom edge) of the mask interactively in the view with the pointer. Whatever you change shows up in this control. To resize the mask while keeping the aspect ratio, drag the onscreen control between the edges (diagonal). That shifts both the width and height in proportion. Angle Alter the mask's rotational angle by sliding the Angle control left or right. You can also type values into the number fields supplied. Otherwise, work the onscreen controls by dragging the small circle at the tip of the dashed angle line to interactively set the ellipse's rotation.

### Common Controls

Image and Settings Tabs Other mask nodes carry copies of the Inspector's Image and Settings tabs too. The closing “The Common Controls” section of this chapter covers these shared controls in detail.

### Mask Paint [PNM]

### The Mask Paint node

### Mask Paint Node Introduction
