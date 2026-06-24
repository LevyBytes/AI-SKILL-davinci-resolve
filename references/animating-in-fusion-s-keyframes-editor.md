# Animating In Fusion S Keyframes Editor (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Animating in Fusion’s Keyframes Editor

The focus of this chapter is keyframing effects from within Fusion’s Inspector, plus editing clips, effects, and keyframes inside the Keyframes Editor.

### Keyframing in the Inspector

Across most effects nodes, the bulk of parameters accept keyframes, letting you build animated effects — animated transforms, rotoscoping by way of splines, warping behaviors that shift on the fly, and beyond; there is no end to the possibilities. As a convenience, a cluster of keyframing controls sits in the Inspector beside every keyframable parameter. Those controls are:

- A gray Keyframe button to the right each keyframable parameter. A click on this gray button drops a keyframe at wherever the playhead currently rests and flips the button to orange.
- Any time the playhead lands squarely on a keyframe, this button shows orange. A click on an orange Keyframe button strips out the keyframe at that frame and returns the button to gray.
- Small navigation arrows show up on the right and left when more keyframes lie in those directions. A click on the navigation arrows flanking the keyframes sends the playhead over to them.

In the Inspector, orange Keyframe buttons signal that a keyframe exists at that very frame After you have keyframed one or more parameters, provided Show Modes/Options is switched on, the node holding the parameters you keyframed shows a Keyframe badge to signal that the node carries animation. After you begin keyframing node parameters, their timing becomes editable in the Keyframes Editor and/or Spline Editor.

A keyframed node displays a Keyframe badge in the Node Editor

### Removing Animation in the Inspector

To strip a keyframed spline off a parameter: 1 On the parameter whose animation you wish to drop, right-click its keyframe control. 2 From the contextual menu, pick Remove [Name of parameter].

### Attaching a Parameter to an Existing Animation Curve

You can tie several parameters to one shared animation curve. That can be a priceless time-saver when you are animating different parameters in a node identically. To wire a second parameter onto that same animation curve: 1 Give the second parameter you mean to attach a right-click. 2 Within the contextual menu, hover over the Connect To submenu. 3 Out of the Connect To submenu, pick the animated parameter by name.

### Keyframes Editor Overview

At its core the Keyframes Editor is a timeline-style view of your composition, where every clip and effect node in that composition shows up as a track. The color coding on these tracks matches the nodes they stand for, and they carry labels where it makes sense. Across the top a Time Ruler conveys your composition’s timing, while a range of controls let you govern what the Keyframes Editor holds. There are two jobs the Keyframes Editor handles:

- To set the timing of a project’s elements, be they clips or effects. You can trim, slide, and stretch clips, set the timing of an animation spline, or trim how long an effects node runs. The order of nodes in the Timeline is yours to reshuffle freely without disturbing your composition’s layering order. Every compositing operation lives in the Node Editor, whereas the Keyframes Editor looks after your composition’s timing.
- To build and/or revise keyframes you have applied to effects in a track-based fashion, you can retime keyframes, add and remove keyframes, and even change keyframe values

### The Keyframes Editor

To show the Keyframes Editor, do one of the following:

- Click the Keyframes Editor button in the UI toolbar to flip the Keyframes Editor’s visibility on or off.
- Press F7 on the keyboard.

### Keyframes Editor Tracks

Although a track stands in for every clip and effect node in your composition, keyframed parameters surface in one of two ways — either as keyframes laid over the track they belong to (as you see on the MOVEMENT track), or split out onto tracks of their own for finer editing, one keyframe track for each keyframed parameter, by clicking a disclosure control left of that track’s name in the Timeline header (as you see beneath the “Drip1” track).

### The Timeline tracks

### The Timeline Header

Sitting on the Timeline’s left side, the Timeline header area is a hierarchical roster of every track in a composition. Each track shows the name of the node it belongs to, a lock button, and a disclosure control that reveals keyframe tracks for each keyframe animation, modifier, and mask attached to it.

### Collapse/Open All

One fast route to opening or closing every available keyframe track in one go is the Expand/Collapse Tool Controls commands found in the Keyframe Timeline Option menu.

### The Timeline header area

### The Playhead

Just as it does throughout Fusion, the playhead shows up as a red vertical bar cutting across the Timeline view to mark where the current frame or time sits. Because the Keyframes Editor playhead is tied to the viewer playhead, the image in front of you stays in sync.

The playhead about to be dragged by the pointer

Dragging the playhead requires clicking it directly, the Timeline ruler included (click and drag anywhere else on the Timeline ruler and you scale the Timeline instead). On top of that, you can send the playhead straight to a new spot by holding the Command-Option keys while clicking in the track area (not the Timeline ruler).

### Spreadsheet

Switch on the Spreadsheet, then click a layer’s name in the keyframe track, and each keyframe’s numeric time position and value (or values, for a multi-dimensional parameter) turn up as entries within the Spreadsheet cells. One keyframe occupies each column, while one facet of each keyframe occupies each row. As an example, while you animate a blur, the Key Frame row reports the frame on which each keyframe sits, and the Blur1BlurSize row reports the blur size at each keyframe. Alter the Key Frame value of any keyframe and you shift that keyframe onto a different frame of the Timeline.

### Editing keyframes in the Spreadsheet

### Scaling and Panning the Timeline

Across the top, a row of zoom and framing controls lets you reshape the work area that holds the layers.

### The Keyframe Editor framing controls

A Horizontal zoom control lets you resize the editor. A Zoom to Fit button sizes the width of every track to match the Keyframes Editor’s current width. A Zoom to Rect tool lets you sketch a rectangle that marks out which region of the Keyframes Editor to magnify. Ordering or filtering the tracks in assorted ways is the job of a Sort pop-up menu. An Option menu opens the door to many further ways of filtering tracks and steering which options are visible.

### Working with Segments in the Timeline

The lion’s share of Timeline work comes down to trimming and lining up clip segments. Picking a single segment in the Timeline can be done in either of these ways:

- Click the node’s name in the header.
- Click the node’s segment in the Timeline.

To add another segment to the selection, do one of the following:

- Hold Command and click further segments to build discontiguous selections.
- Pick a segment, then hold Shift and click a second segment to make a contiguous selection spanning everything between.

To remove a segment from the selection, do the following:

- Hold Command and click a selected segment to drop it from the selection.

TIP: Picking a node’s name from the Timeline header likewise selects that node’s tile in the Node Editor, with its controls shown in the Inspector.

### Moving Segments in the Timeline

To reposition a segment, drag on the node’s segment within the Keyframes Editor. The cursor takes on the look of a bar with arrows pointing both ways. Moving a segment shifts where that clip starts and stops in the composition.

### The Move cursor

### Trimming Segments

Trimming segments plays out differently on Loaders, MediaIn and Effect nodes:

- Trimming a Loader or MediaIn node parallels trimming clips in an editing application, since you are reshaping the in and out points of the media range that clip lends to your composition.
- Trimming an effect node’s segments instead reshapes how far that node’s effect reaches in the composition. Beyond the trimmed region, that effect node acts as though it were switched off.

TIP: Cutting back how long effects nodes run can streamline processing. Picture a Loader or MediaIn node standing for a clip that runs 100 frames long and feeds a Defocus node animated across frames 80–100. There is barely any payoff in processing the defocus node across frames 0–79, so trimming the defocus segment so that it opens at frame 80 in the Timeline effectively keeps it from rendering and eating either memory or processor time until it is actually needed.

To trim a segment in the Timeline, do the following:

- Drag on either end of the node’s segment in the Timeline. Once the cursor reaches the right spot to trim, it becomes a vertical bar carrying a single arrow.

### The Trim cursor

### Holding the First or Last Frame

To freeze a clip on a Loader’s opening or closing frame for a chosen number of frames — what is called a freeze frame — hold Command while dragging past the segment’s first or last edge in the Timeline.

### Working with Keyframes in the Timeline

There are two ways keyframes get drawn. With keyframe tracks closed, they appear over the node’s segment. Clicking the disclosure icon left of the node’s name in the track header opens the display so each keyframed parameter gets a track of its own in the Timeline, making precise editing possible. Beyond that, each keyframe track — open or closed — carries a miniature curve overlay that visually conveys how the keyframed values rise and fall. You cannot edit this little overlay directly.

Here the Drip1 segment shows its keyframe tracks opened out, whereas the Text1 segment keeps its keyframe tracks folded down so that they sit inside the segment.

### Drag and Drop Keyframe Editing

Below are pointer-driven keyframe editing approaches to get you going. Ways to select keyframes:

- Click a single keyframe to select it.
- Drag a bounding box across a string of keyframes to grab them all.
- Command-click to pick out discontiguous keyframes.
- Shift-click the first and last keyframe of a range to capture a contiguous range.

Ways to adjust keyframes:

- Keyframes can be dragged left and right to shift them in time.
- Right-click one or more selected keyframes and lean on contextual menu commands to alter keyframe interpolation, copy/paste keyframes, or even spawn new keyframes.

### Keyframe Editing Using the Time Editor

Down at the lower right of the Keyframes Editor, a drop-down paired with an editing field lets you numerically edit any selected keyframe’s timing, in frames, making precise tweaks simple. Shifting a keyframe’s position by way of the toolbar can be done in any of these ways:

- Pick a keyframe, then type a fresh frame number into the Time Edit box.
- From the Time Editor drop-down pick T Offset, select one or more keyframes, then type a frame offset.
- From the Time Editor drop-down pick T Scale, select one or more keyframes, then type a frame offset.

For relocating keyframes, the Time button can be flipped over to Time Offset or Time Scale.

### The Keyframe Spreadsheet

Switch on the Spreadsheet, then click a layer’s name in the keyframe track, and each keyframe’s numeric time position and value (or values, for a multi-dimensional parameter) turn up as entries within the Spreadsheet cells. One keyframe occupies each column, while one facet of each keyframe occupies each row.

### Editing keyframes in the Spreadsheet

As an example, while you animate a blur, the Key Frame row reports the frame on which each keyframe sits, and the Blur1BlurSize row reports the blur size at each keyframe. Alter the Key Frame value of any keyframe and you shift that keyframe onto a different frame of the Timeline.

### Duplicating Spline Keyframes

Keyframes can be copied, whether onto the very same keyframe track or onto other tracks. That can spare you time when you need to repeat a keyframe sequence elsewhere on the same segment, or simply to set up keyframes with matching timing on two separate segments. Here is how to duplicate keyframes: 1 Pick the keyframe or keyframes you want copied. 2 With Command held down, drag any one of those selected keyframes over to a new position.

### Time Stretching Keyframes

Select a range of keyframes within a keyframe track and you can switch on the Time Stretch tool at the lower left of the Keyframes Editor, which brings up a box for squeezing and stretching the whole range of keyframes against one another — reshaping the overall timing of a keyframe sequence while holding onto the relative spacing from one keyframe to the next. As an alternative, switch on Time Stretch and draw a bounding box around the keyframes you intend to adjust to set up a time-stretching boundary that way. Click the Time Stretch tool once more to switch it off.

### Time stretching keyframes

### Showing Keyframe Values

When a node and the segment that goes with it carry animated parameters, keyframes show up as colored tick marks in keyframe tracks to flag where animated changes happen. With the tracks and splines open on a parameter, picking Show Values from the Keyframes Editor Option menu surfaces editable fields under each keyframe. Those fields display each keyframe’s present value and let you edit it simply by typing a new number.

### Show values from the Keyframes Editor Option menu

### Timeline Filters

As a composition swells to hundreds of nodes, pinning down particular node layers can soon turn awkward. You can build and apply Timeline filters to weed out nodes that the current operation does not need. The Global Timeline preferences ship with a handful of ready-made filters you can switch on, or you can fashion new ones whenever you like. To use a Timeline filter: Open the Keyframes Editor Option menu and pick an item from the menu’s top. Default Timeline filters include;

- Show All, which reveals every node layer in the current composition.
- Show None, which conceals all layers.
- Show Tools at Current Time, which only shows node layers sitting under the playhead.
- Any custom filters you have built turn up here too, in alphabetical order.

To return to displaying it all: From the Keyframes Editor Option menu pick Show All, and every layer comes back into view.

### Choosing a Timeline filter

To build a Timeline filter: 1 From the Keyframes Editor Option menu, pick Create/Edit Filters; this opens the Timeline panel within the Fusion Settings window. That panel is where new Timeline filters get made.

The Global Timeline preferences for enabling filters 2 Press the New button, give your new filter setting a name, and press OK. Up at the top, the filter you just made now sits selected in the Filter pop-up menu. 3 Through the “Settings for filters” list, tick the checkboxes for nodes you want visible and untick the checkboxes for nodes you want screened out. Whole categories of node can be switched on and off, or you can open a category’s disclosure control to flip individual nodes on and off. A press of Invert All instantly switches off every node category. 4 Once your filters are done, press the Save button to dismiss the Fusion Settings window. Whatever filters you have made inside the Timeline panel of the Fusion Settings window then show up in the Keyframes Editor Option menu.

To remove a filter: 1 From the Keyframes Editor Option menu, pick Create/Edit Filters; this opens the Timeline panel within the Fusion Settings window. That panel is where Timeline filters get deleted. 2 Out of the Filter pop-up menu, pick the filter you want gone. 3 Press the Delete button, and once a dialog checks whether you truly mean it, press OK.

### Selected Filtering

Picking “Show only selected tools” from the Keyframes Editor Option menu screens out every segment apart from the layers matching the selected nodes. You can switch this option on or off. TIP: With “Show only selected tools” turned on, you can go on selecting nodes in the Node Editor to refresh what the Keyframes Editor shows.

### Sorting in the Timeline

The top-to-bottom order in which nodes appear in the Timeline is yours to change.

- The Tree Item Order Selection menu lets you order the tracks by a number you assign.
- The Sort pop-up menu is another option.

### The Tree Item Order Menu

Right-clicking over any track in the Keyframes Editor brings up a contextual menu carrying the Tree Item Order Selection submenu. Picking Start from the submenu lets you begin numbering each item in the track header by clicking on them. Your first click marks an item #1, your second #2, your third #3, and onward. After every item has been clicked in the sequence you want for the Keyframes Editor, give a track a right-click and, out of the Tree Item Order Selection submenu, pick End. The items then line up by the numbers you assigned, with #1 riding above #2, which rides above #3, and so on. The very first items in the Keyframe track list will always be the nodes forming the root of the node tree. After those root nodes, the numbered nodes follow in order. As an example, if the node tree opens with a background node and then runs into a Fast Noise, Blur, and Color Corrector, the background node will always sit at the top of the Keyframes Editor track list, since it is the root node.

### The Keyframes Editor Tree Item Order Selection menu

Should you start numbering nodes in the track header and then reconsider or settle on a different order, you can pick Restart to begin the numbering afresh or pick Cancel to keep the current order.

### The Sort Menu

The Sort menu rearranges how each node’s layers show up in the Keyframes Editor. Returning the menu to All Tools lays them out in linear order, sweeping the Node Editor left to right and top to bottom. This is the default setting.

### The Timeline Sort Order menu

- All Tools: Compels every tool presently sitting in the Node Editor to show up within the Keyframes Editor.
- Hierarchy: Orders things with the most background layers up at the header’s top, running down to the most foreground layers at the bottom, tracing the node connections in the Node Editor.
- Reverse: The flip side of Hierarchy, working back from the final node in the Node Editor toward the most background source node.
- Names: Orders the nodes alphabetically, opening at the top with the start of the alphabet.
- Start: Arranges layers by where they begin in the composition. Nodes beginning earlier in the Global project time sit at the header’s top, while nodes beginning later fall to the bottom.
- Animated: Holds the Timeline to animated layers alone. This mode shines when you are tuning the timing of animations across several nodes at once.

### Markers

Markers serve to flag key frames in a project that could bear on how you keyframe animation. They might pinpoint the frame where a dragon breathes fire at a protagonist, the instant someone steps through a portal, or any other crucial frame in a composition you need to keep tabs on. Markers placed on the Timeline in the Cut, Edit, Fairlight, or Color page surface in the Keyframes Editor and Spline Editor of the Fusion page. While you work in Fusion Studio or the Fusion page, the Keyframes Editor or the Spline Editor lets you add them as well. Within Fusion, a selected marker appears as a small handle with a line running vertically through the graph view.

### A marker being moved in the Keyframed Editor

Here is how to create a marker: at a frame on the Keyframes Editor’s Timeline Ruler, right-click and pick Add Marker out of the contextual menu. A marker’s position is its most vital attribute. To be worth anything, a marker has to land on the frame you meant it for. Hovering the cursor over a marker pops a tooltip reporting its current frame position. Should it land on the wrong frame, dragging it along the Time Ruler will reposition it. Markers placed on the Time Ruler stay editable in the Fusion page, and the edits flow back into the other DaVinci Resolve pages. From within Fusion’s Keyframes or Spline Editor, Time Ruler markers can be added, moved, deleted, renamed, and tagged with descriptive notes. NOTE: Markers tied to clips in the Edit page Timeline show up on MediaIn nodes in Fusion’s Keyframes Editor yet cannot be edited there. They do not appear in the Spline Editor.

### Jumping to Markers

A double-click on a marker sends the playhead to that marker’s position.

### Renaming Markers

By default a marker carries the frame number in its name, but you can hand it a more descriptive name alongside the frame number to make it easier to spot. To rename a marker in Fusion, right-click over the marker and pick Rename Guide from the contextual menu. Type a name into the dialog and click OK.

Right-clicking over a marker, or over the Keyframe Editor Time Ruler, brings up the Marker contextual menu.

### Show Marker List

You can use markers to leap to particular spots in a composition by way of the Marker List. Right-click over a marker or inside the Keyframe Editor Time Ruler to summon the contextual menu, and you can pick Show Marker List, or press Shift-G, to bring up the Marker List dialog. The Marker List is a floating dialog that stays above the main window until you close it. The Marker List presents every current marker in the composition, ordered by their position in time along with whatever custom name you gave them. Double-click a marker’s name in the list and the playhead leaps to the marker’s location.

By way of markers, the Marker List dialog lets you move around within a composition. A pair of checkboxes sits beside each marker’s name. One belongs to the Spline Editor, the other to the Keyframes Editor. By default markers appear in both the Spline Editor and Keyframes Editor, but you can clear the relevant checkbox to hide the markers in that view.

### Deleting Markers

To delete a marker, drag it upward past the Time Ruler and let go of the mouse. You can also reach for the marker’s contextual menu and pick Delete Marker.

### Autosnap

To place keyframes and a segment’s start and end precisely while you drag in the Timeline, you can have them snap onto a field, onto a frame, or onto markers. Inside the Options section of the Keyframes Editor’s contextual menu sits the Autosnap option. Two submenu options come with autosnapping. The first dictates how snapping works while you drag keyframes, control points, or a segment’s opening and closing edges. The second dictates how markers snap.

### Autosnap Points

As you drag keyframes or the edges of segments, you often want them to land on a particular frame. By default Autosnap pins the placement of keyframes and segment edges to frame boundaries, but the contextual menu offers other choices. To configure autosnapping for keyframes and segment edges, right-click somewhere within the Keyframes Editor and choose Options > Autosnap Points off the contextual menu. The Autosnap Points submenu then appears, carrying choices that govern how snapping behaves. Those choices are:

- None: With None, keyframes and segment edges may be placed freely at subframe precision.
- Frame: With Frame, keyframes and segment edges are pulled onto the closest frame.
- Field: With Field, keyframes and segment edges latch onto the closest field — that being 0.5 of a frame.
- Guides: Once switched on, keyframes and segment edges latch onto markers.

### Autosnap Markers

When you click to make a fresh marker, its default behavior is to snap to the nearest frame. Reposition that marker and it likewise snaps to the closest frame as you drag. This behavior can be changed via the Keyframes Editor’s contextual menu, picking from within the Options > Autosnap Markers submenu. The choices are:

- None: Markers may sit anywhere at subframe precision.
- Frame: With Frame, every marker is pulled onto the closest frame.
- Field: With Field, every marker latches onto the closest field.

### The Spreadsheet Editor
