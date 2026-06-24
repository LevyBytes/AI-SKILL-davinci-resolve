# Matte Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

To view the matte, switch the viewer over to the alpha channel.

- Tuning Ranges: Paints a false color across the image's Shadow, Midtone, and Highlight ranges. The red channel carries Shadows, the green channel carries Midtones, and the blue channel carries Highlights.
- Status: Surfaces detail marking which regions are solid, transparent, or somewhere between. It likewise reveals zones touched by matte tweaks like thresholding or erode/dilate, plus zones the solid mask reached.
- Intermediate Result: The original source image color channels merged with the finished matte. If you like, feed this output into further Delta Keyer nodes.
- Final Result: The completed keyed image, spill-suppressed and set to merge onto a scene.

### The Delta Keyer Key tab

### Key Tab

Keying typically kicks off on the Key tab, whose job is picking out the screen color. Background Color This refers to the hue of the blue or green screen, occasionally known as the screen color. With the Delta Keyer, build the key by grabbing the screen color out of the image using the background color Eyedropper. Pre-Blur Lays down a blur ahead of alpha generation. That can ease certain noise, edge enhancements, and artifacts present in the source image. Gain Boosting Gain strengthens the screen color's pull, pushing those regions toward greater transparency. Balance A color difference keyer such as the Delta Keyer weighs the gap between the leading channel (set by the chosen background color) against the remaining pair of channels. Tweaking balance sets how those other two channels are proportioned. At 0 it takes the minimum of the other two, at 1 the maximum, and at 0.5 an even split of each.

Lock Alpha/Spill Removal Color Balance Reference Unlock this and you can feed different color references into alpha generation versus how much background color gets pulled out of the image. Left enabled, spill and color are treated as one. Color Balance Reference These Color balance reference controls compensate for lighting or white balance that may be sapping the background color's purity and saturation. Drawing on the reference of a neutral-colored object, a correction kicks in while the key is built and the amount of background color subtraction is gauged, all without changing the background color that gets subtracted.

### The Delta Keyer Pre Matte tab

### Pre Matte Tab

You can think of the Pre Matte tab as a garbage matte keyer running ahead of the delta keyer stage. Its role is smoothing out the screen color before the finer key happens. Having picked the first screen color, jump to the Pre Matte tab and choose PreMatte Out from the view mode menu atop the Inspector. Because Pre Matte deals in color ranges, begin by dragging a bounding box over regions whose lighting differs from that first screen color pick. Widen the selection with Soft range and trim its edges with Erode. With a more uniform screen selection in hand, head to the Matte tab. Soft Range Soft Range broadens both the span of selected color and the screen color's rolloff. Erode Erode pulls in the pre matte's edge so the edge detail avoids clipping.

Blur This eases the pre matte's edges. Pre Matte Range These readouts refresh on their own to mirror whatever color is currently selected. They nudge the selection a little, though all you really need to do is pick colors in the viewer. Lock Color Picking Turning on this checkbox stops the chosen range from creeping wider when you grab additional colors from the view. Switching it on once you've settled on the matte color is wise. Every other control on the node stays editable. Reset Pre Matte Ranges Pressing this clears the entire color selection by resetting the ranges, yet leaves all the remaining slider and control values intact.

### The Delta Keyer Matte tab

### Matte Tab

The Matte tab polishes the key's alpha, folding in whatever solid and garbage masks are wired into the node. As you work here, flip the viewer over to the Delta Keyer's final-output alpha channel. Threshold This range slider fixes the lower threshold with the left handle and the upper threshold with the right handle. Anything sitting under the lower threshold turns black or transparent in the matte. Anything above the upper threshold turns white or opaque. Values caught between the two keep their relative transparency. Restore Fringe This rebuilds the matte's edge around the keyed subject. Keying frequently clips the subject's edge wherever hair appears, and Restore Fringe recovers that edge while the matte stays solid.

Erode/Dilate Grows or shrinks the matte. Blur Eases the matte. Clean Foreground Fills the matte's faintly transparent (light gray) zones. Clean Background Clips off the matte's lower dark range. Replace Mode Sets how matte tweaks put color back into the image.

- None: Color stays put. Matte processing leaves the color alone.
- Source: The hue taken from the original image.
- Hard Color: One flat color.
- Soft Color: A flat color scaled by how much background color got stripped out initially.

Replace Color The hue applied by the Hard Color and Soft Color replace modes.

### The Delta Keyer Fringe tab

### Fringe Tab

Within the Delta Keyer, the Fringe tab takes care of most spill suppression. Spill suppression is a kind of color correction aimed at pulling the screen color off the matte's fringe. Spill itself is the screen color bleeding through the alpha channel's semitransparent regions. With blue- or green-screen keying, that typically leaves the background hue showing along the foreground subject's edges.

Spill Method This picks how aggressive the algorithm is when it applies spill suppression to the image.

- None: Pick None whenever no spill suppression is called for.
- Rare: Strips out hardly any spill color, the gentlest option of the bunch.
- Medium: Suits green screens best.
- Well Done: Suits blue screens best.
- Burnt: Suits blue screens best. Reserve this mode for the most stubborn shots only.

Spill Suppression Hold this slider at 0 and the image gets no spill suppression at all. Raising it dials up how strongly the spill method acts. Fringe Gamma Reach for this control to brighten or darken the fringe or halo ringing the keyed image. Fringe Size This grows or shrinks how big the fringe or halo around the keyed image is. Fringe Shape Fringe Shape shoves the fringe out toward the image's outer edge or draws it inward toward the fringe's inner edge. You'll notice it most when the Fringe Size value runs large. Cyan/Red, Magenta/Green, and Yellow/Blue These three controls let you color-correct the image's fringe. They come in handy for nudging semitransparent pixels that still hold the old background's color so they match the new background.

### The Delta Keyer Tuning tab

### Tuning Tab

An advanced panel, the Tuning tab lets you set how large the shadow, midtone, and highlight ranges are. Reshaping those ranges lets you tie the strength of the matte and spill suppression to tonal values.

Range Controls These range controls spell out how much color counts as belonging to the image's shadows, midtones, and highlights. The spline controls make it simple to reshape the tonal span of each Shadow and Highlight tonal map. Simple/Smooth Press Simple and the range turns linear. Press Smooth and the ranges take on a gentle tonal gradient. Lock Alpha/Spill Removal Tuning Turn this checkbox off and distinct tuning controls govern alpha generation versus how much background color gets subtracted from the image.

- Shadows: Tunes the key's strength across the background's darker regions.
- Midtones: Tunes the key's strength across the background's midtone regions.
- Highlights: Tunes the key's strength across the background's brighter regions.

### The Delta Keyer Mask tab

### Mask Tab

On the Mask tab you decide how the solid and garbage mattes get folded into the key. Solid Source Alpha Serves to blend the source image's existing alpha together with the solid mask.

- Ignore: Leaves the source image's alpha out of the blend.
- Add: Wherever the source image alpha is solid, the solid mask becomes solid too.
- Subtract: Wherever the source image alpha is transparent, the solid mask becomes transparent too.

Solid Replace Mode Here you set how the solid mask puts color back into the image.

- None: Nothing gets recolored. Color stays untouched by the solid mask.
- Source: The hue lifted straight from the original image.
- Hard Color: A single flat color.
- Soft Color: A flat color scaled by the amount of background color that was stripped away to begin with.

Solid Replace Color The hue used by the Hard Color and Soft Color replace modes.

- Invert: Flips the solid mask before it merges with the source alpha.

### Garbage Mask

- Invert: By default, a garbage mask's solid regions cut the image out. Flip it, and instead the mask's transparent regions cut the image out.

### Common Controls

Settings Tab You'll find the Inspector's Settings tab mirrored across the other matte nodes as well. Full descriptions of these shared controls sit at this chapter's close, under "The Common Controls."

### Depth Map [DMp]

### The Depth Map node

### Depth Map Node Introduction

Depth Map builds an Alpha channel from how far away the objects in your clip appear to sit. Once you can single out a particular depth band, the range of ways to work on the resulting image grows enormously. Pair it with a Blur node, say, and you can fake a depth of field look that only touches the far background of the shot. A foreground element such as a person could be lifted with extra contrast, saturation, and sharpness, much as a qualifier would. A Depth Map can also patch up video problems: think of correcting a color temperature issue by singling out a distant window shot in daylight that has tinted the background actors blue, all while sparing the foreground subject lit by studio lighting. That resulting Depth Map Alpha channel reads as a black-and-white image, where white marks whatever the changes reach and black marks whatever is left alone.

### Inputs

Within the Node Editor, the Depth Map node carries two inputs. Input: That yellow input takes a 2D image holding the shot you want examined for depth. Effect Mask: The optional blue input looks for a mask shape drawn from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here confines which pixels the difference matte covers. The tool gets the effects mask only once its own processing has finished.

### Basic Node Setup

The Depth Map's purpose is to pull in an image source and forge an Alpha channel keyed to how far things appear from the camera, then pass that Alpha along to nodes further down the chain. The example that follows uses the Depth Map to single out the image's background and grade only that background, leaving the foreground actors untouched as they cross the frame.

