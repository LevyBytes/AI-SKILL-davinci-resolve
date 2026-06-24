# Resolve Fx Stylize (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Color Space: Tunes the color space of the sky coming in. Falls back to timeline settings by default.
- Gamma: Tunes the gamma of the sky coming in. Falls back to timeline settings by default.
- Detail: Tunes the midtone detail of the sky coming in.
- Brightness: Tunes the brightness of the sky coming in.
- Saturation: Tunes the saturation of the sky coming in.
- Temperature: Tunes the color temperature of the sky coming in.
- Tint: Tunes the tint of the sky coming in.
- Opacity: Tunes the opacity of the sky coming in, for when you'd like to mix it with the sky drawn from the

original footage.

The identical car shot, now with more dramatic storm footage standing in as the replacement sky and tuned through the Source Sky Appearance tools.

### Artificial Sky

With these options you can build artificial sky elements that look believable. They fall under three headings: Sky, Cloud, and Hotspot (a stand-in for the sun or moon). Out of the box, each element's opacity sits at zero (off). To reveal any of them, raise the opacity for that category above zero.

- Preview Artificial Sky: Ticking this box displays the Artificial Sky categories on their own, with no compositing against the foreground plate.
- Sky Opacity: Tunes the sky's opacity. At zero it's fully off; at one it's wholly opaque. Anything between mixes the artificial sky with the source sky.
- Sky Color: Picks the sky's color.
- Horizon Color: Picks the color of the horizon haze that fades into the sky color.
- Horizon Softness: Sets how gently the horizon dissolves into the sky.
- Horizon Height: Sets how far up the frame the horizon climbs.
- Horizon Angle: Sets the angle of the horizon.
- Cloud Opacity: Tunes how opaque the clouds are against the sky. Lower settings fold

the clouds in further; higher ones make them pop.

- Cloud Color: Picks the clouds' color.
- Cloud Scale: Sets the scale of the noise pattern that builds the clouds, which governs

how near the clouds sit to the foreground.

- Cloud Shape: Tunes the horizontal/vertical ratio of the clouds. Lower settings yield puffier

(cumulus) clouds, while higher ones stretch them out (cirrus).

- Cloud Tilt: Tunes the sky's angle against the ground, so it lines up with the

foreground angle.

- Cloud Detail: Sets the balance of coarse versus fine detail across the clouds.
- Cloud Fill: Tunes how much of the sky the clouds cover.
- Cloud Contrast: Tunes how much contrast the cloud cover holds against the sky.
- Cloud Time: Shifts the clouds' noise pattern. Pairing this control with keyframes

lets the cloud pattern evolve across time.

- Hotspot Brightness: Tunes how intense the hotspot is. At zero there's no hotspot. An on-screen control for this sits in the Viewer.
- Hotspot Color: Tunes the hotspot's color.
- Hotspot Position: Tunes where the hotspot sits. An on-screen control for this

resides in the Viewer.

- Hotspot Size: Tunes the hotspot's size.
- Hotspot Sharpness: Tunes how sharp the hotspot's edges read.

### Sky Position

With these tools you track the foreground clip's motion so the sky shifts convincingly along with whatever the camera does.

- Match Motion: Picks which tracking approach to apply. Keyframing Only: Lets you drive the sky's movement by hand, keyframing the position controls. Track Foreground: Runs a track automatically off the foreground elements within the composite. Track Original Sky: Runs a track automatically off the sky in the original clip. It works only where the sky already holds detail such as clouds. When your footage permits, this is the soundest, most dependable tracking approach. Use FX tracker: Ties into the track the FX tracker produced in the tracker controls.
- Adjust Size: Resizes the sky so it can span the range of motion the tracker laid out.
- Adjust Position: Lets you set the sky's X and Y positions by hand.
- Auto-Size for Motion: Examines the track and sets the sky's size and position on its own to

span the track's full reach.

- Flip Horizontal: Mirrors the sky across its horizontal axis.

### Sky Integration

These controls help you reconcile the qualities of the finished sky with the foreground footage.

- Preview Final Sky: Tick this box to see only the finished sky output, motion and any keyframed parameters included.
- Lens Distortion: Tune this to bend the sky so it matches the curve of the original camera lens.
- Lens Defocus: Tune this to soften the sky's focus so it mirrors the depth of field belonging to the

original lens.

- Exposure: Tunes the sky's overall brightness.
- Add Grain: A pared-down toolset for mimicking the grain patterns seen on

motion picture film. Tick this box to switch the grain pattern on or off. Grain: Sets how much grain goes into the sky. Size: Sets how large the sky's grain is. Softness: Sets how crisp each grain reads. Saturation: Lends color to the grain. 0 is monochromatic.

### Foreground Appearance

Switching these controls on makes an automatic effort to reshape the foreground's overall look, drawing on an analysis of the finished sky's parameters.

- Adjust Foreground: Tick this box to switch on the Foreground Appearance tools beneath it.
- Auto Adaptation: Chooses how the Foreground Appearance analysis is produced.

None: Nothing is set automatically. You're free to tune the parameters underneath by hand. Globally Applied: The color cast is derived from the visible sky and then laid across the foreground uniformly, with no brightness variation. Even so, that color cast refreshes on the fly should the sky shift over time. Match Horizon: The color cast is derived from the visible sky but leans toward the horizon, with its reach set by the Localization control. As a result, brighter or darker patches of sky push bright or dark shifts onto the foreground. As an instance, with a dark sky but a moon near the horizon, the foreground reads brighter around the moon than elsewhere. This too refreshes on the fly over time.

- Adaptation Amount: Lets you pick how much adaptive color adjustment is applied.
- Localization (Match Horizon only): Lets you set how far or near the color

cast extends out from the horizon.

- Brightness: Tunes the foreground's gain or brightness.
- Saturation: Tunes the foreground's saturation.
- Temperature: Tunes the foreground's color temperature.
- Tint: Tunes the foreground's tint.

### Sky Replacement Workflow

What follows is a sample run-through for swapping the sky with one the artificial sky tools build. We begin from the original clip, whose sky we mean to swap out. The first move is simply to add a new color node.

The original shot whose sky we intend to swap.

After that the sky needs qualifying. For this particular clip, applying the Magic Mask (object) tool to the node isolates just the sky we mean to swap. The HSL qualifier, 3D qualifier, or even a power window would accomplish the same.

The sky isolated by way of the Magic Mask tool.

With the sky now isolated, we can drag the Sky Replacement effect out of the Effects Library and drop it onto the very node our Magic Mask already occupies.

The black region marks where our new sky will be built.

With both toolsets now live on the same node, the Magic Mask and the Sky Replacement parameters can be tuned together. That turns the full sky replacement into a single-node task.

Both the Magic Mask (or any qualifier) and the Sky Replacement tools can share one node.

The finished replacement sky, tracking right along with the camera's movement.

Through the Artificial Sky Controls we build a fresh, more compelling sky. Next, by way of the Sky position tools, we lock that sky to the original clip's camera movement. Last, layering in the Foreground Appearance toolset lets us blend the foreground and the sky together without a seam.

### Stylize (Studio Version Only)

This plugin lets you cast one of several painterly styles over an image, derived from analyses of various paintings, in a manner that holds up temporally for moving footage: the style strokes seem to settle onto individual objects in the scene and travel and flow with them in a steady way. It offers two controls:

- Styles: A pop-up menu where you pick an artistic style to lay over the image.
- Style Scale: A slider with which you set how large or small the applied art strokes

should be applied.

(Left) The original image; (Right) that same image after Style Transfer, set to Dance at a Style Scale of 4 TIP: There's more range in this plugin than you'd expect, provided you layer Style Transfer against the original image. Pull this off with a duplicate layer on the Edit page, or with two nodes — one carrying the Style Transfer effect, the other the original image — joined by a Merge node on the Fusion page or a Layer node on the Color page. With that in place, just blend the Style Transfer output against the original image through composite modes and opacity tweaks for richer compositing. Notably, the Luminosity composite mode lets you pull texture from the Style Transfer while keeping the original image's color, whereas the Saturation composite mode lets you pull color from the Style Transfer while keeping the original clip's texture.

### Tilt-Shift Blur (Studio Version Only)

This mimics depth-of-field effects by way of a graduated blur driven by a generated Z-depth map. Out of the box its settings produce a “miniaturization” illusion, in which the image looks tiny thanks to the top and bottom depth-of-field settings in play.

### Main Controls

These controls pick and govern the effect as a whole.

- Blur Type: Your two options here are Fast Blur and Lens Blur, with Lens Blur selected by default.
- Blur Strength: A slider with which you set how much blur is added.

### Lens Iris

The Lens Iris controls only come into play with Blur Type set to Lens Blur. They're a trimmed-down version of the controls found on the Lens Blur filter.

- Iris Shape: Lets you pick which kind of aperture to use, shaping the look of the bokeh effect. Aperture Shape choices run to Triangle, Square, Pentagon, Hexagon, Heptagon, or Octagon shaped aperture.
- Blade Curvature: (Only available with Real and Creative Apertures) Lets you soften the corners of the Aperture Shape you picked.
- Rotation: Sets the angle at which the shape sits.
- Anamorphism: Tunes this effect's aspect ratio so it lines up with the lens blur

that anamorphic lenses produce.

- Highlights: Tunes how the image's highlights play into the blur, dilating or eroding the

image to a greater or lesser degree according to how high Smooth Strength runs.

### Depth of Field

Further Depth of Field settings let you tune the depth map driving the depth-of-field effect.

- Map Source: Picks where the depth map comes from. Custom (default) lets you build the depth map within the effect. From Alpha In and From Second Input let you bring in depth maps built in other nodes.
- Center X, Center Y, and Angle: With these parameters you transform the depth map.
- Focus Sweep: Lets you home in on a region by “distance” for isolation. The depth

map's white areas take the blur, while its black areas are skipped.

- In Focus Range: Lets you widen or narrow the depth map's black center that marks out the

blurred region.

- Near Blur Range and Far Blur Range: A pair of parameters for separately tuning the falloff of the

depth map's white bottom and top.

- Depth Map Preview: A checkbox that lets you view the grayscale depth map straight away as you make

these tweaks. The white region gets blurred, while the black region stays untouched. TIP: For Depth of Field adjustments that read more convincingly, pair the Depth Map effect with the Tilt-Shift Blur effect. The depth map's output can flow straight into the Tilt-Shift Blur effect as a blur map: wire the Depth Map node's key output into the Tilt-Shift Blur node's key input, then choose “From Alpha In” from the Map Source dropdown within the effect's Depth of Field section. From there work the Focus Sweep to zero in on the area you mean to isolate. Should the result fall short of what you expect, try inverting the depth map.

### Watercolor (Studio Version Only)

A spin on the Abstraction filter, this one boils images down to simplified washes of gently blended color, in a thoroughly painterly manner.

- Channels: This pop-up menu lets you decide whether Luminance or RGB supplies the source for the smoothed color.
- Show Gradient: This checkbox lets you view the boundaries marking out each region of smooth color, keyed to the value you set on the Smoothness slider below.
- Smoothness: Governs how much detail survives in the end result. Low smoothness values keep more detail in the smoothed output, while higher ones produce broader pools of lower-detail yet smoother color.
