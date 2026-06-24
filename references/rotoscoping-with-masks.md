# Rotoscoping With Masks (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Rotoscoping with Masks

This chapter explains using masks to rotoscope, which ranks among compositing's most frequent jobs.

### Introduction to Masks and Polylines

A polyline is the spline that comes into play any time a control gets animated along a motion path or a node's effect is masked by a drawn shape. The Paint and Grid Warp nodes rely on them as well. At a more elementary level, polylines steer the animation within the Spline Editor. Because these splines turn up in nearly every context, they carry enormous flexibility, packing a sizable set of controls, modes, and options. The pages here give a broad look at polylines and how they work, with targeted notes on putting them to use for masks.

### Mask Nodes

A mask node produces an image whose job is to define transparency within some other image. Where most image-creation nodes in Fusion build a full RGBA image, mask nodes instead build a single channel image. The Polygon mask tool, the one you'll reach for most, sits in the toolbar. To dig deeper into these mask tools, consult Chapter 108, "Mask Nodes" (DaVinci Resolve Reference Manual), or, within the Fusion Reference Manual, Chapter 48.

The nodes on offer within the Effects Library's Mask bin Polygon Mask The masks Polygon produces are Bézier shapes the user draws. It is the polyline type you'll meet most often and the everyday backbone of rotoscoping. The moment you drop a Polygon mask tool into the Node Editor, it is set to animate automatically.

### B-Spline Masks

B-Spline masks are shapes the user builds from polylines drawn with the B-Splines. While linear, they act exactly like polyline shapes, but once smoothed the control points sway the shape via tension and weight. The upshot is generally cleaner shapes that need fewer control points. The moment you drop a B-Spline mask tool into the Node Editor, it is set to animate automatically.

### Bitmap Masks

With the Bitmap mask, images coming from the Node Editor can serve as masks for nodes and effects. A Bitmap mask can draw its values from any of the image's color, alpha, hue, saturation, luminance, or auxiliary coverage channels. You can also build the mask out of the Object or Material ID channels found inside certain 3D-rendered image formats.

### Mask Paint

Mask Paint lets a mask be painted with Fusion's built-in vector paint nodes.

### Wand Mask

A Wand mask gives you a crosshair you can place over the image. Whatever color the pixel beneath the crosshair holds is used to build a mask, and every neighboring pixel of a comparable color joins the mask too. A mask of this sort works perfectly for confining color adjustments.

### Ellipse, Rectangle, and Triangle Masks

These count as primitive shape masks. To dig deeper into these mask tools, consult Chapter 108, "Mask Nodes" (DaVinci Resolve Reference Manual), or, within the Fusion Reference Manual, Chapter 48.

### Ranges Mask

Much like the Bitmap mask, the Ranges mask lets images from the Node Editor stand in as masks for nodes and effects. Rather than pulling a plain luminance-based mask from one channel, Ranges supports spline-based picking of low, mid, and high ranges, much as the Color Corrector node does.

### Polyline Types

Polylines can be drawn with either the B-Spline or the Bézier spline type. Your pick hinges on the shape you're after and how at ease you are with each spline style.

### Bézier Polylines

A Bézier polyline is a shape built from control points and handles. Multiple points working together define a polyline's overall form.

Bézier control point with direction handles extended to create a smooth curve

Every control point carries a pair of handles that pin down the precise form of the polyline segments running through that control point. Changing the angle or the length of the direction handles dictates whether that polyline segment turns out smooth or linear.

Bézier control point with direction handles aligned to create a linear segment Anyone who has worked in programs like Adobe Photoshop or Illustrator will already grasp most of the fundamentals behind editing Bézier polylines.

### B-Spline Polylines

A B-Spline polyline resembles a Bézier spline, yet these polylines really shine at producing smooth shapes. Rather than relying on a control point plus direction handles for smoothness, the B-Spline polyline lays out points without direction handles to set a bounding box around the shape. How smooth the polyline reads comes down to the tension of the point, which you can dial in as needed.

### B-Splines excel at creating smooth curves

### Converting Polylines from One Type to Another

Building a shape with a B-Spline or polyline doesn't lock you into the controls you began with. Whenever you need to, you can turn any shape from B-Spline into Bézier, or Bézier into B-Spline. To swap a shape across the Polyline and B-Spline controls: right-click the shape inside the viewer, then off the spline's contextual menu pick either Convert Bézier Spline to B-Spline or Convert B-Spline to Bézier (whichever one fits is the only choice shown).

Converting between the two types keeps the original shape intact. As a rule the new polyline ends up with roughly double the control points of the original shape so the shape changes as little as possible. Animation carries over as well, though this conversion won't always come out flawless. Reviewing the animation once you've converted spline types is a smart move.

### How to Use Masks with Other Nodes

As a rule, a node applies its effect across every pixel of an image. Many nodes, though, carry mask inputs you can use to confine the effect that node has on the image.

A Blur node with a Polygon node masking its effect A mask is a single-channel image that pins down which regions of an image you intend to affect. You can build masks from primitive shapes (think circles and rectangles), from intricate polyline shapes handy for rotoscoping, or by pulling channels out of another image.

### A Polygon node's mask seen in the viewer

Any single mask node can produce just one shape. Mask nodes, however, are meant to be chained one after another, so you can blend several masks of various kinds into intricate shapes. As an example, a pair of masks can be subtracted from a third mask to punch holes through the resulting mask channel. Fusion gives you a handful of ways to put masks to work on various tasks. You can hang Mask nodes after other nodes where you want to introduce transparency, or you can wire Mask nodes straight into the dedicated inputs of other nodes to confine or generate various kinds of effects.

### Attaching Masks to an Image for Rotoscoping

You'll usually wire up a Mask node, such as a Polygon node, in one of two ways so that it tacks an alpha channel onto an image for compositing further down the node tree.

### Using a MatteControl Node

The chief node for blending masks in assorted ways and dropping the outcome into an image stream is the MatteControl node. You hang the MatteControl node downstream of whichever node outputs the image you mean to rotoscope. Typically you'll wire a Polygon or B-Spline node into the Garbage Matte input of the MatteControl node so the spline serves as an alpha channel.

Feeding a Polygon node to a MatteControl node to perform rotoscoping With this arrangement, you load the MatteControl node into the viewer and pick the Polygon node to reveal its controls, letting you draw and reshape a spline while watching the image you're rotoscoping. Which portion of the image turns transparent is set through the MatteControl node's Garbage Matte > Invert checkbox. Connecting a Mask to a MediaIn or Loader Node's Input Slightly simpler, this route hinges on your awareness that one node can be viewed while a different node is being tweaked, even with that other node disconnected. Add a free-standing Mask node like a Polygon or B-Spline node, then, with the Mask node selected, drop a MediaIn or Loader node straight into the viewer, and you can draw a spline to rotoscope the image. Once rotoscoping is done, simply route the output of the Polygon node into the input of the Loader node, and that node gains an alpha channel automatically.

Rotoscoping a MediaIn node using a disconnected Polygon node

Wiring a Polygon node into a MediaIn node so its spline serves as the alpha channel

TIP: Wire a Mask node into a MediaIn or Loader node's effect input with no shapes drawn yet, and that mask puts out full transparency, so right away the image the MediaIn or Loader node outputs goes entirely blank. That's the reason that, to rotoscope by wiring a mask into the input of a MediaIn or Loader node, you must first work inside a disconnected Mask node. The instant your drawn shape is closed, connect that Mask node into the MediaIn or Loader's input, and you're good to go.

### Combining Multiple Masks

Masks are built to be stacked one after another, with each Mask node serving as one more layer of masking. As soon as a Mask node's input attaches to another mask, a Paint Mode drop-down menu shows up, letting you pick how the two masks should be blended.

Combining multiple Polygon nodes one after the other in the node tree

The Paint Mode parameter in the Polygon node Inspector parameters

Merge is the default choice, but you can also pick Subtract, Minimum, Maximum, Multiply, or whatever other operation delivers the mask boolean interaction you're after. On top of that, a pair of Invert and Solid checkboxes let you fine-tune how the current mask blends with the one preceding it.

### The Invert and Solid options

### Mask Inputs on Other Nodes

Because masks serve so many purposes, different nodes offer several categories of mask input to cover those varied uses. As it happens, you can usually wire either masks or mattes into a mask input to make use of that input's capability. TIP: Pick a node that has an empty effect mask input, then add a Mask node, and it hooks straight into the open effect mask input on its own.

### Effects Mask Inputs

Nearly every node in Fusion carries an Effect mask input (colored blue) that lets you decide which parts of the image that node does or doesn't affect.

A Blur node with a Polygon node masking its effect When a mask (or matte) is wired in through an input, it is really applied "post effect," meaning the node first runs its effect over the whole image and then the mask trims the result by copying unaffected image data back over from the input. Plenty of nodes accept effects masking, but on a few it does not apply—namely Savers, Time nodes, and the Resize, Scale, and Crop nodes. TIP: Effects masks set the domain of definition (DoD) for that effect, boosting its efficiency.

A Polygon node serving as the mask that confines what the Blur node affects

### Pre-Masking Inputs

A pre-mask input (whose name is generally particular to each node that uses one) differs from an effect mask in that the node consults it before running the effect. That usually lets the node render faster and turn out a more lifelike result. With the Highlight and the Glow nodes, a pre-mask pens the effect into certain image areas yet lets the effect's result spill out past the mask's edges. Pre-masking's upside is that it lets glows and highlights behave more like they do in the real world. Picture an actor shot in front of a bright light: the light triggers a glow inside the camera lens. Since the glow occurs in the lens, the actor's luminance gets affected even though the glow originates only from the light. On the DVE node, a pre-mask serves to transform only a selected slice of the picture, sparing the parts that fall beyond the mask. That proves useful when you mean to transform just a single region of the picture.

### Garbage Matte Inputs

A Garbage Matte input (usually colored gray) exists to shut out light stands, rigging, and boom microphones that creep into masks being pulled through blue-screen and green-screen keys. In the example that follows, a lighting stand on the left is wiped from the image by a B-Spline node's mask wired into the Garbage Matte input of the DeltaKeyer node.

Here a B-Spline node feeds the Garbage Matte input on a DeltaKeyer node, wiping out a light stand sitting at frame left TIP: You can drop a mask node onto the Effect/Solid/Garbage Matte inputs of a keyer node in a hurry by right-clicking that node's header bar in the Inspector and picking whichever mask node you want from the Effect Mask, SolidMatte, and GarbageMatte submenus. Whether a garbage matte hits a keying node as opaque or transparent is your call in the Inspector for the node it's wired to.

### Solid Matte

A Solid Matte input (colored white) is meant to plug unwanted gaps in a matte, often via a more loosely pulled key that yields a dense matte with eroded edges, although a polygon or mask paint could fill that role too. In the example below, a soft key meant to keep the gentle edges of the talent's hair leaves gaps in the mask of the woman's face, but bringing in another

DeltaKeyer to build a solid matte for the key's interior, one that can be eroded smaller than the original matte, lets you plug the gaps while keeping the soft edges undisturbed. People sometimes call this a hold-out matte.

Plugging gaps in the mask the DeltaKeyer1 node pulled (left) by way of a harder, eroded key from DeltaKeyer2 wired into the SolidMatte input on DeltaKeyer1 (right)

### Creating and Editing Polylines In‑Depth

This section digs into the Polygon node's capabilities thoroughly.

### The Polyline Toolbar

Any time a node holding one or more polylines is selected, the polyline appears on every viewer and the Polyline toolbar lines up along the side of each viewer. The toolbar holds a handful of buttons that put switching polyline modes and options within easy reach.

### The Polyline toolbar

Hover the pointer over any button on the Polyline toolbar and a tooltip spelling out that button's job pops up. Clicking a button acts on the currently active polyline or on the selected polyline points, depending which button it is. You can resize the toolbar icons, attach labels to the buttons, or otherwise tweak how the toolbar looks to make polylines simpler to work with. Every one of these options turns up when you right-click the toolbar and pick from the choices shown in the contextual menu.

### Selecting a Specific Polyline

Selecting several Mask nodes in the Node Editor can leave more than one polyline in the viewer at the same time, so being able to flip between polylines with ease matters. To make a polyline active, do one of the following:

- Click one of the polyline's control points or segments.
- Press Tab and Shift-Tab to cycle between available polylines.
- Right-click inside the viewer and, from the Controls > Select menu, pick the polyline you want by its name.

### Polyline Creation Modes

The toolbar offers a few different modes for building and reshaping polylines. Which mode kicks in when a polyline is first added hinges on whether it serves as a path or a mask. Each mode gets a fuller description below.

### Click Append

For mask creation, this mode is the default. You use it to lay down the mask's rough form fast, after which you move to Insert and Modify mode to sharpen the mask further.

The Click Append toolbar button (Shift-C) To make a mask via the Click Append mode, follow these steps: 1 Pick Click Append off the toolbar, or hit Shift-C. 2 Click the pointer at the spot where the shape should begin. 3 Reposition the pointer and click to tack a fresh point onto the previous one. 4 Closing the shape means hovering the mouse pointer over that first point you made and clicking once the pointer's appearance changes. Once a shape closes, the polyline flips automatically into Insert and Modify mode. The Click Append mode seldom gets used for paths, but it can come in handy when you know a motion path's overall form yet haven't pinned down the timing. TIP: Holding Shift as you draw a mask locks each new point to 45-degree angles off the prior point. That can really help when you're drawing regular geometry.

### Insert and Modify

A mask built in Click Append mode flips into Insert and Modify mode by itself the moment its shape closes. You can also switch into this mode by hand by clicking the Insert and Modify button in the toolbar or pressing the Shift-I keyboard shortcut. Working in this mode makes it simpler to drop in extra points and refine the mask's shape. Dragging the control points or direction handles reshapes points already on the polyline.

The Insert Modify toolbar button (Shift-I) Insert and Modify mode doubles as the default mode for building motion paths. A fresh control point is tacked onto the polyline's end, extending or refining the path, whenever a parameter animated along a motion path gets moved.

### Draw Append

The Draw Append mode lays down a freehand polyline shape straight on the viewer, much like sketching with a pencil or paintbrush. This mode pairs especially well with a tablet and suits building garbage mattes and effect masks around intricate shapes.

The Draw Append toolbar button (Shift-D)

### Protection Modes

Beyond the modes for building a polyline, two further modes exist to guard the points against any more changes once they've been made.

### Modify Only

Modify Only mode lets you reshape points already on the polyline, but it won't let new points be added to the shape.

The Modify Only toolbar button (Shift-M) TIP: Even with Modify Only active, you can still delete points off a polyline.

### Done

The Done mode blocks the creation of any new points along with any further reshaping of points already on the polyline.

The Done toolbar button (Shift-N)

### Closing Polylines

A polyline can be closed in several ways, each joining the final point back to the first. To close a polyline, do one of the following:

- Bring the pointer over that first point you made, then click that point.
- Press Shift-O on the keyboard.
- Click the Close button on the polyline toolbar.
- Keep drawing a polyline until the shape is ready to close, then right-click and pick Polygon:Polyline > Closed.

The Close toolbar button (Shift-O) Each of these options is a toggle that can likewise reopen a closed polygon.

### Selecting and Adjusting Polylines

To form the shape a mask or motion path calls for, you have to know how to work the splines. Fusion supplies several easy methods for selecting, moving, and smoothing a spline, plus more involved adjustment methods for scaling, skewing, and twisting one.

### Polyline Points Selection

Selecting a polyline's control points, whether one or several, can be done any of these ways:

- Click directly on the control points.
- Lasso around the points.

To add points to or drop them from the current selection, do one of the following:

- Hold the Shift key to select a continuous range of points.
- With Command held, click whichever control points you mean to add or drop.
- Press Command-A to select all the points on the active polyline.

TIP: With a control point selected, pressing Page Down or Page Up on the keyboard picks the next control point going clockwise or counterclockwise. That can really help when control points sit very close together.

### Moving Polyline Points

You can shift the selected polyline points with either the keyboard or the mouse. To move selected control points with the pointer, do one of the following:

- Drag on the selected points anywhere in the viewer.
- Hold Shift while dragging to restrict movement to a single axis.
- With Option held, drag at any spot in the viewer to shift the selected control point.

To move selected control points with the keyboard, do one of the following:

- Tap the keyboard's Up or Down Arrow keys to inch a point upward or downward within the viewer.
- Hold Command-Up or Down Arrow keys to move in smaller increments.
- Hold Shift-Up or Down Arrow keys to move in larger increments.

### Smoothing a Polyline Segment

When you want to mold the polyline and steer its slope, you can opt to smooth a spline segment by working the Bézier direction handles. Smoothing the points selected on an active polyline happens any of these ways:

- Press Shift-S.
- Click the Smooth button on the Polyline toolbar.
- Choose Smooth from the polyline's contextual menu.

The Smooth button in the toolbar (Shift-S)

### Linearizing a Polyline Segment

To guarantee a polyline segment is perfectly straight, that segment has to be linearized. A linear segment lines the Bézier direction handles up with the segment, so it carries no curvature. The segment always renders as a straight line running between two points on the polyline. Linearizing the points selected on an active polyline happens any of these ways:

- Press Shift-L.
- Click the Linear button on the polyline's toolbar.
- Choose Linear from the polyline's contextual menu.

The Linear button in the toolbar (Shift-L)

### Transforming Individual or Multiple Points

Pick the points you want to transform, and then do one of the following:

- Hold T and drag to twist.
- Hold S and drag to scale.
- Hold X and drag to scale horizontally only.
- Hold Y and drag to scale vertically only.
- Hold O and drag to offset the points perpendicular to the tangent.

Wherever the pointer sits as the transformation kicks off becomes the center the transformation pivots around.

### Deleting Selected Points

You can remove a selected point or batch of points by pressing Delete or Backspace, picking Delete off the contextual menu, or clicking the Delete Point button in the toolbar. The polyline's shape shifts to reflect those points being gone. TIP: Removing every point in a polyline doesn't remove the polyline itself. To delete a polyline, you have to delete the node or modifier that spawned it.

### Editing Bézier Handles

On Bézier polylines, each control point carries two direction handles that tune the slope of a curve passing through it. These direction handles surface only while the point is selected. Dragging a direction handle tweaks the curve of the segment leaving that control point. The direction handle on the opposite side of the control point shifts in step too, holding the bond between the two handles. To sever the bond between direction handles and move one on its own, hold Command as you drag a handle. Later changes will restore the bond, unless you keep Command held through each adjustment.

### Hold Command to adjust one handle independently

When you want to change a handle's length without altering its angle, hold Shift as you move a direction handle.

### Point Editor

Through the Point Editor dialog you can relocate control points using exact X and Y coordinates. Tapping the E key on the keyboard summons the Point Editor dialog and lets you relocate one or more selected control points.

Positioning control points through the Point Editor dialog Inside the dialog box sit that point's X- and Y-axis values. Punch fresh values into those boxes and the control point relocates. Select several control points and they all snap to one position. That comes in handy for aligning control points along the X- or Y-axis. Whenever you've selected more than a single point, two radio buttons up at the dialog box's top determine whether your adjustments reach every selected point or only one. Choose the Individual option and the affected point shows up in the viewer inside a larger box. Should the selected point be the wrong one, the Next and Previous buttons at the bottom of the dialog let you shift the selection.
