# Composite Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Alpha Gain slider: Alpha Gain scales the foreground's Alpha channel values in a linear fashion. Within Subtractive merges it governs the composite's density, much as Blend does. Within Additive merges it cuts down how much the background gets hidden, so the overall image grows brighter. Set Alpha Gain to 0.0 in an Additive merge and the foreground pixels are merely added onto the background.
- Burn In slider: What the Burn In control tunes is how much Alpha goes toward darkening the background, leaving the quantity of foreground added in untouched. At 0.0 the merge acts as a plain Alpha blend; at 1.0 the foreground is in effect summed onto the background (following Alpha multiplication when you're in Subtractive mode). The upshot is the foreground image lightening the background image, just as Alpha Gain does. With Additive merges, pushing the Burn In up produces the same outcome as pulling Alpha Gain down.
- Blend slider: Here you have a cloned copy of the Blend slider over on the Common Controls tab, and adjusting either one updates the other at the same moment. The Blend slider blends the node's result against its input, easing the effect back at any value under 1.0. In this instance it blends the background together with the merged result.

Additional Controls The controls that follow give you a way to refine what the settings above produce.

- Filter Method: Where input images are being resized, this setting picks the filter method that interpolates image pixels as clips are scaled. Linear is the default. Which setting serves best varies with the type of resizing at hand. The majority of these filters earn their keep only when enlarging an image. To shrink images the Linear filter is the usual choice, though the Catmull-Rom filter adds a measure of sharpening to the outcome and can help hold detail while scaling an image down.

Nearest Neighbor: Drops or repeats pixels where required, giving the quickest yet roughest output. Box: A straightforward interpolation resize of the image. Linear: Leans on a basic filter that turns out fairly clean, fast output. Quadratic: Yields a middling result, striking a fair balance between speed and quality. Cubic: Delivers stronger output on continuous-tone images, although images holding fine detail may come out blurrier than you'd like. Catmull-Rom: Works well on continuous-tone images scaled down, and renders sharp output on finely detailed images. Gaussian: Closely matches Bi-Cubic for both speed and quality. Mitchell: Resembles Catmull-Rom yet fares better on finely detailed images, at the cost of being slower than Catmull-Rom. Lanczos: Sits very close to Mitchell and Catmull-Rom but comes out a touch cleaner and, likewise, slower. Sinc: An advanced filter producing extremely sharp, detailed output, though in some cases it can introduce visible “ringing.” Bessel: Akin to the Sinc filter while possibly running a bit faster. Window Method: A handful of filters, Sinc and Bessel among them, would need an endless count of pixels to compute exactly. A windowing function steps in to approximate the filter and cap the pixel count, speeding the operation up. This control surfaces once you choose a filter that calls for windowing. Hanning: A plain tapered window. Hamming: Hamming is a lightly adjusted take on Hanning.

Blackman: A window whose falloff tapers more steeply. Kaiser: A more intricate window, landing somewhere between Hamming and Blackman.

The resize filters on display, in order: first Nearest Neighbor, then Box and Linear, followed by Quadratic plus Cubic, next Catmull-Rom alongside Gaussian, after that Mitchell with Lanczos, and lastly Sinc together with Bessel

- Edges Buttons: A set of four buttons determines how the area surrounding images smaller than the canvas's current DoD — itself set by the background image's resolution — gets treated.

Canvas: Whatever lies beyond the frame takes on the canvas's present color/opacity. To alter that value, slot a Set Canvas Color node between the image feeding the foreground input and that foreground input itself, then use Set Canvas Color to settle on a color and/or transparency setting for filling the canvas. Wrap: Builds a “video wall” look by tiling the foreground image into a grid. Duplicate: Takes the outermost pixels along the foreground image's edge and repeats them outward — up, down, left, and right from each side — until they reach the edge of the DoD. Mirror: Like duplicate, except that every alternate copy of the foreground image is flipped and flopped, yielding a repeating pattern.

- Invert Transform: Turning on the Invert Transform control reverses any position, rotation, or scaling transformation. It comes in handy when you tie the merge to a tracker's position for match moving.
- Flatten Transform: The Flatten Transform option stops this node from concatenating its transformation with the nodes that come after it. The node can still concatenate transforms arriving from its input, yet it won't concatenate its own transformation with the node sitting at its output.
- Reference Size: The controls beneath Reference Size leave the image itself alone. What they let you steer instead is how Fusion expresses the location of the Merge node's center. As a rule, coordinates run as values from 0 to 1, where 1 equals a span matching the image's full width or height. That arrangement delivers resolution independence, since you can resize the image without ever touching the center's value.

A drawback of this scheme is that it makes pixel-precise edits to an image trickier. Picture, by way of illustration, an image measuring 100 x 100 pixels. Shifting the foreground element's center 5 pixels rightward would mean taking the merge center's X value from 0.5, 0.5 to 0.55, 0.5. The shift has to be 0.05 because 5/100 = 0.05. Enter the background image's dimensions into the Reference Size controls and the center control values are displayed differently, now reporting genuine pixel positions in their X and Y fields. Carrying the example further, set both width and height to 100 and the center reads 50, 50; nudging it 5 pixels to the right then means typing 55, 50. Under the hood the Merge node keeps storing this as a number from 0 to 1, so querying the center control's value through scripting, or publishing that control for other nodes, would hand back the original normalized figure. The shift only shows in the value displayed for merge center within the node control. Use Frame Format Settings: Choosing this makes the merge adopt the composition's present frame format settings to derive the reference width and reference height values. Width and Height: Dial these sliders to the image's width and height to alter how Fusion presents the Merge node's center control values.

### Channels Tab

### Merge node Channels tab

Controls on the Channels tab give the Merge node the means to draw on the Z-channels carried inside each image, settling what sits in front and what sits behind throughout a Merge operation. The controls below are how you tailor the result.

- Perform Depth Merge: Defaults to off. Switch it on and both images' Z-channel drives the composite order. Alpha channels still spell out transparency, but it's the Z-Depth channel values that fix how image elements stack front to back. Should either image lack a Z-channel, this checkbox's state is disregarded and no depth compositing happens. Where Z-Depth channels do exist, clearing this checkbox keeps them out of the operation.
- Foreground Z-Offset: This slider applies an offset to the foreground image's Z value. Hit the Pick button to lift a value from a displayed image's Z-channel, or key one in through the slider or input boxes. Raise the value and the foreground image's Z-channel shifts farther off along the Z-axis; lower it and the foreground draws nearer.
- Subtractive/Additive: During Z-compositing, background image pixels can end up composited in the output's foreground whenever that pixel's Z-buffer sits closer than the foreground pixel's Z. This slider decides whether such pixels merge in an Additive or a Subtractive mode, working precisely like its counterpart slider over in the Merge tab. Merged atop a background of another color, the original background still peeks through the semitransparent regions. An Additive merge holds the image's transparencies but folds their values into the background.

### Common Controls

Settings Tab The Inspector's Settings tab is likewise mirrored across both the Dissolve and Merge nodes. Those shared controls get their description in the “The Common Controls” section coming up.

### MultiMerge [MMrg]

### The MultiMerge node

### MultiMerge Node Introduction

With the MultiMerge node you can bring several sources together inside a layer-based structure. Where the standard Merge tool takes just one foreground input, MultiMerge spins up a fresh consecutive foreground input every time you drag a new source onto the tool. Those inputs join the Layer List in the Inspector, shown as a stack running top to bottom in a hierarchy. The layers sit so that the one nearest the foreground rides at the list's top and the one nearest the background rests at the bottom. Every layer carries its own separate, independent set of Merge controls (refer to the Merge node above) that turn up in the Inspector's lower half, so you can tune position, size, composite modes, and the rest for each source input on its own. As a composite grows more involved, you can wind up with heaps of standard Merge nodes strewn across the node tree. MultiMerge serves to gather those Merge nodes into one, acting as an organizing aid while letting you direct the order of operations in a layer-based setting rather than a node-based one. In principle you could composite and arrange hundreds of distinct layers with a single MultiMerge node on your node tree.

A sky replacement composite that once took three separate Merge nodes (previous page) gives way to a lone Multi Merge node (above). A faint glow marks the pipe of whichever layer is currently selected in the Layer List (Actors node to MultiMerge node).

### Inputs

These image inputs come on the MultiMerge node: Background: The orange background input takes the first of the images you mean to composite together, and you ought to wire up the background input before the foreground input. Foreground: The foreground inputs take each later image to be composited, usually a foreground subject meant to sit ahead of the background. Running a pipe from a new source onto the MultiMerge node spontaneously adds a fresh foreground input on the node plus a fresh layer in the Layer List. All foreground inputs carry a white color. Effect Mask: (Optional) The effect mask input lets you confine merging to a portion of the output image — wherever the mask reads white (where the foreground image appears in front of the background) — and lets the background image alone show through wherever the mask reads black.

### Basic Node Setup

A MultiMerge node is usually wired up like this: several input images feeding the foreground inputs, one background input, and the output running on to the composition's next node. The effect mask input goes unused in this example, since that's the more common arrangement.

### A typical MultiMerge node structure in DaVinci Resolve

### Resolution Handling

Although images of any resolution may be wired into the MultiMerge node's background and foreground inputs, it's whichever image feeds the background input that sets the output's resolution.

### Inspector

The MultiMerge node's Layer List. Layer 4's input has been unplugged (its name struck through) and switched off (unchecked). The Luma Key layer is mid-rename, the Sky layer is switched off (unchecked), and the Actors layer is switched on (checked).

### Layer List

Every foreground input you connect to the MultiMerge node spawns a new layer, added in turn within the Layer List. That list is ordered hierarchically from top to bottom, with the upper layers sitting above the ones beneath them in the image. There are a few ways to shape this layer arrangement. To Select a Layer: Click a layer in the Layer List to make it active. The active layer's Merge controls show up at the foot of the Inspector, and the pipe running to that layer's input on the MultiMerge node picks up a faint glow in the node tree. Hold the Shift key as you click to grab a range of layers, or the Command key to grab several non-adjacent ones. A right-click on any layer brings up a contextual menu holding these options:

- Go To Source: Picks out the tool feeding that layer's input on the MultiMerge node and surfaces the tool's parameters in the Inspector.
- Split Here: Spins up another connected MultiMerge node on its own and divides the current layers across the two. The layer chosen for the split, together with every layer above it, peels off into a new MultiMerge node, while the original MultiMerge node ties into the background input of that new MultiMerge node.
- Rename Layer X: Brings up a dialog box for relabeling the chosen layer.
- Rename Layer to Match Source: Swaps the layer's name to match the name of the

tool it's connected to.

- Set Layer X to Default: Returns the layer's merge settings below to their default state.
- Delete Layer: Removes the layer outright from the Layer List and unplugs the pipe from the

original tool, though the original tool itself stays.

To Move a Layer up or down the List: Grab the Layer name and drag it higher or lower in the list. A grey line marks the spot where the layer will come to rest. Release the mouse button to commit the move. To Rename a Layer: Out of the box, each layer borrows its name from the input tool. For a more meaningful Layer's name, double-click that name and type a replacement into the text field. Alternatively, right-click a Layer's name and choose Rename Layer off the contextual menu. To Disable/Enable a Layer: Ticking or clearing the box beside the Layer's name switches that layer on or off accordingly. Switching a layer off mutes that input's share of the MultiMerge's overall composite without removing it. To Replace a Layer: By design, unplugging the pipe from the MultiMerge's input leaves the layer sitting in its spot within the Layer List, but with a strike-through on its name to signal that nothing's hooked up at the moment. This lets you rapidly cycle and try out a number of input sources (clips, graphics, and so on) into the same layer without forever reshuffling your Layer List order. Keyframing the Layer List: The Layer List can itself be keyframed by way of the standard keyframe controls off to the list's right. The parameters open to keyframing are layer order along with layer enable and disable.

### Merge Controls

Every layer owns a separate, independent set of Merge controls that surface here once the layer is selected. For a thorough rundown of how the Merge controls behave, turn to this chapter's earlier section headed Merge [Mrg].

### The Common Controls

A handful of the same Inspector controls appear on the Merge, MultiMerge, and Dissolve nodes alike. What this section lays out are the controls those two nodes hold in common.

### Inspector

### Merge Setting Inspector

### Settings Tab

Both tools in the Composite category carry the Settings tab within the Inspector. Even third-party color-type plugin tools sport the Settings controls. They stay uniform and behave identically across tools, though a tool here and there throws in one or two of its own options, which are likewise covered here. Blend The Blend control mixes between the tool's original image input and its final altered output image. With the blend value at 0.0, the outgoing image matches the incoming one exactly. As a rule, that prompts the tool to bypass processing altogether, copying the input straight through to the output.

Process When Blend Is 0.0 The tool keeps processing even with the input value at zero. That can help when this node's processing is scripted to set off another task while the node's value sits at 0.0. Red/Green/Blue/Alpha Channel Selector These four buttons pin the tool's effect to chosen color channels. The filter usually kicks in after the tool has run. Deselect the red button on a blur tool, say, and the blur applies to the image first, after which the original input's red channel is copied back over the result's red channel. A few exceptions exist, like tools where clearing these channels makes the tool skip that channel's processing outright. Such tools generally carry a matching set of RGBA buttons on the tool's Controls tab, and in that case the Settings and Controls tab buttons are one and the same. Apply Mask Inverted Switching on the Apply Mask Inverted option flips the tool's entire mask channel. That mask channel is the pooled result of every mask wired into or produced within a node. Multiply by Mask Choosing this option multiplies the masked image's RGB values by the mask channel's values, turning every image pixel outside the mask (that is, set to 0) black/transparent. Use Object/Use Material (Checkboxes) Certain 3D software can render to file formats carrying extra channels. The EXR file format notably supports Object and Material ID channels, which can serve as a mask for the effect. These checkboxes settle whether those channels get used when present, and the precise Material ID or Object ID affected is set through the next batch of controls. Correct Edges This checkbox shows up only with the Use Object or Use Material checkboxes ticked. It flips the approach taken to overlapping object edges in a multi-object image. Switched on, it draws on the Coverage and Background Color channels to separate out and sharpen the effect around an object's edge. Left off (or with no Coverage or Background Color channels on hand), aliasing can creep in along the mask's edge. For more on the Coverage and Background Color channels, the DaVinci Resolve Reference Manual treats them under Chapter 78, “Understanding Image Channels,” while the Fusion Reference Manual handles them at Chapter 18. Object ID/Material ID (Sliders) These sliders choose which ID builds a mask from an image's object or material channels. Work the Sample button much as you would the Color Picker, lifting IDs straight off the image shown in the view. The image or sequence has to have been rendered from a 3D software package that included those channels.

Use GPU The Use GPU menu offers three settings. Choosing Disable shuts off hardware-accelerated rendering on your computer's graphics card. Enabled puts that hardware to work. Auto taps a capable GPU whenever one is present and drops back to software rendering when none is Motion Blur

- Motion Blur: This flips the rendering of Motion Blur on the tool on or off. Switched on, the tool's predicted motion drives the motion blur that the virtual camera's shutter would create. Switched off, no motion blur appears.
- Quality: Quality fixes how many samples build the blur. Set Quality to 2 and Fusion lays down two samples on each side of an object's true motion. Bigger values smooth the result while lengthening the render time.
- Shutter Angle: Shutter Angle governs the virtual shutter's angle behind the motion blur effect. Wider angles deepen the blur but stretch the render times. A value of 360 amounts to leaving the shutter open across one full frame exposure, and you can go higher still for intriguing effects.
- Center Bias: Center Bias shifts where the motion blur's center falls, which opens the door to motion trail effects.
- Sample Spread: Tweaking this control alters how much weight each sample carries, which bears on the samples' brightness.

### Layers

- Process Layers: Choose the layer whose effects you want processed from:
- Default Layer (default) - Applies the effect to the base/unnamed layer alone, sparing the others.
- All Layers - Applies the effect across every layer on offer.
- Custom - Lets you pick among the other available layers to apply the effect to, leaving the rest untouched.
- Input Layer: The Input Layer enumerates all layers coming from the default input's upstream node. Whatever layer you select can serve the current tool or, on its own, somewhere further down the node tree.
- Effect Mask Layer: When the tool carries an Effect Mask input, this control enumerates the available layers able to supply mattes for the tool.

Comments You attach notes to a tool through the Comments field. Click into the field and type your text. Once a note rides on a tool, a small red square shows at the node's lower left corner while the full tile is on view; should nodes be collapsed instead, a small text bubble icon turns up over on the right. To read the note in the node editor, rest the mouse pointer on the node and the tooltip appears. Scripts From the Settings tab, three Scripting fields sit on every Fusion tool. Each holds an edit box where you place scripts that run as the tool renders. For deeper detail on scripting nodes, turn to the Fusion scripting documentation.
