# Creating And Working With Timelines (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Creating and Working with Timelines

This chapter covers how timelines are built and reshaped — the containers where clips are cut together into the finished sequences that make up your programs.

### Creating and Duplicating Timelines

When you aren’t bringing in a project cut somewhere else, a fresh timeline lets you start an edit from nothing, gather clips destined for a Fusion composition, grade a batch of dailies, or build an audio program over on the Fairlight page. At creation time you may either populate the timeline with every clip sitting in the Media Pool — a fast route to a large set of offline dailies — or begin with an empty one and add chosen clips yourself. Whatever timelines you make land in the Media Pool bin that is currently active. For a quick way to view every timeline across the project at once no matter where each one lives, switch on the “Smart Bin for Timelines” option found in the Editing panel of the User Preferences. Doing so adds a Smart Bin to the Media Pool’s Bin list that gathers all project timelines, letting you survey them all while leaving your existing layout untouched.

### Individual Timeline Settings for Format, Monitoring, Output, and Color

A freshly made timeline can be tailored in several ways, though out of the box it simply inherits the project-wide timeline values for resolution, frame rate, and the rest of the format and monitoring parameters.

The Create New Timeline dialog with standard customization settings That said, each timeline can instead carry its own Format, Monitoring, Output Sizing, and Color Management values — handy whenever a job requires several timelines producing distinct deliverables whose resolutions, pixel aspect ratios, frame rates, monitoring, output scaling choices, and color management differ from the project as a whole, “Mismatched Resolution Files” settings included. Picking per-timeline values is a matter of clearing the Use Project Settings box inside the New Timeline dialog, after which extra controls show up.

Clicking Use Custom Settings exposes additional panels for individualized timeline settings After a timeline has been built with its own values, revisit them by right-clicking the timeline in the Media Pool and selecting Timelines > Timeline Settings from the contextual menu. That opens an Edit Timeline dialog whose distinct Format, Monitor, Output, and Color panels you can work through. Clicking Use Project Settings instead reverts that timeline to the project-wide values. The custom timeline settings even let you adjust the starting timecode of several timelines together. To change the start timecode for multiple timelines at once: 1 Highlight every Timeline whose timecode needs adjusting. 2 Right-click any one of those selected Timelines and pick Timelines > Starting Timecode from the contextual menu. 3 Type the replacement timecode into the Time Start field. 4 Click on OK.

### Creating Blank and Stringout Timelines

For a brand-new video or audio program you’ll generally reach for a blank timeline. That very same command, though, produces stringout timelines for dailies once the “Empty Timeline” checkbox is switched off. To create a new blank timeline: 1 (Optional) Pick or make a folder within the Bin list to hold the new timeline. 2 Do one of the following:

- Choose File > New Timeline (Command-N).
- Right-click within the Media Pool, and choose Timelines > Create New Timeline.

3 Once the New Timeline Options window appears, configure these options: Start Timecode: Adjust the Start Timecode whenever a particular start time is needed. Timeline Name: Type a name into the Timeline Name field.

No. of Video Tracks: Specify the count of video tracks you’d like. Dragging across this field also nudges the video-track count via a virtual slider. Use Fairlight Preset: With this box ticked, the timeline is built with audio tracks pre-assigned from a Fairlight Configuration preset you saved earlier. A drop-down then surfaces so you can pick the exact preset for the Timeline. That preset stands in for the No. Of Audio Tracks setting further down. Fairlight Configuration presets are built through the Fairlight Presets Library, which the Fairlight menu opens. Chapter 171 of the DaVinci Resolve Manual, “Setting Up Tracks, Busses, and Patching,” goes deeper. When no Fairlight Configuration presets exist, this option stays hidden. No. of Audio Tracks: Specify the count of audio tracks you’d like. Dragging across this field likewise sets the audio-track count via a virtual slider. Audio Track Type: Pick the channel mapping the new audio tracks should adopt. Empty Timeline: On by default, this makes new timelines start out empty. Clearing the Empty Timeline checkbox means the resulting Timeline gathers every piece of media across all Media Pool bins, in effect producing a stringout of everything imported. Use Selected Mark In/Out: Surfaces only while “Empty Timeline” is off. Ticking this checkbox makes each clip’s length in the new Timeline follow the In and Out points stored on that clip. Clips lacking In/Out points contribute their full duration. Use Custom Settings: Press this button to reveal the Format, Monitor, and Output tabs that hold per-timeline unique settings. 4 Click Create New Timeline. A new timeline is created. Should the need arise, copying an existing timeline lets you rework an edit or spin up an alternate grade. TIP: When you expect to spin up several new timelines sharing one parameter set, open the User pane of the Preferences and revise the New Timeline Settings under the Editing panel. From then on those presets feed the New Timeline Options window.

### Creating Timelines by Drag and Drop

At the moment a project is first made, the Timeline Editor holds no timeline, which gives you a chance to spin one up via drag and drop. Building a timeline this way takes a single move: pull any clip down into the vacant Timeline Editor region beneath the Viewers on the Edit page, and a fresh timeline is generated on its own.

### Creating Timelines From Bins and Selections

Through the “Create Timeline Using Bin” and “Create Timeline Using Selected Clips” commands you can rapidly build a timeline out of Media Pool contents, honoring whichever In and Out points each clip carries and relying on the host bin’s sort order to set the sequence the clips fall into. TIP: Such commands shine when you want fast assembly edits from metadata-rich media — scene, shot, and take fields for sorting clips, plus In and Out points you’ve already recorded. Assembling a timeline from everything inside a bin works like this: 1 (Optional) Switch the Media Pool to List mode, mark In and Out points on every clip in your Bin, and order the Media Pool by the column that arranges all clips the way you want them assembled. 2 Right-click that bin within the Bin list, then pick Create Timeline Using Bin. 3 Name the new timeline inside the New Timeline Properties dialog. To honor each clip’s In and Out points, confirm “Use Selected Mark In/Out” is ticked, then click Create New Timeline. Building one from clips you choose by hand instead goes as follows: 1 (Optional) Flip the Media Pool into List mode, log In and Out points across each clip in your Bin, and re-sort the Media Pool on whichever column lines the clips up in your intended assembly order. 2 Highlight one or more clips to gather into a fresh timeline. 3 Right-click any of those highlighted clips, then pick Create Timeline Using Selected Clips. 4 Name the new timeline inside the New Timeline Properties dialog. To honor each clip’s In and Out points, confirm “Use Selected Mark In/Out” is ticked, then click Create New Timeline. Out of the box, Audio Track Type sits at “Based on selected media,” so the timeline’s audio tracks mirror the channel mapping of whatever clips you chose, though you may set other specific mappings by hand when needed.

### Creating Timelines Using an IMF or DCP Composition Playlist (CPL)

DaVinci Resolve lets you generate a timeline that faithfully mirrors the Composition Playlist (CPL) belonging to a DCP or IMF package. For now this remains a DaVinci Resolve Studio only feature. The procedure built around a Composition Playlist (CPL) runs as follows: 1 Bring an IMF or DCP package into the Media Pool just as you would any other media. 2 Right-click the imported clip, then pick “Create New Timeline Using Composition Playlist” off the contextual menu. 3 Within the New Timeline dialog box, select the specific CPL from the package via the “Composition Playlist” drop-down menu. 4 Apply whatever ordinary new Timeline tweaks the job calls for (Resolution, Aspect Ratio, and the like), then click the “Create” button.

### Duplicating Timelines

Existing timelines can also be copied — useful for preserving a snapshot before you alter anything, or as the seed for an alternate version of your work. Duplicating a Timeline happens by either of these routes:

- Highlight a timeline in the Media Pool, then choose Edit > Duplicate Timeline. The copy shows up with “copy” tacked onto its name.
- Right-click a Media Pool timeline and pick Duplicate Timeline out of the contextual menu.

### Disabling Timelines

Within the Media Pool you can toggle timelines on or off for reasons of both speed and tidiness. Editors who keep a running record of a program’s edit through a steady stream of periodically copied timelines benefit most. Because a project file packed with many timelines may drag down performance, the option to switch them off lets you keep those backup or alternate timelines around at no cost. Switched-off timelines never get loaded into RAM, leave the speed of opening, saving, exporting, or loading a project untouched, and don’t weigh on program performance. Such a timeline also drops out of the viewer drop-down menus across the program. It stays visible in the Media Pool, yet wears a crossed out eye icon at the lower left to signal its state. None of the DaVinci Resolve pages will open a timeline that’s been disabled. Switching a timeline off works like this:

- Highlight the Timeline, right-click it, and pick “Disable Timeline” from the drop-down menu.

To enable a timeline:

- Highlight the Timeline, right-click it, and pick “Enable Timeline” from the drop-down menu.

TIP: Grouping and arranging Enabled versus Disabled timelines across the whole project is simple — build a Smart Bin keyed on the MediaPool Properties > Timeline fields and set it to “is Enabled/Disabled.” The crossed-out eye at the lower left of the thumbnail marks this Timeline as disabled.

### Adding Media Pool Timelines Directly to the Render Queue

A timeline can be dropped straight onto the Deliver page’s Render Queue: right-click the timeline, hover over Add to Render Queue Using, and pick one of the listed presets. Your own presets join that list whenever you save a fresh custom preset over on the Deliver page. At that point you’re asked where the file should be rendered. The timeline then lands in the Deliver page’s Render Queue, though nothing renders until the Render All button is clicked.

Choosing a Preset under the “Add to Render Queue Using” menu option pushes the timeline straight onto the Render Queue

### Import and Export DaVinci Resolve Timelines (.drt)

Individual timelines can move from one DaVinci Resolve project into another already-existing DaVinci Resolve project, so you can hand timelines off quickly between projects and workstations without generating extra imported project files. Only the timeline plus its linked clip information travels; the actual media files stay behind. Sending one timeline out of the Media Pool goes like this: 1 Select your chosen timeline there. 2 Choose File > Export > Export AAF, XML, DRT (Shift-Command-O). 3 In the file system dialog, set the format popup to “DaVinci Resolve Timeline Files (\*.drt).” 4 Decide where the DaVinci Resolve Timeline file (.drt) should be saved in the file system dialog, then click Save.

Sending several timelines out of the Media Pool goes like this: 1 Highlight several timelines within the Media Pool. 2 Right-click any timeline and follow Timelines > Export > DaVinci Resolve Timeline Files. 3 Point your file browser at the folder where they should be saved. In contrast to single-timeline export, a batch export gives you no chance to rename the .drt files; each keeps whatever timeline name it carries in the Media Pool. Bringing a timeline back into the Media Pool runs as follows: 1 Pick the Media Pool bin that should hold the imported timeline. 2 Do one of the following:

- Choose File > Import Timeline > Import AAF, XML, DRT (Shift-Command-I), then pick a DaVinci Resolve Timeline file (.drt) in the file system dialog and click Open.
- Double click the .drt file in your file system.

The timeline shows up in the Media Pool together with every clip tied to it, media sync information included. To keep names unique, anything imported this way gets the word “import” added to its name. That imported timeline is conformed automatically against matching media already sitting in the Media Pool. If, however, the timeline traveled to a different computer, you might need to reimport or relink any missing or offline media to bring the imported timeline fully online. NOTE: This method handles just one timeline per import or export. For several timelines at once, turn to the Import/Export Bin function instead.

### Backing Up and Restoring Timelines

Inside the User Preferences, under its Project Save and Load panel, ticking the Timeline Backups checkbox lets DaVinci Resolve store several timeline backups at set intervals, following a scheme much like the GFS (grandfather-father-son) rotation. It works whether or not Live Save is active. To roll back to an earlier backup of a timeline, just right-click the timeline in the Media Pool, pick Restore Timeline Backup from the contextual menu, and select the backup you want from the list. Because backups are sorted by date and time, pinpointing the exact timeline to restore is easy. At certain points during editing it’s wise to lay down a backup by hand before you overhaul the rest of your timeline. The safest route is generally duplicating the timeline, though you may instead drop a manual backup point that gets recalled alongside your other timeline backups. Laying down a named backup point yourself takes either of these forms:

- Select File > Create Timeline Backup (Option-Command-S).
- Right-click your Media Pool timeline and pick Create Timeline Backup from the context menu.

Pulling back a timeline backup leaves your current timeline intact. Rather, the chosen backup arrives in the Media Pool as a new timeline carrying the suffix “Backup” on its name.

### Restoring a timeline backup in the Media Pool

A timeline backup is written only after a project has actually changed. Should DaVinci Resolve sit idle for a stretch — say while your smart watch nudges you to step outside and circle the block — no further project backups are written, which stops DaVinci Resolve from replacing valuable backups with pointless ones. Three of the fields govern how frequently a new backup is saved, and the fourth picks where those backups go. Both Project and Timeline backups obey these settings.

- Perform backups every X minutes: This first field sets the cadence for a new backup inside the most recent hour of work. The default cadence is every 10 minutes, which yields six backups across that hour. As soon as an hour of work elapses, an hourly backup is written and the per-minute ones start dropping off in first in, first out fashion. By default that leaves you holding only six backups at any moment, each covering the past hour’s work.
- Hourly backups for the past X hours: This second field sets how many hourly project backups to keep. By default two hourly backups are held for the current day. Beyond that figure, hourly backups start dropping off in first in, first out fashion.
- Daily backups for the past X days: This third field sets how many days’ worth of backups to keep. Whatever backup is saved last on a given day becomes that day’s daily backup, and by default only two days of daily backups are retained. Beyond that figure, daily backups start dropping off in first in, first out fashion. For a project spanning a longer period, feel free to bump this number up.
- Project backup location: Press the Browse button to point these backups at a chosen location. By default they go to a “Project Backup” directory on your scratch disk, but you may redirect them to a volume that suits your data backup methodology better. That folder holds both Project and Timeline backups.

### Restoring Deleted Timeline Backups

Via the Media Pool Options menu, choosing Deleted Timeline Backups lets you inspect removed timelines along with the backup files on hand for each one. From there you may flag backups for restoration or opt to wipe selected backups permanently.

### Timeline View Options

While you cut an edit, reshaping how the Timeline looks is frequently handy — resizing video or audio clips, deciding whether audio waveforms get drawn, and the like. The Timeline View Options dropdown sitting at the Timeline’s far left is where you apply such adjustments on the fly.

### The Timeline View Options dropdown

You have the following options:

- Timeline View Options: A trio of buttons toggles particular Timeline interface elements into or out of view, namely: Display Stacked Timelines: This option presents stacked timelines so several can be shown at once, one above another. Display Subtitle Tracks: Reveals or conceals the Timeline’s subtitle tracks region. Concealing subtitle tracks won’t switch off subtitle display; for that you must disable whichever subtitle track is currently shown. Display Audio Waveforms: Flips audio waveform viewing off or on. With Audio Waveform off, audio tracks shrink to their minimum.
- Thumbnail View Options: A trio of buttons sets the overall look of the video track. From left to right:

Filmstrip: Renders every clip as a run of frames spanning its length. How many frames appear hinges on the clip’s present zoom level in the timeline. Thumbnail: Renders every clip as a solid color, placing a thumbnail of the clip’s In point at its start and a thumbnail of the Out point at its end. Which thumbnails show depends on the clip’s current zoom level and track height in the timeline. When a clip lacks room for both, only the In point thumbnail shows. None: Renders every clip as a solid color across its length.

- Viewer Background: Four choices — Checkerboard, Black, Grey, or Alert Red — set the color used for the transparent background inside the Viewer.
- Fixed Playhead: This option switches between a fixed playhead, which holds the playhead anchored mid-timeline while the tracks slide beneath it, and Free Playhead, where the playhead runs along the timeline during playback.

With the Fixed Playhead option active, you’re free to position the Fixed Playhead wherever you like along the timeline instead of leaving it centered. Just rest the pointer on the playhead’s top within the Timeline Ruler, then drag toward whatever spot you prefer. Relocating the Fixed Playhead can help by widening the timeline working area available for clips ahead of or behind the current point.

- Audio View Options: A trio of buttons controls how audio waveforms appear in the Timeline whenever they’re shown.

Display Non-Rectified Waveform: Switches the waveform between rising from the bottom of the audio track and being centered with a mirror image of itself. Display Full Waveform: Removes the divider bar separating the waveform from each audio clip’s file name region, letting the waveform fill the entire audio bar in the Timeline. Display Waveform Border: Adds a dark outline around each waveform’s edges so they stand out more clearly.

- Video track height slider: Scales every video track together in one move, apart from the audio tracks.
- Audio track height slider: Scales every audio track together in one move, apart from the video tracks.

Beyond that, you can resize a single Timeline track on its own by dragging its top divider within the Track Header region. Edit page track heights operate independently of the Thumbnail and Waveform view choices set in the Timeline View options. In the past, certain Timeline viewing modes like Filmstrip or Thumbnail view carried minimum track height limits. These days track height is fully adjustable regardless of your chosen options, and shrinking one or more tracks beneath the filmstrip or thumbnail minimum quietly folds them into Simple view to keep things tidy.

Adjusting one timeline track’s size by dragging its upper border within the Track Header

### Modifying Timeline Tracks

As you prepare to cut clips into the Timeline, confirm you have enough tracks for the task. The procedures below walk through the various ways to add, remove, and reorder tracks while you work. Every one of these commands lives in the contextual menu that pops up when you right-click anywhere in the Timeline header area (that header is the strip on the left holding each track’s assorted buttons and controls). You may bind Keyboard Shortcuts to track header context menu actions — adding, deleting, moving, recoloring, and linking tracks among them. Track selection is possible from the Track index as well as the Edit and Fairlight timelines. As an illustration, you can bind a keyboard shortcut for adding a new Audio Track on the Edit page by going to Commands > Edit Timeline > Track Controls > Add Track > Audio inside the Keyboard Customization window. Methods for adding, deleting, and rearranging tracks:

- Adding a track to the Timeline: right-click a Track Timeline header and pick Add Track. A fresh video track lands directly above whichever track you right-clicked, while a fresh audio track lands directly below it. When the addition is an audio track, you get to pick the kind of channel mapping it uses.

Audio track channel mappings get fuller treatment in Chapter 45, “Working with Audio in the Edit Page.”
