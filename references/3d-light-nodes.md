# 3D Light Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### 3D Light Nodes

This section walks through the 3D Light nodes you can reach while building 3D composites inside Fusion. Each node name carries a short abbreviation beside it; type that code into the Select Tool dialog to find a tool, and the same code surfaces in scripting references.

Throughout this write-up, any node tree that pictures MediaIn nodes in DaVinci Resolve behaves the same as one using Loader nodes in Fusion Studio, except where a note says otherwise.

### Ambient Light [3AL]

### The Ambient Light node

### Ambient Light Node Introduction

An Ambient Light casts illumination across the whole scene with no particular direction. It carries no meaningful position or rotation, though the viewer still draws an onscreen control so you know a light exists. The viewer also offers position controls so you can slide that widget aside when it overlaps other geometry. As with a Camera 3D, lights are wired into a Merge 3D and become visible only when you view the Merge 3D node; choosing a light node on its own and sending it to the viewer displays nothing.

### Inputs

There is just one optional orange input on the Ambient Light node, meant for a 3D scene or 3D geometry. SceneInput: This optional orange input takes a 3D scene. When you feed it a scene, the node's Transform controls then act on that whole scene.

### Basic Node Setup

Think of the Ambient Light node as one piece of a broader 3D scene. The light wires straight into a Merge 3D, and by routing lights through separate Merge 3D nodes you decide which objects each light reaches.

### Ambient Light node structure

### Inspector

### Ambient Light controls

### Controls Tab

Use the Controls tab to dial in the hue and brightness of the ambient light. Enabled With the Enabled checkbox ticked, the ambient light contributes to the scene; clearing it switches the light off. That checkbox mirrors the red switch sitting to the left of the node’s name in the Inspector. Color This standard Color control picks the light’s color. Intensity Drag this slider to dial the ambient light's Intensity, where 0.2 corresponds to light at 20% percent. As an illustration, a pure-white texture lit by nothing but a 0.2 ambient light renders out as 20% gray (.2, .2, .2).

### Common Controls

Transform and Settings Tabs The parameters shown on the Transform and Settings tabs recur across the other lighting nodes as well. For a fuller description of what each of these tabs offers, turn to the “The Common Controls” section at the end of this chapter.

### Directional Light [3DL]

### The Directional Light node

### Directional Light Node Introduction

A directional light has a definite direction yet no defined origin point or distance, much like sunlight. It does display an onscreen control, but where that control sits carries no significance. Instead, the control's rotation determines the apparent direction the light streams from within the scene. As with a Camera 3D, you wire lights into a Merge 3D and see them by viewing that Merge 3D node; picking a light node alone and loading it into the viewer reveals nothing.

### Inputs

The Directional Light node carries one optional orange input for a 3D scene or 3D geometry. SceneInput: This optional orange input takes a 3D scene, and once a scene is connected the node's Transform controls govern that entire scene.

### Basic Node Setup

The Directional Light node belongs within a larger 3D scene. Run the light straight into a Merge 3D, and split lights across separate Merge 3D nodes when you want to govern which objects each light touches.

### Directional Light node structure

### Inspector

### Directional Light controls

### Controls Tab

Use the Controls tab to choose the hue and brightness of the directional light, while the rotation controls over in the Transform tab steer which way the source points. Enabled Ticking the Enabled checkbox lets the directional light act on the scene; clearing it turns the light off. This checkbox does the same job as the red switch beside the node’s name in the Inspector. Color This standard Color control sets the light’s color. Intensity This slider governs the directional light's Intensity, with 0.2 mapping to light at 20% percent.

### Shadows

The controls here let you define the shadow map this light draws on when casting shadows. For deeper coverage, turn to “3D Compositing Basics” — that is Chapter 85 in the DaVinci Reference Manual, or alternatively Chapter 23 over in the Fusion Reference Manual.

NOTE: For the Directional light to throw visible shadows in the 3D viewer, the Renderer3D node must have its Rendering Type set to Hardware Renderer.

Enable Shadows Tick the Enable Shadows checkbox when you want the light to throw shadows; it is on by default. Shadow Color This standard Color control chooses the shadow's hue, defaulting to black (0, 0, 0). Density How opaque the shadow is comes down to its density: a setting of 1.0 yields a fully solid shadow, and smaller values let more light through. Shadow Map Size The Shadow Map Size control fixes how big the bitmap behind the shadow map is. Bigger values give finer shadow maps but cost more memory and speed. Shadow Map Proxy Shadow Map Proxy governs the shadow map's size while the Proxy or Auto Proxy modes are active. Setting it to 0.5, for instance, yields a shadow map running at half whatever resolution the Shadow Map Size specifies. Multiplicative/Additive Bias Because shadows are really textures laid over scene objects, Z-fighting can crop up, where the parts of an object that ought to catch the shadow instead draw over it. Bias counters this by nudging the shadow a small depth offset away from the surface it falls on, clearing the Z-fighting. With too little bias the objects shadow themselves; with too much the shadow drifts off the surface. Set the Multiplicative Bias first, then refine using the Additive Bias control. Further detail lives in the Multiplicative and Additive Bias portion of “3D Compositing Basics,” which is Chapter 85 of the DaVinci Resolve Reference Manual, or else Chapter 25 within the Fusion Reference Manual. Force All Materials Non-Transmissive By default an RGBAZ shadow map handles the rendering; switch this on and you push the renderer toward a Z-only shadow map instead. That can speed shadow rendering up considerably while consuming only a fifth of the memory, at the cost of losing “stained glass”-style colored shadows. Shadow Map Sampling Sets how finely the shadow map gets sampled. Softness Filtering the shadow map as it is sampled is what gives shadow edges their softness, and Fusion offers two distinct filtering approaches that behave differently. NOTE: A hard-edged shadow skips filtering entirely. Its upside is that a single pixel of the shadow map needs sampling, which keeps it quick.

- Constant: Shadow edges carry a uniform softness. The shadow map is sampled with a fixed-width filter, and the Constant Softness slider scales that filter; bear in mind that a wider filter lengthens shadow render times.
- Variable: Shadow edges soften more the farther the receiver sits from the caster. This variable softness comes from resizing the filter according to the receiver-to-caster distance, and choosing it reveals the Softness Falloff, Min Softness, and Max Softness sliders.

Constant Softness This slider shows up when Softness is set to Constant, and it governs the shadow's overall softness. Softness Falloff Visible when Softness is set to variable, this slider sets how quickly edge softness climbs with distance — more exactly, how fast the shadow map filter widens as the gap between caster and receiver grows, bounded by the Min and Max Softness values. Min Softness Appearing when Softness is Variable, this slider sets the shadow's Minimum Softness: the nearer the shadow is to its casting object, the crisper it stays, down to this slider's floor. Max Softness Also shown when Softness is Variable, this slider sets the shadow's Maximum Softness: the farther the shadow lies from its casting object, the softer it grows, up to this slider's ceiling.

### Common Controls

Transform and Settings Tabs You will encounter the Transform and Settings tab parameters on the other lighting nodes too. For a closer look at what those tabs control, refer to the “The Common Controls” section at the end of this chapter.

### DomeLight [3Do]

### The Dome light

### Dome Light Node Introduction

A Dome Light draws on SDR and HDR images, wrapping the whole scene inside a sphere that is light-mapped with the image, much like an environment light. This light shows an onscreen control.

### Inputs

This node offers an optional orange input for a 3D scene or 3D geometry plus a white Dome Texture input where you attach an image. SceneInput: The optional orange input takes a 3D scene; once one is connected, this node's Transform controls act on the whole scene. DomeTexture: The white input is where an SDR or HDR image plugs in.

### Basic Node Setup

The Dome Light node is meant to sit inside a larger 3D scene. Connect the light straight into a Merge 3D, and keep lights in distinct Merge 3D nodes so you can dictate which objects each light influences.

### Dome Light node structure

### Inspector

### The Dome Light controls

### Controls Tab

Use the Controls tab to set the hue and brightness of the uDome light, while the Transform tab handles the source's position, direction, and scale. Color This standard Color control picks the light's color. Intensity Drag this slider to control the light's intensity, where 0.2 stands for 20% light.

### Point Light [3PL]

### The Point Light node

### Point Light Node Introduction

A point light occupies a definite spot in space and radiates light outward in every direction, much like a light bulb. It carries an onscreen control, though only that control's position and distance matter to the light. Because the source emits a full 360 degrees, its rotation is irrelevant. A point light can also dim with distance, which sets it apart from ambient or directional lights. As with a Camera 3D, lights feed into a Merge 3D and appear in the scene when you view that Merge 3D node; selecting a light node by itself and sending it to the viewer shows nothing.

### Inputs

The Point Light node provides one optional orange input for a 3D scene or 3D geometry. SceneInput: This optional orange input accepts a 3D scene, and supplying one makes the node's Transform controls apply across that entire scene.

### Basic Node Setup

The Point Light node is built to form part of a larger 3D scene. Feed the light directly into a Merge 3D, and by spreading lights over separate Merge 3D nodes you choose which objects feel each light.

### Point Light node structure

### Inspector

### Point Light controls

### Controls Tab

