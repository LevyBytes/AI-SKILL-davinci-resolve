# Resolve Fx Film Emulation (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Resolve FX Film Emulation

Built to reproduce the traits of motion picture film, these plugins serve aesthetic and creative ends.

### Camera Shake (Studio Version Only)

This effect mimics random camera movement across Horizontal and Vertical position, Rotation, and Zoom. You get an assortment of parameters for shaping the motion's character, ranging from a slow wandering drift through to sharp, jagged jerks and pops.

### Main Controls

The chief controls deciding how much camera shake gets applied.

- Motion Scale and Speed Scale: With these sliders you tune the overall amplitude and pace of the camera shake added to the image.
- Motion Blur: Lets you layer simulated motion blur onto the shaken image, lending the motion a more lifelike feel. Such blur shows up more on fast movement, since DaVinci Resolve is mimicking how a motion picture camera's shutter speed treats subjects exposed while in motion.

### Shake Levels

These controls let you dial in how intense the camera shake is.

- Pan Amplitude: Lets you decide how much horizontal motion to apply.
- Tilt Amplitude: With this slider you pick how much vertical motion to apply. The two sliders stay

wholly independent of each other.

- Rotation Amplitude: Lets you fold rotational motion into the camera shake too.
- PTR Speed: Through this slider you set how quickly the Pan, Tilt, and Rotation camera shake runs.
- Zoom Amplitude: Through this slider you add zooming to the camera motion you're building.
- Zoom Speed: Through this slider you pick how quickly this random zooming plays out.
- Zoom Type: From this pop-up menu you decide how zooming is added; the choices are

Outward Only, Inward Only, or Outward and Inward. Pick Inward Only and blanking never creeps in around the frame's edges.

### Shake Quality

These controls let you tailor the kind of shaking you're after.

- Motion Method: From this pop-up menu you select among several ways of generating the motion this plugin brings in. Your options are SINE, Rectified SINE, Rectified SINE (Invert), and Square Wave (handy for popping or flickering motion).
- Phase: With this slider you fix where the camera shake you're building begins, drawing on the Motion Method and Amplitude settings you've picked.
- Randomness Scale: With this slider you work irregularity into the camera shake's Horizontal, Vertical, and Rotational motion. A higher value brings in more irregularity.
- Randomness Speed: With this slider you swing between smoothly erratic motion (toward the low end) and more jagged motion (toward the high end).
- Pause Length: With this slider you tune how often the intermittent pauses arrive that interrupt the random motion this filter adds.
- Pause Interval: With this slider you tune how long the intermittent pauses last that interrupt the random motion this filter adds.
- Pause Randomness: This lets you sprinkle some randomness into the intervals that occur.
- Random Seed: With this slider you change the value driving which random values get

produced. Matching values yield matching randomness.

### Blanking Handling

These controls let you settle what happens when camera shake pushes blanking beyond the image's edge.

- Border Type: From this pop-up menu you pick how to fill the empty edge spaces that show up when the camera shake you create shoves the image past your project's current frame size. Four options let you Replicate, Reflect, or Wrap-Around the image to plug the gap.
- Zoom to Crop: With this slider you zoom into the image to trim away unwanted blanking that the Camera Shake effect brings in.

### ColorTone Diffuser

Designed to imitate a diffusion filter ringed by a rectangle of user-adjustable colored lights, the ColorTone Diffuser is one such effect. As you change those lights' color and intensity, their light scatters off the diffusion elements set into the glass filter sitting right in the camera's image path. This lets you craft particular artistic and creative looks that post tools alone had a hard time delivering, until now.

### The original image

The image with the ColorTone Diffuser “Teal Soft” preset

### ColorTone Diffuser

- Presets: Offers a collection of ColorTone presets to audition on your footage as jumping-off points. Its default, Clean Slate, leaves everything untouched and frees you to build your own custom look.
- 3D LUT Compatible: Switches off every control that a LUT can't carry.
- Color Space Overrides: These controls let you swap the effect's input gammas and color spaces should you need to set them by hand for a display referred workflow. The default, “Use timeline,” lines up with the color spaces you've chosen in the Color Management section of the Project Settings.

Input Color Space: Fixes the input color space; pick one from the drop-down menu. Input Gamma: Fixes the input gamma; pick one from the drop-down menu.

- Diffusion: Spills the bright regions outward, bleeding them into neighboring parts of the frame.

Resolution: Set how much blur lands on the image to recreate the slight resolution loss as light comes through the filter. Diffusion: Tick this box to switch Diffusion on or off. Amount: How strong the diffusion effect is. Radius: How large the diffusing area is.

- Shadow Soft Clip: Shields the shadows from the ColorTone Diffuser's reach. Whatever falls below this level skips the filter. Shadow Clip: Tick this box to enable or disable Shadow Clipping. Threshold: Set the lowest black level the ColorTone Diffuser is allowed to touch. Softness: How gradually the black level is held back at the threshold.
- Highlight Soft Clip: Keeps the highlights clear of the ColorTone Diffuser's reach. Whatever sits above this level skips the filter. Highlight Clip: Tick this box to enable or disable Highlight Clipping. Threshold: Set the highest bright level the ColorTone Diffuser is allowed to touch. Softness: How gradually the bright level is held back at the threshold.
- Tone Lights: These govern the hue of the ring lights scattering off the filter's diffusive elements. Intensity: Governs the overall level of tone light cast across the frame. Bias Red / Green / Blue: The proportion of a given color within the Tone Light. Since these controls hinge on the content and read more clearly in shadows, brighter footage may show little visible change.
- Tone Light Falloff: Imitates how the light dims toward the filter's edges and intensifies at its center. Underneath, a vignette mask is what maps where the effect lands. Apply Falloff Mask: Tick this box to switch the Tone Light Falloff on or off. Preview Falloff Mask: Ticking this box surfaces the Falloff Mask's vignette in the viewer, where darker regions take less of the effect and white more. Size: Set how large the mask's center is. Softness: Sets how soft the mask grows as you travel out from its center. Amount: How forcefully the mask shapes the effects.

In a Falloff Mask preview, the effect reads more strongly across the mask's white regions

- Image Adjustments: Hands you fundamental exposure, contrast, and saturation controls. Making these tweaks here in the node folds everything into the LUT, sparing you from stacking another grade above the node. Enable Adjustments: Tick this box to switch on the Image Adjustments. Show Advanced Clipping Options: Ticking this box brings up a further set of shadow and highlight softclip controls that behave just like the ones above. These, however, run at the plugin's end rather than its start, which can stop blow outs from being reshaped by the original shadow and highlight softclip controls. Exposure: Tunes the Brightness / Gain. Contrast: Tunes the Contrast. Saturation: Tunes the Saturation.

### Film Damage

You'll find it in the Resolve FX Texture category. Once you've leaned on the new Resolve FX Revival plugins to mend damage in archival footage, you can flip things around and apply the Film Damage plugin to give freshly shot digital clips a worn, grimy, scratched appearance instead. Pair it with the Film Grain and Flicker Addition plugins and you can persuasively rebuild the look of badly stored vintage archival footage.

Original image (Left), and result with Film Damage (Right)

### Blur and Shift Controls

The three parameters up top let you reshape the image's underpinnings as a first step toward an older-film look.

- Film Blur: Throws in a touch of targeted defocusing to take the digital crispness off the image.
- Temp Shift: By default it warms the image a little to echo the warmer bulb of a film projector,

though you can push it to cool or warm the image by varying degrees.

- Tint Shift: By default it yellows the image to suggest harm to the film dyes, yet sliding it the opposite way

adds a hint of magenta, evoking a different sort of dye failure.

### Add Vignetting

These parameters mimic lens vignetting that darkens the image's edges.

- Focal Factor: Tunes how deep the vignetting reaches into the image.
- Geometry Factor: Shapes how dark the vignetting runs and how sharply its edges read.
- Tilt Amount: Shapes how evenly the vignetting at the image's top weighs against the bottom.
- Tilt Angle: Shapes how evenly the vignetting on the image's left weighs against the right, though only while Tilt Amount sits at something besides 0.

### Add Dirt

These parameters let you mimic dirt particles (not dust) clinging to the film. They are the larger specks, and you have several ways to shape them.

- Dirt Color: With this control you decide the dirt particles' color (black mimics dirt on a print, while white mimics dirt on a negative).
- Changing Dirt: This checkbox lets you toggle between mimicking temporally unstable dirt on the film (ticked) and stationary dirt on the lens (unticked).
- Dirt Density: Lets you set how many dirt particles surface over time.
- Dirt Size: Lets you set the typical size of the dirt particles that appear.
- Dirt Blur: Lets you soften the dirt's focus so it reads less sharply.
- Dirt Seed: Shifting this value reshuffles the random spread of dirt, yet for any single

value the results hold steady across any given set of control tweaks.

### COLOR 3510

### Add Scratch

Five sets of Add Scratch parameters let you place as many as five scratches on the image, mimicking something gouging the emulsion as the film ran.

- Scratch Color: Lets you set the scratch's color (scratches can take on a range of colors depending on the scratch's depth, the film type, and the printing method).
- Scratch Position: Lets you shift the scratch's horizontal placement across the image.
- Scratch Width and Scratch Strength: Let you tune how severe the scratch appears.
- Scratch Blur: Lets you soften the scratch's focus.
- Moving Scratch: With this checkbox you decide whether the scratch jitters around or holds still.
- Moving Amplitude: Sets how far the scratch travels.
- Moving Speed: Sets how quickly the scratch travels.
- Moving Randomness: Sets the way the scratch wanders about.
- Flickering Speed: Sets how much the scratch flickers lighter and darker in severity.

### Film Grain (Studio Version Only)

Lays a procedurally built layer of simulated “film grain” over the image as a composite. Each simulated grain, complete with falloff, is generated to suit the project's resolution.

### Main Controls

These controls let you swiftly pick and lay down a film grain effect.

- Film Grain Presets: This pop-up lets you swiftly pick from a range of 8mm, 16mm, and 35mm film grain effects.
- Composite Type: Lets you settle on a composite mode for marrying the image to the grain this plugin simulates.
- Opacity: Lets you fade the Film Grain effect against the original image.
- Grain Only: With this checkbox you view the grain layer on its own as you build it, so you

can judge its look before it gets composited into the image.

- Freeze: Halts the grain animation's motion, so you can put the effect to use on a still image or

freeze frame.

### Grain Params

The Grain Params group lets you fine-tune the grain's quality.

- Texture: Bigger values spread the grains this plugin generates farther apart, whereas smaller ones pack them tighter for denser grain patterns.
- Grain Size: Bigger values zoom in on the individual simulated grains this plugin generates, whereas smaller ones zoom back out.
- Grain Aspect Ratio: Lets you tune the grains' aspect ratio.
- Grain Strength: Tunes the simulated grain layer's contrast. Higher values yield more

contrast, lower ones less.

- Offset: Brightens or darkens the whole simulated grain layer. In practice, lower

values play up the lighter grains while higher ones play up the darker grains.

- Symmetry: A lopsided contrast tweak. Lower values darken the lighter grains,

whereas higher values brighten the darker grains.

- Softness: Lets you blur the grain layer for even gentler transitions from one grain to the next.
- Saturation: Lets you dial the grain's color up or down. Set to 0, the grain turns monochrome.

### COLOR 3511

### Advanced Controls

Within the Advanced Controls, the Red, Green, and Blue sliders steer the grain's color. The Shadow, Midtone, and Highlight Gain controls let you set how much grain is composited into each of those tonal zones of the image. Switch on the Optimized Mode checkbox (its default state) and performance ought to climb considerably. Switching on the Animate on Every Refresh checkbox animates the grain while you work the sliders, giving you a clearer sense of how the grain pattern reads in motion.

### Film Look Creator (Studio Version Only)

The Film Look Creator lets you readily reshape both the color and the physical qualities of an image to imitate motion picture film stock, all inside a single Resolve effect. Rather than chasing any one manufacturer's film stock, it lays down a base “Blackmagic” film look that you can then bend in all sorts of creative directions. The Film Look Creator reworks an image's contrast, saturation, hue, and exposure. It packs in the tools you'd want for film emulation as well — halation emulation, film gate, flicker, weave, vignetting, bloom, and more.

