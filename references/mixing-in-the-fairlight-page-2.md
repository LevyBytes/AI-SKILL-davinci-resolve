# Mixing In The Fairlight Page (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Whole effect chains can be duplicated from one track to another with every effect parameter carried across exactly. Imagine you have built a plugin chain on a dialogue track containing Noise Reduction, a De-Hummer, and a Dynamics plugin, each dialed in precisely so those dialogue takes sound their best. Suppose a second track holds comparable recordings that would gain from that very same plugin chain at those same values. Instead of adding each plugin again and re-entering the values by hand, just right-click the track header (A1, for instance) and choose Copy. Next move to the header of the track you want to receive the effects, right-click there, and choose Paste. The matching plugin chain is now duplicated onto the second track, every value preserved precisely as you originally dialed it in on the source dialogue track

### Copying and Pasting Effect Settings

When a single effect has settings you invested considerable time perfecting, and you realize the same settings might serve another track's effect equally well, you can copy and paste only those settings. Say a Reverb on a dialogue track has been tuned just right, and you notice those very settings would suit a different dialogue track elsewhere on your timeline. Instead of rebuilding the settings from scratch, you can clone them.

- Press and hold the option key while dragging the Reverb plugin you wish to clone to its new spot. Doing so produces a copy at the destination and keeps the source untouched.
- You may instead use Copy and Paste from the plugin's three dot Options menu. To carry those settings onto the other track, pick Copy from the source Reverb effect's Options menu, then bring up the target Reverb effect's Reverb plugin window, open its Options menu, and paste. Every parameter is now matched across both plugins.

For more information on using audio effects, see Chapter 180, "Audio Effects."

TIP: Whole channel-strip presets can be built and recalled, then reused across any project or timeline by way of the Fairlight > Presets Library.

### Effects In

With a single control, the Effects In button bypasses every Fairlight FX, AU, or VST effect plugin on a channel. Lit (orange) means all effects are active; unlit means all effects are bypassed. NOTE: The built-in Dynamics and EQ processors, along with Track FX (Voice Isolation with Resolve Studio and Dialogue Leveler), stay unaffected by Effects In.

### Dynamics

A built-in Dynamics processor sits on every Mixer channel strip, and a small Dynamics Indicator graph shown on the strip doubles as the button that opens it. Double-click that Dynamics Indicator to open the Dynamics processor window, which holds three modules: an Expander/Gate, a Compressor, and a Limiter. You can run each one on its own or combine them to shape the dynamics of the audio on the chosen track.

### The Dynamics control window

### The Dynamics Graph

As you switch on whichever combination of Dynamics window modules a track calls for, the Dynamics graph redraws with curves illustrating how the Expander/Gate, Compressor, and/or Limiter settings in use are shaping the signal. The Dynamics graph additionally gives you a live animated readout that meters the actual behavior of the input/output signals against the graphic showing the underlying response curve.

- The X axis (horizontal scale) represents the input signal level.
- The Y axis (vertical scale) represents the output level.
- The blue line represents the threshold.
- The light green line represents the dynamics curve (which depends on the process type and the setting;

this will shift).

- Animating across the top portion of the graph, the light green balls trace how the Dynamics control

settings shape the signal as it rises above or sinks below the threshold. Because the balls respond to the attack and release settings, they let you picture how the compressor is acting on the input signal.

- Along the input and output X-Y lines, smaller markers let you read precisely where the input/output levels sit.

In real time, the Dynamics graph shows the response curve and how the current settings are shaping the signal. That same curve appears on the channel strip's Dynamics Indicator, so a quick look tells you what is happening on the channel (minus the live animated display). You cannot adjust this indicator; open the Dynamics window when you need to make changes.

### The channel strip Dynamics Indicator

### Master Dynamics Controls

At the top of the Dynamics window you will find these overall controls:

- Enable button: Switches the overall dynamics effect on and off while leaving the controls untouched.

NOTE: Dynamics can also be toggled on and off with a single click on the Dynamics button (the mini graph) located on the channel strip.

- Reset button: Sitting at upper right beside the three dot Options menu, the circular reset icon returns every control in the Dynamics window to its default.
- Preset Menu: This is where Dynamics presets show up. Presets can be made, edited, and saved, and the supplied defaults work well as starting points tailored to what your track needs.
- Make Up Gain control: A level control placed after the dynamics stage, letting you raise the signal to offset any drop in overall level that the dynamics settings introduced.

### Expander/Gate

First among the three dynamics modules, the Expander/Gate controls toggle between expansion and gating. Expansion accentuates volume contrasts by pulling down the level of a signal's quiet passages relative to its loud ones, and it serves to suppress noise while widening a signal's dynamic range. Gating lowers the level of, or fully mutes, portions of a signal that drop beneath the chosen threshold so as to cut down or remove noise during the quiet stretches of a recording.

- Expander: This button enables the Expander.

Threshold: Defines the signal level beneath which expansion takes place; its default is –35 dB, adjustable across –50 to 0 dB. Range: How much the signal level drops, in dB, with both threshold and ratio influencing it. A higher ratio lets range exert more pull. With ratios on the low side, raising threshold strengthens what range does. Ratio: Establishes the attenuation ratio (input to output) put on signals dropping below the threshold level. While Range governs how far the signal falls, this governs how fast it falls; the default here is 1:1.1, spanning 1:1.1 up to 1:3.0. Attack: Controls how rapidly expansion kicks in once a signal passes the threshold; it defaults to 1.4 ms (milliseconds) and covers 0 to 100 ms. Hold: Determines, in ms, how long the Expander stays open once the input drops beneath the threshold; the default is 0 ms, with values from 0 to 4000 ms (4 seconds). Release: Sets how fast or slow the Expander attenuates as the input signal returns below the threshold; its default is 93 ms, spanning 50 to 4000 ms (4 seconds).

- Gate: This button enables the Gate.

Threshold: Defines the signal level beneath which gain reduction takes place, adjustable across –50 to 0 dB. Hold: Determines, in ms, the length of time the Gate remains open once the input drops beneath the threshold; it defaults to 0 ms and covers 0 to 4000 ms (4 seconds). Range: Establishes the largest amount of gain reduction applied as the signal drops below the gate threshold. No gain reduction occurs once the signal sinks under the level given by the gate threshold minus the gate range. Here the default is 18 dB, spanning 0 to 60.2 dB. Ratio: Unused for gate. Attack: Controls how rapidly gating engages once a signal passes the threshold; it defaults to 1.4 ms and covers 0 to 100 ms. Hold: Prevents dynamics from retriggering until a set interval, in ms (milliseconds), has elapsed; the default is 0 ms, with values from 0 to 4000 ms (4 seconds). Release: Sets how fast or slow the sidechain detector ceases attenuating as the input signal returns below the threshold; its default is 93 ms, spanning 50 to 4000 ms (4 seconds).

### Compressor

The second group of dynamics parameters applies compression, which reads an audio signal's envelope in order to adjust its level automatically. A compressor narrows a signal's dynamic range by shrinking the level gap between the loudest and softest portions of the input. It can lift the overall level of the signal without clipping, raising perceived loudness. Compression often helps voices sit more present in a mix and evens out level swings on tracks whose dynamic range is too wide for the job at hand.

Yet "overcompressing" can strip away a sound's natural dynamics, or wipe out so many of the natural transients (the bursts of energy, or "attacks") that lend the original sound its character. Heavier compression can also be applied creatively, though, to reshape a sound's character toward more apparent attack, alter its release behavior, or shift the balance and blend of the space a sound was captured in (for instance, compressing a source signal with a higher ratio and quick release to bring up the presence of a room tone in which the source was recorded).

- Compressor: Enables the Compressor.
- Threshold: Defines the signal level above which compression takes effect; its default is –15 dB, with a

span of –50 to 0 dB.

- Ratio: Tunes the compression ratio. This fixes the gain reduction ratio (input to output) put on

signals climbing above the threshold level. The default is 2.0:1. The range is 1.0:1 to 10:1. Commonly used ratios for dialogue processing are 2.5:1 to 3:1. With a 3:1 ratio, for every 3 dB of increase in signal above the threshold, 1 dB is output.

- Knee: Shapes how signals sitting right around the threshold behave. The knee can ease the changeover from where no compression is audible to where the "hard compression" (the set ratio) begins.

The Knee: Control smooths the slope at the threshold point. You can watch the Knee's effect on the graph by using a ratio such as 4:1 and adjusting Knee; the line where compression "kicks in" rounds off as the Knee control rises. Ordinarily, compression starts immediately above the threshold, which is called a "hard knee." For a gentler, less noticeable approach to compression, dial in a softer knee so that compression comes on gradually as signals near the threshold and climb past it.

### Hard and Soft Knee graphs

Mix: Blends the compressed (0) and non-compressed input signal (100), so you can weigh the compressed signal against the original, untreated sound. Say you are building a big explosion impact effect; it can occasionally help to fold a touch of the original, uncompressed signal into a more compressed version, holding onto more of the original character alongside the compressed version. The default is 0 (all compression, no original signal). Attack: Controls how rapidly compression engages once a signal passes the threshold; it defaults to 1.4 ms and covers 0 to 100 ms.

Hold: Once the attack phase finishes, the Hold parameter governs how long that initial attenuation persists before the release phase begins; the default is 0 ms, with values from 0 to 4000 ms. Release: Sets how fast or slow the sidechain detector ceases applying compression as a signal drops back below the threshold; its default is 93 ms, spanning 50 to 4000 ms (4 seconds). Sidechain: This reworked section lets you build sidechain compression, or "ducking," from the parameters and controls listed below, rather than feeding the sidechain input via a Send from a track or bus:

### Sidechain module

- On: A click turns this button red, signaling that the Sidechain module is now active.
- Listen: A click on this button isolates the incoming signal for monitoring, which helps when you

want to verify that the right audio signal is reaching the Sidechain module.

- Source: This button picks which track or bus is supplying the incoming audio.

### Sidechaining and "Ducking" with Dynamics

The Dynamics module lets you build "sidechain" compression, where a source track or bus uses its audible signal to briefly pull down the level of a target track or bus. For instance, dialogue may live on one track or bus (the source) while music lives on another (the target), and you want that dialogue to stand out more. The procedure: 1 On the music track or bus, open the Dynamics plugin and turn on the Compressor. 2 Open the Source dropdown and pick the dialogue track or bus. TIP: Choosing a bus as the ducking source lets several sources drive changes in your target track. 3 Press the On button; it turns red to show the Sidechain section is now active. 4 As a section of your mix plays back, dial in the gain reduction by dropping the Threshold and lifting the Ratio until the target audio is pulled down enough to make the dialogue more audible. 5 If required, tweak the Hold parameter so the gain reduction does not swing around too erratically. 6 You might also need to tune the Release parameter so the gain reduction does not cut off too sharply. A click on the Listen button isolates the incoming signal when you need to verify that the right input signal is reaching the Limiter. This button goes yellow when active.

### Limiter

The third group of dynamics parameters applies limiting, which sets a targeted ceiling on the level a signal is allowed to reach. Limiting resembles compression but works essentially at a very high ratio.

- Limiter: Enables the Limiter.

Threshold: Defines the threshold above which limiting takes place. Since the Limiter is built to hard limit the output, this effectively also fixes the highest permissible output level; its default is –21 dB, adjustable across –50 to 0 dB. The best approach is to judge the amount of limiting by ear, watching the gain reduction shown on the meter. Overdoing limiting can "squash the life out of the sound," since a mix can shed all of its internal dynamics. Applied well, it smooths out the final mix and lifts the average level. The yellow animated balls in the display also let you observe how the controls shape the real time limiting response. Attack: Governs the attack rate time constant of the sidechain detector; it defaults to 0.71 ms and covers 0 to 100 ms. Hold: After the input level drops beneath the threshold, Hold sustains limiting until the hold time runs out, at which point release time begins; the default is 0 ms, with values from 0 to 4000 ms. Release: Governs how fast the sidechain detector ceases applying limiting as the signal sinks below the threshold; its default is 90 ms, spanning 50 to 4000 ms.

NOTE: With limiting placed on your channel's final output (or across a whole mix), the Makeup Gain slider is frequently needed, either to push the output level to its maximum (on a master) or to restore an individual track's original level (unity). To compare the level change, bypass the Limiter alone or the entire Dynamics module.

### EQ

A 6-band equalizer EQ lives on every Mixer channel strip, accompanied by a mini-EQ graph that shows the present EQ curve, bypasses the plugin, and opens it on a double-click. Among the plugin's choices are high and low shelving, response curves that are parametric or notch, plus high and low pass filters reaching slopes of 24dB/octave, together with controls that lift or cut across various frequency ranges. On each band you get controls for the filter type (Bell, Lo-Shelf, Hi-Shelf, Notch), along with Frequency, Gain, and Q-factor (which sets the band's sharpness); whichever filter type is selected decides which of these controls a band exposes. There is also a selection of four response curves, running from the Native Fairlight response curve to emulations of classic EQs.

The EQ Indicator on the channel strip. (Left) EQ has been adjusted; (Right) EQ sits flat (no EQ).

### The channel strip EQ window

### Master EQ Controls

These overall controls are found in the Equalizer window:

- Enable button: Switches the plugin on and off.
- Reset button: Found at the EQ's upper right, the circular Reset icon restores every parameter to its default setting and value.
- Equalizer Type: From this dropdown you can pick the Native Fairlight response curve or any of three classic mixing-console EQ emulations. The Earth option gives you the Native Fairlight response (Default); Air emulates the SSL 4K; Ice models the Neve V; and Fire stands in for the Focusrite.
- Preset Menu: To store your EQ settings as presets, click the Plus button positioned to the left of the Preset menu.
- Gain fader: Placed after the EQ stage, this fader lifts or trims the processed signal so as to offset the EQ changes you made.

### The EQ Graph

A visual picture of the current EQ settings is what the EQ graph delivers, with numbered "handles" for each active EQ band that you can drag any direction to alter the matching frequency and level. Your mouse wheel can additionally adjust each band's Q (bandwidth).

### The EQ graph

When you drag the numbered handles on this graph, you change the parameters of the matching band in turn, and the reverse holds too: altering a band's parameters also reshapes the EQ graph, which serves the extra role of giving a graphical picture of the equalization curve applied to that track. A mouse wheel, if you have one, can be used to control Q.

### Bands 1 and 6

These outermost two sets of band parameters handle the lowest or highest frequencies in an audio signal.

### Band 1 controls active

### Band 6 controls active

- Band filter type: A click on the Band 1 or Band 6 button turns its corresponding controls on or off.
- Band filter type: Off by default, Bands 1 and 6, once active, each open up the filtering options shown below:

On Band 1 the choices are Low Shelf, Bell, High Shelf, and High Pass. For Band 6 you instead get Low Pass, Low Shelf, Bell, and High Shelf.

- Frequency: Adjusts the center frequency of the EQ band.
- Filter Slope: For the high and low pass filters, selectable slopes begin at 6dB/octave

and reach 24dB/octave.

- Gain: With bands 1 and 6 set to a bell or shelving response curve, this parameter trims or

lifts the chosen frequency over a ±20 dB range.

### Bands 2 – 5

On by default, these band controls let you make a range of EQ adjustments..

### The Band 3 controls

- Band enable button: A click on these Band buttons turns their corresponding controls on or off.
- Band filter type: The filtering options on Bands 2 to 5 are Low Shelf, Peaking, Notch, and High Shelf.
- Frequency: Adjusts the center frequency of the EQ adjustment.
- L, ML, MH, H Buttons: A band's center frequency can be confined by these buttons to one of these

frequency ranges: Low, Medium Low, Medium High, or High.

- Gain: Active once a band uses a bell or shelving response curve, this control sets

the center frequency's level over a ±20 dB range.

- Q Factor: Available when a band uses a bell response, or when the Equalizer

type is Fire, this parameter sets an EQ band's bandwidth across a range of .3 to 10.3. Lower Q factors broaden the bandwidth and higher ones tighten it, deciding the degree to which adjacent frequencies are affected as the center frequency moves.

### Bus Sends

A channel strip's source signals can be routed to a bus destination through Bus Sends, with control over level, pan, mute, and pre/post fader routing. Bus sends can be set up on channels feeding any bus destination you have made. A few common mixing jobs that sends are handy for:

- Submixing: For instance, rendering distinct mixed outputs in different formats at once, such as stereo, 5.1 surround, or Dolby Atmos.
- Feeding signals to a shared effect: For instance, routing to a reverb plugin, where post fader sends from several mixer channels supply, in differing amounts, a reverb sitting on a bus channel strip.
- Headphone cue mixes: Build separate pre-fader mixes for the talent without altering what you hear on your own main monitor speakers.

### Creating Sends

To make a Bus Send and reach its controls:

- In the Mixer's Bus Sends area, click the assign button marked with the plus sign (+).
- A dropdown listing the available busses appears; pick one to assign.
- Your send is now created.

Hovering over the rectangular name button gives you a disable/bypass button, an access icon that opens the Bus Send window for the channel, and an "x" for deleting the send. A tooltip appears displaying the send bus name.

Hovering over the rectangular name button will show send controls.

### Accessing the Bus Sends Window

To manage a channel's sends, open the Bus Sends window by clicking the center of the name button.

### Bus Send window controls

In the Bus Send window, each Bus Send you make presents these controls:

- On: Turns the send on or off.
- Pre: Toggles the send between pre- and post-fader routing. Turning this button on lets

that track feed levels to the destination bus ahead of any level adjustments made on the track itself.

- Send Level: Sets how much signal travels from the chosen feed into the send bus, over a span of OFF to +10dB.
- Pan: Provides panning across Bus Send destinations.

### Uses for Pre-fader Routing

A frequent application of pre-fader sends is cue mixes for ADR or voice over talent, when the performer wants to monitor a mix completely different from the control room mix. With pre-fader sends and a full mix built to a bus that feeds the headphone system, you get a mix that stands entirely on its own. Pre-fader sends also suit special creative effects, such as routing a dialogue channel to a reverb plugin through a send. If that send is pre-fader, then when the main channel fader is pulled down near zero, the dialogue keeps feeding the reverb, so it sounds extremely reverberant (nearly all of the signal is "wet"). Slowly bringing the channel fader up makes the voice seem to approach the listener, shifting the reverb balance toward a more present sound. Bus send levels show in the rectangles for each send and carry the color codes assigned to the destination busses.

Bus Send levels shown on the Mixer channel strip

### Legacy Bus Sends – "Auxiliaries"

Before DaVinci Resolve 17, the Bus Send panel went by the name Auxiliaries. Any project made before DaVinci Resolve 17 will use the legacy Fixed Busing. The sole distinction between the two is that "Aux" stands in for sends throughout the windows and titles.

### Pan

The Fairlight Mixer supplies 2D and 3D pan controls covering a range of audio formats, from mono and stereo through standard 5.1 and 7.1 surround, and on to sophisticated immersive formats like Dolby Atmos, Ambisonics, Auro 3D, and NHK 22.2.

### Channel Strip Pan Controls

Within each Channel Strip, the Pan section holds a Panning Indicator that gives you visualization and panning control over left, right, front, and back. While double-clicking the Panning indicator opens the Panner for extra parameters, you can also do the following directly in the channel strip Pan section with the Panner closed:

Drag inside the Pan Indicator to set the basic panning position.

- Single click to bypass panning.
- Command-drag to adjust the width on multichannel tracks.
- Check the Boom level on surround channels, shown as a horizontal blue line near

the foot of the Panning Indicator.

Channel strip Pan Indicator for a stereo track

### 2D Panner Controls

### Default View

How the source audio is mapped determines which controls appear in the Pan window. You can pan either by dragging the icons in the Panner Viewer or by using the controls down the left side of the window.

### The Panner control window – Default 2D view

In its default 2D form, the Audio Pan window presents these controls:
