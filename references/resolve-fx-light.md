# Resolve Fx Light (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Resolve FX Light

Every plugin grouped here recreates some distinct optical or lighting phenomenon. Although the majority were built to hand you believable output quickly, each one can be driven further to deliver a wide range of stylized looks.

### Aperture Diffraction (Studio Version Only)

Located within the ResolveFX Light category, Aperture Diffraction reproduces the starburst look that typically appears when bright sources are filmed at small apertures; physically, it stems from light bending around a lens's aperture blades. The plugin recreates that behavior, automatically targeting scene highlights you can isolate and tune through adjustable virtual apertures. Tiny bright patches take on a star-shaped glow, illustrated in the picture below.

(Left) Original image, (Right) Applying Aperture Diffraction Broader bright areas instead produce a smoother glow whose shaping and texture resemble a genuine optical artifact. You can lean on it for a glow variant that, in certain shots, reads more believably than the Glow plugin, at the cost of heavier processing. Elsewhere, the tool unlocks a broad palette of stylistic glow treatments.

(Left) Original image, (Right) Applying Aperture Diffraction

### Output

This group of controls determines which image the plugin sends downstream.

- View Output Buttons: Lets you inspect the picture at various stages of the Aperture Diffraction process, viewing the Source Regions, Diffraction Alone or Final Result.
- Input Alpha: Determines the role played by the incoming alpha channel. Masks the Source Regions: Employ the input alpha channel to keep sources in those zones from emitting light rays. Is Used for Compositing: Treats the input alpha channel as a compositing matte. Is the Source of the Glow: Treats the input alpha channel as the origin of the glow. This proves useful on VFX-heavy shots where hand-drawn mattes or Fusion alpha outputs mark out bespoke glow regions.
- Quality: Lets you pick a quality level balancing fidelity against rendering speed. Choices are Full, Half (Faster), Quarter (Fast). The high setting yields diffraction with finer detail but is otherwise identical in behavior. When the shot contains no tiny point lights, half or quarter settings are perfectly safe and cost you nothing in image quality.

### Source Regions

With the Source Region controls you decide which of the scene's highlights produce visible glow and patterning. You can watch their impact directly by switching Select Output to Isolated Source..

- Color Mode: A pop-up menu through which you either retain the hues of the various glow-producing highlight zones, or render them all as grayscale luminance alone (downstream color controls can still alter the look). Processing grayscale is quicker, yet Color can yield some striking results.
- Brightness: Establishes the cutoff above which highlights become isolated.
- Gamma: Lets you reshape the isolated highlights.
- Smooth: Lets you soften highlight detail that you would rather not see emphasized.
- Color Filter: Lets you target a specific highlight hue for isolation (an eyedropper lets you

select a value from the Viewer).

- Operation: Lets you refine the resulting Isolation matte (options include Shrink, Grow, Opening,

Closing) with a slider to define how much.

### Aperture Controls

The Aperture controls govern the form and texture of the glow this plugin produces.

- Iris Shape: Lets you pick a shape that sets how many arms appear in the star pattern. Options are Triangle, Square, Pentagon, Hexagon, Heptagon, and Octagon.
- Aperture Size: Lets you reshape the diffraction pattern, shifting toward a star form at higher values and a stippled wave look as values drop.
- Blade Curvature and Rotation: Lets you change the softness and the angle of each star's arms.
- H/V Ratio: Adjusts the aperture's horizontal-to-vertical proportion, letting you mimic an

anamorphic glow.

- Angle: Sets the angle of the aperture.
- Chroma Shift: Lets you push a bit of RGB “bleed” into the glow.

### Diffraction Controls

- Result Gamma: Lets you control how strongly the glow reads in the gaps between the arms of the star patterns.
- Result Scale: Lets you shift between sharply defined star patterns at high values and softer, more spread-out glows at low ones.

### Compositing Controls

These controls govern how the glow gets blended back over the source image.

- Normalize Brightness: This checkbox rescales the glow's brightness on a per-frame basis. As a result, the Aperture Diffraction effect holds a steady overall brightness even as the scene evolves.
- Brightness: Lets you set how intense the glow appears.
- Colorize: Lets you tint the glow using the Color control shown below.

### Cinematic Haze

A haze (or smoke/fog) machine is a common cinematographer's tool for adding a sense of depth and nuance to a shot. Its effect is to reduce contrast and to strengthen that impression the farther a subject sits from the camera. The Cinematic Haze Resolve FX reproduces both that behavior and the look of genuine outdoor smoke/fog conditions, leaning on DaVinci Resolve's powerful AI Depth Map (V2) tool to gauge depth and the objects within a shot. Because of this, Cinematic Haze feels more authentic than merely layering a 2D haze plate on top of the picture, since the haze now behaves as though it occupies a true 3D space, with density that varies by depth, atmospheric scattering, and wind disturbance.

The original image. Your budget might not stretch to actually flooding the whole of Paris with smoke. The depth map preview of the shot, building a matte from each pixel's apparent distance to the camera.

The final image. With the haze settings driven by the depth map, observe how the Eiffel Tower stays clearer than the buildings behind it.

### Color Space Overrides

Here you can override the effect's input gammas and color spaces should you need to set them by hand for a display-referred pipeline. The default, “Use timeline,” mirrors whatever color spaces you picked in the Color Management section of the Project Settings.

- Input Color Space: Establishes the input color space, picked from the menu provided.
- Input Gamma: Establishes the input gamma, picked from the menu provided.

### Depth Map

This group configures the depth map's parameters.

- Depth Map Preview: Switches on the depth map preview so you can review what the depth map has measured. Brighter zones lie farther off, while darker ones sit closer.
- Depth Map Source: Lets you select where the depth map comes from, either generated internally by the plugin or pulled from the node's alpha input when you've supplied an external depth map.
- Invert: Flips the depth map so the near and far ranges trade places.
- Advanced Depth Controls: Tick this box to enable the Advanced Depth Controls.

Quality: Lets you pick between a Better quality or Faster rendering depth map. Stay in Faster mode while you rough in the effect, then flip to Better once you're ready to finish. Adjust Map Levels: Brings the Far Limit, Near Limit, and Gamma controls online as covered below. Isolation: Ticking this box enables the tools that confine the isolation to one chosen depth on the map. Target Depth: Pick the depth you wish to isolate. Tolerance: Pick how broad a depth band you wish to isolate. Softness: Controls whether the boundary between isolated and non-isolated depths is gradual or abrupt. Post Processing: Ticking this box enables the tools that help the effect hug objects more closely. Post Filter: Smooths the depth map to follow image contours. Contract / Expand: Pulls the foreground in or pushes it out. Blur: Softens the picture so colors average together at the edges. Blanking Regions: These controls instruct the Depth Map on how to deal with letter and pillar boxing zones within the effect.

- Process Entire Frame: Instructs the AI to disregard any data about the timeline's shape and simply work on every visible pixel.
- Handle Automatically (default): The AI restricts itself to the region that DaVinci Resolve identifies as holding your media.
- Auto + Extra Crop: This is recommended for cropping away black bars. It draws on DaVinci Resolve's awareness of which pixels your media filled, while still letting you trim away the framing or letterboxing relative to its shape. It comes recommended because it remains consistent as you change Timeline settings.
- Manual Cropping: Simply lets you set the content's framing yourself, disregarding any of DaVinci Resolve's knowledge about your media's shape.
- Deflicker: This dials in how much deflickering occurs. Keep values low for top quality, and raise them if moving objects begin to show extra edges.
- Far Limit: Tunes the depth map's black levels, governing how far out the effect reaches.
- Near Limit: Tunes the depth map's white levels, governing how near the effect reaches.
- Gamma: Lays a gamma curve over the depth map to make it more or less contrasty.

### Atmospheric Scattering

