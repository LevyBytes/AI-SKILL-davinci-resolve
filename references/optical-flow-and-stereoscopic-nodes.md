# Optical Flow And Stereoscopic Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Optical Flow and Stereoscopic Nodes

This chapter walks through the wide range of stereoscopic and optical flow‑based nodes that Fusion offers, along with the workflows tied to them.

### Overview

Within Fusion you'll find 3D stereoscopic and optical flow-based nodes. They can operate jointly or on their own to build, fix, and refine 3D stereoscopic shots.

Stereoscopic comp displayed in the viewers.

### Stereoscopic Overview

Every stereoscopic capability is woven directly into Fusion’s 3D environment. A stereoscopic image may be built from one camera (which exposes eye separation and convergence distance) paired with a Renderer 3D that handles the virtual left and right eye. Alternatively, you can pair two separate cameras to act as a stereo camera rig. These stereoscopic nodes help resolve trouble that arises when shooting in 3D stereo — for instance 3D rig misalignment, mismatched mirror polarization between the images, timing sync problems across cameras, color alignment, convergence, and difficulties with eye separation. On top of that, the stereo nodes are handy for producing depth maps.

### Optical Flow Overview

Optical Flow studies how a clip moves and produces motion vectors spanning adjacent frames. The node yields X and Y vectors pointing from the prior frame to the present one (Back Vectors) plus toward the upcoming frame in the sequence (Forward Vectors). After the calculation finishes, that optical flow data feeds other nodes so you can build silky slow motion, retime clips at variable rates, fill in absent frames, and even fix disparity within stereo 3D clips. NOTE: The stereoscopic nodes on the Fusion page operate separately from the stereoscopic tooling found on the remaining DaVinci Resolve pages.

### Toolset Overview

What follows is a summary of the nodes you can reach.

### Optical Flow Nodes

- Optical Flow > OpticalFlow: Examines the movement across adjacent frames within a sequence and produces motion vectors that downstream nodes can apply for retiming, motion blur, and similar effects.
- Miscellaneous > TimeSpeed: Changes a clip's playback rate to a fixed value via Flow Interpolation mode.
- Miscellaneous > TimeStretcher: Alters a clip's rate across changing speeds via Flow Interpolation mode.
- Optical Flow > RepairFrame: Builds a fresh frame from the motion vectors that span two

neighboring frames.

- Optical Flow > SmoothMotion: Evens out the color or aux channels by leaning on motion vectors.
- Optical Flow > Tween: Blends two non-sequential images together to manufacture a new frame.
- Color > CopyAux: Moves aux channels — motion vectors included — into RGBA with greater efficiency than

Channel Booleans.

### Stereoscopic Nodes

- Stereo > Anaglyph: Merges stereo images into one anaglyph image you can view.
- Stereo > Combiner: sStacks individual stereo images into a single stacked pair

so they can be handled together.

- Stereo > Disparity: Computes disparity across left/right images.
- Stereo > DisparityToZ: Turns disparity into Z-depth.
- Stereo > Global Align: Manually nudges each stereo eye for rough alignment of stereo images.
- Stereo > NewEye: Swaps the left and/or right eye for interpolated eyes.
- Stereo > Splitter: Breaks a stacked stereo image apart into left and right images.
- Stereo > StereoAlign: Tunes vertical alignment, convergence, and eye separation.
- Stereo > ZToDisparity: Turns Z-depth into disparity.

### Working with Aux Deep Channels

Some image formats are able to hold channels beyond RGBA color; these go by the name aux deep channels. Stereo Disparity and OpticalFlow operate right on auxiliary deep channels. The aux channels that Fusion handles are:

- RGBA: The ordinary colors.
- Z: The eyespace Z coordinate tends to be negative, since in eyespace Fusion’s camera rests at (0, 0, 0) and faces down the Z-axis. The value begins at Z = 0 at the camera focal point and grows steadily more negative as objects recede deeper into the scene.
- Coverage: How much of the pixel the frontmost pixel occupies, expressed as a percentage and used for antialiased Z-compositing.
- Object ID: Integers a user assigns to meshes.
- Material ID: Integers a user assigns to materials.
- Texture Coords: Texture coordinates kept in normalized form as (u, v) pairs.
- Normal Vector: Normal vector (nx, ny, nz), whose components usually fall in the range [–1, +1].
- Background Color: What color the pixel would be once the frontmost layer is taken away, used for antialiased Z-compositing.
- Vector: A forward motion vector — an offset (vx, vy) that relates each pixel’s spot in one frame to where that same pixel lands in the following frame.
- Back Vector: A backward motion vector — an offset (vx, vy) relating each pixel’s spot in one frame to where that same pixel sat in the preceding frame.
- World Position: Where the pixel lives in world coordinates, given as (wx, wy, wz).
- Disparity: An offset (dx, dy) linking a pixel across the Left > Right or Right > Left frames.

A handful of these extra channels feed particular Fusion nodes. For instance:

- Merge can lean on the Z channel for a depth merge. When the Coverage and BackgroundColor channels exist, it handles antialiased edges more cleanly during the Z merge.
- The bulk of image-processing nodes (BrightnessContrast among them) expose options on their common controls tab that confine processing according to MaterialID and ObjectID.
- The Z channel is consumed by the Fog and DepthBlur nodes.
- The TexCoord channel is consumed by the Texture node.
- The Normal channel is consumed by the Shader node.

Inside Fusion there are a few routes for fetching or producing those extra channels. For instance:

- The Renderer3D node can produce the majority of these channels.
- The OpticalFlow node creates the Vector and BackVector channels, which TimeStretcher

and TimeSpeed are then able to consume.

- The Disparity node creates the Disparity channels, after which DisparityToZ, NewEye, and

StereoAlign nodes can consume the Disparity channels.

- The OpenEXR format lets you bring aux channels into Fusion or send them out by laying out a

mapping from EXR attributes onto Fusion Aux channels through CopyAux.

### Optical Flow Workflows

Running the Optical Flow analysis is not a real-time task; how long it takes hinges on your machine, the clip’s resolution, and how long the clip runs. For that reason the usual approach is to pre-generate the motion vectors ahead of time — running the analysis overnight or on a render farm — and store the output as an OpenEXR sequence. The Optical Flow toolset is built around four categories of nodes that respectively generate, destroy, pass through, or construct the motion vectors.

### OpticalFlow

The Optical Flow node produces the Vector and BackVector data. For best results you'd normally route the Optical Flow output into a Saver, writing the image out as OpenEXR files that hold the motion vectors inside an aux channel.

### TimeSpeed, TimeStretcher

Smooth slow-motion at either a steady or shifting rate is achievable through the TimeSpeed or TimeStretcher nodes. Whenever Optical Flow motion vectors already sit in an image’s aux channel, switching on Flow mode within the TimeSpeed or TimeStretcher Interpolation settings will exploit the Vector and BackVector channels. Flow mode needs either an upstream OpticalFlow node producing the hidden channels or an OpenEXR Loader feeding those channels in. The nodes draw on the Vector/BackVector data to interpolate the motion channel and afterward discard that data on output, because the incoming Vector/BackVector channels no longer hold. For deeper coverage of TimeSpeed or TimeStretcher, consult Chapter 111, “Miscellaneous Nodes,” within the DaVinci Resolve Reference Manual, together with Chapter 51 of the Fusion Reference Manual.

### SmoothMotion

You can apply SmoothMotion to even out the Vector and BackVector channels or to smooth disparity within a stereo 3D clip. The node passes through, alters, or creates fresh aux channels yet leaves them in place rather than destroying them.

### Repair Frame, Tween

What sets the Tween and Repair Frame nodes apart from ordinary optical flow nodes is that the OpticalFlow analysis and motion vector generation are baked right into them. Tween examines two frames and produces an in-between frame, handy for rebuilding a frame that's missing or damaged. Repair Frame inspects the frames flanking the current one and mends scratches, dust marks, and the like. Since these nodes rely on flow values across non-sequential frames, they can't reuse the optical flow held in the input image’s Vector/BackVector channels; instead they have to recompute each frame's flow, carry out their work, then discard the flow channels. As a result, these nodes are heavy on computation. For deeper coverage of Tween or Repair Frame, consult Chapter 112, “Optical Flow,” within the DaVinci Resolve Reference Manual, or else Chapter 52 of the Fusion Reference Manual.

### Advanced Optical Flow Processing

A quicker GPU-based Optical Flow algorithm ships inside the Optical Flow, Repair Frame, and Tween nodes. After you drop the Optical Flow, Repair Frame, or Tween node into a comp, the Inspector presents a Method drop-down menu from which selecting Advanced turns on the GPU-based algorithm. That Advanced method matches the very Optical Flow algorithm running on the other DaVinci Resolve pages. Picking Classic from the same Method drop-down menu in the Inspector reverts to the older CPUbased algorithm, preserving compatibility with comps built in earlier versions; that choice can also work better for certain Stereo3D processing.

### Stereoscopic Workflows

Disparity captures how the left and right image differ. Nodes draw on the Disparity map to register and fine-tune the stereo pair of images. The Disparity node studies a stereo pair of images and creates an X&Y disparity map. In practice you bring in a left and right stereo image pair and run them through the Disparity node. Once that Disparity map exists, other nodes can act on the images. TIP: While wiring stereo pairs through the node tree, confirm that the left and right images feed the left and right inputs of the Disparity node. Producing disparity, much like Optical Flow, is heavy on computation, so the standard tactic is to pre-generate these channels beforehand — overnight or on a render farm — and write them out as an EXR sequence. That philosophy shapes the whole toolset.

### Stereo Camera

A stereoscopic camera can be configured in one of two ways. The usual route is to drop in a Camera 3D and dial in the eye separation and convergence distance parameters. The alternative is to wire a second camera into the RightStereoCamera input port of the Camera 3D. As you look through the original camera or render, that connected camera supplies the right-eye content.

A stereoscopic camera setup may rely on just one camera or on a pair of linked cameras.

### Stereo Materials

The Stereo Mix material node makes it possible to hand each eye a different texture.

Material viewer showing stereoscopic material.

### Disparity

The bulk of the work in producing disparity maps falls to the Disparity node. It creates the Disparity channel and tucks it away inside the hidden aux channels of the output image.

### NewEye, StereoAlign

Both NewEye and StereoAlign consume and discard the Disparity channel as they interpolate the color channel. The hidden channels get destroyed along the way because, once the nodes have run, the original Disparity channels would be meaningless. These nodes require either an upstream Disparity node producing the hidden channels or an OpenEXR Loader feeding those channels in.

### DisparityToZ, ZToDisparity

The nodes here pass through, alter, or create new aux channels without destroying any. TIP: Should the colors vary from one shot to another, run a global alignment first with Color Corrector or Color Curves before you compute the Disparity map. Route the image you intend to alter into the orange input and the reference into the green input. Under the Histogram section of the Color Corrector, pick Match and also pick Snapshot Match Time. Within the Color Curves’ Reference section, pick Match Reference.

### Separate vs. Stack

Stereo nodes operate in either Separate or Stack modes. Under Stack mode the left/right eyes sit stacked either horizontally or vertically, yielding a single image of double width or double height respectively. What makes Stack mode appealing is that you avoid keeping duplicate branches of the Node Editor for the left and right eyes. Because of this, Stereo nodes appear with two inputs and two outputs marked “Left” and “Right.” While in Stack mode, wire the stack into the left eye input and rely on the Left output to feed downstream nodes. Under Stack mode the corresponding Right eye inputs and outputs stay hidden.

### Setting Up Stereo in the Node Editor

Generating the disparity comes first. You can arrange this inside the Node Editor in two distinct ways.

Two stereoscopic workflows.

Within the example above, the right-hand workflow takes the left and right eye, builds the disparity, and immediately calls on NewEye to produce a new eye for the image. The left-hand example renders the disparity-bearing frames out to intermediate EXR images. Those images then get pulled back into Stereo nodes and used to build the NewEye images. Computing the disparity first via Render nodes lets the later creative steps run far more quickly and interactively. While the diagram above doesn't depict it, it's generally wise to color correct the right eye toward the left eye prior to disparity generation, since that aids the disparitytracking algorithm. Perfect color matching isn't required — for instance, the “Match” option in a Color Corrector’s histogram options can handle it.

### About the Disparity Channel

Inside the Disparity channel are the displacement vectors that pair pixels from one eye with the matching pixels in the other. Vectors held in the left image’s Disparity channel map left>right; vectors held in the right image’s Disparity channel map right>left. To illustrate the left-to-right case: (xleft, yleft) + (Dleft. x, Dleft. y) -> (xright, yright). The right-to-left case follows the same pattern: (xright, yright) + (Dright. x, Dright. y) -> (xleft, yleft). For pixels that aren't occluded you'd anticipate Dleft = -Dright, though the disparity generation algorithm makes that equality only roughly true. NOTE: Disparity holds X as well as Y values because left/right images are seldom lined up perfectly in Y, even when captured through a meticulously arranged camera rig. Values for both Disparity and Optical Flow are kept as un-normalized pixel shifts. Notably, that departs from Fusion’s resolution-independent convention. The choice was made deliberately so that you needn't fuss over rescaling the Disparity/Flow values while cropping an image, nor over scale factors when importing/exporting these channels into other applications. Since the Flow and Disparity channels record values in pixel shifts, friction can arise with Proxy and AutoProxy. Fusion's rule is that, for proxied images, these channels keep unscaled pixel shifts that hold for the full-sized image. Therefore, to read the Disparity values from a script or through a probe, always remember to scale them by (image. Width/image. OriginalWidth, image. Height/ image. OriginalHeight).

### Viewing of Disparity and Vector Channels

You can show aux channels right in the viewers via the Channel viewer button’s menu. The CopyAux node serves to copy those channels straight into the RGB channels for display or downstream processing. What's nice about the CopyAux node is its static normalization, which cuts much of the flicker stemming from the viewer’s time-variant normalization. For long runs of aux channels, the CopyAux node offers an option to drop the aux channels and retain just the current RGB channels, which frees precious memory and lets you cache additional frames.

TIP: While the Channel Booleans can also copy any aux channel into RGBA, doing so takes a few extra clicks versus CopyAux. Keep in mind that aux channels are memory-hungry. A float-32 1080p image holding only RGBA occupies roughly 32 MB of memory, yet with every aux channel switched on it climbs to about 200 MB of memory.

### Stereo and Optical Flow Best Practices

Several factors — the way you assemble your composition, the images in play, and the kind of shot at hand — all influence whether Disparity generation and Optical Flow analysis succeed. Below we'll examine some scenarios worth watching for and how to sidestep common traps when working with optical flow.

### Semi-Transparent Objects

The Optical Flow and Disparity generation algorithms in Fusion presume a single layer per pixel as they track pixels from one frame to the next. Transparent objects and motion blur are especially troublesome. Take a shot soaring through clouds, with semi-transparent clouds up front and a far-off landscape behind: this baffles the Optical Flow/Stereo algorithms, which can't tell apart overlapping objects moving differently. Typically the optical flow winds up following patches of one object or the other. It stops being an issue when the transparent object and the background sit at nearly the same depth and therefore share the same disparity.

### Motion Blur

Motion blur poses a serious challenge as well, for the same reason just described. The Disparity and Optical Flow algorithms can't decide whether a pixel inside the motion blur belongs to the moving object or to the background pixel. Because these algorithms are global by nature, the vectors over the motion blur come out wrong and the algorithm also gets confused in areas neighboring the motion blur.

### Depth of Field

Depth of field is yet another difficulty tied to the previous two. Trouble shows up when a defocused foreground object sits over a background object that is in motion (the Optical Flow case) or that shifts between L/R (the Stereo Disparity case). The softened edges throw off the tracking, since it can't recognize that those edges are really two distinct objects.

### Where to Calculate Disparity and Optical Flow?

The point in your composition at which you produce optical flow or disparity can sharply alter the outcome.

For example, when you've composited a lens flare in, it's wiser to compute OpticalFlow/ Disparity ahead of it, because the semi-transparent lens flare misleads the tracking algorithms. When you're color correcting the left/right eyes to match or to deflicker, applying the OpticalFlow/Disparity afterward works better, since matching colors between frames makes it easier for the tracking algorithm to find correspondences. When you're stripping out lens distortion, weigh carefully whether to do so before or after Disparity computation. Doing it afterward turns your Disparity map into a lens distortion map too, fusing the two effects into one. The broad rule of thumb is to apply OpticalFlow/Disparity ahead of any compositing steps apart from an initial color-matching correction and a lens distortion removal.

### Cropping the Source

A general pointer: whenever you crop your input images for whatever reason, you're usually better off computing the optical flow or disparity prior to the crop and then cropping the flow/disparity alongside the color afterward. This is because flow/disparity matching thrives when shared pixel data exists in both frames; once pixels appear in only one frame (or one eye), the Disparity/ OpticalFlow nodes have to guess and fill in the gaps. The largest occlusions traveling L <–> R are normally pixels along the L/R edges of the images that shift outside the frame. The same holds for optical flow with a moving camera. Watch out, too, for black borders ringing the edges of your frames, which you ought to crop off.

### Nodes with Multiple Outputs

Plenty of the stereo nodes in the Fusion toolset carry multiple outputs, which can puzzle newcomers. A notably confusing detail is that dragging a Stereo node into the view always shows the left output. Seeing the right output is impossible unless you attach another node such as BC (BrightnessContrast) to the right output and view that instead.

### Picking from Aux Channels

Certain nodes — StereoAlign among them — let you drag-pick from the Z or Disparity auxiliary channels. You have to pick from a node upstream of the StereoAlign rather than from the StereoAlign's output. Attempting to pick a disparity from a StereoAlign node's output returns nothing, because StereoAlign consumes/destroys the Disparity aux channel (and even were the Disparity channel left intact, you'd grab the wrong value, since you'd be picking from the aligned result). A typical picking sequence goes like this: 1 Display StereoAlign within the left view. 2 Put whatever node feeds into StereoAlign on the right view. 3 Grab the Disparity value off the left eye, working in that right view.

Even though this picking behaves no differently from ordinary picking of color channels, the situation can still trip people up. As an analogy, the equivalent color-node blunder would be a user attempting to pick a gradient color for a Background node from a view that's showing that very Background node (picking a color for a node out of its own output). One more thing to mind is which eye you're picking from. The safe habit is to always pick from the left eye. That's because the Disparity channels differ between the left and right eyes, and when you pick from a horizontal/vertical stereo stack, Fusion can't tell whether your Disparity value came from the left or right eye. None of the above are strict rules — they're guidelines meant to keep you from shooting your own foot. Grasp the reasoning fully and you'll spot exceptions where everything still works — for instance, taking disparity off the left output of DisparityToZ, or pulling Z off either the left or right output of ZToDisparity.

### Vector and Disparity Channels