The Controls tab handles the hue and brightness of the point light, while its position and distance are managed over in the Transform tab. Enabled Ticking the Enabled checkbox lets the point light affect the scene, and clearing it switches the light off. This checkbox does the same thing as the red switch beside the node’s name in the Inspector. Color This standard Color control sets the light’s color. Intensity This slider governs the point light's Intensity, with 0.2 equating to light at 20% percent. Decay Type By default a point light uses No Decay, so its illumination stays equally strong everywhere in the scene. If you want the brightness to drop off over distance, switch the Decay Type to either Linear or Quadratic modes.

### Shadows

The controls here let you spell out the shadow map this light relies on when it produces shadows. For additional detail, look to “3D Compositing Basics” — Chapter 85 of the DaVinci Reference Manual — or else Chapter 23 found in the Fusion Reference Manual.

NOTE: For the Point light's shadows to register in the 3D viewer, set the Rendering Type on the Renderer3D node to Hardware Renderer. Enable Shadows Select the Enable Shadows checkbox whenever the light should cast shadows; it is enabled by default. Shadow Color This standard Color control chooses the shadow's color and defaults to black (0, 0, 0). Density A shadow's density decides how see-through it is: at 1.0 the shadow is fully opaque, and lower settings make it more transparent. Shadow Map Size The Shadow Map Size control sets how large the bitmap underlying the shadow map is, with larger values delivering richer shadow maps at a cost to memory and performance. Shadow Map Proxy Shadow Map Proxy sets the shadow map size used whenever the Proxy or Auto Proxy modes are turned on. Picking 0.5 here, for example, builds a shadow map at half whatever resolution the Shadow Map Size holds. Multiplicative/Additive Bias Since shadows amount to textures placed onto scene objects, Z-fighting sometimes appears, in which the object regions that should receive the shadow draw over the top of it instead. Adding a small depth offset through bias shifts the shadow off the surface it falls on and removes that Z-fighting. With too little bias the objects shadow themselves, and with too much the shadow separates from the surface. Tune the Multiplicative Bias first, then refine the outcome with the Additive Bias control. You will find more on this in the Multiplicative and Additive Bias portion of “3D Compositing Basics,” namely Chapter 85 of the DaVinci Resolve Reference Manual, or Chapter 25 inside the Fusion Reference Manual. Force All Materials Non-Transmissive An RGBAZ shadow map is the default for rendering shadows; enabling this option compels the renderer to fall back on a Z-only shadow map. That can render shadows markedly faster while drawing only a fifth of the memory, though the trade-off is that you lose “stained glass”-type colored shadows. Shadow Map Sampling Governs how finely the shadow map is sampled.

Softness Filtering the shadow map during sampling is what yields soft shadow edges, and Fusion supplies two distinct filtering methods for rendering shadows, each producing a different look. NOTE: With a hard-edged shadow, the shadow map receives no filtering whatsoever. The benefit is that only one pixel of the shadow map has to be sampled, which keeps it fast.

- Constant: Shadow edges hold a steady softness. A constant-width filter samples the shadow map, and the Constant Softness slider sizes that filter; keep in mind that a bigger filter draws out the shadow render time.
- Variable: Shadow-edge softness increases as the receiver moves farther from the caster. That variable softness comes from scaling the filter by the receiver-to-caster distance, and picking it brings up the Softness Falloff, Min Softness, and Max Softness sliders.

Constant Softness This slider surfaces when Softness is set to Constant and lets you dial in the shadow's overall softness. Softness Falloff Shown when Softness is set to variable, this slider drives how rapidly edge softness rises with distance — more precisely, how fast the shadow map filter grows based on the caster-to-receiver separation, with the Min and Max Softness values reining it in. Min Softness Appearing when Softness is Variable, this slider sets the shadow's Minimum Softness: the closer the shadow lies to the casting object, the sharper it remains, down to this slider's limit. Max Softness Likewise shown when Softness is Variable, this slider sets the shadow's Maximum Softness: the farther the shadow sits from the casting object, the softer it turns, up to this slider's limit.

### Common Controls

Transform and Settings Tabs The settings on the Transform and Settings tabs are ones you will meet on the rest of the lighting nodes. For more detail on what these tabs offer, see the “The Common Controls” section at the end of this chapter.

### Spot Light [3SL]

### The Spot Light node

### Spot Light Node Introduction

A spotlight originates from one fixed point and projects a sharply outlined cone whose light tapers off toward the edges. Stage and theatre lighting veterans will spot its resemblance to the practical fixtures used on live shoots. It is the sole light type that can throw shadows. As with a Camera 3D, you route lights into a Merge 3D and see them in the scene by viewing that Merge 3D node; picking a light node on its own and loading it into the viewer displays nothing.

### Inputs

The Spot Light node has a lone optional orange input for a 3D scene or 3D geometry. SceneInput: This optional orange input takes a 3D scene, and when one is connected the node's Transform controls operate on that whole scene.

### Basic Node Setup

The Spot Light node is intended to be one element of a larger 3D scene. Wire the light directly into a Merge 3D, and keeping lights on separate Merge 3D nodes lets you decide which objects each light reaches.

### Spot Light node structure

### Inspector

### Spot Light control

### Controls Tab

The Controls tab handles the hue and brightness of the spotlight, while its position, rotation, and distance live on the Transform tab. Enabled With the Enabled checkbox ticked the spotlight acts on the scene, and clearing it turns the light off. This checkbox matches the red switch sitting to the left of the node’s name in the Inspector. Color This standard Color control sets the light’s color. Intensity This slider governs the spot light's Intensity, where 0.2 amounts to light at 20% percent. Decay Type Out of the box a spotlight uses No Falloff, so its illumination hits geometry at the same strength no matter the distance from light to surface. To make the brightness taper with distance, change the Decay type to either Linear or Quadratic modes. Cone Angle The light's Cone Angle is the width of the cone within which the light shines at full strength. A bigger value widens that cone, up to a ceiling of 90 degrees.

Penumbra Angle The Penumbra Angle marks the zone past the cone angle where the light’s strength tapers toward 0. A larger penumbra angle creates a broader falloff, whereas 0 yields a hard-edged light. Dropoff The Dropoff governs how fast the penumbra angle drops from full intensity down to 0.

### Shadows

The controls in this area let you pin down the shadow map this spotlight draws on when generating shadows. For additional reading, the “3D Compositing Basics” material sits at Chapter 85 of the DaVinci Resolve Reference Manual, or at Chapter 25 in the Fusion Reference Manual.

NOTE: For the Spotlight, either the Hardware or Software Renderer may be chosen as the Rendering Type in the Renderer3D node, and only then do shadows appear in the 3D viewer. Enable Shadows Tick the Enable Shadows checkbox when the light should create shadows; it starts out selected. Shadow Color This standard Color control sets the shadow's hue and defaults to black (0, 0, 0). Density The density of a shadow controls how transparent it is: 1.0 makes a fully solid shadow, and lower figures let more light through. Shadow Map Size The Shadow Map Size control decides how big the bitmap that builds the shadow map is, where higher values give sharper shadow maps but tax memory and performance. Shadow Map Proxy Shadow Map Proxy fixes the shadow map size in play once the Proxy or Auto Proxy modes are switched on. Choose 0.5, say, and you get a shadow map at half whatever resolution the Shadow Map Size carries. Multiplicative/Additive Bias Shadows are in effect textures draped over scene objects, so Z-fighting occasionally surfaces, with the object areas meant to take the shadow rendering on top of it instead. Bias resolves this by introducing a slight depth offset that pushes the shadow away from the surface it shadows, ending the Z-fighting. Too little bias lets objects shadow themselves; too much pulls the shadow off the surface. Dial in the Multiplicative Bias first, then refine using the Additive Bias control.

More on this appears in the Multiplicative and Additive Bias portion of “3D Compositing Basics,” which is Chapter 85 of the DaVinci Resolve Reference Manual, or Chapter 25 over in the Fusion Reference Manual. Force All Materials Non-Transmissive An RGBAZ shadow map is normally what renders the shadows; turn this option on and you force the renderer onto a Z-only shadow map. That option can speed shadow rendering up sharply while using just a fifth of the memory, but you give up the ability to cast “stained glass”-like shadows. Shadow Map Sampling Determines how finely the shadow map gets sampled. Softness Soft shadow edges come from filtering the shadow map as it is sampled, and Fusion gives you two separate filtering methods for rendering shadows, each with its own effect. NOTE: A hard-edged shadow involves no filtering of the shadow map at all. Its advantage is that just one pixel of the shadow map needs sampling, so it stays fast.

- Constant: Shadow edges keep a single, even softness. A fixed-width filter samples the shadow map, with the Constant Softness slider setting that filter's size; remember that enlarging the filter stretches out the shadow render time.
- Variable: Shadow-edge softness builds the further the receiver lies from the caster. This variable softness is produced by adjusting the filter size according to the receiver-caster distance, and selecting it makes the Softness Falloff, Min Softness, and Max Softness sliders appear.

Constant Softness This slider appears when Softness is set to Constant, and you use it to set the shadow's overall softness. Softness Falloff Present when Softness is set to variable, this slider controls how quickly edge softness builds with distance — specifically, how fast the shadow map filter expands based on the caster-to-receiver distance, kept in check by the Min and Max Softness values. Min Softness Shown when Softness is Variable, this slider sets the shadow's Minimum Softness: the nearer the shadow sits to its casting object, the crisper it is, down to this slider's limit. Max Softness Likewise shown when Softness is Variable, this slider sets the shadow's Maximum Softness: the further the shadow sits from its casting object, the softer it becomes, up to this slider's limit.

### Common Controls
