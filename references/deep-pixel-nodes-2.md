# Deep Pixel Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Motion Blur: This switches the tool’s Motion Blur rendering on or off. With the control enabled, the blur is generated from the tool’s estimated motion as it would appear through the virtual camera’s shutter. Leave the control disabled and nothing is blurred.
- Quality: This figure sets how many samples go into building the blur. Choosing a value of 2 for example prompts Fusion to lay down a pair of samples on each flank of an object’s true path. Bigger numbers yield cleaner output at the cost of longer renders.
- Shutter Angle: This dictates how wide the virtual shutter opens while the motion blur effect is generated. Wider angles yield heavier blur while pushing render times up. Setting it to 360 matches a shutter held open across one entire frame of exposure. You may go beyond that, which opens the door to some interesting effects.
- Center Bias: This shifts where the midpoint of the motion blur falls, making motion-trail looks achievable.
- Sample Spread: Tweaking this control changes how heavily each sample counts, which in turn alters how bright the samples appear.

Comments The Comments field lets you attach notes to a tool. Click inside the field and enter your text. Once a tool carries a note, a tiny red square shows up in the node’s lower-left corner while the full tile is on screen, or a little text-bubble icon shows on the right side once nodes are collapsed. Hovering the mouse pointer over the node surfaces the tooltip so you can read the note inside the Node Editor. Scripts Every Fusion tool offers three Scripting fields, reached through the Settings tab. Each one holds an edit box where you can drop scripts that run while the tool renders. Turn to the Fusion scripting documentation if you need fuller detail on scripting nodes.
