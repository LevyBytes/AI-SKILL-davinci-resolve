# Using Viewers (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

For certain subview types, you can trade what the main viewer shows with what the subview shows. Some types, though — the Color Inspector and Magnifier among them — only function in the subview, so for those the swap simply won’t happen. To trade the subview’s contents with the main view, take one of these actions:

- Press Shift-V.
- In a viewer, right-click and pick Views > SubView > Swap off the contextual menu.

### Viewer and Subview Types

A viewer can present many kinds of information about the image, yet not every view type is on hand at any given moment. The 3D Viewer, for example, isn’t offered for a 2D node, and several of the measurement viewers exist only as subviews. What follows is detailed coverage of the various view types. Navigator The Navigator is a subview-only view. It gives a compact overview of the whole image, with a rectangle marking the slice of the image presently visible in the main viewer. That comes in handy when you’ve zoomed into an image in the main view.

The Navigator subview for panning the image while zoomed in

### Magnifier

The Magnifier works in a subview only. It presents an enlarged view of the pixels sitting beneath the cursor over in the main viewer.

The Magnifier subview, showing an enlarged rendering of the image

The subview serving as a second viewer A 3D Image Viewer placed in a subview

2D Viewer The default view type for displaying images is the 2D Viewer. As a subview, it can show a different node than the one in the main viewer, which you set by dragging that node into the subview. It is the only subview type that isn’t merely an alternate view of the main viewer’s node. 3D Image Viewer You get the 3D Image Viewer whenever a node from the 3D category is being viewed. Image Info The Image Info view exists only as a subview. Its tab places a horizontal bar along the top of the image carrying details about the viewed image’s frame size, pixel aspect, and color depth.

The Image Info subview, used to read size, pixel aspect, and color depth details The Color Inspector subview, used to assess the colors in an image

### Color Inspector

The Color Inspector works in a subview only. It reports on the color channels of whichever pixel sits beneath the cursor. Every channel present is shown, including auxiliary ones such as Z buffer, XYZ normals, and UV mapping channels.

The 3D Histogram Viewer type, used to assess out-of-range colors The Histogram Viewer type, used to assess an image’s contrast and color cast The Metadata subview, used to read embedded metadata

3D Histogram The more sophisticated 3D Histogram Viewer plots an image’s color distribution inside a 3D cube. A benefit of a 3D Histogram is its faithful depiction of the out-of-range colors that frequently turn up in floating-point and high-dynamic-range images. It can likewise be used to inspect vector images such as position, normal, velocity, and the like. To rotate within a 3D Histogram, do one of the following:

- With the Option key held, drag to the left or right while using the middle mouse button.
- Keep both the middle and right mouse buttons pressed as you drag.

Histogram The Histogram Viewer is an analysis node useful for spotting trouble with an image’s contrast and dynamic range. Its graph plots the frequency distribution of the image’s colors, out-of-range colors in floating-point images included. Colors run along the horizontal axis from shadows toward highlights, while the vertical axis counts how many of the image’s pixels land at each level. The Histogram Viewer can also show gradient information. Gradients can be produced with the From Image and Perturb modifiers; to view one represented within a histogram, drag that modifier’s title bar onto the viewer. Metadata Exactly how much this subview shows hinges entirely on how much metadata your image carries. Most Loaders supply the image’s color space and file path, and far more can appear when the image holds it.

### Vectorscope

The Vectorscope Viewer mimics the behavior of a particular kind of video test instrument, showing a circular graph that aids in visualizing the strength of chrominance signals.

The Vectorscope Viewer type for evaluating chrominance in an image

### Waveform

The Waveform Viewer mimics the behavior of a particular kind of video test instrument, showing a line or bar graph that aids in visualizing a broadcast signal’s voltage or luminance.

The Waveform Viewer type for evaluating luminance in an image

### Viewing Selective Channels

In compositing you work just as often with an image’s individual color components or channels as you do with the whole image’s full RGB color. Both the viewers and the subviews can isolate and display the color, alpha, depth channels, and even the auxiliary channels that comprise the image.

