# Automated Grading Commands And Imported Grades (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Automated Grading Commands and Imported Grades

DaVinci Resolve offers an enormous range of hands-on grading controls that let you steer nearly every aspect of a digital image, yet DaVinci has also poured significant effort into research aimed at making colorists more productive by building automated grading features. On top of that, now that integrated editing has welcomed professional editors into a single environment for cutting, grading, and finishing inside DaVinci Resolve, those same automation features designed to send colorists home sooner can equally help editors who aren't colorists handle the more straightforward grading chores.

### Color Match Palette

When the camera crew and lighting team are thoughtful enough to capture a color test chart at each of the principal lighting configurations across the project you're working on, DaVinci Resolve can overlay a grid of sample points onto a chart within a clip and run a mathematical analysis of those sampled values to build an automatic correction. The Color Match palette gives you controls for setting the Source Gamma, Target Gamma, and Target Color Space, ensuring the correction it produces suits both the camera that recorded the footage and the project configuration you've established. These standardized color charts are recognized by the Color Match palette:

- Datacolor SpyderCheckr 24
- DSC Labs ChromaDumonde 24+4
- DSC Labs SMPTE OneShot
- X-Rite ColorChecker Classic
- X-Rite ColorChecker Classic - Legacy
- X-Rite ColorChecker Video
- X-Rite ColorChecker Passport Video

A side-by-side comparison of the X-Rite ColorChecker, Datacolor SpyderCheckr, plus DSC Labs SMPTE OneShot charts, every one of them recognized within the Color Match palette The analysis yields an automatic color correction that establishes a neutral grade for the shot, giving you a base from which to build the remainder of your grade.

### Tips for Properly Shooting a Color Chart

How well Color Match performs hinges entirely on the way the charts were captured on location. Shoot the charts correctly and the outcome will be excellent; capture them badly and the outcome becomes erratic. Follow these recommendations to coax the strongest possible results out of Color Match:

- Light the chart uniformly so that each patch receives identical intensity (level) and color. Wherever shadows fall or the lighting color shifts across the chart, Color Match will attempt to correct for those variations and an imprecise match is the outcome. If you preview a chart on a waveform monitor while it's being lit ahead of the shoot, each patch as displayed on the scope ought to look like a rectangle with a "flat top."

### Poorly lit chart with irregularly topped waveforms

### Well lit chart with flat-topped waveforms

- None of the chart's patches should clip in any of the RGB color channels. Whenever a channel clips, Color Match is fed wrong RGB values, and that throws off the resulting match.
- Aim to record the chart's white patch somewhere in the 70–95 IRE/percent window. Nailing exposure matters a great deal here, and although Color Match offers a measure of leeway through the White Level option, you'll only get reliable output when the original chart was captured with its white patch landing inside the 70–95 IRE/percent band on a waveform monitor. Avoid recording a white patch above 95 IRE/ percent, because at those levels one of the RGB channels is typically near clipping or already clipping, which produces an imprecise match.
- Set the Source Gamma option so it corresponds to the encoded OETF (opto-electrical transfer function, or gamma) carried by the recorded image. Producing a faithful adjustment requires Color Match to work with image data that is scene linear (linear to light). The majority of captured or recorded footage carries a tone curve (gamma curve) applied to make the most of the available bit depth, and various cameras apply distinct gamma curves to draw the most out of their particular sensors. Because the Color Match algorithm first transforms the image data into a scene linear space prior to building an adjustment, it has to reverse the gamma curve introduced by the camera or the debayer stage. Choose the wrong Source Gamma value in the Match Color palette and the data won't linearize properly, leaving you with an imprecise match.
- A scene whose lighting has an odd spectral response or a pronounced color tint can produce an imprecise match. When a scene is illuminated by sources with an unusual spectral response (cheap fluorescent tubes, low-grade LED fixtures, or mercury vapor lamps whose spectral power distribution is extremely narrow or spiky), metameric errors can appear both in how the camera responds and in how the Color Match function behaves, yielding an imprecise adjustment. You'll get the cleanest results when the scene's lighting has a chromaticity sitting near the black body locus (with a tightly correlated color temperature) together with a reasonably smooth spectral power distribution. Put simply, rely on high-quality lighting free of spikes in particular regions of the spectrum.
- A wide gap between the color temperature of the light falling directly onto the chart and the ambient light filling the rest of the scene can produce perceptual errors. Frequently the issue stems from perception rather than a genuinely wrong color adjustment. Take an exterior scene lit artificially with fixtures throwing extremely warm light (color temperatures down around 3200K or below) while cooler ambient light fills the surroundings: matched to a Target Color Temp of 6500K, it can read as excessively blue. The reason is that the chart sitting under the direct fixtures is lit at the warmer (yellower) color temperature, whereas shadowed regions of the scene run far cooler thanks to the ambient "blue" skylight; the upshot is an automatic color adjustment that suits the chart yet looks overdone across the rest of the frame.

