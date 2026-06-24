# Motion Tracking Windows (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Motion Tracking Windows

You can certainly keyframe a Power Window by hand to chase a moving subject you'd like to isolate, but this chapter explains how the cloud- and point-based motion tracking tools in DaVinci Resolve let Power Windows ride along with the movement of both subjects and the camera as quickly and easily as possible. A range of methods then follow for handling tricky tracking situations and the recurring difficulties that show up with subjects that resist tracking.

The Tracker palette has three modes, available from the Palette menu.

- Window mode gives you tracking controls that lock a window onto the motion of a moving feature in the shot.
- Stabilizer mode applies that same engine to calm or steady movement across the whole frame.
- FX mode provides a Point Tracker for driving the positioning controls of ResolveFX or OFX plugins.

To learn more about the FX and Stabilizer modes, refer to Chapter 152, “Sizing and Image Stabilization.” DaVinci Resolve ships with a remarkably straightforward yet potent 3D cloud tracker, letting you lock any Power Window (Circular, Linear, Polygonal, Curve, or Gradient) quickly and precisely onto any moving feature. That spares you from hand-animating a window's location with dynamic keyframes. Specifically, the tracker can match a window's position, size, rotation, plus its pitch and yaw in 3D space, to either foreground or background objects that travel through the frame.

### A Power Window tracking a woman’s face

### Simple Tracking Using the Tracker Menu

The quickest route to tracking a feature with a Power Window is through the commands in the Color > Tracker menu. Those commands are: Track Forward (Command-T): Tracks a window onto a feature starting at the playhead's current location and running ahead to the clip's final frame. Track Reverse (Option-T): Tracks a window onto a feature from where the playhead sits and moving backward, finishing at the clip's first frame. Track Stop (Command-Option-T): Halts any track. Handy for aborting a lengthy track that has gone bad (the Stop button on a control panel halts tracking too). One Frame Forward (Option-Right Arrow): Advances a window's track onto a feature by a single frame past the current spot. One Frame Reverse (Option-Left Arrow): Moves a window's track onto a feature one frame back from where you are. The majority of window tracks can be handled with these three commands. To make any Power Window follow a moving feature inside the frame: 1 Position the playhead on the frame of the current shot where you'd like to start (you needn't begin tracking on a shot's first frame). 2 Switch on any window and shape it to enclose the feature you intend to track. You've usually done this already anyway—for instance, ringing someone's moving face with a Circular window to brighten their highlights. 3 To initiate tracking, do one of the following:

- Choose Color > Tracker > Track Forward (press Command-T).
- Choose Color > Tracker > Track Reverse (Option-T).

DaVinci Resolve then opens the Viewer page on its own, drops a cluster of tracking points inside the window you drew, and runs the track from the current frame—ahead to the last frame or back to the first. DaVinci Resolve studies a cloud of tracking points that ride the vectors of each trackable cluster of pixels inside your window, producing quick and accurate results. Once the track completes, the window you positioned automatically shifts, scales, spins, and shears to keep pace with the feature being tracked. As soon as a clip carries tracking data on one of its windows, a tiny tracking icon shows up inside that clip's icon on the Thumbnail timeline.

A tracking badge in the upper-left of the Thumbnail timeline marks a clip as tracked

Object tracking underway. The software drops tracking points automatically across the image's trackable features Should the track you ran prove unsatisfactory, you can move the window over a different region of the subject you want to track and start the track over. Fresh tracking data replaces whatever previous tracking data was on that window. After you're pleased with the track, you can keep resizing, repositioning, or reshaping the tracked window. Because tracking data lives separately from the window transform parameters (which support keyframing), any edits you make to a window shift it away from the path that was originally tracked.

### Tracking Windows Across Transitions

If you track a window that spans a transition boundary—say a dissolve between two clips—DaVinci Resolve carries the track onward across the entire stretch of video beneath the transition automatically.

### Tracking Windows When You’ll Be Exporting Media With Handles

Because windows tracked to follow moving features in a clip are only transformed on the frames that hold tracking data, Round Trip workflows—where you append handles to graded rendered clips so editorial keeps trimming room in the footage you hand off—require you to track every window across the full span of those handles. That way, if an editor actually trims any of the clips you delivered to make use of the handles, all the windows behave correctly. A simple approach is to choose View > Show Current Clips With Handles, which displays each clip you pick within the Timeline alongside handles whose size comes from the “Default handles length” control located in the Editing panel under the User Preferences. Verify that this “Default handles length” lines up with the handles you output via the “Add X Frame handles” choice found in the Render Settings list over on the Deliver page. Once each clip's handles show up this way, it becomes simple to track windows across every frame you'll render.

### Simple Ways of Working With Existing Tracking Data

When a stretch of a shot is left untracked—maybe you began tracking later, or stopped before the shot ended—the window you tracked simply stays put at the first or last frame that did get tracked. To close those gaps, move the playhead to the first or last tracked frame and run Track Backward or Track Forward to cover the rest of that shot's frames.

### Tips for Better Tracking

When a feature shifts shape in a way that throws off the tracker, try tracking a smaller portion of it with a smaller window. After you land a clean track, you're free to resize the window however you need, and it won't disturb the track you already created. Likewise, if you're tracking a feature that slips behind something onscreen and vanishes for the rest of the shot, there's an easy way to keep an awkward window from hanging in the middle of the scene. You can apply dynamic keyframes to animate the Key Output Gain parameter (found in the Key tab of the Color page), ramping it from a full-strength correction of 1.0 toward 0—the level where the correction disappears and carries the window off with it.

### Tracking One Frame at a Time

Within the Tracker palette, clicking either the “track one frame forward” button or its “track one frame backward” counterpart lets you advance a track over a moving feature a single frame at a time, which makes it simpler to tweak a tough track once you've set tracking to Frame mode (by clicking the Frame button). While in Frame mode, you can keyframe window transformations to hug awkward motion more faithfully as you step through the track one frame at a time; manual edits to a window's position become keyframes that build frame-specific transformations, instead of offsetting the entire tracked motion path the way Clip mode does. As you stack multiple keyframes in the Tracker graph, the animation interpolates from one keyframe to the next on its own.

### Copying and Pasting Tracking

Frequently you'll set several windows on a single moving subject—a car, perhaps—where one motion track can drive them all. Through commands in the Option menu, track data copies and pastes from one window onto another inside the same node, which saves time whenever you want a group of windows tracking in unison. Transferring track data between two windows goes like this: 1 Open the Window palette, then highlight a window already carrying tracking (marked by a tracking badge at its shape icon's corner); from the Option pop-up, choose Copy Track Data. 2 Highlight a different window; from the Option pop-up, choose Paste Track Data. Once one window's track data is on the clipboard, paste it onto as many further windows as suits you. By the same token, tracking can be pulled out of the Tracker palette's FX mode and dropped onto a window, for cases where one set of tracking data ought to power both an effect and a window. Moving track data off an FX track onto a window works this way: 1 Open the Tracker palette, highlight the FX mode that holds the tracking data you'd like to grab; from the Option pop-up, choose Copy Track Data. 2 Open the Window palette, highlight a window; from the Option pop‑up, choose Paste Track Data. Once one window's track data is on the clipboard, paste it onto as many further windows as suits you.

### Tracker Palette Controls in More Detail

Mixing object tracking with keyframing to animate windows is easy. As a rule, you'll lean on object tracking to make a window track the position and orientation of a moving feature, but you can layer dynamic marks onto the window track of the correction in the Color page to adjust its size and shape so it hugs a feature's shifting form.

### Controls in the Window Tracker Palette

Now and then you'll hit a shot that just won't track cleanly with the Tracker menu's simple commands. For those, the Viewer page exposes the full suite of object tracking controls you can use to tweak tracking operations across different scenarios.

### The Tracker palette

The object tracking controls are divided into seven groups.

### Tracker Palette Modes

The Option drop-down menu of the Tracker palette lets you pick among Window mode (to lock a window onto the motion of a feature in the frame), Stabilizer mode (to tame unwanted camera movement For details about Stabilizer mode, consult Chapter 152, “Sizing and Image Stabilization.”), and FX mode (to track position for use with Resolve FX or Open FX plugins).

### Types of Tracking

A pop-up menu sitting below the Tracker graph lets you decide between the Cloud Tracker and the Point Tracker.

### The tracker type pop-up

There are three options:

- The Cloud Tracker: Scans every region of the image for trackable points on its own and uses them to work out the motion in the shot you want for driving a Power Window or steadying a shot. This tracker type excels at quickly locking a window onto the movement of nearly any feature with very little effort.
- The Point Tracker: Lets you place one or more tracker crosshairs by hand to follow particular features in the shot. The greater the number of crosshairs you add and place, the more precise the track becomes. The Point Tracker shines whenever you need to follow the motion of one very specific feature in the frame. It also helps when you want to steady a shot crowded with subjects moving in different directions, where a good result is hard to reach with the Cloud Tracker.
- IntelliTrack: Is an AI tool that leans on no fixed rulesets or heuristics. Rather, real world examples are what train it. As a result it's less prone to break down in cases such as following a subject through short occlusions. In the majority of situations it proves more accurate and more dependable than the ordinary Point Tracker.

### Object Tracking

The object tracking controls supply the most fundamental tracking functions, a number of which are echoed inside the Color > Tracker menu.

Choose which type of transform you want to track before tracking A row of five checkboxes lets you toggle which transforms motion tracking will apply to the window automatically. You have to select these checkboxes before running a track so the transforms in play are restricted.

- Pan and Tilt: Turns on tracking of horizontal and vertical placement, for when a window should transform to chase a tracked subject's location.
- Zoom: Turns on tracking of size, for when a window should transform and rescale to keep up with a tracked subject.
- Rotate: Turns on tracking of orientation, for when a window should transform and spin alongside a tracked subject.
- Perspective 3D: Turns on tracking of pitch and yaw within 3D space, for when a window should skew to match a tracked subject's orientation inside the scene. Ideal for making a window “stick” to a surface.

NOTE: After tracking or stabilization has run, switching these checkboxes off won't change the result at all. To alter things, you have to enable or disable the checkboxes you need first, and then reanalyze the clip.

Having set the transforms you intend to track, the analyze controls then let you go ahead with analyzing the subject being tracked.

- Track One Frame Reverse button: Motion tracks one frame backward. Handy for the slow tracking of tricky subjects that need frequent correction.
- Track Reverse button: Starts tracking backward from the present frame, finishing at the clip's first frame. Useful for reverse tracking when your ideal launch point falls somewhere in the shot's middle.
- Pause button: Halts tracking (assuming you click this button quickly enough before the track wraps up).
- Track Forward button: Starts tracking ahead from the present frame, finishing at the last frame of

the clip.

- Track Forward and Back button: Starts tracking ahead from the present frame, then on

completion runs backward from the frame you originally selected. That gives you a single-button method for tracking out of the middle of a shot.

- Track One Frame Forward button: Motion tracks one frame ahead. Handy for the slow tracking of tricky subjects that need frequent correction.

### Clip/Frame Controls

A pair of buttons governs how hand-made tweaks to the placement of tracked windows influence the track as a whole.

### Selecting clip or frame to apply adjustments

- Clip: This is the default mode, where edits you make to a window's position apply across the whole track at once. As an example, track a feature and then drag the window, and the window travels along a motion path held at a steady offset from the original track for the whole clip. Reach for this mode when the track satisfies you but you'd like to tune the window's overall shape and placement relative to the path of motion it rides.
- Frame: Here, the edits you make to a window's position or shape lay down a keyframe at the frame where the playhead sits. Several keyframes interpolate into animation, letting you hand-transform a window to tackle assorted problems. The mode helps with rotoscoping window shape and placement to match a subject that defies automatic tracking. Frame mode also serves for repairing individual frames that tracked poorly, for animating windows that follow a subject completely out of frame, or for making manual, frame-by-frame window position tweaks to cover untrackable≈sections.

### The Tracker Graph

The Tracker graph gives you a visual readout of the tracking data under analysis. Every transform control that can be tracked owns its own curve, letting you assess each tracked parameter independently, and each curve carries a color that matches the corresponding label of the tracking transforms listed above. A vertical slider on the right of the Tracker graph scales the height of the curve data inside so it all fits more readably within the graph. A horizontal slider along the bottom of the graph zooms the tracker curves in and out, revealing finer detail in the tracking paths. Above the Tracker graph sits a Timeline ruler holding a playhead locked to the playheads in the Viewer and Keyframe Editor.

The Tracker graph showing a curve for each transform control Within the Tracker graph you can draw a bounding box to select part of one or more curves and remove sections of poor-quality tracking data using the Clear Selected Keyframes command in the Tracker Options menu. To clear the current bounding box from the Tracker graph, click once anywhere inside the graph.

### Interactive Mode Controls

Sitting at the bottom-left of the Tracker palette, the Interactive controls let you hand-edit the tracking point cloud that DaVinci Resolve builds automatically when you track with the Cloud Tracker, giving you room to experiment with various approaches toward better tracking in difficult shots.

### Interactive mode controls

- Interactive Mode checkbox: Switches the Interactive tracking mode on or off. Entering Interactive mode lets you hand-edit the point cloud that DaVinci Resolve relies on to track the feature inside the current window. You then run your track while Interactive mode is active.
- Insert: Adds tracking points onto whichever trackable features sit inside a bounding box you've drawn in the Viewer. The inserted tracking points land automatically according to the image's trackable pixels.
- Set Point: Lets you reach for the cursor (with the DaVinci Resolve Advanced control panel) to drop individual tracking points by hand, one at a time, to track a feature. Should no trackable pixel group sit at the cursor's coordinates, the tracking point snaps to the closest trackable pixel group. Tracking rotation requires at least two tracking points on separate pixel groups, and tracking zoom requires at least three.
- Delete: Wipes out every tracking point inside a bounding box you've drawn in the Viewer.

### Point Tracker Controls

When the Point Tracker is active, the Interactive Mode controls go away, swapped out for the Point Tracker's two controls.

### Point Tracker controls

- Add Tracker: Click to spawn a fresh tracker that lands automatically at the frame's center. After it exists, drag it with the pointer to align with whatever feature you intend to track. Create however many trackers you wish; they all track together at once.
- Delete Tracker: Pick any tracker (red marks a selected tracker, blue a deselected one), and click this button to get rid of it.

### Additional Commands in the Tracker Options Menu

A few extra commands live in the Tracker Options pop-up menu.

- Reset Track Data on Active Window: Removes the tracking data tied to whichever window is currently selected.
- Clear Selected Track Data: Once you drag a bounding box across portions of one or more curves in the Tracker graph, this command strips out that stretch of the graph. Handy for clearing away passages of poor-quality track data. Any curve passages erased this way receive linear interpolation on their own, just as though you'd reached for the Keyframes Interpolation controls.
- Delete Keyframe: Removes tracker graph keyframes sitting at the playhead's current spot.
- Clear All Tracking Points: Wipes the tracking points out of the Power Window on whatever frame you're parked on.
- Show Track: Switch this checkbox on to reveal the motion path the tracking

generated.

- Copy Track Data: Copies track data off whichever window is currently selected. You can pick windows

right in the Viewer while the Tracker palette stays open.

- Paste Track Data: Drops copied track data onto whichever window is currently selected. You can pick windows

right in the Viewer while the Tracker palette stays open.

### IntelliTrack AI Point Tracker (Studio Version Only)

Powered by the DaVinci Neural Engine, the IntelliTrack point tracker now appears in the Color tracker, the Fusion point tracker, and the FX tracker within DaVinci Resolve Studio. You can put the IntelliTrack setting to work on general tracking and stabilization jobs. Like other AI tools, IntelliTrack relies on no fixed rulesets or heuristics; rather, it learns from real world examples. That makes it less prone to fail in cases such as tracking a subject through brief occlusions. In most situations it'll prove more accurate and more dependable than the standard Point Tracker.

Using IntelliTrack: Every bit of the IntelliTrack analysis runs behind the scenes, and nothing more is asked of you beyond picking the IntelliTrack setting, placing the tracking crosshairs over high contrast regions on the same moving subject, and then pressing one of the tracker direction controls.

Setting the IntelliTrack mode for the Color page window tracker

### Cloud Tracker Workflows

The handful of examples coming up demonstrate how to apply the Tracker palette's controls in real-world cases. Quite often, objects crossing in front of a tracked subject—called “occlusions”—create trouble. Even though the DaVinci Resolve tracker resists occlusions very well, the sections below lay out an assortment of techniques to use when an occlusion keeps you from landing a usable track.

### Using Interactive Mode to Manually Choose Tracking Features

Interactive mode lets you hand-remove or hand-add tracking points to sharpen tracking performance wherever the automatic image analysis in DaVinci Resolve returns disappointing results. For instance, you can drop tracking points inside a window that correspond to overlapping features you'd rather not track. Picture a car you're tracking driving past a sign that partly hides it. Left alone, the PowerCurve isolating the car would distort badly as the car nears the sign and then pulls away from it. With Interactive mode, you can delete the tracking points destined to overlap the sign you don't want to track, sharpening the result.

Getting rid of particular, unwanted tracking points within a track: 1 Open the Tracker palette. 2 Switch on the Interactive Mode checkbox. Enabling Interactive Mode 3 Within the Viewer, drag a box over the tracking points inside the window that you'd like removed.

Boxing in the tracking points slated for deletion 4 Click the Delete button.

### Deleting tracking points

The points within the selection area are deleted.

Remaining tracking points ready to be used

5 With Interactive mode still active, click Track Forward or Track Reverse to track the subject from the remaining tracking points. 6 Once your track is done, switch off the Interactive Mode checkbox. DaVinci Resolve reverts to automatically placed tracking points. In a different interactive tracking case, you may occasionally hit situations where you'd like to scrap every automatically placed tracking point and set your own in particular image regions instead. To remove the automatic tracking points and substitute your own: 1 Open the Tracker palette. 2 Turn on the Interactive Mode checkbox.

Selecting Interactive mode 3 Within the Viewer, drag a box over every tracking point in the window, then click the Delete button to clear all tracking points off the image.

Selection box surrounding all tracking points 4 Click the Delete button to clear all tracking points off the image.

Deleting tracking points

5 Drag a box across the precise region where you'd like new tracking points added. Here you only want the top half of the woman's face tracked, since the fence posts cut off the lower half.

1 Positioning the selection box across the window's upper portion 2 Now, click the Insert Track Points button. Interactive mode's Insert button populates the current bounding box with tracking points by itself. The new tracking points settle automatically onto whichever features within your drawn box are well-suited for tracking.

### Tracking with the remaining tracking points

NOTE: When no suitable tracking features turn up, no points get added.
