# Trimming In The Cut Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Trimming in the Cut Page

After you've strung a series of clips into a roughly edited timeline, the Cut page gives you many ways to reshape them within the Timeline. CUT The point of these tools is to tighten your program's pacing by refining how each clip is timed, along with the edits dividing them. The goal is to keep adjustments like these effortless, so your program reads clearly and plays back with timing that feels right. Reworking the edits within a timeline this way goes by the name “trimming.”

### Tools That Help You Work in the Timeline

As you set about trimming clips within the Timeline, a row of buttons up at the Timeline's top left assists you in aligning clips and keeping tabs on key frames as you go.

### Ripple on Main Track Option to Disable Ripple Trims

While trimming the main track (track 1) on the Cut page, you're able to switch off the automatic rippling of that track's clips. That gives you the choice of making simple trim adjustments while leaving the Timeline's other clips from shifting up and down the Timeline.

To Enable or Disable Rippling on a Cut Page Timeline:

- Click the Timeline Options icon and pick Ripple On in the contextual menu, or click

straight on the Ripple On icon at the left of the Timeline ruler. Click once more to toggle Rippling

on or off.

- You can instead hold the Option key down while you trim with the mouse on the main

track to suspend rippling for the moment.

The Ripple On control toggles r ippling on the main track.

### Fixed or Free Playhead

You get to decide whether the Cut timeline keeps its default fixed playhead (the video runs beneath the playhead), or instead lets it travel along with the video (the playhead runs over the video). Pick the mode by clicking the Timeline Options icon and ticking or clearing Fixed Playhead,

- With it ticked, the playhead stays pinned at the Timeline's center; your edited clips glide past it whenever you play (press the Spacebar), jog, or shuttle (the JKL keys) in any direction. Locked mode pairs beautifully with the DaVinci Resolve Editor Keyboard, since the Timeline runs past the playhead as you work the Jog/Shuttle/Scroll wheel. You can likewise scroll the Timeline with your pointer by dragging the Timeline Ruler up top left or right, which carries all your clips left or right along with it.
- With it cleared, the playhead rides over the clips whenever you play (press the Spacebar), jog, or shuttle (the JKL keys) in any direction, while the clips hold still. This mode helps when you're doing precision trimming in the Timeline with a pointing device, since the clips stay put as you drag pieces of clips to adjust them. As soon as the playhead reaches the Timeline's right or left edge, the Timeline pages over to show the next portion of your edit. You can also reposition the playhead by clicking in the Timeline Ruler to send it to that frame, or by hovering the pointer above the playhead's top handle (or above the playhead itself) and then dragging it anywhere you like.

### Snapping

Toggle Snapping on or off by clicking the Timeline Options icon and ticking or clearing the magnet-shaped Snap icon, or hit N to switch snapping on or off. With snapping active, clip in and out points, markers, and the playhead all snap into alignment with each other, which makes it simple to join clips at their boundaries or to align clips against markers or the playhead as a reference for key frames you mean to cut to. As a clip's boundary snaps, a white line indicates the edges being lined up together.

The indicator that appears when clip boundaries are snapping to another edge

NOTE: While the playhead is locked, clips won't snap to it. Even so, you'll want to be able to disable snapping whenever the behavior gets in the way of making fine adjustments to Timeline clips. Hit N to switch snapping on or off momentarily as you're dragging a clip in the Timeline, or while scrubbing the playhead with the pointer.

- If you toggle snapping mid-drag of a clip, an edge, or the Timeline, that counts as a temporary change, and snapping returns to its prior state once you let go of the mouse button.
- If you toggle snapping between drag operations, the snapping state holds until you next change it.

### Locking, Muting and Disabling Tracks

While working in the Timeline, it can help to lock tracks holding clips you'd rather not change by accident as you go. As an example, you could lock an audio track holding an edited music piece against which you're currently cutting your other video and audio, so you don't unintentionally alter or trim the music underpinning your program. Clips on locked tracks show up stippled to signal they're protected from changes.

