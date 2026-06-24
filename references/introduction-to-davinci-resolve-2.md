# Introduction To Davinci Resolve (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Inside the Effects Library you'll find a folder holding the assorted Video Transitions, Title Effects, Generators, and Filters that you can apply while editing in the Timeline. This library is split into two panels: a Toolbox panel holding the stock Transitions, Titles, and Generators bundled with Resolve, plus an OpenFX panel that surfaces whatever OpenFX transitions and generators are installed on your machine.

### The Effects Library

### Edit Index

Pressing the Index button brings up the Edit Index, which by default presents an EDL-style list of every edit event in the timeline you're working on. The events shown belong to whichever timeline is highlighted in the Timeline list; every clip and every transition appears as its own event, and each event carries several columns of detail. Should you re-edit a timeline, the list updates on its own to mirror what you changed.

### Edit Index List shown open

### Source/Offline and Timeline Viewers

Use the Source Viewer to look at individual clips drawn from the Media Pool and ready them for editing. The Timeline Viewer, by contrast, displays the frame sitting under the playhead in the Timeline. A click selects either viewer, and whichever one holds focus has its name rendered in orange. Typically the Source Viewer's color matches the original source media, whereas the Timeline Viewer reflects any grade you applied over in the Color page.

### Source and Timeline Viewers

Should you wish to reconfigure the Edit page so the Source Viewer is concealed, pick Workspace > Single Viewer Mode; this hides the Source Viewer and leaves a single viewer that contextually presents either a chosen Source Clip or the Timeline's current frame.

### Single Viewer mode

While Single Viewer mode is active, your selection in the Media Pool or Timeline governs which controls show up in the Viewer, which lets you accomplish nearly anything you could with two viewers open simultaneously. Either the Source or Timeline Viewer can likewise be switched into Cinema Viewer mode through Workspace > Viewer Mode > Cinema Viewer (Command-F), which makes the currently selected viewer expand to cover the whole screen. Issuing this command again toggles Cinema Viewer mode off.

### Inspector

Open the Inspector to fine-tune compositing, transform, and cropping parameters on clips, along with clip-specific retime and scaling choices. On top of that, the Inspector lets you tweak the parameters of transitions, titles, and generators placed in the Timeline so you can tailor their look. Normally the Inspector appears next to the Source and Timeline Viewers, yet on smaller screens opening it flips the Edit page into single-viewer mode, presenting the Timeline item under inspection beside the Inspector loaded with that clip's parameters.

### The Inspector, opened and showing a clip’s parameters

### Toolbar

A row of eleven buttons, beginning at the left and stretching across the top of the Timeline, gives you a choice of tools for carrying out the various editing tasks.

### Buttons in the toolbar

### Timeline

The Timeline presents whatever timeline you double-clicked over in the Timelines browser. It is the space where you assemble programs from the ground up, or bring in sequences authored elsewhere to refine inside Resolve. No more than one Timeline may be open at any moment. It splits into audio and video tracks, and every track carries header controls along its left edge that let you pick destination tracks for editing, label tracks, and switch tracks on or off, among other functions. You can tailor how the Timeline looks via the Timeline View Options drop-down found in the toolbar.

### An edited timeline

### Floating Timecode Window

Every page, the Edit page included, offers a timecode window through the Workspace menu. Selecting it brings up a floating timecode window reporting the timecode of whichever Viewer or Timeline currently holds focus. Because the window is resizable, you can scale the timecode up or down.

### A new floating timecode window is available

### Motion Graphics and Visual Effects in DaVinci Resolve

For starters, DaVinci Resolve packs an abundance of effects across both the Edit and Color pages for building titles, transforming and animating clips, compositing and producing transparency effects, pulling mattes, running filters, stabilizing footage, dewarping lenses, and more. On top of that there's the Fusion page, which contributes far more potent VFX and motion graphics power through its node-based interface and rich toolset of effects nodes, keyframing and curve editing controls, plus 2D and 3D compositing features. Getting the most out of DaVinci Resolve means learning to regard the Edit, Fusion, and Color pages as complementary banks of controls.

- To an editor, the Fusion and Color pages amount to a pair of oversized inspectors; one stocked with

each compositing tool you might ever want, the other stocked with each color and visual adjustment control you might wish for, and both of them sit just a single click away.

- For compositing artists, the Edit page can be regarded as a capable shot management surface and also a chance to do VFX work that's tightly woven into the edit of the program at hand.
- For colorists, the Edit page offers a polished space for handling conform problems and knocking out countless finishing chores swiftly and effortlessly, and it sits a single click away.

If you want more detail on the effects DaVinci Resolve makes available, consult the chapters in Part 6, “Editing Effects and Transitions” and Part 11, “Color Page Effects”.

### VFX Connect

However capable DaVinci Resolve's native compositing has become, there are times when the features across the Edit, Fusion, and Color pages still fall short of the effect you're after; in those cases you can turn to DaVinci Resolve's VFX Connect features to dispatch one or several clips from the Edit page Timeline over to Blackmagic Fusion, Blackmagic Design's potent node-based compositing application, and carry out heavier compositing and effects work there. Beyond that, the VFX Connect feature can also round-trip media out to, and bring rendered results back from, external programs like Nuke from The Foundry, Autodesk Flame, or Blender. It's a straightforward round-trip step: it dispatches clips off the DaVinci Resolve timeline into Fusion or some other application, where you layer on effects and wrap up whatever needs doing before rendering a finished effect file that, provided it's named properly, comes back to your timeline on its own. With Blackmagic Fusion, VFX Connect creates a project file for you automatically and names the render path automatically so it links back from the DaVinci Resolve timeline on its own. When you use the feature with third-party applications, you'll have to set up the naming of your rendered effect file by hand. For more on this, refer to Chapter 63, “Introduction to Compositing in Fusion.”

### The New VFX Connect Clip dialo

### The Fusion Page

The aim for the Fusion page is that it will in time grow into a fully featured embedding of Blackmagic Design Fusion, a capable application for 2D and 3D compositing that boasts more than thirty years of refinement in service of the film and broadcast world, responsible for effects featured in countless films and television series. Folded straight into DaVinci Resolve with a freshly revised user interface, the Fusion page lets you leap right from editing into compositing, with no requirement to export media, relink files, or fire up a separate application to finish the job. Everything you require now sits inside DaVinci Resolve.

The Fusion page with its Viewers, Node Editor, and Inspector on display To dig deeper into working on the Fusion page, refer to Chapter 63, “Introduction to Compositing in Fusion.”

### The Work Area

This term probably won't come up often, since you'll favor the names of the specific panels within it that you actually use, but the region labeled the Work Area is the portion at the lower half of the Fusion page UI where you can reveal the three principal panels for assembling compositions and editing animations on the Fusion page. Those panels are the Node Editor, plus the Spline Editor and the Keyframes Editor. Out of the box the Node Editor is what greets you first, and it's the chief area you'll operate in, but it can sit alongside the Spline Editor and Keyframes Editor when needed, and you can free up more horizontal space on screen for these three panels by setting the Effects Library and Inspector into half-height mode if necessary.

The Work Area with the Node Editor, Spline Editor, and Keyframes Editor visible

### Viewers

The Viewer Area takes in the Time Ruler along with the transport controls. The Time Ruler serves as the main “timeline” of the Fusion page, concentrating solely on the composition you're currently building, which might be one clip or many. You can configure this area to present either one viewer or two at the top of the Fusion page, the choice made through the Viewer button sitting at the far-right end of the Viewer title bar. A given viewer is able to present a single node's output drawn from any spot in the node tree. You decide which node lands in which viewer. That makes it simple to load different nodes into each viewer for side-by-side comparison. As an example, you might drop a Keyer node into the left Viewer and the finished composite into the right Viewer, letting you watch the image you're tuning and the final outcome together.

A pair of viewers lets you tweak an upstream node in one while watching how it changes the whole composition in the other Ordinarily, a viewer renders the 2D nodes of your composition as one flat image. When you're inspecting a 3D node, though, you get the option to switch that viewer into one of several 3D views, including a perspective view granting a repositionable stage on which to lay out the elements of the world you're constructing, or a quad view that shows your composition from four angles, making it simpler to position and edit objects and layers across the XYZ axes of the 3D space you're working in.

### Toolbar

Positioned just below the Time Ruler, the toolbar holds buttons that let you rapidly drop commonly used nodes into the Node Editor. Clicking any of them inserts that node after whichever node is currently selected in the node tree, or drops an unconnected copy of it when nothing is selected. Toolbar buttons for placing frequently used nodes into the Node Editor

Six sections divide the toolbar, grouping commonly used nodes together. As you move the pointer over a button, a tooltip reveals that node's name.

### Effects Library

On the Fusion page the Effects Library exposes every node and effect on offer there, encompassing the effects shipped with DaVinci Resolve along with third-party OFX where present. Whereas the toolbar surfaces many of the most frequent nodes you'll reach for in any composite, the Effects Library holds every single tool the Fusion page provides, sorted by category, with each node poised for quick insertion into the Node Editor. Put simply, the Effects Library offers far, far more nodes than the toolbar, covering an enormous range of purposes.

### The Effects Library with Tools open

### Node Editor

The Node Editor is the core of the Fusion page, since it's where you construct the tree of nodes forming each composition. Each node you tack onto the node tree contributes one specific operation that yields a single effect, whether that's softening the image with blur, shifting color, laying down paint strokes, drawing then attaching a mask, pulling a key, generating text, or merging a pair of images together.

The Node Editor presenting a node tree that builds a composition Inspector The Inspector sits as a panel on the right-hand side of the Fusion page, where you view and adjust the parameters belonging to one or several selected nodes. Selecting a node in the Node Editor brings that node's parameters and settings into the Inspector, ready for editing. Two panels make up the Fusion Inspector. The Tools panel surfaces the parameters of whatever nodes are selected. The Modifiers panel presents different content depending on the node. Across all nodes it surfaces the controls for Modifiers, which are adjustable expressions you've attached to particular parameters so they animate themselves in various ways.

The Inspector shows parameters from one or more selected nodes

Nodes with different tabs expand the Controls, Transform, and Settings parameters

On top of that, plenty of nodes present several tabs' worth of controls in the Inspector, appearing as icons across the top of each node's parameter section. Click any tab to bring up that group of controls.

### Thumbnail Timeline

Concealed by default, the Thumbnail timeline opens when you click the Clips button in the UI Toolbar, and it shows up beneath the Node Editor while it's open. The Thumbnail timeline displays every clip in the current Timeline, offering a means of moving from one clip to the next when handling several compositions in your project, and giving you an interface for building and switching between multiple versions of compositions and resetting the active composition whenever that's needed.

The Thumbnail timeline helps you move through the Timeline and handle composition versions Media Pool On the Fusion page, the Media Pool carries on in its role as the storehouse for every piece of media you've brought into your project. This makes it painless to pull extra clips into your compositions just by dragging whatever clip you want out of the Media Pool and into the Node Editor. The media you bring in shows up as a fresh MediaIn node within your composition, ready to be woven into your node tree however suits you.

The Media Pool in Thumbnail mode showing video clips

### Status Bar

Sitting at the foot of the Fusion page, directly above the Resolve Page bar, the status bar presents a range of current information about whatever you're selecting and whatever is going on in the Fusion page. To illustrate, hovering the pointer over any node surfaces details about that node in the status bar (and in a floating tooltip too), the frame rate currently being hit shows up whenever playback starts, and the share of the RAM cache in use stays visible at all times. Further information, updates, and warnings turn up in this region as you work.

The status bar below the Node Editor reporting details on the node beneath the pointer, alongside a floating tooltip

### The Console

