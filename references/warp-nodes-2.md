# Warp Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Object ID and Material ID Switch on the Object ID or Material ID checkboxes so the grid writes the correct ID channel into the final render. Set Image Coordinates at Subdivision Level Enabled by default, this checkbox places the image coordinates at the subdivision level. Force Destination Render Enabled by default, this checkbox compels a destination render.

### Contextual Menu Options

Within the viewer's contextual menu, the Grid Warp node adds a submenu covering both the source and destination grids. The two menus carry the identical name, and only whichever grid is active gets its menu filled with options. The remaining menu stays empty. Those contextual menu options also turn up on the toolbar shown in the viewer.

### Grid Warp Contextual Menu options

Modify Only/Done These pair of options place the mesh into Modify Only and Done modes, respectively. Pick Modify Only when you want to edit the mesh, or Modify Done to lock a mesh against further change. Smooth/Linear Reach for the Smooth and Linear options to add smoothing to selected vertices or strip it away.

Auto Smooth Points With Auto Smooth Points turned on, the grid's vertices smooth themselves automatically anytime they get moved. As a rule this stays on by default. Z Under/Z Same/Z Over Where two vertices in a grid sit on top of each other, one of them ends up clipped by the other. You use Z Under, Z Same, and Z Over to decide which vertices render in front and which render behind. Select All Choosing this selects every point in the mesh. Show Key Points, Handles, Grid, and Subdivisions Across the viewers, these four options toggle on or off whether you see the grid, the key points (vertices), the Bézier handles, plus the subdivisions. Reset Selected Points This returns the Selected Points (vertices) to their default positions. Reset All Points This returns every point (vertices) in the mesh to its default position. Stop Rendering Picking this halts rendering, disabling all rendering of the Grid Warp node until you turn the mode back off. It often helps while you make a run of fine adjustments to a complex grid.

### Grid Warp Toolbar

Anytime the Grid Warp node is selected and sits in Edit Grid mode, the views show the Grid Warp toolbar. A range of options for manipulating and adjusting the grid is offered by this toolbar. The preceding "Contextual Menu Options" section already covers the buttons that appear on this toolbar.

### The Grid Warp viewer toolbar

### Common Controls

Settings Tab Other Warp nodes share the same Settings tab found in the Inspector. Full coverage of these common controls sits at this chapter's close, in the "The Common Controls" section.

### Lens Distort [Lens]

### The Lens Distort node

### Lens Distort Node Introduction

You can use this node either to strip lens distortion from an image or to add it. How much lens distortion an image carries hinges on the lens, its quality, the count of elements, and plenty of other factors. One motive for removing lens distortion is compositing against an undistorted layer. As an example, dropping a 3D element over a distorted live-action layer produces unwanted artifacts such as straight lines failing to line up between the foreground and background. That composite ends up looking unconvincing.

### Inputs

The Lens Distort node's two inputs serve to hook up a 2D image plus an effect mask, which you can use to bound the distorted region. Input: The orange input takes the primary 2D image that gets distorted. Effect Mask: A mask shape from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools goes into the blue input. Hooking a mask here confines the distortion to just the pixels inside the mask. That effects mask is applied to the tool once the tool finishes processing.

### Basic Node Setup

In the streamlined example below, the Lens Distort runs in Undistort mode over the MediaIn1 live-action layer, the 3D elements get composited, and finally the Lens Distort runs once more at the end with identical settings, only this time in Distort mode so the image regains its original look and distortion.

Lens Distort placed twice on the live-action media: once where the node tree starts and once more right at its end

### Inspector

### The Lens Distort Controls tab

### Controls Tab

Several routes for customizing or constructing the lens distortion model you want appear on the Controls tab. Camera Settings let you state which camera captured the content. Mode Undistort strips the lens distortion to yield a flattened image. Distort restores the original lens distortion into the image. Edges Decides how samples landing beyond the frame get treated.

- Canvas: Pixels beyond the frame take on the default canvas color. Usually that is black with no alpha.
- Duplicate: Pixels beyond the frame get duplicated. The upshot is "smeared" edges, yet that proves handy when, for instance, applying a blur, because black pixels would otherwise cause unwanted blurring between the real image and the black canvas.

### Clipping Mode

- Domain: Holds onto every pixel that might be pushed out of the frame, ready for later re-distorting.
- Frame: Pixels pushed beyond the frame are discarded.

Output Distortion Map Puts out the locations of pixels as a warped screen-coordinate map. Camera Settings The options familiar from the Camera 3D are duplicated here. You can either dial them in manually or link them to an existing Camera 3D.

Lens Distortion Model From this control, pick whichever 3D Equalizer Lens Distortion model fits — your choices being 3DE Classic Model, 3DE4 Anamorphic, 3DE4 Radial Fisheye, and 3DE4 Radial. For more explanation, consult the 3D Equalizer manual. When no lens data has been imported, the sliders in the 3DE Classic LD Model are likely the best fit for applying (un)distortion by hand. Supersampling [HiQ] Sets how many samples decide each destination pixel. As ever, more supersampling drives render times up. Usually 1×1 bilinear delivers adequate quality, though with heavy lens distortion close to the lens edges, the gap to higher settings becomes noticeable. Supersampling Mode [HiQ] Which kind of sample gets taken for every supersample. Nearest produces a sharper image, though one that is more aliased. A blurrier outcome comes from Bi-Linear. Load Distortion Data Lets the user pull in a Lens Distortion profile authored, say, by the 3D Equalizer. How to Manually Determine Lens Distortion Ideally you would hold exact lens parameters for every lens used during the shoot and could feed those values in to undistort the image. In reality, though, those parameters either were never recorded on set or fail to match. Another route is software like 3D Equalizer, which studies the footage and hands back a dataset you can import straight into the Lens Distort node. And lastly, you could attempt to eyeball the lens distortion amount manually with the control sliders. To do so, you might either hunt for horizontal or vertical lines in the footage that ought to be straight and straighten them out via the controls, or shoot a full-frame checkerboard pattern on set to serve as a reference.

### Common Controls

Settings Tab Other Warp nodes share the same Settings tab found in the Inspector. Full coverage of these common controls sits at this chapter's close, in the "The Common Controls" section.

### Perspective Positioner [PPn]

### The Perspective Positioner node

### Perspective Positioner Node Introduction

The Perspective Positioner serves as the counterpart to the Corner Positioner node. By dropping corner points onto a perspective distorted area, it "unpins" an image and thereby pulls the perspective off it. You can also turn this function to wobbling and warping the image by animating the points over time.

### Inputs

The Perspective Positioner node's two inputs serve to hook up a 2D image plus an effect mask, which you can use to bound the transformed region. Input: The orange input takes the primary 2D image that gets transformed. Effect Mask: A mask shape from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools goes into the blue input. Hooking a mask here confines the transform to just the pixels inside the mask. That effects mask is applied to the tool once the tool finishes processing.

### Basic Node Setup

In the example below, the Perspective Positioner unpins a perspective distorted area of the MedianIn2 so you can paint on the flat texture. Afterward the MediaIn2 gets corner pinned back into position. Because the Perspective Positioner and Corner Positioner do not concatenate, these nodes introduce some softness.

The Perspective Positioner unpins an image to paint on a texture map.

### Inspector

### The Perspective Positioner Controls tab

### Controls Tab

Parameters for choosing vector channels and governing how much distortion they apply to an image appear on the Controls tab. Mapping Type The Mapping Type menu serves to pick which kind of transform distorts the image. Bi-Linear remains for supporting older projects. Keeping this on Perspective is strongly advised, since the Perspective setting models the real world more faithfully. Corners X and Y These are the four control points of the Perspective Positioner. Drag them interactively in the viewers to set each corner of the image. You can fine-tune their positions through the Top, Bottom, Left, and Right controls in the Inspector.

### Common Controls

Settings Tab Other Warp nodes share the same Settings tab found in the Inspector. Full coverage of these common controls sits at this chapter's close, in the "The Common Controls" section.

### Vector Distortion [Dst]

### The Vector Distortion node

### Vector Distortion Node Introduction

The Vector Distortion node warps the main source image independently along the X- and Y-axis, drawing on the vector channel data within the source image or on vector channels from a second reference image.

### Inputs

