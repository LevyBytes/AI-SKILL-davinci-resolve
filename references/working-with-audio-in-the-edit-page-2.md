# Working With Audio In The Edit Page (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Should you be sitting on an assortment of subframe edits that you want cleared away, the route is Timeline > Trim Audio Edits to Frame Boundaries. That snaps every edit along the timeline onto frame boundaries for whichever clips were cut to subframe precision. A clip running past the nearest frame gets pulled back, while a clip whose start or end falls near a frame boundary — and which still has extra material to spare — gets stretched out to meet that nearest frame boundary.

### Record Voiceover Tool

Come DaVinci Resolve 20, the Cut page and the Edit page alike can lay voiceovers straight onto a timeline track through a pared-down interface. When the job is serious, exacting ADR, Fairlight’s ADR toolset is the better fit, but for plain VO and scratch tracks the Record Voiceover tool is fast and handy.

### The Record Voiceover tool

You bring up the Record Voiceover tool by choosing Timeline > Record Voiceover, or by clicking the Voiceover icon (that little microphone) on the Timeline Toolbar. To Record Voiceover 1 File Name: Key in a meaningful file name for the new Voiceover file, or simply leave the default. 2 Audio Input: Point this at whichever audio interface on your computer holds your microphone. 3 Record Track: Name the timeline audio track your voiceover should land on. Alternatively pick Auto and let DaVinci Resolve decide from your current track layout. After that, set the playhead on the timeline at the spot the audio should begin. 4 Press the Record Icon to begin laying the recording straight onto the track. 5 Press the Record Icon a second time to halt it. As soon as recording stops, the playhead jumps back on its own to where it started, so you can either play the voiceover clip back in place or fire off a fresh take at once by clicking the Record Icon again. That fresh take overwrites the earlier clip on the track automatically. Every earlier take, however, remains on hand in the Media Pool.

Further options live in the Voiceover Tool’s 3-dot option menu. Input Monitoring: Switch this on and the microphone audio plays back as it records, though with a touch of lag. It gives the voiceover artist, or the audio engineer, a way to hear the audio as it is captured. Turning it on also brings a Mic Monitor Level slider into the main Voiceover tool, by which you govern how loud that playback sits in the headphones. Enable 3 Seconds Countdown: Switch this on and a silent three-second countdown shows in the timeline viewer ahead of recording, granting your talent a moment to ready themselves to speak. No audio beep accompanies this countdown — it is purely a visual cue. Mute Timeline Audio While Recording: Choose this and every audio track on the timeline is muted as you record, sparing you any other distracting sounds. To silence only some of the tracks, do it by hand with the mute buttons in the audio track timeline header. Stereo Input: Choose this and, with a stereo microphone in use, the capture goes to a stereo track rather than mono. Hide Options: Choose this and the File Name, Audio Input, and Record Track fields drop out of the Voiceover Tool, leaving just the Record icon to toggle. It comes in handy when you would rather your voiceover talent not stumble into your settings.

### Audio Settings in the Inspector

Every clip and every track carries a handful of audio-related parameters within the Inspector’s Audio panel. For finer detail on these controls, turn to Chapter 37, “Using the Inspector in the Edit Page.”

### Setting Volume

Every audio clip — or audio item, where a clip’s linked audio spans several tracks — holds its own Volume level. The upshot is that a multi-channel audio clip draws on one shared Volume setting. A few easy methods exist for adjusting these levels.

### Adjusting Audio in the Inspector

With one or more audio clips selected, each clip exposes its own Volume parameters in the Inspector’s Audio panel. Pick a single audio clip in the Timeline and tweak its volume and only that clip changes, which is how you set baseline levels for individual clips across your program. The Volume control acts on every channel inside that clip at the same moment.

The Volume parameter offered for audio clips within the Inspector Select several Timeline clips at once and dragging the Volume sliders or virtual sliders for the whole group applies a relative shift to them all, holding their offsets from one another intact. Should you instead want every clip brought to one level, a numeric adjustment drops all the selected clips to the same absolute level.

### Adjusting Audio in the Timeline

Every clip (or item) of audio on the Timeline wears a Volume overlay, and by dragging it up or down with the pointer you set that clip’s level. Hold the Shift key as you drag for more delicate moves. An Option-click on the level drops a keyframe right there so levels can shift dynamically. This overlay maps to the Inspector’s Volume parameter.

Dragging a Volume overlay to set the clip level Alternatively, click the Curve Editor button down in the audio clip’s bottom right-hand corner, which brings up the Audio Curve Editor. As of this writing, volume and pan are the only parameters this Curve Editor lets you edit.

### Showing the Volume overlay in the Curve Editor

### Adjusting Volume Using Keyboard Shortcuts

Keyboard shortcuts give you yet another way to set the volume of selected clips, and they work even as the Timeline plays. You can rig this up in a handful of ways.

- To adjust just one clip: Highlight it, then issue one of the volume-change commands.
- To adjust any clip at the position of the playhead: Switch on Timeline > Selection Follows Playhead

so that whatever clip the playhead crosses becomes the selected one, then issue a volume-change command. Where several clips meet the playhead, the chosen clip is the one riding the highest track.

- To adjust multiple clips all together: Highlight every clip you mean to change in one go, then issue a volume-change command. Where the clips you picked carry unequal Volume levels, those gaps are kept intact as you adjust.

Here are the commands that change volume. To move volume in steps of 1dB, do one of these:

- Clip > Audio > Increase Audio Level 1dB (Option-Command-Equals)
- Clip > Audio > Decrease Audio Level 1dB (Option-Command-Minus)

To move volume in steps of 3dB, do one of these:

- Clip > Audio > Increase Audio Level 3dB (Option-Shift-Equals)
- Clip > Audio > Decrease Audio Level 3dB (Option-Shift-Minus)

### Normalize Audio Volume Command

What the Normalize Audio Levels command does is drive clip levels automatically toward a stated target, and you get to pick the method by which each audio clip’s levels are analyzed to decide how its volume should be normalized. Among the choices are a range of loudness normalization algorithms keyed to assorted international standards, handy for evening out the perceived overall loudness of several clips against one another no matter the transient levels running through each. Peak normalization is also on the table, with both Sample Peak and True Peak on offer. The loudness choices set out to judge an audio signal by how loud it seems to the listener, which yields a truer automatic balancing of one clip’s audio levels against another’s, regardless of transient peaks cropping up here and there. For gauging maximum “true peak,” the target peak meter now follows the BS.1774 standard, meaning it can read “inter-sample peaks” instead of just the peaks at each waveform sample. You can still opt for Sample Peak, though — the older approach that measures the literal peak of the samples within a media file. Because the Normalize Audio Volume command only shifts volume and lays on no dynamics, the outcome is that the loudest stretches of each selected clip line up with one another at the target level. This command turns up on the Fairlight page as well.

To normalize one or more chosen audio clips: 1 Right-click any of the selected clips and pick Normalize Audio Levels. Up comes the Normalize Audio Level dialog.

The Normalize Dialog on the Edit page 2 Settle on the Normalization Mode you intend to use. The field is open to a range of standardized loudness measurement algorithms, plus Sample Peak and True Peak. 3 Settle on the reference level you want the selected clips’ peak volume to meet. 4 Decide how the level of several selected clips gets set: With Set Level on Relative, every selected clip is handled as though it were a single clip, so the loudest peak across them all sets the adjustment and each clip’s volume shifts by that same amount. This suits a run of clips — a dialog recording, say — whose levels already agree and which you wish to normalize as a group. With Set Level on Independent, each clip’s own peak level dictates that clip’s adjustment, so every selected clip moves by an amount peculiar to itself. The upshot can be a spread of wildly different volume shifts meant to bring each audio clip’s peak levels into line. This suits cases like balancing a batch of disparate sound effects whose starting levels are all over the map. For more on loudness normalization, turn to Chapter 182, “Audio Meters and Audio Monitoring.”

### Keyframing Audio

Audio can be keyframed two ways on the Edit page. One is each audio clip’s volume curve in the Timeline; the other is the Inspector’s keyframe controls, with which an individual clip’s Volume parameter gets animated the same way any other clip attribute would be — easing the level upward or downward, panning side to side from left, or dynamically reworking any of a whole host of filter controls, right down to subframe increments where the need arises. For more on keyframing within the Inspector, turn to Chapter 53, “Keyframing Effects in the Edit Page.” Whatever keyframes you lay down with the Inspector’s Keyframe controls show up automatically on that audio clip’s volume curve in the Timeline.

### Overlay Controls for Volume

Every audio clip on the Timeline carries a Volume overlay control sitting atop it, one that begins perfectly flat by default. As with comparable controls in other applications, this level curve lets you reshape a clip’s levels — either wholesale or dynamically by way of keyframes.

Volume curves shaping the level of a clip’s audio on the Timeline Beyond that, clicking a clip’s Audio Curve Editor button, tucked into the bottom right-hand corner of each audio clip, opens an audio-specific Curve Editor where volume can likewise be keyframed.

The button for opening an audio clip’s Curve Editor

### How to Add and Adjust Volume Keyframes

Mixing audio by placing and tweaking individual keyframes can be a quick, effective route to balancing clip levels against each other, ironing out level trouble inside a single clip, or even building modest mixes (though the Fairlight page’s mixing power runs far deeper). Whenever you edit any audio parameter curve by hand, the procedures below apply. Ways to place or select audio keyframes with the pointer:

- To add keyframes to the Volume curve: With the Option key held, click the curve to drop a keyframe at that frame. At least two keyframes are required before any automated Volume change can occur.
- To select one or more keyframes: A click on any keyframe selects it.
- To select multiple discontiguous keyframes: Command-click every keyframe you want, whether or not they sit side by side.
- To select multiple contiguous keyframes: Click the first keyframe in the run, then shift-click the last one, and everything between them is selected too.

Ways to adjust keyframes in the Volume overlay (or curve) with the pointer:

- To adjust any curve segment: For a clip with no keyframes, rest the pointer over the segment as a whole; otherwise rest it between any two keyframes, squarely on the stretch of curve you mean to raise or lower. Once the Move cursor shows, drag upward to lift the volume or downward to cut it.
- To adjust a keyframe in any direction: Bring the pointer onto a keyframe until the fourway cursor surfaces, then drag up or down to alter the volume, or side to side to alter its timing. Audio keyframe timing can be set in subframe increments for precision mixing.
- To adjust a keyframe in only one direction: Bring the pointer onto a keyframe until the fourway cursor surfaces, hold Shift, and drag along the direction you intend — vertically to change that frame’s clip volume, or horizontally to slide the keyframe to a fresh point in time. The moment you begin dragging a keyframe one way, its movement stays locked to that axis until you let go. Audio keyframe timing can be set in subframe increments for precision mixing.
- To turn a Linear keyframe (or several) into Ease In or Ease Out: An eased keyframe makes animated changes that start off slowly and build to full speed, or wind down gradually to a halt. This only takes effect once two or more keyframes form an animated effect. Highlight one or more keyframes, then right-click one of them and pick Ease In, Ease Out, or Ease In and Out, according to which keyframe you are editing and the effect you are after.
- To revert an eased keyframe (or several) back to Linear: Highlight one or more keyframes, then right-click one of them and pick Linear.

Methods of Cutting, Copying, Pasting, and Deleting keyframes:

- To cut or copy, and paste one or more keyframes: Highlight the keyframes, then hit the Cut (Command-X) or Copy (Command-C) shortcut. Next, park the playhead where the first copied keyframe should begin and hit Paste (Command-V).
- To delete one or more control points from a curve: Highlight the keyframe(s) you intend to remove and hit Backspace.

### Audio Fade Handles

Rest the pointer squarely over an audio clip and a pair of Audio Fade handles surface at the In and Out points. Drag either handle in toward the middle of the clip and you fade the clip volume up at its head and fade it down at its tail.

Audio Fade handles at either end of an audio clip

NOTE: Bringing in a Final Cut Pro X project carries each clip’s fade handles across automatically too. Where a precise transition calls for it, Audio Fade Handles can also be set in subframe increments.

Tuning an Audio Fade handle by subframe increments, viewed inside the shadow cast by a single frame of the playhead

Adjusting the curve of the fade Both the Edit and Fairlight pages let you build and refine fade effects.

With a fade effect in place, you reshape its curve by dragging the handle perched right over the fader curve. Drag that handle up or down to change the curve’s angle, and drag it left or right to change the curve’s shape. By this means, every sort of fade effect is within reach.

### Audio Crossfades

Pick an edit point that holds both video and audio, with Linked Selection on so the video and audio edit points are both caught, and applying a video transition to that edit drops a crossfade onto the audio as well. Cross Fade transitions can be added to any edit point between two audio clips bearing enough handles, much as video transitions are added — drag one out of the Effects Library and drop it, right-click an edit to pick an option from its contextual menu, or highlight an audio edit point and reach for Timeline > Add Audio Only Transition (Shift-T). A Cross Fade transition is a fast, painless way to ease the outgoing clip’s volume down while the incoming clip’s volume climbs up at the same time, giving you a smooth aural handoff between the two audio clips. For precision work, a crossfade’s start and end points can be edited in sub-frame increments.

An audio Cross Fade transition applied between two clips

Double-click a Cross Fade transition to load it into the Inspector, which lays bare these parameters:

- Duration: How long the transition runs, given in both seconds and frames.
- Alignment: A drop-down for choosing where the transition sits relative to the edit point it is

attached to. The options are “End on Edit,” “Center on Edit,” and “Begin on Edit.”

- Transition style: Pick –3dB, 0dB, or +3dB to lock the Fade In and Fade Out levels

both to a single value. To grasp what these levels signify, see the parameter just below.

- Fade In/Fade Out levels: Three options act on the incoming and outgoing halves of

the Cross Fade effect on their own. 0dB lays on a linear fade (the default). +3dB lays on a boosted curve; applied to both Fade In and Fade Out, it can make up for sagging levels in the heart of a Cross Fade. –3dB lays on an attenuating curve that intentionally drops the Cross Fade’s level. Crossfades can be built and refined on both the Edit and Fairlight pages. TIP: For an asymmetrical crossfade, you “checkerboard” clips across two tracks with overlapping handles at head and tail, then work the Fader handles to dial in precisely the timing and curves the effect demands.

### Voice Isolation (Studio Version Only)

Voice Isolation draws on an AI model trained across every sort of human voice — male or female, young or old — which lets you strip loud, unwanted sounds out of existing voice recordings to striking effect. Background noise of all kinds can be banished, from air conditioners and fans to jackhammers, restaurant clatter, music bleeding under a featured line of dialogue, and beyond. The Amount control balances the blend between the untouched source and the isolated voice. Set to 50, that blend sits roughly even. Settings from 70 to 80 tend to give natural results while still isolating the source hard. Voice Isolation will run on an audio track in real time, yet it will not work on live audio input. Any mono, stereo, or dual-mono audio track can take it, but tracks carrying more than two channels are not supported.

### The Voice Isolation plugin

### Dialogue Leveler

The Dialogue Leveler studies the source material to spot dialogue, then “rides down” the louder stretches, “lifts up” the softer ones, and pulls down background sounds that are not dialogue. It manages this free of the usual “pumping” and other unwanted artifacts of dynamics processors (compression/limiting), turning out results on par with painstaking, by-hand clip gain moves or “riding” the track via fader automation.

### The Dialogue Leveler plugin

Time and again the Dialogue Leveler can “fix and mix” a recording cut with one boom mic — where a character stands nearer than the others or swings away from the mic — evening it out so the original relative dynamics survive even as intelligibility and average level rise. The Dialogue Leveler will run on an audio track in real time, yet it will not work on live audio input. Any mono, stereo, or dual-mono audio track can take it, but tracks carrying more than two channels are not supported. Dialogue Leveler controls:

- Dialogue Leveler: Enables or disables the plugin.
- Waveform Processing display: Here a scrolling waveform plays out, with a gray line marking Dialogue Leveler processing. That display is absent, though, when you reach for the Dialogue Leveler in the Inspector to treat audio clips on the timeline.
- Preset Menu: The options this menu hands you are:

Allow wider dynamics: The default, and the right pick for audio whose dynamic ranges widely from loud to soft and whose clip levels run medium to high. More lift for low levels: Reach for this when the source holds more low-level dialogue you wish to lift. Lift soft whispery sources: Reach for this when the source carries whispered dialogue alongside background noise. Optimize moderate levels: Reach for this when the source sits at medium levels from end to end.

- Reduce Loud Dialogue: Switched on, louder dialogue gets ridden down whenever it peaks, behaving like a “perfect limiter” that asks no fiddling with threshold or time parameters. Thanks to the “near real-time” design, the analysis runs ahead of audible playback so the results come out at their best.
- Lift Soft Dialogue: This control hunts out low-level dialogue and raises it, smoothing material that is quieter and more uneven in level. Since the work centers on dialogue, it rarely lifts background sounds unless they happen to sound at the very same moment as the dialogue.

Of the three, the Lift Soft Dialogue option is frequently the handiest, since it brings quieter lines of dialogue up and renders them naturally smooth while leaving background noise unboosted.

- Background Reduction: Working off whichever internal preset is chosen in the Preset menu, this option eases background noise away gently.
- Output Gain: With this control you set the output level, either by clicking and dragging it or by typing a figure into the numeric field. The Output Gain control spans 0.0 to +6.0 dB.

TIP: Ahead of running the Dialogue Leveler on a track, it pays to establish an ideal baseline level for the default “Allow wider dynamics” preset by normalizing the audio first.

For more on normalizing audio, turn to Chapter 176, “The Fairlight Inspector.”

### Music Remixer (Studio Version Only)

Built on the DaVinci Neural Engine, this AI plugin breaks music apart into separate stems — Vocals, Drums, Bass, Guitar, and “Other” (“everything else”) — so you can creatively rebalance or remix the track. The level controls let you set each stem’s volume, while the Mute buttons pull stems out of your mix or bring them back. You might, for one, drop or duck a vocal because it fights with a featured line of dialogue.

### The Music Remixer plugin

### Music Editor (Studio Version Only)

DaVinci Resolve 20 can lengthen or trim music to match your edit without any visible seams. You will find the new AI-driven Music Editor under the inspector’s audio tab. Type in the duration you want and hit the Adjust button to grow or shrink the clip to that length. NOTE: The Music Editor is an “intelligent edit” that performs well on beat-driven music (pop, dance, and so on). It is not meant for free-form, ambient, or non-beat material. Rather than relying on time compression/expansion or any pitch change, the Music Editor borrows the moves a human music editor would, cutting the material to fit the length your picture needs. It hunts for sensible spots to place transitions according to whether you are lengthening (by repeating sections) or cutting material, and tries to use the original composition’s ending or fade when the timing lines up. Should the ending land abruptly, building a fade out is left to you.

### The Music Editor in the Audio Inspector
