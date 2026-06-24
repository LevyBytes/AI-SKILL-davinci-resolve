# Modifiers (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Whatever Number Input 1..9 holds. The X belonging to Positional Control 1..9. The Y belonging to Positional Control 1..9. Where you are in time now (the frame number). What pi equals. What e equals. Logarithm of x to base 10. Logarithm of x to base e (the natural one). Sine of x, with x given in degrees. Cosine of x, with x given in degrees. Tangent of x, with x given in degrees. Arcsine of x, returned in degrees. Arccosine of x, returned in degrees. Arctangent of x, returned in degrees. Arctangent of x,y, returned in degrees. How big x is regardless of sign (its absolute value). x rounded to its whole-number part. The part of x past the decimal point. The Square Root of x. Some random figure that lands between x and y. Some random figure between x and y, governed by seed s. Whichever of x and y is smaller. Whichever of x and y is larger. How far apart point x1,y2 and x2,y2 are. How far apart the 3D points x1,y2,z1 and x2,y2,z2 are

`noise(x)` `noise2(x, y)` `noise3(x, y, z)` `if(c, x, y)`

A Perlin noise figure that varies smoothly off x A Perlin noise figure that varies smoothly off x and y A Perlin noise figure that varies smoothly off x, y and z Hands back x when c isn't 0, and y when it is.

### Expression Syntax Operators

You lean on operators to work out statements. Pair them with functions, and you can carry out logical and mathematical work inside the Number Out and Point Out tabs.

x+y x-y x>=y x>y !x -x +x x^y xy xy x%y x>=y x>=y x=y x == y x<>y x != y x&y x && y x|y x || y

x and y summed. x with y subtracted. Yields 1.0 when x falls below y, else 0.0. Yields 1.0 when x exceeds y, else 0.0. Yields 1.0 when x = 0, else 0.0. (0.0 - x). (0.0 + x) (which changes nothing in practice). x taken to the power y. x times y. x over y. x mod y, that is the remainder left after (x divided by y). Yields 1.0 when x is at most y, else 0.0. Yields 1.0 when x is at least y, else 0.0. Yields 1.0 when x equals y precisely, else 0.0. Yields 1.0 when x equals y precisely, else 0.0 (same as the previous one). Yields 1.0 when x differs from y, else 0.0. Yields 1.0 when x differs from y, else 0.0 (same as the previous one). Yields 1.0 when neither x nor y is 0.0, else 0.0. Yields 1.0 when neither x nor y is 0.0, else 0.0 (same as the previous one). Yields 1.0 when at least one of x or y isn't 0.0, else 0.0. Yields 1.0 when at least one of x or y isn't 0.0, else 0.0 (same as the previous one).

Example 1 To tie a numeric control to a motion path's Y value, attach an expression to whichever control you're targeting and wire the Path into Point In 1. Type the formula p1y into the Number Out field. Example 2 So that the Expression's Number Out gives back the greater of Number In 1 and Number In 2, scaled by the cosine of Number In 3, plus Point In 1's X coordinate, drop the formula max(n1, n2) * cos(n3) + p1x straight into Number Out. Example 3 Add a Background node that's solid black alongside a Hotspot node. Set its Hotspot size at 0.08 and crank the Strength to the top. Drive the Hotspot center with an expression. Move the current frame to 0. Park n1 at 0.0 and add a Bézier Spline. At frame 29, raise the value of n1 up to 1.0. Select both points, then loop that spline via the Spline Editor. Now feed these equations into the expression's Point Out tab. For the X-Axis Expression put `n1`, and for the Y-Axis Expression put `0.5 + sin(time*50)`. 4 Render a quick preview and have a look at how it came out. (Worth trying this one with motion blur switched on.)

### From Image

The From Image modifier acts only on gradients — the sort of gradient sitting on a Background node, say. It reads samples off an image along a line you lay out yourself and builds a gradient out of those samples. From Image differs from the other modifiers in that you won't find it in the Modify With menu. You apply this modifier by right-clicking a Gradient bar in the Inspector and picking From Image.

### Inspector

### From Image modifier

### Controls Tab

You use the From Image controls tab in the Inspector to choose which node holds the image you mean to sample. There you set where the line begins and ends in the image, plus how many color samples build the gradient. Image to Scan Drag the node you want color-sampled out of the Node Editor and into this box. Start X/Y, End X/Y This pair of point controls fixes the Start and End of the line that the samples are drawn along, from whatever image you named in the Image to Scan box. You can also shift the points right in the viewer. Number of Sample Steps This sets how many separate color samples get taken across the line. The effect of this setting is also visible if you check the node's own Gradient control. Define more sample steps here, and more individual color stops show up on the Gradient control. You can even build a gradient with the From Image modifier first and then strip that modifier back off the Gradient control. The gradient you built survives intact and is then open to manual fine-tuning. Edges Edges governs what happens at the image's edges once the sample line runs past the actual frame of the image being sampled. Black This sends out black at every spot on the sample line that sits beyond the image bounds. Wrap This loops the line's edges around the image's borders. Duplicate This makes the image's edges repeat as faithfully as it can, extending the image past its native size. Color This puts out a color of your choosing rather than black at every spot on the sample line lying beyond the image bounds.

### Example

On the left, the source image displays the color selection line in red. On the right, the image shows the gradient that selection produced.

### Gradient Color

With the Gradient Color modifier you build a gradient of your own and map it across a chosen time range so it drives a value. Set the animation's frames with the Start and End time controls. When both the Start and End time values sit at 0, the modifier hands back the value at the gradient's starting point. The Offset control lets you animate the gradient by hand. You apply it by right-clicking a parameter and picking Modify With > Gradient Color.

### Inspector

### The Gradient modifier Controls tab

### Controls Tab

A Gradient bar makes up the Controls tab, and that's where you add and tune the gradient's points. The Start Time and End Time thumbwheels down at the foot of the Inspector set which time range the gradient maps into. Gradient The Gradient control is a bar on which you can add, change, and delete the gradient's points. Every point carries its own color. Both that color and the point's position can be animated. On top of that, a From Image modifier can be hung on the gradient so it's read out of an image. Gradient Interpolation Method By default the gradient runs a straight linear interpolation from one point to the next within RGB color space. Now and then that throws up colors you didn't want. Picking a different color space may give a nicer outcome. Repeat Sets how the gradient's left and right borders behave.

From top down, gradients on Once, Repeat, and Ping Pong respectively, with the gradient pushed leftward.

- Once: As you shift the gradient with the Gradient Offset control, the border colors hold their values. Pushing the default gradient left gives a white border on the left; pushing it right gives a black border on the right.
- Repeat: As you shift the gradient with the Gradient Offset control, the border colors loop around. Pushing the default gradient left makes a hard jump from white to black; pushing it right makes a hard jump from black to white.
- Ping Pong: As you shift the gradient with the Gradient Offset control, the border colors bounce to and fro. Pushing the default gradient left has the edge fade from white back into black; pushing it right has the edge fade from black back into white.

Gradient Offset Lets you scroll across the gradient. Time Controls The Start Time and End Time thumbwheels set which time range the gradient maps into. You give this in frames. You can reach the same result by putting the Gradient on Once and animating the offset thumbwheel.

### Key Stretcher Modifier

The Keyframe Stretcher modifier mainly comes into play while you're building title templates in Fusion meant for DaVinci Resolve's Edit page or Cut page. You attach the Keyframe Stretcher modifier to an animated parameter, so that parameter's keyframes stretch whenever the template gets trimmed on the Timeline. You apply it by right-clicking a parameter and picking Modify with > KeyStretcher. For fuller detail on the Keyframe Stretcher Modifier controls, turn to "Keyframe Stretcher" — that's "Miscellaneous Nodes," Chapter 111 of the DaVinci Resolve Reference Manual, or Chapter 51 over in the Fusion Reference Manual.

### MIDI Extractor

The MIDI Extractor modifier lets you drive a control's value off the data held inside a MIDI file. Using it assumes a bit of MIDI know-how, which this manual won't cover. The value the modifier puts out is pulled from whatever MIDI event you pick in the Mode menu. You can trim each mode so it only processes certain messages for that event — say, processing some notes while skipping others. Extra factors such as Scale, Velocity, Attack, and Decay can scale or reshape that value further. You apply it by right-clicking a parameter and picking Modify With > MIDI Extractor.

### Inspector

### The MIDI Extractor modifier Controls tab

### Controls Tab

You use the Controls tab to load the MIDI file, reshape its timing, and decide which MIDI messages and events drive changes in the Fusion parameter. MIDI File This browser control points to the MIDI file fed into the modifier as its input. Time Scale Time Scale sets the ratio between time the way the MIDI file states it and time the way Fusion states it. At 1.0 the MIDI events run at ordinary speed, at 2.0 they run twice as fast, and so on. Time Offset Time Offset tunes the sync between the MIDI file's timing and Fusion's timing. Should there be an unexpected lag, or should the MIDI file need to begin partway into or ahead of some animation in Fusion, this control can shift the MIDI data however you need.

Result Offset, Result Scale These sliders set the span of values the modifier puts out. By default it generates values from 0 to 1 (or -1 to 1 when in PitchBend mode). That won't always fit the node/parameter, and scale can widen the span (for instance \* 0.0 - 2.0). Offset supplies a fixed value to sit on as a base. Result Curve The Result Curve is another way to shape the output. What it changes, though, is the curve of the result. By default, whatever MIDI data comes in, the results land linearly from 0.1 to 1.0 (so a velocity 127 note gives 1.0, while 63 gives roughly 0.5). The Result Curve lays a gamma-like curve over things so the middle values can yield higher or lower results without losing the full scale. Mode This menu offers Beat, Note, Control Change, Poly AfterTouch, Channel AfterTouch, or Pitch Bend, marking which MIDI event the values get read from. Beat mode stands a little apart in that it puts out steady pulses keyed to the MIDI file's tempo (any tempo maps included). The Beat mode draws on no particular messages; it times its events off the tempo map held in the MIDI file. Combine Events This menu decides what to do when several events land at once. That comes up readily in Notes mode. With other events, it comes up if Multiple Channels are picked. Use it to take the result from the latest event to fire, the oldest one still going, the highest- or lowest-valued event, or the average, sum, or median of every event happening just then. Beat (Quarters) (Beat Mode Only) This sets how frequently a beat lands while in Beat mode. It's stated in quarter notes, so 1.0 gives one beat per quarter. Note Range (Note and Poly Aftertouch Modes Only) This sets which span of notes will produce a value. For instance, isolate the kick drum out of a GM drum track by putting the note range at 35–36. Pitch Scale (Note Mode Only) Pitch Scale sets how strongly the result shifts with pitch. At 1.0 the result ranges across 0.0 to 1.0 over the whole span. Velocity Scale (Note Mode Only) This sets how strongly the result shifts with velocity. At 1.0 the result ranges across 0.0 to 1.0 over the whole span. It gets added onto the Pitch Scale result to form the final result. Control Number (Control Change Mode Only) This names the MIDI controller number that events are pulled from. Envelope Controls (Note and Beat Modes Only) These map out an Envelope that values follow leading up to, throughout, and trailing each note or beat. Pre-Attack Time sets how far ahead of the event it begins ramping up toward the pre-attack level. Attack is the Time/ Level it ramps to once the event has fired, then comes the Decay ramp and Sustain, lasting until the event ends. That stage applies to Notes alone. Beats last no time at all, so it jumps straight to

Release. Release is how long it takes to ramp down after the event wraps up. For a Beat, give Release some value or there probably won't be much beat to hear. You can use these values to trail the real sounds in the MIDI sequence, or simply to spin up interesting effects. Every time value in the MIDI Extractor is given in seconds.

### The MIDI Extractor modifier Channels tab

### Channels Tab

The Channels tab is where you pick which Channels the modifier draws on. Channels The Channels checkboxes pick which of the MIDI file's 16 channels actually count toward events. This is a handy way to pull one specific instrument out of an arrangement.

### About MIDI

One MIDI interface carries 16 channels. As a rule, these go to separate instruments inside one device or to separate devices. MIDI data is normally 7 bits, spanning 0–127. Fusion shows this as a value from 0–1, to stay in step with how Fusion handles data elsewhere. Plenty of distinct MIDI messages and events exist, but the ones that matter most with this modifier are spelled out below.

### MIDI Messages

Note On: This marks a note (on a given channel) coming on; it carries a pitch (0–127, where middle C is 60) and a Velocity (0–127, capturing how hard the key or strings or whatever got struck). Note Off: This marks a note (on a given channel) going off; it carries a pitch (0–127, where middle C is 60) and a Velocity (0–127, capturing how hard the key or strings or whatever got let go). Control Change: This message signals that some controller has moved. There are 128 controllers (0–127), each holding data from 0–127. Controllers set parameters like Volume, Pan, the amount of Reverb or Chorus, and general things such as foot controllers or breath controllers.

### MIDI Events

Channel Aftertouch: This event marks pressure landing on the keys (or strings or whatever) over the course of a note. It stands for the general, all-over pressure on this channel, so it just carries a pressure value (0–127). Poly Aftertouch: This event marks pressure landing on the keys (or strings or whatever) over the course of a note. It applies to each individual note, so along with a pressure value (0–127) it also carries a note number.

### Pitch Bend

What the Pitch Bend controller usually states is how much pitch bend or variation gets laid on the note. Since pitch bend values travel as 14-bit values, this control spans -1 to 1 and carries a correspondingly finer resolution.

### Natural Cubic Spline

The Natural Cubic Spline counts among Fusion's animation modifiers and is normally laid on numerical values rather than point values. You apply it by right-clicking a numerical control and picking Modify With > Natural Cubic Spline. NOTE: Cubic splines, unlike the other spline types, carry no control handles. They try on their own to draw a smooth curve passing through the control points.

### Usage

Because it's an animation spline, this modifier carries no real Controls tab. You can still see and shape its effect, though, within the Spline Editor.

### Natural Cubic Spline Editor

### Offset (Angle, Distance, Position)

There are three Offset modifiers for building differences between values. Which values those are — controls, paths, or points — depends on the modifier. Fusion's three kinds of Offset modifier are:

- Offset Angle
- Offset Distance
- Offset Position

Offset Angle The Offset Angle modifier puts out a value from 0 to 360 keyed to the angle separating two positional controls. The Position and Offset parameters can hold still, link to other positional parameters, or link to paths of their own. Every offset shares one set of controls, which act differently according to the offset type in use. Those controls get covered below. Offset Distance The Offset Distance modifier puts out a value keyed to the gap between two positional controls. This modifier can put out a value derived from a mathematical expression laid on a position. Offset Position The Offset Position modifier makes a position (X and Y coordinates) keyed to how positional controls relate. This modifier works like a calculation control, except it puts out X and Y coordinates in place of a value. You apply it by right-clicking a control and picking Modify With > Offset.

### Inspector

### The Offset Position modifier controls

### Offset Tab

All three Offset modifiers share the very same Inspector. The Offset tab carries Position and Offset values along with a Mode menu for choosing which mathematical operation the offset control runs. Position X and Y The X and Y values that Position feeds into the calculation. Offset X and Y The X and Y values that Offset feeds into the calculation. Flip Position Horizontal and Vertical Switch these on and the Position gets mirrored across the image's vertical or horizontal axis. Flip Offset Horizontal and Vertical Switch these on and the Offset position gets mirrored across the image's vertical or horizontal axis. Mode The Mode menu holds the mathematical operations the Offset control runs. The choices on offer are:

- Offset
- Difference (Position - Offset)
- Difference (Offset - Position)
- Average Use Position Only
- Use Offset Only
- Maximum
- Minimum Invert Position
- Invert Offset
- Invert Sugar
- Random Offset

Image Aspect Tunes the modifier's output to make up for the project's image aspect (not pixel aspect). A square 500 x 500 image takes an Image Aspect value of 1, while a rectangular 500 x 1000 image takes an Aspect Value of 2. The default always follows whatever frame format is currently picked in the preferences. Work out image aspect by dividing the width by the height. You can also bend this control to fake the look of aspect.

### Time Tab

### The Offset Time tab

Position Time Scale This hands back the Position's value at whatever Time Scale you name (0.5, say, gives its value at the halfway point of the present frame time). Position Time Offset This hands back the Position's value at whatever Time Offset you name (10, say, reaches 10 frames earlier). Offset Time Scale This hands back the Offset's value at the Time Scale you name. Offset Time Offset This hands back the Offset's value at the Time Offset you name.

### Example

Here's a basic comp showing one way offsets might come in handy.

- Make a fresh Comp running 100 frames.
- Build a node tree where a black background and a foreground Text node both feed

to a Merge.

- Over in the Text Layout tab, drive the text across the frame with the Center X control, taking it from one edge

over to the other.

- Jump to frame 0.
- Inside the Text tab in the Inspector, right-click the Size control and pick Modify With > Offset

Distance off the contextual menu. That drops in two onscreen controls: a crosshair standing for the position and an X control standing for the offset. Those onscreen controls mirror the Position and Offset controls shown in the Modifiers tab. From here the text's size rides on the gap, or offset, separating the two onscreen controls.

- Drag the X onscreen control around in the viewer and watch how its distance from the crosshair drives the size of the merge, and through that the text. The crosshair and the X onscreen controls are both animatable and can link to other controls.
- Position the X centered at the bottom of the viewer.
- In the Inspector, select the Modifiers tab.
- Within the Offset on Text size section, right-click on Position and pick Connect To >

PathConnect the Offset's position value onto the path that's already present by right-clicking the Position control and selecting Connect To > Path1 Position.

- Play the comp to view the animation.

Now the text contracts toward the middle of the path (where the gap between the offset and the path bottoms out) and swells at the path's ends (where that gap between the offset and the path peaks).

### Path

Two splines drive the Path modifier's animation of points: an onscreen motion path (spacial) and a Time spline you see in the Spline Editor (temporal). To put an object's position control under a Path's control, right-click that Position control (in the Inspector, or else in the viewer) and choose Path from the contextual menu. That lays a keyframe at the present position. Begin a path by moving the playhead and dragging the center position control around the viewer. The Spline Editor shows a displacement spline for editing the path's temporal value, its "acceleration."

### Inspector

### The Path modifier Controls tab

### Controls Tab

The path's Controls tab lets you scale, move, and rotate the path. It also carries the Displacement parameter, which lets you govern the acceleration of an object riding the path. Center Where the path actually centers. This too can be changed and animated to slide the whole path around. Size How big the path is. Once again, this leaves the animation open to later changes.

X Y Z Rotation The path can turn across all three dimensions for sophisticated control. Displacement Every motion path comes paired with a Displacement spline in the Spline Editor. The Displacement spline marks where the animated element sits along its path, given as a value from 0.0 to 1.0. You use Displacement splines to govern how fast — or how accelerated — an object's travel along the path is. To slow, hasten, halt, or even back up the control's motion along the path, change the values of the points for the path's displacement, whether in the Spline Editor or in the Inspector.

- When the Displacement reads 0.0 in the Spline Editor, the control sits right at a path's start.
- When it reads 1.0, the control has reached the path's far end.
- Every locked point along the motion path in the viewer is paired with a point on the

Displacement spline.

- Unlocked points show a control point in the viewer yet carry no matching point on the

Displacement spline. Heading Offset Wiring to the Heading tunes how the object auto-orients along the path. So, for example, when a mask's angle is wired to the path's heading, the mask's angle swings to match the path's angle. Right-Click Here for Shape Animation You can animate the shape of the path too, or wire it to other path controls such as Polyline Masks or Paint Strokes. TIP: Switching Default Paths You're free to change which default path type gets used when you animate a position or center control to a path (should you favor that kind of animation). Open the Preferences window and pick the Global Settings. Under the Default category, open the Point With menu and choose Path. From then on, choosing Animate from a Position or Center control's contextual menu brings up a path.

### Perturb
