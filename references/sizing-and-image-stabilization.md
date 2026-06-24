# Sizing And Image Stabilization (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Sizing and Image Stabilization

For geometric transforms, DaVinci Resolve carries a capable toolset that leans on advanced algorithms to deliver optical-quality sizing. This section digs into how resolution independence works in DaVinci Resolve, plus how to work the Sizing palette. The chapter also walks through putting the Tracker palette’s Stabilizer mode to use for taming unwanted camera wobble.

### The Five Color Page Sizing Modes

On the Color page, the Sizing Palette can be switched into any of five modes, each handling its own job.

- Edit Sizing: These controls echo the ones living in the Edit page’s Inspector.
- Input Sizing: With these controls you size individual clips in ways that touch their

overall geometry (pan, tilt, zoom, and rotation). They come in handy for clip-by-clip pan and scan tweaks.

- Output Sizing: These controls are virtually the same, save that they touch every clip across the whole timeline at once. Output sizing helps when you want to reformat a whole timeline, say turning an HD timeline into an SD timeline with quick tweaks that crop and pan the resulting framing.
- Node Sizing: Lets you drop pinpoint sizing tweaks anywhere along the node tree. As with Input Sizing, Node Sizing applies to one particular clip. In contrast to Input Sizing, Node Sizing is influenced by operations that break apart color channels (like the splitter/combiner nodes) and confine the image (like qualifiers and windows). You can also stack as many node sizing tweaks onto a clip’s grade as you require.
- Reference Sizing: A group of sizing controls that lets you shift the still while a wipe comparison is underway. With these controls you can nudge the still image to line it up better against the clip you’re wiping it against. The Reference Sizing controls function only while you have a wipe switched on.

### Sizing Order of Processing on the Color Page

Input Sizing tweaks take effect ahead of every bit of image processing happening in the node graph, Node Sizing included, whereas Output Sizing tweaks take effect once the node graph’s image processing is done.

### Sizing Controls

Input, Node, and Output Sizing have a lot of the same controls in common. With the Sizing palette switched to Input Sizing mode, the controls reshape each clip on its own. When you’re merely pushing in on a clip or two, or making one-off pan and scan tweaks to handle a format change, these are the controls to reach for.

### The Sizing palette

- Pan: Slides the clip along the horizontal X axis. Positive figures push the clip rightward; negative ones push it leftward.
- Tilt: Slides the clip along the vertical Y axis. Positive figures push the clip upward; negative ones push it downward.
- Zoom: Tunes the clip’s overall dimensions. The range is from 0.250 (1/4x size) to 4.000 (4x size). Normal size is 1.000.
- Rotate: Positive figures spin the clip clockwise. Negative figures spin it counter-clockwise.
- Width: Stretches the picture broader or thinner. The range is from 0.250 (1/4x width) to

  4.000 (4x width). Normal width is 1.000.

- Height: Stretches the picture so it grows taller or squatter. The range is from 0.250 (1/4x height) to

  4.000 (4x height). Normal height is 1.000.

- Pitch: Spins the image toward or away from the camera around an axis that runs through its

middle, from left to right. Positive values shove the image’s top away and draw its bottom forward. Negative values draw the top forward and shove the bottom away. The bigger the value, the harder the image is stretched.

- Yaw: Spins the image toward or away from the camera around an axis that runs through its middle, from top to bottom. Positive values draw the image’s left side forward and shove its right side away. Negative values shove the left side away and draw the right side forward. The bigger the value, the harder the image is stretched.
- Key Lock: (Node Sizing only) Lets you decide how regions of the image fenced off by one or more windows get transformed. Two options exist:

Off: While off, the transform controls shift the windowed region over to a different part of the frame, in effect cloning the windowed area. On: While on, the transform controls draw other parts of the frame into the windowed regions, in effect masking the windowed area with another slice of the picture.

- Flip Image: Two buttons let you flip the image in different dimensions.

Flip Horizontal control: Mirrors the image along the X axis, left to right. Flip Vertical control: Mirrors the clip along the Y axis, flipping it upside down.

