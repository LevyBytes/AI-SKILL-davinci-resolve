# Trimming (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

6 Once a trim is done, tapping the Spacebar launches Play Around Current Selection, letting you preview how the trim plays back. While Dynamic mode is active, the Spacebar performs only a Play Around Current Selection pass instead of its usual forward playback. The range that Play Around Current Selection covers hinges on the current selection: a single edit plays around that edit alone, a single clip plays around the entire clip, and several clips or edits play around the combined selection, factoring in the active Pre-Roll and PostRoll values set in the Editing panel of the User Preferences. 7 Once done, the Up and Down Arrow keys shift both selection and playhead to a different edit point or clip you wish to trim, or you can hit W once more to switch Dynamic mode back off. Be certain to disable Dynamic mode when finished, since otherwise JKL keeps trimming selections any time one or more edits or clips remain selected rather than playing back the Timeline. NOTE: With Dynamic mode turned on, JKL still works for playback as long as nothing is selected (hit Command-Shift-A to clear all selections). Yet the moment anything in the Timeline is selected, JKL trims that selection in the manner just described.

### Trim Operations that are Targeted Using the Playhead

This next group of Trim editing commands gives you several distinct ways to trim clips and edits, relying on where the playhead sits to steer the outcome.

### Trim Start and Trim End

With the Trim > Trim Start (Shift-[) and Trim End (Shift-]) commands you can shift the In or Out point of every clip crossing the playhead, doing so as a ripple operation (in Trim mode) or as a resize operation (in Selection mode). Since no selection is required to invoke Trim Start and Trim End, these commands are quick to reach for in the right moment. Trim End shines, for example, when you've stacked several clips of varying lengths and want them all to begin or end together.

- Trim Start either resizes or ripples (whichever mode you happen to be in) every clip crossing the playhead, relocating each clip's In point to wherever the playhead currently sits.

A Trim Start operation shown before and after; every clip crossing the playhead gets trimmed

- Trim End resizes or ripples the crossing clips such that each intersecting clip's Out point lands at the current playhead position.

A Trim End operation shown before and after; every clip crossing the playhead gets trimmed, while clips that miss the playhead stay as they were

Any clip that fails to cross the playhead stays untouched. On top of that, you can leave clips on certain tracks out of the operation by switching off the Source Track Selector controls for those tracks.

### Resize, Ripple, and Roll Start and End Commands

A further collection of commands within the Trim menu rolls the Trim Start and Trim End behavior together with picking Selection or Trim mode, plus resize, ripple, or roll capability, all bundled into single commands.

- Resize Start to Playhead
- Resize End to Playhead
- Ripple Start to Playhead (Command-Shift-[)
- Ripple End to Playhead (Command-Shift-])
- Roll Start to Playhead
- Roll End to Playhead

Much like Trim Start and Trim End, these commands consult the Timeline Auto Select controls to decide, among the clips crossing the playhead, which ones on which tracks get trimmed. Most of them ship without keyboard shortcuts assigned, yet if this style suits you, you can bind them to shortcuts of your own choice through the Keyboard Mapping Customization tool (Option - Command - K).

### Slip and Slide Playhead to In and Out Commands

Still another batch of commands in the Trim menu lets you slip a clip from whatever frame the Playhead currently rests on over to that clip's In or Out point.

- Slip Playhead to In
- Slip Playhead to Out

TIP: The Slip Playhead to In command behaves exactly the same as performing an extend edit while the playhead crosses a selected clip. As with Trim Start and Trim End, these commands rely on the Timeline Source Track Selector controls to work out, among the clips crossing the playhead, which ones on which tracks to trim. By default these commands carry no keyboard shortcuts, though if this approach appeals to you, you can attach shortcuts of your own through the Keyboard Mapping Customization tool (Option - Command - K).

### Extend Edits

The Extend Edit command (reached via Trim > Extend Edit, or by pressing E) resizes or ripples one or several selected edit points or clips. In contrast to Trim Start and Trim End, whether the playhead happens to cross any clips is irrelevant during an extend edit.

### Extend Editing Edit Points

Select one item per track from any mix of In or Out points, then tap the E key to send those edit points to wherever the playhead currently sits.

Before and after a multi-track extend edit performed in Selection mode. Beforehand, the red selections signal that you've grabbed the first frame of media for those clips. Afterward, those selections shift to green, signaling that extra frames sit at the head of the edit ready for trimming. Within Trim mode, selected edit points ripple rather than resizing the clips they touch. To keep multi-track extend edit operations manageable while the Trim tool is active, though, the lowest-numbered video track that has auto-select on dictates how far the extend edit ripples the remainder of the Timeline; every other selected edit point on the other tracks merely resizes to the playhead's position.

A multi-track extend edit performed in Trim mode, shown before and after; notice how the lowest-numbered track holding a selection sets the extent to which the Timeline ripples Using Extend Edits to Slide Clips The Extend Edit command can also slide the contents of one selected clip with either the Selection or Ripple tools. Just pick a clip, park the playhead over the frame of that clip you'd like to slip to the In point of that clip's spot in the Timeline, then press E to carry out the slip. This even works during playback, should you want to watch the clip roll and press E to slip that frame back at the instant it feels right.

Using the extend edit to slip a clip within the Timeline; the red marker indicates the frame under the playhead being slipped back to that clip's In point in the Timeline
