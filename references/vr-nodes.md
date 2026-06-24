# Vr Nodes

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### VR Nodes

This chapter walks through the Virtual Reality (VR) nodes that Fusion provides.

Each node name has an abbreviation beside it that you can type into the Select Tool dialog while hunting for tools, and that also serves in scripting references. Throughout this document, take node trees that show MediaIn nodes in DaVinci Resolve as equivalent to Loader nodes in Fusion Studio, except where it says otherwise.

With Fusion's collection of VR nodes you can build and repair spherical (360°) video, the kind commonly called Virtual Reality, or VR. For years now, dome productions, planetariums, and similar special-venue theaters have leaned on the adaptability of Fusion together with its 3D system to make and ship specialized content. That equirectangular (lat-long) format so often chosen for 360° video works much like how a globe gets flattened onto a world map, the poles running along the image's top and bottom edges and the forward viewpoint sitting in the middle. TIP: Stereo VR is achievable by stacking a pair of Lat Long images, assigning one to each eye.

A VR Sphere shown both in the Node Editor and within Fusion's 3D viewer

Fusion handles a handful of widespread spherical image formats and converts among them with ease. VCross and HCross: These are a cube's six square faces arranged into a cross, either vertically or horizontally, the forward view sitting at the cross's middle within a 3:4 or 4:3 image. VStrip and HStrip: These are a cube's six square faces set vertically or horizontally in a row, sequenced Left, Right, Up, Down, Back, Front (+X, -X, +Y, -Y, +Z, -Z) within a 1:6 or 6:1 image. LatLong: This is one 2:1 image carrying an equirectangular mapping. Both spherical video and live 3D scenes from the comp can be sent straight to headsets, the Oculus Rift and HTC Vive included. Fusion's “Fix it in post” tools for VR streamline a handful of key jobs that crop up regularly in productions of this sort.

### Fusion VR 180 Support (Studio Version Only)

Several of Fusion's established VR tools have gained support for a 180-degree angle of view. By concentrating on a forward-facing view, the 180-degree VR format lets you make immersive content while easing the production workflow for VR experiences.

### Apple Immersive Option in the Viewer 360 Views Menu

Within the 2D Viewer windows, Fusion can decode Apple Immersive content. Switch this on by clicking the option menu in a Fusion Viewer and picking 360(o) View > Immersive out of the context menu.

### Immersive Patcher [ImP]

### The Immersive Patcher node

### Immersive Patcher Introduction

With the Immersive Patcher tool you can briefly ‘undistort’ a portion of an immersive clip so that tracking, painting and compositing become easier on a flat plane. When you're done, a second Immersive Patcher re-distorts the immersive signal and folds the freshly composited pieces back into the scene.

### Inputs

Within the Node Editor, the Immersive Patcher node carries two inputs. Input: The orange input takes either an immersive or an ordinary 2D output. Metadata: The metadata input takes metadata fed from another node.

### Basic Node Setup

In essence, the Immersive Patcher is built to operate in pairs:

- Send an immersive video clip through an Immersive Patcher node, using Undistort to turn it into an ordinary image.
- Set the Rotation and Angle of view so they frame the region you intend to alter.
- After that, lean on Fusion's broad toolset to composite and reshape the image just as you normally would.
- After that, run a second Immersive Patcher node to Distort it back into an Immersive Video.
- After that, bring in a merge node to fold your edits back into the original immersive video clip.

IMPORTANT: For the image to hold together, both Immersive Patchers need identical Rotation and Angle of view settings. Simplest route: duplicate the first Immersive Patcher and paste it to make the second.

Routing an immersive video clip through an Immersive Patcher that undistorts the picture, next layering on a multipoly and transform operation, then re-distorting the picture by means of a second Immersive patcher, and finally merging it back together with the original immersive video clip.

### Inspector

### The Immersive Patcher Controls

- Mode: A pair of choices lets you either Distort (turn the image from 2D into Immersive Video) or Undistort (turn Immersive Video into a 2D image) the input.
- Rotation: These controls spin the immersive video around until the region you mean to alter sits in the frame.
- Angle of View: This control sets the angle of view presented inside the VR headset.

### Lat Long Patcher [LLP]

### The Lat Long Patcher node

NOTE: Only Fusion Studio and DaVinci Resolve Studio offer the VR category along with the Lat Long node.

### Lat Long Patcher Node Introduction

Equirectangular stitched images frequently call for patches, paintwork, or assorted VFX. What the Lat Long Patcher does is pull out and de-warp a portion of a lat-long (equirectangular) image for treatment, then warp and merge the fixes back atop the original. You're able to swiftly grab a portion of the spherical image to patch or paint and then lay it back onto the original image. Bear in mind that both the Extract and Apply modes rely on matching rotations, which means a node's action can be undone with ease by a copy or instance carrying the same rotation settings.

### Input

There are two inputs on the Lat Long Patcher node. Its orange input takes a 2D image in equirectangular form, the X-axis standing for 0–360 degrees longitude and the Y-axis for –90 to +90 degrees latitude. An effect mask input exists too, though VR nodes seldom call for it. Image Input: The orange image input takes a equirectangular (lat-long) 2D RGBA image. Effect Mask: An effect mask input is on hand here, even if VR nodes make little use of it.

### Basic Node Setup

The Loader node feeds into the input of a Lat Long Patcher node. That Lat Long Patcher node has its output set to Extract, after which it links into whichever image-processing operation you require. A second Lat Long Patcher node, this one set to Apply, takes its input from the processed extraction and lays it back atop the original source.

Two Lat Long Patchers used to repair a section Inspector

### The Lat Long Patcher Controls tab

### Controls Tab

You use the Controls tab to pull out a portion of an equirectangular image and later put it back. The Rotation controls let you home in on the precise piece you mean to repair.

### Mode

- Extract: Draws a de-warped 90-degree square image out of the equirectangular image.
- Apply: Warps a 90-degree square image and merges it onto the equirectangular image. Since the square image's alpha comes into play, this lets things such as paint strokes or text laid over a transparent black background carry onto the original equirectangular image, sidestepping any double-filtering that de-warping and re-warping the original would cause.
- Apply180: Apply this to extract and patch a VR180 image. It hands you the means to lay conventional 2D effects, paint among them, onto a 180 distorted clip.

Rotation Order These buttons set the sequence in which the rotations happen about each axis. Take XYZ, for instance: it spins first about the X axis (pitch/tilt), next about the Y axis (pan/yaw), and finally about the Z axis (roll). You may settle on whichever of the six possible orderings you like. Rotation These dials turn the spherical image about each of the X, Y, and Z axes, giving you separate command over pitch/tilt, pan/yaw, and roll in turn.

### Common Controls

Settings Tab Across the other VR nodes, the Inspector's Settings tab shows up again unchanged. A full account of these common controls waits at this chapter's close, in the “The Common Controls” section.

### PanoMap [PAM]

### The PanoMap node

NOTE: The VR category, together with the PanoMap node, exists solely within Fusion Studio and DaVinci Resolve Studio.

### PanoMap Node Introduction

What the PanoMap node does is translate images from one spherical layout into another — say, turning a cube map into an equirectangular format. While converting, the node is also able to rotate the spherical images.

### Input

Two inputs sit on the PanoMap node. Its orange input takes a 2D image in equirectangular, cube map or other spherical formats. An effect mask input exists too, though VR nodes seldom call for it. Image Input: The orange Image input takes a spherical-formatted 2D RGBA image, which then gets converted into another spherical format. Effect Mask: An effect mask input is on hand here, even if VR nodes make little use of it.

### Basic Node Setup

For the example below, a Loader node holding a Lat Long image links into the input of a PanoMap node. The PanoMap node then converts that image into an H-Cross format, after which it links into whichever image-processing operation you require.

A PanoMap used to convert from one VR format to another

### Inspector

### The PanoMap Controls tab

### Controls Tab

The Controls tab is where you set both the format of the incoming image and the output format you're after.

### From/To

- Auto: Auto reads the incoming image layout off the metadata and the image frame aspect.
- VCross and HCross: VCross and HCross are a cube's six square faces arranged into a cross, either vertically or horizontally, the forward view sitting at the cross's middle within a 3:4 or 4:3 image.
- VStrip and HStrip: VStrip and HStrip are a cube's six square faces set vertically or horizontally in a row, sequenced Left, Right, Up, Down, Back, Front (+X, -X, +Y, -Y, +Z, -Z) within a 1:6 or 6:1 image.
- LatLong: LatLong is one 2:1 image carrying an equirectangular mapping.
- VR 180 is a 1:1 180 degree stereoscopic image.
- Immersive is the format used by Apple Vision Pro.

Rotation Order These buttons set the sequence in which the rotations happen about each axis. Take XYZ, for instance: it spins first about the X axis (pitch/tilt), next about the Y axis (pan/yaw), and finally about the Z axis (roll). You may settle on whichever of the six possible orderings you like. Rotation These dials turn the spherical image about each of the X, Y, and Z axes, giving you separate command over pitch/tilt, pan/yaw, and roll in turn.

### Common Controls

Settings Tab Across the other VR nodes, the Inspector's Settings tab appears once more unchanged. These common controls get a thorough write-up at the end of this chapter, within the “The Common Controls” section.

### Spherical Camera [3SC]

### The Spherical Camera node

### Spherical Camera Node Introduction

You won't find the Spherical Camera in the Effects Library's VR category — it lives in the 3D category instead. Even so, because it sees regular use in building and repairing VR content, it gets a mention here. The Spherical Camera lets the 3D Renderer node put out an image spanning every viewing angle, arranged across a handful of formats. Such an image might serve as a skybox texture or a reflection map, say, or be viewed inside a VR headset. The Image Width setting on the 3D Renderer determines how big each square cube face is, so that the finished image can come out as a multiple of that size both across and down. To read further about the Spherical Camera node, turn to Chapter 89, "3D Nodes," within the DaVinci Resolve Reference Manual, or to Chapter 29, over in the Fusion Reference Manual.

