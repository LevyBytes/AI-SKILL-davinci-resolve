# Using The Fairlight Page (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Video: Pressing this button reveals video tracks scrolling across the bottom of the Fairlight timeline, with low, medium, or high detail available for the video media right around the playhead. Audio 1: A scrolling audio bar plus a magnified visual reference covering the audio media right around the playhead. Which audio track scrolls is picked from a dropdown menu. Audio 2: A second scrolling audio bar plus a magnified visual reference covering the audio media right around the playhead. Which audio track scrolls is again picked from a dropdown menu.

### Zoom Presets

Presets 1-7: Each of these buttons selects one of seven available zoom levels.

### Customizing Zoom Presets

Any Zoom preset can be tailored in Fairlight through the settings found in the Timeline View dialog, which you bring up by right-clicking a preset button.

### Timeline View dialog

You’re able to type in a one-of-a-kind preset name, and it surfaces as a tooltip whenever the mouse cursor rests on the matching preset button. Ticking the checkbox marked “Preset Updates Dynamically” instructs Fairlight to refresh and store the preset live as the view changes, governed by whichever checkboxes you’ve enabled in the Controls section. Any of the presets may be designated the default Zoom setting.

### Grid View Options

Choosing the Grid View options, with the Timecode Time Scale options on view Edit Grid Options Show Grid: Toggling this reveals or conceals the grid line running across the tracks beneath the Timeline. Snap to Grid: With this on, any clip you insert, reposition, or trim on a track locks onto the closest grid line.

### Time Scale Options

Timecode: Choose this and the grid tracks Timecode at whatever resolution you’ve picked. Tempo: Choose this and the grid tracks bars and beats at whatever resolution you’ve picked.

### Timecode Grid Resolution

With the Timecode Time Scale option switched on, the Grid conforms to whichever Timecode Grid Resolution you chose. Available Timecode Grid resolution choices are: 1 second, 1 Frame, 1/2 Frame, and 1/4 Frame.

### Tempo Grid Options

Selecting the Grid View options; Tempo Time Scale options shown These Tempo Grid options below dictate how the grid behaves once the Tempo option is chosen:

- Resolution: Picks the Grid resolution you want, measured in bars and beats:

Bar, 1/2 Note, 1/4 Note, 1/8 Note, 1/16 Note.

- Tempo: Here you type the tempo as a BPM value.
- Time Signature: Choose your time signature from these: 4/4, 3/4, 6/8.
- Song Start: Here you type where the Song Start Timecode sits.

### Setting the Tempo Grid Start

To establish where the Tempo Grid begins:

- Right-click the spot you want along the Timeline ruler.
- Pick Set Tempo Grid start.
- The tempo grid’s opening bar and beat jump over to that spot.

### Setting the Tempo Grid start location

### Setting the Tempo Grid from a Range Selection

To derive the Tempo value for the Tempo Grid out of a range selection:

- Draw a range selection across the Timeline.
- Right-click any point on the Timeline ruler and pick Set Tempo Grid BPM from the contextual menu.
- When the Tempo Grid Setup window opens, type how many bars the selection spans.
- Should you wish, tick Set Start from Playhead.
- Click Set Tempo From Range.
- Dismiss the Tempo Grid Setup window. The tempo over in the Tempo Grid Options settings refreshes to match.

### Tempo Grid Setup window

TIP: When deriving tempo from a range selection, pick a passage of the music where counting out the bars/beats to define the range is straightforward.

### Customizing Clip Display in the Timeline

Go to Fairlight > View Clip Info Display to bring up a dialog that lets you tailor what data appears along the bottom of every clip in the Fairlight timeline. Within this dialog you can opt to show no clip name at all, the file name, or the clip name, and you can pick from an assortment of metadata you might want on hand while working with clips in the Timeline.

### Selecting the audio clip view options

### Customizing the Timeline’s Display

Several approaches exist for tailoring the Timeline so you get a clearer look at your work.

### Playhead Modes

As described in the Timeline View Options section earlier, you’ll find settings for Page Scrolling (“Page”) and No Scrolling (“Disabled”). On top of that, Fixed Playhead mode can be switched on whenever you aren’t in Focus mode. Reach it through the Timeline View Options dropdown menu, or via View > Timeline Scrolling > Fixed. Once it’s on, the playhead stays put while the Timeline glides beneath it as you drive the transport controls or JKL to play, shuttle, or scrub in either direction. NOTE: Fixed playhead scrolling isn’t presently offered while Focus mode is active. Bear in mind, too, that switching DaVinci Resolve > Keyboard Customization away from the default DaVinci Resolve mapping to another one rewrites many of the default key commands. As one example, the Pro Tools Keyboard Customization provides no JKL transport.

### Visible Video Tracks

In the toolbar’s Timeline View Options dropdown menu, a checkbox lets you show short-height video tracks in the Fairlight timeline as a reference. That’s quite handy, since it reveals which audio clips line up with which video clips. Those video clips can additionally serve as snapping targets when you position audio. While the Video Tracks option is active:

- The Track Index lets you decide which video tracks show.
- The video track(s) are editable — both their placement and their clip trimming.
- Editing an embedded clip carrying both video and audio drops a clip holding both audio and

video onto the right matching tracks. Turn the Video Tracks option off, and dropping a clip with both video and audio onto the timeline places only the audio on the matching tracks.

### Showing video tracks on the Fairlight page

### Video and Audio Scrollers

Within the Timeline View Options, checkboxes give you the choice of displaying a single Video Scroller plus as many as two Audio Scrollers along the bottom of the Fairlight timeline.

Video and Audio Scrollers at the bottom of the Fairlight timeline When left at the default Low zoom level, the Video Scroller delivers a scrollable filmstrip of your program’s video, frame by frame, with a single scroller frame matching a single frame of your footage. The two Audio Scrollers, by contrast, each let you concentrate on an unbroken waveform view of one chosen audio track. Set which track an Audio Scroller shows using the dropdown menu over in the Timeline header.

Audio Scrollers with their dropdown menu open, the one that picks the track each will display What Are They Used For? No matter how the Timeline tracks overhead are zoomed, the Audio Scrollers consistently give you a magnified look at the particular audio tracks you care about. That lets you zero in on fine details in the audio of the one or two tracks you’re handling, even as the rest of the Timeline lays out the full stack of tracks whose clips play together right then. The Video Scroller, for its part, always presents the precise video frame tied to the present instant, making it a help for exact editing that hinges on frame‑specific tweaks. Beyond that, both the filmstrip and the waveform viewers keep scrolling throughout playback, offering a glimpse of the visual actions and audio cues arriving a moment ahead, which you can lean on while running automation or laying down foley.

### Repositioning the Scroller Playhead

As long as the scrollers are showing, you can drag the Scroller playhead either way across the Timeline to grant yourself more or less preview space on the right.

### Zooming the Video Scroller

A right-click on the Video scroller offers a Low, Medium, or High zoom level. With Low, you see the program frame by frame, much like dragging a strip of film across a Steenbeck flatbed editor. Move to Medium and High and the film strip grows steadily more condensed and scrolls faster. Scrolling the Fairlight Timeline Using the Scroller Tracks Dragging the scroller tracks in either direction scrubs through the Timeline smoothly and in finer detail, no matter how the Timeline tracks above are zoomed.

### Mixer

Through a collection of graphical controls, the Audio Mixer lets you route track channels to output channels, shape EQ and Dynamics, drop in filters and Fairlight FX, dial in levels and capture automation, pan stereo, surround, and immersive audio, plus mute and solo tracks. The Audio Mixer puts up two banks of channel strips whose controls map to the Timeline’s tracks. As a default, the left-hand bank of channel strips presents one set of controls per Timeline track, while the right-hand bank presents a separate set per bus you’ve built to steer signal flow from the audio tracks into submixes and the outputs you want. TIP: Right-click the number atop a mixer channel strip to copy/paste settings, and you can likewise copy/paste settings inside the mini views of the channel dynamics and EQ. On top of that, effects plugins (Fairlight FX, AUs and VSTs) carry their own local 3 dot Options menus in the upper right for copying and pasting settings.

The Audio Mixer, with channel strips that map to the Timeline’s tracks

- Track color: To stay organized, give every track its own color through the contextual menu you get by right-clicking that track, whether in the Timeline or over in the Tracks Index.
- Track number: This shows the number of the Timeline track that goes with each channel strip.
- Input: A dropdown menu through which you patch inputs, busses, and utility signals, plus set up the input

settings for audio signals coming through Blackmagic Design or other hardware interfaces.

- Track FX: This part of the channel strip provides purpose-built, built-in Fairlight FX plugins, fed straight

off disk and then passed along to further effects processing. Among the Track FX you can reach are Voice Isolation and Dialogue Leveler, plus the more recent trio of plugins: Dialogue Separator, Music Remixer, and Ducker. As a DaVinci Neural Engine AI effect, Voice Isolation ships only with DaVinci Resolve Studio. Chapter 181, “Fairlight FX,” covers the Track FX in depth.

- Order: A dropdown menu where, per track, you set the processing sequence among the EQ, Dynamics, and Effects.
- Effects: The Fairlight FX, VST, and Audio Unit effects you’ve added to tracks from the Effects Library show up here, accompanied by controls to enable/disable each one, to open an effect’s floating user interface or Inspector controls, and to remove that effect.
- Effects In: A button that mutes or enables, all at once, every insert effect on a track (Fairlight FX, AU or VST). This control leaves Track FX and the built-in channel dynamics and EQ untouched.
- Dynamics: A double-click brings up a bank of dynamics controls — three groupings that map to an Expander or Gate, a Compressor, and a Limiter — usable alone or together to govern the dynamics of that track’s audio.

### The channel strip Dynamics control window

- EQ: A double-click brings up a four-band parametric equalizer, rounded out by High and Low Pass filters, offering both graphical and numeric controls to lift or cut various frequency ranges of each track’s audio. From the Equalizer Type dropdown menu you can pick one of four EQ filtering flavors: Earth (the default), Air, Ice, and Fire. Those four equalizer types alter the Curves aspect and Q-factor of the transfer function. Each band gives you a filter-type choice (Bell, Lo-Shelf, Hi-Shelf, Notch) together with Frequency, Gain, and Q-factor settings (Q-factor governing the band’s sharpness), and the exact controls an EQ band presents vary with whichever filter type you’ve selected.

### The channel strip EQ window

- Bus Sends: Hit the + sign to create bus sends. They’re offered only when two or more busses exist. Making a bus send calls for at least one extra bus beyond the main output bus.
- Pan: A pan control that works for both stereo and surround panning. Drag inside it to set pan, or double-click to bring up a pan window. Which controls that window holds rides on how the audio track is mapped, but stereo and surround panning controls are both present, each with matching numeric controls.

### The Pan control window

An Option-double-click on the Mixer’s Pan control launches a different 3D Audio Pan window. Where the ordinary Pan window handles stereo and the usual 5.1 and 7.1 surround panning, the 3D Audio Pan window handles the spatial audio placement that advanced surround formats make possible, including Dolby Atmos, Auro 3D, and NHK 22.2.

### The 3D Pan window

- Bus Outputs: With these buttons you route a track or bus to one or several of the output busses.
- VCA: These buttons route that track’s channels to VCAs 1-10, or, through a secondary dialog box,

draw from the wider pool of 128 VCAs in total.

- Track name: This echoes the track name shown in the Timeline’s header controls. To rename a track from the Mixer, double-click and type into the name field.
- Arm, Solo, and Mute buttons: The same as the controls in each timeline audio track’s header. Arm turns on recording for a track. Solo silences every other track so that one plays on its own (together with any other Soloed tracks). Mute switches off audio playback from that track. You’ll find these controls in the Tracks Index as well.
- dB display: Reports the volume level, expressed in decibels, the track currently sits at.
- Automation Arm: Arms the automation control for each track. Switched on, it captures automation in Latch

mode while the transport rolls. The control also turns red as soon as a fader moves. You can set automation to “Safe” or “Off” by right-clicking this control.

- Level Meter: A live readout that tracks a channel’s signal level across the -60db to 0db range. How the audio metering displays and decays is configured under Project Preferences > Fairlight > Audio Metering.
- Fader: A track’s main vertical faders set that track’s level and let you record automation. Double-click the fader handle and it snaps back to the default level of 0. Keep Shift held while moving a fader for fine level control at .1 dB resolution.

TIP: Bus routing, VCAs, plugins, and the enable/disable of automation safe can all be set in a hurry across a chosen group of channel strips — or across every channel strip — by holding the Option key (Mac) or the Alt key (Windows) for all the selected tracks, or Command-Option (Mac) or Control-Alt (Windows) for every mixer channel strip, before you carry out the action. Shortcuts like these can shave considerable time off your workflow.

### The Monitoring Panel

Stretching across the top of the Fairlight page, the Monitoring panel presents every audio meter that maps to the Timeline’s tracks, plus the Master Output meter, the Control Room meters, and a video viewer.

### The Monitoring panel

On the left sits a row of audio meters tied to the Mixer’s channel strips — one meter per audio track in the Timeline. A given track meter shows however many channels match that track’s audio format: a single audio meter for mono tracks, two for stereo, six for 5.1, and so forth. Every one of these track and bus meters — the Loudness meters aside — plots both peak and RMS (root mean square) levels against a dB scale. Just right of the Track meters come the Bus meters, where all the busses are grouped by type, each showing a meter whose channel count matches that bus’s audio format. That way you can read the combined total of every track routed into a given bus. Farthest to the right of all is the final group, the Loudness meters, made up of two meter sets and a numeric readout area. The Control Room meter mirrors the program’s main output level, while the Loudness meter gauges the mix’s loudness on whichever scale the user selected. This keeps you abreast of the overall mix’s “integrated loudness,” the benchmark every present-day mixing specification cites when laying out client deliverables. You can change the monitoring panel’s height by dragging its bottom edge.

### Absolute and Relative Measurement Scales

Some people like reading their levels on a relative scale anchored at “0,” much as a VU meter’s needle sits above the “0,” whereas others want the amplitude’s absolute reading in LUFS and true peak. Out of the box, the Loudness meter uses the relative scale, yet you can now switch the Loudness meter between relative scale and absolute scale.

That setting within the Loudness panel surfaces the different measure types along with the absolute scale choice.

In the Loudness menu, relative scale is gauged against whichever scale you picked, so a loudness unit of 0 lines up with the target of the selected measure type. As an example, choose EBU R128, whose target measure is -23dB LUFS, and the “0” LU (Loudness Unit) equals -23dB. Pick ATSC A/85 instead, whose target is -24dB, and that value becomes the equivalent of the relative LU of 0. On the absolute scale, the Loudness meter labels its increments to suit the chosen measure type. Under absolute scale the EBU R128 meter reads -23 rather than the 0 of relative scale. With high track counts, a right-click on the panel opens a contextual menu offering single or dual rows plus narrow or wide meters. Double-clicking the bus master meters along the right side likewise gives you a double row view of them.

### The double row Monitoring panel

### Viewer

Tucked at the far-right end of the Monitoring panel, a compact viewer lets you watch video playback; it consistently displays the video frame that matches the playhead’s position.

- Resize the viewer inside the monitoring panel by dragging the left or bottom edge of its window.
- A button down in the lower-right corner pops the Viewer out into its own floating window.
- The Fairlight page supports Cinema Mode viewing (Command-F), or you can reach it from the Workspace menu,

Workspace > Viewer Mode > Cinema Viewer.

- Clean Feed mode view is also available on a second monitor: choose Workspace >

Video Clean Feed and pick the target monitor for dedicated video playback.

- The Viewer can be shut off altogether via the Workspace > Fairlight Viewer submenu.

### The Monitoring panel

### The Media Pool

On the Fairlight page, the Media Pool acts as the storehouse for every audio clip in your project — both the clips sitting in the Timeline and those you’ve brought into the project but haven’t used yet. Record audio into the Timeline and the clips it produces land in the Media Pool too, ready for later. The Media Pool turns up on every DaVinci Resolve page and holds all the video clips and timelines belonging to your project. Off to the left, the Bin list lays out a nested set of folders called bins for arranging your media, and they serve just as well for arranging your timelines. By default the Media Pool has just one bin, called “Master,” though you can add more whenever you need to sort timelines and clips: right‑click any empty spot in the Media Pool and pick Add Bin. Rename a bin by double-clicking its name and typing a fresh one, or by right-clicking the bin’s name and picking Rename Bin. Show or hide the Bin list with the button in the top-left corner of the Fairlight page toolbar.

The Media Pool in Thumbnail mode showing audio clips Over on the right, the browser area presents what’s inside whichever bin is currently chosen in the bin list. Here you’ll see every clip you bring in, every timeline you build, and every AAF, XML, EDL, and other importable file type. Within a single project you may make or import as many timelines as you like. Just as in other places, the Media Pool can appear in Metadata view, Thumbnail view, or List view. List view lets you order the contents by any one of a subset of the full metadata available in the Media page’s Metadata Editor. Audio editors will especially care about columns such as Clip Name, Reel Name, the various timecode streams, Audio Channels, Format, Audio Codec, Date Added, Flags, and Duration.

To learn about putting every Media Pool feature to use, turn to Chapter 18, “Adding and Organizing Media with the Media Pool.” The sections that follow recap a handful of the Media Pool’s main features for easy reference.

### Importing Media Into the Media Pool on the Fairlight Page

Bringing clips into the Media Pool from the Media page gives you the richest organizational options and tools, but when you’re over on the Fairlight (or another) page and need a few clips in a hurry for immediate use, several routes get you there. Bring in media by dragging one or more clips out of the Finder onto the Fairlight page Media Pool (macOS only): 1 Pick one or more clips in the Finder. 2 Drag them into DaVinci Resolve’s Media Pool, or onto a bin in the Bin list. They join your project’s Media Pool. Use the File > Import > Media command: 1 With the Fairlight page showing, go to File > Import > Media. 2 In the Import dialog, pick one or more clips to bring in and click Open. Lean on the Import Media command sitting in the Media Pool of the Fairlight page: 1 While that page is up, right-click somewhere inside the Media Pool and select Import Media. 2 Within the Import dialog, choose the clip or clips you want and press Open. They join your project’s Media Pool.

For deeper coverage of importing media through the Media page’s many features, consult Chapter 18, “Adding and Organizing Media with the Media Pool.”

### Media Pool Preview Player

Atop the Media Pool sits a preview player, a spot to open chosen source clips from the Media Pool, run them, drop marks to log them, and lay down In and Out points ahead of dragging them into the Timeline as an edit. In practice the Media Pool Preview Player stands in as a Source monitor for editing on the Fairlight page.

### The preview player in the Media Pool

- A range of viewing controls fills the title bar up top. At the upper left, a dropdown menu picks the zoom level for the audio waveform on display. Just right of it, a Timecode window reports either the clip’s duration or the duration bracketed by In and Out points. Continuing rightward, a live performance indicator reflects playback performance. Centered there is the title of the clip you’ve currently got selected, and a dropdown to its right lists the last 10 clips you’ve looked through. At the far right, a Timecode field reports where the playhead currently sits (right-click it for a contextual menu that switches which timecode shows and that copies and pastes timecode).
- The middle of the Media Pool Preview Player lays out the waveforms across all channels of the clip you’ve selected, at whichever zoom level is active.
- Down at the bottom, the transport controls comprise a jog bar for scrubbing, Stop, Play, and Loop buttons, and buttons that set In and Out.

### Bins, Power Bins, and Smart Bins

In fact the Media Pool holds three distinct sorts of bins, and the Bin list keeps each one in a section of its own. Within that list, the Power Bin and Smart Bin zones can both be brought into view or tucked away using the Media Pool Options menu (…), whose Show Smart Bins and Show Power Bins entries handle exactly that. The distinctions among the bin types break down as follows:
