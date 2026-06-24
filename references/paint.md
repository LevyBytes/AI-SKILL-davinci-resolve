# Paint (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Paint

This chapter walks through wielding Fusion’s non-destructive Paint tool to mend images, take out objects, and layer in creative elements.

### Paint Overview

As a procedural paint tool, the Paint node treats every paint stroke as a live, editable object drawn from properties you can combine freely to tackle a broad range of painting work. Put it to use painting masks, retouching images, doing beauty work, cloning objects away, or even building motion graphics. Every part of a paint stroke stays open to change well after you lay it down. Because the strokes remain editable, you’re free to apply, adjust, bypass, delete, and even reorder them within a node tree.

### Types of Paint Nodes

Fusion offers two kinds of paint nodes. The Paint node is a fully featured, vector-based paint tool for creative work and retouching that needs an input to paint onto. The Mask Paint node, by contrast, lets you paint an alpha channel specifically so you can confine an effect’s area. With it you draw paint strokes on an alpha channel without any input being required.

- You’ll find the Paint node under the Paint category of the Effects Library.
- You’ll find the Mask Paint node under the Mask category of the Effects Library.

What chiefly separates these two Paint tools is that the Mask Paint tool only ever paints the Alpha channel, hence it has no channel selector buttons. The Paint tool, meanwhile, can paint on any channel or all of them. Most of this chapter deals with the Paint node, given that its parameters and settings match the Mask Paint node’s exactly.

The Paint node, found within the Effects Library’s Paint category

### Setting Up the Paint Node

Two inputs sit on the Paint node. As with most Fusion nodes, the orange background input is the main one, where you hook up the “canvas” or image you’ll paint on, and the second blue input takes an Effect Mask. The Paint node, unlike the Mask Paint node, needs a background input before any painting can start.

### Setting the Paint Node’s Resolution

However you place the Paint node in your node tree, it takes on the background input image’s resolution as the working resolution for that task. The Paint tool is genuinely resolution independent and you can revise this assigned resolution whenever you wish, yet getting the resolution of your media right matters, since it bears on operations like motion tracking that you’ll fold into your paint workflow. For that reason, the Paint node needs a background input to fix the resolution of the “canvas” you’re about to paint on. There are two ways to wire up a Paint node in the node tree for this: painting straight onto an image, or running Paint as the foreground.

### Painting Directly on an Image

The image you intend to paint on can plug straight into the Paint node’s background input. That’s the simplest, tidiest way to build the node tree, though it offers little compositing flexibility.

The Paint node is dropped right after the node it paints on Using Paint as the Foreground in a Merge Composite Another arrangement has a Background node set the resolution for the Paint node, with the result composited over the real background through a Merge node. Going this route lets you lean on the Merge node’s Apply Mode setting (sometimes called composite modes) to dictate how your paint strokes blend against the image, but it does call for a little more setup.

The merge composites the Paint node over the image you mean to paint on

Putting this together takes a bit of node configuration. The Background node has to be wholly transparent, and unless you’re doing something basic such as painting over an image with the Stroke tool set to Color, you have to drag the image you’ll clone or smudge into the Source Tool field of the Paint node’s inspector. Fuller coverage of these steps comes later in the chapter.

### Paint Node Workflow

To start painting, first pick the paint stroke type from the Paint toolbar above the viewer. Ten stroke types are on offer, along with two more tools for selecting and grouping paint strokes. For a full rundown of the stroke types and tools, turn to the DaVinci Resolve Reference Manual’s Chapter 113, “Paint Node,” or, in the Fusion Reference Manual, Chapter 53. The Stroke tool is the main one for painting and cloning. A fully animatable, editable vector-based paint stroke, the Stroke tool starts out spanning the whole global range in duration.

Cloning, beauty work, and creative paint are the Stroke tool’s most frequent uses

### Select the Correct Paint Stroke Type

Rather than juggling several dedicated Paint nodes for separate operations, you get a single tool carrying an assortment of stroke types, thanks to the procedural design of Fusion’s Paint tool. Every stroke type fills a distinct role. From the Paint toolbar above the viewer you choose among the various stroke types and drawing tools, which fall into a handful of categories.

### Single-Frame Stroke Types

The Multistroke and Clone Multistroke are built squarely for single-frame retouching jobs — clearing raindrops out of a shot that’s meant to look sunny, say, or wiping away scratch marks and dust while restoring vintage footage. For tasks of that sort, these two Multistroke options outrun the other stroke types, but they can’t be edited afterward. So you have to settle the brush’s size and function, plus the paint stroke’s duration, before you paint. Each of these stroke types runs one frame by default, a figure you can change with the Stroke Duration slider in the Inspector. Multistroke and Clone MultiStroke are essentially one and the same, save that Clone Multistroke sets the tool up for cloning automatically. The Multistroke, on the other hand, leaves you to configure cloning by hand.

The Multistroke and Clone Multistroke are single-frame stroke types you can’t edit later

### Editable Stroke Types

The Stroke and Polyline resemble each other in that both stay open to change and animation whenever you like. Each one also opens with a duration covering the whole comp, which the Keyframes Editor can likewise alter.

The Stroke and Polyline strokes can be edited and run the whole comp The Stroke Tool Among the most adaptable editable stroke types you’ll reach for across many jobs is the Stroke, since it’s fully animatable and editable. Every element of the Stroke can be animated, and the Write-on/ Write-off parameters let you dictate how the stroke shows up onscreen. You can also tie a tracker to the Stroke’s Center point when you want it to track a specific onscreen motion. Out of the box, the Stroke type keeps the path’s shape control points hidden. The Stroke’s center and rotation can be moved and tracked, yet the individual control points forming the spline stay out of sight. To surface those control points, head to the Stroke Controls down at the Inspector’s base and hit the Make Editable button.

The Make Editable button brings the Stroke’s control points into view The Stroke type may be the most adaptable, but that adaptability can cost performance once you’re laying hundreds of strokes on a frame. When you have a great many strokes that don’t require animation, Multistroke or Clone Multistroke is the wiser pick, since they’re easier on the processor. The Polyline Stroke Tool The Polyline Stroke behaves more like a drawing tool than a paintbrush. It carries the Stroke tool’s full functionality, with the difference that you create it not by dragging or “painting” as you would a brush, but by clicking to lay down a spline path, the way you do with masks and motion paths. Even before you make a stroke in the viewer, the Polyline Stroke can attach to existing polylines such as a mask or a motion path. With a motion path published, a right-click on the Shape Animation label — found at the base of the Polyline Stroke’s Stroke Controls — lets you call up the Connect To menu and take on the shape of a motion path or mask. The same trick works when you import SVG graphics and want to “paint-on” their outlines.

### The Polyline Stroke Shape Animation label

### Shape Drawing Tools

There are five shape-based drawing tools for drawing shapes and then either filling them with a color or cloning an area out of a source image. Each behaves much like the Stroke and Polyline stroke type, in that you can edit them whenever you like and their default duration covers the comp’s full global range. That duration, too, can be edited at any moment in the Keyframes Editor.

The Shape Strokes serve to build shapes or to clone areas defined by shapes Every Copy [Shape Name] stroke type asks that you wire the source node you’re cloning from into the Paint node and switch the Fill Type menu to Image.

The Copy Shapes need a Source wired straight into the Paint tool and set to Image

### Setting the Brush Size

Once the Stroke type is chosen, you can set the Brush size in the Inspector or, more naturally, within the viewer itself. Select the Paint node over in the Node Editor and rest the pointer above the viewer, and an outline of the current brush size becomes visible. To resize the brush, keep the Command key pressed and drag. The circle grows or shrinks, letting you gauge it against other objects you might be painting over.

The brush size can be adjusted interactively right in the viewer

### Choosing an Apply Mode

What the paintbrush actually does is governed by the Apply Mode buttons. Eight Apply modes are available, each tasking the brush with things like painting a color, cloning from a source, smudging an area, or taking out thin wires.

The Apply Mode buttons govern what the paint brush does Picking a Paint Color A colored brush stroke’s paint color and opacity can be chosen in several ways. Reach for the Fill button in the row of Apply modes when your goal is to paint a solid color.

The Color swatch displays the present color A click on it brings up the OS Color Picker window

To pick a color for the paint brush, do one of these:

- Click the color swatch to summon a standard OS Color Picker window.
- Drag the Eyedropper out into the viewer.
- Drag within the color chooser to set a saturation and luminance. Drag along the sidebars to shift the hue and transparency.

As you paint, every stroke comes out unpremultiplied, which means nudging the Alpha slider in the Inspector leaves what you put on the RGB channels alone. Altering opacity, by contrast, reaches all four channels.

### Cloning from the Frame

Picking the Clone Apply Mode lets you paint one area of an image over another. This is the Paint tool’s most frequent application. It lets you strip objects or artifacts from a clip by masking them with a different part of the frame. Whether you clone on a single frame or across the clip’s whole duration depends on the Stroke type you’ve chosen. The Clone Apply Mode lets you sample one area and put it to work as a source for painting over another Clone Apply Mode can draw either from the very image plugged into the Paint node’s background input or from a different source within the node tree. To clone from another region of the same frame: 1 Choose a Stroke type via the Paint toolbar overhead. 2 With the size slider in the Inspector’s Brush controls section, set the brush size. 3 Among the Apply Mode buttons, pick the Clone mode. 4 Option-click over the spot in the viewer you want as the source. A dot turns up marking the center of whatever you’re sampling.

The Clone source’s starting area marked by the X, with the circle standing for the paint brush size 5 Paint across the area you want hidden, drawing on the source pixels.

The Clone finished, once the source area was chosen and the flag pole painted over While erasing objects or artifacts from a clip with the Clone Apply Mode, you’ll sometimes find it simpler to sample from a different frame on the same clip. That approach pays off when the object you’re cloning out shifts during the clip and lays bare the area behind it. By offsetting the source frame, sampling from a different frame can draw on that exposed background. To clone from a different frame of the same clip: 1 Choose a Stroke type using the Paint toolbar that sits over the viewer. 2 Dial in the brush size. 3 Among the Apply Mode buttons, pick the Clone mode. 4 From the Node Editor, drag the clip (MediaIn or Loader) over into the Inspector’s Source Tool field.

The Paint Inspector after MediaIn1 was dragged from the Node Editor into the Source Tool field

5 Tick the Overlay checkbox to view the current frame and the offset frame laid on top of each other. 6 Drag the Time Offset slider to settle on the source frame you want. 7 Option-click over the spot in the viewer you’ll use as the source, or to shift the source frame’s position.

Overlay layers two frames together via Time Offset, so you can clone from one frame onto another 8 Paint across the area you want hidden, drawing on the source pixels.

The plane is halfway painted out by way of the Overlay with Time Offset 9 Untick the Overlay checkbox.

The Clone Apply Mode can pull from a different frame of the same clip

TIP: With a Clone Apply Mode active, keep the O key pressed rather than ticking the Overlay checkbox in the Inspector to see the Overlay. Let go of the O key and you’re back to normal viewing without the Overlay.

### Editing Paint Strokes

After you’ve painted with the Stroke or Polyline stroke type, you can reshape the stroke’s look by selecting it and revising the parameters in the Inspector. Selecting it means switching to the selection tool on the Paint toolbar above the viewer. With the Paint node’s selection tool, either click once on a stroke or draw a bounding box around it to mark it for editing. TIP: To grab several strokes, Shift-click or Command-click to add and drop particular strokes from the selection, or drag a selection box around every stroke you mean to take. While changes can be made in the Inspector’s Tools tab, the Paint node draws on both the Tools tab and the Modifiers tab. Under the Tools tab you make new brush strokes and pick a stroke in the viewer to edit. The Modifiers tab lays out a list of every stroke on the selected Paint node, making it simple to rework any paint stroke you made earlier. NOTE: Multistroke and Clone Multistroke each show as a single item in the Modifiers tab regardless of how many strokes you draw with them. Those two tools can’t be edited once made. The very controls you used in the Tools tab to create strokes live in the Modifier’s tab for changing them. Each individual stroke can be animated as well.

You edit the Stroke or Polyline Stroke type by picking the stroke within the viewer

### Editing Paint Strokes in the Modifiers Tab

Paint a stroke and that stroke’s settings turn up in the Inspector’s Modifiers tab. From there you can adjust the Tools tab settings for the next stroke you’re about to paint. Every time you click, drag, and let go of the pointer button, a new stroke is born. The Modifiers tab numbers each stroke, where it can be selected and edited. Once you finish painting a stroke, it joins the Modifiers tab alongside an extra Stroke modifier standing in for the next stroke. As an example, paint your first stroke and the Modifiers tab lists it as Stroke1 plus a stroke 2, the latter representing the next stroke you’ll make. The Modifiers tab always carries one stroke more than the viewer does. Every stroke shows up in the Modifiers tab ready for editing

### Deleting Strokes

Paint strokes can be removed in two ways. To remove a single stroke, proceed like so: 1 Select the Paint node. 2 Open the Modifiers tab. 3 On the Stroke header you mean to remove, right-click and pick Delete from the menu. To wipe out every paint stroke you’ve made across all frames, do one of these:

- Click the reset button in the Inspector’s top-right corner.
- Delete the Paint node from the Node Editor.

### Animating and Tracking Paint Strokes

In certain respects, animating paint strokes is the same as animating any other effect in the Inspector. Every parameter open to animation carries a gray diamond Keyframe button down its right edge. A click on that Keyframe button drops a keyframe on the current frame and turns on auto-keyframe mode for the parameter. More often, though, the paint stroke gets tracked with one of Fusion’s trackers, or, for motion graphics, animated through the Write-On Start and End sliders.

### Animating with Write-On Controls

Both the Stroke and Polyline stroke types carry Write-On controls, found in the Inspector’s Stroke controls section. Those Write-On controls animate how a stroke emerges along the path. You can drive the Write-On controls either from the Stroke Animation drop-down menu or with the Start and End sliders.

### Stroke Animation Drop-Down Menu

Six options for auto-animating a paint stroke sit in the Stroke Animation drop-down menu. The opening two don’t so much animate the stroke as define a duration. The Limited Duration option leans on the Duration slider to set how many frames the stroke stays onscreen. For genuine auto-animation, choose one of the three Write options or the Trail option. Pick Write On and a write-on animation is built for you automatically. Its duration is pinned by two keyframes that appear the moment you choose Write On from the menu. The Start keyframe lands on the frame where you first drew the stroke. The End keyframe is dropped on the current frame as you choose Write On from the menu. The menu’s other options place their Start and End keyframes much the same way but flip the animation’s direction according to which one you select.

### Write-On Start and End Parameters

The Write-On Start and End parameters let you set the start point and end point along any stroke’s path by hand and keyframe each one on its own. The Start parameter fixes where the stroke begins, given as a percentage offset from the start of the stroke’s path. A Start value of 50, for instance, slides the stroke’s starting point to the middle of its path. The End parameter behaves identically but reckons from the stroke’s far end. By keyframing the End parameter from 0 to 100 across several frames, you can animate a stroke onscreen for a handwriting effect.

### Tracking a Paint Stroke

Any of Fusion’s trackers can animate where a paint stroke sits. Say you cloned a flag pole out of a clip but the camera pans — you can track the flag pole and bind the resulting path to the paint stroke.

A right-click over the Stroke’s Center control in the view lets you apply a tracker modifier To bind a tracker to a paint stroke: 1 Using the Paint node, pick the Stroke brush type and clone an object off a frame. 2 On the Paint toolbar above the viewer, click the Select tool. 3 Draw a selection box around the stroke to grab it. 4 Right-click the stroke’s center control, then pick Stroke1:Center > Modify With > Tracker Position. 5 Click the Modifiers tab to bring up the Tracker controls. 6 Out of the Node Editor, drag the MediaIn for the image you painted on into the Tracker Source field in the Inspector.

Drag the MediaIn you mean to track into the Inspector’s Tracker Source field 7 Click the Track Forward button. 8 Once the track is done, down at the bottom of the Inspector, reach for the Tracker 1 X Offset/Y Offset controls to nudge the paint stroke back into place if needed.

### Tracking a Group of Paint Strokes

You can hand a single tracker to several strokes by folding them into a group and wiring the tracker to that group. Rather than tying in each stroke separately, the group’s center serves all of the strokes. Provided every object moves consistently in the same direction — as things “nailed to the set” would — applying the tracker to the group makes cloning out a batch of objects with one paint node a breeze. To group paint strokes, proceed like so: 1 Draw a bounding box, Shift-click, or Command-click to grab every stroke you want grouped. 2 Click the Paint Group button on the Paint toolbar.

Grabbing all the strokes and then clicking the Paint Group button gathers them into one group The group’s onscreen controls stand in for each paint stroke’s controls, and the Inspector’s Modifiers tab now displays the group’s parameters. You can still edit the individual strokes by picking Show Subgroup Controls in the Inspector’s Modifiers tab. The group, in turn, brings a Center, Angle, and Size control for wiring to a tracker.

Either use the onscreen controls, or, within the Modifiers tab, right-click the Paint Group’s Center X label to wire up the tracker

### Using the Planar Tracker with the Paint Tool

What follows is an example digging further into a workflow that pairs the Paint tool with the Planar Tracker to retouch a clip. By teaming the Paint node with the PlanarTracker node, we’ll wipe a few facial scars off an actor’s forehead in a commercial, showing a typical way these two powerful tools join forces.

The actor carries a few forehead scars the director wants painted out Since this clip is in motion, we can’t simply paint the scars off the man’s forehead; we have to account for the motion so our paint work clings to his face. The usual workflow here analyzes the image’s motion and uses it to run a “steady” operation, locking the area we intend to paint in place so we’re painting on a surface that doesn’t move.

### Setting Up the Planar Tracker for Stabilization

The Planar Tracker is the best route for this, so we’ll drop the PlanarTracker node in after the MediaIn1 node, wiring the image into the PlanarTracker node’s background input. As ever, take care which input you connect so the effect works as intended.

Dropping in a PlanarTracker node to analyze and steady the portion of the image we plan to paint on With the PlanarTracker node selected and loaded into the viewer, a viewer toolbar shows up bearing an assortment of tools for drawing shapes and handling tracking data. The Planar Tracker operates by tracking flat surfaces that you mark out by drawing a shape around the feature you want followed. The moment you create a PlanarTracker node, you can start drawing a shape, so here we trace a plain polygon over the man’s forehead, that being the feature we want steadied ahead of painting. We make a plain box by clicking once on each corner of the man’s forehead to set control points, then clicking back on the first one to seal the shape.

Tracing a shape across the man’s forehead to get ready for Planar Tracking Inside the Inspector, the PlanarTracker node carries tracking transport controls akin to the Tracker’s. There are, however, two buttons — Set and Go — sitting beneath the Operation Mode menu, which starts on Track, that being our first order of business. The Set button picks which frame serves as the “reference frame” for tracking, so you click Set first, then the Track Forward button below it.

Placing a reference frame at the start of the frame range we intend to track TIP: The Set button lets you watch over a Planar Track as it runs and halt it the moment it starts slipping, tweaking things as needed before clicking Set on the new frame to establish a fresh reference, then carrying on tracking forward toward the clip’s end.