Reachable through Workspace > Console, the console is a window where you can read the error, log, script, and input messages that may shed more light on whatever the Fusion page is attempting to do. It's likewise the place where you can review FusionScript outputs or type FusionScripts in directly. Now and then the status bar (covered above) will show a badge to signal there's a message in the console worth a look. That badge tells you whether the message is an error, log, or script message.

### The Console window

### The Color Page

The Color page is where you handle color correction, or grading, for your program. It carries every control for working with color and contrast, cutting noise, making limited secondary color corrections, crafting various image effects, tweaking clip geometry, and applying many other corrective and stylistic changes. Seven principal areas make up the Color page, and they cooperate to help you assemble a grade. For fuller detail on the Color page, refer to Chapter 126, “Using the Color Page.”

### The Color page

### Viewer

The Viewer presents the frame sitting at the playhead's current spot in the Timeline. Its contents are nearly always sent out to video through whatever I/O interface you've hooked up. A header runs across the top of the Viewer showing the Project and Timeline names, plus a Viewer Timecode display that by default reports each clip's source timecode. That Timeline name doubles as a drop-down that lets you jump to any other timeline in the project. Beneath the image, a jog bar (sometimes called a scrubber bar) lets you drag the playhead through the clip's full length, while transport controls below that govern playback. Across the top, a toolbar supplies controls for Image Wipes, Split-Screen, and Highlight display. Other controls let you switch audio playback on or off, or tune it by right-clicking the speaker icon and dragging the slider. You can also pick which onscreen controls are showing at the moment.

### Viewer with transport controls

You can additionally drop the Viewer into Cinema Viewer mode via Workspace > Viewer Mode > Cinema Viewer (Command-F) so it covers the whole screen. Issuing this command again toggles Cinema Viewer mode off. Two further modes, Enhanced Viewer (Option-F) and Full Screen Viewer (Shift-F), exist to grant more working room for chores such as window positioning and rotoscoping.

### Gallery

You use the Gallery to hold still frames that serve as reference when comparing one clip against another. Every still frame also keeps that clip's grade so you can reapply it down the line; stills and grades live together. A button opens the Album browser, which you use to arrange your stills. Across the top of the Gallery, Memories let you stash grade information you can call up through a control panel or keyboard shortcuts. You can also bring up a bigger Gallery window inside the Color page that affords more space for arranging your saved stills and grades. For more on the Gallery page, refer to Chapter 141, “Using the Gallery.”

The Gallery has Memories, stills saved in albums, and your PowerGrades

### Node Editor

The Node Editor is where you string together one or more individual corrections (nodes) to build multi-correction grades (shown as node trees). It's a potent approach to assembling grades, because varied combinations of nodes let you produce different corrections and very particular adjustments by reordering operations, blending keys, or shifting the layer order of separate adjustments. For more on the Node Editor, refer to Chapter 143, “Node Editing Basics.”

Use the Node Editor to lay out the signal flow that processes your grade Timeline Over in the Color page, the Timeline reflects the contents of the Edit page Timeline, yet it takes on a different appearance tuned to what a colorist needs. The content is the same, though, and any change made to the Timeline in the Edit page shows up at once in the Color page as you flip between them. The Color page Timeline offers a handful of ways to move through the clips in your project and to keep tabs on what's been done to which clips.

### The Color page Timeline

Three parts divide the Timeline, each presenting different information and supplying different controls. Across the top, a Timeline Ruler lets you scrub the playhead over many clips and can be zoomed out far enough to display every clip in your whole program. Below it, the MiniTimeline (which you can open or close with a button at the right of the palette bar) presents a compact rendition of the Edit page Timeline in which each clip runs as long as its real duration. At the foot of the Timeline sits the Thumbnail timeline, where a single frame stands in for each clip. The clip currently selected is ringed in orange, and above and below each thumbnail you'll find details like its source timecode, the clip number together with the track number, the version name, plus indicators for grading, for tracking, for flagging, and the like.

### Left Palettes

A row of palettes at the lower left of the Color page opens up the various sets of grading tools, used chiefly for working on color, contrast, and raw media format settings. You open each individual palette by clicking its matching icon across the top of the Palette panel.

### Left palette selection buttons in the top bar

The palettes on offer are the Camera Raw palette (for metadata tweaks on raw media formats), the Color Match palette (which produces grades on its own by reading on-camera color charts), the Color Wheels (graphical balance controls along with master wheels or sliders that tune YRGB Lift/Gamma/Gain), HDR Grade for advanced High Dynamic Range grading, the RGB Mixer (which blends color channels into one another), plus the Motion Effects palette, whose controls handle noise reduction and synthetic motion blur.

### Center Palettes

When you're at 1920x1080 resolution or above, a second group of palettes is laid out at the lower center of the Color page. These palettes cover broad functionality, and the changes you make with them can be paired with those made through the Color palettes.

### Center palette selection buttons

NOTE: When the resolution drops, the Left and Center palettes get combined so the DaVinci Resolve interface squeezes into a tighter footprint. Among the eight Center palettes you'll find these: Curves palette, Color Warper palette, Qualifiers palette, Windows palette, Tracker palette, Magic Mask palette, Blur palette, Key palette, Sizing palette, along with the Stereoscopic 3D palette.

### Keyframe Editor

The Keyframe Editor gives you an interface for animating Color, Sizing, and Stereo Format adjustments across time. Each node sitting in the Node Editor corresponds to its own track over in the Keyframe Editor, so you're able to animate the adjustments of every node independently.

### Keyframe Editor displaying dynamic grade changes

Beyond that, each node's track can be expanded to expose parameter groups, so you can animate portions of an individual node's functions separately from other functions inside the same node.

### The Fairlight Page

When you're in single monitor mode, the Fairlight page offers an optimized view of your project's audio tracks, complete with an expanded mixer and bespoke monitoring controls that make it easy to assess and tune your program's levels and craft a smooth, balanced mix.

### Fairlight page

### About Audio Monitoring and Audio Input

The audio processing across DaVinci Resolve, on the Fairlight page as well as audio processing through Fairlight FX plugins, works identically on every platform DaVinci Resolve runs on, namely macOS, Windows, and Linux. DaVinci Resolve handles audio monitoring through:

- The audio coming from a supported Blackmagic Design I/O device, for instance an UltraStudio or a Decklink.
- The on-board audio of your macOS, Windows, or Linux workstation.
- Any interface that is Core Audio compatible, Windows compatible, or compatible with Advanced Linux Sound

Architecture (ALSA)-supported third-party audio interface.

- The Fairlight Audio Accelerator, MADI Upgrade, and Fairlight Audio Interface. DaVinci Resolve handles audio input through the embedded audio carried on an incoming SDI video feed when capturing live A/V source, by way of system audio and also through the Fairlight Audio Accelerator, MADI Upgrade, and Fairlight Audio Interface.

### The Audio Timeline

At the core of the Fairlight page, the Audio Timeline presents the channels and tracks of whichever timeline is selected in a manner unlike the Edit page, relying on a one-channel-per-track layout tuned for mixing and sweetening audio. The Audio page Timeline can't be closed.

### The Audio Timeline

### Audio layering in a mono audio track

The Fairlight page of DaVinci Resolve handles several audio tracks, and any given audio track can hold several lanes. The clips edited into the Timeline turn up within each track, with each clip's recorded channels filling as many lanes as that clip offers. Along the left of every track is a header region containing a set of controls. The Fairlight page parts ways with the Edit page Timeline in one more distinctive way, in that it supports audio layering. Audio layering is a specialized audio editing mode letting you stack several audio clips in one track, where whichever audio clip sits on top decides which audio plays. In effect, when audio layering is on, stacked audio clips behave like stacked video clips all set to 100% opacity, the topmost clips hiding (or muting) those below.

Switching on Track Layers frees up room to edit additional audio within each track
