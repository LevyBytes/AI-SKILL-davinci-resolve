# Setting Up Tracks Busses And Patching (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- To assign every track, Sub, and Aux to a bus: Pick a button within the Busses section to highlight that bus, then click Assign All.
- To clear all track assignments from a particular bus: Pick a button within the Busses section to highlight that bus, then click Unassign All. Once your bus assignments are complete, click the Close button to dismiss the dialog.

### Bus Assign window

NOTE: As long as the dialog stays open, every assignment you've made can be undone one at a time, or redone, through Command-Z and Command Shift-Z respectively.

Assigning Using Icon View Pick a button within the Busses section to highlight that bus's Send or Out, then either click a target track button or pull a bounding box across all the buttons of the available tracks you'd like assigned to that bus. After assignment, the Available Tracks buttons show which bus now holds them. Once assigned, an “o” or an “s” trails the Bus number, signalling whether it's that bus's send or out.

Pulling a bounding box in Icon view to assign several tracks onto one bus at once

### Setting Signal Paths

Although building and assigning busses lets you submix tracks or pass signal from one bus into another, you'll frequently have to route signals from individual external sources onto a track or bus. For instance, recording audio onto a track means patching your hardware's audio input over to the track you intend to record on. In Fairlight this kind of connection is termed “patching,” and it's carried out via the Patch Input/Output window, present on the Fairlight, Edit and Deliver pages, so patching changes can happen on any of them.

### Using the Patch Input/Output Window

Selecting Fairlight > Patch Input/Output brings up the Patch Input/Output window, which you can show in either List (default) or Icon view. The window splits down the middle, the left half holding whichever Source controls you select and the right half holding whichever Destinations you select.

### Creating a Patch

Out of the box, the available Audio Inputs sit as the Source within the Patch Input/Output window, while the Track Inputs sit as the destination. That makes routing any audio source (a microphone on a USB audio interface, say) over to a particular audio track of the Timeline simple in readiness for recording. Connecting and disconnecting a source from a destination is uncomplicated. In the screenshot below, the Audio 1 Input of an audio interface is highlighted and getting patched over to a track called “Walla.”

The Patch Input/Output window with Source Audio Inputs alongside Destination Track Inputs To patch a source onto a destination: 1 Pick a source type from the Source dropdown menu at the upper left of the window. 2 Click the entry on the source list (or action button in Icon view) you wish to patch from along the left side of the Patch Input/Output window. 3 Pick a destination from the Destination dropdown menu at the upper right of the window. 4 Click the list entry (or action button) for the destination you wish to patch to along the right side. 5 Click the Patch button at the lower right of the window. Both the source and destination then display whatever connection now joins them. To break a source-and-destination pairing: 1 Click a list entry or action button for the source or destination you'd like unpatched. 2 Click Unpatch.

### Patching in Icon view

### Choosing Source and Destination Controls

Through the Audio Source and Destination dropdown menus you select various categories of sources and destinations to patch together. These Source options exist:

- Audio Inputs: The physical audio inputs available on your workstation, such as the Fairlight SX-36 audio interface, MADI, third party interfaces (USB or Thunderbolt, for instance), or system audio. Handy while patching to record audio.
- Bus Out: Any Busses.
- Monitor Direct: Monitor system Direct Out, taken post fold up/down matrix and pre the Monitor VolumeLevel/Dim/Mute.
- Monitor Out: Monitor system output. Taken post fold up/down matrix and Monitor VolumeLevel/Dim/Mute.
- System Generator: Supplies assorted utility sources, beeps and timecode generation among them:

OSC: Supplies a test oscillator. Its controls show up in a floating window reached through Fairlight > Test Tone Settings. Noise: Relies on the Noise generator offering a white or pink noise choice, selectable through Fairlight > Test Tone Settings. Beeps: Means the beeps that ADR panel operations produce, whose controls sit on the ADR setup page. Timecode generator: Produces timecode once enabled and the transport runs, its controls living in a floating window reached through Fairlight > Remote Control Settings.

- Track Direct: Track Direct Out, available pre or post the track fader, carrying an offset.
- Track Reproduction: This is the track playback signal, straight off disk, ahead of any processing.
- Dolby Atmos Renderer: The output from the Dolby Atmos Renderer in whatever

Atmos output monitoring format is currently selected. A parallel stereo binaural output exists too for feeding headphones. These Destination options exist:

- Audio Outputs: For instance, the Fairlight SX-36 audio interface, MADI, third party interfaces (USB or Thunderbolt, for example), or system audio. Handy while patching to play audio back to speakers or headphone systems.
- Talk Back: The mechanism that patches the General Purpose Input and General Purpose Output devoted to talkback.
- Track Input: The inputs of the available audio tracks within the current timeline, which feed the Record and Thru path.
- Dolby Atmos Send: When you're authoring original content this needs patching by hand. Import a Dolby Atmos master file, though, and the Send patching across the bed and object tracks comes together on its own. Whenever an external Dolby RMU renderer is on, each source patched onto these sends gets duplicated across the physical outputs that feed the external renderer, following the base audio outputs set in system preferences.

### Legacy Fixed Bus Patching

Should you opt for the legacy Fixed Bussing under the Project Settings, the options show up somewhat differently. These Audio Source options exist:

- Audio Inputs: The physical audio inputs available on your workstation, for instance SX-36, MADI, or system audio. Handy while patching to record audio.
- Monitor Direct: Monitor system Direct Out. Sits after the fold up/down matrix yet ahead of the Monitor VolumeLevel/Dim/Mute.
- Monitor Out: Monitor system output. Sits after both the fold up/down matrix and the Monitor VolumeLevel/Dim/Mute.
- Main Direct: Main Bus Direct Out; available pre or post the Main bus master fader, carrying an offset.
- Main Out: Main Bus Out; always taken post the Main bus master fader.
- Main Send: Main bus master insert send.
- System Generator: Supplies assorted utility sources, with beeps and timecode generation included:

OSC: Supplies a test oscillator. The oscillator's controls appear in a floating window opened through Fairlight > Test Tone Settings. Noise: Draws on the Noise generator, where white or pink noise can be picked through Fairlight > Test Tone Settings. Beeps: Refers to those beeps that operations on the ADR panel generate, the controls for which are on the ADR setup page. Timecode generator: Creates timecode once enabled with the transport running, its controls offered in a floating window opened through Fairlight > Remote Control Settings.

- Track Direct: Track Direct Out; available pre or post the track fader, carrying an offset.
- Track Reproduction: This is the signal coming from track playback, ahead of any processing.
- Track Send: Track Insert send.

These Audio Destination options exist:

- Audio Outputs: The physical audio outputs available on your workstation. For instance, the Fairlight SX-36 audio interface, MADI, third party interfaces (USB or Thunderbolt, for example), or system audio. Handy while patching to play audio back to speakers or headphone systems.
- Main Return: Main Bus master insert return.
- Talk Back: The setup for patching the General Purpose Input and General Purpose Output for talkback.
- Track Input: The inputs of the available audio tracks within the current timeline, which feed the Record and Thru path.
- Track Return: Track insert return.
- Dolby Atmos Send: For original content you author, patch this one manually. If a Dolby Atmos master file is what you import instead, the Send patching covering the bed and object tracks is established for you. Once an external Dolby RMU renderer is active, whatever sources are patched onto these sends appear mirrored on the physical outputs running to the external renderer, in line with the base audio outputs defined in system preferences.

### Using a Channel Strip’s Input Menu

Atop each track's channel strip in the mixer, the Input dropdown menu offers a few shortcuts for patching assorted inputs and busses onto the tracks of your mix. Picking any option in this menu makes the Patch Input/Output window open with various Source and Destination selections already configured.

### Input

The Patch Input/Output window opens configured to let you patch assorted inputs (the system audio input, for example) onto the tracks of the timeline. That speeds up readying audio inputs ahead of recording.

### Bus

A shortcut that opens the Patch Input/Output window (covered earlier in this chapter) and lets you patch Bus Out or Bus Sends onto Timeline track channels.

### Path Settings

This brings up the Path Settings window for the track, holding controls that adjust the input level of audio signals arriving from an input/output device.

The Path Settings window presenting audio inputs together with track inputs Here are those parameters: Mic/Inst Controls surface on this panel solely once channels 1 or 2 of a Fairlight SX36 audio interface are hooked up to your system. When they're hooked up, every option (level included) for the SX36 mic/instrument inputs can be run remotely after they've been assigned to the channel. Lacking any connection to an SX36, this region stays empty.

### Record Level

- Record: A convenience duplicate of the channel strip's Record Enable button, tied to it directly. Pressing either one enables the other.
- Thru: Lets the input signal flow into the mixer without arming a record path. It's perfect when you'd like a source signal always on hand purely to monitor it.

TIP: That mixer channel can likewise be flipped into Thru mode by Command-clicking the Track Arm button, whether in the Mixer or the Track Header. The button turns green and shows a ’T’ inside it.

- Record Level: Lets you put a digital gain adjustment on the record path to disk, downstream of your audio interface's analog-to-digital converter. As a rule this control belongs at 0.0 (no change, unity gain), since it governs the level you're recording to disk. Best practice is steering the input level into DaVinci Resolve from your audio interface's level controls to keep audio fidelity high. Even so, a moment may come when you want a touch more level, or lack access to an audio interface's controls, and for those you can tweak the input.

