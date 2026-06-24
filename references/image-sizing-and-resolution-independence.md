# Image Sizing And Resolution Independence (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Image Sizing and Resolution Independence

DaVinci Resolve counts as a resolution-independent application. What that means is that no matter your source media's resolution, it can come out at whatever other resolution you please, and nearly every size-dependent effect across your project, text, grade windows, edit and input clip scaling, and the rest, scales to suit the new output resolution. It also means you may freely combine clips of any resolution, dropping 4K, HD, and SD clips into one timeline, each scaling to match the project resolution as needed. The resolution of your project can shift whenever, letting you work at one resolution and then deliver at another. That likewise makes it simple to put out several versions of a program at differing resolutions, say 4K, HD, and SD sizes of the same timeline. On top of that, most controls that transform clips, whether to push into a clip for creative reasons or to pan and scan media of one format so it sits better in another output format, are clever enough to keep referring back to the source resolution as they combine resizing operations to first shrink and then enlarge an image for whatever reason while you work across the Cut, Edit, Fusion, and Color pages. How the various sizing and transform controls in DaVinci Resolve relate to one another, and how they cooperate to manage clip and effect sizing intelligently as you work, is what this chapter covers.

### About Resolution Independence

If you read only one paragraph here, make it this one: Resolution Independence in DaVinci Resolve lets you add clips to a timeline in any blend of resolutions to suit whatever project resolution you've settled on, and lets you afterward output that timeline at as many other resolutions as you need to make multiple deliverables. When you do, every effect and transform readjusts itself automatically to fit the sizing of each new timeline resolution, and most transforms get calculated and processed at the full native resolution of the source media you've tied to that clip. Put briefly, this means you can produce multiple deliverables at multiple resolutions just by altering the timeline resolution, or by using a lower resolution setting on the Deliver page versus the timeline resolution when you set up a new render job, and every effect comes out the right size on its own.

### Timeline Resolution

Among your project's most fundamental settings is the timeline resolution, which defines its frame size. You find it in the Master Settings panel of the Project Settings, where you either pick a predefined resolution from the "Timeline resolution" drop-down menu or type a custom resolution into the X and Y fields beneath it.

The project-wide Timeline Resolution parameters, sitting in the Project Settings window's Master Settings panel

### Mixing Clip Resolutions

Media you use in a project needn't match the timeline resolution. Indeed, blending several resolutions inside one timeline is very common. Any clip that doesn't match the current resolution is resized automatically per the Image Scaling setting currently chosen (described below).

### Changing the Timeline Resolution

As noted earlier, the timeline resolution is yours to change whenever you wish. When you do, every Edit page transform scales accurately and automatically to suit the new resolution, and so does each Fusion clip effects output, each Color page Power Window, every Input and Output Sizing adjustment, each tracking path, each spatial keyframing value, plus any other resolution-dependent Resolve FX effect or transform operation in DaVinci Resolve.

### You Can Use Separate Timelines to Output Different Resolutions

From DaVinci Resolve 16 on, you may create separate timelines carrying individual Format (Input Scaling included), Monitoring, and Output Sizing settings for cases where you must set up multiple timelines to make multiple deliverables with different resolutions, pixel aspect ratios, frame rates, monitoring choices, or output scaling options than the overall project, "Mismatched Resolution Files" settings among them. For more information, see Chapter 34, "Creating and Working with Timelines."

### You Don't Need Separate Timelines to Output Different Resolutions

Thanks to the way DaVinci Resolve operates, separate timelines aren't required when all you want is to output the same timeline at several resolutions. You can instead concentrate on mastering one timeline, which you then output to as many other resolutions as you need. As an example, from one lone timeline in a project sitting at 4096x2160 (4K DCI) resolution, you can readily turn out UHD and HD deliverables, plus center-cut SD and center-cut Instagram sized ones, in any format you require, just by altering the Resolution drop-down on the Deliver page Render Settings before you set up a render job. DaVinci Resolve handles the rest.

Within the Render Settings panel, the Deliver page drop-down menu sets which resolution the current timeline is output at

### Using High Resolution Media in Lower Resolution Projects

Every group of transform and sizing parameters and settings that resizes clips is merged intelligently, so that a clip's full source media resolution always serves as the source for any transform. Take, for example, using 8K media inside a 1920x1080 project where you need to enlarge a clip with the Input Sizing palette's Zoom parameter to 200%; the image scales relative to the source's native 8K resolution, and the outcome is fit into the current timeline resolution. That automatically secures top quality for any image transform you make, as long as you don't zoom past any given clip's native resolution.

The same holds when, say, you shrink a clip on the Edit page with the Edit Sizing controls only to re-enlarge that clip on the Color page with the Input Sizing controls. Here DaVinci Resolve is clever enough to do the arithmetic that folds together project resolution along with the Edit Sizing and Input Sizing controls, so a single transform lands on that clip's native source resolution and yields the finest-quality outcome. NOTE: Applying Fusion effects to any clip alters this, as the discussion later in this chapter explains.

### Clip Source Resolution

In DaVinci Resolve, clip resolution is determined by the combination of Pixel Aspect Ratio and Resolution.

### Pixel Aspect Ratio (PAR)

The Timeline Format settings, located in the Master Settings of the Project Settings, let you set a Pixel Aspect Ratio for the project on top of the frame size. This defaults to Square Pixel, which suits high definition projects and most digital media. There are, though, options as well for 16:9 anamorphic, 4:3 standard definition, or Cinemascope. Which ones show up depends on the timeline resolution you've chosen. Beyond that, each clip carries its own adjustable PAR settings in the clip attributes, for when you're blending several media types within one project. If, for instance, you're mixing SD clips that have non-square pixels with HD clips that have square pixels, you can gather every SD clip in the Media Pool and give them the correct non-square pixel ratio PAR setting, whether NTSC or PAL. For more, see Chapter 22, "Modifying Clips and Clip Attributes."

### Clip Resolution

Normally a clip's resolution rests entirely on whatever resolution was set when the media got shot, or rendered out of a compositing, VFX, or 3D package. After a piece of media is made, its native resolution is locked, and to keep that clip's sharpness ideal, you must make sure any resizing transform you apply zooms in by no more than 10-20% beyond the native resolution (if that much), since otherwise the image visibly softens. Even so, DaVinci Resolve supplies advanced Super Scale image processing within every video and image clip's Clip Attributes, letting you resize clips past their native resolution while the apparent sharpness of a clip still inside its native resolution is preserved. It's an illusion, but a convincing one.

### The DaVinci Resolve Sizing Pipeline

The various sizing controls DaVinci Resolve makes available, and how they work in concert, are the subject of this section.

### "Super Scale" High Quality Upscaling (Studio Version Only)

When you need upscaling of better quality than the standard Resize Filters can manage, you can now turn on one of the "Super Scale" options, either in the Inspector or within the Clip Attributes window's Video panel, for a selected clip or several. Unlike the many scaling options across the Edit, Fusion, or Color pages, Super Scale really does lift the processed clip's source resolution, so that clip then carries more pixels than it did and grows more processor-intensive to handle than it was, unless you optimize the clip (which bakes the Super Scale effect into the optimized media) or cache it somehow.

Super Scale options shown within the Clip Attributes' Video panel The Super Scale dropdown menu offers 2-3-4x and 2-3-4x Enhanced, along with Sharpness and Noise Reduction options for tuning the scaled result's quality. Most Super Scale parameters come in fixed Low, Medium, or High increments, but the Enhanced modes let you apply them in variable amounts. Picking one of these options lets DaVinci Resolve bring advanced algorithms to bear on how image detail reads when you enlarge clips substantially, the way you might when cutting SD archival media into a UHD timeline, or when a clip has to be enlarged past its native resolution for a closeup. Depending on the source media you're handling, you may find that setting Sharpness to Medium gives a fairly subtle result that's tough to spot, while setting Sharpness to high should be noticeably more agreeable, though it also sharpens grain and noise in the image to an undesirable degree at the default settings. While raising Noise Reduction eases that, it likewise erodes the gains you made by raising Sharpness. In such cases, it's worth trying to keep Sharpness at Low or Medium so Super Scale sharpens every aspect of a clip, then using the Color page's Noise Reduction tools (with their extra capacity for fine-tuning) to cut the unwanted noise. TIP: Super Scale, useful as it is, taxes the processor, so be aware that switching it on will probably block real-time playback. One workaround is to make Optimized Media for any clip on which you've switched Super Scale on, given that Optimized Media "bakes in" the Super Scale effect. A second tack is to assemble a string-out of every piece of source media you'll need to enlarge at high quality, switch Super Scale on for all of them, and then render that timeline as separate clips while enabling the "Render at source resolution" and "Filename uses > Source Name" options.

### Fusion Effects and Resolution

Every bit of image processing the Fusion page performs happens ahead of effects applied by the Edit page, the lone exception being the Lens Correction effect. As for sizing and image resolution, whether the Fusion page affects resolution hinges on the way you use it. Fusion Effects Inherit the Source Resolution of a Clip Open a Timeline clip on the Fusion page and the Fusion page takes on that clip's full source resolution, whatever the Timeline resolution happens to be. Verify this by glancing at the resolution listed above the Viewer's upper-right corner. Thus, as long as you apply no operation that drops image resolution (covered later), sizing adjustments made afterward on other pages point at the same resolution the source clip has.

Above the Viewer's upper-right corner, circled in red, you can see the currently selected clip's available resolution and bit depth Fusion Clips Inherit the Timeline Resolution Combine several Timeline clips into a Fusion clip and the Fusion page takes on the timeline resolution, no matter the clip's source resolution. The image then goes out to the Edit page at this timeline resolution, and each subsequent sizing adjustment occurs against the timeline resolution, paying no heed to the source clip's original resolution.

The available resolution and bit depth of a clip converted into a Fusion Clip, now sitting at the timeline resolution of 1920x1080

### Operations in the Fusion Page That Change Resolution

Do nothing to change a clip's size on the Fusion page and its resolution holds, so you effectively send that clip's source resolution to the Edit page. Should you Merge the image with a second clip wired to the background carrying a different resolution, however, or reach for a Crop or Resize node to push the image resolution up or down, the fresh resolution then travels to the Cut and Edit pages as that clip's effective source resolution. Put briefly, within DaVinci Resolve's image processing pipeline the Fusion page hands the Edit page whatever resolution your composition's final node emits, treating that as the clip's effective resolution. Fusion Page Transform Operations Are Resolution Independent On the Fusion page, several Transform nodes operate in a resolution-independent fashion against the source clip's resolution. What this gives you is that shrinking an image to 20% with one Transform node and then bringing it back to 100% with a second Transform node leaves you an image carrying all the resolution and sharpness of the input image.

### Fusion Page Resize Operations Are Not

Within Fusion there are two kinds of transform effect, the Transform node and the Resize node. Which one you reach for makes a dramatic difference to resolution independence.

- The Transform node always looks back to the clip's input resolution (as set by the Clip Attributes) so as to allow resolution-independent sizing, meaning several Transform nodes can scale the image down and up over and over on the Fusion page without needlessly losing image resolution.
- The Resize node genuinely lowers image resolution as you shrink an image, or raises it (with filtering) as you enlarge. That means the Resize node breaks resolution independence, locking the image's resolution to whatever you state from that spot in your composite's node tree onward.

In most cases you'll likely want the Transform node so resolution independence relative to the source media holds, unless you specifically aim to alter and maybe reduce image resolution for a particular special effect that deliberately degrades the image. If, for example, you want a clip forced to a standard definition resolution to mimic a low-resolution archival clip, the Resize node will do it. Enlarge the result with a Transform node afterward and it performs a filtered enlargement that looks like a genuine SD clip blown up. Transforms from the Fusion Page to the Edit Page So long as you avoid the Fusion page, every transform operation you apply on the Cut, Edit, and Color pages stays resolution independent, looking to the source media's original resolution. Say you shrink an image to 20% on the Edit page (using Edit sizing controls) and then bring it back to 100% on the Color page (using Input sizing controls); you finish with an image that retains every bit of the original media's resolution and sharpness, since the final resolution is drawn from the original source media.

The moment you use the Fusion page to touch a clip, though, whether adding a tiny effect or constructing an elaborate composition, the source-media resolution-independent link held by the Edit and Color pages is severed, and the resolution emerging from your Fusion composition turns into the clip's new effective resolution as shown on the Timeline. So if you shrink an image to 20% on the Fusion page (with a Transform node) and then enlarge it on the Color page by 150%, you end up with an image less sharp than the original, because the downconverted Fusion-page image is effectively that clip's new source resolution.

### Image Scaling

DaVinci Resolve carries a dedicated mechanism for handling automatically the sizing of clips whose resolutions don't match the timeline resolution, and it sits apart from the Zoom transform controls available for making creative clip adjustments. This is called Image Scaling, and you can customize it across a few different areas.

### Resize Filter Project Setting

The Resize Filter setting lets you pick the filter method used to interpolate image pixels as clips are resized:

- Smoother: Can give a more agreeable result on projects whose clips have to be scaled down to standard definition, since this filter shows fewer sharp edges at SD resolutions.
- Bicubic: Though the sharper and smoother options run slightly higher in quality, bicubic remains a remarkably good resizing filter and demands less of the processor than either of them.
- Blinear: A lower-quality, lighter-on-the-processor setting. Handy for previewing your work on an underpowered computer before you render, at which point you can shift to one of the higher-quality options.
- Sharper: Generally delivers the best quality across most projects, drawing on an optical-quality processing technique found only in DaVinci Resolve.
- Custom: With this setting you take charge of the precise algorithm every resizing operation uses. The custom Resize Filter options on offer include Bessel and Box; Catmul-Rom, Cubic, and Gaussian; Lanczos plus Mitchell; and Nearest Neighbor, Quadratic, and Sinc. Practically speaking, telling these methods apart can be fairly subjective. Still, when you must match a particular resizing method from another application, here's where you do it. For day-to-day work, the ordinary resizing filters in DaVinci Resolve ought to suffice.
- Override Input scaling: Tick this box to pick an Input Sizing preset for the project to use.
- Override Output scaling: Tick this box to pick an Output Sizing preset for the project to use.
- Anti-alias edges: A second batch of settings lets you decide how edge anti-aliasing is handled for source blanking.

Auto: Brings in anti-aliasing whenever any Sizing control transforms the image; otherwise anti-aliasing stays off. On: Keeps anti-aliasing on the whole time. Off: Turns anti-aliasing off. Switching anti-aliasing off may be needed if you spot black blurring along the edges of blanking applied to an image.

- Deinterlace quality: (only available in Studio version) A fourth batch of settings lets you weigh quality against processing time when deinterlacing Media Pool clips via the Enable Deinterlacing checkbox in the Clip Attributes window. Two settings exist:

Normal: A high-quality deinterlacing method fit for most clips. On many clips, Normal can't be told apart from High. During playback in DaVinci Resolve, Normal is always the one used automatically.

High: A more processor-hungry method that can occasionally turn out better results, depending on the footage, at the cost of slower rendering. DaVinci Neural Engine: This option taps the DaVinci Neural Engine's advanced machine learning algorithms to study motion between the fields of interlaced material and rebuild them into one frame. Hugely demanding to compute, this option should ideally yield a result even more pleasing to the eye than the "high" setting.

### Input Scaling Project Setting

When an imported clip's native resolution doesn't match the timeline resolution, the Input Scaling Preset currently chosen in the Image Scaling panel of the Project Settings governs how mismatched clips get handled project-wide. By default it's "Scale entire image to fit," which shrinks or grows the image to match the frame's present dimensions while cropping none of it, laying in letterboxing or pillarboxing as required to cover the frame's remaining area, according to whether the image's horizontal or vertical dimension hits the frame edge first. The Mismatched resolution files option lets you decide how clips that don't match the current project resolution are dealt with. The illustrated examples below show an SD clip fit into an HD project using each of the different options.

### Center crop with no resizing

Clips of differing resolution aren't scaled at all. Clips smaller than the current frame size get surrounded by blanking, while clips larger than it get cropped. Bear in mind this is a good setting to use when importing a timeline from another NLE where clip resolution adjustments come in as scaling adjustments. Choosing "Center Crop with no resizing" keeps DaVinci Resolve from "double scaling" clips in imported timelines.

### Center crop with no resizing

### Scale full frame with crop

Clips of differing resolution get scaled so the clip fills the frame with no blanking. The surplus pixels are cropped. Reach for this setting when clips that fall outside the project resolution should fill the frame on their own, leaving no letterboxing or pillarboxing.

### Scale full frame with crop

### Stretch frame to all corners

Useful for projects relying on anamorphic media. Clips of differing resolution get squished or stretched to match the frame size across every dimension. That way anamorphic media can be stretched to fill full raster, or full raster media squished to fit an anamorphic frame. A bonus of this setting is that it makes blending anamorphic and non-anamorphic clips in one project easy.

### Stretch frame to all corners

### Scale entire image to fit

The default setting. Clips of differing resolution get scaled so each one fills the frame without cropping. The dimension that comes up short receives blanking (letterboxing or pillarboxing). Reach for this setting when clips that fall outside the project resolution should fit the frame automatically without any cropping, and the letterboxing or pillarboxing that follows is fine by you. If, though, you've brought a timeline in from another NLE and certain clips run twice the size they ought to, that's because this setting is on by default and your imported timeline holds imported scaling settings that were used to resize clips not matching the timeline resolution. When that happens, swap to "Center crop with no resizing" instead, and the trouble clears up.

### Scale entire image to fit

### Output Image Scaling Project Settings

Another batch of settings, also sitting in the Image Scaling panel of the Project Settings, optionally lets you choose a different output resolution, whether through the Deliver page or through your video output interface for monitoring or tape output. In particular, within the Render Settings panel of the Deliver page, set the "Resolution" to anything but the timeline resolution and these settings carry out the change. That helps when you're mastering a high resolution 4K project yet want to monitor on an HD display, and you intend eventually to output HD resolution deliverables alongside the 4K ones for which you want different Scaling and/or Resize Filter settings that suit the lower resolution better.
