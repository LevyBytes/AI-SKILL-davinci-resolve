# Tracking Nodes (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Track to start: Runs the track backward from the current frame to the start (set by the current render range).
- Step tracker to previous frame: Advances the track one frame back, from the current frame to the prior one.
- Stop tracking: Halts whatever tracking operation is underway.
- Step tracker to next frame: Advances the track one frame forward, from the current frame to the following one.
- Track to end: Runs the track forward from the current frame to the end (set by the

current render range).

- Trim to start: Clears every bit of tracking data ahead of the current frame.
- Delete: Wipes all tracking data across all times. Reach for this to throw away every current result and begin

tracking afresh.

- Trim to end: Clears every bit of tracking data after the current frame. It comes in handy, for instance, to

cut off the tail of a track that has drifted out of accuracy once the pattern begins sliding off frame. Show Splines Located just to the right of the "Trim to end" button, this control brings up the Spline Editor and displays the splines tied to the Planar Tracker node. It helps when, by hand, you need to delete points belonging to the Track as well as the Stable Track splines. Right-Click Here for Track Spline During tracking, a spline is built that holds 4 x 4 matrices at every keypoint. It goes by the name "Track spline," or simply "Track." Those matrices fully describe the distortions of the tracked pattern. Create Planar Transform Once footage has been tracked, pressing this button spawns a Planar Transform node in the Node Editor. The present tracking data is baked into the Planar Transform node so it can reproduce the planar distortions that the Planar Tracker node captured. Unless your composite involves a full frame foreground matching the raster's dimensions exactly, the best practice is to make a Planar Transform and drive the foreground's motion with it.

### Steady Mode

With Steady mode, the Planar Tracker warps the background plate so as to hold the pattern as still as it can. Whatever motion remains stems from the Planar Tracker not tracking the pattern precisely, or from the pattern not sitting on a genuinely planar surface. Steady mode does little for real stabilization, yet it works well for gauging a track's quality. When the track is solid, the pattern stays put during playback while the surrounding background plate warps around it. A useful check is to zoom into portions of the pattern, hover the mouse cursor over a feature, and watch how far that feature wanders from the cursor across time. Steady Time This is the moment at which the pattern's position is captured and pinned in place. Setting it to the reference frame is the usual choice. Invert Steady Transform This makes the Planar Tracker node undo what the steady transform did. So two Planar Tracker nodes chained one after another, with the second set to invert, ought to return the original image. Drop an effects node between the pair and the effect becomes locked in place. Reserve this for effects that corner pinning cannot achieve, since the two resamplings involved soften the background image. Clipping Mode Decides what becomes of the parts of the background image pushed off frame by the steady transform:

- Domain: The off frame parts are kept.
- Frame: The off frames parts are thrown away.

Domain mode pays off when Steady mode is being used to "lock" an effect onto the pattern. Picture, for instance, painting onto the license plate of a car in motion. One approach steadies the license plate with a Planar Tracker node, paints over it via a Paint node, and finally reverses the steady transform using a second Planar Tracker. With the Clipping mode at Domain, the off frame parts the first Planar Tracker produced are retained, letting the second Planar Tracker map them back into the frame.

### Corner Pin Mode

With Corner Pin mode, one or several textures can be pinned to a planar surface that was tracked earlier and made to take on the surface's perspective distortions. Here is the Planar Tracker corner pin workflow: 1 Track: pick a planar surface in the shot where you want to add a texture or swap an existing one. Track the shot, following the Track section's description of the tracking workflow. 2 Set the Operation Mode to Corner Pin: Moving into Corner Pin mode from Track mode hides the pattern polygon and puts a corner pin control in the viewer. 3 Connect in the texture: Within the Node Editor, route the output of the MediaIn node holding the texture into the Planar Tracker node's Corner Pin 1 input. 4 Adjust corner pin: Within the viewer, drag the corner pin's corners until the texture lands correctly. The Show Grid option is sometimes handy while placing the texture. For finer placement, you can also scrub to other times and tweak the corner pin there. 5 Review: Play the footage back and confirm the texture "sticks" to the planar surface.

### Merge Mode

Governs the way the foreground (the corner pinned texture) composites over the background (the tracked footage). When several corner pins exist, they all share this single option. Four choices are offered:

- BG only
- FG only
- FG over BG
- BG over FG

Number of Corner Pins The + and - buttons raise or lower how many corner pins there are. Every time you add another corner pin, a matching input shows up on the node within the Node Editor. Corner Pin 1 Input Group A set of related inputs belongs to each corner pin:

- Enable: Sets whether the corner pin is shown in the viewer.
- Show Grid: Overlays a grid on the corner pin, which helps while placing the corners.
- Merge Options: Governs how the corner pin texture composites over the background. (Refer to the

Merge node's documentation.)

- Reference Time Positions: Where the four corners sit at the reference time. Should the track fall

short of perfect, these positions can be animated to layer adjustments on top of the track.

### Stabilize Mode

Stabilize mode evens out camera shakiness by applying a transform that partly cancels the camera shake. That stabilizing transform (held in the Stable Track spline) is worked out by comparing neighboring frames. NOTE: Where Steady mode aims to "lock off" all motion entirely, Stabilize mode merely smooths motions. Keep in mind that the Planar Tracker stabilizes off the pattern's motion, so picking the pattern with care is essential. When the pattern's motion fails to stand in for the camera's, the results can be surprising. As an example, tracking the flank of a moving truck while the camera travels alongside it leads the Planar Tracker to smooth the combined motion of both the truck and the camera mounted to it. Sometimes that is not what you want. A better pick may be a stationary object such as the road or a building's side, which leaves only the camera's motion smoothed. An unavoidable byproduct of stabilization is that transparent edges show up along the borders of the image. They appear because the stabilizer knows nothing of what sits off frame, so it cannot fill in the absent pieces. The Planar Tracker node lets you either crop or zoom these edges away. While shooting, if post-production stabilization seems likely to be needed, filming at a higher resolution (or a lower zoom) can occasionally help.

The Planar Tracker Stabilization Workflow 1 Track: Choose a broadly planar region that stands for the motion you mean to stabilize. Track the shot, following the Track section's description of the tracking workflow. 2 Set the Operation Mode to Stabilize: Up until a stabilization is calculated, the Planar Tracker simply passes the input footage through. 3 Adjust stabilization options: The options most often altered are Parameters to Smooth and Smoothing Radius. 4 Compute stabilization: Click the Compute Stabilization button and let the stabilization calculations run to completion. Play back the Planar Tracker node's output to view what the stabilization did. Note that the stabilization transform has brought transparent edges in around the image's borders. 5 Refine: Tune the stabilization options and recompute as many times as you like. 6 Handle transparent edges (optional): Choose Zoom or Crop for the Frame Mode as you prefer, then click the Auto Zoom or Auto Crop button. Play the footage back to see the result. Should there be excessive zoom, or the image be cropped too tight, try dialing back the amount of smoothing.

### Parameters to Smooth

Specify which of the following parameters to smooth:

- X Translation
- Y Translation
- Rotation
- Scale

Smoothing Window As a given frame is stabilized, this sets how the input from neighboring frames is weighted. The options on offer are Box and Gaussian. Smoothing Radius (Frames) Sets how many frames have their transforms averaged together when the stabilization is computed. Raising the Smoothing Radius produces more smoothing but also brings in more transparent edges. Compute Stabilization A click on this button runs the stabilizer and replaces whatever any earlier stabilization produced. The moment the stabilization completes, the Planar Tracker node's output refreshes at once with the stabilization in effect. NOTE: To produce the Stable Track spline, the stabilizer draws on the Track spline (which the tracker made). The keyframes of both splines carry 4 x 4 matrices, and those keyframes can be edited in the Spline Editor.

Clipping Mode Decides what becomes of the parts of the background image pushed off frame by the stabilization:

- Domain: The off frame parts are kept.
- Frame: The off frames parts are thrown away.

Frame Mode This governs the handling of transparent edges. Its options are:

- Full: Do nothing. Leaves the transparent edges as is.
- Crop: Trims the transparent edges away. With this option chosen, the Planar Tracker's

output image ends up smaller than the input image. No image resamplings take place. While in Crop mode, click the Auto Crop button or set the crop window by hand with the X Offset, Y Offset, and Scale sliders. Auto Crop Button: A click on this button has the Planar Tracker survey every frame and choose the biggest crop window that clears all the transparent edges. That computed crop window stays centered in frame and pixel aligned. On click, Auto Crop refreshes the X/Y Offset and Scale sliders.

- Zoom: Enlarges the image until the transparent edges fall off frame. Picking this option triggers an image resampling. Its drawback is a drop in quality (a slight softening) of the output image. While in Zoom mode, click the Auto Zoom button or set the zoom window by hand with the X Offset, Y Offset, and Scale sliders.

Auto Zoom: A click on this button has the Planar Tracker survey every frame and choose the smallest zoom factor that clears all the transparent edges. That computed zoom window stays centered in frame. On click, Auto Zoom updates the Scale slider together with X/Y Offset. Right-Click Here for Stable Track Spline A right-click on this label opens a spline whose keyframes hold 4 x 4 matrices that in turn stand for the stabilization transforms. It is here chiefly for completeness and for advanced users.

### Options Tab

These controls shape the appearance of the onscreen controls in the viewer.

### The Planar Tracker Options tab

Darken Image Dims the image during Track mode so the controls and tracks read more clearly in the viewer. The Shift+D keyboard shortcut toggles this.

Show Track Markers Switches on or off the dots that mark where the trackers sit at the present time. Show Trails Switches on or off the trails that follow where the trackers go. Trail Length Lets you change how long the tracker trails are. When the pattern crawls along, lengthening them can make the trails easier to read in the viewer. When the pattern races, the tracks may resemble spaghetti in the viewer, and shortening them can help. Inlier/Outlier Colors During tracking, the tracker studies the frame and works out which of the countless tracks belong to the dominant motion and which represent odd, unaccountable motion. By default, the tracks tied to the dominant motion show green (these are the inliers) while those that do not belong show red (the outliers). Only the inlier tracks feed into the computation of the final resulting track.

### Common Controls

Settings Tab The Inspector's Settings tab is mirrored across the other Tracking nodes as well. Full descriptions of these common controls appear in this chapter's closing "The Common Controls" section.

### Surface Tracker [SFt]

### The Surface Tracker node

### Surface Tracker Node Introduction

The Surface Tracker applies textures and effects onto flexible or deformable moving surfaces such as cloth and skin. It makes sure the texture or effect folds and deforms in a way that convincingly tracks the folding and deforming of the surface it is pinned to in the image. As a complex effect, the Surface tracker carries plenty of options and controls aimed at the most realistic composites achievable. Even so, you always work left to right through the buttons in the effect's settings. 1 Click the Bounds button, then click on the screen to mark out the area of the surface where the new texture should go. Have the bounds enclose just one surface at a time and avoid crossing or sitting on object edges. 2 Click the Mesh button to lay down control points along the surface's natural folds and curves inside the bounds.

3 Click the Track button to analyze how the surface moves over time, drawing on the mesh you just laid down. 4 Click the Result button to composite the texture over the moving mesh. Throughout every Surface Tracker tab, the Tracked Range reports the first and last frame numbers of your clip that hold tracking data. Changing the bounds or the mesh layout resets any existing tracking data, and you will have to track it again.

The Surface Tracker at work, laying the logo over the shirt (left) and bending and fitting it believably to the shirt's folds (right). To read more about working with the Surface Tracker, turn to Chapter 168, "Resolve FX Transform."

### Inputs

The Surface Tracker node carries four inputs. Input: The yellow input takes in the media holding the surface you intend to track and composite onto. Overlay: The green input takes in still graphics, video, or a node tree's output. This is the image you want laid over the surface. Occlusion Mask: The pink occlusion mask input serves to mask off regions that need no tracking. Wherever this mask reads white, no tracking happens. For instance, a person passing in front of and hiding portions of the scene can throw off the tracker, so a quick rough mask around that person can instruct the tracker to skip the masked-out portions. Effect Mask: The optional blue effect mask input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask here confines the filter to just the pixels inside the mask. An effects mask is applied to the tool once the tool has been processed.

### Basic Node Setup

Wire the media holding the surface you want to composite onto into the main yellow input. Wire the media holding the graphic or video to be overlaid onto the surface into the green overlay input. If you need them, optionally wire effect or occlusion masks into their matching inputs.

A simple node tree showing a video clip of a guitar player, where the surface tracker lays a small graphic of a bee onto his shirt.

### Inspector

### The Bounds tab in the Surface Tracker controls

### Bounds

Here you are asked to draw an area on the image where the texture should be applied. The ideal pick is a frame in the clip where the surface you want to track sits as near and as square-on to the camera as it can. That frame turns into the effect's default reference frame. Just click on the image to drop several points around the area you mean to define (three points is the minimum), and the effect will link them up into a polygon for you. Place boundary points on the surface meant for tracking, not surrounding it. Dropping points by mistake on object edges or the background instead will introduce tracking errors. The same image can carry several boundaries and several holes, with all boundaries fusing into a single shape before the holes are subtracted out. Several boundaries and holes exist so you can mask off complex surfaces while leaving out regions that should not be tracked. For instance, you might draw a boundary around a person's face yet use several holes to leave out the eyes and mouth, since those shift appearance fast as the subject blinks and speaks, which makes them notoriously hard to track. Several boundaries are meant to operate on one and the same surface; putting several boundaries across different surfaces in the image yields poor results. To track separate surfaces, it is better to use several instances of the Surface Tracker. The boundary serves to analyze a surface's motion, not to rotoscope objects. Foreground objects can be rotoscoped as the Tracking Using a Mask section below explains. Click to Add Points: These are the controls for building boundary areas on the image.

- Boundary: The boundary area presently selected on the image. The drop-down menu lets you switch which boundary or hole is current. When the boundary has problems (such as crossed edges, too few points, and so on), an error message shows up beside the boundary name.
- - Bound: Drops a boundary polygon onto the image. Several boundaries can be defined for one surface, and they merge into a single shape.
- - Hole: Adds a region to keep out of the surface tracking. Handy for pulling overly complex, shifting portions of a surface out of the effect's calculations.
- Delete: Removes whichever boundary or hole is selected in the Boundary field. For now this action cannot be undone, so take care with this button.
- Clear All: Removes every boundary and hole in the effect.

### Mesh

Now that the boundaries are defined, you can build the mesh across the surface to be tracked. Because the first mesh acts as the launch point for tracking, the best results come from placing the mesh when your surface is as square-on and as close to the camera as it gets.

### The Mesh tab in the Surface Tracker controls

You can adjust the mesh by hand, dragging existing points (hold command and drag a region around several points to move them together) or clicking an area to drop new ones. Option-clicking a point takes it out of the mesh. Adding mesh points manually helps when the surface has flexible spots you know will fold the texture but that the mesh placement did not pick up at first. For example, an outstretched arm may carry no active mesh point at the elbow, but a mouse click (plus a little human anatomy) lets you add one there. Another case is seeding points into a low-detail area that you know will gain detail as it turns into view. Dropping mesh points into blank, low-detail regions will not help the results and can even hurt them, so keeping points sparse on smooth areas is preferable. A handy rule of thumb: once more than five points sit inside the boundaries, the mesh is probably good enough for tracking. After tracking, points can neither be added nor removed. A strong mesh signals strong tracking, since the two go together. When few mesh points are detected and the results fail to track tightly, you can prop them up artificially. For instance, confirm the content is plainly visible. Tracking and point detection can break down when the surface is too bright (HDR), too dark, or low in contrast from working in log. As a fix, you can temporarily insert a brightness/contrast node ahead of the Surface Tracker to set contrast by hand, then run the Surface Tracker. Just switch the brightness/contrast node back off once the tracking wraps up. Regenerate Mesh: This button rebuilds the mesh at the current frame and settings, throwing out any manual changes you made.

- Point Locations: These controls set which mode generates the mesh points.
- Automatic: The Surface Tracker finds the strongest details for tracking on its own and drops

mesh points onto those details. For most situations, Automatic delivers the best results.

- Point Number Limit: Sets the ceiling on how many mesh points get placed. Since the count of mesh points governs how the overlay flexes and folds, set it to match how flexible the surface is expected to be. They have no direct bearing on tracking speed.
- Minimum Point Spacing: Sets the smallest allowed gap between mesh points. This keeps mesh points from clustering too closely in highly detailed regions and getting in each other's way.
- Uniform: Lays a regular grid of points within the boundary and leans on internal shape models to warp that grid as tracking proceeds. On a highly detailed surface, this may beat Automatic mode.

Horizontal Spacing: Sets the horizontal gap between neighboring points in the uniform mesh. Vertical Spacing: Sets the vertical gap between neighboring points in the uniform mesh.

The automatic mesh laid over the boundary. The bee now sits composited on the shirt, though it does not look terribly realistic just yet.

### Track

In this part of the effect, the motion of the mesh points is tracked over time. Run the tracking through the clip with the Tracking Direction controls. Once tracking finishes, the effect performs no further analysis, and any extra contrast help from upstream nodes can be dropped after this step. Straightforward cases may track with no user input at all, while trickier ones call on several added controls to refine the track.

### The Track tab in the Surface Tracker controls

Repairing a broken track takes some hands-on tweaking of both the mesh and the tracking data. Whenever tracking is underway, mesh points can be moved either one at a time or with the lasso selection tool (Command - Drag) drawn around the whole mesh or just sections of it. That lasso selection tool can additionally stretch, scale, and rotate the mesh points, which makes it simpler to warp and position the mesh exactly where you want should the automatic tracking falter. Mesh points cannot, however, be added or removed at this stage until you first reset the tracking. Editing mesh points by hand at a frame touches only that frame directly; the neighboring tracking data is left alone. It does, though, shift the neighboring interpolated positions, which makes it useful for tracking from that point forward. For example:

- Tracking holds up until frame 150, where a few points break away from the rest after a lighting change. At frame 150 you can nudge them back into place, and resuming tracking carries them on with their corrected positions.
- Tracking runs until frame 150, then has no data for a handful of frames before picking back up at 160. Editing the points at either frame 150 or 160 makes the in-between frames interpolate with those changes applied.
- Tracking covers up to frame 150 and from frame 160 onward, leaving frames 151-159 interpolated. Adjusting a few points at frame 155 lays down tracking data there, so frames 151-154 now interpolate from the last tracked frame to this one, and frames 156-159 from this one to the next tracked frame.
