# Editing Basics (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Editing Basics

This chapter walks you through a host of the core techniques and commands you'll reach for as you start putting clips together in the Timeline. Covered here are drag-and-drop moves for kicking off a timeline assembly, assorted ways to select and deselect the clips you've edited as you prep for different jobs, holding sync between the audio and video halves of the clips you're editing, and clearing out clips and gaps you'd rather be rid of.

### Keyboard Shortcuts in This Chapter

Below is a list of keyboard shortcuts that touch on this chapter's topics and that you may find useful.

Key Shortcut V Shift-V U Option-U Option-Y Command-Option-Y Y Command-Y Up, Down Arrow Keys Delete Forward Delete Command-Backslash (\) N Command-Shift-L Option-1 through 8 Command-Option-1 thorugh 8 Option-Shift-1 through 8 Option-Shift-9 Option-Shift-F1 through F8 Option-Shift-F9 F9 F10 F11

### Function Select nearest edit to playhead

### Select clip intersecting playhead

### Select incoming, outgoing, or centered part of edit

Switch the selection across video+audio, video alone, and audio alone Across all tracks, grab clips ahead of the playhead Across all tracks, grab clips behind the playhead On just the current track, grab clips ahead of the playhead On just the current track, grab clips behind the playhead Shift the selection to the previous/next edit or clip Remove a clip and leave a gap behind (lift edit) Ripple delete; takes out a clip and pulls the rest of the timeline leftward to close the gap Insert edit; drops a cut into the clip(s) wherever the playhead sits Switch timeline snapping off and on Switch linked selection off and on Point the video destination control at that track number; press once more to enable/disable Point the audio destination control at that track number; press once more to enable/disable Flip the lock for one video track at a time Flip the lock for every video track Flip the lock for one audio track at a time Flip the lock for every audio track Insert Edit, carrying the picked clip(s) from the Media Pool or Source Viewer onto the Timeline Overwrite Edit, carrying the picked clip(s) from the Media Pool or Source Viewer onto the Timeline Replace Edit, carrying the first of the picked clip(s) from the Media Pool or Source Viewer onto the Timeline

### Key Shortcut F12

### Shift-F10 Shift-F11 Shift-F12 Undo Redo

Function Place On Top Edit, taking clips from the Media Pool or Source Viewer over to the Timeline Ripple Overwrite, taking clips from the Media Pool or Source Viewer over to the Timeline Fit to Fill, taking clips from the Media Pool or Source Viewer over to the Timeline Append To End Edit, taking clips from the Media Pool or Source Viewer over to the Timeline Command-Z Command-Shift-Z

### Drag and Drop Editing

For anyone who's already worked in other editing programs, this section's procedures will almost surely feel like old news, but if editing is new to you, here we cover the most elementary ways of cutting a string of clips into the Timeline to get you going. The plainest editing method of all is to pull clips out of the Media Pool and drop them into the Timeline. You can manage this with single clips or with selected batches of clips.

### Drag and Drop Editing of Individual Clips Into the Timeline

When you're editing just one clip at a time to build an edited sequence in a timeline, here's how it goes. 1 Should you need to edit particular stretches of the clips you're working with, you can first place In and Out points in source clips by one of these means: Placing In and Out points while skimming a thumbnail in the Metadata View: While you skim across a clip's thumbnail in the Viewer, press I and O to drop In and Out points around the part of that clip you'll want to use. With Live Media Preview switched on in the Source Viewer, the Source Viewer will display what you're skimming so you can take a closer look. Don't care for the current In and Out points? Press Option-X to wipe them both. Placing In and Out points while skimming a thumbnail in the Media Pool: While you skim across a clip's thumbnail in the Viewer, press I and O to drop In and Out points around the part of that clip you'll want to use. With Live Media Preview switched on in the Source Viewer, the Source Viewer will display what you're skimming so you can take a closer look. Once you're done, a range indicator at the bottom of that clip's thumbnail shows how much of the clip you've picked. Don't care for the current In and Out points? Press Option-X to wipe them both. Working with the Media Pool Filmstrip while the Media Pool sits in List view: Switch the Media Pool to List view, pick Show Filmstrip from the option menu, then pick a clip to surface it in the Filmstrip atop the Media Pool; run the pointer along the Filmstrip to watch it play, and tap I and O to fix In and Out points around the range you want. The Filmstrip dims the heads and tails so you can see the span of media you've marked. With Live Media Preview switched on in the Source Viewer, the Source Viewer will display what you're skimming so you can take a closer look. Don't care for the current In and Out points? Press Option-X to wipe them both.

Working through the Source Viewer: Get a clip into the Viewer by giving it a double-click in the Media Pool, or by selecting it there and hitting the Return or Enter key. From there, drive the playhead with the transport controls, the jog bar, the control panel buttons, the Spacebar, or the JKL commands, and set In and Out points through the In and Out buttons sitting to the right of the transport controls, or simply by hitting the I or O keys. Don't care for the current In and Out points? Press Option-X to wipe them both. 2 Pull whichever clip you'd like to edit out of the Media Pool or the Source Viewer, then drop it onto your chosen spot in the Timeline to run an overwrite edit. Drag a clip atop another already in the Timeline and the clip you're dragging overwrites the portion of the clip that it laps over.

Overwriting a Timeline clip by dragging one over from the Media Pool TIP: Drag a clip into the empty zone above an existing video track or below an existing audio track and a fresh track gets built for you automatically.

### Drag and Drop Editing of Several Clips Into the Timeline At Once

That same procedure applies when several clips need to go into the Timeline together, dragged out of the Media Pool in one motion. 1 Reorder the Media Pool's browser area so the clips fall into the sequence you'd like them shown in. Thumbnail view gives you the Sort Order menu for this, whereas List view lets you click any metadata column's header to sort on that column's data. Where you've leaned on the Metadata Editor to attach Scene, Shot, Take, or other identifying details per clip, sorting by those metadata criteria is possible. 2 Turn to one of three tools—the Media Pool thumbnails, the Filmstrip in the Media Pool's List view, or the Source Viewer—to drop In and Out points around the slice of each clip headed for the Timeline. 3 Choose the Media Pool clips bound for the Timeline by drawing a bounding box, by Command-dragging a few bounding boxes across different sets of clips, by Shift-clicking a span of clips, or by Command-clicking separate non-contiguous clips. 4 Drag any one of the chosen clips to your target spot in the Timeline to run an overwrite edit.

Reordering the Media Pool's clips by way of the Sort Order menu

Pulling several clips into the Timeline following the Media Pool's sort order Whatever clip(s) you drag overwrite any other clips they lap over in the Timeline. Several clips pulled from the Media Pool get edited in whatever order they're sorted into in the Media Pool, drawing on each clip's In and Out points.

### Drag and Drop Editing of Video-Only or Audio-Only Edits

Editing just a clip's video or just its audio is easy enough by switching off the audio or video destination control in the Timeline ahead of any edit (covered later in Chapter 39, "Three- and Four-Point Editing"); still, there's also a pair of keyboard modifiers that pull off the exact same thing while you drag.

For a clip's video alone out of the Media Pool: Option-drag clips into the Timeline from the Media Pool/ Filmstrip, the Source Viewer, or the Finder. For a clip's audio alone out of the Media Pool: Shift-drag clips into the Timeline from the Media Pool/ Filmstrip, the Source Viewer, or the Finder. For just the video or just the audio of a Source Viewer clip: Load a clip into the Source Viewer, then hover the pointer over the Source Viewer and drag off whichever of the Video-only or Audio-only overlays appear along the bottom of the image.

Inside the Source Viewer, Video- and Audio-only overlay controls turn up that let you pull just the video or just the audio across into the Timeline

### Drag and Drop Insert Editing

In the same way, at any frame of the current timeline you can pull several clips from the Timeline, or a lone clip from the Source Viewer, to either tuck the selection between a pair of clips or drop it amid an existing clip—nudging (rippling, in truth) every bit of media past the new edit point you create so the arriving media has somewhere to go. Shuffle inserting several clips out of the Media Pool or Source Viewer into the Timeline goes like this: 1 In the Media Pool, choose one or more clips (their sort order decides how the edited clips end up ordered), or load a clip into the Source Viewer. 2 Keep the Command and Shift keys held, then drag your selection from the Media Pool or Source Viewer over into the Timeline. 3 While you drag, the clips in tow get tucked into the Timeline wherever the pointer rests. Release the mouse to seal the edit.

Making an Insert Edit while dragging clips from the Media Pool

### Audio-Only and Video-Only Insert

### Controls in the Source Viewer

Over in the Edit page, a drop-down menu beneath the Source Viewer holds persistent choices for a source clip's Video and Audio, Video-Only, and Audio-Only inserts.

The fresh persistent Video / Audio insert controls down along the foot of the Source Viewer

### Dragging Clips From the File System Into the Timeline

On supported platforms you can also drag a clip straight out of your file system to the Timeline.

Dragging multiple clips into the Timeline from the macOS Finder

### Inserting Multiple Clips into the Timeline From the Media Pool

On certain high-volume editing projects, you can drop several clips from the Media Pool into a timeline in one go. How the clips get ordered and placed hinges on the method you use.

### Insert Selected Clips to Timeline Using Timecode

Clips can now travel directly out of the Media Pool into a timeline so that every clip's source timecode aligns with an equal record timecode value over in the Timeline. That can pay off on long-form multi-camera events, weddings or concerts say, where every camera shares one timecode to guarantee all edits sync perfectly. This function mirrors the Source Overwrite edit on the Cut page. IMPORTANT: For this edit to work, the Timeline's timecode has to overlap the clip(s)' timecode. That gets fixed within the New Timeline settings' Start Timecode field. Inserting selected clips to a timeline by timecode goes like this: 1 In the Media Pool, pick one or more clips to edit into the Timeline. Where In and Out points sit on a clip, the edit honors those bounds. With no In/Out points set, each picked clip gets edited in over its full duration. 2 Set a destination control to fix which Timeline track you're editing onto. 3 Right-click one of the picked clips and pick "Insert Selected Clips to Timeline Using Timecode" off the drop-down menu. 4 Every picked clip gets overwritten into the Timeline at its proper timecode location onto the destination track. IMPORTANT: Where several picked clips carry overlapping timecode, no edit happens.

### Insert Selected Clips to Timeline With Handles

This command drops several clips into the Timeline one after another, going by the Media Pool's current sort order, with handles pared away from each clip's current In and Out points (drawing on the Default Handles Length found under the User Preferences' Editing panel). Paired with the Add Transition tool (Command-T), this function shines when you're quickly knocking out montages from a batch of clips. To insert clips with handles to the Timeline: 1 In the Media Pool, pick the clips to insert into the Timeline with handles. 2 Right-click any picked clip, then pick "Insert Selected Clips to Timeline With Handles." The clips slot in starting at the Timeline In point with the default handles length already worked out.

TIP: To round off the montage, pick the clips in the Timeline, then pick "Add Transition" (Command-T) off the Timeline menu. That lays the default transition across all the clips in one stroke.

### Audio Track Creation While Editing

When you drag an audio clip into the undefined gray zone of the Timeline below the audio tracks already there in order to build a new track, that new track gets a channel mapping mirroring the channel count of the audio clip you're dragging. That also means if you've used Clip Attributes to map a clip's audio into multiple tracks where each track carries a different channel mapping—one 5.1 track, one stereo track, and six mono tracks, say—then editing that clip into the Timeline so its audio portion spawns new tracks will automatically build eight tracks: one 5.1, one stereo, and six mono.

### Not Creating New Tracks when Adding Clips to a Timeline

Under Edit > Edit Options there's a menu item named Automatically Create Tracks on Edit. On by default, this option keeps DaVinci Resolve's standard behavior of adding new tracks to the timeline automatically whenever your source material holds more audio tracks than your timeline does. Switch it off and you can drag source clips onto the timeline without the timeline spawning new tracks for the extra audio or video elements. Where your source camera files carry more audio tracks than your timeline holds, switching this option off won't build extra new tracks and will pull in only the elements showing in the track destination controls. That can help if, for instance, you wanted to bring in just a single mixed track with a clip from a multitrack recorder and skip the independent microphone tracks.

### Using Keyboard Shortcuts and Three-Point Editing to Assemble a Program

Drag-and-drop editing may be plenty intuitive, yet there are other ways to cut clips into the Timeline—using the playhead to mark where those clips begin—that can run faster and more precisely. Every one of these examples leans on "overwrite" edits, which clear unwanted media out of the Timeline as you add in the clips you do want. Here are two examples showing how to do it.

### Example: Assembling Clips Into the Timeline From the Source Viewer

The example below shows how you can use the Edit page to throw together a quick first cut of edits, drawing on various features of the Media Pool, Viewers, and Timeline. Spelled out with every possible option, it may look like a great many steps, but once you've got these fundamentals down and built a little muscle memory for the keyboard shortcuts in play, these methods turn out really fast. 1 Hit Command-1 to bring up the Media Pool, then steer with the Arrow keys to land on a bin (Up and Down move which one is highlighted, Right and Left open and close bins). Next hit Command-2 to jump to the clip browser, and again work the Arrow keys to land on a particular clip.

2 Hit the Return or Enter key to load the chosen clip into the Source Viewer. 3 Either drag the playhead with the pointer or work the Spacebar or JKL keys to reposition it, then set In and Out points (I and O) bracketing the stretch of that clip bound for your program. 4 By default, the source destination controls are mapped to tracks V1 and A1. If need be, choose different video and audio tracks to edit the clip onto in the Timeline by one of these means:

- Drag the source destination controls from where they sit now to where you want them in the Source Track Selector.
- Right-click an empty source destination control in the Source Track Selector, and pick the source destination off the context menu.
- Shift the source destination controls upward and downward with the Command-Option Up and Down Arrow shortcuts (for audio) and the Command-Shift Up and Down Arrow shortcuts (for video).
- Assign the video and audio source destination controls to particular tracks with the Option-1–8 key shortcuts (for video) and the Command-Option-1–8 key shortcuts (for audio).

5 By default, every source destination control is enabled. Should you want clips edited into the Timeline as audio-only or video-only, any one of these will do:

- Click a source destination control itself to shut off its video or audio component.
- For the tracks currently mapped, hit Option-1–8 (for video) or Command-Option-1–8 (for audio)

to flip the destination controls on those tracks on and off.

- From the drop-down menu sitting under the Source Viewer, choose among a source clip's Video and Audio, Video-Only, and Audio-Only inserts.

6 Working in the Timeline Viewer or the Timeline itself, steer the Timeline playhead with the pointer, the Spacebar, or the JKL controls to the frame where the clip you're about to edit should begin. With no In or Out points set in the Timeline, the playhead's position stands in as the In point by default. 7 To pull off an overwrite edit, do one of these:

- Pull the clip out of the Source Viewer onto the Timeline Viewer and let it drop on the Overwrite overlay. Under single viewer mode, that overlay appears only as you drag a clip out of the Media Pool onto the Timeline Viewer.
- Click the Overwrite Clip button in the toolbar.
- Choose Edit > Overwrite (or press F10).

The chosen clip(s) get overwritten onto the selected track at the playhead's spot, and the playhead travels by itself to the tail of the just-edited clip, primed for your next edit. Where that clip happens to be the final one on the Timeline, the frame sitting to the playhead's left is the last frame (carried with a jagged overlay along the Timeline Viewer's right edge) in place of the black that is the genuine frame after that clip. That eases the job of squaring up the next edit. If not, the playhead displays whichever frame lands at that moment in time. 8 For the next clip, load it into the Source Viewer, set its In and Out points, and lean on the Overwrite Clip button or command to drop it into the Timeline. Carry on this way until the run of edits you're aiming for is assembled.

The Timeline playhead resting on the first frame past the clip you just edited; over in the Timeline Viewer a jagged overlay on the right signals that this frame isn't a genuine one

### Example: Assembling Clips Into the Timeline From the Media Pool

If you like, you can also edit clips straight into the Timeline from the Media Pool using an assortment of commands. That can be a quick way to tack clips onto the end of the Timeline (though you can pull off insert edits this way too).

Editing one or more clips out of the Media Pool onto the Timeline: 1 Using the pointer, click a clip within the Media Pool to select it. 2 For one or more of the Media Pool's clips, place In and Out points by one of these means:

- Under Metadata view, run the pointer across a clip's thumbnail and tap the I and O keys. Where Live Media Preview is turned on for the Source Viewer, dragging across that thumbnail echoes its content into the Source Viewer.
- Under Thumbnail view, slide the pointer over a clip's thumbnail and tap the I and O keys. Should Live Media Preview be active for the Source Viewer, dragging over the thumbnail reflects what it holds in the Source Viewer.
- Under List view, drag along the Media Pool Filmstrip Viewer and tap the I and O keys. Where Live Media Preview is on for the Source Viewer, dragging along the filmstrip echoes its content into the Source Viewer.

3 Reorder the Media Pool's browser area so the clips end up in the sequence you'd like shown. Thumbnail view offers the Sort Order menu for that, while List view lets you click any metadata column's header to sort on that column's data. 4 By clicking, by dragging, by way of the Command-Option as well as Command-Shift Up and Down Arrow Key shortcuts, or by way of the Option-1–8 and Command-Option-1–8 key shortcuts, map the video and audio source destination controls onto whichever tracks should receive the incoming clip(s)' video and audio. Want the clips edited in as audio-only or video-only? Click a source destination control itself to shut it off. 5 Choose the clip or clips you intend to edit. The insert, overwrite, place on top, ripple overwrite, and append at end edits each handle several clips together, whereas the replace and fit to fill edits take just one clip apiece and will edit in only the first of multiple chosen clips. 6 To carry out the edit, do one of these:

- Use any of the editing commands in the Edit menu.
- Drop the picked clips into the Timeline via the corresponding keyboard shortcuts: Insert with F9, Overwrite with F10, Replace with F11, Place On Top with F12, Ripple Overwrite with Shift-F10, Fit to Fill with Shift-F11, or Append To End of Timeline with Shift-F12.
- Right-click one or more picked clips in the Media Pool, and pick "Insert Selected Clips to Timeline" or "Append Selected Clips to Timeline."

The picked clip(s) get edited into the Timeline.

### Making Selections in the Timeline

After you've put together a sequence of clips in the Timeline, you'll likely need to work them over some more—moving, deleting, trimming, or otherwise tweaking the clips in the Timeline so the edit plays with the pacing and verve you're after.

### Manually Selecting Clips in the Timeline

Plenty of operations have you make a selection first, to mark out the scope of what you're about to do. There are many routes to that. Selections you can make using the mouse:

- To select one clip: Click a clip with the mouse.
- To select all clips under the playhead: You can pick every clip under the playhead at once, no matter how many tracks they're spread across, by choosing Trim > Select All Clips Under Playhead (Option-Shift-V).
- To select a continuous range of clips by dragging: Starting from a vacant patch of the Timeline, draw a bounding box that encloses a cluster of clips.

Drawing a bounding box to grab a continuous stretch of clips across the Timeline

- To select a continuous range of clips by Shift-clicking: Begin by clicking the run's first clip, then Shift-click the last; everything between them gets selected on its own as well.
- To select a discontinuous range of clips: Command-click whatever clips you like to grab them no matter where they sit on the Timeline. A Command-click on an already-selected clip drops it from the selection.

Using Command-clicks to grab a discontinuous stretch of clips across the Timeline Selecting clips using the keyboard or menu commands:
