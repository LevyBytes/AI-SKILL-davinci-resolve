# Modifying Clips In The Timeline (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Modifying Clips in the Timeline

After a mix of clips has been assembled into the Timeline, the next phase is reworking them while you polish the cut. This chapter walks through straightforward ways to alter clips: changing their size, cutting them apart, reshuffling their order, switching them off, duplicating, and using copy and paste.

### Keyboard Shortcuts in This Chapter

Below is a set of keyboard shortcuts tied to the subjects covered here that may prove useful.

| Key Shortcut                     | Function                                                                                                                   |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| A                                | Selection tool/mode                                                                                                        |
| V                                | Grab the edit closest to the playhead                                                                                      |
| Shift-V                          | Grab the clip that the playhead is over                                                                                    |
| U                                | Grab the incoming, outgoing, or middle portion of an edit                                                                  |
| Option-U                         | Cycle the selection through video+audio, video alone, and audio alone                                                      |
| Up, Down Arrow Keys              | Shift the selection to the prior/following edit or clip                                                                    |
| Comma, Period                    | “Nudge” keys that shift a chosen edit or clip one frame to either side                                                     |
| Shift-Comma, Period              | “Fast Nudge” keys that shift a chosen edit or clip 5 frames to either side (customizable)                                  |
| Shift-Left, Right Bracket ([, ]) | Trim Start to Playhead and Trim End to Playhead, which crop a clip where the playhead sits                                 |
| E                                | Extend edit, which pulls a chosen edit point over to the playhead                                                          |
| B                                | Razor blade tool that drops cuts onto clips with the pointer                                                               |
| Command-Backslash (\)            | Insert edit; drops a cut into the clip(s) wherever the playhead is positioned                                              |
| Delete                           | Delete a clip while keeping the gap (lift edit)                                                                            |
| Forward Delete                   | Ripple delete; removes a clip and pulls everything to its right leftward to close the gap                                  |
| N                                | Switch timeline snapping on or off                                                                                         |
| Command-Shift-L                  | Switch linked selection on or off                                                                                          |
| Command-D                        | Change clip duration                                                                                                       |
| Command-Shift (modifier)         | Holding Command-Shift during a drag lets you “shuffle” or “swap” clips forward or backward to reorder them in the Timeline |
| D                                | Disable/Enable the chosen clips                                                                                            |
| Command-X                        | Cut the chosen clips while keeping a gap                                                                                   |
| Command-Shift-X                  | Ripple cut the selection; seal the gap the cut clip(s) leave behind                                                        |
| Command-C                        | Copy the chosen clips                                                                                                      |
| Command-V                        | Paste clips                                                                                                                |
| Command-Shift-V                  | Paste insert clips                                                                                                         |

### Moving, Resizing, and Rolling Clips in Selection Mode

Once you’ve dropped a run of clips into a timeline, even the most meticulous editor will soon need to begin adjusting things. The easiest of those adjustments happen in Selection Mode with the ordinary arrow pointer.

The Selection Mode button on the left is active, while the Trim mode button on the right is off. This is the mode you land in by default whenever DaVinci Resolve opens, and it lets you relocate clips elsewhere in the Timeline, stretch or shrink their length, and roll the edit points sitting between a pair of clips so the edit lands earlier or later on the Timeline. Exactly what this tool accomplishes hinges entirely on whatever you click to select while you work. Handling clips with the mouse: 1 Click the Selection Mode tool (the arrow), or hit A. 2 Carry out one of these: To relocate clips in the Timeline: Drag any clip somewhere else in the Timeline. Should you drag a clip so it overlaps another, the clip in your hand writes over the one you drop it on top of.

Dragging a clip across the Timeline to write over part of a neighbor; a tooltip reports the frame count you’ve shifted To shift clips up or down onto other tracks in the Timeline while holding their timing steady: Keep the Shift key pressed as you drag clips up or down through the Timeline. Alternatively, press and hold Option and tap the Up or Down Arrow.

Sending a clip onto a different track without nudging its timing by keeping Shift pressed To trim or extend clips: Hover the Selection Mode pointer over a clip’s start or finish, and once it becomes the Resize cursor, drag the In or Out point either way to alter the clip’s length. While you do this, the audio scrubs together with the Resize cursor.

Shrinking a clip in the Timeline so a gap opens up; a tooltip reports the offset, while outlines reveal how much media remains in the clip you’re tweaking To roll any edit: Hover the Selection Mode pointer over any edit point, and once it becomes the Roll Edit cursor, drag it either way to relocate the edit point while at the same time reshaping the outgoing and incoming edit points of the two clips on each side. While you do this, the audio scrubs along with the In point of the clip on the right.

Rolling an edit; a tooltip reports the offset, while an outline marks the range within which rolling is possible

Handling clips with the keyboard: 1 Hit A to switch into Selection Mode. 2 Carry out one of these:

- To roll any edit step by step: Grab the edit point nearest the playhead with the V key, shifting the selection onto a different edit when needed via the Up Arrow and Down Arrow keys. After that, press Comma to shift it a single frame leftward, or Period to shift it one frame the other way, rolling the chosen edit. Add Shift to either key (Shift-Comma, Shift-Period) and the jump becomes 5 frames.
- To roll any edit with the playhead: Grab the edit point nearest the playhead with the V key, shifting the selection onto a different edit when needed via the Up Arrow and Down Arrow keys. After that, drive the playhead with the JKL keys to whichever frame you want the edit moved to, then hit E for an “extend” edit.
- To trim or extend clips step by step: Grab the edit point nearest the playhead with the V key, then flip the selection between the tail of the outgoing clip and the head of the incoming one using the U key. Next, press Comma to pull that side a single frame leftward, or Period to push it one frame the opposite way, trimming or extending it. Shift one end of a clip far enough to overlap a neighbor and the clip in motion writes over the one beside it. Holding Shift with either key (Shift-Comma, Shift-Period) moves 5 frames at a go. Under Selection mode, this either opens a gap or overwrites the adjacent clips.
- To trim clips with the playhead: Drive the playhead via the JKL keys onto the frame in the Timeline where you’d like a fresh In or Out point for that clip, then hit Shift-Left Bracket ([) for “trim start,” or Shift-Right Bracket (]) for “trim end.” You don’t need a selection. Under Selection mode, this opens a gap.
- To extend clips with the playhead: Grab the edit point nearest the playhead with the V key, then flip the selection between the tail of the outgoing clip and the head of the incoming one using the U key. Next, drive the playhead via the JKL keys to the frame you’d like that edit point pushed out to, then hit E for an “extend” edit. Under Selection mode, this overwrites the adjacent clips.
- To shift clips earlier or later in the Timeline: To pick a clip ahead of moving it, either click it, or run the Spacebar or JKL keys to park the playhead over it and hit Shift-V. After that, press Comma to slide the clip a single frame leftward, or Period to slide it one frame the other direction. Move a clip far enough to overlap another and the clip in motion writes over the one beside it. With Shift held, either key (Shift-Comma, Shift-Period) jumps 5 frames. Under Selection mode, this opens a gap.
- To shift clips up or down onto other tracks: To pick a clip ahead of moving it, either click it, or run the Spacebar or JKL keys to park the playhead over it and hit Shift-V. After that, press Option-Up Arrow to send that clip’s Video and Audio onto the next higher‑numbered track, or Option-Down Arrow to send the Video and Audio onto the next lower‑numbered track.

TIP: Keep Shift pressed as you nudge a selection to perform a “fast nudge.” How far a fast nudge travels can be set in the Editing panel of the User Preferences. The default sits at five frames, though you’re free to dial in any value.

### Trimming Gaps

Where a gap begins and ends can likewise be rippled with the Trim tool.

### For more information, see Chapter 44, “Trimming.”

Employing the Trim tool to ripple a gap’s Out point so it shrinks

### Modifying Clip Duration Via Timecode

There are two numeric routes to adjusting a clip’s duration. To adjust a chosen clip’s duration: 1 Decide first whether altering the duration should ripple the Timeline or write over the adjacent clips. To ripple the Timeline, pick the Trim tool. To overwrite the neighbors or open a gap, pick the Selection tool. 2 Carry out one of these:

- Highlight a clip, then go to Clip > Change Clip Duration.
- Right-click whichever clip in the Timeline you like and pick Change Clip Duration out of the contextual menu. 3 Once the Edit Duration Change dialog opens, type a fresh duration into the Timecode field and click Change.

