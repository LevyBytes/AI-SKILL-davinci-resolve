# Resolve Fx Refine (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Show mask: Ticking this checkbox displays the face mask as it's built, which is handy to watch while you fine-tune it.
- Skin Mask Source: Picks the origin for the skin mask. The default is DaVinci Resolve’s Internal Skin Model, though you may instead draw on the Input Alpha when you've keyed the skin tones in a separate node. None switches the mask off.
- Shadow Range: With this control you can grow or shrink the facial shadows the skin model has detected.
- Tint Range: With this control you can grow or shrink the tint range the skin model has detected.
- Temp Range: With this control you can grow or shrink the color temperature of the face picked up by

the skin model.

- Limit to Face Region: Switching on this checkbox lays down a circular garbage mask that tracks the

face so stray qualification of regions outside the face is removed.

- Region Size: Lets you tune the size of the face mask.
- Region Softness: Lets you tune the edge softness of the face mask.
- Flat Skin Areas Only: Ticking this box leaves the nose and eye-socket regions out of the

mask, so you operate only on the facial skin itself.

- Exclude Mouth: Ticking this box leaves the mouth region out of the mask, so you can

work only on the facial skin itself and not the lips.

- Denoise mask: With this slider you fill in spots of fine detail across the mask.
- Refine mask: With this slider you tweak the face mask to smooth over or close gaps in the key.

### Skin Texture

Three operating modes sit under the Skin Texture controls, letting you pick the approach you'd like for governing skin texture. Beauty Automatic and Beauty Advanced supply the texture controls from the Beauty plugin, whereas Smoothing supplies the texture adjustment controls that were available previously.

### Beauty Automatic Controls

Automatic mode surfaces simple controls for smoothing detail or making it coarser.

- Amount: Lets you set how much smoothing or coarsening gets applied.
- Scale: Lets you dial down or up the amount of smoothing or coarsening that's achieved

across the span of the Amount slider.

### Smoothing Controls

- Smoothing: This slider strips detail from the regions singled out by the Skin Mask controls, smoothing the complexion. How it behaves hinges on where the Detail Size and Detail sliders beneath it are set. You may find that Smoothing can go much further as you push Detail up via the Detail Size and Detail sliders covered below.
- Detail Size and Detail: After working the Smoothing slider, these sliders let you selectively reintroduce subtle skin details into the image; Detail Size sets the largest detail size you want returned to the face, and Detail is a sharpening operation that controls how visible these small details become. Pairing smoothing with a gentle preservation of small details yields a far more lifelike result than leaving the whole face unnaturally smooth.

(Left) The original image, (Right) Only smoothing complexion,

Applying Detail Size and Detail to restore lifelike texture across the smoothed output (effect overstated for print) Beauty Advanced These controls are the same as the Advanced controls in the Beauty plugin, addressed earlier in this chapter.

### Skin Grading

With these controls you can make color tweaks to the whole face.

- Contrast: This slider lets you brighten the face naturally by holding the shadows dark even as you lift the face, which makes it simple to lift actors clear of the background.
- Midtone: Lets you give the skin tone a more luminous quality.
- Color boost: Targets saturation specifically in the least-saturated portions of the face.
- Tint: Offers a narrow band of natural hues leaning on orange through red (yet reaching

to green and magenta) for adjusting complexion.

- Desaturate shadow: This slider lets you selectively pull saturation out of the darkest facial shadows

to keep things looking natural, or to strip saturation harder to stylize the face another way. It also helps when the plugin's other adjustments leave the shadows too colorful. Pushing this slider into negative values instead adds saturation.

- Shine Removal: This slider acts as an inverse contrast adjustment meant to tone down sweat and shine on someone's face, though pushing this slider into negative values will instead emphasize shine.

### Side Lighting

These controls let you fill or boost shadows and even out the light across the two sides of the face.

- Lift Left/Right: Tweaks the dark portions of the image for one side of the face.
- Gamma Left/Right: Tweaks the midtone portions of the image for one side of the face.
- Gain Left/Right: Tweaks the bright portions of the image for one side of the face.
- Area Size: With this control you set the size of the side lighting's region of influence.
- Bias Left/Right: By default the face's left and right sides are divided straight down the nose. You can

reach for this control to shift the effect's center by hand when needed.

- Area Softness: This control sets the softness of the effect around the side of the face.

### Eye Shadow

These controls offer broad command of the eyelids and sockets, without touching the eyes themselves. Applied gently, it readily takes away under-eye bags or plays up makeup details. Applied heavily, you can build convincing eye makeup effects from scratch. The upper and lower eyelid areas have their own separate controls.

- Temp Upper/Lower: Tweaks the eyelid's color temperature.
- Tint Upper/Lower: Tweaks the eyelid's tint.
- Hue Upper/Lower: Tweaks the eyelid's color.
- Saturation Upper/Lower: Tweaks the eyelid's saturation.
- Gamma Upper/Lower: Tweaks the eyelid's gamma.
- Size Upper/Lower: Tweaks the size of the region where the eyelid changes apply.
- Softness Upper/Lower: Tweaks how softly the eyelids blend into the face.
- Strength Left/Right: Lets you assign separate strengths to the left or right eye to make up for

lighting differences across the sides of the face. (Left) the original image; (Right) the Eyeshadow tools applied to recolor the model's upper eyeshadow to purple and push up its intensity

### Eye

These controls focus solely on the eyes and the face area around them.

- Sharpening: This slider lets you add sharpening selectively to just the eyes and lashes, so you can instantly draw focus to any performer.
- Brightening: This slider lets you whiten the eyeballs.
- Eye Light: This slider lets you lift the part of the face around the eyes that often falls into shadow beneath the subject's forehead when the lighting is poorly placed.
- Eyebag Removal: This slider applies an assortment of methods to smooth, color-correct, and brighten the under-eye area most prone to bags on tired talent.

### Lips

These controls focus solely on the lips and the mouth area around them.

- Hue Shift: This slider lets you change the color of a subject's lips or lipstick.
- Saturation: This slider lets you change how intense the lip color is.
- Gamma: This slider lets you change the lip brightness via a gamma curve.
- Upper Lip Smooth: Lets you ease the fine age lines that can show up over the lips.
- Mouth Corners Inner/Outer: Tweaks the side corners of the mouth.
- Top Inner/Outer: Tweaks the upper boundary of the lips.
- Bottom Inner/Outer: Tweaks the lower boundary of the lips.
- Softness: How softly the mouth area blends with the rest of the face.

### Teeth

A grin can mask plenty, but these three controls alone can play up the teeth.

- Blue Gain: This control color-balances the teeth, making them whiter or yellower however you like.
- Gamma: This drives a gamma curve so you can set how bright the subject's smile reads.
- Mask Softness: How softly the teeth blend with the rest of the face.

### Blush

The parameters in this cluster let you shift the hue of the blush area on a subject's cheek, so you can repair a poor makeup choice, or shift a subject's blush color to introduce makeup that wasn't originally present.

- Hue: This slider lets you tweak the hue of the cheeks.
- Saturation: This slider then lets you boost or strip away blush color.
- Size: This slider lets you tweak the size of the cheeks' blush area.

### About Forehead, Cheeks, and Chin Retouching

The next three control clusters lift a trick from portrait painters, who've long leaned on the “traffic light” method of rendering skin hues — noting that foreheads tend toward a touch of yellow, the face's middle usually a touch of red, and chins a touch of green. This stems from a mix of uneven sun exposure, capillary spread, and follicle growth, but the upshot is that faces are rarely one uniform hue. So a portion of the face may benefit from its own adjustment (cheeks that caught too much sun, say). It also means that letting a little hue variation into your face grade can produce a more lifelike result.

(Left) a face graded under one hue; (Right) a face graded with subtle hue shifts across the forehead, blush region, and chin TIP: For all sorts of reasons people are remarkably sensitive to skin-tone hues, so even tiny shifts that are hard to spot still carry a real impact on the final visuals. Barring a deliberate special effect, these controls are intended for restrained use.

### Forehead

True to its name, this adjusts color and texture across the forehead.

- Hue and Saturation: These sliders let you tweak the forehead's color.
- Gamma: This drives a gamma curve so you can set how bright the forehead reads.
- Smooth: This slider lets you apply a dedicated smoothing pass to the forehead to soften wrinkles and worry lines.

### Cheeks

Plain color-adjustment controls covering the whole cheek area, not merely the blush area.

- Hue and Saturation: These sliders let you tweak the color of the cheek, eye, and nose area.

### Chin

Plain color-adjustment controls covering the face's chin.

- Hue and Saturation: These sliders let you tweak the color of the chin, extending up along the sides of the face (the beard area).

### Grain

At times the Skin Smoothing controls leave the skin pleasingly smooth, yet they also strip out the video clip's natural grain by accident, giving it an artificial look. The Grain toolset lets you reintroduce that grain pattern to match the shot's original overall grain. Grain touches only the smoothed regions inside the Face Refinement plugin, so it's already prequalified on your behalf.

- Add Grain to Skin Areas: Tick this box to switch the Grain effect on or off.
- Strength: Sets how much grain gets added.
- Size: Sets the grain's size.
- Softness: Sets how crisp or blurred the grain pattern is.
- Saturation: Sets how colorful the grains are.

TIP: Every parameter above can be keyframed by hand should the automatic tracking fail to lock on, by clicking their keyframe icons in the Inspector. As an example, if you locate a face at frame 10 and once more at 50, Face refinement will interpolate across those moments. Should you manually shift the mouth down at frame 50, then frames 11-49 will adjust to suit.

### Relight (Studio Version Only)

Relight lets you introduce light sources into your scene, lighting up the objects inside it realistically. Whereas a Power Window keeps a fixed on-screen shape, Relight studies the forms of people and objects to build a Surface Map, then uses that map to bounce light appropriately. Tuned well, the effect can sell the illusion of light tracing an object's contours, glinting off highlights, and fading into shadow. Relight comes in handy when you wish there'd been an extra light on set, want to play up an existing light to match another shot, or want to make day-for-night grading more believable. NOTE: The Relight effect manufactures the illusion of depth through its analysis of a scene's surfaces, but it does not work out the 3D relationships among the scene's objects. Shapes can't be set to cast shadows, and depth data can't be produced.

### Setting up Relight

Studying the image to build a Surface Map is extremely demanding on the processor. Working out how light sources affect an existing analysis is, by comparison, very quick. By default, dropping Relight onto a node both builds the map and adds a light in a single step. That's handy, but moving the light position re-runs the effect, and so re-runs the analysis. That can make it sluggish to work with unless you've got an

extremely powerful computer. Happily, the work can be divided across two nodes — caching the analysis in the first node while you tweak light positions in the second. The full procedure follows below. Bear in mind you can add several light sources off the same analysis. With, say, three distinct lights in one scene reusing a single analysis, this runs three times faster than redoing the analysis for every light. And as an advanced option, the split method lets you draw on a Surface Map saved to disk, or one coming from a different application. Such packages can often output the “surface normals” of 3D models next to the images they generate, and these can be made compatible with Relight. Here a “normal” is a geometric term that describes the orientation of a surface. No single universal format exists for surface normals; check the External Map settings for some options that can assist with using these as Surface Maps in the plugin. Here's a sample node graph dividing the Relight across two stages: how to build a dual Relight Node Tree using two distinct Relight nodes, set up as shown. They've been named Surface Map and Lighting to keep things clear. In that example you've got the source video together with two Relight nodes. This is how they're connected:

- Feed the source video into the first RGB input (top green triangle) on both nodes.
- The first Relight Node ((RLT) Surface Map) builds the image's Surface Map when you

tick the “Output Surface Map” checkbox in the Relight effect's settings. Once ticked, the plugin shifts into analysis-only mode and the other options vanish. You can switch on Node Caching to build the Surface Map automatically in the background whenever you aren't using DaVinci Resolve. Route this node's RGB output into the second RGB input (bottom green triangle) on the second Relight Node.

- Over on the second Relight Node ((RLT) Lighting), switch the top option “Surface Map” away from its default of “Use Internal” over to “Use Input 2.” Every other setting stays on screen; this is the node where you'll dial in the light properties.

You can attach Power Windows, Qualifiers, or masks to either node, or to separate nodes joined via the first Alpha channel (top blue triangle) of either node. For instance, you could pick out a person with the magic mask and use it to confine the lighting to that person alone rather than the background.

The Relight Surface Map's output, which then feeds the input of the Relight Lighting node.

### Using Relight

The moment you first drop Relight onto a node and turn the lighting preview off, the image shows no visible change. That's because the map of what the light illuminates lives in the Alpha channel, primed for every one of DaVinci Resolve's color grading tools to act on. The easiest starting move is to raise Gain (boost it directly or add color); changes to gamma and saturation are often fitting too. For a day-for-night look you can invert the Alpha so a scene darkens everywhere except the lit areas, landing a day-for-night effect while the “light source” remains the original scene lighting.

### The Relight Settings

These controls let you set the strength, type, and direction of the light bouncing off the surface map. Most can be keyframed, and positions can be tied to the FX Tracker, enabling things like sliding a light source as though it were fixed to an object, or sweeping a spotlight to trail a person as they cross the scene. The controls and their groupings are:

- Surface Map: This picks the mode used to build the Surface Map. Use Internal: builds the Surface Map and applies it right away within this same node. Use Input 2: takes in the Surface Map handed over from a different Relight Node. Apply this on the second node when you've set up a dual Relight Node arrangement.
- Output Surface Map: Ticking this box makes this instance of the effect output a multi-colored map of the input frame. That Surface Map can next be routed into a second Relight effect (with “Use Input 2” chosen, per above), and there the light sources get placed and tuned.
- Directional/Point Source/Spotlight: Directional: makes a light source casting from one fixed direction at an infinite distance away. Point Source: makes a light source casting outward from a single central point. Spotlight: is likewise a point source, only focused down into a cone shape.
- Relighting Map Preview: Ticking this box exposes the Alpha channel of this light's effect. Unticking it shows the current image but with the light mask held in the Alpha channel.
- Diffuse Reflection Properties: These controls set the character of the emitted light. Brightness: This governs the strength of whatever grading is applied to the scene. On its own it adds no brightness changes; it amplifies the changes you make with the grading tools. Softness: This governs the size of the light emitter, in effect setting how harsh or gentle the gradient runs between light and dark. Distance Falloff: This governs how much reflections dim as distance from the light source grows.
- Light Properties: Brightness: This governs the strength of whatever grading is applied to the scene. On its own it adds no brightness changes; it amplifies the changes you make with the grading tools. Reach: This governs how much reflections dim with distance from the light source. Contrast: This sets how harsh or gentle the gradient runs between light and dark.
- Surface Properties: Glossiness: Lends reflective surfaces the illusion of a metallic sheen. Specularity: Whenever any glossiness is added, this governs how metallic and shiny that glossiness reads. Shadow Softness: Governs how far the light reaches into shadows from ambient reflections, past where it would otherwise land.
- Spotlight :(shown only with Spotlight option enabled) Beam Angle: Sets how wide the cone of light spreads. This control is also offered graphically in the Viewer. Edge Softness: Sets the softness along the edges of the light cone/beam.
- Light Position: These controls handle the position of the light emitter for every light type. They can be set directly, but more conveniently they can be set graphically in the Main Viewer. Make sure the Main Viewer's mode is set to Open FX Overlay using the icon at the lower left.

