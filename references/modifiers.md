# Modifiers (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Modifiers

This chapter runs through which modifiers Fusion makes available.

A modifier extends the regular parameter set a node shows in the Inspector; their very purpose, in fact, is to drive other parameters. Some are as plain as a motion path or a link between two parameters. Others, though, can run to intricate expressions, procedural functions, external data, third-party plugins, or scripted Fuses. To attach a modifier, right-click over a parameter in the Inspector and pick one from the menu. As another route, right-click a control out in the viewer. Not every modifier shows in the right-click menu for every parameter, and some apply only to certain parameter types. NOTE: Text3D and Text+ carry their own text-specific modifiers, addressed in those nodes' sections.

### Modifiers right-click menu

### Anim Curves

The Animation Curves modifier (Anim Curves) lets you reshape an animation's timing, values, and acceleration on the fly, even when you opt to alter a comp's duration. Leaning on it makes stretching or squishing animations, smoothing motion, lending things a bounce, or mirroring animation curves vastly easier, sparing you the headache of hand-tweaking splines.

### The Inspector for the Anim Curves modifier

As you build Fusion templates for DaVinci Resolve's Edit and Cut page, the Anim Curves modifier lets the keyframed animation you set up in Fusion stretch and squish as it should whenever the transition, title, or effect's duration shifts on the Edit and Cut page Timelines.

### Curve Shape Controls

The Anim Curves modifier's controls live in the modifier's own Inspector tab. The Curve Shape controls dictate the animation curve's acceleration or shape.

- Source: This drop-down offers three options keyed to how the comp was spawned from DaVinci Resolve's Edit page. Transition: Chosen automatically whenever the comp springs from an Edit page transition effect. Should the transition's duration be revised on the Edit page, the animation's timing revises along with it. Duration: Reach for this when the comp comes from a clip on the Edit page. The animation timing refreshes if trimming alters the clip's duration. Custom: Brings up an Input dial for steering the timing by hand.
- Input: This dial surfaces only while Source sits on Custom. Its job is to alter the input keyframe value.
- Curve: The Curve drop-down picks which interpolation method runs between keyframes. There are three choices: linear, easing, or custom. Linear: The default Linear interpolation method holds a steady, even acceleration from keyframe to keyframe. Easing: Brings up interpolation menus for the curve's start (In) as well as its end (Out). Custom: Opens a mini Spline Editor for shaping the interpolation across the animation from start to finish.
- Mirror: Runs the animation forward and, on hitting the end, walks it back to its opening value. This doubles the speed of the initial animation, since the comp's back half is spent on the reverse run.
- Invert: Turns the animation curve upside down so the values open high and close low.

### Scaling

The Scale parameters reshape the animation values through relative adjustments.

- Scale: This figure is a multiplier laid over the keyframes' values. Where the Scale value is 2 and a keyframe holds a value of 0, it stays 0. Where the Scale value is 2 and a keyframe holds a value of 10, the outcome is as though the keyframe were set to 20. Picture it as the animation's closing value. The best moment to set it is while you have the comp's final frame in view.
- Offset: The offset gets added onto the keyframe values and can be pictured as the animation's opening value. The best moment to set it is while you have the comp's first frame in view.
- Clip Low: Keeps the output value from ever falling under 0.0.
- Clip High: Keeps the output value from ever climbing past 1.0.

### Timing

The Timing parameters tune the animation's timing through relative values.

- Time Scale: Stretches or compresses the animation so it plays faster or slower. At 1.0 the animation spans the comp's duration (barring any customization you have done with the Modifier's other controls).
- Time Offset: This value holds the animation back by a fraction of its full duration. At 0.0 there is no delay. At 0.5 the animation's start is pushed to the midpoint of the comp's duration.

Using the Anim Curves Modifier to Create a Custom Transition To get a feel for using the Anim Curves modifier on a transition, let's build a simple scaling dissolve. 1 Drop a standard cross dissolve into the Edit page Timeline. 2 Right-click the transition and pick Convert to Fusion Cross Dissolve. 3 Right-click the transition once more and pick Open in Fusion page. 4 Attach a Transform node to MediaIn1 and to MediaIn2. 5 Click the Transform node tied to MediaIn2. 6 In the Inspector, right-click the Size control and pick Modify With > Anim Curves from the contextual menu. Putting this modifier on the Size control makes the slider animate from 0 to 1 across the Cross Dissolve's duration. 7 Click the Transform node tied to MediaIn1. 8 In the Inspector, right-click the Size control and pick Modify With > Anim Curves from the contextual menu. 9 Up top in the Inspector, open the Modifier tab and press the Invert button. Inverting the animation curves drives MediaIn1 to scale the opposite way from MediaIn2. 10 In the Modifiers tab, switch the Curve drop-down to Easing and try out the various ease-in ease-out curve types from the In/Out drop-downs. After you turn this node tree into a Macro and save it as a Transition template, you can drop it into the Edit page Timeline. Alter the transition duration on the Edit page and the animation timing adjusts to suit.

### Using the Anim Curves Modifier with Paths

To grasp how to pair the Anim Curves modifier with a Path modifier, let's suppose you want text that drops from the top of the frame and bounces once it hits the bottom. 1 In Fusion, lay down two keyframes that send text from the top of the frame down to the bottom. A Path modifier is created automatically. 2 In the Inspector's Modifier tab, right-click the Displacement parameter and pick Insert > Anim Curves. The animation is normalized against the comp's duration. 3 Set the Source menu to Duration, given that this is no transition and we are leaving the duration untouched. 4 From the Curve menu pick Easing, then for the Out menu pick Bounce. 5 Run the animation to watch the Bounce animation. 6 To land the bounce halfway down the frame, set the Scale to .05. 7 To double the animation's speed, type 2.0 into the Time Scale parameter. Once this node tree is turned into a macro and stored as a Title template, dropping it into the Edit page Timeline becomes possible. Change the title's duration on the Edit page and the animation timing falls into line. TIP: To see the resulting animation curve in the Spline Editor, click the parameter name in the Spline Editor's header. The spline refreshes as you work the controls.

### Bézier Spline

The Bézier Spline counts among Fusion's animation modifiers and usually goes onto numerical values rather than point values. It attaches automatically when you keyframe a parameter, or any time you right-click a number field and pick Animate.

### Bézier Spline modifier menu

### Usage

To bring the Bézier Spline into the Spline Editor, right-click a number field and pick BezierSpline. Because it is the go-to pick for animation splines, it is pulled out of the Modify With menu so you can reach it faster. Picking BezierSpline from the menu plants a keyframe at the present spot and shows a Bézier Spline in the Spline Editor.

### Bézier Spline Editor

Setting it apart from most modifiers, this one carries no real Controls tab in the Inspector. The Spline Editor does present the Bézier Spline, though, and that is where you work it. The Bézier Spline hands you per-point control over each control point's smoothness by way of Bézier handles. That smoothness can be applied in several ways:

- To smooth the control points, select them and hit Shift-S. The handles then let you refine the smoothness further.
- To make the control points linear, select them and hit Shift-L. These same actions are available through the contextual menu too.
- Choose the control point(s), right-click, and pick Smooth or Linear. That menu also lets you smooth a spline via a convolution analysis known as a Savitzky-Golay filter. Choose the control point(s), right-click, and pick Smooth Points -Y Dialog.

### Ease In/Out

Classic Ease In/Out can likewise be adjusted through the number field virtual sliders in the Spline Editor. Choose the control points you wish to adjust, right-click, and pick Ease In/Out... from the contextual menu. Then steer the Ease In/Out by the numbers using the number field virtual sliders.

### Spline Ease In/Out modifier

### B-Spline

Standing in as an alternative to the Bézier Spline, B-spline is yet another of Fusion's animation modifiers and is usually put onto numerical values rather than point values. You apply it by right-clicking a parameter and picking Modify With > B-Spline.

### Usage

### B-Spline Editor

- This animation spline modifier comes with no real Controls tab. The Spline Editor shows the B-spline, though, and that is where you control it. Observe that even though the second keyframe's actual value is 0, the resulting spline reads 0.33, an outcome of the B-spline's distinctive smoothing and weighting algorithms.
- To change the weight, click a control point to select it, hold the W key, and slide the mouse left and right to ease or raise the tension. The same works on several selected control points at once.

### Calculation

Calculations serve to forge indirect links between parameters. A Calculation runs a mathematical expression over two operands, each of which may be wired to another parameter or entered by hand. On top of that, through the Time tab's Time offsets and Scale controls, the Calculation control can reach a parameter's values at moments other than the present time. Its most frequent use is tying two parameters together when one's value range or scope does not suit the other. NOTE: The Expression modifier is, in essence, a more flexible take on the Calculation modifier, bar one thing. Shaping the operands' timing is far simpler in the Calculation modifier than it is with an Expression.

### Inspector

### Calculation Calc tab

### Calc Tab

The Calc tab carries two dials for the wired-in parameter and the value that gets mathematically blended with it. The Operator menu decides how the Second Operand value blends with the parameter's value. First and Second Operand These sliders either hook into published or animated parameters or get hand-set to the values the calculation needs. Operator Pick from the mathematical operations this menu lists to set how the two operands combine. Click the drop-down arrow to open the menu, which holds these options:

- Add
- Subtract (First - Second)
- Multiply
- Divide (First / Second)
- Divide (Second / First)
- Subtract (Second - First)
- Minimum
- Maximum
- Average
- First only

### Time Tab

The Time tab lets you alter the timing of the Calculation modifier. Its controls either retime how fast the effect runs or shift it in time.

### Calculation Time tab

First and Second Operand Time Scale These sliders scale the frame number and hand back the operands' values at the scaled frame number. At a value of 1 the operand's value comes back from frame x while the composition sits on frame x. As an illustration, if the first operand is animated from a value of 1 to 50 across frame 0 to 10, then a scale of 0.5 makes the calculation hand back a value of 25 at frame 10 (in effect halving the animation's speed as far as the calculation is concerned).

First Operand and Second Operand Time Offset These sliders hand back the operand's value at the Time Offset you specify. A value of 10 fetches the operand's value 10 frames ahead in time, while -10 fetches it 10 frames behind. A practical example appears below.

### Example

The example here leans on a calculation to blur a Text node by an amount that runs inverse to the text's size.

- Start a new composition running from frame 0 to frame 100.
- On frame 0, drop a Text+ node into the composition.
- Type in a little text and set the size to 0.05
- Click the Keyframe button just right of the Size slider to lay down a keyframe.
- Jump to frame 100 and set the Size value to 0.50.
- Wire a Blur node after the Text+ node.
- Bring the Blur node up in one of the viewers.

Making the blur weaken as the text grows cannot be done with plain “pick whip”-style parameter linking. You cannot simply wire the controls together, since the Text Size control's values are climbing rather than shrinking.

- Right-click the Blur Size and pick Modify With > Calculation from the contextual menu.

That puts a Calculation modifier on the Blur node. Up top in the Inspector, a fresh set of controls turns up in the Modifiers tab whenever the Blur node is selected.

- Up top in the Inspector, open the Modifiers tab (F11).
- Right-click the First Operand slider and pick Connect To > Text 1 > Size from the

contextual menu. The Blur Size is now tied to the Text Size parameter, but the link is not much use yet. The Blur Size control caps at a maximum value of 0.5, barely registering as a blur.

- Switch the Operator drop-down to Multiply.
- Push the Second Operand slider to 100.
- The first operand is now multiplied by 100, and working the dial yields a far

blurrier blur.

- Move to the modifier's Time tab and set the First Operand Time Scale to -1.0.

Ordinarily the first operand takes the value of whatever control it links to from the same frame as the present time. So at frame 10 the first operand matches the Text size at frame 10. Setting this to -1 makes the value get read one frame back in time each time the composition's current time steps forward by 1 frame. That, however, means the Calculation would be reading the Text size's value at frame -10 while we sit at frame 10 in the composition.

- To put that right, set the First Operand Time Offset slider to 100.
- Head back to the Tools tab up top in the Inspector and hit Play (Spacebar) to observe how

the Blur Size's value tracks the Text Size's value.

### CoordTransform Position

Owing to how hierarchical 3D is in Fusion, an object's starting position in a 3D scene frequently no longer reflects where it currently sits. Take an image plane that begins at a position of 1, 2, 1, only to be scaled, offset, and rotated by other tools further down the node tree, winding up at an absolute location of 10, 20, 5. That can muddy any attempt to wire an object further down the composition straight to the position of an object upstream. The Coordinate Transform modifier can be dropped onto any set of the XYZ coordinate controls to work out a given object's present position at whatever point in the scene hierarchy. To add one, right-click the numeric input on any node and pick Modify With > CoordTransform Position from the contextual menu.

### Inspector

### The Coordinate Transform modifier Controls tab

### Controls Tab

The Controls tab carries two fields, one for the target and one for the scene input. The target holds the node bearing the original coordinates, while the scene input holds the scene with the new coordinates. Target Object This control wires to the 3D tool that yields the original coordinates due to be transformed. To make that connection, pull its node out of the Node Editor and onto the text edit control, or else right-click that control to choose the tool from the contextual menu. You may also type the tool's name straight into the control. SubID The SubID slider lets you zero in on a single sub-element of certain geometry types, such as one character made by a Text 3D tool or a particular copy spawned by a Duplicate 3D tool. Scene Input This control ought to wire to the 3D tool that outputs the scene holding the object at its new location. To set that up, drop a tool tile out of the Node Editor onto the text edit control, or instead right-click that control to choose an object from the Connect To pop-up menu.

### Cubic Spline

The Cubic Spline is one more of Fusion's animation modifiers, ordinarily put onto numerical values rather than point values. You apply it by right-clicking a numerical control and picking Modify With > Natural Cubic Spline.

### Usage

As an animation spline, this modifier offers no real Controls tab. Its effect can still be viewed and shaped within the Spline Editor, though.

### Cubic Spline Editor

### Custom Poly

The Custom Poly modifier attaches to Polygon masks or paths. Working much like the Custom and pCustom tools, it lets you shift the polyline's existing points around or swap them out wholesale for a fresh set. Its expressions run for every point on the output polygon. To apply it, right-click the “Right-click here for shape animation” text at the foot of the Polygon controls and pick Insert > Custom Poly from the contextual menu.

### Selecting the Custom Poly modifier

### Inspector

### The Custom Poly Controls tab

### Controls Tab

The Custom Poly Controls tab becomes reachable once you open the modifiers tab on the Polygon's inspector. It offers a single point input plus number variables for use in animating the expressions. By default that is one point and four numbers, though both can grow to a maximum of nine. You add further points and numbers from the Config tab.

### The Custom Poly Polyline tab

### Polyline Tab

The polyline tab lays out the controls for wiring up and reshaping the polyline. Connect Source Polyline here Lets you wire other polylines into the modifier. Show View Controls This checkbox flips the polyline controls' visibility in the viewer on or off. Number of Points You can set how many output points there are, which governs how finely the polyline is custom-subdivided. A value of zero falls back on the count of original source points.

Poly Expression X/Y The fields where you type the mathematical expressions. For instance, px*(1-n1)+n1*get2x(disp) and py*(1-n1)+ n1*get2y(disp). It draws on most of the same expression variables as the Expression modifier covered below (that is, n1..n9, p1x..p9x, p1y..p9y, math functions, and so on), and tacks on these:

- px,py giving the current point on the source polygon
- disp giving how far the point sits along the polyline (0.0 marks the start, 1.0 the end)
- index giving the current point’s index (counted from zero)
- num giving the count of output points
- getx(disp), gety(disp) for pulling values from any spot on the polyline
- getx_at(disp, time), gety_at(disp, time) for pulling values from polylines at other times
- In the same vein, get2x/y(), get3x/y(), get2x/y_at(), get3x/y_at() cover the second and third source polys

### Config Tab

The config tab lets you choose how many Points and Numbers the modifier displays (up to 9) and hand them custom names to keep things organized.

### Expression

An expression is a variable or a mathematical calculation placed on a parameter in lieu of a plain numeric value. You can attach an expression to any parameter in Fusion, or you can attach the Expression modifier, which appends several tabs to the modifier Inspector. Putting this modifier on a parameter grants the ability to drive that parameter off any number of controls, whether positional or value-based. It is exceptionally flexible next to the more limited Calculation or Offset modifiers, yet it cannot reach values from frames other than the present time. The Expression modifier takes nine value inputs and nine position inputs, which feed a user-defined mathematical expression that outputs a value. To attach it to a parameter, right-click the parameter in the Inspector and pick Modify With > Expression from the contextual menu. What kind of value the Expression returns hinges entirely on the control it is modifying. Against a value control (a slider, say), the Expression in the Number Out tab is evaluated to form the result. Against a positional control (such as Center), the Point Out tab drives the result. The controls for the Expression modifier sit in the Inspector's Modifiers tab and are described below.

### Inspector

### Expressions modifier controls

### Controls Tab

This tab hands you nine number controls and nine point controls. Within an expression, the number controls' values are addressed as n1 through n9. Each point control's X-coordinate is addressed as p1x through p9x, and its Y-coordinate as p1y through p9y. You can set these values by hand, wire them to other parameters, animate them, and even wire them to other Expressions or Calculations.

### Number Out Tab

Here you type mathematical formulas that pull on the Controls tab's Number In and Point In values. Whatever they output drives the control the Expression was placed on. The syntax for this field is covered below.

### The Number Out tab

### Point Out Tab

This tab's two text boxes run mathematical formulas that tap the Number In and Point In values from the Controls tab. The resulting value drives the control the Expression was placed on. The Expression in the upper text box computes the X-axis value, while the lower text box computes the Y-axis control. The syntax for this field is covered below.

### The Point Out tab

### Config Tab

A solid expression gets reused time and again. Because of that, giving each parameter or control a more telling name and tucking away the unused ones can pay off. The Expressions modifier's Config Tab lets you tailor both the visibility and the name of every one of the nine point and number controls.

### The Expressions modifier Config tab

Random Seed The Random Seed control fixes the starting number that the Rand() function uses. The rand(x, y) function yields a random value between X and Y, generating a fresh one each frame. So long as this Random Seed slider stays put, the values generated at frame x never change. Move the Seed slider to a new value to draw a different value at that frame. Show Number or Point X These checkbox controls number eighteen in all, one per each of the nine Number and nine Point inputs. Tick a checkbox to bring the control for Number x or Point x into the Controls tab.

### Name for Number or Point X

These edit controls also number eighteen, one per each of the nine Number and nine Point inputs. Enter a fresh name for the input into this edit control to relabel that Input in the Controls tab.

### Expression Syntax Formulas

Within an expression, formulas go into either the Number Out tab or the Point Out tab. They may be assembled from the following functions:

n1...n9 p1x...p9x p1y...p9y time pi e log(x) ln(x) sin(x) cos(x) tan(x) asin(x) acos(x) atan(x) atan2(x, y) abs(x) int(x) frac(x) sqrt(x) rand(x, y) rands(x, y, s) min(x, y) max(x, y) dist(x1, y1, x2, y2) dist3d(x1,y1,z1,x2,y2,z2)
