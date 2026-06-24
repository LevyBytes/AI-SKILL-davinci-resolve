# Editing Parameters In The Inspector (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

To pick up a color from an image shown in the viewer, press and hold the cursor on the Eyedropper, then drag the pointer out into the viewer. As you do, the pointer turns into an Eyedropper and a swatch pops up just above the cursor, displaying whatever color sits beneath it together with its values. Once you reach the color you're after, let go of the mouse button to lock it in. Although the Color Picker samples a lone pixel by default, you can enlarge the sampling region: drag into the viewer using the Eyedropper, then hold Command and drag out a rectangle sized to the sample area you want. That new size stays in effect for every Color Picker until you change it once more.

### The Eyedropper with color swatch

### Gradients

You use the Gradient Control bar to build a smooth transition from one color to another. Along the Gradient bar you'll see a preview of the colors running from beginning to end. Out of the box, two triangular color stops are present: the left-hand one fixes the start color while the right-hand one fixes the end color.

### The default Gradient controls

Gradient Type The Gradient Type button array lets you pick the form in which the gradient is rendered. Linear gradient: Linear lays the gradient out along a straight path running from the starting color stop to the ending one.

### Linear gradient

Reflect gradient: Reflect produces the gradient by mirroring the linear gradient on both sides of the starting point.

### Reflect gradient

Square gradient: Square renders the gradient with a square pattern, taking the starting point to be the center of the image.

### Square gradient

Cross gradient: Cross renders the gradient with a cross pattern, taking the starting point to be the center of the image.

### Cross gradient

Radial gradient: Radial renders the gradient as a circular pattern, taking the starting point to be the center of the image.

### Radial gradient

Angle gradient: Angle sweeps the gradient counter-clockwise, taking the starting point to be the center of the image.

### Angle gradient

### Start and End Position

A pair of X and Y edit boxes makes up the Start and End Position controls, handy for precisely tuning where the gradient begins and ends. Those same position values also show up as two crosshair onscreen controls in the viewer, which can be the handier way to do your first rough placement.

### Gradient Colors Bar

The Gradient Colors bar is where you pick the colors that blend together in the gradient. Its two default color stops define the start and end colors. To swap a color in the gradient, click its color stop and then set a fresh color with the Eyedropper or color wheel. The Colors bar also lets you add, reposition, duplicate, and remove gradient colors. To add a fresh stop onto the Gradient Colors bar: 1 Click at any spot across the lower edge of the Gradient Colors bar. 2 Pick the stop's color using either the Eyedropper or the color wheel. To reposition a stop along the Colors bar:

- Drag a color stop left or right along the Gradient Color bar.

To copy a color stop on the Colors bar:

- Hold Command while you drag a color stop.

To remove a stop from the Colors bar, take either of these approaches:

- Drag the color stop up past the Gradient Colors bar.
- Choose the stop and then hit the red X button to remove it.

### Interpolation Space

Via the Gradient Interpolation Method pop-up menu you choose which color space is used when computing the colors that fall between color stops.

### Offset

Moving the Offset control shifts the gradient's placement with respect to the start and end markers. It comes into its own when paired with the repeat and ping-pong modes covered just below.

### Once/Repeat/Ping-Pong

This trio of buttons dictates what the gradient does once the Offset control pushes it beyond its start and end positions. Once is the default, holding the color steady for offset. Repeat wraps back around to the start color the moment the offset passes the end color. Ping-pong plays the color sequence back in reverse.

### 1x1, 2x2, 3x3, 4x4, 5x5

These buttons govern how much sub-pixel accuracy is applied once the gradient's edges show through in Repeat mode, or while the gradient is being animated. Cranking the setting up makes rendering far slower but yields greater precision.

### Gradient Contextual Menu

Each gradient carries its own contextual menu, which you summon by right-clicking the Gradient bar. The Gradient contextual menu holds choices for animating, publishing, and linking one gradient to another. It also includes a gradient-only modifier that constructs a custom gradient by drawing colors from the output of a node in the Node Editor.

### Modifiers

Modifiers are things like expressions, calculations, trackers, paths, and other mathematical building blocks that you connect to a parameter to broaden what it can do. Once a modifier is attached to a parameter, its own controls show up separately in the Inspector Modifiers tab. The steps to attach one: 1 Right-click on the parameter you'd like to give a modifier to. 2 Pick an entry from the Modifier submenu inside the contextual menu.

### Animating Parameters in the Inspector

In Fusion you can keyframe nearly every parameter on nearly every node, opening the door to animated results like moving transforms, spline-based rotoscoping, warps that shift over time, and on and on without limit. To make this easy, keyframing controls sit right inside the Inspector beside each keyframable parameter. They are:

- A gray Keyframe button sitting to the right of each keyframable parameter. Pressing this gray button drops a keyframe wherever the playhead currently rests and flips the button to orange.
- Once a parameter has a keyframe, jumping to a different frame and altering that parameter drops a new keyframe automatically at the spot you're on.
- Any time the playhead lands exactly on a keyframe, the button shows orange. Pressing an orange Keyframe button removes the keyframe at that frame and reverts the button to gray.
- If keyframes exist further along in either direction, little navigation arrows show up on the left and right. Pressing those left and right navigation arrows next to the keyframes sends the playhead straight to them.

Orange Keyframe buttons in the Inspector mark frames that hold a keyframe. After you've set keyframes on a parameter or two, and provided Show Modes/Options is turned on, the node holding those keyframed parameters wears a Keyframe badge that signals the node now carries animation.

A node that's been keyframed wears a Keyframe badge over in the Node Editor. Once node parameters are being keyframed, you're free to retime them within the Keyframes Editor and/or Spline Editor. To dig deeper into Fusion keyframing, turn to Chapter 71, “Animating in Fusion’s Keyframes Editor,” found in the DaVinci Resolve Reference Manual, or to Chapter 9 of the Fusion Reference Manual.

### Removing Animation From a Parameter

To clear all the keyframes from a parameter: 1 In the Inspector, right-click the keyframed parameter's name. 2 From the contextual menu, pick Remove “node name:parameter name”. TIP: Should you switch away from the default Bézier spline type, the contextual menu instead shows whatever spline type is currently in use.

### Attaching a Parameter to an Existing Animation Curve

You can hook several parameters up to one shared animation curve. That's a real timesaver whenever you're driving different parameters on a node with the very same animation. To wire a second parameter onto that same animation curve: 1 Right-click whichever second parameter you'd like to attach. 2 Within the contextual menu, hover your pointer over the Connect To submenu. 3 From the Connect To submenu, select the animated parameter's name.

### Connecting Parameters

There's frequently good reason to link two parameters even when no animation curve is involved. You have two ways to do it.

### Connecting Parameters by Publishing

To bind two parameters so that moving one moves the other, you join them by issuing the Publish menu command on the first and the Connect menu command on the second.

To Publish and Connect parameters: 1 Right-click the name of whichever parameter you'd like to publish and pick Publish from its contextual menu. 2 Right-click the second parameter you mean to attach, then from the Connect To submenu select the name of the parameter you just published.

### The Publish contextual menu

### Connecting Parameters by Pick Whipping

Another route is to tie two parameters together with simple expressions. Pick whipping with simple expressions lets you wire values up and combine them visually, with no need to publish a value beforehand. The pick whip itself is a momentary line you drag from one parameter to another to forge a link between them. To join two parameters with a pick whip: 1 Double-click into the field of the parameter you'd like to pick whip onto another, enter =, and then hit the Return key. 2 Once the Pick Whip controls show up beneath the parameter, drag a “whip” out of the Add button over to the target parameter. From then on, changing the target parameter changes the original one too.

### Pick whipping one parameter to another

TIP: Turn off the Auto Control Close node’s General preference, then select a pair of nodes in the Node Editor, and you'll be able to pick whip two parameters that live on different nodes. Beyond that, the Expression field lets you layer mathematical formulas onto the incoming value from the target parameter. To read up further on Pick Whipping and Expressions, consult Chapter 74, “Using Modifiers, Expressions, and Custom Controls,” within the DaVinci Resolve Reference Manual, or Chapter 12 of the Fusion Reference Manual.

### Contextual Menus

Inside the Inspector you can call up two kinds of contextual menu.

### Node Contextual Menus

To bring up the Node Context menu from inside the Inspector, right-click on the Inspector header. That node's contextual menu offers the very same entries you'd reach by right-clicking the node within the Node Editor itself. To learn more about these choices, refer to Chapter 67, “Working in the Node Editor.” inside the DaVinci Resolve Reference Manual, or to Chapter 5 of the Fusion Reference Manual.

### Parameter Contextual Menus

You reach an individual parameter's contextual menu by right-clicking over that parameter's name, slider, thumbwheel, range control, button array, or any other control type. Right-clicking a slider, for instance, brings up the slider's contextual menu, complete with options to animate the control or stack on extra modifiers. A good many of these options got covered earlier in this chapter.

### Customizing Node Parameters with User Controls

Every Fusion node has an interface laid out to expose its parameters in a sensible way. Even so, there are times you'll want to add, conceal, or rework the controls. That's most often done for simple expressions and macros, though you might also do it for the sake of usability or appearance with favorites and presets. You add or edit user custom controls through the Edit Control dialog. Right-click a node's name in the Inspector (up in the header bar) and pick Edit Control from the contextual menu. A fresh window opens, labeled Edit Control.

### The Edit Control window

Under the Input attributes you can choose an existing control or build a brand-new one, give it a name, set its type, and place it on a tab. Under the Type attributes you spell out the input controls, the defaults and ranges, and whether an onscreen preview control exists. The Input Ctrl attributes box holds settings tied to the particular node control selected, while the View Ctrl attributes box holds settings for the preview control, should there be one. Every change you make with UserControls lives inside the node instance itself, which means they can be copy/pasted, saved into a setting, added to the Bins, or added to your favorites.

### An Example of Customizing Directional Blur

For this walkthrough, imagine we'd like a more intuitive means of steering a linear blur than working the Length and Angle sliders separately.

### Default Directional Blur controls in the Inspector

By leaning on the Center input control alongside its preview control, we can set both an angle and a distance directly inside the viewer through expressions. 1 Right-click the Length parameter's label, pick Expression off the contextual menu, then drop this expression into the Expression field that opens up: `-sqrt(((Center.X-.5)*(Input.XScale))^2+((Center.Y-.5)*(Input.YScale)*(Input. Height/Input. Width))^2)` 2 After that, right-click the Angle parameter's label, again pick Expression off the contextual menu, and drop this expression into the Expression field that opens up: `atan2(Center.Y-.5)/(Input.OriginalWidth/Input.X , .5-Center.X) * 180 / pi`

### Directional Blur controlled by the Center’s position

That works, but the controls are bewildering. The Center control no longer acts as the center, and it really ought to carry the name “Blur Vector” instead. Since the Length and Angle controls aren't meant to be touched, they ought to be tucked out of sight, and because we're only after a linear blur, the Radial and Zoom buttons are surplus. All we actually need is a choice between Linear and Centered.

### Adding Another Control

To begin, let's rename the Center. In the Add Control window, pick Center from the ID list. A dialog pops up offering Replace, Hide, or Change ID. We'll go with Replace. We're now editing the Center input. We'll set the Name to Blur Vector, the Type to Point, and the Page to Controls — the first tab, where the controls usually live. Hit OK, and our new input shows up on our node in the Node Editor. Because the control's ID stays Center, our SimpleExpressions are untouched. To tuck away the Length and Angle, we'll launch the UserControls script once more. This time, with the Length and Angle IDs selected, we'll pick Hide in the dialog. Hit OK for each. Lastly, to adjust which choices the Type offers, two paths are open to us. We can hide the buttons and swap in a checkbox, or we can trim the MultiButton down from four entries to two. Let's do both.

- For the checkbox, fire up UserControls once more, only this time, in place of choosing an existing ID, we'll enter Centered into the Name. That action makes both our input's name and its ID become Centered. We leave the Type at Number and the Page at Controls. Over in the Type Attributes, make the Input Ctrl a CheckboxControl. Hit OK, and there's our checkbox. So that the new control drives the Type, attach a SimpleExpression onto the Type:

iif(Centered==1, 2, 0). With that in place, UserControls can be used to tuck the Type control out of sight.

- For a new MultiButton, launch the UserControl script and create a fresh control ID called TypeNew. Feel free to set its Name to Type, since Names needn't be unique — only the IDs do. Make the Type Number, the Page Controls, and the Input Ctrl a MultiButtonControl. Within the Input Ctrl attributes, we get to type in our button names. We'll use Linear and Centered — enter each and click Add. Press OK, and our new buttons appear with the surplus options gone. So that this new control drives the original Type, attach a SimpleExpression onto the Type:

iif(TypeNew==0, 0, 2).

With that in place, UserControls can be used to tuck the original Type control out of sight.

### Directional Blurs with UserControls applied
