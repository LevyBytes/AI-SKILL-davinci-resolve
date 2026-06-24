# 3D Compositing Basics (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

You bring mesh geometry in from an FBX file by way of the FBX Mesh node. Where one is present, the first texture mapped to a mesh comes along too. Because various 3D applications gauge their 3D scenes in different units, the imported geometry can come in gigantic next to everything else, since Fusion regards its measurement scale as matching its own system. As an example, when your 3D application is set to millimeters by default, a 100-millimeter object lands as a colossal 100 units. The Size slider among the FBX Mesh Inspector parameters lets you shrink such files down to a scale that fits Fusion’s 3D scene.

### FBX Exporter

The FBX Exporter node lets you send a 3D scene out of Fusion into other 3D packages. At render time it stores geometry, cameras lights, and animation across various file formats such as .dae or .fbx. You can keep the animation data within a single file, or have it baked out across sequential frames. Textures and materials, though, can’t be exported.

### Using Text3D

For motion graphics artists building titles and graphics out of Fusion, the Text3D node is likely the most widely used node of all. It’s a capable node packed with enough controls to produce just about any text effect you’d want, fully in three dimensions. The aim of this section is to get you up and running fast with all the Text3D node can do. Further detail lives in Chapter 89, “3D Nodes,” of the DaVinci Resolve Reference Manual, or over in the Fusion Reference Manual at Chapter 29.

### Assembling Text Objects

Every Text3D node is a scene unto itself, and within it each text character stands as its own object. For that reason, when you want many text objects you can animate or style apart from one another, the cleanest approach is to feed however many Text3D objects you'd like to control separately into one or more Merge3D nodes.

Merging multiple text objects to create an intricately styled scene TIP: Click the Text icon in the toolbar to make a Text3D node, then click it once more while that freshly made Text3D node is still selected, and a Merge3D node is created and selected automatically to join the pair. Keep clicking the Text icon and additional Text3D nodes attach to that same selected Merge3D node.

### Entering Text

Select a Text3D node and open the Inspector, and the Text tab presents a “Styled Text” text entry field right at the top where you type whatever text should show onscreen. Underneath sits a group of overall styling parameters for setting the Font, Color, Size, Tracking, and the like. Everything you style on this tab applies to the whole block of text together, which is precisely why you need several text objects to have differently styled words within one scene.

The text entry and styling parameters in the Text tab Toward the foot of the Text tab sit the Extrusion parameters, tucked inside a disclosure control.

The Extrusion parameters near the bottom of the Text tab Out of the box, any text made with the Text3D node is flat, yet the Extrusion Style, Extrusion Depth, and the assorted Bevel parameters let you lend thickness to your text objects.

Unextruded text (left), and Extruded text (right) Positioning and Transforming Text Out of the box, each new Text3D node lands at 0, 0, 0, so adding several Text3D nodes leaves them all stacked in one spot. Happily, every Text3D node carries its own transform controls in the Transform tab.

### Text3D nodes also have Transform parameters built-in

On top of that, selecting a Text3D node brings up all the onscreen transform controls covered elsewhere in this chapter. With those controls you can place and animate each text object on its own.

### Repositioned text objects to create a title sequence

Pairing Text3D nodes with Merge3D nodes builds a scene, but it also lets you transform your text objects one at a time or in clusters:

- Pick a single Text3D node, or a piece of text in the viewer, and you can reposition just that one text object on its own, with no effect on the scene’s other objects.
- Pick a Merge3D node and a transform control appears that acts on every object wired into that Merge3D node together, so the whole scene transforms as one.

### Layout Parameters

On the Layout tab you’ll find parameters for picking how text gets laid out: along a straight line, a frame, a circle, or a custom spline path, plus contextual parameters that shift with whichever layout you choose (every one of them animatable).

Text using two different layouts “Sub” Transforms There’s a second Transform tab (the documentation calls it the “Sub” Transform tab) that lets you lay a separate tier of transform onto characters, words, or lines of text, opening up still more layout variety. As an instance, picking Transform by Words lets you adjust word spacing, spin each word, and so forth. Transforms can run on characters, words, and lines all at the same time, so you can stack every one of these capabilities together if you truly want to push it. And naturally, all these parameters can be animated.

### Transforming individual words in two different ways

### Shading

On the Shading tab you can shade or texture a text object with the standard Material controls.

### Fog 3D and Soft Clipping

Atmospheric depth cues are easy to build with the Fog3D node.

### Split screen with and without fog

The Fog3D node pairs nicely with the depth of field and antialiasing the OpenGL renderer provides. Because it isn’t a post-processing node (unlike the VolumeFog node sitting in the Nodes > Position menu, or the Fog node under Nodes > Deep Pixel), it gets by without extra channels such as Position or Z-channel color. It also handles transparent objects. The SoftClip node leans on how far a pixel sits from the viewpoint to drive opacity, letting objects fade out gracefully as they near the camera. That keeps objects from “popping off” when the camera moves through them, which proves handy especially with particles the camera might travel through. Geometry nodes like the Shape3D node carry a Matte Objects checkbox for masking away portions of the 3D scene. In practice, anything sitting behind a matte object goes unrendered. Even so, matte objects can feed data into the Z-channel and the Object ID channel while leaving every other channel at its defaults. They neither delete nor alter any geometry; picture them as a 3D garbage matte serving the renderer.

A Circle shape acting as a Matte object so the floor shows through Matte Object Parameters Open the Matte disclosure control and the Is Matte option appears, and switching it on unlocks two further options.

Matte parameters within a Shape3D node; turning on Is Matte surfaces extra options Is Matte Found on the geometry’s Controls tab, this serves as the principal checkbox for matte objects. With it on, any object whose pixels sit behind the matte object’s pixels in Z goes unrendered. Opaque Alpha Switching on the Is Matte checkbox brings up the Opaque Alpha checkbox. Turning it on forces the matte object’s alpha value to 1. If you don’t, the alpha — like the RGB — comes out 0. Infinite Z Switching on the Is Matte checkbox brings up the Infinite Z checkbox. Turning it on drives the Z-channel value to infinite. Otherwise the mesh feeds the Z-channel as it normally would. You can’t pick matte objects in the viewer unless you right-click there and choose 3D Options > Show Matte Objects from the contextual menu. That said, the matte object can always be picked by selecting its node within the node tree.

### Material and Object IDs

In Fusion, the bulk of nodes that allow effect masking can draw on Object ID and Material ID auxiliary channels to build a mask. You’ll find the parameters for doing so on each node’s Common Controls tab.

Material ID parameters shown among a Shape3D node’s Inspector controls The Material ID is a value that marks which material an object uses. The Object ID parallels the Material ID closely, save that it tags objects rather than materials. Fusion hands out both the Object ID and the Material ID automatically in counting order, starting at 1. You’re free to give several objects or materials the same ID even when they aren’t alike. Override 3D gives you a quick path to reassign the IDs across a number of objects. During rendering, the Renderer writes the assigned values into the frame buffers whenever those buffers have their output channel options switched on. The usable value range runs from 0 to 65534. Since empty pixels carry an ID of 0, manually handing a value of 0 to an object or material is allowed but unwise, because a 0 signals Fusion to pick an unused ID at render time.

The ground plane and the object both given an identical Object ID number

### World Position Pass

The World Position Pass — WPP for short — is a render pass that comes out of 3D applications. Every pixel gets the XYZ position in world coordinates of the spot where it was generated. So when the face a pixel came from sits at (0,0,0) in the scene, that pixel ends up with a Position value of (0,0,0). Picture that as RGB and the pixel reads black. Place a face at (1,0,0) within the original scene and the RGB pixel it yields reads red. Given the vast spread of possible positions across a typical 3D scene — with 7⁄8 of those holding negative coordinates — the Position channel always renders in 32-bit float.

A World Position Pass render of a scene whose center sits at (0,0,0); the real image is up in the top left 3D Scene Input Nodes drawing on the World Position channel live under the Position category. VolumeFog and Z to WorldPos call for a camera input that matches the camera which rendered the Position channels, which may be either a Camera3D or a 3D scene that holds a camera. As in the Renderer3D, you get to pick which camera to use when several are in the scene. The VolumeFog can render with no camera input from the Node Editor as long as its world space Camera Position inputs hold the right value. VolumeMask takes no camera input. The nodes that support the World Position Pass, found under the Position category, each provide a Scene input, which may be either a 3D Camera or a 3D scene containing a camera. Three Position nodes can make use of World Position Pass data.

- Nodes > Position > Volume Fog
- Nodes > Position > Volume Mask
- Nodes > Position > Z to World
- The “Dark Box”

Across empty stretches of the render, the Position channel comes up wrongly initialized to (0,0,0). To recover proper Position data, drop a bounding sphere or box into your scene so it supplies distant values and lets the Position nodes render as they should.

Lacking a bounding mesh to produce Position values, the fog wrongly fills the background

### Point Clouds

The Point Cloud node is built to handle locator clouds that come out of 3D tracking software. 3D camera tracking tools, SynthEyes and PF Track among them, frequently spit out hundreds or even thousands of tracking points. Viewing those points in the scene and reading their place in 3D and screen space matters for aligning live action with CG, yet pulling each one in as a separate Locator3D would tank performance and crowd the node tree.

### Point cloud in the viewer

The Point Cloud node can pull in point clouds saved into scene files by match moving or 3D scanning software. Importing a point cloud goes like this: 1 Drop the PointCloud3D node into your composition. 2 In the Control panel, click the Import Point Cloud button. 3 Navigate to the scene file and choose one of its clouds to bring in. The whole point cloud arrives as a single object, which is a markedly faster route.

### Finding, Naming, and Publishing Points

A lot of 3D trackers let you name individual tracking points and place tracking points on features of interest. The Point Cloud 3D locates those points fast and publishes them. Once published, a point in the cloud can drive the animation of other parameters.

Locating a point inside the point cloud goes like this: 1 Right-click somewhere within a viewer. 2 Pick Find from the Point Cloud’s submenu in the contextual menu. 3 Enter the point’s name and click OK.

Finding a point cloud using the viewer contextual menu Should a point matching the name you typed turn up, it gets selected in the point cloud and lit yellow. TIP: The Point Cloud Find function searches with case sensitivity. A point called “tracker15” won’t turn up when you search for “Tracker15”.

### Renaming a Point in the Cloud

The Point Cloud contextual menu lets you rename a point you’ve selected. It applies to one point only. You can’t rename a group of points at once.

### Publishing a Point

When you want a point’s XYZ positions available to wire to other controls in the scene, publish the point. That’s handy for tying objects to how a single tracker moves. To publish a point, right-click it and pick Publish from the contextual menu.

### Publishing a point using the viewer contextual menu
