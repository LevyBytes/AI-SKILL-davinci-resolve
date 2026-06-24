# Multicam Editing (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Multicam Editing

When your footage was captured at the same moment by several cameras, the Multicam Editing features in DaVinci Resolve let you build multicam clips that you cut together through a visual switcher. There are also separate controls for swapping the angles of multicam clips that you have already placed into the Timeline.

### Introduction to Multicam Editing

For programs where a performance, an interview, or some event was captured by several cameras rolling at once, DaVinci Resolve supplies dedicated multi-camera editing features — multicam editing for short. Cutting with these features happens across three stages:

- To begin with, you assemble multicam clips out of each separate camera angle (these are known as “ISOs,” or isolated cameras).
- Next, you place the multicam clips you just built onto a timeline.
- Finally, you switch on the Multicam Viewer, at which point you can begin cutting and switching between

angles, much like a director working a live multi-camera show. The steps below walk through each of those stages, plus the choices you have at every step.

### Creating and Modifying Multicam Clips

The very first thing required is to build at least one multicam clip. To make a multicam clip: 1 Bring every ISO (isolated camera) clip belonging to the multi-camera performance or event you intend to edit into the Media Pool. 2 Highlight all of the clips that should be synced as a group, right-click that selection, and pick “Create Multicam Clip Using Selected Clips.” 3 Once the New Multicam Clip Properties dialog appears, set the options described below:

### New Multicam Clip Properties dialog

Start Timecode: Displays the starting timecode for the multicam clip you are creating, derived either from the timecode of the sync point when Angle Sync uses timecode, or from the sync-point timecode of whichever clip carries the earliest timecode when Angle Sync uses waveform. Multicam Clip Name: Lets you supply a label more meaningful than “Multicam 1” for the clip you are about to make.

Frame Rate: Reports automatically the frame rate tied to the clips you picked. There is a Drop Frame checkbox available when your clips run drop frame timecode. Angle Sync: The technique that lines up every separate angle. When you sync angles by hand, you can rely on In or Out points placed inside each clip. When matching timecode was jam synced onto each camera shooting an angle, pick Timecode for a quick sync that is only as precise as the timecode itself. When every camera carried a microphone capturing the location audio at the same time, pick Sound so the form of each audio waveform aligns the angles. When you have placed your own sync point markers onto the clips by hand, pick Marker. Channel: When Sound is chosen as the Angle Sync type, you can pick which audio channel from the clip serves as the sync source. Angle Name: The technique that labels each angle inside the multicam clip you are building. Angles can carry Sequential numbering, draw on Angle or Camera metadata, or take the Clip or File name. Split Multicam at gaps: When Sound is your Angle Sync type, you can have the Multicam files split wherever there is a break in the audio. Detect clips from same camera: Switching on this checkbox causes several clips recognized as coming from one camera to be gathered onto a single angle track within the resulting multicam clip. It also turns on the “Detect using” drop-down menu. Detect Using: Which metadata decides which clips originate from the same camera. The options are Camera #, Angle, Reel Number, Reel Name, and Roll/Card #, all of which you can edit in the Metadata Editor of the Media page, or you can pick Reel Name, which is set up — by hand or on its own — through the Conform Options found in the General Options panel under Project Settings, or alternatively through the Name panel of the Clip Attributes window. The Conform Options are covered more fully in Chapter 4, titled “System and User Preferences.” Move Source Clips to “Original Clips” Bin: Ticking this box sends each source ISO clip off to an Original Clips bin, tucking them aside once your multicam clip has been built. Use source audio channels: When ticked, this opens up the separate tracks and channels in the source clip’s audio (described further below). 4 After your options are set, click Create. Based on the Angle Sync method picked, a waveform analysis may show a progress bar, after which the new multicam clip appears in whatever bin is currently active in the Media Pool. Multicam clips carry a multicam badge in the lower left corner of the clip thumbnail.

A multicam clip showing its badge in the Media Pool

### Using Native Audio Channels from Source when Editing Multicam Angles

The multicam creation dialog offers an option called Use source audio channels, which is switched on by default. While it is on, the multicam clip is built in a mode that opens up the separate tracks and channels of the source angle. If that layout doesn’t work for you, untick the option and every audio track and channel for an angle is consolidated onto one adaptive track sized to hold all of the source’s audio channels. The multicam clip audio then sits on a timeline on an adaptive track. Native audio channels give you access to the individual tracks within the source angle. After a multicam clip is built with the option on, you can audition the audio tracks in the Audio Configuration section of the inspector File tab. With the option off, the multicam clip audio drops onto an adaptive track. With it on, the audio follows the track format of the source. Multicam audio clips can additionally pick alternative mono audio channels from the timeline clip context menu (Command right-click works for quicker access) and from the timeline clip audio configuration section in the Inspector.

### Selecting a Single Reference Audio Track for Multicam Clips

In DaVinci Resolve, multicam clips can adopt reference audio files (for example, those captured by a separate sound mixer) as the audio track shared by every angle, provided you attach an audio file to your multicam clip. While building the multicam clip, choose Reference Audio/Angle 1 in the Multicam Audio selector. That choice locates the first audio-only angle automatically and assigns it as the reference audio for all remaining angles. When a multicam setup contains no audio-only angle, the first angle is used automatically as the reference audio for the clip. While cutting multicam, you can reach the channels underlying the reference audio angle by Command-rightclicking the clip, just as you would with source audio multicam clips.

Setting up the Reference Audio track in a multicam clip

### Changing the Start Timecode for Multicam Clips

The starting timecode can be altered for both multicam and compound clips. To do this, right-click the multicam or compound clip in the Media Pool and pick Starting Timecode from the context menu. A Set New Start Timecode box appears; enter the fresh starting timecode you want and click OK.

### Converting Compound Clips or Timelines to Multicam Clips

Compound clips and timelines can be turned into multicam clips for simpler editing by way of the Edit page’s Multicam Editing interface. The conversion only runs one direction. There is no way to turn a multicam clip back into a timeline or compound clip. To hold on to the original timeline or compound clip, be sure to duplicate it first and convert the copy. To turn a compound clip or timeline into a multicam clip:

- Right-click the clip or timeline in the Media Pool and pick “Convert Compound Clips (Timelines) to Multicam Clips” from the drop-down menu.

### Logging and Editing Multicam Clips

After one or more multicam clips exist, you can review them either in the Media page or within the Edit page’s Source Viewer, then drop markers onto them (the markers are shared across every angle) to set up for the multicam edit you have planned. While reviewing multicam clips on the Media page, the Viewer Option menu lets you decide how many angles appear in the viewer.

Markers placed on a multicam clip within the Media page in readiness for cutting

### Setting up a Timeline for Multicam Editing

With one or more multicam clips built, getting them ready to edit is just a matter of cutting them into the Timeline, either by dragging the multicam clip from the Media Pool onto the Timeline, or by loading the multicam clip into the Source Viewer and then applying any of the editing methods on hand to drop it into the Timeline. After they are edited in, they sit in the Timeline like any clip, only with a multicam badge to the left of the clip name.

### Multicam clip badge in the Timeline

While you carry out a multicam edit, DaVinci Resolve runs the whole audio mix as you cut, so if you would like to take that chance to edit a master audio mix file or an extra piece of music to accompany the multicam clip, you are free to do so.

### Opening and Altering Multicam Clips

Once a multicam clip is built and dropped into a timeline, you can adjust it several ways by right-clicking it in the Media Pool and picking “Open in Timeline.” Doing so swaps the Timeline contents for a vertical stack of superimposed angles, one to a track, each shifted from the Timeline start so they line up with one another.

When opened, a multicam clip resembles a timeline holding a vertically stacked set of clips. With the multicam clip opened, you can prepare it for editing in several ways:

- You can nudge a multicam clip left or right to adjust its sync (picking an angle and using the Period (.) and Comma (,) “nudge” keyboard shortcuts is one handy approach).
- You can remove the track of an angle you have no use for (right-click the track header and pick Delete Track).
- You can reorder tracks to change the sequence in which angles show up (right-click any track header and pick Move Track Up or Move Track Down).
- You can rename tracks to alter the angle name that shows by default in the Multicam Viewer and that also surfaces in the Timeline once you do cut-and-switch editing.
- You can switch off audio or video tracks for angles you would rather not see yet don’t want to discard.
- You can grade each multicam angle on its own (covered later in this section).

When you have finished adjusting the multicam clip’s contents, close it via the path control at the bottom left corner of the Timeline. Click the name of the edited timeline to return, ready for the following steps. A path control lets you exit the multicam clip

### Performing a Multicam Edit

After you have built one or more multicam clips and edited them into a timeline, carrying out the multicam edit itself is straightforward. 1 Open the Timeline you made to contain the multicam clip or clips in your edit, and place the playhead where editing should begin. 2 Pick Multicam from the Source Viewer mode drop-down.

### Switching the Source Viewer to Multicam viewing

The Source Viewer switches to present every angle inside that clip as switching controls. 3 Pick how many angles to display from the drop-down menu at the lower right of the Source Viewer. On a computer that isn’t especially fast, you may have to cut down the number of angles you view to keep real time playback.

Choosing how many angles to view in the Multicam Viewer When the number of angles inside the multicam clip crossing the playhead in the Timeline exceeds what the Multicam Viewer is set to display, page controls show up to the left of this drop-down menu so you can choose which group of angles to see. You can move to another page of angles by one of these means:

- Click any dot to jump to that page of angles.
- Click the arrows to move among next/previous sets of angles.
- Choose Edit > Multicam > Previous Page (Option-Shift-Left Arrow) or Next Page

(Option-Shift-Right Arrow).

4 Choose whether your switch affects both audio and video together, video on its own, or audio on its own, with the Audio/Video selection buttons located at the bottom center of the Multicam Viewer. Identical results come from the menu: Edit > Multicam > Video and Audio handles both at once (Option-Shift-[ ); for picture by itself there is Video Only (Option-Shift-] ); and for sound by itself there is Audio Only (Option-Shift-\).

These buttons let you pick whether the switch affects video, audio, or both at once. 5 Begin playback, and as you watch the program run, do one of these:

- Click any angle in the Multicam Viewer; this drops a cut into the Timeline and moves to that angle. While you cut-and-switch, every cut lands in the Timeline at once as playback rolls forward.
- Option-click any angle to swap the angle on the current clip without adding a cut. This is useful whenever you later regret the angle you cut to and simply wish to change the whole stretch back to your previous cut. The same outcome is reachable from the menu via Edit > Multicam > Previous Angle, bound to Command-Shift-Left Arrow, or its counterpart Next Angle, bound to Command-Shift-Right Arrow.

While playback runs, the whole Timeline mix sounds along with whatever you are switching, keeping you in context.

A timeline being assembled through cut and switch. 6 Once your multicam cutting is done, simply halt playback. To start refining the Timeline by trimming, pick Source from the Source Viewer mode drop-down; from there you can re-cut and trim those multicam clips on the Timeline exactly as you would any others.

### Multicam Controls in the Source Viewer

When it is in Multicam mode, the Source Viewer offers four groups of controls for setting up and running multicam editing.

- Multicam Angle buttons: Every multicam angle shown in the Source Viewer is a button listing the angle name beneath it. Clicking one of these buttons drops a cut and switches the angle of the next clip, whereas Option-clicking swaps the angle of the clip sitting at the playhead without dropping a cut.
- Audio/Video Selection buttons: A click on any of these toggles which tracks — audio, video, or both audio and video — apply to the cut you make on the Multicam clip. Choosing Audio yields an audio-only cut, choosing video yields a video-only cut, and audio and video cuts the pair together.
- Multicam display drop-down: Sets the count of angles shown as you switch. Depending on how your workstation performs, lowering the angle count can boost playback while you edit. The choices are a grid of 1x1, 1x2, 2x2, 3x3, or 4x4 angles to view.
- Multicam Page buttons: When more angles intersect the Timeline playhead in the multicam clip than the Multicam Viewer is currently displaying (set by the multicam display drop‑down), page controls turn up that let you pick a particular set of angles. A click on any dot jumps straight to that page, while the arrows step through the next and previous groups of angles.

### The Source Viewer showing Multicam switching controls

### Multicam Keyboard Controls

A complete set of keyboard shortcuts is also available for multicam editing.

- Multicam Cut: (Clip > Multicam Cut submenu) Tapping number keys 1 through 9 performs a cut-and-switch, identical to a click on one of the angle buttons of a multicam clip in the Source Viewer.
- Multicam Switch: (Clip > Multicam Switch submenu) Tapping Option-1 through 9 performs a switch, identical to an Option-click on one of the angle buttons of a multicam clip in the Source Viewer.
- Previous/Next Angle: (Edit > Multicam submenu) Tapping Command-Shift-Left or Right Arrow steps you to whichever angle comes before or after. The same controls also loop around to the first or last angles within the multicam clip.
- Audio/Video Switching: (Edit > Multicam submenu) Tap Option-Shift-[ to make the Multicam Viewer cut or switch Video and Audio in tandem. Tap Option-Shift-] for the Multicam Viewer to cut or switch Video only. Tap Option-Shift-\ for the Multicam Viewer to cut or switch Audio only.
- Previous/Next Page: (Edit > Multicam submenu) Tapping Option-Shift-Left or Right Arrow steps you to whichever page of multicam angles comes before or after, in cases where the angle count exceeds what the Viewer’s current multi-angle setting can display.

### Editing Multicam Clips in the Timeline

For editing and trimming, there is no practical difference between multicam clips and clips of any other type. Since what you really add are through edits within one clip, any edit can be discarded by selecting it and tapping Delete. What sets multicam clips apart is that angle switching is always on the table, whether from the Multicam Viewer or right inside the Timeline through each clip’s contextual menu. To swap the angle of any multicam clip in the Timeline:

- Right-click any clip and pick a fresh angle from the “Switch Multicam Clip Angle” submenu. That also lets you change angles without resorting to the Multicam Viewer. Should you want to strip all unused angles from a multicam clip and “flatten” it down to a single Timeline clip, there is a command for the job.

To flatten a multicam clip in the Timeline:

- Right-click any clip and pick Flatten Multicam Clip from the contextual menu. Choose either Copying Multicam Grades, which applies the current color grade across the flattened angles, or Retaining Grades from Angles, which holds onto whatever color grades each individual angle received. All unused angles drop away, the clip shortens if it held black tails left by another unused angle, and what remains is a single plain clip in the Timeline.

To Match Frame to the angle of any clip set up for multicam in the Timeline:

- Set the playhead over the frame in the Timeline you wish to match and press F. The exact frame from the referenced mulitcam clip shows up in the Source Viewer, with its correct angle already selected.

To Match Frame to the multicam clip in the Source Viewer:

- Load the multicam clip into the Source Viewer. Use the jog bar to reach the frame you want and press F. The Timeline playhead moves to that exact frame within the referenced mulitcam clip shown in the Source Viewer. Should the frame you chose not exist in the Timeline, pressing F simply has no effect.

To cut an angle of any multicam clip straight out of the Source Viewer:

- You can drag any multicam angle straight from the Source Viewer onto the Timeline. The clip’s length is set by the In and Out point selection of the clip.

### Referencing a Line Cut

On occasion a production hands you what is termed a “line cut.” This is a pre-edited rendition of the program, cut live on the switcher and recorded during the performance or event, intended as a reference for your own work. Should that line cut reach you in movie form, bring it in as an Offline Reference Movie, then hold it up against the Timeline by way of the Source Viewer’s Offline Reference Movie mode on the Edit page. For more about checking an Offline video against a timeline within the Edit page, refer to Chapter 55, “Preparing Timelines for Import and Comparison.”

### Multicam SmartSwitch (Studio Version Only)

DaVinci Resolve 20 introduces a new AI-powered multicam feature named Multicam SmartSwitch, which examines every multicam camera angle and cuts automatically to the angle it judges best, going by who is currently speaking. Multicam SmartSwitch relies on more than the audio track to settle on the strongest angle; it also factors in further video signals — for instance lip motion inside the frame and whether a shot reads as wide or as a close up. Having learned from thousands of hours of multicam footage, Multicam SmartSwitch shines at handing you a strong first pass while you refine what is left.

Selecting a multicam clip to be used with Multicam SmartSwitch To set Multicam SmartSwitch loose on your multicam clip so it cuts on its own: 1 Assemble a multicam clip in the Media Pool out of every separate camera angle clip, in the manner described earlier here. 2 Cut that multicam clip onto the timeline. 3 Right-click the clip and choose Multicam SmartSwitch from its context menu. 4 Dial in the appropriate settings and parameters within the Multicam SmartSwitch tool. 5 Click Analyze.

### Multicam SmartSwitch analyzing the multicam clip

Now Multicam SmartSwitch will study every video angle and audio track and select the angle it considers strongest for the situation. This may take a while, depending on how long the multicam shoot runs and how many camera angles were used.

### Multicam SmartSwitch finished cut on the timeline

Once it is done, a fully cut version of your multicam clip waits for you in the timeline. If a choice Multicam SmartSwitch made isn’t to your liking, swapping the camera angle is easy: rightclick it and pick a different one from the Switch Multicam Clip Angle context menu, or use the standard trim tools to shift the edit point.

### The Multicam SmartSwitch tool

### Multicam SmartSwitch Settings

You can configure parameters on the Multicam SmartSwitch tool that change how it reaches its cut decisions.

- Angle Switching: Tunes the timing of the edits. Minimum Edit Duration: Sets the shortest an edit can run. No matter what unfolds in the cut, Multicam SmartSwitch will not switch angles until this duration ends. Edit Change Delay: This lets you specify the lag between someone speaking and the edit changing.
- Wide Angle Setup: Much like a technical director, Multicam SmartSwitch tends to lean on wide angles to cover situations such as people talking over one another and silences. You can fine-tune those behaviors here. Automatically detect wide angles: Tick this box to let Multicam SmartSwitch pick what it regards as wide shots on its own. Wide Angle: When you have a particular wide shot in mind for coverage, you can select it manually here. Wide Angle Frequency: How often Multicam SmartSwitch should return to the wide shot. The options are Low, Medium, and High. Use wide angle for intro and outro: Tick this box to begin and end the multicam clip on a wide shot. Use wide angle for silence: Tick this box to revert to the wide shot whenever nobody is speaking.
- SmartSwitch Setup: Establishes which kinds of media the analysis draws on. Switch: The cuts can be set to Video Only, or you can have them join Video and Audio tracks at the same time. Use Audio Only Fast Analysis: Tick this box so the pass leans solely on the audio rather than examining the picture too. It is much quicker and shows up only under certain modes.

### Grading Multicam Clips

In the Color page, multicam clips look like any other clip. Each angle inside a multicam clip, however, carries its own grade (unlike the Take Selector covered later, where all takes share one grade). When you grade a multicam clip, you are in fact editing the grade of whichever angle is currently exposed in that clip. To reach every angle within a multicam clip for grading, right-click it and pick “Open in Timeline” to lay out each angle in a superimposed stack. Then you can open the Color page and grade whichever angles you like, whether or not they are visible back in the Edit page. You might do this to bring the various angles into closer agreement, or to pre-grade all of them with the look you want ahead of multicam editing. You also have to use “Open in Timeline” to reach and adjust the camera RAW settings when your footage was captured in a RAW format.

A multicam clip opened on the Color page lays bare every one of its angles for grading one by one. Since opening such clips in the Timeline yields a vertical stack of superimposed clips, you will want Unmix switched on in the Color page viewer so the angle you have selected is actually visible in the Thumbnail Timeline while you work.
