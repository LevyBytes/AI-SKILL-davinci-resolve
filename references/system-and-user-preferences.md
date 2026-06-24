# System And User Preferences (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### System and User Preferences

This chapter walks through the options used to tailor the DaVinci Resolve environment to your liking. The System Preferences manage setup choices that govern your hardware and software environment, whereas the User Preferences handle the assorted user-facing controls inside the application.

### DaVinci Resolve Preferences

Inside the DaVinci Resolve Preferences window you'll find workstation-specific options for tailoring how DaVinci Resolve behaves; these are split across System and User panes, which you switch between using the buttons along the top of the window. To bring up the Project Settings window, take one of these actions:

- Choose DaVinci Resolve > Preferences.
- Press Command-Comma.

TIP: When you first launch DaVinci Resolve and the Project Manager is showing, you can still reach the preferences by pressing Command-Comma.

### System Settings of the Preferences window

### Adjusting Preferences

Both the System and User panes break down into a set of panels you pick from a sidebar along the left edge. Every panel holds a grouping of related options that govern one category of DaVinci Resolve behavior. To modify any given preference: 1 Click the name of a settings group in the left sidebar to reveal its panel. 2 Adjust whatever options you need. 3 Click Save to commit the edits you've made and dismiss the Preferences window. After updating particular System Preferences you'll be asked to relaunch DaVinci Resolve, though editing the User Preferences typically won't require that.

### Resetting Preferences

Returning every preference to its factory default is straightforward. Open the Option menu in the top-right corner of the Preferences window and pick Reset System Preferences.

### System

The System pane within the Preferences window holds a sequence of panels for setting up the computer and the rest of the hardware making up your DaVinci Resolve workstation.

### Memory and GPU

The upper portion of this panel exposes Memory Configuration choices, while the lower portion offers controls governing how GPU processing gets managed.

### Memory Configuration

The preference options below all deal with how memory is used. System Memory: Your workstation's full available RAM is shown here. Limit Resolve Memory Usage to: This option caps how much overall system memory Resolve may consume, leaving headroom for other programs. Its maximum and default value is 75 percent of the RAM in your system. Limit Fusion Memory Cache to: Caps the RAM that the Fusion page playback cache is permitted to occupy. Based on how long the clips you handle on the Fusion page are, that playback cache can take up a sizable portion of free memory. Whatever you assign here is drawn from the overall memory budget set by the "Limit Resolve Memory Usage to" option.

### GPU Configuration

This portion lets you decide how GPU processing gets managed.

### Options for configuring the GPUs on your workstation

GPU processing mode: Lets you direct DaVinci Resolve toward the OpenCL, CUDA, or Metal GPU computing APIs when handling effects processing. The right pick hinges on the GPUs present in your machine. The bulk of users can keep this on Auto and trust DaVinci Resolve to select something suitable. Failing that, here are pointed suggestions. On a macOS system, go with Metal. AMD GPU owners on Linux and Windows should pick OpenCL. Nvidia GPU owners on Linux and Windows should pick CUDA, but confirm you have the right drivers for your machine plus the newest CUDA update installed. On top of that, manually selecting an option from this drop-down menu causes the GPU selection mode drop-down to surface as well. DaVinci Neural Engine Processing: Lets you decide which hardware drives the AI tools running on the DaVinci Neural Engine. Auto picks whatever Resolve judges most capable, yet you can override that by hand and name a particular GPU or Neural Engine. GPU selection mode: Lets you pick between Auto, which hands DaVinci Resolve the job of deciding which of your computer's available GPUs to harness for processing, and Manual, which lets you turn individual GPUs on or off for processing from a list shown beneath. This comes in handy when a machine holds several GPUs and you'd rather dedicate only the strongest ones to processing. It's likewise handy when an external eGPU is attached to a laptop or all-in-one whose own GPU is weaker, letting you point processing at the stronger eGPU. GPU selection list: This list shows up only while GPU processing mode is on OpenCL, CUDA, or Metal, and while GPU selection mode is on Manual. Every GPU present in your computer is listed, and checkboxes beside each one let you switch specific GPUs into or out of processing duty. Optimized Viewer Updates: This surfaces only on multi-GPU macOS and Windows machines or on single- and multi-GPU Linux machines; it speeds up viewer update performance.

### Media Storage

Here you set the scratch disk plus the other media storage spots DaVinci Resolve relies on, along with proxy spots and the default cache directory spots applied when fresh projects are made. Media Storage Locations: This list is where you declare the system's scratch disk. Whatever volume sits first in the list holds the Gallery stills and cache files, so be sure to point it at the quickest storage volume available to you. Mapped Mount: This column lets you spell out translatable media path mapping across Mac, Linux, and Windows file system conventions. Direct I/O: With this turned on, DaVinci Resolve writes straight to the drive through the kernel buffers, skipping the usual storage cache held in RAM. That unlocks the drive's full performance. Automatically display attached storage locations: Tick this checkbox and DaVinci Resolve reaches media across every momentarily and permanently mounted volume, spanning bus types such as SATA and eSATA, SAS, USB, FireWire, Thunderbolt, Gigabit Ethernet (GbE or GigE), plus Fibre Channel, together with any other attached hard drives, all without needing to list them here. It's enabled by default. On the Apple App store build of DaVinci Resolve, enabling "Automatically display attached local and network storage locations" pops a dialog asking you to register "Macintosh HD" as a storage spot. Hitting Add Location asks you, via a second dialog, to pick the Macintosh HD volume, and hitting Open then registers that volume into the Media Storage Volumes list. Once you click Save to dismiss the Preference windows, Resolve ought to auto‑mount whatever volumes are attached to your computer inside the Media page's Media Storage browser. Hold off on this until you've first added a quick storage volume to the Media Storage Locations list, since Macintosh HD shouldn't be the opening volume there – that first slot in the list belongs to your fast scratch volume at all times. Proxy Generation Location: These choices let you declare where any proxy media you produce gets rendered.

- Proxy subfolders in media file locations: The proxy media lands inside a subfolder called "Proxy" sitting at the same hierarchy level as the source media file. So if all your source media lives in one folder, you'll end up with a single "Proxy" folder holding every proxy clip. If instead your source media is spread across separate folders (that is, one folder per video clip), you'll wind up with several "Proxy" folders—one tucked inside each clip folder, each holding a lone proxy clip.
- Use project settings: Relies on the "Proxy generation location" target located in the Working Folders section of the Master Settings within the Project Settings.
- Ask when creating: Brings up a filesystem dialog so you can pick a particular folder for the proxy generation.

### Adding and Removing Storage Locations Manually

A few builds of DaVinci Resolve won't display attached volumes automatically. When that's the case, click the Add button to bring up a dialog for picking a volume to add. To drop a volume, highlight it in the list and then click the Remove button. Accessing Volumes From Other Operating Systems by Way of Path Mapping: thanks to shared media path mapping for Mac, Linux and Windows, life gets simpler for multi-system shops that share Resolve projects across platforms following differing file path conventions. To enter a mapped mount string: 1 Open the Resolve Preferences window's Media Storage panel. 2 Add the volume you mean to map into the Scratch Disks list. 3 Edit the Mapped Mount column of the drive you just added by double-clicking it. 4 Type in the alternate file path you want assigned to that volume. As an example, when you're at a Windows workstation reaching for a Linux volume, enter the Linux file path in the Mapped Mount column. NOTE: Should the volume you picked for the cache become unreachable, DaVinci Resolve alerts you with a dialog.

### Decode Options

Every option for leaning on the GPU to speed up decoding and debayering across assorted formats lives in this panel. Use GPU for Blackmagic RAW decode: Lets the GPU speed up how Blackmagic RAW (BRAW) footage gets decoded. Decode H.264/HEVC using hardware acceleration: Permits hardware acceleration during H.264 or HEVC playback, where the computer you're on supports it. Use easyDCP decoder: Given that DaVinci Resolve ships its own built-in DCP encoder and decoder, this checkbox lets you swap over to easyDCP for DCP decoding when a license sits installed on your machine. Automatically refresh growing files in the media pool: When a third-party app is recording live into a growing video file, you're now able to start cutting that file mid-recording. Just bring the growing file into the Media Pool, and with this box ticked DaVinci Resolve keeps refreshing to spot whether the file has changed, updating its Media Pool attributes on its own. Stream files during download from Blackmagic Cloud: Tick this box so you can work with a clip by streaming it before its download from the Blackmagic Cloud finishes. Use GPU for R3D: Lets the GPU speed up debayering of R3D media. The newest RED API allows accelerated 8K debayering through either Metal or Cuda. Three choices exist:

- None
- Debayer
- Decompression and Debayer

### Video & Audio I/O

The options in this panel let you pick the video and audio interfaces on your workstation.

### Video I/O

Here you choose which Blackmagic Design video interfaces to dedicate to monitoring, capture, playback, and Resolve Live, provided any are wired into your workstation. When more than one Blackmagic Design video device is hooked to your computer, you can set them up separately for playback and for capture. With no interfaces connected, no options appear. Capture Device: When you have a compatible video capture card for video input, select from the card choices shown here. This option also names the chosen input device for Resolve Live, letting you monitor and color correct a live video feed. Altering this option calls for a program restart. Monitor Device: When you have a compatible video output card, select from the card choices shown here. Keeping this on "None" switches off external video output. Turning off video output can boost real time performance whenever external monitoring and output aren't the priority. You can also set "None" while running DaVInci Resolve next to another open application that's claiming your workstation's video output interface. After you've closed that other application, you can reselect the video output interface for DaVinci Resolve to use. Altering this option calls for a program restart. Release video device when not in focus: Once enabled, DaVinci Resolve hands back control of the video output device any time you switch away to a different application. Mirror audio I/O engine output: Audio automatically tracks whatever device is set under Audio I/O Engine below. Audio monitoring delay: Lets you compensate for any lag between the video images and the audio monitoring.

### Video input/output options in the System Preferences

### Audio I/O

This area lets you specify the audio hardware plus the various speaker sets you'll use to monitor audio playback. To go beyond the default stereo system output that most workstations fall back on, you'll need whatever utility your operating system provides to select the audio hardware you want and to declare how many audio outputs your chosen monitoring type calls for (stereo, immersive, and the like). On macOS, for instance, you'd turn to the Audio Midi Setup utility to pick output hardware and choose a speaker configuration to make available on your system.

I/O Engine: Lets you select the audio hardware DaVinci Resolve uses to process audio. The options span System Audio, Desktop Video, Fairlight Audio Accelerator, and ASIO (Windows only).

- System Audio: System Audio talks to your computer's native audio hardware and unlocks the parameters below.

Playback processing buffer size: Lets you set the Playback buffer size; off to the right a latency readout shows roughly how much latency your pick adds in milliseconds. Record buffer size: Lets you set the Record buffer size; off to the right a latency readout shows roughly how much latency your pick adds in milliseconds. Input Device: Lets you pick the audio input device from the hardware wired to your system. Output Device: Lets you pick the audio output device from the hardware wired to your system. Automatic speaker configuration: Ticking this box has DaVinci Resolve route audio through your workstation's built-in audio output, even when a compatible video I/O interface is active for capture and playback or for Resolve Live. Clearing this box reveals extra controls for declaring your own speaker arrangement.

Assigning various audio I/O devices, with the buffer tweaks they call for, plus background on audio monitoring and audio input: every bit of the audio processing across DaVinci Resolve—the Fairlight page included, and likewise processing run through Fairlight FX plugins—behaves identically on each platform DaVinci Resolve supports: macOS, Windows, and Linux alike. To be precise, DaVinci Resolve manages audio monitoring and audio input through (i) the audio of a supported Blackmagic Design I/O device along the lines of an UltraStudio or Decklink, (ii) the on‑board audio of your macOS, Windows, or Linux workstation, (iii) whatever third party audio interface qualifies as Core Audio‑compatible or Windows-compatible, as ASIO, or else as Advanced Linux Sound Architecture (ALSA)supported. As another route, you can monitor audio through the optional Fairlight Audio Accelerator, a PCI card built to manage even larger channel counts of audio I/O monitoring and recording, which can also accelerate audio processing tasks for stronger audio performance. NOTE: ASIO is a trademark and software of Steinberg Media Technologies GmbH.

### Monitor Speaker Configuration

Clearing the Automatic Speaker Configuration box exposes a further panel within the Video and Audio I/O Preferences. From there you can map your monitors to the default Main or Near sets, and you can spin up an extra 15 monitor sets tailored to whatever you require.

- Monitor Set: Pick the default Main or Near, or build as many as 15 additional user-definable configurations.
- Rename: This button lets you rename any monitor set to something more

meaningful for your individual needs.

- Format: A drop-down menu lets you pick the format type you want, ranging from Mono up through

Dolby Atmos 9.1.6. Underneath the Format type sit three windows used to build the Monitor Set: Layout: Splits out the channels matching the chosen format. Output: Where you map the Output channels onto your system. Trim: Where you can pull each level down by as much as -24dB of gain or push it up by as much as +10dB of gain to fine-tune the speaker calibration your specific playback room needs.

### Monitor System External Inputs

From this panel you can assemble several monitoring sets, up to 16 user-definable setups. That gives you the flexibility to keep distinct combinations of monitoring speakers on hand and flip among them while checking, reviewing, and building different mixes.

- External Monitor Source: Pick None or as many as 16 definable configurations.
- Rename: Lets you assign a name to an External Monitor Source.
- Format: Picking a Format brings up a drop-down menu letting you choose the

format type you want, from Mono up through Dolby Atmos 9.1.6. After a format is picked, three further windows appear: Layout: Which splits out the channels matching the chosen format. Source: Where you assign either Input Destination or Audio Repro. Input: Where you assign an individual track while on Audio Repro, or assign the specific channel while on Input Destination.

- Rename: This button lets you rename any of the numbered monitor sets to something more meaningful for your individual needs.

Renaming and patching assorted external inputs from within Video and Audio I/O Preferences

### Immersive Audio Controls

This pair of Preference panels lets you set up the flavor of immersive audio you want on hand within your project and also lets you link to a Dolby RMU for handling Dolby Atmos mixing.

- Immersive Audio: From this panel you switch on the assorted immersive audio types DaVinci Resolve provides. Among the supported formats you'll find Ambisonics, Apple Spatial Audio, and Audio Vivid; also Auro 3D, BS.2051, and Dolby Atmos; together with MPEG-H Audio, 22.2 Surround, SMPTE ST 2098, plus 360 Reality Audio.

### Immersive Audio Preferences

- Dolby Atmos: Ticking this box permits use of an external Dolby Atmos renderer. After it's ticked you can key in the RMU's IP address and pick the base audio output.

### Dolby Atmos Preferences

### Video Plugins

You can choose which specific Open FX plugins load at startup, turning others off. Use this to trim and tidy the Open FX list down to just the plugins you reach for often, or to leave out a troublesome plugin that destabilizes the system. On top of that, DaVinci Resolve checks each startup for the last plugin loading result and bypasses any plugins that previously triggered a crash or hang. You can switch individual Open FX plugins on or off by hand in the Video Plugins panel, ticking or clearing the boxes tied to each plugin.

The Video Plugins panel lets you switch specific Open FX plugins on or off at startup.

### Audio Plugins

A trio of parameter sections lets you handle VST effects, enabled plugins, and external audio processes.

- VST Effects: A list up top lets you manually add or drop VST plugin effects directories when needed. Because VST effects don't land in one standard spot, you may now and then have to add a freshly installed directory of VST plugins you've just put on your system.

### Audio Plugins Preferences - VST Effects

- Available Plugins: Once a VST directory or two has been added up top, a follow-on list underneath surfaces every audio plugin discovered inside those directories. Each plugin in the list carries a checkbox indicating whether it's currently active. Any VST plugins that crash DaVinci Resolve while loading at startup get disabled automatically. Use this list to see which plugins were disabled, for troubleshooting, and to switch such "blacklisted" plugins back on by re-ticking their checkboxes.
- Category Column: VST and Audio Units plugins get sorted into categories inside the Fairlight Mixer. To shift a plugin into a different category, click its category name and choose a new one from the Category popup list.

NOTE: This does not apply to Fairlight FX plugins.

### Audio Plugins Preferences - Available Plugins

- Setup External Audio Processes: While at work on the Fairlight page, you have the option to run an audio file through a third-party application when needed—say you need another app's features to build an effect or fix something the Fairlight page alone can't handle. To pull this off, you first add one or more applications to the External Audio Process list inside the Audio Plugins panel of the System Preferences.

NOTE: VST is a trademark of Steinberg Media Technologies GmbH.

Audio Plugins Preferences - Setup External Audio Processes

Here's how to register an External Audio Process: 1 Hit the Add button. 2 In the Name column, double-click the text and retitle it after whichever application or process you mean to link up. 3 Single-click within the Path column, after which the file dialog lets you track down and select the application or script that should act as your external audio process. 4 From the Type column, open its drop-down menu, then settle on the way the chosen audio process ought to behave: Reveal (open the application), Command Line (use from Terminal), or Clipboard (which copies the audio clip file path onto the clipboard, ready to paste into the open command of some application or utility). 5 When that's all set, click Save, then relaunch DaVinci Resolve should you be prompted.

### Control Panels

A pair of sections let you declare which Color Grading Panel and Audio Console is hooked to your workstation.

- Color Grading Panel: A menu lets you pick which color grading panel is hooked to your workstation. Certain panels reveal extra controls.

When you own a DaVinci Resolve Mini or Micro Panel, keep this option on None and Resolve will detect those panels on its own as you plug them in. For a control panel wired over USB, pick your panel from the list. For a DaVinci Resolve Mini Panel running over Ethernet, pick "DaVinci Resolve Mini Panel (Ethernet)" and then pick your panel from the drop-down that surfaces. When you're on a JLCooper Eclipse, pick "JLCooper Eclipse CX" and then key the IP and Port number into the fields that surface.

- Audio Console: A menu lets you pick which Fairlight Audio Console is hooked to your workstation. Certain panels reveal extra controls.
- Use MIDI Audio Console: A checkbox lets you turn on a third-party audio console wired to your workstation. Switching this on reveals three additional menus.

MIDI Protocol: Lets you pick either the HUI or MCU protocol, whichever suits the audio console you intend to use. MIDI Input: Lets you pick the MIDI input wiring your console. MIDI Output: Lets you pick the MIDI output wiring your console.

- Head Tracker: A menu lets you pick which head tracker profile to apply for immersive audio.
- Display Control Panels Status on Main Footer: Ticking this box shows the status of every

connected control panel as an icon in the interface's lower-right footer. Clearing the box hides that icon.

### The Control Panels Status icon

### General

This panel offers assorted options covering scripting, audio processing, monitoring, and submitting problem reports.
