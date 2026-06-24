# Secondary Windows (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Secondary Windows

A secondary correction means singling out one region of the frame, or one subject, by means of a key. Within DaVinci Resolve, keys are grayscale images: the white portions mark where your adjustment lands, while the black portions mark what stays untouched. You can produce a key through the Qualifier palette controls, through a Power Window, or by bringing in an external matte. If you'd like details on working with external mattes, refer to Chapter 146, “Combining Keys and Using Mattes.” The current chapter walks through building shapes with Power Windows so you can single out portions of the frame in various ways and apply these focused corrections.

### Power Windows

Another approach to secondary correction is the Power Window — at heart a shape that lets you single out areas of the frame. Separate controls give you oval, rectangular, polygonal, or freely drawn curved geometry. Since the isolation is done by drawing, Power Windows deliver remarkably tidy output, and their borders can be placed and feathered with precision for many different looks.

Before/after of a Curve Power Window singling out the sky for a focused correction. A Power Window (often just called a “window”) shines whenever the thing you're tweaking fits inside a well-bounded geometric region. Think of the oval covering someone's face, the front end of a car, or a broad stretch of sky — each is well suited to a windowed tweak. One downside is that windows generally have to be animated so they stay locked to whatever they're isolating. Happily, that's precisely where the robust tracker in DaVinci Resolve helps out, letting you track Power Windows swiftly and precisely so they keep pace with the subject being singled out.

Circular Power Window to focus attention to the skin Combining several Power Windows in assorted arrangements is straightforward in DaVinci Resolve, so they can overlap each other and yield still more elaborate shapes. As an illustration, you can sum several windows together, or carve one window out of another, which spares you from elaborate keyframing just to animate a window's outline.

Multiple windows combined to isolate and mask the image. The pages that follow address using Power Windows — building and editing them, plus how to merge several windows and how to pair windows with qualifiers for highly targeted isolations.

### Adding Nodes with Windows

Just like with qualifiers, the first step before windowing a correction is to drop a node into the node tree of your grade. The reason is that every window inside a given node operates jointly to confine that node's grade. Recall that a node can switch from a primary operation touching the whole frame into a tighter secondary operation merely by activating a window, applying a qualifier, or switching on an external matte.

### Serial nodes showing the window on Node 2

Skip adding a fresh node before you build a window, and you'll find you've mistakenly turned a primary correction into a secondary one. After making a new serial node, you'd reach for the controls inside the Window palette to switch on a window and tailor it however you like. That said, a handful of commands exist that drop in serial nodes with a window already active, sparing you a click or keystroke or two. To insert a fresh node with a window already active: for a serial node bearing a circular window, Choose Color > Nodes > Add Serial Node + CPW (Option-C). For one carrying a linear window, Choose Color > Nodes > Add Serial Node + LPW (Option-Q). To get a polygonal window on the new node, Choose Color > Nodes > Add Serial Node + PPW (Option-G). And for a Curve window, Choose Color > Nodes > Add Serial Node + PCW (Option-B). Whenever you add a node carrying a Power Window, the Window palette pops open on its own, ready for editing.

### The Window palette

There are three control groupings within the Window palette: the Window list, the Presets, and the Transform and Softness controls.

### The Window Palette Interface

After you've made a node to host a Power Window correction, you'll want to open the Window palette unless it's already up. To bring up the Window palette: Click the Window palette button. Most of the Window palette's real estate goes to the Window list, where you can build as many windows as the job calls for. Five distinct window types are available, and each carries its own geometry. They can be applied on their own, or merged together to build even more intricate shapes and interactions. Four clusters of controls in the Window palette let you put these windows to work in various ways.

### The Window palette with the Window list

- Window list: Across the top of this list sits a row of buttons for adding fresh windows, which you can then tailor as needed. Every window listed surfaces an On/Off button displaying the shape type, a Layer Name field (empty until you type something in) you can use to label each window's purpose, an Invert button, and a Mask button that controls how the window relates to the other currently active windows (by default it adds to them, while in Mask mode it carves out from them).
- Transform parameters: Governs the overall size, aspect ratio, placement, and rotation of whichever window is currently selected.
- Softness parameters: Governs the edge softness of whichever window is currently selected. The softness choices vary by window shape.
- Option drop-down menu: The Option drop-down menu holds commands for building and editing custom window presets you can recall later, for resetting windows, deleting windows, saving and organizing window presets, and copying and pasting track data.

Across the top of the Window palette, the buttons let you build five window types:

- Linear: A four-point shape you can reshape into whatever rectangle or trapezoid you require. Beyond the center and corner controls, dragging any of the four sides also reshapes it.
- Circular: An oval you can reshape, resize, and feather to handle a remarkable range of problems.
- Polygonal: A four-point shape that can grow extra control points to form intricate sharp-cornered polygons.
- Curve: A Bezier drawing tool for producing any shape you might need — curved, polygonal, or a blend.
- Gradient: A straightforward two-handled control that splits the screen into halves, with settings for the shape's center, angle, and feathering. Handy for quick sky tweaks.

### Managing Windows

Working on a window starts with making the type you want, or — when you already have a batch of windows built — picking the one you want to work on. Ways to create and pick windows:

- To create a new window: Click either the Shape icon button or the Create Window button (sitting at the top of the Window list) matching whichever window type you'd like to build.
- To pick a window via the onscreen controls: Click somewhere inside a window to select it in the Viewer.
- To pick a window out of the Window list: Click the Shape icon button matching the window you'd like to select.

To remove a window you've finished with:

- Select a window, then click the Delete button.

To reset a window:

- To return a single window to its default shape: Pick the window, then choose Reset Selected Window from the Option drop-down.

### Showing and Hiding Onscreen Window Controls

Opening the Window palette switches the Viewer into Power Window mode. Turning a window on brings that window's onscreen controls up inside the Viewer, and they're mirrored to video out so the window controls show on your external display too. You're free to adjust how and where those onscreen controls show up. To decide whether onscreen controls mirror to video out or get switched off, do either of these: Pick a setting from the Window Outline submenu found in the Viewer’s option menu. Three choices exist there. Off: removes the outline from the Viewer as well as the external display. On: the default, which keeps the outline visible in the Viewer and on the external display alike. Only UI: drops the outline from your external display while keeping it shown in the Viewer. Or press Option-H to cycle through all three modes listed above.

That command cycles three ways. Run it once and the window outline vanishes from your external display while staying in the Viewer. Run it a second time and the outline disappears from both the external display and the Viewer. Run it a third time and the outline returns to both the external display and the Viewer. TIP: When you keep the onscreen controls showing in the Viewer, you may at times want to briefly hide or reveal them so you get a clean view of the image you're working on. Any set of onscreen controls can be flipped off and back on without picking Off in the menu — just press Shift-` (tilde).

### Using the High-Visibility Power Window Outline Option

Normally, Power Window outlines render white (the center shape) and gray (the softness shapes). That palette can be hard to make out at times, though, so the Color panel of the User Preferences offers an option under General Settings labeled “High visibility Power Window outlines.” Switching it on makes Power Window outlines draw as green (the center shape) and yellow (the softness shapes), so these windows stand out better in certain situations. (Left) the default window outlines; (Right) the High Visibility outlines switched on via the Color panel of the User Preferences

### Window Transform Controls

Windows carry transform parameters resembling those in the Sizing palette. With these you can modify the window, moving all of its control points in unison.

### Window transform controls

- Size: Grows or shrinks the whole window. The default size is 50.00.
- Aspect: Changes the window's aspect ratio. The default here is 50.00; raise it to make the

window wider, and smaller values make the window taller.

- Pan: Slides the window along the X axis. The default position is 50.00; raise it to push

it rightward, while smaller values shift it leftward.

- Tilt: Slides the window along the Y axis. The default position is 50.00; raise it to lift the

window up, smaller values move the window down.

- Rotate: 0 is the default value. Raising this parameter turns the shape clockwise, while lowering

this parameter rotates the shape counterclockwise.

- Opacity: Lets you tune how transparent a single window's input to the node's key is.
- Convergence: With “Apply stereoscopic convergence to windows and effects” turned on under the

General Options of the Project Settings, this extra Transform parameter shows up, letting you build correctly aligned convergence for a window dropped onto a stereoscopic 3D clip. For additional details on handling Stereoscopic 3D projects, refer to Chapter 15, “Stereoscopic Workflows.” These transform parameters likewise map to onscreen controls in the Viewer, which the pointer can drive directly.

### Manipulating the window position on the Viewer

Although a lot of the onscreen controls map to parameters within the Window palette, certain ones — like the control points that reshape linear, polygonal, and Curve windows — can only be moved with the pointer. Onscreen controls for window transforms:

- To pick any window: Click on one window from a group of many to select it, which makes that window's controls live.
- To move any window: Drag anywhere inside the window's onscreen control. A window's position maps to the Window palette's Pan and Tilt parameters. With a gradient window, drag the center control point.
- To resize a circular window while keeping its aspect ratio fixed: Drag one of the four blue corner points outward to grow it, or inward to shrink it. This maps to the Window palette's Size parameter.
- To squeeze or stretch a circular window, changing its aspect ratio: Drag any of the blue control points at top, bottom, left, or right. Those tweaks map to the Window palette's Aspect parameter.
- To rotate a window: Drag the inner white rotate handle at the top, in the window's middle. For a gradient, drag the bottom arrow handle.
- To change window softness: Drag any of the magenta softness handles. Window shapes carry different handle sets, which map to the Softness parameters.
- To reshape a linear window: Drag whichever white corner handle to corner-pin the window, or grab a white top, bottom, or side handle to shift an entire side segment of the window.
- To reshape a polygonal window: Switching on a polygonal window shows a plain white rectangle bearing four corner control points. Click anywhere across the rectangle's face to drop in more control points for reshaping the polygon, and drag any control point to alter the form. A polygon window tops out at 128 control points.
- To resize a curve and adjust its aspect: Shift-drag a bounding box over whichever control points you'd like to transform, then drag the box's corners to scale the points while keeping the shape's aspect ratio fixed, or drag the top, bottom, left, or right points to squeeze or stretch the shape.
- To remove control points from polygonal or Curve windows: Middle-click whichever control point you want gone.

NOTE: If you delete a control point from a polygonal window that has already been animated through the Keyframe Editor, that point will snap on and off abruptly at the keyframes that drive the animation.

### Window Softness

Every window type carries its own Softness parameters, which depend on how much that window can be adjusted.

- Circular: One parameter, Soft 1, controls the even softness around the oval's border.
- Linear: A set of four, Soft 1–4, controls the softness of each of the linear window's four

sides on its own. Magenta softness control points at top, bottom, left, and right let you set the softness of every side of the linear shape separately.

- Polygon: A pair of parameters, Inside Softness and Outside Softness, set the overall softness for a polygonal window. No onscreen softness control points are present.
- Curve: A pair, Inside Softness and Outside Softness, govern a curve's overall softness. With the onscreen controls, the magenta inside and outside softness control points can be moved independently to form whatever softness profile you require.
- Gradient: One parameter, Soft 1, controls the even softness along the gradient window's border.

### Drawing Curves

Among all the windows, the Curve window alone shows no onscreen controls the moment it's first switched on. You instead click inside the Viewer to drop in control points, sketching your own bespoke shape around whatever region you'd like to isolate.

### Curve window to isolate a car

TIP: Switching the Viewer to full-screen mode can make drawing detailed shapes easier. As you draw, the Viewer can also be zoomed in and out — use a mouse scroll wheel, or press Command-Plus or Command-Minus. To draw a curve: 1 Switch on the Curve window style control. 2 Click somewhere in the Viewer to begin dropping control points and sketching the shape you want. 3 Click and drag to lay down and shape Bezier curves, or simply click and let go to place a sharp angle. 4 To wrap up the drawing and close the shape, click the first control point you placed for a corner, or click and drag on that first control point for a Bezier curve. With a curve drawn, there are many ways to work on it. Quick ways to modify a curve:

- To add points: Click anywhere on a curve to add control points.
- To reshape a curve: Drag any control point somewhere new. You can move control points even mid-draw on a fresh curve — picking earlier points to reposition them, tweak their spline handles, or delete previously added points — with no need to finish the window first.
- To move a curve: Drag anywhere inside or just outside a curve to shift it.
- To symmetrically change a Bezier curve: Drag any Bezier handle. Its opposite handle swings the other way on its own.
- To asymmetrically change a Bezier curve: Option-drag any Bezier handle. Its opposite handle holds still while you drag the current one. After you've built an asymmetric pair of Bezier handles, they travel together as a unit when you just drag a handle. Option-drag is needed to change the angle.
- To turn a curve into a corner: on any Bezier curve control point, Option-double-click to switch it to a sharp-angled corner point.
- To turn a corner into a curve: on any corner point, Option-click and drag to pull out a Bezier handle, switching it to a curve.
- To remove points: Middle-click the control point you want to remove.

NOTE: Should you delete a control point from a polygonal window that's been animated already by means of the Keyframe Editor, that point pops on and off sharply at the keyframes building the animation. You can likewise Shift-drag a bounding box to grab several control points on a curve and move, delete, or transform them all together.

