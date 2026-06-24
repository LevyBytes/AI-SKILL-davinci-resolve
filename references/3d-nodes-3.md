# 3D Nodes (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Linear: With this option, transforms get multiplied by the copy's number, and the cumulative scale, rotation, and translation are each applied one after another, independent of the other copies.
- Accumulated: With this option, every object copy begins where the previous object ended and is transformed onward from that point. That result is then transformed again to produce the next copy.

Transform Order This menu lets you choose the sequence in which the transforms get calculated. Its default is ScaleRotation-Transform (SRT). Different orders yield different placements of your final objects. Translation The X, Y, and Z Offset sliders define the offset position given to each copy. An X offset of 1 shifts each copy 1 unit along the X-axis away from the previous copy. Rotation The buttons running across the top of this rotation control group set the sequence in which rotations get applied to the geometry. A rotation order of XYZ would rotate first on the X-axis, next on the Y-axis, then on the Z-axis. The three Rotation sliders define how much rotation each copy receives.

Pivot The pivot controls fix where the pivot point sits when each copy is rotated. Scale

- Lock: While the Lock XYZ checkbox is on, any change to the duplicate scale carries across all three axes at once. Switching this checkbox off swaps the Scale slider for separate sliders covering the X, Y, and Z scales.
- Scale: The Scale controls tell Duplicate the amount of scaling to give each copy.

### Jitter Tab

The controls on the Jitter tab let you randomize the position, rotation, and size of every copy generated over on the Controls tab.

### Duplicate 3D Jitter tab

Random Seed The Random Seed slider serves to produce a random starting point for the quantity of jitter given to the duplicated objects. Two Duplicate nodes carrying identical settings but distinct random seeds yield two entirely different outcomes. Randomize Press the Randomize button to auto generate a random seed value. Jitter Probability Moving this slider sets the proportion of copies the jitter touches. Setting it to 1.0 affects 100% of the copies, whereas 0.5 affects only half of them.

Time Offset Use the Time Offset slider to shift any animations applied to the source geometry by a fixed amount for each copy. As an example, set the value to –1.0 and feed in a cube animated to spin on the Y-axis as the source. The first copy displays the animation as it was a frame earlier; the second copy displays animation from a frame before that, and so on. Applied to textured planes, this can be highly effective—say, where each copy can present successive frames of a clip. Translation Jitter Across the duplicated objects, this trio of controls tunes how much the X, Y, and Z translation varies. Rotation Jitter For the duplicated objects, this trio of controls tunes how much the X, Y, and Z rotation varies. Pivot Jitter Among the duplicated objects, this trio of controls tunes how much the rotational pivot center varies. Only the extra jitter rotation is touched here, never the rotation the Rotation settings on the Controls tab produce. Scale Jitter For the duplicated objects, this control tunes how much the scale varies. Switch off the Lock XYZ checkbox to vary the scale independently across all three axes.

### Region Tab

The controls on the Region tab let you mark out an area in the viewer where copies are allowed to show up or are kept from showing up. As with most Fusion parameters, this area can be animated so the copied object pops on and off the screen according to the region's shape and setting.

### Duplicate 3D Region tab

Region Tab The Region section holds two settings governing the region's shape and the effect the region has on the duplicate objects.

- Region Mode: The Region Mode menu offers three options. The default, labeled "Ignore region," skips the node altogether and leaves the copies of objects exactly as set on the Controls and Jitter tabs. The menu entry labeled "When inside region" makes the copied objects show up only while their position lands inside the region this tab defines. The final menu entry, "When not Inside region," makes the copied objects show up only while their position lands outside the region this tab defines.
- Region: The Region menu fixes the region's shape. Among the five options are the cube, sphere, and rectangle primitive shapes. The mesh option lets you wire a 3D model into the node's green mesh input. That green input shows up only once the Region menu is set to Mesh. The All setting points to the whole scene. This lets the copies pop on and off when the Region mode is animated. Once the Region menu is set to Mesh, four more options become visible. They are covered below.

Winding Rule: Drawing on four common techniques, the Winding Rule menu decides how the mesh of polygons is read as an area of volume and, in turn, how copies find the vertices in the mesh. Intricate overlapping regions of a mesh may produce an irregular fit. Switching to a different technique from this menu can occasionally yield a closer match between the mesh and how the copies read the mesh shape. Winding Ray Direction: A 3D model consists of a mesh of vertices built from flat polygons. As this becomes a volume for a region, the Winding Ray Direction decides the alignment direction for each polygon's volume (like depth extrude). Limit by Object ID: With a scene that holds multiple meshes wired into the node's green Mesh input, all of those meshes act as the region. Turning on this checkbox lets you use the Object ID slider to pick the ID for the mesh you want as the Region. Object ID: While the Limit by Object ID checkbox is on, this slider picks the number ID of the mesh object you want for the Region.

### Common Controls

Settings Tab The controls on the Settings tab are shared by many 3D nodes, and you'll find their descriptions in "The Common Controls" section at the close of this chapter.

### Extrude 3D [3Ex]

### The Extrude 3D node

### Extrude 3D Node Introduction

The Extrude3D tool works on Fusion's shape tools, taking flat shapes and turning them into dynamic, three-dimensional objects by way of controlled extrusion, driving the shape's edges out into the Z-axis. Extra beveling can be added for polished edges and chamfers.

### Inputs

This node carries three inputs: a shape connection plus two material connections. BevelMaterialInput: This pink-colored material input accepts a 2D image or, alternatively, a 3D material. From whichever source feeds it (in Fusion Studio a Loader node, or in DaVinci Resolve a MediaIn node), it draws the bevel's texture. Where a 2D image is supplied, it serves as a diffuse texture map feeding the Inspector's Basic Material tab. Wire in a 3D material rather than an image, and that Basic Material tab switches off. ShapeInput: A Shape node is what this yellow input expects—namely the 2D shape destined to be beveled and extruded into 3D space. MaterialInput: This green-colored material input accepts a 2D image or, alternatively, a 3D material. From whichever source feeds it (in Fusion Studio a Loader node, or in DaVinci Resolve a MediaIn node), it draws the shape's texture. Where a 2D image is supplied, it serves as a diffuse texture map feeding the Inspector's Basic Material tab. Wire in a 3D material rather than an image, and that Basic Material tab switches off.

### Basic Node Setup

The Extrude 3D node mainly serves to build a 3D shape out of a 2D shape. The Shape Node node feeds into the Extrude 3D node, which in turn feeds a Merge 3D node. View that Merge 3D node and you'll see the Extrude 3D node along with whatever other elements are wired to it.

Wiring a simple sRectangle Shape node into an Extrude 3D node carries the rectangle over into 3D space.

A simple sRectangle extruded into 3D space and beveled

### Inspector

### The Extrude3D Controls tab

### Controls Tab

The Controls tab serves to define the polygon characteristics, among them extrusion depth and beveling. Extrusion Style Two choices exist: Classic and Custom. Classic produces a standard uniform extrusion, whereas Custom reveals an Extrusion Profile graph where you can add points and manipulate them to build one-off custom extrusions, such as picture frames and knurled buttons. Extrusion Depth This slider fixes the extruded width of the polygon. Extrusion Subdivisions This slider fixes how many subdivisions fall within the smoothed parts of the extrusion profile. Bevel Depth Raise the Bevel Depth slider's value past zero to put a bevel on the polygon. Bevel Width This slider determines how wide the polygon's bevel runs. Smoothing Angle With this control you adjust the smoothing angle that the bevel's edges receive. Bevel Front/Back These checkboxes let you turn on beveling for the front and back faces of the polygon separately.

### Common Controls

Materials, Transform, and Settings Tabs Within the Inspector, the Materials tab along with the Transforms tab and the Settings tab show up on other 3D nodes too. These common controls get a full description at this chapter's close in "The Common Controls" section.

### FBX Exporter 3D [FBX]

### The FBX Exporter node

### FBX Exporter Node Introduction

The FBX Exporter node offers a way to export a Fusion 3D scene out to the FBX scene interchange format. Each Fusion node becomes a single object in the exported file. Objects, lights, and cameras carry the name of the node that produced them. You can set the node to export a single file covering the whole scene, or to write one frame per file. Within the Fusion Studio application, keep the Preferences > Global > General > Auto Clip Browse setting at Enabled (default)—or, over in DaVinci Resolve, keep the equivalent Fusion > Fusion Settings > General > Auto Clip Browse setting enabled—and then dropping this node into a composition pops open a file browser for picking where the file gets saved. Once you've configured the node, the FBX Exporter behaves much like a Saver node: pressing the Render button on the toolbar renders out the file. Past the FBX format itself, the node exports as well to these: the 3D Studio .3ds, Collada .dae, Autocad .dxf, and Alias .obj formats.

### Inputs

The FBX Exporter node carries a single orange input. Input: The output of the 3D scene you wish to export connects into the orange input on the FBX Exporter node.

### Basic Node Setup

What the FBX Exporter 3D node takes as input is any 3D scene you want to export. Below, the node sits as a separate branch off the Duplicate 3D node. Only the objects the Duplicate 3D node generates get exported.

An FBX Exporter 3D branched off from the Duplicate 3D node

### Inspector

### FBX Exporter controls

### Controls Tab

The Controls tab gathers all the parameters you'd use to determine how the FBX file is built and which scene elements get exported. Filename This Filename field serves to show the location and file the node outputs. Click the Browse button to bring up a file browser dialog and switch the location where the file is saved. Format This menu serves to set the output file's format. Not every feature of this node is supported across all file formats. The .obj format, for one, doesn't handle animation. Version The Version menu serves to pick the available versions for the chosen format. The menu's contents shift dynamically to mirror the available versions for that format. Where the selected format offers just one option, this menu stays hidden. For the FBX formats, a Default choice resolves to FBX2011. Frame Rate Whatever frame rate the FBX scene carries is set from this menu. Scale Units By This slider alters the working units in the exported FBX file. Changing it can streamline workflows where your destination 3D software runs a different scale. Geometry/Lights/Cameras These three checkboxes govern whether the node tries to export the named scene element. Deselecting Geometry and Lights while leaving Cameras selected, for example, would output only the cameras presently in the scene.

Render Range Turning on this checkbox writes the Render Range data into the export file so that the FBX scene's time range is known to other applications. Reduce Constant Keys Turning on this option automatically drops keyframes whenever the neighboring keyframes carry the same value. File Per Frame (No Animation) Turning on this option compels the node to export one file per frame, producing a sequence of numbered files. This switches off the export of animation. Turn on this checkbox to expose the Sequence Start Frame control, where you can set the sequence's first frame to a custom value. Sequence Start Frame Turning on this checkbox brings up a thumbwheel control where you assign a particular start frame to the numbering sequence that goes onto the rendered filenames. For instance, with Global Start set to 1 and frames 1–30 rendered, files are ordinarily numbered 0001–0030. Set the Sequence Start frame to 100, and the rendered output is numbered from 100–131 instead.

### Common Controls

Settings Tab The controls on the Settings tab are shared by many 3D nodes, and you'll find their descriptions in "The Common Controls" section at the close of this chapter.

### FBX Mesh 3D [FBX]

### The FBX Mesh node

### FBX Mesh 3D Node Introduction

The FBX Mesh 3D node serves to import polygonal geometry from scene files saved in the FilmBox (FBX) format. It can likewise import geometry out of OBJ, 3DS, DAE, and DXF scene files. This gives you a way to handle more elaborate geometry than Fusion's built-in primitives offer. As this node imports geometry, all the geometry in the FBX file is merged into one mesh carrying a single pivot and transformation. The FBX Mesh node disregards any animation applied to the geometry. As an alternative, in Fusion Studio the File > Import > FBX Scene menu, or in DaVinci Resolve the Fusion > Import > FBX Scene menu, can import an FBX scene. That option spawns individual nodes for each camera, light, and mesh in the file. It can also be used to preserve the objects' animation. Leave the Preferences > Global > General > Auto Clip Browse option in Fusion Studio (or, in DaVinci Resolve, the Fusion > Fusion Settings > General > Auto Clip Browse option) at Enabled (default), and then dropping this node into a composition pops open a file browser for choosing the file you wish to import.

### Inputs

SceneInput: This orange scene input is an optional hookup, there in case you want to fold additional 3D geometry nodes together with the FBX file you've imported. Material Input: Serving as the material input, the green input takes either a 2D image or a 3D material. Feed it a 2D image and that image becomes a diffuse texture map for the node's basic material tab. Connect a 3D material instead, and the basic material tab is disabled.

### Basic Node Setup

You can run the FBX Mesh 3D node on its own without anything else wired to it. Its output runs into a Merge 3D, so the FBX model becomes part of some larger scene. In the example below, the FBX Mesh 3D node also carries a chrome material connected to its material input.

### Inspector

An FBX Mesh 3D node with chrome material applied

### FBX Mesh 3D controls

### Controls Tab

Common controls take up most of the Controls tab. The FBX-specific controls present on this tab are mainly informational rather than adjustments.

Size The Size slider governs the size of the imported FBX geometry. FBX meshes tend to come in far larger than Fusion's default unit scale, so this control helps when you need to scale the imported geometry to suit the Fusion environment. FBX File This field shows the filename and file path of the FBX mesh currently loaded. Click the Browse button to open a file browser you can use to track down a new FBX file. The node's name notwithstanding, it can also load an assortment of other formats.

FBX ascii FBX 5.0 binary Autocad DXF 3D Studio 3Ds Alias OBJ Collada DAE

(_.fbx) (_.fbx) (_.dxf) (_.3ds) (_.obj) (_.dae)

Object Name This input displays the name of the mesh being imported from the FBX file. Leave this field blank, and the FBX geometry's contents come in as a single mesh. You can't edit this field; Fusion sets it when you use the File > Import > FBX Scene menu. Take Name FBX files may hold multiple instances of an animation, known as Takes. This field displays the name of the animation take to draw from the FBX file. Leave this field blank, and no animation gets imported. You can't edit this field; Fusion sets it when you use the File > Import > FBX Scene menu. Wireframe Turning on this checkbox makes the mesh render only the object's wireframe. Wireframe rendering is supported solely by the OpenGL renderer in the Renderer 3D node.

### Common Controls

Controls, Materials, Transform, and Settings Tabs The remaining Visibility, Lighting, Matte, Blend Mode, Normals/Tangents, and Object ID controls are ones that many 3D nodes share. So too are the Materials, Transform, and Settings tabs. You'll find their descriptions in "The Common Controls" section at the close of this chapter.

### Fog 3D [3Fo]

### The Fog 3D node

### Fog 3D Node Introduction

The Fog 3D node lays fog over the scene based on a depth cue. It's the 3D counterpart of the Fog node in the Deep Pixel category. Built to operate entirely in 3D space, it takes full advantage of anti-aliasing and depth of field effects while rendering. In essence, the Fog 3D node retextures the scene's geometry by applying a color correction tied to each object's distance from the camera. An optional density texture image can introduce variation into the correction.

### Inputs

Within the Node Editor the Fog 3D node carries two inputs, though just one is required for the Fog 3D to cast itself over a 3D scene. SceneInput: Feeding this required orange-colored input is the output of a 3D scene that the fog gets "projected" onto. DensityTexture: A 2D image is what this optional green-colored input takes. Whatever fog color the node creates gets multiplied by the pixels of that image. While preparing the density texture's image, keep in mind that, in effect, the camera projects that texture onto the scene.

### Basic Node Setup

The Fog 3D node goes after the Merge 3D node that holds the scene. View the Fog node and you'll see fog laid over the 3D scene's objects according to where each one sits along Z.

A Fog 3D node placed after the Merge 3D scene

### Inspector

### Fog node controls

### Controls Tab

The Controls tab brings together every parameter you'd use to govern the Fog's appearance and how it casts over the scene's geometry. Enable This checkbox lets you switch parts of the node's processing on or off. It's not the same as the red switch at the upper-left corner of the inspector. The red switch shuts the tool off entirely and passes the image through untouched. The Enable checkbox is confined to the tool's effect portion. Other parts such as scripts in the Settings tab still process as usual. Show Fog in View By default, the fog this node creates shows up only when the scene is viewed through a camera node. Turn this checkbox on, and the fog becomes visible in the scene from every point of view. Color This control serves to set the fog's color. That color is also multiplied by the density texture image, where one is wired into the node's green input. Radial By default, the fog forms from the perpendicular distance to a plane (parallel with the near plane) running through the eye point. With the Radial option checked, the radial distance to the eye point is used in its place. The trouble with perpendicular distance fog is that as you move the camera around, objects on the left or right side of the frustum grow less fogged as they drift toward the center, even though they stay the same distance from the eye. Radial fog corrects this. Radial fog isn't always what you want, however.

For instance, while fogging an object near the camera, such as an image plane, the image plane's center could come out unfogged while its edges are fully fogged.

### Radial vs. Perpendicular fog effect

Type This control serves to set the kind of falloff given to the fog.

- Linear: Sets a linear falloff for the fog.
- Exp: Produces an exponential nonlinear falloff.
- Exp2: Produces a stronger exponential falloff.

Near/Far Fog Distance Expressed as units of distance out from the camera, this control gives the fog's range across the scene. The Near Distance sets where the fog begins, while the Far Distance marks the point where the fog reaches its full effect. Fog accumulates, so the farther an object sits from the camera, the thicker the fog ought to look.

### Common Controls

Settings Tab The controls on the Settings tab are shared by many 3D nodes, and you'll find their descriptions in "The Common Controls" section at the close of this chapter.

### Image Plane 3D [3Im]

### The Image Plane 3D node

### Image Plane 3D Node Introduction

The Image Plane node makes 2D planar geometry inside 3D space. It's most often used to stand in for 2D images on "cards" within the 3D space. The image plane's aspect comes from the aspect of the image wired to the material input. If you don't want the image's aspect ratio reshaping the "card" geometry, reach for a Shape 3D node instead.

### Inputs

Between this node's two inputs, the material input is the primary connection for laying an image over the planar geometry the node produces. SceneInput: A 3D scene is what this orange input expects. Because the node turns out flat, planar geometry, that input isn't required. MaterialInput: This green-colored material input accepts a 2D image or a 3D material. From whatever source feeds it (in Fusion Studio a Loader node, or in DaVinci Resolve a MediaIn node), it draws the rectangle's texture and aspect ratio. Where a 2D image is supplied, it serves as a diffuse texture map feeding the Inspector's basic material tab. Wire in a 3D material rather than an image, and that basic material tab switches off.

### Basic Node Setup

Chiefly, the Image Plane 3D node carries a video clip into a 3D composite. The MediaIn or Loader node feeds the Image Plane 3D node, which in turn feeds a Merge 3D node. View that Merge 3D node and you'll see every Image Plane 3D node, plus whatever other elements are wired to it.

Multiple Image Plane 3D nodes connected to a Merge 3D

### Inspector

### Image Plane 3D controls

### Controls Tab

Common controls fill most of the Controls tab. Sitting at the top of the Inspector, the Image Plane specific controls permit only minor tweaks. Lock Width/Height With this checked, the plane's subdivision goes on evenly in X and in Y. Unchecked, it gives you a pair of sliders for governing the X and Y subdivisions separately. The default here is on. Subdivision Level The Subdivision Level slider determines the count of subdivisions used while the image plane is built. Where the Open GL viewer and renderer run Vertex lighting, a mesh with more subdivisions offers more vertices for carrying the lighting. High subdivisions can therefore help while you work interactively with lights. Wireframe Turning on this checkbox makes the mesh render only the object's wireframe when the OpenGL renderer is in use.

### Common Controls

Controls, Materials, Transform, and Settings Tabs Plenty of 3D nodes hold the same remaining controls—Visibility, Lighting, Matte, Blend Mode, Normals/Tangents, and Object ID—and likewise the Materials, Transform, and Settings tabs. You'll find their descriptions in "The Common Controls" section at the close of this chapter.

### Locator 3D [3Lo]

### The Locator 3D node

### Locator 3D Node Introduction
