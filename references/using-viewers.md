# Using Viewers (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using Viewers

This chapter walks through how you work with viewers in Fusion: putting onscreen controls and toolbars to use, building groups and subviews, handling viewer Lookup Tables (LUTs), operating the 3D viewer, and configuring viewer preferences along with options.

### Viewer Overview

Fusion's viewers present the current frame of the current composition in numerous ways, helping you watch your progress and judge the end result of your compositing craft. While viewers present 2D images, they're equally able to present a 3D environment by way of a 3D View, along with a dedicated Quad viewer that helps you work in three dimensions to good effect.

Side-by-side dual viewers, a 3D viewer at left and a 2D viewer at right On top of that, you can surface "subviews" such as color inspectors, magnifiers, waveforms, histograms, and vectorscopes, all to help you study the image as you work.

Viewer carrying a 3D Histogram subview up in its top-left corner

### Single vs. Dual Viewers

Out of the box, a pair of viewers sit side by side along the top of the window. That said, the Single/Dual Viewer button flips you between showing one viewer or showing two viewers laid out side by side.

### The Single/Dual Viewer toggle button

### Floating Viewers in Fusion Studio

On top of the dual views above the Node Editor, Fusion Studio lets you call up any number of floating viewers. These floating viewers work wonderfully for getting the most out of a dual monitor setup. You can also switch floating viewers into full-screen mode to squeeze the most from your screen real estate. To spawn a fresh floating display view, pick Window > New View from the menu bar atop the screen. Should you need it, the new view's position and configuration can be stored in the layout preferences.

### Video Output

In DaVinci Resolve or Fusion Studio, where Blackmagic video hardware sits in the machine, you can pick a node to preview straight on that display. Video output won't let you work onscreen controls like center crosshairs or spline control points, yet it proves invaluable for judging your composition through the output format and for gauging image accuracy on a properly calibrated display. You configure the video hardware from the DaVinci Resolve and Fusion Studio preferences.

### Clean Feed

Running DaVinci Resolve across dual computer monitors, you can throw a full-screen viewer onto the secondary monitor from the Fusion page. That puts a third view indicator button beneath every node, governing what shows up on the second display. To switch this monitor on, confirm Dual Screen is off beneath the Workspace menu, then choose Workspace > Video Clean Feed and, from the submenu, point it at your second computer display.

### Loading Nodes into Viewers

When you first launch each application, the Fusion page in DaVinci Resolve and the one in Fusion Studio present different things. Opening the Fusion page for the first time, you'll usually see the output of the current empty composition (the MediaOut1 node) showing in viewer 2. While in dual-viewer mode, viewer 1 stays empty until you hand a node to one of them. Over in Fusion Studio, since no nodes exist as you start a fresh comp, the viewers show nothing. To load specific nodes into specific viewers, do one of the following:

- Hover the pointer over a node, then click one of the two buttons that surface at the node's bottom-left.
- Click once to select a node, then press 1 (for the left viewer) or 2 (for the right viewer).
- Right-click a node and pick View On > None/Left View/Right View out of the contextual menu.
- Right-click a node's control header in the Inspector, then pick View On > None/Left View/ Right View out of the contextual menu.
- Drag a node and drop it onto whichever viewer you want it loaded into (tablet users will love this one).

While a node is on view, a View Indicator button shows up at its bottom left. It's the very same control that appears when you hover the pointer over a node. Beyond telling you which nodes sit in which viewer, these controls also surface tiny round buttons for switching which viewer a node lands in.

Viewer assignment buttons at a node's bottom left flag when it's on view, and whichever dot lights up tells you which viewer holds that node.

### Clearing Viewers

