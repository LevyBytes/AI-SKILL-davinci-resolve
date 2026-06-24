# Using The Fairlight Page (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Language: Sets the language tied to that particular track's content. Switch Group: Lets a track be placed into a switch group that you define. Such a group bundles a track together with others within the finished content, producing one selectable option once it's rendered. As an illustration, a dialogue switch group holding both an English and a Chinese language track might let the viewer pick a language during playback. To set up a switch group, click the relevant cell in that track's Switch Group column and pick “Sw Groups…” to bring up the Switch Groups Manager window, where new switch groups get created.

### The Switch Group Manager

After at least one group exists, it becomes selectable from the dropdown of any cell within the SW Groups column. From here you can rapidly set up an assortment of bespoke assignments.

### The dropdown in the SW Group column

- Presets: Lets a track be placed into a preset that you define. As an example, one preset might be built from a Bed Mix and Language switch group, while another might pair those same tracks with a spoken subtitle. To establish a Preset, click the relevant cell in that track's Presets column and pick “Presets…” to bring up the Preset Manager window, where new Presets get created.

### The Preset Group Manager

After at least one preset exists, it can be switched on from the dropdown of any cell within the SW Groups column. Since a single track may belong to several presets, the Presets dropdown holds one checkbox for each preset, letting you assign more than one at a time.

### The dropdown in the Presets column

After everything's set, the metadata carried by these presets shapes how the content gets exported into the finished deliverable, leaving you with a collection of presets that hold every configured component and switch group.

### Markers

You can show the markers panel as thumbnails or as a list. In thumbnail mode, every marker on your timeline maps to a thumbnail that shows the timecode of where it sits beneath it, with the marker's color placed just left of that timecode spot. In list view, each marker occupies a row that carries these details: marker number, then frame (rendered as a thumbnail), followed by marker name, plus start timecode, end timecode, duration, marker color, along with notes. For each marker present in the Timeline, the Markers panel lays out a single row of such information.

### Inspector

On the Fairlight page, the Inspector's Audio, Effects, and File panels give you tools for handling selected tracks, buses, and clips on the Audio Timeline. TIP: For finer, “granular” control over virtual sliders, keep the Option or Shift key pressed as you click into the numerical value field and drag it to the left or the right.

### Fairlight page - Inspector - Audio tab

### The Audio Tab

Use the Audio tab to set a chosen track's volume level and to apply and tweak Track FX. With audio clips on the Audio Timeline or in the Media Pool, you can set a chosen clip's volume level and pan, apply and tweak a range of Fairlight FX and EQ, and shift the clip's pitch up or down.

### The Effects Tab

This panel surfaces any Audio Effects you've placed on a track or bus by way of the Effects section on its Mixer channel strip, as well as those dropped onto a Timeline clip from the Effects Library.

### The File Tab

Use this panel to inspect and change the metadata and configuration of chosen Timeline or Media Pool clips. To go deeper on the Fairlight page's Inspector, refer to Chapter 176, “The Fairlight Inspector.”

### Clip Mode vs. Track Mode

A Clip Mode and a Track Mode button live in the Inspector so there's no doubt over whether your parameter-property edits in the Audio tab land on an audio clip or on a track.

The Clip Mode button (circled)

The Track Mode button (circled)

- When you select an audio clip in the Media Pool or on the Timeline, the Clip Mode button lights up and the clip's name shows at the top of the Inspector, just right of the Track Mode button.
- Pressing the Track Mode button while a Timeline clip is selected makes any further Audio tab edits apply to the matching Mixer channel. At that point the name shown at the top of the Inspector changes from the clip name to the track name.

To dig further into the Fairlight Page Inspector, turn to Chapter 176, “The Fairlight Inspector.”

### Test Tone Settings for Generating Tone, Noise, and Beeps

An all-purpose oscillator lives on the Fairlight page, and you tailor its settings by selecting Fairlight > Test Tones Settings. Doing so brings up the Test Tones Settings window, which you set up to produce tones, noise, or beeps by means of five sets of controls:

- Enable/Disable Test Tones toggle: Switches the Oscillator on or off across the whole system.
- Frequency control: Dials in a custom oscillating-tone frequency anywhere from 20 Hz to 15kHz.

Defaults to 1kHz.

- Frequency buttons: Let you jump straight to 100, 440, 1K, or 2K preset tones, or to a steadily climbing

sweep running from 20 Hz to 15kHz.

- Noise type buttons: A pair of buttons lets you pick between White noise and Pink noise.
- Level dial: Sets how loud the tone or noise comes out, spanning –50dB to +10dB. Defaults to –15 dB.

The Oscillator can be configured to put out whatever tone or noise you need, after which you patch it onto tracks to record tones, or onto audio outputs to calibrate speakers. The beep options of the ADR panel, if you use them, run through the Oscillator as well. To route the Test Tone out to your speakers: 1 Pick Fairlight > Patch Input/Output, which brings up the Patch Input/Output window. 2 Under the Source dropdown menu pick System Generator, and under the Destination dropdown menu pick Audio Outputs. 3 Over on the left side, press the button for what you intend to send out — Osc (Oscillator) or Noise. 4 Over on the right side, press the wired audio outputs you'd like to route into, and press Patch. Almost at once the tone or noise should start coming from your configured speakers. Depending on the I/O settings of the particular track, when the Osc is patched through a track you may need to Arm the track via the R (record) button, or hit the Thru button under the channel's Path Settings, letting the signal pass through for output monitoring. 5 To stop, select any one of the patched buttons and press Un-Patch. To lay down a tone or noise from the Oscillator onto an audio track: 1 Pick Fairlight > Patch Input/Output, which brings up the Patch Input/Output window. 2 Under the Source dropdown menu pick System Generator, and under the Destination dropdown menu pick Track Input. 3 Over on the left side, press the button for what you intend to send out — Osc (Oscillator) or Noise. 4 Over on the right side, press the wired audio outputs you'd like to route into, and press Patch. Shut the Patch Input/Output window. 5 Press the Arm Record (R) button on the track header belonging to whichever track the Oscillator was patched onto. Assuming your Main has been patched correctly through to your outputs, the tone or noise will be audible, and that track's audio meter ought to show the level the Oscillator is putting out. 6 On the transport controls, press the Record button to begin laying that tone down onto the patched track. Once you're done, press the Stop button or hit the Spacebar to finish recording.

### Working with Timecode

Fairlight provides synchronization options letting you set up DaVinci Resolve to either chase and lock onto an outside device or separate application, or to create and send out timecode as an audio signal so an outside device can trail your Timeline. These settings are reached by clicking the Fairlight menu and picking Synchronization Settings.

### Fairlight Synchronization settings

### LTC and MTC Chase Sync

### LTC Synchronization

Suppose you wish to have Fairlight chase and lock onto an outside device or a computer system: 1 Turn on External Sync. 2 From the Source dropdown, pick the Timecode option. 3 From the Timecode Audio Input dropdown, pick a suitable audio input on your interface. 4 Set an SMPTE offset where one is called for; if not, keep it at +00:00:00:00. 5 Start the external device playing. Your Fairlight mix will then run in perfect step with that external device.

### External Sync via LTC enabled

### MTC Synchronization

To have Fairlight chase and lock onto either an app on your machine — a DAW, for instance — or an outside device that can send MIDI timecode: 1 Turn on External Sync. 2 From the Source dropdown, pick the MIDI Timecode option. 3 From the MIDI Timecode Port menu, pick the right MIDI port. As an example, to sync DaVinci Resolve with a DAW running on your computer, choose IAC Driver Bus 1. 4 Set an SMPTE offset where one is called for; if not, keep it at +00:00:00:00. 5 Get playback going on the external device or DAW, and Fairlight's audio will follow along in time.

### External Sync via MTC enabled

### Status

This portion of the Synchronized Settings dialog reports live details about how synchronization stands at the moment during playback.

- Incoming Timecode: While playback runs, this field keeps refreshing with the timecode currently being sent to DaVinci Resolve.
- Transport Status: This light goes green to signal that synchronization is holding steady during playback.
- Timecode Freewheel: With this checkbox ticked, Fairlight will produce its own timecode

briefly should trouble arise with the timecode coming in. That keeps synchronization steady and unbroken.

### Sync Status pane

### Generating Timecode

To create and send timecode as an audio signal out of your audio interface to an outside device or application: 1 Switch on Generate Timecode. 2 Pick from the Interface Output dropdown the audio-interface output through which you'd like the timecode audio sent. 3 Start playback of your Fairlight mix. DaVinci Resolve keeps feeding the timecode audio signal to its destination right up until you click the Stop button.

### Generate Timecode enabled

TIP: When a Fairlight SX36 audio interface is in play, that signal serves to synchronize a second DaVinci Resolve system, or indeed any system able to take timecode audio as a reference.

### Pro Tools AAF Import

AAF projects and media from Pro Tools can be brought into DaVinci Resolve, letting you carry an audio project across from a Pro Tools workstation to a Fairlight one. The AAF import handles embedded audio together with track automation. To run it, choose File > Import Timeline > Import AAF/EDL/XML.

### Dual-Monitor Layout

A dual-monitor layout on the Fairlight page hands the mixer and audio meters the full width of one screen while devoting the other to a full-screen timeline. Even with just a single ultra-wide display, the dual-monitor layout remains available, and DaVinci Resolve will scale the interface as though you were running two ordinary monitors side by side.

To enter dual screen mode: Choose Workspace > Dual Screen > On.

### The Fairlight page in dual screen mode

To flip which UI elements land on which screen: Choose Workspace > Primary Display > Display 1 or Display 2, an action that swaps what each of the two monitors shows while in dual screen mode.

### Customizing the Fairlight Page

For plenty of jobs on most screens, the default layout works well enough. Choosing Workspace > Reset UI Layout always brings you back to that default. That said, you're free to reshape the Fairlight page to open up extra room for particular parts of the interface as different tasks demand. To resize any area of the Fairlight page:

- Grab the vertical or horizontal divider separating a pair of panels and drag it to grow one panel while the neighboring one shrinks.

To resize the height of individual audio tracks:

- Bring the pointer down to the lower border of any audio track header, and once it turns into a resize cursor, drag the border up or down to set that track's height. With this method each track can carry its own independent size.

To resize any column of the Index:

- Hover the pointer over the divider sitting between any two columns and drag once the horizontal resize cursor shows up.

To rearrange Index columns:

- Drag any column's header left or right to relocate that column.

NOTE: To keep the track heights you've set even after a project is shut and reopened, right-click the track header and pick “Lock Track Height to.” For any height beyond the standard sizes, pick “Custom” to specify whatever value you want.

TIP: The option key likewise lets you resize the heights of every selected track at once, or use Commandoption to do the same across all selected tracks.

### Fairlight Configuration Presets

Whole configuration presets for the Fairlight page, or for individual portions of it, can be stored and recalled via the Presets Library functions, which sit under Fairlight > Presets Library. To read up further on working with the Presets Library, turn to Chapter 171, “Setting Up Tracks, Busses, and Patching.”

### Undo and Redo in DaVinci Resolve

Wherever you happen to be in DaVinci Resolve, the Undo and Redo commands let you reverse steps or commands you've carried out, then reinstate them should you change your mind. DaVinci Resolve can roll back the whole sequence of actions you've taken since a given project was created or opened. Closing a project wipes its entire undo history. When you next sit down with that project, its undo history begins fresh. Because so much capability is rolled into this one application, DaVinci Resolve keeps three distinct undo “stacks” to help you stay on top of your work.

- One shared multiple-undo stack serves the Media, Edit and Fairlight pages together, so you can reverse work done across the Media Pool, the Timeline, the Metadata Editor, plus the Viewers.
- Every clip on the Fusion page carries its own undo stack, so you can roll back the changes to each clip's composition on its own.
- Every clip on the Color page carries its own undo stack, so you can roll back the changes to each clip's grade on its own.

Across the board, there's no real ceiling on how many steps can be undone (though your own memory may impose one). To make use of that, you have three ways to undo work and return your project to an earlier state, regardless of which page you're on. To plainly undo or redo your changes one at a time:

- Choose Edit > Undo (Command-Z) to undo the previous change.
- Choose Edit > Redo (Shift-Command-Z) to redo to the next change.

The History submenu and window also let you undo a number of steps at once.

For undoing and redoing through the History submenu: 1 Bring up the Edit > History submenu, where (at most) your last twenty actions are listed. 2 Click whichever entry you want to roll the project back to that moment. Your latest action sits at the very top of this list, and the change you just made carries a check beside it. Steps you've undone but can still redo stay put in this menu, so the available options remain visible. Note, though, that if you've undone a batch of changes and then make a fresh change, no further undo is possible and those steps drop off the menu.

The History submenu, which lets you undo several steps at once As soon as you choose a step to roll back to, the menu shuts and the project refreshes to display its present state. By way of the Undo window, here's how to undo and redo: 1 Choose Edit > History > Open History Window. 2 As soon as the History dialog shows itself, click a list entry to roll back to that spot. Unlike the menu, this window puts your most recent action down at the bottom of the list. Selecting a change here dims the changes still left to redo, while the project refreshes to mirror its present state.

The Undo history window, through which you can scroll the whole undo stack on hand for the page you're on 3 Once you've finished, shut the History window.
