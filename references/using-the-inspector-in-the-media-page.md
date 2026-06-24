# Using The Inspector In The Media Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using the Inspector in the Media Page

The Inspector gathers every control needed to modify, resize, retime, and otherwise tweak anything to do with a clip, transition, or effect on the Media page Timeline.

### Using the Inspector

A redesign of the Inspector has made it simpler to locate particular controls and to set common settings for your clips. Rather than one long vertical list, the Inspector’s various facets are now sorted into panels, each governing a specific grouped set of parameters for your clip. To turn the Inspector on, click the Inspector Panel over in the User Interface toolbar’s upper-right section. The Inspector divides into distinct Video, Audio, Effects, Transition, Image, and File panels. Any Inspector panel that has no bearing on your clip or selection shows up grayed out. The Inspector Panel icon up at the right of the UI toolbar

The Inspector panels with Video, Audio, and File parameters open for adjustment; the rest sit grayed out. Ways to work the controls in the Inspector:

- To activate or deactivate a control: Click the toggle sitting left of that control’s name. An orange dot off to the right signals the control is activated. A gray dot off to the left signals the control is deactivated.
- To reveal a control’s parameters: Double-click the control’s name.
- To reset controls to their defaults: Click the reset button sitting right of that control’s name.

### Adjusting Media Pool Clips in the Inspector

Media Pool clips can be modified straight in the Inspector, ahead of editing those clips into a timeline. That lets you alter the parameters of source media so that clips later edited into a timeline carry those new settings along. As an example, you can ready your material before editing by altering the clip’s file and RAW settings, tuning the audio levels and EQ, or handing it a particular lens correction, and so on. Once that’s done, every part of that clip would arrive in your timeline with the right Inspector parameters already set. To adjust Media Pool clips in the Inspector: 1 Within the Media Pool Panel of the Media, Cut, Edit, or Fairlight pages, pick one or more clips. 2 Bring up the Inspector panel, then tweak any parameters across the Video, Audio, Image and File tabs. Those parameter changes get saved with the Media Pool clip and carry over whenever any part of that clip is edited into the Timeline. Naturally, each clip’s Inspector parameters can be tweaked further once it sits in the Timeline, and those Timeline parameters stand apart from the Media Pool Inspector settings. Put another way, whatever further adjustments you apply to the clip in the Timeline leave that same clip’s adjustments already in the Media Pool untouched.

### Video

The Video Panel of the Inspector surfaces a huge range of controls built to handle the size, speed, and opacity of your clips.

### Transform

### The Transform section of the Video Inspector panel

The Transform group carries these parameters for resizing and repositioning your clips:

- Zoom X and Y: Lets you enlarge the image or shrink it. The X and Y parameters may be linked to hold the image’s aspect ratio, or unlinked to stretch or squeeze the image along one direction alone.
- Position X and Y: Shifts the image within the frame, making pan and scan adjustments possible. X drives the image left or right, while Y drives it up or down.
- Rotation Angle: Spins the image about the anchor point.
- Anchor Point X and Y: Sets the coordinate on that clip around which every transform is centered.
- Pitch: Tips the image toward or away from the camera along an axis that runs through the

middle of the image, from left to right. Positive values send the top of the image back and draw the bottom forward. Negative values draw the top of the image forward and send the bottom back. The larger the value, the more extreme the stretch.

- Yaw: Tips the image toward or away from the camera along an axis that runs through the middle of the image from top to bottom. Positive values draw the left of the image forward and send the right back. Negative values send the left of the image back and draw the right forward. The larger the value, the more extreme the stretch.
- Flip Image: A pair of buttons let you flip the image in different dimensions. Flip Horizontal control: Mirrors the image along the X-axis, left to right. Flip Vertical control: Mirrors the clip along the Y-axis, flipping it upside down.

### Cropping

### The Cropping section of the Video Inspector panel

The Video Inspector governs the image’s cropping parameters:

- Crop Left, Right, Top, and Bottom: Lets you trim, in pixels, the four sides of the image. Cropping a clip yields transparency so that whatever lies beneath shows through.
- Softness: Lets you blur a crop’s edges. A negative value softens the edges inside the crop box, whereas a positive value softens the edges outside the crop box.
- Retain Image Position: Ticking this checkbox pins the crop parameters in place as you resize the image with the Transform tool above. Unticking it scales and positions the crop right along with the image.

### Dynamic Zoom

The Dynamic Zoom section sitting within the Video Inspector panel The Dynamic Zoom controls, off to begin with, make pan and scan effects that zoom into or out of a clip quick and painless. Switching the Dynamic Zoom group on brings two controls alive in the Inspector that operate hand-in-hand with the Dynamic Zoom onscreen adjustment controls. For more on working the Dynamic Zoom controls, refer to Chapter 50, “Compositing and Transforms in the Timeline.”

- Dynamic Zoom Ease: Lets you set how the motion these controls produce accelerates. Your choices are Linear, Ease In, Ease Out, and Ease In and Out.
- Swap: This button flips the start and end transforms that build the dynamic zoom effect.

### Composite

### The Composite section of the Video Inspector panel

Composite modes serve to blend clips superimposed over other clips in the Timeline.

- Composite Mode: This picks the kind of composite mode used to blend the superimposed clips. The default “Normal” signals that no compositing mode is applied.

For more on Composite Modes, refer to Chapter 50, “Compositing and Transforms in the Timeline.”

- Opacity: This slider renders a clip more or less transparent on top of whatever compositing is already underway.

### Lens Correction

The Lens Correction section sitting within the Video Inspector panel The Lens Correction group (offered only in Resolve Studio) holds two controls with which you correct lens distortion in the image, or introduce lens distortion of your own.

- Analyze: Automatically inspects the frame in the Timeline at the playhead’s spot for edges bent by a wide angle lens. A click on the Analyze button drives the Distortion slider to deliver an automatic correction. While you analyze an especially tough clip, a progress bar appears to indicate how long it’ll take.
- Distortion: Dragging this slider rightward lets you apply a warp to the image by hand so you can straighten the bent regions of the picture that wide angle lenses can introduce. If you clicked the Analyze button and got an overcorrection, dragging this slider leftward lets you ease off the automatic adjustment until the image looks right.

### Retime and Scaling

The Retime and Scaling section sitting within the Video Inspector panel The Retime and Scaling group holds four parameters bearing on retiming quality and clip scale:

- Retime Process: Lets you pick a default way of processing clips in mixed frame rate timelines and those carrying speed effects (fast forward or slow motion), on a clip-by-clip basis. The default is “Project Settings,” so every speed-effected clip gets handled identically.

Three options exist: Nearest, Frame Blend, and Optical Flow, laid out in fuller detail in the Speed Effect Processing section, refer to Chapter 51, “Speed Effects.”

- Motion estimation mode: While using Optical Flow to process speed change effects or clips whose frame rate differs from the Timeline’s, the Motion Estimation pop-up lets you pick the best-looking rendering option for a given clip. Each method brings its own artifacts, and the top-quality option isn’t always the right pick for a particular clip. The default is “Project Settings,” so every speed-effected clip gets handled identically. Several options exist. The “Standard Faster” and “Standard Better” settings are the very ones carried over from earlier versions of DaVinci Resolve. They lean lighter on the processor and turn out good quality fit for most situations. That said, “Enhanced Faster” and “Enhanced Better” ought to produce better results in just about every case where the standard options show artifacts, though they cost more computationally and so run slower on most systems.
- The “Standard Faster” and “Standard Better” options are the same ones that earlier DaVinci Resolve releases offered. Being easier on the processor, they deliver solid quality suitable for the majority of cases. Even so, “Enhanced Faster” and “Enhanced Better” should give superior output nearly everywhere the standard options reveal artifacts, the trade-off being heavier computation and therefore slower performance on most systems.
- “Speed Warp Faster and “Speed Warp Better” are on hand for even higher-quality slow motion effects by way of the DaVinci Neural Engine. How well this setting performs depends on a clip’s content, but under ideal conditions it’ll deliver greater visual quality with fewer artifacts than even the Enhanced Better setting.
- Scaling: Lets you set how clips that don’t match the current project resolution get handled on a clip-by-clip basis. The default is “Project Settings,” so all mismatched clips share the same method of being resized automatically.

That said, a clip-specific method of automatic scaling can be chosen for any clip too. Your options here are Crop, Fit, Fill, and Stretch; for more, refer to the 2D Transforms sectionm, see Chapter 152, “Sizing and Image Stabilization.”

- Resize Filter: For clips being resized in any fashion, this setting lets you pick the filter method used to interpolate image pixels while resizing clips. Different settings suit different kinds of resizing. Four options exist: Sharper: As a rule the top-quality pick on projects whose clips have to be enlarged to fill a bigger frame size, or shrunk down to HD resolutions. Smoother: May deliver higher quality on projects whose clips have to be shrunk to fit an SD resolution frame size. Bicubic: Although the Sharper and Smoother options edge ahead in quality, Bicubic stays an exceptionally fine resizing filter and asks less of the processor than either of those. Bilinear: A lower quality setting that asks less of the processor. Useful when you preview your work ahead of rendering on an underpowered computer, after which you can switch over to one of the higher quality options. Other Resize Methods: A set of specific resize algorithms is on offer should you need them to line up with other VFX workflows.

### Super Scale

### The Super Scale parameters

For times when you need upscaling of higher quality than the standard Resize Filters provide, you can now switch on one of the “Super Scale” options in the Inspector. Unlike reaching for one of the many scaling options across the Edit, Fusion, or Color pages, Super Scale genuinely raises the source resolution of the clip being processed; that clip thus ends up holding more pixels than it had and becomes heavier on the processor to work with than it was, short of optimizing the clip (which bakes the Super Scale effect into the optimized media) or caching the clip somehow.

For fuller detail on Super Scale, refer to Chapter 11, “Image Sizing and Resolution Independence.”

Working Super Scale in the Inspector is, functionally, the same as configuring those identical controls on the media clip via the Clip Attributes. That means changing this setting affects every additional edit referencing the selected media as well. The Super Scale group carries these parameters touching quality and clip scale:

- Super Scale: Lets you pick how much scaling you need. The options are 2-3-4x and 2-3-4x Enhanced.
- Sharpness: Lets you pick how much detail the scaling carries. This is capped at Low, Medium, or High, unless the Super Scale mode sits on Enhanced, which lets you apply variable sharpness. You’ll want to weigh this setting against Noise Reduction.
- Noise Reduction: Lets you pick how much noise reduction the scaling carries. This is capped at Low, Medium, or High, unless the Super Scale mode sits on Enhanced, which lets you apply variable noise reduction. You’ll want to weigh this setting against Sharpness.

### Audio

The Audio tab holds four audio controls commonly used for video editing, namely Clip Volume, Clip Pan, Clip Pitch, and Clip Equalizer.

- Clip Volume: Each clip carries a single volume control matching the volume overlay across each audio clip.
- Clip Pan: (Surfaced only for clips) A plain Pan slider that governs stereo panning.
- Clip Pitch: Lets you shift a clip’s pitch while leaving the speed alone. A pair of sliders set clip pitch by semi tones (coarse moves, a twelfth of an octave) and by cents (fine moves, 100th of a semi tone).

### Equalizer

This six-band parametric equalizer offers both graphical and numeric controls for boosting or cutting various ranges of frequencies inside that clip, before it even reaches the EQ built into the Mixer. Every band provides its own controls — filter type (Bell, Lo-Shelf, Hi-Shelf, Notch), Frequency, Gain, plus Q-factor (how sharp the band is) — and which of those controls appear on a given EQ band depends on the filter type in use.

### The Audio Inspector parameters

TIP: You may copy Clip EQ settings and paste them across from one Clip EQ onto another, as well as back and forth between Clip EQ and Track EQ instances.

### Clip EQ in the Audio Inspector

### The Clip EQ graph with user-draggable handles

### Master EQ Controls

The Equalizer window carries these overall controls in its upper right and left corners:

- Enable button: Switches the overall EQ effect off and on, leaving the controls unreset.
- Reset button: Returns all controls of the EQ window to their defaults.

### Clip EQ Graph

This graph shows the current EQ curve with handles matching each enabled EQ band listed below. Drag any numbered handle to boost or cut the band’s frequency range, applying whichever equalization type that band is set to.. As you drag the numbered handles on this graph, the matching band’s parameters change accordingly, and changing each band’s parameters in turn redraws the EQ graph, which doubles as a graphical depiction of the equalization being applied to that track.

### Bands 1 and 6

When required, the outermost two sets of band controls give you high-pass and low-pass adjustments.

- Band enable button: Switches each band of EQ on and off.
- Band filter type: Bands 1 and 6 can be flipped among five specific filtering options for

handling the lowest or highest frequencies in the signal. On Band 1 these run (top to bottom): Lo-Shelf, Bell, Notch, Hi-Shelf, and Hi-Pass. On Band 6 the options run (top to bottom): Lo-Pass, Lo-Shelf, Bell, Notch, and Hi-Shelf.

- Freq: Sets the center frequency of the EQ adjustment.
- Gain: Sets how strongly the affected frequencies are impacted. Negative values

cut those frequencies, while positive values lift them.

- Q Factor: This parameter sets the width of affected frequencies and shows up whenever the Bell option is chosen. Lower values take in a wider range of frequencies; higher values take in a narrower range of frequencies.

### Bands 2 through 5

These band controls let you make a broad spread of equalization adjustments.

- Band enable button: Switches each band of EQ on and off.
- Band filter type: These Bands carry four filtering options (top to bottom): Lo-Shelf, Bell,

Notch, and Hi-Shelf.

- Frequency: Sets the center frequency of the EQ adjustment.
- Gain: Sets how strongly the affected frequencies are altered. Negative values

cut those frequencies, while positive values lift them.

- Q Factor: This parameter shows up when the Bell setting is chosen. It sets the width of

affected frequencies. Lower values pull in a broader span of frequencies; higher values tighten that span. NOTE: The Audio FX library holds plenty of more sophisticated plugins and effects for audio clips. Apply any of them and their controls turn up within the Inspector’s Effects tab Audio section rather than here.

### Image

The Image panel holds groups of parameters matching every camera raw media format DaVinci Resolve supports. By means of these Image panel parameters, the original camera metadata written when the footage was recorded can be overridden, and you can adjust camera raw media simultaneously across your whole project. For a thorough rundown of every RAW camera parameter DaVinci Resolve supports, refer to Chapter 7, “Camera Raw Settings.”

### The Image Inspector controµls for BRAW footage

### File

### The File Inspector controls

### Metadata

The File panel of the Inspector offers a consolidated route to view and edit a slice of a clip’s most commonly used media file metadata. From the Inspector it’s readily reached on the Media, Cut, Edit, and Fairlight pages alike. This tab breaks down into these parts:

- Clip Details: Lays out data about the clip’s data format (codec, resolution, frame rate, etc.).
- Metadata: Lays out a trimmed set of common metadata fields for quick user entry.

Timecode: The clip’s start timecode. This field is editable when you want to change the clip’s starting timecode by hand. Date Created: The date the clip was created. This field is editable when you want to change the clip’s creation date by hand. Camera: Writes the Camera # metadata. Reel: Writes the Reel/Card ID. Scene: The clip’s Scene number. Shot: The clip’s Shot letter/number. Take: The clip’s Take number. Good Take: This checkbox marks whether the clip is a good or circled take. Clip Color: Hands a particular color to a clip that shows up in the Timeline. Name: This can be typed in by hand and changes a clip’s name only within that specific timeline. Comments: Tack a text description onto the clip.

Auto Select Next Unsorted Clip: With this box ticked, the next clip in the Media Pool is selected once you press the Return button after filling in a metadata field, and the cursor drops automatically into that same field. That enables rapid sequential metadata entry, sparing you from clicking by hand to load each separate clip within the Media Pool. Regardless of the checkbox status, the Next Clip button moves to the next clip in the Media Pool.

### Audio Configuration

The File tab in the Inspector now carries an Audio Configuration pane that takes over the controls once handled by Clip Attributes in the Media Pool (although that option remains available). The Audio Configuration pane gives a more intuitive, visual route to changing an audio clip’s track properties. Just click an audio clip in the Media Pool or Timeline, then the File Inspector, to bring up this interface. The pane sports a per-channel waveform display for every track inside a multichannel audio file. Where the tracks were named in the audio recorder, those names show up over their respective tracks as well. The Audio Configuration panel can preview as many as 36 tracks of audio. Across the top of the pane sits a composite waveform of all the tracks, refreshed according to the mute status of individual tracks. By default this composite plays when the Play button is engaged, and every channel is audible.

The Audio Configuration panel. Here Track 3 sits muted while Track 5 sits disabled. By way of a format menu you pick common configurations for your source audio file, skipping any clumsy manual re-routing. Custom routing is still catered for by choosing custom in the drop-down, which surfaces the older clip attributes for situations calling for less common configurations. To play or skim the audio of a chosen source or timeline clip, glide the cursor across the waveform; the particular track is solo’ed as you skim or play. You can likewise shift, mid-playback, the play position or the track under monitor. For instance, you might begin playback on track one, then simply click track two, and playback carries on from that point. These controls let you swiftly skim through and pin down exactly which audio sits on which track for further adjustment.

Two adjustments accompany each track: an Enable/Disable checkbox plus a Mute button. Enable/Disable: When a track is enabled, it becomes available for editing operations. When a track is disabled, it drops out of editing operations. As an example, if you disable Track 2 of a 4-track audio file, then dragging that audio file from the Media Pool into the timeline brings over only 3 tracks (1, 3, and 4). These adjustments can be made on Media Pool clips alone; audio clips already in the timeline will have these options disabled. Mute: A click on this icon silences the track so it isn’t heard, but the track itself stays present during editing operations and when dragged into the timeline. Option clicking a channel’s mute button solos it by silencing all the other channels. Beneath the track layout sits a plain transport control of Play and Stop buttons for starting and halting audio playback. Adjusting Trim Levels of Individual Channels in a Source File Inside the audio inspector, a trim control lets you set the level of individual source clip channels. With it, audio in one source clip channel can be pushed up or pulled down in level, as the situation calls for. That trimmed level stays internal to the source clip in the Media Pool and carries over wherever that source clip configuration appears on a timeline, until you change it. NOTE: Trim level has nothing to do with clip gain over in the timeline — the two are wholly distinct. Keep in mind that pushing trimmed levels too high can make them clip.

The trim levels of separate audio channels within a multichannel clip are yours to adjust.

Using the Trim slider 1 Within the Audio Configuration section of the File Inspector, pick one or more channels 2 Drag the Level slider along the bottom to whatever audio level you’re after. The waveform shifts dynamically with the level value and shows a trimmed value in dB on the channel itself. With several lanes selected, all channels get trimmed together. Relative levels aren’t stored, so adjusting one then forces any others in the selection to match. With no channel lanes selected, the Level control is grayed out. Multiple Clip Selection and Adjustments Several audio clips can be selected and their properties adjusted in the Audio Configuration pane. For instance, you can pick a batch of audio files and strip Track 2 from every one at once. Bear in mind, though, the following:

- Within a multiple clip selection, only the last selected clip turns up in the track layout of the Audio Configuration pane. The top composite waveform, however, gets named “Multiple Clips” to flag that more than one clip is selected.
- Any adjustment, such as muting or enabling/disabling a track, lands on all the selected clips at once.

### Timecode

The File tab in the Inspector now carries a Timecode pane that assumes the sorts of controls Clip Attributes in the Media Pool used to manage (though that route stays open). From here the timecode details of a clip, or several clips, in the Media Pool can be overridden.
