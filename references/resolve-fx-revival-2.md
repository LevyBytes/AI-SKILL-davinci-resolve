# Resolve Fx Revival (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Variability: (Spatial patches only) Turning this parameter up makes the Fill Method less even.
- Soft Edges: Lets you ease off the patch's edges.
- Size Adjust: Lets you resize a patch once it has been made.
- Mute: Lets you switch a given patch on or off through keyframing. Handy for blemishes that surface

across only a few pixels of a shot.

- Delete Patch: Removes whichever patch is currently selected; Option-Clicking any patch

works to delete it too.

### Advanced Controls

These controls let you tailor this effect's UI.

- Clone Sticks to Mouse: With this on, drawing or dropping a Rect, Ellipse, or Patch while in Clone or Blend Clone mode jumps straight to placing the sample region, which speeds up the workflow.
- New Patches Stay Selected: With this on, a patch stays selected once you've drawn it, ready for you to refine it further.
- UI Line Thickness: Lets you set how thick the on-screen outlines appear.
- Output Mode: This shows you various views of the patched effect you're building.

It carries four options. Patched Result: The finished image, each patch mending the blemish beneath it. Patch Locations: Presents a key in which every placed patch reads white against black. Differences: Presents how each patch differs from the original image. Difference Magnitude: Presents a stronger version of that Differences view.

### Frame Replacer (Studio Version Only)

The Frame Replacer lets you recycle or merge neighboring frames to help eliminate corrupt frames or artifacts that appear for the span of a lone frame. It comes in handy for repairing issues such as a damaged film frame or a video frame marred by pixelated digital breakup.

- Replace This Frame: Ticking this box picks out the particular frame in the clip you wish to replace. It also drops a keyframe at the right spot in the clip automatically.
- Replacement Method: Lets you pick how the new frame gets made.

From Previous: Swaps in the frame right before the selected one, in effect cloning that frame. From Next: Swaps in the frame right after the selected one, in effect cloning that frame. Blend Prev/Next: Swaps in a merge of the frames sitting just before and just after the selected one. Optical Flow: Swaps in a merge of the surrounding frames built with DaVinci Resolve's optical flow technology.

### Noise Reduction (Studio Version Only)

Drawing on the Color page's Noise Reduction controls, the Resolve FX Noise Reduction splits into a pair of GPU-accelerated noise reduction types built to tame noise in troublesome clips. You can apply either method on its own or both at once, in differing amounts according to what the specific material in front of you calls for.

### Temporal NR Controls

The Temporal NR controls study the picture across several frames so as to tell noise apart from detail. Motion estimation settings let you keep moving subjects out of this process to head off unwanted motion artifacts.

- Frames Either Side: How many frames flanking the current one you want averaged in order to part detail from noise. The choice runs from 0 to 5 frames. 0 does no frame averaging; larger values do more, though at a steep rise in compute cost. A larger frame count can sharpen the analysis, yet it can also breed unwanted artifacts where the frame holds fast-moving imagery. For fast-moving imagery, a value of 1 may serve better. Should you need larger frame values but encounter artifacts, you might also tune the Motion Threshold to clear the problem.
- Motion Est. Type: Selects which method DaVinci Resolve relies on to spot motion in the picture. Faster, the default, is lighter on the processor but less precise. Picking Better can fence off motion more precisely, though it taxes the processor harder. None switches motion estimation off entirely, which applies Temporal NR across the whole picture.
- Motion Range: Three options, Small, Medium, and Large, let you state the motion speed that Motion Estimation should anticipate excluding. The Small option presumes slow subjects with little or no motion blur, letting Temporal NR reach more of the picture at a given Motion Threshold setting. The Large option presumes brisk motion whose blur covers a wider swath of the picture, which fences more of it off from Temporal NR at that same Motion Threshold setting. Pick whichever option strikes the best balance between cutting noise and inviting motion artifacts as you tune the Motion Threshold parameter.

### Temporal Threshold Controls

Through the Temporal Threshold parameters you steer which image traits receive more or less noise reduction.

- Luma Threshold: Lets you set how strongly or how lightly Temporal NR hits the image's luma component. Its scale spans 0–100, with 0 doing no noise reduction whatsoever and 100 the full amount. Push it too far and you can wipe fine detail out of the image.
- Chroma Threshold: Sets how strongly Temporal NR hits the image's chroma component. Its scale spans 0–100, with 0 doing no noise reduction whatsoever and 100 the full amount. Push it too far and you can wipe fine color detail out of the image. That said, you'll often find the Chroma Threshold can climb above the Luma Threshold while leaving artifacting less obvious.
- Luma Chroma Same Threshold: By default the Luma and Chroma Threshold parameters move as a pair, so a change to one changes both. Switch this checkbox off, though, and the two come apart, letting you apply distinct noise reduction amounts to each component of the image, keyed to wherever the noise is worst.
- Motion: Sets the threshold dividing which moving pixels count as in motion (over this threshold) from which count as static (under this threshold). With Motion Estimation in play, Temporal NR steers clear of image regions sitting above this threshold, warding off motion artifacts by withholding frame-averaging from parts of the image that are moving. Lower values hold more of the image back from Temporal NR by catching subtler movement. Higher values let Temporal NR cover more of the image by demanding quicker motion before excluding it. The choice spans 0 to 100, with 0 putting Temporal NR on no pixels and 100 on every pixel. Its default is 50, a fitting middle ground for plenty of clips. Bear in mind that pushing the Motion Threshold too high can surface artifacts in the moving portions of the image.
- Blend: Lets you fade between the image as the Temporal NR parameters shape it (at 0.0) and the image untouched by noise reduction (100.0). This parameter makes it easy to meet halfway when you're leaning on heavy temporal noise reduction.

### Spatial NR Controls

The Spatial NR controls let you even out pockets of high-frequency noise across the image while trying to hold onto detail rather than soften it. It works well at knocking down noise that Temporal NR cannot.

- Mode: The Mode drop-down menu swaps Spatial NR among three separate algorithms. Since all three share identical controls, you can flip between them on the same settings to weigh the results side by side.

Faster: Leans on a compute-light noise reduction method that holds up at lower settings but can throw artifacts once pushed to higher values. Better: Hands the Spatial NR controls a higher-quality algorithm whose output far outclasses Faster, at the cost of heavier rendering load and of barring you from splitting the Luma and Chroma Threshold sliders for separate tweaks per color component. Enhanced: Does a markedly finer job of holding image sharpness and detail as you raise the Spatial Threshold sliders to clear noise. The gain stands out most once the Spatial Threshold sliders climb to high values (where “high” lands depends on the image at hand). At lower values, the gain can read as subtler against the “Better” mode, which is lighter on the processor than the compute-hungry “Enhanced” setting. On top of that, “Enhanced” lets you split the Luma and Chroma threshold sliders so you can dial different noise reduction amounts into each color component as the image demands.

- Radius: The choices are Large, Medium, and Small. A smaller radius buys you better real-time performance and can hold up well at low Luma and Chroma Threshold values. You may, however, spot more aliasing across detailed regions when NR Threshold values stay low. Stepping the Radius up progressively yields higher quality across more visually detailed areas at high Luma and Chroma Threshold values, the trade being slower performance. For most images at medium NR Threshold settings, an NR Radius of Medium should deliver fitting quality. As with so many operations here, the quality-versus-speed balance is yours to adjust.

### Spatial Threshold Controls

Through the Spatial Threshold parameters you steer which image traits receive more or less noise reduction.

- Luma: Lets you set how strongly or how lightly noise reduction hits the image's luma component. Its scale spans 0–100, with 0 doing no noise reduction whatsoever and 100 the full amount. Push it too far and you can wipe fine detail out of the image.
- Chroma: Lets you set how strongly or how lightly noise reduction hits the image's chroma component, smoothing pockets of high-frequency noise while trying to keep significant edge detail crisp. Its scale spans 0–100, with 0 doing no noise reduction whatsoever and 100 the full amount. Push it too far and you can wipe fine color detail out of the image. That said, you'll often find the Chroma Threshold can climb above the Luma Threshold while leaving artifacting less obvious.
- Luma Chroma Same Threshold: By default the Luma and Chroma Threshold parameters move as a pair, so a change to one changes both. You can, however, split these parameters to feed different noise reduction amounts into each component of the image. Say an image goes too soft at a particular noise reduction level yet shows more color speckling than luma noise: you'd pull the Luma Threshold down to hold detail while pushing the Chroma Threshold up to clear the color noise.
- Blend: Lets you fade between the image as the Spatial NR parameters shape it (at 0.0) and the image untouched by noise reduction (100.0). This parameter makes it easy to meet halfway when you're leaning on heavy spatial noise reduction.

### Global Blend

- Blend: Lets you fade between the image with noise reduction switched off (1.0) and the image where Spatial NR together with Temporal NR sit at their present settings (0.0).

### Using Noise Reduction

The procedure below offers one way of working the Noise Reduction (NR) parameters toward a measured result. Applying noise reduction to an image: 1 Switch on Temporal NR by picking 1 to 5 frames in the Number of Frames pop-up menu. Bear in mind that adding frames sharply lengthens this effect's render time, and whether it meaningfully improves the result hinges on your material. 2 From the Motion Est. Type and Motion Range drop-down menus, pick options that match how much motion the image holds. Where motion runs heavy, you may have to go with Better and Large. Where it's light, lower settings may do. 3 Keeping Luma and Chroma Threshold linked, ease either parameter upward until noise just begins dropping within the still areas. From there, make finer moves to find the most you can apply before artifacts appear or detail goes overly soft.

4 When the image plainly carries more chroma noise than luma noise, you can break Luma/Chroma linking once luma noise reduction sits at an acceptable level, then lift the Chroma Threshold to tackle color speckling in the picture. 5 Say the balance between the highest noise reduction threshold possible and keeping motion artifacts at bay leaves you unhappy. Then it may be worth tuning the Motion Threshold setting, dropping it to leave more of the motion out of the noise reduction operation or raising it to take in more motion. Still unhappy? You can also reach for stronger Motion Est. Type and Motion Range settings. Bear in mind that Temporal NR's forte is cutting noise in the unmoving parts of the image. Once you've landed the best balance between noise reduction across the still areas and avoidance of motion artifacts across the moving ones, the moment has come to turn to Spatial NR for clearing noise throughout the rest of the picture. 6 Switch on Spatial NR by lifting either the Luma or Chroma Threshold parameters, linked by default, until you reach a fitting balance between cutting noise and an unwelcome rise in image softness. 7 Choosing the Enhanced option from the Spatial NR mode pop-up is advised, since it yields the finest results possible. It can be processor-hungry, though, so if you need better real-time performance, flip the mode to Faster and weigh the results. 8 When the image plainly carries more chroma noise than luma noise, you can break Luma/Chroma linking once luma noise reduction sits at an acceptable level, then lift the Chroma Threshold to bring more aggressive Spatial NR onto the color speckling in the picture. 9 Should you have had to push a high Spatial NR Luma or Chroma Threshold setting to knock noise down visibly, and detailed areas now look a touch chunky or aliased, you can pick a larger setting in the Radius pop-up menu to unlock a finer analysis of the scene. That brings higher visual quality, but larger NR Radius settings are processor-hungrier and can drag real-time performance down if your system lacks the GPU resources to spare. 10 Should you have settled on fitting noise reduction settings whose result still comes out too aggressive and leaves the image looking overly processed, you can try raising either the Spatial NR or Temporal NR Blend parameters (or both) so as to dissolve from whatever noise reduction each control group put in back toward the image as it stood before you added any. Try Applying Temporal NR First, then Applying Spatial NR Because Temporal NR studies several frames to isolate its noise, it generally does a better job of faithfully keeping detail in image regions with little motion. Applying Temporal NR first and getting a good result, even across only part of the image, may cut how much Spatial NR you then have to apply, lifting your final result's overall quality. Bear in mind that whereas Temporal NR excels in an image's unmoving parts but falters with subjects in motion, Spatial NR can knock down noise anywhere in the frame that falls under its threshold, motion or not. In the end, pairing the two is almost always the winning move.

### Spatial NR Radius, How Large Should You Go?

Larger NR Radius settings can sharply boost quality across high-detail regions in shots where you're running aggressive Spatial noise reduction, yet there's no need to always leap to the large Radius setting, the one offering the greatest precision. Often, while assessing an image you're applying noise reduction to, you won't even be able to make out the extra quality. You'll burn processing time on a level of correction that wasn't needed. The smart move is to judge the full-frame image on a display big enough to reveal the noise you're working on within the viewing conditions of the intended audience. Zooming way into a clip as you apply noise reduction can tempt you toward higher quality settings than the job warrants, because a wildly enlarged image detail surfaces subtle shifts you'd never catch at actual size.

### Object Removal (Studio Version Only)

A Revival category plugin that sits best on the Color page, Object Removal taps the DaVinci Neural Engine to strip an object from the frame as hands-off as it can manage. The plugin fares best on a moving object crossing a background that stays steady over time, or on lens dirt within a shot where the camera itself is moving. You'll see better outcomes with smaller objects than larger ones, though in truth the footage drives the results. A straightforward procedure for doing this follows.

### General

- Show Mask Overlay: Lets you view the very mask the Object Removal employs, picked out in red.

### Analysis

You use these controls to study the scene's motion.

- Scene Analysis: Hit this button to study the clip under the chosen parameters and swap the object for a suitable background. You'll have to hit it again whenever you alter any parameter in this section.
- Assume No Motion: When the camera sat locked off through the shot while the object traveled across it, tick this box to make the background analysis far simpler.
- Scene Mode: Offers various ways to study the scene, sharpening the read on how the region slated for replacement moves so the program can best work out how to patch the gap the removed object leaves. Background: Studies the full image apart from the object region. Boundary: Studies the boundary zone ringing the object region. Object: For studying an object that travels along with the background, like a sticker stuck on a window as the camera moves.
- Analysis Boundary: Sets how large the object's boundary is for analysis.
- Show Scene Mask Overlay: Flips the scene mask overlay on or off, letting you glimpse what's

behind the mask.

### Render

These parameters let you tune how the Object Removal merges into the background. Being heavily footage-dependent, the Object Removal plugin won't always hand you a clean result this readily. Trouble with the result surfaces as gray, whether gray fringing or solid gray flooding the replacement window. That gray flags where your current settings can't locate background content to fill the patch you're pulling out.

- Search Range: Should you spot, as you play through the analyzed result, that the object removal mask carries gray fringing on certain frames, try moving the “Search Range” slider, which is how far, in frames, from the current frame the Object Removal plugin reaches when hunting for replacement image detail. Say the Search Range is 20: it scans +/-20 frames around the current spot, 40 frames in total. With an allowance of 10 frames, every fourth frame is the one we examine. As a rule, the smallest range that still gives an acceptable result will serve you best.
- Blend Mode: When the patch fills in fine but doesn't sit well against the background, try switching the Blend mode. Linear is the default, a plain cloning operation, but you can also pick Adaptive Blend, which can do better except in those cases where the replacement patch's edges differ in color or brightness from the background.

### Clean Plate

When you see the object removal mask flooded wholly with gray on some frames, it means background fill couldn't readily be produced for those frames. Here, give the “Build Clean Plate” button a click.

- Clean Plate Source: Lets you choose where the clean plate comes from. The options are Gray Image, amounting to no source at all; Internal, which makes a “best guess” at a background to fill the frame with and weaves it together with frames that did fill in successfully; and External, which lets you pipe in your own plate from another node.
- Build Clean Plate: Carries out the construction of a fresh clean plate background driven by the Clean Plate Source parameter you've set.
- Show Clean Plate: Ticking this box lets you peer behind the mask to the clean plate sitting back there.

To remove a moving object from a clip: 1 Here, a drone crosses a long shot that's being recorded at the same time. We'll get rid of the drone by drawing a window to mark the feature for removal, then handing it to the Object Removal plugin.

The original shot with a drone that needs to be removed

For straightforward cases, the easiest route is usually to drop the Object Removal effect onto a Corrector node, since a window or qualifier inside that node can isolate the feature you mean to remove. That's the path we'll take here. 2 With the Window palette, trace a window around the object marked for removal. Windows or masks that cling fairly tightly to the feature you're removing will give you the best results. 3 Track or keyframe the window so it follows the feature you're removing. Once more, the snugger your window wraps the object being removed the better the outcome, and a little softness at the window's edge helps.

A window now isolates the object marked for removal 4 Drag the Object Removal plugin and drop it onto the node where you've just isolated the feature for removal. 5 Hit the Scene Analysis button and let the analysis run to completion. If the object you're pulling out is moving while the camera holds locked, switching on the “Assume No Motion” checkbox can sharpen your results in that case. Where your footage suits object removal well, the object drops away once analysis wraps, swapped for a seamless background drawn from detail on the neighboring frames.

### The result after object removal analysis is complete

### Patch Replacer (Studio Version Only)

The Patch Replacer offers a fast remedy when you have to “paint out” some unwanted feature from the image. If you've leaned on windows and Node Sizing for small digital paint chores, this plugin brings more options and a smoother workflow. Add the plugin and an onscreen control of two patches shows up, an arrow between them marking which patch copies into the other. The patch sitting behind the arrow is the “source” patch, which samples a part of the image, while the patch ahead of the arrow is the “target” patch, which masks the unwanted feature with pixels drawn from the source patch. Working the Patch Replacer is as easy as dragging the target patch over whatever you want to hide, scaling it to fit via the corner controls (the source patch resizes to match on its own), then dragging the source patch onto an image area that can believably fill the target patch.

(Left) Original image, (Right) Removing the thermostat with the Patch Replacer Both the source and target patches lend themselves to motion tracking through the FX tracker, which keeps this tool useful even when the subject or camera is on the move.

### Main Controls

The Fill-in Method pop-up menu is perhaps the key one, since it dictates the approach used to fill the destination patch from whatever the source patch holds. How the remaining primary controls behave shifts according to the Fill-in method you settle on.
