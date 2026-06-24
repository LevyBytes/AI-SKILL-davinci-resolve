# Modifying Clips And Clip Attributes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Modifying Clips and Clip Attributes

After clips land in the Media Pool, you will often need to tweak them before they are ready to serve in your project. The ground this chapter covers is varied: resetting the clip attributes tied to each source clip so as to reinterpret video and audio attributes, timecode values, and clip names; turning LTC timecode that was laid onto an audio track into timecode you can actually use; carving lengthy clips down into more workable subclips; and assembling stereo clips out of left- and right-eye media.

### Adjusting Media Pool Clips in the Inspector

Media Pool clips can be edited straight from the Inspector even before you cut them into a timeline. Doing so lets you reset the parameters of your source media, so that whenever such a clip is later edited into a timeline it brings those fresh settings along. Ahead of editing, for instance, you might ready your footage by revising the clip’s file and RAW settings, tuning its audio levels and EQ, or handing it a particular lens correction, and so on. With those revisions made, every portion of the clip already carries the right Inspector parameters at the moment you drop it into your timeline. For fuller detail on working with the Inspector inside the Media Pool, consult Chapter 20, “Using the Inspector in the Media Page.”

### Changing Clip Attributes

The Clip Attributes window is where you can revise extra attributes across several clips in one pass. There is a degree of overlap between this window and other clip attributes you can edit straight from submenus in the Media Pool clip contextual menu. To change the attributes of one or more Media Pool clips on any page: 1 Inside the Media Pool, gather one or more clips by Shift-clicking, by Command-clicking, or by dragging a bounding box over them. 2 Right-click one of those selected clips and pick Clip Attributes. 3 Click to open the panel holding the attributes you intend to edit. With several clips selected, the act of making a change automatically ticks the checkbox for whichever attributes you altered. 4 Once done, click OK to commit the changes. Select clip attributes can likewise be edited on clips already cut into the Timeline. To change the attributes of one or more Timeline clips on the Cut, Edit, or Color pages: 1 Over in the Timeline, gather one or more clips through Shift-click, Command-click, or a dragged bounding box. 2 Right-click whichever of the chosen clips you like and select Clip Attributes. 3 Click open the panel containing whatever attributes you wish to revise. When more than one clip is selected, making any change ticks the checkbox of each attribute you touched on its own. 4 With that done, press OK to lock in the changes.

### Video Attributes

These bear on an individual clip’s frame rate, its geometry, and its data levels.

### The Video panel of the Clip Attributes Window

- Video Frame Rate: Should another application or recording device have stamped a clip’s frame rate wrongly, or should no frame rate metadata exist whatsoever, you can override the rate that DaVinci Resolve assigns to the source clip — either by picking a value from 1 to 120 fps in this menu, or by selecting Custom and typing anything from 1 to 32,000 fps (which makes room for high-speed and specialty-format footage). When you alter a clip’s Video Frame Rate, both its duration and its relative playback speed shift inside DaVinci Resolve, though the clip’s audio is left alone. Bear in mind that support for very high frame rate media does not promise real time performance at extreme rates; how well your workstation copes hinges on its configuration and on how fast your storage runs.
- Data Levels: Now and then you may have to set the data levels by hand for clips that DaVinci Resolve is not reading correctly, picking among Auto, Video, and Full.

To learn more about this setting and the way it shapes the image data throughout your project, turn to Chapter 9, “Data Levels, Color Management, and ACES.”

- Pixel Aspect Ratio: When a project mixes media of differing frame sizes, this drop-down lets you hand particular pixel aspect ratios to those clips. The Pixel Aspect Ratio can also be set to a value of your own to correct for assorted motion picture capture technologies. Pick Custom from the Pixel Aspect Ratio menu, then key a numeric value into the box beneath it. That value stands for the X within the 1:X ratio — enter 1.6, say, and you arrive at a pixel aspect ratio of 1:1.6.
- Horizontal and Vertical Image Flip: Alters the horizontal and vertical image-flip camera metadata on r3d clips, which helps with stereoscopic 3D projects shot on a mirrored camera rig that flips one eye’s media, or whenever a steadicam rig leaves clips upside down. Do not confuse these with the Flip Image controls found in the Color page’s Sizing palette.
- Image Orientation: When media carries an orientation setting, this lets you spin that media so it sits the right way up. Four choices are on hand for adjustment: 0º, 90º right, 180º, and 90º left.
- Input Sizing Preset: Through this panel you can hand a Sizing palette preset to chosen clips. Suppose you hold a dedicated Input Format Preset for standard-definition PAL widescreen clips that were edited into a high-definition project; you could sort the Media Pool to gather them, then select them all and apply the preset.
- Field Dominance: Out of the box, the Auto setting leaves DaVinci Resolve to work out on its own whether a given clip is Upper- or Lower-field dominant. Where that automatic call comes out wrong, you can pick Upper or Lower to override it yourself.
- Enable Deinterlacing: (present only in the Studio version) This checkbox stays available solely while “Enable video field processing” is switched off in the Master Settings panel of the Project Settings. Ticking the Enable Deinterlacing checkbox tells DaVinci Resolve to deinterlace clips by way of the Deinterlace quality setting kept in the Image Scaling panel of the Project Settings. For most clips Normal is a strong, high-quality approach, whereas High costs more processing but can, with some footage, return cleaner results. The DaVinci Neural Engine choice leans on advanced machine learning to rebuild the frame, ideally bettering even what High produces.
- Alpha Mode: Which options show up here turns on the format of the clip you picked, since only some formats — ProRes 4444, QuickTime Animation, OpenEXR, TIFF sequences, and the like — can carry alpha channels. For clips you imported with embedded alpha channels, this panel lets you switch their use in DaVinci Resolve on or off (by selecting None), settle on the alpha channel type (Premultiplied or Straight), or flip the alpha channel. Pick a clip that holds no alpha channel and most of these options simply will not appear.

The Alpha Mode choices on offer once a clip carries an embedded alpha channel

- Super Scale High Quality Upscaling: Whenever you want sharper upscaling than the ordinary Resize Filters deliver, you can switch on one of three “Super Scale” options within the Video panel of the Clip Attributes window for one or more chosen clips. In contrast to the many scaling options scattered across the Edit, Fusion, or Color pages, Super Scale genuinely raises the source resolution of whatever clip it processes, so that clip ends up holding more pixels than before — and grows heavier to work with unless you optimize it (which bakes the Super Scale result into the optimized media) or cache it somehow.

Within the Super Scale drop-down you will find 2-3-4x and 2-3-4x Enhanced, alongside Sharpness and Noise Reduction controls for refining how the scaled output looks. While most Super Scale parameters step in fixed increments, the Enhanced modes let you dial Super Scale in by variable amounts. Choosing any of these turns DaVinci Resolve loose with advanced algorithms that lift the look of image detail when you blow a clip up substantially — say, when cutting SD archival media into a UHD timeline, or when a clip must be pushed beyond its native resolution to fashion a closeup. Depending on the source media at hand, you may notice that a Sharpness of Medium produces a fairly faint change that is easy to overlook, whereas a Sharpness of high reads as plainly better, even as it over-sharpens grain and noise at the default settings. Raising Noise Reduction tempers that side effect, true, but it also chips away at whatever you gained from raising Sharpness. So it pays to experiment with leaving Sharpness at Low or Medium, letting Super Scale firm up every facet of a clip, and then leaning on the Color page’s Noise Reduction tools — which can be tuned more finely — to knock back the stray noise.

Super Scale options shown in the Video panel of the Clip Attributes window TIP: As valuable as Super Scale is, it leans hard on your processor, so expect that switching it on will most likely rule out real-time playback. A workaround is to build a string-out of every piece of source media you need enlarged at high quality, enable Super Scale across all of them, and then render that timeline out to individual clips with the “Render at source resolution” and “Filename uses > Source Name” options switched on.

