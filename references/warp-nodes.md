# Warp Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Warp Nodes

This chapter walks through the Warp nodes that Fusion offers. The short codes printed beside each node's name come in handy within the Select Tool dialog while you're hunting for tools, and they show up in scripting references too. Throughout this document, node trees depicting MediaIn nodes in DaVinci Resolve can be swapped one-for-one with Loader nodes in Fusion Studio, except where a note says otherwise.

### Coordinate Space [CdS]

### The Coordinate Space node

### Coordinate Space Node Introduction

What the Coordinate Space node does is convert the image's coordinate space, going either from rectangular over to polar or back from polar to rectangular.

### Inputs

On the Coordinate Space node there are two inputs, meant for hooking up a 2D image plus an effect mask, the latter letting you confine where the distortion lands. Input: For the main 2D image being distorted, use the orange input. Effect Mask: The blue input takes a mask shape made from polylines, simple primitive shapes, paint strokes, or bitmaps coming out of other tools. Wiring a mask into this input keeps the distortion bound to the pixels falling inside the mask. The effects mask gets applied to the tool only after the tool itself has been processed.

### Basic Node Setup

In the example below, the Coordinate Space node builds a circular pattern off a Fast Noise, a Mosaic Blur (DaVinci Resolve Resolve FX only), and a Transform node. That Crop node tacked on at the end is there to dial in whatever resolution you want.

The Coordinate Space node can help create motion graphics backgrounds

### Example

Here's how to pull off a simple tunnel effect with this node: 1. Drop in a Text+ node carrying some text, then animate it so it travels along a path running from the frame's top down to its bottom. 2. Route the Text+ node's output into a Coordinate Space node. 3. From the Shape menu, pick Polar to Rectangular. As the text travels top to bottom down its original path, within the Coordinate Space node it seems to approach from an endless distance. You might have to flip the text with a Transform node so it reads the right way once inside the Coordinate Space node. People also frequently pair the Coordinate Space node up: two of them tuned to differing Shape settings with a Drip or Transform node sitting between them. Set up that way, the effect changes while the underlying image stays put.

### Inspector

### The Coordinate Space Controls tab

### Controls Tab

Over in the Controls tab, the Shape menu toggles between Rectangular to Polar and Polar to Rectangular. Work through the following example to see how the two coordinate spaces play out.

### Common Controls

Settings Tab This node's Settings tab in the Inspector also turns up on other Warp nodes. Those shared controls get a thorough treatment at this chapter's close, under the "The Common Controls" section.

### Corner Positioner [CPn]

### The Corner Positioner node

### Corner Positioner Node Introduction

With the Corner Positioner you can interactively place an image's four corners. The usual job for this is swapping out a sign or some other rectangular piece of a scene. For animation, tie all of the corners to Paths or Trackers.

### Inputs

The Corner Positioner node carries two inputs, used for attaching a 2D image alongside an effect mask, where the mask can hem in the warped region. Input: Feed the main 2D image you're warping into the orange input. Effect Mask: A mask shape drawn from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools belongs in the blue input. Hooking a mask up here restricts the Corner Positioner to just the pixels lying within the mask. That effects mask is applied to the tool once the tool has finished processing.

### Basic Node Setup

Down below, the Corner Positioner places the rectangular corners of MediaIn2 so they sit inside a particular region of the MediaIn1 node. A Planar Tracker follows the background, after which a Planar Transform holds the Corner Positioner in place while the background clip travels. With the planar tracking finished and the Planar Transform generated, the Planar Tracker node has served its purpose and can be deleted.

The Corner Positioner corner-pins a clip into position, leaning on a Planar Transform to match-move that clip onto the background.

### Inspector

### The Corner Positioner Controls tab

### Controls Tab

