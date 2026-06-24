# Usd Nodes (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Density is tunable through the Scale control, which opens the door to careful, fine-grained tweaks. Color controls for the VDB sit in the Emission section. The Mode selection pulldown is where you pick the method used to alter the VDB's color. The available emission modes are:

- Color: Lays a single ‘diffuse’ color across the imported VDB. Keep in mind that USD lights leave a VDB untouched once its color is set to white.
- Field: Spreads one overall color into a chosen Emission Field.
- Blackbody: Derives color and intensity from temperature, which makes it a good fit for rendering fire and

explosions.

- Gradient: Lets you lay a span of colors across a designated field. The Gradient choice hands

you several controls for aiming at a field and then painting it with the colors you nominate. Standard transformation controls — the kind seen on most nodes throughout Fusion's USD suite — come by way of the uVolume.

### USD Lights

The USD light tools mark a strong expansion of Fusion's USD toolset, handing you finer control and more freedom as you build and shape the lighting across your USD scenes. Six lights ship in the USD toolset; they are:

### uCylinder Light [uCL]

The USD Cylinder light uCylinder Light Node Introduction A uCylinder light is a geometric light carrying both length and diameter, much like a fluorescent tube. It comes with an onscreen control, and translating and rotating that control positions the light within the scene.

### Inputs

A single yellow Scene Input is provided for hooking up a USD scene, after which you can tweak whatever lights already live inside it.

### Inspector

### The USD Cylinder Light controls

### Controls Tab

Color and brightness for the uCylinder light are dialed in from the Controls tab, while the Transform tab governs where the light source sits, its direction, and its scale.

Override Selection Clicking the Pick button lets you grab a light that already exists in an attached USD file, so you can adjust the lights of an imported scene. Color Reach for this standard Color control to tint the light. Intensity This slider governs the light's intensity; a setting of 0.2 stands for 20% percent light. Exposure Much like Intensity, this alters how strongly the light exposes a scene. Color Temperature/Enable This fixes a light source's color temperature, defaulting to 6500K, the temperature of daylight. Diffuse Response Governs how much the light feeds into a material's Diffuse color. Specular Response Governs how much the light feeds into a material's Specular color. Normalize This evens out the light's contribution across the scene. Treat As Line This turns the light into a plainer line light source. Length Sets how long the light is. Radius Sets the light's diameter.

### uDisk Light [uDi]

The USD Disk light uDisk Light Node Introduction This light, the uDisk, takes the form of a flat circular emitter, akin to an umbrella or softlight. You set its color and brightness from the Controls tab, whereas the Transform tab handles the light source's position, direction, and scale.

### Inputs

You get a lone Scene Input, shown in yellow, for connecting a USD scene; once attached, its existing lights become yours to modify.

### Inspector

### The USD Disk Light controls

### Controls Tab

Through the Controls tab you set the uDisk light's color and brightness, leaving the Transform tab in charge of the light source's position, direction, and scale. Override Selection Hitting the Pick button lets you select a light already present in an attached USD file, which is how you adjust the lights of an imported scene. Color This standard Color control sets the light's color. Intensity Drive the light's intensity from this slider; 0.2 corresponds to 20% percent light. Exposure Comparable to Intensity, this shifts how strongly a scene gets exposed by the light. Color Temperature / Enable This establishes a light source's color temperature, with 6500K — daylight temperature — as the default. Diffuse Response Sets how strongly the light adds to a material's Diffuse color. Specular Response Sets how strongly the light adds to a material's Specular color.

Normalize This balances out the light's contribution throughout the scene. Shaping Focus This pins down the focus point for this light's lens effect. Shaping Cone Angle Sets how broadly the light spreads. Radius Sets the light's diameter.

### uDistant Light [uDL]

The USD Distant light uDistant Light Node Introduction A uDistant light behaves like a directional light, mimicking a faraway source the way sunlight does. It carries an onscreen control whose rotation decides the direction the light points from within the scene.

### Inputs

A single Scene Input, marked yellow, attaches a USD scene and from there opens up any lights already in it for adjustment.

### Inspector

### The USD Distant Light controls

### Controls Tab

Color and brightness for the uDistant light come from the Controls tab, with the Transform tab taking care of the light source's position, direction, and scale. Override Selection Press the Pick button to pull in a light that already exists within an attached USD file, the route for adjusting an imported scene's lights. Color Use this standard Color control to choose the light's color. Intensity This slider drives the light's intensity, where 0.2 equals 20% percent light. Exposure Akin to Intensity, this changes the degree to which the light exposes a scene. Color Temperature/Enable This sets a light source's color temperature; the default, 6500K, matches daylight temperature. Diffuse Response Dictates how much the light adds toward a material's Diffuse color. Specular Response Dictates how much the light adds toward a material's Specular color. Normalize This levels the light's contribution within the scene. Angular Size Sets how broadly the light spreads.

### uDome Light [uDo]

The USD Dome light uDome Light Node Introduction A uDome light draws on SDR and HDR images, wrapping the whole scene inside a sphere light that's mapped with the image, in the manner of an environment light. Its onscreen control has a rotation that sets which direction the light points from across the scene.

### Inputs

Scene Input: links in a USD scene, which then lets you alter whatever lights are already present. Image Input: Whether you're texturing a USD object or lighting a scene through uDomeLight, the Image Input draws frames from any Fusion node already in your comp. That means you can feed in Fusion tools — video inputs and generated graphics among them — rather than relying on a pre-rendered image for the texture. Once it's connected, the Inspector hides the File Name control, and the Image Input supersedes whatever image file was sourced beforehand. Wire a node into the Image Input on uShape or uReplaceMaterial and the image arrives as a diffuse texture. Where the File Name route only pulls in a single frame as a texture, the Image Input opens up animated textures, lending more latitude for both lighting and texturing.

### Inspector

### The USD Dome Light controls

### Controls Tab

You configure the uDome light's color and brightness in the Controls tab, while the Transform tab manages the light source's position, direction, and scale. Override Selection A press of the Pick button picks out a light that's already in an attached USD file, the means by which an imported scene's lights get adjusted. Color This standard Color control assigns the light's color.

Intensity This slider sets the light's intensity, with 0.2 standing for 20% percent light. Exposure Similar in effect to Intensity, this varies the amount of exposure the light gives a scene. Color Temperature/Enable This establishes the color temperature of a light source, defaulting to 6500K, which equals daylight temperature. Diffuse Response Regulates how much the light pours into a material's Diffuse color. Specular Response Regulates how much the light pours into a material's Specular color. Normalize This smooths the light's contribution over the scene. Guide Radius This determines how big the dome wrapping the scene is. By default it's large and distant, like the outdoors, but you can shrink the radius to mimic a room-sized space. Texture File/Browse This loads an image to map onto the Domelight. Texture Format Sphere-mapped images may be held in several schemes, the usual ones being Lat-Long, MirrorBall, Angular, and Cube Mapped Vertical Cross.

### uRectangle Light [uRL]

The USD Rectangle light uRectangle Light Node Introduction This emitter, the uRectangle, presents a flat profile, comparable to a softlight or a window . Its color and brightness are set from the Controls tab, while the light source's position, direction, and scale fall to the Transform tab.

### Inputs

There's a single yellow Scene Input for connecting a USD scene, and through it you can reshape any lights the scene already contains.

### Inspector

### The USD Rectangle Light controls

### Controls Tab

The Controls tab handles setting the uDome light's color and brightness, and the Transform tab oversees the light source's position, direction, and scale. Override Selection Click the Pick button to adopt a light that already exists in an attached USD file, the way you adjust the lights of an imported scene. Color Apply this standard Color control to color the light. Intensity This slider determines the light's intensity, where 0.2 maps to 20% percent light. Exposure In the same vein as Intensity, this adjusts how much the light exposes a scene. Color Temperature/Enable This nails down a light source's color temperature; its default of 6500K equals daylight temperature. Diffuse Response Manages how much the light contributes to a material's Diffuse color. Specular Response Manages how much the light contributes to a material's Specular color. Normalize This regularizes the light's contribution throughout the scene.

Shaping Focus This marks the focus point of this light's lens effect. Shaping Cone Angle Sets the angle across which the light spreads. Width Sets how wide the light reads. Height Sets how tall the light reads.

### uSphere Light [uSL]

The USD Sphere light uSphere Light Node Introduction A uSphere light is a local light resembling a point light, except that it also carries a radius. An onscreen control accompanies it, and rotating that control settles which direction the light points from in the scene.

### Inputs

One Scene Input, colored yellow, lets you attach a USD scene, and with it attached you're free to adjust the lights already standing in the scene.

### Inspector

### Controls Tab

You dial in the uSphere light's color and brightness from the Controls tab, and the Transform tab takes over the light source's position, direction, and scale. Override Selection Pressing the Pick button picks up a light already living in an attached USD file, your means for adjusting an imported scene's lights. Color Lean on this standard Color control to set the light's hue. Intensity This slider rules the light's intensity, where 0.2 represents 20% percent light. Exposure Like Intensity before it, this changes how far the light exposes a scene. Color Temperature/Enable This sets the color temperature for a light source, with a 6500K default that matches daylight temperature. Diffuse Response Sets the degree to which the light feeds a material's Diffuse color. Specular Response Sets the degree to which the light feeds a material's Specular color. Normalize This evens the light's contribution across the scene. Treat as Point This reduces the light to a plain classic point source. Radius This sets the sphere light's size.

### USD Material

With the uTexture, uTextureTransform, uNormalMap, and uShader nodes you can pull textures straight into your USD scene and work on them there, skipping the step of bundling them into a USD file beforehand. These tools lend extra freedom and control to the USD workflow you run on the Fusion page.

A sample texture replacement node tree built from the USD Materials tools The uTexture, uTextureFormat, and uNormalMap tools are meant to surround and route a texture into the uShader tool, where the USD or MaterialX models reshape its appearance. Typically the uShader hooks into a uReplaceMaterial node, which picks out the particular regions of the whole USD scene that should receive the new texture. The upshot is that you can cycle through texture changes entirely inside Fusion, with no need to touch the original USD scene over in external 3D modeling software.

### uNormalMap [uNm]

### The USD Normal Map

### Introduction

A handful of controls in the uNormalMap tool let you tweak a “normals” texture ahead of handing it to the uShader. You can therefore work the texture over in different ways and make sure it suits exactly what you need. With whatever adjustments completed, the reworked image then travels on to the uShader.

### Usage

### The uNormal Map controls

For uNormalMap, drop it in following a uTexture node and ahead of a uShader node. It functions solely in the gap between the loaded texture and uShader.

### uShader [uSd]

The USD Shader uShader Node Introduction The uShader node builds materials and looks by drawing on either the USD or the MaterialX shader tools. Paired with uReplaceMaterial, it offers a simple, intuitive path for cycling material changes onto a USD source.

### Inputs

Variable inputs on the uShader node let you bring assorted assets into the tool — a texture, say, fed through a uTexture node. As you make a connection, a drop list presents every possible connection to pick from. Attaching a texture to any input switches off that input's slider and reveals fresh Channel, Scale, and Bias controls, so you can decide which channel the property draws on along with its strength and base values.

Connect a uTexture node onto the uShader node and a drop list appears, laying out every input available to connect to.

### Basic Node Setup

Here the uShader takes an input off the uTexture node, alters that texture, and then forwards it to the uReplace Material node. uReplace Material, in turn, is choosing particular materials out of the MonsterJumpDown USD scene onto which the freshly altered texture gets applied.

### Inspector

### The uShader controls in USD mode

### Shader Model

This is where you decide which toolset to use, picking the USD tools or the MaterialX tools.

### Shader Model: USD

Diffuse Mode Diffuse captures a surface's underlying qualities on their own, leaving out extras such as reflections or specular highlights.

- Color: Supplies controls for changing the shape's diffuse color. Emissive Emissive lays a scene-wide lighting effect onto a shape, building a coat of color above the texture already there. You can take it to varying intensities, and it serves to fake the emission of light.

Workflow Mode Lets you toggle the mode between Metallic and Specular.

- Metallic: Switch this on and the Metallic slider appears. That slider lends objects a reflective character, giving them a metal-like look by boosting how reflective a shape is.
- Specular: Switch this on and the Specular Color controls surface. Specular Color fixes the color of the light bouncing off a glossy surface; the more specular a material gets, the shinier it looks.

Roughness Shapes how much light a surface reflects and scatters, so depending on the value the result looks smoother or more textured; it's central to believable reflections. Clearcoat Alters a surface's look by stacking a glossy layer above it, imitating a protective coating, and it sees frequent use for materials such as car paint or polished metal. Clearcoat Roughness Tunes how flawed or how smooth that overlaid glossy layer is, which can sway the realism and reflectivity of materials like car paint or polished metal. Opacity Lowers the opacity of both material and object, affecting the shape's color and Alpha values.

### Shader Model: MaterialX

### The uShader controls in MaterialX mode

### Controls

An open standard kept up by the Academy Software Foundation, MaterialX exists for authoring material and look-development content in a platform-independent way. It evolves continually, and the most recent specifications live on the MaterialX website: materialx.org

### uTexture [uTx]

### The USD Texture

### Introduction

When you want to make a material/surface inside the uShader, this tool is what brings a texture file in. The uTexture pulls in image files and turns them into the material/surface over in the uShader.

### Inputs

Image Input: As you put a texture on a USD object — or light a scene by way of uDomeLight — the Image Input pulls frames from whatever Fusion node is already there. So in place of a pre-rendered image for the texture, you may rely on Fusion tools, video inputs and generated graphics included. With it connected, the Inspector tucks away the File Name control, and the Image Input takes precedence over any image file sourced earlier. Run a node into the Image Input of uShape or uReplaceMaterial and the picture comes through as a diffuse texture. The File Name path stops at a lone frame for a texture, but the Image Input unlocks animated textures, which grants more room to maneuver in lighting and texturing.

### Usage

### The uTexture controls

Once the node sits in the Node Editor, click the Browse button to pick an image file off your hard drive. As another route, drag an image straight from the Media Pool onto the “File Name” control in the Inspector to load one that's already been brought into DaVinci Resolve.

The “Source Color Space” control governs how the uTexture tool interprets the image. For the best outcome with a Normals image, be sure to choose Linear. Meanwhile, the U/V Address Mode controls give you a handy say over what happens to the image's edges when scaling leaves them exposed.

### uTextureTransform [uTXF]

### The USD Texture Transform

Introduction uTextureTransform hands you fine-grained command over the scale, rotation, and position of every texture file you've loaded. Using uTexture Transform, the size, orientation, and placement of any texture file coming from the uTexture node are quick and simple to adjust.

### Usage

### The uTexture Transform controls

With uTextureTransform, position it just past a uTexture node and just ahead of a uShader node. The node operates only in the span between the loaded texture and uShader. Set the Scale, Rotation, and Position settings however suits you. Scale grows or shrinks the texture file's size, whereas Position shifts the file about inside your project. Rotation, for its part, turns the texture file to whatever angle you have in mind.

### The Common Controls

A number of the same Inspector controls show up on every node that performs USD operations. What this section covers are those controls shared across the USD nodes.

### Transform Tab

Most USD nodes carry the Transform tab within the Inspector. Its controls mirror those of the uTransform node, which you can also use on its own. Translation Transform controls place the USD shape within 3D space. Rotation Order These buttons let you choose the sequence in which rotation is applied along each of the object's axes. XYZ, for instance, rotates the X-axis first, the Y-axis next, and the Z-axis last. Rotation These controls spin the shape about its pivot point. Tick the Use Target checkbox and the rotation references the target's position; leave it clear and the global axis governs instead. Pivot The pivot point is whatever an object turns around. Ordinarily an object turns about its own center, taken as a pivot of 0,0,0, but these controls can shift the pivot away from center. Scale With the Lock X/Y/Z checkbox ticked, you get one scale slider that resizes the object as a whole. Clear that Lock checkbox and separate X, Y, and Z sliders appear, opening up scaling along any dimension.

### Settings Tab

Every tool in the USD category carries the Settings tab in the Inspector, and its controls stay uniform, behaving identically from tool to tool. Hide Incoming Connections Tick this checkbox to conceal the connection lines coming in from upstream nodes, which tidies up a node tree and makes it easier to follow. Once it's on, the Inspector shows an empty field for each of a node's inputs. Drag a connected node out of the node tree into that field and the incoming connection line disappears, so long as the node stays unselected in the node tree; select it there and the line returns. Comments You jot notes onto a tool through the Comments field. Click the empty field and type your text. After a note goes on a tool, a little red square shows at the node's lower-left corner while the full tile is on view, or a small text bubble icon turns up on the right when nodes are collapsed. To read the note in the Node Editor, hover the mouse pointer over the node and the tooltip appears. Scripts From the Settings tab, three Scripting fields are present on every Fusion tool. Each holds an edit box where you enter scripts that run as the tool renders. For fuller detail on scripting nodes, turn to the Fusion scripting documentation.
