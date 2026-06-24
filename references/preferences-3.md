# Preferences (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Compressor: This drop-down menu lists the QuickTime codecs your computer makes available. At startup Fusion checks each codec, and so a codec may be left out when those checks find it unfit for use inside Fusion.
- Quality: This slider governs how much compression the codec applies. Raise it and images grow clearer while files grow bigger. The Quality setting isn’t honored by every codec.
- Key Frame Every X Frames: Ticked, this has the codec lay down key frames at the interval you set. Since key frames aren’t compressed against earlier frames, seeking to them in the finished movie is faster. The key frame setting isn’t honored by every codec.
- Limit Data Rate To X KB/Second: Ticked, this caps the rendered file’s data rates at the amount you name. Not every codec supports this option. Where it applies, enter the data rate that limits the QuickTime in kilobytes (kB) per second. Leave the Limit Data Rate To option unticked and this control does nothing.

### Script

The Scripting preferences carry a field for the passwords used to run scripts from the command line, plus the applications to call on when editing scripts.

### The Script preferences

### Login

Running scripts beyond the Fusion application comes with three login options.

- No Login Required to Execute Script: Switched on, scripts launched from the command line — or scripts that try to drive remote copies of Fusion — can run without logging in to the workstation.
- Specify Custom Login: With a username and password set, Fusion turns away incoming external script commands (those from FusionScript, say) until the Script logs in to the workstation first. This bears only on scripts launched from the command line, or scripts that try to drive remote copies of Fusion. Scripts launched from within the interface need no login no matter how this is set. For more information, see the Scripting documentation.
- Use Windows Login Validation: When you run Fusion on Windows, switching this on checks the user name and password (also known as credentials) against the operating system before the script runs.

### Options

- Script Editor: Reach for this preference to pick an external editor for scripts. It comes into play when you choose Scripts > Edit.

### Python Version

- A pair of options sit here for picking which version of Python you intend to use for your scripts.

### Spline Editor

The Spline Editor preferences let you dial in various spline options covering Autosnap behavior, handles, markers, and beyond. This touches only splines shown in the Spline Editor, not splines made in the viewer with the polygon tool or paths.

### The Spine Editor preferences

### Spline Editor Options

These settings steer how splines behave in the Spline Editor, along with how the graph area looks.

- Independent Handles: Switch this on and the In or Out direction handle on freshly made key frames can move on its own, leaving the other untouched. You’ll also find this option through the Options submenu when right-clicking in the Spline Editor graph.
- Follow Active: The Spline Editor centers on whichever tool is currently active. You’ll also find this option through the Options submenu when right-clicking in the Spline Editor graph.
- Show Key Markers: Small colored triangles appear along the top of the Spline Editor Time Ruler to mark key frames on active splines. Each triangle’s color matches its spline’s color. You’ll also find this option through the Show submenu when right-clicking in the Spline Editor graph.
- Show Tips: Switches the display of tooltips on or off. You’ll also find this option through the Show submenu when right-clicking in the Spline Editor graph.
- Autosnap Points: As you move points in the Spline Editor, they’ll either snap to the fields or frames or stay free to move. You’ll also find this option through the Options submenu when right-clicking in the Spline Editor graph.
- Guides: As you move points in the Spline Editor, they’ll snap to guides too. You’ll also find this option through the Options submenu when right-clicking in the Spline Editor graph.
- Autosnap Guides: As you move or create guides, they’ll either snap to the fields or frames or stay free to move. You’ll also find this option through the Options submenu when right-clicking in the Spline Editor graph.
- Autoscale: Holds the Spline Editor scales steady as the graph’s editable spline content changes. This scale is likewise reachable through the Options submenu when right-clicking in the Spline Editor graph.
- Scroll: Scrolls both horizontally and vertically to bring all, or nearly all, of the spline points into view. You’ll also find this option through the Scale submenu when right-clicking in the Spline Editor graph.
- Fit: Zooms so every point fits within the spline graph, where needed. You’ll also find this option through the Scale submenu when right-clicking in the Spline Editor graph.

