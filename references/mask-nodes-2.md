# Mask Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

With the Mask Paint node you paint mask images directly, treating the pointer like a paintbrush. Beyond ordinary paint strokes, you can lay down basic primitive shapes and polyline style strokes too. A stroke's duration can span the whole project, a single frame, or any number of fields you choose. In the Keyframes Editor each stroke can carry its own duration, which makes timing easy to manipulate. As an alternative, Multistrokes offers a quicker but non-editable route through many mask clean up paint jobs.

### Inputs

A single effect mask input is what the Paint mask node carries.

Effect Mask: The optional blue input looks for a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask into this input merges the masks. The way that merging happens is governed by the Paint mode menu within the Inspector.

### Basic Node Setup

The Mask Paint node comes in handy for painting masks in a looser, more freehand, pressure sensitive manner. In the node tree below, the Mask Paint node serves to patch holes in a Bitmap mask.

A Mask Paint node can be put to work repairing the troublesome regions of a matte.

### Inspector

### Mask Paint controls

Because the Mask Paint node's Controls tab is essentially the same as the Paint node's, you can find fuller detail in Chapter 113, "Paint Node," within the DaVinci Resolve Reference Manual, or Chapter 53 of the Fusion Reference Manual. What sets the two nodes apart is that, since Mask Paint works on single-channel mask images, it has no Channel Selector control and every color control holds just one Alpha value. The Mask tab, though, carries several parameters that differ from the Paint tool, and those are covered below.

### The Mask Paint tab

### Mask Tab

The Mask tab serves to fine-tune the basic mask parameters that sit outside the realm of "panting." Among these are how several masks merge, the overall softness control, and the level control. Show View Controls The Show View Controls checkbox switches the display of the mask's onscreen controls in the viewer on or off. With this checkbox off, the onscreen controls, center position, polylines, angles, and the rest, stay hidden even while the node is selected. Level The Level control fixes the transparency level of the pixels in the mask channel. At a value of 1.0, the mask is fully opaque (barring a soft edge). Lower values leave the mask partly transparent. The outcome matches lowering an effect's blend control. NOTE: Dropping a mask's level drops the values of every pixel the mask covers in the mask channel. As an example, with a Circle mask laid over a Rectangle mask, lowering the Circle mask's level drops the values of all the pixels in the mask channel, even while the Rectangle mask underneath stays opaque. Filter This control picks the filtering algorithm applied when Soft Edge is added to the mask.

- Box: The quickest method, though quality suffers. Box works best with only small amounts of blur.
- Bartlett: Also called a Pyramid filter, Bartlett strikes a solid balance between speed and quality.
- Multi-box: Choosing this filter brings up the Num Passes slider, which lets you dial in the quality. At 1 and 2 passes, the output matches Box and Bartlett in turn. From 4 passes up, the output is generally on par with Gaussian, achieved faster and free of edge "ringing."
- Gaussian: Built on a true Gaussian approximation, the Gaussian filter delivers excellent results, albeit a touch slower than the rest. On occasion it can yield a barely perceptible edge "ringing" on floating-point pixels.

Soft Edge Reach for the Soft Edge slider to blur (feather) the mask through the chosen filter. The larger the value, the farther the edge fades past the mask's boundaries. A value of 0.0 yields a crisp, well-defined edge.

Paint Mode Wiring a mask into the effect mask input brings up the Paint mode menu. The Paint mode decides how the mask coming into the effect mask input and the mask built in the node are merged.

- Merge: Merge is the default across all masks. The new mask is blended into the input mask.
- Add: The new mask's values are added onto the input mask's values.
- Subtract: Within the overlapping areas, the new mask values are taken away from the input mask's values.
- Minimum: Weighing the input mask's values against the new mask, this shows the lowest

(minimum) value.

- Maximum: Weighing the input mask's values against the new mask, this shows the highest

(maximum) value.

