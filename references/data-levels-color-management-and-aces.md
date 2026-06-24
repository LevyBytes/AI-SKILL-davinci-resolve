# Data Levels Color Management And Aces (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Data Levels, Color Management, and ACES

The material here walks through the practical mechanics governing how color gets handled for media moving into and out of DaVinci Resolve. When getting color right matters to you, it pays to dig into the way Resolve treats each clip's data levels, the way DaVinci Resolve Color Management lets you juggle assorted formats, and the way ACES is put to use.

### Data Levels Settings and Conversions

Each media format encodes image data across its own span of values. Because those data formats tend to line up with distinct output pipelines (cinema versus broadcast), knowing the origin of your project's media files and their intended destination helps you set the various data range options in DaVinci Resolve correctly and keep your program's data sound. Broadly speaking, for 10-bit image values (spanning a numeric range of 0–1023), two separate data levels (or ranges) are available for holding image data when you write to media file formats like QuickTime, MXF, or DPX. The ranges go like this: Video: Generally the choice for Y’CBCR video data. Every image value between 0 and 100 percent has to land inside the numeric range of 64–940. To be precise, the Y’ component runs 64–940, whereas the CB and CR components occupy a numeric range of 64–960. The bottom band of 4–63 is set aside for “blacker-than-black,” and the top bands of 941/961–1019 are set aside for “super-white.” Source media captures these “out of bounds” ranges as undershoots and overshoots, yet broadcast output won't accept them. Full: The usual pick for RGB 444 data pulled from digital cinema cameras, or film scanned into DPX image sequences. Here all image data spanning 0 to 100 percent simply maps onto the full numeric range of 4 to 1023. Bear in mind that any digital image, regardless of its format, carries hard minimum and maximum levels, which this section calls 0–100 percent. Any time media in one data range is converted to a different one, every color component's lowest and highest data levels get remapped: the former minimum is scaled to the new data level minimum, and the former maximum is scaled to the new data level maximum;

- (minimum Video Level) 64 = 4 (Data Level minimum)
- (maximum Video Level) 940 or 960 = 1023 (Data Level maximum)

### Converting Between Ranges and Clipping

Moving an image from one data range to another ought to be an invisible operation. The full set of “legal” data from 0–100 percent is always retained and gets linearly scaled out of the old data range and into the new one. What this skips over are the undershoots and overshoots you set on purpose, otherwise called out-of-bounds levels. The overshoots and undershoots permitted in “Video Levels” media (the ones we call sub-black or super-black and super-white) typically get clipped on conversion to full-range “Full Levels.” That said, DaVinci Resolve holds onto this data behind the scenes, so those clipped pixels of detail in the undershoots and overshoots can still be recovered by dialing in the right adjustments on the Color page to pull them back inside the “legal” range. While you work, the out-of-bounds image data that DaVinci Resolve keeps in the headroom of Video Levels usually gets clipped, though, the moment you output to video or render your output. Two settings exist to sidestep that whenever you want these levels kept:

Within the Video Monitoring group of the Master settings sits a checkbox, “Retain sub-black and superwhite data,” which permits DaVinci Resolve to send undershoots (sub-black) and overshoots (super-white) out to video whenever Data Level is set to Video. Leave it off and those out-of-bounds values are clipped at output. Over in the Advanced settings of the Deliver page's Render settings, a checkbox named “Retain sub-black and super-white data” permits DaVinci Resolve to render undershoots (sub-black) and overshoots (superwhite) into exported media while Data Level is set to Video.

### Internal Image Processing and Clip Data Levels

Worth knowing: inside DaVinci Resolve, every bit of image data is handled as full range, uncompressed, 32-bit floating point data. Practically, that means each clip in the Media Pool, no matter its starting bit-depth or data range, gets scaled up into full-range 32-bit data. The scaling applied to any given clip follows its Levels setting in the Clip Attributes window, which you reach from the Media Pool contextual menu.

### Selecting Auto, Video, or Full levels

Promoting every clip to uncompressed, full-range, 32-bit floating point data is how Resolve ensures the best possible image processing. Naturally, how good your output looks still hinges on how good your source media is, yet you can rest assured that Resolve holds onto all the data the original media carried.

### Assigning Clip Levels in the Media Pool

