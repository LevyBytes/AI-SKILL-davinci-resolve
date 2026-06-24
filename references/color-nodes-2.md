# Color Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

background. It additionally switches on the Estimation Options sliders, through which you can further pinpoint and flag regions where fringing occurs. That makes hand-tuning the fix straightforward, with the Scale and Edge controls letting you treat Red/Cyan, Green/Purple, and Blue/Yellow fringing one at a time.

### Common Controls

Settings Tab The Inspector's Settings tab is repeated across the other Color nodes as well. Full coverage of these shared controls appears at this chapter's end, within the “The Common Controls” section.

### Color

A grouping nested under Fusion's Color tools that opens up an assortment of color-processing utilities.

### Auto Gain [AG]

### The Auto Gain node

### Auto Gain Node Introduction

On its own, the Auto Gain node remaps an image's tonal range, driving the darkest and brightest pixels to values you specify. Out of the box, the darkest pixels are sent to black, the brightest to white, and everything between is stretched so the tonal range fills evenly. It comes in handy for evening out lighting differences, working with low-contrast footage, or previewing the entire color range of float images (though the viewer's View Normalized Image option usually serves that purpose better).

### Inputs

A pair of inputs sit on the Auto Gain node, the input and the effect mask. Input: The orange input takes the main 2D picture that the auto gain works on. Effect Mask: The blue input expects a mask shape built from polylines, simple primitive forms, paint strokes, or bitmaps originating in other tools. Wiring a mask here keeps the auto gain adjustment to just the pixels lying inside that mask. The effect mask is applied to the tool once the tool has finished processing.

### Basic Node Setup

Much as with many 2D image-processing nodes, the Auto Gain node is fed a 2D image from something like a Loader node or the MediaIn1 pictured below. From its output, the node tree carries on into a further 2D image-processing node or a Merge node.

An Auto Gain node applied to a MediaIn1 node

### Inspector

### Auto Gain controls

### Controls Tab

Within the Controls tab live the handful of main controls you need to tailor the AutoGain operation. NOTE: As the input image shifts over time, the levels of the result shift along with it. Say a bright object exits an otherwise dark shot: the scene that's left abruptly brightens, since the remaining darker values get stretched toward white. The same holds for abrupt depth shifts whenever Do Z is in play; objects already present can be pushed nearer or farther as a close or distant object enters or exits the scene. Do Z Tick the Do Z checkbox to extend the Auto Gain effect onto the Z or Depth channels. This proves useful for aligning the ranges of one Z-channel with another, or for inspecting a float Z-channel within the RGB values. Range The Range control fixes the image's black point and white point. Every tonal value in the image is rescaled to sit inside that range.

### Example

Build a horizontal gradient using the Background node. Make one color dark gray (RGB Values 0.2). Make the other color light gray (RGB Values 0.8). Drop in an Auto Gain node and put the Low value at 0.0 and the High value at 0.5. As a result, the brightest pixels are dropped to 0.5 while the darkest pixels are driven to black. Everything else among the pixel values scales between those two bounds.

### Common Controls

Settings Tab This same Inspector Settings tab recurs on the other Color nodes too. A thorough walkthrough of these shared controls sits at the end of this chapter, within the “The Common Controls” section.

### Brightness Contrast [BC]

### The Brightness Contrast node

### Brightness Contrast Node Introduction

The Brightness Contrast node tweaks an image's gain, brightness, contrast, gamma, and saturation. How the controls are laid out reflects the sequence in which their operations run. To illustrate, gamma runs ahead of contrast yet behind gain. Brightness Contrast can also be undone via the Forward and Reverse buttons, so a color correction already applied can be rolled back later down the chain. For the best outcome here, image processing ought to run in 32-bit floating point.

### Inputs

A pair of inputs sit on the Brightness Contrast node, the input and the effect mask. Input: The orange input takes the main 2D picture that the brightness contrast works on. Effect Mask: The blue input expects a mask shape drawn from polylines, simple primitive forms, paint strokes, or bitmaps coming out of other tools. Wiring a mask here keeps the Brightness Contrast adjustment to just the pixels lying inside that mask. The effect mask gets applied to the tool once the tool has been processed.

### Basic Node Setup

As with so many 2D image-processing nodes, the Brightness Contrast node is handed a 2D image from a source such as a Loader node or the MediaIn1 shown below. Its output extends the node tree onward into another 2D image-processing node or a Merge node.

A Brightness Contrast node applied to a MediaIn1 node

### Inspector

### Brightness Control controls

### Controls Tab

Inside the Controls tab you'll find every main control needed to tailor the brightness and contrast operations. Color Channels (RGBA) By default the filter works across the R, G, B, and A channels. To filter channels selectively, click each channel button to toggle it on or off. NOTE: Do not confuse this with the RGBA checkboxes sitting under the common controls. Because the node weighs these picks before it processes the image, switching a channel off makes the node bypass that channel during processing, which speeds up rendering the effect. By contrast, the channel controls on the Common Controls tab take hold after the node has done its processing. Gain The gain slider multiplies the pixel value. A Gain of 1.2 turns a pixel reading R0.5 G0.5 B0.4 into R0.6 G0.6, B0.48 (i.e., 0.4 \* 1.2 = 0.48) and leaves black pixels untouched. Since Gain bites harder on higher values than on lower ones, its impact peaks across the image's midrange and upper range. Lift Where Gain pivots the color values about black, Lift pivots them about white. Each pixel value is multiplied by this control's setting. A Lift of 0.5 turns a pixel reading R0.0 G0.0 B0.0 into R0.5 G0.5, B0.5 and leaves white pixels untouched. Since Lift bites harder on lower values than on higher ones, its impact peaks across the image's midrange and lower range. Gamma Settings above 1.0 lift the Gamma (mid-gray), while settings below it pull Gamma down. This node's behavior is non-linear, and the existing black or white points stay completely untouched. Pure gray tones feel it the most.

Contrast Contrast measures the spread between the bright and dark regions. Raising this slider boosts the contrast, driving color out of the midrange toward black and white. Lowering it draws the image's colors back in toward midrange, narrowing the gap between its darkest and brightest pixels. Brightness Whatever the Brightness slider reads is added onto the value of every pixel in the image. This control acts linearly on an image, so it hits all pixels the same way no matter their value. Saturation Reach for this control to raise or lower how much Saturation the image carries. A saturation of 0 strips all color, leaving a grayscale image. Low and High In certain ways this range control resembles the Gain control. Pinning Low at 0.0 and trimming the High value down from 1.0 produces the same outcome as raising the gain. High values are multiplied by the reciprocal of the high value. (e.g., a high of 0.75 means each pixel is multiplied by 1/0.75, or 1.3333). Keeping the high pinned at 1.0 while lifting the low amounts to inverting the image colors, raising the gain, then inverting once more. That shoves more of the image toward black while leaving the whites entirely alone. Direction Forward runs all values as normal. Reverse essentially flips every value. Clip Black/White The Clip Black and Clip White checkboxes trim off out-of-range color values that can crop up in an image while processing at floating-point color depth. Out-of-range colors fall under black (0.0) or over white (1.0). These checkboxes do nothing on images processed at 8-bit or 16-bit per channel, since such images can't hold out-of-range values. Pre-Divide/Post-Multiply Ticking the Pre-Divide/Post-Multiply checkbox divides the image's pixel values by the Alpha values ahead of the color correction, then multiplies them by the Alpha value again afterward. This guards against producing illegally additive images when you color correct material with premultiplied Alpha channels.

### Common Controls

Settings Tab You'll see the Inspector's Settings tab on other Color nodes as well. These shared controls get a detailed treatment toward the close of this chapter, in the “The Common Controls” section.

### Channel Booleans [Bol]

### The Channel Booleans node

### Channel Booleans Node Introduction

The Channel Booleans node runs an assortment of mathematical and logical operations across an image's channels. It operates by letting one image's channels reshape another image's channels. Should no foreground input be present, any option that calls for the foreground's color channels falls back on the background input's color channels instead. NOTE: Watch out for a similarly named Channel Boolean (3Bol), a 3D node meant for remapping and altering the channels of 3D materials. For 2D channel work, reach for the Channel Booleans (spelled with an “s”) node (Bol).

### Inputs

In the Node Editor the Channel Booleans node carries four inputs, yet only the orange Background input must be filled. Background: This orange input takes a 2D image that the foreground input image then modifies. Effect Mask: The blue effect mask input wants a mask shape made from polylines, simple primitive forms, paint strokes, or bitmaps out of other tools. Wiring a mask here keeps the channel booleans adjustment to just the pixels lying inside that mask. Foreground: The green foreground input takes a 2D image that serves to modify the background input image. Matte: The white matte input lets you fold external mattes into the foreground and background operations.

### Basic Node Setup

As a remarkably versatile tool, the Channel Booleans node lends itself to a wide array of uses. In the example that follows, the z-depth channel is copied out of the foreground input (green) and into the background image (orange).

A Channel Booleans set to copy from foreground to background

### Inspector

### Channel Booleans controls

### Color Channel Tab

The Color Channels tab splits its controls into a pair of columns. The left-hand side lists target channels for whatever image feeds the orange background input. Over on the right, a drop-down menu lets you decide whether to alter the BG image using its own channels (the BG suffix after the list name) or using channels from an image wired into the node's green foreground input (the FG suffix in the drop-down list). Operation This menu picks which mathematical operation acts on the chosen channels. The available options run as follows: Copy Duplicates a value out of one color channel and into another. For instance, to build a matte, route the foreground red channel into the Alpha channel of the background.

- Add: Adds the color values of one color channel onto another channel.
- Subtract: Takes the color values of one color channel away from another color channel.
- And: Runs a logical AND across the color values between one color channel and another. Typically the

foreground image strips bits out of the background image's color channel.

- Or: Runs a logical OR across the color values between one color channel and another. Typically the foreground

image contributes bits to the background image's color channel.

- Exclusive Or: Runs a logical XOR across the color values between one color channel and another. Typically the

foreground image toggles bits in the background image's color channel.

- Multiply: Multiplies a color channel's values together. The image looks darkened by this

since the values span 0 to 1. White, valued at 1, leaves the result unchanged. Gray, valued at 0.5, yields a darker image, that is, one half as bright.

- Divide: Divides a color channel's values. The image looks lightened by this as the values span 0 to 1.
- Maximum: Weighs the two images against each other and keeps the maximum, or brightest, value from each.
- Minimum: Weighs the two images against each other and keeps the minimum, or darkest, value from each.
- Negative: Flips the FG input to produce a negative version of the image.
- Solid: Solid drives a channel up to its full value of 255. Handy for raising the Alpha to full value.
- Clear: Clear drops a channel to a value of zero. Handy for wiping the Alpha.
- Difference: Difference takes the greater color values of one color channel away from the lesser values of another color channel.
- Signed Add: Signed Add removes regions sitting below mid-gray and contributes regions sitting above mid-gray, which helps when crafting effects from embossed gray images.

To Red, To Green, To Blue, To Alpha Each of these menus stands for one of the output image's four color channels. Through the drop-down menu you pick which source-image channel feeds that output channel. By default it copies the channels off the foreground channel. You may choose any of the four color channels, plus a handful of auxiliary channels such as Z-buffer, saturation, luminance, and hue.

### Inspector

### Aux Channel Inspector

### Aux Channel Tab

This tab holds a row of menus through which you assign a source to each of the output image's auxiliary channels. Enable Extra Channels Tick the Enable Extra Channels checkbox and the Channel Booleans node becomes able to emit images carrying channels past the standard RGBA. With it on, the rest of the Aux Channels tab controls can route data into those auxiliary channels.

### Examples

When you want to push one image's Alpha channel into its own color channels, point the red, green, and blue channels at Alpha BG. Put the Operation on Copy. To pull the Alpha channel out of a different image, switch the operation type to Alpha FG. To swap an image's current Alpha channel for the Alpha of another image, pick “Do Nothing” on To Red, To Green, and To Blue and “Alpha FG” on To Alpha. Feed the image holding the Alpha into the foreground input of the Channel Booleans node. Set Operation: “Copy.” That very operation is also offered in the Matte Control node. To fold any mask into an image's Alpha channel, pick “Do Nothing” on To Red, To Green, and To Blue and “Matte” on To Alpha. Feed the mask into the foreground input of the Channel Booleans node. Set Operation: “Copy.” To take another image's red channel pixels away from the blue channel, pick “Do Nothing” on To Red and To Green and “Red FG” on To Blue. Feed the image holding the red channel you're subtracting into the foreground input of the Channel Booleans node. Set Operation: “Subtract.”

### Common Controls

Settings Tab The Inspector's Settings tab turns up on other Color nodes too. A full account of these shared controls waits at the end of this chapter, under the “The Common Controls” section.

### Color Corrector [CC]

### The Color Corrector node

### Color Corrector Node Introduction

The Color Corrector node is an all-in-one color node offering histogram matching, equalization, hue shifting, tinting, and color suppression. Its controls are spread across four tabs: Correction, Ranges, Options, and Settings.

### Inputs

Within the Node Editor the Color Corrector node carries four inputs. Input: This orange input is the sole mandatory connection. It takes a 2D image to color correct. Effect Mask: The optional blue input wants a mask shape made from polylines, simple primitive forms, paint strokes, or bitmaps out of other tools. Wiring a mask here keeps the color corrector adjustment to just the pixels lying inside that mask. The effect mask gets applied to the tool once the tool has been processed.

Match Reference: The green input takes an image to serve as the reference when histogram matching. Match Mask: Like an effect mask, this optional white input will accept any mask. This mask, however, marks out the region to match while a Histogram Match runs. It gives you more shape freedom than the Inspector's built-in Match rectangle.

### Basic Node Setup

In keeping with many 2D image-processing nodes, the Color Corrector node receives its 2D image from a source such as a Loader node or the MediaIn1 displayed below. Its output extends the node tree onward to another 2D image-processing node or a Merge node.

### Inspector

A Color Corrector node applied to a MediaIn1 node

### Color Corrector controls

### Correction Tab Colors Menu

The principal Correction tab breaks down further into four correction-method types: colors, levels, histogram, and suppress. Pick one from the menu atop the Correction tab and that method's controls show up. The Color method gets a thorough description below.

Range This menu sets which tonal range this tab's color correction controls act on. Its choices are Shadows, Midtones, Highlights, and Master, with Master being the default and reaching the whole image. Whatever range you pick carries over across the Colors, Levels, and Suppress sections of the Color Corrector node. Edits made to the image on the Master channel land on the image after whatever edits you made on the Highlight, Midtone, and Shadow ranges. NOTE: The controls operate independently per color range. To illustrate, moving the Gamma control while in Shadows mode leaves the Highlights-mode Gamma control's value untouched. Every control stands alone and is applied on its own. Color Wheel The color wheel paints a visual picture of the Hue and Saturation edits you make, along with any tint laid on the image. You can edit directly by dragging the color indicator, or by typing values into the numeric boxes beneath the color wheel. The tint shows up in the color wheel's color indicator, which conveys the tint's hue and strength. For Highlight, the color indicator wears a black outline. Midtones and Shadows get gray color indicators. The Master color indicator is black too, but a white M at its center sets it apart from the rest. The mouse can place a given range's color indicator only while that range is the one selected. For instance, you can't move the Highlight color indicator while the Master range is active. Holding the Command or Ctrl key as you drag this indicator lets you fine-tune by dulling the control's responsiveness to mouse motion. Holding the Shift key pins the color indicator's travel to one axis, so you can hold the effect to tint alone or strength alone. Tint Mode This menu picks the speed-versus-quality algorithm that carries out the hue and saturation edits. Better is the default, though on larger images a quicker method may be the wiser pick. Hue This slider duplicates the Hue control found beneath the color wheel. It makes nudging the value with the mouse in small steps easier. The Hue control gives you a way to rotate the hue of the image (or the chosen color range) around the color spectrum. Its value runs effectively from -0.1 to 1.0, standing for the angle of clockwise rotation. A value of 0.25 equals 90 degrees (90/360) and would shift red toward blue, green to red, and onward. You can shift hue by dragging the slider, typing a value straight into the text control, or hovering the mouse over the color wheel's outer ring and dragging up or down. That outer ring always displays the shifted colors set against the original colors shown at the wheel's center.

Saturation This slider mirrors the Saturation control sitting beneath the color wheel. It eases nudging the value in small steps with the mouse. You reach for the Saturation control to dial the strength of the color values up or down. A saturation of 0 yields gray pixels stripped of any color component, while a value of 1.0 leaves the input image's chroma component as it was. Higher values push out oversaturated values carrying a heavy color component. You can dial saturation by dragging the slider, typing a value straight into the text control, or sweeping the mouse left and right along the outer ring of the color wheel control. Channel This menu applies to the Histogram, Color, and Levels sections of the Color Corrector node. Pick the red channel and the controls in each mode touch only the red channel, and so on for the others. Because the controls are independent, switching over to blue wipes out none of the edits you made to red, green, or Master. Each channel keeps its own animation and edits apart from the rest. The menu merely governs which controls are on display. Contrast Contrast describes how wide the gap runs between the bright and dark areas. Turn this slider up and contrast climbs, forcing color out of the midrange toward black and white. Turn it down and the image's colors gather toward midrange, shrinking the gap between its darkest and brightest pixels. Gain The Gain slider scales the pixel value by multiplication. A gain of 1.2 converts a pixel reading R0.5 G0.5 B0.4 to R0.6 G0.6, B0.48 (i.e., 0.4 \* 1.2 = 0.48), all while black pixels stay wholly untouched. Because Gain weighs on higher values more than lower ones, it hits hardest across the image's midrange and upper range. Lift Whereas Gain pivots the color values about black, Lift pivots them about white. Each pixel value is scaled by this control's setting. A Lift of 0.5 converts a pixel reading R0.0 G0.0 B0.0 to R0.5 G0.5, B0.5, all while white pixels stay wholly untouched. Because Lift weighs on lower values more than higher ones, it hits hardest across the image's midrange and lower range. Gamma Settings over 1.0 lift the Gamma (mid gray), while settings under it bring Gamma down. This node behaves non-linearly, and the existing black or white points go entirely untouched. Pure gray tones take the brunt of it. Brightness Whatever the Brightness slider reads is added onto every pixel's value in your image. This control hits an image linearly, so it lands the same on all pixels no matter their value. Reset All Color Changes Clicking this button restores every color control in this section to its default value.

### Correction Tab Levels Menu

As noted, the principal Correction tab splits into four correction-method types: colors, levels, histogram, and suppress. Choose Levels from the menu and you gain the ability to remap an image's white and black points, with a Gamma control on hand for the midtones. A histogram lays out the image's tonal distribution to steer your edits. The Level method is laid out in detail below.

### Color Corrector Levels controls
