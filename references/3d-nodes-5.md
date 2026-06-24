# 3D Nodes (part 5)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Enable Shadows: Tick the Enable Shadows checkbox when you want a light to cast shadows. Its default state is selected.
- Shadow Color: This ordinary Color control lets you choose the shadow’s color. Its default is black (0, 0, 0).
- Density: How see-through a shadow is comes down to the Shadow Density. At a density of 1.0 the shadow becomes fully transparent, while smaller figures render the shadow transparent.
- Shadow Map Size: The dimensions of the bitmap behind the shadow map are governed by the Shadow Map Size control. Bigger figures yield finer shadow maps, though they cost more memory and performance.
- Shadow Map Proxy: For proxy and auto proxy calculations, the Shadow Map Proxy sets how large the shadow map is. Setting it to 0.5, for instance, applies a 50% shadow map.
- Multiplicative/Additive Bias: Because shadows amount to textures laid over the scene’s objects, Z-fighting crops up now and then, in which the parts of an object meant to catch the shadows draw on top of the shadow rather than beneath it.
- Multiplicative and Additive Bias: Bias operates by introducing a slight depth offset that nudges the shadow off the surface it falls on, doing away with the Z-fighting. With too little bias, objects may cast shadows onto themselves. With too much, the shadow may detach from its surface. Tune the multiplicative bias first, then refine the outcome through the additive bias control.
- Force All Materials Non-Transmissive: As a rule, shadow rendering relies on an RGBAZ shadow map. Switching this option on compels the renderer to adopt a Z-only shadow map instead. The payoff can be markedly quicker shadow rendering at roughly a fifth of the memory. The trade-off is losing the ability to throw “stained-glass”-style shadows.
- Shadow Map Sampling: Determines the sampling quality applied to the shadow map.
- Softness: Filtering the shadow map during sampling is what gives shadows their soft edges. Fusion offers three distinct filtering approaches, each yielding a different look when shadows render. None: Shadows keep a hard edge. The shadow map gets no filtering whatsoever. Its upside is that just a single pixel of the shadow map needs sampling, which makes it quick.

Constant: Every shadow edge carries the same softness. Sampling the shadow map employs a filter of fixed width. The filter’s size is governed by the Constant Softness slider. Keep in mind that a wider filter lengthens how long the shadows take to render. Setting the Softness to constant brings up a Constant slider. You use it to dial in the shadow’s overall softness. Variable: Shadow edges turn softer the greater the gap between the shadow receiver and the shadow caster. This variable softness comes from resizing the filter according to the receiver-to-caster distance. Choosing this option reveals the Softness Falloff, Min Softness and Max Softness sliders. Softness Falloff: The Softness Falloff slider shows up once Softness is set to variable. It governs how quickly shadow-edge softness builds as distance increases. Put more exactly, it sets how rapidly the shadow map filter size expands relative to the caster-to-receiver distance. The Min and Max Softness slider values temper its impact. Min Softness: The Min Softness slider surfaces when Softness is variable. It dictates the shadow’s Minimum Softness. The nearer the shadow lies to the object that casts it, the crisper it stays, bounded by the limit this slider sets. Max Softness: The Max Softness slider surfaces when Softness is variable. It dictates the shadow’s Maximum Softness. The farther the shadow sits from the object that casts it, the softer it grows, bounded by the limit this slider sets.

### Common Controls

Transform and Settings Tabs A great many 3D nodes share the leftover Transform and Settings tabs. You’ll find them described under this chapter’s closing “The Common Controls” section.

### Renderer3D [3Rn]

### The Renderer 3D node

### Renderer3D Node Introduction

Taking the 3D environment and turning it into a 2D image is the job of the Renderer 3D node, which uses either a default perspective camera or a camera already in the scene. Each 3D scene within a composition wraps up with one or more Renderer 3D nodes. To generate the final image, the Renderer node carries both a software and an OpenGL render engine. Third-party plugins may furnish further render engines as well. The software render engine leans solely on the system’s CPU to produce its rendered images. Typically far slower than the OpenGL render engine, it nonetheless gives identical results on every machine, which makes it indispensable for renders that span a network. Soft shadows demand the Software mode, which on the whole handles all the available illumination, texture, and material features. By contrast, the OpenGL render engine taps the graphics card’s GPU processor to speed up rendering the 2D images. Results can shift a little between systems, hinging on precisely which graphics card sits inside. Outcomes from the OpenGL renderer can be swayed by the graphics card driver too. Thanks to the OpenGL render engine’s speed, tailored supersampling and lifelike 3D depth of field options become feasible. Soft shadows lie beyond the OpenGL renderer’s reach. When you need soft shadows, reach for the software renderer. As with the bulk of nodes, you’ll locate the Renderer’s motion blur settings beneath the Common Controls tab. Take note that for scenes holding particle systems, the Motion Blur settings on the pRender nodes have to line up precisely with those on the Renderer 3D node. If they don’t, the subframe renders clash and throw out unexpected (and incorrect) results. NOTE: The Open GL renderer honors the Color Depth option found in the Image tab of the Renderer 3D node. On some graphics cards this may drag down performance when rendering to int16 or float32.

### Inputs

Two inputs sit on the Renderer 3D node. Its primary scene input receives the Merge 3D, or any other 3D nodes, that you need flattened to 2D. Output from the Renderer 3D is constrained by the effect mask. SceneInput: This mandatory orange scene input takes a 3D scene you intend to convert into 2D. EffectMask: The blue effects mask input relies on a 2D image to mask whatever the node outputs.

### Basic Node Setup

Every 3D scene has to conclude with a Renderer 3D node. Its purpose is to turn a 3D scene into a 2D image. In the example below, the Renderer 3D node grabs a Merge 3D node’s output and renders that 3D scene as a 2D image.

Here a Renderer 3D sits immediately downstream of a Merge 3D, turning that 3D scene into a 2D image Multilayer Support By default the Renderer 3D tool emits layers and builds several lighting passes to set up for compositing. It turns out seven discrete layers: Shadow, Diffuse, Specular, Ambient, Reflect, Refract, and Fog. While the renderer still delivers a finished result, each pass that contributes to that image is now reachable on its own, handing you extra command over the end result. These layers can be previewed straight in the viewer via the layer preview control. To assemble a single combined output, employ any compositing node such as Merge, MultiMerge or Channel Booleans. Every pass should be ‘added’ together, save for Shadow, which has to be Multiplied.

### Inspector

### Render 3D controls

### Controls Tab

Camera Which of the scene’s cameras does the rendering is picked through the Camera menu. Choosing Default grabs the very first camera in the scene. Where no camera turns up, the fallback perspective view steps in. Eye Configuring how stereoscopic projects render happens via the Eye menu. Picking Mono disregards the camera’s stereoscopic settings. The Left and Right choices shift the camera according to the stereo Separation and Convergence options set in the camera, yielding either left- or right-eye output. Selecting Stacked layers the two images vertically rather than placing them side by side. Layers lets the left and right eyes emerge as separate layers. Reporting Whether the node writes warnings and errors generated during rendering to the console is governed by this section’s first pair of checkboxes. The second pair tells the node whether to halt rendering the moment a warning or error shows up. By default all four checkboxes on this node are on. Renderer Type The render engines on offer are enumerated by this menu. Fusion ships three of them: the software renderer, OpenGL renderer, and the OpenGL UV render engine. More renderers can arrive through third‑party plugins. Whatever controls appear under this drop-down menu come from the render engine itself. They shift according to what each renderer makes available. For that reason, every renderer gets its own write-up below.

### Software Controls

Output Channels Apart from the customary Red, Green, Blue, and Alpha channels, the software renderer is able to bake these further channels into the image. Switching on extra channels eats more memory and processing time, so reserve them for when they’re actually needed.

- RGBA: Selecting this directs the renderer to generate the image’s Red, Green, Blue, and Alpha color channels. Because they’re mandatory, these channels can’t be switched off.
- Z: Turning this on enables the Z-channel render. Each pixel in the Z-channel holds a value standing for that pixel’s distance away from the camera. Bear in mind the Z-channel values can’t carry anti-aliasing. Wherever several depths overlap in a pixel, the nearest depth value wins for that pixel.
- Coverage: Turning this on enables the Coverage channel render. Held within the Coverage channel is data about which Z-buffer pixels supply coverage (those overlapping other objects). It assists nodes leaning on the Z-buffer to deliver a touch of anti-aliasing. Each pixel’s value here reports, in percentage terms, how much of that pixel the foreground object makes up.
- BgColor: Turning this on enables the BgColor channel render. What this channel holds are the color values belonging to objects sitting behind the pixels covered in the Coverage channel.
- Normal: Turning this on enables the X, Y, and Z Normals channel render. Pixel values across these three channels signal the orientation (direction) of every pixel within 3D space. Each axis is captured by a color channel whose values span the range [–1,1].
- TexCoord: Turning this on enables the U and V mapping coordinate channel render. The texture coordinates of each pixel reside in these channels. Even though the 3D system handles texture coordinates internally as three-component UVW, Fusion images retain only the UV components. Those components land in the Red and Green color channel.
- ObjectID: Turning this on enables the ObjectID channel render. Any object in the 3D environment may receive a numeric identifier at creation time. The pixels of this floating-point image channel hold the values given to whichever objects formed the pixel. A blank pixel carries an ID of 0, and the channel accepts values up to 65534. A single Object ID can be shared across multiple objects. This buffer comes in handy for pulling mattes from the shapes of scene objects.
- MaterialID: Turning this on enables the Material ID channel render. Any material in the 3D environment may receive a numeric identifier at creation time. The pixels of this floatingpoint image channel hold the values given to whichever materials formed the pixel. A blank pixel carries an ID of 0, and the channel accepts values up to 65534. A single Material ID can be shared across multiple materials. This buffer is handy for pulling mattes off a texture; say, a mask gathering every pixel that makes up a brick texture.

### Lighting

- Enable Lighting: Ticking the Enable Lighting checkbox causes whatever lights exist in the scene to illuminate objects. With no lights around, every object renders black.
- Enable Shadows: Ticking the Enable Shadows checkbox has the renderer cast shadows, though it gives up a little speed.

### OpenGL Controls

### Render 3D Open GL controls

Output Channels On top of the customary Red, Green, Blue, and Alpha channels, the OpenGL render engine can likewise bake the channels below into the image. Activating extra channels draws on more memory and processing time, so keep them for occasions that truly call for them.

- RGBA: Picking this instructs the renderer to build the image’s Red, Green, Blue, and Alpha color channels. Being required, these channels cannot be turned off.
- Z: This switches on the Z-channel render. A value sits in each Z-channel pixel that conveys how far that pixel lies from the camera. Keep in mind anti-aliasing can’t be folded into the Z-channel values. Where multiple depths stack in one pixel, the closest depth value is what that pixel takes.
- Normal: This switches on the X, Y, and Z Normals channel render. The pixel values in these three channels point to the orientation (direction) each pixel holds in 3D space. Every axis is conveyed by a color channel whose values run from [–1,1].
- TexCoord: This switches on the U and V mapping coordinate channel render. Sitting in these channels are the texture coordinates of each pixel. Despite the 3D system handling texture coordinates internally as three-component UVW, Fusion images keep only the UV components. Those components get mapped onto the Red and Green color channels.
- ObjectID: This switches on the ObjectID channel render. At creation, each object in the 3D environment can take a numeric identifier. Sitting in this floatingpoint image channel are the values handed to whatever objects spawned the pixel. Blank pixels carry an ID of 0, and the channel reaches values as high as 65534. One Object ID may be shared among several objects. This buffer proves useful for drawing mattes from the shapes of objects in a scene.
- MaterialID: This switches on the Material ID channel render. At creation, each material in the 3D environment can take a numeric identifier. Sitting in this floating‑point image channel are the values handed to whatever materials spawned the pixel. Blank pixels carry an ID of 0, and the channel reaches values as high as 65534. One Material ID may be shared among several materials. This buffer proves useful for drawing mattes from a texture—for instance, a mask gathering every pixel forming a brick texture.

### Anti-Aliasing

Through the Channel menu you can switch anti-aliasing on for each individual channel. By brute force it yields an output image with finer anti-aliasing: it renders a far bigger image, then scales that down to the target resolution. You could reach precisely the same outcome by rendering the oversized image yourself first, then running a Resize node to drop it to the resolution you want. Yet the renderer’s built-in supersampling holds two clear edges over that route. For one, the render isn’t hemmed in by memory or image-size ceilings. Picture, say, what it takes to make a float-16 1920 x 1080 image at 16x supersampling. The conventional Resize node path would have you first render at a resolution of 30720 x 17280, then apply a Resize to shrink that image back to 1920 x 1080. Merely creating that image would call for close to 4 GB of memory. Doing the anti-aliasing on the GPU lets the OpenGL renderer lean on tile rendering to cut memory use dramatically. The GL renderer can rescale the image right on the GPU faster than the CPU could pull it off. As a rule, the more GPU memory the graphics card holds, the quicker the work goes. While working interactively, Fusion bypasses the anti-aliasing stage unless the HiQ button in the Time Ruler is active. Supersampling always factors into final-quality renders whenever it’s switched on. Owing to hardware constraints, point geometry (particles) and lines (locators) always render at their native size regardless of supersampling. The upshot is that these elements get scaled down from their original dimensions and tend to look far thinner than you’d expect.

Anti-Aliasing of Aux Channels in the OpenGL Renderer Why does the AntiAliasing preset give color and aux channels their own distinct anti-aliasing controls? Because supersampling color channels runs noticeably slower than supersampling aux channels. For color you might get by with a 1 x 3 LowQ/HiQ Rate, yet world position or Z could demand 4 x 12 before the results hold up. Color anti-aliasing lags because the RGBA shaders can run 10x, even 100x or 1000x more complex, and color renders with sorting turned on, whereas aux channels render through the much speedier Z-buffer method. TIP: With certain things an SS Z-buffer can lift quality, while with others — such as the merge’s PerformDepthMerge option — it can degrade them. Don’t equate anti-aliasing with higher quality. Anti-aliasing an aux channel is no guarantee of better quality. Quite often, in fact, anti-aliasing an aux channel makes the outcome considerably worse. WorldCoord and Z are the sole aux channels we’d suggest enabling anti-aliasing on. TIP: We firmly advise switching Anti-Aliasing off for the Material ID and Object ID channels, plus TexCoord, Normal, BackVector, and Vector channels. The trouble surfaces once a single pixel spans multiple 3D surfaces with wildly different TexCoord values. Anti-aliasing won’t confine itself to the primary surface; it samples both surfaces. Suppose, for instance, one surface holds TexCoords near (u,v) = (0, 0) inside that pixel while the other holds (0.5, 0.5) — you wind up with a blend of the two. That blended patch of the texture might take on colors like (0, 0) or (0.5, 0.5), spitting out an oddly tinted pixel artifact from the 2D Texture node. Normals can fall prey to the very same issue. Enable (LowQ/HiQ) This pair of check boxes turns on anti aliasing for the rendered image. Supersampling LowQ/HiQ Rate How far the OpenGL render scales the image is set by the LowQ and HiQ rate. Say the rate sits at 4 and the OpenGL renderer is told to output a 1920 x 1080 image; internally it renders a 7680 x 4320 image and then scales it back to make the target image. Push the multiplier up for crisper edge anti-aliasing, paying for it in render time. As a rule, 8 x 8 supersampling (64 samples per pixel) handles most aliasing artifacts. The rate isn’t a precise count of samples per destination pixel; the breadth of the reconstruction filter in use can sway it too. Filter Type While downsampling the oversized image, the pixels neighboring a given pixel typically feed into a more lifelike result. A range of filters exist for blending those pixels. Fancier filters can sharpen the result yet generally cost more to compute. Which filter suits the task tends to ride on how much scaling is involved and on what the image itself contains.

What each of these filters does is illustrated in the image above. Reading left to right, they are:

Box Bi-Linear (triangle) Bi-Cubic (quadratic) Bi-Spline (cubic) Catmul-Rom Gaussian Mitchell Lanczos Sinc Bessel

This performs a straightforward interpolation scaling of the image. This relies on a basic filter that turns out fairly clean, quick results. This filter yields a middling result. The balance it strikes between speed and quality is solid. This gives stronger results on continuous tone images yet runs slower than Quadratic. Where images hold fine detail, the result can come out blurrier than you’d like. This works well on continuous tone images scaled down, delivering crisp results on finely detailed images. In speed and quality it sits very close to Quadratic. This resembles Catmull-Rom but does a better job on finely detailed images, at the cost of running slower than Catmull-Rom. This is much like Mitchell and Catmull-Rom, only a touch cleaner and a touch slower. This advanced filter delivers exceptionally sharp, detailed results, though in certain cases it can introduce visible `ringing'. This behaves much like the Sinc filter but can be a bit quicker.

Window Method Only when the reconstruction filter is Sinc or Bessel does the Window Method menu show up.

- Hanning: A plain tapered window.
- Hamming: Hamming amounts to a lightly adjusted take on Hanning.
- Blackman: A window whose falloff tapers more steeply.

Accumulation Effects Building depth of field effects is what accumulation effects are for. Switch on both the Enable Accumulation Effects and Depth of Field checkboxes, then work the quality and Amount sliders. The blurrier you’d like the out-of-focus regions, the higher you’ll push the quality setting. Dialing the amount down keeps a larger share of the scene in focus. These accumulation effects operate hand in hand with the Focal plane setting found in the Camera 3D node. Match the Focal Plane to the same distance from the camera as whatever subject you want sharp. Keyframing the Focal Plane setting produces rack of focus effects.

### Lighting

- Enable Lighting: Selecting the Enable Lighting checkbox lets whatever lights the scene holds illuminate its objects. Absent any lights, all objects come out black.
- Enable Shadows: Selecting the Enable Shadows checkbox makes the renderer generate shadows, trading away a bit of speed.

### Texturing

- Texture Depth: Lets you set what bit depth texture maps use.
- Warn about unsupported texture depths: Triggers a warning whenever texture maps arrive in a bit depth Fusion can’t handle.

Lighting Mode Lighting gets computed at every vertex of the scene’s geometry under the Per-vertex lighting model. That delivers a quick estimate of the scene’s lighting, though it’s prone to blocky lighting across poorly tessellated objects. Taking a different tack, the Per-pixel method doesn’t depend on the geometry’s detail for its lighting, so its results are generally better. Even though per-pixel lighting under the OpenGL renderer lands nearer to what the more precise software renderer turns out, it carries a few drawbacks still. Handling semi-transparency, soft shadows, and colored shadows correctly is harder for the OpenGL renderer, per-pixel lighting notwithstanding. What the system’s graphics card can do caps the rendering’s color depth. Transparency For picking which ordering method drives the transparency calculation, the OpenGL renderer exposes this control.

- Z Buffer (fast): Blazingly quick, this mode does the job for scenes made up only of opaque objects. Its speed sacrifices accurate sorting, though; just the objects nearest the camera are guaranteed to land in the right sort order. Consequently, semi-transparent objects might not display correctly, hinging on where they fall within the scene.
- Sorted (accurate): Ahead of rendering, this mode sorts every object in the scene (giving up some speed) to deliver correct transparency.
- Quick Mode: An experimental mode that fits scenes made up almost entirely of particles best.

Shading Model This menu is where you choose the shading model applied to the scene’s materials. Smooth matches the shading model the viewers use, whereas Flat gives a plainer, quicker shading model. Wireframe Draws the entire scene as wireframe. That exposes the objects’ edges and polygons. Those edges still take their shading from the objects’ material. Wireframe Anti-Aliasing Switches on anti-aliasing for the Wireframe render.

### OpenGL UV Renderer

A special-case render engine, the OpenGL UV renderer takes a model that already has textures and renders it out into an unwound, flattened 2D version of that model. If you wish, lighting can be baked into it. The usual reason for doing so is to let you paint over the texture afterward and reapply it.

### Render 3D Open GL UV controls
