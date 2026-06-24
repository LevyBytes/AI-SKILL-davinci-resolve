# Capturing From The Cintel Film Scanner (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Capturing From the Cintel Film Scanner

Walking through how to bring scanned film in, this chapter covers the DaVinci Resolve settings and workflows that drive the Cintel film scanner.

### Controlling the Cintel Film Scanner

The Blackmagic Cintel film scanner is a small, simple, real-time film scanner that turns 35mm, 16mm, and 8mm (the latter needing gates bought separately) positive and negative film formats into Cintel Raw Image (CRI) digital files. Those files can then be organized, edited, and graded in DaVinci Resolve, delivered to whatever format DaVinci Resolve is able to output, and stored away for later use.

### The Cintel scanner

Any Blackmagic Cintel film scanner hooked up to your computer over Thunderbolt or PCIe can be driven by DaVinci Resolve. With it connected, you can switch on the Film Scanner controls in the Media page, which let you pick the film type for scanning, line the film frames up with the sensor, tune the scanner’s light source for the best exposure and color, and decide whether the scanner’s hardware-based Automatic Perf Detection should handle image stabilization. NOTE: This chapter of the DaVinci Resolve manual covers running a Cintel film scanner connected to DaVinci Resolve so as to ingest scanned film. For other operational questions, consult the documentation shipped with the scanner itself, or head to the Blackmagic Design support page on the web to download it. This part of the manual walks you through using the settings and features in DaVinci Resolve’s film scanner panel to drive your scanner — for instance, calibrating it, dialing in the light source strength and color temperature, configuring image stabilization, and beyond. You can even dictate how gently your Cintel scanner treats film that may have grown fragile with age. TIP: DaVinci Resolve stores every scanner setting inside your current project.

### The Cintel Scanner Interface

Click the ‘capture’ button on the UI toolbar across the top of the DaVinci Resolve screen to point the media page at your Cintel scanner. Bring up DaVinci Resolve’s film scanner panel to configure, calibrate, and set options for logging or scanning a chosen stretch of the roll of film currently spooled. Should you want extra space to view the Cintel scanner controls, click the full height button sitting at the far right of the UI toolbar, then switch off the ‘metadata’ panel.

### Cintel scanner controls in the Media page

Transport Controls: Though the transport controls beneath the viewer look much like those you use in playback mode, here they instead drive the Cintel scanner. Extra controls show up for stepping forward or backward one frame at a time. In and Out Controls: Once Cintel Scanner mode is active, the transport controls have In and Out buttons sitting to their right that mark out a stretch of the film roll to capture from. The following clusters of settings turn up to the right of the Media page viewer once Cintel Scanner mode is engaged, so you can pull clips from film straight into the Media Pool.

### Film Controls

The film controls give you options to calibrate the scanner’s optics and pick the film type; you can also dial in frame alignment, set scan speed plus spool wind direction, settle on a reel type, and toggle the focus assist feature. You can lean on the calibration button to help clear dust or minor blemishes from your Cintel scanner’s optics.

### Calibration

This option lets you calibrate the scanner’s optics so as to wipe out optical blemishes or dust that won’t come off. Be aware that this feature does nothing about dust on the film itself. Although it’s wise to “spray dust” the optics before scanning fresh material, over time certain blemishes on the optics can prove impossible to remove, and that’s where hitting the calibrate button clears them from the scanned image. Run the calibration with the skid plate installed and lined up correctly, since that helps with image stabilization and yields the best image quality. To accommodate small gauge film types, the calibration button additionally examines the gate that’s fitted and shifts the captured image onto a datum reference. To allow this, run the calibration process on every gate swap with no film in the gate so performance stays optimal. Should you be working with the 8mm HDR gate or 16mm HDR Gate and have moved the aperture shutters to switch to a different film gauge, you’ll have to run the calibration process again to head off a ‘ghost image’ left from the previous calibration.

Incorrect calibration shows Super 8mm film with a Standard 8mm calibration

Incorrect calibration shows Standard 8mm film with a Super 8mm calibration