For further detail on entering timecode, consult “Moving the Playhead Using Timecode” in Chapter 35, “Preparing Clips for Editing and Viewer Playback.”

A dialog used to revise how long a Timeline clip runs

### Resizing or Trimming Clips in the Source Viewer

A clip can additionally be sent from the Timeline into the Source Viewer so you can trim it by other means. Two approaches accomplish this:

- Double-click whichever Timeline clip you want and it opens up in the Source Viewer.
- Park the playhead over a Timeline clip, hit Shift-V to grab that clip, and then press the

Return or Enter key to load it into the Source Viewer. After a clip lands in the Source Viewer, that Viewer takes focus, which lets you run the Spacebar or JKL commands to steer the playhead through the Viewer as you make edits. Whether those edits ripple the Timeline turns on which tool you’re holding — the Selection tool or the Trim tool. TIP: To pull up a match frame of a Timeline clip with the pointer instead, keep Option pressed while you double-click a clip.

### Using the Selection Tool

With the Selection tool active, you’re free to drag the In and Out markers, or lean on the playhead together with the I and O keyboard shortcuts to resize that clip back in the Timeline.

A Timeline clip loaded into the Source Viewer, where dragging its out point resizes the clip and opens a gap (red arrows).

### Using the Trim Tool

With the Trim tool active, dragging the In and Out points — or placing fresh ones via the I and O keys — resizes the clip and ripples the Timeline left or right as required.

### Doing a Slip Edit in the Viewer

Keep Shift pressed as you drag the In or Out point of a timeline clip loaded in the Source Viewer, and both the In and Out points travel as a pair, producing a slip edit of that clip’s content within the Timeline. Either the Selection or the Edit tools can do this.

### Shuffle/Swap Insert Edits

A Shuffle Insert edit (occasionally called a Swap Insert edit) gives you a quick way to reorder one or several chosen clips in the Timeline just by Command-Shift dragging them left or right. As you do, the clips on either side slide right or left on their own to trade positions with whatever you’re dragging. It’s a remarkably fast method for reordering clips while testing different layouts, and you never have to first park clips on extra tracks to clear them out of the way. There’s plenty of latitude in how the shuffling works. You may pick a single clip or a run of consecutive clips to shuffle. Choose several consecutive clips and they travel together as one block. You can even grab several consecutive clips spanning multiple tracks and shuffle them around the Timeline as a single object. On top of that, you can select clips belonging to split edits, where the audio and video In and Out points begin or finish on different frames. Here, how the other clips reposition themselves in the Timeline to clear room for the split-edit clip you’re dragging hinges on whether you grabbed the video or the audio half of the clip to begin the drag:

- Grab and drag the video half of the clip, and every clip reshuffles around the length of that video item on its track, letting all the video items on that track reorganize themselves without writing over one another or opening gaps. While you drag the selection through the Timeline, any overlapping linked audio items will either overwrite the audio on the clips beside them or open a gap.
- Grab and drag the audio half of the clip, and every clip reshuffles around the length of that audio item on its track, letting all the audio items on that track reorganize themselves without writing over one another or opening gaps. While you drag the selection through the Timeline, any overlapping linked video items will either overwrite the video on the clips beside them or open a gap.

With those rules in mind, shuffling clips becomes quite simple, and there are two ways to go about it. To shuffle insert clips alongside their neighbors in the Timeline: 1 Switch snapping on. 2 Pick one or more consecutive clips to shuffle. 3 Hold down the Command and Shift keys and drag the video or audio half of the chosen clips left or right.

Provided you bring clips up to the In or Out points of their neighbors, those neighbors will trade places with the dragged selection on their own. Snapping helps keep the clip(s) you’re dragging lined up with edit points that already exist until you release them in the spot you want.

Before and after clip L gets shuffled among clips I, K, and J in a scene to reorder the sequence To shuffle insert a single clip into its neighbors in the Timeline: 1 Switch snapping off. 2 Pick one or more consecutive clips in the Timeline to shuffle. 3 Hold down the Command and Shift keys and drag the video or audio half of the chosen clips left or right. 4 With snapping off, the selection you’re dragging slots more readily into the middle of the adjacent clips, and the cut piece of each clip slides into the gap the dragged clip(s) leave behind. Release the clip at the spot you want once you’re done.

Before and after clip L gets dropped into the middle of Clip K, which splits in two to make room for it To shuffle insert several clips to another spot in the Timeline: 1 Pick every clip you want relocated to another spot on the Timeline. 2 Hold down the Command and Shift keys and drag the clips left or right. Be sure the item you click to drag sits on the same track as most of the clips you’re reordering; the item you click sets which track governs how the clips get reordered. In the example below, the video item of Clip C is chosen on track V1, so as it’s dragged rightward, the clips on every other track reorder themselves to match the length and placement of clips B and C on track V1. Consequently, clips on tracks apart from V1 may be overwritten or may open gaps, whatever it takes for the items on track V1 to reorder cleanly.

Before and after a batch of clips gets shuffled leftward; the clip you clicked to drag dictates how all the others reorder themselves To shuffle insert several clips, sourced from the Media Pool (or from the Source Viewer), down into the Timeline: 1 Either pick one or more clips sitting in the Media Pool, or load a single clip up in the Source Viewer. 2 Hold down the Command and Shift keys, then drag that selection — whether out of the Media Pool or straight from the Source Viewer — down onto the Timeline. 3 During the drag, each moving clip settles onto the Timeline right where the pointer happens to be. Let go of the mouse to complete the edit.

### Splitting and Joining Clips

There are plenty of moments when you’ll wind up splitting clips (adding edits) so as to break apart several clips that got accidentally fused into one, or to chop clips into segments you intend to treat with separate effects or grade differently. Ways to split and join clips:

- To split a clip a single time: Drag the playhead onto the frame where the split should land, then hit Command-Backslash (\) to cut every clip on a track whose Auto Select is on.
- To split a lot of clips: Click the Razor Edit mode button (or hit B), then click clips in the Timeline to split as many of them as you please.

TIP: Applying the Blade Edit Mode or the Split Clip command to a clip that’s already selected keeps the selection on the front half of the clip once the cut is made.

### Through Edits

Splitting a clip produces a through edit, signaling that the edit you’ve just made carries continuous timecode from the outgoing half into the incoming half. Such an edit is known as a through edit, and it’s marked by a dotted line tracing its edge so its special nature is obvious.

### A through edit seen in the Timeline

To get rid of a through edit, carry out one of these:

- Highlight it in the Timeline and tap Delete.
- Right-click a through edit within the Timeline and pick Delete Through Edit.

TIP: To view a standalone roster of every through edit in the Timeline, open the Edit Index and pick “Show Through Edits” from the Edit Index Option menu. Click any entry in the roster and the playhead leaps to that through edit, which makes it simple to review all the through edits in a timeline and judge whether each is needed.

### Enabling and Disabling Clips and Tracks

While working in the Timeline, you’ll run into moments where you’d like to switch off clips that shouldn’t show up during playback, yet you don’t actually want them gone from the edit. As an instance, a client’s notes might lead you to turn off superimposed clips placed as insert shots partway through a scene, though you’d rather not delete those clips in case the client reverses course.

### A disabled clip oµn track V2

For a different case, suppose you’ve cut a run of titles onto track V3 and now must switch off the whole of track V3 to deliver a textless version of the film. Once a clip or track is switched off, the clips inside it look dimmed, those disabled clips stay out of the Color page, and they won’t go out to tape or render to disk in the Deliver page until that track is switched back on first.

Track V3 has been switched off, which renders the Timeline textless To switch one or more clips on or off in the Timeline:

- Pick one or more clips, then right-click the selection and tick or untick Enable Clip in the contextual menu, or hit D to flip a clip’s enabled state.

To switch a whole track on or off:

- Click the track enable button.

Over in the Edit page, a number of the Track Header controls — among them Auto Track Selection, Visibility, and Lock Track — can all be set in one pass: click an icon and drag the pointer up or down across the track headers. The catch is that only a single kind of control responds at a time, and the sweep won’t cross between Audio and Video tracks.

Click the Lock icon on A1 and then drag the pointer down to A3, and every audio track in that span gets locked.

### Copying and Pasting Clips in the Timeline

