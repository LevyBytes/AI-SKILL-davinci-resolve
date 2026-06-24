# Generator Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Point: Of all the layout modes, Point layout is the most basic. The text wraps around a center point you can move.
- Text box: With Frame layout you lay out a rectangular frame against which the text gets aligned. The alignment controls handle justifying the text both vertically and horizontally inside the frame's edges.
- Circle: Circle layout runs the text along the arc of a circle or oval. You control the diameter as well as the width of that circular shape. With the layout in this mode, the Alignment controls decide whether the text rides the inner or outer edge of the circle, plus how several lines of text get justified.

Center X, Y, and Z These controls place the layout element's center within space. X and Y act as onscreen controls, whereas Center Z appears as a slider among the node controls. Size This slider governs how large the layout element is scaled. Perspective This slider adds or strips perspective away from the rotations that the Angle X, Y, and Z controls produce. Align Layer These controls let you line the layers up horizontally and vertically, and also align them to either the frame boundary or, instead, the title safe margin. Rotation Rotation is a row of buttons that lets you pick the sequence in which the text's 3D rotations occur. Angle dials are available for setting the Layout element's angle on any axis.

### Multitext Shading tab controls

### Shading Tab

Within the Shading tab sit the controls for tuning the text's color, outline, and shadow. Fill These controls govern the color and opacity of the text layer. Enable: Tick this box to switch the text layer on or off. Color Controls:0These assorted controls let you pick the color and opacity for the text layer.

- Softness X and Y: These sliders set how soft the text outline becomes when forming the shading element. The X- and Y-axis can each be controlled on their own. Glow: This slider lays a glow over the softened part of the shading element. Blend: This slider sets how far the softness control's result gets blended back toward the original. You can lean on it to soften the outcome of the soften operation.

Outline These controls fix the color and style of the font outline. Enable: Tick this box to switch the font outline on or off. Color Controls: These controls govern the color and opacity of the outline. Thickness: Thickness sets how thick the outline becomes. Larger values yield thicker outlines. Adapt to Perspective: Ticking this checkbox makes your outline taper thinner where the text recedes from the camera and thicker where it draws nearer. This yields a more believable outline on text transformed in 3D, though it adds considerably to render time. Outside Only: Ticking this checkbox confines the outline to the text's outer edge alone. Out of the box, the outline straddles the edge and overlaps the text in part. Join Style: These buttons present choices for how the outline's corners are rendered. The choices include Sharp, Rounded, and Beveled. Line Style: This menu supplies further choices for the line's style. Apart from the standard solid line, an assortment of dash and dot patterns is on offer. Shadow These controls fix the color and style of the font drop shadow. Enable: Tick this box to switch the font drop shadow on or off. Color Controls: These controls govern the color and opacity of the drop shadow. Position X/Y: These set where the drop shadow lands relative to the main text.

### Page Tab

These parameters let you place a custom-colored backdrop behind the text layers. Layout These govern the text layer's size and placement. Background These controls govern the color of the background shape. Pure black renders as transparent.

### Image Tab

These parameters give you control over the image as a whole, such as aspect ratio plus color and gamma spaces.

### Settings Tab

These parameters are the usual Settings controls shared by Fusion Generator Nodes.

### Plasma [PLAS]

### The Plasma node

### Plasma Node Introduction

The Plasma node generates backgrounds, drawing on four circular patterns to build images resembling plasma. It serves well as a deforming pattern feeding the Shadow and Deform nodes, and for producing an array of other handy shapes and patterns. It bears a resemblance to the Fast Noise node.

### Inputs

Plasma's single input takes an effect mask that restricts where the plasma pattern shows up. Effect Mask: This optional blue effect mask input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input confines the plasma to just the pixels inside the mask.

### Basic Node Setup

Much like the Mandelbrot node, the Plasma node turns out images suited to motion graphics and sci-fi effects. In the figure below it produces motion graphics serving as a title's backdrop.

### Inspector

A Plasma node applied as a background to a Merge node

### Plasma node Circles tab

### Circles Tab

Through the Circles tab you govern the shape and pattern the Plasma node turns out. Scale The Scale control sets how large the generated pattern is. Operation This menu's choices set the mathematical relationship the four circles take on wherever they cross. Circle Type Pick which kind of circle gets used. Circle Center Read out and shift where the circle's center sits. Circle Scale Sets how large the circle used for the pattern is.

### Plasma node Color tab

### Color Tab

By way of the Color tab you tune the colors and where, within the pattern, those colors land for the plasma being generated. Phase Phase shifts the whole image's color phase. Animating it produces psychedelic color cycles. R/G/B/A Phases Shifts the phase of each individual color channel along with the Alpha. Animating these produces color cycling effects.

### Common Controls

Image and Settings Tabs The Inspector's Image and Settings tabs recur across numerous Generator nodes. These shared controls get a full treatment toward this chapter's close, in the "The Common Controls" section.

### Text+ [TXT+]

### The Text+ node

### Text+ Node Introduction

The Text+ node in Fusion is a sophisticated character generator that handles multiple styles, 3D transformations, and several shading layers. You can lay the text out against a user-defined frame, around a circle, or along a path. Text can be built from any TrueType, OpenType, or PostScript 1 font present on the machine. Thanks to multibyte and Unicode character support, text can be generated in any language, right-to-left and vertically oriented scripts included. This node turns out a 2D image. For extruded 3D text with optional beveling, turn to the Text 3D node.

### Inputs

Text+ has a single input, which takes an effect mask for cropping the text. Effect Mask: This optional blue effect mask input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input confines the text to just the pixels inside the mask.

### On-screen Controls

Right within the Viewer overlay you can run a range of editing actions on Text+, among them editing text, showing a cursor, and selecting text. Switch this on by hovering over the popup toolbar inside the Fusion viewer and activating it, or else right-click the View menu. The behavior is intuitive: with Text+ selected, a double-click anywhere in the Fusion viewer turns on the in-viewer text editing mode.

Inside the Fusion viewer you'll also come across pivot points for your Character, Word, and Line transforms. To make them handy, a Pivot Points icon now sits in the popup toolbar, letting you flip their visibility while tweaking rotation and scaling transformations. The Z position-based sorting mode is a strong addition to the toolkit. Unlike the Distance mode, which orders by absolute distance from the camera, this mode orders purely on the Z distance from the camera, no matter the relative orientation. Z position lets you freely stack overlapping text elements for precise layering and depth control. Character-level styling has been polished to make offsets and translation transformations more intuitive. The improvement cuts down on manual positioning and keeps the application consistent across several separate character selections.

### Basic Node Setup

You can pair the Text+ node with plenty of other nodes to build motion graphics. In the figure below it's wired in as a Merge node's foreground.

### Inspector

Text+ node connected as the foreground to a Merge node

### Text+ Text tab controls

### Text Tab

The Inspector's Text tab splits into three parts: Text, Advanced Controls, and Tab Spacing. The Text section holds parameters anyone who's worked in a word processor will recognize. It carries the text formatting options people reach for often. The Advanced controls cover kerning options, while Tab Spacing sets where tabs sit and how they align within the layout.

Styled Text This tab's edit box is where you type the text to be built. Any ordinary character can go into this box. The standard OS clipboard shortcuts function here as well — copy with Command-C or Ctrl-C, cut with Command-X or Ctrl-X, paste with Command-V or Ctrl-V; right-clicking inside the edit box, though, brings up a custom contextual menu. Further detail on these modifiers sits at this section's close. The Styled Text contextual menu offers these options:

- Animate: Drives animation of the text across time.
- Character Level Styling: Lets you alter the font, color, size, and transformations of

separate characters or words by way of the Modifiers tab.

- Comp Name: Drops the composition's name into the Styled text box, handy for building slates.
- Follower: A text modifier that cascades animation from one character of the text to the next.
- Publish: Makes the text available for wiring to other text nodes.
- Text Scramble: A text modifier that shuffles the text's characters at random.
- Text Timer: A text modifier that shows a countdown, or else the present date and time.
- Time Code: A text modifier that shows the Time Code belonging to the current frame.
- Connect To: Wires the text up to another node's published output.

Font A pair of Font menus serve to pick the font family along with the typeface, such as Regular, Bold, and Italic. Color Fixes the text's basic fill color. It's the same control that shows up in the Shading tab color swatch. Size This control raises or lowers the text size. It doesn't work like picking a point size in a word processor. Size is gauged relative to the image's width. Tracking The Tracking parameter sets the even spacing placed between each text character. Line Spacing Line Spacing sets how far apart each line of text sits. Word-processing applications sometimes call this leading. V Anchor The vertical anchor controls comprise three buttons plus a slider. Those three buttons align the text vertically to the text's top, its middle, or its bottom baseline. The slider serves to fine-tune the alignment. Where you set the vertical anchor shapes both how the text rotates and where line spacing adjustments take effect. This control sees most use with the Layout type at Frame in the Layout tab. V Justify The vertical justify slider lets you tune the text's vertical alignment from the V Anchor setting all the way to full justification, so it sits evenly between the top and bottom edges. Reach for it chiefly once Frame is the Layout type over in the Layout tab.

H Anchor The horizontal anchor controls comprise three buttons plus a slider. Those three buttons set the text alignment to the text's left edge, its middle, or its right edge. The slider serves to fine-tune the justification. Where you set the horizontal anchor shapes both how the text rotates and where tracking (leading) spacing adjustments take effect. Its main use comes with Frame chosen as the Layout type inside the Layout tab. H Justify The horizontal justify slider lets you tune the text's justification from the H Anchor setting all the way to full justification, so it sits evenly between the left and right edges. You'll lean on it mostly when Frame serves as the Layout type within the Layout tab. Direction This menu hands you choices for the Direction the text runs — horizontally or vertically, and either way around. That lets certain Asian languages flow correctly through animation. Line Direction Through these menu choices the text's flow is set to one of four directions: top to bottom, bottom to top, left to right, and finally right to left. Underline and Strikeout A pair of buttons that add emphasis styling to the text. Write On This range control quickly lays simple Write On and Write Off effects over the text. For a Write On effect, animate the control's End portion from 1 to 0 across the span of time you need. For a Write Off effect, animate the range control's Start portion from 0 to 1.

### Tab Spacing

### Tab Spacing

The controls in the Tabs section set the horizontal screen positions for eight independent tab stops. Whatever tab characters the text holds will snap to these positions. You can drop tabs straight into the Styled Text input as you type. Another route is to copy from a separate document — Text on macOS or Notepad on Windows, for instance — then paste that into the text box. Position This control sets where, horizontally, the tab falls in the frame. The values run from -0.5 to 0.5, with 0 marking the center. A thin vertical white line in the viewer marks the tab's position whenever the Text node is selected. A handle sits atop each tab line in the viewer. That handle lets you place the tab by hand.

### Alignment

Any tab can be made left aligned, right aligned, or centered. This slider runs from -1.0 to 1.0, where -1.0 gives a left-aligned tab, 0.0 a centered tab, and 1.0 a right-aligned tab. Clicking a tab handle in the viewer cycles that tab's alignment through the three states.

### Advanced font controls

Reading Direction These options let you fix the text's reading direction, whether automatically or by hand. You can call out Left to Right languages such as English, German, etc. or Right to Left languages such as Arabic and Hebrew. Force Monospaced This slider control lets you bypass the kerning (the spacing between characters) the font defines. Leaving this slider at zero (its default value) makes Fusion lean entirely on the kerning each character carries. A value of one makes the spacing between characters perfectly uniform, that is, monospaced. Use Font Defined Kerning This switches on kerning as the TrueType font defines it, and it's on by default. Use Ligatures Should your font carry ligatures, switch them on here by picking All Scripts. Ligatures fuse separate letters into single glyphs, such as and . When you're animating individual text letters, you often want the ligature letters kept apart one by one rather than fused into a single glyph, so None is the default for Latin characters. Some languages such as Arabic need ligatures to render right, and call for the Non-Latin setting.

Style Can Split Ligatures Tick this box should your font carry the option to split ligatures.

Stylistic Set Should your font carry stylistic sets, you can pick them from the drop-down menu.

### Font Features

Here you assign OpenType 4 letter tags to turn on specific font features. For instance, "smcp"

will show

, while "frac" renders fractions as ½ rather than 1/2. A given font won't necessarily

carry every feature. The complete roster of OpenType feature codes lives at this address: https://docs.

microsoft.com/en-us/typography/opentype/spec/featurelist

### Manual Font Kerning/Placement

A right-click on this label brings up a contextual menu you can use to animate the text's kerning. Turn to this node's "Toolbar" section further along in this chapter for the particulars on manual kerning.

### Text+ Layout tab controls

### Layout Tab

The text-positioning controls live in the Layout tab. The Type drop-down menu lets you pick one of four layout types.

- Point: Of all the layout modes, Point layout is the most basic. The text wraps around a center point you can move.
- Frame: With Frame layout you lay out a rectangular frame against which the text gets aligned. The alignment controls handle justifying the text both vertically and horizontally inside the frame's edges.
- Circle: Circle layout runs the text along the arc of a circle or oval. You control the diameter as well as the width of that circular shape. With the layout in this mode, the Alignment controls decide whether the text rides the inner or outer edge of the circle, plus how several lines of text get justified.
- Path: With Path layout you bend your text along the edges of a path. The path may merely lend style to the text, or it can be animated by way of the Position on Path control, which surfaces once this mode is chosen.

Center X, Y, and Z These controls place the layout element's center within space. X and Y act as onscreen controls, whereas Center Z appears as a slider among the node controls. Size This slider governs how large the layout element is scaled. Perspective This slider adds or strips perspective away from the rotations that the Angle X, Y, and Z controls produce. Rotation Rotation is a row of buttons that lets you pick the sequence in which the text's 3D rotations occur. Angle dials are available for setting the Layout element's angle on any axis. Width and Height Whenever the Layout mode is Circle or Frame, the Width control becomes visible. As for the Height control, it appears solely while the Layout mode sits at Frame. The Width and Height controls serve to tune the Layout element's dimensions and aspect. Fit Characters This menu control shows up only when the Layout type is set to Circle. The menu lets you pick how the characters get spaced to sit along the circumference. Position on Path The Position on Path control governs where the text falls along the path. Values below 0 or above 1 push the text past the path, continuing along the same direction as the path's vector between the final two keyframes. Background Color This node usually renders its text against a transparent background. This Color Picker control lets you assign a background color instead. Right-Click Here for Shape Animation This label surfaces only when the Layout type is set to Path. It opens a contextual menu offering options for tying the path to other paths within the node tree and for animating the path's shape across time. For further detail, consult Chapter 73, "Animating with Motion Paths," within the DaVinci Resolve Reference Manual, or else Chapter 11 of the Fusion Reference Manual.

### Text+ Transform tab controls

### Transform Tab

The Transform tab serves to move, rotate, shear, and scale text by character, word, or line. Transform The Transform menu sets which slice of the text the transformations applied in this tab act upon. Transformations can hit the line, word, and character levels all at once. This menu exists merely to hold the count of visible controls to something reasonable.

- Characters: Every text character gets transformed around a center axis of its own.
- Words: Every word gets transformed on its own, around the word's center axis.
- Lines: Every line of the text gets transformed on its own, around that line's center axis.

Spacing The Spacing slider tunes the gap between each line, word, or character. Values under 1 usually start to make the characters overlap. Pivot X, Y, and Z This gives you precise control over where the axis sits. By default the axis lands at the computed center of the line, word, or character. The Axis control acts as an offset, so a value of 0.1, 0.1 here would nudge the axis down and to the right for each of the text elements. Positive values on the Z-axis slider push the axis of rotation farther along the axis (away from the viewer). Negative values draw the axis of rotation nearer. Rotation These buttons set the order the transforms run in. X, Y, and Z would mean the rotation hits X first, then Y, then Z. X, Y, and Z These controls tune the angle of the text elements across any of the three dimensions.

Shear X and Y Work these sliders to skew the text elements' slant along the X- and Y-axis. Size X and Y Work these sliders to alter the text elements' size along the X- and Y-axis.

### Text+ Shading tab controls

### Shading Tab

Within the Shading tab sit the controls for tuning the text's shading, texture, and softness. Transformations are steerable from here as well, layering extra transformations onto as many as eight separate text shading elements on their own. Shading Element The menu's eight number values let you pick which element the adjustments in this tab affect. Enabled Tick this checkbox to switch each layer of shading elements on or off. Element 1, the fill color, is on by default. A shading element's controls stay hidden until this checkbox is ticked. Sort By This menu lets you order the shading elements by number priority, with 1 the topmost and 8 the bottommost element, or by Z depth, going off the Z Position parameter. Name This text label lets you hand each shading element you build a more descriptive name.

Appearance The four Appearance buttons set how the shading element gets laid onto the text. Which controls turn up below hinges on the appearance type you pick.

- Text Fill: Here the shading element covers the whole of the text. This serves as the default mode.
- Text Outline: Here the shading element renders as an outline tracing the text's edges.
- Border Fill: Here the shading element fills a border that wraps the text. Five extra controls come

with this shading mode.

- Border Outline: In Border Outline mode an outline is rendered around the border that wraps the

text. A handful of extra controls come with it. Opacity The Opacity slider sets the shading element's overall transparency. Generally it's wiser to apply opacity to a shading element than to tweak the Alpha of the color on that element. Blending This menu lets you pick how the renderer handles an overlap between two characters in the text.

- Composite: Merges the shading over the top of itself.
- Solid: Sets the pixels in the overlap region to opaque.
- Transparent: Sets the pixels in the overlap region to transparent.

Thickness (Outline only) Thickness sets how thick the outline is. Larger values yield thicker outlines. Adapt Thickness to Perspective (Outline only) Ticking this checkbox makes your outline taper thinner where the text recedes from the camera and thicker where it draws nearer. This yields a more believable outline on text transformed in 3D, though it adds considerably to render time. Outside Only (Outline only) Ticking this checkbox confines the outline to the text's outer edge alone. Out of the box, the outline straddles the edge and overlaps the text in part. Join Style (Outline only) These buttons present choices for how the outline's corners are rendered. The choices include Sharp, Rounded, and Beveled. Line Style (Outline only) This menu supplies further choices for the line's style. Apart from the standard solid line, an assortment of dash and dot patterns is on offer. Level (Border Fill only) This governs which slice of the text border gets filled.

- Text: This draws a border around the entire text.
- Line: This draws a border around each line of text.
- Word: This draws a border around each word.
- Character: This draws a border around each character.
  </content>
