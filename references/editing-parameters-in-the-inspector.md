# Editing Parameters In The Inspector (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Editing Parameters in the Inspector

Each node's parameters are tuned inside the Inspector to accomplish whatever a given task requires. The various parameters carried by nodes, and the ways you work with the controls on offer, are the subject of this chapter.

### Overview of the Inspector

Building and wiring nodes within the Node Editor sets which tools, and in what order, form a composition; tuning the settings held inside each individual node, however, happens over in the Inspector so the result matches your intent.

### Inspector displays the Brightness Contrast controls

How you open a node's parameters in the Inspector, and edit them through whichever controls a node exposes, is covered here. To display the Inspector: Click the Inspector button on the UI toolbar.

### The Tools and Modifiers Panels

Two main panels make up the Inspector.

- The Tools panel is the spot where a selected node's parameters surface for editing.
- The Modifiers panel is where you adjust optional add-ons that extend a tool past its built-in feature set, plus

scripted expressions you can bind to single parameters in order to drive animated results. Beyond that, some nodes (the Paint node, for instance) produce data like Strokes, and that data lives in the Modifiers panel.

### Modifiers displayed in the Modifiers panel

### Customizing the Inspector

Several options let you change the way the Inspector is laid out.

### Inspector Height

Off at the far-right end of the UI toolbar sits a small arrow button that switches the Inspector between its full-height and half-height layouts, according to how much vertical space your parameter editing demands.

The Maximize button at the Inspector's left edge In maximized height mode, the Inspector claims the whole right edge of the UI, so every control a node offers is visible, or so there's room enough to expose the parameters of two or three pinned nodes simultaneously. With half-height mode active, the Inspector's top edge lines up with the tops of the viewers, which widens the horizontal area left over for the Node Editor.

### Inspector Display Preferences

Out of the box, the Inspector shows only the nodes you've selected, and only the Active node has its controls expanded. To alter that behavior, head to Fusion > Fusion Settings while in the Fusion page (or File > Preferences over in Fusion Studio) and bring up the User Interface panel. Within the User Interface, a set of checkboxes governs how controls are shown.

### Control preferences in the User Interface category

- Auto Control Open: When enabled (the default), the active node, whichever one that is, opens its controls in the Inspector on its own. When disabled, choosing an active node reveals that node's Inspector header in the Inspector, yet the parameters stay tucked away until you click the Inspector header.
- Auto Control Hide: When enabled (the default), the Inspector shows only selected nodes, and any node you deselect is dropped from the Inspector automatically so things stay tidy. When disabled, the parameters of selected nodes stick around in the Inspector even after you deselect those nodes, which lets the Inspector pile up the parameters of every node selected over the course of your work.
- Auto Control Close Tools: When enabled (the default), only the active node's parameters are allowed to be open. When disabled, you're free to expose the parameters of several nodes in the Inspector at once.
- Auto Controls for Selected: When enabled (the default), choosing more than one node opens a control header per node in the Inspector. When disabled, the Inspector shows only the active node; the other multi-selected nodes, marked in white, stay hidden.

### Opening Nodes in the Inspector

A node has to be opened in the Inspector before you're able to edit its parameters. To display a node's controls in the Inspector: From the Node Editor, the Keyframes Editor, or the Spline Editor, pick one node or several. Selecting one node on its own, such that the Node Editor highlights it orange, brings every one of its parameters into the Inspector. Select several nodes together and an Inspector header shows up for each one (marked white in the Node Editor), while the parameters belonging to the active node (marked orange) are the ones available to edit.

### Opening multiple nodes in the Inspector

Because only a single node's parameters can be edited at once, clicking a different node's Inspector header reveals that node's parameters and shuts the parameters of whichever node you had open before. Doing so also turns the freshly opened node into the active one, marking it orange in the Inspector.

### Pinning Multiple Nodes in the Inspector

When speed matters and you want to tune the parameters of several nodes together, the Pin button in a node's Inspector header keeps those parameters on display in the Inspector no matter whether that node happens to be selected and active right then. The Pin button on a node's Inspector header As long as the Pin button stays on, that node's parameters stay open in the Inspector. Selecting a different node back in the Node Editor causes that node's parameters to show up below any pinned ones.

A pinned node shown beneath a selected node up top There's no cap on how many nodes you pin in the Inspector, though a larger number raises the odds that you'll be scrolling up or down within the Inspector to reach every parameter you mean to edit. Switching off a node's Pin button in its Inspector header is all it takes to unpin it from the Inspector.

### Hiding Inspector Controls

