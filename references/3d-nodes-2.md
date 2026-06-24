# 3D Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Inside: Uniform scaling grows the film-gate image source until one of its dimensions (X or Y) meets the inside dimensions of the resolution gate mask. According to how the image source and the mask background compare in size, either the source's width or its height may be trimmed to suit the mask's dimension.
- Width: Uniform scaling grows the film-gate image source until its width (X) meets the width of the resolution gate mask. According to how the image source and mask compare in size, the source's Y-dimension may fall short of the mask's Y-dimension, so the source is either cropped in Y or leaves the mask's height not fully covered.
- Height: Uniform scaling grows the film-gate image source until its height (Y) meets the height of the resolution gate mask. According to how the image source and mask compare in size, the source's X-dimension may fall short of the mask's X-dimension, so the source is either cropped in X or leaves the mask's width not fully covered.
- Outside: Uniform scaling grows the film-gate image source until one of its dimensions (X or Y) meets the outside dimensions of the resolution gate mask. According to how the image source and mask compare in size, either the source's width or its height may be cropped or may not suit the mask's dimension.
- Stretch: The film-gate image source gets stretched across X and Y to fill the entire dimensions of the generated resolution gate mask. Doing so can leave the image source visibly distorted.

### Control Visibility

Here you can pick and choose which onscreen controls accompanying the camera get switched on.

- Show View Controls: Toggles every camera onscreen control in the viewers on or off.
- Frustum: Shows the camera's real viewing cone.
- View Vector: Shows a white line within the viewing cone, useful for gauging the

shift while you're in Parallel mode.

- Near Clip: The Near clipping plane. For clearer visibility, this plane is subdividable.
- Far Clip: The Far clipping plane. For clearer visibility, this plane is subdividable.
- Focal Plane: The plane derived from the Plane of Focus slider covered in the Controls tab above.

For clearer visibility, this plane is subdividable.

- Convergence Distance: Where convergence falls while Stereo mode is active. For clearer

visibility, this plane is subdividable.

### Import Camera

A dialog for bringing in a camera from another application opens when you press the Import Camera button. The file types it handles are these:

*LightWave Scene *Max Scene *Maya Ascii Scene *dotXSI

.lws .ase .ma .xsi

NOTE: FBX cameras come in by way of the Fusion > Import > FBX Scene menu within DaVinci Resolve, or through File > Import > FBX Scene over in Fusion Studio.

### Image Tab

Wire a 2D image into the magenta image input on the Camera3D node and an Image tab is generated at the inspector's top. That connected image always orients itself to fill the camera's field of view.

Apart from the controls noted below, this tab's options match those you'd typically meet on other 3D nodes. For fuller coverage of visibility, lighting, matte, blend mode, normals/tangents, and Object ID, consult the "The Common Controls" section at the close of this chapter.

### Camera 3D image plane tab

Enable Image Plane This checkbox switches use of the Image Plane on or off. Fill Method Should the camera carry a different aspect ratio, this menu sets how the image plane gets scaled.

- Inside: Uniform scaling grows the image plane until one of its dimensions (X or Y) meets the inside dimensions of the resolution gate mask. According to how the image source and the mask background compare in size, either the source's width or height may be trimmed to suit the mask's dimensions.
- Width: Uniform scaling grows the image plane until its width (X) meets the mask's width. According to how the image source and the resolution gate mask compare in size, the source's Y-dimension may fall short of the mask's Y-dimension, so the source is either cropped in Y or leaves the mask's height not fully covered.
- Height: Uniform scaling grows the image plane until its height (Y) meets the mask's height. According to how the image source and the resolution gate mask compare in size, the source's X-dimension may fall short of the mask's X-dimension, so the source is either cropped in X or leaves the mask's width not fully covered.
- Outside: Uniform scaling grows the image plane until one of its dimensions (X or Y) meets the outside dimensions of the resolution gate mask. According to how the image source and mask compare in size, either the source's width or height may be cropped or may not suit the respective dimension of the mask.
- Depth: The image plane's distance from the camera is governed by the Depth slider.

NOTE: How far the image plane sits from the camera is unaffected by the Camera Z position.

### Materials Tab

Whatever options the Materials tab presents line up with the ones you'd commonly meet on other 3D nodes. For more on the Diffuse, Specular, Transmittance, and Martial ID controls, consult the "The Common Controls" section at the close of this chapter.

### Projection Tab

Connect a 2D image to the camera node and a fourth projection tab shows up at the Inspector's top. Through this Projection tab, the image can be cast into the scene. What sets a projection apart from an image plane is that the projection lands on the scene's geometry precisely as though a real projector stood there in the scene. Because the image is cast as light, the Renderer 3D node has to have lighting enabled for the projection to show. Enable Camera Projection Tick this checkbox to switch on projection of the 2D image wired into the camera's magenta input. Projection Fit Method With this menu you choose the method that fits the projected image's aspect to the camera's field of view.

### Projection Mode

- Light: Defines the projection as a spotlight.
- Ambient Light: Defines the projection as an ambient light.
- Texture: Permits a projection that other lights can relight. To use this setting, a Catcher node must be wired to the relevant inputs of the material in question.

### Camera 3D projection tab

### Common Controls

Transform and Settings Tabs Whatever the Transform and Settings tabs present, you'll commonly find on other 3D nodes. For more on the controls held in these tabs, consult the "The Common Controls" section at the close of this chapter.

### Tips for Camera 3D

Camera Projection: While importing a camera from a 3D application that doubles as a projector, confirm the Fit Resolution Gate options sit in agreement across both the Controls tab and the Projection tab. Only the former sets itself automatically to whatever the 3D app had in use. You may need to set the latter by hand. Image Plane: The camera's image plane is more than a virtual guide in the viewers. It's real geometry that you can project onto as well. Putting a different image on the image plane calls for inserting a Replace Material node after your Camera node. Parallel Stereo: Reaching true Parallel Stereo mode can be done three ways:

- Connect an additional external (right) camera to the green Right Stereo Camera

input of your camera.

- Create separate left and right cameras.
- With Toe-In or Off Axis in play, push the Convergence Distance slider out to an enormous

value of 999999999. Rendering Overscan: Rendering an image with overscan means you also have to alter your scene's Camera3D. Because overscan settings don't travel along with camera data out of 3D applications, this holds for cameras you've imported through .fbx or .ma files too. The fix is to bump the film back's width and height up by whatever factor accounts for the extra pixels on every side.

### Cube 3D [3Cb]

### The Cube 3D node

### Cube 3D Node Introduction

A simple primitive geometry type, the Cube 3D node can produce a plain cube. On top of that, the node offers six extra image inputs for mapping a texture onto the cube's six faces. Often cubes serve as shadow-casting objects and for environment maps. To explore other basic primitives, look at the Shape 3D node in this chapter.

### Inputs

These optional inputs turn up on the Cube3D node within the Node Editor: SceneInput: Through the orange scene input you connect another node that builds or holds a 3D scene or object. That extra geometry merges into the Cube3D. NameMaterialInput: These six inputs assign the materials that go onto the cube's six faces. Either a 2D image or a 3D material can wire into these inputs. Any textures or materials placed on the Cube3D never carry over to 3D objects connected at the Cube's SceneInput.

### Basic Node Setup

A Cube 3D node's output usually feeds a Merge 3D node, folding it into a bigger scene. During 3D tracking, the Cube 3D frequently stands in as a placeholder for the real geometry that isn't on hand yet.

Cube 3D node wired into a 3D scene that was exported out of the Camera Tracker node Inspector

### Cube 3D controls

### Controls Tab

The Inspector's opening tab is the Controls tab. Inside it sit the main controls that set the Cube 3D node's overall size and shape. Lock Width/Height/Depth Ticking this checkbox binds the cube's Width, Height, and Depth dimensions as one. With it ticked, only a Size control appears; otherwise you get separate Width, Height, and Depth sliders. Size or Width/Height/Depth When the Lock checkbox is ticked, just the Size slider shows; otherwise separate sliders appear for Width, Height, and Depth. Since the Size and Width sliders are one control under two names, any animation put on Size carries to Width as well once the controls are unlocked. Subdivision Level The Subdivision Level slider sets how many subdivisions go into building the image plane. Because the 3D viewers and renderer rely on vertex lighting, every bit of lighting is worked out at the 3D geometry's vertices and interpolated from there. So the more subdivisions a mesh holds, the more vertices there are to carry the lighting. As an illustration, build a sphere and keep its subdivisions low so it looks chunky. With lighting switched on, the object reads as a sphere yet shows some fracturing owing to the wide spacing between vertices. Raise the subdivisions and the vertices draw closer, smoothing the lighting out. That makes raising subdivisions handy while you tune lights interactively. Cube Mapping Tick the Cube Mapping checkbox and the cube wraps its first texture over all six faces through a standard cubic mapping technique. This method counts on a texture arranged in a cross shape. Wireframe Tick this checkbox and the mesh renders nothing but the object's wireframe whenever the OpenGL renderer in the Renderer 3D node is doing the rendering.

### Common Controls

Controls, Materials, Transform, and Settings Tabs Many 3D nodes share the remaining controls covering Object ID, Normals/Tangents, Blend Mode, Matte, Lighting, and Visibility. The Materials, Transform, and Settings tabs hold true the same way. You'll find their descriptions in the "The Common Controls" section at the close of this chapter.

### Custom Vertex 3D [3CV]

### The Custom Vertex 3D node

### Custom Vertex 3D Node Introduction

For 3D geometry, the Custom Vertex 3D node is an advanced custom node carrying out per vertex manipulations. With a fair bit of scripting or C++ programming under your belt, the structure and terminology the Custom node uses should feel familiar. By way of scripting math functions plus lookup tables drawn from images, you can shift vertex positions on 3D geometry. Vertices amount to more than mere positions in 3D space. Normals, texture coordinates, vectors, and velocity are all open to manipulation. As an example, Custom Vertex 3D can set a flat plane waving like a flag, or build spiral models. Alongside a 3D scene input and three image inputs, the Inspector carries as many as eight number fields and up to eight XYZ position values pulled from other controls and parameters across the node tree. NOTE: Altering a 3D object's X, Y, and Z positions leaves the normals/tangents alone. Afterward you can run a ReplaceNormals node to recompute the normals/tangents.

TIP: Every attribute isn't present on all geometry. Most Fusion geometry, for instance, lacks vertex colors, save for particles and certain imported FBX/Alembic meshes. None of the geometry currently carries environment coordinates, and velocities belong to particles alone. When an attribute is missing from the input geometry, a default value is assumed for it.

### Inputs

Four inputs sit on the Custom Vertex 3D node. Of those four, only the orange scene input is mandatory. SceneInput: The orange scene input receives 3D geometry or a 3D scene from a 3D node's output. This is the 3D scene or geometry that the Custom Vertex 3D node's calculations operate on. ImageInput1, ImageInput2, ImageInput3: Colored green, magenta, and teal, the three image inputs are optional ones available for compositing. NOTE: Attributes absent from the input geometry get created whenever the expression for an attribute is nontrivial. The attribute values are supplied as in the point above. Should the input geometry lack normals, for example, the values of (nx, ny, nz) always come out (0,0,1). To alter that, you might run a ReplaceNormals node beforehand to generate them.

### Basic Node Setup

Whatever object you mean to manipulate wires into the orange scene input of the Custom Vertex 3D node. Its output usually feeds a Merge 3D node, folding it into a bigger scene.

Custom Vertex 3D node manipulating an Image Plane 3D node Inspector

### Custom Vertex 3D node Vertex tab

### Vertex Tab

The Vertex tab's fields let you run vertex calculations across these attributes: Velocity, UV Tangents, Environment Coordinates, Texture Coordinates, Vertex Color, Normals, and Position. Three XYZ Position values in world space define the vertices as px, py, pz. Normals state, as a vector, the direction the vertex faces as nx, ny, nz. The point's Red, Green, Blue, and Alpha color make up the vertex color as vcr, vcg, vcb, vca.

### Numbers Tab

Numbers 1-8 Numbers are variables fronted by a dial control that can be animated or wired to modifiers just like any other control. Within per-vertex equations the numbers serve two forms—evaluated at the present frame as n1, n2, n3, n4,… or, for an arbitrary moment t, as n1_at(float t), n2_at(float t), n3_at(float t), n4_at(float t). Expressions over in the Setup and Intermediate tabs can read these controls' values. Through the Config tab you can rename them and keep them out of the viewer.

### Custom Vertex 3D node Numbers tab

### Points Tab

Points 1-8 Rather than the vertices, the point controls stand for points within the Custom Vertex 3D tool. These eight point controls bring 3D X,Y,Z position controls for placing points at the current time: (p1x, p1y, p1z, p2x, p2y, p2z) or at any time: p1x_at(float t), p1y_at(float t), p1z_at(float t), p2x_at(float t), p2y_at(float t), p2z_at(float t), where t is the time you want. You might, for instance, use a point to mark a spot in 3D space for the vertices to rotate about. Through the Config tab they can be renamed and hidden from the viewer. Being ordinary positional controls, they can be animated or wired to modifiers like any other node.

### Custom Vertex 3D node Points tab

### LUT Tab

LUTs 1-4 Four LUT splines come with the Custom Vertex 3D node. A LUT is a lookup table that hands back a value taken from the LUT spline's height. To reach the LUT values, for instance, you call getlut1(float x), getlut2(float x),... with x = 0 … 1. Expressions in the Setup and Intermediate tabs can reach these controls' values through the getlut# function. Setting the R, G, B, and A expressions to getlut1(r1), getlut2(g1), getlut3(b1), and getlut4(a1) respectively, for instance, would make the Custom Vertex 3D node act like the Color Curves node. The Config tab's options let you rename these controls so their purpose reads more plainly, though expressions still see the values as lut1, lut2,...lut8.

### Custom Vertex 3D node LUT tab

### Setup Tab

Setups 1-8 As many as eight separate expressions can be worked out in the Setup tab of the Custom Vertex 3D node. Each Setup expression is evaluated once per frame, ahead of every other calculation. Its results then become available to the node's other expressions as variables s1, s2, s3, and s4. Picture them as global setup scripts that the intermediate and channel scripts can call on for each vertex.

### Custom Vertex 3D node Setup tab

For instance, Setup scripts can carry a vertex from model space into world space. NOTE: Because these expressions evaluate just once per frame rather than per pixel, there's no point pulling in channel variables such as r1, g1, b1, and the like, nor per-pixel variables such as X and Y. Permitted values cover constants, variables like n1…n8, time, W and H, and the like, plus functions such as sin() or getr1d().

### Intermediate Tab

Intermediates 1-8 A further eight expressions can be worked out in the Intermediate tab. Each Intermediate expression runs once per vertex, after the Setup expressions have been evaluated. The results come back as variables i1, i2, i3, i4, i5, i6, i7, i8, which channel scripts can call on. Picture them as "per vertex setup" scripts. You might, for example, run the script to make the new vertex (i.e., new position, normal, tangent, UVs, etc.) or to carry it from world space back into model space.

### Custom Vertex 3D Node Intermediate tab

### Config Tab

Random Seed This sets the seed feeding the rand() and rands() functions. Hit the Reseed button to drop a random value into the seed. You may need this control where several Custom Vertex 3D nodes must each yield different random results. Number Controls Eight sets of Number controls exist, matching the eight sliders over in the Numbers tab. Untick the Show Number checkbox to hide the matching Number slider, or change its name through the Name for Number text field.

### Point Controls

Eight sets of Point controls exist, matching the eight controls over in the Points tab. Untick the Show Point checkbox to hide the matching Point control along with its crosshair in the viewer. In the same way, change the control's name through the Name for Point text field.

### Custom Vertex 3D node Config tab

### Common Controls

Settings Tab The Settings tab's controls are shared by many 3D nodes, and you'll find their descriptions in the "The Common Controls" section at the close of this chapter.

### Displace 3D [3Di]

### The Displace 3D node

### Displace 3D Node Introduction

Working from a reference image, the Displace 3D node pushes an object's vertices along their normals. Where to sample the image is worked out from the geometry's texture coordinates. Bear in mind while using Displace 3D that it shifts only existing vertices and won't subdivide surfaces to add detail. For a finer displacement, raise the subdivision amount on the geometry being displaced. Note too that the displacement image's pixels may hold negative values. TIP: Running a particle system through a Displace 3D node turns off the Always Face Camera option set in the pEmitter. Particles aren't handled as point-like objects; all four of a particle's vertices get displaced on their own, which may or may not be what you're after.

### Inputs

The two inputs below appear on the Displace 3D node within the Node Editor: SceneInput: For the Displace 3D node the orange scene input is the required one. Through it you connect another node that builds or holds a 3D scene or object. Input: A 2D image used to displace the object wired into the Scene input connects through this green input. Supply no image and the node essentially hands the scene through untouched to its output. So while it isn't strictly a required input, there's little point in adding this node unless you wire this input up correctly.

### Basic Node Setup

A Displace 3D node's output usually feeds a Merge 3D node, folding it into a bigger scene. The 3D geometry you want displaced wires into the orange input, and in this example a Fast Noise node does the displacing. A Fast Noise node doing the displacing of an image sitting on an Image Plane 3D Inspector

### Displace 3D controls

### Controls Tab

Two tabs run along the top of the Displace 3D Inspector. The main one, the Controls tab, holds the dedicated Displace 3D controls.

Channel Sets which channel of the connected input image drives the geometry's displacement. Scale and Bias With these sliders you scale (magnify) and bias (offset) the displacement. Bias gets applied first, scale after.

### Camera Displacement

- Point to Camera: Tick the Point to Camera checkbox and each vertex shifts toward the camera in place of along its normal. One use for this option is displacing a camera's image plane. Viewed through the camera, the displaced camera image plane looks unchanged, yet it's deformed in 3D space, which lets you comp in other 3D layers that interact correctly in Z.
- Camera: With the Point to Camera option on, this menu picks which camera in the scene sets the camera displacement.

### Common Controls

Settings Tab The Settings tab's controls are shared by many 3D nodes, and their descriptions live in the "The Common Controls" section at the close of this chapter.

### Duplicate 3D [3Dp]

### The Duplicate 3D node

### Duplicate 3D Node Introduction

Much like the 2D version known as the Duplicate node, the Duplicate 3D node can copy any geometry in a scene, applying a running transformation to each, to build repeating patterns and intricate arrays of objects. The Jitter tab's options permit non-uniform transformations, things like random positioning or sizes.

### Inputs

By default the Duplicate 3D node carries one input where a 3D scene connects. Depending on the node's settings, an optional Mesh input shows up. SceneInput: The orange Scene Input is a required input. Whatever scene or object you wire here gets duplicated per the settings in the Inspector's Control tab. MeshInput: A green optional mesh input surfaces once the Region tab's Region menu is set to mesh. That mesh can be any 3D model, whether built in Fusion or imported.

### Basic Node Setup

A Duplicate 3D node's output usually feeds a Merge 3D node, folding it into a bigger scene. The 3D geometry you want copied, here a Cube 3D, wires into the orange input.

### A Cube 3D is duplicated

### Inspector

### Duplicate 3D controls

### Controls Tab

Every parameter for creating, offsetting, and scaling copies of the object wired to the node's scene input lives in the Controls tab. Copies This range control sets how many copies get made. Each copy duplicates the previous one, so with this control at [0,3] the parent is copied, then that copy is copied, then the copy of the copy, and onward. That opens up some intriguing effects once transformations are laid on each copy through the controls below. Raising the First Copy above 0 drops the original object and leaves only the copies on view. Time Offset The Time Offset slider shifts any animations applied to the source geometry by a fixed amount per copy. Try setting the value to -1.0, say, using as your source a cube animated to spin on the Y-axis. A frame earlier is what the first copy displays; the second copy reaches back another frame; and onward. On textured planes this works to great effect—where successive frames of a clip can be displayed, for instance.

### Transform Method
