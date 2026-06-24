# Resolve Fx Transform (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Resolve FX Transform

The plugins grouped here give you transform types — both keyframed and static — beyond what the Sizing palette or the Inspector's Clip Transform controls can offer.

### Match Move (Studio Version Only)

TIP: These days, match move tasks are handled far more capably on the Fusion page, where the relevant tools and techniques live. The Match Move filter works as a patch-style tracker, following a pattern area marked out by a tracker control. Apply the filter to a node and click any feature in the Viewer that you wish to follow, and you may add as many trackers as you want. The best candidates to track are sharply defined, high-contrast details with crisp angular edges. Every tracker control is made up of (a) a center point marking where the resulting motion path will be anchored, (b) a resizable inner box marking the image patch under track, (c) a resizable outer box marking the search region for that track, and (d) a patch window giving you a magnified close-up of the patch being followed. You resize patch windows, and reveal or conceal the remaining tracking controls, through the settings located in the Display Options section of the Match Move controls.

### A tracker control in the Match Move filter

Should a tracker control land somewhere by mistake, you can relocate it by dragging from anywhere inside the inner box, or remove it entirely by Option-clicking it. After it's down, resizing that tracker control determines how much picture detail gets factored into the analysis. Resizing is done by hovering the pointer over the inner box edge and dragging it smaller or larger. The plugin pulls out whatever amount of motion data the count of placed trackers permits:

- A single tracker follows position along the horizontal and vertical axes (pan and tilt).
- With two trackers or more, rotation is also followed.
- With four trackers or more, perspective is followed as well.
- Once you reach six trackers or more, the Match Move filter can on its own pick

from the whole set whichever tracker data is strongest, producing the most precise track achievable.

### A Match Move Workflow

What follows walks through the most basic end-to-end procedure for bringing in a foreground clip and compositing it, with a match move that tracks a background clip already sitting in the timeline. Use it for jobs like dropping a graphic onto the side of a building as a sign, or onto the screen of a phone. To match move: 1 Within the Media Pool of the Edit page, right-click whichever clip is to be match-moved onto a Timeline clip, then pick “Add as Matte For Color Page Clip” — this drops it into the Color page Node Editor of the clip currently selected, as a Timeline Matte. For now, that is the one and only way to match move and composite a foreground clip over a background clip while on the Color page. 2 Switch to the Color page, verify the destination background clip is selected, bring up the OpenFX library, and drag the Match Move plugin straight onto the link running from the tree's final node to the Output, dropping it in as its own independent FX node. Inserting the Match Move filter on its own as a standalone FX node 3 Right-click whichever corrector node you like in the node tree (here, Node 01), then from the contextual menu's Add Matte > Timeline Mattes submenu select the clip you brought in back at step 1, which surfaces that clip as an Ext. Matte node. Sever the link between the freshly created Ext. Matte node and whatever it connects to, then route its RGB output into the second input of the FX node instead.

Connecting the foreground image to the second input of the FX node

4 Select the FX node, confirm the OpenFX onscreen controls are turned on, decide whether tracking should kick off from the clip's first or last frames, and then click inside the Viewer to drop tracker controls onto the part of the image where the foreground image will be attached. For a perspective track, drop a minimum of four tracker patches onto regions you're confident won't be hidden by other elements in the frame. Pick angular, high-contrast features for best results, and do your best to keep the tracked features from leaving the frame or being covered by other things in it. While you drop tracking controls, each patch window takes on the tint of whichever channel DaVinci Resolve decides on its own will yield the strongest tracking outcome.

Dropping tracker controls onto the feature you intend to Match Move onto 5 (Optional) Where required, unwanted trackers can be removed by Option-clicking them. 6 With every tracker control now in place, the tracking analysis can begin. When the playhead sits at the clip's start, click Track Forward; otherwise click Track Backward. DaVinci Resolve then analyzes, on its own, every tracker control across the clip right through to its final frame.

Using the Tracking controls

7 (Optional) When a tracked patch gets covered by something, or the feature being tracked starts to drift past the frame edge, that tracker control can wander off and ultimately shut itself down. Should that occur, resuming the track is remarkably simple: a) Press the Track Forward (or Track Backward) button once more to halt the analysis. b) Roll the playhead back to the final frame holding good tracking data, then click the inner box of each tracker control that misbehaved to confirm it's active (a visible patch window tells you it's on), and click “Clear tracking forward” or “Clear tracking backward” as appropriate to wipe the bad tracking data. Once that's done, click the inner box of each errant tracker to switch it off again, so it stops trying to track wrongly (a hidden patch window tells you it's off). c) At this point, drop extra trackers onto other features of that same surface to stand in for the trackers you had to disable.

