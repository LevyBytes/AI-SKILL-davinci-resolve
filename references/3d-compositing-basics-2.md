# 3D Compositing Basics (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Right-clicking the viewer and picking options from the contextual menu lets you set the kind of geometry, the renderer, and the lighting state alike. Every viewer carries A and B buffers to help you compare several materials. Ways to work with the Material Viewer:

- To swap the shape of the previewed geometry, right-click the viewer and pick an option from the contextual menu's Shape submenu. Whatever geometry the material covers is pinned to the viewer's center and scaled to fit. Neither panning nor scaling the Material Viewer is possible.
- For a different angle on the material, rotate the Material Viewer by holding Option, pressing the middle mouse button, and dragging side to side.
- The light previewing the material can be repositioned by dragging with the middle mouse button. As an alternative, right-click the viewer and pick an option from the contextual menu's Lighting > Light Position submenu.
- Lighting can also be switched on and off by right-clicking the viewer and selecting Lighting > Enable Lighting from the contextual menu.
- To set which renderer previews the material, right-click the viewer and pick an option from the contextual menu's Renderer submenu.

### Transformations

Merge3D, 3D Objects, and Transform3D each carry Transform parameters gathered into a Transform tab within the Inspector. The parameters in this tab govern how the object is positioned, rotated, and scaled inside the scene.

### The Transform tab of a Merge3D node

The Translation parameters place the object in local space, the Rotation parameters turn the object about its own center, and the Scale slider(s) change its size (which depends on whether they are locked together). Those same adjustments can be done in the viewer through onscreen controls.

### Onscreen Transform Controls

A selected object shows onscreen Transform controls in the viewers so you can set the object's position, rotation, and scale. You switch modes either with buttons in the Transform toolbar or with the keyboard shortcuts. The keyboard shortcuts for changing Transform modes are:

- Press Q for Position
- Press W for Rotation
- Press E for Scaling

The Position, Rotation, and Scale modes in the Transform toolbar

### Using Onscreen Transform Controls

Across all three modes, red stands for the object's local X-axis, green for the Y-axis, and blue for the Z-axis (just keep RGB = XYZ in mind). Drag straight on the red, green, or blue part of any onscreen control to pin the transform to that axis, or drag the onscreen control's center to transform with no constraint. Holding Option and dragging in the viewer lets you translate freely along all three axes without clicking any particular control.

From left to right, the Position, Rotation, and Scale onscreen Transform controls With the Scale's Lock XYZ checkbox turned on in the Inspector, dragging the red or center onscreen control changes only the object's overall scale, and the green and blue parts of the control do nothing. Unlock the parameters and you can scale an object on individual axes one at a time, squishing or stretching it.

### Selecting Objects

While the onscreen controls show in the viewer, click an object's center control to select it. You can equally select any 3D object by clicking its node within the Node Editor.

### Pivot

Within 3D scenes, objects turn and scale about an axis known as a pivot. By default that pivot runs through the object's center. To shift the pivot away from the object's center, reach for the X, Y, and Z Pivot parameters in the Inspector.

### Target

Targets help aim a 3D object at a particular point in the scene. Wherever the object travels, it turns in the local coordinate system so that it keeps facing its target, which you can place and animate.

To switch on a target for a 3D object: 1 Pick that object's node. 2 Within the Inspector, open the object's Transform panel. 3 Tick the Use Target checkbox.

Turning on the Use Target checkbox of a 3D object 4 Place the target with the Inspector's X/Y/Z Target Position controls or the viewer's Target onscreen control, which in turn places the object tied to it. The viewer draws a line from the target to the center of the 3D object it is attached to, conveying the link between these two control sets. Every time the target moves, the object transforms automatically to face the new position.

### A torus facing its onscreen Target controls

For instance, when a spotlight in the scene must aim at an image plane, switch on the spotlight's target in the Transform tab and tie the target's XYZ position to the image plane's XYZ position. From then on, wherever the spotlight moves, it turns to face the image plane.

A light made to face the wall using its enabled target control

### Parenting

A notable benefit of the node-based take on 3D compositing is that parenting among objects falls out implicitly from how a 3D node tree is built. Every bit of parenting rests on the Merge3D node. Connect the various 3D objects you build for your scene thoughtfully, and several Merge3D nodes can govern which groups of objects transform and animate as a unit and which do so on their own. Picture, for example, a scene holding two spheres both wired to a Merge3D. That Merge3D can spin one sphere around the other, the way the moon circles the earth. The Merge3D can then feed another Merge3D so the earth and moon orbit the sun together.

A single Merge3D whose two spheres are parented to a further Merge3D, plus parenting built from three connected spheres

The two plain rules for transforming parented Merge3D nodes are:

- Any transform or animation put on a Merge3D carries to every 3D object wired to that Merge3D node, cameras, lights, geometry, and other merge nodes connected upstream included.
- Any transform or animation put on upstream merge nodes leaves downstream merge nodes untouched.

### Cameras

As you build and animate a 3D scene, the camera metaphor ranks among the most intuitive ways to frame how you want the scene rendered and to animate your path through it. On top of that, compositing artists are often asked to match cameras drawn from live-action clips or from 3D applications. To serve all of this, Fusion supplies a flexible Camera3D node carrying familiar camera controls like Angle of View, Focal Length, Aperture, and Clipping planes, so you can either build your own camera or pull in camera data from other applications. The Camera3D node acts as a virtual camera you view the 3D environment through.

A camera shown in the viewer with onscreen Transform controls, its Focal Plane indicator switched on in green A Merge3D node usually connects and views cameras; even so, you can wire cameras upstream of other 3D objects when you want a camera to transform alongside that object as it moves.

### Quickly Viewing a Scene Through a Camera

Once a camera is in a scene, viewing it "through the camera" takes only a quick setup. To look at the scene through the camera: 1 Select the Merge3D node the camera is wired to, or any node downstream of that Merge3D. 2 Load the chosen Merge3D or downstream node into a viewer. 3 Right-click the axis label in the viewer's bottom corner and pick the camera name. Since the viewer's frame can differ from the camera frame, it may not line up with the true bounds of the image the Renderer3D node will render. When your scene has no Renderer3D node yet, you can fall back on Guides that stand in for the camera's framing. To read more about Guides, consult Chapter 69, "Using Viewers." within the DaVinci Resolve Reference Manual, or Chapter 7 of the Fusion Reference Manual.

### Plane of Focus and Depth of Field

Cameras carry a plane of focus, for whenever depth of field rendering is on hand. Here is how to switch on depth of field rendering in your scenes. To render depth of field within a 3D scene: 1 You have to add a Renderer3D node at the tail of your 3D scene. 2 With the Renderer3D node selected, choose OpenGL Renderer for the Renderer Type. 3 Open the Accumulation Effects disclosure control that shows up, then tick the Enable Accumulation Effects checkbox in the OpenGL render.

Turning on Enable Accumulation Effects enables additional depth of field controls Switching on "Enable Accumulation Effects" brings up a Depth of Field checkbox plus Quality and Amount of DoF Blur sliders for tuning the depth of field effect. These controls touch only the perceived quality of the rendered depth of field. The depth of field actually produced rests entirely on the camera's setup and its position relative to the other 3D objects in your scene. Selecting your scene's Camera3D node to view its controls in the Inspector adds a new Focal Plane checkbox to the Control Visibility group. Switching it on reveals the green focal plane indicator in the 3D Viewer, helping you picture what the Focal Plane slider does; that slider sits in the top group of parameters on the Camera3D node's Controls tab.

Turning on the Focal Plane checkbox in the Camera3D node To read more about these particular camera controls, consult Chapter 89, "3D Nodes," within the DaVinci Resolve Reference Manual, or Chapter 29 of the Fusion Reference Manual.

### Importing Cameras

To match cameras across applications, you can bring in camera paths and positions from many popular 3D applications. Fusion can import animation splines from Maya and XSI straight away in their own native spline formats. Animation on cameras from 3ds Max and LightWave gets sampled and keyframed on every frame. To import a camera out of another application, do this: 1 Select the camera within the Node Editor. 2 Down at the Inspector's bottom, click the Import Camera button. 3 Using the file browser, locate and select the scene holding the camera you wish to import. A dialog box presenting several options shows up. With the Force Sampling checkbox on, Fusion samples each frame of the motion no matter the format.

### The Select Camera dialog

TIP: For parented or rigged cameras, baking the camera animation inside the 3D application before bringing it into Fusion tends to give more dependable results.

### Lighting and Shadows

Light sources can be dropped into a scene to build richly detailed lighting environments and atmosphere. Four kinds of lights are available in 3D scenes: ambient, directional, point, and spotlights.

### Enabling Lighting in the Viewer

A scene with no lights runs on a default directional light, but that vanishes on its own the moment you add a 3D light object. Yet even after light objects join your scene, lighting and shadows stay invisible in the viewer until you first switch on lighting through the viewer contextual menu, right-clicking anywhere inside a viewer and choosing 3D Options > Lighting or Shadows to enable one or the other or both.

### Enabling Lighting to Be Rendered

The Renderer3D node renders no lighting effects until the Enable Lighting and/or Shadows checkboxes are ticked in the Inspector.

### The Lighting button under the viewer

NOTE: Whenever lighting is off in the viewer or in final renders, the image looks as though a 100% ambient light is illuminating it.

### Cotrolling Lighting within Each 3D Object

Every node that builds or merges geometry also carries lighting options for setting how each object responds to light:

- Merge3D nodes carry a Pass Through Lights checkbox that decides whether lights tied to an upstream Merge3D node also light up objects tied to downstream Merge3D nodes.
- ImagePlane3D, Cube3D, Shape3D, Text3D, and FBXMesh3D nodes carry a set of Lighting controls letting you toggle three controls: Affected by Lights, Shadow Caster, and Shadow Receiver.

Each 3D object carries its own lighting controls for steering how it reacts to light and shadows

### Lighting Types Explained

Below is a fuller account of each light type in Fusion.

### Ambient Light

Ambient light serves to establish a baseline light level for the scene, since it spreads a generally even illumination across it. Present everywhere yet seeming to issue from no particular source, ambient light casts no shadows and tends to fill in a scene's shadowed regions.

### Directional Light

A directional light consists of parallel rays that illuminate the whole scene from a single direction, forming a wall of light. The sun makes a fine example of a directional light source.

### Point Light

A point light is a sharply defined light with a small, distinct source, much like a light bulb, that radiates from that point in every direction.

### Spotlight

A spotlight is a more advanced point light that casts a sharply defined cone of light with falloff. It is the sole light that yields shadows.

From left to right: Directional light, point light, and spotlight Every Light node shows onscreen controls in the viewer, though not all controls bear on every light type. For the ambient light, position changes nothing. The directional light can be rotated, but its position and scale are disregarded. The point light disregards rotation. The spotlight responds to both position and rotation.

### Lighting Hierarchies

Lights ordinarily stay on their side of a Merge, because the Pass Through Lights checkbox is off by default. That gives you a way to govern which objects are lit by which lights. Take the two node trees below, where two shapes and an ambient light feed a Merge3D node, which then connects to a second Merge3D node that also takes a plane and a spotlight. On the left, this tree's first Merge3D node has Pass Through Lights off, so only the two shapes show up lit. On the right, Pass Through Lights is on, so both the foreground shapes and the background image plane get lit.

With Pass Through Lights off, only the two front shapes light up (left); with Pass Through Lights on, every shape wired to both Merge3D nodes lights up (right) Lighting Options Most geometry-generating nodes carry extra options for lighting. These options set how each individual object responds to lights and shadows in the scene.

- Affected By Lights: With the Affected By Lights checkbox on, scene lights act on the geometry.
- Shadow Caster: When on, the object throws shadows onto other objects in the scene.
- Shadow Receiver: With this checkbox on, the object takes on shadows.

3D objects have individual lighting controls that govern how each object responds to light and shadows Shadows Spotlight, Point Light, and Directional light are all capable of casting shadows in the 3D viewer, though Point and Directional lights require the Renderer3D node's Rendering Type to be Hardware Renderer. Spotlight runs with either the Hardware or Software renderers. By default these lights cast shadows, yet those shadows stay hidden in the viewer until you switch shadows on with the viewer toolbar button. Nor will shadows turn up in the Renderer3D output unless the Shadows option is on for that renderer. To keep a spotlight from casting shadows, turn off the Enable Shadows checkbox in the node's Inspector.

An image with spotlight casting a variable soft shadow

To read more about shadow controls, consult the "Spotlight" section within Chapter 90, "3D Light Nodes," of the DaVinci Resolve Reference Manual, or Chapter 30 of the Fusion Reference Manual.

### Shadow Maps

A shadow map is an internal depth map recording every pixel's depth within the scene. That data drives the assembly of the shadow layer a spotlight produces. You will find all the shadow map controls in the Spotlight Inspector. Shadow quality leans heavily on the shadow map's size. Bigger maps make better-looking shadows but lengthen render times. The broader the spotlight's cone, or the more falloff it has, the bigger the shadow map must be for usable quality. The Shadow Map Size control's value fixes the depth map's size in pixels. As a rule, trial and error reveals a point of diminishing returns past which enlarging the shadow map stops improving the shadow. Making shadow maps any bigger than necessary is not advised. The Shadow Map Proxy control sets a percentage by which the shadow map is scaled for quick interactive previews such as Autoproxy and LoQ renders. A value of 4, say, equals a 40% proxy.

### Shadow Softness

By default, the spotlight makes shadows with hard edges, but options exist for constant and variable soft shadows. Hard-edged shadows render markedly faster than either Soft Shadow option. Shadows lacking softness usually look aliased unless the shadow map size is big enough. Often, softness is brought in to mask the aliasing instead of enlarging the shadow map, which conserves memory and avoids overrunning the graphics hardware's limits.

### Soft Shadow controls in the Control panel

Set the spotlight's shadow softness to None and you get crisp, sharply defined shadows. The Constant option produces shadows whose softness is even throughout, no matter the shadow's distance from the casting geometry. The Variable option produces shadows that grow softer the farther they sit from the geometry casting them. That looks more realistic, though such shadows are a bit trickier to control. Choosing this option brings up extra controls for tuning the shadow's falloff, along with sliders for minimum and maximum softness.

### Hard shadow cast by a spotlight

Choosing the Variable option exposes the Spread, Min Softness, and Filter Size sliders. One side effect of the technique behind variable softness shadows is that the blur applied to the shadow map can grow effectively boundless as the shadow's distance from the geometry rises. These controls rein the shadow map in by capping the softness calculation at a sensible limit. Where that limit kicks in is set by the filter size. A larger filter size raises the shadow's greatest possible softness. Shrinking it can trim render times yet may also cap the shadow's softness or even clip it. As a value, it is expressed as a percentage of the shadow map size. For further detail, consult "Spotlight" within Chapter 90, "3D Light Nodes," of the DaVinci Resolve Reference Manual, or Chapter 30 of the Fusion Reference Manual.

### Multiplicative and Additive Bias

Shadows are basically textures laid onto objects in the scene, and now and then they "fight." Z-fighting crops up when parts of an object that ought to receive shadows instead render on top of the shadow, because they sit at the very same spot in 3D space.

What shadow map Z-fighting produces (Left), alongside the shadow corrected via Biasing (Righht)

In the Shadows group of Spotlight parameters, two Biasing sliders operate by nudging a small depth offset that pulls the shadow off the surface it shadows, clearing the Z-fighting. Too little bias and objects may shadow themselves. Too much and the shadow may pull away from the surface.

The Spotlight Inspector controls hold the Multiplicative and Additive Bias sliders together with the Non-Transmissive Materials checkbox Aim to move the Multiplicative Bias slider until most of the Z-fighting clears, then move the Additive Bias slider to wipe out what is left. A softer shadow will likely demand a higher bias. For some especially stubborn frames you may even have to animate the bias to land a proper result.

### Force All Materials Non-Transmissive

The way light travels through a semi-transparent material weighs heavily on how the shadow an object casts looks. This transmittance behavior is normally set in each object's Materials tab. Choosing Force All Materials Non-Transmissive in the Spotlight Inspector, however, overrides that, so the shadow map the node produces disregards transmittance altogether.

### Materials and Textures

Rendering a 3D scene requires the renderer to weigh both an object's shape and its appearance. An object's geometry sets its shape, while the material on the object sets its appearance. Fusion offers an assortment of ways to put materials and textures onto geometry, letting you hand your 3D objects whatever surface qualities you want. Nodes that spell out how the geometry answers to light go by the name illumination models. The illumination models bundled in are Blinn, CookTorrance, Ward, and Phong. You will find these nodes under the 3D > Material category of nodes in the Effects Library. Most materials take textures too, which are usually 2D images. Textures sharpen an object's look further by layering on photorealistic detail, transparency, or special effects. More involved textures such as bump maps, 3D textures, and reflection maps live in the 3D > Texture category as well. Materials can also be stacked to form elaborate, richly detailed composite materials. Every node that builds or loads geometry into a 3D scene also hands it a default material. That default is the Blinn illumination model, but you can replace it with one of several nodes that output a 3D material. A few of these materials grant finer control over how the geometry answers to light, offering inputs for diffuse and specular texture maps, bump mapping, and environmental maps that imitate reflection and refraction.

### Material examples from the bin

### Material Components

Every standard illumination model has traits in common that are worth grasping.

### Diffuse

A material's Diffuse parameters govern how an object looks where light is soaked up or scattered. This diffuse color and texture form an object's base look before reflections enter in. An object's opacity is usually set in the material's diffuse component.

### Alpha

The Alpha parameter sets how transparent the object is to diffuse light. It leaves specular levels and color alone. Yet should alpha's value, whether from the slider or a Material input from the diffuse color, sit at or very near zero, those pixels, the specular highlights among them, get skipped and vanish.

### Opacity

The Opacity parameter dims the entire material, the specular highlights included. This value cannot be mapped; it acts on the whole material.

### Specular

A material's Specular parameters govern the highlight of an object where light bounces toward the current viewpoint. The result is a highlight laid on top of the diffuse component. The more specular a material, the glossier it reads. Surfaces such as plastics and glass usually carry white specular highlights, whereas metallic surfaces like gold carry specular highlights that tend to pick up their color from the material color. Specularity comprises color, intensity, and exponent. The specular color decides the color of light reflecting off a shiny surface. Specular intensity sets how bright the highlight is.
