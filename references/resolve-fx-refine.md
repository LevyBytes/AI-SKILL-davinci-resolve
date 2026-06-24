# Resolve Fx Refine (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Resolve FX Refine

With these plugins you can carry out various sorts of focused enhancements.

### Beauty (Studio Version Only)

Beauty is a plugin built for governing texture. Within Ultra Beauty mode, you can selectively soften image detail above a set threshold while keeping detail that sits below a set threshold. That lets you smooth away the larger textures you'd rather not have, all while either keeping or even amplifying the smaller textures you do want. For faces and skin, the plugin offers an additional way to smooth out larger, unwanted blemishes while holding onto the edge detail and underlying structures like pores that you'd want to keep, letting you improve a subject's complexion on shoots that lacked hair and makeup, without over-softening genuine skin detail into an overly fake plastic look.

(Left) The original image, (Right) A face where Beauty has softened the complexion yet held onto fine facial detail Keep in mind that this plugin serves more than skin detail, and it does more than soften. After you've isolated the fine detail you'd like to keep in a subject, you can instead amplify it for heavily textured results. The plugin works well on any subject whose textures call for refinement. TIP: It's best run inside a qualification that isolates the specific feature you mean to smooth. Its default settings deliver a moderate degree of smoothing and fine detail recovery suited to faces in closeup, yet they won't fit every situation, so some fine-tuning is always required. For naturalistic outcomes, this plugin gives its best when applied with restraint.

### Operating Mode

The Beauty plugin offers three operating modes: an Automatic mode whose simpler operation suits you when the goal is the smoothest or most textured result possible while still keeping key details, an Advanced mode for those wanting finer control, and an Ultra Beauty mode that adds further controls letting you hold onto the fine detail you want while smoothing away the coarse details you don't.

### Automatic

Automatic mode surfaces straightforward controls for smoothing or coarsening detail.

- Amount: Lets you set how much smoothing or coarsening gets applied.
- Scale: Lets you dial down or up the degree of smoothing or coarsening reached

through the Amount slider's range.

### Advanced

Advanced mode brings out additional manual controls for smoothing or coarsening detail, without Ultra Beauty mode's complexity.

- Show Split View: Ticking this box places a four-up display in the Viewer presenting the Smoothing, Texture Recovery, Feature Recovery, and Final Output outputs in turn. It's handy to keep open while tuning the advanced options below.

The Advanced Beauty mode's Split View, which presents the Smoothing view (top left) alongside Texture Recovery (top right), then Feature Recovery (bottom left) plus Final Output (bottom right).

### Smoothing

With these parameters you strip out imperfections. Two smoothing controls are yours to adjust. Push them hard enough to wipe out every detail you mean to smooth away. Whatever harm over-smoothing causes gets undone in Texture and Feature Recovery.

- Smoothing Threshold: Move this slider to set how much image detail is kept.
- Diffuse Lighting: Tunes how much detail lands in the mid-tones.
- Preview Smoothed: Displays only the smoothing operation's result in the Viewer.

### Texture Recovery

Through these parameters you bring back patches of fine texture from the source video across flat areas set apart from the edges.

- Texture Threshold: Move this slider to set how much fine texture in the image is kept.
- Add Texture: Raises or lowers the scale of the texture within the Texture Threshold. Positive

figures add texture, whereas negative figures take it away.

- Preview Texture: Displays only the Texture Recovery operation's result in the Viewer.

### Feature Recovery

These parameters let you decide how much of the recoverable Smoothing and Textures gets brought back into the image.

- Recovery Amount: Move this slider to set how much of the detail you've isolated (shown white on the Feature Recovery view) returns to the image.
- Preview Recovery Areas: Displays only the Feature Recovery operation's result in the Viewer.

### Ultra Beauty

The Ultra Beauty controls unlock the Beauty plugin's full strength, supplying preview modes for inspecting various facets of how the plugin behaves, all while you specifically set the degree of smoothing or coarsening you want, how much texture to keep, and which further features of the subject you want recovered from this operation to fine-tune the outcome.