A locked audio track; here the Lock icon shows closed and that track's clips appear stippled

It can also help to mute the audio or disable the video on tracks you don't care to see during Timeline playback. For instance, you might disable a track packed with title graphics when you want a clearer look at the video beneath it. Every track carries Mute and Enable controls, whereas audio-only tracks have just Mute controls. Enabled controls are white; disabled ones are gray.

Here Track 1 is disabled; its Enable button glows orange and the track's clips look dimmed

### Audio Trim View

While trimming on the Cut page, you can opt to enlarge the audio

waveform of a Timeline clip during the trim. This mode delivers a far more precise look at the audio,

making it simpler to land on an exact edit point between words, beats, and so on.

To toggle Audio Trim view: Click the Timeline Options icon and tick Trim to Audio. With this turned on, an enlarged waveform appears for audio/video clips you're trimming in the Timeline as the trim happens. It collapses back once you finish the trim.

The Audio Trim view, with an enlarged audio waveform on display as a Timeline trim is underway

### Timeline Markers

Markers can be dropped into the Timeline Ruler — found in the Upper Timeline as well as the Timeline Editor — to track key frames of clips you want to recall, alternate edit points you're weighing, pivotal moments in the edit, or to jot notes about things still to do. Marker text — which displays as an overlay in the Viewer — can be edited, and you can recolor markers to tell them apart.

### The Marker button in the Timeline track header

Ways to work with markers:

- To add a marker: Park the playhead on a frame you want to flag, then click the Marker button in the Timeline header, or hit the M key. A marker can also be added via the Timeline Actions icon.
- To add a marker with a specific color: Park the playhead on a frame you want to flag, then click the Timeline Actions icon and pick Set Color and Add Marker. This both drops a marker and opens the Markers Edit window, where you can choose a particular color and type a comment.
- To jump the playhead among markers: Hold the shift key and tap the Up or Down Arrow keys to leap the playhead between markers.
- To edit a marker’s name, text, color, or keywords: Either double-click it, or send the playhead onto a marker and press M a second time. When the marker dialog appears, edit the Name, Notes field, Keyword field, or the marker's color, then hit Return or click Done to dismiss it. Markers carrying custom notes display a dot.
- To move a marker: Drag a marker onto a different frame within the Timeline Ruler.
- To delete a marker: Pick a marker and hit Delete. Or, line the playhead up with a marker and press Option-M. Or, send the playhead to a marker, press M to bring up the marker dialog, and click Remove Marker. CUT

Blue, red, and orange markers along the Timeline; only the red one carries text, while the rest have none

### Making Selections

The further you go on the Cut page, the more valuable it becomes to know how to form different sorts of selections, both within the Media Pool and within the Timeline. Most of these selection techniques will feel familiar if you've used other media applications or file managers before. Ways to select clips in the Media Pool:

- To select a single clip: Click a clip within the Media Pool. With a clip selected, the Up and Down arrow keys let you shift the selection to neighboring clips.
- To select a contiguous range of clips: Drag a selection box across every clip you mean to grab, or click the first clip in a run, then Shift-click the last to select those clips plus all in between.
- To select a noncontiguous range of clips: Command-click whichever clips belong in the selection. Or hold Command down as you drag bounding boxes — over clips not yet selected to bring them into the current selection, or over selected ones to take them out.
- To select all clips: Pick one clip, then go to Edit > Select All (Command-A).

Ways to select clips in the Timeline:

- To select one clip: Use the mouse to click a clip. Command-clicking that very clip de-selects it.
- To de-select all clips in the Timeline: Click any empty stretch of the Timeline to de-select everything, or hit Command-Shift-A.
- To select a continuous range of clips by dragging: Starting from an empty stretch of the Timeline, drag a bounding box that wraps a group of clips.
- To select a continuous range of clips by Shift-clicking: Click your first target clip, then Shift-click the final one; everything sitting between them gets selected on its own as well.
- To select a discontinuous range of clips: Command-click whichever clips you want to grab, wherever they sit on the Timeline. Command-clicking an already-selected clip deselects it.
- To select all clips under the playhead: Grab every clip beneath the playhead in one move, no matter how many tracks they span, via Trim > Select All Clips Under Playhead (Option-Shift-V).
- To grab every Timeline clip lying ahead of the playhead: Right-click the playhead's top handle; on the radial menu that pops up, click its right button.
- To grab every Timeline clip lying behind the playhead: Right-click the playhead's top handle; on the radial menu that pops up, click its left button.

The radial menu shown after a right-click on the playhead's top handle Ways to select edits in the Timeline with the pointer:

- To select an edit to roll: Bring the mouse to the middle of an edit point, and once the ripple cursor shows, click to grab the edit.
- To select just the incoming or outgoing half of an edit, ready to resize it: Bring the mouse left or right of an edit's center, and once the resize/ripple cursor shows, click to grab that portion of the edit.
- To select multiple roll points: Command-click the centers of several edit points. Command-click a selected edit point to deselect it.
- To select multiple resize points: Command-click on the left or right side of several edit points.
- To de-select all clips in the Timeline: Click any empty stretch of the timeline to de-select everything.

Keyboard shortcuts for selecting edits in the Timeline:

- To select an edit point from the keyboard: Press V to grab the edit point nearest the playhead.
- To change an edit selection from the keyboard: With an edit point selected, press U to cycle between selecting the outgoing half, the incoming half, or the whole edit.
- To de-select all edits in the timeline: Press Command-Shift-A.

### Moving Clips in the Timeline

After you've cut some clips into the Timeline, you'll likely want to start refining the edit by shuffling clips around. Which operation occurs depends on how you move those clips. Every one of these techniques functions in both the Upper Timeline and the Timeline Editor.

### Ripple Overwriting An Entire Clip in Track 1

