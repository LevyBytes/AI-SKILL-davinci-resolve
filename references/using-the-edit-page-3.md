# Using The Edit Page (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Jog control: Click the Jog control and drag it side to side to creep through a clip or the Timeline one frame at a time.
- Transport controls: Reading left to right, this set comprises Jump to First Frame, Play Reverse, Stop, Play Forward, and Jump to Last Frame.
- Loop Playback: Turns looped playback on or off. You can also toggle looping through the Playback > Loop/Unloop command (Command-/). With it on, every playback command jumps back to the start once it reaches the end of that command’s range. The In and Out points set in the Source or Timeline Viewers will not kick off looping. As an illustration, with looping on the Play command runs through the whole clip or timeline, then circles back to the start once the end arrives and resumes on its own. By contrast, the Play Around command begins at the head of pre-roll, runs out through the post-roll, then loops straight back to the head of pre-roll, repeating that cycle until you halt it.
- Match Frame: From the Source Viewer, Match Frame tries to nudge the Timeline playhead onto the frame currently shown for the clip in the Source Viewer. From the Record Viewer, Match Frame loads the Media Pool clip matching the one under the playhead into the Source Viewer, aligning its In and Out points and playhead with those of the clip on the Timeline.
- In/Out buttons: Drops In and Out points that mark out a span of the clip, or of the Timeline, ahead of carrying out various sorts of edits.
- Jog bar: Within the Source Viewer, drag along the jog bar to shift the Source playhead and scrub the clip. On the Timeline tab, dragging moves the playhead across the whole program.
- Skim Playhead: To skim footage within any viewer across the Media, Cut, Edit, Color, and Deliver pages, hold the C key down and drag the pointer to and fro inside the viewer.

Transport Controls and Important Playback Controls Although how the primary transport controls behave is likely self-evident, the editor has access to further playback controls that might not turn up as easily. For a deeper look at transport controls, consult Chapter 35, “Preparing Clips for Editing and Viewer Playback.”

### Simultaneous Audio Waveform Display in the Source Viewer

With the Source Viewer set to Source, a pair of entries in the Option menu can overlay an audio waveform along the viewer’s lower edge, atop the video of whichever clip is currently chosen. Show Zoomed Audio Waveform: Presents a magnified slice of audio that scrolls along as the clip plays. Handy for spotting dialog and music cues during playback of a clip. Show Full Clip Audio Waveform: Displays the audio waveform across the clip’s complete source media. The stretch of audio between the In and Out points you placed in the Source Viewer is highlighted. Handy when you want to move around that clip by treating the audio waveform as a guide.

The Source Viewer with “Show Full Clip Audio Waveform” enabled

### Cinema Viewer Mode

Either the Source or Timeline Viewers can be expanded to fill the whole screen via Cinema Viewer mode, reached through Workspace > Viewer Mode > Cinema Viewer (P); the selected viewer takes over the display, which suits a test screening of your edit free from the clutter of the DaVinci Resolve Edit Page UI. That command flips Cinema Viewer mode on and off.

### Viewer Indicators

Particular frames cause indicators to show up in the Source or Timeline viewers. As an example, when the playhead sits on the very first or final frame of media a given clip holds, markers surface in the lower-left or lower-right corner of the frame to signal that no further media exists in that direction.

### The first and last frame clip indicators

When the Timeline playhead rests on the first black frame that follows the Timeline’s final video clip, an end of sequence indicator shows up in the Timeline Viewer, telling you that the frame on screen is the last of the current run of clips even though the playhead actually sits on black. That makes your work easy to follow as you are first stringing clips together.

### The end-of-sequence indicator

### Other Viewer Options

Further overlays and settings exist for tailoring the viewer’s appearance.

- Safe Area and Guides: From the upper‑right corner of the Timeline Viewer, you can enable and pick one or several Safe Area guides to lay over the Viewer. This lets you readily confirm that the key action in the frame stays well composed against various delivery requirements.
- Show Checkerboard, Black, Gray, or Alert Red Backgrounds in Viewers: Choosing Viewer Background within the Timeline View options recolors any empty region of the Viewer to the chosen option, which makes it simpler to tell apart the parts that read black due to blanking from the parts that are merely empty because of how the image has been zoomed or panned.

### The Safe Area selector

### Fast Review in the Timeline Viewer

Fast Review runs your timeline forward at varying fast-forward rates, with each rate tied to how long the corresponding clip on the Timeline is. Clips of greater length scroll by faster than brief ones. The purpose of the feature is to let you skim quickly across a heavy load of material on a timeline. To call up Fast Review on your Edit page Timeline, choose Playback > Fast Review. Tapping K or the spacebar drops you back into the usual JKL playback mode. Should you rely on the feature regularly, you can map Fast Review onto a chosen key from the Keyboard Customization window. NOTE: Fast Review applies only to timelines in the Timeline Viewer, not to clips in the Source Viewer.

### Opening Clips in the Source Viewer

Clips can be loaded into the Source Viewer in two ways, and which one is active comes down to the “Live Media Preview” setting in the Viewer options menu (that three-dots menu in the Viewer’s top right corner).

- With Live Media Preview on (the default), skimming a thumbnail in the Media Pool also surfaces the skimmed frame in the Source Viewer, so in effect every clip you skim in the Media Pool opens into the Source Viewer. While you skim, the thumbnail’s playhead stays tied to the playhead shown on the Viewer’s jog bar.
- With Live Media Preview off, you have to either double-click a Media Pool clip to bring it into the Source Viewer, or highlight a Media Pool clip and hit the Return key to load it there. Whichever route you take is entirely down to taste.

### Timeline Viewer Edit Overlays

When you drag a clip out of the Media Pool or Source Viewer onto the Timeline Viewer, edit overlays appear so you can settle on the type of edit simply by deciding which overlay receives the clip.

The overlay that surfaces as you drop a clip onto the Timeline Viewer offers a spread of edit choices This overlay lays out every edit type DaVinci Resolve provides. That roster covers Insert and Overwrite, Replace, Fit to Fill, Place On Top, plus Ripple Overwrite and the Append at End edit — and each one is reachable from the Edit menu as well. It is a handy way to perform three-point edits if drag-and-drop editing appeals to you, while also serving as a tidy refresher on the edit types on hand, given how many options there are. Out of the box, the wider empty zone to the left of these overlays falls to the highlighted Overwrite overlay, and the smaller buttons each carry out one of the remaining edit types on offer. That said, the User Preferences’ Editing panel holds a “Timeline overlay retains the last performed action” checkbox; tick it and DaVinci Resolve hangs onto whichever edit type you last used and highlight it on this overlay each time you drag a fresh clip across the Timeline Viewer, signaling that your most recent edit is now the default whenever you drop clips left of the overlay. To illustrate, with that option on, once you do a place on top edit, the next clip you release into the empty zone left of the overlays produces another place on top edit. The option ships off by default.

### Copy and Paste Timecode in Viewer Timecode Fields

Across the Media, Edit, and Color pages, right-clicking most Viewer timecode fields brings up a contextual menu offering Copy and Paste commands for moving timecode values around. Alternatively, click inside a timecode field and use the ordinary Copy (Command-C) and Paste (Command-V) keyboard shortcuts. The trick even carries across pages. Whatever timecode you paste has to be legitimate timecode — for instance, 0 hour timecode cannot be pasted onto a 1 hour timeline.

Right-clicking on a timecode field to use the Copy Timecode command

### Export The Current Frame from The Viewer

Exporting a still frame from the Viewer is now possible on the Media, Cut, and Edit pages. Follow these steps to send a still frame out of the Viewer: 1 Pick either the Source or Timeline viewer as the export source. 2 Drive the Viewer’s playback controls to land on the frame you want exported. 3 Choose File > Export > Current Frame as Still. 4 Type the still frame’s name in the File System viewer. 5 Set the still frame’s desired format in the File System viewer. 6 Press the Export button.

### Metadata Editor

A Metadata Editor lives on both the Media and Edit pages. On the Edit page, the Metadata Editor appears in the very spot the Inspector uses, right of the Source and Timeline Viewers. Pick a clip in the Media Pool or Timeline and its metadata shows up in the Metadata Editor, with the title bar noting whether the clip under review comes from the Timeline or the Media Pool. Select several clips and only the final one’s details show. Along its header the Metadata Editor carries read-only facts about the chosen clip — the file name, directory, duration, frame rate, resolution, and codec among them. Since there is such an abundance of metadata fields, a couple of drop-down menus up top let you swap which set of metadata the Metadata Editor presents. Metadata Presets (on the left): Where you have built your own custom metadata sets through the Metadata panel of the User Preferences, this drop-down picks which one is shown. Oddly enough, it sits at “Default” by default. Metadata Groups (on the right): This drop-down toggles among the assorted metadata groups on offer, each clustered around particular tasks or workflows. At its core the Metadata Editor is a run of editable fields below the header where you can examine and change the various metadata criteria available. For more on editing clip metadata and on building custom metadata presets, see Chapter 19, “Using Clip Metadata.”

A Timeline clip’s Clip Details panel as shown in the Clip Metadata Editor

### Inspector

Opening the Inspector gives you a place to tailor a clip’s compositing, transform, and cropping parameters, plus its clip-specific retime and scaling options. On top of that, the Inspector is where you adjust the parameters of any transitions, titles, and generators in the Timeline so as to shape their effect.

### The Inspector, opened and showing a clip’s parameters

While the Inspector is open, the Source and Timeline viewers shift leftward to sit beside it as it shows the chosen clip’s parameters. That said, if your monitor’s resolution falls short, opening the Inspector can push the Source Viewer out of sight. Ways to bring up parameters in the Inspector:

- To reveal a video or audio clip’s transform settings while the Inspector is shut: Highlight the clip, then click the Inspector button over at the far right end of the Edit page toolbar.
- When the Inspector already stands open: Merely selecting a clip or effect exposes its controls there.
- When the Inspector is shut: Double-clicking any transition opens it on its own.

Across its top the Inspector carries assorted buttons for jumping between different parameter pages. For instance, select a clip holding both audio and video parts and the Inspector puts Video and Audio buttons up top so you can move between each batch of controls.

### Timeline

The Timeline displays whichever timeline you double-clicked over in the Timelines browser. This is where you build programs from the ground up or pull in sequences created elsewhere. With imported programs, the Timeline gives a visual picture of the cut that helps you confirm the project came in correctly, inspect the media behind each clip in the program, and carry out any editorial steps needed to ready a project for grading (replacing or adding clips, layering composites, and tweaking composite modes or transitions, say).

### An edited timeline

- Timeline Ruler: Along the Timeline Ruler you see the program’s timecode, while the playhead points to the present frame of the present clip. The clip that the playhead crosses is the one you will tackle on the Color page. Drag inside the Timeline Ruler to slide the playhead. Markers you add to the timeline turn up within the Timeline Ruler as well.
- Playhead: This playhead stays synchronized with several others — the one on the Timeline Viewer’s jog bar, those riding the Mini-Timeline and Thumbnail timeline of the Color page and Cut page, and the playhead on the Deliver page. Beyond that, the Edit Index event matching the clip the playhead crosses is highlighted for you automatically.
- Timecode field: Reports the present timecode value that goes with where the playhead sits.
- Video Tracks: Multiple video tracks are supported by DaVinci Resolve. To the left of each track sits a header

area holding several controls.

- Track Header: Within the Track Header sit the various controls for selecting tracks, locking or unlocking them, and switching them on or off. Each track header additionally notes the clip count on that track. The Track Header holds these five controls, reading left to right:

The Track Header area, where each track’s controls reside Track Color: Any track can be tinted with one of 16 distinct colors. Those color codes carry over to the Edit page Mixer along with the Fairlight page Mixer and Audio Meters. To assign a fresh color to a track, right-click its track header and pick from the Change Track Color submenu. Source Track Selector: A pair of rectangular icons under columns marked V1, A1, A2 and so on. The blue left-hand column stands for the tracks inside source clips chosen in the media pool or open in the source viewer. The red right-hand column stands for the destination tracks on your timeline. The Source Track Selector is how you map a given source-clip track onto a particular timeline track. Click a track’s number to flag that track for various editing operations; a flagged track glows red or blue, whereas an unflagged one carries no highlight. Lock Track button: White while on, dark grey while off. Once a track is locked, its clips cannot be swapped, repositioned, or otherwise edited, though clips on locked tracks remain gradable. The track then shows a grey mesh pattern laid over it in the timeline, a cue that it is off-limits to changes. Sync Lock: On out of the box, white when that track is flagged and dark grey when it is not. The icon governs how that track’s clips behave during a ripple edit. Switched on, it ripples alongside the other tracks (say an item is ripple deleted, and the remainder of the timeline slides left to close the gap); switched off, ripple acts solo on that track and skips the ripple from edits on other tracks. Solo (Audio Track Only): Clicking this “S” icon silences every other audio track and plays only the chosen one. Several Solo tracks can be flagged at once so you hear just that selection. Enable Track/Mute button: A small film icon sits on (enabled) by default; a slash across it plus a grey wash over the track itself flags a disabled track. The control switches tracks on and off. Clips on a switched-off track stay out of the viewer, are absent from the Color page, and cannot be rendered or output. On Audio tracks this becomes the Mute button (M). Audio Channel Type indicator: Audio tracks additionally reveal which channel layout the track runs, citing the channel count for mono, stereo, 5.1, 7.1, and adaptive. Track Name: Every track carries a name that starts out as the track type plus its number, like Video 1, Audio 1. You are free, though, to click any track’s name and rewrite it however you wish. As an example, you might retitle each audio track by the kind of audio going onto it — Production, Ambience, SFX, or Music. Those track names also serve to label each track’s channel in the Edit page Mixer and the Fairlight page Mixer. Number of clips: How many clips occupy that specific Timeline track is shown, but only when the track stands tall enough to make room.

- Vertical and horizontal scroll bars: When your project runs wider than the Timeline’s present width, or the video-track stack rises above the Timeline’s present height, these scroll bars let you drag your way around the program.
- Individual Timeline track resizing: You can resize any single Timeline track on its own by dragging the top divider in its Track Header area.

Dragging a single timeline track’s top border within the Track Header to resize it

### Timeline Options

A range of methods exists for tailoring particular Timeline elements and behaviors.

### Fixed Playhead Mode in the Timeline

The fixed playhead mode is chosen from the Edit page’s Timeline View options. With this option active the playhead stays pinned at the timeline’s center while the timeline’s tracks glide beneath it, much as on the Cut page.

Choosing Fixed Playhead mode from within the Timeline View options Selection Follows Playhead Starting with DaVinci Resolve 17, the Clip selection ceased to travel automatically with the playhead. In its place, a fresh batch of commands lets you form and shift a selection by holding the Command key while tapping the Up, Down, Left, and Right Arrow keys. That makes it possible to grab clips above and below the present track as well as to either side, all separate from the playhead. To restore the Clip Selection mode to its old habit of automatically grabbing the top clip it crosses, choose Timeline > Selection Follows Playhead.

### Show Playhead Shadow

By default the Timeline draws the playhead as a lone line marking the start of the frame on view in the Timeline Viewer. You can, however, pick Show Playhead Shadow from the User Preferences UI Settings to wrap the playhead in an orange-ish backdrop. The shadow makes the playhead’s spot easier to read, and it doubles as a gauge on projects where you care to picture a particular offset, measured in frames, on either side of where the playhead currently sits. Adjust that offset using the Pre- and Post-Playhead Shadow Length parameters; you will find them under the User Preferences’ Editing panel, where they govern how many frames get shadowed ahead of and behind the playhead. Out of the box the playhead shadow runs 5 frames long.

(Left) the playhead in its default form; (Right) the same playhead with the optional shadow turned on TIP: Dial the “Pre-playhead shadow length” down to 0 while pushing the “Post-playhead shadow length” up to 1, and you get a “Media Composer-style” playhead that conveys the current frame’s duration.

### Enabling and Disabling Audio Scrubbing

Audio scrubbing comes switched on by default, so dragging the playhead to and fro with the mouse plays audio. That helps while you hunt for audio cues, yet it can be a nuisance when your attention is solely on the picture. To switch audio scrubbing on or off: Choose Timeline > Audio Scrubbing (Shift-S)

### Playback Post-Roll

Lets the playhead keep running beyond the Timeline’s final clip for a span matching the “Post-roll time” Project Setting in the Editing panel. It suits editors who want a brief stretch of playback once they cut or fade to black past the last frame of audio and video on the Timeline. To switch playback post-roll on or off: Choose Timeline > Playback post-roll

### Switching Among Multiple Timelines

Timelines sort just like any other clip in the Media Pool. The procedures below cover opening timelines and moving between them. To change timelines, do any one of these:

- Double-click a timeline in the Media Pool on any page.
- Switch on Stacked Timelines from the Timeline View Options menu in the Edit page toolbar, and every timeline you open shows up as a tab. Click a tab to jump to that timeline.
- On the Edit page Timeline Viewer, grab a timeline from the Timelines drop-down menu at the viewer’s top.
- On the Color page, grab a timeline from the Timelines drop-down menu at the Viewer’s top.
- On the Fairlight page, grab a timeline from the Timelines drop-down menu sitting left of the transport controls.

### Toolbar

Mid-way along the toolbar above the Timeline, a cluster of buttons gives you the various tools and options for carrying out different editing functions.

### Buttons in the toolbar

### Selecting the Timeline View options
