# Resolve Fx Stylize (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Resolve FX Stylize

Every plugin gathered in this category opens up a different route to making artistic alterations to the image.

### Abstraction (Studio Version Only)

A filter more capable than it looks, letting you produce a broad spread of cartoon-style renders by reducing an image into adjustable pools of like color, with outlines as an option.

### Main Controls

This effect is built on these controls.

- Pre Blur: Eases the image by blurring away unwanted detail before this filter does its work.
- Abstraction Strength and Iterate Abstraction: Acting together, these parameters then smooth the image and form pools of simplified color amid its detail. Abstraction Strength: Has to sit above 0 before the Iteration No. parameter does anything. A higher Abstraction Strength flattens image detail further still by averaging neighboring regions of color into one another. Iterate Abstraction: Cuts the small detail in the image down even more by "broadening" adjacent areas of similar color so they merge into one.

### Quantization Controls

By quantizing the bit depth used to stylize the image, these controls thin out the pools of color even more forcefully. What you get is a still sharper flattening within every region of color.

- Quantization: A checkbox switches this function on.
- Steps: Pushing this parameter up divides each region of color into a larger number of

separate regions.

- Softness: Softens the boundary between each level of color.

### Draw Edge Controls

Puts an edge around the regions of color this effect produces.

- Draw Edge: Turns edge drawing on.
- Edge Strength: Higher values yield thicker, more sharply defined edges.
- Edge Detection Threshold: Higher values confine edges to only the strongest edge detail in the picture.

### Blanking Fill

This plugin is built specifically to fill black frame blanking quickly with a stylized image drawn from the clip itself, making blanking less of a distraction for viewers of documentaries and news segments. The example that follows uses the Blanking Fill plugin to put image on the left and right of "pillarboxed" standard definition 4:3 video sitting inside a High Definition or Ultra High Definition 16:9 aspect ratio.

(Left) The standard definition image as shot, (Right) The same image once default Blanking Fill is applied A range of controls makes it easy to tailor this effect to whatever you need.

### Source

These controls reshape the clip in various ways, which in turn affects how that clip gets used to fill the blanking area.

- Zoom: Zooms the clip while holding it inside the native domain of definition. Handy for quickly trimming unwanted edge pixels so they stay hidden and do not feed the blanking fill.
- Crop Left and Right: Trims the image's left and right edges alike and grows the side area given over to blanking fill.
- Same Left/Right Sliders: On by default, it ties both sliders together so that moving one mirrors the move on the other.
- Crop Top and Bottom: Trims the image's top and bottom edges alike and grows the vertical area given over to blanking fill.
- Same Top/Bottom Sliders: On by default, it ties both sliders together so that moving one mirrors the move on the other.
- Center: When checked, it re-centers the image area should a sizing operation have shifted it off.

### Fill Extent

These controls set how the current copy of the image is stretched to cover the blanking area.

- Zoom Mode: Three options are available: Stretch to Timeline: Warps the image automatically so it stretches to fill the full frame. Keeps features within the blanking fill area aligned with where they sit in the original image. Zoom to Timeline: Zooms into the image automatically to fill the full frame. Leaves the clip looking "inset" from the blanking fill image. Manual: Brings up Expand and Aspect sliders so you can set by hand how much the image zooms and stretches to cover the blanking fill area.

Warp Top Layer: lets you pick, with onscreen controls, a strip along an image edge to stretch out and fill the frame's blanking. This mode gives you two sets of onscreen controls for shaping the result: one set of outer handles decides how far out the image's edges warp to fill whatever blanking exists, defaulting to the project frame size. A set of inner handles decides how much of the image gets stretched out, defaulting to the current title safe boundary. When you adjust these, choosing too narrow an edge produces a harsher warp and stretch, whereas choosing a wider edge to stretch reads more naturally but touches more of the frame.

- Expand: (Appears only when Zoom Mode is Manual) Zooms the image.
- Aspect: (Appears only when Zoom Mode is Manual) Stretches the image.

(Left) A 4:3 image dropped into a 16:9 timeline, which leaves black pillar boxing down the left and right sides, (Right) That image once Blanking Fill is set to Warp Top Layer, where the left and right edges stretch out to cover the blanking area

### Fill Appearance

These controls reshape how the image used to fill the blanking area looks.

- Blend Edges: Feathers the seam where the original image meets the blanking fill area.
- Blur Background: Sets how strongly or faintly the image filling the

blanking fill area is blurred.

- Fade Amount: Fades or tints the blanking fill area. At 0, no fade applies. At 1.000,

the blanking area becomes a solid color set by the Fade Color control.

- Fade Color: A combined color picker and eyedropper for choosing a color to

fade, tint, or fill the blanking fill area with.

### Drop Shadow

These controls add a drop shadow that "lifts" the foreground image off the blanking fill image.

- Shadow Strength: Sets how solid the drop shadow looks.
- Drop Angle: Sets the angle at which the drop shadow appears. At 0 the

drop shadow is centered.

- Drop Distance: Pushes the drop shadow out farther along the Drop Angle direction
- Blur: Softens the drop shadow.
- Color: Tints the drop shadow.

### Defocus Background

The Defocus Background effect blurs only an image's background and gives you a thorough toolset for imitating a shot taken with a shallow depth of field.

(Left) The starting image, its background busy and distracting. (Right) The Defocus Background effect blurring that background to calm the distraction and imitate a shallower depth of field On its own, the Defocus Background effect neither qualifies nor isolates the foreground subject. Before you can use Defocus Background, the foreground subject has to be isolated first with an effect or mask from another tool such as Magic Mask or a Power Window. Defocus Background can then go on the same node, or you can feed in the key output from an earlier node.

Wiring the Magic Mask's key output into the Defocus Background effect; for Defocus Background to function, it needs a key produced by another tool such as Magic Mask or a Power Window.

### Adjust Mask

These controls tune the mask that splits the sharply focused areas from the ones you want blurred.

- Mask Preview: Ticking this box brings up a black and white preview of your mask. The mask's white areas stay sharp, while its black areas are the ones blurred by the mask controls below. It is handy to keep visible as you refine the mask, then switch off to view the output of the Effects and Advanced options.
- Mask Invert: Ticking this box flips the mask, turning white areas black and the reverse.
- Mask Blur: This control sizes the Blur around the mask, letting you blend

the foreground and background together smoothly.

- Mask Contrast: This sets how hard the boundary is between the focused and blurred

regions of the matte.

- Adjust Pivot: This lets you place where the boundary falls between the focused and blurred regions

of the matte.

The Mask Preview option reveals where the defocus operations occur (the black areas).

### Effects

These controls establish the chief traits of the blurred area.

- Blur: This slider sets the size and degree of blur applied to the blurred area.
- Saturation: This slider sets how saturated the blurred area is. At 1.000 (default) saturation is full, while 0.000 renders the blurred areas monochrome.
- Colorize: This slider sets how much color tints the blurred areas. 0.000 is the default (no colorization).
- Color: This is the color picker for the Colorize operation above.

### Advanced Options

These controls let you tweak a few of the physical traits of the blurred area.

- Blur Type: This picks the blurring algorithm behind the blur. The options are Lens blur or Gaussian blur.
- Anamorphism (Lens Blur): This slider sets the blur's aspect ratio so it matches various lens types.
- Highlights (Lens Blur): Lets you set how the image's highlights act on the blur, dilating or eroding the image.

### Drop Shadow

Adds a basic drop shadow to any clip, shaping the shadow from that clip's native or generated alpha channel.

- Shadow Strength: Sets how solid the drop shadow looks.
- Drop Angle: Sets the angle at which the drop shadow appears. At 0 the drop

shadow is centered.

- Drop Distance: Pushes the drop shadow out farther along the Drop Angle direction
- Blur: Softens the drop shadow.
- Color: Tints the drop shadow.

### Edge Detect

An edge detection effect that picks out high-contrast boundaries, with options to control which edges become outlines. Once the edges are picked out, you can use this to sharpen soft clips or build a glow around a subject.

(Top) Original image, (Bottom) Image with default edge detect applied

### Main

- Mode: Lets you switch between RGB and Grayscale edges. RGB is the default. RGB locates edges from color and brightness together, whereas Grayscale finds edges from brightness changes alone.
- Edge color: (enabled only when Mode is Grayscale) Lets you colorize the edge outlines produced.

### Detection

These controls govern the strength and parameters of the edges found.

- Edge Width: Sets the thickness of the edges produced.
- Brightness: Sets how bright you want the edges.
- Gamma: Lays a gamma curve over the edge detection. A gamma under one lifts mid-strength edges in brightness, so more edges count as "detected," while a gamma over one darkens mid-strength edges, paring the edges down to all but the strongest found.
- Blur: Softens the final result so the edges blend in more naturally.
- Edge Mask Overlay: This checkbox lays the edges over the current frame so you can watch the filter's results. Clear this box to see only the detected edges.

### Filters

These controls set how the edges merge with the original frame.

- Preprocess: Lets you pick which de-noising filtering method to apply. The default is None. Filter: Cuts texture and strips out detail at the Scale parameter chosen below. Flatten: Smooths the image's even areas, keeping edges only where they part one flat region from another. The Strength parameter below sets how much of this smoothing happens.
- Half-Edges Only: Edges turn up between regions of differing brightness. With this option you choose which half of an edge is retained. By default it is None, so both halves of the edge remain. Keep Light Side: Edge keeps only the brighter half of the edge. Handy, say, for a light-wrap effect on a person's face, since only the lighter (face side) of the edge is kept, holding the added light-wrap brightness to the face alone and off the background. The HalfEdge Gain slider lets you push the edge brightness up further, apart from the main Brightness control. Keep Dark Side: Edge keeps only the darker half of the edge. Handy, say, for a glow effect on a person's face, since only the darker (background side) of the edge is kept, letting a halo form around the face but not over it. The Half-Edge Gain slider lets you push the edge brightness up further, apart from the main Brightness control.

### Advanced Options

These controls give you access to a few advanced parameters for the effect.

- Normalize Per Frame: Brings every incoming frame to a steady brightness level, so edges stay visible as the scene's brightness shifts or flickers. Turn this on when your scene's content keeps changing in brightness; otherwise leave the box clear.
- Clamp Brightness: Stops the output edges from going too bright when the content's contrast runs too high.

Suppose, for instance, you wanted a faint glow around the woman in the frame below using edge detect:

- Choose RGB Edges, tick the Edge Mask Overlay box, and set the Blur near .5 to fold them subtly into the frame.
- Then choose Flatten from the Preprocess control to even out the image's fine detail, so only the highlights off the woman's hat, arm, and phone get detected, along with the bright fluorescent light on the wall. Those are the bits we want to "glow." Set the Strength slider to taste.
- After that, choose "Keep Dark Side" in the Half-Edges Only box. This makes the glow spread outward from the edges rather than onto the woman and the light. Set the Half-Edge Gain slider to taste.

### The shot before the Edge effect

That same image carrying the Edge Detect effect alone, set with the parameters laid out above

The Edge Detect outcome; note how the glow spreads from the light and rings the woman's hat, arm, and phone.

### Emboss

An emboss effect carrying several options for producing different sorts of outline and emboss looks.

- Emboss Style: This pop-up lets you pick from Relief, Emboss Over, Sobel, and Laplacian kinds of embossing.
- Power: Sets how strong the emboss effect is.
- Angle: Sets the apparent angle from which the emboss effect is rendered.

### Channels

Three checkboxes let you opt to use the Red, Green, and Blue channels in building this effect.

### Mirrors

An effect for reflecting a portion of the image in whatever direction you choose. In its plainest form, it makes a split mirror effect like the one at the close of Prince's "When Doves Cry." In its most elaborate form, you can stack multiple reflections to spin up whirling Kaleidoscope patterns in the image.

### Main Controls

These controls set what sort of effect this plugin produces.

- Mirror Placement: Lets you pick among mirror effect types such as Individual (a plain reflection), Rosette, and Kaleidoscope.
- Reflect at Borders: Adds a further reflection of the image any time your reflection's angle and position would otherwise let offscreen black creep into the frame.

### Individual Controls

With Mirror Placement on Individual, six sets of Mirror parameters in a row let you stack multiple mirrored edges in various combinations; only one is on by default, but switching on more edges builds more intricate mirror effects. Every group of Mirror parameters carries the following parameters:

- Enable Mirror: Switches that mirror reflection on.
- X and Y Position: Places the center of the mirror split reflection.
- Angle: Sets the angle of the seam the reflection runs along.
- Flip: Swaps which side of the image gets reflected.

### Rosette Controls

With Mirror Placement on Rosette, one set of parameters generates an assortment of circular patterns.

- X and Y Position: Places the center of the circular rosette reflection.
- Angle: Sets the rosette pattern's orientation about its center.
- Wedge Width: Sets the thickness of the wedges ringing the outside of the rosette

pattern, and with it the number of wedges. Thicker wedges mean fewer reflections around the rosette pattern, while thinner wedges mean more reflections around it.

### Kaleidoscope Controls

With Mirror Placement on Kaleidoscope, one set of parameters lets you generate an assortment of kaleidoscopic images:

- X and Y Position: Places the center of the mirror split reflection.
- Center Size: Shrinks or grows the cells that make up the kaleidoscopic image.
- Angle: Sets the angle of the seam the reflection runs along.
- Number of Sides: Three sides yield a triangular pattern, while four sides yield a rectalinear

pattern lined up with the angle currently chosen.

### Pencil Sketch in DaVinci Resolve (Studio Version Only)

A plugin whose deeply adjustable controls make an image look hand-drawn.

- Color Sketch: Tick this box to switch between a color and a grayscale sketch.
- Sketch Stroke Controls: Parameters governing how thick the outlines are, the threshold at which

they show up around objects in the frame, and how long they run.

- Sketch Tone Controls: Parameters governing how many tonal levels appear in the rendered

result, plus contrast controls that steer how much of the image lands in shadows, mid-tones, and highlights.

- Sketch Texture Controls: Parameters that lay an adjustable stippled texture over the image, with a checkbox to auto animate it.

(Left) The original image, (Right) The image with Pencil Sketch applied

### Prism Blur

Mimics flat chromatic aberration together with a vignetted lens.

- X and Y Position: Let you move the point within the frame around which the chromatic aberration forms.
- Blur Strength: Blurs the primary image.
- Aberration Distance: Sets how far the aberration effect sits from the source image.
- Aberration Strength: Ramps up the zoom blur behind the chromatic aberration

to make it more pronounced.

- Vignette Size: Adds edge vignetting to the image; a setting of 0 clears the vignette,

and 1 is the largest vignette this filter allows.

- Vignette Sharpness: Sets the feathering of the vignette effect; lowering it

softens the edge, while raising it sharpens that edge yet never wholly removes its softness. The Vignette effect is built to fall off in a way that mimics how a lens shows vignetting.

### Scanlines

Mimics the scanlines of a television set, or any effect in which you want alternating lines darkening the image. With its assortment of parameters, this is a very flexible effect you can apply in many ways.

### Appearance

Let you tailor the kind of scanline effect you are after.

- Line Frequency: Sets how many or how few lines overlay the image; with fewer lines, they automatically widen as they spread evenly across the image.
- Line Sharpness: Blurs the boundary between each line, softening the effect.
- Line Angle: Rotates the lines to any angle; the default of 0 gives

horizontal lines.

- Line Width: Widens or narrows the blanking lines that hide the image

(black by default but tinted by the Color 2 parameter), thereby letting more or less image show through.

- Line Shift: Offsets the lines laid over the image. Animating Line Shift produces a rolling scanlines effect.

### Color

Lets you tint and shift the channels of the alternating scanlines this filter makes. Taken to extremes, it can spawn many other stylistic effects.

- Color 1 and Color 2: Color picker and eyedropper controls for tinting each alternating set of lines (the eyedroppers sample a color from the RGB image fed into the current node).
- Red, Green, and Blue Offset: Offsets the individual channels.
- Scanlines Only: Lets you view the scanlines on their own as you adjust them.

### Composite

Lets you decide how the scanlines effect composites against the original image.

- Scanlines Only: Outputs an image made up solely of the scanline pattern you built. Good for producing assorted patterned textures and mattes.
- Composite Type: Lets you pick which composite mode blends the scanline effect into the image.

### Sky Replacement

Swapping a dull, washed-out sky for a livelier one, or matching skies captured on separate days, are routine colorist jobs that the Sky Replacement effect makes more efficient. Choosing Sky Replacement over conventional compositing methods gives you a tight, purpose-built toolset that lets you:

- Match the foreground dynamically to the sky's brightness and color cast.
- Use Tracking options so the sky travels along with the clip's camera movement.
- Add believable computer generated sky elements, such as sky color, horizon haze, clouds,

and light sources.

(Left) The bland sky as shot, (Right) The same image carrying a fresh, better looking sky.

### Selecting the Sky to be Replaced

Worth noting is that the Sky Replacement effect performs no sky selection on its own; instead it accepts that selection from other tools and concentrates on blending it seamlessly into either a background plate of a different sky or its own artificial sky generator. Keeping the sky selection apart from the replacement tools is a deliberate choice, since qualifying a sky is usually easy while landing a clean mask at the horizon is not. That arrangement lets the colorist reach for the right qualifier (HSL, Window, Magic Mask, etc.) for a given scene and then hand it off to the Sky Replacement effect. A further upside is that the Sky Replacement effect can live on the same node as your qualifier, so you select and replace the sky within a single node and update both tools together as you go. To pick the sky to be replaced and feed it to the Sky Replacement FX: 1 Within a color node, reach for any Qualifier (Power Window, HSL, 3D, Magic Mask, etc.) and key the sky and horizon cleanly. 2 Next, drag the Sky Replacement effect out of the Effects Library and drop it on that same node. 3 Or build a new color node, run the alpha output of the earlier node (blue square) into the new node's alpha input (blue triangle), and drag the Sky replacement effect from the Effects Library onto the new node.

### Selecting the Replacement Sky

With your original sky qualified, you face two choices for what replaces it: an artificially generated sky (built in the Sky Replacement Parameters below), or fresh footage of a previously shot sky serving as a background plate. To wire a sky background plate into the Sky Replacement FX: 1 Inside a color node, qualify the sky, then add the Sky Replacement FX. 2 Right-click the node carrying the Sky Replacement FX and choose Add OFX Input from the drop‑down menu. An extra color and alpha input show up on the node. 3 Drag the sky background plate clip out of the Media Pool into the Node tree, creating a new external matte from that clip. 4 Off the external matte, hang a serial node to form a new color node, letting you reposition and grade the sky background plate as needed. 5 Wire the new color node's color output (green square) into the Sky Replacement color input (the lower green triangle on the node). The background plate's video now drives the sky replacement.

The node tree illustrating the way to bring your own sky background plate footage into the Sky Replacement effect.

### Sky Mask Adjustments

These options let you make final tweaks to the source mask coming from whichever qualifier you used.

- Preview Mask: Tick this box to view the mask as a black and white matte; white marks where the new sky shows through.
- Shift Edge: Moves the mask boundary toward or away from the horizon.
- Refine: Fits the mask boundary to the image edges.
- Black Level: Sets the mask's transparency level.
- White Level: Sets the mask's opacity level.

### Source Sky Appearance

These tools tailor the look of the new incoming sky. They do nothing to the artificial sky and act only on a video clip used as a sky background plate.
