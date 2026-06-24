# Matte Nodes (part 5)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

What appears here is the color picked up (or registered) through scrubbing in the viewer with the Fine Tuning tab active. Fine Tuning Sliders The scrubbed pixel’s color is logged as a reference color for fine tuning and turns up in the Color swatch. To carry out the tuning, sample a color region within the image and nudge one of the Fine Tuning sliders until you get the look you want. Spill The Spill slider serves to strip spill out of the chosen color region. Push the slider rightward and more spill comes off; pull it leftward and the color component of the chosen region edges nearer to the hue in the original foreground image. Should pushing the slider right fail to clear the spill, resample the color region and move it once more. The slider’s effects accumulate. Whatever you achieve by dragging the slider right is equally reachable by clicking on the color region in the Spill(-) operational mode. Transparency The Transparency slider lends the matte more translucency across the chosen color region. Drag it right and the chosen color region grows more transparent; drag it left and the matte turns more opaque. If a rightward drag doesn’t make the color region translucent enough, resample the region and drag right again. These slider effects build up. The same outcome from dragging right is also had by clicking on the color region in the Matte(-) operational mode. Detail The Detail slider serves to bring back lost detail. With a color region chosen, dragging this slider left renders that region more visible, while dragging it right renders it less so. If a leftward drag doesn’t make the region visible enough, resample it and drag left once more. The slider’s effects are cumulative. That same result from dragging left can equally be had by clicking on the color region in the Detail(-) operational mode.

### The Primatte Replace tab

### Replace Tab

From the Replace tab you can pick among the three color spill replacement methods detailed earlier in the Spill Sponge section. Three choices govern the replacement color as spill is removed, and you set them through the Replace mode menu.

### Replace Mode

- Complement: Swaps the spill color out for the complement of the screen color. This mode preserves delicate foreground detail and yields the finest results. Where foreground spill isn’t much of an issue, this is the mode to reach for. When the spill on the foreground image runs fairly heavy, though, this mode will frequently push noticeable noise into the finished composite.
- Image: Swaps the spill color for hues drawn from a defocused version of the background image, or from the Replace image when one is wired into the node’s Replace input (magenta ). This mode lands a pleasing color tone on the foreground subject even against a high-contrast background. The downside is that Image mode now and then forfeits the fine edge detail of the foreground subjects. Trouble can also arise if you afterward resize the foreground image relative to the background: because the background/foreground alignment shifts, the color tone borrowed from the defocused image may no longer line up.
- Color: Swaps the spill color for a single solid color. Pick this option and a color swatch alongside R,G,B sliders appears for choosing that color. By adjusting the palette color of the solid replacement, you can land on a good spill replacement that harmonizes with the composite background. Its merit is that it copes well even under severe spill. The drawback is that, in Solid Color Replacement mode, fine detail along the foreground edge is apt to vanish. A lone palette color sometimes can’t produce a pleasing tone when the background image contains some high‑contrast color areas.

### The Primatte Degrain tab

### Degrain Tab

Turn to the Degrain tab when a foreground image is badly marred by film grain. Because of that grain, once backing screen noise has been wiped out entirely, the foreground object’s edges often turn harsh and jagged, producing a poor key. Grain Size The Grain Size selector offers a span of grain removal running from Small to Large. When the foreground image carries a heavy load of film grain-induced pixel noise, you risk losing a clean edge on the foreground object while attempting, via the Clean Background Noise Operation Mode, to scrub every bit of grain noise away. These tools tidy up the grain noise while leaving the key’s quality intact.

- None: Degraining doesn’t happen at all.
- Small: The averaged color taken from a small patch surrounding the sampled pixel. Reach for this

when the grain is very dense.

- Medium: The averaged color taken from a medium-sized patch surrounding the sampled pixel. Reach

for this when the grain is less dense.

- Large: The averaged color taken from a wider patch surrounding the sampled pixel. Reach for this

when the grain is very loose. Grain Tolerance Moving this slider boosts how strongly the Clean Background Noise tool works while leaving the foreground object’s edge untouched.

### The Primatte Matte tab

### Matte Tab

The Matte tab polishes the key’s alpha, folding in whatever solid and garbage masks are wired to the node. While you work the Matte tab, set the viewer to show the alpha channel of Primatte’s final output. Filter This control picks the filtering algorithm that gets applied when blur is added to the matte.

- Box: The quickest option, though at lower quality. Box fits best where only a little blur is needed.
- Bartlett: Also called a Pyramid filter, Bartlett strikes a sound balance between speed and quality.
- Multi-Box: Choose this filter and the Num Passes slider shows up so you can dial in the quality. At 1 and 2 passes the output matches Box and Bartlett respectively. From 4 passes upward, output tends to rival Gaussian, in less time and free of edge “ringing.”
- Gaussian: The Gaussian filter applies a genuine Gaussian approximation and produces excellent output, though it runs a touch slower than the rest. On occasion it can leave an extremely faint edge “ringing” on floating-point pixels.

Blur Matte Blur softens the matte’s edge according to whatever the Filter menu is set to. Set it to zero and you get a crisp, cutout-style hard edge; raise the value and more blur spreads across the matte. Blur Inward Switch on the Blur Inward checkbox and the blur is cast toward the foreground subject’s center. Ordinary blurring or defocus works on the matte edges in both directions (inward and outward) and at times leaves a halo artifact ringing the edge in the composite view. Blur Inward, by contrast, acts solely toward the inside of the foreground subject (in toward the center of the white area). The end result clears small dark noise from the screen area without it being grabbed again in the Clean Background Noise mode. Now and then it yields softer, cleaner edges on the foreground objects.

Contract/Expand This slider tightens or enlarges the semitransparent zones of the matte. Push it above 0.0 to expand the matte; drop it below 0.0 to contract it. You’ll typically pair this control with the Matte Blur to soften a matte’s hard edge and cut down fringing. Because it acts only on semitransparent zones, it leaves a matte’s hard edge alone. Gamma Matte Gamma pushes the matte’s values up or down within the semitransparent zones. Higher settings make the gray areas more opaque; lower settings make those gray areas more transparent. Fully black or fully white parts of the matte stay put. Acting only on semitransparent zones, it has no bearing on a matte’s hard edge. Threshold This range slider fixes the lower threshold with the left-hand handle and the upper threshold with the right-hand one. Anything under the lower threshold turns black or transparent in the matte, and anything over the upper threshold turns white or opaque. Everything in between keeps its relative transparency. The control sees frequent use for rejecting salt and pepper noise in the matte. Restore Fringe This brings back the matte’s edge around the keyed subject. Keying often clips out the subject’s edge wherever there’s hair; Restore Fringe returns that edge while keeping the matte solid. Invert Matte Tick this checkbox and the alpha channel the keyer made is flipped, so every transparent area turns opaque and every opaque area turns transparent. Solid Matte Solid mattes are mask nodes or images wired into the node’s solid matte input. A solid matte is laid straight onto the image’s alpha channel. As a rule, solid mattes hold out keying in regions meant to stay opaque — think of someone with blue eyes shot against a blue screen. Switching on Invert flips the solid matte ahead of its merge with the source alpha. Garbage Matte A garbage matte is itself a mask node or image wired into the node’s garbage matte input. A garbage matte too is laid straight onto the image’s alpha channel. As a rule, garbage mattes strip out unwanted things that can’t be keyed, such as microphones and booms. They also patch in regions that hold the keyed color yet need to be preserved. You can’t blend garbage mattes of differing modes inside one tool. A Matte Control node is frequently placed after a Keyer node to introduce a garbage matte that does the reverse of the matte fed to the keyer. Switching on Invert flips the garbage matte before it merges with the source alpha. Post-Multiply Image Pick this option and the keyer multiplies the image’s color channels against the alpha channel it builds for that image. It’s normally switched on and enabled by default.

Clear this checkbox and the image stops counting as premultiplied when you go to merge it with others. In that case reach for the Subtractive option of the Merge node rather than the Additive one. To read more about these Merge node settings, consult Chapter 95 ("Composite Nodes") of the DaVinci Resolve Reference Manual, or else Chapter 35 within the Fusion Reference Manual.

### Common Controls

Settings Tab The Inspector’s Settings tab is mirrored across the other Matte nodes as well. You’ll find these shared controls spelled out in full at this chapter’s close, under the “The Common Controls” section.

### How to Key with Primatte

To start keying with Primatte, wire the blue- or green-screen shot into the orange foreground input of the Primatte node and route the composite’s background shot into the green background input. With the connections set, working the Primatte breaks down into four core steps, in order: 1 Select Background Color, then 2 Clean the Background Noise, then 3 Clean the Foreground Noise, and finally 4 Remove Spill. Selecting Background Color 1 Within the Inspector, press the Select Background Color button. 2 Hover the mouse pointer over the blue/green-screen region in the viewer, somewhere close to the foreground subject. 3 Drag across the background color. Primatte averages the pixels down to one color. There are times when Primatte performs best on a single sampled pixel rather than a span of them. If your keying is giving you trouble, run Select Background Color again on one dark screen pixel or one light screen pixel. Alternatively, to make a rectangular selection, use the Box button up in the viewer’s top left-hand corner. The Median button behaves like Line selection, save that every sampled point comes from a 3 x 3 region centered on your click that then has a median filter applied. This can help trim down any noisy pixels.

### Primatte viewer buttons

When the foreground image holds a shadow you’d like preserved in the composite, steer clear of selecting any of the dark screen pixels inside that shadow. Doing so keeps the shadow bundled with the rest of the foreground image.

### Clean Background Noise

Any white or light gray patches sitting in the dark screen area get the name “noise.” In practice it’s assorted shades of the screen color that the first sample missed and that ought to come out. Background noise is cleared by way of the Clean Background Noise button. 1 Within the Inspector’s View Mode menu, pick Black. 2 Over the viewer, press the Alpha Channel/RGB button. The displayed picture switches to a black-and-white “matte” rendition. 3 Press the Clean Background Noise button. 4 Drag the mouse pointer across the white or light gray patches that should read as pure black. Primatte works through the selection and strips the noise away. 5 Run this procedure as many times as it takes to rid the background areas of noise. Choosing Gain/Gamma from the viewer’s Options menu to lift brightness or gamma reveals noise that would otherwise stay hidden.

### Primatte viewer Options menu

Good results don’t hinge on clearing out every last white pixel. In a key image, most pixels shown as a dark near-black color count as transparent and effectively let the background stand as the final output there. So there’s no call to wipe out all the noise across the screen portions of the image. Indeed, trying to scrub noise away too meticulously around the foreground subject often makes a smooth composite hard to achieve. TIP: While clearing noise from around loose, flying hair or any background/foreground transitional zone, take care not to grab any of the areas hugging the hair’s edge. Leave a touch of noise around the hair, since the Fine Tuning tools can deal with it later.

### Clean Foreground Noise

Dark patches sitting amid the largely white foreground subject mean the key isn’t 100% in those spots. Clean Foreground Noise can drive the matte as white as it will go. 1 Leave the View Mode menu on Black and the viewer on the Alpha Channel. 2 Press the Clean Foreground Noise button. 3 Drag the mouse pointer across the dark foreground pixels that ought to be pure white. Primatte works through the selection and strips the noise away. 4 Run this procedure as often as it takes to clear noise from the foreground areas. 5 If it’s on, switch off Gain/Gamma in the viewer’s Options menu to get back to a normal viewer.

### Removing Spill

Those first three sections produced a clean matte. From here, the foreground is ready to be composited over any background image. Yet if color spill clings to the foreground subject, one last step is needed to clear that screen spill and yield a more natural-looking composite. 1 From the View Mode menu, pick Composite. 2 Over the viewer, press the Alpha/RGB toggle button to view the RGB image. Primatte offers two routes for removing the spill color: Spill Sponge: The fastest is to press the Spill Sponge button and then sample the spill regions away. You can take out further spill with the tools under the Fine Tuning tab or via the Spill(-) button. Fine Tuning Tab: To work spill through the Fine Tuning tab, begin by scrubbing over the spill color in the viewer. On most images, tweaking the Spill slider is all it takes to clear whatever spill is left. NOTE: When the Fine Tuning tab’s slider is used to remove spill, spill color replacement follows whatever the Spill Replacement options are set to. The remaining two sliders serve the same way for other key adjustments. The Detail slider governs matte softness for the color sitting nearest the background color. As an example, you can salvage lost wispy smoke in the foreground by entering Fine Tuning mode, clicking where the smoke begins to fade out, and dragging the Detail slider left. The Transparency slider governs matte softness for the color sitting nearest the foreground color. For instance, with thick opaque smoke in the foreground, you can render it semitransparent by dragging the Transparency slider right after selecting the pixels in Fine Tuning mode.

### Relight [RLT]

### The Relight node

### Relight Node Introduction

Relight lets you drop light sources into your scene, lighting the objects there in a believable way. Whereas a plain shape node carries a polygon pinned to the screen, Relight studies the forms of people and objects to build a Surface Map and leans on that map to bounce light correctly. Tuned well, the effect conjures the impression of light tracing an object’s curves, glinting off highlights and fading away into shadow. Relight earns its keep when you wish there’d been an extra light on set, when you want to play up an existing light so it matches another shot, or when you’re after more convincing day-for-night grading.

NOTE: Though the Relight effect fabricates a sense of depth by analyzing a scene’s surfaces, it stops short of computing the 3D relationships among the scene’s objects. Shapes can’t be set to throw shadows, and no depth information gets generated.

For more information on Relight, see Chapter 162, “Resolve FX Refine.”

### Inputs

Three inputs feed the Relight tool. Input: The orange input takes the primary footage you intend to relight. Effect Mask: A mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps produced by other tools is what the optional blue effect mask input accepts. Wiring a mask here confines the filter to nothing but the pixels inside that mask. An effects mask gets applied to the tool only after the tool has been processed. Normals: The green input lets you attach an externally created normal maps in place of the one the Relight tool makes on its own.

### Basic Node Setup

Putting the Relight tool to work means assembling some extra node structure around it. Beyond the usual MediaIn node, you’ll want a Merge node plus another effect such as the ColorCorrector or Brightness/Contrast tools.

- MediaIn: The MediaIn node’s output feeds the orange inputs of the Relight, the ColorCorrector (or whatever effect node you use), and the Merge node.
- ColorCorrector (effect): Takes its input from the MediaIn node, and its output runs into the Merge node’s green foreground input.
- Relight: Takes its input from the MediaIn node, and its output runs into the Merge node’s blue effect mask input. Set this node to show in whichever viewer you prefer.
- Merge: Pulls its background input from the MediaIn node, its green foreground input from the ColorCorrector, and its blue effect mask input from Relight. From there its output carries on to the rest of the node tree or to media out. Set this node to show in whichever viewer you prefer.

The node tree laying out the node structure that surrounds the Relight tool. Bear in mind the ColorCorrector can give way to any other effect you favor.

Once the node structure above is in place, you ought to see something close to the arrangement shown below. Viewer 1 carries the finished relight effect that moves on to the rest of the node tree. Viewer 2 holds the relight interface, where you can drag the lighting position around the frame. Which form it takes depends on your Relighting Map Preview option — either a black-and-white embossed image or the RGB image atop a semi-transparent background.

On the left, Viewer 1 shows the Merge node; on the right, Viewer 2 shows the Relight node, with both groups of on-screen controls switched on.

### Inspector

### The Relight controls

### Controls

The Controls give you the run of every parameter on the Relight tool. The viewer carries extra on-screen controls too, which vary with the kind of Relight effect you pick. To learn more about working the Relight controls, turn to Chapter 162, “Resolve FX Refine.”

- Surface Map: This sets which mode you’ll use to build the Surface Map. Use Internal: Builds the Surface Map within the tool itself. Use Normals Input: Pulls in an externally created Surface Map from another node. Wire that map into the green input of the Relight node.
- Output Surface Map: Ticking this box makes this copy of the effect put out a multi-colored map of the input frame. That Surface Map can afterward feed a second Relight node where you place and tune the light sources.
- Directional / Point Source / Spotlight: Directional: Makes a light source casting from one specific direction at infinite distance. Point Source: Makes a light source casting outward from a central point. Spotlight: Is likewise a point source, only aimed into a cone shape.
- Relighting Map Preview: Ticking this box exposes the Alpha channel of this light’s effect. Clearing it shows the current image instead, with the light mask sitting in the Alpha channel. The Map Preview’s bright areas mark where the Relight is acting on the image.

A car image shown with the Map Preview box ticked. The brighter zones reveal where and how strongly the Relight tool acts on the image.

### Light Properties

- Brightness: This governs how strongly whatever grading applied to the scene comes through. It introduces no brightness shifts by itself but magnifies the ones you dial in with the grading tools.
- Reach: This governs how steeply reflections fade as distance from the light source grows.
- Contrast: This sets how abrupt or gentle the gradient running between light and dark turns out.

### Surface Properties

- Glossiness: Lends reflective surfaces the impression of a metallic sheen.
- Specularity: Once any glossiness is present, this dictates how metallic/shiny that glossiness reads.
- Shadow Softness: Dictates how far the light reaches into shadows by way of ambient reflections, past where it would otherwise land.

Light Direction (Directional only)

- Azimuth/Elevation XY : Dictates the direction from which the light arrives.

Spotlight (Spotlight only)

- Beam Angle: Sets how wide the cone of light spreads. This control can also be handled graphically within the viewer.
- Edge Softness: Sets how soft the edges of the light cone/beam appear. Light Position (Point Source and Spotlight).

Light Position (Point and Spotlight only)

- These controls handle the position of the light emitter for the Point and Spotlight types. You can set them right here, though it’s usually easier to do so graphically by means of the Viewer controls.

### External Map

- Rescale Oversaturated: Different software scales the Surface Map differently. One widespread format resembles the Relight plugin’s own internal maps but with the colors heavily saturated, sometimes turning dark or black in places. Should your imported surface map look like this, tick this box to re-interpret it.
- Reinterpret Left/Right: Tick this box to flip the orientation of your external surface map when its surfaces read as concave rather than convex.
- Reinterpret Up/Down: Tick this box to flip the orientation of your external surface map when its surfaces look lit from beneath even though the light sits above them.

### Ultra Keyer [UKY]

### The Ultra Keyer node

### Ultra Keyer Node Introduction

As with the newer Delta Keyer, the Ultra Keyer node packs two keyers inside it: a pre-matte keyer that works as a garbage matte creator and a color difference keyer that pulls out fine detail and transparency. As a rule, you’d open with the Delta Keyer as your first pick. Should that fall short, give Primatte a go if you’re on Fusion Studio. The Ultra Keyer makes a solid third option.

### Inputs
