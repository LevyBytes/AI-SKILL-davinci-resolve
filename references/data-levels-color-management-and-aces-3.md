# Data Levels Color Management And Aces (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- None: With this choice, Input DRT Tone Mapping is switched off. The Input to Timeline Color Space conversion receives no tone mapping whatsoever, which yields a plain 1:1 mapping into the Timeline Color Space.
- Simple: Works well when transforming color from HDR down to SDR.
- Luminance Mapping: Behaves like DaVinci, yet delivers greater precision whenever every clip's Input Color Space

sits within one standards-based color space — for instance Rec. 709 or Rec. 2020.

- DaVinci: Here the transform is tone mapped with a gentle luminance roll-off across the shadows and

highlights, plus measured desaturation of pixel values in the darkest and brightest regions of the picture. It works especially well for wide-gamut camera media and serves as a strong choice when combining footage shot on several cameras.

- Saturation Preserving: This choice carries a gentle luminance roll-off through the shadows and highlights, yet achieves this while keeping dark shadows and bright highlights saturated, making it a worthwhile pick for colorists who prefer pushing color aggressively. Because excessive saturation in the brightest parts of a picture can appear unnatural, though, two parameters are surfaced to deliver some automatic desaturation that the user can tune.

Sat. Rolloff Start: Lets you define a threshold, measured in nits (cd/m2), where saturation begins to fall away together with highlight luminance. Beginning of the rolloff. Sat. Rolloff Limit: Lets you define a threshold, measured in nits (cd/m2), where the picture becomes fully desaturated. End of the rolloff.

### Output DRT Tone Mapping

This control becomes available only when the Resolve Color Management presets menu sits on Custom Settings. For workflows that call for converting one color space into a second whose gamut is far wider or far narrower, an extra cluster of settings has been introduced that can assist in automating the necessary growth or shrinkage of image data toward an attractive outcome. Picking from the choices in the Output DRT drop-down menu will shrink or stretch your image data as required throughout the Timeline to Output Color Space transformation that RCM applies when a timeline is being monitored or rendered, so that the end result either avoids clipping or makes fuller use of the new color space. The intent here is not to deliver your finished grade. Instead, it aims to hand you a quicker launching point, whenever you require one, before you move on to your own deeper grade of the outcome. Below are a few illustrations of the purposes the Gamut Mapping controls of RCM can serve:

1 When you're handling high-dynamic-range log-encoded media and your working output happens to be Rec. 709 while you edit, switching on Gamut Mapping allows RCM to apply saturation and tone mapping so you get a more instantly appealing picture whose highlight detail stays unclipped. 2 When you're handling standard-dynamic-range log-encoded media and your working output is an HDR format, switching on Gamut Mapping allows RCM to apply saturation and tone mapping to stretch the picture's highlights to HDR intensity, yielding an image with stronger immediate punch on HDR displays.

(Before/After) Gamut Mapping applied so high‑dynamic-range footage is fitted automatically within the Rec. 709 color space. Within the Output DRT (Display Rendering Transform) drop-down menu you'll find these choices.

- None: The Timeline to Output Color Space conversion gets no tone mapping at all, producing a plain 1:1 output with neither softness nor rolloff. Any image data beyond the gamut gets clipped.
- Simple: Works well when transforming color from HDR down to SDR.
- Luminance Mapping: Behaves like DaVinci, but offers more precision when every clip resides in a single

standards-based color space, such as Rec. 709 or Rec. 2020, applied to both the Timeline and Output.

- DaVinci: This choice tone maps your output using a gentle luminance roll-off through the shadows and

highlights, along with measured desaturation of pixel values in the darkest and brightest regions of the picture. It was engineered to yield smooth, natural-looking highlights and shadows as you stretch and compress the values of your footage, with no extra settings required. It works especially well for wide-gamut camera media and serves as a strong choice when mixing footage from several cameras.

- Saturation Preserving: This choice carries a gentle luminance roll-off through the shadows and highlights to ward off clipping. It manages this while keeping dark shadows and bright highlights saturated, making it a useful pick for colorists who prefer pushing color a touch harder. Because excessive saturation in the brightest parts of a picture can appear unnatural, though, two parameters are surfaced to deliver some automatic desaturation that the user can tune. Sat. Rolloff Start: Lets you define a threshold, measured in nits (cd/m2), where saturation begins to fall away together with highlight luminance. Beginning of the rolloff. Sat. Rolloff Limit: Lets you define a threshold, measured in nits (cd/m2), where the picture becomes fully desaturated. End of the rolloff.
- RED IPP2: With this choice you can apply RED IPP2 tone mapping when outputting to an SDR format like Rec. 709; two settings are surfaced for shaping how the output behaves. Output Tone Map: Sets which variety of tone mapping gets applied to what you output. Options include: None, Low, Medium, and High. Highlight Roll Off: Determines the variety of highlight rolloff applied to keep clipping at bay. Choose from None, Hard, Medium, Soft, and Very Soft. HDR peak nits: With a slider you select the peak nit value you intend to tone map toward. Defaults to 10,000 nits.

### Use Inverse DRT for SDR to HDR Conversion

This control becomes available only when the Resolve Color Management presets menu sits on Custom Settings. A device rendering transform (DRT) generally comes into play when high dynamic range media is being converted into a color space/mastering standard of lower dynamic range. Building a color transform running from SDR to HDR is therefore an "inverse" procedure that stretches the dynamic range of SDR media up to HDR standards. The mechanism behind this is that levels sitting at 100 nits are remapped to the ceiling value chosen for the Timeline Working Luminance parameter, while every other image level is tone mapped deliberately to hand you a solid launching point for grading SDR media into an HDR program. There's a second purpose for this setting as well. Once it's switched on, you're able to output Rec. 709 clips whose color matches the input exactly, with no compression applied to the highlights. NOTE: Switching on "Use Inverse DRT for SDR to HDR Conversion" can amplify noise in imported SDR media that contains broad flat stretches of bright color.

### Use White Point Adaptation

This control runs a chromatic adaptation transform to compensate for differing white points across color spaces.

- Clear this box if your goal is simply to see the input color space's white point untouched within the output color space. As an example, when you'd like to use a P3-D60 mastered clip inside a P3-D65 timeline purely for reference.
- Tick this box to run the chromatic adaptation transform that converts the input white point so it aligns with the output color space's white point. As an example, when you'd like a P3-D60 mastered clip to intercut with other footage mastered in a P3-D65 timeline.

NOTE: This control becomes available only when the Resolve Color Management presets menu sits on Custom Settings.

### Color Space Aware Grading Tools

Within DaVinci Resolve version 17, both Resolve Color Management and ACES let "color space aware" palettes — including the new HDR palette — carry controls that behave consistently regardless of which color space the source footage came from or which Timeline Color Space you happen to use. Additional palettes, the Qualifier and Curves palettes among them, turn color space aware once you tick the "Use Color Space Aware Grading Tools" checkbox inside the Color Management panel of the Project Settings (which is enabled by default). While color space aware grading tools are in use, you ought not enable HDR Mode on the node you're currently grading.

- For the Qualifier palette, this lets Qualifiers build high-quality keys exactly as you'd anticipate, regardless of the source footage's color space or the Timeline Color Space in play.
- For the Curves palette, this lets each curve's overall span line up better with the present clip's full data range, which makes curve tweaks simpler and more precise.

NOTE: This control becomes available only when the Resolve Color Management presets menu sits on Custom Settings.

### Apply Resize Transformations In

While Resolve Color Management is active, a fresh "Apply Resize Transformations In" Project Setting shows up in the Color Management panel as long as the Resolve Color Management presets menu sits on Custom Settings. This setting lets you pick which color space handles your resizing operations. Resizing normally happens in Linear, yet some specialized workflows gain from resizing within other color spaces, so this option lets you select whichever suits best. The choices available are:

- Timeline: Carries out every resizing operation in the Timeline Color Space.
- Log: Employs a Log Color Space when resizing. Helpful for sidestepping artifacts in particular high-contrast

pictures, like titles and star fields.

- Linear: Generally yields the strongest results across most SDR media.
- Linear Mapped: Generally yields the strongest results across most HDR media.
- Gamma: Included should you ever find a use for this option.
- Gamma Mapped: Generally yields the strongest results when blending SDR media with

wide gamut and log-encoded footage on a single timeline.

### Graphics White Level

The "Graphics white level" setting lets you set a common ceiling level in nits (cd/m2) for titles, generators, and certain effects that produce color. Adjusting this setting lets you shift the ceiling level of every DaVinci Resolve-generated title, generator graphic, and effect simultaneously to suit varying mastering and output needs.

### Display HDR On Viewers If Available

Switch this checkbox on when your computer displays and operating system can support HDR output. Doing so permits the Viewers to present genuine HDR, in line with what your computer monitor can do.

### HDR Mastering Is For (Studio Version Only)

When you own a DeckLink 4K Extreme 12G or an UltraStudio 4K Extreme video interface, DaVinci Resolve 12.5 and later can transmit the metadata required to display HDR video signals correctly on display devices over HDMI 2.0a once you switch on the "Enable HDR metadata over HDMI" checkbox within the Master Project Settings.

The Enable HDR metadata over HDMI option inside the Master Project Settings lets you transmit HDR by way of HDMI 2.0a. Once that's done, the Color Management panel of the Project Settings holds a setting labeled "HDR mastering is for X" through which you declare the output, in nits, that gets embedded as metadata into the outgoing HDMI stream, ensuring the connected display reads it correctly. Whatever value you declare ought to align with what your display anticipates.

The "HDR mastering is for" setting lets you embed metadata for HDR output by way of HDMI 2.0a.

### Resolve Color Management and the Fusion Page

Switching RCM on additionally lets the Fusion page manage clip color on its own. Pictures emitted by MediaIn nodes are converted automatically into Linear color space, which is the favored color space for executing high-quality compositing work. Putting the LUT menu of every Viewer on the Fusion page to Managed guarantees you're viewing the picture in Rec. 709, so the image appears correct to the artist despite the fact they're genuinely working within the Linear color space. Every MediaOut node then turns the picture back into the timeline color space to pass it on to the Color page. With RCM disabled, color on the Fusion page must be handled by hand, either through the Source Color Space and Source Gamma Space settings on each MediaIn node, or via the CineonLog or FileLUT nodes within your node tree. For additional detail on the way color management influences the Fusion page, and why the Linear color space is preferred for compositing, refer to Chapter 76, "Controlling Image Processing and Resolution."

### Ability to Bypass Color Management Per Clip

Right-clicking a clip within the Thumbnail Timeline of the Color page reveals a "Bypass Color Management" setting beneath the Input Color Space and Input Gamma submenus that let you specify a clip's color traits. Selecting this option so it shows a check lets you remove that clip from color management entirely, in case you'd rather handle that clip by hand using LUTs, the Color Space Transform node, or by grading it manually. The Bypass Color Management entry shown per clip within the Thumbnail Timeline contextual menu

### Exporting Color Space Information to QuickTime Files

When you render QuickTime files out of the Deliver page, color space tags get written into each file according to either the Timeline Color Space (when Resolve Color Management is off) or the Output Color Space (when Resolve Color Management is on). A pair of settings within the Advanced Settings of the Render Settings let you decide how color space metadata gets written into your output for the media formats that support it, "Color Space Tag," and "Gamma Tag." These start at "Same as Project," which lines up with whichever Output Color Space is currently active for the project. Where the Color Space Tag and Gamma Tag controls live inside the Render Settings

### Color Management Using ACES

