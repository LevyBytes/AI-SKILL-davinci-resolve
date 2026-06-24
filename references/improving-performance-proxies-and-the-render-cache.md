# Improving Performance Proxies And The Render Cache (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Improving Performance, Proxies, and the Render Cache

### Improving

Performance,

Proxies, and

the Render Cache

As a high-performance application, DaVinci Resolve is built to deliver real time effects across a wide range of workstations. This section lays out the assorted ways you can keep an eye on your performance to confirm real time playback is holding, together with a number of methods for tuning real time performance, among them on-the-fly proxies and the background Render Cache.

### Understanding the GPU Status Display

Each viewer in DaVInci Resolve carries a GPU status indicator plus a frame-per-second (FPS) meter, both sitting in the Viewer’s title bar, that report your workstation’s performance the moment playback begins. Because DaVinci Resolve leans on one or more GPUs (graphics processing units) for all image processing and effects, the GPU status display reveals how much processing power whatever clip is playing happens to be drawing.

### Frame rate and GPU indication, green is good

When the status indicator glows green, there’s ample GPU processing headroom to spare. As the demand on GPU resources mounts, that green graph eventually shifts to red, signaling that the GPU power on hand can’t sustain steady real time playback.

Red means playback has dropped below real time Sooner or later, as you stack on more and more effects and corrections, you’ll hit the ceiling of available performance, which pushes DaVinci Resolve to either drop frames or slow the video down to preserve high image quality — a state the red FPS indicator flags. Whenever real time performance comes up short, DaVinci Resolve offers an assortment of controls and options for boosting real time playback and effects. Each suits a different scenario, and they all combine, letting you strike the best balance between image quality and performance as you work. Every one of these methods can be configured so it leaves your delivered output untouched.

### Prioritizing Audio or Video Playback in the Edit Page

When there isn’t enough processing power to play the clip or clips sitting under the playhead — owing to the grade, transforms, or effects active at that spot in the Timeline — you get to dictate precisely how DaVinci Resolve’s performance degrades, by toggling “Show All Video Frames” on or off from the Edit page Viewers’ Option menu. Show All Video Frames off: This is the default, well-suited to video editing. It favors audio playback and lets video frames drop when processing power runs thin, giving a more conventional playback feel. Show All Video Frames on: An alternative that shines during effects work, where you need to watch every single frame play in sequence. Audio takes a hit while each video frame plays slower-than-real-time, where necessary, to keep playback going. Bear in mind this setting comes into play only when GPU performance is wanting. Across stretches of the Timeline where performance is sufficient, playback stays uncompromised.

### Performance Mode Improves Overall Performance

Performance Mode, located in the Playback Settings of the User Preferences, sizes up your computer’s configuration — the CPU, GPU, connected video interface, and the rest — and automatically tunes DaVinci Resolve’s behind-the-scenes image processing settings to deliver the best interactivity on your machine. By default it’s on Automatic, though you’re free to adjust its impact by hand or shut it off entirely. With it enabled, Performance Mode markedly improves how editing, mixing, and grading feel on less powerful computers. Even while Performance Mode is on, DaVinci Resolve continues to output to video, render in the Delivery page, and process through the Media Management command at top quality. So Performance Mode sacrifices nothing in the quality of your output, which means creative editors and audio mixers can keep this setting on at all times. On less powerful computers, finishing editors and colorists may catch subtle differences in the image on your computer monitor between Performance Mode on and off, and that’s precisely why the setting can be switched off — wholly or partly via checkboxes in the Playback Settings panel of the User Preferences — for cases where GUI interactivity matters less than what’s on your onscreen display.

### Adjusting Performance Mode

Within the Playback Settings panel of the User Preferences, two radio buttons let you pick between Automatic (default) and Manual behavior once you switch on Performance Mode in DaVinci Resolve. On Automatic, Performance mode tunes a range of operations on its own, aiming to weigh performance against the required level of image quality — quick onscreen response while never giving up the highest quality for video output. On Manual, three separate settings are open for you to disable in cases where a given performance tradeoff produces an unacceptably visible drop in image quality under Performance Mode: Optimized Sizing: Concerns the handling of image resizing. Optimized Decode Quality: Concerns the handling of clip resolution against timeline resolution. Optimized Image Processing: Concerns the handling of image processing operations.

### Timeline Proxy Mode Improves Effects Performance

If you’d rather not drop frames or play below real time speed whenever the GPU Status indicator sits in the red, one instant fix is to switch on the Use Timeline Proxies option in the Playback menu. Timeline proxies ease processing demands by drawing on DaVinci Resolve’s resolution independence to drop your clips’ resolution on-the-fly, lifting real time playback performance without your having to spend time caching part or all of the timeline or building optimized media (both covered later).

To turn Use Timeline Proxies on and off:

- Choose Playback > Timeline Proxy Resolution > Half Resolution, Quarter Resolution, or None.

Switching on one of the proxy resolutions cuts the working resolution to either half or a quarter of whatever your project’s current Timeline resolution happens to be. Running at a temporarily lowered resolution lifts your workstation’s real time performance, while Resolve’s resolution independence ensures that every window you draw and every sizing operation you perform scales properly to your project’s actual resolution.

### Proxy Resolution Full 8K UHD

### Width 7680

### Full UHD/Half 8K UHD

### Full-HD/Half UHD/Quarter 8K UHD

### Half-HD/Quarter UHD/Eighth 8K UHD

### Quarter-HD/Eighth UHD/Sixteenth 8K UHD

A table laying out half and quarter proxy resolutions across various television frame sizes

### Height 4320 2160 1080 540 270

IMPORTANT: Timeline Proxy Mode stands wholly apart from, and independent of, the creation of Proxy Media covered later in this chapter. As features, Timeline Proxy Mode and Proxy Media bear no connection to one another.

### Reducing Decode Quality Improves Raw Media Performance

The Use Proxy command lifts performance where grades and effects are what’s pushing your project’s playback below real time, yet Use Proxy does nothing when real time performance is being consumed by the need to debayer raw media. You could of course lift playback performance by investing the time to generate optimized media (see below), or alternatively render to the Fusion Output Cache once the Smart Cache is switched on (covered later in this chapter), but the quickest route is to open the Camera Raw panel of the Project Settings and lower the Decode Quality for the raw media formats in play:

- Decode Quality: Camera raw formats like R3D and F65 admit debayering at varying quality levels. To gain more real time performance, pick a lower quality setting while you work, then bump it back up to a higher quality when you render the final output.

Which resolution-reduction choices you get depends on each raw format’s particular capabilities, but they cover at minimum full, half, and quarter resolution (R3D and Sony Raw add full, half, quarter, eighth, and sixteenth). The Canon RAW, Panasonic Varicam RAW, and Phantom Cine formats are exceptions, decoding only to full resolution. Should you lower the decode quality of raw media formats in your project for the sake of performance, then ticking “Force debayer res to highest quality” — a checkbox in the Deliver page’s Render Settings list — makes DaVinci Resolve render every raw format at the best quality on offer — so there’s no risk of forgetting to restore the decode quality when the moment comes to render your deliverables.

### Optimized Media Improves Overall Performance

When you’re cutting processor-intensive source formats like camera raw, H.264, or 8K media and your computer can’t comfortably keep up in real time, you can build pre-rendered, lowoverhead duplicate media to edit with in their place, managed automatically alongside the originals. This goes by the name “Optimized Media.” Optimized Media speeds up your work by letting you edit using a more processor-efficient media format and resolution, all while keeping the ability to flip your project back to the original source media anytime you wish. In other words, you edit with Optimized media and revert to the original source media once it’s time to finish and output. Flipping between them is as simple as picking, under the Playback menu, Use Optimized Media if Available — that command toggles Optimized media on and off. One advantage of optimized media for working faster is that it’s pre-generated: render it once and the files serve you for the whole stretch of work on that project (unless you alter the raw media’s debayering settings). Optimized media also boosts the playback of clips right across DaVinci Resolve — over on the Media page, plus within the Edit page’s Media Pool and Source Viewer — whereas the comparable yet distinct Fusion Output Cache part of the Smart Cache only helps clips already on the Timeline by caching them at the Timeline resolution. That makes optimized media a fit for editing workflows of every sort. Choosing the Appropriate Optimized Media Format for Your Project You may pick the Format of the optimized media you generate using controls in the Master Settings panel of the Project Settings. Note that the format you select through the “Optimized Media Format” menu governs whether out-of-bounds image data (those so-called “overshoots”), along with Alpha Channels, survive when the clip is cached.

- Preventing Clipping: Reach for 16-bit float, ProRes 4444, ProRes 4444 XQ, or DNxHR 444 whenever you intend to grade with optimized media. That holds especially for HDR grading.
- Preserving Alpha Channels: Note as well that your chosen format decides whether Alpha Channels carry through when the clips being optimized contain them. At present the formats that retain alpha channels are DNxHR 444, ProRes 4444 XQ, ProRes 4444, Uncompressed 16-bit Float, and Uncompressed 10-bit.

### Creating Optimized Media

Building optimized media to work with is straightforward. Resolve looks after the link between source clips and the optimized media you produce on its own, so your only job is to decide which clips get optimized media. You can hand-pick the clips to optimize, or lean on a Smart Bin to procedurally round up every clip matching one or more formats you need optimized. Either way, you’re free to optimize only the clips in formats that actually call for it, which saves time. Say you’re cutting a project that’s half camera raw media and half DNxHD media; you likely need only the camera raw media optimized, so you can build a Smart Bin that pulls all of it together by Resolution, Codec, File Name, or whatever other metadata fits. With it gathered, selecting all those clips for the next step is simple. To build optimized media for one or several selected clips: right-click any one of them and, from the contextual menu, choose Generate Optimized Media.

Every bit of optimized media lands in the same directory the Cache files use, which by default is the first scratch disk shown in the Preference dialog’s Media Storage panel. You can also point the Cache and Optimized files elsewhere through the “Cache files location” setting, which lives in the Project Settings under the Master Settings panel.

### Optimized Media for Raw Source Clips

As a rule, after you’ve generated optimized media, DaVinci Resolve tracks it and keeps drawing on it no matter what changes you bring to your project, the Timeline resolution included. That said, altering the camera raw settings of optimized clips automatically throws out their optimized media, leaving you to re-generate it for those clips.

### Customizing the Type of Optimized Media You Create

A group of controls in the Master Settings panel of the Project Settings dictates which sort of media files come out when you generate optimized media.

The Project Settings’ Master Settings panel and its options for producing optimized media Two settings touch Optimized Media within the Optimized Media and Render Cache section:

- Resolution: Lets you decide whether optimized media is built at the same size as your original media files (pick Original) or whether its bandwidth is trimmed further by cutting its resolution to a Half, Quarter, Eighth, or Sixteenth. The “Choose automatically” option seeks a balance of visual quality and efficiency by lowering the resolution only of media files larger than the Timeline resolution you’ve currently selected, applying whatever reduction ratio best fits the Timeline resolution.
- Optimized Media Format: Lets you set the format and codec used to generate optimized media. Choices run to Uncompressed 10-bit and Uncompressed 16-bit float for top quality. Further choices span ProRes Proxy up through 4444 XQ and DNxHR LB up through 444. Every choice stores image data in the optimized, proprietary .dvcc image format. Smaller formats eat up less of your scratch disk, yet there are two solid reasons to opt for higher-quality formats when making Optimized Media.

Preventing Clipping: Keep in mind that your chosen format settles whether out-of-bounds image data survives once the signal is optimized. Should you notice image data (usually superwhite levels) getting clipped after optimization, move to 16-bit float, ProRes 4444, or ProRes 4444 XQ; in fact, any of these three codecs make suitable optimized formats for HDR grading. Preserving Alpha Channels: Keep in mind too that your chosen format settles whether Alpha Channels endure when the clips being Optimized hold them. At present the formats that retain alpha channels are DNxHR 444, ProRes 4444 XQ, ProRes 4444, Uncompressed 16-bit Float, and Uncompressed 10-bit.

### Choosing Resolution Automatically

The Resolution setting’s “Choose automatically” option deserves a little more detail. With it on, only source media whose resolution tops the chosen Timeline resolution yields downsized optimized media. The degree to which each clip is downsized tracks how far it exceeds the Timeline resolution. Working in a 1080 resolution project, for instance, 8K clips produce quarter-resolution optimized media and 4K clips produce half‑resolution optimized media, so that all the optimized media lands roughly around 1080 resolution. Clips at 1080 and below produce optimized media at the same resolution as their source clips. In a 4K project, by contrast, 8K clips produce half-resolution optimized media, and every other clip at 4K or smaller produces optimized media at the source clips’ own resolution.

The Proxy Resolution tiers run as follows: Full 8K UHD; then Full UHD/Half 8K UHD; next Full-HD/Half UHD/Quarter 8K UHD; after that Half-HD/Quarter UHD/Eighth 8K UHD; then Quarter-HD/Eighth UHD/Sixteenth 8K UHD; and finally Eighth-HD/Sixteenth UHD — a table of optimized resolutions spanning various television frame sizes

### Width 7680 3840 1920 960 480 240

### Height 4320 2160 1080 540 270 135

### Switching Between Optimized and Original Media

Deciding whether or not you’re on optimized media takes no effort. Just choose Playback > Use Optimized Media if Available to flip your whole project between optimized media (when it exists) and the original media. On top of that, a checkbox in the Render Settings of the Deliver page lets you decide whether to render faster with optimized media or to render off the original media alone.

NOTE: Optimized media plays no part in Media Management operations, nor does it figure into Archive operations within the Project Manager.

### Sharing Optimized Media Between Projects

Optimized Media now carries across every project within the same project library (it used to be locked to one project). So if you generate optimized media for a clip in one project, that very same optimized media serves that clip in any other project sitting in the same project library. The whole thing is automatic and asks nothing of you. It sharply trims the space you need when working with the same media spread across different projects.

### Rediscovering Lost Optimized Media

Hard as it is, under certain rare conditions you can still lose track of optimized media you’ve made. Say you generate optimized media on a different workstation but neglect to save the project; DaVinci Resolve may then lose the link tying your Media Pool clips to the optimized media files you built. When that happens, you can rediscover the optimized media and spare yourself a regeneration. To rediscover lost optimized media: within the Media Pool, select the clips you know carry optimized media, then right-click any one of them and pick Rediscover Optimized Media out of the contextual menu.

### Deleting Optimized Media

Whatever optimized media you generate inside a project sticks around; it’s kept for later use even after the project is closed and reopened down the road. If you need to clear optimized media to reclaim space on your scratch volume (or wherever you’ve chosen to keep your project’s cache files), you have to delete it by hand in your OS. By default, the Optimized Media lives on the first volume named in the Media Storage tab of the System Preferences.

### Using Optimized Media for Delivery

Sitting in the More options section of the Render Settings on the Deliver page, the “Use Optimized Media” option lets you output from Optimized Media instead of the original media to shave off rendering time. If this option is part of your plan, it’s wise to set the Optimized media format to a fittingly high-quality, HDR-capable format so the results come out their best.

### Using the Smart or User Cache Improves Effects Performance

One more way to reach real time performance, when the GPU Status indicator goes red because of Timeline effects, Color page grading, or processor-intensive media on the Timeline, is to engage the Render Cache via its Smart Cache or User Cache modes. What DaVinci Resolve terms “caching” other applications occasionally call “rendering.” Both words point to the off-screen creation of new media, with every effect “baked in,” which DaVinci Resolve then plays back in real time in place of the original source media that carries the processor-intensive effects. The payoff is smooth playback free of dropped-frame risk. Acting on their own, the DaVinci Resolve Smart Cache and User Cache render and cache clips — simple video clips, compound clips, Fusion clips, and nested timelines that bear processor-intensive grades and effects, or ones you flag by hand: right-click any clip on the Color page or Edit page timeline and switch on the Render Cache Clip Output option. With the Smart or User Caches active, the frames of every automatically or manually flagged clip are cached either while the Timeline plays or automatically whenever you pause work, into the “Cache files location” named in the Master Settings panel of the Project Settings.

After clips on the Timeline have been cached, they play back in real time right up until you change them, at which point the now-stale cache files for those changed clips are flushed automatically and a re-cache becomes necessary.

The caching controls as they sit in the Project Settings’ Master Settings panel To put clip caching to work on any page, do one of the following:

- Choose Playback > Render Cache > Smart so DaVinci Resolve automatically caches computationally heavy effects and timeline clips whose formats it deems too processor-intensive for real time playback.
- Choose Playback > Render Cache > User so DaVinci Resolve caches the clips and effects you pick by hand, while also automatically caching the processor-intensive effects (transitions, composites, and Fusion Effects) you designate in the Master Settings of the Project Settings.
- Choose Playback > Render Cache > Off to turn off all render caching.
- On the Color and Edit pages, press Option-R to cycle through Off, Smart, and User.

Choosing the Appropriate Cache Media Format for Your Project You’re free to set the Format of the cached media you produce using controls in the Master Settings panel of the Project Settings. Note that the format you select through the “Render Cache Format” menu governs whether out-of-bounds image data (those so-called “overshoots”), as well as Alpha Channels, survive once the clip is cached.

- Preventing Clipping: Reach for 16-bit float, ProRes 4444, ProRes 4444 XQ, or DNxHR

444 whenever you intend to grade with cached media. That holds especially for HDR grading.

- Preserving Alpha Channels: Note as well that your chosen format decides

whether Alpha channels carry through when the clips being cached contain them. At present the formats that retain Alpha channels are DNxHR 444, ProRes 4444 XQ, ProRes 4444, Uncompressed 16-bit Float, and Uncompressed 10-bit.

### How Cached Media Is Organized

In truth, DaVinci Resolve’s cache mechanism is made up of three separately managed media caches that work in tandem. The point is to keep you moving fast by making sure your timeline edits don’t force a grade to be re-cached and your grade edits don’t force the timeline to be re-cached. Caching runs at three levels: First, Fusion Output Caching Known in earlier DaVinci Resolve versions as the “Source Cache.” Switched on either by enabling the Smart Cache, by turning on Render Cache Fusion Output for a single clip, or by enabling automatic caching of clips bearing Fusion Effects in the Project Settings, it caches the slice of each source media file that shows up in the Timeline in its pre-graded state, for clips meeting the following criteria:

- Clips whose media formats DaVinci Resolve regards as processor-intensive to decode, like H.264, HEVC, and assorted raw camera formats
- Clips carrying Fusion Effects that were added on the Fusion page
