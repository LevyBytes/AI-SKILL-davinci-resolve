# Mask Nodes (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Average: Works out the mean (half the total) across the new mask together with the input mask.
- Multiply: Takes the input mask’s values and multiplies them by those of the new mask.
- Replace: Wherever the two overlap, the new mask stands in fully for the input mask. Spots reading

zero (completely black) over in the new mask leave the input mask untouched.

- Invert: Wherever the new mask covers the input mask, those areas flip; white shifts to

black and the reverse. Gray patches in the new mask end up partly inverted.

- Copy: This mode throws out the input mask altogether and draws every value from the new mask.
- Ignore: This mode throws out the new mask altogether and draws every value from the input mask.

Invert Ticking this checkbox flips the whole mask. Unlike the Invert Paint mode, the checkbox reaches every pixel, no matter whether the new mask covers it or not. Center X and Y The position of the ranges mask is adjusted through these controls. Fit Input This menu decides how the image source is dealt with when it doesn’t match the dimensions of the generated mask. As an example, below, a 720 x 576 image source (yellow) goes toward generating a 1920 x 1080 mask (gray). Crop: When the image source is smaller than the generated mask, it lands according to the X/Y controls, screening off only part of the mask. When the image source is larger than the generated mask, it lands according to the X/Y controls and is trimmed at the mask’s borders. Stretch: The image source is pulled in X and Y to fill out the generated mask’s full dimensions. That can introduce visible distortion of the image source. Inside: The image source scales evenly until one of its dimensions (X or Y) meets the inside dimensions of the mask. Depending on how the image source and mask background compare in size, either the width or else the height of the image source may get cropped to suit the corresponding dimension of the mask.

Width: The image source scales evenly until its width (X) meets the mask’s width. Hinging on the relative dimensions of the image source and mask, the Y dimension of the image source might fall short of the mask’s Y dimension, leading either to cropping of the image source in Y or to the image source not spanning the mask’s height fully.

Height: The image source scales evenly until its height (Y) meets the mask’s height. Hinging on the relative dimensions of the image source and mask, the X dimension of the image source might fall short of the mask’s X dimension, leading either to cropping of the image source in X or to the image source not spanning the mask’s width fully.

Outside: The image source scales evenly until one of its dimensions (X or Y) meets the outside dimensions of the mask. Hinging on the relative dimensions of the image source and mask, either the width or the height of the image source may be cropped or fall short of the corresponding dimension of the mask.

Channel The Channel menu sets which Channel of the input image goes toward building the mask. What you can pick from spans the red, green, blue, plus alpha channels; the hue, luminance, or saturation values; or else the input image’s auxiliary coverage channel (where one is supplied). Shadows/Midtones/Highlights These buttons pick which range the node sends out as a mask. White pixels stand for the pixels reckoned to belong to the range, while black pixels lie outside it. Picking Shadows, for instance, would render pixels reckoned as shadows white and pixels that aren’t shadows black. Mid gray pixels sit only partway in the range and miss out on the full force of any color adjustments to that range.

Channel The Channel selection buttons in this tab let you pull a mask from the range of one particular color channel. By default, Fusion turns to the luminance channel as the color ranges are examined. Mini Spline Editor You set the reach of the ranges by working the spline handles. Four spline points exist, each carrying a single Bézier handle. The pair of handles up top mark where the shadow and highlight ranges begin; the pair down below mark where the range ends. Falloff is governed through the Bézier handles. No dedicated control exists for the midtones range, since its span is taken as the gap between the shadow and highlight ranges. Put another way, once the low and high masks are in place, the midtones are all that remains. The X and Y text controls beneath the Mini Spline Editor let you key in exact positions for whichever Bézier point or handle is selected. Presets This drops the splines into two widely-used setups. The Simple button yields a plain linear-weighted selection, whereas the Smooth button leans on a more natural falloff.

### Common Controls

Image and Settings Tabs Other mask nodes carry the same Image and Settings tabs found here in the Inspector. A full account of these shared controls appears at this chapter’s end within “The Common Controls” section.

### Rectangle Mask [Rec]

### The Rectangle node

### Rectangle Mask Node Introduction

What the Rectangle mask makes are plain square or rectangular masks. Out of the box it builds a rectangle matching the comp’s aspect ratio, yet you get separate control over width, height, and angle, opening up a broad range of rectangular shapes.

### Inputs

A single effect mask input sits on the Rectangle mask node. Effect Mask: Into the optional blue input goes a mask shape made from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here merges the masks. Just how they merge is governed by the Paint mode menu over in the Inspector.

### Basic Node Setup

For turning out rectangular shapes, the Rectangle mask node comes in handy. Below, the Rectangle mask serves to make a colored square by carving a square shape out of a background node.

### Inspector

A Rectangle mask node carving a colored square out of a Background node

### Rectangle Mask controls

### Controls Tab

The Controls tab serves to fine-tune how the rectangle looks once you’ve drawn it in the viewer. Show View Controls The Show View Controls checkbox switches the display of the mask’s onscreen controls in the viewer on or off. With this checkbox off, onscreen controls — center position, polylines, angles, and the rest — stay hidden, even while the node is selected. Level The Level control fixes the transparency level of the pixels within the mask channel. At a value of 1.0, the mask is fully opaque (barring a soft edge). Lower values make the mask partly transparent. The outcome matches turning down an effect’s Blend control.

NOTE: Dropping a mask’s level pulls down the values of every pixel the mask covers within the mask channel. As an example, when a Circle mask sits over a Rectangle mask, lowering the Circle mask’s level pulls down the values of all the pixels in the mask channel, even while the Rectangle mask underneath stays opaque. Filter This control picks the filtering algorithm put to work when Soft Edge is applied to the mask.

- Box: The quickest method, though quality suffers. Box fits best where blur amounts are minimal.
- Bartlett: Also called a Pyramid filter, Bartlett strikes a fair balance of speed against quality.
- Multi-box: Choosing this filter brings up the Num Passes slider, handing you control of the quality. At 1 and 2 passes, the results match Box and Bartlett, respectively. From 4 passes upward, the results are typically on par with Gaussian, faster and free of edge “ringing.”
- Gaussian: Drawing on a true Gaussian approximation, the Gaussian filter delivers excellent results, albeit a touch slower than the rest. Now and then it can leave a faint edge “ringing” on floating-point pixels.

Soft Edge Reach for the Soft Edge slider to blur (feather) the mask through the chosen filter. Raising the value makes the edge fade off well past the mask’s boundaries. A value of 0.0 yields a sharp, crisply-defined edge. Border Width The Border Width control tunes how thick the mask’s edge is. With the solid checkbox switched on, the border swells or thins the mask. When the mask isn’t solid, the mask shape renders as an outline, its width set by the Border Width setting. Paint Mode Wiring a mask into the effect mask input reveals the Paint mode menu. The Paint mode decides how the mask coming into the effect mask input and the mask the node builds get combined.

- Merge: Merge is the default across all masks. The new mask blends into the input mask.
- Add: The new mask’s values pile onto the input mask’s values.
- Subtract: Across the overlapping areas, the new mask values come off the input mask’s values.
- Minimum: Weighing the input mask’s values against the new mask, this shows the lowest

(minimum) value.

- Maximum: Weighing the input mask’s values against the new mask, this shows the highest

(maximum) value.

- Average: Works out the mean (half the total) across the new mask together with the input mask.
- Multiply: Takes the input mask’s values and multiplies them by those of the new mask.
- Replace: Wherever the two overlap, the new mask stands in fully for the input mask. Any spot sitting

at zero (completely black) within the new mask makes no difference to the input mask.

- Invert: Wherever the new mask covers the input mask, those areas flip: white becomes

black and back again. Gray regions of the new mask come out partly inverted.

- Copy: This mode throws out the input mask altogether and draws every value from the new mask.
- Ignore: This mode throws out the new mask altogether and draws every value from the input mask.

Invert Ticking this checkbox flips the whole mask. Unlike the Invert Paint mode, this checkbox reaches every pixel, no matter whether the new mask covers it. Solid With the Solid checkbox on, the mask is filled to be transparent (white) unless it has been inverted. Switch it off and the spline renders as just an outline, its thickness governed by the Border Width slider. Center X and Y The position of the Rectangle mask is adjusted through these controls. Width and Height Lean on these controls to adjust, independently of one another, the X or Y scale of the rectangular effect mask. As an alternative, drag the rectangle’s edges in the viewer to size it interactively. Corner Radius Corner Radius lets the corners of the Rectangle mask be rounded off. A value of 0.0 means no rounding whatsoever, leaving the rectangle with sharp corners. A value of 1.0 rounds the corners as much as possible. Angle Shift the rotation angle of an effect mask by sliding the Angle control left or right. Values may be keyed into the input boxes provided. As an alternative, use the onscreen controls, dragging the little circle at the tip of the dashed angle line to spin the ellipse interactively.

### Common Controls

Image and Settings Tabs Other mask nodes carry the same Image and Settings tabs found here in the Inspector. A full account of these shared controls appears at this chapter’s end within “The Common Controls” section.

### Triangle Mask [Tri]

### The Triangle node

### Triangle Mask Node Introduction

What the Triangle mask makes are plain triangular masks. What sets it apart is its lack of any Center, Size, or Angle control. Unlike most other mask types, all three of the triangle’s points can latch onto a tracker or motion path.

### Inputs

A single effect mask input sits on the Triangle mask node. Effect Mask: Into the optional blue input goes a mask shape made from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here merges the masks. Just how they merge is governed by the Paint mode menu over in the Inspector.

### Basic Node Setup

For turning out triangular shapes, the Triangle mask node comes in handy. Below, the Triangle mask serves to make a colored triangle by carving a triangular shape out of a background node.

### Inspector

A Triangle mask node carving a colored Triangle shape out of a Background node

### Triangle Mask controls

### Controls Tab

The Controls tab serves to fine-tune how the triangle looks once you’ve drawn it in the viewer. Show View Controls The Show View Controls checkbox switches the display of the mask’s onscreen controls in the viewer on or off. With this checkbox off, onscreen controls — center position, polylines, angles, and the rest — stay hidden, even while the node is selected.

Level The Level control fixes the transparency level of the pixels within the mask channel. At a value of 1.0, the mask is fully opaque (barring a soft edge). Lower values render the mask partly transparent. The outcome matches turning down an effect’s Blend control. NOTE: Dropping a mask’s level pulls down the values of every pixel the mask covers within the mask channel. As an example, when a Circle mask sits over a Rectangle mask, lowering the Circle mask’s level pulls down the values of all the pixels in the mask channel, even while the Rectangle mask underneath stays opaque. Filter This control picks the filtering algorithm put to work when Soft Edge is applied to the mask.

- Box: The quickest method, but quality drops off. Box suits best where blur amounts stay minimal.
- Bartlett: Known too as a Pyramid filter, Bartlett lands a sound trade-off of speed versus quality.
- Multi-box: Choosing this filter brings up the Num Passes slider, letting you steer the quality. At 1 and 2 passes, the results match Box and Bartlett, respectively. From 4 passes upward, the results usually rival Gaussian, in less time and with no edge “ringing.”
- Gaussian: Relying on a true Gaussian approximation, the Gaussian filter gives excellent results, though it runs a bit slower than the others. On occasion it can throw an extremely slight edge “ringing” onto floating-point pixels.

Soft Edge Reach for the Soft Edge slider to blur (feather) the mask through the chosen filter. Raising the value makes the edge fade off well past the mask’s boundaries. A value of 0.0 produces a sharp, crisply-defined edge. Border Width The Border Width control tunes how thick the mask’s edge is. With the solid checkbox switched on, the border swells or thins the mask. When the mask isn’t solid, the mask shape renders as an outline, its width set by the Border Width setting. Paint Mode Wiring a mask into the effect mask input reveals the Paint mode menu. The Paint mode decides how the mask coming into the effect mask input and the mask the node builds get combined.

- Merge: Merge is the default across all masks. The new mask blends into the input mask.
- Add: The new mask’s values pile onto the input mask’s values.
- Subtract: Across the overlapping areas, the new mask values come off the input mask’s values.
- Minimum: Weighing the input mask’s values against the new mask, this shows the lowest

(minimum) value.

- Maximum: Weighing the input mask’s values against the new mask, this shows the highest

(maximum) value.

- Average: Works out the mean (half the total) across the new mask together with the input mask.
- Multiply: Takes the input mask’s values and multiplies them by those of the new mask.
- Replace: Wherever the two overlap, the new mask stands in fully for the input mask. Wherever the new mask reads zero (completely black), the input mask carries on unchanged.
- Invert: Wherever the new mask covers the input mask, those areas flip: white goes to black and the other way round. Gray portions of the new mask wind up partly inverted.
- Copy: This mode throws out the input mask altogether and draws every value from the new mask.
- Ignore: This mode throws out the new mask altogether and draws every value from the input mask.

Invert Ticking this checkbox flips the whole mask. Unlike the Invert Paint mode, this checkbox reaches every pixel, no matter whether the new mask covers it. Solid With the Solid checkbox on, the mask is filled to be transparent (white) unless it has been inverted. Switch it off and the spline renders as just an outline, with the Border Width slider setting how thick it is. Point 1, Point 2, Point 3 These controls report the position coordinates of the triangle’s three corners. Any point can be published, wired to other controls, animated along a path, or latched onto trackers. You carry these tasks out by right-clicking the Position control or by clicking the point directly in the viewer.

### Common Controls

Image and Settings Tabs Other mask nodes carry the same Image and Settings tabs found here in the Inspector. A full account of these shared controls appears at this chapter’s end within “The Common Controls” section.

### Wand Mask [Wnd]

### The Wand node

### Wand Mask Node Introduction

The Wand mask masks an image off a wand-style selection, much like the Magic Wand tool that Adobe Photoshop offers. Just as with a Bitmap mask, whatever image lives in the composition can serve as the mask’s source. As a rule the default proves handiest, where the source image is the input of the node the mask gets applied to. Adding a Wand mask to a node brings a crosshair up in the viewers. Position this crosshair over the image to pick the color used to build the Wand mask. The mask comes together by reading the pixel color beneath the selection point and folding that color into the mask. From there the mask grows outward, reading the pixels around the selection point. Surrounding pixels join the mask when their color matches. The mask quits growing once no connecting pixels remain inside the mask’s color range.

### Inputs

In the Node Editor, the Wand mask node carries two inputs. Input: The orange input takes a 2D image out of which the mask is built. Effect Mask: Into the optional blue input goes a mask shape made from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here merges the masks. Just how they merge is governed by the Paint mode menu over in the Inspector.

### Basic Node Setup

You don’t actually need the Wand mask node to wire an image into the effect mask input, yet like the Bitmap node it offers options you couldn’t otherwise reach. It lets you choose channels beyond RGBA for the mask, along with softness and clipping. In the node tree below, the Wand node pulls the composite off the merge, building a mask for the color correction.

A Wand node picks out a particular region of the image so as to build a mask.

### Inspector

### Wand Mask controls

### Controls Tab

The Controls tab serves to fine-tune how the mask looks once the Wand has made a selection in the viewer.

Show View Controls The Show View Controls checkbox switches the display of the mask’s onscreen controls in the viewer on or off. With this checkbox off, onscreen controls — center position, polylines, angles, and the rest — stay hidden, even while the node is selected. Level The Level control fixes the transparency level of the pixels within the mask channel. At a value of 1.0, the mask is fully opaque (barring a soft edge). Lower values leave the mask partly transparent. The outcome matches turning down an effect’s Blend control. NOTE: Dropping a mask’s level pulls down the values of every pixel the mask covers within the mask channel. As an example, when a Circle mask sits over a Rectangle mask, lowering the Circle mask’s level pulls down the values of all the pixels in the mask channel, even while the Rectangle mask underneath stays opaque. Filter This control picks the filtering algorithm put to work when Soft Edge is applied to the mask.

- Box: This one is fastest, though quality is reduced. Box works best for small amounts of blur.
- Bartlett: Otherwise termed a Pyramid filter, Bartlett offers a decent balance between speed and quality.
- Multi-box: Picking this filter surfaces the Num Passes slider and hands you control of the quality. At 1 and 2 passes, the results equal Box and Bartlett, respectively. From 4 passes on up, the results are usually as fine as Gaussian, quicker and with no edge “ringing.”
- Gaussian: Built on a true Gaussian approximation, the Gaussian filter returns excellent results, yet runs a little slower than the rest. In certain cases it may yield an extremely slight edge “ringing” on floating-point pixels.

Soft Edge Reach for the Soft Edge slider to blur (feather) the mask through the chosen filter. Raising the value makes the edge fade off well past the mask’s boundaries. A value of 0.0 makes a sharp, crisply-defined edge. Paint Mode Wiring a mask into the effect mask input reveals the Paint mode menu. The Paint mode decides how the mask coming into the effect mask input and the mask the node builds get combined.

- Merge: Merge is the default across all masks. The new mask blends into the input mask.
- Add: The new mask’s values pile onto the input mask’s values.
- Subtract: Across the overlapping areas, the new mask values come off the input mask’s values.
- Minimum: Weighing the input mask’s values against the new mask, this shows the lowest

(minimum) value.

- Maximum: Weighing the input mask’s values against the new mask, this shows the highest

(maximum) value.

- Average: Works out the mean (half the total) across the new mask together with the input mask.
- Multiply: Takes the input mask’s values and multiplies them by those of the new mask.
- Replace: Wherever the two overlap, the new mask stands in fully for the input mask. Anywhere the new mask holds zero (completely black), the input mask is left as it was.
- Invert: Wherever the new mask covers the input mask, those areas flip; white turns into black and back the other way. Gray stretches of the new mask come through partly inverted.
- Copy: This mode throws out the input mask altogether and draws every value from the new mask.
- Ignore: This mode throws out the new mask altogether and draws every value from the input mask.

Invert Ticking this checkbox flips the whole mask. Unlike the Invert Paint mode, this checkbox reaches every pixel, no matter whether the new mask covers it. Selection Point A pair of X and Y coordinates, the Selection Point pins down where within the source image the Wand mask draws its opening color sample. In the viewers this control also appears as a crosshair. You can set the selection point by hand, or wire it to a tracker, a path, or other expressions. Color Space The Color Space button group fixes which color space is used while choosing the mask’s source color. Among the spaces the Wand mask can run in are RGB, YUV, HLS, and LAB. Channel Through the Channel button group you decide whether the masked color comes from all three of the image’s color channels, from the alpha channel, or from a single channel alone. Exactly what the buttons are labeled hinges on the color space chosen for the Wand mask operation. Where the color space is RGB, the choices are R, G, or B. Where YUV is the color space, the choices are Y, U, or V. Range The Range slider governs the spread of colors around the source color taken into the mask. Left at 0.0, only pixels sharing the source’s exact color count as part of the mask. The higher you set it, the more nearby colors in the source are taken as wholly part of the mask. Range Soft Edge The Range Soft Edge fixes the falloff range of the colors picked. Any pixel inside the range set above counts as 100% within the mask. With the soft range at 0.0, no further pixels are weighed for the mask. Raising the soft range pulls in more colors that sit close to, yet not quite inside, the range covered by the mask. Those pixels turn out semitransparent in the mask

### The Common Controls

Several identical controls in the Inspector are shared among nodes that build masks. The controls common to mask nodes are described in this section.

### Inspector

### Mask node Image tab

### Image Tab
