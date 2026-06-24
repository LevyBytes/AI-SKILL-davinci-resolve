# Curves (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Curves

A capable curves interface on the Color page hands you controls for tuning color and contrast through the Custom Curves, plus an assortment of “Hue” or “HSL” curves that let you tackle more pinpointed adjustments to hue, saturation, and luminance in a number of ways.

### Introduction to Curves

You reach the Curves palette through one of the toolbar buttons sitting above the Center Palette panel of the Color page, and it carries six modes, each offering a different curve-based way of working an image’s color and contrast. Every curve lets you tune a customizable region of the picture, keyed to one of three things: image tonality (those zones running light or dark), hue (particular colors), or saturation (how intense the color is). You can adjust all of the curves with the pointer, or with knobs on the DaVinci Resolve Mini or Advanced control panel. Whenever you’re working in Resolve Color Management (RCM) or ACES, the Curves palette is color-space-aware. In practice that means each curve’s overall range fits the current clip’s overall data range better, whatever Timeline Color Space you happen to be in, across both SDR and HDR mastering. The upshot is curves adjustments that come more easily, land more precisely, and feel more consistent, whatever workflow you happen to be running. TIP: Every curve in DaVinci Resolve can act on the whole image, or be confined to just one portion of it as part of a secondary operation built from qualifiers, windows, imported mattes, or any mix of the three.

### Adjusting Curves Using the Mouse

For basic on-screen tweaking with the pointer — driven by your mouse, pen, or whatever input device you prefer — every Color curve in DaVinci Resolve relies on the controls below. Ways of adjusting curves through the on-screen interface:

- To add a control point: Click somewhere on a curve. Wherever the mouse sat when you clicked, a control point gets added, and the curve bends, where it must, to meet that new control point’s position.
- To add a control point without altering the curve: Keep the Shift key held and click anywhere on or near a curve. A control point lands on the curve wherever the pointer was when you clicked, yet the curve stays put.
- To make a control point snap onto the curve’s neutral diagonal: (Custom curve only) Keep the Option key held as you drag any control point on the curve. A diagonal line shows up marking the image’s neutral state, and the control point snaps onto it. Let go of the Option key and then press it once more afterward, and the diagonal guide line goes away.
- To remove a control point: Right-click any control point and it vanishes.
- To return one color channel curve to a fully neutral setting: To the right of that color channel’s intensity slider, click the reset button

there.

- To return every color channel curve at once: Up in the Curves palette’s upper right-hand

corner, click the Reset Custom Curve button. Out of the box, a control point governs the stretch of each curve lying between its two neighboring control points.

A control point’s adjustments act on the whole stretch of curve between adjacent control points. Up in the top screenshot, notice that the control point where the pointer sits governs the bigger part of the curve falling between the lower left-hand control point (present by default) and a user-created control point set up within the curve’s highlights. Down in the bottom screenshot, one more control point placed left of the one being moved narrows the area of curve that gets adjusted. Placing extra control points with care lets you make remarkably targeted adjustments to images via the Custom curves.

What this example drives home is how useful control points are for “locking off” stretches of a curve at a neutral or near-neutral position, so certain parts of an image stay unchanged even while you work other control points to make changes. NOTE: The HSL curves additionally carry an optional adjustment mode using Bezier curves, which those sections will get into.

### Sampling Images to Place Control Points on Curves

A further way to drop control points onto curves is to bring the pointer over to the Viewer and click to sample a color value, which sets a control point on whichever curve is currently open at the spot matching that value. This holds for Custom, Hue, and HSL curves.

### Clicking on a feature of the image

Creates a control point on the currently open curve

### Showing Picker RGB Values

As you drag the pointer across the Viewer hunting for a feature to sample, you can switch on a tooltip showing the RGB Value of the pixel beneath the pointer — right-click the Viewer and pick Show Picker RGB Value to flip this feature on and off. Switch it on and the Show RGB Picker Values In submenu inside the Viewer’s option menu offers a choice of displaying either 8or 10-bit tristimulus values.

Switch on Show RGB Picker Values and this color picker tooltip shows up

### Curves Histograms

Both the Custom curves and the HSL curves carry a histogram standing in for the input of the currently selected Correction node, handy for steering your adjustments. Through the Histograms submenu of the Curves palette’s Option menu you can switch these histograms off, or flip them between showing the node’s input and its output. Flip to Output and the histograms refresh to show the result of your adjustments — at the cost of seeing the image data the curve is actually acting on.

The Custom curves show a YRGB histogram:

A YRGB histogram analysis is what the histogram below the Custom Curves shows Every Hue or HSL curve carries a histogram analysis of whichever two color channels that Curve works on — say, to give three examples, saturation level set against hue, saturation level set against luminance, or saturation level set against saturation level. With Hue or HSL curves, these histograms make it simple to spot which stretches of the Curve controls will genuinely act on image data.

The histogram below the Hue vs Sat curve plots every saturation level at each value of hue

### Custom Curves

DaVinci’s Custom curves deliver smooth tuning of each clip’s Y, R, G, and B channels. Two areas split the Curves palette’s Custom curve mode: on the left the Curve Editor, on the right the Curve controls. The editor houses the actual Curve controls you reach for to adjust the image. The right-hand controls let you pick which curves you’re working and dial in their intensity.

Here the Custom curves build a gentle “S” curve adjustment, with four extra control points set down What the Custom curves are good for is making more tonally specific, channel-by-channel adjustments to an image than the Color Balance controls can manage. They’re also good for strange and wonderful stylistic moves through unusual tweaks to different combinations of color channels. Though the ganged Custom curves look like one curve control, the Custom curve editor is really laid out as a stack of overlaid curves, and the YRGB curves all turn up inside one editor. Out of the box, the Custom curves rest neutral as a diagonal line running from the image’s lower-left black point up through its upper-right white point.

The curve resting at its neutral diagonal, where nothing is being adjusted

Running left to right, the horizontal axis maps how the original image’s tonality spans out — black sitting at the left, white at the right — whereas the span of change you’re able to make is what the vertical axis maps. By dropping control points onto the curve’s surface and raising or lowering it at various regions, you’re effectively remapping a color channel’s original horizontal “input” value to whatever “output” value you like. Further controls turn up to the right of the curve editor itself. Across the top sits a row of buttons that let you pick the curve tied to an individual color channel for isolated tweaking, while a vertical stack of four sliders lets you dial in the intensity of each color channel’s curve.

Off to the curve editor’s right sit the channel-editing buttons together with the curve intensity sliders

### Editing the Top and Bottom Control Points of Curves

Curves can also be edited through the two default control points that the curve control begins with in the Curve Editor. The Black Point control (down at the lower-left) and the White Point control (up at the upperright) let you stretch and squeeze the video signal much as the Lift and Gain Master Wheel controls in the Color Wheels palette would.

### The Curve control at its original state

Here the Black and White Point controls are dragged rightward and leftward so as to stretch the signal

There are these ways to put the Black and White Point controls to use: Using the Black Point control: Drag this control upward and you make a lift adjustment that raises the signal’s black point. Drag this control rightward and you make a lift adjustment that lowers the signal’s black point. Using the White Point control: Drag this control downward and you make a gain adjustment that lowers the signal’s white point. Drag this control leftward and you make a gain adjustment that raises the signal’s white point.

### HDR Grading Using Curves

While reaching for various grading controls on the Color page to grade wide-latitude images bound for HDR output, you might find it handy to switch on the HDR mode of the node you’re on — right-click that node in the Node Editor and pick HDR mode from the contextual menu (offered only in Resolve Studio).

Switching a node into HDR mode by way of its contextual menu This setting reshapes that node’s controls so they operate across an expanded HDR range. In practical terms, this eases work on wide-latitude signals through controls that function by letting you adjust at various tonal ranges — Lift/Gamma/Gain, Custom Curves, Soft Clip, and so on among them.

### Enabling Editable Splines in the Custom Curves

With the Curve palette in Custom mode, picking Editable Splines from the option menu reveals Bezier spline handles on any selected control point, which let you fine-tune the curve more precisely as the need arises.

### Custom curve with editable splines enabled

NOTE: Take care with curve adjustments that turn too sharp, or with control points crowded too closely, since they can bring on unwanted contouring within the image, causing flattening or solarization in spots you might not intend.

### Adding Default Anchors to the Custom Curves

From the option menu of the Curve palette in Custom mode you can also pick Default Anchors to set three more control points on the curve, splitting it into five segments that act on the image’s shadows, low midtones, medium midtones, high midtones, and highlights.

### Custom curve with Default Anchors exposed

### Ganging and Unganging Custom Curves

Out of the box the Custom curves are ganged, so that a curve adjustment acts on a clip’s YRGB channels as one, giving an image-contrast change much like reaching for the Master Wheels in the Color Wheels palette. Make this kind of adjustment and raising contrast raises image saturation too, while lowering contrast lowers image saturation too. Since curves can be worked with finer specificity than the three Master Wheels allow, the YRGB curves let you make far subtler contrast adjustments than the Master Wheels alone. Switch ganging off and you unleash the full reach of the Custom curves on the image. Where the Color Balance controls each move all three color channels at once, the Curve controls let you work each channel on its own once Gang Custom Curves is switched off. To switch off Custom curve ganging: Click the Curve Edit button matching the curve channel you mean to edit. Clicking any Curve Edit button lifts that curve into focus so it’s simple to edit where curves overlap one another. Once one or more curves sits offset from the rest, you’re free to edit any curve by dragging its control points.

On the left you’ll find the Custom Curve Edit buttons, with the Gang button over on the right

To switch Custom curve ganging back on: Click the Gang button to the left of the Curve Edit buttons. Reaching each color channel by way of its own separate curve adjustment lets you craft smooth color-channel specific corrections — or, going the other direction, make wildly individual moves to conjure a broad range of creative effects.

Turning off curve ganging lets you independently adjust each curve TIP: With curve ganging switched off, the Luma curve lets you work the Y channel on its own — much like reaching for those Y-only Lift/Gamma/Gain knobs on the Micro, Mini, or Advanced Control Panels of DaVinci Resolve. Make this kind of adjustment and raising luma contrast brings a perceived drop in image saturation.

### Copying Custom Curves From One Color Channel to Another

Even once you’ve unganged the Custom curves, you can still echo one curve’s adjustments onto another: copy it using, from the Curve palette’s option menu, the “Copy to Red/Green/Blue” commands.

### Curve Intensity Sliders

To the right of the Curve Editor sit four Curve Intensity sliders, one per channel, letting you blend between the current curve’s effect on the clip and the image’s original state before you touched the curve. An Intensity left at its default of 100 has that curve press its full effect onto the image, while an intensity of 0 has that curve act on the image not at all. The Intensity sliders give you a simple route to “split the difference” between any curve adjustment and whatever state the image was in before.

Pulling the Curve Mix slider down eases how strongly that curve’s adjustment bears on the image.

### YSFX Sliders

Each of the Custom curves (Y’, R, G, and B) carries a vertical YSFX slider up in the Curve Editor’s upper left-hand corner, letting you invert any or all color channels by whatever amount you like, for conjuring different kinds of stylized effects.

Image with the Luma channel modified using the vertical YSFX slider Just like every other adjustment on the Color page, YSFX can be paired with Power Windows or HSL qualification to confine channel inversions to certain portions of the image for creative ends.

### Soft Clip

Four sliders beneath the Custom curves’ Curve controls make up the Soft Clip controls, handing you an interface for tuning highlight and shadow soft clipping either across the board, with Ganging on, or channel by channel. The Soft Clip controls are meant for clip-by-clip tuning, as against the Generate Soft Clip LUT settings, which let you fix one soft-clipping setting across the whole program. For more on the Soft Clip LUT setting, turn to Chapter 4, “System and User Preferences.”

High and Low Soft Clip controls within the Curves palette What soft clipping does is put a “knee” on any clipping happening at the image’s upper or lower extremes, and it can quickly take the edge off any unpleasantly harsh loss of detail that comes from blowing out the highlights or crushing the shadows too hard. In the example below, the top screenshot has had its highlights deliberately blown out by overdoing the highlight contrast. As you can tell, the edges of the clipped area carry no detail. The bottom screenshot shows the same image with soft clipping raised across all three color channels. The outcome pulls back detail, squeezing the highlights so the tops of each color channel come back inside the allowable range.

Using High Soft Clip to pull highlight details into the viewable range

### Ganging and Unganging Soft Clip Controls

You can apply soft clipping to all three color channels at once by switching on the Ganging control (on by default), or you can switch Soft Clip ganging off to tune each channel on its own. As an example, soft clipping per channel can help when you’re legalizing RGB out-of-gamut errors on channels that overshoot or undershoot the QC standards you work to. To switch off Soft Clip ganging and tune soft clipping per color channel: Click whichever channel control button matches the color channel you mean to edit, then drag the sliders until the adjustment is where you want it. To switch Soft Clip ganging back on: Just left of the Soft Clip channel controls, click the Ganging control. TIP: Lay too much soft clipping onto individual color channels and you may push an unwanted color tint into the matching highlights or shadows of an image. To steer clear of that, work the soft clipping parameters with ganging on so all three color channels clip equally.

### Soft Clip Controls

Ganged or not, soft clipping for each color channel is steered through two sliders plus two more parameters.

### High

What the High Clipping Point slider does is let you set the top signal level past which the signal gets clipped. Every pixel above the clipping level gets pinned to the clipping level.

By default, measured against the DaVinci Resolve internal video scopes, the High Clipping Point lands at a digital level of 1023. Drag this slider leftward and the image’s highlights clip at a lower level, which gives lower, dimmer maximum levels.

### Selecting and adjusting the high clip

### RGB Parade displays the clipped image

At its default spot no clipping happens, and image data you drive past 1023 on the internal scopes is held and carried through the image processing pipeline to the nodes that follow. As an example, across the next two screenshots, the highlights in the top one are blown out by lifting the gain sharply in Node 1. In the bottom screenshot, a later adjustment in Node 2 drops the gain and reclaims every one of those previously clipped values.

The image is clipped using the Gain control in Node 2

Whatever image data got clipped in Node 1 is reclaimed in Node 3 by dropping the Gain control. This shows how deliberately clipped data is preserved. That said, drag the High Clip slider leftward anywhere along a node tree — even by one single digit — and every bit of image data above the new clipping threshold is thrown away from that node onward. In the example below, the High Clip slider in Node 1 gets lowered. The result is that all the clipped image data is thrown away. So when Node 2 drops the gain, there’s no image detail left to reclaim, and all three channels show flattening.

Drop the High Clip slider on Node 1 and every bit of image data sitting above the fresh High Clip threshold is discarded for good. No node further along can bring that clipped data back.

### High Soft

What the High Soft slider sets is the threshold, beneath the clipping point, where highlights start compressing ahead of hard clipping. At unity, no soft clipping happens. Raise this value and more and more of the clipped highlight values get compressed rather than clipped, giving softer, more pleasant “glowing” highlights. IMPORTANT: Image data clipped “in camera” isn’t necessarily reclaimable with the Soft Clip controls, though there may be some held-back overhead in the super-white highlights of Y’CbCr-encoded video data.

### Low

What the Low Soft Clipping Point slider does is let you set the bottom signal level where the signal clips. Measured against the DaVinci Resolve internal video scopes, this defaults to a digital level of 0. Drag this slider rightward and the image’s shadows clip at a higher level — the result being lifted minimum levels, plus a lower-contrast image whose shadows turn lighter (milky, even).

### Low Soft

What the Low Soft slider sets is the threshold, above the minimum clipping point, where shadows start compressing ahead of hard clipping. At unity, no soft clipping happens. Drag this slider rightward and more and more of the clipped shadow values get compressed rather than clipped, giving a softer, more pleasant rolloff in the shadows.

### The HSL Curves

By way of three sets of Hue curves — along with further curves for Lum vs. Sat, Sat vs. Sat, and Sat vs Lum — you can make different kinds of curve-based changes to the image. Where the Custom curves let you adjust an image’s color channels by tonality (boosting the Red channel in the highlights while dropping it in the shadows, say), the Hue curves let you adjust the hue, saturation, or luma of elements in an image by their hue. Curves controls including six-vector selection and bezier handle button As an example, you might reach for the Hue vs. Sat curve to selectively drop the saturation of everything blue while raising the saturation of everything red. These curves let you make adjustments akin to those from HSL qualification, but with one crucial distinction. A curve adjustment is mathematically smoother than the matte-limited adjustment of an HSL qualifier, so it can sometimes be simpler to make specific changes that blend cleanly into the rest of the image, free of the edge artifacts on qualified keys that can sometimes wreck a seamless result. On the flip side, drawing more distinct boundaries between separate elements is often easier with HSL qualification. Only time and experience will tell you which tools suit which situations best.

Right–Original image, Left–how the Hue vs. Sat curve above has reworked that same image Where the Custom curves default to a diagonal position with lower left as the black point and upper right as the white point, Hue and Sat curves are instead flat. With the Hue vs. Hue/Sat/Lum curves, the curve’s horizontal span from left to right stands for the whole range of possible hues, from red through green through blue and then wrapping back around to red. Because the range of hues wraps smoothly from the left edge to the right, changes touching the curve near these curves’ left boundary loop seamlessly over to the right boundary, and the other way around, so the curve’s left and right sides always travel together (as the screenshot above shows). IMPORTANT: With Hue curves, whatever range of hue you isolate using control points is always relative to the RGB input wired into that node. So if you shift a shirt’s hue from blue to red with Hue vs. Hue and then want to lift that same shirt’s saturation with the Hue vs. Sat curve inside the same node, you’ll need to set control points on the very same range of blue for both curves.

### Image Sampling for Hue and Sat Curves

DaVinci Resolve gives you one more way to work the Hue curves. Open up whichever curve tab you like — be it Hue vs. Hue, or Hue vs. Sat, or Hue vs. Lum, or else Lum vs. Sat, or Sat vs. Sat — then click, or click and drag, across any range of pixels inside the Viewer area; doing so samples that region’s hues and/or image tonality and drops three control points onto the currently open curve matching the range of color and contrast you sampled.

### Additional Controls in the Hue and Sat Curves