To wipe an image out of a viewer, click inside the viewer to make it active; a light purple outline frames the active panel. With that viewer active, press the ` (accent) key. On U.S. keyboards you'll usually find this key just left of the 1 key. The quickest route to clearing every image from every viewer is to see that none of the viewers is the active panel, then press the accent key.

### Position and Layout

Over in Fusion Studio, whenever you resize and rework a composition's viewer layout, that arrangement always saves alongside the composition. So every time you reopen the composition, its size and layout come back. To stop this from happening, switch off the Recall Layout checkbox in the Fusion Global Layout preferences. Should you want every new composition to open with a given viewer layout, set up the layout of the two primary viewers, then hit the Grab Document Layout button in the Fusion Global Layout preferences to lock that layout in for any new compositions. To preserve the position and size of floating viewers, you reach for the Grab Program Layout button. And lastly, to have the floating viewers open by themselves whenever you launch Fusion, switch on the Create Floating Views checkbox.

### The Viewer Divider

You can shift the relative sizes of the left and right viewers by way of the horizontal viewer divider running between them. Drag the viewer divider to grow or shrink how much room one viewer takes. Its neighbor adjusts to make room for the new layout. To set how much vertical room both viewers get, drag the horizontal scrollbar sitting between the viewers and the work area beneath them.

### The viewer divider bar

### Zooming and Panning into Viewers

There's a standard set of techniques for zooming into and panning around viewers whenever you want a closer look. These same techniques carry over to the Node Editor, Spline Editor, and Keyframes Editor. Methods of panning viewers:

- Middle-click and drag to pan around the viewer.
- Hold down Shift and Command, then drag the viewer to pan.
- Drag two fingers across a track pad to pan.

Methods of scaling viewers:

- Click a viewer, then press the Equals key (=) to zoom in or the Minus key (-) to zoom out.
- Hold the middle and left mouse buttons together, dragging left or right to resize the viewer.
- Hold down the Command key and work your pointer's scroll control to resize the viewer.
- Hold down the Command key and drag two fingers across a track pad to resize the viewer.
- Hold the middle mouse button down, then click the left mouse button to zoom in, or the right button to zoom out. The scaling moves by a fixed amount, centered where the cursor sits.
- Click a viewer, then press Command-1 to size the image in the viewer to 100 percent.
- Click a viewer, then press Command-2 to size the image in the viewer to 200 percent.
- Click a viewer, then press Command-F or Command-1 to snap the image in the viewer back to fit the viewer.
- Click the Scale Viewer menu and pick Fit or a percentage.
- Right-click a viewer and pick an option out of the contextual menu's Scale submenu.

Among these sits a Custom Scale command, which lets you key in a scale percentage of your own Methods of spinning 3D viewers:

- While in 3D Perspective view, hold down both the middle mouse button and the right mouse button, then drag to spin the stage around.

### Custom Guides in Fusion Viewers

The Fusion page viewers let you build custom guides of your own. With them you can fully tailor and lay down specific geographic spots in the frame, then have the image snap to those spots during other operations. You can build Guides, which are colored lines crossing the frame either horizontally or vertically. Guides serve as overlay tools for tuning your video position, and they show up in the viewer alone, never in your final project output.

### A Fusion Viewer with Show Guides enabled

To bring up Guides, right-click in the viewer and pick Guides > Show Guides, or else press Command-G. To Show and Create a Guide Line: 1 Switch on the Guides by right-clicking in the viewer and picking > Guides > On (Command-G). Up comes a default batch of guidelines you can click and drag through the frame. 2 Build a fresh Guide by right-clicking in the viewer and picking Guides > Add Resolve Guide. Adding a Resolve Guide makes the guideline show up on other pages within DaVinci Resolve.

3 Within the Add Guide dialog, pick the position and orientation you'd like the new guide to take, then click OK. Units: Pick either pixel or percentage as the metric governing where the line goes. Position: Key in a value marking where in the frame you want the guideline to cross. Later on you can likewise drag this line about in the viewer, placing it by eye. Orientation: Pick either a horizontal or a vertical orientation for the line.

### The Add Guide dialog

To Modify Delete, or Lock a Guide Line:

- Click and Drag the line wherever you like in the viewer.
- Delete a line by right-clicking it in the viewer and picking Remove Guide.
- Adjust an existing line's position and orientation by right-clicking it in the viewer and picking Edit Guide.
- To guard against accidental movement, lock Guides down by right-clicking the line and picking Lock Guide, or lock every guide together by right-clicking in the viewer and picking Guides > Lock All Resolve Guides.

### Snapping to Guide Lines

Right-click in the viewer and pick Guides > Snap to Guides to switch snapping on. As you move the clip around the frame with the Fusion tools, the image edge snaps to a guideline on its own each time it nears one.

### Flipbook Previews

As your compositions grow more involved, and you find you need to preview particular branches of your node tree to gauge how the various details you're working on are shaping up, it can pay to build targeted RAM previews at assorted quality levels right inside the viewer through a RAM Flipbook. A RAM Flipbook Preview is a preview render that lives wholly within RAM, letting you render a node's output at varying quality levels for fast processing so you can watch a real-time preview.

### Creating Flipbook Previews

Building a Flipbook Preview goes fairly quickly, provided you know where to look.

To create a Flipbook Preview: 1 Pick the node in your node tree you'd like to preview by doing one of the following:

- Hold the Option key down while dragging a node into the viewer.
- Right-click a node and pick an option out of the Create/Play Preview submenu in the

contextual menu. 2 Once the Preview Render dialog opens, pick the quality, resolution, and motion blur settings you'd like the Flipbook Preview to use.

The Flipbook Preview Render dialog 3 With your settings chosen, click Start Render. The Time Ruler's current frame range renders using the settings you picked, and the outcome shows up in whichever viewer you selected or dragged into. After you've built a Flipbook Preview inside a given viewer, a right-click on that viewer surfaces Flipbook-specific commands and options: Play, Loop, or Ping-Pong the Flipbook; throw it Full Screen; Show Frame Numbers; or do away with it. TIP: To build a Flipbook Preview while skipping the Render Settings dialog, relying instead on either the default setting or whatever was last chosen, hold Shift-Option down as you drag a node into the viewer. The Settings dialog stays away, and the preview starts rendering immediately.

### Playing Flipbook Previews

Once the Flipbook Preview sits in a viewer, or is opened full-screen, both the mouse and the keyboard let you play it back or scrub through it. For mouse-driven Flipbook playback, here's the move:

- Double-click in the viewer to start playback.

For mouse-driven scrubbing through a Flipbook, here's the move:

- With the right mouse button held down, drag to the left or right and the frames scrub past.

For keyboard-driven Flipbook playback, take one of these routes:

- Press the Spacebar to start or stop playback.
- Hold Shift and press the Spacebar to play in reverse.

For keyboard-driven frame-by-frame scrubbing through a Flipbook, take one of these routes:

- Press the Left or Right Arrow keys to step to the previous or next frame.
- Hold Shift and press the Left or Right Arrow keys to leap back or ahead 10 frames.
- Press Command-Left Arrow to leap to the first frame.
- Press Command-Right Arrow to leap to the last frame.

TIP: These mouse and keyboard shortcuts function in full-screen mode too.

### Removing Flipbook Previews

Having built a Flipbook Preview, you'll want to know how to clear it out of RAM. To do away with a Flipbook you've created: Right-click inside a viewer that holds a Flipbook Preview, then pick Remove Preview.

### Flipbook Preview Render Settings

This section runs through every setting on offer for rendering Flipbook Previews into RAM.

### Settings

The Settings section of the Preview Render dialog carries three buttons that govern your Flipbook Preview's overall quality and look. Those buttons also weigh heavily on render times. HiQ: Switched on, this setting renders the preview at full image quality. To see how a node's final output would appear, you'd switch the HiQ setting on. While putting together a rough preview to test animation, you can spare yourself time by switching it off. MB: The MB here stands for Motion Blur. Switched on, this setting renders with motion blur in place wherever any node is set to produce motion blur. While building a rough preview where the motion blur on animated elements doesn't matter to you, you can spare yourself time by switching it off. Some: With Some switched on, only the nodes truly needed to produce the image of the node you're previewing get rendered.

### Size

Because RAM Flipbook Previews draw on RAM, it helps to know how many frames you can render into RAM before memory runs out. The Flipbook Preview dialog works out the memory currently free and shows how many frames will fit into RAM. Should your machine carry little RAM and you can't render the full range of frames you'd like, you can opt to drop the resolution to a setting that strikes the best quality/duration ratio for your preview.

### Network

Network rendering is on offer in Fusion Studio alone. For more on network rendering, turn to Chapter 66, "Rendering Using Saver Nodes," within the DaVinci Resolve Reference Manual or Chapter 4 of the Fusion Reference Manual.

### Shoot On

There are times you won't want every single frame rendered, but rather every second, third, or fourth frame, to trim render time and get feedback faster. The Step parameter lets you set the interval at which frames get rendered.

### Frame Range

This field starts out at the current Render Range In/Out set in the Time Ruler, fixing the first and last frames for rendering. You can adjust the range to render more frames or fewer.

### Configurations

Having built a preview configuration worth keeping, you can store it for later by clicking the Add button, naming it, and clicking OK.

### Updating a Preview

This option suits the hands-on, frame-by-frame business of rotoscoping and painting. On a preview in the viewer, right-click and pick Update from its contextual menu. While it's active, any frames you change on the previewed node refresh on their own within the preview's playback. That lets you hold the RAM in reserve for playback. You can leave it running on a loop or ping-pong while you carry on in another viewer.

### Onscreen Controls

When you're adjusting images, the Control Panel hands you very precise numerical values, yet now and then placing an element visually through onscreen controls gets you where you're headed with less fiddling.

### The Angle preview control

The viewers present onscreen controls for working the parameters of whichever node is currently selected. Crosshairs, angle indicators, polylines, and paint strokes count among the common onscreen controls. Each of these controls can be worked straight in the viewer with the mouse or keyboard. Which controls the viewers present hinges on which nodes are selected, not on the node shown in the viewer. As an instance, you can easily view a downstream blur while working the controls for a selected polygon mask or merge. With several nodes selected, the controls for every selected node show up all at once.

### Showing and Hiding Onscreen Controls

A viewer's onscreen controls can be tucked away so they don't get in the way of viewing the image. To flip the visibility of onscreen controls, do one of the following:

- Click a viewer's Option menu and pick Show Controls to flip the controls on or off.
- Right-click in a viewer and pick Options > Show Controls from the contextual menu.
- Select a viewer and press Command-K.

### Enabling/Disabling Onscreen Controls in Specific Nodes

Certain nodes, masks among them, let you switch their onscreen controls off node by node, given that you often lean on several Polygon nodes to arrange and animate masks.

You can switch certain nodes, the Polygon node among them, off on a per-node basis.

### Making Fine Adjustments to Onscreen Controls

To pair the visual steer of onscreen controls with the precision of the Inspector, you can call on assorted keyboard modifiers.

- The Up and Down Arrow keys serve to nudge an onscreen control's vertical position in small steps.
- Holding the Command key down as you work the Up and Down Arrow keys shrinks each step's scale tenfold. Holding Shift grows each step's scale tenfold.

### Toolbars

The viewer carries two toolbars: a viewer toolbar, which sits at the top of every viewer and hands you control over what that viewer shows, plus an optional node toolbar appearing beneath it that hands you contextual controls keyed to whichever node you've selected in the Node Editor.

### Viewer Toolbar

A viewer toolbar stretches across the top of every viewer, opening up many of the most frequently used viewer-related settings while also signaling the state of many of the most important ones. The bulk of the menus and buttons on this toolbar get a full treatment across this chapter.

### The viewer toolbar

### Node Toolbars

Alongside the viewer toolbar, a node toolbar shows up beneath it, at the top of the viewer display area, any time you select a node that surfaces special nodes. Among the nodes that surface a toolbar are the text, masks, paths, paint strokes, and the 3D environment.

### The node toolbar shown for the Paint node

### Customizing the Node Toolbar

To resize the buttons sitting in the Node toolbar, or to switch on text names for each node, right-click any empty patch of the toolbar and pick fresh settings out of the Icon Size and Button Style submenus in the contextual menu.

### The contextual menu for the node toolbar

### A/B Buffers

Every viewer carries two buffers, each able to hold images from different nodes, which makes comparing two separate nodes within one viewer simple, whether by flipping between buffers or through an adjustable split-wipe. You can treat each buffer as a full, independent viewer living inside the same viewer pane. The A buffer always shows by default, so the first node you load into a viewer lands its image in the A buffer.

### Flipping between Buffers

Moving from one buffer to the other is simple, whether to view a different image while keeping another close at hand, or to flip between the original image and the affected one for comparison. To switch between buffers, do one of the following:

- Select a viewer, then press comma (,) for the A buffer or period (.) for the B buffer.
- Click the Buffer menu and pick either Switch to A View or Switch to B View.

### The Buffer menu lets you switch between buffers

TIP: Each buffer can carry its own display settings — say, showing different channels or different viewing LUTs, whether applied to different nodes or to two buffered versions of one node.

### Split Wipes between Buffers

You can also wipe across both buffers, which gives you a more direct way to compare. To wipe between buffers, take one of these routes: 1 Get ready to wipe across two images, either by placing separate nodes into each buffer or by placing one node — carrying differing viewer options — into each buffer. 2 To flip the split wipe on or off, pick either of these: a) Hit the Switch to Split Wipe View button. b) Tap Forward Slash (/). 3 To tune the wipe, pick from among these: a) Move the wipe's center by dragging the wipe divider's center handle. b) Hold Command-Option and click somewhere in the viewer, which snaps the wipe divider over to that spot. c) Change the wipe's angle by dragging the wipe divider. With the Shift key held while you drag the wipe divider, it snaps to the closest 45-degree angle. d) When you pan or zoom the viewer, both buffers pan and zoom together.

4 (Optional) To swap the image shown on that side of the split, you can drag fresh nodes onto either half of the viewer. 5 To switch the wipe off, click the Switch to Split Wipe View button once more (or press /).

The wipe divider is adjustable for comparing different stretches of the A and B images Even while wiping, you can pick different display channels, view LUTs, or other display options per buffer by clicking the half of the wipe you'd like to change, then choosing the options you want that buffer to use. That makes comparing different channels, LUTs, or other viewer settings simple as you wipe across one image, or across different images.

### Moving the Wipe Divider

Every so often you'll have zoomed in or panned so far off the viewer divider that it's slipped out of view in the viewer. Holding Command-Option down and clicking anywhere in the image makes the viewer divider jump to where the pointer currently sits.

### Subviews

A subview is a "mini" viewer turning up inside the main viewer. As a rule, a subview serves to show different information about the image.

### The Subview menu with the Histogram subview displayed

As an instance, you can view the RGB channels in the main viewer while the alpha channel shows in a subview. For the most part the subview is a fully working miniature viewer, carrying its own contextual menu and options. It answers to the same keyboard shortcuts and navigation controls any other viewer does. Even so, a handful of view types are meant for the subview alone, among them the Navigator, Magnifier, Color Inspector, and Image Info.

### Showing and Hiding Subviews

Subviews come up and go away easily. To switch on whichever subview is currently selected in a viewer's Subview menu, do one of the following:

- Click the Subview button in the View toolbar.
- Choose Views > Subview > Enabled from the contextual menu.
- Click a viewer, and press the V key.

### The Subview button in the viewer toolbar

### Changing the Subview Type

The Subview button switches the subview on and off, and it usually brings up whichever subview you last chose. You can change this whenever you like.

To change which subview type is displayed, do one of the following:

- Click the little arrow to the right of the Subview button to open its menu, then pick whichever subview you want.
- Right-click inside a subview to call up the subview's contextual menu. Both the Subview drop-down menu and the contextual menu list every subview type on offer. Once you pick an option from the list, that view shows in the subview, and the Subview button brings it up or tucks it away as you please.

### Swapping the Subview with the Main View

</content>
