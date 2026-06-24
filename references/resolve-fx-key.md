# Resolve Fx Key (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Resolve FX Key

Among DaVinci Resolve’s tools are several Resolve FX devoted to compositing and keying work, each applied straight on the Timeline.

### 3D Keyer

Built on the Color page’s 3D Qualifier, the 3D Keyer Resolve FX gives a quick, straightforward route to pulling a key that isolates a band of color in the picture by dragging your mouse pointer across the parts of the image you wish to key. Every drag across the image that adds to or trims the cloud of values carves into a three-dimensional depiction of all the colors on hand; you can view this in the tool’s Key Map box, and it is the source of the 3D Keyer’s name. TIP: Should your goal be isolating a band of luma values in the picture, the HSL or Luma keyer hands you finer control. The 3D Keyer makes a solid first choice when you’re after a key on a blue screen or green screen background. Through its workflow of dragging the mouse pointer over the screen color you want gone, with live feedback, it delivers precise control. Where the 3D Keyer shines most is the speed at which you can sample regions of the picture to lift out of the final key. That same trait can turn into a drawback, though, where your opening samples fail to yield satisfying results, since, unlike the Delta Keyer on the Fusion page, few avenues exist for tuning the key while it’s being built. On the flip side, for well-lit subjects you’re keying, two or three samples are all it takes. A handful of long strokes tend to do a finer job of consistently grabbing a band of like colors, much like a broad brush. By contrast, five to ten short strokes behave like a fine brush and will grab only a very narrow band of color you’ve marked out.

### Selection Range Controls

The Inspector’s Selection Range buttons let you set up a key by sampling Viewer pixels with the mouse pointer.

### The 3D Keyer Selection Range controls

- Picker: Picks the opening color to qualify. Strokes drawn longer tend to hand you a stronger key. On the Edit page, the Timeline Viewer Overlay has to sit at Open FX.
- Picker -: Lets you pick a further color to drop from the present qualification; also reachable by holding the Option key.
- Picker +: Picks a further color region to fold into the present qualification.
- Invert: Flips the present key; qualified regions turn unqualified and the reverse.
- Stroke: Shows the roster of picked (+) and unpicked (-) colors, alongside each one’s respective

RGB values.

- Delete Stroke: Drops whichever stroke is presently chosen in the Stroke drop-down menu.
- Reset: Clears every stroke and returns the 3D Keyer to its default state.

### Behavior Options

The basic parameters and modes of the 3D Keyer are set through these controls.

- Colorspace: Through this drop-down menu you pick whether your color sampling happens in YUV, HSL, HSP, or LAB colorspaces. YUV stands as the default, but should you find the results unsatisfactory, you can reach for another colorspace off the drop-down menu to see whether it fares better. There are assorted theoretical differences between these, yet the strongest pick always rides on the task.
- Soft: Lends the key a softer edge that proves more forgiving of Chroma and Luma adjustments. That gentler drop-off suits cases such as subtle light shifts across a face. Pair this mode with the Shadow/Midtone/Highlight Matte Finesse controls to fine tune the outcome.
- Flat: The default mode. Every color you pick is 100% keyed, with adjustments handling small color variations. This is the suggested mode for chroma keying a green or blue screen. On top of that, raising the Pre-Filter setting within the Matte Finesse controls can deliver a smoother, flatter key.
- Tight: Keys only the precise color band picked and lays on no softening drawn from color ranges. Single pixel sharpness levels are what you’d expect. This serves for tough keying work, calling for hand-tuning the filter and softness within the Matte Finesse controls.
- Luma: Behaves much like the Tight setting yet disregards all chroma data, letting you key off brightness level rather than color.
- Despill: When you’re leaning on the 3D qualifier to pull a blue or green screen key for transparency, this slider lets you dial in color correction that strips blue or green spill out of the picture while holding onto the image’s original color.

### Usage Options

The user feedback tools the 3D Keyer shows in the Viewer are governed by these settings. On the Edit page, you have to set the Timeline Viewer Overlay to Open FX.

The Key Map, sitting at the upper left, depicting a qualifier that aims to grab the background sand (blue lines) while dropping the pirate’s hats (red lines)

- Show Paths: A checkbox letting you toggle on and off whether the lines you’re drawing to sample the image stay visible. Hiding lines leaves the key untouched.
- Smart Show Paths: Tick this checkbox and the lines show only while they’re being drawn, vanishing once the mouse button is let go.
- Auto-B/W Highlight: Tick this checkbox and the Viewer flips on its own to Highlight B/W mode as a line is drawn, the better to reveal the resulting key live. Let the mouse button go and the Viewer reverts to whatever viewing mode it began in.
- Show Key Map: Tick this box to bring the Key Map into the Viewer. Two parts make up the Key Map: the Color Space box plus the Brightness Range. That Color Space box gets laid out much the way the Color Wheels are, with primary colors arranged around its rim. Which exact colors and layout appear hinges on the Color Space you settle on within the 3D Keyer. The Brightness Range shows as a bar below the Color Space, its left end black and its right end white. Inside the Color Space and Brightness Range sit the individual colors you chose by way of the pickers within the Strokes List.
- Key Map Zoom: Sets the Key Map’s zoom level, letting you reach finer detail when needed.

### Key Adjustments

This batch of tools lets you tune by hand how the key gets built from the sampled colors. What these tools do shows up in the Key Map, when it’s on.

- Chroma Tolerance: Drag left or right to widen or narrow the band of colors the key grabs.
- Chroma Softness: Drag left or right to shift how sensitive the key is to like colors it grabs. This sets whether the key acts as a hard cutoff or a soft pickup of like colors.
- Adaptive Chroma Softness: Ticking this box lets the keyer behave steadily across both heavily saturated and desaturated regions of the picture at once. Most of the time you’ll want this left on. The exception comes when you’re struggling to hand-tune chroma softness in Soft or Flat mode; switching Adaptive Chroma Softness off then hands you more range to work within. Adaptive Chroma Softness shuts off on its own in Tight and Luma modes since it runs counter to how those modes work.
- Chroma Tilt: Shifts your chosen color region around the color space, altering its chroma per its vertical placement.
- Chroma Shift: Shifts your chosen color region around the color space, altering its chroma per its horizontal placement.
- Chroma Rotate: Shifts your chosen color region around the color space, altering its tint and temperature per how it rotates about the central origin point.
- Luma Low: Widens or narrows the key’s dark regions across the brightness range.
- Luma High: Widens or narrows the key’s bright regions across the brightness range.
- Low Softness: Sets how sharply defined the brightness range’s low end is. This sets

whether the key acts as a hard cutoff or a soft pickup of like brightness levels.

- High Softness: Sets how sharply defined the brightness range’s high end is. This sets

whether the key acts as a hard cutoff or a soft pickup of like brightness levels. TIP: Each of the parameters above can be key-framed, letting you animate the key across time. As an instance, you might have qualified a shirt while the actor passes through differently colored light within a scene. By key framing those same parameters, you can keep the very same key on that shirt as its colors change over time.

### Matte Finesse

It may turn out that sampling the screen color alone won’t clear up certain problems. Trouble such as chattery edges, holes, or noise can at times be remedied through the Matte Finesse controls. These controls filter what the Keyer puts out and amount to adjustments made on the matte itself, reshaping the key by drawing on the frame’s content.

- Pre Filter: This slider gives the image a cleanup pass prior to any color sampling. The adjustment proves handy where your footage carries MPEG blocking artifacts.
- Clean Black: Clean Black names a focused operation that wipes out noise appearing as white speckling within a key’s black area. Pushing Clean Black up lets you “fill holes” throughout a key’s background portion and chew away translucent edges.
- Clean White: Clean White names yet another focused operation that wipes out noise (appearing as black speckling while you view a high-contrast highlight) within the white portion of a key that covers areas of the image you’re isolating, and it stretches the key by brightening a key’s light parts the further you push this parameter up, easing a key’s light gray areas toward white. The upshot is that pushing Clean White up lets you “fill holes” throughout a key’s foreground portion and stretch translucent edges.
- Black Clip: Pushing Black Clip up lays on a “lift” adjustment such that the matte’s translucent areas (its gray areas while viewing a high-contrast highlight) ease toward black. Values run 0 to 100, where 0 serves as the default setting.
- White Clip: Easing White Clip down lays on a “gain” adjustment such that the matte’s translucent areas (its gray areas while viewing a high-contrast highlight) ease toward white. Values run 0 to 100, where 100 serves as the default setting.
- Blur Radius: In modest doses, blurring a key does a good job of taking the bite off troublesome edges. That said, blurring a key may also feather a key’s edges out past the border of whatever subject you’re keying, the upshot being a visible “halo” ringing your subject, hinging on the adjustment you make. Values run 0 to 2000, where 0 serves as the default. With a maximum blur radius this generous, joined by what the In/Out Ratio brings for tailoring the direction of spread, you can convert some quite precarious mattes into surprisingly smooth, useful results.
- In/Out Ratio: Putting In/Out Ratio to work can help do away with fringing. Pushing In/Out Ratio up will pack small black holes within the matte, whereas easing In/Out Ratio under 0 will do away with speckling by easing small white bits of the matte toward black.
- Morph Operation: Settle on Shrink or Grow to dilate or erode the matte’s edges, or settle on Opening or Closing to plug or open up holes so a ragged matte gets cleaned up.
- Morph Radius: Sets how far to shrink, grow, open, or close the key.
- Denoise: Affords a separate means of post-processing pulled keys to selectively trim a key’s noise, doing away with stray patches of qualification and softly packing holes within a matte.
- Shadow: Tunes key strength off the darker portions of the original image.
- Midtone: Tunes key strength off the midtones of the original image.
- Highlight: Tunes key strength off the brighter portions of the original image.
- Post Filter: Carries out a closing cleanup on the key, putting the original image to use as reference; handy for coaxing back some fine detail across sharp edges or hair.

### Garbage Matte

Through these controls you can crop away other unwanted items present in the frame, such as lighting fixtures, boom microphones, tracking patches, and so forth.

- Matte Shape: Settle on either a Rectangle or Ellipse to crop around whatever subject you’re keying. Settling on None switches Garbage Matte off. With a garbage matte switched on, the Viewer’s Open FX Overlay mode surfaces an on-screen control for tuning the garbage matte’s shape and placement.
- Edge Softness: Lets you soften the edges. It defaults to 50; values run 0 (no softening) to 100 (maximum softening).
- Invert: Flips the garbage matte.
- Center X and Y: Lets you tune and keyframe where a garbage matte sits.
- Bounding Width and Height: Lets you tune the garbage matte’s width and height.
- Rotation: Lets you tune the garbage matte’s angle.

### Output

Through the Output controls you settle on how the image gets output, composited, and shown within the Viewer.

- Output: This menu lays out three options for which channels come out of the effect. Alpha Highlight: Renders an Alpha channel’s transparent part as gray with an alpha channel’s solid part in full color.

Alpha Highlight B/W: Renders the black and white Alpha channel, frequently of use while sampling further areas to key. Final Composite: The keyed image gets rendered composited over whatever video track lies below it.

- Use Alpha: A widespread control found in many Resolve FX and 3rd party Open FX plugins; this checkbox decides whether the Alpha channel applies while compositing over another video track. It can stand in for picking RGB Only (Blank Alpha) off the Output menu.

To put the 3D Keyer to work on the Edit page: 1. Lay the 3D Keyer onto a green screen or blue screen clip sitting on a track above the background. 2. Within the Inspector, tick the Show Paths checkbox so the sampled areas come into view once you begin. 3. Off the Viewer Overlay menu at the lower-left of the Timeline Viewer, pick Open FX Overlays. 4. Within the Viewer, click and drag to draw a sampling stroke over the screen color you wish to strip out. 5. Transparency kicks in right away, showing the keyed subject against whatever clip sits on the video track below it in the Timeline as a composite. To view the matte you built for further tuning, pick Alpha Highlight or Alpha Highlight B/W off the Output drop-down menu. 6. As needed, you can add areas to or trim areas from the screen color selection through the add/ subtract Color range controls. Alternatively, with the default Sample eyedropper active, you can hold Shift to add onto the screen color selection or hold the Option key to pull from the screen color selection.

### Alpha Matte Shrink and Grow (Studio Version Only)

This filter gives you assorted ways to refine the edges of alpha and key mattes, both shrinking and growing those edges and opening or closing holes that surface within a matte. On the Color page, you can apply this filter to Qualifier or Window keys that have been routed into the RGB input of a corrector node, for tuning and refinement, before the result gets wired into a downstream node’s key input to isolate an adjustment.

Putting the Alpha Matte Shrink and Grow filter onto a key matte fed into the RGB input of a separate node

- Morph Operation: Through a drop-down menu you settle on how to reshape the Alpha channel/key. Settle on Shrink or Grow to dilate or erode the matte’s edges with great precision. Or settle on Opening or Closing to plug or open up holes inside the key so a ragged matte gets cleaned up.
- Shape: Through a drop-down menu you settle on how corners and angles along the key’s edges get treated as you grow or shrink it. Circle stands as the default and yields even expansion about the key’s surface that, at extreme Radius settings, eventually averages every angle into a circular form. Square averages every angle into a more rectangular form at extreme Radius settings. Diamond averages every angle into a diamond form at extreme Radius settings.
- Radius: A slider sets how far to Shrink, Grow, Open, or Close the key.
- Process: Lets you pick particular channels for the Morph Operation to act on. The options are RGB

(Blank Alpha), Alpha (RGB Unaffected), and RGB + Alpha. Preview Alpha: Ticking this box lets you quickly preview the Alpha channel the node will put out.

- Manual Iteration Control: Ticking this box hands you direct say over how the operators get applied.

Operator Radius: A slider governing the operator’s size. Repeat Operation: A slider reshapes what the Operator Radius setting does so you can push more extreme adjustments.

### HSL Keyer

Built on the Color page’s HSL Qualifier, the HSL Keyer Resolve FX is an all-purpose keyer drawing on a trio of color components, hue, saturation, and luma, in order to set up a key. On top of that, the HSL Keyer lets you switch off whichever color components you’d sooner keep from feeding the resulting key. A saturation-only key, or a hue-only key, is within reach for cases where leaning on individual components alone yields a finer result. The simplest route to working any keyer is sampling the picture in the Viewer with the settings untouched. Once you sample one or more pixels, the hue, saturation, and luma values get analyzed and assigned differing ranges. A number of eyedropper controls are on hand to sample color and soften the selection.

### Selection Range Controls

The Inspector’s Selection Range buttons let you set up a key by sampling and softening Viewer pixels with the mouse pointer.

### HSL Keyer Color Range controls

- Sample Eyedropper: This tool picks the colors that serve as the qualification range by way of clicking and dragging over the Viewer image. Click it once more to wipe the prior selection. As a rule, long drags yield finer results than short ones.
- Add/Subtract Color Range: This pair of controls lets you fold image areas into, or pull them out of, the presently chosen inner band of values forming the key’s core. As with the other sampling controls, dragging over a band of color works.
- Add/Subtract Softness: This pair of controls lets you reshape the softness that eases out of the key’s inner band, tapering toward the key’s outer edge. As with the other sampling controls, dragging over a band of color works.
- Invert: Flips the sampled color so it turns opaque, while regions left unsampled turn transparent.
- Reset: Clears every sampled color yet holds onto the general control settings.

### Keyer Options

A notable strength of the HSL Keyer is that each of the three HSL components can be switched on or off through the Hue, Sat, and Lum checkboxes. That lets you skip particular color components while zeroing in on others that might matter more. As an example, when you’re after keying the saturated portions of a picture, no matter the hue or brightness, you can switch off Hue and Lum so only Sat drives the sampling.

### HSL Keyer options

### Matte Finesse

Sampling the screen color on its own may prove insufficient for clearing certain problems. Trouble like chattery edges, holes, or noise can occasionally be sorted out by way of the Matte Finesse controls. These controls filter the Keyer’s output and stand as adjustments laid on the matte itself, reworking the key through the frame’s content.

- Pre Filter: With this slider the image gets a cleanup pass before any colors are sampled. The adjustment can pay off where your footage carries MPEG blocking artifacts.
- Clean Black: Clean Black is a dedicated operation that strips noise showing as white speckling across the black region of a key. Lifting Clean Black lets you “fill holes” throughout the background portion of a key and wear down translucent edges.
- Clean White: Clean White is a further dedicated operation that strips noise (showing as black speckling when you view a high-contrast highlight) across the white portion of a key that takes in areas of the image you’re isolating, and it grows the key by making bright parts of a key brighter the more you lift this parameter, nudging light gray regions of the key toward white. In practice, lifting Clean White lets you “fill holes” throughout the foreground portion of a key and grow translucent edges.
- Black Clip: Lifting Black Clip lays on a “lift” adjustment so that translucent regions of the matte (the gray regions when you view a high-contrast highlight) get nudged toward black. Its range runs 0 to 100, with 0 as the default setting.
- White Clip: Dropping White Clip lays on a “gain” adjustment so that translucent regions of the matte (the gray regions when you view a high-contrast highlight) get nudged toward white. Its range runs 0 to 100, with 100 as the default setting.
- Blur Radius: At modest amounts, blurring a key does a fine job of softening troublesome edges. Yet blurring a key can equally feather a key’s edges out past the boundary of the subject you’re keying, leaving a visible “halo” around your subject, according to the adjustment you make. Its range runs 0 to 2000, with 0 as the default. Given so large a maximum blur radius, together with what the In/Out Ratio offers for shaping the direction of spread, you can convert some rather dicey mattes into surprisingly smooth, usable results.
- In/Out Ratio: Reaching for In/Out Ratio can help wipe out fringing. Lifting In/Out Ratio will pack small black holes in the matte, whereas dropping In/Out Ratio below 0 will clear speckling by nudging small white bits of the matte toward black.
- Morph Operation: Pick Shrink or Grow to dilate or erode the matte’s edges, or pick Opening or Closing to plug or open holes so a ragged matte gets cleaned up.
- Morph Radius: Sets the degree to which the key is shrunk, grown, opened, or closed.
- Denoise: Offers a separate route to post-process pulled keys so a key’s noise gets selectively cut, clearing stray patches of qualification and gently packing holes in a matte.
- Shadow: Tunes key strength off the darker portions of the original image.
- Midtone: Tunes key strength off the midtones of the original image.
- Highlight: Tunes key strength off the brighter portions of the original image.
- Post Filter: Runs a closing cleanup of the key, leaning on the original image as reference; handy for restoring some fine detail across sharp edges or hair.

### Garbage Matte

Through these controls you can crop away other stray things in the frame, such as lighting fixtures, boom microphones, tracking patches, and so on.

- Matte Shape: Pick either a Rectangle or Ellipse to crop around whatever subject you’re keying. Picking None switches Garbage Matte off. With a garbage matte switched on, the Viewer’s Open FX Overlay mode surfaces an on-screen control for tuning the garbage matte’s shape and position.
- Edge Softness: Lets you soften the edges. The default is 50; its range runs 0 (no softening) to 100 (maximum softening).
- Invert: Flips the garbage matte.
- Center X and Y: Lets you tune and keyframe a garbage matte’s position.
- Bounding Width and Height: Lets you tune the garbage matte’s width and height.
- Rotation: Lets you tune the garbage matte’s angle.

### Output

Through the Output controls you pick how the image gets output, composited, and shown in the Viewer.

- Output: This menu hands you three options for which channels come out of the effect. Alpha Highlight: Shows an Alpha channel’s transparent part as gray and an alpha channel’s solid part in full color. Alpha Highlight B/W: Shows the black and white Alpha channel, frequently of help while sampling further areas to key. Final Composite: The keyed image gets shown composited over whatever video track sits beneath it.
- Use Alpha: A widespread control across many Resolve FX and 3rd party Open FX plugins; this checkbox sets whether the Alpha channel comes into play while compositing over another video track. It serves in place of picking RGB Only (Blank Alpha) off the Output menu.
