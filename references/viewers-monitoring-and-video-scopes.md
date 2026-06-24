# Viewers Monitoring And Video Scopes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Viewers, Monitoring, and Video Scopes

A Viewer shows you what you're working on, supplies a UI for transport controls and image comparison, lets you draw windows and drag on-screen controls, and surfaces an assortment of warnings and information you won't find elsewhere. Yet professional pipelines also demand real-time monitoring on a calibrated display through supported video I/O hardware. Finally, video scopes deliver a sharper read on the condition of the video signal in front of you, and DaVinci Resolve ships with built-in scopes you can lean on for creative calls and troubleshooting alike. The pages here go deeper on the Color page Viewer, external monitoring with display calibration, and video scopes.

### Using the Viewer

Your window onto the Timeline is the Viewer. Whatever clip and frame sit at the playhead's current spot show up in the Viewer. The Viewer also doubles as a workspace for sampling colors, tuning Windows, leaning on split screen stills for reference, and a host of other display-centered jobs. When a video out interface is hooked to a broadcast display or projector, the video output usually mirrors what the Viewer holds.

### The Viewer Title Bar

Controls and indicators along the Viewer title bar make it simple to steer and stay aware of exactly what you're looking at.

The Color page Viewer title bar with its controls Here is what the Viewer title bar's controls do: Zoom and Fit menu: Lets you zoom to an exact percentage, or pick Fit to size the image to the Viewer's whole available area. Viewer Mode: Flips the Viewer type over to the Image Wipe. Split Screen, or Highlight modes. Viewer Mode: Flips the Viewer type over to Split Screen Viewer Mode: Flips the Viewer type over to Highlight Playback frame rate indicator: This dot reads green while playback stays in step with the project's frame rate, and red once playback drops under real time. The present frame rate appears just to its right. Timeline name and selection drop-down: It shows the name of whatever timeline happens to be open at the moment. The drop-down beside it lets you bring in any other timeline belonging to the current project. Timecode viewer and drop-down: Through a second timecode viewer you can pick an alternate timecode/frame count/KeyKode value, shown at the same time as the timecode viewer beside the transport controls below. A drop-down lets you set whether source (clip) or record (timeline) timecode is shown. Viewer Guides: Lets you arrange Safe Area together with custom Guides and Rulers. Proxy Handling: Lets you go with either proxies or original media as playback runs. Switch Timeline Resolution: Lets you alter which timeline resolution preset is active. Bypass Color and Fusion and drop-down: Switches off grades and/or Fusion effects on command. Expand Viewer drop-down: Stretches the Viewer to fill your workstation display's full area above the palettes. Option menu: Holds options affecting how the Viewer behaves.

The Color Viewer's option menu, showing all the Viewer-related commands

- Highlight: Carries options that switch on the Highlight, Black and White, and Difference views.
- Show RGB Picker Values In: Pick whether the RGB picker reports its values on an 8-bit or 10-bit scale.
- Show Viewer Channels: Offers options to pick every channel, or just R, G, or B individually, in the Viewer.
- Split Screen: Holds options for switching the Split Screen view on or off and for what it shows.
- Timeline Sort Order: Offers options governing the order of the timelines within the drop-down menu at the

top of the Viewer. The choices are: Alphabetical, Creation Date, or Recently Used (which lists the 10 most recently active timelines).Previous Timeline: Opens whichever timeline precedes the current one in the Timeline drop‑down menu list.

- Next Timeline: Opens whichever timeline follows the current one in the Timeline drop-down menu list.
- Show Viewer Options: Reveals or hides that second row of icons across the top of the Viewer, according to the mode you happen to be in.
- Show Marker Overlays: Any markers the paused playhead lands on show up superimposed over the Viewer.
- Window Outline: Carries options for how a Power Window's window outline is drawn. On, Off, or confined to the UI viewer while staying off your video output.
- Video Output Options: Offers options for what your video output signal carries, namely Flags, Markers, Keyer Overlays, plus the choice to Gang the Zoom level with the Viewer.
- Markers: Shows whatever markers have been placed on the timeline. Pick one from the list to jump to that marker.
- Show Reference Wipe: Switches the reference wipe on or off.
- Reference Wipe Mode: Carries options that alter which sources feed the reference wipe.
- Wipe Style: Carries options that alter which kind of reference wipe gets used.
- Invert Wipe: Flips the current reference wipe.
- Reference Reposition: Brings up the Reference Sizing controls, which let you resize and reposition the reference clip.
- Gang Timeline Wipe With Current Clip: Keeps the gap between the current clip and a timeline clip you're wiping against intact as you shift the current clip selection onto other clips.