Within the Controls tab you'll find transform and offset settings covering the image's four corners Mapping Type This picks which method projects the image produced by the Corner Positioner. Under Bi-Linear mode, a plain 2D warp occurs. Under Perspective mode, the image is worked out using the offsets in 2D space and then projected into a 3D perspective. Corners X and Y The Corner Positioner holds four points. Drag them about to interactively set each corner of the image. Hook these control points up to any of the customary modifiers. The input image gets deformed and perspective-corrected so it lines up with where the four corners sit. Offset X and Y Use these to nudge the corner positions a little. That comes in handy when the corners are tied to Trackers whose patterns might not land precisely where you need them.

### Common Controls

Settings Tab Like the other Warp nodes, this one repeats the same Settings tab inside the Inspector. You'll find these shared controls explained fully at the end of this chapter, within the "The Common Controls" section.

### Dent [Dnt]

### The Dent node

### Dent Node Introduction

The Dent node bends an image into a circular deformation akin to a Fish Eye Lens look, offering a pick of six distinct Dent filters.

### Inputs

There are two inputs on the Dent node, for attaching a 2D image plus an effect mask, with the mask serving to confine the warped region. Input: The orange input takes the main 2D image getting warped. Effect Mask: Into the blue input goes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Plugging a mask in here limits the Dent to only the pixels sitting inside the mask. The effects mask is applied to the tool after that tool has been processed.

### Basic Node Setup

Below, the Dent node shapes a circular pattern that's driven by a Fast Noise together with a Mosaic Blur (DaVinci Resolve Resolve FX only). Sitting at the tail end, the Crop node is what locks in whichever resolution you're after.

The Dent node lends a hand in producing lens-distortion looks or a backdrop for motion graphics.

### Inspector

### The Dent Controls tab

### Controls Tab

The settings on the Controls tab let you alter the Dent's style, position, size, and strength.

Type Choose from this menu which kind of Dent filter you'd like. Every Dent parameter can be keyframed. Dent 1 Produces a bulging dent. Kaleidoscope Forms a dent, then mirrors it and inverts it. Dent 2 Produces a displacement dent. Dent 3 Produces a deform dent. Cosine Dent Produces a fracture toward a central point. Sine Dent Produces a smooth, rounded dent. Center X and Y This places the Center of the Dent effect onto the image. By default the values are 0.5, 0.5, which sit the effect at the image's center. Size This alters how large an area the dent touches. Animate the slider to make the dent expand. Strength This adjusts the dent's overall strength.

### Common Controls

Settings Tab The Inspector's Settings tab here is mirrored across the other Warp nodes as well. A complete description of these shared controls waits at the end of this chapter in the "The Common Controls" section.

### Displace [Dsp]

### The Displace node

### Displace Node Introduction

By way of a map image, the Displace node shifts or refracts a second image. That's handy for producing a huge spread of effects, running from bevels and heat distortion through to glass and water looks.

### Inputs

Three inputs sit on the Displace node: the primary image, the foreground image serving as the displacement map, plus an effect mask. Input: A required connection, the orange image input, carries the primary image you mean to displace. Foreground Image: The green input is likewise mandatory, holding the image that drives the displacement of the background. With it connected, you can pick the red, green, blue, alpha, or luminance channel to build the displacement from. Effect Mask: The optional blue effect mask input wants a mask shape created out of polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Wiring a mask here keeps the displacement confined to the pixels within the mask. The effects mask is applied to the tool once it has been processed.

### Basic Node Setup

In the setup below, the Displace node draws on a Fast Noise to build the Displace map. Pushing up the seethe rate can yield heat-distortion looks or a waving-flag effect.

The Displace node using a Fast Noise node for the Displace map

### Inspector

### The Displace Controls tab

### Controls Tab

