# Generator Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Generator Nodes

This section covers the Generator nodes that Fusion offers.

Each node name is paired with an abbreviation; you can type these into the Select Tool dialog while hunting for tools and reference them when scripting. Throughout this document, treat node graphs that display MediaIn nodes in DaVinci Resolve as equivalent to Loader nodes in Fusion Studio, except where a difference is called out.

### Background [Bg]

### The Background node

### Background Node Introduction

Whether you need a plain single-color backdrop or an intricate looping gradient, the Background node can build it.

### Inputs

The Background node carries a single input, meant for an effect mask. Effect Mask: Into this optional blue effect mask input you can feed a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask here confines the background color strictly to the pixels falling inside that mask.

### Basic Node Setup

After the Background node produces a color, it hands that color along to a downstream node such as the Paint node shown below.

### Inspector

A Background node generating a background for the Paint tool

### Color Tab

You govern both the style and the color(s) of the produced background from the Color tab. Type Reach for this control to pick which style of background the node turns out. There are four options:

- Solid Color: As the default, this yields a single-color image.
- Horizontal: This yields a two-color horizontal gradation.
- Vertical: This yields a two-color vertical gradation.
- Four Corner: This yields a four-color corner gradation.

Horizontal/Vertical/Four Point With the Type menu on Horizontal, Vertical, or Four Corner, the node presents two- or four-color swatches that let you assign the left/right, top/bottom, or four-corner gradient colors

### Horizontal gradient controls

### Gradient controls

### Gradient

Switching the Type menu to Gradient brings up extra controls for tailoring the direction of the gradient colors.

Gradient Type Which shape the gradient is drawn in is chosen from this menu. Six options exist:

- Linear: Lays the gradient down along a straight path running from the first color stop to the last.
- Reflect: Builds the gradient by mirroring the linear gradient out from each side of the starting point.
- Square: Builds the gradient with a square pattern while the starting point sits at the

center of the image.

- Cross: Builds the gradient with a cross pattern while the starting point sits at the center

of the image.

- Radial: Builds the gradient with a circular pattern while the starting point sits at the center

of the image.

- Angle: Builds the gradient with a counterclockwise sweep while the starting point sits at the

center of the image. Viewer Start and End Position Two red control points joined by a green line mark the Start and End positions inside the viewer, fixing where the gradient opens and closes. Gradient Colors You pick the gradient's colors from this gradient color bar. By default, two color stops establish the start and end colors. To recolor the gradient, select a color stop and then assign a fresh color with the Eyedropper or color swatch. The gradient bar lets you add, move, copy, and remove colors. Reworking a single color comes down to clicking the triangle that sits beneath it on the bar. Adding a fresh color stop to the gradient bar goes like this: 1 Click anywhere along the bar's lower edge. 2 Set the new stop's color through the Eyedropper or color swatch. Moving a color stop along the gradient bar: just drag it horizontally, left or right, across the bar. Copying a color stop: keep Command (macOS) or Ctrl (Windows) held while dragging a stop. Deleting a color stop: pull it upward, beyond the top of the gradient bar. Interpolation Space Which color space gets used when computing the colors that fall between stops is governed by this menu. Offset The Offset control shifts the gradient's position against the start and end markers. It proves most valuable alongside the repeat and ping-pong modes covered below.

Repeat Three options on this menu dictate how the gradient acts once the Offset control scrolls it beyond its start and end positions. Picking Once holds the color steady through the offset. Picking Repeat wraps back around to the start color whenever the offset runs past the end color. Picking Ping-pong plays the color pattern back in reverse. Sub-Pixel The Sub-Pixel menu sets the sub-pixel precision applied when the gradient's edges show up in repeat mode or when the gradient is animated. Cranking it higher slows rendering considerably but yields more accuracy. Gradient Contextual Menu Each gradient carries its own contextual menu, opened by right-clicking the gradient bar. That Gradient contextual menu holds choices for animating, publishing, and linking one gradient to another. It also offers a gradient-specific modifier that assembles a custom gradient by sampling colors off a node's output.

### Common Controls

Image and Settings Tabs Many Generator nodes repeat the same Image and Settings tabs found in the Inspector. You'll find these shared controls explained thoroughly later on, within this chapter's “The Common Controls” section.

### Day Sky [DS]

### The Day Sky node

### Day Sky Node Introduction

What the Day Sky node sets out to do is simulate the daylight occurring at a given time and place on earth, outputting a high dynamic range image that maps that light. It does not generate a sky on its own, though pairing it with a cloud generator or Noise node would let you build one. NOTE: This generator puts into practice the research paper A Practical Analytical Model for Daylight, authored by Preetham, Shirley, and Smits. You can find a copy of that original paper on the Visual Simulation Group's website at the University of Utah [https://www.cs.utah.edu].

### Inputs

The Day Sky node has just one input, for an effect mask that restricts where the day sky simulation gets applied. Effect Mask: This optional blue effect mask input takes a mask shape made from polylines, simple primitive shapes, paint strokes, or bitmaps brought in from other tools. Hook a mask up here and the Day Sky is held to just the pixels lying inside that mask.

### Basic Node Setup

Being a generator, the Day Sky node usually opens a branch in a node tree and feeds into another node, such as a Merge node.

### Inspector

A Day Sky connected as the background to a Merge node

### Day Sky controls

### Controls Tab

You set the location and time of the daylight simulation from the Controls tab, which in turn drives the overall look that emerges.

Location You name the location behind the Day Sky simulation with the Latitude and Longitude sliders. Date and Time You pick the exact moment for the Day Sky simulation through the Day, Month, and Time controls. Turbidity Turbidity makes light scatter and get absorbed within the simulation rather than traveling in straight lines. Raising the turbidity lends the sky simulation a murky quality, as though smoke or atmospheric haze hung in the air. Do Tone Mapping Because the simulation runs in 32-bit floating-point color space, it puts out color values far above 1.0 and far below 0.0. Tone mapping is the step that takes the simulation's full dynamic range and squeezes it into your target exposure range, all while trying to hold onto as much highlight and shadow detail as it can. Clear this checkbox to switch off any tone mapping on the simulation. As a rule, leave it cleared only when the resulting image will be color corrected afterward inside a floating-point color pipeline. Exposure Turn to this control to choose the exposure that tone mapping uses.

### Day sky Advance tab controls

### Advanced Tab

More targeted controls over the brightness and width of the various ranges within the produced sky live on the Advanced tad. Horizon Brightness Reach for this control to tune the horizon's brightness against the sky. Luminance Gradient Reach for this control to tune how wide the gradient is that divides the horizon from the sky.

Circumsolar Region Intensity Reach for this control to tune the intensity or brightness of the sky closest to the sun. Circumsolar Region Width Reach for this control to tune the width or extent of the sky region the sun affects. Backscattered Light Reach for this control to raise or lower the backscatter light within the simulation.

### Common Controls

Image and Settings Tabs A great many Generator nodes carry the very same Image and Settings tabs in the Inspector. Full descriptions of these shared controls appear later, in the “The Common Controls” section that closes this chapter.

### Fast Noise [FN]

### The Fast Noise node

### Fast Noise Node Introduction

As a Perlin Noise generator, the Fast Noise node is both quick and adaptable. It lends itself to a broad span of effects — clouds, drifting fog, waves, water caustics, stylized fire and smoke, plus other organic textures. It also serves brilliantly as a noise feed for further effects like heat shimmers, particle systems, and dirtiness maps.

### Inputs

By way of the Fast Noise node's two map inputs, you can deploy masks to steer the noise detail and brightness control values on a per-pixel basis. These two optional inputs open the door to some intriguing, inventive effects. A standard effect mask input is present as well, used to bound the Fast Noise size. Noise Detail Map: Feed a soft-edged mask into the gray Noise Detail Map input and you get a flat noise map (zero detail) wherever the mask reads black, full detail wherever it reads white, and a smooth taper of detail at the values in between. It takes effect ahead of any gradient color mapping. This proves handy when you want peak noise detail concentrated in one spot, easing off gently everywhere else. Noise Brightness Map: Wire a mask to this white input to take full command of the noise map — lifting it in select regions, fusing it with other textures, or, when Detail sits at 0, swapping out the Perlin Noise map entirely. Effect Mask: Into this optional blue effect mask input goes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Attach a mask here and the Fast Noise is confined to only the pixels within that mask.

### Basic Node Setup

You call on the Fast Noise node to produce images that downstream nodes can put to work. In the example below, for instance, it supplies the bitmap feeding a Particle Emitter. A Fast Noise node serving as the bitmap origin driving a Particle Emitter Inspector

### Fast Noise controls

### Noise Tab

The Fast Noise node's noise shape and pattern are governed from the Noise tab. Discontinuous Ordinarily the noise function interpolates across values to yield a smooth, unbroken gradient of results. Tick this checkbox to carve hard discontinuity lines along some of the noise contours, which produces a strikingly different look. Inverted Tick this checkbox to flip the noise, turning out a negative of the original pattern. It works best with Discontinuous switched on too. Center Pan and reposition the noise pattern through the Center coordinate control. Detail Push this slider up to draw out finer detail in the noise result. Bigger values stack on more layers of ever-finer noise without disturbing the broad pattern. High values render more slowly yet can deliver a more natural outcome.

Brightness Ahead of any gradient color mapping, this control tunes the noise map's overall brightness. Under Gradient mode it behaves much like the Offset control. Contrast This control raises or lowers the noise map's overall contrast before any gradient color mapping kicks in. It can heighten the noise's impact and broaden the spread of colors used in Gradient mode. Lock and Scale X/Y You resize the noise map via the Scale slider, dialing it from soft variations spread across the whole image to a tighter, denser texture. Ticking the Lock X/Y checkbox just above splits the Scale slider into separate X- and Y-axis scale sliders, which comes in handy for a brushed-metal look. Angle Spin the noise pattern with the Angle control. Seethe Nudge this thumbwheel control to interpolate the noise map toward a different noise map, producing a creeping shift in the noise as though it were drifting or flowing. You must animate this control for the gradient to evolve over time, or instead lean on the Seethe Rate control below. Seethe Rate Like the Seethe control above, the Seethe Rate likewise drives the noise map to evolve and shift. The Seethe Rate fixes how fast the noise changes from frame to frame, automatically generating an animated drift without any need for spline animation.

### Fast Noise node Color tab

### Color Tab

From the Color tab you tune the gradient colors that paint the produced noise pattern.

Two Color A plain two-color gradient colors the noise map, with the noise function easing smoothly from the first color across to the second. Gradient Fusion's Advanced Gradient control hands you finer command over the color gradient applied to the noise map.

### Common Controls

Image and Settings Tabs Numerous Generator nodes share identical Image and Settings tabs within the Inspector. These shared controls get their full write-up toward the chapter's end, under “The Common Controls.”

### Mandelbrot [MAN]

### The Mandelbrot node

### Mandelbrot Node Introduction

Drawing on the Mandelbrot fractal theory set, this node builds an image pattern.

### Inputs

The Mandelbrot node's lone input serves an effect mask that bounds where the fractal noise lands. Effect Mask: This optional blue effect mask input accepts a mask shape drawn from polylines, simple primitive shapes, paint strokes, or bitmaps imported from other tools. Hooking a mask up here keeps the fractals to only the pixels within that mask.

### Basic Node Setup

Images turned out by the Mandelbrot node lend themselves to motion graphics and sci-fi effects. In the example below, it produces motion graphics that sit behind a title.

A Mandelbrot node applied as a background to the Merge node

### Inspector

### Mandelbrot node controls

### Noise Tab

The Mandelbrot node's noise shape and pattern are steered from the Noise tab. Position X and Y This sets the image's horizontal and vertical position, or its seed point. Zoom Zoom drives the pattern larger or smaller. Each level of magnification is recomputed, so the zoom has no real ceiling. Escape Limit Marks the point at which the iteration's calculation halts. Low values bring on blurry halos. Iterations This dictates how repetitive the set is. Animate it and it mimics the set growing. Rotation This spins the pattern. Each fresh angle forces the image to be recomputed.

### Color Tab

From the Color tab you tune both the gradient and how the gradient colors repeat across the produced pattern. Grad Method Reach for this control to decide which kind of gradation applies along the pattern's borders. Continuous Potential This makes the pattern's edges fade into the background color. Iterations This makes the pattern's edges come out solid.

### The Mandelbrot node Color tab

Gradient Curve This governs how wide the gradation runs as the pattern transitions into the background color. R/G/B/A Phase and Repetitions These controls assign the color values for the pattern generators.

### Common Controls

Image and Settings Tabs Other generator nodes reproduce the same Image and Settings tabs seen in the Inspector. A detailed account of these shared controls follows at the chapter's close, in the “The Common Controls” section.

### MultiText [MTxT]

### The MultiText node

### MultiText Node Introduction

Built on the Text+ tool, Fusion's MultiText node is a sophisticated character generator that handles multiple styles, 3D transformations, and several shading layers. You can arrange text within a userdefined frame, around a circle, or along a path. The image this node turns out is 2D. When you need extruded 3D text with optional beveling, turn instead to the Text 3D node.

### Inputs

The MultiText node's single input takes an effect mask for cropping the text. Effect Mask: This optional blue effect mask input takes a mask shape fashioned from polylines, simple primitive shapes, paint strokes, or bitmaps brought over from other tools. Wire a mask in here and the text is held to just the pixels lying within that mask.

### On-Screen Controls

A range of editing tasks can be carried out right on MultiText within the Viewer overlay — among them editing text, showing a cursor, and selecting text. The workflow feels natural: with MultiText selected, a double-click anywhere in the Fusion viewer switches on the in-viewer text editing mode.

### Text+ toolbar

Allow Typing in Viewer Once this is on, you can enter and revise text straight in the viewer. Clicking the text there drops the insert cursor inside the text. The Left and Right Arrow keys walk the insert cursor from one character to the next, while the Up and Down Arrows jump between text lines. Allow Manual Positioning The Manual Positioning button takes over from the automatic kerning that text normally receives. Click the little red handle beneath any character to select it for kerning. Alternatively, drag a selection rectangle around whichever characters you mean to kern. With characters selected, keep the Option (macOS) or Alt key (Windows) held while tapping the Left or Right Arrow key to fine-tune the kerning of the chosen characters. Holding Alt + Shift (Windows) or Option + Shift (macOS) along with the arrow keys shifts the character in bigger steps. To keyframe each character's position, right-click the control label Manual Font Kerning under the Inspector's Advanced Controls and pick Animate from the contextual menu. Every time a character moves, a fresh key lands on the animation spline. As with polyline mask animation, all characters ride the same spline. No Text Outline Turning this button on stops any outline from being drawn around the text edges. That outline belongs not to the text but to the onscreen controls, helping you spot where the text sits. It makes up a three-way toggle, paired with two more buttons: Text Outline Outside Frame Only plus Show Always Text Outline. Text Outline Outside Frame Only Activating this draws a text-edge outline lying outside the visible frame, handy for tracking down text that has drifted offscreen and no longer renders a visible result. It is a threeway toggle paired with the No Text Outline and Show Always Text Outline buttons.

### Show Always Text Outline

No matter whether the text shows inside the frame or not, this button draws an outline around its edges. It is a three-way toggle together with the No Text Outline and Text Outline Outside Frame Only buttons.

The on-screen MultiText editing controls sit at the top-left corner inside the Fusion viewer The Fusion viewer also surfaces pivot points for your Character, Word, and Line transforms. To keep them within reach, the popup toolbar now sports a Pivot Points icon that flips their visibility on and off while you work rotation and scaling transformations. Character-level styling has been polished to make offset and translation transformations more intuitive. The upshot is less reliance on manual positioning and a uniform result across several distinct character selections.

### Basic Node Setup

Pairing the MultiText node with plenty of other nodes lets you build motion graphics. In the example below it feeds in as the foreground of a Merge node.

MultiText node connected as the foreground to a Merge node

### Inspector

### MultiText Text tab controls

### Text Tab

The Text section holds parameters that anyone who has worked in a word processor will recognize, covering the everyday text formatting options. Text List Acting as a master panel, the Text List shows every text layer you have made. Right from the text list panel you can enable/disable, lock, delete, and rename a layer. Just beneath the Text List sit the Add Text buttons, which offer three popular layout types — Point, Text Box, and Circle — so adding your chosen input style takes no effort. CSV lets you pull text in from a spreadsheet. Point: The text grows out from one point on the screen, free of any horizontal or vertical limits. Text Box: A bounding box pens the text in both horizontally and vertically. With Text Box chosen, you'll find the Wrap to Text Box and Clip to Text Box checkboxes on the Layout tab. Turn on Wrap to Text Box and your text automatically rolls onto the next line as it reaches the text box edge. Turn on Clip to Text Box and any text spilling past the text box's bounds is visually trimmed away, stopping overflow while leaving the excess content intact. Circle: The text follows a user-defined arc. CSV: Brings a Comma Separated Value (.csv) spreadsheet into MultiText and lays it out automatically as column-aligned text. Once it lands in MultiText, you're free to revise the titles however suits you. Font A pair of Font menus let you choose the font family and the typeface, such as Regular, Bold, and Italic.

Size Reach for this control to grow or shrink the text. Emphasis This hands you a choice of underlined or strikethrough text. Color Sets the text's basic fill color. It is the very same control that appears in the Shading tab color swatch. Tracking The Tracking parameter tunes the even spacing between every text character. Align Each tab accepts left, right, or centered alignment, plus top, center, or bottom alignment. Justify Justifies the text to the left, right, center, or all. Indent Lets you raise or lower the indention level. Line Spacing Line Spacing sets the gap between each line of text — what wordprocessing applications sometimes call leading. Direction This menu offers choices for the Direction the text runs, either horizontally or vertically in either orientation, which helps certain Asian languages flow correctly during animation. Line Direction Through these menu choices you fix the text flow as one of four options: left to right, its reverse right to left, top to bottom, or the opposite bottom to top. Reading Direction Here the choices let you set the text's reading direction either automatically or by hand. You can call out left-to-right languages such as English, German, and so on, or right-to-left languages such as Arabic and Hebrew. Force Monospaced This slider control lets you override the kerning (the spacing between characters) baked into the font. Leave the slider at zero (its default) and Fusion leans wholly on the kerning carried by each character. Set it to one and the spacing between characters turns perfectly even, or monospaced. Use Font Defined Kerning This switches on the kerning laid out in the TrueType font and starts out enabled.

Use Ligatures Should your font carry ligatures, switch them on here by picking All Scripts. Ligatures fuse separate letters into one glyph, as with ff and fl. When you are animating text letter by letter, you usually want those ligature letters split apart rather than merged into a single glyph, which is why None is the default for Latin characters. Some languages such as Arabic depend on ligatures to render properly and call for the Non-Latin setting. Style Can Split Ligatures Tick this box when your font offers the option to break ligatures apart. Stylistic Set When your font carries stylistic sets, you can pick them from the drop-down menu. Manual Kerning/Positioning Lets you wipe out any earlier manual kerning or positioning of the text with the matching button. Merge Apply merge compositing settings. To learn more about these controls, refer to Chapter 95, "Composite Nodes,".

### MultiText Layout tab controls

### Layout Tab

These parameters govern where the text is positioned.

### Type
