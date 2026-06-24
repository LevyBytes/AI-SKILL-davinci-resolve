# Animating In Fusion S Spline Editor (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

When you need animation to line up exactly, you can copy Keyframes over to a fresh spot on the same spline, or onto entirely separate splines and different tools. The graph’s contextual menu offers two ways to copy keyframes. Picking Copy Points (Command-C) grabs every selected point. Picking Copy Value grabs a lone point that the pointer identifies out of several selected points. Doing so leaves your selection set intact, so you’re free to pull out numbers as you go. To copy and paste points to a fresh spot on the same spline: 1 Select the keyframes you want on the spline. 2 Right-click over the spline and pick Copy Points from the contextual menu, or hit Command-C. 3 Click an empty part of the graph to clear the selection on all the copied points. 4 Bring the playhead to the part of the spline where the points should land and hit Command-V. Or else, hover the pointer over the spline at the paste spot, and once the spline highlights, right-click and pick Paste Points/Value. As another option, you can copy and paste keyframes by dragging them with the mouse. Once the points are selected, hold the Command key down and drag them along the spline to the destination. To copy and paste keyframes from one spline onto another: 1 Make a single spline the active visible spline and select the keyframes you want on it. 2 Right-click over the spline and pick Copy Points from the contextual menu, or hit Command-C. 3 With the status checkbox by that spline’s name in the header, switch it to viewed or disabled. 4 Promote the destination spline to active visible spline, after which you pick the keyframe on it where the new keyframes belong. 5 Right-click and pick Paste Points/Value, or hit Command-V. From a cluster of selected points, you can lift a single point’s value. Because this routine keeps the selected set intact, you can keep pulling values as needed without reselecting points. To copy and paste a keyframe value: 1 Turn a single spline into the active visible spline and select every keyframe on it. 2 Right-click over a lone point and pick Copy Value from the contextual menu. 3 Using the status checkbox by that spline’s name in the header, set it to viewed or disabled. 4 Now turn the destination spline into the active visible spline, then pick the keyframe on it where the new keyframe belongs. 5 Right-click and pick Paste Points/Value, or hit Command-V. You can also paste keyframes with an offset, which lets you reproduce a spline shape while raising the values or nudging the timing by applying an offset to X or Y.

To paste keyframe points and values with an X or Y offset: 1 Turn a single spline into the active visible spline and select the keyframes you want on it. 2 Right-click over the spline and pick Copy Points from the contextual menu, or hit Command-C. 3 Via the status checkbox by that spline’s name in the header, set it to viewed or disabled. 4 Promote the destination spline to active visible spline, then pick the keyframe on it where the new keyframes belong. 5 Right-click and pick Paste with Offset. Within the Offset dialog, type the Y value, which gets added onto the values of the pasted keyframes. TIP: Copying and pasting across different spline types isn’t allowed. As an example, you can’t copy off a Bézier spline and paste into a B-spline.

### Time and Value Editors

Sitting in the lower-right corner of the Spline Editor, the Time and Value Editors let you reset a keyframe’s position and parameter value by typing a number into the number field for each button. Every field toggles among three modes that adjust a keyframe’s time and value in three exact yet separate ways. By default, each field reads the literal frame number or parameter value where you want the keyframe placed. The remaining modes offset and scale the keyframe’s position or value instead.

Type a value or a particular time into the number fields to alter the selected keyframe. Time Editor: The Time Editor exists to change the current time of the selected keyframe. Switching the Time mode lets you type a particular frame number, an offset off the current frame, or spread the keyframes according to their distance (scale) from the playhead. Pick whichever of the three modes you want from the Time mode drop-down menu.

Three time editing modes can be chosen from the Time mode drop-down menu. Time: The number field displays the current frame number of the selected control point. Typing a new frame number into the field relocates the selected control point to that frame. When nothing is selected, or when several keyframes are selected, the field stays empty and no time can be entered.

### Time Offset

Choosing T Offset from the drop-down menu switches the number field’s mode over to Time Offset. Under this mode, the number field shifts the selected keyframes forward or backward in time. You can type in either a positive or a negative offset. As an example, an offset of 2 carries a selected keyframe from frame 10 to 12. Had several keyframes been selected in that same example, each one would advance two frames ahead of where it sat.

### Time Scale

Choosing T Scale from the drop-down menu switches the number field’s mode over to Time Scale. Under this mode, the selected keyframes’ positions scale relative to where the playhead sits. As an example, with a keyframe on frame 10 and the playhead on frame 5, typing a scale of 2 drives the keyframe 10 frames ahead of the playhead’s spot, landing on frame 15. Keyframes lying to the left of the playhead get scaled using negative values.

### Value Editor

The Value Editor exists to change the selected keyframe’s parameter value through one of three Value modes. Switching the Value mode lets you type a particular value for a parameter, an offset off that value, or spread the values out. You set the mode from the Value mode drop-down menu.

Three value editing modes can be chosen from the Value mode drop-down menu. Value: The number field displays the value of whichever keyframes are currently selected. Typing a new number into the field alters the selected keyframe’s value. With more than one keyframe selected, the value shown is an average across the keyframes, yet typing a new value makes every keyframe take on that value. Value Offset: Picking Offset from the drop-down menu puts the Value Editor into the Offset mode. Under this mode, the value for the selected keyframes shifts up or down. You can type in either a positive or a negative offset. As an example, typing a value of -2 turns a value of 10 into 8. With several keyframes selected, all of them have their values changed by -2. Value Scale: Picking Offset from the drop-down menu puts the Value Editor into the Scale mode. Typing a new value scales or multiplies the selected keyframes’ values by the amount you give. As an example, typing a value of 0.5 turns a keyframe’s value of 10 into 5.

### Modifying Spline Handles

Every Bézier spline keyframe carries two control handles that mold the spline as it runs through the key point. Those handles show up only while the keyframe is selected. To begin with, the handles sit at linear, which yields straight-line transitions between keyframes. Still, you can smooth out any control point by right-clicking over it and picking Smooth, or by pressing Shift-S.

### Bézier splines can mix linear and smooth curves

Dragging a keyframe’s handles changes the slope of the segments running through the spline. By default, a control point’s two handles are tied together, so moving one moves the one on the opposite side along with it. This keeps the tension through the keyframe steady. Even so, there are times when you’ll want to adjust these handles on their own for a sharper curve or effect. To break a Bézier spline’s control handles temporarily, so one moves apart from the other: 1 Select the control point you want to change. 2 Hold the Command key down and drag one of the control handles. They’ll now move apart from each other for as long as you keep the Command key held. To have every Bézier handle behave independently throughout the Spline Editor: Right-click in the graph and pick Independent Handles from the Options contextual menu. Turning this option on makes all the Bézier handles independent. It amounts to the same thing as using the Command key while moving a handle, except it covers every control point until you switch it off.

### Reducing Points

When a spline has too many control points crowded together, picking Reduce Points trims their number and makes the remaining points easier to work with. The spline keeps its overall shape as faithfully as it can while dropping redundant points from the path. To cut down a spline’s point count: 1 Select the span of keyframes you’d like to thin. 2 Right-click in the graph area and pick Reduce Points from the contextual menu. 3 Once the Reduce Points dialog comes up, drag the slider down to a lower value. You can push the slider value as low as it goes, provided the spline still closely echoes the shape of your original spline.

TIP: At a value of 100, none of the spline’s points get removed. Dial in smaller values to drop more points.

### Filtering the Spline Editor

The Spline Editor can show the animation splines for many parameters at the same time, and Fusion gives you several ways to decide which spline you view and which you edit. An intricate composition can readily hold dozens, even hundreds, of animation curves. The bigger a composition gets, the harder pinning down one specific spline becomes. You have two routes for filtering the splines on display in the Spline Editor: show only selected tools, or build a filter that surfaces just certain tools. The Spline Editor provides various means of governing which splines appear. Most of these options live in the Options menu, tucked into the upper-right corner of the Spline Editor panel.

The Options menu governs which splines turn up in the Spline Editor. Show Only Selected Tool: You can narrow the splines on display in the Spline Editor down to just those belonging to selected tools. Picking this option at the top of the Options menu surfaces only the splines for tools currently selected over in the Node Editor. Show All/None: By default the Spline Editor presents all the splines for every node carrying animated parameters. Enabling Show Only Selected Tools in the Options menu overrides that. You can also turn off the Show All setting by picking Show None, at which point the Spline Editor sits empty. Expose All Controls: The Expose All Controls option amounts to applying no filtering at all to the parameters. Picking it shows, in the Spline Editor header, every parameter belonging to all the nodes over in the Node Editor. It serves as a quick route to activating one parameter and having an animation spline added for it automatically when none exists yet.

When a lot of nodes are on display, each possibly bearing a lot of parameters, this can clutter the interface and bog it down. The option works best paired with the Show Only Selected Tool option, which caps how many nodes and parameters show up and delivers the best performance. Follow Active: You reach the Follow Active option by right-clicking in the graph and picking Options > Follow Active. This option lets you filter the splines in the graph without filtering the header list of tools. Whereas the Show Only Selected Tool option conceals other tools in the header, the Follow Active option keeps the header showing all the tools yet automatically enables only the splines belonging to the Active tool.

### Working with Filters

Filters let you pick the particular types and classes of tools that appear in the Spline Editor and Keyframes Editor. As an example, you might build a filter that surfaces only particle nodes, or one that surfaces only color correction and brightness/contrast tools. To build a filter: 1 From the Options menu, pick Create/Edit Filters. 2 Click the New button to start a new filter and give it a name in the dialog box. 3 Tick a checkbox beside a whole category, or beside individual tools within each category, to set which tools the filter takes in.

Tick each tool you’d like to keep in the Spline Editor whenever the filter is active. The Invert All and Set/Reset All buttons make sweeping changes to all the checkboxes, flipping the selected states as just described. To flip the selection state of the categories while building a filter list: 1 Click the Invert All button. 2 With the custom filter set up, click the Save button to dismiss the Settings dialog and store the filter. To tick or untick every checkbox: 1 Click the Set/Reset All button repeatedly until all categories end up either checked or unchecked. 2 With the custom filter set up, click the Save button to dismiss the Settings dialog and store the filter.

To apply a filter to the Spline Editor:

- Pick the filter you want by name from the Options menu. That filter takes effect across both the Spline Editor and the Timeline.

Every filter you build appears in the Options menu. To switch a filter off and bring all tools back into the Spline Editor:

- Pick Show All from the Options menu.

### Changing a Spline’s Status

The Spline header presents a hierarchical list of animated parameters together with their parent nodes. Clicking the disclosure arrow beside a tool’s name unfolds the names of every animated parameter on that tool. Clicking straight on a parameter name in the Spline header switches that spline on for display and editing.

The Spline header showing the Brightness Contrast tool alongside its animated Gain and Gamma parameters. Tool Status Checkbox: Beside each spline’s name sits a checkbox that signals the spline’s status. Selecting a parameter name makes the checkbox active, which lets you view and edit the spline in the graph. Each checkbox carries three selection modes: active, viewed, and disabled. Clicking straight on the checkbox cycles it through these three states. Altering the parent node checkbox’s state applies that state to every spline under that node.

Active: With the checkbox showing a check mark, the spline appears in the graph and is editable. Viewed: With the checkbox showing a solid gray box, the spline is visible in the graph but locked against editing. It’s read-only. Disabled: With the checkbox empty, the spline neither appears in the graph nor can be edited. Checkboxes dictate which splines you can see and edit.

### Selection States

There are three selection options here. Their labels — Select All Tools, then Deselect All Tools, plus Select One Tool — govern how the entries in the Spline Editor header act when you select a checkbox or label to switch a spline on. You’ll find these states in the Options menu at the upper-right corner of the Spline Editor. Select All Tools: Picking this option switches every spline on for editing. Deselect All Tools: Picking this one sets all spline checkboxes to disabled. As for Select One Tool, it works as a toggle. With Select One Tool picked from the menu, just one spline in the header stays active and visible at a time. Clicking any spline’s checkbox sets it active and clears all the others. While it’s off, several splines can be active in the header at once.

The Options menu selection states make selecting and deselecting all the header’s parameters simpler. Selection Groups: You can save the splines’ current selection state in the header, forming selection groups that reapply readily whenever you need them. To form a selection group, right-click over any header parameter or in a blank part of the graph and pick Save Current Selection from the contextual menu. A dialog opens for naming the new selection. To bring the selection group back, pick it by name from the Set Selection menu within that same contextual menu. Further context menu options let you rename or delete selection groups.

### Reshaping Splines Using the Toolbar

A spline’s shape can be reworked in several ways, which in turn changes the animation that spline produces. Beyond adjusting Bézier handles by hand, you can rapidly squish, stretch, loop, and reverse a spline. You can likewise switch the interpolation between keyframes from the default linear motion over to more natural smooth motion in a hurry. Every one of these options sits at the bottom of the Spline Editor in the toolbar. That toolbar breaks into separate groups: one sets interpolation, another reverses splines, another loops them, another handles time stretching, and a final one reshapes splines.

### Interpolation

Keyframes are particular frames in an animation at which control points hold exact values for a given parameter. Interpolation is the technique that fills in the unknown values lying between two keyframes. Fusion interpolates between two keyframes on its own. Still, you might want to adjust the interpolation to land a particular style of animation. The Spline Editor offers several interpolation methods you can pick from via the toolbar.

The toolbar’s interpolation buttons are these five: Smooth, Linear, Invert, Step In, and Step Out. Smooth: A smoothed segment eases how the curve enters and leaves the keyframe, achieved by gently lengthening the direction handles on the curve. The result slows the animation as it runs through the keyframe. To smooth whichever keyframe(s) you’ve selected, hit Shift-S, or else click that Smooth button on the toolbar.

### Smooth interpolation between keyframes

### Linear

A linear segment essentially follows the most direct path between two control points, namely a straight line. To set the selected keyframe(s) to linear, press Shift-L or click the Linear button in the toolbar.

### Linear interpolation between keyframes

TIP: Invert applies solely to non-animated LUT splines, which for now exist only inside the LUT Editor window.

### Step In/Step Out

Now and then you don’t want any interpolation at all between two keyframes. Instead, one keyframe’s value may stay put until a later keyframe changes it. In those situations, reach for the Step In or Step Out mode. Step In holds the previous keyframe’s value, then leaps directly to the next keyframe’s value.

Step In keeps a value steady until the comp reaches the next keyframe.

Step Out makes the selected keyframe’s value hold all the way up to the next keyframe.

Step Out jumps straight to the next keyframe value within a comp. You can apply Step In and Step Out modes to selected keyframes by clicking each mode’s toolbar button, or by right-clicking and picking the matching option from the contextual menu. The keyboard shortcuts I and O also serve to switch on Step In and Step Out for selected keyframes.

### Reversing Splines

Reverse flips the horizontal direction of a stretch of an animation spline. To run reverse, pick a cluster of points within a spline. Then take any one of these actions: click the Reverse button; right-click and choose Reverse off the contextual menu; or simply hit the V key. That cluster of points mirrors horizontally in the graph at once. Points neighboring the reversed selection can be affected too.

### The Reverse button in the toolbar

### Looping Splines

Repeating an animated section often comes in handy, whether endlessly or for a set number of passes, as you’d need to build a strobing light or a spinning wheel. Fusion supplies an assortment of ways to repeat a selected segment.

### The various Loop buttons in the toolbar

### Set Loop

To repeat or loop a chosen spline segment, first select the keyframes you mean to loop. Pick Set Loop from the contextual menu, or click the Set Loop button in the toolbar. The chosen part of the spline then repeats forward in time up to the end of the global range, or until a later keyframe caps the repeating segment.

### A looped section in the graph

Changing and Removing the Loop: You can alter the looped segment by tweaking any of the keyframes or control points that originally formed the loop. Just select one of the originating key points, apply whatever changes you need, and the looped segment refreshes. To drop the loop, select the keyframes you used to build it, then click the Loop button in the toolbar.

### Ping-Pong

The Ping-Pong Loop mode repeats the selected segment, flips each following loop around, and then keeps going. You can switch ping-pong looping on for the selected segments from the context menu or the toolbar.

### A ping-pong section in the graph

### Relative Loop

The Relative Loop mode repeats the segment much as the Loop does, except every repetition builds onto the final point of the prior loop, so the values climb steadily as time passes.

### A Relative Loop section in the graph

### Looping Backward

You reach Set Pre-Loop by right-clicking in the graph area and picking it from the contextual menu. This option holds the same looping choices as the Loop option buttons in the toolbar, the difference being that the selected segment repeats backward in time instead of forward.

### Repeating Splines X Number of Times

You can copy splines and repeat them a fixed number of times by right-clicking in the graph area and picking Duplicate from the contextual menu. Duplicated splines resemble looped splines, except the selected segment runs through only as many repeats as you specify, and every repeat is itself a copy rather than an instance. Changes you make to the original segment leave the shape of its repetitions untouched. You reach the Duplicate modes solely through the Duplicate contextual menu, which opens a submenu listing all the looping modes covered above. Picking any of these modes brings up a dialog where you type the number of repetitions.

### Gradient Extrapolation

You reach Gradient Extrapolation by right-clicking in the graph area and picking it from the contextual menu. This option carries on the path traced by the last two keyframes.

### The Gradient Extrapolation applied to the spline

### Time Stretching

Time Stretching lets a selected batch of keyframes be stretched or squashed proportionally. This gives you a way to change the animation’s duration while holding the relative spacing between each keyframe. To switch spline stretching on, select the batch of keyframes you want to time stretch; from there, either pick Modes > Time Stretching out of the graph’s contextual menu, or just click the Time Stretch button sitting in the toolbar.

### The Time Stretch button in the toolbar

With more than one keyframe selected on the spline, switching Time Stretch on wraps the outer keyframes in two vertical white bars. Pull on those white vertical bars to lengthen or compress the timing of whatever spline segments fall between them. Slide these bars back and forth to stretch or squash the spline segment.

### The Time Stretch bars in the graph

TIP: With no keyframes selected as you switch Time Stretch on, drag out a rectangle to mark the boundaries of the Time Stretch. To turn the Time Stretching mode off:

- Click the Time Stretch button in the toolbar once more, or pick Modes > Time Stretching again from the contextual menu.

### Shape Box

The Shape Box transform mode resembles Time Stretching, but it can scale keyframe values vertically on top of adjusting time. To switch the Shape Box on, do one of these:

- Select a batch of keyframes, then pick Modes > Shape Box from the contextual menu.
- Select a batch of keyframes, then click the Shape Box button in the toolbar.
- Select a batch of keyframes, then press Shift-B to switch the Shape Box mode on or off.

### The Shape Box button in the toolbar

A white rectangle frames the selected points once the mode is on. To scale, skew, or stretch the spline, drag any of the control points sitting around the box. To shift all the keyframes, drag the box edges.

### The Shape Box in the graph

TIP: When no points are selected, or whenever you’d like to grab a fresh batch of keyframes, you can drag out a new rectangle at any moment.

### Ease In/Out
