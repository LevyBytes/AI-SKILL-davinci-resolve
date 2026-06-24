# Hdr Setup And Grading (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

With the hardware and software fully configured, you can get going on your HDR grade. The procedure stays reasonably simple. 1 Begin by grading the HDR image on your HDR Monitor until it reads the way you intend. Dolby suggests nailing down the HDR image’s look first, which establishes the grade’s overall intention. 2 As you reach for the assorted grading controls on the Color page to grade HDR images, switching on the HDR Mode of the node in play is often handy — right-click that node in the Node Editor and pick HDR Mode off the contextual menu. The setting retunes that node’s controls to operate across a stretched HDR range. In practice this lets controls that let you adjust separate tonal ranges — Custom Curves, Soft Clip, and the like — cope far better with wide-latitude signals. 3 Once the HDR grade satisfies you, press the Analysis button within the Dolby Vision palette. That examines every pixel of every frame in the current shot, then runs and banks a statistical analysis handed off to the iCMU or eCMU, steering its automatic conversion of the HDR signal into an SDR signal. 4 Pick the “Target Display Output” and “Trim Controls For” settings you’re aiming to trim toward. Their defaults are “100-nit, BT.709, BT.1886, Full,” a standard SDR deliverable, but further options exist when you want multiple trim passes for a sharper result. Whatever you select, “Trim Controls For” marks which trim pass is active, and additional passes come from choosing another entry on this menu. 5 If the automatic conversion disappoints, lean on the Dolby Vision palette’s trim controls to hand-trim the outcome toward the closest BT.709 rendition of the HDR grade you built in step 1. 6 Land a good result and you move along to the next shot and carry on. Can’t land one, and worried your HDR grade went too far to yield an acceptable SDR tone mapping? You can always pull the HDR grade back a touch, then retrim the SDR grade in pursuit of a cleaner tone mapping. Dolby advises that substantial edits to the HDR master — especially shifts to the blacks or peak highlights — warrant reanalyzing the scene, though minor edits don’t strictly call for it. The gist Dolby pushes, then, is that a colorist grades the HDR picture against the 1000, 2000, 4000, or higher nit display in use, and afterward leans on the colorist’s use of the Dolby Vision controls to “trim” it down to a 100 nit SDR version. This metadata rides along inside the mastered media, where it helps tone map the whole image more intelligently to suit any display’s parameters. The colorist’s artistic intent steers every dynamic adjustment made to the content.

Setup and Workflows | HDR Viewers HDR Setup and Grading

### Delivering Dolby Vision

After the HDR grade is done and the SDR tone mapping trimmed, your program has to be output properly over on the Deliver page.

### Rendering a Dolby Vision Master

For a Dolby Vision master once grading wraps, confirm that the Output Color Space in the Project Settings’ Color Management panel sits on the right HDR ST.2084 setting for whatever peak output you intend (anything beyond it gets clipped). Next, configure your render around one of these Format/Codec pairings:

- TIFF, RGB 16-bit
- EXR, RBG-half (no compression)

Rendering for tapeless delivery writes all Dolby Vision metadata into a Dolby Vision XML that ships alongside either the Tiffs or the EXR renders. To produce a Dolby Vision XML file, highlight your timeline in the media pool and go to File > Export >Timeline. Browse to your save location, choose Dolby Vision v2.9 (or v4.0) MXF files in the file type selector, and click save. Those two file sets then go off to a facility equipped to build the Dolby Vision deliverable file.

### Rendering a Dolby Vision IMF

Delivery can go straight to an IMF whose package carries an MXF with Dolby Vision metadata baked in. For a Dolby Vision IMF, apply these Video settings on the Deliver page:

- Format: IMF
- Codec: Kakadu JPEG 2000
- Type: Dolby Vision (HD, 2K, UHD, or 4K), chosen to match your deliverable resolution.

Set whatever remaining IMF settings your project demands.

Deliver-page Video settings for building a Dolby Vision IMF Rendering a Dolby Vision H.265 file You can ship straight to a Dolby Vision-compatible H.265 file, letting video play back in a way that flips your television or computer screen into Dolby Vision mode. For a Dolby Vision H.265 file, apply these Video settings on the Deliver page:

- Format: MP4 or QuickTime
- Codec: H.265
- Dolby Vision Profile: Pick the Dolby Vision profile you intend to use, or None to handle the

Tone Mapping manually.

Setup and Workflows | HDR Viewers HDR Setup and Grading

- Tone Mapping: Set None for no tone mapping, or Dolby Vision to reveal a roster of common deliverables you can tone map toward.

Set whatever remaining H.265 settings your project demands.

Where the Deliver page’s H.265 Video section holds the Dolby Vision Profile and Tone Mapping settings Rendering an Ordinary SDR Media File or Other Specific HDR Trim Pass To put out the SDR trim pass, pick Dolby Vision from the Tone Mapping drop-down within the Advanced Settings of the Deliver page’s Render Settings list, then select the 100-nit, BT.709, BT.1886, Full entry below it. With that on, the SDR version of your program can go out in any format you please. You may likewise export trims at other HDR nit levels for particular displays — 600, 1000 or 2000 nits — within either the BT.2020 or P3 gamuts.

Where the Render Settings list’s Advanced Settings carry the Tone Mapping control

### SMPTE ST.2084 and HDR10

Plenty of display makers with no appetite for licensing Dolby Vision into their sets take the easier road instead, building their displays to comply with SMPTE ST.2084. That route needs only one stream for distribution, carries no licensing fees, demands no special mastering hardware beyond an HDR mastering display, and involves no special metadata to author or wrangle. Tellingly, SMPTE ST.2084 elevates the “PQ” EOTF — first devised by Dolby and used by Dolby Vision — into a general standard that supports encoding HDR at peak luminance figures reaching 10,000 cd/m2. The standard calls for a 10-bit signal at minimum for distribution, with the EOTF framed mathematically so the video signal squeezes the most out of a 10‑bit signal’s available code values while still spanning such a broad luminance range in the image. SMPTE ST.2084 also belongs to the “Ultra HD Premium” industry specification, which requires televisions carrying the Ultra HD Premium logo to offer the following capabilities:

- A UHD resolution no lower than 3840 x 2160
- A gamut covering at least 90% of P3
- A dynamic range that is either 0.05 nits black through 1000 nits peak luminance (suiting

LCD displays), or 0.0005 nits black through 540 nits peak luminance (suiting OLED displays)

- Compatibility with SMPTE ST.2084

Setup and Workflows | HDR Viewers HDR Setup and Grading

Lastly, ST.2084 is folded into the HDR 10 standard that the Blu-ray Disc Association (BDA) adopted for Ultra HD Blu-ray. HDR 10 demands these traits of Ultra HD Blu-ray discs:

- UHD resolution of 3840 x 2160
- Up to the Rec. 2020 gamut
- SMPTE ST.2084
- Mastered to a peak luminance reaching 1000 nits

The catch is that an HDR10 mastered program on its own won’t play back-compatibly on BT.709 displays running BT.1886 (though the up-and-coming HDR10+ standard covered later tackles that). On top of that, nothing scales the image’s above-100 nit region to suit displays whose peak luminance differs. Say you grade and master an image to a peak luminance of 4000 nits and then feed that signal to an HDR10-compatible television (using ST.2084) topping out at 800 nits: everything past 800 nits clips off, while everything under 800 nits appears precisely as graded. The reason is that ST.2084 keys to absolute luminance. Grade an HDR image against a 1000 nit peak luminance display, per HDR10’s recommendation, and any ST.2084 display will honor and reproduce every level of the HDR signal it’s able to, exactly as you graded them, right up to its own peak luminance ceiling. On an HDR10-compatible television able to push 500 nits, for instance, every mastered level from 501–1000 clips away, as the screenshot below shows.

Setting the original 1000 nit waveform, which stands for the grading monitor, against a clipped 500 nit waveform that stands for the consumer television Just how much trouble this poses really hinges on how you grade your HDRstrength highlights. If only the most extreme peak highlights are pushed to maximum HDRstrength levels, the audience may well never register that the display puts out just 800 nits of signal and clips off image detail from 801–1000 nits — there weren’t many details above 800 to begin with. But grade big explosive fireballs wholly above 800 nits because it looks cool, and the audience might notice after all. The upshot: when grading for displays limited to ST.2084, these are the sorts of things you have to keep in mind.

Setup and Workflows | HDR Viewers HDR Setup and Grading

### Monitoring and Grading to ST.2084 in DaVinci Resolve

To monitor an ST.2084 image you need nothing more than a ST.2084-compatible HDR display wired into whichever device drives your signal — DeckLink 8K, DeckLink 4K Extreme 12G, or UltraStudio 4K Extreme. Configuring Resolve Color Management to grade for ST.2084 mirrors the configuration for Dolby Vision. The video scopes get watched the same way and a master is output the same way too, since both standards lean on the identical PQ curve. TIP: When monitoring through the built-in video scopes in DaVInci Resolve, switch on “HDR (ST.2084/HLG)” within the Waveform Scale Style settings of the Scopes option menu to swap the scopes’ 10-bit scale for one keyed to nit values (cd/m2).

### Connecting to HDR-Capable Displays using HDMI 2.0a

With a DeckLink 4K Extreme 12G or an UltraStudio 4K Extreme video interface on hand, DaVinci Resolve 12.5 and later can emit the metadata that display devices need to render HDR video signals correctly over HDMI 2.0a — just tick the “Enable HDR metadata over HDMI” checkbox inside the Master Settings panel of the Project Settings.

Found in the Project Settings’ Master Settings panel, the Enable HDR metadata over HDMI option opens the door to HDR over HDMI 2.0a Once it’s on, a control over in the Project Settings’ Color Management panel — “HDR mastering is for X” — lets you state the output in nits to embed as metadata within the outgoing HDMI stream, so the display you’re wiring to reads it correctly. The figure you enter ought to line up with what your display anticipates.

By way of the “HDR mastering is for” setting you embed metadata for HDR sent out over HDMI 2.0a

Setup and Workflows | HDR Viewers HDR Setup and Grading

### HDR10+™

Samsung’s new HDR10+ HDR format is supported in DaVinci Resolve. Bear in mind the support remains a work in progress, the standard itself being new. Once active, an HDR10+ palette surfaces the trimming-analysis results that drive an automatic HDR-to-SDR downconversion, minting metadata that dictates how HDR-strength highlights read across a range of supported televisions and displays. You switch it on and configure it via the Enable HDR10+ checkbox in the Project Settings’ Color Management panel. Flipping HDR10+ on brings the HDR 10+ palette to life on the Color page.

HDR 10+ settings in the Color Management panel of the Project Settings

### Monitoring and Grading to ST.2084 for HDR10+

Grading a program for HDR10+ output means monitoring an ST.2084 image, and that takes only a ST.2084-compatible HDR display hooked into your output device — be it a DeckLink 8K, DeckLink 4K Extreme 12G, or UltraStudio 4K Extreme. Preparing Resolve Color Management to grade for ST.2084 plays out just as it would for Dolby Vision or plain HDR10. Likewise the video scopes are read the same and a master is output the same, all three standards resting on the one PQ curve. TIP: Should you monitor via the built-in video scopes in DaVinci Resolve, enabling “HDR (ST.2084/HLG)” under the Waveform Scale Style settings in the Scopes option menu trades the scopes’ 10-bit scale for one founded on nit values (cd/m2).

### HDR10+ Grading Workflow

The HDR10+ workflow runs on the premise that you first grade the HDR version of every clip in your program, then let the automatic analysis spin up a metadata-driven, downconverted tone mapped take on each shot. With the HDR10+ trim pass finished, you hand off the rendered HDR output together with HDR10+ JSON metadata files so a facility can perform the final mastering.

### Simultaneous Master and Target Display Output for HDR10+

As you master HDR and trim versions aimed at more constrained displays, being able to weigh your HDR grade against the tone mapped trim pass side by side is enormously helpful. From DaVinci Resolve 15 onward, the Master Display output and the Target Display output can be sent out at the same time whenever you grade with either Dolby Vision or HDR10+ turned on.

Setup and Workflows | HDR Viewers HDR Setup and Grading

### Necessary Hardware

Operating this way requires the following gear on hand:

- A DaVinci Resolve grading workstation whose output runs through one of these video interfaces — DeckLink 8K, DeckLink 4K Extreme 12G, UltraStudio 4K Extreme — or anything stronger.
- A Mastering Display reaching the HDR nit levels that your intended deliverable calls for.
- An HDR target display you can dial to the right tone mapped output.

### Enabling Simultaneous Monitoring

As you wire up your display hardware, route the HDR Master Display into output A and the Target Display into output B of whatever BMD video output device is in play. Then enable the “Use dual outputs on SDI” checkbox under the Master Settings of the Project Settings. From here, provided all your connections agree with one another, an HDR image should reach your HDR display while a trimmed image reaches your SDR display.

### HDR10+ Auto Analysis Commands

Once an HDR version of every clip in your program is graded, a batch of HDR10+ specific commands lets you auto-analyze each clip and mint custom HDR to SDR downconversion metadata, handing you a launch point for the SDR trim pass ahead. You’ll find these commands in the Color > HDR10+ submenu:

- Analyze All Shots: Runs an automatic analysis on every Timeline clip and banks each result on its own.
- Analyze Selected Shot(s): Confines the analysis to the shots you’ve selected in the Timeline.
- Analyze Selected and Blend: Looks at several selected shots and averages their result, which is

then written to every one of those clips. A time-saver when the clips you’re analyzing share identical content.

- Analyze Current Frame: A quick path for clips where one frame stands in

for the whole shot.

### Delivering HDR10+

With the HDR grade complete and the SDR downconversion trimmed, your program must be output the right way on the Deliver page.

### Rendering an HDR10+ Master

For an HDR10+ master once grading is done, verify the Output Color Space in the Project Settings’ Color Management panel rests on the proper HDR ST.2084 setting for your target peak output (anything over it clips). After that, build your render around the top-quality Format/Codec pairing that suits whoever handles the final mastering. The HDR10+ analysis plus the manual trim metadata you produced while trimming is stored per clip across a run of JSON sidecar files; export them by right-clicking the timeline in the Media Pool and selecting Timelines > Export > HDR10+JSON. Those two file sets then travel to a facility able to build an HDR10+ Mezzanine File (something DaVinci Resolve cannot do). NOTE: The HDR10+ mastering workflow remains a work in progress, and more information will follow as it surfaces.

Setup and Workflows | HDR Viewers HDR Setup and Grading

### HDR Vivid

HDR Vivid is the HDR video technology standard put out by the UHD World Association (UWA). Mastering to this format guarantees broad compatibility across HDR televisions, phones, computers, and other devices that conform to the standard.

HDR Vivid settings in the Color Management panel of the Project Settings

### Monitoring and Grading to ST.2084 for HDR Vivid

For grading a program toward HD Vivid output, you’ll monitor an ST.2084 image, and all that demands is a ST.2084-compatible HDR display joined onto your output hardware — a DeckLink 8K, DeckLink 4K Extreme 12G, or UltraStudio 4K Extreme. Readying Resolve Color Management to grade for ST.2084 unfolds exactly as it does for Dolby Vision or ordinary HDR10. The video scopes are likewise observed the same and a master output the same, because every one of these standards depends on the same PQ curve. TIP: While monitoring on the built-in video scopes in DaVinci Resolve, turning on “HDR (ST.2084/HLG)” in the Waveform Scale Style settings within the Scopes option menu replaces the scopes’ 10-bit scale with one based on nit values (cd/m2).

### HDR Vivid Grading Workflow

The HDR Vivid workflow rests on grading the HDR version of every clip in your program first, then leaning on the automatic analysis to build a metadata-governed, downconverted tone mapped rendition of each shot. After the HDR Vivid trim pass wraps, you deliver the rendered HDR output carrying embedded HDR Vivid metadata.

### Simultaneous Master and Target Display Output for HDR Vivid

While mastering HDR and trimming versions destined for more limited displays, the ability to judge your HDR grade alongside the tone mapped trim pass is tremendously useful. As of DaVinci Resolve 15, both the Master Display output and the Target Display output can be emitted together whenever you grade with HDR Vivid switched on.

### Necessary Hardware

Going about it this way calls for the equipment below:

- A DaVinci Resolve grading workstation feeding its output through some video interface — a DeckLink 8K, a DeckLink 4K Extreme 12G, an UltraStudio 4K Extreme — or a superior model.
- A Mastering Display able to hit the HDR nit levels your required deliverable demands.
- An HDR target display that can be tuned to the correct tone mapped output.

Setup and Workflows | HDR Viewers HDR Setup and Grading

### Enabling Simultaneous Monitoring

Setting up your display hardware, send the HDR Master Display to output A and the Target Display to output B on whichever BMD video output device you happen to use. Next, switch on the “Use dual outputs on SDI” checkbox within the Master Settings of the Project Settings. From there, so long as every connection is mutually compatible, you ought to get an HDR image driving your HDR display and a trimmed image driving your SDR display.

### HDR Vivid Trim Controls in DaVinci Resolve

The newest HDR Vivid palette lays out three groups of controls, the first being the main controls:

- Target Display Output: This drop-down sets which parameters drive how the tone mapped image is shown. Through the menu you pick particular display properties to preview how the trimmed image reads on assorted displays spanning different gamuts and peak luminance capabilities.
- Trim Mode: Picks the toolset behind the trims, whether the Curve or the Statistical mode.
- Analyze controls: The commands that drive HDR Vivid auto-analysis show up as buttons,

doing the same jobs as their like-named siblings over in the Color > HDR Vivid submenu. Keep in mind that most trim controls stay greyed out until an analysis is run, a mandatory first move. All: Runs an automatic analysis on each clip in the present Timeline and banks each result separately. Selected: Restricts the analysis to selected shots in the Timeline. Frame: Handy where one stretch of a clip holds an extreme level of color or lightness atypical of the rest, skewing the analysis into a poor result. Park the playhead on a frame that captures how the clip ought to look and choose the Frame option to base the analysis on that frame alone. It’s also a quick route for clips where a single frame speaks for the whole shot.

- Enable Tone Mapping Preview: Surfaces the target display output in the Color page Viewer and the video output, so you can gauge how the tone mapped version reads on your HDR display.

Which controls come next depends on the Trim Mode you’ve chosen. Curve: The Curve trim mode opens up an assortment of controls letting the colorist tweak the trim metadata by hand at the clip or frame level. Offset, Brightness, and Detail settings cover the Dark and Bright stretches of the curve, while Midtones carry a brightness control. Highlight Crop reins any highlights that overshot the display’s top brightness — and thus blew out — back into range. Separate Global and Highlight saturation settings are on offer too. Statistical: The Statistical trim mode opens controls for fine-tuning the automatic tone mapping algorithm applied during the Analyze step.

Setup and Workflows | HDR Viewers HDR Setup and Grading

### HDR Vivid controls in the Color page

### Delivering HDR Vivid

After your HDR grade is finished and the SDR downconversion trimmed, the program needs outputting correctly over on the Deliver page.

### Rendering an HDR Vivid Master

For an HDR Vivid master once grading concludes, ensure the Output Color Space in the Project Settings’ Color Management panel is parked on the right HDR ST.2084 setting for your intended peak output (whatever exceeds it clips). After that, set your render to export an H.265, Quicktime, or MP4 codec under the Video Settings, tick the Embed HDR Vivid Metadata box, and pick the matching HDR mode you graded the master in from the drop-down box beneath.

HDR Vivid settings in the Video section of the Deliver page

### Hybrid Log-Gamma (HLG)
