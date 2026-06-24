# Conforming Aaf Files (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Conforming AAF Files

A project exchange format, AAF (Advanced Authoring Format) was first created by the Advanced Media Workflow Association (AMWA). Widely used video applications capable of writing out project data in the AAF format take in Avid Media Composer, Avid Symphony, Autodesk Smoke plus Flame Premium, along with Adobe Premiere Pro. Detailed guidance on the suggested workflows for carrying projects out of Media Composer (or Symphony) into DaVinci Resolve for grading fills this chapter, whether as a one-way trip or as a round-trip workflow where you head back to Avid Media Composer to finish. Because round-trip workflows in Media Composer involve so many variables, the chapter treats the topic thoroughly. Toward the end, the chapter also explains bringing in audio projects out of Pro Tools that were exported to AAF.

### Supported Media Types in AAF Workflows

Several ways of ingesting and handling compatible media formats are offered by Media Composer. In the end, which formats will serve for a one-way or round trip from Media Composer to DaVinci Resolve hinges on whether they work with DaVinci Resolve. Keep one further point in mind while you handle media inside Media Composer: not every format works with every media management operation. Because format compatibility and operational compatibility combine this way, you have to shape your workflow carefully around the particular media files you intend to use.

### Transcoding to DNxHD or DNxHR Always Works

Because DNxHD and DNxHR were built to serve as the core codecs of Media Composer, any workflow in which you transcode other media formats into MXF-wrapped DNxHD/DNxHR ahead of editing is guaranteed to function, and these are the most straightforward when round tripping across Media Composer and DaVinci Resolve. Both MXF-wrapped and QuickTime-wrapped DNxHD/DNxHR media are supported by DaVinci Resolve.

### Linking to Media Using AMA and Consolidating

A way to link clips straight to media files within Media Composer, without having to either transcode them into DNxHD/DNxHR MXF files or copy them across to an Avid MediaFiles directory, is Avid Media Access (AMA). Handy as it is, any workflow that involves media linked through AMA calls for somewhat more planning. Media Composer cannot consolidate every AMA-compatible media format, which caps your ability to assemble a smaller, more portable batch of media for moving into DaVinci Resolve. Whether a given AMA-linked clip is consolidatable comes down to its media format; the only formats Media Composer can consolidate are ones it is able to write. As an example, because Media Composer is unable to write R3D media, R3D media cannot be consolidated. On top of that, not every AMA-compatible media format works with DaVinci Resolve. The mere fact that you can edit a media format on a Media Composer timeline is no assurance that it is usable in DaVinci Resolve. Which media formats are AMA-linkable in Media Composer, which ones can be consolidated, and which ones work for use in DaVinci Resolve are all set out in the table that follows. When you are prepping a sequence drawing on an assortment of media formats, where some can be consolidated and some cannot, transcode every clip that won't consolidate into an Avid native codec before you start consolidating media and writing out an AAF for DaVinci Resolve.

### Fast Imported Media

A further complication is that Media Composer offers a media ingest approach termed “Fast Import,” in which imported media gets copied swiftly to the Avid MediaFiles directory by dropping the original image data, using its original codec, inside an MXF wrapper. Although this is a remarkably quick and efficient route for pulling media into Media Composer projects, the files it leaves behind usually won't work with DaVinci Resolve. That said, remember that whatever media format can be Fast Imported is also consolidatable. Should you intend to round trip a sequence built on Fast Imported media, the advice is to either transcode the Fast Imported clips into DNxHD ahead of AAF export, or instead conform your exported AAF project against the camera original media inside DaVinci Resolve. TIP: Any time your project mixes in media formats that don't work with DaVinci Resolve, the “Transcode Video To” checkbox, located among the options of the Export As dialog, is available while you export an AAF project. With that option you can transcode every piece of media that isn't a compatible format into one that is. A few nonstandard frame sizes won't transcode within Avid and instead come back with an unsupported resolution error.

### Codec

Compatible AMA-linked formats, with each codec rated for the three columns below:

| Codec                  | Can be Natively AMA-Linked | Can be Consolidated | DaVinci Resolve Compatible |
| ---------------------- | -------------------------- | ------------------- | -------------------------- |
| ARRI ALEXA Raw         | Non-native support         | No                  | Yes                        |
| AVCHD                  | Yes                        | No                  | Yes                        |
| AVC-Intra and Long GOP | Yes                        | Yes                 | Yes                        |
| Blackmagic RAW         | Non-native support         | No                  | Yes                        |
| Canon XF               | Yes                        | Yes                 | Yes                        |
| Cine (Phantom)         | Yes                        | Yes                 | Yes                        |
| CinemaDNG              | No                         | No                  | Yes                        |
| DVC PRO P2             | Yes                        | Yes                 | No                         |
| QuickTime (ProRes)     | Yes                        | Yes                 | Yes                        |
| R3D (RED)              | Non-native support         | No                  | Yes                        |
| Sony F65 Raw           | Yes                        | No                  | Yes                        |
| Sony HDCAM SR (SStP)   | Non-native support         | No                  | Yes                        |
| Sony XAVC              | Yes                        | Yes                 | Yes                        |
| Sony XDCAM             | Yes                        | Yes                 | Yes                        |

### Logged Errors When Importing AAF

When the “Import log messages as markers” checkbox is switched on within the Load AAF dialog, particular error messages that warn you about problems with the AAF import you're attempting get attached as markers, complete with notes, on the Timeline. Through a pop-up tucked inside the text of that checkbox, you can pick the color of the markers that hold this information. Markers will be produced by the following messages:

- The ‘XXXX’ transition type isn't handled by this release, so a Cross Dissolve gets dropped in instead.
- This release doesn't handle the ‘XXXX’ effect type, so plain clips come in instead.
- This release doesn't handle the ‘XXXX’ SMPTE Wipe Transition type, so a Cross Dissolve gets

dropped in.

- The ‘XXXX’ interpolation type isn't handled by this release, so Linear interpolation gets used.
- Linking the ‘XXXX’ clip failed, since its timecode extents line up with no clip inside

the Media Pool.

- A mismatch sits between the stated target timecodes ‘XXXX’ and the located file timecodes ‘YYYY.’
- The stated target timecodes ‘XXXX’ and the located file timecodes ‘YYYY’ share no overlap.
- The ‘XXXX’ clip on track ‘XXX’, timecode ‘UNKNOWN’, carrying reel name ‘XXXX’ plus filename ‘XXXX.’
- The ‘XXXX’ clip on track ‘XXX’, timecode ‘UNKNOWN’, carrying reel name ‘XXXX’ plus filename ‘XXXX.’
- No file turned up across the search directories.

At the moment this is being written, the feature is offered solely while you import AAF files.

### Simple AAF Import

A far more detailed look at the Import AAF, EDL, XML dialog occupies this section. A single procedure lets you carry out any of the workflows below:

- Bringing in an AAF file and having it automatically conform to and import the media it links to.
- Bringing in an AAF file and hand-picking a different batch of media, presumably at a different

format or resolution, carrying matching metadata, to conform against instead.

- Bringing in an AAF file linked to offline media that was derived from a camera original format,

and having it automatically conform to and import the camera original media. Through the Timeline Import dialog you can pick several XML, AAF, FCP XML, or EDL timelines (or any mixture of them) all at once. The chosen timelines import one after another, pausing each time once the OK button has been pressed, which lets you set separate Import Settings per timeline. Every one of these workflows becomes possible once you select the right blend of options, all of which the procedure below spells out. To bring in an AAF file and link automatically to its referenced media: 1 Do one of the following:

- From any page, choose File > Import Timeline (Shift-Command-I).
- Head to the Edit page, right-click somewhere within the Media Pool, then pick Timelines >

Import > AAF/EDL/XML/DRT/ADL/OTIO.

2 With the file dialog that comes up, locate the project file you wish to bring in, and click it to open. Depending on what you picked, the Load AAF window comes up.

Options when importing an AAF file 3 Pick whichever options suit your particular project. Out of the box, these options derive from metadata held within the file you selected.

- Source file: The file you selected in the previous step.
- Import timeline: Should the chosen AAF source file hold several sequences, this pop-up

menu lets you decide which sequence comes in as a DaVinci Resolve timeline.

- Timeline name: The name carried by the Timeline you're on the verge of creating. This defaults to the name of

the sequence that was exported, though you may rename it if you wish.

- Master timeline start timecode: The timecode where the imported timeline gets going. This

falls automatically in line with the start timecode of the chosen Import Timeline.

- Automatically set project settings: Keep this option enabled to have the frame size

and frame rate settings in the Project tab of the Config page automatically updated to match the ones in this window. Timelines whose frame rates differ from the Project frame rate can still be imported.

- Automatically import source clips into media pool: Keep this checkbox enabled so the media referenced by the AAF project file you chose is automatically brought into the Media Pool according to the embedded file paths. Should the media files not turn up automatically at those spots, you'll be asked to pick a directory by hand where the clips reside.

Ignore file extensions when matching: Switch this checkbox on whenever you wish to hand-pick a separate directory of media to link against; for instance, when the AAF you're bringing in links to ProRes Proxy media and you wish to relink to a separate directory of matching ProRes 4444 or camera raw media.

- Use sizing information: Lets you bring in position, scale, and rotation transforms out of the originating NLE by way of the imported AAF project file. Each clip's settings in the Edit page Inspector hold these transforms.
- Import log messages as COLOR markers: Switch this checkbox on and pick a color out of the attached drop-down menu for markers that will land on the Timeline carrying note text that describes import errors you may want to look into later.
- Import multi-channel audio tracks as linked groups: Switch this checkbox on whenever multi-channel audio such as stereo, 5.1, and 7.1 should arrive as separate mono timeline tracks bound to one another inside the Fairlight page.

To learn more about Linked Groups, refer to Chapter 171, “Setting Up Tracks, Busses, and Patching.” With this checkbox switched off, multi-channel audio comes into multi-channel audio tracks on the Timeline.

- Import AAF to current timeline: Brings the AAF into the Timeline currently loaded, rather than building a fresh timeline in the Media Pool.

Insert Additional Tracks: Hands fresh tracks to the Timeline automatically, keeping the AAF referenced media from writing over clips that already sit on the existing timeline. Insert with offset: Writes the AAF referenced media onto the Timeline, then nudges it along by whatever amount you've set using timecode format.

- Set timeline resolution to: A pair of fields let you state the width and height of the frame size you wish to work at within DaVinci Resolve. The default amounts to whatever resolution is named in the AAF file being imported.
- Timeline frame rate: By default this comes from the frame rate of the AAF file being imported. When you bring an AAF file into a project that already holds media in the Media Pool, the Timeline frame rate gets locked and can't be altered.
- Use drop frame timecode: As a default, this gets taken from whichever AAF file is being imported.
- EDL frame rate: As a default, this gets taken from the frame rate carried by the chosen file.
- Use drop frame timecode: As a default, this gets pulled from the frame rate carried by the chosen file.
- Mixed frame rate format: Through this drop-down menu you pick the method that conforms

mixed frame rates for rendering and playback. The “Final Cut Pro 7” or “Final Cut Pro X” conform methods are selectable, whereas for projects brought in out of Media Composer, Premiere Pro, Smoke, or other NLEs, you ought to leave it set to “DaVinci Resolve.” That same drop-down menu turns up within the Load AAF dialogs while you import a project. 4 Once every needed setting is chosen, click OK.

5 Provided you kept “Automatically import source clips into media pool,” enabled, then if the media that the AAF file links to isn't sitting at the expected disk location, or if you switched on the “Ignore file extensions when matching” checkbox, a further dialog comes up asking you to pick the folder holding the media for this project. Do one of the following: Should you wish to attempt relinking to media sitting at a different disk location: Click Yes, then navigate over to the folder housing your media (every subfolder gets walked automatically as well), highlight it, and click OK. Should you instead wish to merely bring in the Timeline carrying every offline clip: Click No.

A prompt appears if all the media was not found IMPORTANT: You can always pick the top level of any volume so that all media in any directories nested within gets found automatically, but should the volume be large and packed with many files, sweeping every folder and document on the volume can turn into a remarkably timeintensive process. 6 If you clicked Yes to picking another folder, then work the folder selection dialog to browse to a different folder, and click Ok. Repeat this cycle as many rounds as you require until you've located every piece of media that timeline links to.

Picking the source folder that holds the clips your AAF brought in. The import of the AAF file completes. A fresh timeline alongside the referenced media files turns up in the Media Pool, and the Timeline opens up so its contents are visible to you. Straightforward nested clips ought to come across as well. Any clips that couldn't be linked to a matching file on disk show up red in both the Media Pool and Timeline to signal that they're offline and unlinked.

TIP: By opening the Edit Index and picking Filter Offline Clips out of the option menu, you can view a list of every offline clip on the current Timeline.

### Supported AAF Timeline Features

The extra AAF timeline information listed below gets brought into DaVinci Resolve automatically:

- Timeline Markers: Whatever timeline markers sit inside the AAF get imported. Timeline markers can likewise be written out of DaVinci Resolve to AAF for round-trip workflows.
- Nested Clips: AAF files carrying simple nested clips will be imported by DaVinci Resolve.
- Boris Continuum FX: The effects and settings of Boris Continuum FX get brought in together with a timeline through AAF export. The same Continuum suite of effects has to be installed on both machines (the OFX version for DaVinci Resolve, AVX for Avid). Upon importing an AAF, the Boris Continuum effects applied in the original NLE turn up on every affected clip within the resulting DaVinci Resolve timeline, with every parameter you'd applied earlier on hand in the Inspector. For now, the Sapphire and Mocha suites can't be imported through AAF.

### Performing an AAF Avid Round Trip

A thorough workflow for building projects in Media Composer that will work with DaVinci Resolve, carrying projects from Media Composer into DaVinci Resolve, then grading, rendering, and returning the finished graded project to Media Composer, is laid out in this section. The procedures within the steps below address these tasks:

- Bringing in all media as high quality MXF-wrapped DNxHD, then round tripping out of Media Composer into DaVinci Resolve.
- Bringing in and editing Resolve-compatible AMA-linked media formats, then round tripping out of Media Composer into DaVInci Resolve.
- Converting AMA-linked media files down to offline-quality DNxHD clips so you can edit, after which an AAF file gets written out and reconformed within DaVinci Resolve against high quality camera original media over the course of the round trip.

Since there are so many ways that Media Composer is able to ingest media and produce AAF projects, acquaint yourself with the procedures that follow before you press on with a project of your own.

### Step 1–Create a Project in Media Composer

1 As you build a project in Media Composer, note the image format details, since these ought to be matched within DaVinci Resolve. Specifically, set the image format (e.g., 1080p/24) along with the raster dimensions (e.g., 1920x1080) to fit the mastering format you're after. As well, color space ought to be set to RGB 709 when you plan on sending ingested/transcoded media out of Media Composer into DaVinci Resolve for grading. NOTE: The Avid Project Format tab can also surface this information.

2 Open your project and bring all the media you need into a fresh bin using one or both of the approaches below: Transcode media for editing: For AAF import and round-trip workflows, the most straightforward path is to ingest transcoded, native MXF-wrapped DNxHD media by way of the Import command. Import AMA-linked clips: AMA-linked clips can be imported as well, provided every AMA-linked file sits in a format that works with DaVinci Resolve. Bear in mind that Media Composer cannot consolidate every AMA-compatible format. Here, bring AMA-linked media into a fresh bin through the Link to AMA File(s) command, and edit as you normally would. After every needed piece of media is ingested, you can edit your project just as you would any other, while staying mindful of which effects work with DaVinci Resolve. To learn more about effects across Media Composer to DaVinci Resolve round trips, refer to Chapter 55, “Preparing Timelines for Import and Comparison.”

### Step 2–Exporting an AAF for DaVinci Resolve

After you wrap up editing, you have to write out an AAF that will conform the .mxf media you worked with in Media Composer into a DaVinci Resolve timeline. Depending on whether DaVinci Resolve and Media Composer sit on the same system, two export configuration options exist. 1 Pick the sequence you wish to export, and choose File > Output > Export to File. 2 Within the Export As dialog, key in a name for the AAF file you're about to write out. 3 Pick a place to store the AAF. You may keep it wherever you like, but should you be carrying the project to another workstation, you might wish to store it within a specific folder on a removable hard drive where you keep your AAF and XML files. The spot you settle on can double as the location of the media that gets exported alongside the AAF. 4 Click the Options button to bring up a fuller window of export settings. 5 Switch on the AAF Edit Protocol checkbox. With this option, Media Composer is compelled to write a simplified AAF file that meshes better with the project exchange workflows of various applications. 6 Pick the suitable option out of the Export Method pop-up menu to set how the AAF and the media accompanying it get exported. Your pick hinges on this: Where both Media Composer plus DaVinci Resolve live on a single system: Choose “Link to (Don't Export) Media” so the AAF file you write links back to media that already sits at its current spot. Open the Audio Details tab, then pick “Link to (Don't Export) Media” out of the Export Method pop-up menu. Where Media Composer and DaVinci Resolve instead live on separate systems: pick whichever of these two export methods fits: Copy All Media: For every source clip you've used, its entire matching media file gets duplicated. This can come in handy when you wish to keep the original tie of each clip to the source media file it originated from. Be aware, though, that you'll potentially export a great deal of media whenever you use this option. Consolidate Media: For finished projects this is a leaner media management workflow, since media that went unused won't be copied. Within the Handle Length field you can name extra handles, measured in frames, to tack onto the head and tail of each exported media file. Whenever a media file together with its handles overlaps another media file together with its handles, the two get merged into one exported media file.

7 (Optional) Should your project mix in formats that don't work with DaVinci Resolve, you can optionally switch on the “Transcode Video To” checkbox and pick a media format out of the pop-up menu to its right. This option automatically transcodes every piece of media in your sequence that doesn't fit the format named in the pop-up so it matches that format. 8 When you're copying or consolidating media onto a different drive, choose “Folder” from the Media Destinations Video/Data pop-up menu. Switch on the “Use Same Folder As AAF File” checkbox to store the exported media within the same folder you picked back in step 3. Leaving that checkbox switched off, you can click Select Folder to pick another spot. 9 Click Save, and once you're back at the Export As dialog, click Save once more. After export wraps up, you'll find a duplicate sequence and duplicate media filling your Media Composer bin, the suffix “.Exported” tacked onto the sequence and “.new” tacked onto each media clip. On the file system, the resulting folder holds an AAF file plus an Avid MediaFiles folder containing the exported media.

### Step 3–Conforming Your AAF in DaVinci Resolve

1 Open DaVinci Resolve and create a new project. 2 First of all, you must set DaVinci Resolve so it reads the timecode and reel number information out of the AAF files that Media Composer produces correctly. Click the gear button at the lower right-hand corner of the DaVinci Resolve window to bring up the Project Settings window, click General Options to surface the Conform Options, and do the following:

- Confirm that “Use Timecode” has been set over to “Embedded in the source clip.”
- Turn the “Assist using reel names from the” checkbox on, and choose

“Embedding in source clip file.”

Conform help drawing on reel names that are embedded inside the source clip 3 Click Save. 4 Do one of the following:

- From any page, choose File > Import AAF, EDL, XML (Shift-Command-I).
- Head to the Edit page, right-click somewhere within the Media Pool, then pick

Timelines > Import > AAF/EDL/XML.

5 Once the File Selection window opens, pick the AAF file you exported out of Media Composer, and click Open. 6 Once the Load AAF dialog comes up, whichever settings you pick govern which media files the AAF gets conformed against:

### Load AAF window conform options

To conform to the transcoded or AMA-linked media files you edited: Keep the “Automatically import source clips into media pool” checkbox switched on. For conforming against a separate batch of camera original media files: Tick both checkboxes, “Automatically import source clips into media pool” together with “Link to source camera files,” which lean on the Source Name metadata that Media Composer/Symphony writes into exported AAF files so the naming match between transcoded footage and its camera original counterpart stays tracked. For conforming against a directory of media you've chosen yourself: Tick both the “Automatically import source clips into media pool” checkbox plus “Ignore file extensions when matching.” For conforming against media sitting in the Media Pool already: Leave the “Automatically import source clips into media pool” checkbox unticked. For this to function there have to be clips in the Media Pool. 7 On top of that, make sure the “Automatically set project settings” checkbox is on. 8 Three other options bear on AAF import:

### Load AAF window conform options

Use Sizing Information: (Optional) Turn to this checkbox whenever position, scale, and rotate transform data should carry across from the source Media Composer project over into DaVinci Resolve. Import log messages as COLOR markers: Tick this checkbox and choose a color via the attached drop-down menu for markers that get placed on the Timeline bearing note text that describes import errors you might wish to investigate down the line. Import multi-channel audio tracks as linked groups: Switch this checkbox on whenever multi-channel audio such as stereo, 5.1, and 7.1 should arrive as separate mono timeline tracks bound to one another inside the Fairlight page. To learn more about Linked Groups, refer to Chapter 171, “Setting Up Tracks, Busses, and Patching.” With this checkbox switched off, multi-channel audio comes into multi-channel audio tracks on the Timeline. 9 Click OK.
