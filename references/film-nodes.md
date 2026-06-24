# Film Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Film Nodes

This portion of the manual covers Fusion's Film nodes.

Each node's shortened abbreviation, shown beside its name, works in the Select Tool dialog while hunting for a tool and also turns up in scripting references. Throughout these pages, treat any node tree that depicts MediaIn nodes inside DaVinci Resolve as equivalent to Loader nodes within Fusion Studio, except where a note says differently.

### Cineon Log [Log]

### The Cineon Log node

### Cineon Log Node Introduction

Use the Cineon Log node to translate a variety of log camera encodings into linear gamma, as well as the reverse trip. Despite a name that suggests Cineon material, this tool also copes with “log” gamma sourced from numerous digital cinema cameras, including those made by Blackmagic Design, Arri, and Red.

### Input

The Cineon Log node carries a pair of Inputs: one accepts the log image, the other receives the effects mask. Input: Feed the primary 2D image that receives the highlight into the orange input. Effect Mask: Into the blue input goes a mask shape, which may come from polylines, simple primitive shapes, paint strokes, or bitmaps produced elsewhere. Wiring a mask here keeps the log conversion confined to whatever pixels the mask covers. The tool runs its own processing first, after which the effects mask takes effect.

### Basic Node Setup

Position the Cineon Log node immediately downstream of a MediaIn node when in DaVinci Resolve, or of a Loader node when in Fusion Studio. A frequent second use is ahead of a MediaOut or Saver node, where it reverses the conversion to yield a Logencoded image.

### Inspector

A Cineon Log node sitting downstream of a Fusion Studio Loader node

### Cineon Log controls

### Controls Tab

Within the Controls tab live the options that move log gamma toward linear, or run the trip the other way from linear into log. Begin by picking the Mode, followed by the Log Type. As an example, pick Log to Lin in the Mode menu, then set the Log Type to BMD Film when your composite uses a RAW clip captured on a Blackmagic Design camera. That combination yields a linear image that is ready to composite.

### Depth

Through the Depth menu you choose which color depth governs how the incoming image is processed. Its factory setting is Auto, which reads the loaded file format and picks a depth accordingly. JPEG files, for instance, default to 8 bit, since that format will not hold color depths beyond 8. By contrast, Blackmagic RAW files arrive at Float, and so on. Whenever a format's depth cannot be worked out, Fusion falls back on the depth set in the Frame Format preferences.

### Mode

Two choices sit in the Mode menu: one path turns log images into linear, while the other takes linear images into logarithmic.

### Log Type

Use the Log Type menu to indicate where the file originated. Most of the time that means naming the camera that shot the image, though the Josh Pines entry exists for film scan pipelines. The camera log types offered by this menu are listed below:

- Cineon
- Arri Log C
- BMD Film
- Canon Log
- Nikon N Log
- Panalog
- Panasonic V-Log
- Red Log Film
- Sony S-Log
- Viper Film Stream
- ACESlog

Lock RGB With this turned on, whatever you set in the tab is applied identically to every color channel. Switch it off when you want to treat the image's red, green, and blue channels separately, each with its own settings. Level This range control lets you fix where the black level and the white level fall in the log image ahead of conversion. Drag the left handle to move the black level and the right handle to move the white level. After conversion, any pixel whose log-space value lies under the black level drops into out-of-range territory below 0.0, while any pixel above the white level climbs to out-of-range values past 1.0. A floating-point color space keeps both the negative and the elevated out-of-range values intact; switch to 16-bit or 8-bit mode and those out-of-range values get clipped instead. Soft Clip (Knee) Reach for the Soft Clip control when you want to pull out-of-range values back into the picture. It works by easing the conversion curve at its upper and lower ends, which makes room for additional values to be expressed. Set the soft clip to anything besides 1 and the node switches to 16-bit integer processing, discarding every out-of-range value that won't sit inside the soft clip.

Film Stock Gamma, Conversion Gamma, and Conversion Table Together these controls shape the response curves applied to the logarithmic data as it converts. Beyond the controls already covered, you may build a custom ASCII file Lookup Table (LUT) holding your own conversion values, then bring that ASCII LUT file in by clicking the Browse button.

### Common Controls

Settings Tab Because every Film node shares the same Settings tab controls, you will find them documented together under the “The Common Controls” heading that closes this chapter.

### Black Rolloff

