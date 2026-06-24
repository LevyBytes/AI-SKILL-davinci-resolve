# Exploring The Fusion Interface (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Down along the bottom, the Spline Editor toolbar gathers together a blend of control point interpolation buttons, Spline loop modes, and Spline editing tools.

### Control Point Interpolation

Those first six buttons let you reshape the interpolation across one or more chosen control points.

### Control point interpolation controls

Smooth: Builds Bézier curves that adjust on their own to yield smoothly interpolating animation. Linear: Builds straight-line interpolation running between control points. Invert: Flips the vertical placement of LUT splines that aren't animated. It has no effect on animation splines. Step In: At each keyframe, produces abrupt value jumps at the keyframe immediately to its right. Much like a hold keyframe in After Effects® or a static keyframe over on the DaVinci Resolve Color page. Step Out: Produces abrupt value jumps at every keyframe where the value shifts at the next keyframe to its right. Much like a hold keyframe in After Effects or a static keyframe over on the DaVinci Resolve Color page. Reverse: Flips the chosen keyframes' horizontal placement in time, leaving the keyframes running backward.

### Spline Loop Modes

The three buttons that follow let you arrange spline looping past the final control point on a parameter's spline, letting a small run of keyframes animate across a vastly longer span. Looping touches only the control points you've selected.

### Spline Loop modes

Set Loop: Plays back the identical keyframe pattern again and again. Set Ping Pong: Plays a reversed copy of the chosen keyframes followed by a straight copy of them, knitting a smoother run of animation. Set Relative: Plays back the identical pattern of chosen keyframes, but bumps the values of each repeated pattern up or down by the overall trend across every keyframe in the selection. The upshot is a keyframe loop whose value climbs or falls steadily with each fresh loop.

### Spline Editing Tools

The five buttons after that supply purpose-built Spline editing tools.

### Spline editing controls

Select All: Grabs every keyframe presently on hand in the Spline Editor. Click Append: One click turns this tool on, another click turns it off. The tool lets you add or rework keyframes and spline segments (the stretches of spline between two keyframes), according to whichever keyframe mode you're in. Under Smooth or Linear keyframes, clicking anywhere over or under a spline segment drops a fresh keyframe onto the segment right where you clicked. Under Step In or Step Out keyframes, clicking anywhere over or under a line segment shifts that segment to the spot you clicked. Time Stretch: Once you've chosen a range of keyframes, flipping on the Time Stretch tool brings up a box for squeezing and stretching the whole keyframe range against one another, reshaping the broad timing of a keyframe sequence while holding the relative spacing from keyframe to keyframe. As an alternative, you can flip on Time Stretch and drag a bounding box over the keyframes you mean to adjust, making a time‑stretching boundary that way. A second click on Time Stretch shuts it off. Shape Box: Flip on the Shape Box to drag a bounding box over a cluster of control points you want to work, so you can squish and stretch them horizontally (via the top/bottom/ left/right handles), corner pin (via the corner handles), move (by hauling on the box edge), or stretch a corner (Command-drag a corner handle). Show Key Markers: Flipping this control on surfaces keyframes up in the top ruler matching the frame where each visible control point sits. Those keyframes take on the color of the control points they point to.

### Thumbnail Timeline in the Fusion Page

Over on the Fusion page of DaVinci Resolve, the Thumbnail timeline (which stays hidden by default) opens up when you click the Clips button in the UI toolbar, and it shows beneath the Node Editor while open. The Thumbnail timeline puts every clip in the current Timeline on view, handing you a way to move from clip to clip. Each thumbnail carries a pop-up menu for building and flipping among several composition versions, and for resetting the current composition whenever that's needed.

Through the Thumbnail timeline you move around the Timeline and handle the various composition versions.

Right-clicking any thumbnail brings up a contextual menu.

### The contextual menu for the Thumbnail timeline

To open another clip:

- Click any thumbnail to leap to that clip's composition. An orange outline marks the current clip.

To navigate the Thumbnail timeline:

- Middle-click and drag the Timeline either way to scroll across the clips in the Timeline.
- Click and drag the slider down at the foot of the Thumbnail timeline to scroll across the clips in the Timeline.

To create and manage versions of compositions:

- To spin up a fresh composition version: Right-click the current thumbnail and pick Create New Composition off the contextual menu.
- To load a different composition: Right-click the current thumbnail and pick “NameOfVersion” > Load off the contextual menu.
- To delete a composition: Right-click the current thumbnail and pick “NameOfVersion” > Delete off the contextual menu.
- To rename a composition: Right-click the current thumbnail and pick “NameOfVersion” > Rename off the contextual menu.

To reset the current composition:

- Right-click the current thumbnail and pick Reset Current Composition off the contextual menu.

To change how thumbnails are identified:

- Double-click the strip beneath any thumbnail to cycle among clip format, clip name, and the composition version name.

### The Media Pool in the Fusion Page

On DaVinci Resolve's Fusion page, the Media Pool keeps right on doing its job as the home for all the media you've brought into your project. That makes pulling extra clips into your compositions a snap — just drag whichever clip you want out of the Media Pool and into the Node Editor. Media you bring in lands as a fresh MediaIn node in your composition, set to be worked into your node tree however suits you. TIP: Should you drag one or several clips from the Media Pool onto a connection line linking two nodes in the Node Editor, the clips wire onto that line automatically by way of enough Merge nodes to join them all.

To dig into the countless capabilities of the Media Pool, turn to Chapter 18, “Adding and Organizing Media with the Media Pool.”

The Media Pool in Thumbnail mode showing video clips

### Importing Media Into the Media Pool on the Fusion Page

Should you be sitting on the Fusion page and need to bring in a few clips fast for immediate use, a couple of routes are open to you. Bringing media in by dragging a clip or several out of the Finder onto the Fusion page Media Pool (macOS only) goes like this: 1 Pick one or more clips over in the Finder. 2 Drag those clips into DaVinci Resolve's Media Pool, or onto a bin in the Bin list. Those clips join your project's Media Pool. Leaning on the Import Media command within the Fusion page Media Pool goes like this: 1 With the Fusion page on screen, right-click anywhere in the Media Pool and pick Import Media. 2 Through the Import dialog, pick one or more clips to bring in, and click Open. Those clips join your project's Media Pool.

To dig into bringing media in through the countless capabilities of the Media page, turn to Chapter 18, “Adding and Organizing Media with the Media Pool.”

### Bins in Fusion Studio

Bins over in Fusion Studio play much the same role as the Media Pool does in DaVinci Resolve. Bins are organizing panels that give you a tidy way to reach frequently used tools, settings, macros, compositions, and media content. They hold all your custom content and resources within arm's reach, so you can call on them without digging through your hard drives. Bins can also travel across a network to smooth a collaborative workflow alongside other Fusion Studio artists.

### The Bins window

To open the Bins window: Choose File > Bins from the menu bar. As with the Media Pool in DaVinci Resolve, dropping an item into the Fusion bins forges a link between the on-disk item and the bins. Fusion makes no copy of the file in its own cache or drive space. The file holds its original format and stays put in its original spot.

### Bins Interface

The Bins window is in fact a standalone application for stashing content you might want to reach for again down the line. Two panels split the Bins window. On the left, the sidebar is a bin list where items get sorted into categories, while the right panel shows the chosen bin's content.

### The Bin list sidebar

The Bin list sorts content into bins or folders through a hierarchical List view. You're free to arrange these folders to match your workflow, though standard ones come supplied for Clips, Compositions, Favorites, Settings, and Tools. Parent folders house subfolders that carry the content. The Tools bin, for one, acts as parent folder over every category of tools. To reach subfolders, click the disclosure arrow beside the parent folder's name. Choosing a bin from the bin list throws that folder's contents up in the Contents panel as thumbnail icons.

### The Bins icon view

Running along the bottom of the bin, a toolbar opens up organization, playback, and editing controls.

### The Bins toolbar

New Folder: Spins up a fresh folder inside the current window. New Reel: Spins up an empty reel able to hold several clips cut together into a timeline. New Clip: Brings up a dialog for linking a fresh media file into a bin. Studio Player: Brings up a playback viewer for a chosen clip.

Icon/List view: This button flips between showing a bin's contents in thumbnail view and in list view. Checkerboard: Lays a checkerboard pattern over a clip thumbnail to flag transparency. Thumbnail size: Hands you a handful of preset sizes for thumbnail icons.

Right-clicking anywhere across the bin window throws up a pop-up menu reaching most of a bin's features. Right-clicking an item inside a bin shows that same menu plus extra options for renaming, playing, or deleting the item.

### The Bin Studio Player

Choose a clip inside a bin and press the Studio Player button — or just double-click the clip — and the Studio Player opens. You can lean on the Studio Player to view clips, view metadata, and jot notes.

### The Bin Studio Player

To read further about Bins, turn to Chapter 13, “Bins” in the Fusion Referance Manual.

### The Console

The Console is a window where you can watch the error, log, script, and input messages that may spell out in fuller detail something Fusion is attempting. It's likewise where you read FusionScript outputs, or feed FusionScripts in directly. Within DaVinci Resolve, you reach the Console by choosing Workspace > Console, or by choosing View > Console in Fusion Studio. A Console button also sits in the Fusion Studio User Interface toolbar. Now and then the Status bar flashes a badge to tip you off that there's a message in the Console worth a look.

### The Console window

Up top, a toolbar on the Console holds the controls that steer what the Console displays. Off to the top left, the Clear Screen button wipes the Console's contents. The four buttons after it flip the visibility of error messages, log messages, script messages, and input echoing. Limiting the view to one kind of message can help you track down what you're after when you're racing the clock at 3:00 in the morning. The three buttons beyond those let you pick the input script language. Lua 5.1 stands as the default and ships with Fusion. Python 2.x and Python 3.x call for you to set up the matching Python environment on your machine. Since scripts in the Console run right away, you can hop between input languages whenever you like. Down at the foot of the Console is an Entry field. Scripting commands typed here run in the current comp context. You enter scripts a line at a time, and they fire off immediately. For more information on scripting, see the Fusion Scripting Manual.

### Customizing Fusion

This section lays out how you can tailor Fusion to fit whatever workflow you happen to be chasing.

### The Fusion Settings Window

Fusion carries a settings window of its own, reached in DaVinci Resolve via Fusion > Fusion Settings, or inside Fusion Studio via Fusion > Preferences on macOS, while on Windows or Linux it's File > Preferences. A whole assortment of options for tailoring how Fusion works lives in that window. To read further, the place to look is Chapter 75, “Preferences,” within the DaVinci Resolve Reference Manual — or else Chapter 15 of the Fusion Reference Manual.

The Fusion Settings window set to the General panel Saving Fusion Layouts You can tailor how panels are laid out and configured to fit your desktop and monitor size, or simply to match your own taste. Within DaVinci Resolve, set up and resize whichever panels you want shown, and then: Choose Workspace > Layout Presets > Save Layout Presets.

Over in Fusion Studio, set up and resize whichever panels you want shown, and after that:

- Press the Grab Document Layout button over in the Preferences > Layout panel so the layout sticks for every new Composition.
- Press the Grab Program Layout button to hold onto where any floating views sit and how big they are, then tick the Create Floating Views checkbox so the floating windows spring back up when Fusion restarts.

### Showing and Hiding Panels

Up at the top of the screen, the UI toolbar lets you bring up the panels you need and tuck away those you don't. It's the quickest route to throwing together a layout for whatever you're after in the moment.

### The UI toolbar of the Fusion page

### Resizing Panels

You can reset each panel's overall size through preset configurations, or tune them by hand. The viewers and the Work panel run opposite one another. The more room handed to the Work panel, the less is left for the viewers. To resize a panel, drag by hand anywhere along the raised border that rings the panel's edges.

Dragging the edge between two viewers to resize it

### Fusion Studio Floating Frame

Fusion Studio ships with a Floating Frame window able to hold any panel. To drop a panel into the Floating Frame, do this: 1 Within Fusion Studio, choose Window > New Floating Frame. 2 Right-click inside the Floating Frame and pick the panel out of the Add View submenu. Across multiple monitors, you can opt to scatter floating panels over your displays for extra freedom.

### Fusion Keyboard Remapping

On the Fusion page, you can bind functions and tools to hot keys on your keyboard by choosing DaVinci Resolve > Keyboard Customization. Over in the Commands column of the Keyboard Customization window, pick Panels > Fusion Page. To read further about working with the Keyboard Customization window, turn to Chapter 4, “System and User Preferences.”

### Fusion Studio Keyboard Remapping

Inside Fusion Studio, you can bind functions and tools to hot keys on your keyboard by choosing Views > Customize Hotkeys. Two sections divide the Fusion Hotkey Manager dialog. On the left, you pick the functional area where a keyboard shortcut should go. The right side shows the keyboard shortcut, if one is set. The New button down at the dialog's foot lets you tack on a fresh keyboard shortcut.

### The Fusion Studio Hotkey Manager window

Say, for example, you'd like to pin a shortcut onto a specific node: 1 Open the Keyboard Hotkey Manager. 2 Pick Views > Effect out of the Target area of the Hotkey Manager. 3 Beneath the Key/Action area, hit the New button to begin a brand-new shortcut keyed to the Node. 4 Inside the Edit Hotkey window, hit the Tools disclosure arrow, after which you pick Blur so every Blur-related node shows. 5 Pick Glow in the Action panel. 6 Near the top of that same window, key in G as the Glow node's shortcut, then hit OK. 7 Glow paired with its G hotkey now appears over in the Key/Action area on the right. 8 Hit OK to dismiss the Manager. 9 Click inside the Node Editor and hit G, which drops a Glow node into place.

### Undo and Redo

The Undo and Redo commands let you step out of moves you've made or commands you've run, and put them back if you have second thoughts. Fusion can roll back the whole history of what you've done since you created or opened a given project. Closing a project clears its entire undo history. The next time you pick a project back up, its undo history begins fresh. For all practical purposes there's no ceiling on how many steps you can undo (though there may well be a ceiling on what you can recall). To undo or redo your changes plainly, one at a time: Choose Edit > Undo (Command-Z) to roll back the previous change. Choose Edit > Redo (Shift-Command-Z) to move forward to the next change.
