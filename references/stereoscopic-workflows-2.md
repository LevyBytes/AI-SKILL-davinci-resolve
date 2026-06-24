# Stereoscopic Workflows (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Suppose someone gives you a stereo 3D muxed tape carrying a finished, mastered program that still needs grading, yet no project file or EDL accompanies it. In that case you can bring it in as separate left- and righteye media files using a supported VTR — for example HDCAM SR running in 4:2:2 x 2 mode — by enabling the “Use left and right eye SDI” checkbox located in the Capture and Playback panel of the Project Settings. As muxed stereoscopic signals come in, the software splits each eye out into its own left-eye and right-eye image files. After ingest, Scene Detection can carve the left-eye media into one bin and, to build an EDL, you can likewise carve the right-eye media into a second bin, giving you an ordered run of stereo clips ready to grade.

### Adjusting Clips Using the Stereo 3D Palette

After you have built or imported a timeline flagged as stereoscopic 3D, grading can begin. By default the Edit and Color pages show the left eye, but a right-click on the Timeline followed by Stereo 3D Mode lets you switch to the opposite eye. The usual approach for colorists is to grade a single eye first — generally the left — and then ripple those grades across to the second eye, making distinct tweaks per eye whenever camera mismatches need correcting. DaVinci Resolve can handle that rippling for you automatically. Once stereo 3D media is configured, the Stereo 3D palette becomes available on the Color page. Every control you need for stereoscopic work lives in this palette. Among its functions: picking which eye to grade, dialing in convergence, swapping and copying both grades and media across paired left- and right-eye clips, automatically matching the color and geometry of those paired clips, configuring stereo 3D monitoring, and managing floating windows.

### Stereoscopic 3D palette

This palette will only open if your project already holds stereo 3D clips. To learn how to configure a stereo 3D project, consult the “Creating Stereo 3D Clips From Separate Files” section of this chapter.

### Stereo Eye Selection

The usual approach for colorists is to grade a single eye first — generally the left — and then ripple those grades across to the second eye, making distinct tweaks per eye whenever camera mismatches need correcting. Within the Stereo 3D palette, the first three buttons govern which eye you grade as you work and whether each clip’s grade ripples through to its opposite-eye counterpart. Each time you flip eyes, the 3D badge sitting above a clip’s thumbnail shifts color (blue meaning right, red meaning left) and the thumbnails redraw to reflect that eye’s media.

The Left eye is master and ganged with the Right Left button: Shows the left-eye image along with its grade. Ripple Link button: While active (orange), every grade change you apply to the eye that’s currently selected is mirrored automatically onto its opposite eye. While inactive (gray), any grade applied to the selected eye stays independent. Right button: Shows the right-eye image along with its grade. Another way to set which eye you view and grade is to right-click a clip’s thumbnail and pick Stereo 3D > Switch Eye, or to use View > Switch Eye To > Left Eye or Right Eye.

### Using Ripple Link When Grading Stereo 3D Clips

Switching Ripple Link off pauses the rippling, which is handy when you need to tweak a single eye’s grade on its own to bring the two into closer agreement. After the two clips line up, flip it back on and automatic grade rippling resumes. Because stereo 3D grade rippling always works relatively, any differences already present between the left- and right-eye grades stay intact. Indeed, adding or deleting nodes on one eye automatically mirrors that same node addition or deletion on its paired clip, no matter whether Ripple Linked is on or off. IMPORTANT: No matter the state of Ripple Link, any local versions you create for one stereo 3D-identified clip are automatically made available to the paired timeline.

### Stereo 3D Geometry Controls

The following set of parameters governs the geometry of stereo 3D clips. The Pan, Tilt, and Zoom controls exist here for convenience and just echo the identical parameters in the Transform palette’s Input mode, only tailored to the geometry of the left- and right-eye media. The three parameters found nowhere but the Stereo 3D palette are Convergence, Pitch, and Yaw.

### Stereoscopic 3D Geometry controls

Convergence: Tunes the disparity between left and right eyes so as to set the point of convergence (POC) — the area of the picture where left- and right-eye features line up exactly. Where required, you can animate Convergence by way of the Stereo Format parameter group located within the Sizing track of the Keyframe Editor. To work with convergence in pixel units, open the Stereo 3D palette option menu and switch on “Show convergence in pixels.” Where features sit exactly atop one another in both the right- and left-eye clips, parallax is zero, placing that feature’s depth right at the screen plane. Where matching features diverge across the left- and righteye clips, parallax grows increasingly positive and the features read as receding from the audience. Where matching features are both divergent and reversed across the left- and right-eye clips, parallax grows increasingly negative and the features read as advancing toward the audience past the screen plane. Linked Zoom button: While active (white), both left- and right-eye clips zoom together each time Convergence changes, so neither eye ever stops filling the screen. While inactive (gray), Convergence changes let blanking creep in along the opposing left and right edges of each eye’s clip. Pitch: Tips the image about the frame’s horizontal center plane. Yaw: Tips the image about the frame’s vertical center plane.

### Sizing Repositioning in Stereo 3D

Most of the time you’ll reposition stereo 3D clips while Ripple Link is on, though now and then you may need to hand-adjust one specific eye with Ripple Link off. Just like color work, Sizing changes performed with Ripple Link off apply only to the clip in the current Timeline. With Ripple Link on, every Sizing change copies automatically to the equivalently numbered shot in the partner stereo 3D timeline. WARNING: Avoid the Rotate parameter when transforming stereo 3D clips. From a geometric standpoint, rotation skews a stereo clip pair the wrong way and destroys the “side by side” convergence required for the stereoscopic illusion to hold.

### Protecting Stereo Adjustments When Copying Grades

Every grade version keeps its own stereo adjustments saved alongside the Sizing settings. So that convergence and alignment data isn’t accidentally clobbered while copying grades between clips, you can right-click inside the Gallery and enable any of these options:

- Copy Grade: Preserve Convergence
- Copy Grade: Preserve Floating Windows
- Copy Grade: Preserve Auto Align

With these on, you can replace a clip’s grade while leaving particular Stereo 3D parameters untouched. TIP: In the DaVinci Resolve image processing pipeline, Stereo 3D and Sizing settings get applied ahead of any node-based corrections.

### Swap and Copy Controls

A further group of controls along the right edge of the Stereo 3D palette handles swapping and copying grades plus swapping clips, for cases where you must reverse whatever has been applied across a left- and right-eye clip pair.

### Swap and Copy grades between eyes

- Swap Grade: Trades the grades sitting on the left- and right-eye clips.
- Swap Shot: A checkbox that, once enabled, switches the actual media used by two

corresponding left- and right-eye clips. Handy when a stereo 3D clip’s eyes got labeled incorrectly and you’d like to swap the clips without having to rebuild both EDLs.

- Copy Right to Left: Applies the right-clip grade onto its matching left-eye clip.
- Copy Left to Right: Applies the left-clip grade onto its matching right-eye clip.

### Batch Grade Management for Stereo 3D Projects

A further group of batch-processing commands handy for stereoscopic grading shows up when you right-click one or more chosen clips in the Thumbnail timeline:

- Stereo 3D Batch Copy: Duplicates every grade from the left-eye clips onto the right-eye clips.
- Stereo 3D Batch Sync: Carries grades from one eye to the other strictly when the two node graphs

share an identical node count. That safeguard stops you from inadvertently clobbering a bespoke grade whose node layout was built specifically to reconcile two eyes on a troublesome shot. Within the Stereo submenu of the Timeline contextual menu you’ll also find these commands: Copy Grade, Swap Grade, Swap Shots, Ripple Link, plus Switch Eye.

### Automatic Image Processing for Stereo 3D

On stereoscopic shoots it’s typical for small geometry and color divergences to creep into the captured footage. To ease the burden of grading stereo 3D media, DaVinci Resolve supplies a group of auto-adjustment controls along the right side of the Stereo 3D palette that hands you a starting point for matching left- and right-eye clips.

### Auto align and color match buttons

### Options for Auto Processing

The frame used to automatically analyze and process stereo clips is selectable through the Alignment and Matching controls in the Stereo 3D palette option menu. Pick Auto Process > First or Middle, whichever suits your media best.

### Auto Process—Stereo Alignment

If the stereoscopic effect is to read without giving viewers headaches, both eyes absolutely must be aligned. Adjusting this by hand is fiddly, but the software can analyze it for you automatically. You can run stereo 3D alignment on a single clip, or pick a range of clips to align them all at once. Two choices exist, and the right one depends on the kind of geometry problem you’re trying to fix.

- Transform Alignment: Examines the image and applies vertical and rotational tweaks to register the left- and right-eye images as tightly as it can.
- Vertical Skew: Examines the images and applies a vertical-only tweak to register the left- and right-eye images.

To align one or more clips automatically: 1 In the Thumbnail timeline of the Color page, highlight one or several stereo clips. 2 Decide which frame of each clip drives the analysis: open the Stereo 3D palette, click the Option menu, and pick Auto Process > First or Auto Process > Middle. 3 Click whichever of the Stereo Alignment buttons you want. The left button handles Automatic Transform; the right button handles Automatic Vertical Skew. Should you have picked several clips, the Stereo Alignment window opens and a progress bar reports how much time is left for the job.

### Auto Process—Color Matching

Owing to differences among stereo 3D rig designs, the color and contrast of one eye’s media sometimes fails to line up precisely with the other eye. DaVinci Resolve offers two commands that match two eyes together fast and automatically.

- Stereo Color Match (Primary Controls): Leans on the Lift/Gamma/Gain controls to bring one eye into line with the other. The outcome is an easily tweaked, simple adjustment that occasionally falls short of what Custom Curves can do.
- Stereo Color Match (Custom Curves): Leans on the Custom Curves to build a multipoint adjustment matching one eye to the other. The outcome tends to be more capable on difficult shots.
- Stereo Color Match (Dense Color Match): Runs a pixel-by-pixel, frame-by-frame color match of remarkable accuracy. The operation is heavy on the processor, so when batch processing lots of clips or matching lengthy clips, budget enough time. Since this match is so exact, it’s advisable to apply Dense Color Match only after running one of the stereo alignment commands.

TIP: For optimal output, run automatic color matching inside its own dedicated node, kept apart from your other corrections. The behavior of stereo 3D color match shifts depending on whether one half of the stereo 3D pair already carries a grade. The walkthrough below shows how to match a left- and right-eye pair before applying any hand adjustments at all. To match a pair of left- and right-eye clips automatically: 1 In the Thumbnail timeline of the Color page, highlight one or several clips. 2 Open the Stereo 3D palette and click any of the three Color Match controls. The Color Matching window opens, and a progress bar reports how much time remains for the job. You can likewise use automatic color matching to align an ungraded clip with a paired clip that’s already graded. That works solely for grades made up of one or more primary corrections; secondary corrections won’t auto-match. To auto-match an ungraded clip against an already-graded paired stereo clip: 1 To suspend stereo grade linking temporarily:

- Open the Stereo 3D palette, and turn off the Ripple Link button.
- Right-click the Thumbnail timeline, and choose Stereo 3D > Ripple Link > Solo.

2 Apply a primary adjustment to some clip in the left-eye timeline so as to build a basic base grade. At this point the left-eye clip carries a grade while the right-eye clip carries none. 3 Do one of the following to switch eyes:

- In the Stereo 3D palette, click Right.
- Right-click the Thumbnail timeline again, and choose Stereo 3D > Switch Eye.

This routine succeeds only if you run the Stereo Color Match commands on the ungraded half of a left- and right-eye stereo pair so as to align it with the graded half. 4 To make the match, do this: in the Stereo 3D palette, click any of the three color match controls. The two clips ought to line up with each other very closely.

### Stereo 3D Monitoring Controls

Sending both eyes to a stereo 3D display requires clicking the Vision: Mono or Stereo button and then picking a display mode from the Out pop-up menu.

### Monitoring controls for Stereo 3D

- Vision: A button toggles between Stereo — where both eyes can appear in the Viewer and feed video output across many formats — and Mono, where just one eye reaches the Viewer and your video output interface.
- Out: A pop-up menu offering various stereo viewing methods for previewing stereo 3D signals different ways. By default it also links to the Internal Video Scope options of the Viewer display. Each stereo 3D viewing mode is described thoroughly in the upcoming “Stereo 3D Output Options” section.
- Link button: While active, the Viewer and internal video scopes share the Out pop-up menu’s stereo 3D viewing choice. While inactive, you can set different stereo 3D viewing options for the Viewer and for the internal video scopes.
- Viewer: Lets you pick a stereo 3D viewing method for the Viewer.
- WFM: Lets you pick a stereo 3D viewing method for the internal video scopes.
- Cbd Size: Should any stereo 3D viewing option be set to Checkerboard, this parameter turns

active, allowing you to specify, in pixels, how big the checkerboard boxes are. On certain Blackmagic I/O devices, dual 4:2:2 Y’CbCr stereoscopic video streams are sent across HD-SDI once you switch on the ”Use left and right eye SDI output” checkbox within the Master Settings panel of the Project Settings. Depending on what your stereo-capable display supports, you can pick either Side-by-Side or Line-by-Line output to feed it.

### Stereo 3D Output Options

On top of that, the Viewer and video scopes can be configured to present both “eyes” in any of several modes.

- Side by Side: Places both images alongside each other. Each eye gets anamorphically squeezed so the pair fits the same resolution as the GUI viewer.
- Top and Bottom: Stacks both images one above the other. Each eye gets vertically squeezed so the pair fits the same resolution as the GUI viewer.
- Line by Line (Even/Odd): An interlaced mode in which the eyes alternate line by line. How thick those lines look in the Viewer scales with your zoom level.
- Checkerboard: Shows both eyes through an alternating checkerboard pattern. It’s a great mode for spotting picture regions where color or geometry differs between the two eyes.
- Anaglyph (B/W): Both eyes are desaturated and overlaid via Red/Cyan anaglyph to expose the disparity between them across different parts of the picture. Divergence in the left eye reads red, divergence in the right eye reads cyan. Areas where the eyes align show up grayscale. Anaglyph modes help judge geometric differences between the eyes and pinpoint the point of convergence (where the eyes register most precisely) that sets a picture region at the screen plane. The red/cyan coding also reveals which way the parallax runs. For any one feature, a disparity in which red sits to the right while cyan sits to the left marks positive parallax (projecting backward, away from the audience). The reverse — red on the left, cyan on the right — marks negative parallax (projecting forward, toward the audience).
- Anaglyph (Color): Like Anaglyph (B/W), except areas that align closely keep full color. As it happens, both anaglyph modes can be viewed on regular displays through old-school red/cyan anaglyph glasses, which permits stereo 3D monitoring even on displays that aren’t stereo 3D-capable.
- Difference: Overlays grayscale renditions of both eyes through the difference composite mode. Corresponding left/right-eye pixels in perfect register render black, while pixels that disagree render white. This mode is exceptionally handy for judging geometric differences between the eyes and locating the point of convergence, free of the color distraction the anaglyph modes carry.

NOTE: In the Viewer, only the eye belonging to the timeline you currently have selected is shown. That said, it works together with one checkbox — “Use Dual Outputs on SDI” — found under Master Settings within Project Settings; turning that on routes each eye to its own HD-SDI output on your Blackmagic I/O card.

The Viewer set to display an anaglyph stereo image in color

### Floating Windows

Floating Windows exist to fix “Window violations,” cases where picture elements carrying negative parallax — the ones projecting forward off the screen plane toward the audience — get clipped by the frame edge. When that happens, the mismatch between what the left and right eyes are shown produces a visual paradox viewers find hard to resolve. To be precise: once a forward-projecting element gets clipped by the frame’s left or right edge, one eye perceives something its partner never does. A fast-moving subject may make this a non-issue, but if the clipped (or occluded) element hangs around onscreen, it troubles viewers and collapses the stereo 3D illusion. Here stereopsis (the viewer’s binocular vision) supplies one depth cue at the same time that occlusion supplies an entirely contradictory one.

The remedy is to apply Floating Windows that crop the clipped object out of the eye on the side where it’s cut off, removing the slice of the stereo image hidden from the other eye that’s causing the trouble.

### Floating Window controls

The point of Floating Windows is to shape the illusion of the viewer’s “window into the scene.” Beyond repairing Window violations, some have suggested that Floating Windows can serve as a creative device, the geometry of this Window being reshaped to subtly shift how the viewer reads the screen’s orientation.

- Trimming the right-eye frame along its right-hand side produces the illusion that the

“window into the image” has its right edge leaning farther forward toward the viewer.

- Trimming the left-eye frame along its left-hand side produces the illusion that the Window’s

left edge is leaning toward the viewer.

- Crop the left-eye frame on its left edge while also cropping the right-eye frame on its

right edge, and the whole plane of the “virtual screen” seems to advance toward you.

- Apply oppositely angled Windows across the left- and right-eye clips at either edge of the frame (or both), and the screen seems to “tilt” toward or away from the viewer.

### Animating Floating Windows

You can animate Floating Windows via the Float Window keyframing track, located inside the Sizing track of the Keyframe Editor, pushing the frame edge inward when required and then drawing it back out once the partly occluded subject has fully entered frame. To read more about animating keyframing tracks, turn to Chapter 148, “Keyframing in the Color Page.” The controls and parameters offered by Floating Windows are these.

- L/R/T/B buttons: Lets you pick an edge on which to place a Floating Window. Click the button for the edge you wish to adjust. Each edge carries its own position, rotate, and softness settings.
- Position: Brings masking to the currently selected edge.
- Rotate: Turns the currently selected edge so you can build an angled Window.
- Softness: Feathers the currently selected edge so you can build a soft Window that viewers notice less.

To add a Floating Window to fix a Window violation: 1 Decide which eye should receive the Floating Window.

- For a Window violation on the screen’s right-hand side, click the right eye view to put a Floating Window there.
- For a Window violation on the screen’s left-hand side, click the left eye view to put a Floating Window there.

2 Pick the edge you’ll adjust by clicking the L or R buttons.

- To clear a Window violation on the right-hand side, click R.
- To clear a Window violation on the left-hand side, click L.

3 Tune the Position parameter however much is needed to crop away the strip along the selected eye’s edge that the other eye can’t see. 4 If you decide the Window tweak you just made stands out too much, raise the Softness parameter so that edge becomes harder to notice.

### Outputting Stereo 3D Media in the Deliver Page

For full frame media, each stereo 3D eye has to be rendered on its own through the Deliver page controls, exported in whichever media format the client demands.

### Rendering Frame-Compatible Media

Frame-compatible media packs both left- and right-eye images, anamorphically squeezed, into one media file. To produce it, pick the “Both eyes as” option among the Render Stereoscopic 3D controls sitting beneath the Deliver page’s File output options, then select an output method from the Mesh Options pop-up menu.

Stereoscopic 3D mesh render options on the Deliver page Your choices are Side-by-Side, Line-by-Line, or Top-Bottom. Anaglyph is another choice when you need a classic red/cyan anaglyph stereo 3D image that any display can show.

### Rendering Individual Left- and Right-Eye Clips

When your pipeline calls for delivering separate left- and right-eye media sets, this is simple: either configure a render job with “Render Stereoscopic 3D” set to “Right eye” or “Left eye,” or pick “Both eyes as” and choose the “Separate files” option.

### Apple Spatial Video (MacOS Only)

Newer Apple iPhone models include a Spatial Video mode that records 3D videos meant for viewing in a VR headset. DaVinci Resolve recognizes these spatial videos automatically and lets you apply every DaVinci Resolve feature to them, the complete 3D toolset described above included.

Grading an Apple Spatial Video on the Color page with Anaglyph (B/W) mode engaged (the colorist’s goofy 3D glasses not shown)

### Using Apple Spatial Video in DaVinci Resolve
