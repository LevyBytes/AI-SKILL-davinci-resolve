# Fusion (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Inside: Scales the image evenly so its longest side just fits within the cone. Put differently, the picture grows as large as it can while still staying entirely inside the light's pyramid. Because of this, no area beyond that pyramid will ever pick up any of the projected light.
- Width: Scales the image evenly so its width sits within the cone. Keep in mind the picture may still spill past the cone along its height.
- Height: Scales the image evenly so its height sits within the cone. Keep in mind the picture may still spill past the cone along its width.
- Outside: Scales the image evenly so its shortest side fits within the cone. Put another way, the picture shrinks as much as it can while still ensuring it blankets the whole pyramid (that is, the pyramid sits fully within the image). As a result, every pixel of any object inside the light's pyramid is always lit.
- Stretch: Scales the image unevenly so that it precisely fills the projector's cone.

### Projection Mode

- Light: Casts the texture in the manner of a diffuse/specular light.
- Texture: Paired with the uCatcher node, this option enables texture projections you can re-light. Only surfaces whose material shaders include the catcher material are hit by the projection. A handy approach is wiring a uCatcher node into the Specular Texture input of a USD Material node (a Blinn, for instance). Then every object carrying that Blinn material picks up the projection within its specular highlight. You can apply this same idea to any material input that accepts texture maps, including the Specular and Reflection maps.

Shadows Because the projector derives from a spotlight, it can likewise cast shadows by means of shadow maps. The settings within this reveal govern the dimensions and characteristics of that shadow map.

- Enable Shadows: Turn on the Enable Shadows checkbox when the light should generate shadows. Its default state is selected.
- Shadow Color: This ordinary Color control sets the shadow's color. It defaults to black (0, 0, 0).
- Density: The Shadow Density governs how transparent the shadow appears. At a density of 1.0 the shadow becomes fully transparent, while smaller numbers reduce its opacity.
- Softness: Governs how soft the shadow's edges are.
- Softness Quality: Governs the quality level of that softness.
- Shadow Map Size: The Shadow Map Size control sets the dimensions of the bitmap used to build

the shadow map. Bigger numbers yield finer shadow maps but cost additional memory and performance.

- Shadow Map Bias: When shadows fail to appear, this control can be tuned so the shadow map shows up in the scene.
- Shadow Map Offset: Shifts the value of the Shadow Map Size.

### Common Controls

Transform and Settings Tabs The Transform and Settings tabs that remain are shared by many USD nodes. You will find their descriptions in the “The Common Controls” section that closes this chapter.

### uCatcher [uCa]

The uCatcher node uCatcher Node Overview The job of the uCatcher material is to “catch” texture-mode projections thrown by uProjector and uCamera nodes. Those captured projections become a texture map, which the uCatcher material then lays onto whatever geometry it is wired to. Grasping the uCatcher node is easier once you see how light-based and texture-based projections differ. Picking Light in the projection mode menu of a uProjector or uCamera node merely adds the RGB channel values from the projected picture onto the diffuse texture of whatever geometry falls inside the projection cone. That makes it impossible to trim away geometry using an image's Alpha channel under light mode projections. Picture a case where you want to throw an image of a building onto an image plane for a set extension shot. You begin by rotoscoping the picture to cut out the windows. Doing so lets you reveal the geometry of the rooms behind the wall in the finished composite. Once that image is cast as light, its Alpha channel goes unused, leaving the masked windows opaque. If instead you wire the uCatcher into the diffuse texture map of the material on the image plane, and then flip the projection mode menu on the uProjector or uCamera node from Light to Texture mode, the image gets laid down as a texture map. Following this method for the example above, the windows turn transparent and the geometry behind them becomes visible. The chief benefits of this route over light projection are that the uCatcher can throw Alpha onto an object and needs no lighting turned on. Another plus is that the uCatcher is not confined to a material's diffuse input, letting you cast specular intensity maps, or even maps for reflection and refraction. NOTE: The uCatcher material needs a uProjector or uCamera node present in the scene, configured to cast an image in Texture mode onto the object the uCatcher is wired to. With no projection present, or a projection not set to Texture mode, the uCatcher merely renders the object transparent and invisible.

### Inputs

USD geometry feeds the yellow Scene input — for instance a uShape, or a USD asset routed in via a uLoader.

### Basic Node Setup

What feeds the uCatcher node is the geometry of the USD asset meant to receive the projected texture. From there the uCatcher node sends its output to a uMerge where additional assets, lights, or cameras may be composited.

A uCatcher node draws its input from the geometry node (uShape1) that receives the texture projection, and then feeds a uMerge node. Inspector

uCatcher controls Controls Tab The Options under the Controls tab decide how the uCatcher manages stacking up several projections. Color Mode The Color mode menu governs the way the uCatcher blends light coming from multiple projectors. With a single projector present, it changes nothing. Alpha Mode The Alpha mode governs the way the uCatcher blends the Alpha channels coming from multiple projectors. With a single projector present, it changes nothing.

Threshold The Threshold lets you keep certain low values out of the accumulation math. As an example, in Median Accumulation mode a threshold of 0.01 would leave out any pixel whose value is under 0.01 from the median computation. Restrict by Projector ID Once enabled, the uCatcher takes in light solely from projectors whose ID matches. Projectors carrying a different ID get skipped.

### Common Controls

Transform and Settings Tabs The Transform and Settings tab in the Inspector also appears again across other USD nodes. You will find these common controls explained fully at the close of this chapter under “The Common Controls” section.

### Fusion Global in-out controls for USD Loader

Bringing a USD file into stand alone Fusion now offers a way to define a global in-out range.

### 3D Renderer now Supports Creating and Using Cryptomatte

When working with the Renderer3D’s hardware renderer, Cryptomatte layers and metadata can now be produced for objects as well as materials. This added capability lets you build several soft mattes targeting particular 3D objects or materials drawn from a rendered scene. Fusion’s Cryptomatte tool can read the new layers, natively pulling in the embedded mattes and making it easier to isolate rendered pieces for compositing. You can also store them in an OpenEXR file to use later.

### Relief Map Tools

The Relief Map tools are new to Fusion and can boost the realism of a 3D object. What sets Relief mapping apart from ordinary bump maps is that it can produce self-occlusion. This pair of additions, CreateReliefMap and ReliefMap, exist to assist in building detailed surface textures. CreateReliefMap is a fresh filter tool that produces the image the ReliefMap node requires. That generated depth map drives the creation of simulated texture and lighting effects. CreateReliefMap offers controls for depth scale and smoothing so you can dial how pronounced or gentle the relief looks. ReliefMap is a fresh 3D tool that adds height-driven surface detail onto 3D shapes. Working from an image, the ReliefMap carves away parts of a 3D shape, in effect building depth information for the surface. This sculpting approach modifies a material’s normal/displacement mapping directly, allowing rich textures to emerge without hand-modeling every detail. Detailed coverage of both tools follows below.

### CreateReliefMap [CRM]

### The CreateReliefMap node

### CreateReliefMap Node Introduction

Create Relief Map is a partner tool that produces the image the ReliefMap node needs. It builds a relief map by taking a height field and computing values that reshape the object’s surface normals. Once fed into a Relief Map, it yields simulated texture and lighting effects. CreateReliefMap offers controls for depth scale and smoothing so you can dial how pronounced or gentle the relief appears.

### Inputs

The lone yellow input takes a 2D image.

### Basic Node Setup

Here, a chain of shape nodes feeds the input of the CreateReliefMap node. That node’s output would next be routed into a ReliefMap node to set the depth of the 3D surface.

A 2D shape arrives from the sRender node into the CreateReliefMap node.

As an example, a plain Arrow Shape is built and routed into the CreateReliefMap node.

Once you have tweaked the CreateReliefMap node, you would then wire its output into a ReliefMap node.

You would then tweak settings in the ReliefMap Node to actually lay the shape onto the connected 3D image.

### The source shape fed into the CreateReliefMap node

What the CreateReliefMap produces here is the output you would then route into the ReliefMap node

The output the ReliefMap node yields once applied onto a 3D shape

### Inspector

### CreateReliefMap controls

### Controls Tab

Map Type There are 3 choices on offer: Relief, Relaxed Cone and Cone. Each of the three relies on a mix of RGB and Alpha to build the relief map. Relaxed Cone and Cone can give more accurate output at the cost of performance. Depth Source Pick from the dropdown menu which source supplies the depth data for the relief map. Depth Scale Raising the slider’s value deepens the relief map. Texture Depth Choices to keep or alter the bit depth of the relief map. Pre Blur Move the slider to apply more pre blur onto the source image ahead of building the Relief Map. Flip Depth Ticking this box reverses the depth mapping.

The same shape above, with the Flip Depth checkbox selected.

### Common Controls

Transform and Settings Tabs The Transform and Settings tabs that remain are shared by many nodes. You will find their descriptions in the “The Common Controls” section that closes this chapter.

### ReliefMap [3RM]

### The ReliefMap node

### ReliefMap Node Introduction

Relief Map is a 3D tool that adds height-driven surface detail onto 3D shapes. Drawing on an image routed through its partner Create Relief Map node, the Relief Map carves away parts of a 3D shape, in effect building depth information for the surface. This sculpting approach modifies a material’s normal/displacement mapping directly, allowing rich textures to emerge without the need to hand-model every detail. What distinguishes Relief mapping from bump maps is that Relief can occlude itself, producing natural lighting interactions. The Relief Map’s RGB channels hold normals values while the alpha carries the height/depth.

### Inputs

Background Input: A material connection feeds the yellow input — for example Blinn, Ward, CookTorrance or Phong. Relief Map Input: Into the white input you wire a 2D image, routed through the Create Relief Map node, that will serve as the Relief Map texture.

### Basic Node Setup

Here, a Text+ node runs through a Create Relief Map node to build the data the Relief Map needs before it is laid onto a Shape3D. For the Relief Map, the produced map goes into the white input while a material goes into the yellow input. The Relief Map’s output is wired to 3D geometry (Shape3D) and merged into a 3D scene.

The ReliefMap node merging data from both a Relief Map and a Blinn node before sending the completed relief data on to apply to a Shape3D node.

### Inspector

### ReliefMap controls

### Controls Tab

Depth Scale This slider lets you stretch or compress the relief map’s total depth. Pushing the depth scale up boosts the overall span of depth. Lock U/V With this on, the U/V channels scale together uniformly. With it off, each channel’s frequency can be tuned on its own. Map Type Two methods exist for applying a relief map, Relief and Cone. Both draw on RGBA values to build data, though Cone delivers higher quality and quicker shading at a performance cost. Quality Raising the quality slider’s value sharpens the result. The effect is most visible with the Relief map type.

### Common Controls

Transform and Settings Tabs The Transform and Settings tabs that remain are shared by many nodes. You will find their descriptions in the “The Common Controls” section that closes this chapter.

### Multi-Inspector

The Multi-Inspector is a strong new addition in Fusion v21 letting users tweak shared properties across several selected tools at the same time. It smooths out workflows by removing the need to set identical parameters on every tool one by one. With several tools chosen in the Flow, the Multi-Inspector shows controls shared among them all. Users then adjust these common parameters, and the edits land at once on every selected tool.

### Changing Common Inspector Properties

The Combine Selected Tools icon in the Inspector header With several tools selected, a fresh toggle icon in the Inspector header now lets them merge into one set, displaying only the controls every selected tool has in common. Dragging one such control, or entering a fresh value, adjusts all the selected tools together. This can speed up plenty of routine workflows, letting you tweak many different tools at once without needing full instancing or copy & paste.

Two uTransform nodes merged let you set parameters for both tools at once. When the chosen controls hold differing values across tools, the control knobs and values are hidden. Dragging on the value edit field adds or removes an offset from each tool’s control on its own, keeping the differences rather than forcing them to match. Size and Scale controls instead apply a scaling factor, holding the ratio between each tool. On top of that, holding the Opt/Alt key while dragging toggles between offset and scale mode, giving you even finer control.

### The Set Values To context menu

Once several controls are merged, the control’s context menu picks up a fresh batch of Set Values To options, namely First, Middle, Minimum, Maximum, Spread, and Jitter. These operate across the span of values among the selected controls, and can pin them all to one point in the range, spread them evenly over that range, or sprinkle a bit of randomness onto each value.

### Multilayer Support for Stereoscopic 3D Clips and Deep Images

Within Fusion 21, multilayer now extends to Steresocopic 3D and Deep Images.

### Color Correction for Deep Images in Fusion

A new Deep Color Corrector tool is available for color grading deep images. Detailed coverage of the tool follows below.

### dColorCorrector [dCC]

The dColorCorrector node dColor Corrector Node Introduction Serving as a full-featured color node for Deep images, the dColor Corrector node delivers histogram matching and equalization, hue shifting, tinting, and color suppression. The dColor Corrector node’s controls fall into four tabs: Correction, Ranges, Options, and Settings.

### Inputs

Within the Node Editor the dColor Corrector node carries two inputs. Input: The sole required hookup is this yellow input. It feeds in a Deep image for color correction. Effect Mask: The optional blue input takes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Wiring a mask here confines the color corrector’s adjustment to only the pixels inside the mask. An effect mask is applied to the tool once the tool has been processed.

### Basic Node Setup

The dColor Corrector node, as with many Deep image-processing nodes, takes in a Deep image such as one from a Loader node or the MediaIn1 pictured below. Its output continues the node tree by feeding either a Merge node or one more Deep image-processing node. Here a dColor Corrector node sits on a MediaIn1 node that holds an EXR Deep image file. Inspector

dColor Corrector controls

### Correction Tab Colors Menu

The primary Correction tab is divided further into four kinds of correction methods: colors, levels, histogram, and suppress. Choosing one from the menu atop the Correction tab brings up that method’s controls. Detailed coverage of the Color method follows below. Range This menu picks the tonal range that the color correction controls on this tab affect. You can set the menu to Shadows, Midtones, Highlights, and Master, with Master as the default that affects the whole image. The chosen range carries across the Colors, Levels, and Suppress sections of the dColor Corrector node. Changes applied to the image in the Master channel land after any edits made to the Highlight, Midtone, and Shadow ranges. NOTE: Each color range has its own independent controls. As an example, tweaking the Gamma control while in Shadows mode neither changes nor affects the Gamma control’s value for the Highlights mode. Every control stands alone and is applied on its own. Color Wheel The color wheel gives a visual sense of the changes made to Hue and Saturation, plus any tint laid on the image. You can adjust directly by dragging the color indicator, or by keying values into the numeric boxes beneath the color wheel. The tint shows up in the color wheel’s color indicator, which conveys the tint’s color and strength. The Highlight setting draws its color indicator with a black outline. The Midtones and Shadows rely on gray color indicators. The Master color indicator is black as well, yet carries a white M at its center to set it apart from the rest. The mouse can place the color indicator for a given range only while that range is selected. As an example, the Highlight color indicator will not move while the Master range is selected. Holding the Command or Ctrl key as you drag this indicator lets you fine-tune by lowering the control’s sensitivity to mouse motion. Holding the Shift key confines the color indicator’s movement to one axis, letting you limit the effect to either tint or strength. Tint Mode This menu picks the speed and quality of the algorithm that applies the hue and saturation changes. Better is the default, but for bigger images a faster method may be preferable. Hue This slider duplicates the Hue control sitting beneath the color wheel. The slider makes nudging the value by mouse easier. The Hue control offers a way to rotate the hue of the image (or chosen color range) around the color spectrum. Its effective span runs from -1.0 to 1.0, standing for the angle of rotation turning clockwise. A value of 0.25 equals 90 degrees (90/360) and would shift red toward blue, green toward red, and so forth.

Shifting the hue can be done by dragging the slider, typing a value straight into the text control, or by hovering the mouse over the color wheel’s outer ring and dragging up or down. The outer ring always displays the shifted colors next to the original colors shown at the wheel’s center. Saturation This slider duplicates the Saturation control sitting beneath the color wheel. The slider makes nudging the value by mouse easier. The Saturation control governs how intense the color values are. A saturation of 0 yields gray pixels with no color component, while a value of 1.0 leaves the input image’s chroma component unchanged. Larger values produce oversaturated output with a heavy color component. You can set saturation values by dragging the slider, typing a value straight into the text control, or by sweeping the mouse sideways along the color wheel control's outer ring. Channel This menu serves the Histogram, Color, and Levels sections of the dColor Corrector node. Selecting the red channel makes the controls in each mode affect only the red channel, and so on. Because the controls are independent, switching to blue neither removes nor wipes out any edits made to red, green, or Master. The animation and edits for each channel stay separate. This menu only decides which controls appear. Contrast Contrast is the spread of difference between the light and dark regions. Raising this slider’s value increases contrast, driving color from the midrange out toward black and white. Lowering the contrast pulls the image’s colors toward midrange, narrowing the gap between the darkest and brightest pixels. Gain The Gain slider multiplies the pixel value. A gain of 1.2 turns a pixel that is R0.5 G0.5 B0.4 into R0.6 G0.6, B0.48 (i.e., 0.4 \* 1.2 = 0.48), while leaving black pixels completely untouched. Gain works on higher values more than lower ones, so its effect is strongest across the midrange and upper range of the image. Lift Whereas Gain scales color values about black, Lift scales them about white. The pixel values get multiplied by this control’s value. A Lift of 0.5 turns a pixel that is R0.0 G0.0 B0.0 into R0.5 G0.5, B0.5, while leaving white pixels completely untouched. Lift works on lower values more than higher ones, so its effect is strongest across the midrange and lower range of the image. Gamma Values above 1.0 raise the Gamma (mid gray), while lower ones lower it. This node’s effect is not linear, and any existing black or white points stay entirely unaffected. Pure gray colors take the largest effect. Brightness The Brightness slider’s value is added onto each pixel’s value in your image. This control acts linearly on an image, so it lands identically on every pixel no matter the value. Reset All Color Changes Pressing this button restores every color control in this section to its default value.

### Correction Tab Levels Menu

The primary Correction tab is divided further into four kinds of correction methods: colors, levels, histogram, and suppress. With Levels chosen from the menu, you can reposition an image’s white and black points, plus a Gamma control to tune midtones. A histogram offers a look at the image’s tonal spread to help steer your edits. Detailed coverage of the Level method follows below.

dColor Corrector Levels controls Range Just like the Range menu when Color is chosen in the Menu, the Range menu picks the tonal range that the color correction controls on this tab affect. You can set the menu to Shadows, Midtones, Highlights, and Master, with Master as the default that affects the whole image. The chosen range carries across the Colors, Levels, and Suppress sections of the dColor Corrector node. Changes applied to the image in the Master channel land after any edits made to the Highlights, Midtones, and Shadows ranges. NOTE: Each color range has its own independent controls. As an example, tweaking the Gamma control while in Shadows mode neither changes nor affects the Gamma control’s value for the Highlights mode. Every control stands alone and is applied on its own. Channel This menu picks and shows the histogram for each color channel or for the Master channel.