The ACES (Academy Color Encoding Specification) color space was built to turn scenereferred color management into something practical for high-end digital cinema workflows. ACES additionally simplifies pulling high-precision, wide-latitude image data out of raw camera formats, so that highquality image data is preserved from capture all the way through color grading, and to deliver high-quality data for broadcast viewing, film printing, or digital cinema encoding. To put it simply, the way ACES operates is that each camera and capture device is profiled to produce an IDT (Input Device Transform) defining how footage from that device gets converted into the ACES color space. The ACES gamut was engineered to be wide enough to span all visible light, carrying over 25 stops of exposure latitude. ACES has thus been crafted to remain future-proof, accounting for progress in image capture and distribution. In parallel, an RRT (Reference Rendering Transform) takes whatever data a given image format's IDT supplies and converts it into image data that is standardized, highly precise, and wide in latitude, which afterward passes through an ODT (Output Device Transform). Each ODT setting matches a particular standard of monitoring and output, and lays out how to convert the data inside the ACES color space accurately into that display's gamut so the image is rendered as faithfully as possible in every scenario. The RRT and ODT always work together.

### Image Data

### IDT

### Encode ACES to ACEScc / ACEScct

### DaVinci Image Processing

### Decode ACEScc / ACEScct back to ACES

### ODT

### RRT

### Monitoring

### Disable ODT for Deliver

### Page Output

### ACES signal and processing flow

Through the ACES color space and the specification of an IDT and an ODT, you're able to bring in footage from any capture device, grade it on a calibrated display, output it toward any destination, and hold onto the color fidelity of the graded picture.

For more information on ACES see the ACES Central Website.

### Setting Up ACES in the Project Settings Window

The Color Science drop-down within the Color Management panel of the Project Settings offers four parameters that let you configure DaVinci Resolve for the ACES workflow:

- Color science is: This drop-down menu lets you select either DaVinci ACES or DaVinci ACEScc color science, which turns on ACES processing throughout DaVinci Resolve.

ACEScc: Pick DaVinci ACEScc color science to lay a standard Cineon-style log encoding over the ACES data ahead of its processing by DaVinci Resolve. This well-defined shared encoding lets ASC CDL values travel between systems that share the same ACEScc encoding. Following processing, a reverse encoding is applied so ACES linear data can be output. ACEScct: A variant of ACEScc that introduces a roll-off at the toe of the picture distinct from the encoding of ACEScc, so that color correction lift moves "feel" closer to how they behave with film scans and LogC encoded images, which makes raising the picture's darkest values and producing milky shadows easier — a result that's tricky with ACEScc. Following processing, a reverse encoding is applied so ACES linear data can be output.

- ACES Version: After you've selected one of the ACES color science options, this drop-down opens up so you can choose which ACES version you'd like to use. Your choices are ACES 1.0.3, ACES 1.1, ACES 1.2, ACES 1.3, or ACES 2.0 (the latest version).
- ACES AMF: With Aces 1.3 or newer, you're able to choose an ACES AMF file for application. Further detail appears in the ACES AMF section below.
- ACES Input Device Transform: This drop-down menu lets you select which IDT (Input Device Transform) applies to the predominant media format you're working with. DaVinci Resolve presently supports these IDTs:

ACEScc/ACEScct/ACEScg: One standardized transform per ACES standard listed here. ADX (10 or 16): Film-density encoding transforms in either 10-bit or 16-bit integer form, meant for when you're handling film scans that began life within an ACES workflow. The aim of this transform is to keep the look differences between distinct film stocks intact. ALEXA: Configures color management for every ARRI ALEXA camera. BMD Film/4K/4.6K: Configures color management for Blackmagic Design cameras. Canon 1D/5D/7D/C200/C300/C300MkII/C500/C700: Configures color management for Canon cameras. DCDM: This IDT converts X'Y'Z'-encoded media at a gamma of 2.6. DCDM (P3D65 Limited): Operating on X'Y'Z'-encoded media held at a 2.6 gamma, this IDT also lays down a hard clip specifically into a P3 gamut tied to a D65 white point. DRAGONcolor/2 and REDgamma3/4/REDlogFilm combinations: Assorted combinations of the DRAGONcolor, REDgamma, and REDlogFilm settings are offered for legacy RED workflows. P3-D60: Converts RGB-encoded image data set to a D60 white point, intended for a P3-compatible monitor running at a D60 white point. P3-D65: Converts RGB-encoded image data set to a D65 white point; intended for a P3-compatible monitor running at a D65 white point. P3-D65 (D60 sim.): Converts RGB-encoded image data set to a D65 white point; built to emulate a P3-compatible monitor at a D60 white point while the actual display sits at D65. P3-D65 ST2084 (108/1000/2000/4000 nits): Converts a picture that fits the P3 color gamut, drawing on the SMPTE standard PQ (ST.2084) tone curve toward High Dynamic Range (HDR) post-production. Across four separate peak luminance ranges, three settings come provided; which suits depends on the topmost white level of whichever display authored the media. Provisional standards already cover HDR displays whose peak luminance hits 1000 nits, 2000 nits, and 4000 nits. For Kodak laser projection, a 108 nits setting comes provided.

P3-D65: Converts RGB-encoded image data set to a D65 white point, intended for a P3-compatible monitor running at a D65 white point. P3-D65 ST2084 (1000/2000/4000 nits): Converts a picture that fits the P3 color gamut, drawing on the SMPTE standard PQ (ST.2084) tone curve toward High Dynamic Range (HDR) postproduction. Across three separate peak luminance ranges, three settings come provided; which suits depends on the topmost white level of whichever display authored the media. Provisional standards already cover HDR displays whose peak luminance hits 1000 nits, 2000 nits, and 4000˛nits. P3-DCI (D60 sim.): Yields output crafted specifically for a DCI projector carrying a D60 white point. That output can appear magenta on other display devices that aren't configured for DCI display. P3-DCI (D65 sim.): Yields output crafted specifically for a DCI projector carrying a D65 white point. That output can appear magenta on other display devices that aren't configured for DCI display. Panasonic V35: Color management settings for each camera listed. Rec.2020: This IDT converts media made under the wide-gamut consumer and broadcast television standard. Rec.2020 ST2084 (1000/2000/4000 nits): This IDT converts media made under the wide‑gamut consumer and broadcast television standard, drawing on the SMPTE standard PQ (ST.2084) tone curve toward High Dynamic Range (HDR) post-production. For HDR televisions of varying peak luminance capability, three settings come provided. Rec.2020 HLG (1000 nits): This IDT converts media under the wide-gamut consumer and broadcast television standard while drawing on the Hybrid Log-Gamma (HLG) standard tone curve toward High Dynamic Range (HDR) post-production. A lone setting comes provided for HDR televisions whose peak luminance hits 1000 nits. Rec.709 (Camera): A deprecated legacy IDT for Rec. 709 retained for backward compatibility. It converts the source data to linear on the basis of Rec. 709 and transforms the outcome into ACES, but although this transformation is technically accurate, it isn't necessarily attractive once converted through the matching ODT. On that account, the academy switched to the Rec. 709 IDT described next, which inverts the Rec. 709 ODT. Rec.709: A standard transform crafted to move footage from the Rec. 709 color space across into the ACES color space. Use this choice for whatever other file type comes in, ProRes out of Final Cut Pro, DNxHD out of Media Composer, plus any media file pulled off tape. Rec.709 (D60 sim.): A standard transform built to carry media in the Rec. 709 color space with a D60 white point into the ACES color space. REDColor2/3/4/REDGamma3/4/REDLogFilm combinations: Assorted combinations of the REDcolor, REDgamma, and REDlogFilm settings are offered for legacy RED workflows. RWGLog3G10: The standardized RED IPP2 color pipeline transform covering all RED camera media. Should you be on a project that blends media formats calling for distinct IDTs, you're able to assign separate IDTs to clips through the Media Pool's contextual menu, or via the Clip Attributes window, which the Media Pool's contextual menu likewise reaches.

- ACES Output Device Transform: This drop-down menu lets you select an ODT (Output Device Transform) for transforming the image data so it can be monitored on your calibrated display, and when you export a timeline within the Deliver page. Your choices are:

ADX (10 and 16): A standardized ODT built for media bound for film output. Two settings cover 10-bit and 16-bit output. This ODT isn't intended for monitoring use. DCDM: At a gamma of 2.6, this ODT writes out X'Y'Z'-encoded media intended for passing to applications that re-encode the data to assemble a DCP (Digital Cinema Package) for digital cinema distribution. An XYZ-capable projector can display it.
