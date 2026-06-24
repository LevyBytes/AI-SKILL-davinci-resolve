# Editing Basics In The Fairlight Page (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Focus mode acts as a Multi Tool built for quick pointer-driven selections and edits, paired with a range of commands — fired off through customizable keyboard shortcuts — for stretching and reshaping those selections. For anyone editing with a mouse and keyboard, the mode aims to keep you moving fast by lighting up assorted functions depending on which part of a Timeline clip you click. One more thing sets Focus mode apart: it alone lets you edit the Timeline mid-playback, something Pointer and Range modes won't allow.

- If no tracks have been selected: Make a selection with the hand and the Timeline In and Out points snap to that selection's edges. Make one with the crosshairs and the Timeline In and Out points snap to the edges of the region you dragged. Either way, whichever tracks hold the selected clips and clip regions get selected too.
- If tracks have been selected: Any clip on a chosen track that crosses the playhead lights up brightly on its own, while clips on de-selected tracks are passed over. Drag the crosshairs across one or more clips with the pointer and you override every automatic selection, grabbing instead the clip regions you drag over along with their tracks.
- If In and Out points have been set: Click the lower half of a Timeline clip to select that clip and its track, and the In and Out points shift to wrap around that clip.

To choose Range mode:

- In the toolbar, click the Range Selection tool — the crosshairs sitting at a track's bottom.
- Choose Trim > Range mode.
- The keyboard shortcut is pressing - R.

To grab a whole clip with Focus mode's Hand tool:

- Bring the pointer to a clip's lower half until the hand cursor shows, then click once to grab that whole clip.

Selecting a clip in Focus mode by clicking its lower half

- With the Hand, Command-click several clips to build either contiguous or noncontiguous selections.
- With the Hand, Shift-click several clips to build contiguous selections.

To grab a range with Focus mode's I-beam cursor:

- Bring the pointer to a clip's upper half until the I-beam cursor shows, then drag to select a region spanning one or more clips. The playhead trails the Out point as you drag.

Selecting a region in Focus mode by dragging across a clip's upper half

- With the crosshairs, Shift-click to widen or narrow the selected region across one or more clips.
- With the crosshairs, double-click to grab a whole clip.
- A partial edit selection holding a fade will copy along with that fade intact.

To grab a single frame with Focus mode's I-beam cursor:

- Bring the pointer to a clip's upper half until the I-beam cursor shows, then click once to drop a point selection on the frame you clicked. The playhead jumps to that frame as well.

Making a single-frame selection by clicking inside a clip's upper half

- With the I-beam cursor, Command-click clips on tracks above and below to fold them into the single-frame selection, all lined up on the same frame — handy, for example, for splitting several clips together. Single-frame selections can sit on tracks that aren't adjacent.

Command-clicking inside the upper halves of several clips across several tracks to drop single-frame selections all on one frame To reposition a selection with Focus mode's Hand tool: With a selection of one or more clips or regions made via the Hand or I-beam cursor of Focus mode, you can bring the pointer to the lower half of any selected clip and drag the whole selection somewhere else on the Timeline.

### Commands For Editing and Extending the Selection

With one or more selections made in the Timeline, a set of commands stands ready to tweak or grow that selection. They were conceived to pair with Focus mode, yet they function in any mode. Editing the Selection Six commands handle changing the current selection, carrying it from one clip or batch of clips in the Timeline to another. They shift only the selected span of clips/frames, never the clips themselves. You'll find them in the Timeline contextual menu under Edit Operations after right-clicking a clip.

- Move To Previous/Next Edit: Carries the current selection to the neighboring clip/edit point on the left or right in the Timeline.
- Move To Previous/Next Track: Carries the current selection to the adjacent track above or below in the Timeline.
- Move to Previous/Next Frame: Bumps the current selection left or right in the Timeline.

Extend Edit Selection Four commands grow what's selected in the Timeline, a single clip or track at a step. You'll find them in the Timeline contextual menu under Edit Operations after right-clicking a clip.

- To Previous Edit: Stretches the selection to take in the clip just to its left in the Timeline.
- To Next Edit: Stretches the selection to take in the clip just to its right in the Timeline.
- To Previous Track: Stretches the selection to take in the clip on the track just above in the Timeline.
- To Next Track: Stretches the selection to take in the clip on the track just below in the Timeline.

### Locking Audio Tracks

A further bit of prep ahead of any editorial operation is locking the tracks whose media you'd rather your next move not disturb. Say track A3 carries an intricate set of music edits you don't want touched by an operation that deletes overlapping media — lock track A3 and those clips stay safe.

### Locking an audio track

Clips sitting on locked tracks can't be moved, deleted, cut, or otherwise touched by editorial operations, and their parameters are off-limits in the Inspector as well. They can, however, still play back and mix just like any other audio clips. To flip audio tracks between locked and unlocked on the Fairlight page, do one of the following:

- Click a track's lock control to switch its lock on or off.
- Click a track's lock control and drag across the lock controls of other Timeline tracks to lock or unlock a run of adjacent clips fast.
- Open the Index and click or drag one or more track lock controls to switch lock on or off.

### Splitting Clips

Beyond splitting timeline clips by hand in Pointer or Range mode, Fairlight gives you two more ways to wrangle your timeline audio. Those are Remove Silence and AI Checkerboard to New Tracks, which together with AI Create ADR Cues make up the Intellicut feature set.

For a fuller account of AI Create ADR Cues, turn to “ADR (Automated Dialog Replacement)” over in Chapter 174.

### Remove Silence (Studio Version Only)

This feature spots the silent stretches within a timeline clip and strips them out non-destructively, making your workflow leaner.

### Audio clip with silence indicators

### Remove Silence Parameters

- Threshold: Fixes the loudest audio level (in dB) still counted as silence. Anything beneath that level is judged silent and cut, so raising the threshold removes more audio.
- Pre Head: Sets how much silence, or pre-roll, sits ahead of each audible section.
- Minimum to Strip: This parameter sets the shortest span of silence (in milliseconds) that gets

be stripped from selected timeline clips.

- Bigger figures leave more silent patches in place. Smaller ones strip more, though you may notice some of the leftover audio sounding “chopped up” where it cuts off abruptly.
- Fade Head and Tail: Tick this checkbox and fades go onto the start and end of every surviving clip, sized by the Pre Head and Post Tail values.

### Remove Silence dialog

To remove silences from a timeline clip: 1 Pick a clip or a group of clips on a track. 2 Right-click that selection and pick Remove Silence from the contextual menu. 3 The selected audio's look shifts, gaining vertical red stripes that mark where the resulting silences fall and how long they run, according to the parameter values set in the Remove Silence dialog.

### AI Checkerboard to New Tracks (Studio Version Only)

Suppose several actors were captured by one boom mic on a single track and you need them split apart: this feature studies and transcribes the original audio, then sorts the resulting clips onto a dedicated track for each voice. To break speakers out onto fresh tracks: 1 Right-click the timeline clip, or a range within it, and pick AI Tools > Checkerboard to New Tracks from the contextual menu.

AI Tools contextual menu

2 As the Transcribing Audio dialog appears, Fairlight leans on AI to examine the audio and pick out each voice.

Transcribing Audio dialog 3 Every speaker gets a fresh track holding their new clips, while the original timeline clip is muted and kept whole.

### New track timeline clips for each speaker

NOTE: Recoloring the new timeline clips and tracks and timeline clips can be a handy way to keep them straight.

To learn how to recolor a timeline clip, see “Changing Clip Color in the Timeline” further along in this chapter. To learn how to recolor a track, consult “Using the Fairlight Page” at Chapter 170.

### Manually Split Clips in Pointer or Range Mode

To split one or more clips while in Pointer or Range mode: 1 Pick every track that holds a clip you intend to split. 2 Park the playhead across those clips on the precise frame where the split should fall. 3 Take either route: a) Use the Timeline > Split Clip menu item, or its shortcut Command-\ (backslash). b) Reach instead for Timeline > Razor, or hit Command-B. Split a clip on the Edit page and a through edit shows up, signaling that you now have an edit whose timecode runs unbroken from the outgoing half into the incoming one. That through edit is drawn on the Edit page with a dotted line along its edge to flag it as special. As of this writing, the Fairlight page doesn't render through edits.

### Linked Clips in the Fairlight Page

The Fairlight page lets you bind clips together. Once clips are linked, Fairlight's editing commands handle the whole set as though it were one clip — whatever you'd do to a lone clip happens to every linked clip together. Selecting any member of a linked clip selects all of them, and editing the In point of one member edits every one. To bind two or more clips: 1 Pick all the clips you want joined. 2 Right-click one of those selected clips and pick Link Clips from the contextual menu. A link indicator at the lower left of each newly linked clip signals their fresh linked status.

### Trimming Clips Without Rippling the Timeline

On the Fairlight page, most everyday adjustments touch only the selected clip or region of the Timeline. Whatever lies to the right of the adjusted area usually stays put, so sync isn't thrown off when you least expect it. What follows covers the foundational pieces of the Fairlight page's “seven-point editing” paradigm.

### Multi-Point Editing Overview

Every Timeline clip carries a handful of draggable handles and click targets that let the pointer carry out different editing chores.

- In point: Drag the clip's left edge to resize where the clip begins.
- Out point: Drag the clip's right edge to resize where the clip ends.
- Fade In handle: A handle in the clip's top-left corner that surfaces only while the

mouse hovers over that clip; drag it rightward to fade the audio in, or use it as one side of a crossfade between two audio clips. Double-click the fade handle to reset (clear) the fade.

- Fade In curve: A handle at the midpoint of the Fade In curve, visible only once the curve is exposed, for shaping the fade-in's strength. Drag it up or down to change the fade's X-Level, and left or right to change its X-Point. Double-click the curve handle to reset a fade curve.
- Fade Out handle: A handle in the clip's top-right corner that surfaces only while the mouse hovers over that clip; drag it leftward to fade the audio out, or use it as one side of a crossfade between two audio clips. Double-click the fade handle to reset (clear) the fade.
- Fade Out curve: A handle at the midpoint of the Fade Out curve, visible only once the curve is exposed, for shaping the fade-out's strength. Drag it up or down to change the fade's X-Level, and left or right to change its X-Point. Double-click the curve handle to reset a fade curve.
- Level: Treated as an editorial trait, any audio clip's level is adjustable through a level overlay stretching across the clip. Double-click that overlay to send the level back to its default 0.0 dB.
- Position: Click anywhere in a clip's middle in Pointer or Range mode, or along the bottom in Focus mode, and you can drag the clip earlier or later in time, or onto another track.

### Resizing the In and Out Points of a Clip

On the Fairlight page, trimming a clip's head or tail amounts to resizing its In or Out point, lengthening or shortening the clip to suit. To resize the beginning or end of a clip:

- To shorten or lengthen clips: Hover the pointer over a clip's start or end, and once it becomes the Resize cursor, drag the In or Out point left or right to alter the clip's length. While you drag the In or Out point of a Fairlight-page audio clip, an overlay pops up showing the waveform of every available frame at the head (when you drag the In point) or the tail (when you drag the Out point) of the clip being resized.

The overlay that shows up while you resize a Fairlight-page audio clip's In point To snap a clip's start or end straight to the outermost edge of its available media:

- Double-click the clip's In point to snap that In point to the very start of the clip's media.
- Double-click the clip's Out point to snap that Out point to the very end of the clip's media.

Resize a clip's In or Out point so it laps over one or more neighboring Timeline clips, and the overlapping stretches of those neighbors get overwritten by the clip you just resized.

### Trim Start and Trim End

The Trim > Trim Start (Shift-[) and Trim End (Shift-]) commands shift the In or Out point of every clip the playhead crosses; in Trim mode that happens as a ripple, while in Selection mode it happens as a resize. Since neither one needs a selection first, they're quick to reach for in the right moment. A textbook job for Trim End is a stack of superimposed clips of varying lengths that you want lined up to start or end together.

- Trim Start resizes or ripples — whichever your mode dictates — all clips crossing the playhead, dragging each clip's In point to the playhead's current spot.
- Trim End resizes or ripples the crossing clips so each one's Out point lands at the playhead's current spot.

Clips the playhead never crosses go untouched. You can also keep clips on certain tracks out of the operation by locking those tracks.

### Trim to Selection

The Trim > Trim to Selection (Shift-Command-T) command lops off the heads and tails lying outside a selection of one or more clips in one stroke, leaving just the selection behind. You'll find it in the Timeline contextual menu after right-clicking a clip.

(Left) a selection spanning parts of two clips; (Right) what Trim to Selection leaves once the heads and tails beyond that selection are cut away.

### Moving and Overwriting Clips

There's more than one way to relocate clips in the Timeline. A clip can be nudged or dragged within its track to retime where it sits in the edit, or it can be shifted up or down onto other tracks. To reposition Timeline clips, take any of these routes:

- To move one or more selected clips in the Timeline: Drag any Timeline clip wherever you like. In Focus mode you have to drag from the lower half of the selection. Drag a clip so it laps another, and the clip you're dragging overwrites the one beneath.
- To frame-nudge selected clips from the keyboard: Make a selection, then tap the Comma key to roll the edit one frame left or the Period key to roll it one frame right. Shift-Comma and Shift-Period jump by 5 frames.
- To shift selected clips onto tracks above or below all at once: Make a selection, then keep Shift held as you drag one of those clips up or down the Timeline, which pins their timing while they cross to other tracks. Alternatively, hold Option and press the Up or Down Arrow.

### Sync Offset Indicator

When a Fairlight-page audio clip drifts out of sync with the video item it's linked to, the clip shows an “out-of-sync” or sync offset indicator.

### Snap to Playhead

In Focus Mode, you can pin an audio clip's head (beginning) or tail (end) to wherever the playhead sits (the destination). That comes in handy for matching audio to an onscreen moment, like a ball shattering a window. The “Automation follows edit” option does cooperate with this, but keep a few points in mind:

- It still works even when the playhead is off the visible screen.
- A clip can only be snapped one at a time, and only to a spot on the same track.
- A “snapped” clip overwrites whatever audio already lives at the destination, even when that audio sits on a layered clip's

top layer.

- A set of clips on one track, picked in Range mode by the playhead position, can serve as a destination as well.

That said, you'd want to snap the clip toward the side of the playhead free of any existing audio you mean to keep. For more information Range Mode, see “Using Range Mode.”

To pin a clip's head onto the playhead: 1 Turn on Focus Mode and park the playhead at the destination you want. 2 Hold Command-Option and click the clip you'd like to move. The Audio now sits in its new spot with the clip's head pinned to the playhead. To pin a clip's tail onto the playhead: 1 With Focus Mode running, park the playhead at the destination you want. 2 Hold Command-Option-Control and click the clip you'd like to move. The Audio sits in its new spot with the clip's tail pinned to the playhead.

### Subframe Nudging

Within the Preferences/User/Editing panel, under General Settings, you can set the Fairlight page's nudge amount in either subframes or milliseconds. Both are fully user-definable, so just type the nudge amount you want into the matching box. Take the time to explore this whole settings panel, since it holds pre-roll and post-roll settings along with other handy Fairlight tweaks.

### Slipping

Once known as re-syncing, slipping an audio clip leaves the clip parked where it is in the Timeline while swapping out the stretch of media shown there. A slip edit alters neither the overall Timeline's length nor the clip's place relative to its neighbors; all it changes is the range of media the clip stands for. NOTE: Though earlier versions of Fairlight offered it, slipping isn't available as of this writing.

### Duplicating Clips

The Duplicate Selection command copies one or more selected clips and drops the copies right after the selection's Out point. When you duplicate a region of a clip that has tails, or a clip wedged between others, the duplicate overwrites whatever sits to the right of the current selection for as long as the copy runs.

Using the Duplicate Selection command to duplicate a selected region Hold Option while dragging a Timeline clip and you'll drop a duplicate of it at the spot where you release.

### Option-dragging to duplicate a clip in the Timeline

### Disabling and Re-Enabling Clips in the Timeline

Now and then a Timeline holds one or more audio clips you'd rather not play with the rest of the edit, yet you don't want to toss them out either in case you reconsider down the line. That's why you can disable clips, switching them off without deleting them. Earlier Fairlight versions called this Mute clip. A disabled clip dims in the Timeline — it won't play, won't render, and won't reach the video output — but its place in the Timeline is kept, so you can re-enable it whenever you decide you want it after all. Disabled clips show up gray in the Timeline. To disable or re-enable one or more selected clips:

- Right-click part of the selection and pick Enable Clip from the contextual menu.
- Choose Clip > Enable Clip.
- Press D.

### Deleting Audio Clips and Regions

Any selected clips or clip regions can be removed in either Pointer or Range mode by hitting the Delete key, or by right-clicking a clip and picking Delete Selected from the contextual menu. On the Fairlight page, a deletion leaves a gap by default. Through the Edit Menu > Ripple Delete you can ripple delete the selected clips, which reshuffles where every following clip lands.

### Cut, Copy, and Paste

The Fairlight page brings its own approach to copy and paste, built around the “ghost” overlays that stand in for the waveforms of selected audio clips. The approach makes copying and pasting clips simple via keyboard shortcuts and the JKL keys.

### Conventional Cut, Copy, and Paste

The familiar cut, copy, and paste commands every application offers are present on the Fairlight page too, but with a distinctive twist that especially rewards users of the Fairlight control surface, or anyone driving the Timeline through the JKL transport-key shortcuts for keyboard-led editing. To cut, or copy, and then paste a clip in whole or in part: 1 For a whole clip, switch to either Selection (press A) or Range Selection (press R) mode. For only part of a clip, be sure you're in Range mode (press R).

2 To build a clip selection with the playhead, first select the track holding the clip you intend to copy or cut. When one or more tracks are already selected, the Control-Option-Up or Down Arrow shortcuts shift the track selection up or down onto the track carrying the clip you're after.

Picking the track that carries the clip you want to cut 3 Take either route: a) For a whole clip, slide the playhead until it crosses the clip you want to cut or copy. Should the playhead cross a clip on a selected track, that clip ought to become selected. Note that even when you click a clip with the mouse before selecting a track, you should still run the playhead across the clip you're copying or pasting, since that establishes a key reference point for the operation. b) For a segment of a clip, slide the playhead until it crosses the clip you want to cut or copy. Should the playhead cross a clip on a selected track, that clip ought to become selected. Then, with JKL plus the I (In) and O (Out) keys, mark out a Timeline range covering the segment you want, and that segment should highlight as a result.

Using In and Out points to cut or copy one segment of a clip
