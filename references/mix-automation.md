# Mix Automation (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Mix Automation

For mixing audio, the Fairlight page offers automation that is uncomplicated, adaptable, and capable. You can build automation data by drawing the changes graphically, or by capturing the movement of onscreen mixer or effects controls as you operate them with a mouse or a Fairlight control surface. There's even the option to generate panning automation from how on-screen people or objects move within the Fairlight Viewer. After it's recorded, automation for any kind of mix parameter—faders, sends, panning, or effects—plays back in flawless sync with both the audio and the video. The focus of this chapter is automation mixing driven by the combined controls of the on-screen mixer and the timeline.

To learn more about the fundamentals of mixing, refer to Chapter 177, "Mixing in the Fairlight Page."

### Creating Mix Automation

A full set of tools for building and editing mix automation ships with the Fairlight page. You're able to draw the automation data, capture mix changes by operating on-screen controls, or call on IntelliTrack-powered Audio Panning to Video, which generates panning automation from how people or objects move within the Fairlight Viewer. And yes, this really is "a thing."

### Why Use Track Automation?

As a video editor, you might be more accustomed to reaching for clip-based automation when altering your audio mix, yet that route carries limitations. There are occasions where you'll want to apply global changes to a track across the timeline, or to tweak groups of tracks together see Chapter 179, "Track Groups." With time-based effects such as reverb or a recurring delay, you might want to dynamically tune the level of the "trails" as a track develops. As an example, you might have a scene shifting perspective from a wider space into a tighter one, where the room ambience or the dialogue's tonal character must evolve over time as the characters travel through the scene. That's exactly where track automation techniques (drawing or recording control movement) become powerful and a source of creative inspiration.

### What Can Be Automated

Almost every control on a Mixer channel strip can have automation recorded for it, the fader, sends, mute, and panning included. Plugin parameters for audio can be automated too.

### Audio Panning to Video

IntelliTrack-powered Audio Panning to Video speeds up the creative process by tracking people or objects in the Fairlight viewer on its own to produce pan automation that mirrors their on-screen motion, with the accuracy that Resolve's cutting-edge object tracking engine provides.

### Drawing Automation

For a video editor or audio creative, drawing mix automation data is often the more direct option in many situations, when you're making static or ramped level shifts or switched changes to controls like a mute button, particularly if you're working with a mouse and don't have the advantages of Fairlight hardware control. As an example, where you'd struggle to finesse a real-time "performance" of fader movements or effect parameter shifts, you could instead select a timeline range and mute several tracks together, "carve out" fixed level boosts or drops on tracks at precisely the moment you want them based on an on-screen event or dialogue, or gradually build up the strength of a reverb on foley footsteps as a character heads into a long, dark cavern. Drawing automation means you needn't concern yourself with the various Fairlight automation recording modes or the control enables/disables for the parameter you want to create or edit; you simply draw or tweak your automation data right in the matching track "lane" on the Timeline.

### Recording Automation

Mix automation can also be built by capturing real-time on-screen fader and control movements, or plugin parameter changes, as playback runs. Your "performance" can then be reproduced faithfully afterward. A further benefit of recording your automation is that you can naturally "perform" the changes against the picture as the action unfolds. This way you can craft a dynamic mix where varying audio levels, pan, EQ, dynamics, and audio processing settings shift over time to bring music up or down against effects or dialogue, pan the sound of a passing car from one speaker across to another, or steadily grow the strength of a reverb as your character heads into that long, dark cavern. Although recording keyframe automation is usually thought of in terms of either the on-screen mixer or the Fairlight console, you can equally record automation using the controls in the Inspector, or via the controls of the Pan, EQ, and Dynamics plugin effects, which lets you record automation for the various audio effects you've placed on a track.

### Drawing Mix Automation

For any parameter, automation can be drawn in the Timeline by globally turning on automation recording and playback, displaying a parameter to be automated, then drawing the automation in the Timeline.

### Enabling and Viewing Automation

Sitting to the right of the transport controls, the Toggle Automation button switches automation recording and playback on and off. It has to be on for you to draw or record track-based automation and to view busses on the Timeline.

### Toggle Automation button

TIP: You can rapidly switch automation safe on or off for a chosen group of channel strips, or for every channel strip, by keeping held, across all selected tracks, the Option key (Mac) or Alt key (Windows), or for every mixer channel strip Command-Option (Mac) or Control-Alt (Windows), prior to carrying out the operation. These shortcuts can shave a great deal of time off your workflow.

### Automation View

Ordinarily, audio tracks show an arrangement of clips on the Timeline ("Clips View"). Within Clips View, clips can be placed or edited, and the clip gain of individual clips can be set, see Chapter 176, "The Fairlight Inspector." Effects can be applied to clips as well, and these can be handled in the Inspector.

Tracks can additionally present an Automation View, which surfaces once the automation button is on. While it's active, a dropdown menu shows up beneath the track controls in the track header. By default that menu reads "None," signaling that you're working with clips alone; no automation data will be shown.

### Fairlight Automation View showing "None"

Clicking that dropdown menu lets you pick an automation parameter to view or edit. There are options for each parameter that a track can control: fader, sends, pan, mute, plus built-in dynamics and EQ, along with AU or VST plugin effects.

### Fairlight Automation View menu choices

For a quicker route, right-click the Mixer channel control you intend to view or edit, or right-click that same target parameter when it lives on a Fairlight FX plugin, a supported Audio Unit, or a VST plugin. After a parameter is picked, the automation view shifts so the emphasis moves to editing track automation data instead of manipulating clips. The clips dim and the automation data line appears in light gray. Once automation is drawn or recorded for that parameter, the line switches to bright green. NOTE: While in Automation View you can still move and trim clips, though cut/copy/paste and delete act on automation keyframe data alone. While in Automation View, timeline-based clip gain keyframe adjustment isn't available, but overall clip gain can still be set with the Volume slider in the Audio tab of the Inspector.

### Vector-based Automation

Audio keyframe automation is vector-based, so levels ramp smoothly between any 2 points on the Timeline according to the direction of the change in control value and the gap in time between the points. As an illustration, say you have one keyframe putting fader level at 0 dB landing at 01:00:20:00 on the timeline; add a further point at 01:00:28:00 set to -10.5 dB, and the level glides smoothly from 0 dB down to -10 dB over the 8 seconds between the 2 points. This lets you draw individual keyframes to quickly assemble different transition shapes, like fade-ins or fade-outs, with only a handful of points, or to bump them up or down by precise amounts quickly and easily.

### Creating Curves

Bear in mind that audio automation keyframes aren't Bezier keyframes, so each one only allows a single level adjustment at that moment in time. Make a large adjustment with just one new keyframe and you can wind up with an abrupt level change, or with level changes lacking the curve you might want (exponential changes can be especially helpful on fade ins or outs to land a natural result). You can produce convex or concave shapes when drawing by laying down just a few keyframes to form your curve, or you can carry out the change exactly to your liking by recording the automation (refer to "Recording Mix Automation" further along in this chapter).

A fade out transition with 5 keyframes for an exponential shape

### Track Automation Line

Audio automation on a track is depicted by a line running across the length of the Timeline, known as the automation line, or "curve." That line's level can be altered by dragging, by entering keyframes one at a time, or by drawing a series of keyframes with the Pencil tool.

Automation line for fader level showing multiple keyframes

Sample Accuracy: With audio keyframes you can place exactly positioned parameter changes onto timeline tracks. Audio keyframes on the Fairlight page are sample accurate, which is to say they can sit at any sample location to sub-millisecond precision, offering finer precision than how keyframes are handled on the Cut and Edit pages. That said, sample-accurate audio automation data made on the Fairlight page plays back accurately on the other pages too. Sample accuracy matters when working to picture, since the location of audio events frequently doesn't land on exact frame or sub-frame boundaries.

### Working with Audio Keyframes on the Timeline

To draw automated changes to any audio control:

- Turn on the Automation button to display Automation View across all audio tracks.
- On the track(s) where automation should be created, choose, within the Automation type dropdown menu in the track header, the parameter you'd like to automate.
- Focus Mode's Multi tool lets you draw automation via the up/down arrow cursor (for shaping a broad curve), insert or delete keyframes individually using modifier keys, generate varied curves according to where each keyframe sits, mark and remove a span of keyframes, and beyond.

### Adding and Deleting Individual Keyframes

Handling keyframes on the automation line is almost the same as working with clip gain.

- To add a keyframe: Hold the option key and a plus sign appears. Click to drop a keyframe onto the automation line.
- To remove a keyframe: Hold Command-option and a minus sign appears. Click on the keyframe to delete it.

For more information see Chapter 176, "The Fairlight Inspector."

TIP: You can rapidly switch between Clips View and Automation View with the keyboard shortcut F4. This can be reassigned via the DaVinci Resolve > Keyboard Customization dialog.

### Editing Mix Automation Curves

### Using Edit Operations

The usual editing operations—cut, copy, paste, delete, and nudge—all work on automation keyframe data. When automation data gets cut or deleted, the value at each end of the selection is held. Nudging proves quite handy for fine-tuning where automation events sit.

### Before and after cut or deletion

### Adjusting the Automation Line

Once one or more keyframes sit on the automation line, the resulting curve for the whole track can be adjusted. Individual keyframes can be moved up or down using the same techniques as adjusting clip gain; the entire line can be adjusted, or just a selection can be affected. Adjust the last keyframe on a line carrying multiple keyframe points and the line will shift from that point onward to the level you newly set.

Adjusting an individual keyframe changes the line from that point onwards.

### Adjusting the Entire Line

To adjust the entire line:

- With automation view on, click anywhere inside the track, and select every bit of automation data on the curve by choosing Command-A.
- Bring the cursor near the line and the dual arrow cursor appears, letting the level of the whole line be adjusted.

### Select all automation to adjust the entire line

### Adjusting a Selected Range

Adjustments can be confined to only a specific portion of the automation curve. This is useful for those times you'd like to apply "snapshot" changes to one particular scene. To adjust only a selected range:

- Use the Focus Mode Select tool (I-beam cursor) to mark the range you want to affect.
- Bring the mouse near any part of the line, and the up/down arrow cursor appears.
- Trim the line up or down. A tooltip surfaces showing the current value plus a delta from the original value, so any change in a control's value is visible.
- At the edges of the selection, "bounding keyframes" get created automatically, so the level at the selection's border is held.

### Trimming a selected range of the automation curve

TIP: Hold the Shift key while adjusting levels to keep precision. When you're adjusting fader levels this gives .1 dB accuracy, even while working with small track heights.

### Drawing Automation with the Pencil Tool

Automation keyframes can be drawn freely with the Pencil tool:

- Pick the Pencil tool in the Automation toolbar, or while in Focus mode, hold Option-Shift to switch over to the Pencil tool temporarily.
- Click the mouse and drag to draw keyframes in either direction.

### Automating Switched Controls

Some automation parameters are switched (that is, they hold only fixed states). Mutes (on or off) are an example of this control type. When you're adjusting switched automation, keyframes can only sit at the bottom end of the Automation view or the top.

### Mute automation showing on and off states

### Trimming Automation from Unity in the Mixer

In the Fairlight mixer, Trim mode lets you trim automation from unity (Fader at 0) by working through the steps that follow: 1 Within the Automation toolbar, switch the Automation mode over to Trim. The Automation toolbar - Trim mode 2 Choose one Touch mode out of Latch, Snap, or Snap Latch. 3 Hit the Automation Arm button on whatever mixer channel or tracks need trimming. On the armed mixer channels the faders go yellow and snap down to zero, while the dB Indicator sitting above each armed fader reads Δ0.0dB. TIP: Either Command-Option click the Automation Arm button to trim automation across every track, or Option-click that button to trim automation for whichever set of tracks or mixer channels you've highlighted. Mixer faders set to trim utomation from unity 4 Start playback and shift the fader above or beneath Δ0.0dB. That trims the automation curve, with the dB indicator displaying the trim figure as a plus or minus (+/-) value. Where you've chosen Snap mode, the fader heads back to Δ0.0dB according to the Glide time set in Preference > User > Fairlight > Automation.

### Audio Panning to Video

Audio Panning to Video taps DaVinci Resolve's cutting-edge object-tracking engine to help you rapidly produce precision panning automation from how people and objects move in the Fairlight Viewer. Audio Panning to Video provides Automatic and Manual modes of operation.

### Automatic Tracking

Within Automatic Tracking mode, select a person or object on screen and DaVinci Resolve handles the related movement data over a chosen timeline range by itself, then produces the automation data. To switch on and work with Automatic Tracking: 1 Hit the Toggle Automation button found to the right of the transport controls.

Toggle Automation button 2 Open the Fairlight Viewer tools menu and select Show Tracker Controls.

### Fairlight Viewer Tools menu

The Tracker Controls show up along the lower edge of the Viewer, and an Auto Tracker Object appears on screen.

### Tracker controls

### Audio Tracker Object

You can also pick Show Tracker Coordinates, which gives an alpha-numerical readout of the tracker's current on-screen position.

Audio Tracker Object with Coordinates

3 Pick the target track you want to write panning automation onto, and use the I-Beam tool to mark the Timeline range you want the tracking to operate on.

### Range Select tool

NOTE: Unless a Timeline range is chosen, Auto-tracking won't run. 4 Within the Tracking Controls section, hit the Auto button to engage Auto Tracking. 5 According to whether the panning movement you're automating is horizontal or vertical, hit the Left-Right (L–R) or the Down-Up (D–U) button. TIP: Only while the Auto button is off does the Front-Back (F-B) button appear. 6 Over on the target track, hit the Automation dropdown in the Track Header, followed by Pan > L/R Pan or Pan > U/D Pan so it lines up with what you chose a step earlier. 7 Drag the Auto Tracker Object onto whichever on-screen object or person you mean to track. 8 Hit the Track button so the Auto-Tracking process begins. 9 Kick off playback to verify your audio track; it ought to trail the object or person you set for tracking. TIP: With a trickier track, perhaps a person whose distance from the camera keeps changing or who drifts out of frame, you might need to track in segments. When that happens, mark an area that tracked poorly, drag the tracker object into place, and re-track across the problem range to redo that stretch.

### Manual Tracking

Manual mode has you create keyframes off the Playhead position on the Timeline, with DaVinci Resolve smoothly vectoring between those keyframes exactly as it does for any other automation curve data. To switch on and work with Manual Tracking: 1 Hit the Toggle Automation button found to the right of the transport controls. 2 Choose the target track onto which your panning automation should be written. 3 Open the Video Viewer tools menu and select Show Tracker Controls. Those tracker controls appear along the Viewer's lower edge, with a Tracker Object showing on screen as a plain crosshair.

### Tracker Controls manual mode

### Manual Tracker Object

NOTE: The Tracker object won't show onscreen unless an audio track has been selected. You can also opt to Show Tracker Coordinates.

Manual Tracker Object with Coordinates 4 Confirm the Auto button is switched off within the Tracking controls. That puts you in Manual Tracking mode. 5 Inside the Tracking Controls, hit the panning control of your choice, namely Left-Right (L–R), or alternatively FrontBack (F-B), or Down-Up (D–U). 6 Over on the target track, hit the Automation dropdown in the Track Header, then to mirror your earlier choice pick Pan > L/R Pan, or else Pan > F/B Pan, or Pan > U/D Pan. Should the Automation dropdown be hidden, you can increase the track height. 7 Bring the Playhead to whatever Timeline spot the automation should start at. 8 Lay down a keyframe at the video's current position by Option-clicking the Viewer wherever you'd like the sound sitting at that instant. A corresponding Automation node drops onto the automation line at the Playhead position. 9 For a further keyframe, shift the Playhead elsewhere along your timeline, then Option-click whichever on-screen person or object you're tracking. The Tracker Object leaps to that spot, a keyframe gets written, and a fresh Automation mode joins it at the Playhead position.

DaVinci Resolve vectors smoothly across the keyframes, just as it would with any other automation curve data. 10 Keep laying down keyframes at the spots you want by redoing the prior step. 11 For a "bounding keyframe" that pins a position so the automation line holds before shifting to a new one, Option-Shift-Click on a location. 12 Start playback to verify, and tweak your automation should it need it.

### Recording Mix Automation

Recording mix automation leans on plenty of the same techniques as drawing, only here you capture a performance by moving whichever controls need automating. It can prove flexible and creative as you "perform to picture" to land the outcome you want. As a first step, confirm Automation recording is switched on (refer to "Enabling and Viewing Automation" above), with one or more parameters set up for automation recording.

Clicking the Automation Controls button displays the Automation toolbar

### Automation Controls

Positioned to the right of the transport controls, the Automation Controls button lets you show and hide the Automation toolbar. The Automation toolbar carries buttons for each option available when you're getting ready to record automation in your mix.

### Automation toolbar options

The Automation toolbar shows the following options:

- Automation Modes: Governs how automation data gets recorded. Write: Records absolute changes to a control's position, overwriting whatever data sat there before. Trim: Records relative changes to a control's position, keeping the relative existing levels built up over time while raising or lowering those levels overall. This can be very useful when you're incrementally refining a mix.
- Touch Modes: Sets what occurs when an automatable control is moved during a mix. Off: No automation gets recorded. Latch: Automation begins recording once a control is moved and keeps recording after the control is released until the transport stops. Snap: Automation begins recording once a control is moved and then glides smoothly back to the prior level at the point of release, producing a seamless transition.

Where the glide transition finishes, automation is no longer recorded unless the control is moved once more while the transport plays. You can keep capturing further automation with Snap until the transport stops. You set the glide transition's duration, in milliseconds, under Preferences > User > Fairlight > Automation. Its default sits at 250 ms. Snap Latch: A blend of Snap and Latch modes, in which faders work in Snap while every other control works in Latch. This proves useful when you want dynamically changing fader levels through a mix pass while other controls "stick" when they're moved. It's particularly useful with Fairlight mix control surfaces, where faders and rotary controls can be altered at the same moment during a mix pass.

### FAIRLIGHT 3926

- On Stop: Determines what happens once you press Stop at an automation pass's end. Event: The most recent recorded automation value overwrites the earlier levels right up to where the next available recorded automation data (or event) begins on that track. Hold: Erases every previously recorded mixing entry following what you just laid down, so the last recorded level carries through the rest of that track. Return: That last recorded automation value gets interpolated, ramping back toward the track's previously recorded automation values.
- Enables: The buttons here let you toggle on or off the various controls you record automation for. Fader: covers track and bus volume. Mute: drives the mute button. Pan: handles all pan controls. EQ: takes in all EQ controls. Comp: targets only the Compressor controls inside the Dynamics window. Gate: targets only the Gate controls inside the Dynamics window. Lim: targets only the Limiter controls inside the Dynamics window. Sends: governs the Send controls over in the Sends window. Plugins: spans all Fairlight, VST, or Audio Unit (AU) plugins. Misc: reaches the Buss on/off, Insert, and Direct Out controls. Should a project be running the Fairlight legacy Fixed Bus configuration, automation of the fixed bus Main and Sub bus enables becomes available too.

### How to Record Automation

Two distinct approaches exist for setting up automation recording across levels, panning, EQ, Dynamics, and the other audio controls within the mixer.

### Recording Automation for Multiple Tracks
