# Preparing Clips For Editing And Viewer Playback (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

DaVinci Resolve includes tailored arrangements for vertical projects and timelines. The moment a vertical project or timeline opens, the interface shifts on its own to an arrangement suited to vertical viewers across the Cut, Edit and Color pages. Open an ordinary landscape project or timeline instead, and the interface reverts on its own to the prior arrangement, with nothing required from you. To adjust how this works, head to Preferences > User > UI Settings > Use optimized UI layouts for vertical video. Leaving that box unticked keeps the standard horizontal arrangement in place, even when a timeline holds vertical video.

The interface reshapes itself on its own to suit timelines built around vertical video.

### Option to “Stop and Go to Last Position”

Playback > Stop and Go to Last Position puts DaVinci Resolve into a mode that, each time you halt, sends the playhead back to the spot where playback originally kicked off. Audio editing is where this proves handiest, though you can call on it whenever you like. While driving the Viewer with the JKL keys under this mode, “K” holds the playhead at its current spot, whereas the space bar (stop) sends it to the last position. The same setting can be reached by right-clicking the Stop button found in the transport controls of any viewer. Doing so opens a contextual menu that lets you flip “Stop and go to last position” on or off as your default behavior.

### Enabling and Disabling Audio Scrubbing

Out of the box, audio scrubbing is turned on, so dragging the playhead forward and backward with the mouse produces sound. That behavior helps when you’re hunting for audio cues, yet it can pull your attention away when the picture alone is your concern. To switch audio scrubbing on or off: Choose Timeline > Audio Scrubbing (Shift-S).

### Playback Post-Roll

Lets the playhead keep rolling beyond the final clip in the Timeline, for a span matching the “Post-roll time” Project Setting found in the Editing panel. It suits editors who like to feel a brief stretch of playback once they’ve cut, or faded to black, past the last frame of picture and sound in the Timeline. To switch Playback Post-Roll on or off: Choose Timeline > Playback Post-Roll.

### Source Tape in the Edit Page Source Viewer

Source Tape, which originated on the Cut page, can likewise be reached from the Edit Page Source Viewer. Turning it on is a matter of picking a bin and then clicking the Source Tape icon at the upper right of the Source Viewer, or hitting Shift-Q. With this turned on, every clip held in the bin you currently have open, plus any subfolders nested inside it, of the Media Pool surfaces in the Source Viewer as a “stringout” within the scroll area along the bottom of the Viewer. There, the clips line up back to back in one long strip, sequenced according to the sort order. That arrangement makes scrubbing across an entire set of clips painless while you work out what you’d like to use. During playback, whatever clip the playhead happens to cross is highlighted in the Media Pool, so you always know which clip is on screen, and you can drop In and Out points onto any clip within the Source Tape.

Editing directly from the Source Tape is also possible on the Edit page. For that, click the Source Tape icon located in the Source Viewer (circled red). When you have a great deal of footage to watch and assess, the Fast Review button now sits at the lower left of the Source Viewer too. Clicking it bumps playback up to a quicker speed, scaled to the duration of whatever clip is showing in the Source Tape.

### Limiting the Source Tape Scope by Folder Structure

Once a project balloons, keeping a whole film’s media loaded in the Source Tape at all times grows cumbersome. You can, however, confine the Source Tape’s reach at the bin level. Clicking straight on bins within the Bin list lets you widen or tighten the Source Tape’s reach in a hurry. Click a bin called Scene02, for instance, and the Source Tape narrows down to display only the clips housed in that folder. Click back onto Master and the Source Tape widens out once more to present clips across every folder. The same trick helps when you’re moving through bin hierarchies that mirror the camera’s original file system. Picture a camera that writes each memory card to its own folder, then stores every individual clip in a separate folder nested within that one. Pull that file system into the Media Pool through the Create Bins option, and those nested tiers carry over into the Media Pool bin hierarchy. From then on, clicking a card bin in the Source tape takes you straight to all of that card’s clips, instead of presenting a heap of separate sub-bins.

### Moving the Playhead Using Timecode

Both absolute and relative timecode entry are at your disposal, either to shift the playhead within the Source and Timeline Viewers, or to nudge or trim whichever edit points or clips you’ve selected. As you work through the Timeline, typing timecode lets you reposition the playhead with great precision, or leap to particular timecode values in an instant. TIP: The timecode-entry approach laid out here underpins a wide range of commands that call for timecode entry, and it’s built around fast, efficient editing.

### How to Enter Timecode Values

As you enter timecode, work left to right through each pair of hour, minute, second, and frame values, leaning on a period to stand in for a pair of zeros and speed things up. Whatever numbers you key in show up in the timecode field at the top right of whichever Viewer holds focus. Once you’ve finished typing, hit the Enter key to carry out the timecode command. These are the rules that govern timecode entry:

- Whatever pair of timecode values (or period) sits farthest to the right in your entry is always taken as the frame number.
- Place a period on either side of a number you type and it counts as a pair of zeroes.
- One period sitting between two numbers reads as a single zero, or gets disregarded when it falls

between two pairs of numbers.

- Any pairs of values to the left that you leave untyped are presumed to keep whatever they held

before the timecode you just entered; that lets you type partial timecode values with ease, even on a Timeline that begins at hour one.

- There’s no requirement to type colons or semicolons.

IMPORTANT: On a full-length keyboard, the number pad supports implicit timecode entry without your having to trigger the Go To Timecode action (=) first. During a multicam or printer light operation, any number pad key that’s already mapped keeps firing its assigned action, such as flipping between angles or stepping color values up. With the number keys that sit above the letters, though, you have to choose Go To Timecode (=) first, or click into the field you mean to change, before you key in a fresh value.

### Absolute Timecode Entry

Entering absolute timecode is just a matter of typing a timecode value. Provided nothing in the way of clips or edit points is selected at the instant you press the Return key, the playhead jumps to that timecode value. Should an edit point or clip be selected, it gets moved or trimmed to the matching timecode value where that’s feasible. Below are a few examples of absolute timecode entry done this way:

Original TC Value 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10 01:10:10:10

User-Typed Value 15245218 2.. 15 12 1.2 1115.. 23...

New TC Value 15:24:52:18 01:02:00:00 01:10:10:15 01:10:10:12 01:10:01:02 11:15:00:00 23:00:00:00

### Relative Timecode Entry

To enter relative timecode, lead the timecode value with either a plus (+) or a minus (–). A plus causes whatever value you type to be tacked onto the current timecode value, so as to offset the playhead or shift a selection. A minus instead deducts the value you type from the current timecode value. Two examples of relative timecode entry follow:

### User-Typed Value +20. +3.. -5

Result 00:00:20:00 gets tacked onto the current timecode value. 00:03:00:00 gets tacked onto the current timecode value. 00:00:00:05 gets taken away from the current timecode value.

### Copy and Paste Timecode in Viewer Timecode Fields

Across the Media, Edit, and Color pages, right-clicking most Viewer timecode fields brings up a contextual menu with Copy and Paste commands for moving timecode values around. Alternatively, click into the timecode fields and lean on the usual Copy (Command-C) and Paste (Command-V) keyboard commands. It even carries over from one page to another. Whatever timecode value you paste has to be valid timecode; you can’t, say, drop 0 hour timecode onto a 1 hour timeline.

Right-clicking on a timecode field to use the Copy Timecode command

### Gang Viewers (Playhead Ganging)

By default, playhead motion runs separately in the Source and Timeline Viewers. Click the Option menu at the top right of either Viewer and switch Gang Viewers on, though, and the two playheads become locked so that they travel together in lockstep. That comes in handy while, within the Source Viewer, you set a clip’s In and Out points so they line up with the length of a clip or some other event in the Timeline. Even with the Source and Timeline Viewers ganged, you can still pass focus between the Source and Timeline Viewers, and your video output device will reliably output whichever Viewer currently holds focus.

### Adding Markers

Markers, flags, and clip labels get fuller treatment in other parts of the editing section, yet markers matter enough that a quick rundown of adding and editing them belongs right here. You use markers to flag a specific frame inside a particular clip. Each marker can carry its own color along with custom name and note text. The moment you type any text into a marker, that marker shows a tiny dot signaling that there’s more detail held inside. After they’re placed, markers snap, when snapping is on, to In and Out points, edit points, the playhead, and to other markers, which makes them handy for “measuring” the edits and trims you perform on the Timeline.

### Adding Markers to Clips

Markers can be dropped onto the jog bar of source clips within the Source Viewer (or within the Media Page Viewer), as well as onto clips you’ve selected inside a timeline.

### Markers placed on a source clip

### Markers placed on a clip in the Timeline

To set a marker on a source clip within the Source Viewer or Media Page Viewer, take one of these approaches:

- To drop a marker and nothing more, bring the playhead to the frame you’d like marked, then press M.
- To drop a marker and have its dialog open right away so you can add a name or note mid-playback, press Command-M. Playback holds until you’ve typed the text you want and shut the marker dialog again, whereupon playback resumes.
- Bring the playhead to the frame you’d like marked, then right-click within the jog bar and pick a marker color out of the Add Marker submenu in the contextual menu.

After you’ve dropped a few markers, you might wish to tweak what’s inside them to make them more useful. To bring up a marker’s edit dialog and change its properties: 1 Do one of the following:

- Press Command-M to drop a marker mid-playback and have its edit dialog open at once.
- Double-click whichever marker you’d like to edit.
- Using Shift-Up Arrow/Down Arrow, bring the playhead to the frame that holds the marker you want

to annotate, then press M.

- Pick any marker in the Source Viewer or Timeline, and press Shift-M.

2 Once the marker dialog is open, several properties become editable.

### The properties found in the marker dialog

For a great deal more on markers, turn to Chapter 41, “Marking and Finding Clips in the Timeline.”

### Setting In and Out Points

With your clips reviewed via the playback commands, you’re ready to drop In and Out points that define the portion of each clip you mean to edit into the Timeline. Leave In or Out points unset and the whole clip lands in the Timeline. Set them, and those points get stored in the Media Pool, ready for the next time you edit that clip.

### Setting Clip In and Out Points in the Media Pool

You’re able to drop In and Out points straight inside the Media Pool to get ready for editing. While skimming a thumbnail in Metadata view, here’s how to mark In and Out points: Put the Media Pool into Metadata view, hover the pointer over the Thumbnail, and pause a beat until dragging the pointer starts skimming that clip. As it skims, tap I and O so the In and Out points bracket whatever stretch of that clip you mean to use. Skimming instead inside Thumbnail view, the steps run thus: Switch the Media Pool over to Thumbnail view, rest the pointer on a clip, and wait a moment until a drag of the pointer kicks off skimming through it. With it skimming, tap I and O so the In and Out points bracket whatever stretch you plan to keep. When that’s done, a range indicator along the foot of the clip’s thumbnail reveals how much you’ve picked out. The List view Filmstrip offers a third route for marking In and Out points: Switch the Media Pool over to List view, choose a clip so it surfaces in the Filmstrip running atop the Media Pool, sweep the pointer through the Filmstrip to watch it roll, and tap I and O so the In and Out points span the range you’re after.

Marking In and Out points via the List view Filmstrip of the Media Pool The Filmstrip greys out the heads and tails, letting you take in the span of media you’ve marked. Once In and Out points sit in the Filmstrip, a leftward or rightward drag moves them around.

### Setting Clip In and Out Points in the Source Viewer

For a closer look at your footage, you can lay down In and Out points in the Source Viewer ahead of editing.

Here’s the routine for marking In and Out points within the Source Viewer: 1 With Live Media Preview enabled via the Source Viewer’s option menu, either skim a thumbnail from the Media Pool, or else load a clip in. 2 Reach for JKL, the Spacebar, the transport controls, or a jog-bar drag to bring the playhead to wherever an In or Out point belongs. 3 Take one of these paths: For plain In and Out points, click the In and Out buttons just right of the transport controls, or hit the I or O keys. For split In and Out points, ahead of a split edit, right-click the Jog Bar; out of the Mark Split submenu, the video side gives you Mark Video In (Shift-Option-I) and Mark Video Out (Shift-Option-O), while the audio side gives you Mark Audio In (Command-Option-I) and Mark Audio Out (Command-Option-O).

Placing In and Out points within the Source Viewer, shown both as simple (Left) and as split edits (Right) With plain In and Out points, the picture and sound of two clips meet at a single shared edit point on the Timeline. Lay down split In or Out points, on the other hand, and you’re set up to craft split edits in which the video runs offset from the audio in one move.

### Clearing and Navigating In and Out Points

After they’re set, you can also wipe away In and Out points you no longer want, and send the playhead to In and Out points you may want to edit. To clear In and Out points:

- To clear In or Out points: With the pointer resting on a marked thumbnail in the Media Pool, or on the Media Pool film strip, or with a clip open in the Source Viewer, press Option-I to wipe the In point you’ve set, or Option-O for the Out point.
- To clear Split In or Split Out points: A press of Shift-Option-X wipes the Video In and Video Out points; Command-Option-X wipes the Audio In and Audio Out points.
- To clear both the In and Out points together: Rest the pointer on a marked thumbnail in the Media Pool, or on the Media Pool film strip, or activate the Source Viewer, then press Option-X.

To send the playhead, within either the Source or Timeline Viewer, onto the current In or Out points:

- Press Shift-I to carry the playhead to the current In point (Playback > Go To > In).
- Press Shift-O to carry the playhead to the current Out point (Playback > Go To > Out).

The Go to In and Go to Out commands can drop the playhead onto the implied (yet unmarked) In and Out points that a three point edit you’re building defines, even while Preview Marks stay switched off. Say you drop In and Out points on the Timeline, and afterward, within the Source Viewer, set a clip’s In point; a press of Shift-O (Go to Out) will, all by itself, bring the Source Viewer playhead onto the frame destined to be that clip’s Out point were you to run the edit.

A three point edit takes shape from In and Out points placed on the Timeline together with an In point placed in the Source Viewer,

Go to Out, used here to bring the Source Viewer playhead onto the implied Out point that a three point edit defines

### Clip Edit Points Are Saved

After you set them, In and Out points stay put inside each source clip or timeline until fresh ones replace them. Should you quit DaVinci Resolve and later open that same project again, every clip’s In and Out points are preserved for later use.

### Turning In and Out Points into Markers With Duration and Back Again

Should you want to log the key stretches of clips with In and Out points, only one stretch can be logged at any moment, since In and Out points serve to flag the next portion of a clip headed into a three point edit. That said, a pair of commands in the contextual menu of the Source Viewer jog bar team up to let you swap In and Out points for Markers with Duration, and back the other way:

- Convert In and Out to Duration Marker: Converts a pair of In and Out points into a duration marker. Out of the box, no key shortcut is tied to this command, although you’re free to assign one.
- Convert Duration Marker to In and Out: Converts a duration marker into a pair of In and Out points, all while keeping the marker. Out of the box, no key shortcut is tied to this command, although you’re free to assign one.

With these two commands, markers with duration become an easy way to flag regions of clips you’d like to log for later, each region turning into an In and Out point whenever editing calls for it. These commands ship with no keyboard shortcuts attached, but you can attach your own if you reach for them often.

To turn In and Out points into a duration marker: 1 On the Source Viewer jog bar, drop In and Out points that bound a region you wish to log for later reference. Placing the bounds of that clip section ahead of logging it 2 Do one of the following:

- Right-click the jog bar, then pick Convert In and Out to Duration Marker.
- Go to Mark > Convert In and Out Into Duration Marker. A duration marker now appears just above where the In and Out points sit. To revise its name or notes, double-click the marker, hit Shift-M, or head to Mark > Modify Marker.

A duration marker is created from the In and Out points That’s the way to log several separate regions within a lone clip for later use.

One clip carrying several logged sections, each flagged by a duration marker To turn a duration marker into an In and Out point: 1 Track down whichever duration marker you’d like turned into In and Out points..

Locating the duration marker that’s to become In and Out points 2 Do one of the following,

- Right-click the jog bar, then pick Set In and Out from Duration Marker.
- Bring the playhead onto the duration marker, then go to Mark > Set In and Out from Duration Marker.

In and Out points show up beneath the duration marker.

In and Out points are created from the duration marker This is how a duration marker you’ve logged becomes In and Out points, readying you to run a three-point edit. Three things make these logging techniques especially valuable. To begin with, markers with duration are searchable in the Media Pool through the All Fields, Marker Name, and Marker Notes Filter by options. On top of that, Smart Bins can filter on them via the Marker Name and Marker Notes Media Pool Properties options. Finally, once a clip carries one or more duration markers, they offer a fast route to three-point edits into the timeline.

### Organizing Media by Creating Subclips

Subclips hand you yet another approach to organizing media in the Media Pool, letting you carve overly long clips down into shorter pieces. Suppose a project’s director leans on “rolling takes,” recording several takes inside one clip; you can pull those takes apart by turning each into its own subclip. Building a subclip on the Edit page goes like this: 1 Ahead of making any subclips, load a clip into the Source Viewer from either the Media page or the Edit page, by one of these means.

- Double-click any clip in the Media Pool.
- With a single click on any clip in the Media page’s Media Library, build a subclip without first having

to bring that clip into the Media Pool. 2 Lay down In and Out points in the Source Viewer to mark out the section you mean to turn into a subclip. 3 Do one of the following:

- Choose Mark > Create Subclip.
- Press Option-B.
- Right-click the jog bar, then pick Create Subclip out of the contextual menu.
- Drag a clip out of the Source Viewer and into the Media Pool.

4 A new subclip dialog opens, where you can name the subclip and, by ticking the checkbox, opt to use its full extents.

### The New SubClip dialog

Subclips, once made, show up and behave just like every other clip in DaVinci Resolve. You can build subclips on the Media page as well, while you’re busy with other organizational chores there.

### Removing or Changing Subclip Limits

After it’s made, right-clicking any subclip in the Media Pool or a timeline and choosing Edit Subclip brings up a dialog where you can tick a checkbox to use the subclip’s full extents, or revise the subclip’s start or end timecode through the timecode fields, then click Update to apply your changes to the subclip.

### The Edit Subclip dialog

### Create a Timeline Subclip from In / Out Range

You can also build a subclip spanning several clips out of the active timeline on the Edit page. That lets you grab just one section of a timeline and set it apart in a brand-new timeline of its own for more work, leaving the original untouched. To create a Timeline Subclip in the Edit page: 1 Lay down the In and Out points marking where the subclip should start and stop on the timeline. 2 Right-click the selected range along the bottom of the Timeline viewer or on the Timeline ruler bar, and choose Create Subclip from the context menu. You could instead press Option-B.

Doing so spawns a fresh timeline holding only the range you grabbed from the original timeline. In the Media Pool it’s labeled “<timeline name> Subclip” so it stands apart from the original.

Right-clicking the ruler bar within the timeline likewise offers Create SubClip among the list of options.
