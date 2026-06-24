# 3D Camera Tracking (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### 3D Camera Tracking

These pages walk through how the Camera Tracker node operates and the workflow built around it. The point of camera tracking is to derive a virtual camera inside Fusion's 3D environment from how a real camera moved through a live-action clip. With that virtual camera in hand, you can drop 3D models, text, or flat 2D images into a live‑action shot whose camera is in motion.

To read up on Fusion's remaining tracking methods, turn to Chapter 82, "Using the Tracker Node," within the DaVinci Resolve Reference Manual, or to Chapter 22 in the Fusion Reference Manual.

### Introduction to Tracking

Few compositing techniques are as valuable or as fundamental as tracking. Loosely speaking, it means producing a motion path by studying how a chosen region behaves across the frames of a clip. To handle the various kinds of motion you might encounter, Fusion ships several distinct tracking nodes, and every tracker type is documented in its own chapter here. The material below concentrates on tracking by way of the Camera Tracker node.

### What Is 3D Camera Tracking?

Match moving relies on camera tracking, which bridges 2D footage and 3D scenes so that artists can drop 3D CGI elements into live-action clips. By working out where the real camera traveled, the Camera Tracker node produces a virtual camera positioned in 3D space. The aim is for that virtual camera to behave just like the one that originally filmed the shot, reproducing both its movement and its lens focal length. Getting that virtual camera's location and motion right is what makes 3D elements sit convincingly against the live action.

An example of 3D elements integrated in a live-action scene

### How Camera Tracking Works

The starting point for camera tracking is following stationary features as they shift from frame to frame. Said differently, the algorithms latch onto features that are "nailed to the set." Anything that travels on its own apart from the camera, like passing cars or pedestrians, degrades the tracks, which is why masks can rein in which features get tracked and sharpen the outcome. It also pays to supply concrete camera metadata, for instance the sensor dimensions and the lens focal length. Feeding that data into the scene-reconstruction step, known as a solver, steers it toward a truer virtual camera. What the Camera Tracker ultimately delivers is an animated 3D camera plus a point cloud of the scene. That point cloud is a dense collection of points the solver produces, approximating where the tracked features sit in 3D. You can then lean on the point cloud to line up other 2D or 3D elements beside the live-action footage.

### The Camera Tracking Workflow

There are two principal stages to camera tracking: 1 Tracking, the act of examining a scene. 2 Solving, which works out the virtual 3D scene. After both stages are finished, an animated camera and point cloud get pushed from the Inspector into a 3D composite. All of this lives inside the single Camera Tracker tool. Across the top of the Inspector sit five tabs, ordered loosely to match the sequence you'll follow. The five tabs are:

- Track: Used to track a clip.
- Camera: Configures the basic Camera parameters.
- Solve: Works out where the 2D tracking points belong in 3D and rebuilds the camera.
- Export: Produces a Camera 3D node, a Point Cloud node, plus a 3D scene within the node tree.
- Options: Used to customize the look of the onscreen overlays.

### The Camera Tracker tab

### Clips That Don't Work Well for Camera Tracking

While the Camera Tracker runs largely on its own, there are moments when it leans on you. Spotting likely trouble up front, before any tracking or solving, can spare you a great deal of effort. Some footage is far harder on the tracking process than other footage. A few of these cases can be repaired; with others you simply concede and reach for a different approach. Below is a roster of shot types worth watching for, since each one tends to be a real thorn for camera tracking:

- Lack of depth: For the process to function, a clip has to contain parallax. As the camera travels, you need to be able to tell nearer objects apart from ones farther off. With everything sitting an equal distance away, depth simply can't be derived. Here you're better off bypassing the Camera Tracker node and looking for a different route.
- Locked-off shots: A camera that never moves leaves no basis for working out which objects sit nearer and which sit farther. Once more, don't sink much effort into this case; bypassing the Camera Tracker node and finding another route is the wiser move.
- Tripod pans: Much like a locked-off shot, a pan that stays fixed atop a stationary tripod offers no basis for sorting nearer objects from farther ones. Bypass the Camera Tracker node and look for a different route.
- No detail: Footage such as green screens lacking tracking markers simply doesn't carry enough detail to track. Should you be fortunate enough to take part in filming these kinds of shots, dropping in tracker markers makes a solid track far simpler to obtain. Lacking detail, the tracking will fall apart and you'll have to turn to a more hands-on fix.
- Motion blur: Quick camera moves or long shutter exposures can bring on motion blur, which complicates the hunt for patterns to track. Footage like this is worth a try to gauge whether enough detail survives for a good solve, but recognize the moment to abandon it for another route.
- Rolling shutter: With CMOS-based cameras, the shutter records separate lines at marginally different instants, which can throw in distortion. For camera tracking, that distortion can spell serious trouble. On occasion you can build motion vectors via the Optical Flow node, synthesizing fresh in-between frames that drop the rolling shutter's wobble. The fixed-up footage can then feed into the Camera Tracker.
- Parallax issues: Where objects at varying distances overlap within the frame, that overlapping region risks being read as a corner. A tracker placed on such an overlapping angle will throw errors once the parallax begins shifting and that overlap region drifts. The remedy in Fusion is deleting that tracker ahead of the solve.
- Moving objects: Capturing a shot in which nothing moves is tough. Crowds, vehicles, animals, and the like can drift into and out of frame. Since these objects travel apart from the camera, they must be removed or they'll trigger solving errors. The fix is masking off anything not "nailed to the set." Those masks then route into the Track Mask input on the Camera Tracker node.

TIP: Footage that defeats Fusion's Camera Tracker can sometimes be handled by purpose-built 3D camera-tracking packages such as 3D Equalizer and PF Track. The tracking data those programs produce can later be brought into Fusion through the Camera3D node.

### Outputting from the Camera Tracker

In contrast to nearly every other Fusion node, the Camera Tracker node provides two separate outputs:

- The first one, a 2D view, serves you while you lay out the Track, fine-tune the camera, and carry out your initial solve.
- The other, a 3D output, comes into play once that initial solve is done, letting you survey the camera path and point cloud throughout 3D space. It proves useful while you polish tracks for a more accurate solve and square up your ground plane. You can run it alongside the 2D output in side-by-side views.

Keep in mind that whatever tracks you select in the 2D view stay linked to their matching locators in the point cloud over in the 3D view. On top of that, both the 2D and 3D views carry viewer menus that put fast control of this tool's behavior at your fingertips.

### 2D View

For this node, the 2D view serves as the main display. When you view the node you see the footage under analysis along with overlaid tracker markers and the paths they trace. A purpose-built toolbar puts the everyday tracking and solving controls within reach.

The Camera Tracker 2D output with toolbar and auto-track points

### 3D View

A 3D scene comes out of the Camera Tracker node's second output. Seeing it requires routing that 3D output into a 3D Transform or Merge 3D node, then viewing the latter.

After solving, routing the Camera Tracker node's second output into a Merge 3D shows the point cloud in 3D. Following an initial solve, that 3D output presents the point cloud together with the camera and the image wired to it. Picking points brings up the Camera Tracker toolbar over the viewer, handing you control over assorted actions like renaming, deleting, and recoloring the point-cloud points.

3D output of a point cloud and a solved camera path

### Auto-Tracking in the Camera Tracker

The word tracking covers the job of watching or examining a run of frames (in other words, a clip). Before it can pin down where the virtual camera sits and how it moves, the Camera Tracker node has to account for how the original footage moves. On its own, the Camera Tracker tool hunts down high-contrast patterns in the clip and pins trackers onto those features. The strongest track comes from spreading tracking points broadly over the frame and from points that persist for a long duration.

### Increasing Auto-Generated Tracking Points

Whereas you place tracking points yourself with the Tracker node, the Camera Tracker handles it fully automatically, though the Detection Threshold and Minimum Feature Separation sliders give you control over the rules used to locate tracking points. Drop those values and you raise how many tracking points turn up. That comes in handy when a scene yields too few points, leaving the solver unable to build an accurate camera and point cloud. Still, tread carefully with these tweaks, because piling on too many points can spawn redundant trackers that bog the whole process down while gaining you little.

### Previewing Tracking Points

To inspect the tracking points the clip currently has, view the Camera Tracker node and switch on the Preview AutoTrack Locations checkbox. Doing so paints green tracking points into the viewer while you scrub through the clip. That preview lets you judge whether the Detection Threshold or Minimum Feature Separation need tweaking to raise or lower how many tracking points appear on their own.

Green tracker dots appear on their own atop the features within an image Bi-Directional Tracking As you run a track, switching on the Bidirectional Tracking checkbox makes it track forward from the clip's beginning first, then run a reverse second pass. By revisiting points that the forward pass first found, this two-pass method may stretch out how long any given point lasts. Short of being pressed for time, there's hardly a reason to leave it off. Yes, bidirectional tracking eats more time, yet it generally pays off and runs fairly fast given what you gain.

### Choosing a Tracking Algorithm

You get three options for which tracking algorithm runs. Those three live in the New Track Defaults section of the Inspector:

- Optical Flow: Generally the pick to reach for, except when a clip is full of criss-crossing objects.
- Tracker: A solid fallback whenever motion-estimation trouble like criss-crossing objects rules out Optical Flow.
- Planar: Suited mainly to plainer clips, where most of the frame is made of flat surfaces like building facades.

### Masking Out Objects

As it tracks a clip, the Camera Tracker lays down trackers on feature details on its own. That said, not every feature that pops out in a clip suits camera tracking. The only features you want tracked are those "nailed to the set." Put another way, things that move on their own apart from the camera, such as cars and people in motion, introduce errors during camera tracking. Such objects have to be cut from the analysis. Masking is the main route to steering clear of these trouble spots. By wiring a mask into the Camera Tracker node's Track Mask input, you mark which regions of a scene the Camera Tracker is allowed to study. Take a shot of an airport runway beside a coastline: the water's waves and the drifting clouds overhead need masking because they travel independently of the camera. As you build the mask, the steady portions of the image meant for tracking analysis belong in the white part of the mask. Everything in motion that should be skipped belongs in the black part. That mask then gets wired into the Camera Tracker Track Mask input.

Masks keeping the drifting clouds and waves out of the Camera Tracker's analysis

With that in place, the tracker disregards the water's waves and the drifting clouds. This mask isn't like one you'd draw for an effect; it needn't be exact. Your only aim is to mark the approximate zone you want hidden from the tracking analysis.

On the left, the source image set for tracking; on the right, the occlusion mask covering the clouds and water

TIP: When a shot carries plenty of motion, the Tracker or Planar Tracker nodes can drive your occlusion mask so it rides along with the region you mean to track. Bear in mind, though, that once the PlanarTracker or PlanarTransform node has warped your mask, a Bitmap node is needed to convert it back into a mask suitable for the Camera Tracker node's Track Mask input.

### Matching the Live-Action Camera

With tracking behind you, the workflow's following stage calls for the controls on the Camera tab. Here you describe the real camera that was used on set, chiefly its film gate size and focal length. Ideally that detail was recorded on set so it's on hand during postproduction. With camera-original media, the file metadata will sometimes hold this information. Use the steps below to track down camera metadata:

- Working in DaVinci Resolve, pick the MediaIn node holding the camera clip, bring up the Metadata Editor, and look at the Camera metadata preset.
- Working in Fusion Studio, bring up the metadata subview using the viewer toolbar.

### The Camera tab in the Camera Tracker tool

When you don't have the real figures, make your best estimate. Because the solver hunts for a camera in the vicinity of these settings, handing it values as near to the live action as you can manage helps it along. Better input on your part yields a more precise solver result. As a bare minimum, at least pick the right camera model in the Film Gate menu. Choose the wrong film gate and the odds of the Camera Tracker nailing the lens focal length drop sharply. Unlike the Track and Solve tabs, the Camera tab carries no button at the top of the Inspector to kick off a process. Once the camera settings are in place, the Camera tab has nothing further to run. Having dialed the camera settings to match the live-action camera, you head over to the Solve tab.

### Running the Solver

This phase of the workflow centers on the controls living in the Solve tab. Solving is a heavy computation where the Camera Tracker studies the tracks that currently exist to build a 3D scene. Out of it come a virtual camera mirroring the live action and a point cloud of 3D locators that reproduce the tracked features in 3D space. Driving the analysis is the frame's parallax, the effect whereby features nearer the camera appear to travel faster than those farther off. Picture gazing out a car's side window, where distant scenery drifts by more slowly than whatever sits near the road's edge. Whether the solver succeeds or fails hinges heavily on the trackers gathered during the Track phase, so handing it the finest set of tracking points from the outset is essential. Even though the occlusion masking you set up earlier strips out troublesome tracking points, you'll nearly always have to thin and remove low-quality tracks further inside the Solver tab. That's why, from your vantage point, solving is best approached as something you repeat. To work out a camera's motion: 1 Press the Solve button so the solver runs. 2 Screen out and remove weak tracks. 3 Run the solver once more.

The Solver tab once a run has finished, yielding an average solve error of 04367 pixels

### How Do You Know When to Stop?

Once solving wraps, an Average Solve Error (also referred to as a reprojection error) shows up at the top of the Inspector. That number is the key gauge of how well the computation turned out. For HD material, anything under 1.0 counts as a good Average Solve Error. Read a value of 1.0 as a one-pixel offset, meaning the track might be off by a single pixel at any moment. As resolution climbs, the solve error ought to drop. On 4K footage, aim to land the solve error under 0.5.

### Tips for Solving Camera Motion

Feeding the solver precise live-action camera details, like focal length and film gate size, can lift the camera solve's accuracy considerably during this stage. As an illustration, a focal length that strays too far from the true physical figure can leave the solver unable to converge and the result worthless. Beyond that, to let the solver triangulate and rebuild the camera and point cloud accurately, you'll want:

- Tracks spread sensibly over objects at assorted depths, without overloading the far background or sky (those add no extra perspective cues for the solver).
- Tracks scattered uniformly across the frame rather than bunched onto a handful of objects or just one side.
- Track beginnings and endings spaced out across time, so few of them finish on the very same frame.

### Using Seed Frames

To begin, the solver assembles a partial solution spanning a pair of seed frames. Normally those seed frames are chosen for you. That automatic pick, however, tacks extra time onto the process. The amount shows up in the solve summary at the top of the Inspector after you run the solver. Picking your own seed frames can trim that time and may yield a stronger solve on tougher clips. From this intermediate solution built on the seed frames, the solver then grows it both forward and backward across the whole clip. Hand-picking seed frames isn't really advised unless camera tracking is already familiar territory for you. Leaving the default Auto Select Seed Frames checkbox turned on in the Solve Options section of the Solver tab picks the optimal frames the bulk of the time. You can, though, clear the checkbox and reach for the Seed Frame 1 and Seed Frame 2 slider to land on frames you think will do better. Two key qualities matter when you settle on seed frames:

- Seed frames should have lots of tracks in common.
- Seed frames should be far apart in perspective.

### Sometimes There's Nothing You Can Do

When a shot lacks the camera motion needed to triangulate where features sit, no reconstruction will reach any worthwhile accuracy. Making a shot camera-trackable starts during the shoot, through the right use of track markers and by making certain the camera moves carry enough shifts in perspective for the solver to extract something useful.

### Cleaning Up Camera Solves

At times the very first solve is already fine. On other occasions you might burn several hours pruning tracks to reach a solid solve, and once in a while it simply can't be done. Over time you develop an instinct for which tracks ought to go and which to keep, and for which shots will prove easy, hard, or hopeless. Watch out, though: stripping away too many tracks can drive the Average Solve Error up, since the solver ends up starved of data. Specifically, with under eight tracks on a frame, the math just doesn't carry enough information to solve the clip. That said, for a sturdy, accurate solve you'll want comfortably more than eight tracks in play. IMPORTANT: When camera tracking is new to you, there's a pull toward reaching straight into the Spline Editor and reshaping the solved 3D splines to better a camera's motion path. Treat that path as a true last-ditch option. The smarter move is to adjust the 2D tracks you're feeding the solver.

### How to Judge Track Accuracy

Because tracking markers get color-coded on their own, weeding out false or weak tracks becomes simpler. After the solver finishes, every tracker receives a solve error color flagging which 3D locators line up closely with their 2D tracking points and which line up badly.

- Green: Good. Tracked very well.
- Yellow: Moderate confidence. Usually an acceptable track.
- Orange: Low Confidence. May be acceptable in some situations.
- Red: No Confidence. The tracks have not solved well.

Park the pointer over any tracking point and a sizeable metadata tooltip pops up carrying that point's solve error. For a clearer picture of the accuracy, switch on the 3D locator display in the viewer using the Reprojection Locators button on the viewer toolbar.

After a solve, the Camera Tracker toolbar can display Reprojection locators As the solver turns the tracking points into a point cloud, it generates a 3D reprojection locator for every tracking point. Each of these Reprojection locators shows up as a tiny X mark beside its matching tracking point. The tighter those two sit on each other, the smaller the solve error.

Reprojection locators displayed with tracking points, and tooltip Filtering the trackers comes down to clearing out every red tracker mark while holding onto all the green ones. Deciding whether to keep both yellow and orange, or yellow alone, mostly depends on how many marks the clip gives you. Keeping yellow marks only yields a better solve, yet if there aren't enough marks left to compute the 3D scene, you'll have to retain a few of the stronger orange ones too. Tips for What to Keep and What to Delete Learning to recognize false tracks, then trimming the track data by hand down to a tight set of clean tracks, leads to a more accurate solve. As you tidy any track—especially the yellow and orange color-coded ones—bear these points in mind:

- Hold onto any track whose movement is driven entirely by the movement of the

live‑action camera.

- Remove tracks sitting on people or objects in motion, along with any that suffer parallax issues.
- Remove tracks showing up as reflections in glass or water.
- Remove tracks on highlights that slide across a surface.
- Remove tracks that fail to track a feature cleanly.
- Remove tracks landing on false corners produced where

foreground and background layers overlap.

- Think about removing tracks tied to locators the solver placed

at the wrong Z-depth.

### Deleting Tracks

Removing tracks can be done by hand in the viewer or through filters that grab batches of tracks at once. For hand-deletion in the viewer, it helps to tweak the viewer a little so the tracks read more clearly. On the Camera Tracker toolbar over the viewer, hitting the Track Trails button conceals the trails behind the tracking points. With the viewer thus tidied to points alone, selecting becomes easier. Over at the toolbar's far right, the Darken Image button dims the image a touch, once more helping the points pop in the viewer.

Concealing trails and dimming the viewer makes spotting and picking out weak tracks simpler
