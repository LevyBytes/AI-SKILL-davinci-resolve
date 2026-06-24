# Exporting Timelines To Other Applications (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Exporting Timelines to Other Applications

After a program is edited and graded, you might have to write your finished graded timeline out as EDL, AAF, XML, or OTIO files so it can travel to another application for added finishing, effects work, or to round-trip back from an NLE. Sending a graded project onward to another application first calls for rendering the graded clips, using the Deliver page controls to lay the Timeline down as separate source clips. Under this mode, each rendered clip’s reel name and timecode metadata is carried over into the exported project file, which keeps exported EDL, XML, AAF, or OTIO data tied to the media that was rendered. For a thorough account of rendering on the Deliver page, turn to Chapter 187, “Rendering Media.” Should you render with the Easy Setups matching Final Cut Pro XML or Avid AAF round trips, an XML or AAF lands in the very same directory your render went to. Even so, exporting an XML, AAF, or EDL file on its own remains an option whenever that need comes up. Or, if a project was built from scratch inside DaVinci Resolve and a timeline has to head to another application, you’re free to write any timeline out in any format for project exchange, with no fresh media to render (your workflow permitting). Even when a timeline came in from another application, the wide-ranging project compatibility of DaVinci Resolve lets you bring in one species of project exchange file, say XML, and then send out an altogether different one, such as AAF or EDL. That turns DaVinci Resolve into a project exchange utility.

### Exporting Timelines from DaVinci Resolve

Post-production today is rarely handled under a single roof. Shuttling timelines and assets among numerous applications from all sorts of companies is a routine requirement. DaVinci Resolve carries its own proprietary .drt format for ferrying timelines between DaVinici Resolve workstations, yet the program also packs a capable toolset for sending your assets out to plenty of other well-known applications. At the time of writing, here’s the surest route for passing DaVinci Resolve timelines from one application to another. Moving from DaVinci Resolve to/from another DaVinci Resolve workstation, going either way: use Export/Import on a DaVinci Resolve Timeline file (.drt). Moving from DaVinci Resolve to/from another application, going either way: reach for Export/Import on an OpenTimelineIO file (.otio, .otioz), where it’s supported. Lacking that support, drop back to XML or AAF flies in its place.

### Exporting to OTIO

For moving timelines into and out of applications, DaVinci Resolve handles the Open Timeline IO (.otio) format. OTIO is an open source interchange format for media and timelines, the work of the Academy Software Foundation. Built to stay neutral about both application and platform, it lets you hand off your timeline along with its media assets across programs at higher compatibility than AAF or XML manage. DaVinci Resolve recognizes two distinct OTIO formats: .otio: A file of this kind holds nothing but the timeline’s metadata, with no media attached. Such files stay small and portable, leaving the recipient to relink the timeline to their own media copies. .otioz: A bundle file of this sort packs the timeline metadata together with every one of the timeline’s media assets, all zipped into a single file. That can make the file enormous, since it carries the full-length media files for each asset the timeline draws on. The upside is that whoever opens it receives all the media required, automatically linked, so the timeline rebuilds flawlessly on their machine.

Writing out an OpenTimelineIO (.otio, .otioz) file runs like so: 1 Select File > Export > Timeline (Shift-Command-O). 2 Give the timeline file a name. 3 Within the file browser, pick either .otio files or .otioz bundle files from the format selector. 4 Click Save. NOTE: Choosing to export .otioz bundle files triggers an extra OTIO-bundle-building pass, during which every complete media file from each clip in the timeline gets folded into the finished bundled file. That can run long and may demand extra storage, depending on how much media is in play and how lengthy it is.

### Exporting to AAF/XML

