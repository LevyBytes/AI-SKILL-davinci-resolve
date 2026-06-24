# Trimming (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Ripple deleting a gap or clip (Forward-Delete)
- Ripple cutting any clip (Shift-Command-X)
- Rippling a single edit or several edits or gaps via the Trim tool (press T for the Trim tool)
- Issuing the Extend Edit (E), Trim Start (Shift-[), or Trim End (Shift-]) commands while in Trim mode
- Issuing Ripple Start (Command-Shift-[) or Ripple End (Command-Shift-]) from within any mode
- Carrying out an insert edit (F9) or a ripple overwrite edit (Shift-F10)
- Applying the Retime controls to accelerate or decelerate a clip while in Trim mode
- Working in the Change Speed dialog with the Ripple Sequence checkbox switched on
- Swapping clips inside a Take Selector while the Ripple control is enabled

The Edit page timeline's ripple behaviors aim to keep sync intact across the majority of scenarios. Practically, that means lengthy overlapping superimpositions like titles, graphics, and music beds hold their position as you ripple individual clips inside a montage that's being cut against those longer elements. Any track whose relative sync you wish to maintain must have its Sync Locks (covered further down) switched on in the Track Header. Once Sync Locks are turned on:

- Ripple trimming will keep sync intact automatically for every clip lying both ahead of and behind the ripple edit point.
- To let you carry out insert trims, clips sitting on other tracks may be cut.
- At the ripple trim edit point, clips on the remaining tracks are trimmed automatically so they don't

occlude the tracks beneath them.

### The original timeline before a Ripple Trim operation

The starting timeline appears above. Observe how the pink markers on the music track align with the blue markers placed on the source footage. Those pink markers indicate an emotional music beat sitting in flawless sync with the picture. Our aim is to keep that relationship intact as we ripple trim.

Following the ripple trim, the timeline reveals the music track being cut (red rectangle) so sync holds across every other track. Next we ripple trim to shorten an incoming clip in V1 (marked by the red arrow at the highlighted green line). Note how, as the ripple trim happened, every music marker held its sync, and the video clip on track 2 was trimmed by the identical amount as well. Achieving this required a cut at the edit point of the music track, which was then trimmed (red rectangle), leaving a jarring jump cut in that music track. That still needs handling, though it's a far simpler fix than re-syncing the entire timeline. Something had to yield, and the music track was the one sacrificed to keep every other track in sync. Ripple trimming this way, with all Sync Locks active, is generally the most efficient route for the bulk of work, but should you want to shield a particular track, just disable the Sync Locks on whichever timeline tracks you'd like to leave untouched while ripple trimming.

### Sync Lock Controls

Out of the box, sync lock is active on every track. This stops linked clips spread across different tracks from drifting out of sync while a ripple operation runs (for instance, when something is ripple deleted and the remainder of the timeline shifts left to close the gap). That behavior can occasionally cause you to accidentally overwrite a portion of a track you meant to keep, and not every track genuinely has to remain in sync.

To cover those occasions, there's an icon (just right of the track lock icon) controlling the ripple on/off behavior per track. This sync lock toggle operates separately from the source track selector, letting you switch sync on or off according to track type without fussing over toggling track selection states. While it's on, the track ripples alongside the other tracks. While it's off, ripple still functions on its own for that track, but the track won't ripple in response to edit operations occurring on other tracks.

### The Sync Lock icon

What follows is an illustration of how Sync Locks can be applied during Ripple Editing to accomplish different goals

The original timeline before a Ripple Trim operation.

The resulting ripple with all the Sync Locks on

When every Sync Lock is on, running the ripple on EE additionally cuts and trims the video and audio tracks of DD at the ripple point, ensuring the relative sync between EE and DD holds now that EE has been shortened.

The resulting ripple with the Sync Locks off on V1 and A1 Once the Sync Locks are switched off on V1 and A1, carrying out the ripple on EE leaves DD unaffected, but the clips fall out of sync.

