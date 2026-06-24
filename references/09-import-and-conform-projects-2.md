# Creating Digital Dailies For Round Trip Workflows, Conforming Xml Files

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

## Overview

Covers: Creating Digital Dailies for Round Trip Workflows; Conforming XML Files.

## Creating Digital Dailies for Round Trip Workflows

### Creating Digital Dailies for Round Trip Workflows

Whenever a different application can’t open a particular project format that DaVinci Resolve handles, you can rely on DaVinci Resolve to produce media for editors working in that other application. While doing so, DaVinci Resolve’s wide range of organizational, effects, and grading features lets you turn out footage that’s genuinely pleasant to cut with: log-encoded clips get normalized, dual-source audio is synced through any of several techniques, and a quick (or more deliberate) pass of grading makes the edited footage look its best. As a bonus, building a project to handle these tasks also gives you a running start on reconforming later, should your pipeline involve sending the cut project back into DaVinci Resolve to edit and finish. The material below describes a workflow for bringing in, prepping, and outputting media for cases like these.

### Step 1–Ingest Media and Add/Edit Metadata

You don’t need a project file exported from an NLE before you can begin in DaVinci Resolve. The Media Storage browser on the Media page reaches any volume the system currently has mounted, letting you bring any supported media format into the Media Pool.

### Media Storage browser with scrubbable clip thumbnails

Serving as DaVinci Resolve’s built-in library of the media available to whatever project is open, the Media Pool can, if you prefer, hold its clips across several bins. After media lands in the Media Pool, the Metadata Editor opens up a range of descriptive fields you can fill in: descriptions, notes, scene and take details, flags, day and date entries, program and episode info, and more. Those entries can feed metadata tags when you export ALE lists to carry the metadata over to a compatible NLE. To dig deeper into ingesting media on the Media page, consult Chapter 18, “Adding and Organizing Media with the Media Pool.”

### The Media Pool

### Step 2–Sync Audio to the Dailies

When your video already carries embedded audio, DaVinci Resolve can just pass that audio along while it outputs media from the Deliver page. If instead the production used dual-system audio recording, the Media page offers several ways to sync it up. You may also bring timecoded Broadcast WAVE files into the same bin that holds the matching video clips (a sub-bin works too if you prefer), getting ready to sync the dailies in DaVinci Resolve. After the video and audio you want paired are sitting in the Media Pool of the Media page, right-click the surrounding folder and pick “Auto-Sync Audio Based on Timecode,” which lines up every timecode-matched audio-and-video clip pair inside that folder in one operation. Or you can pick “Auto-Sync Audio Based on Timecode and Append Tracks” to stack the synced tracks on top of whatever audio the video clips already include. TIP: You’ll get cleaner outcomes by keeping a separate folder per day for that day’s audio and video clips. When synced timecode isn’t available but your video clips do carry separately captured audio (commonly from an on-camera microphone) matching the dual-system recordings, waveform syncing is a fast way to pair each video clip with its corresponding audio. Drop your separately recorded audio files into the same bin as the matching video clips (again, a sub-bin is fine), readying them for syncing. After importing, right-click the surrounding folder and pick “Auto-Sync Audio Based on Waveform,” which lines up every timecode-matched audio-and-video clip pair inside that folder all at once. Or pick “Auto-Sync Audio Based on Waveform and Append Tracks” to stack the synced tracks onto whatever audio the video clips already hold. TIP: To make waveform syncing both faster and more accurate, split each day’s audio and video clips into their own folders — or even one folder per scene — so fewer waveforms have to be matched against each other in a single pass. And if your only sync reference is a plain clapboard, you can match video and audio by hand: open a video clip into the Media page viewer, click the Waveform button in the Audio panel, then click the matching audio clip so its waveform shows in the audio panel. From there, drag the Viewer and Audio panel’s playheads onto the respective video and audio sync points, and press the Audio panel’s link button to lock that clip’s A/V sync. To learn more about syncing audio with video on the Edit page, turn to Chapter 22, “Modifying Clips and Clip Attributes.”

### Step 3–Do Whatever Grading is Necessary

