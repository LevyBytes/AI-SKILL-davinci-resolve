# The Fairlight Inspector (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### The Fairlight Inspector

Every clip in the Timeline and Media Pool, plus each audio track or bus, carries settings and properties you can tweak, animate, and edit from the Fairlight Inspector. With it, jobs become straightforward, like aligning the levels or EQ across several clips while keeping the track level free for your full mix, or tuning levels and audio effect parameters on tracks and busses. Keep in mind that clip-based effects are not the same as real-time track and bus effects, since they touch only single clips sitting on the Timeline or in the Media Pool instead of every clip on a track. The pages that follow explain how to operate these controls inside the Fairlight Inspector.

### Clip Mode vs. Track Mode

To clear up any doubt over whether your parameter changes in the Audio tab land on an audio clip or a track, the Inspector carries a Clip Mode and a Track Mode button. (Left) the Clip mode (circled); (Right) the Track mode (circled)

- Pick an audio clip in the Media Pool or on the Timeline and the Clip Mode button lights up, with that clip’s name shown at the top of the Inspector just right of the Track Mode button. Should you pick a Media Pool clip, the words “Media Pool “ precede the clip name up top in the Inspector. Pick a timeline clip and only its name shows.

Up top in the Inspector, the words “Media Pool “ sit ahead of the clip name

- Click the Track Mode button while a Timeline clip is chosen and any edits you then make in the Audio tab go to that clip’s matching Mixer channel, with the clip name up top in the Inspector swapping over to the track name.
- Clicking a track header likewise flips on track mode. Either way, the clip name shown up top in the Inspector becomes the track name.

### Common Controls

Pick an audio clip, an audio track, or a bus channel strip in the Mixer and the Audio and Effects panels reveal a set of shared audio-specific parameters and controls.

Closed and open Inspector group controls in the Fairlight page

Among these controls are:

- Enable button: Sitting to the left of a parameter group’s name, this toggle lets you switch off then back on every parameter in that group together. Orange signals that track is on; gray means off.
- Parameter group title bar: A double-click on any parameter group’s title bar collapses or opens it. Better still, Option-double-clicking one group’s title bar collapses or opens all parameter groups together.
- Keyframe and Next/Previous Keyframe buttons: With this button you place or remove keyframes at the playhead position across every parameter in the group. An orange highlight means a keyframe sits at the playhead’s current spot; dark gray means none does. The left and right arrow buttons hop the playhead between keyframes for more tweaking.
- Reset button: Returns all parameters in that group to their default settings.

TIP: For “granular” moves on the virtual sliders, hold the Option or Shift key as you click into the numerical value field and drag it left or right.

### The Audio Tab

### Clip Mode

While you handle audio clips (Clip mode) on the Audio Timeline or in the Media Pool, the Audio tab supplies the controls and audio effects covered below. NOTE: You cannot edit parameters in the Inspector for audio clips that live on locked tracks.

To read more about locking audio tracks, turn to Chapter 175, “Editing Basics in the Fairlight Page.” Volume The Volume control is what sets the gain of a given clip.

### Volume control in the Inspector

### Pan

Use this control to pan a chosen clip. Although most professional mixes keep panning to the beefier panner in the Fairlight page Mixer, this basic clip-level Pan control helps picture editors in the Edit page whip up simple panning effects to support a craft edit. Drag the slider to pan audio from left to right. By default this control rests centered at 0.

### Pan control in the Inspector

Voice Isolation (Studio Version Only) Switch this control on and Voice Isolation is applied.

### Voice Isolation control in the Inspector

To read more about Voice Isolation, turn to Chapter 181, “Fairlight FX.” Dialogue Leveler Every audio clip on the Timeline or in the Media Pool carries Dialogue Leveler controls for applying that effect to the clip.

### Dialogue Leveler controls in the Inspector

To read more about Dialogue Leveler, turn to Chapter 181, “Fairlight FX.”

### Pitch

With the Pitch control you shift a clip’s pitch while its speed stays put. A pair of sliders adjusts clip pitch in Semi Tones (coarse moves, a twelfth of an octave) and Cents (fine moves, 100th of a semi tone).

### Pitch control in the Inspector

### Speed Change

Use the Speed Change control to alter how fast the clip runs. It offers the choice of letting the clip’s pitch track the new speed change or holding onto the original speed’s pitch.

### Speed Change control in the Inspector

These are the overall controls in the Speed Change window:

- Enable button: Flips the whole Speed Change effect off and on

without clearing the controls.

- Reset button: Restores every control of the Speed Change window to its default.
- Direction: The Right Arrow keeps the waveform running forward, the Left Arrow

flips the waveform’s direction, and the Snowflake icon makes a freeze frame.

- Speed %: A flywheel control that shifts the speed by a percentage of plus or minus 100%.
- Frames Per Second: A flywheel control linked to the Speed % control that displays the

FPS in relation to the speed change.

- Duration: Shows the clip’s revised timing.
- Ripple Sequence: Tick this and every bit of media past the action ripple-edits over to

the new duration.

- Pitch Correction: Tick this and the clips keep their original pitch through the

speed change. Leave it unticked and the audio speeds up or slows down along with the speed move. A slower speed change drops the pitch; a faster one raises it.

NOTE: Inside the Speed Change controls, steer clear of the freeze frame option, as it will harm the chosen audio file.

### Parametric Equalizer

Offering graphical as well as numeric controls, this four-band equalizer boosts or cuts assorted frequency ranges inside a clip even before that signal reaches the EQ built into the Mixer. Every band carries controls covering its filter type (Bell, Lo-Shelf, Hi-Shelf, Notch), plus Frequency, Gain, and a Q-factor (the band’s sharpness); which controls a band offers shift according to its filter type. Switch on a channel strip’s EQ and the Mixer shows the equalization curve in force. Because a channel strip’s EQ settings hit every clip on that track, you have to open the EQ window to make those changes.

### The channel strip’s EQ indicator

Master EQ Controls Up in the top right and left corners, the Equalizer window holds these overall controls.

- Enable button: Flips the whole EQ effect off and on, leaving the controls as they were.
- Reset button: Returns every control of the EQ window to its default.

### EQ Graph

Here the present EQ curve appears, fitted with handles tied to each active EQ band listed beneath. Drag any numbered handle to boost or cut the frequency range that band rules, applying whichever equalization type that band has been assigned.

### The EQ graph with user-draggable handles

When you drag the numbered handles on this graph, the matching band’s parameters change, and reshaping a band’s parameters likewise reshapes the EQ graph, which doubles as a visual picture of the equalization being put on that track. Bands 1 and 4 The pair of outer band control sets handle high-pass and low-pass moves when you need them.

- Band enable button: Switches each EQ band on and off.
- Band filter type: For Bands 1 and 4 you can pick among six particular filtering options

aimed at the signal’s lowest or highest frequencies. Running top to bottom these are: Hi-Shelf, Hi-Pass, Bell, Notch, Lo-Pass, and Lo-Shelf. For Bands 2 and 3 the picks are Lo-Shelf, Bell, Notch, and Hi-Shelf.

- Freq: Sets where the center frequency of the EQ move sits.
- Gain: Sets how strongly the targeted frequencies are hit. Negative figures cut those frequencies, while positive figures lift them.

Bands 2 and 3 The pair of middle band control sets let you perform a broad assortment of equalization moves.

- Band enable button: Switches each EQ band on and off.
- Band filter type: For Bands 2–5 you can pick among four distinct filtering options, running top

to bottom: Lo-Shelf, Bell, Notch, and Hi-Shelf.

- Frequency: Sets where the center frequency of the EQ move sits.
- Gain: Sets how strongly the targeted frequencies are hit. Negative figures

cut those frequencies, while positive figures lift them.

- Q Factor: Sets the span of frequencies affected. Smaller figures take in a broader band of

frequencies; larger figures take in a narrower one.

NOTE: It may go without saying, but not every parameter exists for every curve type. A Bell curve filter, say, has Frequency, Gain, and Q adjustments, yet a Lo-Pass or Hi‑Pass filter leaves only Frequency open to adjust.

### Track Mode

As you work with audio tracks or busses (Track mode), the Audio tab lets you set the volume level plus switch on and tune Fairlight Track FX. To read more about Fairlight Track FX, turn to Chapter 181, “Fairlight FX.”

### Audio tab - Track mode

NOTE: You cannot edit parameters in the Inspector for locked tracks. To read more about locking audio tracks, turn to Chapter 175, “Editing Basics in the Fairlight Page.”

### The Effects Tab

This tab shows the Audio Effects you have placed on a track or bus through the Effects section of its Mixer channel strip, or onto a timeline clip out of the Effects Library.

### Fairlight FX Delay controls in the Effects tab

### For more information, see Chapter 180, “Audio Effects.”

### The Transition Tab

Should you have placed any Transitions (Crossfade) between clips on either the Edit or Fairlight pages, the Transition tab lets you adjust them; open it by double-clicking a Crossfade transition.

Crossfade controls in the Transition tab of the Inspector

These properties are open to editing:

- Transition Type: Whichever transition is presently chosen. Swap it for any other installed transition by picking one from the dropdown menu.
- Duration: How long the transition lasts, given in both seconds and frames.
- Alignment: A dropdown for setting where the transition lands in relation to the edit

point it is applied to. The picks are “Start on Edit,” “Center on Edit,” and “End on Edit.”

- Fade In: This dropdown lets you pick from -3dB to 3dB.
- Fade Out: This dropdown lets you pick from -3dB to 3dB.

To read more about adjusting crossfades, turn to Chapter 175, “Editing Basics in the Fairlight Page.”

### The File Tab

Across its various sections, the File tab lets you inspect or change how audio clips on the Timeline and in the Media Pool are set up and what properties they hold.

### File Information

Beyond the audio clip’s name, this part of the File tab supplies more details about the file, as the screenshot below shows.

### File tab - File Information section

### Metadata

Every text field, save for the embedded Timecode field, accepts whatever information you choose to type in.

### File tab - File Metadata section

### Auto Select Next Unsorted Clip

With this box ticked, hitting the Return key once you have filled a metadata field jumps to the next Media Pool clip while leaving the cursor in that same field. That makes for fast back-to-back metadata entry without clicking the Next Clip button or hand-selecting whichever Media Pool clip comes next. Auto Select Next Unsorted Clip checkbox and Next Clip button Any time a Media Pool clip is chosen, the name shown to the right of the Clip and Track and Mode buttons opens with “Media Pool – “.

### File tab - Media Pool clip selected

### Audio Configuration

This part of the File tab carries features and controls for changing an audio clip’s channel properties in a natural way. What you change here sets how many channels in the clip stay active and fixes each one’s source and volume level as the clip drops into the Timeline. How the Audio Configuration pane looks shifts with the format of the clip you are trimming. The screenshots below, for instance, show a 6-channel clip in the Media Pool under two distinct channel formats.

6-channel adaptive - Media Pool clip

### 6-channel mono - Media Pool clip

- Format: Pick an audio clip in the Media Pool and the Format dropdown shows its current channel format, the standard channel configurations, and a Custom option. You can hand the clip any of these channel configurations without going through Clip Attributes to customize it.

Format dropdown menu - for a 6-channel adaptive clip Pick a timeline clip instead and the Format dropdown shows its current channel format together with the Custom option. That timeline clip, though, is built from two mono channels, and you can swap the audio source on each channel. Picking the Custom option brings up the Audio tab of the Clip Attributes dialog.

To read more about working with the Clip Attributes dialog, turn to Chapter 22, “Modifying Clips and Clip Attributes.”

- Waveforms: With a Media Pool clip, the topmost waveform under the Format dropdown shows a composite of every channel in the audio file. The waveforms below it stand for the audio in each individual channel of the clip.

That composite waveform is missing when you work with timeline clips. Listen to the audio by skimming it under your mouse cursor, by clicking the Play button in the transport control beneath the last waveform, or by tapping the spacebar. Click anywhere inside any waveform and playback carries on from that spot. The Transport Controls section further down covers this idea in more depth.

- Channel Controls: With source clips in the Media Pool, each clip channel gets its own Enable/Disable checkbox and Mute button.
- Active/Inactive: Tick the checkbox to enable a channel, putting it in play and open to editing operations. Leave the checkbox empty and editing operations skip that channel, as though it were gone from the clip. Take a 6-channel mono clip in the Media Pool: switch channel 2 off and only five tracks (1, 3, 4, 5, and 6) come along when you drag it from the Media Pool to the Timeline.

### 6 mono channel Media Pool clip

- Mute: Click this button to silence the channel while it stays put inside the clip. So with the six-channel Media Pool clip, if you ticked the checkbox for channel two and then hit the Mute button, all six channels still travel when the clip is dragged onto the Timeline, yet only channels 1, 3, 4, 5, and 6 can be heard.

TIP: Option-clicking a Mute button or an Active/Inactive checkbox flips all the others to the opposite state, which effectively solos the channel you are touching.

- Channel Source: For multichannel clips made entirely of mono channels, the Audio Configuration pane adds a dropdown showing each waveform’s current audio source by name. Click that dropdown to pick from a roster of mono audio sources. It helps when, for example, you must reroute a person’s lavalier mic signal to a different one, or the boom mic channel got bumped during a take and now carries loud noise that needs swapping to another source.

### Audio Channel Source menu

Changing the Channel Source on the Timeline To swap an audio source on the Timeline, right-click the audio channel that needs fixing and pick an option from the foot of the contextual menu.

### Audio Channel Source menu - Timeline menu

For faster access to these options, Command right-click the audio channel in question.

### Audio Channel Source menu - Simplified Timeline menu

- Transport Controls: After you have begun playback with the Play button, clicking anywhere inside a waveform “solos” that channel and keeps the audio playing on from that spot. With a Media Pool clip, clicking anywhere inside the composite waveform plays the blend of enabled, unmuted channels starting there. With a timeline clip, return to hearing every channel by clicking the Stop button and then the Play button.
- Level: This control wakes up once you have selected one or more channels and serves to trim the level of individual channels in multichannel Media Pool or timeline clips. It comes in handy when a channel or two sits too quiet and must be trimmed up to match the rest. Trim moves you make inside timeline clips stand apart from their clip gain and leave the matching Media Pool clip untouched.

TIP: Command-clicking or Shift-clicking to grab several channels lets you trim every channel in that group at once. Bear in mind, though, that all of them get trimmed by the very same amount (in dB).

### Adjusting Multiple Clips in the File Tab

You may pick several audio clips and adjust their properties together in the Audio Configuration pane. As one example, you can grab a batch of audio files and strip Track 2 from every one of them in a single move. A few things bear noting, though:

- Within a multi-clip selection, only the clip you picked last shows up in the track layout of the Audio Configuration Pane. The top composite waveform, however, takes the name “Multiple Clips” to signal that you have more than one clip selected.
- Whatever you adjust, such as muting or enabling/disabling a track, hits every selected clip together.

### Timecode

This pane holds controls that Clip Attributes in the Media Pool once took care of (that route still works too). With them you can override the timecode details for one or several clips in the Media Pool.

### File tab – Timecode section

- Current Frame: Here is where you give a fresh time to the timecode at the clip’s currently viewed frame.
- Slate: When source media arrives from a shoot that used a timecode slate on set, you can set the slate timecode as a second timecode track for assorted operations, all without disturbing the clip’s primary timecode, which might already be serving program sync.
- To enter the right Slate timecode, choose a Media Pool clip showing a visible timecode slate and park the playhead on a frame where the slate’s timecode reads clearly. Next, open the Timecode panel of the Clip Attributes window and key the timecode value you read in the picture into the Slate Timecode field.
- Offset Source: When a whole batch of clips merely has its timecode shifted, you can fix the timecode offset across as many selected clips as you wish.

### Adjusting Multiple Clips Simultaneously

A simple route exists for tweaking the Inspector parameters of many clips at once, with no need for Paste Attributes (covered later here). Just select every clip you mean to change at the same time, then adjust the parameter you want in the Inspector. The upshot is that each selected clip shifts by the same amount. It works for compositing effects, transforms, text parameters, filters, and audio settings, pretty much anything that can be shown in the Inspector for several selected clips together. Select multiple clips and the Inspector reads “Multiple Clips” as its title. Where the selected clips hold differing values in the parameter you are adjusting, that parameter shows two dashes in its value field. Two routes let you adjust multiple clips:

- To make a relative change across all selected clips while their original offsets from one another stay intact, drag the virtual slider in the parameter field, which shows a + or – ahead of however many units your change spans.

If instead you want every selected clip set to one identical value, double-click the number field, type the value, and press Return.

Applying a relative plus 4.00 shift to the Volume level across every selected clip

### Animated Inspector Adjustments

Key-framing on the Edit page behaves a touch differently from using the Keyframe Editor on the Color page. You can handle most basic key-framing right in the Inspector through three buttons that sit to the right of any parameter able to be keyframed. An animated effect needs at least two keyframes.

Shown in the Inspector are three keyframe controls, reading left to right: Previous keyframe, Create/ Delete keyframe, Next keyframe Ways to key-frame parameters from the Inspector:

- To add a keyframe: Pick a clip, open the Inspector, slide the Timeline playhead to the frame where the keyframe should go, then click the Keyframe button beside the Inspector parameter you wish to animate. After a parameter holds at least one keyframe, every further change you make to Inspector parameters, or with the onscreen Transform/Crop controls in the Timeline Viewer, drops new keyframes on its own whenever the playhead sits on a different frame.
- To move the playhead to the next or previous keyframe: Click the little left or right arrow on either flank of a parameter’s keyframe control to send the playhead to the neighboring keyframe. The Right-Bracket ( [ ) and Left-Bracket ( ] ) keys also step you keyframe to keyframe.
- To edit an existing keyframe of a parameter: Park the playhead right on the keyframe you mean to edit, then change that parameter, whether in the Inspector or through the Timeline Viewer’s onscreen controls.

Methods of changing keyframe interpolation in the Inspector:

- To change a keyframe to Ease In or Ease Out: Eased keyframes make animated changes that start gently and build to full speed, or wind down gradually to a halt. This applies only once two or more keyframes are forming an animated effect. With the next/previous keyframe controls, bring the playhead onto a frame that holds a keyframe; right-click its orange keyframe button, then pick Ease In, Ease Out, or Ease In and Out, depending on the keyframe you are editing and the effect you are after.
- To change a keyframe to Linear: With the next/ previous keyframe controls, bring the playhead onto a frame that holds a keyframe; right-click its orange keyframe button, then pick Linear.

Methods of deleting keyframes and disabling keyframed effects:

- To delete a single keyframe: Open the Inspector, send the Timeline playhead to a frame holding a keyframe, and click the orange Keyframe button in the Inspector to remove it.
- To delete all keyframes for one parameter: In the Inspector, click the reset button on the right of that parameter’s keyframe control.
- To delete every keyframe across a whole parameter group from within the Inspector: Click the reset button sitting on the right of that parameter group’s title bar.
- To disable or enable a single parameter’s keyframed effect: On the Timeline, click the toggle control at the left edge of a parameter’s keyframe track. Orange signals that track is on; gray means off.
- To disable or enable a group of parameters in the Inspector: Within the Inspector, click the toggle control sitting at the left edge of that parameter group’s title bar. Orange signals that group is on; gray means off.

### Paste and Remove Attributes

On the Fairlight page you will find Paste Attributes and Remove Attributes commands for copying and clearing audio Inspector parameters and effects, mirroring the matching commands over on the Edit page.