No matter whether your project was cut from scratch within DaVinci Resolve, or you’re round-tripping through an application that runs on AAF, on Final Cut Pro 7 XML, or on the Final Cut X XML format for project exchange, any DaVinci Resolve timeline on the Edit page can be written out to whatever project format DaVinci Resolve handles. Whatever your workflow, bear these points in mind: Timelines export on their own as you render a timeline on the Deliver page: Reach for either the “Final Cut Pro Round-Trip” preset or the “Avid AAF Round-Trip” one among the render setting presets, or some preset spun off from one of them, and a matching XML or AAF file goes out on its own beside the media you render. Even a project pulled in from another application stays open to re-editing before you export it: Where it’s called for, feel free to re-edit projects bound for export. Once you write out an AAF or XML file, the Timeline heads back to the NLE it came from, or forward to whichever finishing application you favor. Round-Trip workflows sometimes hold on to unsupported effects: When the original sequence carried effects or clip constructs that DaVinci Resolve couldn’t support, the handling of those effects hinges on the project format you’re exporting toward, and on whether the project got edited. With XML projects, unsupported effects are tucked away inside DaVinci Resolve and ride out with whatever XML file you produce, no matter what. So they ought to surface again when you reopen the exported file in the NLE it came from. With AAF projects, exporting unsupported effects works only while the project goes un-re-edited. Re-edit it, though, and the AAF file you can export is one purged of every unsupported effect. Project formats convert into other formats: Through DaVinci’s Export commands, compatible project formats can shift from one format into another. An imported EDL, for one, can come out as Final Cut Pro X XML. By the same token, Final Cut Pro 7 XML can be brought in and then sent back out as Final Cut X XML. Or an AAF file out of Media Composer can be imported and afterward exported as a Final Cut Pro XML file, ready to open in any NLE or finishing application that handles that format, Premiere Pro or Smoke among them.

To export an AAF or XML file once the graded clips are rendered: Do one of the following: 1 With the current Timeline in hand, either choose File > Export AAF, XML, or instead press Shift-Command-O.

- On the Edit page, right-click in the Media Pool the Timeline you mean to export, and choose Timelines > Export > AAF/XML.
- As the Export XML dialog comes up, key in a file name, pick a spot for the exported XML file, then click Save.

2 An XML rendition of that timeline gets written, references to the graded media you rendered and all, set to import into an NLE or finishing application.

### More About Exporting to AAF

Exporting to AAF actually puts two choices in front of you, hinging on whether you reworked the Timeline editorially on the Edit page: Where you left the imported Timeline’s edit untouched: You can choose File > Export AAF, XML, and pick “AAF Files” out of the Format dropdown menu. That writes out every bit of audio and effects drawing on data from the original AAF file Media Composer exported, whether or not DaVinci Resolve supports them. As you export an unedited AAF, DaVinci Resolve leans on the Avid AAF file you first imported to build a refreshed one, so confirm it still sits where it was the day you first brought it into DaVinci Resolve. Where you did rework the imported Timeline’s edit, or you’re exporting a project that started as something other than AAF: You then have to right-click in the Media Pool the Timeline you mean to export and choose Timelines > Export > Generate New AAF. That choice mints a wholly new AAF file, though any audio and effects an AAF import brings in that DaVinci Resolve doesn’t support are thrown out.

### Exporting an EDL

DaVinci Resolve can likewise write out EDLs that other applications can pull back in. For fuller coverage of EDL workflows, three chapters help. There’s Chapter 24, “Ingesting From Tape.” You can also see Chapter 56, “Conforming and Relinking Clips.” plus, on the conform side, Chapter 60, “Conforming EDL Files.” Here’s how an EDL gets exported: 1 Open the Edit page and, in the Media Pool, pick the Timeline you want an EDL from. 2 An exported EDL holds only one video track. On timelines carrying several tracks, just the events on whichever video track owns the destination control get exported (that destination control being the leftmost control in the track header). To export a track that isn’t Video 1, hand the destination control to the particular track you need exported. 3 Right-click the Timeline within the Media Pool, and choose Timelines > Export > AAF/XML/EDL out of the contextual menu.

4 As the Export Timeline dialog comes up, enter a name, pick a spot for the exported EDL, choose EDL Files from the dropdown menu along the bottom, then click Save. Your EDL is written out.

### Exporting a Missing Clips EDL

This command writes out a quick report naming every clip that sits offline in the track you currently have selected on the Edit page’s Timeline. That report comes in EDL format, an event per offline clip, each spelling out the missing media’s reel number and source timecode, plus the record timecode marking where the missing media falls on the Timeline. An example of an exported Missing Clips EDL follows:

### TITLE: ( no title ) 1 A001_C002_0820GA_001 V

C 10:28:27:03 10:28:28:00 01:00:00:00 01:00:00:21

2 A004_C012_0820MC_001 V C 14:07:31:21 14:07:35:13 01:00:12:13 01:00:16:05

3 A017_C001_0820CV_001 V C 21:16:14:22 21:16:15:00 01:00:16:05 01:00:16:07

With this information exported, you can pass it along to whoever is able to help you run down the media that’s gone missing. Exporting a Missing Clips EDL goes thus: 1 Open the Edit page and, in the Timeline browser, open the Timeline you want a Missing Clips EDL for. 2 On timelines with several tracks, the hunt for missing clips covers only the events on whichever video track holds the destination control. To scan a track other than Video 1, pass the destination control to the specific track you need checked for missing clips. 3 Right-click the Timeline within the Media Pool, and choose Timelines > Export > Missing Clips EDL out of the contextual menu. 4 As the Save Missing Clips EDL dialog comes up, enter a name, pick a spot for the exported EDL, then click Save.

### Exporting Timeline Markers to EDL

Should you stash project notes inside the notes field of Timeline markers, the ones sitting in the Timeline ruler, those notes can be written out as an EDL. Here are the steps for putting timeline markers out this way: 1 Right-click that timeline within the Media Pool, and choose Timelines > Export > Timeline Markers to EDL. 2 From the Export Edit Index dialog, settle on a location and export format, then click Save. The resulting EDL names every Timeline marker, folding in whatever notes there are along with a duration wherever that applies.

### Exporting to CDL

Through a Color Decision List (CDL), DaVinci Resolve can move basic grading data both out to and in from other applications. The CDL is an industry-standard file format that first came out of the technology committee at the American Society of Cinematographers. DaVinci Resolve handles the 1.2 CDL standard, which, channel by channel across red, green, and blue, lays down the slope, offset, and power, and on top of that captures every clip’s overall saturation throughout a program. A CDL file is laid out much like an EDL, its SOP (Slope/Offset/Power) and SAT (Saturation) values tucked in as metadata roughly the way comments sit inside a more ordinary EDL. Here’s an example of a single CDL event: 020 001 V C 03:02:49:13 03:02:53:00 01:01:28:11 01:01:31:22 *ASC_SOP (1.109563 1.717648 0.866061)(-0.238880 -0.390357 0.353743) (0.672948 1.384022 0.889876) *ASC_SAT 1.000000 Since a CDL pins down a grade so narrowly, any project you intend to send out to other applications by way of a CDL has to stay within just the operations the CDL defines mathematically. A few things are worth bearing in mind:

- What gets exported is limited to the primary corrections sitting in each clip’s first node.
- Keep yourself to the Lift/Gamma/Gain, Offset, and Saturation controls and nothing else.
- No keyframes ever go out. Where a grade carries keyframes, only the parameter values living at

the clip’s opening frame come into play.

- Both the track grade and any group grades are passed over entirely.
- Should the first node hold an HSL Qualifier or a Power Window, that gets skipped, and the corrections sitting in

that node are exported as though they were a primary correction.

- Steer clear of Y’ only adjustments; CDLs can’t accommodate them. So that the CDL you export

stays accurate, set the Lum Mix parameter, found in the Primary Controls palette, to 0 on every grade. When CDL export crops up often in your workflow, switching on the “Luminance Mixer defaults to zero” option, over in the Color section of the General Options panel within the Project Settings, locks this parameter at 0 every time. Once your timeline satisfies all of the limits above, a CDL export is within reach. The steps run thus: 1 Open the Edit page, right-click in the Media Pool the Timeline you mean to export, and choose Timelines > Export > CDL out of the contextual menu. 2 Give the CDL a name, pick where to save it, and click OK.

For more on bringing in a CDL to layer grades onto your project, turn to Chapter 149, “Copying and Importing Grades Using ColorTrace.”

### Exporting the Edit Index as a CSV or TXT File

Whatever the Edit Index currently holds, on the Edit page, can be written out as a stand-alone file you can reference in all sorts of ways. The export goes like this: 1 Open the Edit Index and, where needed, pick one of the Edit Index filters out of the Edit Index option menu. You might, say, narrow the edit index to Offline Clips Only when you want a list of every offline clip in the present timeline written out. 2 Right-click that timeline within the Media Pool, choose Timelines > Export > Edit Index, then settle on a location and export format in the Export Edit Index dialog, and click Save.

### Exporting to ALE

DaVinci Resolve can write out ALE (Avid Log Exchange) files too. ALE is a tab-delimited, ASCII text-based clip logging list format whose purpose is to shuttle clip metadata that won’t fit inside MXF files. The point of an ALE file is to let you put out a log of every clip a given timeline uses, carrying all the metadata DaVinci Resolve has tied to those clips, so that metadata can be pulled into and matched up with clips over in Media Composer or Symphony. An ALE file breaks into three parts, named Heading, Column, and Data:

- The Heading lays out details about the clips under log, the picture and audio format among them, along with the frame rate.
- The Column line sets out each metadata column the list will export. A baseline set of metadata columns rides along automatically, filled in or not. On top of those, DaVinci Resolve tacks extra metadata columns onto the list whenever the matching metadata field in the Metadata Editor holds something. Type entries into the Camera, Keyword, and Shot fields of the Metadata Editor, for instance, and those columns join the exported ALE. No user setting governs any of this.
- The Data section runs several lines, one per event the list references, each holding all of the data that belongs to that clip.

When you export stereoscopic clips out of stereoscopic timelines, these extra metadata columns ride along automatically inside the pair of ALE files that get produced:

- Pan (measured against timeline resolution)
- Tilt (measured against timeline resolution)
- Zoom
- Rotate
- Convergence (measured against timeline resolution)
- HFlip (0 or 1)
- VFlip (0 or 1)

When the ALE files come out of projects built on ARRIRAW clips, these further metadata columns may be folded in:

- Temperature
- Tint

To export an ALE file: 1 Open the Edit page, right-click in the Media Pool the Timeline you mean to export, and choose Timelines > Export > ALE out of the contextual menu. 2 Give the ALE file a name, pick where to save it, and click OK. The ALE file gets written, and a dialog pops up reminding you of the file path it landed at (click OK to clear it).

A short ALE export, by way of example:

### Heading

### FIELD_DELIM

### TABS

### VIDEO_FORMAT

AUDIO_FORMAT

### 48khz

FPS

### 23.976

### Colu m n

Name, Tracks, Start, End, Take, Tape, UNC, FPS, Reel, Scene, Shoot, date, Manufacturer, Source Resolution, Source, Bit Depth, DESCRIPT, Comments, Audio SR, Audio Bit Depth, Auxiliary TC1, KN Start, Source File Path, Display Name

### Data

A001_C002_V01.CBF6A4FD139AD.mxf, V, 10:28:27:03, 10:28:28:00, A001_C002_V01.CBF6A4FD139AD /Volumes/Disk_1/Avid MediaFiles/MXF/1/A001_C002_V01.CBF6A4FD139AD.mxf 23.98, DaVinci Resolve, 1920x1080, 10 /Volumes/Disk_1/Avid MediaFiles/MXF/1/A001_C002_V01.CBF6A4FD139AD.mxf A001_C002_V01.CBF6A4FD139AD A016_C008_V01.CBF6A4FD13ABD.mxf,V, 23:35:56:03, 23:36:00:11, A016_C008_V01.CBF6A4FD13ABD /Volumes/Disk_1/Avid MediaFiles/MXF/1/A016_C008_V01.CBF6A4FD13ABD.mxf 23.98, DaVinci Resolve, 1920x1080, 10 /Volumes/Disk_1/Avid MediaFiles/MXF/1/A016_C008_V01.CBF6A4FD13ABD.mxf A016_C008_V01.CBF6A4FD13ABD A004_C012_V01.CBF6A4FD1438E.mxf, V, 14:07:31:21, 14:07:35:15, A004_C012_V01.CBF6A4FD1438E /Volumes/Disk_1/Avid MediaFiles/MXF/1/A004_C012_V01.CBF6A4FD1438E.mxf 23.98, DaVinci Resolve, 1920x1080, 10 /Volumes/Disk_1/Avid MediaFiles/MXF/1/A004_C012_V01.CBF6A4FD1438E.mxf

NOTE: An actual ALE doesn’t carry the commas printed above; they appear here only to keep the fields clear.

### Exporting to ALE with CDL

Avid Media Composer and Symphony will likewise import ALE files that carry extra CDL metadata columns, the ones that bind SOP (Slope/Offset/Power) and SAT (Saturation) adjustment metadata to every clip logged in the ALE. Bring an ALE with CDL file into Media Composer and the SOP and SAT data fill metadata columns, ready to be held onto and exported across the various Avid workflows. Below is an example showing the Heading, Column, and Data sections of a sample ALE with CDL, carrying a single line of clip and CDL data.

Putting out an ALE with CDL file runs thus: 1 Open the Edit page, right-click in the Media Pool the Timeline you mean to export, and choose Timelines > Export > ALE and CDL out of the contextual menu. 2 Give the ALE file a name, pick where to save it, and click OK. The ALE file gets written, and a dialog pops up reminding you of the file path it landed at (click OK to clear it).

A short ALE with CDL export, by way of example:

### Heading

### FIELD_DELIM

### TABS

### VIDEO_FORMAT

AUDIO_FORMAT

–

FPS

### 23.976

### Colu m n

Name, Tracks, Start, End, Take, Tape, UNC, FPS, Reel, Scene, Shoot date, Manufacturer, Source Resolution, Source Bit Depth, DESCRIPT, Comments, Audio SR, Audio Bit Depth, Auxiliary TC1, KN Start, Source File Path, Display Name KeyKode, ASC_SOP, ASC_SAT, RESOLVE_SIZING

### Data

A001_C002_V01.CBF6A4FD139AD.mxf, V, 10:28:27:03, 10:28:28:00, A001_C002_V01.CBF6A4FD139AD /Volumes/Disk_1/Avid MediaFiles/MXF/1/A001_C002_V01.CBF6A4FD139AD.mxf 23.98, DaVinci Resolve, 1920x1080, 10 /Volumes/Disk_1/Avid MediaFiles/MXF/1/A001_C002_V01.CBF6A4FD139AD.mxf A001_C002_V01.CBF6A4FD139AD (1.0260 1.0260 1.0260)(-0.0260 -0.0260 -0.0260)(0.8237 0.8237 0.8237) 0.8640 (0.0000 0.0000 1.0000 0.0000 0.0000 0 0)

NOTE: Those commas above aren’t part of a real ALE; they’re printed here purely so the fields read clearly.

### Exporting Timeline Markers to EDL

This command puts out a quick report that gathers, as EDL notes, the text of every marker dropped onto the Timeline. Clip markers don’t count. The report arrives in EDL format, one event per Timeline marker, each bearing a stand-in reel number (001 unless changed) along with source and record timecodes matching where that marker sits on the Timeline (running one frame long). For every event, the EDL note carries the Marker note where one exists. No note records the markers’ color

An example of an exported Timeline Marker EDL follows:

TITLE: ( no title )

### 001 001

### V C 01:00:09:09 01:00:09:10 01:00:09:09 01:00:09:10

Replace with another car door sound effect

### 002 001

### V C 01:00:20:12 01:00:20:13 01:00:20:12 01:00:20:13

Trim this clip shorter

### 003 001

### V C 01:00:30:12 01:00:30:13 01:00:30:12 01:00:30:13

Find another stock footage clip of the bridge

### 004 001

### V C 01:00:30:13 01:00:30:14 01:00:30:13 01:00:30:14

### Trim this montage three seconds shorter

### Exporting and Importing Media Pool Metadata

DaVinci Resolve lets you write metadata out of one project’s Media Pool so it can be brought into another project’s clips, for those times you have to shift metadata around. The operation puts out the entire Media Pool’s metadata as a .csv file. Picture a DIT who loaded plenty of metadata into the DaVinci Resolve project used to turn out dailies, after which a hurried editor spun up a separate project to start cutting those dailies. Rather than make the editor retype every clip’s metadata from scratch, you can export the metadata out of the DIT’s project and import it into the editor’s fresh project, with the relevant metadata matched to each corresponding clip on its own. To export Media Pool metadata: 1 Open a project that holds Media Pool metadata you’d like to export. 2 Should you wish, single out which Media Pool clips the metadata export covers. 3 For metadata covering the whole Media Pool, choose File > Export Metadata From > Media Pool; to keep the export to just the clips you singled out back in step 2 earlier, instead choose File > Export Metadata From > Selected Clips. 4 As the Export Metadata dialog comes up, key in a name, choose where the file should be written, then click Save. The whole of the metadata goes out into a .csv file you can open and edit in any spreadsheet application.
