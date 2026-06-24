# Media Management

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Media Management

Within DaVinci Resolve, Media Management covers operations that let you copy or transcode the media tied to clips in your timeline, optionally dropping unused media along the way. You reach for Media Management when consolidating media from a cut timeline or from a project drawing close to the finish line.

### What Is Media Management in DaVinci Resolve?

Once you've cut a program inside DaVinci Resolve, the Media Management command can handle a range of jobs, among them:

- Building a copy of your project's clips that drops unused media to prep the media for handoff to a different facility.
- Transcoding every clip in a timeline into another format while trimming away unused heads and tails.

Say, for instance, you're getting ready to export a project to pass along to a different DaVinci Resolve user elsewhere, or even an XML or AAF bound for someone on an entirely different NLE or finishing tool—you can lean on Media Management in DaVinci Resolve to consolidate and relink the media the handoff timeline uses, so the exported project or timeline points at a smaller pool of media. And even with no handoff in sight, if you've pulled a massive amount of source media into a project and, with most of the editing behind you, decide to make a trimmed-down set of the media you're actually using to ease the project's weight in the Media Pool, you can build a duplicate of the media to reconform against, dropping unused clips and clipping the unused heads and tails off the ones you keep as you go. But Media Management earns its keep beyond projects you've cut in DaVinci Resolve. For example, if you're bringing in a project from another tool and were handed a mountain of source media to conform against, you might balk at copying every bit of it to your accelerated storage volume, given that (a) the bulk of it is probably never touched by the project file you received, (b) copying it off the cheap USB 2 hard drive they handed over will drag on forever, and (c) it'll choke your local storage, robbing space from other projects. Here, Media Management can copy a slimmed-down set of media files holding only the clips the Edit page's current timeline actually uses.

### Media Management of Timelines Creates .drt Files

While running Media Management operations to copy or transcode media off a timeline, a DaVinci Resolve Timeline (.drt) file is generated automatically in the same bin as the media files produced, linked to the freshly created media. That timeline is then yours to import into the same DaVinci Resolve project or a new one.

### File Formats That Are Compatible With Media Management

Whatever you put it toward, Media Management is built to handle every video format with decode support inside DaVinci Resolve, and it can output a handful more formats than the Deliver page manages.

Compatible formats include but are not limited to:

- QuickTime
- MXF
- R3D
- Image-based raw media formats including Blackmagic RAW and Alexa raw
- DPX, EXR, JPEG 2000, TIFF, Cineon, and other compatible image sequence formats
- AVI
- H.264
- XAVC
- AVC-Intra

On top of that, the "trim unused media" choices under the Copy or Move operations now work with clips whose codecs employ temporal compression—H.264, XAVC, and AVC-Intra, mp3, Flac, and QuickTime—so you can drop unused media for these formats during media management without recompressing or transcoding.

### Using Media Management

Working with Media Management is straightforward. To media manage clips and timelines inside a project you've built: 1 Pick the items you want to media manage, whether clips or one or more Timelines. 2 Choose File > Media Management, and up comes the Media Management window.

Media Management window

3 Set the scope of the Media Management operation, shown along the top of the window. You can opt to act on the Entire Project, only one or more Timelines, or only Clips. Whatever you'd selected before opening the Media Management window shapes which scope is chosen as it opens, but it doesn't pin the operation to only those selected items. So with nothing selected in the Media Pool, "Entire Project" lights up on its own. With any clips selected, "Clips" lights up automatically. With any Timelines selected, "Timelines" lights up. Yet if for any reason the wrong option is highlighted, all you do is click the one you actually want to choose it instead.

Media Management scope options 4 Then, settle on which operation to run: Copy: Builds duplicates of all media tied to clips or timelines at the destination. Transcode: Builds duplicates of all media tied to clips or timelines in a new format you name; every transcoded clip lands at the same destination.

Media Management operations 5 Click the Browse button and lean on the File Destination dialog to pick where the managed media gets written. That location's file path shows up in the Media Destination field. 6 Set the options that go with the operation you picked. If you media manage Timelines, a Timeline Selection option lets you pick which Timelines to fold into this operation. Listed below is the current size of the selected media, beside an estimate of the media's size once the operation you chose runs. Depending on your option choices, that estimate may grow or shrink, but it'll signal whether you need to change the chosen options to land on a more agreeable final size. 7 With option choices made, click Start. A progress bar turns up to report how long the operation will run.

Here the Media Management options are displayed while trimmed media is copied out of one particular timeline. The walkthrough that follows shows how Media Management can shrink the volume of media you have to wrangle when conforming a project imported from elsewhere, where you've been handed far more media than you truly need, since all you require is what actually sits in the timeline you're importing. To use Media Management to build a consolidated copy of media for a project you're conforming: 1 Hook the portable drive carrying the media to be conformed up to your workstation. 2 Bring the AAF or XML project file you were handed into the Edit page, and conform it to the footage sitting on the portable drive that step 1 had you connect. The sole point of this is to identify which clips call for media managing, not because you'll work off that volume. 3 Choose File > Media Management. The Media Management window turns up. 4 Pick Timelines along the top of the window, then open the Timeline selection section and switch on the checkbox for the timeline whose media you want consolidated. 5 Click the Browse button and pick the volume you want the consolidated media written to. 6 Set the following options for consolidating the media. For this operation, switch on:

- Hit the Browse button and point it at the accelerated storage volume that holds every bit of media you work with in DaVinci Resolve.
- Set the “Timelines” Media Management scope, unless it's already chosen, so all media from the timeline you picked gets managed.
- Pick “Copy” so the media gets duplicated off the portable storage volume onto your accelerated storage.
- Pick “Copy and trim used media keeping 12 frame handles” provided 12 frame handles suit you.
- Switch on “Consolidate multiple edit segments into one media file” if larger media files don't bother you and you'd like to keep the tie between which clips trace back to which single media files. Grading can go more smoothly down the road this way.
- Switch on “Relink to new files” so the timeline you chose automatically relinks to the freshly generated media.

The Consolidate dialog lets you set how and where the trimmed media gets copied. 7 With these settings chosen, click Start. A progress bar turns up to report how long the operation will run. A portion of the media that timeline uses gets copied into the directory you named, and a DaVinci Resolve Timeline (.drt) is generated automatically that relinks to the timeline and clips in the Media Pool. The project is now ready for you to keep working on.

### Continuing Media Management Jobs on Error

DaVinci Resolve handles errors during media management operations in a friendlier way. In earlier releases, DaVinci Resolve would halt and wait for your input the moment it hit an error, which meant that if an error cropped up while you were out at lunch, nothing moved until you got back. These days, DaVinci Resolve will pass over error-flagged files and press on with whatever media management remains for all the other clips.

### Options in the Media Management Window

Each Media Management operation puts different options on the table.

- Entire Project Copy/Transcode all media: (Not available for Timelines) Picking this option copies the complete source media for every last clip in the project. Should you add more media down the line and then run the Copy function again, DaVinci Resolve copies only the extra files needed to mirror the current Media Pool.
- Destination: Click the Browse button to pick a destination for the managed media to be copied to. Need a fresh directory? Right-click a Volume icon over in the File Browser list, pick New Folder, key a name into the resulting dialog, and click OK.
- Timeline selections: With the Timelines mode of media management chosen, you can open the Timeline Selection controls and switch on the checkbox beside each timeline holding media you want included.
- Copy/Transcode All media: Copies all media available to that operation.
- Copy/Transcode Used media: Restricts copying to the media files behind clips a timeline actually uses, and

brings them across whole.

- Copy/Transcode Used media and trim keeping x frame handles: Restricts copying to the media files a timeline uses, yet strips away unused heads and tails save for the handles you specify.
- Use project name subfolder: Automatically builds a subfolder named after the project beneath the destination directory holding all the copied or transcoded media.
- Consolidate multiple edit segments into one media file: This option only opens up if you've picked "Copy and trim used media" When several clips in a timeline trace back to the same media file, a single consolidated media file gets built holding every frame from all those clips, plus whatever extra frames sit between them. Even though this option ends up copying or moving more media, it's tremendously handy when you're consolidating media you intend to grade with the automatic grade linking of remote versions, since it preserves the original tie between each Timeline clip and the source media file it came from.
- Preserve folder hierarchy after x folder levels: Keeps a depth you specify of the original directory structure a clip's source media file uses, rebuilding it as new files are rendered for output. The number you pick sets how many subdirectory levels DaVinci Resolve will automatically build inside the currently named "Render job to" directory to mirror the path the source files use. Defaults to 0, which builds no matching subdirectories. The count of path levels is measured starting from the head of each media file path.
- Relink to new files: (Appears for the Copy operation only) Relinks the chosen clips and/or timelines to the new media you've produced by copying, wherever you copied it.

### Options for Transcode Only

The options below show up only when Transcode is the Media Management operation in play. Settings: Surfaces the default controls for the Media Management operation. Video: Surfaces the video codec controls for rendering to every available video format. Audio: Surfaces the audio codec controls for rendering to every available audio format.

### File Naming When You Consolidate Media

When you're media managing clip-based formats such as QuickTime or MXF, and the "Trim Used Media" option is on while the "Consolidate Multiple Edit Segments Into One Media File" checkbox is off, timelines drawing on several clips from the same media file will spawn several trimmed media files. So these files don't overwrite each other, extra characters get tacked onto each trimmed media file sharing a source; which characters are used hinges on the video format. For DPX files: \_0, \_1 For R3D files: \_S000.RDC, \_S001.RDC For QuickTime files: \_S000.mov, \_S001.mov
