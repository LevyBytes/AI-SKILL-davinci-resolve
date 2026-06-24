# Apple Immersive Workflow (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

With the 3D Panner's Cartesian view active on an ASAF Object, X, Y, and Z parameters stand in for Azimuth, Elevation, and Radius, as laid out here: X: Drives the panner's Left/Right parameter, ranging from -10m to +10m. Y: Drives the panner's Front/Back parameter, ranging from -10m to +10m. Z: Drives the panner's Down/UP parameter, ranging from -10m to +10m. With the Panner switched to Spherical, this control stays hidden.

The Cartesian View gets a fuller account in Chapter 177, "Mixing in the Fairlight Page."

- Width: Fixes the object width, ranging from 0° to 180°.
- Height: Fixes the object height, ranging from 0° to 180°.
- Directivity: Fixes an object's directivity pattern (radiation pattern), which spells out how the audio shifts according to the object's orientation toward the listener. Say someone speaks with their back to the listener — their voice comes across as though a low-pass filter had been laid over it.
- Yaw: Fixes an object's horizontal orientation, ranging from -180 ° to +180°. With the Directivity parameter bypassed, this setting has no bearing on an object.
- Pitch: Fixes an object's vertical orientation, ranging from -90 ° to +90°. With the Directivity parameter bypassed, this setting has no bearing on an object.
- Roll: Tilts or rolls the scene from side to side.
- Follow Listener: While active, the object turns to face the listener no matter where it sits.
- Headlock: While active, an object's position holds steady even as the listener's head shifts. With Headlock off, the object's perceived location moves as the listener turns or repositions their head.

NOTE: Headlock only affects binaural rendering.

- Externalize Binaural: This parameter surfaces only while Headlock is active. With it active, HRTF kicks in as the Binaural output renders, so the audio seems to sit beyond the listener's head. Switch Externalize Binaural off and HRTF drops out of the rendering, leaving the object panned between the listener's ears.

### Offsets

The Radius Offset parameter tacks on as much as 200 meters to the distance the 3D Panner's Radius parameter sets. This control appears only where the Fairlight mixer has the track's Panner plugin set to 3D Spherical.

### ASAF Objects – Offsets

When the 3D Panner is showing the Cartesian View, the X, Y, and Z Offsets laid out below appear in this section: X Offset: Fixes the offset on the panner's Left/Right parameter, ranging from -200 m to +200m. Y Offset: Fixes the offset on the panner's Front/Back parameter, ranging from -200 m to +200m. Z Offset: Fixes the offset on the panner's Down/Up parameter, ranging from -200m to +200m.

### Reverb

You switch this reverb effect on by ticking the Reverb checkbox sitting above the Mix control, which governs how much reverb reaches the ASAF Object.

### ASAF Objects – Reverb

NOTE: This Reverb section only affects ASAF Objects.

### Metadata

Rather than handling it in the Track Index, you can use this part of the Audio Inspector to attach the right metadata information to the object through the settings below:

### ASAF Objects – Metadata

- Content Type: Through this drop-down menu, the object gets classed as either Music and Effects or Interactive.
- M & E Tag: Where the content carries a Music and Effects tag, this dropdown's options let you pin the object down further—say, Music, Effects, Dialogue, Narration, etc.
- Interactivity: Where the content was tagged Interactive, picking an entry from this list narrows the object down further, to something like Commentary or Audio Description.
- Salience: Hands the object audio a level of importance, helping the ASAF export encoder rank it against the project's other ASAF objects.
- Language: Through this dropdown you set the content's language.
- Post Reverb: While active, the object is configured so the playback application — Vision Pro, for one — can read the room characteristics of the users' listening environment and, should they choose, layer in a fitting reverb setting. Post Reverb stacks on top of whatever reverb settings the ASAF Object Reverb noted above applies. It leaves the output from the ASAF Renderer plugins untouched, though.

### ASAF Scene Controls

### Gain

Switched on by ticking the Gain Enable checkbox, this plugin raises or drops the ASAF Scene's gain in line with whatever level the Gain control sets.

### ASAF Scene – Gain Control

### Transform

You reach for the Transform controls laid out below to make positional changes inside an ASAF Scene.

### ASAF Scene –Transform

- Mirror Left/Right: Tick this checkbox to swap sounds' positions from left to right by flipping the whole scene.
- Mirror Up/Down: Fill this checkbox in to flip sound's vertical placement by turning the scene upside down.
- Mirror Front/Back: Tick this checkbox for a front-to-back flip of the whole scene, swapping where sounds sit along the front–back axis.
- Rotation Enable: Filling the checkbox in switches on the Yaw, Pitch, and Roll parameters and applies them per their respective values.
- Yaw: Swings the scene left or right about the vertical axis.
- Pitch: Tips the scene forward or back about the horizontal axis.
- Roll: Tilts or rolls the scene from side to side.

### Spatial Filter

### ASAF Scene – Spatial Filter

- Enable: Ticking the Enable checkbox switches the plugin on and reshapes the scene per the Base Gain plus each of the four filters' settings, every filter governed by its own batch of filtering parameters:
- Base Gain: Fixes the overall gain the plugin applies.
- Filter Enable: Switches the individual filter on.
- Filter Shape: Sets whether the spatial filtering shape comes out an ellipse or a rectangle.
- Filter Azimuth: Fixes the azimuth coordinate at the individual spatial filter's center.
- Filter Elevation: Fixes the elevation coordinate at the individual spatial filter's center.
- Filter Width: Fixes the width of the individual spatial filter shape in degrees.
- Filter Height: Fixes the height of the individual spatial filter shape in degrees.
- Filter Focal Gain: Fixes the gain for whatever audio falls inside the individual filter's spatial boundary.

Filter Focal Gain comes in handy when you need to strip an unwanted sound arriving from one particular place or direction. For that, set the filter's position and spread controls to blanket that area, drop the Base Gain to 0.0 db, and take the Focal Gain to -Inf db.

### Metadata

Rather than handling it in the Track Index, the ASAF Scene Metadata part of the Audio Inspector lets you attach the right metadata information to the scene through the settings below:

### ASAF Scene – Metadata

- Content Type: This drop-down menu sorts the object into either Music and Effects or Interactive.
- M & E Tag: Once the content bears a Music and Effects tag, this dropdown's options help you define the object more precisely—for instance, Music, Effects, Dialogue, Narration, etc.
- Interactivity: Once the content was tagged Interactive, an entry chosen from this list defines the object further, perhaps Commentary or Audio Description.
- Language: This dropdown lets you set the content's language.
- Salience: Hands the object audio a level of importance so the ASAF export

encoder can rank it against the project's other ASAF objects.

- Post Reverb: While active, the object is configured so the playback application, such

as Vision Pro, can read the room characteristics of the users' listening environment and, if they wish, layer in a fitting reverb setting. Post Reverb stacks on top of whatever reverb settings the ASAF Object Reverb noted above applies. It leaves the output from the ASAF Renderer plugins untouched, though.

### ASAF Channel Controls

The parameters below let you set the metadata for a Channel Bed:

### ASAF Channel – Metadata

- Content Type: This drop-down menu sorts the bed into either Music and Effects or Interactive.
- M & E Tag: Once the content bears a Music and Effects tag, this dropdown's options help you define the bed more precisely—for instance, Music, Effects, Dialogue, Narration, etc.
- Interactivity: Once the content was tagged Interactive, an entry chosen from this list defines the bed further, perhaps Commentary or Audio Description.
- Salience: Hands the audio a level of importance.
- Language: This dropdown lets you set the content's language.
- Post Reverb: While active, the Channel Bed is configured so Vision Pro can read the

room characteristics of the users' listening environment and layer in a fitting reverb setting. Post Reverb leaves the output from the ASAF Renderer plugins untouched.

### Effects

Ambisonic-native Fairlight FX plugins — the Limiter, Channel Dynamics, and EQ among them — together with compatible Ambisonic-native third-party effects in AU and VST form. The Fairlight FX plugins are documented more fully in Chapter 181, "Fairlight FX." As for working with VST, VSTi, and Audio Units plugins, that's covered in Chapter 180, “Audio Effects.”

### ASAF Monitoring

Fairlight gives you options for choosing the output monitoring source you'd like to hear, plus the output format you'd like to hear it in.

### Selecting the ASAF Master as the Monitoring Source

To make the ASAF Master bus your monitoring source, click the Bus Monitoring menu off at the far right of the Transport control and pick ASAF out of the dropdown.

### ASAF Monitoring Source Selection

### Selecting a Monitoring Format

To pick a monitoring format, click the dropdown beside the speaker output level control. Among the various options you'll spot Binaural, for monitoring over headphones. With a format chosen, the matching decoder slots automatically into the monitoring path, and the audio travels to your Audio I/O and out to your speaker system.

### Monitoring Output Format selection

### ASAF Binaural Monitoring with Head Tracking

Having picked the Binaural option for your output format, you can also monitor your ASAF mix over headphones with Head Tracking support, delivering the full Apple Spatial Audio experience.

### Enabling Head Tracking

You turn head tracking on by heading to Preferences > Control Panels > Head Tracker. NOTE: These settings only need configuring when you're on a third-party head tracker rather than compatible Apple AirPods.

### Head Tracker preferences

This puts two buttons to the left of the Monitor Bus Source dropdown right beneath the docked Video Monitor panel: HT: Toggles Head Tracking on and off. CAL: Sets the tracker's current direction as the “Front,” or point of origin. With compatible AirPods this button isn't needed and won't show, since calibration runs on its own.

### Head Tracking Video Viewer Overlay

Binaural Head Tracking further lets you lay an overlay over the video viewer for checking your mix against the picture: click Headtracking Display > On, which drops an onscreen crosshair marking the current head (headphone) orientation. That submenu also carries a Show Torso option, dropping a head and torso into the video viewer that turns along with shifts in the head tracking angles and positions.

### Head Tracking Video Viewer overlay

### ASAF Metering Options

### ASAF Loudness Standard

An Apple ASAF loudness standard is on hand within the Metering section of the Fairlight Monitoring Panel. Switching it on means making sure that panel is showing. If it's hidden, click the Meters button in the Interface Toolbar, then pick Apple ASAF off the Loudness menu.

Selecting Apple ASAF from the Loudness menu in the Monitoring Panel

### Mixer and Track Header Meters

Fairlight Ambisonic metering leans on one composite bar-graph meter across the Mixer, Track header, and Meter panel. Unlike other audio formats, these don't line up with particular speaker positions or levels you'd watch to gauge what the signal is doing. As an alternative, bar-graph meters that lay out Ambisonic signals as discrete, separate bus streams are available by choosing Fairlight > Immersive Audio > Ambisonics Channel Metering.

Default Ambisonics metering (left) and Discrete Channel metering (right)

Monitoring Panel meters with Ambisonics Channel Metering enabled

### Space View

Space View is a 3D interactive workspace where you watch the real-time positions and automated movements of your unmuted sound sources, across either of two Scene Modes (Room or Spherical Plane), as covered below. Open Space View by heading to Fairlight > Immersive and picking Space View. NOTE: A source shows up only when it's unmuted and its fader level sits above -70dB.

### Space View Controls

Space View provides the control options below; paired with the track mute and solo buttons, they're highly flexible and let you zero in on individual sources or groups of sources.

### Space View of an Immersive Mix

Over in the workspace's lower left corner sit four buttons letting you view your sound sources from various angles or perspectives. Rotate the workspace freely by holding Command-Option-Shift while you drag. To snap back to a default view, click one of the perspective buttons. Across the window's lower edge sit the following checkboxes:

- Scene Mode: This dropdown flips the Space View mode between Room and Spherical, as shown below.
- Ambisonics Metering: This checkbox switches on Ambisonics sonar-type metering while you work on Ambisonic mixes.
- Auto Zoom: Switched on, this function zooms the view in or out on its own, going by how close the sound sources sit overall to the listening position shown in the 3D space.
- Compact Meters: This option swaps the larger halo-style meters for smaller bar-graphs.
- Show Active Level Only: Click this option to hide the names of silent sound sources.
- Show Beds: This option brings up the labels and meters for ASAF Channel Beds feeding the ASAF Master.

The choices in the drop-down menu to the right of the checkboxes set which objects turn up in the virtual space:

- Show Only Selected: Displays sources based on tracks you've picked in the Mixer or timeline.
- Show Visible: Displays only the active audio sources for tracks left unhidden.
- Show All: Every sound source shows and is labeled.

### Spherical Plane view of an Immersive Mix

Sources can be freely repositioned in the 3D sound field in step with your mouse movements (Left/Right and Forward/Backward):

- Hold Command while moving the mouse forward and back, and the sound

source travels up and down within the sound field.

- Hold Command while moving the mouse left and right, and the sound source travels

left and right within the sound field. Every change you make can be automated (Touch and Pan) and saved.

### ASAF Rendering

With the Timeline Range you want to export set, your ASAF mix can go out as either an ASAF BWF or an APAC MP4: head to the Fairlight menu > Immersive Audio > Export Master File, then from the Format dropdown pick Apple Spatial Audio Format BWF or else Apple Spatial Audio Format MP4, and click the Export button.

### Delivery

On the deliver page, a pair of render settings let you render Apple Vision Pro files for review and final delivery.

### Render Settings– Custom Export

Vision Pro Review: Builds a small MV-HEVC package for previewing. Apple ‘shares’ the resulting file across to the Apple Vision Pro over Wi-Fi, where you watch it in the Apple Immersive Video Utility (AIVU) app, found on the App store. Vision Pro Bundle: Builds a large ProRes file bundle you can archive or run through Apple Compressor to ready it for Apple TV playback. ASAF: Turns out an ASAF audio mix using WAV or MP4 formats. VR180: Produces a stereoscopic video file that conforms to VR180.

### Bypassing Transitions

Add a transition to an immersive timeline and it gets pre-rendered, becoming a single playback track. The XML produced for immersive content lays out how playback switches among these rendered streams (footage, then the pre-rendered transition, then footage again). Within the Advanced Settings of the Render Settings panel, you can bypass visionOS transitions (Always), honor them according to their timeline status (’With transition settings’), or carry them as they sit in the timeline (Off).

### Bypass Transition settings

### Streaming to the Apple Vision Pro

Streaming to the Apple Vision Pro is possible from the edit, color, Fusion, and deliver pages in DaVinci Resolve: head to the Workspace menu, choose ‘Stream to visionOS,’ and pick your AVP device. For smooth streaming, a fast wireless network is advised (Wi-Fi 5 minimum; Wi-Fi 6 preferred).

### The Steam to visionOS option

### About Apple Immersive Video Utility

The Apple Immersive Video Utility is a purpose-built macOS and visionOS app meant to smooth the creation, management, and playback of Apple Immersive Video content. Geared toward professional filmmakers and immersive media creators, it lets users import, organize, package, and review 8K stereoscopic video files carrying a 180-degree field of view and Spatial Audio. It backs the creation of AIVU (Apple Immersive Video Universal) files, opening up metadata inspection and modification for post-production workflows. Users can assemble playlists, sort and search their libraries, and even stream content straight to one or more Apple Vision Pro devices.

### The Apple Immersive Video Utility

</content>
