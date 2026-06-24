# Rendering Media (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

The Deliver page now lets you import and export render presets. To store a custom render preset: 1 On the Deliver page, set the Video, Audio, and File options in the Render Settings however you need them. 2 From the Render Settings Option (3-dot) menu, choose Save as New Preset. 3 Type a name for the new preset, then press OK. That new preset then shows up in the Render Settings Option menu, and also as a choice under the Custom Preset Settings icon within the Render Presets row across the top of the Render Settings. To send a custom render preset out to a file: 1 On the Deliver page, open the Render Settings Option (3-dot) menu. 2 Choose the name of the saved preset you want to export. 3 Pick Export Preset from the dropdown menu. 4 With the file browser, give the preset a name and choose where to save it. That new preset becomes available as an .xml file. To bring a custom render preset in: 1 On the Deliver page, open the Render Settings Option (3-dot) menu. 2 Pick Import Preset from the dropdown menu. 3 In your file browser, locate the Render Setting .xml file. 4 Press Open. Your imported preset will now appear within the Render Settings Option menu, and likewise as a choice under the Custom Preset Settings icon within the Render Presets row across the top of the Render Settings. To refresh a custom render preset with new settings: 1 Make whatever changes you like to the Video, Audio or File Render Settings. 2 On the Deliver page, open the Render Settings Option (3-dot) menu. 3 Choose the name of the saved preset you want to update. 4 Pick Update Preset from the dropdown menu. 5 Press the Update Button in the warning dialog. There's no undoing this action. The chosen preset then takes on the new settings you picked.

To remove a custom render preset: 1 On the Deliver page, open the Render Settings Option (3-dot) menu. 2 Choose the name of the saved preset you want to delete. 3 Pick Delete Preset from the dropdown menu. 4 Press the Delete Button in the warning dialog. There's no undoing this action. The chosen preset is then wiped for good from the Render Presets list.

### Choosing a Location to Render

Your very first call when rendering output is deciding where it gets rendered. Fittingly, this is the first batch of controls sitting at the top of the Render Settings parameters.

- Filename: A preview of how the file will be named, drawn from the settings in the File panel covered later. What shows here is shaped by the Custom/Timeline name and File suffix fields, together with the “Use x digits in the filename” settings. You can also edit the editable parts of this filename preview right here.
- Location: Hit the Browse button to pick a directory where the media that DaVinci Resolve outputs should be written. Once you've picked a directory, its path name shows up in the “Render job to” field.

### Single Clip vs. Individual Clips

Although the Deliver page's Render Settings present plenty of options, there are essentially two broad ways to render your project, set by which of the “Render” radio buttons you click within the Output group.

### Render a single clip or individual clips

### Single Clip

Choosing the Single clip option configures a render in which every clip in the session goes out together, as one media file in whatever format you pick. That means you're rendering the chosen range of the session into a single MXF or QuickTime file, or into a single set of image sequences.

- Timecode: Whatever timecode gets written out is set by the “Start timeline timecode at” value of the timeline you're rendering. Media files hold a continuous timecode track, whereas image sequences carry timecode written into each frame’s data header and worked into the file name (as a frame count).
- Frame Rate: When you render a project running mixed frame rates, rendering to a single clip converts every clip across the whole session to the project frame rate, drawing on either the project-wide or clip-specific “Retime process” setting.
- Effects: Render a single clip and most effects get “baked into” the rendered output.

IMPORTANT: Any time clip filtering is on (through the dropdown menu to the right of the Clips button), you can't pick Single Clip rendering. You can tell clip filtering is on by an orange line beneath the Clips button in the UI toolbar.

### Individual Clips

Picking the Individual clips option configures a render where each clip goes out as its own media file in whatever format you pick. You wind up holding as many separate media files as the count of clips within whichever range you picked to render.

- Timecode: The timecode written to each clip is copied straight from the original source media, which makes reconforming media easy for projects moving back and forth between DaVinci Resolve and NLEs.
- Frame Rate: For a project that mixes frame rates, rendering to source keeps every clip on its own native frame rate, which lets round-trip workflows carry on.
- Effects: You decide whether any timeline-based effects get ignored or “baked into” the individual clips by checking or unchecking the Render Timeline Effects box.
- Resolution: You decide whether the individual clips render at the timeline size or at their original source resolution by checking or unchecking the Render at Source Resolution box.

### All Other Render Settings for Output

Here we cover the various render settings on offer for tailoring your output. Some may be hidden depending on which Render Setting mode you picked, but this section lays out the full roster found in the Advanced panel of controls. Pick one of the Easy Setups and certain settings lock while others stay editable, according to what that setup needs. Should none of the Easy Setups fit the job in front of you, leave the Easy Setup dropdown menu on none and choose the settings the task requires by hand.

### Video Panel

Every video-oriented parameter sits in this panel.

### Format and Codec Controls

These top-level parameters decide whether or not video gets rendered, and which format it renders to. Other options may or may not surface depending on which Format, Codec, and Type you settle on.

- Export Video: Switch this checkbox on to render the source video. Switch it off when you want the source audio rendered all on its own; doing so disables every video control and surfaces an Audio Format dropdown menu within the audio section of settings.
- Format: A dropdown menu giving you the container formats currently available on your system. Which options you see hinges on whether Final Cut Pro and QuickTime are installed, and on which operating system you're running. The list keeps expanding as new file formats arrive over time, so check each new version for the newest supported formats.

AVI: A file-based media format, now deprecated, that despite its years holds on to popularity within Windows applications. Handles delivery via these codecs: Cineform, Grass Valley HQ and HQX, plus Uncompressed RGB and YUV. Cineon: A somewhat dated uncompressed image sequence format out of Kodak, made for film scanning and for digital mastering, delivering RGB 10-bit. DCP: Native DCP encoding together with decoding, intended purely to produce unencoded DCP files. Hold a license for Frauenhofer’s EasyDCP and a setting within the Configuration panel of the System Preferences lets you choose between EasyDCP (which makes encrypted DCP output) and the native DaVinci Resolve encoding.

DPX: An uncompressed image sequence format the film industry leans on for mastering and for DCDM mastering delivery; output choices span RGB 10-, 12-, 16-bit integer and half float, alongside RGBA 8-bit. easyDCP: (when installed) Lets you master a DCP or IMF right from DaVinci Resolve once you hold an installed license of Fraunhofer’s EasyDCP software. EXR: The OpenEXR format, a high-dynamic-range image sequence format ILM developed for work needing top quality across many channels. Used for outputting ACES and HDR deliverables. Delivery is available across a range of RGB Half and RGB Float settings. Should you choose the RGB half (DWAA) or (DWAB) compression codecs, one more “Compression level” setting appears so you can dial in how much compression gets applied. IMF: A native IMF encoding choice that exports to the SMPTE ST.2067 Interoperable Master Format (IMF), aimed at tapeless deliverables bound for networks and for distributors, with JPEG2000 encoding handled by a library licensed from Kakadu software. Outputting to IMF takes no extra licenses or plugins. Within the IMF format you get several video tracks, several audio tracks, and several subtitle and closed caption tracks, every one shaped to handle a variety of output formats and languages out of one deliverable. The mechanism wraps a timeline’s distinct video plus audio tracks (the media essences) along with subtitle tracks (the data essences) into one “composition” held inside the Material eXchange Format (MXF). JPEG 2000: Beginning with DaVinci Resolve 15 came encoding and decoding of JPEG2000 through a library licensed from Kakadu software. The implementation fully covers the JPEG2000 Part 1 standard, together with much of Parts 2 and 3. You'll see JPEG2000 used widely throughout IMF and DCP workflows. MJ2: The Motion JPEG 2000 format. Beginning with DaVinci Resolve 15 came encoding and decoding of JPEG2000 through a library licensed from Kakadu software. The implementation fully covers the JPEG2000 Part 1 standard, together with much of Parts 2 and 3. You'll see JPEG2000 used widely throughout IMF and DCP workflows. MP4: Through dedicated MP4 encoding you can export movies encoded in H.264. MXF OP–Atom: A simple standard built on the Material eXchange Format, a file-based media format, often picked for DNxHD delivery. The version meets the SMPTE 390M standard; among its codec options for delivery are DNxHD, DNxHR, Kakadu JPEG 2000, NTSC and PAL Avid, RGB Avid 10bit, plus XDCAM MPEG2. MXF OP1A: A Material eXchange Format version conforming to the SMPTE 378M standard; among its codec options for delivery are 1080i Avid 8-bit, DNxHD, DNxHR, Kakadu JPEG 2000, NTSC and PAL Avid, RGB Avid 10-bit, Sony MPEG4 422 and 444, plus Sony XAVC Intra CBG and VBR, and XDCAM MPEG2. QuickTime: Apple’s own file-based media format. Among the things it delivers: Apple ProRes; then DNxHD or DNxHR wrapped inside QuickTime; next GoPro Cineform RGB 16-bit and YUV 10-bit; also Grass Valley HQ and HQX; the codec Kakadu JPEG 2000; then H.264, HEVC, and H.265 (single or multi-pass); additionally Photo JPEG; once more Kakadu JPEG 2000; on top of that Uncompressed 8- and 10-bit formats carrying ARGB/BGRA/RGB/YUV channel orders; finally VP9 at 8-, 10-, and 12-bits. TIFF: “Tagged Image File Format.” It's an image sequence format getting along with loads of desktop video applications across loads of platforms, and it too is chosen for delivering toward DCDM mastering.

- Codec: A dropdown menu that lets you pick from the codecs available to the format you selected above.
- Type: Various codec options may also offer different bit depth and color space combinations, reachable from this menu.
- Maximum Bit Rate: (Does not appear for all codecs) Codecs like Kakadu JPEG 2000 let you state a maximum bit rate, in Mbits per second, at which to encode the delivered video.
- Field rendering: When you're working with interlaced source material, this checkbox tells DaVinci Resolve to render each field on its own before stitching them back into a single frame, so clips process most accurately under filtering operations that would otherwise cross field boundaries and cause trouble. If you aren't rendering interlaced media, leave this checkbox off, since it's more processing intensive.
- Interlaced rendering: By default, frame-based media sources (image sequences, and the like) render progressively. Check this box to instead render them as interlaced media. Once checked, pick the Field Order to encode, either top or bottom field first.
- Export HDR10 Metadata: (Surfaces in Single clip mode once HDR10+ is switched on in Project Settings) During an HDR workflow, writes HDR10 metadata into the rendered file.
- Embed HDR10 Metadata: (Surfaces in Single clip mode once HDR10+ is switched on in Project Settings) During an HDR workflow, writes HDR10 metadata into the rendered file. Tucks HDR10 metadata inside the exported media for selected formats.
- Embed HDR Vivid Metadata: Writes HDR Vivid metadata to the rendered file when you're running an HDR workflow. Embeds HDR Vivid metadata inside the exported media of selected formats.
- Render at Source Resolution: (When rendering Individual Clips) Tick this checkbox and every clip renders matching the resolution of its own source media file, so you preserve mixed frame sizes through to final delivery.
- Resolution: The output resolution used for rendering. It defaults to Timeline Resolution, which lets you build a preset whose resolution settings update dynamically and shift automatically to the currently loaded timeline/project. You can, though, change the resolution here when you want a specific resolution set for the preset. Through this setting you're able to queue several render jobs each at its own resolution, so that, as an example, both HD and SD resolution media come out inside one render session. Certain file formats demand specific resolutions, in which case the Output Size settings snap automatically to the required resolution.
- Frame rate: (When rendering Single Clip) This defaults to the Timeline Frame Rate, which lets you build a preset whose frame rate settings update dynamically and shift automatically to the currently loaded timeline/project. That said, you might want to set this to a variation of the current conformed rate, choosing, say, between 23.98 or 24 fps. Doing that adjusts the metadata written inside the file, which helps drive playback across the range of systems found worldwide.

3:2 Pulldown Insertion Options: As of DaVinci Resolve Studio 12.5, outputting either 29.97 or 30 fps media with 3:2 pulldown insertion becomes possible whenever the playback frame rate of your project sits at either 23.98 or 24 fps. For 29.97 output, the project has to be 23.98 fps; just pick (23.976 3:2) from the Frame rate dropdown. Projects running 24 fps frame rates can only go out at 30 fps.

- Chapters from Markers: (QuickTime or MP4 only) Tucks chapter points into the rendered file that line up with each marker’s spot on the Timeline for the chosen marker color.
- Export Alpha: (When rendering Individual Clips) Switching this checkbox on sends the alpha channels held in each clip’s source media file out to each delivered clip, along with any alpha information you create in DaVinci Resolve and feed into that clip through the Alpha output of the Color page Node Editor, which goes out to each delivered clip as well.
- Alpha Mode: (When rendering Individual Clips) Lets you decide how alpha channels export once Export Alpha is on. The choices are Straight or Premultiplied.
- Render Stereoscopic 3D: (Shows up solely when a timeline holds stereo clips) A trio of options dictates the way stereoscopic timelines render, whether putting out just one eye’s worth of media at a time, or putting out a single set of stereo media in one of four ways, based on the option you pick from the “Both eyes as” dropdown menu.

Left eye: Renders only the left-eye media out of a stereo timeline.

Right eye: Renders only the right-eye media out of a stereo timeline. Both eyes as: Offers four approaches to rendering a stereo timeline's left and right eyes down into one set of media files. “Separate files” pushes out the left-eye media and the right-eye media as standalone files, all together. The Side-by-side, Line-by-Line, plus Top-Bottom choices put out frame-compatible media able to feed stereo-capable displays. Anaglyph puts out a traditional anaglyph red/cyan stereo image for viewing on any display through red/cyan glasses. MV-HEVC puts out spatial video clips compatible with most VR headsets.

- Use Constant Bit Rate: When the Format and Codec you've chosen lets you toggle between variable and constant bit rate output, this checkbox forces video to render at a constant bit rate.

### Optional MP4, H.264, H.265, VP9, or HEVC Controls

Set the format to MP4, or set QuickTime alongside the codec H.264, H.265, or VP9, and the extra options below come into view. On a workstation whose NVIDIA GPUs supply NVENC, alternative accelerated options appear, whereas a workstation supplying QuickSync hardware encoding instead can reach for that path.

- Use hardware acceleration if available: Where your workstation provides it, DaVinci Resolve will use QuickSync hardware encoding for both H.264 and HEVC.
- Quality: When the option currently selected in the Render to dropdown menu offers ways to change the compression quality, this dropdown menu lets you pick the quality you want. If not, it stays disabled.
- Restrict to X Kb/s: You may choose Automatic, or set a maximum data rate to export with.
- Encoding Profile: A dropdown letting you pick among various encoding profiles, each

tuned for a different purpose. The trade is between quality and how heavy the encoding and playback compute is. The options on offer are: Auto: Picks an encoding profile automatically. Base: For H.264, aimed at video conferencing and mobile phone use; very heavily compressed. Main: For H.264, aimed at SD analog transmission. For H.265, aimed at compressing 4:2:0 video up to 4K 60fps at a bit depth of 8-bits per channel. Main10: (H.265 only) Aimed at compressing 4:2:0 video up to 4K 60fps at a bit depth of 10-bits per channel. Main 4:2:2 10: (H.265 only) Aimed at compressing 4:2:2 video up to 4K 60fps at a bit depth of 10-bits per channel. High: For H.264, aimed at Blu-Ray and HD transmission.

- Entropy Mode: (called Entropy Coding Mode for compatible Nvidia GPUs) A dropdown letting you pick which algorithm the encoder uses for compression. The options are:

CALVC (context-adaptive variable-length encoding): A lower-quality algorithm whose lighter compute load makes it easier to process and to play back. CABAC (context-based adaptive binary arithmetic coding): A higher-quality algorithm that wins better visual quality while using lower bandwidth, though it demands more compute during processing and playback.

- Multi-pass encode: (Available for QuickTime H.264 and H.265) You may pick between Single and Multi-pass encoding. Single pass runs faster, while multi-pass yields better results where quality matters. Turn on Multi-pass and the number of passes performed is automatic.
- Key Frames: (Available for QuickTime H.264 and H.265) You may pick Automatic, or set a duration for manual keyframe insertion.
- Frame Reordering: (Available for QuickTime H.264 and H.265) On out of the box, Frame Reordering permits B frames to get encoded so the resulting compressed movie file gains quality. Switch Frame Reordering off to speed up encoding at the cost of visual quality.
- Rate Control: (Available for compatible NVIDIA GPUs) Offers six options for governing Encoding Profile and Entropy Mode.
- Lookahead: (Available for compatible NVIDIA GPUs) Lets you state how many frames the encoder examines ahead of compression.

### Optional DCP and IMF Controls

Choose DCP or IMF as the Format and extra options surface, described below.

- Use interop packaging: (DCP only, located under Type parameter) Lets you build an Interop DCP package, based on an earlier DCP delivery standard that isn't forward compatible with SMPTE DCP packages.
- Package Type: (IMF) Falls back to App2 Extended (App2e) by default, which encodes JPEG 2000 as high as 4K.
- Bit Depth: (IMF) The bit depth of the encoded IMF video.
- Encoding Profile: (IMF) A dropdown letting you pick among Auto, IMF, and Broadcast.
- Encoding Level: (IMF) Offers different choices based on what's picked in Encoding Profile.
- Maximum bit rate: (DCP, IMF) Lets you pick how much to compress the result.
- Lossless Compression: (IMF) Lets you opt to encode with lossless compression.
- Slope-Rate Control: (DCP, IMF) A checkbox lets you specify lossless compression.
- QStep: (DCP, IMF) Lets you pick either automatic or manually set DCP quantization levels

to compress the video signal at when using the Kakadu JPEG 2000 encoder.

### Advanced Controls

An advanced settings disclosure button keeps the following additional controls hidden by default.

- Pixel aspect ratio: Lets you override the Project Settings and switch the PAR of the rendered output to either Square or Cinemascope.
- Data levels: Defaults to “Auto,” which simply renders every clip with the data level suited to the codec currently selected in the “Render to” dropdown menu, which is usually what you want. Pick one of the other options (“Video” or “Full”) and every clip outputs using whichever data range you selected. For a deeper dive, turn to Chapter 9, “Data Levels, Color Management, and ACES.”

Retain sub-black and super-white data: Switching this checkbox on lets you output media files that keep overshoots and undershoots, data sitting above and below the maximum and minimum data levels of the data level you picked, assuming the video format and codec you're exporting to support it. Otherwise, DaVinci Resolve clips these “out-of-bounds” parts of the signal to keep your deliverables from breaking whatever QC standards your grade adheres to.

- Color Space Tag: A dropdown menu through which you pick a color space to embed as metadata in the rendered file. The default lands on Same as Project whenever the project's color science reads DaVinci YRGB Color Managed, or on the ACES Output Device Transform whenever your color science reads ACEScc or ACEScct. Overriding this by hand is possible from the dropdown menu choices.
- Gamma Tag: A dropdown menu through which you pick the gamma to embed as metadata in the rendered file. The default lands on Same as Project whenever the project's color science reads DaVinci YRGB Color Managed, or else you may override this by hand from the dropdown menu choices.
- Data burn-in: A dropdown menu defaulting to “Same as Project,” which keeps the current Data Burn In palette settings active during rendering, inserting a window burn into the media being output. Pick “None” to switch window burns off while rendering. Keep in mind that rendering as Individual Source Clips lets you assign per-clip burn in presets, provided they were built in the Data Burn In palette.
- Bypass re-encode when possible: Switching this checkbox on makes it possible to copy the video essence of video items in the Timeline directly, straight from the source media to the file being output, whenever the chosen Format, Codec, and Type matches the source. This also keeps Alpha channel data intact for compatible formats. Bypass re-encode removes the need to re-encode video media, preserves quality, and speeds the output process up dramatically, though it only works for clips in the Timeline that have had no extra effects applied. Anything like grading a clip, dropping in a Resolve FX plugin, layering on overlapping effects or compositing onto clips in the Timeline, resizing or stabilizing clips, altering the Timeline's output sizing, or adding Fusion effects forces the entire clip back through re-encoding so that those effects get processed. Transitions will need processing, but only for the span of each transition.
