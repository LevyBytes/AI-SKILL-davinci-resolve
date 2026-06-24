# Color Nodes (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Range Working just like the Range menu does when Color is the Menu choice, the Range menu here governs which tonal band this tab's color correction controls act upon. You can set it to Shadows, Midtones, Highlights, or Master, with Master being the default that touches the whole image. Whatever range you pick stays in force across the Colors, Levels, and Suppress sections of the Color Corrector node. Whatever you do to the image on the Master channel lands after any edits applied to the Highlights, Midtones, and Shadows ranges. NOTE: Every color range carries its own separate controls. As an illustration, nudging the Gamma control while you're in Shadows mode leaves the Gamma control's value for Highlights mode untouched. Each control stands alone and takes effect on its own. Channel With this menu you choose and view the histogram for any single color channel or for the Master channel. Histogram Display Think of a histogram as a graph showing how color values are spread across the scene. You read it left to right, the values farthest left standing for the scene's deepest darks and the values farthest right for its brightest tones. Wherever more of an image's pixels share the same or a close value, that part of the graph climbs higher.

Because luminance gets computed channel by channel, the red, green, and blue channels each carry their own histogram, and stacking them together yields the Master Histogram. To stretch the histogram up and down, set the mouse pointer within the control and drag it upward to zoom in or downward to zoom out. Display Selector Toolbar Sitting atop the histogram, the Display Selector toolbar gives you a way to switch parts of the histogram readout on and off. Rest the mouse pointer on a button and a tooltip pops up explaining what that button does.

- Input Histogram: Switches the input image's histogram readout on or off.
- Reference Histogram: Switches the reference image's histogram readout on or off.
- Output Histogram: Switches on or off the readout of the post-colorcorrected image's histogram.
- Corrective Curve: Flips on or off a spline that shows precisely how the auto color

corrections applied using a reference image are affecting the image. That comes in handy while you're evening out luminance across the input and the reference images. Histogram Controls Lined up along the foot of the histogram readout, these controls reshape the input image's histogram, squeezing or sliding the selected color channel's ranges. You adjust them by dragging the triangles under the histogram readout leftward and rightward. Dragging the High value toward the left (lowering its value) tilts the histogram toward white, sliding the image's distribution that way. The Low value works the same but in reverse, driving the image's distribution toward black. Output Level The Output Level control lets you clip the image, squeezing the histogram. Pulling the High control down drops pixel values across the whole image, easing white pixels down to gray and gray ones on toward black. Moving the Low control up toward High flips this, sliding the darkest pixels up toward white. Were the low value pegged at 0.1, any pixels reading 0.0 would jump to 0.1 instead, with other values rising to absorb the shift. The clearest way to picture the result is to watch how the output histogram up above changes. Reset All Levels A click of this button returns every control in the Levels section to its default.

### Correction Tab Histogram Menu

With the menu switched to Histogram, the input image gets rendered as a histogram display. Supply a reference image as well and its histogram shows up too. This tab's controls mostly serve to match one image against another, drawing on either the Equalize or the Match modes of the Color Corrector. Channel With this menu you choose and view the histogram for any single color channel or for the Master channel.

### Color Correction in Histogram mode

Histogram Display Think of a histogram as a graph showing how color values are spread across the scene. You read it left to right, the values farthest left standing for the scene's deepest darks and the values farthest right for its brightest tones. Wherever more of an image's pixels share the same or a close value, that part of the graph climbs higher. Because luminance gets computed channel by channel, the red, green, and blue channels each carry their own histogram, and stacking them together yields the Master Histogram. To stretch the histogram up and down, set the mouse pointer within the control and drag it upward to zoom in or downward to zoom out. Display Selector Toolbar Sitting atop the histogram, the Display Selector toolbar gives you a way to switch parts of the histogram readout on and off. Rest the mouse pointer on a button and a tooltip pops up explaining what that button does.

- Input Histogram: Turns the readout of the input image's histogram on or off.
- Reference Histogram: Turns the readout of the reference image's histogram on or off.
- Output Histogram: Turns on or off the readout for the histogram of the post-colorcorrected image.
- Corrective Curve: Toggles a spline whose job is to make plain exactly how the auto color

corrections applied using a reference image are affecting the image. That comes in handy while you're evening out luminance across the input and the reference images. Float Images and Histogram Equalization or Matching Running the Histogram Match or Equalize methods on a float image converts the output image's color depth to 16-bit integer. Since two-dimensional histograms cope poorly with the wide dynamic range that float images carry, these operations always fall back to 16-bit integer processing.

Histogram Type Every one of these menu choices triggers a distinct kind of color correction operation.

- Keep: Keep leaves the image untouched, with the reference histogram disregarded.
- Equalize: Picking Equalize tweaks the source image so that every color value within it is

equally represented—which amounts to leveling the histogram so the image's spread of colors grows more uniform.

- Match: The Match mode reshapes the source image off the reference image's histogram. Its job is making two shots whose lighting and exposure differ end up looking alike.

Once chosen, the Equalize and Match modes expose the controls below.

- Match/Equalize Luminance: How hard the Color Corrector node leans on the image's luminance distribution is governed by this slider. At zero (the default), matching and equalization hit each color channel on its own, leaving luminance—the three color channels combined—alone. Give this control a positive value while equalizing and the input image's luminance distribution gets flattened ahead of any color equalization. Give it a positive value with the correction mode on Match and the input's luminance values are matched to the reference before any correction touches the R, G, and B channels. The Luminance and RGB controls can stack their effects, and as a rule you don't crank both to full (1.0) at once.
- Lock R/G/B: Tick this checkbox and color matching hits every color channel uniformly. Leave it unticked and a separate set of controls appears for each channel.

Equalize/Match R/G/B Whether you've gone with Equalize or Match mode decides what this control gets named. Use the slider to dial back how strongly the image is corrected for equalizing or matching. Set it to 1.0 and the Equalize or Match runs at full strength, while lower settings temper the outcome. Precision The color fidelity used while sampling the image to build the histogram is set by this menu. 10-bit yields better fidelity than 8-bit, and 16-bit yields better fidelity than 10-bit. Smooth Correction Color equalization and matching jobs frequently bring on posterization, which happens because the image's gradients get stretched or squeezed until the dynamic range between colors falls short of showing a clean transition. This control can soften the correction curve, mixing a portion of the original histogram back into the result so the transition comes out smoother. Snapshot Match Time A click of this button freezes a snapshot of the current reference histogram, banking its present state in memory. Skip snapshotting the reference histogram and it refreshes frame by frame. That can produce flickering and phasing in the correction as the node strains to match a shifting source against a shifting reference.

Release Match A click of this button drops the histogram's current snapshot and goes back to the live reference input. Reset All Histogram Changes Pressing this button wipes out every change made to the histogram, restoring the controls to their defaults and putting the mode back on Keep.

### Correction Tab Suppress Menu

Color Suppression gives you a way to strip an unwanted color element out of the image. Its Color Wheel control resembles the one in the node's Colors section, except this one is ringed by six controls, each standing for one particular color around the wheel. To knock back a color within the chosen range, drag the control for that color in toward the wheel's middle. The nearer that control sits to the center, the harder that color gets suppressed from the image.

### Color Corrector Suppression controls

Suppression Angle The Suppression Angle control spins the controls around the suppression wheel so you can home in on one specific color. Reset All Suppression A click of this control returns the suppression colors to 1.0, their default value.

### Ranges Tab

Within the Ranges tab sit the controls that define which of an image's pixels count as shadows and which count as highlights. The midrange is always worked out as whatever pixels aren't already swept into the shadows or the highlights.

### Color Corrector Luminance controls

Range Use this menu to pick which tonal range the viewers display. They make the pixels in the range easier to see. Choose the Result menu option and the color corrector shows the color corrected image in the viewers. That's the default. Pick any of the other menu options and the display flips to a grayscale image marking which pixels belong to the chosen range. White pixels stand for those counted as inside the range, and black pixels fall outside it. Picking Shadows, for example, would paint pixels deemed shadows white and pixels that aren't shadows black. Mid gray pixels sit only partway inside the range and won't catch the full force of any color tweaks aimed at that range. Channel This tab's Channel menu lets you inspect the range of one particular color channel. Out of the box, Fusion shows the luminance channel whenever the color ranges get examined. Spline Display You select the ranges by working the spline handles. Four spline points exist, each carrying one Bézier handle. The pair up top mark where the shadow and highlight ranges begin, while the pair at the bottom mark where the range ends. The Bézier handles let you steer the falloff. The midtones range gets no dedicated controls, since its span is read as the gap separating the shadow range from the highlight one. Below the spline display, the X and Y text controls let you key in exact coordinates for whichever Bézier point or handle you've chosen. Output the Range You See Now as Final Render Tick this checkbox and the monochrome range shown in the viewers gets sent out as the final render. As a rule the Color node puts out the full RGBA image even when it's been left displaying one of the color ranges in the view. This control opens the door to using the Color Corrector node to build a range's matte for use as an effect mask elsewhere. Preset Simple/Smooth Ranges These two buttons let you reset the spline ranges to either Smooth (default) or Simple (linear) settings.

### Options Tab

The Options tab holds a handful of weighty processing operations, among them a tidy fix for color correcting premultiplied Alpha channels.

### Color Corrector controls

Pre-Divide/Post-Multiply Choosing this option divides the color channels by the Alpha value ahead of the color correction. Once the color correction is done, the color values get re-multiplied by the Alpha to yield a correctly additive image. That matters a great deal during an additive merge or when handling CG images built with premultiplied Alpha channels. Histogram Proxy Scale How precise the creating and calculating of histograms is gets decided by the Histogram Proxy Scale. Lower settings mean greater precision, while higher ones turn out a coarser, more general histogram. Process Order This menu lets you decide whether tweaks to the image's gamma take effect before or after any edits to the image's levels.

### Common Controls

Settings Tab The Inspector's Settings tab shows up in other Color nodes as well. These shared controls get a thorough write-up at this chapter's close, in the "The Common Controls" section.

### Color Curves [CCv]

### The Color Curves node

### Color Curves Node Introduction

For carrying out Lookup table (LUT) color manipulations, the Color Curves node is a spline-driven node. Every color channel gets its own separate spline. You can animate or dissolve the effect, and it can be brought to the image through the RGB, YUV, YIQ, CMY, or HLS color spaces.

You can scale the Color Corrector's LUT view with the + and - keys on the numeric keypad. The color curves LUT has full support for out-of-range values—that is, pixels whose color values run above 1.0 or below 0.0. Should you need finer precision while adjusting the controls, the splines on show in this LUT view can also be reached from the Spline Editor.

### Inputs

Three inputs come with the Color Curves node in the Node Editor. Input: Standing as the lone mandatory connection, this orange input. It feeds in a 2D image that the color curves act upon. Effect Mask: The optional effect mask input takes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input confines the color curves adjustment to just the pixels falling inside the mask. An effect mask gets applied to the tool once it has been processed. Reference Image: The optional green input serves to connect a second 2D image usable for reference matching. Match Mask: This optional white input takes any mask, much as an effect mask does. This mask, though, marks out the area to match during a Match. Shape-wise it gives you more leeway than the Inspector's built-in Match reference rectangle.

### Basic Node Setup

Like a great many 2D image-processing nodes, the Color Curves node takes in a 2D image such as a Loader node or the MediaIn1 pictured below. Its output carries the node tree onward by wiring into a further 2D image-processing node or a Merge node.

### Inspector

A Color Curves node applied to a MediaIn1 node

### Color Curves controls

### Controls Tab

Two sections split up the color curves' Controls tab. Up in the Inspector's top half live the curves and LUT controls. The lower half is given over mainly to matching the reference image. Mode The Mode choices switch among Animated and Dissolve modes. No Animation is the default mode, where curve adjustments stay static. Setting the mode hands each channel a change spline, so the color curve can be animated across time. Dissolve mode is for all intents obsolete and ships purely for compatibility's sake. Color Space The LUT view's splines stand for color channels drawn from an assortment of color spaces. Red, Green, and Blue is the default. This menu's choices let a different color space be picked. Below is a thorough rundown of the color spaces on offer here:

- RGB (Red, Green, Blue): Working in the RGB color space, Fusion has most of its nodes and displays read an image's primary channels as Red, Green, and Blue.
- YUV (Luma, Blue Chroma, and Red Chroma): PAL video's analog broadcast relies on the YUV color space. In years past this format saw frequent use for color correcting images, owing to how familiar it was to a great many video engineers. Each pixel gets spelled out by its Luminance, Blue Chroma, and Red Chroma components.
- HLS (Hue, Luminance, and Saturation): Within the HLS color space, every pixel gets spelled out by its Hue, Luminance, and Saturation components.
- YIQ (Luma, In Phase, and Quadrature): NTSC video's analog broadcast relies on the YIQ color space. Far scarcer than YUV, this format is almost never met with in production. Each pixel gets spelled out by its Luminance, Chroma (the in-phase or red-cyan channel) and Quadrature (magenta-green) components.
- CMY (Cyan, Magenta, and Yellow): More usual in print though it is, the CMY format turns up often in computer graphics out of other software packages. Each pixel gets spelled out by its Cyan, Magenta, and Yellow components. CMY is nonlinear.

Color Channels (RGBA) The Color Channel controls let you choose which channel's spline is open for editing right now. These controls' labels shift to mirror the channel names belonging to the current color space. As a rule they read as Red, Green, and Blue. Should the Color Curves node be running in YUV color space, they read as Y, U, and V instead. These controls don't pen the node's effect to one particular channel. All they pick is whether that channel's spline can be edited. Most often you reach for these controls to make certain that adding or shifting points on one channel's spline doesn't accidentally disturb a different channel's spline. Spline Window A conventional curve editor for each RGBA channel is what the Spline Window shows. Depending on which color channels you've selected above, these splines can be edited one by one or together as a set. The spline starts off as a linear range, running from 0 in/0 out down at the bottom left up to 1 in/1 out at the top right. At that default, a color comes out at the same value as the output. Drop a point into the middle at 0.5 in/0.5 out and lift it, and you brighten the image's mid color. The spline curves grant fine command over color ranges, so targeted tweaks can land without disturbing other color values.

In and Out The In and Out controls let you fine-tune a chosen point's exact values. To alter a value, pick a point and key in the in/out values you want. Eyedropper (Pick) Click the Eyedropper icon—also known as the Pick button—and grab a color off an image in the display to have control points set automatically on the spline for the chosen color. Drawn with a triangular shape, the new points can shift only up and down (where a point is locked, only its Out value can change). Points land solely on enabled splines. To drop points on just one channel, switch the other channels off before you make the pick. White balancing an image is one place this technique pays off. Reach for the Pick control to grab a pixel from the image that ought to read as pure gray. Tune the points that turn up so the Out value is 0.5, recoloring the pixels gray. Use the contextual menu's Locked Pick Points option to free points made with the Pick option, turning them into ordinary points. Reference Inside the Reference section sit controls that manage matching to sample patches of the connected reference image.

- Match Reference: The Match Reference button drops points onto the curve to match an image wired into the green reference image input. How many points get used to match the image rides on the Number of Samples slider underneath.
- Sample Reference: A click of the Sample Reference button samples the background image's center scanline and builds a LUT out of its color values. How many points get used to match the sampled scanline rides on the Number of Samples slider underneath.
- Number of Samples: How many points serve to match the curve against the range within the reference image is set by this slider.
- Show Match Rectangle: Tick this checkbox to put a rectangle in the viewer marking the patch of the reference image drawn on during the match process. The match rectangle bears only on the outcome of the Match Reference operation. The Sample reference always runs off the image's center scaling.
- Match Center: Repositioning the match rectangle to sample a different patch when matching is what the X and Y parameters let you do.
- Match Width: Width controls the width of the match rectangle.
- Match Height: Heigh controls the height of the match rectangle.
- Pre-Divide/Post-Multiply: Ticking this checkbox has the image's pixel values divided

by the Alpha values ahead of the color correction, then re-multiplied by the Alpha value afterward. This helps head off illegally additive images, especially around the fringes of a blue/green key or while handling 3D-rendered objects.

### Common Controls

Settings Tab The Inspector's Settings tab shows up in other Color nodes as well. These shared controls get a thorough write-up at this chapter's close, in the "The Common Controls" section.

### Color Gain [Clr]

### The Color Gain node

### Color Gain Node Introduction

Within the Color Gain node sit options for tuning the image's gain, gamma, saturation, and hue. Plenty of the controls the Color Gain node hands you also turn up in the Color Corrector node, yet this plainer node may render faster. What sets the Color Gain node apart from the Color Corrector is its balance tab controls. With them you can adjust how the colors get tinted across the highs, mids, and lows.

### Inputs

Two inputs come with the Color Gain node: one feeding the main image and the other an effect mask. Input: Standing as the lone mandatory connection, this orange input. It feeds in a 2D image that the color gain acts upon. Effect Mask: The optional blue effect mask input takes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input confines the color gain adjustment to just the pixels falling inside the mask. An effect mask gets applied to the tool once it has been processed.

### Basic Node Setup

Like a great many 2D image-processing nodes, the Color Gain node takes in a 2D image such as a Loader node or the MediaIn1 pictured below. Its output carries the node tree onward by wiring into a further 2D-image processing node or a Merge node.

A Color Gain node applied to a MediaIn1 node

### Inspector

### Color Gain controls

### Gain Tab
