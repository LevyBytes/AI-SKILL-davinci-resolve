# Working With Audio In The Edit Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Working with Audio in the Edit Page

Right inside the Edit page, DaVinci Resolve packs a robust toolkit for editing, mixing, and mastering the audio in your programs. No matter whether you are tweaking synced audio for dailies, polishing the levels of a cut you are putting together, mixing a program for output, or importing the sound designer’s audio mix files and laying them in so you can output them for mastering, DaVinci Resolve supplies Level, Pan, and Channel Assignment controls to govern your audio output across both monitoring and delivery, automated fader recording at the track level and the clip level for mixing, plus VST and Audio Unit audio filter support so you can master audio tracks and channels with industry-standard noise reduction, compression, EQ, and further filters. And should that still fall short, the Delivery page lets you export to Pro Tools, handing off your program along with its audio ready for more work. After you wrap the editorial audio work in your program and you want to really dig into its audio for fine-grained editing and mixing, the audio-focused tools on the Fairlight page are there. To read more, turn to Chapter 170, “Using the Fairlight Page.”

### Audio in the Edit vs. Fairlight Pages

Although the Fairlight page delivers purpose-built audio editing and mixing fit for sweetening your program’s audio once the edit is done, the Edit page brings broad audio powers of its own. Those let editors cut and refine audio clips, dial in levels, and run simple mixes while they first build the program. Once the pieces are cut together, though, the intent is for you to move freely between the Edit and Fairlight page as you polish, leaning on whichever environment best fits the job in front of you.

### Compatible Audio Formats

Among the formats DaVinci Resolve works with you will find WAVE and Broadcast WAVE, AIFF, MP3, AAC (M4A), CAF, plus iOS Voice Memo (macOS only), the AC3 audio format housed in either MTS or QuickTime containers, and Enhanced AC-3 (macOS and Windows only). When it comes to sample rates, the audio DaVinci Resolve handles runs to 32, 44.1, 48, 88.2, 96, and 192 kHz, among others.

### Assigning Audio Channels in the Media Pool

As soon as you bring audio into the Media Pool, it pays to confirm that whatever channels those files hold are mapped properly before you begin cutting clips into the Timeline. Put differently, you want stereo files set as stereo clips, 5.1 and 7.1 files set as surround clips, and multi-channel files set to surface as many tracks as you mean to edit on their own in your program. You make a clip’s channel assignments from the Audio panel of the Clip Attributes window. This matters especially once a clip carries more than two audio channels. Production sound recordists, for instance, may lay down three, six, or even more audio channels, one for each of the several microphones used on set to capture different actors at once, along with a mixdown track. In that situation you have to spell out how many of these channels should play (or stay muted), along with how many audio items belong on the Timelines of the Edit and Fairlight pages. Clips that are mono, stereo, 5.1, or 7.1 sort themselves out automatically, yet multi-channel clips that need custom assignments in the Media Pool ought to be remapped through Clip Attributes where needed, so DaVinci Resolve can more readily drop incoming audio clips onto the right Timeline track. You may change the clip attributes one clip at a time or for a batch of selected clips together. To read more about these settings, turn to Chapter 22, “Modifying Clips and Clip Attributes.”

### How to Assign Audio Channels

Within the Audio panel of the Clip Attributes window, every audio-bearing clip offers the options below:

The controls available for adding tracks with which to remap channels At the top of the Track/Channel list sits a group of controls for adding extra tracks to a clip. Those extra tracks let you remap the clip’s available channels so they show up as more items in the timeline once you edit it, with one item for each track that has an unmuted channel. The way you deal with audio in your timeline is your call. Take production audio made of five channels, four for separate microphones plus one mixdown channel: you might lean on Clip Attributes to fold every channel onto a single track.

A single-track clip carrying four channels, shown in the Clip Attributes window’s Audio panel

Under this mapping, the audio clip shows up as a lone item on a single Edit page Timeline track, or as five lanes within one track on the Fairlight page Timeline. Either way, you get one editable unit out of it.

### A single audio channel exposed in the Timeline

As another option, you could silence the four separate microphone channels and listen to only the top mixdown channel. To do that, set channels 2-5 to mute. Muted channels never go away, they simply are not heard, and you can switch them back on any time by right-clicking a clip in the Timeline and choosing Clip Attributes to return to these controls for the particular timeline clip you have cut.

A clip with four muted channels, shown in the Clip Attributes window’s Audio panel NOTE: When you export audio clips that have muted tracks to Pro Tools from the Deliver page, those muted channels go along in the export too.

A further alternative is to build these clips with five separate audio tracks, each carrying a single audio channel, so every channel surfaces on its own in the Timeline for independent editing. Begin by making the top track Mono using Embedded Channel 1. Next, through the Add channel controls at the top of the channels list, set Tracks to 4, the format to Mono, and click Add to spawn four more tracks beyond the one that clip started with. Pointing channels 2-5 at these fresh tracks gives the track mapping shown in the next screenshot. The Clip Attributes window’s Audio panel once four channels have been added Cut a clip like that into the Timeline and you wind up with five linked audio items spread across five separate audio tracks, every one of them editable on its own in the Timeline.

Each channel exposed as a separately editable clip in the Timeline

### Support for Mixed Audio Track Formats from Source Clips

DaVinci Resolve likewise handles media whose several audio tracks hold channels in differing formats. A clip bearing one stereo track, one 5.1 surround track, and six mono tracks, say, can all be configured properly from the Audio panel of Clip Attributes once that clip is imported. That Audio panel of Clip Attributes now lets you decide which format (Mono, Stereo, 5.1, 7.1, Adaptive) the channels inside a given clip take. So you can build clips of several tracks, each potentially drawing on a different audio format with a different mix of clips, which proves useful for mastering.

Through Clip Attributes you can now spread channels across separate tracks, each holding its own channel assignments.

### Mono-Multichannel Audio Files with Suffixes Import as a Multichannel Clip

DaVinci Resolve can read mono audio files carrying channel-name suffixes and bring them in as one formatted multichannel audio clip. Which format results turns on how many files it finds and what their channel suffixes are. To illustrate, Audio001.L.wav and Audio001.R.wav on their own come in as a stereo ‘Audio001.wav’ clip. Add a third file bearing a ‘C’ or ‘LFE’ suffix and you get LCR or 2.1 formatted media.

Importing multi-mono audio files to a single multichannel track

### Editing Audio Into the Timeline

In the Edit page Timeline, a distinct group of audio tracks holds every bit of audio you cut into the Timeline, plus any standalone audio files that may have arrived together with an AAF or XML file.

### Editing Audio Using the Source Viewer

Load an audio-only clip into the Source Viewer, or load a clip holding both video and audio and switch the Viewer to Audio Waveform, and you get a split view: the full waveform of the whole source clip fills the top half, while the bottom half carries a magnified slice of the waveform that you can zoom from 1x to 50x via the Zoom menu in the Source Viewer’s upper-left corner. From here it is easy to drag the box up top to locate the audio section you need against the entire clip, all while still dropping In and Out points precisely with the scrubber bar underneath. This view lays out every channel inside each track of the current clip. Just as with any other clip, you can add markers and lay down In and Out points for audio clips to get ready for editing.

### An audio clip opened into the Source Viewer

### Simultaneous Audio Waveform Display in the Source Viewer

You can also edit off audio waveforms even with the Source Viewer set to Source. A pair of options in the Option Menu put a superimposed audio waveform along the foot of the Viewer, laid over the video of whichever clip is selected.

- Show Current Frame Audio Waveform: Displays a magnified stretch of audio that scrolls along as the clip plays. Handy for catching dialog and music cues while you run through a clip.
- Show Full Clip Audio Waveform: Displays the audio waveform spanning that clip’s whole source media, with the stretch between the In and Out points you set in the Source Viewer highlighted. Handy for steering through the clip by treating the audio waveform as a reference.