- Average: This takes the new mask and input mask and averages them (half their sum).
- Multiply: This multiplies the input mask's values by the new mask's values.
- Replace: Wherever they overlap, the new mask fully takes the place of the input mask. Spots that

read zero (fully black) in the new mask leave the input mask unchanged.

- Invert: Wherever the new mask covers the input mask, those areas flip; white turns

black and the reverse. Gray spots in the new mask invert only partly.

- Copy: This mode throws away the input mask entirely and draws all values from the new mask.
- Ignore: This mode throws away the new mask entirely and draws all values from the input mask.

Invert Ticking this checkbox flips the whole mask. Unlike the Invert Paint mode, the checkbox acts on every pixel, whether or not the new mask covers it.

### Common Controls

Image and Settings Tabs The Inspector's Image and Settings tabs appear in the other mask nodes too. Full descriptions of these common controls sit at this chapter's close, in the "The Common Controls" section.

### MultiPoly [MPly]

### The MultiPoly node

### Introduction

By letting you build several masks inside one node, the MultiPoly tool streamlines rotoscoping. The inspector's list of polygon shapes makes it easy to modify, organize, and animate shapes from a single straightforward interface. Because the masks sit in a scrolling list, much like the convenience MultiMerge provides, organizing, editing, and animating individual shapes is effortless. This intuitive interface simplifies drawing intricate masks and lets you assemble polished compositions with ease. On top of that, every one of these benefits lives inside this List view, which speeds up selecting and modifying particular shapes, toggling whether they are visible, and adjusting their parameters precisely.

### Usage

Once the MultiPoly is added, the tool stands ready for you to begin drawing your first mask. To build a mask, use the tools across the top of the viewer to lay down polygons, splines, and points (those points become the polyline's segments). Click the first point again to close the mask.

The MutliPoly tool showing three creation of masks on the viewer Inspector

### Multipoly controls

Within the Inspector, clicking the Polygon or BSpline button creates a new mask type. Every new mask joins the List view housed in the Inspector. Inside the List view you can rename or reorder any masks you have just added. To modify particular shapes, select them in the layer list and change their properties in the Inspector's lower section.

To animate any of the masks you have drawn, click the animation diamond beside the text "Right-click here for shape animation" at the Inspector's foot, or right-click that text and pick Animate. Right-clicking a mask in the layer list brings up a few options. Duplicate: Copies the selected mask and inserts a new entry into the layer list. Split here: Splits off the selected mask along with any mask beneath it, copying them into a brand-new MultiPoly node. Rename: Lets you rename the selected mask. Reset to default: Leaves the mask entry in the layer list but strips its shape away and returns all its controls to default. Delete: Removes the mask.

### Polygon Mask [Ply]

### The Polygon node

### Polygon Mask Node Introduction

The Polygon mask shines when you need to mask objects whose shape is irregular. Freshly added to a node, the Polygon mask shows only Center and Angle controls onscreen. Clicking in the viewer adds points to the polyline, each new point linking to the one made just before it. As with the B-Spline mask tool, the Polygon mask animates itself automatically. Adding this node to the Node Editor lays a keyframe on the current frame. Jumping to another frame and altering the shape lays a new keyframe and interpolates between the two defined shapes.

### Inputs

A single effect mask input is what the Polygon mask node carries. Effect Mask: The optional blue input looks for a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask into this input merges the masks. How that merging works is set in the Inspector's Paint mode menu.

### Basic Node Setup

You can use the Polygon node to produce a detailed spline shape, or pair it with other masks for shapes more complex still. In the node tree below, the Polygon mask produces a detailed shape serving as a solid matte on the Delta Keyer.

A Polygon node generates a detailed shape as a Solid matte.

### Inspector

### Polygon Mask controls

### Controls Tab

The Controls tab serves to refine how the polyline looks once you have drawn it in the viewer. Show View Controls The Show View Controls checkbox turns the display of the mask's onscreen controls in the viewer on or off. With the checkbox off, those onscreen controls, center position, polylines, angles, and the rest, remain hidden even while the node is selected. Level The Level control fixes the transparency level of the pixels in the mask channel. At a value of 1.0 the mask is fully opaque (unless it carries a soft edge). Lower values render the mask partly transparent. The effect is the same as turning down an effect's blend control. NOTE: Lowering a mask's level lowers the values of every pixel the mask covers within the mask channel. For instance, when a Circle mask sits over a Rectangle mask, dropping the Circle mask's level lowers the values of all the pixels in the mask channel, even though the Rectangle mask below stays opaque.

Filter This control chooses the filtering algorithm used as Soft Edge is applied to the mask.

- Box: The fastest of the options, but with lower quality. Box suits small amounts of blur best.
- Bartlett: Known as well by the name Pyramid filter, Bartlett trades off speed against quality nicely.
- Multi-box: Picking this filter reveals the Num Passes slider for tuning the quality. With 1 and 2 passes, the output equals Box and Bartlett in turn. At 4 passes or more, it usually rivals Gaussian, taking less time and leaving no edge "ringing."
- Gaussian: Using a genuine Gaussian approximation, the Gaussian filter produces excellent results, though it runs a bit slower than the others. Now and then it may put a very faint edge "ringing" onto floating-point pixels.

Soft Edge Use the Soft Edge slider to feather (blur) the mask through the chosen filter. Higher values let the edge fade well past the mask's boundaries. A value of 0.0 makes a crisp, well‑defined edge. Border Width The Border Width control sets how thick the mask's edge is. With the solid checkbox on, the border fattens or thins the mask. When the mask is not solid, its shape draws as an outline whose width follows the Border Width setting. Paint Mode Wiring a mask into the effect mask input brings up the Paint mode menu. The Paint mode sets how the mask arriving at the effect mask input and the mask made in the node are merged.

- Merge: Merge is the default for every mask. The new mask is blended into the input mask.
- Add: The new mask's values are summed with the input mask's values.
- Subtract: Across the overlapping areas, the new mask values are deducted from the input mask's values.
- Minimum: Setting the input mask's values beside the new mask, this shows the lowest

(minimum) value.

- Maximum: Setting the input mask's values beside the new mask, this shows the highest

(maximum) value.

- Average: This averages together the new mask and the input mask, giving half their combined sum.
- Multiply: This multiplies the input mask's values by those of the new mask.
- Replace: Anywhere they overlap, the new mask wholly supplants the input mask. Spots that

are zero (entirely black) in the new mask leave the input mask alone.

- Invert: Where the new mask covers the input mask, those areas flip; white turns

black and the other way around. Gray spots in the new mask are inverted only in part.

- Copy: This mode discards the input mask completely and pulls every value from the new mask.
- Ignore: This mode discards the new mask completely and pulls every value from the input mask.

Invert Checking this box inverts the whole mask. Unlike the Invert Paint mode, the box acts on all pixels, regardless of whether the new mask covers them.

Solid With the Solid checkbox on, the mask is filled to read transparent (white) unless inverted. With it off, the spline draws as a mere outline whose thickness comes from the Border Width slider. Center X and Y These controls set the position of the polygon spline mask. Size The Size control resizes the polygon spline effect mask without disturbing the relative behavior of the points making up the mask and without laying a keyframe in the mask animation. X, Y, and Z Rotation These three controls set the mask's rotation angle on any axis. Fill Method The Fill Method menu gives two distinct techniques for handling overlapping regions of a polyline. When overlapping segments in a mask spawn unwanted holes, switch this control over to Non Zero Winding from its Alternate setting. Right-Click Here for Shape Animation Each polygon spline mask, by default, is animated the moment it is created. The first keyframe lands at the current time, and shape changes at other times add new keys. A right-click on this label opens a contextual menu with options for stripping or re-adding animation to the mask, or for publishing and linking the masks together.

### Common Controls

Image and Settings Tabs The Inspector's Image and Settings tabs also recur across the other mask nodes. You will find these common controls fully described at this chapter's end, within the "The Common Controls" section.

### Adding Points

Putting points onto a polygonal effect mask is fairly straightforward. Right after the node lands in the Node Editor there are no points yet, but the tool sits in Click Append mode. Click once in the viewer at each spot where the mask needs a point. Keep clicking to trace the mask's shape. With the shape finished, click the first point again to close the mask. Once the shape is closed, the polyline's mode shifts to Insert and Modify. That lets you adjust and add further points to the mask by clicking on the polyline's segments. To lock the mask's shape and guard against accidental changes, set the Polyline mode to Done from the Polyline toolbar or the contextual menu.

### B-Spline Mask Polygon toolbar

Adding a Polygon (or B-Spline) mask to a node makes a toolbar appear above the viewer, giving quick access to the modes. Rest the pointer on any toolbar button to bring up a tooltip explaining what that button does.

- Click: Click is the default choice while you build a polyline (or B-Spline) mask. It works as a Bézier style drawing tool. A click drops a control point, and clicking again at another spot appends the next control point.
- Draw: Draw is a freehand drawing tool, making a mask the way you might sketch with a pencil on paper. Use the Draw tool to start a new mask, or to extend an open spline already there by clicking the Draw tool and resuming from the last control point.
- Insert: Insert drops a fresh control point onto the spline.
- Modify: Modify lets you safely reposition or smooth any existing point on a spline with no risk of dropping new points by accident.
- Done: Stops any point on the spline from being moved or modified, and bars new points from being added. You can still, however, move and rotate the whole spline.
- Closed: Closes an open spline.
- Smooth: Turns the selected control point from a linear corner into a smooth curve.
- Linear: Turns the selected control point from a smooth curve into linear.
- Select All: Selects every control point on the spline.
- Keys: Reveals or conceals the control points along the spline.
- Handles: Reveals or conceals the Bézier handles along the polyline.
- Shape: Drops a reshape rectangle around the selected spline shape. With that reshape rectangle, deforming groups of control points or entire shapes is far easier than editing each point.
- Delete: Removes the selected control point(s).
- Reduce: Opens a Freehand precision window for cutting down the number of control points on a spline. That can make the paint stroke simpler to edit, particularly when it was made with the Draw tool.
- Publish menu: The publish menu lets you choose between publishing the control points or the path. Publishing is a kind of parameter linking that makes the chosen item available to other controls. It also lets you tie a control point to a tracker.
- Follow Points: Lets a selected point trail the path of a published point, trailing it at an offset position.
- Double Poly: Lets you soften part of the spline curve while leaving other stretches of the curve sharp. The double polyline consists of two shapes, an inner and an outer one. The inner shape is the original shape from the single polyline, while the outer shape governs how far the softness spreads. The farther the outer shape sits from the inner shape, the softer that stretch of the shape grows. Both polylines begin matching the original single polyline exactly, so the mask starts off sharp. Whatever animation was already on the shape carries over. To select the outer shape, tap the Tab key to step through the onscreen controls until the dashed outline shows, or pick the outer polyline from the contextual menu's Controls > Outer Polygon menu.
- Multiframe: Multiframe is a way of editing control points across several keyframes. At the default of none, only a spline's control point on the current keyframe is changed. Setting the menu to All edits the control point on every keyframe. Prev edits the current and previous keyframe, while Next edits the current and next keyframe.
- Onion Skinning: Switching on onion skinning shows a blend of the spline animation in the viewer. It helps when you are lining up spline animation with motion. Picking Onion Skin Settings from the drop down menu lets you set how many overlapping frames appear.
- Roto Assist: Turn on the Roto Assist button as you start painting with the Polyline Stroke tool. As you click to build up the shape's points, the polyline points snap onto the closest edge. A cyan outline flags the points that have snapped onto an edge. The drop down menu offers three chief Roto Assist options: Multiple Points: When on, a single click on a high contrast edge drops several points to map the entire edge at once, sparing you from placing each point on its own. This is a one time only click; the next click reverts to single point edge detection. Distance 8: Opens a dialog for setting the pixel range across which the edge search runs. Reset: Clears the snap attribute on every snapped point. Once reset, those points are no longer available for tracking.

Alter how the toolbar appears by right-clicking it and picking from the choices in the toolbar's contextual menu. The Polylines chapter covers what each of this toolbar's buttons does in depth.

### Ranges Mask [RNG] FUSION

### The Ranges node

### Ranges Mask Node Introduction

Much like the Bitmap mask, the Ranges mask lets images from the node tree serve as masks for nodes and effects. Rather than making a plain luminance-based mask out of a single channel, Ranges supports spline-based selection of low, mid, and high ranges, much as the Color Corrector does.

### Inputs

Within the Node Editor, the Ranges mask node carries two inputs. Input: The orange input takes a 2D image that the mask is built from. Effect Mask: The optional blue input looks for a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask into this input merges the masks, and how that merging is done is set in the Inspector's Paint mode menu.

### Basic Node Setup

You do not strictly need the Ranges node to feed an image into the effect mask input, but, as with the Bitmap node, it opens up options not otherwise on offer. It permits choosing channels beyond RGBA for the mask, plus softness and clipping. In the node tree below, the Ranges node pulls the composite out of the merge and builds a mask for the color correction.

A Ranges node picks out a particular range within the image so as to build a mask.

### Inspector

### Rangers Mask controls

### Controls Tab

The Controls tab serves to refine how the image wired into the orange input becomes the ranges mask. Show View Controls The Show View Controls checkbox switches the display of the mask's onscreen controls in the viewer on or off. With the checkbox off, those onscreen controls, center position, polylines, angles, and the rest, stay out of sight even while the node is selected.

Level The Level control fixes the transparency level of the mask channel's pixels. When the value reads 1.0, the mask is fully opaque (save for a soft edge). Lower values leave the mask partly transparent, the same outcome as turning down an effect's blend control. NOTE: Lowering a mask's level lowers the values of all pixels the mask covers in the mask channel. As an example, with a Circle mask placed above a Rectangle mask, lowering the Circle mask's level lowers the values of all the pixels in the mask channel, although the Rectangle mask beneath remains opaque. Filter This control chooses which filtering algorithm is used as Soft Edge is applied to the mask.

- Box: This method is the fastest, at the cost of quality. Box fits best where only a little blur is needed.
- Bartlett: Sometimes called a Pyramid filter, Bartlett balances speed against quality well.
- Multi-box: Selecting this filter surfaces the Num Passes slider for governing the quality. With 1 and 2 passes the output matches Box and Bartlett in turn, and at 4 passes or above it generally equals Gaussian, in less time and with no edge "ringing."
- Gaussian: Resting on a true Gaussian approximation, the Gaussian filter gives excellent results yet runs slightly slower than the rest. From time to time it can leave an extremely faint edge "ringing" on floating-point pixels.

Soft Edge Drag the Soft Edge slider to feather (blur) the mask via the chosen filter. The higher the value, the farther the edge fades beyond the mask's boundaries. A value of 0.0 yields a crisp, welldefined edge. Paint Mode Wiring a mask into the effect mask input surfaces the Paint mode menu. The Paint mode decides how the mask reaching the effect mask input and the mask formed in the node are merged.

- Merge: Merge is the default for all masks. The new mask blends into the input mask.
- Add: The new mask's values are combined onto the input mask's values.
- Subtract: Throughout the overlapping areas, the new mask values are subtracted from the input mask's values.
- Minimum: Placing the input mask's values next to the new mask, this returns the lowest

(minimum) value.

- Maximum: Placing the input mask's values next to the new mask, this returns the highest

(maximum) value.
