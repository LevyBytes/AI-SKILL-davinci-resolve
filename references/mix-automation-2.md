# Mix Automation (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Follow these steps to capture automated moves on any audio control within any control strip: 1 Bring up the Automation toolbar and carry out the following three preparatory steps: a) Decide whether you intend to write fresh automation or to trim automation that's already on record. Write mode suits the first time you record automation, or any time you're replacing earlier automation with entirely new values. Trim mode suits situations where you're making incremental adjustments to automation recorded earlier. Keep in mind that, for now, Trim mode behaves as a delta trim system only when fader positions sit at zero (unity) on Fairlight control surfaces. b) After that, pick Touch and On Stop behaviors that fit the type of automation recording you're about to do. 2 Position the playhead at the start of the timeline section you want to record automation across. 3 Then start playback by any means (Spacebar, L, Play button, Fairlight or third-party audio control surface), and apply whatever changes you like to the controls you armed for automation recording. As you adjust them, the affected fader control glows red to signal that automation is being recorded. 4 Once you've finished, stop the transport by any means (Spacebar, K, Stop button, third-party or Fairlight audio control panel). Recording of automation ceases right along with it.

### Recording Automation for Specific Individual Tracks

Follow these steps to capture automated moves on controls within control strips you've specifically armed: 1 Bring up the Automation toolbar and carry out the following three preparatory steps: a) Decide whether you intend to write fresh automation or to trim automation that's already on record. Write mode suits the first time you record automation, or any time you're replacing earlier automation with entirely new values. Trim mode suits situations where you're making incremental adjustments to automation recorded earlier. b) After that, set Touch to Off, which turns off blanket automation recording and obliges you to arm the particular tracks you wish to automate. 2 Click the automation arm button situated above the fader of whichever Mixer track or track header you want to record automation onto. Even with the Touch control set to off, moving a control on an armed channel strip records automation in Latch mode.

The automation arming button above a fader in the Mixer

The automation arming button in the track header

3 Position the playhead at the start of the timeline section you want to record automation across. 4 Then start playback by any means (Spacebar, L, Play button, Fairlight or third-party audio control panel), and apply whatever changes you like to the controls you armed for automation recording. As you adjust them, the affected fader control glows red to signal that automation is being recorded. Should the Timeline be showing the very automation data you're recording, you can watch the new automation drawn live, in red.

New automation line in red while being recorded

5 Once you're done, halt playback by any means (Spacebar, K, Stop button, Fairlight or thirdparty audio control panel). Automation recording halts at the same time. Displayed automation shifts to green after recording ends. If the result isn't to your liking, you can undo and begin again, or edit the automation through the methods covered later in this chapter. Alternatively, you can move the playhead back and overwrite automation with new automation whenever you wish.

### Automation Preview Mode

Preview is one more mix automation workflow, made specifically for working across scene-based material. With it on, mix items that are in preview aren't governed by previously recorded automation, so they react to their controls manually. Afterward, those items can be switched into write (or trim) to lay down actual automation. As a rule, Preview mode serves to try out new mix settings on one specific stretch of a timeline while other stretches already hold recorded automation data. Preview mode stops previously recorded automation from moving the controls you're trying to adjust within a targeted section. Once you're satisfied with the new adjustments, they can be committed to the targeted section. Preview mode releases the faders (along with other controls) from automation control and lets you move them freely as you experiment with various levels and settings. Normally, moving one or more controls means writing automation data for them, but switching into Preview mode lets you play with the controls as much as you wish without committing anything, writing automation data only when you're ready. To bring enabled mix items into the Preview state, first enter Preview mode by doing one of the following:

- Toggle Preview in the Automation toolbar.
- Press the Preview key on the Mix page of the Fairlight controller.

Once Preview is engaged:

- Individual parameters can be switched into Preview Touch Latch.
- The AUTO key beside a fader can be used to preview every enabled parameter on that channel.
- The Auto button on the screen mixer strips is available for this too.
- While Preview mode is active, every parameter sitting in Preview is marked with a BLUE automation indicator.

After you're in Preview mode, you can move mix items into write (or trim) through:

- Dropping in manually via the Fairlight > Automation > Punch In menu choice.
- Dropping in manually with the In key on the Fairlight controller.
- An automatic drop-in based on the Active In and Out points on the Fairlight controller. Once a parameter is enabled for Preview, it holds that state no matter how the transport starts and stops. That differs from placing mix items into WRITE, which has to be redone after every transport stop.

Other Preview-related operations include:

- Populating a range marked by In and Out points using every parameter that's presently in Preview.
- Sliding each parameter from the value it holds at the Range In point over to its Preview value at the Range Out point.

### Automation Active Range

Using the Automation Active Range, you can designate just one specific range on the timeline for automation recording, so that anything beyond that range stays “write protected” and remains undisturbed.

- To switch on the Active Range, pick Fairlight > Automation > Active Range, where you're able to mark the Active Range In/Out points, or to enable or disable the Active Range.
- After a range is set, automation writing happens only within that range.
- You can pick whichever automation mode you'd like to work in (e.g., Snap).
- After playback gets underway, every bit of automation data generated ahead of the range is handled automatically in

Preview mode (without your having to flip the Preview switch on) right up until you hit the Active Range in point. Once you're inside the Active range, automation recording begins.

- When the range ends, automation recording is punched out for you automatically.
- Switching the Active Range off is done by clearing the checkmark on Fairlight > Automation > Active Range > Enable.

NOTE: Whatever controls sit in Read mode keep playing back their automation no matter what state the Active Range is in. A red bar marks the Active Range along the ruler; automation data gets written inside that range

### Viewing Automation in the Timeline

Once automation has been recorded against a supported plugin parameter or a Mixer channel control, picking it out and displaying it on the matching timeline track is possible through one of the approaches outlined below.

### Right-Click to View Automation

Fairlight lets you pick out and display track automation by right-clicking parameters on Fairlight FX, on supported Audio Unit or VST plugins, or on Mixer channel controls. The name of that parameter or control shows up in the track header, while its matching automation curve appears in the Timeline. This is a real time-saver, particularly when automating supported plugins that carry a long parameter list, such as a parametric EQ or a mixer channel strip emulation.

### The Automation Dropdown Menu

With automation switched on through the Toggle Automation button, the Automaton dropdown menu on the track header lets you pick which automation curve to display; the available choices cover Fader, Mute, Pan, EQ, Compressor, Limiter, Aux, Plugins, and Misc controls.

Mixing automation for the Fader shown in the Timeline NOTE: While you're looking at Fader Level automation on a track routed to a VCA, the curve for that VCA's automation shows up as well.

### Overwriting Automation

After automation has been recorded for a given clip, you can overwrite it on later passes. With either of the recording approaches described earlier, adjusting the level of a track control that already holds recorded automation shows a red line indicating the new level against the level recorded previously.

Setting new levels to overwrite previously recorded automation displays a red line Hitting play to actually capture this new automation overwrites the earlier levels at this new value.

### New automation overwrites the previous levels

Copying, pasting, and erasing of automation data is handled under the Fairlight Menu > Automation > Copy/ Paste/Erase.

### Automation Follows Edit

As you edit your timeline, you get to decide whether automation travels along with clips as they move or stays pinned to its place. It's on by default, but you can change that by unchecking Fairlight > Automation > Follows Edit. While it's enabled, any time a clip gets moved or edited on the Timeline, whatever automation you'd written across its range comes along too, so that as edits change, the automation tied to a given clip range stays intact. It also proves immensely handy during an initial edit of audio clips that carry automation data. Say you have a recurring sound effect panning left to right; automate that pan onto the audio clip first. As that clip is copied throughout the Timeline, it keeps the same panning automation for every fresh instance. That can be very handy for all sorts of edits needing identical automation data across audio clips in a timeline.

Bear in mind, though, that Automation Follows Edit should be switched off when copying and pasting clips or sequences whose applied automation has no bearing on the new edits. While Automation Follows Edit is on, automation data “lives with” the time range it originated in. Anything of that sort, like volume or panning, rides along with clips. So if an entire section is deleted, all the automation inside the clips in that section is deleted as well. If a section of clips is relocated within the Timeline, all the automation embedded in those clips moves with them to the new spot on the Timeline. With automation switched on in the Fairlight toolbar, the Automation Follows Edit button shows up.

The Automation Follows Edit button, positioned just left of the toolbar's Flag button

### Editing Automation

While automation is switched on (the Toggle Automation button is active), the Pencil tool appears. Paired with the Focus mode, these tools let you edit automation in a variety of ways.

The principal tools for editing automation come from Focus mode. Enabling automation (with Toggle Automation on) brings up the Pencil.

### Adjusting and Deleting Automation Keyframes

The Focus tools give you two distinct ways to adjust automation.

### Adjusting Individual Keyframes

With the Focus tools, you can grab any automation keyframe and drag it up or down and left or right (limited by its neighboring keyframes) to adjust it directly. While zoomed in, this can be a handy way to make exact adjustments. The portion of automation altered by the keyframe you're dragging stays green to show the new curve forming, and a tooltip displaying the value currently being adjusted appears, while the data made earlier shows in gray. Once you let go of the mouse button, the curve is adjusted

A lone keyframe under adjustment, with its earlier level rendered in gray Adjusting and Deleting Multiple Keyframes There's also the Focus mode I-beam selector tool, which lets you build a selection covering several keyframes, then move or delete them.

Pick a span of keyframes with the Focus mode I-beam selector Should you delete the keyframes inside the range, the surviving stretch of the curve levels off so it spans the selection's first keyframe through its last.

### Automation curve after deleting the selected keyframes

### Adding and Editing New Keyframes

For additional detail on drawing and editing keyframes, see “Working with Audio Keyframes on the Timeline” earlier in this chapter.

### Clear All Track Automation

If your goal is to wipe out every bit of automation tied to a track or bus, send and plugin automation included, right-click the track header and pick Clear Track Automation from the menu. A fresh window then opens, presenting the following choices in case you reconsider or wish to erase the automation:

- Cancel: To keep your automation data.
- Reset: Wipes every bit of automation and sends all the controls and parameters it touched back to their default

settings and values.

- Hold: Wipes every bit of automation while preserving the settings and values on all the controls it touched

and parameters.

### Fairlight > Automation Controls

The Fairlight > Automation submenu holds a set of commands that kick off various automation tasks. The commands are:

- All Read: Returns to Read mode every parameter that currently sits in Trim or in Write mode.
- Punch In: With Preview mode on, moves whatever parameters are presently in Preview (blue) over to

Write or Trim. With Preview mode off, it moves every Automation-enabled parameter across all selected channels into Write or Trim.

- Punch Out: With Preview mode on, moves any parameter sitting in Write, Trim or Preview over to Read. With Preview mode off, it moves every Automation-enabled parameter across all selected channels into Read.
- Fill Range: Whenever an active In and Out range exists in the Timeline, the present value of each parameter in Preview gets written across that range.
- Glide Range: While in Preview mode, it “glides” each parameter away from the value it holds at the Timeline's In point toward the preview value waiting at the Out point.
- Join Mix: Allows you to pick automation writing back up by hand in Latch mode, starting at the present level and traveling to whatever level you choose.

### Automation – Copy/Paste/Erase

The Fairlight > Automation submenu additionally provides dedicated local choices for Copy, Paste, and Erase of automation data. Copy/Paste lets you carry out powerful range-based manipulation of automation, or build a “snapshot” change in which all automation data is pasted at a single moment in time, letting every enabled parameter jump at once to new levels. Working with these commands means you have to spell out which automation parameters are affected by using the Automation Enables controls (the same ones that govern what automation data gets recorded). For instance, to affect fader, mute, and pan automation, you first have to turn on the enables for those parameters. Only the enabled parameters are affected.

NOTE: These commands work whether you're in Clip view or Automation view (for any parameter); what ends up affected is decided by the Automaton Enables rather than by which view you're in.

Enables configured so that copy, paste, or erase touches only Fader, Mute, and Pan data

- Copy: When an active In and Out range exists in the Timeline, Fairlight > Automation > Copy places onto the clipboard the automation data belonging to every selected channel and enabled parameter inside that range. Lacking an active In and Out range, the command instead grabs the data of all automated parameters across every selected and enabled item at the playhead (Snapshot mode).
- Paste: Drops in, at the active range or in point, all the automation data sitting on the clipboard for Automation-enabled parameters. Where an active In to Out range has been set, that range gets populated with whatever automation data was placed on the automation clipboard through Automation > Copy. Where no active In to Out range has been set, the entire automation clipboard is simply dropped in.

TIP: You can move Track Automation among Faders, Sends, and Direct-Out levels. To illustrate, the Fader Level automation from one track can be copied onto a different track's Send Level, and the other way around too. The clipboard's contents may well be directed at a separate channel set and/or a separate target time, just by picking a fresh in point or track selection. Where an active In to Out range has been set in the Timeline, and the clipboard carried Snapshot mode data at the moment of copying, this range gets populated with the static values from that snapshot data.

- Erase: When an active In and Out range exists in the Timeline, Erase removes the automation data of every selected channel inside the range, honoring all the Automation Enable buttons. With no range selected, nothing changes.

TIP: To strip all automation from a Timeline or set of tracks, select the whole timeline range, switch on the Automation Enable buttons for the automation types you mean to clear, and pick Fairlight > Automation > Erase. As an alternative, Fairlight > Automation > Mix List can serve to clear all automation off the Timeline.

### Automation – Mix List

With the Mix List, you can build and manage several mix “passes” plus complete routing and effects setups for one Timeline. Every stored mix can hold wholly different mix automation data changing over time, along with its own routing, plugin setup, track grouping, and so on. This ability is tremendously powerful and grants plenty of creative latitude for producing different versions of mixes (for instance shifting among stereo, 5.1, and Dolby Atmos as formats), or for working with entirely different plugin effects or different creative takes on the mix itself across all the automated parameters.

### The Mix List Window

So the Mix List proves useful for more than holding mix automation data; it can store a dynamic preset of practically anything about how the Mixer is set up. Bear in mind that the Mix List is tied to one specific Timeline and likewise can't be shared across projects. Even so, leaning on the Mix List can be handier than saving many separate versions of timelines or projects. The Mix List can sit as a floating window where the various mixes are visible, or it can stay tucked away until the moment you have to load or save another version. Using the Mix List Window:

- Set up your mix, including all routing and automation as you like.
- Once you've got a mix version worth saving, head to Fairlight > Automation > Mix List, pick “Save Mix,” and supply a name plus whatever notes you'd care to attach.
- From there you're free to alter your mix automation, any routing, and so forth, then store a new version, bring up a different one, or remove an existing mix.
- That “System” preset is a built-in system preset you can't change; feel free to disregard it.

The “New Mix” Dialog: Choosing “New Mix” within the Mix List window brings up a dialog carrying these options:

- Cancel: Lets you cancel the operation.
- Write All: Records the present levels of every control onto their automation curves, laying down a baseline

“snapshot” of all parameters.

- Empty Mix: Strips every bit of automation data out of the mix, keeping only the assignments, routing,

track group enables, etc. This choice gives you a straightforward way to begin “fresh” with a mixer setup on a new mix.

### New Mix dialog

### Playing Automation

Once you've automated a mix, playing it back just means moving the playhead to a spot on the timeline ahead of the recorded automation and starting playback. As the timeline runs, the onscreen controls for each automated parameter appear in green. They glide and refresh so the levels they captured are reflected. During playback, any control holding recorded automation is displayed in green.