Productions that opt against camera raw often choose instead to capture a log-encoded or “flat” image to ProRes or DNxHD media files, holding onto as much image data as possible for grading without clipping the highlights or shadows. You might get there through in-camera settings that write log-encoded QuickTime or MXF media, or through external recorders like the Blackmagic Video Assist. Which log-encoded gamma curve ends up in the recording is determined by your camera. Common examples include Log-C and the S-Log, S-Log2, and S-Log3 family, along with BMD Film, CanonLog, Panasonic VLog, and REDlog Film, among still others.

Other pipelines record raw video formats and later debayer them into log-encoded clips, keeping as much debayered data as they can for grading or for an upcoming transcode. When the media files you’re putting out are high quality and destined to be finished from directly, you may prefer to leave the source image data untouched as it passes through. But when you’re generating offline media that editors, directors, and producers will be screening for the next three months, you have many grading options to deliver a nicer-looking, “normalized” result that comes closer to what was monitored on set during the shoot. DaVinci Resolve offers numerous routes to normalizing log-encoded media. With one or more raw formats in play, you can elect to debayer every clip directly to Rec. 709 from the Camera Raw panel of the Project Settings. Log-encoded ProRes or DNxHD media, on the other hand, calls for other normalization methods. One simple yet powerful choice is DaVinci Resolve Color Management: open the Color Management panel of the Project Settings and set the “Color science” setting to “DaVinci YRGB Color Managed.” After that, right-click each clip or selection of clips in the Media Pool and pick the matching option for that media type from the Input Color Space submenu (you can set the Input Color Space across multiple selected clips in one go). For a fuller treatment of working with DaVinci color management, refer to Chapter 9, “Data Levels, Color Management, and ACES.”

### Enabling DaVinci Resolve color management

Should you prefer to skip DaVinci color management, one or more LUTs (Lookup Tables) are another way to normalize log-encoded media. Applying a LUT across the whole project can normalize the specific log characteristics of whatever media you’re handling. You set project-wide LUTs from the Project Settings, on its Color Management panel. Further detail appears in Chapter 4, “System and User Preferences.”

Project-wide LUT table controls, found within the Project Settings on its Lookup Tables panel With LUT-managed shoots, where assorted LUTs were custom-built to monitor different scenes, you can hand-apply individual LUTs to one or more selected clips from each scene through the Media Pool’s contextual menu. Another route is to cut each scene’s clips into timelines and assign separate LUTs per clip in the Clip mode of the Node Editor on the Color page, or attach one LUT to a whole timeline via the Node Editor’s Timeline mode. To see how LUTs fit into grades, look at Chapter 143, “Node Editing Basics.” Alternatively, when on-set color correction arrived as a CDL-compliant EDL out of one of the several on-set grading systems on the market, the ColorTrace™ from CDL command can batch-import that grading data from the other application. For coverage of CDL import workflows, turn to Chapter 149, “Copying and Importing Grades Using ColorTrace.”

### Selecting Timeline in the Node Editor

When your pipeline demands even higher-quality dailies, nothing stops you from grading individual clips by hand the way you would on any project. But if a quick “one-light” correction across every clip in the Master Timeline is what you’re after, the Timeline grade mode of the Node Editor on the Color page lets you push a single adjustment onto every clip in the current Timeline at once. That’s especially handy because you can keep tweaking the Timeline grade as much as you want, and each change automatically carries through to every clip in the Timeline. Additional detail lives in Chapter 143, “Node Editing Basics.”

### Step 4–Export Media Suitable for Editing

With your clips organized, the dailies synced, and whatever grading the job called for applied, you head to the Deliver page to define the format, file naming scheme, and arrangement of the media bound for editing or finishing downstream. Deliver page with several jobs set up for rendering On top of that, when the media needs a window burn, watermark, or logo, you handle it from the Project panel of the Data Burn-In window, reached by choosing Workspace > Data Burn-In. Window burns offer a great deal of formatting flexibility and get baked into media that is either rendered or sent out to tape.

### For more information, see Chapter 12, “Data Burn-In.”

After you’ve dialed in the right render settings and window burn options, you can render out a single version or multiple versions of the media to cover jobs that require more than one deliverable. For a complete walkthrough of configuring and operating the Deliver page, see Chapter 186, “Using the Deliver Page.”

### Step 5–Reconform Media to an EDL, AAF, OTIO, or XML Project File

After the offline media you delivered has been cut in whatever NLE the project relies on, pulling the edited project back in is easy by way of an AAF, XML, OTIO, or EDL file, whichever best fits your application. That edit data lets you reconform the original media you brought into the Media Pool, so you instantly regain the graded adjustments you used to build the offline media, now applied to the source clips. Bringing AAF, XML, OTIO, or EDL files into the Edit page generates new timelines, and you can keep importing additional Timelines to keep up with changes to the edit if you happen to be grading a project that is still being cut. In fact, the way you structure your grades can let you use remote versions that automatically ripple to track each clip when you import a re-cut version of the program as a new timeline, sparing you from redoing your work. To learn more about remote versions, consult Chapter 142, “Grade Management.”

### Step 6–Output Final Media for Finishing

When your final grade is complete, you return to the Deliver page controls to render the program’s finished media, putting it out either as separate clips for a round-trip workflow or as one media file or image sequence to deliver as a digital master.

## Conforming XML Files

### Conforming XML Files

Among the simplest ways to move edits carrying as many video tracks as you need out of various NLEs and into DaVinci Resolve is XML. A bonus of XML import is that an assortment of supported effects can come across alongside the edit data, together with several tracks of video. The pages here describe the fairly easy procedure for importing XML projects into DaVinci Resolve. It might be a one-way trip, where you finish the project inside DaVinci Resolve, or part of a round-trip, where you head back to the originating NLE to finish. XML round-trip workflows are reasonably simple; if you need detail on exporting individual clips, look to Chapter 187, “Rendering Media.”

### More About Conforming XML Files

Projects exported in the Final Cut Pro 7 or Final Cut Pro X XML formats can be brought into DaVinci Resolve. Adobe’s Premiere Pro along with Autodesk Smoke and Flame Premium can likewise tap the Final Cut Pro XML project exchange format for round-trip workflows. For the cleanest results, though, make sure the XML you write comes out of Premiere Pro version 5.5.1 or a later build — and preferably from the most current Premiere Pro release you can run. Producing XML for DaVinci Resolve is simple, and beyond choosing which XML version to write, there really isn’t much to configure when exporting an XML file. Because of that, it’s wise to finish any timeline and/or media management you need before you export the XML.

### Manage Your Media Before Exporting an XML

When you’re bringing in XML or AAF projects (or even EDLs), relinking and conforming to the accompanying media files goes most smoothly if every file sits under one directory path. Spreading media across several directories is fine too, provided they all live within one parent directory you can point to at the right step of project import.

### Importing XML Project Files

Here we look at the Import AAF/EDL/XML dialog in far greater depth. A single procedure can carry out any of these workflows:

- Bringing in an XML file while automatically conforming to, and importing, the media it references.
- Importing an XML file while hand-picking a separate set of media instead, presumably in a different

format or resolution, with identical metadata, to conform to instead.

- Importing an XML file linked to offline media derived from a camera original format, and

automatically conforming it to and importing the camera original media. You reach each of these workflows by selecting the right mix of options, all of them explained in the procedure that follows. Using the Timeline Import dialog, you can pick several XML, AAF, FCP XML, or EDL timelines together (in any combination). Those chosen timelines import one after another, pausing each time you press the OK button so you can set separate Import Settings per timeline. To bring in an XML file and have it link up to its referenced media on its own: 1 Take one of these actions:

- On any page, choose File > Import Timeline (Shift-Command-I).
- Go to the Edit page, right-click anywhere within the Media Pool, and pick Timelines >

Import > AAF/EDL/XML/DRT/ADL/OTIO. 2 In the file dialog that opens, locate the project file you want and click it to open. Depending on what you chose, the Load XML window appears.

Options when importing an XML file 3 Set the options that suit your particular project. These default to values drawn from metadata inside the file you picked.

- Source file: Whatever file you chose during the prior step.
- Import timeline: When the selected XML source file holds more than one sequence, this pop-up

menu is where you pick which of those sequences becomes the imported DaVinci Resolve timeline.

- Timeline name: The label for the Timeline you’re creating. It starts out matching the name of the exported sequence, though you’re free to rename it.
- Master timeline start timecode: The timecode where the imported timeline begins. This is set automatically to the start timecode of the selected Import Timeline.
- Automatically set project settings: Keep this on so the frame size and frame rate in the Project tab of the Config page are updated automatically from the values shown in this window. Timelines whose frame rates differ from the Project frame rate can still be imported.
- Automatically import source clips into media pool: Keep this checkbox on so the media that the chosen XML project file points to is brought into the Media Pool automatically using the embedded file paths. Should the media not turn up at those locations on its own, you’ll be asked to pick a directory that holds the clips by hand.

Ignore file extensions when matching: Switch this checkbox on when you’d rather hand-pick a different media directory to link against — say the incoming XML references ProRes Proxy media yet you’d like to point instead at a separate directory holding the equivalent ProRes 4444 or camera raw media.

- Use sizing information: Brings in position, scale, and rotation transforms from the source NLE by way of the imported XML project file. Those transforms live in each clip’s settings within the Edit page Inspector.
- Use color information: Applies to Final Cut Pro X XML files only. With it, you can pull in a portion of the color correction data from the Final Cut Pro X color board controls.
- Import multi-channel audio tracks as linked groups: Enable this checkbox when you want multi-channel audio — stereo, 5.1, and 7.1, for example — brought in as separate mono timeline tracks that are linked together on the Fairlight page.

To read more on Linked Groups, head to Chapter 171, “Setting Up Tracks, Busses, and Patching.” Leaving this checkbox off causes multi-channel audio to come in as multi-channel audio tracks in the Timeline instead.

- Set timeline resolution to: A pair of fields where you enter the width and height of the frame size you intend to work at inside DaVinci Resolve. It defaults to whatever resolution the imported XML file specifies.
- Timeline frame rate: By default this comes from the frame rate of the XML file you’re importing. When you import an XML file into a project whose Media Pool already holds media, the Timeline frame rate is locked and can’t be altered.
- Use drop frame timecode: By default this comes from the XML file being imported.
- EDL frame rate: By default this comes from the frame rate of the chosen file.
- Use drop frame timecode: By default this comes from the frame rate of the chosen file.
- Mixed frame rate format: From this pop-up menu you select the method used to conform

mixed frame rates during rendering and playback. The “Final Cut Pro 7” or “Final Cut Pro X” conform methods are available, but for projects coming from Media Composer, Premiere Pro, Smoke, or other NLEs, keep it set to “DaVinci Resolve.” The same pop-up menu also shows up in the Load XML dialogs as you import a project. 4 Once all the needed settings are in place, click OK. 5 Provided you kept “Automatically import source clips into media pool,” turned on, then if the media the XML file references isn’t at the expected disk location, or if you ticked the “Ignore file extensions when matching” checkbox, a further dialog opens asking you to point to the folder where this project’s media lives. Do one of the following:

- If you’d like to attempt relinking to media at a different disk location: Click Yes, then browse to the folder that holds your media (every subfolder gets scanned too), select it, and click OK.
- If you’d simply like to bring the Timeline in with every clip offline: Click No.

A prompt appears if all the media was not found

IMPORTANT: You can always point to the top level of any volume so all media in any directories beneath it is found automatically, but on a large volume packed with files, combing through every folder and document on it can take an extremely long time. 6 If you clicked Yes to pick another folder, use the folder selection dialog to browse to a different folder and click Ok. Repeat this cycle as many times as necessary until every piece of media the timeline links to has been located.

Selecting the source folder for your XML imported clips With that done, the XML file comes in. A fresh timeline together with the referenced media files shows up in the Media Pool, and the Timeline opens so you can view its contents. Any clips that couldn’t be matched to a file on disk show up red in both the Media Pool and Timeline, marking them as offline and unlinked. TIP: Opening the Edit Index and picking Filter Offline Clips from its option menu surfaces a roster of every offline clip in the Timeline you’re working on.