The first time media lands in the Media Pool, whether you brought it in by hand on the Media page or it arrived automatically through an AAF or XML project imported on the Edit page, Resolve hands it the “Auto” Levels setting. With a clip on Auto, the Levels setting in play is worked out from the codec of the source media. For the most part DaVinci Resolve does a solid job picking the right Levels setting for each clip without help. There are situations, though, like footage that began life in one format and was then transcoded into another, where you'll need to pick the correct settings yourself so each clip's levels read properly. You manage that via each clip's Levels setting in the Clip Attributes window, which the Media Pool contextual menu exposes on either the Media or Edit pages. Here's how to reassign a clip's Data Level setting: 1 Bring up the Media page or the Edit page. 2 Highlight one clip or several, then right-click any of them and pick Clip Attributes. 3 Click whichever Levels ratio button matches the data level you mean to apply, and confirm with OK. TIP: When you have to adjust the Levels setting for a batch of clips that share some distinct property like reel name, resolution, frame rate, or file path, switch the Media Pool to column view and sort on whichever column most cleanly isolates the media you intend to give a data level assignment.

As soon as you alter a clip's Levels setting, that clip is reconverted on the spot according to the fresh assignment. Looks right? Then you're good to go. Looks wrong? Then it's worth rethinking the Levels assignment you chose, and you'd do well to ask whoever supplied the media how it was generated, captured, and exported. Provided the Levels settings on your clips are correct, you should be set to start working. Even so, trouble can still crop up depending on which external video hardware your workstation is paired with and how your client needs the finished media delivered. That's why three more data level settings exist, letting you protect data integrity while still seeing the correct image as you work.

### Video Monitoring Data Levels

Cosmetic issues can crop up when the settings on your external display don't line up with the settings Resolve uses to process data levels. To address that, a Video/Full Level setting lives in the Master Settings panel of the Project Settings (under the Video Monitoring section). Adjusting it should shift the picture sent to your external display, while leaving the picture in your Viewer untouched. The reason is that this setting governs only the data levels going out over the video interface that links the Resolve workstation to your external display. It changes nothing about the data Resolve crunches internally, nor the files produced when you render on the Deliver page. Two choices are offered: Video: The right pick when your broadcast display sits on the Rec. 709 video standard (10-bit 64–940). Full: Where a monitor or projector of yours can present “full range” video signals and you'd like to watch the entire 10-bit data range (4–1023) as you work, this is the one to use. The option you set in DaVinci Resolve absolutely must agree with the data range your external display is on. If it doesn't, the video signal will look wrong, even while DaVinci Resolve is processing the internal data correctly.

### Auto/Video/Full Level selection for monitoring

### Deck Capture and Playback Data Level

A distinct “Video/Data Level” setting applies specifically to capturing from or sending to VTRs. It likewise shapes the video signal pushed out over the video interface tying the Resolve workstation to your VTR (a link that usually doubles as part of the monitoring signal chain). Yet it only kicks in while you're capturing from tape on the Media page or editing to tape on the Deliver page. Should you never capture from or output to tape, this setting stays dormant. You'll find it in the Deck Capture and Playback panel of the Project Settings.

Tape capture and output get their own option because you'll frequently want monitoring in one format (normally scaled Rec. 709) while writing to tape in another (full range RGB 444). With this, you can configure Resolve to support that workflow and spare yourself the chore of toggling your video interface by hand. Two choices exist: Video: The right pick when your goal is sending standard Rec. 709 video to a compatible tape format. Full: The right pick when your goal is sending “full range” RGB 444 video to a compatible tape format. After a tape ingest or output wraps up, your video interface reverts to whatever the “Colorspace conversion uses” option dictates, found within the Project Settings under Master Settings (in the Video Monitoring section).

### Output Data Level Settings in the Deliver Page

Last of all comes one final group of data level settings, sitting in the Render Settings list inside the Format group. This is the “Set to video or data level” drop-down menu. Its purpose is to let you convert your rendered output's data level whenever that's needed. Every piece of media goes out at one data level, which one depending on your choice. Three options are available: Automatic: The output data level for all clips is chosen automatically from the codec you target in the “Render to” drop-down menu. Video: Every clip is rendered as normally scaled for video (10-bit 64–940). Full: Every clip is rendered as full range (10-bit 4–1019). On the majority of projects, leaving this on “Automatic” produces the right outcome. But when you're rendering media destined for another image processing application (a compositing application, say) that can cope with “full range” data, full range output is the better choice for media exchange because it carries the highest data fidelity. As an example, when you send media off for VFX work in the form of a DPX image sequence, or instead a ProRes 4444 encoded QuickTime file, choosing “Unscaled full range data” secures the best image quality on offer. It's vital, though, that whatever application processes this media is configured to interpret it as “full range” data, or else the images won't display correctly.

### So, What’s the “Proper” Data Range for Output?

Honestly, there's no single “proper” data range you must use when you output image data. So long as each clip's Levels setting in the Media Pool mirrors how that clip was made, your main concern becomes which data range suits the media format or application you're handing off to. When the media format you're exporting to accepts either normally scaled or full range, and the application the media will be brought into accepts either as well, then the decision is genuinely yours, provided everyone touching the project grasps how the media's data range is supposed to be read once it reaches them.

Sending output to hardware gets a little thornier, because you have to confirm the external display or VTR receiving it is configured to take a signal in the data range you picked. When a device handles just one data range, you have to be certain you're feeding it that data range, otherwise the image levels will look off even though the image data Resolve is processing is perfectly fine.

### Introduction to DaVinci Resolve Color Management

The way color gets handled in DaVinci Resolve comes down to the “Color Science” setting, which sits atop the Project Settings' Color Management panel. Four choices appear there: DaVinci YRGB, DaVinci YRGB Color Managed, DaVinci ACEScc, and DaVinci ACEScct. The focus of this section is the second one, DaVinci YRGB Color Managed. ACEScc and ACEScct get their own treatment in the next section of this chapter.

### Display Referred vs. Scene Referred Color Management

The default DaVinci YRGB color science setting, the one DaVinci Resolve has employed from the start, leans on what's termed “Display Referred” color management. In other words, Resolve knows nothing about how the source media on the Timeline is meant to appear; the only way to gauge color accuracy is through the calibrated broadcast display you send output to. You, in effect, are the color management, paired with a dependable broadcast display calibrated for accuracy. With DaVinci Resolve 12 came a color science option named “DaVinci YRGB Color Managed,” or just “Resolve Color Management” (RCM) for short. That brought in a so-called “Scene Referred” color management scheme, under which you can pair each kind of media you've imported into your project with a color profile telling DaVinci Resolve how to render every individual color from each clip's native color space inside the shared working color space of the timeline where you edit, grade, and finish. This carries weight because two clips holding the same RGB value at a given pixel might genuinely depict different colors there, depending on which color space was originally tied to each captured clip. That happens when you set raw clips from cameras built by different manufacturers side by side, and it's all the more true comparing clips recorded in the distinct log-encoded color spaces particular to each camera. The Scene Referred part of color management through RCM won't grade for you, but it does aim to keep the color and contrast from every different media format you've imported into your project faithfully represented across your timeline. Take an example where two cameras from different makers shoot green trees, one recording in Blackmagic Film color space and the other in the Sony SGamut3.Cine/SLog3 color space; you can now lean on RCM to align the green of the trees in one batch of clips with the green in the other, inside the Timeline's shared color space. It's worth noting that the same result can be achieved by hand in a more traditional Display Referred workflow, by attaching LUTs tailored to each media type, or by applying Color Space Transform Resolve FX to carry each clip from the source color space into whichever destination color space you need. RCM's automation, though, can speed this up by sparing you from having to track down and maintain a big pile of LUTs to cover

all your different workflows. On top of that, the matrix math behind RCM (and behind the Color Space Transform operation too) pulls high-precision, wide-latitude image data out of each supported camera format, holding onto high-quality image data right through acquisition, editing, color grading, and output. Every one of these is a plus over lookup tables, which may offer ample precision yet can clip out-of-bounds image data and stir up trouble when varying lookup table interpolation methods produce small inconsistencies in color space transformations as you move between applications. The way wide-latitude image data is preserved warrants more detail. A LUT clips image detail straying past the numeric range it was built to cover, which often forces the colorist into a pre-LUT adjustment to “pull back” the highlight image data they hope to recover. RCM does away with that two-step dance, since the input color space matrix operations transforming the source keep all wide-latitude image data, leaving highlights easy to retrieve with no further steps.

### Updated RCM In DaVinci Resolve 17

With version 17, DaVinci Resolve rolled out the largest set of upgrades to Resolve Color Management (RCM) since its debut, piling on features that streamline setup, lift image quality, and steady the “feel” of your grading controls. Among the concrete gains are better metadata management for arriving media files that carry color metadata, a fresh wide gamut color space well suited to serving as your default Timeline working color space on any program, a new Input Tone Mapping option (Input DRT) that smooths out mixing media formats across SDR and HDR grading, an upgraded Timeline to Output Tone Mapping (Output DRT) with stronger shadow and highlight handling, and a handful of color space-aware grading palettes whose controls feel and behave well whatever you happen to be grading. This refreshed Resolve Color Management keeps the same name as its predecessor. Older projects built on the prior RCM, however, will show Color science set to Legacy, so their earlier color management settings and the effect of their color transformations stay intact. To read up on how the previous generation of RCM operates, turn to the September 2020 release of the manual for DaVinci Resolve 16. So how does DaVinci Resolve Color Management differ from ACES? People ask this a lot, though the answer is fairly straightforward. Resolve Color Management (RCM) and ACES are each Scene Referred color management schemes built to tackle the same problem. Still, when you're not inside a dedicated ACES-driven cinema workflow, DaVinci Resolve Color Management can prove easier to handle and hands you every benefit of color management while staying close to the “feel” that the DaVinci Resolve Color page controls have always delivered.

### Resolve Color Management for Editors

Colorists aren't the only ones RCM serves. It can be a friendlier tool for editors whenever the source footage is log-encoded. Log-encoded media holds onto highlight and shadow detail, a boon for grading and finishing, yet it reads flat and unappealing, which is awful for editing. Even with zero color correction know-how, flipping RCM on in the Color Management panel of the Project Settings is easy, after which you use the Media Pool to assign the specific Input Color Space matching the source clips from each camera. Once that's in place, the default Timeline Color Space of Rec. 709 Gamma 2.4 is applied automatically to every log-encoded clip. Editors, as a result, can be cutting with nicely normalized clips on the Edit page without ever opening the Color page.

### The Input, Timeline, and Output Color Space

Three core settings form the bedrock of Resolve Color Management. You can pin down the color science of each separate source clip either automatically or by hand (that's the Input Color Space), you hold direct command over the working color space in which every color adjustment and operation takes place (the Timeline Color Space), and you wield independent command over the Output Color Space that dictates how your graded image is monitored and output. In essence, then, Resolve Color Management amounts to two color transforms operating in tandem: one carrying each source clip, by way of its Input Color Space definition, into the Timeline Color Space where you work, and another carrying the adjusted image from the Timeline Color Space out to whichever Output Color Space the project's delivery demands.

### Input Color Space

### Timeline Color Space

### Output Color Space

Resolve Color Management is made up of three color transforms operating in concert. The upshot for you as a colorist is that you're free to set the Timeline Color Space you grade in to whatever suits you. Should you favor grading wide-gamut log media because of how the grading controls respond in that color space, then within the Project Settings' Color Management panel you can aim the Timeline Color Space at DaVinci Wide Gamut (covered further below), or at any of the offered log formats, among them ARRI Log C, REDWideGamutRGB/Log3G10, and Cineon Film Log. If instead you'd rather grade in Rec. 709 color space, perhaps because the program is a standard dynamic range (SDR) master bound for Rec. 709 and you feel more at home with how the DaVinci Resolve controls have always behaved there, that option is open to you too. Whichever Timeline Color Space you pick is the one all source clips get transformed into when you make grading adjustments on the Color page, so a single setting decides it. A major upside of the color space conversions RCM performs: not one bit of image data is ever clipped while the Input to Timeline color space conversion runs. Even with a log-encoded source or a camera raw format, for instance, grading against a Rec. 709 Timeline Color Space does nothing to clip or otherwise constrain the image data feeding the RCM image processing pipeline. Every image value above 1.0 or below 0.0 survives and is handed to the next RCM processing stage, the Timeline to Output color space conversion. As a result, grading in a color space that isn't your output target means you needn't fear data loss when the color transformation carries you back to the color space you actually intend to output to. The Output Color Space setting lets you work in whatever Timeline Color Space you fancy while grading, with Resolve automatically converting your output into the precise color space you want to monitor and deliver in. And because the image processing in DaVinci Resolve is so precise, you can move from a larger color space to a smaller one and back with no clipping or quality loss. Naturally, applying a LUT or invoking Soft Clip inside a grade will introduce clipping, but that's simply what those particular operations do.

TIP: When you'd like to run Resolve Color Management but have the Input and Output Color Spaces track whatever you've set the Timeline Color Space to, select “Bypass” in the “Input Colorspace” and “Output Colorspace” drop-down menus. In the end, the Output Color Space is what sets the final color space of your rendered result. No image data is clipped over the Source to Timeline color space conversion, yet image data does get clipped over the Timeline to Output color space conversion so the final image fits the color space being rendered and output, unless you turn to the Gamut Mapping options to compress image data during that Timeline to Output Color Space conversion.

### The RCM Image Processing Pipeline

What came before is, of course, a simplification. For advanced users wanting clarity on how Resolve Color Management runs under the hood, the flowchart below lays out a basic picture of how all the parameters cooperate to automatically manage the color of clips throughout your program.

### Resolve Color Management Parameters

### Timeline Working Luminance

### Affects Input DRT

### Source Media

### Input Color Space

### Input DRT

### Timeline Color Space

### Your Grade

Sourced from any of these: Manual Color Space Tagging, the Source Media Color Space Metadata, else the Input Color Space Project Setting

A diagram of the image processing pipeline behind Resolve Color Management

### Affects Output DRT

### Output DRT

### Ouput Color Space
