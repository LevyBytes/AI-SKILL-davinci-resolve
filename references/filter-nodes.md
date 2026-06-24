# Filter Nodes

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Filter Nodes

This chapter walks through the Filter nodes that Fusion offers. The shorthand shown beside each node name is what you type into the Select Tool dialog while hunting for tools, and it also shows up in scripting references. Throughout this document, node trees that display MediaIn nodes in DaVinci Resolve stand in equally for Loader nodes in Fusion Studio, except where a note says otherwise.

### Create Bump Map [CBu]

### The Create Bump Map node

### Create Bump Map Node Introduction

The Create Bump Map node takes a grayscale (height map) image and turns it into a bump map. Whereas the Bump Map node converts an image into a 3D material, the Create Bump Map node instead generates bump vector data and hands back the result as an RGB image, leaving it open to further image-processing operations.

### Input

Two inputs sit on the Create Bump Map node: one carries the main image, while the other takes an effect mask that confines where the bump map gets built. Input: The orange input pulls the RGBA channels out of an image so the bump map can be calculated. Effect Mask: The optional blue effect mask input takes a mask shape drawn from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input restricts bump-map creation to just the pixels falling inside the mask. The effects mask gets applied to the tool only after the tool has finished processing.

### Basic Node Setup

A 2D grayscale image such as a fast noise feeds the Create Bump Map node, after which it can run through assorted 2D image-processing filters that build the bump map texture.

A Create Bump Map node outputs its bump map in RGB form, ready for downstream image processing

### Inspector

### Create Bump Map controls

### Controls Tab

Every parameter for building the bump map lives in the Controls tab. Filter Size This menu fixes the filter size used when generating the bump map. The filter size can be put at 3 x 3 pixels or 5 x 5 pixels, which sets how wide a radius of pixels gets sampled. A bigger size means a longer render. Height Source The Height Source menu picks the channel from which the grayscale information is drawn. Clamp Normal.Z This slider trims the lower readings of the blue channel inside the resulting bump texture. Wrap Mode This menu governs how the image wraps along its borders, letting the filter give a proper result with seamless tiling textures. Height Scale The height scale menu changes the contrast of the values produced in the bump map. Pushing this value up makes the bump map more pronounced. Bump Map Texture Depth Through this menu the finished bump texture is matched to, or recast into, whichever bit depth you prefer. NOTE: The definitions below are offered to make some of the terms used in the Create Bump Map node and other comparable node types clearer. Height Map: A grayscale image that holds one height value per pixel. Bump Map: An image whose RGB channels store normals used to alter the existing normals (typically expressed in tangent space). Normal Map: An image whose RGB channels store normals used to replace the existing normals (typically expressed in tangent or object space).

### Common Controls

Settings Tab Because the Settings tab controls are shared by every Filter node, you'll find their write-ups in the "The Common Controls" section closing out this chapter.

### Custom Filter Node [CFlt]

### The Custom Filter node

### Custom Filter Node Introduction

You use the Custom Filter node to run custom convolution filters over images. A custom convolution filter can deliver an enormous range of image effects. Emboss, relief, sharpen, blurring, and edge detection, for instance, are all convolution filters. A number of ready-made custom filters ship in the Filters directory and can be brought in by right-clicking the control header and choosing Settings > Load from the contextual menu. The Custom filter leans on an array (or grid) carrying values in a 3 x 3, 5 x 5, or 7 x 7 layout. (Note: Inside the Inspector the array is forever drawn as a 7 x 7 grid, yet dialing the Matrix Size down to 3 x 3 engages just the middle 9 cells.) The middle of the array stands for the current pixel, while the surrounding entries stand for neighboring pixels. A value of 1 feeds the pixel's full value into the filter. A value of 0 disregards the pixel's value. A value above 1 amplifies that pixel's contribution to the outcome. You can also key in negative values, where the pixel's value gets subtracted from the average. Only whole numbers are allowed; 0.x won't work.

### Input

Two inputs sit on the Custom Filter node: one carries the main image, while the other takes an effect mask that confines where the custom filter is applied. Input: The orange input pulls the RGBA channels out of an image so the custom filter can be calculated. Effect Mask: The optional blue effect mask input takes a mask shape drawn from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input restricts the custom filter to just the pixels falling inside the mask. The effects mask gets applied to the tool only after the tool has finished processing.

### Basic Node Setup

You can drop the Custom Filter node in after an image, a mask, or any node that calls for a custom convolution filter.

A Custom Filter node placed after a MediaIn node in DaVinci Resolve

### Inspector

### Custom Filter controls

### Controls Tab

The Controls tab is where you fix the filter size and then enter convolution filter values into the filter matrix. Color Channels (RGBA) By default the custom filter works across the R, G, B, and A channels. You can edit channels selectively by ticking or clearing the checkboxes next to each one. These are not the same as the RGBA checkboxes sitting under the Common Controls. The node weighs these controls before it does any processing. Clearing a channel makes the node bypass that channel during processing, which speeds up rendering the effect. By contrast, the matching controls on the Common Controls tab take effect after the node has processed. Matrix Size This menu offers a filter size of 3 x 3 pixels; alternatively 5 x 5 pixels, or else 7 x 7 pixels, thereby fixing how wide a radius of pixels gets sampled. A bigger size means a longer render. Update Lock With this control on, Fusion holds off rendering the filter. That's handy while you dial in each value of the filter, after which you switch Update Lock off and render. Filter Matrix Laid out as a 7 x 7 grid of text boxes, the Filter Matrix control takes a number in each cell that represents how strongly the matching pixel sways the overall convolution filter. The text box dead center stands for the pixel the filter processes. The text box just to the left of center stands for the pixel immediately to its left, and so on. The Matrix size defaults to 3 x 3. Only the pixels directly bordering the current pixel get analyzed. Choosing a larger Matrix size switches on more of the grid's text boxes for entry.

Normalize This dictates how much filter normalization reaches the outcome. Zero gives back a normalized image. With positive values the filter result gets brighter, its level pushed upward. With negative values it goes darker, its level pulled down. Floor Level This tacks on or strips away a minimum, the so-called Floor Level, against the result of the filtered image. Zero adds nothing to the image. Positive values add to the filtered image, while negative values subtract from it.

### Examples

Original Image Example Take, for example, a filter holding the values... 000 010 000 ...which draws nothing from its neighboring pixels, leaving the resulting image untouched.

### Original image

Softening Example A faint softening effect would look like... 111 111 111 ...where the surrounding pixels get averaged together with the center.

Before and after averaging neighboring pixels to soften the image

### Emboss Example

In the example that follows, five times the value is subtracted from the top left and five times the value is added at the lower right. -5 0 0 010 005 Wherever stretches of the processed image are very smooth in color, the neighboring values stay very close. Wherever the pixels differ across the image (an edge, say), the outputs differ too and tend to accentuate or emboss edges in the image.

A Custom Filter that adds and subtracts surrounding pixels, yielding an embossed look Exposure Example Taking the values... 111 111 111 ...and pushing Normalize toward a positive value brightens the image or makes it glow, mimicking film overexposure.

The Custom Filter Normalize slider used to change exposure Relief Example Taking the values... -1 0 0 000 001

... and pushing Floor Level toward a positive value yields a Relief filter.

Custom Filter Floor Level slider driving a relief result Common Controls Settings Tab Because the Settings tab controls are shared by every Filter node, you'll find their write-ups in the "The Common Controls" section closing out this chapter.

### Erode Dilate Node [ErDl]

### The Erode Dilate node

### Erode Dilate Node Introduction

The Erode Dilate node shrinks or grows the image, the direction depending on whether the Amount slider holds a negative or a positive value.

### Inputs

Two inputs sit on the Erode Dilate node: one carries the main image, while the other takes an effect mask that confines where the erode or dilate is applied. Input: The orange input pulls the RGBA channels out of an image so the custom filter can be calculated. Effect Mask: The optional blue effect mask input takes a mask shape drawn from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input restricts the erode or dilate to just the pixels falling inside the mask. The effects mask gets applied to the tool only after the tool has finished processing.

### Basic Node Setup

People routinely reach for the Erode Dilate node to shrink or grow mattes. In the example below, a Luma Keyer feeds the Erode Dilate, which then hands the altered key off to a Matte Control that embeds it into the image.

### Inspector

An Erode Dilate node sitting downstream of a Luma Keyer, acting on a Matte Control

### Erode Dilate controls

### Controls Tab

The Controls tab holds the main Amount slider, which decides whether you're running an erode (by keying in a negative value) or a dilate (by keying in a positive value). Color Channels (RGBA) By default the Erode Dilate node works across the R, G, B, and A channels. You can edit channels selectively by ticking or clearing the checkboxes next to each one. These are not the same as the RGBA checkboxes sitting under the Common Controls. The node weighs these controls before it does any processing. Clearing a channel makes the node bypass that channel during processing, which speeds up rendering the effect. By contrast, the channel controls on the Common Controls tab take effect after the node has processed.

Lock X/Y The Lock X/Y checkbox splits the Amount slider into amount X and amount Y, letting each axis carry its own value for the effect. Amount A negative Amount value drives the image to erode. Eroding imitates an underexposed frame, contracting the image as the darker regions spread and gnaw into the brighter ones. A positive Amount value drives the image to dilate, much like overexposing a camera. Areas of high luminance and brightness expand, gnawing into the darker regions of the image. Either approach wipes out fine detail in the image and tends to posterize subtle gradients. How the Amount slider scales is tied to the width of the input image, since an amount value of 1 = image width. To erode or dilate an HD image by precisely 1 pixel, then, you'd key in 1/1920, or 0.00052083.

### Common Controls

Settings Tab Because the Settings tab controls are shared by every Filter node, you'll find their write-ups in the "The Common Controls" section closing out this chapter.

### Filter Node [Fltr]

### The Filter node

### Filter Node Introduction

The Filter node packs several standard convolution filters that you pick straight from a list. With this node you can do anything from radically reshaping an image's look to layering in subtle randomly-generated film grain. The Sobel and Laplacian settings see frequent use for edge detection.

### Inputs

Two inputs sit on the Filter node: one carries the main image, while the other takes an effect mask that confines where the filter is applied. Input: The orange input handles the main 2D image that the filter acts on. Effect Mask: The optional blue effect mask input takes a mask shape drawn from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input restricts the filter to just the pixels falling inside the mask. The effects mask gets applied to the tool only after the tool has finished processing.

### Basic Node Setup

You can drop the Filter node in after an image, a mask, or any node needing a filter applied. In the example below, it builds an edge matte, which then masks the soft glow ringing the keyed foreground.

A Filter node set to Sobel, pulling an edge matte out of the image Inspector

### Filter controls

### Controls Tab

The Controls tab is where you choose the filter type, the channels it acts on, and how much it blends back with the original image.

Filter Type The Filter Type menu offers a lineup of filter types covered below.

- Relief: This makes the image look pressed into metal, like the design on a coin. The image seems bumped and laid over gray.
- Emboss Over: Embosses the image atop itself, with highlight and shadow height and direction you can adjust.
- Noise: Adds noise evenly across images. It's frequently handy for 3D computer-generated images that have to be composited with live action, since it cuts down the squeaky-clean look baked into rendered images. The frame number serves as the random generator seed. As a result, the effect changes on every frame yet stays repeatable.
- Defocus: This filter type blurs the image.
- Sobel: Sobel is an advanced edge detection filter. Paired with a Glow filter, it produces

impressive neon light effects from live-action or 3D-rendered images.

- Laplacian: Laplacian is a highly sensitive edge detection filter, giving a finer edge than the

Sobel filter.

- Grain: Layers noise onto images resembling film grain (chiefly in the midrange). It's handy for

3D computer-generated images that have to be composited with live action, since it cuts down the squeaky-clean look baked into rendered images. The frame number serves as the random generator seed. As a result, the effect changes on every frame yet stays repeatable. Color Channels (RGBA) By default the Filter node works across the R, G, B, and A channels. You can edit channels selectively by ticking or clearing the checkboxes next to each one. Power Values span 1 to 10. Power scales up, in proportion, how strongly the chosen filter hits the image. This has no bearing on the Sobel or Laplacian filter type. Angle This control runs from 0 to 315 degrees and shifts the effect in steps of 45 degrees. It applies only to the Relief and Emboss filters. Median Depending on the Filter Type chosen, the Median control may surface. It modulates the Median filter's strength. A value of 0.5 gives the true median result, since it locates the middle values. A value of 0.0 locates the minimums, and 1.0 locates the maximums. This applies to the Median setting only. Seed This control shows up only with the Grain or Noise filter types. The Seed slider lets you keep the effect's random elements seeded with a steady value. Given the same seed value, the randomizer always returns the same result. Animated This control shows up only with the Grain or Noise filter types. Tick the checkbox to make the noise or grain shift from one frame to the next. For static noise, clear this checkbox.

### Common Controls

Settings Tab Because the Settings tab controls are shared by every Filter node, you'll find their write-ups in the "The Common Controls" section closing out this chapter.

### Rank Filter Node [RFlt]

### The Rank Filter node

### Rank Filter Node Introduction

The Rank Filter inspects surrounding pixels, orders those pixels by value, and then swaps the color of the inspected pixels for the color of whichever pixel holds the chosen rank.

### Inputs

Two inputs sit on the Rank Filter node: one carries the main image, while the other takes an effect mask that confines where the filter is applied. Input: The orange input handles the main 2D image that the Rank filter acts on. Effect Mask: The optional blue effect mask input takes a mask shape drawn from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input restricts the rank filter to just the pixels falling inside the mask. The effects mask gets applied to the tool only after the tool has finished processing.

### Basic Node Setup

You can park the Rank Filter node anywhere in a node tree to apply an effect to an image.

A Rank Filter node placed after a MediaIn node in DaVinci Resolve

Inspector

l Rank Filter controls Controls Tab The Controls tab is where you set the filter's size and rank value. Size This control fixes the pixel size of the area the filter samples. A value of 1 samples 1 pixel in every direction next to the center pixel. That comes to 9 pixels total, the center sampled pixel included. Bigger values draw from a wider area. Low Size settings work wonders for clearing salt and pepper style noise, whereas higher Size settings yield something akin to watercolor paintings. Rank The Rank slider decides which of the sampled pixel values wins out. Here 0 points to the lowest value (the darkest pixel), while 1 points to the highest value (the brightest pixel).

### Example

What follows is a before and after pairing for a Rank filter, its Size put at 7 and its Rank at 0.7, building a watercolor effect.

Before and after of a Rank Filter producing a watercolor-style effect

### The Common Controls

A handful of identical controls in the Inspector are shared across the Filter nodes. This section runs through the controls that the Filter nodes have in common.

### Inspector

### Common Filter settings Inspector

### Settings Tab

You'll find the Settings tab of the Inspector on every tool in the Filter category. These Settings controls even turn up on third-party filter-type plugin tools. The controls stay consistent and behave the same way on each tool, though a few tools tack on one or two extra options, which are covered here as well. Blend The Blend control fades between the image the tool received at its input and the finished, altered image it sends to its output. With the blend value at 0.0, the outgoing image is the same as the incoming one. Typically this makes the tool skip processing altogether, copying the input straight through to the output. Process When Blend Is 0.0 The tool still processes even when the input value is zero. That can help when this node's processing is scripted to kick off another task while the node's value sits at 0.0.

Red/Green/Blue/Alpha Channel Selector These four buttons confine the tool's effect to chosen color channels. This filter often kicks in after the tool has been processed. For instance, if you clear the red button on a Blur tool, the blur runs across the image first, and then the red channel from the original input gets copied back over the red channel of the result. A few exceptions exist, such as tools where clearing these channels makes the tool skip processing that channel entirely. Tools that behave this way usually carry a matching set of RGBA buttons on the Controls tab in the tool. In that case, the buttons on the Settings and the Controls tabs are one and the same. Apply Mask Inverted Turning on the Apply Mask Inverted option flips the whole mask channel for the tool. The mask channel is the merged outcome of every mask wired into or produced within a node. Multiply by Mask Choosing this option multiplies the RGB values of the masked image by the mask channel's values. That turns every pixel of the image left out of the mask (that is, set to 0) black/transparent. Use Object/Use Material (Checkboxes) Certain 3D software can render to file formats carrying extra channels. The EXR file format notably supports Object ID and Material ID channels, which can serve as a mask for the effect. These checkboxes decide whether those channels get used, when present. Which specific Material ID or Object ID is affected gets chosen with the next set of controls. Correct Edges This checkbox surfaces only while the Use Object or Use Material checkboxes are on. It flips the method used for handling overlapping object edges in a multi-object image. When on, the Coverage and Background Color channels are tapped to separate and sharpen the effect around the object's edge. With this option off (or where no Coverage or Background Color channels exist), aliasing can crop up on the mask's edge. To dig deeper into the Coverage and Background Color channels, turn to Chapter 78, "Understanding Image Channels," within the DaVinci Resolve Reference Manual, or to Chapter 18 over in the Fusion Reference Manual. Object ID/Material ID (Sliders) With these sliders you choose which ID gets turned into a mask, drawn from an image's object or material channels. The Sample button works much like the Color Picker does, letting you grab IDs straight off the image shown in the view. The image or sequence has to have been rendered out of a 3D software package with those channels baked in. Use GPU The Use GPU menu carries three settings. Putting the menu on Disable shuts off hardware-accelerated rendering through your computer's graphics card. Enabled taps the hardware. Auto leans on a capable GPU when one exists and drops back to software rendering when no capable GPU is around

### Motion Blur

- Motion Blur: This flips the rendering of Motion Blur on the tool on or off. With this control on, the tool's predicted motion drives the motion blur that the virtual camera's shutter would create. With the control off, no motion blur is made.
- Quality: Quality sets how many samples build the blur. A quality setting of 2 has Fusion make two samples on either side of an object's true motion. Bigger values give smoother results but lengthen the render time.
- Shutter Angle: Shutter Angle steers the angle of the virtual shutter producing the motion blur effect. Wider angles make more blur but lengthen the render times. A value of 360 equals leaving the shutter open for one full frame exposure. Higher values are allowed and can drive interesting effects.
- Center Bias: Center Bias shifts where the center of the motion blur sits. That opens the door to motion trail effects.
- Sample Spread: Tweaking this control shifts the weighting handed to each sample. That changes the brightness of the samples.

Comments You use the Comments field to attach notes to a tool. Click into the empty field and type your text. Once a note is on a tool, a little red square shows in the lower-left corner of the node while the full tile is shown, or a small text bubble icon shows on the right while nodes are collapsed. To read the note inside the Node Editor, rest the mouse pointer over the node so the tooltip appears. Scripts Every tool in Fusion offers three Scripting fields from the Settings tab. Each holds an edit box where you can drop scripts that run while the tool renders. For deeper detail on scripting nodes, turn to the Fusion scripting documentation.
