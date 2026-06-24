# Fast Editing In The Cut Page (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Working with a pointer — be it a mouse, a trackpad, or a tablet — lets you take hold of the In and Out handles sitting just below the scroll area along the Viewer’s bottom and drag them to mark out a span of media. The draggable In/Out controls along the foot of the Viewer Once your In and Out points are placed, the jog In and Out controls — parked at the far left and far right ends of the Viewer’s scroll area — let you refine exactly where those points land. Click and drag on either the Jog In or Jog Out control to inch that edit point along. While you drag, a filmstrip overhead reports how many frames you are trimming. The draggable Jog In control trimming the In point, with In/Out points placed in the Timeline Ruler (whether the Upper Timeline’s or the Timeline Editor’s) that can be dragged either way for fine adjustment. The draggable In/Out points within the Timeline Ruler

### Editing the Duration Field in the Cut Page Viewer

As you edit on the Cut page, you drop In and Out points to bring in a particular span of video. How long that video span runs shows in the Duration field, tucked into the Viewer’s upper-right corner. That field can now be edited, and it shifts the Out point to agree with whatever value you type. You may key in a specific frame count outright, apply the + or - modifiers to bump the value by exactly that much, or work the hh:mm:ss:ff field straight away. The editable duration field in the top right of the Viewer

### Change Clip Duration Dialog

Through the Change Clip Duration dialog you reset a clip’s length outright — by entering frames, a timecode value, or by leaning on time- and frame-based presets. To bring the Change Clip Duration dialog up, pick one or more clips on the Timeline and go to Clip > Change Clip Duration (Command-D), or right-click a clip and pick Change Clip Duration off the contextual menu. This dialog runs on the Cut page as well as the Edit page. The fresh Change Clip Duration box shown in Timecode mode. Here are the options in the Change Clip Duration Dialog box: Format: Choose whether to work in Time (Timecode) or in Frame values. Duration: Enter the timecode value or frame count you want the selected clip’s new length to be. Preset: Set a length by clicking 1, 5, or 15 seconds (or the matching value in frames). End stretches the length out to the selected clip’s final frame, no matter what Out points are set. Extend Beyond Clip Length (Cut page only): This tacks black filler onto any clip whose length is pushed past the clip itself. Cancel/Change: Hit Cancel to back out without altering the clip’s length, or Change to commit the new length to the selected clip. TIP: You can adjust the length of several clips together by selecting multiple clips before you open Change Clip Duration. Every selected clip will then take on the single length entered in the Change Clip Duration dialog box.

### Video Only and Audio Only Edits

As a rule, every edit function on the Cut page pulls in both a clip’s Audio and Video sections when placing it on the Timeline. There are, however, a number of situations in which you would rather use only the Audio or only the Video portion.

For an Audio Only edit: Click the Audio Only icon over to the left of the Upper Timeline, and click it off again to go back to the usual audio-and-video edit. For a Video Only edit: Click the Video Only icon to the left of the Upper Timeline, then click it off to resume the usual audio-and-video edit.

(Left) The Audio Only icon, (Right) The Video Only icon

### Drag and Drop Editing

Editing by drag and drop offers a simple route to stitching clips into a rough cut. After you have marked a span of media with the Source Clip or the Source Tape, you can click and drag — from either the Viewer or the Media Pool — onto the Upper Timeline or the Timeline beneath it to drop a clip into your program. The manner and the spot in which you drag dictate how that clip ends up edited.

### Append

Drop a clip onto a bare timeline, or onto the dark gray region left of the clips in the Timeline, and it becomes the opening clip of your edit. Drop a clip against the extreme left or right edge of every other clip in the Timeline’s upper or lower zone, and you tack that clip onto the Timeline’s end or start.

(Top) A clip being dragged to the Timeline’s far right so it appends, (Bottom) That same clip now appended

### Ripple Overwrite

Drag a clip over an existing one in the Timeline or Upper Timeline so the whole clip lights up, then drop it at once, and you carry out a Ripple Overwrite edit, swapping the old clip in the Timeline for the new one. Once you have ripple overwritten a clip on Track 1, every clip to its right shifts along — opening room when the incoming clip runs longer, or closing the gap when it runs shorter.

(Top) Clip DD being dragged over clip BB on the Timeline so as to Ripple Overwrite clip BB, (Bottom) Because clip DD runs shorter than clip BB, the Timeline shrinks after the edit completes

### Overwrite

Drag a clip over an existing one in the Timeline or Upper Timeline and pause for a beat, and the Timeline overlay shifts from lighting up the entire clip to lighting up only the slice of the incoming clip that sits over the existing one. Release the clip and you carry out an Overwrite edit, which paints the incoming clip’s media over whatever media already occupies the Timeline. An Overwrite edit leaves the Timeline unrippled.

(Top) Clip DD being dragged over clip BB on the Timeline with a pause to trigger an Overwrite, (Bottom) Clip DD paints over the middle of clip BB, splitting it in two even as the Timeline keeps its length

### Using Cut Page Edit Commands

Along the bottom of the Media Pool sit five buttons that open up other kinds of edits. A few of these carry keyboard shortcuts and also have dedicated keys on the DaVinci Resolve Editor Keyboard.

### Smart Indicator showing where an edit will occur

The edit buttons beneath the Media Pool run in this order: first Smart Insert, then Append and Ripple Overwrite, followed by Close Up, then Place On Top, and finally Source Overwrite

### Smart Indicators

Several of the smart tools on the Cut page spare you from setting explicit In and Out points in the Timeline; instead they read where the playhead sits over a clip to infer the spot you probably mean to edit. Wherever DaVinci Resolve plans to land that edit is flagged by a Smart Indicator icon along the Timeline Ruler. So the edit points read more easily on the Timeline, after a few seconds the Smart Indicator bobs up and down on the Timeline ruler while the actual edit point pulses green (or red, should the clip have hit its first or last frame).

### Setting Up and Performing Edits

Whatever sort of edit you have in mind, the routine for setting it up and carrying it out stays identical. What this section lays out is that general routine, while the sections after it explain how each individual edit operates. To set up and perform an edit: 1 To begin, find a clip you want to drop into the Timeline. Two broad approaches exist: a) Open a bin holding the clips you want, then click the Source Tape in the Viewer to lay out a stringout of every clip in the current bin and its subfolders, ordered by the sort you currently have chosen. From there, scrub through them all with JKL or the DaVinci Speed Editor’s shuttle/jog/ scroll wheel until you spot the media you are after. b) Open a bin holding the clips you want and work through the thumbnails, filmstrips, or columns to pick the one you need, calling on the Search field when it helps you track the clip down. 2 Scrub a thumbnail or filmstrip, work the controls in the Viewer, or use your DaVinci Speed Editor’s controls to find the frames where you want In and Out points marking an edit range, then press the I (In) and O (Out) keys to lay those points down.

3 Where it matters, pick the video track you want to edit onto by clicking its track header to select it; selected tracks show highlighted. 4 Carry out an edit that drops the source clip’s chosen range onto the selected video track at the frame you want, using either the buttons along the bottom of the Media Pool or keyboard shortcuts. Each edit command lands the source clip somewhere different. 5 With your edit committed, press Q (or click the Timeline Viewer button) to flip the Viewer over to the Timeline so you can play back and review what you just cut, then press Q once more to return to the Source Clip or Source Tape (whichever you used last) and hunt down the next clip to edit, beginning the whole cycle again at Step 1.

### Smart Insert

Drops the incoming clip in on its own at whichever edit point lies nearest the playhead (flagged by the Smart

Indicator) along the chosen track, shoving every clip beyond that edit point forward to open space

for the incoming clip when you have inserted onto Track 1. Since this counts as a smart operation, it bars you

from dropping a clip at just any frame you please; incoming clips only land at the nearest already

present edit point.

(Top) Ahead of a Smart Insert, (Bottom) Once clip DD has been inserted between clips AA and BB Append Here the playhead’s position carries no weight; incoming clips always go in right after the final clip on the Timeline.

Performing an Append edit of clip DD to the Timeline

### Ripple Overwrite

In its plainest form, Ripple Overwrite swaps out a Timeline clip for an incoming one. Apply Ripple Overwrite to a clip on Track 1 and every clip lying to the right of the affected one in the Timeline shifts on its own — forward to open space when the incoming clip is longer, or backward to wipe out gaps when it is shorter.

Carrying out a Ripple Overwrite that replaces a whole clip sitting at the playhead (BB) with the incoming clip (DD)

That said, Ripple Overwrite behaves another way once you have laid In and Out points in the Timeline to mark a range. Then the incoming clip takes the place of whatever stretch of the Timeline lands inside that range, and every other clip to the right of the affected range slides — forward to open space when the incoming clip is longer, or backward to erase gaps when it is shorter.

Carrying out a Ripple Overwrite that swaps an In/ Out range of the Timeline (part of clips BB and CC) for the incoming clip DD

### Close Up

Lets you cut a clip into the Timeline as a zoomed-in close up, compensating for the absence of genuine close ups that would have called for longer lenses or for moving the camera nearer the subject. The function earns its keep especially when, say, 4K media sits in a 1080 timeline, or 8K footage in a 4K timeline; you can then push into existing wide shots to fashion medium shots, or into medium shots to fashion close up shots, all without quality loss. Running this edit brings the incoming clip in scaled to roughly 150% as a close up, runs a face detection too, and, where a face or faces turn up, repositions the face within the frame on its own. The Timeline frame the incoming clip lines up with rests on the following:

- With no In or Out points on the Timeline, the incoming clip takes the Timeline playhead for its In point.
- Where a timeline In point exists, the incoming clip snaps to it.
- Should only a timeline Out point be set, with no In point, the incoming clip’s Out point meets it, which “backtimes” the clip.

(Top) Ahead of a Close Up edit, (Bottom) Once clip DD has been cut into the Timeline via a Close Up edit

### Place On Top

Lets you cut the incoming clip in as a superimposition over whatever else occupies the Timeline; it always rides on top, so when clips already fill tracks 1, 2, and 3, the incoming clip drops onto track 4 by itself, no matter which track happens to be selected. The frame the incoming clip lines up with rests on the following:

- Should the playhead sit close to an edit point (five frames or fewer away), and no timeline In or Out points exist, the incoming clip snaps to the nearest timeline edit point by the playhead (marked by the Smart Indicator).
- Should the playhead be nowhere near an edit point, and no timeline In or Out points exist, the incoming clip snaps to the playhead.
- Where a timeline In point exists, the incoming clip snaps to it.
- Should only a timeline Out point be set, with no In point, the incoming clip’s Out point meets it, which “backtimes” the clip.

(Top) Ahead of placing a clip on top, (Bottom) Once clip DD has been cut into the timeline via a Place On Top edit

### Source Overwrite

For this edit to behave, several clips have to carry overlapping timecode — the situation you get when synced timecode is recorded to multiple cameras on a multi-cam shoot. Where no overlapping timecode exists, the edit accomplishes nothing. When your footage comes from several cameras whose timecode is synced, the simplest path is to lay In and Out points across a Timeline clip at the spot you want to cut away to a different angle. Take this example: a wide shot of a cooking show holds on the instant the chef begins slicing a chili. Marking out a cutaway by laying Timeline In and Out points. From the Media Pool you then choose a clip matching the angle you want as your cutaway, one whose synced timecode overlaps the Timeline clip. Leave In and Out points unset; should any already exist, clear them with Option-X.

Choosing a Media Pool clip from another camera that has overlapping timecode

Press the Source Overwrite button and a synced portion of the chosen Media Pool clip gets cut into the Timeline across the In and Out points you laid, layered over the top. What you get is a flawlessly timed cutaway.

Putting Source Overwrite to work, cutting a layered, synced portion of the source clip onto the Timeline across the In/Out points

As another option, Source Overwrite can on its own drop a source clip bearing a marked In/

Out region over a Timeline clip so its timecode falls in step with the timeline clip’s timecode — handy for those times you are unsure just how much of the incoming source clip belongs in the

Timeline and simply want it synced the right way.

### Overwrite

No button exists for an overwrite edit, yet the F10 key will carry one out, painting the incoming clip over a stretch of the Timeline while leaving every other clip exactly where it is. The frame the incoming clip lines up with rests on the following:

- With no timeline In or Out points defined, the incoming clip snaps to the playhead.
- Where a timeline In point exists, the incoming clip snaps to it.
- Should only a timeline Out point be set, with no

In point, the incoming clip’s Out point meets it, which “backtimes” the clip.

(Top) Beforehand, parking the playhead on the frame you mean to serve as the incoming clip’s In point, (Bottom) Afterward, with the end of clip CC overwritten by incoming clip DD

### Copy, Paste and Remove Attributes from Timeline Clips

On the Cut page timeline you can copy, paste, and strip attributes from clips, much as the Edit page lets you. The way to do it: right-click the timeline clip whose attributes you want to grab and choose copy. Next, pick the timeline clip you mean to change, right-click, and choose Paste Attributes. Up comes a check box menu where you single out exactly which attributes to paste. So, by way of the context menu’s controls, clip attributes can be cut, copied, and pasted from the Cut page timeline.

### Subtitles

### Subtitles in the Cut Timeline

Subtitle support on the Cut page now matches what the Edit page provides, the automatic Create Subtitles from Audio feature included. For a fuller account of how to handle subtitles, turn to Chapter 52, titled “Subtitles and Closed Captioning.” Adding a Subtitle Track to the Cut Timeline goes like this:

- Click on the Timeline Actions icon.
- Select Add Subtitle Track from the drop-down menu.

To free up room for Audio and Video tracks, Subtitle Tracks can be shrunk on the Cut page by clicking the Timeline Options icon and choosing Minimize Subtitle Track.

### Create Subtitles from Audio (Studio Version Only)

Subtitles can be generated for you straight from your timeline’s audio tracks: the DaVinci Resolve Neural engine studies the speech and converts it into text subtitles on its own. For more on automatic subtitling, see Chapter 52, “Subtitles and Closed Captioning.”

To Automatically Detect and Create Captions from Timeline Audio:

- Open whichever timeline holds the video and audio clips that need captioning.
- Click the Timeline Actions icon, then pick Create Subtitles from Audio off the drop-down menu.

### Source Tape Editing

Though every Cut page feature works fine on its own, a handful are built to pair up and smooth your editing along. Bring the File Inspector, Source Tape, Metadata View, and the Navigable Folder Structure together, for instance, and you can turn one folder of jumbled clips into a tidy, well-organized project.

### Metadata Entry Using the File Inspector

Entering metadata is where organizing any project begins. Our starting project holds a great many clips, every one of them parked in a single Master Bin. Those clips need suitable metadata attached, and the File Inspector is what we will lean on to do it.

### An unorganized Media Pool in the Cut page

With the File Inspector open, tick the Auto Select Next Unsorted Clip box; from then on, pressing the return key jumps you to the very same metadata field on the next clip in the Media Pool. Fill in each clip’s Scene, Shot, and Take metadata, going by what the slate in that clip shows. Once every clip bears its scene, shot, and take values, highlight the whole Media Pool, then type the text string “%{Scene}_%{Shot}_%{Take}” into the File Inspector’s Name field. Those variables relabel each clip with its scene, shot, and take numbers strung together by underscores — “02A_CU_03”, to give one. Keying Scene, Shot, and Take values into the File Inspector and renaming every clip through variables. Next, create a pair of new bins in the Media Pool, Scene01 and Scene02, then drag every clip whose name begins with 01 into the Scene01 folder and every clip whose name begins with 02 into the Scene02 folder. With that, this project’s metadata entry is finished.

The Media Pool, its scene 1 clips now gathered in the Scene01 folder and its scene 2 clips in the Scene02 folder

### Using the Source Tape

Switch the Source Tape on by clicking its icon in the Viewer. From the Media Pool view options choose Metadata View, then in the Sort menu choose Sort By Scene, Shot. The clips in the Media Pool now group by scene, and the clips from both scenes lay out in scene order inside the Source Tape viewer. Click a particular clip in the Media Pool and the playhead leaps to that clip’s opening frame in the Source Tape. From here the shots’ progression is plain to see (take two trails take one, and so on), and you can keep editing without poking around and clicking in the Media Pool.

The Source Tape mirroring every clip in the Media Pool, with the Metadata View grouping those clips by Scene

### Limiting the Source Tape Scope by Folder Structure

Once a project swells, keeping a whole film’s worth of media in the

Source Tape at all times turns cumbersome. You can rein the Source Tape’s scope in at the bin level. While you move through the

Source Tape, the clip you are on is highlighted, and its hierarchy now shows along the top of the Media Pool

title bar. Click straight on the bins in that bin path and you widen or tighten the reach of

the Source Tape in a flash. Click Scene02 and the Source Tape narrows to display only the clips in

that folder. Click back on Master and the Source Tape widens out once more to show every folder’s clips.

The navigable folder structure; a click on any of these levels tightens or widens how far the Source Tape reaches.

The Source Tape pared down to just the clips in Scene02

The Source Tape narrowed to display only the Scene01 clips

The Source Tape opened up to reveal every clip within the Master folder

It comes in handy too when you work through bin structures that echo the original camera file system. Picture this:

a camera might write each memory card out as its own folder, and within that, every single

clip is stored as a separate folder of its own. Pull this file system into the Media Pool

by way of the Create Bins option and those nested levels carry over into the Media Pool bin structure. From then on,

clicking a card bin in the Source tape shows you every clip on that card directly, instead of

presenting a host of separate sub-bins. You can view this in Thumbnail, List, and Filmstrip layouts as well.

### Sync Bin Multicam Editing

A whole set of tools in DaVinci Resolve makes editing multi-camera productions feel more natural and run more efficiently. When clips shot at the same instant on different cameras carry common timecode, DaVinci Resolve can knit all those camera angles into sync for you as you cut. Think of the tools covered in this section as a kind of digital assistant editor, forever combing through your media and laying the right shots in front of you at just the right moment. Pair this with the DaVinci Resolve Speed Editor and the Cut page becomes a formidable multi-camera editor.

### Preparing Footage for Sync Bin Editing

For the Sync Bin to function correctly, each clip it holds has to meet the characteristics laid out below.

### All Clips Must Have a Common Timecode

As a rule, professional video cameras and audio recorders can “jam-sync” their timecodes to one another, so that every distinct video and audio source lays down the exact same timecode at the exact same instant. Jam-syncing timecode is the fastest, simplest, and most dependable way to make your footage line up flawlessly. Where your footage lacks a shared timecode, you will have to take a few extra steps to get all your material aligned at the right moment. For more, consult the Sync Clips Window section further down.

### All Clips Must Have a Unique Camera Name

Nearly every professional video camera provides some means of naming the camera within its internal menu system. That camera name then rides along as metadata in each captured clip, where DaVinci Resolve can read it automatically. Name your cameras either with letters (A, B, C, etc.) or with numbers (1, 2, 3, etc.), running in sequence up to however many cameras you are shooting with. Should your camera fail to log this on its own (or log it wrong), you can set the camera’s name by hand through the Camera # field of the Metadata Editor in the Media Pool.

### Sync Clips Window

When your footage carries no shared timecode, or the timecode it has needs changing for whatever reason, the Cut page’s Media Pool puts forward a Sync Clips window where you can adjust the sync of every clip in a bin. You reach it by clicking the Sync Clips Window icon atop the Media Pool.

### The Media Pool Sync Clips window icon

When the Sync Clips window opens, a live multi-camera sync Viewer sits on its left and an ordinary clip Viewer on its right. A timeline runs along the bottom too, charting how all the bin’s clips relate in time.

### The Media Pool Sync Clips window

### Sync By Tools

Several tools within DaVinci Resolve will bring your shots into flawless sync on their own.