- Lens Correction: (Edit Sizing only) A pair of controls let you fix lens distortion in the picture, or introduce lens distortion of your own (offered only in the Studio version).

Analyze: On its own, examines the frame at the playhead’s spot in the Timeline for edges bent by a wide angle lens. Pressing the Analyze button reshapes how the Distortion slider behaves so it lands a more accurate result, though it carries out no correction itself. Distortion: Drag this slider rightward to lay a warp onto the picture that straightens the bent regions wide angle lenses can introduce. You don’t have to press the Analyze button before reaching for this slider, but pressing it can sharpen the accuracy of the outcome.

### Blanking Controls

Output Sizing mode further carries a group of Blanking controls you can put to use adding custom blanking onto a clip or project. As an example, these controls let you put nonstandard letterboxing or pillarboxing onto an image. Like every other Output Sizing tweak, blanking enters the image processing pipeline last, so none of the color or contrast tweaks you make touch it.

- Top: Adjusts the top letterbox.
- Right: Adjusts the right pillarbox.
- Bottom: Adjusts the bottom letterbox.
- Left: Adjusts the left pillarbox.
- Smooth: A checkbox that switches on edge anti-aliasing for source blanking. It overrides the

Anti-alias Edges drop-down menu sitting in the Image Scaling panel of the Project Settings.

NOTE: You may have to switch anti-aliasing off if black blurring shows up along the edges of the blanking laid onto an image. Blanking presets can also be reached by picking from the Timeline > Output Blanking submenu. Picking one of these entries sets the Blanking parameters of the Sizing palette’s Output Sizing mode automatically. Here’s what you can pick from: 1.33: SD or 4:3 1.66: the European theatrical ratio 1.77: HD or 16:9 1.85: the theatrical flat aspect ratio 2.00: Univisium, an aspect ratio built to serve both theatrical wide-screen alongside HD delivery. 2.35: original anamorphic (scope) theatrical wide-screen 2.39: current 35mm anamorphic (scope) theatrical wide-screen 2.40: a current 35mm anamorphic (scope) theatrical wide-screen ratio (rounded up for Blu‑Ray) Reset: returns the clip to the aspect ratio it began with. Edge anti-aliasing on the blanking is governed by an Anti-Alias Edges setting sitting in the Project Settings’ Image Scaling panel. To read more, refer to Chapter 4, “System and User Preferences.”

### Resetting the Sizing Palette

At any moment you can clear every control inside the Sizing palette by pressing the reset button up in the palette’s top right-hand corner.

### Input and Output Sizing Presets

When you keep reaching for the same Input or Output Sizing settings, you can stash them as presets so they’re easy to call back. As an example, if there’s a batch of input settings you use to resize a clip of a certain format so it fits the current project, you can store it as a preset to pull up whenever you like.

- Preset drop-down menu: Opens up every preset presently stored within the current project library.
- Delete Preset: To remove a preset, pick it out of the drop-down menu, press the trash can button, then press OK.
- Save As New Preset: To stash a preset, dial in whatever settings tweaks you need, then press the plus button. Once the Format Preset dialog shows up, type a name, confirm the settings are right, then press Save in the Format Preset window.
- Update Preset: To revise a preset, load the one you want to revise, make whatever changes you need, then press Update in the Format Preset window.

The Input and Output Sizing modes hold separate presets. You can reach either preset set through the “Override input scaling” and “Override output scaling” drop-down menus sitting in the Image Scaling project setting menu.

### Using Node Sizing for Channel and Paint Effects

Node Sizing lets you lay down separate sizing tweaks on a per-node basis. Every Node Sizing tweak inside a grade stacks up, and any keyframing applied to Node Sizing parameters is held in that node’s Node Format keyframe track within the Keyframe Editor. Two solid examples of Node Sizing are realigning color channels one at a time together with the Splitter/Combiner nodes, or copying windowed regions of an image by shifting them around the frame.

### Example 1

Putting node sizing to work on separate color channels: 1 Choose Color > Nodes > Add Splitter/Combiner Node to drop this node structure into the current grade. 2 Pick whichever of the three Corrector nodes wired between the Splitter and Combiner nodes maps to the color channel you mean to transform. 3 Open the Sizing palette, pick Node Sizing from the mode drop-down, and reach for the Sizing parameters to transform that channel however you need. As an example, with an old video clip whose color components are misaligned, you could pan a misaligned channel left or right to try to tighten up its alignment.

Dropping in the Splitter/Combiner nodes so Node Sizing can act on separate color channels

### Before and after panning the green channel

### Example 2

Putting Node Sizing to work copying a windowed patch of an image to hide a blemish: 1 Make a new node. 2 Open the Window palette, build a Circular window, then shrink it and move it so it wraps around a feature you want gone. 3 Open the Tracking palette and track the window so it follows the feature being removed. 4 Once the track is finished, shift the window over to a neighboring patch of clean detail right beside the feature you want gone. This is the part of the image you’ll copy and lay over the unwanted feature. 5 Now open the Sizing palette, pick Node Sizing from the mode drop-down, tick Key Lock, and reach for the Sizing parameters to slide a copy of the windowed area on top of the unwanted feature.

Before/after where Node Sizing clones a patch of the image so a plant hides the actor and yields a clean background Once you’re finished, running through the clip should reveal that the copied patch of the image keeps tracking the feature you want gone.

### Image Stabilization in the Tracker Palette

The Tracker palette’s Image Stabilization mode lets you smooth out, or even fully steady, unwanted camera motion inside a clip. Its analysis runs in a way that holds onto the motion of separate subjects within the frame, along with the overall heading of any wanted camera move, all while ironing out the unsteadiness.

### Using the Stabilizer

DaVinci Resolve runs an advanced stabilizer that can both warp and translate to cut unwanted shaking in a clip, taking over from the classic stabilization tools that used to be on hand (those tools remain available should you need particular capabilities of the older toolset, and a later section covers them). One press of the Stabilize button analyzes the currently selected clip and stabilizes it automatically using a blend of warping and image translations.

### The default Stabilizer controls

### Stabilizer Parameters and Controls

The default settings give good results in most cases, yet there are ways to tailor stabilization when unusual problems crop up. A drop-down menu offers three different choices that govern how the chosen clip is analyzed and reshaped as it’s stabilized. You have to pick a choice first, ahead of pressing the Stabilize button, because the choice you make alters how the image analysis runs. Switch to another choice and you have to press the Stabilize button once more to reanalyze the clip.

- Perspective: Enables perspective, pan, tilt, zoom, and rotation analysis and stabilization.
- Similarity: Turns on pan, tilt, zoom, and rotation analysis plus stabilization, for cases where

perspective analysis brings about unwanted motion artifacts.

- Translation: Turns on pan and tilt analysis plus stabilization alone, for cases where X and Y

stabilization on its own gives you results you can accept.

- Camera Gyro: When your footage comes off a Blackmagic Cinema Camera fitted with a gyroscope, this

choice turns up in the drop-down menu. You can steady the footage using the movement logged by the internal gyro baked into the clip. How forcefully the chosen clip gets stabilized is set by the remaining controls.

- Bypass Stabilization: This checkbox lets you flip stabilization off and on so you can weigh the stabilized image against the unstabilized one.
- Cropping Ratio: By spelling out how much blanking or zooming you’ll put up with in trade for clearing unwanted motion, this value caps how hard the stabilizer pushes. Set it to 1.0 and no stabilization is applied. Stepping it progressively lower switches on more aggressive stabilization. After changing this value you have to press the Stabilize button once more to re-analyze the clip.
- Smooth: Applies mathematical smoothing to the analyzed data the clip is stabilized with, leaving camera motion in the shot in place while clearing out unwanted jitter. Lower values smooth less, letting more of the original camera move’s character come through, whereas higher values smooth the shot more aggressively. After changing this value you have to press the Stabilize button once more to reanalyze the clip.
- Strength: Acting as a multiplier, this value lets you set how tightly the stabilization track is used to clear motion from a shot under the current analysis. At a value of 1.00, stabilization peaks. Because certain clips can feel more natural with looser stabilization, picking a figure under 100 leaves a slice of the original camera motion visible. Zero (0) shuts stabilization off entirely. As a further tip, you can flip the stabilization around by