In Directional mode: Azimuth/Elevation XY : sets which direction the light arrives from. In Point and Spotlight modes: Source Follows FX Tracker: tick this box so the light source rides along with the FX tracker. Light Source XYZ: these controls fix where the light emitter sits in 3D space. In Spotlight mode: Spot Follows FX Tracker: tick this box so the light source trails the FX tracker. Spot Target XY: these controls fix where the base of the spotlight cone lands.

While in Use Input 2 mode, options appear for working with an externally generated Surface Map.

- Rescale Oversaturated: Various applications scale the Surface Map differently. One common format resembles the Relight plugin's own internal maps but with the colors heavily saturated, and it can run dark or black across some regions. If your imported surface map looks like that, tick this box to reinterpret it.
- Reinterpret Left/Right: Tick this box to flip the direction of your external surface map when its surfaces look concave rather than convex.
- Reinterpret Up/Down: Tick this box to flip the direction of your external surface map when its surfaces look lit from beneath while the light sits above them.

While you're producing an analysis internally with Use Internal, or using Output Surface Map, an Advanced Options group also appears holding an option tied to Blanking Regions. These won't matter in most cases; they exist only to fix certain particular situations. They serve to force different edge-of-frame behavior in these special cases:

- The source video carries letterboxing or some framing border that's been “baked in,” meaning the incoming frames hold black pixels at the edges that DaVinci Resolve didn't add. Letterboxing that DaVinci Resolve itself adds (say, a 21:9 frame fit into a 16:9 timeline) needs no special handling. You'll spot the trouble because the Surface Map AI treats the scene as though the black areas are genuine objects or stuck to objects in frame. Objects touching the black bars may seem to merge into those regions.
- The source video carries pillarboxing, just like the letterboxing above. As an example, a 4:3 source video captured into a 16:9 clip with black borders before it reached DaVinci Resolve.
- A case where a wide clip was placed into a narrower timeline correctly, but once resizing or effects were applied you want the plugin to process the original blanking areas because content now sits there. This case is obvious, since the analysis halts at the original blanking edge, cropping off areas you mean to analyze.

When you hit any of these special cases your options are:

- Blanking Regions:

Process Entire Frame: Tell the AI to disregard any data about the timeline shape and simply process every visible pixel. Handle Automatically (default): The AI processes only the region DaVinci Resolve knows holds your media. Auto + Extra Crop: This is recommended for cropping away black bars; it draws on DaVinci Resolve's knowledge of which pixels your media occupied while letting you crop out the framing or letterboxing relative to its shape. It's recommended because it stays consistent as you change timeline settings. Manual Cropping: Simply lets you override whatever the content's framing is, ignoring any of DaVinci Resolve's knowledge of your media's shape.

### The Relight On-Screen Controls

Several of the light-source positioning controls are offered graphically in the Viewer; be sure Open FX Overlay is chosen at the Viewer's lower left to see them.

While in Directional mode, dragging the emitter (red rays) about the frame sets the Azimuth/Elevation controls.

In the Point Source and Spotlight modes you can shift the emitter (red rays) to change the XY coordinates, and the circle to adjust the emitter's Z coordinates. While in Spotlight mode you can drag the X to change the Spot Target's XY coordinates, and scale the large circle to adjust the Cone Angle.

### Example

For this example, we'll relight the scene shown below. Filmed on a cloudy overcast day, the director is happy with the flat look on the building. Sadly, the dull muted lighting also hit the model, which he'd like to make pop more out of the scene. We'll turn to the Relight tool to drop a phantom sunbeam onto the model alone and onto none of the surrounding fence or walls.

The model's lighting reads flat and dull. We want to alter it by adding an artificial sunbeam landing on her that the shot didn't have. We also want to leave the fence and background untouched. The first tool we'll reach for is the Magic Mask to separate the model from her surroundings.

Separating the model via a Magic Mask to confine the effect Next we'll bring in two distinct relight nodes — one that builds the surface map, the other that receives it and does the actual relighting of the shot. The node tree gets explained below.
