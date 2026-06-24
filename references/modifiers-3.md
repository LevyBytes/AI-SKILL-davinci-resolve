# Modifiers (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

The Perturb modifier produces smoothly shifting random values for a chosen parameter, driven by Perlin noise. You can lean on it to introduce jitter, shake, or wobble into any animatable parameter, even one that's already animated. The outcome resembles what the Shake modifier delivers, though Perturb relies on a different, perhaps more intuitive, set of controls. Setting it apart from the other random modifiers, the Perturb modifier applies to polylines, shapes, grid meshes, and even color gradients. As an example, to layer camera shake onto an existing path, right-click the crosshair, pick Insert > Perturb, then trim the Strength down to taste. As another route, right-clicking the path's “Right-click here for shape animation” label down at the foot of the Inspector lets you put perturb on the path's polyline. That works best with a polyline holding plenty of points—say one that's been tracked or hand-drawn using the Draw Append pencil tool. A third option uses the Insert contextual menu to drop the modifier onto the Displacement control. The motion along the path then jitters to and fro without ever straying off the path.

NOTE: Perturb is only able to introduce jitter; smoothing out existing animation curves is beyond it.

### Inspector

### The Perturb modifier Controls tab

### Controls Tab

For Perturb, the Controls tab mostly handles the Strength, Wobble, and Speed parameters of the random jitter. Value Whatever this control holds hinges on the type of control the modifier was placed on. Should the Perturb modifier have gone onto a basic Slider control, the Value appears as a slider. Should it have gone onto a Gradient control, a Gradient control shows here instead. Use it to fix the default, or center, value the Perturb modifier acts on.

### The Perturb modifier Gradient controls

Jaggedness (Polylines and meshes only) This lets you raise how much variation runs along the length of the polyline or mesh, as opposed to over time. A higher Jaggedness yields a squigglier polyline or a more tangled mesh, separate from its movement. Phase (Polylines and meshes only) Animating this can shift the ripple of a polyline or mesh along its own length, from one end to the other. The effect reads most plainly when Speed sits at 0.0. Random Seed Randomize The Random Seed serves to “seed” how much jitter the modifier applies. Two Perturb modifiers sharing identical settings but holding different random seeds turn out two utterly different results. Click the Randomize button to drop in a random seed value. Strength This control tunes the strength of the Perturb modifier's output, that is, its largest deviation from the primary value set above. Wobble The Wobble control dictates how smooth the resulting values come out. Less wobble means a smoother handoff between values, whereas more wobble yields less predictable results. Speed Raising the Speed slider value quickens the rate at which the value shifts. It can heighten the apparent wobbliness more predictably than the Wobble control does, lending the jitter a more frantic or languorous character.

### Probe

The Probe modifier ranks among the most versatile modifiers in Fusion. It lets you steer any numeric parameter by the color or luminosity of a particular pixel or rectangular patch of an image. Picture driving the Brightness node off the pixel values of flickering lights in a shot, or gauging graded LUTs to compare values. You apply it by right-clicking a parameter and picking Modify With > Probe.

### Inspector

### The Probe modifier Controls tab

### Controls Tab

For the Probe modifier, the Controls tab lets you choose the node to probe, set the channel that drives the parameter, and govern how big the probed patch is. Image to Probe Drag a node out of the Node Editor into this field to name the image to probe. Channel Pick the channel you'd like to probe. The usual choices run:

- Red
- Green
- Blue
- Alpha

Luma With a Probe modifier sitting somewhere in your comp, you can wire other nodes' values to its outputs too. The Probe lets you tap into its values one by one:

- Result
- Red
- Green
- Blue
- Alpha

Position X Y Where in the image the probe draws its samples from. Probe Rectangle Out of the box, the Probe reads only the value of a single pixel at its position. Switch on the Probe Rectangle mode and you can sample across a wider patch of pixels based on the Evaluation method. Width Height Controls These set how large the patch to be probed is. Evaluation Decides how the pixels inside the rectangle get crunched into the output value. The choices cover:

- Average: All pixel values inside the rectangle are averaged.
- Minimum: The smallest value of all pixels inside the rectangle is used.
- Maximum: The highest value of all pixels inside the rectangle is used.

### The Probe modifier Value tab

### Value Tab

The Value tab governs the modifier adjustment's range or scale, thereby setting how sensitive the Probe is. Scale Input By default the Probe puts out the Black Value when the probed patch comes to a value of 0 (that is, black), and it puts out its White Value when the probed patch comes to a value of 1 (that is, white). This range control lets you reshape the Probe's sensitivity. Black Value The value the Probe puts out should the probed patch return the result set in Scale Input Black. White Value Whatever the Probe emits once the probed patch yields the result fixed under Scale Input White. Out of Image Value Whatever the Probe emits once the probed patch sits beyond the frame boundaries of the probed image. When probing a rectangle, this value won't be produced until the whole rectangle lies beyond the frame boundaries of the image being probed.

### Publish

Only parameters that carry animation are reachable from the Connect To menu. To wire up non-animated parameters, you first have to Publish them. Animated controls get published on their own, while static controls call for manual publishing. To publish a static control, right-click it and pick Publish out of the contextual menu.

### The Publish modifier Controls tab

### Controls Tab

The Controls tab presents the published control on offer for linking to other controls. Published Value How the published control displays naturally depends on which control was published from which node.

### Resolve Parameter

The Resolve Parameter Modifier comes into play when you build a transition template in Fusion meant for DaVinci Resolve's Edit page or Cut page. As you construct a transition in Fusion, the Resolve Parameter modifier gets attached to whichever control you wish to animate. The Resolve Parameter modifier animates that parameter automatically across the transition's length, letting you trim the transition over on the Edit page or Cut page. As an instance, building a cross dissolve goes like this: 1 Out of the Effects Library, drop a Fusion Composition onto the Edit page Timeline. 2 Within Fusion, drop a Dissolve node into the Node Editor. 3 Over in the Inspector, right-click the Background/Foreground parameter, then pick Resolve Parameter out of the Modifier contextual menu. With the modifier on the Background/Foreground parameter, the slider updates by itself any time the transition is altered back on the Edit/Cut page. 4 Within the Node Editor, right-click the Dissolve node and pick Macro > Create Macro. 5 Whenever the macro you're building will act as a Fusion transition, the Macro Editor needs two inputs plus one output selected. Beneath the Dissolve heading here, tick the boxes for Output, Background and Foreground. 6 Name the transition, after which you store the macro via the top File menu.

7 Drop the macro into the folder below so the Edit page or Cut page Effects Library lists it. On MacOS the destination is `$TEMPLATE_MAC_OS_PATH/Transitions`, or alternatively `$TEMPLATE_MAC_ USER_PATH/Transitions`. Should you be running Windows instead, place it under `$TEMPLATE_WIN_OS_PATH\Transitions`, or else `$TEMPLATE_WIN_ USER_PATH\Transitions`. 8 Close and relaunch DaVinci Resolve so the transition list in the Effects Library updates. 9 On the Edit page, open the Effects Library. Browse to Video Transitions Fusion Transitions, and your custom Fusion transition shows up there.

### Shake

The Shake modifier serves to randomize a Position or Value control so semi-random numeric inputs come out. The shake that results can be wholly random. The motion may also be smoothed for a gentler, more organic feel. To put the Shake modifier on a parameter, pick Modify With > Shake from that parameter's contextual menu. The Shake modifier draws on the following controls to pull off its effect. You apply it by right-clicking a parameter and picking Modify With > Shake.

### Inspector

### The Shake modifier Controls tab

### Controls Tab

Random Seed The Random Seed control holds the value that seeds the random number generator. Hand it the same seed and a random number generator always turns out the same results. Swap the seed whenever the randomizer's results don't satisfy. Smoothness This control smooths the overall randomness of the Shake. A higher value renders the motion smoother. A value of zero yields wholly random results, with no smoothing applied at all. Lock X/Y This checkbox unlocks the X- and Y-axis, exposing independent slider controls per axis.

Minimum and Maximum This control fixes the shake's overall strength. The low values stand for the lowest value the randomizer can produce, and the high values stand for the highest. To make a Shake that sends a center crosshair anywhere across the image, put the Minimum at 0.0 and the Maximum at 1.0. To pen the motion into a smaller shake at the image's bottom-right corner, put the Minimum at 0.70 and the Maximum at 0.90.

### Example

- Create a new comp, and then add and view a Text node.
- Type some text in the Text node.
- Inside the viewer, right-click atop the text's Center control and pick Modify With >

Shake Position.

- Over in the Inspector, open the Modifiers tab and dial the smoothing to 5.0.
- Set the Minimum to 0.1 and the Maximum to 0.9.

That layers some chaotic movement onto the text. We can shift this over time, though Move to frame 0 and, inside the Inspector, click the Keyframe button alongside the Minimum together with the Maximum controls.

- Head to frame 0 and, within the Inspector, click the Keyframe button sitting beside both the Minimum and the Maximum controls.
- Head to frame 90 and reset the Minimum to 0.45 along with the Maximum to 0.55.
- View the results.

Now the text kicks off flying all across the screen and draws in toward the screen's center as the comp runs.

### Track

While a standalone Tracker node exists, a Tracker modifier can also be used to attach a tracker straight onto a parameter. To apply the Tracker modifier, head into the viewer and right-click the Center control belonging to any transform, text, mask, or similarly positionable element. Out of the contextual menu, pick Object x Center > Modify With > Tracker. Then settle on one of three options:

- Tracker Position: Tracks a point from the source.
- Steady Position: Stabilizes based on a single point in the source.
- Unsteady Position: Adds original motion back after stabilizing.

That places a modifier in the Inspector carrying a set of controls nearly the same as those in the Tracker node itself.

### Inspector

### The Tracker modifier

For a thorough rundown of this node, turn to Chapter 119, "Tracking Nodes," within the DaVinci Resolve Reference Manual; the Fusion Reference Manual covers it in Chapter 59.

### Tracker Modifier vs. Tracker Node

Here's how a Tracker modifier and a Tracker node differ:

- The Tracker modifier can only track a single pattern.
- The Tracker modifier emits just one value, leaving it unsuited to intricate stabilization or match-moving work.
- For the modifier, the default source image is the node directly upstream of the one holding the modifier (so, when adding a Tracker modifier onto a Glow node fed by a Loader, the Tracker Source input defaults to the Loader's output). Point the Tracker modifier at a different source image by typing in the node's name. Or else, drag the source node out of the Node Editor into the Text Box control.

### Example

Suppose you have to track an actor's eyes so an otherworldly, alien glow can be laid over the eyes.

- Select the Loader node.
- Add a Glow node.
- Put an Ellipse mask onto the Glow, shaped to match one of the eyes.
- Right-click that mask's center, then choose Modify With > Tracker > Position.

Because the track rides on the mask, the tracker treats the glow as its tracking image. That could spell trouble, since the glow may heavily obscure the eye. A cleaner source is the Loader feeding the glow.

- Drag the Loader into the modifier Inspector's Track Source field.
- Track the actor's eye.
- Perform the same steps on the other eye.

### Vector Result

The Vector Result modifier serves to offset positional controls, crosshairs among them, by distance and angle. These can be static or animated values. You apply it by right-clicking a control and picking Modify With > Vector.

### Inspector

### The Vector Result modifier Controls tab

### Controls Tab

Origin This control marks the position the vector's distance and angle values spring from. Distance This slider control fixes how far the vector reaches from the origin. Angle This thumbwheel control fixes the vector's angle relative to the origin. Image Aspect This slider control mainly exists to offset image aspect differences. For a square image of 500 x 500 the Image Aspect value would be 1, whereas a rectangular image of 500 x 1000 would call for an Image Aspect value of 2. This value defaults to what the current Frame Format preferences supply via width/height. You may have to alter this control to fit the current image.

### Example

- Create a 100-frame comp.
- Build a plain node tree out of a black background plus a Text node foreground

connected to a Merge.

- Enter some text in the Text node.
- Select the Merge node.
- Inside the viewer, right-click the Merge's Center control and pick Modify With >

Vector Result. That drops a crosshair onscreen control governing the Vector distance and angle. This onscreen control corresponds to the Distance and Angle controls displayed in the Modifiers tab.

- Within the Modifiers tab of the Inspector, drag the Distance control so the text moves away from the Vector origin.
- Drag the Angle thumbwheel so the text swings around the Vector origin.
- Unlike adjusting a pivot point, here the text itself does no rotating.
- Those points accept animation and may be wired to other controls.
- Over in the Inspector, right-click the Origin control and pick a path so a motion path

modifier joins the Origin control.

- Confirm the current frame reads frame 0 (zero), then either use the Origin controls in the

Inspector or drag the Vector Origin crosshair down to the screen's bottom-left corner.

- On the Vector Angle thumbwheel, click the Keyframe button so this control animates.
- Set the Angle thumbwheel to a value of 10.
- Move to frame 100 and click the screen's top-left corner to shift the

Vector Origin crosshair.

- Set the Vector Angle thumbwheel to a value of 1000.
- Play the comp to see the results.

That sends the text orbiting around the path you've just made.

### XY Path

The XY Path type relies on two separate splines, one for position along the X-axis and one for position along the Y-axis. To animate a coordinate control via an XY path, right-click the control and pick Modify With > XY Path from the contextual menu. On first look, XY paths behave like Displacement paths. To lay out the path, switch frames and place the control where it belongs on that frame, then switch frames once more and shift the control to its next spot. Fusion fills in the interpolation between the points for you. The distinction is that the onscreen path receives no keyframes. The X and Y channel splines turn up inside the Spline Editor. Whatever changes you make to the control's values get keyframed on those splines. The upside of the XY path is how simple it makes working with motion along one individual axis.

### Inspector

### XY Path modifier controls

X Y Z Values These mirror the animated control's position through X, Y, and Z values. Center The path's actual center. This too can be modified and animated to shift the whole path about. Size The path's size. Again, this permits later modification of the animation. Angle The path's angle. Again, this permits later modification of the animation. Heading Offset Should another control (a mask's Angle, for example) be wired to the path's heading, this control lets you add to or subtract from the computed angle. Plot Path in View Switches on or off whether the actual path shows in the views. Switching Default Paths You can swap the Default Path type to XY path (when that's your preferred animation type). Open the Default category within the Global Preferences and find the Point With drop-down menu. Switch it from its current value to XY Path. The next time Animate gets chosen from a Coordinate control's contextual menu, an XY path serves in place of a Displacement path.
