# Project Settings (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Use Timecode: Governs the way DaVinci Resolve pulls timecode out of the media files it references. You get two choices: Embedded in the source clip: The setting most projects should favor, since it conforms automatically and carries grades onto the clips it produces. Provided DaVinci Resolve can read the timecode from either a media file's timecode track or the header metadata of the frames within a DPX sequence, you're able to lean on timecode to reconform clips, or even swap out entirely the media file a clip points at. From the source clip frame count: A handy option whenever the source media carries no timecode metadata and the only thing on hand is a frame count that labels frames through sequentially numbered integer values.
- Conform partial clips with black gaps: Drops black frames in wherever you conform a clip that's missing some of the frames it needs. With this option turned on, partial clips get marked in the Edit page by a P inside the thumbnail of whichever clip is short on frames.
- Automatically conform missing clips added to Media Pool: On by default; you have to switch it off to run a collaborative workflow. While this checkbox is on, DaVinci Resolve keeps a live link between the clips in the Media Pool and the ones across a project's various timelines. With this checkbox enabled, importing clips whose timecode/file names/reel names line up with clips already in a timeline causes DaVinci Resolve to automatically reconform every matching missing clip, plus all the other timeline clips that have force conform switched off.
- Assist using reel names from the: With this checkbox enabled, DaVinci Resolve leans on reel numbers while conforming clips to align against any imported project. You also have to switch this setting on if you intend to pick distinct reel name extraction methods for individually chosen clips through the Clip Attributes window. Leaving this checkbox off compels DaVinci Resolve to recognize clips by file names while conforming XML and AAF projects. File names work for conforming only XML or AAF files, or when bringing in a DaVinci Resolve project. You get four choices: Source clip file pathname: Derives the reel number by pulling it out of each media file's path. This lets you draw a reel number out of all or some of the file name, or out of all or some of the name of any folder along the path that contains the file. You spell out the extraction in the Pattern field. Pattern: A code spelling out how a reel number ought to be pulled from the source clip path name.

To learn more on building patterns, refer to Chapter 56, "Conforming and Relinking Clips." within "Using the Pattern Field."

Media Pool folder name: The reel number comes from the name of the bin within the Media Pool that contains the clip. People often pick this for stereo projects, drawing the reel number out of directories named "Left" and "Right." It's handy as well for projects taking in fresh VFX clips day by day. Embedding in source clip file: Useful for file formats in which the reel number lives inside the media file itself. QuickTime files originating in Final Cut Pro, along with DPX frame files plus CinemaDNG files, all count as formats capable of carrying reel number header data. Source clip filename: Where no reel number is defined, it's frequently simplest to just fall back on the source clip filename. This is a safe pick in cases where you intend to manually choose distinct reel name extraction methods per clip through the Clip Attributes window.

- Limit reel name matching to X characters: For cases where the media files you were handed carry extra characters in the reel name that don't line up with the names used in the project file you received, "Limit reel name matching to X characters" lets you drop a set number of characters off the end of a reel name. It operates together with the setting that follows.
- Ignore the first X characters of the reel name: For cases where the media files you were handed carry extra characters in the reel name that don't line up with the names used in the project file you received, "Ignore the first X characters of the reel name" lets you drop a set number of characters off the front of the reel name. Paired with the prior setting, you can pare any reel name down to a conformable subset of characters.
- Extract reel names from EDL comments: Media file formats like R3D carry reel names, drawn from the file names, that run past the eight characters a standard EDL permits. This option lets DaVinci Resolve pull reel names out of suitably formatted EDL comments, like the ones produced by Final Cut Pro 7.
- Sort timeline using reel number and timecode: Lets you alter how C mode sorting behaves in the Timeline. With this checkbox on (the default), every clip in the Timeline gets sorted by reel number first and then by source timecode. That way, clips carrying similar timecode off the same reel land beside one another in C mode. Switch this checkbox off and reel number is disregarded, so every clip in the Timeline sorts purely by source timecode. The result can mix clips from several sources together, yet it proves useful in certain cases.
- Mixed frame rate format: (Available only before you import media into a project) From this drop-down menu you pick the method used to conform mixed frame rates for rendering and playback. The option you settle on governs how closely retimed clips inside DaVinci Resolve agree with the same clips after they were retimed in other editing applications, once you bring those timelines into DaVinci Resolve through XML or AAF. This same drop-down menu turns up in the Load AAF or XML dialogs as well.

If you're editing from scratch in DaVinci Resolve: Just leave this setting on "Resolve." When importing timelines via XML from Apple software: Pick either the "Final Cut Pro 7" or "Final Cut Pro X" conform methods. When bringing timelines in through XML or AAF originating in Premiere Pro, Media Composer, Smoke, or any other NLEs: Go with "Resolve." When none is selected: DaVinci Resolve conforms and processes every clip in the Timeline so they play at whichever frame rate is picked in the "Timeline frame rate" drop-down menu. As an example, 23.98, 29.97, 30, 50, 59.94 and 60 fps clips will every one play back at 24 fps when that's the value "Timeline frame rate" carries in the Master Project Settings, and clips run slower or faster to match. The way clips in mixed frame rate timelines render out hinges on whether the Render Settings are configured to render individual source clips or a single combined clip. Render the Timeline as individual source clips and each clip renders on its own at its native frame rate. Pick "single clip" and every clip converts to the "Timeline frame rate" frame rate and renders as one media file.

### Color

These settings shape clip versions and timeline behavior while you work on the Color page.

- Automatically label gallery stills using: Once turned on, DaVinci Resolve auto-builds labels for every gallery still you grab, drawing on the controls below:

Naming drop-down: Lets you settle on what name new stills should carry. Among the choices you'll find Clip Name, then Clip Version Name, plus Source Timecode, alongside Timeline Timecode, as well as Timeline Name, together with Display LUT Name, and finally Custom Label Using Tags (drawing on metadata variables). Append still number on export checkbox: Once turned on, each fresh still picks up an appended still number. Where that number lands depends on the radio buttons below. As Suffix/As Prefix buttons: Let you settle on placing still numbers at the tail of an auto generated gallery label or at its head.

- Luminance mixer defaults to zero: Picking this option drives the Y channel of the YRGB parameters down to zero across every grade. It's a prerequisite for exporting a compliant ASC-CDL, and it touches every grade relying on the Lum Mix control.
- Use legacy Log grading ranges and curve: DaVinci Resolve 12.5 brought in a change to the Log grading controls that yields smoother, more agreeable results from the same controls. To keep older projects working as before, the Color panel of the Project Settings carries a "Use legacy Log grading ranges and curve" checkbox that toggles a given project across the older Log control behavior versus the newer one. When DaVinci Resolve opens an older project, this checkbox comes on by default, while a freshly created project comes with it off by default.
- Use S-curve for contrast: Enabled by default, this checkbox makes the contrast control in the Color Wheels palette lay an "S-curve" over the image, so a signal's shadows and highlights won't clip as you raise the value. Should you rather have those contrast adjustments applied linearly, with the signal permitted to clip once it hits the top and bottom limits of the video signal, you can switch this checkbox off.
- Use legacy sizing interactions for windows and effects: In version 14.1.1, DaVinci Resolve reworked how window tracking lays down its transformations, letting it now handle things like pixel aspect ratio (par) correctly. New projects ought to keep this setting off, though older projects ought to keep this checkbox on so tracking and transforms stay applied the way they were beforehand.
- Apply stereoscopic convergence to windows and effects: Once turned on, DaVinci Resolve correctly holds the position of a window that's been properly set over each eye while convergence shifts in the 3D palette. Switching this checkbox on also surfaces an extra Convergence parameter in the Window palette that lets you build properly aligned convergence for a window placed atop a stereoscopic 3D clip, as the screenshot below shows.

l Within the Transform section of the Window palette, the Convergence control surfaces once "Apply stereoscopic convergence to windows and effects" is switched on

- Use local version for new clips in timeline: Automatically configures every new clip added to existing timelines, plus every clip added to new timelines brought in through AAF, EDL, or XML, to default to local grades. Should you want every clip added to new timelines to lean on remote grades instead, the way DaVinci Resolve version 9 and earlier did, you can switch this checkbox off.
- Automatically match master timeline with media pool: Switch this option on before importing any media into the Media Pool, or before importing any timelines that will themselves pull media into the Media Pool, and you can build projects holding a Master Timeline. Once enabled, clips join and leave the Master Timeline as they join and leave the Media Pool, so the Master Timeline forever holds all media within the Media Pool. After media has been brought into a project, this setting can no longer be altered.
- Save timeline thumbnails with project: To keep project size down and saving and loading projects fast, you ought to leave this checkbox off. Tick the checkbox and all of your Timeline thumbnails get tucked inside every project, rather than in the default directory normally set aside for stills, throughout both Save and Auto Save operations. That gives you a solid record of the project but takes far longer to finish and eats more hard disk space.
- Use BGR pixel order for DPX v2: Lets you settle on a different pixel order for projects relying on DPX version 2 media.
- Embed timecode in audio output: Switch this on and DaVinci Resolve sends out LTC timecode riding on channel 16 within the SDI stream plus channel 2 of the analog audio output that comes off your video interface.
- Use Timelines Bin: You can only change this option before adding clips to the Media Pool; once you've added clips, it's no longer available. Switching Use Timelines Bin on builds a dedicated Timelines bin within the Media Pool, sitting at the top of the Bin List. Once enabled, the Timelines bin holds every timeline in a project, and you're blocked from dropping timelines into any other bin in the Media Pool. Each time you create or import a new timeline, it shows up automatically in the Timelines bin. You're free to add subfolders beneath the Timelines bin for finer organization.

### Dynamics Profile

Establishes, for keyframed effects on the Color page, the default move from a given dynamic keyframe across to the one after it. By default that move is linear, the "Dynamic profile start" and "Dynamic profile end" parameters sitting at 1 apiece. That said, when you need to change the acceleration of how values interpolate from one dynamic keyframe to the next, you can alter that keyframe's Dissolve Type to "ease" the effect transition you're building. What these settings hold corresponds to the graph curves shown in the Dynamic Attributes dialog as you edit keyframes on the Color page. To learn more, refer to Chapter 148, "Keyframing in the Color Page." within ""Changing Dynamic Attributes"".

### Versions

Ten text fields give you a means of assigning automatic names for the versions of grades you pick on the Color page. Beside every text field sits a drop-down menu letting you pull a name from a convenient list of predefined terms that's been supplied. Alternatively, you can just click any field and type a custom name of your own. Once you rename a version on the Color page, whatever names you configured in this list show up through a drop-down menu inside the Version Name dialog. Working with the named drop-down while renaming a version Relying on a ready-made list of names for your different versions heads off the typos that can later cause folder naming trouble once you turn to the "Commercial Workflow" options for rendering your media on the Deliver page.

### Camera Raw

This panel holds groups of parameters lining up with every camera raw media format DaVinci Resolve supports. Working with the controls inside the Camera Raw panel, you're able to supersede whatever original camera metadata got written down at the moment of capture, and tune every camera raw clip at once by way of the "project" raw settings. For fuller detail, these settings get their own dedicated chapter. For more information, see Chapter 130, "Camera Raw Palette."

### Capture and Playback

All of this panel's settings let you shape the behavior of capture and playout to tape using device-controlled VTRs tied into your Resolve workstation via whichever video capture and output interface is attached. To read up on deck capture, turn to Chapter 24, "Ingesting From Tape." To read up on video output to tape, turn to Chapter 189, "Delivering to Tape."

### Deck Settings

Both capture and playback come under these settings whenever you rely on the tape ingest controls of the Media page or the tape output controls of the Deliver page.

- Video capture and playback: From this drop-down menu you can pick the video format (frame size and frame rate) to output to tape with. An HD timeline can be downconverted to SD, while an SD timeline can be upconverted to HD by way of the format conversion built into your DeckLink card.
- Use left and right eye SDI: A checkbox letting supported video interfaces ingest and output muxed stereoscopic video when paired with supported VTRs, such as HDCAM SR decks running 4:2:2 x 2 mode. (As muxed stereoscopic signals come in, each eye splits into separate left-eye and right-eye image files.) This parameter shows up only when your hardware is configured for it.
- Video connection operates as: Picks among the signal options on offer: Use 4:4:4 SDI and Enable Single Link. Which options you see hinges on which video capture card you're running.
- Data Levels: Lets you set the data range (normally Video or Full) applied while ingesting from or outputting to tape. This option flips the data range of the signal your video capture card outputs, but solely during capture from tape on the Media page, or output to tape on the Deliver page. Whenever neither capture nor output is in progress, your video capture card falls back on the same-named data range setting over in the Master Project Settings pane, the one controlling how you monitor whatever signal gets sent to an external broadcast display or projector.
- Video bit depth: Pick the bit depth that suits what your deck can handle. According to how your workstation is configured, the options are 8-bit or 10-bit. Going with 10-bit puts more load on the processor, yet yields higher quality on compatible devices, and serves as the default setting.
- Use deck autoedit: When your video deck supports it, this is the best way to record video to the deck, since it lets the deck roll the edit using the specified preroll and govern the edits through serial device control. Switch this checkbox off and the deck falls back on a basic edit On/Off mode, with a chance of frame inaccuracies should the "Non auto edit timing" setting not be dialed in properly.
- Non auto edit timing: Tunes the edit synchronization of the connected deck while auto edit is off.
- Deck preroll: Sets how many seconds of preroll to use. What's right depends on how your deck performs.
- Video output sync source: With a DeckLink card this sits at Auto. With other capture cards you may have to point the sync source at "Reference" for playout and at "Input" for ingest. You'll see this setting only if a DVS card is installed on your system.
- Add 3:2 pulldown: Inserts or removes the 3:2 pulldown that's required whenever 23.98 fps media has to be recorded onto, or played back off, a 29.97 tape format.

### Capture

These settings come into play while you use the Capture mode on the Media page to capture clips off tape into the Media Pool.

- Capture: Lets you settle on capturing both Video and Audio, or Video Only.
- Video Format: The format scanned film frames are saved as. When capturing from tape, the

choices on offer are DPX and QuickTime. While capturing from the Cintel film scanner, this is held to Cintel Raw Image (CRI); that's a raw data format which DaVinci Resolve debayers on its own into a Cineon log-encoded image ready for grading.

- Codec: The codec applied while writing captured media. Capturing off tape, the choices span the assorted Apple ProRes variants, plus 8- and 10-bit YUV 422, then 10-bit RGB, together with the assorted DNxHD variants. Cintel Raw Image files default to rgb.
- Save in folder path: A row of checkboxes lets you spell out what additional information to draw on for the directory hierarchy that will hold the captured media. Each checkbox you turn on adds another directory whose name comes from that checkbox's metadata. You can pick any or all of these: Program name, Clip number, Reel number, and Roll/Card.
- Apply reel number to: Lets you settle on how the reel name gets written. Two checkboxes let you write the reel number into the file's name and/or into the Header data.
- Use prefix: A field lets you type a prefix to use within the media file's name. This lets you tack on text identification that makes the media easier to spot and search for.
- Apply prefix to: A pair of checkboxes let you choose to apply whatever prefix you entered within the file name and/ or within the folder name.
- Use frame number with: While capturing to image sequences, you can settle on how many digits to use while writing the frame number into each frame file's name.
- Set batch ingest handles to: While capturing to image sequences off a batch list, defines how many frames of extra handles to ingest alongside each logged clip.
- Input: Lets you settle on how many tracks of audio to capture, from 2 to 16.

### Playout

These settings shape only the video signal output while you use the Edit to Tape mode of the Deliver page.

- Output: Lets you settle on outputting both Video and Audio, Video Only, or Audio Only when you're doing an audio layback.
- Output Source Timecode: Switch this checkbox on to output each clip's own source timecode. This option applies solely while assemble editing to tape.
- Output LTC: With a Blackmagic Design DeckLink or UltraStudio device on HD-SDI, longitudinal timecode (LTC) rides on track 16 of the HD-SDI video signal, making it simple to use a Mini Converter de-embedder to pull this analog timecode audio signal off and feed it straight into a recording device. That's especially handy when you've got outboard video processing gear such as a noise reducer or format converter that passes the VITC timecode through.
- Delay LTC by x frames: When you send LTC out so it bypasses outboard processing hardware (a noise reducer or format converter, say), you're able to make up for the processing delay by pushing the timecode back by some frames, ensuring the processed image and its timecode land at the deck at the same moment. With a DVS card there's a separate timecode output.
- Offset audio by x frames: Lets you set an offset between the audio track and video to land proper A/V sync in cases where outboard processing hardware is delaying the video.
- Output x channels of audio: Pick how many audio tracks to output to tape.
- Set batch playout head handle to x seconds: While batch outputting multiple clips, you can spell out a number of frames ahead of each clip's In point to be output as well.
- Set batch playout tail handle to x seconds: While batch outputting multiple clips, you can spell out a number of frames past each clip's Out point to be output as well.

### Subtitles and Transcription

The Subtitles panel lets you tune presets governing subtitles being built within subtitle tracks of the timeline.

- Max Character Per Line: Defaults to 60. Lets you settle on the largest number of characters permitted on a single line within a subtitle.
- Minimum Caption Duration: Defaults to 3 seconds. Lets you settle on the shortest duration permitted for subtitles in the timeline.
- Maximum Characters Per Second: Defaults to 30. Automatically works out the largest allowable characters per second from a subtitle clip's duration.

The Transcription setup panel lets you pick the language DaVinci Resolve relies on to analyze audio clips for transcription. Language: Pick one of the supported languages here. Picking Auto lets DaVinci Resolve study the audio clip and settle on the language being spoken.

### Fusion

Fusion permits consistent frame numbering across all compositions, trimmed clips included. What this means is that any composition built in Fusion can begin from the same start frame number. In new projects you can alter the default start frame for Fusion compositions within the project settings.

- Legacy Fusion Composition Frame Count: Pins the Fusion composition at zero frames to the first frame of the composition's source media.
- Default Start Frame: Lets you type a default frame number to begin your fusion comps in this project on.

This aids Visual FX workflows three ways:

- Matching existing keyframes to the right frame offsets—while swapping in an asset whose

frame offsets don't line up (for instance a sub clip, a differing format or round trip, or VFX connect workflows where the handles fail to match).

- Rendering to specific frame ranges—when conforming to the delivery standards of commercial workflows (for instance, having compositions begin at sequence frame 1000).
- Consistent Referenced Comp behavior—indispensable while applying a referenced composition to different clips with different trims.
- Downscale to Timeline Resolution for Timeline Clip Compositions: To lift playback performance on complex fusion projects, you can tick this box to automatically downscale all media to the timeline resolution ahead of fusion operations running. This does not work with .exr media however.

### Fairlight

Through the Fairlight panel you can establish the audio sample rate for your project, as well as configure a range of audio-specific tools found on the Fairlight page.

### General

### Audio Sample Rate