### Real-Time 3:2 Pulldown Removal

When you are handed 29.97fps interlaced footage that was encoded carrying a 3:2 pulldown, DaVinci Resolve can rebuild the original material’s progressive frame rate on the fly. Take source media off a film camera (24fps progressive) that has since been telecined to NTSC video (29.97fps interlaced): DaVinci Resolve is able to lift the 24 distinct film frames back out of the assorted interlaced fields that compose the NTSC signal. To strip 3:2 pulldown in real time: 1 In the Media Pool, pick one or more 29.97 fps interlaced clips. 2 Right-click any of the chosen clips and pick Clip Attributes. 3 Under the Video tab, switch on the Remove 3:2 Pulldown checkbox. 4 In the “First Frame of Clip” drop-down, set the Frame at which the 3:2 cadence began (typically the “A” frame). 5 Click OK. From here on the footage acts as a 24fps progressive clip.

Telecined footage after its 3:2 pulldown has been removed; the jumbled number (a blend of the digits 1 and 2) trailing the KeyKode acts as a field indicator, confirming that this A frame was built correctly out of fields 1 and 2 of the interlaced signal.

### Audio Attributes

Through the Audio panel you can revise the channel format together with the channel assignments across one or more clips. What you set here governs what turns up in the Timeline’s audio tracks once a clip is edited into a program. At the moment you first bring clips into the Media Pool, the Audio Attributes panel lets you spell out which embedded audio channels become tracks — and how they look — for editing on the Edit and Fairlight page timelines.

### The Audio panel of the Clip Attributes window

### Add Track Controls

Sitting atop the Track/Channel list, a cluster of controls lets you append extra tracks onto a clip. Tacking on those extra tracks gives you a way to remap the clip’s available channels so they surface in the Timeline as you edit.

- Format: A drop-down through which you pick a format for whatever new tracks you add. Your pick here drives how many channels show up in the Channel Assignments list beneath it, and likewise what sort of Timeline audio track it takes to surface every channel of the clip. Should you pick

a Channel Format carrying fewer channels than the clip actually holds, every surplus channel gets switched off. The choices on hand are: Mono: Suited to single-channel clips Stereo: Suited to clips bearing two-channel left/right audio 5.1: Suited to 5.1 surround mixes 7.1: Suited to 7.1 surround mixes Adaptive: Suited to multiple-mono production audio — multi-channel recordings, for instance, where a boom microphone, a pair of separate lavaliere microphones, and a mixdown track are all captured at once.

- Tracks: Sets how many tracks you wish to tack onto the current clip or clips. Every track you tack on means one more linked audio item gets dropped into one more audio track once the clip is edited into the Timeline. Say you hold a multi-channel production recording made with four separate microphones; you could tack on 3 mono audio tracks and then route each channel to its own track, surfacing every channel as a standalone audio clip in the Timeline so each microphone can be edited on its own.
- Add button: Tacks the tracks you have specified onto the current clip or clips.

On the left, a clip holding one track of two-channel stereo audio, set beside a clip on the right holding two tracks of single-channel mono audio Audio Track and Channel List Beneath the Add Track controls, the list carries one entry per track defined inside whichever clip or clips you have selected. Pop-ups inside that list let you respecify and route how the clip’s channels get distributed across the variously mapped tracks you built.

- Format: Whichever format a given audio track takes — the options being Mono, Stereo, 5.1, 7.1, or Adaptive.
- Source Channel: Per track, you see as many channels as the chosen format demands.

Where a Stereo track carries two source channels, a 7.1 track carries eight. Each channel is shown nested below whichever track it belongs to. To drop a particular channel out of the clip, pick <none> from the list.

- Track: The name of each track in a clip.
- Channel in Track: The name of each channel in that track.
- Delete Track button: Float the pointer over a track and a trashcan icon surfaces; click it to remove that track.

The trashcan button for deleting an audio track from inside Clip Attributes, which shows up only while the mouse hovers over a track

Support for Mixed Audio Track Formats from Source Clips DaVinci Resolve will also handle media whose several audio tracks hold channels embedded in differing formats. A clip bearing one stereo track, one 5.1 surround track, and six mono tracks, for example, can each be configured correctly in the Audio panel of Clip Attributes once that clip has been imported. The Audio panel of Clip Attributes now gives you a say over which format (Mono, Stereo, 5.1, 7.1, Adaptive) the channels embedded in a given clip ought to take. As a result, you can build clips with several tracks, each potentially drawing on a different audio format and a different mix of clips — a real convenience for mastering.

Clip Attributes now allows channels to be parceled out across separate tracks each holding its own channel assignments

### Timecode Attributes

Should you be wrestling with clips whose timecode is wrong, or whose timecode bears a faulty relationship to the EDL, XML, or AAF project you were handed, these attributes let you revise the timecode and reel name of clips in the Media Pool. Not one of these tools touches the source media sitting on disk; they merely rewrite the timecode metadata inside your DaVinci Resolve project, which in turn shapes the timecode of whatever media you render.

- Current Frame Timecode: Hands a fresh time to the timecode sitting at whatever frame of the clip you are presently viewing.
- Slate Timecode: When your source media stems from a shoot on which a timecode slate was used, you can register that slate timecode as a secondary timecode track usable for assorted operations — all without disturbing the clip’s primary timecode, which may already be carrying program sync.

To dial in the right Slate timecode, choose a Media Pool clip that shows a timecode slate, and park the playhead on a frame where the slate’s timecode reads clearly. Next, open the Timecode panel of the Clip Attributes window and key the timecode value you can read in the picture into the Slate Timecode field.

- Offset Source Timecode: When a whole batch of clips carries timecode that is simply shifted, you can fix that offset across however many selected clips you wish.

### The Timecode panel of the Clip Attributes window

### Reel Name Attributes

Within the General Options panel of the Project Settings, the “Assist using Reel Names” checkbox ranks among the most consequential settings for steering how conform behaves. It sits off out of the box, leaving Reel Names empty. That is perfectly fine for conform workflows where the file path or file name plus source timecode is all you need to pin each media file to its clip. Yet should reconforming your project’s clips demand more than that, ticking the “Assist using Reel Names” checkbox lets DaVinci Resolve lean on one of four methods to set reel names automatically for every Media Pool clip. The Clip Attributes dialog also opens the door to defining by hand how the Reel Names of one or more chosen Media Pool clips get assigned. That helps whenever certain clips in a project call for a different reel name extraction method, or for reel names entered by hand. After you have leaned on Clip Attributes to rewrite a clip’s reel names, those clips stop refreshing on their own when you adjust the “Assist using Reel Names” options in the Project Settings.

Before the reel name attributes in the Clip Attributes window can be edited, you have to switch on “Assist using Reel Names” under the General Options of the Project Settings and settle on a Reel Assist setting.

- Source clip file pathname: Derives the reel name by pulling it out of each media file’s path. This lets you draw a reel name from the whole file name or part of it, or from the whole — or part — of any folder name along the path enclosing that file. You spell out the extraction through the Pattern field.
- Pattern: A code laying out how a reel name ought to be pulled from the source clip pathname. Further notes on building patters come later in this chapter.

The Reel Name panel of the Clip Attributes Window

- Media Pool bin name: Here the reel name comes from whatever bin in the Media Pool holds that clip. In a stereoscopic workflow, for one, you might export offline stereo media using the “Left” and “Right” bin names — the bins they sit in — as reel names. Another case would be VFX undergoing incremental processing, filed into individually named bins like “VFX_Tuesday_10-12.”
- Embedding in Source clip file: Handy with file formats that tuck the reel name inside the media file itself. CinemaDNG and other digital cinema cameras, QuickTime files born of Final Cut Pro, and DPX frame files all number among the formats that can hold reel name header data.
- Source clip filename: Where no reel number has been defined, it is frequently simplest to fall back on the Source clip filename.
- User Defined: This choice surfaces only when you hand-edit the reel name for one or more chosen Media Pool clips by way of the Clip Attributes dialog. Picking User Defined lets you type whatever text string you please as the reel name.

