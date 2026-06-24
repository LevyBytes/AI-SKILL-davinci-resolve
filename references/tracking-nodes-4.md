# Tracking Nodes (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Go to Start: Pressing this jumps the playhead to whichever frame was tracked first, or to the frame on which the boundary was made. Go To End: Pressing this jumps the playhead to whichever frame was tracked last. Tracking Direction Controls: This cluster runs the tracking analysis in whichever direction you choose. Reading left to right, the buttons go: Track Backwards, then Track Backwards One Frame, followed by Pause Tracking, next Track Forwards Then Reverse, after that Track Forwards One Frame, and finally Track Forwards. With them you can lay down a track over the entire clip or confine the tracking to only one stretch of it. Trimming: This group lets you reshape the track data once it has already been generated.

- Remove Tracking Data Before This Frame: Wipes every bit of tracking data that precedes the current frame.
- Track From Last Known Match: This button ties the tracking data at the current frame back to the most recent frame that still holds tracking data. Should too much motion separate those two moments, you can nudge the points roughly where they belong and attempt the match once more. Say, for instance, the track runs cleanly up to frame 150, but an object crossing the scene throws the track off for six frames (151-157). You can either pause the tracking data before it reaches those frames or delete that span’s data afterward. Then, at frame 158, this button lets you pick the track back up from the last solid result at frame 150.
- Remove Tracking Data At This Frame: Wipes the tracking data sitting on the current frame.
- Remove Tracking Data After This Frame: Wipes every bit of tracking data that follows the current frame.

Tracking Behavior: These settings let you tune how the tracking behaves.

- Motion Range: Governs how widely the search for matches extends. Push this slider up when the surface moves so fast the tracking can’t keep up with it.
- Mesh Rigidity: Governs the mesh’s flexibility. Lower this slider to loosen up the mesh points. You’ll get the cleanest results when the clip is free of noise and warps gently. Raise this slider for a “stiffer” tracked surface that warps less internally.
- Quality: Because the tracker can demand heavy computation, the advice is to run the Faster setting while you tweak the mesh, then switch to Better for the final track after every parameter is dialed in.

Interaction Overlays: These buttons govern whether the mesh overlays appear in the Viewer.

- Show: Keeps the mesh visible the whole time.
- Hide on Drag: Leaves the mesh visible until you drag a point, at which moment it vanishes so you can study the surface beneath while making fine adjustments.
- Hide: Keeps the mesh hidden the whole time.

NOTE: The Surface Tracker generates data on every frame of the source clip. When the source clip’s frame rate differs from the timeline’s, the tracking can look like it stutters or skips frames. You can “bake” the retiming into a clip by right-clicking it on the Edit page and selecting “Render In Place,” which yields a result carrying precisely one frame per timeline frame.

### Result

After the tracking data is finished, the Result section is where you decide what video layer to lay over the moving surface and how to composite it.

### The Result tab in the Surface Tracker controls

Output: Six choices govern what becomes of the tracking data you’ve produced.

- Warp Input 2 Onto 1: Bends the Surface Tracker’s overlay input to match the tracked mesh’s shape and position, then composites it onto the clip.
- Warp Input 2 Onto Blank: Bends the Surface Tracker’s overlay input to match the tracked mesh’s shape and position while carrying through the Alpha channel information, so you can do the real composite over in another node or effect.
- Warp Input 1’s Alpha: Feeds the Surface Tracker’s results into the Effect Mask input.
- Create Mesh Alpha Mask: Builds an Alpha mask that traces the position and shape of the mesh outline. Every input and alpha is disregarded.
- Stabilize-Warp Input 1: Applies an inverse warp toward the Reference Frame (which, once more, should ideally be a frame as close to and as square-on to the camera as you can get). What you get is a still image inside the boundary that nonetheless carries all the lighting shifts and surface-motion detail painted onto it. With the image now stabilized, any of DaVinci Resolve’s existing tools can modify it, sidestepping whatever trouble this region’s motion caused in the original video clip. After modifying it, you warp the result back onto the original footage using a duplicate of the original Surface Tracker node, this time set to Rewarp Stabilized Clip instead.
- Rewarp Stabilized Clip: Takes whatever the Stabilize-Warp Input 1 selection produced and, after it’s been modified, lays that result back over the source footage. This choice is meant to pair with a duplicate of a Surface node running Stabilize-Warp Input 1. It cleanly merges whatever extra modifications were introduced between the two Surface Trackers.

Overlay/Alpha Source: Lets you pick which frames of the overlay or alpha feed into the result.

- First Frame: Handy for locking content from an overlay clip so a single still frame serves as a static texture.
- Reference Frame: Begins at whatever reference frame is currently set (see below) rather than at frame

0. That reference frame is the one on which the mesh overlay first sits in its “un-warped” state, with the positioning controls live.

- Each Frame: Handles the overlay or alpha like a clip, warping every frame one after another. You’ll need this for animated overlays or for re-warping stabilized content.

Contract/Expand: Lets you tack on or strip away pixels at the overlay or alpha edges. Keep in mind that the expanded region isn’t tracked and won’t be stabilized to the content. Softness: Softens the boundary of the Expand/Contract tool so it folds more convincingly into the scene. Motion Blur: This slider adds motion blur to the overlay, sustaining the impression that it was truly shot alongside the scene. Overlay Placement: These controls set the starting transform options for whatever image you mean to lay over the mesh.

- Go To Reference: Sends the playhead to the chosen reference frame.
- Set to Current: Marks the frame currently under the playhead as the reference frame.
- Reference Frame: Reports the frame number where the overlay originally rests, unwarped (the basis from which the warp to all other frames is computed). The positioning controls show up on screen whenever the clip sits on the reference frame. The ideal launch point for rendering onto other frames is a frame where the surface appears largest and least distorted.
- Positioning: Lets you pick the way you adjust the overlay’s position.

Sliders: Selecting this brings up a row of transform sliders (X/Y position, zoom, rotate, and so on) for tweaking the overlay’s starting position. Interactive Canvas: Selecting this brings up draggable frame controls in the Viewer, so you transform the overlay with mouse gestures. The Viewer presents a large grid split into 9 regions; dragging within any one moves, skews, or warps the overlay. Interactive Pins: Reshaping the image in this mode means placing control points by hand, known as pins, in the Timeline Viewer. A single pin grants position control alone. Scaling and rotation call for two points at minimum. Dragging one pin scales or rotates the image about the other pin. With three pins, dragging any of them yields perspective distortions. You can go up to four pins for distinctive corner pinning distortions.

- Reset Position: Returns the on-screen overlay to its default state.

Interaction Overlays: This set of buttons decides whether the mesh overlays are shown in the Viewer.

- Show: Displays the mesh continuously.
- Hide on Drag: Keeps the mesh on screen until you drag a point, whereupon it disappears so you can view the underlying surface while fine-tuning.
- Hide: Suppresses the mesh continuously.

Compositing: Lets you pick the composite blend mode for the overlay operation.

- Composite Type: A drop-down listing every available composite operation.
- Opacity: This slider sets how transparent the overlay is.

For a fuller account of each blend mode, refer to Chapter 50, "Compositing and Transforms in the Timeline."

In the finished surface track, the bee graphic is composited onto his shirt. Screen served as the composite type, with opacity lowered so it blends into the fabric. As the shirt folds and deforms during play, the bee follows along convincingly.

### Tracker [Tra]

### The Tracker node

### Tracker Node Introduction

The Tracker exists to spot and follow one or more pixel patterns as they move from frame to frame in video. You can then feed that tracking data to drive the position or values of other nodes in the composition (the center of a Light Rays node, say). On top of that, trackers can steady an image or impose destabilization on one image derived from the movement of another.

For further detail, turn to "Using the Tracker Node" (Chapter 82) within the DaVinci Resolve Reference Manual, or to Chapter 22 of the Fusion Reference Manual.

### Inputs

Three inputs feed the Tracker: Background: The orange image input takes the primary 2D image you want tracked. Foreground: The optional green foreground takes a 2D image that gets composited atop the background, serving as a corner pin or a match move. Effect Mask: A mask shape is what the blue input expects — one built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input restricts the tracking to particular regions.

### Basic Node Setup

You can drop Tracker nodes inline among other nodes or hang them off as a branch from the clip you’re tracking. Inline, an image is stabilized by wiring it into the orange background input. Once the image is tracked, switching the Tracker’s Operation menu to Match Move stabilizes the connected image.

A Tracker node connected inline to an image for stabilization Used as a branch off the node tree, an image gets tracked and then its tracking data is published so another node elsewhere in the node tree can use it. The Tracker’s output needn’t feed into any other node. With the tracking data published, you can call on it through the Connect To contextual menu.

### A Tracker node branched from the node tree

In match-moving setups, the Tracker can also stand in for a Merge tool. In the example below, the Tracker tracks the image fed to the orange background input and then applies that tracking data to the image fed to the foreground input. The Tracker node carries the very same foreground-over-background merge capabilities.

A Tracker node configured so a match move is applied onto the foreground input

### IntelliTrack AI Point Tracker

By default, the Fusion Tracker node now relies on IntelliTrack, the new DaVinci Neural Engine tracker. Leaning on AI makes tracking simpler and more accurate, particularly when many points are involved. As with other AI tools, IntelliTrack works without fixed rulesets or heuristics; instead it learns from real world examples. That makes it less prone to breaking down in situations such as following a subject through brief occlusions. In most cases it proves more accurate and more dependable than the ordinary point tracker. Every bit of the IntelliTrack analysis runs out of sight, demanding nothing extra from you beyond selecting the IntelliTrack setting, placing the tracking crosshairs over high contrast areas on a single moving subject, and then pressing one of the tracker direction controls.

Placing a Tracking Point while in IntelliTrack mode within the Fusion Tracker NOTE: You can still reach the original Point tracker by selecting the Point button.

### Legacy Point Tracker Onscreen Controls

Even though Fusion now defaults to IntelliTrack, the old Point tracker remains within reach via the Point button should you prefer it. Within the tracker, each pattern carries its own onscreen controls for choosing which pixels in the image get tracked. Those controls appear in the viewers any time you select a tracker in the node tree.

### Tracker onscreen controls

Pattern Rectangle Inside the viewer, the tracker shows a red rectangle drawn with a solid line, known as the pattern rectangle. The pattern used for tracking consists of every pixel sitting inside that rectangle. When needed, you can resize the pattern by dragging the rectangle’s edges.

### A pattern rectangle identifies the area to track

Search Rectangle Any time the mouse passes over the pattern rectangle, a second rectangle outlined with dashes shows up. That dashed outline marks the search area, which sets how far from the current pattern the Tracker hunts in the following frame. The search area ought to always exceed the pattern in size and be big enough to cover the largest frame-to-frame movement in the scene. Quicker-moving objects call for bigger search areas, whereas slower-moving objects manage with smaller ones. A bigger search area lengthens the track, so avoid making it larger than it needs to be. When the selected Tracker carries a custom name, that name shows as a label at the lower right of the search area rectangle.

The search rectangle marks the region scanned from frame to frame to find the pattern.

### Repositioning the Tracker

A small handle sits at the pattern rectangle’s upper-left corner. Dragging that handle moves the pattern. While you do, an enlarged view of the pattern appears beneath your mouse pointer to help you place it precisely. That thumbnail goes away as soon as you let go of the mouse button. The magnification ratio can be tuned in the Inspector’s Options tab.

Dragging the handle magnifies the pattern rectangle for precise placement. TIP: A single composition can hold any number of trackers, and any number of objects may draw on the tracking data. Likewise, one Tracker node can track any number of patterns. Although this chapter documents the Tracker’s assorted controls, we strongly encourage you to study the broader background — see "Using the Tracker Node" (Chapter 82) in the DaVinci Resolve Reference Manual, or alternatively Chapter 22 of the Fusion Reference Manual. There are two ways to use the Tracker: as a node within the Node Editor, or as a modifier bound to a parameter. As a node in the Node Editor, the tracked image arrives from whatever feeds the Tracker node’s input. As a modifier, its controls surface in the Modifiers tab of the node holding the connected control. A Tracker Modifier can follow just one pattern, yet its image source may originate anywhere in the composition. Reach for this approach when you want to track a quick position for an element.

### Inspector

### The Tracker node Trackers tab

### Trackers Tab

The Trackers tab holds the controls for making, placing, and launching tracking operations. Once a track is done, offset controls sharpen how the image lines up after the track. Track Buttons Four buttons kick off tracking, plus a middle button that halts a track already underway. These buttons can drive the current pattern forward or backward in time. Hovering the pointer over any button pops up a tooltip naming it. Here is how the buttons behave:

- Track Reverse: Pressing this sets every active tracker tracking from the end of the render range and working backward in time to the render range’s start.
- Track Reverse From Current Time: Pressing this sets every active tracker tracking from the current frame and working backward in time to the render range’s start.
- Stop Tracking: Pressing this, or hitting ESC, halts the tracking process at once. It’s only live while tracking is happening.
- Track Forward From Current Time: Pressing this sets every active tracker tracking from the current frame and working forward in time to the render range’s end.
- Track Forward: Pressing this sets every active tracker tracking from the first frame of the render range and working forward in time to the render range’s end.

Tracking Behavior Controls Every control here shapes how trackers cope with shifting patterns, how the resulting track path gets defined, and how many keyframes come out of it. Frames Per Path Point This slider sets how frequently the Tracker drops a keyframe onto the path. Its default of 1 lays a keyframe on the tracked path at each and every frame. Raising the figure makes the tracked path less precise. That can be useful when the track keeps returning unsteady results, but ordinarily you should leave this control at its default. TIP: With a field-rendered project, a value of 1 places a keyframe on every field. Because the Tracker is so precise, the field positions then introduce a faint up-and-down jitter. To get cleaner results tracking interlaced footage in Field mode, raise the Frames Per Path Point slider to 2, which yields a single keyframe per frame of your footage.

Adaptive Mode To assist with tricky tracks, Fusion can re-grab the tracked pattern whenever that’s needed. This menu picks the Adaptive tracking method.

- None: At None, the tracker hunts for the original pattern on each frame.
- Every Frame: At Every Frame, the tracker re-grabs the pattern on each frame. This lets

the Tracker absorb slow shifts in profile and lighting across time.

- Best Match: At Best Match, the tracker weighs the originally selected pattern against the pattern grabbed at each frame. Should the difference between the two exceed the threshold set by the Match Tolerance control, the tracker skips re-grabbing the pattern on that frame. This guards against Tracker drift brought on by fleeting artifacts crossing the pattern’s path (a shadow, for example).

Path Center This menu governs how the Tracker acts when a pattern is repositioned. It comes in especially handy once a pattern leaves the frame or alters so drastically that tracking it is no longer possible.

- Pattern Center: With Pattern Center chosen in the menu, the tracked path picks up from the center of the new path. That suits cases where you’re swapping out an existing path completely.
- Track Center (append): With Track Center (append) chosen in the menu, a new pattern’s tracked path is tacked onto the existing one. The fresh path is offset automatically by however much is required. You use this setting to introduce a new tracking pattern once the original drifts out of frame or gets hidden behind other objects. The trick works best when the new pattern sits near the original’s location, sparing you parallax or lens-distortion trouble.

### Tracker List

One Tracker node is able to track several patterns. Every tracker pattern made in the current Tracker node is administered through the Tracker List. Tracker List The Tracker List lists the names of all the trackers you’ve made.

- Each tracker pattern shows in the list by name beside a small checkbox. Clicking a tracker pattern’s name selects it.
- The controls beneath the list then shift to act on that tracker pattern alone. Click an already-selected tracker pattern once to rename it to something more descriptive.
- Clicking the checkbox toggles the tracker’s state.

### Tracker States

- Enabled (black checkbox): A pattern that’s enabled re-tracks on every launch of the track. Other nodes can use its path data, and that data is open to Stabilization and Corner Positioning.
- Suspended (white circle): A Suspended pattern won’t re-track when the track launches. Its data is locked so it can’t change further. The path’s data still serves other nodes and remains open to advanced Tracking modes such as Stabilization and Corner Positioning.
- Disabled (clear): A Disabled pattern lays down no path when tracking launches, and its data reaches neither other nodes nor advanced Tracking operations such as Stabilization and Corner Positioning.

Three tracking patterns, top to bottom: enabled, suspended, and disabled

Add/Delete Tracker These buttons let you add or remove IntelliTrack or Point trackers from your Tracker List. Show This menu chooses which controls appear among the Tracker node controls. It has no bearing on how the tracker runs; it only governs the lower half of the Inspector interface.

- Selected Tracker Details: With Selected Tracker Details picked, the controls on view apply solely to whichever tracker is currently selected. You’ll get the Pattern window plus the Offset sliders.
- All Trackers: With All Trackers picked, the pattern window for every added tracking pattern shows at once beneath the Tracker List.

Left Pattern Display The pattern display holds two image windows set side by side along with a row of status bars. The left window presents the pattern you first selected, while the right one gives a live view of the current pattern as the track moves along. Whenever the onscreen controls shift during tracking, the leftmost window refreshes to reflect the pattern. As the pattern travels, the vertical bars just to the right of the image report how clear and contrasty each image channel is. Whichever channel or channels read clearest are picked for tracking. Those channels carry a gray background in their representative vertical bar. You can stick with the automatic tracking or overrule it and name the channel yourself by clicking the button under the channel you want tracked.

### Tracker pattern display

Ordinarily, the pattern display shows the channel that’s selected. When that channel is blue, what appears is a grayscale rendering of the pattern’s blue channel. The image is shown in color only after you switch on the Full Color button. To change this, click the Show Full Color button under the pattern display rather than the Show Selected Channel button. TIP: Since Fusion automatically chases the highest-contrast channel, you could wind up tracking a channel that’s noisy yet high in contrast. It’s always wise, before you track, to zoom into your footage and inspect the RGB channels one at a time. Right Pattern Display The right-hand pattern display reflects the actual pattern grabbed for tracking. It stays black until you’ve tracked the selected pattern at least once. During tracking the display springs to life, showing the pattern Fusion grabs frame after frame. As the track runs, each frame’s pattern stacks up into a Flipbook that you can replay in the pattern window afterward using the transport controls along the bottom of the window.

As the track proceeds, the vertical bar right beside the pattern conveys how sure Fusion is that the current pattern lines up with the one you first selected. A green bar signals strong confidence that the current pattern matches the original, a yellow bar signals weaker certainty, and a red bar signals severe doubt. Once tracking finishes, the pattern display presents a little Flipbook of that pattern’s track to help you spot frames where the track went wrong. Tracker Sizes Beyond the onscreen controls, every tracker comes with sizing parameters for adjusting the pattern and search box.

- Pattern Width and Height: These controls let you set the selected tracker pattern’s width and height by hand. You can also size the tracker pattern in the viewer, which is the usual approach, though tiny adjustments often go more smoothly with the precision these manual controls offer.
- Search Width and Height: The search area dictates how far Fusion scans the image from frame to frame to re-grab the pattern while tracking. Just as with Pattern Width and Height, you can size the search area in the viewer, but you might prefer to make small adjustments by hand with these controls.
