# Using The Inspector In The Edit Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using the Inspector in the Edit Page

Every control for changing, resizing, retiming, and otherwise adjusting whatever pertains to a clip, transition, or effect on the Edit page Timeline lives in the Inspector.

### Using the Inspector

A redesign of the Inspector now makes locating particular controls and tweaking everyday clip settings simpler. Rather than one long vertical list, the Inspector’s various aspects are sorted into panels, each one in charge of a specific grouped set of parameters for your clip. You bring up the Inspector by clicking the Inspector Panel at the upper-right end of the User Interface toolbar. The Inspector splits into separate Video, Audio, Effects, Transition, Image, and File panels. Whichever Inspector panels don’t apply to your clip or selection appear grayed out.

The Inspector Panel icon located at the top right of the UI toolbar The Inspector panels with Video, Audio, and File parameters open for adjustment, the rest grayed out. Ways to work the controls in the Inspector:

- To turn a control on or off: Click the toggle sitting to the left of the control’s name. An orange dot on the right signals the control is on. A gray dot on the left signals it’s off.
- To expose a control’s parameters: Double-click the control’s name.
- To restore controls to default values: Click the reset button found at the right of the control’s name.

### Video

A huge selection of controls for working the size, speed, and opacity of your clips sits in the Inspector’s Video panel.

### Transform

### The Transform section of the Video Inspector panel

For resizing and repositioning your clips, the Transform group carries these parameters:

- Zoom X and Y: Lets you enlarge the image or scale it down. You can link the X and Y parameters to hold the image’s aspect ratio, or unlink them to stretch or compress the image along a single axis.
- Position X and Y: Shifts the image around inside the frame so pan and scan adjustments become possible. X slides the image left or right, while Y slides it up or down.
- Rotation Angle: Spins the image about the anchor point.
- Anchor Point X and Y: Sets the coordinate on the clip around which every transform is centered.
- Pitch: Tilts the image toward or away from the camera about an axis that runs through the

middle of the image, left to right. Positive values send the image’s top away while bringing its bottom forward. Negative values bring the top forward while sending the bottom away. The larger the value, the more extreme the stretch.

- Yaw: Tilts the image toward or away from the camera about an axis through the image’s center running top to bottom. Positive values bring the image’s left forward and send its right away. Negative values send the left away and bring the right forward. The larger the value, the more extreme the stretch.
- Flip Image: A pair of buttons flips the image along different axes. Flip Horizontal control: Mirrors the image across the X-axis, left to right. Flip Vertical control: Mirrors the clip across the Y-axis, flipping it upside down.

Smart Reframe (Studio Version Only)

The Video Inspector panel’s Smart Reframe section Smart Reframe, as a feature, streamlines rapid reframing of material across drastic aspect ratio shifts. It comes in handy when you’ve shot a 16:9 horizontal video yet need a vertical 9:16 version for mobile phones and social media deliverables, or when fitting 4:3 archival footage into a 2.39:1 widescreen movie. You can drive Smart Reframe by hand or let the DaVinci Resolve Neural Engine run it automatically.

- Object of Interest: Tools for choosing the subject the resize will build its framing around.
- Auto: DaVinci Resolve’s Neural Engine examines the clip and settles on its most representative

object. It’s your only choice when more than one clip is selected for Smart Reframing.

- Reference Point: Lets you adjust by hand a bounding box drawn around the subject you want to

reframe around.

- Mode: Tools for confining the AI reframing to a single axis.
- Auto: Smart Reframe adjusts a clip’s pan and tilt however much it judges necessary to reframe

the target properly.

- Pan Only: Smart Reframe limits itself to the clip’s pan (left and right) motion.
- Tilt Only: Smart Reframe limits itself to the clip’s tilt (up and down) motion.
- Reframe: Pressing this button runs the Smart Reframe command. How long it takes hinges

on the length and quantity of clips.

### Cropping

### The Cropping section of the Video Inspector panel

The image’s cropping parameters are governed by the Video Inspector.

- Crop Left, Right, Top, and Bottom: Lets you trim away the four edges of the image in pixels. Cropping

a clip opens up transparency so whatever lies beneath becomes visible.

- Softness: Lets you blur a crop’s edges. A negative value softens the edges

inside the crop box, whereas a positive value softens those outside it.

- Retain Image Position: Ticking this checkbox pins the crop parameters in place while you resize the image with the Transform tool above. Clearing it makes the crop scale and reposition right along with the image.

### Dynamic Zoom

The Dynamic Zoom section of the Video Inspector panel Switched off by default, the Dynamic Zoom controls make pan and scan effects that zoom into or out of a clip quick and painless. Enabling the Dynamic Zoom group lights up two Inspector controls that operate in tandem with the Dynamic Zoom onscreen adjustment controls. For more on working the Dynamic Zoom controls, refer to Chapter 50, “Compositing and Transforms in the Timeline.”

- Dynamic Zoom Ease: Lets you set how the motion these controls create speeds up. The choices are Linear, Ease In, Ease Out, and Ease In and Out.
- Swap: Pressing this button flips the start and end transforms behind the dynamic zoom effect.

### Composite

### The Composite section of the Video Inspector panel

When clips sit layered over other clips in the Timeline, composite modes let you blend them together.

- Composite Mode: This picks which composite mode merges the layered clips. With the default “Normal,” no compositing mode is in effect.

For more on Composite Modes, refer to Chapter 50, “Compositing and Transforms in the Timeline.”

- Opacity: On top of any compositing already happening, this slider raises or lowers a clip’s transparency.

### Speed Change

### The Speed Change controls in the Video Inspector

Your clip’s speed can be altered right inside the Video Inspector’s Speed Change controls. One advantage of this route is that it’s present on both the Cut and Edit pages.

- Direction: Chooses how the clip moves — forward, backward, or freeze frame.
- Speed %: Moving this slider alters the clip’s motion as a percentage. The value

accepts keyframes.

- Frames Per Second: Moving this slider alters the clip’s motion by raising or lowering the

number of frames per second at which the clip plays back. The value accepts keyframes.

- Duration: You can pick a clip’s length outright by entering a specific duration

here in HH:MM:SS:FF format. The clip’s speed then adjusts on its own so every frame plays within that precise span of time.

- Ripple Sequence checkbox: Switch this checkbox on if you want the speed change you’re about to apply to ripple the Timeline, nudging every clip after the current one forward or back to make room for its new size.
- Pitch Correction checkbox: Ticking this box runs pitch correction on the clip’s attached audio so that, even as the audio duration shifts to track the picture speed, it still sounds natural. Bear in mind that pitch correction across large speed changes may not sound as clean as it does across small ones.

### Stabilization

### The Stabilization section of the Video Inspector panel

These controls let you smooth away — or fully steady — unwanted camera motion inside a clip. The analysis runs in a way that keeps the movement of individual subjects in the frame intact, along with the overall direction of the camera motion you want, while ironing out the shakiness. They’re the very same stabilizer controls in the Color page’s Tracker palette (the tracker graph aside), and the resulting stabilization analysis carries over to the Color page, where you can view the data plotted on the graph should the need arise. A pop-up menu offers three options that set how the selected clip is analyzed and reshaped during stabilization. Pick an option before you click the Stabilize button above, since your choice alters how the image analysis runs. Switch to a different option and you’ll have to click the Stabilize button once more to reanalyze the clip.

- Perspective: Turns on perspective, pan, tilt, zoom, and rotation analysis and stabilization.
- Similarity: Turns on pan, tilt, zoom, and rotation analysis and stabilization, for cases where

perspective analysis produces unwanted motion artifacts.

- Translation: Turns on pan and tilt analysis and stabilization only, for cases where X and Y stabilization alone gives acceptable results.

The remaining controls let you tailor how forcefully the selected clip gets stabilized.

- Stabilization Toggle: The toggle that governs the Stabilization controls lets you flip stabilization off and on so you can compare the stabilized image against the unstabilized one.
- Camera Lock: Switching on this checkbox shuts off Cropping Ratio and Smooth and lets the stabilizer concentrate on stripping every bit of camera motion out of the shot in pursuit of a locked-off result.
- Zoom: With this checkbox on, the image is scaled up by enough of a percentage to erase the blanking (black edges) left behind when warping and transforming the image removes unwanted camera motion. The lower you set Cropping Ratio, the harder DaVinci Resolve must zoom into an image to clear those blanked edges. Leave it off and the image isn’t zoomed at all; whatever blanking creeps into the frame is output right along with the image, on the premise that dedicated compositing artists will handle the blanking by filling in the missing image data more elaborately. You might also keep this checkbox off when you intend to animate the Input Sizing Zoom parameter, dynamically zooming a stabilized shot in and out to clear blanking only where it crops up, applying no more zoom than each region of the shot needs.
- Cropping Ratio: This value caps how hard the stabilizer pushes, by dictating how much blanking or zooming you’ll tolerate in trade for removing unwanted motion. At 1.0, no stabilization is applied. Steadily lower values open up more aggressive stabilization. Altering this value means clicking the Stabilize button once more to reanalyze the clip.
- Smooth: Lets you run mathematical smoothing over the analyzed data driving the clip’s stabilization, permitting camera motion in the shot while wiping out unwanted jitter. Lower values smooth less,

letting more of the original camera motion’s character come through, while higher values smooth the shot more aggressively. Altering this value means clicking the Stabilize button once more to reanalyze the clip.

- Strength: This value acts as a multiplier letting you decide how tightly the stabilization track is used to remove motion from a shot under the current analysis. At a value of 1, stabilization runs at its fullest. Because some clips read more naturally with looser stabilization, a number below 1 lets a share of the original camera motion remain visible. Zero (0) shuts stabilization off entirely. As one more tip, you can invert the stabilization by choosing –1 when you paste a stabilization analysis from another clip to do a match move based on the scene’s overall motion, and you can use a negative value either below 0 or above –1 to under- or overcompensate while inverting, mimicking parallax where foreground and background planes drift together yet at different rates.

### Lens Correction

The Video Inspector panel’s Lens Correction section Available solely in Resolve Studio, the Lens Correction group provides two controls for either fixing lens distortion in the image or introducing distortion of your own.

- Analyze: Automatically inspects the Timeline frame sitting under the playhead for edges being bent by a wide angle lens. Clicking the Analyze button shifts the Distortion slider to deliver an automatic fix. On an especially tough clip, a progress bar shows up to tell you how long it’ll take.
- Distortion: Pulling this slider rightward lets you hand-apply a warp that straightens the curved regions a wide angle lens can introduce. Should clicking the Analyze button leave you with an overcorrection, pulling this slider leftward eases off the automatic adjustment until the image looks right.

### Retime and Scaling

The Retime and Scaling section of the Video Inspector panel Four parameters in the Retime and Scaling group bear on retiming quality and clip scale:

- Retime Process: Lets you set, clip by clip, a default way of handling clips in mixed frame rate timelines

as well as those carrying speed effects (fast forward or slow motion). Its default is “Project Settings,” which treats every speed-effected clip alike. Three choices exist — Nearest, Frame Blend, and Optical Flow — and the Speed Effect Processing section covers them more fully; see Chapter 51, “Speed Effects.”

- Motion estimation mode: When Optical Flow is processing speed change effects or clips whose frame rate differs from the Timeline’s, the Motion Estimation pop-up lets you select the best-looking rendering option for a given clip. Every method leaves its own artifacts, and the top-quality option isn’t invariably the right pick for a particular clip. Its default is “Project Settings,” which treats every speed-effected clip alike. A handful of choices are offered. The “Standard Faster” and “Standard Better” settings match those carried over from earlier versions of DaVinci Resolve. They lean lighter on the processor and give good quality fit for most situations. By contrast, “Enhanced Faster” and “Enhanced Better” ought to deliver better outcomes in almost every case where the standard options show artifacts, though at the cost of heavier computation and therefore slower speeds on most systems.
- The “Standard Faster” and “Standard Better” settings match those carried over from earlier versions of DaVinci Resolve. They lean lighter on the processor and give good quality fit for most situations. By contrast, “Enhanced Faster” and “Enhanced Better” ought to deliver better outcomes in almost every case where the standard options show artifacts, though at the cost of heavier computation and therefore slower speeds on most systems.
- “Speed Warp Faster and “Speed Warp Better” exist for even higher-quality slow motion effects powered by the DaVinci Neural Engine. How well this setting performs depends on the clip’s content, but under ideal conditions it yields finer visual quality with fewer artifacts than even the Enhanced Better setting.
- Scaling: Lets you decide, clip by clip, how clips that don’t match the current project resolution get handled. Its default is “Project Settings,” so every mismatched clip is automatically resized the same way.

That said, you can also assign an individual automatic-scaling method to any clip. The choices are Crop, Fit, Fill, and Stretch; for more, see the 2D Transforms section and Chapter 152, “Sizing and Image Stabilization.”

- Resize Filter: Whenever a clip is resized in any fashion, this setting lets you pick the filter method that interpolates image pixels during the resize. Some settings suit certain kinds of resizing better than others. Four choices are on offer:

Sharper: Generally gives the best quality on projects whose clips must be scaled up to fill a bigger frame size, or scaled down to HD resolutions. Smoother: Can give higher quality on projects whose clips must be scaled down into an SD resolution frame size. Bicubic: Though the Sharper and Smoother options edge it out on quality, Bicubic is still an excellent resizing filter and asks less of the processor than either of them. Bilinear: A lower-quality, lighter-on-the-processor setting. It’s handy for previewing your work on an underpowered computer before rendering, when you can swap in one of the higher-quality options. Other Resize Methods: A set of particular resize algorithms is available when you need to align with other VFX workflows.

- Deinterlace Quality (Interlaced Clips Only): Permits per clip deinterlace-quality tweaks for how DaVinci Resolve fuses the two fields of interlaced media into progressive frames.

Normal: A high-quality deinterlacing method fit for most clips. On many clips, Normal can’t be told apart from High. Normal is what DaVinci Resolve always applies automatically during playback. High: A more processor-hungry method that, depending on the footage, can occasionally produce better results at the cost of slower rendering. DaVinci Neural Engine: This choice taps the advanced machine learning algorithms of the DaVinci Neural Engine to study motion between the fields of interlaced material and rebuild them into one frame. It’s very heavy on computation but, at its best, should yield an even more pleasing result than the “high” setting.

### Super Scale

### The Super Scale parameters

When you require higher-quality upscaling than the standard Resize Filters can manage, you can now switch on one of the “Super Scale” options in the Inspector. Unlike the many scaling options across the Edit, Fusion, or Color pages, Super Scale genuinely raises the source resolution of the clip it processes, meaning the clip ends up with more pixels than before and grows more processor-hungry to handle — unless you optimize it (which bakes the Super Scale effect into the optimized media) or cache it somehow. For deeper coverage of Super Scale, see Chapter 11, “Image Sizing and Resolution Independence.” Applying Super Scale in the Inspector amounts to the same thing as setting those controls for the media clip in the Clip Attributes. Consequently, changing this setting also touches every additional edit that references the selected media. These are the Super Scale group’s parameters bearing on quality and clip scale:

- Super Scale: Lets you choose how much scaling is needed. The choices are 2-3-4x and 2-3-4x Enhanced.
- Sharpness: Lets you choose how much detail the scaling carries. Your picks are confined to Low, Medium, or High except when Enhanced is the chosen Super Scale mode, where variable sharpness becomes available. You’ll want to weigh this setting against Noise Reduction.
- Noise Reduction: Lets you choose how much noise reduction the scaling applies. Again, the picks stay confined to Low, Medium, or High except when Enhanced is the chosen Super Scale mode, where variable noise reduction becomes available. You’ll want to weigh this setting against Sharpness.

Cinematic (Apple iPhone Footage and MacOS Only) The Cinematic parameters With Apple iPhone footage shot in Cinematic mode, on MacOS builds of DaVinci Resolve, you can tune that footage’s parameters by choosing the Cinematic overlay from the Viewer Overlays drop-down. F-Stop: Moving this slider lets you mimic the depth of field behavior of a lens iris.

### Audio

### The Audio Inspector Clip and Track parameters

The Audio Inspector operates on either individual clips or whole tracks, depending on which icon is chosen at the Inspector’s upper left. As a rule this option sets itself for you

according to what you’ve selected in the timeline. Click an audio clip in the timeline, for instance, and the Inspector opens in Clip mode; click an audio track header, and it flips to Track mode on its own. You can always override these manually just by clicking the right icon. Clip and Track modes carry different options for audio editing.

The Audio Inspector in Clip mode (circled)

The Audio Inspector in Track mode (circled)

The Audio tab gathers the audio controls used most often in video editing, among them Volume, Pan, Pitch, and Equalizer. It also holds several remarkably handy DaVinci Neural Engine powered tools such as Voice Isolation, Dialog Leveler, and Music Remixer.

- Volume: Every clip carries one volume control tied to the volume overlay drawn across each audio clip.
- Pan: A basic Pan slider governing stereo panning. Although most professional mixes confine panning to the more capable panner in the Fairlight page Mixer, this simple Pan control helps picture editors on the Edit page quickly whip up basic panning effects to support a craft edit.
- Voice Isolation (Studio Version Only): Voice Isolation is a plugin built to strip loud, unwanted sounds out of existing voice recordings. The effect draws on AI models that let you fully eliminate the sounds you don’t want. Its AI model is trained on every sort of human voice — male or female, young or old — so you can achieve striking results that pull dialog clear of background noise in a recording, covering everything from air conditioning or fans to extremely loud sources like a jackhammer, restaurant chatter, or music playing while the subject speaks, and beyond.

For a fuller treatment of Voice Isolation, turn to Chapter 45, “Working with Audio in the Edit Page.” Amount: Lets you dial how much voice isolation processing is applied.

- Dialogue Leveler: The Dialogue Leveler studies source material to find dialog, then “rides down” the louder stretches, “lifts up” the softer ones, and turns down background sounds that aren’t dialog. It does so without the usual dynamics-processor “pumping” (compression/limiting) or other obvious artifacts, giving results akin to meticulous manual clip gain work or to carefully “riding” the track with fader automation.

Preset Menu: The preset menu offers these choices:

- Optimized for most sources: Chosen by default, this works well across most sources.
- More lift for low levels: Pick this when the source carries more low-level dialog that

you’d like to boost.

- Lift soft whispery sources: Pick this when the source holds whispered dialog and background noise.

Reduce Loud Dialogue: Once on, louder dialogue gets ridden down on its peaks, behaving rather like a “perfect limiter” for which you needn’t set threshold or time constants. Thanks to the “near real time” design, analysis runs ahead of audible playback for the best outcome. Lift Soft Dialogue: Once on, it locates low-level dialogue and lifts and evens out material that runs softer and more uneven in level, yet because the process zeroes in on dialogue it generally won’t raise background sounds (unless they coincide with the dialogue itself). More often than not, Lift Soft Dialogue proves the most useful of the three, since it brings barely-audible lines of dialogue up to an audible, naturally smooth level without amplifying background noise.
