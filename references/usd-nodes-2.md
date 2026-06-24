# Usd Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

The uRenderer node uRenderer Node Introduction Turning the USD 3D scene into a 2D image is the job of the uRenderer node, which draws on either a default perspective camera or one of the cameras present in the scene. Any USD scene within a composition ends at one uRenderer node or more.

### Inputs

Two inputs feed the uRenderer node. Its primary scene input accepts the uMerge or whatever other USD nodes require conversion to 2D, while the effect mask constrains the uRenderer output. SceneInput: A required input, the orange scene input takes in a USD scene you intend to convert to 2D. EffectMask: A 2D image fed to the blue effects mask input masks the node's output.

### Basic Node Setup

A uRenderer node has to close out every USD scene. Its role is to turn a 3D scene into a 2D image. In the example below, the uRenderer node receives the output of a uMerge node and renders the 3D scene as a 2D image.

Here the uRenderer node receives what the uMerge node feeds it and collapses it down to a 2D image for display.

### Inspector

### USD Renderer controls

### Controls Tab

Camera Use the Camera menu to pick which of the scene's cameras renders the image. With the Default setting, the first camera the scene contains is used; when none is found, the default perspective view steps in instead.

Renderer Type The render engines on offer are listed in this menu. At present, Storm is the sole renderer available. Output AOVs As Layers Permits AOVs to come out as layers, leaving you free to render every required element from a single uRenderer. Tick the Output AOVs as Layers checkbox and each existing AOV emerges as its own separate layer. AOV AOV, or Arbitrary Output Variable, refers to extra passes the render can produce; these go by Deep Channels or Auxiliary channels as well. Color is one example; Depth and Camera Depth are others.

- Color: Produces the chief full-color render of the USD scene, textures and lighting included
- Depth: Produces a black-and-white depth map. This depth map gets normalized on every frame, presenting dynamic black-to-white values.
- PrimID: Produces a numeric value per distinct prim within the USD scene.
- Camera Depth: Produces a precise camera depth map, computing where the camera sits

relative to the USD scene. Rendered as a float 32bit image, it looks black on first sight. Lighting Governs the manner in which the USD scene gets lit.

- None: Disables all lighting.
- Camera: Enabled objects are lit by the default camera light
- Scene: Enabled objects are lit by any lights in the USD scene.
- Enable Sky Dome: When ticked, the sky dome texture shows up and is rendered

out of the uRenderer. Complexity Sets the level of detail rendered: Low, Medium, or High detail. Aux Channel Z Switching this option on renders the Z channel, the depth channel that captures how far each pixel sits from the camera. With it enabled, the camera depth map renders to the Z channel. Film Back Fit Sets how the rendered image is fitted to the camera's Film Back. When the rendered images don't share the same relative dimensions as the film back, these options decide how the image should be fitted. Max Iterations Sets how many iterations of the rendering algorithm get processed.

### USD Renderer Image controls

### Image Tab

Process Mode: Picks whether the node's output is handled as Full Frames or through one of the listed interlaced methods. Image: Governs the output image's size and aspect ratio.

- Width/Height: Sets the pixel dimensions of the node's output.
- Pixel Aspect XY: Sets a custom pixel aspect ratio for non-square video formats.
- Auto Resolution: Matches the resolution to the Timeline resolution. Clear it to set the

width/height above by hand.

- Depth: Sets the bit depth of the uRenderer's output by hand.

Domain Overscan Permits extra pixels to render beyond the data window, useful for things like camera stabilization and lens distortion operations. Overscan Permits extra pixels to render beyond the display window, useful for things like camera stabilization and lens distortion operations. Render Color Space Lets you render the output into Linear or sRGB color spaces.

Source Color Space The Color Space Type menu fixes the media's color space to support a linear workflow. Unlike the Gamut tool, it performs no actual color space conversion; instead it writes the source space data into the metadata when that metadata isn't already there. Downstream, that metadata can then feed a Gamut tool set to From Image, or a Saver where explicit output spaces have been defined.

- Auto: Passes along any metadata that might be in the incoming image.
- Space: Lets the user pick the color space among an assortment of options.

Source Gamma Space The Curve Type menu either detects automatically or lets you pick the image's Gamma setting, and offers the choice to strip the Gamma curve away to support a linear workflow.

- Auto: Carries forward whatever metadata the incoming image may hold.
- Space: Lets you pick a particular setting from a Gamma Space drop-down menu, while a

visual graph shows you a depiction of the gamma setting you chose.

- Log: Much like the Log-Lin node, this option surfaces particular log-encoded gamma profiles so

you can pick whichever one suits your content. A visual graph depicts the log setting you chose. Pick Cineon from the Log Type menu and extra options appear for fine-tuning the gamma output: Lock RGB, Level, and Soft Clip, along with Film Stock Gamma, then Conversion Gamma plus a Conversion table.

- Remove Curve: Based on the chosen gamma space, or the gamma space detected under Auto mode, the matching gamma curve is stripped from the material, in effect converting it to output in a linear color space.
- Pre-Divide/Post-Mujltiply: Where needed, lets you turn "straight" Alpha channels into pre-multiplied Alpha channels.

### Common Controls

Settings Tab Other USD nodes carry a duplicate of the Inspector's Settings tab as well. Full descriptions of these common controls appear in this chapter's closing "The Common Controls" section.

### uReplaceMaterial [uRM]

The uReplaceMaterial node uReplaceMaterial Node Introduction With the uReplaceMaterial node you can swap an object's material for a new one. That new material may be a standard color material, a texture file, or a MaterialX file. You can apply it to every object in the scene, or confine it to particular objects via the Prim Selection controls.

### Inputs

Two inputs feed the uReplaceMaterial node. Scene Input: A USD scene file from a uLoader tool is what the yellow input takes in. Material Input: Material files arrive at the green input from assorted tools such as uMaterialX, uShader, or even pulled from a separate USD scene through a uLoader tool. Image Input: Whether you're texturing a USD object or lighting a scene with uDomeLight, the Image Input lets you draw frames from any existing Fusion node. That hands you the choice of feeding in Fusion tools (video inputs and generated graphics among them) rather than a pre-rendered image to serve as a texture. Once it's connected, the Inspector hides the File Name control, and the Image Input takes precedence over whatever image file was previously sourced. Tying a node to the Image Input on uShape or uReplaceMaterial lays the image down as a diffuse texture. Where the File Name option only sources a single frame as a texture, the Image Input opens the door to animated textures, lending more flexibility to lighting and texturing.

### Basic Node Setup

Connect the material output to the rest of the USD tools.

A straightforward node tree where a uReplaceMaterial tool receives input from a USD scene named Walkstop, swaps out a material in that scene, and then hands the scene off to a uTransform node so its transform parameters can be tweaked.

### Inspector

### The uReplaceMaterial controls

### Controls

With the uReplaceMaterial controls you alter which materials a USD scene uses.

- Prim Selection: Pick brings up the Scene Tree window, where you single out particular materials or objects within a USD scene.

Invert Prim Selection: Tick this box and the Prim Selection inverts, leaving out the materials or objects sitting in the Selected Prims box.

- Type: Choose which kind of material should take the original's place.

Color: Picks a standard Color material and opens the color controls. Texture: Brings up a file requester for loading a texture file. MaterialX: Brings up a file requester for loading a MaterialX file, or for choosing a Material from a file tied to the node's green Material input. Pick this option and every other control closes.

- Diffuse: Lets you recolor the material or load a texture.

Color: Brings up a standard color picker for choosing the material's new color. Red: Tunes how much red is in the Material. Green: Tunes how much green is in the Material. Blue: Tunes how much blue is in the Material.

- Emissive: Emissive lends a shape a global lighting effect, laying a color layer over the texture already there. Its intensity is adjustable across various levels, and it serves to mimic the emission of light.

Color: Brings up a standard color picker for choosing the lighting's new color. Red: Tunes how much red is in the lighting. Green: Tunes how much green is in the lighting. Blue: Tunes how much blue is in the lighting.

- Workflow Mode: Lets you set the mode between Metallic and Specular.
- Metallic: Once enabled, this control reveals the Metallic slider. That slider lends objects a reflective

character, conjuring the look of metal and boosting a shape's reflective properties.

- Specular: Once enabled, this surfaces the Specular Color controls. Specular Color fixes the color of light bouncing off a shiny surface; the more specular the material, the glossier its look.
- Roughness: Shapes how much light a surface reflects and scatters, lending it a smoother or rougher appearance per the setting. It's central to producing believable reflections.
- Clearcoat: Alters a surface's look by laying a glossy layer over it, imitating a protective coating. Materials such as car paint or polished metal commonly use it.
- Clearcoat Roughness: Dials in how flawed or smooth that overlaid glossy layer appears. It can sway the realism and reflection of materials like car paint or polished metal.
- Opacity: Cuts the opacity of the material and object, affecting the shape's color and Alpha values.
- Opacity Threshold: Tunes the point at which opacity begins showing.

### Common Controls

Settings Tab The Inspector's Settings tab is replicated across other USD nodes too. You'll find these common controls covered thoroughly within the "The Common Controls" section that closes this chapter.

### uShape [uSh]

The USD Shape node uShape Node Introduction The uShape node serves to generate a handful of basic primitive 3D shapes, among them capsule, torus, planes, cubes, spheres, and cylinders.

### Inputs

Image Input: As you texture a USD object — or light a scene using uDomeLight — the Image Input makes it possible to pull frames out of any existing Fusion node. This lets you supply Fusion tools (such as video inputs and generated graphics) in place of a pre-rendered image to act as a texture. After connection, the Inspector's File Name control disappears, and the Image Input supersedes any image file sourced earlier. Hooking a node up to the Image Input on uShape or uReplaceMaterial puts the image down as a diffuse texture. Whereas the File Name option draws in just one frame as a texture, the Image Input makes animated textures possible, granting added flexibility in lighting and texturing.

### Basic Node Setup

The uShape node turns out a 3D shape that's then merged with a uCamera node so you can adjust the view.

### Inspector

### The USD Shape Controls

### Controls Tab

Shape This menu is where you select which primitive geometry the Shape 3D node builds. The rest of the Inspector's controls adapt to match your chosen shape. The available Shape primitives: Capsule, Cone, Cube, Cylinder, Ico sphere, Plane, Sphere and Torus. Double Sided Gives the polygons a pair of faces, letting them receive lighting from both sides. Lock Width/Height/Depth Only for Plane and Cube shapes. Tick this checkbox and the width, height, and depth controls bind together into one size slider; leave it unticked and you get separate control over the shape's size along each axis. Size Width/Height/Depth Only for Plane and Cube shapes. Governs how big the shape is. Radius With a Capsule, Sphere, Cylinder, Cone, or Torus chosen in the shape menu, this control sets the chosen shape's radius. Height With a Capsule, Cone, or Cylinder chosen in the shape menu, this control sets the chosen shape's height. Top Radius With a cone chosen in the Shape menu, this control defines a radius for the cone's top, which makes truncated cones possible. Subdivision Level/Base/Height/Cap/Cylinder The Subdivision controls govern the mesh tessellation on every shape. A higher subdivision means more vertices and polygons per shape.

Subdivision Scheme Which algorithm tessellates the polygons in the shapes is set by the Subdivision Scheme. The methods are None, Bilinear, Loop and Catmull-Clark. Angle With the Capsule, Cone, Cylinder, Sphere, or Torus shape chosen in the Shape menu, this range control sets how much of the shape gets drawn. A start angle of 180° together with an end angle of 360° would render only half the shape. Latitude With a Sphere or Torus chosen in the Shape menu, this range control crops or slices the object by carving out a latitudinal subsection of it. Cap Bottom/Top With Cylinder or Cone chosen in the Shape menu, the Bottom Cap and Top Cap checkboxes decide whether these shapes get end caps or are left open Section With the Torus chosen in the Shape menu, Section governs the thickness of the tube that forms the torus.

### Material Tab

### The USD Shape Material controls

Diffuse Mode Diffuse captures a surface's base traits, leaving out extras such as reflections or specular highlights.

- Color: Supplies controls for adjusting the shape's diffuse color.
- Texture: This control lets a source image serve as the diffuse surface color. Press the

Browse button to bring up the file browser and pick an image file. Emissive Emissive lends a shape a global lighting effect, laying a color layer over the texture already in place. Its intensity is adjustable across various levels, and it can mimic the emission of light.

Workflow Mode Lets you set the mode between Metallic and Specular.

- Metallic: Once enabled, this control reveals the Metallic slider, which lends objects a reflective character, conjuring the look of metal and strengthening a shape's reflective properties.
- Specular: Once enabled, this surfaces the Specular Color controls. Specular Color fixes the color of light bouncing off a shiny surface; the more specular the material, the glossier its look.

Roughness Shapes how much light a surface reflects and scatters, lending it a smoother or rougher appearance per the setting. It's central to producing believable reflections. Clearcoat Alters a surface's look by laying a glossy layer over it, imitating a protective coating. Materials such as car paint or polished metal commonly use it. Clearcoat Roughness Dials in how flawed or smooth that overlaid glossy layer appears, which can sway how realistic and reflective materials such as car paint or polished metal look. Opacity Cuts the opacity of the material and object, affecting the shape's color and Alpha values.

### Common Controls

Transform and Settings Tab Other USD nodes likewise duplicate the Inspector's Transform and Settings tab. Detailed coverage of these common controls sits at this chapter's end, in the "The Common Controls" section.

### uSwitch [uSw]

The uSwitch node uSwitch Node Introduction Much like Switch, uSwitch works in a comparable way but is built specifically for the USD environment. uSwitch is a tool letting artists flip among several USD input sources and pick a single output from whichever inputs they've chosen. That makes it particularly handy for switching between different visual elements inside a composition. The count of input connections is flexible, the node accommodating a dynamic number of inputs that can be renamed at will. Controls on the Config tab let users add or drop inputs and rename them.

### Inputs

A uSwitch node accepts as many as nine inputs, added via the slider in the Config tools. Need more than nine sources? You can type that figure straight into the Number of Inputs field.

### Basic Node Setup

Hook up however many input sources you want to the uSwitch Node, then wire its output into the remainder of the node tree.

The uSwitch tool taking in five USD media inputs, letting you select one to send out to uRender.

### Inspector

Through the uSwitch controls you select which source passes through the switch.

### Controls

A Source switcher makes up the Switch Controls, letting you decide which source passes through the switch.

### The uSwitch configuration

### Config

Through the uSwitch configuration you set the input count and rename them.

- Number of Inputs: Drag the slider to set how many inputs you want, up to nine. For more than nine inputs, click into the number field and enter the figure by hand.
- Name X: A numerical input name can be swapped for something more descriptive.

### Common Controls

Settings Tab Across the other USD nodes, the Inspector's Settings tab appears in duplicate form too. A thorough rundown of these common controls lives in the closing "The Common Controls" section of this chapter.

### uTransform [uXF]

The USD Transform node uTransform Node Introduction When your USD scene holds several objects or prims, the uTransform node lets you single out individual groups of objects and adjust their transform on their own, apart from the rest of the scene.

### Inputs

One required input for a USD scene or USD object feeds the uTransform node. Scene Input: Wire the orange scene input to a USD scene or USD object to layer on a second set of transformation controls.

### Basic Node Setup

The uTransform node layers 3D position, rotation, and pivot control on top of whatever transforms already exist in the USD node ahead of it. Chaining several uTransform nodes together lets you construct parenting or hierarchical movement.

The uTransform node hands you a further set of 3D transform controls, usable for tweaking the ones in the uShape node's Transform tab.

### Inspector

### The USD Transform controls

### Controls Tab

Pick Pick brings up the Scene Tree window, where you single out particular materials or objects within a USD scene. For more on working with the USD Scene Tree, consult its section near this chapter's start. Translation Transform controls serve to place the USD shape within 3D space.

Rotation Order These buttons set the order in which rotation is applied along each axis of the object. XYZ, for instance, would rotate the X-axis first, then the Y-axis, and finally the Z-axis. Rotation Use these controls to spin the shape about its pivot point. With the Use Target checkbox ticked, rotation is relative to the target's position; otherwise the global axis governs it. Pivot An object's pivot point is the spot it rotates around. By default an object turns about its own center, treated as a pivot of 0,0,0. These controls let you shift the pivot off the center. Scale With the Lock X/Y/Z checkbox ticked, a single scale slider appears that resizes the object overall. Leave the Lock checkbox unticked and separate X, Y, and Z sliders show up so you can scale along any dimension. Scale Ticking the Use Target checkbox brings up a set of controls for positioning an XYZ target. With the target on, the object continually rotates to face it, and the object's rotation becomes relative to the target.

### Common Controls

Settings Tab The Settings tab found in the Inspector is mirrored on the other USD nodes as well. These common controls receive a full explanation in the "The Common Controls" section wrapping up this chapter.

### uVariant [uVa]

The uVariant node uVariant Node Introduction Hooking the uVariant node up to the USD loader lets you flip among the various alternatives, or "variants," that have been defined for assets within the USD scene.

### Inputs

One required input for a USD scene or USD object is all the uVariant node has.

### Basic Node Setup

The uVariant node lets you pick from whichever variants have been created inside a USD scene. It takes a USD scene as input.

The uVariant node accepts the input from the MonsterJumpDown USD scene.

### Inspector

### The uVariant controls

### Controls Tab

Pick Pick brings up the Scene Tree window for singling out particular materials or objects within a USD scene. For more on working with the USD Scene Tree, consult its section near this chapter's opening. Selected Prims Lists which prims have been picked. Invert Prim Selection Tick this box to trade the picked prims for the unpicked ones. Keyframes can animate this action.

Variant Set This drop-down menu reveals which of the scene elements carry variants to pick from. When no variants exist, it shows No Selection. Variant Having chosen a variant set above, the variant choices to pick between turn up in this dropdown.

### uVisibility [uVis]

The uVisibility node uVisibility Node Introduction Hooking the uVisibility node up to the USD loader lets you govern whether an object, or a whole branch of objects, in a scene is visible.

### Inputs

A lone required input for a USD scene or USD object is what the uVisibility node carries. Scene Input: Connect the orange scene input to a USD scene or USD object so a second set of transformation controls can be applied.

### Basic Node Setup

The uVisibility node takes a USD scene and then sends the visible elements onward to the rest of the node tree.

### The uVisibility node

The uVisibility tool lets you reveal or conceal individual 3D assets. Above, the cityscape model (left) has been set visible, while below it's concealed with its visible box cleared.

### Inspector

### The uVisibility controls

### Controls Tab

Pick Pick brings up the Scene Tree Dialog, where you single out particular materials or objects within a USD scene. The prims highlight in the viewer as you select them. Refer to this chapter's opening for details on working with the Scene Tree Dialog. Selected Prims Lists the prims that have been picked.

Invert Prim Selection Tick this box to swap the picked prims for the unpicked ones. Keyframes can animate this action. Visible Toggling this checkbox either adds the picked prims to the view or pulls them from it. Keyframes can animate this action.

### uVolume [uVo]

### The uVolume tool

Introduction uVolume is a flexible, capable tool that streamlines bringing volumetric VDB files into a USD environment. Through this node you can tweak VDB parameters like density, temperature, and color, handing you full command over how the imported VDB file looks and behaves.

### Usage

Adding uVolume to the Node Editor pops a File dialog open automatically so you can select a VDB file off your media drive. You may bring in either one VDB file or a VDB sequence (animated VDB). After a VDB is loaded with the uVolume node, the uVolume serves to trim, loop, and alter the speed of the imported asset.

### The uVolume controls for manipulating VDB files