picking –1.00 when pasting a stabilization analysis from a different clip to run a match move keyed to the scene’s overall motion, and you can apply a negative value either below or above –1.00 to under- or overcompensate while inverting the stabilization, faking the parallax effect where foreground and background planes travel together yet at differing rates.

- Camera Lock: Switching this checkbox on shuts off Cropping Ratio and Smooth and lets the stabilizer concentrate on wiping out every bit of camera motion in the shot, aiming to produce a locked shot.
- Zoom: With this checkbox switched on, the image is enlarged by enough of a percentage to clear the blanking (black edges) left behind by warping and transforming the image to cancel unwanted camera motion. The lower Cropping Ratio is set, the more DaVinci Resolve has to zoom into an image to clear those blanked edges. Switch this off and the image isn’t zoomed at all, so whatever blanking creeps into the frame goes out alongside the image, on the premise that you’ll have dedicated compositing artists handle clearing that blanking by painting in the missing image data through more elaborate means. You can also keep this checkbox off if you mean to animate the Input Sizing Zoom parameter to push into and out of a stabilized shot, clearing blanking only at the spots it shows up, using no more zoom than each part of the shot demands.

### Using the Classic Stabilizer

The “classic” image stabilizer controls found in DaVinci Resolve version 12.5 and earlier are still on hand; just pick “Classic Stabilizer” from the Tracker palette’s option menu. Classic image stabilization in DaVinci Resolve runs in three steps. First you analyze the clip. Second you settle on the Stabilization settings you’d like to use. Third you press Stabilize to work out the result. As you analyze the clip, you can go with the default Cloud Tracker, which on its own rounds up as many trackable points as it can across the image and figures stabilization from all of them, or you can switch to the Point Tracker, which lets you set one or more individual crosshairs by hand on image features you pick. To learn more about putting the Point Tracker to work for window tracking, turn to Chapter 140, “Motion Tracking Windows.”

### The Classic Stabilizer mode of the Tracker palette

Much as with object tracking, you can pick which facets of motion to stabilize, but that has to happen before you run the initial image analysis.

### Analyze Controls

The Analyze controls sweep through the whole clip on their own, picking out trackable features that can serve to steady the shot. A set of four checkboxes lets you switch on and off the axes you want stabilized. These checkboxes have to be ticked before you run an analysis so the data that gets generated stays limited.

- Pan: Enables horizontal stabilization.
- Tilt: Enables vertical stabilization.
- Zoom: Enables stabilization of size.
- Rotate: Enables stabilization of orientation.

NOTE: After stabilization is done, switching these checkboxes off does nothing to change the outcome. To make changes you first need to tick or untick the relevant checkboxes, then reanalyze the clip. The five direction buttons let you run the stabilization analysis.

- Track One Frame Reverse: Kicks off tracking from the present frame, going back one frame’s worth.
- Track Reverse: Kicks off tracking from the present frame going backward, stopping at the clip’s first frame.
- Pause: Halts tracking (provided you’re quick enough to hit this button before tracking wraps up).
- Track Forward: Kicks off tracking from the present frame going forward, stopping at the clip’s last

frame.

- Track One Frame Forward: Kicks off tracking from the present frame, going ahead one

frame’s worth.

### Interactive Mode Controls

The Interactive controls let you tweak by hand the tracking point cloud DaVinci Resolve builds on its own, so you can try out different approaches to landing better stabilization results in tricky situations.

- Interactive Mode checkbox: Flips the Interactive stabilization mode on and off. Step into Interactive mode and you can reshape by hand the point cloud DaVinci Resolve uses to steady the image. You then run your analysis while still in Interactive mode. Step back out of Interactive mode and your hand-made changes to the point cloud are dropped, with DaVinci Resolve once more using automatically placed point clouds for all stabilization.
- Insert: Lets you drop tracking points onto whatever analyzable features sit inside a bounding box you’ve drawn in the Viewer. Inserted stabilization points get placed on their own.
- Set Point: Lets you use the cursor (via the DaVinci Resolve control panel) to place individual tracking points by hand, one at a time, to track a feature with. If no trackable pixel group sits at the coordinates where you set the cursor, a tracking point lands on the nearest trackable pixel group. You have to set no fewer than two tracking points across separate pixel groups to track rotation, and no fewer than three for tracking zoom.
- Delete: Clears every stabilization point that falls inside a bounding box you’ve drawn in the Viewer.

The steps for using Interactive mode to stabilize match the ones for tracking. To read more, refer to Chapter 140, “Motion Tracking Windows.”

### Stabilization Parameters and Controls

The Stabilization group holds five controls:

### Stabilization selections

- Strong: Lets you set how tightly the stabilization track is used to clear motion out of a shot. At a value of 100, stabilization peaks in a bid to “lock” the shot in place and wipe out every bit of camera motion. This value works as a multiplier. Because certain clips can feel more natural with looser stabilization, picking a figure under 100 leaves a slice of the original camera motion visible. Zero (0) shuts stabilization off entirely. On top of that, you can flip the stabilization around by picking –100, as laid out in the section on running a match move below, and you can apply a negative value either below or above –100 to under- or overcompensate while inverting the stabilization, faking the parallax effect where foreground and background planes travel together yet at differing rates.
- Smooth: Lets you lay mathematical smoothing onto the analyzed data the clip is stabilized with, and is intended for use once the Strong parameter drops below 100, leaving camera motion in the shot while clearing out unwanted wiggle. Lower values smooth less, letting more of the original camera move’s character come through, whereas higher values smooth the shot more aggressively.
- Zoom: With this checkbox switched on, the image is enlarged by enough of a percentage to clear the blanking (black edges) left behind by repositioning the image to cancel unwanted camera motion. The higher Smooth Frames is set, the more DaVinci Resolve has to zoom into an image to clear those blanked edges. Switch this off and the image isn’t zoomed at all, so whatever blanking creeps into the frame goes out alongside the image, on the premise that you’ll have dedicated compositing artists handle clearing that blanking by painting in the missing image data through more elaborate means. You can also keep this checkbox off if you mean to animate the Input Sizing Zoom parameter to push into and out of a stabilized shot, clearing blanking only at the spots it shows up, using no more zoom than each part of the shot demands.
- Tracker Type: A drop-down menu beneath the Tracker graph lets you pick whether to go with the Cloud Tracker or the Point Tracker. The default Cloud Tracker on its own rounds up as many trackable points as it can across the image and figures stabilization from all of them. That’s fast, but it can run into trouble when too many prominent subjects in the frame move along different vectors. The Point Tracker, by contrast, lets you set one or more individual crosshairs by hand on image features you pick. That takes more steps, but it carries the upside of letting you pick exactly which features carry the motion you’re out to stabilize.

To learn more about putting the Point Tracker to work for window tracking, turn to Chapter 140, “Motion Tracking Windows.”

- Stabilize: Once you’ve tracked the clip and dialed in the previous two controls, you need to press Stabilize to work out the combined effect of the Strong, Smooth, and Zoom controls on your clip. Any time you change the Strong, Smooth, or Zoom parameters, you need to press Stabilize to recompute the resulting effect on your clip.

### Classic Stabilization With the Cloud Tracker

Classic Image stabilization in DaVinci Resolve is straightforward, but landing it right means following a particular sequence of steps. To stabilize an image: 1 Open the Tracker palette and pick Stabilizer from the Palette mode drop-down menu. Pick Classic Stabilizer in the option menu. Confirm that the Tracker Type drop-down menu at the lower right of the Tracker palette is set to Cloud Tracker. 2 Switch off any of the Analyze checkboxes (Pan, Tilt, Zoom, Rotate, Perspective 3D) tied to transform axes you don’t want smoothed. 3 Hit the Track Forward button so the clip tracks forward (or pick Track Reverse if you’d sooner begin at the clip’s end and work back).
