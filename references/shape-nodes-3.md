# Shape Nodes (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Inspector view of an sStar node wired into an sDuplicate node, with the result shown through an sRender node

### The sStar Controls tab

### Controls

On the Controls tab you set the star shape’s attributes: how many points it has, its depth, fill, border, dimensions, and where it sits. Points This slider sets how many points (arms) the star carries. Depth The depth slider governs the inner radius, or arm thickness. Set depth to 0.001 for razor-thin arms; push it to 1.0 to get a faceted circle instead. Solid Tick the Solid checkbox and the star fills with whatever color you set on the Style tab. Untick it and you get an outline drawn by the Border Width control, with a transparent middle. Border Width This control grows or shrinks the border ringing the shape. It works whether or not Solid is ticked, but its real job is setting outline thickness once the checkbox is cleared. Border Style The Border Style parameter dictates the way the star’s sides meet at each corner. Three style choices are offered. Bevel flattens the corners. Round gives you rounded corners. Miter keeps the corners pointed. Cap style With the Solid checkbox cleared, three cap style choices appear. These caps end the lines with flat, rounded, or squared finishes. A flat cap ends square and abrupt, whereas a rounded cap finishes in a semicircle. A squared cap juts past the line’s end by half the line width. You won’t see any caps unless length drops under 1.0. Position The Position parameter shows up only while the Solid checkbox is cleared. Use it to set where the shape’s starting point lands. Paired with the length parameter, it moves where the gap in the outline falls. Length The Length parameter also appears only with the Solid checkbox cleared. At a length of 1.0 the shape is closed. Drop length under 1.0 and you carve an opening or gap into the outline. Keyframe the Length parameters and you can build write-on style animations. X and Y Offset These parameters slide the shape left, right, up, and down across the frame. Because the shape begins centered in the frame, these parameters shift it away from that center. Offset coordinates scale to the frame width, so an X offset of 0.0 sits dead center while 0.5 drops the shape’s center right onto the frame’s right edge. Width/Height The Width and Height parameters fix the star’s vertical and horizontal extent. Match the two values and every arm of the star comes out the same length. Angle The Angle parameter spins the shape around its center axis.

### FUSION 2712

### Style Tab

### The sStar Style tab

### Style

Use the Style tab to give the shape its color and dial in transparency. Color The Color controls set the fill and border color coming out of the sStar node. Pick a shape color by clicking the color disclosure arrow and working the color swatch, or by dragging the eye dropper over the viewer to sample a color straight from an image. With the RGBA sliders or number fields you type in a value for each color channel, or set how strong the Alpha channel is. Allow Combining Tick this checkbox and the Alpha channel value holds steady, even after the shape flows through downstream nodes that let it overlap duplicates of itself. Leave it cleared and overlapping the shape with itself can drive the Alpha channel value upward. Say a star’s Alpha channel reads .5: turning on the Allow Combining checkbox keeps that reading intact even when the shape runs through a duplicate or grid node that overlaps the shape and its Alpha channel. Clear the checkbox instead and the Alpha channel values stack up wherever the overlaps occur.

Allow Combining Enabled (left), Allow Combining Disabled (right)

### Common Controls

Settings Tab Every Shape node shares the Settings tab found in the Inspector. The “The Common Controls” section, at this chapter’s close, walks through those shared controls thoroughly.

### sText [sTxt]

### The sText node

### Introduction

Built for the Fusion Shape environment, the sText node is a powerful character generator that handles many styles, 3D transformations, and multiple shading layers. Think of the sText node as the “Shape” counterpart to the 2D Text+ node. Its controls line up almost exactly with the 2D version across the board, the one exception being that sText offers no gradient colors.

The sText controls

### sTransform

### The sTransform node

The sTransform node layers a further set of transform controls on top of those already built into Shape nodes. Those extra transforms let you build hierarchical animations. As an example, a sStar’s own Angle control can spin the star in place. You then feed that star out to an sTransform node. From there the sTransform’s rotation control sends the star orbiting around the frame. As with nearly every Shape node, the sStar node’s output is only visible once it runs through a sRender node.

### External Inputs

On the node’s tile in the Node Editor you’ll find this input: Input1: [orange, required] It takes in the output coming from a second Shape node. Whatever shape you wire here gets moved, scaled, and rotated according to the sTransform settings.

### Basic Node Setup

Fed by another Shape node’s input, the sTransform node tacks on a further set of transforms, or hierarchical animation. Route the sTransform’s output into a sRender to view it and carry on compositing.

Inspector view of an sStar node wired into an sTransform node, with the result shown through an sRender node

### The sTransform Controls tab

### Controls

Use the Controls tab to apply a set of transform controls to the shape coming in. X and Y Offset These parameters move the shape left, right, up, and down within the frame. Since the shape begins at the frame’s center, these parameters nudge it off that center. Offset coordinates scale to the frame width, so an X offset of 0.0 stays centered while 0.5 drops the shape’s center onto the frame’s right edge. X and Y Size The X and Y Size fix how the incoming shape scales vertically and horizontally. Make the two values differ and the shape skews away from its original form. Rotation Turning the dial rotates the shape around the pivot controls. X and Y Pivot These parameters set where the rotation axis sits for the incoming shape. You can spot the pivot point in the viewer as a red X. Drag that X inside the viewer to reposition it. Transform Axis Tick this box to apply the transform onto the shape’s axis.

### Common Controls

Settings Tab All Shape nodes carry the same Settings tab inside the Inspector. You’ll find a full account of these shared controls in the “The Common Controls” section that closes out this chapter.

### Common Controls

In the Inspector, the various Shape-operation nodes hold a set of matching controls. What follows covers the controls that Shape nodes have in common.

### Settings Tab

Every Shape node carries the Settings tab in the Inspector. The bulk of the controls shown here live solely on the sRender node, though a handful apply to all Shape nodes. Blend (sRender only) Use the Blend control to mix between the tool’s original image input and the tool’s final processed output. At a blend value of 0.0, the image leaving the tool matches the one coming in. As a rule, that makes the tool bypass processing altogether and pipe the input straight through to the output. Process When Blend Is 0.0 (sRender only) Here the tool still processes even with the input value at zero. That helps when this node’s processing is scripted to kick off some other task while the node’s own value sits at 0.0.

Red/Green/Blue/Alpha Channel Selector (sRender only) This quartet of buttons confines the tool’s effect to whichever color channels you pick. Typically the filtering happens once the tool has already run. Take a Blur tool: clear its red button and the blur still hits the whole image first, after which the red channel from the original input is laid back over the red channel of the output. A few tools behave differently — clearing a channel there makes the tool skip that channel’s processing outright. Such tools usually carry their own matching RGBA buttons over on the tool’s Controls tab. When that happens, the buttons on the Settings tab and the Control tab do the same thing. Apply Mask Inverted (sRender only) Switching on Apply Mask Inverted flips the tool’s entire mask channel. That mask channel is what you get after combining every mask either wired into or generated within a node. Multiply By Mask (sRender only) Pick this option and the masked image’s RGB values get multiplied by the values of the mask channel. Every pixel left out of the mask (that is, set to 0) then turns black/transparent. Motion Blur (sRender only)

- Motion Blur: Switches motion-blur rendering on the tool on or off. Switched on, the tool reads its predicted motion to generate the motion blur a virtual camera’s shutter would cause. Switched off, you get no motion blur at all.
- Quality: Sets how many samples go into building the blur. At a quality setting of 2, Fusion lays down two samples on each side of an object’s real motion. Bigger values smooth the result but lengthen the render time.
- Shutter Angle: Governs the angle of the virtual shutter that drives the motion-blur effect. Wider angles add more blur but push render times up. Set it to 360 and the shutter stays open across one full frame exposure. You can go higher still, which opens the door to some interesting effects.
- Center Bias: Shifts where the center of the motion blur falls. With it you can produce motion-trail effects.
- Sample Spread: Tweaking this control changes how much weight each sample carries. That in turn shifts the brightness of the samples.

Use GPU (sRender only) The user GPU menu offers three choices. Choose Disable to switch off hardware-accelerated rendering on your computer’s graphics card. Auto taps a capable GPU whenever one exists and drops back to software rendering when none is on hand. Hide Incoming Connections Tick this checkbox to tuck away the connection lines running in from upstream nodes, which leaves the node tree tidier and quicker to read. With it on, the Inspector shows an empty field for each of a node’s inputs. Drag a connected node out of the node tree onto that empty field and the incoming connection line stays hidden, provided the node isn’t selected in the node tree. Select the node in the node tree and the line shows up again.

Comments Use the Comments field to attach notes to a tool. Click into the blank field and type your text. Once a tool has a note, a small red square shows in the node’s lower-left corner while the full tile is on screen, or a small text-bubble icon appears at the right when the nodes are collapsed. To read the note inside the Node Editor, rest the mouse pointer on the node so the tooltip pops up. Scripts From the Settings tab, every tool in Fusion offers three Scripting fields. Each one holds an edit box where you enter scripts that run as the tool renders. The Fusion scripting documentation has more on scripting nodes.
