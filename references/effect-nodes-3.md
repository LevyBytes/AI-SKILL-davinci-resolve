# Effect Nodes (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Normal: The default mode treats the foreground object's Alpha channel as a mask, deciding from it which pixels turn transparent and which stay opaque. While it's active, a further menu lists the available operations: Over, In, Held Out, Atop, and XOr.
- Screen: Screen combines the objects by multiplying their color values together. It disregards the Alpha channel, and layer order ceases to matter. Whatever color results comes out lighter. Screen against black and the color is untouched; screen against white and you always get white. The look it yields resembles several film frames projected onto a single surface. While it's active, a further menu lists the available operations: Over, In, Held Out, Atop, and XOr.
- Dissolve: Dissolve intermixes objects that overlap, doing the blend by way of a computed average of those objects.
- Multiply: Multiplies a color channel's values. The object appears to darken as those values run across the 0-to-1 scale. White sits at a value of 1, so the result stays the same; gray sits at 0.5, so the object turns darker, half as bright, to put it another way.
- verlay: Overlay either multiplies or screens the foreground object's color values, the choice driven by the background object's color values. Patterns or colors are laid over the existing pixels while the highlights and shadows of the color values belonging to the objects behind the foreground are kept intact. Those background objects aren't swapped out but mingled with the foreground objects so the original brightness or darkness of the background carries through.
- Soft Light: Soft Light either deepens or brightens the foreground object according to the color values of whatever lies behind it. The result feels like aiming a soft, diffused spotlight at the picture.
- Hard Light: Hard Light either multiplies or screens the foreground object's color values according to the color values of whatever lies behind it. The result feels like aiming a stark, harsh spotlight at the picture.
- Color Dodge: Color Dodge draws on the foreground object's color values to lift the brightness of the objects behind it, echoing the darkroom technique of dodging, where you cut an area's exposure during printing.
- Color Burn: Color Burn draws on the foreground object's color values to deepen the objects behind it, echoing the darkroom technique of burning, where you boost an area's exposure during printing.
- Darken: Darken reads the color data in every channel and keeps whichever color value, front object or back, is the darker one. Pixels brighter than the blended colors get swapped out, while pixels darker than the blended color hold steady.
- Lighten: Lighten reads the color data in every channel and keeps whichever color value, front object or back, is the lighter one. Pixels darker than the blended color get swapped out, while pixels brighter than the blended color hold steady.
- Difference: Difference reads the color data in every channel and subtracts the foreground object's color values from the background's, or the reverse, whichever carries the greater brightness value. A white blend inverts the color, while a black blend leaves it as-is.
- Exclusion: Exclusion yields a result akin to Difference mode but softer in contrast. A white blend inverts the base color values, while a black blend leaves them as-is.
- Hue: Hue builds a color from the luminance and saturation of the background object's color paired with the hue of the foreground object's color.
- Saturation: Saturation builds a color from the luminance and hue of the base color paired with the saturation of the blend color.
- Color: Color builds a color from the luminance of the background object's color paired with the hue and saturation of the front object. It keeps the image's gray levels intact and is handy for tinting monochrome objects.
- Luminosity: Luminosity builds a color from the hue and saturation of the background object's color paired with the luminance of the foreground object's color, producing the reverse of what Color mode does.

Operator This menu picks the Operation mode that takes over wherever the trailing objects overlap. Switching the Operation mode alters the way overlapping objects get merged into a result. The dropdown only appears while the Apply mode sits at Normal. Within the trails node, pixels are always combined by the formula (fg object _ x) + (bg object _ y). Each operation sets what x and y work out to, as spelled out under each mode below. The Operator Modes are as follows:

- Over: The Over mode lays the foreground object onto the background object, swapping the background pixels for the pixels out of the Z everywhere the foreground object's Alpha channel exceeds 1.

x = 1, y = 1 - [foreground object Alpha]

- In: The In mode multiplies the background object's Alpha channel against the foreground object's pixels. The foreground object's color channels are disregarded. Nothing but foreground-object pixels survive into the final output. In effect this trims the foreground object down using the background object's mask.

x = [background Alpha], y = 0

- Held Out: Held Out is, in essence, the inverse of the In operation. Here the foreground object's pixels are multiplied against the background object's inverted Alpha channel.

x = 1 - [background Alpha], y = 0

- Atop: Atop sets the foreground object over the background object solely where the background object carries a matte.

x = [background Alpha], y = 1 - [foreground Alpha]

- XOr: XOr joins the foreground object and the background object anywhere one of the two has a matte, yet never where both have a matte at once.

x = 1 - [background Alpha], y = 1 - [foreground Alpha] Subtractive/Additive This slider dictates whether Fusion runs an Additive composite, a Subtractive composite, or some mix of the two where the trailing objects overlap. Its default is Additive, on the assumption that the incoming image's Alpha channel is premultiplied, which is the usual situation. In case the distinction between Additive and Subtractive compositing is unfamiliar, a brief rundown follows. NOTE: You need an Additive blend operation whenever the foreground image is premultiplied, meaning its color-channel pixels have already been multiplied by the Alpha-channel pixels. Because of that, transparent pixels always come out black, since anything times 0 is 0. The operation hides the background (multiplying it by the inverse of the foreground Alpha) and then sums in the foreground pixels. You need a Subtractive blend operation when the foreground image is not premultiplied. That compositing approach resembles an additive composite, except the foreground image first gets multiplied by its own Alpha to strip away any background pixels lying outside the Alpha region. Where many other applications make Additive/Subtractive a simple either/or checkbox, the Trails node instead lets you slide between the Additive and Subtractive flavors of the compositing operation, which proves handy for taming troublesome edges that read too bright or too dark. To illustrate: Subtractive merging on a premultiplied image can yield darker edges, while Additive merging on a non-premultiplied image throws any non-black area beyond the foreground's Alpha into the result and so brightens the edges. Sliding between Additive and Subtractive lets you tune the edge brightness to exactly suit the shot. Alpha Gain Alpha Gain scales, in linear fashion, the Alpha-channel values of the trailing objects up front. That cuts down how much the trailing objects in back get hidden, brightening the whole result. With the Subtractive/Additive slider on Additive and Alpha Gain at 0.0, the foreground pixels are summed onto the background. With the Subtractive/Additive slider on Subtractive, this instead governs the composite's density, much like Blend.

Burn In The Burn In control sets how much Alpha goes toward darkening the objects that trail beneath others, leaving untouched how many foreground objects get summed in. At 0.0, the blend acts like a plain Alpha blend. At 1.0, the front objects are essentially summed onto the back objects (with Alpha multiplication first, if you're in Subtractive mode). The upshot is that the foreground objects brighten the ones behind, just as Alpha Gain does. Indeed, for Additive blends, raising Burn In lands the same result as lowering Alpha Gain. Merge Under Switch this on and the current image is set beneath the generated trail rather than the customary over-the-top arrangement. The trailing elements' layer order is flipped as well, so the final trail ends up on top.

### Common Controls

Settings Tab Since the Settings tab controls are shared by every Effect node, you'll find their write-ups in the “The Common Controls” section closing out this chapter.

### TV [TV]

### The TV node

### TV Node Introduction

The TV node is a basic node built to reproduce a few of the everyday defects you'd spot in analog television broadcasts and on their screens. Within DaVinci Resolve this Fusion-specific node is largely redundant now, thanks to the more capable Analog Damage ResolveFX.

### Input

The TV node's two inputs serve to attach a 2D image plus an effect mask, the latter handy for confining where the TV effect shows up. Input: The orange input takes the main 2D image that the TV distortion gets applied to. Effect Mask: The blue input accepts a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps drawn from other tools. Wiring a mask into this input restricts the zone in which the TV effect to appears. Any effects mask gets applied to the tool once the tool itself has been processed.

### Basic Node Setup

An image's output gets wired into the TV node's input. From there you shape the flavor of TV interference through the controls over in the Inspector.

The TV node reproduces television-style defects across whatever image is wired into its orange input Inspector

### TV node controls

### Controls Tab

The Controls tab is the first among three tabs for tailoring the analog TV distortion. This one reworks the effect's scan lines and image distortion. Scan Lines This slider recreates the interlaced look by knocking lines out of the picture. Set it to black with a transparent Alpha and a line drops. A value of 1 (default) removes every other line. A value of 2 keeps one line, then drops the next two, and repeats that pattern. A value of zero switches the effect off. Horizontal Reach for this slider to nudge the picture with a plain Horizontal offset. Vertical Reach for this slider to nudge the picture with a plain Vertical offset. Skew This slider lays a diagonal offset on the picture. Positive values lean the image toward the top left, negative values toward the top right. Pixels shoved past the frame wrap around and resurface on the picture's far side. Amplitude The Amplitude slider lets you bring smooth sine-wave-style deformation to the picture's edges. Crank the value up and the deformation grows more intense. Lean on the Frequency control to govern how often the distortion repeats.

Frequency The Frequency slider fixes the frequency of the sine wave that warps the picture's edges once the amplitude control rises past 1. Offset Use Offset to shift the sine wave's position, which drives the deformation the Amplitude and Frequency controls apply to ripple across the picture.

### The TV Noise tab

### Noise Tab

The Noise tab is the second among three tabs for tailoring the analog TV distortion. This one shapes the picture's noise to mimic a feeble analog antenna signal. Power Push this slider's value past 0 to seed noise into the picture; the higher it climbs, the heavier the noise. Size Reach for this slider to blow the noise map up larger. Random Leave this thumbwheel control at 0 and the noise map holds still. Vary its value over time and the static shifts from one frame to the next.

### The TV Roll Bar tab

### Roll Bar Tab

The Roll Bar tab is the third among three tabs for tailoring the analog TV distortion. This one drives the bar's animation. Bar Strength With the default value of 0, nothing gets drawn. Raise it and the region the bar covers grows darker.

Bar Size Push this slider's value up to give the bar more height. Bar Offset Animate this control to scroll the bar across the screen.

### Common Controls

Settings Tab Since the Settings tab controls are shared by every Effect node, their write-ups sit in the “The Common Controls” section that comes next.

### The Common Controls

A number of identical controls turn up in the Inspector across all Effect nodes. The controls covered in this section are the ones Effect nodes hold in common.

### Inspector

### The Common Effects Settings tab

### Settings Tab

You'll find the Inspector's Settings tab on every tool within the Effects category, and the Settings controls show up even on third-party Effects-type plugin tools. They stay consistent and behave the same from tool to tool, though a handful of tools toss in one or two of their own options, which get covered here too. Blend The Blend control mixes between the tool's original image input and the tool's finished, altered output image. With the blend value at 0.0, the outgoing image matches the incoming one exactly, so the tool bypasses processing altogether and copies the input straight through to the output. Process When Blend Is 0.0 The tool still processes even with the input value at zero, which helps when the node is scripted to kick off some other task while the blend sits at 0.0. Red/Green/Blue/Alpha Channel Selector This quartet of buttons pins the tool's effect to particular color channels. Typically the filter kicks in once the tool has finished processing. Take a Blur tool with its red button switched off: the blur runs across the image first, after which the red channel from the original input is laid back over the result's red channel. A few exceptions exist, namely tools where switching off these channels makes the tool skip that channel's processing entirely. Such tools carry a matching set of RGBA buttons on their Controls tab, and in that case the buttons on the Settings and the Control tabs are one and the same. Apply Mask Inverted Switching on the Apply Mask Inverted option flips the tool's entire mask channel. That mask channel is the merged product of every mask wired into or produced within a node. Multiply by Mask Choose this option and the masked image's RGB values get multiplied by the mask channel's values, which turns every image pixel left out of the mask (that is, set to 0) black/transparent. Use Object/Use Material (Checkboxes) Certain 3D software can render to file formats carrying extra channels. The EXR file format in particular supports Object and Material ID channels, either of which can act as a mask for the effect. These checkboxes decide whether those channels get used when they're present, and the precise Material ID or Object ID involved is set with the next group of controls. Correct Edges This checkbox surfaces only while the Use Object or Use Material checkboxes are on. It flips between the methods for handling overlapping object edges in a multi-object image. Switched on, the Coverage and Background Color channels come into play to cleanly separate and refine the effect around an object's edge. Switched off (or with no Coverage or Background Color channels on hand), the mask edge can show aliasing. To dig further into coverage along with background channels, consult Chapter 78, “Understanding Image Channels,” within the DaVinci Resolve Reference Manual, or else Chapter 18 over in the Fusion Reference Manual.

Object ID/Material ID (Sliders) Reach for these sliders to pick which ID builds a mask out of an image's object or material channels. The Sample button works just like the Color Picker, letting you pluck IDs from the image shown in the view. That image or sequence has to have been rendered by a 3D software package with those channels baked in. Clipping Mode This option governs how the domain of definition rendering deals with edges. Clipping mode matters most once blur or softness enters the picture, since those may need samples drawn from parts of the image beyond the current domain.

- Frame: Frame is the default; it automatically points the node's domain of definition at the image's full frame, in effect disregarding the current domain of definition. Should the upstream DoD fall short of the frame, whatever remains of the frame counts as black/transparent.
- None: Pick None and no clipping of the source image takes place. Any data the node's effect needs that would ordinarily sit beyond the upstream DoD counts as black/transparent.

Use GPU The Use GPU menu carries three settings. Pick Disable and hardware-accelerated rendering on your computer's graphics card is switched off. Enabled puts the hardware to work. Auto draws on a capable GPU whenever one is on hand and drops back to software rendering when no capable GPU is around Motion Blur

- Motion Blur: This flips Motion Blur rendering on the tool on or off. With it switched on, the tool's predicted motion drives the motion blur a virtual camera's shutter would cause. With it switched off, no motion blur is generated.
- Quality: Quality fixes how many samples go into building the blur. A Quality setting of 2 has Fusion lay down two samples on each side of an object's real motion. Bigger values smooth the result but lengthen the render.
- Shutter Angle: Shutter Angle sets the angle of the virtual shutter that creates the motion blur effect. Wider angles pile on more blur but stretch the render times. A value of 360 matches a shutter held open for one whole frame's exposure. You can push past that, and higher values lend themselves to interesting effects.
- Center Bias: Center Bias shifts where the motion blur's center sits, opening the door to motion-trail effects.
- Sample Spread: Tweaking this control reweights each sample, which bears on how bright the samples come out.

Comments The Comments field lets you attach notes to a tool. Click into the blank field and type away. Once a note is on a tool, a tiny red square shows in the node's lower-left corner while the full tile is shown, or a tiny text-bubble icon appears at the right when the nodes are collapsed. To read the note inside the Node Editor, rest the mouse pointer on the node so the tooltip pops up. Scripts Every tool in Fusion offers three Scripting fields off the Settings tab. Each holds an edit box for entering scripts that fire while the tool renders. For fuller details on scripting nodes, turn to the Fusion scripting documentation.
