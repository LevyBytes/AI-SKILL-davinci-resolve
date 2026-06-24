# 3D Texture Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### 3D Texture Nodes

This chapter walks through the 3D Texture nodes on hand for building 3D composites in Fusion. The abbreviation beside each node name works in the Select Tool dialog while hunting for tools, and across scripting references.

For the sake of this document, node trees that show MediaIn nodes in DaVinci Resolve stand in interchangeably for Loader nodes in Fusion Studio, except where noted otherwise.

### Bump Map [3Bu]

### The Bump Map node

### Bump Map Node Overview

The Bump Map node turns a grayscale (height map) image into a bump map, taking its input straight from a bump map made by the Create Bump Map node. What the node puts out is a material.

### Inputs

The Bump Map node holds one orange input where you attach a 2D image meant as the bump map texture, or where it accepts the Create Bump Map node's output. ImageInput: Use the orange Image input to attach a 2D RGBA image driving the bump calculation, or a ready-made bump map from the Create Bump map node.

### Basic Node Setup

The Bump Map node wires into the Bump Map material input on any of the material shader nodes. In the example below, a Fast Noise node makes an image that connects to the Bump Map node. The Bump Map node's output then connects to the Bump Map material input on a Ward node.

A Bump Map wired into the Bump Map material input of a material node.

### Inspector

### Bump Map controls

### Controls Tab

Every parameter for modifying the input source and the look of the bump map sits on the Controls tab. Source Image Type Flip between Height Map, which produces a bump map much like the Create Bump Map node does, and Bump Map, which anticipates a bump map made by the Create Bump Map node. Filter Size The bump information comes from a custom filter, and you size that filter through the drop-down menu. Height Channel Picks the channel the grayscale information is pulled from. Clamp Z Normal Clips the lower values of the blue channel within the resulting bump texture. Height Scale Alters the contrast of the resulting values in the bump map. Push this value up and the bump map grows more visible. Texture Depth Optionally turns the resulting bump map texture into whatever bit depth you want. Wrap Mode Wraps the image at its borders, so the filter yields a correct result when seamless tile textures are in play.

### Common Controls

Settings Tab Other 3D nodes carry a copy of the Inspector’s Settings tab. You’ll find these common controls covered in full toward this chapter’s end within the “The Common Controls” section.

### Notes on Bump Maps

Bump mapping carries some muddled terminology, varying by where you read about it. The Fusion conventions go like this: Height Map

### Bump Map

A grayscale image containing a height value per pixel

### Normals Map

An image whose RGB channels hold normals that modify the existing normals (normally supplied in tangent space)

An image whose RGB channels hold normals that replace the existing normals (normally supplied in tangent or object space)

### Catcher [3Ca]

### The Catcher node

### Catcher Node Overview

The Catcher material exists to “catch” texture-mode projections thrown from Projector 3D and Camera 3D nodes. Those caught projections become a texture map that the Catcher material lays onto whatever geometry it connects to. Grasping the Catcher node is easier once you grasp the difference between light-based projections and texture-based projections. On the Projector 3D or Camera 3D nodes, choosing Light in the projection mode menu merely tacks the projected image's RGB channel values onto the diffuse texture of whatever geometry falls inside the projection cone. As a result, you can't clip geometry away through an image's Alpha channel while in light mode projections. Imagine wanting to throw an image of a building onto an image plane for a set extension shot. First you rotoscope the image to mask the windows out, which lets the geometry of the rooms behind the wall show through in the finished composite. Project that image as light, though, and the Alpha channel goes ignored, leaving the masked windows opaque. Hook the Catcher into the diffuse texture map of the image plane's material, then flip the projection mode menu on the Projector 3D or Camera 3D node away from Light or Ambient Light mode and over to Texture mode, and the projected image is applied as a texture map. Used this way for the example above, the windows would turn transparent, and you'd be able to see the geometry behind the window. This approach beats light projection mainly because the Catcher can project Alpha onto an object and asks for no lighting to be switched on. Another plus is that the Catcher isn't confined to a material's diffuse input, so projecting specular intensity maps, or even reflection and refraction maps, becomes possible. NOTE: For the Catcher material to work, the scene must hold a Projector 3D or Camera 3D node configured to throw an image in Texture mode onto whatever object the Catcher attaches to. With no projection present, or one not switched to Texture mode, the Catcher merely leaves the object transparent and invisible.