With “Show Current Frame Audio Waveform” switched on, the Source Viewer puts the audio waveform along the foot of the picture

### Using Multi-Channel Timeline Tracks

Multi-channel audio tracks on the Edit page Timeline come in handy when your clips are stereo, 5.1, 7.1, or carry some arbitrary count of channels captured in the field, because you can pack all those channels as one clip onto one track, correctly routed to your project’s outputs and easily handled as a single item in the Timeline. Open the Fairlight page, though, and you will find that while the total tally of audio tracks matches the Edit page, the Fairlight page presents the channels the Edit page keeps hidden as lanes inside each track, surfacing every channel as a visible audio item in the Timeline. That way editors can deal with multi-channel audio free of visual clutter, while audio editors and mixers get to see every channel on every track to finish their work. Returning to audio tracks on the Edit page, several kinds exist, paralleling the several kinds of audio clip: Mono, Stereo, 5.1, 7.1, and Adaptive. Although you can cut any sort of audio clip into any sort of audio track, any clip audio channels beyond the channel count a given timeline track type holds get muted. Nothing stops you, for instance, from cutting a six-channel Adaptive audio clip onto a Mono audio track, yet you will hear only its first channel, since a Mono track puts out a single channel. For that reason, it pays to lay out your timeline so each clip rides on a track able to hold the channel count it carries. TIP: Cut an audio clip into the undefined gray region below the existing audio tracks in the Timeline and new audio tracks spring up automatically, matching in count the number of tracks the clip you drag holds, with every new track given audio mappings that fit the incoming audio items.

### Defining Timeline Audio Track Channels at Creation

As you make a brand-new audio track, you must decide what type of audio track it should be. A right-click down in the lower audio area of the Timeline track header opens a contextual sub-menu offering three distinct kinds of audio track to create.

- Mono: Holds a single channel.
- Stereo: Holds stereo left and right channels. Stereo tracks can be panned.
- 5.1: Carries the six channels that make up a 5.1 surround mix. On the broadcast side, SMPTE lays out

Left, Right, Center, LFE, Left Surround, Right Surround. For cinema distribution the order of these tracks is Left, Center, Right, Surround Left, Surround Right, and LFE.

- 7.1: Carries the eight channels that make up a 7.1 surround mix. On the broadcast side, SMPTE arranges them as Left, then Right, then Center, followed by LFE, next Left Surround with Right Surround, and lastly Back Surround Left plus Back Surround Right. For cinema distribution the sequence runs Left, then Center, then Right, followed by Left Surround alongside Right Surround, then LFE, and closing with Back Left Surround plus Back Right Surround.
- Adaptive: Able to carry as many as 24 audio channels. An adaptive audio track accepts clips bearing assorted channel combinations, up to the ceiling set for that track. How many channels a particular Adaptive track permits is something you define (1–24) at the moment the track is made. Cut a clip carrying more channels into an Adaptive track built for fewer, and the surplus channels get muted.

A set of four audio tracks of differing kinds, reading top to bottom as Mono, then Stereo, then Adaptive, then 5.1 Changing How Many Channels an Audio Track Has Should you have laid out your timeline with one type of audio track only to realize you really want another, you can switch any audio track’s type whenever you wish. Simply right-click anywhere in that audio track’s timeline header and pick an option from the contextual menu’s Change Track Type To submenu.

### Contextual menu for changing audio track types

### Creating Timelines With Audio Mixer Presets

To support advanced audio workflows and smoother use with Fairlight, you can now spin up a timeline whose audio tracks are pre-assigned from a Fairlight Configuration preset you built earlier. To do so, start a new timeline and tick the “Use Fairlight Configuration Preset” box. A drop-down then shows up, letting you pick the exact preset for the Timeline. You build Fairlight Configuration presets from the Fairlight Presets Library, reached through the Fairlight menu. To read more, turn to Chapter 171, “Setting Up Tracks, Busses, and Patching.”

### Editing Audio Clips Into the Timeline

Cut a video clip that has audio with it, or an audio-only clip, into the Edit page Timeline, and what shows up hinges on how the audio’s inner tracks and channels were laid out in the Media Pool through Clip Attributes. Define a clip to surface several audio tracks, each carrying a different channel, and you trade the ease of handling many audio channels as a single item for the latitude to edit each audio channel on its own, as separate clips in the Timeline. Suppose you were handed a multi-channel recording made of two boom microphones, two separate lavaliere microphones, and a mixdown track all captured at once: through the Audio panel of the Clip Attributes window you can set that clip’s audio as 5-channel Adaptive audio across 5 tracks of one channel apiece. Cut that into the Timeline and you end up with five separate audio items spread over five tracks. Cutting a multi-channel production recording into five distinct audio tracks This way, once you cut the clip into the Timeline, each audio channel arrives as its own clip on its own Timeline audio track, editable on its own so you can work the scene to pick the best dialog off each microphone.

Cutting multi-track audio to single out the strongest dialog from each microphone

### Changing Audio Clip Attributes After Editing

Settling on which audio tracks and channels get assigned is best done before you start editing. The reason is that after a clip lands in a timeline, the Clip Attributes window can no longer change how many audio tracks and audio channels surface in the Timeline. You can, however, still turn to Clip Attributes to alter which channels are assigned and/or muted among the tracks and channels you have already cut into the Timeline. Say you are cutting clips holding five channels of source audio (channels 1 and 2 form a stereo mix and channels 3 through 5 are three separate microphones): you might have configured your synced source clips with a single audio track holding five audio channels, channels 3–5 left muted. Down the line, a handful of clips would sound far better drawing on channel 4 alone, the isolated lavaliere microphone for that actor, so you can pick those clips and use the Audio panel of Clip Attributes to mute every channel but channel 4. If for any reason you must surface more audio tracks in the Timeline than the clip was first set to use, here is the procedure. To re-cut an audio clip so it surfaces more audio tracks than were available at first: 1 On the Timeline, right-click the clip whose audio track mapping needs changing; from the contextual menu, choose Find in Media Pool. 2 Over in the Media Pool, right-click that clip; from the contextual menu, choose Clip Attributes. 3 Bring up the Audio panel within the Clip Attributes dialog and decide how many audio tracks and audio channels that clip should get. Click OK. 4 That settled, cut the revised audio clip out of the Media Pool onto the Timeline to swap out the original by whatever method suits.

### Displaying Waveforms in the Timeline

Through a button at its top, the Timeline View options palette flips the Audio Waveform display on and off. The Audio View options then let you decide how your waveforms appear on the Timeline.

- Audio View Options: When waveforms are visible, three buttons steer their appearance in the Timeline. Non-Rectified Waveform: Switches between drawing the waveform upward from the audio track’s bottom or centering and mirroring it on itself. Full Waveform: Drops the divider bar that separates the waveform from each audio clip’s file name area, letting the waveform fill the whole height of each audio bar in the Timeline. Waveform Border: Outlines every waveform with a dark border so they stand out more.
- Video track height slider: Resizes all video tracks together, apart from the audio tracks.
- Audio track height slider: Resizes all audio tracks together, apart from the video tracks.

Within the Timeline View drop-down, the Audio Waveform display option is ringed in red. Reading left to right, the Audio View Options run Non-Rectified Waveforms, Full Waveform, then Waveform Border.

By default a clip shows one averaged audio waveform standing for all its channels, but you can flip any clip to a vertical stack of each separate waveform by right-clicking that audio clip and choosing Display Individual Audio Channels. Cut an audio clip and every audio channel in it gets cut along with it. Audio channels packed inside one track cannot be edited individually.

Enabling the display of multiple channel waveforms in the Timeline

### Switch Mono Audio Channels of a Clip on the Timeline

On mono channel lanes in the Edit page, you can swap your mic (or other) audio sources either from a context menu or through the Inspector. This helps when you are cutting with a mix track and notice a lav mic carrying noise that you would rather replace with boom audio. Two routes exist for swapping a mono audio source: through the timeline or through the Inspector. Changing mono audio sources via context menu on the timeline: When you sit on a mono timeline track whose parent audio file holds several mono tracks, right-click it and an Audio Channel choice turns up at the foot of the context menu. From the hierarchical menu you can then pick any mono source.

A right-click on an audio clip surfaces the available source audio channel choices for you to pick

Command right-clicking an audio clip on the timeline surfaces nothing but the source audio channels

For an even tidier workflow, press Command right-click instead and you get a drop-down listing only the mono sources: Changing mono audio sources via the Inspector: Once a timeline clip is open through the File Inspector, you can swap mono track/lane sources via a drop-down on the channel waveform.

To swap the audio channel, work the drop-down menu sitting on the channel within the File Inspector’s Auµdio Configuration section.

### Editing Audio In the Timeline Using In and Out Points

Every command and tool that works on video clips works on audio clips as well. Worth knowing, though, is that one of the most widespread audio-editing techniques from other environments is here in DaVinci Resolve too: marking off a span of audio to cut, copy, or delete with Timeline In and Out points, which lets you readily remove, shift, or duplicate partial audio stretches with no need to reach for the Razor Edit or Split Clip commands. Deleting an audio section by means of In and Out points: 1 In the Timeline, lay down In and Out points that mark the audio span you mean to remove. Where needed, switch off the Auto Select controls on tracks to leave out overlapping audio clips you do not want deleted in this pass. 2 Tap the Backspace key to remove the audio span and leave a gap, or tap the Forward Delete key to remove the span and ripple the Timeline shut over the gap.

Laying down In and Out points to mark off a span of audio for deletion

Removing the audio with the Backspace key so a gap remains

Copying an audio section by means of In and Out points: 1 Lay In and Out points in the Timeline to mark the audio span you mean to copy. Where needed, switch off the Auto Select controls on tracks holding overlapping audio you do not want copied; Option-click the Auto Select control of the audio track you are copying from to solo it, and Shift-click any video track’s Auto Select control to switch them all off. Here we are copying a bit of background ambience to keep building an ambience track.

Laying down In and Out points to mark off a span of audio for copying 2 Tap Command-C to copy that audio span. 3 Tap Option-X to wipe the Timeline In and Out points, then bring the playhead to wherever you want the copied audio span pasted. 4 Tap Command-V to paste the copied audio. When looping a span of audio, paste repeatedly to loop whatever you copied.

Pasting the background ambience several times to loop it

### Resizing Audio Clips in Subframe Increments

As an option, DaVinci Resolve permits subframe audio tweaks to the In and Out points of Timeline audio clips.

### Enabling and Disabling Subframe Editing

Found in the Editing panel of the DaVinci Resolve User Preferences, the “Align audio edits to frame boundaries” preference decides whether an audio clip’s In and Out points snap to whole frame boundaries the way video clips do. Leave this option on and subframe audio edits are off-limits; turn it off (its default) and they are allowed.

### Subframe Editing of In and Out Points

Though the playhead itself will not move in subframe steps, you can resize audio clips in subframe steps by dragging an audio clip’s In or Out point on the Timeline, or by dragging an audio edit to roll it. That helps when trimming tiny audio bits like pops, clicks, or vocalizations.

An audio item’s Out point being resized in subframe steps, viewed inside a one-frame playhead shadow Be aware that with Linked Selection on, trying to resize a selected Video+Audio pair runs into the whole-frame resizing video demands, which stops you from resizing the audio on its own. The fix is simple: Option-Click to grab the linked audio item by itself, after which subframe resizing is yours to do freely. On top of that, with snapping enabled, a subframe move may prove impossible when you sit too near another edit point, a marker, or the playhead; here, pressing the N key to switch snapping off clears the trouble.

### Eliminating Subframe Audio Edits
