# Project Settings (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Project Settings

The settings that define what each separate project is made of are the focus of this chapter. Getting acquainted with what's here before you build your very first project is a wise move.

### What Are the Project Settings?

Every project-specific parameter stored alongside a given project lives in the Project Settings window. Among them are core project properties: the timeline format, video monitoring choices, the approach to optimizing media, and the destination for cache files. Image scaling properties, color management options, and a host of other properties that shape projects at a deep level are in there too.

### Opening and Editing Project Settings

From any point inside DaVinci Resolve, you reach all of these project-specific settings simply by clicking the gear button at the lower right of the page bar.

### Project Manager and Project Settings buttons

Onscreen, the Project Settings window opens up centered.

### Project Settings window

A sidebar down the left side of the Project Settings window lets you pick from a row of panels into which it's split. Every panel holds a cluster of related settings governing one category of DaVinci Resolve behavior. To alter project settings: 1 In the left sidebar, click the name of whichever settings group you want, which opens that panel. 2 Adjust the settings as required. 3 To commit your changes, do one of these: Click Save to commit them and shut the Project Settings. Option-click Save to commit them yet leave the Project Settings window open for further changes. That choice exists because keeping the Project Settings window open is sometimes needed as you go on making changes whose effect may show up visibly on the clips and timelines in your project.

### Presets

Saving tailored bundles of Project Settings for later reuse is what the Presets menu is for. A preset can capture the condition of nearly every parameter and setting across every panel of the Project Settings window, which makes hopping between different setups for different tasks, or fitting different kinds of projects, painless. You get to the Presets menu by clicking the option menu (three dots) at the top-right corner of the Project Settings window. These are the items the Presets menu shows:

- Project Settings Presets: Every existing Project Preset is listed here, with the Default Preset at the top.
- Set Current Settings as Default Preset: Picking this writes the present Project Settings out as the fresh Default Preset.
- Save Current Settings as Preset: Picking this stores the present Project Settings as a brand-new preset, which then turns up in the menu list overhead.
- Import Preset: Picking this opens a file browser so you can pull in a DaVinci Resolve Project Settings Preset file. These files carry the .preset extension.

Through this menu you can build, import, and export presets of your own, piling up however many you require for the kinds of projects you take on.

Reaching the Presets Menu means clicking the option menu within the Project Settings window

To create a new preset: 1 Do one of the following:

- In the Project Manager, right-click a project and pick Project Settings off the contextual menu.
- Open any project and then bring up the Project Settings.

2 Use the assorted panels of the Project Settings window to set whatever settings you require. You needn't save along the way; it all saves together later. 3 In the top-right corner of the Project Settings window, click the option menu (three dots). 4 Select Save Current Settings as Preset. 5 Into the dialog box, type a descriptive name for the new preset, then press the OK button. 6 The Project Settings Preset menu now lists your new preset name. Once a custom preset or two exists, you're free to load them into a project at any moment. To pull a preset's stored settings into a project: 1 Open the project whose preset you mean to update. 2 Bring up the Project Settings window. 3 In the Project Settings window, click the option menu. 4 Click the Project Preset name you'd like applied to the open project. 5 From the drop-down menu, select Load Preset. The new preset's values are applied to the Project Settings right away. This function has no undo. To update a preset: 1 Bring up the Project Settings window. 2 Run through the assorted panels of the Project Settings window to change whatever needs updating. 3 In the Project Settings window, click the option menu. 4 Click the Project Preset name you want updated. 5 From the drop-down menu, select Update Preset, then pick Update in the dialog box. Your current settings overwrite the preset. This function has no undo. To set the default preset: 1 Out of the Project Settings Presets list, pick the preset you want loaded each time a new project begins. 2 Click the preset and pick Set As Default Preset. or 1 From the Project Settings window's option menu, choose "Set Current Settings as Default Preset" to turn whatever your settings currently are into the new default. 2 Pick Update in the dialog box. Your current settings overwrite the preset. This function has no undo.

To export a preset: 1 Out of the Project Settings Presets list, click the preset you plan to export. 2 From the drop-down menu, choose Export Preset. 3 Within the file browser, supply a name and save spot for the preset, then press Save. The DaVinci Resolve Project Settings Preset file arrives there with a ".preset" extension. To import a preset: 1 Within the Project Settings window, click the option menu. 2 Select Import Preset. 3 Through the file browser, navigate to the DaVinci Resolve Project Settings Preset file you'd like to bring in. The ".preset" extension marks it. Press Open. To delete a preset: 1 Out of the Project Settings Presets list, click the preset you'd like gone. 2 From the drop-down menu, choose Delete Preset. 3 In the dialog box, press Delete. The Project Settings disappear at once. This function has no undo.

### Master Settings

Project-specific, this panel is where you establish and tune the most fundamental properties of your project's timelines, the timeline format, the video monitoring method, and conform options among them. Plenty of workflows call for tuning these before you even begin a project. Out of the box, every timeline draws on these project-wide settings. That said, from DaVinci Resolve 16 onward, you may instead build timelines that carry their own individual Format, Monitoring, and Output Sizing settings. Still, switch a timeline over to "Basic Settings" and it falls back in line with the project-wide options picked in the Project Settings.

### Timeline Format

The current project's geometry and image processing are governed by this group of settings.

- Timeline resolution: A drop-down menu from which you pick a frame resolution preset that image processing uses during grading. Because DaVinci Resolve is resolution independent, you're free to swap the resolution whenever, and every window, track, sizing change, and bit of keyframe data is recomputed on its own to suit the new size. You could, say, grade a 4K project while monitoring at HD if your suite holds only an HD monitor, then render the completed project at 4K for final delivery. Or you might shrink an HD project down to SD to produce a second set of deliverables.

For deeper coverage of Resolve's resolution independence, turn to Chapter 152, "Sizing and Image Stabilization.""

- Frame size (Labeled "For X x Y processing"): Lets you dial in resolutions absent from the "Timeline resolution" drop-down menu.
- Use vertical resolution: Ticking this checkbox flips the horizontal and vertical pixels of the Timeline resolution. That lets you lay out a timeline vertically for showing on phones, tablets, or upright-mounted televisions used as digital signage.
- Pixel aspect ratio: Serves to pick PAR settings for image formats outside the default square pixel format. Among the choices: a 16:9 anamorphic PAR, for SD projects a 4:3 PAR, or else a Cinemascope ratio.
- Timeline frame rate: Fixes the project's main frame rate. Both standard and high frame rate (HFR) options are on offer. Importing an AAF or XML file sets this automatically through a choice in the Project Import dialog. The best practice is to settle on a frame rate ahead of bringing media into the Media Pool. Even so, the very first time you import media into an empty Media Pool, you're asked about it when the incoming media's frame rate differs from the Timeline frame rate fixed here, and you may have this setting updated automatically to match the media you're bringing in. After one or more files have landed in the Media Pool, the setting can no longer be altered.
- Use drop frame timecode: Switches drop frame timecode on or off for the current project. Off by default.
- Enable interlace processing: Interlaced media is supported throughout DaVinci Resolve. Ticking the "Enable interlace processing" checkbox makes DaVinci Resolve run every internal operation on separated fields, so the field integrity of your program's interlaced clips stays intact. On top of that, each Media Pool clip has, within the Clip Attributes window's Video panel, a Field Dominance drop-down menu for declaring whether clips are upper- or lower-field dominant; an Auto setting makes that call by default. A matching checkbox named "Field rendering" also sits in the Render Settings panel of the Deliver page, switching field rendering on or off as you render file-based output.

Two situations call for keeping this setting off:

- With progressive-frame media, switching this checkbox on serves no purpose. It only pads processing time needlessly.
- If you've got interlaced clips inside a progressive-frame project and you mean to deinterlace them with the Enable Deinterlacing checkbox in the Clip Attributes window, then "Enable video field processing" has to stay off. If not, the Enable Deinterlacing checkbox goes disabled for every clip.

For more on deinterlacing clips, turn to Chapter 22, "Modifying Clips and Clip Attributes." On a project whose interlaced media you plan to keep interlaced, whether you even need field processing on hinges on the kinds of corrections you put on your clips. When you're mastering your program to an interlaced format and applying any adjustment that would push or smear pixels from one field into neighboring fields, field processing ought to be on; effects that demand it include filtering work such as blur, sharpen, and OpenFX operations, plus sizing transforms covering pan, tilt, zoom, rotate, pitch, and yaw. By contrast, no matter whether your output is interlaced or progressive-frame, when you aren't filtering or resizing clips and you're only tweaking color and contrast, field processing isn't needed on interlaced material, and indeed leaving it off may trim your project's rendering time a little.

- Align Clips to Frame Boundaries: With interlaced material, you get to decide whether edits land on field or frame boundaries. Tick it and every editing action and playhead step happens on full frame boundaries. Since this runs apart from the audio subframe controls, flawless audio sync is still attainable while you handle video at the frame level. Leave it unticked and every editing action and playhead step instead happens on the field boundary.
- Playback frame rate: Normally tracks the frame rate chosen in the "Video format" setting (down in the Video Monitoring section), which itself usually follows the frame rate of the external display wired to your video interface, given the "Timeline Frame Rate" setting. A 50Hz monitor, for one, needs a 25 fps playback frame rate to display in sync without dropping frames. To monitor playback at a lower frame rate, enter the frame rate you want in this field and DaVinci Resolve runs the math to drop or repeat frames as required to hit it. That's handy for briefly checking how clips read in slow motion.

### Video Monitoring

The settings in this group steer the signal sent out by the video output interface attached to your workstation, letting you state which signal standard goes out and along which signal path. Out of the box, the frame size and frame rate echo whatever sits in the Timeline resolution and Playback frame rate options. Should you need to, though, you can shift these settings to match the external display you monitor on. For instance, if your files are 2K bound for 2K output yet you grade on a high definition monitor set to 1080, you can pick the right HD standard for that monitor without touching the Timeline Resolution settings.

- Video Resolution: Picks a standard video frame size for output through the video output interface you've connected.
- Format: Picks a standard video frame rate sent out across the video output interface you've connected.
- Video connection checkboxes: Sets which signal standard travels from your connected video output interface over to the video monitor. Be sure the standard you pick is one both your video interface and your monitor handle.

Here are the options: Use 1080PsF: Puts progressive video out as 1080i so older HDTV sets can take it. Use 4:4:4 SDI: A signal path for feeding image data to monitors that handle 4:4:4 chroma sampling, usually across SDI connections. Use Level A for 3Gb SDI output: A signal path that carries image data over one 3 Gb/s SDI connection. Use dual outputs on SDI output: Every DaVinci Resolve system can build a side-by-side display deliverable to a Stereoscopic monitor through the HD-SDI output of an UltraStudio 4K or DeckLink card. With dual SDI 3D monitoring switched on, each eye goes out separately at full resolution. While in this mode, split-screen wipes and cursors stay hidden on the grading monitor.

- SDI Configuration: Picks between Single Link, Dual Link, and Quad Link SDI according to what your display can take.
- Data Levels: Only the data levels leaving the video interface that links the DaVinci Resolve workstation to your external display are touched by this setting. It does nothing to the data DaVinci Resolve handles internally, nor to the files written when you render on the Deliver page. The option you pick in DaVinci Resolve absolutely has to match the data range your external display is set to. Otherwise the video signal will look wrong, even while the internal data keeps being processed correctly by DaVinci Resolve.

Two options exist: Video: This is the right pick when your broadcast display is set to the Rec. 709 video standard. Full: Use this option when your monitor or projector can show "full range" video signals and you want to monitor the entire 10-bit data range (0–1023) as you work. For more on data levels, turn to Chapter 9, "Data Levels, Color Management, and ACES."

- Retain sub-black and super-white data: Switch this checkbox on and DaVinci Resolve sends the undershoots (sub-black) and overshoots (super-white) that live within the headroom of video encoded data levels out to video. Switch it off and those out-of-bounds values get clipped in the video output.
- Video bit depth: Pick the bit depth that suits what your display can handle. The choice is between 8-bit and 10-bit. Monitoring at 10-bit taxes the processor more, but it's the better pick for avoiding the look of banding that may not actually exist in the image data DaVinci Resolve is processing.
- Monitor scaling: Sits at basic by default and only kicks in to soften the edges of video shown on a projector across very large screens. These settings cut down high frequency artifacts that might otherwise appear. The effect can also show when you've got a 2K or HD project but you're monitoring on an SD monitor. Its other option, Bilinear, treats the monitored image differently depending on your display device, so you may want to confirm it suits your setup.
- Use Rec601 Matrix for 4:2:2 SDI output: Leave this checkbox alone unless its purpose is already clear to you. You know who you are.
- Enable HDR metadata: (only available in Studio version) Tick this checkbox to output the metadata needed for High Dynamic Range signals to travel over HDMI 2.0a and be decoded properly by an HDR-aware video display. With this checkbox on, it's advisable to switch on the "HDR mastering is for X nits" checkbox on the Color Management page as well, and dial the "nit" level (slang for cd/m2) to whatever peak luminance your HDMI-connected HDR display can reach.

### Optimized Media and Render Cache

The resolution and codec of the optimized media DaVinci Resolve can build for stronger real time performance are set by these settings, along with the cached media produced by the Smart and User Cache.

- Proxy media resolution: Through a drop-down list, you decide whether proxy media is built at each clip's Original size, at Half, Quarter, One-Eighth, or One-Sixteenth of the original media's resolution, or whether DaVinci Resolve picks this for you automatically from your timeline settings.
- Proxy media format: Names the format the proxy media files get written in. A range of Uncompressed, ProRes, and DNxHD formats is open to you, per your needs.
- Optimized media resolution: A drop-down list is where you decide whether optimized media is built at each clip's Original size, at Half, Quarter, One-Eighth, or One-Sixteenth of the original media's resolution, or whether DaVinci Resolve picks it automatically from your timeline settings.
- Optimized media format: Names the format the optimized media files get written in. Pick from a range of Uncompressed, ProRes, and DNxHD formats, per your needs.
- Render cache format: Names the format the render cache files get written in. A range of Uncompressed, ProRes, and DNxHD formats is available, per your needs.
- Enable background caching after X seconds: Sets the stretch of idle time after which automatic background caching kicks off. A row of checkboxes lets you push particular effect types into the cache when you run the User Cache, a more selective form of caching than the Smart Cache. Among them: Automatically cache transitions in user mode: When you're in User mode and find your workstation can't play transition effects in real time, you can compel these effect categories into the Sequence Cache so they're cached while you use the User mode of caching.

Automatically cache composites in user mode: When you're in User mode and find your workstation can't play composite mode or opacity effects in real time, you can compel these effect categories into the Sequence Cache so they're cached while you use the User mode of caching. Automatically cache Fusion effects in user mode: When you've built effects for a clip on the Fusion page and find your workstation can't play that clip in real time, you can compel these effect categories into the Sequence Cache so they're cached while you use the User mode of caching.

### Working Folders

Which folders receive cache and gallery files is what these fields let you set.

- Project media location: Lets you pick a particular folder on your system to house every piece of generated media made for that project. Generated media covers things like fresh audio files born of the Voiceover tool and Voice Convert, or really any new media DaVinci Resolve itself creates. This keeps all of a project's media gathered in one shared spot, which eases handing off, moving, or relinking media instead of leaving some inside DaVinci Resolve's internal file structure and some out on a media drive. DaVinci Resolve spins up new subfolders at your chosen media location by media type on its own, which makes shipping some or all generated media elsewhere easy. This location can also be assigned in the Create New Project dialog as you set up a new project.

Within the project media location, DaVinci Resolve builds subfolders by itself to keep any media generated inside the program organized.

- Proxy generation location: Every proxy media file you produce is written to the directory path this field names.
- Cache files location: Every render cache file you make is stored at the directory path this field names. By default that path points to a hidden "CacheClip" directory created at the spot of the first Media Storage Volume you designate in the DaVinci Resolve Preferences window.
- Gallery stills location: By default each still you save is written in the DPX format and dropped at the directory path this field names. By default that path points to a hidden ".gallery" directory created at the spot of the first Media Storage Volume you designate in the DaVinci Resolve Preferences window.

NOTE: Should the volume you've chosen for the cache go offline, DaVinci Resolve raises a warning dialog.

### Frame Interpolation

The default behavior of every retiming and speed change effect, mixed frame rate timeline clips included, is decided by these settings.

- Retime Process: From this drop-down menu you set a default way of handling clips that don't line up with the project frame rate in mixed frame rate timelines, plus clips carrying speed effects (fast forward or slow motion), across the whole project. Because every clip in every timeline starts at "Project Settings," altering this setting changes how most mixed frame rate and speed-affected clips are handled, apart from those given custom settings.

Three options exist: Nearest: The least sophisticated yet most processor-efficient approach; frames get dropped for fast motion or duplicated for slow motion. Frame Blend: Likewise easy on the processor but capable of smoother output; neighboring duplicated frames are dissolved into each other to even out slow or fast motion effects. When Optical Flow throws up unwanted artifacts, this option can do better. Optical Flow: The most processor intensive yet highest quality way of handling speed effects. Through motion estimation, fresh frames are built from the original source frames to make slow or fast motion effects. When a clip's motion runs linear, the outcome can be remarkably smooth. Two elements crossing in opposite directions, or erratic camera movement, can however bring on unwanted artifacts.

- Motion estimation mode: Whether you're running mixed frame rate clips in a timeline with Optical Flow retiming on, leaning on Optical Flow to handle speed change effects, or working the Image Stabilization or Temporal Noise Reduction controls on the Color page, the Master Settings' Motion Estimation dropdown (over in the Project Settings window) hands you options that balance speed against quality.
