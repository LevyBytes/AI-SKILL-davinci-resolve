# Three And Four Point Editing (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Three- and Four‑Point Editing

When you need tighter control over how footage lands in your program, three- and four-point editing lets you map a chosen span of source media onto a chosen span of the Timeline. The pages ahead walk through the fundamentals of these techniques and survey the broad range of edit commands they put at your disposal.

### Keyboard Shortcuts in This Chapter

Below you'll find a handy collection of keyboard shortcuts tied to the subjects discussed throughout these pages.

```text
Key Shortcut Command-1 Command-2 Arrow Keys Return or Enter Q I, O Shift-I, O Option-I, O Shift-A X Option-X Command-Shift-Up, Down Arrow Command-Option-Up, Down Arrow Option-1 through 8 Command-Option-1 t horugh 8 Option-F1 through F8 Option-F9 Option-Command-F1 t hrough F8 Option-Command-F9 Option-Shift-Q F9 F10 F11
```

### Function Choose Media Pool Bin list

Pick the Media Pool browser area Shift the highlight within the Media Pool Bin list or browser area onto a bin or clip Load the picked clip or timeline into the Source Viewer Flip focus back and forth between the Source and Timeline Viewers Place an In or Out point Send the playhead to an In or Out point Remove an In or Out point Snap In and Out points around whatever clip is currently selected on the Timeline Snap In and Out points so they wrap the clip beneath the playhead on the Timeline Remove both the In and Out points Bump the video destination control up or down onto a neighbouring track Bump the audio destination control up or down onto a neighbouring track Point the video destination control at a given track number; a second press toggles enable/disable Point the audio destination control at a given track number; a second press toggles enable/disable Flip the video auto-select for a given track number Flip every video auto-select control collectively off or on Flip the audio auto-select for a given track number Flip every audio auto-select control collectively off or on Switches the “Switch to Timeline After Edit” behaviour, deciding whether focus holds on the Source Viewer or jumps to the Timeline once an edit is made; enabled out of the box Insert Edit the chosen clip(s) from the Media Pool or Source Viewer onto the Timeline Overwrite Edit the chosen clip(s) from the Media Pool or Source Viewer onto the Timeline Replace Edit the first of the chosen clip(s) from the Media Pool or Source Viewer onto the Timeline

### Key Shortcut F12

### Shift-F10 Shift-F11 Shift-F12 Undo Redo

Function Place On Top Edit the clip from the Media Pool or Source Viewer onto the Timeline Ripple Overwrite the clip from the Media Pool or Source Viewer onto the Timeline Fit to Fill the clip from the Media Pool or Source Viewer onto the Timeline Append To End Edit the clip from the Media Pool or Source Viewer onto the Timeline Command-Z Command-Shift-Z

### Introduction to Three-Point Editing

Because three-point editing is a common editorial convention found across plenty of other post-production tools, the workflow should already seem natural to you. The principle is simple: place any three In and Out points across the source clip and Timeline to drop a clip into your program at a precise moment, and DaVinci Resolve works out the remaining fourth edit point on its own to carry out the edit. In practice, overwrite and insert edits are the usual vehicles for three-point editing.

### Choosing a Track to Edit and Using the Source Track Selector

Use the Source Track Selector to map the audio and video parts of a source clip onto the specific timeline tracks you intend them for. Pointing each track's destination control where it belongs is both a simple action and an essential part of building any edit.

In the Source Track Selector, blue denotes the source tracks on the left while red marks the timeline tracks over on the right

On the blue left-hand column you see the tracks belonging to whichever source clips are picked in the media pool or open in the source viewer (say, a clip carrying one video track V1 plus four audio tracks A1-6). The red right-hand column stands for the timeline's destination tracks (for instance, two video tracks V1-2 and six audio tracks A1-6). Through the Source Track Selector you assign each source-clip track to a particular timeline track. You can reach the source tracks either by dragging them onto different destination tracks or through the Timeline > Source Track Selector menu. To illustrate, grab the video portion of a source clip (blue v1) and place it on video track 2 of the timeline (red v2) by dragging the blue v1 icon over beside the red V2 icon. The equivalent menu route is Timeline > Source Track Selector > Select/Deselect v2.

Pulling the Source (blue) video track 1 across so it patches to the Timeline destination (red) video track 2 for editing into that track To route the destination tracks of incoming (blue) source clips, take any one of these approaches:

- Drag the blue source control onto whatever timeline track you want.
- Click the blue source control, then click whichever red destination control on the timeline you're after.
- Use Command-Shift Up Arrow and Down Arrow to shift the Video source control between video tracks, or Command-Option Up Arrow and Down Arrow to shift the Audio source control between audio tracks.
- Hit Option-1 through 8 to route a source to a video destination, and Option-Command-1 through 8 to route a source to an audio destination across tracks 1 through 8.
- Pick whichever command you need from the Timeline > Source Track Selector submenu, where every Source Track Selector choice appears next to its keyboard shortcut.

Audio sources offer one more selection route, since a clip can hold several of them rather than the lone video source. Right-click a blue source audio channel and choose a different source audio track from the context menu to send it to the timeline track instead.

As another option, right-click an audio source track (A3 blue) and use the context menu to pick a different source audio track that gets patched to timeline track A3 Red

When you'd like to bring a source video clip into the Timeline minus its audio (or the reverse), switch off the relevant Video or Audio destination controls. Here is how to turn a source or destination control off and back on:

- Click any source or destination icon that's already assigned to flip it off and then back on. A disabled destination control loses its highlight. Should repeated tweaking of the track selectors leave you muddled, you can return them to their default state at any time.

To return every track selector to default: choose Timeline > Source Track Selector > Reset Track Selectors.

### Setting In and Out Points in the Timeline

Much of the time, preparing a Timeline edit takes nothing more than parking the Timeline playhead on the frame where the incoming source clip should land. When no In or Out points exist, the playhead stands in as the In point. That said, marking specific In and Out points to carve out particular Timeline ranges opens the door to other kinds of edits. Ways to set and remove In and Out points in the Timeline:

- To set an In or Out point: give focus to the Timeline or Timeline Viewer with a click or the Q key, position the playhead using the transport controls, jog bar, or control panel buttons, then tap the I key for an In point or the O key for an Out point.
- To clear In or Out points: while the Timeline Viewer holds focus, hit Option-I to drop the current In point or Option-O to drop the current Out point.
- To clear both the In and Out points together: press Option-X.

In and Out points displayed on the Timeline, with the unmarked stretches beyond the selection dimmed Ways to move In and Out points in the Timeline:

- Reposition the playhead, then tap the I or O keys so the In or Out point jumps to wherever the playhead now sits.
- Drag an In or Out point along the Timeline ruler to shift it elsewhere.

Everything on the Timeline beyond the span your In and Out points currently bracket appears dimmed, drawing your eye to the stretch the next edit is going to touch.

When you want the playhead sitting on an In or Out point before tweaking something:

- Tap Shift-I to send the playhead straight to the current In point, or Shift-O to send it to the current Out point.

Even with Preview Marks switched off, the Go to In and Go to Out commands can drop the playhead onto the implicit (yet unmarked) In and Out points that a three point edit in progress implies. Say you mark In and Out points on the Timeline, then give a Source Viewer clip its own In point: a press of Shift-O (Go to Out) sends the Source Viewer playhead to the very frame that would become that clip's Out point if you ran the edit.

A three point edit comes together once In and Out points sit on the Timeline alongside an In point placed in the Source Viewer.

Relying on Go to Out to send the Source Viewer playhead onto the implicit Out point that a three point edit establishes

### Mark Clip and Mark Current Selection

Both of these commands lay down Timeline In and Out points at the same time automatically, borrowing the timing of clips already present. They shine when you need to bound an incoming edit against a clip on the Timeline that you mean to swap out, or a gap you intend to close. Put simply, Mark Clip reads the opening and closing frames of a target clip or gap on the Timeline and sets the editing In and Out points from them. So if a shot in your cut needs replacing with an alternate take of the same action, or a gap among your clips begs to be filled fast with B-roll, Mark Clip gets you there. Mark Current Selection instead takes the opening and closing frames across a span of selected clips to lay down the Timeline In and Out points. It fits nicely when a run of clips on the Timeline should all give way to one incoming source clip.

To use Mark Clip: 1 Slide the playhead so it crosses either the clip whose In and Out points you want, or the gap (empty stretch) between two clips you mean to target. Any frame of that clip will do for the playhead's location.

Parking the playhead over a clip you intend to mark 2 Should other clips on a multi-track timeline sit over the one you're aiming at, the clip riding the lowest video track becomes the target for setting the In and Out points. To target a clip on a higher track instead, either switch off the Auto Selection controls of every track beneath it, or Option-click the Auto Selection control of the targeted clip's track to solo it, which forces that track to serve as the target. 3 Hit the X key and the In and Out points snap automatically to the opening and closing frames of the target clip.

Applying Mark Clip so the In and Out points line up with a clip's length TIP: Pressing Option-X wipes both In and Out points and acts as the reverse of this command.

To use Mark Selection: 1 Pick one or several clips on the Timeline.

Choosing the clips whose span will mark the In and Out points 2 Tap Shift-A and the In and Out points jump automatically to the opening and closing frames of your selection. Whether the selected clips run continuously or have gaps between them, the outcome is identical.

Marking a selection so the In and Out points are set TIP: Mark Selection works on Timeline gaps as well.

### Preview Marks During Three‑Point Editing

So you can preview the outcome of a three-point edit before committing, preview marks show up in either the Source Viewer or the Timeline Ruler to report exactly how much Timeline the pending edit will touch. To keep them from getting in your way, they surface only after you've deliberately placed three edit points across the Source Viewer and Timeline, and you can toggle them with View > Show Preview Marks.

As an illustration, place In and Out points in the Source Viewer plus an In point on the Timeline, and a preview marker surfaces in the Timeline Ruler to reveal where the pending edit's implied Timeline Out point falls.

A preview marker on the Timeline reflects the Timeline Out point that DaVinci Resolve works out on its own from the Viewer's In and Out points together with the Timeline In point Conversely, when you place both In and Out points on the Timeline but only an Out point in the Source Viewer, a preview marker turns up in the Source Viewer's jog bar to point out the pending edit's implied In point there.

A preview marker in the Source Viewer reflects the Source Viewer In point that DaVinci Resolve derives on its own from the Timeline's In and Out points along with the Source Viewer In point When convenient, jump the playhead onto the preview mark with Shift-I for an In point or Shift-O for an Out point.

### Dragging Preview Marks to Change an Edit

Dragging a preview mark reshapes the edit you're about to commit. As you drag one, the matching In or Out point on the side opposite the focused Viewer shifts to suit the revised three-point edit. Picture an In point in the Source Viewer with In and Out points on the Timeline: a preview mark shows up in the Source Viewer indicating the Out point that will cut the Source Viewer clip into the Timeline. Drag that preview mark leftward in the Source Viewer and the Timeline Out point travels right along with it, because you're retiming the edit.

Pulling a preview mark within the Source Viewer reshapes the matching edit point over on the Timeline

### The Rules of Three-Point Editing

In the cases above, three-point editing worked because source In and Out points bounded the portion of the source clip headed for the Timeline while the Timeline playhead stood in as the acting Timeline In point; those three points pinned down the edit. Yet threepoint editing earns its keep just as much when you have to overwrite stretches of an already-cut timeline with fresh source clips in a measured way, for instance dropping an insert shot into a scene to mask a change that would otherwise break continuity. Which rules apply hinges on the mix of Source and Timeline In and Out points you've set:

- If there is no In point in the source clip: media's opening frame stands in as the acting source In point. A thick bar reaching left of the Out point in the Source Viewer's jog bar signals this.

A thick bar marks the portion of the source clip drawn upon when no Source In point exists

- If there is no Out point in the source clip: media's closing frame serves as the acting source Out point. A thick bar reaching right of the In point in the Source Viewer's jog bar signals this.

A thick bar marks the portion of the source clip drawn upon when no Source Out point exists

- With neither an In nor an Out point on the Timeline: the playhead serves as the acting Timeline In point.
- Given a Timeline In point yet no matching Out point on the Timeline: the entire span between the source clip's In and Out points goes into the Timeline with the Source In point lined up against the Timeline In point. A thick bar reaching right of the In point in the Timeline Ruler signals this.

A thick bar marks where the Source clip lands once no Timeline Out point is present

- Given a Timeline Out point yet no matching In point on the Timeline: the incoming source clip gets backtimed so its Out point lines up with the Timeline Out point. A thick bar reaching left of the Out point in the Timeline Ruler signals this.

A thick bar flags a backtimed edit whenever no Timeline In point is present

- Given both Timeline In and Out points plus a Source Out point alone: here too the incoming source clip is backtimed so its Out point meets the Timeline Out point, while the Timeline edit points fix how much of the source clip is used.
- Given the full set of Source In and Out plus Timeline In and Out edit points: the Timeline edit points govern how much source clip enters the Timeline, and the frame sitting at the Source In point meets the Timeline In point, except when you run a Fit to Fill or ripple overwrite edit, each of which can operate as a four-point edit.

TIP: When all four Source and Timeline edit points are in play to retime a source clip into a chosen Timeline range, reach for a Fit to Fill edit rather than an overwrite edit.

### Editing Rules for Split In and Out Points

Whenever split In and Out points exist in the Source Viewer or Timeline, these rules take effect:

- If the Source Viewer has split In and Out Points: when the clip is cut in, its leftmost split point — be it video or audio — meets the playhead, and the remaining split point sits offset to the right.
- If the Timeline has split In and Out Points: the incoming clip's In point meets the leftmost split point, whether that's video or audio, while the partner audio or video In point lands offset at the split point to its right.

### Editing a Specific Range of the Source Clip Into the Timeline

What follows are a few everyday three-point editing scenarios for cutting into the middle of an already-assembled timeline. In this first one, you've got a defined span of source media to place on the Timeline and aren't fussed about whatever the incoming clip overwrites there. 1 Mark In and Out points on a source clip, working from the Media Pool or the Source Viewer.

Placing In and Out points on the source clip

2 To establish the landing spot for the incoming clip, aim the destination control at the tracks you mean to edit onto, then take one of these steps:

- Park the Timeline playhead on whichever frame should act as the edit's Timeline In point.
- Mark a Timeline In point for the edit.

Letting the playhead stand in for a Timeline In point 3 To carry out the edit, hit the Overwrite Clip button on the toolbar, press F10, or drop a clip onto the matching overlay in the Timeline Viewer.

The finished edit; how long the source clip runs sets how long the edit runs

### Editing Part of a Source Clip to Fit Into a Specific Range of the Timeline

Here you've got a portion of a clip, or a gap within the cut sequence on the Timeline, that should soak up however much of the present source clip it takes to "plug the hole." 1 If needed, mark an In point on the source clip to fix the first frame of source media bound for the Timeline. Marking only a source clip In point 2 Place In and Out points on the Timeline to pin down both the incoming clip's landing spot and how much of it gets used.

Marking both Timeline In and Out points to bound a gap 3 To carry out the edit, hit the Overwrite Clip button on the toolbar, press F10, or drop a clip onto the matching overlay in the Timeline Viewer.

The finished edit; the span between the Timeline edit points decides how much source clip gets used

### Backtiming a Source Clip When Editing Into the Timeline

For this final scenario, a particular beat in the latter half of a source clip has to meet a Timeline Out point so that the clip's leftover length overwrites the cut sequence working from right to left. Lining a Source Out point up with a Timeline Out point to make an edit goes by the name backtiming, and there are two ways to arrange it. Backtiming method one: 1 Mark In and Out points on the source clip, from either the Media Pool or the Source Viewer. 2 Mark an Out point on the Timeline at the frame where the incoming source clip's matching Out point should line up.

Building a backtimed match-on-action edit from In and Out points in the Source Viewer plus a lone Out point on the Timeline 3 To carry out the edit, hit the Overwrite Clip button on the toolbar, press F10, or drop a clip onto the overwrite overlay in the Timeline Viewer.

The finished edit, with the source clip's Out point matched to the Timeline's Out point

Backtiming method two: 1 Mark an Out point on the source clip, from either the Media Pool or the Source Viewer. 2 Place In and Out points on the Timeline to pin down both the incoming clip's landing spot and how much of it gets used.

Building a backtimed edit by marking an Out point in the Source Viewer alongside In and Out points on the Timeline that set the edit's length 3 To carry out the edit, hit the Overwrite Clip button on the toolbar, press F10, or drop a clip onto the matching overlay in the Timeline Viewer.

The completed edit, where the source clip's Out point sits flush against the Timeline's Out point

### Switch Focus to Timeline After Edit

Found in the Edit menu, the “Switch focus to timeline after edit” option (Option-Shift-Q) governs whether DaVinci Resolve hands application focus from the Source Viewer over to the Timeline Viewer/ Timeline each time you cut an edit. It ships turned on. Suppose you're pulling clips out of many different source files into the Timeline and trimming as you go — keeping this on can save time, since focus hops from the Source Viewer to the Timeline after each edit, letting you grab the clip or edit point you want to trim, make adjustments, and only then load the next clip into the Source Viewer for the following edit. Conversely, when you're cutting several pieces out of one long interview clip, you might switch it off so you can keep playing forward in the Source Viewer, dropping In and Out points and sending clips to the Timeline as you go. With it off, focus stays put on the Source Viewer after each edit, so you carry on editing from the same source clip without a break.

### Different Types of Three‑ and Four‑Point Edits

What follows runs through the various edit types on offer for dropping source clips into whichever Timeline is currently open.

### Overwrite Edits

Your go-to edit and the one you'll reach for most, an overwrite edit wipes out whatever media occupied the Timeline before and drops the incoming source clip in its place. It's the natural choice while first assembling clips or working through three-point editing, and it leaves the Timeline unrippled. To overwrite one or more Timeline clips: 1 Park the playhead on the Timeline frame where the clip should go. 2 In the Source Track Selector, click the right audio and video destination controls for the tracks that will receive the incoming source clip, adding new tracks if you must. 3 Open a single Media Pool clip into the Source Viewer, then mark In and Out points to bound the media range you want to drop in. 4 To carry out the edit, choose Edit > Overwrite, hit the Overwrite Clip button on the toolbar, press F10, or drop a clip onto the Overwrite overlay in the Timeline Viewer.

Before and after an overwrite edit, total Timeline length is unchanged The chosen Media Pool clips overwrite onto the chosen track from the playhead's position outward, replacing whatever sat there before while bringing the incoming clip in. Nothing else on the Timeline ripples during the operation.

### Insert Edits
