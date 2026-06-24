# 3D Compositing Basics (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Three spheres, left to right: diffuse only, specular only, and combined What the specular exponent governs is the falloff of the specular highlight. Push the value higher and the falloff grows sharper while the specular component shrinks.

Left to right: white, complimentary, and matching specular colors Transmittance With the software renderer, the Transmittance parameters set how light travels through a semi-transparent material. As an illustration, a solid blue pitcher throws a black shadow, whereas one built from translucent blue plastic would throw a far lower density blue shadow. Those transmittance parameters are vital to conjuring the look of stained glass.

TIP: A material’s opacity and transmittance can be tuned independently of each other. A surface can be fully opaque and yet pass 100% of the light that lands on it, so in a way it acts as a luminous/emissive surface. Transmissive surfaces can be reined in further by way of the Alpha and Color Detail control.

### Attenuation

How much color travels through the object is set by the transmittance color. For an object to throw fully transmissive shadows, the transmittance color has to be set to RGB = (1, 1, 1), meaning 100% of the green, blue, and red light passes through the object. Set this color to RGB = (1, 0, 0) and the material then passes 100% of the red landing on the surface but none of the green or blue light.

### Alpha Detail

With the Alpha Detail slider at 0, the non-zero regions of the diffuse color’s alpha channel get disregarded and the object’s opaque regions throw a shadow. Set it to 1 and the alpha channel then sets how dense a shadow the object throws. NOTE: The OpenGL renderer disregards alpha channels while rendering shadows, so a shadow always ends up thrown from the whole object. Alpha in the shadow maps is backed by the software renderer alone. The examples below for Alpha Detail and Color Detail throw a shadow built from this image. It runs as a green-red gradient from left to right. Its outer edges are transparent, and inside sits a small semi‑transparent circle.

Alpha Detail set to 1; shadow density is driven by the alpha channel

Alpha Detail set to 0; the upshot is a dense-colored shadow Color Detail Color Detail serves to tint the shadow with the object’s diffuse color. With the Color Detail slider lifted from 0 toward 1, additional diffuse color plus texture enters the shadow. TIP: The OpenGL renderer will forever throw a black shadow from the whole object, paying no heed to the color. Color in the shadow maps is backed by the software renderer alone.

Color Detail set to 0; no color is visible in the shadow.

Saturation Saturation lets the diffuse color texture set the shadow’s density without touching the color. This slider lets you mix between the full color and luminance only. Transmittance and Shadows A material’s transmittance plays a major part in setting how the shadow it throws looks. As a rule, that transmittance behavior gets defined within each object’s Materials tab as covered above. Ticking Force All Materials Non-Transmissive in the Spotlight Inspector overrides this, though, making the shadow map the spotlight produces disregard transmittance altogether.

### Illumination Models

With the various components that build up a material or shader now clear to you, we’ll examine them in more detail. Illumination models are sophisticated materials for crafting lifelike surfaces such as plastic, wood, or metal. Every illumination model carries upsides and downsides that suit it to particular looks. Since an illumination model sets how a surface answers light, these nodes need at least one light source for the object’s look to change. The Nodes > 3D > Material menu holds four different illumination models. Illumination models, in left-to-right order: Standard, Blinn, Phong, Cook-Torrance, and Ward Standard What the Standard material gives is a default Blinn material with basic command over the diffuse, specular, and transmittance components. For the diffuse component it accepts only a single texture map, with the alpha serving as opacity. The Standard Material controls sit within the Material tab on every node that loads or builds geometry. Wire any node that puts out a material into that node’s Material Input and the Standard material gets overridden, with the controls in the Material tab going hidden.

### Blinn

The Blinn material is an all-purpose material pliable enough to stand in for both metallic and dielectric surfaces. While it draws on the same illumination model as the Standard material, the Blinn material opens up a finer degree of command by offering extra texture inputs for the specular color, intensity, and exponent (falloff), plus bump map textures.

### Phong

The Phong material gives the same diffuse outcome as Blinn but with broader specular highlights at grazing incidence. Phong can equally make sharper specular highlights at high exponent levels.

### Cook-Torrance

The Cook-Torrance material fuses the Blinn material’s diffuse illumination model with a joint microfacet and Fresnel specular model. Those microfacets need not exist within the mesh or bump map; a statistical function, Roughness, stands in for them, and it can be mapped. According to the Refractive Index, which can be mapped, the Fresnel factor dampens the specular highlight.

### Ward

The Ward material carries the same diffuse model as the rest but layers on anisotropic highlights, perfect for mimicking brushed metal or woven surfaces, since the highlight can be stretched along the mapping coordinates’ U or V directions. Each of the U and V spread functions is mappable. This material does call for properly structured UV coordinates on whatever meshes it lands on.

### Textures

Texture maps reshape how a material looks on a per-pixel basis. That happens by wiring an image or another material into the inputs on the Material nodes within the Node Editor. Where a 2D image gets used, the geometry’s UV mapping coordinates serve to fit the image onto the geometry, and as each pixel of the 3D scene gets rendered, the material reshapes the material input per the value of the matching pixel in the map. TIP: UV Mapping is the technique used to wrap a 2D image texture onto 3D geometry. Much like X and Y coordinates within a frame, U and V are the coordinates for textures across 3D objects.

A range of material inputs gets reshaped by texture maps, among them diffuse color, specular color, specular exponent, specular intensity, bump map, and others. Where texture maps see the most use is the diffuse color/opacity component.

The Fast Noise texture put to work driving the roughness on a Cook-Torrance material

A node that puts out a material gets reached for often, in place of an image, to offer other shading options. The materials handed between nodes are RGBA samples; they hold no further information about the shading or textures that gave rise to them.

The Texture2D node serves to shift a texture within the object’s UV space, as well as set the filtering and wrap mode Composite Materials Building intricate materials comes down to wiring the output of one Material node into one of the Material inputs on another Material or Texture node. Where a Material input gets supplied, just as with a 2D image, its RGBA values serve per pixel as a texture. That allows for very direct compositing of shaders. As an instance, to pair an anisotropic highlight with a Blinn material, you can take the Blinn’s output, specular included, and use it as the diffuse color of the Ward material. Or, should you not want the Blinn’s output relit by the Ward material, you can reach for the Channel Boolean material so the Ward material’s anisotropic specular component gets laid onto the Blinn material with a finer degree of command.

Pairing an anisotropic highlight together with a Blinn material by way of the Channel Boolean material

### Reflections and Refractions

Environment maps can be laid on with the Reflect material under the 3D > Material category. This node can serve to mimic reflections and refractions across an object. Reflections are direct-bounce light striking an object, whereas refractions mimic how light distorts when seen through semi-translucent surfaces. The reflections and refractions lean on an environment mapping technique to yield an approximation that balances lifelike results against greater rendering performance. Environment maps treat whatever surrounds an object as infinitely far away and rendered down into a cubic or spherical texture enclosing it. To help build environment maps, you have the Nodes > 3D > Texture > Cube Map and Sphere Map nodes, which lay special processing and transforms on to mint the cubic or spherical coordinates required.

### Sphere map example

To yield reflections with real-time interactive feedback at a quality fit for production environment maps, you accept some trade-offs in functionality versus the slower but physically accurate raytraced rendering. Environment-mapped reflections and refractions offer no self-reflection nor any other sort of interaction across separate objects. This infinite distance assumption, in particular, means objects cannot interact with themselves (for instance, the reflections on a teapot’s handle will not show the teapot’s body). It equally means objects sharing the same cube map will not inter-reflect with one another. As an example, two adjacent objects would not reflect each other. A separate cube map has to be rendered per object. The Reflect node puts out a material that can land on an object directly, yet the material holds no illumination model. Consequently, objects textured straight by the Reflect node will not answer the scene’s lights. That is why the Reflect node usually gets paired with the Blinn, Cook-Torrance, Phong, or Ward nodes.

### Reflection

Reflection puts out a material that makes it possible to lay the reflection or refraction onto other materials either ahead of or after the lighting model for differing effects.

A Blinn material wired into a background material input on the Reflect; the result is the reflection getting added onto the Blinn output

Here a Reflect feeds the Diffuse Color component on the Blinn, so the reflection ends up multiplied against the diffuse color and shaped by the lighting

### Refraction

Refraction shows up only where transparency exists in the background material, which generally gets steered through the Opacity slider and/or the alpha channel of whatever material or texture feeds the Background Material Texture input. The Reflect node offers the following material inputs:

- Background Material: Sets the refraction opacity along with the reflection’s base color.
- Reflection Color Material: The environment reflection.
- Reflection Intensity Material: A multiplier for the reflection.
- Refraction Tint Material: The environment refraction.
- Bump Map Texture: Normal perturbing map for environment reflection/refraction vectors.

Handling reflection and refraction can get fiddly. Below are a few techniques to ease it:

- As a rule, lean on a modest amount of reflection, somewhere between 0.1 and 0.3 strength. Higher values suit surfaces such as chrome.
- Bump maps can lend detail to the reflections/refractions. Reach for the same bump map within the Illumination model shader that you pair with Reflect.
- Where detailed reflections aren’t called for, lean on a fairly small cube map, say 128 x 128 pixels, and blur the image out.
- The alpha of refracted pixels gets set to 1 even though those pixels are technically transparent. Refracted pixels raise their alpha by the reflection intensity.
- Should the refraction stay invisible even with a texture wired into the Refraction Tint Material input, take a second look at the background material’s alpha/opacity values.

### Bump Maps

Bump mapping helps lend detail and tiny irregularities onto an object’s surface look. What bump mapping does is reshape the object’s geometry or change its silhouette.

Split screen of a sphere—half with bump map, half without To lay on a bump map, you typically wire an image holding the bump information into the BumpMap node. That bump map then gets wired into the Bump input on a Material node. Two routes exist for building a 3D material’s bump map: by way of a height map and by way of a bump map.

Image connected to a BumpMap connected to a CookTorrance material node

### Using a Height Map

A height map is an image where a pixel’s value stands for the height. You can pick which color channel drives bump creation. White stands for high and black for low; what sets the bumpiness, though, isn’t a pixel’s value in the height map but rather how that value shifts across a pixel’s neighborhood.

### Using a Bump Map

A bump map is an image holding normals tucked into the RGB channels. TIP: Normals get produced by 3D modeling and animation software as a means of fooling the eye into perceiving smooth surfaces, even though the geometry that builds the models leans only on triangles to assemble the objects. Normals are 3 float values (nx, ny, nz) whose components sit within the range [–1, +1]. Since only positive values can be stored within Fusion’s integer images, the normals get packed out of the range [–1, +1] and into the range [0, 1]: each is scaled by 0.5, then 0.5 is added on. To handle the unpacking, you can lean on Brightness Contrast or a Custom node. Were you to wire a bump map straight into a material’s bump map input, incorrect lighting would result. Fusion blocks you from doing this, however, because Fusion leans on a different coordinate system for the lighting calculation. You first have to route through a BumpMap, which anticipates a packed bump map or height map and performs the bump map’s conversion so it ends up behaving correctly.

Should your bump mapping look off, here are a few things worth checking:

- Confirm the nodes are wired correctly. The height/bump map ought to feed into a BumpMap and then, in turn, ought to feed into the bump map input on a material.
- Shift the precision of the height map to win less banding across the normals. For low frequency images, float32 may be required.
- Tune the Height scale on the BumpMap. This scales the bump map’s overall effect.
- Confirm you set the type to HeightMap or BumpMap to align with the image input. Fusion cannot work out which type of image you have.
- Verify High Quality is on (right-click within the transport controls bar and pick High Quality off the contextual menu). Certain nodes such as Text+ yield an anti-aliased version in High Quality mode that will markedly lift bump map quality.
- Should you be leaning on an imported normal map image, confirm it is packed [0–1] across RGB and sits in tangent space. The packing can happen within Fusion, but the conversion to tangent space cannot.

### Projection Mapping

Projection is a technique for texturing objects by way of a camera or projector node. That can pay off for texturing objects across multiple layers, laying a texture over multiple separate objects, casting background shots from the camera’s vantage, image-based rendering techniques, and a great deal more. Fusion offers three routes to projection mapping.

### Using the Projector/Camera Tool to Project Light

With lighting switched on, a Camera 3D or Projector 3D can stand in as a light carrying every lighting feature. Once Camera Projection is switched on or you reach for a projector, you can pick whether the projection acts like a spotlight or an ambient light; alpha channels, however, cannot be projected. Overlapping projections sum together like any other light node. An internal clipping plane (around 0.01 distance off the camera) bounds how near the projector or camera can come to the projection’s receivers.

### Camera node used for a projection map

### Project a Texture onto a Catcher Material

Should you prefer not to deal with light sources, you can reach for the projector or camera as a texture projector. To run without lighting, a catcher is needed in order to take the texture and lay it onto a material. Only objects on this material will take the projection. That brings certain upsides, such as the projection of alpha channels, plus texturing other channels like specular color or roughness. With the software renderer in play, overlapping projections can be merged in assorted ways (mean, median, blend, and so forth) by way of the Catcher node. With the OpenGL renderer in play, one catcher per projector gets used, and the outcomes can be merged through another material. As with the Light Projection technique, an internal clipping plane (around 0.01 distance off the camera) bounds how near the projector/camera can come to the projection receivers.

Camera projection paired with a Catcher node (this example comes from an earlier Fusion release)

### Project Using the UVMap Node

This mode needs a camera plus a UVMap3D node sitting downstream of the objects the texture is being projected onto. Within the Inspector, once the UVMap Map mode is set to Camera, it pulls the information off the camera and mints fresh UVs for the input objects, which then drive the texturing. Because the UVs sit tucked into the mesh’s vertices, the object has to be tessellated enough. Textures get assigned onto the object like any other texturing technique. The UVs can be pinned to the vertices at a chosen frame through the Ref Time slider. That pinning holds only so long as vertices aren’t created, destroyed, or reordered (for instance, projection locking will not work on particles since they get created/destroyed, nor will it work on a Cube3D while its subdivision level slider is animated). TIP: Projected textures can be permitted to slide over an object. Should the object shift relative to the Projector 3D, or alternatively, once you group the pair beneath a Merge3D, the two shift as a single unit while the texture holds pinned to the object. Within the following slice of a far larger composition, an image (the Loader1 node) gets thrown into 3D space by being mapped across five planes (Shape3D nodes renamed ground, LeftWall, RightWall, Building, and Background), positioned as required inside a Merge3D node to lay reflections onto a 3D car destined for compositing into that scene.

A slice of a composition busy casting a street-scene image into 3D space Whatever the Merge3D node that gathers those planes into a scene puts out then gets handed to a UV Map node, which alongside a Camera3D node correctly casts every one of these planes into 3D space so they look as they would through that camera in the scene. Ahead of this UVMap projection, you can see the planes laid out in space at left, where each plane carries the scene texture mapped onto it. At right sits the image following the UVMap projection, where you can see the scene once more looks “normal,” save for a car-shaped hole brought into the scene.

Five planes setting a street scene into 3D space ahead of UV Projection (left), alongside the UV Map node at work casting those planes so they read as though seen through a camera within the scene (right) This is now a 3D scene, though, primed for a digital car to be set within it, taking reflections and lighting and throwing shadows into the scene as if it belonged there.

The fresh 3D scene throwing reflections and lighting onto a 3D car while taking on the shadows that car produces

### Geometry

Fusion offers five nodes for building geometry. Those nodes can serve a range of purposes. As an instance, the Image Plane 3D mainly serves to drop image clips into a 3D scene, whereas the Shapes node can lend extra building blocks to a 3D set, and Text 3D can lend three-dimensional motion graphics for title sequences and commercials. Although the “3D Nodes” chapter treats each node in more depth, a rundown of the 3D creation nodes follows below. Cube 3D The Cube 3D builds a cube whose six inputs let you map a different texture onto every face of the cube. Image Plane 3D The Image Plane 3D serves as the basic node for setting a 2D image into a 3D scene on a plane scaled automatically. Shape 3D Several basic primitive shapes for piecing a 3D scene together come with this node. Planes, cubes, spheres, cylinders, cones, and toruses are all within its reach. Text 3D The Text 3D is a 3D rendition of the Text+ node. This version supports beveling and extrusion yet lacks support for the multi-layered shading model that Text+ offers. Particles Wire a pRender node into a 3D view and it will push its particles out into the 3D environment. Those particles then get rendered by way of the Renderer3D rather than the Particle renderer.

For further detail, turn to Chapter 114, “Particle Nodes,” within the DaVinci Resolve Reference Manual; that content also lives at Chapter 54 of the Fusion Reference Manual.

### Common Visibility Parameters

Visibility parameters live within the Controls tab on most 3D geometry-producing nodes, surfaced through a disclosure control. Those parameters let you steer an object’s visibility within the viewers and within the final render.

### A 3D geometry node’s visibility parameters

Visible Leave the Visibility checkbox unticked and the object won’t show within a viewer, nor will a Renderer3D render it into the output image. An object that isn’t visible throws no shadows. This is usually on by default, so the objects you build show within both the viewers and final renders. Unseen by Cameras Tick the Unseen by Cameras checkbox and the object will show within the viewers but go invisible when the scene gets viewed through a camera, so a Renderer3D will not render the object into the output image. Shadows an Unseen object throws will still show. Cull Front Face/Back Face Lean on these options to cull (leave out) rendering of certain polygons within the geometry. Tick Cull Back Face and every polygon whose normals face away from the view will go unrendered and throw no shadows. Tick Cull Front Face and every polygon whose normals face away from the view will likewise get left out. Ticking both checkboxes lands the same outcome as unticking the Visible checkbox. Ignore Transparent Pixels in Aux Channels For any bit of geometry, the Renderer3D throws out transparent pixels within the auxiliary image channels. The reason this is the default is to keep aux channels (such as normals, Z-channel, UVs) from filling in where blank space or full transparency belongs. As an example, say in post you want to lend some fog onto the rendered image. Had you fully transparent geometry up front touching the Z-channel, you’d land incorrect fog rendering. Untick this checkbox and the transparency goes unconsidered while every aux channel gets filled across every pixel. That could pay off where you wanted to swap the texture on a 3D element that’s fully transparent across certain areas for a texture that’s transparent across different areas; having the whole object set aux channels (UVs in particular) would come in handy.

### Adding FBX Models

The Filmbox FBX format is a scene interchange format that eases moving 3D scene information from one application across to another. Fusion’s FBX format support stretches model import support over to other 3D files such as Collada and OBJ.

### Importing an FBX Scene

To bring in a whole FBX scene, you add an FBXMesh3D node onto your node tree. Once prompted to pick a scene or object file, Fusion brings it in to build a composition carrying the same lights, cameras, materials, and geometry held within an FBX file.

### An imported model, via the FBXMesh3D node

### FBX Scene Import Dialog
