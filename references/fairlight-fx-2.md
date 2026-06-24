# Fairlight Fx (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Delay: Tunes how the delay is timed. Left/Right Delay (ms): The per-channel delay duration. Left/Right Feedback (%): What percentage of the Left or Right channel routes back into itself. Going negative makes that feedback percentage arrive phase-reversed relative to the source.
- Feedback: A cluster of settings that govern how much channels bleed into each other. High Ratio: Tunes the cutoff of a damping filter acting on the fed-back signal. Stereo Blend: Sets how much of each side's feedback crosses over to drive the opposite channel. Inserting the Delay plugin on a Mono channel hides the Stereo Blend control entirely.
- Output: A group of settings governing what this plugin ultimately sends out. Dry/Wet (%): A percentage that balances the mix between the untouched “dry” source and the processed “wet” result. At 0 the output is purely dry; at 100% it is purely wet. Output Level (dB): Raises or lowers the overall level coming out of the processed sound.

### Dialogue Processor

Within one plugin, the Dialogue Processor links six routine audio-treatment stages in series, with each stage geared toward the kinds of fixes that make recorded dialog sound better. Its dedicated De-Rumble, De-Pop, De-Ess, Comp(ressor), Expander, and Excite sections each expose a pared-down control set aimed at the typical corrections a clean-sounding dialogue track tends to need.

### The Dialogue Processor plugin

- De-Rumble: This stage is a high pass filter that lets you clear out subsonic rumble (the subharmonic low end) from a vocal microphone feed. For the bulk of condenser mics, 40 or 50Hz is a dependable setting. Pushing the value upward begins eating into legitimate low frequencies of the source, though that can occasionally be a handy creative trick.

Frequency: Places the high-pass filter anywhere from 40Hz to 235Hz.

- De-Pop: Governs the center frequency of a purpose-built filter that strips out vocal “popping,” or plosives — the bursts that happen when a speaker is right up on a microphone capsule on-axis.

Frequency: Places the filter anywhere from 50Hz to 200Hz. Amount: Dials in how strongly the filter acts on the signal; smaller numbers do less and larger numbers do more. A meter beside the amount knob displays the degree to which the signal is being treated.

- De-Ess: Fixes the center of a dedicated bandpass filter that tames vocal “Esses,” which tend to stand out too much because of sibilance. Removing those esses lets you push up the average level and add brightness to a vocal without harshness, since our hearing reacts strongly to excessive sibilance. For both male and female voices, 6 to 7 kHz is usually the sweet spot.

Frequency: Places the filter anywhere from 700Hz to 9000Hz. Amount: Dials in how strongly the filter acts on the signal; smaller numbers do less and larger numbers do more. A meter beside the amount knob displays the degree to which the signal is being treated.

- Compressor: Narrows a signal’s dynamic range by shrinking the gap in level between its loudest and softest moments. By doing so it can lift the whole signal upward, gaining without clipping and therefore sounding louder. It is a common way to bring voices forward in a mix and to even out tracks whose dynamic range is too wide for where they sit.

Threshold (dB): Marks the point, between –40dB and –8dB, where the signal begins to be affected. Amount: Dials in how much compression hits the signal; smaller numbers do less and larger numbers do more. A meter beside the amount knob displays the degree to which the signal is being treated. Fast/Slow: Chooses whether the processing engages quickly or slowly.

- Expander: Widens volume contrasts by pulling down the quieter portions of a signal relative to its louder ones, which is handy for suppressing noise while opening up a signal’s dynamic range.

Threshold (dB): Marks the point, between –40dB and –8dB, where the signal begins to be affected. Range: How far, in dB, the level drops as the expander pushes the softer passages down. Fast/Slow: Chooses whether the processing engages quickly or slowly.

- Excite: Manufactures extra high-frequency content on top of a source signal through several methods. Applied gently, it lends presence to sounds that might otherwise feel dull, with no need to reach for EQ.

