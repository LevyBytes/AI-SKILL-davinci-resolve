# Exploring The Fusion Interface (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Spacebar: Switches forward playback on or off.
- JKL: The familiar JKL scheme works here too — press J to run backward, K to halt, and L to

play forward.

- Back Arrow: Steps backward by a single frame.
- Forward Arrow: Steps forward by a single frame.
- Shift-Back Arrow: Sends the playhead to the clip’s Global Start frame.
- Shift-Forward Arrow: Sends the playhead to the clip’s Global End frame.
- Command-Back Arrow: Jumps to the Render Range In point.
- Command-Forward Arrow: Jumps to the Render Range Out point.

### Real-Time Playback Not Guaranteed

A great many of the effects built on the Fusion page demand heavy processing, so smooth playback at the project’s full frame rate cannot be promised unless your composition has been cached beforehand (covered farther on).

### Frame Increment Options

A contextual menu appears when you right-click either the Play Reverse or the Play Forward button. Inside it you can assign a frame increment value, after which a keyboard shortcut will advance the playhead in either sub-frame or multi-frame steps. Stepping by several frames at once comes in handy while rotoscoping. Stepping by a fraction of a frame helps when rotoscoping or when reviewing interlaced frames one field at a time (0.5 of a frame).

To set the step size the playhead jumps by, right-click either the Play Forward or the Play Backward button.

### Looping Options

Toggling the Loop button turns playback looping on or off. Right-click the same button to pick which looping behavior is applied:

- Playback Loop: The playhead runs to the end of the Time Ruler and then restarts from the top.
- Ping-pong Loop: Once the playhead hits the end of the Time Ruler, playback reverses back toward the start of the Time Ruler, and from there it keeps bouncing back and forth.

### Render Range Fields

Use the pair of time fields on the left of the transport controls to adjust the Render Range. Either type values in frames or drag inside the fields to set the In and Out of the render range used for previews and caching.

### The Render Start and Render End time fields

### Audio Monitoring

When you play a composition on DaVinci Resolve’s Fusion page, the audio comes from the Edit or Cut page Timeline. The Audio toolbar button to the left of the transport controls lets you decide whether to listen to that audio or silence it. To help you time your animations, the audio waveforms show up in the Keyframes Editor. TIP: Any Timeline track whose Mute button is on will not be audible from within Fusion. In Fusion Studio, audio is brought in through the Loader node’s Audio tab. This audio support exists in Fusion Studio mainly as a scratch track, for lining up effects against audio and clip timing. As a rule, final renders are produced without audio. Audio plays back only when it has been loaded through a Loader node. To listen to the audio from a particular Loader node: right-click the Speaker icon and pick the file name holding the audio you wish to hear.

### Audio Toolbar Button

Acting as a toggle, the toolbar’s Audio button turns the clip’s audio playback on or mutes it. Right-clicking the same button also brings up a contextual menu, from which you can pick a MediaIn node on the Fusion page or, in Fusion Studio, an external WAV file to use for playback.

### The Current Time Field

Sitting at the right end of the transport controls, the Current Time field reports the frame number at the playhead, matching the frame currently shown in the viewer. Click and drag within it to scrub the playhead forward and backward. You may instead type time values into the field to advance the playhead by an exact amount. While defining ranges or typing frame numbers to reach a given frame, the values you enter may include sub-frame fractions. For example, a range could run from –145.6 to 451.75, or the playhead could sit at 115.22. This proves quite useful for animating parameters, since keyframes can land exactly where they belong instead of snapping to a whole-frame boundary, yielding more natural animation. Working in sub-frame time also lets you drive time remapping nodes — or simply scale keyframes in the Spline view — while keeping precision intact.

### The Fusion Page Viewer Quality and Proxy Options

Right-click anywhere inside the transport control area — except over the Play Forward/Play Reverse buttons — to switch Fusion quality controls on or off. From there you can either turn on high-quality playback and accept the longer processing it requires, or drop into one of several proxy modes that briefly reduce your composition’s display quality so the software keeps up while you work. None of these choices affect final output, which always renders at full quality. High Quality While assembling a composition, the speed at which you can work usually matters more than how the displayed image looks. The High Quality setting lets you choose between snappier interactivity and final render quality. With High Quality switched off, demanding, time‑consuming steps such as area sampling, anti-aliasing, and interpolation are bypassed so the viewer image renders sooner. Switching High Quality on forces a full-quality render to the viewer that matches exactly what final delivery produces. Motion Blur The Motion Blur button works globally. Switching Motion Blur off temporarily suspends motion blur across the whole composition, no matter which individual nodes have it turned on. Doing so can markedly accelerate viewer renders. Before this button does anything, motion blur has to be enabled on the individual nodes first. Proxy The Proxy setting is a draft mode meant to speed up processing as you build your composite. Switching Proxy on lowers the resolution of the images sent to the viewer, shortening render times by processing only one pixel out of every x rather than every single pixel. A slider governs the value of x; you will find it within the Proxy section of the Fusion > Fusion Settings > General panel. Auto Proxy This control likewise serves as a draft mode for speeding up processing as you build your composite. Switching Auto Proxy on lowers the image resolution only while you click and drag to tweak a parameter. The moment you let go of that control, the image returns to full resolution. This makes adjusting processor-intensive operations feel smoother, sparing you the jerkiness of waiting for each frame to render at full quality. To dial in the auto proxy ratio, adjust the matching slider housed under the Proxy section of the Fusion > Fusion Settings > General panel.

Selective Updates As you work in Fusion, only the tools required to show the viewer image are refreshed. The Selective Update options pick which mode governs previews and final renders. These too live under the Proxy section of the Fusion > Fusion Settings > General panel. Here are the three:

- Update All (All): Drives every node in the current node tree to render. Its chief purpose is refreshing all the thumbnails on display in the Node Editor.
- Selective (Some): Renders only those nodes feeding directly into the current image. The label reflects that nothing but the selective nodes get rendered. It is the default.
- No Update (None): Suppresses rendering altogether, a help when you need to apply many changes to a composition that renders slowly.

### Transport Controls in Fusion Studio

In Fusion Studio, the transport controls offer playback buttons, time fields along the left for defining the global range and render range, and a Render button that kicks off rendering of the composite. The right side carries additional controls for proxy and motion blur, and the field at the far right shows the current time.

### Fusion Studio transport controls

### Controlling Playback

Beneath the Time Ruler in Fusion Studio sit eight transport controls. The first four are Composition First Frame, Step Backward, Play Reverse, and Stop; the remaining four are Play Forward, Step Forward, Composition Last Frame, and Loop.

### Fusion Studio transport controls

### Navigation Shortcuts

A lot of the usual transport keyboard shortcuts you already know carry over into Fusion, though a handful are unique to what Fusion needs to do. Use any of these to push the playhead along the Time Ruler from the keyboard:

- Spacebar: Switches forward playback on or off.
- JKL: The familiar JKL scheme is supported, with J to play backward, K to stop,

and L to play forward.

- Back Arrow: Steps backward by a single frame.
- Forward Arrow: Steps forward by a single frame.
- Shift-Back Arrow: Moves to the clip’s Global End frame.
- Shift-Forward Arrow: Moves to the clip’s Global Start frame.
- Command-Back Arrow: Jumps to the Render Range In point.
- Command-Forward Arrow: Jumps to the Render Range Out point.

### Real-Time Playback Not Guaranteed

Since so many of the effects you build on the Fusion page lean heavily on the processor, real-time playback at the project’s full frame rate is not assured unless the composition has been cached beforehand. The “Fusion RAM Cache for Playback” section later in this chapter goes into more detail.

### Frame Increment Options

Right-click any of the Step Backward, Play Reverse, Play Forward, or Step Forward buttons to open a dropdown where you can define a frame increment value. Picking a frame number there causes the playhead to advance in sub-frame or multi-frame steps every time you use a keyboard shortcut or press the Step Forward/Backward buttons. Multi-frame steps are handy while rotoscoping. Sub-frame steps help while rotoscoping or when checking interlaced frames one field at a time (0.5 of a frame).

To set the step size the playhead jumps by, right-click either the Step Forward or the Step Backward button.

### Looping Options

Toggle the Loop button to switch playback looping on or off. Right-clicking the button lets you choose which looping behavior applies:

- Playback Loop: The playhead runs to the end of the Time Ruler and then begins again from the start.
- Ping-pong Loop: After the playhead reaches the end of the Time Ruler, playback runs in reverse until it arrives back at the start of the Time Ruler, then keeps bouncing to and fro.

### Range Fields

In Fusion Studio, the four time fields on the left of the transport controls give you a fast way to change the global range and render range.

Global Time Fields sitting on the left-hand side of the transport controls Audio The Audio button acts as a toggle that mutes or restores whatever audio belongs to the clip. Right-clicking it also opens a drop-down where you can pick a WAV file to play alongside the composition and set an offset for its playback.

### Render

Click the Render button among the transport controls to bring up the composition’s Render Settings dialog. That dialog is where you set the render options and start rendering any Saver nodes the composition contains. Shift-click the button to bypass the dialog and use the default render values (full resolution, high quality, motion blur enabled).

### The Current Time

At the right of the transport controls, the Current Time field displays the frame where the playhead sits, which matches the frame visible in the viewer. You may also type time values into it to shift the playhead by a precise amount. While defining ranges or typing frame numbers to reach a specific frame, the entries can include sub-frame fractions. A range might run from –145.6 to 451.75, or the playhead might rest at 115.22. This is especially handy when animating parameters, because keyframes can sit exactly where they need to be instead of on a frame boundary, producing more natural animation. Sub-frame time also lets you employ time remapping nodes, or simply scale keyframes in the Spline view, without losing precision. NOTE: A great many Fusion fields can evaluate math expressions you type in. Typing 2 + 4 into most fields, for instance, enters the value 6.0. Since Feet + Frames treats the + symbol as a separator rather than a math operator, the Current Time field will not properly evaluate math expressions containing the + symbol, even with the display format set to Frames mode.

### Fusion Studio Viewer Quality and Proxy Options

A row of five buttons on the right of the transport controls lets you either switch on high-quality playback and accept slower processing, or step into one of several proxy modes that briefly cut the display quality to keep processing quick while you work. Whatever you choose here, final output always renders at the highest quality.

These five buttons govern viewer quality, motion blur, the proxy options, and how image processing updates are applied.

HiQ While assembling a composition, how fast you can work tends to matter more than how the displayed image looks. The High Quality setting lets you pick between quicker interactivity and final render quality. With High Quality off, demanding, time-consuming steps such as area sampling, anti-aliasing, and interpolation are skipped so the viewer image appears faster. Turning High Quality on forces a full-quality render to the viewer matching exactly what final delivery will output. MB The Motion Blur button is a global control. Switching Motion Blur off briefly suspends motion blur across the entire composition, regardless of which individual nodes have it on. That can sharply speed up viewer renders. Motion blur must already be enabled on the individual nodes before this button does anything. Prx A draft mode for quicker processing while you build your composite. Switching Proxy on cuts the resolution of the images sent to the viewer, trimming render times by processing only one of every x pixels rather than each one. A slider in the General panel of the Fusion Preferences sets x; you open those preferences via the Fusion menu on macOS, or via the File menu under Windows and Linux. Aprx Another draft mode for quicker processing while you build your composite. Switching Auto Proxy on cuts the image resolution only while you click and drag to change a parameter. As soon as you let go, the image jumps back to full resolution. This smooths the adjustment of processor-intensive operations, removing the jerkiness of waiting for every frame to render fully. The auto proxy ratio likewise comes from a slider in the General panel of the Fusion Preferences, opened from the Fusion menu under macOS or from the File menu on Windows and Linux. Selective Updates Last in this right-hand group of five, this button is a three-way toggle controlling when nodes refresh the viewer image. By default, as you work in Fusion, every node needed to show the viewer image is updated. The Selective Update button alters that behavior across previews and final renders. The three options are:

- Update All (All): Makes every node in the current node tree render. This mainly serves to refresh all the thumbnails shown in the Node Editor.
- Selective (Some): Renders only the nodes that contribute directly to the current image. The name reflects that just the selective nodes get rendered. This is the default.
- No Update (None): Halts rendering completely, which helps when you have many edits to make on a composition that renders slowly.

These options also live in the Fusion Preferences General panel.

### Changing the Time Display Format

Out of the box, every time field and marker in Fusion is counted in frames, yet you can switch the time display to SMPTE timecode or Feet + Frames instead. Here is how to switch the time display format: 1 In DaVinci Resolve, pick Fusion > Fusion Settings; within Fusion Studio under macOS, use Fusion Studio > Preferences; and within Fusion Studio under Windows or Linux, use File > Preferences. 2 Once the Fusion settings dialog appears, open the Defaults panel and pick a Timecode option. 3 Open the Frame Format panel. For timecode, select a frame rate and tick the “has fields” checkbox when your project is interlaced. For feet and frames, set the Film Size value so it matches how many frames fit in a foot of film for the format your project uses. 4 Click Save.

### Keyframe Display in the Time Ruler

Select a node that has keyframed parameters and those keyframes show up along the Time Ruler as small white tic marks, so you can move between and edit them without opening the Keyframes Editor or Spline Editor just to see them.

### The Time Ruler displaying keyframe marks

To shift the playhead between keyframes along the Time Ruler:

- Use Option-Left Bracket ([) to skip leftward onto the nearest keyframe.
- Use Option-Right Bracket (]) to skip rightward onto the nearest keyframe.

### The Fusion RAM Cache for Playback

As you put a node tree together, every image processing operation renders live so the finished result shows in the viewers. Yet as each frame renders — and particularly once you start playback in either direction — these processed images are saved automatically into a RAM cache, allowing you to replay those frames at full speed. While playback runs, the frame rate actually reached appears in the Status bar at the bottom of the Fusion window. Naturally, if you play past the cached portion of the Time Ruler, the uncached frames must first render before they join the cache. Caching priority goes to the nodes currently on screen, according to which nodes are loaded into which viewers. Other nodes may end up cached as well, depending on factors such as how much memory is free and how processor-heavy those nodes are.

### Memory Limits of the RAM Cache

DaVinci Resolve offers just one control for capping the RAM devoted to caching, and it lives in the DaVinci Resolve Preferences Memory and GPU panel.

Limit Fusion Memory Cache To: This slider fixes the upper bound of RAM that Fusion may use for caching. That amount is carved out of the RAM already given to DaVinci Resolve. At most you can hand Fusion 75% of DaVinci Resolve’s overall RAM allotment. Whenever you are away from the Fusion page, that RAM is freed for the other pages in DaVinci Resolve. Fusion Studio, by contrast, provides two controls for capping cache RAM, both in the Preferences Memory panel.

- Limit Caching To: This slider fixes the upper bound of RAM spent on caching. The default of 60% on a 32-GB system caps the cache at 19.2 GB. The most you can grant Fusion Studio is 80% of total system memory, which keeps a minimum reserve for other programs and the operating system.
- Leave at least # MBytes: This number field tightens caching further whenever the system’s free RAM falls under the value you enter. Setting it to 200 MB, for example, tries to keep 200 MB of RAM available for the OS or other programs. Setting the field to 0 lets Fusion Studio consume the entire amount allowed by the Limit Caching To setting and ignore other apps.

Once the cache grows to the Fusion Caching/Memory Limits value in the Memory panel of the Preferences, lower-priority cache frames get dropped automatically to free space for fresh caching. A percentage indicator at the far right of the Status bar along the bottom of the Fusion window lets you watch how much of the RAM cache is in use.

### Displaying Cached Frames

A green line along the bottom of the Time Ruler marks every cached frame for the node you are currently viewing. Wherever the Time Ruler is green, playback should run at full speed.

A green line denotes frames whose playback cache is ready. Temporarily Preserving the Cache When Changing Quality or Proxy Settings Toggling the composition’s quality settings or proxy options does not throw the cache away at once. Instead the green line goes red, signaling that the cache is being held and can serve again when you return to the original quality level or switch proxy mode off. If, though, you play across those frames under the new quality or proxy settings, the held cache is replaced by a fresh cache at the current quality or proxy setting.

A red line shows that cached frames from a different quality or proxy setting are being held.

One case breaks this rule, however. If you cache frames under the High Quality setting and afterward switch High Quality off, the green frames stay green rather than turning red. The High Quality cached frames keep being used even though the HiQ setting is now off.

### Toolbar

Found just below the Time Ruler, the toolbar holds buttons for dropping frequently used nodes into the Node Editor in a hurry. Clicking one of them places that node right after whichever node is selected in the node tree, or, when nothing is selected, drops in a standalone instance of that node. You can tailor the Toolbar and save versions of it for particular tasks.

The toolbar carries buttons for adding frequently used nodes to the Node Editor. By default it is split into sections that gather related, commonly used nodes. Hover the pointer over any button and a tooltip reveals that node’s name.

- Loader/Saver nodes (Fusion Studio Only): The Loader node is the main node for choosing and bringing in clips from the hard drive. The Saver node handles writing or rendering your composition out to disk.
- Generator/Title/Paint nodes: The Background and FastNoise generators see frequent use across all sorts of effects, while the Title generator is an everyday staple, as is Paint.
- Color/Blur nodes: ColorCorrector, ColorCurves, HueCurves, and BrightnessContrast rank as the four most-used color adjustment nodes, and the Blur node is everywhere.
- Compositing/Transform nodes: The Merge node is the main node for layering one image over another. ChannelBooleans and MatteControl both matter greatly for moving channels from one node to another. Resize changes the image resolution, permanently altering what resolution is available, whereas Transform applies pan/tilt/rotate/zoom in a resolution-independent way that always refers back to the source image’s original resolution.
- Mask nodes: The Rectangle, Ellipse, Polygon, and BSpline mask nodes let you draw shapes for rotoscoping, building garbage masks, and other purposes.
- Particle system nodes: Clicking three particle nodes from left to right builds a complete particle system. pEmitter releases particles into 3D space, pMerge combines several emitters and particle effects into more elaborate systems, and pRender produces a 2D result you can composite against other 2D images.
- 3D nodes: A set of seven 3D nodes lets you assemble rich 3D scenes. Clicked from left to right, they auto-attach to one another to form a quick 3D template. ImagePlane3D brings 2D stills and movies in for compositing into 3D scenes. Shape3D produces assorted geometric primitives. Text3D creates 3D text objects. Merge3D combines several 3D image planes, primitive shapes, and 3D text into complex scenes, and Camera3D frames that scene however you choose. SpotLight lights the scenes in various ways, and Renderer3D renders the finished scene, outputting 2D images plus auxiliary channels usable for compositing the 3D output against other 2D layers.

While you are just getting started with Fusion, these nodes really are everything you need to build most ordinary composites. Even after you grow into an advanced user, you will keep finding that these remain by far the operations you reach for most.

### Customizing the Toolbar