The Vector Distort node carries three inputs covering the primary 2D image, the distort image holding vector channels, and an effect mask. Input: The orange image input must be connected and carries the primary image you want to distort. Should that image hold vector channels, the distortion uses them. Distort: An optional distort image input, the green one warps the background image off its vector channels. Once it is connected, whatever vector channels the input image held get overridden. Effect Mask: For a mask shape, the optional blue effect mask input expects polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Hooking a mask here confines the displacement to just the pixels inside the mask. That effects mask is applied to the tool after it gets processed.

### Basic Node Setup

In the example below, the MediaIn1 node leans on an Optical Flow node to produce the vector channels, which then pass along to the Vector Distort node. MediaIn2 gets distorted and composited over the background. For the Vector Distort node to work, the image must carry vector channels or an Optical Flow node must generate them.

### Inspector

### The Vector Distortion Controls tab

### Controls Tab

Parameters for choosing vector channels and governing how much distortion they apply to an image appear on the Controls tab. X Channel and Y Channel These two menus pick which channel of the (green) distort image input distorts the X and Y channels. Should no distort reference image be connected, the main orange input's channels stand in instead. Flip Channel X and Flip Channel Y Through these checkboxes you reverse which way the distortion runs along the picked axis. Lock Scale X/Y Ticking this checkbox divides the Scale slider into a pair, namely Scale X and Scale Y. Scale With the Scale slider you multiply whatever values come off the distortion reference image. Lock Bias X/Y Ticking this checkbox divides the Bias slider into a pair, namely Bias X and Bias Y. Center Bias The Center Bias slider shifts or nudges the distortion down a given axis. Edges How the image's edges get treated is set by this menu.

- Canvas: This makes the edges uncovered by the shake take on the canvas color—usually transparent or black.
- Duplicate: This duplicates the edges, yielding a slight smearing effect along the edges.

Glow Use this slider to lay a glow over the result of the vector distortion.

### Common Controls

Settings Tab Other Warp nodes share the same Settings tab found in the Inspector. Full coverage of these common controls sits at this chapter's close, in the "The Common Controls" section.

### Vortex [Vtx]

### The Vortex node

### Vortex Node Introduction

The Vortex effect shows up as a swirling whirlpool across designated regions of the image. By animating its various controls, you can make the Vortex move and grow.

### Inputs

Two inputs sit on the Vortex node — one for the primary 2D image, one for the effect mask. Input: A required connection, the orange image input holds the primary image you want to swirl. Effect Mask: The optional blue effect mask input wants a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Hooking a mask here confines the swirling vortex to just the pixels inside the mask. That effects mask is applied to the tool after it gets processed.

### Basic Node Setup

Below, the Vortex runs on text to build motion graphics. Since the Vortex would swirl the text outside the text boundary, a Set Domain node serves to widen the text boundary, making sure the text is not cropped once the Vortex applies.

The Vortex is used to create swirling whirlpool effects.

### Inspector

### The Vector Distortion Controls tab

### Controls Tab

Parameters for tuning the position, size, and strength of the Vortex effect appear on the Controls tab. Center X and Y This control places the center of the Vortex effect on the image. By default it sits at 0.5, 0.5, which puts the effect in the image's center. Size Size alters how large an area the Vortex affects. You can drag the effect's circumference in the viewer or work the Size slider. Angle Drag the rotation handle in the viewer or work the thumbwheel control to alter how much rotation the Vortex carries. A higher angle value means a stronger swirling effect. Power Pushing the Power slider up shrinks the Vortex while tightening it. In effect it concentrates the swirl within the given image area.

### Common Controls

Settings Tab Other Warp nodes share the same Settings tab found in the Inspector. Full coverage of these common controls appears in the following "The Common Controls" section.

### The Common Controls

A number of identical controls in the Inspector are shared across nodes that perform Warp operations. The controls common to Warp nodes are covered in this section.

### Inspector

### Warp Common Controls tab

### Settings Tab

Every tool in the Warp category carries the Settings tab found in the Inspector. Even third-party Warp-type plugin tools include these Settings controls. They stay consistent and behave the same way for every tool. Blend The Blend control mixes between the original image fed into the tool and the modified output the tool finally produces. Where the blend value sits at 0.0, the outgoing image matches the incoming image exactly. Usually this will make the tool skip processing altogether, passing the input directly through to the output.

Process When Blend Is 0.0 Even with the input value at zero, the tool still processes. This proves handy when the node is scripted to set off a task, while the node's value reads 0.0. Red/Green/Blue/Alpha Channel Selector Use these four buttons to confine the tool's effect to chosen color channels. Typically this filter takes hold once the tool has finished processing. For instance, with the Red button on a Blur tool deselected, the blur will apply to the image first, and afterward the original input's red channel will be copied back across the result's red channel. Exceptions exist, such as tools for which deselecting these channels makes the tool skip processing that channel altogether. Tools of that sort will usually carry an identical set of RGBA buttons on the tool's Controls tab. In such a case, the buttons on the Settings and the Controls tabs match. Apply Mask Inverted Turning on the Apply Mask Inverted option flips the tool's entire mask channel. That mask channel combines every mask connected to or created within a node. Multiply by Mask Choosing this option will have the masked image's RGB values multiplied by the mask channel's values. This will turn every image pixel left out of the mask (that is, set to 0) black/transparent. Use Object/Use Material (Checkboxes) Certain 3D software can render to file formats carrying extra channels. The EXR file format notably supports Object ID and Material ID channels, usable as a mask for the effect. Whether those channels will be used, when present, is governed by these checkboxes. Which specific Material ID or Object ID is affected gets picked through the Object and Material ID sliders explained below. Correct Edges This checkbox surfaces only once the Use Object or Use Material checkboxes are on. It switches the method used for handling overlapping object edges within a multi-object image. With it on, the Coverage and Background Color channels serve to separate and refine the effect along the object's edge. Where this option is off (or no Coverage or Background Color channels exist), the mask's edge may show aliasing. To dig deeper into how the Coverage and Background Color channels work, turn to Chapter 78, "Understanding Image Channels," within the DaVinci Resolve Reference Manual, or else Chapter 18 over in the Fusion Reference Manual.

Object ID/Material ID (Sliders) These sliders pick which ID will build a mask out of an image's object or material channels. Operate the Sample button just like the Color Picker: to lift IDs from the image shown in the viewer. The image or sequence has to have been rendered by a 3D software package that included those channels.

### Motion Blur

- Motion Blur: This switches the rendering of Motion Blur on the tool on or off. With this control switched on, the tool's predicted motion drives the motion blur produced by the virtual camera's shutter. With the control switched off, no motion blur gets created.
- Quality: Quality sets how many samples build the blur. A quality setting of 2 will have Fusion create two samples on either side of an object's actual motion. Bigger values give smoother results yet lengthen the render time.
- Shutter Angle:L Shutter Angle governs the angle of the virtual shutter that produces the motion blur effect. Wider angles yield more blur but lengthen the render times. Set to a value of 360 the shutter stays open for one full frame exposure. Going higher is possible and can yield interesting effects.
- Center Bias: Center Bias shifts where the center of the motion blur sits. That allows motion trail effects to be created.
- Sample Spread: Tweaking this control alters how each sample is weighted. That changes how bright the samples are.

Use GPU Three settings live on the Use GPU menu. Setting the menu to Disable shuts off GPU hardwareaccelerated rendering. Enabled puts the GPU hardware to work rendering the node. Auto taps a capable GPU when one exists and drops back to software rendering whenever a capable GPU is absent. Hide Incoming Connections Turning on this checkbox can conceal the connection lines from incoming nodes, leaving a node tree that looks cleaner and reads more easily. With it on, empty fields for each input on a node show in the Inspector. Dragging a connected node out of the node tree into the field will hide that incoming connection line for as long as the node stays unselected in the node tree. Once the node is selected in the node tree, the line returns. Comments Use the Comments field to attach notes to a tool. Click inside the empty field and type the text. Once a note is attached to a tool, a small red square shows at the node's lower-left corner while the full tile is on display, or a small text bubble icon shows at the right while nodes are collapsed. To view the note inside the Node Editor, rest the mouse pointer over the node so the tooltip appears. Scripts From the Settings tab, every tool in Fusion offers three Scripting fields. Each holds edit boxes for adding scripts that run while the tool renders. For more on scripting nodes, refer to the Fusion scripting documentation.
