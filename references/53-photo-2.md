# Photo (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Over in the right hand column sit the capture controls; what you can do here varies with your camera model, since many cameras let you alter their settings straight from this capture interface. The top toolbar gives you direct command over things like aperture, shutter speed, ISO and Exposure compensation. Just below that, focus is adjusted by spinning the wheel or tapping the direction buttons. Drop further down into Settings to reach more advanced camera options. Any camera settings the device does not support appear grayed out. Just to the left you have the Capture Live View, refreshing live with whatever your camera currently sees, including onscreen overlays such as focus boxes and focus peaking. The panel furthest to the left holds the most recent photo you captured, letting you weigh it against your current shot setup. Whenever you wish, the Capture Live View slider pauses the Live View. As soon as the framing matches what you want, fire off the image by pressing the shutter release button in the top right of the capture controls.

### Capture

These tools let you drive your camera and grab images.

- Camera Name: The model of camera that is connected to capture.
- Half Press: Click this icon to issue a half-press to the camera, a common way to lock autofocus

before the shutter fires.

- Shutter Release: Click this icon to trip the camera’s shutter release and take a photo.
- Aperture: Shows the currently selected aperture of the camera lens.
- Shutter Speed: Shows the currently selected Shutter Speed of the camera.
- ISO: Shows the currently selected ISO of the camera.
- Exposure Compensation: Shows the currently selected exposure compensation of the camera.
- AutoFocus: Click this icon to set the autofocus.
- Control Wheel: Whichever parameter is presently active and adjustable, the control

wheel together with the forward and backward controls lets you change its value.

- Enable Capture Live Preview: Flip this toggle on to bring up the Live Camera Preview in

the viewer.

### Scopes

The scopes shown here match the ones found in the Inspector. Whichever scope is chosen refreshes live off the camera data.

### Settings

From the Capture interface, these settings give you direct command of the tethered camera. Some or all of these modes might be unavailable, depending on your particular camera.

- Shooting Mode: Choose how the camera exposes; you will commonly see A (aperture priority), then S (shutter priority), along with P (program), and finally M (manual). Which ones appear can vary from camera to camera.
- Aperture: Sets the lens’ aperture.
- Shutter: Sets the camera’s shutter speed.
- ISO: Sets the camera’s ISO
- Exposure Comp: Specifies how many stops of exposure compensation the camera applies.
- White Balance: Set’s the camera’s white balance setting preset.
- Temperature: Set an exact white balance temperature in degrees kelvin.
- Drive: Choose how the camera advances frames. You will often find Timer, and High Frame Rate, etc.

Exactly which options appear here comes down to your camera model.

- Focus Mode: Choose how the camera focuses. You will often find AF-S, AF-C, Manual, etc.

Exactly which options appear here comes down to your camera model.

- Focus Area: Choose where the camera focuses when working automatically. You will often find Wide,

Center, Zone etc. Exactly which options appear here comes down to your camera model.

- File Settings: Choose which format the captured image takes. You will often find RAW, .jpg,

RAW+.jpg etc. Exactly which options appear here comes down to your camera model.

- File Size: Sets the file size of the photo format.

### Production

This toolset exists to assist with file and photo management chores.

- File Name: Lets you set up automatic naming rules for the photos you capture next, mixing plain text with metadata variables (which you trigger by first typing a % sign).
- Custom Name: Lets you enter a friendlier, more readable photo name that surfaces in the Media Pool without disturbing the original file name.
- Production Name: Lets you enter a production (shoot) name so this field is available for organizational purposes.
- Location: Click the browse button to bring up a file requester where you choose where the captured photos are kept.
- Add To Bin: Pick a Media Pool bin into which each captured photo lands automatically.
- Add to Album: Pick an Album into which each captured photo lands automatically.
- Keywords: Add any specific keywords here describing the photo for organizational purposes.
- Auto Select Latest Captured Image: Tick this box so the most recently captured image is always selected in

the interface, ready for further work.

### Overlay

With this toolset you can lay an existing image over the Capture Live View. It is a help when composing for model placement, aspect ratio, or simply lining up with an earlier shot.

- Overlay Image: Hit the Browse button and select whichever image you want laid over the Capture Live View window.
- Zoom X/Y: Scale the overlay image larger or smaller as required to fit the shot in the Capture Live View window.
- Center Position X/Y: Shift the overlay image up or down as required to fit the shot in the Capture Live View window.
- Opacity: Adjust this slider to change the transparency of the overlay image.
- Flip: Click these icons to flip the overlay image horizontally or vertically.

### Inspector

Opening the Inspector lets you tweak RAW and Photo parameters for photos, adjust any Effects you have applied, and supply File metadata. Ways to bring parameters up in the Inspector:

- If the Inspector is already open: Simply choosing a clip or an effect brings its controls into view within the Inspector.
- If the Inspector is closed: Click on the Inspector tab.

NOTE: Across the top, the Inspector turns on different tabs that move you between separate pages of parameters. As an example, selecting a RAW photo activates the RAW tab. Choosing an ordinary post-debayered photo such as a .jpg switches the RAW section off. The effects tab likewise stays off by default until you apply an effect to a photo.

### Scopes

The Photo Page opens on the Histogram Scope, though any of the other scopes in DaVinci Resolve are available to you. For more about which scopes are available and the way each works, turn to Chapter 127, “Viewers, Monitoring, and Video Scopes,” located in the DaVinci Resolve Reference Manual.

### Histogram

- RGB/YRGB: Lets you switch between viewing only the RGB histograms or the RGB histograms together with the luminance (Y) channel.
- Gain: Drag the slider to boost or cut the histogram signal. This touches only the histogram, leaving the image untouched.
- Graticule: Drag the slider to lighten or darken the histogram scale.
- Show Reference Levels: Tick this box to place user-adjustable level lines onto the histogram.
- Low: Lets you set the brightness level of the low level line.
- High: Lets you set the brightness level of the high level line.
- Reset View: Resets the histogram to the default values.

### RAW

These controls let you work on the image through its pre-debayered RAW data settings. RAW editing stays nondestructive and is generally calibrated to your specific camera, which makes it the favored route for adjusting exposure and color. When your file is not a RAW format, this tab appears grayed out.

- Decode Quality: Debayers your RAW files at one of three resolutions — Full, Half, or Quarter — easing the burden on slower machines. Lower-resolution media looks worse but is quicker to handle and process. If needed, drop to a lower resolution that keeps real time playback smooth on limited hardware while you work, then move up to higher quality for the final render. Picking Project Settings ties the decode quality of every photo to the project settings.
- White Balance: The first choice keeps the white balance recorded in camera as shot. The remaining choices supply White Balance presets that set the Temperature and Tint parameters for you. They cover Daylight, Cloudy, Shade, Tungsten, Fluorescent, and Flash.
- Color Space: Lets you pick which color space the photo is edited and delivered in. With RAW settings it is usually wise to pick a color space from your camera’s maker, or one of the common video standards.
- Gamma: Lets you pick the gamma curve applied to the image — either one from your camera’s maker or a gamma matching a common video standard.
- Temperature: Tunes the white balance color temperature, meant to shift the “warmth” of the image. It is adjustable in degrees Kelvin. Lower readings compensate for “warmer” lighting, while higher readings compensate for “cool” lighting.
- Tint: Meant to shift the green-to-magenta balance of the image for shots with fluorescent tinting. Lower readings add green to offset magenta lighting, while higher readings add magenta to offset green lighting.
- Exposure: Raises or lowers the image’s brightness in units tied to ƒ-stops. Should your exposure change push image data past the maximum white level, no need to worry; every bit of image data survives and can be recovered in later adjustments. 0 is unity. The range is –5 to +5.
- Sharpness: A sharpness filter tied to the debayer that lends the image a look of greater detail. 10 is unity. The range is 0 to 100.
- Highlights: Makes it simple to win back blown-out highlight detail in high-dynamic-range media by lowering this control, blending the recovered highlights smoothly into the untouched midtones for a natural look. 0 is unity. The range is –100 (minimum) through +100 (maximum).
- Shadows: Lets you selectively brighten or darken shadow detail. Raising this value recovers shadow detail captured below 0 percent while leaving the midtones untouched. 0 is unity. The range is -100 (minimum) through +100 (very high).
- Color Boost: Lets you naturalistically lift saturation in areas that are low in saturation, an effect sometimes called vibrance. It can equally be used to drop saturation in such regions. Here unity sits at 0 while the available span runs from –100 (minimum) up to +100 (very high).
- Saturation: Tunes the color intensity of the image. Here unity sits at 0 while the available span runs from –100 (minimum) up to +100 (very high).
- Midtone Detail: Raising this control lifts the contrast in image regions rich in edge detail to heighten the sense of sharpness, an effect sometimes called definition. Pushing it to a negative value softens regions that hold little detail while leaving high-detail areas alone. Here unity sits at 0 while the available span runs from –100 (minimum) up to +100 (very high).
- Lift: Tunes the black point of the media, raising or lowering it while scaling every midtone value between it and the white point. However you set this control, all image data is preserved and can be recovered in later adjustments. The range is –100 to +100.
- Gain: Tunes the white point of the media, raising or lowering it while scaling every midtone value between it and the black point. However you set this control, all image data is preserved and can be recovered in later adjustments. 0 is unity. The range is –100 to +100.
- Contrast: Raising contrast deepens shadows and lifts highlights while keeping midtones at 50 percent unchanged. However you set this control, all image data is preserved and can be recovered in later adjustments. 0 is unity. The range is –100 to +100.

These controls let you tune the transform, cropping, color, and exposure of your image.

### Source Transform

- Zoom X/Y: Lets you enlarge the image or scale it down. The X and Y parameters can be locked together to hold the image’s aspect ratio, or unlocked to stretch or squeeze the image in a single direction.
- Position X/Y: Repositions the image inside the frame, allowing pan and scan moves. X slides the image left or right, while Y slides it up or down.
- Rotation Angle: Rotates the image around the center point.
- Pitch: Tips the image toward or away from the camera about an axis that runs through the

middle of the image, left to right. Positive values send the top away and pull the bottom forward. Negative values pull the top forward and send the bottom away. Larger values stretch the image more severely.

- Yaw: Tips the image toward or away from the camera about an axis that runs through the middle of the image, top to bottom. Positive values pull the left forward and send the right away. Negative values send the left away and pull the right forward. Larger values stretch the image more severely.
- Flip Image: Two buttons let you flip the image in different dimensions.
- Flip Horizontal control: Mirrors the picture across the X axis, swapping its left and right sides.
- Flip Vertical control: Mirrors the picture across the Y axis, flipping it top to bottom.

### Source Cropping

- Ratio: Lets you choose a width-to-height ratio for the image. Pick from the common still photo ratios, or leave it As Shot to keep your camera’s native ratio.
- Lock Aspect Ratio: Tick this box to hold the aspect ratio fixed across any of the cropping functions below. With it locked, cropping the image always moves the other cropping sliders to match the aspect ratio; with it unlocked, cropping changes the ratio.
- Crop Left/Right/Top/Bottom: Trims away each of the image’s four edges, measured in pixels.

### Looks

- Type: Lets you place preset look filters onto the photo. Pick one from the dropdown menu, or leave it on Default (Original) to skip the look filters.
- Intensity: Controls the strength at which the look filter blends into the picture.

### Adjustments

- Auto Balance: A single-button option that sets the parameters below automatically by way of machine learning.
- Temp: Lets you slide the image along a warm/orange to cool/blue axis matching the natural span of color temperatures used in lighting. Raising this control shifts the color balance toward orange, while pushing it negative shifts the color balance toward a blue/cyan.
- Tint: Lets you slide the image along a magenta-to-green axis matching the unnatural span of color temperatures from artificial lighting sources such as fluorescent and sodium vapor fixtures. Raising this control shifts the color balance toward magenta (often called “minus green” to fix fluorescent lighting), while pushing it negative shifts the color balance toward green (“plus green” to fix other kinds of lighting).
- Lift: Lets you change the perceived shadow density by moving the image’s black point. Dragging the Lift slider left darkens the darkest values, widening the gap between the image’s black and white points and stretching all the midtones in between. Dragging the Lift slider right lightens the darkest values, cutting contrast and squeezing all the midtones between the black and white points.
- Gamma: Lets you change the overall perceived brightness by reshuffling those midtones lying in between where the Lift and Gain master wheels are set. Push the Gamma master wheel toward the left and the whole image darkens; push it right and the image brightens.
- Gain: Lets you change the brightness of the highlights by moving the image’s white point. Dragging the Gain slider left darkens the lightest values, squeezing the midtones between the image’s white and black points. Dragging Gain right brightens the lightest values further, eventually clipping at maximum white.
- Contrast: The Contrast parameters let you swiftly narrow or widen image contrast about a userdefinable pivot point. This single parameter raises or lowers the gap between an image’s darkest and lightest values, increasing or decreasing image contrast.
- Pivot: Moves the tonal center about which the dark and bright parts of the image are stretched or pinched during a contrast adjustment. Darker images may need a lower Pivot value to avoid crushing the shadows too hard when contrast is stretched, while lighter images may gain from a higher Pivot value to build adequate shadow density.
- Midtone Details: Raising this control lifts the contrast in image regions rich in edge detail to heighten the sense of sharpness, an effect sometimes called definition. Pushing it to a negative value softens regions that hold little detail while leaving high-detail areas alone.
- Shadows: Lets you selectively brighten or darken shadow detail. Raising this value recovers shadow detail captured below 0 percent while leaving the midtones untouched.
- Highlights: Makes it simple to win back blown-out highlight detail in high-dynamic-range media by lowering this control, blending the recovered highlights smoothly into the untouched midtones for a natural look.
- Saturation: A consistent saturation move that, when set above 50 boosts — or below 50 cuts — the color intensity of each color value across the picture. At 50 it is unity and saturation stays as it was. Its span goes from 0 (completely desaturated) up through +100 (saturation is doubled).
- Hue: Spins every hue of the image right around the full circumference of the color wheel. With 50 as the default, the original spread of hues is kept. Nudging this value up or down sends all the hues forward or back along that hue spread as it would appear on a color wheel.

### Effects

When you have applied an effect from the Effects tab to your photo, its parameters can be tuned here. With no effect applied, this tab appears grayed out. NOTE: You will find full coverage of every effect within the Resolve FX portion of the DaVinci Resolve Reference Manual

### File

These settings present data about your file format and let you edit commonly used metadata fields.

### File Data

- File Name: The file name of the photo.
- Star Rating: Lets you grade the photo anywhere from one star up to five.
- ISO: Shows the ISO setting that the photo was shot with.
- Shutter Speed: Shows the shutter speed that the photo was shot with.
- Aperture: Shows the lens aperture that the photo was shot with.
- White Balance: Shows the current white balance setting from the RAW controls.
- Image Format: Shows the image file format.
- Resolution: Shows the source resolution of the image.
- Color Space: Shows the current Color Space setting from the RAW controls.

### Metadata

- Date Created: Adjust the date that the photo was taken.
- Camera: For sorting and organization, lets you record a camera name, letter, or number.
- Tag: For sorting and organization, lets you mark a photo Good, Untagged, or Rejected.
- Keywords: For sorting and organization, lets you attach keywords to the photo.
- Color: For sorting and organization, lets you give the photo a color code.
- Name: Lets you change the photo’s name as it appears in the media pool. Altering this name does

not change the original file name.

- Comments: Lets you add comments that are attached to the photo.
- Flags: For sorting and organization, lets you attach a color flag to the photo.
- Auto Select Next Photo: With this box ticked, hitting the return button after you finish a metadata field automatically selects the next photo in the Media Pool

and drops the cursor into that same field. This lets you race through metadata one photo after another without clicking to load each photo manually in the Media Pool.

- Next Photo: This button selects the next photo in the Media Pool no matter how the Auto Select Next Photo checkbox is set.

### Inspector Option Menu

- Reset Photo: (Command-R) Resets any adjustments made in the Photo tab.
- Remove All Photo Effects: (Shift-R) Strips off whatever effects you had placed onto the picture.
- Reset Camera Raw: Returns each RAW adjustment you made on the RAW tab to its default state.
- Remove and Reset All: (Shift-Command-R) Clears every applied effect and returns the image

to it’s original state.

### Adding LUTs to your Photos

Once you have installed a custom or ready-made look up table (LUT) into DaVinci Resolve, a LUT can be applied to any photo in the Media Pool or the Photo Album. Just right-click the photo’s thumbnail and pick the LUT from the LUT context menu.

### Exporting from the Deliver Page

You get finer control over exporting still photos from the Deliver page. Clicking Deliver while an Album is active opens a dedicated export view built for stills.

### The Deliver page in Photo Album mode

To export photos from the Deliver page:

- Select your File Naming, Location and Image Format in the Render Settings.
- Choose whether to send out the Entire Album, or just the Selected Photos drawn from the Album.
- Hit the Add to Render Queue button. Should you wish, tweak any of the export settings, then

press Add to Render Queue again to export multiple output formats.

- In the Render Queue press Render All to start processing your images.

### Render Settings

- File Name: Enter the base name for the rendered photo or photos. Pressing the + icon lets you add common metadata types to the file name, which fill in automatically per photo. By default the exported file takes this name plus a numbered suffix so every shot gets a unique file name.
- Location: The spot on disk where your photos should be written. Hit the Browse button to bring up a file system requestor and pick it.
- Export: Pick either Entire Album to export every photo in the album, or Selected Photos to export only the photos you have selected in the Album at the bottom of the Deliver page.

These settings let you set parameters for the exported photo format. Not every format carries all of these parameters.

- Format: Pick which photo format the export targets. The options on offer are: HEIF, JPEG, PNG and TIFF.
- Bit Depth: Choose the bit depth for the exported photo.
- Include Alpha Channel: When your format supports an alpha channel, tick this box to switch it on and

carry transparency information.

- Size: Choose the method by which you want to size your photo.

Original: With this approach the photo goes out at exactly it’s original dimensions. Width and Height: Here you type a precise width plus a precise height, both in pixels, for the export. Short Side: Here you give a precise pixel figure for the image’s short side (usually its height), and the long side is sized to match the aspect ratio on its own. Long Side: Here you give a precise pixel figure for the image’s long side (usually its length), and the short side is sized to match the aspect ratio on its own. Percentage: Here you set a percentage by which the image shrinks. The figures available go from 25% to 100%. Megapixels: Here you scale the image by a Megapixels figure instead. Enlarge: Tick this box whenever the resolution you are after exceeds the original resolution.

- Resolution: Type the image resolution you want right here, expressed either as Pixels per Inch (ppi) or as Pixels per Centimeter (ppcm).
- Compression: If your format supports image compression, enter your desired values here.
- Include Metadata: Tick this box to carry metadata such as location data, lens values, and the like into the

exported photo.

### File

These settings let you decide how the file naming of the exported photos is handled.

- File Name Uses: Pick either Custom Name to build your own naming structure, or Timeline name to take the timeline’s name plus a numerical suffix instead.
- Custom Name: Type text here to set the custom name; you can also fold in metadata variables that update per photo by first typing “%” and then picking the metadata field from the dropdown list.
- File Suffix: Type text here to tack on as a suffix following the custom name you set above.
- Use X Digits in the File Name: This number governs how many decimal places the file
