# Editing Basics In The Fairlight Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Editing Basics in the Fairlight Page

The Fairlight page serves to polish audio first laid out on the Edit page, and it equally lets you record and build audio programs entirely from nothing. Since audio clips carry traits that video clips lack, working with sound involves extra steps you won’t find on the Edit page. Throughout this chapter you’ll learn the core moves for cutting audio the Fairlight way.

### Compatible Audio Formats

On the format front, DaVinci Resolve handles WAVE, Broadcast WAVE, and AIFF; it reads MP3, AAC (M4A), and CAF (macOS only); and it accepts both MTS and QuickTime containers carrying the AC3 audio format, along with Enhanced AC-3 (macOS and Windows only). On the sample-rate side, DaVinci Resolve works with audio at 32, 44.1, 48, 88.2, 96, and 192 kHz. Anyone on Linux gains the extra capacity to encode and decode MP3 files within Fairlight. With DaVinci Resolve 17 comes the creation and handling of Dolby Atmos ADM files plus a way to export Dolby Atmos masters as IMF deliverables. IMF (Interoperable Master Format) refers to a SMPTE standard describing one master file format that bundles every piece of media and metadata required to deliver the result.

### ADM Import

Bringing an ADM file into a project loads the Bed mix or mixes plus any linked Object tracks into a timeline. Each lands on the track type that matches the audio files baked into the ADM. So if a Bed file happens to be 7.1.2, that file opens on import into a 7.1.2 track within Fairlight. Object files turn into their own separate Fairlight tracks, holding all of their panning data.

NOTE: Pulling a Dolby Atmos file in from the Media Pool renders it dynamically to your chosen output format right on the Timeline by way of the Dolby Renderer. Fairlight, though, can take in the complete Atmos file along with its beds and objects when you import from the Fairlight menu instead - Fairlight > Immersive > Audio > Import Master File. Importing through that route builds a timeline where the file’s entire Atmos program and dynamic metadata are correctly mapped and routed.

### Editing Audio Clips Into the Timeline

A full audio editing environment lives on the Fairlight page, where you can either record and build clips from nothing or refine tracks packed with audio clips assembled in various ways. Depending on the kind of work at hand, there are four routes for getting media onto the Timeline of the Fairlight page:

- Recording fresh audio into one or several tracks,.

### For more information, see Chapter 173, “Recording.”

- By dragging fresh audio clips out of the Media Pool and dropping them onto the Fairlight timeline
- By cutting audio clips into audio tracks over on the Edit page
- By importing a project that already holds audio clips
- By auditioning and approving sound effects out of the Sound Library No matter how audio clips end up on your timeline, the remainder of this chapter walks through the countless ways you can edit and sweeten what’s there.

### Overwriting Vs. Layering Clips That Overlap

As you place clips on the Timeline, the outcome of dropping one that overlaps a clip already sitting in your target track hinges on the Timeline > Layered Audio Editing setting. Out of the box, with Layered Audio Editing switched off, laying one audio clip over another causes the incoming clip to non-destructively erase the overlapping portion of the clip beneath it from the Timeline. Flip Layered Audio Editing on, however, and incoming clips stop overwriting the clips they overlap; instead they stack within the track, so the arriving audio clip wins out over what sat there before, yet the overlapping audio segments already on the Timeline survive — something you can view by selecting View > Show Audio Track Layers. That gives you the choice, as the job demands, of either overwriting clips you edited earlier or layering the newly edited ones, whether or not Audio Track Layers happen to be on screen. Audio layering is available on the Edit page and the Fairlight page alike. The topic of audio layering gets fuller treatment in a later section of this chapter.

### Choosing Parts of Clips to Edit in the Media Pool

Sitting atop the Media Pool is a preview player, a spot where you can open chosen source clips from the Media Pool, play them back, drop marks to log them, and set In and Out points before drag-and-dropping them onto the Timeline. In practice the Media Pool Preview Player stands in as a Source monitor for editing on the Fairlight page.

### The preview player in the Media Pool

- A range of viewing controls fills the title bar across the top. Up at the left, a dropdown menu lets you pick a zoom level for the audio waveform on display. Just right of it, a Timecode window reports either the clip’s length or the length bracketed by In and Out points. Continuing right, a real-time performance indicator reflects how playback is performing. Dead center sits the title of the clip you’ve currently selected, and a dropdown to its right surfaces the last 10 clips you browsed. Over at the far left, a Timecode field reports where the playhead currently rests (a right-click here brings up a contextual menu offering ways to swap the displayed timecode and to copy and paste timecode).
- The middle of the Media Pool Preview Player displays the waveforms for every channel of the selected clip, drawn at whichever zoom level you’ve chosen.
- Down at the bottom, the transport controls comprise a jog bar for scrubbing, Stop, Play, and Loop buttons, along with In and Out buttons.

### Dragging Audio Clips Into the Timeline

With the Media Pool open on the Fairlight page, you can cut whole audio clips onto the Timeline by dragging single clips and dropping them on whichever audio track should hold them. Any clip can go onto any track, no matter whether the clip’s channels line up with the track’s channel mapping. That said, dropping a clip carrying more channels than the track supports (say, a stereo clip onto a mono track) outputs only the channels the track can handle and mutes every other channel in that clip. Should that occur, you can always re-map the audio track by right-clicking its track header and selecting a fresh mapping from the Change Track Type To submenu.

TIP: Dropping one or more clips into the open space below the Timeline’s existing audio tracks spawns new tracks, and each one is mapped automatically to as many channels as the audio clip being edited calls for. With Ambisonics files, dragging a clip to the timeline — or making a new timeline that references a clip — produces a track of the right type, matched to the file’s Ambisonic order and channels. When you intend to drag several clips out of the Media Pool and edit them onto the Timeline together, a little prep usually pays off to ensure they land in the proper order. Dragging several clips onto the Timeline as one unbroken run of edited clips: 1 Adjust the sort order in the Media Pool’s browser area so the clips fall into the sequence you want them shown. Thumbnail view offers the Sort Order menu, whereas List view lets you click any metadata column header to sort by that column’s contents.

Reordering Media Pool clips by way of the Sort Order menu 2 Rely on the Media Pool thumbnails, the Filmstrip in Media Pool List view, or the Source Viewer to set In and Out points that mark which portion of each clip should go onto the Timeline.

3 Choose the Media Pool clips bound for the Timeline by dragging a bounding box, Command-dragging several bounding boxes across different groups of clips, Shift-clicking a run of clips, or Command-clicking separate non-adjacent clips. 4 Drag any of those chosen clips to the spot you want in the Timeline to carry out an overwrite edit. Whatever clips you drag overwrite any other clips they land on top of in the Timeline. When several clips come from the Media Pool, they edit in the same sequence as their Media Pool sort order, each honoring its own In and Out points. You can also cut audio clips onto the Timeline so that every clip’s timecode aligns with the Timeline Ruler. That comes in handy when you’re arranging multiple source audio recordings you want synced together across several tracks. Dragging several clips to edit them into a track at their timecode positions: 1 Choose the Media Pool clips bound for the Timeline by dragging a bounding box, Command-dragging several bounding boxes across different groups of clips, Shift-clicking a run of clips, or Command-clicking separate non-adjacent clips. 2 Keep Command-Shift held and drag the chosen clips into the track that should hold them to carry out an overwrite edit.

A series of audio clips edited into the Timeline by timecode position Every clip placed into that track lands at the timecode position carried in its own embedded timecode. So if you had been recording time-of-day timecode, each clip turns up on the Timeline at the moment it was captured. A batch of clips taped between hours 10 and 13 will spread out across hours 10-13 of your timeline. Two or more audio clips can likewise be edited onto the Timeline as a stack, setting you up to layer several sound effects for sound design work. Dragging several clips to edit them into a track as a parallel stack: 1 Choose the Media Pool clips bound for the Timeline by dragging a bounding box, Command-dragging several bounding boxes across different groups of clips, Shift-clicking a run of clips, or Command-clicking separate non-adjacent clips. 2 Command-drag the chosen clips into a track of the Timeline. The first of the chosen clips drops into the track you dragged onto, while the rest land either in audio tracks below that first one or, when no audio tracks are free, in newly created audio tracks made to hold them. Everything you’ve edited shows up as a parallel stack, spread across separate tracks one above another.

### Moving Audio Clips to Embedded Timecode Position

Every clip carries a timecode tucked into its metadata. Using that metadata, you’re given ways to drop clips onto the Timeline either from the Media Pool or within the Timeline itself. A right-click on a clip in the Timeline offers Move to Embedded Start Timecode. Clicking it spots the clip onto a chosen track of the Timeline at that timecode. Keep in mind both the embedded audio timecode and the Timeline’s own timecode. Unless the two overlap, the function won’t do anything. As an example, a clip whose embedded timecode reads 00:00:00:00 could prove hard to locate on a Timeline beginning at 00:59:58:00. If you’ve spotted a clip with these tools yet still can’t find it, inspect the embedded timecode in the Inspector’s Metadata panel together with the Timeline’s timecode.

A right-click on a clip in a Timeline surfaces the Move to Embedded Start Timecode option.

A right-click on a clip in the Media Pool surfaces the Insert Selected Clips to Timeline option.

When you right-click a clip in the Media Pool, one option is Insert Selected Clips to Timeline Using Timecode. Choosing it spots the clip onto a chosen Timeline track at the embedded timecode.

NOTE: A clip’s embedded timecode is shown in the Inspector’s File tab beneath timecode.

The Timecode metadata lives within the Inspector window on the File tab.

Clip Attributes now lets you hand channels out across different tracks carrying different channel assignments

### Support for Mixed Audio Track Formats from Source Clips

Media holding several audio tracks whose embedded channels follow different formats is supported by DaVinci Resolve. Take a clip carrying one stereo track, one 5.1 surround track, and six mono tracks: every one of them can be set up correctly in the Audio panel of Clip Attributes once that clip is imported. The Audio panel of Clip Attributes governs which format (Mono, Stereo, 5.1, 7.1, Adaptive) the channels inside a given audio track are configured as. As a result, you can build clips with multiple tracks, each running a different audio format and a different mix of channels — handy when preparing imported audio mix files you intend to output while mastering a program.

### Making Audio Clip Selections in the Timeline

Almost every editing action covered in this chapter and elsewhere asks you to make a selection that pins down which clips get affected. Three editing modes on the toolbar hand you different approaches to selecting clips, shaped by your goal and your working style. Reading left to right, they are the Pointer mode, the Range mode, and the Focus mode. The mode you pick dictates how clips and clip segments get selected on the Timeline ahead of every sort of editorial action.

The Pointer, Range, and Focus modes seen in the toolbar

### Fairlight Edit Mode Remains Between Application Restarts

Across restarts, Fairlight holds on to whichever Edit Mode the project was saved in. The edit mode you had active before quitting the application is the one that greets you on reopening.

### Why Are There Three Edit Modes?

Although the Pointer and Range modes work with the pointer too, their real purpose is to drive automatic selections keyed to where the playhead sits. That happens as you steer Timeline transport with the Fairlight Editing console, the Fairlight Desktop Console, or keyboard shortcuts while particular tracks are selected to permit selection and editing on them. Focus mode, by contrast, is built for quick selections drawn with the pointer through a mouse, trackpad, or pen and tablet, paired with an assortment of commands for stretching and editing selections fired off by keyboard shortcuts. For anyone cutting with a keyboard and mouse, this mode aims to keep you fast by switching on a range of selection behaviors tied to where on a clip you click.

### Selecting Tracks

Grasping clip selection means first grasping track selection. On the Fairlight page, the Timeline lets you select whole tracks so that clips crossing the playhead on those tracks get picked automatically through keyboard shortcuts, the Fairlight Desktop Console, or the Fairlight Editing panel while in Pointer and Range modes (both covered in sections ahead). Suppose you select tracks A2, A3, and A4: nudging the playhead in Pointer mode so it crosses two clips on those tracks selects them on its own, leaving them ready for whatever you want to do to both. As a sampling, you might now split the two at the playhead, apply Cut Head or Tail relative to it, Delete the pair, or Copy them to paste somewhere else. On top of that, clicking or dragging on one or more clips with the pointer will sometimes select those clips together with the tracks beneath them. Selecting clips via Focus mode, for one, also picks the tracks those clips live on.

Command-clicking several track headers selects those tracks When you select tracks by hand with the pointer, several approaches are open to you. Ways to select and deselect tracks on the Fairlight page Timeline:

- To select one track: Click somewhere in the header background, or hit that header’s track number (steer clear of a button). Under Range mode you may also click any empty spot on the track itself.
- To deselect one track: Click somewhere in the header background of an already-selected track, or hit its track number (not a button). Under Range mode you may also click any empty spot on the track itself. With several tracks selected, Command-clicking one peels just that track out of the selection.
- To select several tracks: Command-click in the track header background of each track you want. Under Range mode you may also Command-click any empty spot on the tracks themselves. A Command-click on a track that’s already selected deselects it.
- To select several adjacent tracks: Click anywhere in the background or on a track header’s track number, then drag a bounding box upward or downward across the other tracks you want. Under Range mode you may also drag a bounding box over any part of the tracks themselves, which simultaneously sets a range you wish to work within.
- To shift the selection up or down the tracks: Press Control-Option-Up Arrow or Down Arrow to carry the selection state to the next track up (Control-Option-Up Arrow) or down (ControlOption-Down Arrow). When several tracks are selected, the whole multi-selection moves as a block; selecting tracks A2 and A3 and then pressing Control-Option-Down Arrow, for instance, leaves tracks A3 and A4 selected.

### Using Pointer Mode

Pointer mode leans on where the playhead sits to make automatic selections whenever you select clips on chosen tracks through the Fairlight Editing console or keyboard shortcuts. You can equally pair this mode with the pointer and keyboard shortcuts for a different selection style. The chief aim of Pointer mode is to support quick editing of entire clips.

- When no tracks are selected: Clips the playhead crosses stay unselected. With the pointer you can grab a clip or several through a click, a Command-click, or a dragged bounding box. Clips chosen this way glow orange. Working like this mirrors how you select clips on the Edit page Timeline.
- When tracks are selected: Every clip the playhead crosses on the chosen tracks is highlighted automatically, though no In and Out points get set. Clips on deselected tracks are passed over. Grabbing a clip or several with the pointer (via a Command-click or a dragged bounding box) yields an orange-highlighted selection.
- When you set In and Out points: Certain functions act on ranges of clips lying between the In and Out points on chosen tracks. Clips on unselected tracks are passed over.

To switch on Pointer mode:

- Click the Selection tool (the arrow) on the toolbar.
- Choose Trim > Pointer mode.
- Press A.

To have the playhead position auto-select clips in Pointer mode: 1 Press A to drop into Pointer mode. 2 Select one or more tracks holding the clips you’re after. 3 Move the playhead so it crosses those clips. Each clip the playhead crosses on the Timeline’s chosen tracks gets selected automatically in full. The automatic selections glow brighter to mark them as selected. Crossed clips on tracks that aren’t selected stay unselected.

In Pointer mode, clips the playhead crosses get picked on their own and glow with orange highlights

Ways to select clips with the pointer:

- Click any clip and it’s selected.

### Click a clip to select it

- Command-click several clips to grab them all in one go.

Command-clicking several clips picks those clips even when other clips sit between them

- Click anywhere in the Timeline background and drag a bounding box across several clips.

Dragging a bounding box across several clips selects every one of them

### Using Range Mode

Range mode likewise draws on where the playhead sits to select a partial span of clips on the Timeline when you work through the Fairlight Editing console or keyboard shortcuts. This mode can also team up with the pointer and keyboard shortcuts to make partial clip selections.

- When no tracks are selected: Clips the playhead crosses stay unselected. With the pointer you can click a clip to select all of it plus the track beneath it. You can also drag the pointer across one or more clips to grab a partial span ahead of various editing actions. Each time you select with the pointer, Timeline In and Out points snap to the edges of that selection.
- When tracks are selected: The chosen tracks brighten on the Timeline, and any clip the playhead crosses on a chosen track lights up brighter automatically. Clips on deselected tracks are passed over. Dragging a crosshairs across one or more clips with the pointer

overrides every automatic selection and grabs the regions of the clips you drag across, plus the tracks they belong to.

- When you set In and Out points: On every chosen track, the partial regions of clips sitting between the In and Out points brighten. Clips on unselected tracks are passed over. With In and Out points in place, the playhead stops making automatic selections; in this mode you must lay down new In and Out points to alter the selection. To switch on Range mode:
- Click the Range Selection tool (the crosshairs) on the toolbar.
- Choose Trim > Range mode.
- Press R.

To have the playhead position auto-select clips in Range mode: 1 Press R to drop into Range mode. 2 Select whichever tracks carry the clips you’re after. 3 Move the playhead so it crosses those clips. Every clip the playhead crosses, on the tracks you chose, marks out a selected span running from the start of the first selected clip to the end of the last.

In Range mode, a clip the playhead crosses on a chosen track is picked without any prompting To build your own clip ranges with In and Out points on the Timeline: 1 Press R to drop into Range mode. 2 Select whichever tracks carry the clips you’re after. 3 Move the playhead and tap the I (Mark In) and O (Mark Out) keys to mark out a range on the Timeline.

Each clip segment that lands inside the span of your In and Out points on the chosen tracks gets selected.

Range mode picking out clip segments across chosen tracks by way of In and Out points Ways to select clips in Range mode by clicking and dragging:

- To grab one clip: Click any clip to select both it and its track, and to mark out a Timeline range equal to that clip’s length.

A click grabs one clip together with the track beneath it

- To grab several clips: Command-clicking several clips to take them all at once marks out a Timeline range covering the combined overlapping length of every clip in the selection, from the start of the first selected clip to the end of the last.

### Range selection by Command-clicking multiple clips

- To drag out a range inside one clip: With the Range Selection tool active, drag anywhere across a clip so the bounding box covers whatever segment of that clip (or of one or more clips) you want, selecting both that clip segment and the track it sits on. It’s a handy way to grab part of a recording you mean to move or delete.

Ranged selection within a clip using a bounding box

- To drag out a range across several clips: Click and drag a bounding box across whatever segment of one or more clips you want, selecting both those clip segments and their tracks. Or, Command-click and drag anywhere across any clip so the bounding box spans whatever region of clips and tracks suits you.

Ranged selection across multiple clips using a bounding box Under Range mode, each selection you make refreshes the In and Out point fields with the range you’ve built.

The range fields displaying which In and Out point values pin down the present range Those ranges can be wiped out when needed. Ways to clear In and Out points and so drop the current range:

- Press Option-I to wipe the current In point.
- Press Option-O to wipe the current Out point.
- Press Option-X to wipe both the In and Out points.

### Using Focus Mode