### How to Use Color Match

The procedure below demonstrates building a color correction with the Color Match palette and its overlay.

### The Color Match palette

To sample a color chart to make an automatic correction: 1 Pick the clip containing the chart you intend to sample. When needed, the View > Show Current Clip With Handles option reveals extra frames ahead of the present clip so a color chart sitting in the media's leader becomes visible. 2 When needed, pick the entry from the Source Gamma drop-down menu that matches the gamma used while the footage was recorded. 3 Next, select a target gamma and color space matching the format you intend this clip to be matched against. 4 Open the Viewer tool drop-down, select the Color Chart overlay, and work its corner-pinning controls to align the sampling boxes against the color patches on the chart.

Aligning the Color Match target with the chart in the video 5 Once you're done, press the Match button and the clip receives its automatic correction.

### A clip before and after automatic color matching

TIP: Bear in mind that a chart isn't required for every shot. Where a location's lighting holds steady throughout a scene, a single chart analysis is enough to build a correction you then copy onto all the remaining clips of that same scene. Naturally, when several cameras are at work in one scene, you'll want a separate chart analysis per camera if your goal is to bring them into closer agreement. And for a scene stretched across an entire day, consider capturing charts whenever the time shifts enough to track the lighting changes underway.

### Configuration Controls

What follows breaks down in greater depth each parameter you'll find in the Color Match palette.

- Source Gamma: Sets the source gamma that the footage was captured with. Picking the right gamma is mandatory or the output loses accuracy.
- Target Gamma: Lets you pick the target gamma you want the corrected clip to adopt. Although this is usually the gamma at which you'll deliver the finished program, alternative target gamma values are available for specialized workflows.
- Target Color Space: The color space in which you'll deliver the finished program.
- Color Temp: A tunable color temperature control letting you hand-adjust the target

color balance of the resulting correction toward warmer (lower values) or cooler (higher values). The default is 6500K.

- White Level: A checkbox, off by default, that lets you hand-pick the target white point the automatic correction will rely on. Pushing this value up or down expands or tightens the contrast of the finished correction.
- Match button: After you've dialed in the right settings and lined the color match target up with the chart that was captured, click to run the match.
- Chart type drop-down menu: This drop-down lets you pick from the chart types that are supported. As of this writing, the roster includes Datacolor SpyderCheckr24, then theChromaDuMonde 24+4, followed by DSC Labs SMPTE OneShot, alongside X-Rite ColorChecker Classic, plus X-Rite ColorChecker Classic - Legacy, as well as X-Rite ColorChecker Video, and finally X-Rite ColorChecker Passport Video.
- Reset All button: Clears every control and adjustment within this palette.

### Reset Controls

Within the Color Match option menu sit several commands letting you undo work you've done in the Color Match palette.

- Reset Match Configuration: Restores the Configuration parameters covered above.
- Reset Applied Match: Clears the matching operation while leaving the Configuration controls untouched.

### Automatic Adjustments in the Primaries Palette

The Primaries palette holds four controls aimed at automating various color adjustments, giving you a leg up any time you set out to remove a color cast from the shot or settle on stronger black and white points for exposure.

### White Balance Eyedropper

Sitting at the lower-left corner of the Primaries palette beside the Automatic Correction button, the White Balance eyedropper offers a self-running route to clearing a color cast from your shot, which you steer by hand-selecting an element of the image meant to read as white. To clear an unwanted color cast or tint from a shot through auto white balance: 1 Press the White Balance eyedropper button. The pointer becomes the White Balance eyedropper.

The White Balance eyedropper 2 Inside the Viewer, click whatever element ought to be white, whether that's a white wall, white trim framing a window, white blinds, a white shirt, or similar. While you move the eyedropper about, the RGB values surface as a tooltip so you have a clearer sense of the color belonging to the feature you're about to select. Confirm that what you click is (a) genuinely meant to be white rather than off-white, and (b) tied to image detail that isn't clipped, since clipping can make regions look white when they truly aren't. The outcome is that the image's white balance should read far more neutral than it did. Keep in mind this adjustment doesn't route through any Primaries palette control; it's an invisible, self-contained adjustment.

### Pick Black Point and Pick White Point

Found at the top-left corner of the Lift and Gain controls within the Wheels and Bars modes of the Primaries palette, the Pick Black Point and Pick White Point eyedropper controls let you reshape contrast by dropping the black point or lifting the white point of the shot, while also fixing unwanted color casts living in the shadows or highlights. NOTE: With the Pick Black and White Point controls it's all too simple to push the highlights up or pull the shadows down far enough that part of the image clips. To give these controls their best shot at working, hunt down the very brightest or darkest regions of the image to sample, per the directions below.

To set a shot's black point automatically: 1 Press the Pick Black Point control. The pointer becomes the Black Point tool.

The Auto Pick Black Point control 2 Inside the Viewer, click whatever element ought to be black, such as the deepest pocket of a background shadow or a fold of clothing, black fabric, or an object painted black. As you slide the Black Point tool about, the RGB values surface as a tooltip giving you a better read on the color of the feature you're poised to select. Confirm that what you click is (a) genuinely meant to be black rather than some very dark shade, and (b) tied to image detail that isn't clipped, since clipping can make regions look black when they truly aren't. The outcome is that the image's darkest regions should read considerably darker than before, with any color imbalance in the shadows neutralized. In contrast to the White Balance eyedropper, this adjustment routes through the Lift controls of the Wheels and Bars mode, which ought to show some degree of movement as a result. To set a shot's white point automatically: 1 Press the White Point control. The pointer becomes the White Point tool.

The Auto Pick White Point control 2 Inside the Viewer, click whatever element ought to be white, whether that's a white wall, white trim framing a window, white blinds, a white shirt, or similar. As you slide the White Point tool about, the RGB values surface as a tooltip giving you a better read on the color of the feature you're poised to select. Confirm that what you click is (a) genuinely meant to be white rather than off-white, and (b) tied to image detail that isn't clipped, since clipping can make regions look white when they truly aren't. The outcome is that the image's brightest regions should read considerably lighter than before, with any color imbalance in the highlights neutralized. In contrast to the White Balance eyedropper, this adjustment routes through the Gain controls of the Wheels and Bars mode, which ought to show some degree of movement as a result.

### Auto Color

The Auto Color command gives you a fast route to automatically balancing a clip's blacks and whites using the present frame sitting under the playhead. Beginning with DaVinci Resolve 16, both the A button in the Primaries palette and the Shot Match command reached from the Thumbnail Timeline contextual menu now lean on advanced algorithms, powered by the DaVinci Neural Engine, to deliver better outcomes when automatically tuning color balance and contrast. These controls were engineered to perform best in the Rec. 709 color space, at a gamma of 2.4, so they pair nicely with using Resolve Color Management (RCM) to normalize media first.

- The A button runs an automatic analysis of the present frame under the playhead to hand you a more reliably useful neutral base for additional adjustment.
- The Shot Match command brings one or more clips into line with the color and contrast of a target clip, whether that target is graded or ungraded. This refreshed Shot Match is meant to be run once you've applied the A button to every clip involved, covering the clips being aligned together with the reference clip they're aligned against.

When you want a quick neutral base across a span of clips, you can also pair these commands, grading a target clip with the A button and then leaning on Shot Match to bring a range of clips from the same scene into line with that automatically graded reference. Do note that these commands aim to give you a fairly neutral base for ongoing grading; they aren't built to produce creative or artistic grades.

### The Auto Color button

To make an automatic correction, do one of the following:

- Bring up the Primaries palette in whichever mode, then press the A button sitting at its lower left-hand corner.
- Choose Color > Auto Color (Option-Shift-C).
- Press the AUTO COLOR button on the T-bar panel.

Auto Color's strength is that it delivers an instant outcome on any clip without you needing to sample the image or have a dedicated test pattern to analyze, but its weakness is that the absence of guidance leaves how useful the command turns out to be rather unpredictable. On the occasions it succeeds, it can do a fine job of handing you a neutral base for ongoing grading. On the occasions it falls short, you're best served clearing the resulting adjustment and grading by hand the traditional way.

### Legacy Auto Color

You can reach the earlier approaches to Auto Color and Shot Match from the Color panel of the User Preferences through a pair of checkboxes labeled "Use Legacy Auto Color/Shot Match." Switch these on and DaVinci Resolve hunts for the darkest values in the image to neutralize the RGB color balance across the blacks, plus the brightest values to neutralize the RGB color balance across the highlights. On top of that, Master Lift and Master Gain get tuned to push image contrast out to the extremes of 0 and 100 percent. Keeping the Primaries Bars mode open while using this control makes it simpler to spot what shifted once these automatic adjustments take effect.

### Shot Match

The pair of automated color correction commands available earlier, Auto Color and Color Match, each help bring a chosen clip to a clean, neutral base when you're pressed for time or struggling to reason out a fix by hand. That said, this is merely the opening move in grading a scene. Once you've made a broad adjustment to lift a clip's color within a scene, another of the colorist's core duties is tuning every clip in that scene so they all align with the clip you began from, leaving them looking as though they were captured at one time in one place. The trade calls this scene-to-scene color correction, scene balancing, or shot matching. Although DaVinci Resolve packs plentiful tools that smooth the manual version of this work, wouldn't it be handy to simply pick a run of clips you want aligned and let the software handle it? That's precisely the job Shot Match was built for. Whether you're a colorist racing the clock to power through a low-budget feature on a punishing schedule, a DIT cutting best light dailies who simply wants them to align a bit more tightly before shipping media to editorial, or an editor who isn't quick at color correction and needs to throw a fast color balance onto a rough cut before screening the project for a client the first time, the Shot Match feature of DaVinci Resolve was created to swiftly draw different clips on a timeline into closer agreement with one another, in as few steps as possible. Beginning with DaVinci Resolve 16, the Shot Match command reached from the Thumbnail Timeline contextual menu leans on an advanced algorithm, powered by the DaVinci Neural Engine, to deliver better outcomes when automatically tuning color balance and contrast. This control was engineered to perform best in the Rec. 709 color space, at a gamma of 2.4, so they pair nicely with using Resolve Color Management (RCM) to normalize media first. The refreshed Shot Match is meant to be run once you've applied the A button to every clip involved, spanning the clips being aligned as well as the reference clip they're aligned against.

(Top) the scene as originally shot; (Bottom) the same scene once shot match has brought every selected clip into line with clip 62 Legacy Auto Color Both legacy routines, for Auto Color as well as Shot Match, stay accessible within the Color panel of the User Preferences via two checkboxes carrying the label "Use Legacy Auto Color/Shot Match." Turn them on and DaVinci Resolve seeks out the image's darkest values so it can neutralize the RGB color balance through the blacks, plus its brightest values so it can neutralize the RGB color balance through the highlights. Beyond that, Master Lift and Master Gain are nudged to drive image contrast all the way to the boundaries of 0 and 100 percent. Working with the Primaries Bars mode visible alongside this control makes spotting the changes from these automatic adjustments more straightforward.

### Shot Match Guidelines

Remember that Shot Match isn't trying to make your clips look good; it's trying to make them read the same as the clip you pick to match against, or at least come as close as it can without building a color correction that damages the image. Shot Match exists to make it easier for you to bring a scene's worth of clips into alignment, giving you a base on which to build out the rest of the look you're after for that scene, layered atop this first match. The clip you choose to match against can carry a correction of its own, but for the strongest results, hold yourself to simple Lift/Gamma/Gain primary adjustments. Apply Custom curve work or secondary adjustments to the image and Shot Match will have a far harder time delivering a good result. Shot Match performs best on normalized clips. When your timeline is cut from log-encoded clips, consider running DaVinci Color Management to normalize every clip in the Timeline ahead of using Shot Match, so you land the most accurate results. You certainly can run Shot Match against logencoded media, yet the flat color signal of log-encoded media may make solid results harder to reach, depending on the scene. On top of that, Shot Match isn't the right tool for trying to match un-normalized log-encoded clips that rely on different flavors of log encoding, such as LogC and RedLogCine, nor for trying to match normalized clips against un-normalized ones. Since log-encoding resembles a set of red, green, and blue curve operations, Shot Match isn't built to land a successful result in that situation. Shot Match also isn't designed to apply corrections to clips that already carry node adjustments. Those outcomes will be unpredictable and likely won't match. While the clip you're matching against can have simple primary adjustments applied, the rest of the selected clips being matched ought to be entirely ungraded. Finally, Shot Match was built to do no harm to the image. That means if you turn Shot Match loose trying to match an underexposed interior shot to an exterior captured under high-noon sun on a clear day, the Shot Match algorithm will do what it can to "split the difference" so the gap between those two clips reads as less jarring, all while being careful not to stretch the color and contrast adjustments on the underexposed clips so far that the image breaks apart.

### How to Use Shot Match

Describing what Shot Match does in plain terms isn't easy. It's an intricate algorithm built to grapple with an impossibly wide spread of distinct scenarios. Consequently, Shot Match leaves every user-editable control on the Color page untouched. Instead, the image adjustment Shot Match generates is laid on invisibly, as the final adjustment on whichever node was selected at the moment Shot Match ran, much like a LUT.

### A Shot Match adjustment applied to a clip

Running Shot Match looks deceptively straightforward as a procedure. Even so, landing a good result demands some deliberate thought about which clips you pair against which.

To match one or more selected clips to a specific clip: 1 Working from the guidelines laid out in this section, Command-click or Shift-click whichever clips you want to be matched. The clip you intend to match against may or may not sit within the selection. You can pick as few as one clip or as many as you'd like.

### Selecting clips you want to be matched

TIP: To make the before-and-after easier to notice, switch on Split Screen and pick Selected Clips from the mode drop-down in the Viewer Options. Doing so lets you view every clip you're about to match laid out as a grid. 2 Then, right-click the clip you want all the selected clips matched against, and choose Shot Match to This Clip.
