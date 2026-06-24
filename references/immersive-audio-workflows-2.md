# Immersive Audio Workflows (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Within the Export Immersive Master dialog, point the File Name at Timeline Name and the Format at Dolby Atmos ADM BWF. For the exported file's Sample Rate you may pick either 48000 (delivery) or 96000 (delivery). The Source defaults on its own to the Atmos Send Patching. That patching routes the signal by way of the sends into the internal Dolby Atmos Renderer, both to process it and to build a fresh Dolby Atmos master file.
- Click Export. Within the Export Immersive Master finder window, browse to the folder where the file should be saved. Click Save.

The Export Immersive Master dialog laying out the source and format behind the fresh ADM export.

The Export allows for several types of file types:

- Dolby Atmos ADM BWF
- Dolby Atmos IMF IAB
- Fraunhofer MPEG-H Production
- Fraunhofer MPEG-H Production XML

### Parallel Loudness Measurement

While the render runs, a parallel 5.1 down-mix can serve as the source for a 5.1 loudness measurement. Some delivery specifications (those for Netflix, for instance) demand that the loudness measurement of Atmos Masters happen at 5.1. You're able to switch on this parallel 5.1 (or stereo) render for the loudness measurement while still monitoring in the room's native format.

### Selecting a Downmix option

### Low-latency Rendering

Earlier builds of the Dolby Atmos Renderer ran at a fixed latency of 10.67 ms. With that limit gone, you can now pick lower latency engine processing block sizes, which brings monitoring latency through the Dolby Atmos renderer down. The renderer does, however, force the larger block size during certain operations — the Binaural renderer, say, or whenever a parallel loudness down-mix is switched on.

### Surround Buses in Fairlight (Studio Version Only)

Fairlight's FlexBus structure opens up user-definable buses. Atmos mixes need several bus formats, which DaVinci Resolve 17 and later make available.

- 9.1.6
- 22.2

### Object-Based Format Support (Studio Version Only)

- Dolby Atmos with support for 7.1.2 and 7.1.4
- MPEG-H with support for 5.1.4, 7.1.4, and 7.2.3
- SMPTE ST.2098 with support for 9.1 OH, 9.1 HT, 11.1 HT, 13.1 HT, and 15.1 HT

### Auro-3D Support (Studio Version Only)

- Auro-3D with support for 9.1, 10.1, 11.1 (7+4), 13.1

### Dolby Atmos Configuration Controls

By way of the Video and Audio I/O panel of the Resolve System Preferences, you can switch on and configure the use of a Dolby RMU for Dolby Atmos mixing. Type in the RMU's IP address and pick the base audio output.

Configuring Dolby Atmos in the Resolve System Preferences

### Atmos Re-Renders

To keep things on par with the external renderer, you can build presets that spell out a PCM output format together with a set of sources drawn from the bed, object, and group definitions (5.1, for example). Bounce Mix to Track makes room for these re-render presets inside Dolby Atmos timelines, so a single pass can turn out several deliverables. The render presets get stored and recalled along with the timeline.

### Bounce Mix to Track Dolby Atmos re-render options

Beyond the render format, the source can be picked from some combination of beds, objects, or defined VCA groups.

### Dolby Atmos Render Preset options

### MPEG-H Authoring

DaVinci Resolve supports MPEG-H authoring. That covers Native MPEG-H track and bus formats plus monitoring, including the option to set basic track-level meta-data for export into an MPEG- H scene, along with export of a MPEG-H Master file. Switch it on and the formats turn up as choices for a bus, track, or monitoring format inside the Bus Format window.

The MPEG-H format options in the Bus Format window

The same formats also turn up for multi-channel track assignment.

The MPEG-H format options in the Track Format submenu Much as with most immersive content, tracks are mixed natively, building a bed mix out of a set of immersive object tracks driven by dynamic panning. Those get folded onto the main bus to make up the immersive mix.

### Track Configuration

On top of that process, switching the format on enables a set of MPEG-H meta-data columns in the DaVinci Resolve Track index — namely Track Type, Kind, Language, SW Group, and Preset.

These columns, and the steps to configure them, get a fuller treatment in Chapter 170, “Using the Fairlight Page.”

With MPEG-H switched on in the Project Settings, the Tracks panel surfaces extra columns of information for defining every track within the Timeline

### Export

With everything configured and your project mixed, you export a master file. Doing so requires that you set a range In and Out point on the Timeline to mark out an export range. You also have to specify which busses are slated for rendering by setting their Kind, and you may pick extra tracks to export as well.

### Selecting tracks and busses to export

NOTE: An MPEG-H master file tops out at fifteen channels total. Should the chosen track and bus stems run past that, the export fails with a warning. The same happens when no range is set. Exporting an MPEG-H mix goes like this: 1 Choose Fairlight > Immersive Audio > Generate MPEG-H Audio File. 2 Settle on a save location plus a name, then click Save. From there, every defined bus is rendered. After that, track loudness gets measured for compliance. Finally, the source audio is exported and the metadata baked into the deliverable MPEG-H wav file.

Several error conditions, cleared away during the export process, will each make the export fail. Every track, for one, has to hold audio. Audio inside switch groups has to sit within a set loudness tolerance of one another. Whenever any of these crop up, a dialog shows.

### Warning dialog during MPEG-H export

### Quality Control

A quality control check of the finished audio export is possible through a Fraunhofer MHAPI tool that can open the exported content. It runs compliancy tests and visualizes the metadata held inside. The tool can also render and monitor the content, though that side of it is rudimentary and only handles external audio that's tied to the metadata. Put differently, you have to hook the components back up to the source audio files by hand.

### Quality control using the Fraunhofer MHAPI tool

### B-Chain Support for Audio Monitoring (Studio Version Only)

Picking Fairlight > Immersive Audio > B-Chain Control brings up the B-Chain Control window. In the language of classic cinema audio postproduction, the “A-Chain” covers all the busing and signal processing taking place inside the mix (here that's via the Fairlight page), while the “B-Chain” covers the signal processing, amplification and speaker system that carries the sound from your workstation's output and delivers it “into your ears.” That ordinarily takes in whatever signal decoding or preprocessing hardware, amplification systems, and speaker setups most professional and commercial listening environments call for, particularly with immersive audio or surround sound formats. Such options run complex, with no shortage of variables around speaker configuration, selection, and placement, output channel timing, attenuation, and phase, plus a host of further considerations. In DaVinci Resolve, these B-Chain controls govern how the audio channels coming out of the Main you're mixing get mapped to the actual audio signals leaving your workstation for the amplification and speaker system of the current viewing environment. The deep level of control the B-Chain presets afford comes into its own in settings like surround-sound configured grading and mixing theaters, where you define how the immersive audio standard you're mixing maps onto your particular application's speaker setup, and where you fine-tune the channels going to each speaker for your environment specifically. In plainer monitoring setups, the B-Chain controls help you configure whatever standard you're mixing in to play through a non-standard speaker setup in your room. In the end, the B-Chain controls are built for users who need custom, fine-tuned settings tailored to their specific monitoring situation. That's why nearly every real-world use of these B-Chain controls ends up demanding custom configuration suited to your unique environment.

### Overview of Setting Up a B-Chain Configuration

Putting a B-Chain configuration together takes a bit of effort, but once it's done you've got a preset that reopens easily anytime. The example below configures a B-Chain preset to turn a 5.1 surround output into a 3-channel left-center-right room speaker setup. Here's the B-Chain setup procedure: 1 To bring up the B-Chain Control dialog, Choose Fairlight > Immersive Audio > B-Chain Control. That surfaces the monitoring controls but leaves the configuration controls hidden. 2 Click this window's Option menu and pick Setup B-Chain Presets. Up comes the B-Chain Setup window. 3 Click the New button to start a fresh B-Chain preset, then type a name into the dialog and click OK. For this example we'll go with the name “5.1 to LCR.” The Name you type here labels the saved setting data. Once you pick already-created presets from the Setting pop-up, extra buttons let you Delete, Rename, or Duplicate them. 4 Type a label into the Name field (this is what shows in the preset menu). Whatever name you type here is the one that turns up in whichever pop-up menus you select these options from. 5 From the pop-up menus, pick Input Mode > Fixed Format together with Input > 5.1. These set what signal leaves your mix. (Input Mode > Monitor Feed has the B-Chain follow the chosen monitor source, whereas Input Mode > Custom Format lets you settle on any number of channels.)

6 Pick an Output Mode > Fixed Format, and Output > LCR from the next batch of pop-up menus. These set the speaker rig you'll play the mix through. Here we've gone with LCR, short for Left, Center, Right. Notice that once the Input and Output channels are defined, the “Inputs/Outputs” table of cells fills in:

- Down the left of this table, every channel of the Input you picked takes a vertical column. Here, the Input columns read L, R, C, LFE, Ls, Rs, lining up with the 5.1 channels you chose to output. Rigs with far more channels are possible, and then the table's left half turns scrollable.
- Down the right of this table, every channel of the Output you picked takes a horizontal row crossing the Input columns. Here, the rows read Left, Center, Right.

So every Input column meets each Output row, letting you set how much of each Input feeds each Output by typing values into each crossing cell.

The Inputs/Outputs table of the B-Chain preset window 7 To route Input channels to Output channels, double-click the field where the wanted Input crosses the wanted Output, and type a value fixing how much level from that Input goes to that Output. Typing 0 sends Input to Output at “unity” gain (0dB). The numbers you type here count in tenths of a dB. Typing -3 sends half the level along from Input to Output. A value of -100 mutes that Input to that Output outright. Cells left blank make no assignment. In this case, the entries we type are: a) 0 into cell L-1 so the whole Left source lands on the Left output b) 0 into R-3 to route the full Right source onto the Right output c) 0 into C-2 so the entire Center source reaches the Center output d) -6 into Ls-1 to feed a slice of Left surround into the Left output e) -6 into Rs-3 to feed a slice of Right surround into the Right output f) -8 into LFE-1 to pass a smaller slice of LFE onto the Left output (LFE is not directional) g) 8 into LFE-3 so a smaller slice of LFE reaches the Right output as well, LFE having no direction By now we've laid out in full how much of which Input channels reach which Output channels. Along the way, you can see that this table interface lets you route full levels of Input channels to Output channels, route partial levels of Input channels to Output channels, and route fractions of Input channels across multiple Output channels.

The Inputs/Outputs table of the B-Chain preset window, fully filled in so inputs map onto outputs 8 By now you ought to spot extra columns to the right of the Output channels, offering assorted options for fine-tuning each channel's output so your room's acoustics and layout come out right:

- Trim each channel (in tenths of a dB)
- Add a Delay (in milliseconds)
- Add specific EQ (None, LFE Only, Surr Mode)
- Mute or Solo groups.

9 The final move is to right-click the right-most Output column of each Output channel row and pick the hardware output of your audio or video+audio interface you want that channel sent to. Check one of the I/O Setup procedures coming up for how to rename these options and make this simpler.

### Assigning I/O channels to output to

Once your B-Chain preset is set up, click OK, and the preset is saved and ready to use. Here's how to select a B-Chain preset and switch B-Chain on: 1 To bring up the B-Chain Control dialog, Choose Fairlight > Immersive Audio > B-Chain Control. 2 Flip on the toggle in the window's upper left-hand corner to enable B-Chain, and pick a preset off the pop-up menu. 3 Pick the Input that B-Chain preset should be assigned to. 4 A set of Solo and Mute buttons lets you single out sets of channels to hear on their own, or to mute from the whole, so you can better assess chosen parts of your mix. 5 A Fixed Level button pins the output level in the DaVinci Resolve UI to one value. With it on, dragging the level slider to change the monitoring volume is blocked. 6 Once you're done using B-Chain to monitor, flip the toggle in the upper left‑hand corner back off.

NOTE: As long as the B-Chain stays enabled, the Speaker Setup controls sitting in the Resolve System Preferences' Video and Audio I/O panel are switched off.

The B-Chain Control Window, the place to pick and switch on a B-Chain preset that shapes the output To label your system's various channel outputs for easy assignment: 1 To bring up the B-Chain Control dialog, Choose Fairlight > Immersive Audio > B-Chain Control. 2 Click this window's Option menu and pick Setup I/O Names. The I/O setup window opens, listing every single audio input and output on every audio interface your system is connected to and recognizes. The I/O Setup window lets you rename the Inputs and Outputs tied to your workstation setup, making Fairlight easier to configure when you're juggling hundreds of channels. The names you settle on here show up throughout DaVinci Resolve wherever channels can be selected and/or exposed. 3 Renaming a channel means double-clicking its field in the Name column, typing a fresh name, then pressing Return. 4 To protect a channel, tick the checkbox in the Protect column. Channels under protection can't be patched to. The point is potentially high-volume speaker outputs, where wiring the wrong input by accident would be dangerous. Protected channels stay visible everywhere patches can be made, but appear grayed out. The only spots they can be used are the Speaker Setup controls within the Resolve System Preferences' Video and Audio I/O panel, plus the B-Chain Setup window. 5 Once you're finished, close the window. A channel's names and protected status form a system-wide setup.

The I/O Setup window, your place to rename the system's audio outputs and shield channels feeding amplified speakers

### Space View

Space View is a 3D interactive workspace where you watch your unmuted sound sources' real-time positions and automated movements. Sources can be freely repositioned in the 3D sound field in step with your mouse movements (Left/Right and Forward/Backward). Hold Command while you move the mouse forward and back, and the sound source travels up and down within the sound field. Every change you make can be automated (Touch and Pan) and saved. To open Space View, head to Fairlight > Immersive and pick Space View. NOTE: A source shows up only when it's unmuted and its fader level sits above -70dB.

### Space View of an Immersive mix

### Space View Controls

Space View provides the control options below, which, paired with the track mute and solo buttons, give you very flexible ways to zero in on individual sources or groups of sources. Down in the workspace's lower right corner sit four buttons that let you view your sound sources from various angles or perspectives. The workspace rotates freely while you hold Command-Option-Shift and drag it. To snap back to a default view, click one of the perspective buttons.

Across the window's lower edge sit the following checkboxes:

- Ambisonics Metering: This checkbox switches on Ambisonics sonar-type metering while

working on Ambisonic mixes.

- Compact Meters: This option swaps the larger halo-style meters for smaller bar-graphs.
- Show Active Level Only: Tick this option and the names of silent sound sources are hidden.
- Show Beds: This option brings up the labels and meters for sound sources belonging to

sound beds rather than just the signals feeding your master Dolby Atmos bus. The choices in the dropdown menu to the right of the checkboxes set which objects show in the virtual space: Show Only Selected: Displays sources based on tracks you've picked in the Mixer or timeline. Show Visible: Displays only the active audio sources for tracks left unhidden. Show All: Every sound source shows and is labeled.
</content>
