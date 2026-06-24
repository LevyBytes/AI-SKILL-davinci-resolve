# Transform Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Transform Nodes

The Transform nodes provided within Fusion are covered in this chapter.

Each node name carries an abbreviation beside it; those shorthand codes are what you type into the Select Tool dialog when hunting for a tool, and they also surface in scripting references. Throughout this document, treat any node tree that depicts MediaIn nodes under DaVinci Resolve as equivalent to Loader nodes under Fusion Studio, except where a note says otherwise.

### Camera Shake [CSh]

### The Camera Shake node

### Camera Shake Node Introduction

A range of camera-shake-style motion, anywhere from organic to mechanical, can be reproduced by this node. Do not confuse it with the Shake Modifier, whose role is to feed random numeric values into parameters. The Shake modifier is documented separately in Chapter 124, "Modifiers," within the DaVinci Resolve Reference Manual, or alternatively Chapter 64 of the Fusion Reference Manual. For better-quality processing, the Camera Shake node merges its output with neighboring transformation nodes.

### Inputs

A 2D image plus an effect mask attach to the Camera Shake node's two inputs, and the mask serves to confine where the shake takes effect. Input: The primary 2D image that will shake plugs into the orange input. Effect Mask: A mask shape—built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools—feeds the blue input. Wiring a mask here restricts the shake so that only pixels falling inside the mask are affected. The tool finishes processing first, and only then is an effects mask applied to it.

### Basic Node Setup

Feed the image you intend to transform into the Camera Shake background input. To flag regions that the shake ought to skip, run polygon masks into the occlusion mask input.

You can wire the Camera Shake node straight after a MediaIn node, or after any node that hands off a 2D output.

### Inspector

### The Camera Shake Controls tab

### Controls Tab

Offsets, strength, speed, and frequency for the simulated camera-shake movement are all dialed in from the parameters on the Controls tab. Deviation X and Y These two controls set how much shake hits the image horizontally (X) and vertically (Y). The accepted range runs from 0.0 to 1.0. At 1.0, shake positions can land anywhere inside the image's borders. Rotation Deviation This sets how much shake is applied to the rotational axis. The accepted range runs from 0.0 to 1.0. Randomness Raising this control makes the shake motion more erratic and random, while lowering it makes the motion more predictable. Overall Strength This scales the combined amplitude of every parameter, easing the whole effect in and out. At 1.0 the effect plays exactly as the rest of the controls specify. Speed Speed governs the frequency, or rate, at which the shake occurs. Frequency Method This picks the overall waveform of the shake. The frequencies on offer are Sine, Rectified Sine, and Square Wave. Compared to a Sine, a Square Wave yields motion that looks far more mechanical.

Filter Method While rescaling a pixel, nearby pixels are frequently consulted to yield a more believable outcome. The various methods of blending those pixels together are known as filters. The more elaborate filters tend to deliver better quality at the cost of slower computation. Which filter suits a given task usually comes down to how much scaling is involved and what the image itself contains.

- Box: A plain interpolation resize applied to the image.
- Linear: Relies on a basic filter that turns out fairly tidy, quick results.
- Quadratic: Delivers a middling outcome, striking a reasonable balance between

speed and quality.

- Cubic: Yields stronger results on continuous-tone images. Where an image holds fine detail,

the outcome can come out blurrier than you'd want.

- Catmull-Rom: Performs well on continuous-tone images that are scaled down.

On finely detailed images it returns sharp results.

- Gaussian: Roughly matches Bi-Cubic in both speed and quality.
- Mitchell: Resembles Catmull-Rom but handles finely detailed images more effectively. It runs

slower than Catmull-Rom.

- Lanczos: Closely tracks Mitchell and Catmull-Rom, though it is a touch cleaner and slower too.
- Sinc: A sophisticated filter delivering exceptionally sharp, detailed output; in certain cases, though, it can introduce

visible “ringing.”

- Bessel: Behaves much like the Sinc filter while running a little quicker.

Window Method (Sinc and Bessel Only) A handful of filters, Sinc and Bessel among them, would in theory need an unlimited count of pixels to compute precisely. A windowing function speeds this up by approximating the filter and capping how many pixels it has to touch. Whenever you pick a filter that needs windowing, this control becomes visible.

- Hanning: A plain tapered window.
- Hamming: A lightly adjusted variant of Hanning that stops short of tapering completely

down to zero.

- Blackman: A window whose falloff tapers more steeply.
- Kaiser: A more involved window landing somewhere between Hamming and Blackman.

For the most part these filters earn their keep only when you are enlarging an image. To downsize, the Bi-Linear filter is the usual pick; that said, the Catmull-Rom filter adds a touch of sharpening and can help hold onto detail as you scale an image down.

### Example

Resize filters. Reading across, the samples run Nearest Neighbor, then Box, Linear, Quadratic, and Cubic, followed by Catmull-Rom and Gaussian, then Mitchell, Lanczos, Sinc, plus Bessel.

Edges This menu decides how the image's Edges are dealt with.

- Canvas: Makes the edges uncovered by the shake take on the canvas color—typically transparent or black.
- Wrap: Wraps the edges around, so the top carries over to the bottom, the left over to the right, and so forth.
- Duplicate: Repeats the Edges, which leaves a faint smearing at the borders.
- Mirror: Pixels from the image are mirrored outward to reach the frame edge.

Invert Transform Turn this control on to Invert whatever position, rotation, or scaling transformation is present. It comes in handy when you need to precisely undo motion that an upstream Camera Shake introduced. Flatten Transform Switching on the Flatten Transform option stops this node from merging its transformation with the nodes beside it. Transforms arriving from its input may still be concatenated, but its own transformation will not combine with whatever node sits at its output.

### Common Controls

Settings Tab Other Transform nodes carry a copy of the same Settings tab found here in the Inspector. You will find a full account of these shared controls under the “The Common Controls” section at this chapter's close.

### Crop [Crp]

### The Crop node

### Crop Node Introduction

With the Crop node you can carve out a section of an image, or shift the image inside a bigger image area. Note, though, that—unlike a mask—this node genuinely alters the image's resolution. TIP: To crop directly in the viewer, switch on Allow Box Selection at the viewer's upper-left corner while the Crop node is both selected and being viewed. Then drag out a crop rectangle over the region you care about to carry out the crop. NOTE: Since this node alters the image's physical resolution, animating the parameters is discouraged.

### Inputs

A 2D image to be cropped wires into the Crop node's lone input. Input: The primary 2D image you intend to crop attaches to the orange input.

### Basic Node Setup

In the layout below, the Crop node sits between the MediaIn1 node and the Merge's background input. In contrast to a mask tool, cropping the MediaIn1 alters the clip's resolution. Because the cropped MediaIn1 node feeds the orange background input, it also dictates the resolution of the Merge output.

Use the Crop node to carve out a section of an image.

### Inspector

### The Crop Controls tab

### Controls Tab

For cropping the image, the Controls tab offers both XY Offset and XY Size methods. Offset X and Y These controls slide the image off-screen by nudging it left/right or up/down. Whatever is cropped vanishes past the borders of the output image. These control values are expressed in pixels. Size X and Y Reach for these controls to define the vertical and horizontal resolution of the image the Crop node outputs. These control values are expressed in pixels.

Keep Aspect Switched on, the Crop node holds onto the aspect of the input image. Keep Centered Switched on, the Crop node automatically nudges the X and Y Offset controls so the image stays centered. With the XY Offset sliders driven automatically, you steer the cropping through the Size sliders or via the Allow Box Selection button in the viewer. Reset Size This returns the image dimensions to match the input image's size. Reset Offset This returns the X and Y Offsets to their defaults. Change Pixel Aspect Tick this checkbox to expose a Pixel Aspect control, which lets you alter the image’s pixel aspect. Clipping Mode This option picks the method used to deal with the image edges during domain of definition (DoD) rendering. It matters a great deal for nodes such as Blur, which can need samples drawn from areas of the image beyond the current domain.

- Frame: Frame is the default; it forces the node’s domain of definition to span the image's full frame, in effect disregarding the present domain of definition. Should the upstream DoD fall short of the frame, whatever frame area is left over gets handled as black/transparent.
- Domain: Choosing Domain makes the node honor the upstream DoD as it applies its effect. Where the node relies on a large filter, this can produce unwanted clipping.
- None: Picking None skips source-image clipping entirely. As a result, any data the node’s effect needs that would ordinarily fall beyond the upstream DoD gets handled as black/transparent.

### Auto Crop Tab

The Auto Crop tab inspects the chosen channel and crops the image according to that channel’s edges. Whatever auto crop arrives at then shows up over in the Crop tab parameters.

### The Auto Crop tab

RGBA Color Channels Pick which channels get inspected during an Auto Crop. This helps when auto cropping images whose backgrounds are not solid in a given color channel, such as a blue color gradient. Switching a channel off tells Auto Crop to skip it while assessing the image. Auto Crop This examines the image and tries to work out the background color, then trims each edge of the image inward to the first pixel that differs from that color.

### Common Controls

Settings Tab Other Transform nodes carry a copy of the same Settings tab found here in the Inspector. You will find a full account of these shared controls under the “The Common Controls” section at this chapter's close.

### DVE [DVE]

### The DVE node

### DVE Node Introduction

A 3D-image transformation, the DVE (Digital Video Effects) node mirrors the kind of nodes that lived in the old tape-based online editing suites. Image rotations, perspective shifts, and Z moves all fall within its scope. Every transformation lets you specify its axis.

### Inputs

A 2D image, a DVE mask, and an effect mask all attach to the DVE node's three inputs, with the effect mask available to confine where the DVE acts. Input: The primary 2D image the DVE transforms feeds the orange input. DVE Mask: The white DVE mask input masks the image ahead of the DVE transform being carried out, which alters both the image and the mask together. Effect Mask: A mask shape—made from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools—feeds the blue input. Wiring a mask here makes the DVE alter only the portion of the image inside the mask. The tool finishes processing first, and only then is an effects mask applied to it.

### Basic Node Setup

In the example here, the DVE node lands between the MediaIn2 node and the Merge's foreground input. The MediaIn1 node is reshaped within the DVE node and laid over the top of the MediaIn1 node.

The DVE node modifying the foreground input of a Merge node

### Inspector

### The DVE Controls tab

### Controls Tab

Every transform parameter for the DVE lives on the Controls tab. Pivot X, Y, and Z Sets where the axis of rotation and scaling sits. By default this is 0.5, 0.5 for X and Y—the image's center—and 0 for Z, which sits at the middle of Z space. Rotation Order These buttons let you choose the sequence in which rotations get applied to the image. XYZ Rotation Reach for these controls to spin the image around the pivot on the X-, Y-, and Z-axis. Center X and Y This sets where the center of the DVE image sits onscreen. The default of 0.5, 0.5 drops the DVE in the image's center. Z Move This pushes the image in and out along the Z-axis. When animated, it visually resembles an object drawing closer from far away. Perspective This layers extra perspective onto an image that has been rotated on the X- or Y-axis, much like adjusting a camera's Field of View and zoom.

### Masking Tab

The DVE node permits pre-masking of the image it receives. That makes it possible to build transformations out of the masked region of the image while the rest of the image stays untouched.

### The DVE Masking tab

In contrast to ordinary effect masks, here the masking happens before the transformation. Every one of the usual mask types works on the DVE mask. Black Background Switch this on to wipe the region beyond the mask out of the transformed image. Fill Black Switch this on to wipe the region inside the mask (prior to transformation) out of the DVE’s input, in effect cutting the masked region out of the image. Turning on both Black Background and Fill Black leaves only the masked, transformed region visible. Alpha Mode This decides how the DVE treats the image's alpha channel while merging the transformed image regions over the untransformed image.

- Ignore Alpha: Makes the input image’s alpha channel be disregarded, leaving every masked area opaque.
- Subtractive/Additive: Decide whether, internally, the pre-masked DVE image is laid over the input image as Subtractive or as Additive. You need an Additive setting whenever the foreground DVE image is premultiplied—that is, its color-channel pixels have already been multiplied by the alpha-channel pixels. Because of that, transparent pixels always come out black, given that anything times 0 stays 0. The background gets obscured (multiplied by the inverse of the foreground alpha), after which the foreground pixels are simply added on top.