Amount: Dials in how much the exciter acts on the signal; smaller numbers do less and larger numbers do more. A meter beside the amount knob displays the degree to which the signal is being treated. Female/Male: Biases the exciter’s behavior toward either a male or a female voice.

### Dialogue Leveler

The Dialogue Leveler studies the source to locate speech, then proceeds to “ride down” the louder stretches, “lift up” the quieter ones, and pull down non-dialogue background. It achieves this without the telltale “pumping” of a normal dynamics processor (compression/limiting) or other obvious artifacts, landing close to what you would get from meticulous manual clip-gain work or from carefully “riding” a fader as automation. It can frequently “fix and mix” a single-boom-mic recording in which one actor sits nearer than another or swings off-axis at points, evening it out so the original relative dynamics survive while clarity and average level both climb. You can run it on track audio as it plays, though not on a live input, and it accepts any mono or stereo (or multi-mono) track — but tracks wider than stereo are not supported.

### The Dialogue Leveler plugin

The controls offered by Dialogue Leveler are:

- Dialogue Leveler: Switches the Dialogue Leveler processing on or off.
- Waveform Processing display: Presents a scrolling waveform readout and marks the Dialogue Leveler

activity with a gray line. Bear in mind, though, that this readout is absent from the clip-based variant of Dialogue Leveler.

- Preset Menu: The choices available from the preset menu are:

Allow wider dynamics: The default pick, suited to material whose loud-to-soft swings are broad and whose clip levels run medium to high. More lift for low levels: Reach for this when the source carries a lot of quiet dialogue you would like to bring up. Lift soft whispery sources: Use this for material that combines whispered speech with background noise. Optimize moderate levels: Choose this when the whole source sits at moderate levels.

- Reduce Loud Dialogue: With this on, the louder speech is ridden down at its peaks, behaving rather like a “perfect limiter” that frees you from setting any threshold or time constants. Because of its “near real time” nature, the analysis runs ahead of what you hear so the result is optimal.
- Lift Soft Dialogue: With this on, it locates quiet speech and raises and smooths out passages that are softer and more uneven, yet because its focus stays on dialogue it generally leaves background sounds alone (unless they coincide with the speech itself). In most cases this is the handiest of the three, since it pulls faint lines of dialogue up into audibility and natural smoothness without lifting background noise.
- Background Reduction: With this on, it trims background sounds by concentrating on the dialogue and easing the rest out according to the built-in presets (Preset menu).
- Output Gain: Set the Output Gain either by dragging on the Output Gain control or by typing a number into the field (the Output Gain control runs in dB across a 0 to +6 dB range at .1dB resolution).

### Distortion

An effects plugin. It generates audio distortion handy for sound design and effects work, spanning everything from gentle harmonic distortion that mimics a signal passing through crude or broken electronics (think poor speakers, old telephones, or outdated recording gear) up to imitating an overdriven feed undergoing varying degrees of hard clipping (picture someone shouting into a cheap bullhorn, megaphone, or PA rig). A soft tube emulation sits in the output stage. As you tweak the Distortion parameters, an animated graph updates to picture the harmonic distortion, waveshaping, and clipping about to reshape the signal. Input and Output meters reveal what is happening to the levels.

### The Distortion Fairlight FX

The controls Distortion offers are:

- Bypass: Flips this plugin on or off.
- Filters: A pair of filters lets you mimic gear that only reproduces a narrow band of frequencies. LF Cut: Shapes the distortion at the low end. HF Cut: Shapes the distortion at the high end.
- Distortion: Three control groups let you dial in the character and severity of distortion you are after. Mode buttons: Toggle which distortion mode is running. The left one, Distortion, yields harmonic distortion. The right one, Destroy, is a harsher polynomial waveshaper. Distortion: Sets how much distortion lands on the signal, with bigger numbers distorting harder. Ceiling: Sets the input level at which clipping kicks in.
- Output: A group of settings governing what this plugin finally sends out. Dry/Wet (%): A percentage that balances the mix of the untouched “dry” source against the processed “wet” result. At 0 it is fully dry; at 100% it is fully wet. Output Level (dB): Raises or lowers the overall level of the affected sound. Auto Level button: Automatically compensates for the gain the distortion adds to the signal. Leaving it on keeps the signal from jumping up wildly and unexpectedly, while switching it off lets you chase whatever you want — including a heavy dose of distortion.

### Echo

An effects plugin. A traditional Echo effect that recreates sound reflections arriving some delay after the direct sound reaches the ear. Whether it runs in stereo or mono follows the track you place it on. A graph plots the timing and strength of the echoes the plugin produces per channel, and an Output meter shows the output level of the resulting signal.

### The stereo Echo Fairlight FX

The controls Echo offers are:

- Bypass: Flips this plugin on or off.
- Input Format: (Shows up only when Echo sits on a multi-channel track.) Decides how the

several channels feed into the echo. Stereo keeps the Left and Right channels apart. Mono folds Left and Right into both channels. Left feeds in just the Left channel, while Right feeds in just the Right channel.

- Filter: Changes which proportion of frequencies make it into the delay effect. Placing the Delay plugin on a Mono Channel collapses the Left and Right sections into one “Delay” section. Low Cut (Hz): Acts as a High Pass filter across the whole signal. High Cut (Hz): Acts as a Low Pass filter across the whole signal. Feedback: Tunes the cutoff of a damping filter on the fed-back signal.
- Left Channel: Settings that act on the Left Channel’s delay on their own. Placing the Echo plugin on a Mono Channel collapses the Left Channel and Right Channel sections into one “Echo” section carrying only the Delay Time, Feedback Delay, and Feedback controls. Delay Time: The Left Channel’s overall Delay time. Feedback Delay: The Left Channel’s Echo Delay time. Feedback: How much of the Left channel feeds back into itself, as a percentage. L > R Feedback: What percentage of the Left feedback signal crosses over into the Right Channel.
- Right Channel: Settings that act on the Right Channel’s delay on their own. Delay Time: The Right Channel’s overall Delay time. Feedback Delay: The Right Channel’s Echo Delay time. Feedback: How much of the Right channel feeds back into itself, as a percentage. R > L Feedback: What percentage of the Right feedback signal crosses over into the Left Channel.
- Output: A group of settings governing what this plugin finally sends out. Dry/Wet (%): A percentage that balances the mix of the untouched “dry” source against the processed “wet” result. At 0 it is fully dry; at 100% it is fully wet. Output Level (dB): Raises or lowers the overall level of the affected sound.

### EQ ‑ Fairlight EQ

The Fairlight EQ is a 6-band parametric equalizer offering controls to lift or cut various frequencies. Every band carries controls for its filter type — Bell, Lo-Shelf, Hi-Shelf, Notch — plus Frequency, Gain, and Q-factor (how sharp the band is).

### Fairlight EQ plugin

### Master Controls

Along the top portion of the interface, the Equalizer window holds these controls

- Preset Menu: Store your EQ settings as presets by hitting the Plus button just left of the Preset menu, then bring them back later by opening the menu and picking one. You can likewise step through the presets with the left or right “arrow” (< or >) sitting to the right of the drop-down.

TIP: Make an EQ setting the default by choosing Set as Default from the Options menu (three dots) at the upper-right corner, right of the Reset button. Fairlight EQ Presets copy and paste between separate instances of the plugin to speed up your workflow.

- Compare Buttons (A and B): These let you flip rapidly between two distinct EQ settings. Build an EQ setting or load a preset while button A glows red, then switch to button B and build or pick a different one; clicking back and forth between the buttons swaps instantly from one to the other.
- Bypass Button: Turns the Fairlight EQ on and off.
- Reset Button: Hitting the round Reset icon at the EQ’s upper-right corner reverses

whatever you most recently did inside the plugin interface.

### EQ Graph

This graph plots the present EQ curve, with a handle standing in for each EQ band. Even though each handle's place on the graph follows the parameter settings shown in the plugin interface, you can grab any numbered handle and drag it to lift or cut the frequency range that an active band controls, according to whichever equalization filter is currently chosen.

### Fairlight EQ graphical display

### Bands 1 and 6

With these parameters you tune the bottom-most and top-most frequencies of the audio. Band enable button: Turns each EQ band on or off. Band filter type: Bands 1 and 6 can each cycle through five filtering options, listed here:

- On Band 1, the choices run (top to bottom): Lo-Shelf, Notch, Hi-Shelf, and Hi-Pass.
- On Band 6, they run (top to bottom): Lo-Pass, Bell, Notch, and Hi-Shelf. Frequency: Sets where the center of the EQ adjustment sits.

Q Factor: This parameter governs how wide a band of frequencies is touched and shows up only when Bell is chosen. Smaller numbers span a broader frequency band; larger numbers tighten it. It has no effect on the audio whenever the Hi-Pass, Lo-Shelf, or Hi‑Shelf filter is active.

### Bands 2 through 5

The controls and parameters carried by these bands are: Band enable button: Switches each EQ band on or off. Band filter type: Each of these Bands offers four filtering options (top to bottom): Lo-Shelf, Bell, Notch, and Hi-Shelf. Frequency: Sets where the center of the EQ adjustment sits. Gain: Negative numbers cut the chosen frequency while positive numbers lift it. It has no effect on the audio when the Notch filter is active. Q Factor: This parameter surfaces once Bell is picked. It governs how wide a band of frequencies is touched. Smaller numbers span a broader frequency band; larger numbers tighten it. It has no effect on the audio whenever the Lo-Shelf, Notch, or Hi-Shelf filter is active.

### Flanger

An effect plugin that delivers that instantly recognizable Flanger sound, a throwback to the era of paired tape machines where a small periodic delay on one of them produced flanging as the two drifted back into sync. People reach for it to lend a warbling harmonic flavor to a signal in all sorts of ways. While you adjust the Modulation parameters, an animated graph refreshes to picture the warble being layered onto the signal.

### The Flanger Fairlight FX

The controls the Flanger offers are:

- Bypass: Flips this plugin on or off.
- Input mode: (Appears only when the Flanger sits on a multi-channel track.) Decides

how the several channels feed into the Flanger. Stereo keeps the Left and Right channels apart. Mono folds Left and Right into both channels. Left feeds in just the Left channel, while Right feeds in just the Right channel.

- Modulation: A low frequency oscillator (LFO) that powers the Flanger effect.

Waveform (Hz): Sets the LFO shape that modulates how fast the Flanger sweeps. There are three options: Sine, which eases the rate up and down smoothly; Triangle, whose rate shifts more abruptly; and Sawtooth, which jumps the rate suddenly. It governs the timing of the warble layered onto the sound. Rate: The LFO speed, which drives how quickly that warble moves. Small rate numbers yield a slow warble, while large ones turn it into more of a buzz. Depth: Governs the “length” of the warble added to the sound. Small numbers add only the warble's leading edge; large ones add a more fully formed warble.

- Width: Holds a single parameter, Expansion, which sets the length difference between the Left/Right channels along with the phase offset of the modulators.
- Feedback: These controls largely decide how extreme the Flanging effect becomes.

Amount (%): What percentage of the signal routes back into the Delay Line. The value may be positive or negative, defaulting to 0 (no effect). Raising it pours more of the Flange effect into the signal; lowering it pours in more of the inverted Flange effect. At values near 0, you hear only a faint phase shift in the audio, but the farther the value moves from 0 (topping out at +/- 99), the more a steadily growing warble emerges. Which warble you get hinges on the Modulation controls. High Ratio: Sets how the echo fades out over time.

- Output: A group of settings governing what this plugin finally sends out.

Dry/Wet (%): A percentage that balances the mix of the untouched “dry” source against the processed “wet” result. At 0 it is fully dry; at 100% it is fully wet. Output Level (dB): Raises or lowers the overall level of the affected sound.

### Foley Sampler

The Foley Sampler is a sampler built into the application that simplifies dropping in sound effects you intend to trigger from a keyboard, pad, or any other MIDI performance device hooked up to your computer, so you can place timed effects in sync with what is happening on screen. Its whole design is to streamline capturing performed audio cues onto the current track that hosts the sampler.

### Setting Up the Foley Sampler

Capturing samples through a MIDI controller with the Foley Sampler is straightforward. 1 Make an audio track to hold your sound effects or instrument recording. 2 Drop the Foley Sampler onto the track header to bind it to that track. The Foley Sampler window opens on its own. Because the Fairlight page recognizes this as an instrument with no plugin inputs, the effect gets patched straight to that track’s input, set to record. 3 When a MIDI controller of any sort is connected and correctly set up, it shows up in the MIDI dropdown at the top-right of the Foley Sampler window (beside the Keyboard button). Pick your device there, and the Keyboard button lights up to confirm it is on. The Foley Sampler is now usable, yet out of the box it holds no samples to play. Adding sound effects comes next.

### Adding Sound Effects

There are several routes for loading prerecorded sound effects or instruments into the Foley Sampler:

- From the file system, drag a supported-format audio file and drop it onto the Foley Sampler window
- Pull a sound effect out of the Sound Library and drop it on the Foley Sampler window
- Open the Option menu of the Foley Sampler window and bring sounds in from your connected drives.

As soon as some sound effect is loaded, it maps itself to the four highest keys of your instrument, beginning at C2. Hitting a key or pad on your controller fires that sound. Click the Sample button atop the Sound panel to view the sound’s waveform. For this walkthrough, we have a run of continuous footsteps recorded back to back to work with.

### A footsteps recording loaded into the Foley Sampler

### Splitting Sound Effects

A frequent practice is to grab pre-recorded library effects — a string of recorded footsteps, cloth rustles, punches, or similar “foleyed” recordings — so you can trigger variations of one repetitive effect in time with on-screen action. The Foley Sampler makes that simple. 1 With a sound effect already loaded, open the Foley Sampler window’s Option menu and pick Split Sample; this carves the current sample into slices by analyzing its noise floor and parks each slice on a group of keys or pads on your chosen MIDI device. Picking up the earlier example, each footstep is now split off onto its own key.

2 To fine-tune the timing of any split-off slice, click the assignment text above the keyboard along the bottom of the window to bring that slice up in the Sample view. 3 Use the Range Start and Range End parameters to take in as much or as little of that slice as you wish to play. 4 Should you want a sample to loop while a note is held, switch on the Loop button and then set the Loop Start and Loop End parameters to decide how much of each slice loops. 5 To clear out slices you don’t need, select one you dislike and press Shift-Delete to wipe it from the virtual keyboard.

One isolated slice from that footsteps recording once the Foley Sampler has split it, its effect range now tweaked Assigning Sound Effects Manually The first sound effects you load into the Foley Sampler land automatically across a run of notes. Every further effect you load drops onto the next run of notes off to the right. Once every note is taken, new effects push all earlier assignments leftward. You may also assign loaded effects by hand. That comes in handy when you want to load an assortment of different effects in one go (say, a mix of punch sounds, human grunts, and cloth rustles for a fight scene) and drop them onto notes you specify. 1 Bring in the sound effect you intend to place. 2 Hit the Mapping button to change which span of notes it covers. 3 Use the Low and High parameters to pick a note range for the chosen sound.

4 Where needed, you also have the option of tuning the pitch of particular sound effects.

Using the Mapping controls to pin a sound onto a specific group of notes Adjusting Sound Effects To take a sample or slice further, select it above the virtual keyboard and reach for the Level panel controls to shape the dynamics of playback, or the Filter panel controls to EQ the sound. TIP: When a sample or slice is set to loop, hold the Control key and click a key on the virtual keyboard to kick off looping, letting you hear the adjustments as you dial them in.

### Playing and Recording Sound Effects
