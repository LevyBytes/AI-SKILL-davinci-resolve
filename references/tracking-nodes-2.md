# Tracking Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Even with the camera solved, it remains clueless about where the ground plane or the scene’s center sits. Out of the box, the solver drops the camera into Fusion’s 3D virtual environment such that, on frame one, it rests at the origin (0, 0, 0) and faces straight down the Z-axis. From here you may export this raw scene and tell the Camera Tracker nothing further, or you may pin down the ground plane and origin so that the 3D scene is easier to work in once you get started. What the 3D Scene Transform controls give you is a way to line up the actual ground plane in the footage with the virtual ground plane shown in the 3D viewer. Tweaking the 3D Scene Transform leaves the camera solve alone — all it does is shift the 3D scene so it best mirrors where the live-action camera was. NOTE: Should you export the scene and afterward alter the 3D Scene Transform, remember to click Update Previous Export by hand if you want those changes reflected in the exported nodes. Aligned/Unaligned This menu either locks or frees the origin and ground plane settings. Under Unaligned, you set the ground plane and origin by hand or by picking locators in the viewer. While unaligned, a 3D Transform control inside the 3D viewer can be dragged manually to nudge the origin. After the ground plane and origin are aligned, flipping the menu to Aligned locks the section. Set from Selection Whenever the section is unaligned, buttons reading Set from Selection appear beneath the Origin, Orientation, and Scale sections. Pressing one of these grabs the locators you have selected in the viewer and orients the ground plane or origin from that selection. As an example, here is how to fix the ground plane: 1 Once solved, switch the 3D Scene Transform menu to Unaligned. 2 Hunt for a frame where the ground plane appears biggest and sharpest. 3 Inside the viewer, drag a selection rectangle over every ground plane locator. 4 Holding Shift, drag once more to extend the selection. 5 Within the Orientation section, confirm the Selection Is menu lines up correctly with how the chosen locators are oriented. 6 Press the Set from Selection button that sits below the Orientation parameters. 7 Return the 3D Scene Transform menu to Aligned. For the cleanest ground plane result, aim to grab as many ground-belonging points as you can, spread far apart.

TIP: As you pick points for the ground plane, viewing the Camera Tracker node in side-by-side 2D and 3D layouts pays off. Grabbing ground tracks can go more smoothly when you choose tracks across several frames in the 2D viewer instead of trying to box-select locators over in the 3D viewer.

Pinning down the origin lets you drop 3D objects into the scene with greater accuracy. The procedure mirrors the one above, except a single locator is all it takes to establish the origin. For that locator, pick one whose solve error is very low. Ground Plane Options Through these controls you tune the scene’s ground plane — a step that matters a great deal for getting the composite to read correctly.

### Color

Determines what color the ground plane takes on.

### Size

Governs the maximum size the ground plane may reach.

Subdivision Level Reports the polygon count making up the ground plane.

### Wireframe

Chooses whether the ground plane renders as a wireframe or a solid surface in the 3D view.

### Line Thickness

Controls the on-screen thickness of the lines drawn in the viewer.

### Offset

The ground plane’s center normally rests at the origin (0, 0, 0). You can apply this to nudge the ground plane higher or lower along the Y-axis.

Export Options Offers a checkbox list governing which items become nodes once you press the Export button. Your options here cover the following: Camera; Point Cloud; Ground Plane; Renderer; Lens Distortion; plus the camera’s Enable Image Plane. By way of the Animation menu you decide whether the camera or the point cloud gets animated. Pick the camera and the point cloud stays frozen in place while the camera is keyframed onto the live-action shot. Pick the point cloud and the reverse holds: the camera stays fixed while the whole point cloud is keyframed onto the live-action shot. Previous Export Clicking the Update Previous Export button refreshes the earlier exported nodes named here with whatever new data has been produced — that covers the camera path and attributes, the point cloud, and the renderer.

### Options

Through the Options tab you tailor the Camera Tracker’s onscreen controls, helping you make the most of whatever scene material is in front of you.

### The Camera Tracker Options tab

Trail Length Lays trail lines for the tracks over the viewer. How many frames ahead of and behind the current one are drawn comes down to this length value. Location Size This control resizes the point cloud locators within the 3D viewer. Each of Track Colors, Locator Colors, and Export Colors carries options to set its color to any of these: User Assigned, Solve Error, Take From Image, and White.

### Track Colors Locator Colors Export Colors

These cover the onscreen tracks shown in the 2D viewer, the point cloud locators shown in the 3D viewer, and the hues given to the locators exported inside the Point Cloud node.

Darken Image Lowers the image brightness in the viewers so the overlaid tracks stand out better, taking effect in both the 2D and the 3D viewers. Visibility Switches on or off which overlays appear in the 2D and 3D viewers. The available toggles are Tracker Markers and Trails; Reprojected Locators and Tracker Patterns; and a pair of Tooltips entries, one labeled “Tooltips in the 2D viewer” and the other “Tooltips in the 3D viewer.”

Colors Sets the color of the overlays.

- Selection Color: Controls the color of selected tracks/locators.
- Preview New Tracks Color: Sets the hue of the points that show in the viewer once the

Preview AutoTrack Locations option is switched on.

- Solve Error Gradient: Out of the box, a green-yellow-red gradient tints tracks and locators

so their solve error reads at a glance. You can adjust this gradient however you like. Reporting Sends an assortment of parameters and information out to the Console.

### Understanding Camera Tracking

On big productions, camera tracking — or 3D match moving — usually goes to specialists who know how to track and solve troublesome shots. Almost never can you tap a button or two and get a flawless result. Real success demands a grasp of the entire workflow and of what truly matters for landing a solid solved track. With hundreds of thousands of unknown variables to resolve, the Camera Tracker faces a tough job. The whole thing hinges on gathering quality tracking data that persists in the shot over a long stretch. Tracks that are false or poor will throw off the outcome. The pages here walk through clearing out false tracks along with other methods for reaching a good solve.

### Workflow

Arriving at a good solve is an iterative cycle: you Track, then Solve, apply your Refine Filters and Solve once more, run a Cleanup tracks pass followed by Solve, do a Cleanup from point cloud and Solve yet again, and Repeat the whole loop. At the start you will have many tracks, not all of them sound, so you have to filter and prune the unwanted ones until you are left with the strongest set. Once each round of cleanup finishes, hitting Solve should drive the solve error steadily downward. That figure has to drop below 1.0 to serve full HD content well, and it must go lower still at higher resolutions. Refining the tracks usually — though not always — yields a better solve. False Tracks A range of conditions spawn false tracks: objects moving through a shot, or glints and highlights bouncing off a car. Another flavor is the parallax error, where two objects lie at differing depths and their intersection ends up tracked. Such moiré effects can make a track drift. Spotting these False tracks and weeding them out is the single most important move in solving. Track Lengths A solid collection of long tracks is vital — the longer a track runs, the stronger the solve. Use the Bi‑Directional tracking option on the Tracker tab to push the start of tracks further back in time. The longer a track lasts and the more tracks that share overlapping time within a shot, the steadier and more precise the solve.

Seed Frames The solve relies on two seed frames. Its algorithm singles out a pair of frames separated as widely as possible in time while still holding the same tracks. This is precisely why long tracks weigh so heavily on which seed frames get chosen. Those two Seed frames act as the reference frames and ought to come from differing angles of one scene. The solve treats them as a master jumping-off point for fitting the remaining tracks across the sequence. The Solve tab offers an Auto Detect Seed Frames option, on by default and generally the smart pick — though letting it auto-detect can stretch the solve out. While you refine the Trackers and re-solve, switch the checkbox off and type the prior solve’s seed frames into the Seed 1 and Seed 2 sliders. You will find those seed frames listed in the Solve Summary near the top of the Inspector after the first solve. Refine Filters Once that first solve runs, every Tracker gains extra generated data — namely solve errors and tracking errors. Lean on the refine filters to thin out unwanted tracks, say by setting a minimum tracker length of eight frames. As you move each filter’s value, the Solve dialog reports how many tracks fall under that filter. Then Solve again. Onscreen Culling On the Options tab, dial the track to 20, which shows every track over the footage carrying a +-20 frame trail. As you scrub or play through, bad tracks become visible, can be selected right on screen, and removed with the Delete key. Catching tracks that go wrong this way calls for a practiced eye. Then Solve again. You may also open the exported scene in a 3D perspective viewer, where the point cloud appears. Orbit and pan the point cloud, then select and delete any points that fail to line up with the image and the scene space. Then Solve again. Keep cycling until the solve error sits below 1.0 ahead of exporting.

