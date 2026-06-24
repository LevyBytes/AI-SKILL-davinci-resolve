# Exploring The Fusion Interface (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Tools can be added to or pulled from the Fusion toolbar, after which you're able to store your custom toolbar as a preset. Fresh tools get added by dragging them out of the Effects Library or the Node Editor, and dividers can be dropped in to cluster sets of tools together. To build a new toolbar, proceed as follows: 1 Right click on a blank stretch of the toolbar and select Customize > Create Toolbar from the contextual menu. 2 Type a name for the toolbar into the dialog box, then click OK. To reorder the tools sitting in the toolbar, proceed as follows: 1 Build a new custom toolbar or pick an existing custom toolbar. 2 Drag a node in the toolbar over to a fresh spot. To add a tool to the toolbar: 1 Build a new custom toolbar or pick an existing custom toolbar. 2 Do one of the following:

- Pull a node out of the Effects Library and drop it at whatever spot on the toolbar you'd like it placed.
- Pull a node out of the Node Editor and drop it at whatever spot on the toolbar you'd like it placed.

To drop a divider onto a toolbar, proceed as follows: 1 Build a new custom toolbar or pick an existing custom toolbar. 2 Right-click over any tool and select Customize > Add Divider. The divider lands to the right of that tool. To pull a tool off a toolbar, proceed as follows: 1 Build a new custom toolbar or pick an existing custom toolbar. 2 Right-click over any tool and select Remove [name of tool]. To strip out a group of tools sitting between two dividers, proceed as follows: 1 Build a new custom toolbar or pick an existing custom toolbar. 2 Right-click over any tool within a group and select Remove Group. To keep a custom toolbar from being altered:

- Right-click over the toolbar and select Lock from the contextual menu.

To swap between toolbars:

- Right-click over the toolbar and select the custom toolbar name, or select Default to come back to Fusion's default toolbar.

To rename a custom toolbar, proceed as follows: 1 Right-click over the toolbar and select the name of the custom toolbar you'd like to rename. 2 Right-click over the toolbar once more and select Customize > Rename [toolbar name]. 3 Type a fresh name for the toolbar. To delete a custom toolbar, proceed as follows: 1 Right-click over the toolbar and select the name of the custom toolbar you'd like to delete. 2 Right-click over the toolbar once more and select Customize > Remove [toolbar name].

TIP: There's no undo for adding or removing tools on a custom toolbar. When you're assembling an elaborate toolset, spin up a fresh custom toolbar derived from your current one between each major change and work from it. Should you slip up that way, you can fall back to the last toolbar you knew was good. Once the final toolbar looks exactly as you intend, you can circle back and clear out every one of the in-between custom toolbars you built along the way.

### Node Editor

At the core of Fusion sits the Node Editor, since this is where you assemble the tree of nodes behind each composition. Every node you drop into the node tree contributes one specific operation that yields a single effect—be that blurring the picture, tweaking color, laying down paint strokes, drawing and adding a mask, pulling a key, generating text, or merging two images into one.

The Node Editor displaying a node tree creating a composition It can help to picture each node as a layer in an effects stack, save that you're free to steer image data any which way to branch off and recombine parts of your composite in thoroughly nonlinear fashion. That makes intricate effects easy to assemble, and just as easy to follow, because the node tree works as a flowchart too, plainly laying out everything going on once you've learned how to read it.

### Adding Nodes to Your Composition

However you feel like working, there are several routes for bringing nodes out of the Effects Library into your composition. With most of these routes, when a single node is selected in the Node Editor, fresh nodes get tacked on after it automatically, but when nothing is selected or several nodes are, then fresh nodes arrive disconnected from everything else.

Methods of adding nodes include:

- Click a button in the toolbar.
- Open the Effects Library, track down the node you want in its category, and click once on

a node you'd like to add.

- Right-click a node and pick Insert Tool from the drop-down menu to drop it in after the

node you right-clicked. Or you can right-click the Node Editor's background and lean on that submenu to drop in a disconnected node.

- Hit Shift-Spacebar to bring up a Select Tool dialog, type letters matching the name of the node you're after, and press the Return key (or click OK) once it surfaces. After you've picked this route up, it'll likely turn into one of your go-to ways of adding nodes.

As long as you know its name, the Select Tool dialog turns up any node in a flash.

### Removing Nodes from Your Composition

Getting rid of nodes is just a matter of selecting one or more of them, then hitting the Delete or Backspace keys.

### Identifying Node Inputs and Node Outputs

Every node shows small colored connections ringing its edges. Inputs are shown by one or more arrows, while the square connection stands for the tool's processed output—of which there's never more than one. Hover the pointer over any of a node's inputs or its output and that input or output's name pops up in the Status bar right away. Hold there a few seconds longer and a floating tooltip shows the same name directly above the node.

### Node Editing Essentials

Each node carries inputs and outputs that get "wired together" through connections. Arrows stand for the inputs, marking how image data travels from one node onward to the next, with each node laying down its effect and passing the result (by way of the square output) along to the next node in the tree. This way, you can swiftly assemble intricate results out of a chain of fairly simple operations.

### Three nodes connected together

A single node's output can be wired into the inputs of several nodes (this is termed "branching").

A single node branching out to a pair, sending the image down two separate operations You can then merge images together by routing the output from several nodes into certain nodes such as the Merge node, which folds multiple inputs down into one output.

Two nodes being merged together into one to create a composite Out of the box, fresh nodes get laid out left to right in the Node Editor, yet they can equally run top to bottom, right to left, bottom to top, or every direction at once. Connections reorient themselves automatically across all four sides of each node, holding the tidiest possible look as you reshuffle other connected nodes.

A node may face whichever way you like; tracing the input arrows shows you how image data flows through.

### Navigating the Node Editor

As your Node tree grows, parts of it are bound to slip offscreen. Once a stretch of the node tree falls offscreen, a resizable Navigator pane shows up in the top-right corner. The Navigator is a scaled-down picture of the whole node tree that you can drag inside of to pan over to different parts of your composition in a hurry. You can resize the navigator with a handle down in the lower-left corner, and toggling the Navigator's visibility is done either by tapping the V key or by right-clicking the Node Editor and heading into the contextual menu's Options submenu.

The Navigator pane for accessing offscreen parameters or tools Other standard ways of panning and zooming about the Node Editor exist as well. Methods of navigating the Node Editor:

- Middle-click and drag to pan about the Node Editor.
- Hold Shift and Command down and drag the Node Editor to pan.
- Press the Middle and Left mouse buttons together and drag to resize the Node Editor.
- Hold the Command key down and spin your mouse's scroll control to resize the Node Editor.
- Right-click the Node Editor and pick an option from the Scale submenu of the

contextual menu.

- Press Command-1 to snap the Node Editor back to its default size.
- Drag two fingers across a track pad to pan.
- With the Command key held down, slide two fingers across a track pad to resize the Node Editor.

### Vertical Node Editor Layouts

Alternative Node View Layout presets found on the Fusion page let you stand the Node Editor up vertically, whether beside the Inspector or down the left edge of the screen. That can prove a real help while you're animating in the Spline Editor or Keyframes Editor. Once on the Fusion page, you can grab the layouts from Workspace > Layout Presets. Picking a vertical layout lets the node tree run top to bottom, opening up considerably more room down the screen's bottom portion where the Spline Editor or Keyframes Editor can live.

Here the Mid Flow Vertical layout preset is paired with the Vertical Flow direction setting. While you're on the vertical layouts, switching on the Flow > Build Direction > Vertical option in the Fusion settings makes every new Node tree build vertically, leaving the most possible room for Fusion's animation tools. You can then store alternative layouts built on these two vertical presets by way of the Workspace > Layout Presets submenu. Whenever you'd like to head back to the default horizontal Node Editor layout, just pick Workspace > Layout Presets > Fusion Presets > Default. These Layout options aren't on offer in Fusion Studio; even so, you can rely on the Floating Frame to place the Node Editor anywhere you please.

### Keeping Organized

While you work, keeping the node trees you build tidy matters a great deal toward a clear grasp of what's going on. Happily, the Fusion Node Editor hands you an assortment of methods and options to help with exactly that, sitting inside the Options and Arrange Tools submenus of the Node Editor contextual menu.

### Status Bar

Down in the lower-left corner of the Fusion window, the Status bar surfaces an assortment of current information about what you're selecting and what Fusion is up to. As an instance, hovering the pointer over a node shows details about that node in the Status bar. On top of that, the frame rate currently being hit appears the moment you kick off playback, and the share of the RAM cache in use stays on display at all times. Further information, updates, and warnings turn up in this area as you go. The Status bar beneath the Node Editor presenting details about whatever node sits under the pointer, alongside a popup box carrying still more pertinent info. Every so often the Status bar puts up a badge to tip you off that there's a message waiting in the console you might care about. That message could be a log, a script message, or an error. A notification that there's a message in the Console

### Effects Library

Fusion's Effects Library lays out every node and effect Fusion has on offer, third-party OFX plugins among them, if those are installed. When you're in DaVinci Resolve, Resolve FX turn up in the OFX category as well. Whereas the toolbar surfaces a good many of the most common nodes you'll reach for in any composite, the Effects Library holds every single tool Fusion offers, sorted by category, each node set to be dropped quickly into the Node Editor. Suffice it to say the Effects Library carries far, far more nodes than the toolbar does, covering a broad spread of purposes.

### The Effects Library with Tools open

### The Templates section of the Effects Library

The Effects Library's hierarchical category browser breaks into several sections according to whether you're in Fusion Studio or on the Fusion page within DaVinci Resolve. The Tools section sees the heaviest use, since it holds every node standing for an elemental image-processing operation in Fusion. Hover the pointer over a particular tool and a tool-tip explaining what it does appears at the bottom right of the DaVinci Resolve interface. The OpenFX section carries third-party plugins, and if you're on the Fusion page, it also carries ResolveFX, which ship with DaVinci Resolve. A third section, on view only while you're on the Fusion page in DaVinci Resolve, is the Templates section. An assortment of extra content fills that Template section: you'll find templates covering Lens Flares, Backgrounds, Generators, Particle Systems, plus Shaders, the latter meant for texturing 3D objects, along with yet more resources to draw on in your composites.

A button sitting at the far left of the UI toolbar switches the Effects Library's list between full height and half height.

### The Inspector

Over on the right side of the Fusion window sits the Inspector, a panel you use to show and work with the parameters of one or more selected nodes. Select a node in the Node Editor and its parameters and settings turn up in the Inspector.

The Inspector shows parameters from one or more selected nodes.

### The Modifier panel showing a Perturb modifier

### The Tools and Modifiers Panels

The Fusion Inspector splits into two panels. The Tools panel is the primary one, surfacing the parameters of selected nodes. The Modifiers panel shows optional add-ons to a tool's standard parameters. In the image below, a Perturb modifier has been attached to a parameter to lend that parameter random animation, and the controls in the Modifier panel let you tailor exactly what sort of randomness gets applied.

Other nodes put node-specific items here. For instance, Paint nodes present each brush stroke as its own set of controls in the Modifiers panel, on hand for further editing or animating.

### Parameter Header Controls

Sitting atop each node's controls in the Inspector, you'll find a cluster of controls.

### Common Inspector controls

Set Color: A pop-up menu letting you hand a node one of 16 colors, overriding the node's own color. Versions: Click Versions and another toolbar of six buttons appears. Each button can keep its own set of adjustments for that node, which you can use to bank several versions of an effect. Pin: The Inspector can also show, all at once, every parameter for the multiple nodes you've selected in the Node Editor. On top of that, sitting in the title bar of each node's parameters is a Pin button, which "pins" those parameters into the Inspector so they linger even once the node has been deselected—handy for key nodes you have to tweak while inspecting other nodes of your composition. Lock: Locks that node so nothing about it can be changed. Reset: Resets every parameter within that node.

### Parameter Tabs

A good many nodes lay out several tabs' worth of controls in the Inspector, shown as icons across the top of each node's parameter section. Click any tab to bring up that set of controls.

### Nodes with several tabs' worth of parameters

### Keyframes Editor

The Keyframes Editor presents every node in the current composition as a stack of layers inside a scaled-down timeline. The layer order barely matters, since it's the order and flow of connections in the node tree that drive the order of image-processing operations. The Keyframes Editor is what you reach for when trimming, extending, or sliding Loader, MediaIn, and effects nodes, or when fine-tuning keyframe timing—those keyframes sitting layered over each effect node until you open them out into their editable track.

Tuning the timing of clips, effects, and keyframes is the job of the Keyframes Editor.

### Keyframes Editor Control Summary

Up top, a row of zoom and framing controls lets you adjust the work area holding the layers.

By way of these controls you can work the Keyframes Editor view. Scaling the editor's size is handled through a Horizontal zoom control.

- A Zoom to Fit button sizes the full width of every layer to match how wide the Keyframes Editor currently is.
- A Zoom to Rect tool has you draw out a rectangle, marking a region of the Keyframes

Editor to zoom in on.

- A Sort pop-up menu offers a handful of ways to sort or filter the tracks.
- An Option menu opens the door to plenty of other approaches for filtering tracks and

steering which options show. For a time reference—and a spot to scrub the playhead through—there's a timeline ruler. Over at the left, each layer's name lives in a track header, which also carries the controls that govern that layer.

- A lock button keeps a given layer safe from being altered.
- Any node that's been keyframed carries a disclosure control; open it and a

keyframe track appears for every animated parameter. The actual editing area in the center shows all the layers and keyframe tracks the current composition holds. Down at the bottom-left, Time Stretch and Spreadsheet mode controls hand you further ways to work keyframes. Over at the bottom right, the Time/TOffset/TScale drop-down menu together with its value fields let you shift the position of selected keyframes by the numbers—whether absolutely, relatively, or according to how far they sit from the playhead.

### Adjusting Clip Timings

Each Loader or MediaIn node standing for a clip used in a composition shows up as a layer in this scaled-down timeline. You can edit a layer's In or Out points by setting the pointer over a segment's start or end and using the resize cursor to drag that point somewhere new. A layer can be slid by dragging it left or right, helping it sit in sync with how other pieces of your composition are timed. The Keyframes Editor likewise lets you adjust the timing of elements you've added straight from inside Fusion.

### Adjusting Effect Timings

Every effect node turns up as a layer too, the same as clips do. You can resize an effect layer's In and Out points, and slide the whole layer forward or back in time, exactly as with a Loader or MediaIn layers. Trim an effect layer shorter than the composition's duration and the effect cuts in at whichever frame the layer starts, then cuts out following that layer's last frame, just like a clip on a timeline.

### Adjusting Keyframe Timings

Once you've animated an effect by laying keyframes onto a parameter in the Inspector, the Keyframes Editor becomes the place to edit the keyframe timing with ease. By default, every keyframe placed on parameters within a given node's layer is stacked together into a single flat track laid across the top of that layer. To get at the keyframes for editing, click the disclosure control sitting to the left of any animated layer's name over in the track header; that opens out a keyframe track for each keyframed parameter held by that layer.

### Keyframe tracks exposed

### Keyframe Editing Essentials

Here's a brief rundown of keyframe editing methods to get you going. Methods of adjusting keyframes:

- Clicking a lone keyframe selects it.
- Dragging a bounding box across a run of keyframes selects the whole bunch.
- Dragging keyframes to the left or right shifts where they fall in time.
- Right-click one or more selected keyframes and the drop-down menu's commands let you alter keyframe interpolation, copy and paste keyframes, or even spawn brand-new ones.
- Command-drag one or more selected keyframes and you'll drag a copy of them off to a different spot in the keyframe track.

To reposition a keyframe by way of the toolbar, take one of these steps:

- Pick a keyframe, then key a fresh frame number into the Time Edit box.
- Out of the Time Editor pop-up choose T Offset, then with one or more keyframes selected, supply a frame offset.
- Out of the Time Editor pop-up choose T Scale, then with one or more keyframes selected, supply a multiplier that's tacked onto the current playhead frame position. As an instance, with the playhead on frame 10 and the keyframe on frame 30, supplying the TScale value of 2 lands the keyframe on frame 50. Since the gap between the playhead and the original keyframe is 20, (20 x 2) = 40, which then gets added onto the playhead position.

### Time Stretching Keyframes

Select a span of keyframes within a keyframe track and you can switch on the Time Stretch tool, which brings up a box for squeezing and stretching the whole span of keyframes against one another. The Time Stretcher reshapes the overall timing across a run of keyframes while holding on to the relative timing from each keyframe to the next. As an alternative, you can switch on Time Stretch and draw a bounding box around whichever keyframes you want to adjust to set up a time-stretching boundary that way. Click the Time Stretch tool a second time to switch it off.

### Time stretching keyframes

### The Keyframe Spreadsheet

Switch on the Spreadsheet and then click a layer's name in the keyframe track, and for each keyframe its numeric time position together with its value—or values, where the parameter is multi-dimensional—turn up as entries within the Spreadsheet's cells. Each column stands for one keyframe, while each row stands for a single aspect of every keyframe.

### Editing keyframes in the Spreadsheet

As an example, when you're animating a motion path, the "Key Frame" row reports the frame each keyframe lands on, and the "Path1Displacement" row reports the position along the path at each keyframe. Alter the Key Frame value of any keyframe and you'll shift that keyframe to a new frame of the Timeline.

### Spline Editor

The Spline Editor lays out a finer-grained space for editing the timing, value, and interpolation of keyframes. By way of control points at each keyframe joined up by splines (also known as curves), you can shape how animated values shift over time. The Spline Editor breaks into four main areas: the Zoom and Framing controls up top, the Parameter list off to the left, the Graph Editor in the center, and the toolbar along the bottom.

The Spline Editor breaks down into Zoom controls along the top, a Parameter list on the left, the Graph Editor, plus the toolbar.

### Spline Editor Control Summary

Up top, a row of Zoom and Framing controls lets you adjust the work area holding the curves.

- Scaling the editor's size is done with the vertical and horizontal zoom controls.
- A Zoom to Fit button brings the full width of every curve in line with how wide the Spline Editor currently is.
- A Zoom to Rect tool has you draw out a rectangle that marks a region of the Spline Editor to zoom in on.

For a time reference—plus a place to scrub the playhead along—there's a Timeline ruler. The Parameter list off to the left is where you settle which splines are on view in the Graph view. By default, the Parameter list presents every parameter of every node in a hierarchical list. Beside each name sit checkboxes that reveal or conceal the curves belonging to different keyframed parameters. Color controls let you tailor each spline's tint so splines stand out more easily in a crowded situation. The Graph view, which fills most of this panel, lays out the animation spline along two axes. Time runs along the horizontal axis, while the spline's value runs along the vertical axis. Selected control points report their values in the edit fields down at the bottom of the graph. Finally, the toolbar along the bottom of the Spline Editor offers controls for setting control point interpolation, spline looping, or picking Spline editing tools for various jobs.

### Choosing Which Parameters to Show

Before you set about editing splines to tailor or build animation, you'll need to pick which parameter's splines you mean to work on. To show every parameter in every node:

- Click the Splines Editor Option menu and pick Expose All Controls. Flip this control off again to return to whatever you'd been viewing beforehand.

To show splines for the currently selected node:

- Click the Splines Editor Option menu and pick Show Only Selected Tool.

### Essential Spline Editing

The Spline Editor is a deep, capable space for editing and retiming keyframes and splines, but the overview below will get you going with this tool for building and refining animation. To select one or more control points:

- Clicking any control point selects it.
- Command-click several control points to select all of them.
- Draw a bounding box round several control points and they get selected together as one group.

To edit control points and splines:

- Click at any spot along a spline to drop in a control point.
- Drag one or more selected control points to reshape the spline.
- Shift-drag a control point to pin its motion to the vertical or horizontal.

To edit Bézier curves:

- Pick any control point and its Bézier handles appear, ready to be dragged.
- Command-drag a Bézier handle and the angle joining the left and right handles snaps apart.

To delete control points:

- Pick one or more control points, then hit the Delete or Backspace key.

### Essential Spline Editing Tools and Modes
