# Audio Meters And Audio Monitoring

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Audio Meters and Audio Monitoring

Sitting along the top of the Fairlight page, the Meters panel gives you an at-a-glance read on your mix’s track levels, dedicated meters for the busses, meters that watch over the mix and its loudness, and a video Viewer that keeps the current project in view as you work. The pages here walk through how to use these meters and lay out the assorted options on offer.

### The Monitoring Panel

Switch the meters on from the UI toolbar and up comes the Monitoring panel, stretched across the top of the Fairlight page; it presents every audio meter tied to the Timeline’s tracks, plus the Bus meters tied to your mix’s Mains, Subs, and Aux busses, the Control Room meters, and a video viewer alongside.

### The Monitoring panel

Because immersive audio pushes track counts higher, DaVinci Resolve hands you extra metering choices so more tracks stay visible in real time. A right-click anywhere on the meters brings up a menu where you decide whether the Track display shows as a single row or at double height. That same menu also lets you swap between narrow and wide meters. While the wide meter view is active, a double-click anywhere on the Tracks meters panel flips between the single-row and double-height layouts. Move the mouse just under the Tracks panel and a cursor appears that lets you resize the Monitoring panel’s height. You can also resize the Compound meters and the Bus Output meters by hovering at the right edge of the Loudness meter and dragging out to whatever dimensions you want.

### The double-height Monitoring panel

### Track Meters and Monitoring Controls

Over on the left, a row of audio meters lines up with the Mixer’s channel strips, a meter apiece for every audio track on the timeline. The meter count a track shows follows its audio mapping: a mono track carries one audio meter, a stereo track two, a 5.1 track six, and onward from there. Every track and bus meter, the Loudness meters aside, reads out RMS (root mean square) levels against a dB scale. Just above the live RMS levels, a lone line marking the peak value at that instant lingers briefly, while the levels themselves rise as a solid bar climbing up from the meter’s base. What an RMS meter shows is a weighted “average” of the audio level, nearer to how the ear truly hears it, though it gauges perceived loudness less precisely than the loudness meters covered further on in this section.

Track audio meters whose meter count varies with each track’s audio mapping

### The peak meter at top

Color coding on each meter bar flags three distinct sound level “zones,” running from low through medium (green) up to moderately high (yellow) and on to very high (red). A meter is labeled by the track number it stands for (track names don’t appear above track meters), along with that track’s color.

### Bus Meters

Off to the right of the track meters sit the bus meters, where every user-created main and bus shows up, grouped by type, each carrying the meter count that matches that track’s audio mapping. They let you watch the combined level of all tracks routed into a given bus, just as you can from the bus channel strips.

Bus meters for the Mains, Subs, and Aux busses

### Meter Plugin

A Meter plugin is on hand for dropping a meter onto a specific track or FlexBus for a while, or, under fixed busing, onto a Sub, Aux, or Main. These run as sample peak processing meters, handy whenever you’d like one large meter trained on a particular bus as you work.

The presentation here is stripped down: a gray bar tracks the level, and a red peak line, marking the highest peak, lingers for two seconds. Up top, a numeric reading reports the precise level in dB. That figure keeps holding, showing the loudest level caught over any given stretch of playback. From the option menu in this meter’s floating window, you can pick among various settings.

### For more information, see Chapter 181, “Fairlight FX.”

### The Meter Fairlight FX

Here the signal leans further rightward, a sign of how the audio is panned.

### Surround Analyzer

Rather than the usual bar graph, the Surround Analyzer is a graphical meter that paints a spatial picture of the audio under measurement. Since its form keeps shifting with whatever signal plays, people sometimes call it the “jellyfish meter.” This kind of metering proves quite useful; instead of leaning on bars to point out which directions the audio is radiating, you get a clear view of how all the channels relate to one another.

### Compound Meters and Output Bus Selection Menu

Set to the right of the bus meters, the compound meters bring together Control Room meters and Loudness meters, placed side by side to deliver a full picture of your overall audio mix. Underneath, dropdown menus let you settle on which bus to monitor and which set of speakers to do that monitoring through.

The Control Room meters (at left) and Loudness meters (at right)

### Monitoring Menus

### Bus Monitoring Menu

Which bus your audio output (speakers or headphones) monitors comes down to the bus monitoring dropdown menu, and that in turn fixes which bus the compound meters analyze, so you get to pick the bus you monitor as you work. Your pick might be a main, or whatever other bus (or track) you’ve configured and would like to concentrate on for closer work.

From the monitoring menu you select whichever bus you’d like to keep tabs on as you work.

### Speaker Set Monitoring Menu

Just right of the Monitoring menu, the output defaults to “Auto” (provided Automatic speaker configuration is ticked on under Preferences > Video and Audio I/O > Audio I/O). What that does is route your basic speaker setup, on its own and with no room to change it, to whichever stereo or surround output your hardware can manage.

### Monitoring with Multiple Speaker Sets

Should you wish to set up several speaker sets by hand, clearing the automatic speaker configuration preference brings a dropdown into view at the right and lets you pick one of the available speaker sets, once they’ve been set up in the System Preferences’ Video and Audio I/O panel. That gives you the freedom to swiftly check your mix across an array of speakers and configurations, gauging how it stands up under differing conditions. For more on setting up the various speaker arrangements, turn to Chapter 4, “System and User Preferences.”

This monitoring menu is where you settle on the bus to keep an ear on as you work.

### Control Room Meters

The mustard-hued Control Room audio meters present the combined level of every audio channel feeding the bus you currently have selected for monitoring (the one picked in the dropdown menu below). They are peak meters read in dBFS. A true peak audio reading sits at the top of the Control Room meter.

### Loudness Meters

Furthest to the right lie the Loudness meters, a pairing of two graphical meters with a numerical readout. They let you stay on top of the overall mix’s “integrated loudness,” the very measure every present-day mixing specification cites when it lays out client deliverables. Where the RMS audio meters in the Timeline or Mixer gauge audio in dB, the Loudness meters carry out a different sort of analysis, expressed in LUFS (loudness units relative to full scale).

### What Is LUFS?

A LUFS measurement weighs sound levels averaged across time and pegged to full scale. Full scale marks the loudest point a digital audio system can take before it overloads (“clipping”). Because LUFS lets wildly different sorts of program material line up in how loud they seem to human ears, it has grown into the usual yardstick for measuring mixes when program material ships for final delivery. LUFS read out as negative figures, -23, -14, and the like, since the level is pegged to full scale (digital 0).

### Loudness Meter Options

Within the General Options of the Project Settings, a pair of options let you tailor the Loudness meters.

- Target Loudness level: Lets you fix the LUFS value that serves as the reference point for loudness metering. It defaults to –23 LUFS, which handily makes these meters scale much like the traditional audio meters you already know.
- Loudness Scale: Lets you settle on which scale the meters are read against. The choices at present are the default EBU +9 Scale (–18 to +9) and the EBU +18 Scale (–36 to +18).

### Support for Multiple Loudness Standards

You can flip the Loudness Meter between a range of international, industry-standard loudness monitoring standards. Whichever standard you settle on draws on the integrated loudness value (together with a tolerance that each chosen standard spells out) to signal whether the present mix level counts as acceptably loud, doing so by color-coding the Integrated Loudness value and within the Integrated Loudness graph laid out below. Blue marks loudness levels sitting under tolerance, yellow marks those that fall within tolerance, and red marks those running over tolerance.

The built-in standards open to you cover these: BS.1770-1: A somewhat dated loudness standard that DaVinci Resolve version 15 and earlier relied on. BS.1770-4: The freshest loudness standard once DaVinci Resolve 16 arrived; its specified algorithms underpin the rest of the standards further down this dropdown menu. ATSC A/85: America’s benchmark for permissible broadcast loudness. EBU R128: Europe’s benchmark for permissible broadcast loudness. OP-59: The New Zealand and Australian benchmark for permissible broadcast loudness. TR-B32: Japan’s benchmark for permissible broadcast loudness. AGCOM 219: Italy’s benchmark for permissible broadcast loudness. NETFLIX: Netflix’s own benchmark for permissible broadcast loudness. YouTube: YouTube’s own benchmark for permissible broadcast loudness. Disney 2.0: The Disney 2.0 benchmark for permissible broadcast loudness. Disney 5.1: The Disney 5.1 benchmark for permissible broadcast loudness. Every one of these loudness standards can be used for off-line readings too, by way of the Loudness Analyzer laid out in the section that follows.

NOTE: For gauging the maximum “true peak,” the target peak meter has switched to the BS.1770-4 standard, which means it can now register “inter-sample peaks” instead of catching only the peaks landing at each waveform sample.

### Graphical Loudness Meters

Two distinct meters hand you a live graphical read on the loudness of whichever bus you’re monitoring, judged against the loudness standard you’ve picked, which sets how the subjective loudness of a given audio mix is analyzed so it meets the broadcast quality control (QC) standards demanded of it.

- A steel-blue meter marked M (for momentary) carries as many channels as the bus you’re monitoring, leaving out the LFE channel(s) of surround formats, which loudness metering doesn’t reckon with. It gauges LEQ (equivalent sound level) inside a 400ms window trailing the playhead, sampled every 100ms. That lets you read the mix’s LUFS (Loudness Units Full Scale) level at the current frame as it plays. This per-channel analysis feeds the calculation of every other value the loudness metering system reports.
- A second steel-blue mono meter on the right shows the combined level of all channels in the M meter, given in LU (loudness units). The figure at the top of this meter is the highest LU value caught across any span of timeline playback. It stays put until reset, which happens either by halting and starting playback again while Link to Playhead is on, or by clicking the Reset button down at the foot of the loudness meter area.

### Numeric Loudness Meters

Off to the right of the meters, a group of values keep up a running account of your mix’s audio level. Handy as the graphical meters are for studying your mix while you work, these numeric readouts earn their keep by supplying the exact figures you need to meet written QC standards. Here’s what each one means:

- Short: Gauges the average LU level across a 30-second window trailing the playhead.
- Short Max: Reports the peak level over that same 30-second window. EBU R128 calls

for this analysis.

- Range: Gauges the dynamic range of your mix’s Loudness (in LU, or loudness units), namely

the gap between the average soft and average loud portions of your mix. It weighs the overall loudness across a played stretch of the mix, sets aside the bottom 10% and top 5%, then puts out a standardized figure for the gap between the soft and loud levels that remain. Its window of analysis runs for however long you’ve been playing. Most QC specifications call for this analysis.

- Integrated: Gauges the LUFS value across the slice of the mix you’ve played through. This integrated figure builds up as playback continues. Most QC specifications call for this analysis.

### Absolute Scales and Dialog

Some people like to read their levels against a relative scale anchored at “0,” the way a VU meter’s needle rides above the “0,” while others would rather see the amplitude’s absolute figure in LUFS and true peak. The Loudness meter starts out on relative scale, yet you can now toggle the Loudness meter between relative scale and absolute scale. Relative scale in the Loudness menu is reckoned against the chosen scale, so a loudness unit of 0 lines up with the target of whatever measure type you’ve selected. Take EBU R128, whose target measure is -23dB LUFS: there the “0” LU (Loudness Unit) equals -23dB. Choose ATSC A/85 instead — its target is -24dB — and that value becomes the equivalent of the relative LU of 0. Switch to absolute scale and the Loudness meter lays out its increments to mirror the chosen measure type. On absolute scale, the EBU R128 meter reads -23 in place of the 0 you’d see on relative scale.

The option over in the Loudness panel surfaces the assorted measure types along with the choice for absolute scale.

### Using the Loudness Meters

When you put the Loudness meters to work on a structured analysis of your mix to check QC adherence, a cluster of controls lets you mark out where the analysis starts and stops.

- Lock Metering to Transport: You’ll find this setting in the compound meter option menu. With it on, every loudness metering analysis resets on its own each time you carry the playhead somewhere else on the Timeline. It comes in handy while you’re spot-checking various parts of your mix, or focused on one scene. Leave this option off when you’d rather the measurement of playback up to that point on the Timeline stayed in place.
- Absolute Scale: An absolute reading of the chosen scale type.
- Pause and Reset buttons: During a formal analysis of your mix, the Reset button

clears out all the analyses gathered so far, while the Start button kicks off the build-up of loudness values. Need to halt playback for a moment to handle something else? Click Pause, then click Resume once you’re set to pick the analysis back up.

### Offline Loudness Analyzer

You can also examine an audio file’s loudness offline. It’s a quick route to measuring loudness within imported audio files or bounced mixes. To kick off offline loudness analysis:

- Right-click the file on the Timeline and pick Analyze Audio Level from the contextual menu. A dialog box then lays out the measurement options on offer.

Every measurement the real-time loudness meter offers is reachable through the dropdown menu inside the Analyze Audio Level panel. Pick an analyzer mode and that mode’s target measurements appear beside the reading in parentheses. Click the analyze button and the results land in the panel next to the chosen mode’s target measurement values.

Pick the audio file, choose the analyzer mode you want, EBU R128 in this instance, and click analyze.

### Visualizing Loudness Monitoring

Bring a Main bus’s track into view on the Timeline and, so long as the track stands high enough (ahem, tall enough), you can reveal or hide a set of “Loudness History” curves that picture the loudness analysis of that bus’s mix across the whole length of the mix. On offer are these curves:

- Integrated: A thick curve traces the averaged “integrated” loudness analysis of the present mix, a reading drawn from the start of playback through to its end. This graph stands as the chief gauge of whether the measured loudness passes muster. Each segment’s color signals whether that part of the mix sits “to spec.” Blue points to loudness levels under tolerance, yellow to those inside tolerance, and red to those above tolerance. Read the curve’s colors and you can readily pick out which parts of your mix might want adjusting to hit the required specification.
- Momentary: A reading of the loudness over the past 400ms, drawn as a thin green-blue curve, which reports on transient shifts in level.
- Short Term: A reading of the loudness over the past 3 seconds, drawn as a thin blue line, which gives a more averaged take than the Momentary curve while still conveying the mix’s dynamics.

To bring Main 1’s loudness history into view: 1 Open the Automation controls with a click of the automation button over on the Fairlight toolbar. 2 Bring up the Index, then click the eye button for whichever Main you want to view on the Timeline. Loudness History turns up among the track header controls as long as the track stands tall enough to show those controls. On short tracks they stay hidden. 3 Switch on the Loudness History toggle, then tick the curves you’d like to see. The Integrated, Momentary, and Short Term loudness analyses can each be shown or hidden on their own, opening up overlapping graphs within that track where your program’s loudness is visible across time.

Viewing the loudness graph of the mix leaving a Main NOTE: For now, loudness history is supported on Main 1 alone.

### Metering Options

DaVinci Resolve offers an assortment of metering options for shaping metering around your workflow. Their settings live under Project Preferences > Fairlight on the Audio Metering pane, yet they reach the mixer, Fairlight effects, and master metering on the Cut and Edit pages.

### Level Metering Options

You get to pick the response characteristic for the level meters covering channel strips and Fairlight FX. The Meter Type dropdown lets you settle on IEC 60268-18, Digital VU, or Custom response characteristics. Each meter type keeps its own “hold and fall” metering, so the highest peak reached stays visible.

IEC 60268-18: A digital PPM-style meter set to a -18 dBFS reference standard, quick to answer peaks yet slower on release. It’s the default within DaVinci Resolve and runs throughout every Blackmagic Design software and hardware product. Digital VU: A two-value meter showing the peak level via a single fast-ballistics segment, with the RMS (volume unit) drawn as a bar graph. Its decay is far quicker and roughly linear, which makes average levels easy to watch while still letting sounds with sharp transients and decays be followed more readily. This one tends to suit audio editing and mixing best. Custom: Lets you choose every facet of the meter response, level detector, scale, peak, deck, and peak indication included.

### Pre-fader Metering

Out of the box, “Pre fader metering on tracks” sits unchecked (disabled), which places the metering on channel strips post (after) the fader level and mute button. Say the source audio file peaks at -2 dBFS and you pull the channel fader down from 0 to -10, after which the peaks shown on the meter land at -12. Turn pre-fader metering on and the metering point moves ahead of the fader, untouched by where the fader sits. The meter does still respond to clip gain settings or keyframing, though, since those level shifts happen before the clip’s signal reaches the mixer’s signal path. Under pre-fader metering you could drop the fader all the way off (minus infinity) and the meter would keep reading the source signal’s level. That keeps you forever aware of the source signal and what it’s up to before the mixer’s controls or processing touch it. Plenty of video editors lean toward post-fader metering, whereas most audio mixers favor pre fader so the true source level is known at every moment.

### Solo and Pre-fader Metering

With pre-fader metering switched on, soloing one or more tracks paints a fainter “ghost” of meter activity onto the tracks that aren’t soloed, so audio levels stay visible even on tracks the soloing has muted. That makes it simple to concentrate on the tracks you can actually hear while still catching what’s happening on the ones you can’t. Where pre-fader metering is off (the default), soloing one or more tracks leaves the unsoloed tracks with no metering at all.

Pre-fader metering, the non-soloed tracks showing lightly shaded meters

### Target Loudness Level

Lets you set the master Loudness meters’ target loudness level, in LUFS, to whatever output target you’re aiming for. DaVinci Resolve’s default loudness standard target, for one, is -23 LUFS, while YouTube’s target LUFS specification calls for -14 LUFS. Set -14 LUFS and the “0” mark on the loudness meter scale shifts to that level, helping you steer your master mix levels toward that loudness standard.

### Viewer

A compact viewer set to the right of the Monitoring panel displays the video frame sitting under the playhead. It’s the very image fed to your workstation’s external broadcast display, should one be hooked up.

The Viewer shows you the picture you’re mixing against. Click the Expand Viewer button down in the bottom right corner and the Viewer opens into a floating window you can then drop wherever you please. To shut the floating Viewer, click the Dock Viewer button in the upper right corner of the floating viewer window.

Click the button in the upper right corner to dock the Viewer once more.

### Cinema Viewer on Fairlight Page

There are times, when you have to confirm lip sync or sound effects sync, or just look over a fresh stretch of a mix you’ve been shaping, that watching the program’s visuals full screen while your mix plays really helps. The Fairlight page Viewer can now be put into Cinema Mode by choosing Workspace > Viewer Mode > Cinema Mode (Command-F).