### LUT View Options

These settings let you steer how the LUT view is shown.

- Independent Handles: Switch this on and the In or Out direction handle on freshly made key frames can move on its own, leaving the other untouched.
- Show Key Markers: Small colored triangles appear along the top of the Spline Editor Time Ruler to mark key frames on active splines. Each triangle’s color matches its spline’s color.
- Show Tips: Switches the display of tooltips on or off.

### Splines

You’ll find options for handling and smoothing animation splines, tracker path defaults, and rotoscoping over in the Splines preferences.

### The Splines preferences

- Autosmooth: Smooths any freshly made points or key frames automatically on whichever splines are picked in this section. You can opt to auto-smooth animation splines, B-Splines, polyline matte shapes, LUTs, paths, and meshes.
- B-Spline Modifier Degree: This setting fixes how strongly the line segments sway the resulting curvature when B-Splines drive animation. Cubic B-Splines trace a segment through two control points between the anchor points, while Quadratic B-Splines trace a segment through one control point between the anchor points.
- B-Spline Polyline Degree: This setting works like the one above but applies to B-Splines used for masks.
- Tracker Path Points Visibility: This setting fixes how visible the control points on tracker paths are. You can show them, hide them, or have them appear when your cursor hovers over the path, which is the default behavior.
- Tracker Path: By default the tracker makes Bézier-style spline paths. Two further options in this setting let you pick B-Spline or XY Spline paths instead.
- Polyline Edit Mode on Done: This setting fixes what state the Polyline tool lands in once you finish drawing a polyline. It can be set either to adjust the spline’s existing control points or to adjust and add new control points to the spline.
- Onion Skinning: The Onion Skinning settings fix how many frames show while you rotoscope, letting you preview and compare a span of frames. You can also set whether the preview draws frames only from before the current frame, after the current frame, or split across the two.

### Timeline

The Timeline preferences are where you build and edit Keyframes Editor/Spline Editor filters and set the default options for the Keyframes Editor.

### The Timeline preferences

### Filter/Filter to Use

The Filter menu fills the hierarchy area beneath it with that setting and lets you edit the filters. The Filter to Use menu picks the default filter setting found in the Keyframes Editor Options menu.

### Settings for Filters

This area serves to build a new filter and spell out its settings. Begin by clicking the New button and typing the new Filter’s name. Then tick any of the tools you want the filter to hold. Only ticked tools turn up in the Keyframes Editor or Spline Editor once the filter is picked. You can also duplicate the filter with the Copy button or drop a filter from the list by clicking the Delete button.

### Timeline Options

The Timeline Options set which options in the Keyframe Editor start out switched on. A run of checkboxes maps to buttons in the Timeline, letting you fix the states of those buttons at the moment a new comp is built.

To dig further into the Keyframes Editor functions, turn to Chapter 71, “Animating in Fusion’s Keyframes Editor,” within the DaVinci Resolve Reference Manual, or to Chapter 9 in the Fusion Reference Manual.

- Autosnap Points: As you move points in the Keyframes Editor, they’ll snap to the fields or to the frames, or else stay free to move.
- Guides: As you move points in the Keyframes Editor, the point will snap to the guides set down in the Timeline graph.
- Autosnap Guides: As you move or create guides, they’ll snap to the fields or to the frames, or else stay free to move.
- Autoscale: Holds the Timeline scales steady while you change the graph’s editable spline content. Set to scroll, the Timeline scrolls horizontally and vertically to bring all, or nearly all, of the spline points into view as you change the graph’s editable spline content. Set to Fit, the Timeline zooms so every point fits within the graph, where needed.
- Tools Display Mode: This menu fixes the default sort order of the tools shown in the Keyframes Editor. You can change that default by way of the Sort order menu at the upper right of the Keyframes Editor.

### Tweaks

The Tweaks preferences hold a cluster of settings for fine-tuning Network rendering in Fusion Studio along with graphics hardware behavior.

### Network

The Network section serves to steer and watch the health of communication packets over TCP/IP while rendering across a network in Fusion Studio.

- Maximum Missed Heartbeats: This setting fixes how many times the network can be checked before communication with a Render node is cut off.
- Heartbeat Interval: This sets how much time passes between network checks.
- Load Composition Timeout: This timeout option fixes how long the Render Manger will hold on

waiting for a composition to load before it moves to another task.

- Last Slave Restart Timeout: This timeout option fixes how long the Render Manager will

hold on waiting for a render salve to answer before it turns to another render slave.

### The Tweaks preferences

### File I/O

The File I/O options serve to steer performance as frames or large media files are read off both direct and network-attached storage.

- I/O Canceling: This option switches on an operating-system feature that lets queued operations be canceled once the function that asked for them stops. It can sharpen responsiveness, above all while loading large images across a network. Switching it on will specifically sway performance while loading and reaching formats that do a great deal of seeking, such as the TIFF format. Since this option hasn’t been tested across every hardware and OS configuration, it’s wise to switch it on only once you’ve thoroughly tested your hardware and OS configuration with drive loads from both local disks and network shares.
- Enable Direct Reads: Ticking this checkbox brings a more efficient method to bear when loading a large chunk of contiguous data into memory, since it cuts down I/O operations. Not every operating system carries this ability, so it may bring on unknown behavior.
- Read Ahead Buffers: This slider fixes the count of 64K buffers devoted to reading ahead during a file I/O operation. A larger count makes pulling frames off disk more efficient, yet leaves things less responsive to changes that call for interactive disk access.

### Area Sampling

The Area Sampling options let you fine-tune RAM usage on Render nodes by trading speed for lower RAM demands.

- Automatic Memory Usage: This checkbox fixes how area sampling draws on the memory at hand. Area sampling comes into play for Merges and Transforms. With the checkbox ticked (default), Fusion gauges the RAM at hand while processing the tool and works out the right trade-off between speed and memory. Where less RAM is at hand, Fusion runs at a higher proxy level internally and takes longer to render. The image quality isn’t hurt in any way — only the time it takes to render. In node trees handling images bigger than 4K, overriding the automatic scaling and pinning the proxy scale by hand can be worthwhile. Doing so can hold RAM in reserve for later operations.
- Pre-Calc Proxy Level: Clearing the Automatic Memory checkbox switches on the Pre-Calc Proxy Scale slider. Higher values draw on less RAM but stretch render times considerably.

### Open GL

This section steers how Fusion puts your graphics card to work when compositing in 3D with the Renderer 3D node. Most settings can stay as they are, but because OpenGL hardware ranges so widely in capability and different driver revisions can now and then bring bugs, these tweaks can come in handy when you hit unwanted behavior.

- Disable View LUT Shaders: OpenGL shaders can frequently speed up View LUTs dramatically, though this can occasionally carry small trade-offs in accuracy. This setting forces Fusion to process LUTs at full accuracy on the CPU instead. Give it a try when View LUTs don’t seem to land the result you want.
- Use Float16 Textures: When your graphics hardware handles 16-bit floating-point textures, switching this on has int16 and float32 images sent up to the viewer as float16 in their place, which can lift playback performance.
- Texture Depth: Fixes the depth at which images are uploaded to the viewer.

Auto: The Auto option (recommended) lets Fusion strike the best balance of performance and capability. int8: Much like the Use Float16 Textures switch, this option can send images up to the Display View as int8; that route can run faster yet leaves a narrower range for View LUT correction. Native: With the Native option, images go up at whatever their native depth is, and so nothing is converted.

- Image Overlay: The Image Overlay is a viewer control paired with Merge and Transform tools to show a translucent overlay of the transformed image. It can help you picture the transformation when it falls outside the image bounds, though it may cost performance on selecting the tool if cache memory runs low. Three settings are on offer: None, Outside, and All.

None: This setting never shows the translucent overlay or controls, which can cut the need for background renders and, in some cases, speed up the display. Outside: This shows only those parts of the control that fall outside the image bounds, which can ease visual confusion. All: Shows every overlay of every selected tool.

- Smooth Resize: This setting can switch off the viewer’s Smooth Resize behavior while showing floating-point images. Some older graphics cards can’t filter floating-point textures or may be very slow at it. When Smooth Resize doesn’t sit well with float images, try setting this to flt16 or int.
- Auto Detect Graphics Memory (MB): Keeping Fusion open beside other OpenGL programs like 3D animation software can leave graphics memory short. In such cases you can lower by hand how much memory Fusion may use on the card. Setting this too low or too high may bring on performance trouble or data loss.
- Use 10-10-10-2 Framebuffer: Where both your graphics hardware and monitor are capable of 30-bit color — Nvidia Quadro/AMD Radeon Pro, plus certain Nvidia GeForce/AMD Radeon cards — this setting draws viewers at 10 bits per primary accuracy in place of 8 bits. Banding drops sharply while showing 3D renders or images deeper than 8-bit.

### User Interface

The User Interface preferences set how the user interface window looks and how the Inspector is shown.

### The User Interface preferences

### Appearance

Switched on, the Use Gray Background Interface checkbox shifts the background color across Fusion’s panels to a lighter, more neutral gray.

### Controls

This cluster of checkboxes governs how the controls in the Inspector are shown.

- Auto Control Open: Switched off, only the header of the selected node shows in the Inspector. You then double-click the header to bring up the parameters. Switched on, the parameters come up automatically once the node is selected.
- Auto Control Hide: Switched on, only the parameters for the currently active tool (red outline) are made visible. Otherwise every tool header stays visible and is shown according to the Auto Control Open setting.
- Auto Control Close Tools: Switched on, only the active (red outlined) tool in the Node Editor has its controls shown. Any earlier active node’s tools get closed in the Inspector. Switched off, any number of tools may be opened to show parameters at once. This setting does nothing when the Auto Control Hide checkbox is ticked.
- Auto Control Close Modifiers: Switched on, only one modifier’s parameters show for the active node. Any extra modifiers on the active node show only their header.
- Auto Control Advance: With the Auto Control Advanced checkbox ticked, the Tab key and Return/Enter key push the keyboard focus on to the next edit box within the Inspector. Switched off, Return/Enter accepts the value you entered, yet the keyboard focus holds where it is, inside that control’s edit box. You can still rely on the Tab key to push the keyboard focus along.
- Show Controls for Selected: With this option switched off, only the active tool’s parameters show in the Inspector. By default it’s switched on, showing controls for the active tool as well as every selected tool.
- Combined Color Wheel: While the Color Corrector tool shows in the Inspector, ticking this checkbox brings up one color wheel with buttons to flip between the master, shadow, midtones, and highlight channels. Otherwise four color wheels show in the Inspector.
- Gamma Aware Color Controls: This setting adjusts color correction nodes whenever a non-color managed project holds Rec. 709 images. Rec. 709 images read correctly on the computer monitor because monitors carry a built-in gamma adjustment. While working in the Rec. 709 color space with no color management, switching on Gamma Aware color strips the gamma, applies the color correction as though it were linear, and then puts the gamma back. Where Rec. 709 images are concerned, switch the Gamma Aware setting on and key in a Gamma value of 2.4. Within a color managed linear project, leave this at Off or a value of 1.0. When mixed color spaces are in play, Fusion reads the image’s metadata and sets the Aware gamma value from whatever metadata is on hand.
- Grab Distance: This slider runs from 1 to 10 and defaults to 5. It marks the active area around the mouse pointer and can be changed when you struggle to select points for adjustment in paths and spline curves. Smaller values demand a more precise selection with the mouse pointer.

### Touch Scrolling and Mouse Wheel

This cluster of settings lets you set which keyboard modifiers, if any, are needed to pan or zoom a panel while using a trackpad or middle mouse wheel.

### Video Monitoring

This setting shows up only in Fusion Studio. Control over video hardware for the Fusion Page is handled in the DaVinci Resolve preferences. The Video Monitoring preferences serve to configure Blackmagic Design capture and playback gear — DeckLink PCIe cards and UltraStudio i/O units among them.

### The Video Monitoring preferences

### Video Output

This cluster of drop-down menus lets you choose your installed video I/O device type along with the output resolution and the pixel format. None of these settings touch your rendered output; they bear only on your display hardware. The Output HDR over HDMI settings serve to send the needed metadata when high dynamic range signals go out over HMDI 2.0a so an HDR capable video display decodes them correctly. The Auto setting reads the image’s values and outputs HDR. This leaves non HDR images alone. The Always setting keeps HDR forced on at all times. That can come in handy while checking non HDR and HDR grades. Once Auto or Always is picked, the “nit” level (slang for cd/m2) is yours to set, matched to whatever peak luminance level your HDMI connected HDR display can manage.

### Stereo Mode

This cluster of settings sets up the output hardware for showing stereo 3D content.

- Mono will output a single non stereo eye.
- Auto will detect which method with which the stereo images are stacked.
- Reach for the Vstack option when your stereo images sit one above the other — left up top, right beneath.
- Reach for the Hstack option when your stereo images sit beside each other — left then right.

The Swap eyes checkbox will swap the eyes if stereo is reversed.

### View

The View preferences serve to manage settings and default controls for viewers.

### The View preferences

### Saved View Settings

The area atop the view preferences lists the saved settings you’ve created from the viewer’s contextual menu. You can lean on the Rename and Delete buttons to manage whichever entries you’ve picked in the list. To dig further into the viewer and its contextual menu, turn to Chapter 69, “Using Viewers.” within the DaVinci Resolve Reference Manual, or to Chapter 7 in the Fusion Reference Manual.

### Settings for View

Every viewer carries its own preferences. The Settings for View drop-down menu serves to pick the viewer you want to set up.

### Control Colors

The Control Colors setting lets you fix the color of the active/inactive onscreen controls.

### Color Picking Area Size

You can use these width/height controls to fix how many pixels get sampled while using the Color Picker in the viewers.

### Displayed Depth Range

The Displayed Depth Range setting steers the view normalization of the Z-Channel.

### Fit Margin

The Fit Margin setting fixes how much padding stays around the frame once the Fit button is pressed or Fit is picked from the viewer’s contextual menu.

### Display LUT Plugins

This list shows the display LUTs on hand and switches the picked one on as the default.

### VR Headsets

The VR Headsets preferences let you set up any connected Virtual Reality headsets, including how stereo and 3D scenes get viewed.

### Headset Options

The Headset options serve to pick the type of VR headset you’re using to view the composite, along with the video layout of the 360° view.

### API

- Disabled: Disabled switches off and hides every use of headsets.
- Auto: Auto will detect which headset is plugged in.
- Oculus: Oculus will point the VR output at the Oculus headset.
- OpenVR: OpenVR will back a number of VR headsets like the HTC Vive.

The VR Headsets preferences 360° Video Format

- Auto: Auto reads the incoming image layout off the metadata together with the image frame aspect.
- VCross and HCross: With VCross and HCross, a cube’s six square faces sit in a cross — vertical or horizontal — the forward view holding the cross’s center, within a 3:4 or 4:3 image.
- VStrip and HStrip: With VStrip and HStrip, a cube’s six square faces run vertically or horizontally along a line, in the order Left, Right, Up, Down, Back, Front (+X, -X, +Y, -Y, +Z, -Z), within a 1:6 or 6:1 image.
- LatLong: LatLong amounts to one 2:1 image in equirectangular mapping.
- Enable Mirror Window: Enable Mirror Window brings up a window that mirrors the headset user’s live view.

### Stereo

Much like the normal viewer options for stereo 3D comps, these preferences steer how a stereo 3D comp shows in a VR headset.

### Mode

- Mono: Mono puts out one non stereo eye.
- Auto: Auto works out the way the stereo images have been stacked.
- Vstack: With Vstack, the stereo images stack one above the other — left up top, right beneath.
- Hstack: With Hstack, the stereo images stack side by side — left and right.
- Swap Eyes: Swap eyes flips the eyes whenever stereo comes through reversed.

### 3D
