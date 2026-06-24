# Recording

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Recording

On the Fairlight page you can record onto one track or several, covering workflows as diverse as editors laying down scratch voiceover or temporary sound effects, recording engineers capturing narration, ADR, or foley while finishing the audio, music studios tracking orchestras for the score, or garage bands committing their newest masterpiece to disk. DaVinci Resolve may be a full-featured post-production suite for film and video, but the Fairlight page suits whatever audio recording need you bring to it, whether books on tape, live music, feature films, or television.

### Setting Up to Record

How your workstation is configured determines whether you can record onto several tracks at once in the Fairlight page. Exactly how many tracks you can capture to hinges entirely on the hardware you have on hand. The steps in this section cover how recording onto tracks in the Fairlight page works.

### Patching Inputs

Ahead of recording any audio, you have to open the Patch Input/Output window and route an available audio input to a track. DaVinci Resolve lets you nominate a permanent default input that gets patched to the track input on its own once the R (Record Arm) button is pressed, or you can patch an audio input in by hand before record-arming. Lacking a connected audio interface, you can fall back on your workstation’s own inputs to hook whatever device is configured as your system’s default audio input up to the track you intend to record on.

### Automatic Input Patching

This section’s steps describe how to set DaVinci Resolve up so it automatically patches a chosen default audio input in the moment you press the R (Record-Arm) button on the track header or mixer channel belonging to your intended recording track. Here is how you configure Automatic Input Patching: 1 Click the Fairlight menu > Patch Input/Output. 2 Once the Patch Input/Output panel has opened, pick Setup I/O Names from the Options menu in the upper-right corner. Doing so brings up the I/O Setup panel.

The Patch Input/Output Options menu 3 Put a checkmark in the Default column beside the audio input you wish to make the default track input source, then close the I/O Setup panel.

Default audio input selection in the I/O Setup panel That input then gets patched in on its own whenever you record-arm any audio track via the R button on the Track header or Mixer channel. Up in the channel strip’s input section, the audio input name will show.

### Manual Input Patching

The steps below let you pick an input source by hand without disturbing whatever default audio input you may already have configured. To patch in an auto input by hand: 1 Open the Patch Input/Output pane this way: on the Mixer channel you mean to record on, click the Input button up top and choose Input. Or else, you can pick Patch Input/Output off the Fairlight menu.

Mixer channel strip Input button menu 2 Once the Patch Input/Output panel opens, choose both the audio input source and the destination track input. Repeat as often as needed until every input you want to record from is patched to every track you want to record to. As many inputs as your system allows can be patched to as many tracks. 3 Click the Patch button down in the panel’s lower-right corner.

Showing the Patch Input/Output panel once an Audio Input plus a Track Input have been chosen

### Arming Tracks

The moment you are set to record on a track, press the R (Record Arm) button on either the Track header or the matching Mixer channel. An audio track can only be record-armed after it has been patched by one of the methods covered above.

(Left) A Track header showing the Record Arm button engaged; (Right) a channel strip with that same Record Arm button engaged

### Record Name Prefix

Right-clicking the chosen record track header offers an option to assign a recording name prefix to that track’s recordings. It is a handy way to stay on top of the assorted recordings your project calls for. When recording ADR, for instance, you might add a prefix per character’s recordings, as shown below for a character named Pilot.

Right-clicking a track header reveals the Set Track Record Name option

Example of a recording name prefix for a character called Pilot

### Choosing Where to Record Audio Clips To

Recording in the Fairlight page produces fresh clips and writes more media to disk. You can set the on-disk spot where these recordings are saved by opening the Capture and Playback panel of the Project Settings. Within the Capture section, the Browse button sitting beneath the “Save clips to” field lets you pick a new spot (the default is a folder called “Capture” on your scratch disk). To decide where the newly created clips land in the Media Pool, simply open the Media Pool, then click any bin within the Bin list; alternatively, create a fresh bin and select it should you want your recordings kept in their own spot.

### User-Selectable Input Monitoring Options

Five choices governing how you monitor inputs during recording sit in the Fairlight > Input Monitor Style submenu.

- Input: All you hear is the live signal coming in; the contents of tracks never reach you.
- Auto: While one or more tracks sit armed for recording, you hear the live input signal; come

playback you hear the contents of each track.

- Record: The live input signal reaches you only during active recording, that is, once the Record button

has been hit with one or more tracks armed for recording. While tracks merely sit armed, the input signal stays silent to you.

- Mute: You hear nothing.
- Repro: During recording, all you hear is what was just laid down, replayed off the track. Put differently, you are not monitoring the live input but instead reviewing the freshly recorded material as it records.

### Recording Using the Onscreen Controls

You can record wherever you like on the currently armed track or tracks by parking the playhead at the point recording should start. That way, you can drop recordings into particular spots in your program as you capture voiceover, sound effects, foley, or other timed performances meant to slot into a specific stretch of the edit. To begin recording: 1 Park the playhead at the point recording should begin. 2 Click the Record button among the transport controls. Recording starts right away, and the incoming material immediately begins painting a waveform live, giving you instant confirmation of whether the input you are recording is hooked up properly, plus where on the currently armed track material is going down. To stop recording, do one of the following:

- Click the Stop button in the transport controls.
- Press the Spacebar.

### Recording and Editing Multiple Takes Using Layering

Multiple takes can be recorded in two ways. One option is to record them back to back, sequentially, then edit them afterward. Yet you also have the option of recording multiple takes onto the same stretch of the timeline, stacked one over another, all while track layering keeps every take intact. The screenshot below shows multiple takes recorded across the same section of the timeline, partial takes among them to patch particular phrases in the voiceover being captured. When you work this way, the outcome looks like a run of cuts and overwritten clips, the most recently recorded pieces being the ones that play over the segments recorded earlier.

Overlapping recordings with Audio Track Layers turned off That said, if you choose View > Audio Track Layers, you will see that all your recordings have in fact been kept via a vertical stack of overlapping audio clips.

The same overlapping recordings, now with Audio Track Layers turned on so the layering inside one track becomes visible Audio-clip layering in DaVinci Resolve means that, inside a layered stack like this, the uppermost superimposed clips silence the audio of any overlapping clips lower down. Thanks to layering, picking out the best parts of the best takes while holding onto every other take is simple: just add edits and shuffle clips around the stack so the best bits sit on top. To dig deeper into audio layering, see Chapter 175, “Editing Basics in the Fairlight Page.”

### Recording VSTi Instruments

DaVinci Resolve works with VSTi instruments driven by connected MIDI controllers to fire instrument sounds that can be recorded live onto the audio tracks of the Timeline. The Fairlight FX Foley Sampler ships with DaVinci Resolve Studio. You can load it up with foley sounds such as footsteps or human movements, then perform those sounds live and record the outcome onto another track while you watch performers walking or punching in the edit, even without a recording booth full of foley pits and props.

The Foley Sampler ready to be filled with sounds

For more information about the Foley Sampler, see Chapter 181, “Fairlight FX.” Then again, if you are a musician, nothing prevents you from loading VSTi musical instruments of various sorts for playback and treating the Fairlight page as a multi-track recorder. DaVinci Resolve lacks MIDI sequencing, but you can record live playback right onto the Timeline, leaning on layered audio to juggle multiple takes for re-editing later. Bet you never thought you’d be recording music in DaVinci Resolve...

A track of the Timeline holding a VST Instrument, here Serato Sample To switch on a MIDI controller under macOS: 1 Should DaVinci Resolve be running, quit it before you connect your MIDI controller and configure it. 2 On macOS you will turn to the Audio Midi Setup utility to pick output hardware and choose a speaker configuration to make available on your system. From the Finder, use Spotlight and search for Audio MIDI Setup to launch it. 3 Within Audio MIDI Setup, choose Window > Show MIDI Studio. A window appears showing icons for every connected MIDI controller. Your controller ought to display an icon. If it does not, you might need to install drivers for it. 4 Pick the icon for your controller and switch on the “Enter test MIDI setup mode” button (it resembles a tiny keyboard) to check whether your keyboard is talking to the computer. If it is, switch this back off. To learn more about getting MIDI working across various systems, consult the DaVinci Resolve Configuration Guide, which the web offers via Blackmagic Design’s support page, reachable at www.blackmagicdesign.com/support/family/davinci-resolve-and-fusion.

To get the Fairlight page ready for sampler-based VSTi instrument recording: 1 Open DaVinci Resolve. 2 Make certain at least two free audio tracks exist in the Timeline, one to play the instrument on and one to capture into. Here, tracks A4 and A5 will serve that purpose. 3 Open the Effects Library, track down a VSTi sampler installed on your system, then drag it onto the track header of whichever track you plan to play from, say track A4. Heavily-loaded sampler/synth combos like Native Instruments Kontakt and Steinberg Halion are everywhere and come in handy when you want to map a set of sound effects to specific keys or pads in order to build re-usable multi-purpose instruments. That said, slimmer samplers whose strength is slicing audio clips automatically, Serato Sample (Windows and macOS) or Image Line Slicex (Windows only) among them, can knock out the more specialized chore of loading library sound-effects recordings (or ones you record yourself) packed with multiple footsteps, punches, keyboard presses, cloth rustles, or other foley actions, and rapidly carving them into individually playable samples you can trigger off pads or a keyboard. 4 When the VSTi interface window shows up, open the MIDI menu at its upper right-hand corner and pick the correct MIDI channel from your MIDI controller’s submenu. With the right MIDI channel selected, the instrument should start answering the keys or pads on your controller.

Enabling MIDI control 5 Next, set up the VSTi instrument you are using to play whatever sound effects you want for foley. Here, the Serato Sample VSTi plugin handles the automatic chopping-up of a footsteps recording pulled out of one among the numerous Sound Ideas sound effects libraries. Because the VSTi you added sits on that track’s Insert (look at the Mixer and the I button should be lit on whichever channel strip hosts the instrument), the Send is PRE the Instrument. So, to record the instrument, you must route that track’s Track Direct output into another track’s input.

6 Pick Fairlight > Patch Input/Output so the Patch Input/Output window opens; now point the Source dropdown menu at Track Direct, and point the Destination dropdown menu at Track Input. With Audio 4 clicked on the left and Audio 5 on the right, hit the Patch button; that arranges things so the VSTi plugin plays on track A4 while its output records onto track A5. Keep in mind that once Track Direct is patched from the instrument’s track across to your recording track, you must additionally turn “Direct Output” on for that track within its channel strip’s Path Settings over in the Mixer. 7 With the Mixer open (if necessary), click the Input dropdown menu sitting atop whichever channel strip displays the VSTi instrument in use, and pick Path Settings. As soon as the Path Settings window appears, press its ON button beside Direct Output, after which you can close the Path Settings window. From here, you are ready to start recording.

To perform and capture a VSTi instrument: 1. On your destination track (A5 here), click the Record Arming button, drag the playhead to the spot where recording should kick off, and then press the Record button to begin recording. 2. As your program’s video plays, work your MIDI controller to fire sound effects as needed. Once you are done, click the Stop button. If needed, you can record multiple takes through track layering until the timing comes out right. When you are finished, you can pull the instrument off the track it sits on, since the recorded audio is all you need.
