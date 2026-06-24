# Resolve Fx Texture

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Resolve FX Texture

This family of plugins exists to layer texture onto images, recreating both true-to-life and more stylized looks.

### Analog Damage (Studio Version Only)

Sitting in the Texture category, this plugin mimics the assorted ways a signal breaks down through analog broadcast and tape recording, so Analog Damage is your tool for conjuring all sorts of “old TV” or “junky videotape” treatments. Its Preset pop-up menu offers a selection of ready-made looks, and a Custom option opens the door to rolling your own.

(Left) The original image, (Right) The image with Analog Damage applied

- Preset: Lets you layer onto your footage the very video damage types DaVinci Resolve was originally built to clean up.
- It has the following categories of parameters:
- Telecine Source: Settings covering lens vignetting plus automatic leftward and rightward shutter weave.

Vignetting: Dims the frame toward its edges, mimicking a weak telecine lamp. Vignette Aspect: Tunes how wide the vignette spreads. Shutter Weave: Mimics the faint drift of the picture as a film reel feeds through a telecine.

- Broadcast Signal: Options governing adjustable noise, loss of detail, signal ghosting, and chroma misalignment. Noise Scale: Sets how fine-grained the noise becomes. Signal Noise: Sets how much static rides on the Luma signal. Chroma Noise: Sets how much static rides on the Chroma signal. Detail Loss: Sets how much detail drops out during “transmission.” Chroma Detail Loss: Sets how much chroma detail drops out during “transmission.” Ghosting: Recreates the ghost image a reflected signal produces. Ghost Offset: Lets you shift the ghost image's placement. Chroma Misalignment: Sets how far the color signal sits out of register with the brightness.
- Color Dials: Color tweaks specific to a television signal. Brightness: Stands in for a consumer set's brightness knob. Contrast: Stands in for a consumer set's contrast knob. Color: Stands in for a consumer set's color (saturation) knob. Tint: Stands in for a consumer set's tint knob.
- Scan: Controls that recreate faults in television scanning. Image Aspect: Reshapes the frame, padding or trimming it where required. H-Shift: Lets you roll the image horizontally.

V-Shift: Lets you scroll the picture up and down. V-Hold/Latch: V-Hold works together with the V-Hold Latch parameter so that a little keyframing can trigger animated vertical rolls that “bounce” convincingly over time the way a broadcast would. Overscan: Lets you set how much of the frame gets trimmed for on-screen display. V-Scale: Lets you tune the image's vertical scaling. Vertical Blanking: Lets you dictate the Vertical Blanking Interval size.

- Scan lines: Recreate adjustable television scan lines able to reproduce moire and color artifacts. Line Sharpness: Lets you dial in how crisp the scan lines look. Line Frequency: Lets you set how many scan lines fill the image. Colored Lines: Tick this box to give the scan lines colored outlines.
- TV Construction: Controls that recreate CRT troubles with phosphor brightness, tint, and defocus, plus the means to apply an adjustable curved border and warped screen curvature. Phosphor Brightness: Lets you tune the front screen's brightness even while the tv is supposedly “off.” Phosphor Tint: Lets you tune the front screen's color even while the tv is supposedly “off.” Defocus: Lets you tune how much detail the screen swallows. Screen Curvature: Lets you tune how rounded the picture tube appears. Edge Mask: Tick this box to wrap a black mask around the screen's edge. Edges Transparent: Tick this box to render the screen edges transparent for compositing. Mask Curvature: Lets you tune the black mask's shape. Mask Aspect: Lets you tune the aspect ratio of the black mask.
- VHS: Lets you bring in an adjustable “Restless Foot” that recreates recorded-tape artifacts. Restless Foot Height: Lets you decide how far the restless foot creeps up from the screen's bottom. Restless Foot Offset: Lets you pick the direction and degree of the restless foot's distortion. Restless Foot Jitter: Lets you tune how much the restless foot shakes from frame to frame.

TIP: Running the Analog Damage plugin over on the Fusion page means you can hook up Modifiers that drive automatic animation (Perturb among them) on the various parameters, a fast and simple way to generate self-animating video damage effects.

### Detail Recovery (Studio Version Only)

Detail Recovery is a no-frills, practical effect: it pulls image detail off the second input and grafts it onto the picture arriving at the first input. That way you can put detail back, piece by piece, into an image that had it stripped away. Owing to its mechanics, this effect is meant for the Color page. Putting Detail Recovery to work requires that you drop it into the node tree as a Resolve FX node, dragging it straight out of the Open FX library so it stands as its own node, which is what surfaces both of the RGB inputs that then appear on it. Out of the box, the first RGB input takes the picture you intend to enrich, while the second RGB input takes the picture you're harvesting detail from. For the walkthrough below, Node 1 holds the base grade and Node 2 holds a grade whose highlights are deliberately blown out for a stylistic look. The Detail Recovery node is then introduced to feed targeted image detail from Node 1 back into the output of Node 2.

Configuring Detail Recovery so that image detail off Node 1 feeds into the picture arriving from Node 2 Set against the picture in Node 2, the outcome remains severely exposed yet now carries hints of fine image detail, so it reads as less clipped.

(Left) The frame whose highlights are crushed hard, (Right) The frame after high-frequency detail is restored The parameters Detail Recovery exposes are as follows.

### Detail Recovery

- Transfer Direction: A drop-down where you pick which input supplies the detail and which input that detail gets merged into.

### Details Extraction

- Frequency Cutoff: A slider for setting how much detail to pull out for recovery. Lower settings single out the finest details, while higher ones progressively take in larger ones.
- Detail/Edge Balance: This lets you decide whether to recover every detail or only the more pronounced edges.
- Strength: A slider that boosts or dampens whatever detail gets pulled for recovery.
- Detail Mix: Set to 1.000, this slider mixes the harvested detail into the picture you're adding

it to so the two layers fuse. Set to 0.000, the harvested detail overwrites whatever overlapping pixels live in the picture you're adding it to. The slider lets you land on whichever blend suits your needs.

- Preview Detail checkbox: Switch this checkbox on and you can watch the detail being harvested via the Frequency Cutoff and Strength sliders.

### Fast Noise

Fast Noise generates noise patterns by computer that you can composite over a clip, or use to warp it, for an assortment of effects like smoke, haze, or rippling water.

(Top) The unaltered frame; (Bottom) that same frame after Fast Noise’s Smoke preset, with the position and rotation onscreen controls on display.

### Appearance

Controls that govern which noise pattern gets produced. Every parameter can be keyframed to vary the noise pattern across time.

- Preset: Pick from several typical noise-pattern scenarios: Mist, Smoke, Water Surface, River, and Heat Haze. Default gives the baseline noise pattern, and Custom switches itself on the moment you alter any parameter below.
- Scale: How large the noise pattern is.
- H/V Ratio: Governs the horizontal-to-vertical spread ratio.
- Detail Level: How many tiers of fine detail get produced.
- Detail Balance: Weights the various detail scales against each other. The slider lets you favor

either bolder large detail or bolder fine detail. A value of 0.000 strips out fine detail completely.

- Evolution: Shifts the noise pattern by degrees. This slider drives the noise pattern's “progress”

through time instead of merely tweaking its present form.

### Adjustment

Controls for tuning the noise pattern's parameters after it has been produced. They come in especially handy for reworking the noise pattern's Alpha channel ahead of compositing. Every parameter can be keyframed to vary the noise pattern across time.

- Brightness: Raises or lowers the noise pattern's gain.
- Contrast: Pushing this slider rightward brightens the light zones and deepens the dark zones within the

noise pattern, lifting the contrast. Pulling it leftward flattens the contrast.

- Saturation: This slider sets where the noise pattern falls between grayscale and full color.

A value of 0.000 is wholly grayscale, whereas 1.000 is fully saturated color.

- Color Tint: Establishes the effect's overall hue.
- Invert Dark Regions: Tick this box to flip the dark regions to white and deepen the edges within

the noise pattern.

- Invert Pattern: Tick this box to flip the noise's color.
- Allow Negative Values: Tick this box to feed negative values into the Output section further down.

### Position

Controls that set the noise pattern's center point and orientation.

- Position X/Y: Where the noise pattern's center sits.
- Rotation: Spins the noise pattern about its center.
- Position Reference: Dictates how the effect is placed when a clip gets resized or

repositioned within the Timeline. Sizing and FX Tracker: Here the noise pattern tracks along with Sizing and FX Tracker moves made on the Color page. Suppose you used the FX Tracker to follow a camera pan: the noise pattern would travel with that pan instead of holding still as the shot slid beneath it. Keyframed Positions: You adjust the noise pattern's placement the usual way, through keyframes. The position and rotation controls are also adjustable right in the Viewer once you choose Open FX Overlay mode from the drop-down at the Viewer's lower left. Drag the star inside the Viewer to set the X/Y position; drag the circle either clockwise or counterclockwise to set the rotation.

### Auto-Animation

This set of controls lets you shape how the noise pattern animates.

- Velocity X/Y: How far each frame is advanced automatically away from the starting position. Keyframing these controls steers the noise pattern's direction without touching its real X/Y position, which lets you imitate behavior like smoke shifting course in a breeze.
- Seethe: Dictates how far each frame is automatically evolved beyond the starting Evolution value.
- Randomize Start Frame: Pins the skipping cycle to the present frame, so you can reuse a

favorite effect across several clips without every copy turning out identical.

- Start Frame: Lets you name the reference frame for the skip pattern, giving you a handle on the

run of noise produced should you ever need to line it up with the same noise pattern on a different clip. That frame is the one that repeats.

### Output

This set of controls lets you decide how the noise pattern's output is handled.

- Preview Noise: Tick this box to view the noise pattern on its own.
- Output: Decide how the noise pattern is put to use.

Composite Onto Clip: The noise pattern gets laid over or blended into the video clip. Composite Type: Picks the composite mode for the noise pattern. Put Into Alpha Channel: The noise drops into the node's Alpha channel, letting you press the noise pattern into service for compositing. Bear in mind you'll also have to right click the node and pick “Use OFX Alpha” for this setting to take effect. As an alternative, drag the Fast Noise effect straight into the Node Graph as an FX Node rather than onto a corrector node, and the Alpha becomes available with no extra setup. Use to Warp Image: The noise pattern serves to distort the image. Input Alpha: Governs how the incoming Alpha channel is treated.

- Limits Warping Effect: Pens the warp into specific zones spelled out by the Alpha channel, for instance when you want a water ripple or heat shimmer confined to just part of the clip.
- Gets Warped as Well: The warp acts on the Alpha channel alongside the RGB channels, for instance when warping a logo that has a transparent backdrop.

### JPEG Damage

Recreates the slight or severe artifacts that crop up under JPEG compression; handy for faking compression damage.

- Quality: Lets you drop the image's bit depth.
- Resolution: Lets you enlarge the macroblocking artifacts that show up.
- Block Aspect Ratio: Lets you push the macroblocks toward squarer or more rectangular shapes.
- Frequency Scale: Crisps up the effect.
- Scale Component: Lets you anchor this effect on All Frequencies, the X-Frequency, or the

Y-Frequency.

### Texture Pop (Studio Version Only)

Texture Pop is a richer, more adaptable take on the Midtone Detail control that lives in the Primaries and HDR palette. With this effect's controls you can strip texture away or push it harder. It offers two operating modes that set how fine-grained a result is within reach.

- Within Simple mode, you get to dial in stronger doses of the Midtone Detail effect from the Primaries and HDR palette. One Details slider softens or sharpens the image's midtone detail across a wider range, and a Strength slider then pushes the effect further or eases it back.
- Within Advanced mode, you can finely shape the softness or sharpness of high-, medium-, and low-frequency image detail through seven separate “details” sliders, named Rough, Coarse, Medium, Small, Fine, and Tiny. That lets you treat several frequencies of image detail distinctly, softening Fine detail, say, while boosting Medium detail. The Strength slider raises or lowers the combined effect of all the sliders together.

Whichever mode you're in, the Details/Range sliders sit at a default of 0.000, leaving the image untouched. That's the setting to keep when you want the image's original detail quality preserved. Their span runs from -1.000 (the most softening) to +1.000 (the most sharpening). Beyond that, a group of Tonal Range controls (covered further on) lets you decide how strongly this effect lands on the image's Shadows, Midtones, and Highlights, handing you even tighter say over which areas of the picture get softened and/or sharpened.

### Understanding Advanced Mode

Advanced mode is where this effect gets genuinely interesting. To get a feel for what it does, drop every Details slider to -1.000, then bring each one up on its own to watch what sort of image detail comes back, and eventually gets boosted, as you carry each slider past 0.000. In the image below, every Details slider sits at -1, the heaviest smoothing each one allows, yielding an image stripped nearly bare of detail. In that example, a person plus the mechanical workings of a helicopter shot are smoothed out by parking each detail slider at -1.000. Notice that both results keep the broad sweep of color and contrast marking out each color region, but past the high-contrast edges every bit of textural detail has melted into a clean gradient.

(Left) A shot of a person rendered with every bit of detail smoothed off, (Right) A shot of machinery likewise smoothed flat of detail

Next, walking each Details slider back up to 0 or even +1 one at a time reveals precisely which kind of detail that slider governs. In the person example, the Tiny and Fine sliders touch nothing but the very smallest details, the hairs, lines, and skin pores. Over in the helicopter, you'll watch the small textures, tiny lines, and rivet details return.

(Left) That same shot of the person, now with the Tiny and Fine sliders lifted to feed gentle detail back in, (Right) The helicopter close-up after Tiny and Fine detail are restored to it Two sets of rules of thumb apply when you're considering the detail across a human face.

- Tiny, Fine, and Small controls govern an image's smallest details, the pores

(tiny), blemishes (fine), and wrinkles (small) typical of ordinary closeups. They also reach high-frequency edge detail such as individual strands of hair, foliage on a tree, or lettering on a printed page or a screen.

- Rough, Coarse, and Medium lean toward progressively smaller shadow contouring across faces, bodies, and objects.

Naturally, how granular a given type of image detail is comes down to whether the clip is a closeup or a long shot. With the camera nearer the subject you're adjusting, far finer details fall within reach. With the camera far off, even sizable details on the subject end up governed by the Tiny, Fine, and Small controls. So an adjustment you craft for a subject in a closeup will need reworking before it suits a long shot.

### Mode Controls

- Operating Mode: Lets you switch the plugin between its Simple and Advanced modes.
- Color Mode: Lets you switch between operating in RGB and in Luma/Chroma mode. Under RGB, one

shared set of parameters drives all three color channels together. Under Luma/Chroma mode, two separate control sets let you shape the luma and the chroma on their own.

- Output Mode: Lets you switch the output among the Final Result, Differences mode (which shows the effect diffed against the source image), and Difference Magnitude, which presents a high-contrast difference comparison.

### Details Controls

- Strength: Lets you drive the other Details sliders' effect harder or pull it back.
- Details: (Simple mode only) Softens or sharpens the image's midtone detail over a wider operating range.
- Rough/Coarse/Medium: (Advanced mode only) This trio of sliders acts on the image's progressively larger contours, seeming to work on its shadows and underlying structure.
- Small/Fine/Tiny: (Advanced mode only) This trio of sliders acts on the image's progressively smaller details and texture, reaching medium down to tiny details, lines, and specks.

### Tonal Range Controls

- Shadows: Lets you dial back the effect you've built up in the image's shadows, bounded by the Low Range parameter.
- Midtones: Lets you dial back the effect you've built up in the image's midtones, bounded by the Low and High Range parameters.
- Highlights: Lets you dial back the effect you've built up in the image's highlights, bounded by the High Range parameter.
- Low Range: Lets you pin the image value marking the handoff from Shadows to Midtones.
- High Range: Lets you pin the image value marking the handoff from Midtones

to Highlights.
