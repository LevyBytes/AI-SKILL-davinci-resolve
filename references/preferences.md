# Preferences (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Preferences

This chapter walks through the assorted options on offer in the Fusion Preferences Window.

### Preferences Overview

A broad range of optional settings lives in the Preferences window, letting you shape Fusion’s behavior to fit your working environment more closely. You reach these settings through the Preferences window, opened by way of a menu sitting up near the interface’s top edge. Within DaVinci Resolve, opening the Fusion Preferences window is done in one of these ways:

- On macOS, switch to the Fusion page and choose Fusion > Fusion Settings.
- On Windows, switch to the Fusion page and choose Fusion > Fusion Settings.
- On Linux, switch to the Fusion page and choose Fusion > Fusion Settings. Within Fusion Studio, opening the Fusion Preferences window is done in one of these ways:
- On macOS, choose Fusion Studio > Preferences.
- On Windows, choose File > Preferences.
- On Linux, choose File > Preferences.

The Preferences window includes composition settings.

### Global and Composition Preferences

A category sidebar runs down the left of the Preferences window, with the settings panel filling the right. Fusion Studio carries two tiers of preferences: Global and Composition. On the Fusion page in DaVinci Resolve there is only one Global preference, and it governs every project, whether new or already made. The Global preferences hold options tied to Fusion’s overall behavior together with the defaults for each new composition. In Fusion Studio, the Composition preferences can further tweak whichever composition is currently open without disturbing the Global preferences or any other composition that happens to be open yet not on display.

### Categories of Preferences

The Global preferences claim the very first entry in the Preferences sidebar. Clicking the Global and Default Settings disclosure arrow opens up the sections that follow.

Fusion Studio Global and Default settings

### 3D View

The 3D View preferences hand you control over a range of 3D Viewer parameters, among them grids, the starting ambient lighting arrangement, plus Stereoscopic views. AVI (Windows Fusion Studio Only) The AVI preferences establish the default compression options applied as a Saver node writes out AVI files. You can override these on a case-by-case basis through the Format tab in the Saver’s Inspector.

### Defaults

The Defaults preferences let you settle the default behavior for a spread of choices, among them animation, the global range, how timecode is shown, and the automatic merging of tools.

### Flow

A good number of the options living in the Node Editor’s contextual menu are also adjustable through the Flow preferences, including the settings for Tile picture, the Navigator, and pipe style.

### Frame Format

The Frame Format preferences let you build new frame formats and also pick the default image height and width when you add new creator tools like Background and Text+. You set the playback frame rate here too.

### General

The General preferences gather options for everyday operation, such as auto save and the gamma settings for color controls. GPU (Fusion Studio Only) The GPU preferences carry options for picking specific GPU acceleration methods according to your computer platform and hardware. They are also used for switching on caching and for debugging GPU devices and tools. Layout (Fusion Studio Only) The Layout preferences let you save the precise arrangement of Fusion’s windows. Loader (Fusion Studio Only) The Loader preferences are where the default Loader’s depth plus its aspect ratio get their options, and where you spell out the local and network LoaderCache settings. Memory (Fusion Studio Only) The Memory preferences configure memory management for multi-frame and simultaneous branch rendering. Network (Fusion Studio Only) The Network rendering preferences set up options like picking a render master, email notification, and whether the machine may act as a render slave.

### Path Map

The Path Map preferences establish the virtual file path names that Loaders and Savers draw on, plus the folders Fusion consults to find comps, macros, scripts, tool settings, disk caches, and the rest. Preview (Fusion Studio Only) The Preview preferences are the place to establish the options for Preview creation along with playback. QuickTime (macOS Fusion Studio Only) Here is where the QuickTime codec used for rendering gets preset.

### Script

The Script preferences include a field for the passwords that run scripts externally, the programs used to edit scripts, and the default Python version to apply.

### Spline Editor

The Spline Editor preferences let you set a range of spline options covering Autosnap behavior, handles, markers, and more.

### Splines

The Splines preference holds options for handling and smoothing animation splines, Tracker path defaults, onion-skinning, roto assist, and more.

### Timeline

The Timeline preferences are where you build and edit Timeline/Spline filters and set the default options for the Keyframes Editor.

### Tweaks

The Tweaks preferences handle assorted settings that change behavior when frames load over the network and during queue/network rendering.

### User Interface

These preferences govern how the user interface window looks and how the Inspector is shown. Video Monitoring (Fusion Studio Only) The Video Monitoring preferences are the spot to configure Blackmagic video display hardware so monitoring runs on an HD, Ultra HD, or DCI 4K display.

### View

The View preferences span the viewer settings, reaching the default control colors, the Z-depth channel viewing ranges, default LUTs, the padding applied for fit, zoom, and the rest.

### VR Headsets

The VR Headsets preferences let you configure whatever Virtual Reality headsets are attached, taking in the way stereo and 3D scenes get viewed. Bins (Fusion Studio Only) Three panels make up the Bins preferences: a Security panel for assigning users plus passwords that serve the local bins; a Servers panel for choosing which remote Bin servers connect; and a Settings panel devoted to stamp rendering.

### Import

The Import settings carry options for EDL Import that shape how flows are built from the data in an EDL.

### Preferences In Depth

Each category holds a deep set of controls for tuning Fusion so it fits your working environment better. The preferences span both software and hardware options that touch every newly created comp. The section below explains every option found across the preferences categories.

### 3D View

The 3D View preferences hold settings for assorted defaults in the 3D Viewers, taking in grids, the default ambient light setup, and Stereoscopic views.

### The 3D View preferences

### Grid

The Grid section of the 3D View preferences sets up the way the grid in 3D Viewers is drawn.

- Grid Antialiasing: Certain graphics hardware and drivers cannot handle antialiased grid lines, which causes them to sort incorrectly in the 3D Viewer. Clearing this checkbox switches off antialiasing of the grid lines. To shut the grid off entirely, right-click in a 3D Viewer and choose 3D Options > Grid.
- Size: Raising the Size value adds more grid lines. Fusion does not pin down the units used for the spacing between grid lines. A “unit” is whatever you decide it is.
- Scale: Tuning the overall scaling factor for the grid helps, for instance, when the grid area looks too small next to the size of your geometry.

### Perspective Views

The Perspective Views section governs how the perspective view looks in both a normal and a stereoscopic project.

- Near Plane/Far Plane: These values fix the closest and farthest distance any object may reach toward or away from the camera before it gets clipped. The minimum setting is 0.05. Putting Near Plane too low and Far Plane too far costs you depth precision in the viewer.
- Eye Separation/Convergence/Stereo Mode: This cluster of settings establishes the defaults applied once stereo is switched on in the 3D Viewer.

### Orthographic Views

In a manner that echoes the Perspective Views, the Orthographic Views section — covering the front, top, right, and left views — pins down how near or far an object may travel relative to the viewer before clipping kicks in.

### Fit to View

The Fit to View section has two value fields governing how much empty space surrounds objects in the viewer when the F key is pressed.

- Fit Selection: Fit Selection governs the empty margin left once one or more objects are picked and you press the F key.
- Fit All: Fit All governs the empty margin left when F is pressed with nothing picked.

### Default Lights

These three settings govern the default light setup in the 3D Viewer. The default ambient light comes into play once lighting is switched on and you have added no light to the scene. The directional light travels with the camera, so when the directional light is set to “upper left,” the light seems to arrive from the upper-left side of the image/camera.

### AVI

The AVI preference shows up only in Fusion Studio on Windows. It sets up the default AVI codec settings whenever you pick AVI as the rendering file format in the Saver node.

- Compressor: This drop-down menu lists the AVI codecs your computer offers. Fusion checks each codec as the application starts, so some may be missing if those checks find them unfit for use within Fusion.
- Quality: This slider sets how much compression the codec applies. Higher values yield cleaner images but bigger files. Not every codec honors the Quality setting.
- Key Frame Every X Frames: When ticked, the codec lays down keyframes at the interval you set. Keyframes are not compressed against earlier frames, which makes them faster to seek within the finished movie. Not every codec honors the keyframe setting.
- Limit Data Rate To X KB/Second: When ticked, the rendered file’s data rates are capped at the amount you give. Not every codec honors this option. Enter, in kilobytes (kB) per second, the data rate that caps the AVI, where applicable. This control leaves the file alone unless the Limit Data Rate To option is selected.

### Defaults

What you choose here shapes Fusion’s behavior as fresh tools land in the Node Editor and as parameters get animated.

### The Defaults preferences

### Default Animate

The Default Animate section lets you change which kind of modifier attaches to a parameter once the Animate option is picked from its contextual menu. The default option is Nothing, which reaches for a Bézier spline when animating numeric parameters and turns to a path modifier where positional controls are concerned.

- Number With and Point With: These drop-down lists let you pick a different modifier as the new default. For instance, change the default used to animate position by setting Point with the drop-down menu to XY Path. The choices in this menu come from installed modifiers valid for that parameter type. They take in third-party plug-in modifiers along with the native modifiers that ship with Fusion.

### Auto Tools

The Auto Tools section decides which tools get added automatically for the most common Background tool operations and Merge operations.

- Background: When set to None, a standard Background tool is used; the drop-down menu, however, lets you pick from an assortment of tools, including 2D and 3D tools, to shape the operation to your workflow.
- Merge: When set to None, nothing occurs. When set to Merge, joining the outputs of two tools or dragging several clips onto the Node Editor uses a standard Merge. Other valid choices here are Anaglyph, Channel Booleans, and Dissolve.
- Use Merge Only When Connecting Outputs Directly: With this option active, Merges are not added automatically when you drag several clips from the Finder or Windows Explorer onto the Flow area.

### Global Range

Through the Start and End fields, you define the Global Start and End frames applied when new compositions are created.

### Time Code

You use this option to decide whether new compositions default to showing SMPTE Time Code or frames (Feet + Frames) for representing time.

### Flow

A good number of the options living in the Node Editor’s contextual menu — among them the settings for Tile Picture, the Navigator, and Pipe Style — are gathered in this category.

### The Flow preferences

### Force

The Force section can set the default so that certain tool tiles in the Node Editor display pictures rather than plain tiles. The Active checkbox turns pictures on for the actively selected tool, the All checkbox enables pictures for every tile, and the Source and Mask checkbox enables tile pictures only for Source and Mask tools.

When All is enabled, the picture shown is either a thumbnail of the image the tool rendered if the tool has rendered, or — when the Show Thumbnails option is off — the tool’s default icon. Concatenated transforms also show a default icon.

- Show Modes/Options: Switching this on places icons on the tool tile that depict various states, like Disk Caching or Locked.
- Show Thumbnails: With this checkbox ticked, tool tiles set to show tile pictures display the rendered output of the tool. With the checkbox cleared, the tool’s default icon is used instead.

### Options

The Options section gathers several settings that control or assist the layout and alignment of tools in the Node Editor.

- Arrange to Grid: This switches on a new node tree’s Snap to Grid option so the tool layout lines up with the grid marks in the flow.
- Arrange to Connected: A tool snaps onto the vertical or horizontal position held by whichever other tools it links with.
- Auto Arrange: This option lets the Node Editor shift tool positions as needed to clear space when inserting new tools or auto-merging layers.
- Show Grid: This switches the Node Editor’s background grid display on or off.
- Auto Remove Routers: Pipe Routers, or “elbow nodes,” in the Node Editor count as

“orphaned” once the tools wired to either their input or output are deleted. With this option on, Orphaned Routers are deleted automatically.

- Pipes Always Visible: When on, the lines linking one tool to another are rendered on top of the tool tiles themselves.
- Keep Tile Picture Aspect: Switching this on forces tool tile thumbnail pictures to hold the aspect of the original image in the thumbnail.
- Full Tile Render Indicators: Ticking this checkbox makes the whole tile change color while it is processing. That can make it easier to spot which tools are processing in a large composition. The coloring itself acts as a progress bar, signaling how near slower tools are to finishing.
- Show Instance Links: This option picks whether Instance tools show links, drawn as green lines, between Instance tools.
- Navigator: The Navigator is a small square overview of the whole composition. It lets you jump quickly to different parts of a node tree while zoomed in. The checkboxes in this section decide when, if ever, the Navigator appears.

On: The Navigator stays visible at all times. Off: The Navigator stays hidden at all times. Auto: The Navigator appears only when the Node Editor’s contents spill beyond the currently visible Work area.

- Pipe Style: This drop-down menu picks the method used to draw connections between tools. The Direct method runs a straight line between tools, while Orthogonal uses horizontal and vertical lines.
- Build Direction: While auto-building or laying out a node tree, Build Direction decides whether tools are arranged horizontally or vertically.
- Scale: The Scale menu lets you pick the default zoom level of the Node Editor whenever a new composition is created.

### Pipe Grab Distance

The Pipe Grab Distance slider lets you choose how near the pointer must come (in pixels) to a connection line in the node tree to select it.

### Link Grab Distance

The Link Grab Distance slider lets you choose how near the pointer must come (in pixels) before a node’s knot makes or breaks a connection. At 0 pixels you must land right on the knot, whereas a top setting of 20 lets you sit 20 pixels away from a knot and still connect to it.

### Group Opacity

This slider governs the opacity of an expanded group’s background in the Node Editor.

### Frame Format

The Frame Format preferences let you pick the resolution and frame rate for the nodes that generate images, such as Background, fast noise, and Text+. On top of that they fix the color bit depth applied to final renders, to previews, and to interactive updates shown in the viewer. Those color bit depth choices take effect in Fusion Studio alone. Rendering in DaVinci Resolve always uses 32-bit float.

### The Frame Format preferences

### Default Format

This drop-down menu lets you pick the default resolution for Generator tools from a list of presets. It is only a default, and a node’s Inspector can override it by way of its Resolution settings. Any of the default settings is changed through the Edit boxes. To make a new setting, press the New button, enter a name in the dialog box that appears, and enter the parameters.

### Settings

The Settings section spells out the format chosen in the Default Format menu. You can change an existing format or build a new one.

- Width/Height: When building a new format for the menu or changing an existing menu item, you give the format’s Width or Height in pixels through these fields.
- Frame Rate: Enter or view the frames per second the format plays. From the Saver tool, this becomes the default Frame Rate for previews as well as final renders. The comp’s own playback is fixed by it too, along with the frame-to-time-code conversion for tools that take temporal inputs.
- Has Fields: With this checkbox on, any Creator or Loader tool added to the Node Editor will run in Fields process mode.
- Film Size: This field defines how many frames sit in one foot of film. The value drives the display of time code in Feet + Frames mode.
- Aspect Ratio: The chosen frame format’s pixel aspect ratio is established through these two fields.
- Guide 1: The four fields for Guide 1 set the left, top, right, and bottom guide positions for

the custom guides in the viewer. Repositioning a guide means typing a value somewhere in the 0 to 1 range. At the bottom-left corner the value is forever 0/0, and at the top-right corner it is forever 1/1. Should the entered value’s aspect fail to agree with the frame format defined by the Width and Height parameters, a further guide turns up onscreen. The dotted line marks the image aspect centered about Guide 1’s Center values.

- Guide 2: This setting fixes the image aspect ratio against the whole frame format width and height. Values above 1 shrink the height relative to the width. Values below 1 grow the height relative to the width.
- New: The New button is how a fresh default setting joins the drop-down menu. After the button is clicked, the dialog box that pops up is where you name that setting.
- Copy: Pressing the Copy button duplicates whatever setting is current, giving you a fresh one to customize.
- Delete: Pressing the Delete button takes whatever setting is current off the default drop-down list.

### Color Depth

Within the Color Depth section, its three menus let you select the color mode that handles preview renders, interactive renders, and full (final) renders. Working an image at 8-bit gives you the lowest color depth, seldom adequate for final work these days, yet perfectly fine for quick previews. 16-bit color brings far greater color fidelity at the cost of more system resources. Both 16-bit and 32-bit float per channel consume still more system resources and are the best fit for digital film and HDR rendered images. By default, the composition pays these options no mind until a Loader or Creator tool has its Color Depth control set to Default.

### General

The sections gathered under the General preferences bear on how the Inspector behaves and on a few additional user interface elements besides.

### Usability

Under Usability sit a range of project, Node Editor, and user interface settings that, according to how you work, can smooth out using the application.

- Auto Clip Browse: With this checkbox on, the File Browser appears automatically when a new Loader or Saver is added to the Node Editor.
- New Comp on Startup: When ticked, a new, empty project is created each time Fusion Studio launches. This has no bearing on DaVinci Resolve’s Fusion page.

### The General preferences

- Summarize Load Errors: While loading node trees, or “comps,” that hold unknown tools (for example, comps built on other computers with plugins absent from the current machine), the missing tools are summarized in the console instead of a dialog appearing for every missing tool.
- Save Compressed Comps: This option lets node trees be saved compressed rather than as ASCII-based text files. Compressed node trees occupy less disk space, though they may take a moment longer to load. Node trees holding complex spline animation and many paint strokes can swell into tens of megabytes with this option off. Compressed comps, however, cannot be edited in a text editor unless saved again uncompressed.
- Show Video I/O Splash: This toggles whether the Splash image appears over the video display hardware. It applies only to Fusion Studio.
- Use Simplified Copy Names: This option cuts down on the underscores that appear in tool names when copying.
- Show Render Settings: With this checkbox ticked, the Fusion Render Settings dialog appears each time a render begins in Fusion Studio. Holding Shift as you start a render stops the dialog from appearing for that session, applying whatever settings were used on the last render. Switching this option off reverses that behavior.
- Mouse Wheel Affects the Window Under the Pointer: As a rule, a turn of the mouse wheel or a trackpad swipe affects whichever window is active. With this option on, the affected window is the one lying under the cursor, so there is no need to click into a window beforehand to activate it.
- Frames Start From: This fixes which frame number begins the clip times in the Loader and its Clip list.
- Show Color As: This setting pins down the numeric scale that stands in for colors. Your options are Normalized (0 to 1), 8-bit (0 to 255), and 16-bit (0 to 65,535). The image’s real processing and quality stay untouched, yet it can ease the mental arithmetic you sometimes do when working out adjustments.

### Auto Save

The Auto Save settings take effect in Fusion Studio alone. For auto backups on the Fusion page within DaVinci Resolve, turn instead to the DaVinci Resolve Project Load and Save Preferences. With Auto Save switched on in Fusion Studio, comps write themselves to a backup file at steady intervals that the Delay setting fixes. Should a backup file turn up as you go to open the comp, you are offered the choice between loading the backup and loading the original. When the backup comp is opened from the location named in the Path Map preference, saving that backup writes over the original file. When the backup file is shut without saving, it gets deleted while the original stays intact.

- Save Before Render: When on, the comp is saved automatically before a preview or final render begins.
- Delay: This preference sets the interval between Auto Saves. The interval uses mm:ss notation, so entering 10 makes an Auto Save happen every 10 seconds, whereas entering 10:00 makes an Auto Save every 10 minutes.

### Proxy

- Update All, Selective, No Update: The Update mode button sits above the toolbar. This preference lets you pick which mode fresh comps adopt by default. Ordinarily that default is Selective, which renders just the tools required to put the images up in the Display view. All renders every tool in the composition, whereas None blocks all rendering.
- Standard and Auto: These sliders set the default ratio used to create proxies once the Proxy and Auto Proxy modes are switched on. These settings leave the final render quality alone.
