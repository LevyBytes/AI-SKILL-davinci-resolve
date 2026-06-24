# Resolve Fx Warp

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Resolve FX Warp

This group of filters distorts the picture along several axes to produce procedural or hand-shaped warps, a number of which can animate on their own. The Warper plugin offers a point-driven, free‑form Warp tool.

### Dent

A distortion that produces assorted styles of round bulging and creasing.

- DentType: Pick among six distinct styles of “dent” distortion. Available are Type 1, Type 2, Type 3, Sine, Cosine, and Black Hole.
- X and Y: These position sliders shift where the warp is centered.
- Size: Use this to set the warp's diameter.
- Strength: Sets both how far and which direction the warp goes; pushing this beneath zero “pulls”

the picture inward toward the effect's middle, whereas pushing it past zero “pushes” the picture out so it bulges following whichever DentType you’ve picked.

- Edge Behavior: This removes blanking produced by negative distortion, filling the black regions through one of several modes you choose; choices are Black (takes no action, keeping the blanking), Reflect, Wrap-Around, and Replicate.

### Lens Distortion (Studio Version Only)

Applies either convex or concave lens distortion so the picture bulges either out or in, mimicking a cheaply built lens. The same filter works correctively too, offsetting footage that shows barrel distortion. On top of that, you can dial the distortion amount separately per color channel, producing a chromatic aberration look by leaning on the curvature of the distortion you’re introducing for greater realism.

- Red, Green, and Blue Distortion: By default these sliders move together because of the Gang checkbox. While ganged, dragging them leftward (negative values) deepens “fisheye” distortion, and dragging them rightward (positive values) yields a reversed “fisheye” that curves the picture inward instead of out. Switching Gang off lets each of the Red, Green, and Blue Distortion sliders hold its own value, adding a more faithful chromatic aberration to the picture.
- Fine Adjustment: Ticking this checkbox narrows the operating range of the distortion sliders considerably, allowing finer control.
- X and Y Position: Use these sliders to relocate where the distortion effect is centered.
- Edge Behavior: The choices in this pop-up clear away blanking that negative

distortion causes, populating black regions through one of several user-chosen modes; the choices are Black (takes no action, keeping the blanking), Reflect, Wrap-Around, and Replicate. TIP: When a clip holds a heavy distortion effect that pushes blanking onto the frame edges, you'll have to resize it with the Zoom control, which sits inside the Node Sizing mode within the Sizing palette. Both Edit and Input sizing confine their zoom to the picture inside the boundary blanking has created.

### Ripples

A distortion that produces assorted styles of ripples.

### Main Controls

These settings determine the ripple style along with the quality of any optional ripple shine you'd like.

- Ripple Shape: Pick from Circular, Square, Horizontal, Vertical, Exponential, Star, and Radial ripples.
- Wave Shape: Pick from Sinusoidal, Triangular, Fresnel In, Fresnel Out, and Natural waves.

A group of Shine parameters lets you lay a simulated shine over the top of these ripples.

- Shine: This checkbox switches the shine on or off.
- Shine Direction: Adds a light shine along the ripple crests. Performs best when shine strength is kept low.
- Vertical Shine Height: Sets how thick the highlights along the ripples appear.
- Shine Size: Sets how long the highlights along the ripples run.
- Shine Strength: Governs the shine's overall look.
- Animate: When ticked, this checkbox exposes a Speed slider that controls the pace at which the

ripple effect auto-animates the phase of whatever ripple effect is currently set, with no keyframes required.

### Ripple Controls

A distinct group of Ripple parameters lets you activate as many as five ripples laid over one another.

- Enable Ripple: A keyframable checkbox that switches an individual ripple on or off.
- X and Y Position: Relocates where each group of ripples is centered.
- Amplitude: Sets the “height” this effect gives each ripple.
- Frequency: Sets the number of ripples being generated.
- Decay: Sets the ripple effect's falloff, with ripples slowly fading out as they

approach the decay point.

- Phase: Sets the ripple effect's phase against the central origin point. When you

want a quick way to animate a ripple, keyframing the Phase parameter reproduces the same result the Animate checkbox above gives you.

### Vortex

Vortex starts off as an S shaped distortion, yet tweaking its parameters yields many kinds of warping effects.

- X and Y position: A pair of sliders shift where the warp is centered.
- Size: Sets the warp's diameter.
- Angle: Sets both the direction and strength of the warp effect; an Angle under 0 spins the

picture leftward, while an Angle above 0 spins the picture rightward.

- Power: Turns the affected region so there's a sharper edge separating the warped part from the rest.
- Swirl: Strengthens the result, winding the picture into a tighter swirl still.
- Edge Behavior: The choices in this pop-up clear away blanking that negative

distortion causes, filling black regions through one of several modes you choose; choices are Black (takes no action, keeping the blanking), Reflect, Wrap-Around, and Replicate.

### Warper (Studio Version Only)

The Warper is a free-form picture warper that relies on points or curves to nudge and stretch parts of a picture as though it were stretched rubber. Although the Warper carries plenty of options and settings, beginning with it is genuinely simple.

### Warp Mode Points

To warp some part of the picture, choose Points for the Warp mode, click somewhere on the picture to drop a warp point, then drag to shove that region of the picture wherever you'd like. Warp points appear gray. Out of the box, warp points act on the whole picture, which stays pinned at its corners. This setup makes warping broad swaths of the picture easy, for instance when you need to warp a picture edge to remove a boom dip.

(Left) the unaltered frame, (Right) that frame warped using one control point To “pin down” regions of the picture you'd rather leave alone, Shift-click to set limiter points (shown red). Pairing warp points with limiter points lets you rapidly build highly precise warps that squish and stretch picture features however you choose.

(Left) the unaltered frame, (Right) that frame warped using control (gray) plus limiter (red) points While working, Option-click any warp or limiter point you no longer want to remove it. For a clean slate, click the Reset Warp control over in the Inspector. Both warp and limiter points accept keyframes through the Positions and Warp Strength parameters.

### Warp Mode Curves

The Curves mode of the Warper builds the warp along a curve or shape rather than around plain points on a grid. That gives you finer control over your selection and yields a more organic‑looking warp on the picture. Curves mode brings extra drawing tools and keyboard shortcuts into the Viewer.

To trace a curve, choose Warp Mode Curves first, then click in the Viewer at the spot the curve should begin, drag the line to where the next point belongs, and click once more. Keep dragging lines and clicking points until the rough line or shape is in place. A curve may stay open or be closed off into a shape.

### Add, Adjust, and Warp modes

As you build a curve, you start in Add mode; this is where you lay down the first curve or shape, but as soon as you close the shape or hit Esc to quit drawing, the Warper by default moves you into Adjust mode, where you reshape the curve without tacking on more points. Next you move to Warp mode to relocate the original curve points elsewhere, which is what actually carries out the warp. You can make as many curves or shapes as you'd like to draw, and whenever one curve crosses another a point is dropped automatically at the crossing. You're free to flip back and forth between Add, Adjust, and Warp modes whenever you need.

### Curve Drawing Commands

Although most curve editing happens naturally by clicking and dragging inside the Viewer, a handful of extra keyboard commands exist too.

- Esc: Stops drawing.
- Enter: Seals the curve by joining its final point back to its first point; alternatively, just click that first point

a second time to close the shape.

- Click: Anywhere across the picture to begin a fresh curve.
- Click: Anywhere along a curve that already exists to drop in one more point.
- Click and Drag: Places a point and pulls its spline handles outward to tune how it curves.
- Shift-Click: Anywhere across the picture to begin a limiter curve. Such a curve outlines a shape

or region where warping is suppressed. The limiter curve shows up red.

- Option-Click: Starts a fresh line in Add mode, no matter whether you happen to be in Adjust or

Warp modes at the time.

- Delete: Removes a selected point or points.

### Drawing curves in the Warper

In this example, the limiter (red) shape encircling the 1 ball keeps it from warping. The straight line on the left pulls the table down and to the left along its edge, which the origin reference (dotted lines) marks as the warp's starting point while the solid line marks where the warp currently sits. The curve spanning the cluster of balls on the right reveals the spline handles belonging to whichever point is selected.

### Editing Splines

Out of the box, your “curves” resemble sharp lines more than smooth flowing curves. You shape the curve's smoothness by tweaking a point's spline handles. A point's spline handle becomes visible when you click straight on the point. Should the handles stay hidden, hold the Command key and pull the handles out from the point. Spline handles come paired by default, so moving one swings the other the opposite way. You can also work a single spline handle on its own by holding Command and clicking the lone spline handle you intend to move.

### Selection

To pick curves and points for editing, click straight on them inside the viewer. Click the shape a second time to wrap it in a bounding box. You may select the entire shape, one point, or drag a selection box around specific points. Hold shift while dragging to make a freeform selection lasso rather than a box. With the box set, scaling the points is done by dragging the bounding box at its edges. Rotate the selection by moving the mouse close to a box edge until the rotate tool shows, then click and drag to spin it. Hold Option and drag to scale the shape about the box's geometric center.

Once a bounding box surrounds a curve, you can both scale and rotate that curve.

### Warper Settings

Warp Mode: Pick the control mode used to apply the warp, either Curves or Points.

### Curves

- Add: While this mode is active, you add points to build a curve or shape to warp around.
- Adjust: While this mode is active, you reshape the curve or shape you’ve built apart

from the warp.

- Warp: While this mode is active, the picture warps around the curves or shapes you’ve

built and refreshes live as you shift them.

- Render a Reference Grid: Tick this box to lay a reference grid over the picture, so you can gauge

exactly how strongly the warp touches each region of the frame.

- Origin Reference: Moving this slider changes how visible the original curve

and point positions are. Drag right to raise their intensity, drag left to make them transparent.

- Position Keyframing: Keyframes the positions of the curve points.
- Warp Keyframing: Keyframes the warps of the curve points.
- Warp Strength: Drag this slider to intensify or weaken the warp's distortion effect.

### Selected Points

- Symmetric: Renders the chosen point (or every point along the chosen curve) symmetric relative to the chosen control point.
- Corner: Turns the chosen point (or every point along the chosen curve) into hard corners.
- Rounded: Turns the chosen point (or every point along the chosen curve) into rounded corners equipped with

spline controls.

- Reset Handle Adjustments (Warp mode): Click this button to return a point's spline curve tweaks

to neutral.

- Reset Warp (Warp mode): Click this button to send the warp back to its original neutral condition.

### Selected Curve

- Show All Handles: This checkbox switches on or off every spline handle for all the points along a curve.
- Open/Close: Click this button to flip between closing a curve (joining the last point to the first point) and opening it (cutting that connection).
- Warper/Limiter: Click this button to swap a curve between a warper and limiter curve. A limiter curve stops warping inside the area it covers.
- Delete: Deletes an entire curve.

### Points

- Render a Reference Grid: Tick this box to lay a reference grid over the picture, so you can gauge exactly how strongly the warp touches each region of the frame.
- Positions: Keyframes the positions of the points in the Viewer.
- Show Origin Locations: Reveals where every point in the Warper originally sat.
- Clear All Points: Wipes out every added point and resets the Warper to neutral.
- Reset Warp: Sends the Warper back to neutral yet keeps every added point at its

origin position.

- Warp Strength: Drag this slider to intensify or weaken the warp's distortion effect.

### On-Screen Controls

- Show: Shows the on-screen controls in the Viewer.
- Auto Hide: Displays the on-screen controls in the Viewer but conceals them only while they're being adjusted,

so you can watch the finished picture as you make changes.

- Hide: Hides the on-screen controls in the Viewer.
- Warp Boundaries (Points Only): This pop-up menu provides three options for showing which

regions of the picture get locked off by limiter points you set on the picture. None: Conceals this information and is the default setting. As Border: Draws a red line at the edge where warping turns locked off. As Mask: Dims the region that limiter points shield from warping.

- Scale Controls: This slider lets you shrink or enlarge the control points or warp vector handles to whatever size suits the work at hand.

### Advanced Options

- Limits: A pop-up menu lets you decide how the picture's edges behave while you're warping it.

Pin at Corners: Holds the picture's four corners fixed, yet lets the sides bow in or out as you warp and lets blanking sneak in. Around the Edges: Holds the entire width and height of all four edges fixed while you warp, blocking blanking. Distant: Holds in place picture areas that sit n pixels off, though the default setting is quite loose. Manual (Free-Floating): Permits warping the whole picture without anchoring any part, enabling extreme warps across an entire picture edge, but obliging you to set at least one limiter point before you add a warp point.

- Elasticity: A pop-up menu lets you pick one of three ways to interpolate how the picture flexes around a Warp point: Fabric, Rubber (the default), and Jelly. Fabric yields the “most pointy” warps, whereas Jelly yields the gentlest curved warps. Rubber lands midway between those two extremes..

### Fabric

### Rubber

### Jelly

- Edge Behavior: A pop-up menu removes any blanking that warping at the picture edge produces by filling black regions through one of several modes you choose; choices are Black (takes no action, keeping the blanking), Reflect, Wrap-Around, and Replicate.
- Warp Detail: A pop-up menu lets you pick among three ways of computing the warping effect you’re building: Faster, Default, and Better. Every option is a clear trade-off between picture smoothness and performance.
- Effect Follows: Lets you decide whether the points cling to the scaled content (Input and Edit Sizing) or to the original frame in the timeline (Timeline Frame).
- Auto Advance to Adjust Mode: With this box ticked, the app switches automatically to Adjust mode for editing right after you add a point or curve.

### Waviness

- Waviness Type: Lets you pick Vertical or Horizontal waviness.
- Scale: Lets you set the size of the waves.
- Strength: Lets you set the amplitude.
- Phase: Lets you “move” the wave and makes a handy parameter to keyframe when you’re animating

this effect by hand.

- Animate: A checkbox that exposes a Speed slider controlling the pace at which the Waviness effect

auto-animates with no need for keyframes.
