# 3D Compositing Basics (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### 3D Compositing Basics

Here we walk through many of the nodes that build 3D composites, what each one does, and the ways they pair up so you can assemble convincing 3D scenes.

### An Overview of 3D Compositing

Conventional image-layer compositing happens in two dimensions. Stacked images carry just enough depth to mark one layer as the foreground and another as the background. That clashes with how production actually works, because every image is either shot through a live-action camera that moves freely along all three axes within a scene that genuinely has depth, or it originates inside a real 3D modeling and rendering package. The Fusion Node Editor gives you a GPU-accelerated 3D compositing space with support for imported geometry, point clouds, and particle systems, letting you handle jobs like these:

- Converting 2D images into image planes in 3D space
- Creating rough primitive geometry
- Importing mesh geometry from FBX or Alembic scenes
- Creating realistic surfaces using illumination models and shader compositing
- Rendering with realistic depth of field, motion blur, and supersampling
- Creating and using 3D particle systems
- Creating, extruding, and beveling 3D text
- Lighting and casting shadows across geometry
- 3D camera tracking
- Importing cameras, lights, and materials from 3D applications such as Maya,

### 3ds Max, or LightWave

- Bringing in matched cameras plus point clouds out of packages like SynthEyes or PF Track

An example 3D scene in Fusion

### 3D Compositing Fundamentals

The 3D category of nodes — encompassing the Light, Material, and Texture subcategories — collaborate to build 3D scenes. You'll find nodes that author geometry, bring in geometry, reshape geometry, set up lights and cameras, and pull all those pieces into one scene. Almost every node of this kind lives together inside the 3D category of nodes found in the Effects Library.

The 3D category of nodes in the Effects Library Helpfully, you never have to declare anywhere whether the whole composition is meant to be 2D or 3D, since any quantity of 2D and 3D "scenes" can blend together fluidly into one result. That said, for everything to behave correctly, the nodes building those scenes have to be wired up in particular arrangements.

### Creating a Minimal 3D Scene

Building a 3D scene is about as simple as it gets, provided you wire the necessary nodes together correctly. The bare minimum is wiring a geometry node (a Text3D node, for example) into a Renderer3D node, which yields a 2D image you can blend with the other 2D images of your comp, as pictured below. The catch is that you'll end up with nothing more than flatly shaded geometry, though you can still tint and reposition it in the Inspector through the controls built into whatever geometry node you happen to be working with.

A basic 3D scene where a Text3D node feeds straight into a Renderer3D node

In practice, most 3D scenes you set out to build will likely involve three to five nodes so the result is framed and lit more effectively. The typical set includes:

- Any single geometry node on offer (for instance Text3D or Image Plane 3D)
- A light node (such as DirectionalLight or SpotLight)
- A camera node
- A Merge3D node
- A Renderer3D node

Wire all of these up the way the illustration below shows, producing the correspondingly richer 3D scene also pictured below.

That same text, now framed and lit by wiring Text3D, Camera, and SpotLight nodes into a Merge3D node Here's a quick run-through of how this node tree functions: the geometry node (Text3D in this case) builds an object for the scene, then the Merge3D node acts as a virtual stage where that geometry meets the light and camera nodes, yielding a framed, lit outcome complete with highlights and shadows, and finally the well-named Renderer3D node renders that 3D scene into a 2D image you can subsequently combine with the rest of the 2D images in your comp. These nodes matter so much, in fact, that they sit at the right end of the toolbar, letting you spin up 3D scenes any time the need arises. Notice that the left-to-right sequence of the 3D toolbar buttons mirrors the usual order in which you reach for these nodes. As a result, clicking each button in turn from left to right is guaranteed to lay down a correctly built 3D scene that's ready for further work, just as the previous screenshot shows.

The 3D nodes available from the toolbar include the ImagePlane3D, Shape3D, Text3D, Merge3D, Camera3D, SpotLight3D, and Renderer3D nodes

### The Elements of a 3D Scene

Every 3D node falls into one of several groupings.

### Geometry Nodes

To bring 3D geometry into a comp, reach for the ImagePlane3D node, the Shape3D node, the Cube3D node, or the Text3D node, or alternatively import a model through the FBX Mesh 3D node. On top of that, pEmitter nodes let you add particle geometry to your scenes. Any of these can feed into a Merge3D node, whether on their own or several at a time, so you can build rich results out of multiple combined pieces. A richer 3D scene that brings together a number of geometry nodes, among them the Text3D, Shape3D, and ImagePlane3D nodes Texturing Geometry On its own, a geometry node carries nothing but a single flat color. You can change the appearance of 3D geometry, though, by texturing it with clips (stills or footage), by routing it through material nodes like the Blinn and Phong nodes to build richer textures from blends of 2D images and environment maps, or by grabbing a ready-made shader out of the Templates > Shader bin of the Effects Library, which is stocked with materials and texture presets you can drop straight in. For basic geometric primitives, texturing is as easy as wiring an image (a still or footage) or a Templates-bin shader from the Effects Library directly into the material input of a Shape3D, Cube3D, or another node that accepts it, as the figure below illustrates.

An image fed into the material input of a Shape3D node configured as Torus — the source image at left, and the textured torus at right When it comes to shading or texturing Text3D nodes, the texture has to be applied a particular way, because each such node is really a scene whose individual 3D objects (the characters) operate together. The example that follows applies the RustyMetal shader preset onto a Text3D node by way of the ReplaceMaterial3D node. What's notable about the ReplaceMaterial3D node is that it textures every geometric object in a scene simultaneously — so dropping a ReplaceMaterial3D node downstream of a Text3D node textures all of that node's characters. Place a ReplaceMaterial3D node after a Merge3D node instead, though, and you'll retexture every last geometric object being merged in that Merge3D node, which is a powerful thing to be able to do.

Texturing the geometry from a Text3D node by routing a shader through a ReplaceMaterial3D node placed downstream of whichever object you mean to shade

### The Merge3D Node

A Merge3D node pulls the output of one or several 3D nodes into a unified scene. In contrast to the Merge2D node, scene ordering here isn't confined to just foreground and background inputs. The Merge3D node instead accepts as many inputs as you care to attach, and the combined output reflects where each object sits in absolute 3D space. Pulling numerous objects into a single 3D scene by way of the Merge3D node Combining Objects Directly The Merge3D node offers an organized route to combining objects, but you can equally well join 3D objects such as Text3D and Shape3D nodes by wiring one 3D object node's output into the input of another, as the next screenshot demonstrates. Doing so means you'll rely on each node's own internal transform parameters to directly set position, size, and rotation, yet a downstream 3D object node's transform control also drives every upstream 3D object node along with it. The same holds for lights and the Camera3D node, which is a quick way to bundle objects that always belong together — a bundle you can wire into a Merge3D node afterward for extra lighting and an eventual hookup to a Renderer3D node.

Joining one Shape3D node straight into another to merge them Transforming the final downstream 3D object carries every upstream object along with it; the last Shape3D node is the one being viewed, with both visible Combining Multiple Merge3D Nodes On top of that, one Merge3D node can be joined to another Merge3D node, so you're able to assemble compound 3D scenes built from several "sub-scenes," each one constructed inside its own Merge3D node.

You can build elaborate scenes using multiple Merge3D nodes connected together

### Lighting Multiple Merge3D Nodes

After you've joined several Merge3D nodes, there's a simple mechanism for governing the degree to which lights wired into upstream Merge3D nodes reach the output of other Merge3D nodes sitting downstream. The Controls tab of every Merge3D node holds one checkbox, Pass Through Lights, that allows lighting to carry through an upstream Merge3D node's output so it falls on objects attached to downstream Merge3D nodes.

Switching on Pass Through Lights lets lights wired into upstream Merge3D scenes illuminate the downstream Merge3D scenes too By default this checkbox is off, so you can light objects in one Merge3D scene without fretting over whether that lighting bleeds onto geometry hooked into other Merge3D nodes further down the chain. As an illustration, you might want a spotlight to brighten a building wall inside one Merge3D node and not have it spill across the grass or pavement at the base of that wall built in a separate Merge3D node. In the figure below, the left image shows the cone and torus wired to a downstream node staying dark beneath the light in an upstream node while Pass Through Lights is off, whereas the right image shows everything lit once Pass Through Lights is switched on.

On the left, lights striking the text inside one Merge3D node leave the cone and torus that were added in a downstream Merge3D node untouched. On the right, switching Pass Through Lights on within the upstream Merge3D node causes those same lights to fall on the downstream shapes as well.

### Transforming Merge3D Scenes

A Transform tab is part of every Merge3D node. The transform parameters there move, scale, and rotate every object gathered inside that Merge3D node as a group, lighting and particles included. Each of these transformations pivots around one shared point. That mechanism underpins parenting throughout the 3D environment. When you transform a Merge3D node that's wired to other Merge3D nodes, the outcome hinges on whether the node you're transforming is upstream or downstream:

- Transform a downstream Merge3D node and every upstream node feeding it moves along too, behaving as though the whole thing were one scene.
- Transform an upstream Merge3D node, by contrast, and the downstream Merge3D nodes stay put, which lets you confine a transform to just that one node's scene.

### The Transform tab of a Merge3D node

### Transforming Upstream, Lighting Downstream

In intricate scenes made from many combined Merge3D nodes, a frequent approach is to reserve one final downstream node for gathering the light and camera nodes that illuminate the finished scene, while keeping the upstream Merge3D nodes available for handling object transforms and animation. That way you can move and animate portions of the overall scene without the risk of inadvertently disturbing the scene's master lighting setup or cameras — unless of course you've deliberately wired upstream lights or cameras that are supposed to travel with the geometry you're transforming.

A sample 3D scene driven by several cooperating Merge3D nodes; the upstream Merge3D nodes lay out the 3D objects in the scene, and the final Merge3D node (orange) handles the framing and lighting.

### The Renderer3D Node

Each 3D node you place emits a full 3D scene. That differs from most conventional 3D modeling and animation software, where every object lives within a single global scene environment. What it means is that the scene from a Camera 3D node and the scene from an image plane stay independent until a Merge3D node fuses them into one scene, and that Merge3D node itself emits a complete 3D scene. This 3D scene data, however, can't be composited against the other 2D images in your comp, nor can it be rendered out, until a Renderer3D node first renders it inside the node tree. Put more precisely, 3D nodes that emit 3D scenes can't be wired straight into inputs expecting 2D images. As an example, an ImagePlane3D node's output won't connect directly to a Blur node's input, and a Merge3D node's output won't connect straight into an ordinary Merge node. You first have to drop a Renderer3D node at the tail of your 3D scene to convert it into 2D images, which you can then composite and tweak exactly like any other 2D image in the comp.

A Merge3D output wired into a Renderer3D node so the result becomes 2D image data To make its image, the Renderer3D draws on one of the scene's cameras (usually one wired to a Merge3D node). When it locates no camera, it falls back to a default perspective view. Because that fallback view seldom lands on a helpful angle, most artists construct their 3D scenes with a camera or more included. Whatever the Renderer3D outputs can be set to any resolution, with choices for fields processing, color depth, and pixel aspect.

### Software vs. GPU Rendering

With the Renderer3D node you pick either a software renderer or an OpenGL renderer, swapping some measure of rendered image quality for speed, and swapping depth of field rendering for soft shadow rendering, according to what a given piece of your comp calls for. You pick the rendering method from a Renderer Type pop-up menu, which the Inspector shows on the Controls tab among each Renderer3D node's parameters. Software Renderer is the default.

The Renderer Type option in the Controls tab of a Renderer3D node

### Software Renderer

For producing the final output, the software renderer is the usual pick. The software renderer isn't the speediest way to render, but it carries two benefits. The first is that the software renderer copes easily with textures far bigger than half your GPU's largest texture size, so reach for the software renderer whenever your texture images run past 8K and you want the best possible quality.

The second benefit is that you need the software renderer to render "constant" and "variable" soft shadows whose Spread is adjustable, something the OpenGL renderer simply can't do. Such soft shadows look more natural; you switch them on within the Shadows parameters in the Controls tab of light nodes, where you pick a Sampling Quality and a Softness type and set the Spread, Min Softness, and Filter Size sliders. The software renderer also honors alpha channels inside shadow maps, so transparency can vary how dense a shadow appears.

With the Renderer3D node "Renderer Type" drop-down on OpenGL Renderer, soft shadows and outsized textures are off the table (left). Switch that same dropdown to Software Renderer, and higher-quality textures plus soft shadows become available (right).

### OpenGL Renderer

To render the image, the OpenGL renderer leans on your machine's GPU; the geometry and textures get uploaded to the graphics card, and OpenGL shaders then generate the output. This path can yield high-quality images that work perfectly for final rendering, and it can run potentially many times quicker than the software renderer, though it does come with restrictions on certain rendering effects — soft shadows can't be drawn, and the OpenGL renderer additionally disregards alpha channels while rendering shadows, so a shadow is always thrown by the whole object. Because it's so fast, on the other hand, the OpenGL renderer surfaces extra Accumulation Effects controls that switch on depth of field rendering for shallow-focus looks. The snag is that you can't get soft shadow rendering and depth of field rendering at the same time, so for any one 3D scene you render you'll have to decide which matters more. Don't Forget That You Can Combine Rendered Scenes in 2D It might feel like a hard wall that one renderer can't put out both soft shadows and depth of field, but remember that you're free to build several 3D scenes — each on a different renderer — and bring them together in 2D afterward. Beyond that, you can also render auxiliary channels that feed 2D image processing nodes such as AmbientOcclusion, DepthBlur, and Fog, building pseudo-3D effects from the images you've rendered.

### OpenGL UV Renderer

Pick the OpenGL UV Renderer option, and a Renderer3D node puts out an "unwrapped" rendition of the textures sitting on the upstream objects, at whatever resolution you've set in the Image tab of that Renderer3D node.

On the left, a 3D scene rendered the usual way; on the right, that very scene put through the Renderer3D node's OpenGL UV Renderer mode That special output image serves to bake texture projections or materials down to a texture map, for either of two purposes:

- Baking out projections can speed up a render.
- Baking projections down also frees you to edit the texture with the comp's other 2D nodes,

or even through third-party paint software (assuming you write this image out on its own as a graphics file) before you map it back onto the geometry. Imagine, say, that you've got a scene at a street corner where a shop sign carries a phone number you'd like to alter. Track the scene, hold standing geometry for the sign, and you can project the footage onto that geometry, run a UV render, swap the digits with a Paint node, and then reapply the result to the mesh through a Texture2D. Retouching textures is another job the UV renderer handles well. You might stitch together several DSLR stills of a place, project them all onto the mesh, render out the UV, fix up the seams, and reapply it to the mesh. Or you could project tracked footage of a road full of cars, UV render the projection off the geometry, run a temporal median filter over the frames, and lay a "clean" road surface back down.

### Loading 3D Nodes into the Viewer

Loading a 3D node into the viewer flips it to a 3D Viewer, where you can pan, zoom, and spin the scene in 3D so that making adjustments in three dimensions is straightforward.

### The 3D Viewer

How well the interactive 3D Viewer performs hinges heavily on the machine's graphics hardware, since it depends on OpenGL support. Your workstation GPU's onboard memory, along with its speed and feature set, dramatically affects how fast and capable the 3D Viewer is. Load any node carrying a 3D output into any viewer and that viewer's display type changes to a 3D Viewer. At first, the scene's contents show through a default perspective view.

### A 3D Viewer's default perspective view

You change the viewpoint by right-clicking inside the viewer and picking the viewpoint you want from those offered in the Camera submenu. As a shortcut to that Camera submenu, right-click the axis label shown in the viewer's bottom corner.

Right-click the Axis label of the viewer to change the viewpoint Alongside the standard Perspective, Front, Top, Left, and Right viewpoints, any cameras and lights present in the scene as candidate viewpoints appear too. You can even view the scene through a Merge3D or Transform3D by choosing it from the contextual menu's Camera > Other submenu. Moving through the scene and observing it from a range of viewpoints aids positioning, alignment, and lighting, plus other facets of your composite.

Cameras, lights, plus Merge3D and Transform3D nodes you're able to jump to all appear in the Perspective drop-down menu as well.

### Navigating the 3D View

By and large, panning and scaling the 3D Viewer relies on the same controls the 2D Viewer uses. For fuller detail on the choices the 3D Viewer provides, turn to "Using Viewers." — that's Chapter 69 of the DaVinci Resolve Reference Manual, or Chapter 7 within the Fusion Reference Manual. Panning in a 3D Viewer goes like this:

- Hold the middle mouse button and drag in the viewer.

To dolly (zoom) in the 3D Viewer, do one of the following:

- Press and hold both the middle and left mouse buttons, then drag sideways inside the viewer.
- Keep the Command key held while you work the scroll control on your pointing device.

To rotate around the 3D Viewer, do the following:

- With the Option key held, middle-button-drag from side to side within the viewer.

To frame particular objects within the viewer: 1 Pick the viewer where you intend to work. 2 Do one of the following:

- Press Shift-F to Fit all objects in the viewer.
- Hit F for Fit to selection (or, with nothing selected, Fit All).
- Hit D to Rotate the viewer so it faces the middle of whichever object is selected without

shifting where the viewer sits. On top of that, picking a 3D node in the Node Editor likewise picks its matching object in the 3D Viewer.

### Transforming Cameras and Lights Using the Viewers

When the viewer looks through a 3D object in the scene — a camera or spotlight, say — the ordinary panning and rotating controls for the viewer now act straight on the position of whatever camera or spotlight you're peering through. Here's an example. To reposition a camera while you're viewing through it: 1 Right-click the viewpoint label and pick a camera off the contextual menu. (Optional) In dual-viewer mode, you can drop the camera you chose in one viewer into the second viewer so you can watch its position as you go. 2 Bring the pointer over into whichever viewer is showing that camera's viewpoint. 3 Drag with the middle and left mouse buttons held to zoom that viewer, middle-clickdrag to pan it, or option-middle-click-drag to spin it — and in every case the camera moves right along with you.

Once a viewer is showing what a camera or light sees, panning, zooming, or rotating that viewer (at right) really moves the very camera or light you're looking through (at left) The scene can even be observed from a Merge3D or Transform3D node's vantage point by choosing that object from the Camera > Others menu. The very same transform techniques will then reposition the object. That comes in handy when you're attempting to point an object a particular direction.

### Transparency Sorting

Although a 3D scene's geometry order normally follows the Z-position of every object, sorting each face of each object across a big scene can eat up a tremendous amount of time. For the best achievable performance, the OpenGL renderer and viewers fall back on a Fast Sorting mode. You set it by right-clicking in the viewer and picking Transparency > Z-buffer. That route is far quicker than a complete sort, yet it can also give wrong results once scene objects turn partly transparent. The Sorted (Accurate) mode is there to carry out a more precise sort, trading away some performance to do it. You choose that mode from the Transparency menu in the viewer's contextual menu. A Transparency menu also appears on the Renderer3D whenever its Renderer Type is set to OpenGL. Sorted mode won't support shadows under OpenGL. The software renderer relies on the Sorted (Accurate) method at all times.

### Transparency Sorting in the viewer contextual menu

The simple guideline: reach for the Full/Quick Sort modes whenever a scene holds overlapping transparency, and otherwise stick with Z-buffer (Fast). Should the Full Sort method prove too sluggish, fall back to Z-buffer (Fast).

### Material Viewer

Viewing a node drawn from the 3D > Material category of nodes in the Effects Library makes the viewer flip over to a Material Viewer automatically. That Material Viewer lets you preview the material as it sits on a lit 3D sphere, rendered with OpenGL by default.

### The Material Viewer mode of the viewer
