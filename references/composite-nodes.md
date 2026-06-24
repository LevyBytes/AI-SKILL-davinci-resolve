# Composite Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Composite Nodes

This section covers the Dissolve and Merge nodes that Fusion offers.

Each node name is paired with an abbreviation; you can type these into the Select Tool dialog while hunting for tools and reference them when scripting. Throughout this document, treat node graphs that display MediaIn nodes in DaVinci Resolve as equivalent to Loader nodes in Fusion Studio, except where a difference is called out.

### Dissolve [DX]

### The Dissolve node

### Dissolve Node Introduction

Most often the Dissolve node blends a pair of images so that one clip eases gradually into another. The blend ratio between foreground and background is governed by a Background/Foreground slider. Such dissolves are a staple of editing, letting you cross from one shot to the next. That said, pushing the Background/Foreground slider hard to either end lets you flip between inputs instead. The Dissolve node breaks from Fusion convention in that no image needs to be wired into the background; whichever of the two — background or foreground — gets output depends on where the Background/Foreground slider sits. Because of this trait, you can repurpose the Dissolve node as an automatic layer-switcher whenever it is fed background and foreground clips of unequal length. Wire each clip to its respective background and foreground input, then push the Background/Foreground slider toward the shorter clip to decide which one sits “on top.” Once that clip plays past its final frame, the Dissolve node hands off automatically to whatever is wired to the remaining input. Beyond the ordinary dissolve, choosing Gradient Wipe from the Operation menu lets you build freeform animated dissolve patterns driven by the luminance of an image fed into the optional Gradient Wipe input. Feed it anything — geometric shapes, assorted gradients, footage of fire, rippling water, or rain, the Fast Noise node, or particle systems built right on the Fusion page — to author all sorts of original transitions. Layering soft-edged effect masks on top widens the range of looks even further. In the end, keyframing the Background/Foreground control gives you authority over the transition that carries you from the foreground input across to the background, or the reverse.

### Inputs

Three optional image inputs are offered by the Dissolve node: Background: One of the two images you intend to mix or flip between. Contrary to how most nodes behave, you needn't wire the background input ahead of the foreground input. Foreground: The other of the two images you intend to mix or flip between. Results are best when the foreground and background inputs both receive images at matching resolution. Gradient Map: (Optional) You only need the Gradient Map when Gradient Wipe is the chosen mode.

### Basic Node Setup

A standard wiring for Dissolve nodes feeds two source images into the background and foreground inputs and routes the output onward to the next node in the comp.

### A typical dissolve node structure in Fusion

### Resolution Handling

Best practice is to keep every image fed to the foreground, background, and gradient map inputs of the Dissolve node at one shared resolution and one shared pixel aspect. None of that is mandatory, though. When you do mix resolutions, the outcome hinges on where the Background/ Foreground slider lands.

- Where the source images differ in size yet the Foreground/Background slider sits at full Foreground (pushed fully right) or full Background (pushed fully left), the output resolution matches the image resolution of whichever node input is selected.
- Where source images of unequal size are blended by parking the Background/Foreground slider somewhere in the middle, the output adopts the larger of the two input resolutions so that both images fit. Under those conditions, you may notice unwanted resolution shifts as the slider travels from full foreground or background toward an intermediate spot.

Say, for instance, you dissolve a 4K image (wired to the background) into an 8K image (wired to the foreground): the Dissolve node puts out 4K while the slider rests at full Background, then abruptly leaps to 8K once you set full Foreground or blend anywhere between the foreground and background.

### Inspector

### Dissolve controls

### Controls Tab

Here are the primary controls steering how the Dissolve node behaves.

- Operation Pop-Up: Seven distinct techniques for blending the Foreground and Background inputs live in the Operation menu. The pair of images blend according to the Background/Foreground slider value, which sets the contribution percentage of each.

Dissolve: The ordinary Dissolve mode behaves like a cross dissolve — as one clip fades out, the other fades in. Additive Dissolve: Resembling a classic film dissolve, an Additive dissolve first sums in the second clip and afterward fades the first one away. Erode: The Erode technique crosses between the two images by spreading the darkest regions of the background image until the foreground image shows through. Visually it resembles a strip of film burning away. Random Dissolve: The blend between images is carried out with a randomly created dot pattern. Random Noise Dissolve: The blend is carried out using a dot pattern that shifts randomly over time. Gradient Wipe: Here the dissolve follows the luminance values found in the image at the Gradient Map input. You can soften the edges of this dissolve, and both the border's density and its color are adjustable on their own. SMPTE Wipe: The SMPTE wipe mimics the elementary effect wipes seen on many video effects switchers. Both a horizontal wipe and a vertical wipe are supplied. These wipes accept soft edges and added borders, with the border's density and color each set independently.

- Background/Foreground Slider: Defaults to Foreground. This control decides whether what you get out is the background image, the foreground image, or some blend of the pair. Which kind of blend is dictated by the Operation control. Should either input image be unavailable at the moment, the remaining one is output no matter where this slider sits.

### Gradient/SMPTE Wipe Controls

These controls show up solely when Gradient Wipe or SMPTE Wipe is chosen.

- Wipe Style: (SMPTE Wipe only) Two wipe styles can be picked from this drop-down list: Horizontal - Left to Right and Vertical - Top to Bottom. Tick the Invert Wipe checkbox to flip the wipe's direction.
- Invert Wipe: (SMPTE Wipe only) Ticking this reverses the direction of the wipe.
- Softness: Reach for this control when you want to soften the transition's edge.
- Border: Turning on the Border lets you color the transition's edge and brings its related

controls into view. The result is a border drawn around the transition edge.

- Border Softness: (Appears only when Border is turned on) Both the width and density of the border are governed by the Border Softness slider.

Raising the value yields a denser border, while lowering it yields a thinner one.

- Border Color: (Appears only when Border is turned on) Pick the hue applied to the border via Border Color.

### Common Controls

Settings Tab The Inspector's Settings tab appears identically in both the Dissolve and Merge nodes. Full coverage of these shared controls comes later, in this chapter's “The Common Controls” section.

### Merge [Mrg]

### The Merge node

### Merge Node Introduction

Working from the Alpha (opacity) channel that belongs to the front image, the Merge node fuses two pictures together. Two inputs feed this node: a background image and a foreground image. Which technique fuses the foreground and background is governed by the Operation mode, which covers the usual Over, In, Held Out, Atop, and XOr compositing methods. Alongside that, an Apply Mode pop-up offers various composite modes, transfer modes, or blend modes (call them what you like) for stacking the foreground against the background in assorted ways. Among these are familiar modes like screen, dissolve, multiply, overlay, plus a great many more. Depending on how your comps and footage are configured, the Merge node handles both additive (premultiplied) and subtractive (non-premultiplied) compositing. On top of that, the Additive/Subtractive slider gives you room to mix between additive and subtractive composite outcomes — a handy bonus that sometimes rescues troublesome edges. By default, the order in which layers stack within this node follows the foreground and background input wiring. You can, however, switch on Z-Depth compositing whenever Z-channels exist in the input images. Z-merging weighs the depth value of every pixel across the layers to work out which pixels belong in front and which belong behind.

### Inputs

Three optional image inputs come with the Merge node: Background: The orange background input takes the first of the two images you mean to composite. Wire the background input first, before you attach the foreground input. Attach an image to the background while leaving the foreground input empty, and the Merge node simply outputs that background image. Foreground: The green foreground input takes the second of the two images for compositing, usually a foreground subject meant to sit ahead of the background. Attach something to the foreground input while the background input is still empty, and the Merge node produces no output at all. Effect Mask: (Optional) The effect mask input restricts the merged region of the output to wherever the mask is white (where the foreground image appears ahead of the background), allowing the background image alone to show through wherever the mask is black.

### Basic Node Setup

A common wiring for Merge nodes runs two source images into the background and foreground inputs and sends the output onward to the next node in the comp. The effect mask input stays unused in this example, since that is the usual case.

### A typical Merge node structure in DaVinci Resolve

### Resolution Handling

Although images of any resolution may be wired into the background and foreground inputs of the Merge node, it is the image on the background input that sets the output resolution. TIP: To alter the resolution of whatever is wired to the background, reach for the Crop node to resize the image's “canvas” resolution while leaving the original image's dimensions alone, or reach for the Resize node to alter both the resolution and the image's size together.

### Inspector

### Merge node controls

### Merge Tab

Most of the controls you need to tailor a typical merge live on the Merge tab. Foreground Sizing Controls These controls let you resize whatever image feeds the foreground input, so in simple comps there is no need for a separate Transform node just to fit the foreground layer onto the background layer.

- Center X and Y: This control places the foreground image within the composite. Its default is 0.5, 0.5, which drops the foreground image squarely in the middle of the background image. The displayed figure always reflects the real position in normalized coordinates, scaled by the reference size. The reference size controls are explained further down.
- Size: Turn to this control to grow or shrink the foreground image before it lands over the background. This slider spans 0.0 to 5.0, though you may type in any value above 0 by hand. At a size of 1.0 you get a pixel-for-pixel composite, where one foreground pixel equals one background pixel in size.
- Angle: Turn to this control to spin the foreground image before it joins with the background.

Compositing Mode and Adjustment Controls The six parameters that follow govern how the background and foreground input images merge into one output image.

- Apply Modes: Whichever math is used to blend or combine the foreground and background pixels is set by the Apply Mode setting.

Normal: The default Normal merge mode treats the foreground's Alpha channel as a mask, sorting transparent pixels from opaque ones. While it is active, a second menu surfaces the available operations — Over, In, Held Out, Atop, and XOr. Screen: Screen fuses the images by multiplying their color values together. Here the Alpha channel is disregarded and layer order stops mattering. The outcome is invariably brighter. Screen against black and the color stays put, whereas screen against white and you always land on white. The look recalls several film frames projected together onto one surface. While it is active, a second menu surfaces the available operations — Over, In, Held Out, Atop, and XOr. Dissolve: Dissolve combines two image sequences, blending them via a computed average of the two pictures. Darken: Darken inspects the color data per channel and keeps whichever of the background or foreground image's color value is darker as the result color. Pixels brighter than the merged colors get swapped out, while pixels darker than the merged color stay as they are. Multiply: Multiplies a color channel's values. As values scale from 0 to 1 this tends to darken the image. White carries a value of 1, so the result is unchanged. Gray carries a value of 0.5, so the result comes out darker — an image at half brightness. Color Burn: Color Burn leans on the foreground's color values to darken the background image. It parallels the darkroom practice of burning, where you boost the exposure over a region of a print. Linear Burn: Linear Burn dims the base color according to the blend color's value. Its result runs darker than Multiply yet less saturated than Color Burn. Among the Darker group, Linear Burn also yields the strongest contrast in darker colors of any blending mode.

Darker Color: The Darker Color blending mode closely resembles Darken. It does not actually blend pixels; instead it merely weighs the base color against the blend color and retains whichever is darker. What sets it apart is that Darker Color judges the combined RGB channels together, while Darken evaluates each RGB channel on its own before settling on a final blend. Lighten: Lighten reads the color data in each channel and picks whichever of the background or foreground image's color values is brighter as the result color value. Pixels darker than the merged color get swapped out, while pixels brighter than the merged color stay put. Color Dodge: Color Dodge applies the foreground's color values to brighten the background image, echoing the darkroom practice of dodging, where you cut the exposure over a region of a print. Linear Dodge: Linear Dodge (Add) gives results akin to Screen or Color Dodge but stronger. This mode reads the color data per channel and lifts the base color toward the blend color by raising brightness. Blending against black changes nothing. Linear Dodge (Add) behaves differently depending on whether Fill Opacity or Opacity is what you adjust. Lighter Color: Lighter Color is much like Lighten. It does not blend pixels; it only weighs the base color against the blend color and keeps the brighter one. What sets it apart is that Lighter Color judges the combined RGB channels, while Lighten works through each RGB channel to reach a final blend. Overlay: Overlay either multiplies or screens the foreground image's color values, the choice hinging on the background image's color values. Patterns or colors lay over the existing pixels while holding onto the background image's highlights and shadows. Rather than replacing the background image, it mixes the foreground into it so the background's original lightness or darkness still reads through. Soft Light: Soft Light brightens or dims the foreground image based on the background image's color values, much like aiming a diffused spotlight at the image. Hard Light: Hard Light either multiplies or screens the foreground image's color values, depending on the background image's color values, much like aiming a harsh spotlight at the image. Vivid Light: Vivid Light is a severe blend of Overlay and Soft Light. Anything below 50% gray gets darkened, and anything above 50% gray gets lightened. Vivid Light is one of the blending modes where dialing back the opacity often helps, because 100% opacity tends to be too aggressive. It ranks as the fifth of the eight blending modes that respond differently to reducing fill versus opacity. Linear Light: Linear Light marries Linear Dodge blending on the brighter pixels with a Linear Burn on the darker ones. The colors that emerge are usually extreme, so you may want the Opacity or Fill sliders to temper them. Linear Lights behaves differently depending on whether you adjust Fill Opacity or Opacity. Pin Light: Pin Light is a severe blending mode that runs Darken and Lighten at once. It can produce patches or blotches and strips out every mid-tone entirely. Difference: Difference reads the color data per channel and subtracts either the foreground color values from the background's or the background's from the foreground's, whichever holds the greater brightness value. Merging against white inverts the color, while merging against black changes nothing. Exclusion: Exclusion yields an effect like Difference but at lower contrast. Merging against white inverts the base color values, and merging against black changes nothing. Hue: Hue builds a result color from the luminance and saturation of the background color values combined with the hue of the foreground color values.

Saturation: Saturation builds a result color from the luminance and hue of the base color paired with the saturation of the blend color. Color: Color builds a result color from the luminance of the background color value together with the hue and saturation of the foreground. Because it keeps the image's gray levels intact, it works well for tinting monochrome images. Luminosity: Luminosity builds a result color from the hue and saturation of the background color values paired with the luminance of the foreground color values, producing the reverse of what the Color mode does. Hypotenuse: This blend mode suits HDR images carrying out-of-range colors above 1; it squares each color, sums them, and takes a square root to blend. Out = sqrt (Fc*Fc +Bc*Bc) Geometric: This blend mode suits HDR images carrying out-of-range colors above 1; for any value past zero, you get double the product of foreground and background color, then that total split by their sum. Out = 2*Fc*Bc / (Fc+Bc)

- Operator Modes: You pick the merge's Operation mode from this menu. Switching the Operation mode alters the way the foreground and background fuse into a result. This pop-up only appears while the Merge node's Apply mode is set to Normal or to Screen. For a first-rate account of the math behind the Operation modes, track down the 1984 paper "Compositing Digital Images" by Porter, Thomas, and T. Duff, which ran across pages 253-259 of the ACM SIGGRAPH Computer Graphics proceedings. In short, the math runs as laid out below. Bear in mind that a few modes absent from the Operator drop-down (Under, In, Held In, Below) are readily reached by swapping the foreground and background inputs (via Command-T or Ctrl-T) and selecting the matching mode. Pixels in the merge always combine through the formula (fg _ x) + (bg _ y). Each operation pins down precisely what x and y become, per the write-up for that mode.

Here are the Operator modes: Over: The Over mode stacks the foreground layer onto the background layer, swapping the background pixels for the pixels from the Z anywhere the foreground's Alpha channel exceeds 1. x = 1, y = 1-[foreground Alpha] In: Within the In mode, the foreground's pixels are multiplied by the background input's Alpha channel. The foreground input's color channels are disregarded. Nothing but foreground pixels survives into the final output. In effect this clips the foreground against the background's mask. x = [background Alpha], y = 0 Held Out: Held Out is basically the reverse of the In operation. The foreground image's pixels are multiplied against the background image's inverted Alpha channel. You can reach the very same result with the In operation plus a Matte Control node to invert the background image's matte channel. x = 1-[background Alpha], y = 0 Atop: Atop lays the foreground over the background solely where the background carries a matte.

x = [background Alpha], y = 1-[foreground Alpha] XOr: XOr fuses the foreground with the background anywhere that either the foreground or the background holds a matte, yet never where both hold one. x = 1-[background Alpha], y = 1-[foreground Alpha] Conjoint: The Conjoint mode performs a decision-driven combination of the Alpha channels from the foreground and background images; it comes in handy with soft-edged and motion-blurred Alpha, where the Alpha isn't solid.

### X= 1, Y= X+Y(1-af)/ab, if af>ab

Disjoint: The Disjoint mode performs a decision-driven combination of the Alpha channels from the foreground and background images; it helps you join layers without producing out-of-range Alpha, and premultiplied edges receive the proper Alpha combination.

### X= X+Y(1-af)/ab, Y= X+Y if af+ab<1

Mask: The Mask mode emits the background image scaled by the foreground Alpha.

### X = X \* af, Y =0

Stencil: The Stencil mode emits the background image scaled by the inverse foreground Alpha.

### X = X \* (1-af), Y =0

Under: The Under mode runs the identical operation to Over mode but flips the foreground and background images within the operations. X = Y, Y =X \*(1-af)

- Subtractive/Additive slider: Whether Fusion runs an Additive merge, a Subtractive merge, or a mix of the two is set by this slider. For most operations it defaults to Additive merging, on the assumption that the input images are premultiplied (as they typically are). In case the distinction between Additive and Subtractive merging is unfamiliar, here is a brief rundown.
- You need an Additive merge when the foreground image is premultiplied — that is, the color-channel pixels have already been multiplied by the Alpha-channel pixels. The upshot is that transparent pixels always come out black, since anything multiplied by 0 equals 0. This hides the background (by multiplying against the inverse of the foreground Alpha) and then merely sums in the foreground's pixels.
- You need a Subtractive merge when the foreground image is not premultiplied. The technique mirrors an additive merge, except the foreground image is first multiplied by its own Alpha to strip out any background pixels lying beyond the Alpha region.

Although the Additive/Subtractive option might just as well have been a simple checkbox picking one mode or the other, the Merge node instead lets you blend across the Additive and Subtractive variants of the merge — handy now and then for taming troublesome composites whose edges read as too bright or too dark. As an example, Subtractive merging on a premultiplied image can darken the edges, whereas Additive merging on a non-premultiplied image folds every non-black region beyond the foreground's Alpha into the result, brightening the edges. Blending across Additive and Subtractive lets you dial the edge brightness in exactly right for your shot.