The Controls tab is where you adjust the displacement's style, position, size , strength, and lighting (embossing). Type The Type menu lets you select which mode the Displace node runs in. Radial mode leans on the map image to refract each pixel outward from the center, whereas X/Y mode hands you control over how much displacement happens along each axis on its own. NOTE: Radial mode gives you a single set of Refraction controls, while XY mode supplies two sets—one apiece for the X and Y channels. Center (Radial Only) Where pixels get pushed toward or pulled away from is marked by the Center control. Refraction Channel This drop-down governs which channel of the foreground image drives the image's displacement. Pick from the Red, Green, Blue, Alpha, or Luminance channels. Under XY mode this control shows up twice, once for X displacement and once for Y displacement. Refraction Strength (Radial) Sets how strong the refraction is. Bigger values bring on stronger, more pronounced refraction. X and Y Refraction (X/Y) A pair of separate sliders shows up so the Refraction strength can be set along the X- and Y-axis independently. Apart from that, it behaves just like Refraction Strength. Light Power This governs how intense, or strong, the simulated light is, making bright and dim regions appear that follow the contour of the refraction image. Larger values render those bright and dim regions more pronounced.

Light Angle This dictates the angle the simulated light source comes from. Spread This broadens the Displacement effect and softens the edge of the Refraction map. Larger values make the ridges or edges fan out. Light Channel Decide which channel of the refraction image stands in as the simulated light source. Your options are the Color, Red, Green, Blue, Alpha, or Luminance channels. NOTE: In Radial mode, pixels are driven inward or outward away from a central point according to the pixel values read off the Displacement map. XY mode draws on two separate channels of the map to shift pixels both horizontally and vertically, which buys you tighter precision. Working in XY mode, the Displace node is even capable of pulling off basic morphing effects. Meanwhile the Light controls bring directional highlighting to refracted pixels, faking a beveled appearance.

### Common Controls

Settings Tab This node's Settings tab in the Inspector recurs on the other Warp nodes too. The shared controls are laid out in full toward the end of this chapter, in the "The Common Controls" section.

### Drip [DRP]

### The Drip node

### Drip Node Introduction

Across the whole image, the Drip node lays down a ripple effect that can be made to animate outward from a central origin. A selection of differing Drip effects is on offer.

### Inputs

The Drip node provides two inputs, used to attach a 2D image and an effect mask, where the mask can confine the warped region. Input: Send the main 2D image getting warped into the orange input. Effect Mask: The blue input expects a mask shape formed from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Hooking a mask in here keeps the warping bound to only the pixels inside the mask. That effects mask is applied to the tool once the tool has been processed.

### Basic Node Setup

Down below, the Drip node produces rippling, water-like effects working off a MediaIn node.

### Inspector

You can wire the Drip node in right after a MediaIn node, or after any node that hands off a 2D output.

### The Drip Controls tab

### Controls Tab

The Controls tab handles the style, position, size , strength, and phase that animate the Drip's "ripples." Shape Reach for this control to choose the Drip's shape. Circular Produces circular ripples. This is the Drip's default mode. Square Produces evenly sided four-cornered drips. Random Produces a randomly scattered noise that warps your image, much like a particle effect. Horizontal Produces horizontal waves traveling in a single direction. Vertical Produces vertical waves traveling in a single direction.

Exponential Produces a Drip effect resembling a diamond with curved, inverted sides (an exponential curve flipped and mirrored). Star Produces an eight-way symmetrical, star-shaped ripple that behaves like a kaleidoscope once the phase is animated. Radial Produces a star-shaped ripple radiating out of a fixed pattern. Center X and Y Use this to set where the Drip effect's center lands within the image. The default of 0.5, 0.5 sits the effect at the image's center. Aspect Governs the aspect ratio of the assorted Drip shapes. Setting it to 1.0 keeps the shapes symmetrical. Lower values stretch the shape taller and thinner, while higher values squash it shorter and wider. Amplitude The Drip effect's Amplitude refers to how tall the peak of each ripple stands. Use the slider to set how much distortion the Drip imposes on the image. At 0.0, every ripple has no height, which leaves the effect transparent. A top Amplitude of 10 makes each ripple extremely pronounced and warps the image completely. You can type even larger numbers into the text entry boxes. Dampening Governs the Dampening, or falloff, of the amplitude as it travels away from the effect's center. It's useful for reining in the size or extent the Drip affects. Frequency This sets how many ripples spread out from the Drip effect's center. At 0.0 there are no ripples. Slide it up to a value of 100 to match the ripple density you want. Phase This governs how far the frequencies are offset from the center. Animate the Phase value to send the ripple radiating from the effect's center.

### Common Controls

Settings Tab In the Inspector, this Settings Tab is duplicated on the other Warp nodes as well. You'll find a full account of these shared controls at the close of this chapter, in the "The Common Controls" section.

### Grid Warp [Grd]

### The Grid Warp node

### Grid Warp Node Introduction

The Grid Warp node amounts to a 2D deformation grid whose vertices can move freely. It deforms the image such that the source grid is brought into alignment with the destination grid.

### Inputs

On the Grid Warp node sit two inputs, for connecting a 2D image and an effect mask, the mask being able to confine the warped region. Input: The orange input receives the main 2D image you're warping. Effect Mask: A mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools goes into the blue input. Connecting a mask here limits the warping to just the pixels found inside the mask. The effects mask is applied to the tool after the tool has been processed.

### Basic Node Setup

Below, a pair of Grid Warp nodes warp separate regions of a frame. That can come in handy for chaining a shot's framing or lending a still a bit of motion. By way of the Copy Src to Dest button, only the region altered by Grid Warp 2 gets pasted as the foreground in the Merge.

The Grid Warp lets you nudge regions of a shot around, whether to reframe it or to bring a bit of animation to a still.

### Inspector

### The Grid Warp Controls tab

### Controls Tab

Inside the Controls tab live the parameters that set up the onscreen grid plus the style of distortion that kicks in when a grid control point is moved. Source and Destination The Source and Destination buttons decide which grid is active at the moment—the source one or the destination one. Just a single grid may be shown or worked on at any time. Whichever button is selected lights up to show it's the active grid. Every other control on this tab acts upon whichever grid this control has selected. Selection Type These three buttons set the selection styles used while manipulating the points. Three choices are on offer. Selected Under Selected mode, grid adjustments touch only the points presently selected. This mode matches ordinary polyline behavior. Region Under Region mode, all the points within the zone surrounding the mouse pointer shift when you click the mouse button. Points that wander into the region mid-move are disregarded. Selecting this option brings up Magnet Distance and Magnet Strength controls that govern the zone's size and falloff. Magnetic Under Magnetic mode, every point within the zone around the mouse pointer moves on a mouse-button click. Points entering the region during the move get affected too. Picking this option surfaces Magnet Distance and Magnet Strength controls for setting the zone's size and falloff.

Magnet Distance The default tool for picking and shaping the grid is a Magnet node. In the viewer, the magnet shows up as a circle ringing the mouse pointer. The Magnet Distance slider sets how wide the magnet's zone of effect reaches—that is, how big the circle is. Drag across the grid and every vertex within the slider's range shifts. Bump up this slider's value to enlarge the magnet. As an alternative, resize the magnet by holding the D key down as you drag the mouse. Magnet Strength The Magnet Strength slider raises or lowers the falloff of the magnet cursor's influence. With it at 0.0, the magnetic cursor does nothing and vertices stay perfectly still. As you raise the values, the magnet drives a wider range of motion through the chosen vertices. Lean on smaller values for delicate tweaks and larger ones for sweeping changes across the grid. X and Y Grid Size How many divisions the grid carries is governed by the X and Y Grid Size sliders. Wherever the X and Y divisions cross, a control vertex springs up. Keep in mind that changing either of these after you've already altered the grid wipes the whole grid back to scratch. Lock in the X and Y grid sizes at the right resolution before you start making fine adjustments to the grid. Subdivision Level The Subdivision Level sets how many subdivisions fall between each pair of divisions. Subdivisions don't spawn vertices where they intersect. More subdivisions tend to make the deformation smoother, though they slow the render down. Center The Center coordinates pin down the grid's exact center. While you're editing the grid, the onscreen Center control stays hidden. Switch to Edit Rect mode and the grid center becomes both visible and editable. Use the Center control to carry the grid across a scene without disturbing the animation laid onto the individual vertices. As an example, while deforming lips, follow the face's motion with a Tracker and link the grid center to that Tracker. This keeps the grid riding along with subtle head movements while you concentrate on deforming the lips. Angle This Angle control spins the entire grid. Size The Size control scales the grid up or down. Edit Buttons Four edit modes are available, each chosen by clicking the matching button. Edit None Put the grid into Edit None mode to switch off the display of every onscreen control. Edit Grid Edit Grid mode is the default. With it on, the grid is drawn in the viewer and the grid's control vertices can be worked directly.

Edit Rectangle With the grid set to Edit Rectangle mode, the onscreen controls show a rectangle defining the grid's dimensions. You can drag the rectangle's sides to grow or shrink the grid's extent. This mode likewise brings out the onscreen Center control for the grid. Edit Line Edit Line mode helps when you're building grids around organic shapes. Once it's on, every onscreen control vanishes and a spline can be traced around the shape or object you mean to deform. As you draw that spline, a grid forms automatically that best fits the object. When this mode is on, extra controls for Tolerance, Over Size, and Snap Distance show up. Those controls get covered further down. Set Mesh to Entire Image Pressing the Set Mesh to Entire Image button instantly snaps the grid's size back to match the image's exact dimensions. Any vertex tweaks within the grid get reset. Copy Buttons This pair of buttons offers a way to duplicate the precise shape and dimensions of the source grid over to the destination, or of the destination grid over to the source. It's especially handy after you've set the source grid, ensuring the destination grid starts out matching the source grid before a deformation begins. Point Tolerance This control shows up only while Edit Line mode is on. The Point Tolerance slider sets how much tessellation the grid applies in order to track the spline's point density closely. The lower this value, the fewer vertices the resulting grid carries and the more even the grid looks. Higher values begin laying down denser grids that vary to handle stretches of the spline calling for more detail. Oversize Amount This control appears only with Edit Line mode enabled. The Oversize Amount slider decides how big an area surrounding the spline should be folded into the grid. Higher values build a larger border, which helps when you're blending a deformation back into the source image. Snap Distance This control surfaces only when Edit Line mode is on. The Snap Distance slider determines how forcefully the drawn spline pulls in nearby vertices. When a vertex sits close enough to a spline's edge, it slides over to align with the spline. The higher the value, the farther the spline's pull extends. Right-Click Here for Mesh Animation By default the grids don't move. Right-clicking the Right-Click Here for Mesh Animation label opens a contextual menu with choices for animating the grid or tying it to another grid in the composition. The grid relies on a Polychange spline. Any change to the control points adds or revises the keyframe across every point on that spline. Right-Click Here for Shape Animation This label turns up only in Edit Line mode. Right-clicking the Right-Click Here for Shape Animation label brings up a pop-up menu for animating the shaping polyline or linking it to other polylines.

### The Grid Warp Render tab

### Render Tab

The Render tab governs the final rendered quality and look of the warping. Render Method The Render Method drop-down picks the rendering approach and quality used on the mesh. Its three settings run in order of quality, with the first, Wireframe, being the quickest and lowest in quality. The default is Render mode, which delivers full-resolution, full-quality output. Anti-Aliasing The Anti-Aliasing control turns up merely as a checkbox while in Wireframe Render mode. In the other modes it becomes a drop-down offering three quality levels. Stronger anti-aliasing lifts image quality dramatically but pushes render times way up. The Low setting can be a fair choice while you're laying out a big, dense grid or previewing a node tree, though seldom for a final render. Filter Type Whenever the Render Method is anything but Wireframe mode, the Filter Type menu shows and sits on Area Sample. This setting stops the grid from working out area samples for every vertex in the grid, giving solid render quality. Super Sample can yield even finer results but demands far longer render times. Wireframe Width This slider shows up only when the Render Method is set to Wireframe. It dictates how wide the lines forming the wireframe are. Anti-Aliased This checkbox shows up only when the Render Method is set to Wireframe. Use it to turn anti-aliasing on or off for the lines making up the wireframe. Black Background The Black Background checkbox decides whether pixels lying outside the grid in the source image are forced to black or kept as they are.
