# Tracking Nodes (part 5)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Tracked Center Where the tracker's center sits is reported by this positional control. To strip a path you tracked earlier off a tracker pattern, right-click this parameter and pick Remove Path out of the contextual menu. X and Y Offset For objects that don't hand you a well-defined or dependable pattern, the Offset controls help you build a track anyway. What the Offset controls do is let you track something nearby in place of the intended object. Lean on these Offsets to nudge the path into the position you want, all while the tracker pattern rectangle stays parked over the real tracking spot. The Offset is adjustable right in the viewer too, by switching on the Offsets button found in the viewer toolbar.

Up at the viewer's top left, the tracker offset icon serves to shift the tracking pattern away from the object you're aiming at.

### Operation Tab

Whereas the Trackers tab controls let you shape how the Tracker node studies motion to build motion paths, the Operation tab takes that studied motion data and puts it to work, carrying out image transforms of assorted kinds. A wide range of jobs falls within the Tracker node's reach, anything from match moving an object into a moving scene, to steadying a shaky camera move, to swapping out the content of a sign. Turn to the options and buttons on the Operation tab to choose what job the Tracker node performs.

### The Tracker Operation tab

### Operation Menu

Four jobs that the Tracker performs are held within the Operation menu. The rest of the controls on this tab fine-tune whatever that selection produces.

- None: Beyond simply locating and tracking the pattern you chose, the Tracker carries out no further operation on the image. This is the default mode, relied on to build a path that will subsequently drive some other parameter on another node.
- Match Move: With only the orange background input hooked up, this mode steadies the image. Once a foreground image is wired into the green foreground input, that foreground image follows along in position, rotation, and scaling according to the tracking patterns. Both stabilizing and match move call for at least one tracking pattern to fix position, and two or more to fix scaling and rotation.
- Corner Positioning: The Corner Positioner mode tracks a rectangular object's four corners and swaps its contents out for a fresh image. At minimum, four tracking patterns are required for this function. Where there aren't enough tracking patterns, fresh tracking patterns get added until the tally hits four.
- Perspective Positioning: This mode runs the reverse of the Corner Positioning mode. Instead of swapping out the rectangle's contents, the four trackers are mapped onto the image's four corners. Its typical use is stripping perspective out of an image. As with the Corner Positioning mode, this one needs four tracking patterns, which get tacked on automatically should fewer patterns exist.

### Additional Layering Controls

Picking any operation besides None makes a set of extra controls appear. Merge What the Merge control settles is what happens (if anything at all) to the image fed into the green Foreground input of the Tracker. This menu surfaces once the operation is set to anything other than None.

- BG Only: The foreground input goes unused; only the background is touched. This serves chiefly when you're stabilizing the background image.
- FG Only: The foreground input gets transformed to track the movement in the background, and that transformed image passes out through the Tracker's output. This Merge approach comes into play when match moving the motion of one layer onto another layer's motion.
- FG Over BG: The foreground image lands over the background image, drawing on the Merge method spelled out by the Apply Mode control that appears.
- BG Over FG: The background lands over the foreground. People often reach for this approach when tracking a layer that carries an Alpha channel, so that a more static background can sit behind it.

Apply Mode and Operator Menus A range of options that decide how the two layers ought to combine is offered by this menu. The choices held in this menu match exactly the ones found in the Merge node.

- Apply Modes: What the Apply Mode setting fixes is the math that runs when the foreground and background pixels are blended or combined.

Normal: The Default merge mode treats the foreground's alpha channel as a mask that decides which pixels are transparent and which aren't. While it's active, a further menu surfaces the possible operations, among them Over, In, Held Out, Atop, and XOr. Screen: Screen merges the images by multiplying their color values together. The alpha channel goes ignored and layer order ceases to matter. The color you end up with always comes out lighter. Screening against black leaves the color as it was, whereas screening against white yields white every time. The effect resembles projecting several film frames onto one surface. While it's active, a further menu surfaces the possible operations, among them Over, In, Held Out, Atop, and XOr. Dissolve: Dissolve blends two image sequences into one. It draws on a computed average of the two images to carry out the mixture. Multiply: Multiplies a color channel's values. This lends the look of darkening the image as the values scale from 0 to 1. White carries a value of 1, so the outcome would stay the same. Gray carries a value of 0.5, so the outcome would be a darker image — put another way, an image half as bright. Overlay: Depending on the background image's color values, Overlay either multiplies or screens the foreground image's color values. Patterns or colors lie over the existing pixels while the background image's color-value highlights and shadows are kept intact. Rather than being replaced, the background image is mixed with the foreground image so that the background image's original lightness or darkness comes through. Soft Light: Depending on the background image's color values, Soft Light either darkens or lightens the foreground image. The result is akin to aiming a diffused spotlight at the image. Hard Light: Depending on the background image's color values, Hard Light either multiplies or screens the foreground image's color values. The result is akin to aiming a harsh spotlight at the image. Color Dodge: Color Dodge draws on the foreground's color values to brighten the background image. This parallels the photographic trick of dodging, where exposure across a region of a print is cut back. Color Burn: Color Burn draws on the foreground's color values to darken the background image. This parallels the photographic trick of burning, where exposure across a region of a print is increased. Darken: Darken examines the color information in each channel and picks whichever color value — the background's or the foreground's — runs darker as the result color. Pixels lighter than the merged colors get replaced, while pixels darker than the merged color hold steady.

Lighten: Lighten examines the color information in each channel and picks whichever color value — the background's or the foreground's — runs lighter as the result color value. Pixels darker than the merged color get replaced, while pixels lighter than the merged color hold steady. Difference: Difference looks at each channel's color information and, depending on whichever carries the greater brightness value, takes the foreground color values away from the background ones — or the background away from the foreground. Merging against white inverts the color. Merging against black leaves it unchanged. Exclusion: Exclusion yields an effect much like the Difference mode but lower in contrast. Merging against white inverts the base color values. Merging against black leaves it unchanged. Hue: Hue builds a result color out of the luminance and saturation of the background color values together with the hue of the foreground color values. Saturation: Saturation builds a result color out of the luminance and hue of the base color together with the saturation of the blend color. Color: Color builds a result color out of the luminance of the background color value together with the hue and saturation of the foreground. It keeps the image's gray levels and proves handy for coloring monochrome images. Luminosity: Luminosity builds a color out of the hue and saturation of the background color together with the luminance of the foreground color. This mode produces the inverse of what the Color mode does.

- Operator Modes: Selecting the merge's Operation Mode is what this menu is for. It settles how the foreground and background get combined to yield a result. You'll only see this drop-down menu while the Merge node's Apply Mode sits at either Normal or Screen.

NOTE: Should you want an outstanding account of the math that drives the Operation modes, the source to read is "Compositing Digital Images" — a paper credited to Porter, T., and T. Duff that ran in the SIGGRAPH 84 proceedings, across pages 253-259. In essence, the math runs as laid out below.

TIP: A handful of modes absent from the Operator drop-down menu (Under, In, Held In, Below) come easily by swapping the foreground and background inputs and selecting a matching mode. Combining pixels in the merge always follows the formula fg _ x + bg _ y. Which values x and y take is what the different operations decide, as the description for each mode lays out. The Operator modes run as follows:

- Over: The Over mode lays the foreground layer atop the background layer by swapping the

background pixels for the pixels from the Z wherever the foreground's alpha channel exceeds 1. x = 1, y = 1-[foreground Alpha]

- In: The In mode multiplies the background input's alpha channel against the foreground pixels. The foreground input's color channels go ignored. Only foreground pixels reach the final output. This in effect clips the foreground using the background's mask.

x = [background Alpha], y = 0

- Held Out: Held Out is in essence the reverse of the In operation. Here the pixels of the foreground image get multiplied by the background image's inverted alpha channel. The identical outcome is reachable through the In operation paired with a Matte Control node that inverts the matte channel of the background image.

x = 1-[background Alpha], y = 0

- ATop: ATop sets the foreground over the background only where the background carries a matte.

x = [background Alpha], y = 1-[foreground Alpha]

- XOr: XOr joins the foreground with the background wherever either the foreground or the background carries a matte, yet never where both carry one.

x = 1-[background Alpha], y = 1-[foreground Alpha]

- Subtractive/Additive: Whether Fusion runs an Additive merge, a Subtractive merge, or some blend of the pair is governed by this slider. For most operations the slider defaults to Additive merging, on the assumption that the input images are premultiplied (as they usually are). Should the gap between Additive and Subtractive merging be unclear to you, here's a brief rundown:
- An Additive merge is called for when the foreground image is premultiplied, meaning that within the color channels the pixels have already been multiplied by those of the alpha channel. The upshot is that transparent pixels stay black at all times, since anything multiplied by 0 always comes to 0. This hides the background (through multiplication with the inverse of the foreground alpha), then merely adds the foreground pixels on top.
- A Subtractive merge is called for if the foreground image isn't premultiplied. The compositing method mirrors an Additive merge, except the foreground image gets multiplied by its alpha first to wipe out any background pixels lying outside the alpha area. Across most software applications, you'll see the Additive/Subtractive option shown as a plain checkbox. Fusion lets you blend across the Additive and Subtractive variants of the merge operation, which now and then helps with troublesome composites whose edges draw the eye for reading too bright or too dark.

To take an example, applying a Subtractive setting to a premultiplied image can leave you with darker edges. Applying an Additive setting to a non-premultiplied image can lighten the edges. By blending across Additive and Subtractive, you can dial the edge brightness in until it's exactly right for your situation. Filter Method (Match Move) Settles which filter handles image transforms produced through the Tracker node. This menu shows up only while the Operation Mode is set to Match Move.

- Box: A plain interpolation-based resize of the picture.
- Linear: Relies on a bare-bones filter that turns out fairly clean, quick results.
- Quadratic: Yields a middling result from this filter. Between

speed and quality it strikes a fair balance.

- Cubic: Yields stronger results on continuous-tone pictures, though it runs slower than Bi‑Cubic.

Where the pictures hold fine detail, the outcome can come out blurrier than you'd want.

- Catmull-Rom: Yields solid results on continuous-tone pictures scaled down.

On finely detailed pictures it turns out sharp results.

- Gaussian: Sits very close to Bi-Cubic in both speed and quality.
- Mitchell: Resembles Catmull-Rom yet turns out stronger results on finely detailed pictures. Compared to Catmull-Rom it runs slower.
- Lanczos: Sits very close to Mitchell and Catmull-Rom, just a touch cleaner and a touch slower as well.
- Sinc: A high-end filter delivering exceptionally sharp, detailed results; that said, it can throw

visible "ringing" under certain conditions.

- Bessel: Resembles the Sinc filter though it may run a shade faster.

Edges Which way the revealed edges get treated, once the image has shifted to match position and scaling, is what this menu picks.

- Black Edges: Whatever out-of-frame edges Stabilization exposes are left black.
- Wrap: Whatever stretches of the image get pushed off frame on one side go toward filling the edges exposed

on the opposite side.

- Duplicate: The final valid pixel along an edge gets repeated outward to the frame's edge.
- Mirror: To fill out to the frame's edge, the image's pixels are mirrored.

Position, Rotation, and Scaling Checkboxes (Match Move) This trio of checkboxes surfaces only while the mode sits at Match Move. They settle which components of motion Stabilization will try to correct in the image. As one case, when nothing but the Position checkbox is ticked, no attempt is made at fixing the image's Rotation and Scaling. Flatten Transformation (Match Move) This particular checkbox surfaces only while the mode rests at Match Move. As with most transformations in Fusion, Stabilization concatenates with other sequential transformations by default. Ticking this checkbox flattens the transform, severing any concatenation under way and applying the transform right away. Mapping Type The Mapping Type control surfaces only within the Corner Positioning mode. Two options sit in the menu:

- Bi_Linear: The first approach is Bi-Linear, where the foreground image maps into the background with no effort made to correct for perspective distortion. This matches how earlier versions of Fusion behaved.
- Perspective: The foreground image maps into the background while accounting for perspective distortion. This is the preferred setting, since it maps to the real world better than the older Bi‑Linear setting does.

Corner Selector (Corner or Perspective Positioning) The moment the Tracker's operation lands on either Corner or Perspective Positioning modes, four drop-down menus surface. These options pick which trackers map onto each of the rectangle's four corners. This proves handy when a Tracker has more than four patterns selected and you must decide which patterns the positioners draw on. Rotate Clockwise and Counter-Clockwise Buttons (Corner or Perspective Positioning) Only when the Tracker's operation has been pointed at either Corner or Perspective Positioning modes do these controls surface. Their job is to spin the foreground image by 90 degrees before it's laid onto the background.

Stabilize Settings The Tracker node automatically puts out several steady and unsteady position outputs that other controls in the Node Editor can be wired to. The Stable Position output supplies X and Y coordinates for matching or reversing motion across a sequence. These controls stay available even where the operation isn't set to Match Move, since the Stable Position output is forever on hand for connection to other nodes.

### Match Move Settings

What these settings settle is how the tracking data gets correlated with the reference pattern when making transforms. Pivot Type What the Pivot type menu settles is how the anchor point for rotation gets chosen.

- Tracker Average: Averages the location out of the tracking points.
- Selected Tracker: Offers a menu where one of the current trackers can be picked

as the pivot point.

- Manual: Shows X and Y position number fields in which you can place the pivot points by hand.

Reference What the Reference mode settles is the "snapshot frame," based on the frame where the pattern first gets selected. Every bit of Stabilization aims to return the image back to that reference.

- Select Time: Lets you pick the current frame.
- Start: The Snapshot Frame is taken to be the first frame in the tracked path. Every bit of Stabilization

aims to return the image back to that reference.

- Start and End: The Start and End Reference mode departs somewhat from all the other Reference

modes. Where the others mean to grab a snapshot frame that all stabilization returns to, freezing the image in place, the Start and End mode means to smooth out existing motion without stripping it away. This mode averages the motion running between the Start and End of the path, tracing a straight line across those points. With this mode active, it exposes the Reference Intermediate Points control. Raising this control's value raises the count of points along the path that the Reference draws on, smoothing the motion away from a straight line between Start and End without rendering it wholly linear.

- End: The Snapshot Frame is taken to be the last frame in the tracked path. Every bit of Stabilization aims to return the image back to that reference.

TIP: Out of the box, within the Spline Editor the Tracker shows just one displacement path for the tracked data. Should you want the tracked points' X and Y paths shown in that same editor, head to Preferences > Globals > Splines.

### Display Options Tab

What the Display Options tab lets you do is shape the look of the onscreen controls in the viewer.

### The Tracker Display Options tab

Show Pattern Names What this option defines is whether the Tracker's pattern names show up in the viewer. Switch it off to view the pattern rectangle instead. Enlarged Pattern on Dragging What this option defines is whether a magnified thumbnail view appears while you position the pattern rectangle. Enlargement Scale The zoom factor put to use when positioning the pattern rectangle once the above option is switched on. TIP: Scripts may likewise tap a tracker's outputs (the ones shown within the Connect to… menu). The full roster runs as follows. First the overall position and axis outputs: SteadyPosition: Steady Position UnsteadyPosition: Unsteady Position SteadyAxis: Steady Axis. Then the size and angle outputs: SteadySize: Steady Size UnsteadySize: Unsteady Size SteadyAngle: Steady Angle UnsteadyAngle: Unsteady Angle. Next, the outputs tied to an individual tracker: Position1: Tracker 1 Offset position PerspectivePosition1: Tracker 1 Perspective Offset position. After those come the axis-resolved entries — PositionX1: Tracker 1 Offset X position (3D Space) PositionY1: Tracker 1 Offset Y position (3D Space) PerspectivePositionX1: Tracker 1 Perspective Offset X position (3D Space) PerspectivePositionY1: Tracker 1 Perspective Offset Y position (3D Space). Rounding out the set are the steadiness entries: SteadyPosition1: Tracker 1 Steady Position UnsteadyPosition1: Tracker 1 Unsteady Position (the same pattern carries on for the 2nd, 3rd, and onward)

### Common Controls

Settings Tab The Settings tab in the Inspector also has a duplicate in other Tracking nodes. These common controls get a full description toward the end of this chapter under "The Common Controls" section.

### The Common Controls

Several identical controls in the Inspector are shared by nodes that carry out tracking operations. The controls common across Tracking nodes are described in this section.

### Inspector

### The Common Tracking Controls Settings tab

### Settings Tab

Every tool in the Tracking category carries the Settings tab in the Inspector. The controls stay consistent and behave the same way from one tool to the next.

Blend The Blend control mixes between two things: the image the tool took in to begin with and the finished, altered image the tool puts out. With the blend value at 0.0, the outgoing image matches the incoming image. Ordinarily this leads the tool to bypass processing altogether, copying the input straight through to the output. Process When Blend Is 0.0 The tool runs its processing even when the input value sits at zero. This can come in handy if the node is scripted to fire off a task while the node's value rests at 0.0. Red/Green/Blue/Alpha Channel Selector These four buttons serve to confine the tool's effect to particular color channels. This filter typically gets applied after the tool has finished processing. To give an example, if the Red button on a Blur tool is switched off, the blur gets applied to the image first, and then the red channel from the original input is copied back over the result's red channel. There are a few exceptions, such as tools where switching these channels off makes the tool skip processing that channel outright. Tools that behave this way will generally carry a set of identical RGBA buttons on the Controls tab within the tool. Here the buttons on the Settings and the Controls tabs are one and the same. Apply Mask Inverted Switching the Apply Mask Inverted option on inverts the tool's complete mask channel. The mask channel is the pooled result of every mask wired into or generated within a node. Multiply by Mask Picking this option makes the masked image's RGB values get multiplied by the mask channel's values. As a result, any image pixel the mask excludes (in other words, set to 0) goes black/transparent. Use Object/Use Material (Checkboxes) Certain 3D software is able to render into file formats supporting extra channels. The EXR file format notably supports Object ID and Material ID channels, which can serve as a mask for the effect. These checkboxes settle whether those channels get used, where present. Which specific Material ID or Object ID is affected gets chosen through the next set of controls. Correct Edges This checkbox surfaces only once the Use Object or Use Material checkboxes are ticked. It flips the method used to deal with the overlapping edges of objects within a multi-object image. With it switched on, the Coverage and Background Color channels serve to separate and sharpen the effect around the object's edge. With this option switched off (or where neither Coverage nor Background Color channels are present), the mask's edge may show aliasing. To read further about the Coverage and Background Color channels, turn to Chapter 78, "Understanding Image Channels," within the DaVinci Resolve Reference Manual, or to Chapter 18 of the Fusion Reference Manual.

Object ID/Material ID (Sliders) Turn to these sliders to pick which ID will build a mask out of the object or material channels of an image. Put the Sample button to work the same way you would the Color Picker: to lift IDs off the image shown in the viewer. The image or sequence must have come out of a 3D software package with those channels rendered in.

### Motion Blur
