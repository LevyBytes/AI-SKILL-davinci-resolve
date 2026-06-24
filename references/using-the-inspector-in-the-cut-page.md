# Using The Inspector In The Cut Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using the Inspector in the Cut Page

Every control needed to alter, rescale, retime, or otherwise tweak whatever clip, transition, or effect sits on the Cut page Timeline is gathered inside the Inspector.

### Using the Inspector

To make pinpointing a given control simpler and to streamline tweaking the settings you touch most, the Inspector got a fresh layout. Rather than one tall, scrolling column, its sections are now split into panels, each devoted to a related cluster of parameters for the clip at hand. Click the Inspector Panel near the top-right of the User Interface toolbar to turn it on. Its contents divide across separate Video, Audio, Effects, Transition, Image, and File panels. Any panel that has no bearing on the current clip or selection appears dimmed.

The Inspector Panel icon in the upper right of the UI toolbar

The Inspector panels with the Video, Audio, and File parameters open for tweaking; the rest sit dimmed. Ways to work the controls inside the Inspector:

- To activate or deactivate a control: Hit the toggle sitting to the left of the control’s name. An orange dot over on the right signals the control is on. A gray dot over on the left signals it is off.
- To reveal a control’s parameters: Double-click the control’s name.
- To reset controls to their defaults: Press the reset button found to the right of the control’s name.

### Video

A broad set of controls for reshaping the size, speed, and opacity of your clips lives on the Video panel of the Inspector.

### Transform

### The Transform section of the Video Inspector panel

For rescaling and relocating a clip, the Transform group offers these parameters:

- Zoom X and Y: Lets you scale the image larger or smaller. You can link the X and Y parameters to hold the image’s aspect ratio fixed, or unlink them to stretch or compress the image along a single axis only.
- Position X and Y: Shifts the image inside the frame so pan and scan moves can be made. X slides the image left or right, while Y slides it up or down.
- Rotation Angle: Rotates the image around the anchor point.
- Anchor Point X and Y: Sets the spot on that clip that every transform pivots around.
- Pitch: Spins the image toward or away from the lens around a horizontal axis through its middle, running left to right. With positive numbers the upper edge tilts back while the lower edge swings toward you; negative numbers do the reverse, pulling the top forward and pushing the bottom back. The bigger the value, the more pronounced the stretching becomes.
- Yaw: Spins the image toward or away from the lens around a vertical axis through its middle,

running top to bottom. Positive numbers swing the left edge toward you while the

right edge tilts back. Negative numbers tilt the left edge away and pull the right

side forward. Larger values exaggerate the stretch further.

- Flip Image: Two buttons let you flip the image in different dimensions.

Flip Horizontal control: Mirrors the image across the X-axis, swapping left and right.

Flip Vertical control: Mirrors the clip across the Y-axis, flipping it upside down.

Smart Reframe (Studio Version Only)

Within the Video Inspector panel, the Smart Reframe area holds a feature that speeds up the job of reframing footage when the aspect ratio shifts dramatically. It comes in handy whenever, say, you captured a 16:9 horizontal shot but now must deliver a vertical 9:16 cut for phones and social platforms, or you’re dropping 4:3 archival clips into a 2.39:1 widescreen film. You can run Smart Reframe by hand or have the DaVinci Resolve Neural Engine do it for you automatically.

- Object of Interest: Controls for picking the subject the resize will build its framing around. Auto: DaVinci Resolve’s Neural Engine studies the clip and settles on the object it finds most representative. When you’ve selected more than a single clip for Smart Reframing, this becomes the sole choice.

Reference Point: Lets you hand-tune a bounding box drawn around the subject you want to reframe around.

- Mode: Controls for confining the AI reframing to one specific axis. Auto: As it sees fit, Smart Reframe shifts a clip’s pan and tilt to reframe the target correctly.

Pan Only: Here Smart Reframe touches only the clip’s pan (left and right) movement. Tilt Only: Here Smart Reframe touches only the clip’s tilt (up and down) movement.

- Reframe: Pressing this button runs the Smart Reframe command. How long it takes depends on how many clips there are and how long they run.

### Cropping

### The Cropping section of the Video Inspector panel

The image’s cropping parameters are governed by the Video Inspector.

- Crop Left, Right, Top, and Bottom: Trims away, measured in pixels, any of the image’s four edges. Once a clip is cropped, transparency opens up there, letting anything below it become visible.
- Softness: Lets you blur the edges of a crop. A negative setting softens the

borders on the inside of the crop box, while a positive setting softens the borders

beyond the crop box.

- Retain Image Position: Tick this checkbox and the crop parameters stay pinned in place as you resize the image with the Transform tool above. Leave it unticked and the crop is scaled and repositioned right along with the image.

### Dynamic Zoom

Within the Video Inspector panel, the Dynamic Zoom area's controls, which start off turned off, give you a fast, easy way to do pan and scan moves that ease into or back out of a clip. Toggling the Dynamic Zoom group on brings up two Inspector controls that operate in tandem with the Dynamic Zoom onscreen adjustment controls. To read more about working with the Dynamic Zoom controls, refer to Chapter 50, “Compositing and Transforms in the Timeline.”

- Dynamic Zoom Ease: Sets the way the movement these controls produce ramps up. The choices are Linear, Ease In, Ease Out, and Ease In and Out.
- Swap: Pressing this button flips the opening and closing transforms behind the dynamic zoom effect.

### Composite

### The Composite section of the Video Inspector panel

When clips are layered above other clips on the Timeline, Composite modes let you blend them together.

- Composite Mode: Picks which kind of composite mode blends the layered clips together. The default of “Normal” signifies that no compositing mode is in effect.

To read more about Composite Modes, refer to Chapter 50, “Compositing and Transforms in the Timeline.” CUT

- Opacity: On top of whatever compositing is already happening, this slider raises or lowers

a clip’s transparency.

### Speed Change

Right inside the Video Inspector’s Speed Change controls you can retime your clip. One advantage of doing it here is that the controls show up on both the Cut and Edit pages.

### The Speed Change controls in the Video Inspector

- Direction: Picks the clip’s intended playback, whether forward, backward, or freeze frame.
- Speed %: Adjusting this slider changes the clips motion on a percentage basis.

This value can be keyframed.

- Frames Per Second: Moving this slider alters the clip’s motion by raising or lowering the number of frames per second at which the clip plays back. You can keyframe this value.
- Duration: Right here you can pick exactly how long the clip should run by entering a precise duration in HH:MM:SS:FF format. The clip’s speed then adjusts on its own so that every frame plays within that precise span of time.
- Ripple Sequence checkbox: Turn this checkbox on if you want the upcoming speed change to ripple the Timeline, shoving or dragging every clip after the current one to make room for that clip’s altered length.
- Pitch Correction checkbox: Ticking this box applies pitch correction to the clip’s audio, so that as the audio length stretches or compresses to track the picture speed, it still sounds natural. Keep in mind that pitch correction over big speed shifts may not hold up as well as pitch corrections done on small speed shifts.

### Stabilization

### The Stabilization section of the Video Inspector panel

Unwanted camera shake inside a clip can be smoothed or even fully steadied with these controls.

The analysis runs in a manner that keeps the motion of separate subjects in the

frame intact, along with the intended path of any wanted camera movement, all while ironing out the jitter.

These controls are the very same stabilizer controls found in the Color page’s Tracker palette (without the tracker graph), and the stabilization analysis that results is mirrored over to the Color page, where the data can be viewed on the graph whenever needed.

Three choices in a pop-up menu set how the chosen clip gets analyzed and reshaped while it is stabilized. Pick one before you press the Stabilize button above, because your pick alters the way the image analysis runs. Should you switch to a different choice, you have to click the Stabilize button once more to reanalyze the clip.

- Perspective: Enables perspective, pan, tilt, zoom, and rotation analysis and stabilization.
- Similarity: Turns on pan, tilt, zoom, and rotation analysis plus stabilization, for cases where perspective analysis brings about unwanted motion artifacts.
- Translation: Turns on pan and tilt analysis plus stabilization alone, for cases where X and Y stabilization on its own delivers results you can accept.

How forcefully the chosen clip is stabilized can be tuned with the remaining controls.

- Stabilization Toggle: Acting as the on/off switch for the Stabilization controls, this lets you flip stabilization off and on so you can weigh the stabilized image against the unstabilized one.
- Camera Lock: Switching this checkbox on shuts off Cropping Ratio and Smooth and lets the stabilizer concentrate on wiping out every bit of camera motion in the shot, aiming to produce a locked shot.
- Zoom: With this checkbox on, the image is enlarged by just enough of a percentage to wipe out the blanking (black edges) left behind by warping and transforming the image to cancel unwanted camera movement. The lower you set Cropping Ratio, the harder DaVinci Resolve has to zoom into an image to clear those blanked edges. Turn this off and the image stays at its original size, so whatever blanking creeps into the frame is sent out with the image, on the premise that you’ll have dedicated compositing artists handle the blanking by painting in the missing image data through more elaborate means. You can also keep this checkbox off if you intend to animate the Input Sizing Zoom parameter to push into and out of a stabilized shot, clearing blanking only at the spots it shows up and using no more zoom than each part of the shot demands.
- Cropping Ratio: By deciding how much blanking or zooming you’ll tolerate in trade for canceling unwanted motion, this value caps how aggressively the stabilizer works. At a setting of 1.0 no stabilization is applied at all. Stepping the value progressively lower turns on more aggressive stabilization. After changing this value you must click the Stabilize button again to reanalyze the clip.
- Smooth: Applies mathematical smoothing to the analyzed data the clip is stabilized with, permitting camera movement in the shot while clearing out unwanted jitter. Lower settings smooth less, letting more of the original camera move’s personality come through, whereas higher settings smooth the shot more aggressively. After changing this value you must click the Stabilize button again to reanalyze the clip.
- Strength: Acting as a multiplier, this value sets how tightly the stabilization track is used to remove motion from a shot under the current analysis. At a value of 1, stabilization is at its peak. Because certain clips can feel more natural with looser stabilization, picking a figure below 1 allows a slice of the original camera movement to remain visible. Zero (0) shuts stabilization off entirely. As a further tip, you can flip the stabilization by selecting –1 when pasting a stabilization analysis from a different clip to run a match move keyed to the scene’s overall motion, and you can apply a negative value either under 0 or above –1 to under- or overcompensate while inverting the stabilization, faking the parallax effect where foreground and background planes travel together but at differing rates.

### Lens Correction

Within the Video Inspector panel, the Lens Correction area (offered only in Resolve Studio) provides two controls that let you fix lens distortion in the picture, or introduce lens distortion of your own.

- Analyze: Automatically scans the frame currently under the Timeline playhead for edges bent by a wide angle lens. Pressing the Analyze button shifts the Distortion slider to apply a correction for you. If the clip you’re analyzing is an especially tough one, a progress bar shows up to tell you how long it will run.
- Distortion: Dragging this slider rightward lets you manually warp the picture to straighten out the bent regions that wide angle lenses tend to cause. If pressing the Analyze button left you with an overcorrection, dragging the slider leftward lets you ease off the automatic adjustment until the image looks right.

### Retime and Scaling

Within the Video Inspector panel, the Retime and Scaling area carries four parameters governing retime quality and clip scale:

- Retime Process: On a clip-by-clip basis, lets you set a default way to process clips in mixed frame rate timelines and those carrying speed effects (fast forward or slow motion). The default is “Project Settings,” so every speed-effected clip gets handled identically.

You get three choices here, Nearest, Frame Blend, and Optical Flow, each covered at greater length in the Speed Effect Processing section see Chapter 51, “Speed Effects.”

- Motion estimation mode: When Optical Flow handles speed change effects or clips whose frame rate differs from the Timeline’s, the Motion Estimation pop-up lets you pick the best-looking render choice for a specific clip. Each approach carries its own artifacts, and the top-quality choice isn’t always right for a particular clip. The default is “Project Settings,” so every speed-effected clip is treated the same. Several options exist. The “Standard Faster” and “Standard Better” settings match the ones offered in earlier DaVinci Resolve releases. They use less processor power and produce good quality that suits most cases. That said, “Enhanced Faster” and “Enhanced Better” should deliver better results in almost every instance where the standard choices show artifacts, at the cost of heavier computation and therefore slower speeds on most systems.
- The “Standard Faster” and “Standard Better” settings match the ones offered in earlier

DaVinci Resolve releases. They use less processor power and produce

good quality that suits most cases. That said, “Enhanced Faster” and “Enhanced

Better” should deliver better results in almost every instance where the standard choices show

artifacts, at the cost of heavier computation and therefore slower speeds on

most systems.

- “Speed Warp Faster and “Speed Warp Better” come into play for even finer slow motion effects driven by the DaVinci Neural Engine. How well they work depends on what’s in the clip, but under the best conditions they deliver finer visual quality with fewer artifacts than even the Enhanced Better setting does.
- Scaling: On a clip-by-clip basis, lets you decide how clips that don’t fit the current project resolution are dealt with. The default is “Project Settings,” so every mismatched clip is automatically resized the same way. You can, however, also assign an individual automatic scaling method to any clip.

Your choices here are Crop, Fit, Fill, and Stretch; to read more, refer to Chapter 152, “Sizing and Image Stabilization.”

- Resize Filter: For any clip being resized in whatever way, this setting lets you pick the filter method used to interpolate image pixels during resizing. Different settings suit different kinds of resizing. There are four options:

Sharper: Generally gives the finest quality on projects whose clips have to be scaled up into a bigger frame size, or scaled down into HD resolutions. Smoother: Can deliver finer quality on projects whose clips have to be scaled down into an SD resolution frame size. Bicubic: Although the Sharper and Smoother choices edge it out slightly on quality, Bicubic remains a remarkably good resizing filter and demands less processor power than either of them. Bilinear: A lesser-quality choice that taxes the processor less. Handy for previewing your work on an underpowered computer ahead of rendering, after which you can swap in one of the higher-quality choices. Other Resize Methods: When you need to align with other VFX workflows, a range of particular resize algorithms is on hand.

- Deinterlace Quality (Interlaced Clips Only): Permits per clip deinterlace quality tuning of how DaVinci Resolve merges an interlaced clip’s two fields into progressive frames. Normal: A high-quality deinterlacing method suited to most clips. On many clips, Normal can’t be told apart from High. Normal is always applied automatically while playing back in DaVinci Resolve. High: A more processor-intensive approach that can occasionally give better results, depending on the footage, at the cost of slower render times. DaVinci Neural Engine: This choice uses the advanced machine learning algorithms of the DaVinci Neural Engine to study motion between the fields of interlaced material and rebuilds them into one frame. It is extremely computationally intensive but, in the best case, should produce an even more pleasing result than the “high” setting.

### Super Scale

### The Super Scale parameters

For those moments when you require finer upscaling than the regular Resize Filters offer, you can now switch on one of the “Super Scale” options in the Inspector. Unlike the many scaling options across the Edit, Fusion, or Color pages, Super Scale actually raises the source resolution of the clip being processed, meaning that clip ends up with more pixels than before and is heavier to work with than before, unless you optimize it (which bakes the Super Scale effect into the optimized media) or cache it somehow. To dig into Super Scale further, refer to Chapter 11, “Image Sizing and Resolution Independence.” Turning to Super Scale within the Inspector accomplishes the same thing as configuring the matching controls for the media clip over in the Clip Attributes. That means altering this setting affects every additional edit that references the selected media too. The Super Scale group carries the following parameters that govern quality and clip scale:

- Super Scale: Lets you pick how much scaling you need. Your choices are 2-3-4x and 2-3-4x Enhanced.
- Sharpness: Lets you set how much detail the scaling carries. The choice here is held to Low, Medium, or High, unless Super Scale mode runs in Enhanced, which opens up variable sharpness. You’ll want to weigh this setting against Noise Reduction.
- Noise Reduction: Lets you set how much noise reduction the scaling applies. The choice here is held to Low, Medium, or High, unless Super Scale mode runs in Enhanced, which opens up variable noise reduction. You’ll want to weigh this setting against Sharpness.

### Audio

### The Audio Inspector Clip and Track parameters

Depending on which icon you’ve picked at the upper left of the Inspector, the Audio Inspector can act on individual clips or on whole tracks. Usually this choice flips automatically for you based on what is selected in the timeline. As an example, clicking an audio clip in the timeline opens the Inspector in Clip mode, while clicking an audio track header switches the Inspector to Track mode by itself. You can always override these manually just by clicking the right icon. Clip and Track modes hold different options for audio editing.

The Audio Inspector in Clip mode (circled)

The Audio Inspector in Track mode (circled)

For the audio side of video editing, the Audio tab gathers the controls you reach for most, such as Volume, Pan, Pitch, and Equalizer. On top of that, it bundles several truly useful tools powered by the DaVinci Neural Engine, among them Voice Isolation, Dialog Leveler, and Music Remixer.

- Volume: Every clip carries one volume control, tied to the volume overlay drawn across each audio clip.
- Pan: A straightforward Pan slider that drives stereo panning. Although most professional mixes keep their panning to the sturdier panner over in the Fairlight page Mixer, this basic Pan control comes in handy for picture editors over on the Edit page who want to whip up simple panning moves to support a craft edit.
- Voice Isolation (Studio Version Only): Voice Isolation is a plugin built to strip loud, unwanted noises out of existing voice recordings. The effect leans on AI to supply models that let you fully erase undesired sounds. Trained on every kind of human voice, male or female, young or old, the AI model can deliver remarkable results isolating dialog from background noise in a recording, covering everything from air conditioning or fans to extremely loud sources like a jackhammer, restaurant chatter, or music playing while the subject talks, and beyond.

To read more about Voice Isolation, refer to Chapter 31, “Video and Audio Effects in the Cut Page.” Amount: This control sets how much voice isolation processing gets applied. To read more about Voice Isolation, refer to Chapter 181, “Fairlight FX.”

- Dialogue Leveler: The Dialogue Leveler studies source material to spot dialog and then “ride down” the louder stretches, “lift up” the softer ones, and pull down background noise that isn’t dialog. It does this without the usual dynamics processor “pumping” (compression/limiting) or other tell-tale side effects, giving results on par with meticulous hand-done clip gain moves or with laboriously “riding” the track using fader automation. Preset Menu: From the preset menu you get these choices:
- Optimized for most sources: Chosen by default, this one performs nicely across most sources.
- More lift for low levels: Pick this one when the source holds more low level dialog you’d like lifted.
- Lift soft whispery sources: Pick this one when the source carries whispered dialog alongside background noise. Reduce Loud Dialogue: With this on, louder dialogue is ridden down on its peaks and behaves much like a “perfect limiter” where you needn’t set a threshold or time constants. Owing to the “near real time” nature, analysis runs ahead of audible playback for the best results. Lift Soft Dialogue: With this on, it locates low level dialogue and lifts and evens out material that swings more in level and runs softer, yet since the process keeps its attention on dialogue, it generally avoids lifting background sounds (except when they land at the exact instant the dialogue does). In most cases, of the three choices the Lift Soft Dialogue one proves handiest, as it brings faint lines of dialogue forward and smooths them naturally without pushing up background noise. Background Reduction: With this on, it trims background sounds by locking onto dialogue and easing them out per the built-in presets (Preset menu). Output Gain: Set the Output Gain either by click-dragging on the Output Gain control or by typing a figure into the numeric field (the Output Gain control runs in dB across a 0 to +6 dB range at .1dB resolution).

### CUT 617
