# Combining Keys And Using Mattes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

How the composition looks within the Color page Node Viewer When you right-click the Node Editor's background and pick Add Source, a second source shows up over on the left side of the Node Editor.

Bringing in the matte output of the MediaOut2 node from the Fusion page composition via an added source This second source lines up with the second MediaOut node you placed in the Fusion page composition, the one that sends the Matte out as a key over in the Color page, where it behaves just like any other key. Hover your pointer over each source and a tooltip pops up telling you which output goes with which node.

Resting the pointer on a source names it through a tooltip As a rule, the sources run from top to bottom following the order of MediaOut nodes in the Fusion composition, first through last. From here, you can wire the second Source into the Key input of a second corrector node, then lean on that key to grade only the woman up front (her grade pushed hard for emphasis) while sparing the background. Here the Viewer has Splitscreen set to Highlight Modes, letting you view both the outcome and the key coming off the Fusion page that Node 2 relies on.

Wiring the second source into a second Corrector node's KEY input so the matte confines a correction to the foreground character

### Using the Key Mixer

With the Key Mixer node you can blend the keys put out by several Corrector nodes, joining them through various methods to yield one key output. That opens the door to far more elaborate keys than a lone qualifier or a set of four windows could ever give you. Notably, the Key Mixer node stands as the sole means of fusing several keys built from qualifiers and windows, whether you add, subtract, or intersect them to arrive at a tightly targeted result.

### Adding Two Keys Together

The walkthrough below shows you how to wire up a Key Mixer that blends the keys put out by two Corrector nodes within a node tree. After that, you'll see how to alter the manner in which those input keys get blended by way of the Key palette. To blend two or more keys through the Key Mixer: 1 Anywhere on the Node Editor's gray backdrop, right-click and pick Add Node > Key Mixer. 2 Make two Corrector nodes, wire their RGB inputs to the RGB output of a fitting node in the main body of the tree, and run their key outputs into the key inputs of the Key Mixer. 3 After that, run the key output of the Key Mixer node into the key input of whichever node you intend to use for the correction. Bear in mind, the whole point is to take the key the Key Mixer puts out and use it to rein in the adjustment another node is making, here Node 3.

Building the node tree required to blend two keys into one

Bear in mind, all the more so because this involves a major rearrangement of nodes within the Node Editor, that each node has to be hooked up correctly for the grade as a whole to function. 4 With the node structure now fully wired, draw on windows, qualifiers, or a mix of both to build keys in each of the nodes you tied to the Key Mixer. Here, Node 2 picks out the primary skin tone while Node 5 picks out the blue of his jeans and hood. By default, every key feeding the Key Mixer gets summed together, which the Key Mixer's thumbnail makes visible.

### Combining multiple keys with the Key Mixer

Should you wish, the controls in the Key palette let you alter that behavior so as to isolate where two keys overlap, or to take one key away from another. The next section walks through this. 5 Sticking with the earlier setup in which both keys are summed by default, choosing Node 3 and dialing the saturation way down stylizes the whole background while sparing the assorted hues of the man we singled out.

The finished grade, with the talent in color against a B&W background

### Subtracting One Key from Another

How several keys merge inside the Key Mixer hinges on a pair of Key Input buttons you flip through the Key palette. Take the example below, where a qualifier washes a partial green tint across the image's midtones, yet you'd like to keep the man's skin tone out of that operation. The Key Mixer makes it easy to pull one key out of another to manage exactly this.

A targeted blue tint laid over the image's midtones takes in the red sign. To alter the Key Input settings on a node wired to a Key Mixer: 1 Here, Node 2 picks out a portion of the image's midtones and routes its key through the Key Mixer to Node 4, which uses it to lay down a partial blue tint. To set up the removal of the skin tone from that operation, though, Node 3 picks out the man's skin tone. A node arrangement readied for pulling the Bar sign out of the midtone isolation that's being used to introduce a partial blue tint 2 To bring up the controls you'll need to govern how Node 3's key plays against Node 2's key, double-click the Key Mixer node so it's selected. 3 Open the Key palette; over on the right appears a list of every input link tied to the Key Mixer.

The Key Mixer node's list of inputs

4 Every list entry holds the input name (Input Link 1, Input Link 2, etc.), plus an offset parameter, a gain parameter, a Mask control, and a Matte control. To take Node 3's key away from Node 2's: For Input Link 2, switch on both the Key Input Matte button as well as the Key Input Invert button.

Switching on Matte and Invert for Input Link 2 so the output is Node 3 subtracted from Node 2 To take Node 2's key away from Node 3's: For Input Link 1, switch on both the Key Input Matte button as well as the Key Input Invert button. Switching on Matte and Invert for Input Link 1 so the output is Node 2 subtracted from Node 3 To narrow the output down to where both keys overlap: For either Input Link 1 or Input Link 2, switch on the Key Input Matte button.

Switching on Matte for Input Link 1 to put out the intersection of two mattes

To flip the matte you've just produced: Switch on the Output Link Invert button. Once you're done, should you opt to take Node 3's key away from Node 2's, the outcome ought to look like the screenshot below.

What you get from removing a key of the man's face from a key covering the image's midtones overall, then using it to introduce a targeted green tint

### Adding Inputs to Key Mixer Nodes

A fresh Key Mixer node ships with two key inputs by default. When you need them, extra inputs can be tacked on so you can blend still more keys together. To tack inputs onto the Key Mixer:

- Drag the Key Output from a corrector node to the Key Mixer.
- Right-click a Key Mixer node, and choose Add One Input.

Once you're blending three or more keys, how those keys play together under the Key palette controls grows more tangled, yet the principles spelled out above hold just the same.

### Using the Key Palette

Take the Key Input Invert control, for instance: it's switched on automatically whenever you add an Outside node, and that's precisely why the Outside node works its adjustments on the area opposite the previous node. Switch the control off and that node's key becomes an exact copy of the original key handed to it by the prior node. Which controls show up in the Key palette shifts according to the type of node you've selected: Corrector Nodes: Carry three groups of parameters. By way of the Key Input parameters you tune keys arriving over a node's Key Input connection. By way of the Key Output parameters you tune the key data departing a node's Key Output connection, and they take in the remarkably potent Offset Gain parameter that dictates how strongly that node weighs into the grade as a whole. Lastly, the Qualifier parameters let you tune the internal key built with the HSL Qualifier or Window controls. The next section treats this in greater depth. Ext Mattes: Carry two groups of parameters. The Transform parameters let you apply geometric transformations to a matte so it conforms better to the clip it's laid over. An Offset control lets you nudge the sync between an external matte and the clip it's applied to. The section on external mattes treats this. Key Mixer Nodes: Carry two groups of parameters whose makeup depends on which of the connections feeding a Key Mixer's key inputs is highlighted. The Input parameters let you set how much a key adds to the total key mix and whether that contribution is additive or subtractive. The Output parameters let you set the inversion and strength of the key the Key Mixer puts out. The Key Mixer section treats this in greater depth. Layer Mixer and Parallel Mixer nodes offer no adjustable controls in the Key palette.

### Using the Key Palette to Affect Corrector Nodes

Opening the Key palette while a Corrector node is selected gives you these parameters to adjust:

The Key palette and its controls as they appear with a node selected

### Key Input Controls

- Input invert: Flips the key arriving at the key input. Off by default.
- Input matte: Toggles the key input between Matte and Mask modes. Under Matte mode (on by default) the key input merges by intersection with keys made internally through the Qualifier or Windows palette. Under Mask mode, the key input is instead summed onto the internal key.
- Gain: Sets the strength of the key wired to the key input.
- Offset: Sets the contrast of the key wired to the key input.
- Blur Radius: Softens the key wired to the key input
- Blur H/V Ratio: Changes the horizontal-to-vertical ratio of the blur being laid on the key input.

### Key Output Controls

- Qualifier invert: Flips the key as a whole.
- Gain: Acting on the key output, this parameter dictates how strongly that node figures into the grade as a whole. With Gain at 0 the node does nothing whatsoever, whereas the default of 1.00 lets the node's adjustments come through at full strength. Pushed to its ceiling of 2.00, it boosts the intensity of any portion of the key output sitting below 100 percent white. This parameter can also keyframe the key output, fading that node's contribution in or out across a single set of keyframes.
- Offset: Lets you tune the contrast of the Output key. It does nothing when the whole key is 100 percent white (a solid key).

### Qualifier Controls

- Qualifier invert: Flips the key produced by that node's Qualifier palette.
- Qualifier matte: Lets you flip how the keys from the Qualifier and Window palettes interact between Matte and Mask modes. Under Matte mode (the default), the Qualifier and Windows palettes merge by intersection. Under Mask mode, they're summed together instead.
- Gain: Lets you push the strength of the key from the Qualifier palette up or down.
- Offset: Lets you tune the contrast of the key from the Qualifier palette.

### Using the Key Palette to Adjust Key Mixer Controls

Opening the Key palette while a Key Mixer node is selected gives you these controls to adjust:

The Key palette and its controls as they appear with a Key Mixer selected

- Input list: A roster of every input wired to the Key Mixer. Each row on the roster carries these controls:

Input name: The label of each node connection attached to that key mixer, like Input Link 1, Input Link 2, and so forth. Input invert: Flips the key arriving at this specific input. Off by default. Input mask: Toggles the key input between Matte and Mask modes. Under Matte mode (on) the key input merges by intersection with the other inputs wired to the Key mixer. Under Mask mode (off by default), the key input is summed onto the other key inputs wired to the Key mixer. Gain parameter: Dials the strength of that input matte's share of the resulting output matte up or down. Offset parameter: Tunes the contrast of that input matte's share of the resulting output matte.

- Output invert: Flips the combined upshot of all the various Input Link interactions.
- Gain: This parameter raises or lowers the strength of the resulting output key. With Gain

set to 0 it drives every input to black, whereas the default of 1.00 sends out the merged mattes at full strength. Pushed to its ceiling of 2.00, it boosts the intensity of any portion of the key output below 100 percent white, which in practice can “grow” soft edges. This parameter can likewise keyframe the key output, fading that node's contribution in or out across one set of keyframes.

- Offset: Lets you tune the contrast of the Output key.

### The Many Uses of Key Output Gain

A number of the methods covered here and over in “Secondary Qualifiers,” can be tailored even further through the Key Output Gain parameter, which makes it simple to govern how strongly a node bears on your grade with one move. For the example below, a clip gets two plain Serial nodes, the first widening image contrast while the second leans on assorted controls to pour intense warmth into the highlights.

A tint laid over the image's highlights alone Were you to decide you wanted to cut back the warmth the second node introduced without reworking the controls you used to build the effect, you could open the Key palette and bring the Key Output Gain parameter down to fade the effect in a single move.

A side-by-side look at four takes on this grade through the Split Screen controls' Versions option, each at a different Output Gain — 1, .75, .5, and.25 This same idea applies to governing the strength of individual nodes combined in parallel, of nodes combined through the Layer node, or simply to dialing back the effect of any node in the node tree you'd like to “turn down” a touch.
