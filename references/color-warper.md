# Color Warper (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Color Warper

As a robust toolset, the Color Warper handles everything from pinpoint tweaks to single elements within the frame to broad, sweeping changes that build distinctive looks. Each of the Color Warper's two modes makes it simple to shift hues with the Chroma Warp, or to reshape a pair of color attributes at once, whether that pairing is saturation and hue or lightness and hue. That capability sets the Color Warper apart from curves, which restrict you to altering a lone color characteristic per pass.

### Introduction to the Color Warper

Two distinct modes make up the Color Warper: Chroma Warp, and Hue-Saturation / Chroma-Luma. The aim of either mode is to bend one group of colors into another while keeping a gentle falloff that qualifiers on their own would struggle to deliver. On any given node, though, you have to commit to either the Chroma Warp or the Hue-Saturation / Chroma-Luma controls.

### Chroma Warp

You will find the Chroma Warp as a mode within the Color Warper Palette. It shares its goal with the Color Warper Hue-sat / chroma-luma controls, namely producing smooth, accurate transitions across color ranges. Where it parts ways is the method: the Chroma Warp draws strokes onto a chromaticity diagram instead of nudging mesh points to apply its changes. Either approach yields excellent output, yet only one of the two can run on a single node, so you commit to either the traditional Color Warper or the Chroma Warp.

The Chroma Warp chromaticity diagram on the left, with its toolset over on the right At the heart of the Chroma Warp interface sits a chromaticity diagram, with the spread of the image's present colors laid over it in white (much like a vectorscope rendering) and the toolset off to the left. Because that chromaticity diagram is perceptually uniform, the gaps between its points track closely with the visual differences you perceive in the image while working the Chroma Warp. The Chroma Warp also ignores exposure, so once a Chroma Warp is in place, later shifts in luminance will not undo your qualified selection. Your opening choice is whether to run the Chroma Warp in Normal or Point to Point modes.

### Using The Chroma Warp in Normal Mode

Reach for this mode whenever you want a color to flow organically into another across the whole span of colors sitting between the two, such as deepening an entire sky toward a richer blue. Pick the color range you intend to alter by:

- Picking the starting color with the qualifier eyedropper in the Viewer, and then dragging toward where the replacement color sits on the chromaticity diagram. As you drag across the color ranges, the Viewer refreshes, which lets you settle precisely on the change you are after.
- Clicking the color as it appears within the chromaticity diagram itself, and then dragging in the direction of whatever color you mean to swap it for.

Whichever route you take, a blue dot on the chromaticity diagram marks the color you began with, while an orange dot stands for the destination color. An arrow joins the two to convey the extent of the change. Surrounding the vector, an orange outline traces every color that has been touched. Pull the points in toward the white point (that small circle in the diagram) to drain saturation, or push them out toward the edges to boost a color's saturation.

The Chroma Warp running in Normal mode, simultaneously pushing the grass tones toward more yellow and the sky toward a deeper blue.

### Using The Chroma Warp in Point to Point Mode

Turn to this mode to single out one color and convert it wholesale into a different one, for instance taking a shirt from blue all the way to yellow without passing through green. Identify the particular color you wish to alter by:

- Sampling the source color via the qualifier eyedropper in the Viewer, then dragging in the direction of the replacement color on the chromaticity diagram. The Viewer keeps updating as you drag among the colors, so you can comfortably home in on the precise destination color you have in mind.
- Clicking the color where it shows up inside the chromaticity diagram, then dragging toward whichever color you want it to become.

By either method, the color you started from shows as a blue dot on the chromaticity diagram and the target color as an orange dot, with an arrow linking them to express the extent of the change. Here an orange outline wraps around both dots, marking the selection range of the original color and the final one. Dragging the points in toward the white point (the small circle in the diagram) strips saturation away, whereas dragging them toward the edges raises a color's saturation.

The Chroma Warp running in Point to Point mode, shifting only the shirt's color from blue over to yellow. TIP: Several Normal and Point to Point selections can run together inside one node, opening the door to very sophisticated color changes.

### Pin Points

With this tool you drop a pin that marks a color range to be held out of the selected range. Say you were recoloring a sign from red to green, but its yellow lettering happened to land in the band between those hues; you could place a pin point on the yellow text so it stays out of the color change. A second scenario would be pinning an actor's skin tones, keeping their skin constant no matter how the colors around them shift. Setting a pin point works just like the selection described above: either qualify a color straight off the image in the Viewer, or click the color within the chromaticity diagram.

Dropping a pin point around the white point so neutral tones avoid taking on a tint through a Chroma Warp operation TIP: Should the tool start introducing tinting, try parking a Pin Point on the chromaticity diagram's white point (the center circle), which pulls every neutral gray out of the color adjustment.

### The Chroma Warp tools

### Chroma Warp Tools

The Chroma Warp toolset is your gateway to the Warp's principal color-selection parameters.

- Add Stroke (Normal): Switches the Chroma Warp over to Normal mode for selecting a color range.
- Add Stroke (Point to Point): Switches the Chroma Warp into Point to Point mode for selecting one particular color.
- Add Pin Point: Lets you drop a pin that marks a color to be kept out of the selected range.
- Select: Lets you grab an existing range and drag it about the chromaticity diagram.
- Delete Strokes or Points: Lets you remove particular strokes and points already laid down on the Chroma Warp. Just click one of a range's points, then click the trashcan icon.

### Chroma Warp Stroke

Use the Chroma Warp stroke tools to tweak and sharpen whatever selection you have built.

- Chroma Range: Move this slider to dictate how many neighboring colors fall inside the range. Smaller ranges tighten the color selection, while larger ranges sweep in more of the surrounding colors.
- Exposure: Sliding this control dims or lifts the selection only at the ending circle (the orange dot), with negative values darkening and positive values brightening.
- Tonal Range Low: Sliding this control aims your change mainly at the darker areas of the originally selected color, sparing the lighter areas. The effect is global, reaching every stroke on the chromaticity diagram.
- Tonal Range High: Sliding this control aims your change mainly at the lighter areas of the originally selected color, sparing the darker areas. The effect is global, reaching every stroke on the chromaticity diagram.
- Tonal Range Pivot: This slider fixes the starting split between Tonal Range Low and Tonal Range High from which those tools branch apart.
- Normal/Point to Point Toggle: Clicking either icon flips a Normal selection into a Point to Point one, or the reverse.

### Hue-Saturation / Chroma-Luma Mode

The Color Warper Hue-Saturation / Chroma-Luma palettes form a mesh-based warping tool that bends one group of colors into another rather than displacing pixels in space. What's more, in contrast to the HSL curves, they allow you to tune two color parameters together at once, confined to userselectable zones of chosen hues. Carried out through a grid of draggable control points, these adjustments naturally taper off smoothly from the colors you are warping toward the other colors that have been locked in place. How smooth that taper turns out hinges on the gap between the warp points you are moving and the nearby warp points held fixed against change.

The Color Warper, sitting in the center palette area This tool offers two avenues of use. One is to drag the grid's control points directly, giving you very targeted image adjustments. The more instinctive route is to click and sample the image, which grabs the nearest grid point governing that color, and then drag to adjust using that control point.

Clicking and dragging to sample skin tone in the Viewer so that color's control point on the Hue-Saturation warping grid can be adjusted This tool can carry out extremely precise color tweaks in an image, comparable to what a Qualifier key or the HSL curves would let you do. Yet because the points warp through a grid, you can work two color characteristics together, moving both hue and saturation, or chroma and luma. The example that follows fine-tunes the woman's shirt, corrects her skin tone, and reworks the greens of the foliage in the shot. Each of these three lifelike adjustments stays smooth and free of artifacts thanks to the clean way the Color Warper remaps color.

(Top) The original image, (Bottom) Reworking the grass's hue and saturation by way of the Chroma-Luma controls Beyond that, this tool can build sweeping stylistic looks across the whole image, twisting the color in inventive directions other controls cannot reach. In the next image, every neutral and lower-saturation color gets warped toward a bluish-cyan, while the more saturated oranges are warped toward a saturated orange-red, producing a quick stylistic treatment of the image.

(Top) The original image, (Bottom) Giving the whole image a stylized treatment with the Hue-Saturation controls

### The Color Warper Interface

You may work with the Color Warper right where it docks in the middle palette area, or hit the Expand button to pop it out into a floating window you can stretch to any size, which gives you finer command over crowded grids of control points. For clarity, this chapter's examples present the Color Warper alongside the Viewer in a floating window. Once the Color Warper is open in its own window, pressing the Close button returns the palette to the palette area underneath.

Pressing the Expand button floats the Color Warper into its own window, and pressing the Close button inside that window docks the palette again. The Color Warper palette breaks into two broad regions. On the left, the grid area holds the warping grid itself, whose points you move to make adjustments, with controls below it for setting the grid's resolution and the color space it operates in. On the right, the control area supplies every tool, range control, and feathering control you can use to work the warping grid in all sorts of highly specific ways.

### Using the Grid Controls to Manipulate Color

Two modes live in this palette, each giving you its own way to work the image's colors and each carrying a distinct grid style for warping whichever color channels come into play. Getting comfortable with how you move the color-warping points on each of these grids is key to grasping how the palette behaves.

(Left) Hue-Saturation mode's radial grid, (Right) Chroma-Luma mode's pair of rectangular grids Dragging to Warp Colors Their shapes differ, yet all of these grids respond to handling in much the same fashion. When you drag a control point, the color tied to that point changes, and the colors ringing the dragged point shift proportionally too, based on where they fall between the point you are moving and neighboring points that either (a) go untouched or (b) are pinned in place. Pinned points hold the colors at those spots steady. Locking certain stretches of a grid while dragging others lets you build refined, hue-targeted adjustments.

Here the orange control point has been chosen and dragged to apply an adjustment. Those control points wearing black outlines are pinned and serve to keep the control points across from them from shifting. Every other control point lying between the selected and locked ones gets stretched or compressed according to how the selected point was moved.

The picture above illustrates the three states a control point can hold in the grid:

- Orange: A selected point shows in orange. You can pick several at once by Command-clicking each point, by dragging a bounding box across multiple points, or by reaching for the draw selection tool to click and sketch over whichever points you want. After you have selected a control point and moved it, it locks itself so the adjustment stays put.

A selected point shows in orange; here four points are selected so they can all be moved together.

- Outlined: White control points carrying a black outline are locked. Such points do not budge on their own when points nearby are dragged, which makes them valuable for protecting particular colors you would rather leave alone, and for preserving edits to points you have already moved. Any adjusted point becomes locked. The Chroma-Luma grid locks its outer corners, just as the Hue-Saturation web locks its outer ring and center point.

Locked points with black outlines stopping the selected point from adjusting other colors in the image

- White: A white control point is neither selected nor locked, and it will stretch or compress whenever adjacent control points are moved.

Unlocked control points caught between a selected point and locked points (here the grid's corners) will compress and stretch, warping a whole range of color as you drag.

Although control points behave largely alike whether you are in Hue-Saturation or Choma-Luma mode, a few meaningful distinctions exist. The radial “spokes” of the Hue-Saturation wheel leave their neighboring spokes alone, so any tweak you apply to a control point on one spoke reaches only the colors lying between it and the two spokes flanking it. As a result, there is no need to lock control points on adjacent spokes of this wheel-shaped grid to keep them steady.

Tweaks applied to control points on one “spoke” of the Hue-Saturation wheel grid leave the points on neighboring spokes untouched, which behave as though locked despite not being so. Both the Hue-Saturation and Chroma-Luma warper grids pin the grid's outer boundary. You may still drag those points to adjust them, but they cannot be unlocked and they won't shift on their own as you move other control points. The Hue-Saturation grid pins one extra point dead center, holding the neutral colors (black through gray and white) neutral. TIP: Dragging that locked center point of the Hue-Saturation grid lets you recolor the white point while every other color in the image warps proportionally to absorb the change smoothly. That move can serve as the seed for a wide variety of looks.

### Previewing Which Colors Are Warped By Each Control Point

Hold down the Option key as you click a control point in the warp grid, and the Viewer shows you a preview of exactly which colors that control point reaches. The affected pixels show up in color over a black field, where the black stands for all the pixels that point will leave alone.

Keeping the Option key held while clicking a Color Warper control point previews the affected pixels set against black.

### Sampling to Warp Colors

Although it pays to understand how the grid's control points are handled, the most natural way to work this control is to point inside the Viewer, click to sample a color you want to change, keep the button pressed, and drag to adjust it. As you move the pointer through the Viewer, a crosshairs travels around the warping grid to mark the exact color on the vectorscope graph, while a yellow box flags the control point nearest the color you are sampling, the one a click would grab. In the example below, parking the eyedropper over the sky reveals that a click would land on a control point near the grid's center.

Gliding the pointer across the Viewer previews on the warping grid the very control point a click would select. A click-and-drag first grabs and then relocates the control point that matches that color in the Viewer. While you drag, the chosen control point follows your mouse in lockstep as the image's colors refresh live to reflect the change you are making. At the same time, an arrow on the grid conveys the delta of the adjustment underway. Carrying a selected control point to a different hue in the grid warps the starting color into the new one.

A click-and-drag shifts the grid's control point for that color to apply your change and pins it in place. Control points can also be locked by sampling the image: hold Command and Shift together, then click whichever color or colors in the warp grid you want frozen against change. This lets you lock unwanted colors right in the Viewer before you go on to adjust the colors you actually mean to alter. In the example below, Command-Shift-clicking the woman's shoulder pins the yellowish highlights resting on her uniform. After that, click-dragging a highlight on her face pushes the highlights toward teal while the warmer highlights on her shoulder survive intact, all done by sampling straight in the Viewer.

(Top) Command-Shift-clicking to pin the warping grid's closest control point to a color you want left alone, (Bottom) Warping an adjacent color while that freshly locked control point holds its part of the image steady

### Resetting Grid Points

Whenever you have moved a point and decide you want it back to default, just right-click it to unlock and reset that point.

### Grid Resolution Affects The Specificity and Quality of Adjustments

In both Hue-Saturation and Chroma-Luma modes you can alter the grids' resolution through the controls along the foot of the Color Warper palette, just below the grid. Individual drop-down menus set the control-point resolution for hue and saturation, or for chroma and luma, on their own, though out of the box the two stay tied together.

The two resolution controls sitting beneath the grid controls Out of the box the Hue-Saturation grid runs at a resolution of 6x6, the coarsest setting on offer. The Chroma-Luma grid also starts at 6x6, yet it can drop further, down to 4x4. Coarse warping grids make it simple to apply broad color changes that span wide bands of analogous color while staying smooth. On top of that, weaker media that is 8-bit, uses 4:2:0 chroma subsampling, and/ or is heavily compressed gains from coarser warping grids, which fend off artifacts and keep the color changes smooth.

(Left) The Hue-Saturation grid at a resolution of 6x6, (Right) The Hue-Saturation grid at a resolution of 24x16 Finer grids, by contrast, let you target tighter color bands with more pinpoint adjustments. That route pays off best on projects shot with high-quality media (10- or 12-bit, 4:2:2 or 4:4:4 chroma subsampling, and lightly compressed) where artifacts can be kept at bay. Given high-quality media, you will be able to lean on the Color Warper for astonishingly precise adjustments. To fix the default Hue and Saturation grid resolutions, open the Color Warper's Option menu, pick Default Hue Resolution or Default Saturation Resolution, and choose the resolution you prefer from the drop-down menu.

The Chroma-Luma grid at a resolution of 6x6

The Chroma-Luma grid at a resolution of 24x24 NOTE: Should you adjust the grid at one resolution and then switch it coarser or finer, your adjustment is interpolated onto the new grid resolution, even though the end result may shift slightly.

### You Can Warp Color in Different Color Spaces

Down in the lower-right corner of the warping grid, a drop-down menu picks which color space governs how you work the image's colors. Each color space maps the image's colors onto the two-dimensional warping grid in its own way, and a given one might make a particular image easier to handle as you intend by fanning certain color ranges out more broadly.

### The color space found underneath the grid controls

The available color spaces are:

- HSV
- HSL
- HSY
- HSP

### Hue – Saturation Controls

True to its name, the Hue-Saturation mode lets you shift hue and saturation together. For most people it is probably the most instinctive mode to operate in, since the image's spread of hues and saturation is laid out radially, exactly as on the Vectorscope; indeed a Vectorscope graph of the image sits beneath the “wheel” grid of control points you use to push color around. By default, dragging any point on this grid affects the colors right around that point, the ones falling between the point you are moving and the radial grid's neighboring “spokes” that are either beyond that point's reach or locked down. In truth, you can drag these radial control points far past the line of the grid's adjacent spokes to warp those colors into completely different hues.

The control point you are adjusting leaves the points on neighboring columns alone, those columns running from the outer ring in to this control's center, even after you drag the point clear past them. Reshaping color through control points feels much like sliding color around a color wheel. Carrying a control point radially along the grid's circumference alters the hue of the colors that point represents. Bring a control point nearer the center and those colors lose saturation, while pulling one toward the grid's edge gains saturation for them. The sections ahead lay out how the various tools in this mode operate to let you work these radial control points in differing ways.

### Tools

Every one of the tools on offer gives you a different way to work the warping grid's control points once you click it.