### Smoothing

With these parameters you strip out imperfections. Two smoothing methods are on offer to pick from. Push these controls hard enough to wipe out every detail meant to be smoothed away. Any harm from over-smoothing gets undone in Detail Recovery. To gauge the smoothing on its own, lower the Detail Recovery strength and texture down to zero.

- Flatten: Cuts texture and screens out detail. Strength: How much smoothing effect lands on the image. Levels: Governs how strongly the image is abstracted toward smooth levels. Quality: Governs how sharp the resulting effect is, Full being sharpest and Fastest blurriest.
- Filter: Flattens the image's smooth areas, leaving edges only where they separate one flat region from another. Strength: How much smoothing effect lands on the image. Filter Radius: Governs which scale of details gets filtered. Edge Threshold: Governs the level at which an edge is kept or smoothed over. A low threshold holds onto even faint edges, while a high one smooths over a growing number of edges unless they're very high contrast.

### Detail Recovery

These parameters let you bring back the parts of the source video surrounding the image edges, returning detail to the image.

- Strength: Sets how much detail is recovered.
- Width: Governs how far out on each side of the edges image detail is recovered.
- Gamma: Governs whether every edge is recovered or only the stronger ones. A higher gamma trims down the number of edges recovered.
- Blur: Softens the edge map where detail is due to be recovered.
- Preview Edges/Details: Tick this checkbox to reveal the areas where image detail is set

to be recovered; that lets you watch firsthand how the section's other controls bear on the image.

- Preview Recovery: Tick this checkbox to reveal the actual detail under recovery on its own against a neutral gray background.

### Texture Recovery

Through these parameters you bring back stretches of fine texture from the source video across flat areas held apart from the edges.

- Texture: Sets how much recovered texture is restored.
- Scale: Lets you fix a threshold beneath which texture is pulled from the source image and

laid onto the result.

- Detail/Edge Balance: Lets you tilt the recovery toward all textures (a negative value), or solely toward

stronger details such as edges (a positive value).

- Preview Texture: Tick this checkbox to reveal the actual texture under recovery on its own against a

neutral gray background.

### Grain

These parameters let you lay grain over the image to mimic detail in video areas carrying poor texture or none at all. Grain shows up only in smooth areas and steers clear of the recovered edges.

- Strength: Governs how much grain is added to the image.
- Size: Governs how big the individual grains are.
- Softness: Softens the grain texture.
- Saturation: Applies saturation to the grain.

### Custom Mixer

Think of the Custom Mixer as a more capable take on the Layer node. It accepts two inputs and merges them according to the second input's Alpha channel. Its controls let you mix sources, blend effects, and interpolate among grades with per-channel command and mixing options. You can wield this tool in numerous ways to govern the relative intensity between the sources, or just as a stand-in for the Layer Node but driven by sliders. Add the Custom Mixer straight into the node graph rather than dropping it on top of a Corrector node. To bring the Custom Mixer into your Node Graph, drag its icon out of the Effects library's Resolve FX Refine section right into the Node Graph. You may also drop it onto an existing link in the Node Graph to set it inline. Here's how the Custom Mixer node gets wired. The first and second RGB (Green) inputs serve as input 1 and input 2 in turn. The alpha of the second input drives the blend of input 2 onto input 1. The 1st input's Alpha leaves the result alone; it travels through the node to the output key.

How the Custom Mixer Node connects: Input 1 sits at the Green triangle above, with Input 2 at the Green triangle below. Input 2's alpha drives the blend of Input 2 over Input 1 and is the value you adjust within the Custom Mixer controls.

The Custom Mixer carries two principal modes selected via the Mix mode; both act the same way, differing only in the controls used to alter how the input shapes the output.

### Blend

Blends the second input over the first. Its usual range runs from 0 (entirely input 1) to 1 (entirely input 2), yet you can push the blend factor as much as 10 times higher or lower by typing values straight into the fields. That lets you heighten the contrast between inputs past what either looks like alone. Every slider can be keyframed on its own.

- Blend Input 2 onto 1: Governs each source's strength, drawing on the color channels of the chosen color space (RGB, YUV, XYZ, etc.). With the Gang checkbox cleared, these are adjustable one by one.
- Gang: Tick this box to gang the custom mixer's channels together, or clear it to adjust them separately.

### Combine

Merges the inputs together, letting you shift how strongly each input contributes to the mix. The usual range spans 0 (entirely input 1) to 1 (entirely input 2), though you can drive the blend factor as much as 10 times more or less by entering values straight into the fields. That lets you amplify the contrast between inputs past how either appears on its own. Each slider keyframes independently.

- Input 1 Contribution: Governs input 1's source strength, drawing on the color channels of the chosen color space (RGB, YUV, XYZ, etc.). These adjust individually when the Gang checkbox is cleared.
- Input 2 Contribution: Governs input 2's source strength, drawing on the color channels of the chosen color space (RGB, YUV, XYZ, etc.). These adjust individually when the Gang checkbox is cleared.
- Offset: Governs the combination's offset, drawing on the color channels of the chosen color space (RGB, YUV, XYZ, etc.). These adjust individually when the Gang checkbox is cleared.
- Gang: Tick this box to gang the custom mixer's channels together, or clear it to adjust them separately.

### Advanced Options

Sets the composite type along with the resulting mix's color space and gamma.

- Composite Type: Picks, from the drop-down menu, the composite type the mixer uses.
- Color Space: Picks the Color Space applied to the blend. It defaults to the current

Timeline color space.

- Gamma: Picks the Gamma applied to the blend. It defaults to the current Timeline color space.

In the Custom Mixer's starting setup, Node 1 holds the original image while Node 2 is the same but with a Noise Reduction effect on it. In the Custom Mixer's final setup, raising the blend factor by 7 has the mixer add noise to the image instead. For that example, applying the Noise Reduction FX to Node 2 and wiring the identical image from Node 1 straight into the Custom Mixer leaves the noise pattern from the effect itself as the inputs' sole difference. Manually pushing the blend above 1 mixes in more noise than you began with. Thus, pairing Noise Reduction with the Custom Mixer lets you genuinely heap extra noise onto an image that exactly matches the original grain pattern, with no need to hunt down a comparable external grain or noise source.

### Depth Map (Studio Version Only)

NOTE: The Depth Map Resolve FX has seen sizable behind-the-scenes improvement and an update from DaVinci Resolve 20 onward. Its interface and usage stay as they were, yet you should get markedly more precise results out of the tool. The fresh Depth Map v2 has taken the original's place and gets applied automatically whenever you use the Depth Map effect. Depth Map builds an Alpha channel from how far away the objects in your clip appear. Being able to single out a particular depth region greatly widens what you can do to the resulting image. As one example, teamed with a Fast-Noise plugin you could fake a fog effect kept solely to the far background of your shot. You could lift a foreground object such as a person by raising contrast, saturation, and sharpness, much as a qualifier would. A Depth Map can mend video troubles too — say, correcting a color temperature issue by isolating a distant window shot in daylight that tinted background actors blue, while sparing the foreground subject lit by studio lighting. Depth Map can additionally pair with DaVinci Resolve's other windows and keying tools to assemble more elaborate rotoscoping and keys with less work. The resulting Depth Map Alpha channel is shown as a black-and-white image, white marking the area the changes affect and black areas staying untouched.

(Top) The original image. (Bottom) The scene's Depth Map v2 analysis; white marking areas "closer" to the camera and black marking those farther off

### Main Controls

These controls establish the Depth Map's chief parameters.

- Quality: Depth Map is a heavily computational effect. The quality setting offers a Faster mode that quickens how responsively adjustments register, whereas the default Better mode yields the best results and ought to be on once the adjustments are done.
- Depth Map Preview: This box is ticked by default and presents the current Depth Map for your adjustments. Switch it off and the resulting alpha becomes usable for grading on other nodes. Should you have applied the effect to a corrector node, be sure to right-click the Depth Map's node and choose "Use OFX Alpha" so the node passes the effect's Alpha channel correctly.
- Invert: Ticking this box flips the Depth Map, swapping its transparent and opaque regions.

### Resulting Map Adjustment

These controls let you decide how the Depth Map's contrast gets adjusted.

- Adjust Map Levels: Left off (the default), DaVinci Resolve's grading tools (lift, gamma, gain, etc.) can work the Depth Map's whole range. Switched on, this option clips the Depth Map's levels to 0 and 1, serving as a preview of what becomes of the Depth Map once it's used as an Alpha channel, where DaVinci Resolve always clips the values to 0 and 1.
- Far Limit: This control tunes the Depth Map's black levels.
- Near Limit: This control tunes the Depth Map's white levels.
- Gamma: This control nudges the in-between depth values brighter or dimmer relative to

the fixed black and white levels.

### Isolate Specific Depth

These controls let you glide back and forth through the scene by depth, so you can isolate a particular depth range to adjust.

- Isolation: This checkbox switches the depth isolation tools on or off.
- Target Depth: This sets the exact depth you want isolated. 1 sits fully in the foreground,

whereas 0 sits fully in the background.

- Tolerance: Fixes how much range on each side of the Target Depth is folded into the Depth Map.
- Softness: This adds a gentle ramp-in and ramp-out to the chosen range, lending it a more

organic selection.

### Map Finesse

These controls reshape the resulting Depth Map's Alpha channel so it's ready for grading.

- Post Processing: This control switches the Map Finesse tools on or off.
- Post Filter: Smooths the depth map along the image contours.
- Contract/Expand: This control swells or shrinks the overall shape at its edges, handy for fine-

tuning the border between the map's affected and unaffected regions.

- Blur: This control softens the map's border so it blends more smoothly into the

resulting image.

### Advanced Options

These controls instruct the Depth Map on how to deal with assorted blanking issues.

- Blanking Regions: These controls instruct the Depth Map on handling letter and pillar boxing regions within the effect. Process Entire Frame: Has the AI disregard any data about the timeline shape and simply process every visible pixel. Handle Automatically (default): The AI processes only the area DaVinci Resolve recognizes as holding your media. Auto + Extra Crop: Advised for trimming away black bars; it leans on DaVinci Resolve's awareness of which pixels your media filled while letting you crop out the framing or letterboxing relative to its shape. It's advised because it holds steady as you tweak Timeline settings. Manual Cropping: Simply lets you override whatever the content's framing is, disregarding any of DaVinci Resolve's awareness of your media's shape.

As an example, suppose you have footage of a person filmed on a rainy day, but the background is overly distracting and contrasty. Building a depth map that isolates only the foreground person lets us then put a Fast Noise smoke effect on the background alone, giving it a foggy-mist look that's less of a distraction.

### The original footage with a distracting background

That same footage with a Fast Noise Smoke effect node faking a fine mist, except it blankets the whole frame, the main subject included. For realism, the mist belongs in the background alone.

Dropping a node carrying Depth Map between the original nodes lets you use the effect to pull a key based purely on "distance" from the camera. Here we've picked the background (white) and ruled out the woman with the umbrella (black). Notice the fine detail in the furry coat, which an HSL or window qualifier would struggle to capture.

The process's end result shows the main subject up front with the Fast Noise smoke effect held to the background only. TIP: For more convincing Depth of Field adjustments, run the Depth Map effect alongside the Tilt-Shift Blur effect. You can route the Depth Map's results straight into the Tilt-Shift Blur effect as a blur map by joining the Depth Map node's key output to the Tilt-Shift Blur node's key input and choosing "From Alpha In" from the Map Source drop-down within the effect's Depth of Field section. From there, tune the Focus Sweep to home in on the area you want isolated. If the results aren't what you expected, try inverting the Depth Map.

### Face Refinement (Studio Version Only)

The Face Refinement effect now boasts better tracking, profile handling, and smooth skin options. The freshly revised effect is laid out below. Face Refinement is a remarkably sophisticated yet approachable filter that lets you rapidly make highly targeted tweaks to people's complexions. To put the face refinement toolset to work, your first job is to identify the face (or faces) you intend to work on, then analyze and track that face across the clip. You identify a face by clicking the Detect Faces in Frame button. When faces sit in the frame at the playhead's position, the result is boxes drawn over each detectable face. Click any of those boxes to pick the face you want to refine, and that box highlights green to show which face you'll be refining.

With several faces detected, you can click a box to pick the one to work on. Having chosen the face to work on, you then use the tracking controls to track it across the clip, and an outline of the face's main features shows up so you can follow along.

### The Face Refinement filter detecting a performer’s face

In most cases the basic tracking controls do a good enough job of tracking faces. In trickier situations, though — when the subject's head tilts away or something else in the frame blocks it — you might have to adjust the track by hand. Do that by jumping to the track's last reliable point and ticking the Interpolate (Keyframed) box. That drops keyframes automatically for the frame and turns the outlines blue to signal you're in manual mode. You can then move to the troublesome frames and click and drag to adjust the whole face by hand, or pick and adjust each separate feature as needed. As soon as you reach a point where automatic tracking holds up again, just clear the Interpolate box and hand it back to the automatic tracker.

Adjusting an eyebrow by hand in the Interpolate (Keyframed) mode With the face tracked, you're set to work. This plugin carves the tracked face into separate zones for the routine operations colorists frequently carry out — rapidly clearing blemishes, adjusting complexion hue and saturation in regionally fitting ways, reshaping lighting, sharpening worthwhile detail, and refining makeup. Since each adjustment conforms to the proportions of the detected and tracked face, your only task is making whatever adjustments you need, and DaVinci Resolve handles the rest.

### Main Controls

The top controls let you kick off the Face Refinement process.

### The tracking controls for Face Refinement

- Detect Faces in Frame: This button sets off the process of having the Face Refinement plugin's facial detection spot any faces in the frame. Be sure to land on a frame that plainly shows the face you mean to adjust. What can trip up the Detect Faces in Frame is a face that's upside-down, partly hidden, or lit oddly.

TIP: Pick a face box and it doubles as a selection box you can shift-click-drag. Doing so hunts the box for face points. On a tricky frame, nudging this around a bit often forces the detections to where you want them. When it lands, it's the quickest way to steer the Detect Faces in Frame toward a good result.

- Tracking Controls: Basic tracking controls for following facial features' motion across the clip Track Reverse: Pins down the face and tracks it backward across the clip. Track Reverse 1 Frame: Pins down the face and tracks it back 1 frame.

Find in Frame: Pins down the face in the current frame. Track Forward then Reverse: Pins down the face, then tracks it forward from the current spot and afterward in reverse from that spot. Track Forward 1 Frame: Pins down the face and tracks it ahead 1 frame. Track Forward: Pins down the face and tracks it forward across the clip.

- Show overlay: To wow your clients and judge how well Face Detection is tracking the face you're on, switch on this checkbox, which enables the wireframe tracking that reveals which facial details are being detected.

### Face Location

These controls let you set the effect's strength and also make manual tweaks to where the face and its features sit in the frame.

- Effect Strength: This slider sets the relative strength of the adjustments against the original image. 1.000 is full strength, while 0 shuts the effect off entirely.
- Interpolate (Keyframed): Ticking this box lets you hand-adjust the face and feature tracking in the Viewer and keyframes any changes for you. Click and drag in the Viewer to shift the whole face. Shift-click and drag to reframe the face. Click any single feature to adjust it, or any dot to relocate its position.

### Skin Isolation

These controls let you tweak the skin mask the plugin builds automatically so the effect stays confined to just the face of the person you're after.

### Adjusting the key with the face mask active
