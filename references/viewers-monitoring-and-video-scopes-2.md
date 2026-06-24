# Viewers Monitoring And Video Scopes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Up/Down Arrow: Jumps the playhead onto the first frame of the clip before or after it.
- Left/Right Arrow: Steps the playhead one frame backward or forward each press.
- Shift-Left/Right Arrow: Steps the playhead one second backward or forward each press.

### Controlling Playback Using the Spacebar and JKL Keys

Playback can be started and stopped with the spacebar, or you can adopt the JKL keyboard shortcut scheme for driving playback: J runs it backward, K halts it, and L runs it forward. These shortcuts have plenty of further applications. For details, refer to Chapter 35, “Preparing Clips for Editing and Viewer Playback.” under “Using JKL to Control Playback”

### Skimming in the Viewer

Footage can be skimmed in any viewer across the Media, Cut, Edit, Color, and Deliver pages: hold down the C key and drag the pointer back and forth within the viewer.

### Fast Review on the Color Page

The Fast Review playback command (Playback > Fast Review) has now arrived on the Color page. Built to help you scan long runs of clips at speed, choosing it kicks off accelerated playback through the Timeline, with the playback rate scaled to the length of each clip you pass through. Longer clips race by, while shorter ones play nearer to real time.

### Navigating Using Timecode

You can also enter timecode in absolute or relative terms to reposition the playhead in the Color page Viewer. As you type timecode, key in each pair — hour, minute, second, and frame — one after another, using a period to stand in for a pair of zeros and speed entry along. Whatever pair (or period) you type last is always taken as the frame number, and any pairs you skip are assumed to be zero. There's no need to key in colons or semicolons. For details, refer to Chapter 35, “Preparing Clips for Editing and Viewer Playback.” under “Moving the Playhead Using Timecode.”

### Viewer and Transport Timecode Displays

Two timecode displays sit on the Viewer, and each one defaults to a different timecode setting. The upper display, the Header timecode display, defaults to showing the Source timecode. The lower display, the Transport timecode display, defaults to the Record timecode. That bottom display can be switched among four options, much like those in the Data Burn-In palette. To switch a timecode display to another setting: The upper timecode display is a drop-down menu you can set to whatever timecode, frame number, or KeyKode you'd like shown. The lower timecode display can likewise be switched by right‑clicking it and picking the value type to show from the contextual menu that opens. The options are these:

- Timeline Timecode: The timecode that matches the playhead's spot within the overall Timeline.
- Source Timecode: The timecode that matches the playhead's spot relative to the

currently selected clip.

- Timeline Frame: The frame count that matches the playhead's spot within the overall Timeline.
- Source Frame: The frame count that matches the playhead's spot relative to the currently

selected clip.

- KeyKode: The KeyKode number that matches the media's KeyKode track, where one exists.
- Show Timecode at 30 FPS: Presents 24 fps timecode, via 3:2 pulldown, as 29.97 fps timecode.

Has no effect on video playback.

- Copy and Paste Timecode: A pair of commands makes copying and pasting timecode values easy.

Likewise, the upper timecode display can instead be switched to show KeyKode, when it is present, inside the header of a DPX media file.

### Enhanced, Full, and Cinema Viewing

To grow the Viewer, switch on Enhanced Viewing mode via Workspace > Viewer Mode > Enhanced Viewer Mode (Option-F).

### Enhanced Viewing Mode

While in Enhanced Viewing mode, the Viewer behaves just as it does at normal size, but it grows to occupy the full area of screen above the palettes and Keyframe Editor. Press (Option-F) once more to leave Enhanced Viewing mode. This comes in handy when you need a tighter view of the image — to make detailed corrections, study noise patterns up close, perform a delicate color selection, or trace an elaborate PowerCurve.

### Color page in Enhanced Viewer mode

### Full Viewing Mode

While in Full Viewing mode (reached by choosing Workspace > Viewer Mode > Full Page Viewer, by pressing Shift-F, or by Option-clicking the Enhanced Viewing mode button), the Viewer claims still more space by hiding the palette controls, yet leaves the bottom strip of the DaVinci Resolve UI intact — there you still find the transport controls, the Onscreen Control dropdown menu, the timecode readout, and the page buttons. This mode helps when you want a closer look at the image but still need a small set of onscreen controls within reach.

### Color page in Full Viewer mode

### Cinema Viewing Mode

There's also Cinema mode, which gives you full-screen viewing. Reach Cinema mode by choosing Workspace > Viewer Mode > Cinema Mode Viewer (P). Within Cinema mode the menu bar disappears, and the image fills the screen with none of the usual onscreen controls present. Sliding the pointer across the screen exposes a hidden set of onscreen controls — a play button, jog bar, mute button, and exit button (which turns off Cinema mode). You can additionally lay scopes over the image, which proves useful in on-set settings.

### Color page in Cinema mode

Cinema mode serves well for thorough media review during on-set and digital dailies work when you're remote and have no secondary video display.

TIP: Should you want to overlay timecode on the image in Cinema mode for reference, the controls inside the Data Burn-In window (Workspace > Data Burn-In) let you configure whatever information you'd like shown throughout playback.

### Safe Area Overlays in the Viewer

A set of safe area overlays can be shown or hidden within the Viewer. Every safe area overlay option lives in the View > Safe Area menu. Each one can be turned on or off on its own from that menu.

Viewer displaying extents, center, safe, action and title area overlays On/Off: Toggles all the currently selected safe area marker options on or off together. Extents: A boundary showing the precise outer edge of the frame. Particularly handy when the safe markers use an aspect ratio other than the one the Viewer is currently set to. Action: A boundary marking out the frame's outer 90% action safe area. Title: A boundary marking out the frame's outer 80% title safe area. Center: A crosshairs pinpointing where the frame centers. Aspect: Turns on the View > Select Aspect Ratio submenu so you can alter the aspect ratio of the safe area markers. The aspect ratios you can pick among are: 1.33 (a.k.a. 4:3), 1.66, 1.77 (a.k.a. 16:9), 1.85, and 2.35.

### Use Gray Background

Ticking the “Use gray background in viewers” box within the User Preference's UI Settings turns the Viewer's empty area (where there is any) a lighter gray, which makes it easier to tell which parts of the Viewer are black due to blanking from those that are merely empty because of how the image is zoomed or panned.

### Monitor Calibration

Those who calibrate displays with Light Illusion's LightSpace CMS or with SpectraCal's Calman can now press DaVinci Resolve into service as a sync-able pattern generator. That means DaVinci Resolve can put out color patches, synced by LightSpace, to your display over whichever video interface ties into your computer. A monitor probe — itself driven by LightSpace — reads these synchronized color patches, stores the probe data, and weighs it against the original color values of the output color values to characterize that display. To use the feature, you must first hold a licensed copy of LightSpace CMS, a Windows application. Syncing depends on a wired or wireless LAN being on hand so the LightSpace application can talk to DaVinci Resolve. To sync LightSpace CMS with DaVinci Resolve so it acts as a pattern generator client: 1 Launch LightSpace on whichever Windows computer hosts it. 2 With LightSpace open, click the Network Manager button. A window opens listing the two network IP addresses that LightSpace uses. Jot them down, then click the Enable button.

The Network Manager dialog in LightSpace CMS 3 Within DaVinci Resolve, pick Workspace > Monitor Calibration > LightSpace. 4 After the LightSpace dialog appears, enter the latter of those two network IP addresses LightSpace shows into the Remote Machine field, and verify that the Port number agrees. Next, click the Connect button.

The Calibration dialog in DaVinci Resolve, connected to LightSpace CMS via WiFi When all is working, the LightSpace dialog in DaVinci Resolve should display the word “Connected,” and the Network Manager dialog in LightSpace should report that there is 1 available client/s. You can then dismiss the Network Manager dialog in LightSpace and follow the steps laid out in the LightSpace CMS documentation for characterizing your display and for building and exporting a display LUT (in the .cube format) you can use as a display LUT in DaVinci Resolve. As an alternative, a display LUT exported from LightSpace can instead be loaded onto an external video processing device. 5 Once finished, hit Disconnect inside the LightSpace dialog, then hit Cancel to dismiss the window.

### Viewing Broadcast Safe Exceptions

Choosing View > Display Broadcast Safe Exceptions makes the Color page Viewer show a false-color overlay that flags in blue the parts of the picture breaching the currently selected broadcast safe level set in the Color Management panel of the Project Settings.

Areas of the image that violate broadcast safe are highlighted in blue To read further about how broadcast safe limiting works from the Project Settings' Color Management panel, consult Chapter 127, “Automated Grading Commands and Imported Grades.”

### Comparing Clips in the Viewer

Being able to weigh one clip against another is a core part of color correction work. DaVinci Resolve gives you three distinct ways to do it. The Gallery can show two clips side by side for split screen comparison. You can also draw on different reference modes to bring a timeline clip or reference movie straight into a split screen comparison. Lastly, the Split Screen controls let you lay out multi-frame arrangements within the Viewer.

### Saving and Wiping Stills in the Gallery and Timeline

The Gallery on the Color page gives quick reach to stills you've saved off the various clips in the Timeline. While the dedicated Gallery page offers a fuller interface for browsing presaved “looks” and for importing stills out of other projects, you can save, organize, and browse stills right inside the Gallery of the Color page. Stills get saved in the DPX file format. After you've saved one or more stills, you can arrange split screen wipes in the Viewer, which mirror across to your external display.

Holding a Gallery still up against the current shot eases the job of matching grades What follows is a condensed rundown of still store and split screen behavior to get you up and running fast. To save a still, do one of these:

- Choose Color > Stills > Grab Still (Option-Command-G).
- Right-click on the Viewer and choose Grab Still.

To wipe a still, do one of these:

- Pick a still in the Gallery, then on the top Viewer toolbar click the Image Wipe button.
- Choose Color > Stills > Play Still (Command-W); alternatively, right-click within the Viewer and pick Toggle Wipe.
- Double-click a still in the Gallery.

To adjust a wipe in the Viewer, do one of these:

- Drag the pointer within the Viewer to move the wipe.

### The different wipe customization modes

To customize a wipe in the Viewer: On the Viewer toolbar, click any of the Wipe mode buttons. The modes available are: Horizontal: Lets you set the wipe's two halves on either side of a vertical border. Dragging the pointer shifts the wipe border left and right. Vertical: Lets you set the wipe's two halves above and below a horizontal border. Dragging the pointer shifts the wipe border up and down. Diagonal: Lets you set the wipe's two halves across an adjustable diagonal border. Dragging the pointer moves the wipe to the left and right. Hold the Option key and drag, circling the pointer around, to spin the wipe's border to whatever angle you like. Mix: Lets you blend the two images together for comparison. As you drag the pointer, the fade balance between one image and the other shifts. Alpha: Lets you employ a qualifier to set transparency within the current clip's image while weighing it against a Gallery still acting as the backdrop. Drop a node onto the grade and let the qualifier key a particular color you want turned transparent (the green of a green screen, say). Then route that node's KEY output to the Alpha Output that turns up in the Node Editor. The portion of the foreground image the key isolates becomes transparent, so the Gallery still behind shows through. This can help when previewing how the lighting or grade of a foreground VFX plate reads once the image is composited over a particular background image held in the Gallery. Difference (A/B): Lets you see only the pixels that shift because of an operation on the node. For instance, if you pick this highlight and tweak the gain, only the pixels the gain altered would appear in the Viewer. Box: Lets you present the current clip as a picture-in-picture overlay sitting on the still behind. Dragging the pointer resizes the crop box around the edge of the reference image. Venetian Blind: Lets you weigh the two wiped images via alternating horizontal strips. Drag the pointer up or down to resize the alternating strips. Good for quickly checking vertical color uniformity, zeroing in on color and contrast shifts from top to bottom. Checkerboard: Lets you weigh the two wiped images via an alternating checkerboard. Drag the mouse left or right to flip between images by squeezing each check horizontally. Good for checking color uniformity across the width and height of two images.

