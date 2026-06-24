# Effect Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Effect Nodes

Here you will find documentation covering the Effect nodes in Fusion.

You can type the short abbreviation shown beside each node name into the Select Tool dialog while looking up tools, and these abbreviations also serve scripting purposes. Throughout this text, any node tree that depicts MediaIn nodes inside DaVinci Resolve should be read as equivalent to Loader nodes within Fusion Studio, except where a difference is called out.

### Duplicate [Dup]

### The Duplicate node

### Duplicate Node Introduction

Much like its counterpart the Duplicate 3D node, this Duplicate node lets you rapidly clone any 2D image while feeding each clone an incremental transform, which builds tiling patterns and intricate object arrays. Controls found under the Jitter tab make uneven transforms possible, for instance randomized placement or scaling.

### Inputs

This node exposes a pair of inputs: one for a 2D image and one for an effect mask that confines where the cloned objects show up. Input: The orange input takes the principal 2D image to be cloned. Effect Mask: The blue input accepts a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask here keeps the cloned objects visible solely within the masked pixels. Such a mask is processed after the tool itself has run.

### Basic Node Setup

There are many possible ways to wire and apply this node, with assorted inputs feeding it. In the example below, which produces motion graphics, a masked Background node yields a round shape that the Duplicate node then clones.

A Duplicate node used to create a repeating circular object

### Inspector

### Duplicate controls

### Controls Tab

Within the Controls tab sit every parameter for generating, shifting, and resizing copies of whatever object feeds the node's input. Copies This slider governs how many copies get produced. Every copy is derived from the previous one. With a setting of 5, the parent gets copied, that copy is then copied, the copy of that copy is copied next, and the chain continues. Such chaining yields intriguing results once you apply transforms to each copy through the parameters that follow. Time Offset Drag the Time Offset slider to shift any animation on the source image by a fixed step for each copy. As a demonstration, dial the value to -1.0 with a square rotating on the Y-axis serving as the source. Your first copy displays the animation one frame back. The next copy displays it a frame earlier still, continuing in sequence. On textured planes this is especially powerful, since consecutive clip frames can be displayed at once. Center The X and Y Center fields establish the positional offset given to every copy. Setting an X offset of 1 nudges each copy one unit along the X-axis away from the prior one.

Pivot The Pivot fields fix where the pivot point lands when you alter the size, position, or angle of each copy. That pivot stays put rather than traveling with either the source object or the cloned array. If you want the pivot to track the array, you must adjust the Pivot fields yourself. Size The Size field dictates the scaling amount given to each copy. Angle The Angle field specifies the degree of Z rotation given to each copy. This angular change scales linearly according to where the pivot point sits.

### Angle adjustment with centered pivot

### Angle adjustment with offset pivot

Apply Mode The Apply Mode choice sets the arithmetic used to blend or merge overlapping cloned objects.

- Normal: This default treats the foreground object’s Alpha channel as a mask that says which pixels stay transparent and which do not. With it active, a second menu surfaces the available operations: Over, In, Held Out, Atop, and XOr.
- Screen: Screen merges objects by multiplying their color values together. Here the Alpha channel plays no part and stacking order stops mattering. The output color always trends brighter. A black screen value leaves the color as-is, while a white screen value yields pure white. The look resembles several film frames projected together onto one surface. With it active, a second menu surfaces the available operations: Over, In, Held Out, Atop, and XOr.
- Dissolve: Dissolve blends overlapping objects together, deriving the blend from a computed average of those objects.
- Multiply: This multiplies the values within a color channel. The object appears to darken as the values run from 0 to 1. Since White equals 1, the outcome stays unchanged; since Gray equals 0.5, the outcome becomes a darker object, that is, one half as bright.
- Overlay: Depending on the values of the object underneath, Overlay either multiplies or screens the foreground object’s color values. Colors and patterns lay over the present pixels yet keep intact the highlights and shadows belonging to the underlying objects. Rather than being swapped out, the lower objects blend with the front ones so the original brightness or darkness shows through.
- Soft Light: Based on the color values of the objects underneath, Soft Light either dims or brightens the foreground object. The result is much like aiming a diffused spotlight at the picture.
- Hard Light: Based on the color values of the objects underneath, Hard Light either multiplies or screens the foreground object’s color values. The result is much like aiming a harsh spotlight at the picture.
- Color Dodge: Drawing on the foreground object’s color values, Color Dodge lightens the objects beneath it. It parallels the darkroom technique of dodging, which cuts an area’s exposure on a print.
- Color Burn: Drawing on the foreground object’s color values, Color Burn darkens the objects beneath it. It parallels the darkroom technique of burning, which raises an area’s exposure on a print.
- Darken: Per channel, Darken inspects the color data and picks whichever of the foreground or background color value is darker as the outcome. Pixels brighter than the blended colors get swapped out, while pixels darker than the blend stay put.
- Lighten: Per channel, Lighten inspects the color data and picks whichever of the foreground or background color values is lighter as the outcome value. Pixels darker than the blend get swapped out, while pixels brighter than the blend stay put.
- Difference: Per channel, Difference inspects the color data and, according to which side carries the greater brightness, subtracts the foreground object’s color values from the background’s, or vice versa. A white blend inverts the color; a black blend leaves it alone.
- Exclusion: Exclusion yields a result akin to the Difference mode but with reduced contrast. A white blend inverts the base color values; a black blend leaves them alone.
- Hue: Hue forms a result color that takes its luminance and saturation from the background objects’ color values and its hue from the foreground object’s color values.
- Saturation: Saturation forms a result color from the luminance and hue of the base color combined with the saturation of the blend color.
- Color: Color forms a result color carrying the luminance of the background object’s color value plus the hue and saturation of the foreground objects. Because it holds the image’s gray levels intact, it works well for tinting monochrome objects.
- Luminosity: Luminosity builds a color from the background object’s hue and saturation together with the foreground object’s luminance. The result is the reverse of what the Color mode produces.

