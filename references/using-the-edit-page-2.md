# Using The Edit Page (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

The Edit Index lets you tailor its columns so the details that matter to you come first. Ways to tailor the Edit Index's metadata columns: To show or hide columns: Right-click atop any Edit Index column and pick an entry from the contextual menu list to check or uncheck a given column. Columns left unchecked stay out of sight. To rearrange column order: Pull any column header rightward or leftward to reorder the columns. To resize any column: Pull the divider between two columns right or left to make that column narrower or wider.

The Edit Index also lets you tailor column layouts. After you've built a column layout that suits your particular need, you can store it to bring back later. Ways to store and reuse a custom column layout: Building a column layout: Get the columns a given task needs shown, hidden, resized, and rearranged, then right-click a Media Pool column header and pick Create Column Layout. Into the Create Column Layout dialog, type a name, then click OK. Bringing a column layout back: From a right-click on any Media Pool column header, pick the name of whichever layout you want. All your custom layouts gather at the top of the list. Removing a column layout: From a right-click on any Media Pool column header, pick the layout's name out of the Delete Column Layout submenu.

### Filtering the Edit Index

The options in the Edit Index's option menu let you filter for particular things you want to inspect—whether running through every marked clip to catch any notes that need handling, singling out all offline clips, or combing through edits to spot anything needing a fix. The Edit Index can be filtered these ways:

- Show All: Shows all entries in the list. Pick this option after using any of the others to return to viewing the whole timeline.
- Show Active Track Items: Filters out every clip sitting on tracks above or below the ones marked with a destination control. Say you have three video tracks with the destination control on track V2; then every clip on tracks V1 and V3 gets hidden from the Edit Index.
- Show Video Track Items: Strips every audio clip out so the list holds video clips alone.
- Show Audio Track Items: Strips every video clip out so the list holds audio clips alone.
- Show Flags: Singles out clips carrying flags in the list. A submenu lets you choose to show every clip with

flags or only clips with a particular color of flag.

- Show Markers: Singles out every clip carrying markers in the list. A submenu lets you choose to show all

clips with markers or only clips with a particular color of marker.

- Show Clip Colors: Singles out every clip tagged with clip colors in the list. A submenu

lets you opt to show every clip tagged with any clip color at all, or just those tagged in one specific color.

- Show Through Edits: Filters for only the clips holding through edits—cuts where continuous timecode runs from the outgoing into the incoming half of the edit—which, depending on the reason they exist, you might choose to remove or to leave alone.
- Show Offline Clips: Singles out every offline clip (those that have come unlinked from their matching source media on disk) in the Timeline, so you can jump to each one fast and sort out the issue.
- Show Clip Conflicts: Filters for every clip wearing a clip conflict warning badge (signaling reel, name, and timecode metadata that overlaps another clip's) in the Timeline, so you can jump to each one fast and confirm the right clip is in use.
- Show Clips With Speed Effects: Filters for every clip in the Timeline carrying linear or variable Speed Effects.
- Show Clips With Composite Effects: Filters for every clip whose Composite mode or Opacity settings differ from the default (Normal, 100).
- Show Clips With Transform Effects: Filters for every clip with changed Transform settings.
- Show Clips With Filters: Filters for every clip that has Resolve FX or OFX filters applied.
- Show Stills and Freeze Frames: Filters for every clip that's a still or that carries freeze frame speed

effects applied to them.

- Show Compound Clips and Nested Timelines: Filters for every compound clip and nested timeline in

the Timeline.

- Show VFX Connect Clips: Filters all Fusion Connect Clips.

### Exporting the Edit Index

Should you have filtered a run of edits in the Edit Index you'd like to pass to someone else, doing so is simple. For instance, you might filter the Edit Index down to a list of every offline clip in the current timeline, then export that list as a .csv or .txt file to hand your assistant editor so they can track down the media required. Both file types play nicely with spreadsheet and database software, should you wish to pull the data into a different application. Exporting the Edit Index goes like this: 1 Open the Edit Index option menu and pick Export Edit Index off the contextual menu. 2 Within the Export Edit Index window, choose where the exported file should be saved, then choose a format from the bottom drop-down menu. Two export choices exist: a Comma Separated Values (.csv) file, or alternatively a Tab Delimited Values (.txt) file. 3 Click Save.

### Tracks

A number of the most-used track controls are gathered together in the Track Index. You reach the Track Index by clicking the Index Pane and choosing the Tracks Tab. The index lays out all the current tracks in your timeline along with their position and attributes. Each of these can be changed right inside the Track Index.

### The Tracks Index

### Tracks Index Columns

Every track exposes a handful of information columns. You can reorder these columns by pulling the column headers right or left, according to which information weighs most for you. A click on a track row picks that track for changes.

The information columns on hand are:

- Color: The track's present color is shown. Right-click anywhere in the row and pick Change Track Color to choose a new one.
- #: Shows the present track order. To reorder the tracks, drag this column's number up or down through the track hierarchy and release. Bear in mind the literal absolute track number (V1, A1, etc.) doesn't budge—what shifts is which track is mapped to that number.
- Name: The Track's name. You can click into this field to rename the track.
- Track Controls: The very track controls found in the Track Header in the Timeline can be reached here too: Lock/Unlock, Disable/Enable Video Track, Solo, and Mute.
- Format (audio track only): Shows the audio track's present format. You can switch this format to any other by right-clicking anywhere in an audio track's row and choosing Change Track Type to, then picking a new format off the contextual menu.
- Monitor (audio track only): Picks which tracks can be chosen in the monitor drop-down menu up at the top right of the Edit Timeline or Fairlight page windows.
- ADC (audio track only): Ticking this box switches on Automatic Delay Compensation (ADC) for the track.

Right-clicking one track or several in the track index lets you delete every selected track by choosing Delete Tracks off the contextual menu. A click on the Tracks Index's option menu lets you bring in or leave out track types (video, audio, subtitle) from the tracks.

### Markers

With the Marker Index you can readily view, edit, and organize every one of your timeline and clip markers from one handy spot. You reach the Marker Index by clicking the Index panel and choosing the Markers tab. Ways to work with markers in the Marker Index:

- To filter markers in the Marker Index: Open the Marker Index's Option menu, then pick Show All, or pick Show Only to single out one specific color. Every clip bearing a matching marker lands in a list, its columns mapping to the color(s), information, and notes of every timeline and clip marker. You can sort columns in ascending or descending order by clicking the column header. Individual columns can be switched on or off by right-clicking the column header and checking or unchecking the column name.
- To send the playhead to where a marker sits, working from the Marker Index: In the list, give that marker's entry a double-click.
- To edit marker information: You can alter a marker's values by clicking into the Name, Notes, or Keyword fields and editing the text field. Other values can't be edited in the Marker Index and ought to be changed in the timeline marker's Edit dialog.
- To search for a specific marker: Click the Search icon (magnifying glass) and type your search terms in. For now the search only looks at the Marker Name column; you can't search by notes and keywords.
- To switch between Thumbnail and List view: Click either the Thumbnail or List View icons up in the Marker Index's top bar.

The Marker Index's List View mode lets you edit and organize all of your timeline's markers from one spot.

### Source and Timeline Viewers

Out of the box, the Edit page offers a classic source/record style editing experience. The Source Viewer lets you look over individual clips from the Media Pool to ready them for editing. The Timeline Viewer, meanwhile, lets you play through your program, showing the frame at wherever the playhead sits in the Timeline.

### Source and Timeline Viewers

To choose a viewer, click it with the pointer or press Q (Source/Timeline Viewer); the viewer that currently holds focus has its name rendered in orange.

### How Each Clip's Grade Looks in Each Viewer

Owing to DaVinci Resolve's deep color and effects tools, how the image looks in each viewer of the Edit page hinges on several factors.

### The Source Viewer

The Source Viewer presents each clip the way it looks at the source. If Resolve Color Management (RCM) is switched on or source LUTs are applied, then the Source Viewer presents your clips as RCM and/or the source LUTs are processing them, since those operate as source-level color operations. Without RCM and source LUTs, though, the image in the Source Viewer matches exactly what's on disk. If your log-encoded media looks flat and low in contrast, that's just how it'll appear in the Source Viewer.

### The Timeline Viewer

The Timeline Viewer obeys every rule the Source Viewer does, plus it additionally shows how each Timeline clip looks once Fusion page and/or Color page operations are applied, since the Timeline Viewer is in fact presenting the Color page's output—so you can see each clip of your program in the context of how the DaVinci Resolve image processing pipeline is affecting the image. NOTE: The Color Viewer Lookup Table options found in the Project Settings' Color Management panel touch only the GUI Viewer in the Color page. They leave the Edit page's viewers alone. Turning Grades and/or Fusion Effects Off in the Timeline Viewer The Color page's Bypass Color Grades and Fusion Effects button/drop-down is on hand in the Edit page too, reachable either through the View > Bypass Color and Fusion drop-down or through a toggle button/ drop-down menu in the Timeline Viewer. Pick Bypass All Grades or click the Viewer control and you switch off whatever sits checked in the optional menu, which lets you decide whether to bypass both Color and Fusion or just one of the two.

(Left) The menu commands that bypass Color and Fusion, (Right) The Edit page's Timeline Viewer controls Switching color grades and Fusion effects off is a simple way to boost playback performance on low power systems when all you need is to knock out a quick set of edits, and it's a handy way to quickly size up the original source media as well.

### Timecode Toolbar on Edit Viewers

You can switch on the same Timecode toolbar from the Media page over in the Edit page. Inside the Edit page Source or Timeline Viewer, pick the Option (3-dot) menu and pick Show Timecode Toolbar from the drop-down. The Timecode Toolbar presents the In/Out point timecodes along with the total duration that's been set.

### The Timecode toolbar activated in the Source monitor

### Source and Timeline Viewers vs. Single Viewer Mode

Should you want to reshape the Edit page layout to tuck away the Source Viewer, you can pick Workspace > Single Viewer Mode so that just one viewer contextually shows either a chosen Source Clip or the Timeline's current frame.

Under Single Viewer mode, whatever you pick in the Media Pool or Timeline drives which controls turn up in the Viewer, letting you do nearly all of what you'd do with two viewers open at once.

### Single Viewer mode turned on

### Previous and Next Clips or Timelines in Viewers

Across the Media, Edit, and Color pages, the Viewer's Option (3-dot) menu lets you hop to the recent next/previous clip or timeline right out of its submenu. In the Edit page Source Viewer the entries read Previous/Next Clip; in the Edit page Timeline Viewer they read Previous/Next Timeline.

Selecting the next clip from the Viewer Option menu

### Viewer Controls

Both viewers have these onscreen controls in common:

- Zoom drop-down menu: Picking Fit sizes the currently visible frame to the Viewer's available room. Picking a percentage zooms the visible frame to that size. You can also lean on the scroll wheel function of your mouse, trackpad, or tablet to zoom into and out of the Viewer..
- Duration field: Up at the Source Viewer's top left, this shows the clip's total duration, or the span from the In to the Out point if those have been set. Within the Timeline tab, this shows the total duration of whichever timeline is currently chosen.
- GPU Status Display: Each viewer in DaVinci Resolve carries a GPU status indicator plus a frame-per-second (FPS) meter, shown in the Viewer's title bar, which reveals your workstation's performance any time playback kicks off. Since every bit of image processing and effects in DaVinci Resolve runs on one or more GPUs (graphics processing units), the GPU status display reveals how much processing power whichever clip is playing is consuming.
- Clip Name: Right at the middle of the Source Viewer title bar, the clip name sits.

The Source Viewer: Up at the Source Viewer's top, next to the name of the clip currently open, a drop-down appears that opens a menu listing the 10 most recent clips you've opened in the Source Viewer. That list runs first in, first out, the newest-opened clips up top. Should you wish to wipe the visual history in the menu, you can clear unwanted entries and kick off a fresh queue by clicking the Viewer's option menu and picking Clear Recently Viewed Clips. The Timeline Viewer: Shows the timeline name and doubles as a drop-down menu letting you flip among other timelines in the current project. The clip/timeline name turns orange whenever the Source or Timeline Viewer holds focus.

- Bypass Color Grades and Fusion Effects: The Color page's Bypass Color Grades and Fusion Effects button/ drop-down is on hand in the Edit page too, reachable either through the View > Bypass Color and Fusion drop-down or through a toggle button/drop-down menu in the Timeline Viewer. Switching color grades and Fusion effects off is a simple way to boost playback performance on low power systems when all you need is to knock out a quick set of edits, and it's a handy way to quickly size up the original source media as well.
- Source/Timeline Timecode/Frame/Keykode Display: Up at the Source Viewer's top right, this field shows the timecode of the current frame at wherever the playhead sits in the Source Viewer's jog bar, and a right-click plus a pick from the contextual menu flips it among source timecode, source frame, and keykode. Within the Timeline Viewer, this field reports the record timecode of the present frame wherever the playhead lands in the Timeline, and a right-click plus a contextual-menu pick flips it among source and record timecode, source and record frames, and keykode.
- Source Viewer Option menu: Contains the following commands:

Gang Viewers: With Gang Viewers turned on, the Source and Timeline Viewer playheads lock to each other, traveling as one. That comes in handy when you need to line up the timing of a portion of a Source Viewer clip with some event over in the Timeline. Live Media Preview: On by default, it lets thumbnails you skim in the Media Pool show the skimmed frame in the Viewer. While skimming with Live Media Preview on, the playhead shown in the thumbnail stays locked to the playhead shown in the Viewer's jog bar. Show Timecode Toolbar: The Timecode toolbar presents the In/Out point timecodes along with the total duration that's been set.

Show All Video Frames: When the processing power on hand falls short of playing the clip or clips at the playhead's position—owing to the grade, transforms, or effects applied at that moment in the Timeline—you get to decide exactly how performance in DaVinci Resolve degrades. Off, DaVinci Resolve favors audio playback and drops video frames when processing power runs tight, giving a more conventional playback experience. On, audio quality takes a hit while every video frame plays in slower-than-real time to keep playback going. Show Zoomed Audio Waveform: Switched on, it lays an audio waveform overlay across the bottom of the Source Viewer with a zoomed-in slice of the audio around the playhead's current position. Show Full Clip Audio Waveform: Switched on, it lays an audio waveform overlay across the bottom of the Source Viewer that shows the audio over the clip's full duration. Previous Clip: Jumps to the prior clip held in the Media Pool. Next Clip: Jumps to the following clip held in the Media Pool. Clear Recently Viewed Clips: Empties the Source Viewer's recollection of its recent clips. Show Marker Overlays: On by default; while playback is paused, any marker the playhead crosses appears superimposed in the Viewer. Markers submenu: Whenever one or more markers sit on the Source Viewer's clip, they're listed here chronologically by Name and Note. Pick a marker off this menu and the playhead leaps to it within the Source Viewer.

- Timeline Viewer Option menu: Contains the following commands:

Gang Viewers: With Gang Viewers turned on, the Source and Timeline Viewer playheads lock to each other, traveling as one. That comes in handy when you need to line up the timing of a portion of a Source Viewer clip with some event over in the Timeline. Show All Video Frames: Should the processing power available prove too little to play the clip or clips at the playhead's spot—because of the grade, transforms, or effects in force at that moment in the Timeline—you can dictate precisely how DaVinci Resolve's performance gives way. Off, DaVinci Resolve puts audio playback first and sheds video frames whenever processing power gets scarce, yielding a more conventional playback experience. On, audio fidelity suffers while each video frame plays slower than real time so playback can carry on. Show Timecode Toolbar: The Timecode toolbar presents the In/Out point timecodes along with the total duration that's been set. Timeline Sort Order: These options let you set the sort order timelines use in the timeline selector at the top middle of the Viewer. You can pick from Alphabetical, from Creation Date, or from Recently Used (which surfaces the 10 timelines most recently in active use). Previous Timeline: Jumps to the prior timeline held in the Media Pool. Next Timeline: Jumps to the following timeline held in the Media Pool. Show Marker Overlays: On by default; while playback is paused, any marker the playhead crosses appears superimposed in the Viewer. Show Timecode Overlays: Switched on, it shows the source timecode of the video and audio clips sitting under the playhead while playback is paused. Show Overlays During Playback: Switched on, it keeps timecode and marker overlays on the Viewer steadily throughout playback. Switched off, overlays only show while playback is paused. Markers submenu: Whenever one or more markers sit on a Timeline, they're listed here chronologically by Name and Note. Pick a marker off this menu and the playhead leaps to it within the Timeline.

- Source Viewer Mode drop-down (Source Viewer only): Depending on the task in front of you, this drop-down menu has the Source Viewer present various views of the clips under your hand.

Source: Plays the video of whatever clip is open in the Source Viewer. Offline Reference Movie button: Have you assigned an offline reference movie to the timeline now chosen, a click on the Offline Mode button brings that offline movie up so you can set it beside the timeline now open. While this mode is on, Source and Timeline playback stay in sync; an Offset field takes the duration field's place, so you can re-sync the offline reference movie should that be needed. Audio Track: Lays out the audio waveforms for every channel of whatever clip is open in the Source Viewer. Across the top, this audio-only view runs the waveform for the clip's whole length, while the viewer's main area carries a zoomed-in stretch of the audio waveform. The zoom drop-down up at the Source Viewer's upper left corner dictates how far the zoom goes. Multicam: Brings up the multi-angle Multicam Viewer, which you can lean on to swap among assorted angles of video and audio as you multicam edit a clip in the Timeline. For a fuller account of multicam editing, see Chapter 42, "Multicam Editing." Annotations: Lets you draw straight onto the current frame to mark areas needing further attention.

- Transform Mode drop-down (Timeline Viewer Only): It serves at once as a toggle switch and as a drop-down menu. A click on the left-hand button control turns on or off the onscreen controls with which you transform the clip directly inside the viewer. A click on the right-hand drop-down control lets you switch across two transform modes:

Transform: Surfaces the following controls — Pan (X) and Tilt (Y), Scale X and Y, and Rotation. Crop: Brings up controls that crop from the top, bottom, left, and right. Dynamic Zoom: Surfaces controls for fast pan and scan effects on the picked clip. OpenFX Overlay: Brings up the onscreen controls of an OpenFX filter that's been applied. Fusion Overlay: Brings up the onscreen controls of a Fusion FX or Title filter that's been applied. Annotations: Lets you draw straight onto the current frame to mark areas needing further attention. A right-click inside the viewer lets you grab a particular control off the drop-down list. You can likewise Tab and Shift-Tab among the Fusion controls in the inspector to land on a control. Smart Reframe: Brings up the onscreen controls of the Smart Reframe.
