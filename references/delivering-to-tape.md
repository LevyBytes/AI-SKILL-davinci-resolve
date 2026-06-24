# Delivering To Tape

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Delivering to Tape

This section explains how the Deliver page lets you send a timeline, whole or in pieces, out to a device-controllable VTR hooked up to a compatible Blackmagic Design video interface. No matter which output interface you settle on, confirm that the RS-422 interface ties into the VTR's own and that device control is up and running.

### The Tape Output Interface

You carry out tape output from the Deliver page, but only after switching it into Tape mode. To flip the Deliver page over to tape output:

- Click the Tape button, the third one in from the left along the Interface toolbar at the top of DaVinci Resolve. The Deliver page then refreshes to surface the controls that pertain to editing to tape.

Once Edit to Tape mode is active, you drive the VTR from the Deliver page, marking In and Out points for an insert or assemble edit of the chosen stretch of the current Timeline out to tape.

- Capture and Playout: The Render Settings panel becomes the Capture and Playout panel, holding the controls and settings that dictate how DaVinci Resolve sends your program to tape.
- Edit to Tape Queue: The Render Queue becomes the Edit to Tape Queue, where you can assemble a batch made up of already-rendered media files or In- and Out-point-bounded slices of the current Timeline, all for output to tape together.
- Transport controls: Though they look much like the ones in Render mode, the transport controls here drive the VTR instead.
- Shuttle control: A shuttle control takes the place of what used to be the jog or scrubber bar, letting you sweep across whatever reverse and forward speeds the deck supports.
- In and Out controls: Under Edit to Tape mode, the In and Out buttons sitting right of the transport controls stake out a span of tape to Insert or Assemble edit onto from within the current Timeline. Still in Edit to Tape mode, marking In and Out points for a particular stretch of the Timeline is also possible: right-click a clip over in the Thumbnail or Mini‑Timeline and pick Mark In or Mark Out. In and Out points can only land at the start and finish of clips.
- Cue In and Cue Out controls: The buttons beside the timecode In and Out fields cue the tape to those particular frames on tape.

### Edit to Tape controls

### Gang Timecode to Tape

With the Deliver page sitting in Tape mode, right-clicking the ruler that runs across the top of the Timeline and picking “Gang Timecode to Tape” throws DaVinci Resolve into a state where setting an In point on the Deliver page Timeline automatically drops a matching In point on the tape deck. Lay down both In and Out points on the Deliver page Timeline and the deck's In and Out points get placed at the identical timecode, which makes layering insert edits onto an already-output program straightforward.

### The Gang Timecode to Tape option

### Insert/Assemble Dropdown Menu

Beneath the In and Out buttons, a dropdown menu sets how the chosen portion of the Timeline gets edited to tape. It carries two choices:

- Insert: Carries out an insert edit to tape, where the selected tape tracks get overwritten cleanly and frame-accurately while the timecode and control track keep running. An insert edit demands that you output to either a blacked tape or a prerecorded one.
- Assemble: Carries out an assemble edit, where every tape track gets overwritten, the video, audio, timecode, and control tracks included.
- Crash: (Shows up only when “Output Source Timecode” is switched on within the Playout area inside the Project Settings' Capture and Playback panel) Much like an assemble edit, save for the absence of a pre-roll period to bring the VTR up to speed. A crash edit likewise overwrites every track of the tape, video, audio, timecode, and control tracks alike, and can leave a more noticeable jump right at the edit point. Even so, there are situations where a crash edit is the sole option available for a given task.

NOTE: While DaVinci Resolve runs a Batch Output operation, the only ways to output clips are assemble editing or crash recording.

### Start Record Button

After you've placed In and Out points to bound how much tape gets recorded onto, the Start Record button kicks off device-controlled output to tape.

### Setting Up for Tape Output

Ahead of any edit to tape, the Capture and Playback panel of the Project Settings holds several options you'll want to dial in so they line up with the format and style of tape output you're undertaking.

### General Options

Switch on the Output LTC checkbox and DaVinci Resolve is told to send out LTC timecode.

### Capture and Playout Settings

These options govern capture as well as playback whenever you're using the Media page's Tape Ingest options or the Deliver page's Tape Output options.

- Video capture and playback: This dropdown is where you pick the video format (frame size and frame rate) used to output to tape. Your DeckLink card's format conversion can downconvert HD timelines to SD and upconvert SD timelines to HD.
- Use left and right eye SDI: A checkbox letting supported video interfaces take in and put out muxed stereoscopic video alongside supported VTRs, HDCAM SR decks running 4:2:2 x 2 mode among them. (As muxed stereoscopic signals come in, each eye is split off into its own left-eye and right-eye image files.) This parameter surfaces only when your hardware is configured for it.
- Video connection operates as: Chooses among the signal options on offer: Use 4:4:4 SDI, and enable Single Link. Which of them you'll see hinges on the video capture card in use.
- Data Levels: Lets you set the data range (typically scaled or full range) applied as you ingest from or output to tape. The toggle swaps the data range of the signal your video capture card emits, but solely during capture from tape on the Media page or output to tape on the Deliver page. Outside of active capture or output, your video capture card reverts to the like-named data range control found under the Project Settings' Master Settings panel, the one steering how you monitor the signal sent to an external broadcast display or projector.
- Video bit depth: Pick the bit depth that fits what your deck can handle. The options are 8-bit and 10-bit. A 10-bit output taxes the processor more but delivers higher quality on compatible gear, and it's the default.
- Use deck autoedit: Where your video deck supports it, this is the surest way to lay video onto the deck, since it has the deck roll the edit on the stated preroll and govern the edits through serial device control. Leave this checkbox off and the deck falls back to a plain edit On/Off mode, which risks frame inaccuracies unless the “Non auto edit timing” setting is dialed in correctly.
- Non auto edit timing: Tunes the edit synchronization of the attached deck while auto edit is switched off.
- Deck preroll: Sets how many seconds of preroll to use. The right amount turns on how your deck performs.
- Video output sync source: With a DeckLink card this stays at Auto. Other capture cards may need the sync source set to “Reference” for playout and “Input” for ingest. The setting appears only if a DVS card is installed in your system.
- Add 3:2 pulldown: Adds or strips the 3:2 pulldown needed to record or play 23.98 fps media onto or off a 29.97 tape format.

### Capture

You'll reach for these options when capturing clips off tape into the Media Pool through the Media page's Capture mode. The media comes in as DPX image sequences.

- Capture: Lets you decide between pulling in both Video and Audio or Video Only.
- Video Format: The format your scanned film frames get stored in. Off tape, your choices are DPX and QuickTime. Off the Cintel film scanner, you're limited to Cintel Raw Image (CRI), a raw data format that DaVinci Resolve debayers on its own into a Cineon log-encoded image for grading.
- Codec: The codec that writes the captured media. Off tape, the lineup spans the various Apple ProRes flavors, 8- and 10-bit YUV 422, 10-bit RGB, and the assorted DNxHD types. Cintel Raw Image files fall back to RGB.
- Save clips to: A field showing the directory path where media files captured off tape land. Aim for a volume quick enough to keep up with the data rate of whatever media format you're bringing in.
- Browse: Click here to pick a directory for the captured media to write into. Your chosen directory then shows in the field above.
- Save in this folder path: A row of checkboxes lets you spell out what extra information shapes the directory hierarchy holding the captured media. Each checkbox you enable tacks on another directory named after that checkbox's metadata. Pick any or all of: Program name, Clip number, Reel number, and Roll/Card.
- Apply reel number to: Lets you decide how the reel name gets written. A pair of checkboxes write the reel number into the file's name and/or into the Header data.
- Use prefix: A field where you type a prefix to fold into the media file's name, adding text identification that makes the media easier to spot and search for.
- Apply prefix to: Two checkboxes let you apply the prefix you typed to the file name and/or to the folder name.
- Use frame number with: When you're capturing to image sequences, this picks how many digits go into the frame number written into each frame file's name.
- Set batch ingest handles to: When capturing image sequences from a batch list, this sets how many frames of extra handles come in alongside every logged clip.
- Enable audio input: Tick this checkbox to bring in audio together with the video. For QuickTime or MXF files, the audio lands as extra tracks inside each file. For a DPX image sequence, a separate broadcast .wav file gets recorded.
- Input: Lets you pick how many audio tracks to capture, anywhere from 2 to 16.

### Playout Settings

These options touch nothing but the video signal sent out while you're in the Deliver page's Edit to Tape mode.

- Output: Lets you pick whether to send out both Video and Audio, Video Only, or Audio Only for an audio layback.
- Output Source Timecode: Tick this checkbox to send out each clip's own source timecode. It only comes into play when you're assemble editing to tape.
- Output LTC: On a Blackmagic Design DeckLink or UltraStudio device running HD-SDI, longitudinal timecode (LTC) rides on track 16 of the HD-SDI video signal, so a Mini Converter de-embedder can readily pull off this analog timecode audio signal and route it straight into a recording device. That's especially handy when outboard video processing gear such as a noise reducer or format converter fails to pass the VITC timecode through.
- Delay LTC by x frames: When you send LTC out to route around outboard processing gear like a noise reducer or format converter, you can offset for the processing lag by holding the timecode back a handful of frames so the processed image and the timecode hit the deck together. A DVS card provides its own separate timecode output.
- Enable audio output: Tick this checkbox and DaVinci Resolve plays every available timeline audio track alongside the outgoing video, letting both be laid to tape.
- Offset audio by x frames: Lets you dial in an offset between the audio track and the video to land proper A/V sync whenever outboard processing hardware is delaying the picture.
- Output x channels of audio: Pick how many audio tracks get sent out to tape.
- Set batch playout head handle to x seconds: When you batch-output several clips, you can

call for a certain number of frames ahead of each clip's In point to be sent out too.

- Set batch playout tail handle to x seconds: When you batch-output several clips, you can call for a certain number of frames after each clip's Out point to be sent out too.
- Apply gaps between clips: This checkbox drops a black gap of the stated frame duration between each pair of clips being sent out while you're outputting in batch mode.

### Edit to Tape Queue Option Menu Settings

The options below live in the Option menu over at the upper-right corner of the Edit to Tape Queue.

- Show Job Details: Reveals more about each job sitting in the Render Queue.
- Clear Recorded: Wipes out every queue item that's already gone to tape.
- Clear All: Wipes out every queue item.
- Sort by Reel & Timecode: Runs a two-key sort on reel and timecode, putting reel first

and timecode second.

- Sort by Timecode: Orders strictly by timecode.
- Output Source Timecode: Tells tape output to lay source timecode to tape (each clip's

own timecode) in place of record timecode (drawn from the Timeline).

- Use Preview for Tape Output: Switches on Preview mode for tape output. Preview

mode lets you rehearse how an edit-to-tape pass will behave before you commit it to recording.

### Tape Output Procedures

Several distinct paths exist for getting media onto tape, and which one fits depends both on your goal and on how heavy your grades are next to what your workstation can crunch.

### Power Mastering

Power Mastering lets you pick either a span of clips or a whole timeline and lay it to tape in real time, no rendering involved. That spares you a lengthy render and conserves disk space besides. Power Mastering gives up nothing, because your program still goes out at full quality. Should a few clips carry grades you already know are too processor-heavy to Power Master, the Render Cache controls can cache those troublesome clips before they go out. For a fuller treatment, turn to Chapter 8, “Improving Performance, Proxies, and the Render Cache.”

### Outputting a Program From the Timeline

The most straightforward way to go to tape is to send out a single Timeline, whether the whole thing or just a portion when you're insert editing a small revised stretch. To Power Master to tape: 1 If you must, lean on the Render Cache to cache any clips too processor-heavy to output live. 2 Click the Edit to Tape mode button left of the transport controls to flip into tape output.

3 Stake out how much of the current Timeline to send by running the playhead through the program, then right-clicking the clips that mark the range's beginning and end and invoking the Mark In and Mark Out commands. 4 With the transport controls, locate the In point on tape where recording should begin, and click the In button. 5 Pick Insert from the dropdown at the Viewer's upper right when you're either going to a striped and blacked tape or inserting over a program already on tape. 6 Click the Power Mastering (lightning bolt) button down at the bottom of the tape settings to drop the job you just built into the Edit to Tape Queue. 7 Click Start Record to set the output to tape in motion. Device control handles recording onto the chosen stretch of tape, while a progress bar at the foot of the Render Queue indicates how long it'll run.

Prefer not to Power Master? Then render the stretch of the Timeline you need to send as one clip up front, a self-contained media file, and feed that clip straight into the Edit to Tape Queue. That can be the smoother route when the timeline you're outputting is exceptionally processor-heavy.

To send a pre-rendered media file to tape: 1 Down at the foot of the tape settings, click the Add Clips button; in the VTR Record dialog, choose the media file you rendered back in step 1, then hit Add Clip(s) to Queue. The file you chose joins the Edit to Tape Queue as a Power Mastering job and goes out whole. 2 With the transport controls, locate the In point on the tape where recording should begin, and click the In button. 3 Pick Insert from the dropdown at the Viewer's upper right when you're either going to a striped and blacked tape or inserting over a program already on tape. 4 To rehearse the edit before it's actually committed to tape, turn on “Use Preview for Tape Output” via the Edit to Tape queue option-menu, then click Start Record and watch DaVinci Resolve walk through the edit on the deck. Once you've previewed it, switch that setting back off. 5 Click Start Record to set the output to tape in motion. Device control handles recording onto the chosen stretch of tape, while a progress bar at the foot of the Render Queue indicates how long it'll run.

### Batch Outputting Multiple Clips

There's also the choice of laying a set of clips to tape as a batch job rather than going out from the Timeline. Once you've lined up a batch of several clips in the Edit to Tape Queue, DaVinci Resolve records them onto tape one after another on its own. The way timecode gets generated during batch output rides on the “Output Source Timecode” option, found under the Project Settings' Capture and Playback panel. Leave it off and a single continuous timecode track is written across everything sent to tape. Switch it on and each clip's source timecode is written to tape with breaks between. While batch-outputting to tape, you can space the clips apart with black handles to ease later ingest, drawing on the “Set batch playout head/tail handle” options housed in that same Capture and Playback panel of the Project Settings.

To Batch Record several clips to tape: 1 With the transport controls, locate the In point on tape where recording should begin, and click the In button. 2 Take one of these routes to add items for output to the Edit to Tape Queue:

- Click the Add Clips button at the foot of the tape settings, select one or several media files in the VTR Record browser, then hit Add Clip(s) to Queue.
- Right-click any clip in the Timeline, pick Render This Clip, then click the Power Mastering button at the foot of the tape settings to drop that clip into the Queue.

3 Pick either Assemble or Crash from the dropdown at the Viewer's upper right. Since the clips you're sending carry discontinuous timecode, insert editing isn't available during batch output. 4 With every clip you mean to send now in the queue, click Start Record to start the output to tape. Device control handles recording onto the chosen stretch of tape, while a progress bar at the foot of the Render Queue indicates how long it'll run.