### Trim

- Polarity: This button reverses the polarity of whatever signal arrives at the channel strip (a move sometimes dubbed “flipping the phase”). Picture an incoming signal such as an explosion, where the transient attack produces a strongly positive-going waveform (one that mostly rides above the zero line).

Flip the polarity and the signal turns mostly negative-going, the waveform gathering below the zero line. Polarity inversion is sometimes used to better line up signals from several microphones and can serve creatively to shape such a signal's frequency response.

- Trim Level: The Trim knob lets you tune the level of the signal arriving “off of disk” during playback so the feed into effects and the busses is optimized. It's useful for nudging an otherwise perfect element slightly up or down within your mix. Trim adjustments land post the recorded signal and Track FX (which work straight “off of disk”), and pre every other effect, leaving the recording level untouched.

### Direct Output

Every audio channel strip can switch on a direct output usable to feed any other input destination. To patch this source, reach for the Source dropdown of the Patch Input/Output dialog and select Track Direct there.

- On/Off: Turns the direct output on and off.
- Pre: Places the direct output tap-off point pre (before) the channel fader. On by default.
- Level Control: Sets the direct output level anywhere from minus infinity (fully off) up to +10 dB.

Default is 0.0 (unity gain).

For more information see Chapter 171, “Setting Up Tracks, Busses, and Patching.”

### Insert

A convenience duplicate of the channel strip's Effects In button, tied to it directly. Clicking either location enables its counterpart and flips every Fairlight FX, AU, or VST channel effect into or out of the signal path.

### Input Menu with Legacy Fixed Bussing

Under the legacy Fixed Busing, the options there differ a little. Here's how they look once it's enabled. Input The Patch Input/Output window opens configured to let you patch assorted inputs (the system audio input, for example) onto the tracks of the Timeline. That speeds up readying audio inputs ahead of recording. Aux Bus A shortcut opening the Patch Input/Output window (covered earlier in this chapter), which opens configured to let you patch assorted Aux busses onto specific submix and Timeline track channels. Sub Bus A shortcut opening the Patch Input/Output window (covered earlier in this chapter), which opens configured to let you patch assorted Sub (submix) bus channels onto specific Timeline track channels. Main Bus A shortcut opening the Patch Input/Output window (covered earlier in this chapter), configured so you can route assorted Main bus channels toward particular Timeline track channels. Path Settings Picking this brings up the Path Settings window, whose controls tune the input level of audio signals arriving from an input/output device.

### The Fairlight Presets Library

The Fairlight page provides a strong, adaptable preset system letting you store and recall presets for everything from the entire configuration of the audio page down to individual presets for plugins. Reaching the presets library is done through Fairlight > Presets Library.

The Fairlight Presets Library, its saved presets along the left panel and the target tracks down the right

Up at the upper left, a Filter By dropdown menu lets you pick which preset type you want to work with.

### Filter By menu of preset types

The choices are:

- Equalizer Presets: Presets for the built-in channel EQ.
- Dynamics Presets: Presets for the built-in Dynamics Processor.
- Plugins Presets: Fairlight FX, AU, or VST.
- Global Track Presets: All settings for a Mixer channel strip.
- Global Bus Presets: All settings for a Mixer bus.
- Fairlight Configuration Presets: Numerous parameters of the Fairlight page get stored as a preset, including:
- Track height.
- Which tracks stay visible versus hidden within the Index's Tracks pane.
- Split point in the Mixer.
- Full Track vs. Small Track views in the Mixer.
- Track Groups enable status.

NOTE: A handful of items aren't presently kept in Fairlight Configurations, such as which panels show (Media Pool or Index, for example), Meter Panel show/hide, Fairlight video window docking, plus the size when the video window is set to float.

### Using the Presets Library

From the Filter By dropdown menu over on the left, choose whichever preset type you intend to work with. Over on the right, the tracks list (present for most preset types) serves a dual role: it's both a roster of sources holding information you'd like stored and a roster of destinations you'd like assigned once presets exist. To store and recall and assign presets:

- The first time you store a preset, choose, over in the window's right-hand tracks list, the source track you'll be pulling the preset type from (a Fairlight Configuration preset being the exception, since it's global and presents no tracks to pick).
- Click the Save New button to store your preset.
- To load your preset onto a different track, clear any tracks currently selected in the track list on the right, then pick the track(s) you'd like to assign to. Click Apply and the preset loads.
- To store a fresh version of an existing preset or refresh your current one, begin by choosing a track in the track list that already has your preset assigned. Next click the Save New button; a dialog then appears offering the choice to refresh the preset's existing version or to store a brand-new preset built from the current settings.
- To Delete a preset, pick it in the list, then click the Delete button.

### Update or Create New preset dialog
