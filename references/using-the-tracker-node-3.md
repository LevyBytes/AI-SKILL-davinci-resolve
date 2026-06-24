# Using The Tracker Node (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Once you select the Tracker node, a lone green box turns up in the viewer; that box is the default onscreen control belonging to the first default tracker the node holds (you can spot it within the Tracker List of the Inspector controls). Remember that onscreen controls only show for nodes you’ve selected, so whenever those onscreen tracker controls are nowhere to be seen, that tells you the tracker you mean to work on still needs selecting. Pulling the tracker you intend to work on into the viewer is likewise the surest route to confirming you’re placing the controls correctly against the actual picture you’re tracking. Hover your pointer over this box and the whole onscreen control for that tracker shows up, and clicking that onscreen control to select the tracker turns it red. Like so many of the other tracker interfaces you’ve probably run into, it’s made up of two boxes carrying assorted handles for shifting and resizing them:

- The inner box is the “pattern box,” which pins down the “pattern” within the picture you mean to track and want to chase the motion of. A tiny handle sits at the pattern box’s upper-left corner, and you grab it to drag the box over whatever you intend to track. You can also resize that box by dragging any corner, or squash or stretch it by dragging any edge so the box fits the size of the pattern you’re after more closely. Where the tracker’s center sits is reported through X and Y coordinates.
- The outer box is the “search box,” which pins down how much of the picture the tracker has to study in order to chase the pattern’s motion. With a slow-moving picture, the default search box size is likely fine. Yet with a fast-moving picture, you might need to resize the search box (using the same sort of corner and side handles) so it scans a wider area, though that costs you a longer analysis. That tracker’s name shows down at the lower right of the search box.

The onscreen controls of a selected tracker seen in isolation

It bears repeating that the handle for shifting a tracker’s onscreen control is a tiny dot perched at the upper-left corner of the inner pattern box. Newcomers to Fusion find it really easy to overlook. You have to click that dot to drag the tracker about.

The handle for dragging the tracker boxes to move them around For this example, we’ll drag the onscreen control until the pattern box sits over a stretch of the bridge directly above the leftmost support. While we drag the onscreen control, a zoomed-in view of the area we’re dragging across appears to help us seat the tracker with more accuracy. Here, the default sizes of the pattern and search box work just fine as they stand.

A magnified preview that aids in seating the pattern box while you drag it along Using the Tracker’s Inspector Controls to Perform the Analysis Now let’s turn to the Tracker node’s controls over in the Inspector. The controls are plentiful, but for this straightforward example we only care about the main Tracker panel, holding the tracking analysis buttons up top, the tracking options beneath those, and the Tracker List under them. The Tracker List also carries buttons for adding and removing trackers; you may add multiple trackers that can all be analyzed together for various workflows, though we have no need of that right now.

Tracker Inspector controls, where the tracking analysis buttons sit up top, the tracker options run through the middle, and below them rests the Tracker List Further controls covering each tracker and the image channels under analysis turn up at the bottom, alongside offset controls for each tracker, though we don’t need those just yet (at least not for now). Again, this track is straightforward enough that we hardly need to alter the default behaviors at all, but because the drone keeps flying along a circular path, the form of the pattern area keeps shifting while the clip plays. Luckily, we can pick Every Frame out of the Adaptive Mode menu to tell the tracker to refresh the pattern being matched at every frame of the analysis, which accounts for this.

Switching the Adaptive Mode on the Tracker node over to Every Frame so the camera’s changing vantage point gets handled Now all that’s left is to reach for the tracker analysis buttons up top to launch the analysis. These buttons behave much like transport controls, letting you start and halt analysis whenever you need to handle problem tracks in different ways. Bear in mind that the bookend buttons, namely Track from Last Frame plus Track from First Frame, always kick off a track at whichever end the composition has, its last or first frame, regardless of where the playhead happens to rest, so make certain your tracker onscreen controls are seated properly on that last or first frame. Reading from left to right, the analysis buttons run: Track from Last Frame, then Track Backward, then the central Stop Tracking, followed by Track Forward, and finally Track from First Frame

For now, hitting the Track from Beginning button will study this clip across its whole range, running from the first frame through to the last. A dialog tells you once the analysis finishes, and hitting the OK button clears it away so you can take in the nice clean motion path that comes of it.

The motion path produced by analyzing a stretch of the bridge while the camera sweeps by Viewing Motion Track Data in the Spline Editor This isn’t a required part of the tracking workflow, but should you have an otherwise nice track carrying a few bumps, you can review the motion tracking data within the Spline Editor by viewing that tracker’s Displacement parameter curve. That curve can be edited, so you’re free to massage your tracking data in all sorts of ways if you need to.

Viewing motion tracking analysis data in the Spline Editor

### Connecting Motion Track Data to Match Move

Now that a successful analysis is in hand, the time has come to put it to work building the Match Move effect. To smooth this along, we’ll double-click the tracker’s name within the Tracker List of the Inspector, and enter a fresh name that’s simpler to keep track of (heh). Giving your trackers your own names makes a given tracker easier to track down across later contextual menus and lets you stay clear on which trackers are following which subjects as your compositions grow ever more involved.

Renaming a tracker to make it easier to find

Now the moment has come to wire the track we just built to the text so it starts moving. After loading the Merge1 node into the viewer so we can see the text against the overall composite we’re building, we’ll select the Text1 node so its parameters open up within the Inspector, then click the Layout panel icon (the second button from the left) to reveal the Layout controls, which are the text-specific transform controls used for placing the text object within the frame. These are the very controls you work when the Text node onscreen controls are used to reposition or rotate text.

Shown here within the Layout panel are a Text node’s Layout controls The Center X and Y parameters, though each can be adjusted on its own, also act together as a single target for the purpose of hooking up to tracking to set up match moving animation fast. You arrange this through the contextual menu that pops up when you right-click any parameter inside the Inspector, which holds an assortment of commands for adding keyframing, modifiers, expressions, and other automated routes to animation, hooking up to motion tracking among them. By right-clicking anywhere along the line of controls for Center X and Y, we can pick Connect To > Tracker1 > Bridge Track: Offset position off the contextual menu, which ties this parameter to the tracking data we analyzed before.

Wiring the Center X and Y parameter onto the Bridge Track: Offset position motion path that we just analyzed Right away, the text shifts so its center position lines up with the center of the tracked motion path at that frame. That tells us the center of the text is being match moved onto the motion track path.

The text now aligns with the motion track coordinate

### Offsetting the Position of a Match Moved Image

In fact, we’d like to offset the match-moved text so it rides higher within the frame. To pull this off, we pick the Tracker1 node once more and use the Y Offset 1 dial control to nudge the text upward, since any change we make now to the Bridge Track dataset carries over to the center of the text that’s tied to it.

Leaning on the X and Y Offset controls within the Tracker1 node to shift where the text layer sits relative to the tracked motion path The offset we build shows up as a dotted red line that lets us see the real offset the X and Y Offset controls are producing. This, in fact, is exactly why we hooked into the Bridge Track: Offset position option earlier.

The text shifted away from the tracked motion path; that shift reads as a dotted red line within the viewer

Now, playing through this clip lets us watch the text move right alongside the bridge.

A pair of frames showing the text match moved so it tracks the bridge throughout the shot
