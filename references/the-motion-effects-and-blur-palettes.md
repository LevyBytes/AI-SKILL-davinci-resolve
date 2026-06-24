# The Motion Effects And Blur Palettes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### The Motion Effects and Blur Palettes

Here we look at the Noise Reduction and Motion Blur effects housed in the Motion Effects palette, and we dig into the Blur palette's Blur, Sharpen, and Mist features as well.

### Motion Effects Palette (Studio Version Only)

Found only in the Studio version, the Motion Effects palette holds two groups of controls for laying optical-flow-derived effects over the clips in your program. Among them are upgraded Spatial and Temporal noise reduction together with motion-estimated synthetic motion blur.

### Noise Reduction Controls

Two parameter groups give you GPU-accelerated Temporal and Spatial noise reduction, built to tame noise in troublesome clips at close to real time when your workstation has enough processing muscle. You can run either noise reduction method on its own or pair them, dialing in different amounts to suit whatever footage is in front of you. On top of that, each control group is deeply adjustable, letting you target the chroma and luma of an image with separate doses of reduction and offering plenty of choices for how that reduction gets applied.

### Noise Reduction and Motion Blur controls

### Temporal NR Controls

By studying an image over several frames, the Temporal NR controls tell noise apart from genuine detail. The motion estimation settings keep moving subjects out of that process so you avoid unwanted motion artifacts.

- Number of Frames: How many frames you'd like DaVinci Resolve to average when pulling detail away from the noise. Your choices run from 0 to 5 frames. At 0 no frame averaging happens; higher figures average across more frames but grow markedly heavier on computation the further you push them. A higher frame count also sharpens the analysis, yet it can introduce artifacts wherever the frame holds fast-moving imagery. For such fast-moving imagery, a value of 1 may serve you better. Should artifacts crop up while you need higher frame counts, try tuning the Motion Threshold to clear them.
- Motion Est. Type: Selects how DaVinci Resolve spots motion within the image. Its default, Faster, eases the processor load while sacrificing some accuracy. Picking Better excludes motion with more precision but leans harder on the processor. None switches motion estimation off entirely, so Temporal NR then covers the whole image.
- Motion Range: The trio of Small, Medium, and Large lets you tell Motion Estimation what speed of motion to anticipate excluding. With Small, the assumption is slow subjects carrying little to no motion blur, so Temporal NR reaches more of the image at any given Motion Threshold. With Large, the assumption is fast motion whose blur spans a wider area, which keeps more of the image out of Temporal NR at that same Motion Threshold. As you work the Motion Threshold parameter, settle on whichever setting best balances cutting noise against introducing motion artifacts.
- Luma Threshold: Sets how much or how little Temporal NR lands on the image's luma component. It spans 0–100, with 0 meaning no reduction whatsoever and 100 the maximum. Pushing it too far can strip fine detail out of the image.
- Chroma Threshold: Sets how much or how little Temporal NR lands on the image's chroma component. It spans 0–100, with 0 meaning no reduction whatsoever and 100 the maximum. Going too high can strip fine color detail away, though you'll often be able to push the Chroma Threshold past the Luma Threshold while artifacting stays less obvious.
- Luma/Chroma Threshold ganging: By default the Luma and Chroma Threshold parameters move as one, so changing either changes both. You can break that link, however, to feed each component its own dose of reduction wherever the noise is worst.
- Motion Threshold: Marks the dividing line between moving pixels counted as in motion (above it) and those counted as static (below it). With Motion Estimation in play, Temporal Noise Reduction stays clear of image regions above this line, so frame-averaging never touches moving areas and motion artifacts are headed off. Lower figures hold more of the image back from Temporal NR by reacting to subtler movement; higher figures admit more of the image by demanding faster motion before exclusion. The scale runs 0 to 100, where 0 applies Temporal NR to none of the pixels and 100 applies it to every pixel. Its default of 50 strikes a workable middle ground for many clips. Set the Motion Threshold too high and artifacts may surface in the moving portions of the image.
- NR Blend: Cross-fades between the image as the Temporal NR parameters shape it (at 0.0) and the image carrying no reduction at all (100.0). The parameter makes it easy to meet in the middle when your temporal noise reduction runs heavy.

### Spatial NR Controls

The Spatial NR controls iron out patches of high-frequency noise across the image while trying to hold onto detail so the picture doesn't go soft. They handle noise that Temporal NR simply can't.

- Mode: Through the Mode drop-down you flip Spatial NR among three distinct algorithms. Because every mode shares the very same controls, you can jump between them on identical settings to weigh the outcomes side by side.

Faster: Leans on a computationally light reduction technique that holds up well at lower settings but can throw artifacts once values climb. Better: Hands the Spatial NR controls a higher-quality algorithm whose results far outclass Faster, though it costs more to render and forecloses splitting the Luma and Chroma Threshold sliders for per-component tuning. Enhanced: Keeps image sharpness and detail intact far more successfully as you push the Spatial Threshold sliders up to wipe out noise. The gain stands out most once those Spatial Threshold sliders sit at high values (and what counts as “high” shifts with the image at hand). Down at lower values the gain can read as subtler next

to the “Better” mode, which taxes the processor less than the computation-heavy “Enhanced” setting. On top of that, “Enhanced” lets you split the Luma and Chroma threshold sliders apart so each color component gets the dose of reduction the image calls for. UltraNR: UltraNR is an AI-driven reduction option delivering intelligently targeted results drawn from machine learning of real-world video noise patterns, rather than leaning on any fixed mathematical formula. Its usage is covered further down.

- Radius: The choices are Large, Medium, and Small. A smaller radius runs faster in real time and still looks good when your Luma and Chroma Threshold values stay low, although low NR Threshold values may leave more aliasing in detailed regions.

Working the Radius progressively higher lifts quality inside the most detailed areas when Luma and Chroma Threshold values are high, the cost being reduced speed. For most images a Medium NR Radius pairs well with medium NR Threshold settings. As so often, there's a quality-versus-speed tradeoff you can dial.

- Luma Threshold: Governs how much or how little reduction reaches the image's luma component. It runs 0–100, where 0 means none at all and 100 the full amount. Too high a value can wipe fine detail from the image.
- Chroma Threshold: Governs how much or how little reduction reaches the image's chroma component, smoothing patches of high-frequency noise while striving to keep significant edge detail crisp. It runs 0–100, where 0 means none at all and 100 the full amount. Too high a value can wipe fine color detail away, though you'll often manage to lift the Chroma Threshold above the Luma Threshold while artifacting stays harder to spot.
- Luma/Chroma Threshold ganging: Normally the Luma and Chroma Threshold parameters travel together, so a change to one is a change to both. Unlink them, though, and you can hand each component a different amount of reduction.

Say an image softens too much at some level of reduction yet shows more color speckle than luma noise — you can drop the Luma Threshold to hold detail while lifting the Chroma Threshold to clear the color noise.

- NR Blend: Cross-fades between the image as the Spatial NR parameters work on it (at 0.0) and the image with none applied (100.0). The parameter lets you easily land in the middle when your spatial noise reduction runs heavy.

### UltraNR Noise Reduction

UltraNR is an AI-driven reduction option whose intelligently targeted results come from machine learning of real-world video noise patterns instead of any fixed mathematical formula. On badly noisy footage this mode tends to outperform the rest by a wide margin, and it edges ahead even on ordinary noise reduction too. The design aim is the sweet spot between cutting the noise you want gone and avoiding the picture-softening you don't.

An under-exposed frame of a black dog lying on a black blanket atop a black couch — pretty much the worst case for video noise, pictured above.

That same frame with UltraNR engaged in the Spatial NR settings. The Show Patch icon is active, drawing a white box around the spot where the noise pattern gets sampled.

### Using UltraNR Controls

Turning on UltraNR is as easy as choosing it from the drop-down in the Mode section of SpatialNR. From there a single click on the Analyze button has UltraNR sample a flat patch of the image on its own to gauge the Luma/Chroma noise level, then set the analysis Luma and Chroma sliders to match. Want to fine-tune further? Let Auto find the flat patch, then switch on the “Show Patch” icon. A small white outlined square shows up on your clip marking where the AI has dropped its analysis point. You can then drag that patch by hand — and nudge its size a little via the handles — across flat areas to read the Luma/Chroma noise level. Let go of the mouse button and the luma and chroma get recalculated for the box's new spot. If it still isn't right, shift the sliders to tweak the analyzed luma and chroma slightly, luma before chroma. Happy with the outcome, you can tuck the patch away.

This new UltraNR spatial-denoise mode lives on the Color page within the Motion Effects > Spatial NR pane, and it shows up inside the Resolve FX noise reduction effect too.

The UltraNR controls as they appear within the Motion Effects pane on the Color page Using Noise Reduction The steps below outline one way to work the Noise Reduction (NR) parameters toward a measured result. Applying noise reduction to an image: 1 Switch on Temporal NR by picking 1 to 5 frames in the Number of Frames drop‑down menu. Remember that adding frames pushes this effect's render time up sharply, and depending on your footage it may or may not help the outcome much. 2 Set the Motion Est. Type and Motion Range drop-down menus to match how much motion the image holds. Heavy motion may call for Better and Large; with little motion, gentler settings will often do. 3 Keeping Luma and Chroma Threshold linked, ease either one upward until noise just begins to drop in the still areas of the image, then refine in smaller steps to find the most Temporal NR you can add before motion artifacts appear or the detail you want to keep softens too much. 4 When the image clearly carries more chroma than luma noise, unlink Luma/Chroma once luma reduction looks good, then raise the Chroma Threshold for harder Temporal NR against the color speckle. 5 If the balance between maximum reduction and freedom from motion artifacts disappoints you, revisit the Motion Threshold — drop it to keep more motion out of the operation, or lift it to fold more motion in. Still unhappy? Stronger Motion Est. Type and Motion Range settings are worth a try.

(Left) the shot beforehand and (Right) the same shot once Temporal NR has cut the noise in its still regions Remember that Temporal NR shines at clearing noise from the parts of the image that don't move. Once you've struck the best balance between reduction in the still areas and freedom from motion artifacts in the moving ones, it's time to bring in Spatial NR to mop up noise across the remainder of the picture. 6 Switch on Spatial NR by lifting either the Luma or Chroma Threshold parameters — linked out of the box — until you find a fitting balance between noise loss and an unwanted rise in softness. 7 Reaching for the Enhanced option in the Spatial NR mode drop‑down is recommended, since it produces the finest results. That choice is processor‑heavy, though, so when real-time performance matters more, drop the mode to Faster and compare. 8 When chroma noise plainly outweighs luma noise, unlink Luma/Chroma at a comfortable level of luma reduction, then raise the Chroma Threshold for more aggressive Spatial NR against the color speckle.

(Left) Before and (Right) after noise reduction improves the “look” 9 Should a high Spatial NR Luma or Chroma Threshold have been needed to knock the noise back visibly, leaving detailed areas looking chunky or aliased, pick a larger value in the Radius drop-down menu so the scene gets a finer analysis. Visual quality climbs as a result, but bigger NR Radius settings demand more from the processor and can sap real-time performance when your system lacks the GPU headroom. 10 If your noise reduction settings work yet come off too strong and leave the image looking over-processed, try lifting the Spatial NR and/or Temporal NR Blend parameters to blend between the reduction each control group adds and the image as it stood beforehand.

Try Applying Temporal NR First, then Applying Spatial NR Since Temporal NR leans on several frames to isolate noise, it usually holds detail more faithfully wherever the image barely moves. Leading with Temporal NR and landing a good result — even across only part of the frame — can cut how much Spatial NR you then need, lifting the overall quality of the finished shot. Bear in mind that Temporal NR excels in an image's static regions yet loses ground on moving subjects, whereas Spatial NR can knock down noise anywhere in the frame that falls under its threshold, motion or not. In the end, pairing the two almost always proves the winning move.

### Spatial NR Radius, How Large Should You Go?

A bigger NR Radius can do wonders for high-detail regions in shots where your Spatial noise reduction is running hard, yet you don't always have to leap to the large Radius setting, which carries the highest precision. Quite often, while assessing an image under noise reduction, you simply won't perceive the extra quality, and you'll burn processing time on correction you never needed. It pays to judge the full-frame image on a display large enough to reveal the noise within the same viewing context your intended audience will have. Pushing a clip's zoom way in during noise reduction can tempt you toward higher-quality settings than the shot warrants, because a heavily magnified slice of an image surfaces subtle shifts that vanish at actual size.

### Limiting Noise Reduction in Useful Ways

Just like every other Color page correction, noise reduction can be reined in through HSL Qualification or Power Windows. That lets you aim your effort at an image's worst trouble spots — shadows and background areas, say — while leaving alone the parts you'd rather not touch, such as faces or the better-lit stretches of the frame. You can also press Spatial NR into service instead of Blur operations for a gentler kind of complexion smoothing, using the HSL qualifier or a window to single out an actor's skin tone for focused reduction.

### Controlling the Order of Operations for Noise Reduction

A dedicated node lets you drop noise reduction in anywhere along your image processing tree. When an image carries noise that your planned corrections might amplify — bumping the contrast of underexposed clips tends to bring out whatever noise lurks inside — two routes to noise reduction open up:

- Apply noise reduction at the beginning of a node tree: Tackling noise up front clears it before your intended adjustments can turn it into a problem. The picture can come out smoother, though the image's edge detail may read as a touch softer.
- Apply noise reduction at the end of a node tree: The other route is to do your adjustments first and then run noise reduction in a separate node afterward. Here the noise-reduced regions may end up a little less smooth, but the image's edge detail can look noticeably sharper for it.
- Apply noise reduction to only one color channel of an image: With the Splitter/Combiner nodes you can also confine noise reduction to a single color component. Grading a clip whose Blue channel is noisy, for instance, lets you steer reduction exactly where it counts. Singling out one color channel for reduction is likewise doable through the Channels selection

reached by right-clicking a node. Picking the channel numbers in that node that match your color space (RGB, YUV, LAB, etc.) keeps the reduction confined to just those channels. Neither outcome wins outright — which one suits you hinges on the image at hand and the look you're chasing (some shots you might want softer, others sharper). The takeaway is that DaVinci Resolve's node-based image processing puts the choice of technique in your hands. NOTE: When noise reduction and color adjustments share a single node, the noise reduction runs first and the color adjustments follow.

### Motion Blur

Drawing on optical-flow motion estimation, the Motion Blur settings graft synthetic motion blur onto clips that have none. That comes in handy when a program shot at a fast shutter speed turns out, in hindsight, to strobe too much. By reading the motion inside a clip, the Motion Blur settings can blur the image selectively according to how fast and in which direction each moving element in the scene travels.

### Motion Blur controls

A trio of parameters governs how much motion blur lands and at what quality:

- Motion Est. Type: Choosing Better maps pixels more accurately but leans harder on the processor. Faster yields a rougher approximation while going easier on the processor.
- Motion Range: Sets which speed of motion to weigh when marking out the regions that get blurred.
- Motion Blur: Push this parameter up for more motion blur on the image, pull it down for less. Its scale spans 0–100; at 0 there is no motion blur, and 100 gives the most.

### The Blur Palette

Three operating modes make up the Blur palette—blur, sharpen, and mist. Although the Blur and Sharpen modes overlap somewhat in what they do, each one carries its own controls that the others don't. As with nearly everything on the Color page, you can confine the Blur palette's work as a secondary operation via HSL Qualifiers, Windows, or Imported mattes, which makes targeting specific parts of the image straightforward. A good many of the palette's controls are built from three ganged sliders — one red, one green, one blue. Out of the box those ganged sliders shift in unison, so every color channel takes the same hit. A small white button beside each control's name unlinks the sliders, letting you push individual color channels by differing amounts.

### Blur

Blur, the default mode, lets you lay down a remarkably high-quality Gaussian blur — or an equally high-quality sharpening pass — on your image. Of the modes, this one keeps the controls simplest.

Blur Radius controls are ganged by default, but can be unganged Two linked parameter sets adjust how far the blur or sharpening reaches and how directional it is. Which of the two you get hinges on which way you move the Radius control.

- Radius: This sits at the heart of adding blur or sharpening. Left at its default of 0.50, nothing is applied to the image. Nudging the radius slider up grows the blur, while pulling it down grows the sharpness, and the floor of 0.00 delivers the sharpest possible result.

TIP: When the Radius slider is maxed at 1.00 and the image still isn't blurry enough, tack on another node and run a second blur there. Hovering over one of the bars and spinning your mouse scroll wheel will also drive the radius up.

- H/V Ratio: Adds directionality to the operation in play. Held at its default of 0.50, the image is worked equally in the horizontal and vertical directions. Raising H/V Ratio steers the effect more along the horizontal axis, while lowering it steers the effect more along the vertical axis.

### Sharpen

Even though the Blur controls can sharpen too — just lower the Radius sliders instead of raising them — the dedicated Sharpen mode hands you extra controls made specifically for shaping sharpening passes.

### Sharpening with Coring Softness and Level

- Radius: This is the central control for laying on blur or sharpening. Sitting at its default of 0.50 means no effect reaches the image. Pushing the radius slider up raises the blur all the way to a ceiling of 1.00, whereas dropping it raises the sharpness, with the floor of 0.00 yielding the maximum sharpness.
- H/V Ratio: Brings directionality to the operation in play. At its default of 0.50, both the horizontal and vertical directions of the image are worked equally. Raising H/V Ratio biases the effect toward the horizontal axis, while lowering it biases the effect toward the vertical axis.
- Scaling: Boosts how much scaling the Radius control applies during sharpening passes. For blur effects, the scaling parameter does nothing once Radius sits at 0.50 or higher.
