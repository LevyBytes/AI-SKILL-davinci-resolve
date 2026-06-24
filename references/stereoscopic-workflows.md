# Stereoscopic Workflows (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Stereoscopic Workflows

A broad range of stereoscopic workflows is solidly supported in DaVinci Resolve. With the tools built into the Studio version of DaVinci Resolve, you can cut with stereoscopic clips, grade the finished program, tweak each clip’s stereo‑specific properties — convergence and floating windows among them — and master a stereoscopic output, every bit of it inside DaVinci Resolve.

### MEDIA 326

Building a stereo 3D project takes several steps and goes much more smoothly with careful media organization. The pages ahead explain how to prepare for stereoscopic projects, how to bring them in, and how to send stereoscopic media back out. To begin, stereoscopic clip pairs — that is, the separate left- and right-eye media files — get imported into the Media Pool, arranged, and then joined with the “Stereo 3D Sync” command to produce a fresh set of linked stereo clips. From there, those stereo clips may be edited or conformed against imported project data within a single Timeline. In the Color page, DaVinci Resolve lets you handle left- and right-eye grades and sizing through the controls in the Thumbnail timeline’s shortcut menu and in the Stereo 3D palette. Working with stereoscopic CineForm media — which holds muxed left-eye and right-eye image data that DaVinci Resolve can decode — still requires you to follow this same process, except that you’ll rely on duplicate clips to fill the Left and Right folders with matching sets.

### Hardware Requirements for Working in Stereo 3D

On Mac systems running DaVinci Resolve, twin 4:2:2 Y’CbCr stereoscopic video streams come out over SDI from a compatible Blackmagic Design video interface. Depending on what your stereo 3D-capable display accepts, you can pick either Side-by-Side or Line Mesh output to send to it. As an alternative, head into the Project Settings, open its Master Settings panel, find the Video Monitoring group there, and tick “Enable Dual SDI 3D Monitoring”; that makes your compatible Blackmagic Design video interface deliver full resolution 4:2:2 Y’CbCr per eye to compatible displays. As you build a 3D-capable DaVinci Resolve workstation, bear in mind that a 3D project’s paired video streams place heavier loads on disk bandwidth, on media decoding handled by your workstation’s CPU, and on effects processing handled by the GPU cards your workstation has available.

### Setting Up to Display Stereo 3D via SDI

Every DaVinci Resolve system is able to send out a side-by-side frame-compatible signal viewable on a stereo 3D-capable display over a single SDI connection, driven by a DeckLink HD Extreme card or something better. To monitor at higher quality, you can route two SDI signals so the left-eye and right-eye images each go out separately at full resolution, using one of these Blackmagic Design video interfaces:

- DeckLink HD Extreme 3D+
- DeckLink 4K Extreme
- DeckLink 4K Extreme 12G
- DeckLink 8K Pro
- UltraStudio 4K
- UltraStudio 4K Extreme
- UltraStudio 4K Extreme 3

On very old legacy systems, this is handled through NVIDIA dual SDI monitoring outputs.

NOTE: When your stereo display can’t multiplex the two arriving SDI signals on its own, an external device can do the job, combining both SDI signals into one compatible stereo 3G signal. Ask your display manufacturer beforehand whether you’ll need that. The procedures that follow lay out two separate ways to configure stereo 3D monitoring. Monitoring via dual SDI to dual SDI: 1 Within the Project Settings, open the Master Settings panel, and then carry out these steps:

- Confirm that the Use 4:4:4 SDI checkbox is left unchecked.
- Switch on the “Use dual outputs on SDI” checkbox. 2 Over in the Color page, open the Stereo 3D palette, then carry out these steps:
- Set Vision to Stereo.
- Set the Out pop-up menu to None.

NOTE: While “Enable dual SDI 3D monitoring” is active, the grading monitor won’t show split-screen wipes or cursors, and image resizing won’t be visible there either.

### Setting Up to Display Stereo 3D via HDMI

When your stereo-capable display offers only an HDMI input, you’ll have to send stereo 3D signals from the HDMI output of a compatible Blackmagic Design video interface equipped with HDMI 1.4 or newer; consult the documentation that came with your video interface for further details.

### Supported Stereo 3D Media

If you’re bringing stereo 3D media in from other applications, two media types will work with DaVinci Resolve stereoscopic workflows.

### Using Dual Sets of Media in Any Supported Format

As originally captured, the media for stereo 3D workflows lives in two directories — one holding the left-eye media and the other the right-eye media. To get the most automated workflow you can, that media has to be kept tightly organized. Every left-eye and right-eye media file pair across both directories ought to carry matching timecode plus reel numbers that plainly mark which shots are left-eye and which are right-eye. Organized that way, it becomes fairly straightforward for DaVinci Resolve to turn each matching clip pair into the stereo 3D clips you’ll need to work with in DaVinci Resolve. A later section walks through this process in detail.

### Using Stereoscopic OpenEXR Media

For professional cinema and specialty workflows, DaVinci Resolve supports stereo OpenEXR files. A stereo OpenEXR clip keeps each eye’s media as a separate part, so one OpenEXR file can put out either a lone image or stereo 3D images whenever it’s opened in an application that handles it, DaVinci Resolve included. That lets you cut stereo OpenEXR media, grade it, and apply every stereoscopic adjustment the Stereo palette of the Color page offers. Bring stereo OpenEXR clips into the Media Pool and they’ll initially look like ordinary non-stereo clips outputting a single image. Even so, turning them into stereo 3D clips is simple via the steps below. To make stereo OpenEXR clips usable as stereo clips: 1 Bring the OpenEXR media into the Media Pool the same way you’d handle any clip. 2 Highlight one or more OpenEXR clips, right-click them, and from the contextual menu pick “Convert to Stereo.” From then on those clips carry a stereo 3D badge marking them as stereo.

### Using Stereoscopic CineForm Media

CineForm stereo QuickTime files are likewise supported by DaVinci Resolve. A CineForm clip encodes both eyes’ media and muxes (multiplexes) them together such that a CineForm file can hand back either a single frame of image data, when opened in an application without stereoscopic capability, or stereo 3D media, when opened in one that has it — DaVinci Resolve being an example. So you’re able to edit CineForm media in nearly any NLE, export the project through whatever workflow suits you, and finish with a stereoscopic project that DaVinci Resolve can grade. CineForm files can be produced in two ways. The first uses a camera or recorder that takes two synchronized video signals and builds a single set of CineForm media. The second runs dual sets of stereo 3D assets back through the CineForm conversion tools bundled with GoPro CineForm Studio to reprocess them into the CineForm format. As a codec, CineForm encodes full-frame image data with wavelet compression, at any resolution, up to 12-bits, choosing among RGB, Y’CbCr, or RAW color spaces. DaVinci Resolve handles CineForm inside a QuickTime wrapper in any supported color space, giving access to the two image-data streams it carries. When you reach the point of outputting your program, remember that although DaVinci Resolve can read CineForm files, CineForm files won’t render out of DaVinci Resolve unless you’ve bought a GoPro encoding license for OS X or Windows. On top of that, DaVinci Resolve is unable to render Stereoscopic CineForm files. Import stereo CineForm clips into the Media Pool and at first they’ll seem like normal non-stereo clips outputting a single image. They can, however, be converted into stereo 3D clips quite easily with the steps below. To make stereo CineForm clips usable as stereo clips: 1 Drop the CineForm media into the Media Pool exactly as you’d treat any clip. 2 Select the CineForm media slated for conversion, right-click it, and from the contextual menu pick “Convert to Stereo.” Those clips will then show a stereo 3D badge indicating they’re stereo.

### Using Stereoscopic MXF Media

To serve professional cinema and specialty workflows, DaVinci Resolve also supports stereo MXF files. A stereoscopic MXF clip stores each eye’s media as a separate part, letting one MXF file return either a single image or stereo 3D images when opened in an application that handles it, such as DaVinci Resolve. As a result you can cut stereo MXF media, grade it, and apply all the stereoscopic adjustments the Stereo palette of the Color page provides. Once stereo MXF clips land in the Media Pool, they’ll first look like plain non-stereo clips outputting a single image. They’re readily converted into stereo 3D clips, though, with this procedure: To make stereo MXF clips usable as stereo clips: 1 Load the MXF media into the Media Pool the same way you’d handle any clip. 2 Highlight one or more MXF clips, right-click them, and from the contextual menu pick “Clip Attributes.” 3 Inside Clip Attributes, choose the correct stereoscopic encoding mode — either side by side or over/under — from the Stereoscopic Mode dropdown. With multiple clips highlighted, remember to enable the checkbox sitting to the left of the Stereoscopic Mode dropdown so every selected clip takes the mode.

### Creating Stereo 3D Clips From Separate Files

When your stereo media was shot or generated as separate left- and right‑eye files, you’ll have to combine each matching clip pair into the stereo 3D clips DaVinci Resolve needs you to work with. That takes two steps.

### Step 1 – Import and Organize Your Media

Bring every left-eye and right-eye media file into its own bin. 1 Open the Media page and make three Media Pool bins called “Left,” “Right,” and “Stereo Clips.” The precise names don’t matter; how the media is organized does. 2 Place every left-eye file in the “Left” bin while every right-eye file goes in the “Right” bin. For stereoscopic Cineform media you must still build the same arrangement, which means putting a duplicate of each clip into each of the “Left” and “Right” bins.

### Step 2 – Generate 3D Stereo Clips

With your media properly arranged, you’re ready to line up the left- and right-eye clips by timecode. 1 Add a new bin in the Media Pool and call it “Stereo Clips.” This bin will hold the linked stereo clips you’re about to generate.

How to organize media for working in stereo 3D

2 Right-click anywhere inside the Media Pool and pick Stereo 3D Sync. Up comes the Stereo 3D Sync dialog, offering buttons to select the left-eye folder, the right-eye folder, and the output folder, checkboxes to say whether reel names and file names should match, and extra fields for typing the characters that mark left- and right-eye clips.

The Stereo Media Sync window 3 Press the Browse button next to “Choose left eye folder,” then use the nested list of bins that opens to select the bin you called “Left.” Repeat the same steps for the right-eye media. 4 Press the Browse button next to “Output folder,” then use the nested list of bins that opens to select the bin you called “Stereo Clips.” 5 Decide which matching criteria to apply. Ideally you’ll use only whichever one of the three fits. The three choices are: Match Reel Name: switch this checkbox on if the reel names of the left- and right-eye media agree. Match File Name checkbox: switch this checkbox on if the file names of the left- and right-eye media agree. Left Identifiers and Right Identifiers fields: when a particular subset of characters inside the file name distinguishes the left- and right-eye clips (say, “3D_R” and “3D_L”), type each one into its field and those characters will pair the left and right eyes. 6 Press Sync. The starting clips in the Left and Right bins vanish, and a complete set of Stereo 3D clips shows up in the output bin you picked back in step four.

Final stereo clips, ready to be edited and graded

### Step 3 – (Optional) Create Optimized Media

Should your stereo media be unusually large, optimized media is an option. 1 Pick the stereo clips you’ve made. 2 Right-click one of the chosen clips and select Generate Optimized Media from the contextual menu. A window opens telling you how long the optimized media will take to finish.

### Monitoring Stereoscopic 3D in the Edit Page

A Stereoscopic 3D signal can now be viewed straight from the Edit page. In the past, the Edit page limited video output monitoring to the left eye only. The Edit Page Viewer still presents just one eye, yet it now sends Stereoscopic 3D video out through the Decklink or Ultrastudio video outputs. Over in the Color page, the 3D palette holds the stereoscopic controls for picking the stereo viewing options (Side by Side, Anaglyph, Line by Line, and so on) and for tuning convergence along with the other stereoscopic parameters.

### Converting Clips Between Stereo and Mono

A pair of Media Pool commands also gives you the choice of switching clips between mono and stereo 3D.

### Converting Stereo Clips Back to Mono

When the need arises, a single command splits one or more stereo clips back into mono clips. To turn stereo clips into mono clips: 1 In the Media Pool, highlight at least one stereo clip. 2 Right-click any of the highlighted clips and select Split Stereo 3D Clips from the contextual menu. Two fresh bins named Left and Right then appear, each holding the separate left- and right-eye clips you’ve pulled apart.

### Converting Mono Clips or an Entire Timeline to Stereo

Clips that aren’t stereo (those lacking separate left- and right-eye media files) can be turned into stereo clips one at a time or across a whole timeline, for either of two reasons:

- You might convert non-stereo clips to stereo so they fit into a stereo project and output correctly with the rest of a stereo timeline, though without adjustable convergence or depth effects.
- When you’d like to grade both an HDR and a non-HDR version of your program simultaneously, converting non-stereo clips to stereo lets you a) keep two distinct SDR and HDR grades per clip in a timeline by way of the left- and right-eye channels, and b) route the SDR and HDR signals out independently over your compatible Blackmagic Design interface’s left- and right-eye SDI outputs, provided you’ve enabled “Use dual outputs on SDI” — that checkbox lives in the Video Monitoring section, under the Master Settings panel within the Project Settings.

To turn mono clips into stereo clips: 1 In the Media Pool, highlight at least one non-stereo clip. 2 Right-click any of the highlighted clips and select Convert to Stereo from the contextual menu. That clip then shows up in the Media Pool as a Stereo 3D clip, and once it’s edited into a timeline it can reveal its controls in the 3D Stereo palette in the Color page. When a whole timeline is filled with clips you’ve just converted to stereo using the steps above, you must also set the Timeline itself to stereo before you can build stereo grades for each clip. To give a timeline stereo grades for simultaneous HDR/SDR output during grading:

- Right-click a timeline in the Media Pool and pick Timelines > Set Timeline to Stereo.

For more on running stereo timeline workflows for simultaneous HDR and SDR grading, consult Chapter 9, “Data Levels, Color Management, and ACES.”

### Attaching Mattes to Stereo 3D Clips

When you’ve got left- and right-eye mattes to attach to stereo clips, the steps mirror those for importing mattes onto ordinary clips, the difference being that selecting a stereo 3D clip in the Media Pool surfaces a pair of dedicated commands: “Add As Left Eye Matte,” along with “Add As Right Eye Matte.”

### Organizing and Grading Stereo 3D Dailies

One frequent workflow is producing digital dailies inside DaVinci Resolve ahead of editing in an NLE. This gives editors, the director, and producers nicer-looking media to work with that’s also easier on the eyes, provided you run the automatic geometry and colormatching functions that pair the media of each shot together for a first-pass left- and right-eye balance. The Timelines that come out of this can then be exported to whatever media format proves most convenient.

### Step 1 – Create 3D Stereo Clips

When making dailies, the opening step is to bring every left-eye and right-eye media file into its own organized bin and then link them up into stereo 3D clips, exactly as the previous section laid out.

### Step 2 – Edit the New Stereo Clips Into One or More Timelines for Grading

With a set of Stereo 3D clips now in hand, you can cut them into one or more Timelines for grading. The simplest route is to make a new Timeline while leaving the Empty Timeline checkbox deselected. A new Timeline then appears already populated with the stereo 3D clips you built.

### Step 3 – Align Your Media

If the stereoscopic effect is to work without giving viewers headaches, keeping both eyes aligned is essential. Dialing this in by hand can be fiddly, but it’s something the software can analyze on its own. You can run stereo 3D alignment on one clip via the Stereo 3D Palette controls, or you can pick a span of clips and align them all automatically in a single pass. Two alignment methods exist, and the better fit depends on the kind of geometry problems you’re facing.

- Transform Alignment: Examines the image and applies vertical and rotational tweaks to bring the left- and right-eye images into the closest possible match.
- Vertical Skew: Examines the images and applies a vertical-only tweak to bring the left- and right-eye images into line.

### Controls for aligning the left- and right-eye media

### Step 4 – Grading Stereo Media

Grade the Timeline’s clips just as you would any other digital dailies, the one extra task being to use the Stereo 3D palette controls to govern monitoring and handle whatever per-eye adjustments are called for. Whichever eye is currently selected is the one the video scopes show. Exactly as with any other dailies, you’re free to apply LUTs, the Timeline Grade, and clip-by-clip grading to make whatever changes are needed to yield media that’s useful for editing.

### Grading Windows

When you work with windows, look inside the Project Settings, within its General Options panel, where the Color group carries a checkbox labeled “Apply stereoscopic convergence to windows and effects” that holds a window’s position correctly — once it’s been placed properly over each eye — as convergence changes.

A checkbox in the Project Settings has to be enabled before stereo convergence applies to windows With that option active, the Window palette gains an extra Transform parameter, “Convergence,” which lets you build correctly aligned convergence for a window set onto a stereoscopic 3D clip.

The Convergence control in the Transform section of the Window palette

Once you’ve set a window over some feature in the image while watching a single eye, turn on Stereo output in the Stereo 3D palette and work the Pan and Convergence controls so that window sits in correct stereo alignment over that same feature in both eyes. From there, moving the Convergence control in the Stereo 3D palette keeps the window’s position right within each eye’s grade.

### A convergence-adjusted window in stereo

### Matching Media From Left and Right Eyes

To help you cope with the visual gaps between left- and right-eye clips, three automatic color matching commands are on hand that can batch process however many clips you need to fix in one go.

- Stereo Color Match (Primary Controls): Relies on the Lift/Gamma/Gain controls to bring one eye into agreement with the other. It’s a straightforward, easily customized adjustment, though in certain cases it won’t do as well as Custom Curves.
- Stereo Color Match (Custom Curves): Leans on the Custom Curves to build a multipoint adjustment matching one eye to the other. It can do better on tougher shots.
- Stereo Color Match (Dense Color Match): Runs a pixel-by-pixel, frame-by-frame color match of remarkable accuracy. The process is heavy on the processor, so when you plan to batch process numerous clips, or to match lengthy ones, make sure you’ve allowed enough time. Given how exact this match is, the advice is to run Dense Color Match only after you’ve applied one of the stereo alignment commands.

Controls for matching the grade of the left and right eye media

### Step 5 – Output Offline or Online Media for Editing

Once you’ve finished whatever grading the media needs to become suitable for editing, you’ll export each clip as separate left- and right-eye clips by way of the Deliver page controls. 1 Open the Deliver page and configure your render to output the media format you need. Make sure to do the following:

- Set Render Timeline As to Individual source clips.
- Switch on the “Filename uses Source Name” checkbox.
- To render media for both eyes, select “Both eyes as” from the Render Stereoscopic 3D option and select Separate Files in the pop-up menu beside it. If you prefer, you can instead render only the left-eye or right-eye media.

2 Decide how much of the Timeline to render through the Render pop-up menu in the Timeline toolbar; pick Entire Timeline to do the whole thing. 3 Click “Add Job to Render Queue.” 4 Click Start Render. At this point DaVinci Resolve renders either two sets of left- and right-eye clips or a single set of media for the eye you picked. So that the edited project conforms back to the originating DaVinci Resolve project without trouble, it’s vital to render individual source clips and to enable the “Filename user Source Name” checkbox, which reproduces the timecode, reel numbers, and file names of the source media.

### Conforming Projects to Stereo 3D Media

Because DaVinci Resolve handles stereo through one set of purpose-built stereo 3D clips, you import stereo 3D projects with the very same import methods you’d use on any other project. Just one imported timeline is required. It also follows that you can cut stereo projects in NLEs that have no stereo awareness and then finish them in full stereo 3D within DaVinci Resolve. For that, be sure to edit the left-eye media in your NLE and afterward export either an EDL or XML file to conform inside DaVinci Resolve. Conforming an EDL against stereo 3D media goes like this: 1 On the Media page, build the needed set of stereo 3D clips that will line up with the project you’re about to import, following the earlier description. Open the Edit page, then run the Import AAF/EDL/XML command to bring in your edit. 2 Once the Load EDL/XML dialog opens, do the following:

- When importing an EDL, confirm the frame rate is right, then click OK.
- When importing XML, be sure to clear the “Automatically import source clips into

Media Pool” checkbox, because you want the imported project relinked to the stereo 3D clips you made back in step one. The left-eye media timecode and reel data baked into each stereo 3D clip is what conforms the stereo 3D clips against the imported EDL, after which you should be set to work.

### Grading Mastered Stereoscopic Media From Tape
