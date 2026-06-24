# Deep Pixel Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Deep Pixel Nodes

The Deep Pixel nodes within Fusion are what this chapter covers. What Deep Pixel nodes can do is process AOVs (Arbitrary Output Variables) coming from 3D-rendered files.

The abbreviation shown beside every node name serves both as a search term inside the Select Tool dialog when hunting for tools and within scripting references. Throughout this document, any node tree depicting MediaIn nodes in DaVinci Resolve stands in for Loader nodes in Fusion Studio, except where a note states otherwise.

### Ambient Occlusion [SSAO]

### The Ambient Occlusion node

### Ambient Occlusion Node Introduction

Ambient Occlusion (AO) refers to the illumination that arises when a uniform diffuse spherical light source wraps around a scene. Picture the scene enclosed by an enormous sphere whose surface gives off light evenly in every direction. What AO records is the low frequency lighting. Sharp shadows, along with Diffuse or Specular lighting, lie outside what it records. For that reason, AO is generally paired with Diffuse and Specular lighting to assemble a complete lighting solution. As a post effect, the Ambient Occlusion node produces global lighting results across 3D-rendered scenes. It offers a fast approximation of the computationally costly ray-traced global illumination. Since it runs as a post effect, it surfaces aliasing problems much like the Shader, Texture, and Volume Fog nodes do. Consequently, certain circumstances may bring out artifacts.

### Usage

Seldom does the AO node deliver correct results untouched; some adjustment is needed. Getting it set up means tuning the Kernel Radius along with the Number Of Samples until the look you want appears. How large the Kernel Radius should be hinges on the scene’s inherent “scale.” At the outset it can seem as though no AO shows up whatsoever. Most often the Kernel Radius sits too small or too large, and you have to hunt down values that work.

### Inputs

The AO node carries three inputs. To confine the AO effect, the standard effect mask comes into play. Both the Input and Camera connections are mandatory. Leave out either one and the node produces no image at its output. Input: This orange input takes a 2D RGBA image, Z-Depth, and Normals. Camera: That green camera input will accept either a 3D Scene or the 3D Camera that rendered the 2D image. Effect Mask: This optional blue effect mask input takes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input confines the Ambient Occlusion to just the pixels falling inside the mask. An effects mask gets applied to the tool once the tool has finished processing.

### Basic Node Setup

You normally drop the Ambient Occlusion node in after a Renderer 3D node. That Renderer 3D node has to have Z-Depth and Normals switched on among its output channels. The Camera3D the Renderer3D node renders then gets wired into the camera input on the AO node.

### Ambient occlusion as a 2D post process

### Inspector

### Ambient Occlusion controls

### Controls Tab

Every primary control for compositing with AO lives on the controls tab. It governs how good and how the effect looks.

### Output Mode

- Color: Picking the Color menu option merges the arriving image together with Ambient Occlusion laid on top.
- AO: This choice puts out the raw Ambient Occlusion as a grayscale image. Bright areas of the picture map to white, whereas the areas meant to be darker map to black. That lets you build a lighting equation by joining separate ambient/diffuse/ specular passes. Keeping the AO as its own buffer grants you the creative latitude to blend the passes in all sorts of ways.

Kernal Type AO is worked out by shooting rays off a point on the shaded surface, outward toward a big enclosing sphere. Whichever rays reach the sphere unobstructed set the AO factor.

- Hemisphere: Rays head toward a hemisphere aligned with the surface’s normal. Being more lifelike than Sphere, this choice ought to be used barring a solid reason not to. Flat surfaces take on 100% ambient intensity, while the remaining parts get darkened.
- Sphere: Rays head toward a sphere centered on the point under shading. This choice exists to deliver a stylistic look. Flat surfaces take on 50% ambient intensity, while the remaining parts grow darker or brighter.

Number of Samples Push the samples upward until artifacts across the AO pass vanish. Larger values can yield finer results yet also lengthen render time. Kernel Radius What the Kernel Radius governs is how large the filter kernel is within 3D space. Per pixel, it governs how far the search for occluders reaches into 3D space. You should dial in the Filter Kernel by hand for every separate scene. Set it too small and nearby occluders may go unseen. Set it too large and the AO quality drops, forcing you to crank the samples way up to win that quality back. This value rides on the scene Z-depth. So with enormous Z values throughout the scene, the kernel size has to be large to match. With minuscule Z values, a modest kernel size around 0.1 ought to do. Lift/Gamma/Tint The lift, gamma, and tint controls are there for you to tweak the AO toward artistic ends.

### Common Controls

Settings Tab A copy of the Settings tab in the Inspector also turns up across the other Deep Pixel nodes. Those shared controls get covered thoroughly at this chapter’s close within the “The Common Controls” section. TIP: Blending several AO passes that use differing kernel radii can yield finer effects.

### AO Tips and Limitations

Transparency/Translucency: Opaque objects are what AO is built to handle. Known shortcomings exist with transparent receivers as well as transparent occluders. Some of those shortcomings can be sidestepped by pulling the transparent/translucent objects out into separate scenes and computing AO solely on the opaque objects. Particles: Owing to the transparency/translucency shortcomings, steer clear of using AO on particles unless those particles are solid opaque geometry. Anti-aliased edges count as yet another kind of transparency, so they too trip up AO. Supersampling: For rendering anti-aliasing alongside Ambient Occlusion, switch on HiQ for the Z and Normals pass within the Renderer 3D. Viewer Dependence: AO methods operate in viewer space, leaving the outcome viewer dependent. What this means is the degree of darkening can shift with the viewing position when it really ought to hold constant. Where the AO at a point on an object reads 0.5, shifting the camera might turn it into 0.4. Baking of AO: The OpenGL UV renderer can serve to bake AO down into the textures on models.

### Depth Blur [DBl]

### The Depth Blur node

### Depth Blur Node Introduction

What the Depth Blur node chiefly serves is producing focal length or depth-of-field looks. Drawing on the bundled Z-channel values, it blurs 3D-rendered images, and through the Blur Channel controls it can equally drive general per-pixel blurring effects.

### Inputs

Three inputs come with the Depth Blur node: one carrying the main image, one carrying a blur image, plus another carrying an effect mask to bound the region where the depth blur lands. Input: This orange input is the lone connection that’s required. It takes a 2D image carrying a Z channel. That Z channel sets how much blur applies across the differing regions of the picture. Blur Image: Wire up the Blur Image input and the image’s channels then steer the blur. That opens up general 2D per-pixel blurring effects. Effect Mask: This optional blue effect mask input takes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input confines the depth blur to just the pixels falling inside the mask. An effects mask gets applied to the tool once the tool has finished processing.

### Basic Node Setup

The image holding the Z channel is what feeds the Depth Blur node. Down below, the Z depth channel arrives as a standalone image file and gets merged with the RGB (beauty) image by way of a Channels Booleans tool. Channel Booleans is set so the Z buffer channel copies into the luminance foreground.

Working from a Z depth channel, Depth Blur lands on the beauty image Inspector

### Depth Blur controls

### Controls Tab

Parameters for dialing in how much blur lands and how deep the blurred zone runs sit on the Controls tab. It additionally offers choices for picking channels apart from the Z channel as the blur map. Filter This menu picks which filter drives the blur.

- Box: This lays a plain depth-based box blur effect onto the image.
- Soften: This lays on a depth-based general softening filter effect.
- Super Soften: This lays on a depth-based high-quality softening filter effect.

Blur Channel Pick one of these choices to set which channel governs how much blur each pixel receives. The channel drawn from the main image input is what’s used, unless an image gets wired into the node’s green Blur Image input.

Lock X/Y Switched on, this control binds the X and Y Blur sliders together so blurring stays symmetrical. Blur Size This slider serves to set how strong the horizontal and vertical blurring is. Focal Point Only when the Blur channel menu is set to draw on the Z channel does this control show. Lean on this control to pick how far off the simulated point of focus sits. Drop the value and the Focal Point moves nearer the camera; raise it and the Focal Point moves farther off. Depth of Field This control serves to set how deep the in-focus zone runs. With the focal point sitting at the center of the region, every pixel whose Z-value falls inside the region holds focus. As an example, were the focal point picked off the image and set to 300, with the depth of field set to 200, any pixel carrying a Z-value between 200 and 400 would stay in focus. Z Scale Scales the Z-buffer value by whatever amount you pick. Raise the value and the distances within the Z-channel stretch out. Drop it and they pull in. This proves handy for overstating the depth effect. It can equally serve to soften the blur’s boundaries. Certain images carrying small depth values may call for the Z-scale to sit fairly low, under 1.0.

### Common Controls

Settings Tab A copy of the Settings tab in the Inspector also turns up across the other Deep Pixel nodes. Those shared controls get covered thoroughly at this chapter’s close within the “The Common Controls” section.

### Fog [Fog]

### The Fog node

### Fog Node Introduction

What the Fog node serves is building simulated fog looks across 3D-rendered images that hold a valid Z-buffer channel. Depending on which Z-channel planes you pick, the fog can sit ahead of or behind the assorted elements of a rendered image.

### Inputs

Three inputs come with the Fog node: one carrying the main image with a Z channel, one carrying a blur image, plus another carrying an effect mask to bound the region where the depth blur lands.

Input: This orange input is the lone connection that’s required. It takes a 2D image carrying a Z channel. That Z channel sets how much fog applies across the differing regions of the picture. Blur Image: The green second image input hooks up an image serving as the fog’s source. Supply no image and the fog ends up a single color. As a rule, some sort of noise map gets wired in here. Effect Mask: This optional blue effect mask input takes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input confines the fog to just the pixels falling inside the mask. An effects mask gets applied to the tool once the tool has finished processing.

### Basic Node Setup

You normally drop the Fog node in after a Renderer 3D node. That Renderer 3D node has to have Z-Depth switched on among its output channels.

A Fog node slotted in as a 2D post process following the Renderer 3D node Inspector

### Fog controls

### Controls Tab

Parameters for dialing in the fog’s density and color sit on the Controls tab. Z-Buffer Near Plane and Far Plane These controls serve to pick how far the fog reaches within the scene. To set a value, drag the Pick button onto a spot in the image you’re viewing where the plane should sit. The Near Plane serves to pick the depth at which the fog tapers off to nothing. The Far Plane serves to pick the depth at which the fog turns opaque. Z Depth Scale This choice scales the Z-buffer values by whatever amount you pick. Raise the value and the distances within the Z-channel stretch out, whereas dropping it pulls those distances in. This proves handy for overstating the fog effect. Fog Color This choice shows and governs the present fog color. Alpha tunes the fog’s transparency value. Fog Opacity Lean on this control to tune the opacity across every channel of the fog.

### Common Controls

Settings Tab A copy of the Settings tab in the Inspector also turns up across the other Deep Pixel nodes. Those shared controls get covered thoroughly at this chapter’s close within the “The Common Controls” section.

### Shader [Shd]

### The Shader node

### Shader Node Introduction

The Shader node can steer the lighting, reflection mapping, and 3D shading of elements within a rendered image. What the node depends on is the normal map channel being present in a rendered image. Should that channel be absent, this node does nothing.

### Inputs

Three inputs come with the Shader node: one carrying the main image with normal map channels, one carrying a reflection map, plus another carrying an effect mask to bound the region where the depth blur lands. Input: This orange input is the lone connection that’s required. It takes a 2D image carrying a normals channel.

Reflection Map Image: The green reflection map image input casts an image onto every element in the scene, or onto elements singled out by the Object and Material ID channels within the Common Controls. Reflection maps perform best as 32-bit floating point, equirectangular formatted images Effect Mask: This optional blue effect mask input takes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input confines the shader to just the pixels falling inside the mask. An effects mask gets applied to the tool once the tool has finished processing.

### Basic Node Setup

You slot the Shader node in after a 2D image holding a Normals channel. Down below, a Renderer 3D serves to attach a Normals channel onto an image. The Shader node draws on the normals to refine how the surface looks, with a reflection map wired in.

The Shader node drawing on normals out of a Renderer 3D together with a reflection input Inspector

### Shader controls

### Controls Tab

The Controls tab for the Shader node carries parameters for tuning how the overall surface responds to light sources. You can reshape the ambient, diffuse, specular, and reflection traits of the image wired into the orange image input. Light Tab Parameters covering basic lighting brightness plus reflections sit on the Controls tab. Ambient What Ambient governs is the Ambient color present throughout the scene or on the chosen object. This is a baseline level of light laid onto every pixel, even across fully shadowed areas.

Diffuse This choice governs the Diffuse color present throughout the scene or for the chosen object. This is the object’s normal color, thrown back equally in every direction. Specular This choice governs the Specular color present throughout the scene or for the chosen object. This is the color of the glossy highlights bounced toward the eye off a light source. Reflection This choice governs the Reflection contribution throughout the scene or for the chosen object. High settings leave objects looking mirrored, while low settings layer on faint reflections for a polished feel. With no reflection map wired in, it does nothing. Reflection Type This menu sets which kind of reflection mapping projects the image arriving at the second input. Screen: Screen makes the reflection map look as though it were cast onto a screen sitting behind the point of view. Spherical: Spherical makes the reflection map look as though it were cast onto an enormous sphere wrapping the entire scene. Refraction: Refraction makes the reflection map look as though it were refracting or warping in line with the scene’s geometry. Equator Angle What Equator Angle governs is the left-to-right angle of the light the Shader node produces and maps for the scene or the chosen object. Polar Height What Polar Height governs is the top-to-bottom angle of the light the Shader node produces and maps for the scene or the chosen object.

### Shader Tab

What the Shader tab serves is adjusting the falloff of the Diffuse and Specular light along with the tint color of the specular highlight. Diffuse and Specular Switched on, these checkboxes let you edit the Diffuse and/or Specular Shader curves inside the Shader spline window. In and Out These choices serve to show and edit point values along the spline. Specular Color Lean on the Diffuse curve to shape the diffuse shading and the Specular curve to drive the specular shading. Drag a box across several points to group-select them. A right-click brings up a menu carrying choices for tuning the spline curves.

### Common Controls

Settings Tab A copy of the Settings tab in the Inspector also turns up across the other Deep Pixel nodes. Those shared controls get covered thoroughly at this chapter’s close within the “The Common Controls” section.

### Texture [Txr]

### The Texture node

### Texture Node Introduction

What the Texture node governs is the texture mapping of elements within a rendered image. The Texture node depends on U and V Map channels being present in a 3D-rendered image wired into the main Image input. Should those channels be absent, this node does nothing. NOTE: Background pixels may carry U and V values of 0.0, which pins those pixels to the color of the texture’s corner pixel. To hold texturing to particular objects, lean on an effect mask drawn from the object’s Alpha or from its Object or Material ID channel.

### Inputs

Three inputs come with the Texture node: one carrying the main image with UV map channels, one carrying a texture map image, plus another carrying an effect mask to bound the region where the replace texture lands.

Input: This orange input takes a 2D image carrying UV channels. Should the UV channels be missing from the images, this node does nothing. Texture: The green texture map input supplies the texture that gets wrapped around objects, swapping out the current texture. Effect Mask: This optional blue effect mask input takes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input confines the texture to just the pixels falling inside the mask. An effects mask gets applied to the tool once the tool has finished processing.

### Basic Node Setup

You slot the Texture node in after a 2D image holding a Texture UV channel. Down below, a Renderer 3D serves to attach texture coordinates onto 3D text. The Texture node can then serve to reshape those coordinates by way of a fresh texture wired into the green texture input.

A Texture node put to work reshaping the texture coordinates and laying texture onto a Text 3D node Inspector

### Texture controls

### Texture Tab

The Texture tab controls let you flip, swap, scale, and offset the UV texture image wired into the texture input. Flip Horizontal and Vertical This pair of buttons lets you mirror the texture image across its horizontal axis and/or its vertical axis. Swap UV With this checkbox ticked, the source image’s U and V channels trade places.

Rotate 90 Tick this checkbox and the texture map image turns 90 degrees. U and V Scale These controls alter the scaling of the U and V coordinates that map the texture. Shifting these values effectively grows and shrinks the texture map as it lands. U and V Offset Nudge these controls to offset the U and V coordinates. Shifting the values makes the texture appear to slide along the object’s geometry.

### Common Controls

Settings Tab A copy of the Settings tab in the Inspector also turns up across the other Deep Pixel nodes. Those shared controls get covered in the “The Common Controls” section below.

### The Common Controls

The nodes that carry out Deep Pixel compositing operations share a number of identical controls within the Inspector. What this section describes is the controls held in common across the Deep Pixel nodes.

### Inspector

### Settings Tab

The Settings tab in the Inspector shows up on every tool inside the Deep Pixel category. Those Settings controls even appear on third-party Deep Pixel-type plugin tools. The controls stay consistent and behave alike for each tool, though some tools do carry one or two individual options likewise covered here. Blend What the Blend control serves is mixing between the tool’s original image input and the tool’s final reshaped output image. With the blend value at 0.0, the outgoing image matches the incoming image. Ordinarily that makes the tool bypass processing altogether, copying the input straight across to the output. Process When Blend Is 0.0 The tool still runs even where the input value is zero. That can come in handy where this node’s processing is scripted to kick off another task, yet the node’s value sits at 0.0. Red/Green/Blue/Alpha Channel Selector These four buttons serve to hold the tool’s effect to particular color channels. This filter often gets applied once the tool has run. As an example, deselect the red button on a Blur tool, and the blur lands on the image first, after which the red channel from the original input copies back over the result’s red channel. A few exceptions exist, such as tools where deselecting these channels makes the tool bypass processing that channel altogether. The tools that behave this way generally carry an identical set of RGBA buttons on the Controls tab within the tool. Here, the buttons across the Settings and the Controls tabs match. Apply Mask Inverted Switching on the Apply Mask Inverted option flips the tool’s entire mask channel. That mask channel is the merged outcome of every mask wired into or produced within a node. Multiply by Mask Pick this option and the masked image’s RGB values get multiplied against the mask channel’s values. That drives every pixel of the image lying outside the mask (that is, set to 0) to turn black/ transparent. Use Object/Use Material (Checkboxes) Certain 3D software can render to file formats that carry extra channels. Notably, the EXR file format carries Object and Material ID channels, usable as a mask for the effect. These checkboxes decide whether those channels get used when present. Which particular Material ID or Object ID is affected gets picked through the next set of controls. Correct Edges This checkbox surfaces only where the Use Object or Use Material checkboxes are ticked. It flips the method used to cope with overlapping object edges across a multi-object image. Switched on, the Coverage and Background Color channels serve to separate and sharpen the effect around the object’s edge. Leave this option off (or have no Coverage or Background Color channels on hand) and aliasing may show along the mask’s edge. For further detail, consult Chapter 78, “Understanding Image Channels,” within the DaVinci Resolve Reference Manual; the same material sits at Chapter 18 of the Fusion Reference Manual.

Object ID/Material ID (Sliders) Lean on these sliders to pick which ID builds a mask from an image’s object or material channels. Work the Sample button the same way as the Color Picker: to lift IDs off the image shown in the viewer. The image or sequence has to have been rendered out of a 3D software package carrying those channels. Use GPU The Use GPU menu carries three settings. Setting the menu to Disable shuts off hardware-accelerated rendering by way of your computer’s graphics card. Enabled puts the hardware to work. Auto draws on a capable GPU where one exists, yet drops back to software rendering when no capable GPU is on hand.

### Motion Blur
