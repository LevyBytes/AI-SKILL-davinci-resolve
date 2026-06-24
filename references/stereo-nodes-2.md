# Stereo Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Foreground Disparity (Pick from Left Eye) Once the camera Mode sits on Artistic, you gain a Foreground Disparity slider. It holds the disparity belonging to the nearest foreground object. The depth value named in the Foreground Depth control is where it gets mapped. Should any object's disparity fall beyond the range [ForegroundDisparity, BackgroundDisparity], its disparity gets clamped to that range, which flattens patches of the Z channel, so be sure the values you choose bracket the true disparity range. Background Disparity (Pick from Left Eye) Once the camera Mode sits on Artistic, a Background Disparity becomes available. It holds the disparity belonging to the farthest background object. The depth value named in the Background Depth control is where it gets mapped. Picture this input as the ceiling on disparity values for objects sitting at -infinity. The value here is meant for the left eye. Over in the right eye, the matching value carries the same magnitude but flips negative. Foreground Depth This is where Foreground Disparity ends up mapped. Read it as the depth of the closest object. Bear in mind the values here run positive in depth. Background Depth This is where Background Disparity ends up mapped. Read it as the depth of the farthest object. Falloff Falloff shapes the depth curve stretching between the foreground and background depths you asked for. With Hyperbolic chosen, the disparity-depth curve roughly follows depth = constant/ disparity. With Linear chosen, the curve follows depth = constant \* disparity. Hyperbolic leans toward stressing Z features up front, whereas linear hands foreground and background features equal weight in the Z channel. Absent a particular reason, go with Hyperbolic, since it tracks physics more closely, while Linear bears no relation to nature and exists purely for artistic effect.

### Common Controls

Settings Tab The Inspector's Settings tab is mirrored on the other Stereo nodes as well. A full rundown of these common controls sits at this chapter's end inside the "The Common Controls" section.

### Global Align [GA]

### The GlobalAlign node

NOTE: You'll only find the Global Align node within Fusion Studio and DaVinci Resolve Studio.

### Global Align Node Introduction

Unlike Stereo Align, this node makes no use of optical flow whatsoever. Its purpose is to give you a quick, handy means of basic stereo alignment across X and Y plus rotation. Slotting Global Align in at the start of the node chain helps you visually fix big gaps between the left and right eye ahead of computing Disparity. Hand-correcting large left-right discrepancies, along with laying down an initial color match, lets Disparity turn out more accurate results.

### Inputs

You wire the left and right images into the two inputs on the Global Align node. Left Input: Either the left eye image or the stack image hooks into the orange input. Right Input: The right eye image hooks into the green input. That input shows up only while the Stack Mode menu is set to Separate.

### Outputs

Differing from most Fusion nodes, Global Align carries two outputs, one per eye. Left Output: Out of this comes the freshly aligned left eye image. Right Output: Out of this comes the freshly aligned right eye image.

### Basic Node Setup

The usual home for Global Align is right at the top of the node tree. In the example below it goes in between the left and right eye images and the Disparity node so major differences can be visually corrected.

A Global Align node put to work hand-fixing mismatches between the left and right eyes

### Inspector

### The Global Align Controls tab

### Controls Tab

Translation and rotation controls for hand-aligning the stereo images live in the Controls tab.

### Translation X and Y

- Balance: Sets how the global offset gets laid onto the stereo footage.
- None: No translation is applied.
- Left Only: Only the left eye moves; the right eye stays put.
- Right Only: Only the right eye moves; the left eye stays put.
- Split Both: The two eyes shift in opposing directions.

Snap to Nearest Pixel As you turn the X or Y shift dial, this option keeps the image shifting in whole-pixel steps alone so quality stays at its best. Doing so sidesteps sub-pixel rendering of the image, which could bring on faint blurring.

### Rotation

- Balance: Sets how the global rotation gets laid onto the stereo footage.
- None: No rotation is applied.
- Left Only: Only the left eye turns; the right eye stays put.
- Right Only: Only the right eye turns; the left eye stays put.
- Split Both: The two eyes rotate in opposing directions.

Angle The rotation's angle gets set with this dial. Remember the outcome hinges on the Balance settings. Rotate only one eye by, say, 10 degrees and that eye receives the full 10-degree turn. Rotate in Split mode and one eye picks up a -5 degree turn while the other gets a +5 degree one. Translation Filter Method Depending on what your footage contains, this menu picks the filter method that yields the best results.

Visualization This control offers various color encodings of the left and right eye, a convenient way to inspect what the controls above did without tacking on an extra Anaglyph or Combiner node. Switch it to None for the final output. Stack Mode Sets the way the input images stack. Switched to Separate, the right input and output surface and you must connect distinct left and right images. Swap Eyes Under Stacked Mode, the left and right images of stereo pairs can be exchanged.

### Common Controls

Settings Tab This Inspector Settings tab also turns up on the rest of the Stereo nodes. You'll find these common controls covered thoroughly toward the chapter's close in the "The Common Controls" section.

### New Eye [NE]

### The New Eye node

NOTE: Only Fusion Studio along with DaVinci Resolve Studio offers the New Eye node.

### New Eye Node Introduction

By interpolating between two existing stereo images via the embedded disparity channels, the New Eye node builds a brand-new image. The node can also swap one view for a warped rendition of the other. Under Stack Mode, the L and R outputs put out the same image. Mapping the left eye onto the right eye to replace it is possible. That can come in handy while clearing errors from particular regions of the frame. Rather than interpolate the aux channels, New Eye wipes them out. The disparity channels in particular get consumed/destroyed. Tack on another Disparity node after the New Eye whenever you need Disparity generated for the realigned footage.

### Inputs

You wire the left and right images into the two inputs on the New Eye node. Left Input: Either the left eye image or the stack image hooks into the orange input. Right Input: The right eye image hooks into the green input. That input appears only while the Stack Mode menu is set to Separate.

### Outputs

Differing from most Fusion nodes, New Eye carries two outputs, one per eye. Left Output: This puts out the left eye image bearing a new disparity channel, or a Stacked Mode image bearing a new disparity channel. Right Output: This puts out the right eye image bearing a new disparity channel. You'll see that output only if Stack Mode sits on Separate.

### Basic Node Setup

In the example that follows, the New Eye node builds a fresh image by interpolating across the two stereo images using their embedded disparity channels.

A New Eye node builds a fresh stereo image out of embedded disparity Inspector

### The New Eye Controls tab

### Controls Tab

Identical sets of parameters for the left eye and the right eye divide up the Controls tab. With these parameters you pick which eye to rebuild and the methods the interpolation uses. Enable The Enable checkbox lets you turn the left or right eye on by itself. Whichever eye is enabled gets swapped by New Eye for an interpolated one. Say the left eye is your "master" and you're rebuilding the right eye: you'd switch the left eye off and the right eye on.

Lock XY Holds the X and Y interpolation parameters together. Unlock them and you may feed separate interpolation factors that draw on the X and Y disparity. For instance, working on the right eye with the X Interpolation slider at 1.0 and the Y Interpolation slider at -1.0 effectively maps the left eye onto the right eye while keeping it vertically aligned to the left eye. XY Interpolation Factor Interpolation sets where the interpolated frame lands relative to the two source frames: a slider sitting at -1.0 yields the frame Left, while one at 1.0 yields the frame Right. At 0.0 the slider yields a result midway between Left and Right. Depth Ordering Depth Ordering decides which portions of the image render on top. Warping images frequently produces overlap. Where the image overlaps itself, two choices govern which values draw on top.

- Largest Disparity On Top: Within the overlapping sections, the bigger disparity values are what render in front.
- Smallest Disparity On Top: Within the overlapping sections, the lesser disparity values are what render in front.

Clamp Edges In some situations this option clears away the transparent gaps that can show up along the edges of interpolated frames. Clamp Edges brings a stretching artifact to the frame's edges, most noticeable as objects pass through it or as the camera moves. Given those artifacts, it's wise to reach for Clamp Edges only to patch small gaps around an interpolated frame's borders. Softness Cuts down the stretchy artifacts that Clamp Edges might bring in. With more than one of the Source Frame and Warp Direction checkboxes switched on, the stretching effect near the edges can double up. There, hold softness fairly low, somewhere near 0.01. With just one checkbox on, a bigger softness of about 0.03 works. Source Frame and Warp Direction This node's output comes from blending as many as four separate warps. You may draw on the color values from the left or right frame paired with the Forward (left > right) Disparity or the Backward (right > left) Disparity. At times you'll want to replace an eye that already exists. To regenerate the right eye, for example, you'd rely solely on left eye warps. Trying out the various options to find which looks best is worthwhile. Drawing on both the left and right eyes can plug gaps along the left/right side of images. Drawing on both the Forward/Backward Disparity can produce a doubling-up effect wherever the disparities clash.

- Left Forward: Grabs the Left frame, then interpolates the new frame via the Forward Disparity.
- Right Forward: Grabs the Right frame, then interpolates the new frame via the Forward

Disparity.

- Left Backward: Grabs the Left frame, then interpolates the new frame via the Back Disparity.
- Right Backward: Grabs the Right frame, then interpolates the new frame via the Back Disparity.

### Common Controls

Settings Tab On the other Stereo nodes too, this Inspector Settings tab is reproduced. Detailed coverage of these common controls waits at the end of this chapter within the "The Common Controls" section.

### Splitter [Spl]

### The Splitter node

NOTE: The Splitter node ships only with Fusion Studio plus DaVinci Resolve Studio.

### Splitter Node Introduction

A stacked input image—say one the Combiner produced—goes into the Splitter, which then hands back two output images: one left eye and one right eye.

### Inputs

You wire the left and right images into the two inputs on the Splitter node. Left Input: A stacked stereo image hooks into the orange input.

### Outputs

Differing from most Fusion nodes, the Splitter node carries two outputs, one per eye. Left Output: Out of this comes the left eye image. Right Output: Out of this comes the right eye image.

### Basic Node Setup

In the diagram below, a stacked stereo image feeds the input of a Splitter, from which a left and a right eye emerge.

A Splitter node pulls a left and a right image out of one stacked stereo image

Inspector

l The Splitter Controls tab Controls Tab You use the Controls tab to declare the kind of stacked image wired into the node's input. Split Three options for setting the stacked input image's orientation live in the Split menu.

- None: Nothing happens. Both outputs carry an image identical to the one that came in.
- Horiz: The node looks for a horizontally stacked image. The upshot is two output images, each

spanning half the width of the source image.

- Vert: The node looks for a vertically stacked image. The upshot is two output images, each

spanning half the height of the source image. Swap Eyes Lets you flip the left and right eye outputs with ease.

### Common Controls

Settings Tab Across the other Stereo nodes as well, this Inspector Settings tab is duplicated. A thorough description of these common controls appears at the chapter's end in the "The Common Controls" section.

### Stereo Align [SA]

### The StereoAlign node

NOTE: Access to the Stereo Align node is limited to Fusion Studio and DaVinci Resolve Studio.

### Stereo Align Node Introduction

Remarkably flexible for sorting out Stereo trouble, this node can carry out any of the following actions, or mixes of them:

- Vertical alignment of one eye to the other
- Changing the convergence
- Changing the eye separation

Folding these operations into a single node lets you run them with just one image resampling. At heart, picture this node as scaling and translating the disparities, then leaning on those modified disparities to interpolate across the views. NOTE: Shifting the eye separation can open up holes, and filling them may prove impossible when the needed information isn't present in either image. Even where that information exists, the disparity might have mismatched the holes. Filling the holes by hand may be necessary. Only the RGBA channels are touched by this node.

TIP: Instead of interpolating the aux channels, Stereo Align destroys them. The disparity channels especially get consumed/destroyed. Place another Disparity node after the StereoAlign whenever you want Disparity generated for the realigned footage.

### Inputs

You wire the left and right images into the two inputs on the Stereo Align node. Left Input: Either the left eye image or the stack image hooks into the orange input. Right Input: The right eye image hooks into the green input. That input is on hand only while the Stack Mode menu is set to Separate.

### Outputs

Differing from most Fusion nodes, Stereo Align carries two outputs, one per eye. Left Output: Out of this comes the left eye image fitted with a fresh disparity channel, or else a Stacked Mode image fitted with one. Right Output: Out of this comes the right eye image fitted with a fresh disparity channel. That output is visible only if Stack Mode sits on Separate.

### Basic Node Setup

In the example below, the Stereo Align takes in the left and right eye images along with disparity. After the adjustments are done, another Disparity node follows it to produce disparity for the realigned footage.

A Stereo Align node wipes out the disparity channel, hence another Disparity node sits downstream of it Inspector

### The Stereo Align Controls tab

### Controls Tab

Vertical Alignment This option sets how the vertical alignment gets divided between the two eyes. Customarily the left eye is held untouchable and the right eye is aligned to it so resampling artifacts are avoided. While doing per pixel vertical alignment, roughly pre-aligning the images with a global Y-shift ahead of disparity computation can help, because the disparity generation algorithm may struggle to resolve small objects that travel large distances. Mind the lens distortion as well: even two perfectly vertically aligned cameras still show vertical disparities owing to lens distortion. The sound practice is to strip the lens distortion out before the disparity is computed. Carry out a vertical alignment of the right eye and you've essentially pulled the Y-component of the lens distortion from the right eye, which then looks wrong later when you go to distort it once more.

### Apply to

- Right: Only the right eye is adjusted.
- Left: Only the left eye is adjusted.
- Both: Across both the left and right eyes, the vertical alignment is shared evenly.

### Mode

- Global: To match up, the eyes are merely nudged up or down by the Y-shift.
- Per Pixel: Leaning on the disparity, the eyes get warped pixel by pixel to bring them into vertical alignment.

Bear in mind this may bring on sampling artifacts and edge artifacts. Y-shift Y-shift is on hand only while the Mode menu sits on Global. To land a match you can either tune the Y-shift by hand, or else drag the Sample button onto the viewer so it draws from the left eye's disparity channel. Recall too that, if you use this node to alter disparity, the Sample button is off-limits while you view the node's output. Snap to Whole Pixels Turning this option on snaps the global shift to whole pixels. With it on, no resampling of the image occurs; instead a plain shift happens, so there's no softening or image degradation. Convergence Point The Convergence Point section serves as a global X-translation of the L/R images. Apply to This menu decides which eyes convergence touches. You may aim the convergence at the left eye, the right eye, or split it between the two. Usually this ends up on Split. Set the eyes to Split and the convergence gets shared 50-50 across both eyes. Splitting the convergence over both eyes hands you half the shift in each, which in turn yields smaller holes and artifacts to clean up later. The cost is that you've resampled both eyes rather than holding one eye as a pure reference master. X-shift You can either move the slider to tune the X-shift by hand for a match, or use the Sample button to draw from the disparity channels for easy point-to-feature alignment. Snap This option lets you snap the global shift to whole pixels. In this mode, no resampling of the image happens; rather a plain shift takes place, so there's no softening or image degradation. Eye Separation Eye Separation alters the gap between the left/right eyes, making objects in the left/right eyes converge or diverge more according to how far they sit from the camera. The effect matches the Eye Separation option found in the Camera 3D node.

Separation This is a scale factor for eye separation.

- At 0.0, the eyes go untouched.
- Push it to 0.1 and, in each eye, every scene object's shift grows by 10%.
- Push it to 0.1 and every object's shift is scaled down by 10%.

In contrast to the Split option for vertical alignment, which shares the alignment effect 50-50 over both eyes, the Both option lays 100-100 eye separation onto both eyes. While altering eye separation, turning on per-pixel vertical alignment is frequently wise; without it, interpolation drawing on both frames can produce a doubled-up result. Left/Right Eye Options Independently for the left and right eye, the left and right eye options hold depth ordering and warp direction controls. Depth Ordering Depth Ordering decides which portions of the image render on top. Warping images often produces overlap. Where the image overlaps itself, two choices govern which values draw on top.

- Largest Disparity On Top: In the sections that overlap, the higher disparity values get drawn frontmost.
- Smallest Disparity On Top: In the sections that overlap, the lower disparity values get drawn frontmost.

Clamp Edges Under some conditions this option removes the transparent gaps that can appear at the edges of interpolated frames. Clamp Edges introduces a stretching artifact near the frame's edges, especially noticeable as objects move through it or as the camera moves. On account of those artifacts, it's smart to apply Clamp Edges only for patching small gaps around an interpolated frame's edges. Edge Softness Tones down the stretchy artifacts that Clamp Edges might introduce. With more than one of the Source Frame and Warp Direction checkboxes on, the stretching effect near the edges can double up. In that case keep softness fairly low, around 0.01. With only one checkbox on, a larger softness near 0.03 is fine. Source Frame and Warp Direction Blending up to four different warps yields this node's output. You may use the color values from the left or right frame together with the Forward (left > right) Disparity or the Backward (right > left) Disparity. Now and then you'll want to replace an eye that's already there. To regenerate the right eye, say, you'd use left eye warps alone. Experimenting with the various options to see which gives the best effect pays off. Calling on both the left and right eyes can plug gaps along the left/right side of images. Calling on both the Forward/Backward Disparity, meanwhile, can yield a doubled-up effect wherever the disparities disagree with one another.

- Left Forward: Draws on the Left frame and the Forward Disparity to interpolate the resulting frame.
- Right Forward: Draws on the Right frame and the Forward Disparity to interpolate the resulting frame.
- Left Backward: Draws on the Left frame and the Back Disparity to interpolate the resulting frame.
- Right Backward: Draws on the Right frame and the Back Disparity to interpolate the resulting frame.

Stack Mode Under Stack Mode, the L and R outputs put out the same image. With High Quality off, the interpolations rely on nearest-neighbor sampling, giving a "noisier" result. To be sure High Quality is on, right-click beneath the viewers near the transport controls and pick High Quality off the pop-up menu. Swap Eyes Makes exchanging the left and right eye outputs effortless.

### Common Controls

Settings Tab On the remaining Stereo nodes this Inspector Settings tab is likewise present. Detailed write-ups of these common controls come at the chapter's end within the "The Common Controls" section.

### Example

Different settings for Eye Separation…

…and example settings for Convergence

### Z To Disparity [Z2D]

### The Z To Disparity node

NOTE: Fusion Studio and DaVinci Resolve Studio are the only places the Z To Disparity node appears.

### Z To Disparity Node Introduction

Handed a stereo camera plus an image carrying a Z channel, Z To Disparity returns that same image now holding disparity channels. It's handy for building a Disparity map out of CG renders, one that will beat the accuracy of the Disparity map the Disparity node makes.

### Inputs

You wire the left and right images plus a camera node into the three inputs on the Z To Disparity node. Left Input: Either the left eye image or the stack image hooks into the orange input. Right Input: The right eye image hooks into the green input. That input is on hand only while the Stack Mode menu is set to Separate. Stereo Camera: A stereo perspective camera connects through the magenta input; that can be a Camera 3D set with eye separation, or alternatively a tracked L/R Camera 3D.

### Outputs

Differing from most Fusion nodes, Z To Disparity carries two outputs, one per eye. Left Output: Out of this comes the left eye image now holding a fresh disparity channel, or else a Stacked Mode image equipped the same way. Right Output: Out of this comes the right eye image now holding a fresh disparity channel. That output is visible only if Stack Mode sits on Separate.

### Basic Node Setup

In the example below, a stereo camera together with an image carrying a Z channel feeds a Z To Disparity node. That same image comes out bearing disparity channels.

A Z To Disparity node that accepts a Z-channel image and builds a disparity channel from it Inspector
