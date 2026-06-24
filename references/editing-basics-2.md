# Editing Basics (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- To select one clip: From the keyboard, confirm that the Source Track Selector button is on for whichever track holds the clip, position the playhead above that clip, and then press Shift-V.
- To select a clip using keyboard navigation: While holding the Command key, tapping the Up, Down, Left, and Right Arrow keys lets you jump the selection to clips on the tracks above and below, as well as those to either side, without regard to where the playhead sits.
- To select all clips forward of the playhead on the current track: Position the playhead over the first clip you'd like in your selection, then hit the Y key (Timeline > Select Clips Forward > On This Track), which grabs that clip plus everything to its right on the same Timeline track.
- To select all clips forward of the playhead on all tracks: Position the playhead over the first clip you'd like to include, then hit Option-Y (Timeline > Select Clips Forward > On All Tracks), which grabs that clip along with everything to its right across every Timeline track.
- To select all clips backward from the playhead on the current track: Position the playhead over the final clip you'd like in the selection, then hit Command-Y (Timeline > Select Clips Backward > On This Track), which grabs that clip plus everything to its left on the same Timeline track.
- To select all clips backward from the playhead on all tracks: Position the playhead over the final clip you'd like included, then pick Command-Option-Y (Timeline > Select Clips Backward > On All Tracks), which grabs that clip along with everything to its left across every Timeline track.
- To select all clips in the Timeline: Confirm the Timeline holds focus, then hit Command-A.

To change which clip is selected using the keyboard:

- Pick a clip, then apply the Command-Up/Down/Left/Right Arrow keys to shift the selection to whichever clip sits above, below, before, or after it across all tracks.

### Selecting Clips Based on Markers, Flags, and Clip Color

You can also grab several clips at once when they share a given marker color, flag color, or clip color. This comes in handy any time you've been leaning on those organizational aids to track clips carrying particular traits that you may later want to round up for batch operations. As an illustration, you could tag a run of audio clips with purple markers because they call for distinct EQ treatment. Afterward, picking Timeline > Select Clips By Marker Color > Purple grabs every one of those clips so you can relocate them to a different track and treat them all with one track-level audio filter. Three different routes exist for grabbing clip groups this way. To select groups of clips based on marker, flag, or clip color:

- Choose Timeline > Select Clips By Flag Color > Blue – Cream
- Choose Timeline > Select Clips By Marker Color > Blue – Cream
- Choose Timeline > Select Clips By Clip Color > Orange – Chocolate

### Selecting Edits in the Timeline

Many of the editing and trimming techniques expect you to first grab an edit point, or one side of an edit point, before you can resize, ripple, or roll it. Either the mouse or the keyboard will get the job done. Methods for selecting edit points using the mouse:

- To select an edit to roll: Bring the mouse over the middle of an edit point, and once the ripple cursor shows up, click to grab the edit.

### Selecting an edit point to roll

- To grab only one side of an edit point, the incoming or the outgoing, for resizing or rippling: Bring the mouse just left or right of an edit's center, and once the resize/ripple cursor shows up, click to grab that side of the edit.

Grabbing an edit point's incoming or outgoing half to resize or ripple it

To select multiple edit points, do one of the following:

- To select multiple roll points: Command-click the middle of several edit points. To drop one you've already grabbed, Command-click that edit point again.

Command-clicking the middle of multiple edits in readiness to roll the whole set

- To select multiple ripple points: Command-click either the left or the right side of several edit points.

Command-clicking either side of multiple edits to ripple the whole set

- To drag to select many edit points: Pick the Trim tool (T), then drag a bounding-box across the edit points you'd like to grab. Pressing U cycles every chosen edit point through rippling incoming edits, rippling outgoing edits, and rolling edits.

With the Trim tool you can drag a bounding box across several edits to grab them. A versatile collection of keyboard shortcuts also stands ready, making it simple to grab edit points ahead of various operations whenever you'd sooner skip the mouse.

Keyboard shortcuts for selecting edits: V — grabs the edit point closest to the playhead on the lowest track that has Source Track Selector switched on, taking the clip's audio and video edit points as a pair. Option-E — grabs the closest video edit point to the playhead on that same lowest track carrying Source Track Selector enabled, while leaving any linked audio edit points untouched. Shift-E — on the lowest track whose Source Track Selector is on, grabs the audio edit point nearest the playhead, while leaving any linked video edit points untouched. U — after an edit point is grabbed, this shortcut cycles through grabbing the outgoing half, the incoming half, or the whole edit. Option-U — after an edit point is grabbed, this shortcut cycles through grabbing the edit's video+audio, the video only, or the audio only.

To move the selection to another edit:

- Grab a single edit point, then move the selection to whichever edit point precedes or follows it across every track by pressing Up Arrow key (Previous Edit) or, for the one after, Down Arrow key (Next Edit).

To deselect all edit points:

- Using the mouse: Click any empty area of the Timeline.
- Using the keyboard: Press Shift-Command-A.

### A Practical Example of Keyboard-Driven Selections

What follows shows how these shortcuts chain together into a single run of steps. To select an edit point using the keyboard: 1 Hit Command-4 to hand focus to the Timeline. 2 Bring the Timeline playhead near the edit point you're after by working the JKL keys. 3 Hit the V key to grab the nearest edit point to the playhead on the lowest track that has Destination Track Selector enabled. Should superimposed clips overlap on several tracks, switch off the Destination Track Selector controls for tracks whose edits you'd rather skip, using Option-F1 through Option-F8, which line up with the Destination Track Selector controls on tracks 1–8. With the mouse, Option‑clicking a track's Destination Track Selector button solos that track's Destination Track Selector state. (Option-F9 flips the Destination Track Selector controls for every video track.) 4 At first the whole edit is grabbed, set up for a roll edit. Press the U key to cycle among grabbing the outgoing half, the incoming half, and the full edit. 5 Press Option-U to cycle among grabbing the edit's video+audio, only the video, or only the audio. 6 Carry out whatever you came to do. Once done, shift the selection earlier or later in the Timeline with Up-Arrow or Down-Arrow, or hit Command-Shift-A to clear it.

### Using Destination Track Selector Controls to Define Selections

The Timeline Destination Track Selector controls are remarkably handy, flexible controls that fill numerous roles. Put simply, they let you declare which tracks get acted on or weighed when you run an operation across multiple superimposed clips spread over several Timeline tracks. On top of that, the Timeline Destination Track Selector controls really shine when you're editing by keyboard and would rather not reach for the mouse just to pick out a single clip, given that Destination Track Selectors can be switched on or off through keyboard shortcuts.

### Defining Selections With the Help of Destination Track Selector Controls

Here's the most straightforward case showing why the Destination Track Selector controls matter. Picture an example holding two superimposed video clips alongside three superimposed audio clips. Say you intend to clear the media off tracks V2, V1, and A1 while leaving whatever sits on A2 and A3 untouched; you'd switch off the Destination Track Selector controls for tracks A2 and-A3, then place Timeline In and Out points marking the span of clips you mean to remove. Pressing the Delete key then clears only the media on the tracks whose Destination Track Selector is enabled.

Before and after a clip is deleted, with the Destination Track Selectors (red) switched on for Tracks V2, V1, and A1 and switched off for Tracks A2, and A3 TIP: When you've placed In and Out points for an operation yet spot no shading in the Timeline marking which stretches will and won't be touched, odds are some other selected clip is lurking out of view in the Timeline and overriding the Destination Track Selectors. Hit Command-Shift-A to de-select everything and matters should return to normal.

### Overriding Automatic Selections by Making Manual Selections

Keep in mind that whenever you manually highlight particular clips in the Timeline, those manual selections always win out over whatever a track's Destination Track Selector control happens to be set to. Take an example with three superimposed clips where the Destination Track Selector control of every track besides V2 has been switched off. Placing Timeline In and Out points then automatically marks that stretch of the clip on track V2 for deletion, should you press the Delete key. The portion of the Timeline involved stands out because it's highlighted while everything else dims.

Soloing track V2's Destination Track Selector control so a Delete operation stays confined to it However, were you to click the clip on track V1 to grab it by hand, the automatic selection that the In and Out points had set up vanishes, giving way to the highlighted clip you just clicked. That's because manual selections nearly always outrank the automatic ones you set up through the In and Out points and Destination Track Selector controls.

A manual selection takes priority over the Auto Select controls Bear this in mind whenever the quickest route to the operation at hand is simply picking the clip by hand to mark out that operation.

### Using Destination Track Selector Controls to Control Other Operations

The Destination Track Selector controls also steer every command whose result hinges on "the clip on the lowest-numbered track with Destination Track Selector enabled." Among such commands are these: Copy and Paste; Mark Clip; Go To Next Edit/Previous Edit; Selection Follows Playhead mode; Next Gap/Previous Gap; plus more (you'll find a full roster of the affected operations further on). One frequent case where this counts is any time you reach for the Mark Clip command to have In and Out points set automatically to span a Timeline clip's length. Should that clip fall at a spot on the Timeline holding several superimposed clips of differing lengths, then by default the In and Out points (first and last frames) belonging to the clip on the lowest numbered track drive the Timeline In and Out points whenever Mark Clip runs.

With Mark Clip run while every Destination Track Selector control stays enabled, the outcome is set by whichever clip sits on the lowestnumbered video track that still has Destination Track Selector enabled However, switch off the Destination Track Selector control for track V1, and whichever clip now sits on the lowest video track whose Destination Track Selector remains enabled becomes the target for the Mark Clip operation. Here, the briefer clip on track V2 takes over setting where the In and Out points land.

A Mark Clip run while the Destination Track Selector controls remain enabled Here are the ways to switch the Destination Track Selector controls on and off:

- To toggle Destination Track Selector for any track: A click on that track's Destination Track Selector control does it.
- To toggle Destination Track Selector for video tracks: Hit Option-F1 through F8, each flipping Destination Track Selector on its matching track.
- To toggle Destination Track Selector for audio tracks: Hit Option-Command-F1 through F8, each flipping Destination Track Selector on its matching track.
- To flip every video track's Destination Track Selector off and on together: Press Option-F9.
- To flip every audio track's Destination Track Selector off and on together: Press OptionCommand-F9.
- To "solo" one track's Destination Track Selector while switching Destination Track Selector off everywhere else: An Option-click on any Destination Track Selector control keeps that one active and shuts off every other Destination Track Selector control of the matching kind (video or audio).
- To switch on or off every audio or video Destination Track Selector control at once: A Shift-click on any video or audio Destination Track Selector control flips every Destination Track Selector control of the matching kind (video or audio) on or off at once.

Each track's Destination Track Selector control state bears on the following operations:

- Cutting, copying, or deleting clips: With Timeline In and Out points marking a span of media to clear from the Timeline, only the media on tracks whose Destination Track Selector control is enabled gets cut, copied, or deleted.
- Deleting gaps: As you pick and clear gaps in the Timeline, clips on other tracks that cross the chosen gap are deleted as well on tracks whose Destination Track Selector control is enabled. Media sitting to the right on the affected tracks ripples leftward to seal the gap.
- Selecting edit points using the keyboard: Pressing V to grab the nearest edit point lands on the edit point belonging to the lowest track with Destination Track Selector enabled. When you walk the selection from one edit point to the next with the Up Arrow and Down Arrow keys, edit points on tracks whose Destination Track Selector control is off get skipped.
- Selecting clips using the keyboard: With a clip selected, the Up Arrow and Down Arrow keys walk the selection from clip to edit clip, yet clips on tracks whose Destination Track Selector control is disabled stay invisible to this operation.
- Using Mark Clip: While the Mark Clip command runs, clips on tracks whose Destination Track Selector controls are disabled get passed over. This lets you single out a target clip for marking the clip whenever several overlapping superimposed clips are present.
- Match Frame: During a Match Frame operation, clips on tracks whose Destination Track Selector controls are disabled get passed over. This lets you single out a target clip for matching a frame whenever several overlapping superimposed clips are present.
- Pasting clips: Every copied clip lands on the lowest numbered track whose Destination Control is enabled. Should all tracks of a given type have their Destination Track Selector controls switched off, then none of that type's clips get pasted whatsoever.
- Finding gaps: When you invoke Playback > Previous Gap (Command-Option-Semicolon), or alternatively Next Gap (Command-Option-Apostrophe), any gaps residing on tracks whose Destination Track Selector is off get skipped.
- Using Selection Follows Playhead: Switching on "Selection Follows Playhead" makes whichever clip the playhead crosses get picked automatically. When more than one clip crosses the playhead, the one on the highest track gets chosen. Clips on tracks whose Destination Track Selector is disabled won't be picked.

### Locking Tracks You Don't Want to Change

One more move you can make before launching into any editorial operation is to lock down tracks holding media you'd rather keep clear of whatever's coming. As an instance, if track A3 carries an intricate batch of music edits you want shielded from operations that would ripple the Timeline, locking track A3 keeps those clips untouched.

Here tracks V2, V1, and A1 stay unlocked, whereas tracks A2, A3, and A4 are locked Clips sitting on locked tracks can't be moved, deleted, cut, or otherwise touched by editorial operations. On top of that, you can't edit a locked clip's parameters in the Inspector. Even so, clips on locked tracks remain open to grading and other changes over in the Color page. To flip tracks between their locked and unlocked states, take one of these routes:

- A click on any track's lock control flips that track's lock on or off.
- A Shift-click on any track's lock control flips locking on or off across all tracks at once.
- Option-Shift-1 through 8 locks or unlocks the tracks V1 through V8.
- Option-Shift-9 locks or unlocks every video track.
- Option-Shift-F1 through F8 locks or unlocks the tracks A1 through A8.
- Option-Shift-F9 locks or unlocks every audio track.

### Position Lock for Finishing

Put briefly, switching position lock on stops clips from sliding left or right and blocks every ripple operation. Its main value comes near the close of post on a project whose cut is locked (or as close to "locked" as directors and producers will still permit) while you still need surgical tweaks that won't risk knocking the video out of sync with audio that could be getting edited and mixed elsewhere, all from one stray rippled edit. With position lock engaged, you remain free to perform edits (Replace among them), slip clips, roll edits, drop in Resolve FX and other Open FX, and adjust every sort of effect in the Inspector. The one thing you can't do is anything that moves clips around the Timeline or ripples whole stretches of it. Position Lock can be switched on in two ways.

### Position Locking All Tracks

A single button in the toolbar over the Timeline lets you switch Position Lock on and off for all tracks at once.

### The Position Lock button on the toolbar

Once you switch position lock on, every track's Lock button turns red to signal that position lock is now active instead. Position lock indicated by each track's Lock icon changing

### Position Locking Individual Tracks

For an extra-clever touch, you can engage position lock track by track by Command-clicking any track's Lock button. To release position lock, just click that same track's Lock icon.

### Disabling and Re-Enabling Clips in the Timeline

Now and then a video or audio clip or two sits in the Timeline that you'd rather not have play with the rest of the cut sequence, yet you also aren't ready to pull it out of the Timeline in case you reconsider down the line. That's why you can Disable clips, switching them off without taking them out. Disabled clips show up dimmed in the Timeline. They won't play back, they aren't rendered, and they don't get output to video. Their spot in the Timeline stays intact, though, so you can re-enable them whenever you reconsider and decide you'd like to use them after all.

A disabled clip shown dimmed and flanked by two enabled clips To disable or re-enable one or more clips you've selected:

- On part of the selection, right-click and pick Enable Clip out of the contextual menu.
- Choose Clip > Enable/Disable Clip.
- Press D.

NOTE: Dedicated Enable and Disable clip actions can now be mapped to keyboard shortcuts within the Keyboard Customization Dialog. The toggle shortcut for enable / disable clip stays "D", yet mapping these dedicated actions sidesteps the problem of a selection holding both disabled and enabled clips merely flipping their on / off states instead of all turning enabled or all turning disabled. 1. Open DaVinci Resolve > Keyboard Customization. 2. Beneath Commands, pick Clip. 3. Enter "able" within the search box. 4. Map a keyboard shortcut onto both Disable Clip and Enable Clip.

### Deleting Clips From the Timeline

Two routes exist for clearing out clips you no longer want in the Timeline. With the Delete key you can carry out what's often termed a "lift edit," pulling the unwanted clips and leaving behind a gap. With the Forward Delete key you can carry out a "ripple delete," pulling unwanted clips and sealing the gap by rippling whatever remains of the cut Timeline that sits to the right of the removed clip(s) leftward. Deleting clips as a "lift edit" operation:

- To pull one or more clips out of the Timeline while leaving a gap behind: Grab a clip in the Timeline, or Shift-click or Command-click to grab the clips you mean to pull, then press the Delete key (or right-click the selection and choose Delete).
- To pull a stretch of media off several Timeline tracks while leaving a gap behind: Place Timeline In and Out points marking the span of media you mean to clear, then switch off the Destination Track Selector controls for any tracks whose media you want kept, and hit Delete (or right-click the selection, choosing Delete).

Clearing a clip on V1, A1 with the Backspace or Delete key so a gap remains Deleting clips as a "ripple delete" operation:

- To pull one or more clips and seal the gap by rippling the Timeline leftward: Grab a clip in the Timeline, or Shift-click or Command-click to grab the clips you mean to pull, then press the Forward Delete key.
- To pull a stretch of media and seal the gap by rippling the Timeline leftward: Place Timeline In and Out points marking the span of media you mean to clear, then switch off the Sync locks for any tracks whose media you want kept, and press the Forward Delete key.

Clearing a clip with the Forward Delete key so that every clip carrying In points to the right ripples leftward in the Timeline and seals the gap. Observe that tracks A2, A3 don't ripple, since their Sync Locks were switched off in their track headers. Just as in any ripple operation, every clip whose Sync Locks are enabled ripples to seal the gap.

### Gaps in the Timeline

A gap means the empty space sitting between any two clips on a single track. Quite often gaps are what you want, since they let audio or video clips be set apart from each other with precision, but at other times they aren't. Should you need to hunt down stray gaps in your timeline that are too narrow to notice, a couple of commands handle it. To move the playhead to the next gap on the Timeline: 1 Switch off the Destination Track Selector controls for whatever tracks you'd like left out of this operation. 2 Do one of the following:

- Pick Playback > Previous Gap, or hit Option-Command-Semicolon (;), which jumps the playhead leftward to the nearest gap before wherever it currently sits.
- Pick Playback > Next Gap, or hit Option-Command-Apostrophe ('), which jumps the playhead rightward to the nearest gap after wherever it currently sits.

Now and then you'll deliberately want a gap added to the timeline, perhaps as a placeholder holding room for a clip, or to break a stretch into smaller chunks. To insert a gap: 1 Set the playhead at the edit point where you'd like the gap to show up. 2 Select Edit > Insert Gap. 3 As an alternative, right-click an empty stretch of the timeline and pick Insert Gap from the context menu to drop a gap at the playhead's current spot. To select or deselect a gap: One click grabs a gap, and clicking that same gap again drops it. Only a single gap can be grabbed at any one time. The chief reason to grab a gap is to delete it, which ripples the Timeline shut over it in the process. Take the following case, where a gap separates two clips on track V1 that you'd like to seal.

### Selecting a gap on track V1

To delete a gap: Press the Delete key to seal the gap. Every clip to its right on tracks whose Sync Locks are enabled gets rippled leftward to seal the gap. Clips on tracks whose Sync Locks are disabled stay put. Should you grab a gap in a timeline holding clips across several tracks, exactly which clips get deleted hinges on how each track's Sync Lock control is set within the Timeline.

- All tracks with Sync Lock enabled: Whatever range of media crosses the chosen gap gets deleted too. Clips on those tracks ripple leftward to fill the gap.
- All tracks with Sync Lock disabled: Whatever range of media crosses the chosen gap stays whole, and clips on those tracks won't ripple left, drifting out of sync with whichever clips do ripple..

### Deleting Multiple Timeline Gaps at Once

</content>
</invoke>
