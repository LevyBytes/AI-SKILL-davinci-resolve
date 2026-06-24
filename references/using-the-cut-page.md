# Using The Cut Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using the Cut Page

For fast editing, the Cut page gives you a tightly focused environment. It pays off whenever you have to rapidly cut a news segment, assemble an episode of web content, edit a straightforward program, try out several arrangements of a scene, or throw together a first assembly edit. The Cut page also makes a friendly first editing interface for newcomers, since it puts forward a pared-down toolset that's quick to pick up and easy to operate. Wherever you're coming from, the Cut page proves a worthwhile addition to how you edit in DaVinci Resolve.

### Overview of the Cut Page

Now that the Cut page exists, DaVinci Resolve carries two editing environments aimed at two distinct audiences. The Cut and Edit pages have plenty of panels in common, the Media Pool, the Timeline, and the Viewer among them, yet the controls the Cut page surfaces are built around speed, letting you cut professional programs faster than you ever could before.

### Overview of the Cut Page User Interface

By default the Cut page workspace is made up of the Media Pool, one Viewer, and the Timeline area. Those three regions let you import and organize clips, edit them, and even export the finished result, all without leaving the Cut page.

### The Cut page interface

### Customizing the UI

Across the top of the Cut page, a User Interface toolbar lets you show and hide individual panels as you see fit. You could, for instance, hide the Media Pool to free up more space for the Viewer. The Media Pool's default area can also host other browsers in its place, surfacing the Sync Bin, Transitions, Titles, or Effects Browser so you can drop those effects into your program on the Timeline. Over on the right end of the User Interface toolbar, you can run a Quick Export, blow the Viewer up to Full Screen, or open the Inspector. Down the left, individual tabs bring up the Media Pool, Sync Bin, Keyframe Editor, Transitions, Titles, and Effects browser.

Drag the vertical seam joining the Media Pool and Viewer left or right to resize them, which enlarges one panel as it shrinks its neighbor.

### The Viewer resize handle

### The Timeline resize handle

The Timeline area, too, can be resized by dragging the timeline handle (up at the Timeline's top-right corner)

up or down, which makes more or less room for the Timeline while also resizing the

Media Pool and Viewer areas.

### Choose Settings Before You Start

Right after you create a new project, its Timeline settings have to be defined; you can either pick from common presets or set up something fully custom.

### Timeline Resolution Quick Menu

Sitting at the Viewer's top-right, this drop-down menu lets you swiftly select the resolution you'd like to work at. A Custom option opens the Timeline Settings panel so you can set your own options.

For more information about the Timeline Settings, see Chapter 6, "Project Settings."

### The Project Settings quick menu

### The Media Pool

Every video clip, audio clip, graphic, and other piece of media you bring into your project lands in the Media Pool. You can set up bins to organize all that media, which makes locating what you want faster. Those bins open from the bin drop-down at the top-left corner. Each piece of media you import, be it video, audio, or graphics, shows up as its own clip and can be selected, scrubbed for a quick look, sorted into bins, opened into the Viewer for playback, or cut into a timeline with the edit buttons or by dragging and dropping.

### The Media Pool in Thumbnail view

View icons at the Media Pool's top-right let you look at your clips in various ways, according to what you're trying to do.

### The Viewing ModeFs buttons

Metadata view: A clip is shown on its own card carrying a scrubbable thumbnail plus basic clip metadata. The aim of this view is to give more metadata than a thumbnail view yet more focused detail than the List view. Thumbnail view: A scrubbable thumbnail stands in for each clip. Hover the playhead over a thumbnail and slide it left and right to watch the clip play; the I and O keys then mark the sections of a clip you intend to use. Click a thumbnail's lower-right corner to reveal that clip's metadata. Filmstrip view: A filmstrip of consecutive frames spanning the Media Pool's width stands in for each clip. Hover the playhead over the clip and slide it left and right to watch it play; again the I and O keys let you mark whichever clip sections you mean to use. List view: Each clip is an entry in a multi-column list displaying assorted metadata per clip. While in List view, click any column header to sort the contents by that column's data (click again to flip the sort between Ascending and Descending). Scroll right to expose more columns of information.

A Sort Media By drop-down menu lets you set which criterion governs the order clips appear in within the Media Pool. Among its choices you'll find Custom, Timecode, and Camera; also Date Time, Clip Name, and Bin; plus Scene Shot, Clip Color, and Date Modified; rounding out with Date Imported and Online Status. Sorting can go Ascending (bottom to top) or Descending (top to bottom). Finally, a search field lets you enter a term to track down one or more clips matching it. As you type, the Media Pool's contents narrow to just the clips fitting your criteria.

### The Sort Media By dropdown menu

### The Viewer

Clips from the Media Pool, or clips on the Timeline, are shown in the Viewer, which carries plenty of controls for governing what you see and how things play.

### The single Viewer in the Cut page

Four mode options are available in the Viewer. Which one is active can be both seen and changed via four buttons up in the Viewer's top-left corner.

### The Viewer modes buttons

Various actions enter the Different options automatically (left to right):

- Double-clicking any clip opens it into the Viewer as a Source Clip.
- A whole bin's worth of clips can be viewed via the Source Tape.
- Your edited program plays back in the Timeline.
- Every bit of your synced material shows together at once in the Multi Source viewer.

### Playing Clips and Navigating the Timeline

A handful of controls live along the bottom of the Viewer. With them you play through and otherwise move around clips and the Timeline in different ways. They're covered here from left to right.

### The toolbar at the bottom of the Viewer

- Tools button: Clicking the Tools button surfaces an assortment of controls: transform and crop, audio, speed effects, plus camera stabilization with lens correction, on top of dynamic zoom and compositing, each given fuller treatment later on.
- Voiceover: Reveals controls for recording voice over directly into the timeline.
- POI and Add POI: With these tools you select and adjust Points of Interest within Replay,

which has a manual of its own. For more on these tools, consult the "DaVinci Resolve Replay Editor Instruction Manual."

- Fast Review button: Made to help you get through a big pile of media in a hurry, clicking this button kicks off sped-up playback across the Source Tape or the Timeline, with the playback speed tied to how long each clip is. Long clips race by, while shorter ones play nearer to real time. That way you can take in a great deal of material very fast.
- Jog control: Click and drag inside the jog control to scrub through the Viewer's content with great precision.
- Transport controls: Clickable controls for driving playback of clips and the Timeline are formed by a bank of buttons: Previous Edit (Up Arrow) and Stop (Spacebar), then Play (Spacebar), followed by Next Edit (Down Arrow), with Loop Playback (Command-/) rounding it out. Each button has a keyboard shortcut to match.
- Mark In/Out: Clickable controls to set In and Out points respectively.
- Playhead timecode: A number field displays the timecode value at the playhead of a clip or the Timeline, giving you a numeric read on where you are.
- Skim Playhead: Footage can be skimmed in any viewer across the Media, Cut, Edit, Color, and Deliver pages by holding the C key and dragging the pointer back and forth within the viewer.

### Optimized UI Layouts for Vertical Editing

DaVinci Resolve supports optimized layouts for vertical timelines and projects. Load a vertical timeline or project and the UI shifts on its own to a layout tuned for vertical viewers across the Cut, Edit, and Color pages. Load a regular landscape timeline or project afterward and it flips back to the original layout automatically. Nothing further is required of you. This behavior is adjustable under Preferences > User > UI Settings > Use optimized UI layouts for vertical video. Clear that box to hold onto the normal horizontal layout even for vertical video timelines.

The UI now changes format to accommodate vertical video timelines automatically.

### Tools

Click the Tools button and out comes a toolbar for adding and editing clip effects right inside the Viewer, no Inspector needed. That toolbar puts forward an assortment of controls: transform plus crop, audio, speed effects, alongside camera stabilization with lens correction, and finally dynamic zoom plus compositing, all detailed further on. The Tools bar shown opened to the transform controls.

### Bypass Color Grades and Fusion

The Bypass Color Grades and Fusion Effects button/drop-down lets you switch off every grade and effect you may have laid down in the Color page and/or Fusion page so that playback runs better on low-power computers. Click the button (Shift-D) to turn grading and effects off or back on, or right-click it to reach a menu where you choose which things the button governs.

The Bypass Grades and Fusion button as it's right-clicked to surface its options

### Export The Current Frame from The Viewer

A still frame can now be exported from the Viewer across the Media, Cut, and Edit pages.

To Export a Still Frame from the Viewer: 1 With the Viewer's playback controls, navigate to whichever frame you'd like exported. 2 Pick File > Export > Current Frame as Still. 3 Within the File System viewer, type a name for the still frame. 4 Within the File System viewer, set the still frame's format. 5 Click the Export button.

### Audio Meter

Off to the right of the Viewer, an audio meter gives you a visual picture of the audio levels playing in the current clip or on the Timeline as you play through the Viewer, by way of animated vertical bars colored to show how loud things are:

- Green marks levels that are safe
- Yellow marks levels peaking right around the safe mark
- Red marks levels possibly peaking higher than they should,

at the risk of clipping the signal and bringing on distortion These animated bars act as a visual cue you can lean on to balance the volume of different clips pleasingly, and to keep from going past the loudest level you want and introducing clipping. Up top of the meters sits a speaker button for muting or unmuting audio playback.

### The Audio Meter showing an audio signal

### The Timeline

The term "timeline" covers two things: an edited sequence of clips, which forms a program kept in the Media Pool, and the region of the Cut page interface where you open that sequence of clips to view its contents, play it back, and edit it.

Timelines are built and held in the Media Pool right alongside your other clips. Each timeline, though, is put together and edited in what people sometimes call the Timeline Editor. The various pages of DaVinci Resolve present your timeline differently to suit each page's particular needs, with their focus shifting variously across editing, grading, compositing, and audio.

Yet while the Timeline Editor's interface shifts from page to page, what's actually in the Timeline stays the same, because every page's Timeline Editor is really displaying the very same Timeline you have open. So an advanced user can use each page of DaVinci to do different things to one Timeline, with only the interface shifting to enable different functions on different pages.

For the Cut page user, the Timeline splits into an Upper Timeline up top and a bigger, more

detailed Timeline Editor down below showing a zoomed-in slice of the Timeline around the playhead. Together,

these two views of your edited sequence let you move through your

whole project and cut in fine detail.

The Cut page Timeline, made up of the Upper Timeline together with the zoomed-in Lower Timeline

### Upper Timeline

Across the full width of your computer's display, the Upper Timeline always shows the whole program. Its playhead always runs free, so you can easily scroll around the entire program by dragging the pointer within the Timeline Ruler up top. It also doubles as a visual cue for tracking where you sit in your program while editing inside the zoomed-in Lower Timeline below. Small as the Upper Timeline is, you can still edit there, with most of the editing and trimming functions found in the Lower Timeline available in it too. Most intriguingly, you can also drag clips from one stretch of your program in the Lower Timeline over to another stretch in the Upper Timeline, and the reverse as well. Right-clicking a clip in the Upper Timeline brings up the same context menu as right-clicking one in the Cut page's main timeline, so you can carry out the same operations. A row of small numbers down the left side of the Upper Timeline lets you click a number to set the currently selected track; that pick is mirrored on the zoomed-in timeline below. Which track is selected affects where incoming clips drop in during editing, among other things.

### Lower Timeline

The zoomed-in Lower Timeline (often called simply "the Timeline") gives you a close-up of the part of the open timeline immediately around the playhead. Its zoom level is fixed and can't be changed. Detailed editing is what the zoomed-in lower timeline is for, though you can drag clips back and forth between the Timeline and Upper Timeline to swiftly reorder them across your whole program. Several editing functions sit in the Toolbar, gathered into Action and Option menus. You reach these functions by clicking the right icon and choosing a function from the drop-down menu. These tools get full coverage throughout the Cut section of the manual.

The Toolbar icons, left to right: Timeline Options, Timeline Actions, Edit Actions

### Timeline Options

The tools beneath this icon concern how the clips and timeline are shown, plus certain modes and tools applying to the whole timeline.

### All of the Timeline Options functions

- Ripple On: Flips ripple editing behavior on track V1.
- Snap: Switches playhead snapping behavior on or off.
- Trim to Audio: Brings up an expanded audio view on the timeline as you trim a clip.
- Trim with Safe Edit: Flips the Safe Edit function, which stops you from inadvertently overwriting neighboring clips during a trim.
- Display Clip Names: Switches the clip's name on the timeline clip on or off.
- Display Clip Status: Switches on or off the status icons for assorted operations on the timeline clip.
- Display Speed Keyframes: Switches the Speed Keyframes on or off for a clip carrying speed changes.
- Viewer Background: Sets how the empty regions of the Viewer background appear, whether Checkerboard, Black, Gray, or Alert Red.
- Set Default Transition: Brings up the Set Default Transition window, where you pick the default transition's type, duration, and alignment.
- Edit Using (Audio Track): Lets you settle on either every audio track or particular audio pairs to

edit with on the Cut page.

- Minimize Subtitle Track: Cuts down the subtitle tracks' vertical height so there's extra room in

the timeline.

- Fixed Playhead: Switches the fixed playhead on or off. On holds the playhead still as the timeline slides beneath it; off sends the playhead traveling along the timeline.
- Boring Detector: Activates the Boring Detector.

### Timeline Actions

The tools beneath this icon mostly serve to add fresh items to the Timeline or make changes to it.

### All of the Timeline Actions functions

- Create Subtitles from Audio: Builds subtitles automatically for every line of dialog on the timeline.
- Detect Scene Cuts: Runs a Detect Scene Cuts operation that breaks one long clip of a finished program back into separate clips.
- Audio Assistant: Leans on AI to mix your timeline's audio automatically against common deliverable requirements.
- Voice Convert: Leans on AI so you can swap the speaking voice from one person for another.
- Add Video Track: Puts a video track onto the timeline.
- Add Audio Track: Puts an audio track onto the timeline.
- Add Subtitle Track: Puts a Subtitle Track onto the timeline.
- Split Clips: Cuts the current clip into two at the playhead position.
- Join Match Edit Clips: Reunites two continuous clips that were split apart.
- Add Marker: Drops a marker at the playhead position.
- Set Color and Add Marker: Drops a marker and brings up the Markers editor, letting you change the color, add comments, and so on.
- Clear Transition from All Edits: Strips every existing transition off the timeline.
- Add Dissolve to All Edits: Puts a Cross Dissolve on every edit point along the timeline.
- Add Transition to All Edits: Puts the last-used transition on every edit point along the timeline.

### Edit Actions

The tools beneath this icon serve to adjust clips on the Timeline.

### All of the Edit Actions functions

- Trim Start to Playhead: Removes the whole portion of the clip sitting left of the playhead.
- Trim End to Playhead: Removes the whole portion of the clip sitting right of the playhead.
- Resync Clip: Should a clip drift out of sync with the rest of the program, this operation resyncs it.

### Tracks

Multiple tracks divide up the Timeline, each one able to hold a sequence of clips so as to form a program. The main tracks, labeled by number, fold a clip's video and audio into one item on the Timeline for simplicity. Editing the In or Out point of such a clip edits its video and audio in tandem.

Tracks on the Cut Page Timeline. A subtitle track sits on Track ST1. Track V1 displays Video only clips as well as combined Video+Audio clips, shown enlarged. A standalone audio track sits on Track A4.

TIP: Over on the Edit page, Video+Audio clips appear as separated Video and Audio items on different tracks. Open the Fairlight page and audio shows up on tracks with lanes, each audio channel visible. This way each page hands you different sets of controls over what's in the Timeline, fitted to that page.

### Track Header Controls

The track controls, in their order, let you enlarge a track, lock it against edits, mute its audio, and turn its video on or off.

Controls for enlarging a track, locking it, muting its audio, and disabling its video The Importance of Track 1 Every track in the Cut page Timeline is built to carry particular parts of your program. Track 1 holds the program's main video+audio, often dubbed the "A-roll," since these are the chief shots that set the timing and pacing of the story you're telling. Add, delete, insert, trim, or otherwise reshuffle clips on Track 1 and the rest of the edited timeline ripples on its own to take in your change, with clips right of the altered spot sliding left to fill the gap left by a deleted or shortened clip, or sliding right to open room for an inserted or lengthened one.

### Tracks 2 and Above

Tracks 2 and up are meant for "B-roll," the extra footage you layer over other clips on Track 1 to show what someone in the Track 1 audio is talking about, or for superimpositions that composite two images together in inventive ways. Moving or resizing a clip on Track 2 and above shifts or resizes only that single clip; the Timeline's other clips stay put and no rippling happens when you do it. Where several video clips overlap one another across multiple tracks, the one on the highest track hides those beneath it, so only the topmost clips show during playback. That helps when you're experimenting with rearranging several clips in a busy scene. You might, say, be editing a scene where an interview clip rests on the bottom track and various b-roll clips are edited onto tracks above it, leaving you free to shuffle them around at will, while it stays easy to reveal the speaker on the bottom track by opening a gap in the superimposed b-roll.

### Editing a scene with multiple superimposed clips

That said, if you superimpose video-only or video+audio clips for compositing, the composite modes and the opacity slider in the Composite section of the Viewer Tools controls let you blend several images together in different ways for artistic effects.

(Left) Stacking the clips you intend to composite, (Right) Building compositing effects out of several superimposed clips When you need them, you can add further Video+Audio tracks, either by dragging a clip to the empty gray region of the Timeline above the existing tracks to spawn a new one automatically, by clicking the New Track button at the Timeline's top-left corner, or by right-clicking the timeline header area and picking "Add Video Track" from the contextual menu.

### Audio-Only Tracks

Audio-only clips such as music, narration, or sound effects can likewise be edited onto separate audio-only tracks below, which then get labeled A1, A2, A3, and so on. Drag an audio clip into the empty gray region of the Timeline beneath the existing tracks and an audio-only track is created automatically.

### Audio-only tracks in the Cut page Timeline

### Gaps

Since Track 1 is built to carry your program's principal clips, the Timeline ripples itself automatically to seal gaps that would otherwise open when you move or rearrange clips on Track 1, while superimposed clips on Tracks 2 and above shift to stay in sync with the clips they sit over. You can, however, move superimposed clips on Tracks 2 and above to put them wherever you like, and gaps stay open between several clips sharing one superimposed track, letting them be edited at particular spots.

### Timeline Controls

Up in the Timeline's top-left corner, the Timeline controls let you toggle Rippling on Track 1, enter Dynamic Trim mode, Split a clip where the playhead sits, make Markers, and bring up the Keyframe Editor.

### The Cut page Timeline controls

### Audio Mixer

A full Audio Mixer can be shown on the Cut page, reaching every track and bus of your mix, plus shortcuts to any audio Track FX, Dynamics, and Equalizer tools. To turn on the Audio Mixer, click the Mixer tab up top of the Cut page.

The Audio Mixer in its expanded state, which keeps every audio track in view as you go on editing in the Cut page's Upper Timeline.

### Audio Mixer Controls

The channel strip of each track carries these controls:

- Track Number: Shown here is the number of the timeline audio track that each channel strip maps to.
- Track Effects: To open one of the track effects sitting above the fader controls, double-click it.

FX: Opens the Track Effects controls in the Inspector.

EQ: Opens the Track Equalizer.

DY: Opens the Track Dynamics.
