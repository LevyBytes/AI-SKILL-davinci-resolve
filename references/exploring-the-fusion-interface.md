# Exploring The Fusion Interface (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Exploring the Fusion Interface

Here you'll get your bearings in the Fusion user interface, taking a brisk walk through which tools you have on hand, where various things live, and how the panels mesh so you can build and polish compositions inside this capable node-based environment.

### The Fusion User Interface

Reveal it all at once and Fusion breaks down into four main regions meant to speed your node-based compositing along. Up top sit the viewer(s), the work area runs along the bottom, the Inspector occupies the right, and the Effects Library is the region over on the left. On DaVinci Resolve's Fusion page, the Effects Library and the Media Pool share that space. Working in concert, all these panels let you layer on effects, paint away problems, build motion graphics or title sequences, or assemble elaborate 3D and multi-layered composites.

### The Fusion user interface shown completely

That said, Fusion needn't be so involved; honestly, you can get along just fine with only the viewer, Node Editor, and Inspector showing for a pared-down setup.

A pared-down arrangement of Fusion controls for day-to-day work

### The Work Area

Odds are the phrase “the work area” won't come up often, since people name the particular panels inside it that they're actually using. Even so, what we call the work area is the zone filling the lower half of the Fusion user interface, the place where you can bring up the three principal panels for assembling compositions and editing animations in Fusion. Those would be the Node Editor, the Keyframes Editor, and the Spline Editor. Out of the box the Node Editor greets you first and is the main space you'll work in, yet it can sit alongside the Spline Editor and Keyframes Editor whenever you need. To hand these three panels more horizontal room on your display, you can drop the Effects Library and Inspector into a half-height mode if it helps.

The work area with the Node Editor, the Spline Editor, and the Keyframes Editor on display

### Interface Toolbar

Across the very top of Fusion runs a toolbar whose buttons reveal and hide the various parts of the user interface (UI). Each labeled button tells you which UI part it shows or hides. On DaVinci Resolve's Fusion page, a right-click anywhere on this toolbar gives you the choice of showing the bar with its text labels or without them.

### The UI toolbar of the Fusion page

### The UI toolbar of Fusion Studio

These buttons are as follows, from left to right:

- Media Pool/Effects Library Full Height: Lets the space taken by the Media Pool (DaVinci Resolve only) and/or Effects Library stretch to your display's full height, handing you more room to browse while squeezing the Node Editor and viewer area narrower. In half-height, the Media Pool/Templates/Effects Library stay penned into the UI's upper half next to the viewers (only one can show at a time), leaving the Node Editor to span your display's whole width.
- Media Pool: (DaVinci Resolve only): Reveals and conceals the Media Pool, out of which you can drag more clips into the Node Editor to put them in your Fusion page composition.
- Effects Library: Brings up or hides the store of every node tool Fusion has on offer. From here a click on a node adds it after whichever node is selected in the Node Editor, or you can drag and drop nodes onto any part of the node tree you please.
- Clips: (DaVinci Resolve only): Brings up and closes the Thumbnail timeline, your means of moving through the program, making and managing several versions of compositions, and resetting the current composition.
- Nodes: Brings up and closes the Node Editor, where the building and editing of your compositions happens.
- Console (Fusion Studio only): The Console is a window showing the error, log, script, and input messages that can shed more light on whatever Fusion is up to. It's also the place to read FusionScript outputs or type FusionScripts in directly.
- Spline: Brings up and closes the Spline Editor, where you shape the curves that interpolate keyframe animations so you can tune and nail their timing. Every keyframed parameter is nested under the effect it belongs to, within a list off to the left.
- Keyframes: Brings up and closes the Keyframes Editor, which renders each clip and effects node in your Fusion composition as its own layer. The Keyframes Editor lets you edit and fine-tune the timing of keyframes laid onto the various effects in your composition. It also lets you shift the relative timing of clips brought into Fusion and trim their In and Out points. A spreadsheet can be revealed or hidden in which you numerically edit keyframe values for the effects you've selected.
- Metadata (DaVinci Resolve only): Conceals or reveals the Metadata Editor, your tool for reading and editing the available clip and project metadata attached to any piece of media inside a composite.
- Inspector: Reveals or conceals the Inspector, which presents every editable parameter and control tied to the nodes you've selected in the Node Editor. You can display the parameters of several nodes together, and even pin the parameters of nodes you want to keep editing so they stay visible even when those nodes aren't selected.
- Inspector Height: Lets you set the Inspector to half height (matching the viewer area) or full height (matching your entire display). Half height frees up more space for the Node Editor, Spline Editor, and/or Keyframes Editor, while full height lets you edit more node parameters at once or holds enough room to show several nodes' parameters together.

### Choosing Which Panel Has Focus

Any time you click somewhere on the Fusion interface with the pointer, or use a keyboard shortcut to “select” a given panel, you grant that panel of the user interface “focus.” A focused panel grabs certain keyboard shortcuts to act within itself rather than somewhere else in the interface. So you can readily tell which panel holds focus, a highlight shows up along the top edge of whichever one it is. In DaVinci Resolve, that highlight only appears once you've enabled “Show focus indicators in the User Interface,” a checkbox living under the User Preferences within its UI Settings panel.

The focus indicator running along the Media Pool's top edge, set beside a viewer that lacks focus

### Viewers

Across the top of the Fusion page the viewer area presents one or two viewers, a count governed by the Viewer button at the far right of the Viewer title bar. Any viewer can show the output of one node drawn from anywhere in the node tree, and you decide which node lands in which viewer. That makes it simple to drop different nodes into each viewer side by side for comparison. You might, for example, put a Keyer node in the left viewer and the final composite in the right, letting you watch the image you're tweaking and the finished result together.

With dual viewers you can edit an upstream node in one while watching how it plays out on the whole composition in the other. As a rule, each viewer renders the 2D nodes of your composition as a single image. When you're looking at a 3D node, though, you get the choice of switching that viewer to one of several 3D views. A perspective view hands you a movable stage on which to lay out the elements of the world you're building. A quad view, on the other hand, shows your composition from four angles, which makes arranging and editing objects and layers along the XYZ axes of your 3D space easier.

Sending a 3D node to a viewer brings up a Perspective view

TIP: While in Perspective view, holding down the middle and right mouse buttons and then dragging in the viewer swings the view around the center of the world. Every other way of navigating viewers behaves just as it normally does. Viewers come with a range of abilities for comparing and assessing images. This section runs through a brief rundown of those viewer abilities to get you going.

### Zooming and Panning into Viewers

A set of conventional techniques exists for zooming into and panning around viewers when you want a tighter look at things. The very same techniques apply to the Node Editor, Spline Editor, and Keyframes Editor. Ways to pan viewers:

- Hold middle-click and drag to move around the viewer.
- Keep Shift and Command held and drag the viewer to pan.
- Drag two fingers across a track pad to pan.

Ways to scale viewers:

- Click a viewer; from there the equals key (=) zooms you in, while the minus key (-) pulls you back out.
- Push the middle and left mouse buttons together and drag left or right to resize the viewer.
- Keep the Command key held and spin your pointer's scroll control to zoom the viewer in and out.
- Keep the middle mouse button held, then click the left mouse button to zoom in or the right button to zoom out. Each step scales by a set amount, centered where the cursor sits.
- Click a viewer and press Command-1 to size the viewer's image to 100 percent.
- Click a viewer and press Command-2 to size the viewer's image to 200 percent.
- Click a viewer and press F to snap the viewer's image back to fit the viewer.
- Click the Scale viewer menu and pick Fit or a percentage.
- Right-click a viewer and pick something from the contextual menu's Scale submenu. That includes a Custom Scale command letting you type your own scale percentage.
- Keep the Command key held while dragging two fingers on a track pad to zoom the viewer in and out.

Ways to spin 3D viewers:

- While in 3D Perspective view, hold the middle and right mouse button, then drag to whirl the stage around.
- While in 3D Perspective view, hold the Shift key and drag two fingers on a track pad to whirl the stage around.

### Loading Nodes Into Viewers

On your first visit to the Fusion page in DaVinci Resolve, viewer 2 typically holds the output of the present empty composition (the MediaOut1 node). In Dual-viewer mode, viewer 1 sits empty until you give a node to one of them. Over in Fusion Studio, neither viewer holds anything until you assign a node to one of them.

To put particular nodes into particular viewers:

- Rest the pointer on a node and click one of the two buttons that surface at its lower left.
- Click once to select a node, then press 1 (for the left viewer) or 2 (for the right viewer).
- Right-click a node and pick View On > None/Left View/Right View from the contextual menu.
- Right-click a node's control header in the Inspector and pick View On > None/Left View/ Right View from the contextual menu.
- Drag a node and let it drop over the viewer you want it in (a real boon for tablet users).

While a node is being viewed, a View Indicator button shows up at its lower left. It's the very control that appears whenever you hover the pointer over a node. Beyond telling you which nodes occupy which viewer, this control also reveals small round buttons for flipping between viewers.

The viewer assignment buttons along the bottom of nodes signal when those nodes are being viewed.

### Clearing Viewers

To wipe an image out of a viewer, click in the viewer so it goes active; a slim red highlight shows along the top of the active viewer. With it active, hit the ` (accent) key, which on U.S. keyboards usually sits just left of the 1 key. The quickest route to clearing every image from every viewer is to ensure no viewer is the active panel and then press the Tilde key. Another option is to select the node currently displayed in the viewer and press that viewer's number once more (1 or 2 as the case may be) to empty it.

### Viewer Controls

A row of buttons and pop-up menus in the viewer's title bar gives you a handful of fast ways to tailor what the viewer shows.

### Controls in the viewer title bar

- Zoom menu: Lets you push in on the viewer's image for a tighter look, or pull back to open up space around the frame's edges for rotoscoping or placing different layers. Pick Fit and the whole image is sized automatically to whatever room the viewer has.
- Split Wipe button and A/B Buffer menu: Using a viewer's A/B buffers, you really can load two nodes into one viewer: pick a buffer from the menu and load a node into the viewer. Switch on the Split Wipe button (press Forward Slash) and a split wipe appears between the two buffers, which you can slide left or right by the handle of the onscreen control, or spin

by dragging anywhere along the dividing line of that onscreen control. Or you can flip between each full-screen buffer to compare them (or to clear a split-screen) by pressing Comma (A buffer) and Period (B buffer).

- SubView type: (Not on offer in 3D viewers.) A click on the icon itself turns the “SubView” option you've picked on or off, while the menu is where you choose which SubView is active. The menu does one of two jobs. With ordinary 2D nodes on display, it opens up SubViews, viewer “accessories” living in a small pane that let you size up images in assorted ways. Among them are an Image Navigator (for getting around when zoomed deep into an image), the Magnifier, the 2D viewer (which gives you a miniature look at the image), plus a 3D Histogram scope, a Color Inspector, a Histogram scope, an Image Info tooltip, a Metadata tooltip, and either a Vectorscope or a Waveform scope. Hitting the Swap option (Shift-V) trades what's in the viewer for what's in the Accessory pane. With 3D nodes on display, this button instead grants you a second mini 3D viewer.
- Node name: Whatever node you're currently viewing has its name shown in the middle of the viewer's title bar.
- ROI controls: A click on the icon itself turns RoI (Region of Interest) limiting in the viewer on or off, while the menu is where you set the RoI's region. RoI marks out the part of the viewer whose pixels genuinely have to be refreshed. As a node renders, it overlaps the current RoI with the current Domain of Definition (DoD) to work out which pixels ought to change. With it on, you can place a rectangle that pens rendering to a small slice of the image, which can give performance a real lift when you're tackling very high resolution or complex compositions. Auto (the default) ties the region to whatever's on screen at the viewer's present zoom/pan level. Pick Set and you draw a custom region inside the frame by dragging a rectangle that starts at the viewer's size and resizes by dragging the corners or sides of the onscreen control. Pick Lock and the current RoI is frozen against changes. Pick Reset and the RoI snaps back to the whole viewer.
- Color controls: Lets you decide which color and/or image channels the viewer shows. A click on the icon itself flips between Color (RGB) and Alpha, the two things you most often want to see (pressing C or A flips between Color and Alpha as well). Open the menu and it lists every channel the node you're viewing can display, commonly RGB, Red, Green, Blue, and Alpha (reachable from the keyboard with R, G, B, or A). With certain media and nodes, further auxiliary channels can be viewed too, such as Z-depth, Object ID, Material ID, XYZ Normals, and the like.
- Viewer LUT: A click on the icon itself flips LUT (LookUp Table) display on or off, while the menu lets you pick which of the many available color space conversions to put on the viewer. The top entries offer Fusion controls you can customize through the Edit item at this menu's top. The rest of the menu lists all LUTs installed in the LUT directory for use in viewing.

By default in DaVinci Resolve, the Fusion page viewers present the image before any grading happens on the Color page, because the Fusion page sits ahead of the Color page in the DaVinci Resolve image processing pipeline. When your clips have been converted to linear color space for compositing, you'll want to composite and adjust the image against a normalized version that looks close to the eventual final. Switching on the LUT display lets you do exactly that as a preview, without baking color adjustments permanently into the image.

- Option menu: Inside this menu live assorted settings governing Fusion's viewers.

Snap to Pixel: As you draw or tweak a polyline mask or spline, the control points lock onto pixel positions. Show Controls: Flips on or off whatever onscreen controls belong to the node you've got selected. Region: Holds all the settings for the viewer's Region of Interest.

Smooth Resize: This setting applies a gentler bilinear interpolated resizing approach as you zoom into a viewer's image; without it, scaling falls back on the nearest neighbor method and shows obvious aliasing artifacts. The nearest neighbor approach, though, proves handier for zooming to the pixel level, since nothing gets interpolated. Show Square Pixels: Steps over the automatic aspect correction when you work with formats whose pixels aren't square. Checker Underlay: Flips on a checkerboard underlay that makes transparent areas easy to spot. Normalized Color Range: Lets you see brightness values lying beyond the usual viewing range, which is especially handy with floating-point images or auxiliary channels. Gain/Gamma: Brings out a plain pair of Gain and Gamma sliders for adjusting the viewer's brightness. 360 View: Serves to correctly show spherical imagery across a range of formats you pick from this submenu. Stereo: Serves to correctly show stereoscopic imagery across a range of formats you pick from this submenu.

### Time Ruler and Transport Controls

Sitting just below the viewer area, the Time Ruler keys off the composition's overall duration. What it stands for hinges on the Fusion version you're running:

- For DaVinci Resolve users, the span shown in the Time Ruler range follows whatever is selected at the moment in the Edit or Cut page timeline.
- In Fusion Studio, the Time Ruler follows the Global Start and End values set under Fusion Studio Preferences > Defaults.

The transport controls beneath the Time Ruler bring together playback controls, audio monitoring, and number fields for the composition duration and playback range. Further controls switch on motion blur and proxy settings.

### Time Ruler Controls in the Fusion Page

With a single clip selected in the Edit or Cut page Timeline, the global range the Time Ruler displays reflects that clip's full source duration. The playhead can't travel past the global range. Those yellow lines, known as the render range, pin down the clip's current In and Out points and mark the only frames the Fusion page shows. Everything beyond that range makes up the unused head and tail handles of the source clip.

The Time Ruler laying out a clip's ranges in the Timeline through yellow marks (with the playhead in red) Should you have made a Fusion clip or a compound clip, the “working range” then mirrors that clip's whole duration.

The Time Ruler laying out a Fusion clip's ranges in the Timeline Render Range The render range fixes which frames the Fusion page shows and which feed interactive playback, disk caches, and previews. Frames lying past the default render range stay hidden on the Fusion page and go neither rendered nor played. You're free to alter the render range's length for preview and playback alone. Shortening or lengthening that range does nothing to trim the clip in the Edit or Cut page Timelines. To change the render range in the Time Ruler, do one of these:

- Keep the Command key held and drag a fresh range inside the Time Ruler.
- Drag either the starting or ending yellow line to shift where the range begins or ends.
- Right-click inside the Time Ruler and pick Set Render Range from the contextual menu.
- Type fresh ranges into the Range In and Out fields left of the transport controls.
- Drag a node out of the Node Editor onto the Time Ruler to match the range to that node's duration.

To send the render range back to the timeline clip's In and Out points, do one of these.

- Right-click inside the Time Ruler and pick Auto Render Range.
- Step back to the Edit or Cut page, then come back to the Fusion page.

### Time Ruler Controls in Fusion Studio

Sitting under the viewer area, the Time Ruler lays out two separate frame ranges: one spanning the whole composition, termed the global range, and another termed the render range, which dictates what gets rendered and what gets cached in memory for previews. The global start and end range fills the entire Time Ruler and sets a composition's total duration. The playhead can't be moved past the global range.

The Time Ruler showing a clip's ranges in the Timeline by way of yellow marks (the playhead rendered red) Global Start and End Range This range amounts to nothing more than the current composition's total duration. To change the global range, do one of these:

- To set the global range that every new composition starts with, macOS users choose Fusion Studio > Preferences, while on Windows or Linux you go to File > Preferences. Over in the Global and Default Settings panel, type a fresh range into the Global range fields.
- To set the Global range for the current composition, type a fresh range into the Global Start and End fields left of the transport controls.
- Dragging a node out of the Node Editor onto the Time Ruler automatically pins the Global and Render Range to the node's extent.

### Render Range

The render range sets which frames feed interactive playback, disk caches, and previews. Frames beyond the render range go neither rendered nor played, though you can still drag the playhead onto them to view those unused frames. When you want to preview or render a particular stretch of a composition, several ways exist to adjust the render range. To set the render range in the Time Ruler, do one of these:

- Keep the Command key held and drag a fresh range inside the Time Ruler.
- Right-click inside the Time Ruler and pick Set Render Range from the contextual menu to base the Render Range on the selected Node's duration.
- Type fresh ranges into the Range In and Out fields left of the transport controls.
- Drag a node out of the Node Editor onto the Time Ruler to match the range to that node's duration.

### The Playhead

A red playhead in the Time Ruler points to the frame you're currently viewing. Click anywhere in the Time Ruler and the playhead leaps to that frame; drag inside the Time Ruler and the playhead moves along within the available duration of the clip or composition.

### Zoom and Scroll Bar

A gray scroll bar with two handles lets you zoom into whatever range the Time Ruler shows, which helps when a very large Global range leaves the Render range as just a thin sliver in the Time Ruler. Dragging this bar's left or right handle zooms against the opposite handle, widening each displayed frame. After you've zoomed in, sliding the scroll bar left or right moves you across the composition. TIP: With the middle mouse button held down, a drag inside the Time Ruler scrolls the visible range.

### Transport Controls in the Fusion Page

On DaVinci Resolve's Fusion page, the Transport Controls gather buttons for driving playback plus time fields, those on the left for setting the render range and those on the right for the current time. The right-click menu holds extra controls.

### Controlling Playback

Beneath the Time Ruler on the Fusion page sit six transport controls. They run as follows: Composition First Frame and Play Reverse, then Stop, followed by Play Forward, and finally Composition Last Frame plus Loop.

### The Fusion page controls for playback

### Navigation Shortcuts

Plenty of the usual transport control keyboard shortcuts you already know carry over into Fusion, while a few answer to Fusion's own particular needs. To shift the playhead along the Time Ruler from the keyboard, do one of these:
