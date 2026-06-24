# Mixing In The Fairlight Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Mixing in the Fairlight Page

Think of the Mixer as the command center of the Fairlight page: it gives you everything required to blend a program’s separate audio tracks into a unified, balanced result. Drawing on EQ, dynamics, panning, and level control — plus every kind of Fairlight FX, VST, and Audio Units plugin effect, all fully automatable — you can shape your sound and bring each track’s parts into balance with the rest. The purpose of this chapter is to walk through the Mixer’s many functions so its capabilities are yours to command.

### Introduction to Mixing

Here you’ll learn to lean on the Mixer for setting levels and refining the sound of every track in the timeline. The emphasis falls on what the channel strip controls do, apart from a few topics covered elsewhere: bussing is detailed in Chapter 171, “Setting Up Tracks, Busses, and Patching.” Recording audio is covered in Chapter 173, “Recording.” Mix automation is handled in Chapter 178, “Mix Automation.”

### The Mixer

Through a panel of onscreen controls, the Audio Mixer lets you route track channels to output channels, tune EQ and dynamics, set levels and capture automation, pan both stereo and surround material, toggle mute and solo per track, and insert Fairlight FX, or VST, or AU effects plugins. In the simplest case, every audio track in the timeline maps to one channel strip within the Mixer, and a lone main stereo mix bus named “Bus 1” gathers all those tracks into a single overall mix by default.

The Audio Mixer, its channel strips matched up with the Timeline’s tracks

### Tracks and Busses

As soon as you begin adding busses, the Audio Mixer reveals two groups of channel strips. The strips on the left side stand for the audio tracks in the Timeline, whereas the strips farther to the right surface a control set for each bus you’ve built.

Out of the box, the Audio Mixer splits into two zones — tracks live at left and busses at right. Should your tracks and busses together exceed what fits across your display, each Mixer half carries its own scroll bar, letting you pick which tracks and which busses sit side by side. You can equally drop the divider between the two zones for one continuous scrolling view of every track, or rearrange the channels and where they split.

### FlexBus Routing and Mixing

FlexBus is the name given to the Fairlight audio engine’s bussing system. True to that name, FlexBus delivers a high degree of freedom over bus types and how signals are routed. The earlier Fixed Bus arrangement in DaVinci Resolve Fairlight (used prior to DaVinci Resolve v17) provided a more constrained, fixed bus topology that remains available, yet FlexBus lets you patch outputs and sends however a given project demands. Under FlexBus, any track may feed up to ten busses, plus sends — each with their own level and pan controls — to ten more busses. A bus can route into other busses as many as six layers deep, which supports intricate stem building and processing and yields separate deliverables. See Chapter 171, “Setting Up Tracks, Busses, and Patching,” for more.

### What is a Bus?

In an audio mixer, a bus is nothing more than a shared point where signals join. A bus may be mono, stereo, or some wider format such as 5.1 or Dolby Atmos 9.1.6 (which carries 16 audio signals). These bussed junctions serve as the audio’s mixing points: every audio track sending its signal into the bus is added together to form a master output for that bus.

### Bus-to-Bus Routing

Some mixes need only one bus — the default stereo Main 1 bus might suffice for straightforward stereo work. Alternatively, you can build “submixes” in which several busses pour into still other busses to form a master mix. You might, say, keep a dialogue bus, an effects bus, and a music bus so each group can be controlled on its own through its bus “master,” then send those 3 masters into a main output bus for the final rendered mix. The output of a bus can also be routed to an audio track to record what comes out of it, or sent to monitor speakers so you can hear the real time result. And ultimately, the Deliver page is able to render whatever your chosen master bus outputs into a final bounced file.

The FlexBus architecture lets a wide range of bus track types be created or altered. Because busses are user-definable, they support bus-to-bus, bus-to-track, or track-to-bus routing, and each bus can sum signals running from mono all the way to fully immersive formats (Dolby Atmos and Ambisonics, for example) however you choose. Just like every other audio track type in Fairlight, bus types remain changeable whenever the need arises. What makes FlexBus so capable is that it can steer signals toward many destinations simultaneously, enabling elaborate mixing setups. Suppose you must produce two mixes whose content is the same but whose output levels differ. You could set up two mix busses — one aimed at a target output level of -14 LUFS and the other at -24 LUFS. The completed mix signal goes to a single bus, which then splits into two further busses: one carrying a limiter tuned for the -14 LUFS mix and the other set correctly for the -24 LUFS mix, so both versions emerge at once. With Ambisonic work, one Ambisonic bus can be routed into another even when their orders don’t match, and the Fairlight engine and FlexBus take care of any necessary up- or down-mixing on their own.

Broadened Dolby Atmos features and Ambisonics are both supported by FlexBus; turn to Chapter 184, “Immersive Audio Workflows,” for details.

### FlexBus bus routing buttons

### Legacy Fixed Bussing

Before DaVinci Resolve 17, the Mixer used a fixed layout with set, unchanging counts of sends, submix busses, and main outputs. To stay compatible with older projects, DaVinci Resolve continues to support that earlier “legacy” bussing layout. Under today’s FlexBus bussing, the Mixer’s appearance differs a bit: the legacy Mixer’s Aux panel is now called Bus Send, and its Main/Submix panel is now Bus Outputs. Within the legacy Fixed Bus view:

- The channel strip for each audio track carries Main and Submix bus buttons, which route that strip’s audio output either to a Sub (commonly used to group subsets of tracks into submixes) or to a Main (commonly used for outputting or rendering complete mixes).
- Every Sub and Aux channel strip carries a set of Main buttons, allowing varied groupings of Subs to be routed to each Main. Because Main channel strips are the end of the bussing chain, they bear no buttons.
- Tracks are routed to busses, and busses to other busses, by way of the Main and Submix buttons.

### Main and Submix bus buttons

### Using Legacy Fixed Busing

Should you prefer the former Fixed Bus mapping approach, you can enable it on new projects by opening the Project Settings > Fairlight panel and ticking the “Use fixed bus mapping” checkbox. That said, since the older legacy fixed bus system offers no real benefit and a number of capabilities exist only in FlexBus, FlexBus is the recommended choice.

### Converting Older Fixed Bus Projects to FlexBus

To migrate an older Fixed Bus project over to FlexBus, follow these steps:

- Open Project Settings > Fairlight.
- Beneath the Bussing heading, clear the “Use fixed bus mapping” checkbox.
- A dialog then appears that lets you convert the project to FlexBus.

### Customizing the Onscreen Mixer Controls

Found in the Mixer’s upper right-hand corner, the 3 dot Option menu offers a range of choices for tailoring how the Mixer looks and for deciding which controls stay visible or hidden:

### The Small Track Mixer view

- Full Track Mixer or Small Track Mixer option: The Full Track Mixer devotes extra space to buttons and controls big enough to read without straining, whereas the Small Track Mixer fits a far greater number of channel strips on screen simultaneously.
- Show Labels option: These are the category names for the Mixer’s functional regions, shown along the far left edge of the channel strip area. They help newcomers find their way, but after you grow comfortable with the layout, switching them off frees up a little extra space for an additional channel strip or two.
- Channel Strip Control Visibility options: Lets you reveal or conceal controls within the Mixer. Anything you won’t be using, no longer need to tweak, or want left undisturbed can be hidden.

### Selecting Channel Strips and Tracks

Selecting a track in the Timeline simultaneously selects its matching Mixer channel strip, and the reverse holds true as well:

- For a single track, a plain click does it.
- To grab a run of adjacent tracks, click a first track or channel strip, hold down Shift, and

click on last item you want in your selection.

- Within the Mixer, you can equally select several channel strips by clicking and dragging a

bounding box around the tracks you want to select.

- For tracks or channel strips that aren’t side by side, command-click each one you

want to add to your selection.

Picking several channel strips selects the matching tracks over in the Timeline

### Track Organization

Three organizational attributes belong to every channel strip, helping you recognize which strip handles which portion of the mix. Track color: each track can wear its own color code as an aid to organization. That color shows up in the Timeline track header, the Mixer, and the meters so you can tell at a glance which track ties to which channel strip and meter. A strip’s track color and track number sit at its top.

Track number: this is where the number of the corresponding timeline audio track is shown for each channel strip. Track name: this echoes the name found in the track header of a Timeline track. Rename an audio track in either the Timeline or the Mixer, and the new name shows up here.

Each track’s name sits between the assignment buttons and the arm/solo/mute buttons

### Rearranging Tracks

To move tracks and busses around within the Mixer, click and hold a track name and drag it left or right to wherever you want it. The technique applies whether you’ve selected one channel strip or several. While you drag the mouse, a white line marks the destination, and the Index updates to match the change.

### Rearranging tracks by moving a Mixer channel strip

### Disabling Tracks

To switch off an audio track from the Mixer, right-click the track number atop its channel strip and pick Disable Track from the contextual menu; running through the same steps again turns the track back on. To disable several tracks together, select them, Option right-click any track number among them, and pick Disable Tracks from the contextual menu.

### Disabling multiple tracks via the Mixer

### Managing Channel Strips Using the Index

Gathering every track of the current Timeline into one list view, the Index makes timelines packed with tracks far simpler to handle. Its columns surface each track’s visibility, track number, name, controls, channel format, monitor assignment (where there is one), ADC controls, and VCA assignment. Through the controls in those columns you can run the current Timeline’s tracks — revealing or hiding them, flipping track controls, or reordering them. A right-click on one or more selected tracks additionally lets you color code them or switch the track type.

Both the Timeline and the Mixer have all their tracks listed in the Index’s Tracks panel.

### Showing and Hiding Tracks

The Index’s Tracks panel lets you tuck away tracks you aren’t working on so the ones you do need have more room. TIP: To toggle visibility across several tracks fast, click and drag upward or downward across the eyeball button of each track you want to flip.

### Color Coding Tracks

Pick one or more tracks, then right click any of those selected and choose a hue from the contextual menu’s Change Track Color submenu.

### Toggling Lock, Record, Solo, and Mute

Much like visibility, the Lock, Record, Solo, and Mute controls let you turn many tracks on or off in a hurry: click and drag upward or downward across the Lock, R, S, or M buttons you wish to toggle.

### Rearranging Tracks

Within the Index’s Tracks tab, reorder tracks by clicking any track strip region between the other controls and then dragging that track upward or downward in the Index. A white line during the drag indicates where the track lands once you let go. You may even grab an unbroken run of tracks and shift them all to a fresh position in the Timeline in one move. Managing the Dividing Line The Index defaults to two track zones — one holding audio tracks and another holding busses and VCAs, with a dividing line between them. Busses and VCAs can be pulled up out of that divider into any spot and any order. That comes in handy, for example, with a run of dialogue tracks where you want to bring the dialogue bus right up beside them. Drag the dividing line wherever you like, so you can preserve the two-zone split yet rearrange what each shows. After the order changes in the Index, the Mixer panel and the Meter panel both reflect it. Reordering busses and tracks lets you tune your workflow to whatever group of tasks is at hand. Single Mixer View The three-dot Option menu at the top of the Mixer panel includes a Single Mixer view choice. Single Mixer view drops the divider line out of the Index’s Tracks tab altogether, giving one uninterrupted scroll of the tracks across both the Mixer panel’s horizontal scroll and the Index’s vertical scroll. The divider can be brought back whenever you want.

NOTE: To put the bus order back to how it started, pick “Reset Bus Order” from the three-dot Options menu at the Mixer’s upper right.

### Changing Track Type

An audio track’s track type denotes its channel width and format, and you’re free to change it whenever you like. A mono track, for instance, could become a stereo, 5.1, or 12 channel adaptive track. To do so, select one or more tracks, right-click any of them, and pick another type from the contextual menu’s Change Track Type submenu. NOTE: Bear in mind that moving from a wider track type down to a narrower one may require you to also specify which channels of the larger source audio file remain audible on the smaller type. That’s set through the Clip Attributes choice on a clip’s contextual menu, using the Audio tab.

### Deleting Tracks

Remove a single track by right-clicking it and picking Delete Track from the contextual menu. To wipe out several selected tracks at once, right-click any track in the group and pick Delete Tracks from the contextual menu.

### Fairlight Mixer Signal Path

A mixer’s signal path — its layout, or “topology” — sets out how audio signals travel from one stage to the next. On the Fairlight channel strip, the standard flow runs like this: 1 Audio source: the Input menu picks where the signal originates — file playback, a bus, live input, and so on. 2 Path Settings: reached through the Input menu, these let you tweak the incoming signal. 3 Track FX: the built-in effects, namely Voice Isolation (Studio only) and Dialogue Leveler, off by default. 4 Effect: any Fairlight FX, AU, or VST effects. 5 Dynamics: a dedicated per-channel dynamics processor offering expander/gate, compressor, and limiter. 6 EQ: a dedicated 6 band EQ with adjustable gain, frequency, and Q. 7 Output Routing: covers panning and bussing. From there the channel strip’s main fader governs the level feeding any main output busses it’s assigned to. Bus Send faders set the level going to whatever destination a mixer channel send targets, and can be configured pre­‑or post-fader.

### What Is An Effects Insert?

Every effect you place on a channel switches on a signal processing “insert” — an insertion point. From there the source signal runs through the effect’s input to its output, then carries on to any further insert(s) and on to the next stage in the Mixer’s signal flow. Beyond the built in Dynamics and EQ processing, DaVinci Resolve allows six inserts per channel in all. Clicking the Input area opens the Input dropdown menu, where you can patch inputs, patch busses, and set up the input parameters for audio signals coming through Blackmagic or other hardware audio interfaces.

“Pre” vs. “Post” When a signal is described as pre, it’s tapped for use ahead of some other connection point. You might, for instance, favor pre-fader metering since the meter then always reflects the original signal level arriving from disk. A post signal, by contrast, is taken after a connection point. Typically you’d want effect sends headed to a reverb to track a track’s main fader so the reverb level rises and falls with the overall level. For that reason, Bus Sends default to post fader routing.

### Input

To learn more about working with the Input menu’s options, consult Chapter 171, “Setting Up Tracks, Busses, and Patching.”

Through the Input dropdown menu you can begin patching any source that’s available by way of the Patch Input/Output window.

### Path Settings

Selecting Input at the top of the Mixer channel strip brings up the Path Settings control window. The controls there let you alter several aspects of the Mixer channel strip that might need attention before or after recording — managing the mic/line inputs on Fairlight audio interface hardware, among other things.

### Path Settings window

### Mic/Inst

This panel shows controls only when channels 1 or 2 of a Fairlight SX36 audio interface are hooked up to your system. With that connection in place, you can remotely drive every option — level included — for the SX36’s mic/instrument inputs whenever they’re assigned to the channel. Lacking an SX36 connection, the area stays empty.

### Record Level

- Record: Tied to and the same as the channel strip’s Record Enable button, placed here for convenience; pressing either one activates the other.
- Thru: Lets the input signal reach the Mixer without turning on a record path. It’s perfect when you want a source always on hand purely for monitoring.
- Record Level: Lets you put a digital gain change on the record path to disk, downstream of your audio interface’s analog-to-digital converter. Ordinarily leave this at 0.0 (no change, unity gain), since it governs the level being recorded to disk. For the best audio fidelity, the recommended approach is to manage the input level into DaVinci Resolve with your audio interface’s own level controls. Even so, you may occasionally want a touch more level, or lack access to the interface’s controls, and in those cases this input adjustment is available.

### Trim

- Polarity: Flips the polarity of the signal entering the channel strip — often called “flipping the phase.” Picture an input like an explosion whose transient attack yields a strongly positive-going waveform sitting mostly above the zero line. Inverting the polarity makes that signal chiefly negative-going, so its waveform now bunches below the zero line. Polarity inversion is sometimes employed to bring signals from several microphones into tighter alignment, and it can serve creatively to shape such a signal’s frequency response.
- Trim Level: Lets you adjust the level of the signal arriving from disk, after the Track FX (which work straight off disk) and before every other effect. Sitting downstream of the recorded-to-disk signal, Trim Level leaves the recording level untouched. As a playback adjustment, Trim lets you set how loud the signal entering your mix is so as to optimize what feeds the effects and busses, or to nudge an otherwise flawless mix element slightly up or down.

### Direct Output

Every audio channel strip can switch on a direct output capable of feeding any other input destination. To patch that source, use the Track Direct option in the Patch Input/Output dialog through the Source dropdown.

- On/Off: Turns the direct output on or off.
- Pre: Places the direct output’s tap-off point pre (ahead of) the channel fader. On by default.
- Level Control: Adjusts the level across the range from full off (minus infinity) up to +10 dB. Default is 0.0 (unity gain).

Further detail appears in Chapter 171, “Setting Up Tracks, Busses, and Patching.”

### Insert

Bound to and the same as the channel strip’s Effects In button, provided here for convenience; pressing either activates the other. With one toggle it moves every Fairlight FX, AU, or VST effect on a channel into or out of the signal path.

### Effects

Fairlight FX, VST, and Audio Unit effects can all be placed on the Mixer’s channel strips. Such an effect acts on the whole track rather than on just one or more of that track’s clips in the Timeline. Clicking the plus (“+”) button reveals a dropdown menu from which any Fairlight FX, VST, or AU effect installed on your machine can be added to the track. Entries in that menu are grouped by processing type, and within each type a nested set offers Fairlight FX, AU, and VST (on a Mac) or Fairlight FX and VST (on Windows). NOTE: What you’ve installed determines the lineup, but the audio effects offered for Mixer channel strip inserts is frequently near to — or the very same as — those reachable for clip-based audio processing in the Effects panel along the left of the Cut, Edit, and Fairlight pages. TIP: Keep favorite effects handy at the top of the list by flagging them as favorites in the Effects panel. To mark one, click the star beside its name.

Clicking the plus sign brings up the Effects dropdown list for assignment

Hover over any effect in the list to surface controls for turning it on or off, swapping or removing it, or opening that effect’s custom controls (its own user interface).

Holding the pointer over an effect insert brings up that effect’s controls.

### Changing the Order of Effects on a Channel

To rearrange the effect order on any Mixer channel strip, click the Effects Order button. The dropdown that opens lets you reshuffle the routing among every insert effect (Fairlight FX, or AU, or VST plugins) together with the built-in Dynamics and EQ modules. By default that routing is Effects (“FX”), Dynamics, EQ.

### Effects Order dropdown menu

Reordering effects can lead to markedly different creative outcomes. As a rule, for instance, it’s wise to put noise reduction at the head of a signal chain so you don’t alter the volume or character of the noise floor you mean to strip out, letting the plugin work at its best. You might likewise place dynamics processing ahead of EQ, since reshaping your source’s spectral content can change how the compressor reacts.

### Moving Inserts by Dragging

Relocating inserts is as easy as clicking and dragging one to a fresh spot. With this method you can carry an effect from one channel over to another, or shift or trade an effect’s place on a channel to a different insert slot on that same channel (bumping aside whatever plugin was already there). Keep in mind that, for now, the technique won’t copy tracks to busses or the other way around.

### Copying and Pasting Effects