Drag a clip in the Timeline or Upper Timeline across another Timeline clip so the pointer covers that clip, then quickly drop it onto another clip in Track 1. Your dragged clip takes over the clip you dropped it on, and every clip to the right shifts to either open space (if the dragged clip is longer) or close the gap (if it's shorter).

### Clicking clip BB to begin dragging it

Dragging clip BB onto clip DD to ripple overwrite it

Clip BB relocates and assumes clip DD's spot, as the remainder of the Timeline slides left to seal the gaps in Track 1 NOTE: Linger too long and this Ripple Overwrite turns into a plain overwrite. Drag a clip from Track 1 onto a clip on any other track and an overwrite is all you'll get, not a ripple overwrite.

### Ripple Trimming on Secondary Tracks

The Cut page's ripple editing works on secondary tracks too, but only where there's no underlying video on the primary video track (Track 1). Toggle this ripple behavior on or off with the Ripple On control in the Cut page timeline header.

Here the aim is to remove the selected clip and seal the gap, despite our clips sitting on a secondary track. Observe that the primary track (Track 1) holds nothing. With Ripple On switched off, removing a clip leaves behind a gap on the secondary track.

With Ripple On switched on, removing a clip seals the gap on the secondary track.

### Overwriting the Middle of Other Clips

Drag a clip in the Timeline or Upper Timeline across another Timeline clip so the pointer covers that clip, hold until your selected clip sits over the second clip, then release the mouse button. The target clip gets overwritten for the length of the clip you dragged and is split into two.

Dragging clip BB and pausing to overwrite part of clip DD

Clip BB relocates, writing over the middle of clip DD, which now sits in two pieces; the remainder of the Timeline slides left to fill the gap that moving clip BB opened in Track 1

### Overwriting The Edges of Other Clips

Drag a clip in the Timeline or Upper Timeline onto a neighboring clip's edge without letting your pointer overlap it, then drop the clip. The overlapped piece of that neighboring clip gets overwritten.

Dragging clip CC so it partly overlaps clip DD, with the goal of overwriting it

Once clip CC has been dropped to partly overwrite clip DD's start, clip DD becomes shorter and the Timeline's remaining clips shift left to seal the gap in Track 1

### Swapping Clips

Drag one or more clips from one spot in the Timeline or Upper Timeline to another so the pointer lands on an edit between two clips (the edit point goes purple), then drop. The clip(s) you dragged are now relocated and slotted in at the edit point you aimed for.

(Top) Dragging clip CC so as to swap it in between clip II and JJ. (Bottom) Once clip CC is dropped, the Timeline reorganizes, sealing every gap and pushing clips rightward as needed; superimposed clips stay synced to the Track 1 clips that shifted

### Copy, Cut, and Paste

Just as you'd handle words in a word processor, clips can be cut, copied, and pasted within the timeline or Upper Timeline to duplicate or relocate them. To cut/copy and paste in the Timeline: 1 Pick one or more clips in the Timeline. 2 Do one of these: a) Hit Command-C to copy them (the chosen clips stay put). b) Hit Command-X to cut them (the chosen clips vanish and the Timeline auto-ripples to seal the gap). c) Move elsewhere in the Timeline, then hit Command-V to paste. The clips land at the playhead frame, on the same track they came from, overwriting whatever clips already sit at that point in the Timeline.

### Splitting Clips

Any clip can be split into two pieces — effectively dropping an edit point at the midpoint — to set up moving one section of a clip, removing one section, slotting another clip in at that edit point, or putting some effect on a single section of a clip rather than the rest.

To split a clip: 1 Park the playhead on the clip frame where the split should occur. 2 Do one of these:

- Click the Edit Actions icon and pick split from the drop-down menu.
- Right-click the playhead's top handle and click the Split button that shows on

the radial menu.

- Press Command-Backslash.
- Click the Split Clips (scissor) icon at the far left of the Cut page Edit commands.

(Left) A clip prior to splitting, (Right) Afterward, a fresh edit point divides it into a pair of pieces

### Disabling and Deleting Clips

Clips you no longer need can be either disabled or deleted.

### Disabling and Muting Clips

You can switch off a Timeline clip's audio and/or video without removing the clip itself. This comes in handy when you want to use a clip's audio or video selectively, or when you'd like to disable both the audio and video of a clip you don't intend to use without removing it from the Timeline entirely in case you reconsider.

### Disabling Clips

Switch off a clip's video while keeping it in the Timeline by selecting it and pressing D, or by right-clicking it and clearing Enable on the contextual menu. The clip goes dull to signal it's disabled. Its audio keeps playing unless you mute it too.

### A disabled clip in the Timeline

### Muting Clips

Switch off a clip's audio while keeping it in the Timeline by right-clicking it and picking Mute on the contextual menu. A mute icon overlays the clip's start to signal the audio is off. Its video keeps playing unless you disable it too.

### A muted clip in the Timeline

### Deleting Clips

When you want one or more clips gone from the Timeline entirely, pick them and hit the Delete key. The clip(s) disappear. Delete a clip on Track 1 and the Timeline ripples to close the gap on its own.

### Selecting clip DD to delete it

Removing clip DD sends clips EE through NN sliding left to seal the Track 1 gap; superimposed clips travel along to stay synced with whatever sits beneath them

### Deleting Parts of Clips

To remove only part of one or more clips, place In and Out points around the Timeline section you want gone, then hit the Delete key. The stretch of Timeline between the In and Out points is removed. Delete part of a clip on Track 1 and the Timeline ripples to close the gap on its own.

Setting In and Out points to remove that stretch of the Timeline Once everything between the In and Out points is gone, every clip sitting right of the marked stretch slides left to seal the Track 1 gap

### Trimming Clips

You can also reshape your edited timeline in a hurry by resizing any clip's In and Out points, shifting the edit points between clips, and slipping a clip's contents.

### Resize Clips While Rippling the Timeline

In the Timeline or the Upper Timeline, move the pointer onto a clip's far left or right edge and it turns into a Resize icon, signaling that you can drag that clip's In or Out point to shorten or lengthen it, rippling every clip to the right along the Timeline to fit the clip's new length. As you drag, a tooltip reports how many frames you've shifted the clip plus its new duration. Meanwhile the audio scrubs along with the Resize cursor. Resize a clip in Track 1 and the rest of the edited timeline ripples automatically to absorb your changes, with clips right of the altered area sliding left to fill the gap of a deleted or shortened clip, or sliding right to make space for an inserted or lengthened one. Clicking clip DD's Out point in Track 1 Dragging inward to shorten clip DD ripples the Timeline, and a tooltip shows you the number of frames resized Moving or resizing a clip on Track 2 or higher touches only that one clip; the Timeline's other clips stay put and no rippling happens.

Clicking the out point of clip HH in Track 2

Dragging to lengthen the clip doesn’t ripple the Timeline

TIP: If you resize the Out point of a Track 1 clip that sits under a superimposed clip, and that superimposed clip's In point sits rightward of where the resized clip's In point is, then dragging the trimmed clip's Out point leftward past the superimposed clip's In point will delete that superimposed clip from the Timeline.

### Rolling an Edit

Any edit point dividing two clips — whether in the Timeline or the Upper Timeline — can be grabbed and dragged to “roll” it, which essentially resizes the outgoing clip's Out point together with the incoming clip's In point at once. This moves an edit point while leaving the overall timeline's duration unchanged. As you drag, a white overlay in the Timeline shows how much media is on hand for rolling (based on the handles available in the source media). Meanwhile the audio scrubs along with the right clip's In point.

### Clicking an edit between clips CC and DD

Dragging rightward rolls the edit forward, resizing both clip CC and clip DD at the same time

### Slipping Clip Content

Every clip in the Timeline carries a Slip handle at its center. Drag this handle to slip that clip's contents so a different stretch of media shows, all without altering the clip's position or duration, and without touching any other part of the Timeline. You can even pick several clips — two superimposed clips, say, or a run of consecutive clips — and slip them all together. As you drag, a white overlay in the Timeline shows how much media is on hand for slipping (based on the source clip's duration).

(Top) A click on a clip's slip handle, (Bottom) Dragging that slip handle so the stretch of media inside the clip changes

### Roll and Trim Audio Edit Points to Add Split Edits

On the Cut page you can trim a video clip's audio channel on its own. That lets you build a split edit (L-cut or J-cut), where one video clip's audio carries on beneath the video of a different clip. With this you can shape a scene's flow and rhythm through reaction shots and more natural-sounding dialogue.

To Trim Only the Audio and Build a Split Edit on a Cut Page Timeline:

- Enlarge the track on the Cut page by clicking the Enlarge Track icon at the left of the track header. It isn't strictly required, but it makes the tool's trigger point easier to hit and the audio waveform easier to see while you trim.
- Hover the pointer over the edit point in the track's lower audio area. Once the trim icon displays a musical note on its right, you can slide that edit point back and forth so only the clip's audio portion stretches forward or backward.
- The Trim View also shows in the Viewer as you edit, alongside enlarged audio waveforms zoomed to the frame level for accuracy.

Setting the pointer within the track's audio area brings up the trim indicator carrying the musical note icon. With it, you can slide only the audio edit point back and forth along the Timeline while the video stays put.

### Trim or Extend Clip to Playhead

Trimming or extending a clip to a precise length is simple: set the playhead on the Timeline right where the video should begin or end, then choose the matching operation by clicking the Edit Actions icon. To Trim or Extend Clip to Playhead:

- Set the playhead at the spot you want to either extend the clip to or trim the clip off at.
- Click the Edit Actions icon.
- Pick Trim Start to Playhead on the contextual menu to trim or extend the clip's left side to the playhead position.
- Pick Trim End to Playhead on the contextual menu to trim or extend the clip's right side to the playhead position.

The starting Timeline, its playhead landing between the second and third group of “BB’s,”

(Top) How the clip ends up after picking Trim Start to Playhead, (Bottom) How it ends up after picking Trim End to Playhead

### Trimming Edits in the Viewer