An example Depth Map node layout that singles out subjects by how far they sit from the camera Inspector

### The Depth Map Controls tab

### Controls Tab

Every parameter for dialing in the quality of the finished matte lives on the Depth Map's Controls tab.

- Mode: Depth Map leans hard on computation. Its quality setting offers a Faster mode that keeps responses to your tweaks snappy, whereas the default Better mode delivers top quality and is best switched on once you've stopped adjusting.
- Depth Map Preview: This box starts out checked, showing the present Depth Map so you can make tweaks. Uncheck it and the resulting Alpha becomes available for grading over on other nodes.
- Invert: Tick this and the Depth Map flips, trading its transparent and opaque regions.

Resulting Map Adjustment Use these controls to dictate how the Depth Map's contrast gets tuned.

- Adjust Map Levels: Left off (the default), all scaling is suspended so you can work the Depth Map's full range. Switch it on and the option pins the Depth Map's levels to 0 and 1. That previews what becomes of the Depth Map once it serves as an Alpha channel, where the values are forever clamped to 0 and 1. Ticking this box also lights up the tools beneath it.
- Far Limit: This one tunes the Depth Map's black levels.
- Near Limit: This one tunes the Depth Map's white levels.
- Gamma: This one shifts the in-between depth values brighter or darker relative to

the fixed black and white levels. Isolate Specific Depth With these controls you can travel forward and back through the scene by depth, picking out one depth band to adjust.

- Isolation: This checkbox flips the depth isolation tools on or off.
- Target Depth: This picks the exact depth to single out. 1 lands fully in the foreground, whereas

0 lands fully in the background.

- Tolerance: Fixes how far on each side of the Target Depth gets folded into the Depth Map.
- Softness: This eases a gentle ramp-in and ramp-out at the edges of the chosen band for a more

natural selection. Map Finesse These controls reshape the finished Depth Map's Alpha channel so it suits grading.

- Post Processing: This toggles the Map Finesse tools on or off.
- Post-Filter: This blends the map onto the image's smooth zones and edges. Its job is to

keep later grading effects from visibly drifting within the region.

- Contract/Expand: This dilates or erodes the whole shape along its edges, handy for fine

tuning where the map's affected and unaffected regions meet.

- Blur: This eases the map's boundary so it folds more seamlessly into the

resulting image.

### Common Controls

Settings Tab This Inspector Settings tab shows up again on the other Matte nodes too. The shared controls it holds are spelled out fully where the chapter ends, in the "The Common Controls" section.

### Difference Keyer [DFK]

### The Difference Keyer node

### Difference Keyer Node Introduction

Difference keying works by deriving a matte from the gap between two images. It draws on a pair of inputs: one that shows the subject sitting in front of the background, and one that shows the background by itself. Plausible as that sounds up front, small shifts in camera placement between the two shots normally make clean results hard to achieve. Picture the hopeless task of keying smoke against a brick wall while handing it a clean plate of that same brick wall as the difference input. Some of the wall's texture never quite disappears with this approach. So a Difference Keyer tends instead to deliver a rough matte that you marry to other nodes for a finer one.

### Inputs

Over in the Node Editor, the Difference Keyer node offers four inputs. Background: This orange background input takes a 2D image showing the set alone, minus your subject. Foreground: The green foreground input takes a 2D image of the shot with your subject present in the frame. Garbage Matte: The gray garbage matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask here and the image regions inside that matte turn transparent. Solid Matte: The white solid matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask here and the image regions inside that matte turn fully opaque. Effect Mask: The optional blue input looks for a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask here to pin down which pixels the difference matte covers. That effects mask reaches the tool only after the tool has finished processing.

### Basic Node Setup

Lacking footage shot against a blue or green screen, you can slot the Difference Keyer in as one link among many in a chain that lifts an object off its background. In the example here, MediaIn1 supplies the main subject and a clean background plate without the subject fills the Background. A B-Spline reins in the area the Difference Keyer has to wrestle with during extraction. What comes out is a matte that assists the key without fully cracking it.

A Difference Keyer fed two inputs: one showing the subject over a background, the other showing that background by itself Inspector

### The Difference Keyer Controls tab

### Controls Tab

Every parameter for tuning the matte's quality sits on the Difference Keyer's Controls tab. Threshold This range slider pins the lower threshold with the left handle and the upper threshold with the right. Moving them carves out a span of difference values between the two images from which the matte is built. A difference under the lower threshold goes black or transparent in the matte. A difference over the upper threshold goes white or opaque. The difference values that fall between yield a grayscale matte.

Filter This picks which filtering algorithm runs when a blur is laid onto the matte.

- Box: The quickest approach, though quality drops. Box fits best where blur is kept small.
- Bartlett: Also called a Pyramid filter, Bartlett strikes a sound balance of speed against quality.
- Multi-box: Choosing this brings up the Num Passes slider so you can steer the quality. With 1 and 2 passes you match Box and Bartlett in turn. From 4 passes upward, the output usually rivals Gaussian, faster and free of edge "ringing."
- Gaussian: Built on a genuine Gaussian approximation, the Gaussian filter yields superb output, albeit a touch slower than the rest. Now and then it leaves an exceedingly faint edge "ringing" on floating-point pixels.

Blur This softens the matte's edge with whatever method the Filter menu has chosen. Set it to zero and you get a crisp, cutout-style hard edge. Push it higher for more blur. Clipping Mode This setting governs how edges behave during domain of definition rendering. It matters greatly when you blur the matte, since that may pull samples from parts of the image beyond the current domain.

- Frame: Frame, the default, automatically hands the node's domain of definition the image's whole frame, in effect disregarding the current domain of definition. Should the upstream DoD fall short of the frame, the leftover frame area counts as black/transparent.
- Domain: Switch to Domain and the node honors the upstream domain of definition as its effect runs. That can clip badly wherever the node reaches for a large filter.
- None: Choose None and no source image clipping happens whatsoever. Consequently, any data the node's effect needs that would normally lie beyond the upstream DoD counts as black/transparent.

Contract/Expand This slider trims or swells the matte's semitransparent zones. Above 0.0 it expands the matte; below 0.0 it pulls it in. You'll usually pair it with the blur to soften a matte's hard edge and cut fringing. Because it touches only semitransparent zones, it leaves a matte's hard edge alone. Gamma Matte Gamma pushes the matte's values up or down across the semitransparent zones. Larger values make the gray areas more opaque; smaller ones make them more transparent. Fully black or white parts of the matte stay put. Invert Tick this checkbox to flip the matte, turning every transparent area opaque and every opaque area transparent.

Solid Matte A Solid Matte is any mask node or image fed to the node's solid matte input. It lands directly on the image's alpha channel. Typically a solid matte shields keying wherever you need things kept opaque, say a blue-eyed person standing against a blue screen. Turn on Invert and the solid matte is flipped ahead of its merge with the source alpha. Garbage Matte A Garbage Matte is any mask node or image fed to the node's garbage matte input. It too lands directly on the image's alpha channel. Typically a garbage matte clears away stray elements no key can handle, microphones and booms among them. It can likewise fill spots that carry the keyed color but which you mean to hold onto. Within a single tool, garbage mattes of unlike modes won't mix. A frequent move is placing a Matte Control node downstream of a Keyer node so it adds a garbage matte that counters the matte handed to the keyer. Turn on Invert and the garbage matte is flipped ahead of its merge with the source alpha. Post-Multiply Image Pick this so the keyer multiplies the image's color channels by the alpha channel it makes for that image. It tends to be enabled and ships on by default. Uncheck it and, for merging with other images, the image no longer reads as premultiplied. There, lean on the Merge node's Subtractive option in place of the Additive one. To dig into these Merge node settings, consult the DaVinci Resolve Reference Manual at Chapter 95, "Composite Nodes," or, equivalently, the Fusion Reference Manual at Chapter 35.

### Common Controls

Settings Tab The same Settings tab in the Inspector appears on the remaining Matte nodes as well. Detailed coverage of these common controls lives at the tail end of this chapter, within "The Common Controls."

### Luma Keyer [LKy]

### The Luma Keyer node

### Luma Keyer Node Introduction

The Luma Keyer node forges an Alpha channel out of an image's overall luminance. Its name can mislead a bit, given that it can pull mattes from nearly any channel. By one measure it's truer to think of this node as a general-purpose channel keyer, yet its chief role remains extracting alpha channels from luminance

### Inputs

Inside the Node Editor, the Luma Keyer node carries four inputs. Input: This orange input takes a 2D image holding the luminance values you want keyed for transparency. Garbage Matte: The gray garbage matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask here and the image regions inside that matte turn transparent. That garbage matte goes straight onto the image's alpha channel. Solid Matte: The white solid matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask here and the image regions inside that matte turn fully opaque. Effect Mask: The optional blue input looks for a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask here to confine which pixels the luminance key touches. That effects mask reaches the tool only after the tool has finished processing.

### Basic Node Setup

The Luma Keyer pulls a key from an image whose luminance varies markedly. From there, the Luma Keyer's output can route into any mask input you like.

A Luma Keyer output wired into a Merge node's effect mask Inspector

### The Luma Keyer Controls tab

### Controls Tab
