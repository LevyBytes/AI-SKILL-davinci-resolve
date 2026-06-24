# Using The Tracker Node (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Best Match operates along similar lines to Every Frame, with one key distinction: it declines to reacquire a pattern whenever the gap between the original and the candidate grows too wide. That behavior guards against situations where momentary shifts in the picture would otherwise confuse the Tracker. To contrast the pair of Adaptive modes, picture a shadow sweeping across the tracker point — under Every Frame, the analysis may latch onto the shadow rather than the intended subject. Best Match, by contrast, recognizes that the departure from the prior frame’s pattern was too severe and refuses to capture a fresh pattern there. As you track, the Adaptive mode affects every pattern that is currently active. To limit it to a subset, switch off the remaining patterns in the list before you begin tracking.

### Dealing with Obscured Patterns

It frequently happens that a perfectly good pattern is briefly hidden (occluded) or kept from tracking— say, while following a car that slips behind a telephone pole. When that occurs, split the render range into two segments: one running up to the point where the pattern vanishes and another picking up once it reappears. Once each segment has been tracked on its own, the Tracker fills in the gap automatically, interpolating from where the first ends to where the second begins. Should you need to revise the resulting motion path to allow for any non-linear movement happening between the two tracked segments, click the track path to bring up a Node toolbar whose controls let you adjust this path’s control points. As one example, you might pick Insert and Modify mode to add points within the untracked span, compensating for nonlinear motion in the pattern being tracked.

The viewer’s Node toolbar holding tools for editing tracker paths

### Dealing with Patterns That Leave the Frame

You have two choices once a tracker exits the frame. Should the pattern come back into view, handle it as you would an obscured pattern. If it never returns, or hand-tracking parts of the movement is unappealing, reach for the Track Center (Append) mode to pick a fresh pattern.

### The Track Center (Append) mode pop-up menu

With Track Center (Append) mode, you choose a fresh pattern that keeps adding keyframes onto the path you already have. The system works out the offset between the prior pattern and the replacement on its own, yielding a single unbroken path. Here is the procedure for the Track Center (Append) mode: 1 Once the pattern can no longer be tracked for whatever reason, halt the analysis and park the playhead on the final frame that tracked cleanly. 2 In the Inspector, open the Path Center pop-up menu and pick Track Center (Append). 3 At this point, drag the Pattern selector onto a fresh pattern that can be tracked going forward. 4 Resume tracking from the present frame.

When you pick a pattern to append onto an existing path, the strongest results come from one that sits near the prior pattern and at the same apparent depth within the frame. As the new pattern moves farther off, it becomes increasingly likely that shifts in perspective and axial rotation will undermine how accurately the track resolves.

### Setting Up Tracker Offsets

Frequently you simply can’t track the very thing you intend to attach an effect to. Suppose the sole pattern that supports an accurate track is a button on an actor’s sleeve, yet the effect calls for the person’s hand to glow. Getting the glow’s effect mask to sit centered on the actor’s hand means you must turn to the Tracker Offset control.

### The Tracker Offset controls in the Inspector

With the X and Y Offset controls you can build either fixed or animated positional offsets measured against the actual pattern center of the Tracker. In the viewer, a dashed line drawn from the pattern center out to the offset location marks where that offset sits. The offset can likewise be tweaked in the viewer by means of the Tracker Offset button. Pressing it lets you move the path around while the Tracker pattern stays put.

Within the viewer’s Node toolbar sits the Tracker Offset tool; here a track of the orange dot is shifted over to sit at the ray gun’s center After an offset is established for a pattern, other positional controls can be wired to the Tracker’s Offset menu through the Connect To > Tracker: Offset Position option found in the control’s contextual menu. The path produced during the track stays anchored to the pattern’s center.

### Stabilizing with the Tracker Node

A Tracker node switched to Match Move in the Operations tab can perform several jobs. The obvious one is transferring the background clip’s motion onto the foreground clip. That said, Match Move also serves to stabilize footage, either stripping motion from the scene entirely or smoothing out movement that is already there. Below are a few typical stabilization scenarios that the Tracker handles in Match Move.

- Footage meant to hold still is marred by vibration or unwanted motion.
- A clip that calls for a fluid camera move is instead afflicted by jarring.

The Tracker Operation tab Match Move set to BG Only for stabilization

### Stabilization Using the Tracker Match Move Mode

When you stabilize motion, all apparent movement is erased from the image. The shift between one frame and the next is computed, then the frame’s contents are transformed so the picture returns to a reference position. That position might be the sequence’s opening or closing frame, or any frame you single out by hand. A lone pattern is enough for stabilization to fix position, whereas correcting rotation or scaling inside the image takes at least two patterns. With the Operation menu on Match Move, selecting BG only in the Merge operation menu stabilizes the background (yellow input) clip. The Operation tab surfaces only those controls that pertain to stabilization. A handful of stabilization controls stay accessible throughout, gathered beneath the Match Move Settings disclosure button. They remain on hand at all times because a tracker always publishes its Steady and Unsteady positions, which keeps them available for other controls to connect to even when the Tracker isn’t set to match moving.

### The Match Move settings

### Merge

Which input connection receives the Tracking data is decided by the Merge menu. To stabilize an image so that all motion is gone, or merely to smooth it, the Merge button has to be on BG Only.

### Edges

Once stabilization is applied, the Edges menu sets whether image borders that slide past the visible frame get cropped, duplicated, or wrapped. Wrapped edges often suit certain match-moving approaches, though they are seldom what you want when stabilizing for any other reason. For fuller detail on these controls, consult Chapter 119 (“Tracking Nodes”) of the DaVinci Resolve Reference Manual, or alternatively Chapter 59 within the Fusion Reference Manual.

### Position/Rotation/Scaling

The Position, Rotation, and Scaling checkboxes let you pick which facets of the motion get corrected.

### Match Move Settings

Among the Match Move settings you’ll find Pivot and Reference. Pivot Type The stabilization’s Pivot Type feeds the math that figures out the rotation axis and the scaling. It defaults to the averaged centers of all the patterns, but you can switch it to a single tracker’s position or to a spot you choose by hand. Reference The Reference controls decide whether the picture is stabilized against the sequence’s first frame, its last frame, or a frame you pick yourself. Wherever the tracked patterns stray from this reference, the image is transformed back toward this ideal frame. A handy rule of thumb: to strip every bit of motion from a clip, put the Merge mode on BG Only, set Pivot Type to Tracker Average or Selected Tracker, and leave the Reference control on Start, End, or Select Time.

### Smoothing Motion

Faced with footage whose camera motion is jittery or jerky, you often want to keep the original camera move while shedding only the erratic part, rather than wiping out movement altogether. That is exactly what the Start & End reference option is built for. Rather than locking onto a reference frame, it simplifies the tracked path. Each pattern’s position is assessed at the path’s beginning and end together with the points in between. What emerges is smooth motion standing in for the previous unsteady move.

The Reference Intermediate Points slider appears once Start & End is chosen, making it possible to smooth the motion To hold onto some of the original camera move’s curvature, raise the value of the Reference Intermediate Points slider that surfaces under the Start & End reference mode. When you track to produce smooth camera motion, confirm that the Start & End reference mode is on and that the Merge mode is set to BG Only. Leaving the Pivot Type control on Tracker Average is the recommended choice.

### Using the Tracker Node for Match Moving

The chapter opened with a basic match moving example, yet this part fills in extra particulars you might not have realized. Some cases where match moving applies are:

- A motionless CG element has to be convincingly dropped into a moving shot.
- A pair of sequences carrying unlike motion have to be combined into one.

Certain clips have to be stabilized first so that material from a different source can be placed into the shot. Once that element or effect is composited in, you take the stabilization back out so the shot reads naturally once more.

### Simple Match Moving

At its core, match moving hands the movement of the tracked clip over to a second clip. You can carry it out in two ways. The first wires other nodes — Transform or Merge, say — to a Tracker’s outputs. The second stabilizes an image as though removing every trace of motion, except that you leave the Merge menu off BG Only and choose FG Over BG, FG Only, or, on rare occasions, BG Over FG instead.

Choose, for the Merge menu, one of BG Only, FG Over BG, or BG Over FG With this Merge menu in play, you attach a foreground image to the input connection of the Tracker node within the Node Editor.

Connect a foreground image to the Tracker’s foreground input Turning on FG Only mode transfers the background’s motion onto the foreground, and the Tracker then outputs nothing but the altered FG image. That output can afterward be merged over the original, so you can keep refining the foreground with other nodes before laying the result over the background clip.

### Corner Positioning Operations

Corner Positioning pins the four corners of a foreground image onto four patterns held by the Tracker. People most often turn to this operation, or technique, when swapping out signs. For the Tracker’s Corner Positioning operation to work, at least four patterns must exist. Should you choose this mode without already having four patterns in the Tracker, it quietly adds more until the count reaches four. Switching the mode on brings up a row of drop-down boxes for assigning which tracker maps to each corner of the rectangle. It does nothing while the Merge control option sits on BG Only.

### Perspective Positioning Operations

Perspective Positioning serves either to strip perspective out of a foreground image or to carry the perspective of one sequence over to another. It comes in handy when you have to paint out a region that perspective has distorted. Pulling the perspective off flattens the images for painting, after which a second tracker restores the perspective. The Tracker’s Perspective Positioning operation demands at least four patterns. Pick this mode when fewer than four patterns are already configured in the Tracker, and it will add the missing ones automatically until four are present. With the mode active, a set of drop-down boxes appears for choosing which tracker corresponds to each corner of the rectangle. It produces no result while the Merge control option is set to BG Only.

### Connecting to Trackers’ Operations

A very frequent use for a tracked pattern is to let its tracked position or path govern where another node’s parameters sit. Take, for instance, tracking an eye so you can color correct it to blue through an effect mask. You begin by tracking the eye, then build a color corrector configured the way you want. You draw a mask shaped like the eye and tie the Tracker’s position to that mask’s Center. Beyond the path (known as Offset Position), every pattern within a tracker exposes four more values that can act as connections for other nodes in the Node Editor.

To bind a node’s position parameters to a tracker, choose the connection type out of the control’s contextual menu (say, via Transform 1: Center > Connect To > Tracker 1 > Offset Position). The tracker automatically publishes five connection types for hooking up to a position parameter on another node.

### Steady Position

Steady Position lets you stabilize footage across X and/or Y so camera shake and other unwanted movement disappear. This connection flips the output of the tracked pattern’s motion. Wire a Center parameter to the Tracker’s Steady Position and, by default, it lands at 0.5/0.5 (the center of the screen) on frame 1. The Reference mode in the Tracker’s Operation tab lets you alter that.

### Steady Angle

Steady Angle mode also stabilizes footage along X and/or Y to clear away camera shake and other unwanted movement. Connect a control — the Angle of a Transform, for example — to the Tracker’s Steady Angle, and by default it begins at 0 degrees on frame 1. That can be reset through the Reference mode in the Tracker’s Operation tab. From that point onward, the motion Steady Angle yields spins counter to the direction of the original. Thus, if the angle reads 15 degrees at frame 10, Steady Angle returns -15 degrees. Steady Angle calls for a minimum of two tracked patterns in the tracker; with only one point on hand, your sole option is (Un)Steady Position.

### Offset Position

Fundamentally, an Offset Position is the path the tracker produces. It’s what you reach for when you need an object to ride along the path. Each individual tracker inside the Tracker node has its own, and it pertains to that one tracker alone. Tie the Center X and Y parameters to the Tracker’s offset position, and the node’s center will trace that tracker’s path precisely. Hooking up to individual trackers is always handy when you want elements to align with object motion in your footage. You might, say, track your actor’s hand and pin a ball to the Tracker’s offset position so the ball mirrors the hand’s exact movement. Or track something that needs rotoscoping and fasten the mask’s center to the Tracker’s offset position.

### Unsteady Position

Once Steady Position has done its work, Unsteady Position brings the original movement back onto an image after you’ve layered in an effect or a new element. The motion Unsteady Position produces amounts to an offset running the same way as the original motion did.

### Steady Size

What the Steady Size connection puts out is the inverse of the tracked pattern’s scale. Tie a parameter — the Size of a Transform, for instance — to the Tracker’s Steady Size and by default it starts at a Size of 1 (that is, the original size) on frame 1. You can revise that through the Reference mode in the Tracker’s Operation tab. The size Steady Size mode generates then works against the size shifts of the original motion. So when the true size at frame 10 comes to 1.15, Steady Size returns 1 - (1.15 - 1) = 0.85. Steady Size needs at least two tracked patterns in the tracker; with a single point only, you’re limited to (Un)Steady Position.

### Using the Outputs of a Tracker

Every tracker pattern you create in the Tracker node publishes the outputs covered above. On top of that, the Tracker node as a whole publishes a Steady Position, Angle, Size, and an Unsteady Position. These node-level outputs are worked out from all the patterns in that tracker, governed by the Match Move Settings controls in the Tracker’s Operation tab. Those Match Move settings fix the reference frame for stabilization and the point that stabilization pivots around Rather than leaning on the Tracker node to carry out the Merge operation, a common alternative is to build a match move by routing these published outputs to several nodes. A tracker tracks a pattern, and the resulting data can then be fed to multiple other nodes by way of the Connect To submenu. As an illustration, here is how to perform a match move through the Connect To menu: 1 Track the background clip with no fewer than two tracking patterns in the tracker. 2 On a separate branch, attach a Transform node to the background clip.

With the background branched off toward a Tracker and a Transform 3 Over the Transform’s Center, right-click and choose Connect to > Tracker1 > Steady Position.

Here the tracker exposes its output so other nodes can hook into it, used in this case to steady the clip 4 Wire the foreground into a corner-positioned node so you can line up the foreground’s corners suitably over the background. 5 Drop one more Transform node into the Node Editor following the Merge.

Following the Merge, a second Transform serves to reintroduce the original motion through Unsteady Poisition 6 Link the new Transform’s Center to the Tracker’s Unsteady Position. The picture returns to its initial state, now carrying the added effect. To get a clearer sense of the mechanism, picture a pattern chosen at frame 1 sitting at position 0.5, 0.5. It stays put on frame 2, so it remains at 0.5, 0.5. By the third frame it has shifted 10 percent of the image’s width rightward, putting it at 0.6, 0.5. With a transform center tied to the Tracker’s Steady Position output, the Transform node’s center reads 0.5, 0.5 across the first two frames since nothing changed. At frame 3 the center slides to 0.4, 0.5 — the mirror image of the horizontal motion the pattern tracked, nudging the picture a touch rightward by 10 percent of the image width to offset the movement and bring the pattern of pixels back to where it originally lay.

### Using the Tracker as a Modifier

One more way to attach a tracker straight to a control is to bring it in as a modifier. Picking the Tracker out of the Modify With contextual menu doesn’t employ a Tracker node at all; it instead places a modifier in the Inspector whose parameters are nearly the same as those in the Tracker node itself. The upside is that whatever object you want riding the tracked path gets wired to the tracker modifier automatically the moment you apply it.

### Applying the tracker as a modifier

Here is how a Tracker modifier diverges from a Tracker node:

- A Tracker modifier is limited to tracking just one pattern.
- You have to assign a source image to the Tracker modifier.

Because a Tracker modifier emits only a single value, it can’t handle elaborate stabilization jobs, yet it offers a tidy, fast way to drop a tracker onto a point you need to follow.

Over any Center Coordinate Control, right-click and pick Modify With > Tracker Position to bring in a Tracker modifier

For an example of applying the Tracker as a modifier, follow these steps: Suppose you had to track an actor’s eyes so an otherworldly, alien glow could be laid over them. 1 Place an ellipse mask node so it covers one of the actor’s eyes. 2 Within the Inspector, right-click the mask’s Center parameter and, from the contextual menu, pick Ellipse1 Center > Modify With > Tracker Position. 3 Open the Modifiers tab in the Inspector and drag the MediaIn1 node you intend to track into the Tracker Source field.

Holding the tracking controls plus a Tracker Source field that names which node does the tracking, the Modifiers tab 4 Press the Track Forward button to set the eye-tracking in motion. 5 Slot a Soft Glow node right after the MediaIn and route the Ellipse Mask into the white Glow Mask input.

A Tracker modifier put on the Ellipse so a green glow forms over an actor’s pupil

To give the Tracker modifier a different source image, type the node’s name or drag the node out of the Node Editor and drop it onto the Tracker Source field control. Where a node (call it node#1) is wired into the node that holds the modifier (call it node#2), the Tracker modifier’s source image becomes node #1 automatically To dig deeper into the Tracking parameters, consult Chapter 119 (“Tracking Nodes”) of the DaVinci Resolve Reference Manual, or alternatively Chapter 59 within the Fusion Reference Manual.

### Match Moving Text Example

Walking you through an entire motion tracking job, this example demonstrates how to build a very basic match-moving effect with the Tracker node — Fusion’s Swiss army knife among trackers.

### Adding a Layer to Match Move

Our sample composition holds a Text1 node generating a “Switzerland” title laid over a drone shot that sweeps over and around a mountain bridge. When the Text1 node is selected, the viewer reveals the onscreen controls for placing the text it produces, and that text already sits at the starting spot we want. Keep in mind that, with the Text node selected, even the portion of the text running offscreen shows up as an outline that tells us where it is.

Text laid over a backdrop, prepared for tracking

What we’re after in this composition is to motion track the background picture so the text travels in step with the scene while the camera soars past.

### Setting Up Motion Tracking

To prepare the motion track, we’ll start by making a standalone Tracker node through a different route than the ones shown earlier. Right-click on any empty part of the Node Editor (ideally where you’d like the new node to land) and pick Add Tool > Tracking > Tracker from the contextual menu, which spawns a fresh Tracker1 node below the MediaIn node (or the Loader node, if you’re on Fusion Studio).

Creating a new node using the Node Editor contextual menu After that, we’ll pull a connection from the MediaIn1 node over to the Tracker1 node so the source clip wires itself into the Tracker1 background input automatically. Doing so branches the MediaIn1 node’s output into the Tracker node, letting the Tracker1 node work on the image apart from the rest of the node tree. It isn’t mandatory, but it’s a neat organizational touch that makes clear the Tracker node is running an analysis referred to by means other than a “physical” connection.

Branching off a Tracker node so it can analyze an image

### A Simple Tracking Workflow

Of all the tracking operations on the Fusion page, the Tracker node is the most basic, and though it can be used in several fashions, one extremely common workflow is to let the Tracker node controls analyze the motion of a subject in the frame whose movement you wish to follow, then put the resulting motion path data to work by “connecting” it to the Center parameter of some other node that can transform the image you want to match move.

### Positioning the Tracker Onscreen Control