There are numerous ways to cut, copy, and paste clips through the usual keyboard shortcuts. Cutting or copying can act on a single clip or a group of several, and you’re also free to copy or cut only the video or only the audio media of a clip. When it’s time to paste, you can drop the result into the same timeline, or into a different one if your goal is to move media across timelines. Ways to perform a basic cut, copy, and paste:

- To cut one or more clips and leave a gap behind: Build a selection, then go to Edit > Cut (Command-X). The chosen clip or clips disappear from the Timeline and sit in memory ready for pasting.
- To ripple cut one or more clips and ripple the Timeline shut over the gap: Build a selection, then go to Edit > Ripple Cut (Command-Shift-X). The chosen clip or clips leave the Timeline and wait in memory for pasting. Every clip on a track with Auto Select on ripples leftward to seal the gap the cut clips leave.
- To copy one or more clips: Build a selection, then go to Edit > Copy (Command-C). The chosen clip or clips remain in the Timeline while copies are held in memory for pasting.
- To paste one or more clips back onto the same track: Park the playhead at the frame where the pasted selection should begin, then go to Edit > Paste (Command-V). By default each copied clip lands on the very track it came from.
- The pasted clips appear wherever the Playhead sits.
- The pasted clips write over whatever clips on that track stand in their path.
- The pasted clips arrive already selected, set for nudging in either direction or for whatever else you need.
- To paste one or more clips onto a different track: Sending clips to another track calls for a slightly altered approach. Park the playhead at the frame where the pasted selection should begin, then either Option-click any vacant spot on the destination track or Option-click that track’s Auto Select control to solo it, and afterward go to Edit > Paste (Command-V).
- The pasted clips appear wherever the Playhead sits.
- The pasted clips write over whatever clips on that track stand in their path.
- Once dropped, the pasted clips come up pre-selected, primed for nudging side to side or any further operation.

### Paste Insert

There’s a second paste command, Edit > Paste Insert (Command-Shift-V), which drops clips you cut or copied in as an insert edit, adding an edit at the playhead among the clips already sitting in the Timeline, while everything to the right of the playhead ripples even farther right to clear space for the clip or clips coming in. Just like every other ripple edit, this touches only the clips on tracks whose Auto Select control is switched on. The pasted clips arrive already selected, set for nudging in either direction or for whatever else you need.

### Cut/Copy/Paste of Partial Clip Segments Using In and Out Points

As a default, pasted clips drop in at the playhead position. The Timeline’s In and Out points give you several ways to cut and copy just part of a longer clip. It’s an invaluable trick for detailed audio and dialog work, though it serves equally well for copying partial chunks of any clip in the Timeline. IMPORTANT: Before In and Out points will work for pasting, you have to head to Preferences > User > Editing first and tick the box “Prioritize pasting to the in and out range.”

To cut or copy a portion of a clip for pasting somewhere else: 1 Place In and Out points to fence off the part of the clip you mean to cut or copy. While doing so, the Auto Select controls let you take in or leave out clip segments on particular tracks. 2 For that clip segment, press Command-X if you’re cutting it, or Command-C if you’re copying. 3 Wipe the In and Out points with Option-X. If you skip this, the segment will simply paste straight back where it began. 4 Park the playhead on the Timeline frame where the pasted clip should start, then run the Paste or Paste Insert commands to drop the segment there. Once positioned, the pasted clips come up pre-selected, primed for nudging side to side or any further operation. In and Out points can likewise let you paste only a slice of a far longer clip you’ve cut or copied. To paste just a part of a clip: 1 Pick a clip and hit Command-X to cut or Command-C to copy it. 2 Place In and Out points to mark out the Timeline region you intend to paste into. 3 Run the Paste or Paste Insert commands to lay down only as much of the Cut or Copied clip as fits between the In and Out points you set. Once positioned, the pasted clips come up pre-selected, primed for nudging side to side or any further operation.

### Copying and Pasting Clips to a Different Track

When every track has its Auto Select control switched on, clips always return to the same track they were copied from, beginning at the playhead’s spot. That’s handy in the many cases where you keep copying and pasting clips you want repeated, particularly during audio editing. But if your aim is to paste the cut or copied clips onto an entirely different track, you’ll need the Auto Select controls to designate which track receives them. The rules go as follows:
