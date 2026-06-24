# 3D Nodes (part 6)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

A handful of pitfalls to keep in mind while working with the OpenGL UV renderer follow. Baked-in lighting: Once you've baked lighting into a model's texture, take care to switch lighting off on the object afterward whenever you render it carrying the baked-in lighting texture. Single textures/multiple destinations: Watch out for situations where one patch of the texture map gets reused across several patches of the model. That's frequently done to conserve texture memory and cut modeling time. One example is a person's texture where the artist mirrored the left side mesh/uvs/texture so as to make the right side. Attempting to bake lighting in here won't work. Unwrapped more the one mesh: Unwrapping several meshes in one go can lead to trouble. The cause is that most models are built to wring maximum use out of (u,v) in [0,1] x [0,1], so generally models sit on top of one another in UV space. Seams: Leaving the UV gutter size at 0 yields seams once the model gets retextured using the unwrapped texture. UV Gutter Size: Raise this value to conceal seams between faces.

### Common Controls

Image and Settings Tabs The rest of the controls for the Image and Settings tabs are shared across many 3D nodes. You'll find their descriptions in the “The Common Controls” section toward the end of this chapter.

### Replace Material 3D [3Rpl]

### The Replace Material 3D node

### Replace Material 3D Node Introduction

The Replace Material 3D node swaps the material applied to every piece of geometry in the input scene for its own material input. Whatever lights or cameras sit in the input scene get passed along untouched. How far the replacement reaches can be capped through Object and Material identifiers within the Inspector. Its reach can additionally be narrowed to individual channels, which makes it feasible to apply an entirely different material on the Red channel, say. Because the Text 3D node carries no material input, you can call on the Replace Material to attach material shaders onto the text.

### Inputs

The Replace Material node carries two inputs: one for the 3D scene, object, or 3D text holding the original material, plus a material input for the fresh replacement material. SceneInput: The orange scene input takes a 3D scene or 3D text whose material you wish to swap. MaterialInput: The green material input takes either a 2D image or a 3D material. Supply a 2D image and it acts, for the node's built-in basic material, as that material's diffuse texture map. Hook up a 3D material and the basic material gets switched off.

### Basic Node Setup

The Replace Material 3D node drops in right after the 3D object or scene whose material you wish to swap. Below, it's put to work swapping the default material on a Text 3D node for a chrome shader.

Replace Material 3D swapping out the default material that sits on a Text 3D node Inspector

### Replace Material 3D controls

### Controls Tab

Enable Through this checkbox the material replacement is switched on. It isn't the same thing as the red switch up in the upper-left corner of the Inspector. That red switch shuts the tool down completely and lets the image pass through with no change. The enable checkbox is confined to the effect portion of the tool. Other portions, such as scripts in the Settings tab, keep processing as usual.

Replace Mode The Replace Mode section presents four ways to swap each RGBA channel:

- Keep: Stops the channel from getting swapped by the input material.
- Replace: Swaps the material for the matching color channel.
- Blend: Mixes the materials with one another.
- Multiply: Multiplies the channels coming from both inputs.

Limit by Object ID/Material ID Switch this on and a slider shows up where the IDs you want can be dialed in. Other objects hold on to their materials. With both options switched on, an object has to meet both conditions.

### Common Controls

Material and Settings Tabs The rest of the controls for the Material and Settings tabs are shared across many 3D nodes. You'll find their descriptions in the “The Common Controls” section toward the end of this chapter.

### Replace Normals 3D [3RpN]

### The Replace Normals 3D node

### Replace Normals Node Introduction

Within 3D modeling, normals are the vectors that establish which direction light bounces off surfaces. The Replace Normals node serves to swap the normals/tangents on incoming geometry, in effect nudging an object's surface between smooth and flat. Every piece of geometry wired to the node's scene input is touched. Lights/Cameras/PointClouds/Locators/Materials, along with other non-mesh nodes, pass through untouched. The normals/tangents this node touches are Per-vertex normals/tangents, not Per-face normals/tangents. For tangents to be worked out, the input geometry has to carry texture coordinates. At times geometry carries no texture coordinates, or the texture coordinates got set to All during the FBX import because they weren't present on the FBX.

### Inputs

For the 3D scene or incoming geometry, the Replace Normals node carries just one input. SceneInput: The orange scene input takes a 3D scene or 3D geometry holding the normal coordinates you wish to alter.

### Basic Node Setup

The Replace Normals 3D node drops in right after the 3D object or scene whose normals you wish to alter. Below, it's put to work smoothing the material on an imported 3D model.

Replace Normals 3D used to smooth normals on 3D geometry Inspector

### Replace Normals 3D controls

### Control Tab

The options within the Control tab concern repairing 3D geometry and then recalculating normals/tangents. Pre-Weld Position Vertices At times position vertices end up duplicated within a geometry despite sharing the same position, which throws off the calculation of normals/tangents. Whatever pre-welding yields gets discarded; it leaves the output geometry's position vertices untouched. Recompute Governs when normals/tangents get recalculated.

- Always: The mesh's normals get recalculated every time.
- If Not Present: The mesh's normals get recalculated solely when they're absent.
- Never: The normals never get calculated. This option proves handy while animating.

Smoothing Angle Neighboring faces whose angles in degrees fall under this value get their shared edges smoothed across. A value one would commonly pick for the Smoothing Angle sits between 20 and 60 degrees. Special-case code exists for 0.0f and 360.0f (f stands for floating-point value). Set to 0.0f, faceted normals come out; that's handy for artistic effect. Ignore Smooth Groups Set this to False and two faces carrying different Smooth Groups won't be smoothed across (for instance, a cube's faces or a cylinder's top surfaces carry different Smooth Groups). Tick this On and make the smoothing angle large enough, and a cube's faces do get smoothed across. For now there's no means of visualizing Smooth Groups inside Fusion. Flip Normals Flipping of tangents can prove confusing now and then. Flip takes effect when the mesh carries tangent vectors. Most meshes in Fusion carry no tangent vectors until they hit a Renderer 3D, though. As well, while you view tangent vectors in the viewers, those tangent vectors get made when they don't already exist. The confusing part is that if you view a Cube 3D carrying no tangent vectors and press the FlipU/FlipV button, nothing occurs. That stems from there being no tangent vectors to make, though later the GL renderer can make some (unflipped) tangent vectors. NOTE: There are five points you ought to keep in mind while dealing with normals. #1 The FBX importer recalculates the normals when they're absent, but a higher-quality result is available from the Replace Normals node. #2 Bump maps may now and then hinge on the model's normals. Specifically, after you reduce a complex high polygon model to a low polygon model + bump map, those normals together with the bump map can end up “linked.” Recalculating the normals here can make the model look odd. The bump map was meant to go with the original normals. #3 Most primitives in Fusion aren't built carrying tangents; when called for, they get built on the fly by a Renderer 3D and cached. #4 At present tangents are needed solely for bump mapping. Should a material call for bump mapping, then tangents get built. Such tangents get built using a few default settings (Smoothing Angle, and so on, for instance). If you'd rather Fusion not build tangents automatically, the Replace Normals node lets you build them by hand. #5 Every computation runs within the local coordinates of the geometries rather than within the coordinate system of the Replace Normals 3D node. That can cause trouble whenever a non-uniform scale has been applied to the geometry ahead of Replace Normals 3D being applied.

### Common Controls

Settings Tab The Settings tab is shared across many 3D nodes. You'll find the description of these controls in the “The Common Controls” section toward the end of this chapter.

### Replicate 3D [3Rep]

### The Replicate 3D node

### Replicate 3D Node Introduction

The Replicate 3D node duplicates input geometry at the positions of destination vertices. Those vertices may be mesh vertices as well as particle positions. To each copy of the duplicated input geometry, an assortment of transformations can be applied. The options within the Jitter tab permit non-uniform transformations, like random positioning or sizes.

### Inputs

The Replicate 3D node carries a pair of inputs: one taking the destination geometry that holds the vertices, plus one for the 3D geometry you wish to duplicate. Destination: The orange destination input takes a 3D scene or geometry carrying vertex positions, whether from the mesh or from 3D particle animations. Input[#]: The input takes the 3D scene or geometry for duplicating. As soon as this input is wired up, a fresh input for alternating 3D geometry gets made. A minimum of one wired input is needed.

### Basic Node Setup

In the example below, a Replicate 3D node drops in right after the pRender node. A spaceship FBX node is wired to the green input standing for the object that will be duplicated based on the particles. Each particle cell adopts the shape of the 3D geometry wired to the input.

Replicate 3D used to create an armada of swarming spaceships

### Inspector

### Replicated 3D Jitter controls

### Controls Tab

Step Sets how many positions get skipped over. As an example, a step of 3 means only every third vertice of the destination mesh gets used, whereas a step of 1 means all positions get used. The Step setting helps hold performance reasonable for large destination meshes. On parametric geometry such as a torus, it can serve to single out particular parts of the mesh. Point clouds are represented internally by six points once the Make Renderable option has been switched on. To land a single point, apply a step of 6 and assign an X offset of –0.5 so you reach the center of the point cloud. Use –0.125 for Locator 3Ds. After these have been scaled, the offset may shift. Input Mode This menu sets the order in which several input scenes get duplicated at the destination. Whichever setting you pick, supplying just one input scene leaves this setting with no effect.

- Set to Loop, the inputs get used one after another. The first input lands at the first position, the second input at the second position, and onward. Should the destination hold more positions than there are inputs, the sequence loops back around.
- Set to Random, a fixed yet random input gets used per position based on the seed within the Jitter tab. This input mode can serve to feign variety out of only a few input scenes.
- The Death of Particles setting makes the input geometries' IDs shift; as a result, their copy order may shift too.

### The Input Mode Loop vs. Random order

Time Offset Reach for the Time Offset slider to shift any animations applied to the input geometry by a fixed amount per copy. As an example, dial the value to –1.0 while taking, as your source, a cube configured to spin on the Y-axis. The first copy displays the animation from a frame earlier; the second copy displays animation from a frame ahead of that, etc. This can be put to powerful effect on textured planes—for instance, where consecutive frames of a video clip can be shown. Alignment Alignment lays out how the copies get aligned relative to the destination mesh normal or particle rotation. Not Aligned: Leaves the copy unaligned. It stays spun in the same direction as its input mesh.

### Replicate 3D Not Aligned layout

Aligned: This mode draws on the point's normal and attempts to rebuild an upvector. It performs best with organic meshes carrying unwelded vertices, like imported FBX meshes, since it gives the same rotations to vertices at the same positions. On flat geometric meshes, a gradual drift in rotation becomes visible. For the best outcome, the advice is to apply this method at the origin ahead of any transformations.

### Replicate 3D Aligned layout

Aligned TBN: This mode yields a more accurate, steadier alignment grounded in the tangent, binormal, and normal of the destination point. It performs best for particles and geometric shapes. On unwelded meshes, two copies of several unwelded points at the same position may end up with different alignments owing to their individual normals.

### Replicate 3D Aligned TBN layout

Color Shapes the diffuse color or shader of each copy according to the input's particle color. Use Object Color: Leaves the destination particle's color unused. Combine Particle Color: Draws on the shader of whatever input mesh and tweaks the diffuse color so it lines up with the color from the destination particle. Use Particle Color: Swaps out the whole shader of whatever input mesh for a default shader. Its diffuse color is drawn from the destination particle.

### Replicate 3D Color options

Translation These three sliders inform the node how much offset to lay on each copy. An X Offset of 1 would shove each copy one unit, one unit along the X-axis away from the prior copy. Rotation Order These buttons serve to set the sequence in which rotations get applied to the geometry. Setting the rotation order to XYZ would lay the rotation on the X-axis first, then carry out the Y-axis spin, and finish with the Z-axis spin. XYZ Rotation These three rotation sliders inform the node how much rotation to lay on each copy. XYZ Pivot The pivot controls fix where the pivot point used while rotating each copy sits. Lock XYZ With the Lock XYZ checkbox ticked, whatever adjustment you make to the scale lands on all three axes at once. With this checkbox switched off, the Scale slider splits into separate sliders covering the X, Y, and Z scales each on their own. Scale The Scale control fixes how much scaling lands on each copy.

### Jitter Tab

The Jitter tab serves to bring randomness into an assortment of parameters.

### Replicated 3D Jitter controls

Random Seed/Randomize The Random Seed serves to generate the jitter laid on the replicated objects. Two Replicate nodes carrying identical settings but different random seeds will turn out two wholly different results. Click the Randomize button to hand over a Random Seed value.

Time Offset Reach for the Time Offset slider to shift any animations applied to the source geometry. Unlike Time Offset over on the Controls tab, Jitter Time Offset is random, grounded in the Random Seed setting. Translation XYZ Jitter Reach for these three controls to tune the variation in the translation of the replicated objects. Rotation XYZ Jitter Reach for these three controls to tune the variation in the rotation of the replicated objects. Pivot XYZ Jitter Reach for these three controls to tune the variation in the rotational pivot center of the replicated objects. This touches only the extra jitter rotation, not the rotation yielded by the rotation settings over on the Controls tab. Scale XYZ Jitter Reach for this control to tune the variation in the scale of the replicated objects. Untick the Lock XYZ checkbox to tune the scale variation on its own across all three axes.

### Common Controls

Settings Tab The Settings tab is shared across many 3D nodes. You'll find the description of these controls in the “The Common Controls” section toward the end of this chapter.

### Ribbon 3D [3Ri]

### The Ribbon 3D node

### Ribbon 3D Node Introduction

Ribbon 3D builds an array of subdivided line segments or a single line running between two points. It comes in quite handy for motion graphics, particularly alongside Replicate 3D to fasten other geometry onto the lines, and alongside Displace3D for crafting lightning bolt-like structures. By default, the array of lines comes assigned texture coordinates, so they're usable with a 2D texture. As is customary, UVMap 3D can serve to change the texture coordinates. This node leans heavily on certain OpenGL features and yields no visible result once the Renderer 3D node has been set to use the software renderer. What's more, how the lines get drawn rests entirely on the graphics card capabilities, so the ribbon's look may differ depending on your computer's graphics card.

### Inputs

The Ribbon 3D node carries a pair of inputs: one taking the destination geometry that holds the vertices, plus one for the 3D geometry you wish to replicate. 3D Scene: The orange input takes a 3D scene or geometry. Material: The input takes the 2D texture for the ribbon. Neither wired input is required.

### Basic Node Setup

In the example below, a Ribbon 3D node is put to work building lines. A gradient background is wired in to “colorize” the lines. Further nodes then follow the Ribbon 3D to bend and warp the lines.

### Ribbon 3D generates lines distorted by additional nodes

### Inspector

### Ribbon 3D controls

### Controls Tab

The Controls tab fixes the count of ribbon strands plus their size, length, and spacing. Number of Lines How many parallel lines get drawn spanning the start point through to the end point. Line Thickness Within the user interface, line thickness is allowed to hold a floating-point value, though some graphics cards permit only integer values. Some cards may permit only lines equal to or thicker than one, or top out at a certain value. Subdivision Level How many vertices sit on each line running from start point to end points. The greater that count, the more precise and smoother 3D displacement looks. Ribbon Width Fixes how far apart the lines sit from one another. Start XYZ control to fix the start point of the ribbon. End XYZ control to fix the end point of the ribbon. Ribbon Rotation Permits rotation of the ribbon about the virtual axis laid out by start point and end points. Anti-Aliasing Lets you lay anti-aliasing on the rendered lines. Reaching for anti-aliasing isn't necessarily advised. Switched on, there may be gaps between the line segments. That's especially noticeable at high values of line thickness. Once again, how the lines get drawn rests entirely on the graphics card, which means these artifacts can differ from card to card.

### Common Controls

Controls, Materials, and Settings Tabs Within the Controls tab, the controls covering Visibility, Lighting, Matte, Blend Mode, Normals/Tangents, and Object ID recur across many 3D nodes. Likewise the Inspector's Materials tab plus Settings tab appear again in other 3D nodes. A detailed account of these shared controls sits toward this chapter's end in the “The Common Controls” section.

### Shape 3D [3Sh]

### The Shape 3D node

### Shape 3D Node Introduction

The Shape 3D node serves to turn out several basic primitive 3D shapes, planes, cubes, spheres, and cylinders among them.

### Inputs

The Shape 3D offers a pair of optional inputs. Folding additional geometry in with the Shape 3D is the scene input's job, whereas texture mapping the Shape 3D object falls to the material input. SceneInput: Even though the Shape 3D builds its own 3D geometry, you can reach for the orange scene input to fold in an additional 3D scene or geometry. MaterialInput: The green input takes either a 2D image or a 3D material. Supply a 2D image and it acts, for the node's built-in basic material, as that material's diffuse texture map. Hook up a 3D material and the basic material gets switched off.

### Basic Node Setup

In the example below, four Shape 3D nodes are put to work building the primitives of a 3D set. Two of the Shape 3D nodes get wired together, forming a more elaborate primitive shape. Those shapes can then be paired with a Projector 3D to texture them using a realistic material.

Shape 3D nodes paired with a Projector 3D so as to build a realistic 3D set

### Inspector

### Shape 3D controls

### Controls Tab

The Controls tab lets you pick a shape and reshape its geometry. Different controls surface depending on the particular shape you opt to build. Shape This menu lets you pick the primitive geometry that the Shape 3D node turns out. The rest of the controls in the Inspector shift to suit the chosen shape.

- Lock Width/Height/Depth: [plane, cube] Tick this checkbox and the width, height, and depth controls get locked together as a single size slider. Otherwise, individual controls over the shape's size along each axis are on offer.
- Size Width/Height/Depth: [plane, cube] Serves to govern the shape's size.

Cube Mapping With Cube chosen in the shape menu, the Cube relies on cube mapping to lay on the Shape node's texture (a 2D image wired to the material input on the node). Radius With a Sphere, Cylinder, Cone, or Torus chosen in the shape menu, this control fixes the radius of the chosen shape. Top Radius With a cone chosen in the Shape menu, this control serves to set a radius for the top of a cone, making truncated cones possible to build. Start/End Angle With the Sphere, Cylinder, Cone, or Torus shape chosen in the Shape menu, this range control fixes how much of the shape gets drawn. A start angle of 180° together with an end angle of 360° would draw only half of the shape.

Start/End Latitude With a Sphere or Torus chosen in the Shape menu, this range control serves to crop or slice the object by laying out a latitudinal subsection of it. Bottom/Top Cap With Cylinder or Cone chosen in the Shape menu, the Bottom Cap and Top Cap checkboxes serve to decide whether the end caps of these shapes get built or whether the shape stays open. Section With the Torus chosen in the Shape menu, Section governs the thickness of the tube that makes up the torus. Subdivision Level/Base/Height The Subdivision controls serve to fix the tessellation of the mesh across all shapes. The higher the subdivision, the more vertices each shape carries. Wireframe Tick this checkbox and the mesh renders only the wireframe for the object.

### Common Controls

Controls, Materials, Transform and Settings Tabs Within the Controls tab, the controls covering Visibility, Lighting, Matte, Blend Mode, Normals/Tangents, and Object ID recur across many 3D nodes. Likewise the Inspector's Materials tab, Transforms tab, and Settings tab appear again in other 3D nodes. A detailed account of these shared controls sits in the “The Common Controls” section, found toward this chapter's end. Using a Sphere Map versus wiring the texture straight onto a sphere: rather than running it through the Sphere Map node first, you can connect a LatLong (equirectangular) texture map directly to a sphere. That yields a different rendering once you set the start/end angle and latitude below 360°/180°. In the first case, the texture comes out squashed. With the Sphere Map node in use, the texture comes out cropped. Compare:

### Spherical mapping differences

NOTE: Pipe the texture straight into the sphere and it also gets mirrored horizontally. You can alter this by running a Transform node first.

### Soft Clip [3SC]

### The Soft Clip node

### Soft Clip Node Introduction

The Soft Clip node serves to fade out geometry and particles that draw near the camera. That helps sidestep the visible “popping off” that plagues many particle systems and 3D flythroughs. This node closely resembles the Fog 3D node, in that it hinges on the geometry's distance from the camera.

### Inputs

The Soft Clip carries only a single input for a 3D scene that has a camera wired to it. SceneInput: The orange scene input is a required connection. It takes a 3D scene input carrying a Camera 3D node.

### Basic Node Setup

The Soft Clip node usually sits just ahead of the Renderer 3D node so that downstream tweaks to lighting and textures leave the result untouched. It can sit anywhere within the 3D portion of the node tree whenever the soft clipping effect is called for over only a portion of the scene.