### Using the Source Track Selector to Control Trimming

Each track in the Timeline carries Source Track Selector buttons that drive a wide range of operations, broadly indicating that the chosen track is ready to be acted upon. While a track's Track Selector and control is on, clips residing on that track are taken in automatically by these kinds of operations:

- Operations affecting clips that intersect the playhead's location
- Operations affecting clips that intersect a region bounded by timeline In and Out points

While a track's Source Track Selector control is off, those same operation categories skip the clips on that track, unless you select one or more clips or edit points by hand. The sections coming up explain in depth how the Source Track Selector buttons let you steer the trimming operations described in this chapter, plus the variety of "playhead-targeted" trim operations described later on. For additional detail on applying the Source Track Selector controls to define selections and govern other editing operations, see Chapter 36, "Editing Basics."

### Using the Source Track Selector to Control Which Clips Are Trimmed

A primary purpose of the Source Track Selector controls is to give keyboard shortcut-driven editors a way to pick exactly which clips on which tracks an operation will touch, when that operation would otherwise hit every superimposed clip at the playhead's location or enclosed by In and Out points placed in the timeline. As an example, picture several clips stacked across V1, V2, and V3, plus A1, A2, and A3, with the Source Track Selector (red) controls active on all six of those tracks; park the playhead over one of them and run Trim End from Selection mode, and every one of the six stacked clips is trimmed.

Trimming all clips at the position of the playhead

If, however, you wish to trim only the clip in track V3, you can solo that track's Source Track Selector control by Option-clicking it, and then invoking the Trim End command trims the clip on V3 alone, leaving the rest of the clips untouched.

Soloing the V3 Auto Select controls so that the trim affects the V3 clip alone

### Using Manual Selections to Control Which Clips Are Trimmed

Worth remembering: any manual selections you make in the Timeline that highlight particular clips always override whatever the Source Track Selector controls happen to be. For instance, if Source Track Selector is on for tracks V1, V2, and V3, yet you've selected a clip on track V1, only that selected clip will still be affected by whichever operation you choose to run. So if you use Trim End, the clip on track V1 is what gets affected.

A hand-picked clip on track V1 takes priority over the Source Track Selector controls across every track

### Trimming Multiple Edits or Clips at Once

DaVinci Resolve lets you pick several edit points or clips for certain trimming operations, so you can trim multiple edits and clips simultaneously. For straightforward cases, this makes it simple to resize, ripple, slip, and slide a number of superimposed clips together, a genuine time-saver, or you might select the In point of every title generator across a credit sequence at once to prepare for shortening or lengthening them all together. For trickier cases, this opens up more elaborate trimming setups, like multi-track asymmetric trimming, to dispatch difficult tasks quickly. However ambitious the trim operation you intend to build, the procedure stays precisely the same as for a regular trim operation. Just make certain you observe these three broad steps and you'll be in good shape: 1 Pick Selection mode, then highlight whichever edit points or clips you intend to trim. For more than one selection, click once on the first item, then Command-click each additional item you wish to fold into the selection. You're free to grab as many clips and/or edit points spread over as many tracks as you please. 2 If you want to ripple, slip, or slide the full selection together, switch to Trim mode. If instead you want to resize or move every selected item together, remain in Selection mode. 3 Run the trimming operation with the mouse, keyboard shortcuts, or timecode entry, just the same as you would if only a lone edit point or clip were selected. The sections below cover each of the special-case multi-selection trim operations available, together with the particular rules and limits of each.

### Resizing and Rolling Multiple Edit Points

Multiple edit selections can be resized or rolled in one go. Doing so lets you adjust the edit points of several superimposed clips all at once. Trimming multiple edit points essentially "gangs" them together so every selected edit shifts as a single unit.

- To resize a number of clips together, grab the left (outgoing) or right (incoming) side of each edit point that needs changing, then drag those edit points using the Selection tool to resize them as a group.
- To roll several clips at once, select every edit point you need to change right at the center, so both the incoming and outgoing halves of each edit point are chosen, then drag those edit points with either the Selection or Trim tools to roll them all together.

