# Motion Tracking Windows (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Dealing With Occlusions When Tracking

Now and then, a stretch of usable tracking data simply isn't there and you have to compensate. A typical cause: something in the shot moves in front of whatever you're following, breaking the continuity of a clip's tracking record. When the thing you're tracking disappears entirely behind some other object in the picture, a straightforward interpolation trick fills in the missing stretch of data. Take the example below, where the woman strolls behind yet another fence post, except this one rises higher than her head. At that moment the window following her face loses its target outright, yet interpolation lets you rescue the take.

### Original clip

Bridging across an occlusion by joining two separate spans of track data: 1 Position the playhead on the earliest trackable frame of the moving feature you're fixing, then draw a Power Window enclosing it.

Adding the Power Window 2 Use Track Forward to advance along the feature as long as you're able, right up until something else in the shot hides it. 3 As soon as the Power Window can no longer hold onto the feature dependably, halt the track.

With the post now blocking the Power Window 4 Open the Tracker palette. 5 Click the Frame button to switch the Tracker into a mode that adjusts one frame at a time. Don't skip this step.

Selecting Frame mode 6 Bring the playhead to whatever frame shows the tracked feature emerging again from behind the obstruction, then reposition the window until it sits over the feature once more.

Moving the playhead and position the window 7 Use Track Forward to keep following the feature through to the clip's final frame. As an alternative, you might have begun at the tail of the clip and applied Track Reverse to follow the feature back as far as it would go, whichever proves simpler. Having now pinpointed where this clip loses dependable tracking, you can move on to configuring the interpolation.

Observe the missing stretch of track data left where the window sat behind the post

8 Drag a bounding box around the segment of the Tracker graph curves lying between the solid tracking at the start and at the finish of the shot.

9 From the option pop-up menu of the Tracker palette, pick Clear Selected Track Data.

Whatever portions of the curves you highlighted get removed, and linear interpolation steps in automatically across that span, leaving no break in either the track data or the window's travel, which glides cleanly from the final reliable frame on one side to the first reliable frame on the other.

### Point Tracker Workflows

For all the sophistication of the Cloud Tracking enabled by default in DaVinci Resolve, certain situations are handled more readily with plain old-school crosshairs. The Point Tracker is built to lock onto very particular details of whatever subject is moving in the way you care about. Where the Cloud Tracker hunts on its own for every trackable point inside a region you outline with a window, the Point Tracker has you drop one or more crosshairs and hand-place them over the high-contrast details you intend to follow. Below are the three principal workflows that cover working with the Point Tracker.

### Tracking a Window Using the Point Tracker

What follows sketches, at a broad level, the way you'd employ the Point Tracker to follow a subject in motion and pass that movement to a Power Window. 1 Set the playhead on whichever frame of the present shot you'd like as your starting point (there's no rule that you begin at a shot's opening frame, given that tracking backward is always an option). 2 Switch on a window of any kind and shape it around the feature you mean to track. As a rule you'd already have set this up, say, surrounding someone's moving face with a Circular window to brighten

their highlights. Confirm that the window meant to receive the tracked motion is the one selected before tracking starts. Here, we'll track a Circular window so it trails the woman’s face.

Preparing to follow a window placed across a woman's face 3 Bring up the Tracker palette, then pick Point Tracker via the lower-right pop-up.

Choosing the Point Tracker 4 Ahead of tracking, decide which kinds of motion you'd like analyzed and passed to the window in front of you. The available choices are Pan, Tilt, Zoom, Rotate or Perspective 3D. How many of these transformations you can actually apply hinges on the number of points you set up to track. Picking which sort of motion gets analyzed 5 Click the Add Tracker Point icon. A fresh tracker crosshairs shows up in the Viewer, centered on the frame.

Clicking the Add Tracker Point icon

6 Bring the pointer right onto the tracker crosshairs, and once it becomes the move cursor, drag it so the crosshairs sit squarely over the feature you intend to track. You'll get the cleanest result by choosing a high-contrast detail, such as a corner, a line's endpoint, a tiny shape like a pebble, or some ragged detail. In contrast to other point trackers, here there's no separate inside or outside zone to tune, just the single crosshairs you have to position. In this case, that first crosshairs lands at the inner edge of her stage left eyebrow (parking it at the corner of her eye would add too much jitter, since the tracker would catch her blinks).

Aligning the tracker crosshairs onto the detail you intend to follow 7 To sharpen the precision of the track, you can add further tracker crosshairs and drop them over additional details on the subject you're following. The cleanest results come from putting every crosshairs on details sharing one plane of motion. Put differently, avoid placing some crosshairs on a foreground face and others on a distant background tree, because those two features travel along wildly different motion vectors. Here, the trackers go on her inner eyebrows and at the corner of her lips.

Placing four trackers onto the corners of her eyebrows and mouth

The completed track, done with four point trackers and the track path displayed 8 Once your crosshairs are all set, click either Track Forward or Track Backward to begin tracking. The clip gets analyzed, the Tracker graph fills in with the tracking data, and the window you'd selected shifts on its own to match how the tracked feature moves.

### Removing Trackers

Should a given tracker turn out to cause trouble, you can get rid of it by selecting it inside the Viewer and clicking the Delete Tracker icon, then retracking the subject afterward.

### Clicking the Delete Tracker icon

### Using Frame Mode to Offset Track

One recurring headache with point tracking is handling occlusions, along with moments when the tracked feature drifts out of the frame. The remedy in DaVinci Resolve is the Frame mode of the Tracker palette, which lets you shift the tracker crosshairs over to a different feature while keeping the resulting motion offset so it stays on the original motion path. 1 Here, a point tracker crosshairs sits at the corner of a building's window that's being adjusted on its own with a Power Window. The window serves the purpose because, once the woman turns to depart, she blocks most of the building's other trackable outer edges, which would otherwise wreck the track.

Setting up to track a building moving off screen

2 With the camera panning, the tracked feature is on the verge of leaving the frame, which threatens to wreck the track. The moment this occurs, click the Stop Track button.

Halting the track at its final solid frame, just before the tracker leaves the screen 3 Return the playhead to the last solid frame of tracking, then click the Frame button in the Tracker palette to enter Frame mode.

Turning on Frame mode, to prepare to offset the track 4 While in Frame mode, you can drag the tracker over to a different part of the building, this time the roof's outer edge, which makes a better target as the building exits frame to the left, given that the Power Window leaves frame ahead of the building roof's far right corner.

Moving the tracker onto a different, more suitable feature 5 Now press the Track Forward button once more, and the crosshairs start following the new feature, except the motion is offset, so the Power Window keeps traveling along the original motion path.

By tracking an offset feature, you let the window travel entirely past the screen edge

Across the relocation of the tracker crosshairs in Frame mode, the tracker path stays smooth and unbroken 6 If you switch on the track path (via the Tracker Option menu) and park the playhead on the frame where the tracker was relocated, you'll notice the motion preceding the move and the motion after it flow on along one continuous path, free of abrupt jumps. Once you're done, click the Clip button to leave Frame mode.

### Rotoscoping Window Shapes After Tracking

As remarkable as the DaVinci Resolve trackers are at keeping a window glued to moving subjects or to elements inside a shot in motion, there will be no shortage of occasions where the finished track falls a little short. Say you're trying to isolate a person's face with a highly specific window, and that person rotates their head; the shape change that follows will almost surely demand animated tweaks to the window if you want to hold such a precise isolation.

Comparing before and after as a window tracks a turning head: the window falls slightly short of hugging the edge of the woman's face while her head rotates

Happily, the Frame mode of the Tracker palette makes it straightforward to animate the shape edits you apply to windows so they hug a moving subject more closely, work often called rotoscoping. By tracing a moving subject and laying down a run of automatically keyframed window tweaks wherever the subject shifts speed or direction, you can keep a window isolating a moving target with striking accuracy.

Employing Frame mode to rotoscope the window so it more closely hugs her facial edges and the line of her jaw On top of that, Frame mode can also fix sloppy tracks where the window strays off course thanks to fast or erratically moving features. For those cases, you have the choice of tracking the window by hand in Frame mode to match the feature's path, one frame after another. And finally, you needn't even have run a track at all to use the Tracker graph in Frame mode for keyframing animated window changes. As it happens, working the Tracker graph in Frame mode can at times beat using the Keyframe Editor in Auto Keyframe mode, depending on the task at hand.

### Rotoscoping Controls

Whether you're rotoscoping a shape comes down to the Clip/Frame buttons. In Clip mode: Whatever edits you apply to a window reshape it across the full length of that clip. To put it another way, you can track a window onto a moving feature, and in Clip mode any change to the window's size, rotation, position, or shape happens uniformly from that clip's start to its end. In Frame mode: An edit to a window automatically lays down a keyframe at the foot of the ruler in the Tracker graph. Two or more window edits in Frame mode yield automatically interpolated animation running from one keyframed window transformation to the next. You're free to switch back and forth between Clip and Frame modes as you edit a window. Even after keyframing a window's shape changes, you can flip on Clip mode and apply a blanket change to the window, enlarging it say, which enlarges the window equally at every keyframe.

### Keyframing in Frame Mode

After you've laid keyframes into the Tracker palette, several options exist for editing them. Ways to work with keyframes in the Tracker graph:

- To add a keyframe: In the top right corner of the Tracker graph, click the Add Keyframe icon. It looks much like the Keyframe icons sitting in the Edit page Inspector. It's handy when you want a keyframe on a frame where the window matches the subject nicely, ahead of advancing a few frames and reshaping the window onto the subject, which produces another keyframe.
- To move the playhead from one keyframe to another: In the top right corner of the Tracker graph, click the Previous Keyframe and Next Keyframe icons. They look much like the controls over in the Edit page Inspector.
- To delete a keyframe: With the playhead parked on the exact frame that holds the keyframe you want gone, open the Tracker option menu, and choose Delete Keyframe.

The graph's Previous Keyframe, New Keyframe, and Next Keyframe buttons sit in the Tracker graph

### A Rotoscoping Workflow

The walkthrough below shows how a window can rotoscope an onscreen feature you want isolated. As it goes, it explains preparing a window for rotoscoping by means of the Tracker palette, plus a handful of practices that keep your rotoscoping work quick. To rotoscope, or hand-track, a window with automatic keyframing: 1 Build a window around the feature you mean to adjust, and let the tracker carry it along with the subject's motion. Where the window fails to trace the subject's contours as tightly as you need, you can begin keyframing its shape manually atop whatever tracking you've already performed to rotoscope your subject. 2 With the Tracker palette open, click Frame to switch the tracking mode.

Clicking the Frame button to start keyframing the shape The best Frame mode tracking technique is to either start on the last frame you tracked successfully and proceed forward, or start on the first frame you tracked successfully and proceed backward. That approach extracts the maximum from the automatic keyframing and the between-keyframe interpolation, animating the window you're reshaping cleanly. 3 With the playhead resting on whichever frame (first or last) shows the window fitting your isolated subject, you may click the Add Keyframe button in the upper right corner of the Tracker graph, or jog any control point a pixel or two, in order to set a keyframe there.

Clicking the Add Keyframe icon in the Tracker graph Placing a keyframe at the final frame where the window tracks the subject's motion well ensures any later animated changes interpolate forward from that frame, instead of from earlier frames that need no edits.

Adjusting the window in Frame mode adds a keyframe Throughout Frame mode, the edits you make to the window automatically spawn a keyframe in the Tracker palette, showing up at the foot of the Tracker graph's timeline.

### Keyframes appear in the Tracker graph ruler

It's often crucial to drop a keyframe on the final frame where a window matches the subject you're isolating well, so as to confine window animation between that frame and the next keyframed transformation, rather than letting it animate by accident from the clip's opening, or from an adjacent keyframe in the Tracker graph. 4 Then, advance the playhead to the next frame where the window needs adjusting to better suit the moving subject, and tune the window's position, its control points, or both, isolating the subject however necessary.

Readjusting the window in Frame mode to follow the subject’s motion

The result is a second keyframe placed into the Tracker graph ruler. A pair of keyframes producing rotoscoped animation atop whatever motion tracking is in effect 5 Once your opening pair of keyframes is down, drag the playhead to and fro between them to judge how well the window's animation interpolates automatically to track the subject you're isolating. If the window isn't following your subject's motion closely enough, take the playhead to the frame where the window strays the worst and make a further tweak to fix the shape. That spawns yet another keyframe.

One of the frames sitting between your two rotoscoped keyframes that calls for more adjustment

After adjusting the in-between frame

6 Having finished tweaking between your opening two keyframes, push the playhead onward and lay down keyframes as needed so the window tracks your subject's motion. As a rule, hunt for the frames where your subject's motion begins, ends, accelerates, decelerates, or shifts direction. While you work, aim to use the smallest number of keyframes that still yields smooth motion between them. Cramming too many keyframed tweaks too tightly together for a smoothly moving subject risks introducing jerky motion if you're not watchful. Conversely, with an erratically moving subject you might be forced to add more keyframes, perhaps frame by frame, to land the look you're after.

TIP: When you're isolating a subject whose shape is intricate and that moves a great deal, think about using several simple overlapping shapes to track and rotoscope it rather than one complicated shape, which makes the job easier. 7 After you've wrapped up rotoscoping the window, make a point of clicking the Clip button to return to Clip mode, so that you can trim the window's shape across every keyframe you just laid down, if needed. This also keeps you from inadvertently piling on more keyframes if you go select other shapes.

This approach takes a touch more effort than relying on the Tracker alone, but it lets you swiftly fine-tune a window's animation so it clings more snugly to a moving subject whenever you need a tweak aimed at that subject by itself. The same approach also works for nudging particular motion path points partway through an otherwise good track to seat them better, or for adding keyframes at the head or tail of a track where the subject leaves frame but the window stays put.

### Viewing a Window’s Motion Path

To display the motion path for whichever window you're tracking, choose Show Track from the Tracker Option menu.
