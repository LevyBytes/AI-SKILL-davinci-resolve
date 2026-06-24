# Animating With Motion Paths (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Animating with Motion Paths

By traveling along a chosen spline shape, layers and 3D objects produce motion path animations. This chapter covers building, editing, and applying motion paths within Fusion.

### Animating Using Motion Paths

Splines (polylines) — paint strokes and masks among them — become motion paths once a path modifier is attached to them. It’s the path modifier that lays out the movement turning everyday spline shapes into motion paths. You add the path modifier one of two ways: explicitly, by applying it onto the Center X/Y or Pivot X/Y parameters; or implicitly, when you keyframe the Center or the Pivot parameters. Whichever route you take, the spline path shows up in the viewers and is then tuned visually there. Across every motion path, the viewer’s coordinate control stands for where an object or effect sits — for example, the center of a Transform or Rays node as it slides along the path. Onscreen, coordinate controls take the form of vertical and horizontal positioning arrows or an X.

A Center Offset onscreen control belonging to an object’s Transform node The nodes listed below carry parameters you can animate with path modifiers to shift an image about the composition. They include, though aren’t restricted to:

- Transform: Animate Center X/Y to drift an image about.
- DVE: Animate Center X/Y to drift an image about.
- Merge: Animate Center X/Y to drift the connected Foreground image about.
- Paint: Animate Stroke Controls > Center X/Y to drift a stroke about.
- Camera 3D node: Translation X/Y/Z
- Shape 3D node: Translation X/Y/Z

These nodes below carry parameters you can animate with paths to swing the direction of a visual effect. They include, though aren’t restricted to:

- Directional Blur: Animate Center X/Y to redirect the blur.
- Hot Spot: Animate Primary Center X/Y to drift the hot spot about.
- Rays: Animate Center X/Y to vary the angle the rays shoot out at.
- Polygon/BSpline/Ellipse/Rectangle/Triangle mask: Animate Center X/Y to

shift the mask.

- Corner Positioner: Animate Top Left/Top Right/Bottom Left/Bottom Right X/Y to relocate

each corner of the corner-pinned effect.

- Vortex: Animate Center X/Y to relocate the heart of the warping effect.

NOTE: A one-dimensional value — blur strength or merge angle, say — can’t take a motion path. You can, though, lean on the Spline Editor to shape values like these visually.

### Types of Motion Paths

Motion paths come in three varieties: Polyline paths, XY paths, and 3D motion paths meant for 3D scenes.

- Applying the path modifier produces a Polyline path. Two splines describe it: one carrying the path’s shape in the viewer, and a Displacement spline carrying the object’s speed along the path, shown over in the Spline Editor. As the default kind of path modifier, the Polyline path is what most of this chapter’s material presumes you’re using.
- For its part, the XY path modifier draws on one spline for the point’s X position and a second for the Y. Fuller coverage of the XY path modifier comes later in this chapter.
- 3D motion paths apply solely to positional controls inside 3D scenes.

### Polyline Path

Of all the motion paths, Polyline paths are the simplest to handle. The spline shape in the viewer governs the path’s shape, while one Displacement curve in the Spline Editor governs the acceleration along it. The plainest route to a Polyline motion path is keyframing a Transform node’s Center X/Y parameter in the Inspector. To build a Polyline motion path from the Center X/Y parameter in the Inspector: 1 Park the playhead on the frame where the motion starts. 2 In the Inspector, click the gray Keyframe button just right of the Center X and Y parameters. That step puts the path modifier into the Inspector’s Modifiers tab. 3 Dial in the Center X and Y for the opening keyframe’s position. 4 Park the playhead on the frame where the motion ought to shift or halt. 5 In the Inspector, alter the Center X and Y parameters, which sets a keyframe for the new spot automatically. 6 Back in the viewer, reshape and refine the motion path by choosing a control point and reaching for any of the spline controls on the viewer toolbar. 7 Open the Spline Editor and tweak the Displacement spline to steer the object’s speed along the path. Keyframing Center X/Y isn’t the sole way to attach the path modifier. Another approach attaches it to the Center X/Y parameter, done either in the Inspector or through the viewer’s coordinate control.

To attach a Polyline path to the Center X/Y parameter: 1 Park the playhead on the frame where the motion starts. 2 Place the object’s (or effect’s) center coordinate control at its opening position. 3 Now right-click that onscreen center coordinate control in the viewer — or, alternatively, the Center X and Y parameter over in the Inspector — and pick Path from the control’s contextual menu. Applying a path modifier to the center of a Transform node A path modifier now sits on the object, so even without a keyframe you can drag it to start laying a motion path in the viewer. 4 Advance the playhead to a fresh frame. 5 Drag the onscreen coordinate control, or change the Offset or Center values in the Inspector. The motion path gains a keyframe automatically, and a polyline is traced from the first keyframe to the new one.

A pair of keyframes set a few frames apart reveal a motion path that marks the animation’s direction.

6 Where the center control sits gets interpolated between the two keyframes. Keep tacking on points by advancing the playhead and resetting the object’s position until the whole motion path you’re after exists. With motion paths, closing the spline path isn’t required; leaving it open is fine. 7 When you’re done, switch the polyline into Insert and Modify mode by picking a point on the path and hitting Command-I, or by clicking the Insert and Modify button on the toolbar. Don’t fret over the motion path’s overall shape just yet. You can refine that shape later by dropping more points onto the polyline and reworking the ones already there. One last alternative for making a motion path is to draw the spline shape first and then wire a path modifier to it. With any of Fusion’s spline tools, draw the path’s shape and then hook the path modifier up to that published spline. After those two are joined together, keyframe the Displace parameter to carry an image along the path. This route comes in handy when you want a paint stroke or mask shape serving as a motion path. To press a mask shape or paint stroke into service as a path: 1 Draw a polygon mask, or a paint stroke, shaped like the path you mean to use. Closing the mask shape isn’t necessary.

An open Polyline mask shape 2 Once the shape is drawn, click the Insert and Modify button on the viewer toolbar so the mask shape stays an open spline. 3 From here you can grab any control point along the spline and press Shift-S to smooth it or Shift-L to make it linear. Every mask polyline ships with animation switched on, which usually isn’t what you want for a motion path. That keyframe animation has to go when you’re working from a mask shape. 4 Down at the bottom of the Inspector, right-click the “Right-click here for shape animation” label and pick Remove Polygon1Polyline.

Right-clicking at the bottom of the Inspector to strip auto-keyframing off a mask shape 5 Right-click at the bottom of the Inspector once more and choose Publish so other nodes can reach this spline shape. (With a paint stroke, first make the Stroke editable by clicking the Make Editable button in the Stroke Controls.) Doing this lights up the Modifiers tab with the Published Polyline modifier. That published spline can then dictate the shape of splines in other nodes. 6 Wire a Transform node to the image meant to trail the path. 7 Over in the Inspector, right-click the Center X/Y parameter and pick Path. That sends a path modifier into the Modifiers tab. 8 Still in the Inspector, open the Modifiers tab and double-click Path1’s heading to expose its parameters. A keyframe already sits on the Displacement parameter by default. Get rid of it so you can place your own. 9 Click the red keyframe button just right of the Displacement parameter to clear it.

Clear the automatic displacement keyframe before you lay down your own keyframes. 10 Down at the bottom of the Modifiers tab, right-click “Right-click here for shape animation” and pick Connect To > Polygon1Polyline. 11 For a fast look at where your object ended up, drag the Displacement slider to and fro. 12 The Size parameter is there if you need to scale the whole path. The Displacement slider is built to be keyframed so the object animates along the path.

### Path Modifier

Functionally, the method you pick to spawn the path modifier changes nothing. Each of the approaches above is merely a different road to the same destination. No matter how you choose to add the path modifier, the Modifiers tab holds the controls for the path.

Making a path puts controls into the Inspector’s Modifiers tab. Those path modifier controls in the Inspector let you reposition, resize, and rotate the entire path shape. Over in the Spline Editor, the Displacement parameter appears as a spline that fixes the object’s position along the path, while the Heading Offset handles orientation along it.

### Controlling Speed and Orientation along a Path

Each Polyline path carries its own Displacement spline over in the Spline Editor. That Displacement spline stands for acceleration — that is, where the animated object falls along its path — expressed as a value somewhere between 0.0 and 1.0.

A Poly path’s Displacement curve captures how an object accelerates on a path. Lower values land nearer the path’s start, and higher values creep ever nearer its finish.

Picture, for example, a bumblebee bobbing up and down while crossing the screen. Getting the bee to speed up through its rises and dips yet ease off at the peaks and troughs is a job for the Displacement curve.

### A curvy path defined by a spline shape

How fast the bee travels isn’t set by the curved shape of the path. At any given spot along the path, the bee’s speed comes down to the Displacement parameter. You can govern that Displacement parameter from the Modifiers tab or from the Spline Editor. To wield the Displacement parameter for an object’s speed on a path, proceed like so. 1 Park the playhead at the animation’s opening. 2 In the Modifiers tab, drag the Displacement parameter to 0.0. That plants the object at the path’s start. 3 Click the Keyframe button just right of the Displacement parameter. 4 Move the playhead deeper into the comp and drag the Displacement parameter until the object rests where you want it for the current frame. 5 Keep updating the playhead and the Displacement parameters at the comp’s key moments until you arrive at the path’s end. With the first pass of animation laid down, the Displacement curve in the Spline Editor lets you refine the timing. To refine an object’s timing along a path: 1 Open the Spline Editor and switch on the Displacement spline in the header. 2 Slide control points horizontally toward each other to quicken the pace between them while keeping the object’s spot on the path. A longer, flatter curve linking two points signals a gentler rate of change. 3 Drag a control point up or down to move its location on the path while holding the timing between two points steady.

### A Displacement curve in the Spline Editor

TIP: Keep Option pressed as you click the spline path in the viewer and a fresh point joins the spline path without any Displacement keyframe landing in the Spline Editor. That way you reshape the path while leaving the speed along it untouched.

### Using a Path Modifier to Adjust Orientation

Orienting the object along the path is the Heading parameter’s job. Say you want our animated bee to auto-orient according to which way the path runs — you’d tie the bee’s angle to the Heading parameter. To link the Heading with an object’s angle: 1 Within a Transform node, right-click that object’s angle parameter. 2 Pick Connect To > Path > Heading. Within our sample comp, the bee now auto-orients as the path dips and climbs.

The Transform’s angle parameter wired to the path modifier’s Heading parameter

### XY Path

In contrast to a Polyline path, the XY path modifier leans on separate Spline Editor splines, one figuring the X-axis position and the other the Y-axis. To animate a coordinate control through an XY path modifier:

- Right-click either the viewer’s center coordinate control or, in the Inspector, the Center X/ Y parameter, then pick Modify With > XY Path off the contextual menu.

Adding the XY Path modifier to a Center parameter in the Inspector On the surface, XY paths behave much like Polyline paths. With the modifier in place, build the path by parking the playhead and dragging the onscreen control to where you want it. Park the playhead once more and shift the onscreen control to its next spot. What sets them apart is that the control points exist purely for spatial placement. No Displacement parameter is on hand to manage temporal placement.

XY path modifier controls in the Modifiers tab of the Inspector

Rather than dragging in the viewer, you can build a motion path from the controls in the Modifiers tab, with the object’s own Inspector controls acting as an offset against that motion path. Use the XYZ parameters to place the object, the Center X/Y parameters to place the whole path, the Size and Angle to scale and turn the path, and the Heading Offset control to tune orientation.

Animating a snippet of text by means of an XY path modifier Working with XY Paths inside the Spline Editor For the XY path, the Spline Editor shows the X and Y channel splines. Any change you make to the path in the viewer or the Inspector turns up as keyframes on those splines in the Spline Editor. In contrast to a Polyline path, XY paths carry no Displacement curve. The object’s speed along the path is bound to the path itself and can’t be pried apart from the timing of the keyframes that shape it. TIP: XY path and Poly path can be flipped into one another from the contextual menu. That lets you switch methods to fit the moment without redoing your animation. The strength of the XY path modifier is that you can pin an exact XY coordinate to a precise time for tighter control.

XY Path shows X and Y curves in the Spline Editor yet carries no Displacement control.

### Switching Default Paths

To make XY path the default path type, go in Fusion Studio to Fusion > Preferences > Globals, or, within DaVinci Resolve, to Fusion > Fusion Settings. Inside the Settings window, pick the Defaults category and set the Point With drop-down menu to XY Path. From then on, keyframing the Center X/Y parameter or picking Animate from CenterX/Y’s contextual menu calls up an XY path modifier rather than a Polyline path.

### Types of Control Points

In the viewer, an XY path’s control points are tied to the control points on the X and Y curve over in the Spline Editor. Both hold the same count of points, and dropping a control point in one place drops it in the other too. A Polyline path doesn’t work that way. Polyline paths are built from locked and unlocked points. What makes a point locked is the manner in which it was added to the Polyline. A locked point on the motion path in the viewer has a matching point on the Displacement spline in the Spline Editor; an unlocked point has no such counterpart. Each behaves differently, as laid out below.

### Locked Points

On a motion path, locked points play the role keyframes do. You make them by shifting the playhead and then moving the animated control. Such a point declares that the animated control has to sit at a particular position on a particular frame. In the viewer, locked points show up as larger hollow squares. Every locked key has a matching point on the path’s Displacement curve in the Spline Editor.

### Locked points on a path in the viewer

Removing a locked point from the motion path reshapes the motion’s overall timing.

To alter a path’s duration by way of locked points: 1 Wire an object to a Transform node. 2 Set the spot where you want the motion path to begin.

A graphic set on the right-hand side of the frame 3 Park the playhead at frame 0. 4 Pick the Transform node and, in the Inspector, click the Keyframe button just right of the Center X/Y parameter. That attaches the path modifier and lays down the path’s first locked point. 5 Park the playhead at frame 45. 6 Drag the object’s center to the lower middle of the screen.

Advancing the playhead and relocating the bee drops a second locked point That establishes the second locked point.

7 Open the Spline Editor and bring up Path1’s Displacement spline.

### The path’s Displacement spline with locked keyframes

With a value of 0.0, the control sits at the path’s opening. Once the Displacement spline reads 1.0, the control sits at the path’s close. 8 Grab the keyframe at frame 45 in the Displacement spline and drag it over to frame 50. The motion path now runs 50 frames, and its shape hasn’t budged. Try pulling this point’s value from 1.0 down to 0.75 and it won’t take, because as the animation’s final point its value in the Displacement spline has to stay 1.0. 9 Park the playhead on frame 100 and drag the bee center up to the screen’s top-left corner.

Shifting locked points alters a motion path’s duration while leaving its shape alone That drops one more locked point and gives the path a new endpoint.

### Unlocked Points

Unlocked points come about when you tack extra points onto the motion path while in Insert and Modify modes. Such points serve to reshape the motion path overall without directly touching the motion’s timing. In other words, you can pile on as many unlocked points as you like to rework a motion path, and none of it disturbs the timing of that path’s animation. That makes refining a motion path spatially far easier once you’ve nailed the animation’s timing temporally. Unlocked points carry no counterpart on the path’s Displacement spline. In the viewer they show as smaller, solid square points. To put unlocked points onto a motion path, proceed like so: 1 Pick a motion path spline by tapping Tab to cycle through controls until the path is the one selected. 2 To drop points along a path, click the Insert and Modify button on the toolbar. 3 Click the path and lay down two fresh points: one midway between the first and second points, the other midway between the second and third. Those two newly added points don’t appear on the motion path’s Displacement spline. They’re unlocked points, there to shape the motion but disconnected from the path’s timing.

Unlocked points placed on the motion path don’t show on the Displacement spline Unlocked points can go onto the Displacement spline too. Extra unlocked points in the Spline Editor can be put to work making the object’s motion hold for a moment.

To stall motion along a motion path with an unlocked point: Grab a locked point on the Displacement spline, then keep Command pressed as you drag that point horizontally to a different frame. The point is duplicated as an unlocked point at the new frame.

Build a hold in the motion by duplicating locked points Grasping how locked and unlocked points differ hands you separate command over the spatial and temporal sides of motion paths.

### Locking and Unlocking Points

Flip an unlocked point into a locked one, or the reverse, by selecting the point(s) and picking the Lock Point option off the contextual menu.

### Tips for Manipulating Motion Paths

Several different approaches let you build and edit motion paths within the viewer.

### Compound Motion Paths Using Path Centers

Each motion path owns a set center marked by a crosshair. Path centers let paths hook onto other controls and act hierarchically, which is a remarkably potent way to build intricate motion out of fairly simple paths. A handy illustration of the technique would be animating a bee’s flight path. A bee will often trace a steady figure eight even as it presses forward. The straightforward way to pull that off uses two paths in tandem. In the example that follows, the bee would tie to a first path inside a Transform node — a figure eight of the bee moving on the spot. The center of that first path would then tie, through a second Transform node, to another path describing the bee’s forward travel across the scene. To make a compound motion path: 1 Build a figure-eight motion path either by keyframing an object or by drawing a polyline mask. (With a polygon mask, you’ll have to strip off the auto-keyframing and publish the mask before the next step.) 2 Add a polyline mask and trace a smooth curve spline that runs across the screen. 3 At the bottom of the Inspector, right-click the “Right-click here for shape animation” label and pick Remove Polygon Polyline to clear the auto-animation behavior. 4 Right-click the label once more and pick Publish. 5 Pick the object’s Transform node and click the Modifiers tab.

6 Right-click over the Path1 Center X/Y parameter and pick Path. 7 Down at the bottom of Path2, pick Connect To > Polygon: Polyline. 8 Keyframe the Path2 Displacement so the object travels along the second path.

### Two motion paths working together

### Copying and Pasting Motion Paths

An entire motion path can be copied to the clipboard and then dropped onto a different node, path, or composition. Ways to copy and paste motion paths:

- To copy a motion path: Over in the Inspector’s Modifiers tab, right-click the path’s control header and pick Copy from the contextual menu.
- To cut a motion path away from a node: Inside the Inspector, bring up the contextual menu on the path’s control header and pick Cut.
- To paste the copied path over a different path: In the Inspector, right-click the path’s control header and pick Paste from the contextual menu.

As you paste a path, the clipboard’s version writes over the old motion path.

### Removing Motion Paths

Several routes lead to removing or deleting a path, each one running through a right-click contextual menu. Taking a path modifier away leaves the object and the spline shape intact; it merely strips the animation off the object and the modifier out of the Inspector’s Modifiers tab. To remove a path, do one of these:

- In the Modifiers tab, right-click over the Path1 header and pick Delete from the menu.
- In the Inspector, right-click over the Center XY parameter and pick Remove Path1 from the menu.
- In the viewer, on the center coordinate control belonging to the object you’re animating, right-click and pick Remove Path1 from the submenu under the NameOfObject; Center submenu.

### Removing an entire motion path at once

### Recording Motion Paths
