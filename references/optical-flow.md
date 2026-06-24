# Optical Flow (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Optical Flow

This chapter walks through the Optical Flow nodes that Fusion provides.

The shorthand printed beside each node name works in the Select Tool dialog while you hunt for tools, and it also serves in scripting references. Throughout this document, unless stated otherwise, node trees that depict MediaIn nodes in DaVinci Resolve stand in equally for Loader nodes in Fusion Studio.

### Optical Flow [OF]

### The OpticalFlow node

### Optical Flow Node Introduction

Using an Optical Flow algorithm, this node examines whatever clip feeds its input. Picture optical flow as a per-pixel motion vector that ties features together across a run of frames. Whatever optical flow it computes lands in the output’s Vector and Back Vector aux channels. Other nodes — the Vector Motion Blur or Vector Distort, say — can then draw on those channels. That said, Optical Flow has to render twice when you wire it into a Time Stretcher or Time Speed node. Those nodes expect the channels A. FwdVec and B. BackVec in that sequence, yet Optical Flow turns out A. BackVec and A. FwdVec as it processes. Should you find optical flow too sluggish, think about rendering it out to OpenEXR files via a Saver node. TIP: When the footage input flickers from one frame to the next, it pays to deflicker it first.

### Inputs

A lone orange image input belongs to the Optical Flow node. Input: A 2D image is what the orange background input takes. That image is the run of frames you want optical flow computed for. The Optical Flow node’s output carries both the image and vector channels. To view the vector channels, right-click in the viewer and pick Channel > Vectors, then Options > Normalize Color Range.

### Basic Node Setup

Whatever frames feed the background input are what the Optical Flow node examines. By trimming a Loader or MediaIn down to just the range you require, you keep it from analyzing frames it doesn’t need. From there, the node’s output can feed any node that makes use of vector channels, a Time Stretcher among them. TIP: While analyzing Optical Flow vectors, think about placing a Smooth Motion node after it with smoothing turned on for the forward/ backward vectors.

An Optical Flow node generating motion vectors on-the-fly. Alternatively, should the Optical Flow node prove too slow at analyzing the frames, consider rendering it out in an OpenEXR format through a Saver node. After that, import the rendered EXR file as a fresh image whose vector channels are already embedded.

An Optical Flow node rendered out through a Saver node.

### Inspector

### Optical Flow advanced controls

Controls Tab (Advanced) Once you drop an Optical Flow, Repair Frame, or Tween node into a Comp, a Method drop-down in the Inspector lets you pick between an Advanced GPU-based algorithm and a Classic CPUbased one. That Advanced method is the very same Optical Flow algorithm employed across other DaVinci Resolve pages. Warp Count Lowering this slider speeds up the optical flow computations. To grasp what this option does, bear in mind that the optical flow algorithm warps one image step by step until it lines up with the other. Past a certain point convergence is achieved, and any further warps simply squander computation time. You’re free to adjust this value to hasten the computations, though it’s wise to keep an eye on what the optical flow is doing as you do.

Iteration Count Lowering this slider hastens the computations. Notably, as with the Warp Count, pushing this option upward eventually hits diminishing returns and stops producing meaningfully better output. Out of the box this value is set to a level that ought to converge across every conceivable shot, and you can frequently lower it without hurting the disparity’s quality. Smoothness This governs how smooth the optical flow is. More smoothness helps with noise, whereas less smoothness teases out more detail. Half Resolution The Half Resolution checkbox exists solely to accelerate the optical flow calculation. It scales the input images down and tracks them to derive the optical flow. Controls Tab (Classic) Selecting Classic from the Inspector’s Method drop-down lets you fall back on the older CPUbased algorithm so Comps built in earlier versions stay compatible. This method can also suit certain Stereo3D processing better. With the Classic method, one slider at the top of the Inspector boosts performance by making proxies. The other parameters in the Advanced section fine-tune the Optical Flow vector calculations. Their defaults make a solid baseline. Most of the time the advanced settings need no adjustment; many of them give only small or diminishing returns. Even so, depending on how they’re set, rendering time can swing by as much as 10x. To trim process time, your best opening move is to experiment with the Proxy, Number of Iterations, and Number of Warps sliders and to switch the filtering to Bilinear. Proxy (for Tracking) The Proxy slider exists solely to speed up the optical flow calculation. It shrinks the input images by the proxy scale and tracks them to derive the optical flow. Computation time runs roughly in proportion to the image’s pixel count. So a proxy scale of 2 yields a 4x speedup, and a proxy scale of 3 yields a 9x speedup. Smoothness This dictates how smooth the optical flow comes out. Greater smoothness copes with noise, while lesser smoothness surfaces more detail. Edges This slider offers another take on smoothness, but ties it to the color channel. Its effect is essentially to set how closely edges in the flow trail edges in the color images. Set it low and the optical flow grows smoother and tends to overshoot edges. Set it high and detail from the color images begins leaking into the optical flow, which you don’t want. Edges in the flow wind up hugging the color-image edges more tightly. That can leave streaked-out edges once the optical flow is used for interpolation. As a loose rule of thumb, lower the value when you’re using the disparity to make a Z-channel for post effects such as Depth of Field. When the disparity drives interpolation instead, you might prefer a higher value.

Match Weight This control fixes a threshold governing how neighboring clusters of foreground/background pixels get matched across a span of frames. At a low value, large structural color features are what gets matched. At higher values, small sharp color variations get matched instead. A sound value for this slider usually falls in the [0.7, 0.9] range. In stereo 3D work, nudging this option higher tends to sharpen the matching where differences arise from smoothly shifting shadows or local lighting variances between the left and right images. Even so, you should still color match or deflicker the initial images where needed so they resemble one another as closely as possible. This option also assists with local variances such as lighting differences caused by light traveling through a mirror rig. Mismatch Penalty This option dictates how the penalty for mismatched regions climbs as they grow more dissimilar. The slider lets you strike a balance between Quadratic and Linear penalties. Quadratic comes down hard on large dissimilarities, whereas Linear shrugs off dissimilar matches more readily. Pushing this slider toward Quadratic tends to leave a disparity peppered with more small random variations, while Linear delivers smoother, more pleasing results. Warp Count Lowering this slider hastens the optical flow computations. Notably, the computation time scales linearly with this option. To make sense of what it does, recall that the optical flow algorithm warps one image incrementally until it agrees with the other. Once convergence is reached, further warps merely burn computation time. Fusion’s default is set high enough that convergence should always occur. You can adjust the value to speed things along, but it’s wise to watch what the optical flow is doing meanwhile. Iteration Count Lowering this slider hastens the computations. Here too, the computation time scales linearly with this option. As with the Warp Count, raising this option eventually meets diminishing returns and won’t deliver meaningfully better results. By default it’s set to a level expected to converge across all possible shots, and you can often drop it without eroding the disparity’s quality. Filtering This option steers the filtering operations applied during flow generation. Catmull-Rom filtering produces better results, but flipping Catmull-Rom on also drives the computation time up sharply.

### Common Controls

Settings Tab The Inspector’s Settings tab is mirrored across the other Optical Flow nodes as well. A full account of these shared controls appears at this chapter’s close, in the “The Common Controls” section.

### Repair Frame [REP]

### The Repair Frame node

### Repair Frame Node Introduction

Repair Frame swaps out damaged or missing frames, or pieces of frames marred by scratches or other fleeting temporal artifacts. Three frames are needed: the repair frame plus its two neighbors. You don’t need a separate Optical Flow node to make motion vectors here, because the Repair Frame node works out the optical flow itself — though that can slow processing down. Rather than passing aux channels through, Repair Frame wipes them once the computation finishes. Look to the Optical Flow node for its controls and settings details. TIP: When your footage shifts color from one frame to the next, the repair can sometimes show, since Repair Frame has to borrow color values from the surrounding frames to fill the gap. Reach for deflickering, color correction, or a soft-edged mask to cut down on artifacts like these.

### Inputs

The Repair Frame node carries two inputs. One hooks up the 2D image you want repaired; the other takes an effect mask. Input: The orange input handles the chief 2D image slated for repair. Effect Mask: A mask shape goes into the blue input — one drawn from polylines, simple primitive shapes, paint strokes, or bitmaps produced by other tools. Wiring a mask here keeps the repairs to specific regions.

### Basic Node Setup

The Repair Frame node studies the incoming MediaIn node and fixes single-frame defects such as dust or scratches.

A Repair Frame node configured to study a MediaIn node by way of its internal optical flow analysis.

### Inspector

### The Repair Frame Controls tab

### Controls Tab

The Controls tab holds options for how the frames get repaired. It carries controls for tuning the optical flow analysis too, the same ones found on the Optical Flow node. Depth Ordering Depth Ordering decides which portions of the image render on top, via either Fastest On Top or Slowest On Top. The scenarios below illustrate these options best. Take a locked-off camera shot with a car crossing the frame: the background stays put and so emits small, slow vectors, while the car emits larger, faster ones. Here the depth ordering is Fastest On Top, since the car paints over the background. Now take a shot where the camera pans to follow the car: the background carries the faster vectors and the car the slower ones, making Slowest On Top the right Depth Ordering method. Clamp Edges In some situations this option clears away the transparent gaps that can crop up at the edges of interpolated frames. Clamp Edges introduces a stretching artifact near the frame’s edges, most apparent when objects pass through it or the camera moves. On account of those artifacts, it’s best to reserve clamp edges for fixing only the small gaps around an interpolated frame’s borders. Edge Softness This slider shows up only while Clamp Edges is on. It helps tame the stretchy artifacts Clamp Edges might introduce. Turning on more than one of the Source Frame and Warp Direction checkboxes can double up the stretching effect near the edges. When that happens, keep the softness fairly low, around 0.01. With just one checkbox on, you can afford a larger softness near 0.03.

Source Frame and Warp Direction With these checkboxes you decide which frames and vectors build the in-between frames. Whatever methods you tick get blended into the final result.

- Prev Forward: Grabs the preceding frame and leans on the Forward vector to interpolate the new one.
- Next Forward: Grabs the following frame in the sequence and leans on the Forward vector to interpolate the new one.
- Prev Backward: Grabs the preceding frame and leans on the Back Forward vector to interpolate the new one.
- Next Backward: Grabs the following frame in the sequence and leans on the Back vector to interpolate the new one.

Optical Flow Options These settings adjust the optical flow analysis. Refer to the Classic and Advanced Controls section covering the Optical Flow node earlier in this chapter.

### Common Controls

Settings Tab The Inspector’s Settings tab recurs across the other Optical Flow nodes as well. You’ll find these shared controls laid out fully at the end of this chapter, under “The Common Controls.”

### Smooth Motion [SM]

### The Smooth Motion node

### Smooth Motion Node Introduction

By drawing on optical flow to consult neighboring frames, the Smooth Motion node smooths assorted AOV (Arbitrary Output Variables) channels within a clip. One use is smoothing the Disparity channel of a stereo 3D clip, where it helps cut temporal edge/fringing artifacts, but it can equally smooth a broad set of channels such as vectors, normals, and Z. The image feeding the node’s input must already hold precomputed Vector and Back Vector channels; without them, this tool writes error messages into the Console window. Tick the channels you’d like temporally smoothed. Note that if a channel you’ve marked for smoothing isn’t there, Smooth Motion neither fails nor emits any error messages. You can also turn it on the Vector and Back Vector channels; at times, though, that worsens the interpolated results when the shot holds conflicting motions or objects that move erratically, jitter, or bounce rapidly.

TIP: Stringing two or more Smooth Motion nodes together gives you extra smoothing. A single Smooth Motion node looks at the previous, current, and next frames for a total of 3; two of them look at 5 frames; and three of them look at 7. A further approach with two Smooth Motion nodes is to let the first one smooth the Vector and Back Vector channels. Then have the second Smooth Motion smooth the channels you’re after (Disparity, for example). That way the smoothed vector channels are what smooth Disparity. You might also experiment with feeding the smoothed motion channels back to smooth the motion channels.

### Inputs

A single orange image input belongs to the Smooth Motion node. Input: A 2D image is what the orange image input takes. That image is the run of images you want smooth motion computed for. It must already carry precomputed Vector and Back Vector channels, whether produced by an Optical Flow node or saved into EXR format with vector channels.

### Basic Node Setup

For the Vector and Back Vector channels it needs, the Smooth Motion node draws on the Optical Flow node’s output. From there, the Smooth Motion node can smooth those channels or the AO channels.

A Smooth Motion node drawing on the Optical Flow node’s Vector and Back Vector channels.

### Inspector

### The Smooth Motion Controls tab

### Controls Tab

On the Controls tab sit checkboxes for whichever channels you want smoothed. Should a channel you’ve marked for smoothing be absent from the input image, Smooth Motion won’t fail and won’t write any error messages to the Console. Channel Smooth Motion reaches beyond just the RGBA channels; it applies to the other AOV channels as well.

### Common Controls

Settings Tab Here too, the Inspector’s Settings tab repeats across the other Optical Flow nodes. A detailed write-up of these shared controls sits at the end of this chapter, within “The Common Controls.”

### Tween [Tw]

### The Tween node

### Tween Node Introduction

Tween rebuilds a missing frame by interpolating across two neighboring frames using the optical flow. In what it does, Tween nearly matches Time Speed and Time Stretcher. The key distinction is that it operates on two images that aren’t consecutive members of a sequence. Because of that, it can’t tap the Vector or Back Vector aux channels held in the images. The Tween node works out the optical flow on its own, so there’s no need to put an Optical Flow node ahead of it. Whatever optical flow it produces is discarded rather than written back into the output frames. Since optical flow rests on color matching, it’s wise to color correct your images to agree beforehand. Likewise, if noisy images give you grief, stripping some of the noise out in advance can help. Tween destroys any incoming aux channels. Consult the Optical Flow node for its controls and settings details.

### Inputs

The Tween node sports two image inputs plus an effects mask input. Input 0: The orange input, marked input 0, holds the frame preceding the one you’re generating. Input 1: The green input, marked input 1, holds the frame following the one you’re generating. Effect Mask: A mask shape goes into the blue input — one made from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Hooking a mask up here confines the Tween to specific regions.

### Basic Node Setup

The Tween node takes two inputs, one for each of the two frames flanking the one you’re generating. In the example below, the earlier frame, frame 01, feeds the orange input 0, while the later frame, frame 03, feeds the green input 1. The Tween node then produces frame 02 and outputs the sequence.

The Tween node takes two neighboring frames and produces the one in between.

### Inspector

### The Tween Controls tab

### Controls Tab

The Controls tab carries options for how frames get tweened. It also carries controls for adjusting the optical flow analysis, the same as those on the Optical Flow node. Interpolation Parameter This option pins down where your interpolated frame falls relative to source frames A and B. Setting the Interpolation Parameter to 0.0 produces frame A, a value of 1.0 produces frame B, and a value of 0.5 lands you midway between A and B.

Depth Ordering Depth Ordering settles which parts of the image render on top, through either Fastest On Top or Slowest On Top. The scenarios below explain these options best. Picture a locked-off camera shot with a car crossing the frame: the background holds still and so emits small, slow vectors, whereas the car emits larger, faster ones. Here Fastest On Top is the Depth Ordering, since the car paints over the background. Picture instead a shot where the camera pans to follow the car: now the background owns the faster vectors and the car the slower ones, so Slowest On Top becomes the Depth Ordering method. Clamp Edges In certain conditions this option clears the transparent gaps that may surface at the edges of interpolated frames. Clamp Edges brings on a stretching artifact close to the frame’s edges, most noticeable when objects pass through or the camera moves. Owing to those artifacts, it’s smart to apply Clamp Edges only for fixing small gaps around the borders of an interpolated frame. Edge Softness This slider appears only once Clamp Edges is on. It works to lessen the stretchy artifacts Clamp Edges may bring in. Enabling more than one of the Source Frame and Warp Direction checkboxes can double the stretching effect near the edges. When that occurs, hold the softness rather low, around 0.01. With just a single checkbox enabled, a larger softness near 0.03 is fine. Source Frame and Warp Direction Through these checkboxes you select which frames and vectors form the in-between frames. Each method you tick is blended into the result.

- Prev Forward: Pulls the preceding frame, then interpolates the new frame from the Forward vector.
- Next Forward: Pulls the following frame in the sequence, then interpolates the new frame from the Forward vector.
- Prev Backward: Pulls the preceding frame, then interpolates the new frame from the Back Forward vector.
- Next Backward: Pulls the following frame in the sequence, then interpolates the new frame from the Back vector.

Optical Flow Options These settings adjust the optical flow analysis. Refer to the Class and Advanced Controls section covering the Optical Flow node earlier in this chapter.

### Common Controls

Settings Tab As before, the Inspector’s Settings tab is replicated across the other Optical Flow nodes. The shared controls get a thorough treatment in the “The Common Controls” section that follows.

### Vector Warping Toolset (Studio Version Only)

The Vector Warping 2D imaging toolset below lets you map and warp a reference frame onto every other frame in the sequence. It proves handy for face replacements, digital makeup, sign replacements, and the like, letting you track and warp assets right alongside the background. In its most basic form, you:

- Apply VFX changes—make-up, face paint, scars, black eyes—on a single frame,
- Make sure the reference frame’s regions stay visible throughout the frames you’re tracking,
- Add Vector Warp, set the reference frame, choose Generate + Texture Map, and track the changes onto

the sequence using optical flow.

### Vector Denoise [VDn]

### The Vector Denoise node

### Vector Denoise Node Introduction

This tool performs a general-purpose averaging across neighboring frames. Though it resembles temporal noise reduction, the source pixels being averaged are motion vector compensated.

### Inputs

One orange image input belongs to the Vector Denoise node. Input: A 2D image is what the orange image input takes. That image has to come with precomputed Vector and Back Vector channels, whether made by an Optical Flow node or stored in EXR format with vector channels.

### Basic Node Setup

For the Vector and Back Vector channels it requires, the Vector Denoise node draws on the Optical Flow node’s output, then strips noise across several frames.

A Vector Denoise node drawing on the Optical Flow node’s Vector and Back Vector channels

### Inspector

### The Vector Denoise Controls tab

### Controls Tab

The Controls tab is where you adjust the Vector Denoise settings. Average: Specify the temporal window as a number of frames. Threshold: Set an upper limit so flashes and brief highlights are skipped while pixel values are averaged.

### Common Controls

Settings Tab Likewise, the Inspector’s Settings tab carries over to the other Optical Flow nodes. These shared controls are spelled out fully at this chapter’s end, in the “The Common Controls” section.

### Vector Transform [VXf]

### The Vector Transform node

### Vector Transform Node Introduction

This tool permits custom transforms on the vector channel information, so tracking data can be resized, rotated, and translated before being applied to another image or sequence. Reach for it to mimic the transfer of kinetic energy, object responses, and differences in material properties within a dynamic scene.

### Inputs

The Vector Transform node comes with an orange image input plus an attenuate mask input. Input: A 2D image is what the orange image input takes. Attenuate Mask: A mask shape is what the white input takes.

### Basic Node Setup

For the Vector and Back Vector channels it needs, the Vector Transform node draws on the Optical Flow node’s output, then transforms the vector channel information. A Vector Transform node drawing on the Optical Flow node’s Vector and Back Vector channels Inspector

### The Vector Transform Controls tab

### Controls Tab

The Controls tab is where you adjust the Vector Transform settings.
