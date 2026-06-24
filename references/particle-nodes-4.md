# Particle Nodes (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Randomize The Random Seed slider together with the Randomize button show up any time a Fusion node leans on a random outcome. Feed two nodes the same seed values and they will turn out matching random results. Hit the Randomize button to have a new seed value drawn for you at random, or work the slider to choose a new seed value yourself. X, Y, and Z Strength The Strength control governs how much chaotic motion gets pushed onto the particles. Strength Over Life This mini Spline Editor control lets you steer how much turbulence hits a particle based on its age. A fire particle, say, might begin its life with barely any turbulence, then see that turbulence grow as it gets older. Density Reach for this control to tune how dense the turbulence field is. Smaller numbers make more particle cells respond alike, as though “waves” of the turbulence field swept through the particles and moved batches of cells together. Larger numbers introduce finer variation across more individual particle cells, spreading the turbulence field out further.

### Common Controls

Conditions, Style, Region, and Settings Tabs Because the Conditions, Style, Region, and Settings tabs are shared across every Particle node, you will find what they do described in “The Common Controls” section at this chapter's close.

### pVortex [pVt]

The pVortex node pVortex Node Introduction The pVortex node lays a rotational force on every particle, pulling them in toward the Vortex's source. On top of the Common Particle Controls, the pVortex node carries these controls as well.

### Inputs

Out of the box the pVortex node shows one orange input. As with most particle nodes, that orange input will accept nothing but other particle nodes. A green bitmap or mesh input materializes on the node once you switch the Region tab's Region menu to either Bitmap or Mesh. Input: The orange input receives the output coming from other particle nodes. Region: The green or magenta region input receives a 2D image or a 3D mesh, depending on whether the Region menu reads Bitmap or Mesh. Which color the input takes follows whichever you picked first in the menu. The 3D mesh, or a channel you select from the bitmap, marks out the vortex's area.

### Basic Node Setup

You drop the pVortex node between the pEmitter and pRender nodes. A pVortex node sets up a spiraling motion for whichever particles land inside its pull.

### Inspector

### The pVortex controls

Randomize Whenever a Fusion node depends on a random outcome, both the Random Seed slider and the Randomize button appear. Hand two nodes identical seed values and the random results they yield will match. Press the Randomize button for a randomly drawn seed value, or drag the slider to set a seed value by hand. Strength This control fixes the Strength of the Vortex Force that lands on each particle. Power This control fixes how steeply the Strength of the Vortex Force tapers off with distance. X, Y, and Z Offset Work these sliders to dial in how far the vortex Offsets the particles it affects. Size This sets the Size of the Vortex Force. Angle X and Y These sliders govern how much rotational force the Vortex exerts along the X and Y axes.

### Common Controls

Conditions, Style, Region, and Settings Tabs Since the Conditions, Region, and Settings tabs are shared by all Particle nodes, descriptions of them live in the “The Common Controls” section that follows.

### The Common Controls

A whole set of identical controls turns up in the inspector across the particle nodes. This section walks through the Style, Conditions, Region, and Settings tabs that those nodes hold in common.

### Inspector

### The pEmitter Style tab

### Style Tab

The Style Tab is shared by the pEmitter, pSpawn, pChangeStyle, and pImage Emitter. Through broad controls such as type, size, and color, it dictates how the particles look.

### Style

The Style menu opens up the assorted particle types the Particle Suite supports. Every style carries controls of its own plus controls it holds in common with other styles.

- Point: This choice yields particles exactly one pixel across. Two controls belong to Point Style alone: Apply Mode plus Sub Pixel Rendered. Apply Mode: This menu bears only on 2D particles; 3D particle systems go untouched. It offers Apply modes for Add and Merge. Add fuses overlapping particles by summing each one's color values. Merge fuses overlapping particles with a plain over operation. Sub Pixel Rendered: This checkbox sets whether the point particles render at Sub Pixel precision, which yields smoother-looking motion at the cost of blurrier particles that take a touch longer to render.
- Bitmap: This style builds particle cells off an image file or another node in the Node editor. Selecting it makes an orange image input show up on the node in the node editor. A handful of controls govern the look and animation. Beyond the Style section's controls, picking Bitmap as the Style brings a Merge section to the foot of the inspector. That Merge section holds controls for additive or subtractive merges wherever the particle cells overlap.

Animate Over Time: This menu carries three options that set how movie files play once pressed into service as particle cell bitmaps. The Over Time setting runs the movie file in order. So when the comps sits on frame 2, frame 2 of the movie file shows; when the comp sits on frame 3, frame 3 of the movie files shows; and onward. Should a particle cell not come into being until frame 50, it opens on frame 50 of the movie file. What follows is that, on any give frame of the comp, all the particle cells draw the identical image. The Particle Age setting has each particle cell open on the movie file's first frame, no matter when that cell was born. The Particle Birth Time setting has each particle open on the frame that lines up with its own particle cell birth time. So if the particle comes into being on frame 25, it sticks with frame 25 of the movie file across the whole comp. Setting it apart from the other two, the Particle Birth Time setting holds one frame for the length of the comp Time Offset: This dial slides or offsets which starting frame is taken from the movie file. As an example, putting it at 10 makes the movie file open on frame 10 rather than frame 1. Time Scale: This slider acts as a multiplier on the frame. Rather than offsetting, it shifts the starting frame by multiplying the frame by the value you pick with the slider. As an example, with a value of 2 chosen, the moment the playhead hits frame 2, the movie files shows frame 4 (2x2=4), and the moment the playhead hits frame 8, the movie file shows frame 16 (8x2=16). Gain: The gain slider acts as a multiplier on the pixel value. Its job is to correct the overall Gain of the Bitmap. Suppose you have a bitmap particle cell carrying a pixel value of R0.5 G0.5 B0.4 and you apply a Gain of 1.2; you wind up with a pixel value of R0.6 G0.6, B0.48 (i.e., 0.4 \* 1.2 = 0.48) while black pixels stay put. Bigger numbers brighten the image, while smaller ones cut both its brightness and its transparency. Style Bitmap: This control surfaces when the Bitmap style is chosen, and an orange Style Bitmap input joins the node's icon over in the Node view. Wire a 2D node into this input to feed the images the particles will use. You can do that within the Node view; alternatively, drop the image source node onto the Style Bitmap control out of the Node Editor or Timeline, or right-click the control and pick the source you want from the Connect To menu.

- Blob: This choice yields big, soft, spherical particles and comes with controls for Color, Size, Fade timing, Merge method, and Noise.

Noise: This slider bears only on 2D Blob particles. Its purpose is to inject a computer-generated Perlin noise pattern into the blob particles so the blobs gain more texture. At a setting of 0 no noise reaches the Blob particles, and at a setting of 1 the noise is at its maximum.

- Brush: This style builds particle cells off whatever image file sits in the brushes directory. Plenty of controls govern the look and animation.

Gain: The gain slider acts as a multiplier on the pixel value. Its role is to correct the overall Gain of the image serving as the Brush. Suppose you have a brush particle cell carrying a pixel value of R0.5 G0.5 B0.4 and you apply a Gain of 1.2; you wind up with a pixel value of R0.6 G0.6, B0.48 (i.e., 0.4 \* 1.2 = 0.48) while black pixels stay put. Bigger numbers brighten the image, while smaller ones cut both its brightness and its transparency. Brush: This menu lists the names of whatever image files reside in the Brushes directory. Where the Brushes directory lives is set in the Preferences dialog, under Path Maps. By default that is the Brushes subdirectory inside Fusion's install folder. Use Aspect From: The Use Aspect From menu carries three settings for the brush image's aspect ratio. Pick image format to keep the brush image's native aspect ration. Pick Frame Format to adopt the aspect ratio set in the Frame Format Setting within the Fusion Preferences, or pick Custom to type in your own Pixel X and Y dimensions.

- Line: This style yields straight, line-shaped particles with optional “falloff.” The Size to Velocity control covered further down (under Size Controls) often pairs well with this Line type. The Fade control sets how much falloff runs along the line's length.
- Point Cluster: This style yields small clusters made of single-pixel particles. Point Clusters resemble the Point style, but they prove more efficient when a great many particles are needed. The style borrows parameters from the Point style. Two controls belong specifically to Point Cluster style: Number of Points along with Number Variance. Sub Pixel Rendered: This checkbox sets whether the point particles render at Sub Pixel precision, which yields smoother-looking motion at the cost of blurrier particles that take a touch longer to render. Number of Points and Variance: This control's value sets how many points each Point Cluster holds.

### Color Controls

The Color Controls pick the color and Alpha values for the particles the emitter spawns. Color Variance These range controls give you a way to broaden the colors the pEmitter turns out. Putting the Red variance range at -0.2 to +0.2 yields colors that swing 20% to either side of the red channel, a total variance of 40%. With the pEmitter set to turn out R0.5, G0.5, B0.5 (pure gray), the variance just described yields points spanning a color range from R0.3, G0.5, B0.5, to R0.7, G0.5, B0.5. To picture color space as values from 0-256 or from 0-65535, swap the values Fusion uses through the Show Color As option in the General tab of the Preferences dialog. Lock Color Variance Ticking this checkbox locks the particles' color variance. Unlock it and the color variance can be applied unevenly per color channel, opening up a wider range of colors.

### Particles Color Over Life controls

Color Over Life This ordinary gradient control lets you pick a span of color values the particle will follow across its lifetime. The gradient's left point stands for the particle color at birth. Its right point gives the particle color at the close of its lifespan. Drop extra points onto the gradient control and the particle color shifts as its life runs on.

A control of this sort comes in handy for fire-type effects (for instance, the flame might open blue, move to orange, and finish on a darker red). You can animate the gradient itself over time by right-clicking the control and picking Animate from the contextual menu. Every point on the gradient is driven by one Color Over Life spline, which sets how fast the gradient itself shifts. There is also the From Image modifier, which builds a gradient out of the spread of colors in an image taken along a line drawn between two points.

### Particles Size and Fade controls

### Size Controls

Most of the Size Controls explain themselves. The Size and Size Variance controls set the size and the spread of size variation for each particle. Worth flagging is that the Point style carries no size controls (each point measures a single pixel, with nothing more to adjust). Under a Bitmap Particle style, a value of 1.0 means each particle should match the input bitmap's size. A value of 2.0 grows the particle by 200%. For top-quality particles, always aim to keep the input bitmap as large as, or larger than, the biggest particle the system turns out. Under the Point Cluster style, the size control governs the cluster's density, that is, how tightly the particles pack. Further size controls exist for refining particle size against velocity and depth. Size to Velocity This grows each particle in proportion to its velocity or speed. The particle's velocity is folded into the size, scaled by this control's value. At 1.0 on this control, a particle moving at 0.1 picks up another 0.1 of size (velocity \* size to velocity + size = new size). It suits Line styles best, though the control will adjust the size of any style. Size Z Scale This control gauges how much each particle's size shifts with its Z position. The result is to overstate or dampen how strongly perspective reads. The default value is 1.0, which gives a fairly realistic perspective effect.

Anything on the focal plane (Z = 0.0) shows at its true size. Anything further out along Z shrinks. Anything nearer along Z grows. A value of 2.0 blows the effect up dramatically, whereas a value of 0.0 strips perspective out altogether. Size Over Life This spline control sets a particle's size over the course of its lifespan. The vertical axis stands for a percentage of the value the Size control defines, running 0 to 200%. The horizontal axis covers the particle's lifespan as a percentage, from 0 to 100%. Every feature a standard spline editor offers is supported on this graph. You reach those features by right-clicking the graph. You can equally view and edit the graph spline within the larger Spline Editor.

### Fade Controls

This plain range slider gives you a way to fade a particle in at the opening and out at the close of its lifetime. Raising the Fade In value fades the particle in as its life begins. Lowering the Fade Out value fades the particle out as its life ends. The control's values stand for a percentage of the particle's whole life, so putting the Fade In at 0.1 fades the particle in across the first 10% of its total lifespan. As an example, a particle that lives 100 frames would fade in from frame 0…10.

### Merge Controls

This batch of particle controls shapes how individual particles get merged. The Subtractive/ Additive slider behaves as the standard Merge node documents. The Burn-In control drives the particles to overexpose, or “blow out,” as they combine. Not one of the Merge controls does anything to a 3D particle system.

### Particles Blur controls

### Blur Controls

This batch of particle controls lets you lay a Blur onto the individual particles. The blurring can run globally, by age, or by Z depth position. Not one of the Blur controls does anything to a 3D particle system.

Blur (2D) and Blur Variance (2D) These controls blur each particle. In contrast to the Blur in the pRender node, this one hits each particle on its own before the particles get merged. The Blur Variance slider shifts how much blur lands on each particle. Blur Over Life This spline graph governs how much blur reaches the particle across its life. The vertical axis stands for a percentage of the value the Blur control defines. The horizontal axis stands for a percentage of the particle's lifespan. This graph supports every feature a standard Spline Editor offers. You reach those features by right-clicking the graph. Viewing and editing the spline inside the larger Spline editor is possible too. Z Blur (DoF) (2D) and DoF Focus This slider control blurs each particle according to where it sits along the Z axis. The DoF Focus range control marks out which part of the image stays sharp. Smaller values along Z lie nearer the camera; larger ones lie further off. Particles inside the range stay sharp. Particles beyond it pick up the blur the Z Blur control defines. Conditions

pVortex Conditions tab Conditions Tab The Conditions tab narrows which particles the node's behavior reaches. You can pare the particles down by probability or, more pointedly, by sets. Probability The Probability slider fixes the percentage chance that the node touches any one particle. At its default of 1.0 it touches every particle. A setting of 0.6 would give each particle a 60 percent chance of being touched by the control. The probability is worked out for each particle on each frame. So a particle left untouched by a force on one frame faces the same odds of being touched on the following frame.

Start/End Age This range control lets you confine the node's effect to a given percentage of the particle lifespan. As an example, to hold a node's effect to the final 20 percent of a particle's life, put the Start value at 0.8 and leave the End value at 1.0. Across frames 80 through 100 the node touches only a particle whose lifespan is 100 frames. Set Mode Menu The Set Mode menu steers how the particle node acts on the active particle sets. Three options come off this menu:

- Ignore Sets: The particle node pays no mind to the Set checkboxes' state and applies to all nodes.
- Affect Specified Sets: The particle node directs its behavior at the active Set checkboxes alone.
- Ignore Specified Sets: The particle node directs its behavior at the inactive Set checkboxes alone.

Set # A Set # checkbox's state decides whether the Particle node's effect reaches the particles in that set. It lets you hold some nodes' effects to a slice of the particles. Sets get handed out by the nodes that create particles, namely the pEmitter, pImage Emitter, pChangeStyle, and the pSpawn nodes.

### Region Tab

The Region tab serves to pen the node's effect into a geometric region or plane and to fix the area where particles spawn on a pEmitter node, or where a node's behavior carries weight.

pEmitter Regions tab set to mesh The Region tab is shared by nearly all particle nodes. On the pEmitter node, Emitter Regions fix where particles spawn. On most other tools, it pens the tool's effect into a geometric region or plane. Seven region types exist, each with controls of its own. A single pEmitter node admits just one emitter region. With the pRender set to 2D, the emitter region spawns particles along a flat plane in Z Space. 3D emitter regions carry depth and can spawn particles inside a user-defined, three-dimensional region.

Region Mode Menu The Region Mode menu holds seven region types for defining the area, each with its controls.

- All: In 2D, particles spawn anywhere inside the image's bounds. In 3D, the region is a cube measuring 1.0 x 1.0 x 1.0 units.
- Bézier: Bézier mode leans on a user-drawn polyline to set where particles spawn. The mode functions in both 2D and 3D, yet the Bézier polyline region itself can be drawn only in 2D. To animate the polyline's shape over time or wire it to another polyline, right-click the Shape animation label at the foot of the inspector and pick the fitting option from the drop-down.
- Bitmap: A Bitmap source drawn from one of the composition's other nodes serves as the region where particles are born.
- Cube: A full 3D Cube sets the region inside which particles spawn. Its height, width, depth, and XYZ positions are all yours to set and to animate over time.
- Line: A plain line control sets where particles spawn. The line runs between two end-points, which you can wire to Paths or Trackers as the need arises. This emitter region type brings X, Y, and Z position controls for both the line's start and its end
- Mesh: Any 3D Mesh will serve as a region. Under Mesh mode, you can also pare the region down by Object ID through the ObjectID slider. A fuller account of how mesh regions work appears below.
- Rectangle: The Rectangle region type works like the Cube type, except this one carries no depth in Z space. Setting it apart from other 2D emitter regions, it can be positioned and rotated in Z space.
- Sphere: This is a spherical 3D emitter region carrying Size and Center Z controls. Sphere (3D) stands as the default region type for a fresh pEmitter node.

### Mesh Regions

Region Type The Region Type drop-down lets you decide whether the region takes in the inner volume or only the surface. On a pEmitter mesh region, for instance, this settles whether particles emit off the surface or out of the full volume. Winding Rule and Winding Ray Direction Together, these two parameters set how the mesh region copes with particle creation on meshes that are not closed, a frequent state of affairs in many meshes brought in from outside applications. It crops up often with imported mesh geometry, and even geometry that looks closed will routinely seem to “leak” owing to vertices that were welded improperly. To judge whether a particle sits inside an object, a ray is fired from infinity through that particle and onward to -infinity. The Winding Ray Direction sets the direction in which this ray is fired. Every time the ray pierces a surface, that is logged and tallied into a running winding number. Crossing against a surface's normal scores +1, and crossing with the normal scores -1. The Winding Rule then settles what counts as inside versus outside. Set the Winding Rule to Odd, for instance, and only particles whose winding number is odd are kept as the particles are created. That very same method makes sure self-intersecting polylines close up correctly.

As an example, the node tree and image below show a pair of image planes pressed into service as a mesh region for particle creation.

Switch the region's Winding Ray Direction to the Z (blue) axis and this mesh can then stand in as a closed volume for the sake of particle creation, as the picture below shows.

Limit By ObjectID Ticking this checkbox frees the Object ID slider to choose the ObjectID brought into the region.

### Style Tab

The Style tab is present on the pEmitter, pSpawn, pChangeStyle, and pImage Emitter. It dictates how the particles look, letting their appearance be designed and animated over time. Style The Style menu opens up the assorted particle types the Particle Suite supports. Every style holds controls of its own along with controls it shares with other styles.
