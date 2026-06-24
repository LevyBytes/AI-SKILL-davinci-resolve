# Deep Image Nodes

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Deep Image Nodes

Fusion’s Deep Image Nodes, used to composite objects in 3D space, are the subject of this chapter. Each node name carries an abbreviation beside it that you can type into the Select Tool dialog while hunting for tools, and that also turns up in scripting references. Throughout this document, treat node trees that show MediaIn nodes in DaVinci Resolve as equivalent to Loader nodes in Fusion Studio, except where a note says otherwise.

### Deep Image Compositing Toolset (Studio Version Only)

A subset of tools in Fusion can load, work with, and save deep image data. Such deep image data — most notably in formats like OpenEXR — keeps several samples for each pixel so as to capture data about objects sitting at varying depths within one pixel. By drawing on this valuable information, the Fusion Deep Image toolset can stack intricate 3D renders — especially in spots where several objects overlap — and merge them into rendered 3D scenes. You’ll find the tools inside the Deep Image subcategory, each carrying a d-prefix. There’s also this:

- Renderer3D nodes can output deep image data.
- Loader and the MediaIn node can import deep image data EXRs.
- Saver can export deep image EXRs.
- Every deep compositing tool — apart from Image to Deep and Deep to Image — is able, on its own, to

turn 2D image inputs into a deep image. NOTE: A linear colorspace is what deep compositing calls for. After the merge is done, you’re free to convert the results into whatever colorspace you want.

### Caching Deep Composites to Disk

Caching deep compositions to disk eases the load that intricate deep compositions place on your computer. The way to do it: right-click whichever node you’d like to cache, pick Cache to Disk, choose where the cache should be saved, and hit OK.

### dCrop [dCr]

The dCrop node dCrop Node Introduction Using min and max depth values you specify, this tool crops Deep Image samples. Pixels can also be cropped by it through an input mask.

### Inputs

A single input is what the dCrop tool relies on. Input: The lone required connection is this orange input. A node carrying deep image data feeds it. Effect Mask: That optional blue effect mask input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools.

### Basic Node Setup

Into the dCrop node comes the media in that holds the deep image data. From there it lets you refine which depth boundaries get handed along to the next tool.

dCrop accepts deep image data Inspector

dCrop controls Controls Tab Inside the Controls tab sit parameters that govern how much depth information moves on to — or is held back from — the node tree beyond. Depth Crop Cropping the Z parameters belonging to the deep image data is what this lets you do.

- Use Minimum Z: Tick this box to apply a Minimum Z depth to the crop. Use Minimum Z: Set the Minimum Z amount with this slider. Sample: Click and drag out of the sample button into the Viewer to pick a value.
- Use Maximum Z: Tick this box to apply a Maximum Z depth to the crop.
- Keep Outside Depth Range: Reach for this control to flip the cropped selection. Once you’ve set a

minimum and/or maximum value with the sliders above, this control reverses the selection so that the cropped area now shows.

### Common Controls

Settings Tab Other Deep Image nodes carry a copy of the Inspector’s Settings tab as well. Full coverage of these common controls waits at this chapter’s close, under “The Common Controls.”

### Deep to Image [DTI]

### The Deep to Image node

### Deep to Image Node Introduction

By flattening its depth samples, this tool turns deep data into a 2D image. What comes out is the deep composite, set for ordinary 2D compositing.

### Inputs

A single input is what the Deep to Image tool relies on. Input: The lone required connection is this orange input. A node carrying deep image data feeds it.

### Basic Node Setup

Into the Deep to Image node comes the media in that holds the deep image data. From there it flattens the image for further work in normal 2D compositing.

Taking in deep image data, Deep to Image flattens it and then routes the resulting 2D image onward through the node tree.

### Inspector

### Deep to Image controls

### Controls Tab

Inside the Controls tab sit parameters that govern the depth information.

- Flip Depth: Inverts the depth information.
- Volumetric Composition: Rather than treating overlapping deep samples as flat surfaces, the Volumetric Composition option blends them as semi-transparent volumes, modeling true interaction through elements like fog or VDBs. The upshot is a more believable composite of semi‑transparent elements.

### Image Tab

What this tab’s controls do is set the resolution, color depth, and pixel aspect of the rendered image the node turns out.

### The Deep to Image Image tab

Process Mode Reach for this menu control to pick which Fields Processing mode Fusion uses while rendering changes to the image. Which option starts out as the default hinges on the Has Fields checkbox control in the Frame Format preferences.

Depth Setting the pixel color depth of the particles is the job of the Depth menu. Where an 8-bit pixel sits, a 32-bit pixel needs 4X the memory but delivers far finer color accuracy. With Float pixels you get high dynamic range values reaching past the usual 0…1 range, so colors brighter than white or darker than black can be represented. Source Color Space To set the Color Space of the footage and steer a linear workflow, you can turn to the Source Color Space menu. This carries out no real color space conversion the way the Gamut tool does; instead it writes the source space data into the metadata, where that metadata is missing. Downstream, that metadata can then feed a Gamut tool set to the From Image option, or a Saver where explicit output spaces have been defined. You get two options to pick from:

- Auto: Reads whatever metadata the image may hold and passes it along automatically.
- Space: Brings up a Color Space Type menu where you can pick the image’s correct color space.

the image. Source Gamma Space The footage’s Gamma Space is something you set through the Curve type menu, and while working in a linear workflow you can choose to strip it out via the Remove Curve checkbox. Three choices fill the Curve type menu:

- Auto: Reads whatever metadata the image may hold and passes it along automatically.
- Space: Brings up a Gamma Space Type menu where you can pick the image’s correct gamma curve.

the image.

- Log: Calls up the Log/Lin settings, much like the Cineon tool does.

To learn more, turn to Chapter 99, “Film Nodes,” within the DaVinci Resolve Reference Manual, or to Chapter 39 within the Fusion Reference Manual. Remove Curve Depending on which Gamma Space you chose, or on the Gamma Space turned up by Auto mode, the Gamma Curve gets stripped from the material — or a log-lin conversion gets run on it — which in effect converts it to a linear output space. Pre-Divide/Post-Multiply When you need it, this lets you turn “straight” Alpha channels into pre-multiplied Alpha channels.

### Common Controls

Settings Tab A copy of the Inspector’s Settings tab also lives on other Deep Image nodes. These common controls get their detailed treatment at the end of this chapter, in the “The Common Controls” section.

### Deep to Points [DTP]

### The Deep to Points node

### Deep to Points Node Introduction

Deep images get turned into a 3D point cloud by this tool. Handy for picturing depth samples, it gives you a way to see elements in Z as you bring them in.

### Inputs

A single input is what the Deep to Points tool relies on. Input: The lone required connection is this orange input. A node carrying deep image data feeds it. Camera: Wire a scene’s camera into the green camera input and the point cloud lands precisely relative to the original 3D scene. The camera’s perspective gets factored in, so points end up accurately placed inside the 3D Viewer.

### Basic Node Setup

Into the Deep to Points node comes the media in that holds the deep image data. From there it builds a 3D point cloud out of the image to make picturing elements in Z space easier.

Taking in deep image data, Deep to Points builds a Point Cloud out of it and then hands that visualization along to the node tree beyond.

### Inspector

### Deep to Points controls

### Controls Tab

Inside the Controls tab sit parameters that govern the point cloud.

- Style: Style lets you render the points in the viewer either as cross hairs or as points.
- Size: Use this slider to enlarge the onscreen crosshairs or points
- Antialiasing: Switch it on and points turn rounded and smooth, giving softer edges.
- Density: This slider lets you steer how concentrated the points are overall in the viewer.

Raise the value and the intensity of points builds up; lower it and the reverse happens.

- Default Color: Clear the Use Per-Point Colors checkbox and every point takes on the color you set in this control.
- Use Per-Point Colors: Switch it on and every point takes its color from the connected source clip.
- Make Renderable: Sets whether the point cloud you see in the 3D viewer will render in a Renderer3D node. Tick this checkbox and the point cloud can be rendered out to a flat 2D image.
- Unseen by Camera: This checkbox control shows up once the Make Renderable option is on. Tick the Unseen by Cameras checkbox and the point cloud stays visible in the viewers yet isn’t rendered into the output image by the Renderer 3D node.
- Scale: This slider lets you grow or shrink the point cloud’s overall size.
- Depth Scale: With the slider you can stretch or squeeze the point cloud’s overall depth. Raise the depth scale and the overall depth distance grows; the points spread apart, giving you a fuller picture of the point cloud.
- Flip Depth: Reach for this checkbox to invert the depth data, swapping the points’ position from negative to positive

### Transform Tab

What this tab’s controls do is set the position and scaling parameters of the point cloud.

### The Deep to Points Transform tab

### Translation

X, Y, Z Offset Reach for these controls to position the point cloud.

### Rotation

Rotation Order Reach for these buttons to pick the order in which rotation gets applied along each axis of the object. As an example, XYZ applies the rotation first to the X axis, next to the Y axis, and last of all to the Z axis. X, Y, Z Rotation Reach for these controls to spin the object about its pivot point. With the Use Target checkbox on, the rotation is relative to the target’s position; otherwise the global axis is what’s used.

### Pivot

X, Y, Z Pivot The point an object rotates about is its Pivot point. An object normally turns about its own center, which counts as a pivot of 0,0,0. Reach for these controls to shift the pivot away from the center.

### Scale

X, Y, Z Scale With the Lock X/Y/Z checkbox ticked, just one Scale slider appears. That sets the object’s overall size. Clear the Lock checkbox and separate X, Y, and Z sliders show up so you can scale each dimension on its own. Note: When the Lock checkbox is ticked, you can’t scale individual dimensions, not even by dragging particular axes of the Transformation Widget in scale mode. Use Target Tick the Use Target checkbox and a set of controls opens up for placing an XYZ target. With target on, the object always turns to face the target. Its rotation becomes relative to the target. Import Transform Opens up a file browser where you pick a scene file your 3D application saved or exported. These file types are supported:

LightWave Scene Max Scene Maya Ascii Scene

.lws .ase .ma

Only transformation data gets brought in by the Import Transform button. When it comes to 3D geometry, lights, and cameras, think about reaching for the File > FBX Import option instead.

### Onscreen Transformation Controls

Out in the viewer, most of the Transform tab’s controls show up as onscreen controls for transformation, rotation, and scaling. To switch which mode the onscreen controls are in, click one of the three buttons on the toolbar at the viewer’s upper left. There are keyboard shortcuts for flipping between the modes as well: translation is Q, rotation is W, and scaling is E. Across all three modes, you can drag a single axis of the control to affect just that one, or drag the control’s center to affect all three axes at once.

For most 3D tools the scale sliders start out locked, which scales all three axes uniformly. Clear the Lock X/Y/Z Scale checkbox to scale an object along one axis alone.

### Viewer Transform controls

### Common Controls

Settings Tab The Inspector’s Settings tab is mirrored on other Deep Image nodes too. You’ll find these common controls spelled out fully at the close of this chapter, within “The Common Controls.”

### dHoldout [dHld]

The dHoldout node dHoldout Node Introduction With a foreground Deep Image, this tool occludes background Deep Image samples — either dropping them or working out the value once occlusion has happened Inputs One background input plus a foreground input is what the dHoldout tool relies on. Background: From a node holding the deep image data you mean to serve as the background, this orange input is connected. Foreground: That white foreground input takes the second of two deep images, usually a foreground subject meant to occlude the background.

### Basic Node Setup

Into the dHoldout node comes the background media holding the deep image data. From there it lets you refine the foreground deep image’s depth boundaries so as to occlude the background.

Pulling in deep image data from a pair of sources, dHoldout occludes the background by means of the foreground source. Inspector

dHolodout controls

### Controls Tab

Inside the Controls tab sit parameters that govern how much depth information goes into — or is held back from — occluding the background deep image.

- Compute Occluded Samples: Reach for this checkbox to drop samples out of a semi-transparent foreground input. Visible background pixels get recolored as though glimpsed through a partly transparent foreground.
- Holdout Z Offset: This slider lets you slide the holdout depth samples forward or back. Lower this value to push the holdout forward; raise it and the reverse happens. Sample: Click and drag out of the sample button into the viewer to pick a value.
- Holdout Center: This lets you reposition the holdout along the X and Y axis.

### Common Controls

Settings Tab Other Deep Image nodes likewise hold a copy of the Inspector’s Settings tab. A detailed account of these common controls comes at the end of this chapter in the “The Common Controls” section.

### dMerge [dMg]

The dMerge node dMerge Node Introduction Several data streams get combined by this tool, which merges their depth samples for seamless compositing. Like the merge 3D tool, it sports numerous inputs.

### Inputs

One background input plus multiple foreground inputs is what the dMerge tool relies on. Background: From a node holding the deep image data you mean to serve as the background, this orange input is connected. Foreground: That white foreground input is for wiring in other deep image nodes you’d like to combine with the background. You can feed this tool several foreground inputs simply by dragging extra connections between the nodes.

### Basic Node Setup

Into the dMerge node comes the background holding the deep image data. From there it lets you merge in additional deep image nodes so as to combine the data.

dMerge accepts deep image data from multiple sources and combines them.

### Common Controls

Settings Tab A copy of the Inspector’s Settings tab lives on other Deep Image nodes as well. These common controls receive full coverage at this chapter’s end, in the section called “The Common Controls.”

### dRecolor [dRc]

The dRecolor node dRecolor Node Introduction Deep Image data gets combined with an RGB (multi-layer) image by this tool. The node carries two inputs — one for Deep/depth, the other for Color. Turn to this node to recolor Deep Image samples using 2D RGB values Inputs Two inputs are what the dRecolor tool relies on, one for deep color images and one for RGB images. Depth: From a node holding the deep image data you mean to recolor, this orange input is connected. Color: That green input is for the RGB image you’d like to use in combining with the Depth input.

### Basic Node Setup

Into the dRecolor node comes media holding deep image data. From there it lets you combine that with an ordinary 2D image by way of the RGB input.

Taking in deep image data, dRecolor lets you blend it together with a 2D RGB image. Inspector

dRecolor controls Controls Tab Inside the Controls tab sit parameters for blending the 2D RGB image into the background deep image.

- Center X/Y: Reposition the 2D RGB image over the deep image.
- Target Input Alpha: Tick this checkbox to switch on the Alpha channel from the Color input,

shaping how transparent the deep samples are. Switch this option off and only RGB goes toward recoloring the deep image.

- Drop Input Zero Alpha: Switch this on and pixels in the RGBA source carrying zero alpha get skipped and leave the deep image untouched.

### Common Controls

Settings Tab Other Deep Image nodes carry the Inspector’s Settings tab in duplicate too. Detailed coverage of these common controls arrives at the end of this chapter, under the “The Common Controls” section.

### dResize [dRz]

The dResize node dResize Node Introduction A Deep Image’s width and height get resized by this tool.

### Inputs

One input alone is what the dResize tool relies on. Image: From a node holding the deep image data you mean to resize, this orange input is connected.

### Basic Node Setup

Into the dResize node comes media holding deep image data. From there it lets you resize that before handing it on to the rest of the node tree.

dResize accepts deep image data and lets you resize it. Inspector

dResize controls Controls Tab Inside the Controls tab sit parameters for resizing the deep image.

- Width: Scales the image’s width.
- Height: Scales the image’s height.

### Common Controls

Settings Tab A duplicate of the Inspector’s Settings tab appears on other Deep Image nodes as well. These common controls are laid out in full at the chapter’s end, within the “The Common Controls” section.

### dTransform [dXF]

The dTransform node dTransform Node Introduction Adjusting the spatial positioning of deep image data while keeping its depth samples is what this tool lets you do. Deep Images can be scaled and translated, the sample Z values included.

### Inputs

One input plus an effect mask is what the dTransform tool relies on. Image: From a node holding the deep image data you mean to transform, this orange input is connected. Effect Mask: That optional blue effect mask input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools.

### Basic Node Setup

Into the dTransform node comes media holding deep image data. From there it lets you transform that before handing it on to the rest of the node tree.

dTransform accepts deep image data and lets you transform it.

Inspector

dTransform controls Controls Tab Inside the Controls tab sit parameters for transforming the deep image.

- Scale Z: With the slider you can stretch or squeeze the source’s overall depth samples. Raise the scale and the overall depth distance grows. Lower it and the depth range gets compressed.
- Translate Z: Translate Z lets you slide an object forward or back along its depth channel. That gives you the control to move an object nearer to or farther from camera. Sample: Click and drag out of the sample button into the viewer to pick a value.
- Center X/Y: Move the center position of the deep image.
- Pivot X/Y: Move the pivot point of the deep image.
- Size X/Y: Resize the deep image on the selected axis.
- Use Size and Aspect: Tick this box to switch on the parameters below. Size: Scales the image evenly along both the X and Y axes Aspect: Lets you set the image’s aspect ratio.

### Common Controls

Settings Tab The Inspector’s Settings tab is duplicated across other Deep Image nodes too. Full detail on these common controls is given at this chapter’s end, in the “The Common Controls” section.

### Image to Deep [ITD]

### The Image to Deep node

### Image to Deep Node Introduction

An input for a 2D image is what this tool carries. Once connected, the image gains deep image data and can be composited within a deep environment through the dMerge node.

### Inputs

A single input is what the Image to Deep tool relies on. Input: The lone required connection is this orange input. A node carrying 2D image data you mean to use with a Deep Image feeds it.

### Basic Node Setup

Into the Image to Deep node comes the media in that holds the 2D image data. From there it tacks Deep Image information onto it, so that it can be put to work in deep image compositing with a dMerge node.

Taking in a 2D image (MediaIn3), Image to Deep then tacks on Deep Image data so that, through a dMerge node, it can be composited together with Deep Image media (MediaIn1).

### Inspector

### Image to Deep controls

### Controls Tab

Inside the Controls tab sit parameters that govern the depth information.

- Specify Z: Tick this box to set the current Z depth. Leave it unticked and you can adjust it with the Z Scale control below.
- Z Scale: With the slider you can stretch or squeeze the source’s overall depth samples. Raise the scale and the overall depth distance grows. Lower it and the depth range gets compressed.
- Z Offset: Lets you slide an object forward or back along its depth channel. That gives you the control to move an object nearer to or farther from camera. Sample: Click and drag out of the sample button into the viewer to pick a value.
- Center X/Y: Reposition the 2D image along the X/Y axes.

### Common Controls

Settings Tab A copy of the Inspector’s Settings tab also appears on the other Deep Image nodes. These common controls are covered thoroughly at the end of this chapter, in the “The Common Controls” section.

### The Common Controls

### Settings Tab

On most tools in Fusion you’ll find the Common Settings tab. The controls below are settings specific to Deep Image nodes.

### The Deep Image Settings tab

Hide Incoming Connections Switch this checkbox on to tuck away connection lines coming from incoming nodes, which makes a node tree look tidier and read more easily. With it on, the Inspector shows an empty field for each input on a node. Drag a connected node out of the node tree into the field and that incoming connection line hides itself, so long as the node stays unselected in the node tree. Select the node in the node tree and the line returns. Comments Tab A single text control fills the Comments tab, used for adding comments and notes onto the tool. Add a note to a tool and a tiny red dot icon turns up beside the setting tab’s icon, while a text bubble shows on the node. To read the note in the Node Editor, rest the mouse pointer over the node briefly. Should you need it, the Comments tab’s contents can be animated over time. Scripting Tabs Every tool in Fusion carries the Scripting tab. It holds several edit boxes for adding scripts that run as the tool renders. For fuller detail on what this tab holds, please refer to the scripting documentation.