### Spherical Stabilizer

### The Spherical Stabilizer node

NOTE: You'll find the VR category and the Spherical Stabilizer node in Fusion Studio and DaVinci Resolve Studio alone.

### Spherical Stabilizer Node Introduction

Because VR live action so often relies on handheld cameras, shaky footage tends to be a recurring headache. The Spherical Stabilizer node finds and tracks visible features in the footage on its own, then studies how they move to work out pan, tilt, and roll rotations. With the tracking complete, you can then smooth or steady the footage's rotation.

### Inputs

A lone orange input sits on the Spherical Stabilizer node. Image: This orange image input node needs a spherical-layout image; acceptable forms include Lat Long (2:1 equirectangular) VR 180, Horizontal/Vertical Cross, and Horizontal/Vertical Strip.

### Basic Node Setup

For the example below, a 2:1 Lat Long image links into the input of the Spherical Stabilizer node. After the image has been stabilized, what the Spherical Stabilizer node puts out is a steadied clip.

A Spherical Stabilizer configured to settle a 2:1 Lat Long clip Inspector

### The Spherical Stabilizer Controls tab

### Controls Tab

On the Controls tab sit the parameters that kick off the tracking and shape the results toward stabilization or smoothing. Reject Dominant Motion Outliers While Tracking When this control is switched on (which is the default), any features moving against the grain of the majority get disregarded. Doing so helps the node tune out the movement of the shot's subjects, favoring instead the steady, dependable markers of the surroundings.

Track Controls Pressing these buttons launches the tracking and analysis of the shot. Keep in mind that the reference frame for stabilization is taken to be the first frame that gets tracked.

- Track Backward from End Frame begins running the track in reverse, beginning at the end of the current render range.
- Track Backward from Current Time begins running the track in reverse, beginning at the current frame.
- Stop halts tracking while keeping every result gathered up to that point.
- Track Forward from Current Time begins running the track forward, beginning at the start of the current render range.
- Track Forward from Start Frame begins running the track forward, beginning at the current time.

### Append to Track

- Replace makes the Track Controls throw out whatever tracking results came before and put the freshly created track in their place.
- Append tacks the new tracking results onto any tracks made earlier.

Stabilization Strength This control adjusts how much smoothing or stabilization gets applied, running from 0.0 (no change) up to 1.0 (maximum). Smoothing The Spherical Stabilizer node is able to strip every bit of rotation from a shot, locking the forward viewpoint (Still mode, 0.0), or it can gently iron out any panning, rolling, or tilting to make viewing more comfortable (Smooth mode, 1.0). The slider lets you pick either extreme or land anywhere between them. Offset Rotation A shot is frequently a touch off-level and needs its horizon straightened, or perhaps you want to bring a deliberate pan back in once the shot has been fully stabilized. The Offset Rotation controls give you extra hands-on command over how the Spherical Stabilizer rotates the footage, covering pitch/tilt (X), pan/yaw (Y), and roll (Z) in turn. That rotation always runs in the order X, Y, Z.

### Common Controls

Settings Tab Across the other VR nodes, the Inspector's Settings tab turns up again unchanged. A detailed account of these common controls appears just below, in the “The Common Controls” section.

### The Common Controls

The nodes that take on VR operations have a set of identical controls in the Inspector in common. What follows lays out the controls shared across the VR nodes.

### Inspector

### The VR Common controls

### Settings Tab

Every tool in the VR category carries the Settings tab within the Inspector. Its controls stay the same and behave identically from one tool to the next. Apply Mask Inverted Switching on the Apply Mask Inverted option flips the whole mask channel for that tool. The mask channel itself is the pooled outcome of every mask either fed into or produced within a node. Use GPU There are three settings on the Use GPU menu. Choosing Disable shuts off hardware-accelerated rendering that would otherwise use your computer's graphics card. Auto draws on a capable GPU when one is on hand and drops back to software rendering whenever a capable GPU isn't.

Hide Incoming Connections Ticking this checkbox lets you conceal the connection lines coming from upstream nodes, which makes a node tree read more cleanly and clearly. With it on, the Inspector shows an empty field for each input on a node. Drag a connected node out of the node tree into that empty field and the incoming connection line stays hidden for as long as the node isn't selected within the node tree. Select the node in the node tree, though, and the line shows again. Comments You use the Comments field to attach notes to a tool. Click into the empty field and type your text. Once a note is on a tool, a small red square shows in the node's lower-left corner while the full tile is on view, or a small text bubble icon shows on the right when nodes are collapsed. To read the note in the Node Editor, rest the mouse pointer on the node so the tooltip appears. Scripts Every tool in Fusion offers three Scripting fields on the Settings tab. Each holds an edit box into which you place scripts that execute as the tool renders. To learn more about scripting nodes, please refer to the Fusion scripting documentation.
