# Using Modifiers Expressions And Custom Controls

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using Modifiers, Expressions, and Custom Controls

Among Fusion’s greatest strengths are the several routes it opens for reaching past the ordinary toolset that ships with the program. Here you will find a primer on a range of advanced capabilities — Modifiers, Expressions, and Scripting among them — each of which lets you broaden what the software does and fold Fusion more tightly into your studio.

### The Contextual Menu for Parameters in the Inspector

You reach nearly all of the capabilities described here through a contextual menu, which pops up whenever you rightclick most parameters in the Inspector. The exact menu you get changes according to which spot in the Inspector your right-click lands on. In particular, right-clicking a parameter name or a slider opens a richly stocked contextual menu — one that can attach animation, expression fields, and modifiers that broaden behavior, plus publishing and linking tools that let you drive several controls at once.

### Using Modifiers

Modifiers — which act as add-ons to a node’s toolset — give you a way to drive parameters. A good many of them will generate, on their own, animation that would be a chore to build by hand. At one end a modifier might be nothing more than keyframe animation or a link tying parameters to other nodes; at the other it might involve elaborate expressions, procedural functions, outside data, third-party plugins, or fuses.

### Adding the Right Modifier for the Job

The set of modifiers on offer hinges on the kind of parameter sitting under your right-click. Each parameter type — numeric values, text, polylines, gradients, and points — comes with its own compatible modifiers, which is why the Modify With menu narrows its choices to suit whichever parameter you picked.

### Adding Modifiers to Individual Parameters

To attach modifiers to a parameter, use the Inspector’s contextual menu, or right-click that parameter’s onscreen control out in the viewer. Whichever path you take, you are shown a live list of the modifiers suited to the parameters you have selected. As an example, dropping a Perturb modifier onto any slider auto-animates the parameter by jiggling its value at random. With the modifier in place, the Modifiers tab fills with controls for tuning how fast and how far the random animation swings.

Adding a Perturb modifier to the Center X and Y parameters by way of the Inspector contextual menu

You will find a modifier’s controls under the Modifiers tab in the Inspector. Should the node you have selected carry a modifier, that Modifiers tab lights up to signal as much. Where no modifier has been applied, the tab simply stays grayed out.

### The Modifiers tab with two modifiers applied

Just as node tools do, modifiers show up with their own header bars and header controls. You can likewise drag a modifier’s title bar into a viewer when you want to inspect what it puts out.

### Combining Modifiers and Keyframes

Auto-animating modifiers such as Perturb and Shake pair nicely with keyframes, together yielding animation that feels more lifelike and organic. You might, say, lay down the broad motion path of an object by keyframing its Center X and Y parameters, then layer a modifier over those same parameters to add a secondary jitter. To pair a keyframed motion path with a Perturb modifier: 1 Apply a Transform to some image, perhaps a butterfly or spaceship. 2 In the Node Editor, click the Transform node to select it. 3 Over in the Inspector, press the Keyframe button sitting to the right of the Center X and Y parameters. 4 Place the butterfly or spaceship picture at whatever spot you intend the animation to open on. 5 Keep advancing the playhead through the render range, nudging the image each time, until a figure-8 motion path takes shape. 6 In the Inspector, right-click the Center X label and pick Modify With > Perturb. 7 Open the Modifiers tab atop the Inspector, then dial in jittery random movement by tuning the Strength, Wobble, and Speed parameters as playback runs.

### Publishing a Parameter

What the Publish modifier does is expose a parameter’s value so that other parameters are free to connect to it. The upshot is that a single slider can drive several parameters at once, whether they sit on the same node or on different ones. Publishing a motion path, for one, lets you hook a number of objects up to that one path.

Publish a parameter so that other parameters may be tied to it After a parameter has been published, a right-click on some other parameter lets you pick Connect To > [published parameter name] out of the contextual menu. From then on the two values move together, and editing one of them in the Modifiers tab shifts the other. The pick whip drawn between two parameters delivers comparable linking while granting you more latitude. Pick whipping across parameters gets its own treatment further along in this chapter.

### Connecting Multiple Parameters to One Modifier

One modifier — or one published parameter — can govern several parameters together so that they behave in unison. The Connect To submenu is where this gets set up. Much as with assigning a modifier, the menu trims itself down to just those choices that fit whichever parameter you right-clicked. The resulting link runs both ways: edit either side and the opposite parameter follows.

Linking modifiers across several parameters by way of the Connect To menu

### Adding and Inserting Multiple Modifiers

In the same way nodes do in the Node Editor, modifiers can be wired together and branched off one another. Take the Calculation modifier: it emits a number yet carries two Number parameters, and either of those can itself receive a modifier. Should you need to slot a modifier in between an existing one and the parameter it modifies, reach for the Insert submenu found in that parameter’s contextual menu.

Available Modifiers in Fusion:

- Anim Curves: Brings in an animation curves modifier with which you can reshape an animation’s timing, scaling, and acceleration on the fly.
- Bézier Spline: Drops a Bézier spline into the Spline Editor so the chosen parameter can be animated.
- B-Spline Spline: Drops a B-Spline spline into the Spline Editor so the chosen parameter can be animated.
- Calculation: Forges an indirect link, carrying a mathematical expression, between a pair of parameters.
- CoordTransform Position: Works out where a given object currently sits in 3D, even once several 3D transforms have shuffled that object along the node tree hierarchy.
- Cubic Spline: Drops a Cubic spline into the Spline Editor so the chosen parameter can be animated.
- Expression: Lets you feed a parameter a variable or a math calculation in place of a plain numeric value. Controls for the Expression modifier live in the Modifiers tab, where there is more room and more parameters at hand than the SimpleExpression
- From Image: Reads color samples off an image along a line you define, then builds a gradient out of those samples.
- Gradient Color Modifier: Builds a gradient of your own design and lays it across a stated time range to animate a value.
- KeyStretcher: Stretches keyframes within a Fusion Title template when that template is trimmed on the Edit page or Cut page timeline.
- MIDI Extractor: Drives a parameter’s value from the data held inside a MIDI file.
- Natural Cubic Spline: Drops a Natural Cubic spline into the Spline Editor so the chosen parameter can be animated.
- Offset (Angle, Distance, Position): These three Offset modifiers serve to introduce variances, or offsets, between a pair of positional values. Attach this modifier to a size parameter, for example, and an object’s size can be driven by the gap between two onscreen controls (position and offset).
- Path: Yields a pair of splines that steer an object’s animation: an onscreen motion path (spacial) plus a Time spline shown in the Spline Editor (temporal).
- Perturb: Produces smooth, continuously shifting random animation on a chosen parameter.
- Probe: Auto-animates a parameter by reading the color or luminosity of a particular pixel, or a rectangular patch, of an image.
- Publish: Linking two un-animated parameters starts with the Publish modifier publishing a parameter. From there, other parameters can reach the Connect To submenu and tie themselves to the published one.
- Resolve Parameter: Lets you alter how long a Fusion transition template runs straight from the Edit page Timeline. Rather than keyframing the transition, you apply the Resolve Parameter Modifier to any animated parameter.
- Shake: Much like Perturb, Shake puts out smooth, continuously shifting random animation on a chosen parameter.
- Track: Pins a single-point tracker onto the chosen parameter. That tracker can then follow an object across the screen to animate the parameter. It is faster and more direct than the usual Tracker node, though less flexible, since the tracker amounts to just one point and serves only the parameter it is attached to.
- Vector Result: Akin to the Offset modifier, Vector Result offsets position parameters by way of origin, distance, and angle controls in order to form a vector. That vector is then available to drive any other parameter.
- XY Path: Yields an X and a Y spline in the Spline Editor for animating an object’s position..

For fuller detail on every modifier Fusion offers, turn to Chapter 124, “Modifiers,” in the DaVinci Resolve Reference Manual, along with Chapter 64 in the Fusion Reference Manual.

### Performing Calculations in Parameter Fields

Straightforward math equations can be typed right into a number field to work out the value you are after. Enter 2.0 + 4.0 into most number fields, for instance, and you land on a value of 6.0. That comes in handy whenever you want one parameter to equal the total of two others, or some fraction of the screen resolution.

### Using SimpleExpressions

A Simple Expression is a distinct kind of script that can sit right beside the parameter it governs. They earn their keep for working out modest calculations, wiring up one-way parameter links, or doing both together. To create a SimpleExpression, type an equals sign straight into the parameter’s number field and then press Return.

Typing an equals sign brings up the SimpleExpression field together with its Pick Whip control A blank field opens beneath the parameter, while a yellow marker shows up off to the left. Meanwhile the parameter’s present value gets dropped into the number field. With Simple Expressions you can write a math formula that drives a parameter’s value, or even bind two separate parameters together. It comes in handy whenever an animation is too hard — or simply impossible — to build through keyframing. To make an object pulse, for one, apply the sine and time functions to a Size parameter. Divide the time function to ease the pulsing down; multiply it to quicken the beat.

### A SimpleExpression using the sine and time functions

Within the SimpleExpression text box you may write single-line Lua scripts that lean on a bit of Fusion-specific shorthand. A handful of Simple Expressions, shown with their syntax, follow:

### Expression time Merge1.Blend

Merge1:GetValue("Blend", time-5)

### Description

This hands back the current frame number. This hands back the value of a separate input, Blend, taken from a separate node, Merge1. This hands back another input’s value as well, only sampled at a different frame — here, the point five frames earlier than the current one.

### Expression

Description

sin(time/20)/2+.5

This yields a sine wave ranging from 0 to 1.

iif(Merge1.Blend == 0, 0, 1)

When the Blend value equals 0 this gives back 0; otherwise it gives back 1. The iff() function serves as shorthand for a conditional, the if-then-else construct.

iif(Input.Metadata.ColorSpaceID == "sRGB", 0, 1)

Should the image feeding the current node’s Input carry the sRGB colorspace tag, this gives back 0. With no other node name spelled out, the expression takes the Input to be arriving from the current node — making it the same as self.Input. Across most Fusion nodes, though not every one, the Input is the principal image input that the Node Editor draws as an orange triangle. Images carry members you are able to read off, among them Depth, Width, Metadata, and the like.

Point(Text1.Center.X, Text1. Center.Y-.1)

In contrast to the earlier cases, what comes back here is a Point rather than a Number. A Point input draws on two members, X and Y. For this case, the Point handed back sits 1/10 of the image height beneath the Text1’s Center. That can prove handy when forging one-way parameter links, such as nudging one Text away from another.

Text1.Center - Point(0,.1)

This one closely resembles the expression just above. Here the SimpleExpression hands back Text in place of a Number or Point.

Text("Colorspace: "..(Merge1. Background.Metadata.ColorSpaceID)

Whatever text sits within the quotes gets joined onto the metadata string, which might yield: Colorspace: sRGB

`Text("Rendered "..os.date("%b %d, %Y").. " at "..os.date("%H:%M").."\n on the computer "..os. getenv("COMPUTERNAME").. " running "..os. getenv("OS").."\n from the comp "..ToUNC(comp.Filename))`

This produces a far longer Text, along the lines of: Rendered Nov 12, 2019 at 15:43 on the computer Rn309 running Windows*NT from the comp \\ SRVR\Proj\ Am109\SlateGenerator* A01.comp

os.date("%H:%M")

A range of details about the machine can be drawn from the OS library. Up above, os.date fetches the date along with the time in hours:minutes.

"..os.getenv("COMPUTERNAME").. " running "..os.

os.getenv will read back any environment variable you ask for — here, the machine’s name together with its operating system.

"\n from the comp "..ToUNC(comp.Filename)

A \n is what inserts a fresh line into the Text. By way of the comp variable you can reach assorted attributes of the comp — the filename among them, given here as a UNC path.

TIP: With lengthy SimpleExpressions, you may find it useful to pull the Inspector panel out so it grows wider, or to copy/paste by way of a text editor or the Console. Once you have set an expression that drives animation, the Spline Editor can be opened to watch the values charted across time. It is a sound way to gauge how your SimpleExpression resolves from frame to frame.

A sine wave shown in the Spline Editor, produced by the expression driving Text1: Size To learn more about composing Simple Expressions, consult the Fusion Studio Scripting Guide along with the official Lua documentation.

### Pick Whipping to Create an Expression

While a SimpleExpression field stands open, a + button shows along its left edge. Drag that + button over onto another control — an act known as "pick whipping" — and the two parameters become tied together, much as the Connect To menu would do. The difference is that, where a Connect To link is fixed, the pick whip lets you reshape the connection by editing the expression further.

Pick whipping as a fast way to wire one parameter to another You can also build and edit SimpleExpressions from inside the Spline Editor. In the Spline Editor, right-click the parameter and pick Set SimpleExpression off the contextual menu. The SimpleExpression then gets charted within the Spline Editor, letting you watch the outcome across time.

### Removing SimpleExpressions

Getting rid of a SimpleExpression is a matter of right-clicking the parameter’s name and picking Remove Expression off the contextual menu.

### Customizing User Controls

Within the Inspector, every tool lays its parameters out in a sensible sequence. Controls you reach for most sit nearer the top, while the finer tuning controls fall further down the list. Now and then, though, you will want to add, conceal, or alter those controls. SimpleExpressions and macros frequently call for it, but you might also do it on favorites and presets purely for usability or appearance. You add or revise custom controls through the Edit Control dialog, reached by right-clicking the node’s name in the Inspector and selecting Edit Controls from the menu.

### Choose Edit Controls to create and customize parameters

Inside the Edit Control dialog, the ID menu is where you either pick an existing parameter or spin up a fresh one. From the Type attributes list you give the control a name and settle whether it behaves as a text field, a number field, or a point.

### Edit Control dialog

The page list is how you drop the new control onto one of the Inspector’s tabs. Further settings fix its defaults and ranges, plus whether it gets an onscreen preview control. Settings tied to the chosen Type live in the Input Ctrl box, while the View Ctrl attributes box holds whatever onscreen preview controls are meant to show, if any. Everything you change in the Edit Controls dialog is held within the current tool instance, which means it can be copied/ pasted onto other nodes throughout the comp. Carrying those changes into other comps, though, means saving the node settings and filing them into the Bins in Fusion Studio or among your favorites. By way of illustration, we will tailor the controls of a DirectionalBlur:

### The Inspector for a default direction blur

Suppose we wanted a more hands-on means of steering a linear blur out in the viewer, in place of reaching for the Length and Angle sliders back in the Inspector. By way of a SimpleExpression, we will steer the length and angle parameters using the Center parameter’s onscreen control in the viewer. Such a SimpleExpression would read roughly thus: For Length: `sqrt(((Center.X-.5)*(self.Input.XScale))^2+ ((Center.Y-.5)*(self.Input.YScale)*(self.Input.Height/self.Input.Width))^2)` For Angle: `atan2(.5-Center.Y , .5-Center.X) * 180 / pi`

DirectionalBlur driven by where the Center sits.

Granted, this is a fairly advanced function, but it performs well enough. Dragging the onscreen control sets both the angle and the length of the directional blur. The trouble now is that the parameter names mislead. The Center parameter no longer behaves as a center at all; it stands for the blur’s direction and length, so "Blur Vector" would suit it better. Since the Length and Angle controls no longer need editing, they ought to be tucked out of sight, and because this is strictly a linear blur, the Type menu has no need of Radial or Zoom — Linear and Centered are the only choices we require. The Edit Controls dialog makes such changes simple. To rework the example’s Inspector parameters along these lines: 1 Within the Edit Control dialog, choose Center out of the ID list. 2 A dialog appears asking whether you mean to Replace, Hide, or Change ID; we will go with Replace. 3 Rename it to Blur Vector. 4 Set its Type to Point. 5 Under the Page list, pick Controls. (Normally Controls is the Inspector’s first tab.) 6 Click OK.

The DirectionalBlur Center parameter has had its name swapped to Blur Vector. That new Blur Vector parameter now shows up in the Inspector. Because the control’s internal ID stays Center, our SimpleExpressions went untouched. To conceal the Length and Angle parameters within the Inspector: 1 Within the Edit Control dialog, pick Length out of the ID list. 2 Choose Controls under the Page list. 3 From the input Ctrl list, choose Node. 4 Click OK. 5 Back in the Edit Control dialog, this time pick Angle from the ID list. 6 Again from the input Ctrl list, choose Node. 7 Click OK.

Lastly, to strip the Radial and Zoom options out of the Type menu: 1 In the Edit Control dialog, pick Type from the ID list. 2 Choose Controls under the Page list. 3 In the Items list, highlight Radial and press Del to drop it. 4 In the Items list, highlight Zoom and press Del to drop it. 5 Click OK. Only two options remain in the Type menu now. Should you prefer to swap the Type menu out for a fresh checkbox control, you can manage that with one new control plus a tiny expression. To build a new control: 1 Within the Edit Control dialog, enter Center Blur in the Name field. 2 From the ID list, choose New Control. 3 With Type set to Number, point the Page at Controls. 4 For its Input Ctrl, choose CheckboxControl. 5 Click OK. So that this fresh checkbox drives the original Type menu, you must hang a SimpleExpression off the Type: iif(TypeNew==0, 0, 2) In Lua script, the "iif" operator goes by the name conditional expression. It weighs something according to whether a condition holds true or false.

### FusionScript

As a route to higher productivity, scripting is indispensable. Scripts can unlock new abilities or take over repetitive chores, above all the ones peculiar to your own projects and workflows. Within Fusion, a script might reshuffle the nodes in a comp, look after caches, and turn out several output files ready for delivery. They can also bridge Fusion to other applications — logging an artist’s hours, firing off emails, or refreshing web pages and databases. The umbrella name for Fusion’s scripting environment is FusionScript. It supports Lua, and in certain contexts Python 2 and 3 as well. FusionScript furthermore bundles libraries that smooth over many routine jobs you would otherwise do by hand in Lua and Python inside Fusion. Interactive scripts can be run under a variety of circumstances. Among the common ones:

- Utility Scripts, which run in the Fusion application context, sit under the File > Scripts menu.
- Comp Scripts, which run in the composition context, sit under the Script menu, or you type them

into the Console.

- Tool Scripts, which run in the tool context, sit within the Tool’s context menu > Scripts.

Still other script kinds exist too — these include SimpleExpressions, Intool Scripts, and Hotkey Scripts, as well as Event Suites, Bin Scripts, Scriptlibs, and Startup Scripts. Beyond that, Fusion Studio permits external and commandline scripting, plus Job and Render node scripting for network rendering. FusionScript likewise underpins Fuses and ViewShaders, the specialized scripting-driven plugins for tools and viewers usable across both Fusion and Fusion Studio. For deeper detail on scripting, turn to the Fusion Scripting Documentation, reachable from the Documentation submenu within the Help menu.
