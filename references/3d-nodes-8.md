# 3D Nodes (part 8)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

A right-click inside the Styled Text box brings up a menu listing the text modifiers below. A given Text 3D Styled Text box accepts only a single modifier at a time. What follows is a short rundown of the modifiers that are specific to text. Additional detail lives in Chapter 124, “Modifiers,” in the DaVinci Resolve Reference Manual, or in Chapter 64 of the Fusion Reference Manual. Animate Apply the Animate command to drop a keyframe on the text you typed and let the content change as time advances.

Character Level Styling Direct Character Level Styling isn’t available on the Text 3D node. As a workaround, build a Text+ node first and adjust its text field through a Character Level Styling modifier. From there you can either link the Text 3D’s text field to the modifier that has now become available, or duplicate the Text+ node and transfer its values into the Text 3D node (right-click > Paste Settings) Comp Name Comp Name drops the composition’s name into the Styled Text box and serves mainly as a fast way to build slates. Follower Follower is a text modifier that lets you stagger an animation so it cascades across each individual character of the text. Consult “Text Modifiers” near this chapter’s close. Publish Publish the text so other text nodes can link to it. Text Scramble A text modifier ID that shuffles the characters of the text at random. Consult “Text Modifiers” near this chapter’s close. Text Timer A text modifier that counts down from a chosen duration or, alternatively, shows today’s date plus the time. Consult “Text Modifiers” near this chapter’s close. Time Code A text modifier that prints Time Code corresponding to the active frame. Consult “Text Modifiers” near this chapter’s close. Connect To Choose this to wire the text produced by this Text node into the published output belonging to a different node.

### Transform 3D [3XF]

### The Transform 3D node

### Transform 3D Node Introduction

You can apply the Transform 3D node to move, spin, or resize every element inside a scene without a Merge 3D node being needed. That comes in handy for hierarchical transforms, or for shifting objects that get merged into one scene several times over. The controls it exposes match those in the Transformation tabs of the other 3D nodes.

### Inputs

A single mandatory input on the Transform node accepts a 3D scene or a 3D object. Scene Input: Wire the orange scene input to a 3D scene or 3D object so an extra layer of transformation controls is applied.

### Basic Node Setup

On top of whatever transforms already exist on the 3D node before it, the Transform 3D node layers additional 3D position, rotation, and pivot control. Chain several Transform 3D nodes one after another to construct parenting or hierarchical movement.

Transform 3D nodes strung together to create a parenting hierarchy Inspector

### Transform 3D controls

### Controls Tab

For the Transform 3D node, the Controls tab is the main tab. It carries controls that move, spin, or resize all elements inside a scene without a Merge 3D node being required.

### Translation

- X, Y, Z Offset: These controls place the 3D element wherever you want within 3D space.

### Rotation

- Rotation Order: These buttons pick the sequence in which rotation is applied along each of the object’s axes. As an example, XYZ rotates the X-axis first, then the Y-axis, and the Z-axis last.
- X, Y, Z Rotation: Turn the object about its pivot point with these controls. When the Use Target checkbox is on, rotation is measured against the target’s position; if it isn’t, the global axis governs instead.

### Pivot Controls

- X, Y, Z Pivot: An object turns around its pivot point. By default an object spins about its own center, treated as a pivot at 0,0,0. Use these controls to shift the pivot away from that center.

### Scale

- X, Y, Z Scale: With the Lock X/Y/Z checkbox checked, only one scale slider appears. It changes the object’s overall size. Clear the Lock checkbox and separate X, Y, and Z sliders appear, letting you scale along any dimension.

NOTE: While the Lock checkbox is checked, you cannot scale individual dimensions, not even by dragging particular axes of the Transformation widget while in Scale mode.

Use Target Turning on the Use Target checkbox brings up a group of controls for placing an XYZ target. With Use Target active, the object continuously turns so it faces the target. Its rotation is then measured relative to that target. Import Transform Brings up a file browser in which you pick a scene file that your 3D application saved or exported. The supported formats are:

LightWave Scene Max Scene Maya Ascii Scene dotXSI

.lws .ase .ma .xsi

The Import Transform button brings in transformation data alone. To bring in 3D geometry, lights, and cameras, look instead at the File > FBX Import option in the menus.

### Import Transform Browser

Onscreen Transformation Controls The Onscreen Transformation controls offer another route to the same settings found in the Inspector. The viewer supplies modes for moving, rotating, and scaling. Switch the mode of the onscreen controls by clicking one of the three buttons in the toolbar running down the side of the viewer. You can also toggle between modes via these keyboard shortcuts: Q handles translation, W handles rotation, and scaling uses E. Across all three modes, drag a single axis of the control to affect only that axis, or drag the control’s center to affect all three at once. By default the scale sliders on most 3D nodes are locked, producing uniform scaling on all three axes. Clear the Lock X/Y/Z Scale checkbox to resize an object along just one axis.

### Transform 3D onscreen transformation controls

### Triangulate 3D [3Tri]

### The Triangulate 3D node

### Triangulate 3D Node Introduction

What sets the Triangulate 3D node apart is that it carries no controls whatsoever. The node converts polygon shapes into triangles. A quad made of four points, for example, ends up as two triangles. Its job is to break complicated polygon shapes down into a mesh so they process more readily.

### Inputs

A single mandatory input on the Triangulate 3D node accepts a 3D scene or a 3D object. Scene Input: Wire the orange scene input to the 3D scene or 3D object you intend to triangulate.

### Basic Node Setup

Place the Triangulate 3D node downstream of the geometry you intend to triangulate.

### Triangulate 3D nodes connected after an imported model

### Inspector

### Triangulate 3D controls

### Controls Tab

This node has no controls.

### Common Controls

Settings Tab Other 3D nodes carry the same Settings tab found here in the Inspector. A full account of these shared controls appears at this chapter’s end within “The Common Controls” section.

### UV Map 3D [3UV]

### The UVMap 3D node

### UV Map 3D Node Introduction

What the UV Map 3D node does is swap out the UV texture coordinates on the scene’s geometry. Those coordinates instruct Fusion on the way a texture is laid onto an object. You can tweak the overall properties of whichever mapping mode is chosen, yet you cannot reach in and hand-edit the UV coordinates of single vertices inside Fusion. Onscreen controls that appear in the viewers serve only as a reference and aren’t adjustable. Camera Projections with UV Map 3D With the Camera Mapping mode you can cast texture coordinates onto geometry by way of a camera. After picking Camera in the Mapping mode menu, attach the Camera 3D node you intend to use for generating the UV coordinates. NOTE: This does not literally cast an image through the camera. Feed the picture you want projected into the diffuse texture input of whichever material the objects carry. As the texture lands, it relies on the UV coordinates the camera produced. Since this is a projection of texture and not of light, the texture’s Alpha channel properly drives the geometry’s opacity. Look at the Camera 3D and Projector 3D nodes for other ways to handle projection. If you like, the projection can be pinned to the vertices the way it looks on a chosen frame. That breaks when the mesh’s vertex count varies over time, because Fusion has to align the mesh between the reference time and the current time. Put plainly, vertices must not be added, removed, or reordered. Consequently, projection locking won’t hold for many particle systems, nor for primitives whose subdivisions are animated, nor for duplicate nodes carrying non-zero time offsets. NOTE: The UV Map 3D node lays neither a texture nor a material on the mesh; all it touches are the texture coordinates the materials draw from. That can be puzzling, since the material typically sits upstream, as the Basic Node Setup example below shows.

### Inputs

There are two inputs on the UV Map 3D node: one taking a 3D scene or 3D object, and a second optional one taking a Camera 3D node. Scene Input: Wire the orange scene input to the 3D scene or 3D object you intend to triangulate. CameraInput: This input is meant for the output of the Camera 3D node. It shows up only after the Camera Map mode menu has been switched to Camera.

### Basic Node Setup

Position the UV Map 3D node downstream of all the geometry and switch it to Camera Map. Hooking a camera up to the UV map lets you align the texture using a centered camera position together with the 3D geometry.

Set downstream of the Merge 3D, the UV Map 3D has a camera wired in so the texture aligns Inspector

### UV Map 3D controls

### Controls Tab

In the UV Map 3D Controls tab you can choose among Planar, Cylindrical, Spherical, XYZ, and Cubic mapping modes, all of which work on basic Fusion primitives as well as on imported geometry. You can dial in the position, rotation, and scale of the texture coordinates for precise control over how the texture looks. There’s also an option that pins the UV this node generates to animated geometry by way of a reference frame. That keeps textures from sliding across animated geometry.

Map Mode The Map mode menu sets the way the texture coordinates get built. Think of this menu as choosing the virtual geometry that casts the UV space onto the object.

- Planar: Creates the UV coordinates using a plane.
- Cylindrical: Creates the UV coordinates using a cylindrical-shaped object.
- Spherical: The UVs are created using a sphere.
- XYZ to UVW: Each vertex’s position coordinates get mapped straight over into UVW coordinates.

This is used for working with procedural textures.

- CubeMap: The UVs are created using a cube.
- Camera: Switches on the node’s Camera input. Once a camera is wired into the node, the

texture coordinates are created based on camera projection. Orientation X/Y/Z Sets which reference axis is used to align the Map mode. Fit A click on this button fits the Map mode to the input scene’s bounding box. Center Clicking here relocates the Map mode’s center onto the center of the input scene’s bounding box. Lock UVs on Animated Objects When the object is animated, enable this option to pin the UVs to it. Doing so also exposes the Ref Time slider, letting you pick a reference frame for the UV mapping. With this in use, animating the UV map parameters becomes unnecessary. Setting up the UV map at the reference time is sufficient. Size X/Y/Z Sets the size of the projection object. Center X/Y/Z Sets the position of the projection object. Rotation/Rotation Order These buttons choose the sequence in which rotation is applied along each of the object’s axes. As an example, XYZ rotates the X-axis first, then the Y-axis, and the Z-axis last. Rotation X/Y/Z Sets the projection object’s orientation per axis, separately from the rotation order. Tile U/V/W Sets how many times a texture repeats inside the projected UV space along the relevant axis. Keep in mind the UVW coordinates get transformed, not a texture. For best results pair it alongside the Create Texture node. Flip U/V/W Mirrors, about the relevant axis, the texture coordinates. Flip Faces (Cube Map Mode Only) Mirrors the texture coordinates across the cube’s individual faces.

NOTE: Getting the most out of the UV Map 3D node is easier with a basic grasp of how 2D images get mapped onto 3D geometry. Applying a 2D image to a 3D surface turns it into a texture map whose UV coordinates dictate how the picture lands on the object. Every vertex of a mesh carries a (U, V) texture coordinate pair describing how the object looks once it is unwrapped and laid flat. The various mapping modes each take a different approach to figuring out how the vertices flatten into a 2D texture. To alter the texture coordinates on a mesh with the UV Map 3D node, you’ll get the best results sticking to the default coordinate system of that mesh or primitive. The usual chain therefore reads Shape 3D > UV Map 3D > Transform 3D. You’d leave the Transformation tab of the Shape node at its defaults, and let the Transform 3D node placed after the UV Map 3D handle whatever positioning the node needs in the scene. Changing or animating the Shape node’s transform makes the texture creep across the shape, which is usually unwanted. The UV Map 3D node alters texture coordinates per vertex rather than per pixel. When the geometry the UV map covers is poorly tessellated, unwanted artifacts can show up.

### Common Controls

Settings Tab Other 3D nodes carry the same Settings tab found here in the Inspector. A full account of these shared controls appears at this chapter’s end within “The Common Controls” section.

### Weld 3D [3We]

### The Weld 3D node

### Weld 3D Node Introduction

Now and then 3D geometry carries vertices that ought to have been joined as the geometry was built but, for whatever reason, were left separate. The result can be artifacts, particularly where the two vertices carry differing normals. As an example, you might run into:

- The different normals produce hard shading/lighting edges where none were intended.
- Should you Displace 3D those vertices down their normals, cracking occurs.
- Missing pixels or doubled-up pixels in the rendered image.
- Particles pass through the tiny invisible cracks.

Rather than going back to your 3D modeling application to mend these “duplicated” vertices, the Weld 3D node lets you handle it right in Fusion. Weld 3D fuses together vertices whose positions are identical or very nearly so. Use it to clear up cracking that shows when vertices get displaced by welding the geometry ahead of the Displace. No user controls exist for choosing vertices. As it stands, the node fuses only position vertices; it leaves normals, texcoords, and every other vertex stream untouched. Thus, even though two vertices now share the same position, their normals retain their former values. In some cases that yields hard edges.

### Inputs

The Weld 3D node carries one input for the 3D scene or 3D object you want to repair. Scene Input: Wire the orange scene input to the 3D scene or 3D object you intend to fix.

### Basic Node Setup

Set the Weld 3D node downstream of geometry suffering from duplicate-vertex trouble. Such problems sometimes surface when the geometry is displaced. When that happens, dropping the weld after the geometry yet ahead of the Displace 3D can mend things.

Weld 3D is placed after the 3D geometry that needs repair Inspector

### Weld 3D controls

### Controls Tab

On the Weld 3D node, the Controls tab offers a single Weld Mode menu. You decide between welding vertices or fracturing them. Fracture Fracturing inverts welding, so every vertex is unwelded. Consequently all polygon adjacency data is thrown away. As an example, an Image Plane 3D ordinarily consists of joined quads sharing vertices. Fracture the image plane and it turns into a cluster of disconnected quads. Tolerance Under auto mode, the Tolerance figure is worked out for you. That covers most situations. You can also set it by hand where needed.

USAGE Reach for Weld 3D when the geometry gives you trouble. Don’t scatter it everywhere just because it exists, since it adds to render time. Weld 3D is meant as a mesh robustness tool, not as a mesh editing tool for merging vertices. If the gap between the vertices you intend to weld is visible in the 3D view, odds are you’re misusing Weld 3D. Strange results can follow when you try it; proceed at your own risk. LIMITATIONS A tolerance set too high can make edges and faces collapse into points. When a model spreads its detail across several orders of scale, settling on a tolerance figure can be tough or even impossible. Imagine, for instance, a model of the International Space Station bearing both many large polygons and many extremely small ones. Set the tolerance too high and small polygons that shouldn’t merge will; set it too low and some large polygons stay unmerged. Vertices a long way from the origin may not merge as they should. The cause is that bignumber + epsilon can come out exactly equal to bignumber under float math. That’s one argument for merging in local coordinates rather than world coordinates. On occasion, Weld 3D-ing a mesh degrades it. Consider Fusion’s cone. Its top vertex is presently duplicated once per neighboring face, each copy holding a different normal. Weld the cone and the top vertices fuse into a single normal, throwing the lighting off. Weld 3D is not multithreaded. WARNING: Do not abuse Weld 3D as a way to simplify (cut the polygon count of) meshes. Its purpose is to efficiently fuse vertices separated by only tiny amounts, on the order of a 0.001 distance.

### Common Controls

Settings Tab Other 3D nodes carry the same Settings tab found here in the Inspector. A full account of these shared controls appears at this chapter’s end within “The Common Controls” section.

### Modifier

### Coordinate Transform 3D

Owing to the hierarchical structure of Fusion’s 3D node tree, an object’s starting position in the 3D scene frequently does not reflect where the object currently sits. Picture an image plane whose position starts out as 1, 2, 1, yet later nodes downstream in the 3D scene then scale, offset, and rotate it until it ends up at an absolute location of 10, 20, 5. That makes it tricky to link a downstream object in the composition straight to an upstream object’s position. You can attach the Coordinate Transform modifier to any group of XYZ coordinate controls and have it compute an object’s present position anywhere in the scene hierarchy. To bring in a Coordinate Transform modifier, just right-click a number field on any node and pick Modify With/CoordTransform Position from the Controls’ contextual menu.

### Inspector

### Weld 3D modifier tools

Target Object Connect this control to the 3D node that supplies the original coordinates you want transformed. To hook up a node, drag it from the node tree and drop it into the Text Edit control, or right-click the control and pick the node from the contextual menu. Typing the node’s name straight into the control works as well. Sub ID The Sub ID slider lets you single out one sub-element of certain geometry types, such as a particular character made by a Text 3D node or a specific copy spawned by a Duplicate 3D node. Scene Input Connect this control to the 3D node that emits the scene holding the object at its new location. To hook up a node, drag it from the node tree and drop it into the Text Edit control, or right-click the control and pick an object from the Connect To submenu.

### The Common Controls

Several identical controls in the Inspector are shared by nodes that work with 3D geometry. The controls common to 3D nodes are described in this section.

### Common Controls Tab

### Common Controls 3D tab

You’ll usually find these controls in the lower portion of the Controls tab. They show up in nodes that build or hold 3D geometry.

### Visibility

- Visible: With this option on, the object appears in the viewers and in final renders. Turn it off and the object is neither shown in the viewers nor rendered into the output image by the Renderer 3D node. A non-visible object also casts no shadows.
- Unseen by Cameras: With the Unseen by Cameras checkbox on, the object stays visible in the viewers (provided the Visible checkbox isn’t off), apart from when seen through a camera. The Renderer 3D node also leaves it out of the output image. Even so, shadows an unseen object casts still appear when the software renderer in the Renderer 3D node draws them, though the OpenGL renderer does not.
- Cull Front Face/Back Face: Reach for these options to stop certain polygons in the geometry from being rendered and shown. With Cull Back Face on, polygons turned away from the camera neither render nor cast shadows. With Cull Front Face on, polygons turned toward the camera neither render nor cast shadows. Switching on both produces the same outcome as clearing the Visible checkbox.
- Suppress Aux Channels for Transparent Pixels: In earlier Fusion releases, the software and Open GL render options in the Renderer 3D node threw out transparent pixels. To be

more specific, any pixel whose R,G,B,A read 0 was dropped by the software renderer, while the GL renderer dropped a pixel once its A read 0. That behavior is now a choice. Why opt in is to obtain aux channels (e.g., Normals, Z, UVs) over the transparent regions. Imagine, for instance, that you mean to swap the texture on a 3D element which is transparent in some spots for a texture transparent in other spots. Then it pays to have the transparent regions write aux channels (UVs in particular). Or, imagine you’re adding depth of field. You likely don’t want the Z-channel written over transparent areas, because that hands you a false depth. Bear in mind, too, that the exclusion keys off the final pixel color, lighting included if it’s active. So a specular highlight sitting on a clear glass material isn’t touched by this checkbox.

### Lighting

- Affected by Lights: Clearing this checkbox keeps scene lights from influencing the object. The object then neither takes nor casts shadows, and it appears at the full brightness of its color, texture, or material.
- Shadow Caster: Clearing this checkbox stops the object from casting shadows on other objects in the scene.
- Shadow Receiver: Clearing this checkbox stops the object from receiving shadows other objects in the scene cast.

Matte Switching on the Is Matte option applies a special texture that makes the object not only invisible to the camera but also hides everything sitting directly behind the camera. This option takes precedence over all textures. Where Fog 3D and Soft Clipping are concerned, turn to “3D Compositing Basics” (Chapter 85) within the DaVinci Resolve Reference Manual, or to Chapter 25 of the Fusion Reference Manual. Is Matte: Once active, objects whose pixels lie behind the matte object’s pixels in Z are not rendered. Switching on the Is Matte checkbox brings up two more options. Opaque Alpha: With the Is Matte checkbox on, the Opaque Alpha checkbox forces the matte object’s Alpha value to 1. Infinite Z: This option drives the value in the Z-channel to infinite. The checkbox shows up only while the Is Matte option is on. Blend Mode A Blend mode determines which technique the renderer uses to fold this object into the rest of the scene. These blend modes are basically the same as those covered in the 2D Merge node section. For a thorough rundown of each mode, see that node’s section. The blending modes were first intended for 2D images. Putting them to work in a lit 3D environment can yield unwanted results. For the best outcome, apply the Apply modes within unlit 3D scenes using the software option of the Renderer 3D node.
