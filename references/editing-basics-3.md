# Editing Basics (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

The Edit > Delete Gaps command lets you ripple-delete every video and audio gap throughout the Timeline in a single operation. It clears the gaps sitting between back-to-back clips across all tracks that have Sync Lock turned on. Whenever a portion of the Timeline holds a gap, that portion is rippled so that any clips lying to the right of the gap shift leftward and seal it. For the purposes of this command, a gap counts as an empty stretch between clips that runs across every track in the Timeline. The example that follows shows assorted audio/video, audio-only, and video-only clips separated by gaps. Applying Remove Gaps ripples the Timeline so those clips butt up against each other in one unbroken run, with none overlapping any of the rest.

(Top) Before removing gaps, (Bottom) After removing gaps This command is remarkably potent and far-reaching. That said, a set of firm rules makes it safer by keeping your overall A/V sync intact across timelines:

- A gap won't be closed beyond the spot where video and/or audio clips would begin to overlap each other.
- A gap won't be closed when superimposed video clips sit above it and span across it.
- A gap won't be closed when one or more uninterrupted audio clips span across it.
- By placing In/Out points on the Timeline, you can restrict which gaps get deleted to a chosen range.
- When a linked pairing of video and audio holds a gap containing an L or J split edit, the gap closes

only as far as the point where the audio or video — whichever reaches farthest — meets the closest clip beside it.

- Switching off a track's Sync Lock Control leaves that track out of the calculation for the rules above. That allows gaps on the remaining tracks to close even where clips end up overlapping whatever sits on the Sync Lock disabled track.

WARNING: Running Remove Gaps while one or more tracks have their Sync Locks switched off can throw your video/audio badly out of sync if you aren't cautious. As a safeguard, Shift-click a single video Sync Lock control (or press Option-F9) plus one audio Sync Lock control (or press Command-Option-F9) to flip every video and every audio Sync Lock control on together in one move.

### Audio/Video Linking

With DaVinci Resolve you have full command over how the video and audio belonging to a clip relate to each other in their linked state. Out of the box, DaVinci Resolve does everything it can to hold the video and audio of clips and timelines together in sync. Even so, you have a handful of options for pausing that automatic syncing whenever a particular sort of edit calls for it.

### Controlling Linked Selection

As you pick edits and clips, you also get to decide whether a clip's video and audio are chosen as a pair (linked) or kept apart. That choice governs whether anything you do to a clip's video carries over automatically to its audio, and the reverse. For the majority of situations you'll likely keep Linked Selection switched on, so that grabbing a clip's video to reposition it within the Timeline brings the audio along to be selected and shifted right alongside it. Turning off A/V linking here might knock your video and audio out of sync in ways you don't want. Still, there are many moments where you'll want to set that linked A/V relationship aside for a while — for instance, to build a split edit in which a clip's audio In point lands on a different frame than its video In point. Here you can pause Linked Selection to grab only the audio In point, then roll it backward or forward to form the split, while leaving the In point of that clip's video untouched. Once you're done, A/V linking can be switched back on. The current condition of Linked Selection is always shown by the Chain-link button over at the right end of the toolbar.

### The Link Audio/Video button

To turn Linked Selection off and on:

- Click the Link Audio/Video button (or press Shift-Command-L).

To temporarily suspend Linked Selection while making a selection:

- Hold the Option key as you click a clip or edit point to grab the video without grabbing the audio, or the other way around.

### Linked Move Across Tracks

The Timeline > Linked Move Across Tracks setting teams up with Linked Selection to govern how a linked pair of video and audio shifts within the Timeline as you drag it upward and downward to shuffle clips between tracks. Whichever behavior suits you can vary by the job in front of you, yet regardless of how this mode is configured, video/audio sync holds steady whenever you slide clips to the left or right.

- When Linked Move Across Tracks is enabled: (On by default) Dragging either half of a linked video-and-audio pair up or down in the Timeline carries the partnered item up or down too. Thus, shifting a video clip from track V1 to V2 makes its linked audio clip move from track A1 to A2 right along with it.

Linked Move Across Tracks turned on, shown before and after; relocating the video clip drags its linked audio clip along at the same moment

- When Linked Move Across Tracks is disabled: Dragging either half of a linked video-and-audio pair up or down onto a different track in the Timeline relocates only that one item, while the other linked item(s) stay on their original track. So shifting a video clip from track V1 to V2 keeps the audio clip on track A1 where it started. This makes it simple to spread video clips across separate tracks while keeping your audio clips arranged as they already were, or the reverse. Bear in mind that under this mode you can slide one half of a linked pair up and down at will, but sliding that item left or right shifts every linked item by an equal distance, so sync stays intact.

Linked Move Across Tracks turned off, shown before and after; relocating the video clip leaves its linked audio clip sitting where it was, or the reverse

### Dealing with Audio Video Sync Offsets

Holding audio/video sync is among the most critical concerns in any finished program. Yet there are occasions where you might wish to override a clip's audio-and-video sync relationship for the sake of a specific edit, so pushing a clip's audio and video apart from sync is permitted. Should you turn off Linked Selection and then shift a clip's audio or video on its own, apart from its linked video or audio partner, red "out-of-sync" indicators show up at the left of each clip's name bar, reporting the timecode offset separating that clip's audio and video. In the example below, a clip's audio and video have been pulled out of sync by Option-clicking the video and dragging it leftward.

Sync markers on a clip with audio and video out of sync Once you've shifted a clip's audio and video apart from each other, restoring them is genuinely easy: right-click the red out-of-sync indicator on any clip and pick from the commands offered:

- Slip into place: Slips what's inside the selected clip, leaving the clip put, so that it lines up with the other items linked to that clip.
- Move into place: Shifts the selected clip so that it lines up with the other items linked to that clip.
- Slip others into place: Slips what's inside every other item linked to the selected clip, leaving them put, so that all of the linked items line up.
- Move others into place: Shifts every other item linked to the selected clip so that all of the linked items line up.

### Commands in the contextual menu of sync tooltips

### Manually Unlinking and Relinking Audio and Video

By default, any clip you bring into DaVinci Resolve arrives with its video and audio linked, which keeps the relationship and sync of a clip's audio and video components easy to preserve while you edit. Even so, plenty of situations call for overriding this automatic relationship — whether that means severing a clip's A/V linking outright, or breaking and then relinking it differently, or to other clips entirely. Ways to permanently rework audio/video linking within the Timeline:

- To unlink audio and video from one another: Pick a clip, then right-click it and pick Link from the contextual menu (or press Option-Command-L). Once unlinked, clips show no chain icon ahead of the clip name in the Timeline.
- To link audio and video clips to one another: Hold Command and click both an audio clip and a video clip to select the two, then right-click your selection and, from the contextual menu, choose Link (or press Option-Command-L). At that point a chain icon turns up in front of the name of any linked clips within the Timeline.

(Left) video and audio that are linked, marked by a chain icon beside the clip name; (Right) audio and video that aren't linked carry no such icon.

### Linking Multiple Clips in the Timeline

Linking isn't limited to audio and video clips that already sync together, though. You're free to link as many video and audio clips as you like so they can be selected, moved, and edited as a single unit, even ones that were never intended to be in sync. That turns linking into an organizing device every bit as much as a sync-management one.

Here are some examples of how you can use this:

- You can tie a text generator carrying a subtitle to the clip it runs alongside.
- You can tie a stack of overlapping audio sound effects to the video clip they go with.
- You can tie off-camera audio to the on-camera shot it belongs to.
- You can tie the background and foreground clips of a green screen composite together, with the sound from each.

Linking several clips in the Timeline behaves just like linking one audio and video clip pair; each linked item shows a chain icon at the left of the clip name, and pausing linked selection to knock any single clip out of sync triggers an "out-of-sync" indicator. Several audio and video items hand-linked into one unit that acts like a single clip on the Timeline while Linked Selection stays on

### Commands for Slipping Audio/Video Sync

A further group of commands under the Trim > Slip Audio submenu lets you slip what's inside one or more chosen clips to adjust the sync between their audio and video, working either in full-frame steps or in sub-frame steps for clips whose borderline sync you'd like to tighten up.

- One Frame Forward (Option-Period)
- One Frame Reverse (Option-Comma)
- One Subframe Forward (Option-Right Arrow)
- One Subframe Reverse (Option-Left Arrow)