### Common Controls

Settings Tab You will find this same Inspector Settings tab repeated across the other Tracking nodes too. The shared controls get a full write-up just ahead, in the “The Common Controls” section.

### Planar Tracker Node [PTRA]

### The Planar Tracker node

The Planar Tracker node exists to tackle a match-moving challenge that turns up all the time in post-production. Picture live-action footage holding a flat surface — a license plate or a road sign, say — where you need fresh numbers on the plate or a different city’s name on the sign. The wrinkle is usually that the camera is on the move during the shot, so the plate or sign keeps shifting perspective. Simply compositing a new license plate over the old one will not do unless you account for those perspective distortions. One slow route would be to reach for a Corner Pin node and hand-keyframe all four corners. The Planar Tracker takes that keyframing off your hands, following a flat surface’s perspective distortions through time. It then lays that tracking data, along with the very same perspective distortions, onto a separate foreground. For deeper guidance on the Planar Tracker, turn to Chapter 83, "Planar Tracking," in the DaVinci Resolve Reference Manual, or to Chapter 23 in the Fusion Reference Manual.

TIP: Working with a Planar Tracker also means recognizing when to quit and retreat to Fusion’s Tracker node or to keyframing things by hand. Certain shots just will not track, or the track that comes out is plagued by too much jitter or drift. As a time-saver in the artist’s kit the Planar Tracker earns its place, yet even though it handles most shots, it is not a 100% solution.

### What the Planar Tracker Saves

The Planar Tracker writes the finished final track into the composition on disk, but it leaves out the temporary tracking information — things like the individual point trackers (unlike the Camera Tracker, which does keep the individual point trackers). A few things follow from that:

- Save and reload a comp that holds a Planar Tracker node and the point trackers vanish from the viewer.
- You may be unable to pick tracking back up once a comp with a Planar Tracker node has been saved and reopened — and that holds for auto saves as well, which is why finishing all your planar tracking in a single sitting is wise.
- Composition file sizes stay sensible (there are cases where a Planar Tracker would otherwise spit out hundreds of megabytes of temporary tracking data).
- Comps save and load more quickly and feel more responsive.

### Inputs

Four inputs sit on the Planar Tracker: Background: This orange background image input takes a 2D image carrying the flat surface you mean to track. Corner Pin 1: The green corner pin 1 input takes a 2D image to be laid on top of the background; there can be several such inputs, named Corner Pin 1, Corner Pin 2, and so on. Occlusion Mask: The white occlusion mask input serves to block out regions that need no tracking — wherever this mask reads white, nothing is tracked. For instance, someone walking in front of and hiding parts of the pattern could throw the tracker off, so a quick, rough rotomask drawn around that person tells the tracker to skip the masked-out parts. Effect Mask: The blue input takes a mask shape made from polylines, basic primitive shapes, paint strokes, or bitmaps out of other tools. Wire a mask into it and the Planar Tracker’s output is confined to particular areas.

### Basic Node Setup

A bare-bones Planar Tracker arrangement needs only two nodes: a MediaIn feeds the background input, while the Planar Tracker sits on its own branch apart from the rest of the node tree. After tracking wraps up, you should spin off a Planar Transform node to put the planar tracking data to work.

A Planar Tracker may be set apart on a branch all its own within the node tree.

### A Typical Planar Tracker Workflow

Here is how the Planar Tracker workflow unfolds, step by step: 1 Remove lens distortion: The heavier the lens distortion in your footage, the more the finished track will slip and wobble. 2 Connect footage: Wire a Loader or MediaIn node holding a flat surface into the orange background input, then bring the Planar Tracker node up in a viewer. 3 Select a reference frame: Jump to a frame where the flat surface you want to track is clear of occlusion and press the Set button to make it the reference frame. 4 Choose the pattern: With the onscreen controls showing in the viewer, trace a polygon around the flat surface you intend to track — this is the so-called “pattern.” Usually a rectangle does the job, though any closed polygon will work. The pixels inside that boundary become the pattern hunted for across the remaining frames. Keep in mind the pattern has to be drawn on the reference frame, and do not mix it up with the region you corner pin (which is always four-cornered and gets specified separately in Corner Pin mode). 5 Adjust render range: Over in the Keyframes Editor, set the render range so it lines up with the span of frames where the flat surface shows.

6 Adjust track options: The settings you will tweak most often are Tracker, Motion Type, and Track Channel. 7 Mask out occluders: Should moving objects partly hide the flat surface, consider wiring an occlusion mask into the Planar Tracker. With the Hybrid tracker, handing it a mask to cope with occluding objects is strongly advised; with the Point tracker, you are better off attempting the track without a mask first. 8 Track: Hit the Go button to jump back to the reference frame, press the Track To End button, and let the track finish. Hit Go once more to land on the reference frame again, press the Track To Start button, and again wait for completion. Bear in mind that, unlike in a Camera Tracker, the tracks shown in the viewer can be neither selected nor deleted. 9 Check track quality: Look the track over to judge its accuracy — does it cling to the surface? Flipping to Steady mode can make this easier to see. 10 Use the track: From here you will most often build a Planar Transform node out of the Inspector and use it to push the tracked perspective distortion onto masked images. When the image you are feeding the tracking data into is a full-frame, unmasked clip, the Steady, Corner Pin, and Stabilize operation modes of the Planar Tracker are available to you.

### Inspector

### The Planar Tracker Controls tab

### Controls tab

On the Controls tab you find the settings that decide how the Planar Tracker is put to use, fix the reference frame, and kick off the track. Operation Mode The Operation Mode menu picks what the Planar Tracker node is for. The Planar Tracker offers four operating modes:

- Track: Serves to single out a flat surface and follow how it moves through time. From there you can build a Planar Transform node that draws on this data to match move some other clip in a number of ways.
- Steady: Having studied a flat surface, this mode strips every bit of motion and distortion off it, usually as a setup for a paint or roto task, before the clip is later “unsteadied” to bring its motion back.
- Corner Pin: Once a flat surface has been analyzed, this mode works out a matching perspective distortion, applies it to a foreground image you feed into the Planar Tracker node’s foreground input, and lays that on top of the tracked footage.
- Stabilize: After examining a flat surface, this mode lets you smooth out a clip’s translation, rotation, and scale across time — handy for ridding a clip of unwanted shake while keeping the deliberate camera motion intact.

Those final three modes — Steady, Corner Pin, and Stabilize — all feed on the tracking data that Track mode generates. NOTE: You cannot run the operations together. Corner Pin and Stabilize, for one, cannot happen simultaneously, and you cannot track while corner pinning is active. Reference Time The Reference Time sets the frame on which the pattern gets outlined; it is likewise the moment from which tracking starts. You cannot revise the reference frame after it is set without wiping out every bit of existing tracking information, so scrub the footage you mean to track and decide with care. Picking the reference frame thoughtfully is what gives you the best-quality track. To set one, park the playhead on a fitting frame and click the Set button to lock it in. Pattern Polygon You mark which slice of the image to track by drawing a polygon on the reference frame. Normally the moment you drop in a Planar Tracker node you are set to begin drawing a polygon in the viewer, so it is best to get on with it straight away. As you decide where to draw, make sure the region you pick belongs to a genuinely flat surface in the shot. In a pinch a roughly flat region will serve, but the less flat the surface, the worse the track turns out. The general rule is that more pixels in the pattern mean a better track. Put concretely, the reference frame pattern ought to be:

- As large as possible.
- As much in frame as possible.
- As unoccluded as possible by any moving foreground objects.
- Captured as big as it gets (for instance, with a road sign coming toward camera, favor a later frame

where it measures 400 x 200 pixels over one where it is only 80 x 40 pixels).

- Fairly free of distortion (for example, as the camera circles a flat stop sign, lean toward a

frame in which the sign sits face-on and parallel to the camera, not one where it is sharply angled). Too few pixels in the pattern, or too few trackable features, can breed trouble in the track — jitter, wobble, and slippage among them. Stepping down to a simpler motion type sometimes eases that. Once your pattern is drawn, a group of Pattern parameters lets you transform and invert the polygon you made, if the need arises.

### Track Mode

What separates Track mode from the Operation menu’s other three choices is that it alone sets the planar tracking in motion; the rest simply consume the tracking data Track mode has produced. Tracker You get two trackers to choose between:

- Point: Follows points across successive frames. Under the hood, this tracker is not really chasing points as such but small patterns, much as Fusion’s Tracker node does. The point tracker can build its own internal occlusion mask on its own, spotting and discarding outlier tracks that fall outside the dominant motion. In the viewer, tracks show up green or red according to whether the point tracker judges them part of the dominant motion or casts them out. If you like, you can hand it an external occlusion mask to steer the Point tracker further.
- Hybrid Point/Area: Puts an Area tracker to work on every pixel in the pattern. The Area tracker, unlike the Point tracker, cannot on its own throw out portions of the pattern that stray from the dominant motion, so you have to feed it an occlusion mask yourself. For the sake of performance the Hybrid tracker quietly runs the Point tracker first, which explains why the point tracks remain visible in the viewer. No single tracker wins outright; each brings its own trade-offs:

Artist Effort (occlusion masks): The Point tracker spins up its own internal occlusion mask without your help, whereas the Hybrid tracker has you putting in extra time crafting occlusion masks by hand. Accuracy: Because it tracks every pixel in the pattern instead of a handful of standout feature points, the Hybrid tracker comes out more accurate and less given to wobble, jitter, and drift. Speed: The Hybrid tracker runs slower than the Point tracker. As a rule, do a fast first pass on the shot with the Point tracker and study the outcome; if it does not hold up, then reach for the Hybrid tracker. Motion Type Sets how the Planar Tracker models, internally, the distortion of the flat surface under track. There are five distortion models:

- Translation.
- Translation, Rotation (rigid motions).
- Translation, Rotation, Scale (squares stay squares, with scale held uniform across x and y).
- Affine - covers translation, rotation, scale, and skew (turns squares into parallelograms).
- Perspective (turns squares into arbitrary quadrilaterals).

Every model in turn is broader than the last and folds in all the earlier ones as special cases. Unsure which to use? Go with Perspective for your first track attempt. Where the footage carries perspective distortions and you pin the Planar Tracker to a simpler motion type, the track can wind up sliding and wobbling. On stubborn shots, stepping down to a simpler motion model can occasionally help — say when a lot of track points bunch up on one edge of the tracked region, or when you are tracking a small region thin on trackable pixels.

Output Governs what the Planar Tracker node sends out while it is running in the Track operation mode.

- Background: Passes the input image through untouched.
- Background - Preprocessed: Ahead of tracking, the Planar Tracker runs assorted preprocessing on the

input image (converting it to luma, for one), and seeing that can help you settle on which track channel to use.

- Mask: Emits the pattern as a black-and-white mask.
- Mask Over Background: Emits the pattern mask composited over the background.

Track Channel Picks which image channel of the background image gets tracked. Aim for a channel rich in contrast and trackable features but light on noise. The permitted values are red, green, blue, and luminance. Tracking Controls This is the set of controls that drives the Tracker. Keep in mind that, during tracking, you should only advance to a new frame when the current one is already tracked or is the reference frame.
