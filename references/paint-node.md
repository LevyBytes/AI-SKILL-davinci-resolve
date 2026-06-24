# Paint Node

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Paint Node

The Paint node found in Fusion is the subject of this chapter.

When you're hunting for tools in the Select Tool dialog, or working with scripting references, the abbreviation beside each node name comes in handy. Throughout this document, treat node trees that display MediaIn nodes in DaVinci Resolve as interchangeable with Loader nodes in Fusion Studio, except where stated otherwise.

### Paint

### The Paint node

### Paint Node Introduction

Paint is a highly adaptable, stroke-based tool meant for wire and rig removal, image cloning, or quickly building custom masks and mattes. You can even lean on Fusion's paint to construct brand-new images and artistic elements from nothing. A series of brush strokes makes up each Paint node. Those strokes are vector shapes whose brush, size, and effect can all be edited. There's a broad selection of apply modes and brush types on offer. The majority of Brushstrokes styles are editable polylines that give you fine control. You can animate them so their shape, length, and size shift over time. With a supported tablet, a stroke's opacity and size can respond to velocity and pressure. Because paint offers unlimited undo and redo, you're free to experiment before locking changes into an image sequence. Paint strokes can be reordered, deleted, and modified with practically boundless flexibility.

### Inputs

The Paint node carries two inputs, used to attach a 2D image plus an effect mask that can confine the painted region. Input: The orange input has to be wired to a 2D image, which establishes the size of the “canvas” you paint onto. Effect Mask: The blue input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Attaching a mask here keeps the Paint confined to just the pixels inside the mask.

### Basic Node Setup

A Paint node can never go without an input connection. The most basic arrangement is to paint straight onto the incoming MediaIn node.

A MediaIn node connected directly to the Paint input

A setup with more flexibility uses a Background node to define a size matching the image you'll paint on. Within the Inspector, you'd make that background completely transparent. The Paint tool can then be merged as the foreground above the actual image you intend to paint on.

For added flexibility, a Paint node merged above a MediaIn

### Types of Paint Strokes

Paint stroke types located in the viewer toolbar. When you start out with the Paint tool, first pick the paint stroke type from the Paint toolbar sitting above the viewer. There are ten stroke types available, alongside a pair of additional tools that select and group paint strokes. Coverage of the stroke types and tools follows below, matching the sequence they sit in along the toolbar.

- Multistroke: While this is the default pick and the first real brush type in the toolbar, Multistroke generally isn't the stroke type you'll reach for most. That said, it's ideal for those 100-strokes-per-frame retouching paint jobs such as removing tracking markers. Multistroke runs much quicker than the Stroke type but can't be edited once it's made. By default a Multistroke lasts a single frame and can't be altered after it's painted. Set the number of frames ahead of painting using the Duration setting in the Stroke controls. The Keyframes Editor shows a shaded area for the Multistroke duration, though it's not editable there. Even though Multistrokes can't be edited directly, they can be grouped using the PaintGroup modifier and then tracked, moved, and rotated by animating the PaintGroup instead.
- Clone Multistroke: Much like Multistroke but built specifically for cloning elements from one area or image onto another. Ideal for those 100-strokes-per-frame retouching paint jobs such as removing tracking markers. Clone Multistroke moves faster than the Stroke type yet can't be edited once it's made. By default a Clone Multistroke lasts a single frame and can't be altered after it's painted. Set the number of frames ahead of painting using the Duration setting in the Stroke controls. The Keyframes Editor shows a shaded area for the Clone Multistroke duration, though it's not editable there.
- Stroke: For the most part, the Stroke tool is what comes to mind when people picture paint, and it's the go-to choice for most jobs. It's a fully animatable, editable, vector-based paint stroke. It can bog down when hundreds of strokes fill an image; when you're laying down a great many paint strokes, Multistroke is the better option. The Stroke type spans the whole global range as its duration. You can, however, change its duration whenever you like in the Keyframes Editor. After you've finished painting, click the Select button in the Paint toolbar so you don't accidentally tack on new strokes.
- Polyline Stroke: This lets you build and reshape a stroke the same way you'd build a Bézier path or polygon mask. To add a Polyline Stroke, click the Polyline button and click in the viewer to drop the first point. Keep clicking to drop further points onto the polyline. This click append style is the default, though polyline strokes can also be drawn in draw append mode. Polylines can be tracked or hooked up to existing polylines such as masks or animation paths. By default the Polyline Stroke spans the whole global range as its duration. You can, however, change its duration whenever you like in the Keyframes Editor.
- Circle: Builds a circular shape with animatable control over radius and center. By default the Circle type spans the whole global range as its duration. You can, however, change its duration whenever you like in the Keyframes Editor.
- Rectangle: Builds a rectangular region. By default the Rectangle type spans the whole global range as its duration. You can, however, change its duration anytime in the Keyframes Editor.
- Copy Polyline: Lets you build a closed Polyline region with an animatable offset so you can clone elements from one area or image onto another. By default the Copy Polyline type spans the whole global range as its duration. You can, however, change its duration whenever you like in the Keyframes Editor.
- Copy Circle/Rectangle: A circular or rectangular shape region with an animatable offset for cloning elements from one image onto another. By default the Copy Circle/Rectangle type spans the whole global range as its duration. You can, however, change its duration whenever you like in the Keyframes Editor.
- Fill: Comparable to the Wand mask tool. It fills neighboring pixels of similar color using a fill color drawn from the chosen color channel. By default the tool spans the whole global range as its duration. You can, however, change its duration whenever you like in the Keyframes Editor
- Paint Group: Lets you bundle several paint strokes together with full command over center and size. Because the Multistroke and Clone Multistroke styles can't be tracked, bundling those paint stroke types and tracking the paint group is one common reason to use groups.

### Editing Options Toolbar

Paint edit options show up in the viewer once a Polyline stroke has been made. Polyline-based paint strokes bring a second toolbar into the viewer for picking among different editing options. Polyline Stroke and Copy Polyline are the paint strokes that bring along this second toolbar. As for the Stroke style, it too surfaces this toolbar once you've selected the stroke and pressed the Make Editable button over in the Inspector.

- Click Append: This is the default behavior while you're making a polyline stroke. It acts more like a Bézier pen drawing tool than a paintbrush. A click sets a control point and adds the next control point when you click again somewhere else.
- Draw Append: A freehand drawing tool. It lays down a stroke much like sketching with a pencil on paper. With the Draw tool you can build a fresh Polyline Stroke or Copy Polyline Stroke, or lengthen a Stroke style once the Make Editable button over in the Inspector has been pressed.
- Insert: Insert drops a new control point onto the paint stroke spline.
- Modify: Modify lets you safely shift or smooth any existing point along a spline without

worrying that you'll accidentally tack on a new point.

- Done: Keeps every point along the spline from being moved or modified. New points can't be added either. You are, however, free to move and rotate the whole spline.
- Closed: Closes an open polyline.
- Smooth: Converts whichever stroke or control point is selected from a linear into a smooth curve.
- Linear: Converts whichever stroke or control point is selected from a smooth curve into linear.
- Select All: Selects every control point on the polyline.
- Keys: Reveals or hides the control points along the polyline.
- Handles: Reveals or hides the Bézier handles along the polyline.
- Shape: Wraps a reshape rectangle around the selected polyline control points. With that reshape

rectangle, you can deform clusters of polyline control points or whole shapes far more easily than tweaking each point.

- Delete: Deletes the selected control point(s).
- Reduce: Opens a Freehand precision window you can use to cut down the count of control

points on a polyline. That can make a paint stroke easier to modify, particularly one drawn with the Draw tool.

- Publish: The Publish menu lets you publish either control points or the path. Publishing is a kind of parameter linking. It makes the chosen item available for other controls to use, or lets you attach a control point to a tracker.
- Follow Points: Lets a chosen point trail the path of a published point. The point follows the published point at an offset position.
- Roto Assist: Switch on the Roto Assist button as you start painting with the Polyline Stroke tool. As you click to build up the shape's points, the polyline points snap onto whichever edge is closest. Points that have snapped onto an edge are marked by a cyan outline. Three principal Roto Assist options are available from the drop-down menu:

Multiple Points: With this on, a single click on a high-contrast edge drops several points to map the entire edge, rather than making you place each one by hand. It's a one-time-only click. The next click goes back to single point edge detection. Distance 8: Brings up a dialog where you set the pixel range within which the edge search happens. Reset: Used to clear the snap attribute from every snapped point. Once reset, those points can no longer be tracked.

### Inspector

### The Paint Controls tab

### Controls Tab

Not every control described here turns up in every mode. Certain controls matter only within a particular Paint mode and stay hidden when they don't apply. The Controls tab is where you set up your paint settings before painting. After a paint stroke has been made, apart from the Multistroke and Clone Multistroke, you can pick the stroke in the viewer and revise the controls.

### Brush Controls

- Brush Shape: Picking the brush tip shape is done with the brush shape buttons. Apart from the single pixel shape, the brush shape's size can be changed in the viewer if you hold the Command or Ctrl key as you drag with the mouse. Soft Brush: A circular brush tip with soft edges is what the Soft Brush type gives you. Circular Brush: With hard edges, a Circular Brush is a brush tip shape. Image Brush: Through the Image Brush, pictures pulled from any node in the node tree, or off a file system, can act as a brush tip. Single Pixel Brush: Well suited to fine detail work, the Single Pixel Brush yields a brush tip measuring precisely one pixel across. The single pixel brush receives no anti-aliasing. Square Brush: With hard edges, a Square Brush is a brush tip.
- Vary Size: Vary size settings alter the stroke size according to speed or a pressure-sensitive pen and tablet.

Constant: The brush tip holds a constant size across the stroke. With Pressure: The stroke size changes with the pressure actually applied. With Velocity: The stroke size changes with how fast you paint. A quicker stroke comes out thinner.

- Vary Opacity: Vary opacity settings alter the stroke opacity according to speed or a pressuresensitive pen and tablet.

Constant: The brush tip stays at a constant transparency setting across the whole stroke. With Pressure: The stroke transparency changes with the applied pressure. With Velocity: The stroke transparency changes with how fast you paint. A quicker stroke comes out more transparent.

- Softness: This control lets you raise or lower the Softness of a soft brush.
- Image Source: With the Image Source brush type, choose among three possible source

brush images. Node: Here the image source is taken from a node's output within the node tree. To assign the source, drop that node onto the Source node input field in the Inspector. Clip: Here the image source is taken from an image or sequence stored on disk. Any file format that Fusion's Loader or MediaIn node handles will work. Brush: From the menu, choose an image that will serve as a brush. Whatever images live in the Fusion > Brushes directory fill out that menu.

- Color Space: With the Fill tool active, a Color Space menu picks the color space used when sampling colors around the Fill tool center to decide what goes into the fill range.
- Channel: With the Fill tool active, a Channel menu picks which color channel drives the fill paint. As one example, with alpha chosen, the fill spreads over contiguous pixels of the alpha channel.

### Apply Controls

- Apply Mode: The Apply Modes are buttons that change how a brush paints. Color: The Color Apply Mode paints plain colored strokes. Paired with an image brush, it can also tint the image.

Clone: Drawing on adjustable positions plus time offsets, the Clone Apply Mode duplicates a region out of the same image. It's also capable of copying parts of one image into a second image. The source image can be any image taken from the node tree. Emboss: The Emboss Apply Mode embosses the parts of the image the brush stroke covers. Erase: Erase reveals the underlying image through every other stroke, effectively wiping away parts of the strokes below it without actually destroying those strokes. Merge: This Apply Mode effectively merges the brush onto the image. It works much like the Color Apply Mode but offers no color controls. It's best paired with the image brush type. Smear: Smears the image, taking the brushstroke's direction and strength as a guide. Stamp: Stamps the brush onto the image, disregarding any alpha channel or transparency information entirely. This mode suits applying decals to the target image best. Wire: By sampling the pixels nearby and dragging them inward toward the stroke, this Wire Removal Mode takes out wires, rigging, and similar small elements within the frame.

### Stroke Controls

The stroke controls hold parameters that adjust the whole stroke of paint along with governing it over time.

- Size: This control sets the brush size when the brush type is either Soft Brush or Circle. The brush diameter is drawn in the viewer as a little circle ringing the mouse pointer. The size can likewise be set on the fly within the viewer if you keep the Command or Ctrl key held down as you drag the mouse pointer.
- Spacing: The Spacing slider sets how far apart the dabs sit (the samples used to draw a continuous stroke along the underlying vector shape). Raising this value makes the stroke denser, while lowering it gives the stroke the look of a dotted line.
- Stroke Animation: The Stroke Animation menu supplies several ready-made animation effects you can apply to a paint stroke. This menu shows up only for vector strokes such as Stroke and Polyline Stroke.

All Frames: This default shows the stroke across every frame of the image wired into the orange background input of the Paint node. Limited Duration: This lasts for the number of frames the Duration slider specifies. Write On: With Write On chosen, an animation spline gets added to the paint stroke that exactly mirrors the timing of how the paint stroke was created. The stroke is written onto the image precisely as you drew it. To tweak the Write On effect's timing, head to the Spline Editor and use the Time Stretcher node to alter the animation spline's overall length. To smooth or hand-adjust the motion, try thinning out the points in the animation spline. Write Off: Write Off does the opposite of Write On, drawing the stroke from the end and moving backward toward the stroke's start. Write On Then Off: This menu option puts a Write On followed by a Write Off animation mode onto the stroke. Trail: Picking the Trail option from the menu animates the stroke's start and end points at the same time, offset from one another by the amount the Duration control specifies. What you get is a painted segment trailing along the path of the stroke. Just like the Write On and Write Off effects, it begins on the current frame as soon as the animation mode is chosen. The animation's timing can be hand-adjusted through the Spline or Keyframes Editors.

- Duration: In frames, Duration determines the length of each stroke. You'll see this control only with Multistroke and Clone Multistroke, or whenever Limited Duration is the chosen stroke animation mode. Its most frequent application is frame-by-frame rotoscoping across a scene.

In the Keyframes Editor, every Vector stroke placed on a scene holds a duration that's trimmable independently, stroke by stroke. Setting that duration to a value of 0.5 makes each stroke survive for only one field while the node tree runs in Fields mode.

- Write On and Write Off: Whenever Stroke Animation uses one of the Write On and Write Off methods, this range slider appears. Its range corresponds to where the stroke begins and ends. Pushing the Start value upward from 0.0 to 1.0 erases the stroke, while pushing the End value upward from 0.0 to 1.0 paints the stroke onto the screen. Animating this control can yield nice results. The best outcome comes from animating it automatically by way of the Write On and Write Off modes within the Stroke Animation menu.
- Make Editable: This button shows up only for Vector strokes. Clicking Make Editable converts the current stroke into a polyline spline so its shape can be adjusted or animated.

### Paint Node Modifiers

Each paint stroke you draw in the viewer brings an associated modifier stroke into being. Inside the Inspector's Modifiers tab, those modifier strokes show up as a roster of paint stroke operations. Every stroke you draw is open to being modified, deleted, or reordered by way of the modifier stack. NOTE: Because the MultiStroke tools are made for speed, they can house plenty of strokes internally without spawning an enormous list stack in the modifiers Each Paint modifier stroke holds Brush controls, Apply controls, and Stroke controls that match the ones in the main Controls tab of the Inspector.

### Keyboard Shortcuts

By way of keyboard shortcuts, you can switch painting styles and color without burrowing into menus. As you paint: a left-drag while you hold Command or Ctrl resizes the brush. Holding Option or Alt and clicking samples a color out in the viewer. As you clone: an Option-click or Alt-click fixes the clone source position, and strokes begin cloning from wherever that location is. Keeping O held briefly turns on a 50% transparent overlay of the clone source (you can adjust the % through the pref Tweaks.CloneOverlayBlend). A tap of P flips an opaque overlay of the clone source on and off. With the overlay visible: the clone source position shifts via the Arrow keys, plus you're free to drag crosshairs and tweak the angle control or size sliders. The clone source angle shifts with the Option + Left/Right or Alt + Left/Right Arrow keys. The clone source size shifts with the Option + Up/Down or Alt + Up/Down Arrow keys. Adding Shift + Command or Shift + Ctrl alongside any of these yields larger or smaller adjustments. The two square brackets, [ and ], shift the clone source Time Offset (a particular Clone Source node has to be assigned in the Source Node field for this). Copy Rect/Ellipse: constrain the shape by dragging the source out with Shift held. When one stroke alone is selected (this isn't offered on multi or polyline strokes): a press of X or Y flips that stroke. Paint Groups: a Command + drag or Ctrl + drag relocates a group's crosshair, leaving the group's own position untouched.
