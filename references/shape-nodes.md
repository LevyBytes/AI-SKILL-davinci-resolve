# Shape Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Shape Nodes

This chapter walks through the Shape nodes that Fusion offers.

### sBoolean

### The sBoolean node

The sBoolean node merges or removes the overlapping regions of two shapes according to a menu of boolean operations. As with nearly every shape node, the sBoolean node's output is only viewable through a sRender node.

### External Inputs

The node's tile in the Node Editor presents the inputs below. Apart from the subtract boolean operation, which shape goes to which input doesn't matter. Input1: [orange, required] This input takes the output of another shape node. It acts as the base shape once the subtract boolean operation is selected. Input2: [green, optional] This input takes the output of another shape node. It carves the hole out of the base shape once the subtract boolean operation is selected.

### Basic Node Setup

The sBoolean node serves to fuse two shape nodes together. From there, the sBoolean's output can route on to another shape node or a sRender node for viewing.

A star and an ellipse merged within an sBoolean node, then sent to an sRender for viewing and further processing Inspector

### The sBoolean Controls tab

### Controls

The Controls tab mostly exists to pick the boolean operation governing how the two shapes merge. Operation The operation menu carries four boolean operations: Intersection: Now and then called an AND operation, this setting reveals only the regions where the two shapes overlap. What you get is solely where input 1 AND input 2 overlap.

A star and ellipse with the sBoolean node in intersection mode Union: Now and then called an OR operation, this setting reveals only the regions where either of the two shapes lives. What you get is wherever input 1 OR input 2 exists. The Union setting resembles the result of the sMerge node.

A star and ellipse with the sBoolean node in union mode Subtract: Now and then called a NOT operation, this setting outputs input 1's shape but strips away the regions where input 2 overlaps. What you get is input 1 minus input 2.

A star and ellipse with the sBoolean node in subtract mode

Xor: Now and then called an AND NOT operation, this setting outputs input 1's or input 2's shape but strips away the regions where they overlap. What you get is (input 1 minus input 2) + (input 2 minus input 1).

A star and ellipse with the sBoolean node in xor mode Style Mode The Style mode menu carries just one option. The Replace setting swaps the color and alpha level of the incoming shapes for the color set within the Style tab.

### Style Tab

### The sBoolean Style tab

### Style

Whatever color was assigned to the individual shape nodes gives way to the color set through the Style tab controls. Color The color controls fix the color of the output shape coming from the sBoolean node. To pick a shape color, click the color disclosure arrow, work the color swatch, or drag the eyedropper into the viewer to lift a color out of an image. With the RGBA sliders or number fields you can key in each color channel's value or the Alpha channel's strength.

### Allow Combining

With this checkbox on, the Alpha channel value holds steady even while passing through downstream nodes that might overlap the shape with copies of itself. With it off, the Alpha channel value can climb wherever the shape overlaps itself. For example, if an ellipse's Alpha channel reads .5, turning on the Allow Combining checkbox preserves that value even when the shape moves through a duplicate or grid node that overlaps it. Leaving the checkbox off lets the Alpha channel values compound at each spot of overlap. When the sBoolean node is in play, the individual shape node checkboxes are disregarded, and the sBoolean node's own checkbox dictates the Alpha channel's behavior.

Allow Combining Enabled (left), Allow Combining Disabled (right)

### Common Controls

Settings Tab The Settings tab in the Inspector is shared across every Shape node. Those common controls get a full treatment at this chapter's close in the “The Common Controls” section.

### sBSpline [sBSp]

### The sBSpline node

Introduction sBSpline matches a sPolygon in every way but one. Where sPolygon relies on Bézier splines, this node relies on B-Splines. Whereas Bézier splines lean on a central point plus two handles to govern the smoothing of a spline segment, a B-Spline needs only a single point. As a result, a sBSpline shape calls for far fewer control points to land a nicely smoothed shape.

### Usage

### The sBSpline controls

When first dropped into a Node Editor, the sBSpline shape holds only its Center control, shown onscreen. You add points to the sBSpline by clicking in the viewer. Every new point links to the one made before it, but rather than the spline running straight through each control point, sBSpline control points merely sway the spline's shape. Each control point tugs the spline toward itself to form a smooth curve. Much like the sPolygon shape tool, the sBSpline shape auto-animates. Dropping this node into the Node Editor lays a keyframe on the current frame. Stepping to a new frame and altering the shape lays a new keyframe and interpolates between the two defined shapes.

### sChangeStyle [sCS]

The sChangeStyle node sChangeStyle Node Introduction The sChangeStyle node applies a fresh style across the merged shape tree, replacing whatever style—color plus Allow Combining settings—was set up in the upstream shape tools.

### Inputs

The single input on the sChangeStyle tool serves to connect the Shape node whose style you intend to change.

### Basic Node Setup

Wire the output of the shape whose style you want to alter into the input. The node's output then carries on to the rest of the shape node tree.

A basic node tree where the sChangeShape node receives an sEllipse shape's output, applies the style change, and forwards it onward to the sRender node.

### Inspector

### The sChangeStyle controls

### Controls

The Style tab handles assigning color to the shape and managing its transparency. Color The Color parameter controls fix the color of both fill and border coming from the sPolygon node. To pick a shape color, click the color disclosure arrow and work the color swatch, or drag the eye dropper into the viewer to lift a color out of an image. With the RGBA sliders or number fields you can key in the value of each color channel or the Alpha channel's strength. Allow Combining With this checkbox on, the Alpha channel value holds steady, even while passing through downstream nodes that might overlap the shape with copies of itself. With it off, the Alpha channel value can climb wherever the shape overlaps itself. For example, if a rectangle Alpha channel reads .5, turning on the Allow Combining checkbox preserves that value, even when the shape moves through a duplicate or grid node that overlaps the shape and Alpha channel. Leaving the checkbox off lets the Alpha channel values compound at each spot of overlap.

Allow Combining enabled (left), Allow Combining disabled (right)

### sDuplicate

### The sDuplicate node

The sDuplicate node makes copies of the input shape, shifting each copy's position, size, and rotation. As with nearly every shape node, the sDuplicate node's output is only viewable through a sRender node.

### External Inputs

On the node's tile inside the Node Editor sits the input below: Input1: [orange, required] This input takes the output of another Shape node. Whatever shape you wire here gets copied and offset per the controls in the Inspector.

### Basic Node Setup

The sDuplicate node accepts one input, typically a lone shape or a compound one arriving out of a sMerge or sBoolean node. The sDuplicate node copies the incoming shape and offsets the copies to form a pattern. Its output may then head onward to a further shape node, or into a sRender node, for viewing or for compositing within the wider node tree.

An sEllipse shape feeding an sDuplicate and then routed to an sRender to view and blend with other elements

### Inspector

### The sDuplicate Controls tab

### Controls

The Controls tab is where you set the number of copies and dial in their position, size, and rotation offset. Copies This slider fixes how many copies the node makes. That number leaves out the original shape, so entering a value of five gives you five copies on top of the original. Copy Probability This slider tunes the likelihood of a duplicate shape. Time Offset Reach for the Time Offset slider to shift any animation applied to the source geometry by a set amount per copy. For instance, set the value to –1.0 with a cube rotating on the Y-axis as the source. The first copy displays the animation from one frame earlier; the second copy displays animation from a frame before that, and so on. This can pay off nicely on textured planes—for instance, where consecutive frames of a clip get shown. X and Y Offset These sliders fix the X and Y distance separating the copies. Each copy is offset from the one before it by whatever value you entered in the X and Y number fields. The copies all begin at 0, the center of the original shape, and offset outward from there. With Fusion's normalized coordinate system, entering X Offset at 0.5 would push each copy half the frame's width rightward. Entering -1.0 would slide each copy leftward by a full frame width.

X and Y Size Fixes the X and Y size offset relative to the previous shape's size. As an example, an X and Y value of 1.0 makes copies the same size as the original but. Entering an X and Y of 0.5 makes each copy half the size of the one before it. Axis Mode The Axis mode menu hands you four options governing how each copy works out its rotational pivot point.

- Absolute: Lets you fix an X and Y position for the rotation axis relative to where the original shape sits. That rotation axis is then copied and offset along with each duplicated shape.
- Origin Relative: Every copy takes its own center point as its rotation axis.
- Origin Absolute: Every copy takes the original shape's center as its rotation axis.
- Progressive: Builds up each shape copy by transforming it step by step from the

position, rotation, and scale of the shape before it. X and Y Pivot The X and Y pivot controls surface once the Axis mode reads Absolute. These position controls let you set where the rotation axis lands. Rotation Sets an offset rotation laid on each copy. That rotation is figured from the offset rotation of the copy preceding it. To spin every copy the same way, turn to the Angle parameter on the original shape or bring in a sTransform node. Style A set of color-picking tools for tinting the duplicate shapes.

### Duplicate Jitter tab

### Jitter Tab

The options in the Jitter tab let you randomize the position, rotation, size, and color of every copy made over in the Controls tab.

Random Seed The Random Seed slider together with the Reseed button generate a random starting point governing how much jitter falls on the duplicated objects. A pair of Duplicate nodes sharing identical settings but holding different random seeds produce two completely distinct outcomes. Click Reseed to mint a new random starting point. Center X and Y This pair of controls adjusts the amount of variation entering each duplicate's X and Y position. Pivot X and Y This pair of controls adjusts the amount of variation entering each duplicate's rotational pivot center. It affects only the extra jitter rotation, leaving alone whatever the Rotation settings on the Controls tab produce. Size This control adjusts the amount of variation entering each duplicate's Scale. Tick the Lock size box to pin this parameter. Angle This dial adjusts the amount of variation entering each duplicate's Z rotation. Gain The Gain RGBA controls multiply the image channel values at random, in a linear fashion. Blur Edits here randomize the blur from one object to the next.

### Common Controls

Settings Tab The Settings tab in the Inspector is shared across every Shape node. Those common controls get a full treatment at this chapter's close in the “The Common Controls” section.

### sEllipse

### The sEllipse node

The sEllipse node serves to build circular shapes. As with nearly every shape node, the sEllipse node's output is only viewable through a sRender node.

### External Inputs

This node generates shapes and does not have any inputs.

### Basic Node Setup

Being a shape generator, the sEllipse node produces a shape and so carries no input. The sEllipse's output can feed a sRender for viewing and further compositing, or—more commonly—hook into another shape node such as sGrid or sDuplicate. An sEllipse node feeding an sGrid node, the result then viewed by way of an sRender node Inspector

### The sEllipse Controls tab

### Controls

You use the Controls tab to set the elliptical shape's traits—fill, border, size, and placement. Solid With the Solid checkbox on, the elliptical shape fills with whatever color you defined in the Style tab. With it off, only an outline drawn by the Border Width control shows, and the middle turns transparent. Border Width This parameter grows or shrinks the border running around the shape. Though usable while the Solid checkbox is on, its main job is governing outline thickness once the checkbox is off. Cap style With the Solid checkbox off, three cap style options appear. Those cap styles let lines end flat, rounded, or squared off. Flat caps finish with flat, squared ends, whereas rounded caps finish with semi-circular ends. Squared caps carry projecting ends reaching half the line width past the line's end. None of the caps show up unless the length sits below 1.0.

Position Only when the Solid checkbox is off does the position parameter appear. It lets you set the shape's starting point. Paired with the length parameter, it places the gap in the ellipse outline. Length Only when the Solid checkbox is off does the length parameter appear. A length of 1.0 yields a closed shape. Dropping the length under 1.0 opens a gap in the outline. Keyframing the length parameters lets you build write-on style animations. X and Y Offset You use these parameters to shift the shape left, right, up, and down across the frame. The shape begins at the frame's center, and the parameters offset that placement. The offset coordinates are normalized to the frame's width. An X offset of 0.0 sits centered, and a value of 0.5 drops the shape's center right onto the frame's right edge. Width/Height The width and height fix the vertical and horizontal size of the ellipse. When the values match, you've got a perfect circle. Angle The angle spins the shape, which on a perfect circle barely alters the image, but if you make an oval or a short-length outline, you can rotate the shape around its center axis.

### Style Tab

### The sEllipse Style tab

Style The Style tab handles assigning a color to the shape and managing its transparency. Color The color controls fix the color of both fill and border. To pick a shape color, click the color disclosure arrow, work the color swatch, or drag the eyedropper into the viewer to lift a color

out of an image. With the RGBA sliders or number fields you can key in each color channel's value or the Alpha channel's strength. Allow Combining With this checkbox on, the Alpha channel value holds steady even while passing through downstream nodes that might overlap the shape with copies of itself. With it off, the Alpha channel value can climb wherever the shape overlaps itself. For example, if an ellipse's Alpha channel reads .5, turning on the Allow Combining checkbox preserves that value even when the shape moves through a Duplicate or Grid node that overlaps it. Leaving the checkbox off lets the Alpha channel values compound at each spot of overlap.

With Allow Combining on (left) and off (right) Common Controls Settings Tab Every Shape node shares the Inspector's Settings tab. Those common controls get a full treatment at this chapter's close in the “The Common Controls” section.

### sExpand

### The sExpand node

The sExpand node serves to dilate or erode shapes. As with nearly every Shape node, the sExpand node's output is only viewable through a sRender node.

### External Inputs

The input below shows up on the node's tile within the Node Editor. Input1: [orange, required] This input takes the output of another shape node. Whatever shape or compound shape you wire here is eroded or dilated.

### Basic Node Setup

The sExpand node accepts one input, most often a compound shape. That said, it works on single shapes such as sStars and sNgons too. The sExpand's output may then head onward to a further shape node, or into a sRender node, for viewing or for compositing within the wider node tree.

A star and an ellipse merged within an sBoolean node, then sent to an sExpand for dilating or eroding Inspector

### The sExpand Controls tab

### Controls

Every parameter for the sExpand node lives on the Controls tab. Amount A positive value dilates the shape while a negative one erodes it. Border Style The border style governs how the expanded or contracted shapes meet at the corners. There are four styles to pick among. Bevel flattens each corner to a square. Round gives corners a curved finish. Miter together with Miter Clip keep edges pointed until they cross a set threshold. That Threshold is fixed by the Miter limit slider. Miter Limit Only when the Miter or Miter Clip border style is chosen does the Miter parameter appear. The miter limit decides when the pointed edges turn beveled, based on the shape's thickness.

### Common Controls

Settings Tab The Settings tab in the Inspector is shared across every Shape node. Those common controls get a full treatment at this chapter's close in the “The Common Controls” section.

### sGrid

### The sGrid node

The sGrid node duplicates the shape over an X and Y grid and throws in the ability to offset the rows and columns. As with nearly every Shape node, the sGrid node's output is only viewable through a sRender node.

### External Inputs

The node's tile within the Node Editor carries the input below. Input1: [orange, required] This input takes the output of another Shape node. Whatever shape you wire here is replicated across a custom grid.

### Basic Node Setup

The sGrid node accepts one input, a lone shape or a compound one coming from am sMerge or sBoolean node. The sGrid node lays the incoming shape onto a grid of rows and columns. The sGrid's output may then head onward to a further Shape node, or into a sRender node, for viewing or for compositing within the wider node tree.

An sEllipse shape feeding an sGrid and then routed to an sRender to view and blend with other elements Inspector

### The sGrid Controls tab

### Controls

The Controls tab is where you set the number of grid cells and their offset position.

Grid Cells X and Y These parameters fix how many cells the grid holds, both horizontally and vertically. As an example, entering 5 in the X and Y number field yields five rows of the shape and five columns. X and Y Offset Fixes how far apart the rows and columns sit along X and Y. With an offset value of 0.0, every row and column stacks directly on each other. Set X Offset to 1.0 and the columns spread out by the frame's full width.

### Common Controls

Settings Tab The Settings tab in the Inspector is shared across every Shape node. Those common controls get a full treatment at this chapter's close in the “The Common Controls” section.

### sJitter

### The sJitter node

The sJitter node most often serves to randomly position an array of shapes generated by a sGrid or sDuplicate node. Even so, it carries an auto-animating random mode that can distort and randomly jitter single shapes. As with nearly every Shape node, the sJitter node's output is only viewable through a sRender node.

### External Inputs

Within the Node Editor, this node's tile shows the single input listed here. Input1: [orange, required] This input takes the output of another Shape node. Whatever shape you wire here is offset, distorted, and animated per the sJitter node settings.

### Basic Node Setup

Fed an array of shapes out of a sGrid or sDuplicate node, the sJitter node randomly shuffles their position, size, and rotation. The sExpand's output may then head onward to a further Shape node, or into a sRender node, for viewing or for compositing within the wider node tree.

A sGrid-generated array of shapes fed into an sJitter node, which then randomly offsets or scales them

### Inspector

### The sJitter Controls tab

### Controls

The Controls tab provides range sliders that set the variation amount for offset, size, and rotation. The Point Jitter parameters serve to offset the invisible points making up the vector shapes. Jitter Mode The Jitter Mode menu lets you choose between static position and size offsets or switching on an auto-animation mode. Leaving the default Fixed selection lets you offset a grid of shapes, animating with keyframes or modifiers when needed. The Random menu selection auto-animates the parameters according to the range you set with the range sliders. Leave every range slider in its default position and no random animation arises. Widen the range on any single parameter and it animates randomly across the span those range sliders define. Shape X and Y Offset These parameters fix the horizontal plus vertical offset away from the shape array's starting placement. Because it's random, the shapes throughout the array don't all offset by an equal amount. Shape X and Y Size Here you set, horizontally and vertically, the scaling applied to every shape across an array. The left range value pulls the scale down, while the right range value pushes it up. Being random, the array's shapes won't all scale by the same degree. Shape Rotate This parameter rotates every shape across an array. Point Jitter With the X and Y Point Jitter parameters you draw on the vector control points to warp the shape. The result can give ellipses a distressed look or hand other shapes a wobbly animation.

### Common Controls

Settings Tab The Settings tab in the Inspector is shared across every Shape node. Those common controls get a full treatment at this chapter's close in the “The Common Controls” section.

### sMerge

### The sMerge node

The sMerge node merges shapes much like a standard Merge node, except the sMerge node can take more than two shape inputs. As with nearly every Shape node, the sMerge node's output is only viewable through a sRender node.

### External Inputs

The node shows only two inputs at first, but as each shape node hooks up, a fresh input appears on the node, making sure one is always free to bring a new shape into the composite. Input[#]: These multi-colored inputs serve to connect multiple Shape node. There is no ceiling on how many inputs this node will take. The node dynamically tacks on more inputs as needed, ensuring at least one input stays available at all times.

### Basic Node Setup

The sMerge node serves to fuse two Shape nodes. As for layering, each subsequent input lands over the previous one. For instance, the first shape wired to the orange input sits as the bottom-most shape, the green input layers over it, and a third shape on the pink input becomes the topmost layer.

A trio of shapes merged within an sMerge node, then sent on to an sRender for viewing and further processing.

### Inspector

### The sMerge Controls tab

### Controls

The sMerge node's single control is the Override Axis checkbox, which takes over the shape's axis.

### Common Controls

Settings Tab The Settings tab in the Inspector is shared across every Shape node. Those common controls get a full treatment at this chapter's close in the “The Common Controls” section.

### sNGon

### The sNGon node
