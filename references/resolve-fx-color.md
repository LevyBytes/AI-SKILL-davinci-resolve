# Resolve Fx Color (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Resolve FX Color

What these plugins deliver are color-processing techniques you won't find in any of the Color Page palettes on the Color page, and they bundle in a handful of color-management tools usable beyond Resolve Color Management (RCM).

### ACES Transform

This one carries out the same sort of color transforms handled by the ACES Input Device Transform and ACES Output Device Transform parameters over in the Color Management panel, yet it doesn't require ACEScc or ACEScct to be switched on.

- ACES Version: Once you've picked one of the ACES color science options, this pop-up unlocks so you can settle on which version of ACES to run.
- Input Transform: From this pop-up menu you choose the IDT (Input Device Transform) used to process the image. The choices it offers match those found in the Color Management panel of the Project Settings.
- Output Transform: This pop-up menu is where you pick an ODT (Output Device Transform) for converting the image data so it can be monitored on your calibrated display and when a timeline gets exported from the Deliver page. The choices it offers match those found in the Color Management panel of the Project Settings.
- Gamut Compress Type: Here you decide which flavor of ACES Gamut compression the node applies. Either choice can keep highly saturated monochromatic light sources (LEDs, neon signs, tail lights, etc.) from clipping the gamut.

For a fuller picture of what these parameters bring to the table, head to Chapter 9, "Data Levels, Color Management, and ACES." NOTE: The ACES transforms this plugin performs are done correctly, relying on the transforms the Academy lays down, while the Color Transform plugin instead converts colormetrically into the ACES color space—an approach that isn't genuinely correct for ACES pipelines.

### Chromatic Adaptation

Belonging to the Color category, this plugin lets you accurately convert an image that was lit or processed on the assumption of one given color temperature over to a different, user-chosen color temperature. The conversion shifts how every color in the image looks to human vision in just the way a fresh illuminant would—be that illuminant a light in the scene being captured or the color temperature of a display the image appears on. The plugin proves handy whenever you need to carry out particular color-temperature conversions within color-management pipelines, or to dial in precise color-temperature tweaks as part of a creative grade.

- Method: A range of transform methods is on offer in the Method pop-up menu, with CAT02 as the default. Every entry in the Method pop-up menu relies on a distinct set of measurement data to build its own CAT matrix that steers the conversion. Because of that, each method puts its accuracy emphasis on a different group of colors. To illustrate:

CAT02 carries a non-linear component that counters the way extremely saturated blues tend to drift purple, a common shortcoming of rival methods. For the broadest spread of measured data sets it tends to deliver the best outcome, and it shines with emissive sources (displays) and dim viewing surroundings. Bradford Linear sees frequent use as well, even though it's a method where extremely saturated blues will go purple over the course of the transform. It performs nicely both for emissive sources in dim rooms and for reflective sources (theater screens) in dark settings.

Von Kries ranks among the oldest of the commonly used methods, though it too is one where extremely saturated blues will go purple during the transform. Both it and all the rest are on hand should you need to match work produced in some other image-processing application.

- Source/Target Illuminant: You steer this conversion through pop-up menus that set the Illuminant Type for the source (usually whatever color temperature the camera was dialed to) and for the target you'd like the image converted to. With either group of controls, you may select a Standard Illuminant off a list, a Color Temperature by way of a slider, or CIE 1931 xy coordinate values. This conversion is remarkably precise, since the image first moves from the Timeline Color Space into XYZ, and then it's converted to match the LMS (long, medium, short) color space that mirrors how the human eye's cones respond to colors under various illuminants.
- Current Color Space and Gamma: This plugin further accounts for the clip's current color space and gamma, which default to whatever the current timeline is set to. Should you want to alter these values, the Color Space and Gamma menus let you do so.

NOTE: Keep in mind that every method on the list nails neutral colors flawlessly; where they part ways is purely in how each handles the conversion of various bands of saturated color.

### Color Compressor (Studio Version Only)

This filter gives you the ability to squeeze a span of colors toward one chosen target color. It performs at its best on similarly hued regions you've already isolated using a secondary qualifier or window. As an example, when you're adjusting something unevenly lit—a soda can or a dress that has to hold a very specific hue—you can isolate the item and reach for this filter to drive its span of Hue, Saturation, and Luminance nearer to the target color you've pinned down with the color picker.

(Before/After) Employing the Color Compressor plugin within a secondary operation to squeeze the jacket's starting spread of hues down into a tight "target" range

- Target Color: A color control letting you settle on a particular color or sample one out of the image with the eyedropper. Whatever color values you select here are the ones every other color gets nudged toward.
- Compress Hue, Compress Saturation, and Compress Luminance: With these sliders you can separately tighten the span of colors you're adjusting in the image so it tracks the image ever more closely. At 0, no compression happens; at 0.500 the image's original range of colors has been shifted halfway between their starting values and those of the Target Color; and at 1.000 the original color range has been forced to match the Target Color exactly.

### Color Space Transform

This carries out the same kind of color transforms that LUTs do, but rather than relying on lookup tables, the plugin draws on the very math used by Resolve Color Management (RCM) to perform extremely clean color transforms without any clipping.

### Color Space Transform

It surfaces four pop-up menus for setting an Input Colorspace, Input Gamma, Output Colorspace, and Output Gamma, so you can run controlled transforms from the Input settings over to the Output settings directly inside a grade. You needn't have Resolve Color Management switched on to make use of this filter. With the Swap button you can flip the color and gamma space conversion in a hurry.

### Tone Mapping

Switching on tone mapping via Tone Mapping Method accommodates pipelines where one color space has to be turned into another carrying a hugely larger or smaller dynamic range, automating a stretch or squeeze of image contrast in a way that yields a pleasing result free of clipping.

- None: Picking this turns off Input DRT Tone Mapping. Not a bit of tone mapping touches the Input to Timeline Color Space conversion, so you end up with a plain 1:1 mapping to the Timeline Color Space.
- Clip: Hard clips all out-of-bounds values.
- Simple: Leans on a plain curve to carry out this conversion, squeezing or stretching the

highlights and/or shadows of the timeline's dynamic range so they sit better within the output dynamic range. Bear in mind that the "Simple" option maps somewhere between roughly 5500 nits and 100 nits, so when you're going from an HDR source carrying upward of 5500 nits to an SDR destination, the highlights past 5500 nits may still see a bit of clipping.

- Luminance Mapping: Works just like DaVinci, but lands more accurately when every piece of your media shares a single standards-based Input Color Space, like Rec. 709 or Rec. 2020.
- DaVinci: With this option the transform gets tone mapped using a gentle luminance roll-off through the shadows and highlights, plus measured desaturation of image values in the very brightest and darkest stretches of the picture. It comes in especially handy with wide-gamut camera media and makes a solid pick when you're blending footage from several cameras.
- Saturation Preserving: This option likewise applies a gentle luminance roll-off in the shadows and highlights, yet does it without draining saturation from the dark shadows and bright highlights, which makes it a good fit for colorists fond of pushing color harder. Still, since over-saturated highlights can read as unnatural, two parameters are surfaced to hand you some adjustable automated desaturation.

Sat. Rolloff Start: Here you fix a threshold, measured in nits (cd/m2), where saturation begins falling off in step with highlight luminance. This marks where the rolloff begins. Sat. Rolloff Limit: Here you fix a threshold, again in nits (cd/m2), where the image ends up fully desaturated. This marks where the rolloff ends.

- Use Custom Max Input/Output: Ticking these boxes and moving the slider underneath lets you spell out the input image's minimum and maximum luminance in nits. Working the two sliders in tandem, you can decide which value of the Input Gamma maps over to which value of the Output Gamma.
- Adaptation: This compensates for big swings in the viewer's state of visual adaptation between watching a bright image on an HDR display and seeing that same image on an SDR display. With most "average" images, a setting somewhere between 0–10 works best. That said, when you're converting very bright images (a snow scene at midday, for instance), a higher value will tease out more detail within the highlights.

### Gamut Mapping

Choosing a Gamut Mapping Method serves pipelines where one color space must become another with a vastly larger or smaller gamut, helping to automate a stretch or squeeze of image saturation so the result reads as pleasing and naturalistic without clipping.

- Choosing None results in no Gamut mapping at all.
- Picking Saturation Mapping out of this menu switches on saturation mapping so it can squeeze the span of

saturation values coming from the Input Color Space and Gamma down into the Output Color Space and Gamma. Doing so switches on the Saturation Knee and Saturation Max. controls. Where saturation mapping kicks in is set by the Saturation Knee slider, marking an image level beneath which nothing gets remapped. From that level upward, every saturation value gets remapped per the Saturation Max. slider. Here, 1.0 stands for the fullest saturation possible within whatever output color space is active. As for the Saturation Max slider, it fixes the fresh ceiling you'd like every saturation value above the Saturation Knee setting raised or lowered to. Once again, a reading of 1.0 marks peak saturation inside the output color space you've currently got selected.

- Choosing "Clip" hard clips all out-of-gamut values.

NOTE: Even though this plugin carries ACES settings, the way it converts into the ACES color space is colormetric, which isn't truly correct for ACES pipelines. When you're on a genuine ACES pipeline, reach instead for the ACES Transform plugin, which draws on the transforms the Academy specifies.

### Advanced

This drop-down opens up the advanced capabilities of the Color Space Transform effect.

- Apply Forward OOTF: Tick this box to take the image from scene-referred over to display-referred color management.
- Apply Inverse OOTF: Tick this box to take the image from display-referred over to scene-referred color management.
- Use white point adaptation: Runs a chromatic adaptation transform to reconcile differing white points across color spaces. Leave this box unticked if you'd simply like to see the input color space's white point carried into the output color space untouched. As an example, you might want a P3-D60 mastered clip inside a P3-D65 timeline strictly for reference. Tick the box to run the chromatic adaptation transform, converting the input white point so it lines up with the output color space's white point. As an example, you might want a P3-D60 mastered clip to intercut cleanly with other clips mastered in a P3-D65 timeline.

### Color Stabilizer (Studio Version Only)

Built to handle clips suffering from inconsistent exposure and color—brought on by hand-twisting a lens's aperture, or by a camera's auto exposure and white balance shifting color and brightness partway through a shot in unwanted ways. The Color Stabilizer plugin examines one frame of the clip that embodies the exposure and color you want, then automatically brings every other frame of the current clip into line with those analyzed levels. IMPORTANT: You'll get the strongest results out of the Color Stabilizer on clips whose highlights aren't clipped. Within the Color page, the advice is to first grade the image so all the highlights you care about land at or below a value of 1023, then drop the Color Stabilizer onto a node downstream of that adjustment. The Color Stabilizer is best run before you grade the image. Grade ahead of running the Color Stabilizer and the outcome can turn unpredictable. The Color Stabilizer can be put to work in two ways:

- The simplest route is to pick Entire Frame from the Region of Analysis pop-up menu. Next, slide the playhead in the Viewer onto the frame holding the contrast and color you want spread across the whole clip, and hit the Analyze Now button. Now play back through the clip and the shifts in contrast and color ought to be gone. This route works best on clips where the inconsistency you're out to remove affects the whole picture.
- An alternative is to pick Selected Area from the Region of Analysis pop-up menu. Doing so brings up an onscreen rectangle you can resize and drag over a particular region you'd like to sample across the clip's length. If the feature you've selected to analyze happens to be moving, you can lean on the FX Tracker to follow the subject so the selection box trails it (which matters for a steady result). With that arranged, slide the playhead in the Viewer onto the frame holding the contrast and color you want the whole clip to carry, and hit the Analyze Now button. Now play through the clip and the contrast and color shifts should be gone. This lets you steady the shot's color even as dark objects pass through the frame or the highlights change level. The selection box lets you zero in on analyzing the part of the frame carrying the unwanted exposure change while leaving the desirable exposure change alone.

Which extra options surface will vary according to the choice you make in the Region for Analysis pop-up menu.

### Analysis Region

Pick "Selected Area" from the Region of Analysis pop-up and a rectangle shows up in the Viewer, whose position, scale, and size you govern by clicking and dragging its corners in the Viewer. These on-screen controls let you reshape the selection box that marks which slice of the image gets analyzed.

### Channels to Stabilize

Once the frame holding that clip's ideal contrast and color has been analyzed, you'll decide how the correction happens by way of the Channels to Stabilize controls. Through the What to Stabilize pop-up menu you pick between stabilizing White Balance and Brightness, or R, G, B Channels Separately.

- Pick White Balance and Brightness, and two checkboxes let you decide independently whether to bring in Stabilize White Balance and Stabilize Brightness.
- Pick R, G, B channels separately, and three checkboxes turn up for Stabilize Red, Green, and Blue Channel, so you get to single out exactly which channels to correct.

Through the Stabilize drop-down menu you pick how the correction gets applied, its choices being Levels and Contrast, Offset, and Gain. Each one tackles the needed correction by a separate method, so should one fall short on whatever specific trouble your clip is showing, you're free to fall back on the others in pursuit of a better outcome.

### Captured Analysis Values

With the frame analyzed, a further set of parameters surfaces showing the captured analysis values that the automated correction rests on, so you can tweak things by hand where needed to sharpen the outcome. Which parameters appear hinges on the option you settled on in the What to Stabilize pop-up menu.

- Had you chosen White Balance and Brightness, you'll get a Normalized White Balance color control plus Low Level and High Level sliders.
- Had you chosen R, G, B Channels Separately, you'll get Red, Green, and Blue High and Low Level sliders.

### Contrast Pop (Studio Version Only)

A harsher, more targeted take on the Midtone Detail control over in the Color Wheels palette, crafted to drop either crisp high-contrast looks or gentle low-contrast looks onto a chosen slice of the image's tonal range.

- Detail Amount: Lets you set how heavily this effect lands. At 0, nothing is applied. Push into positive values and progressively crisper contrast builds, while negative values bring on progressively softer low-contrast.
- Detail size: Lets you pick which image structures this local contrast tweak touches, ranging from smaller ones to larger ones.
- Low and High Threshold: With these values you mark out which slice of image tonality the filter acts on, so you can leave either shadows or highlights out of the operation.
- Softness: Lets you ease the transition between the image's affected and untouched regions.

### DCTL (Studio Version Only)

Gives you a way to drop in a DCTL anywhere ResolveFX plugins are allowed. To dig deeper into DCTLs along with their install locations, consult Chapter 201, "Creating DCTL LUTs."

- DCTL List: A pop-up through which you select among the DCTLs that are already present at the location on your machine. Under Mac OS X, that path reads Library/Application Support/Blackmagic Design/DaVinci Resolve/LUT/ whereas on a Windows box it becomes C:\ProgramData\Blackmagic Design\DaVinci Resolve\Support\LUT and for Linux users the folder is /home/resolve/LUT
- Reload DCTL: Lets users refresh the content of the currently loaded DCTL file. With it, you can edit the DCTL in a text editor and then reload to view the outcome. It won't refresh the DCTL list, though; for that you have to relaunch the DaVinci Resolve application.

### Dehaze (Studio Version Only)

Crafted to let you tweak color and contrast so the visible signs of Aerial Perspective (that is, smog, airlight, and haze) in an image are toned down. The filter builds a simulated depth map on its own, drawn upon to lay more of this corrective color tweak onto distant parts of the image—those a haze would hit hardest—and less onto the nearby parts. It gauges haze and provides options for steering that estimate and shaping the processing.

- Dehaze Strength: This slider lays down a color and contrast tweak at once. Pushing Dehaze Strength up gently lifts contrast (the shadows most of all) while rebalancing color toward the complement of the chosen Haze Color and selectively boosting saturation. Pulling Dehaze Strength down lowers contrast and rebalances color back toward the chosen Haze Color itself while selectively trimming saturation.
- Haze Color: A color control letting you pick or sample the color of the smog, airlight, or haze in an image that you'd like to cut down.
- Display Depth: Lets you look at the simulated depth matte being built. Switch this on before you touch the Shadow and Highlight controls below.
- Shadow: This slider lifts or lowers the darkest stretches of the simulated depth map that mark which parts of the image are reckoned to be farthest away.
- Highlight: This slider lets you lift or lower the lightest stretches of the simulated depth map that mark which parts of the image are reckoned to sit closest to us.

### Despill

Strips away the color cast thrown onto a subject by light bouncing off the green or blue screen. That cast can linger even after the green screen's been keyed out. The Despill filter helps in cutting down spill after keying, or alongside keys or masks generated elsewhere.

- Key Color: Sets which color gets pulled off the subject—Red, Green, or Blue.
- Strength: How much Despill to apply. 1.000 matches having despill "on" in the earlier version

of the 3D Keyer checkbox. Having strength be adjustable is useful, since you get to hold on to more of the source color information whenever the situation permits. As an instance, a lighter despill makes sense if the fresh composited background is itself going to be green.

The Despill FX clearing a green color cast off the subject's arms and hair. The top shows no despill, the bottom full despill.

### False Color (Studio Version Only)

False Color is meant to mirror precisely the false color readout of a Blackmagic Design camera, yet it can also serve as a creative effect—recreating camera HUDs, infrared sensors, and custom posterization looks by remapping pixel brightness onto adjustable color bands and gradients. The color set can either echo the False Color setting on a particular Blackmagic Design camera or be tailored from a list of creative style presets supplied for use or inspiration. Those presets can be reshaped by setting how many colors are in play and spelling out the tonal range each color covers.

### Resolve FX False Color Camera preset and legend

Resolve FX False Color thermal creative preset and legend

### General

- Plugin Mode: This menu flips between matching a particular Blackmagic Design Camera's False Color setting and reaching the creative presets. With Specific Camera Model picked, the Camera Model section appears so you can select the camera and settings you want. With Creative picked, the Color bands section appears for selecting and tailoring the preset.

### Camera Model

The Camera Model controls show up once Specific Camera Model is picked from the Plugin Model menu. Through these menus you match the False Color of a camera configuration.

- Camera: Selects the exact Blackmagic Design camera sensor.
- Camera Mode: Selects the dynamic range setting.
- ISO Level: Sets the ISO or light sensitivity setting.

### Color Bands

These controls show up once Creative is picked from the Plugin Model menu. The Color Bands cluster of controls handles selecting and reshaping how the False Color presets look.

- Creative Style: Picks whichever of the effect's built-in style presets you want.
- Number of Bands: Lets you decide how many distinct colors make up the scale.
- Show Sliders: Brings out the Top and Bottom controls that let you pick a color's particular range

expressed as percentages. As an instance, dialing a Red color value to sit between Bottom 45 and Top 55 will shade red every part of the image whose brightness on the waveform monitor falls between 45 and 55%.

- Color: Hands you either a color swatch or a picker for choosing the band's color.

### Preprocessing

This cluster of controls handles laying tonal and blur processing onto the image.

- Blur: Applies a blur filter to the image before analysis.
- Black Level: Grows or shrinks the shadow range handed to colors landing lower on the

False Color legend.

- White Level: Grows or shrinks the highlight range handed to colors landing higher on the

False Color legend.

- Gamma: Nudges the mid-tone range toward whichever colors sit lower or higher along the False Color legend.

### Scale/Legend

This section governs how visible the False Color legend is and how it looks, sitting at the frame's left. The Legend lays out how dark-to-light inputs get mapped onto new colors. It is burned in to the image.

- Show Scale: Shows or hides the Legend.
- Show Values: Toggles whether numeric values appear on the Legend. Those numeric values stand for

differing scales according to the Value Style menu.

- Show Labels: Toggles whether data point labels appear on the Legend. Those labels flag the key data

points across the tonal range—black clipping, white clipping, and middle gray among them.

- Contrast: Grows or shrinks the transparency of the underlay behind the Legend's background.
- Value Detail: Grows or shrinks how many axis value labels get shown on the Legend.
- Value Style: This menu carries three options for the scale used by the Legend's numeric values.