### Viewing Color Channels

The full RGB color channel appears by default, but the channel on display can be changed three ways: through the Channel toolbar button, through the viewer’s contextual menu, or via keyboard shortcuts. To switch between the RGB and alpha channels in whichever viewer is active:

- In the viewer toolbar, click the Color button to flip between full RGB color and that image’s alpha channel.

The Channel toolbar button for switching between color, alpha, and depth channels

To toggle the channel that’s displayed in the active viewer:

- Click the arrow just right of the Color button to pick one specific channel to view from the current image’s list of available channels.
- Click the viewer you intend to toggle, then hit one of these keyboard shortcuts;

C

### Full RGB color display

R

### Display red channel

G

### Display green channel

B

### Display blue channel

A

### Display alpha channel

Z

### Display Z-buffer channel

### Viewing Auxiliary Channels

Beyond the RGBA and Z channels they handle through keyboard shortcuts, the viewers can show other channels too. File formats like OpenEXR frequently carry auxiliary image data that opens up extra control and compositing options when you work with rendered 3D images. To pull auxiliary image data into a viewer, either click the arrow beside the RGB button on its right to open the drop-down menu, or right-click in the viewer and select an option from the contextual menu’s Channels submenu.

### Viewing Multilayer Files (Studio Version Only)

Fusion can deftly manage multilayer image workflows, supporting EXR, Stereoscopic 3D, and PSD assets. On the Fusion viewers you can view a list of layers and interact with the layers of each node through the Settings tab in the Inspector. Because this layer structure persists across the whole toolset, you can confine a tool to a single layer while the remaining layers pass through untouched.

### Viewer

With a multilayer file loaded, you can preview individual layers in the Viewer by choosing a layer from the dropdown list. A file lacking layer support offers only a ‘default’ entry in the drop-down menu.

Choosing only the Asteroids layer of a multilayer file for viewing, by way of the Viewer’s Layer drop-down

### The 3D Viewer

Assembling a composite in 3D space calls for something different than ordinary 2D compositing. Whenever a node from the 3D category — or certain particle systems — is selected, the scene is shown in a 3D Viewer. That 3D Viewer renders a representation of the composite inside a genuine GPU-accelerated 3D environment. For further detail on the 3D controls, consult Chapter 85, “3D Compositing Basics,” within the DaVinci Resolve Reference Manual, or Chapter 25 of the Fusion Reference Manual.

### Panning, Scaling, and Rotating a 3D Viewer

Navigation in the 3D Viewer largely mirrors how you navigate the 2D Viewer. The same controls handle panning and zooming even though you’re now moving through a 3D space. When you view a 3D scene, however, panning shifts the viewpoint and therefore the center point used for scaling and rotation as well. Pairing panning with rotation lets you take the viewpoint anywhere in the scene. One other minor difference is that a 3D scene has a lower scale limit. Keep zooming past that limit and the viewpoint instead moves forward (a “dolly”). The mouse wheel advances slowly, whereas the keyboard advances faster.

Crucially, the 3D Viewer hands you extra control to rotate the view across the scene’s three dimensions, so you can study your scene from many different angles while you work. Rotating within a 3D Viewer is done one of these ways:

- With the Option key held, drag to the left or right while using the middle mouse button.
- Keep both the middle and right mouse buttons pressed as you drag.

The rotation pivots around the middle of the view. TIP: You can apply these same rotation controls to the 3D Histogram subview as well.

### Viewing Objects via Wireframe

3D composites handle not only 2D images on image planes but also true geometry — such as that made by the Particle system, the Text 3D node, imported FBX meshes, and the basic primitives of the 3D toolset. A Wireframe view makes it easier to see through a mesh or to gauge the geometry’s density. Catching a change in an ImagePlane3D’s Subdivision level is much easier in wireframe than in the rendered image. To render 3D geometry as wireframe, do this: right-click the 3D Viewer and pick 3D Options > Wireframe off the contextual menu.

### Changing the POV of a 3D Viewer

Compositing a 3D scene frequently means viewing it from several angles to verify the position and animation are right. Although the 3D Viewer uses a perspective camera that lets you look at the 3D scene from any angle, you can also flip the 3D Viewer to a view from the scene’s front, top, left, or right side — together known as Orthographic views. And if your scene contains a camera or spotlight, you can point the viewer at the scene from that object’s vantage point. To switch the 3D viewpoints: right-click the viewer and select an entry from the contextual menu’s Camera submenu. Among the choices are Perspective, Front, Top, Left, and Right.

### Changing Cameras in a 3D Viewer

When the 3D scene holds one or more camera objects, they appear as choices in the contextual menu. Spotlights and other lights or objects within the scene are listed under the Other submenu. Selecting any of these objects makes the 3D Viewer jump to the scene as seen from that object’s vantage point. While you look “through“ an object and rotate, pan, or zoom, the viewer instead alters the rotation, position, and scale of that camera, light, or other object.

### Copying a Viewer’s POV to a Camera

Often you’ll set up your scene using the default perspective view and then wish that vantage point (POV) to become your main camera’s point of view. With the Copy PoV To command you can effortlessly position and orient a camera, light, or other object to match the viewer’s current vantage point. To transfer the viewer’s point of view onto a camera, follow these steps: 1 Dial in the vantage point you want on a 3D Viewer by zooming, panning, and rotating it. 2 Add a camera to your 3D scene. 3 Right-click anywhere inside the 3D Viewer and pick Camera > Copy PoV To > Camera3DNameOfCamera off the contextual menu. The Camera3D’s controls then take on the position and angle values from the viewer. TIP: Because the Copy PoV To command operates in the object’s own coordinate space, any transformations a downstream node applies are ignored.

### POV Labels

As you change the viewer’s POV, a text label in the viewer’s lower-left corner keeps you informed of which POV is showing. Right-clicking that label directly, or the axis control just above it, serves as a shortcut to the Camera submenu, letting you readily pick a different viewpoint.

The Viewpoint label and Axis control in a 3D Viewer

### Lighting and Shadows in 3D Viewers

Default lighting is supplied before you place any lights in a 3D scene. This flat, basic lighting lets you make out the shading on objects without having to add and configure lights as you work in the 3D Viewer. Shadows, moreover, are hidden by default. As soon as you begin adding your own lights, you’ll need to change modes to observe what they affect while working.

To see the effects of the default light on the scene:

- Inside the 3D Viewer, right-click and pick 3D Options > Default Lights off the contextual menu. Once you’re set to add your own lighting, you can wire light nodes in assorted ways to a Merge 3D node for the scene at hand. After you connect a light to a Merge 3D node, you must switch the 3D Viewer over to display the new, proper lighting.

To toggle lighting rendering within a 3D scene: inside the 3D Viewer, right-click and pick 3D Options > Lighting off the contextual menu.

A 3D scene lit by default lights (top), and that same scene once lighting is switched on (bottom) TIP: Trying to load a Light node into a viewer on its own yields an empty scene, lit by nothing. To witness the lights’ effects you have to view the Merge 3D node that the light is connected to. As with lights, the default 3D Viewer keeps shadows switched off. To see shadows thrown by the lighting you’ve built, you have to enable them.

To toggle shadows rendering within a 3D scene: inside the 3D Viewer, right-click and pick 3D Options > Shadows off the contextual menu. Switching shadows on also switches lighting on automatically, unless it already was.

A 3D scene with shadows enabled along with the lights

### Transparency in 3D Viewers

Whether image planes and 3D objects hide one another in a scene depends on each object’s X, Y, and Z position coordinates in 3D space. The default scheme for working out which polygons are concealed and which are visible from those coordinates is called Z-buffering. Z-buffering is exceptionally fast, though it isn’t always precise when several transparent layers occupy a scene. Happily, a different option exists for trickier 3D scenes that involve transparency: Sorted. The Sorted approach can run considerably slower in some scenes, but it delivers more accurate results regardless of how many transparency layers the scene contains. The viewer defaults to Z-buffering, yet you can readily switch over if your scene needs the Sorted approach. To choose a Sorted method of 3D compositing:

- Right-click anywhere inside the 3D Viewer and select one of the entries in the contextual menu’s Transparency submenu; Full Sort: Draws each polygon in Z order, giving the most precise transparency result. Quick Sort: Reshuffles the scene’s polygons one after another, back to front, giving a fairly precise transparency result.

### Grid

The 3D Viewer shows a grid that supplies a plane of reference within the 3D scene. By default that grid measures 24 x 24 units, is centered on the origin at (0,0,0), and is divided into large squares of 2 units containing small squares of 0.25 units apiece. You can change these defaults in the 3D View panel of the Fusion Settings window, reachable from the Fusion menu.

To toggle the grid on and off: right-click anywhere inside the 3D Viewer and pick 3D Options > Grid off the contextual menu.

The 3D Viewer’s default grid, its origin sitting at x = 0, y = 0 and z = 0

### Vertex Normals

A normal records which way each vertex of a piece of 3D geometry points, and normals feed into the lighting and texturing calculations for an object. When viewing any sort of 3D geometry — an image plane or a complete FBX mesh alike — a scene’s per-object normals can be displayed. To bring up those normals: right-click anywhere inside the viewer and pick 3D Options > Vertex Normals off the contextual menu.

### The normals viewed in a 3D scene

### Quad View

3D compositing often has you looking at the scene from several vantage points to better manage transformations across three dimensions. You can switch the 3D Viewer between vantage points, but doing it repeatedly grows tedious. Luckily, you can instead turn on a Quad view that carves the viewer into four panes. Those panes can then present four different angles of the scene at once. Toggling the Quad view on or off is done one of these ways:

- Right-click anywhere inside the viewer and pick Views > Quad View off the contextual menu.
- Press Shift-Q.

### A Quad view of a 3D scene

Although a Quad view holds four panes, all of them display the same scene. As you assign views within a Quad view, your options run to the Front, Left, Top, Bottom, and Perspective orthographic views, or the view seen through any camera or spotlight present in the scene. Assigning different views to a Quad view’s panes is done one of these ways:

- Right-click straight on the POV label in the lower-left of whichever pane you’re reassigning, and pick a different camera, light, or Point of View off the contextual menu.

### Quad View Layouts

Quad view layouts come in several arrangements, from four equally sized panels to three small panels along the bottom of one larger panel. To move to a different Quad view layout, do this: 1 Turn on the Quad view. 2 Right-click anywhere inside the viewer and select an entry from the contextual menu’s Views > Quad Layouts submenu.

### Using Quad Views for 2D Scenes

Quad views serve 3D scenes, but they aren’t limited to them — they work with 2D scenes too, where each pane shows a different image channel or subview type. One pane could carry the image while the rest carry the alpha channel, a vectorscope, and a histogram. To hand different channels or subviews to the panes of a Quad view set up for a 2D scene: 1 In a viewer, right-click and pick Views > Quad View. 2 Click once inside the pane you’re reassigning. 3 Then do one of these: a) Pick a channel off the Channel Viewer menu. b) Right-click in the viewer, pick Views, and then pick a Subview from the submenu.

### Guides

Guides are onscreen overlays that help you arrange elements within a boundary or along the central vertical and horizontal axes. Displayed in the viewer, they are not rendered into the scene itself. Four guides see common use and can be shown: Monitor Safety, Safe Title, Center, and Film.

### The Guides submenu in the viewer’s contextual menu

Methods of using guides:

- To display guides in a viewer: right-click in the viewer, then pick Guides > Show Guides off the contextual menu, or press Command-G.
- To alter the aspect ratio of the guides on screen: right-click in the viewer, then pick an entry from the Guides > Frame Aspect submenu. Frame aspect usually sits at Default, which locks the frame aspect to the resolution of the image being shown. Set it to a particular value, though, and the guides snap to the precise edges of the chosen format, with any image area beyond that rendered dark gray.
- To show or hide specific guides: right-click in the viewer, then pick an entry from the Guides submenu. A selection of specific guides is on offer, each able to be turned on or off on its own.

Monitor Safety: Monitor Safety marks the safe action region that most monitors and TV screens can display. Safe Title: Safe Title marks the safe zone for titles across all TV and monitor screens. Center: Center draws a crosshair at the center point along with the view’s x- and y-axis. Film: Certain frame formats arrive with film guides already preset, while others need customizing. You can customize the film guides in the Preferences > Frame Format window.

### The Guides submenu in the viewer’s contextual menu

### Frame Format Settings

The Frame Format panel of the Fusion Settings window (found in the Fusion menu) offers two film guide settings you can use to tailor these guides.

- Guide 1 holds four fields specifying, in order, the offset from the image edges for the left, top, right, and bottom guides. Like every offset in Fusion, this is a resolution-independent figure where 1 equals the full image width and 0.5 equals half of it.
- The aspect ratio of the projection area is entered in Guide 2’s text box.

### The Frame Format Guides settings

### Domain of Definition and Region of Interest

As a compositing environment, the Fusion page leans on the familiar compositing conventions — Region of Interest (RoI) and Domain of Definition (DoD) — to lift performance dramatically.

### Domain of Definition (DoD)

In compositing, the Domain of Definition — usually shortened to DoD — denotes a rectangular region marking which part of an image truly holds data. DoD loosens the notion of an image’s actual frame, since rendering is no longer confined to the image’s literal width and height. This affects how Fusion renders images in two ways. First, nodes no longer have to render parts of the image the node won’t touch, which lets the renderer run more efficiently. Second, Fusion can now track and apply a node’s effect to pixels lying beyond the visible portion of the image. Take, for instance, the output of a Text+ node rendered over a transparent background: the text fills only some of the image’s pixels. Without Domain of Definition you’d be forced to process every pixel needlessly; with a DoD you can streamline the effects applied to the image, yielding faster results while using less memory. The image below shows an image with its DoD outlined.

The DoD appears as a pair of XY coordinates marking the corners of an axis-aligned bounding box (in pixels) Generally the DoD is worked out automatically with no need for you to step in. Every node in the Generator category, for example, generates the correct DoD on its own. For nodes such as Fast Noise, Mandelbrot, and Background, that usually means the full image dimensions, while for Text+ and nearly every Mask node the DoD is often much smaller or larger. The OpenEXR format can store an image’s data window, and Fusion applies that as the DoD when it loads such an image through a Loader node, then writes the DoD back out through the Saver node. When you work in the Fusion page within DaVinci Resolve, clips drawn from the Edit page timeline or Media Pool typically default the DoD to the full image width of the source media — media stored in OpenEXR format being the exception.

The DoD comes into being the moment the image is created or loaded into the composition. From there it flows downstream, where viewers fold it together with their Region of Interest to pin down precisely which pixels the node should affect. As you work, the various nodes automatically shrink, grow, or reposition the DoD as they apply their effect to an image, so the DoD shifts from node to node.

### Showing the DoD

When a node’s current DoD differs from that image’s frame size, it appears in the tooltip that pops up as the pointer hovers over a node in the Node Editor. The DoD can also be made visible in the viewer: right-click in a viewer and pick Region > Show DoD off the contextual menu.

### Setting the DoD Manually in the Node Editor

You can likewise set an image’s DoD by hand using the Tools > Miscellaneous > Auto Domain node found in the Effects Library. This node proves handy when you’re dealing with pre-created media that doesn’t fill the whole image. A rendering of a 3D character walking toward the camera, for instance, will often occupy only part of the image. The Auto Domain node can animate a DoD that wraps the character and disregards the rest of the image, which makes image processing more efficient.

### Region of Interest (RoI)