A Subtractive setting is required whenever the foreground DVE image has not been premultiplied. The compositing approach resembles an Additive merge, except the foreground DVE image is first scaled by its own alpha to strip out any background pixels lying beyond the alpha area.

### Common Controls

Settings Tab Other Transform nodes carry a copy of the same Settings tab found here in the Inspector. You will find a full account of these shared controls under the “The Common Controls” section at this chapter's close.

### Letterbox [LBX]

### The Letterbox node

### Letterbox Node Introduction

Reach for the Letterbox node when you need to fit existing images to the frame size and aspect ratios of some other format. Most often it is used to turn film-resolution images into HD-sized frames so they can be viewed on an external television monitor. Where aspect ratios differ, horizontal or vertical black edges get added automatically to make up the difference. This node genuinely alters the image's resolution. NOTE: Since this node alters the image's physical resolution, animating the controls is discouraged.

### Inputs

A 2D image for letterbox/cropping wires into the Letterbox node's lone input. Input: The primary 2D image you intend to letterbox/crop attaches to the orange input.

### Basic Node Setup

In the example below, the Letterbox node serves to alter the resolution of the Merge node’s output. According to how the resolution gets changed, either side pillars or a horizontal letterbox mask is laid in to “fill in” the part of the frame the Merge node output leaves uncovered.

The Letterbox node changing the Merge output resolution while inserting letterbox masking as required.

### Inspector

### The Letterbox Controls tab

### Controls Tab

The Controls tab supplies parameters for tuning the image's resolution and pixel aspect. It can also do either letterboxing or pan-and-scan formatting. Width and Height These control values fix the output image's size, expressed in pixels. TIP: The formatting contextual menu lets you grab a resolution from a list in a hurry. Hover the pointer over the Width or Height controls, then right-click to bring up the contextual menu. At the bottom you'll see a Select Frame Format submenu listing the available frame formats. Choose any entry from the menu and the Height, Width, and Aspect controls are set for you automatically. Auto Resolution Tick this checkbox and the Width and Height sliders are set automatically from the Frame Format settings in the Preferences window for Fusion Studio, or from the DaVinci Resolve Timeline's resolution. Pixel Aspect X and Y These controls fix the output image's pixel aspect ratio. Center X and Y This Center control shifts the image window when paired with Pan-and-Scan mode. While the node is set to Letterbox mode, it does nothing to the image. Mode This control selects the Letterbox node’s mode of operation.

- Letterbox/Envelope: Fixes the input image's aspect and rescales it so it fits the width you specify.
- Pan-and-Scan: Fixes the input image's aspect and rescales it so it fits the height you specify. Where the rescaled input image ends up wider than the specified width, you can lean on the Center control to animate which slice of the rescaled input stays visible.

Filter Method While rescaling a pixel, nearby pixels are frequently consulted to yield a more believable outcome. The various methods of blending those pixels together are known as filters. The more elaborate filters tend to deliver better quality at the cost of slower computation. Which filter suits a given task usually comes down to how much scaling is involved and what the image itself contains.

- Box: A plain interpolation resize applied to the image.
- Linear: Relies on a basic filter that turns out fairly tidy, quick results.
- Quadratic: Delivers a middling outcome, striking a reasonable balance between

speed and quality.

- Cubic: Yields stronger results on continuous-tone images. Where an image holds fine detail,

the outcome can come out blurrier than you'd want.

- Catmull-Rom: Performs well on continuous-tone images that are scaled down.

On finely detailed images it returns sharp results.

- Gaussian: Roughly matches Bi-Cubic in both speed and quality.
- Mitchell: Resembles Catmull-Rom but handles finely detailed images more effectively. It runs

slower than Catmull-Rom.

- Lanczos: Closely tracks Mitchell and Catmull-Rom, though it is a touch cleaner and slower too.
- Sinc: A sophisticated filter delivering exceptionally sharp, detailed output; in certain cases, though, it can introduce

visible “ringing.”

- Bessel: Behaves much like the Sinc filter while running a little quicker.

Window Method (Sinc and Bessel Only) A handful of filters, Sinc and Bessel among them, would in theory need an unlimited count of pixels to compute precisely. A windowing function speeds this up by approximating the filter and capping how many pixels it has to touch. Whenever you pick a filter that needs windowing, this control becomes visible.

- Hanning: A plain tapered window.
- Hamming: A lightly adjusted variant of Hanning that stops short of tapering completely

down to zero.

- Blackman: A window whose falloff tapers more steeply.
- Kaiser: A more involved window landing somewhere between Hamming and Blackman.

For the most part these filters earn their keep only when you are enlarging an image. To downsize, the Bi-Linear filter is the usual pick; that said, the Catmull-Rom filter adds a touch of sharpening and can help hold onto detail as you scale an image down.

### Example

A range of resize filters. Reading across, the samples run Nearest Neighbor, then Box, Linear, Quadratic, and Cubic, followed by Catmull-Rom and Gaussian, then Mitchell, Lanczos, Sinc, plus Bessel.

### Common Controls

Settings Tab Other Transform nodes carry a copy of the same Settings tab found here in the Inspector. You will find a full account of these shared controls under the “The Common Controls” section at this chapter's close.

### Planar Transform [PXF]

### The Planar Transform node

The Planar Transform node takes the perspective distortions a Planar Tracker node produces and lays them onto any input mask or masked image. You can lean on the Planar Transform node to cut down the hours sunk into rotoscoping objects. The idea behind this workflow rests on the fact that the Planar Tracker node is able to track objects that are only loosely planar. Once an object has been tracked, a Planar Transform node can warp a rotospline so that it roughly trails the object across time. After that, the rotospline still needs detailed cleanup by hand. How much tedious rotoscoping time you save hinges on how faithfully the Planar Tracker followed the object, and the savings can be considerable. The trick to this technique is spotting the cases where the Planar Tracker does a strong job on an object that has to be rotoscoped. Here is a rough sketch of the steps involved: 1 Track: With a Planar Tracker node, choose a pattern that stands in for the object you want to rotoscope. Track the shot (consult the tracking workflow in the Track section covering the Planar Tracker node). 2 Create a Planar Transform node: Click the Create Planar Transform button on the Planar Tracker node to make one. That brand-new Planar Transform node can be cut and pasted into a different composition however you like. 3 Rotoscope the object: Jump to any frame the Planar Tracker tracked. If you are unsure whether a frame got tracked, check the Spline Editor for a tracking keyframe on the Planar Transform node. Wire a Polygon node into the Planar Transform node, and while viewing the Planar Transform node, rotoscope the object. 4 Refine: Scrub along the timeline to gauge how closely the polygon trails the object, and tweak the polyline on any frames where it drifts. You can also drop in new points to sharpen the polygon further.

### Inputs

There are just two inputs on the Planar Transform: Image Input: A 2D image that the transform will act on plugs into the orange image input. Effect Mask: A mask shape—drawn from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools—feeds the blue input. Wiring a mask here confines the Planar Transform's output to particular regions.

### Basic Node Setup

In the example below, a Planar Transform node is placed so it sits between a masked MediaIn2 node and a Merge node's foreground input. The background MediaIn1 node runs into the Planar Tracker that was used to produce the Planar Transform. After the Planar Transform exists, you no longer need the Planar Tracker in the node tree.

### A Planar Transform creating a match move

### Inspector

### The Planar Transform Controls tab

### Controls Tab

There are only a handful of controls on the Planar Transform node, and all of them sit on the Controls tab. It exists to take the analyzed Planar Tracking data and lay it down as a match move. Reference Time This refers to the moment in time from which the pattern was sampled in the Planar Tracker node that generated the Planar Transform. Right-Click Here for Track Spline The Track spline holds the perspective-distortion data, kept as 4 x 4 matrices. When a Planar Transform node is exported out of a Planar Tracker node, the Track spline the Planar Tracker produced is shared by linking it to the Planar Transform node. One upshot of sharing the Track spline this way is that altering the track inside the Planar Tracker node automatically refreshes the Planar Transform. Keep in mind that you can inspect this spline in the Spline Editor, which helps reveal how many frames were tracked.

### Common Controls

Settings Tab Other Tracking nodes carry a copy of the same Settings tab found here in the Inspector. You will find a full account of these shared controls under the “The Common Controls” section at this chapter's close.

### Resize [Rsz]

### The Resize node
