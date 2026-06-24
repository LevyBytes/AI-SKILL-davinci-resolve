# Primaries Palette (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Bars mode's principal controls are the separate Luma (or Y), Red, Green, and Blue sliders, with four of each spanning Lift, Gamma, and Gain. Through these sliders you get exact Lift/Gamma/Gain-style command over every one of the image's YRGB channels. Paired with a Parade Scope video analysis of the picture, they let you correct lopsided color imbalances in particular channels in a hurry. On top of that, the Luma (Y) Lift/Gamma/Gain sliders make Y-only contrast tweaks simple, where pushing contrast up reads perceptually as reduced color saturation. They line up with the trio of knobs stacked vertically just left of the Trackball panel on the DaVinci Advanced control panel, or with the three leftmost knobs on the DaVinci Micro or Mini control panels. Y-only contrast tweaks are a fine path to more contrast when you're chasing muted saturation or a gritty feel. The same tweak also helps wherever you want to deepen shadow density while leaving the image's colorfulness alone.

### Log Wheels Mode

The Shadow/Midtone/Highlight color balance and Master Wheel controls run on their own, separate from the Lift/Gamma/Gain color balance and Master Wheel controls of the Primaries mode. Although the Log mode draws on the same kinds of controls as the Primaries mode, how each control acts on the picture differs sharply. To switch between the Primaries and Log modes of the Wheels: Pick an option off the mode drop-down, click the right mode button, or hit Option-Z.

Log color balance controls, behaving quite differently from the Wheels mode color balance controls You can put the Log mode controls to use in two ways. The first leans on how these controls behave to apply quick, filmic tweaks to log-encoded media before it gets normalized or “de-logged” by operations running on nodes that sit later in your node tree's image processing pipeline. Normalizing or de-logging the picture is achievable through Color Space Transform operations, LUTs, and manual tweaks when you grade with DaVinci YRGB color science. With color management on, you reach it through the Output Color Space setting under Resolve Color Management (RCM), or by means of the ACES Output Device Transform (ODT). For the second way of wielding the Log controls, you draw on the Shadow/Midtone/Highlight controls and their tighter (though still adjustable) tonal range to stylize normalized clips, tinting or shifting the contrast of tonally specific zones of the picture. Whether or Not to Use Legacy Log Grading Ranges and Curve A change arrived in DaVinci Resolve 12.5 affecting the Log grading controls, one that yields smoother, nicer results out of the same controls. To keep things compatible with projects from before, the General Options panel of the Project Settings holds a “Use legacy Log grading ranges and curve” checkbox that flips your project between the old Log control behavior and the new one. Older projects opened in DaVinci Resolve arrive with this checkbox switched on by default, whereas new projects arrive with it switched off by default.

### Using the Log Mode Controls to Grade Log-Encoded Media

The Log controls carry that name because they're purpose-built for media using Log-C or comparable gamma and color encoding, traced back to the Cineon Log gamma curve, which Kodak created to digitally hold flat-contrast, wide-gamut image data that keeps image detail intact alongside a broad margin for adjustment.

An example of a log-encoded clip (left) beside that same clip once normalized (right) Most raw formats can be debayered to a log-encoded image so as to pull the greatest possible amount of image data and adjustable margin out of the source. For more information, see Chapter 7, “Camera Raw Settings.” Even so, the picture that results has to be normalized so it fills the final color and contrast range you have in mind for the finished result. There are two routes to doing this:

- One route is a meticulous curves tweak on a second node that stretches the log-encoded image out to match the contrast profile you're after. Putting this tweak on Node 2, you leave room for a styling tweak via the Log controls on Node 1, ahead of the normalization tweak. That's the crux.
- The other route applies a 1D Output or 3D LUT to a clip's first node to normalize the picture. This runs faster, though it bends less, but a smooth tonal range may come more readily. Because a LUT applied inside a node always lands as the final adjustment in that node's order of operations, you can likewise lean on Node 1's Log controls to style the look of the footage.

Either route demands that the normalizing tweak follow your Log control tweaks, so the Log control tweaks do their job properly. With the node tree arranged like this, you'll watch a normal-looking picture while still drawing on the distinctive tonal ranges of the Log mode controls to work the log-encoded image data with fine specificity. TIP: Inside corrector nodes, LUTs land after Log control tweaks, so to keep your node tree's node count low, you can drop a normalizing (or de-logging) LUT onto the very node where you make your Log tweaks, secure that the LUT lands properly after the log tweaks.

For more information, see Chapter 144, “Image Processing Order of Operations.”

As you get a feel for the Log mode controls, here's a workflow worth weighing:

- To start, reach for the Offset master wheel to fix the black point, and lean on the Contrast and Pivot parameters to stretch or squeeze contrast however much it takes to reach the tonal range you want.
- Next, turn to the Offset color balance control to set the picture's overall color balance to your taste.
- Finally, work the Shadow/Midtone/Highlight color balance and Master Wheel controls for pinpoint tweaks to the picture's color and contrast in tonal ranges matching where that data falls in the log-encoded image.

Going about it this way, you'll notice that tweaks via the Offset color balance and Master Wheel controls plus the Contrast controls steer the log-encoded image quite cleanly for an overall adjustment, while the Shadow, Midtone, and Highlight controls let you mend particular trouble spots, like shadow balance and density, once your main adjustment is in place. The illustration below sketches roughly how the default ranges of the Shadow, Midtone, and Highlight controls carve up the tonal range of a log-encoded image.

This graphic sketches the tonal range of each Log control as used on a log-encoded image As the picture shows, on a log-encoded image the color interactions across each adjustment blend together very gently, yet still permit finer tweaks than the Lift/Gamma/Gain controls deliver. Beyond that, the edges of the Shadows, Midtones, and Highlights Log controls can be reshaped with the Low and High Range parameters. That hands you extra latitude to make finer contrast and color tweaks. After you've made an adjustment with the Log mode controls alongside a normalizing LUT or curve adjustment, you're free to stack on more nodes and switch to the Wheels mode of the Primaries palette to keep reworking the now-normalized picture, going about it just as you would with any of DaVinci Resolve's other tools. TIP: Inside the order of operations that governs image processing on any single node, the Wheels mode's Lift/Gamma/Gain adjustments come before the Log mode's Shadow/Midtone/Highlight/Offset adjustments, so to run Log mode controls before Wheels mode controls, you'll need to apply Wheels controls on a node added afterward. For more information, see Chapter 144, “Image Processing Order of Operations.”

### Using the Log Mode Controls to Stylize Normalized Media

The Log mode controls work on already-normalized images too. The outcome differs somewhat, yet this can be a quick route to eye-catching stylizations. Where subtle tweaks come with great ease thanks to the widely overlapping tonal ranges belonging to the Lift, Gamma, and Gain color balance controls, the color balance controls of the Log palette strike far tighter tonal zones that overlap a good deal less on normalized images. The illustration below sketches roughly how the Shadows, Midtones, and Highlights split the image's tonal range, by default, into non-overlapping thirds. As the prior section showed, these splits were first meant to map onto log-encoded media. With normalized media, though, these splits hand you a different, and potentially handy, set of ranges apart from the Primaries mode controls.

### Shadows

### Midtones

### Highlights

### Low Range

### High Range

This graphic sketches roughly the tonal range of each Log control, with the extra low and high range that stretches or shrinks the range. On normalized media, the Shadows genuinely touch only the deepest shadows, tapering off around the lower third of image tonality. The Midtones touch only the central third of grays, and the Highlights touch the brightest upper third of image values. These default spans of image tonality can, however, be reshaped with the Low Range and High Range controls, covered in greater depth later on. The image below shows how extreme corrections applied to a grayscale image with the Log mode controls interact by default. The Shadows have been driven toward green, the Midtones toward blue, and the Highlights toward red.

Severe tweaks that reveal how the Shadow, Midtone, and Highlight color balance controls overlap one another

As the picture shows, on normalized media the color interaction across each adjustment stays very subtle. The deepest shadows come out bright green, the midtone values vivid blue, and the highlights nearly pure red. That tightness pays off when you want a correction held to one particular tonal range inside the picture without resorting to a Luma qualifier. It's equally handy for bold, stylistic color tweaks as you build a look that isn't naturalistic. TIP: Within the Log controls, the Highlights adjustment can also prove extremely handy for lifting or otherwise reining in the highlights of HDR grades. That said, the several highlight zones of the HDR palette grant a far greater degree of command over this sort of adjustment, through similar control panel-friendly controls.

### Adjusting the Default Tone Ranges in Log Mode

Once you're in Log mode, two more parameters turn up in the top shared controls bar, letting you reshape how much Shadows and Highlights image tonality each Color Balance control reaches, which in turn tightens or loosens the range of Midtones. Bear in mind that the ranges accept customization, yet the degree of overlap between each range does not. Low Range: Shifts the boundary where the Shadows and Midtones come together. Dropping this parameter broadens the span the Midtones reach and tightens the span the Shadows reach. Lifting this parameter tightens the Midtones and broadens the Shadows. High Range: Shifts the boundary where the Midtones and Highlights come together. Dropping the High Range parameter tightens the span the Midtones reach and broadens the span the Highlights reach. Lifting this parameter tightens the Highlights and broadens the Midtones. There are also Saturation and Hue parameters that echo these same settings found across other palettes and modes.

### Adjusting Contrast in Log Mode

While you work with the Log mode controls, the main tools you'll lean on for image contrast tend to be the Offset master wheel along with the Contrast and Pivot parameters. With these three controls you can fix a black point and dial in the overall contrast in short order. The Shadow, Midtone, and Highlight master wheels let you set image lightness inside those same tight ranges of image tonality marked out by the Low Range, High Range, and Pivot parameters. On log-encoded media, these tweaks ought to come out smooth, if a touch narrower than the Lift/Gamma/Gain controls deliver. On normalized images, though, harsh tweaks from a single master wheel won't always blend cleanly into the next neighboring range of image lightness. NOTE: Since these controls run so tight on normalized images, it's easy to spawn solarization effects, say by lifting the shadows above the Midtones, or dropping the Highlights under the Midtones, as two examples.

### Log Offset Color and Master Controls

The Log controls share the identical Offset color balance and Master Wheel controls that show up within the Wheels and Bars controls under their Lift/Gamma/Gain mode. Although the Offset controls actually get processed as part of the Log controls, they're laid out beside the Wheels controls for convenience, given how handy they are. The Offset color balance control: Behaves as one simultaneous tweak across all three Offset sliders sitting in the Primaries palette; tweaks to the Offset color balance control likewise move the Offset sliders. Applied gently, this makes it simple to cancel color imbalances in the picture's darkest area while rebalancing every other part of the picture at once. Applied more boldly, this control makes it simple to lay a color wash over the whole picture. The Offset wheel: Behaves as a global tweak to image lightness, an operation that's sometimes called setup, lifting or dropping all YRGB channels in unison.

### Offset and Printer Points

Within Bars mode, the Offset controls take the form of three vertical sliders that mirror what the Offset color balance controls hold in the Color Wheel palette, save that here you get separate command over the Red, Green, and Blue color channels. As it turns out, this interface is also ground zero for the Printer Points functionality that DaVinci Resolve offers. Drag one of the Offset sliders up or down and you lift or drop that entire color channel. That can help when you're tackling color channels that are especially troublesome, but it's also how you bring in the kind of traditional linear color adjustments that film color timers have leaned on for decades. In truth, plenty of colorists prize the plainness of these controls, and welcome the faint shadow or highlight contamination that linear color balancing like this can produce as a creative signature of traditional cinema color adjustment.

### Offset RGB and master controls

NOTE: Unlike the other Color Balance control adjustments covered in this chapter, the Offset controls don't draw on the Lum Mix parameter to govern whether separate tweaks to the R, G, or B channels trigger automatic tweaks across the other two color channels so as to hold Luma levels constant. Every Offset and printer points tweak you make to a given color channel touches that channel alone.

### Adjusting Printer Points in the Bars Mode

Every Offset slider carries a pair of arrow buttons too, one up top and one at the bottom. These buttons deliver “Printer Point” adjustment of those values, letting you shift each Offset channel in discrete steps. Printer Points come in handy for projects tightly bound to a film lab, and are built to mimic color adjustments made on optical printers.

The “plus” and “minus” red, green, and blue buttons that make printer point adjustments Sitting under the Offset sliders, the Offset wheel control shifts all three sliders at once, performing a master or setup adjustment. Keyboard shortcuts can drive the Offset sliders, the Printer Point buttons, and the Offset wheel alike. NOTE: Printer point adjustment is supported on both the DaVinci Resolve Advanced and Mini color grading panels, each through rotary controls covering the Red, Green, and Blue channels, plus All channels together.

### Adjusting Printer Points Via Keyboard Shortcuts

Should you lack a color control panel that handles printer points, one of the finest ways to use them is to switch the numeric keypad over to dedicated keyboard shortcuts meant just for printer points.

To use the Printer Lights Hotkeys: Pick Color > Printer Light Hotkeys, or press Option-Command-Grave Accent (`) Once Printer Light Hotkeys are on, two sets of shortcuts let you work the printer points. The first set is for when you'd like to drive RGB directly in whole steps.

Red 7 - Plus Red 4 - Minus Red

Green 8 - Plus Green 5 - Minus Green

Blue 9 - Plus Blue 6 - Minus Blue

If instead you'd rather work the classic way, driving cyan, magenta, and yellow in whole steps, a second set of shortcuts covers that, drawing on the rest of the keys on the numeric keypad.

Cyan 1 - Plus Cyan Minus (–) - Minus Cyan

Magenta 2 - Plus Magenta 0 - Minus Magenta

Yellow 3 - Plus Yellow Period (.) - Minus Yellow

There's also a pair of keyboard modifiers that hand you finer command over printer points tweaks made with these special keyboard shortcuts, while keeping the coarser default tweaks that let you swing bigger changes faster:

- Hold Command as you use these key shortcuts to shift printer points in quarter‑increments.
- Half-increments are available as well, though you'll have to assign their keyboard shortcuts by hand.

### Printer Light Step Project Settings

Whatever steps the Printer Point buttons take get defined by the Printer Light Step Calibration parameters, which live in the Color panel of the User Preferences. Their defaults are built to mimic traditional film printer adjustments, yet you can customize them so DaVinci Resolve's printer points adjustments match those of a particular film lab's gear. Still, when no lab is in the picture, altering the Step and Density settings changes how big an adjustment each printer point delivers, however your own taste runs. For more information, see Chapter 4, “System and User Preferences.” The Color panel of the User Preferences holds controls for tuning Printer Point functionality TIP: Should you feel left out because everybody else relies on printer points while they remain new to you, surfacing the Parade scope makes a great way to learn how these adjustments behave as you watch their exact effect on the red, green, and blue channels of the video signal.
