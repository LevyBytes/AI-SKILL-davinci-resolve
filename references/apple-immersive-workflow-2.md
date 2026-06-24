# Apple Immersive Workflow (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

The Undistort tab 3 Lean on the X, Y, and Z rotation parameters to pick out a portion of the immersive image you want flattened. 4 Carry on compositing just as you would with an ordinary 2D video signal. That covers (though isn’t limited to) standard paint techniques for erasing stray objects, sampling frame regions with transforms and polygons to extend a set, or laying in mattes, text, and outside image/video layers to swap out signs or screens. With that done, the flat image has to be re-distorted so it lines up with the original immersive warp. 5 Copy the Immersive Patcher so the original rotation and angle-of-view information is kept. 6 Paste the Immersive Patcher beyond the composite nodes and wire it to the tail of the composition pipeline.

The second Immersive Patcher, pasted out of that first copy.

7 Within the Inspector, click Distort. 8 Merge the composited patch onto the original clip so the effect folds into the immersive scene.

### The final node graph

In a collaborative setup, you can leave the Fusion page and go on editing, mixing, and grading the immersive timeline within DaVinci Resolve. For immersive turnovers, render each eye out separately as EXRs in ACES AP0 so the fullest set of properties survives for immersive delivery.

### Color Grading

Here we walk through the optical, color, and 3D tools at your disposal while handling immersive media on DaVinci Resolve’s color page. Given how distinctive immersive content is, certain tools simply can’t be used during postproduction. Still others are off the table for now but are being reworked to handle immersive content.

### Noise Reduction

You can still reduce noise while working with immersive video. Inside the Motion Effects palette, Spatial NR studies the noise pattern in the source media so it can cut that noise as far as possible while holding on to the original image detail. 1 From the color page toolbar, open the Motion Effects palette. Within the Spatial NR column you get to pick which noise reduction mode to apply.

- The Faster, Better, and Enhanced modes each carry out their pattern analysis inside a chosen radius size

and shape their output according to the threshold you set. They appear here in ascending order of processing complexity.

- AI UltraNR is an AI-powered noise pattern detector that pulls the noise pattern out of the signal by finding and studying the “flattest’’ region of the frame for pure noise. 2 Switch the spatial noise reduction mode to AI UltraNR.

Spatial Noise Reduction settings

3 Click Analyze. The viewer shows a bounding box marking the “emptiest” patch of pixel data in that frame. Because it holds no real visual content, whatever sits inside the square is perfect for pulling out the digital noise the camera sensor generates.

The bounding box for AIUltraNR. The bounding box can be moved and resized in the viewer should you want, yet it usually isn’t a good idea—AI UltraNR spots the best analysis regions more reliably than our eyes do. You’re also free to tweak the Noise Profile Luma and Chroma Threshold settings by hand, but once more, AI UltraNR generally lands on the right blend of thresholds for clean noise reduction on its own.

### Primary Grading

Primary color grading behaves exactly as it would on ordinary video footage. Apply the same thinking around normalization, balancing, and matching as you work the primaries color and log wheels, the HDR palette, and the HSL Curves. Likewise, the Color Slice and Color Warper palettes behave as you’d expect.

### Secondaries

Selection approaches that work at the pixel level, such as the Qualifier, behave as expected on immersive media. Object- or window-based selection can stay accurate only inside a flat equirectangular (or viewport) environment, so most secondary techniques demanding a precise qualification shape are off the table for the moment. That covers Power Windows (and, by extension, the Tracker palette) along with the Magic Mask tool.

### Sizing

Immersive content offers no sizing controls at all (that is, zooming and panning).

### 3D Palette

On the color page, the 3D palette carries controls for handling an assortment of 3D camera and graphics formats. In contrast to other stereoscopic formats, there’s no need to tune the alignment of the eyes here, since the Blackmagic URSA Cine Immersive camera lenses, focal length, and irises are all fixed.

### 3D palette

Reserved solely for immersive content, the Edge Blend mode lets you reshape and soften the outer rim of the immersive video frame. You can put it to work hiding film gear that would otherwise show and reining in how far the observer can see. Past that edge, the observer takes in the backdrop.

- Open the 3D palette.
- Over in the upper right corner, switch the mode to Edge Blend.

### Edge Blend Mode

- Confirm the viewer’s onscreen controls are switched to Edge Blend.

