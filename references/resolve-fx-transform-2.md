# Resolve Fx Transform (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Remove Tracking Data Before This Frame: Wipes every bit of tracking data that sits earlier than the current frame. Track From Last Known Match: Pressing this lines up the tracking data with the current frame and links it back to the most recent frame that still holds tracking data. Where too much movement separates those two moments, you can nudge the points roughly where they belong and attempt the match once more. Say tracking runs cleanly through to frame 150, but an object crossing the scene throws the track off for six frames (151-157). You can halt the tracking data before those frames arrive, or strip out their tracking data afterward. Then, at frame 158, pressing this button picks the track back up from the last solid track at frame 150. Remove Tracking Data At This Frame: Wipes the tracking data sitting on the current frame. Remove Tracking Data After This Frame: Wipes every bit of tracking data that comes later than the current frame.

- Interaction Overlays: These buttons govern whether the mesh overlays appear on the Viewer.

Show: Keeps the mesh visible the whole time. Hide on Drag: Keeps the mesh visible until you drag a point, at which moment it vanishes so you can study the surface beneath while making fine tweaks. Hide: Keeps the mesh out of sight the whole time.

- Tracking Behavior: These options give you a say in how the tracking behaves.

Motion Range: Decides how broad a region is searched for matches. Push this slider up when the surface travels too fast and the tracking can't lock onto it.

Mesh Rigidity: Decides how supple the mesh stays. Pull this slider down to loosen the mesh points. You'll see the best results when the clip is free of noise and warps smoothly. Push this slider up for a “stiffer” tracked surface that warps less internally. Quality: The tracker can really tax your processor; the advice is to stay on the Faster setting while you tweak the mesh, then switch to Better for the finished track after every parameter is dialed in right. Tracking Keyframes: Drives the Surface Tracker from within the standard Keyframe Editor. This option lets you add, remove, and move between the various keyframes. NOTE: The Surface Tracker lays down data on every frame of the source clip. Should the source clip's frame rate differ from the timeline's, tracking can look like it stutters or drops frames. You can “bake” the retiming into a clip by right-clicking it on the Edit page and picking “Render In Place,” which yields a result holding precisely one frame per timeline frame.

### Result

After the tracking data is finished, the Result section is where you decide what video layer to lay over the moving surface and how to composite it.

- Output: Six choices govern what becomes of the tracking data you've produced.

Warp Input 2 Onto 1: Bends the Surface Tracker's second RGB input to match the tracked mesh's shape and position, then composites it onto the clip. Warp Input 2 Onto Blank: Bends the Surface Tracker's second RGB input to the tracked mesh's shape and position and carries the Alpha channel data through, so you can do the real composite in some other node or effect. Warp Input 1's Alpha: Sends the Surface Tracker's results to the first Key input (the second RGB and Key inputs go unused). When that first Key input gets an Alpha channel from another node — a drawn shape, a key, or other Alpha data — it can be warped from the opening frame across the rest. Create Mesh Alpha Mask: Builds an Alpha mask that traces the position and shape of the mesh outline. Every input and alpha is disregarded. Stabilize-Warp Input 1: Runs an inverse warp toward the Reference Frame (which, again, should ideally sit as close to and as square-on to the camera as you can manage). What you get is a still image inside the boundary that carries all the lighting shifts and detail of the surface's movement. You can then work this now-stabilized image with any of DaVinci Resolve's existing tools, sidestepping whatever trouble this region's motion caused in the original video clip. After you've reworked it, you warp the result back onto the original footage with a copy of the original Surface Tracker node, this time set to the Rewarp Stabilized Clip option. Rewarp Stabilized Clip: Composites the result of the Stabilize-Warp Input 1 choice back onto the original video clip once it's been reworked. This option is meant to pair with a copy of a Surface node running Stabilize-Warp Input 1. It blends whatever extra changes were made between the two Surface Trackers seamlessly back into one.

- Overlay/Alpha Source: Lets you pick which frames of the overlay or alpha go into building the result.

First Frame: Handy for locking content from an overlay clip so a single still serves as a fixed texture. Within DaVinci Resolve's External Matte controls you can dial in the offset, and you can equally use that same frame as the texture reference through Reference Frame.

Reference Frame: Begins from whichever reference frame is set right now (described below) rather than from frame 0. That reference frame is the one where the mesh overlay first sits in its “un-warped” state and the positioning controls are live. Each Frame: Handles the overlay or alpha as a clip, warping every frame one after another. You need this for animated overlays or for re-warping stabilized content. Worth noting: over in the Key controls on the Color page, picking an External Matte brings up options that govern how long the external clip lasts.

- Expand/Contract: Lets you push pixels onto or pull them off the overlay or alpha edges. Keep in mind that the expanded region isn't tracked and won't be stabilized along with the content.
- Softness: Softens the edge produced by the Expand/Contract tool so it sits more believably in the scene.
- Motion Blur: This slider adds motion blur to the overlay to keep up the impression that it was

genuinely shot alongside the scene.

- Overlay Placement: These controls let you dial in the starting transform options for the image you intend

to lay over the mesh. Go To Reference: Jumps the playhead to the chosen reference frame. Set to Current: Marks the frame currently under the playhead as the reference frame. Reference Frame: Reports the frame number where the overlay first sits, positioned and unwarped (the spot from which the warp out to every other frame is figured). The positioning controls show on screen whenever the clip rests on the reference frame. The ideal launch point for rendering onto other frames is a frame where the surface looks biggest and least warped. Positioning: Lets you pick how the overlay position is adjusted.

- Sliders: Picking this option brings up a bank of transform sliders (X/Y position, zoom, rotate, and so on) for shaping the overlay's starting position.
- Interactive Canvas: Picking this option brings up draggable frame controls inside the Viewer so you can transform the overlay with the mouse. The Viewers display a big grid split into 9 regions; drag inside any one to move, skew, or warp the overlay.
- Interactive Pins: In this mode you reshape the image by hand-placing control points, known as pins, in the Timeline Viewer. A single pin grants you position control only. Scaling and rotation call for at least two points. Dragging one of the pins scales or rotates the image about the other pin. With three pins down, you can build perspective distortions by dragging any one of them. Up to four pins can be added for one-of-a-kind corner pinning distortions.

Reset Position: Returns the on-screen overlay to its default state.

- Interaction Overlays: These buttons govern whether the mesh overlays appear on the Viewer. Show: Keeps the mesh visible the whole time. Hide on Drag: Keeps the mesh visible until you drag a point, at which moment it vanishes so you can study the surface beneath for fine tweaks. Hide: Keeps the mesh out of sight the whole time.
- Compositing: Lets you choose the composite blend mode for the overlay operation.

For a fuller rundown of each blend mode, refer to Chapter 50, “Compositing and Transforms in the Timeline.” Composite Type: A pull-down menu carrying every available composite operation. Opacity: This slider governs how transparent the overlay is.

### Using the Surface Tracker

The Surface Tracker is a rich, flexible tool you can call on to convincingly isolate a moving surface for all sorts of effects. The examples that follow will help you begin exploring what it can do. Using the Surface Tracker to Composite a Logo onto a Fabric Surface A frequent job for the Surface Tracker is laying a still graphic over a moving surface so the graphic acts believably as that surface bends and warps. Here, we'll stick a simple logo onto the back of a jacket. Step one is marking out the boundary for the region we want analyzed. To get the best outcome, lay the boundary on the surface you mean to track rather than around it, and look for a frame where the surface faces the camera squarely and fills as much of the frame as it can. Step two is laying out the Mesh inside the surface we want warped. Here we'll leave the Point Locations setting on Automatic so the effect drops in the mesh points itself. You ideally want more than five mesh points for a solid track. As luck would have it this surface lacks the detail for a good mesh, so we'll briefly drop a Contrast Pop node ahead of the Surface Tracker to artificially boost its detail.

Drawing the first boundary so the jacket region that will carry the logo is isolated

Dropping the Contrast Pop FX ahead of the Surface Tracker input lets us artificially bump up the detail within the boundary, handing it a stronger surface from which to build the mesh.

Next we'll track the Mesh's motion with the Track Forward button, leaving every other control at its default. Notice the track keeps warping and folding right, even as the subject reclines in his chair. The Tracker studies the Mesh movement across the remainder of the video clip. Now that the surface is properly analyzed, the Contrast Pop node is no longer needed, so we can unplug it here. After that we'll drag the logo (a .png file carrying transparency) out of the Media Pool and into the node tree, where it arrives as a matte. We then place a corrector node after the matte so we can tweak the logo's color/saturation/brightness, and the like. Next we route each node's RGB and Key links onward, passing through the matte and corrector nodes, then on into the Surface Tracker's second RGB and Key inputs. The node tree below illustrates it:

The node tree, laying out how the RGB and Key inputs are wired so the logo composites over the jacket Moving on to the Result section now, we dial in this parameter:

- Output: Warp Input 2 onto 1 This grabs the second RGB and Key input (the logo) and bends it across the original image arriving at RGB input 1.

We'll then press the Go To Reference button to send the clip to its reference frame, and within Positioning we'll use the Interactive - Canvas tool to reframe the logo so it sits on the same plane as the jacket.

Reshaping the logo within Interactive Canvas mode so that it reads as though it sits on the jacket's plane As a final move, we shift the Composite Type from Normal across to Overlay so the logo melds more naturally into the jacket's surface. See how the mesh deforms the logo so it hugs the jacket's curves and folds and follows the man as he reclines in his chair.

The completed Surface Tracker composite; the logo clings to every curve and fold of the jacket and rides along with the man as he repositions himself in the chair.

### Tracking Using a Mask in the Surface Tracker

When something blocks the surface you mean to track, an input key can serve as a tracking mask to keep the obstructing object out of the track. Regions of full alpha (pure white) in the Alpha channel get analyzed for tracking, and the rest is left out. Whatever suits — an effect, a window, or a qualifier — can act as the Alpha channel generator. Take the shot below: the path has the surface mesh on it, yet the woman crossing the path disrupts the mesh tracking. Wire up a node's key output that carries a Magic Mask isolating the walking woman's shape, then invert that mask (making the woman black against white surroundings), and the mesh disregards her legs and feet as they cross it, tracking only points in the white regions (everything that isn't the woman).

Trouble tracking the path's surface; while the woman crosses the mesh, its points latch onto her feet rather than the path, which breaks the tracking along the path's right side.

Wiring up an inverted key from a Magic Mask node of the woman alone makes the tracking pass over the woman crossing the mesh (any black region) and track only points within the white portion of the Alpha channel.

The mesh that results now sits properly on the path's right side and tracks correctly while she walks across it.

At the Surface Tracker's last step, the alpha-bearing overlay is composited over the alpha-bearing original clip, so when you've used a tracking mask, the advice is to unplug it from the Surface Tracker's key input once the tracking has finished.

### Using the Surface Tracker's Stabilize Warp

The Surface Tracker's Stabilize Warp operation lets you lean on the mesh to lock a stretch of video in place, making it simpler to pair with certain other operations. It's a help when the surface you're reworking resists isolation by other tools because of how it moves. Setting up the Surface Tracker to stabilize regions plays out a little differently.

- To begin, set up the Surface Tracker's mesh tracking on whatever surface you intend to work on, just as covered earlier in this chapter.
- When that's done, head into the Result section and pick the Output mode named Stabilize-Warp Input 1, then route that RGB output into a fresh corrector or FX node.
- Doing so singles out just the mesh surface and pins it in place so you can make whatever tweaks you need. This approach contrasts with, say, a window qualifier, which clings to the video and travels with it. With Stabilize Warp, the “window” (really the mesh-defined boundary) is the thing held still, while the video shifts and warps inside it.
- Once your tweaks are done, route the corrector node's RGB output back into a precise copy of the first Surface Tracker node. That copied Surface Tracker node's Output then has to be switched to Rewarp Stabilized Clip. This lays the adjusted mesh back down onto the original video clip. Copying an FX node such as the Surface Tracker outright isn't supported right now. To duplicate the Surface Tracker, pull a still into your Gallery, then right-click it and append the still's node graph back into the same clip, removing the surplus duplicate nodes apart from the Surface Tracker.

Take the clip below, where we'll lean on the Surface Tracker to take a small mole off the woman's chin. Ordinarily we could reach for a Patch Replacer FX to drop a clean patch of nearby skin over the mole. This shot is hard to handle well in the Patch Replacer because the subject tilts her head as she speaks while the camera trucks around her. With movement on every axis, the skin beneath the source patch keeps shifting angle and lighting, which wrecks the effect. The patch replacer does offer tracking, but the mole sits on her chin and her talking flexes the skin around her cheek too, leaving it ill-suited to a plain track. Here, we can put the Surface Tracker's Stabilize Warp function to work to “hold” those facial pixels still beneath the source and target patches, patch them, and then build a Rewarp Stabilized Clip version of the Surface Tracker to drop those fixed pixels back onto the original image.

We'd like this mole gone from the woman's chin. Between camera movement and her chin and cheek flexing as she speaks, the Patch Replacer can't manage it on its own. We'll start by building a mesh over her face and tracking it as laid out above. Cutting holes for the eyes and mouth keeps their quick movement from upsetting the mesh on her face.

We lay the mesh over her face and track it, leaving gaps in the mesh at her eyes and mouth. With the tracking finished, in Result we'll pick the Output mode Stabilize-Warp Input 1. That pins the mesh in place and hands us the resulting output, which we'll route into a Patch Replacer node. Now we can just use the Patch replacer statically to cover the mole with another patch of skin. There's no tracking to do. Since the mesh holds still while the video warps inside it, this region now lines up flawlessly with the angles, lighting shifts, and skin stretching of the area as she talks.

The locked mesh holds steady (over the face) while the video bends within it. That lets us run a static Patch Replacer to swap the mole region for a clean patch on her cheek. No further tracking is called for.

From here, we'll make a precise copy of the Surface Tracker node and set it down after the Patch Replacer. To duplicate the Surface Tracker node, pull a still of the current clip, then right-click that still in the Gallery and pick Append Node Graph to bring it back into our node tree. We want to drop whatever surplus nodes got added and keep only the Surface Tracker copy. Then, inside the copied Surface Tracker, we'll pick “Rewarp Stabilized Clip” from the Result tab's Output mode. After that, hook the original clip up to RGB input 1 and feed the Patch Replacer's output into RGB input 2, as the node graph below shows:

The node tree laying out the proper wiring for Warp Stabilizing the mesh. On the first Surface Tracker node, the Result Output reads “Stabilize-Warp Input 1.” On the second Surface Tracker copy, that Result Output instead reads “Rewarp Stabilized Clip.” The actual mole removal takes place inside the Patch Replacer FX node. Our finished effect now shows the mole gone, and no matter how her jaw moves or where the camera sits, the source patch always lines up flawlessly with the lighting and position changes as time passes. The upshot is a far more seamless, convincing effect.

The shot that results conceals the mole flawlessly (above), regardless of how her face is positioned or how the camera moves.

### Transform

The Transform Resolve FX gives you a good deal more command than you get from the basic transforms found in the Inspector's Sizing or in the Color page Sizing palette. It carries all the usual Position, Tilt, Zoom, and Rotate controls but throws in corner pinning, two flavors of on-screen control, motion blur, plus Edge behavior controls.

### General

- Control Mode: This drop-down offers three ways to drive the transforms. One leans on sliders in the Inspector, while the other two work by manipulating the Viewer's image.

Sliders: Drives the transforms with sliders and checkboxes in the Inspector. This route gives you no Viewer overlays for setting position, scale, or rotation, but it does deliver exact control through numeric values. Interactive-Canvas: Picking this mode shifts the controls out of the Inspector and into the Timeline Viewer. The Viewer's controls appear as a bold white outline with four vertices, one per corner. Drag any part of that white outline to stretch, squeeze, and corner-pin. Dragging the image's center repositions the frame. The red subdivision overlays make shearing effects simple — drag line segments to shift two corners at once. Interactive-Pins: In this mode you reshape the image by hand-placing control points, known as pins, in the Timeline Viewer. A single pin grants you position control only. Scaling and rotation call for at least two points. Dragging one of the pins scales or rotates the image about the other pin. With three pins down, you can build perspective distortions by dragging any one of them. Up to four pins can be added for one-of-a-kind corner pinning distortions. TIP: You can Option-Click a pin to delete it, or hit the Reset Canvas button to clear every pin.

Resolve FX Transform Interactive-Canvas mode (Left) alongside Interactive-Pins mode (Right) Just one Control mode can be live at any given moment. You can't, for example, make tweaks with the sliders and then jump to one of the interactive methods. The sliders reset the instant you choose a different method. You can, though, apply two Transform effects to one clip, adjusting one through Sliders and the other through an interactive method.

### Position Controls

- Canvas Keyframe: Shown only while the Control mode sits on Interactive-Canvas or Interactive-Pins. The Canvas Keyframe carries no control beyond a keyframe button that lets you keyframe the changes you make in the Viewer.
- Reset Canvas: Clears any interactive changes made in the Viewer along with any keyframes born from those changes.

The parameters below appear only while the Control Mode is set to Sliders.

- Position X and Y: Slides the image around within the frame for pan and scan tweaks. X carries the image left or right, while Y carries it up or down.
- Zoom: Lets you enlarge the image or shrink it.
- Rotate: Spins the image about its center.
- Width: Stretches or squeezes the image along one direction only.
- Height: Stretches or squeezes the image along one direction only.
- Pitch: Tips the image toward or away from the camera around an axis that runs through the

center of the image left to right. Positive values shove the image's top away and draw its bottom forward. Negative values draw the top forward and shove the bottom away. The bigger the value, the more extreme the stretch.

- Yaw: Tips the image toward or away from the camera around an axis running through the image's center top to bottom. Positive values draw the image's left forward and shove its right away. Negative values shove the left away and draw the right forward. The bigger the value, the more extreme the stretch.
- Flip Horizontal/Vertical: A pair of checkboxes flip the image across different dimensions. Flip Horizontal: Mirrors the image along the X-axis, left to right. Flip Vertical: Mirrors the clip along the Y-axis, flipping it upside down.

### Image Adjustment

- Crop: Ticking this checkbox reveals the crop tools so you can selectively trim parts of the frame off each side.
- Edge Softness: This control sets how much the Alpha channel is feathered for compositing.
- Edge Rounding: This control rounds off the corners of the Alpha channel for compositing.

### Animation

- Motion Blur: Keyframe the transform so the frame travels fast and you'll get a blurring effect. The Motion Blur slider governs how strong the blur is.

### Advanced Options

- Edge Behavior: This menu decides how the frame's edges behave once the transforms shrink below the Timeline Resolution. Transparent: Whatever lies beyond the transformed image turns transparent, letting the video on the tracks below show through behind it. Reflect: The image is flipped and flopped into a mirrored image that reaches out to the Timeline Resolution frame boundary. Wrap-Around: Copies the image into a video-wall effect that fills the gap out to the Timeline Resolution frame boundary. Replicate: Copies the outermost pixels along the image edge. Those pixels are drawn out from every side to meet the Timeline Resolution boundary.
- Composite Type: Sets the Composite type used to blend several video layers as one.

For more on what each Composite type does, refer to Chapter 50, “Compositing and Transforms in the Timeline.”

### Global Blend

- Blend: Lets you dissolve between the image with no Transform on it and one with the Transform applied in full.

### Video Collage
