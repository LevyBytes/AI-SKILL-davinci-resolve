# 3D Material Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Settings Tab Within the Inspector, the Settings tab recurs across the other 3D nodes. A full account of these shared controls waits at this chapter’s close, under “The Common Controls.”

### Material Merge 3D [3MM]

### The Material Merge node

### Material Merge Node Introduction

Two distinct materials can be fused together by the Material Merge node. It serves to composite Material nodes — pairing several illumination materials (Blinn, Cook Torrance) with texture nodes (Bump Map, Reflection) to assemble intricate shader networks. On top of that, the node offers a way to stamp a fresh material identifier onto the merged result.

### Inputs

For the pair of materials being joined, the Material Merge node supplies two inputs. Background Material: The orange Background material input takes a 2D image or a 3D material, which becomes the background material. Foreground Material: The green Foreground material input takes a 2D image or a 3D material, which becomes the foreground material. Under the basic shading model, any 2D image is read as a diffuse texture map.

### Basic Node Setup

A Material Merge node’s output feeds the material input of a 3D scene or 3D geometry node. In the example that follows, the Material Merge node draws a background base layer off the Blinn shader and blends it with a more heavily textured bump map layer.

A Material Merge node that fuses a Blinn-based shader (teal underlay) with a Ward-based shader (orange underlay)

### Inspector

### Material Merge controls

### Controls Tab

A lone slider on the Controls tab blends the two materials with one another.

### Blend

How the Material Merge blends echoes the Dissolve (DX) node used for images. Each input’s share of the mix between the two materials or textures is governed by the slider’s value. Even though a 2D image may stand in for a material at either the background or foreground input, what leaves this node is always a material. In a departure from the 2D Dissolve node, here both foreground and background inputs must be present. Material ID Through this slider you assign the numeric identifier carried by the resulting material. Whenever the matching renderer option is switched on, that figure is written into the MatID auxiliary channel.

### Common Controls

Settings Tab This Inspector Settings tab appears again throughout the rest of the 3D nodes. The shared controls it holds get a thorough write-up where the chapter ends, in “The Common Controls.”

### Phong [3Ph]

### The Phong node

### Phong Node Introduction

As a basic illumination material, the Phong node can be laid onto geometry sitting in the 3D scene. It defines the object’s reaction to light and exposes several texture map inputs so you can finely tune the material’s diffuse, specular, and bump map components. Although its highlight resembles the one the Blinn model yields, the Phong node tends to be chosen for glossy, polished plastic surfaces.

### Inputs

The Phong node carries five inputs, each taking a 2D image or a 3D material. They steer the overall color and imagery of the 3D object and likewise the color and texture feeding the specular highlight. Every one of them scales the texture map’s pixels by the like-named parameter on the node itself, an efficient way to dial portions of the material up or down. Diffuse Material: The orange Diffuse material input takes a 2D image or a 3D material that supplies the object’s main color and texture. Specular Color Material: The green Specular Color material input takes a 2D image or a 3D material that supplies the highlight color and texture for the object. Specular Intensity Material: The magenta Specular Intensity material input takes a 2D image or a 3D material acting as an intensity map for the material’s highlights. Should the input be a 2D image, its Alpha channel builds the map while the color channels are thrown out. Specular Exponent Material: The teal Specular Exponent material input takes a 2D image or a 3D material acting as a falloff map for the material’s specular highlights. Should the input be a 2D image, its Alpha channel builds the map while the color channels are thrown out. Bump Map Material: The white Bump Map texture input takes only a 3D material. The usual route is to wire the texture into a Bump Map node and then route that Bump Map node into this input. The RGB data here serves as texture-space normals. With a node carrying this many inputs, precise connections can be tricky. While dragging another node’s output across the node tile, press and keep holding the Option or Alt key, still holding it as you let go of the left mouse button. Up pops a small drop-down listing every input the node offers. Click the one you want to finish the connection.

### Basic Node Setup

A Phong node’s output wires into the material input of a 3D scene or 3D geometry node. In the example beneath, the Phong node pulls a base Color Diffuse input from the Fast Noise node plus a bump map texture that another Fast Noise node produces.

A Phong node with a diffuse color and Bump Map input

### Inspector

### Phong controls

### Controls Tab

On the Controls tab sit the parameters that tune the main color, highlight, and lighting behavior of the Phong shader node.

### Diffuse

Diffuse captures the underlying surface traits before extras such as reflections or specular highlights come into play. Beyond setting an object’s base color, the diffuse color additionally governs the object’s transparency. A diffuse texture map’s Alpha lets you render selected parts of the surface see-through. Diffuse Color The Diffuse Color of a material is the base hue it shows when lit by indirect or ambient light. With a diffuse texture map present, the color value entered here is multiplied against the texture’s color values. Alpha This slider fixes the material’s Alpha channel value. It acts on diffuse and specular colors alike and on the material’s Alpha value in the rendered output. With a diffuse texture map present, the Alpha value entered here is multiplied against the Alpha values in the texture map. Opacity Lowering a material’s Opacity pulls down the color and Alpha values of both specular and diffuse colors together, turning the material transparent.

### Specular

Settings in the Specular section dictate how the surface’s specular highlight looks, and each illumination model interprets these values its own way. Specular Color Specular Color picks the hue of light bouncing off a shiny surface. A more specular material reads as glossier. Plastics and glass usually show white specular highlights, while metals such as gold carry highlights tinted by the material color itself. With a specular texture map present, the value here is multiplied by the texture’s color values. Specular Intensity Specular Intensity sets how pronounced the specular highlight becomes. When the specular intensity texture is present, this value is multiplied by that texture’s Alpha value. Specular Exponent Specular Exponent governs the highlight’s falloff. A larger value sharpens that falloff and renders the material smoother and glossier. When the specular exponent texture is present, this value is multiplied by the texture map’s Alpha value.

### Transmittance

Transmittance dictates how light travels through a material. Take a solid blue sphere, which throws a black shadow; the same form in translucent blue plastic would throw a far thinner blue shadow instead. A distinct Opacity option exists too. Opacity decides how transparent the actual surface appears once rendered. Fusion lets opacity and transmittance be tuned independently. For anyone new to 3D software this can feel odd at first. You can indeed build a surface that stays fully opaque yet passes 100% of the light striking it, in effect a luminous or emissive surface. Attenuation Attenuation fixes how much color travels through the object. To give an object transmissive shadows, set the attenuation to (1, 1, 1), so that 100% of green, blue, and red light passes through it. Dialing this color to RGB (1, 0, 0) lets the material transmit 100% of incoming red while blocking all green and blue, handy for “stained glass”-styled shadows. Alpha Detail With the Alpha Detail slider at 0, the object’s Alpha channel is disregarded and the whole object throws a shadow. At 1, the Alpha channel decides which parts of the object cast a shadow. Color Detail The Color Detail slider tints light crossing the surface by the diffuse color plus texture colors. Reach for it to cast a shadow holding the color detail of the texture on the object. Raising the slider from 0 to 1 feeds progressively more diffuse and texture color into the shadow. Keep in mind that the object’s Alpha and opacity are bypassed while color is transmitted, so an object with a solid Alpha can still pass its color into the shadow.

Saturation The Saturation slider sets how saturated the color portion handed to the shadow is. Drop it to 0.0 and the shadows turn monochrome. Receives Lighting/Shadows These checkboxes decide whether scene lighting and shadows touch the material at all. Switch them off and the object stays fully lit and unshadowed throughout. Two-Sided Lighting This in practice renders the surface two sided by appending a second batch of normals that point the other way on its backside. It usually sits off to speed up rendering, yet you can enable it for 2D surfaces or for objects that aren’t fully sealed, making their reverse or inner faces visible too. By convention a 3D application shows only a surface’s front face and culls the back, so a camera orbiting a plane would see it vanish on reaching the rear. Turning a plane two sided in a 3D application amounts to stacking a duplicate plane on the first, spun 180 degrees so its normals point the other way at the back. Hence, orbiting to the rear reveals that second image plane, whose normals face opposite. When you make a surface two sided, Fusion behaves precisely as those 3D applications do. The muddle over two-sided lighting stems from Fusion not culling back-facing polygons out of the box. Orbit a one-sided plane in Fusion and the backside still shows (though what you see is the frontside carried through to the back as if transparent). Rendering the plane two sided in effect tacks a second set of normals onto its backside. NOTE: Once the surface goes transparent this gets genuinely confusing, because the same rules hold and the outcome runs against intuition. Viewing a transparent two-sided surface from the front while it’s lit from behind makes it look unlit. Material ID Use this slider to set the numeric identifier given to this material. When the matching option is active in the renderer, that value writes into the MatID auxiliary channel.

### Common Controls

Settings Tab The Inspector’s Settings tab is mirrored across the other 3D nodes. Its shared controls receive their detailed coverage at the chapter’s end inside “The Common Controls.”

### Reflect [3RR]

### The Reflect node

### Reflect Node Introduction

Environment map reflections and refractions are layered onto materials by the Reflect node. You get a say over face on and glancing strength, falloff, per channel refraction indexes, and tinting, with several texture map inputs available to reshape how each parameter behaves. Environment mapping is itself an approximation, treating an object’s surroundings as though they sit infinitely far away. Picture a cube or sphere wrapped around the object at its center. Because of that infinite-distance premise, objects can’t reflect themselves — the reflections on a teapot’s handle show the surrounding environment map rather than the teapot’s own body. By the same token, applying one cube map to several scene objects leaves them unable to mirror one another, so two adjacent objects won’t reflect each other. Getting objects to reflect one another calls for rendering a separate cube map per object. Fuller coverage sits in Chapter 85, “3D Compositing Basics,” of the DaVinci Resolve Reference Manual, as well as Chapter 25 of the Fusion Reference Manual.

### Inputs

Five inputs sit on the Reflect node, each one taking a 2D image or a 3D material. They drive the overall color and imagery of the 3D object together with the color and texture feeding the reflective highlights. Background Material: The orange Background material input takes a 2D image or a 3D material; a 2D image gets read as a diffuse texture map over a basic material. Reflection Color Material: The white Reflection Color material input takes a 2D image or a 3D material, whose RGB channels serve as the reflection texture while the Alpha goes unused. Reflection Intensity Material: The white Reflection Intensity material input takes a 2D image or a 3D material, and that texture’s Alpha channel scales the reflection’s intensity. Refraction Tint Material: The white Refraction Tint material input takes a 2D image or a 3D material; its RGB channels supply the refraction texture. Bump Map Texture: The white Bump Map texture input takes only a 3D material. As a rule, you wire the texture into a Bump Map node and then route that Bump Map node here. The RGB data at this input acts as texture-space normals. Once a node sports this many inputs — several sharing a color — landing connections precisely gets awkward. As you drag another node’s output across the node tile, hold the Option or Alt key down and keep it held while releasing the left mouse button. A compact drop-down then lists every input the node provides. Click the one you need to seal the connection.

### Basic Node Setup

As shown in the example beneath, the Reflection node can act as an object’s primary shader, or it can supply the diffuse material input of a Ward, Blinn, Phong, or some other material node. The Reflect node’s reflection color input is typically fed from a Sphere Map node.

A Reflect node producing a strongly mirror-like surface on a Shape 3D node Inspector

### Reflect controls

### Controls Tab

Parameters on the Controls tab let you tune reflective strength according to the object’s orientation, plus the tint color of the Reflect shader node.

### Reflection

Reflection Strength Variability This multi-button control toggles between Constant and By Angle, varying reflection intensity in line with how the surface is oriented relative to the viewer. The three controls below it surface only while this is set to By Angle. Glancing Strength [By Angle] Glancing Strength sets reflection intensity across the geometry where the reflection turns away from the camera. Face On Strength [By Angle] Face On Strength sets reflection intensity over the geometry that reflects straight back at the camera. Falloff [By Angle] Falloff governs how sharp the handoff is between the Glancing and Face On Strength zones — akin to gamma-correcting a gradient stretched between the Face On and Glancing values. Constant Strength [Constant Angle] This one appears only while reflection strength variability is set to Constant, where reflection intensity holds steady no matter the reflection’s incidence angle.

### Refraction

Whenever the incoming background material drops below an opacity of 1, an environment map can serve as the refraction texture, letting you fake refraction inside transparent objects. Separate RGB Refraction Indices Ticking this checkbox tucks away the Refraction Index slider and swaps in three sliders that tune the refraction index for the Red, Green, and Blue channels individually. That opens the door to mimicking the spectral refraction often visible in thick, flawed glass. Refraction Index This slider dictates how heavily the environment map warps when seen through a surface, with the overall warp keyed to the incidence angle. Being an approximation rather than a true simulation, its output isn’t built to model real refractions exactly. Refraction Tint Multiplying the refraction texture by the tint color simulates color-filtered refractions — useful for the kind of coloring found in tinted glass, like that of many beer bottles.

### Common Controls

Settings Tab Inside the Inspector this Settings tab turns up on the other 3D nodes as well. Full detail on its shared controls lives at the chapter’s close under “The Common Controls.”

### Stereo Mix [3SMM]

### The Stereo Mix node

### Stereo Mix Node Overview

Swapping the left and right material inputs is this node’s job. It frequently feeds the left and right eye of the 3D Render.

### Inputs

Two inputs sit on this node, and both must be wired for it to function; either a 3D material or a 2D image is accepted at each. LeftMaterial: The orange left material input takes a 2D image or a 3D material that becomes the material for left eye rendering. A 2D image gets turned into a diffuse texture map via the basic material type. RightMaterial: The green right material input takes a 2D image or a 3D material that becomes the material for right eye rendering. Here too a 2D image is converted into a diffuse texture map via the basic material type. Although either input may be a 2D image or a 3D material, the output is invariably a material.

### Basic Node Setup

Either stereo images or stereo materials work with the Stereo Mix node. In the example beneath, two images merge inside the Stereo Mix node so that its output becomes a stereo anaglyph material.

A Stereo Mix node merging left and right images down to one stereo material Inspector

### Stereo Mix controls

### Controls Tab

A lone switch on the Controls tab exchanges the left and right material inputs. Swap This option flips both of the node’s inputs. Material ID This slider assigns the numeric identifier given to this material. Should the corresponding renderer option be on, the value lands in the MatID auxiliary channel.

### Common Controls

Settings Tab The Settings tab carried in the Inspector shows up again on the rest of the 3D nodes. Its common controls are spelled out fully where this chapter finishes, in “The Common Controls.”

### Ward [3Wd]

### The Ward node

### Ward Node Introduction

A basic illumination material, the Ward node can be draped over geometry within the 3D scene. It sets out the object’s response to light and exposes several texture map inputs for fine command of the material’s diffuse, specular, and bump map components. In particular, the Ward node excels at faking brushed metal surfaces, since its highlight can be stretched along the U or V axes of the mapping coordinates — what’s termed an anisotropic highlight. The Ward node emits a 3D Material that wires into the material inputs of any 3D geometry node.

### Inputs

Six inputs live on the Ward node, every one taking a 2D image or a 3D material. They command the overall color and imagery of the 3D object plus the color and texture driving the specular highlight. Each scales the texture map’s pixels by the matching parameter on the node itself, a tidy way to scale portions of the material. Diffuse Material: The orange Diffuse material input takes a 2D image or a 3D material supplying the object’s main color and texture. Specular Color Material: The green Specular Color material input takes a 2D image or a 3D material supplying the object’s highlight color and texture.

Specular Intensity Material: The magenta Specular Intensity material input takes a 2D image or a 3D material that works as an intensity map for the material’s highlights. Where that input is a 2D image, its Alpha channel forms the map while the color channels get dropped. Spread U Material: The white Spread U material input takes a 2D image or a 3D material. Within the Alpha channel of that material, the per-pixel values get multiplied by the Spread U option’s setting from the node’s controls. Spread V Material: The white Spread V material input takes a 2D image or a 3D material. Likewise, inside that material’s Alpha channel the per-pixel values are multiplied by the Spread V control’s setting. Bump Map Material: The white Bump Map material input takes only a 3D material. The usual approach is to wire the texture into a Bump Map node and then feed that Bump Map node into this input. The RGB data here functions as texture-space normals. When a node holds this many inputs — some sharing a color — making accurate connections is often fiddly. While you drag another node’s output over the node tile, keep the Option or Alt key pressed, holding it still as you release the left mouse button. A little drop-down then enumerates all the node’s inputs. Click whichever one you want to complete the connection.

### Basic Node Setup

In the example beneath, the Ward node builds a glossy glass surface and stands in for the 3D text material. Its diffuse color material arrives from a Reflect node, while a gradient-colored Fast Noise node reshapes the specular color.

A Ward node used with a diffuse connection and specular color connection

### Inspector

### Ward controls

### Controls Tab

The Controls tab gathers parameters that adjust the main color, highlight, and lighting traits of the Ward shader node. Diffuse Diffuse covers the underlying surface traits before any add-ons such as reflections or specular highlights enter the picture. On top of defining an object’s base color, the diffuse color also fixes how transparent the object is. The Alpha within a diffuse texture map can make chosen parts of the surface see-through. Diffuse Color The Diffuse Color of a material is the base hue it presents under indirect or ambient light. When a diffuse texture map is supplied, the color value here is multiplied by the texture’s color values. Alpha This slider establishes the material’s Alpha channel value. It bears equally on diffuse and specular colors and on the rendered material’s Alpha value. When a diffuse texture map is supplied, the Alpha value here is multiplied by the texture map’s Alpha values. Opacity Cutting a material’s Opacity lowers the color and Alpha values of specular and diffuse colors in equal measure, rendering the material transparent.

### Specular
