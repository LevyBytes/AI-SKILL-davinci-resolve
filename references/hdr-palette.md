# Hdr Palette (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### HDR Palette

The subject here is the overall and zone-driven tweaks available through the HDR palette, DaVinci’s most recent primary grading tool. Its name notwithstanding, you can rely on this palette — much as you would the Lift/Gamma/Gain mode of the Primaries palette — to build the base adjustment underneath any grade, whether SDR or HDR. That said, because it operates by zones, it carries the reach and precision associated with curve-based work, which leaves the HDR palette well-suited to a wide range of both creative and corrective jobs. On top of that, the palette’s awareness of color space, combined with the perceptually uniform space where its adjustments take place, positions it especially well for governing the saturation and highlights of images mastered in HDR.

### Introduction to the HDR Palette

Purpose-built for quick, adaptable primary grading of wide-latitude footage bound for either SDR or HDR delivery, the HDR palette is what it is. Being “color space aware” means it cooperates with Resolve Color Management, mapping the source image data into the palette’s own perceptually uniform operational color space according to that known transform. Sophisticated color processing under the hood then yields more economical color and contrast moves, plus perceptually uniform controls that let you treat every color across the spectrum evenly while keeping a tight grip on the image’s saturation.

### The HDR palette

On the right side of the palette sits a group of global controls for base adjustments to the whole image, joined at the bottom by Hue, Midtone Detail, Contrast/Pivot, and Black Offset controls. Beyond that, an overlapping bank of zone-specific controls handles color and contrast tweaks aimed at particular bands of image tonality. Taken together, the HDR palette supports primary grading work that stays photographically natural while reaching as broadly or as narrowly across the tonal range as you want, all with few unwanted artifacts. For all its depth, the palette relies on color balance and slider controls any colorist or editor who knows the more traditional Lift/Gamma/Gain controls will recognize. Seasoned grader or color newcomer alike, you’ll get strong results with less effort from the HDR palette once you’ve learned to wield it.

### The controls panel of the HDR palette

TIP: As HDR-capable media and HDR streaming delivery pipelines keep spreading, both the node HDR mode and the HDR palette ship with no restrictions in the free downloadable build of DaVinci Resolve.

### What Makes the HDR Palette Special?

Ahead of working through the specifics of the palette’s controls, it pays to grasp a little more about the way the HDR palette handles image data, since that context clarifies the benefits this tool brings to the table.

### Using the HDR Palette Without Color Management

Although the HDR palette was built to operate alongside color management, nothing stops you from using it in workflows that aren’t color managed, provided you configure it properly. Inside the HDR palette option menu you’ll find Color Space and Gamma submenus where you declare how you intend to work. Out of the box, each submenu defaults to “Timeline,” mirroring the color space you’ve elected to work in for display-referred workflows.

### Color Space Aware Controls When Using Color Management

Where the HDR palette truly excels is with Resolve Color Management or ACES turned on, since as a color space aware palette it exploits color management for all it’s worth. What color space awareness amounts to is this: the palette’s color and contrast controls adapt themselves to the span of each clip’s image data, mapped from the Input Color Space assigned to the source clip over to the Timeline Color Space in which your program lives. In day-to-day terms, that yields two advantages:

- Regardless of which kind of source clip you’re tweaking, and regardless of the timeline color space you’ve picked to work in, the HDR palette’s controls behave and feel essentially the same.
- Tweaks you apply through the HDR palette on one media type carry over to other media types with comparable results when copied. As a consequence, lining up shots and porting looks across media types becomes simpler than it was with earlier tools.

NOTE: Since the HDR palette is color space aware, you don’t have to switch on the HDR setting on nodes for the controls to behave intuitively when you’re working in a wide gamut Timeline Color Space, or outputting to an HDR format such as ST.2084. The palette handles all of that on your behalf, automatically.

### Perceptually Uniform Adjustments

On top of that, every clip’s image data gets translated out of the Timeline Color Space into an operational color space that the HDR palette employs; the image is adjusted there, then translated back into the Timeline Color Space, set for whatever operation comes next. That operational color space the HDR palette draws on is perceptually uniform, so the band of values tied to each visible hue spreads itself evenly across the whole space. The HDR palette grades standard dynamic range (SDR) material perfectly well, yet the color science beneath it also tackles problems that have long vexed colorists grading high dynamic range programs with conventional controls. Among those benefits:

- Because this palette computes all of its color transformations inside a perceptually uniform color space, your color adjustments gain finer, more photographically intuitive control. You might notice, for instance, that yellow hues grade more readily here, owing to a more balanced spread of hues around the rim of the color wheels.
- With the HDR palette you can change contrast and leave image saturation untouched; in contrast to the master wheels on the Lift, Gamma, and Gain panel, the HDR palette lets you push contrast up without driving saturation up, and pull contrast down without pulling saturation down. This proves especially handy when you’re lifting highlights

within HDR grades, because you can do it now without triggering runaway saturation in those highlights. In truth, any contrast move you make with these controls reshapes the image while holding saturation rock-steady (perceptually, that is; the Vectorscope will indeed reveal slight saturation shifts). Naturally, the saturation controls are the exception to this.

- Thanks to how tightly the HDR palette is woven into Resolve Color Management, matching shots and porting looks from one media type to another is also easier than with earlier tools. Pro or color beginner, you’ll see better outcomes with less hassle from the HDR palette.

### Superior Temp and Tint Controls

Owing to the HDR palette’s color space awareness, the Temperature and Tint moves in it rely on the very same XYZ to LMS color space transform that drives the Chromatic Adaptation Resolve FX plugin. What follows is that Temp adjustments come out photometrically accurate, producing visuals that resemble how human vision registers a scene shifting as the color temperature of the lighting changes.

### Customizable Zones

A further distinctive trait of the HDR palette is the degree to which you can tailor it to a broad spread of working styles, particular jobs, and individual colorist tastes. Flipping over to the Zones panel exposes an interface for tuning the Range and Falloff of every zone you’ve defined, via graphical controls laid over a histogram of the present image, while a curve illustrates to you how the contrast and color moves you’ve made mathematically influence the image’s RGB channels inside each zone. The default zones preset gives an efficient launching point for many scene types, yet because the tonal range of image data differs from scene to scene — daytime, nighttime, interior, or exterior — you’ll frequently need to customize these zones to wring the best out of adjustments made with these controls.

Through the Zones panel you can tailor the tonal ranges that each group of zone controls governs. On top of that, the sidebar to the left supplies controls for adding and deleting zones, letting users mold the palette to behave precisely as they prefer. You can save any custom preset for quick recall later. In this fashion, users get the latitude to work however suits them best. Meanwhile, the Option menu offers rapid access to other ways of customizing the palette’s behavior — picking and managing presets, choosing among methods for editing Color Balance adjustments numerically, and a setting that decides whether the Global controls stay permanently exposed or get banked to alongside the other zone controls.

### The HDR Palette Interface

Two panels make up the HDR palette. The first holds Color Balance controls and custom sliders and exists for color and contrast moves. The second holds the Zones sidebar and Zones graph and exists for tailoring the range and falloff of each zone tied to a given group of controls over on the controls panel. Those zones are precisely what you use to apply detailed image adjustments to tonally-specific regions of the picture. By default the two panels share the same palette area, and a pair of buttons at the upper right of the palette toggles between them. That comes in handy when screen space is tight, or your adjustments are straightforward. Otherwise, a single button click reveals both panels side-by-side, filling the left and middle palette areas of the Color page at once.

Going across from the left: the Side-by-side view button, then the Controls panel, the Zones panel, the Reset control, plus the Option menu. This Side-by-side mode makes it straightforward to view and tailor how each zone maps onto the source image data while you adjust simultaneously.

The HDR palette in Side-by-side mode; on the left, the Color/Exposure/ Saturation controls; on the right, the Zone Customization controls. An Option menu sitting at the far right of the title bar (rendered as three dots) brings up this palette’s preset manager, plus assorted GUI options for tailoring how you’d like to work with the palette.

### Navigating Multiple Zones in the Controls Panel

A strip of buttons directly beneath the HDR palette’s title bar indicates, out of all the zones on offer, which ones you can currently adjust with the controls visible below. The default HDR palette preset carries six zone-specific Zone controls along with the Global controls, but most users will find the GUI has room for only four sets of controls on screen at any moment. Grading control panel users, for their part, will be limited by however many trackballs their specific control panel offers.

### The Zone bank controls

Because you’ll nearly always have more zones on hand than you have space to adjust them, this interface reveals which zones you’re working with at the moment, which zones are mapped to a control panel, and which other zones you can swap to. By default, three active zones appear up top, matching the three sets of Zone controls positioned to the left of the Global controls. Zones that exist but are hidden show up in gray on the left and/or right of the zones currently visible, which appear in color. By this means, you can bank back and forth across three zones at once while keeping the Global controls always on hand for adjustment. The HDR palette’s Option menu also holds a setting, “Bank Global With Color Wheels,” that puts all four GUI control clusters in the palette to work showing Zones controls, speeding up how quickly you can hop between tonally-specific adjustments. Under that mode, four active zones appear up top, matching the four sets of Zone controls on display. In this mode, though, you have to page all the way over to the right to surface the Global controls, since they’re banked together with every other zone.

