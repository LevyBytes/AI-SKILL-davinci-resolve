# Blur Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Blur Nodes

The pages here go through the Blur nodes that Fusion offers. The short abbreviation shown beside each node name works in the Select Tool dialog while you hunt for tools, and it also serves in scripting references. Throughout this document, node trees that show MediaIn nodes in DaVinci Resolve stand in equally for Loader nodes in Fusion Studio, except where a note says otherwise.

### Blur [Blur]

### The Blur node

### Blur Node Introduction

Just as its name promises, the Blur node softens the image fed into it. It ranks among the most frequently reached-for image-processing operations.

### Inputs

A Blur node carries two inputs, one for a 2D image and one for an effect mask that can restrict where the blur lands. Input: The orange input takes the main 2D image that gets blurred. Effect Mask: The blue input accepts a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming out of other tools. Wiring a mask here confines the blur to the pixels inside that mask. An effect mask gets applied once the tool itself has finished processing.

### Basic Node Setup

Like a great many 2D image-processing nodes, the Blur node accepts a 2D image such as the MediaIn1 pictured below. Its output carries the node tree onward by feeding another 2D image-processing node or a Merge node.

### Inspector

### A Blur node applied to a MediaIn1 node

### Blur controls

NOTE: Because an ideal Gaussian filter would need to look at an endless number of pixels, every workable Gaussian is, by necessity, an approximation. Fusion's algorithm takes a heavily-optimized route that brings real advantages, yet in a few extreme situations it can produce visible ringing along the edges. That ringing shows up only when you blur float-depth images and normally sits well under what the eye can detect, particularly in final renders or HiQ mode, though it may surface in later processing. Should you run into it, the Multi-box filter can be a sound pick.

### Controls Tab

Inside the Controls tab live the main controls you need for shaping the blur, among them five filter algorithms. Filter The Filter menu is the place where you pick which kind of filter builds the blur.

- Box Blur: This choice runs quicker than the Gaussian blur but yields a coarser outcome.
- Bartlett: This choice gives a gentler, anti-aliased blur filter.
- Multi-box: Multi-box runs a Box filter across several layered passes to mimic a Gaussian shape.

Use a fair number of passes (four, say) and you get a high-quality blur, frequently quicker than the Gaussian filter and free of any ringing.

- Gaussian: Gaussian lays down a smooth, symmetrical blur filter built on a refined constant-time Gaussian approximation algorithm.
- Fast Gaussian: Gaussian lays down a smooth, symmetrical blur filter built on a refined constanttime Gaussian approximation algorithm. This mode is the filter method used by default.

Color Channels (RGBA) Out of the box the filter works on the R, G, B, and A channels. You can filter channels selectively by clicking each channel button to turn it on or off. NOTE: This isn't the same thing as the RGBA checkboxes sitting under the common controls. These picks are honored before the node processes the image, so turning off a channel makes the node bypass it during processing, which speeds the effect's render. The channel controls on the Common Controls tab, by contrast, kick in after the node has processed. Lock X/Y Ties the X and Y Blur sliders together so the blur stays symmetrical. It's on by default. Blur Size Sets how much blur lands on the image. Deselect the Lock X and Y control and you get separate command over each axis.

Clipping Mode This setting governs how edges get treated during domain-of-definition rendering. It carries real weight for nodes such as Blur, which may need to sample parts of the image lying beyond the current domain.

- Frame: Frame is the default, and it automatically forces the node's domain of definition to span the image's whole frame, in effect disregarding the present domain of definition. Where the upstream DoD falls short of the frame, the leftover frame area is taken as black/ transparent.
- Domain: Choosing Domain honors the upstream domain of definition as the node's effect is applied. This can lead to unwanted clipping wherever the node reaches for a large filter.
- None: Choosing None skips source image clipping altogether. So whatever data the node's effect needs that would normally fall outside the upstream DoD is taken as black/transparent.

Blend The Blend slider sets what share of the affected image is blended with original image. The nearer the value gets to 0, the more of the original image it folds back in. This control is a cloned copy of the Blend slider over on the Common Controls tab; adjusting one adjusts the other in lockstep.

### Examples

Below is a side-by-side of the Blur filters drawn as “cross-sections” through a filtered edge. Notice that Box yields a straight ramp, whereas Bartlett yields a somewhat gentler ramp. Multi-box and Gaussian look identical unless you magnify the slopes way in. Both deliver still gentler ramps, yet, as noted above, Gaussian overshoots a touch and can push values negative when used on floating-point images.

The Blur filters rendered as edge “cross sections” showing how each filters a single edge Common Controls Settings Tab The Settings tab inside the Inspector likewise repeats on the other Blur nodes. A full account of these shared controls waits at the chapter's end, under the “The Common Controls” section.

### Defocus [Dfo]

### The Defocus node

### Defocus Node Introduction

The Defocus node imitates what happens with an out-of-focus camera lens, blooming and image flaring among the effects. It supplies a quick Gaussian mode plus a more lifelike though slower Lens mode.

### Inputs

A Defocus node has two inputs, for wiring up a 2D image and an effect mask that can hold the simulated defocus to a chosen region. Input: The orange input takes the main 2D image for defocusing. Effect Mask: The blue input accepts a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming out of other tools. Wiring a mask here confines the defocus to the pixels inside that mask. An effect mask gets applied once the tool has processed.

### Basic Node Setup

A Defocus node accepts a 2D image such as the MediaIn1 pictured below. Its output carries the node tree onward by feeding another 2D image-processing node or a Merge node.

### Inspector

### A Defocus node applied to a MediaIn1 node

### Defocus controls

### Controls Tab

Inside the Controls tab live all the main controls for shaping the defocus. Filter Reach for this menu to pick the precise method used to build the defocus. Gaussian delivers a basic effect, while Lens mode produces a more lifelike defocus. Lens mode runs considerably longer than Gaussian. Lock X/Y With Lock X/Y picked, the same amount of defocus is applied to both the X- and Y-axis of the image. Deselect it for separate command. Defocus Size The Defocus Size control sets how big the defocus effect grows. Bigger values blur the image more heavily and yield larger blooms. Bloom Level The Bloom Level control governs how intense and how large the blooming is on pixels sitting above the bloom threshold. Bloom Threshold Pixels whose values sit above the chosen Bloom Threshold get defocused and pick up a glow (blooming). Pixels under that value are only defocused. The four lens options that follow show up solely when the Filter is set to Lens.

- Lens Type: The base shape used to build the “bad bokeh” effect. The Angle, Sides, and Shape sliders let you refine it further.
- Lens Angle: Sets the rotation of the shape. Most visible on NGon lens types. Owing to a circle's round nature, this slider has no effect you can see when the Lens Type is set to Circle.
- Lens Sides: Sets the number of sides an NGon shape carries. Most visible on NGon lens types. Owing to a circle's round nature, this slider has no effect you can see when the Lens Type is set to Circle.
- Lens Shape: Sets how pointed the NGons turn out. Higher values yield a more pointed, starry look. Lower values yield smoother NGons. Most visible on NGon lens types with Lens Sides between 5 and 10. Owing to a circle's round nature, this slider has no effect you can see when the Lens Type is set to Circle.

Clipping Mode This setting governs how edges get treated during domain-of-definition rendering. It carries real weight for nodes such as Blur, which may need to sample parts of the image lying beyond the current domain.

- Frame: Frame is the default, and it automatically forces the node's domain of definition to span the image's whole frame, in effect disregarding the present domain of definition. Where the upstream DoD falls short of the frame, the leftover frame area is taken as black/ transparent.
- Domain: Choosing Domain honors the upstream domain of definition as the node's effect is applied. This can lead to unwanted clipping wherever the node reaches for a large filter.
- None: Choosing None skips source image clipping altogether. So whatever data the node's effect needs that would normally fall outside the upstream DoD is taken as black/transparent.

### Common Controls

Settings Tab The Settings tab in the Inspector also recurs across the other Blur nodes. These shared controls get a full treatment at this chapter's close, under the “The Common Controls” section.

### Directional Blur [DrBl]

### The Directional Blur node

### Directional Blur Node Introduction

You use this node to produce Directional and Radial blurs. It comes in handy for faking motion blur and light ray-type effects. Directional Blur acts on every channel (RGBA).

### Inputs

A Directional Blur node carries two inputs, one for a 2D image and one for an effect mask which can hold the blur to a chosen region. Input: The orange input takes the main 2D image that the directional blur is applied to. Effect Mask: The blue input accepts a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming out of other tools. Wiring a mask here confines the directional blur to the pixels inside that mask. An effect mask gets applied once the tool has processed.

### Basic Node Setup

A Directional Blur node accepts a 2D image such as the MediaIn1 pictured below. Its output carries the node tree onward by feeding another 2D image-processing node or a Merge node.

A Directional Blur node applied to a MediaIn1 node

### Inspector

### Directional Blur controls

### Controls Tab

Inside the Controls tab live all the main controls for shaping the directional blur. Type Reach for this menu to pick which type of directional blur lands on the image.

- Linear: Linear smears the image along a straight line, much like the view through the window of a train at full speed.
- Radial: Radial spreads a distortion outward from some chosen center, the way the scene would look to someone riding up front and gazing ahead.
- Centered: The Centered button gives a result close to linear, except the blur spreads evenly to either side of the original.
- Zoom: Zoom warps the scale of the image smear to mimic the zoom streak of a camera shooting at a slow shutter speed.

Center X and Y This coordinate control, along with its viewer crosshair, touches only the Radial and Zoom Motion Blur types. You use it to set where the blurring effect begins. Length Length tunes the strength and heading of the effect. Values under zero send blurs in the direction opposite the angle control. Values past the slider's top can be entered by hand right in its edit box. Angle Whenever you're in Linear or Center mode, this control steers the heading of the directional blur. In the Radial and Zoom modes, the result is like the camera spinning while it stares at one spot. When the length slider sits at anything other than zero, the result builds a whirlpool effect. Glow This lays a Glow over the directional blur, useful for reproducing the extra light exposure a camera picks up with longer shutter speeds.

Clipping Mode This setting governs how edges get treated during domain-of-definition rendering. It carries real weight for nodes such as Blur, which may need to sample parts of the image lying beyond the current domain.

- Frame: Frame is the default, and it automatically forces the node's domain of definition to span the image's whole frame, in effect disregarding the present domain of definition. Where the upstream DoD falls short of the frame, the leftover frame area is taken as black/transparent.
- Domain: Choosing Domain honors the upstream domain of definition as the node's effect is applied. This can lead to unwanted clipping wherever the node reaches for a large filter.
- None: Choosing None skips source image clipping altogether. So whatever data the node's effect needs that would normally fall outside the upstream DoD is taken as black/transparent.

### Common Controls

Settings Tab The Settings tab in the Inspector also recurs across the other Blur nodes. These shared controls get a full treatment at this chapter's close, under the “The Common Controls” section.

### Glow [Glo]

### The Glow nozzde

### Glow Node Introduction

A Glow comes about by blurring an image, then brightening that blurred result and mixing it back over the original. The Glow node serves up a range of takes on this idea. A Bartlett glow, for instance, is a high-quality glow with a gentler falloff, though it asks more of the processor at bigger sizes.

### Inputs

Three inputs sit on the Glow node: an orange one feeding the main 2D image, then a blue one taking an effect mask, plus a third — colored white — for a Glow mask. Input: The orange input takes the main 2D image that the glow is applied to. Effect Mask: The blue input accepts a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming out of other tools. Wiring a mask here holds the glow's source to the pixels inside that mask. An effect mask gets applied once the tool has processed. Glow Mask: The Glow node allows pre-masking by way of the white glow mask input. A Glow pre-mask filters the image ahead of the glow being applied. The glow is then merged back over the original image. That differs from an ordinary effect mask, which clips the rendered output. The Glow mask permits the glow to spill past the mask's edges while still holding the glow's source to the pixels inside the mask.

Apart from that, Glow masks behave just like Effect masks in every way.

### Basic Node Setup

A Glow node accepts a 2D image such as the MediaIn1 pictured below. Its output carries the node tree onward by feeding another 2D image-processing node or a Merge node.

### Inspector

A Glow node applied to a MediaIn1 node in DaVinci Resolve

### Glow controls

### Controls Tab

Inside the Controls tab live all the main controls for shaping the glow. A Color Scale section down at the bottom of the Inspector lets you tint the glow. Filter Reach for this menu to pick the Blur method the filter uses. The choices are spelled out below.

- Box: A plain yet very fast Box filter.
- Bartlett: Bartlett brings a softer, more delicate glow with a gentler falloff but can take longer to

render than Box.

- Multi-box: Multi-box runs a Box filter across several layered passes to mimic a Gaussian shape.

Use a fair number of passes (four, say) and you get a high-quality blur, frequently quicker than the Gaussian filter, and free of any ringing.

- Gaussian: Gaussian brings a soft glow, blurred via the Gaussian algorithm.
- Fast Gaussian: Fast Gaussian brings a soft glow, blurred via the Gaussian algorithm. This is the default method.
- Blend: Blend brings a nonlinear glow that reads evenly in the whites and blacks.
- Hilight: Hilight brings a glow yet raises no halo around the surrounding pixels.
- Solarize: Solarize brings a glow and solarizes the image.

Color Channels (RGBA) Out of the box this filter works on the R, G, B, and A channels. You can filter channels selectively by clicking each channel to turn it on or off. NOTE: This isn't the same thing as the RGBA checkboxes sitting under the common controls. These picks are honored before the node processes the image, so turning off a channel makes the node bypass it during processing, which speeds the effect's render. The channel controls on the Common Controls tab, by contrast, take effect only once the node finishes its work. Lock X/Y Checking Lock X/Y keeps the horizontal and vertical glow amounts bound to one another. Otherwise you can apply different glow amounts to each axis. Glow Size Glow Size sets how big the glow effect grows. Bigger values widen the glowing highlights across the image. Num Passes Available only in Multi-box mode. Bigger values smooth out the effect's spread but also push render times up. It pays to find the sweet spot between the quality you want and render times you can live with. Glow The Glow slider sets how intense the glow effect is. Bigger values tend to blow the image right out to white. Clipping Mode This setting governs how edges get treated during domain-of-definition rendering. It carries real weight for nodes such as Blur, which may need to sample parts of the image lying beyond the current domain.

- Frame: Frame is the default, and it automatically forces the node's domain of definition to span the image's whole frame, in effect disregarding the present domain of definition. Where the upstream DoD falls short of the frame, the leftover frame area is taken as black/transparent.
- Domain: Choosing Domain honors the upstream domain of definition as the node's effect is applied. This can lead to unwanted clipping wherever the node reaches for a large filter.
- None: Choosing None skips source image clipping altogether. So whatever data the node's effect needs that would normally fall outside the upstream DoD is taken as black/transparent.

Blend The Blend slider sets what share of the affected image is blended with original image. The nearer the value gets to 0, the more of the original image it folds back in. This control is a cloned copy of the Blend slider over on the Common Controls tab; adjusting one adjusts the other in lockstep. Apply Mode Three Apply Modes are on hand for how the glow gets applied to the image.

- Normal: Default. This mode simply lays the glow straight over top of the original image.
- Merge Under: Merge Under tucks the glow beneath the image, going by the Alpha channel.

Threshold mode allows clipping of the threshold values.

- Threshold: This control clips how far the glow's effect reaches. A fresh range slider shows up. Pixels in the

glowed regions whose values fall under the low value are driven to black. Pixels whose values top high are driven to white. High-Low Range Control: On hand only in Threshold mode. Pixels in the glowed regions whose values fall under the low value are driven to black. Pixels whose values top high are driven to white. Color Scale (RGBA) These Scale sliders let you set how much glow lands on each color channel one at a time, tinting the glow. Click and hold the Pick button, then drag the pointer across the viewer, to lift a specific color out of the image.

### Common Controls

Settings Tab The Settings tab in the Inspector also recurs across the other Blur nodes. These shared controls get a full treatment at this chapter's close, under the “The Common Controls” section.

### Sharpen [Shrp]

### The Sharpen node

### Sharpen Node Introduction

The Sharpen node runs a convolution filter to bring out detail across an image as a whole or within a single channel.

### Inputs

A Sharpen node carries two inputs, one for a 2D image and one for an effect mask that can hold down the region the sharpen touches.

Input: The orange input takes the main 2D image for sharpening. Effect Mask: The blue input accepts a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming out of other tools. Wiring a mask here confines the sharpen to the pixels inside that mask. An effect mask gets applied once the tool has processed.

### Basic Node Setup

A Sharpen node accepts a 2D image such as the MediaIn1 pictured below. Its output carries the node tree onward by feeding another 2D image-processing node or a Merge node.

### Inspector

A Sharpen node applied to a MediaIn1 node in DaVinci Resolve

### Sharpen controls

### Controls Tab

Inside the Controls tab live all the main controls for shaping the sharpen. Color Channels (RGBA) Out of the box this filter works on the R, G, B, and A channels. You can filter channels selectively by clicking the channel buttons to turn them on or off. NOTE: This isn't the same thing as the RGBA checkboxes sitting under the common controls. These picks are honored before the node processes the image, so turning off a channel makes the node bypass it during processing, which speeds the effect's render. The channel controls on the Common Controls tab, by contrast, kick in after the node has processed. Lock X/Y This ties the X and Y Sharpen sliders together so the sharpening stays symmetrical. It's checked by default.

Amount This slider sets how much sharpening lands on the image. Deselect the Lock X/Y control and you get separate command over each axis. Clipping Mode This setting governs how edges get treated during domain-of-definition rendering. It carries real weight for nodes such as Blur, which may need to sample parts of the image lying beyond the current domain.

- Frame: Frame is the default, and it automatically forces the node's domain of definition to span the image's whole frame, in effect disregarding the present domain of definition. Where the upstream DoD falls short of the frame, the leftover frame area is taken as black/ transparent.
- Domain: Choosing Domain honors the upstream domain of definition as the node's effect is applied. This can lead to unwanted clipping wherever the node reaches for a large filter.
- None: Choosing None skips source image clipping altogether. So whatever data the node's effect needs that would normally fall outside the upstream DoD is taken as black/transparent.

Blend The Blend slider sets what share of the affected image is blended with original image. The nearer the value gets to 0, the more of the original image it folds back in. This control is a cloned copy of the Blend slider over on the Common Controls tab; adjusting one adjusts the other in lockstep.

### Common Controls

Settings Tab The Settings tab in the Inspector also recurs across the other Blur nodes. These shared controls get a full treatment at this chapter's close, under the “The Common Controls” section.

### Soft Glow [SGlo]

### The Soft Glow node

### Soft Glow Node Introduction

The Soft Glow node resembles the Glow node but puts the image through extra processing to land a far softer, more natural glow. It's a great fit for atmospheric haze around planets, skin tones, and conjuring dreamlike settings.

### Inputs