### Update Timecode from Audio – LTC

Certain cameras provide no way to lock onto an outside timecode source. The timecode they record might be time of day or free run, yet it will not be frame-accurately matched to other cameras, to the dual system audio recorder, or to the digital slate. That turns multi-cam or dual sound system syncing into a slow, hands-on chore. DaVinci Resolve answers this so long as the footage the camera shot carries a timecode reference on its audio track from the shoot — achieved by feeding an externally generated timecode into the camera’s audio input. Pick that clip, or clips, in the media pool, then right-click one of the highlighted clips and choose “Update timecode from audio - LTC.” On its own and at once, DaVinci Resolve rewrites the clip timecode from the LTC it detects on the audio tracks. The clips are now yours to use as though they had been synced right on set.

### Changing Clip Thumbnails in the Media Pool

With the Media Pool set to Thumbnail mode, a small image stands in for each clip, defaulting to that clip’s first frame. Hover the pointer over any clip for a moment and you can scrub its thumbnail to preview the contents. Once you stop scrubbing, though, sliding the pointer off the clip snaps the thumbnail back to the first frame of media, which may or may not capture what the clip actually holds. If you prefer, this can be changed. To set a custom thumbnail for any clip: 1 Bring the pointer over the clip whose thumbnail you mean to customize. 2 Hover briefly, then scrub along to a frame that represents it well. 3 Right-click the clip and pick Set Poster Frame, or hit Command-P. To wipe out a clip’s custom poster frame:

- Give the clip a right-click and pick Clear Poster Frame, or else tap Option-P.

### Creating Subclips

Subclips hand you yet another route to organizing media within the Media Pool, since they let you split overlong clips into shorter pieces. Say a project’s director favors “rolling takes,” with several takes all captured inside one clip; you can pull those takes apart by turning each into a subclip. To make a subclip: 1 Pick any Media Pool clip to load it into the Viewer. 2 Lay down In and Out points marking the stretch you want carved into a subclip. 3 Then do one of these:

- Give the jog bar a right-click and pick Make Subclip.
- Pull a clip out of the Viewer, or the Source Viewer, and drop it onto the Media Pool.

4 Up comes a new subclip dialog, where you can title the subclip and, by ticking the checkbox, opt to use its full extents.

### The New SubClip dialog

Built, a subclip shows up and behaves just like any other clip throughout DaVinci Resolve. Subclips can likewise be created over on the Media page as you carry out other organizational work there.

### Removing or Changing Subclip Limits

Once it exists, a right-click on any subclip — whether in the Media Pool or on a timeline — and a choice of Edit Subclip opens a dialog where you can tick a checkbox to draw on the subclip’s full extents, or revise its start or end timecode through the timecode fields, then click Update to apply the change.

### The Edit Subclip dialog

### Organizing Stereo 3D Media

Among the earliest jobs when handling stereo media in DaVinci Resolve is syncing each stereo pair of clips so the two behave as one. That goes smoothly provided you are deliberate about how your media is laid out in the Media Pool. Every set of right- and left-eye media ought always to be filed into separate left-eye bins and righteye bins, which eases the later syncing of these clips through the Stereo 3D Sync command in the Media Pool contextual menu. For fuller guidance on readying media destined for stereo pipelines, “refer to Chapter 15, “Stereoscopic Workflows.” Within the section titled “Stereoscopic Workflows”

### Camera Raw Decoding

Camera raw media formats earn the name because they grab raw color space data straight off the sensor of whichever digital cinema camera shot the footage. Such raw image data is not legible to people; it has to be debayered or demosaiced to turn the original raw data into image data ready to pass along to DaVinci Resolve’s image processing pipeline. You have four levers for governing how camera raw media gets debayered into a usable, “normalized” image for adjustment or output:
