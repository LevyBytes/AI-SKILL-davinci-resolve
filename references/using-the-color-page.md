# Using The Color Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using the Color Page

Because DaVinci Resolve began life as a professional grading application, the Color page sits at the core of the DaVinci Resolve experience. Everything you need to manipulate color and contrast, cut noise, build limited secondary corrections, craft image effects of various sorts, adjust clip geometry, and apply countless other corrective and stylistic changes lives within the Color page. This chapter teaches you how to read the Color page interface, tailor it to your needs, and work within it to play back and move through your project’s timeline. You will also pick up how to study and compare clips before grading using stills, playheads, and the video scopes built into DaVinci Resolve.

### The Color Page Interface

The Color page splits into seven main areas that cooperate to help you build a grade. This section runs through what those areas are and how each one works.

### The default layout of the Color page

### The Interface Toolbar

Running across the very top of the Color page is a toolbar of buttons for showing and hiding different parts of the user interface. Reading left to right, they are: The Interface toolbar Gallery: Shows or hides the Gallery panel. LUTs: Shows or hides the LUT Browser. Media Pool: Shows or hides the Media Pool. Clips: Shows or hides the Thumbnail timeline. A drop-down to its right lets you select a timeline filtering option for the Thumbnail timeline. Quick Export: Brings up the Quick Export window.

Timeline: Shows or hides the Mini-Timeline. Nodes: Shows or hides the Node Editor. Open FX: Shows or hides the Open FX panel. Lightbox: Shows or hides the Lightbox.

### Showing Which Panel Has Focus

Any time you click somewhere on the DaVinci Resolve interface with the pointer, or use a keyboard shortcut to “select” a given panel (as in the Edit page), you grant that interface panel “focus.” A focused panel grabs specific keyboard shortcuts to act within itself rather than somewhere else in the interface. A highlight along the top edge tells you which panel holds focus, so you can keep tabs on which part of the current page is taking precedence, and you can move focus around as needed to get your work done. You can switch the Focus Indicator on or off under Preferences > User > UI Settings > Show focus indicators in the user interface.

The focus indicator running along the Media Pool’s top edge, beside a Viewer that lacks focus

### Viewer

The Viewer presents the frame at the playhead’s current spot in the Timeline. A header across the top of the Viewer shows the Project and Timeline names, plus a Viewer Timecode display that by default reports each clip’s source timecode. The Timeline name doubles as a drop-down that lets you jump to any other timeline in the project. A scrubber bar beneath the image lets you drag the playhead through the clip’s full length, while transport controls below that govern playback. A toolbar up top supplies controls for Image Wipes, Split‑Screen, and Highlight display. Further controls let you loop playback, flip Unmix mode on or off, switch audio playback on or off, and pick which onscreen controls show at the moment. There’s more on using the Viewer later in this chapter.

### The default Viewer with transport controls

You can also switch the Viewer into one of three alternate modes to get a larger working image. All three are reachable from the Workspace > Viewer Mode submenu.

- Enhanced Viewer: (Option-F to toggle this on and off) clears away everything flanking the Viewer on both sides, handing you a roomy working area for jobs like window positioning and rotoscoping, all while leaving the palettes and their controls on view as you work.

### The Color page in Enhanced Viewer mode

- Full Screen Viewer: (Shift-F to toggle this on and off) is there to grant extra working area for jobs like window positioning and rotoscoping. It can also show the Effects panel at full height, and you’re free to switch the Node Editor on and off to reach different effects controls as you work.

### The Color page in Full Screen Viewer mode

- Cinema Viewer: (P to toggle this on and off) stretches the Viewer to fill your workstation’s whole monitor. It comes in handy when you want to play the current Timeline free of distractions. Move the pointer over the image and transport controls plus a jog bar appear so you can drive playback. For DITs, right-clicking anywhere on the image opens a contextual menu for switching on and tailoring a video scope overlay (which you can drag to various spots on the Viewer).

### The Color page in Cinema Viewer mode

### Gallery

The Gallery holds still frames you keep for reference along with grades you may wish to copy; stills and grades are stored side by side. A button opens the Album browser, which you use to organize your stills. Down at the bottom of the Gallery, Memories let you stash grade information that you can recall via a control panel or keyboard shortcuts. The Color page Gallery mirrors what the Gallery page holds. For more on the Gallery page, see Chapter 141, “Using the Gallery.”

The Gallery has Memories, stills saved in albums and your PowerGrades

### LUT Browser

The LUT Browser gives you one central place to browse and preview every LUT installed on your workstation. Every LUT shows up in the sidebar, grouped by category.

### The LUT Browser

Out of the box, every LUT shows a test thumbnail that previews its effect, yet you can also see a live preview of the current clip under a LUT by hover-scrubbing the pointer across a given LUT’s thumbnail (more on that further down). To open the LUT Browser: in the UI Toolbar at the top of the Color page, click the LUT Browser button. Methods of working with the LUT Browser:

- To see the LUTs in any category: Click a LUT category in the sidebar to select it, and that category’s LUTs show up in the browser area.
- To make a LUT a favorite: Move the mouse over a LUT and click the star badge in its upper right-hand corner, or right-click any LUT and pick Add to Favorites. That LUT then turns up whenever you select the Favorites category.
- To search or filter for specific LUTs: Open a bin containing the LUT you’re after, click the magnifying glass icon to bring up the search field, and type text that pinpoints the LUTs you want.
- To see LUTs in Column or Thumbnail view: Use the Column or Thumbnail buttons at the LUT Browser’s top right to set how the LUTs display in the browser area.
- To sort LUTs in Thumbnail view: Open the Thumbnail Sort drop-down menu and pick the criteria to sort the LUTs by. The choices are Filename, Type, Relative Path, File Path, Usage, Date Modified, along with ascending and descending sort modes.
- To sort LUTs in Column view: Click a column header to sort on that column, and click it again and again to flip between ascending and descending modes.
- To give a LUT a new thumbnail taken from a clip: Pick the clip and frame you want as that LUT’s fresh thumbnail, then right-click the LUT and pick Update Thumbnail With Timeline Frame.
- To put a LUT’s thumbnail back to the standard one: Right-click the LUT and pick Reset Thumbnail to revert to the standard test image.
- To pull newly installed LUTs into a category: Choose the LUT category, then right-click anywhere in the browser area and pick Refresh, reloading that category’s contents from disk.

Methods of adding LUTs to a grade from the LUT Browser:

- To apply a LUT to the current node: Pick a clip in the Thumbnail timeline, then right-click a LUT and pick Apply LUT to Current Node off the contextual menu.
- To apply a LUT to a specific node: Drag a LUT out of the LUT Browser and drop it on the node you’d like it applied to. Dropping a LUT onto a node that already carries one replaces the old LUT with the new.

### Media Pool

The Media Pool is on hand in the Color page, which makes it simple to drag and drop clips you’d like to use as external mattes straight into the Node Editor for quick, easy hookup when building various Color page effects. Opening it swaps out the Gallery, since it occupies the same area. For the most part, the Color page Media Pool behaves like the Media Pool on almost every other page of DaVinci Resolve.

The Media Pool is available in the Color page. Dragging a clip from the Color page Media Pool over to the Node Editor triggers two things:

- The clip becomes an external matte within the current grade, usable as a matte for secondary adjustments or — paired with the Layer mixer — as a compositing layer for blending textures or images into your grade.
- The clip is also hooked up automatically, as a clip matte, to the Media Pool clip that matches the one you’re grading, which helps you keep straight which clips draw on others as mattes.

For more about the Media Pool, turn to Chapter 18, “Adding and Organizing Media with the Media Pool.”

### Node Editor

The Node Editor is where you stitch one or more individual corrections (nodes) into a finished multi-correction grade (node tree). It’s a potent way to assemble grades, since the various node types let you create different blends of corrections and very precise adjustments by reordering operations, combining keys, or shifting how the various adjustments are layered. For more about the Node Editor, consult Chapter 143, “Node Editing Basics.”

Node Editor to construct your grade processing signal flow

### Timeline

The Timeline gives you several ways to navigate the clips in your project and to track what has been done to which ones. It splits into two parts, each showing different information and offering different controls, and each able to be opened or closed on its own through the Clips and Timeline buttons on the Interface toolbar.

### The Thumbnail timeline with a Mini-Timeline below

### Thumbnail Timeline

Up top is the Thumbnail timeline, where each clip stands for a single frame. The Thumbnail timeline (or its alternate form, the Lightbox) is the simplest way to pick which clip you want to work on and to make clip selections for various grade-management tasks. Whichever clip is currently selected — the one whose controls appear in the Color page’s various palettes — is highlighted in orange. A good deal of useful information surrounds each thumbnail above and below it — among it a clip’s clip number, source timecode, and track number, plus whether the clip is flagged, automatically linked or grouped, tracked, and so on.

### A clip thumbnail in the Thumbnail timeline

You can change what appears beneath each thumbnail by double-clicking the space below it. Several options exist, and you can keep double-clicking to cycle among them:

- Clip format or codec (the default)
- Clip Name (either the clip name or the file name, according to how View > Show File Names is set) or

Multicam Angle (when you’re working with multicam clips)

- Version name or number

### Mini-Timeline

Below it, the Mini-Timeline presents a compact view of the Edit page Timeline’s video tracks, where each clip stretches to its real duration. This gives the most faithful view of how the current timeline is built, because clip length stands in for duration and the multiple tracks appear, so you can spot which clips overlap. A Timeline Ruler scrubs the playhead over several clips and zooms out far enough to show every clip in your entire program.

The Mini-Timeline reveals timeline structure, while small track header controls let you switch tracks on, switch tracks off, and have the playhead bypass particular tracks Small track labels down the left of each track in the Mini-Timeline let you turn a track on or off with a click (white labels mark enabled tracks, gray ones disabled). Option-click one of these controls and the track stays enabled but the playhead passes it over during the Next and Previous Clip commands — useful when you’d rather skip clips you don’t need to grade (such tracks show a red label). Inside the Mini-Timeline, whichever clip is selected appears highlighted in orange, and you select any clip by clicking it. A scroll bar at the bottom moves you left and right, while the mouse scroll wheel zooms in and out. The Mini-Timeline shows six tracks of video at most. Should your project hold more, you can scroll up and down to expose the hidden ones. Any markers placed on clips or on the Timeline back in the Edit page turn up here too, and clicking any marker reveals and lets you edit its color and notes.

As pictured above, a colored outline encircles the clip number of any shot that’s been graded, and that outline doubles up once extra versions are applied to the clip. For fuller detail on the Color page Timeline, see Chapter 130, “Camera Raw Palette.”

### Palette Area

Most of the everyday tools and functions for grading are spread across a series of palettes in the Color page’s palette area. You reach these palettes through a row of palette buttons along the Palette bar at the top of the area.

### All palettes seen in the Palette bar

These buttons also tell you which palettes carry adjustments for the node currently selected in the Node Editor. A palette holding adjustments shows a small orange dot on its corresponding palette button.

An orange dot on a palette button signals that the palette holds adjustments Left Palettes A row of palettes along the Color page’s lower left brings up different sets of grading tools, used chiefly to work color, contrast, and raw media format settings. You open any individual palette by clicking its matching icon at the top of the Palette panel.

### Left palette selection buttons

Camera Raw palette: For metadata adjustments to raw media formats Color Match palette: Automatic grading driven by test charts Primaries: Graphical color balance controls plus master wheels, together with a Slider mode that adjusts YRGB Lift/Gamma/Gain HDR palette: Sophisticated primary grading controls built for wide-gamut media and SDR or HDR mastering RGB Mixer: For blending color channels into one another Motion Effects palette: Carrying controls for noise reduction and artificial motion blur The five palettes work individually or in combination, according to your goal. For more on most of them, see Chapter 131, “Primaries Palette.” For the Motion Effects palette specifically, see Chapter 153, “The Motion Effects and Blur Palettes.” Center Palettes Once you’re at 1920x1080 resolution or beyond, a second cluster of palettes lines up at the Color page’s lower center. These palettes range across many functions, and what you achieve with them can be folded together with what you do using the Color palettes.

### Center palette selection buttons

NOTE: When the resolution is lower, the Left and Center palettes combine so the DaVinci Resolve interface fits a tighter space.

Among the center palettes are the Curves palette, Color Slice palette, Color Warper palette, Qualifier palette, Window palette, Tracker palette, Magic Mask palette, Blur palette, Key palette, Sizing palette, and Stereoscopic 3D palette.

### Curves palette

### ColorSlice palette

### Color Warper palette

### Qualifier palette

### Window palette

### Tracker palette

### Magic Matte palette

### Blur palette

### Key palette

### Sizing palette

### Stereoscopic 3D palette

### Keyframe Editor, Video Scopes, and Information

The bottom right of the Color page can be flipped among one of three things:

The trio of controls that bring up the Keyframe Editor, the video scopes, or the Information palette Keyframe Editor: Hands you an interface for animating Color, Sizing, and Stereo Format adjustments across time. Every node in the Node Editor lines up with a track in the Keyframe Editor, so each node’s adjustments can be animated separately. Beyond that, a node’s track opens up to reveal parameter groups, letting you animate subsets of one node’s functions independently of that node’s other functions. For more on keyframing, consult Chapter 148, “Keyframing in the Color Page.” Video scopes: Gives you a docked spot in which a single video scope can be surfaced at a time for reference while you work. The video scopes can also be “undocked” into a stand-alone window capable of showing four different scopes at once. More on the video scopes comes later in this chapter. Information: Offers a means of viewing clip and system information as you work.

### Dual-Monitor Layout

The Color page offers a dual monitor layout that hands the primary monitor as much room as possible for the Viewer, Node Editor, and Control palettes, while the secondary monitor simultaneously displays a Gallery, Lightbox, Keyframe Editor, Metadata Editor, and Video Scope panel. A dual-screen layout’s second screen can be resized but not rearranged. Even on a single ultra-wide monitor you can adopt the dual-monitor layout, and DaVinci Resolve scales the interface as if a pair of ordinary monitors stood next to each other. To enter dual-screen mode: Choose Workspace > Dual Screen > On.

### The Color page in dual screen mode

To swap which UI elements land on which monitors: Choose Workspace > Primary Display > (Monitor Name), which flips the contents of the two monitors while in dual screen mode.

### The Info Palette and Clip Information

The Info palette stays hidden by default. Click the Info palette button at the far right of the toolbar to reveal it. It carries two tabs that show different information, and it holds no user-editable controls.

### Info palette displaying Clip Info and System Status

### Clip Info

The first tab reports on whichever clip is currently selected in the Timeline. None of this is editable; it’s provided for reference, and it includes:

### File Name

### Reel Name Start T/C End T/C Duration Frames

The disk file name of the media. Where the current clip is a Multicam clip, this instead shows whichever angle is selected. That clip’s reel name, provided one is being read correctly. The first frame’s source timecode value within the clip. The last frame’s source timecode value within the clip. How long the clip runs, expressed in timecode. How long the clip runs, expressed in frames.

### Version Frame Rate Source Res Codec

Which remote or local version the clip uses. The frame rate the clip runs at. The source clip’s native resolution. Which codec or format the source clip uses.

### System Info

The second tab reports on the operational modes DaVinci Resolve is currently running in. It’s meant to convey the state of the various DaVinci Resolve features that can be turned on, turned off, or cycled through different options. This information includes:

### Clips Proxy Clip Cache Ref Transform Ref Mode

### Wipe Style

### Convergence Stereo Grade Stereo Display

How many clips the Timeline holds in total. Whether Proxy mode is on (On or Off). Where the Clip Cache mode stands (Off, All, Dissolves, User, User & D). Where Reference Still reposition stands. Where the Reference mode stands (Gallery, Timeline, Offline). Whichever Wipe Style is chosen for split screens (Wipe-H, Wipe-V, Wipe-M, Wipe-A). The Convergence setting in force (Linked Zoom, Opposite) Whichever Eye and Gang mode shows (Left or Right - Gang or Solo). The Stereo Display mode in force (Mono or Stereo).

### Clip Details

You can right-click whichever clip is currently selected in the Thumbnail Timeline and pick View Clip Details to bring up a small window holding all of that clip’s information at a glance. Drag this window wherever you like, even onto another display.

### The Clip Details window

None of this is editable; it’s provided for easy reference, and it includes:

File Name Start Timecode End Timecode Duration Frames Reel Name Version Format Codec Folder Description Comments EDL Comments

At the top sits the media’s disk file name. The first frame’s source timecode value within the clip. The last frame’s source timecode value within the clip. How long the clip runs, expressed in timecode. How long the clip runs, expressed in frames. That clip’s reel name, provided one is being read correctly. Which remote or local version the clip uses. The format the source clip uses, together with its frame size and bit depth. Which codec the source clip uses. The disk directory where the source media lives. The Metadata Editor’s description field. The Metadata Editor’s Comments field. Any EDL comments tied to that event, where they exist.

### Customizing the Color Page

The Color page’s assorted sections can be resized, hidden, and rearranged as needed to suit different working styles. This section covers every method available for Color page customization. It’s easy to resize the Viewer, Gallery, and Nodes Editor against one another, so you can make the Viewer bigger, broaden the Node Editor for extra workspace, or free up more or less space for stills inside the Gallery. To resize the Viewer, Gallery, and Node Editor: hover the pointer over the vertical divider sitting between any two areas. When the resize icon appears, drag that divider sideways to enlarge one area at the other’s expense. In the same way, the Gallery, the Memories, the Node Editor, and the Keyframe Editor can each be expanded fully to take over whatever interface area lies next to them. To expand the Keyframe Editor, Viewer, and Gallery: click the Expand control in the top right of whichever interface area you want enlarged. Click the Expand control once more afterward and that area shrinks back to its starting size, bringing back whatever had been hidden. Within Display mode the Viewer can be hidden completely, shoving the Gallery to the far right of the DaVinci Resolve window while the Node Editor stretches to fill the remainder. To toggle Display mode: right-click in the Node Editor’s empty area and pick Toggle Display Mode off the contextual menu. Repeat to switch Display Mode off and set the interface back the way it was.

To reveal or conceal the Mini-Timeline: click the Timeline button sitting at the far right of the palette button bar. To reveal or conceal the Color page Viewer’s upper toolbar: open the Viewer option menu and pick Show Viewer Options to clear its checkmark. To send every page back to its default layout: choose Workspace > Reset UI Layout.

### Undo and Redo in DaVinci Resolve

Wherever you happen to be in DaVinci Resolve, the Undo and Redo commands let you step out of actions you’ve taken or commands you’ve run, and reapply them should you change your mind. DaVinci Resolve can undo the whole history of what you’ve done since you created or opened a given project. Close a project and its entire undo history is wiped; the next time you take up that project, its undo history begins fresh. Since DaVinci Resolve packs so much capability into a single application, it keeps three distinct sets of undo “stacks” to help you stay organized.

- The Media, Cut, Edit, and Fairlight pages draw on one shared multiple-undo stack, letting

you retrace your steps out of changes made within the Media Pool, the Timeline, the Metadata Editor, and the Viewers.