Within the Viewer's option menu, pick one of these out of the Wipe Style submenu. Wipe Style: Steps through these modes in turn — Horizontal, Vertical, Diagonal, Mix, Alpha, Difference, Box, Venetian Blind, and Checkerboard. Invert Wipe: Swaps each half of the wipe (Option-W).

### Hover Scrub in the Gallery

When Live Preview is turned on in the Gallery option menu, the Hover Scrub Preview submenu lets you decide how Live Preview appears via a thumbnail in the Gallery and in the Viewer while your pointer hovers above a still, or above a LUT within the LUT Browser:

- You can opt to scrub both the thumbnail under your pointer and the Viewer, so you preview the current still's grade or a LUT over the span of the current clip in both the thumbnail and Viewer.
- You can opt to scrub the thumbnail alone, leaving the Viewer to display only the grade or LUT over the frame where the playhead sits.
- You can switch off scrubbing entirely, in which case both the thumbnail and the Viewer show only the grade or LUT over the frame at the playhead's position.

### Copying Grades from Stills in the Gallery

Stills also carry the grade of the clip they came from, so they can serve to copy grades between clips or to bank grades you may want later. To copy a grade off a still onto a clip, do one of these:

- With one or more Timeline clips selected, right-click a Gallery still and pick Apply Grade.
- With one or more Timeline clips selected, middle-click a Gallery still.

When you copy a still this way, the saved grade fully replaces the grade in the target clip, unless you've engaged the “Preserve number of nodes” option found in the Gallery's contextual menu. For fuller guidance on working with the Gallery — including ways to organize the Gallery browser, instructions for Albums, Power Grades, and Memories, plus other methods of copying grades and handling advanced grade management — see Chapter 141, “Using the Gallery.” and see Chapter 142, “Grade Management.”

### Different Viewer Reference Modes for Wipes

Although wiping against reference stills via the Gallery is common, changing the reference mode further opens up wiping against a Timeline clip, or — where one has been assigned to the current Timeline — against an Offline Reference Clip or Timeline. To switch the Viewer reference mode, do one of these:

- Within the Viewer's option menu, pick an entry from the Reference Wipe Mode submenu.
- Pick from the Reference Mode icons sitting along the top of the Viewer.

There are three reference modes:

- Gallery: The default reference mode. Wipes the current clip set against a Gallery still.
- Timeline: Wipes the current clip set against a different Timeline clip by means of the Wipe Timeline Clip command (see below).
- Offline: Wipes the current clip set against an offline video assigned to this Timeline.

For details on attaching Offline References to a timeline for comparison purposes, turn to Chapter 55, “Preparing Timelines for Import and Comparison.”

### Wiping Between Clips in the Timeline

If you'd like to wipe the current clip against another Timeline clip but skip saving a still to the Gallery first, a dedicated procedure exists. Wiping between two clips in the Timeline reference mode goes like this: 1 Click the thumbnail of whichever clip you wish to compare first. 2 (Optional) A “Gang timeline wipe with current clip” option, found in the Viewer option menu, holds steady the gap separating the current clip from the timeline clip being wiped against, even as you shift the current clip selection to other clips. With it on, the offset between the timeline wiped clip and the current clip holds as you move the clip selection. You can advance the timeline reference clip one frame by pressing Command-Option-Right Arrow, and step it back one frame with Command-Option-Left Arrow. This allows precise positioning. With the option off, the timeline wiped clip stays put no matter which clip you pick. 3 On the thumbnail of the second comparison clip, right-click and pick Wipe Timeline Clip out of the contextual menu. The two clips appear split screened against each other. NOTE: Wipe Timeline Clip surfaces in the contextual menu only when you right-click a Timeline thumbnail that hasn't been chosen as the current clip.

Change a Timeline Wipe Using the Timelines Album of the Gallery While Wipe Timeline Clip displays a wipe of the current clip against any other Timeline clip, the Gallery's Timelines album can be opened so that clicking among its clips changes which timeline clip serves as the wipe target (outlined in blue) while leaving the current clip untouched (outlined in orange).

### Using Split Screen Modes

A collection of split screen modes adds further ways to weigh several images in the Viewer at once. They give you grid and side-by-side comparisons spanning several shots and several versions, every one routed out to video for monitoring on your external video display. As an example, the Split Screen Versions mode can display every single version applied to the current clip in a grid, making them easy to evaluate. The clip currently selected in the Timeline is highlighted in gray, so you can keep your bearings. To turn on a split screen mode, do one of these:

- Click the Split Screen button on the top Viewer toolbar, and pick a split screen method from the drop-down menu that opens in the Viewer toolbar at the right.
- Within the Viewer's option menu, pick an entry from the Split Screen submenu.
- Press Option-Command-W to toggle Split Screen on and off, using the last chosen option.
- Right-click the Viewer and, from the contextual menu's Split Screen submenu, pick an entry.

NOTE: With any split screen mode active, the Viewer hides every other onscreen control — Power Window shapes among them — and won't show them again until split screen is switched off.

A four-shot grid produced by the Split Screen > Selected Clips mode

### Viewing and Choosing the Current Selection

In every split screen mode, the current selection carries a gray outline. For a cleaner comparison that outline can be turned off: within the Viewer's option menu, Split Screen > Show Outline toggles it on and off. Within certain modes, double-clicking a given frame of the split screen view also lets you swap the current clip, choose the active version, or lay on a gallery grade.

### Available Split Screen Modes

You can pick from among these split screen modes:

- Current Group: Displays as many as 16 clips sharing the group of the current clip. In this mode a double-clicked frame has no effect.
- Highlight Modes: Displays a four-up view in which you can, all at once, take in (going clockwise) the RGB image of the clip, then its gray matte, next the high contrast matte, and finally a difference matte that comes from weighing the node's input against its output. Here too, double-clicking a frame does nothing.

Viewing a key using the Split Screen > Highlight Modes

- Neighbor Clips: Displays the four clips that immediately bracket the current clip. The two prior clips take the upper left and upper right spots, the current clip lands at the lower lefthand corner, and the next one fills the lower right. A double-clicked frame does nothing here. How many neighboring clips appear in this mode is governed by the “Neighboring Clips in Split Screen” parameter found in the Color panel of the User Preferences.
- Playheads: Within the Color page Viewer, presents side-by-side views of as many as four playheads shown in the Mini-timeline after you select several playheads from the Color > Active Playhead submenu. For every playhead you reveal (up to 4), its frame shows in a 2-up, 3-up, or 4-up grid. When enabled, an outline in the Viewer flags which playhead is active at the moment. This serves both for weighing several clips and for weighing different frames inside one clip. Switching among the active playheads is done by clicking the clips in the split screen Viewer

### Placing three playheads in the Mini-timeline

- Selected Album: Choosing this option brings up in the Viewer a split screen of the grades from each still in that album, shown as they would look on the current clip. A double-clicked frame applies that gallery grade onto the current clip. As many as 16 grades can appear.
- Selected Clips: Displays every Timeline clip currently selected, up to 16 at a time. A click on a clip moves the playhead onto that clip's first frame.
- Selected LUTs: Lets you preview, all at once, how different LUTs affect the current clip — shown as a split screen in the Viewer — by Command-clicking up to 16 LUTs in the LUTs browser that you'd like to preview.

With the Selected LUTs split screen option you can audition a batch of LUT looks together

- Selected Still Grades: When you pick this option, selecting stills in the Gallery of the Color page shows each grade tied to those stills as it looks applied to the current clip, in a split screen layout. Double-clicking a frame applies that gallery grade to the current clip.

Previewing four gallery grades using the Split Screen > Gallery Grades mode
