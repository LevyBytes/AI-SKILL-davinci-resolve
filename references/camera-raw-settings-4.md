# Camera Raw Settings (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Gamma 2.4: A straightforward power-function gamma choice that broadcast work typically relies on. Gamma 2.6: The same plain power-function gamma, but the one ordinarily chosen for digital cinema projection. Rec. 709: A gamma curve suited to a Rec. 709 display. SLog: These Sony SLog gammas aren’t meant to be viewed directly; instead they hand you broad latitude for grading work — 14-stops by Sony’s own figures. 18% gray sits at 38%. SLog2: Compared with SLog, this one carries a half-stop offset so a wider dynamic range becomes possible. 18% gray sits at 32%. SLog3: A take on SLog that Sony calls “easier to grade.” 18% gray sits at 40%. As the Sony paper titled “Technical Summary for S-Gamut3Cine/S-Log3 and S-Gamut3/S-Log3” lays out, this gamma targets a more conventional log-encoded pipeline, with a curve close to — though not exactly matching — Cineon workflows. Linear: A plain linear gamma choice.

- Lift: Moves the media’s black point up or down, rescaling every midtone value that falls between it and the white point. However you set this control, none of the image data is lost — it stays available to pull back in later passes. The range is –100 to +100.
- Gain: Moves the media’s white point up or down, rescaling every midtone value sitting between it and the black point. Whatever you do with this control, the full image data remains and can be recovered in later passes. 0 is unity. The range is –100 to +100.
- Contrast: Pushing contrast higher pulls shadows down and lifts highlights, but midtones at 50 percent stay put. No matter how you set this control, all the image data survives and is recoverable in later passes. 0 is unity. The range is –100 to +100.
- Sharpness: A debayer-specific sharpening filter that lends the look of crisper detail. 20 is unity. The range is 0 to 100.
- Highlights: Pulling this parameter down makes it simple to claw back clipped highlight detail in high-dynamic-range media, blending the recovered highlights smoothly into the untouched midtones for a natural-looking outcome. 0 is unity. The range is –100 (minimum) through +100 (maximum).
- Shadows: Lets you brighten or darken shadow detail at will. Pushing this value up brings back shadow detail captured below 0 percent without disturbing the midtones. 0 is unity. The range is –100 (minimum) through +100 (very high).
- Color Boost: Lets you lift the saturation of weakly saturated regions in a natural way — what’s often called a vibrance operation. It can equally pull down saturation in those low-saturation regions. 0 is unity. The range is –100 (minimum) through +100 (very high).
- Saturation: Governs how intense the image’s colors appear. 0 is unity. The range is –100 (minimum) through +100 (very high).
- Midtone Detail: Push this parameter up and the contrast within high-edge-detail regions climbs, boosting the sense of sharpness — sometimes called definition. Drop it to a negative figure and low-detail regions soften while the high-detail areas are spared. 0 is unity. The range is –100 (minimum) through +100 (very high).
- Enable ICVFX: When you shoot VFX inside a virtual production workflow, the background LED wall lighting blends with the ordinary lighting falling on foreground people. Ticking this box lets you correct for that combined lighting.

LED Wall Kelvin: Set the LED wall’s color temperature here. Light Blend: Sets how the ordinary lighting and the LED wall lighting are proportioned against each other. At a value of 100 you get the ordinary lighting on its own (the same as having ICVFX mode disabled). At a value of 0 only the LED wall lighting remains.

### Use Camera Metadata

The most basic camera metadata controls on offer for exposure and color.

- Exposure: Raises or drops image lightness, measured in units tied to ASA values. Should your exposure change push image data past the highest white level, there’s no cause for concern — every bit of image data is kept and can be recovered in later passes. +800 is unity. The range is +1 to +65,535.
- Color Temp: Meant to shift the “warmth” of the image and tunable in degrees Kelvin. Lower figures compensate for “warmer” lighting, while higher figures compensate for “cool” lighting. +6500 is unity. The range is +2000 to +50,000.
- Tint: Surfaces only once White Balance is set to anything besides As Shot. Its job is to shift the image’s green-to-magenta balance, handy for shots with fluorescent tinting. Lower figures introduce green to offset magenta lighting, while higher figures introduce magenta to offset green lighting. 0 is unity. The range is –150 to +150.

### Sony Media and SLog

Sony’s in-house SLog gamma setting — which yields flat-contrast, wide-gamut image data that holds onto detail and leaves you plenty of room to adjust — turns up on a number of other Sony cameras too. Much as you would with clips shot in the ARRI ALEXA’s Log-C gamma, SLog clips have to be normalized: either through Resolve Color Management (RCM), through a hands-on tweak of color and contrast, or by laying on a LUT, all using the methods covered earlier. Sony puts forward two approaches when a LUT is involved. Should your end goal be Log media destined for film printing, a 1D LUT can convert SLog clips into the standard Cineon (or Log-C) curve. And if instead you intend to deliver a normalized format, a purpose-built LUT will carry out that conversion. To dig deeper, look online for Sony’s paper “SLog: A new LUT for digital production mastering and interchange applications.”