The Zone bank controls configured to display four zones when the Global controls are banked together with all the other zones. With these controls you can move your visible control across every available zone, much the way audio mixers shift between banks of tracks using a fader panel. Ways to switch between different Zone controls:

- Clicking any gray zone button sitting to the left of the zones now visible shifts all zones so that the leftmost visible zone lands on that one.
- Clicking any gray zone button sitting to the right of the zones now visible shifts all zones so that the rightmost visible zone lands on that one.
- Clicking the Left or Right Arrow buttons on either side of the zones indicators nudges all zones one step to the left or one step to the right.

### Making Global Adjustments

As a rule, when you’re leaning on the HDR palette for primary grading, the Global controls are where you’ll most likely want to start. Out of the box, they live at the right of the Controls panel.

The graphical Global control cluster, positioned at the right of the HDR palette. With these controls you take that first step of applying an overall adjustment to the image. For color, you’re given a color balance wheel, temp and tint sliders (flanking the wheel on the left and right, and numerically below it too), and saturation adjustments. For image contrast, a Global Exposure control lets you stretch overall image contrast upward to lighten the image, or squeeze it downward to darken it, relative to the present Black Offset level, which holds pixels at minimum black in place. At the bottom of the palette, a pair of Contrast/Pivot controls let you work overall color contrast by spreading highlights and shadows outward or inward relative to the pivot point, measured in stops. Global color adjustments bear some resemblance to the offset, temp, and tint controls in the Color Wheels or Log Wheels controls, yet there are meaningful differences, laid out in detail below. The Global Exposure control, by contrast, works in a very different fashion from Master Offset. A closer look at the Global controls:

- Global Color Balance: A color balance control that lets you shift the red, green, and blue channels together, more or less linearly through the image’s tonal range, to rebalance the color freely. That said, RCMv2 keeps a smooth saturation and exposure rolloff going automatically in the maximum highlights and minimum shadows, so the effect fades in the blackest blacks and the whitest whites of the image (the effect looks stronger in test gradients than in real world images). Adjustments via this control won’t push the darkest pixels in the image below the Black Offset level, though individual color channels can drop beneath that level to hold onto colorfulness within darker shadows. The color changes this control produces resemble the way optical color filters mounted over a lens would alter an image.

(Top) The original image, (Bottom) A Global Color Balance adjustment acting on the whole image, with a rolloff visible in the shadows and highlights of the superimposed ramp gradient

- Global Exposure: Lightens or darkens the whole image. Dragging rightward stretches image contrast by lifting the highlights while holding the shadows fixed relative to the Black Offset value. Dragging leftward reduces image contrast by lowering the highlights while holding the shadows fixed relative to the Black Offset value. For a fuller account of how Black Offset works, refer to the next section.

Bear in mind that every contrast move in the HDR palette holds saturation steady whether contrast rises or falls. The upshot is that, even with sizeable contrast moves on HDR images, the image’s saturation stays perceptually unchanged.

(Top) The original image, (Bottom) Raising Global Exposure

- Global Saturation: Boosts or cuts the intensity of color across the whole image. Because contrast moves leave saturation alone, any changes you want in image saturation you’ll have to make by hand.
- Global Color Balance Value Fields: Two numeric values capture how the color balance control’s center handle position is expressed. There are two numeric representations available: X and Y, or Angle and Strength. You pick whichever you like from the HDR palette’s Option menu; the method you select governs how the center handle of every color balance control behaves when you edit these values directly.

Down at the bottom of the HDR palette, you’ll find further Global Temp and Tint, Hue, Midtone Detail, and Contrast/ Pivot controls; these apply other sorts of global adjustments to the image’s color, detail, and contrast, in ways closely mirroring the same-named controls in the Color Wheels or Log Wheels controls. There’s also a Black Offset control for setting the lowest permitted black level in the current shot.

Global controls located at the bottom of the HDR palette. A closer look at the additional Global controls:

- Temp: This global temp adjustment warms or cools the image across a range running from -4000 to +4000 on a kelvin scale. The adjustment tracks the spectral locus line of the CIE graph, so the strength of the move stays naturalistic. To hold visual artifacts down, this control can warm the image more aggressively than it cools it.
- Tint: This global tint adjustment applies “plus green” or “minus green” shifts over a range from -100 to +100 on an arbitrary scale.
- Hue: Spins every hue in the image around the entire rim of the color wheel. At its default of 50 the original hue distribution is shown. Pushing this value up or down rotates all hues forward or backward along the hue distribution as it appears on a color wheel.
- Midtone Detail: Raising this parameter lifts the contrast of image regions carrying high edge detail, heightening the sense of image sharpness. People sometimes call this effect definition. Pushing the parameter into negative territory softens image regions with little detail, while leaving high-detail areas untouched. 0 is unity. The range runs –100 through +100.
- Contrast: This single parameter widens or narrows the gap between an image’s darkest and lightest values, raising or lowering image contrast. It behaves much like driving the Lift and Gain master controls in opposing directions at the same time. Bright and dark portions of the image are spread apart or drawn together about a center point set by the Pivot parameter. In contrast to the Contrast control in the Primaries palette, the HDR palette’s Contrast control disregards whatever the “Use S-curve for contrast” checkbox is set to, found within the General Options panel of the Project Settings.

Remember that all contrast moves in the HDR palette keep saturation fixed as contrast climbs or drops. So even with substantial contrast moves on HDR images, the image’s saturation looks perceptually identical to your eye, with tiny tweaks made to the image’s actual saturation to sustain that perception. Note that the tone mapping settings in RCMv2 will influence how much saturation survives in the topmost highlights and bottommost shadows of the image, as opposed to being rolled off automatically at the outer edges of the signal.

(Left) The original image, (Right) Raising Contrast; saturation holds perceptually constant, apart from the signal’s outer edges within the highest highlights and lowest shadows (subject to however your RCM tone mapping is configured).

- Pivot: Shifts the tonal center about which the image’s dark and bright portions get spread or pulled in during a contrast move. This lets you reshape how contrast falls across the shadows and highlights. At its default of 0, it lifts highlights above 50% gray higher and drops shadows below 50% gray lower, in equal measure to each other. Moving the pivot point alters the percentage of image tonality about which contrast gets expanded or compressed.

Darker images can call for a lower Pivot value to lift more levels upward and keep from crushing the shadows too hard when stretching image contrast, whereas lighter images may gain from a higher Pivot value to drive levels down and build shadow density.

(Top) Changing contrast by raising Pivot, which shifts most of the contrast expansion downward toward the shadows, (Bottom) Changing contrast by lowering Pivot, which shifts most of the contrast expansion upward toward the highlights

- Black Offset: Sets the darkest permitted part of the image. No move by any other control in the HDR palette will ever drop below this level, apart from the occasional color channel when the shadows grow extremely saturated. For fuller detail on this enormously important control, turn to the very next section.

### Black Offset Explained

Among all the Global controls, the Black Offset control ranks as one of the most quietly important. Black Offset lets you set the image’s darkest pixels. Moves applied to Black Offset don’t offset the whole signal; they touch only the very darkest stretch of the signal, letting you lift or lower the image’s black point while smoothly feathering the resulting move into the untouched part of the image. As a result, you’re able to squeeze or stretch the bottom of your signal. Lift Black Offset and you can introduce “flaring” to the image, akin to how light flaring inside a lens might brighten the image’s darkest area.

(Left) The original image, (Right) Raising Black Offset so as to add flaring to the image’s darkest pixels. As an alternative, you can drop Black Offset to lower the very darkest pixels in the image. When the source image is dark enough, this control can take the darkest pixels below 0, yet that image detail is retained within the color image processing pipeline. The key thing to grasp about this control is that whatever level you set Black Offset to becomes the new level at which Global exposure adjustments occur. In the example that follows, the first image presents the original color of a clip exposed dark. In the second image, Black Offset is tuned to lift the image’s darkest parts, compressing them relative to the midtones and lending the shadows a pleasing flaring effect.

(Left) The original image; (Right) Black Offset raised on that same image. Now look at the next image, where Global Exposure is lifted, and the Waveform scope reveals how the exposure change stretches the image’s contrast upward, with the darkest pixels “locked” to the Black Offset you defined.

(Left) Before, (Right) After raising Global Exposure to stretch image contrast outward from the Black Offset level; observe that the bottom of the signal keeps “touching” the same level once global exposure is lifted.

The Black Offset level you choose likewise becomes the minimum picture level whenever you bring exposure down, whether through Global Exposure changes or by way of the “darkening” zone controls — Shadow, Dark, and Black among them. The next image illustrates what happens when you lower Global Exposure; the image’s shadows compress more aggressively than the highlights as exposure drops, leaving the image’s minimum value parked at the Black Offset level you defined. While shadow detail stays impressively intact, this compression rolls off smoothly and nonlinearly through the midtones so the image keeps looking as natural as it can.

(Left) Before, (Right) After Global Exposure is dropped, squeezing image contrast downward until it reaches the Black Offset level; observe how the signal never dips below the Black Offset level. The same holds when you use other darkening zone exposure controls, like the Shadow control, which selectively drives the exposure of the image’s darker region down while leaving the highlights untouched. As you reduce Shadow exposure, the darkest pixels still compress such that nothing falls below the Black Offset level you defined. In short, you can tweak Black Offset whenever you like, before or after any other Global or Zone adjustment, to fine tune the image as needed.

### Making Zone-Based Adjustments
