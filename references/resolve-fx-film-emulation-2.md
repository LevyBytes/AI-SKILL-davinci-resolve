# Resolve Fx Film Emulation (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

exposed “frame” of film where you want it. It behaves much like a telecine control. NOTE: Film Gate can produce surprising outcomes when the video hasn't been scaled to cover the whole frame. Should that be the situation, first reach for the sizing controls to make your image fill the frame.

### Flicker Addition

Rather than stripping flicker out with the Resolve FX Flicker Removal plugin, why not put some in? The Flicker Addition plugin introduces fast, animated exposure shifts that make the picture seem to flicker, producing animated results that would be tough to keyframe on your own. Applied to an image in various ways, this plugin can stand in for torchlight, firelight, fixtures running old ballasts or frayed wiring, or any light source that's unstable over time. As an example, you might key just the highlights in a night-time shot and let Flicker Addition act on those isolated highlights alone. Its flickering quality is governed by two sets of controls.

### Main Controls

With these controls you decide how the flicker gets applied along with its overall pace and strength.

- Flicker Type: This pop-up menu sets which kind of adjustment carries the flicker, your choices being Lift, Gamma, Gain, Vignette, or Alpha.
- Range slider: Use this to dictate how broadly the flickering ranges.
- Speed: Use this to set the rate at which the flickering animates.
- Smoothness: With this slider you tune the temporal character of the flickering, deciding whether it jumps

sharply from one value to the next (at lower settings) or eases through smoother transitions between values (at higher settings).

- Flicker R, G, B Channels: A trio of checkboxes lets you pick which color channels this flickering touches.

### Flicker Quality

These controls let you fine-tune the specifics of the flickering animation.

- Randomness Scale: With this slider you bring irregularity into the Horizontal, Vertical, and Rotational motion of the camera shake. A higher value brings in more irregularity.
- Pause Length: This slider governs how often the intermittent pauses occur that interrupt the random motion this filter adds.
- Pause Interval: This slider governs how long the intermittent pauses last that interrupt the random motion this filter adds.
- Pause Randomness: This adds some measure of randomness to the intervals that take place.
- Random Seed: This slider changes the value that determines which random values get

generated. Matching values yield matching randomness.

### Halation (Studio Version Only)

An effect that recreates the faint light scatters, reflections, and analog blooms produced as light bounces back through the dye layers of motion picture film. Typically it shows up as a delicate red/orange-tinted glow ringing bright, high-contrast areas such as lights or reflections. Halation can equally arise from light bouncing inside processing and development gear, or within the camera body. Such small imperfections lend digital files a quietly organic, analog feel.

The Halation effect can lend an organic, analog l ook to your digital files. Original (L), Halation (R). A range of tools and controls hands you precise say over just how the halation comes across.

Before the Halation effect is applied The same image carrying the Halation effect; observe how the halation appears in the water reflections and on the woman wearing the white t-shirt.

### Processing Color Space

Allows you to pick the color space used by the Halation effect. By default it matches whatever the current timeline uses.

### Isolation

Which parts of your clips end up producing halation halos is set by the Isolation controls.

- Threshold: Sets the low clip level used by the Halation effect.
- Normalization: Sets the high clip level used by the Halation effect.
- Film Saturation Level: The point past which all color gets suppressed and pushed to white. This proves handy in HDR workflows, keeping the resulting Halation effects visible at HDR brightness levels.
- View Isolated Regions: Displays solely the regions singled out for producing the Halation effect.

The View Isolated Regions checkbox reveals which areas the halation is going to act on.

### Dye Layer Reflections

Through the Dye Layer Reflections controls you can fine-tune the physical traits of the halation glow.

- Strength: Sets how bright the reflection is.
- Gamma: Sets the manner in which the glow spreads out.
- Saturation: Sets how intense the glow's color appears.
- Spread: Sets how far the dye reflection reaches.
- Fine Tune Relative Spread: Ticking this box lets you adjust the red, green, and

blue reflection distances by hand.

### Secondary Glow

Extra halation traits come from the Secondary Glow controls.

- Strength: Sets how bright the secondary glow is.
- Gamma: Sets how the glow spreads out.
- Spread: Sets how far the glow extends around bright detail.
- Filter: Confines the glow's color to the chosen color.

### Basic Grain

This is a pared-down slice of the Film Grain effect offering fast grain settings. Should you want more, you can place a full Film Grain effect instance just after the Halation effect on the same node for finer detail.

- Append Gain internally: Switches on the simplified grain control.
- Strength: Introduces grain into the halation layer.
- Size: Sets how large the grains are within the halation layer.
- Softness: Softens the grain texture.
- Saturation: Applies saturation to the grain.

### Global Adjustments

- View Glow Alone: This checkbox displays the Halation effect by itself before it merges into the frame. Switching it on comes in handy while you adjust any of the tools above.

The View Glow Alone checkbox presents the Halation effect on its own, kept separate from the underlying image rather than blended with it.

- Reduce Highlights: Dials back the effect in places where it would lighten the scene without feeding the halo. In practice this keeps the halo along a region's edges while sparing the region itself from being blown out.
- Aspect Ratio: Stretches or compresses the glow and grain along the horizontal axis for anamorphic projects.
- Detail Loss: Strips away fine detail the film stock wouldn't realistically have resolved, by defocusing the

image beneath the effect.

### Split Tone Effect

With the Split Tone effect you tint shadows and highlights along opposing hue angles. You might, for instance, push orange into the highlights and teal into the shadows for a more contemporary cinematic feel.

The unaltered image The Preview Influence checkbox reveals where each split color lands and which one it is

### The final split-toned image

### Split Tone

- Split Tone Mode: Bundles presets together with a custom mode. Natural: Built to imitate how film behaves. Strong: A bolder, more deliberate stylized look. Custom: Hands you full command over whichever two colors you want for the Split Tone.
- Preview Influence: Reveals where the split falls, rendered in true colors.
- Shadows (custom only): Governs the shadow half of the split. Strength: How saturated the picture's darker areas become. Hue: Which color those darker areas take on.
- Highlights (custom only): Governs the highlight half of the split. Strength: How saturated the picture's lighter areas become. Hue: Which color those lighter areas take on.
- Neutrals (custom only): Shields the neutral (grey tone) regions of your image from the Split Tone effect. Protect Neutrals: Tick this box to switch the Neutrals controls on or off. Minimum Saturation: Regions sitting below this saturation stay grey. Maximum Saturation: Regions sitting above this saturation feel the Split Tone effect.
- Strength: The amount of split tone color blended into the original image.
- Pivot: Fixes where highlights and shadows part ways, establishing the spot at which the

color “splits”.

- Hue Angle: The split tone's color, read off as the angle on the vectorscope.
- Color Space Overrides: With these controls you can alter the effect's input and output gammas

and color spaces whenever a display referred workflow asks you to set them up manually. Its default value is “Use timeline,” which falls in line with the color spaces chosen under the Color Management section within the Project Settings. Input Color Space: Establishes the input color space, picked from the drop-down menu. Input Gamma: Establishes the input gamma via that same drop-down menu. Output Color Space: Determines the output color space, again chosen from the drop-down. Output Gamma: Determines the output gamma using the drop-down menu. Output White Point: Fixes the display white point. With creative aims in mind, you may pick one from the drop-down menu. The default white point here is D65.

### Vignette

A plugin offering two modes for building vignette effects of varying styles.

- Basic mode hands you Size, Anamorphism, and Softness controls to rapidly build a classic lens vignetting effect that darkens the frame's edges. A Color control adds a tint to the vignette.
- Advanced mode brings in Border Shape, Rotation, Center, Transparency, and Composite Type controls so you can tailor this vignetting effect with even greater precision.
