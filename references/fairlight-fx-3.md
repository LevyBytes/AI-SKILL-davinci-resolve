# Fairlight Fx (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

After the Foley Sampler is configured with effects you can trigger from a MIDI controller, capturing those effects takes only a few steps. 1 Confirm that the “Save clips to” field, found in the Capture and Playback panel of the Project Settings, points at the storage volume you intend to record onto — use the Browse button to redirect it if needed. 2 In the track header of the audio track that hosts the Foley Sampler, press the R button so the track enters Record Enable mode. 3 In the Fairlight toolbar, press the Record button. 4 As recording proceeds, trigger your sounds in time with the on-screen image by pressing the keys or pads of the MIDI controller, then press Stop once you have finished. The result is a captured clip holding the effects you performed, aligned to the picture. Should the timing drift slightly, the Elastic Wave audio retiming tools let you nudge things back into alignment rather than recording the whole pass again.

A freshly captured audio clip, produced by recording the sounds you triggered through the Foley Sampler

### Frequency Analyzer

Presenting your clips or tracks as either a Spectrum or Waterfall graph, the Frequency Analyzer gives you a visual readout that exposes potential tonal problems and helps you refine the sound. Using the Mode menu at the top right, you can inspect the entire frequency range of the signal (the default) or zoom into Low, Midrange, or High frequency regions.

### Frequency Analyzer Spectrum view

### Frequency Analyzer plugin Waterfall view

### Gain

Use this plugin when you need to raise or lower an audio signal’s loudness by an exact decibel amount. It comes in handy across many situations — for instance, quickly tweaking the overall level of a track that already carries a lot of mixer or plugin automation. Use this plugin when you need to raise or lower an audio signal’s loudness by an exact decibel amount. It comes in handy across many situations — for instance, quickly tweaking the overall level of a track that already carries a lot of mixer or plugin automation.

### The Fairlight Gain plugin

### LFE Filter

This is a low-pass filter you can place on a FlexBus or Main carrying a surround sound format, used to route low-frequency content to an LFE channel within a surround mix. Anything above the frequency you choose is held back from the audio fed to a sub-woofer on the LFE channel. The result is cleaner playback, since superfluous content never reaches the sub-woofer. A Frequency control selects the low band you want passed through, and a Trim control sets the level of the resulting LFE channel. When the source is multi-channel yet lacks an LFE channel — a 5.0 layout, for example — the plugin simply has no effect.

### The LFE plugin

### Limiter

By detecting and taming peaks, the Limiter lets you push the overall level higher without clipping, while compressing the dynamic range much as a compressor would. As a genuine true peak limiter, it can look 64 samples ahead of the incoming signal, which yields an exceptionally smooth limiting action. Adjust the incoming level with the Input control, and use the Threshold and Release to govern when limiting kicks in and how long it lasts. The graph highlights the portions of the signal currently being acted upon.

### The Limiter plugin

### Limiter controls

- Bypass: Toggles this plugin on and off.
- Input Meter: Shows the level of the incoming signal.
- Input Level: Sets the level of the signal coming in, spanning from -18 dB up to +18 dB.

Switching on the Soft button makes the limiter apply a more gradual attack.

- Ceiling: Fixes the point (level) above which the Limiter begins pulling the incoming signal down.

At a setting of -24 dB, everything louder than that point is limited; at 0 dB, nothing is limited.

- Release: Governs the duration of the limiting (signal reduction). Dialing this

control down to 0.01 milliseconds produces a very fast release, while the longer 1000 milliseconds value is the slowest on offer.

- Reduction Meter: Displays how much level (gain) reduction is currently hitting the incoming signal.
- Output Meter: Shows the output level after the limit.

### Limiter Sidechaining

Sidechaining is supported by the Fairlight FX Limiter, letting you momentarily pull down the level of a destination track or bus driven by the audible content of a source track or bus. It proves quite useful when several tracks compete for room in a mix because they occupy some or all of the same frequencies — say, a dialogue track alongside a bus carrying traffic and crowd ambience. In essence it is yet another flavor of “ducking”: in that scenario the dialogue lowers the traffic and crowd noise until the speaking stops, so the voices come through with greater clarity.

### Sidechain controls

### Using the Limiter Sidechain

Picking up the earlier scenario: 1 On the destination track or bus carrying the traffic and crowd noise, open the Limiter. 2 From the source dropdown beside the Listen button, pick the Dialogue track or bus.

- This is the source signal whose content drives the level reduction on the target track.
- Choosing a bus as your source means several inputs can drive the changes on the target track. Pressing the Listen button plays back the incoming signal, which is handy for verifying that the right input is actually reaching the Limiter. When active, this button glows yellow.

### Meter

This is a sample peak processing meter, handy for momentarily attaching a meter to one particular track or FlexBus. Such meters earn their keep whenever you want a sizable meter trained on a single bus or track during your work.

### The Meter Fairlight FX

The display is deliberately spare: a gray bar tracks the level while a red peak line holds for two seconds to mark the loudest peak. A numeric readout at the meter’s top reports the precise level in dB, and that figure keeps holding to indicate the highest level reached over any span of playback. You can resize the Meter by dragging from its lower-right corner, and the option menu carries these controls:

- Reset Peak on Play: With this on, the numeric peak figure clears each time you stop and restart playback. With it off, that figure stays put until a louder peak replaces it.
- Reset: Resets the numeric peak level.

### Modulation

This is an effect plugin — a versatile modulation tool aimed at sound effects and sound design. Its four effects bring together an LFO, FM adjustment, AM adjustment, Sweep and Gain filters so that frequency, amplitude, and spatial modulation can happen all at once. Together with the Rotation controls, you can fold straightforward Tremelo and Vibrato effects into auto-filter and auto-Pan tools to lend a sound texture and motion. As you tweak the Modulator, Frequency, and Amplitude parameters, an animated graph charts the outcome, giving you a picture of the kinds of modulation about to hit the signal. Output meters reveal the level leaving the plugin.

### The Modulation Fairlight FX

Modulation has the following controls:

- Bypass: Toggles this plugin on and off.
- Modulator: A low frequency oscillator (LFO), drawn in blue on the animated graph.

Shape: Picks the waveform the LFO uses to modulate the audio. Six choices are on offer: Sine, Triangle, Saw1, Saw2, Square, Random. Rate (Hz): Sets how fast the modulating LFO runs. Slower settings produce a warbling tone, whereas pushing it very high turns the audio into a buzz whose color depends on the shape you picked.

- Frequency: Frequency modulation (FM) driven by a secondary oscillator, rendered green on the animated graph.

Level (%): Behaves like a Dry/Wet knob that sets how much Frequency Modulation is layered on, dialing the effect up or back. Phase: Because all four core effects in this plugin may run together — and because modulation with level components (Tremelo/Rotation/Filter) can either reinforce or cancel one another — phase controls are provided. Shifting one effect’s phase lets you steer that interaction (for example, canceling a strong level change or offsetting a cancellation).

- Filter: Sweep and gain filters.

Filter (%): Behaves like a Dry/Wet knob governing how much filter sweep and gain is applied on top to reshape the signal. A 1D graph alongside previews the amount you’ve dialed in. Tone: Adjusts the center frequency of sweep. Phase: Because all four core effects in this plugin may run together — and because modulation with level components (Tremelo/Rotation/Filter) can either reinforce or cancel one another — phase controls are provided. Shifting one effect’s phase lets you steer that interaction (for example, canceling a strong level change or offsetting a cancellation).

- Amplitude: Amplitude modulation (AM) driven by a secondary oscillator, rendered green on the animated graph.

Level (%): Behaves like a Dry/Wet knob setting how much Amplitude modulation is applied. (Disabled in Ring Modulation Mode.) Phase: Because all four core effects in this plugin may run together — and because modulation with level components (Tremelo/Rotation/Filter) can either reinforce or cancel one another — phase controls are provided. Shifting one effect’s phase lets you steer that interaction (for example, canceling a strong level change or offsetting a cancellation). Ring Modulation Mode: Switches on a Ring Modulation effect, in which the carrier is multiplied by the modulator instead of being modulated by it.

- Rotation: This set of controls becomes accessible solely on a multi-channel track.

Rotate: How much Rotation is applied. Offset: The starting offset of the rotation, used to position the signal further out in space. Phase: Because all four core effects in this plugin may run together — and because modulation with level components (Tremelo/Rotation/Filter) can either reinforce or cancel one another — phase controls are provided. Shifting one effect’s phase lets you steer that interaction (for example, canceling a strong level change or offsetting a cancellation).

- Output: Controls that shape what finally leaves this plugin.

Dry/Wet (%): A percentage blend, as output, between the “dry” untouched signal and the “wet” processed one. 0 is completely dry, 100% is completely wet. Output Level (dB): Trims the overall level of the processed sound on its way out.

### Multiband Compressor

This is a dynamics processor that applies compression across precisely defined frequency bands. Its graph lays out frequencies in Hertz along the horizontal and gain in decibels along the vertical. That arrangement enables compression targeted at specific bands, which is handy when you only need to rein in one or a few portions of a signal.

### The default setting of the Multiband Compressor

Every band carries dynamics control across the set Low, Med, and High frequency ranges, and you adjust them either by dragging the intersection mark on each band’s graph or by entering a frequency directly. Bands 1 – 4: Controls for each band.

- Threshold: Caps how loud the output may get. The default is –25dB. The range is from –50 to 0dB.
- Gain: Lets you boost or cut by as much as 12 dB of gain.
- Ratio: Tunes the compression ratio. This is the gain reduction ratio (input to output) imposed on

signals climbing past the threshold level. The default is 1.5.0:1. The range is 1.0:1 to 7:1.

- Limit: Caps the output by as much as 15 dB. The default is 4.5 dB.
- Attack: Tunes the sidechain detector’s attack rate time constant. The default is 1.4 mS. The

range is 0.1 to 100 mS.

- Hold: Prevents the dynamics from firing again until a set interval has elapsed, expressed in mS

(milliseconds). Defaults to 0mS. The range is from 0 to 4000 mS.

- Release: Tunes how fast the sidechain detector ceases applying dynamics once a signal drops

down past the threshold once more. It defaults to 150 mS and spans 50 mS through 4.0 S. Master: A group of controls governing what finally exits this plugin.

- Gain (dB): Trims the processed sound’s overall level, adding or removing up to 18 dB of gain.
- Q: Tunes how wide a band of frequencies is affected. Smaller values cover a broader span, larger values a narrower one.

### Noise Reduction

This is a repair plugin built to suppress many varieties of noise across all sorts of recordings. A graph presents a spectral view of the targeted audio, with a purple overlay marking which noise is being acted on. A pair of audio meters — input on the left, output on the right — let you weigh how much signal the noise reduction is costing you. Three default presets ship with it: De-Hiss, De-Rumble, and De-Rumble and Hiss.

### The Noise Reduction Fairlight FX in action

Noise Reduction has the following controls:

- Bypass: Toggles this plugin on and off.
- Listen to Noise Only: Found at the top right, this checkbox isolates just the noise being

removed for monitoring. It is invaluable for judging whether you’re stripping out too much signal or whether you can push the attenuation harder.

- Threshold (in dB): Tied to the signal-to-noise ratio (SNR) of the original recording. Where that ratio is poor, a higher threshold value is needed, which in turn produces more aggressive noise reduction.
- Attack (in ms): Chiefly relevant in Auto Speech mode, this governs the window over which the noise profile is sampled. Ideally the attack time tracks how much the unwanted noise varies. A small value means the noise profile refreshes faster and suits rapidly changing noise; a large value refreshes more slowly and suits noise that stays fairly steady.
- Sensitivity: Raising this overstates the noise profile that was detected; consequently more noise gets stripped away, though more of the dialogue you’d rather preserve may suffer too.
- Ratio: Sets the signal profile’s attack time relative to that of the noise profile. A quicker ratio catches and keeps speech transients more readily, though the resulting speech profile turns out less precise.
- Frequency Smoothing: Evens out the resulting signal across the frequency domain to offset harmonic ringing that lingers once the noise has been pulled out.
- Time Smoothing: A toggle that additionally applies smoothing to the resulting signal across the time domain.
- Dry/Wet: As output, a percentage blend between the “dry” original signal and the “wet” processed one. 0 is completely dry, 100% is completely wet.
- Level: So you can make up for any level lost to the noise reduction you’re applying, this adds pre-gain, ranging from -6dB to +18dB, just ahead of the dry/processed blend.

### Phase Meter

Phase cancellation is the effect in which the two waveforms of a stereo recording — say a stereo capture of a live music performance — slip out of sync for some reason and start canceling one another in erratic ways, leaving the audio sounding odd. The upshot is degraded sound that can be troublesome when you try to encode a mix to a delivery format such as AAF or MP3. The Phase Meter plugin offers a visual gauge for judging whether a signal is in phase; it is intended for a bus, so you can assess the phase of a whole mix and fix any issues that crop up. Where a green dot sits inside a horizontal meter tells you the signal’s phase: with no signal, or with signal on only one side of a stereo bus, the dot rests in the center (0); when the signal is out of phase it swings fully to the left (–); and when it is in phase it swings fully to the right (+).

### The Phase Meter plugin

### Pitch

An effects plugin that shifts audio pitch without altering clip speed.

### The Pitch Fairlight FX

Pitch has the following controls:

- Bypass: Toggles this plugin on and off.
- Semitones: A “coarse” control that moves audio pitch by as much as +/- 12 semitones.
- Cents: A “fine” control that nudges audio pitch by as little as +/-100th of a semitone.
- Dry/Wet: As output, a percentage blend between the “dry” original signal and the “wet” processed one. 0 is completely dry, 100% is completely wet.

### Reverb

A spatial simulation plugin able to reproduce multichannel reverberation for rooms of varying size, which you steer through a graphical 3D cube control. With it, a “dry” recording can be made to seem as though it were captured inside a vast cathedral, a bare room, a tiled bathroom, or any number of other spaces.

### The Reverb Fairlight FX

It helps, when learning this plugin’s controls, to recognize that the signal travels along three paths that combine into the final effect:

- A direct path.
- An early reflection path (ER) that models the early reflection rays produced by the first several

bounces off the walls as sound travels from the virtual source toward the virtual listener.

- A late reverberation path (Reverb) that models how an acoustic representation of the room behaves.

A graph offers a rough picture of how the reverb shapes the frequencies of the audio signal. Reverb has the following controls:

- Bypass: Toggles this plugin on and off.
- Room Dimensions: By setting how large the virtual room the sound occupies is, these

parameters jointly drive how both Early Reflection and Late Reverberation processing are configured. The room’s computed acoustic modes are routed into Late Reverberation processing, while the shape, gain, and delay of those first reflections are computed and routed into Early Reflection processing. Height, Length, Width: Sets each dimension of the reverberant space, measured in meters. Room Size: The computed Room Width x Length, given in meters.

- Reverb: Extra controls for fine-tuning how Early Reflection and Late Reverberation processing are configured.

Pre Delay: Lengthens or cancels the travel time from the virtual source to the virtual listener, thereby changing the opening gap between the source signal and its first reflection. Reverb Time: The decay time of the Reverb tail; it drives the overall decay of the acoustic modes coming out of late reverberation processing. Distance: Alters how far apart the virtual source and the virtual listener sit. It touches only how the early reflections processing is configured. Brightness: Shapes how decay time varies with frequency. At full brightness, every frequency decays in the same time; at minimum brightness, the higher frequencies decay faster and so sound duller. Modulation: Introduces random low-frequency phase modulation taken from the ER processing tap point. At 0%, no modulation occurs.

- Early Reflection Tone: A set of four post-equalization controls that shape the tone of the early reflections to match a given room. Low Gain: The gain applied to the low band. Low Frequency: Covers a band from 150 Hz to 500 Hz. High Gain: The gain applied to the high band. High Frequency: Covers a band from 1k Hz to 16k Hz.
- Reverb Tone: A set of four post-equalization controls that shape the tone of the reverb tail to match a given room. Reverb Tail Low Gain: The gain applied to the low band. Reverb Tail Low Frequency: Covers a band from 150 Hz to 500 Hz. Reverb Tail High Gain: The gain applied to the high band. Reverb Tail High Frequency: Covers a band from 1k Hz to 16k Hz.
- Output: These controls fold the three audio processing paths back together into one output. Dry/Wet: As output, a percentage blend between the “dry” original signal and the “wet” processed one. 0 is completely dry, 100% is completely wet. Direct Level: How much of the direct level is folded into the final signal. Early Reflection Level: How much early reflection is folded into the final signal. Reverb Level: How much reverb is folded into the final signal.

### Soft Clipper

The Soft Clipper is a limiting processor that pulls down output above a set threshold in a rounded fashion, so peaks are attenuated more gently. Driven hard past that threshold, the Soft Clipper plugin introduces saturation, lending the sound warmth and a touch of distortion. A graph illustrates the curve this plugin applies to the audio. Pairing a soft clipper with a conventional limiter is a common way to boost a track’s perceived loudness while avoiding harshness.

### The Soft Clipper Fairlight FX

Threshold: Adds input gain ahead of the clipper, driving audio peaks past the threshold by that amount, which in turn fuels the saturation and distortion. Shape: The clipper’s shape can be swept to alter the soft clipper’s character, from full soft-clipping (fully right, where peaks are rounded) to full hard-clipping (fully left, where peaks are squared off). Output Level: Lets you trim the output gain to make up for any signal lost during soft clipping when needed.

### Stereo Fixer

A straightforward plugin meant to repair stereo source material — for cases where only one side of a stereo signal got recorded, where the two sides of a stereo recording sit at different levels, or where the Left/Right channels were mistakenly swapped. It can double as a “Mid/Side” decoder for material captured with that microphone technique. This plugin works on stereo clips only.

### The Stereo Fixer Fairlight FX

- Format: Which input processing mode you’ll use to repair the stereo output. Stereo: (Default) Leaves the format untouched, with no conversion. Reverse Stereo: Trades the Left and Right sides. Mono: The plugin puts out a mono blend of its two inputs. Left Only: The left input feeds both the left and right outputs. Right Only: The right input feeds both the left and right outputs. M/S: The left output equals the left (Mid) input minus the right (Side) input; the right output equals the left (Mid) input plus the right (Side) input.
- Left/Right Gain: Lets you set gain separately on the left and right outputs. It is applied after (post) the input processing mode.

TIP: To build a full M/S decoder, just chain a pair of Stereo Fixer plugins. The first unit governs the Side signal level, which in turn governs the width of the second unit (set to M/S).

### Stereo Width

This is an enhancement plugin that broadens or narrows a stereo signal’s spread to widen or tighten the separation between channels. Placed on a Mono channel it switches off, since there is no stereo width there to spread or rein in. A graph renders the chosen width of stereo spread as a purple arc, and within that graph a stereo meter charts the Left and Right spread of the signal. Two audio meters track levels — an Input meter on the left and an Output meter on the right.

### The Stereo Width Fairlight FX in action

Stereo Width has the following controls:

- Width: Governs how wide the stereo output spreads. Values run from 0 (Mono) through 1 (Stereo) to 2 (extra wide stereo).
- Diffusion: Adds more complexity to the output.
- Sparkle: Adds more high frequencies to the spread.

### Surround Analyzer

Rather than the usual bar-graph display, the Surround Analyzer is a graphical meter that paints a spatial picture of the audio it measures. Because its outline keeps shifting with whatever is playing, people sometimes call it the “jellyfish meter.” This style of metering is genuinely helpful: instead of leaning on bars to show where the audio is heading, you get a clear view of how every channel relates to the others.

Here the signal leans toward the right, which reflects how the audio is panned.

### Vocal Channel