A mathematical log() applied to zero or a negative number yields garbage, so to stay correct Fusion snaps anything under 1e-38 (a 0 trailed by 38 zeros) down to 0. In practice this rarely matters, because numbers that minuscule leave no mark on a picture. Glimpsing values that faint would require stacking three Brightness Contrast nodes, each one gained up to 1,000,000, and even that would leave them barely off zero. Some pipelines, rather than discarding these tiny numbers, choose to rescale them: values sitting between 0.0 and 1e-16 get remapped into the 1e-18 to 1e-16 band. The goal is to compress nearly the whole visible range of a float image down toward zero and then stretch it back out, producing a soft ramp through the deepest blacks. If you ever inherit a color pipeline built on this trick, you can reproduce it with a Custom node as follows. First convert the log image to linear using a tiny gamma along with an unusually broad black-to-white spread (for instance, conversion gamma of 0.6, black of 10, white of 1010), which squeezes most of the image’s range into very small numbers. Next comes a Custom node (covered just below), and after that a linear-to-log conversion that undoes the earlier step while applying a marginally higher black level. That gap between the two black levels sets the falloff range. Because this raises the blacks, you normally finish by converting once more to linear with the usual figures (i.e., 95-685) to re-establish the black point. Inside the Custom node, enter this equation into each of the red, green, and blue expressions: if (c1< 1e-16, 1e-18 + (c1/1e-16)\*(1e-16 - 1e-18), c1)

### Falloff Comparison

### The black falloff from the native Fusion process

A nearly indistinguishable black falloff produced by the ramped clipping technique

### Film Grain [FGr]

### The Film Grain node

### Film Grain Node Introduction

The Film Grain node lays synthesized film grain over an image. A common workflow, when a composite mixes film-shot and digital elements, is to strip the grain away during the compositing work and then add it back onto the finished composite. Doing so sells the illusion that every element was captured in one take on a shared film stock. NOTE: While it is the more precise tool, the Film Grain node is not a drop-in replacement for the legacy Grain node, which stays available so older compositions can still load and render; even so, the Film Grain node is the better pick in nearly every situation.

### Input

Two inputs sit on the Film Grain node: one takes the image and one takes the effects mask. Input: Route the primary 2D image that should receive grain into the orange input. Effect Mask: The blue input expects a mask shape, drawn from polylines, plain primitive shapes, paint strokes, or bitmaps brought over from other tools. Hooking a mask here keeps the grain inside only the pixels the mask spans. Note that the tool finishes its processing before the effects mask is layered on.

### Basic Node Setup

You will usually drop the Film Grain node ahead of a MediaOut node in DaVinci Resolve, or ahead of a Saver node in Fusion Studio. Because source footage frequently has its grain stripped for cleaner keys and compositing, reintroducing film grain just before output makes the final composite read as more believable.

### Film Grain node adding grain back before output

### Inspector

### Film Grain controls

### Controls Tab

Every parameter that shapes how the film grain looks lives in the Controls tab. Complexity The Complexity value sets how many grain “layers” are stacked onto the image. At a complexity of 1, the node figures and applies a lone grain layer. Raise complexity to 4 and it works out four independent grain layers, then blends their averaged result into the final image. Pushing complexity higher yields richer-looking output that avoids the obvious repetition you can often spot in grain generated digitally. Alpha Multiply Turning on the Alpha Multiply checkbox makes the Film Grain node scale its output by the Alpha channel of the source image. You need this for post-multiplied images, so that grain stays clear of any region where the Alpha equals 0.0 (transparent). NOTE: Because there is no way to know a semitransparent pixel's final value until it has been merged with its background, hold off on applying log-processed grain to those elements until the compositing is done. That timing keeps the grain's strength correct. Log Processing With this checkbox on (the default), the grain's intensity is mapped onto the image nonlinearly so it tracks the grain signature of typical film. Put simply, grain intensity climbs exponentially as you move from black up to white. Switch the checkbox off and the grain lands evenly, no matter how bright the pixel underneath happens to be. A defining trait of real film grain is that its look shifts dramatically with exposure: the blacks carry almost no grain, while both the quantity and the spread of grain grow as a pixel's exposure rises. Within a film negative, the image's deepest shadows read as fully opaque, hiding the grain there; as the negative grows clearer, more of the grain surfaces in the outcome. Chemical differences

in how the R, G, B, layers each react to light give every color component of the film its own grain signature, and ordinarily the blue channel shows the heaviest grain. For that reason, the Log Processing checkbox is one of the Film Grain node's key controls: leave it on when you are matching film, and turn it off for images that call for a more linear grain response. With it switched on, the result closely echoes what you would get by placing a Linear to Log conversion before the old Grain node and a Log to Linear conversion right after it. Seed Any Fusion node whose output depends on randomness exposes a Seed slider together with a Reseed button. Feed two nodes matching seed values and they yield identical random results. Press the Reseed button to draw a fresh seed at random, or move the slider to dial one in by hand. Time Lock Switching on Time Lock prevents the random seed from spawning fresh grain frame after frame. Monochrome While the Monochrome checkbox is on (the default), grain hits the image's red, green, and blue channels in equal measure. Clear it and you gain per-channel command over the grain's Size, Strength, and Roughness. Lock Size X/Y Clear the Lock Size X/Y checkbox so you can size the grain independently along the X- and Y-axis. Size Grain size is measured against a single pixel's size, which means altering the image resolution leaves the grain's relative look untouched. At the default grain size of 1.0, each grain kernel spans about 2 pixels. Strength Grain shows up as a departure from a pixel's original color, and the greater the grain's strength, the larger that possible swing away from the starting pixel value. Take a pixel whose original value is p run through a Grain node where complexity = 1 size = 1; roughness = 0; log processing = off; the output works out to p +/- strength. Put differently, a pixel valued at 0.5 paired with a grain strength of 0.02 might land anywhere from 0.48 to 0.52. As before, that simplifies things a bit, all the more so once complexity climbs past 1. Switching on the Log Processing checkbox additionally reshapes that swing so the blacks vary less and the whites vary more. NOTE: To picture how grain acts on an image, the more mathematically minded might imagine a sine wave in which each lobe spans 1 pixel while the Grain Size sits at 1.0. The Grain Size then governs that sine wave's frequency and the Grain Strength its amplitude. This too is a bit of a simplification. Roughness Dragging the Roughness slider introduces low-frequency variation, suggesting that the grain clumps together. Set roughness to 0 and you will see the grain hold a very uniform luminance variation right across the image. Crank roughness up to 1.0 and notice the “cellular” unevenness appear in that luminance variation.

Offset Use the Offset control to align grain intensity down in the deep blacks; it shifts the values first, and only then is the grain's intensity (strength) worked out. With an offset of 0.1, for example, a pixel sitting at 0.1 picks up grain as though it were really at 0.2.

### Common Controls

Settings Tab The same Settings tab controls turn up on all Film nodes; for that reason their write-ups sit together in the chapter-ending “The Common Controls” section.

### Processing Examples

### Log Processing On

Out of the box, the blacks and the whites of the image each pick up their own distinct amounts of Grain Log Processing Off

With Log processing switched off, the Grain spreads uniformly over the whole image, just as pictured here

### Grain [Grn]

### The Grain node

### Grain Node Introduction

Compared with the newer, more faithful Film Grain node, the Grain node gives you a legacy approach to emulating film grain. It remains in the toolset purely so that older compositions can keep loading and rendering, yet for nearly any task the Film Grain node is the wiser choice.

### Input

The Grain node exposes two Inputs, one meant for the 2D image and one for the effects mask. Input: Send the primary 2D image that is to be grained into the orange input. Effect Mask: A mask shape feeds the blue input, and you can build that shape from polylines, ordinary primitive shapes, paint strokes, or bitmaps carried over from other tools. Attaching a mask at this point confines the grain to just the mask's pixels. The tool processes itself first, and the effects mask is then applied afterward.

### Basic Node Setup

Typically the Grain node goes ahead of a MediaOut node within DaVinci Resolve, or ahead of a Saver node within Fusion Studio. Its job is to restore grain that was taken out earlier in the composite.

A Grain node reinstating grain for a more believable composite Inspector

### Grain controls

### Controls Tab

All the settings that govern the grain's look are gathered in the Controls tab. Power This slider sets how strong the grain is; raising it makes the grain more visible and pronounced. RGB Difference Independent Red, Green, and Blue sliders let you tune the effect's strength channel by channel. Grain Softness This slider governs how blurry or fuzzy the grain reads, with lower values rendering it sharper and coarser. Grain Size This slider sets how large the grain particles are, and bigger numbers enlarge the grain. Grain Spacing This slider sets the grain's density, or how much grain falls in a given area; raise it and the grain looks more spread apart. Aspect Ratio This slider tweaks the grain's aspect so it can line up with anamorphic images. Alpha-Multiply Tick this checkbox to multiply the image by the Alpha, wiping any grain effect out of the black regions.

### Grain Spread controls

### Spread Tab

By means of separate curves for the red, green, and blue channels, the Spread tab regulates how much grain appears across each channel's tonal range. RGB Checkboxes Ticking the red, green, and blue checkboxes switches on each channel's own curve, giving you control over the grain level in that channel. Following typical film behavior, the blue channel would carry more grain than the red, and the green channel the least of all. A right-click inside the spline area brings up a contextual menu whose options relate to editing spline curves.

If you want fuller detail on the LUT Editor’s controls, turn to Chapter 107, “LUT Nodes,” within the DaVinci Resolve Reference Manual, or to Chapter 47 of the Fusion Reference Manual. In and Out With this control you edit curve points directly by entering their In/Out point values.

### Examples

Default Spread Left at its default, the grain falls uniformly over the whole image, just as pictured here. Real film, though, frequently carries differing grain amounts through the blacks, mids, and whites. Bell-Shaped Spread A bell curve usually makes a solid jumping-off point for grain that looks more lifelike. What you see here is an uneven distribution with the grain set to different levels in the red, green, and blue channels. Across both of these examples, the grain's power has been pushed higher than normal so the effect reads more clearly.

### Common Controls

### Setting Tab

Since the Settings tab controls show up the same way on every Film node, you will find each one explained in the chapter's closing “The Common Controls” section.

### Light Trim [LT]

### The Light Trim node

### Light Trim Node Introduction

What this node reproduces is the light trims of a film scanner. It is built to perform best on logarithmic data, the kind held in Cineon, Arri, or Blackmagic RAW files. Hand the Light Trim node logarithmic data and you can use it to raise or lower the image's apparent exposure level.

### Inputs

You get two Inputs here: the Light Trim node devotes one to the 2D image while reserving the other for the effects mask. Input: Feed the primary Log 2D image whose exposure needs tweaking into the orange input. Effect Mask: A mask shape goes into the blue input, built from polylines, simple primitive shapes, paint strokes, or bitmaps imported from other tools. Wiring a mask here holds the exposure change to only the pixels under the mask. As usual, the tool runs its processing before the effects mask is applied.

### Basic Node Setup

Set the Light Trim node downstream of a LOG clip, yet upstream of wherever a Cineon LOG node converts that Log clip.

A Light Trim node tuning the exposure of a LOG clip

### Inspector

### Light Trim controls

### Controls Tab

A lone slider in the Controls tab handles the image's exposure. Lock RGBA Enabling the Lock RGBA control folds every image channel under a single slider; it ships turned on. Clear this checkbox whenever you need to drive the individual color channels on their own. Trim This slider moves the color in terms of film, optical printing, and lab printing points, where 8 points equals one stop of exposure.

### Common Controls

Settings Tab Every Film node carries the same Settings tab controls, which is why a single description of them lives in the “The Common Controls” section wrapping up this chapter.

### Remove Noise [RN]

### The Remove Noise node

### Remove Noise Node Introduction

For straightforward noise control, reach for the Remove Noise node. Under the hood it blurs the image channels and then weighs that blurred version against the original to isolate the noise. Afterward it sharpens the image everywhere except the spots where noise turned up. In practice, display the image and study the red channel, then push Red Softness up until the grain looks gone. Now raise the sharpness until detail returns, halting just before the grain creeps back. Carry out the same steps for the green and blue channels.

### Inputs

A pair of inputs sits on the Remove Noise node, one handling the 2D image and one handling the effects mask. Input: The orange input receives the primary 2D image that is to have its noise stripped. Effect Mask: Into the blue input goes a mask shape, made from polylines, basic primitive shapes, paint strokes, or bitmaps drawn from other tools. Connecting a mask there pins the noise-removal change to nothing beyond the mask's pixels. The effects mask kicks in only once the tool itself has finished processing.

### Basic Node Setup

Any noisy clip is fair game for the Remove Noise node. In the example below, for instance, it clears noise ahead of keying the clip with the DeltaKeyer.

A Remove Noise node clearing noise ahead of a keying pass Inspector

### Remove Noise controls

### Controls Tab

From the Controls tab you flip the noise removal between its two methods, Color and Chroma. Pick Color and the Controls tab lets you tune blur and sharpness separately on each RGB channel. Pick Chroma and blur and sharpness are governed instead through the Luma and Chroma controls. Method This menu decides whether the node handles color via the Color method or the Chroma method, and your pick also swaps in a different set of control sliders.

Lock Ticking this checkbox ties each channel's Softness and Detail sliders to one another. Softness Red, Green, and Blue These Softness sliders fix how much blur each channel of the image receives; switch to Chroma mode and they turn into softness sliders for the Luminance channel and the Chrominance channel. Detail Red, Green, and Blue These Sharpness sliders fix how much detail is restored to a channel after it has been softened, and under Chroma mode they become a Luminance slider and a Chrominance slider.

### Chroma Method controls

### Common Controls

Settings Tab Across all Film nodes the Settings tab controls stay the same, so you will read about them in the “The Common Controls” section that comes next.

### The Common Controls

A set of matching Inspector controls is shared across the Film nodes, and this section walks through those controls the Film nodes hold in common.

### Inspector

### The Common Film settings inspector

### Settings Tab

Every tool in the Film category carries the Inspector's Settings tab, and you will even meet these Settings controls on third-party Film-type plugin tools. They behave identically from one tool to the next, though a handful of tools add one or two unique options, which are documented here as well. Blend Turn to the Blend control to mix the tool's untouched image input against its final, altered output image. At a blend value of 0.0, what leaves the tool matches what entered it, and as a rule the tool then bypasses processing altogether, passing the input straight through to the output. Process When Blend Is 0.0 With this on, the tool still processes even though the input value reads zero. That comes in handy when a script ties this node's processing to firing off another task while the node's own value sits at 0.0.