### Correct calibration of Standard 8mm film

### Incorrect

### Incorrect

### Super 16mm poss correct

### Standard 16mm neg correct

### Film Type

Lets you pick which type of film you’re scanning. Whether the film is color or black and white, your choices are positive, negative, interpositive, and internegative. HDR scanning brings a step up for every one of these film types. Choose the film type you’re scanning from 35mm 2, 3, and 4 perf, 16mm, Super 8mm, and 8mm. On its own, the scanner figures out the gauge — 35mm, 16mm, or 8mm. Where 8mm scanning is concerned, Super 8mm is the default. When you scan regular 8mm, you’ll need to set your scanner to that particular film type by hand. When you scan interpositive and internegative film on Cintel Scanner and Cintel Scanner G2, the film’s heavier density calls for slightly longer pulse durations out of the light source. Usually this leaves the scan untouched; however, a small drop in resolution can show up when scanning above 12 frames per second. Should you spot a resolution difference, just drop your scanning speed to 12 frames per second or below.

### Film Type controls in the Media page

- Enable 2 Pass HDR Scan: Turns on high dynamic range multi pass capture. Running an ‘auto black’ or ‘auto white’ on a frame holding a wide dynamic range matters here, since it works out the high and normal exposure levels from the frame you chose.
- Perf nudge: Serves for making fine tweaks to where the perf sits relative to the scanner gate aperture. To nudge upward, press Command-J; to nudge downward, press Command-L.
- Frame: These buttons activate on a push and hold. While held, the film advances slowly to shift the frame up or down, and on release the film halts where it is. This comes in handy for lining the film frame up with the scanner’s sensor. Using the ‘perf nudge’ and ‘frame’ buttons, line the visible film frame up such that the previous frame’s bottom and the following frame’s top barely show at the viewer’s top and bottom, while the current frame sits centered vertically. Make a point of confirming that the image in the viewer isn’t zoomed in while you do this. On your keyboard, Command‑Left Arrow shifts the frame up, whereas Command-Right Arrow shifts it down.
- Scan Speed: Given enough disk performance, you ought to be able to scan at 30 fps. That said, if you’re scanning to a slow hard drive, you can lower the scanning speed to a frame rate your workstation can keep up with and not drop frames.
- Supply: Sets the wind direction of the left-hand side feed spool. Auto-detection will block incorrect operation, but you should still set the reel winding direction by hand to match how each film roll is wound.
- Take up: Establishes which way the right-hand side take up spool winds. Auto-detection will block incorrect operation, but you should still set the reel winding direction by hand to match how each film roll is wound.
- Use Film Reel: Small film reels carry a different weight and inertia than large film spools, and that can throw off the transport system. Tick this box to switch over to settings that give small film reels better stability.
- Focus Assist: Switches on luminance peaking on your scanner’s HDMI monitor output, along with the viewer in DaVinci Resolve’s film scanner panel, which makes nailing optimum focus adjustments straightforward.

### Adjusting the Light Source

These controls let you tune your Cintel Scanner’s light source so the optimal Dmin density minimum can be calibrated. That value — the Dmin density minimum — represents the lowest scanned value, together with the color temperature of the scanned material. Setting the light source correctly will deliver the best quality scans and keep you from clipping image data during the scanning process. Checking your light source settings whenever you change film is a smart move to safeguard your capture quality. Lean on the built-in software scopes inside DaVinci Resolve to help you set your light source to its best level settings. You can open the scopes in the Media page by choosing Workspace > Video Scopes > On.

The Media page Light Source controls, with the light source in its default uncalibrated state (left) and in its state once calibration succeeds (right)

- Light Source master wheel: The vertical light source master wheel sits beside the color wheel and sets the intensity of the light source that illuminates the film, lifting or dropping the RGB channels all together. For typical negative film, this lets you set the black point of the film image, which is the image’s darkest part. With negative film, that actually maps to the film image’s highlights. Nudge the light intensity so it rests just over the typical Dmin value of 95, as read on the histogram of the video scopes, which makes sure the highlights aren’t clipped by a Cineon‑style LOG conversion. For positive film, simply set the master wheel so no part of the signal gets clipped.
- Auto Black and Auto White button: Reads whatever frame is showing in the Viewer and, for negative and internegative, automatically fixes the black point off the framing bar area. With print and interpositive film, it instead leans on the image area’s brightest highlight when fixing the white point, which makes your choice of frame a key one. There’s another route for positive film types: a punch hole frame can serve as your maximum white, keeping every later frame consistent. With positive film types, what reads as the ‘auto black’ button instead becomes ‘auto white’.

### Light Source Status Indicators

These indicators beneath the ‘auto’ button let you know whether the auto black or auto white light source calibration came off successfully or whether there are things to deal with. They also serve as a handy nudge to recalibrate the LED light source so your scans stay at the highest quality.

Light source calibration has not yet been performed.

Light source calibration has performed successfully.

Light source calibration failed. Double-check that the right film type is chosen, that nothing blocks the light path, and that a fitting reference frame is picked. Should it be needed, try winding the film forward and choosing a different reference frame.

Light source calibration balanced the colours fine, yet not at the levels you wanted. To work around this, either accept the balanced scan and refine the image over on DaVinci Resolve’s color page, or pick a different reference frame — one with a broader dynamic range — for calibration.

- RGB controls: By default, a color balance control lets you shift all three color channels by differing amounts to change the color temperature of the light source that illuminates the film, while the adjusted R, G, and B values show in three fields beneath. If you like, you can flip this control into ‘color bars’ mode using the mode pop-up that sits just right of the ‘light source’ title bar; doing so turns the control into three vertical red, green, and blue color channel sliders.Image Stabilization

NOTE: The light source calibration is held when you swap rolls. That means one light source calibration can cover several rolls across both SDR and HDR modes alike. Whatever the most recent light source calibration was, it stays held until a fresh calibration runs, or until your Cintel scanner is power cycled. These controls let you switch image stabilization on and off as well as steer it to wipe out vertical film hop and horizontal weave

### Image Stabilization controls in the Media page

- Image Stabilization enable/disable control: Sitting just left of the ‘image stabilization’ title bar, a dot lets you switch your scanner’s hardware-based image stabilization on or off entirely. Hardware stabilization is usually what you want when your perforations are high quality, yet you might switch this option off when the perforations are in poor shape and you opt for DaVinci’s software based stabilization instead. With image stabilization switched on, a horizontal X axis detection overlay shows in the viewer, marking the edge of the film perforation that will serve as the reference for stabilization. This overlay hides itself automatically during recording. Image stabilization is switched on by default.
- Enable X and Y checkboxes: Enable X and enable Y let you decide whether hardware image stabilization should fix horizontal gate weave and vertical gate hop respectively. Should the results fall short with both axes switched on, you can switch off whichever axis is causing the stabilization trouble and reach for DaVinci Resolve’s software-based stabilization tools instead.
- Horizontal Position slider: Your Cintel scanner tries on its own to drop the stabilization detection overlay in the best spot, going by the perforation shown on the frame currently loaded, for the best stabilization result.

You’ll spot a thin transparent line within the blue alignment overlay. For the best stabilization, that line should sit right on the edge of the perforation. When the automatic positioning falls short, you can shift the overlay to a better spot by hand — drag it across the viewer with your mouse, or work the horizontal slider. The best placement of the stabilization overlay puts the clear line in the alignment overlay on the perforation’s edge, as the example image shows. With the overlay placed correctly, this switches on hardware stabilization of gate weave along the X axis. Image stabilization takes care of vertical gate hop on its own once you tick the ‘enable y’ checkbox. No further tweaking is needed, and it works hand in hand with horizontal stabilization.

Incorrect 35mm setup. Here the stabilization overlay’s horizontal position is being adjusted; it has not yet settled onto the perforation’s edge.

Correct 35mm setup. In the viewer, the hardware stabilization control rests squarely over a perforation, its transparent stripe meeting that perforation’s edge.

Incorrect 16mm perf setup. The overlay has missed the perforation’s edge. Fit the 16mm HDR skid plate and the stabilizer snaps to the perforation’s far side on its own, steering clear of the film image and tightening horizontal stability. A ‘non-HDR’ 16mm skid plate behaves just like the 35mm one.

Correct 16mm perf setup. Because the perforation’s left edge stays free of image content, that edge is where the overlay defaults to; its transparent stripe lands on the perforation’s edge as it should.

Incorrect 16mm film edge setup. Here the overlay has not landed on the film reference edge.

Correct 16mm film edge setup. Here the overlay sits on the film reference edge, its transparent band meeting the film ref edge cleanly.

Incorrect 8mm setup. Here the overlay has not landed on the film’s edge.

Correct 8mm setup. Within the film base area, the overlay’s transparent stripe is correctly contained.

Incorrect 8mm perf setup. Here the overlay has missed the perforation’s edge.

Correct 8mm perf setup. Because the perforation’s left edge stays free of image content, that edge is the overlay’s default position; its transparent stripe lands on the perforation’s edge as it should.

Incorrect 8mm film edge setup. Here the overlay has not landed on the film reference edge; it sits off the film reference edge.

Correct 8mm film edge setup. Here the overlay sits on the film reference edge, its transparent band meeting the film ref edge cleanly.

To look over how your stabilization settings turned out before you capture, switch the Viewer to full resolution and zoom right in on the perforation area so you can fine-tune. Just click the options settings at the Viewer’s top right corner and pick ‘full resolution preview’ from the menu, then click the zoom scalar at the Viewer’s top left-hand corner and pick ‘100%’. This setting leaves the stabilization feature alone but gives you the best possible preview so you can watch how well it’s doing. Full resolution preview leans hard on the GPU and may bring some frame lag. For the best performance, switch full resolution off once you’ve checked stabilization. Worth noting is that the overlay position is stored within the project settings rather than the clip settings, so it may need to be set individually for several rolls. To reset the detection overlay to its default position for a given film type, use the Stabilization pane Reset button.

### Audio and Synchronization

The Audio and Synchronization palette holds settings for the optional Cintel Audio and KeyKode Reader. For more, consult the Blackmagic Cintel manual under its ‘optional Audio and KeyKode Reader’ section.

### Film Protection

These controls exist so that delicate film can be treated gently by the Cintel Scanner. Quick acceleration and shuttle speeds can be rough on archival footage, so it’s wise to bring both of these sliders down from their defaults any time you’re scanning older film.

When you scan older, delicate archival film, bring down the ‘Acceleration’ and ‘Shuttle Speed’ sliders. NOTE: A ‘Film Tension Adjust’ slider shows up on Cintel scanners fitted with sprockets.

- Max Acceleration: Sets the largest change in speed, to climb or fall by 5-30 fps per second.
- Max Shuttle Speed: Governs the pace of shuttling between film sections — ranging 1–100 frames per second on 35mm film, and ranging 1–200 frames per second on 16mm film.
- Film Tension Adjust: When your Cintel Scanner carries sprocket wheels, this setting lets you tune how much tension is put on 35mm film — say, when loading delicate archival film or making up for film shrinkage. There’s no way at all to harm the film with the ‘film tension adjust’ setting. The adjustment values are tiny, and only gentle changes are ever needed to stop sprocket picking. When your Cintel Scanner carries capstans, sprocket picking can’t happen, so this setting is disabled or absent.

### Editing Capture Info Metadata

When DaVinci Resolve runs alongside Cintel Scanner, a set of capture metadata fields turns up along the lower edge of DaVinci Resolve’s film scanner panel. Within the ‘capture info’ panel sit editable metadata fields that spell out capture properties such as where files get saved, the codec type, frame rate, and the format of file names. Each clip carries this metadata, and you can read it back on the media page. Before you start scanning, you may want to tweak some of the project settings.

The ‘capture info’ panel lets you specify metadata for your scanned clips.

- Capture Location: Before any film scanning session gets going, scroll down within DaVinci Resolve’s film scanner panel to its ‘capture info’ section and confirm the scanned files are landing in the directory and volume you intend. Click the ‘browse’ button and pick a location from the file destination dialog. Handling this first is wise, since this step is easy to overlook.
- Capture: When a Cintel Audio and KeyKode Reader is fitted, this menu hands you options for ‘audio only’ so no images get captured, or ‘image and sound’. As an alternative, you can capture ‘image only’ when audio doesn’t matter.
- Resolution: The resolution of the capture files rides on the source film format, so this field can’t be edited.
- Codec: DaVinci Resolve picks the ‘Cintel Raw’ codec for lossless compression by default, or you can opt for ‘Cintel Raw 3:1’ to get even smaller file sizes.
- Film Frame Rate: State the frame rate the film was first shot at. DaVinci Resolve adjusts the timeline frame rate on its own from this value. This setting has nothing to do with capture or transport speeds. Should you scan audio with the optional Audio and KeyKode Reader accessory, that reader compensates for frame rate on its own to keep an overall sample rate of 48kHz. As for timecode output, it works at 16, 24, 25, and 30 fps; outside those rates, nothing is output.
- File Name Prefix: A prefix to help pin down the scan. You might use your project’s name here — the title of whatever film is going through the scanner, for instance.
- Timestamp Prefix: Tick this checkbox to put a timestamp in front of your scans alongside the ‘file name prefix’ you set. Your clips get saved into separate sub-folders inside the destination folder. This checkbox is ticked by default. Should you want all your clips kept together in one master destination folder with no timecode in the file name, just clear the checkbox.

NOTE: Skip the timestamp prefix and your capture names may not be unique; when such files share one location, existing files could end up overwritten.

- Roll/Card, Reel Number, Clip Number, and Program Name: Each of these is a metadata field for labeling the clip.
- Flags: You can use these color coded flags to tag clips.
- Good Take: Corresponds to ‘circled take’ metadata in the media pool.
- Log Clip: Adds a clip to the media pool. Once you’ve marked ‘in’ and ‘out’ points for a section you want

to scan, check the metadata is right, then click ‘log clip’. For more details, the DaVinci Resolve manual covers this across its ‘Logging and Capturing Individual Clips’ and ‘Logging and Capturing Multiple Clips’ sections.

- Batch Clip, Capture Clip, Capture Now, and Snapshot: These scanning buttons give you different ways to capture clips. To read more about them, this manual devotes its ‘Scanning One or More Sections of Film’ section to the topic.

### Film Scanning Workflows

The sections that follow lay out how to scan film with DaVinci Resolve and drive the Cintel scanner. All through them, the features covered in the previous section appear in the order you’ll carry out each step of the scanning process.

### Before You Begin

Before you switch your scanner on and load film, first dust the gate so your scans come out as clean as they can. Compressed air can handle this, though a badly dirty gate may need to come off for a more thorough cleaning. That done, power up the Cintel Scanner, launch DaVinci Resolve, set up the project that will hold your scanned film, and over on the media page hit the ‘Cintel scan’ button. From there, the ‘Film Scanner’ tab brings up DaVinci Resolve’s film scanner panel. Ahead of loading any film or doing anything else, hit the ‘calibrate’ button down in the panel’s lower-left corner. You ought to dust the scanner gate every time before a fresh reel goes in, yet it’s the calibrate button that wipes out, from the scans you’re about to make, any blemishes in the optics that simply won’t come off.

### Load and Align the Film

Load the film you want to scan. With an image present, the scanner will line up a frame on its own. Bear in mind the image may come out framed wrong if you first load blank film leader. Next, pick the film type. If you need to, use the ‘perf nudge’ and ‘frame’ buttons to hand-tune the framing bar’s alignment to the scanner’s sensor such that the previous frame’s bottom and the following frame’s top barely show at the viewer’s top and bottom, while the current frame sits centered vertically. Make a point of confirming the image in the viewer isn’t zoomed in while you do this.

### Focus the Scanner
