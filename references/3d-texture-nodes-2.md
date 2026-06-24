# 3D Texture Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Wiring a Sphere Map node into a Reflect node Reflection Color input produces a reflective environment.

### Inspector

### Sphere Map controls

### Controls Tab

The Controls tab in the Inspector governs how the image input is mapped onto the sphere map. Angular Mapping Tweaks the texture coordinate mapping so the poles look less squashed and regions of the texture cover equal-area patches on the sphere. It converts the latitude-line mapping from a hemispherical fisheye into an angular fisheye. Because this mapping tries to keep area constant, it becomes simpler to paint over or alter a sphere map, since the image isn't as crowded at the poles. Rotation Provides controls for spinning the texture map. Material ID This slider assigns the numeric identifier given to this material. The value gets rendered into the MatID auxiliary channel whenever the matching option is switched on in the renderer. The node looks for an image whose aspect ratio is 2:1. If that isn't the case, the image gets clamped per these rules:

- 2 \* width > height: The width gets sized to the sphere, leaving clamped edges showing at the poles.
- 2 \* width < height: The height gets sized to the sphere, with clamping occurring around the 0-degree

longitude line.

### Common Controls

Settings tab The Inspector's Settings tab repeats across the other 3D nodes. Full descriptions of these shared controls appear later in this chapter under the "The Common Controls" section.

Sphere Map vs. Connecting the Texture to a Sphere Directly Rather than routing it through the Sphere Map node first, you can hook an equirectangular texture map straight to a sphere. Doing so renders differently once you drop the start/end angle and latitude below 360°/180°. In the former scenario the texture ends up squashed. With the Sphere Map node in place, the texture is cropped instead. Compare:

### Spherical mapping differences

NOTE: Feeding the texture straight into the sphere also flips it horizontally. To undo that, run it through a Transform node first.

### Texture 2D [3Tx]

### The Texture 2D node

### Texture Node Overview

The Texture 2D node writes metadata for an image that's serving as a texture map. By default an image spans (0,0) to (1,1) UV, although you can change that. The Texture node depends on U and V Map channels being present within 3D rendered images. Without those channels, this node does nothing. NOTE: Background pixels can carry U and V values of 0.0, which paint those pixels with the color of the texture's corner pixel. To confine texturing to particular objects, apply an effect mask keyed to the object's Alpha, or to its Object or Material ID channel.

Further detail lives in the DaVinci Resolve Reference Manual under Chapter 78, "Understanding Image Channels," or over in the Fusion Reference Manual at Chapter 18.

### Inputs

Image Input: The orange image input expects a 2D image.

### Basic Node Setup

In the example below, the Texture 2D node receives a 2D gradient out of the Background node and writes the UV metadata onto it. That metadata then drives how the texture lands on the FBX geometry. When the UV Map tool is available to you, it's the recommended choice, since it can be quicker and offers onscreen controls.

Here a Texture 2D node assigns the 3D texture metadata onto the incoming image.

### Inspector

### Texture 2D controls

### Controls Tab

The Inspector's Controls tab carries these options. U/V Offset Use these sliders to shift the texture along the U and V coordinates. U/V Scale Use these sliders to resize the texture along the U and V coordinates.

Wrap Mode When a texture gets transformed within the texture space (via the controls below or the UV Map node), regions beyond the image borders might end up mapped onto the object. The Wrap Mode dictates how the image fills those regions.

- Wrap: This folds the picture's edges around onto the image's borders.
- Clamp: Texturing draws on the color found at the edges of the images. The behavior here resembles the

Duplicate mode in the Transform node.

- Black: Along its borders the image gets clipped, with a black color at Alpha = 0 substituted there.
- Mirror: The image is mirrored in both X and Y.

Texture Filtering Mode How the texture gets filtered varies depending on whether the Renderer 3D node is set to the Software Renderer or the OpenGL renderer. Inside either render engine you can pick high-quality anti-aliasing or low quality. The texture filtering mode supplies distinct filtering choices across the two render engines and the two anti-aliasing settings.

- Nearest: As the most basic filtering approach, it runs very fast but may introduce artifacts as textures are scaled.
- Bilinear: A conventional isotropic filtering approach for resampling textures across several resolutions.

Works well for magnification of textures.

- Trilinear: A step up from Bilinear filtering. Trilinear is usually the stronger pick when

scaling down textures

- Anisotropic: The top-quality filtering approach, which factors in the camera orientation along with polygon

perspective into account.

- SAT: SAT (Summed Area Table) delivers high-quality filtering, though it may demand

more memory than other options. Works very well on smaller bitmaps.

### Common Controls

Settings Tab The Inspector's Settings tab repeats across the other 3D nodes. Full descriptions of these shared controls appear later in this chapter under the "The Common Controls" section.

### Texture Transform [3TT]

### The Texture Transform node

### Texture Transform Node Overview

You can rely on the Texture Transform node to translate, rotate, and scale a 3D object's UVW texture coordinates. Although its input may also be an image, what it outputs is always a material.

### Inputs

The Texture Transform node carries a lone input where you attach the image or material you intend to transform. Material Input: The orange Material input takes a 2D image or 3D material whose texture coordinates get transformed by the controls in the Inspector.

### Basic Node Setup

In the example below, the Texture Transform node accepts a 2D image, transforms it, and emits a material destined for use on 3D geometry.

A Texture Transform node transforms a texture applied to 3D geometry.

### Inspector

### Texture Transform controls

NOTE: Not all Wrap modes are supported by all graphics cards.

### Controls Tab

The Controls tab for the Texture Transform node carries plenty of standard transform controls for transforming the texture through UVW coordinates. Translation The U, V, W translation sliders move the texture along the U, V, and W axes. Rotation Rotation Order buttons fix the sequence in which the rotation gets applied. Together with those buttons, the UVW dials set the rotation around the UVW axes. Scale U, V, W sliders resize the texture along the UVW axes. Pivot U, V, W Pivot establishes the anchor point used for rotation and scaling. Material ID This slider assigns the numeric identifier given to this material. The value gets rendered into the MatID auxiliary channel whenever the matching option is switched on in the renderer.

### Common Controls

Settings Tab The Inspector's Settings tab repeats across the other 3D nodes. Full descriptions of these shared controls appear in the "The Common Controls" section that follows.

### The Common Controls

Nodes that work with 3D geometry share a set of identical controls within the Inspector. This section covers the controls common to the 3D Texture nodes.

### Settings Tab

### Common Settings 3D controls

Most tools in Fusion include the Common Settings tab. The controls below are the settings unique to 3D nodes. Hide Incoming Connections Turning on this checkbox can conceal the connection lines coming from upstream nodes, leaving a node tree that looks tidier and reads more easily. With it on, a field appears for each input on a node. Drag a connected node from the node tree onto the field and that incoming connection line is hidden for as long as the node stays unselected in the node tree. Select the node within the node tree and the line shows up again. Comment Tab The Comment tab holds a single text control where you jot comments and notes onto the tool. Once a note is attached to a tool, a small red dot icon appears alongside the setting's tab icon, while the node itself gains a text bubble. To read the note inside the Node Editor, rest the mouse pointer over the node briefly. The contents of the Comments tab may be animated over time when needed. Scripting Tab Every tool in Fusion carries the Scripting tab. It holds several edit boxes for adding scripts that run while the tool renders. For fuller details on what this tab contains, refer to the scripting documentation.
