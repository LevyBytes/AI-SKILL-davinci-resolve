# Fusion (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Histogram Display A histogram is a graph showing how the scene’s color values are spread out. You read the graph left to right, where the values on the far left stand for the scene’s darkest colors and those on the far right stand for the brightest. As more pixels in an image share the same or a near-identical value, that section of the graph rises higher. Because luminance is figured per channel, the red, green, and blue channels each get their own histogram, and combining all three yields the Master Histogram. To stretch the histogram vertically, hover the mouse pointer within the control and drag it upward to zoom in or downward to zoom out. Display Selector Toolbar Sitting at the top of the histogram, the Display Selector toolbar gives you a way to switch individual parts of the histogram display on and off. Rest the mouse pointer over a button and a tooltip appears explaining what that button does.

- Input Histogram: Switches on or off the showing of the input image’s histogram.
- Reference Histogram: Switches on or off the showing of the reference image’s histogram.
- Output Histogram: Switches on or off the showing of the histogram taken from the post-colorcorrected image.
- Corrective Curve: Flips on or off a spline display that lets you see precisely how the automatic color

corrections, made with a reference image, are changing the image. It comes in handy while you balance luminance across the input and reference images. Histogram Controls Running along the bottom of the histogram display, these controls let you tune the input image’s histogram by compressing or shifting the ranges of whichever color channel is chosen. You adjust them by dragging the triangles below the histogram display left and right. Move the High value leftward (lowering it) and the histogram leans toward white, pushing the image distribution that way. Doing the same with the Low value works the other direction, driving the image distribution toward black. Output Level Clipping can be applied to the image through the Output Level control, which compresses the histogram. Lowering the High control drops pixel values across the image, sliding white pixels down toward gray and gray ones down toward black. Pushing the Low control toward High reverses that, lifting the darkest pixels toward white. Were the low value set to 0.1, any pixel at 0.0 would become 0.1 instead, with the remaining values rising to make room for the shift. The clearest way to see the result is to watch how the output histogram shown above changes. Reset All Levels Clicking this button returns every control in the Levels section to its default setting.

### Correction Tab Histogram Menu

Setting the menu to Histogram generates a histogram display from the input image. When a reference image is supplied as well, that reference image gets its own histogram shown too. This tab’s controls mainly serve to match one image against another, by way of the Equalize or Match modes of the dColor Corrector.

dColor Correction in Histogram mode Channel With this menu you choose which color channel — or the Master channel — to select and show the histogram for. Histogram Display A histogram is a graph showing how color values are distributed throughout the scene. Reading from one side to the other, the leftmost values represent the scene’s deepest darks while the rightmost ones represent its brightest tones. Wherever many pixels in an image carry the same or a similar value, that portion of the graph climbs higher. Since luminance gets computed for each channel separately, red, green, and blue all maintain individual histograms, and the three together make up the Master Histogram. Scaling the histogram up and down is done by holding the mouse pointer inside the control and dragging up to zoom in or down to zoom out. Display Selector Toolbar Found across the top of the histogram, the Display Selector toolbar offers a means of turning components of the histogram display on or off. Pause the mouse pointer over a button and its tooltip describes the button’s purpose.

- Input Histogram: Turns the showing of the input image’s histogram on or off.
- Reference Histogram: Turns the showing of the reference image’s histogram on or off.
- Output Histogram: Turns on or off the showing of the histogram drawn from the

post-color-corrected image.

- Corrective Curve: Switches a spline display on or off so you can see exactly how the automatic color

corrections, applied through a reference image, are altering the image. It proves handy as you even out luminance between the input and reference images.

### Correction Tab Suppress Menu

Color Suppression gives you a way to strip an unwanted color component out of the image. The Color Wheel control resembles the one in the node’s Colors section, except this version has six controls ringing it, one for each specific color around the wheel. To knock down a color in the chosen range, drag the control standing for that color in toward the center of the color wheel. The nearer that control sits to the center, the more strongly its color is suppressed from the image.

dColor Corrector Suppression controls Suppression Angle The Suppression Angle control turns the controls on the suppression wheel so you can home in on one particular color. Reset All Suppression Clicking this control sets the suppression colors back to 1.0, which is their default.

### Ranges Tab

Inside the Ranges tab live the controls that define which of an image’s pixels count as shadows and which count as highlights. The midrange is always whatever pixels weren’t already swept into the shadows or the highlights. Range This menu picks the tonal range shown in the viewers. They make it easier to see the pixels within that range. With the Result menu option chosen, the image the color corrector puts in the viewers is the color-corrected image. That’s the default. Pick one of the other menu options and the display flips to a grayscale image marking which pixels belong to the selected range. The white pixels are the ones counted as part of the range, while black pixels lie outside it. Choosing Shadows, for instance, would render pixels regarded as shadows white and everything else black. Mid-gray pixels are only partway in the range and won’t take the full effect of any color adjustments aimed at that range.

dColor Corrector Ranges controls Channel This tab’s Channel menu lets you inspect the range of one specific color channel. Out of the box, Fusion shows the luminance channel whenever the color ranges are being examined. Spline Display You pick the ranges by working the spline handles. Four spline points exist, each carrying a single Bézier handle. The upper two handles mark where the shadow and highlight ranges begin, while the lower two mark where the range ends. Falloff is governed through the Bézier handles. The midtones range carries no controls of its own, since its span is understood as whatever falls in between the highlight and shadow ranges. The X and Y text controls beneath the spline display let you key in precise coordinates for whichever Bézier point or handle is selected. Output the Range You See Now as Final Render Ticking this checkbox makes the monochrome view of the range shown in the viewers become the final render. Ordinarily the Color node sends out the complete RGBA image, even when the node was set to show one of the color ranges in the view. This control lets you put the dColor Corrector node to work generating a range’s matte for use as an effect mask elsewhere among the nodes. Preset Simple/Smooth Ranges These two buttons return the spline ranges to either Smooth (default) or Simple (linear) settings.

### Options Tab

The Options tab carries a handful of very important processing operations, among them an easy fix for color correcting premultiplied Alpha channels. dColor Options controls Histogram Proxy Scale How much precision is used when histograms are built and computed is set by the Histogram Proxy Scale. Lower values mean greater precision, whereas higher ones give a coarser, more generalized histogram. Process Order This menu decides whether tweaks to the image’s gamma happen before or after any changes applied to the image’s levels. Apply Mask Inverted Turning on the Apply Mask Inverted option flips the tool’s entire mask channel. That mask channel is the merged result of every mask either connected to or created within a node.

### Settings Tab

Clipping Mode This option governs how edges get treated during domain of definition rendering. It matters most for nodes such as Blur, which can need samples from parts of the image beyond the current domain.

- Frame: Frame is the default; it makes the node’s domain of definition span the image’s full frame on its own, which in effect disregards the current domain of definition. Where the upstream DoD comes in smaller than the frame, whatever frame area is left over reads as black/transparent.
- Domain: Choose Domain and the node honors the upstream domain of definition while its effect is applied. In cases where the node uses a large filter, this can produce unwanted clipping.
- None: Choose None and no clipping of the source image happens whatsoever. So any data the node’s effect needs that would ordinarily fall beyond the upstream DoD reads as black/transparent.

Other nodes carry a duplicate of this Inspector Settings tab as well. Full descriptions of these shared controls appear at this chapter’s end under “The Common Controls.”

### User Defined Metadata Variables in Paths, Expressions, and Scripts

Fusion has gained a new variables system. The feature extends Fusion’s already capable scripting layer and makes it more flexible still. There are three sides to it. 1 Setting it up in the Fusion Preferences. 2 Putting variables to work inside Expressions. 3 Putting variables to work in Saver paths.

### Getting started

A fresh category, Variables Map, now sits in preferences. You’ll find it under Global and Comp Preferences. You can author and edit variables globally, covering every comp, or on a per‑comp basis. They’re also allowed to hold expressions and to reference other variables.

### The Fusion Variables Map preference

Within an expression, Global Variables are reachable through fu.vars.[variable name] and Comp Variables through comp.vars.[variable name] in expressions. Both Global and Comp variables can be used in a Saver to build a save location or a file name. Inside a Saver’s Filename control, type %{name}. That call pulls up the list of categories on offer — among them custom variables (drawn from Prefs), clip metadata, and Resolve metadata (over on the Fusion Page). In a Saver, Input Metadata variables take the form %{metadata.metadataname}, while Resolve variables take the form %{resolve:Resolve Metadata}

Using a mapped variable in a text field. Within expressions, metadata coming from an upstream clip is reachable with fu.vars.metadata. [name] or comp.vars.metadata.[name] On top of that, on the Fusion Page you can pull metadata from Resolve inside an expression using fu.vars.resolve[“Name”]. Example fu.vars.resolve[“Timeline Name”].

### Improved Lens Distort Tool

Checkerboard calibration has been added to the Lens Distort tool, and the tool can now run with GPU acceleration.

### Motion Vector Layers Generated from Optical Flow

An update has come to Fusion’s Optical Flow tool, which now emits motion vectors as separate layers. The vector channels that the Optical Flow tool produces are now fully compatible with Fusion’s multi‑layer pipeline. Thanks to this change, tools that once relied on vector auxiliary channels can now reach the new Vector and Back Vector layers. Tools able to take in motion vector layers are:

- Smooth Motion
- Vector Denoise
- Vector Transform
- Vector Warp
- TimeSpeed (Flow Interpolation Mode)
- TimeStretcher (Flow Interpolation Mode)

### Improved Guides and Rulers

In Fusion 21 the Guides and Rulers gained upgrades: locked persistence, guide presets, and improved snapping.

### MediaIn Nodes Show Clip Name

Under Fusion 21, MediaIn nodes will display the clip name rather than showing MediaIn#.

### Open Keyframes and Spline Editor as a New Window

When you need extra room, the Fusion Keyframe and Spline editors can now be popped out into a fresh resizable window by clicking the Undock icon in the Keyframes or Spline toolbar.

Undocking the Keyframe editor into it’s own resizable window.

### Nudge Spline Keyframes

Within the Spline editor, the comma (,) and period (.) keys let you nudge a Spline keyframe to the left or right respectively.

### Up to 2x Faster Relight Tool

Fusion’s Relight tool now runs as much as twice as fast as it did before.

### Up to 6x Faster Depth Map Tool

The Depth Map tool runs much faster now, gaining as much as a sixfold speed boost over the earlier version.

### Support for Remote Monitoring of Fusion Previews

You can now stream Fusion Previews live through DaVinci Resolve’s Remote Monitoring tools and application.

### SpeedWarp [SPDw]

### The SpeedWarp node

### SpeedWarp Node Introduction

SpeedWarp is an AI-driven retiming node that studies the motion across existing frames to build fresh in-between frames, delivering smooth slow-motion free of stutter. Drawing on DaVinci’s neural network, SpeedWarp can rebuild intricate motion that ordinary interpolation or frame blending would usually smear or warp.

### Inputs

Input: The 2D image you want the SpeedWarp to act on is fed into the orange input.

### Basic Node Setup

A straightforward case has the SpeedWarp node retiming the video clip wired into it (A001\_), and then handing that retimed video off to the MediaOut node.

### A simple SpeedWarp setup

### Inspector

### SpeedWarp controls

### Controls Tab

Speed The speed wheel sets how fast the Speed Warp output runs. It sits at 1.0 by default, where nothing changes. Drop the speed to 0.5 to cut the output speed in half; raise it to 2.0 to double it, and so forth. Delay The delay shifts where the Speed Warp output begins. A delay of 10.0 pushes the output 10 frames forward, while a delay of -10.0 pushes it 10 frames backward. Mode Pick the SpeedWarp’s mode.

- Faster: Faster processing for a quicker result.
- Better: Higher quality at a performance cost.

### Common Controls

Transform and Settings Tabs The Transform and Settings tabs that remain are shared across many nodes. You’ll find their descriptions under “The Common Controls” at this chapter’s end.
