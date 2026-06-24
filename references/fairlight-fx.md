# Fairlight Fx (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Fairlight FX

Fairlight FX are audio plugins built specifically for DaVinci Resolve; they run natively across macOS, Windows, and Linux and bring high-quality audio effects with professional features to every DaVinci Resolve user. You will find these plugins on both the Edit and the Fairlight pages, where they hand you a range of options for mending broken audio, building effects, and conjuring spaces. Over on the Fairlight page they fall into one of two groups — Track FX or Audio Effects — according to where they sit in the Fairlight Mixer’s signal path.

To dig deeper into the Fairlight Mixer’s signal path, turn to Chapter 177, “Mixing in the Fairlight Page.” The pages here lay out what these plugins do and how you put them to use.

### Common Controls For All Fairlight FX

Ahead of the controls unique to each Fairlight FX plugin, a handful of controls are shared by every plugin, sitting along the top of each plugin’s custom GUI window.

### Common controls for all Fairlight FX

- Presets: A grouping of controls through which you save and call back presets tied to each individual plugin.

Add Preset button: Press this to store the present settings of the Fairlight FX in use. A dialog box prompts you for a Preset name, after which you click OK. Preset dropdown menu: Every preset belonging to the plugin you have open shows up in this menu. Previous/Next preset buttons: With these you step through presets one at a time, moving up and down the list as you weigh how each sounds.

- A/B Comparison: A group of buttons for weighing two differently tuned takes on the same plugin against each other. The A and B buttons let you keep two distinct sets of adjustments for that plugin and flip between them to hear which sounds better. The arrow button copies the adjustments from one button onto the other, preserving the take you prefer while you go on tinkering.
- Reset: One reset control returns every parameter of the current plugin to its default. With Automation switched on, an automation button shows at the upper right of each plugin, and that effect’s automatable parameters become available through the Plugin dropdown menu for that track.

### Automation activated and available to the Fairlight FX

NOTE: Default may be the preset that loads at first, yet a good number of the plugins ship with presets already in place. Reverb, for one, comes with Cathedral, Concert Hall, and Studio presets built in. These make fine jumping-off points that you can alter, rename, and save to fit your own needs, and any such new presets also turn up in the Preset dropdown menu. TIP: Fairlight FX allow “granular” control tweaks: hold the Option or Shift key while you click into and drag left or right across the numerical value fields of the virtual sliders, whether in a Fairlight FX plugin or the Inspector.

### Track FX

You get at these built-in Fairlight FX plugins through the Track FX section of Audio Track channel strips, or from the Inspector. Should the Track FX section be missing from the Mixer, click the three dots at the Mixer’s upper-right corner and pick Track FX. This category holds the following plugins: Voice Isolation, Dialogue Leveler, Dialogue Separator, Music Remixer, and Ducker. Every one of them sits at a fixed, dedicated insert point within the Track FX section, with Voice Isolation and Dialogue Leveler shown by default. To surface the rest, click those three dots at the Mixer’s upper-right corner and choose each plugin from the “Visible Track FX” submenu down at the bottom. TIP: Track effects will work on stereo-linked groups (stereo-linked tracks).

### The Mixer menu

### Dialogue Leveler

The Dialogue Leveler studies the source material to pick out dialogue, then “rides down” the louder passages, “lifts up” the quieter ones, and pulls down background sounds that are not dialogue. It does this free of the usual “pumping” and other unwelcome artifacts of dynamics processors (compression/limiting), arriving at results like what you would get from painstaking, hand-tuned clip gain moves or from “riding” the track with fader automation.

Often the Dialogue Leveler can “fix and mix” a take captured on a lone boom mic — one where a character sits nearer than another or swings away from the mic — smoothing it so the original relative dynamics survive even as intelligibility and average level climb.

### The Dialogue Leveler plugin

While the Dialogue Leveler runs on an audio track in real time, it will not operate on live audio input. Any mono, stereo, or dual-mono audio track is fair game, yet tracks carrying more than two channels are not supported. Dialogue Leveler controls:

- Dialogue Leveler: Enables or disables the plugin.
- Waveform Processing display: Here you see a scrolling waveform alongside a gray line that marks Dialogue Leveler processing. This display, however, does not appear when you reach for the Dialogue Leveler in the Inspector to treat audio clips on the timeline.
- Preset Menu: The choices this menu offers are these: Allow wider dynamics: The default, suited best to audio whose dynamic swings broadly from loud to soft and whose clip levels run medium to high.

More lift for low levels: Pick this when the source carries a lot of low-level dialogue you would like raised. Lift soft whispery sources: Pick this when the source holds whispered dialogue together with background noise. Optimize moderate levels: Pick this when the source stays at medium levels all the way through.

- Reduce Loud Dialogue: Switch this on and the louder dialogue gets ridden down at its peaks, behaving like a “perfect limiter” with no threshold or time parameters for you to set. Thanks to the “near real-time” design, the analysis runs ahead of the audible playback for the best outcome.
- Lift Soft Dialogue: This control locates and raises low-level dialogue, smoothing out material that runs quieter and more uneven in level. Since the work is centered on dialogue, it tends to leave background sounds alone unless they happen to sound at the same moment as the dialogue.

Of the three, Lift Soft Dialogue tends to prove the handiest, since it brings quieter lines of dialogue up and renders them naturally smooth while leaving background noise untouched.

- Background Reduction: Working from whichever internal preset you picked in the Preset menu, this option eases background noise away gently.
- Output Gain: Set the output level with this control either by clicking and dragging it or by typing a figure into the numeric field. Its Output Gain range spans 0.0 to +6.0 dB.

TIP: Ahead of running the Dialogue Leveler on a track, it pays to normalize the audio so you have an ideal baseline level for the default “Allow wider dynamics” preset. For more on normalizing audio, see Chapter 176, “The Fairlight Inspector.”

### Dialogue Separator (Studio Version Only)

Drawing on DaVinci Neural Engine AI, Dialogue Separator hands you separate command over the level of the dialogue, the background sounds, and the reverberant field or ambient room sound (“ambience”).

### The Dialogue Separator plugin

The Dialogue Separator shines when, for instance, a source file boasts a lovely roomy sound yet has music or crowd noise lurking behind it. Here you can rebalance the audio to dial the background sounds back, or tweak the room sound so the dialogue reads more clearly. Another scenario: someone walks toward the camera in a roomy space while talking. You might lean on automation to rebalance the audio so the ambient room sound grows steadily “drier” as they near, all while the background stays put. For now the Dialogue Separator handles mono only. A stereo source has to be split into dual-mono, with each mono track treated on its own.

### Ducker

With this plugin you take the audible signal off one track or several and use it to pull down the level of another. Creative uses abound, but the classic “ducking” move is to automatically drop a music or sound effects bed so dialogue or a VO track sits more clearly out front in the mix — and it does so without compressing the incoming signals. Dial the Ducker interface in correctly, or work through the Inspector’s Audio tab, and your audio tracks come close to “mixing themselves.” In a plain case, the Ducker reads the level swings of one incoming dialogue or VO track to turn down the sound effects bed of a noisy freeway. In a trickier one — a scene where three characters chat beside that same noisy freeway — a lone Ducker plugin can take each dialogue track’s level swings and use them to tame the traffic noise. Fed by only a single input source (Dialogue 1), the Ducker would respond solely when the first character talks. This new feature, though, lets you bring the other two dialogue tracks (Dialogue 2 and Dialogue 3) on board as input sources for knocking the traffic noise back.

### The Ducker plugin

### Using the Ducker

Picking up the examples above: 1 Pick the target track you mean to attenuate (the Freeway Traffic track) and open the Ducker. 2 Open the Source dropdown and set Dialogue 1 as the input source.

- For extra input sources, Command-click the remaining track names — here that means Dialogue2 and Dialogue3.
- Run a portion of your sequence and tune the duck level along with the other controls to taste.

### Adding Input Sources via the Inspector

Should you rather stay inside the Inspector: 1 Pick the Freeway Traffic track, confirm the Ducker is on, and open the Inspector’s Audio tab. 2 Hit the plus sign beside the Source 1 dropdown that holds Dialogue 1 to spawn a dropdown for Source 2, and pick Dialogue2 off the list. 3 Hit the plus sign beside the Source 2 dropdown to spawn a dropdown for Source 3, and pick Dialogue3 off the list.

### Adding Ducker input sources in the Inspector

### Ducker Controls

- Duck Amount: This sets how much the target track’s level drops, measured in dB, with a default value of 2.7 dB. As a rule, somewhere between 2.0 dB and 5.0 dB sounds best.
- Lookahead: Sets the lookahead time in milliseconds, defaulting to 15ms. Lookahead lets the Ducker begin pulling the destination track down before the source track even becomes audible. Raise the value and the Ducker “pre-anticipates” the source track more. If you want the sound to start dropping before a line of dialogue or VO arrives, try higher values, though the default usually does the trick.
- Rise Time: This fixes how many milliseconds the Ducker takes to hit the reduction set by the Duck Amount. By default it is 10 milliseconds, fine for most cases. Longer Rise Times can help when Duck Amount values run high and the source track has wider gaps.
- Hold: This parameter governs how long the target signal stays attenuated. Its default is 150ms.
- Recovery Time: This figure tells how fast the target signal climbs back to its prior level

once attenuation lifts. The default sits at 750ms, but a well-chosen Recovery time is key to ducking that sounds natural, so test a range of values to land on the best.

### Ducker Graph Display

In this area a gray line stands for the incoming signal, set against the Ducker’s action drawn in yellow. Wherever the yellow line dips, the target track is being attenuated according to the Duck Amount working together with the other parameters.

### Music Remixer (Studio Version Only)

Built on DaVinci Neural Engine AI, this plugin pulls music apart into separate stems — Vocals, Drums, Bass, Guitar, and “Other” (“everything else”) — so you can rebalance or remix the track to creative ends. The level controls let you set each stem’s volume, while the Mute buttons drop stems out or fold them back into your mix. You might, for instance, want to strip out or lower a vocal that fights with a featured piece of dialogue.

### The Music Remixer plugin

### Voice Isolation (Studio Version Only)

Powered by an AI model schooled on every sort of human voice — male or female, young or old — Voice Isolation lets you strip loud, unwanted sounds out of existing voice recordings entirely, and to striking effect.

### The Voice Isolation plugin

All manner of background noise can be cleared away — air conditioners and fans, jackhammers, the din of a restaurant, music sounding under a featured piece of dialogue, and beyond.

The Amount control balances the blend of the original source against the isolated voice. Set it to 50 and the two sit at roughly equal weight. Settings from 70 to 80 tend to give natural results while still isolating the source hard. Voice Isolation will run on an audio track in real time, but not on live audio input; it accepts any mono, stereo, or dual-mono audio track, though tracks of more than two channels lie outside what it supports.

### Insert Effects

### Ambisonics Meter

Drop this Fairlight FX plugin onto an Ambisonics track or bus and it paints a graphic picture of your Ambisonic sound field. A click on the three dots at the upper right opens an options menu where you choose your metering style — either “power” (Power Map) or “Sonar.” Whichever you pick, the meter conveys how intense the sound is and where it currently sits in the Viewer.

### Ambisonics meter - Power Map view

### Ambisonics meter - Sonar view

### Chain FX

With Fairlight Chain FX you can string together as many as six Fairlight FX, or compatible Audio Units or VST effects plugins, and steer the whole lot from one control.

### Chain FX plugin

### Master Controls

Along the upper part of the interface, the Chain FX window carries the controls below.

- Preset Menu: The spot where Chain FX settings get saved and recalled.
- To store a Chain FX combination as a preset, click the Plus button left of the Preset menu; to bring one back, open the menu and pick it.
- You can also page through the presets by clicking the left or right “arrow” ( < or >) sitting to the right of the drop-down menu.
- To make a Chain FX configuration the default, choose Set as Default from the Options menu (three dots) over in the upper-right corner, just right of the Reset button.
- For a quicker workflow, Chain FX presets copy and paste across to other instances of the plugin.

TIP: Another route to a Chain FX preset is to click the plus sign on an insert slot and then choose Chain FX.

- Compare Buttons (A and B): A quick way to pit two different Chain FX settings against one another.
- Build a Chain FX setting or load a preset while button A glows red, then click button

B and craft a different setting or load a different preset; from there, clicking between the buttons jumps you swiftly from one to the other.

- Bypass Button: Toggles the Fairlight EQ on or off.
- Reset Button: A click on the round Reset icon at the EQ’s upper-right corner reverses the last action you made in the plugin interface.

### Sidechain (SC) Section

- On Button: A click here switches on the plugin’s Sidechain section, then prompts you, by way of the Source drop-down menu, to pick an audio track or buss to serve as the input source.

To read more about Sidechaining, see Chapter 180, “Audio Effects.”

- Listen Button: Click this to monitor the incoming audio signal by itself — useful for confirming that the right audio signal is reaching the Sidechain module.
- Source: This button chooses the track or buss that the incoming audio signal comes from.

### Building an FX Chain

To assemble an effect chain inside a Chain FX instance: 1 On a Mixer Channel Strip, click a vacant Effects slot, then travel to Multi Effect > Fairlight FX > Chain FX to bring up a blank Chain FX plugin. Make sure the plugin is active. 2 In the Plugin Chain section, click the plus sign and choose an effect off the menu to add your first Fairlight FX or compatible third-party plugin. With it active, either recall a saved preset or work the controls until the settings are where you want them. 3 Do that step over and over until you have an FX chain of up to six plugins that suits you. 4 Save the resulting plugin combination, just as it stands, as a Chain FX Preset by clicking the Plus button left of the Preset menu. TIP: Clicking any plugin’s name in the effect chain pops open that plugin’s own window.

A fresh effects chain can also be started from any compatible plugin — a compressor, say — by clicking the three dots at the plugin window’s upper-right corner and choosing Add to Plugin Chain off the menu.

### Add to Plugin Chain menu option

Doing so spins up a new Chain FX instance with the plugin you began from (the compressor, here) already dropped into the first slot.

- In the mixer channel insert, the Chain FX plugin takes the compressor’s place.
- To pile on more plugins, click the plus sign in the Plugin Chain

section and choose a plugin off the menu.

### Chorus

A time-honored Chorus effect, it stacks voices or sounds against modulated copies of themselves to lend harmonic interest in assorted ways. An animated graph reflects what happens as you move this plugin’s Modulation parameters, showing you the warble or tremolo about to be layered onto the signal as you tweak.

### The Chorus Fairlight FX

Chorus has the following controls:

- Bypass: Flips this plugin on or off.
- Input Format: (Shows up only when Chorus sits on a multi-channel track.) Decides

the way several channels feed into the Chorus. Stereo keeps the Left and Right channels apart. Mono folds Left and Right onto both channels. Left routes in the Left channel alone, while Right routes in the Right channel alone.

- Delay: The gap, in delay, separating the dry sound from the Chorus effect. Delay Time: How long the Chorus delay lines run. Separation: The spacing in time between the delay voices. Expansion: Dictates L/R length differences along with the phase offset of the modulators.
- Modulation: This bank of controls shapes, in several ways, the low frequency oscillator (LFO) behind the chorus effect’s tremolo. Waveform: Names the shape of the LFO that drives the Chorus rate and so colors the timing of the oscillations. The oscillator gives you six shapes to pick from:

Sine (Smooth oscillations)

Saw2 (Jerky oscillations)

Triangle (Sudden oscillations)

Square (Hard stops between oscillations)

Saw1 (Jerky oscillations)

Random (Randomly variable oscillations)

Frequency: Rate of the LFO steering the Chorus. Dial it low for a warble, high for a tremolo.

Pitch: How much frequency modulation there is, which bends the Chorus pitch. Level: Depth of level modulation, governing the “length” of the slice of Chorus folded into the sound. At low settings only the very onset of the Chorus effect comes through; at high ones a fuller Chorus warble or tremolo emerges.

- Feedback: A signal routed back into the Chorus Delay Line Amount (%): The share of signal sent back to the Chorus Delay Line. The value may be positive or negative, defaulting to 0 (no effect). Push it up and more of the Chorus effect joins the signal; pull it down and more of the inverted Chorus effect joins instead. Near 0 only a faint trace of Chorus reaches the audio, whereas farther from 0 (topping out at +/- 99) a steadily stronger Chorus comes through. Blend (%): The amount of feedback that spills into the opposite channel (Stereo mode only).
- Output: The controls that shape this plugin’s final output. Dry/Wet (%): A percentage blend of the “dry” or original signal against the “wet” or processed one; 0 is fully dry, 100% fully wet. Output Level (dB): Sets the overall output level of the treated sound.

### De-Esser

A repair plugin aimed at dialog. The De-Esser is a purpose-built filter meant to tame harsh sibilance — hissing “s” sounds or sharp “ts” sounds — within dialogue or vocals. A graph points out which slice of the signal the controls are tuned to act on, and reduction and output meters reveal which part of the signal is affected and at what level it leaves the plugin.

### The De-Esser Fairlight FX

The De-Esser has the following controls:

- Bypass: Switches the plugin on and off.
- Listen to Ess Only: With this top-right checkbox you hear nothing but the ess being

stripped out — a great help in judging whether too much signal is going or whether more ess attenuation is warranted.

- Frequency Range: A pair of controls homes in on the “s” frequency of a given speaker. Target Frequency: A knob that zeroes in on the frequency of the troublesome sibilance, which usually falls between 5 - 8kHz. Range: flips the De-Esser’s operating mode; reading top to bottom, the three choices are Narrow Band, Wide Band, and All High Frequency, the last of which treats every bit of audio above the source frequency.
- Amount: Sets how much de-essing gets applied.
- Reaction Time: Sets how abruptly the de-essing comes on, offering three options.

Slow: Like a slow attack. Medium: Like a medium attack. Fast: Like a fast attack.

### De-Hummer

A repair plugin you can bring to bear on any recording. It wipes out hum noise, the kind that frequently arises when audio gear picks up electrical interference through faulty cabling or grounding. As a rule, 50 or 60 cycle hum is a harmonic noise built from a fundamental frequency plus partial harmonics that begin at twice that fundamental. A graph reveals the frequency and harmonics under fire as you work this plugin’s controls.

### The De-Hummer Fairlight FX

De-Hummer has the following controls:

- Bypass: Turns this plugin off or back on.
- Listen to Hum only: This top-right checkbox lets you monitor solely the hum being

taken out — handy for gauging whether too much signal is leaving or whether further hum attenuation is needed.

- Frequency: Targets the source’s fundamental frequency. A knob handles a free-form frequency choice, while radio buttons offer the common 50Hz/60Hz electrical-mains values that are the usual cause of hum.
- Amount: Sets how much De-Hum extraction is applied.
- Slope: Tunes the balance of fundamental frequency against partial harmonics, and shifting it

makes it possible to go after various kinds of hum. A value of 0, for example, tilts hum extraction toward the fundamental frequency, 0.5 pulls all harmonics out evenly (up to 4), and 1.0 zeroes in on the higher-frequency partials.

### Delay

An effects plugin. An all-purpose stereo delay effect that covers jobs from track doubling to early reflection generation to plain harmonic enhancement. It works in stereo or mono, depending on the track it lands on. A graph charts the timing and strength of the echoes this plugin produces on each channel, while an Output meter reports the output level of the resulting signal.

### The Delay Fairlight FX

Delay has the following controls:

- Bypass: Toggles the plugin between on and off.
- Input Format: (Appears only once Delay is placed on a multi-channel track.) Governs

the way several channels feed into the delay. Stereo holds the Left and Right channels separate. Mono blends Left and Right onto both channels. Left brings in the Left channel by itself, and Right brings in the Right channel by itself.

- Filters: Reshapes how much of each frequency makes it into the delay effect. Should the Delay plugin land on a Mono Channel, the Left and Right sections give way to one combined “Delay” section.

Low Cut (Hz): Acts as a global High Pass filter. High Cut (Hz): Acts as a global Low Pass filter.
