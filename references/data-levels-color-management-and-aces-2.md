# Data Levels Color Management And Aces (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Final Output

### Identifying the Input Color Space of Different Clips

At the heart of automated color management lies knowing the color space and transfer function carried by every clip of source media in your project. DaVinci Resolve has several ways to work this out, following a cascading decision-tree you can override by hand where needed. Working out the Input Color Space ran through these stages of automated decision making: 1 When the source media is a camera raw format such as .braw, .R3D, .ari, etc., DaVinci Resolve leans on manufacturer-supplied colorimetry to debayer the clip automatically and pin down its Input Color Space. 2 Failing that, when the source media carries embedded color space metadata (something QuickTime or .MXF allow), that metadata is used to pin down the Input Color Space. 3 Failing that, when no embedded color space metadata exists, the default Input Color Space setting in the Project Settings is applied to give an Input Color Space to every clip not otherwise identified. 4 Where needed, you may set the Input Color Space of clips in the Media Pool by hand, which overrides either embedded color space metadata (should it be wrong) or the default Input Color Space setting (when you are juggling multiple color spaces). The Input Color Space of camera raw media cannot be overridden.

Each of these steps is taken up in finer detail across the sections that follow.

### Using Camera Raw Formats

While you run RCM on a project built around Camera Raw formats, color science data from each camera maker debayers every camera raw file to particular color primaries with linear gamma, so that all of the source’s image data survives and reaches DaVinci Resolve’s color managed image processing pipeline. Consequently, the Camera Raw project settings and the Camera Raw palette of the Color page are switched off, since RCM has taken over debayering for all camera raw clips, and the whole of the raw file’s image data is on hand regardless of which Timeline Color Space you decide to work in.

### Using Source Media Color Space Metadata

Once switched on, RCM identifies on its own the color space details of imported media that was either transcoded or recorded straight to supported non-raw media formats. It does so by reading several sources: the NCLC metadata inside QuickTime-wrapped files, the color space metadata inside .mxf-wrapped files, plus the XML sidecar files tracking color management across ACES workflows. The process happens automatically; no visible controls steer it beyond the individual Input Color Space and Input Gamma settings tied to each clip in the Media Pool. Color Space Metadata in QuickTime For correct color management, DaVinci Resolve is able to read the NCLC metadata held inside media files that a QuickTime container has wrapped. That metadata is made of three values written as (for instance) 1-1-1. Taken from left to right, the trio of digits identifies, in turn, the Color Primary (or color space), then the Transfer Function (or gamma), and lastly the Color Matrix the media file relies on. The SMPTE Registered Disclosure Document RDD 36:2015 standardizes these values. For reference, the various codes appear in the table below. In the earlier instance, a code of 1-1-1 marks a standard dynamic range clip relying on the BT.709 primaries, transfer function, and color matrix.

Color Primary 0 Reserved 1 ITU-R BT.709 2 Unspecified 3 Reserved 4 ITU-R BT.470M 5 ITU-R BT.470BG 6 SMPTE 170M 7 SMPTE 240M 8 FILM 9 ITU-R BT.2020 10 SMPTE ST 428-1

Transfer Function 0 Reserved 1 ITU-R BT.709 2 Unspecified 3 Reserved 4 Gamma 2.2 curve 5 Gamma 2.8 curve 6 SMPTE 170M 7 SMPTE 240M 8 Linear 9 Log 10 Log Sqrt

Color Matrix 0 GBR 1 BT709 2 Unspecified 3 Reserved 4 FCC 5 BT470BG 6 SMPTE 170M 7 SMPTE 240M 8 YCOCG 9 BT2020 Nonconstant Luminance 10 BT2020 Constant Luminance

Color Primary 11 DCI P3 12 P3 D65 –– –– –– –– –– ––

Transfer Function 11 IEC 61966-2-4 12 ITU-R BT.1361 Extended Colour Gamut 13 IEC 61966-2-1 14 ITU-R BT.2020 10 bit 15 ITU-R BT.2020 12 bit 16 SMPTE ST 2084 (PQ) 17 SMPTE ST 428-1 18 ARIB STD-B67 (HLG)

Color Matrix –– –– –– –– –– –– –– ––

The Default Input Color Space The default Input Color Space is available to set only when the “Resolve color management preset” drop‑down menu sits on Custom. Otherwise it falls back to “Rec. 709 Gamma 2.4” across all presets. Beyond that, this setting is the default color space that every clip in the Media Pool not otherwise identified will adopt. Manually Tagging Clip Color Space Where needed, you can identify by hand the color space of one or more chosen clips in the Media Pool, right-clicking them and picking the Input Color Space (and, if you like, the Input Gamma) from the contextual menu.

### Simple RCM Setup

The moment you first pick DaVinci YRGB Color Managed out of the Color science drop-down menu on the Color Management panel within the Project Settings, two plain menus appear for shaping how Resolve Color Management should operate for you: the “Resolve color management preset,” along with the “Output Color Space.”

### Automatic Color Management

Your first decision under RCM is whether to lean on Automatic Color Management or on the Manual Presets. Ticking the Automatic Color Management box, DaVinci Resolve hands you a pared-down set of options aimed at the most common use cases. For the Color Processing Mode, you pick SDR or HDR, and going by the file types and codecs present in the Media Pool, DaVinci Resolve picks the fitting input color space on its own. After that, choose from a list of common Output color spaces for delivery. Should you want hands-on control of these parameters, clear the Automatic Color Management box and pick from the Color Management Presets below.

Automatic Color Management presets for fast, simple color management set up

### Resolve Color Management Presets

The Resolve Color Management preset menu lets you decide how RCM is put to work grading your program. Every one of these presets fully arranges your project’s color management, and whichever setting you pick has a direct bearing on how you will grade. For that reason, once you settle on a way of working and grade every clip in your program, those grades count on the preset you used staying selected so that they appear as intended.

Resolve Color Management presets for manual color management set up A sound way to think about which preset to use is to reach for an SDR or HDR preset matching the primary deliverable you intend to output. Each of the SDR and HDR presets comes in several variations to pick among. Although these presets line up with how you plan to output your program, they do not box you in, because you can always switch the Output Color Space (covered below). That makes it possible to export several versions of your program, each meant for a different venue, no matter which color management preset is in play. Each time you pick a preset, a short description spells out the workflow that preset is built to support. Below is a list of the presets on offer, with somewhat fuller explanations.

- SDR Rec.709: (default) Builds a Rec. 709 SDR grading environment. On output, what you create may be converted to HDR where called for, yet it stays bounded to a Rec. 709 gamut, with any out-of-bounds colors clipped. The name leaves out Gamma 2.4 because scene-versus-display OOTF is handled for you. A fit for everyday streaming and broadcast.
- SDR P3 Broadcast: Builds a P3-D65 SDR grading environment. On output, what you create may be mapped to HDR where called for, yet it stays bounded to a P3-D65 gamut, with any out-of-bounds colors clipped. The name leaves out Gamma 2.4 because scene-versus-display OOTF is handled for you. A fit for broader gamut streaming and broadcast held at SDR levels.
- SDR P3 Cinema: Builds a P3-D60 SDR grading environment. On output, what you create may be mapped to HDR where called for, yet it stays bounded to a P3-D60 gamut, with any out-of-bounds colors clipped. A fit for everyday Cinema projection.
- SDR Rec.2020: Builds a Rec. 2020 SDR grading environment. On output, what you create may be mapped to HDR where called for. Well suited to wide gamut streaming and broadcast.
- DaVinci Wide Gamut: Builds an extra wide gamut grading environment that serves equally for grading SDR or HDR. It can export at maximum image fidelity, holding onto highlight details as far as 10,000 nits. This is a log-encoded grading space for colorists who prefer that approach. A fit for turning out mezzanine intermediates or final deliverables, or for grading HDR at high nit levels.
- HDR P3 Broadcast: Builds a P3-D65 HDR grading environment. The output gamut stays bounded to P3‑D65, with any out-of-bounds colors clipped. A fit for grading wide gamut SDR or HDR as far as 1000 nits.
- HDR Rec.2020: Builds a Rec. 2020 HDR grading environment. A fit for wide gamut SDR or HDR deliverables as far as 1000 nits.
- Custom: When none of the presets on offer matches the way you must work, pick Custom, which lays bare the entire set of RCM settings for you to arrange however suits you.

IMPORTANT: With every preset, bringing in media whose gamut matches or is smaller maps the image data into the preset’s larger color space and leaves it untransformed. Bringing in media whose gamut is wider than the preset’s color space remaps the image data so it fits the smaller color space, while holding onto as much image detail as it can.

### Output Color Space

On most DaVinci Resolve installations and projects, you will set your Output Color Space to suit the needs of your program, in keeping with what your display can do (or with the capabilities your display is configured to use for the project in hand). You will typically pair that with a Resolve Color Management preset matching those same capabilities. Even so, RCM gives you the freedom to grade in one color space and then output to others when the situation calls for it. Take this case: you might easily grade an SDR Rec. 709 cut of a program meant for streaming or for broadcast, after which you flip the Output Color Space over to SDR P3 Cinema to put out an extra deliverable for theatrical exhibition. To make that possible, you can set the Output Color Space to any value, separate from whichever Resolve Color Management preset you have picked, and DaVinci Resolve converts on its own from your Color Management Preset to the Output Color Space you chose. Doing so, the rules below govern the image transform that results. When going SDR to HDR:

- Within your program, 0-50 nits (18% mid-gray) lands at 0-50 nits on output (no change).
- Within your program, the 51-90 nits band gets shifted to 51 to 100 nits (slightly

expanded).

- Within your program, the 91-100 nits band gets shifted to 101 to 1000 nits

(greatly expanded).

Original SDR grade seen within an HDR scale,

### After an automatic SDR to HDR conversion

Going the other direction, from HDR to SDR, the reverse takes place:

- Within your program, 0-50 nits (18% mid-gray) lands at 0-50 nits on output (no change).
- Within your program, the 51 to 100 nits band gets shifted to 51-90 nits (slightly

compressed).

- Within your program, the 101 to 1000 nits band gets shifted to 91-100 nits

(greatly compressed).

Although these ways of converting between SDR and HDR give you a workable jumping-off point, they are not meant as a hands-off fix. It is vital to run a trim pass any time you output a deliverable in a fresh color space and EOTF, so you can inspect every clip and tweak it to better the result where needed. NOTE: While converting SDR to HDR, this behavior can amplify noise in imported SDR media that happens to hold large flat sweeps of bright color. Where certain clips betray this problem, you can switch the behavior off clip by clip from the Media Pool clip contextual menu, or from the Thumbnail Timeline contextual menu on the Color page, by toggling “Inverse DRT for SDR to HDR Conversion.”

### Advanced RCM Setup

Advanced users wanting finer command of every facet of RCM can pick Custom from the Resolve Color Management preset menu. That lays bare every control there is, opening a wealth of workflow possibilities for advanced users and post production facilities. Since each setting wraps up a sizable amount of functionality, the sections to follow treat each parameter one at a time. NOTE: Older projects on RCM will carry Color science set to Legacy, so that the earlier color management settings and the effect of their color transformations on your work are preserved. To read more about how the prior generation of RCM behaves, consult the September 2020 version of the DaVinci Resolve 16 Manual.

The Custom Color Management controls within Resolve Color Management, in their revised form as of DaVinci Resolve 17

### Single Setting vs. Dual Setting RCM

RCM can be set up in two ways. With the “Use Separate Color Space and Gamma” checkbox switched off, the Color Management panel of the Project Settings shows a single drop-down apiece for the Input, Timeline, and Output Color Space settings. Each setting transforms gamut and gamma together, according to the option you pick. That makes arranging the transform you want a touch simpler.

### Single setting Resolve Color Management

Switch the “Use Separate Color Space and Gamma” checkbox on, and the Color Management panel shifts so that the Input, Timeline, and Output Color Space settings each show two popups. The first drop-down sets the gamut on its own, while the second sets the gamma on its own. That makes it plainer to see exactly which pair of transforms applies at each stage of RCM.

### Dual setting Resolve Color Management

On top of that, Dual Setting RCM lets you assign a clip in the Media Pool its own gamut transform and its own gamma transform, kept apart. Dual setting Resolve Color Management assignments as applied to Media Pool clips

### Setting the Input Color Space

This setting is the default color space that every clip in the Media Pool not otherwise identified will adopt, unless you identify the color space of these clips by hand — right-clicking them and picking an Input Color Space (and, if you like, an Input Gamma) from the contextual menu. The setting leaves media in camera raw formats alone, and likewise media carrying embedded color space metadata.

### Choosing a Timeline Color Space

The Timeline Color Space is the “working” color space that settles the way a clip’s contrast and its color get mapped for adjustment, and that in turn shapes how responsive the effects and grading controls feel while you work. Some colorists like the classic “video” color space of Rec. 709, since its controls feel familiar and comfortable, above all when mastering SDR content. Others, accustomed to log-encoded media (most likely with the Log controls), tend to favor a more film-oriented workflow with Cineon, LogC, or other wide gamut, logarithmically encoded formats. For an SDR deliverable, any color space you are at ease with will turn out fine. But for an HDR deliverable, it serves you well to pick a wide gamut Color Space (and Gamma) for the strongest results on output. Here, DaVinci Wide Gamut is an excellent pick (more on it below). Whichever Timeline Color Space you settle on, every clip in an edit is transformed out of the Input Color Space assigned to it — automatically or by hand — and into the Timeline Color Space setting to yield the final output. This is what lets you grade inside a Log-encoded timeline color space yet view a normalized or de-logged image. IMPORTANT: Once you settle on a Timeline Color Space and start grading, leave that Timeline Color Space alone, or you will alter every grade built on the mathematics it defines. The Output Color Space can always be changed to make a fresh deliverable, though every grade leans on the Timeline Color Space for a correct render. DaVinci Wide Gamut Color Space and DaVinci Intermediate Gamma Built by Blackmagic Design, DaVinci Wide Gamut (DaVinci WG) and DaVinci Intermediate serve as Timeline Color Space and Gamma settings that furnish a dependable universal internal working color space, one reaching a practical ceiling of whatever image data any camera might record. The DaVinci Wide Gamut color space is larger than BT.2020, ARRI Wide Gamut, and even ACES, so image data is never lost wherever your media originates.

### The DaVinci Wide Gamut color space

Beyond that, the primary color values of the DaVinci WG color space are positioned so that mapping source media from various cameras into this gamut automatically is highly accurate as part of the Input to Timeline Color Space conversion, while tone and saturation mapping between color spaces can run more accurately in the Timeline to Output Color Space conversion. It also helps deliver greater consistency across media from different cameras as you make manual grading adjustments (though some variation owing to differences in camera and lens systems will linger). The DaVinci Intermediate OETF gamma setting was built to pair with DaVinci Wide Gamut, supplying a fitting internal luminance mapping of high precision image data, readying it for mastering toward either HDR or SDR standards, as your needs dictate, without surrendering image data.

### The DaVinci Intermediate OETF seen encoding HDR levels

### The DaVinci Intermediate OETF encoding SDR levels

Resolve Color Management bends to your needs, so you are under no obligation to adopt DaVinci Wide Gamut/ DaVinci Intermediate as your Timeline color space if that is not your wish. Still, it carries plenty of upsides and merits a trial to see whether it improves your workflow. To read more, consult the “DaVinci Resolve Wide Gamut Intermediate” document at https://www.blackmagicdesign.com/support/family/davinci-resolve-and-fusion.

### Timeline Working Luminance

This control surfaces only while the Resolve Color Management presets menu sits on Custom Settings. The Timeline Working Luminance drop-down menu lets you decide how the Input DRT (covered below) maps a source image’s maximum level into the Timeline Color Space currently chosen. The setting also fixes the maximum highlight level you can output into the Output Color Space currently chosen by way of the Output DRT. While it is usual to set this to suit the mastering standard you are grading toward, through a collection of SDR and HDR labeled settings, extra settings are on hand that let you build in more automatic highlight compression while grading. SDR 100: The customary choice for grading SDR material whose ceiling is 100 nits. HDR 500-4000: Customary choices for grading HDR material across a spread of maximum mastering levels. Provided output DRT is anything but None, the highlights will roll off in some fashion, except where inverse DRT is switched on, in which case there is no rolloff. SDR and HDR ER settings: Each of these “extended range” settings names a pair of values and opens up more headroom for bold highlight grading, since DaVinci Resolve can then compress a broader band of out-of-bounds image data without clipping, often for a smoother look. Here is the way it operates. Say you pick the setting “HDR ER 1000/2000.” In that case, the Input DRT maps the maximum brightness of each source image into the range set by the first value, 1000 nits. Then, as you grade, the signal stays unclipped until it hits the maximum range set by the second value, 2000 nits. That supplies a further 1000 nits of out-of-bounds headroom before RCM’s image processing pipeline hard clips the image data. The Output DRT next maps from the maximum brightness set by the second number (2000 nits) down to the output value defined by the Output Color Space currently chosen, compressing this out-of-bounds headroom along the way to keep as much highlight detail as the range you picked allows. Custom: Exposes a field where you can enter a specific nit value.

### 203 Nit Support for SDR to HDR

This control surfaces only while the Resolve Color Management presets menu sits on Custom Settings. Resolve Color Management can remap SDR content to HDR by mapping 100 nits to 203 nits (set as the diffuse white level) in line with the BT.2100 recommendation. That lets the peak highlights of SDR material hold their own against the markedly brighter highlights of HDR content in programs blending the two (documentaries, say), so SDR whites keep reading as white rather than gray when set beside diffuse white in HDR.

By default the checkbox that switches this on stays hidden. Whenever the Output is set to an HDR standard yet the Timeline still rests at SDR, a checkbox labeled “Use 203 nits reference for Rec.2100 HDR” — the one that remaps SDR highlights up into HDR — appears in two places: within the RCM settings on the Color Management panel under Project Settings, and within the Color Space Transform Resolve FX plugin.

The “Use 203 nits reference for Rec.2100 HDR” checkbox, found in Resolve Color Management, used to scale SDR levels suitably up into HDR color space

### Gamut Limiting, Restricting Values Within a Larger Gamut

This control surfaces only while the Resolve Color Management presets menu sits on Custom Settings. As larger gamuts for distribution take hold, delivery specifications more and more call for output to a large gamut, such as Rec. 2020, while still demanding that image values be held inside a smaller gamut, such as P3. The aim is delivery to “future-proofed” standards while heading off saturation values too high to show on consumer displays that cannot reach the full extent of those standards. In this situation, you will pick a larger gamut in Output Color Space, then pick a smaller gamut in “Limit Output Gamut To.” Once you do, every image value lying beyond the named “Limit Output Gamut To” standard is hard clipped. This setting defaults to None.

Pick an entry from the Limit Output Gamut To menu so image values stay confined inside a larger gamut

### Input DRT Tone Mapping

This control surfaces only while the Resolve Color Management presets menu sits on Custom Settings. RCM has always reworked the color primaries of differing media formats to agree with one another inside the shared Timeline Color Space. In this updated release, the Input DRT (Display Rendering Transform) drop-down menu offers an assortment of options that let DaVinci Resolve tone map the image data of SDR and HDR clips automatically so they agree more closely once fit into the Timeline Color Space currently chosen. Though the options differ in their specifics, all are automated input-to-timeline color transforms that accomplish the following:

- Media that is log-encoded, or that uses a 2.4 gamma transfer function, gets mapped so its black point, its midtones at 18% gray, and its white levels line up with those of HDR media. Where it is required, highlight data is stretched with care so that every Timeline clip’s highlights, SDR or HDR alike, receive comparable handling.
- Raw formats — among them BRAW, RED, and ARRI RAW — together with media on HDR transfer functions, undergo only minimal mapping across an HDR span of tonality.
- All color transforms into the Timeline Color Space are done without clipping.

The intent is to spread each Timeline clip’s image data, whether SDR or HDR media, across a comparable histogram, with shadows, midtones, and highlights laid out so as to make a friendlier starting point for grading. One upshot is that grades made for one kind of media largely carry over well to other kinds. A range of options is given for the specifics of how this Input to Timeline Color Space transform happens. They all accomplish the same end yet bring different advantages.
