# Working With Audio In The Edit Page (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

To Use Music Editor to retime a music clip: 1 On the timeline, pick the clip you intend to retime; the material must be beat-driven music. 2 Within the Audio Inspector, beneath AI Music Editor, type the new Target Length matching the music duration you're after. 3 Click the Adjust button. 4 As another route, tick the Live Trim box so the Trim tools can resize the clip and retime the music live on the timeline. Clear that checkbox to go back to ordinary editing (such as trimming) for the clip once you've built the edit you wanted. When the analysis finishes, four candidate edits become available along the bottom, numbered 1-4, each taking a distinct approach. From there, further editing happens nearly instantly. Markers along the edited music identify the spots at which cuts and transitions land.

### The initial music is too long

Here the Music Editor has shortened the audio clip so its length lines up with the video. Observe the jagged lines across the audio clip, which flag where the original got cut. Within the waveform, notice that the tail of the music carries over into the retimed clip. TIP: Although the timing is often very close, it isn't always precise. When you require an exact result after using AI Music Editor, consider the Elastic Wave tool over on the Fairlight page, picking the general purpose (music) algorithm. What you end up with is really a dedicated Music Editor clip, so you can keep refining the edit. To reach the edit beneath, right-click the clip and decompose, which reveals the edit points along with whatever crossfades were generated. Bear in mind, though, that after decomposing you can no longer trim the clip's overall length as a unit, since every editing fragment has become its own clip.

### Dialogue Separator Track FX (Studio Version Only)

Powered by DaVinci Neural Engine AI, Dialogue Separator hands you separate control over the levels of dialogue, of background sounds, and of the reverberant field or ambient room tone (“ambience”).

### The Dialogue Separator plugin

Take a case where a source file has wonderful roomy character but carries music or crowd noise underneath — that's where the Dialogue Separator earns its keep. Here you can rebalance the mix to pull down the background sounds, or tweak the room sound so the dialogue reads more clearly.

A second scenario: somebody walking toward the camera in a roomy space as they talk. Automation could rebalance things so the ambient room tone steadily grows “drier” as the person nears, leaving the background untouched. At present, Dialogue Separator works in mono only. Stereo sources have to be broken into dual-mono, with each mono track handled on its own.

### Ducker Track FX

With this plugin you tap the audible signal from one or several tracks to pull down the level of another. There are plenty of creative applications, but the usual point of “ducking” is to automatically dip a music or sound effects bed so dialogue or a VO track sits more clearly out front in the mix — and it does so without compressing the signals coming in. Configure it properly inside the Ducker interface, or through the Audio tab in the Inspector, and your tracks will all but “mix themselves.” As a basic example, the Ducker reads the level changes of one incoming dialogue or VO track and reduces the volume on the sound effects bed of a noisy freeway. Take a trickier setup — three people talking beside that same noisy freeway — and a lone Ducker plugin can read each dialogue track's level changes to hold down the traffic noise. Given a single input source (Dialogue 1), the Ducker only kicks in while the first person talks. This newer capability, though, lets you bring in the remaining two dialogue tracks (Dialogue 2 and Dialogue 3) as further input sources for taming the traffic noise.

### The Ducker plugin

### Using the Ducker

Picking up from the use cases above: 1 Pick the target track you mean to attenuate (the Freeway Traffic track) and launch the Ducker. 2 Open the Source dropdown and pick Dialogue 1 to serve as the input source.

- For extra input sources, Command-click the remaining track names — here, Dialogue2 and Dialogue3.
- Run a portion of your sequence and tune the duck level along with the rest of the controls until it sounds right.

Adding Input Sources via the Inspector If the Inspector is where you'd rather work:

- Pick the Freeway Traffic track, confirm the Ducker is turned on, and bring up the

Inspector’s Audio tab.

- Hit the plus sign beside the Source 1 dropdown that holds Dialogue1, which spins up a

dropdown menu for Source 2; from there choose Dialogue2 in the list.

- Hit the plus sign beside the Source 2 dropdown to spin up a dropdown menu for

Source 3, then pick Dialogue3 in the list.

### Adding Ducker input sources in the Inspector

### Ducker Controls

- Duck Amount: Governs how much the target track is attenuated, measured in dB, defaulting to 2.7 dB. In most cases a setting from 2.0 dB to 5.0 dB performs best.
- Lookahead: Tunes how much lookahead time, in milliseconds, is used; the default is 15ms. Lookahead lets the Ducker begin attenuating the destination track before the source track becomes audible.
- A bigger value makes the Ducker “pre-anticipate” the source track to a greater degree. Should you want the Ducker dipping the sound ahead of a line of dialogue or VO, try pushing the value higher, though the default tends to give solid results.
- Rise Time: Sets the number of milliseconds the Ducker takes to arrive at the reduction defined by the Duck Amount. Its default is 10 milliseconds, fine for the majority of cases. Longer Rise Times can help when you're running higher Duck Amount values and there are longer gaps in the source track.
- Hold: Controls the duration over which the target signal stays attenuated. Default is 150ms.
- Recovery Time: Specifies how fast the target signal climbs back to where it was once attenuation lets up. The default sits at 750ms, but dialing in the right Recovery time matters a lot for natural-sounding ducking, so experiment with several values to land on the best one.

Ducker Graph Display Within this region a grey line plots the incoming signal alongside the Ducker's behavior, drawn in yellow. Where the yellow line dips, the target track is being attenuated according to the Duck Amount working together with the remaining parameters.

### Beat Detector (Studio Version Only)

For a piece of music sitting on the timeline, DaVinci Resolve is able to find the beats on its own, and it lets you snap to those beat marker positions. That comes in handy whenever you're cutting to the beat. NOTE: For now the Beat Detector functions reliably only with beat-driven music and only at 4/4 or 3/4 time signatures. Right-click the timeline audio clip and pick Detect Music Beats from the context menu to run the detection. After analysis, beat indicator overlays appear on the timeline clip, and you can snap other timeline elements to them.

A music track carrying the Beat Detector. Its lined overlays line up against the music's beat.

### Dialogue Matcher (Studio Version Only)

Using Dialogue Matcher, you can align one piece of dialogue to another so the level, EQ, and reverb agree. It's handy when fresh recordings don't sit in the same environment as existing material. Fully automated, the Dialogue Matcher only asks the user to grab a tone profile off one clip and then apply it onto another.

Capturing a Dialogue Profile off a clip by way of the main menu To Use Dialogue Matcher: 1 Pick a reference clip carrying the dialogue you want to match, right-click, and pick Clip > AI Tools > Dialogue Matcher > Capture Dialogue Profile. 2 Pick the clip whose dialogue should change, right-click, and pick Clip > AI Tools > Dialogue Matcher > Apply Dialogue Profile. 3 Turn the Dialogue Matcher on or off for a clip by right-clicking and picking Clip > AI Tools > Dialogue Matcher > Enable. 4 Strip the Dialogue Matcher off a clip by right-clicking and picking Clip > AI Tools > Dialogue Matcher > Remove Applied Profile.

### Audio Assistant (Studio Version Only)

Through the Audio Assistant, DaVinci Resolve can sort and color-code your tracks on its own, balance out your dialogue levels, and set the mixer faders to deliver a professional-grade blend of your music, sound effects, and dialogue. Along the way your dialogue gets cleaned up too, with Voice Isolation and DeEssing applied where called for. Music tracks receive ducking, whatever automation is needed gets written, and the right mastering and finalizing plugins are inserted and tuned to reach the proper loudness target for the delivery standard you picked.

To use AI Audio Assistant: 1 Open up a timeline holding unmixed audio. Where the faders start really doesn‘t matter, because Audio Assistant takes care of every fader move while it mixes. 2 To kick off automatic mixing, pick Timeline > AI Tools > Audio Assistant from the Timeline menu, choose the Delivery Standard for your mix in the dropdown menu, and hit the Auto Mix button. 3 The Audio Assistant dialog switches over to show how the mixing is progressing, with a button to cancel.

### Audio Assistant dialog - Delivery Standard

Audio Assistant dialog - Mix Progress

4 Once mixing wraps, you're free to audition the mix and, if you like, refine it further or throw it out entirely.

NOTE: Should a track land in the wrong category, right-click its track header, pick the proper category from the Track Category portion of the contextual menu, then run the Audio Assistant once more.

### Ripple Delete Silence for Selected Clip

On the Edit or Cut page timeline you can analyze a chosen clip and strip out its silences, drawing on the comparable tool over in Fairlight. Pick a clip, choose Clip > Audio Operations > Ripple Delete Silence, and the Ripple Delete Silence dialog opens.

- Threshold: Sets the highest audio signal level (in dB) that counts as silence. Anything sitting below the threshold is regarded as silence and stripped out. Raise the threshold and more audio gets removed.
- Pre Head: Defines how much silence, or pre-roll, sits ahead of each audible passage.
- Post Tail: Defines how much silence, or post-roll, sits after each audible passage.
- Minimum to Trip: Sets the least amount of silence (in frames) that gets

stripped from the chosen timeline clips. Larger numbers preserve more silent stretches in the audio. Smaller numbers yield more strips, though some leftover audio may sound “chopped up” where it cuts off sharply.

- Cross fade audio: Lays a basic crossfade across the surviving audio clips to ease the transition, provided your head and tail settings leave enough room.

### The Ripple Delete Silence dialog

To remove silences from a timeline clip: 1 Pick any clip on a track. 2 Go to Clip > Audio Operations > Ripple Delete Silence. 3 The chosen audio redraws with vertical red stripes that mark where the resulting silences fall and how long they run, based on the values you set in the Remove Silence dialog. 4 Hit Remove. Everything under the red stripes is cut away, and the surviving sections of the clip are ripple deleted together along the timeline.

### The Audio Mixer

On the Edit page the Audio Mixer is a pared-down take on the Fairlight page Mixer, built to hand you a tidy set of graphical controls for dialing in basic track levels (the Edit page has no track-level fader automation), panning stereo audio per track, and muting and soloing tracks as you go. Open it like so: Click the Mixer button over on the Interface toolbar. The Audio Mixer lays out a row of channel strips whose controls map to the Timeline's tracks, and each strip shows as many audio meters as that track has channels. By default a Main 1 channel strip sits at the far right, letting you ride the overall mix level. That said, any subs and mains you create on the Fairlight page show up at the mixer's right edge too.

The Audio Mixer, showing four channel strips that map to the Timeline's four tracks NOTE: Automation can't be recorded on the Edit page. For full mixing controls with complete automation recording, turn to the Fairlight page.

### Audio Mixer Controls

These controls live on every track's channel strip:

- Track Color: Tracks can each carry a distinct color code to keep you organized. The same colors show up in the timeline track header and on the Fairlight page.
- Track Number: This shows the number of the timeline audio track that the channel strip belongs to.
- Track Effects: To open one, double-click a track effect at the top of the fader controls. FX: Brings up the Track Effects controls in the Inspector. EQ: Brings up the Track Equalizer. DY: Brings up the Track Dynamics.
- Pan control: Lets you swing a Mono track's audio between left and right, flip a Stereo track's left and right channels, or work in surround.
- Name: The name of the audio track the strip represents. Should you have renamed the audio tracks in the Timeline, those names show here.
- Solo: Silences every track apart from the ones soloed.
- Mute: Switches that audio track off.
- dB: Reports the current level of that track in decibels.
- Fader: Drag each track's vertical fader with your mouse or other pointing device to

set that track's volume and record automation. Drag upward to raise volume, downward to lower it.

- Audio meters: Sitting to the right of each fader, the audio meters show the playback volume of every channel on that track. Each strip carries its own meters, one per channel that track has been configured for.

### Mute and Solo Tracks For Output

Engaging the Audio Mixer's Mute or Solo controls turns track audio off for playback as well as for output delivery. Be certain you've switched any needed tracks back on before you move to the Deliver page. Mute and solo on tracks can only be changed on the Edit, Cut, and Fairlight pages.

### Displaying Audio Meters

When all you need is a look at your program's levels, you can flip the display over to the “Control Room” audio meters in place of the Mixer. How many audio meters appear depends on the speaker configuration currently active under System Preferences in its Video and Audio I/O panel. To show the Audio Meters: Hit the Mixer button over on the Interface toolbar so the audio panel appears, then pick Meters out of the option menu in the upper-right corner.

### Audio Compound Clips

Audio compound clips are supported in DaVinci Resolve, and you build them the same way as any compound clip: select several audio clips, right-click one, and pick New Compound Clip. Compound clips that include video can now hold several audio items as well. Right-click an audio compound clip, pick Open in Timeline, and when it opens on the Edit or Fairlight page, breadcrumb controls show up under the Timeline so you can step out of the compound clip and return to the master Timeline.

### Opening an audio compound clip

### Audio Playback for Variable Speed Clips

Clips with variable speed effects on them — video or audio — can now be played back with the variable speed audio either pitch-corrected or not. A choice in the Speed menu of the Retime controls decides whether the audio gets pitch-corrected.

### Using Audio Filters

DaVinci Resolve ships with Fairlight FX, a collection of audio plugins specific to DaVinci Resolve that run natively across macOS, Windows, and Linux, delivering high-quality, professional-grade audio effects to every DaVinci Resolve user on every platform. Beyond those, DaVinci Resolve will work with third-party VST audio plugins on Mac OS X and Windows. Under Mac OS X, DaVinci Resolve also handles Audio Unit (AU) audio plugins. Install these effects on your machine and they turn up in the Audio FX panel of the Effects Library. With audio plugins you can treat single audio clips or whole tracks of audio — adding creative touches such as echo or reverb, or addressing mastering needs through noise reduction, compression, or EQ. Ways to apply audio filters to clips on the Edit page:

- To apply an audio filter to a clip: Drag whatever filter you want from the Audio FX panel of the Effects Library onto the Timeline clip you're targeting.
- To apply an audio filter to multiple clips: Pick every clip you intend to treat, then drag whichever filter you want out of the Effects Library's Audio FX panel onto any one of those selected clips.

### Audio filters in the Effects Library

To edit a clip’s audio filters:

- Pick that clip and open the Inspector. Every audio filter on the clip is listed under the Effects panel, within the Audio tab, and that filter's controls show up right inside the Inspector.

Plenty of VST and Audio Unit audio filters come with a bespoke user interface that makes wrangling the filter's controls far easier. You can open these from inside DaVinci Resolve.

### The custom audio filter interface for iZotope RX4

To expose a filter’s custom controls:

- Click the Custom Control button (the one next to the trash can). The custom controls open in a floating window. Close that window when you're done tweaking them.

### The button for opening a filter’s custom control

Ways to work with audio filters inside the Inspector:

- To disable or re-enable a filter: Click the toggle button sitting at the far left of each filter's title bar.
- To remove a filter: Click the Trash Can button.

Once they're on a clip or track, audio filters can be keyframed or automated as well — just like volume and pan settings — letting you build audio effects that evolve over time.

### Installing Audio Filters

Since VST effects don't go to one standard location, you may now and then have to point the application at a directory of VST plugins you've just installed on your machine. For that, the Audio Plugins panel of the Preferences window holds a list where you can manually add or drop VST plugin directories whenever needed.

After you've put one or more VST directories on the list, a second list beneath it shows every audio plugin found inside those directories. Each entry carries a checkbox indicating whether it's enabled at the moment. Any VST plugin that crashes DaVinci Resolve while loading at startup gets disabled automatically. This list lets you see which plugins were disabled — useful for troubleshooting — and re-enable any “blacklisted” ones by switching their checkboxes back on.

### Voice Convert (Studio Version Only)

DaVinci Resolve carries a remarkably advanced AI-driven voice conversion tool that essentially lets you trade one speaking voice for another. Its applications run broad and even somewhat controversial, yet this Voice Convert toolset can prove a hugely valuable asset in a post production. It lets you take a generated voice model that DaVinci Resolve has captured and “drive” that model off another voice recording used as its base. Simple uses include swapping your own voiceover tracks for a voice with greater depth and gravitas, or even flipping the gender of your own voice if that suits the material better. Maybe you recorded in a noisy room and want a clean version instead, using your own voice as the model to stand in for your noisy originals. In tougher cases you might train your own voice convert model on your actor's vocal patterns and use it to alter and replace their earlier voiceover without dragging them back into the booth. It's even possible, finally, to swap an actor's voice out wholesale for another while staying dead-on in sync with the picture. The original's inflection, pitch movement, and emotion all carry over — it merely sounds like a different person. Obviously a tool this powerful demands a degree of responsibility from whoever uses it. Privacy, copyright, and union laws and rules are all unsettled right now where AI generated content is concerned, and the ethics of using it professionally have to be navigated with care.

### The Voice Convert tool

NOTE: Voice Convert is highly processor intensive and needs your system to carry at least 8GB of video ram before it'll switch on, which guards against crashes and instability. Even on a powerful rig, building a Voice Model demands sustained, heavy CPU and GPU effort, so juggling other tasks while it runs can be tough.

### Using Voice Convert

As with most of DaVinci Resolve's AI tools, Voice Convert is quite straightforward to use, since the voice model shoulders all the heavy processing. To use Voice Convert to change one voice to another: 1 Drop the clip or clips whose voice you want to change onto the timeline and select them. 2 Right-click the clip and pick Voice Convert from the context menu, or pick Clip > AI Tools > Voice Convert from the main menu. 3 Pick the track where the new audio should land (this can mean overwriting the original). 4 Pick the file name you'd like the new audio to carry. 5 Pick the Voice Model for the new audio (custom voice models of your own can be built as described below), along with its parameters. 6 Click Render to launch the Voice Convert process.

### Voice Convert analyzing a clip

The Voice Convert dialog now opens and reports the conversion's progress. How long this runs depends on how many clips you chose and their length. Once finished, the new audio lands on the timeline in precisely the same spot as the original (or at the same spot on a different track, if you chose that option). Those new audio clips show up in the Media Pool as well. Just play the timeline back to audition the new voice. To return to the original, right-click a clip and pick Revert to Original Voice from the context menu. TIP: You can drive voices that carry different accents, but Voice Convert usually can't manufacture another accent. As an example, take a voice model of a speaker with a British accent and drive it with an American accent, and you'll get something closer to an American rendering of that British-accented speaker. Speak with a British accent while driving the British voice model, however, and it works nicely.

### Voice Convert Settings

Every voice conversion calls for set up parameters that drive the model.

- Track: Pick which track the new audio belongs on. It defaults to Render in Place, which writes over the original audio.
- File Name: Define the file name of the new audio clip. Type a specific name, or build a naming template out of the metadata variables. The name defaults to ClipName-(Voice Model Name).
- Voice Model: Pick the voice model you want applied to the new audio. A handful of built-in choices ship with DaVinci Resolve, and any you build yourself will appear here too.
- Tight Matching to Source: Tick this box to closely track the source voice's pitch, intonation, and volume variance. Clear it for a looser reading driven by the Pitch Variance tool.
- Pitch Variance: This tool comes alive once the Tight Matching to Source box is cleared. Smaller values yield a flatter, more monotone reading, while larger ones add more pitch movement.
- Pitch Change: This slider builds a deeper voice (negative values) or a higher one (positive values) off the model. Values are given in semitones and adjust in 100 cents (.1 semitone) steps.

### Creating Your Own Voice Models
