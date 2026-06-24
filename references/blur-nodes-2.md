# Blur Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Much like the Glow node, Soft Glow carries three connections too: an orange one feeding the main image, a blue one for an effect mask, plus a white one dedicated to a Glow mask. Input: Feed the primary 2D image for the soft glow into the orange connection. Effect Mask: Into the blue connection goes a mask shape that polylines, simple primitive shapes, paint strokes, or bitmaps from other tools can produce. Attaching a mask here confines the soft glow to just the pixels inside the mask. Such an effect mask takes hold on the tool once processing has finished. Glow Mask: Pre-masking through the white glow mask input is supported by the Soft Glow node. A Glow pre-mask runs a filter over the image before the soft glow is laid down. After that, the soft glow gets composited back atop the original image. That behavior contrasts with an ordinary effect mask, which crops the finished render. With a Glow mask, the soft glow may spill past the mask edges, even though the soft glow's source stays confined to pixels inside the mask. In all other ways, Glow masks behave just like effect masks.

### Basic Node Setup

A 2D image such as the MediaIn1 pictured here feeds the Soft Glow node. From its output, the node tree carries on into a further 2D image-processing node or into a Merge node.

### Inspector

A Soft Glow node applied to a MediaIn1 node

### Soft Glow controls

### Controls Tab

Every primary control you need to tailor the soft glow operation lives on the Controls tab. Down at the foot of the Inspector, a color scale region lets you tint the soft glow. Filter Pick the Blur method for the filter from this menu. What follows describes the available choices.

- Box: A simple but very fast Box filter.
- Bartlett: Bartlett produces a gentler, more understated glow whose drop-off is smoother, though rendering can run

slower than Box.

- Multi-box: Multi-box stacks a Box filter across several passes to mimic a Gaussian shape.

A modest pass count (say, four) yields a high-quality blur that frequently beats the Gaussian filter on speed and avoids ringing entirely.

- Gaussian: Gaussian lays down a soft glow blurred via the Gaussian algorithm. It serves as the default method.

Color Channels (RGBA) By default the filter works across the R, G, B, and A channels. You can filter channels selectively by toggling the channel buttons on or off. NOTE: Do not confuse this with the RGBA checkboxes under the common controls. Because the node honors these picks ahead of processing the image, turning a channel off makes the node bypass it during processing, which speeds up how fast the effect renders. By contrast, the channel controls on the Common Controls tab take effect once the node finishes processing. Threshold Use this control to cap how much the soft glow does. A higher threshold means a pixel has to be brighter before the glow touches it. Gain The Gain control sets how bright the glow is. Lock X/Y With Lock X/Y enabled, the horizontal and vertical glow amounts are tied together. Otherwise you can dial in distinct glow amounts on each axis of the image. Glow Size This figure governs how large the glow effect grows. Bigger values widen the glowing highlights across the image. Num Passes Offered only when in Multi-box mode. Higher values yield a smoother spread of the effect while also pushing render times up. Finding the balance between the quality you want and render times you can live with is worthwhile. Clipping Mode This choice governs how edges get handled during domain-of-definition rendering. It matters enormously for nodes such as Blur, since those can demand samples from regions of the image beyond the current domain.

- Frame: Frame, the default choice, makes the node's domain of definition span the image's whole frame, so the current domain of definition is effectively disregarded. Should the upstream DoD be smaller than the frame, whatever frame area is left over reads as black/transparent.
- Domain: Choosing Domain here honors the upstream domain of definition as the node's effect is applied. In cases where the node uses a large filter, this can produce unwanted clipping.
- None: Picking None skips any clipping of the source image whatsoever. So any data the node's effect needs that would ordinarily sit beyond the upstream DoD reads as black/transparent.

Blend How much of the affected image gets blended with the original image is set by the Blend slider. The closer the value drops toward 0, the more of the original image is mixed back in. This control mirrors the Blend slider over on the Common Controls tab. Adjusting one updates the other in the common controls at the same time. Color Scale (RGBA) These Scale sliders let you tune, channel by channel, how much glow lands on each color channel, tinting the glow. Click and hold the Pick button, then drag the pointer across the viewer to sample a particular color out of the image.

### Common Controls

Settings Tab Other Blur nodes share the same Settings tab found in the Inspector. Full coverage of these common controls sits at this chapter's close, in the "The Common Controls" section.

### Unsharp Mask [USM]

### The Unsharp Mask node

### Unsharp Mask Introduction

Unsharp masking is a method for sharpening solely the edges inside an image. Most commonly this node fixes blurring and lost detail in low-contrast pictures; one example is pulling usable detail from long exposure frames of distant galaxies. The filter pulls a band of frequencies out of the image and blurs that band to cut detail. That blurred output then gets weighed against the original images. Where a pixel differs markedly between the original and the blurred version, it is probably edge detail. Then that pixel is brightened so it stands out.

### Inputs

The Unsharp Mask node's two inputs serve to hook up a 2D image plus an effect mask that confines the effect. Input: The orange input takes the primary 2D image for the Unsharp Mask. Effect Mask: A mask shape from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools goes into the blue input. Hooking a mask up here restricts the Unsharp Mask to just the pixels inside the mask. That effect mask kicks in on the tool after processing wraps up.

### Basic Node Setup

A 2D image like the MediaIn1 shown here feeds the Unsharp Mask node. Its output keeps the node tree going by linking to another 2D image-processing node or a Merge node.

### Inspector

An Unsharp mask node applied to a MediaIn1 node

### Unsharp Mask controls

### Controls Tab

All the primary controls you need to tailor the Unsharp Mask operation reside on the Controls tab. Color Channels (RGBA) Out of the box the filter operates over the R, G, B, and A channels. Selective channel filtering happens when you click the channel buttons to switch them active or inactive. NOTE: Do not mistake this for the RGBA checkboxes living under the common controls. Since the node weighs these picks before it processes the image, switching a channel off has the node skip it while processing, which makes the effect render faster. By contrast, the channel controls on the Common Controls tab apply once the node has finished processing.

Lock X/Y Once Lock X/Y is enabled, the horizontal and vertical sharpen amounts get locked together. Otherwise, distinct glow amounts can land on each axis of the image. Size This control sets how large the blur filter applied to the extracted image is. The larger this value goes, the greater the chance pixels register as detail. Gain The Gain control governs how much gain hits pixels the mask flags as detail. Bigger values yield a sharper image. Threshold Which frequencies get pulled from the source image is decided by this control. Pushing the value up drops lower-contrast regions out of having the effect applied.

### Common Controls

Settings Tab Other Blur nodes share the same Settings tab found in the Inspector. Full coverage of these common controls sits at this chapter's close, in the "The Common Controls" section.

### Vari Blur [VBL]

### The Vari Blur node

### Vari Blur Node Introduction

A genuine per-pixel variable blur comes from the Vari Blur node, which leans on a second image to drive how much blur each pixel gets. Its effect resembles the Depth Blur node somewhat, yet it takes a different route that often yields cleaner results.

### Inputs

For the primary image, the Vari Blur node has two inputs: the blur map image plus an effect mask. Input: The gold image input must be connected and carries the primary image you want to blur. Blur Image: The green input must be connected too, though as the blur map image it accepts any of these: a spline shape, text object, still image, or movie file. After connecting it, you pick the red, green, blue, Alpha, or luminance channel to define the blur's shape. Effect Mask: The optional blue effect mask input wants a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Hooking a mask here confines the Vari Blur to just the pixels inside the mask. That effect mask is applied to the tool once it has been processed.

### Basic Node Setup

A 2D image like the MediaIn1 below feeds the Vari Blur node. A gradient Background tool wires into the Blur image input to steer which regions the blur touches. From the output, the node tree carries on by linking to another 2D image-processing node or a Merge node.

### Inspector

A Vari Blur node sitting on a MediaIn1 node, with a gradient background steering which regions blur

### Vari Blur controls

### Controls Tab

Every primary control you need for tailoring the Vari Blur operation lives on the Controls tab. Method Pick the Blur method for the filter from this menu. The choices appear below.

- Soften: This method ranges from a plain Box shape through a Bartlett triangle up to a respectable Smooth blur as Quality climbs. It holds onto detail in less-blurred regions a touch better than Multi-box.
- Multi-box: Like Soften, it delivers a stronger Gaussian approximation at higher Quality settings.
- Defocus: Gives blurred pixels a flat, circular shape that can mimic the

look of a defocus. Quality Raising Quality yields smoother blurs at the cost of speed. With Quality set to 1, a very fast yet plain Box blur drives every Method setting. For low Blur Size values, a Quality of 2 generally does the job. A Quality of 4 usually suffices for most work unless Blur Size runs especially high.

Blur Channel This picks which channel of the Blur Image governs how much blurring lands on each pixel. Lock X/Y When chosen, only one Blur Size control shows, and any change to the blur amount lands on both axes alike. Clearing the checkbox brings up separate controls for X and Y Blur Size. Blur Size Pushing this control up raises the total blur applied to every pixel. Wherever the Blur image is black or absent, those pixels still blur, regardless of the Blur Size. Blur Limit This slider caps the usable range drawn from the Blur image. Certain Z-depth images carry values running to infinity, which throw off blur size. The Blur Limit serves to hold values inside range.

### Common Controls

Settings Tab Other Blur nodes share the same Settings tab found in the Inspector. Full coverage of these common controls sits at this chapter's close, in the "The Common Controls" section.

### Vector Motion Blur [VMB]

### The Vector Motion Blur node

### Vector Motion Blur Introduction

You use this node to build directional blurs driven by a Motion Vector map or by AOV (Arbitrary Output Variable) channels exported out of 3D-rendering software such as Arnold, Renderman, or VRay. Alternatively, the Optical Flow node in Fusion can generate motion vectors for you. Typically the vector map comprises two floating-point images: one channel states how far the pixel travels in X, the other how far it travels in Y. Those channels might sit inside OpenEXR or RLA/RPF images, or arrive as separate images through the node's Vectors input. To carry + and – values, the vector channels ought to use a float16 or float32 color depth. In the X channel, a value of 1 signals that pixel has shifted one pixel rightward, whereas a value of –10 marks ten pixels of movement leftward.

### Inputs

The Vector Motion Blur node carries three inputs covering a 2D image, a motion vector pass, plus an effect mask. Input: The required orange input handles a 2D image that takes on the motion blur. Vectors: The green input is required as well. Wire in here a motion vector AOV that a 3D application rendered, or else an EXR file the Optical Flow node in Fusion produced. Vector Mask: The optional white Vector Mask input masks the image ahead of processing. Effect Mask: A mask shape from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools feeds the shared blue input. Hooking a mask here keeps the motion blur's source confined to just the pixels inside the mask. That effect mask is applied to the tool after it gets processed.

### Basic Node Setup

A 2D image like the IMAGE shown below feeds the Vector Motion Blur node. A MediaIn or Loader node holding motion vectors wires into the Vector's input. From its output, the node tree carries on by linking to another 2D image-processing node or a Merge node.

### Inspector

A Vector Motion Blur node sitting on a MediaIn or Loader node, its motion vectors wired into the Vectors input

### Vector Motion Blur node

### Controls Tab

Every primary control you need for tailoring the Vector Motion Blur operation lives on the Controls tab.

X Channel From this menu, pick which channel of the image supplies the vectors driving pixel movement along the X-axis. Y Channel From this menu, pick which channel of the image supplies the vectors driving pixel movement along the Y-axis. Flip Channel Use these checkboxes to flip, or invert, the X and Y vectors. As an example, a value of 5 for a pixel in the X-vector channel turns into –5 once the X checkbox is on. Lock Scale X/Y Ticking this checkbox unlocks separate sliders for X and Y Scale. By default a single Scale slider appears. Scale Each pixel's X and Y vector channel values are multiplied by this slider's value. Say the scale is 2 and the vector value is 10; you would get 20. This slider divides into Scale X and Scale Y when the Lock Scale X/Y checkbox is off.

### Common Controls

Settings Tab Other Blur nodes share the same Settings tab found in the Inspector. Full coverage of these common controls sits in the following "The Common Controls" section.

### The Common Controls

A handful of identical controls in the Inspector are shared across nodes that perform blur operations. The controls common to Blur nodes are covered in this section.

### Inspector

### Common Blur settings

### Settings Tab

Every tool in the Blur category carries the Settings tab found in the Inspector. Even third-party Blur-type plugin tools include these Settings controls. They stay consistent and behave the same way for every tool. Blend The Blend control crossfades the original image fed into the tool against the modified output the tool finally produces. Where the blend value sits at 0.0, the outgoing image matches the incoming image exactly. Usually that makes the tool skip processing altogether, passing the input directly through to the output. Process When Blend Is 0.0 Even with the input value at zero, the tool still processes. This proves handy when processing of this node is scripted to set off another task, while the node's value reads 0.0. Red/Green/Blue/Alpha Channel Selector Use these four buttons to confine the tool's effect to chosen color channels. Typically this filter takes hold once the tool has finished processing. For instance, with the Red button on a Blur tool deselected, the blur applies to the image first; afterward the original input's red channel gets copied back across the result's red channel. Exceptions exist, such as tools where deselecting these channels makes the tool skip processing that channel altogether. Tools of that sort usually carry an identical set of RGBA buttons on the tool's Controls tab. In such a case, the buttons on the Settings and the Controls tabs match. Apply Mask Inverted Turning on the Apply Mask Inverted option flips the tool's entire mask channel. That mask channel combines every mask connected to or created within a node. Multiply by Mask Choosing this option has the masked image's RGB values multiplied by the mask channel's values. As a result, every image pixel outside the mask (that is, set to 0) turns black/transparent. Use Object/Use Material (Checkboxes) Certain 3D software can render to file formats carrying extra channels. The EXR file format notably supports object and material ID channels, usable as a mask for the effect. Whether those channels are used, when present, is governed by these checkboxes. Which specific material ID or object ID is affected gets picked through the next group of controls. Correct Edges This checkbox surfaces only once the Use Object or Use Material checkboxes are on. It switches the method used for handling overlapping object edges within a multi-object image. With it on, the Coverage and Background Color channels serve to separate and refine the effect along the object's edge. Where this option is off (or no Coverage or Background Color channels exist), the mask's edge may show aliasing. Wanting more on the Coverage and Background Color channels? See either Chapter 78, "Understanding Image Channels," within the DaVinci Resolve Reference Manual, or else Chapter 18 over in the Fusion Reference Manual.

Object ID/Material ID (Sliders) These sliders pick which ID builds a mask out of an image's object or material channels. Operate the Sample button just like the Color Picker to lift IDs from the image shown in the viewer. The image or sequence has to have been rendered by a 3D software package that included those channels. Use GPU Three settings live on the GPU menu. Disable shuts off GPU hardware accelerated rendering. Enabled puts the GPU hardware to work rendering the node. Auto taps a capable GPU when one exists and drops back to software rendering whenever a capable GPU is absent.

### Motion Blur

- Motion Blur: This switches the rendering of Motion Blur on the tool on or off. With this control switched on, the tool's predicted motion drives the motion blur produced by the virtual camera's shutter. With the control switched off, no motion blur gets created.
- Quality: Quality sets how many samples build the blur. Set Quality to 2 and Fusion creates two samples on either side of an object's actual motion. Bigger values give smoother results yet lengthen the render time.
- Shutter Angle: Shutter Angle governs the angle of the virtual shutter that produces the motion blur effect. Wider angles yield more blur but lengthen the render times. At a value of 360, the shutter stays open for one whole frame exposure. Going higher is possible and can yield interesting effects.
- Center Bias: Center Bias shifts where the center of the motion blur sits. That enables motion trail effects to be created.
- Sample Spread: Tweaking this control alters how each sample is weighted. That changes how bright the samples are.

Comments Use the Comments field to attach notes to a tool. Click inside the field and type the text. Once a note is attached to a tool, a small red square shows at the node's lower-left corner while the full tile is on display, or a small text bubble icon shows at the right while nodes are collapsed. To view the note inside the Node Editor, rest the mouse pointer over the node so the tooltip appears. Scripts From the Settings tab, every tool in Fusion offers three Scripting fields. Each holds edit boxes for adding scripts that run while the tool renders. For more on scripting nodes, refer to the Fusion scripting documentation.