NOTE: You cannot combine ripple and roll operations at the same time.

### Rippling Multiple Edit Points

You can also pick multiple incoming or outgoing edit points either on superimposed video tracks, or on a single video track, so as to ripple them all in one go. A good illustration of wanting to ripple several clips on a single track is when you have an end credit sequence built from 14 text generators and wish to compress that whole run by a particular figure. You can see this very case below. As you ripple trim several edits sharing one track, how many frames come off in any single trim depends on which method you pick for the trimming.

- Should you drag in the Timeline with the Trim tool, you can choose to ripple the entire batch of edits by some arbitrary duration, perhaps trimming or extending the whole batch by eight frames. When you do, DaVinci Resolve runs your multi-selection trim one edit at a time, shaving a single frame off each selected edit moving left to right as you trim, continuing until either you stop the operation or each selected edit has lost one frame, whereupon DaVinci Resolve begins removing the second frame from each selected edit left to right, then the third, and onward, until your trimming ceases. Going about it this way, the mouse lets you fit any quantity of clips into any duration you choose.
- Alternatively, you can choose to ripple every selected edit by the same fixed amount, say stripping three frames off each of the selected edits all in one move. For that, keep the Command key held as you drag selected edits with the Trim tool, or rely on Dynamic JKL trimming, or trim by typing relative timecode values, or reach for the nudge keys (Period and Comma).

To ripple trim several edits sharing one track: 1 Click the Trim tool, then drag out a bounding box across the Timeline to grab all 14 edits. 2 Hit the U key to highlight the incoming side of each selected edit. 3 Reach for whichever trimming method you like to ripple the run shorter or longer. Dragging via the Trim tool permits trimming by an arbitrary frame count, whereas keeping Command held as you drag with the Trim tool, typing timecode to trim, pressing the Comma and Period nudge keys, or invoking Dynamic JKL trimming each trims every selected edit by an equal frame count.

(Before) Choosing 14 incoming credits edit points, (after) Trimming the whole batch in one move

(Before) Choosing several incoming edit points and (after) Trimming the entire group together

### Asymmetric Trimming

Asymmetric resize or ripple trimming can be performed on multiple clips too, allowing one selection per track on as many tracks as you need. To trim two or more clips asymmetrically, select an outgoing edit point on one track, then Command-click an incoming edit on another track.

Choosing opposing outgoing video and incoming audio edit points while getting set to carry out an asymmetric ripple trim To grab the outgoing video edit on one clip together with the incoming audio edit on the next clip while preparing a split edit, you can Option-click the outgoing video edit so linked selection is suspended, then Command-click the incoming audio edit, adding that one on its own into the selection. After that, dragging, nudging, or trimming with timecode sends each chosen edit point in the reverse direction.

Dragging with the Trim tool to run an asymmetric ripple trim that forms a split edit DaVinci Resolve permits asymmetric trims on multiple edits within the same video and/or audio track. Two compelling reasons exist for doing so: Grab the outgoing half of an edit point (its left side), then Command-click to independently grab the incoming half of that very same edit point (its right side). This produces no roll edit; instead it lets you either reach for the Selection tool to pull both edit points away from one another and open a gap, or reach for the Trim tool to ripple the edit's two sides, trimming both clips down while at the same time tightening up the Timeline.

Before and After ripple trimming an edit's incoming and outgoing halves together to cut down both clips' duration in a single move You can likewise grab a clip's In and Out points in the Timeline together and reach for the Trim tool to ripple that clip's head and tail toward the middle, trimming it down while holding the central content intact, and tightening up the Timeline as you go.

Before and After ripple trimming a clip's In and Out points simultaneously, cutting it down by stripping heads and tails while the central action stays put

In essence, you can apply almost any combination of edit selections you require to trim multiple clips at once within the same track, across several tracks, whatever you need to do to save time. On top of that, asymmetric trimming works in either Selection or Trim mode, whether to open and close gaps or to slide edit points over one another to form split edits.

### Slipping Multiple Clips

Any number of selected clips can be slipped simultaneously (provided they have handles) across any mix of tracks: select the clips you wish to slip, then choose the Trim tool, and drag their name bars or use the Comma and Period keys to nudge the selection.

### Dragging to slip multiple selected clips at once

### Sliding Multiple Clips

You can select as many clips as you'd like to set up a slide operation. Select multiple contiguous clips and they slide together as a single unit.

(Before) Picking four clips for a slide, (After) Every one of the four dragged rightward with the mouse

### Keyboard Trimming During Looped Playback

If you favor precision trimming through the Nudge commands, one excellent approach is turning on looped playback so that the Play Around command (Forward Slash) keeps circling around the edit point under your trim while you nudge a frame or five at a time to refine the cut. To trim while looping: 1 Bring the playhead near the edit point that needs trimming, and press V to grab it. 2 Press the U to decide which half of the edit to grab so you can ripple or roll it, and/or Option-U to settle whether the trim covers video+audio, video alone, or audio alone. 3 Press Command-Forward Slash (/) to switch looped playback on. 4 Press Forward Slash (/) to play around whatever is currently selected. With looping active, playback runs on until you halt it. The Edit panel of the User Preferences is where Pre-roll and post-roll get adjusted. 5 While looped playback runs, press the Comma (,) and Period (.) keys to shift the selection back or ahead one frame, or Shift-Comma and Shift-Period to move it in 5-frame steps. Should you do this while looped playback is in its post-roll, the loop replays instantly from the top, so no time is wasted in seeing the result. 6 Once finished, press the Spacebar or K key to halt playback. TIP: Holding down the Shift key as you nudge for a "fast nudge" gives you a duration that's customizable through the Editing panel of the User Preferences. Five frames is the default, yet you can dial it to whatever value you prefer.

### Dynamic JKL Trimming

One of the more interactive trimming capabilities in DaVinci Resolve lets you dynamically resize, ripple, roll, slip, slide, or move chosen edit points and clips through the JKL transport control keyboard shortcuts. What that buys you is the ability to set up an appropriate Timeline selection (edit points for resizing, rippling, or rolling, or clips for slipping or sliding) and then trim it as playback runs, all while you keep an ear on the audio and an eye on the video. The advantage of trimming as the chosen clip or edit point plays back is that it lets you become emotionally caught up in what's on screen, and also feel a clip's timing as it runs, both of which sharpen your sense of precisely how a given cut needs trimming. As you dynamically trim, you see the very same two-up or four-up display, the very same Timeline overlays, and the very same live-updating Timeline that appear when the Trim tool is driven by the mouse. The sole difference is that the trimming happens while your program plays.

There are two methods of doing dynamic trimming:

- Quick Trim: Pick one or more edit points or clips and trim them right away by pressing Command-J or Command-L for a backward or forward trim. It's a speedy route to dynamic trimming, with the caveat that backward and forward trims happen only at 100 percent speed or above.
- Turning on Dynamic mode: When you need finer control, tap the W key to engage Dynamic mode (or pick Trim > Dynamic Trim Mode), which drops you into a dedicated mode in which the JKL shortcuts trim nothing but the active selection, no matter what that is. This mode further offers extra options for steering which slice of the selection, where multiple selection trims are involved, gets monitored during audio/video playback.

TIP: With nothing selected while you sit in Dynamic Trim mode, JKL just runs through the Timeline as it normally would.

### Quick Trimming

When time is short and you can land the trim you're after at real-time or quicker playback, then keeping the Command key held as you use the J or L keyboard shortcuts lets you dynamically trim whatever is selected in the Timeline, complete with audio/video playback. For dynamic trims via Command-J or Command-L:

- To dynamically roll an edit: From either Selection or Trim mode, grab the center of one or more edit points, then keep Command pressed as you tap J or L to drive the selection around.
- To dynamically ripple an edit: Switch to Trim mode, grab the outgoing or incoming half of one or more edit points, then keep Command pressed and tap J or L to drive the selection.
- To dynamically resize an edit: Switch to Selection mode, grab the outgoing or incoming half of one or more edit points, with Command held while J or L nudges the selection along.
- To dynamically move a clip: Switch to Selection mode, grab one or more clips, with Command held as J or L carries the selection back and forth.
- To dynamically slip or slide a clip: Switch to Trim mode, grab one or more clips to slip, or a lone clip to slide, press S to flip between Slip or Slide modes, then with Command held use J or L to run either the slip or the slide.

When trimming several selections, you decide which edit point to monitor across the whole trim by parking the playhead on one of the chosen edit points. TIP: Once a "quick trim" is finished and you'd like to watch how that edit plays, hit the Forward Slash key (/) to play around the current selection and rapidly preview that stretch of the Timeline.

### Dynamic Trimming (or "JKL Trimming")

Should you want the further ability to trim using the JKL shortcut keys in slow motion or frame by frame, beyond just trimming at 100% or higher playback speeds, you'll have to enable Dynamic Trim mode. To apply Dynamic mode for a dynamic trim of one or more chosen clips or edits: 1 There's no need to make any selection ahead of enabling Dynamic mode, because entering Dynamic mode by itself grabs the edit point lying nearest the playhead. Even so, should you wish to use Dynamic mode on an intricate trim, you're free to grab whatever mix of edit points you want to resize, ripple, or roll, or to grab one or more clips for slipping or sliding (the S key flips between slipping and sliding). 2 Hit W to step into Dynamic mode, or click the Dynamic tool on the toolbar. With nothing selected in the Timeline, the playhead's nearest edit point is grabbed for you automatically. Where a selection already exists, it holds and serves as the trimming target. After you've entered Dynamic mode, the toolbar's Dynamic Trim tool goes yellow to flag that you're in Dynamic mode, with its icon revealing whether trimming is set to Slip or Slide. Beyond that, the playhead itself goes yellow as an ever-present cue that you're in Dynamic mode, in which trimming clips is the only thing on offer.

The Dynamic tool lights up on the toolbar to flag that you're in Dynamic mode; that same tool also reveals whether you're set to Slip (Left) or Slide (Right) 3 Settle on the kind of operation you want; do so by clicking either the Selection tool (or pressing A), or else the Trim tool (or pressing T). In Selection mode: Edits can be dynamically resized or rolled when you've grabbed one or more edit points in the Timeline. Clips can be moved or slipped when you've grabbed one or more clips in the Timeline. Whether selected clips move or slip is your call via the S key, or by right-clicking the Dynamic trim tool on the toolbar and picking Slip or Slide off the drop-down menu. In Trim mode: Edits can be dynamically rippled or rolled when you've grabbed one or more clips in the Timeline. Clips can be slid or slipped when you've grabbed one or more clips in the Timeline. Whether selected clips slide or slip is your call via the S key, or by right-clicking the Dynamic trim tool on the toolbar and picking Slip or Slide off the drop-down menu.

4 Where you've grabbed several edit points or clips, the Left and Right arrow keys in Dynamic mode let you shift the playhead onto whichever selected edit point you'd like to monitor as you trim. Should the playhead not line up with a selected edit point, it'll jump over to the nearest selected one the moment trimming gets going. 5 Use whatever combination of the JKL keyboard shortcuts you like to kick off playback and trimming, including:

- J+K or K+L for slow-motion trimming, with slow-motion audio playback alongside
- Holding K while tapping J or L for a one-frame-at-a-time trim
- Pressing J or L for trimming at real-time playback
- Tapping J or L over and over to trim in fast-reverse or fast-forward across a range of speeds
- While you dynamically trim, each audio clip on every audio track plays as the playhead rolls past it, letting you take in your whole mix mid-trim.
