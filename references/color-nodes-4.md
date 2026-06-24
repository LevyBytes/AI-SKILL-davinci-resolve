# Color Nodes (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Through the Gain tab you govern the separate RGBA Lift/Gamma/Gain parameters. Such controls let you swiftly correct uneven color casts confined to particular channels. Lock R/G/B Switch this on and the Red, Green, and Blue channel controls for each effect collapse into a single slider. Effects on the Alpha channel stay independent. Gain RGBA What the Gain RGBA controls do is scale the image channel's values linearly. Every pixel gets the same multiplier, yet the result shows up more on bright pixels and less on dark ones. A black pixel won't budge, since any number times 0 always yields 0. Lift RGBA Whereas Gain pivots the color values around black, Lift pivots them around white. This control's value is multiplied into the pixel values. Set Lift to 0.5 and a pixel reading R0.0 G0.0 B0.0 becomes R0.5 G0.5, B0.5, while white pixels stay completely untouched. Lift bears down on the lower values more than the higher ones, so its grip is firmest across an image's low and middle tones. Gamma RGBA The Gamma RGBA controls steer the brightness of the image's midrange. This node behaves nonlinearly. Adjusting gamma leaves the image's white and black pixels alone, while the pure grays feel the most from changes to this parameter. Push this control hard and midrange pixels tend to get driven toward black or white, depending on the value you choose.

Pre-Divide/Post-Multiply Tick this checkbox and the image's pixel values are divided by the Alpha values ahead of the color correction, then multiplied by the Alpha value again once the correction is done. It comes in handy when you're trying to color correct images carrying premultiplied Alpha channels.

### Saturation Tab

Within this Setting tab live the controls for how intense the colors are in each separate RGB channel.

### Color Gain Saturation setting tab

RGB Saturation As you adjust a single channel, setting it to 0.0 drains every bit of that channel's color away. Going above one heightens the scene's color, driving it toward the primary color.

### Balance Tab

Inside the Color Gain node, this tab supplies controls for tuning a color channel's overall balance. You get separate color and brightness controls covering the image's High, Mid, and Dark ranges. The colors come paired as opposites drawn from the two leading color spaces. Red values may be nudged toward Cyan, Green values toward Magenta, and Blue toward Yellow. Each channel's brightness can be lifted or dropped.

### Color Gain Balance tab

CMY Brightness Highs/Mids/Darks Out of the box, the Balance sliders move from -1 to +1, though you can type in values past that span by hand to strengthen the result. Leaving any slider at 0.0 means the image channel goes unchanged. A positive or negative reading tells you the image channel's balance has been shifted toward one or the other color of the pair.

### Hue Tab

Turn to the Color Gain node's Hue tab when you want to rotate the image's overall hue while leaving brightness and saturation alone. Three sliders give you separate command over the High, Mid, and Dark ranges. Here's how the hues sit in order across the RGB color space: Red, Yellow, Green, Cyan, Blue, Magenta and Red.

### Color Gain Hue tab

High/Mid/Dark Hue Anything over 0 rotates the image's hue rightward (red shifts to yellow). Anything under 0 rotates it leftward (red shifts to magenta). Reach -1.0 or 1.0 and the hue rounds the full cycle back to where it began. The hue sliders default to a -1.0 to +1.0 span. You can key in values beyond that span by hand.

### Ranges Tab

Housed in the Ranges tab are the controls for declaring which of an image's pixels count as shadows and which count as highlights. The midrange is always worked out as whatever pixels fall outside both the shadows and the highlights.

### Color Gain Ranges tab

Spline Display You dial in the ranges by working the spline handles. Four spline points exist, each carrying a single Bézier handle. The upper pair of handles marks where the shadow and highlight ranges begin, while the lower pair marks where the range ends. Those Bézier handles govern the falloff. There are no dedicated controls for the midtones range, since it's taken to be whatever sits between the shadow and highlight ranges. The X and Y text controls under the Spline display let you type exact positions for whichever Bézier point or handle is selected. Preset Simple/Smooth Ranges Pressing one of these two buttons resets the spline ranges to either Smooth (the default) or Simple (linear).

### Settings Tab

You'll find the Inspector's Settings tab repeated across the other Color nodes as well. A full account of these shared controls waits at this chapter's close, in the “The Common Controls” section.

### Color Matrix [CMx]

### The Color Matrix node

### Color Matrix Node Introduction

With the ColorMatrix you get an enormous range of operations for tweaking values one color channel at a time.

### Inputs

Two inputs come with the Color Matrix node: one carries the main image and the other an effect mask. Input: This orange input is the sole connection you must make. It feeds in a 2D image for the color matrix to adjust. Effect Mask: The optional blue effect mask input takes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming out of other tools. Wiring a mask here confines the color matrix adjustment to just the pixels inside that mask. An effect mask gets applied to the tool once the tool has been processed.

### Basic Node Setup

As with plenty of 2D image-processing nodes, the Color Matrix node takes in a 2D image such as a Loader node or the MediaIn1 pictured below. Its output carries the node tree forward by wiring into a further 2D image-processing node or a Merge node.

### Inspector

A Color Matrix node working on a MediaIn1 node

### Color Matrix controls

### Controls Tab

Color Matrix scales the RGBA channels according to the figures you enter in a 4 x 4 grid. That grid's fifth column/row serves as an Add column. Update Lock With this control on, Fusion holds off rendering the node. It's handy for dialing in each of the node's values first, then clearing Update Lock to render it. Matrix This is what sets which kind of operation actually runs. Reading across, the horizontal rows lay out the node's output values, left to right being R, G, B, A, and Add. The vertical columns lay out the input values, top to bottom being R, G, B, A, and Add. Through the Add column you can simply add values onto the separate color channels. By default the output values match the input values exactly.

- 1.0 sends a full 100% of the Red channel input through to the Red channel output.
- 1.0 likewise carries 100% of the Green channel input over to the Green channel output.
- 1.0 passes 100% of the Blue channel input straight to the Blue channel output.
- 1.0 routes 100% of the Alpha channel input onward to the Alpha channel output.

Laid out as math, the matrix's default settings come out like this: [R out] = 1 _ [R in] + 0 _ [G in] + 0 _ [B in] + 0 _ [A in] + 0 [G out] = 0 _ [R in] + 1 _ [G in] + 0 _ [B in] + 0 _ [A in] + 0 [B out] = 0 _ [R in] + 0 _ [G in] + 1 _ [B in] + 0 _ [A in] + 0 [A out] = 0 _ [R in] + 0 _ [G in] + 0 _ [B in] + 1 _ [A in] + 0 Invert Turning this option on flips the Matrix. Picture shuffling channels around, running other operations through different nodes, then copying and pasting the original ColorMatrix, set to Invert, to bring your channels back to where they started.

### Example 1: Invert

Say you want a plain invert or negative of the color values while keeping the Alpha channel as is; the matrix would come out like this: Color Matrix example Notice that we're obliged to add 1 to every channel so the inverted values climb back into the positive numbers. We'll walk this example through one step at a time, watching the waveform of a 32-bit grayscale gradient. 1 The original grayscale.

Original Grayscale

2 RGB set to -1. That inverts the values, but they drop under 0.

RGB set to -1 3 Adding 1 to each channel holds the inversion in place while shifting the values back up into a positive range.

### Adding 1 to each channel

### Example 2: Brightness per Channel

Here the brightness of each channel is steered on its own. It takes 0.2 away from the red channel, puts 0.314 onto the green channel, and puts 0.75 onto the blue channel, all while Alpha stays put.

### Brightness per channel example

### Example 3: Copying Values

Color values can also be shuttled back and forth from one channel to another. Here the red channel holds the image's luminance values figured by thirds, the green channel holds luminance values figured by the proper black-and-white conversion method, and the blue channel takes a third approach that pulls more information from red and less from blue. On top of that, the blue channel's brightness drops by 0.1, and the Alpha channel is swapped out for the original blue channel.

### Copying Values example

### Settings Tab

This same Settings tab from the Inspector turns up in the other Color nodes too. The chapter spells out these shared controls thoroughly at its end, within “The Common Controls” section.

### Color Space [CS]

### The Color Space node

### Color Space Node Introduction

The Color Space node lets you operate on an image through an assortment of alternate color space formats. Out of the box Fusion runs on the RGB color space, and the bulk of nodes and displays read an image's primary channels as Red, Green, and Blue. Shift the color space away from RGB and most images take on an odd look, because Fusion's viewers keep reading the primary channels as Red, Green, and Blue. Convert an image to YUV and view it in one of the viewers, for instance, and the Y channel reads as Red, while Green stands in for the U channel and Blue for the V channel. A number of familiar Fusion interface elements point at the RGB channels straight away. Among them are the four buttons usually sitting on the Inspector's Settings tab that confine the node's effect to one color channel. Apply a conversion to an image and those buttons stay labeled R, G, and B, yet the values behind them now come from the present color space. (For an RGB to HLS conversion, as an example, Red stands for Hue, Green for Luminance, and Blue for Saturation. The color space conversion never alters the Alpha value.)

### Inputs

The Color Space node carries a pair of inputs, one taking the main image and the other an effect mask. Input: This orange input is the sole connection that's mandatory. It pipes in a 2D image for the color space operation to convert. Effect Mask: The optional blue effect mask input welcomes a mask shape made from polylines, plain primitive shapes, paint strokes, or bitmaps produced by other tools. Hooking a mask up here keeps the color space adjustment to nothing but the pixels falling inside that mask. The tool gets an effect mask applied to it once its processing has finished.

### Basic Node Setup

In the manner of many 2D image-processing nodes, the Color Space node accepts a 2D image such as a Loader or the MediaIn1 shown below, works on the image, and then stretches the node tree onward by joining to a further 2D image-processing node or a Merge node.

### Inspector

A Color Space node carrying out a conversion on a MediaIn1 node

### Color Space controls

### Controls Tab

Two menus make up the Color Space node's Controls tab. The upper Conversion menu sets whether you're taking an image to RGB or away from RGB. The lower menu chooses the alternative color space you're converting either to or from. Conversion Three options sit in this menu. None leaves the image alone. Pick To Color and the input image is taken into whichever color space the Color Type control below it names. Pick To RGB and the input image is brought back to the RGB color space out of the type named in the Color Type menu (YUV to RGB, say). Color Type This menu is where you pick the color space conversion that runs when the To Color conversion is active. With the To RGB option chosen in the Conversion menu, the Color Type option ought to match the input image's existing color space. Eight color space options are on offer.

- HSV (Hue, Saturation, and Value): Every pixel in the HSV color space gets spelled out by its Hue, Saturation, and Value components. Value is the trait that lets us tell a light color apart from a dark one, in other words brightness. Lowering saturation is loosely like working white into a paint chip on a palette. Raising Value is loosely like working in black.
- YUV (Luma, Blue Chroma, and Red Chroma): PAL video's analog broadcast relies on the YUV color space. In the past this format was a frequent choice for color correcting images, owing to how well-known it was among a big share of video engineers. Every pixel gets spelled out by its Luminance, Blue Chroma, and Red Chroma components.
- YIQ (Luma, In Phase, and Quadrature): NTSC video's analog broadcast relies on the YIQ color space. This one shows up far less than YUV and is hardly ever encountered in production. Every pixel gets spelled out by its Luminance, Chroma (the in-phase or red-cyan channel), and Quadrature (magenta-green) components.
- CMY (Cyan, Magenta, and Yellow): Though it's more at home in print, the CMY format crops up often in computer graphics from other software packages. Every pixel gets spelled out by its Cyan, Magenta, and Yellow components. CMY is nonlinear.
- HLS (Hue, Luminance, and Saturation): Every pixel in the HLS color space gets spelled out by its Hue, Luminance, and Saturation components. Only slight differences separate the HLS and HSV color spaces.
- XYZ (CIE Format): You use this mode to carry a CIE XYZ image to and from RGB color spaces. Unlike the other color spaces here, CIE XYZ is a weighted space rather than a nonlinear one. Nonlinear, in this sense, means that identical changes in value at different spots in the color space might not deliver the same visual magnitude of change to the eye.

Put plainly, the CIE color space is a perceptual color system whose weighted values came out of experiments in which subjects were tasked with matching an existing light source by means of three primary light sources. Because it spans the full gamut of colors a person can perceive, this color space is most commonly put to work for gamut conversion and for matching color spaces between image display formats.

- Negative: The color channels get inverted. The color space stays RGBA.
- BW: The image is turned into black and white. How much each channel adds to the luminance

of the image can be tuned through slider controls that show up once this option is chosen. Those sliders default to values reflecting each channel's typical perceptual share of an image's luminance. The image keeps its RGBA color space.

### Settings Tab

Other Color nodes carry a copy of this Inspector Settings tab as well. These shared controls get a detailed write-up where the chapter wraps up, under the “The Common Controls” section.

### Copy Aux [CpA]

### The Copy Aux node

### Copy Aux Node Introduction

You turn to the Copy Aux node to move channels around between the visible channels and the auxiliary data channels inside a single 2D image. As a rule, those auxiliary channels come rendered out of 3D applications. Among the auxiliary channels the Copy Aux node handles you'll find z-depth and background color, texture coordinates plus coverage, object ID alongside material ID, normals together with vectors and back vectors, and world position as well. Copy Aux is largely a convenience node, given that the same copying can be pulled off, with more effort, through a Channel Booleans node. Channel Booleans works on individual channels, whereas Copy Aux works on channel groups. By default, the Copy Aux node lifts its output's depth on its own to line up with the aux channel's depth. Copy Aux supports static normalization ranges too. What static normalization has over the dynamic normalization Fusion's viewers perform is that the colors hold steady over time. Picture viewing the Z or WorldPos values for a ball: you get a smooth gradient running white to black. Now suppose a different 3D object enters the background at some point. Dynamic normalization washes the ball nearly all white while that background object becomes the new black. Dynamic normalization also brings on flicker trouble when you view vector/disparity channels, which can make visually comparing the aux channels of two frames at different times hard.

### Inputs

A pair of inputs belongs to the Copy Aux node, one for the main image and one for an effect mask. Input: Of these, the orange input is the only connection you have to wire. It brings a 2D image in for the Copy Aux node to act on. Effect Mask: The optional blue effect mask input takes in a mask shape drawn from polylines, basic primitive shapes, paint strokes, or bitmaps that other tools supplied. Attaching a mask here pins the Copy Aux operation to only the pixels lying within that mask. The tool has an effect mask applied to it after its processing wraps up.

### Basic Node Setup

Much like a great many 2D image-processing nodes, the Copy Aux node takes a 2D image such as a Loader node or the MediaIn1 below. From there its output keeps the node tree going by linking to another 2D imageprocessing node or a Merge node.

A Copy Aux node acting on a MediaIn1 node

### Inspector

### Copy Aux controls

### Controls Tab

You use the Controls tab to copy groups of auxiliary channels into the RGBA channels. Copy Aux carries a fair few options, yet most of the time you just pick the channel to copy and leave the rest of the functionality aside. Mode The Mode menu decides whether the auxiliary channel goes into the RGBA color channel (Aux to Color) or the other way round (Color to Aux). Leaning on this option, you can have one Copy Aux node pull an auxiliary channel into color, run a few compositing operations on it, then have a second Copy Aux node write the color back into the auxiliary channel. With Mode set to Color to Aux, every option on the Controls tab apart from the Aux Channel menu is tucked out of sight. Aux Channel The Aux Channel menu picks which auxiliary channel gets copied from or written to, according to the current mode. Suppose the aux channel abcd holds a single valid component; it then copies as aaa1. With two valid components it becomes ab01, with three it becomes abc1, and a full four components copy as abcd. So the Z-channel, to illustrate, copies as zzz1, while texture coordinates turn into uv01 and normals into nxnynz1. Out Color Depth Out Color Depth governs the color depth of the output image. The bulk of aux channels hold float values, or if they're integer valued they can hold values past 255. Copying float values into an int8 or int16 image can be a snag, since negative values and values over 1.0 stand to be clipped. Precision can slip away as well. This option sets what occurs if the input image's RGBA channel depth isn't enough to hold the copied aux channel. Take care copying float channels into integer image formats, because they can get clipped should you not configure Copy Aux properly. For this node, every aux channel counts as float32 apart from ObjectID or MaterialID, which count as int16.

- Match Aux Channel Depth: The output image's RGBA channels have their bit depth raised to meet the aux channel's depth. Put concretely, that makes the output image's RGBA channels either int16 or float32. Tread carefully with this option, because if your color channels are normally int8, for instance, you're now spending 2x or 4x the memory on them. In particular, the Z, Coverage, TextureCoordinate, Normal, Vector, BackVector, WorldPosition, and Disparity channels always come out as float, while the Material/ObjectID channels come out as int16.
- Match Source Color Depth: The output image's RGBA channels keep the same bit depth as the input image. That can lead to a few surprises. If your input image is int8, for example, the XYZ components of normals (floating-point numbers in the [-1, 1] range) get clipped down to the non-negative [0, 1] range. For a starker case, think about what becomes of Z values. Z values are floating-point numbers held in the [-1e30, 0] range, and they all get truncated into the [0, 1] range, leaving your Z-channel packed with zeroes.
- Force Float32: The output image's RGBA channels are always given a bit depth of float32.

Channel Missing Channel Missing settles what occurs when a channel isn't there. It governs, for instance, what happens when you've opted to copy Disparity to Color but your input image carries no Disparity aux channel.

- Fail: The node fails and writes an error message out to the console.
- Use Default Value: This loads the RGBA channels with the default value of zero for everything

except Z, where it's -1e30. Kill Aux Channels Tick this and Copy Aux copies the chosen channel into RGBA and then puts out an image that's nothing but RGBA, with the other channels killed off. It helps when you want to bump up how many Copy Aux frames can be cached for playback—say, to play back a long disparity sequence. One handy tip: you can also apply the Kill Aux feature with just Color to Aux > Color for a lengthier color playback.

### Kill Aux channels

Enable Remapping Switch remapping on and the aux channel you've got selected gets rescaled, mapping the range linearly per the From and To slider picks described below. The Remapping options run ahead of the conversion operation. So, ahead of any clipping, you might give the From > Min-Max values a setting of -1, 1 so your normals get rescaled into the [0, 1] range, or hand them [-1000, 0] so your Z values move out of [-1000, 0] and into the [0, 1] range.

Bear in mind the Remapping options operate per channel. As a result, normals can take a default scale of [-1, +1] > [0, 1], whereas Z can be handed [-1000, 0] > [0, 1]. Toggle between normals and Z and both settings are retained. This can pay off in that you're able to lay out the remapping ranges and save them as a setting to reuse later. Remapping comes in handy for squeezing the aux channels into a fixed [0, 1] range for viewing, or, for instance, when you'd like to compress normals into the [0, 1] range so they fit in an int8 image.

- From > Min: The aux channel value that lines up with To > Min.
- From > Max: The aux channel value that lines up with To > Max. You're allowed to make

the max value smaller than the min value, which flips/inverts the values.

- Detect Range: This sweeps the current image to find the min/max values, then sets the

From > Min/ From > Max Value controls to whatever it found.

- Update Range: This sweeps the current image to find the min/max values, then widens the

existing [From > Min, From > Max] region so it takes in the min/max values the sweep turned up.

- To > Min: The smallest output value, defaulting to 0.
- To > Max: The largest output value, defaulting to 1.
- Invert: After rescaling has carried everything into the [To > Min, To > Max] range, this

flips/inverts the range.

### Settings Tab

Here too the Inspector's Settings tab is mirrored across the rest of the Color nodes. You'll find these shared controls covered fully at the chapter's conclusion, in the “The Common Controls” section.

### Gamut [Gmt]

### The Gamut node

### Gamut Node Introduction

The Gamut node carries controls for converting one color space into another and for stripping out or adding gamma curves. This node, together with the Cineon Log node, mostly serves to linearize images coming in and then put the right output gamma curve back on at the tail end of a node tree.

### Inputs

The Gamut node comes with two inputs: one handling the main image and the other an effect mask for confining where the conversion applies. Input: This orange input is the lone connection you're required to make. It feeds in a 2D image output that serves as the source for the gamut conversion. Effect Mask: The optional blue effect mask input takes a mask shape fashioned from polylines, basic primitive shapes, paint strokes, or bitmaps that came from other tools. Wiring a mask to this input restricts the Gamut operation to just the pixels sitting inside that mask. An effect mask is laid on the tool after the tool has been processed.

### Basic Node Setup