At left, the original video; at right, its Film Look Creator Bleach Bypass Super 16mm rendition A good number of the Film Look Creator's pieces have their own dedicated equivalents over in the Resolve FX library. Even so, the Film Look Creator rolls these film look tools into one Resolve effect with a vastly streamlined control set. Should you ever want finer command over some facet of the look, you can simply switch off that module of the effect and drop a dedicated Resolve Effect into the node tree instead. Apply this effect and an underlying Blackmagic film look is laid in automatically up front. Over 60 parameters drive that film look, all handed to you the moment the plugin is active (with every effect off). These parameters come carefully tuned and “baked in” to the Blackmagic film stock. Although you can't touch those, the plugin's upper region carries extra controls for refining and shaping looks of your own. Built for scene referred workflows, the Film Look Creator works with any camera source and output display. Under either Resolve Color Management or ACES this falls into place on its own, because the plugin defaults to the timeline color space for both input and output. It functions on manually display referred timelines (DaVinci YRGB, for instance) too, but there the user has to hand-pick the source footage's transform and the display transform, which you handle within the plugin's Color Space Overrides section. NOTE: The Film Look Creator does its best work on video that fills the whole frame. Effects such as Halation and Film Gate can behave unexpectedly when the video sits smaller than the frame size. Where needed, fill the frame with the Sizing controls, or head to Project Settings > Image Scaling > Input/Output Scaling and pick “Scale Full Frame with Crop” in place of the default “Scale entire image to fit.”

### Main Controls

These controls build this effect's foundation.

- Presets: Sets every control automatically for a chosen preset look. “Clean Slate” skips the underlying Blackmagic Film Look and leaves you a clean image to start from. “Default No Effects” switches the Blackmagic Film Look on while turning off all the extra effects beneath.
- Color Blend: Lets you blend the underlying color look with whatever changes you've made to other color settings and split tone controls.
- Effects Blend: The master control for tuning the strength of the spatial effects below. At 0% the effects are fully off, and at 100% you get the Film Look Creator's complete output.
- 3D LUT Compatible: Ticking this box strips out the spatial effect options that a 3D LUT can't represent. That lets you carry your custom film look over to other programs and camera hardware through a LUT.

### Color Space Overrides

These controls let you reassign the effect's input and output gammas and color spaces whenever you have to set them up by hand for a display referred workflow. Bear in mind that altering them applies no tone mapping. Their default, “Use timeline,” lines up with the color spaces you've chosen in the Color Management section of the Project Settings.

- Input Color Space: Fixes the input color space; pick one from the drop-down menu.
- Input Gamma: Fixes the input gamma; pick one from the drop-down menu.
- Output Color Space: Fixes the output color space; pick one from the drop-down menu.
- Output Gamma: Fixes the output gamma; pick one from the drop-down menu.
- Output White Point: Fixes the display white point. For creative ends, you can pick one from

the drop-down menu. The default white point is D65.

### Film Look

These controls let you shape the base film look's overall parameters.

- Film Look Blend: Tunes how strong the initial default base film look is, before you touch other parameters.
- Skin Bias: Tunes the film look's skin tones. Negative values lend warm, darker, more saturated skin tones, whereas positive values lend brighter, rosier, less saturated ones.

### Color Settings

These controls let you reshape the color information behind the film look. A 3D LUT will carry these effects.

- Exposure: A photometric control that shifts the exposure in stops (+/- 5).
- Contrast: Reshapes the overall S-curve transfer function to add contrast to or strip it from the shot.
- Highlights: Reshapes the roll-off at the S-curve's top, letting you rein in or stretch out the

shot's brightest regions.

- Fade: Reshapes the roll-off at the S-curve's bottom, letting you rein in or stretch out the

shot's darkest regions.

- White Balance: Through chromatic adaptation, this control imitates how the source footage might

have looked had it been shot under different lighting. It is set in degrees Kelvin.

- Tint: Lets you shift the clip's green/magenta balance to even out footage shot under

narrow-spectrum lighting like fluorescent tubes or sodium vapor streetlights.

- Skin Bias: Lets you shift the image's skin tones, running from -1 (warmer, darker, more saturated) to +1 (rosy, brighter, less saturated). It also comes in handy when you, say, push tint one way and then call on Skin Bias to even the image back out.
- Subtractive Sat: Lets you tune the image's overall saturation in a manner that hews closer to a subtractive approach.
- Richness: Works on the already more saturated regions, laying subtractive saturation onto just those areas. Handy for deepening and enriching the image, or for easing off slightly on the more saturated regions.
- Bleach Bypass: Recreates this familiar look by stacking a desaturated, higher-contrast copy of the image back onto itself.

### Split Tone

These controls tint shadows and highlights along opposing hue angles — say, orange into the highlights and teal into the shadows for a more contemporary cinematic feel. A 3D LUT will carry these effects.

- Enable Split Tone: Switches this effect on or off.
- Split Tone Mode: Pick between the Strong and Natural settings.
- Amount: How intense the split tone is. This value has to exceed 0 before any effect shows.
- Hue Angle: This slider sets which complementary hues land on the shadows and highlights.
- Pivot: This control fixes where in luma the hue transition falls. Pushed to its extremes of 0.000 or

  1.0000, the pivot lets you drop a single tint onto the shadows or the highlight.

### Vignette

These controls are a pared-down window for dropping a vignette onto the shot. When you want finer command, switch this setting off and turn to the Vignette effect instead.

- Enable Vignette: Switches the vignette on or off.
- Amount: Sets how intense the vignette's darkened regions are.
- Size: Sets how far the vignette pushes into the frame.

### Halation

These controls offer a pared-down way to wrap soft glows around the edges of the subjects in your frame, echoing this trait of motion picture film. For finer command, switch this setting off and turn to the Halation effect instead.

- Enable Halation: Switches the Halation effect on or off.
- Highlights Only: Confines the Halation effect to the edges of highlights alone.
- Amount: Lets you fix how intense the halation is.
- Radius: Lets you fix how far the glow spreads out from the edges.
- Saturation: Lets you tune the halation's color intensity.
- Hue: Lets you tint the glow with a chosen color.

### Bloom

These controls let you bring a faint glow around the edges of highlights.

- Enable Bloom: Switches the Bloom effect on or off.
- Amount: Lets you fix how intense the bloom is.
- Radius: Lets you fix how far the bloom spreads out from the edges.

### Grain

These controls form a pared-down toolset for reproducing the grain patterns you find on motion picture film. When you want finer command, switch this setting off and turn to the Film Grain effect instead.

- Enable Grain: Switches the grain pattern on or off.
- Preset: Hands you a few jumping-off points for grain, grounded in film stock standards.
- Amount: Sets how much grain appears in the image.
- Size: Sets how large the grain in the image is.
- Softness: Sets how crisp each individual grain reads.
- Saturation: Tints the grain. At 0 it stays monochromatic.
- Image Defocus: Bears on the image's overall resolution, softening focus further as you pull the

control toward 0. At 1.000 the resolution stays untouched. This control leaves the grain alone.

### Flicker

These controls lend the image exposure a soft pulse, echoing the flicker of motion picture projection. For finer controls, switch this setting off and turn to the Flicker Addition effect instead.

- Enable Flicker: Switches the Flicker effect on or off.
- Amount: Sets how much flicker reaches the image. Low settings barely register,

while high ones lend themselves to more extreme looks such as the Nostalgic preset.

- Rate: The pace at which the flicker pulses.

### Gate Weave

These controls reproduce the faint horizontal and vertical drift of the image as the film is mechanically dragged through the camera's gate.

- Enable Gate Weave: Switches the Gate Weave on or off.
- Amount: Sets how much motion the weave carries.
- Rate: The pace at which the weave moves.

### Film Gate

These controls lay blanking along the image's edges that echoes film projection or telecine alignment controls.

- Enable Film Gate: Switches the Film Gate on or off.
- Preset: Pick an aspect ratio drawn from various common film standards.
- Ratio H/V: Here you can set a custom ratio for the image.
- Enable Curvature: Switching this on gently rounds the image's corners to echo the way an actual

film frame's shape is exposed.

- Padding: This zooms the image into and out of the blanking, letting you take in the entire
