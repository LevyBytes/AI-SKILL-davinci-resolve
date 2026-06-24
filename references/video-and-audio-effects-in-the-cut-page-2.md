# Video And Audio Effects In The Cut Page (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

With speed effects you can accelerate, decelerate, or otherwise alter how fast clips play back in the Timeline. Altering a clip's speed also alters its duration, producing either a shorter clip that runs faster or a longer one that runs more slowly. Both video and audio playback are affected by speed effects, though the audio of clips that are sped up or slowed down is always pitch corrected. Any speed effects you apply on the Cut page also show up—and stay editable—through a handful of different routes in the Edit page timeline and the Video inspector.

### Speed Effects controls in the Viewer

Add Speed Point: Drops a speed-change point at the playhead's location so you can build speed-ramping effects. Speed: Adjusting this figure lets you accelerate or decelerate playback using a straightforward numeric multiplier. A negative value is also an option, which produces reverse speeds. Duration: While you retime a clip, the Duration field shows you how the change you're making affects the new duration relative to the clip's original duration with no speed effect applied.

### Stabilization

By applying warping and/or translation, the Image Stabilization controls let you smooth away—or even fully lock down—unwanted camera motion inside a clip. The analysis runs in a way that holds onto the motion of individual subjects within the frame, along with the overall direction of any intended camera motion, all while ironing out the unsteadiness.

### Stabilization controls in the Viewer

Stabilizing an image takes only a couple of steps: pick a Stabilization Method from the drop-down (more on those below), then click the Stabilize button. DaVinci Resolve studies the current clip and applies a stabilization effect. The remaining stabilization controls are there to fine-tune the outcome. Any time you change one of these parameters, you have to click the Stabilize button once more for the effect to refresh.

Stabilization Method: This drop-down menu offers three separate options governing how the chosen clip gets analyzed and reshaped while being stabilized. Settle on an option before you click the Stabilize button, since the option you select alters the way the image analysis runs. Switch to a different option and you click the Stabilize button again to reanalyze the clip.

- Perspective: Switches on perspective, pan, tilt, zoom, plus rotation analysis and stabilization.
- Similarity: Switches on pan, tilt, zoom, plus rotation analysis and stabilization, for cases

where running perspective analysis introduces motion artifacts you don't want.

- Translation: Switches on pan plus tilt analysis and stabilization alone, for cases where nothing more than

X and Y stabilization yields results you can live with. Stabilize: Click this button on a clip not yet stabilized and it studies that clip's motion before laying down an initial smoothing effect. Click it on a clip already analyzed and you can recompute a tweaked stabilization effect. TIP: These controls match the ones in the Video Inspector and the Color page Tracker palette, and they feed the same image processing data. So you can run the Stabilization on the Cut page, then turn to the stabilization graph and controls on the Color page to refine the outcome whenever that's needed.

### Lens Correction

Lens Correction supplies two controls that let you either fix lens distortion in the picture or introduce lens distortion of your own as an effect. You can also edit these controls in the Video Inspector and the Color page Edit Sizing palette.

### Lens Correction controls in the Viewer

Analyze: Automatically inspects the frame sitting at the playhead in the Timeline for edges that a wide-angle lens has distorted. Clicking the Analyze button shifts the Distortion slider to deliver an automatic correction. On an especially tough clip, a progress bar shows up to let you know how long it'll take. Distortion: Dragging this slider rightward lets you manually warp the image so that areas bent by wide-angle lenses are straightened out. Should clicking the Analyze button leave you with an overcorrection, dragging the slider leftward backs off the automatic adjustment until the picture looks right.

### Color

Inside the Tools, the Color section holds a single option: Auto Color. The Auto Color command offers a fast way to automatically balance a clip's blacks and whites using the current frame sitting at the playhead. Driven by advanced algorithms built on the DaVinci Neural Engine, it gives you superior results when automatically tuning color balance and contrast.

### Color controls in the Viewer

To dig deeper into working with Auto Color, turn to Chapter 127, “Automated Grading Commands and Imported Grades.”

### Audio

A slider lets you tune the current clip's audio levels right in the Viewer, making that audio clip's volume quieter or louder. This matches each clip's volume setting over in the Edit and Fairlight pages.

### Audio controls in the Viewer

### Effects Overlay

Switching on either the Open FX or Fusion overlays lets you work with the onscreen viewer controls for whichever effects make use of them. The Effects overlay turns on the onscreen viewer controls for effects.

### Smart Reframe (Studio Version Only)

The Smart Reframe feature inside DaVinci Resolve takes the pain out of quickly reframing footage across big aspect ratio shifts. It proves handy in cases where you shot a 16:9 horizontal video and now require a vertically-oriented 9:16 cut for mobile phones plus social media deliverables, or where you're fitting 4:3 archival footage inside a 2.39:1 widescreen movie. Smart Reframe runs either by hand or automatically; the automatic path is driven by the Neural Engine inside DaVinci Resolve. Smart Reframe in action with the Reference Point bounding box active (right) Within the Inspector's Video tab you'll find the Smart Reframe tool, on hand across both the Cut and Edit pages. Here is how you put the Smart Reframe tool to work: 1 Make a copy of your Timeline, then right-click it and pick Timelines > Timeline Settings; click Use Custom Settings so you can set the Timeline Resolution to whatever aspect ratio your delivery calls for. Confirm that “Mismatched resolution files” reads “Scale full frame with crop,” then click OK. 2 Pick one or more clips you'd like to reframe, then open the Inspector to its Video tab. 3 Bring up the Smart Reframe controls, keep the Object of Interest drop-down menu on Auto (where you've picked more than a single clip, Auto is your only choice), and click “Reframe.” DaVinci Resolve studies your footage and ought to shift each clip's position on its own to a framing that looks more pleasing. 4 (Optional) Should the “Auto” setting fall short on a given clip, you can pick the main subject by hand through these steps: a) To mark the subject area yourself, set the Object of Interest drop-down menu to “Reference Point,” then click the Target icon located just to the right of it. Doing so flips the Viewer mode over to Smart Reframe and reveals the onscreen controls for picking a reference. b) Drag the Reference Point bounding box so it encloses the frame's main subject of interest. Where your subject sits beyond the current framing, the Transform controls right above in the Inspector let you reposition the source clip. 5 (Optional) To pen the AI in to reframing along just one axis, pick either Pan Only or Tilt Only over in the Mode selector. 6 Click Reframe.

The Inspector’s Smart Reframe controls showing the manual reference point selected Using the reference you've picked, DaVinci Resolve fixes onto your subject—and tracks it where needed—automatically panning and scanning the original clip so the reference stays inside the new aspect ratio. Even with a little manual adjustment required, this function still cuts dramatically into the time it takes to pan and scan footage by hand-adjusting and keyframing the sizing controls.

### Ripple Delete Silence for Selected Clip

You can analyze and strip silences out of a selected clip on the Edit or Cut page timeline, leaning on the comparable tool over in Fairlight. Select a clip, then choose Clip > Audio Operations > Ripple Delete Silence to bring up the Ripple Delete Silence dialog. Threshold: Sets the highest signal level of your audio (in dB) that counts as silence. Audio signals beneath the threshold are regarded as silence and removed. Raising the threshold removes more audio. Pre Head: Sets how much silence, or pre-roll, sits ahead of each audible section. Post Tail: Sets how much silence, or post-roll, sits after each audible section. Minimum to Trip: This parameter sets the smallest stretch of silence (in frames) to be pulled from the selected timeline clips. Larger values leave more silent sections in the audio. Smaller values produce more strips, but you might notice that some leftover audio sounds “chopped up” where it cuts off abruptly. Crossfade audio: Runs a basic crossfade across the remaining audio clips to smooth out the sound, provided your head and tail settings allow enough length.

### The Ripple Delete Silence dialog

Here's how you strip silences out of a timeline clip: 1 On a track, pick a clip. 2 Head to Clip > Audio Operations > Ripple Delete Silence. 3 The look of the selected audio shifts to add vertical red stripes that mark where and how long the resulting silences run, drawn from the parameter values set in the Remove Silence dialog. 4 Click Remove. Every bit of audio beneath the red stripes is cut and removed, and the clip's leftover sections are ripple deleted together along the timeline.

### Voice Isolation (Studio Version Only)

Voice Isolation draws on an AI model trained for every kind of human voice—male or female, young or old—

which lets you fully strip loud, unwanted sounds out of existing voice recordings with

remarkable results.

### The Voice Isolation plugin

You can clear away all manner of background noise, whether it's air conditioners or fans, jackhammers, restaurant ambience, music playing under a featured line of dialogue, and beyond. The Amount control sets the blend between the original source and the isolated voice. At 50, the blend is roughly even. Settings between 70 and 80 deliver natural results while still isolating the source firmly. Even though Voice Isolation can run on an audio track in real time, it won't work on live audio input. It works on any mono, stereo, or dual-mono audio track, but tracks carrying more than two channels aren't supported.

### Dialogue Leveler

The Dialogue Leveler examines source material to find dialogue, then “rides down” the louder stretches, “lifts up” the softer ones, and pulls down background sounds that aren't dialogue. It does this without the usual “pumping” or other unwanted side effects that come with dynamics processors (compression/limiting), arriving at results akin to those you'd get from careful, manual clip gain tweaks or from “riding” a track via fader automation. Often the Dialogue Leveler can “fix and mix” a recording made on a single boom mic, where one character sits closer than another or turns away from the mic. The Dialog Leveler evens it out so that the original relative dynamics stay intact while intelligibility and average level both rise. Even though Dialogue Leveler can run on an audio track in real time, it won't work on live audio input. It works on any mono, stereo, or dual-mono audio track, but tracks carrying more than two channels aren't supported.

### The Dialogue Leveler plugin

### Dialogue Leveler controls

Dialogue Leveler: Turns the plugin on or off. Waveform Processing display: This presents a scrolling waveform alongside a gray line marking Dialogue Leveler processing. That said, the display goes missing whenever you reach for the Inspector's Dialogue Leveler to process timeline audio clips. Preset Menu: This menu hands you the following options:

- Allow wider dynamics: The default choice, and the strongest pick for audio whose dynamic spans a wide range from loud down to soft, with clip levels running medium to high.
- More lift for low levels: Reach for this option where the source carries more low-level dialogue you'd like to lift.
- Lift soft whispery sources: Reach for this option where the source holds whispered dialogue together with background noise.
- Optimize moderate levels: Reach for this option where the source sits at medium levels from start to finish.

Reduce Loud Dialogue: With this on, louder dialogue is ridden downward as it peaks, behaving like a “perfect limiter” where there's no threshold or time parameter for you to set. Thanks to the “near real-time” design, analysis happens ahead of audible playback for the best outcome. Lift Soft Dialogue: This setting locates and raises low-level dialogue, smoothing out material that is quieter yet more variable in level. Since the process zeroes in on dialogue, it tends not to push up background sounds unless they're audible at the same moment as the dialogue. The Lift Soft Dialogue option is frequently the handiest of the three, since it makes quieter dialogue lines louder and naturally smooth without lifting background noise. Background Reduction: This option softly removes background noise according to the internal preset chosen in the Preset menu. Output Gain: Reach for this control to set the output level, either by clicking and dragging or by typing a value into the numeric field. The Output Gain control ranges from 0.0 to +6.0 dB.

TIP: Ahead of running the Dialogue Leveler on a track, you may find it worthwhile to establish a solid baseline

level—suited to the default “Allow wider dynamics” preset—by normalizing the audio first.

To learn more about normalizing audio, consult Chapter 176, “The Fairlight Inspector.”

### Music Remixer (Studio Version Only)

This DaVinci Neural Engine AI-based plugin separates music into individual stems: Vocals, Drums, Bass, Guitar, and “Other” (“everything else”), so you can creatively rebalance or remix the track. The level controls let you set each stem's volume, and the Mute buttons let you drop stems out or bring them back into your mix. For instance, you might want to pull down or remove a vocal because it competes with a featured line of dialogue.

### The Music Remixer plugin

### Music Editor (Studio Version Only)

DaVinci Resolve 20 can seamlessly stretch or trim music to match the length of your edit. You'll reach the new AI powered Music Editor through the Inspector's Audio tab. Type in a desired duration and hit the Adjust button so the clip stretches or trims to fit it. NOTE: As an “intelligent edit,” Music Editor performs well on beat-driven music such as pop or dance. Free-form, ambient, or material lacking a beat falls outside what it's built for. Rather than using time compression/expansion or shifting the music's pitch, Music Editor borrows the techniques a music editor would use to fit material to a desired length against picture. It hunts for sensible spots to build transitions depending on whether you're lengthening (by repeating sections) or trimming material, and it tries to use the original composition's ending or fade when the timing lands well. Where the ending is abrupt, it's left to you to craft a fade out by hand.

### The Music Editor in the Audio Inspector

To Use Music Editor to retime a music clip: 1 On the timeline, pick the clip you intend to retime; bear in mind it has to be beat-driven music. 2 Within the Audio Inspector, beneath AI Music Editor, type in a fresh Target Length matching the music duration you're after. 3 Hit the Adjust button. 4 As another route, tick the Live Trim box so the Trim tools can resize the clip and retime the music on the timeline on the fly. Untick the checkbox to drop back into ordinary editing (trimming, say) for that clip once you've built the edit you wanted. Once the analysis finishes, four candidate edits open up at the bottom for you to choose among, each going about the edit a different way and numbered 1-4. Any editing you do afterward can happen almost instantly. The edited stretches of music carry indicators on the clip flagging where the cuts and transitions land.

### The initial music is too long

Here the Music Editor has retimed the audio clip so it lines up with the video's length. Notice the jagged lines along the audio clip flagging where the original got cut. Within the waveform, you can spot that the music's ending survives in the retimed clip.

TIP: Timings often land very close, yet now and then they won't be spot-on. Should you need precise timing once you're done with AI Music Editor, the Elastic Wave tool on the Fairlight page is worth a try—pick its general-purpose (music) algorithm.

The edited clip is in fact a specialized Music Editor clip, which lets you keep trimming your edit. If

you'd like to reach the underlying edit, you can also right-click the clip and decompose, which exposes

the edit points along with any crossfades that were created. Bear in mind, though, that once you've decomposed it, you can't

trim the clip's length as a single entity, since each editing snippet is now its own separate clip.

### Dialogue Separator Track FX (Studio Version Only)

Powered by DaVinci Neural Engine AI, Dialogue Separator hands you separate control over the level of the dialogue, the background sounds, and the reverberant field—or ambient room sound (“ambience”). Dialogue Separator earns its keep when, say, a source file has a wonderful roomy sound but carries music or crowd noise underneath. Here you can rebalance the audio to cut down the background sounds or shape the room sound to make the dialogue clearer. Another scenario: someone walks toward the camera in a roomy space while talking. Automation could then rebalance the audio so the ambient room sound steadily turns “drier” as they draw nearer, all without touching the background. For now, Dialogue Separator is a mono-only plugin. Where your source is stereo, you'll need to break it into dual-mono and process each mono track on its own.

### The Dialogue Separator plugin

### Ducker Track FX

This plugin lets you take the audible signal from one track or several and use it to pull down the level of another.

While it can be put to plenty of creative uses, a common application of “ducking” is automatically lowering a music or sound effects bed so dialogue or a VO track stands out more clearly in a mix.

That's accomplished without compressing the signals coming in. Set up properly in the Ducker interface or by way of the Inspector's Audio tab, your audio tracks can practically “mix themselves.”

In a simple scenario, the Ducker uses the level changes of a single incoming dialogue or VO track to lower the volume of the sound effects bed of a noisy freeway.

In a trickier situation—say a scene where three characters are talking beside that same noisy freeway—a lone Ducker plugin can draw on the level changes of each dialogue track to attenuate the traffic noise.

With just one input source (Dialogue 1), the Ducker would kick in only while the first character

speaks. This new capability, though, lets you bring the other two dialogue tracks (Dialogue 2 and

Dialogue 3) in as input sources for knocking down the traffic noise.

### The Ducker plugin

### Using the Ducker

Carrying on from the use cases above: 1 Pick the target track you'd like to attenuate (the Freeway Traffic track), and open up the Ducker. 2 Open the Source dropdown and pick Dialogue 1 to serve as the input source.

- For extra input sources, Command-click the remaining track names; here that means Dialogue2 and Dialogue3.
- Run a stretch of your sequence and dial in the duck level along with the other controls until it sounds right.

Adding Input Sources via the Inspector If working inside the Inspector suits you better: 1 Pick the Freeway Traffic track, confirm the Ducker is on, and bring up the Inspector’s Audio tab. 2 Hit the plus sign at the right of the Source 1 dropdown that holds Dialogue1; that spawns a dropdown menu for Source 2, and you then pick Dialogue2 off the list.

3 Hit the plus sign at the right of the Source 2 dropdown; that spawns a dropdown menu for Source 3, and you then pick Dialogue3 off the list.

### Adding Ducker input sources in the Inspector

### Ducker Controls

- Duck Amount: Sets, in dB, how much the target track gets attenuated; its default sits at 2.7 dB. For most jobs, somewhere between 2.0 dB and 5.0 dB suits best.
- Lookahead: Tunes the lookahead time, measured in milliseconds, defaulting to 15ms. With lookahead, the Ducker can begin attenuating the destination track ahead of the source track becoming audible.

A larger value has the Ducker “pre-anticipate” the source track that much sooner. Where you want the Ducker to start dropping the sound before a dialogue or VO line begins, experiment with higher values—though the default usually serves you well.

- Rise Time: Sets, in milliseconds, how long the Ducker takes to arrive at the reduction the Duck Amount calls for. It defaults to 10 milliseconds, which suits most cases. Longer Rise Times can help alongside higher Duck Amount values and wider gaps in the source track.
- Hold: This parameter fixes how long the target signal stays attenuated. Its default is 150ms.
- Recovery Time: This figure governs how fast the target signal climbs back to its prior level once attenuation ends. The default sits at 750ms, but dialing in the right Recovery time is key to ducking that sounds natural, so test a range of values to land on the best one.

### Ducker Graph Display

This area presents a gray line standing for the incoming signal set against the Ducker's action, drawn in yellow. Dips in the yellow line mark attenuation of the target track, driven by the Duck Amount together with the other parameters.

### Beat Detector (Studio Version Only)

For a piece of music on the timeline, DaVinci Resolve can detect the beats on its own, and it lets you snap to those beat marker spots. That comes in handy when you're aiming to cut on the beat. NOTE: For now, the Beat Detector performs reliably only with beat-driven music carrying 4/4 or 3/4 time signatures. To pick up the beats, right-click the timeline audio clip and choose Detect Music Beats off the context menu. After the analysis, the timeline clip presents beat indicator overlays, and other timeline elements can snap onto them. A music track carrying the Beat Detector. Those lined overlays line up with the music's beat.

### Dialogue Matcher (Studio Version Only)

Dialogue Matcher lets you match one piece of dialogue to another, lining up level, EQ, and reverb. It can rescue situations where new recordings don't sit in the same environment as existing ones. The Dialogue Matcher is a fully automated tool that only asks the user to grab a tone profile from one clip and then apply it to another.

Capturing a Dialogue Profile from a clip using the main menu

To Use Dialogue Matcher: 1 Pick a reference clip whose dialogue you'd like to match, right-click it, and go to Clip > AI Tools > Dialogue Matcher > Capture Dialogue Profile. 2 Pick the clip whose dialogue you mean to alter, right-click, and go to Clip > AI Tools > Dialogue Matcher > Apply Dialogue Profile. 3 Switching the Dialogue Matcher on or off for a clip is a matter of right-clicking and going to Clip > AI Tools > Dialogue Matcher > Enable. 4 To strip the Dialogue Matcher off a clip, right-click and go to Clip > AI Tools > Dialogue Matcher > Remove Applied Profile.

### Audio Assistant (Studio Version Only)

Through the Audio Assistant, DaVinci Resolve is able to sort and color-code your tracks for you, smooth

over your dialogue levels, and move the mixer faders so as to build a professional-quality blend of your music,

sound effects, and dialogue.

As this runs, your dialogue gets cleaned up as well, and where the situation calls for it, Voice Isolation and

De‑Essing are brought in. Music tracks receive Ducking, whatever automation is required gets

written, and the right mastering and finalizing plugins are added and tuned to help

reach the correct loudness level for whichever delivery standard you've selected.
