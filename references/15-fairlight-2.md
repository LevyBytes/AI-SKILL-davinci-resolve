# Track Groups, Audio Effects

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

## Overview

Covers: Track Groups; Audio Effects.

## Track Groups

### Track Groups

Track groups give you a way to apply adjustments and edits to your mix over several tracks all at once.

### Editing with Track Groups

Track groups let you shift your attention from single tracks onto bundles of tracks, anything from a handful of tracks up to a sizable multitrack sub-mix group. Once a group is on, an editing action carries across every track within it. Some actions that shift clip boundaries or trim, however, behave differently. As an example, tapping the Up and Down arrows to jump between clip boundaries respects the boundaries of each track inside the group, no matter where they stack vertically in the timeline. You can switch groups off to return your focus to the individual tracks they hold. Yet when smaller groups sit “nested” inside a bigger one, disabling the larger group leaves the smaller group untouched. Where an edit group holds clips of unequal lengths, the group behavior still holds, so that every edit—trim, cut, or paste—follows the group at whatever boundaries it currently has.

### Mixing with Track Groups

While mixing with track groups, an adjustment to one channel applies to all the others in the group at the same time. That spans fader moves, panning settings, send levels, automation, plus toggles of the mute, solo, and record-arm buttons.

NOTE: Plugin controls cannot be added to Mix groups.

### Showing the Groups List

Click the Groups button in the Interface Toolbar to open and close the Groups list. Should the Track Index or other Index tabs already be open, the Groups list shows up below them. Even after you shut the Track Index, or click any of the remaining Index tabs, this list keeps showing.

### Groups list

### Groups List Controls

Group Name: This column shows the group name or “ID.” Groups Switch: Flips all groups on or off, letting you move smoothly from working with groups to working with individual tracks.

Selected Checkbox: When ticked, every track belonging to the group is selected. If only part of them are selected, a hyphen appears instead. Action Icons on Hover: These icons surface only while you hover over the group row. The Tools icon opens the Modify Groups dialog, and the Trash icon removes the group.

### The All Group

The All Group holds every track's Mixer channels, which makes editing or mixing across all tracks at once simple. This group always lives at the top of the Groups list.

### The Selected Checkbox

Ticking the Selected Checkbox places a checkmark, which means every track inside the group is now selected. That makes it simple to build on a current group (shift-clicking to bring in more members and using Create Group) or to steer the routing of all selected tracks together by holding the Option (Alt Windows) keys while assigning or unassigning. Say, for instance, we've got Group 1 with six tracks and Group 2 with 10. Just click the Selected checkbox for Group 1, and every track in Group 1 gets selected. Then hold Shift and click the checkbox beside Group 2. Now both groups' members are selected, and you can build a new Group 3 containing all of them.

- A hyphen (“-“) is shown if only some tracks are selected.
- Clicking the checkbox to remove the checkmark or hyphen deactivates the group.

NOTE: Whether a group sits enabled or disabled has no bearing on the Selected checkbox; it stands as its own control, not bound directly to grouping.

Group Key Commands Switch Groups on or off with Command + num keypad 0 key (Control on Windows). Use Command (Control on Windows) + num keypad number 1-9 to switch the first nine groups on or off. Use Command (Control Win) + num keypad \* key to toggle the All Group.

### Creating and Editing Track Groups

To create a track group, do one of the following:

- Pick one or more tracks through their track headers in the Timeline. Right-click any track you'd like in the group and choose Create Group. The same works in the Mixer on a channel strip.
- Pick one or more tracks through their track headers in the Timeline. Then click the Create Group icon at the top-right corner of the Groups list.

### Create Groups icon

Inside the dialog that opens, proceed this way: 1 Give the group a name. To choose a group color, click the dropdown list sitting to the right of the Group Name field. 2 Decide which controls belong to the group (Editing, Fader, Solo, Mute, Arm, Sends, Panning, and Automation). Hit Set as Default and these choices stick for any groups you make later. 3 Highlight tracks within the Add Channels column at the left, then click the >> icon to move the highlighted tracks into the group. The same way, highlight tracks in the Channels Added column at the left and click the << icon to take those tracks out again. 4 Hit Save to store the group. 5 Up pops the new group in the Groups list.

### Create Group - Group Settings dialog

To activate or deactivate a group:

- In the Groups list, select or deselect the group. A selected group lights up, a sign that it's active.

To rename a group:

- Double-click the group name in the Groups list.
- Type the new name you want for the group.

To edit a group:

- Hover over the group you'd like to edit and click the Settings icon to bring up the Modify Groups (Group Settings) dialog.
- Make whatever changes you want, then pick Save.

### Tools icon to launch Modify Groups dialog

Removing a track group: 1 Open the Tracks Index. 2 Within the Groups list, hover over whichever group you want gone, click the Trash Can icon on the right, then hit the Delete button in the confirmation dialog.

### The Mixer and Track Groups

Temporary Override (“Clutch”) As you work the Mixer, hold Command‑Shift (Mac) or Control-Shift (Windows) while nudging one fader or several within a group, and you can move them independently of the group's other members (in other words, this acts like suspending the group just for whichever faders you've “clutched”).

### Group Management via Mixer Channel Strips

Group assignment and creation can also be managed by clicking any channel strip's Group name section, which opens a menu holding the details below along with an option to make a new group:

- Active and inactive channel groups
- Where it applies, a checkmark beside whichever group name the channel strip is part of.

### Group menu on a Mixer channel strip

## Audio Effects

### Audio Effects

DaVinci Resolve ships with Fairlight FX audio plugins and supports compatible third-party VST and Audio Unit plugins for the Edit and Fairlight pages, letting you layer effects such as echo, reverb, noise reduction, and aural enhancement onto audio clips, tracks, and busses. This chapter walks through various ways of putting these effects on clips and tracks.

### Elastic Wave Audio Retiming

Elastic Wave retiming is a quick, simple, keyframe-based approach to dynamically retiming audio, squashing and stretching different stretches of a waveform to subtly retime audio playback for all sorts of reasons, all while pitch stays constant. For instance, if you're swapping in the audio of one take for the current take, but the performer's timing runs a touch different, Elastic Audio lets you make small tweaks to retime the second performance against the first. Putting Elastic Wave retiming to work on an audio clip: 1 Here, two tracks of foley effects have been laid down, and the lower one has to be retimed so it lines up with the upper one. 2 Right-click an audio clip, then pick Elastic Wave retiming off the contextual menu to bring up the Elastic Wave retiming controls. Switching Elastic Wave on 3 Command-click any point on the clip to drop speed keyframes onto the waveform sections you'd like retimed by stretching or squishing. Speed keyframes can also be placed to pin down waveform sections you'd rather leave untouched.

Dropping a speed keyframe while Elastic Wave retiming is on 4 Drag the speed keyframe to the left or the right and the audio speeds up on one side of the keyframe while it slows on the other, reaching from that keyframe out toward the adjacent keyframes on the clip. With an audio clip's waveform to guide you, several speed keyframes let you align one performance's waveform against another's so their timing matches. Alternatively, shift speed keyframes at will to warp performances or sounds for creative effect. In the same vein, dragging an audio clip's start or end retimes that stretch of the clip forward or back as far as the next speed keyframe you've placed.

Tuning a run of speed keyframes so one performance matches another

5 If you've made a handful of speed keyframe tweaks but find yourself wishing one you created sat somewhere else relative to the audio waveform being adjusted, hold down the Command key and drag any speed keyframe to move it toward or away from the part of the waveform it should retime. Doing so fine-tunes the audio retiming taking place at that point in the clip.

(Left) The state before a speed keyframe is Command-dragged nearer the original start of the retimed sound, (Right) the state afterward 6 Once finished, click the close button up in the top-left corner to hide the Elastic Wave retiming controls. To clear Elastic Wave retiming keyframes, take one of these routes:

- To clear one speed keyframe: Right-click a speed keyframe and pick Remove Speed Keyframe out of the contextual menu.
- To clear every speed keyframe and wipe out the Elastic Wave retiming effect: Right-click a clip and pick Reset Speed Curve.

NOTE: Every Elastic Wave retiming tweak you make on the Fairlight page surfaces on the Edit page as variable speed effects, reachable through the Retime controls. Bear in mind that although any Elastic Wave retiming effect can show up as an Edit page retime effect, the reverse isn't true—not every Edit page retime effect translates into an Elastic Wave retiming effect back on the Fairlight page.

### Elastic Wave Options

The Elastic Wave context menu carries three processing options:

- Off: Elastic Wave is not enabled for the clip (Default).
- Voice: Geared toward human speech or singing. Bear in mind it's a poor fit for any other material.
- General Purpose: Ideal for music and effects.

### Elastic View

Elastic view reveals Elastic Wave “time points,” which resemble Resolve keyframes but aren't quite the same. Keyframes stand for a point in time together with a value, whereas Elastic Wave time points stand for only a point in time.

With Elastic View on, time points become visible on the selected clip.

### Elastic Wave time points

### Elastic Wave disabled

When it's off, the time points stay hidden, yet the info lane still flags that Elastic Wave is on with the Elastic Wave icon.

### Clearing Timing Points

“Timing points” are the movable Elastic Wave control points that stretch or squeeze a particular region of a clip. Choosing “Clear Timing Points” wipes out (deletes) every selected point inside a clip. Elastic Wave is able to operate in the Edit window, where video editors might want spoken word performances re-timed so that, as the audio shifts, the video follows that retiming to stay in sync. On the Fairlight page, by contrast, video re-timing is turned off so you retain independent control over the audio file.

### About Audio Plugins

When in FlexBus mode, there's no cap on how many single or multiple plugins you can apply to clips and tracks. There is, however, a ceiling of 480 under Fixed Bus Legacy. You reach plugins through each track's control strip, or through the Inspector, which opens the door to both clip and track plugins.

### Fairlight FX

Fairlight FX are proprietary DaVinci Resolve-specific plugins running natively on macOS, Windows, and Linux, delivering high-quality audio effects with professional features to every DaVinci Resolve user on every platform. Most Fairlight FX plugins—Channel Dynamics and EQ included, along with dynamics processors such as the Multiband Compressor, Limiter, Reverb, and Ambisonics Meter—run Ambisonics native and deliver multichannel processing.

### VST and VSTi

VST (Virtual Studio Technology) is an audio plugin standard that Steinberg created. The VST standard opens the door for third-party developers to build plugins usable inside VST host applications, or to build VST host applications themselves. The Fairlight page handles VST effects from Mono right up to 7.1 and beyond. You can insert these effects on mono channels or Link Groups, and compatible VST Ambisonic effects work on Ambisonic tracks or busses.

Drop a stereo VST effect onto an LCR, LCRS, or 5.1 Link Group, and the left plus right channels are routed on their own to the Link Group's left and right channels. DaVinci Resolve supports VST3. VST effects are at your disposal on macOS and Windows workstations, yet Linux misses out. VST Effects versus VST Instruments (VSTi) A VST effect is one type of VST plugin built to process audio. Such an effect might take the form of a Reverb, Compressor, or EQ. VST Instruments, on the other hand, typically generate sound or replay sampled audio. VSTs have quickly displaced hardware synthesizers and dedicated samplers thanks to their flexibility, repeatability, and low cost.

### Audio Units

Audio Units is an audio plugin API that Apple created for macOS workstations. As with VST, Audio Units (AU) can either process audio or operate as instruments. Compatible AU Ambisonic effects work on Ambisonic tracks or busses.

### Using Audio Plugins

Fairlight FX come pre-installed with every DaVinci Resolve installation. Install extra VST or Audio Unit effects on your workstation and they show up in the Audio FX panel of the Effects Library, sorted into separate categories.

### Audio plugins in the Effects Library

A click at the far right of any effect tags it with a star as a favorite effect. Do that and the favorited effects collect into their own Favorites area down at the foot of the Effects Library Bin list, while they also surface up top in the Effects button's menu on the Mixer whenever you click the “plus” button.

Stars mark a flagged favorite effect; right now every favorite is filtered Audio plugins let you drop effects onto single audio clips or an entire track's worth of audio—to layer on creative qualities like echo or reverb, or to tackle mastering tasks via noise reduction, compression, or EQ.

### Applying Plugins

Methods of applying audio plugins to clips on the Fairlight page:

- Putting an audio effect on a clip: From the Audio FX panel of the Effects Library, drag any effect onto whichever Timeline clip you want it on.
- Putting an audio effect on several clips: Highlight every clip you want the audio effect on, then drag any effect out of the Audio FX panel of the Effects Library onto any one of the highlighted clips. Once a plugin lands on a clip, a badge shows up to the left of that clip's name bar in the Timeline, signaling that an effect is on it.

A badge marks Timeline clips that carry applied audio plugins. Ways to apply audio plugins to tracks on the Fairlight page:

- Putting an audio effect on a whole track in the Timeline: Drag any effect from the Effects Library straight onto the track header.

Applying an audio effect to a whole track via the Timeline

- Putting an audio effect on a track or bus in the Mixer: From the Audio FX panel of the Effects Library, drag any effect onto whichever Timeline clip you want it on.

Adding an audio effect across an entire track by dragging and dropping onto the Mixer

- Putting an audio effect on a track or bus through the Mixer controls: Click the plus button on the channel strip of the track you're effecting, then pick an effect from the dropdown menu that opens. Every filter sits within categories so they're easier to track down. If you've starred any filters in the Effects Library as favorites, those favorite filters land at the top of the plus button's dropdown list.
- Copying audio effects from one mixer channel onto another: Hold the Option key while you click and drag the effect to the channel and slot you want it copied to.
- Reordering audio effects within the Mixer: Click and drag the audio effect over to whatever slot position you want.

Adding an audio effect across a whole track using the Mixer's built-in controls TIP: The categories that VST and Audio Units effects fall under inside the Mixer are editable over in the Audio Plugins panel of the DaVinci Resolve System Preferences window. Each plugin on a workstation lists in the Available Plugins list, and a click within the Category column gives you a dropdown menu for changing categories.

NOTE: This does not apply to Fairlight FX plugins.

### Editing Plugin Parameters

To edit a clip’s audio plugins:

- Select that clip and open the Inspector. Every audio plugin applied to that clip turns up in the Effects tab, with that effect's controls showing directly in the Inspector.

To edit a track’s audio plugins, do one of the following:

- Click an empty spot in the Timeline header to select that track, then open the Inspector. Click that effect's custom UI button to bring up its controls.

The custom UI button for audio plugins in the Inspector

- Hover the pointer over the plugin's name in the Mixer's Effects area, then click the custom UI button to bring up its controls.

The custom UI button for audio plugins in the Mixer Almost every Fairlight FX, VST, and Audio Unit audio plugin carries a custom user interface that makes handling that effect's controls far easier. These can be opened from inside DaVinci Resolve.

The custom audio effect interface for iZotope RX Voice De-noise

### Working with Plugins in the Inspector

Methods of working with audio plugins in the Inspector:

- Reordering several audio effects on a clip: Reach for the move up or move down buttons sitting in an effect's title bar, just left of that effect's Trash Can button.
- Switching an effect off or back on: Click the toggle button sitting at the far left of each effect's title bar.
- Getting rid of an effect: Click the Trash Can button.
- Resetting any effect parameter: Click the Reset button over at the far right of whichever parameter you're resetting.
- Expanding or collapsing one effect's parameters: Double-click the title bar.
- Expanding or collapsing the parameters of every effect: Hold down the Option key and double-click any effect's title bar.

Once you've put them on a clip or track, audio plugins can also be keyframed or automated exactly like volume and pan settings, to build dynamic audio effects that shift over time.

### Sidechaining

DaVinci Resolve supports sidechaining for compatible Fairlight FX, AU, and VST plugins, which lets you momentarily pull down a target track or bus's level by way of the audible signal off a source track or bus. Known too as “ducking,” the technique earns its keep when multiple tracks jostle for space in a mix because they share part or all of the same frequencies—say, a track or bus holding dialogue next to a bus where a crowd cheers at a sports event. Above, the dialogue is routed into the sidechain input of a compatible dynamics plugin (a compressor or limiter, in other words) on the crowd-noise Mixer channel. With the dynamics controls set up right, the Dialogue channel's voices gently and modestly drop, or attenuate, the crowd noise's level, so the voices stand out more sharply in the mix. As soon as the dialogue stops, the cheering rises back to where it started.

### Sidechain controls

### To use sidechaining

- Bring up the compressor or limiter on the Mixer channel carrying the crowd noise.
- Pick the Dialogue channel from the source dropdown up top in the plugin,

just right of the Listen button. That's the audio you're leaning on to attenuate the cheering crowd's level. Choosing a bus as the ducking source lets several sources drive the changes in your target track.

- Click the On button—it goes red—signaling that the Sidechain (S/C) function is now active.
- Adjust the controls to taste as your mix plays, keeping the effect natural-sounding throughout. Feel free to experiment with the Channel Dynamics plugin's Compressor section, or with the Fairlight FX Limiter.

To dig deeper into sidechaining via the Channel Dynamics plugin, turn to Chapter 177, “Mixing in the Fairlight Page.” To dig deeper into sidechaining via the Fairlight FX Limiter, turn to Chapter 181, “Fairlight FX.”

- A click on the Listen button lets you monitor the incoming signal whenever you need to verify that the right input signal is reaching the Limiter. The button glows yellow while active.

### Applying Audio Plugins to Busses

Audio plugins go onto Main and Sub buses the same as any other track, so you can apply whatever audio mastering effects individual submixes call for, or even a whole main. TIP: Plugins can be assigned in a hurry across a chosen set of channel strips, or to all of them, by holding the Option key (Mac) or the Alt key (Windows) for every selected track, or Command-Option (Mac) or Control-Alt (Windows) for every mixer channel strip, prior to performing the operation. Such shortcuts can cut plenty of time from your workflow.

### Dealing With Processor Intensive Plugins

As you stack more and more plugins straight onto clips in complicated mixes, you may find you don't have the processing power to play every audio track and effect in real time. When that happens, there are two routes to lighten the load that audio clip effects place on your workstation.

### Caching Audio Clips With Plugins

One fast fix is to manually switch on caching for one or more selected audio clips carrying audio effects, which lifts your project's performance. Once an audio clip is cached, all the plugin effects are “baked in,” and that clip's audio waveform refreshes to reflect the changed audio. Cached clips show a small badge to the right of the FX badge in the clip's name bar.

A cache badge signals that this audio clip carries cached effects The action is non-destructive and leaves the source media of cached clips permanently untouched. A cached clip's plugin parameters remain yours to tweak at any time. Bringing up a cached clip's graphical controls briefly pauses audio caching, and when you're done, the clip re-caches by itself and refreshes its waveform to mirror the change, provided Cache Audio Effects remains enabled.

To cache audio effects for one or more selected clips:

- Right-click an audio clip that has a plugin on it and pick Cache Audio Effects to turn on audio effect caching for that clip. Right-click one clip among several selected ones and you turn on Cache Audio Effects across every selected clip at once. From then on, that clip stays cached (and re‑cached each time you alter the plugin's parameters) until you manually turn audio caching off.

To disable audio caching for one or more selected clips:

- Right-click a clip that has already been cached and pick Cache Audio Effects to switch off audio effect caching for it.

### Exporting Audio Clips With Plugins

A second way to lighten the toll audio clip effects take on your system is exporting the effected clip onto a separate layer. Doing so creates a brand-new piece of audio media carrying the effect “baked in,” saved to the directory spelled out in the “Save clips to” field, which lives under the Capture and Playback panel inside the Project Settings. To bounce one or more selected audio clips that carry effects onto a separate layer:

- Right-click an audio clip that has a plugin on it and pick Export Audio Files. Right-click one clip among several selected ones and you're offered choices for what to export from each selected clip all at once. Once exported, clips hold no editable effects, yet you can always choose View > Show Audio Track Layers to reveal the original underlying clip, which still keeps the original plugin effect; from there you can unmute it, move it back up top, edit the effect, and export a fresh version of the clip that arrives as the topmost layer.

To learn more about exporting clips to files, turn to Chapter 175, “Editing Basics in the Fairlight Page.”