Operator Through this menu you pick the Operation mode applied where duplicate objects overlap. Switching the Operation mode alters how those overlapping objects merge. The drop-down shows up only while the Apply mode sits at Normal. Within the Duplicate node, pixels are always combined by the formula (fg object _ x) + (bg object _ y). Each operation defines what x and y stand for, per the explanation given for every mode. Here are the Operator Modes:

- Over: Wherever the foreground object’s Alpha channel exceeds 1, the Over mode stacks the foreground onto the background by swapping the background pixels for the pixels coming from the Z.

x = 1, y = 1 - [foreground object Alpha]

- In: The In mode takes the background object’s Alpha channel and multiplies it against the foreground object’s pixels. It disregards the foreground object’s color channels. The output retains only

foreground object pixels. In effect this trims the foreground object by the background object’s mask. x = [background Alpha], y = 0

- Held Out: Held Out behaves as the inverse of the In operation. Here the foreground object’s pixels get multiplied by the background object’s inverted Alpha channel.

x = 1 - [background Alpha], y = 0

- Atop: Atop lays the foreground object on top of the background object solely where the background object carries a matte.

x = [background Alpha], y = 1 - [foreground Alpha]

- XOr: XOr joins the foreground and background objects anywhere one or the other holds a matte, yet never where the two overlap with a matte.

x = 1 - [background Alpha], y = 1-[foreground Alpha] Subtractive/Additive Use this slider to choose whether Fusion runs an Additive composite, a Subtractive composite, or some mixture of the two where the duplicate objects overlap. By default it sits at Additive, on the assumption that the incoming image’s Alpha channel is premultiplied, which it generally is. Here is a brief primer if the distinction between Additive and Subtractive compositing is unclear. You need an Additive blend when the foreground image is premultiplied, meaning each color-channel pixel has already been multiplied by the matching Alpha-channel pixel. Consequently transparent pixels end up black, because anything times 0 stays 0. The operation hides the background by multiplying it with the inverted foreground Alpha and then adds the foreground pixels on top. A Subtractive blend is what you want when the foreground image lacks premultiplication. The technique resembles an additive composite, except the foreground image is first multiplied by its own Alpha to wipe out any background pixels lying beyond the Alpha region. Whereas most other software treats Additive/Subtractive as a strict either/or toggle, the Duplicate node permits a blend between the Additive and Subtractive flavors of the compositing math. That comes in handy for troublesome composites showing bright or dark fringes. As an illustration, Subtractive merging on a premultiplied image can darken edges, while Additive merging on a non-premultiplied image adds any non-black region beyond the foreground’s Alpha into the result and so lightens the edges. Sliding between Additive and Subtractive lets you dial the edge brightness exactly right for the shot. Gain The Gain RGB fields scale the image channel values in a linear fashion. Each pixel gets multiplied by one shared factor, though bright pixels shift more than dark ones. Black pixels stay fixed, since anything multiplied by 0 stays 0. Alpha Gain scales the Alpha-channel values of the front objects linearly. Doing so cuts how much the background objects get hidden and thereby brightens the whole result. With the Subtractive/Additive slider at Additive and Alpha Gain at 0.0, the foreground pixels merely add onto the background. With the Subtractive/Additive slider at Subtractive, it instead governs the composite’s density, much as Blend does. Every Gain value compounds with each successive duplication.

Blur Introduces a blur onto the cloned layers.

- Lock Blur: Ties the X and Y Blur sliders together so blurring stays symmetrical. It comes on by default. Deselecting the Lock Blur control hands you separate command of each axis.
- Blur: Determines how much blur the tool puts on the cloned layers. This Blur amount does not compound with the count of duplications.
- Glow: Puts a glow onto the blur of the cloned layers.
- Blend: The Blend slider sets what percentage of the processed image gets mixed back with the

original image. The closer the value sits to 0, the more of the original image it folds in.

- RGBA Scale: Lets you tune the strength of the separate Red, Green, Blue, and Alpha channels

feeding the blur of the cloned layers. Burn In The Burn In field sets how much Alpha is used to darken objects sitting behind others, while leaving the quantity of added foreground objects alone. At 0.0 the blend acts as a plain Alpha blend, whereas at 1.0 the front objects are essentially added onto the rear objects (following Alpha multiplication when in Subtractive mode). The upshot is that foreground objects appear to brighten the ones behind, just as Alpha Gain does. Indeed, with Additive blends, raising the Burn In matches the outcome of lowering Alpha Gain. Blend This blend control differs from the Blend slider found on the Common Settings tab. Adjusting it applies the blend across objects. The Blend slider dissolves the last object’s result first, the second-to-last next, and onward. The blend spans from 0 to 1, where 1 keeps every object fully opaque and 0 leaves only the source object visible. Merge Under Ticking this checkbox flips the stacking order of the cloned elements, so the final copy becomes the lowest layer and the first copy becomes the topmost.

### Jitter Tab

Controls on the Jitter tab let you randomize position, rotation, size, and color across all the copies that the Controls tab produced.

r Duplicate Jitter tab

Random Seed Together, the Random Seed slider and the Reseed button create a random origin point for how much jitter is applied to the cloned objects. Pair two Duplicate nodes with matching settings but different random seeds and you get two entirely separate outcomes. Center X and Y These two fields tune how much the X and Y position of the cloned objects varies. Axis X and Y These two fields tune how much the rotational pivot center of the cloned objects varies. They touch only the extra jitter rotation, leaving the rotation from the Controls tab’s Rotation settings untouched. X Size This field tunes how much the Scale of the cloned objects varies. Angle This dial tunes how much the Z rotation of the cloned objects varies. Gain The Gain RGBA fields randomly scale the image channel values in a linear way. Blend Adjusting this control randomizes the blend across objects.

### Common Controls

Settings Tab Because the Settings tab controls apply across every Effect node, you will find them documented under the “The Common Controls” heading that closes this chapter.

### Highlight [HIL]

### The Highlight node

### Highlight Node Introduction

In bright areas of the picture, the Highlight filter produces star-shaped highlights or glints, akin to what a lens star filter does.

### Inputs

The Highlight node carries three Inputs: one for the image, one for the effects mask, and a third for a highlight mask.

Input: The orange input handles the principal 2D image onto which the highlight goes. Effect Mask: The blue input accepts a mask shape made from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Wiring a mask here keeps the highlight confined to the masked pixels. Such a mask is processed after the tool runs. Highlight Mask: Through the white highlight mask input, the Highlight node permits pre-masking. The picture is filtered first, then the highlight goes on. After that the highlight merges back atop the source image. Differing from standard effect masks, it will not clip highlights off source pixels where the highlight reaches past the mask edges. In every other way highlight masks behave just like effects masks.

### Basic Node Setup

In the example below, the Highlight node produces glint-style highlights over an incoming picture, with the highlight mask keeping the effect within a chosen region.

### Inspector

A Highlight node placed on a picture, where a highlight mask confines the region of the effect

### Highlight controls

### Controls Tab

Every parameter for the highlight’s style lives on the Controls tab apart from color, which the Color Scale tab takes care of. Low and High This range control sets which span of Luminance values in the picture spawns highlights. Anything beneath the Low value gets no highlight. Anything past the High value gets the highlight at full strength.

Curve The Curve value adjusts the falloff across the highlight’s span. Raise it and the flare brightness fades nearer the highlight’s center; lower it and the fade happens farther out. Length This sets how long the flares reach from the highlight. Number of Points This fixes how many flares radiate out of the highlight. Angle This control spins the highlights. Merge Over Turn it on and the effect lays over the source image; turn it off and you get just the highlights as output. That is handy for color-correcting the highlights later down the chain.

### Highlight Color Scale controls

### Color Scale Tab

Color for the highlight is governed by the Color Scale tab. Click and hold the Pick button, then drag the pointer across the viewer, to grab a particular color out of the picture. Red, Green, and Blue Scale Lowering one or all of these channel sliders alters the highlight’s falloff color. Alpha Scale Lowering the Alpha slider renders the highlight falloff more see-through.

### Common Controls

Setting Tab Since the Settings tab controls are shared by all Effect nodes, look for their descriptions within the “The Common Controls” heading at this chapter’s close.

### Hot Spot [Hot]

### The Hot Spot node

### Hot Spot Node Introduction

With the Hot Spot node you build assorted lens flare, spotlight, and burn/dodge effects. Physically, lens flares arise when very bright light sources in a scene bounce off pieces of glass inside the camera’s lens. You will notice flares in a shot when a powerful light source, such as the sun or another brilliant star, is seen through a camera lens.

### Inputs

The Hot Spot node offers three inputs: one for the image, one for the effects mask, and one more for an Occlusion image. Input: The mandatory orange input handles the principal 2D image that receives the hot spot. Effect Mask: The blue input takes a mask shape drawn from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Wiring a mask here keeps the hot spot inside the masked pixels. Such a mask is processed once the tool has run. Occlusion: The green Occlusion input takes an image that supplies the occlusion matte. That matte serves to block the hot spot so it appears to “wink.” White pixels in the image occlude the hot spot, while gray pixels partly suppress it.

### Basic Node Setup

Because the Hot Spot node cannot generate on its own, you must feed it an image input onto which the hot spot is placed.

### Hot Spot node applied to an image

### Inspector

### Hot Spot controls

### Hot Spot Tab

Through the Hotspot tab you command the primary and secondary hot spots, dialing in each one's placement, size, strength, angle, plus its apply mode. Primary Center X and Y This sets where the primary hot spot lands in the scene. The placement of secondary lens elements and reflections is referenced off the primary hot spot’s position. Primary Strength This field fixes how bright the primary hot spot is. Hot Spot Size This field fixes the primary hot spot’s diameter, where a value of 1.0 spans a circle as wide as the whole image. Aspect This governs the spot’s aspect. At 1.0 the hot spot stays perfectly round; above 1.0 the circle stretches sideways, and below 1.0 it stretches up and down. Aspect Angle This field rotates the primary hot spot. Secondary Strength This field fixes the strength, meaning the brightness, of the secondary hot spot, which is a mirror of the primary one and always sits on the image’s opposite side from the primary hot spot.

Secondary Size This sets how large the secondary hot spot is. Apply Mode This field fixes the way the hot spot acts upon the picture beneath it.

- Add (Burn): The created spots brighten the picture.
- Subtract (Dodge): The created spots dim the picture.
- Multiply (Spotlight): The created spots single out one region of the picture with light while

darkening everything else. Occlude This menu lets you pick which channel of the image fed to the Hot Spot node’s Occlusion input supplies the occlusion matte. You can drive occlusion from the Alpha or the R, G, or B channels of whatever image is wired into the Occlusion input on the node’s tile. Lens Aberration Aberration reshapes and re-behaves the primary and secondary hot spots.

- In and Out Modes: Stretches the hot spot’s shape into a flare. With In mode the hot spot reaches toward the center, while with Out mode it reaches toward the corners.
- Flare In and Flare Out Modes: This setting is a lens distortion effect driven by the lens effect’s motion. Flare In intensifies the effect as the hot spot nears the center, whereas Flare Out grows the effect as the hot spot approaches the image edges.
- Lens: This setting mimics a circular, ringed lens look.

Aberration The Aberration slider sets the overall intensity of the lens aberration effect.

### Color Tab

Color for the primary and secondary hot spots is adjusted on the Color tab.

### Hot Spot color controls

Color Mode From this menu you decide whether color changes are animated or static, working through the compact curves editor in the Inspector.

- None: With the default None choice, a single static curve adjustment applies across the whole range.
- Animated Points: This choice lets the color curves in the spline region animate over time.

After you pick it, jump to the frame you want and make an edit in the Spline Editor to drop a keyframe.

- Dissolve mode: Largely outdated, Dissolve mode remains only for backward compatibility.

Color Channel and Mix Ticking these checkboxes turns on editing of the selected splines in the small Inspector Spline Editor. Ticking the Mix checkbox turns on the Mix Spline, which gauges the sway that the Radial tab controls hold along the hot spot’s radius. Red, Green, Blue, and Alpha Splines The Spline Window plots the curves for each separate channel and acts as a tiny Spline Editor. You use the Red, Green, Blue, and Alpha splines to shape the spotlight’s color across the hot spot’s radius. Up the vertical axis runs the color channel’s intensity or strength. Across the horizontal axis runs the hot spot position along the radius, going from the outer left edge to the inner right edge. By default the curve gives the red, green, blue, and Alpha channels a linear falloff. Mix Spline The Mix spline gauges the sway the Radial controls hold along the hot spot’s radius. Across the horizontal axis runs the position around the circle’s circumference, where 0 marks 0 degrees and 1.0 marks 360 degrees. Up the vertical axis runs how much of the radial hot spot to mix with the color hot spot. At 0 it is entirely the radial hot spot, and at 1.0 it is entirely the color hot spot. NOTE: A right-click within the LUT brings up a contextual menu offering options for editing spline curves.
