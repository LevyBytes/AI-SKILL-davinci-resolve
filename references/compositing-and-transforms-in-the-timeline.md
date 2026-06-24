# Compositing And Transforms In The Timeline (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Compositing and Transforms in the Timeline

A great many of the compositing and transform effects in DaVinci Resolve live on the Edit page as well. Plenty of these effect types can be brought into DaVinci Resolve, among them composite modes, opacity settings, and clips that carry alpha channels. After they're inside DaVinci Resolve, the Edit page lets you adjust these effects. Or, if you prefer, DaVinci Resolve's own controls let you build effects from the ground up.

### Composite Modes and Transparency Effects

Composite modes are effects that combine one superimposed clip with another through assorted mathematical operations, leaning on standard image-processing math per color channel, where black pixels hold a value of 0, white pixels hold a value of 1, and the gradations of gray in between map to decimal values (so 0.5, for instance, stands for 50% gray). When composite modes blend a pair of clips on the Timeline, each pairing of pixels across the three color channels gets combined according to that particular composite mode's math. The outcomes can produce transparency effects, lift image exposure, and merge several images in many inventive and useful ways.

Two source clips combined with the Subtract composite mode When you work with composite modes, it's easy to drive portions of the resulting image past the maximum or under the minimum brightness values. That image data isn't clipped, though, even where such regions of the picture look like flat white or black. Out-of-range data produced by a composite mode effect is held onto and can be recovered by later image-processing operations on the Color page. As you import XML project files, DaVinci Resolve brings in whatever composite modes the clips in the original sequence used. Where needed, you can then swap a clip's composite mode for one that suits the grade you're building better. Naturally, you can also apply composite modes to clips that never had them, layering in fresh effects of your own. Every composite mode works together with the Opacity slider (sitting below the Composite Mode pop-up menu in the Inspector) to render a clip more or less transparent on top of whatever compositing is already happening. Composite modes can be applied to clips superimposed over other clips on the Timeline. They're available, however, within a grade on the Color page too, by way of the Layer Mixer node, where you can blend differently graded versions of an image in inventive ways. The Add and Overlay composite modes, for instance, can be handy for crafting glow effects, while Subtract and Difference can yield more surreal results.

Handling composite modes over on the Edit page is straightforward. To assign or swap a clip's composite mode: Pick a clip on the Timeline, open the Video Inspector, then choose an option out of the Composite Mode pop-up menu.

### Composite mode and Opacity controls in the Timeline

To turn a clip's composite mode off: Pick a clip on the Timeline, open the Inspector, then choose Normal out of the Composite Mode pop-up menu.

### More About Composite Modes

Ten composite modes are on offer. For clarity, plain image math is used here to explain the available Composite Mode effects.

### Normal

No image compositing happens. The whole frame is filled by either the Timeline's topmost image or, in the Layer Mixer node, its bottom input.

### Add

Each pairing of pixels across both superimposed layers is summed. Layer order doesn't matter. The result can be a striking brightening of light areas across both images, with picture regions blown out to maximum white; to build hot glow effects, this is often done by summing the brighter part of an image onto itself. Image data climbing above 1.0 is retained and can be recovered by later color correction operations. Conversely, black areas in either image leave the combined image untouched (0 + n = n).

### Color

Rebuilds two layers from HSL image components: the bottom layer's Luma is joined to the top layer's Hue and Saturation.

### Color Burn

The bottom layer is inverted, then divided by the top layer, and that result is itself inverted.

### Color Dodge

The bottom layer's pixels are divided by the top layer, which has been inverted.

### Darken

Each pairing of pixels in every color channel is compared, and the darker of the two becomes the output. Layer order doesn't matter. Darken serves you well when you want the darker features of both layers to win out, though for any particular pixel the output might come out as a color found in neither source layer at that pixel.

### Darker Color

For each pairing of pixels, all three color channels from the bottom layer are summed, and all three color channels from the top layer are summed. Those results are compared, and the darker pixel of the two layers becomes the output. Layer order doesn't matter. Darker Color serves you well when you want the darker features of both layers to win out. Unlike the Darken composite mode, the result is always a specific color drawn from either the bottom or top layer.

### Difference

The absolute value of the top layer minus the bottom layer is taken and returned as the result, always a positive number. Layer order doesn't matter. People often reach for this Blend mode to set two differently processed versions of a single image side by side, checking for any alterations and judging how big they are.

### Divide

Takes the bottom layer and divides it by the top layer. A color over itself yields = 1.0, that is white, whereas a color over white (1.0) yields = itself.

### Exclusion

Much like the Difference composite mode, but it yields lower contrast.

### Hard Mix

The bottom layer's R, G, and B channel values get summed with those same R, G, and B channel values from the top layer. Layer order doesn't matter. Can yield extreme effects.

### Hardlight

Hardlight is Overlay's opposite. Every bottom layer pixel above 50% is Multiplied, while every bottom layer pixel at 50% and below is Screened.

### Hue

Rebuilds two layers from HSL image components: the bottom layer's Luma and Saturation are joined to the top layer's Hue.

### Lighten

Each pairing of pixels in every color channel is compared, and the lighter of the two becomes the output. Layer order doesn't matter. Lighten serves you well when you want the lightest features of both layers to win out, though for any particular pixel the output might come out as a color found in neither source layer at that pixel.

### Lighter Color

For each pairing of pixels, all three color channels from the bottom layer are summed, and all three color channels from the top layer are summed. Those results are compared, and the lighter pixel of the two layers becomes the output. Layer order doesn't matter. Lighten Color serves you well when you want the lighter features of both layers to win out. Unlike the Lighten composite mode, the result is always a specific color drawn from either the bottom or top layer.

### Linear Burn

Each pairing of pixels is summed, then 1 is subtracted from the total. Layer order doesn't matter. White regions in one layer let the other layer through; meanwhile, the colors and darker tones drawn from both layers play off one another to tint or darken the result.

### Linear Dodge

Each pairing of pixels is summed. This composite mode is identical to Add.

### Linear Light

Every region where the bottom layer sits above 50% is Linear Dodged so as to lighten those parts of the final result, while every region where the bottom layer falls below 50% is Linear Burned so as to darken those parts of the final result. This composite mode heightens image contrast in the final result.

### Luminosity

Rebuilds two layers from HSL image components: the bottom layer's Hue and Saturation are joined to the top layer's Luma.

### Multiply

Each pairing of pixels is multiplied. Layer order doesn't matter. Generally this has the effect of stressing the darkest parts of both images in the resulting output; black areas of either image in particular are retained (0 _ n = 0), while white areas of either image leave the output image unchanged (1 _ n = n). Multiply is good for compositing darker elements set in a field of white into an image, and when you blend in a noise, grain, or damage layer it can emphasize that layer's darkest regions.

### Overlay

Overlay marries useful aspects of both the Screen and Multiply composite modes, keyed to the pixel values of the bottom-most image on the Timeline; every bottom layer pixel above 50% is Screened, while every bottom layer pixel at 50% and below is Multiplied. Overlay is an excellent composite mode for marrying a layer of noise, grain, or damage imagery with another clip, since it combines both images in visually useful ways across the tonal range from shadows through highlights.

### Pin Light

Wherever bottom layer pixels sit under 50% gray, the bottom layer's darker pixels take over the top layer's lighter ones, while in the top layer darker pixels stand in for the bottom layer's lighter pixels, so the final image's darker half draws darker pixels out of both layers. Wherever bottom layer pixels go over 50% gray, the bottom layer's lighter pixels take over the top layer's darker ones, while in the top layer lighter pixels stand in for the bottom layer's darker pixels, so the final image's brighter half draws lighter pixels out of both layers.

### Saturation

Rebuilds two layers from HSL image components: the bottom layer's Luma and Hue are joined to the top layer's Saturation.