### Edge Blend Viewer Controls

A ring of control points should appear around the edge of the video frame, with an anchor handle sitting at its center.

- Drag a control point to move it.

### Dragging a control point

### Or right-click to delete a point

- Over in the 3D palette’s right column, the Feather parameter softens the frame’s edge.
- Tick ‘visionOS Effect’ so the fresh edge data gets handled properly during playback

on the Apple Vision Pro. Leave it off and the edge ends up baked into the rendered video file.

- In the left column, the Left and Right tabs flip between eyes in the viewer.

Bear in mind that a good many of the 3D palette’s controls sit greyed out. Across DaVinci Resolve, parameters turn grey whenever they don’t apply to whatever media you’re actively handling — here, the immersive content.

- In the center column, the Stereo and Mono tabs toggle between single- and double-lens views of the immersive video clip.

### CST Color Management

Applying the Color Space Transform (CST) effect to nodes within the color page’s node editor gives you precise color mapping plus tailored command over the timeline’s peak output nit luminance. The suggested workflow leans on four CST nodes:

### CST nodes

### CST Timeline Mapping

To begin, you map from the camera source input color space into the ‘working’ timeline color space. The Blackmagic URSA Cine Immersive camera runs in the Blackmagic Design Wide Gamut Gen 4/5 color gamut, paired with the DaVinci Intermediate log curve. 1 Bring up the Effects panel. 2 Onto an empty node (01), drag Color Space Transform within the node editor. While mapping the input color space into the timeline color space, this node belongs near the front of the node tree, ahead of any grading operations. Where you instead map straight from the input color space to the monitoring or delivery color space, set this node near the back of the node tree, past the grading work. 3 Give node 01 the label INPUT CST. NOTE: The node labels in these steps exist purely to keep the documentation and screenshots easy to follow. Feel free to adopt whatever naming scheme suits you, or skip labelling entirely. 4 For the Input Color Space, choose Blackmagic Design Wide Gamut Gen 4/5. 5 Make the Input Gamma DaVinci Intermediate. 6 Put the Output Color Space at DaVinci Wide Gamut. 7 Leave the Output Gamma on DaVinci Intermediate.

CST settings for node 1 8 Create a fresh serial node (02). 9 Copy the first node (01) and paste it onto that new node (02). 10 Label node 02 as OUTPUT CST. In this new serial node you’ll want the earlier output color space and gamma to serve as the input, keeping the node tree’s timeline color space consistent. 11 Hit the Swap button to trade the input and output parameters. The Input Color Space and Gamma now suit this CST node. 12 Set the Output Color Space to P3-D65. That’s the present default gamut for Mac displays. 13 Set the Output Gamma to Rec.2100 ST2084, the HDR standard governing a 1000-nit signal.

Every grading operation takes place between those two nodes. Yet because you’re using node‑based color management, you also gain the rare option to act outside the bounds of the timeline color management — something many colorists exploit to bring in particular grading operations, effects, or third-party elements.

### CST settings for Node 2

### ICC Profiles

As an added safeguard that the Blackmagic URSA Cine Immersive signal maps properly to your Mac display, head into System Settings > Displays and confirm the color profile Preset reads Apple XDR Display (P3-1600 nits).

### CST Grading Monitor Mapping

Extra CSTs let you temporarily cap the peak nit output values for monitoring while you grade. 1 Create a fresh serial node (03) following the color management OUTPUT CST (02). 2 Label node 03 as MONITOR.

CST node graph 3 Add the Color Space Transform effect onto the MONITOR node (03). Its input values must line up with the signal coming out of the prior CST. 4 For the Input Color Space, choose P3-D65. 5 Make the Input Gamma Rec.2100 ST2084. Since this CST node exists only to remap the image’s luminance down to a smaller nit value, the input and output parameters can stay identical. 6 Put the Output Color Space at P3-D65. 7 Leave the Output Gamma on Rec.2100 ST2084.

NOTE: There are times when a CST’s color space or gamma needn’t be set at all if input and output match (nothing maps). Here it’s required, because how the custom nit mapping behaves depends on the value and shape of the signal’s log curve. 8 Tick ‘Use Custom Max. Output’. 9 Set the Max. Output (nits) to 250.

### CST tone mapping

That 1000 nit signal now gets remapped down to 250 nits by way of the DaVinci Tone Mapping Method. The upshot is an image that comes very close to the rendered Apple Vision Pro signal as seen on an HDR grading monitor (the Flanders XMP310, Sony BVM-HX310, and the like). To actually monitor your project on an Apple Vision Pro, though, one further tone mapping step is required.

### CST Apple Vision Pro Monitoring

One last CST node opens the door to live monitoring, preview, and final delivery onto Apple Vision Pro devices. 1 Create a fresh serial node (04) following the MONITOR node (03). 2 Copy MONITOR node (03) and paste it onto node 04. You’ll keep the same input and output parameters and alter nothing but the nit count. 3 Label node 04 as AVP.

Apple Vision Pro Monitoring node graph 4 Tick ‘Use Custom Max. Input’. 5 Set the Max. Input (nits) to 250 so the mapped signal arriving from the MONITOR node is read correctly. 6 Set the Max. Output (nits) to 108, the ceiling nit value for monitoring and delivery onto the Apple Vision Pro.

### Apple Vision Pro CST settings

With that in place you can carry on grading, switching off the CST nodes if and when your workflow calls for it. During the first grading pass on your external grading monitor, for instance, turn off the AVP node (04) so you’re seeing the 250-nit signal accurately on that HDR grading monitor. Once you move to previewing in the Apple Vision Pro or to final delivery, switch the AVP node (04) back on. Can the CSTs live in the timeline node editor? No. For now, clip tonal mapping depends on applying the Color Space Transform Adaptation parameter precisely, and that has to happen one clip at a time.

### Audio

Both the Apple Vision Pro and DaVinci Resolve back the spatial and ambisonic varieties, plus AVP (Apple Vision Pro) audio and the AIA (Apple Immersive Audio) formats. Plenty of audio post-production carries on the same way once you’re working in spatial audio. A key departure is that, instead of monitoring on high-end speakers, sound engineers ought to reach for headphones or Airpods to get genuine spatial immersion and a truer take on the audience’s listening environment. Where 2D mixes park most of the dialogue in the center channels, spatial audio has to be placed wherever the sound actually comes from. Ducking, equalization, and balancing have to shape the audio stems so the listener is never overwhelmed or confused. Immersive spatial elements can sit alongside an ordinary stereo stem, letting certain sounds hold steady regardless of how the head turns. That’s useful for keeping non-diegetic material — the music score, voiceovers — clear and easy to follow. Environmental sounds tend to read quieter in spatial audio, so they frequently need a heavier hand in the mix to register, though never to the point of disorienting the listener. Reverb adds a great deal to immersion, being something listeners encounter naturally each day — every sound made inside a given space rebounds off the surfaces around the listener, yielding a ‘blooming’ reverb character. For that reason, reverb is welcomed in spatial audio design to guarantee full immersion. The Apple Immersive Audio (AIA) format acts as a container holding several formats:

- Apple Spatial Audio Format (ASAF): ASAF serves as the raw working audio format.
- Apple Positional Audio Codec (APAC): APAC is the encoded .mp4 format that plays on

APAC-supported devices such as Airpods, or out of an AIVU file on the Apple Vision Pro.

### Apple Spatial Audio Format (ASAF)

The Apple Spatial Audio Format (ASAF) is an immersive audio format built chiefly for VR and AR work on the Apple Vision Pro. macOS-only, ASAF is handled through ProTools (by way of plugins) and DaVinci Resolve (natively). Among ASAF’s advanced technical strengths are built-in support for Ambisonics sources (termed Scenes) and routing through bus assigns. Mixing happens virtually, free of any physical bus, and users can pick from a range of monitoring formats, binaural with headtracking through direct Apple AirPod integration among them. Panning runs through DaVinci Resolve’s established tools — the pan dialog, automation, SpaceView, and in-viewer pan tools — backed by secondary controls in the Inspector. Together they enable exact spatial placement of sources, including automatic tracking against lat-long video. You can export ASAF mixes as WAV or MP4 (with their metadata alongside) through the Immersive Audio > Export Master File option, though for now they can’t be imported or played back inside DaVinci Resolve.

### ASAF File Support

Beyond Ambisonic Scene formats spanning 1OA to 7OA, ASAF Object sources may take on any channel width, from mono through stereo and on to multi-channel immersive audio. That latitude makes it simple to build and draw on beds in any format when assembling intricate immersive experiences.

### Enabling ASAF

Turn ASAF on by heading to Preferences > Video and Audio I/O and ticking the Apple Spatial Audio Format checkbox within the Immersive Audio section.

### Setting Up an ASAF Mix

Because Apple Spatial Audio Format is so deeply woven into DaVinci Resolve, building an Apple Immersive mix comes down to little more than adding an ASAF Master bus to your project and pointing your audio tracks and buses at it.

### Creating an ASAF Master Bus

To build your ASAF Master bus: 1 Head to Fairlight > Bus Format. 2 Once the Bus Format dialog appears, either convert the existing Stereo bus into an ASAF master or click the Add Bus button down in the lower left. 3 Should you opt to make a new bus, rename it however you like (say, ASAF), then choose Apple Spatial Audio Format > ASAF Master from the matching dropdown in the Format column and click OK.

### Creating an ASAF Master Bus

A fresh ASAF Master Bus channel strip, marked with an Apple logo across its top, joins the mixer, and a matching track header turns up on the timeline.

ASAF Master Bus Channel Strip (left), ASAF Master Bus Track Header (right)

### Sending Audio to the ASAF Master

As you route audio into the ASAF Master, keep these points in mind: An Ambisonic bus (ASAF Scene or native Ambisonic) sent to the ASAF Master turns into a Scene inside the Master.

- The ASAF master accepts just one Ambisonic bus — meaning either an ASAF Scene bus or a native Ambisonic bus, not both.
- That new scene inside the ASAF Master can take in any number of additional Scenes routed its way.
- As many as 128 mono objects can feed into Scene busses.

Any non-Ambisonic bus pointed straight at the ASAF Master becomes a static Channel Bed matching the source format — stereo, 5.1, or 7.1.4, for instance.

- No more than 8 non-Ambisonic busses may route directly into the ASAF Master.
- Within the Track Index, a Bus can become a Dynamic Object by switching its Type from

Channels to Object. Audio tracks of any format can be routed straight to the ASAF Master as Dynamic Objects.

- As many as 128 mono objects can route directly into the ASAF Master.
- Each stereo object is made up of two mono objects.

### Panning

On every track, the 2D, 3D, Spherical, or Cartesian View Panners let you place your sources along both the horizontal and vertical planes. Any channel-based format will do — mono, stereo, or 7.1.2, say — and you can set them within the spherical sound field. To dig deeper into the 2D and 3D Panners, turn to Chapter 177, "Mixing in the Fairlight Page."

### Audio Inspector Controls

When finer adjustments are called for, pick a track or Bus and open the Inspector’s Audio tab to surface a set of extra controls. For more on the Audio Tab, see Chapter 176, “The Fairlight Inspector.”

### ASAF Master Controls

### Content Type

This section’s drop-down menus let you set the parameters below:

ASAF Master – Content Type section of the Audio Inspector

- Content Kind: Through this dropdown you choose a label for the content the ASAF Master delivers. Your options are Movie or Music.
- Monitor Mix Path: Here you set the playback monitoring path the audio signal takes while you mix the project. The options run: Virtual Reality Virtual Reality + Speakers Headphones Headphones + Speakers Speakers
- Reverb Preset: Lets you drop one of the on-hand reverb settings onto the ASAF Object signals. The categories on offer break down as follows. Under Room Reverbs you’ll find Small, then Medium, Large, and Large 2, followed by Office 50m3 and Office Hallway, then the treated set — Treated Room 133m3, Treated 500m3, and Large Treated Room 800m3 — plus Studio 200m3, Untreated Room 210m3, and the pair Small Tiled Room and Medium Tiled Room

Among Hall Reverbs sit Medium, then Medium 2 and Medium 3, alongside Large and Large 2. There is also a Plate Reverb. The Chamber Reverbs come as Medium or Large, and a Cathedral is offered too. For the open-air choices, Outdoor Environments give you Outdoor and Outdoor Park. TIP: A click on the icon at the upper-right corner brings up the Space View plugin, where you can watch the live positions and scripted movements of audible sound sources. For more, turn to this chapter’s Space View section Active Resources

### ASAF Master – Active Resources

Active resources give you a tally of the audio resources within your ASAF mix, laid out below:

- Objects: How many dynamic objects the current timeline uses. The cap on dynamic objects is 128, across any audio format or mix of formats. Route a 7.1 track to the ASAF Master, though, and it consumes 8 of those 128.
- Headlocked: How many Headlocked objects sit on the current timeline, capped at 15.
- Scene Objects: How many dynamic scene objects on the current timeline are routed into

an ASAF Scene. Scene Objects may be in any audio format, but a project tops out at 128 of them.

- Scenes: Flags when an ASAF Scene (bus) is routed to the ASAF Master. There’s a ceiling of one ASAF Scene per project, yet any number of Scene Objects can route into that ASAF Scene.
- Channels: How many static channel Beds (buses) feed the ASAF Master. A project allows at most 8 Beds. Beds can be in mono, 2.0, LCR, Quad, 5.0, 5.1, 5.1.2, 5.1.4, 7.0, 7.1, 7.1.2, 7.1.4, 7.1.6, or 9.1.6 format.

### Head

This section’s parameters govern how the listener’s head is oriented. ASAF Master – Head section of the Audio Inspector

- Head Yaw: The listener’s head turning left to right, spanning -180 ° to +180°.
- Head Pitch: Governs the listener’s head moving up and down, as though glancing up and

down, spanning -90 ° to +90°.

- Head Roll: The listener’s head tipping side to side, “one shoulder toward the other,” spanning

-180 ° to +180°.

- HRTF: With compatible AirPods in use, this parameter flips between the Personalized

and the System default HRTF profiles. NOTE: The Yaw, Pitch, and Roll parameters refresh on their own to track your head position whenever compatible AirPods or a head-tracker are in use.

### Room Simulation

By way of the parameters below, the Room Simulation section lets you choose among various simulated materials and “build” a virtual room — its walls, its floor, its ceiling — which you then apply to your ASAF Scene Objects, with room size and reflective quality both adjustable. ASAF Master– Room Simulation section of the Audio Inspector

- Size (X): Sets the room’s width, spanning 2 to 20 meters.
- Size (Y): Fixes the room’s length, spanning 2 to 20 meters.
- Size (Z): Sets the ceiling height, spanning 2 to 20 meters.
- Floor Material, Wall Material, and Ceiling Material: Every one of these parameters hands you the same set of materials for its respective surface:

ASAF Master – Room Simulation Floor Materials section of the Audio Inspector

- Absorption: Fixes how reflective the room is.
- Room RT60: Reports how long the sound takes to fall off by 60dB (decay time) once

the audio signal falls silent.

### World

The Grid parameter sets where the Room Simulation sits vertically relative to the listener, all without altering the height of the audio object itself. In effect this raises or lowers the entire room while the listener and the audio object or objects stay put. It comes in handy when, say, you need to mimic a space with a tall ceiling while the listener sits nearer the floor.

ASAF Master – World section of the Audio Inspector Defaults These controls let you set the default panning setup handed to every new audio track.

ASAF Master – Defaults section of the Audio Inspector

- Coordinate System: Pick either the 3D Spherical or the Cartesian panner for all new tracks.
- Range: This control fixes the default value of the Panner’s Range parameter, spanning 1 to 10 meters. A Range of 1m holds panning in the room at unity. Bigger values push objects farther off, dropping their loudness just as distance would in real life.
- Set Global Defaults: A click on this button pushes the Coordinate System and Range out to every newly made Timeline.

### ASAF Object Controls

### 3D Panner

This take on the 3D Panner brings a broader set of parameters for placing an Audio Object, spelled out below.

### 3D Panner for an ASAF Object

TIP: A click on the icon at the upper-right corner brings up the 3D Panner plugin.

For more on the 3D Panner plugin, see Chapter 177, "Mixing in the Fairlight Page."

- Azimuth: Fixes the object’s horizontal angle (left to right) around the listener, spanning -180 ° to +180°. You’ll see this control only where that channel uses a 2D or 3D Spherical Panner plugin in the Fairlight mixer.
- Elevation: Fixes the object’s vertical angle above and below the listener (-90° to +90°). It surfaces solely once the channel’s Fairlight mixer Panner plugin runs in 3D Spherical.
- Radius: The gap between the object and the listener, anywhere from 0 to 10 meters in any direction. This one appears only if the channel’s mixer Panner plugin in Fairlight sits on 2D or 3D Spherical.

The ASAF renderer draws on this value, together with the Offset, to fake shifts in distance by lowering or lifting the audio signal level. An object placed 1 meter off, say, plays at unity gain, while at 10 meters it reads roughly 20dB quieter.
