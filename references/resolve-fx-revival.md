# Resolve Fx Revival (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Resolve FX Revival

Gathered in this category are plugins for sorting out the everyday technical, damage, and quality troubles that plague programs in the midst of finishing, remastering, or restoration.

### Automatic Dirt Removal (Studio Version Only)

Optical flow technology drives the Automatic Dirt Removal plugin, which pinpoints and mends temporally unstable specks of dust, dirt, hair, tape hits, and similar unwanted artifacts that flash by for a frame or two before vanishing. Every repair preserves structurally consistent detail in the frame underneath, so the image comes out restored at high quality. Happily, for all its sophistication the plugin is fairly easy to operate; you simply drop it onto a shot, tune the parameters for the best outcome, and let it run.

(Left) Original image, (Right) Using Automatic Dirt Removal. NOTE: The plugin fares worse against vertical scratches that stay fixed in one position across multiple frames, and it does nothing at all for lens dirt that lingers for the whole shot.

### Main Controls

The main controls govern how much dirt the filter strips from the image.

- Motion Estimation Type: Offers a pick among None, Faster, Normal, and Better. This sets where you land on the performance-versus-quality tradeoff.
- Neighbor Frames: Sets how many frames get compared while dirt is being detected. Comparing more frames lengthens processing, yet generally turns up more dirt and artifacts.
- Repair Strength: A slider that sets how aggressively found dirt and artifacts get repaired. Lower settings can let small specks slip by that may or may not really be dirt, whereas higher settings wipe out everything turned up.
- Dirt Size Threshold: A slider that sets how big a detected speck of dirt has to be before it’s removed. Pushing this parameter up keeps things like film grain out of the operation, though it may let smaller specks of dirt through.
- Show Repair Mask: A checkbox that displays the detected dirt and artifacts on their own, letting you judge how effective the results are while you fine tune this filter.

### Fine Controls

These controls let you fine tune the effect as you chase the ideal balance between clearing dirt successfully and holding onto genuine image detail.

- Motion Threshold: A slider that sets the point above which moving pixels get treated as dirt and artifacts. Lower values let more dirt escape correction but leave you with fewer motion artifacts. Higher values clear more dirt, though footage with camera or subject motion may show more motion artifacts as a result.
- Edge Ignore: A slider for shielding the picture’s hard edges from being touched by the dirt or artifacts being removed. The higher the value, the more edges get left untouched.

### Chromatic Aberration Removal (Studio Version Only)

A Revival category plugin for correcting by hand the faint color fringing that a lens’s chromatic aberration leaves behind. The Show Estimated Fringes checkboxes for the RGB channels bring up an “alignment guide” that sets each fringing type apart visually against gray. (Left) The original image in close up, with chromatic aberration on show; (Right) the same image once Estimated Red Fringes is on, which surfaces the precise problems as differences between red and cyan stripes.

### Advanced Options

Advanced Options supply extra parameters for troublesome shots.

- Lens Center: The Center X and Y parameters shift the lens center when you’re working on a reframed and re-rendered shot. You can also reposition by dragging the lens center on-screen control inside the Viewer.
- Stronger Correction: Points out where image features that look like fringing sit.

### Estimation Options

The Estimation options exist only to highlight and pinpoint regions of fringing. They leave the image’s final output untouched. They turn available solely once one of the Show Estimated Fringes boxes is ticked in the Aberration Correction section.

- R/C, G/P, B/Y Balance: These tools shift the incoming balance between their respective colors to make hard-to-spot fringing easier to identify.
- Brightness: Amplifies the fringe indicators shown whenever you switch on either of the Estimated Fringes checkboxes.

### Aberration Correction

These tools let you correct aberration troubles by hand.

- R/C, G/P, B/Y Scale: Work these sliders to clear the fringing out of their respective colors.
- R/C, G/P, B/Y Edge: Work these to offset the fringing difference brought on by the curvature of the

lens’ edges.

- Show Estimated Fringes: Tick this box to display nothing but the estimated fringes over a gray

background. Ticking it also switches on the Estimation Options sliders, which help you highlight and pin down fringing regions further. From there it’s simple to correct the problem by hand, leaning on the Scale and Edge controls to treat Red/Cyan, Green/Purple, and Blue/Yellow fringing one at a time.

(Left) The original image in close up, with chromatic aberration appearing as a cyan fringe down the right of the smokestack and a red fringe along the building’s nearest corner; (Right) the corrected image in close up, the fringe now gone.

### Dead Pixel Fixer (Studio Version Only)

When you have clips shot on a camera whose sensor carries one or more “dead” or “stuck” pixels, the image may show black or white spots locked in one place. This filter is built to let you lay patches over each dead or stuck pixel, marking them out so you can apply various fix methods. The Dead Pixel Fixer resembles the Dust Buster in many ways, but the Dust Buster effect targets fleeting bits of dust and dirt that survive only a frame or two, while the Dead Pixel Fixer is meant for blemishes pinned in place across a clip’s whole length. To mend dead or stuck pixels, apply the Dead Pixel Fixer filter, confirm the OFX onscreen controls are switched on in the viewer, then click each pixel you need fixed with the mouse to drop a patch on it. Click anywhere on the image to lay down as many patches as you want — there’s no cap. An Option-click removes patches you no longer need. To relocate a patch, just drag it elsewhere.

### Multiple dead pixel removal patches

Once several patches are down, a click selects whichever patches you’d like to set the controls for. The control settings can differ from one patch to the next.

### General

These top-level controls govern how you draw the patches used to mend frame blemishes, along with whether their on-screen controls appear and in what manner.

- Draw Rect: Click and drag to lay a rectangular patch of any size from one corner across to the opposite corner. After it’s drawn, click any edge of the overlay and drag to reposition it.
- Draw Ellipse: Click and drag to lay an elliptical patch of any size from one corner across to the opposite corner. After it’s drawn, click any edge of the overlay and drag to reposition it.
- Place Patch: For laying small patches aimed at tiny details such as dead pixels. Picking this option brings up a New Patch Size slider that sets the size of the patches you’re about to place before you place them. After one’s drawn, click the edge of any patch and drag to reposition it.
- New Patch Size: (active only while Place Patch is selected) Sets how big a patch the Place Patch tool lays down.
- Show Patches: A checkbox that reveals or conceals every patch’s onscreen outline in the Viewer.
- Hide During Interaction : Conceals every patch’s onscreen outline in the Viewer as you move a patch; this makes it easier to gauge the effect of moving the patch on the image, without the outline in the way.

### Patch Type

Three methods stand ready for fixing the contents of a selected patch. As you draw new patches, whichever Patch Type is selected at the time dictates what the next patch becomes. Once you’ve selected a patch that already exists, switching the Patch Type alters how that patch operates.

- Spatial: Fills the inside of the selected patch automatically with pixels pulled from around the patch, by way of the Fill Method. It serves small blemishes well, but on large blemishes a pattern may become noticeable, which betrays the effect.
- Clone: Clone mode copies a portion of the image to fill a shape or patch laid over whatever you want gone. Here, once you click and drag a Rect or Ellipse across an imperfection, a second click then sets the sample region you mean to clone. A single click to lay a Patch is followed by a second click that sets the sample region. Selecting an existing shape or patch and picking Clone lets you click on the shape to position the clone region. A dotted shape tied to the original shape marks where the sample region is.
- Blend Clone: Works much like Clone mode, except that the copied portion of the image filling the Rect, Ellipse, or Patch is blended into the image so it merges more softly.
- Fill Method: With the Spatial Patch Type in use, the fill method decides how the image blemish gets mended.

Grid: Reads the pixels ringing the Rect, Ellipse, or Patch, blurring them inward along both axes at once. Hugely effective on tiny blemishes. On larger ones, a grid-like pattern can surface. Horizontal: Reads the pixels flanking either side of the Rect, Ellipse, or Patch, then blurs them inward.

Vertical: Reads the pixels above and beneath the Rect, Ellipse, or Patch, then blurs them inward. Patchy: Gathers pixels from every direction around the Rect, Ellipse, or Patch, then spreads and blurs them together into a soft, non-uniform region for mending the blemish. It sidesteps the patterning of the grid fill methods while delivering an exceptionally smooth result. Smooth: Just applies a gaussian blur to mend the blemish.

### Patch Options

These options let you tailor how a patch fills over a blemish.

- Variability: (Spatial patches only) Pushing this parameter up makes the Fill Method less uniform.
- Soft Edges: Softens the patch’s edges.
- Size Adjust: Resizes a patch after you’ve made it.
- Mute: Switches a given patch on or off through keyframing. Handy for blemishes that crop

up across only a few pixels of a shot.

- Delete Patch: Removes the currently selected patch; an Option-Click on any

patch deletes it as well.

### Advanced Controls

These controls let you tailor this effect’s UI.

- Clone Sticks to Mouse: With this on, the moment you draw or place a Rect, Ellipse, or Patch while in Clone or Blend Clone mode, the tool jumps straight to positioning the sample region, which speeds things up.
- New Patches Stay Selected: With this on, patches remain selected after you draw them, ready for more customization.
- UI Line Thickness: Sets how thick the on-screen outlines come out.
- Patches Stick to: This parameter handles fixing dead pixels or blemishes on clips that

have undergone stabilization. Source: The patches you lay stay put, unless you apply motion stabilization to the shot, at which point they’re transformed along with the image so they stay “stuck” to the feature in the source clip they’re mending. Scene: When clearing a blemish off a moving subject, the FX Tracker can track whatever you’re fixing, so the patch travels along with it.

- Output Mode: This shows you various representations of the patched effect you’re building. Four options are on offer. Patched Result: The finished result, every patch mending the blemish beneath it. Patch Locations: Presents a key with each placed patch in white against black. Differences: Presents each patch’s difference against the original image. Difference Magnitude: Presents a more pronounced version of the Differences view.

### Deband (Studio Version Only)

Low bit-depth media carrying regions of shallow color gradient, such as a sky or a wall, often display color banding — visible stripes — since there simply aren’t enough color values to render the gradation from light blue to darker blue in the sky smoothly.

An example of banding in the sky of an image

### Minimizing banding using the Deband filter

This filter is built to single out the edges of color banding and tamp them down by dithering pixels on either side to ease the transition. It performs best on image regions you’ve isolated with a secondary qualifier or window; otherwise you run the risk of every edge in your image getting dithered and softened (though that can make for an interesting stylistic effect).

### Deband Parameters

Deband’s controls are these:

- Edge Threshold: Governs how sharply defined an edge must be before the filter acts on it; lowering it leaves out fainter edges, while raising it takes them in.
- Radius: Dials the strength of dithering up or down within the affected regions.
- Post Refine: Tightens (when lowered) or broadens (when raised) the regions touched by dithering.
- Display Edge: A checkbox that gives you a black-and-white high-contrast preview of which edges

are being picked up for dithering, which can help you fine-tune your results.

### Deflicker (Studio Version Only)

The Deflicker plugin copes with problems as varied as flickering exposure in timelapse clips, flickering fluorescent lighting, flicker in archival film sources, and in some subtle cases even the “rolling bars” seen on video screens shot with cameras whose shutter speeds don’t match. Two things stand out about this filter: it goes after only rapid, temporally unstable swings in lightness, and it can confine its attention to just the image areas where flickering shows up, leaving the rest of the image alone. Thanks to that, the plugin can frequently mend problems once written off as “unfixable.”

The unprocessed image, its blue screen marred by flicker bars The outcome once Deflicker is set to Fluoro Light, (clip courtesy Redline Films)

### Main Parameters

By default the plugin’s top section surfaces just one control, which in plenty of cases is all you’ll require.

- Deflicker Settings pop-up menu: The first two options, Timelapse and Fluoro Light, are presets that do a solid job of clearing two distinct categories of flickering artifact. Should neither preset perform quite as well as you’d hoped, a third option, Advanced Controls, unlocks the Isolate Flicker controls sitting at this plugin’s core so you can tailor it further to your needs.

### Temporal NR

Concealed by default, these controls surface only once you set Deflicker Setting to Advanced Controls; they govern how motion in the scene gets detected, so that flickering is handled correctly in relation to the movement of subjects and objects in the frame where it shows up.

- Frames Either Side: Sets the count of frames analyzed to work out what’s moving. More isn’t always better; the optimal setting, once again, depends on the scene. The default is 3.
- Mo.Est. Type: Picks the technique DaVinci Resolve applies to analyze the image and detect motion. The option names notwithstanding, which one performs best leans heavily on the scene. The default, Faster, demands less of the processor and gives up some accuracy; that can actually be a plus, doing a better job on high-detail images that would trip up the Better option. Picking Better buys more accuracy at a higher processor cost, and Better strains harder to match fine details, which can occasionally cause trouble. None switches off motion analysis entirely, which can serve well (and runs far faster) where the scene holds no motion whatsoever. The default is Better.
- Motion Range: Three settings — Small, Medium, and Large — let you set the speed of frame motion that ought to be detected.
- Luma Threshold: Sets the threshold past which luma changes won’t count as flicker. The range is 0–100; at 0 nothing is deflickered, at 100 everything is. The default is 100.
- Chroma Threshold: Sets the threshold past which chroma changes won’t count as flicker. The range is 0–100; at 0 nothing is deflickered, at 100 everything is. The default is 100.
- Luma Chroma Same Threshold: Lets you decide whether or not to gang the Luma and Chroma Threshold sliders.
- Motion Threshold: Sets the threshold past which motion won’t count as flicker.

### Speed Optimization Options

Collapsed by default, expanding this control group brings up two controls:

- Reduced-Detail Motion checkbox: On by default, it trims how much detail gets analyzed during flicker detection. Often it makes no visible difference yet speeds processing up. Switch it off if your clip carries fine detail that’s being smoothed too aggressively.
- Limit Analysis Area checkbox: Switching this on brings up controls for a sample box that you can use to pen deflickering into a particular region of the image. The option earns its keep when: a) only one part of the image flickers, so concentrating on that area alone speeds the operation up considerably, or b) deflickering that’s handling one part of the image beautifully is smoothing another part too much.

### Restore Original Detail After Deflicker

Collapsed by default, expanding this control group brings up two controls:

- Detail to Restore slider: Quickly singles out grain, fine detail, and sharp edges that the deflicker operation should leave alone, holding those fine details exactly as they were.
- Show Detail Restored checkbox: Switching this checkbox on reveals the edges that the Detail to Restore slider detects and uses, which helps you tune the operation.

### Output

The Output pop-up menu lets you set what Deflicker sends out, with options geared toward troubleshooting problem clips. The available options are:

- Deflickered Result: The finished, repaired result. This is the default setting.
- Detected Flicker: This option presents a mask that highlights the image parts being

flagged as flickering, helping you judge whether the right parts of the image are getting targeted. That mask can be quite subtle, though.

- Magnified Flicker: This option presents an exaggerated take on the Detected Flicker mask, making it easier to see what the Deflicker plugin is up to.

### Dust Buster (Studio Version Only)

This plugin, too, sets out to clear away dust and dirt, plus other imperfections and artifacts, from clips — but it works only under your guidance, on clips where the Automatic Dirt Removal plugin comes up short. That guidance amounts to stepping through the clip frame-by-frame and drawing boxes around the imperfections you want gone. The moment you’ve drawn a box, the offending imperfection vanishes auto-magically, as seamlessly as can be. It handles dirt and dust well, and it copes with really large stains and blotches too, as shown below.

The Dust Buster shares a lot with the Dead Pixel Fixer, yet the Dust Buster effect is meant to mend fleeting bits of dust and dirt that survive only a frame or two, whereas the Dead Pixel Fixer is meant for blemishes locked in place across a clip’s whole length.

### General

These top-level controls govern how you draw the patches used to mend temporally unstable dust and dirt in the frame, along with whether their on-screen controls appear and in what manner.

- Navigation Controls: Four buttons let you leap to frames where you’ve drawn patches. The four buttons are:

First Modified Frame: Sends the playhead to that clip’s first frame holding a patch. Previous Modified Frame: Sends the playhead back to the nearest earlier frame holding a patch. Next Modified Frame: Sends the playhead ahead to the nearest later frame holding a patch. Last Modified Frame: Sends the playhead to that clip’s last frame holding a patch.

- Draw Rect: Click and drag to lay a rectangular patch of any size from one corner across to the opposite corner. After it’s drawn, click any edge of the overlay and drag to reposition it.
- Draw Ellipse: Click and drag to lay an elliptical patch of any size from one corner across to the opposite corner. After it’s drawn, click any edge of the overlay and drag to reposition it.
- Place Patch: For laying small patches aimed at tiny details such as dead pixels. Picking this option brings up a New Patch Size slider that sets the size of the patches you’re about to place before you place them. After one’s drawn, click the edge of any patch and drag to reposition it.
- New Patch Size: (active only while Place Patch is selected) Sets how big a patch the Place Patch tool lays down.
- Show Patches: A checkbox that reveals or conceals every patch’s onscreen outline in the Viewer.
- Reset Frame: Wipes all patches off the current frame.

### Patch Type

Six methods stand ready for fixing the contents of a selected patch. As you draw new patches, whichever Patch Type is selected at the time dictates what the next patch becomes. Once you’ve selected a patch that already exists, switching the Patch Type alters how that patch operates.

- Auto: The default method. After you draw a bounding box, the two frames ahead of and the two frames behind the current clip get analyzed and weighed against the current image. Whichever of these 5 frames fits best is sampled to lift the imperfection out of the current frame. Frames two away get priority because that staves off frozen grain, but only when they suitably match the current frame’s content.
- +/- 1 Frame: Under this mode, drawing a bounding box left to right pulls from the next frame to lift the imperfection. Drawing one right to left pulls from the previous frame instead.
- +/- 2 Frames: Drawing a bounding box left to right pulls from the image two frames ahead to lift the imperfection. Drawing one right to left pulls from the image two frames back instead.
- Spatial: Fills the inside of the selected patch automatically with pixels pulled from around the patch, by way of the Fill Method. It serves small blemishes well, but on large blemishes a pattern may become noticeable, which betrays the effect.
- Clone: Clone mode copies a portion of the image to fill a shape or patch laid over whatever you want gone. Here, clicking and dragging to lay a Rect or Ellipse over an imperfection

is followed by a second click that sets the sample region you mean to clone. A single click to lay a Patch is followed by a second click that sets the sample region. Selecting an existing shape or patch and picking Clone lets you click on the shape to position the clone region. A dotted shape tied to the original shape marks where the sample region is.

- Blend Clone: Works much like Clone mode, except that the copied portion of the image filling the Rect, Ellipse, or Patch is blended into the image so it merges more softly.
- Fill Method: With the Spatial Patch Type in use, the fill method decides how the image blemish gets mended. Grid: Reads the pixels ringing the Rect, Ellipse, or Patch, blurring them inward along both axes at once. Hugely effective on tiny blemishes. On larger ones, a grid-like pattern can surface. Horizontal: Reads the pixels flanking either side of the Rect, Ellipse, or Patch, then blurs them inward. Vertical: Reads the pixels above and beneath the Rect, Ellipse, or Patch, then blurs them inward. Patchy: Gathers pixels from every direction around the Rect, Ellipse, or Patch, then spreads and blurs them together into a soft, non-uniform region for mending the blemish. It sidesteps the patterning of the grid fill methods while delivering an exceptionally smooth result. Smooth: Just applies a gaussian blur to mend the blemish.

### Patch Options

Through these options you shape how a patch fills in over a blemish.
