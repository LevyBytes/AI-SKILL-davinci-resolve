# 3D Material Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### 3D Material Nodes

This section covers the 3D Material nodes you have on hand for building 3D composites in Fusion. The abbreviation beside each node name works in the Select Tool dialog while hunting for tools, as well as in scripting references.

Throughout this document, treat node graphs that display MediaIn nodes in DaVinci Resolve as equivalent to Loader nodes in Fusion Studio, except where a difference is called out.

### Blinn [3Bl]

### The Blinn node

### Blinn Node Introduction

As a fundamental illumination material, the Blinn node can be laid onto geometry within the 3D scene. It spells out how an object reacts to light and supplies several texture map inputs so you can finely steer the material's diffuse, specular, and bump map parts. That standard basic material sitting in the Materials tab of most geometry nodes is really a pared-down take on the Blinn node, the chief distinction being that the Blinn node hands you extra texture map inputs on top of diffuse alone. What the Blinn node puts out is a 3D Material you can wire into the material inputs of any 3D geometry node. Within Fusion, the Blinn model figures the highlight from the dot product of the surface normal against the half angle vector between the light source and viewer (dot(N, H)), which won't always line up with the Blinn illumination model that other 3D applications employ.

### Inputs

The Blinn node carries five inputs that take 2D images or 3D materials. Through them you govern the overall color and image applied to the 3D object, plus the color and texture driving the specular highlight. Every one of these inputs scales the texture map's pixels by the like-named parameters living in the node, giving you a tidy way to scale portions of the material. Diffuse Texture: The orange Diffuse Texture input takes a 2D image or a 3D material to serve as the object's main texture map. Specular Color Material: The green Specular Color material input takes a 2D image or a 3D material to serve as the color texture map across specula highlight regions. Specular Intensity Materials: The magenta Specular Intensity material input takes a 2D image or a 3D material for adjusting how intense the specular highlights are. Should that input be a 2D image, the map is built from the Alpha channel while the color channels are thrown away. Specular Exponent Material: The teal Specular Exponent material input takes a 2D image or a 3D material acting as a falloff map for the material's specular highlights. Should that input be a 2D image, the map is built from the Alpha channel while the color channels are thrown away. Bump Map Material: The white Bump Map material input takes a 3D material only. The usual route is to wire the texture into a Bump Map node, then run that Bump Map node into this input. Here the RGB information is read as texture-space normals.

Once a node sports this many inputs, wiring them up precisely gets tricky. Press and hold the Option (macOS) or Alt (Windows) key as you drag another node's output across the node tile, and keep Option or Alt down as you let go of the left mouse button. Up pops a compact drop-down menu naming every input the node exposes; click the one you want to seal the connection. As another route, dragging a node's output with the right mouse button calls up that same menu.

### Basic Node Setup

You route a Blinn node's output into the material input of whichever 3D scene or 3D geometry node you mean to shade. The Blinn inputs accept images for the diffuse color material (orange) and the specular color material (green), which can yield a smooth, glossy material.

A Blinn shader with diffuse and specular color materials connected Inspector

### Blinn controls

### Controls Tab

For the Blinn node, the Controls tab is the main one. It steers the color and shininess laid across the 3D geometry's surface.

### Diffuse

Diffuse captures the underlying surface traits before any extras such as reflections or specular highlights enter the picture. On top of fixing an object's base color, the diffuse color also sets the object's transparency, and the Alpha within a diffuse texture map lets you render parts of the surface see-through. Diffuse Color A material's Diffuse Color is the base color it shows when lit indirectly or by ambient light. Supply a diffuse texture map and the color value entered here gets multiplied against the texture's color values. Alpha This slider fixes the material's Alpha channel value, acting on diffuse and specular colors alike and on the material's Alpha value in the rendered output. Supply a diffuse texture map and the Alpha value set here gets multiplied against the texture map's Alpha values. Opacity Lowering the material's opacity drops the color and Alpha values of both the specular and diffuse colors together, turning the material transparent.

### Specular

Within the Specular section, the parameters spell out the look of the surface's specular highlight, and these values get evaluated differently under each illumination model. Specular Color Specular Color sets the color of light bouncing off a glossy surface. A more specular material reads as glossier. Materials such as plastics and glass usually throw white specular highlights, while metallic surfaces like gold show specular highlights that take their color from the material color itself. Supply a specular texture map and the value entered here gets multiplied against the texture's color values. Specular Intensity Specular Intensity governs how forceful the specular highlight is. Supply the specular intensity texture and this value gets multiplied against the texture's Alpha value. Specular Exponent Specular Exponent governs the specular highlight's falloff. A larger value makes the falloff sharper and the material smoother and glossier. Supply the specular exponent texture and this value gets multiplied against the texture map's Alpha value.

### Transmittance

Transmittance governs how light travels through a material. Take a solid blue sphere, which throws a black shadow, versus one of translucent blue plastic, which would throw a far lighter blue shadow. A distinct Opacity option exists too. Opacity decides how see-through the actual surface renders. Fusion lets you tune opacity and transmittance on their own, which can feel odd at first to anyone new to 3D software. You can indeed have a surface that is wholly opaque yet still passes 100% of the light reaching it, in effect turning it into a luminous/ emissive surface. Attenuation Attenuation sets how much color makes it through the object. To give an object transmissive shadows, dial the attenuation to (1, 1, 1), meaning all of the green, blue, and red light travels through. Set this color to RGB (1, 0, 0) and the material lets through 100% of the red striking the surface but none of the green or blue. This serves well for “stained glass”styled shadows. Alpha Detail With the Alpha Detail slider at 0, the object's Alpha channel is disregarded and the whole object throws a shadow. Push it to 1 and the Alpha channel dictates which parts of the object throw a shadow. Color Detail The Color Detail slider tints the light crossing the surface by the diffuse color + texture colors. Reach for it to cast a shadow carrying the color details of the texture on the object. Raising the slider from 0 to 1 folds more diffuse color + texture color into the shadow. Keep in mind that the object's Alpha and opacity are skipped while transmitting color, so even an object with solid Alpha can still send its color into the shadow. Saturation The Saturation slider rules the saturation of the color component handed to the shadow. Drop it to 0.0 and you get monochrome shadows. Receives Lighting/Shadows These checkboxes decide whether scene lighting and shadows touch the material. Switch them off and the object stays fully lit and/or unshadowed. Two-Sided Lighting This in effect renders the surface two sided by appending a second set of normals pointing the other way on the surface's backside. It usually sits off to speed up rendering, but you can enable it for 2D surfaces or for objects that aren't fully sealed, so the reverse or interior surfaces show as well. Ordinarily, a 3D application shows only a surface's front face and culls the back, so a camera orbiting a plane in such an application would find the plane vanish once it swung behind. Making a plane two sided in a 3D application amounts to stacking a second plane onto the first, spun 180 degrees so its backside normals face the other direction. So when you orbit around the back, what greets you is that second image plane, its normals pointing the opposite way.

When you make a surface two sided, Fusion behaves precisely as those 3D applications do. The muddle over what two-sided lighting accomplishes stems from Fusion not culling back-facing polygons out of the box. Orbit a one-sided plane in Fusion and you still catch it from the backside (though what you see is the frontside carried straight through to the back as if transparent). Turning the plane two sided in effect tacks a second set of normals onto the plane's backside. NOTE: Things can get genuinely confusing the moment you make the surface transparent, since the same rules hold and the outcome runs counter to intuition. View a transparent two-sided surface from the front while it is lit from behind, and it reads as unlit. Material ID This slider assigns the numeric identifier given to this material. That value is written into the MatID auxiliary channel whenever the matching option is switched on in the renderer.

### Common Controls

Settings Tab Other 3D nodes carry the same Settings tab found in the Inspector. A full account of these shared controls comes later, within this chapter's “The Common Controls” section.

### Channel Boolean [3Bol]

### The Channel Boolean node

### Channel Boolean Node Introduction

The Channel Boolean (don't mix it up with the 2D Channel Booleans) lets you remap and reshape the channels of 3D materials through mathematical operations. Say you want a material's red channel to drive a scalar input on an illumination model that reads the Alpha channel (e.g., Blinn. SpecularExponent) — you can remap the channels right here. On top of that, it opens the door to geometry-specific data such as texture space coordinates and normals.

### Inputs

The Channel Boolean Node has two inputs: one carrying the foreground material and one carrying the background material. Each input takes either a 2D image or a 3D material such as the Blinn, Cook-Torrence, or Phong node. BackgroundMaterial: The orange background material input takes a 2D image or a 3D material. ForegroundMaterial: The green foreground input likewise takes a 2D image or a 3D material.

### Basic Node Setup

The material 3D Channel Boolean finds plenty of uses. More often than not it serves to merge material looks or work over UV texture coordinates In the example below, the Channel Boolean node fuses the Cook Torrance and Blinn materials. Drawing on the math operands inside the Channel Boolean, it switches, inverts, and blends the two inputs to conjure a neon flickering effect.

A Channel Boolean merging and acting upon a pair of Cook Torrance and Blinn nodes Inspector

### Channel Boolean controls

### Controls Tab

The Controls tab carries a section per RGBA channel. Each channel holds two input menus named Operand A and Operand B, and the Operation menu picks which function runs on the pair. Operand A/B One Operand menu exists for every output RGBA channel, letting you choose the input information you want feeding that channel.

Red/Green/Blue/Alpha FG Red/Green/Blue/Alpha BG Black/White/Mid Gray Hue/Lightness/Saturation FG Hue/Lightness/Saturation BG Luminance FG Luminance BG X/Y/Z Position FG U/V/W Texture FG U/V/W EnvCoords FG X/Y/Z Normal

Pulls the foreground material's color information. Pulls the background material's color information. Pins the channel's value to 0, 0.5, or 1. Pulls the foreground material's color information, recasts it into the HLS color space, and drops the chosen information into the matching channel. Pulls the background material's color information, recasts it into the HLS color space, and drops the chosen information into the matching channel. Pulls the foreground material's color information and works out the channel's luminance value. Pulls the background material's color information and works out the channel's luminance value. Pins the channel's value to where the pixel sits in 3D space, with the vector information handed back in eye space. Maps the foreground material's texture space coordinates onto the channels. Maps the environment texture space coordinates onto the channels. Place it ahead of nodes that alter the environment texture coordinates, such as the Reflect 3D node. Pins the channel's value to the chosen axis of the normal vector, the vector being handed back in eye space.

Operation Sets the Operation by which the operands are merged.

`A` `B` `1-A` `1-B` `A+B` `A-B` `A*B` `A/B` `min(A,B)` `max(A,B)` `avg(A,B)`

Draws on Operand A alone for the output channel. Draws on Operand B alone for the output channel. Takes the value of Operand A away from 1. Takes the value of Operand B away from 1. Sums the values of Operand A and B. Takes the value of Operand B away from A. Multiplies the values of both Operands together. Divides A by the value of Operand B. Weighs the values of Operands A and B against each other and yields the smaller. Weighs the values of Operands A and B against each other and yields the larger. Yields the mean value of both Operands.

Material ID This slider hands this material its numeric identifier. The renderer writes that value into the MatID auxiliary channel when the matching option is turned on.

### Common Controls

Settings Tab The Inspector's Settings tab shows up again across other 3D nodes. These shared controls receive a thorough write-up at the chapter's end, under “The Common Controls.”

### Cook Torrance [3CT]

### The Cook Torrance node

### Cook Torrance Node Introduction

As a fundamental illumination material, the Cook Torrance node can be laid onto geometry within the 3D scene. Its diffuse calculation runs close to what the basic material and the Blinn node use, yet its specular highlights are worked out through an optimized Fresnel/Beckmann equation. You reach for this illumination model mainly when shading metal or other glossy, strongly reflective surfaces. What the Cook Torrance node puts out is a 3D Material you can wire into the material inputs of any 3D geometry node.

### Inputs

The Cook Torrance node carries six inputs that take 2D images or 3D materials. Through them you govern the overall color and image applied to the 3D object, along with the color and texture driving the specular highlight. Every one of these inputs scales the texture map's pixels by the like-named parameters living in the node, which gives you a tidy way to scale portions of the material. Diffuse Color Material: The orange Diffuse Color material input takes a 2D image or a 3D material to act as the object's overall color and texture. Specular Color Material: The green Specular Color material input takes a 2D image or a 3D material to act as the specular highlight's color and texture. Specular Intensity Material: The magenta Specular Intensity material input takes a 2D image or a 3D material for adjusting the specular highlight's intensity. Should that input be a 2D image, the map is built from the Alpha channel and the color channels are thrown away. Specular Roughness Material: The white Specular Roughness material input takes a 2D image or a 3D material to act as a map for tweaking the specular highlight's roughness. The texture map's Alpha gets multiplied by the roughness control's value. Specular Refractive Index Material: The white Specular Refractive Index material input takes a 2D image or a 3D material, treating its RGB channels as the refraction texture. Bump Map Material: A 3D material is all that the white Bump Map material input will take. The usual route is to wire the texture into a Bump Map node, then run that Bump Map node into this input, where the RGB information is read as texture-space normals. Every one of these inputs scales the texture map's pixels by the like-named parameters living in the node, which gives you a tidy way to scale portions of the material. Once a node sports this many inputs, wiring them up precisely gets tricky. Press and hold the Option (macOS) or Alt (Windows) key as you drag another node's output across the node tile, and keep Option or Alt down as you let go of the left mouse button. Up pops a compact drop-down menu naming every input the node exposes; click the one you want to seal the connection.

### Basic Node Setup

You route a Cook Torrance node's output into the material input of whichever 3D scene or 3D geometry node you mean to shade. The Cook Torrance inputs accept images for the diffuse color material (yellow) and the specular color material (green), which can yield a smooth, glossy material.

A Cook Torrance shader with diffuse and specular color materials connected

### Inspector

### Cook Torrance controls

### Controls Tab

On the Controls tab you'll find parameters for tuning the Cook Torrance shader node's main color, highlight, and lighting properties.

### Diffuse

Diffuse stands for the fundamental surface traits before extras like reflections or specular highlights come into play. Beyond fixing an object's base color, the diffuse color also governs how transparent the object is, and a diffuse texture map's Alpha can render chosen parts of the surface see-through. Diffuse Color The Diffuse Color of a material is the base color it presents under indirect or ambient lighting. Hand it a diffuse texture map and the color value here is multiplied against the texture's color values. Alpha This slider fixes the material's Alpha channel value, weighing equally on diffuse and specular colors and on the material's Alpha value in the rendered output. Hand it a diffuse texture map and the Alpha value here is multiplied against the texture map's Alpha values. Opacity Pulling down the material's Opacity cuts the color and Alpha values of the specular and diffuse colors in equal measure, rendering the material transparent.

### Specular

The Specular section's parameters lay out how the surface's specular highlight looks, and each illumination model evaluates these values its own way. Specular Color Specular Color fixes the color of light reflecting off a glossy surface. The more specular the material, the glossier it reads. Plastics and glass typically carry white specular highlights, whereas metallic surfaces such as gold draw their highlight color from the material color. Hand it a specular texture map and the value here is multiplied against the texture's color values. Specular Intensity Specular Intensity rules how strong the specular highlight comes across. Hand it the specular intensity texture and this value is multiplied against the texture's Alpha value. Roughness The specular highlight's Roughness captures how the highlight spreads across the surface. A larger value broadens the falloff and lends the surface a more brushed, metallic feel. Hand it the roughness texture map and this value is multiplied against the texture's Alpha value. Do Fresnel Ticking this checkbox folds Fresnel calculations into the material's illumination model, yielding more believable metal surfaces by factoring in the material's refractiveness. Refractive Index This slider surfaces once the Do Fresnel checkbox is ticked. The Refractive Index bears only on the highlight calculations; it does not actually refract light through transparent surfaces. Hand it the refractive index texture map and this value is multiplied against the input's Alpha value.

### Transmittance

Transmittance rules how light makes its way through a material. Consider a solid blue sphere, which throws a black shadow, against one of translucent blue plastic, which would throw a far fainter blue shadow. A separate Opacity option is on hand as well. Opacity decides how transparent the actual surface comes out when rendered. Fusion lets you tune opacity and transmittance independently — a notion that may strike newcomers to 3D software as odd at first. You really can have a surface that is fully opaque yet still passes 100% of the light reaching it, which in effect turns it into a luminous/ emissive surface. Attenuation Attenuation rules how much color travels through the object. To grant an object transmissive shadows, set the attenuation to (1, 1, 1), so all of the green, blue, and red light passes through. Set this color to RGB (1, 0, 0) and the material lets 100% of the red striking the surface through while blocking the green and blue. You can lean on this to fashion “stained glass”-styled shadows.

Alpha Detail Hold the Alpha Detail slider at 0 and the object's Alpha channel is passed over, so the whole object throws a shadow. Raise it to 1 and the Alpha channel decides which parts of the object throw one. Color Detail The Color Detail slider colors the light crossing the surface by the diffuse color + texture colors. Turn to it to cast a shadow that carries the color details of the texture on the object. Nudging the slider from 0 toward 1 pours more diffuse color + texture color into the shadow. Mind that the object's Alpha and opacity are bypassed while color is transmitted, so an object with solid Alpha can still pour its color into the shadow. Saturation The Saturation slider commands the saturation of the color component sent to the shadow. Bring it to 0.0 and the shadows come out monochrome. Receives Lighting/Shadows These checkboxes decide whether the scene's lighting and shadows reach the material. Switch them off and the object stays fully lit and/or free of shadow. Two-Sided Lighting This in effect makes the surface two sided by tacking on a second set of normals that point the other way on the surface's backside. It normally rests off to keep rendering quick, but you can switch it on for 2D surfaces or for objects that aren't fully sealed, so their reverse or interior surfaces become visible too. Typically a 3D application shows only a surface's front face and culls the back, so a camera circling a plane in such an application would watch the plane disappear upon reaching the backside. Making a plane two sided in a 3D application comes down to laying a second plane atop the first, turned 180 degrees so its backside normals point the opposite way. Hence, swinging around the back reveals that second image plane with its normals facing the other direction. NOTE: This can grow rather bewildering once the surface goes transparent, since the same rules persist and hand you a counterintuitive result. Look at a transparent two-sided surface from the front while it is lit from behind, and it appears unlit. Material ID This slider hands this material its numeric identifier. That value lands in the MatID auxiliary channel whenever the matching option is enabled in the renderer.

### Common Controls