Dropping additional tracking controls to make up for those that shut themselves down on leaving the frame or being hidden by other moving elements in the picture d) Click “Track forward” again to pick the track back up, and DaVinci Resolve will draw on those extra features as it carries on the analysis. e) Once the analysis wraps up, switch the trackers you'd disabled back on. Every active tracker feeds data into the match move across whatever frame ranges hold valid tracking data for it. 8 After DaVinci Resolve wraps up its analysis, roll the playhead back to the track's first frame and pick Positioning from the “Show controls for” pop-up menu. That carries you into the following stage of the Match Moving process.

Choosing the Positioning controls

9 A grid shows up across the Viewer. This is the positioning canvas, which lets you corner-pin the region where the foreground image you wired up in step 3 gets composited and tracked. Dragging its corners both corner-pins and resizes it, while dragging the center repositions it.

Resizing the canvas to fit the foreground image into the background 10 With the grid placed, scrub forward and backward to confirm it tracks accurately and holds up visually once things move. 11 In the “Show controls for” pop-up menu, pick Compositing so the compositing controls appear. 12 Switch the Output pop-up menu over to “Composite” in order to render out the finished match-moved composite. As needed, the Composite Type and Plate Cropping controls let you set how the foreground image blends against the background and let you trim away unwanted edge portions of the image.

### The final match moved composite

With that, the match move is complete.

### Main Controls

Through the “Show controls for” pop-up menu you select among four control pages that walk you through the match moving workflow. The Output pop-up menu sets what gets output, offering Disabled, Positioning Reference, and Composite.

### Tracking Controls

The Tracking Controls oversee the opening stage of match moving, and this control page supplies all you require to set up, run, and fine-tune multi-patch motion tracks.

Controls revealed once Main Controls is switched to Tracking Controls The Tracking Controls group The main controls for kicking off tracking. They comprise the tracking buttons, which run tracks either automatically via the outer Track Forward or Track Backward buttons or by hand via the inner Track Next or Track Previous buttons. Pausing a track is handled by the middle button. The Next Track End and Previous Track End buttons jump you to earlier and later tracked spans of frames; whenever gaps exist in your tracking data, these controls hop you between separate stretches of continuous tracking data. A pair of checkboxes determines whether Zoom and/or Rotation gets tracked and analyzed. You have to set these before tracking starts.

### The Manage Tracking Patches group

Up top, two buttons govern which tracking patches are switched on to feed the overall match moving result and which are switched off. Activate None and Deactivate All flip every patch on or off in a single action.

Clear Past and Clear Future wipe out faulty tracking data either ahead of or behind the playhead's present position, applying to enabled tracker controls. Delete Tracking removes the tracking data only at the current frame, again for enabled tracker controls. Refresh Tracks renews a tracker control's patch whenever the tracked feature shifts enough in shape, color, or lighting to disrupt the track. Pick one or more trackers and click Place New Patch in Track to refresh the tracked feature at that frame.

### The Display Options group

Use this group to toggle whether various onscreen controls appear. Its checkboxes cover Show Trackers; Show Center, meaning the red center point of the track; Show Paths, meaning the motion paths that were tracked; and Show Active Patches. A slider sets the dimensions of each patch window. Show Comp Result reveals the composited foreground layer over the background layer.

### Positioning

The Positioning controls handle the second phase of the match moving process. They give you all you need to transform the foreground image so it sits against the background, through repositioning, corner-pinning, and resizing.

Controls revealed once Main Controls is switched to Positioning Canvas Options The Canvas Controls pop-up menu toggles you into corner-pin controls, in which dragging each of the four corners performs corner-pinning, dragging the center moves the grid, and dragging the top, bottom, or sides scales it vertically or horizontally. A Reset Corners button returns the grid to full screen, handy when you want to abandon the current attempt and start fresh.

### The Display Options group

Within this group you switch the display of assorted onscreen controls on or off. The available checkboxes are Show Trackers; Show Center, being the red center point of the track; and Show Paths, being the motion paths that were tracked. Show Comp Result displays the composited foreground layer over the background layer.

### Compositing

The Compositing controls oversee the third phase of match moving, used as you fit the foreground image against the background image to build a seamless composite. Note that if the foreground image needs color correction to match the background, you'll have to insert a corrector node between the Ext. Matte feeding the foreground image into the Color page and the FX node performing the compositing.

Controls revealed once Main Controls is switched to Compositing Rendering Options: Through the Composite Type pop-up menu you decide whether the output composite is the Ext. Matte overlaid on the background or the background Plate by itself. Plate Cropping: Four sliders trim the Left, Right, Top, and Bottom of the image as required. Global Blend: The Blend slider, found in every Resolve FX plugin within DaVinci Resolve, sets the effect's opacity, which in practice governs how opaque the foreground layer is.

### Stabilizing

Despite the name, the Stabilizing controls have nothing to do with match moving; rather, they let you repurpose the motion tracking produced via the Tracking Controls to steady the image. An Edge Behavior pop-up menu determines how to deal with the blanking that appears around the edges when the background image is transformed to hold the frame's subject in position.

Controls revealed once Main Controls is switched to Stabilizing

### Surface Tracker (Studio Version Only)

The Surface Tracker serves to lay textures and effects onto pliable or deformable moving surfaces such as cloth and skin. It makes certain that the way the texture or effect folds and deforms convincingly tracks the folding and deforming of the surface it's pinned to within the image. As a sophisticated effect, the Surface tracker carries a wide array of options and controls aimed at producing the most lifelike composites achievable. In every case, though, you simply proceed left to right across the buttons sitting in the effect's settings. 1 Press the Bounds button, then click on the screen to mark out the surface region where the fresh texture should go. The bounds ought to cover a single surface at a time and steer clear of crossing or sitting on object edges. 2 Press the Mesh button to set the control points that follow the surface's natural folds and curves inside the bounds. 3 Press the Track button so the surface's motion gets analyzed over time, drawing on the Mesh you just laid out. 4 Press the Result button to lay the texture over the top of the moving Mesh. The advice is to run the Surface Tracker as its own FX Node, dragged straight from the effects library into the node tree, instead of attaching it to an ordinary corrector node. Doing so gives you an extra Alpha input for laying down textures that carry some built-in transparency. On each of the Surface Tracker's tabs, the Tracked Range reports the first and last frame numbers of your clip that hold tracking data. Altering the bounds or the mesh layout clears any tracking data already present, and you'll have to track it again.

(Left) The Surface Tracker at work, laying the logo on, and (Right) bending and matching it convincingly to the shirt's folds.

### Bounds

Here is where you're asked to outline a region on the image onto which the texture should go. The best choice is a clip frame in which the surface you intend to track sits as near to the camera and as flat-on as it can. That frame then serves as the effect's default reference frame. To use the tool, confirm the Open FX Overlay controls are switched on in the Viewer. Just click around the image to drop several points enclosing the region you're defining (three points at minimum), and the effect joins them into a polygon for you automatically. Place boundary points on the surface being tracked, not surrounding it. Dropping points on object edges or the background by mistake will introduce tracking errors.

The same image can carry several boundaries and several holes; every boundary merges into a single shape first, and then the holes are subtracted from it. Multiple boundaries and holes exist so you can mask off intricate surfaces, leaving out regions you don't want tracked. You might, for instance, draw a boundary around a person's face while using several holes to leave out the eyes and mouth, since those shift appearance rapidly as the subject blinks and speaks and are therefore extremely hard to track. Multiple boundaries are meant for one shared surface; applying them across different surfaces in the image produces poor results. To track distinct surfaces, it's better to use several instances of the Surface Tracker. The boundary isn't meant for rotoscoping objects, only for studying a surface's motion. For rotoscoping foreground objects, see the discussion in the Tracking Using a Mask section further down. Click to Add Points: These controls are what you use to form boundary regions on the image.

- Boundary: The boundary region presently selected on the image. The drop-down menu switches which boundary or hole is current. Where a boundary has problems (such as crossed edges, too few points, and so on), an error message shows up beside its name.
- - Bound: Drops a boundary polygon onto the image. Several boundaries can be set for one surface, and they get merged into a single shape.
- - Hole: Introduces a region that's left out of tracking on the surface. It's used to strip overly intricate, shifting portions of a surface out of the effect's calculations.
- Delete: Removes whichever boundary or hole is selected in the Boundary field. At present this action can't be undone, so treat the button with care.
- Clear All: Wipes out every boundary and hole in the effect.

### Mesh

Once the boundaries exist, you go on to lay the mesh across the surface that's to be tracked. Because the starting mesh is what tracking builds from, you'll get the best outcome by placing it while your surface is as flat-on and as close to the camera as it gets. You tweak the mesh by hand, dragging existing points (hold command and drag a box around several points to move them together) or clicking somewhere to drop new ones. Option-clicking a point deletes it from the mesh. Hand-placing mesh points helps when the surface has flexible spots known to fold the texture but not picked up when the mesh first goes down. An outstretched arm, say, might lack an active mesh point at the elbow, yet a mouse click (paired with a little grasp of human anatomy) lets you add one there. Another scenario is seeding points in a low-detail region that you anticipate will gain detail as it turns into view. Dropping mesh points into flat, detail-poor areas won't help results and can in fact worsen them, so keeping points sparse on smooth areas is preferable. As a rough guideline, once more than five points sit inside the boundaries, the mesh is probably solid enough to track. Points can't be added or removed once tracking is done. Since they go hand in hand, a good mesh signals good tracking. When your mesh registers few points and the results fail to track tightly, you can boost your results deliberately. For instance, make sure the content is plainly visible. Tracking and point detection can break down if the surface is overly bright (HDR), overly dark, or low in contrast from working in log. To get better results, place a corrector node ahead of the Surface Tracker to set contrast and levels by hand, then run the Surface Tracker. You could

likewise put a corrector node carrying the Contrast Pop effect ahead of the Surface Tracker to assist with tracking surfaces that are too smooth. Either way, just switch the corrector node off again once tracking has wrapped up.

- Regenerate Mesh: Clicking this rebuilds the mesh using the current frame and settings, throwing away whatever manual edits were made.
- Point Locations: These controls set which mode produces the mesh points.

Automatic: On its own, the Surface Tracker finds the best details for tracking and drops mesh points onto them. Automatic yields the best results in most situations.

- Point Number Limit: Sets the ceiling on how many mesh points get placed. How the overlay flexes and folds depends on the mesh point count, which you should match to how flexible you expect the surface to be. They have no direct bearing on tracking speed.
- Minimum Point Spacing: Sets the smallest allowed gap between mesh points. It keeps mesh points from clustering too densely in highly detailed regions and getting in each other's way.
- Uniform Grid: Lays down an even grid of points within the boundary and leans on internal shape models to warp that grid as tracking proceeds. On a highly detailed surface this can outperform Automatic mode.

Horizontal Spacing: Tunes the horizontal gap separating neighboring points in the uniform mesh. Vertical Spacing: Tunes the vertical gap separating neighboring points in the uniform mesh.

### Track

In this part of the effect, the motion of the mesh points is tracked across time. The Tracking Direction controls let you run the tracking procedure through the clip. Once tracking finishes, the effect performs no further analysis, and you can throw away any extra contrast help from upstream nodes after this step. Straightforward cases may track all the way through with no user involvement, while trickier ones call on several extra controls to refine the track. Repairing a broken track means making some manual tweaks to both the mesh and the tracking data. Whenever tracking is underway, you can adjust mesh points individually or with the lasso selection tool (Command - Drag) drawn around the whole mesh or only portions of it. That lasso selection tool can also stretch, scale, and rotate the mesh points, so it's simpler to deform the mesh by hand and set it precisely where you want should the automatic tracking fall short for some reason. That said, you can't add or delete extra mesh points at this point without first resetting the tracking.

Command-Drag lets you lasso a group of mesh points and then scale, rotate, and stretch them however you need.

Hand-editing the mesh points at one frame changes only that frame directly and leaves the adjacent tracking data alone. It does, though, alter adjacent interpolated positions, which makes it useful for tracking from that frame forward. For example:

- The track holds up through frame 150, where a handful of points break away from the others because of a lighting shift. Those points can be dragged back into place at frame 150, and if you then resume tracking, they carry on from their corrected positions.
- Tracking runs to frame 150, then has no data for a few frames until it picks back up at 160. Editing the points at either frame 150 or frame 160 makes the frames in between interpolate with those edits factored in.
- Tracking covers up to frame 150 and again from frame 160 on, leaving frames 151-159 interpolated. Some points get adjusted at frame 155. That generates tracking data at that frame, so now frames 151‑154 interpolate from the last tracked frame to this one, and frames 156-159 interpolate from this one to the next tracked frame.

Suppose something in the frame covers the tracked surface — say you're tracking a mesh on a shirt and the person's arm sweeps down through the mesh, breaking the track. An Alpha channel may let you resolve this, as the Tracking Using a Mask section below explains. Tracking data also appears as keyframes within the Keyframe Editor under the FX node's Surface Tracker keyframing data, and it's reachable too as the bottommost control in the Track section, where data at a frame can be made or removed directly.

- Go to Start: Pressing this jumps the playhead to the earliest tracked frame, or to the frame on which the boundary was made.
- Go To End: Pressing this jumps the playhead to the latest tracked frame.
- Tracking Direction Controls: These controls run the tracking analysis in whichever direction

is shown. Reading left to right, they run: Track Backwards, then Track Backward One Frame, next Pause Tracking, after that Track Forwards Then Reverse, followed by Track Forwards One Frame, and lastly Track Forwards. With them you can lay the track over the entire clip or restrict tracking to only a portion of it.

- Tracking Data Controls: These controls let you work with the track data once it has been generated.
