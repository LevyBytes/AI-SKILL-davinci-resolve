# Controlling Image Processing And Resolution

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Controlling Image Processing and Resolution

The image-processing pipeline as a whole is the subject of this chapter, which takes up color bit-depth alongside the means of steering output resolution within a resolution‑independent setting.

### Fusion’s Place in the DaVinci Resolve Image-Processing Pipeline

Inside one unified setting such as DaVinci Resolve, grasping the sequence in which the pages operate matters a great deal. DaVinci Resolve reveals part of that sequence through how the page buttons line up along the bottom of the screen — the Media, Cut, and Edit page opening the chain, with the Color, Fairlight, and Deliver page closing it. That ordering tells only part of the tale, though, particularly where the Fusion page is concerned. Below, the sections lay out exactly where the Fusion page sits within DaVinci Resolve's image-processing chain.

### Source Media into the Fusion Page

For plain single clips arriving from the Edit or Cut page, the source media is stood in for by the Fusion page's MediaIn node, shaped by whatever the Clip Attributes window specifies. You may pick the clip over on the Edit or Cut page Timeline, yet within the Fusion page it's reached through the Media Pool. TIP: Decoding or debayering of RAW files runs ahead of everything else, so any RAW tweaks render accurately on the Fusion page. What this gives you is the whole source clip on the Fusion page, though the render range gets set to the clip's Timeline duration. The source clip's full resolution is likewise at your disposal, even should the Timeline be configured for something lower. None of the Edit or Cut page Inspector tweaks travel into the Fusion page, however, save for the Lens Correction adjustment. Make Zoom, Position, Crop, or Stabilization changes on the Edit or Cut page and they stay invisible in the Fusion page. The same holds for any Resolve FX or Open FX third-party plugins: apply such items to a clip on the Edit or Cut page, then open the Fusion page, and you won't watch them take hold. Every Edit and Cut page timeline effect and Inspector tweak, the lone exception being the Lens Correction adjustment, is calculated after the Fusion page but ahead of the Color page. Open the Color page and you'll find the Edit and Cut page transforms and plugins laid onto that clip, in effect as a step preceding the grading tweaks and effects you set in the Color page Node Editor. Bearing that in mind, the way effects get processed across the various DaVinci Resolve pages runs like this:

### Source Media

### RAW Debayering

### Clip Attributes

### Fusion Effects

### Edit/Cut Page Inspector Adjustments

### Edit/Cut Plug-ins Resolve FX

### Color Effects

TIP: Retiming you've placed on a clip in the Edit page Timeline likewise fails to follow it into the Fusion page.

### Forcing Effects into the Fusion Page

You can in fact push a clip that carries Edit page Inspector adjustments, alongside plugins, retiming, and grades from the Color page, on into the Fusion page — the trick is converting that clip into a compound clip or a Fusion clip. With Edit page effects and Color page grading baked into compound or Fusion clips, the MediaIn nodes that stand for compound clips feed the affected clip onward into the Fusion page. Pulling a compound clip or Fusion clip into the Fusion page does, however, reset the source clip's resolution so it lines up with the Timeline resolution. Further detail lives in this chapter's “Sizing Between DaVinci Resolve Pages” section.

### Output from the Fusion Page to the Color Page

Whatever composition emerges from the Fusion page's MediaOut node travels onward through the Color page's source input — the one exception being that, if you've attached plugins to that clip on the Edit or Cut page, the pass from the Fusion page to the Color page proceeds like this:

### Fusion Effects

### Edit/Cut Page Inspector Adjustments

### Edit Page Plugins

### Color Effects

### What Viewers Show in Different DaVinci Resolve Pages

Because compositing artists, editors, and colorists each need something different, the viewers present the clip in differing states. The Edit page source viewer: It shows the source media at all times, the one exception being when you open a compound clip stored in the Media Pool. Turn on Resolve Color Management and the Edit page source viewer then renders the source media using the Timeline's gamma and color space. The Edit page Timeline viewer: Here clips appear with every Edit page effect, Color page grade, and Fusion page effect in place, letting editors view the program amid the full set of effects and grading. The Fusion page viewer: This presents Media Pool source clips at the Timeline color space and gamma, Resolve Color Management adjustments included, yet without any Edit page Inspector adjustments or Resolve FX effects and without Color page grades. The Color page viewer: This shows clips carrying every Edit page effect, Color page grade, and Fusion page effect.

### Managing Resolution In Fusion

A comp in Fusion carries no formal resolution of its own.

- On the Fusion page, the Timeline resolution dictates the default resolution of Fusion-generated images such as the Background tool, Fast Noise, Text+, and the like.
- Within Fusion Studio, generator resolution is configured under Preferences > Frame Format, where a standard resolution can be chosen from the drop-down menu or the Width and Height entered by hand.
- A Fusion page composition's resolution is, to begin with, governed by the source resolution of the input image.

Say your Timeline runs at HD resolution (1920 x 1080) while a clip sitting on that timeline has a source resolution of UHD (3840 x 2160); opening the clip in the Fusion page pushes the composition's resolution up to UHD (3840 x 2160). From then on, every Fusion-generated image in the composition comes out at UHD resolution.

### UHD Source Media

### HD Timeline

### Fusion timeline sizing for the Fusion page

### Fusion Page UHD

### Resize Scale Crop Letterbox

### HD res

TIP: Whatever the Fusion page produces returns into the Edit page Timeline according to DaVinci Resolve's Image Sizing setting. Out of the box, DaVinci Resolve relies on an image sizing setting named Scale to Fit. The result is that, even when the Fusion page turns out a 4K composition, it conforms to 1920 x 1080 should that be the project's or a given Timeline's setting. Altering the image sizing setting in DaVinci Resolve's Project Settings changes how Fusion compositions fold into the Edit page Timeline.

### Changing the Resolution of a Clip

Where your comp draws on a single image, the pixel output resolution can be altered through a few different routes. The Resize, Scale, and Crop nodes are three frequently used tools for changing a clip's pixel resolution. A fourth, Letterbox, sees less use but likewise shifts a clip's pixel resolution. All four of these nodes reside in the Transform category of the Effects library, and Resize additionally appears on the toolbar.

- Crop: Fixes the node's output resolution by pairing X and Y size with X and Y offset to trim the frame down to whatever dimensions you're after. Because Crop discards pixels from the image, reaching for a Transform node afterward to reposition the image leaves those pixels unavailable.
- Letterbox: Fixes the node's output resolution by laying horizontal or vertical black edges wherever they're needed to shape the frame size and aspect ratio.
- Resize: Fixes the node's output resolution in terms of absolute pixels.
- Scale: Fixes the node's output resolution as a relative percentage of the current input

image size.

TIP: When you want to rescale and reposition a frame yet leave a clip's pixel resolution untouched, turn to the Transform node.

### Compositing with Different-Resolution Clips

As you composite images of differing resolutions through the Merge node, it's the image feeding the orange background input that settles the Merge node's output resolution. Frequently the simplest way to govern comp resolution from the outset is to wire a node holding your intended output resolution into that orange background input on the Merge node. A Background node tends to be the pick here, since it draws very little from your system.

A Background node fixes the merge's output resolution The Background node establishes the output size, and a foreground image bigger than that gets cropped.

A Background node made at 1280 x 720 crops the larger foreground. Even so, the whole pixel content of that larger foreground stays on hand for repositioning.

### Downscale Clip Compositions to Timeline Resolution

Should your machine be laboring under your Fusion comps, switch on Project Settings > Fusion > Downscale Timeline Resolution for Timeline Clip Compositions. With it active, your clips are scaled down to the timeline resolution before any processing happens. That lets you, for one, handle 4K original footage in an HD timeline while carrying only HD-sized processing overhead. NOTE: EXR files stay un-downscaled no matter the Downscale Timeline Resolution for Timeline Clip Composition settings, on account of the potentially enormous number of information channels they may hold.

### Sizing Between DaVinci Resolve Pages

How sizing operations are ordered across DaVinci Resolve pages carries a touch more subtlety. Knowing which sizing operations land inside the Fusion page versus afterward matters, because it tells you which effects reshape the image fed into the Fusion page and which reshape what the page puts out. Lens correction, for instance, isn't strictly a sizing operation, but it still alters how the image enters your Fusion composition. The Edit or Cut page stabilization function, by contrast, is an effect occurring past the Fusion page, so it never shows up in the composition you're building. Across the various DaVinci Resolve pages, the sequence of sizing effects can be laid out this way:

### Super Scale

### Edit/Cut Page Lens Correction

### Fusion Transforms

### Edit/Cut Page Transforms

### Input Sizing

### Output Sizing

### Sizing with Compound and Fusion Clips

One more route for reshaping resolution before clips pass from the Edit page over to the Fusion page is to build a compound clip or a Fusion clip. Either kind shifts the working resolution of the constituent clips to align with the Timeline resolution. Stack two 4K clips one atop the other in an HD timeline, say, and forming a compound or Fusion clip rescales them to HD. The individual 4K clips' full resolution then isn't on offer in Fusion and is consequently passed to the Color page at the reduced size. To hold onto source clips' full resolution, carry just a single clip into the Fusion page from the Edit or Cut page Timeline, then draw the rest into the Fusion composition by way of the Media Pool. Naturally, when your clips are full HD and your timeline is full HD too, making a Fusion clip or compound clip leaves the resolution alone.

### UHD Source Media

### Timeline HD Resolution

### Fusion Clip Compound Clip

### Fusion timeline sizing for Fusion and Compound clips

### Fusion Page Timeline Resolution

### Color Bit Depths

Bit depth refers to the count of colors on offer in the palette from which an image is built. A larger bit depth means finer color precision in the image and, with it, richer color reproduction. That extra precision reveals itself most in gradients carrying delicate transitions. Gradients of lower bit depth pick up visible banding artifacts, while images of higher bit depth can render more colors, so banding artifacts grow scarce or vanish entirely. Inside DaVinci Resolve the Fusion page invariably processes images at 32-bit float bits per channel precision. In Fusion Studio, though, you may opt to process images at 8-bit integer, 16-bit integer, 16-bit float, or 32-bit float bits per channel. Staying at 16-bit float or 32-bit float always yields the finest quality, yet leaning on a lower bit depth can prove more efficient when your images start out in 8-bit or 16-bit integer formats.

### Understanding Integer vs. Float

As a rule, 8-bit integer color processing marks the lowest bit depth you'll meet among video formats. Images at 8-bit originate from older or consumer-grade gear such as mobile phones and camcorders. Push any sizable gamma or color correction onto 8-bit images and banding often grows more apparent. Stepping up to 16-bit integer color depth doubles the precision and clears away banding troubles. You can apply 16-bit integer processing to an 8-bit clip, but doing so won't lessen banding already baked into the original file, though it does help once you start piling further effects onto the clip. This seems like the ideal answer right up until you notice that plenty of digital cameras — the Blackmagic Design URSA Mini Pro among them — record in formats able to capture over-range values, with shadow regions under 0.0 and super highlights over 1.0, all of which get cut off at 16-bit integer. The 16-bit float color depth gives up a sliver of the precision found in ordinary 16-bit integer color depth in exchange for storing color values below 0 and above 1.0. Often termed half-float, 16-bit float turns up most commonly in the OpenEXR format and packs ample dynamic range for the bulk of film and HDR television work, all while demanding far less memory and processing time than full float, 32-bit images call for.

Holding onto over-range values lets you shift exposure without sacrificing highlights Working at 32-bit float copes with shadow regions under 0.0 and highlights over 1.0 much as 16-bit float does, only with a far wider span of precision and, alongside it, far heavier memory and processing demands.

### Setting Color Depth in Fusion Studio

As noted before, DaVinci Resolve always processes at 32-bit float bits per channel; even so, the Performance Mode setting in the User > Playback Preferences panel lets you spend less memory and still land more-than-acceptable results. Fusion Studio picks, on its own, whichever color depth best suits each file format. Pull in a JPEG file from disk, for instance, and the Loader's color depth is fixed at 8 bits per channel. Given that JPEG is an 8-bit format, loading it at a deeper color depth would mostly be a waste. Bring in a 16-bit TIFF and the color depth lands at 16 bits. A DPX file defaults to 32-bit float, whereas OpenEXR typically defaults to 16-bit float. That automatic per-format color depth can be overridden, however, through the settings in the Import tab of the Loader node's Inspector. Both the Loader's Inspector and the Inspector for images Fusion generates (text, gradients, fast noise, and so on) carry a Depth menu offering 8-bit, 16-bit integer, 16-bit float, and 32‑bit float.

### The Loader’s Inspector Color Bit Depth settings

### Configuring Default Color Depth Preferences

When set to default, the color depth pushes the tool to process according to whatever the Node Editor's Frame Format preferences hold. Those preferences establish a default color depth value that kicks in as a Generator tool joins the Node Editor. The preferences carry three drop-down menus for configuring color depth, each naming a separate color depth for the interactive session, for final renders, and for preview renders. For better performance while you build your comp, you might pin the Interactive and Preview depth at 8-bits per channel and leave final renders at 16-bit integer. That said, when the output of your final render is 16-bit float or 32-bit float, steer clear of the integer options for the interactive setting, since the finished results can diverge markedly from interactive previews left on integer options.

### The Frame Format Color Depth settings

Unsure which color depth a tool processes at? Rest the pointer on the node's tile in the Node Editor and a tooltip naming that node's color depth shows up on the Status bar.

Hover over a node to read its Color Bit Depth setting. TIP: For images carrying 10-bit or 12-bit dynamic range or more, such as Blackmagic RAW or Cinema DNG files, set the Inspector's Depth menu to either 16-bit float or 32-bit float, which holds onto highlight detail throughout compositing.

### Combining Images with Different Color Depths

Images of differing color depths can live together within one composition. Once such images are merged, the bit depth output is dictated by the image coming from the node's background input, with the foreground image brought into line to match.

### Advantages of Floating-Point Processing

Floating-point processing brings two big upsides that justify its heavier RAM appetite and slower renders. For one, floating-point values carry more accuracy than integer values do. For another, it holds onto shadow and highlight values that reach past the usual tonal range.

### Greater Accuracy

Working in 16- or 32-bit floating point keeps you from the accuracy loss that 8- or 16-bit integer processing can introduce. It comes down to this: integer values have no room for fractional or decimal numbers, so rounding creeps into every image operation. Floating-point processing, by allowing decimal or fractional values per pixel, never has to snap a pixel's values to the nearest integer. The payoff is color precision that stays all but flawless however many operations an image goes through.

Picture an 8-bit pixel whose red value is 75 (dark red); halve it with a Color Correction tool and the pixel's red value becomes 37.5. Because integers can hold no decimal or fractional values, that figure rounds down to 37. Then doubling the pixel's brightness with a second Color Correction tool ought to restore the original 75, but rounding makes 37 x 2 come out to 74. In that very plain example, integer rounding cost the red value a whole point of precision. The trouble is that it can breed visible banding across a run of color corrections, and the same kind of thing crops up when merging or transforming images. The longer the chain of operations applied to an image, the more color precision rounding eats away under 8- or 16-bit integer processing.

### Accessing Extended Highlights and Shadows

A growing share of productions now record out-of-range images, thanks to digital cinema bodies such as the Blackmagic URSA Mini Pro and even the Pocket Cinema 6K camera. Such cameras grab RAW images of very high dynamic range and hold onto color detail even in frames that are badly over- or underexposed. That extended white color detail can also produce lovely, natural-looking results once it's blurred, glowed, color corrected, or simply faded or dissolved. You can certainly handle these RAW images with integer data, but going that way discards the extended-range values, wiping out all detail in the highlights and shadows. Float processing eases work with logarithmic RAW images a great deal by keeping highlight and shadow detail intact. Take an 8-bit pixel with a red value of 200 (bright red) and run a Color Gain tool to double the red channel's brightness: the math gives 200 x 2, or 400. Yet 8-bit color values can only span 0 through 255, so the pixel's value gets clipped to 255, pure red. Halve the brightness now and you land on half of 255, or 127 (rounded), rather than the starting 200. Process colors in floating point, by contrast, and pixel values brighter than white or darker than black survive — nothing is clipped. The viewer still shows the pixel as pure red, but had float processing stood in for 8-bit, that second pass halving the gain would have carried the pixel back to its original 200.

### Using Float with 8-Bit HD Video

Float color depths carry some worth with 8-bit HD video too, whenever the images demand heavy color correction. Choosing float helps hold precision by sidestepping the rounding errors that plague 8-bit processing, as covered above.

### Detecting Extended Highlight and Shadow Values

Even though floating-point processing keeps extended values under 0.0 and over 1.0 — the so-called “out-of-range values” — the viewer goes on showing them as plain black or white. That can leave you hard-pressed to gauge an image's overall dynamic range.

To find out whether a viewed image holds out-of-range values: Right-click within the viewer and pick Options > Normalized Color Range.

Reach for the Normalized Color Range pop-up menu to spot out-of-range images. Switching this display mode on rescales the image's color values so the brightest color maps to 1.0 (white) and the darkest maps to 0.0 (black). The 3D Histogram subview lends another hand in picturing an image's out-of-range colors. For fuller detail, the DaVinci Resolve Reference Manual covers this under Chapter 69, “Using Viewers.”, while the Fusion Reference Manual addresses it in Chapter 7.

### Clipping Out-of-Range Values

Processing in floating point, you may now and then run into cases where an image's out-of-range values have to be clipped. Checkboxes on the Brightness/Contrast tool exist to clip out-of-range values to 0 or 1. Some files, for example, hold out-of-range alpha values. Because the alpha channel stands for a pixel's opacity, going beyond fully transparent or beyond fully opaque makes little sense, and compositing an image like that can yield surprises. To clip alpha values under 0 and over 1 with ease, bring in a Brightness/ Contrast toolset to Clip Black and Clip White while leaving only the Alpha checkbox ticked.

The Clip White and Clip Black settings within Brightness/Contrast serve to clip mattes. As another option, clip the range by dropping in a Change Depth node and moving to 8-bit or 16-bit integer color depths.