### Viewer Guides

### Safe Area

A whole set of handy framing guides drops over the Viewer from this drop-down menu, showing you which slice of the image stays and which gets cropped away should you alter the Timeline's aspect ratio. You toggle the framing guides on and off via the Safe Area Framing Guide icon in the Viewer, and the precise guides come from the drop-down menu. Social Media: 1:1, 4:5, 9:16, 1.91:1, 16:9. Broadcast and Film: Default (your current timeline aspect ratio), 1.33, 1.66, 1.77, 1.85, 2.35. "Safe Area Guides: These choices lay extra guide lines over the Viewer that shield your composition against getting clipped at the outermost edges of a physical cathode ray tube. Although a bit of a relic now that flat-screen digital televisions rule, plenty of legacy programs still hold to these guidelines. Even so, Safe Areas remain useful guides for keeping your image from being unintentionally clipped across the assortment of mobile devices and social media sites people rely on today.

- Extents: Show the full boundary of the frame.
- Action: Keep all movement and important action within this box.
- Title: Keep all on screen text within this box.
- Center: Designates the exact middle of the image.

Alongside the Action, Title, and Center overlays, you can switch the extents safe area overlay on or off. These features live at View > Safe Area > Extents."

The Safe Area Framing Guide icon and the possible framing options

### Custom Guides and Snapping in the Timeline Viewer

The timeline viewer lets you build guides of your own. That way you can fully tailor and pin down particular geographic spots in the frame, then have the image snap onto those spots during other operations. You can lay down Guides, the colored lines crossing the frame horizontally or vertically, plus Rulers, which line measurement metrics along the frame's edges. Both Guides and Rulers act as overlay tools for tuning your video position, appearing only in the viewer rather than your finished project output.

### The Timeline Viewer with Guides and Rulers enabled

You can show Guides or Rulers separately by clicking the relevant icon, found under Ruler Guides inside the Timeline viewer's Viewer Guides drop-down menu. Each can likewise be switched on by itself through the View > Rulers and View > Guides menus.

The Ruler Guides section of the Viewer Guides dropdown

To Show and Modify a Ruler: 1 Turn the Ruler on by choosing View > Rulers > On, or by clicking the Ruler Icon in the Viewer Guides dropdown of the Timeline Viewer. 2 Decide which metric the Ruler should use through View > Rulers, or by right-clicking the Ruler in the Viewer. Pixel: Marks the ruler as a pixel count out from the origin point (0,0) at the frame's center, on a standard x/y cartesian coordinate graph that mirrors the Position field in the Video Inspector. Percentage: Marks the ruler as a percentage distance out from the origin point (0%, 0%) at the frame's top-left. Across the top, the ruler goes from 0% on the left to 100% on the right, while down the side it reads 0% at the top down to 100% at the bottom. So a point sitting dead center in the frame lands at (50%, 50%).

### The Add/Edit Guide dialog

To Show and Create a Guide Line: 1 Switch the Guides on via View > Guides > On, or by clicking the Guides Icon inside the Timeline Viewer's Viewer Guides dropdown. 2 Add a fresh Guide via View > Guides > Add Guide, or right-click the Ruler in the Viewer and pick Add Guides. 3 Within the Add Guide dialog, dial in the new guide's position and orientation, then click Add. Units: Pick the metric the guideline should follow. Pixel reports the pixel count out from the guide's origin point, whereas Percentage reports the percentage distance from the frame's top left at 0%,0%. Position: Type in a value for the spot in the frame where the guideline should cross. The line can also be click-dragged in the viewer to place it by eye (a small popup surfaces the exact position value while you move it). If you like, click the lock icon so this guide can't be nudged by mistake. Orientation: Pick a horizontal or vertical orientation for the line. Color: Pick the guideline's color from the choices on offer.

To Modify a Guideline:

- Click and drag the line anywhere within the viewer; a small pop-up window surfaces to report the exact position value to you.
- For better legibility you can recolor the Guidelines by right-clicking inside the Ruler and picking a fresh color off the Guide Color context menu.
- Remove a line by right-clicking it in the viewer and picking Remove Guide.
- Alter an existing line's position and orientation by right-clicking it in the viewer and picking Edit Guide.
- Remove every line, only the horizontal ones, or only the vertical ones via View > Guides > and choosing which lines to drop. Right-clicking the ruler achieves the same thing.
- Pin Guides in place against accidental drift by clicking the small lock icon at the ruler's upper-left, or through View > Guides > Lock Guides.

Right-click the Ruler and a context menu opens for tuning every parameter of the Rulers and Guidelines Snapping to Guidelines By default, as you reposition the clip within the frame through the Transform Viewer controls, an image edge that drifts close to a guideline snaps onto it automatically, the guideline going purple to confirm it sits exactly. To turn that behavior off, just keep the option key down as you drag the image around the viewer, and the snap is skipped.

The Guidelines go purple once an image edge snaps onto that spot

### Proxy Handling

In the Cut page you can flip between playing back your original source media and the proxy media via the Proxy Handling icon in the Viewer, picking one of these options:

- Disable All Proxies: Picking this shuts proxies off entirely and forces playback from the original media alone. Should the original media be missing, a Media Offline graphic stands in for the clip.
- Prefer Proxies: Picking this plays back from the proxy files, and where a clip has no proxy file, the original media steps in on its own.
- Prefer Camera Originals: Picking this plays back from the original media files, and where a clip has no original media file, the proxy media steps in on its own.

The Viewer's Proxy Handling icon lets you decide how proxy files get used

### Timeline Resolution

Sitting at the Viewer's top-right, this drop-down menu lets you swiftly pick which resolution to work at. A Custom option opens the Timeline Settings panel so you can set your own options.

### The Project Settings quick menu

For more on the Timeline Settings, refer to Chapter 6, "Project Settings."

### Bypass Color Grades and Fusion

Through the Bypass Color Grades and Fusion Effects button/dropdown you can shut off every grade and effect you may have applied on the Color page and/or Fusion page, helping playback run better on lower-powered computers. Hit the button (Shift-D) to switch grading and effects off or back on, or right-click the button to reach a menu where you pick which things the button governs.

The Bypass Grades and Fusion button, pictured under a right-click that reveals its options

### Viewing Isolated Channels

Reach for the Show Viewer Channels submenu in the Viewer's option menu to flip the Color page Viewer between RGB, R, G, or B channels. That proves handy when judging one image channel for noise or other artifacts, or when color matching by comparing and tuning the individual red, green, and blue channels across two clips.

### The Viewer Toolbar

The Color page also lays out a toolbar above the image (just under the title bar) that makes enabling and disabling image wipe, split screen, and highlight viewing as easy as clicking one of these buttons, which then reveals further controls tied to each of those operating modes (covered elsewhere in this chapter). You can show or hide those options by clicking the Viewer option menu and unchecking Show Viewer Options.

The Color page Viewer toolbar, where the Wipe, Split Screen, and Highlight controls appear. You can spot the Highlight options in the bar beneath.

Along the way, these buttons give you an easy cue for when a comparison mode is on. Within each of these Viewer modes, the right controls for tailoring that view show up to the right of the Viewer toolbar.

### Showing Marker Overlays and Annotations

For Timeline and Clip markers, the Color page Viewer can display Marker Overlays and Annotations. Choose Show Marker Overlays off the Viewer's 3-dot option menu, or, via the Viewer overlay controls drop-down at bottom left, select the annotation mode.

With Show Marker Overlays checked, the Color Viewer renders any Marker Overlays (upper left) along with annotations.

### The Onscreen Control (OSC) Menu

Which onscreen controls you want to show and tune in the Viewer is your call through the Onscreen Control drop-down menu. Opening certain palettes switches on their matching onscreen controls automatically. As an example, opening the Window palette brings up the Power Window onscreen controls, and opening the Qualifier palette brings up the Qualifier onscreen controls.

### The onscreen control menu for the Viewer

A spread of choices awaits you, each one bound to a separate adjustment you can perform: Off: Every onscreen control drops out of sight, leaving the image in the Viewer free of clutter. Qualifier: Switches on the Color Sample cursor. To read more on using the Color Sample controls, see Chapter 135, "ColorSlice." Power Window: Switches the Power Windows onscreen control on and off. For deeper coverage of adjusting Viewer windows, refer to "Power Windows" see Chapter 138, "Secondary Windows." Image Wipe: Switches mouse-driven dragging of the split screen right on the Viewer on and off. For deeper coverage of split-screen work, see "Comparing Clips in the Viewer" later on here. Open FX Overlay: Reveals and hides whatever onscreen controls an Open FX plugin exposes within the currently selected node. Color Chart: Reveals and hides the color chart overlay, which lets you flag a color chart in the picture for use with the Color Match palette to build an automatic grade. Annotations: Brings the annotation tools into the toolbar. Annotating a frame that lacks a marker spawns a fresh Timeline marker. To read more on using Annotations, see Chapter 41, "Marking and Finding Clips in the Timeline."

TIP: As you work, you may sometimes want to briefly hide or reveal the onscreen controls for a clean, uncluttered look at the image you're tuning. Any set of onscreen controls can be toggled off and on without choosing Off in the menu by pressing Shift-` (tilde).

### Toggling Viewer Overlays On and Off

Hitting Shift-` (Tilde) flips the current Viewer overlay on and off. Commands for showing, hiding, and switching between overlays in the Color page Viewer live in the View > Viewer Overlay submenu. While most of this menu's options sit unassigned by default, you can map them to keys through the Keyboard Customization window.

### Onscreen Controls and External Displays

DaVinci Resolve was made to run with calibrated external displays wired to video output interfaces, and for most colorists handling broadcast or theatrical programs, this is the advised way to work when color-critical evaluation matters. For that reason, many onscreen controls tied to jobs like color sampling, window adjustment, and key manipulation get mirrored to your video output, so you can hide the Viewer on your computer's monitor and work off an external display alone. To set whether onscreen controls mirror to video out or stay off: Pick an option from the Window Outline submenu within the Viewer's option menu. The three options are:

- Off: Drops the window outline from both the external display and the Viewer.
- On: The default; keeps the window outline on both the external display and the Viewer.
- Only UI: Drops the window outline from your external display while keeping it in the Viewer.

To show clip flags on video output: Tick the "Show clip flags on video output" checkbox option within the Color page Viewer's option menu. Doing so paints one or more small colored flag overlays into the bottom-left corner of the video output. That keeps the flagged clips visible at all times on your grading hero display while you work, should that aid you in tracking whatever the flags are helping you stay on top of. By default it stays off. Limitations When Grading With the Viewer on a Computer Display Few computer displays can meet the color-critical tolerances or specs that quality control insists on for streaming, broadcast, or theatrical delivery. A further wrinkle is that, depending on the mix of workstation and computer display, the Viewer may not render each clip's image data the same way the calibration your operating system applies to your computer display renders it, varying with which OS you run DaVinci Resolve on. That can leave your computer display unfit, in its default state, for monitoring projects bound for the web's sRGB standard. For instance, grade a project on your computer display using the Color page Viewer and the resulting clip might not look identical in the QuickTime player or in other post-production applications.

You can address this in one of two ways:

- When running DaVinci Resolve on macOS, you can switch on "Use Mac Display Color Profile for viewers" within the Hardware Configuration panel of the System Settings. That lets DaVinci Resolve adopt whatever color profile you set under the macOS System Preferences, via the Displays panel's Color tab, leaning on ColorSync on macOS so DaVinci Resolve renders color the same way your computer monitor does. It now covers every color profile bundled with macOS, plus color profiles produced by calibration software like that from X-rite, Datacolor, or other applications. Where the computer supports it, an "Use 10-bit precision in viewers" option may also be available for you to switch on. Turn that on and the rendered output shown in QuickTime Player lines up with what the DaVinci Resolve Viewer shows.
- Failing that, you can put a dedicated Color Viewer LUT to work for calibration through the 1D/3D Color Viewer Lookup Table drop-down menu sitting in the Color Management panel of the Project Settings. This has you profiling your computer display for calibration just as you would an external display, with a probe plus color management software, then loading the resulting calibration LUT into DaVinci Resolve. Bear in mind that calibrating a monitor can only bring a high-quality display into standards compliance; it can't compensate for a display gamut that runs too small.

For more, head to the "Lookup Tables" section, see Chapter 4, "System and User Preferences." Put bluntly, if professional work is the goal, your grading belongs on some kind of calibrated external broadcast display, class A and 10- or 12-bit, hooked up through a Blackmagic Design video interface. Provided everything runs as it should, an image sent to video out of DaVinci Resolve ought to match one sent to video out of whatever other post-production application you use, and that should serve as your baseline when weighing the output of two different applications.

### Zooming into the Viewer

While using the Viewer to sample tricky colors or trace a detailed PowerCurve, zooming into the image can pay off. To zoom in or out of the Viewer, do one of the following:

- Bring the pointer inside the Viewer, then spin the scroll wheel to zoom the image in or out.
- Press Command-Equal to zoom in, or Command-Minus to zoom out.

To pan around the Viewer:

- Bring the pointer inside the Viewer, then middle-click and drag to pan the image around.

To reset the size of the Viewer image:

- Pick 100% (Actual Size) (Option-Shift-Z) off the sizing drop-down menu at the Viewer's upper left.
- Choose View > Zoom > Zoom to Fit (Shift-Z).

To enable or disable image zoom being sent to video out:

- Pick "Gang viewer zoom with video output" from the Viewer's option menu so the image on video out zooms to exactly match the Viewer's zoom level, letting you judge a zoomed-in slice of the image on your suite's hero display.

### Using the Jog Bar and Transport Controls

Controlling playback ranks among the Viewer's chief jobs. The jog bar, sitting right below the image in the Viewer, carries a playhead you can drag left and right to scrub through the currently selected clip as quickly as you can move the pointer. That jog bar playhead is tied to the playheads in the Timeline and Keyframe Editor. Move one playhead and all three move. How much of the Timeline the jog bar covers depends on whether the Node Editor sits in Clip or Timeline mode. Under Clip mode, the jog bar's width equals however long the currently selected clip runs. Under Timeline mode, its width equals the whole Timeline's combined duration. Below the jog bar, a row of transport controls hands you finer control over timeline playback.

- Previous clip: Jumps the playhead onto the first frame of the clip before this one.
- Reverse: Initiates 100% playback in reverse.
- Stop: Stops playback.
- Play: Initiates 100% playback.
- Next clip: Jumps the playhead onto the first frame of the clip after this one.
- Loop: Confines playback to the current clip, wrapping back to the first frame when you're playing

forward to a clip's end, or wrapping to the last frame when you're playing in reverse toward a clip's start. Two further buttons hand you control over audio playback and clip display within the Viewer:

- Unmix: Switching Unmix on disables every transition, composited superimposition, and effect that blends two or more clips at once. With Unmix, you can size up a clip's look free of distraction any time an adjustment hinges on how the clip reads on its own, or any time changes depend on frames that a transition like a dissolve or a fade from black would otherwise bury. Once you want to view your grades alongside transitions and composites again, switch Unmix off.
- Mute: Click the speaker icon to switch audio playback on or off, or right-click the speaker icon and drag the slider to set the level.

### Navigating Using the Arrow Keys

The keyboard's Arrow Keys let you move through clips and the Timeline in a few different ways.
