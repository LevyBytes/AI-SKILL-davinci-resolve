# Using The Fairlight Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using the Fairlight Page

The fully rebuilt Fairlight Audio Core engine can play back as many as 2,000 tracks at once, and it leans on smart load balancing to support the largest possible number of plugins. That higher track ceiling answers what both clients and immersive formats like Dolby Atmos demand. Big studio features and episodic television lean on large track counts so they can hold elaborate mixes and turn out several deliverables. Immersive formats such as Dolby Atmos push those counts even higher, since deliverables span anywhere from 7.1 all the way to 22.2. The pages ahead walk through the fundamental interface controls on the Fairlight page — what each one is, where to find it, and its purpose — so you gain a broad sense of how this combined audio workspace operates.

### The Fairlight Page User Interface

When run on a single display, the Fairlight page gives you a workspace tuned for working on audio tracks. A larger mixer plus dedicated monitoring controls let you cut and shape your audio media with ease, while you check and tweak program levels to land a clean, well-balanced mix.

### The Fairlight page

### The Interface Toolbar

A toolbar sits across the top of the Fairlight page, holding buttons that reveal or conceal the various sections of the interface. Reading from the left edge toward the right, those buttons are:

### The Interface toolbar

Media Pool: Reveals or conceals the Media Pool, the source you draw from to cut audio clips into the Fairlight page Timeline. Effects: Brings up the Audio FX panel within the Effects Library, where you can drop Fairlight FX, or AU or VST audio effects, onto clips or tracks in the Timeline. Index: Toggles the Index together with its Edit Index, Tracks, and Markers panels. Edit Index: Lists every edit event across the visible tracks of the Timeline. Tracks: Gives you control over which Timeline tracks are shown or hidden so you can focus on the ones in play. Markers: Surfaces all of the markers in the Timeline plus the data tied to each one. Scan through every marker together to track down the detail you want fast.

Groups: Toggling this button reveals or hides the Groups list, which you reach for when several tracks need mix changes applied together. The list stays put even after you dismiss the Track Index or switch to a different Index tab. To dig deeper into Track Groups, refer to Chapter 179, “Track Groups.” Sound Library: Toggles the Sound Library panel. Search and filter fields help you pinpoint the sounds you need, and a playback window lets you preview them before cutting them into the Timeline. ADR: Toggles the ADR panel, whose List, Record, and Setup tabbed controls drive how the ADR panel behaves. Mixer: Reveals or hides the Mixer along the right of the Timeline, the place where you tune the effects and levels of every audio track to build your mix. Meters: Toggles the Monitoring audio meters together with the Fairlight viewer across the top of the page. Metadata: Reveals or hides the clip Metadata panel.

Inspector: Reveals or hides the Inspector, the place where individual clip attributes are edited.

### The Audio Timeline

At the core of the Fairlight page sits the Audio Timeline, which lays out the audio channels and tracks belonging to whichever Timeline is active. The number of lanes a given audio track holds depends on its Track Type, or format. Clips you cut into the Timeline show up inside each track, and any multichannel content in a clip fills as many lanes as the track type provides (say, 2 channel stereo, or 6 channels for 5.1). A header packed with controls runs along the left edge of every track. These multi-lane tracks look different here than on the Edit page, which is geared toward simple audio-for-video work and renders multichannel files as composite waveforms on single-lane tracks. There is no way to close the Fairlight page Timeline.

### The Audio page Timeline

### Controls in the Audio Timeline

These are the controls available in the Audio Timeline.

- Timecode fields and Range buttons: These readouts show the Playhead's present timecode along the Timeline Ruler, where the Range In and Range Out points sit, and how long the Range runs. Pressing the Range In and Range Out buttons — positioned to the left of each timecode field — assigns those values and pins their spots on the Timeline Ruler.

Timecode fields and Range buttons in the Fairlight page

- Transport controls: This bar at the top of the Timeline holds transport controls specific to audio, which aren't quite the same as the ones on the Media, Edit, Color, and Deliver pages because recording is part of the mix here. Among them are Fast Reverse, Fast Forward, Play Forward, Stop, Record, Loop, plus the icons that toggle Automation and show the Automation toolbar.

### Fairlight page transport controls

- Toggle Automation button: Pressing this turns on automation recording and playback and inserts an Automation Follows Edit button into the Toolbar, sitting between the Flags and Markers buttons. To read more about the Toolbar, look ahead to “Toolbar,” which appears later in this chapter.
- Automation toolbar: Pressing this reveals a second toolbar that carries every control required to record mixer automation.

To go further on Automation, consult Chapter 178, “Mix Automation.”

### Fairlight page automation toolbar

- Monitoring controls: Three monitoring controls sit at the far right end of the transport controls and give you fast command of your mix's output level. A click on the Speaker icon toggles muting of the audio, and that icon glows red while the audio is silenced.

Sliding the horizontal control raises or lowers the output level by degrees, and the matching signal level appears in decibels as you drag. Pressing DIM briefly drops the output, which comes in handy when you want a short word with your client about sports or current events while still half-listening to the mix. Engaging the DIM function tints the slider yellow.

### The monitoring controls

- Timeline Ruler: The Timeline Ruler shows the program's timecode and, together with the playhead, marks the frame (or sample) you're currently on in the Timeline. A handle sits atop the playhead inside the Timeline Ruler, and you reposition the playhead by grabbing and dragging that handle.

Any Markers you place in the Timeline show up at their matching spots inside the Timeline Ruler as well.

- Playhead: Marks the frame and sample being played and gives you a visual cue of your spot as you play, shuttle, and jog across the Timeline. Meanwhile the big timecode readout in the Timeline's top-left corner also reports where the playhead is. That playhead position doubles as a reference point for editing tasks.
- Audio tracks: Multiple audio tracks are supported on the Fairlight page. A track can carry several lanes to fit the audio channels inside multi-channel clips, drawing on any of the supported mappings: stereo, then 5.1 and 7.1, along with Dolby Atmos, Ambisonics, or an Adaptive track of 1–24 channels. Clips you cut into the Timeline land inside the tracks, and the captured channels take up as many lanes as the clip offers.

To the left of every track sits a matching header region filled with various controls.

The Fairlight timeline splits into tracks and lanes; track A1 is mono and carries one lane for mono audio. Track A2 is stereo and carries two lanes for stereo audio.

### Track header

Controls in the track header let you toggle lock, toggle solo and mute, and record-arm the track. Beyond a level meter, the header carries informational readouts listing the track type, the track's number and name, its volume, and how many clips it holds.

The track header controls of the Fairlight page timeline

- Track color: Any track can be tagged with one of 16 colors, and that color also shows up on the Fairlight and Edit page Mixers, the Tracks Index, and the Audio Meters. To color a track, right-click its header and pick a color out of the Change Track Color submenu. The same color goes onto several tracks at once if you drag across neighboring headers, or Command-click headers that aren't adjacent, then choose a color from the Change Track Color submenu.
- Track number: Shows the number assigned to each track.
- Track name: Every track carries a name that initially matches its track number, like Track 1, Track 2.

That said, you can click any track's name and change it to anything you want. For instance, label each track by the kind of audio you're cutting onto it — Production, Ambience, SFX, or Music. Those same names label each track's channel in the Mixer, centered in each channel strip (with the channel strip's track number shown up top at the same time).

- Audio channel type indicator: Audio tracks also report the channel configuration in use, spelling out the channel count for mono, stereo, 5.1, 7.1, Atmos, adaptive, and the rest.
- Fader value: A readout reports the fader's present setting at the playhead's spot, in dB. It mirrors the track's fader level over on the Mixer panel. Drag the figure upward or downward and the fader tracks along with it.
- Lock Track button: A locked track won't let its clips be swapped, repositioned, or otherwise altered, though clips on locked tracks can still be graded over in the Color page. The lock appears shut while the track's contents are locked and appears open when they aren't.
- Arm button: Pressing this arms that track for recording.
- Solo button: Silences every track except the active one so you can isolate and listen to a single track quickly. Because this carries into rendering, soloing one or more tracks means the muted ones aren't output or rendered.
- Mute button: Briefly silences a track's audio so it isn't monitored or output. Since this carries into rendering, muting one or more tracks keeps them out of the rendered result.
- Audio meters: Every track carries audio meters in its header so you can watch levels as playback runs.
- Toolbar editing tools: The toolbar holds both modal buttons and command buttons to help you work through your projects. The section that follows covers them in greater depth.
- Vertical and horizontal scroll bars: When your project runs longer than the Timeline's current width, or when there are more audio tracks than its current height can show, these scroll bars let you drag your way around the program. Scrolling sideways carries the playhead along with the track waveforms, so for a moment it can slide out of sight; starting playback snaps it back into view. You can also scroll up and down with your mouse's scroll wheel (or other scroll control), and scroll sideways by holding the Command key while you do so.
- Individual Timeline track resizing: You can resize any one Timeline track on its own by right-clicking somewhere inside that track's header control region and picking a height out of the Lock Track Height To submenu in the contextual menu. The fixed sizes on offer are Micro, Mini, Medium, Large, Extra Large, and Custom. Once you set a fixed height, vertical zoom stops affecting that track until you switch its “Lock Track Height to” setting back to None. You can also select several tracks, or all of them, and set them to a single height; every selected track adopts that size until you change it again, whether globally or one at a time.

Resizing an individual audio timeline track using contextual menu options

### Zooming Audio Waveform Height

You're able to zoom the audio waveforms inside the clips of one or more tracks larger or smaller, making them taller or shorter, or send them back to their default sizes. None of this touches the actual audio levels of the clips in those tracks — it simply makes the waveforms easier to read. To resize waveform height with your scroll wheel: hold Command-Option down and roll the scroll wheel or control either way to resize every waveform across all tracks. There are menu commands too, reached at the top under View > Zoom Audio Waveform, for any Timeline track. Pick one track or several to resize their waveforms together. The menu offers three groups of commands:

- Reset
- Zoom Increase Height
- Zoom Decrease Height

Right-click any clip in the Timeline and you can open the Track Waveform Zoom submenu, which carries still more zoom choices.

### Smart Zoom Track Height

Select a track in the Timeline or Mixer and hit Command-Option-E, and Smart Zoom grows that track's height while centering your selection so it fills the entire visible region of the Timeline. When your edits are done, press Command-Option-E once more to leave Smart Zoom. Like the rest of DaVinci Resolve's keyboard shortcuts, Smart Zoom can be reassigned in the Keyboard Customization dialog. To learn more about Keyboard Customization, refer to Chapter 4, “System and User Preferences.”

### Standard Timeline view

### Smart Zoom Timeline view

### Audio Editing Modes

Two audio editing modes live on the Fairlight page: Overwrite Mode and Layered Audio Editing Mode.

### Overwrite Mode

True to the name, when part of a clip lands over another clip during an edit, the overlapped region of the lower clip is removed non-destructively to make room for the arriving clip. Should you move or delete that overlapping clip, the clip beneath it stays trimmed. Whatever this removed is still held in the original clip and can be brought back by trimming the head or tail (whichever side you affected). Overwrite is the mode set by default and suits most everyday editing best.

(Left) Overwrite edit showing original clips, (Right) Right hand clip dragged left

### Resulting overlap

### Layered Audio Editing

Layered Audio Editing is a dedicated mode that lets you stack several audio clips on the same track, where clips placed on the upper layers silence the overlapping parts of clips sitting on lower layers. With this enabled (Timeline > Layered Audio Editing), stacked audio clips behave much like stacked video clips set to 100% opacity, the upper clips hiding (or muting) whatever lies beneath. You can flip this on or off independently under the View menu > Show Audio Track Layers. The mode shines whenever you're stitching pieces of several takes together (“comping”) into one voiceover, vocal track, ADR, or dramatic read, since you decide which pieces to keep by where they stack in that track, all while the other takes stay safe underneath should you want them down the line. Bear in mind, though, that deleting any clip resting “above” another lets the lower layer “poke through.” That extra bookkeeping during editing is among the reasons Overwrite Editing mode is the default. TIP: You can also use Layered Audio Editing mode on audio tracks over in the Edit page.

Layered Audio Editing and Show Audio Track Layers enabled

Layered Audio Editing while Show Audio Track Layers is off — every layer collapses down into one combined view.

### Flatten Audio Layers

Once you've worked through Layered Audio Editing, building a “comp” (composite) of a performance is handy when you want one element that captures the finished result you're after. Timeline > Flatten Audio Track Layers lets you produce a single layer-free edit while keeping the clip boundaries intact. Picking this command slices across each layered clip at its in/out points and merges them down into one layer.

After choosing Flatten Audio Layers, audio layers showing (so blank space above) When you're heading out to an AAF, switch layered audio editing off, because only the lowest, first layer makes it into the export. If you'd been working with layered audio editing already, run Flatten Audio Layers first and then do your AAF export. Note too that with any layered crossfades, only the fades on the incoming clip survive.

### Switching Among Multiple Timelines

Like any other clip, timelines can be organized within the Media Pool. Use the steps below to open one or move between them. Every Timeline holds onto whatever view settings were last set inside it, track heights and zoom among them. To change timelines, do any of these:

- On the Edit, Cut, or Fairlight page Media Pool, double-click a timeline.
- On the Edit page Timeline Viewer, pick a timeline from the Timelines dropdown menu atop the viewer.
- On the Color page, pick a timeline from the Timelines drop-down menu atop the viewer.
- On the Fairlight page, pick a timeline from the Timelines dropdown menu sitting left of the transport controls.

### Toolbar

Some buttons on the Toolbar let you pick functional modes, while others fire off commands such as dropping markers and flags.

The toolbar icons on the Fairlight Page as they look while the transport bar shows the Automation button lit Timeline View Options dropdown menu: Holds an assortment of controls for tailoring how clips appear and for setting the Timeline's navigation and scrolling behavior. Grid View Options dropdown menu: Holds controls for tailoring the timeline grid, letting you show reference lines or snap clips to timecode or musical beat positions.

Pointer Mode: The standard mode, where you reposition and resize clips in the Timeline, roll edits, and handle other routine editing. Though it works with the pointer, it's built to let you auto-select clips at the playhead's spot on chosen tracks via keyboard shortcuts or the Fairlight Editing console. Range Mode: An editing mode for selecting partial stretches of one or more clips so you can edit just those portions. It's built to let you auto-select using In and Out points that mark regions on chosen tracks, by way of keyboard shortcuts or the Fairlight Editing console. Focus Mode: Within Focus mode you reach Multi Tool behavior that shifts with cursor placement: The Selection tool (I-beam): Shows up as you hover the cursor over the top portion of the waveform track “lane,” letting you select time ranges of clips or automation keyframe data (which depends on the track view). The Hand tool: Shows up as you hover the cursor over the bottom portion of the waveform lane, letting you click to pick a clip or clips, drag to move them, or run Cut, Copy, and Paste. This tool is on hand in the other modes too. The Trim tool (Up/Down arrows): Shows up as you bring the cursor near the clip gain line, letting you trim the automaton curve for clip gain or keyframe levels. While you trim an automation parameter, a tooltip reports the level plus the delta from its original value. Trim tool cursors for adjusting clip boundaries — to trim a clip's head or tail, or to do rolling trims — are likewise available. This tool is on hand in the other modes too. Pencil: A tool for drawing automation data with the pointer acting as a pencil. The Pencil tool turns up once automation is on. Razor (Scissors): Click to drop a cut into every clip on an unlocked track that crosses the playhead's spot. Snapping: Turns clip snapping on or off. While on, clip In and Out points, markers, and the playhead all snap together for reference as you edit. Linked Selection: With this enabled, choosing an edit point that has both video and audio parts selects both edit points, so applying a video transition to an edit also lays a crossfade onto the audio. It also lets you tie together otherwise unrelated audio clips so edit operations (trimming, for one) hit every linked clip together. Automation Follows Edit: Turns on or off the per-timeline mix automation being baked into clips, so that copying and pasting fresh instances of them in the Timeline keeps their levels, panning, filter settings, and so on. That's a real help when the same audio clips appear repeatedly across an edit. The Automation Follow Edit button shows up once automation is on, and it's on by default.

Flag Clip/Flag Colors dropdown menu: Flags mark clips and point out every clip that traces back to the same piece of media in the Media Pool. A clip can carry more than one flag. Pressing the Flag button drops a flag onto whatever clip is currently picked in the Timeline. Its dropdown menu lets you set the flag color and offers a way to clear every flag from the selected clip (when one is picked) or from the whole timeline (when none is). Add Marker/Marker Colors dropdown menu: Markers pinpoint particular frames within individual clips or timelines. With a clip picked in the timeline, pressing the Add Marker button drops a marker onto that clip at the playhead's spot in the Timeline. With no clips picked, pressing Add Marker drops a marker onto the timeline ruler at the playhead. Its dropdown menu lets you set marker color and offers a way to clear every marker from the selected clip (when one is picked) or from the whole timeline (when none is). Transient Detection: Switches on transient detection for all of a track's clips. Once on, a transient button shows up on tracks so the transients across that track's clips can be spotted and stepped through easily. With the Jump to Transient button on, the Up and Down arrow keys move between transients inside a clip. Vertical Slider: Lets you set the vertical zoom level of the tracks.

Horizontal Slider: Lets you set the horizontal zoom level of the Timeline.

### Timeline View Options

### Selecting the Audio Timeline View options

### Track Display Options

Video Tracks: This button shows or hides the video tracks in the current Timeline so you can keep them on hand for reference as you work. Full Waveforms: This button switches full waveforms on and off, optionally dropping the divider bar that separates the waveform from each audio clip's file-name area, so the waveform spreads across the full height of each audio bar in the Timeline. Waveform Borders: This button switches waveform outlines on and off, painting a dark edge around each waveform to make them stand out. Gain Line: This button switches the clip gain indicator line on and off. It's also reachable under the Fairlight Menu > Show Clip Gain Line.

### Navigation Options

Jump to Clip: When on, this steps you from one clip to the next with the Up or Down Arrow keys. Jump to Fade: When on, this steps you from one fade to the next with the Up or Down Arrow keys. Jump to Marker: When on, this steps you from one marker to the next with the Up or Down Arrow keys. Jump to Transient: When on, this steps you from one transient to the next with the Up or Down Arrow keys. For this to work, Transient Detection has to be switched on for both the Timeline and the track.

### Timeline Scrolling

Fixed Playhead: This button pins the playhead in place so that, during playback, the tracks slide past it while it stays put — handy when you're at the Fairlight control surface. Page Scrolling: This button has the playhead run to the end of the current Timeline view, then begin a fresh page once the Timeline reaches its end. How quickly the page flips depends on the Timeline's zoom level. No Scrolling: This button locks the Timeline so it won't follow the playhead at all. Depending on zoom, the playhead may end up playing off-screen with no timeline update

NOTE: You'll also find these options in the View menu > Timeline Scrolling.

### Scroller