### Screen

Each layer's pixel values are first inverted, multiplied together, and then that product is inverted once more. Layer order doesn't matter. Screen is Multiply's inverse, since it keeps the lightest parts of both images, and it's useful when compositing lighter elements set in a field of black into an image; blend in a noise, grain, or damage layer and it can emphasize that layer's lightest regions.

### Softlight

A gentler way of applying the Hardlight composite mode that lands on a more even blend between the two layers.

### Subtract

For every pixel pairing, the top layer's value has the bottom layer's value taken away from it. This can yield dark areas of the image that bottom out at flat black, but image data dropping below 0 is retained and can be recovered by later color correction operations.

### Vivid Light

Every region where the bottom layer sits above 50% is Color Dodged so as to lighten those parts of the final result, while every region where the bottom layer falls below 50% is Color Burned so as to darken those parts of the final result. For an extreme effect, this composite mode pushes the final result's image contrast and its saturation up dramatically.

### Foreground

When the Foreground composite mode is put on the top layer, the transparency of its pixels is governed by a bottom layer set to one of the composite modes below: Alpha The Alpha composite mode set on the bottom layer governs the transparency of the top layer in a Foreground mode. The layer's alpha is what's used.

### Inverted Alpha

Set the Inverted Alpha composite mode on the bottom layer and it governs how transparent the Foreground-mode top layer becomes. This time, though, it rests on the inverted alpha of the bottom layer.

### Lum

When the Lum mode is set on the bottom layer, it alters the transparency of the top layer in a Foreground mode. The pixels' luminosity value is what decides this.

### Inverted Lum

Set the Inverted Lum mode on the bottom layer and it alters how transparent the Foreground-mode top layer becomes. This rests on the inverted luminosity value of the pixels.

### Unknown

As you import XML or AAF project files carrying composite modes that DaVinci Resolve doesn't offer, the Composite Mode pop-up menu is set to Unknown; in practice, this matches Normal. TIP: For a fast preview of the various composite modes, rest your pointer on any mode within the Composite Mode drop-down list, and that mode previews right in the viewer.

### Opacity

Every clip carries an Opacity parameter, found in the Inspector, that lets you make it more transparent, across a range from 0 (totally transparent) to 100 (totally opaque). Set below 100, the chosen clip blends with whatever clip lies under it on the Timeline, following the composite mode in use at the time. Should no clip appear under the Timeline, the clip blends with black instead. By keyframing this parameter you can craft more elaborate fade-to-black effects or cross dissolves. There's fuller coverage of keyframing in Chapter 53, "Keyframing Effects in the Edit Page." Here's how to change a clip's opacity: Pick the clip you mean to adjust, open the Composite controls within the Video Inspector, and dial the Opacity slider to whatever degree of transparency you're after.

### Video Fader Handles

Dissolving a clip to or from another clip, or to or from black, has traditionally meant reaching for one of the transitions in the Effects Library. As an alternative, though, you can rely on fader handles that surface at a clip's start and finish once the pointer rests right over it. Fader handles offer a quick, everywhere-available route to a fade leading to or from black. They also, however, make fading to or from other clips beneath a superimposed one easy, as the following screenshot shows.

Dragging a video fader handle on a clip in track V2

Putting a fader handle to use means resting the pointer over whichever clip you'd like to adjust; once small white fader handles surface at the top left and top right of that clip's video, drag them left or right for as long as you want the fade to last.

### Fade In and Out to Playhead Commands

Within the Trim menu sit two commands that draw on where the playhead lands over a clip, letting you "Fade In to Playhead" or "Fade Out to Playhead." It works on a single clip or on several superimposed clips. These commands hold for both audio and video items, across the Edit and Fairlight pages alike.

### Alpha Channel Support

Where a superimposed video or still image clip on the Timeline carries an embedded alpha channel, that alpha channel automatically introduces transparency within the clip, compositing it against whatever sits in the track beneath. You don't need to do a thing for this to work.

Place a clip carrying an alpha channel above another and that clip is automatically composited over the one underneath. However, should you need to disable or change how an alpha channel is interpreted for any clip—say, where a clip is read as carrying the wrong type of alpha channel—right-click on that clip, pick Clip Attributes off the contextual menu, and turn to the Alpha Mode pop-up menu on the Clip Attributes Video panel to put it right. NOTE: When you've imported clips that carry alpha channels, you can render those channels back out again to support Round Trip workflows. Pick a Format and Codec pairing that handles alpha channel output, and switch on the Export Alpha checkbox over in the Video panel of the Render Settings list.

### Keying in the Timeline Using Resolve FX

The Resolve FX Key filters let keys be pulled straight in the Timeline. Look for them inside the Resolve FX section of the Open FX category, over in the Effects Library. Three filter options exist: the 3D Keyer, the HSL Keyer, plus the Luma Keyer. To read more on putting the Resolve FX Key filters to use, see Chapter 159, "Resolve FX Key." The Resolve FX 3D Keyer filter at work in the Timeline serves as the example below.

### Setting Up a Green Screen (Chroma Key) on the Timeline

For a green screen composite, set your background video on a track under your foreground video, then drag the 3D Keyer onto the foreground clip. To tune the key's parameters, click the Effects icon over in the Inspector so the Keyer's controls show, then pick "Open FX Overlay" from the Transform Mode drop-down menu down at the lower left of the Timeline Viewer, which lets the effect qualifiers act on the Timeline Viewer.

Putting the 3D Keyer onto the News Anchor clip on the V2 Timeline; observe that the Viewer's "Open FX Overlay" mode is on (circled), so the Inspector Effect controls become usable in the Viewer. Here's how to pull a Chroma Key in the Timeline with the 3D Keyer. 1 Stack your green screened foreground video on a track above your background video. 2 Switch the Timeline Viewer into Open FX Overlay mode by way of the drop-down menu down at the lower left of the Viewer. With this option, the effect GUI controls become usable straight on the Viewer.

3 Drag the 3D Keyer out of the Effects Library and onto the foreground video. A fast, high-quality keyer that's easy to use, the 3D Keyer has you draw strokes that mark out the image's background and foreground as you try to key it. 4 Pick the foreground video clip, then open the 3D Keyer from the Effects tab over in the Inspector. 5 Click the Pick eye dropper icon within the Controls section, then, across the green screen over in the Timeline Viewer, click and drag. A blue line marks where you've selected, and most of the green screen should go transparent. 6 Optional) With the Add eye dropper (drawing blue lines), click and drag over whatever stretches of the green screen remain opaque. With the Subtract eye dropper (drawing red lines), restore any foreground elements that turned transparent by mistake. 7 Switch on the Despill checkbox within the 3D Keyer to clear any green light (spill) that may have bounced onto your foreground subject off the green screen.

### Using Resolve FX and Open FX Alpha for Track Compositing

For compositing on the Timeline, DaVinci Resolve lets you draw directly on the alpha channel that comes from Resolve FX and Open FX plugins. Where an effect introduces transparency into the image, a "Use alpha" checkbox surfaces at the foot of the effect parameters within the Effects tab of the Inspector. Tick this box and the alpha channel applies to the chosen clip at once, compositing it over whatever background elements show up in lower tracks. Should a single clip carry more than one alpha-modifying effect, their alpha channels get blended together.

The Use Alpha checkbox sitting at the foot of the Inspector's Effects tab

### Transform and Cropping in the Video Inspector

DaVinci Resolve is a resolution-independent application. What that means is that no matter what resolution your source media holds, output can happen at whatever other resolution you choose. It also means clips of any resolution can be mixed freely, with 4K, HD, and SD clips dropped into one timeline and each scaled to suit the project resolution as needed. Since your project's resolution is changeable at any moment, you can work at one resolution and output at a different one. That likewise makes it simple to put out several versions of a program at varying resolutions—say, both an HD and a 4K sized version of the same program. For geometric transforms, DaVinci Resolve carries a powerful toolset that leans on advanced algorithms for optical-quality sizing operations. Over on the Edit page, each clip owns a set of transform parameters, used mainly to hold sizing data brought in from AAF or XML once the "Use sizing information" checkbox is on. The upside is that these imported Edit Transform settings stay apart from the Input Sizing parameters on the Color page, the ones a colorist usually reaches for to make pan and scan adjustments of various sorts.

Naturally, these controls also serve for your own tweaks as you work in the Timeline—zooming into clips, nudging them to sharpen the composition, and so on. Though these parameters overlap a bit with those in the Color page's sizing palette, the two stay distinct sets, so each batch of adjustments can be kept apart. Come output time, each clip's final resolution is worked out by weighing several things: the source media's original resolution, then the timeline resolution, the image scaling settings, plus both the Edit page transforms and the Color page transforms—so that final resolution puts the cleanest geometric transformation to use, drawn from the highest resolution each source clip can offer.

### Transform

These are the parameters gathered in the Video Inspector transform group; all of them are likewise editable in the Edit Sizing mode of the Sizing palette on the Color page:

- Zoom X and Y: Enlarges the image or scales it down. Link the X and Y parameters to lock the image's aspect ratio, or unlink them to stretch or squeeze it along a single direction.
- Position X and Y: Repositions the image inside the frame for pan and scan adjustments. X slides the image left or right; Y slides it up or down.
- Rotation Angle: Spins the image about the anchor point.
- Anchor Point X and Y: Defines the clip coordinate that every transform centers on.
- Pitch: Tilts the image toward or away from the camera about an axis that runs through the

image center, left to right. Positive values send the image's top backward and draw its bottom forward. Negative values draw the top forward while sending the bottom back. Larger values stretch the image to a greater extreme.

- Yaw: Tilts the image toward or away from the camera about an axis that runs through the image center from top to bottom. Positive values draw the image's left side forward and send its right side back. Negative values send the left side back and bring the right side forward. Larger values stretch the image to a greater extreme.
- Flip Image: A pair of buttons lets you flip the image across different dimensions. Flip Horizontal control: Mirrors the image along the X axis, left to right. Flip Vertical control: Mirrors the clip along the Y axis, flipping it upside down.

### Smart Reframe (Studio Version Only)

With the Smart Reframe feature, reframing material across drastic aspect ratio changes goes faster. It earns its keep when, for instance, a clip shot as 16:9 horizontal video has to become a vertically oriented 9:16 cut bound for mobile phones and social media deliverables, or when 4:3 archival footage lands inside a 2.39:1 widescreen movie. You can run Smart Reframe by hand, or let the DaVinci Resolve Neural Engine carry it out automatically.

- Object of Interest: Tools that pick the subject the resize frames around. Auto: Here DaVinci Resolve's Neural Engine studies the clip and settles on its most representative object. It's the sole option once more than a single clip is selected for Smart Reframing. Reference Point: Lets you hand-adjust a bounding box around the subject you want to reframe around.
- Mode: Tools for confining the AI reframing to a specific axis. Auto: Smart Reframe will adjust a clip's pan and tilt as it sees fit to properly reframe the target. Pan Only: Smart Reframe will adjust only the pan (left and right) motion of the clip. Tilt Only: Smart Reframe will adjust only the tilt (up and down) motion of the clip.
- Reframe: This button runs the Smart Reframe command. It can take a while depending on the length and number of clips.

### EDIT 1084

### Cropping

The Video Inspector carries an additional set of cropping parameters:

- Crop Left, Right, Top, and Bottom: Trims the image's four sides by a chosen number of pixels. Because cropping a clip introduces transparency, whatever lies beneath becomes visible through it.
- Softness: Blurs a crop's edges. A negative value softens the edges within the crop box, whereas a positive value softens the edges beyond the crop box.

### Dynamic Zoom
