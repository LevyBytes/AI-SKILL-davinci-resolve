# Matte Nodes (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Within the Luma Keyer, the Controls tab gathers every parameter you use to tune how good the matte looks. Channel This menu picks which color channel drives matte creation. Pick from Red, Green, Blue, Alpha, Hue, Luminance, Saturation, or Depth (Z-buffer). Threshold On this range slider, the left-hand handle establishes the lower threshold, while the right-hand handle establishes the upper threshold. Moving them marks out a span of luminance values from which the matte is built. Anything that falls under the lower threshold setting turns black, or transparent, in the matte. Anything that climbs past the upper threshold setting turns white, or opaque, in the matte. Whatever sits inside that span produces a grayscale matte. Filter This control picks which filtering algorithm runs when a blur is applied to the matte.

- Box: The quickest option, though quality drops. Box works best when only a small amount of blur is needed.
- Bartlett: Also called a Pyramid filter, Bartlett strikes a reasonable balance between

speed and quality.

- Multi-box: Choosing this filter brings up the Num Passes slider, which hands you control over

quality. With 1 and 2 passes you get output identical to Box and Bartlett, respectively. From 4 passes upward, the look is typically on par with Gaussian, achieved faster and free of edge “ringing.”

- Gaussian: Built on a genuine Gaussian approximation, the Gaussian filter delivers superb output, though it runs a touch slower than the rest. Occasionally it may introduce a barely perceptible edge “ringing” on floating-point pixels.

Blur This applies a blur to the matte’s edge by way of whichever method you chose in the Filter menu. Set it to zero and you get a crisp, cutout-style hard edge. Raise the value and the blur grows. Clipping Mode This setting governs the treatment of edges during domain of definition rendering. It matters enormously when you blur the matte, since doing so can pull samples from parts of the image that lie beyond the current domain.

- Frame: Frame is the default, and it automatically pins the node’s domain of definition to the image’s full frame, in effect disregarding the current domain of definition. Where the upstream DoD is smaller than the frame, whatever frame area is left over counts as black/transparent.
- Domain: Choosing Domain honors the upstream domain of definition as the node applies its effect. In cases where the node uses a large filter, this can introduce unwanted clipping.
- None: Choosing None skips source image clipping entirely. As a result, any data the node needs to render its effect that ordinarily sits beyond the upstream DoD counts as black/transparent.

Contract/Expand This slider grows or shrinks the matte’s semitransparent regions. A setting above 0.0 expands the matte; a setting below 0.0 contracts it. You typically pair this control with the blur so you can soften a matte’s hard edge and cut down on fringing. Because the control touches only semitransparent regions, a matte’s hard edge is left alone. Gamma Matte Gamma drives the matte’s values up or down across the semitransparent regions. Pushing the value up makes the gray regions more opaque; pulling it down makes them more transparent. Regions of the matte that are fully black or white stay as they are. Invert Tick this checkbox to invert the matte, so every transparent region turns opaque and every opaque region turns transparent. Solid Matte Solid mattes are mask nodes or images wired into the node’s solid matte input. That solid matte goes straight onto the image’s alpha channel. As a rule, solid mattes hold out keying wherever you need things to stay opaque — say, a person with blue eyes shot in front of a blue screen. Turning on Invert flips the solid matte before the source alpha takes it in. Garbage Matte A garbage matte, too, is a mask node or image wired into the node’s garbage matte input. That garbage matte goes straight onto the image’s alpha channel. As a rule, the garbage variety strips out stray elements that resist keying, such as microphones and booms. They also serve to patch in regions that hold the key color but that you want to keep. You can’t blend garbage mattes of differing modes inside one tool. It’s common to place a Matte Control node downstream of a Keyer node to introduce a garbage matte whose effect is the reverse of the matte on the keyer. Turning on Invert flips the garbage matte before it merges with the source alpha. Post-Multiply Image Pick this option and the keyer multiplies the image’s color channels by the alpha channel it generates for that image. This option is normally on and is enabled by default. Clear this checkbox and the image can no longer be treated as premultiplied when you merge it with other images. On the Merge node, reach for the Subtractive option in place of the Additive one. To read up on these Merge node settings, turn to Chapter 95, "Composite Nodes," in the DaVinci Resolve Reference Manual, or to Chapter 35 in the Fusion Reference Manual.

### Common Controls

Settings Tab The Inspector’s Settings tab also appears in the other Matte nodes. These shared controls get a full write-up at this chapter’s close, under the “The Common Controls” section.

### Magic Mask [MagM]

The Fusion Magic Mask tool now defaults to Magic Mask v2. Its behavior lines up almost exactly with Magic Mask v2 on the Color page, apart from a few Fusion-specific interface differences. Should you want the older Magic Mask for the sake of compatibility with legacy projects, you can switch to it by ticking the Use Legacy Magic Mask checkbox down at the bottom of the tool’s inspector.

### The Magic Mask node

### Magic Mask Node Introduction

Driven by the DaVinci AI Neural Engine, the Magic Mask palette builds a mask automatically to single out one or more people or objects in the frame, steered by clicks the user applies to mark the subject to isolate. You can generate masks for a whole object or person, or for individual features of that person — their face, hair, arms, shoes, and so on. The images below illustrate these two kinds of masks with Highlight switched on in the Viewer. A red onionskin overlay reveals exactly what Magic Mask is singling out.

(Left) Magic Mask singling out skin tones alone and (right) the same tool singling out the apron alone. Notice that although the apron and the shirt are very similar in color, Magic Mask grasps the apron’s shape well enough to build the mask. Masks from Magic Mask are frequently solid enough to drive high‑quality isolated adjustments on their own, yet they won’t always come out perfect. When that happens, the Matte Finesse controls let you soften and loosen the resulting mask as much as you need in order to clean up the edge of a tricky subject you’re isolating, with help from another mask-generation method such as a qualifier key or window. For fast cleanup on a single frame, the paint tool is also there to add or take away regions of the mask by hand. When you’re isolating particular features of a person, you can additionally combine what you isolate to build precisely the mask you want. In the example above, you could isolate the face together with bare skin on the torso and arms, producing a mask for an overall skin tone adjustment that leaves out the subject’s hair and clothing. Clicks you place to identify the subject steer this entire process. The usual workflow has you making positive clicks (shown in blue) over the person or feature you want isolated. After that, if needed, you can place subtractive clicks (shown in red) over areas of the image that aren’t the person or feature you’re isolating, fixing any flaws you notice in the generated mask.

### Making Points in the Viewer

Magic Mask operates by dropping points right into the viewer. As soon as a point is laid down, the viewer immediately displays the mask you’ve built. Lay down several points to build a mask additively, and use negative points to subtract regions from the mask. Pick a frame to draw on where the object sits fully in view and unobscured. To make a positive point to add an object to a mask: Open the Magic Mask node in a viewer, then left-click and set a point on the object you want to pick. As an alternative, switch the Point Mode to Add in the Inspector and left-click to place a fresh positive point. A positive point appears in blue. To subtract an object from a mask with a negative point: Open the Magic Mask node in a viewer, then Option-left-click and drag to set a point on whatever object you want gone. As an alternative, switch the Point Mode to Subtract in the Inspector and left-click to place a fresh negative point. A negative point appears in red. To clear a point — or a whole cluster of them — out of the mask: Shift-drag around the point or cluster to select it (green), then hit the delete key. As an alternative, switch the Point Mode to Select in the Inspector, then left-click and drag a selection window across one or more points. Pressing the delete button clears them. Positive points pick out regions of like contrast and color, letting you tie intricate shapes together. Negative points subtract regions of the object you’d rather not isolate. That could be as plain as taking a car’s wheels out of a mask, or as involved as pulling specific books out of a mask of a bookshelf. Ideally you’d center both positive and subtractive clicks on the portion of the person or object you’re adding to the mask. A single point will usually pin down the object, or the part of it you mean to mask, correctly; you shouldn’t have to stack several points on one object unless it’s extraordinarily complex.

Just one blue click placed on her back masks her whole body — arms and hair included — accurately. Notably, Magic Mask v2 tells her apart from her mirror reflection, even where the two overlap.

### Inputs

In the Node Editor, the Magic Mask node carries four inputs: Input: This orange input takes a 2D image holding the luminance values you want keyed for transparency. Garbage Matte: This gray garbage matte input takes a mask shape built from polylines, basic primitive shapes, paint points, or bitmaps masks. Wiring a mask here makes the image regions inside the matte transparent. The garbage matte goes straight onto the image’s Alpha channel. Solid Matte: This white solid matte input takes a mask shape built from polylines, basic primitive shapes, paint points, or bitmaps masks. Wiring a mask here makes the image regions inside the matte fully opaque. Effect Mask: This optional blue input looks for a mask shape built from polylines, basic primitive shapes, paint points, or bitmaps masks. Wiring a mask here confines the luminance key to certain pixels. An effects mask gets applied to the tool once the tool has finished processing.

### Basic Node Setup

Magic Mask accepts RGB inputs from other nodes and lets you single out particular objects in the frame for use as a mask. The tool has tracking of the mask as it shifts over time built right in. From there you can route the Magic Mask output into any mask input.

Here a Magic Mask node sends its matte into a Color Corrector that is wired to the foreground of a Merge node Inspector

### Tracking Tab

Picture each point you’ve set as a sticky eyedropper that samples whatever image overlaps it. The mask produced by every point’s combined reading of the image is generated live across each frame of the clip. So if the camera or the subject shifts, you’ll need to motion track or otherwise reposition each point so it travels with the motion, keeping the subject correctly recognized. You’ll also want to confirm that each point can analyze what it’s meant to, and switch off any points that, for whatever reason, can’t.

- Mode: A pair of options lets you weigh quality against performance. Faster generates a lower-quality mask more quickly, well suited to garbage matting. Better generates a higher-quality, more detailed mask that demands more from the processor.
- Point Mode: The primary controls for adding and removing points that define the mask:

Add Point: With the positive eyedropper icon you set a point (blue) in the Viewer flagging an area for inclusion in the mask. Subtract Point: With the negative eyedropper icon you set a point (red) in the Viewer flagging an area to leave out of the mask. Select Points: Lets you grab points that already exist in the viewer by drawing a bounding box around one or several. Selected points turn green. Delete Point: Removes whichever points are selected.

- Tracking Controls: These buttons govern the tracking direction, listed left to right:

Track Reverse: Tracks without stopping from the current frame all the way back to the clip’s start. Track Reverse One Frame: Tracks a single frame backward, then halts. Handy when you’re tracking frame-by-frame to watch how a particularly tricky bit of motion progresses. If something breaks, you can step back to the last frame where the point tracked the subject cleanly, then drag the point to a better spot with the pointer so it follows the subject correctly. If you must, work one frame at a time, nudging the point into a better position each time it fails to follow the feature you’re isolating with it. Track Forward Then Reverse: Starting at the current frame, this tracks right through to the clip’s end, then returns to the original tracking point and runs backward to the clip’s start. Stop Tracking: Halts tracking, for those moments when the track has a problem and you want to make a change. Track Forward: Tracks without stopping from the current frame all the way to the clip’s end. Track Forward One Frame: Tracks a single frame forward, then halts. Handy when you’re tracking frameby-frame to watch how a particularly tricky bit of motion progresses. If you must, work one frame at a time, nudging the point into a better position each time it fails to follow the feature you’re isolating with it.

- Clear Points: These buttons strip every point from the chosen range:

Current: Strips points from the frame under the playhead. Range: Strips points from the chosen render range. All: Strips every point from the whole clip.

- Go To Frame: These buttons jump the playhead to the chosen frame, listed left to right:

First Frame of Tracked Area: Sends the playhead to the first tracked frame in a range of tracked frames, getting ready to track backward when untracked frames sit at the clip’s start. Reference Frame: Sends the playhead to the frame where you first drew the points. Last Frame of Tracked Area: Sends the playhead to the last tracked frame in a range of tracked frames, getting ready to track forward when untracked frames sit at the clip’s end.

- Disk Cache: These buttons let you manage what gets held in the disk cache: Regenerate All: Rebuilds the disk cache. Clear: Wipes the frames in the current cache.
- Reference Time: The Reference Time fixes the frame where the initial points get drawn. It’s likewise the moment from which tracking starts. Once set, the reference frame can’t be moved without wiping out all the tracking information that already exists.
- Processed Frames: Shows the range of frames already tracked. Start is the earliest tracked frame and end is the latest tracked frame. You can’t edit these fields.

Post-Multiply Image Pick this option and the keyer multiplies the image’s color channels by the Alpha channel it generates for that image. This option is normally on and is enabled by default. Clear this checkbox and the image can no longer be treated as premultiplied when you merge it with other images. On the Merge node, reach for the Subtractive option in place of the Additive one. To read up on these Merge node settings, turn to Chapter 95, "Composite Nodes," found within DaVinci Resolve Reference Manual; its counterpart is Chapter 35 over in the Fusion Reference Manual.

### Matte Tab

The Matte tab fine-tunes the key’s alpha, taking into account any solid and garbage masks wired into the node. While working in the Matte tab, set the viewer so it shows the Alpha channel of Magic Mask’s final output.

- Filter: Picks the Filter used to blur the matte. Box Blur: This option lays a Box Blur effect over the whole image. It’s quicker than the Gaussian blur but yields lower quality. Bartlett: Bartlett lays down a gentler, anti-aliased blur filter. Multi-Box: Multi-Box stacks a box filter across several passes to mimic a Gaussian shape. With a moderate pass count (say, four), you can land a high-quality blur, frequently quicker than the Gaussian filter and with no ringing. Gaussian: Gaussian lays down a smooth, symmetrical blur filter using a refined constant-time Gaussian approximation algorithm. Fast Gaussian: Gaussian lays down a smooth, symmetrical blur filter using a refined constanttime Gaussian approximation algorithm. This mode is the default filter method.
- Blur: This blurs the matte’s edge with a standard, constant-speed Gaussian blur. Set it to zero and you get a crisp, cutout-style hard edge. The higher the value, the heavier the blur laid onto the matte.
- Erode/Dilate: This grows or shrinks the matte. Eroding the matte exposes more of the foreground input, whereas dilating it exposes more of the background input. Settings above 0.0 dilate the matte and settings below 0.0 erode it.
- Gamma: This drives the matte’s values up or down across the semitransparent regions. Pushing the value up makes the gray regions more opaque, and pulling it down makes them more transparent. Regions of the matte that are wholly black or white stay as they are.
- Threshold: Anything under the lower threshold turns black, or transparent, in the matte. Anything over the upper threshold turns white, or opaque, in the matte. Everything inside the range keeps its relative transparency values.
- Restore Fringe: This brings back the matte’s edge around the keyed subject. Keying often clips out the subject’s edge wherever there’s hair. Restore Fringe recovers that edge while keeping the matte solid.
- Invert Matte: Tick this checkbox and the image’s Alpha channel is inverted, so every transparent region turns opaque and every opaque region turns transparent.

Solid Matte Solid mattes are mask nodes or images wired into the node’s solid matte input. That solid matte goes straight onto the image’s Alpha channel. As a rule, solid mattes hold out keying wherever you need things to stay opaque — say, a person with blue eyes shot in front of a blue screen. Turning on Invert flips the solid matte before the source alpha takes it in. Garbage Matte A garbage matte, too, is a mask node or image wired into the node’s garbage matte input. That garbage matte goes straight onto the image’s Alpha channel. As a rule, the garbage variety strips out stray elements that resist keying, such as microphones and booms. They also serve to patch in regions that hold the key color but that you want to keep. You can’t blend garbage mattes of differing modes inside one tool. It’s common to place a Matte Control node downstream of a Keyer node to introduce a garbage matte whose effect is the reverse of the matte on the keyer. Turning on Invert flips the garbage matte before it merges with the source alpha.

### Common Controls

Settings Tab The Inspector’s Settings tab also appears in the other Matte nodes. These shared controls get a full write-up at this chapter’s close, under the “The Common Controls” section.

### Matte Control [MAT]

### The Matte Control node

### Matte Control Node Introduction

Keyer nodes exist to build an alpha channel on an image that lacks one. The Matte Control node serves to combine and reshape the alpha channels carried inside images, as well as masks made by masking tools. You’ll commonly drop this node in to copy a color channel or alpha channel from the foreground input onto the background input, or to merge alpha channels from the two images.

### Inputs

In the Node Editor, the Matte Control node carries four inputs. Background: This orange background input takes a 2D image that receives the foreground image’s alpha channel (or whatever other channel you want copied to the background). Foreground: This green foreground input takes a 2D image carrying an alpha channel (or some other channel) you want applied to the background image. Garbage Matte: This gray garbage matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here makes the regions of the foreground/background combination inside the matte transparent. Solid Matte: This white solid matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here makes the regions of the foreground/background combination inside the matte fully opaque. Effect Mask: This optional blue input looks for a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here confines the matte control to certain pixels. An effects mask gets applied to the tool once the tool has finished processing.

### Basic Node Setup

In the example below, the Matte Control node is wired to copy the foreground (green) input’s alpha channel onto the background (orange) input. What the Matte Control then outputs is an alpha-bearing image that serves, within the Merge node, as the foreground composite.

### Inspector

A Matte Control routing an alpha out of the foreground input and into the background input

### The Matte Control Matte tab

### Matte Tab

The Matte tab merges and reshapes alpha or color channels drawn from an image on the foreground input together with the background image. Combine Reach for this menu to choose which operation runs. It defaults to None, meaning no operation.

- None: This makes the foreground image be disregarded.
- Combine Red: This merges the foreground red channel into the background alpha channel.
- Combine Green: This merges the foreground green channel into the background alpha channel.
- Combine Blue: This merges the foreground blue channel with the background alpha channel.
- Combine Alpha: This merges the foreground alpha channel with the background alpha channel.
- Solid: This drives the background alpha channel to become fully opaque.
- Clear: This drives the background alpha channel to become fully transparent.

Combine Operation Reach for this menu to choose the method that merges the foreground channel with the background.

- Copy: This copies the foreground source over the background alpha, overwriting whatever alpha already exists in the background.
- Add: This adds the foreground source to the background alpha.
- Subtract: This subtracts the foreground source from the background alpha.
- Inverse Subtract: This subtracts the background alpha from the foreground source.
- Maximum: This weighs the foreground source against the background alpha and keeps the value

from whichever pixel is highest.

- Minimum: This weighs the foreground source against the background alpha and keeps the value

from whichever pixel is lowest.

- And: This runs a logical AND across the two values.
- Or: This runs a logical OR across the values.
- Merge Over: This lays the foreground source channel atop the background’s alpha channel and blends the two.
- Merge Under: This tucks the foreground source channel beneath the background’s alpha channel and blends the two.

Filter Picks the Filter used to blur the matte.

- Box Blur: This option lays a Box Blur effect over the whole image. It’s quicker than the Gaussian blur but yields lower quality.
- Bartlett: Bartlett lays down a gentler, anti-aliased blur filter.
- Multi-Box: Multi-Box stacks a box filter across several passes to mimic a Gaussian shape.