Should you wish, the Inspector parameters of particular nodes can be concealed so they stay out of sight even while that node is selected. That's handy for guarding against unintended edits by you or by fellow compositors on a shared composition whenever locking the node outright isn't what you want. To Toggle the Inspector controls for a node or or off: Either the node itself in the Node Editor, or its Inspector header, can be right-clicked; then pick Modes > Show Controls off the contextual menu.

### Using the Inspector Header

Selecting a node fills the Inspector with a title bar, known as the Inspector header, showing both that node's name and the rest of the controls that manage it. Although a node's Inspector header carries an assortment of controls in its own right, clicking (or double-clicking) it also reveals that node's parameters.

### A node's Inspector header

Select several nodes together and the Inspector shows a header for each. By default only the active node's parameters (marked orange in the Node Editor) may be opened at any one moment, though Fusion's Preferences let you alter that behavior.

### Selecting and Viewing Nodes in the Inspector

You click Inspector headers to select nodes, to open and close node parameters, and for other purposes. Ways to work with headers:

- To select a node using the Inspector header: With several nodes selected, clicking a node's Inspector header in the Inspector promotes it to active node. Once it's the actively selected node, both its Inspector header and its counterpart in the Node Editor turn orange, and its parameters are revealed.
- To load a node into the viewer using the Inspector header: Drag a node's header onto one of the viewers to see it there.
- To view a node's splines with the control header: To bring a node's animated curves into the Spline Editor, drag its Inspector header onto the Spline Editor. Every animated spline tied to that node's parameters then appears automatically.
- Using Header Controls

Because of the controls sitting in each node's Inspector header, simple jobs go quickly. To turn nodes off and on: A toggle switch sits left of the name on every Inspector header and serves to enable or disable that node. A disabled node hands image data straight from its upstream neighbor to its downstream neighbor untouched. To change the Inspector header name: Next along is the name of the node that header belongs to. Rename it by right-clicking the Inspector header to bring up contextual menu commands much like the ones you get right-clicking a node in the Node Editor, then choosing Rename. As an alternative, select an Inspector header and hit F2 to rename it. A Rename dialog opens, where you key in a fresh name and click OK (or press Return). To color-code nodes: From a color pop-up menu you can apply any one of 16 colors as a code. Pick Clear Color to send that node back to its default color. To version nodes: Switch on the Versions button and a Version bar carrying six buttons shows up. The section after this one covers versioning. To pin Inspector controls: Click the Pin button and a node's parameters get "pinned" in the Inspector, holding their spot even once you've deselected the node. There's no limit on how many nodes you pin, yet a bigger count forces more scrolling through the Inspector to find every parameter. To lock nodes: Click the Lock button and that node is locked, barring any changes to it. To reset Inspector controls: At the far right end of the Inspector header lives a Reset button, which restores the whole node to its default settings.

### Versioning Nodes

Every button can hold its own distinct set of parameter values for that node, which makes saving and comparing as many as six settings versions per node simple. Each version is stored together with its node in the Node Editor so you can reuse it later.

The Version bar sitting below an Inspector header once versions are enabled An orange underline marks whichever version is selected at the moment, meaning the version your composition is actively drawing on. To discard a version you no longer want, right-click its number and choose Clear from the contextual menu.

### Parameter Tabs

Below the Inspector header runs a row of panel tabs shown as themed icons. Click any one of these icons to open its own tab of parameters, typically gathered by purpose. A basic node like the Blur node has just two tabs, the first holding every parameter to do with blurring the image, the second being the Settings tab.

### The parameter tabs of the Blur node

Nodes of greater complexity carry additional tabs holding more parameter groups. The Delta Keyer, as an example, has seven tabs that split apart its Key, Pre-Matte, Matte, Fringe, Tuning, and Mask parameters alongside the mandatory Settings tab. Those tabs stop the Delta Keyer from becoming one enormous scrolling list of settings and help you track which stage of keying you're refining as you go.

### The parameter tabs of the Delta Keyer node

### The Settings Tab

A Settings tab ships with every node in Fusion. It holds a collection of standard controls present on practically every node, though a handful of nodes carry special Settings tab controls the rest don't have.

### The Settings tab in the Inspector

While the controls below appear on most nodes, a few are particular to certain ones. Motion Blur settings, for one, serve no function on a Color Space node.

### Blend

Every node except the Loader, MediaIn, and Generator nodes carries the Blend control. Its job is to mix the node's untouched input image against the node's fully processed result. At a blend value of 0.0, the output image matches the input image exactly. Normally that makes the node bypass processing altogether, passing the input directly through to the output. This node's default is 1.0, so the node sends out the modified image at 100%.

### Process When Blend is 0.0

Even when the input value sits at zero and the output image equals the input, this checkbox makes the node process anyway. That can help on certain nodes or third-party plugins that carry values across from one frame to the next. Leave this checkbox off on nodes that behave that way and the node skips processing whenever Blend is at 0, which yields wrong results on the frames that follow.

### Red/Green/Blue/Alpha Channel Checkboxes

A row of RGBA boxes sits in the Settings tab of most nodes. Ticking these boxes lets you keep any mix of those channels from being touched by the node.

A Transform node's channel-limiting boxes, in its Settings panel, configured to act on the green channel alone. Say you wanted the Transform node to act on an image's green channel alone; you'd switch off the Red, Blue, and Alpha checkboxes. The green channel then runs through this operation, while the red, blue, and alpha channels travel straight from the node's input to its output, bypassing that node's processing so they stay untouched.

Applying a Transform effect to nothing but the image's green color channel

### Skipping Channel Processing

Behind the scenes, most nodes really do process all of the channels first and only afterward copy the input image to the output for whichever channels you've unchecked. Today's workstations are quick enough that you rarely notice this, but a few nodes really will skip a channel's processing entirely when you deselect it. Such nodes carry a linked group of Red, Green, Blue, and Alpha boxes on a separate tab within the node.

On the Blur node's Controls tab, the channel boxes signal that any disabled channel is skipped outright so rendering time is saved.. When that's the case, the Common Control channel boxes are instanced to the channel boxes located elsewhere in the node. Blur, Brightness/Contrast, Erode/Dilate, and Filter are among the nodes that carry RGBY checkboxes on the Inspector's main Controls tab as well as on the Settings tab.

### Apply Mask Inverted

Enable the Apply Mask Inverted checkbox and any mask wired into that node's Effect Mask input is flipped. TIP: The Apply Mask Inverted checkbox acts on effects masks alone; garbage masks are left out.

### Multiply By Mask

Choosing this option multiplies the masked image's RGB values by the values of the Mask channel. The upshot is that every image pixel left out of the mask (the ones set to 0) turns black. The result is a premultiplied image. Use Object/Use Material (For Masking) Certain 3D animation and rendering packages can write to file formats carrying auxiliary channels. The OpenEXR file format, notably, holds Object ID and Material ID channels, and either one can serve as the mask for an effect. Whether those channels get used when present is decided by this checkbox. Exactly which Material ID or Object ID is targeted is set with the next group of controls.

- Sample Controls: The Sample Controls show up only after the Use Object or Use Material checkbox is turned on. With them you pick which ID builds a mask from the Object or Material channels stored in the image. The Sample button grabs IDs out of the image in the viewer the same way the Color Picker grabs a color: hold the left mouse button down on the Sample button, then drag across to the viewer onto the part of the image you mean to select. Whatever image or sequence you use must have been rendered out of a 3D software package with those channels baked in.
- Correct Edges: The Correct Edges checkbox shows up only after the Use Object or Use Material checkbox is turned on. With the Correct Edges checkbox enabled, the Coverage and Background Color channels go to work separating and refining the effect around an object's edge. With it disabled (or with no Coverage or Background Color channels on hand), the mask edge may show aliasing.

### Motion Blur

On nodes able to introduce motion, Transform nodes and Warp nodes among them, the Motion Blur checkbox switches that node's motion blur rendering on or off. With this checkbox on, the node's estimated motion drives the blur a virtual camera shutter would produce. Switch the control off and no motion blur is generated. While Motion Blur stays off, no extra controls show up. Switch Motion Blur on, though, and four more sliders appear for shaping the look of the motion blur you're applying to that node. Quality: Sets how many samples go into building the blur. At the default of 2, two samples are placed to either side of an object's real motion. Bigger numbers smooth the result but lengthen the render time. Shutter Angle: Governs the angle of the virtual shutter that yields the Motion Blur effect. Wider angles add blur but push up the render times. Setting 360 is the same as leaving the shutter open across one full frame's exposure. You can go higher, which opens the door to interesting effects. This slider defaults to 100. Center Bias: Shifts where the center of the motion blur sits. Tuning the value makes trail-type effects possible. Sample Spread: Tuning Sample Spread changes the weighting handed to each sample. That alters how bright the samples chosen with the Quality slider come out.

### Scripting

Every node carries Scripting fields holding one or more editable text fields where you can drop in scripts that run as that node renders. Turn to the Scripting documentation for more on what this tab contains.

### Comments

Every node also has a Comments field, a lone text field for attaching comments and notes to that node. Just click inside the field to drop a cursor and start typing. Add a note and the comments icon turns up in the Control Header, visible in a node's tooltip when you hover the cursor over the node in the Node Editor. If you need it, the contents of the Comments tab can be animated across time. When the node is a Loader, extra controls show up under this tab. For the details, turn to Chapter 104, "Generator Nodes." In the DaVinci Resolve Reference Manual, or to Chapter 44 of the Fusion Reference Manual.

### Editing Individual Tool Controls From the Inspector Context Menu

Right-clicking inside the Inspector and choosing Edit Control summons the Control Editor, where you can tweak the parameters of that one specific tool within the node tree.

### The Fusion Edit Control Dialog

### Inspector Controls Explained

A handful of nodes rely on wholly bespoke interface elements found nowhere else, but most nodes draw on a blend of sliders, angle wheels, and checkboxes. Working with those controls is what this section explains.

### Fusion Slider Controls

You pick a single value out of a range with Slider Controls. Change that value either by dragging the slider or by typing a number into the edit box. So far this is ordinary slider behavior. There's more on offer, though, that can speed up the changes you make with sliders. Click the gutter on the handle's left or right side to raise or lower the value. Hold Command while clicking the gutter to nudge the values in finer steps. Hold Shift while clicking to step the value in coarser amounts.

Hold Command while clicking in the gutter to move in smaller increments

Slider controls run between a minimum and a maximum, yet typing an out-of-range number into the edit box will frequently stretch the slider's range to take in the new value. You can, for example, type 500 into a Blur Size control even though the Blur Size slider tops out at 100 by default. The slider widens its displayed maximum on its own so those bigger numbers can be entered. Once a slider differs from its default value, a tiny round marker appears beneath the gutter. Click that circle to send the slider back to its default.

### Thumbwheel

A Thumbwheel control behaves just like a slider apart from having no maximum or minimum. Adjust it by dragging its middle portion left or right, or by typing a value straight into the edit box. Angle parameters are the usual home for Thumbwheel controls, though they serve other purposes too.

Thumbwheel controls handling X, Y, and Z rotation, flanked by arrows at each end for precise tweaks With the thumbwheel selected, the Up and Down Arrows on your keyboard let you refine the values further. Just as with the slider control, the Command and Shift keys raise or lower how much the value shifts in finer or coarser steps. Once a thumbwheel differs from its default value, a tiny round marker appears above the thumbwheel. Click that circle to send the thumbwheel back to its default.

### Range Controls

The Range controls are really a pair of separate controls, one fixing the Low Range value and the other the High Range value. Drag the handle at either end of the Range bar to adjust the values. Drag from the middle of the Range bar to shift the high and low ends of the range together. You can also widen or narrow the range evenly by holding Command and dragging either end of the Range bar. Range controls turn up on parameters that call for both a high and a low threshold, such as the Matte Control, Chroma Keyer, and Ultra Keyer nodes. TIP: Floating-point numbers can go into the Range controls too, just key them into the Low and High numeric entry boxes.

### A Matte Threshold Range control

### Checkboxes used to select options for tracking

### Checkboxes

A checkbox is a control holding one of two states, On or Off. Clicking the checkbox control switches it from selected to not selected and back. You can animate a checkbox, where 0 stands for Off while 1.0 or anything above it stands for On.

### Drop-Down Menus

A drop-down menu serves to pick one option out of a menu. With the menu open, clicking an item selects that entry. Once the menu shuts, the Inspector shows the chosen selection. A drop-down menu's selection can be animated as well, where 0 stands for the list's first item, 1 for the second, and onward from there.

### Drop-down menu in the TimeSpeed node

### Button Arrays

A button array is a cluster of buttons letting you choose from a set of options. They behave almost exactly like drop-down menu controls, except a button array makes all of the choices visible together at once. Button arrays frequently rely on icons to make their options easier to grasp at a glance.

The Lens Type button array in the Defocus node

### Color Chooser and Picker

Wherever a parameter wants a color for its value, like the Fill or Outline color in the Text+ node, the Color panel appears. A swatch shows the chosen color with an Eyedropper beside it, and the Color Chooser sits below the swatch. The Color panel is remarkably versatile, offering four separate ways to pick and show colors.

### The Color panel with transparency preview

TIP: Pick the range you prefer in the Preferences > General panel and color is then expressed as 0–1, 0.255, or 0–65000. macOS and Windows Color Nodes A click on the color swatch summons the operating system's own Color Selection node. The layout differs a little on each operating system, but the overall concept holds. Pick a color from the swatches on offer, from the color wheel on macOS, or from the color palette on Windows. Whatever way you settle on a color, you have to click OK for it to take effect.

macOS Colors panel

### Windows Color dialog

### The Color Chooser

A built-in color chooser is also at your disposal, with areas for choosing grayscale values plus the hue you've currently picked across varying ranges of saturation and value. A hue bar, and an alpha bar on some nodes, let you settle on different values.

### The color chooser in the Background node

### Picking Colors from an Image
