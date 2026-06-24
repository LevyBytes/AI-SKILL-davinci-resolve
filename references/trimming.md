# Trimming (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Trimming

Ask most cutters and they'll tell you that trimming accounts for roughly half of an editor's work. The Timeline lets you adjust your cut in plenty of ways with the selection and razor blade tools, but there's also a separate Trim mode that handles the more involved trim operations in fewer steps, driven by either the pointer or the keyboard according to your preference. Getting comfortable with DaVinci Resolve's trimming operations pays off in saved time during the unavoidable work of polishing a cut.

### Summarizing Trim Operations

Ahead of covering the various trimming approaches on offer, anyone just starting out with editing may find it helpful to read a short rundown of what each trimming operation does. Every trim operation exists to let you reposition edits and clips relative to their neighboring clips by carrying out a handful of operations together. There are five primary methods of trimming:

- Resize: Trims back or extends an outgoing clip's tail or an incoming clip's head, either overwriting an adjacent clip or leaving behind a gap as required. Although it's not normally counted among the "trim" operations, it's really the most basic form of trimming there is.
- Roll: Moves an edit point to the left or right, either by shortening the outgoing clip as it lengthens the incoming clip, or the reverse. Such edits leave the overall Timeline's duration unchanged.
- Ripple: Trims back or extends an outgoing clip's tail or an incoming clip's head and, at the same time, shifts every clip either rightward (when you ripple to lengthen a clip) or leftward (when you ripple to shorten a clip), so as to close the gap or avoid the overwriting that a resize operation would otherwise cause. This kind of edit does alter how long the overall Timeline runs and, if you're careless, can disturb the sync relation between different tracks.
- Slip: Pins a clip in place on the Timeline while swapping out the range of media shown at that location. A slip leaves the overall Timeline's duration as it was.
- Slide: Holds a clip's range of media constant but shifts the clip left or right, either shortening the outgoing clip on its left as it lengthens the incoming clip on its right, or the reverse.

### Selection-Based Trimming Using the Trim Tool

What sets Trim mode apart from Selection mode is that actions that would shift clips with the Selection tool instead slip or slide clips with the Trim tool. Likewise, actions that the Selection tool would treat as resizing edits will instead ripple the Timeline to close gaps automatically when the Trim tool is active. The sections that follow walk through the various trim operations on offer, covering both pointer use and keyboard use. Getting into Trim Edit mode is a matter of one action: Click the Trim Edit button, or press the T key.

### How the Trim Tool Differs From the Selection Tool

Beyond the trimming operations themselves, a handful of other meaningful distinctions separate the Trim tool from the Selection tool.

### Selecting Edit Points

With the Trim tool active, dragging a bounding box across a run of clips in the Timeline picks the edit points that join clips together rather than the clips themselves. That makes it quick and convenient to grab several edit points you intend to work on at the same time.

Using the Trim tool to select Timeline edit points. Rippling the Timeline With Different Operations. While the Trim tool is active, any other commands and controls that would otherwise resize one or more clips and leave gaps behind will instead shift (ripple) the clips positioned to the right of whichever clip or edit you trim over, moving them leftward, so that no gaps open up whenever clips or edits are repositioned or resized.

Resizing Clip L by rippling its incoming edit point, where the clips on the right (Clips P, L, and N) shift over to the left so no gap shows up. Take, for instance, these: the Retime controls, the Extend and Trim Start/End commands, plus the Nudge keyboard shortcuts. Each one behaves differently according to whether the Selection or Trim tool is in use. So one set of tools can carry out distinct operations based on what you're trying to accomplish.

### Rippling Gap

A gap's start and end in the Timeline can likewise be rippled with the Trim tool, or with the other trim operations described later in this chapter. When you ripple a gap, you enlarge or contract it while whatever portion of the Timeline lies past the gap on its right slides forward or backward in time. Any time you ripple against a gap, a 2-up display appears so you can see both the clip you're trimming and whatever superimposed clips happen to be visible through the gap.

Narrowing a gap by rippling its Out point with the Trim tool. TIP: While running these operators, you can briefly switch between the selection (A) and trim tools (T) to observe what they do. Letting go of the key returns you to whichever mode was originally chosen.

### Using the Trim Tool With the Mouse

Trimming with the pointer lets you carry out every available kind of trim operation from one tool: just click the Trim mode/tool button and then drag on the appropriate part of whichever Timeline clip you're working on. Here are the pointer-driven trimming methods available in Trim Edit mode:

- To slip a clip: To slip a clip's range of content while it stays put on the Timeline, click on a clip's middle top region, then drag left or right to "slip" the clip so it holds a different range of frames. A dashed overlay indicates the full duration of media you have available to slip with, shifting left and right as you drag.

Before a slip, clicking the upper clip area brings up an overlay that shows the media range a clip has available.

Once dragged to slip, the clips stay put, though the slipped clip now draws on a different media range. When you slip clips, a 4-up display presents all the relevant outgoing and incoming frames so you can judge how the action carries from one clip to the next. Mid-slip, the top two frames refresh to reveal the clip's new incoming and outgoing frames as it's slipped, set against the fixed outgoing frame of the clip on the left and incoming frame of the clip on the right.

TIP: You can briefly turn off this four-up display by holding the Shift key as you slip, leaving only the frame at the playhead position visible. That lets you watch which frame crosses the playhead while you ripple the Timeline. To switch this two-up display off entirely, select View > Enable Multiview Edit Preview.

### Four-up display when slipping a clip

- To slide a clip: To slide a clip, moving it somewhere else along the Timeline while, to absorb the dragged clip's shift in position, the previous clip's Out point together with the next clip's In point adjust in tandem, grab the clip's bottom-middle name bar and drag it to a fresh spot.

Once dragged to slide, the chosen clip occupies a new location and the neighboring clips have closed the gap. When you slide clips, a 4-up display presents all the relevant outgoing and incoming frames so you can judge how the action carries from one clip to the next. Mid-slide, the bottom two frames refresh to reveal the new outgoing frame of the clip on the left and the new incoming frame of the clip on the right of the clip being slid.

TIP: You can briefly turn off this four-up display by holding the Shift key as you slide, leaving only the frame at the playhead position visible. That lets you watch which frame crosses the playhead while you ripple the Timeline. To switch this two-up display off entirely, choose View > Enable Multiview Edit Preview.

### 4-up display when sliding a clip

- To roll an edit point: To roll an edit, moving in unison the outgoing clip's Out point along with the incoming clip's In point, take an edit point that sits between two clips and drag it leftward or rightward. (Selection mode supports roll edits as well.)

### Selected edit point before roll

The edit point shifted rightward, with both neighboring clips resized so no gap forms

When you roll an edit, a 2-up display reveals how the action's continuity shifts from the outgoing frame of the clip on the left to the incoming frame of the clip on the right, and you'll hear the audio scrubbing of the right clip.

### Two-up display when rolling an edit

- Ripple edit: To ripple the outgoing or incoming part of an edit, adding or removing media from a clip while at the same time shifting every other clip to the left in the Timeline to open space, click the Trim tool and drag an edit point to a fresh spot in the Timeline.

Selected outgoing half of an edit point before ripple

Now shorter, the rippled clip leaves the remainder of the Timeline shifted leftward to close the gap. When you ripple an edit, a 2-up display reveals how the action carries from the outgoing frame of the clip on the left to the incoming frame of the clip on the right. The frame that refreshes hinges on which side of the edit you're rippling.

TIP: You can briefly turn off this two-up display by holding the Shift key as you ripple, leaving only the frame at the playhead position visible. That lets you watch which frame crosses the playhead while you ripple the Timeline. To switch this two-up display off entirely, select View > Enable Multiview Edit Preview.

### Two-up display when rippling an edit

### Turning Off the Heads Up Display While You Trim

Holding the Shift key during most drag and trim operations lets you suspend the multi-frame heads up displays that show up in the Timeline window, so you can concentrate on the frame that meets the playhead. Switching those two- and four-frame heads up displays on or off is done one way: Choose View > Enable Multiview Edit Preview.

### The Precision Trim Editor

The Edit Page viewer offers an upgraded trim mode much like the precision trim editor of the Cut page. It swaps the source viewer for one large display showing frame changes on both sides of your edit, so you get a closer look at the edit point. As soon as trimming wraps up, it reverts to its earlier state on its own. The Precision Trim Editor shows up automatically when you carry out a trim operation, or when you double-click an edit point. Should you favor the older trim editor, which leaves the source viewer in place, you can turn this off via a User Preference under DaVinci Resolve > Preferences > User > Editing, by selecting or clearing the box beside "Automatically switch to single viewer mode when opening trim editor."

### Trimming Edits in the Timeline Viewer

Double-clicking any edit point between two clips in the timeline opens the Precision Trim Editor, a detailed way to adjust both halves of an edit point. A graphical A/B roll interface presents two filmstrips, the outgoing clip on top and the incoming clip on the bottom. You can drag these controls:

- To trim the outgoing clip's Out point, drag the left edge of the handle on the top filmstrip.
- To trim the incoming clip's In point, drag the right edge of the handle on the bottom filmstrip.
- For a roll of the edit point, drag the white handle sitting between the upper and lower filmstrips,

adjusting the outgoing and incoming edit points together. Numbers above each frame show you precisely how many frames you're trimming, and a pair of buttons flanking the transport controls in the Viewer toolbar let you shift the outgoing clip's Out point and the incoming clip's In point one frame at a time.

The Precision Trim Editor, as it appears after a double-click on a timeline edit

### Trim Tool Operations With the Keyboard

The Nudge keyboard shortcuts also let you carry out every trim operation with greater precision. To trim with the keyboard: 1 Press T to choose the Trim tool. 2 Trim the selection using any one of these approaches: To slide a clip: With a clip chosen via Shift-V, tap the Comma key for a single-frame leftward slip, or the Period for a single-frame rightward one. Holding Shift-Comma and Shift-Period moves the clip in 5-frame steps. To slip a clip: After Shift-V picks a clip, hit the S key to switch into Slip mode (a further S returns you to Slide mode), then use Comma or Period to drive its contents leftward or rightward. Here Shift-Comma and Shift-Period shift the contents in 5-frame steps. To roll an edit: With V selecting an edit point, tap the Comma key to nudge leftward by one frame, or the Period to nudge rightward by one. Shift-Comma and Shift-Period roll that edit in 5-frame steps. To ripple an edit: After V picks an edit point, press U to isolate just the incoming or outgoing side of that edit. From there, the Comma key ripples the chosen In or Out point of the clip leftward, while the Period sends it rightward by a frame. In this case Shift-Comma and ShiftPeriod ripple in 5-frame steps. 3 Should you wish to suspend the 2- or 4-up display that turns up in the Timeline Viewer mid-trim, the route is Choose View > Enable Multiview Edit Preview, which switches those trimming displays on and off. TIP: When you hold the Shift key while nudging to perform a "fast nudge," the length of the nudge can be set in the Editing panel of the User Preferences. Its default sits at five frames, though you may dial in any value you wish.

### Important Trimming Keyboard Shortcuts

When you trim with the keyboard, the shortcuts below are worth committing to memory. The majority of these commands, plus many more that have no shortcut assigned, are also available in the Trim menu. A good number of them can be remapped to different shortcuts via the User Preferences' Keyboard Mapping panel. For more information, see Chapter 4, "System and User Preferences."

### Key Shortcut T A Command-L and J W

### Function

Trim mode, ripples edits while slipping or sliding clips. Selection mode, resizes edits while relocating clips. Fast trim commands, which let you dynamically trim a selection at full 100% forward and reverse speeds. Dynamic trim or resize mode, relying on JKL to trim whatever's selected.

Key Shortcut S V Shift-V Shift Option-F1 through F9 Command-Option F1 through F9 U Option-U Comma (,) Period (.) Forward-Slash (/) Command-/ Down Arrow, Up Arrow E Shift-[

### Function

Switches between Slip and Slide mode while a clip sits selected in Trim mode. Grabs whichever edit point lies nearest the playhead and brings the playhead over to it. Grabs the clip or gap sitting under the playhead. Where clips are superimposed, switch off the Auto Select controls on any tracks holding clips you'd rather not grab. A modifier that briefly turns off the 2- and 4-up display shown while you trim edits and clips by pointer or by keyboard shortcut. Switches Auto Select on or off for video tracks 1 through 9, letting you confine certain selection and trim operations run from the keyboard. Switches Auto Select on or off for audio tracks 1 through 9, letting you confine certain selection and trim operations run from the keyboard. Cycles whichever edit point is selected through its outgoing, centered, or incoming part. Cycles a selected edit point or clip through Video+Audio, Video Only, or Audio Only. Once a selection exists, nudges the chosen edits or clips a single frame leftward. Shift-Comma nudges 5 frames (you set this duration in the User Preferences' Editing panel). Once a selection exists, nudges the chosen edits or clips a single frame rightward. Shift-Period nudges 5 frames (you set this duration in the User Preferences' Editing panel). How this command behaves shifts with whatever's selected in the Timeline. Plays back a stretch of the Timeline running from x frames ahead through y frames past whichever of these applies: (a) the playhead, when nothing is selected, (b) the currently selected edit point, (c) the currently selected clip, or (d) a selection of multiple clips. It comes in handy for auditioning how the present selection reads next to its immediately neighboring clips. You set the pre-roll and post-roll time in the User Preferences' Editing panel. Switches looped playback on or off. Carries both the playhead and the selection state to the following or preceding edit point. Where several clips or edits overlap, selection begins with the first clip on the lowest numbered track, then climbs to the next clip up, and continues until the topmost superimposed clip is reached, after which it moves on to the next clip in the Timeline. Extend edit. Resizes or ripples the chosen edit points up to the playhead's current position. Trim Start. Resizes (Selection) or ripples (Trim) the In point of every clip on auto-select-enabled tracks meeting the playhead, bringing it to the playhead's position.

### Key Shortcut Shift-] Shift-Command-[ Shift-Command-]

### Function

Trim End. Resizes (Selection) or ripples (Trim) the Out point of every clip on auto-select-enabled tracks meeting the playhead, bringing it to the playhead's position. Ripple Trim Start. No matter whether Selection or Trim mode is active, this always ripples the In point of clips on auto-select-enabled tracks meeting the playhead over to the playhead's position. Ripple Trim End. No matter whether Selection or Trim mode is active, this always ripples the Out point of clips on auto-select-enabled tracks meeting the playhead over to the playhead's position.

IMPORTANT: The Slip, Roll, and Slide tools alter the sync relationship of whichever clips you're adjusting against a matching soundtrack, yet leave the rest of the Timeline untouched. Ripple, by contrast, can shift the overall sync relationship across large stretches of your timeline and its matching soundtrack, so reach for it only with extreme care.

### Trimming Using Timecode Entry

Absolute or relative timecode entry is another way to trim clips and edits. Exactly what gets trimmed comes down to whatever selection you set before typing the timecode. To use timecode for trimming the selection forward from where it currently sits, make sure to type an equal sign or plus (= or +) ahead of the timecode value; to trim the selection backward in relative terms, type minus (–) ahead of the timecode value.

- To roll an edit: Pick the center of an edit point, key in a timecode value, then press Return.
- To ripple an edit: Pick either the outgoing or incoming half of an edit point, then key in a timecode

value, and press Return.

- To slip a clip: Pick a clip, pressing S where needed to switch into Slip mode, then key in a timecode

value, and press Return.

- To slide a clip: Pick a clip, pressing S where needed to toggle to Slide mode, then key in a timecode

value, and press Return.

### How to Enter Timecode Values

To enter timecode, type each pair of hour, minute, second, and frame values working left to right, using a period to stand for a pair of zeros so entry goes faster. Whatever numbers you type show up in the timecode field at the top right of the Viewer that has focus. Once you've finished typing, press the Enter key to run the timecode command. These are the rules for timecode entry:

- Whatever pair of timecode values (or period) you type furthest to the right always stands for the frame number.
- Placing a period on either side of any digit you type counts as a pair of zeroes.
- A lone period set between two digits counts as a single zero, or is dropped altogether when it falls

between two pairs of numbers.

- Any pairs of values you leave untyped to the left of your entry default to whatever those values

held before the timecode you entered; that lets you key in partial timecode values with ease, even where the Timeline starts at hour one.

- There's no need to type colons or semicolons.

IMPORTANT: On full length keyboards, the number pad supports implicit timecode entry without you having to invoke the Go To Timecode action (=). During a multicam or printer light operation, any number pad key that's already mapped keeps invoking actions such as switching angles or incrementing color values. With the number keys above the letters on a keyboard, you have to first choose Go To Timecode (=) or click in the field you want to change before you type a new value.

To enter absolute timecode you simply type in a timecode value. As long as no clips or edit points are selected at the moment you press the Return key, the playhead jumps to that timecode value. When an edit point or clip is selected, it gets moved or trimmed to match the timecode value, where that's possible. Below are several examples of absolute timecode entry done this way:

Original TC Value 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10

User-Typed Value 15245218 2.. 15 12 1.2 115.. 23...

New TC Value 15:24:52:18 01:02:00:00 01:10:10:15 01:10:10:12 01:10:01:02 01:15:00:00 23:00:00:00

You enter relative timecode by beginning the timecode value with a plus (+) or minus (–). A plus causes the value you type to be added to the current timecode value when offsetting the playhead or moving a selection. A minus causes the value you type to be subtracted from the current timecode value.

Here are two examples of relative timecode entry: +20. 00:00:20:00 is added to the current timecode value. -5 00:00:00:05 is subtracted from the current timecode value.

### Commands to Make Selections and Trim

A group of commands in the Trim menu makes it quick to automatically pick the In or Out point of whichever clip sits nearest the playhead's current position, and to drop into either Selection or Trim mode ready to resize or ripple trim that edit point. The commands are:

- Select Nearest Edit to Resize In
- Select Nearest Edit to Resize Out
- Select Nearest Edit to Ripple In
- Select Nearest Edit to Ripple Out
- Select Nearest Edit to Roll
- Select Nearest Clip to Move
- Select Nearest Clip to Slip
- Select Nearest Clip to Slide

These commands resemble combining the Edit Selection (V) or Clip Selection (Shift-V) keyboard shortcuts with those for picking the Selection (A) or Trim tool (T) all in one move, to set you up for trimming the way you intend. They carry the extra advantage, in some instances, of letting you specifically pick the In or Out points of the clip closest to the playhead's current position. None of these commands have keyboard shortcuts by default, but if this style suits you, you can map them to shortcuts of your choosing via the Keyboard Customization tool (Option - Command - K).

### Trimming Clips in the Source Viewer

Another option is to double-click a clip in the Timeline so it loads into the Source Viewer for trimming. While the Selection tool is active, dragging the In and Out markers, or working with the playhead plus the I and O keyboard shortcuts, resizes that clip back in the Timeline. While the Trim tool is active, the clip's In and Out points can be rippled.

Ripple-resizing a Timeline clip after loading it into the Source Viewer, dragging its In point with the Trim tool

To slip the clip's contents, keep the Shift key held and drag either the In or Out point.

Slipping a Timeline clip after loading it into the Source Viewer, Shift-dragging its In point with the Trim tool

NOTE: To bring a match frame of a clip that belongs to an edited sequence into the Source Viewer with the pointer, hold the Option key down as you double-click a clip in the Timeline.

### Ripple Editing Rules

Ripple operations are the lone trim functions that alter the duration of the overall Timeline and that may potentially shift the sync relationship across multiple clips on different tracks. That makes them tremendously handy, but it's important to grasp which portions of the Timeline will move during a ripple operation and which won't. These are the operations that ripple the Timeline:
