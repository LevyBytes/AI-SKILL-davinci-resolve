# Resolve Fx Light (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Softness: Blurs that element. Bristle Density: (Corona Only) Changes how many optical bristles show up and how they're laid out. Drop the value and fewer bristles appear; raise it and more turn up. Shifting this parameter's value also relocates the bristles, so a single control governs both their spread and their count. Bristle Scale: (Corona only) Changes how thick the bristles that appear are. Lower values yield thicker bristles, while higher values yield thinner bristles bunched more tightly. Ringing: (All types but Bubble) Recreates a diffraction-artifact pattern. Raising the value adds more rings or streaks to the element. Chromatic shift: Recreates chromatic aberration. Eclipse Position: Recreates the spot where a Ghost Element loses its outer side (away from the center) or its inner side (toward the center) because the light has run off the edge of a lens element or been blocked by part of the tube housing. In practice, it sets which side of the Ghost Element responds to the remaining Eclipse parameters—size, softness, and chromatic shift. Tuning it produces semi-circular ghost shapes of various sorts. At 0, no eclipse occurs. With positive values the eclipse begins inside the frame and pushes outward; with negative values it begins outside the frame and pushes inward. Eclipse Size: Sets how large the eclipse region is for that flare element. The higher the value, the more of the flare element gets eclipsed. Eclipse Softness: Sets how soft the boundary is between the eclipsed and non-eclipsed regions. Eclipse Chromatic shift: Produces a chromatic aberration effect along the edge of the eclipsed region. At 0, no chromatic shift happens. As values climb positive, the shift heads toward blue. Going negative, the shift heads toward red. Repeat: Uses this element to generate many copies governed by the two parameters that follow. Repeat Position Seed and Repeat Size Seed: Across their range, these parameters pseudo-randomly rearrange where the repeated elements sit.

### Lens Reflections (Studio Version Only)

Sitting under the ResolveFX Light category, Lens Reflections recreates bright highlights bouncing off the assorted optical pieces inside a lens to produce flaring and scattering tied to the shape and movement of highlights you single out in the shot. It's a convincing simulation that performs best when the scene holds light sources or specular reflections—think headlights on a car, the sun, light fixtures, fire and flame, or any other lighting elements credibly bright enough to throw off such flaring. What's more, this plugin truly comes alive when those light sources travel, since each layer of simulated reflection moves in line with that element's spot inside the virtual lens being modeled, yielding organic motion you never have to keyframe. Lacking strong highlights, this filter's output works well for more abstract light-leak looks.

On the left, the original picture; on the right, Lens Reflections applied. Output The Output controls give you a preview of the picture at various stages of the Lens Reflections effect.

- View Output Buttons: Lets you preview the picture at various stages of the Lens reflection effect, viewing the Source Regions, Reflections Alone or Final Result.
- Input Alpha: Decides how the input alpha channel gets used. Masks the Source Regions: Leans on the input alpha channel to keep sources in those areas from throwing off light rays.

Is Used for Compositing: Puts the input alpha channel to work for compositing. Is the Source of the Glow: Treats the input alpha channel as where the glow originates, This can come in handy on VFX heavy shots where custom mattes or Fusion alpha outputs mark out custom glow areas.

- Quality: This pop-up lets you decide how the effect renders. Choices are Full, Half (Faster), and Quarter (Fast). You're trading sharpness against speed. The reflection process itself stays identical at every quality level. Smoother, lower-resolution material won't gain anything from the Full Quality setting.

### Source Regions

The Source Region controls let you pick which scene highlights will spawn lens reflections. You can watch what these controls do directly by switching Select Output to Isolated Source. It's strongly advised to tailor the Isolation controls to the picture in front of you when running this plugin, since, even more than with other plugins, the specific highlights involved sway the final effect dramatically.

- Color Mode: A pop-up menu that lets you either hold onto the colors of the various highlight regions feeding the lens reflections, or render them all as grayscale brightness alone (color controls downstream can still alter the effect). Grayscale processes faster, but Color can yield some dazzling results.
- Brightness: Sets the threshold at which highlights are isolated.
- Gamma: Lets you shape the isolated highlights.
- Smooth: Lets you blur details in the highlights you'd rather not have stand out.
- Color Filter: Lets you single out one particular highlight color to isolate (an eyedropper lets you

select a value from the Viewer).

- Morph Operation: A pop-up lets you tweak the resulting Isolation matte (choices include Shrink,

Grow, Opening, Closing), with a slider to set the amount. Morph Amount: Tunes the edges of the light source per the Morph Operation you picked.

### Global Controls

The Global controls let you swiftly and simply tune the overall quality of the Lens Reflections effect through one centralized cluster of parameters.

- Global Brightness: Lets you push the level of every reflection up or down. Lowering brightness is a handy way to soften a big lens reflection effect, though pictures carrying small lens reflection effects might gain from a touch more brightness.
- Global Blur: Lets you defocus every reflection. This is another solid route to softening lens reflection effects of all sorts.
- Anamorphism: Lets you warp the reflection elements to mimic the stretch of an anamorphic lens.
- Global Colorize: Lets you tune the color intensity of the reflections, whether by deepening the color of all reflections or draining it.

### Presets

A Presets pop-up offers a range of different settings to start from. Choosing a preset fills in the Reflecting Elements parameters below, from where you can tailor the effect to suit the picture in front of you. It's strongly advised to tailor these effects to match the kind of highlights in your picture so you get the best outcome.

### Reflecting Elements

There are four clusters of Reflecting elements, each carrying identical controls. That lets you build interactions blending as many as four sets of reflections. The controls inside each cluster are these.

- Brightness: Lets you tune the intensity of that reflection.
- Position in Optical Path: Lets you slide the reflection along an element's position in the

lens. In practice, that means positive values grow an inverted reflection drawn from the highlights, while pulling values toward 0 shrinks the reflection, and pushing into negative values flips the reflection and drags it the other way as it starts growing once more. A value of –1 places the reflection squarely over the highlight that produced it.

- Defocus type: Lets you pick the kind of blur to apply, options being Box blur, Triangular blur, Lens blur (the heaviest on the processor), and Gaussian blur (the default).
- Defocus: Lets you decide how much to blur that element.
- Stretch: Lets you hand the flare an anamorphic widescreen feel.
- Stretch Falloff: Lets you taper the edges for a less even stretch.
- Lens Coating: A pop-up lets you pick common colors like purple, green, and yellow matching different anti-reflective lens coatings, plus an assortment of other vivid colors. Defaults to none. Choosing any other option surfaces a color control and eyedropper so you can manually set a color or sample one from the picture. A Colorize slider lets you vary how strongly to tint the reflection with the chosen color, though dropping Colorize to 0 lets the flare draw its color from the source highlights of the picture, which can occasionally give you the most striking look.

### Light Rays

A "rays of light" effect that recreates volumetric lighting streaming out of light sources marked by a threshold you set. The effect echoes what people sometimes call "god rays" across the sky, or other strongly directional glow effects.

### Main Controls

The Main controls include:

- View Output Buttons: Lets you preview the picture at various stages of the Lightray effect, viewing the Source Regions, Rays Alone or Final Result.
- Input Alpha: Decides how the input alpha channel gets used. Masks the Source Regions: Leans on the input alpha channel to keep sources in those areas from throwing off light rays. Is Used for Compositing: Puts the input alpha channel to work for compositing. Is the Source of the Glow: Treats the input alpha channel as where the glow originates. This can come in handy on VFX-heavy shots where custom mattes or Fusion alpha outputs mark out custom glow areas.
- Source of Rays: Lets you set what emits the rays, using Bright Regions or Edges.
- Source Threshold: A slider that lets you set the cutoff at which bright parts of the picture

emit rays.

### Position

Position parameters let you set the direction the rays travel.

- Ray Directions: A pop-up menu offering a choice between "From A Location," which surfaces controls for picking an X or Y position to mark an origin point setting the angle of the light beams, or "At an Angle," which surfaces controls for picking an overall orientation for the rays.

### Shimmer

Adds gentle variation to the light pattern thrown by the rays.

- Add Shimmer: Tick this box to switch the Shimmer effect on or off.
- Strength: Governs how much the light patterns vary.
- Detail: Governs the relative detail of the variation, lower levels produce finer detail and higher

levels produce larger detail.

- Scale: Governs the size of the noise pattern.
- H vs. V Ratio: Governs the ratio between horizontal and vertical spread of the variations.
- Evolution: How much the noise pattern should shift.
- Seethe: How much to automatically evolve on each frame counting from the start.

### Appearance

Appearance parameters let you tailor the ray effect.

- Ray Dropoff: A pop-up carrying four options. Default (soft): Yields soft, indistinct rays of light that seem to dissolve as they stream outward. Keep Shape of Source: The edge of the light rays follows the shape that emitted them. CCD Bloom Harsh: Sharply lifts the brightness of the part of the picture emitting rays as Length climbs, producing harsh glow or bloom in the picture.

CCD Bloom Soft: Mildly lifts the brightness of the part of the picture emitting rays as Length climbs, producing a very gentle brightening of the picture.

- Length: Lets you make the rays longer or shorter.
- Relative Length Red: How far the red glow spreads compared with the other colors.
- Relative Length Green: How far the green glow spreads compared with the other colors.
- Relative Length Blue: How far the blue glow spreads compared with the other colors.
- Soften: Lets you blur the rays being emitted.
- Brightness: Lets you tune how bright the rays are.
- Gamma: Tunes the brightness of the ray effect through a gamma curve.
- Saturation: Tunes the intensity of the ray's color.
- Color: A color picker and eyedropper let you set a color with which to tint the rays.
- Composite Type: Lets you pick a composite mode for blending the glow effect into the

picture. Defaults to Add, which suits hotter, more intense rays. Screen lets you make gentler rays, while other composite modes let you produce other varied effects.

- Bright Region Recovery: Drag this slider to win back some picture detail in spots blown out by the rays.

### Atmosphere

- Add Atmosphere: Tick this box to switch the Atmosphere effect on or off.
- Strength: Governs how much the light patterns vary.
- Detail: Governs the relative detail of the variation, lower levels produce finer detail and higher

levels produce larger detail.

- Scale: Governs the size of the noise pattern.
- H vs. V Ratio: Governs the ratio between horizontal and vertical spread of the variations.
- Evolution: How much the noise pattern should shift.
- Seethe: How much to automatically evolve on each frame counting from the start