### Inputs

The Catcher node has no inputs. The node's output wires into the diffuse color material input of the Blinn, Cook Torrance, or another material node applied to the 3D geometry.

### Basic Node Setup

A Catcher node's output should wire into the material input of your 3D geometry node. A camera is arranged as a projector with an image fed into the camera's image input. With the camera set to texture projection mode, the Catcher node decides which geometry takes on the texture.

A Catcher node's output wired into the input of the geometry node taking on the texture projection Inspector

### Catcher controls

### Controls Tab

The Options on the Controls tab govern how the Catcher gathers up multiple projections. Enable Tick this checkbox to enable or disable the node. It differs from the red switch in the upper-left corner of the Inspector. That red switch shuts off the tool entirely and passes the image along untouched. The Enable checkbox is confined to the effect portion of the tool. Other portions, such as scripts in the Settings tab, keep processing as usual. Color Mode The Color mode menu governs how the Catcher blends the light from multiple projectors. It has no bearing on the outcome when just one projector is in the scene. The control is meant for the Renderer 3D node's software renderer and does nothing once the OpenGL renderer is in use.

Alpha Mode The Alpha mode governs how the Catcher blends the Alpha channels from multiple projectors. It has no bearing on the outcome when just one projector is in the scene. This setting targets the Renderer 3D node's software renderer and stays inert whenever the OpenGL renderer handles the job. Threshold The Threshold can leave certain low values out of the accumulation calculation. For instance, in the Median Accumulation mode, a threshold of 0.01 would drop any pixel valued below 0.01 from the median calculation. Restrict by Projector ID When on, the Catcher accepts light solely from projectors whose ID matches. Projectors carrying a different ID are passed over. Material ID This slider fixes the numeric identifier handed to this material. The value is rendered into the MatID auxiliary channel if the matching option is switched on in the Renderer 3D node.

### Common Controls

Settings Tab The Inspector’s Settings tab repeats across the other 3D nodes. A thorough rundown of these common controls waits at the chapter’s close in the “The Common Controls” section.

### CubeMap [3Cu]

### The Cube Map node

### Cube Map Node Overview

The Cube Map node builds texture maps from separate images, one for each face of the cube. It can equally pull the individual cube faces out of a single image holding an unfolded cube in the Vertical or Horizontal Cross layouts. You produce a cube map by mounting six cameras at 90 degrees angle of views, pointing up, down, left, right, front, and back. The node hands you options for setting the reference coordinate system and rotation of the resulting texture map. The Cube Map node typically serves to make environment maps for distant regions (skies or horizons, say) or reflection and refraction maps.

### Sample cube map

### Inputs

This node's Inputs change with how the Layout menu is set in the Inspector. One input covers a 2D image for the entire cube, while six inputs can each accept a separate 2D image per cube side. CrossImage: The orange Cross Image input is on view by default, or any time the Inspector's Layout menu shows Vertical Cross or Horizontal Cross. That input accepts a 2D image. CubeMap.[DIRECTION]: These six multi-colored inputs surface solely when the Inspector's Layout menu reads Separate Images. Every input accepts an image lined up with the left, right, top, bottom, front, and back faces.

### Basic Node Setup

The Cube Map node draws on a vertical or horizontal cross image, here represented by the MediaIn2 node wired into the orange cross image input. You use the Cube Map node much as you'd use the Sphere Map node. It builds an environment that wraps around the geometry connected to a Shader node.

A Cube Map node fed a cross image input, which builds an environment for the Shape 3D

### Inspector

### Cube Map controls

### Controls Tab

Layout The Layout menu sets the type and count of inputs for the cube map texture. The valid options are:

- Separate Images: Choosing this puts six inputs on the node, one per cube face. Should the separate images be non-square or of unequal size, they're rescaled into the biggest 1:1 image able to hold them all.
- Vertical Cross: Choosing this puts a single input on the node. The image ought to be a cube's unwrapped texture with every face laid out in a Vertical Cross arrangement, the height exceeding the width. Where the cross image's aspect isn't 3:4, the CubeMap node trims it down to fit the applicable aspect ratio.
- Horizontal Cross: Choosing this puts a single input on the node. The image ought to be a cube's unwrapped texture with every face laid out in a Horizontal Cross arrangement, the width exceeding the height. Where the cross image's aspect isn't 4:3, the CubeMap node trims it down to fit the applicable aspect ratio.

Coordinate System The coordinate system menu fixes the position values used as the image is turned into a texture.

- Model: Picks this to orient the texture along the object local coordinate system.
- World: Picks this to orient the resulting texture by the global or world coordinate system.
- Eye: Picks this to line the texture map up with the camera or viewer's coordinate system.

Rotation The rotation controls split into buttons selecting the order in which rotation runs along each axis of the texture. As an example, XYZ would apply rotation to the X axis first, next the Y axis, and finally the Z axis. The rotation controls' other half are dials that spin the texture around its pivot point. Warn About Bad Dimensions Ticking this checkbox throws a warning message onto the console when the dimensions of the supplied image fall short of the requirements for the chosen orientation mode. Material ID This slider fixes the numeric identifier handed to this material. The value is rendered into the MatID auxiliary channel if the matching option is switched on in the renderer.

### Common Controls

Settings Tab The same Settings tab in the Inspector shows up on the other 3D nodes. These common controls get their full explanation at the end of the chapter, under the “The Common Controls” section.

### Falloff [3Fa]

### The Falloff node

### Falloff Node Overview

The Falloff node blends two materials or textures according to the incidence angle between the camera and the object the material sits on. It comes in handy when you'd like one material for the portions of geometry that bounce light straight back at the camera and a different material for the portions that send light back into the scene.

### Falloff example

### Inputs

The Falloff node's two Inputs serve to connect two images or materials. One reflects back toward the camera, while the other reflects away from the camera into the scene. Face On Material: The orange Face On material input takes a 2D image or a 3D material. Supply a 2D image and it becomes a diffuse texture map by way of the basic material shader. This input handles the material reflecting straight back to the camera Glancing Material: The green Glancing material input takes a 2D image or a 3D material. Supply a 2D image and it becomes a diffuse texture map by way of the basic material shader. This input handles the material reflecting away from the camera into the scene. While this node's inputs can be images, its output is always a material.

### Basic Node Setup

The Falloff node below governs the strength of the Blinn material and the Reflect material. Connect the Falloff node's Face On input to whatever material should appear on the object's camera-facing sides, and connect the Glance input to whatever material should appear on the sides that don't face the camera head-on. So the Falloff node uses one input for the camera-facing material and another for the material turned away from the camera.

### Inspector

### Falloff controls

### Controls Tab

The parameters across the Controls tabs tune the tint and opacity belonging to the Face On material as well as the Glancing material. The blend between the pair is governed by a Falloff slider.

### Color Variation

- Two Tone: A pair of ordinary Color controls set the Glancing and Face On colors.
- Gradient: One Gradient control sets the Glancing and Face On colors. You can put this toward all kinds of effects—building Toon Shaders, for one.

Face On Color The Face On Color sets the color of the surface parts that face the camera. When a Face On texture map is supplied, the color value you give here is multiplied against the texture's color values. Dialing back the material's opacity lowers the color and Alpha values of the Face On material, turning the material transparent. Glancing Color The Glancing Color sets the color of the surface parts more perpendicular to the camera. When the Glancing material port has a valid input, that input is multiplied by this color. Dialing back the material's opacity lowers the color and Alpha values of the Glancing material, turning the material transparent. Falloff This value governs the transition between Glancing and Face On strength. It behaves much like a gamma operation laid on a gradient, blending one value into another. Material ID This slider fixes the numeric identifier handed to this material. The value is rendered into the MatID auxiliary channel if the matching option is switched on in the renderer.

### Common Controls

Settings Tab Across the other 3D nodes the Inspector’s Settings tab is mirrored. The complete account of these common controls sits near the chapter’s finish in the “The Common Controls” section.

### Fast Noise Texture [3FN]

### The Fast Noise Texture node

### Fast Noise Texture Node Overview

The Fast Noise Texture node is the procedural, resolution-independent counterpart to the 2D Fast Noise node. It generates a noise texture straight away as a material for use with 3D nodes. It also offers a 3D volumetric mode for building seamless textures together with nodes that supply UVW texture coordinates (much like the UV Map 3D node set to XYZ-to-UVW or Camera).

### Inputs

The Fast Noise Texture node carries an optional input for hooking up a 2D image or material. SourceMaterial: The Source Materials input takes a 2D image or a 3D material. That image is then reshaped by the noise pattern.

### Basic Node Setup

The Fast Noise Texture node below serves to generate a resolution-independent 3D texture for an FBX imported model.

A Fast Noise Texture node builds a seamless texture, putting UVW coordinates to use.

### Inspector

### Fast Noise Texture controls

### Controls Tab

The parameters of the Fast Noise Texture node govern the look and, in 2D, the animation of the noise.

### Output Mode

- 2D: Works out the noise texture from 2D texture coordinates (UV). Under this setting the noise pattern can be varied smoothly through animation.
- 3D: Works out the noise texture from 3D texture coordinates (UVW). A node such as Shape 3D supplies a third texture coordinate on its own; failing that, the UV Map node can build a 3D texture space. With the 3D setting, animating the noise pattern isn't supported.

Detail Raise this slider's value to coax a finer level of detail out of the noise result. Bigger values stack on more layers of increasingly detailed noise without touching the overall pattern. High values take longer to render yet can yield a more natural result (not every graphics card supports higher detail levels in hardware). Brightness This control tunes the overall Brightness of the noise map. Contrast This control raises or lowers the overall Contrast of the noise map. It can play up the noise's effect. Scale The Scale slider lets you size the noise map, shifting it from gentle variation across the whole image to a tighter overall texture effect. This value represents how the noise scales along the UV axis. Scale Z (3D only) Within texture space, the Scale Z value scales the noise texture along the W-axis. For a 3D texture map, W points perpendicular to the UV plane. Seethe (2D only) Through the Seethe control, the 2D noise pattern varies smoothly. Seethe Rate (2D only) Like the Seethe control above, the Seethe Rate likewise makes the noise map evolve and shift. The Seethe Rate fixes how fast the noise changes each frame, driving an automatic animated drift in the noise with no need for spline animation. Discontinuous Ordinarily, the noise function interpolates between values to form a smooth continuous gradient of results. Tick the Discontinuous checkbox to carve hard discontinuity lines along some of the noise contours. The upshot is a dramatically different effect. Invert Tick the Invert checkbox to invert the noise, producing a negative image of the original pattern. This works best with Discontinuous switched on too. Material ID This slider fixes the numeric identifier handed to this material. The value is rendered into the MatID auxiliary channel if the matching option is switched on in the renderer.

### Common Controls

Settings Tab The Settings tab found in the Inspector recurs throughout the other 3D nodes. Look for a detailed treatment of these common controls at the chapter’s tail end in the “The Common Controls” section.

### Gradient 3D [3Gd]

### The Gradient node

### Gradient Node Overview

The Gradient 3D node serves to texture objects with an assortment of gradient types. It carries many of the same controls as the Background node. Although the gradient can't be transformed directly within 3D space, it can be oriented with the nodes below: Texture Transform Node: The Texture Transform node can tune the mapping per pixel. UV Map Node: The UV Map node can tune the mapping per vertex (use the XYZtoUVW mode). It carries onscreen controls, so you can watch what the gradient is doing. Reaching for this node is the recommended route since it evaluates faster. Out of the box the gradient is linear, sweeping from -1 to +1 along the Z-axis. For UVW mapping, each primitive within the Shape 3D node is able to emit a third texture coordinate.

### Inputs

The Gradient node has no Inputs. The node's output wires into a material input on 3D geometry.

### Basic Node Setup

The Gradient 3D node below produces a resolution-independent 3D texture for an FBX imported model. Placing a UV Map tool after the geometry makes positioning within UVW space easiest.

A Gradient 3D node producing a resolution-independent gradient texture, placed by the UV Map tool

### Inspector

### Gradient 3D controls

### Controls Tab

The Controls tab for the Gradient node governs the pattern and colors that make up the gradient texture. Gradient Type Picks which type or pattern the gradient follows. Linear: A plain linear gradient. Reflect: Resting on the Linear mode, this gradient mirrors itself at the center of the textured range. Square: The gradient is applied with a square pattern. Cross: Much like the Reflect mode, though Cross draws on two axes to apply the gradient. Radial: The Radial mode applies the gradient with a circular pattern.

### Gradient 3D modes

Gradient Bar The Gradient control is a bar where you can add, modify, and remove the gradient's color stops. Every triangular color stop along the Gradient bar stands for one color in the gradient. Both the color and the point's position can be animated. On top of that, a From Image modifier can be laid on the gradient to evaluate it from an image.

Interpolation Space By default the gradient interpolates linearly from point to point in RGB color space. That can occasionally throw up unwanted colors. Choosing a different color space may give a better result. Scale Lets you size the gradient. Offset Lets you pan through the gradient. Repeat Sets how the gradient's left and right borders are handled. Once: As you shift the gradient with the Gradient Offset control, the border colors hold their values. Shifting the default gradient leftward yields a white border on the left, while shifting it rightward yields a black border on the right. Repeat: As you shift the gradient with the Gradient Offset control, the border colors wrap around. Shifting the default gradient leftward yields a sharp jump from white to black, while shifting it rightward yields a sharp jump from black to white. Ping Pong: As you shift the gradient with the Gradient Offset control, the border colors ping-pong back and forth. Shifting the default gradient leftward makes the edge fade from white back to black, while shifting it rightward makes the edge fade from black back to white.

From top to bottom, gradients in Once, Repeat, and Ping Pong respectively, with the gradient shifted leftward Sub Pixel Fixes the accuracy with which the gradient is built. Material ID This slider fixes the numeric identifier handed to this material. The value is rendered into the MatID auxiliary channel if the matching option is switched on in the renderer.

### Common Controls

Settings Tab Every other 3D node duplicates this Inspector Settings tab. A full description of these common controls appears where the chapter wraps up, in the “The Common Controls” section.

### Sphere Map [3SpM]

### The SphereMap node

### Sphere Map Node Overview

The Sphere Map node can build simulated environment mapping, also known as reflection mapping. Ray trace rendering a reflective scene can eat up a lot of time, but sphere map-based reflection mapping can produce 360-degree reflections faster with little loss of accuracy. As an example, when crafting a reflective environment, a sphere map is created, big enough to surround the 3D object in your scene. The sphere gets mapped with the environment you want reflected and connects to the Reflection Color input on a Reflect node.

### Inputs

The single image input on the Sphere Map node takes a 2D image texture in an equirectangular format (where the X-axis stands for 0–360 degrees longitude, and the Y-axis stands for –90 to +90 degrees latitude.) ImageInput: The orange Image input takes a 2D RGBA image. Ideally this is an equirectangular image showing the full vertical and horizontal angle of view up to 360 degrees.

### Basic Node Setup

The Sphere Map node below takes a spherical image as its map to produce the environment reflected across the Shape 3D. It wires into the Reflection Color input of a Reflect node.