These tools reproduce the way the atmosphere alters light passing through fog and haze.

- Airlight: Controls how much ambient haze there is, akin to an off-screen source such as the moon or a big streetlight.
- Density: Controls how thick the haze is.
- Resolution Loss: Introduces blur to the picture as the haze obscures it.
- Halation Threshold: Defines the brightness ceiling a source light must cross to trigger the

halation effect.

- Halation: Controls how much halation the source lights produce.
- Saturation: Controls the saturation of the halation.
- Colorize: Choose a color to tint the haze.

### Light Halos

You use these controls to fine-tune the light halos.

- Halo Threshold: The cutoff governing source light motivation.
- Size: Controls how large the halo around source lights is
- Brightness: How bright the halo around the source lights appears.
- Saturation: The color saturation that arises from the source lights' own color.
- Colorize: Applies a color cast to the halo.

### Light Rays

These controls recreate volumetric light streaming out from sources within the picture.

- Enable Light Rays: Tick this box to switch on the light rays toolset.
- Preview Threshold: Renders a preview that isolates only those lights in the picture set to

cast rays.

- Source Threshold: Defines how bright an object must be before it casts rays.
- Ray Directions: A pop-up menu offering either “From A Location,” which surfaces

controls for picking an X or Y position as the origin point that fixes the beams' angle, or “At an Angle,” which surfaces controls for setting one overall orientation for the rays.

- Angle: Sets the angle of the light rays.
- Length: Lets you stretch or shorten the rays.
- Soften: Lets you blur the rays as they're emitted.
- Brightness: Lets you set how bright the rays appear.
- Saturation: Tunes how strong the rays' color is.

### Air Disturbance

These controls inject motion and stir the haze to mimic wind or similar atmospheric activity.

- Enable Disturbance: Tick this box to switch on the air disturbance toolset.
- Preview Influence: Renders a preview that displays the disturbance pattern

interacting with the haze depth map.

- Intensity: Controls how dense the air disturbance pattern is.
- Brightness: Controls how bright the air disturbance pattern is.
- Scale: Controls how large the air disturbance pattern is.
- Detail: Governs how much fine detail the disturbance pattern carries.
- Flow Direction: Sets the angle along which the disturbance pattern flows.
- Flow Speed: Governs how quickly the disturbance pattern flows.
- Seethe Rate: Controls how fast the disturbance pattern changes over time.
- Start Frame: Lets you nominate a particular frame where the seethe begins.
- Randomize Start Frame: Picks a random frame for the seethe to begin, which you can use

to avoid repeating the identical disturbance pattern across several shots.

### Glow

A refined, soft glow treatment that stays highly adjustable through just a handful of essential parameters.

- View Output Buttons: Lets you inspect the picture at various stages of the Lens reflection process, viewing the Source Regions, Glow Alone or Final Result.
- Input Alpha: Determines the role played by the incoming alpha channel. Masks the Source Regions: Employ the input alpha channel to keep sources in those zones from emitting light rays. Is Used for Compositing: Treats the input alpha channel as a compositing matte. Is the Source of the Glow: Treats the input alpha channel as the origin of the glow. This proves useful on VFX-heavy shots where hand-drawn mattes or Fusion alpha outputs mark out bespoke glow regions.
- Shine Threshold: Sets the luminance value above which glow begins to appear in the picture.

### Shape and Spread

- Spread: Sets how far the shine reaches out from the picture regions that set it off.
- H/V Ratio: Lets you change the balance of horizontal versus vertical spread, so you can fashion

“streaky” shine that travels farther along one axis.

- Relative Spread Red/Green/Blue: Lets you set a separate spread amount per color channel,

mimicking a form of chromatic aberration within the glow.

### Color and Composite

- Gain: Sets how bright the glow is.
- Gamma: Tunes the glow's spread and the way it falls off with distance.
- Saturation: Sets how strong the glow's color is.
- Color Filter: A color picker and eyedropper let you select a hue to tint the glow with.
- Glow framing: Lets you decide what occurs when shine reaches the frame's edge, whether it gets

boosted by “Reflect in Camera” or tempered by a “Vignette” effect.

- Composite Type: Lets you select which composite mode blends the glow over the

picture. The default is Screen, well suited to soft glows. Add produces hotter, more intense glows, and the remaining composite modes open up other varied looks.

- Opacity: Lets you set how transparent the glow is, giving a quick way to “ease off” a glow you like overall but that runs too strong for the shot in hand.
- Invert Effect: Ticking this box reverses the Glow parameters, so now the darker regions drive the brighter ones rather than the reverse.
- Bright Region Recovery: Move this slider to win back some image detail in spots the glow has blown out.

### Secondary Glow

In effect, this is a glow layered onto your glow. It lets the inner and outer glows carry distinct colors within a single glow effect. Take a red neon sign on a blue wall: you could give it a vivid red inner glow paired with a blue-tinted secondary outer glow. That outer glow picks up more of the surroundings, as if a brighter blue wall were lit by the sign, while the inner glow stays vivid red, echoing the neon tube's own color.

- Add Secondary Glow: Tick this box to switch the Secondary Glow effect on or off.
- Gain: How bright the secondary glow appears.
- Spread: How far the secondary glow reaches outward.
- Color Filter: The color of the Glow Halo.

### Atmosphere

- Add Atmosphere: Tick this box to switch the Atmosphere effect on or off.
- Strength: Governs how much the light patterns vary.
- Detail: Governs the relative fineness of that variation; lower settings yield finer detail and higher

settings yield coarser detail.

- Scale: Governs how large the noise pattern is.
- H vs. V Ratio: Governs the horizontal-versus-vertical proportion of the variations' spread.
- Evolution: How far the noise pattern should shift.
- Seethe: How much it should evolve on its own at each frame from the outset

### Lens Flare (Studio Version Only)

Recreates a variety of lens flares produced as light passes through an aperture of your chosen shape and ricochets among the stacked optical elements inside a lens. Four sets of controls hand you plenty of room to tailor the presets into an effect of your own:

### Select Output

The Select Output dropdown lets you toggle between these viewing modes:

- Flare Alone: Displays the flare on its own, which makes adjustment easier.
- Final Result: (Default) Displays the lens flare composited over the current clip.

### Lens Flare Preset

Pick a flare style from the Lens Flare Preset drop-down. Once you tweak the controls to build an effect of your own, this drop-down flips to Custom.

### Light Source Masking

Three extra controls up top let you build a quick-and-dirty luma key, producing a mask you can use to hide the lens flare behind foreground objects in the scene. Say you're applying a lens flare to stand in for the sun crossing behind trees: these controls let those tree silhouettes shift and reshape the flare source to suit.

- Enable Light Source Masking: This checkbox turns on the Mask Threshold and Virtual Light Source Size sliders. From there you can pick either Source Mask or Magnified Source Mask to view the mask that raising the Mask Threshold slider generates.
- Mask Threshold: Pushing this slider up draws a fast Luma Key that hides darker foreground objects (trees set against the horizon, for instance) and keeps the flare to picture regions where the flaring light source can “shine through” (here, shining between the trees on the horizon).
- Virtual Light Source Size: This slider sets how rapidly a flare's center vanishes behind the luma-keyed mask you've built; larger values (standing in for bigger light sources) make a flare fade more gradually as it travels “behind” an image feature that the Mask Threshold slider is keying out.

### Position

The Position parameters let you move the X and Y Position of the simulated source driving the flare. You have three avenues for repositioning the flare.

- You can Adjust the X and Y Position sliders.
- You can enable the OpenFX Overlay in the Viewer and drag the on-screen control.
- You can motion track scene elements with the FX Tracker.

Ticking the Move With Sizing checkbox keeps the lens flare's relative spot in the frame even when the Input and Editing sizing change.

### Global Corrections

The Global Corrections group holds parameters for swiftly tuning the flare effect's overall look.

- Global Scaling: Lets you scale every part of the flare effect up or down together.
- Anamorphism: Lets you stretch all flare elements sideways to mimic the stretch of an anamorphic

lens.

- Lens Center X and Y position: Lets you shift the center of the simulated lens producing the

flaring, the point around which the flare's various parts pivot.

- Global Defocus: Lets you blur the whole flaring effect to soften it.
- Global Brightness: Lets you push the overall amount of flaring up or down.
- Global Saturation: Lets you tune the overall color strength of the flaring.
- Colorise Result: Lets you decide the degree of flare tinting, or none. With this left at its 0 default, zero

colorization happens whatsoever.

- Colorization Color: Lets you pick a color for tinting the flare through the Colorize Result

slider above. Either a color control or an eyedropper works for sampling color from the current node's source RGB image.

### Aperture

The Aperture parameters let you specify the aperture of the simulated camera rig that the flare passes through. The shape these parameters set shapes the look of each flare's “starburst element,” along with that of any aperture-shaped “ghost elements” you switch on.

- Aperture Blades: Sets how many blades the aperture contains. You can choose from 3 to 16 (defaults to 6). Lens flare diffraction is symmetric, so an odd blade count yields twice as many rays as there are blades, whereas an even count gives you a ray count equal to the blades.
- Angle: Sets the angle of the resulting Aperture shape.

### Elements

The Elements drop-down looks deceptively simple, yet it surfaces the customization controls for every layer and element that together build the simulated lens flare. As many as ten tiers of elements can feed into a single lens flare effect. Every element and ghost shape carries its own parameter set unique to that element type. The elements offered in this pop-up menu include:

- Full-Screen Glare: A simulated overall flaring that, at full strength, blankets the whole frame. The glare grows as the flare approaches screen center and shrinks as it heads toward the frame's edges. Suited to extremely large flaring effects. Parameters include:

Glare Brightness: A slider; drop it to 0 and the glare vanishes. Glare Color: A paired color picker and eyedropper for tinting the glare.

- Flare Spot: Stands in for the central light source setting off the flare. Its parameters are Flare Size (zero it out to remove the flare spot), Flare Irregularity (for a more organic, lopsided flare), Flare Softness, and Flare Color.
- Starburst: Beams of light radiating from the flare's center. Its parameters are Starburst Size (zero it out to remove the starburst), Starburst Softness, Starburst Split Angle (which fans each starburst streak into a broader feathered shape), Starburst Split Balance (for balancing brightness across the two halves of split streaks), and Starburst Color.
- Ghost elements: Up to seven Ghost Elements layers can be switched on and assigned different optional shapes for each lens element you wish to model. Any of these Ghost element layers may adopt one of five shape types, namely:

None: Switches off that specific ghost element. Aperture Shape: A polygonal form set by how many blades your chosen aperture has. Anamorphic Streak: A broad horizontal artifact typical of the anamorphic lens. Disc Shape: A circular ring-shaped artifact. Bubble Shape: An oval with haze trapped inside. Corona Rays: An outward-radiating ring of streaks. While many parameters are shared across ghost elements, individual ones contribute extras of their own. Here is that parameter list: Color: A paired color picker plus eyedropper for tinting that particular element. Position: A slider places the element along the optical path running at the angle that the (Flare) Position X and Y form together with the Lens Center X and Y parameters. Set to 0, the element sits on the Lens Position; raise it and the element drifts progressively away from the Lens Position. Size: Governs how big that flaring element is, or, for an Anamorphic Streak, how wide. Height: (Anamorphic Streak only) Governs the streak's vertical thickness. Center Brightness: (Aperture, Disk, and Anamorphic Streak only) Governs the brightness at the element's core, filling it so it reads solid. Push it toward 0 when you want a hollow-looking element. Edge Brightness: (All but Anamorphic Streak) Governs the brightness along the element's edge. Lifting this while dropping the Center Brightness lets you build outlined element looks.
