# Hdr Setup And Grading (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### HDR Setup and Grading

For cinema, television, and streaming, High Dynamic Range (HDR) grading represents the newest stage in how consumers experience media. Although HDR pipelines are already established in premium cinema and television, the spread of this mastering approach into cheaper programming has historically lagged. That said, recent advances together with a widening selection of affordable, HDR-capable consumer hardware are set to make HDR mastering of visual material far more commonplace. For anyone new to the subject, this chapter explains what HDR actually is and walks through the practical steps for configuring DaVinci Resolve to perform HDR grading.

The Dolby and Dolby Vision names, plus the double-D symbol, are registered trademarks belonging to Dolby Laboratories Licensing Corporation.

### High Dynamic Range (HDR) Grading in DaVinci Resolve

The HDR capabilities in DaVinci Resolve ship only with DaVinci Resolve Studio. High Dynamic Range (HDR) video refers to a developing set of encoding and distribution technologies built so that the latest television displays can show footage with extremely bright highlights and richer saturation. Broadly speaking, most of an HDR picture is graded much the way a Standard Dynamic Range (SDR) picture is today, since the shadows and midtones stay largely consistent between conventionally SDR-graded and HDR-graded images. That holds true partly because shadows are by nature dark; beyond that, keeping them aligned preserves a comfortable viewing experience and makes backward compatibility simpler whenever both an SDR and an HDR version of a program must be produced. Where HDR differs is in offering generous extra headroom for very bright highlights and color saturation well past anything SDR television and cinema could previously show. That headroom lets the colorist craft more vivid, lifelike highlights — think sunsets, lit clouds, firelight, explosions, sparkles, and similarly brilliant, saturated subjects. Put differently, you can now “open up” an image’s highlights exactly as you’ve always been able to open up, or expand, shadow detail. Beyond delivering more natural lighting intensity and saturation, this also greatly widens the contrast a scene can contain. As an illustration, a properly calibrated SDR display should peak at a luminance of 100 nits (cd/m2), whereas current HDR displays can reach peak luminance levels of 700, 1000, or even 4000 nits. Yet because the technology keeps evolving, the published technical standards reach well beyond what today’s consumer televisions, projectors, phones, and tablets can actually deliver. As things stand today, a consumer television can typically put out somewhere between 700 and 1600 nits. On top of that, consumer displays frequently include automatic brightness limiting (ABL) circuitry that caps power draw at levels appropriate for the home, so only a portion of the picture can hit those peak values simultaneously. That limitation is acceptable, since HDR isn’t about brightening the whole frame — it’s about reserving headroom for select bright highlights and added saturation. For all these reasons, HDR standards concentrate on defining what a display must be able to do, rather than dictating how those levels get used. That remains a creative decision.

### HDR Isn’t Just for Televisions

In case you assume that living-room televisions and projectors are the sole route to HDR content, several flagship iOS and Android phones and tablets now include HDR playback that can match — or even surpass — the UltraHD requirements for HDR content on an OLED display. As a result, HDR has, perhaps unexpectedly, become a broadly accessible mobile experience.

### The Different Ways of Mastering HDR

Even though each HDR technology takes its own route to mapping your program’s video levels onto an HDR display’s range, every one of them emits a “near-logarithmically” encoded signal that depends on a compatible television to stretch it correctly back into its “normalized” form for viewing. Consequently, if you view an HDR signal coming out of your grading workstation’s video interface on an SDR display, it appears flat, desaturated, and unappealing right up until it reaches your chosen HDR display. On output, a graded HDR picture resembles a log-encoded one in appearance As things stand now, DaVinci Resolve can support five main routes to HDR mastering, namely:

- Dolby Vision®
- HDR10
- HDR10+
- HDR Vivid
- Hybrid Log-Gamma (HLG) Every one of these HDR standards specifies how an HDR signal gets encoded for export and is subsequently mapped to the visible output of an HDR or SDR display. Grading toward any of them calls for a measure of color management, and DaVinci Resolve offers three principal approaches to it:
- The simplest route is to switch on Resolve Color Management (RCM) or ACES in the Color Management

panel of the Project Settings, then apply the Color Space conversion options provided there. Each supported flavor of HDR has its own option in that list.

- The same transforms RCM provides are also exposed as Resolve FX operations, should you prefer to assemble your grading pipeline by hand using the Color Transform Resolve FX adjustment.
- LUTs likewise handle each of these color space conversions, in case you want to build a bespoke image processing pipeline around custom-made LUT or DCTL transforms. On the whole, Resolve Color Management and ACES are the dependable, recommended way to tackle HDR grading in DaVinci Resolve for most situations.

To dig deeper into Resolve Color Management, refer to Chapter 9, “Data Levels, Color Management, and ACES.”

### What Do I Do With HDR?

Although these standards enable HDR mastering and distribution, they say nothing about how the HDR-strength levels ought to be employed for creative effect. That decision falls to you, because making use of the wide headroom for brightness and saturation that HDR opens up sits squarely in the colorist’s hands — a sequence of creative choices about how to map the range of highlights present in your source media onto the above-100 nit HDR levels you’re mastering toward as you grade, within the peak luminance level you’ve been assigned. The particular HDR peak luminance level you target (1000 nit, 3000 nit, 4000 nit) likely comes down to which display you can access and who is distributing the finished program.

### Analyzing HDR Signals Using Video Scopes

With any flavor of waveform scope — parade and overlay scopes included — the way HDR is encoded causes the signal to sit within the 10-bit scale used for analysis very differently than you might expect. The chart of values below should clarify how each level in “nits” (i.e., cd/m2) maps to a code value on the 10-bit image scale:

10-Bit Code 1019† 948 920 889 844 824 767 728 691 635 528 520 4†

Nearest Value in cd/m2 HDR Display Peak Luminance Capability

### 10,000

### No commercially available display

### Outdoor LED Displays

Professional HDR Displays from Sony, Dolby, Flanders Scientific, EIZO, etc.

Professional HDR Displays from Sony, Dolby, Flanders Scientific, EIZO, etc.

Professional HDR Displays from Sony, Dolby, Flanders Scientific, EIZO, etc.

### Virtual Production Wall Panels

Professional HDR Displays from Sony, Dolby, Flanders Scientific, EIZO, etc.

### OLED mobile phone brightness

### Minimum standard for an “UltraHD” OLED display

### Professional SDR displays in “HDR preview mode”

BT.2408 recommended diffuse-white value when SDR content is intercut 203 against 1000 nit max HDR content

### Dolby Cinema projector

### Standard peak luminance for SDR displays

Reference peak luminance for SDR DCI projection; Dolby Cinema 3D peak 48 luminance

Absolute black

† the 0–3 and 1020–1023 ranges are reserved values

This table of values helps you see where HDR nit levels land on older external scopes, but when you monitor with the video scopes built into DaVinci Resolve, you can enable the “HDR (ST.2084/HLG)” entry under Waveform Scale Style, reached through the Scopes option menu; doing so swaps the scopes’ 10-bit scale for one keyed to nit values (or cd/m2) instead.

The video scopes shown with HDR (ST.2084/HLG) active, set via Waveform Scale Style under the Scopes option menu IMPORTANT: When you run a workflow that isn’t Davinci Resolve Color Managed and you switch on the HDR (ST.2084/HLG) scopes, the waveform keeps reporting HDR levels no matter what — even after you’ve manually chosen Rec.709 as the output color space — so its readings won’t be 100% accurate. TIP: Should the detail visible in the 0–519 range (0–100 nits) of the video scope graphs prove insufficient, you can turn to the 3D Scopes Lookup Table control, found within the Color Management panel of the Project Settings, and assign a fitting “HDR X nits to Gamma 2.4 LUT,” with X standing for the peak nit level of the HDR display in use. That redraws the scopes such that the signal’s 0–100 nit span occupies the scopes’ full height, from 0 through 1023. As a result, the HDR-strength highlights are driven past the visible top edge of the scopes and vanish, yet the payoff is markedly clearer midtone detail in the picture.

### HDR Viewers

On both Mac and Windows systems, the native DaVinci Resolve viewers can be shown in HDR. This setting reaches every DaVinci Resolve viewer — that covers the main page viewers, Cinema Mode, Fairlight Floating Viewer, Scene Cut Dialog, plus the Video Clean Feed. You’ll need an HDR-capable display along with HDR switched on at the OS level:

- Turn on the Windows HDR display settings (System > Display > HDR).
- Turn on the Mac HDR display settings (System Settings > Displays > High Dynamic Range).
- Within DaVinci Resolve Preferences > System > General, you’ll have to enable the “Use 10-bit

precision in viewers if available” box. NOTE: The broader controls/UI and dialogs that aren’t viewers (for instance, the secondary screen, project manager, floating Media Pool) remain unaffected.

Setup and Workflows | HDR Viewers HDR Setup and Grading

### Dolby Vision®

A longtime advocate and innovator in using HDR to improve how consumers experience video, Dolby Laboratories created an HDR mastering and delivery method named Dolby Vision. Like the majority of HDR standards covered in this chapter, Dolby Vision relies on the PQ (perceptual quantizer) electrical-optical transfer function (EOTF, which describes how an electronic video signal appears on a display) as defined by SMPTE ST.2084, paired with a tiered set of metadata carried alongside the video stream. Every piece of metadata Dolby Vision uses is sorted into levels, and the ones below matter most to the colorist:

- Level 0 metadata, the global metadata describing the Mastering Display (the one the colorist works on), covering aspect ratio, frame rate, color encoding, plus details about all the target displays referenced by the Level 2 and Level 8 trim metadata noted below.
- Level 1 metadata, the Dolby Vision v2.9 analysis metadata produced automatically whenever you employ the Dolby Vision controls to analyze the timeline’s clips. Every DaVinci Resolve Studio user has access to the controls that auto-generate Level 1 metadata.
- Level 2 metadata, the Dolby Vision v2.9 trimming metadata the colorist sets through the version 2.9 trim controls found in the Dolby Vision palette of the Color page. This trim governs how the Dolby Vision image gets mapped onto a target display (for example, a 100 nit BT.709 display) that differs from the mastering display (for example, a 1000 nit BT.2020 display). Its role is to safeguard a program’s artistic intent by letting the colorist guide how the program’s signal is fitted into the varying luminance ranges of displays whose peak luminance capabilities differ. Hand-adjustable Level 2 metadata is offered to DaVinci Resolve Studio users only through a license acquired from Dolby.
- Level 3 metadata, the Dolby Vision v4.0 offset added to the Level 1 metadata produced by the analyze buttons in the Dolby Vision controls. It additionally holds the mid tone offset data.
- Level 5 metadata, which reports the deliverable format’s aspect ratio together with the aspect ratio of the actual picture sitting inside that format. This metadata applies at the per clip level as well.
- Level 6 metadata, which holds the MaxCLL and MaxFALL levels that the HDR10 mastering standard of HDR requires.
- Level 8 metadata, the revised Dolby Vision v4.0 trimming metadata the colorist sets through the v4.0 trim controls found in the Dolby Vision palette of the Color page. This more advanced collection of trim commands permits finer control over how the Dolby Vision image is mapped onto a target display (for example, a 100 nit BT.709 display) distinct from the mastering display (for example, a 1000 nit BT.2020 display). As with Level 2 metadata, Level 8 metadata exists to protect a program’s artistic intent by letting the colorist steer how the program’s signal fits into the differing luminance ranges of displays of varying peak luminance capability. Hand-adjustable Level 8 metadata is available to DaVinci Resolve Studio users solely via a license obtained from Dolby. Which set you use — the Level 2 trim controls or the Level 8 trim controls — hinges on the Dolby Vision version setting you pick in the Color Management panel of the Project Settings.

NOTE: At present every user is advised to select Dolby Vision v4.0 for both analysis and trimming, since it yields better results. Should you need to supply Dolby Vision v2.9 metadata when mastering for backwards compatibility, DaVinci Resolve is now able to export v2.9 metadata out of projects built on v4.0 workflows. The metadata levels outlined above reflect the situation as of this writing. Because Dolby Vision evolves quickly, though, you should consult Dolby’s website to stay abreast of new features and metadata levels as Dolby introduces them: https:// professionalsupport.dolby.com/s/article/Dolby-Vision-Metadata-Levels?language=en_US

Setup and Workflows | HDR Viewers HDR Setup and Grading

For some time to come, the consumer display field will include a broad mix of televisions and projectors with differing performance, all but certain to get better year after year. The upshot is that grading for the displays of today can leave content looking less vibrant than material produced five years down the road. That is particularly frustrating for narrative work destined to live a long time on streaming services, where fresh waves of viewers keep finding it. One remedy would be to re-grade your program repeatedly at assorted nit levels so you have deliverables matched to a span of display capabilities — but that is a staggering amount of labor. Dolby Vision provides a shortcut, applying advanced algorithms to derive auto-analyzed metadata that smartly directs the reshaping of a picture graded at a single nit level (4000 nits, for instance) so it appears perceptually equivalent to a viewer on a 1000 nit display. Highlights and saturation too intense for a given display are reined in so as to preserve nearly the same impression without clipping or flattening detail. On top of that, a colorist can manually trim this automatic analysis to honor the program authors’ artistic aims wherever the auto pass falls short of what’s desired. That pairing of auto-analysis with manual trimming is central to how Dolby Vision simplifies mastering programs for backward compatibility with SDR displays and for the assorted peak luminance capabilities of various makes and models of HDR consumer displays, now and going forward. You need only perform a single 100 nit trim pass to direct the HDR program’s downconversion all the way to SDR, and the Dolby Vision system can lean on that data to determine how intermediate presentations (for instance, at 700 or 1200 nits) ought to be adjusted. You may even run several trim passes at chosen nit levels, like a 100 nit pass plus a 1000 nit pass, giving the Dolby Vision system richer information to steer intermediate presentations across different displays accurately. Moreover, trimming every clip isn’t necessary. Where the analysis holds up, you can leave those clips alone and trim only the ones that call for it. The system as a whole was designed to be as efficient as possible for colorists so the broadest range of viewers see the image the way it was intended. That, in essence, is what makes the Dolby Vision system valuable. It’s possible to grade on a more future-proofed 4000 nit display, then lean on auto-analysis plus one or two hand-done trim passes to keep things backward compatible with SDR televisions, all while the HDR highlights are scaled intelligently to deliver the best possible rendition of the mastered picture for whatever peak luminance and color volume a given television can manage. Every part of this is driven by the choices the colorist makes during the grade. Currently, every one of the seven major Hollywood studios masters in Dolby Vision for cinema. Among the studios that have committed to mastering content in Dolby Vision for home distribution are Universal, Warner Brothers, Sony Pictures, and MGM. Content providers that have signed on to distribute streaming Dolby Vision content include Netflix, Vudu, and Amazon. And if you’d like to watch Dolby Vision content on a television at home, consumer television makers LG, TCL, Vizio, HiSense, Sony, Toshiba, and Bang & Olfusen have all released models that support Dolby Vision.

### Organizing Your Timeline for Dolby Vision Mastering

Among the very first tasks before starting a Dolby Vision grade is arranging your timeline to suit it. Since every clip is run through a visual analysis to support the Dolby Vision workflow, particular restrictions apply to how clips may be laid out in a timeline.

- Any clip you want analyzed in a Dolby Vision workflow has to sit on video track V1; clips on the other tracks are disregarded.
- Clips that overlap one another to form a composite must be consolidated into a single timeline item before they can be analyzed properly. In practice, that means every cluster of clips forming a composite in a timeline — whether overlapping clips joined through keys or alpha channel transparency, overlapping clips joined via composite or blend modes, or text generators sitting over one or more video clips — has to be converted into a compound clip for Dolby Vision analysis to function correctly.

Setup and Workflows | HDR Viewers HDR Setup and Grading

### Letterboxing for Dolby Vision Mastering

When a Dolby Vision workflow analyzes clips, it records both the timeline aspect ratio and the image aspect ratio of each clip within that timeline. The Dolby Vision analysis can handle programs that combine various aspect ratios of letterboxing (or blanking); however, Dolby Vision won’t support letterbox on two sides at once (both pillarbox and letterbox), only one at a time.

### Setting Up Color Management for Dolby Vision Mastering

So that an HDR signal displays correctly, you have to output your graded program with the EOTF appropriate to the HDR standard you’re mastering. That EOTF translates the various levels DaVinci Resolve sends to your HDR display, using the SMPTE ST.2084 PQ setting that Dolby Vision output requires. There are three ways to configure this:

- Output Color Space and Gamma settings in RCM or ACES
- Color Space and Gamma settings inside a chain of Resolve FX Color Transform plugins that

you place after each individual grade or following a Timeline grade

- 3D LUTs that convert signals from one standard into another, dropped in after

each clip’s grade or once a Timeline grade is complete Although Dolby Vision content isn’t tied to any one color space, Resolve Color Management offers a P3 D65 setting that lines up with what most mastering displays in use as of this writing can do.

### Choosing Mastering Displays for Dolby Vision

Performing HDR grading requires an appropriate HDR display. In principle, any monitor that supports SMPTE ST.2084 (aka PQ) will do the job. Fortunately, an expanding lineup of professional displays from Sony, Flanders Scientific, TV-Logic, Canon, and Eizo is well suited to HDR grading suites. EBU Tech 3320 lays out the requirements for a Grade 1 HDR mastering monitor. Dolby suggests these minimum specifications for HDR monitors:

- A minimum Peak Luminance of 1000 nits
- A 200,000:1 contrast ratio
- Minimum black at 0.005 nits
- Capable of at least 99% of P3 gamut To learn more about Dolby’s recommended practices for color grading Dolby Vision, head to: https://www.dolby.com/us/en/technologies/dolby-vision/dolby-vision-for-creativeprofessionals.html.

### Using the Dolby Vision Internal Content Mapping Unit (iCMU)

DaVinci Resolve includes a GPU-accelerated “internal” software implementation of the Dolby Vision CMU (Content Mapping Unit), letting you preview Dolby Vision mapping directly inside DaVinci Resolve. You enable and configure iCMU support in the Color Management panel of the Project Settings by switching on the Enable Dolby Vision checkbox. It’s available only in DaVinci Resolve Studio.

Setup and Workflows | HDR Viewers HDR Setup and Grading

Dolby Vision settings in the Color Management panel of the Project Settings Beyond that, the Dolby Vision group of settings surfaces menus for picking which version of Dolby Vision to run, the analysis type and the Master Display kind you’re working with, and whether to use an eCMU (provided you have that option). There are also options to turn on HDMI tunneling (covered below). Lastly, enabling Dolby Vision likewise activates the Dolby Vision palette and controls on the Color page, which this chapter explains more fully later on. Mastering with Dolby Vision in DaVinci Resolve through the built-in iCMU still demands a more particular hardware configuration than a typical grading and finishing workstation, made up of the equipment below:

- Your DaVinci Resolve grading workstation fitted with a DeckLink 8K Pro or DeckLink 4K Extreme

12G video interface.

- A mastering display that can output HDR nit levels appropriate to the deliverable you must

produce

### Simultaneous Master and Target Display Output for Dolby Vision

While mastering HDR and trimming versions for more constrained displays, being able to judge your HDR grade alongside your SDR trim pass is enormously helpful. You can send out the Master Display output and the Target Display output at the same time whenever you grade with either Dolby Vision or HDR10+ turned on.

### Necessary Hardware

To work in this manner, you must have the following equipment:

- Your DaVinci Resolve grading workstation has to output through a DeckLink 8K Pro by way of the attached HDMI card. That carries the Dolby Vision metadata onward to the SDR display, letting you see the SDR derived from the HDR grade.
- Your Mastering Display has to handle HDR nit levels appropriate to the deliverable you must produce.
- A display you can configure to output calibrated SDR, most likely using the BT.709 gamut

Setup and Workflows | HDR Viewers HDR Setup and Grading

### Enabling Simultaneous Monitoring

As you wire up your display hardware, attach the HDR Master Display to output A and the Target Display to output B of whatever BMD video output device you’re using. After that, within the Master Settings of the Project Settings, tick the “Use dual outputs on SDI” checkbox. From there, provided every connection is mutually compatible, you should get an HDR image sent to your HDR display and a trimmed image sent to your SDR display.

### HDMI Tunneling using DeckLink 8K Pro G2
