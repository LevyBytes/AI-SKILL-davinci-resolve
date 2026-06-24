# Fusion (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Fusion

### Krokodove Toolset Integrated into Fusion and Edit Effects

The well-liked third-party Krokodove Fusion tools now ship built straight into DaVinci Resolve and Fusion, adding well over a hundred fresh motion graphics effects and tools. What follows is a short rundown of the toolset:

### 3D Mapped Duplicate 3D

Builds a 3D grid of cloned objects spanning X, Y and Z space. Imagery can drive the offset, rotation, scale, and timing of those objects.

Image Tools Bounding Box Color Map Connect Dither Extend Fragments Grow Grow Color Microwaves Pack Painterly

Paints a rectangle out of a chosen channel, its dimensions governed by the Threshold controls. Maps a texture onto one or several flat colors, which you either pick by hand or have detected for you. Connect lays an unbroken line between separate points, each of which you can place on its own to form ‘way-points’ along that line. Dither is a filter that seeds a noise pattern to suggest shading; its various methods can yield a crisp, crunchy texture. Extend copies edge pixels along a horizontal or vertical axis for a repeating-pixel effect. Fragments slices an image into discrete pieces you can then fade in or out through the Range options. Grow lets an image expand or vanish outward from one or more seed locators. Grow Color pushes the color at an image’s edge outward, packing transparent regions by stretching those edges. Microwaves throws radiating highlights out from a center point, mimicking light beams and adding controls to reshape the whole form. Pack assembles patterns of stacked shapes inside a nominated color channel. Painterly is a filter effect that lays a stylized ‘artwork’ finish over an image or graphic.

### Image Tools Rasterize

### Time Mapper Worm

### Image Color Tools Invert Match Color

### Recolor Replace Color Threshold

### Image Create Tools Blobs Generate Lines Pattern Shapes

### Image Pixel Tools Average Bevel Channel Shifter

Rasterize is a filter effect that takes an image and recasts it as a run of shapes — dots, squares or diamonds — handy for producing a half-tone look. Time Mapper blends different moments of a sequence under the direction of an external image map. Worm assembles a mix of straight and curved lines from points you specify. Invert flips the color, luminance or hue. Reach for Match Color to grab a tonal band — shadows, midtones, or highlights — and swap it out for a color. Recolor hands you controls for substituting colors: nominate one or more source colors and replace those picks with new ones via the color swatch. Alternatively, nominate a single source color and trade it for a correction. Threshold isolates a tight, specific span of color or brightness within a nominated channel, with its controls letting you tune the selection’s tolerance. Blobs scatters circular shapes at the points you specify. Generate is a tool for adding texture to a source input; producing a greyscale image, it lays down what looks like a randomized noise pattern. The Lines tool forms patterns from one or several line sets and spawns multiple tiers of repeating lines. Pattern lays out an array of tessellated shapes for a full-frame design. The Shapes tool stacks several tiers of concentric shapes, squares and circles included. This tool averages a run of consecutive frames in a sequence for a frame-blending effect. The Bevel tool draws an inner bevel around an image to imply depth. Channel Shifter splits the RGBA channels apart and supplies controls to offset, blur, or scale them.

Image Pixel Tools Clean Edges Deflicker Duplicate Extrude Noise Plastic Positioner Push Rest Seamless Seamless Loop Sort Image Position Tools Contour Image Vector Tools Vector Visualisation Image Warp Tools Bend Directional Scale Kaleidoscope Mirror

Strips off frame-edge pixels, either by duplicating them or filling with a solid color. Frame border. Deflicker irons out flickering — local or across the whole frame — over consecutive frames. Repeats the incoming image along a chosen pattern or shape. The Extrude tool warps an image’s edge to fake a sense of depth. The Noise tool lays down a pixellated pattern whose colors are either randomly generated or hand-picked. Plastic is a filter tool that produces a synthetic bevel effect, draping a plastic film or sheen across the source image. Positioner is a corner-pinning tool offering source and destination controls. Push yields a ‘slide’ effect: hook up a second image and one slides into the other. Rest nudges pixels so they settle onto a single line, bending an image’s upper or lower portion along a path you set. Seamless mirrors the opposite edge and blends it with the original. Seamless Loop hands you controls to retime a comp into an unbroken looping sequence. Sorts pixels by color value. The Contour tool traces an outline around an image, spawning repeating lines across a gradient. Produces an overlay that shows motion-vector direction and velocity. Bend is a radial warp tool that flexes an image with a three-point spline. Directional Scale is a one-sided scaling tool that stretches an image at a chosen angle. Kaleidoscope is a classic filter tool that radially mirrors the image for a kaleidoscopic result. Reflects the image about an arbitrary axis, flipping it along a line you specify.

### Image Warp Tools Offset Radial

### Relative Transform

Listed here are Segment, Transform, Shear, Shuffle, Spherize, and Stretch; then the Modifiers — Beat, Color Switcher, and Random; and the Text Modifiers — Formula From File, Juggle, and Write.

Offset slides image pixels under the control of another image, shoving the image along the horizontal or vertical axis. Drives pixels radially outward or inward rather than scaling them, yielding a dent-like distortion. Draws on a second input to warp or distort via position, rotation, and scale controls. Its transformation pivot is read off the incoming image and can be placed relative to the actual pixel data. Splits the frame into square segments, each one taking its own angle and scale distortion. The Shear tool imposes an angular shear, with the extra input governing how strong that shear is; the subdivided frame is then shifted around inside the image. Spherize is a radial and cylindrical deformation tool that bends a round-style warp into a chosen region. The Stretch tool elongates an image along any preset axis, stretching pixels along a line you specify. The Beat modifier supplies controls to animate in Frames per Beat or Beats per Minute, alongside Start and End time, Attack, Decay, Sustain, and Release. Faced with several color palettes, this modifier makes hopping between them — or rotating colors inside one palette — straightforward; setting it up means wiring individual channels (RGBA) to the separate outputs. (A script here would be handy). The Random modifier bolts a random-value generator onto any control, letting you bound the Min and Max range of values to randomize, plus controls that spread new random values across a frame range for a smooth glide from one value to the next over time. Custom tool acting as a modifier. A modifier that lets the user pull in a txt-format file or type entries by hand, with controls to reveal text one line at a time for a fixed or custom span. A modifier that shuffles characters at random. A Write On-style modifier offering to append a cursor or caret at the text’s tail, as though it were being keyed in from a device; it can also tack on a Prefix that stays permanently visible, IE untouched by the write-on effect.

### Improved Macro Editor

DaVinci Resolve 21 sharpens the Fusion macro editor considerably, making it more intuitive and showing a live preview in the inspector of how your macro will look while you assemble it. That preview lets you put together even the trickiest macros with faster iteration feedback and greater clarity. Certain effects don’t come from a single tool but from a whole chain of operations, occasionally across tangled branches whose parameter controls interlink. Fusion offers plenty of individual effects nodes to work with, yet also lets you repackage them in varied combinations as self-contained “bundles” — either macros or groups. Such “bundles” bring a few benefits:

- They cut down on visual clutter throughout your node tree.
- They safeguard sound user interaction by letting you limit which controls from each node of

the macro are available to the user.

- They lift productivity by letting artists rapidly reuse ready-made answers to common compositing

challenges and creative adjustments that have already been built and saved.

### Using the Macro Editor

Every macro begins from the individual tools sitting in the node editor. Pick out the tool or tools there that you want a macro built from, then right click one of them and choose Macro > Create Macro off the context menu. Up comes the Macro Editor.

### The Fusion Macro Editor

Three principal areas make up the Macro Editor:

### Enter a name for your macro

Up top sits the Macro Name field, where you title your macro for the tool list; right-clicking the magic wand icon lets you pick an image to serve as the new macro’s thumbnail icon.

### The Macro Edior

Over on the left lives the macro editor proper. It lays out, in column view, every parameter belonging to each tool you picked. A checkbox in the Export Column accompanies every parameter; ticking it folds that parameter into your macro, while clearing it leaves the parameter out. The Macro Editor Columns:

- Tool/Input: Fusion’s internal name for the parameter, or the Input connection.
- Export: Tick this box to include the parameter in your macro; clear it to leave the parameter out.
- Name: A text field for naming or renaming how this parameter’s title reads in the macro.
- Type: The kind of data this parameter is set up to accept.
- Default: A field where you preset the parameter’s default value.
- Minimum: A field for setting the parameter’s lowest permitted value.
- Maximum: A field for setting the parameter’s highest permitted value.

### Enter a name for your macro

On the right sits the live Inspector Preview, mirroring how your macro will appear as you assemble it. That visualization earns its keep, letting you add, remove, or edit controls while the macro takes shape. Doubling as an interactive space, the live preview lets you drag and drop controls within it to reshuffle their order. A parameter can be dragged up or down the list, or even moved to a different page. You may also add a fresh page of parameters or rename one that exists. The layout buttons at the Macro Editor’s lower left fine-tune your macro’s appearance further: Add Separator: Drops a separator line into the macro to divide unrelated controls; clear its export box to remove it. Add Spacer: Drops a blank gap into the macro to divide unrelated controls; clear its export box to remove it. Add Nest: Drops a nested disclosure list into the macro. Place the nest, then drag in the parameters you want kept out of sight until the disclosure icon is clicked. Its starting open or closed state comes from the Default column (1 for open, 0 for closed); clear its export box to remove it. While assembling your macro, testing it live within the node editor — without saving and re-importing each round — is handy. From the Macro Editor’s three-dot option menu, choose Copy Macro mid-build, then paste your work in progress straight into the node editor to watch how it truly behaves in Fusion.

After your Macro is complete, the option menu offers several ways to commit it back into Fusion.

### Macro Editor Option Menu

The Macro Editor’s Option Menu:

- Open: Pulls an existing macro into the Macro Editor.
- Save: Commits the work currently in progress.
- Save As Macro: Stores the active macro (one node carrying custom parameters).
- Save As Group: Stores the active macro as a group (a shell of separate nodes you can expand again later).
- Save to Edit Template: Stores the macro as an edit template that surfaces in the effects list on the Cut or Edit pages. Your choices span Title, Generator, Effect, or Transition templates.
- Choose Thumbnail: Lets you load an image to stand in as the macro’s thumbnail picture.
- Show in Folder: Reveals the file location holding your saved macro.
- Copy Macro: Grabs the macro’s present state so you can paste it into the node tree for testing.

### Fusion Animation can be Creatively Driven by Fairlight Audio

Fusion tools now carry a fresh Fairlight Animator modifier. This potent addition wires Fusion into Fairlight’s audio engine so animation can run automatically off audio analysis. Drawing audio from timeline clips or media pool sources, the Fairlight Animator reads audio levels and pipes them into any numerical control. Reach the tool by right-clicking a fusion parameter and picking Modify With > Fairlight Animator from the context menu.

### Choosing the Fairlight Animator modifier

Its controls come into view once you click the Modifiers tab over in the inspector.

### The Fairlight Animator controls

### Support for OGraf HTML Graphics and Lottie Animations

On macOS and Windows, DaVinci Resolve 21 introduces support for OGraf (.json) and Lottie (.lottie) HTML-based animation. Whether you sourced the animation online or built it yourself, it now drops straight onto your timeline. Just export your .json or .lottie file and drag-and-drop it into your Media Pool the way you would any other media. It also goes right into the timeline, where Resolve recognizes it and handles it as a fully rendered animation clip. Because the alpha background is recognized too, transparency carries through. Lay the clip over another layer and it composites cleanly, which makes it a natural fit for a stinger or transition. Beyond that, Fusion gains a new node named OGrafLoader, a convenient way to pull your OGraf or Lottie files straight into your composition.

### Text+ and MultiText Support Spell Checking

As a welcome quality-of-life touch for the spelling-challenged, DaVinci Resolve 21 bundles a multi-language text spell checker covering Text+ and MultiText inside Fusion. Misspellings get flagged in red across both the viewer and the inspector. Right click a word to peek at suggested fixes or to skip it.

### Font Improvements Including Color Fonts and Emojis

Both Text+ and MultiText now accept emoji, so you can drop expressive icons and visual accents right into your text for livelier, more engaging designs. Insert emoji straight into the text fields with Control-Command-Space on macOS and Windows key-. (period) on Windows. On top of that, Text+ and MultiText carry sturdier font handling, with better treatment of color fonts, bitmap fonts, and font styles. When a color font is supported, the Text+ inspector surfaces extra Color Palettes controls beneath Advanced Controls, where the font’s display options are chosen. Some emoji fonts — Noto Color Emoji among them — hold only emoji glyphs and no letters, so typing Latin characters in such a font leaves nothing in the text. Type emoji while a regular font is active and Fusion spots it, switching to an emoji font on its own; the reverse swap, however, doesn’t happen. A Fusion preference settles which emoji font gets used.

### Improved MultiText for Position, Pivot, Alignment and CSV Import

Fusion’s MultiText gains refinements to its position and alignment controls and to CSV import, plus new pivot adjustments on the Layout tab.

### Support for USD SDK 25.11 with Hydra 2.0 API for Storm Renderer

Fusion now runs on USD SDK 25.11 with the Hydra 2.0 API behind the Storm renderer. The upgrade delivers a better Fusion USD environment plus a welcome uRenderer addition named Neye. That new AOV yields camera-relative normals, opening up still more flexibility in your workflow.

### USD Support for 3D Matte Objects and Textures

Our USD geometry tools pick up fresh “Is Matte” controls for added creative latitude. Baked straight into the USD geometry tools, these controls also turn up in the uReplaceMaterial tool. Behaving much like Fusion 3D tools, the Is Matte feature lets you hide background objects or carve tidy alpha channel cutouts by punching holes wherever they’re needed.

### USD Projector and USD Catcher Tools

Say hello to the new USD Projector and uCatcher tools. Through the uProjector node you project images straight onto USD geometry, throwing imagery across any objects in your USD scene and reshaping how those USD objects appear in an instant. Partnered with the uProjector, the uCatcher tool grabs the texture-mode projections and turns them into textures that drop cleanly onto your connected geometry. In concert, these tools unlock creative avenues for dynamic texture mapping across your USD workflows. The uCamera tool gains projection too; wire an image into the new Image Input and additional tabs surface. Just as with Camera 3D, those tabs carry Image and Material as well, handily affording a camera-matched image plane. Fuller descriptions of these tools sit below.

### uProjector [uPj]

The uProjector node uProjector Node Introduction An image gets thrown onto USD geometry by the uProjector node. It serves plenty of ends: layering texture onto objects, spreading one texture over several separate objects, casting background plates from the camera’s vantage point, image-based rendering techniques, and beyond. The uProjector node is only one of a handful of nodes able to project images and textures, and each approach has its trade-offs. You can let projected textures “slide“ over an object as that object shifts relative to the uProjector, or instead bundle the pair into a uMerge so they move together and the texture stays pinned to the object. Grasping the uProjector node’s strengths and limits comes easiest when you treat the uProjector as a spin on the uDisk node.

- Lighting has to be switched on before any projection result shows up.
- Whatever light the projector emits counts as diffuse/specular light, which means it is

affected by the surface normals and can cause specular highlights.

- Switching Shadows on makes uProjector throw shadows.
- A uProjector’s projected light reaches every object sitting downstream of the uProjector

in the USD node tree.

- Within Light mode, the projected image’s Alpha values won’t clip geometry. Lean on Texture

mode instead.

- Should two projections overlap, their light contributions sum together.

For re-lightable textures, or textures bound for non-diffuse color channels (Specular Intensity or Bump, say), switch to the Texture projection mode instead:

- A Texture-mode projection lands only on objects whose material — in whole or in part — draws on the uCatcher node’s

output applied to that object.

- Such projections clip the geometry by the Alpha channel of the

projected image. The uCatcher node’s section holds further detail.

uCamera Projection vs. uProjection Node The uCamera node carries a projection feature of its own, and it’s the right pick when the projection should align to a camera, since this node grants finer command over aperture, film back, and clip planes. The uProjector node, by contrast, was built to serve as a custom light in USD scenes for layering and texturing, offering tighter control over light intensity, color, decay, and shadows.

### Inputs

Two inputs sit on the uProjector: one for the scene you’re projecting onto and one for the projected image. SceneInput: The orange scene input takes a USD scene. With a scene wired in here, any transformations placed on the spotlight ripple through the rest of the scene as well. ProjectiveImage: The white input looks for a 2D image to drive the projection, and this connection is mandatory.

### Basic Node Setup

By way of illustration, the uProjector node beneath casts a light (Background1) onto USD primitives. Every set element feeds into a uMerge, which pushes the projected set out into a larger scene holding camera, lights, and further elements. Routing the uProjector node into either uMerge node yields the same outcome. uProjector texturing groups of shapes to construct a set Inspector

uProjector controls

### Controls Tab

Color Ahead of being cast into the scene, the input image is multiplied by this color. Intensity This slider dials the projection’s Intensity whenever the Light and Ambient Light projection modes are active. Under Texture mode, the same option scales the texture’s Color values once they’ve been multiplied by the color. Exposure This alters how much light falls across a scene, much in the spirit of Intensity. Color Temperature/Enable This fixes a light source’s color temperature, defaulting to 6500K — daylight temperature. Diffuse Response This governs how much the light adds to a material’s Diffuse color. Specular Response This governs how much the light adds to a material’s Specular color. Decay Type By default a uProjector uses Quadratic Decay, so intensity tapers off with Distance. Linear decay reads similarly, whereas No Decay holds the light at one intensity everywhere in the scene. Decay Rate This is how fast the projected light fades across distance; a smaller decay rate makes the projection stronger. Shaping Focus Tweaking this draws the projection inward from its edges toward the centre. Shaping Cone Angle The Shaping Cone Angle is the width of the cone over which the projector pours out its full intensity; a bigger angle means a wider cone, capped at 180 degrees. Normalize Intensity Tick this checkbox and the projection’s Width and Height snap to default values. Clear it to expose separate Width and Height figures you can tune by hand. Fit Method The Fit Method decides how the projection seats inside the projection cone. Worth knowing up front: though this documentation might say “cone,” the uProjector and Camera USD nodes don’t actually project a cone — it’s nearer a pyramid of light whose apex rests at the camera/projector. The uProjector node forever projects a square pyramid of light, meaning its X and Y angles of view match. The Camera USD node’s pyramid of light, on the other hand, can come out non‑square depending on the camera’s Film Back. The aspect of whatever image feeds the uProjector/Camera USD leaves the pyramid’s X/Y angles alone; instead the image is scaled to seat within the pyramid per the fit options.

Should the pyramid’s aspect (AovY/AovX) and the image’s aspect (height _ pixelAspectY)/(width _ pixelAspectX) line up, the fit options aren’t needed and every one of them behaves identically. Once those two aspects diverge — the pyramid’s being set by the Film Back settings in Camera USD — the fit options start to matter. Take Fit by Width, which spreads the image’s width across the width of the Camera USD pyramid; here, if the image’s aspect ratio outstrips the pyramid’s, part of the projection spills vertically beyond the pyramid. There are five options:
