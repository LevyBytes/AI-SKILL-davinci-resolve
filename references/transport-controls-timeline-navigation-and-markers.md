# Transport Controls Timeline Navigation And Markers

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Transport Controls, Timeline Navigation, and Markers

Distinct transport control, zooming, and scrolling choices live on the Fairlight page that the rest of the DaVinci Resolve pages lack, and they let you handle audio more productively. This chapter explains getting around the Fairlight take on the Timeline.

### Transport Controls and JKL Navigation

Owing to the audio-centered workflow of the Fairlight page, its transport and playback controls aren't the same as the ones over on the Media, Edit, Color, and Deliver pages.

### Transport Controls

### Fairlight page transport controls

The Fairlight transport controls are likewise built to echo the matching controls found on the Fairlight control panels. They cover these functions:

- Rewind and Fast Forward: Kicks off sped-up playback along the Timeline either way. Hitting either button repeatedly ramps the motion up, stepping through 8x, 24x, 60x, 150x, and 360x play speeds.
- Play: Plays forward. The same as hitting the Spacebar or L keys with playback stopped.
- Stop: Halts playback. The same as hitting the Spacebar or K keys while playback runs.
- Record: Begins recording provided you've patched an audio source to a track, and provided that track is

enabled for recording. For more information about recording, see Chapter 173, “Recording.”

- Loop: Switches looped playback on and off. With looped playback turned on, playback loops at the

end of the Timeline, loops too when you invoke the Play In to Out command, and keeps looping on its own until you halt playback.

- Automation controls: Pressing this button reveals the automation toolbar.

For more information about recording automation, see Chapter 178, “Mix Automation.”

### Using JKL to Control Playback

Plenty of editing applications share the JKL keyboard shortcuts, and seasoned editors regard them as among the handiest playback and editing controls going. Below is a rundown of the numerous ways you can put these three keyboard shortcuts to use, playing through clips and timelines while you work.

### J K L Press J repeatedly

### Press L repeatedly Shift-J

Runs backward at 100%. Halts playback. Runs forward at 100%. Steps up the reverse play speed with every press of J, across a spread of fast-reverse speeds. Steps up the forward play speed with every press of L, across a spread of fast-forward speeds. Runs in fast reverse.

Shift-L K+J K+L Holding K as you tap J Holding K as you tap L

Runs in fast forward. Runs backward in slow motion (audio plays back slowed too). Runs forward in slow motion (audio plays back pitch-corrected on OS X). Nudges the playhead back by a single frame. Nudges the playhead forward by a single frame.

When you're driving Fairlight from the keyboard, this is likely to turn into one of your principal means of shifting the playhead about within DaVinci Resolve.

NOTE: Every keyboard command this document lists assumes the DaVinci Resolve keyboard customization preset. Remapping keyboard commands to layouts you might know better, such as Premiere Pro or Pro Tools, carries real benefits. That said, if their command set lacks the same commands the DaVinci Resolve keyboard commands provide, they won't behave identically. As an example, the Pro Tools keyboard preset offers no J-K-L timeline navigation.

### Dragging the Playhead to Scrub

The playhead can also be dragged side to side to scrub across the visible stretch of the Timeline by clicking and dragging anywhere inside the Timeline ruler up top of the Timeline, just under the toolbar. When you're zoomed in at a sensible editing level, scrubbing the playhead with your pointer yields smooth, tape-style slow and fast audio playback, handing you plenty of precision as you trim audio.

### Looping Playback

A pair of controls run looping over on the Fairlight page, much like the way looping behaves on the Edit page.

- Loop: Command-Forward Slash (/). Switches looped playback on and off. With looped playback on, playback you kick off using any of the commands below will loop on its own until you halt playback.
- Play In to Out: Option-Forward Slash (/). Once you've bracketed a portion of a clip or timeline using In and Out points, this command gives you a preview of how that stretch plays.

### Loop Jog Scrubbing

For now offered only on the Fairlight page, picking Timeline > Loop Jog lets a short sample preview play back as you scrub the playhead along the Timeline. That can help you pick out snippets of dialog or music while rapidly scrubbing through tracks, in cases where you're hunting for particular lines or music cues. It likewise lets that short sample preview loop without end while you hold the playhead on a frame, so you can pause mid-scrub and hear (by default) the latest 80 ms ahead of the playhead as it loops. A couple of settings within the User Preferences let you tailor this behavior.

- Loop Jog Alignment: Three choices let you decide whether the audio loops Pre the playhead's position, Centered on the playhead, or Post the playhead's position.
- Loop Jog Width: A field lets you set how many milliseconds of audio loop once Loop Jog is on. How many milliseconds of audio a single frame works out to depends on the video's frame rate. To illustrate, with a 25 fps frame rate, the math is 1000/25 = 40 ms per frame, meaning the default value of 80 ms covers two frames' worth of looping.

### Moving the Playhead Using Timecode

Absolute or relative timecode entry can be used to shift the playhead within the Timeline. Entering timecode lets you nudge the playhead with great accuracy or leap to particular timecode values in a hurry.

### How to Enter Timecode Values

To enter timecode, type each pair of hour, minute, second, and frame values going left to right, where a period stands in for a pair of zeros to speed entry. Whatever numbers you type show up in the Timecode field at the upper right-hand corner of the focused Viewer. Once you've finished typing, hit the Enter key to run the timecode command. These are the rules for timecode entry:

- Whatever right-most pair of timecode values (or period) you type always stands for the frame number.
- A period sitting to the left or the right of any number you type counts as a pair of zeroes.
- One period set between two numbers counts as either a single zero, or is disregarded when it falls

between two pairs of numbers.

- Any value pairs left untyped to the left of your entry are taken to be whatever those values

held before the timecode you typed; this lets you type partial timecode values easily even where the Timeline begins at hour one.

- Typing colons or semicolons isn't required.

IMPORTANT: On full length keyboards, the number pad supports implicit timecode entry without your having to trigger the Go To Timecode action (=). During a multicam or printer light operation, any number pad key that's already mapped keeps triggering actions such as swapping angles or stepping color values. With the number keys above the letters on a keyboard, you must first pick Go To Timecode (=), or click inside the field you mean to alter, ahead of typing a fresh value.

### Absolute Timecode Entry

You enter absolute timecode just by typing the timecode value you'd like the playhead moved to, and once you press the Return key, the playhead jumps to that timecode value.

Below are a few examples of absolute timecode entry done this way:

Original TC Value 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10

User-Typed Value 15245218 2.. 15 12 1.2 1115.. 23...

New TC Value 15:24:52:18 01:02:00:00 01:10:10:15 01:10:10:12 01:10:01:02 11:15:00:00 23:00:00:00

### Relative Timecode Entry

You enter relative timecode by leading the timecode value off with a plus (+) or minus (–). Putting a plus means the value you type gets added onto the current timecode value, so as to offset the playhead away from where it currently sits. Putting a minus means the value you type gets taken off the current timecode value. Below are three examples of relative timecode entry:

### User-Typed Value +20. +3.. –5

Result 00:00:20:00 is added to the current timecode value. 00:03:00:00 is added to the current timecode value. 00:00:00:05 is subtracted from the current timecode value.

### Clip, Marker, and Track Navigation

The Up and Down Arrow keys serve to shift the playhead between one edit point and the next on the Fairlight page Timeline, exactly as on the Edit page Timeline. But holding Command-Option while you work the Arrow keys hands you Fairlight page-specific behaviors meant for moving among clips, markers, and tracks on the Fairlight page in a manner unlike the other DaVinci Resolve pages yet well suited to how the Fairlight page works. This section runs through the basics.

### Selecting Tracks

The behavior of the Arrow keys is set by which tracks you've selected.

- In Pointer mode: Tracks get selected by clicking or Command-clicking (for several tracks at once) anywhere across the background area or on the track number within the track headers. Clicking and dragging in the track header lets you draw a bounding box to grab several tracks. Pointer mode won't make selections in the Timeline's empty areas.
- In Range or Focus mode: You select tracks by clicking or Command-clicking anywhere, whether over the header's background, on the header's track number, or across any unused portion of the track itself inside the Timeline. A click-and-drag here lets you draw a bounding box to grab several tracks.

### Moving the Clip Selection

The Command-Option-Left and Command-Option-Right Arrow key shortcuts serve to shift the playhead left and right within the Timeline, hopping clip to clip or marker to marker. The way these keys behave turns on whether or not one or more tracks sits selected in the Timeline.

- If no tracks are selected: The Left and Right Arrow keys leap the playhead from one Timeline marker to the next. Clip markers get skipped.
- If one or more tracks are selected: The Left/Right Arrow keys leap the playhead among clip In points, clip Out points, and Timeline markers.

### Moving the Track Selection

The Command-Option-Up and Command-Option-Down Arrow key shortcuts serve to shift the track selection up and down within the Timeline, altering which tracks are selected. By altering which tracks sit selected, you change which clip's In and Out points get used to leap the playhead around the Timeline. With no tracks selected, nothing occurs.

### Zooming and Scrolling

The Fairlight page offers several ways to zoom into and out of the Timeline, plus scrolling once you're zoomed far enough that your edited run of clips spills past the left and right edges of the visible timeline.

### The Playhead

Zooming always centers on wherever the Playhead sits. By default the Playhead travels along the Timeline during playback. Fairlight, though, gives you the choice of a Fixed Playhead, where the Timeline shifts while the Playhead stays centered.

You'll find the Playhead options inside the Timeline Scrolling panel.

### Setting the Zoom Level of the Timeline

Your working style dictates which of the several Timeline zoom-in and zoom-out methods suits you. Using the Vertical Zoom slider: Two sliders sitting at the toolbar's right edge handle both vertical and horizontal zoom. The first scrolls you vertically, surfacing more detail across your waveforms' height. Where no tracks sit selected, the zoom centers on the Timeline's top audio track. Where one or more tracks sit selected, the zoom centers on the uppermost selected audio track. Using the Horizontal Zoom slider: That same right-side toolbar pair of sliders covers vertical and horizontal zoom alike. The second zooms you horizontally, surfacing more detail across your waveforms' width. Pressing Command-Equal (=) and Command-Minus (–): Both Command-Equal (which also goes by Command-Plus) and Command-Minus zoom you horizontally into the Timeline. Use Shift-Z to Zoom to Fit: Horizontal zooming via Command-Z shrinks every clip in your program to whatever width the Timeline has on hand. Using scroll controls of your pointing device to scroll horizontally: Hold the Option key as you spin the scroll wheel (or scroll control) on your pointing device and you zoom horizontally into the Timeline. Hold the Command key as you spin the scroll wheel and the Timeline slides to a time earlier or later than now, leaving the Playhead put. Using scroll controls of your pointing device to scroll vertically: Hold the Shift key as you spin the scroll wheel (or scroll control) to zoom vertically inside the Timeline. In this case, where no tracks sit selected, the zoom centers on the Timeline's top audio track. Where one or more tracks sit selected, the zoom centers on the uppermost selected audio track. Using the Fairlight panel's Jog/Edit wheel: With a Fairlight panel on hand, holding the ZOOM button down as you spin the Jog/Edit wheel zooms into the Timeline at the playhead's location.

### Scrolling Through the Timeline

No matter how tightly you're zoomed into the Timeline, once you're zoomed far enough that clips run past the Timeline's visible area, scroll bars show up below. Should the playhead be offscreen, a little orange tic mark flags where it sits relative to the whole timeline, which the full width of the scroll bar's background stands in for. When you drag the playhead, or use any of the transport controls or playback key shortcuts to travel through the Timeline, the Timeline's contents refresh each time the playhead strikes the left or right edge of what's on view.

### Using Flags

Flags exist to mark a whole clip, and they also flag every other clip in the Timeline drawing on the same Media Pool source clip, which makes for a quick way to spot which clips in a given timeline trace back to the same Media Pool source. Flags appear across every page of DaVinci Resolve, which makes them a fine means of following media from one page to another.

The Flag and Marker buttons and pop-ups. Clips can take several flags, in a range of colors to pick from. Beyond flagging particular media files, flags come in handy for sorting by column within the Media Pool, plus a range of other tasks. Any time you type text into a flag, it shows a small dot signaling there's more information tucked inside. Ways to flag clips over on the Fairlight page:

- To flag a clip: Pick one or more clips, then either click the Flag button to flag that clip in the current color, or click the Flag pop-up on the toolbar to pick a different color before clicking the Flag button. Over on the Edit page, flags show up in the Timeline laid over the name bar of each clip.
- To remove all flags from a clip: Pick one or more clips holding flags you'd like gone, then click the Flag pop-up on the toolbar and pick the top “Clear All” option.
- To change the Flag color or remove individually: A double-click on the clip's Flag icon brings up a Marker dialog box where you can recolor the Flag, clear the flag, or jot down a note about it.

### Using Markers

Markers serve to draw attention to one particular frame inside a given clip. Each marker can be colored on its own and can carry custom name and note text. Any time you type text into a marker, that marker shows a small dot signaling there's more information tucked inside. After placement, with snapping switched on a marker snaps onto In and Out points, edit points, the playhead, plus other markers, which makes it simple to wield markers to “measure” the edits and trims you perform within the Timeline. Markers appear across every page of DaVinci Resolve, which makes them a fine means of following frames in clips and particular moments in the Timeline from one page to another.

Markers can be added to the Timeline (within the Timeline ruler) or onto clips. The full set of steps for placing and editing markers within the Fairlight page's onscreen interface is the same as on the Edit page, so to read more, consult Chapter 41, “Marking and Finding Clips in the Timeline.” For the moment, here's a recap.

### Adding Markers to Clips

The steps below explain adding markers onto clips within the Timeline of the Media page. To mark a clip within the Timeline, do one of these:

- Pick one or more clips you'd like to mark, then bring the playhead to the frame of a selected clip within the Timeline, and click the Marker button on the toolbar (or press M) to drop a marker on that frame in the current color (if several overlapping clips are selected, you'll add a marker onto all of them).
- To set a marker mid-playback and pop open the marker dialog right away to type a name or note inside it, pick one or more clips you'd like to mark, play through the selection until you're ready to set a mark, then press Command-M. Playback halts until you type some text and shut the marker dialog again, whereupon playback resumes.
- Pick one or more clips you'd like to mark, then click the Marker pop-up to pick a different color, and click the Marker button.

### Adding Markers to Timelines

Markers in any color can also be set into the Timeline ruler to flag particular times for later reference, or to attach notes about issues you want to keep tabs on. Bear in mind that every marker set onto clips or in the Timeline likewise turns up within the Mini-Timeline of the Color page, which makes it easy to drop notes referencing specific audio cues that may prove useful while editing or grading. To mark the Timeline itself, confirm every clip is deselected, then do one of these:

- Click the Marker button (or press M) to drop a marker in the currently selected color into the Timeline ruler.
- To set a marker mid-playback and pop open the marker dialog right away to type a name or note inside it, pick one or more clips you'd like to mark, then press Command-M. Playback halts until you type some text and shut the marker dialog again, whereupon playback resumes.
- Click the Marker pop-up to pick a different color, and click the Marker button.
- Right-click within the Timeline ruler and pick a marker color out of the Add Marker submenu of the

contextual menu.
