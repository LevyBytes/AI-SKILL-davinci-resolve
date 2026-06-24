# Animating In Fusion S Spline Editor (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Animating in Fusion’s Spline Editor

These pages walk through keyframing effects and steering animations inside Fusion’s Spline Editor.

### Spline Editor Overview

The Spline Editor stands as the chief workspace for reshaping and polishing animation. Your main use for it is to render how parameters’ values shift over time, drawn as splines. Where Keyframes plainly pin a parameter’s value to a particular frame, Splines are the lines or curves that interpolate values across keyframes. Set a keyframe on a parameter and a spline springs into being, ready to appear in the Spline Editor where you can fine-tune the animation further. The Spline Editor, though, outdoes an ordinary curve editor, since it can also lay out functions that may be no splines at all, such as characters shifting inside a text string or the mathematical expressions steering your animations.

### The Spline Editor with three animated parameters

### What Are Splines?

Every animation rests on splines that trace a parameter’s value at any moment in time. Across the Spline Editor graph, the comp’s time runs along the horizontal axis while the parameter’s value runs along the vertical one. Picturing animation as splines, rather than as keyframes the way the Keyframes Editor does, pays off because splines let you work the interpolation that sits between keyframes. Suppose a parameter holds a keyframe valued at 1.0 on frame 1, then a keyframe valued at 10.0 on frame 10, after which the values in between get smoothly interpolated, computed from the spline’s shape. The functions and controls within the Spline Editor hand you remarkable command over that interpolation.

### Spline Editor Interface

Out of the box the Spline Editor stays hidden, yet a click of the Spline button on the user interface toolbar reveals it whenever you like. Another route: in the Node Editor right-click a node, or in the Keyframes Editor right-click a segment, then pick Edit Splines from the drop‑down menu. You can keep the Spline Editor open beside the Node Editor or Keyframes Editor, or set it apart so it fills the whole work area.

### The Graph, Header, and Toolbar

Three principal working areas make up the Spline Editor: the graph, header, and toolbar. Along the Spline Editor’s left edge sits the header, presenting a list of animated parameters. Most of the panel goes to the splines shown in the graph area, with a toolbar stretched across the bottom that offers assorted ways to work the splines.

### Graph

The graph claims the most space in the interface. Here is where you view and edit the animation splines. Two axes span the graph: the horizontal one stands for time, the vertical one for the spline’s value. A slim bar known as the playhead travels down through the graph to mark the current time, much as it does in the Timeline Editor. Drag the playhead and the current time shifts, refreshing whatever frame the viewers show. Stripping a spline off a parameter takes the animation away with it Spline Editor Header The header gives you a way to decide which splines show up in the graph. It lists each spline in the project under the tool that holds that parameter. Next to every name a checkbox signals whether that spline is on display in the graph and whether it can be edited.

### The Spline header

### Spline Editor Toolbar

Running along the foot of the Spline Editor, the toolbar gathers the operations most often performed on an animation spline. Every operation it carries is reachable from the graph’s context menu too, but these buttons offer a quicker shortcut.

### Spline toolbar buttons

### Playhead

The playhead is that slim red vertical bar passing down through the Spline Editor graph to stand for the comp’s current time. Drag it and the current time changes.

### Status Bar

Down in the Fusion window’s lower-right corner, the status bar steadily reports where the pointer sits, together with the time and value axes.

### Contextual Menus

Two contextual menus can be reached from the Spline Editor. A right-click over the graph brings up the Spline contextual menu, whereas a right-click on the Time Ruler above the graph brings up the Guide contextual menu.

Right-click on the horizontal axis Time Ruler for the Guide menu

### Renaming Splines

Whatever a spline is called in the header takes after the parameter it drives. To rename a spline, right-click it within the header and pick Rename Spline from the contextual menu.

### Changing Spline Colors

Every spline in the graph gets its own distinct color, which makes telling them apart simpler whenever several are on screen together. While a spline is active, a round color swatch shows up beside that spline’s name in the header. To recolor a spline: 1 Click the color circle sitting next to the spline name in the header. 2 Or right-click that spline’s name in the header and pick Change Color from the contextual menu. 3 Pick the new color out of the dialog box that opens and click OK.

### Navigating Around the Spline Editor

Often enough you’ll need to zoom and pan about the graph area so the splines you mean to work on stay in view. By and large, scaling and panning the Spline Editor behaves just as it does throughout the navigable corners of the Fusion interface. Even so, the Spline Editor brings a handful of its own functions for governing your view by the height, width, and selection of several animation splines. The plainest navigation tools to reach for are the scale sliders and buttons up in the top left of the Spline Editor panel.

For moving about the graph you have the Zoom Height slider, the Zoom Width slider, the Fit button, and the Zoom to Rectangle button To scale and pan with the sliders and buttons: The Zoom Height and Zoom Width sliders resize the graph area’s height and width. The Fit button tries to rescale the view so that every active spline fits inside the graph. The Zoom to Rectangle button (Command-R) lets you draw a bounding box over the patch of graph you’d like centered and scaled. To scale by the axis labels: Rest the mouse pointer on whichever ruler, horizontal-axis or vertical-axis, then drag to resize the graph along that axis alone. The scaling centers on wherever the pointer first sat on the ruler.

Dragging within the Time Ruler scales the graph horizontally To scale and pan via the mouse and/or keyboard:

- With the Spline Editor active, tap the + and - keys on your keyboard to zoom the graph in and out.
- You can likewise zoom onto a particular control point by holding the Command key and rolling the middle mouse wheel. Wherever the mouse pointer rests sets the area that magnifies.
- Rest the mouse pointer over the graph, then hold the middle mouse button down. While that middle button stays pressed, a single left-button click zooms in and a single right-button click zooms out.

To pan the graph area:

- Drag leftward or rightward with the middle mouse button, or lean on the scroll bar along the graph’s bottom and right edges.

Using the Graph contextual menu to navigate: The Spline Editor contextual menu opens up several more ways to move about the graph area.

- Choose Scale > Scale to Fit (Command-F) to tuck every active spline into the graph area.
- Choose Scale > Scale to Rectangle (Command-R) to drag a bounding box around the patch of graph

you’d like centered and scaled. The result matches clicking the Zoom to Rectangle button.

- Choose Scale > Default to return the graph area’s scaling to its default values.
- Choose Scale > Zoom In/Zoom Out to scale the graph area. It carries out the same job as

tapping the + and - keys on the keyboard.

- Choose Scale > Auto Fit to have the graph rescale on the fly to hold every spline as you show splines

and hide them. Change the scaling while Auto-Fit is on and the graph area scrolls along as the comp plays so all the keyframes stay in view.

- Choose Scale > Auto Scroll to make the graph area scroll whenever, during playback, the splines drift past the graph horizontally.
- Choose Scale > Manual to switch off every automatic effort to keep splines shown in the graph.
- Choose Options > Fit Times to scale the X-axis on its own so the selected spline fits. Every visible spline counts toward this, not the freshly selected one alone. Leave this option off and bringing up a new spline won’t alter the horizontal scale.
- Choose Options > Fit Values to scale the Y-axis on its own so the selected spline fits. Every visible spline counts toward this, not the freshly selected one alone. Leave this option off and bringing up a new spline won’t alter the vertical scale.

### Markers

Markers serve to flag frames that matter within a project. One might point to a frame where a ray gun fires a beam in the scene, the instant somebody steps through a portal in the image, or any other notable event in the composite. A marker dropped onto the Timeline on the Cut, Edit, Fairlight, or Color page turns up in the Fusion page’s Keyframes Editor and Spline Editor. Markers can be placed from the Keyframes Editor or the Spline Editor as well, whether you’re in Fusion Studio or on the Fusion page. They line up along the top of the Spline Editor’s horizontal-axis Time Ruler. Drawn as small blue shapes, each, once selected, sends a line straight down through the graph. NOTE: Markers fastened to clips on the Cut, Edit, Color, or Fairlight pages Timeline stay invisible in Fusion’s Spline Editor.

Markers left unselected sit along the top as blue shapes, while a selected one casts a vertical line down through the graph

### Working with Markers

A marker draws the eye to one particular frame inside a comp. Markers can be named, shown in a list, and edited. Once they’re in place, you can readily hop the playhead from one to the next, reposition them, or remove them entirely. To create a marker:

- Right-click within the horizontal axis Time Ruler and pick Add Marker.

A right-click in the horizontal time axis is how markers get added To delete a marker, do one of the following:

- Drag the marker upward, clear of the Spline Editor panel.
- Right-click the marker, then pick Delete Marker from the menu.
- Pick the marker, then press Delete or Backspace on the keyboard.
- Within the Marker List, pick a guide from the list and click the Del button.

To shift a marker onto a new frame, do one of the following:

- Drag the marker handle along the time axis.
- Right-click in the marker area and pick Options > Enable Marker Grab, then drag the marker’s vertical line to reposition the guide.

To send the Playhead to a marker:

- Right-click a marker and pick Set Current Time To [Frame number].

### Using the Marker List

The Marker List rounds up every marker in the present comp. It can present markers from the Keyframes Editor, from the Spline Editor, or from both panels at once. Click a guide’s frame number or name and the current time jumps to that marker’s frame. Being a floating window, the Marker List can stay open, letting you dash between different markers as you work in the Spline Editor. To show the Marker List:

- Right-click within the horizontal axis and pick Show Marker List, or press Shift-G.

Any markers already in the comp turn up in the Marker List on their own, no matter whether they came from the Keyframes Editor, the Spline Editor, or another page in DaVinci Resolve. Markers can also be added straight from the Marker List, which helps when several need adding and their timing is roughly known to you. Adding a guide from there runs thus: 1 In the Marker List window, click the Add button. 2 Type a frame number into the Time field. 3 Press Tab or click the Close button to shut the Marker List. To name a marker, do one of the following:

- Within the Marker List, double-click the Name column, just right of the frame number, and type a name for the marker.
- Right-click a marker in the horizontal axis and pick Rename Marker. In the dialog that opens, type a name for the marker.

### Displaying Marker with the Timeline

Beside each marker, the Marker List window carries checkboxes that set whether that marker shows in the Spline Editor, the Keyframes Editor, both, or neither. Fresh markers start out active across both panels. To keep a marker out of one panel, clear the matching checkbox.

### Autosnap

To help you place keyframe control points exactly along the horizontal (time) axis, the Spline Editor’s Autosnap function can be switched on. Right-click a spline and pick Options > Autosnap Points to open a submenu of four choices.

- None: Lets keyframes sit anywhere, even between frames.
- Frame: Keyframes snap onto the closest frame.
- Fields: Keyframes snap onto the closest field.
- Markers: Keyframes snap onto the closest marker.

### Autosnapping and Markers

Out of the box, a freshly made marker snaps onto the closest frame. Dragging markers with the mouse snaps them onto the current frame as well. To alter this behavior, pick Options > Autosnap Markers > None, or pick Options > Autosnap Markers > Field, from the contextual menu.

### Creating Animation Splines

An animation spline comes into being on its own the moment you keyframe a parameter in the Inspector or the Keyframes Editor. Yet you can bring an animation spline to life without laying down a keyframe first. To create a spline: Right-click the parameter you mean to animate in the Inspector, and pick Animate from the contextual menu.

Picking Animation from the menu puts a spline up in the Spline Editor Choosing Animate from the contextual menu ties the parameter to the default spline type. That’s typically a Bézier Spline, unless you swap the default spline out in the Defaults panel of the Fusion Preferences.

### Deleting Animation Splines

To strip an animation spline off a parameter, right-click that control in the Inspector and pick Remove [tool parameter’s name] from the contextual menu. Pulling a spline off a parameter actually deletes it only when no other tool in the composition is hooked to that same spline at the time.

Removing a spline from a parameter removes the animation

### Animating with Different Spline Types

Unless the Preferences say otherwise, a Bézier spline is the default. Should you want some spline type other than Bézier for the animation curve, you can pick that spline type from the Modify With contextual submenu before you set down any keyframes.

### Three spline types in the Modify With menu

- Bézier Spline: The Bézier spline is the default curve type. At every keyframe on the spline, three points set how smooth the curve runs. The first of them is the keyframe proper, standing for the value at a given moment. The remaining two act as handles that govern how smoothly the curve gets drawn for the segments leading into and out of the keyframe. Bézier ranks as the most-used spline type, since a Bézier spline lets you mix curves and straight lines together.

### Bézier spline

- Modify with > B-Spline: A B-spline leans on one lone point to set the curve’s smoothness. Rather than handles, a single control point fixes both the value and how smooth the curve is. Hold the W key while dragging the control point left or right to tune the curve’s tension.

### B-spline

- Modify with > Cubic Spline: A Cubic spline resembles a Bézier in that the spline runs through the control point. Cubic splines, however, show no handles and always form the smoothest curve they can. On that count they’re akin to B-splines. This spline type sees use almost never.

### Cubic spline

- Modify with > Natural Cubic Spline: A Natural Cubic spline behaves much like a Cubic one, save that its changes stay more confined. Adjusting a single control point leaves other tangents untouched beyond the neighboring control points on either side.

### Natural Cubic spline

### Working with Keyframes and Splines

After you’ve animated a parameter and brought up the Spline Editor, the spline’s keyframes, and with them the animation, can be worked in all manner of ways. Selecting Keyframe control points lets you move, copy, and reshape the interpolation of your animation.

### Adding Keyframes

Once a first keyframe exists, more keyframes get tacked onto a spline on their own each time you move the playhead and alter the value of that spline’s parameter. Change the strength of an animated glow at frame 15, for instance, and a keyframe carrying the new value lands on frame 15. Within the Spline Editor, you can also drop control points straight onto a spline by clicking it wherever the new keyframe should go.

Adding Keyframes at the Playhead To set a fresh keyframe at the playhead’s present spot, press Command-K on the keyboard, or right-click in the graph and pick Set Key, and a keyframe appears beneath the playhead. Adding Equal Keyframes To hold a value across several frames, right-click in the graph area and pick Set Key Equal To, which opens a submenu for adding a new keyframe set equal in value to either the previous or the following keyframe. To keep a value steady across a pair of keyframes, choose from that Set Key Equal To submenu

### Locked and Unlocked Controls Points

Animate the Center X/Y or Pivot X/Y parameters on any tool and you bring a displacement spline into the Spline Editor. That displacement spline stands for the animated object’s relative offset position as it travels its path. Because the displacement spline works in relative terms, each of its keyframes lands on a value from 0.0 up to 1.0. Where the Spline Editor reads a displacement of 0.0, the object sits right at a path’s start. Read 1.0 and the object rests at the path’s end.

The displacement spline represents the relative position along a motion path

A displacement path is built from locked and unlocked points. How you added a point to the polyline decides whether it’s locked. A locked point on the spline carries a matching point in the viewer’s motion path, whereas an unlocked point has no counterpart in the viewer’s motion path. Each behaves in its own way, laid out below. TIP: You can turn displacement splines into X and Y coordinates by right-clicking the motion path in the viewer and picking Path#: Polyline > Convert to X/Y Path.

### Locked Points

A locked point is the motion path’s counterpart to a keyframe. You make one by shifting the playhead’s position and altering the parameter value. Such points dictate that the animated object has to occupy a set position on a set frame. Since these keyframes bear only on position along the path, they can travel solely in the horizontal direction across the spline’s time axis. In the Spline Editor, locked points show up as larger lock icons. Every locked key carries a matching point on the viewer’s motion path. Delete a locked point and the overall timing of the motion shifts.

### Unlocked Points

An unlocked point comes from clicking right on the spline in the Spline Editor. Points like these grant extra say over the acceleration along the motion path while leaving the path itself alone. Going the other direction, you can drop unlocked points in the viewer to shape the motion path without touching the timing. To turn an unlocked point into a locked one, or the reverse, select the point(s), right‑click, and pick Lock Point from the contextual menu. For more on motion paths and locked keyframes, the DaVinci Resolve manual covers them across Chapters 71 and 73 while the Fusion Studio manual does so across Chapters 8 and 10.

### Selecting, Moving, and Deleting Keyframes

Where you put keyframes does much to shape the style of the animation. Through the graph, you can pick keyframes and shift them up or down to alter their value, or left and right to alter the timing. Keyframes copy and paste across splines and parameters. Ways to select keyframes:

- Click a keyframe right where it sits on the spline, or rope it inside a dragged bounding box.
- Drag a bounding box wide enough to take in several keyframes to grab more than one at a time.
- To toss a keyframe into or out of the current selection, hold the Command key as you select keyframes. That drops the keyframes already selected and picks up the ones not yet selected.
- Press Command-A, or right-click in the graph area and pick Select Points > Select All from the contextual menu, to grab every keyframe across the active splines.

### Moving Keyframes

Keyframes move freely under the mouse, the keyboard, or the edit point controls. They can even slide past existing points while you move them. Say keyframes sit on frame 5 and frame 10, with the one at frame 5 then carried out to frame 15. To move keyframes with the mouse:

- Drag the selected keyframe to its new place in the graph. With more than one keyframe selected, all of them travel together.
- Hold the Option key before you start dragging the keyframe to pin its motion to a single axis.

To move keyframes with the keyboard:

- The Up and Down Arrow keys nudge the keyframes’ value a little at a time.
- How far each key press shifts the value vertically follows the graph’s current scale. The tighter your zoom on the spline, the finer the adjustment.
- Hold the Shift key as you press the Up or Down Arrow keys to step the value in bigger jumps.

To move keyframes via edit fields:

- The Value and Time Editors live at the far right of the toolbar. Into these number fields you can type exact values for the selected keyframes. These controls get a fuller treatment further on in this chapter.

To delete one or more keyframes:

- With one or more keyframes selected, hit Delete or Backspace on the keyboard. That clears only the keyframes; the spline stays, even once it holds no keyframes. To get rid of the spline, right-click the parameter in the Inspector and pick Remove [parameter name].

### Showing Key Markers

By turning to the key markers, you can retime the keyframes without bothering to handle splines at all. The horizontal time axis is able to display markers pointing out where each keyframe sits. To switch these markers on, right-click in the graph and pick Show > Key Markers from the contextual menu, or click the Show Key Markers button on the toolbar.

In the horizontal axis, the key markers depict keyframes in the same color the splines wear

### Copying and Pasting Keyframes