A Shift-drag of a bounding box across several control points lets you handle them all in one go. To grab several control points on a curve: 1 Keep the Shift key held and drag a bounding box over whichever control points you'd like to adjust or remove. Every enclosed control point becomes highlighted. 2 Do one of the following:

- To move the control points: Drag anywhere within the bounding box.
- To transform the control points: Drag any outer corner to scale every control point

uniformly, drag the top, bottom, or side handles to squeeze or stretch the points against each other, or bring the pointer to a corner until the rotate cursor shows up, then drag to spin the control points.

- To delete the control points: Press the Backspace key.

3 Once you're done, press the Escape key to deselect the control points.

### Converting Linear, Circular, and Polygon Windows into Bezier Curves

Suppose you begin singling out a subject with one of the basic Linear, Circular, or Polygon shape windows and then realize the job needs a more involved shape; it's easy to upgrade them to a richer Bezier shape: from the Window palette Option menu, pick Convert to Bezier.

A before-and-after of a circular window turned into a Bezier curve, the result tweaked, prior to any edge softening being added After you've turned a simple shape into a Bezier window, you're free to add control points and mold the shape however you need so it hugs the subject better — exactly as you would with any curve.

### Resetting the Window Palette

The whole Window palette can be cleared via the Option menu's Reset command.

### Combining Power Windows with the Mask Control

Stacking several windows on one node is a simple route to composite keys. As windows combine, the Mask control decides whether one window adds to or subtracts from another. In the example below, both a Circular and a Curve window have been built, and each window's Mask control is on too (the default), so both masks sum together and the sunset look correction reaches both the sky and the woman's face.

The two images show the combination of the key mattes. Switching off the Mask control on the circular window subtracts that circular window from the curve.

Turning off the Mask control of the circular window At this point the woman's face is shielded from the heavy sky treatment.

The two images show the result of subtracting the circular window Because each window can be tracked and keyframed on its own, you can rapidly arrange elaborate window interactions to handle the everyday problems you run into. As an example, when tracking a window onto a moving subject that passes behind something in frame, a second window with Mask off can mask the object in front. Then, as the tracked window crosses the subtractive one, the correction drops away together with the subject. The Mask control likewise lets you build shapes more complex than a lone window allows.

Mattes and mask used together to make complex shapes On top of that, once you hit the ceiling of what the four windows can shape, you can join several nodes holding several shapes and qualifiers by way of the Key Mixer.

### Copying and Pasting Windows

When you've made a window you'd like to reuse within the current node or carry over to a different node, an individual window's shape can be copied and pasted from one Window list entry onto another. Ways to copy and paste windows:

- To copy a window: Click any active window in the Window list, then open the Window palette option menu and pick Copy Window.
- To duplicate a window: Once you've copied a window, build another window matching the type you copied, then open the Window palette option menu and pick Paste Window.
- To paste a window to another node: Double-click or otherwise pick a different node, open the Window palette, choose the same window type you copied within the Window list, then open the Window palette option menu and pick Paste Window.
- To paste a window to the same node: Click any active window in the Window list, open the Window palette option menu and pick Copy Window, then click Paste Append Window in the Window Option menu.

### Saving Window Presets

When there's a certain window shape or window combination you reach for often, you can store one or more windows as a preset and recall it any time. For instance, on a documentary where you wind up brightening a lot of faces, you might build preset face ovals for close-up, medium, and wide shots, so you're not customizing a stock circular window on every new shot. Groups of windows can also be saved together as one preset, letting you reuse complicated multi-window shapes. Window presets live in a cluster of Presets controls within the option menu at the upper right of the Window palette.

Controls for saving, applying, and deleting window presets

Ways to work with Power Window presets:

- To save a window preset: After building one or more windows you'd like to keep, click the Save as New Preset option within the Window palette’s option menu. Enter a name in the dialog that appears, and click OK. From then on that preset shows up in the Preset section of the option menu.
- To recall a window preset: Open the Window palette’s option menu, then pick a preset off the list. A loaded window preset replaces whatever windows had been arranged in that node.
- To update an already saved preset: Bring back a preset, edit its window(s), then open the Window palette’s option menu. Choose Update Preset, then choose the preset name. The selected preset is then overwritten with your revised window layout.
- To delete a window preset: Open the Window palette’s option menu, pick Delete Preset, then pick a preset off the list. Confirm you've picked the right preset name; no warning appears beforehand, and the deletion can't be undone afterward.

Once recalled, windows spawned by presets can be edited and tracked just like any other window.

### Using Windows and Qualifiers Together
