# Editing Basics In The Fairlight Page (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

4 With the playhead sitting over the part of the waveform you’ll treat as the frame for moving the clip, press Command-X to cut or Command-C to copy that clip (right-clicking a clip and choosing Copy or Cut works too). The clip lights up right away.

Cutting or copying a clip at the position of the playhead 5 From here, you have two routes for getting the cut or copied clip to the spot in the Timeline where you mean to paste it: a) Moving the playhead now drags the clip you cut or copied along with it, drawn as a ghost clip with waveform “attached” to the playhead at the frame you picked. Whether you drag the playhead with your mouse or work JKL to run the playhead through the Timeline, the cut or copied clip travels in step, so shifting the playhead repositions the cut or copied clip on that track. b) Should you want the cut or copied clip on a different track, lean on the Control-Option-Up or Down Arrow key shortcuts to switch the selected track; the ghost clip follows the change in track selection.

Positioning the cut or copied clip before you paste it

In this way, the playhead lets you line the ghost waveform up against the other audio clips around it ahead of pasting. 6 With the clip sitting where you want it, press Command-V to paste it at the spot you’ve picked (right-clicking a track and choosing Paste from the contextual menu works too). The clip turns solid, and that’s it.

### The pasted clip

Going about cut and paste this way makes it fast to cut or copy clips with keyboard commands alone, and the clip’s ghost overlay makes it easy to land the clip you’re pasting precisely where you need it, perfectly in sync.

### Using the Cut/Copy Head and Tail Commands

Four more commands make it easy to cut or copy stretches of one or more clips that cross the playhead — either from the In point up to the playhead’s current spot (the Head), or from the playhead’s current spot through to the Out point (the Tail). Here is how to cut or copy a clip’s head or tail and paste the result: 1 With these commands there’s no partial selection to make, so either the Selection (press A) or Range Selection (press T) mode will serve. 2 Select the track holding the clip you mean to copy or cut. When one or more tracks are already selected, the Control-Option-Up or Down Arrow key shortcuts let you shift the track selection state up or down so it lands on whichever tracks hold the clip you mean to cut or copy. 3 Run the playhead so it crosses the clip you mean to cut or copy at the frame you want to mark — either the head’s end or the tail’s start. Where the playhead crosses a clip on a selected track, that clip should select itself automatically. Bear in mind that even when you select a clip with the mouse without selecting a track first, the playhead should still be moved to cross the clip you’re copying or pasting, since doing so lays down a key reference point for the work ahead. 4 Pick Edit > Cut/Copy Head/Tail to lift the stretch of the selected clip you mean to paste. That stretch of the clip lights up right away. 5 From here, you have two routes for getting the cut or copied head or tail of the clip to the spot in the Timeline where you mean to paste it:

a) Moving the playhead now drags the clip you cut or copied along with it, drawn as a ghost clip with waveform “attached” to the playhead at the frame you picked. Whether you drag the playhead with your mouse or work JKL to run the playhead through the Timeline, the cut or copied clip travels in step so that shifting the playhead repositions the cut or copied clip on that track. b) Should you want the cut or copied clip on a different track, lean on the Control-Option-Up or Down Arrow key shortcuts to switch the selected track; the ghost clip follows the change in track selection. In this way, the playhead lets you line the ghost waveform up against the other audio clips around it ahead of pasting. 6 With the clip sitting where you want it, press Command-V to paste it at the spot you’ve picked (right-clicking a track and choosing Paste from the contextual menu works too). The clip turns solid, and that’s it.

### Paste and Remove Attributes

The Fairlight page carries Paste Attributes and Remove Attributes commands for copying and resetting audio parameters and effects, much like the matching commands on the Edit page.

### Clip Attributes Naming

Double-click any clip in the Timeline to reach the Clip Attributes window and rename the clip. A right-click still gets you to this window, opening the dropdown menu of options.

### Copying and Pasting Clip Attributes

With clips, it’s as straightforward as copying a clip, then selecting one or more audio clips, right-clicking another clip, and choosing Paste Attributes from the contextual menu. A dialog comes up so you can pick which audio attributes to paste before you click Apply.

### The Paste Attributes dialog in the Fairlight page

### Copying and Pasting Track Attributes

With tracks, things go a bit differently. Right-click a track header and choose Copy Attributes to grab every track setting and effect. Next, with one or more other track headers selected, right-click that selection and choose Paste Attributes. A dialog comes up so you can pick which track attributes to paste before you click Apply.

The Fairlight page Paste Attributes dialog, here carrying attributes across from one track onto another

### Removing Attributes

For clips or tracks alike, you can right-click and choose Remove Attributes to open a dialog where you pick which attributes to reset to their defaults. NOTE: Ticking the Volume check box in Remove Attributes wipes out every Clip Gain keyframe that’s been added to a clip.

### EQ, Level, and AI Dialogue Matching

To help lay a solid groundwork for a great mix, Fairlight puts forward three features that match unlike timeline clips by their tonal characteristics (EQ profile), their volume level, or their sonic characteristics, as laid out below.

### EQ Matcher

EQ Matcher comes in handy where, for instance, you need to swiftly carry the tonal characteristic (EQ Profile) of on-location dialogue recorded with one kind of microphone over to newly recorded dialogue captured in post on an entirely different microphone. Here is how to capture and apply an EQ Profile: 1 On the timeline clip you’re matching to, right-click and pick Clip Operations > EQ Matching > Capture EQ Profile from the contextual menu.

Timeline clip EQ Matcher contextual menu 2 The captured EQ Profile then goes onto another audio clip by either of these routes: Apply to Clip EQ: For every selected clip on the destination track, this drops the same EQ setting onto its Clip EQ plugin. Apply to Track EQ: Lays the EQ profile over the entire track. Up in the EQ section of the matching Mixer channel strip, the applied EQ curve appears.

A fresh EQ curve shown within a Mixer channel strip Apply to Automated Track EQ: Where a track holds several clips, each one needing its own EQ setting to hold the right tonal match through playback, this option earns its keep. The selection lets you swiftly write automation data, which reshapes the Track EQ curve for each clip as needed. Here is how to put the EQ profile onto an automated track EQ: 1 On the timeline clip you’re matching to, right-click and pick Clip Operations > EQ Matching > Capture EQ Profile from the contextual menu. 2 With the Toggle Automation button — found just right of the transport control — confirmed active (red), pick an EQ parameter out of the Automation drop-down within the destination Track Header, such as EQ > Band 3 > Gain. 3 On the first clip you’re targeting, right-click and pick Clip Operations > EQ Matching > Apply to Automated Track EQ. Do the same for each clip that follows on the track.

- As you repeat the this step, you’ll watch the automation curve shift with every application of the EQ Profile.
- Through playback, the EQ Curve display in the matching mixer channel strip shifts according to the automation data and Playhead position.

### Level Matcher

Level Matcher lets you swiftly and precisely line up the volume of unlike timeline clips with one another. Here is how to match your clip levels with the Level Matcher: 1 On the timeline clip you’re matching to, right-click and pick Clip Operations > Level Matching > Capture Level Profile.

Timeline clip Level Matcher contextual menu 2 On a timeline clip you mean to adjust, right-click and pick Clip Operations > Level Matching > Apply Level Profile. Do the same for whatever other timeline clips you’d like to change.

### AI Dialogue Matcher

AI Dialogue Matcher proves useful when you need to align the ambient quality of one timeline clip with another. In a dialogue replacement scenario, for instance, you may need newly recorded dialogue to sound as though it was captured in the same room as the rest of the on-location dialog.

### Timeline clip AI Dialog Matcher contextual menu

Here is how to put AI Dialogue Matcher to work: 1 On the timeline clip you’re matching to, right-click and pick AI Tools > Dialogue Matcher > Capture Dialogue Profile from the contextual menu. 2 After the audio is analyzed, right-click across the timeline regions you’re targeting and pick AI Tools > Dialogue Matcher > Apply Dialogue Profile from the contextual menu. With the dialogue profile applied, a checkmark turns up beside the Enabled option in the Dialogue Matcher contextual menu.

- Clicking that checkmark flips the dialogue profile on and off.
- Choosing Remove Profile strips the profile off the clip entirely.

### Audio Clip Layering

Audio layering is a special audio editing mode that lets you stack several audio clips in one track, where audio clips edited into the upper layers mute the overlapping stretches of audio clips on lower layers. With audio layering switched on, stacked audio clips behave much like stacked video clips set to 100% opacity, the ones on top hiding (or muting) the ones below.

An illustration of layered multiple-audio performance editing, in which the uppermost layer silences the overlapping stretches of audio clips sitting on layers below Audio layering earns its keep in any case where you’re piecing together segments of several takes into one voiceover, audio vocal track, or dramatic performance, since you can pick which segments to use by their stacked position in the pile of clips on that track, all while keeping the other takes underneath should they prove useful down the line. TIP: Track layering can be used on the Edit page as well.

To enable audio layering:

- Choose Timeline > Layered Audio Editing so a check mark shows beside the command. From that point on, all overlapping audio gets layered rather than overwritten.

To view audio layering: 1 Choose View > Show Audio Track Layers, which brings up the track layers belonging to every audio track — and to every lane inside a given audio track — across the Timeline. With layering on, space opens above each Timeline track, handing you a region for editing layered audio clips. 2 To bring an audio clip or segment in as a layer inside a particular audio track, drag it over from elsewhere in the Timeline or out of the Media Pool, then drop it into the empty space above whatever audio is already in that track.

Dragging one audio clip so it layers above another 3 Work the various stacked layers of audio so the segments of each take you like end up on top. Only the topmost clip segments will be heard. Audio segments that overlap beneath stay silent. To set another layer on top, drag it from where it is to the empty space at the top of the track.

Dragging a bottom audio layer to appear on top 4 Once you’re done editing clips in track layers, choose View > Show Audio Track Layers once more to tuck the individual layers away, so only the topmost clips show as a flat sequence in each track and lane.

Tuck the layers away and every audio layer collapses onto one track, looking as though the top clips overwrote what lay below — yet the silenced material beneath survives

### Audio Compound Clips

DaVinci Resolve handles audio compound clips, built just like any other compound clip — by selecting several audio clips, right-clicking one, and choosing New Compound Clip. On top of that, compound clips with video clips may now hold several audio items too. Open a compound clip that holds audio in the Edit or Fairlight pages — right-click an audio compound clip and choose Open in Timeline — and breadcrumb controls show up beneath the Timeline, letting you step out of the compound clip and back to the master Timeline.

An audio compound clip being opened; spot the path control down at the Timeline’s lower left

### Audio Crossfades

Any edit point between two audio clips with enough handles can take a Cross Fade transition, the same as with video transitions. Three approaches exist: drag and drop one out of the Effects Library; right-click an edit and pick an option off the contextual menu; or select an audio edit point and head to Timeline > Add Audio Only Transition (Shift-T). A Cross Fade transition is a fast, easy means of fading the outgoing clip’s volume down while at once fading the incoming clip’s volume up, which builds a smooth aural transition between two audio clips.

An audio Cross Fade transition applied between two clips Double-click a Cross Fade transition to open it into the Inspector, where these parameters come up:

- Duration: How long the transition runs, shown in both seconds and frames.
- Alignment: A dropdown for choosing where the transition lands in relation to the edit point it’s

applied to. The available settings are “End on Edit,” “Center on Edit,” and “Begin on Edit.”

- Transition style: Picking –3dB, 0dB, or +3dB pins the Fade In and Fade Out levels alike

to a single value. For more on what these levels signify, see the parameter that follows.

- Fade In/Fade Out levels: Three options act on the incoming and outgoing halves of

the Cross Fade effect on their own. 0dB lays down a linear fade (this is the default). +3dB lays down a boosted curve; applied to both Fade In and Fade Out, it can make up for sagging levels in the middle of a Cross Fade. –3dB lays down an attenuating curve, deliberately pulling the Cross Fade’s level down.

NOTE: Building and editing crossfades is possible on the Edit page as well as the Fairlight page.

### Fades and Crossfades

Working with fades and crossfades is part of audio editing on the Fairlight page. This section walks you through building these effects so you can segue smoothly between audio clips. A Dolby Atmos master file dropped on a timeline as a clip can take basic fades. Complex fades and batch fades, however, aren’t supported.

### Using Fades

As on the Edit page, every audio clip carries fader handles, which surface in the top right and top left corners once your pointer hovers over that clip.

Hovering the pointer over a clip surfaces its fader handles Drag one of these handles outward and you build a fade effect whose duration equals the distance you dragged the handle.

Creating a fade effect by pulling out one of the fader handles With a fade effect built, you can reshape the fade’s curve by dragging the handle that sits right atop the fader curve. Dragging the handle up and down changes the curve’s angle, while dragging it left and right changes the curve’s shape. This way, you can build fade effects of every kind.

### Adjusting the curve of the fade

### Batch Fade and Crossfade Editor in the Fairlight Page

Several fades become available to several clips with several tracks selected, greatly widening fade functionality. The Batch Fades window holds fade shapes for Fade In, Cross Fade, and Fade Out. You set the Fade Length by frame for each of these fade types, and an option lets you overwrite existing fades on the highlighted clips.

All of the settings in the Batch Fades window Each Fade type carries six options for precise use. When you add Fades between sources, settling the shape matters so only the media you intend lands in the fade. The curves show the ramping slopes of the fade. Every box carries similar controls for steering its own Fade type. 1 Beside the Fade type name sits the on/off toggle 2 Six Fade curves are there to build exactly the fade needed. 3 A Length box sets how many frames the fade spans, 4 A click box overwrites any earlier fades, where needed. The Crossfade box carries three extra controls. 1 Equal Power holds the signal level steady through the fade. 2 Equal Gain comes into play when crossfading media that could phase once combined. If a music cue is crossfaded, for instance, the fade’s mid-point could bring a jump in level or added phasing trouble. This option holds the gain across the fade for that sort of media. 3 Unlinked allows a different curve type on each side of the crossfade. This window holds onto whatever settings were last made, so after a run of Fade types is chosen, Batch Fades can be applied without reopening it — a single click from the Fairlight menu does the job across highlighted regions. Whatever you set in the Batch Fades window carries over to the Apply Batch Fades command in the Fairlight menu.

### Batch Fade options in the Fairlight menu

Here the graphic shows clips and tracks highlighted and set for Batch Fades to be applied.

### Tracks and clips highlighted for Batch Fades

The graphic below shows how the Batch Fades land. Clips that aren’t connected get Fade In and Fade Out. Clips that are connected get Crossfades. The Batch Fades window settles each of the Fade parameters and then lays them onto all of the selected clips. In this example, the Overwrite box was left unchecked. Compare the fades that were already there and notice they keep their original Fade length and shape.

Every one of the highlighted clips now carries fades drawn from the Batch Fades window.

NOTE: When the media runs too short, a dialog box warns you that there aren’t enough handles and that the fade couldn’t be created. From there you can choose to trim clips, skip clips, or cancel the Batch Fade. Cancel and you can then adjust the settings to better suit the media.

### Fade In and Out to Playhead

In the Trim menu sit two commands: park the playhead over a clip, and from where it sits you can call “Fade In to Playhead” or “Fade Out to Playhead.” Both the Edit and Fairlight pages support these.

(Left) Parking the playhead at the spot where a fade in should finish, (Right) Calling Fade In to Playhead

### Creating Crossfades With Overlapping Fades

Where a fade eases a single track of audio up or down, a crossfade eases two overlapping clips at once — one clip up and another down — for the aural equivalent of a cross dissolve. Two ways of building a crossfade exist in the Fairlight page right now. Both lean on clip layering so you can hold overlapping fades over overlapping clips. Here is how to build a crossfade by overlapping two clips: 1 Put a fade out on the end of one clip and a fade in on the start of another. Every fade added this way is linear by default, though you can reset them to whatever gain you like.

Adding fades to adjacent clips 2 Drag the first clip so it overlaps the second by the length of the fade you’ve built.

Dragging the clips into overlap; clip layering keeps the overlapping parts intact 3 Drop the clip. Clip layering keeps both overlapping fades intact, and a crossfade turns up in the Timeline.

### The resulting crossfade

Here is how to build a crossfade over two clips already layered: Drag the fader handle sitting at either the start or end of a layered clip, and a crossfade turns up on its own.

Creating a crossfade by adjusting the fader handle of a layered clip

### Using Crossfades From the Edit Page

You can add crossfades in the Edit page too, but they show in the Fairlight page as transitions in the Edit page style.

### The resulting crossfade

### Finding Clips in the Media Pool

On any clip in the Timeline, a right-click plus Find in Media Pool picks that clip out in the Media Pool for you — handy for times you’d like to cut another copy of it elsewhere in the Timeline, or work a different segment of it back into the same spot. NOTE: Automation Follows Edit whenever clips bearing embedded automation get moved or pasted out of the Timeline. Pull those same automation-bearing clips from the Media Pool instead and they show up in their default state, no automation attached.

### Changing Clip Color in the Timeline

With one or more clips selected in the Timeline, a right-click lets you recolor them and stay better organized. You might, for instance, set production audio clips holding dialog from different actors to different colors, or set clips with dialog, music, and effects to different colors so each clip’s purpose stands out at a glance.

### Editing Audio Clips in External Editors

While you’re working in the Fairlight page, you can process an audio file through a third-party application when needed — for those times you must lean on another application’s strengths to build an effect or fix an issue the Fairlight page can’t handle on its own. Setting this up starts with adding one or more applications to the External Audio Process list, which lives in the Audio Plugins panel of the System Preferences.

The External Audio Process list configured to send audio to Adobe Audition Here is how to add an external audio process: 1 In the DaVinci Preferences, open the System tab and pick the Audio Plugins panel. 2 Within the “Setup External Audio Processes” section, click the Add button. 3 Want a different name for the audio process? Double-click in the Name column and key one in. 4 In the new process’s empty Path column, double-click, then from the dialog pick an application to bind to that process. 5 From the dropdown menu in the Type column, settle on the kind of process you want it to be. With one or more external audio applications set up in Preferences, any clip in the Fairlight page can run through them: right-click the audio clip, then off the contextual menu’s External Audio Process submenu pick whichever application you want. Doing so makes a duplicate of that clip’s media, copied (bounced) into the directory spelled out by the “Save clips to” field within the Capture and Playback panel of the Project Settings. The external application then either opens or fires off as a command-line command — which one depends on how that external application was set up in Preferences. As soon as the bounced audio opens in the external application, process it however you need, then commit the changes by saving/rendering/outputting and overwriting the original copied audio media file. Changes don’t go unnoticed; DaVinci Resolve picks them up and reimports the altered result automatically as one more audio layer over the original clip in the Timeline. How an audio application is set up in the DaVinci System Preferences dictates how the bounced audio file gets handed to the external program. Three choices exist:

- Command Line: As a command line parameter, when your audio application can be run from the Terminal.
- Clipboard: By dropping the path to the bounced file on the clipboard, so you can paste it into the application that’s been launched automatically, or bring it in via a File > Open dialog.
- Reveal: By revealing the bounced copy in your workstation’s file manager, so you can drag and drop it onto the application that’s been launched automatically.

### Exporting Audio Clips to External Files
