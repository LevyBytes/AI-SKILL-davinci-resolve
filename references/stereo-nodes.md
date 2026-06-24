# Stereo Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Stereo Nodes

This chapter walks through the Stereo nodes that Fusion offers. Stereoscopic nodes appear only within Fusion Studio and DaVinci Resolve Studio.

You can type the abbreviation beside each node's name into the Select Tool dialog while hunting for tools, and the same shorthand applies in scripting references. Throughout this document, any node tree that depicts MediaIn nodes in DaVinci Resolve can be read as equivalent to Loader nodes in Fusion Studio, except where stated otherwise.

### Anaglyph [ANA]

### The Anaglyph node

NOTE: You'll find the Anaglyph node solely within Fusion Studio and DaVinci Resolve Studio.

### Anaglyph Node Introduction

You reach for the Anaglyph node to build stereoscopic pictures out of distinct left eye and right eye images. Typically it sits at the close of a stereoscopic pipeline, where it shows or hands off the finished result.

### Inputs

Three connections sit on the Anaglyph node, namely a left eye input, a right eye input, plus an effect mask. Left Eye Input: Feed the orange input the 2D picture that stands for the left eye of your stereo comp. Right Eye Input: Feed the green input the 2D picture that stands for the right eye of your stereo comp. Effect Mask: The blue input expects a mask shape built from polylines, simple primitive forms, paint strokes, or bitmaps coming from other tools. Wiring a mask here confines the stereoscopic creation to just the pixels lying inside that mask.

### Basic Node Setup

You normally drop the Anaglyph node at the tail of a stereoscopic node tree so it can present the finished result. With distinct left- and right-eye pictures, the left eye image goes into the orange input while the right eye image goes into the node's green input. With horizontally or vertically stacked pictures that already hold both left- and right-eye data, only the orange input gets a connection.

An Anaglyph node using separate left and right eye inputs

### Inspector

### The Anaglyph Controls tab

### Controls Tab

With the parameters found in the Controls tab, the individual images get merged into a stereoscopic output. Color Type Menu The Color Type menu lets you select among various color encodings to suit whichever display device you favor. So your stereo glasses match, pick from these encodings: Red/Cyan, Red/Green, Red/ Blue, Amber/Blue, and Green/Magenta. Of these, Red/Cyan sees the most use.

### The Anaglyph Color Type menu

Method Beyond the color chosen to encode the image, the Method menu offers a further five approaches to pick from: Monochrome, Half-color, Color, Optimized, and Dubois. Each is explained in the entries that follow.

### The Anaglyph Method menu

- Monochrome: Take a Red/Cyan Color Type as the example: the left eye holds the left image's luminance, which lands in the red channel of the output. The right eye holds the right image's luminance, which lands in the output's green and blue channels.
- Half-Color: Again assuming a Red/Cyan Color Type, the left eye holds the left image's luminance, deposited into the red channel of the output. The right eye instead holds the color channels of the right image that correspond to that eye's glasses color.

### Monochrome

### Half-Color

- Color: The left eye holds the color channels of the left image matching that eye's glasses color, and the right eye holds the color channels of the right image matching that eye's glasses color.
- Optimized: Take red/cyan glasses, for instance: the brightness reaching the viewer through the left eye comes out far dimmer than the brightness through the right eye. Going by the usual ITU-R 601 luminance ratios, the red eye delivers 0.299 brightness whereas the cyan eye delivers 0.587+0.114=0.701 brightness—more than double. That brightness gap across the eyes can trigger what's known as retinal rivalry or binocular rivalry, capable of wrecking the stereo effect. With the Optimized method, the right eye is built exactly as the Color method builds it. The left eye likewise draws on the green and blue channels, but paired with a brightness boost that cuts down retinal rivalry. Because it pulls the identical pair of channels from each source image, it leaves the third channel unreproduced. As an example, the red output channel receives 1.05× the green plus 0.45× the blue channels of the left image, while the output's green and blue channels receive the green and blue channels of the right image. The red component of both the left and right images goes unused.

### Color

### Optimized

- Dubois: When colors are reasonably saturated, the Half-color, Color, and Optimized methods can bring on retinal rivalry, since the color reaches only a single eye. Picture red/ cyan glasses: a saturated green object reads as black through the red eye yet green through the cyan eye. By drawing on the spectral behavior of red/cyan glasses specifically together with CRT (Trinitron) phosphors, the Dubois method yields a superior anaglyph that, on the whole, lessens the retinal rivalry stemming from such per-eye color discrepancies. It likewise tends to curb the ghosting that appears as one eye 'leaks' into the other. Fusion's specially computed matrix targets red/ cyan glasses and is not offered for other glasses types. And because it derives from CRT color primaries, it may fall short on a typical LCD (even so, it will most likely still yield less retinal rivalry and ghosting than the alternative methods).

### Dubois

Swap Eyes Lets you trade the left and right eye inputs with little effort. Horiz Stack Accepts an image whose left- and right-eye data sit side by side horizontally. Such images often go by the names “crosseyed” or “straight stereo.” Just wire that single image into the node's orange input. The node then builds an image half as wide as the original, drawing the left half of the source for the left eye and the right half of the source for the right eye. Color encoding follows whatever color type and method you specified. Vert Stack Accepts an image whose left- and right-eye data sit stacked vertically. Just wire that single image into the node's orange input. The node then builds an image half as tall as the original, drawing the bottom half of the source for the left eye and the top half of the source for the right eye. Color encoding follows whatever color type and method you specified.

### Common Controls

Settings Tab You'll find the Inspector's Settings tab repeated across the other Stereo nodes as well. Full coverage of these shared controls sits at this chapter's close, under the “The Common Controls” section.

### Combiner [Com]

### The Combiner node

NOTE: You'll find the Combiner node solely within Fusion Studio and DaVinci Resolve Studio.

### Combiner Node Introduction

Fed two stereoscopic inputs, the Combiner node produces what are called “stacked images” holding the left and right eye, arranged either beside one another or one above the other. Stereoscopic nodes ship only with Fusion Studio and DaVinci Resolve Studio.

### Inputs

The Combiner node's pair of inputs receive the two images that will be merged into a stacked stereo image. Image 1 Input: Wire the orange input to the 2D picture standing for the left eye within the stereo comp. Image 2 Input: Wire the green input to the 2D picture standing for the right eye within the stereo comp.

### Basic Node Setup

In the example below, both a left eye image and a right eye image feed the Combiner node so it can produce one stacked stereo image. Writing the stacked stereo images out as EXR files is often more efficient than computing the disparity on the fly.

Feeding a Combiner node both a left-eye and a right-eye image produces one stacked stereo image.

### Inspector

### Controls Tab

For stacking, route the left eye image into the orange input and the right eye image into the node's green input. Combine Three choices in the Combine menu govern how the two images become a stacked stereo image.

- None: Nothing happens here. What comes out matches the left eye input exactly.
- Horiz: The two images stack horizontally, side by side, with whatever feeds the

left eye input placed on the left. The result is an output image twice as wide as the input.

- Vert: The two images stack vertically, one over the other, with whatever feeds

the left eye input placed at the bottom. The result is an output image twice as tall as the input.

- Layers: This reveals layer name fields so you can rename the layers.

Swap Eyes Lets you trade the left and right eye input without fuss. Add Metadata Metadata travels alongside the images, and this checkbox lets you append it to whatever metadata already exists. To inspect Metadata, point the viewer's SubView menu at Metadata.

### Common Controls

Settings Tab This same Inspector Settings tab recurs on the other Stereo nodes too. A thorough walkthrough of these shared controls lives at the end of this chapter, within the “The Common Controls” section.

### Disparity [Dis]

### The Disparity node

NOTE: You'll find the Disparity node solely within Fusion Studio and DaVinci Resolve Studio.

### Disparity Node Introduction

Disparity computes the left/right offset across the frames of a stereo pair. It additionally computes the vertical disparity between the left/right images, which normally runs far smaller than the horizontal disparity and ideally should be 0 to keep viewing discomfort to a minimum. While inspecting the Disparity node's output in the views, your eye picks out quality and detail in the Disparity map more readily from either the grayscale X disparity or Y disparity than from the combined XY disparity shown as a Red/ Green color image.

The disparity that gets generated is kept in the output image's Disparity aux channel: the left image holds the left > right disparity while the right image holds the right > left disparity. Since disparity operates by pairing regions in the left eye with regions in the right eye through comparison of colors and color gradients, the colors in both eyes need to be as alike as you can make them. For that reason, color correcting beforehand is wise. It is equally wise to trim off any black borders ringing the frames, because those throw off the disparity tracking (and they also cause trouble if you lean on the Color Corrector's histogram match feature for the color matching). Under Stack mode, the left and right outputs hand back the same image. Should the left and right images carry an overall vertical offset of more than a handful of pixels, the disparity tracking algorithm benefits when you pre-align features across the left/right eyes vertically with a Transform node. Fine details are prone to vanishing during tracking whenever a sizable vertical offset separates the left/right eyes. Think about running a SmoothMotion node over your disparity channel. Doing so can cut the time-dependent flickering that shows up when you warp an eye. Weigh, too, whether to strip lens distortion before the disparity is computed. Skip that and your Disparity map turns into a blended Disparity and Lens Distortion map. There are upsides and downsides to this. A downside is that performing a vertical alignment afterward also undoes the lens distortion effects. To trim the computation time, begin by tweaking the Proxy and Number of Iterations sliders. The Disparity node offers no support for RoI or DoD.

### Inputs

The Disparity node's two inputs receive the left and right images. Left Input: Route either the left eye image or the stacked image into the orange input. Right Input: Route the right eye image into the green input. You only get access to this input when the Stack Mode menu sits on Separate.

### Outputs

Departing from the way most Fusion nodes work, Disparity provides two outputs, one per eye. Left Output: This carries the left eye image plus a fresh disparity channel, or a Stacked Mode image plus a fresh disparity channel. Right Output: This carries the right eye image plus a fresh disparity channel. The output only shows up when Stack Mode is set to Separate.

### Basic Node Setup

Down below, a left eye image together with a right eye image feed the Disparity node. From there the Disparity node sends each eye onward to Saver nodes. Writing the stereo images out as EXR files is often more efficient than computing the disparity on the fly.

Feeding a Disparity node both a left-eye and a right-eye image lets it build and render a stereo image

### Inspector

### The Disparity Controls tab

Proxy (for Tracking) The input images get scaled down by the proxy factor, tracked to derive the disparity, and then the resulting disparities get scaled back up again. Its sole purpose is to accelerate the disparity calculation, which can run slow. Computation time scales roughly with how many pixels the image holds. So a proxy scale of 2 yields a 4x speedup, and a proxy scale of 3 yields a 9x speedup. Broadly, a 1:1 proxy produces the most detailed flow, though bear in mind this hinges heavily on how much noise and film grain are present. With noise in heavy amounts, it can wipe out any benefit you'd gain stepping from 2:1 down to 1:1 proxy. In certain cases it can even degrade things. Picture the Proxy setting as behaving like a crude low-pass filter that strips noise and grain. Advanced The Advanced settings region holds parameter controls for fine-tuning how the Disparity map is calculated. Its defaults were settled on as the best starting values after experimenting across a wide variety of shots, and they make a sound baseline. Most of the time, no fiddling with the Advanced settings is called for. Smoothness This governs how smooth the disparity is. Raise it to better cope with noise; lower it to coax out additional detail. Edges This slider is a further smoothness control, but one keyed to the color channel. Its usual effect is to dictate how closely the disparity's edges trace the color images' edges. At a lower value the disparity grows smoother and is apt to overshoot edges. At a higher value the disparity's edges hug the color images' edges more tightly, and detail from the color channels begins bleeding into the disparity, which is rarely what you want. As a loose rule of thumb, lean toward higher values when the disparity feeds a Z channel for post effects such as depth of field, but lean toward lower values when the disparity drives interpolation. Broadly, an Edges slider set too high can bring on streaked-out edges where the disparity is used for interpolation.

Match Weight This dictates how neighboring pixels in the left image are paired up with neighboring pixels in the right image. A lower value matches large structural color features. A higher value matches small, sharp shifts in the color. A sound choice for this slider usually lands in the [0.7, 0.9] range. Pushing this option higher tends to sharpen the matching wherever differences arise from gently varying shadows or local lighting changes between the left and right images. You should nonetheless color match the starting images so they resemble each other as closely as possible; this option mainly assists with local variations (e.g., lighting differences from light passing through a mirror rig). Mismatch Penalty This dictates how steeply the penalty for mismatched regions climbs as those regions grow more unlike. The slider lets you balance between Quadratic (lower values) and Linear (higher values) penalties. Lower Quadratic settings come down hard on large dissimilarities, whereas higher Linear settings hold up better against dissimilar matches. Dragging this slider lower tends to leave the disparity peppered with small random variations, while higher values give smoother, more pleasing results. Warp Count Lowering the Warp Count speeds up the disparity computations. Notably, computation time rises linearly with this option. To grasp what it does, recognize that the Disparity algorithm warps the left image step by step until it lines up with the right image. Past a certain point, convergence is reached and further warps merely burn computation time. Fusion's default is set high enough that convergence should always occur. You may trim this value to hasten the computations, but keep an eye on how the disparity's quality slips as you do. Iteration Count Lowering the Iteration Count speeds up the disparity computations. Again, computation time rises linearly with this option. As with the Warp Count, raising this option past a certain threshold delivers diminishing returns and won't meaningfully improve the outcome. Out of the box, this value is set to something expected to converge on any conceivable shot and can frequently be dialed down without harming the disparity's quality. Filtering This menu sets which filtering operations run while the flow is generated. Catmull-Rom filtering gives finer results, yet it drives the computation time up sharply. Stack Mode This menu sets how the input images are stacked. With Separate chosen, the Right Input and Output appear, and distinct left and right images have to be wired in. Swap Eyes Ticking this checkbox makes the left and right images trade places.

### Common Controls

Settings Tab The Inspector's Settings tab likewise shows up on the rest of the Stereo nodes. You'll find these shared controls covered fully toward the end of this chapter, in the “The Common Controls” section.

### Disparity To Z [D2Z]

### The DisparityToZ node

NOTE: You'll find the Disparity to Z node solely within Fusion Studio and DaVinci Resolve Studio.

### Disparity to Z Node Introduction

Disparity To Z accepts a 3D camera plus an image that carries a disparity channel as its inputs, and it returns that same image now bearing a freshly computed Z channel. As an option, the node can also write Z out into the RGB channels. Ideally you connect either a stereo Camera 3D or a tracked stereo camera into Disparity To Z. Yet when no camera is attached, the node hands you artistic controls for deciding a Z channel. The depth this node builds is handy for post effects such as fogging or depth of field (DoF). The Z values it returns grow less accurate the larger (in the negative direction) they become. That happens because disparity tends toward a fixed value as Z heads toward -infinity. Hence Z = -1000 and Z = -10000 and Z = -100000 might all map to D=142. 4563 and D=142. 4712 and D=142. 4713. Notice that a mere 0.0001 of D separates 10,000 from 100,000 in Z. The maps that disparity yields simply aren't precise enough to draw distinctions of that kind.

### Inputs

The Disparity To Z node's three inputs take the left and right images along with a camera node. Left Input: Wire either the left eye image or the stack image into the orange input. Right Input: Wire the right eye image into the green input. You can only use this input when the Stack Mode menu rests on Separate. Stereo Camera: Wire a stereo camera node into the magenta input.

### Outputs

In a break from how most Fusion nodes behave, Disparity To Z exposes two outputs, one for each eye. Left Output: This carries the left eye image bearing a new Z channel, or a Stacked Mode image bearing a new disparity channel. Right Output: This carries the right eye image bearing a new Z channel. The output appears solely when Stack Mode is set to Separate.

### Basic Node Setup

Disparity To Z takes in a 3D camera together with stereo images that hold a disparity channel. What it returns is an image carrying a freshly computed Z channel.

A Disparity to Z node creates an image with a Z channel.

### Inspector

### The Disparity To Z Controls tab

### Controls Tab

On top of writing Z values into the Z channel, this tab bumps the color channels up to float32 and emits the Z values into the color channels in the form {z, z, z, 1}. This option is handy for a fast peek at the Z channel. NOTE: Z values run negative, turning more negative as your distance from the camera grows. Since the viewers display only 0.0 to 1.0 color, any other data must be remapped through a normalization step to fall within a 0-1 display range. To pull that off, right-click within the viewer and pick Options > Show Full Color Range. Output Z to RGB Instead of confining the Z values to the linked aux channel alone, this copies them into the RGB channels so any of Fusion's nodes can work on them further. Refine Z The Enable checkbox sharpens the depth map using the RGB channels. That refinement nudges the flow's edges into tighter agreement with the color channels' edges. The trade-off is that unwanted detail from the color channels begins surfacing in the flow. It can be worth trying this option to ease off harsh edges for Z-channel post effects such as depth of field or fogging.

HiQ Only Switching this checkbox on confines the Refine Z option to running only while rendering sits at High Quality. To confirm High Quality is on, right-click just to either side of the transport controls in the main toolbar. Strength Raising this slider accomplishes two things at once. It evens out the depth across regions of constant color and shifts edges in the Z channel so they track edges in the RGB channels. The drawback of pushing the refinement is that texture from the color channel starts appearing in the Z channel. You'll want to strike a balance between the two. Radius This sets the radius used by the smoothing algorithm. Stack Mode This menu sets how the input images are stacked. With Separate selected, the Right Input and Output emerge, and you must wire in distinct left and right images. Swap Eyes Switching on this checkbox swaps the left and right images.

### The Disparity To Z Camera tab

### Camera Tab

When accurate real-world Z values matter because you're trying to line an effect up with a scene that already exists, turn to the External Camera options to recover precise Z values. Where any Z-buffer will do and you aren't fussy about the exact way it's offset and scaled, or where no camera is on hand, the Artistic option may come in handy.

- External Mode: The node exposes an input for hooking up an existing stereo Camera 3D. That can be either a lone stereo Camera 3D (i.e., one whose eye separation is non-zero), or a pair of (tracked) Camera 3Ds joined through the Camera 3D > Stereo > Right Camera input.
- Artistic Mode: Lacking a camera, you can work these controls to yield an “artistic” Z channel whose values won't be physically correct yet remain useful. To rebuild the Disparity > Z Curve, choose (D, Z) values for one point up front and one point in the back.

TIP: Should artistic mode feel a touch too “artistic” and you'd rather tune more physically-grounded parameters (e.g., convergence and eye separation), spin up a dummy Camera 3D, wire it into the Disparity To Z > Camera input, and then play with the Camera 3D's controls.
