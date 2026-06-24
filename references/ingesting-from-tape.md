# Ingesting From Tape

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Ingesting From Tape

Through a compatible video input device, like a Blackmagic Design UltraStudio or a DeckLink card, DaVinci Resolve can pull media in off tape. Device control is among the supported features.

### Tape Ingest

Here we walk through bringing media off tape straight into the Media Pool inside DaVinci Resolve. Whether you've got just a few clips to grab for an existing project or you have to recapture every clip tied to the events of an EDL, the Media page in Capture mode lets you pull from any device-controllable deck over a compatible video interface. To move into tape capture on the Media page: Click the Capture button, which sits to the left of the Interface toolbar along the top of the Media page. The Media page then shifts to show the controls relevant to editing to tape, and a purpose-built set of capture metadata and controls takes the place of the Audio panel to help you keep tabs on the clips you produce.

### The Tape Capture Interface

Once you're in Capture mode, the Media page drives the VTR so you can set In and Out points for logging or grabbing a chosen stretch of the tape.

### Tape Capture viewer in the Media page

- Transport controls: Though the transport controls look much like the ones you'd use just to play through selected clips on the Media page, here they instead drive the VTR.
- Shuttle control: Where the scrubber bar once sat, a shuttle control now appears, letting you shuttle across the span of reverse and forward speeds the connected deck supports.
- In and Out controls: Under Capture mode, the In and Out buttons sitting to the right of the transport controls mark out a stretch of the tape to capture.
- Capture panel: The panel flips over to the Capture panel on its own, bringing tape-specific metadata and capture controls. Filling in File Name Prefix refreshes the file name preview displayed up in the Header, which also reports the Capture directory, Resolution, and Frame Rate set in the Capture and Playback panel of the Project Settings.

### Editable capture metadata

### Setting Up to Capture From Tape

Ahead of any tape capture, you'll have to set a range of options within the Capture and Playback panel of the Project Settings. There are two clusters of settings, especially, that must be filled in.

### Deck Settings

These options bear on both capture and playback whenever you turn to the Tape Ingest options on the Media page or the Tape Output options on the Deliver page.

- Video capture and playback: From this drop-down menu you pick the video format (frame size and frame rate) to output to tape with. Your DeckLink card's format conversion can downconvert HD timelines to SD and upconvert SD timelines to HD.
- Use left and right eye SDI: A checkbox letting the Blackmagic Design DeckLink HD Extreme 3D+ take in and send out muxed stereoscopic video alongside supported VTRs, like HDCAM SR decks running 4:2:2 x 2 mode. (As muxed stereoscopic signals come in, each eye is split off into its own left-eye and right-eye image files.)
- Video connection operates as: Chooses among the offered signal options: Use 4:4:4 SDI and Enable Single Link. Exactly which options show up rides on the video capture card you've got.
- Data Levels: Lets you state the data range (typically scaled or full range) applied while ingesting from or outputting to tape. The option flips the data range of the signal your video capture card puts out, but solely during capture from tape on the Media page or output to tape on the Deliver page. While no capture or output is underway, your video capture card reverts to the data range setting of the same name over in the Master Settings panel of the Project Settings pane, which dictates how you monitor the signal sent out to an external broadcast display or projector.
- Video bit depth: 10-bit stands as the sole option.
- Use deck autoedit: Where your video deck supports it, this is the best route for laying video

down to the deck, since it lets the deck roll the edit off the specified preroll and steer the edits over serial device control. With this checkbox off, the deck falls back on a plain edit On/Off mode, which risks frame inaccuracies should the “Non auto edit timing” setting be set up wrong.

- Non auto edit timing: Fine-tunes the edit synchronization of the connected deck whenever auto edit is switched off.
- Deck preroll: Sets how many seconds of preroll to use. The right amount hinges on how your deck performs.
- Video output sync source: With a DeckLink card this sits at Auto. Other capture cards may ask you to point the sync source at “Reference” for playout and “Input” for ingest. You'll only see this setting if the DVS card is installed on your system.
- Add 3:2 pulldown: Adds or strips out the 3:2 pulldown that lets 23.98 fps media be laid onto, or played back off, a 29.97 tape format.

### Capture

You'll lean on these options when you turn to Capture mode on the Media page to bring tape clips into the Media Pool, or when you're driving the Cintel Film Scanner to scan film across various formats.

- Capture: Lets you decide between capturing both Video and Audio together, or Video on its own.
- Video Format: The format your captured media gets saved as. When you're capturing from tape, the

choices on offer are DPX and QuickTime.

- Codec: The codec that writes your captured media. For tape capture, the lineup takes in Apple ProRes in its assorted flavors, YUV 422 at 8- and 10-bit, 10-bit RGB, plus the DNxHD family in its various forms.
- Save clips to: A field showing the directory path where media files grabbed from tape land. Aim for a volume quick enough to keep up with the data rate of the media format you're capturing.

Browse: Hit this button to pick a directory for writing captured media into. Whatever directory you settle on turns up in the field above.

- Save in this folder path: A run of checkboxes lets you dictate what extra information shapes the directory hierarchy holding the captured media. Each checkbox you tick adds one more directory whose name comes from that checkbox's metadata. Pick any or all of these: Program name, Clip number, Reel number, Roll/Card.
- Apply reel number to: Lets you decide how the reel name gets written. A pair of checkboxes let you stamp the reel name into the file's name and/or into the Header data.
- Use prefix: A field where you can enter a prefix to attach to the media file's name. This lets you fold in text identification so the media is easier to spot and search for.
- Apply prefix to: Two checkboxes let you opt to apply the prefix you entered to the file name and/or to the folder name.
- Use frame number with: For captures going to image sequences, you choose how many digits go into the frame number written into each frame file's name.
- Set batch ingest handles to: Lets you tack extra frames of handles onto the start and finish of every scanned clip during batch capture with the scanner.
- Input: A drop-down for picking how many audio tracks to capture, anywhere from 2 to 16.

### The Three Methods of Capture

After you've dialed in every relevant option in the Project Settings window, at the very least the settings labeled “Video Capture and Playback,” “Capture Clips Saved to,” along with Apply Reel Name to,” you're set to begin capturing. Which of the three tape-capture methods you reach for comes down to your workflow. Across all of them, media can be brought in as QuickTime Movies or DPX image sequences.

### Using Capture Now

When all you need is to grab a stretch of tape in a hurry, the Capture Now command does the job. To Capture Now: 1 Lean on the transport controls and the In button to pin down what you'd like to capture. 2 Fill in all the pertinent details across the various fields of the Metadata Editor. The Header refreshes to preview the file name that's going to be saved. 3 Use the transport controls to roll playback, then click the Capture Now button down at the foot of the Metadata Editor. 4 Once the stretch of tape you meant to record has run out, click Capture Now once more to halt capture. A fresh clip turns up in the Media Pool, dropped on its own into a new folder in the Media Pool under a name built from the timecode value turned into a frame count according to the ingest frame rate. To illustrate, a clip grabbed at timecode 01:00:00:00 winds up with the file name 00086400.dpx.

### Logging and Capturing Individual Clips

When you're after a precise range of tape, or several sections in one pass, another route is to log each section of tape you want ahead of time, then call on the Capture Clip or Batch Clips commands as a follow-up step. To grab a single clip through device control: 1 With the transport controls, locate the start of the tape section you intend to record and click the In button. Next, locate its end and press the Out button. 2 Key all the pertinent details into the various fields of the Metadata Editor. The Header refreshes with a preview of the file name about to be saved. 3 Once you're done, click Capture Clip. Deck control kicks in automatically to run through the stated range of tape and grab that clip. As soon as capture wraps, the new clip shows up in the Media Pool.

### Logging and Capturing Multiple Clips

To save time, you might instead log a batch of clips in one go, drawn from several tapes where needed, and then batch capture the whole lot together. To log one or more clips: 1 Using the transport controls, track down the start of the tape section you mean to record and click the In button. After that, track down its end and press the Out button. 2 Type all the pertinent details into the various fields of the Metadata Editor. The Header refreshes to preview the file name that will be written. 3 When that's done, click Log Clip. The clip joins the Media Pool as an offline tape clip, flagged by a black icon bearing a tape badge.

A logged clip sitting in the Media Pool ahead of capture To batch capture one or more logged clips: 1 (Optional) Flip the Media Pool over to List view, then use the Reel No column header to order the clips there by reel number. Doing so makes it simpler to pick out a run of clips to grab off one reel. 2 Choose one or more offline tape clips in the Media Pool that originate from a single reel. 3 Click Batch Clips, found at the foot of the Metadata Editor. Should you want to break off capture at any point, click Batch Clips again. Deck control takes over automatically to run through the tape currently in the VTR and grab every logged clip you've chosen that turns up on it, beginning with the one carrying the lowest timecode value and finishing with the one holding the highest timecode value. A progress bar, paired with text, reports how much remains before capture wraps. With each clip captured, its matching logged clip in the Media Pool gains a thumbnail mirroring the captured media. Once DaVinci Resolve has captured all the clips off a given reel, Batch Capture comes to a halt.

### Batch Capture Via EDL

An EDL can likewise serve to build offline tape clips, one per event in the EDL, which you then batch capture to pull in all the media a project needs to conform from tape. To bring an EDL in as a batch capture list: 1 Open the Project Settings, then in the sidebar click Master Panel and verify each of these:

- Set “Timeline frame rate” to the frame rate of your EDL.
- Turn on “Use drop frame timecode” if your EDL requires it.
- Make sure “Use Timecode” is set to “Embedded in the source clip.”
- Turn on “Assist using reel names from the.”

2 Choose File > Import Batch List From EDL. 3 Should a Conform Settings dialog pop up asking you to sign off on the current Project Settings, click OK if everything checks out. 4 Through the controls of the Select EDL files dialog, pick one or more EDLs, then click Open. Picking several EDLs pulls in every event from each EDL together. 5 In the dialog that follows, settle on a frame rate to conform the EDL at, then click OK. Every event in the EDL now shows up as offline tape clips in the Media Pool, set for capturing. If you load an EDL while the Media Pool already holds clips sharing a reel name and start timecode with events in the EDL, DaVinci Resolve skips making new offline tape clips for those.

A batch of logged clips brought in from an EDL 6 (Optional) Switch the Media Pool to List view, then click the Reel No column header to order the Media Pool clips by reel number. That eases picking a run of clips to grab off one reel. 7 (Optional) Any offline clips you don't intend to capture can be cleared out: right-click them within the Media Pool and choose Remove Selected Clips.

8 Mark which of the offline tape clips you'd like captured. Ideally, choose stretches of clips drawn from one and the same reel. 9 Click the Capture mode button sitting to the left of the transport controls, after which clicking Batch Clips kicks off capture. To stop capture partway through at any moment, click Batch Clips a second time. On its own, Deck control plays through whatever tape is loaded in the VTR and grabs each logged clip you've marked that it locates there, opening with the clip whose timecode value is lowest and closing with the clip whose timecode value is highest. Alongside text, a progress bar indicates how far there is left to go until capture finishes. As every clip comes in, the logged clip it answers to in the Media Pool picks up a thumbnail echoing the captured media. The instant DaVinci Resolve wraps up every clip from a given reel, Batch Capture stops.
