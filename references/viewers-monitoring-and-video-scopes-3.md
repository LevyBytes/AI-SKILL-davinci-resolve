# Viewers Monitoring And Video Scopes (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Selected Still Images: Lets you compare the present clip against an assortment of other stills you pick out from the Gallery. Rather than a grading preview, what you're really getting is a split screen built from the selected still images in the Gallery.
- Version: Presents as many as 16 versions of the present clip simultaneously, which makes it simple to weigh a run of differing versions against each other. Should you keep more than 16 versions, an award of some kind is surely owed to you. Double-clicking a version makes it the active version.
- Versions and Original: Presents up to the first 15 versions of the present clip, plus the original ungraded clip tucked into the upper left-hand corner. Double-clicking a version makes it active, yet a double-click won't let you pick the original.

### Marker Overlays and Navigation

Should you rest the playhead directly over a marker within the Timeline of the Color page, that marker's details surface in a Viewer overlay, exactly as they do on the Edit page, which makes reading notes and spotting the available information simpler. Hiding these overlays is straightforward: click the Viewer option menu and switch "Show marker overlays" off.

### Timeline Marker List Available in Color Page Viewer Option Menu

A submenu within the option menu of the Color page Viewer enumerates every Timeline Marker present in the timeline you've got open. This makes working through client notes a breeze.

A quick-access list of Timeline markers reachable from the option menu of the Viewer

### Using Video Scopes

Though they aren't bound directly to how the Viewers are used, video scopes still operate side by side with them to assist you in assessing the pictures you're handling. A collection of five real-time video scopes ships with DaVinci Resolve, which you can lean on to keep an eye on the internal data levels of the clips throughout your project as you work. Every scope delivers a clear graphical breakdown of distinct traits of the video signal, presenting the relative strength and span of separate color components — luma, chroma, saturation, hue, gamut, white point, plus the red, green, and blue channels that jointly make up the color and contrast of the pictures in your program.

### Video Scope Location

Out of the box, you can display any single one of these scopes at a moment in the lower right corner of the Color page, by clicking the Video Scope button found in the palette button bar.

The video scope, parked alongside the remaining palettes down at the foot of the Color page

If you prefer, clicking the Expand button at the upper right of the video scope opens the video scopes into a floating window, where you're able to show all four video scopes together, or one at a time, on whichever monitor is hooked up to your workstation.

Video scopes in a floating window in HDR (ST.2084/HLG) mode On top of that, the video scopes can sit docked on a secondary display within many of the dual-screen layouts DaVinci Resolve offers. That said, with three computer displays and dual screen layouts active, you've still got the choice of opening the floating Scopes window and dropping it onto your third display, sized however big you want. The video scopes don't live solely in the Color page. You'll find them in the Media and Deliver pages too, for any moment you have to assess the video signal more impartially, like while preparing to capture from tape or scan from film, or while readying things for output. To bring up video scopes from the Media, Color, or Deliver pages, do one of these: Choose Workspace > Video Scopes > On/Off (Command-Shift-W), which floats them out; or floatingwrkspace > Dual Screen > On, which folds them into a dual screen layout instead.

### Video Scope Measurement Using Scales

Since what you're assessing is the internal condition of the image data, the numeric scales of the WFM and Parade scopes by default always show 10-bit full range data spanning 0–1023, no matter which Video/ Data Level setting you've picked within the Master Settings panel of the Project Settings. That hands you a view into the way the image gets processed by DaVinci Resolve ahead of being sent out through your computer's video I/O interface. While you're grading in HDR (High Dynamic Range), you can pick HDR (ST.2084/HLG) out of the Video Scopes option menu (this capability exists in the Studio version alone). Doing so swaps the 10-bit scale of the Waveform, Parade, and Histogram video scopes for a scale built on nit values (or cd/m2) in its place.

### The Parade scope showing the data range scale

### The Parade scope showing the HDR "nit" scale

### Changing Waveform Scales

A Waveform Scale Style submenu inside the Video Scopes option menu (the three dots menu) lets you decide how the numeric scale sitting at the left of Waveform and Parade scopes gets represented. The choices on offer begin with 10-bit display (the default), then 12-bit display, followed by Percentage (0 to 100), then millivolt (mV), and lastly HDR (ST.2084/HLG). Beyond the extra flexibility this affords you, it also means there's no longer any need to head into the Preferences to make the scope show an HDR scale in nits (cd/m2).

### Waveform scale options

IMPORTANT: When you're working in a workflow that isn't DaVinci Resolve Color managed and you switch on the HDR (ST.2084/HLG) scopes, the waveform will reflect HDR levels at all times, even where you've hand-picked the output color space as Rec.709, so it won't be 100% accurate.

### Changing Vectorscope Scales

A Vectorscope Scale Style submenu inside the Video Scopes option menu (the three dots menu) lets you decide how the hue reference indicators get shown.

### Vectorscope scale options

Four graticule options exist: Off: Switches off every graticule overlay within the Vectorscope, handing you a clean look at the Vectorscope graph set against black. Standard: The default arrangement. Cross hairs mark the scope's center, while boxes pinpoint, for every primary and secondary hue, its center target (red, magenta, blue, cyan, green, yellow). A surrounding circle supplies a broad reference for the angle along which any portion of the graph might land. Simplified: Presents a crosshairs marking the scope's center plus smaller crosshairs marking each primary and secondary hue. Handy whenever you want references stripped of extra clutter. Hue Vectors: A graticule crafted to give colorists a more practical reference for creative calls and image comparison. There's nothing merely ornamental about it. For every primary and secondary hue, graticule lines trace its reference angle, running from the hue targets inward to the center, furnishing a more instantly practical reference while you weigh one vector scope graph against another. Within the zone of average saturation in most pictures, these reference lines fade away, so they don't obstruct your read of faint detail. The center crosshairs sit along the red‑cyan and yellow-blue axes, marking the natural warm-to-cool axis running between them. Tic marks flag both the 75% and 100% levels of image saturation per hue. You're also free to decide whether the primary and secondary hue targets appear for 75% image saturation, 100% image saturation, or both, and whether the text labels for each hue get shown.

### Displaying Scopes With Data or Video Levels

When a project is being graded at video levels, a setting within the Video Scope option menu's Waveform Scale Style submenu lets you flip the video scope scaling between Data Levels (the default) on one hand and Video Levels on the other (which you reach by switching on Video Level Scopes). This governs nothing but how your scopes appear; monitored or rendered output stays untouched.

The Waveform scope shown at default Data Levels,

The same waveform shown with Video Level Scopes turned on

### Video Scope Performance and Detail

Within DaVinci Resolve 16 every video scope was overhauled to render more detail at faster speeds than earlier releases managed. Although they're GPU-accelerated, the video scopes still draw on a measure of video processing muscle to run. Based on whichever mix of video scopes and scope options you've turned on, your real time processing headroom may dip ever so slightly. Shutting the video scopes returns all that processing to color correction and effects. On heavy-duty workstations you'll likely spot no change, yet on weaker machines, closing the scopes could yield a modest gain. A pair of global settings within the Video Scope option menu shape the performance and detail of every video scope alike.

- On slower workstations, a quality submenu lets you pick High, Medium, or Low quality scope drawing, trading legibility against performance. High quality reveals the fullest detail about the video signal, whereas an Auto option chooses on the basis of what your workstation can handle.

The Quality setting in the Video Scope option menu

- Every video scope carries a Low Pass Filter setting within the Video Scope option menu that strips a signal's noise so the scope graphs read more cleanly. Though this can serve as an "x-ray" for spotting detail inside the scope graph interiors, it can leave the highlight and shadow excursions on the graph looking slightly shy of their real positions, so enabling the "Extents" option of whatever scope you're on is advised, giving you a clear read of the peak excursions across your scopes. Extents draws an outline marking every graph excursion to reveal the genuine level of all overshoots and undershoots within the video signal, even with the Low Pass Filter switched on.

The Waveform scope with Low Pass Filter turned off

The Waveform scope with Low Pass Filter turned on

### Display Qualifier Focus in Video Scope Graphs

The Display Qualifier Focus setting within the Video Scope option menu helps you work out which features of the video picture line up with which regions of the video scopes. With Display Qualifier Focus switched on, picking the Qualifier mode of the Viewer and sliding the eyedropper across the picture traces circles around the sampled pixels wherever they show up in the video scope graph that's currently on view. Where several video scopes are on view, each scope carries its own marking, particular to that scope, of where the sampled pixels lie.

Holding the eyedropper above a feature within the Viewer Those same pixels analyzed by region, surfacing across the stacked red, blue, and green waveforms of the Waveform scope.

### Explanation of Each Video Scope

Five video scopes are on offer, and each presents a separate breakdown of the video signal you're tweaking.

### Waveform Monitor

Stacks waveform readouts — whether of the Y (luma/luminance) channel, the CBCR (the color difference channels of Y'CBCR), or the RGB (red, green, and blue) channels — atop one another so their alignment is visible to you.

The Waveform scope showing Y' (luma) only, with colorization and extents enabled. What the Y option hands you is a genuine Luma scope on which Colorize can be switched on to surface false color, letting you see where the colors of the Viewer image land within the video scope graph.

Where the RGB scopes are concerned, what the relative heights of the red, green, and blue graphs convey matches exactly the account given further down for the Parade scope, and once color is switched on those red, green, and blue graphs each pick up a tint of the color they stand for. That makes it simple to spot where all three graphs line up, by hunting for the places where stretches of the waveform monitor read as white, which results from the red, green, and blue graphs lining up and combining their color.

### Parade

The Parade scope lays out separate waveforms beside one another that gauge the strength of individual video signal components. You can configure the Parade scope to gauge RGB, YRGB, and Y'CBCR. By presenting the intensity of the luma, red, green, and blue channels side by side, the Parade scope makes spotting and weighing imbalances possible through a comparison of the relative heights of the RGB graphs across three zones — the highlights, found at the top of the R, G, and B graphs; the shadows, down at the bottom of the R, G, and B graphs; and the midtones, sitting in the middle of the R, G, and B graphs — all so you can pin down color casts and carry out scene-by-scene correction. With the YRGB channels viewed together, the foot of all graphs flags the black point of the picture, while the crest of all graphs flags the white point. From there it follows that the gap between the foot and crest of all graphs flags the overall contrast ratio of the picture under your assessment. Tall parade graphs flag a wide contrast ratio, whereas short parade graphs flag a narrow contrast ratio.

The Parade scope showing YRGB waveforms, with colorization and extents enabled

### Vectorscope

Gauges the full sweep of hue and saturation present within a picture. The readings are taken against a centered graticule, which you can switch on, overlaid upon the scope to supply a reference through crosshairs. A traditional vectorscope ships with DaVinci Resolve, its graph mimicking a trace-drawn one, where 75 percent color bar targets mark the angle of every primary and secondary color around the graph's rim, alongside an optional skin tone reference graticule (also called the In-phase reference). The Vectorscope can have Colorize switched on to surface false color, which lets you see where the colors of the Viewer image fall within the video scope graph. The more saturated colors in the frame push those stretches of the graph further out toward the rim, while the less saturated ones cling nearer the vectorscope's center, which stands for 0 saturation. By gauging how many stretches of the vectorscope graph jut out at varying angles, you can tell how

many hues sit in the picture, while the precise angle of each stretch of the graph reveals which hues those are. On top of that, by gauging how neatly the middle of the vectorscope graph centers itself against the crosshairs, you can sense whether a color imbalance is present in the picture. Should the vectorscope graph sit off-center, whichever direction it tilts toward signals that a color cast (tint) is present in the picture.

The Vectorscope displayed at 2x mode, its highlights, mid-tones, and shadows extents merged together

### Histogram (RGB/YRGB parade histogram)

Presents a statistical breakdown of how many pixels of each color channel sit at each percentage of tonality, charted along a digital scale running from 0 percent (black) up to 100 percent (white). Setting the left, middle, and right portions of the Y, R, G, and B graphs (Y being optional) against one another lets you gauge the color balance across the shadows, midtones, and highlights of the picture.

### The Histogram scope set to YRGB

Viewed together, the left edge of all graphs flags the black point of the picture, while the right edge of all graphs flags the white point. From there it follows that the gap between the left and right edges of all graphs flags the overall contrast ratio of the picture under your assessment. Wide histogram graphs flag a wide contrast ratio, whereas narrow histogram graphs flag a narrow contrast ratio.

### CIE Chromaticity Scope

DaVinci Resolve carries CIE 1931 xy and CIE 1976 uv scopes, which let you view the current image analysis as a graph laid over a triangle standing for the tristimulus values of the color gamut you're operating within, together with a marker for the current white point. A label names the gamut presently chosen, with the exact coordinates of these Red, Green, and Blue values plus the White point, while the broad "horseshoe" outline stands for the whole range of visible light, the lot of it charted upon an xy graph. The white point generally rests atop a curve tracing the center of the shape. That curve marks the black body locus, along which the assorted color temperatures of a picture's white point line up, running from orange-ish warm toward blue-ish cool. This black body locus corresponds to the color temperatures yielded by heating carbon up through successive temperatures. You've also got the choice of displaying a second gamut triangle, for occasions where you'd like to set the current analysis against two distinct gamuts. That can prove handy when your deliverables span several gamuts and you want to see which stretches of the video signal stay safe across all gamuts and which stretches push past the smaller of the pair. When you do so, a label goes on each of the two gamuts, while off to the side you'll find listed, for both gamuts, the coordinates of the Red, Green, and Blue values.

The CIE 1931 xy scope showing both P3 and Rec. 709 gamuts. Seen one way, the Chromaticity scope counts as a 3D scope, yet it's rendered as though you were peering down at the top of a 3D form that charts every color value in a picture across X, Y, Z space, while you can only make out the 2D outline tracing the broadest stretches of that form drawn upon an X, Y plot. Truly the graph accounts for each individual value that a 3D plot of the image data contains, yet the triangle marks nothing more than the broadest "slice" of the current gamut and of this 3D form across the mid-tones. The upshot is that, although the Chromaticity scope's graph hands you a rough sense of whether the current picture sits within gamut against your delivery spec, it's neither exact nor foolproof, since a portion of the image data might land inside this wide triangle yet still overshoot the demanded gamut somewhere else, up in the highlights at the top or down in the shadows near the bottom of the 3D form you're peering down upon. Conversely, should any portion of the graph reach beyond the edges of the gamut triangle, that unmistakably marks a gamut violation. An extra gamut triangle can be added within the scope settings so you can set the color space you're working in against another color space, for reference. Anyone with even passing exposure to color grading ideas will recognize the traditional CIE 1931 horseshoe graph, which charts the slice of the spectrum the human eye can perceive per studies carried out in the late 1920s (later studies have borne out this analysis). The optional CIE

1976 uv graph rests on a revised color space (CIELUV) that the International Commission on Illumination (CIE) put forward in a bid to draw a more perceptually uniform graph of color. Where the CIE 1931 analysis visually overstates certain stretches of a color graph, the CIE 1976 graph renders every stretch of a color graph roughly in proportion to the rest. On the whole, neither analysis ranks as more "correct" than its counterpart; it comes down simply to which you'd rather look at.

The CIE 1976 scope showing both P3 and Rec. 709 gamuts

### Panning and Zooming the Video Scopes

Should you wish to inspect any stretch of a video scope's graph more closely, here's what you can do: To zoom into a graph: Keep the Option key held while you spin the scroll control. To pan around a graph: Drag with the middle pointer button held down.

### Customizing the Video Scopes

Having opened the video scopes, you've got a range of ways to tailor how the scopes look and to surface extra onscreen graticule detail that helps you measure whatever you're after. Ways to tailor the Scopes window:

- To resize the Scopes window: Grab its lower right-hand corner and drag to set the Scopes window to whatever size suits you.
- To set how many scopes show simultaneously: Within the upper right-hand corner of the Scopes window, click one of the buttons to lay the video scopes out in 1, 2, 4, or 9 up arrangements. You can equally set how many scopes show at the same time by choosing Workspace > Video Scopes > 1-Up, 2-Up, or 4-Up.
- To reassign which scope sits in which pane: At the upper left corner of each scope's pane, click the Name drop-down and pick a different scope. If it suits you, you can spin up more than one of any kind of video scope within multi-scope layouts, for occasions where you'd like to view variations on one scope type carrying different settings.

To give an example, you might choose to surface three Vectorscopes, each set to a separate tonal range, so you can view Vectorscope analyses of Low (shadows), Mid (midtones), and High (highlights) all at once.

### Different layout options in the Scope window

Once it's open, you can resize the Scopes window as big or small as you need, dropping it on a secondary display should you want it bigger still. To tailor each video scope's display options: 1 Click the Option button sitting to the right of the Scope drop-down menu to surface the current scope's Custom Controls window.

Clicking to open the current scope's custom controls 2 Tweak any of the controls on offer to shape the look of that particular scope. 3 Click anywhere beyond the Custom Controls window to dismiss it.

### Parade Scope Display Options

The Parade scope has the following options:

- RGB, YRGB, and YCbCr modes, which let you assess more channels than was possible before.
- A colorize checkbox lets you view graphs either in monochrome or in false-color (marking red,

green, and blue).

- An Extents checkbox draws an outline marking every graph excursion, to plainly reveal

all overshoots and undershoots within each waveform.

- The Parade slider turns that scope's graph brighter or dimmer. Brighter graphs make fine detail

easier to catch, yet harder to judge which stretches of the graph run stronger and weaker.

- The Graticule slider turns that scope's scale brighter or dimmer, rendering it more or less visible

(or distracting) against the graph.

- The Show Reference Levels checkbox lets you switch on adjustable Low and High

reference level markers by nudging the low and high sliders off their defaults. This proves especially handy for HDR grading where you're operating within a particular peak luminance threshold.

### Options in the Parade scope

### Options in the Waveform scope

### Waveform Scope Display Options

The Waveform scope has the following options:

- Y (luma) and CbCr (chrominance) modes that show you the genuine luma or chroma signals on their own, plus RGB that shows you nothing but an RGB analysis.
- In RGB mode, R, G, and B buttons each of which can be flipped on and off on its own to view whatever combination of graphs you want.
- A colorize checkbox lets you view overlaid graphs either in monochrome or in false-color (marking red, green, and blue). Where only the Y or C scopes are switched on, the distinct stretches of these graphs get drawn in color lifted from the image under analysis, which makes it easier to see which stretch of the scope graph maps to which stretch of the image.
- An Extents checkbox draws an outline marking every graph excursion, to plainly reveal all overshoots and undershoots within each waveform.
- The Waveform slider turns that scope's graph brighter or dimmer. Brighter graphs make fine detail easier to catch, yet harder to judge which stretches of the graph run stronger and weaker.
- The Graticule slider turns that scope's scale brighter or dimmer, rendering it more or less visible (or distracting) against the graph.
- The Show Reference Levels checkbox lets you switch on adjustable Low and High reference level markers by nudging the low and high sliders off their defaults. This proves especially handy for HDR grading where you're operating within a particular peak luminance threshold.

### Vectorscope Display Options

The Vectorscope has the following options:
