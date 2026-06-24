# Working In The Node Editor (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- To paste nodes to be inserted after another node: In the node tree, pick the node you want the pasted node(s) inserted after, then go to Edit > Paste (Command-V).
- To paste nodes so they sit apart from the remainder of the node tree: Clear every node selection, then go to Edit > Paste (Command-V), or right-click any spot in the Node Editor and pick Paste from the contextual menu.
- To paste disconnected nodes into a particular region of the Node Editor: Clear every node selection, then click the Node Editor spot where the pasted node(s) should land, and go to Edit > Paste (Command-V), or right-click any spot in the Node Editor and pick Paste from the contextual menu.
- To paste a node that takes the place of one already in the Node Editor: Right-click whichever Node Editor node you mean to replace, pick Paste from the contextual menu, and when a dialog pops up asking whether to replace that node, click OK. This works solely by way of the contextual menu command.

TIP: When you paste a MediaIn, Loader, or Generator node so that it lands after a selected node in the node tree, a Merge tool gets built automatically and used to composite the pasted node by hooking it into the foreground input. Though this can spare you a couple of steps, certain artists would rather carry out such merges by hand, and that preference can be set through the Defaults panel within the Auto tools section of the Fusion > Fusion Settings.

### Pasting Node Settings

Rather than pasting a whole node, you may opt to paste only the parameter settings copied off another node. That comes in handy whenever you have painstakingly dialed in or animated parameters on one node and wish to reuse them on a second. Bear in mind that settings can be pasted between two nodes of identical type, or between two wholly different node kinds that nonetheless share one or more of the same parameters in the Inspector. While copying settings across node types, only the settings shared by both nodes get carried over. One common scenario takes an animated Center parameter from a Transform node and drops it onto a Mask node’s Center parameter. Moving settings between two nodes goes like this: 1 Pick a node holding settings you wish to copy, then choose Copy from the Edit menu (Command-C). 2 Right-click whichever node should receive those settings, and choose Paste Settings from the contextual menu.

### Copying and Pasting Nodes to and from Any Text Editor

Nodes in the Node Editor are stored not as binary but rather in a straightforward text format. What that implies might not jump out at first, yet one handy benefit shows up plainly once you begin handling nodes. You can copy one or more nodes out of the Node Editor and paste them straight into a text editor or an email. Doing so drops in the selection as text, exactly the way Fusion keeps it internally. As an illustration, were you to copy the following set of three nodes:

Three nodes shown in the act of being copied. Paste them afterward into a fresh text editing document and what you end up with is this:

The same three nodes pasted into a text editor.

From here, you can edit that text (assuming you know what you are doing), email it to coworkers, or tuck it away in some digital notepad for later use. Putting this script back to work in Fusion takes nothing more than copying it and pasting it back into the Node Editor. TIP: It makes for an exceedingly simple way to trade particular node settings between artists who might be in different rooms, cities, or even countries.

### Using Multilayer Nodes (Studio Version Only)

Multilayer image workflows are handled smartly by Fusion, which supports EXR, Stereoscopic 3D, and PSD assets. The Fusion viewers let users view a list of layers, and within the Settings tab in the Inspector you can interact with the layers belonging to each node. Because this layer structure carries through the whole toolset, you are able to confine a tool to operate on a single layer while the remaining layers pass through untouched.

### Viewer

While loading a multilayer file, you can preview individual layers in the Viewer and pick a layer off the drop-down list. A file lacking layer support offers only a ‘default’ entry in the drop-down menu.

Employing the Viewer’s Layer drop-down to isolate, for viewing, only the Asteroids layer out of a multilayer file

### Nodes and Inspector

The Settings tab holds a Layer category that grants you a set of controls for affecting particular layers and for governing layers coming from each tool input.

- Process Layers: Picks which layer the effects draw from: Default Layer (default): Puts the effect on the base/unnamed layer and leaves the rest untouched. All Layers: Puts the effect across every layer on offer. Custom: Lets you pick among the other available layers to receive the effect, leaving the remaining ones untouched.
- Input Layer: The Input Layer enumerates every layer coming from the upstream node feeding the default input. The chosen layer can be put to use by the current tool, or in isolation further down the node tree.
- Effect Mask Layer: Should the tool carry an Effect Mask input, this control enumerates the available layers able to supply mattes for the tool.

Wiring the multilayer file straight into the BrightnessContrast Effect Mask (blue arrow) on top of its normal input lets you swiftly produce flawless masks of any layer within the file.

Where a tool carries additional named inputs (Image, for one), it may surface further layer controls bearing a matching name (Image Layer, for one).

### Input Layer Controls

To run at peak performance, Fusion tools ask each input only for the processed layers. The Input Layer, Effect Mask Layer, Image Layer and the other input layer controls let the user tailor that behavior. Within each input control, you may pick Auto or Match, or settle on an explicit layer value to map:

- Auto (Default): Asks for whichever layer the Process Layers control has chosen. Should that layer be absent, the tool drops back to the default layer.
- Match: Asks for whichever layer the Process Layers control has chosen. Should that layer be absent, the tool reports a failure instead.
- Explicit Layer Selection: Asks for one specific layer named among those listed. Doing so confines that single layer for use in the present tool, or onward down the node tree.

When dealing with Fusion plugins, the Process Layer and Input Layer controls get generated automatically inside the Inspector’s Settings tab. Plugin authors may elect to spell out and position the controls somewhere else, much as the MultiMerge sets its controls within the main controls section. A number of Fusion tools carry controls for handling extra layer-based decisions. For instance:

- With a stereoscopic camera in play, the Renderer3D surfaces a fresh Eye control > Layers option,

which lets the left and right eyes each be output as their own layer.

- While merging multilayered sources by way of composite nodes (MultiMerge, say),

Channel Booleans, or a MatteControl, the Settings tab carries extra controls offering Background or Foreground options that isolate the chosen layers and bring them together.

- The Combiner tool serves to build custom layers. Switch the Mode to Layer. That reveals layer name fields where you can title the new layers.

### Instancing Nodes

As a rule, when copy and paste produces a duplicate of a node, that fresh node stands fully apart from the source node, so edits to one never propagate to the other. Even so, occasions arise where two nodes have to carry matching settings at every moment. Take the example of applying identical color corrections to two or more images: you would rather not endlessly tweak one color correction node and then by hand match the second to it. That is tedious, and in a rush you might neglect to keep them aligned. There do exist ways to publish controls in one node and tie them to corresponding controls in another, but for nodes where you are adjusting several controls that approach grows unworkably intricate and slow. Under such circumstances, building “instanced” nodes saves genuine time, and also serves as a plain visual signal in your node tree of what is happening.

### Using Instanced Nodes

Instanced nodes are those created with the Paste Instance command, and they share their settings with the source node, so any change made to one instanced node automatically carries across to every other instance of that node (and to the original node you copied as well). Building an Instance goes as follows: 1 Pick a node you wish to instance and copy it (Command-C). 2 Carry out one of these: To make a stand-alone instance of a node: Right-click in the Node Editor background and choose Paste Instance from the contextual menu (Command-Shift-V). To drop an instanced node in between two existing nodes: Pick a node that lies upstream of the intended spot, then press Command-Shift-V. Or instead, rightclick squarely atop a connection line, where the contextual menu again offers Paste Instance. Whichever route you take to paste the instance, that instanced node’s name comes out in the form "Instance_NameOfNode." Paste several instances and each one is numbered "Instance_NameOfNode_01."

A green link line depicts how an instanced Blur node relates to the original Blur node it sprang from. Anytime a node tree contains instanced nodes, a green line denotes the tie binding the original node to its instances. If you prefer, you can switch those green link lines off so the Node Editor looks less cluttered. Showing or hiding the green instance link lines within the Node Editor works thus: 1 Right-click any point of the Node Editor background. 2 From the contextual menu, pick Options > Show Instance Links. After working with a node’s instance and then finding that it needs to take on its own separate adjustments, you can “de-instance” the node.

To de-instance a node, cutting it loose to stand alone: 1 Right-click an instanced node. 2 From the contextual menu, pick Deinstance. From then on that node is divorced from the original node. Once a node has been de-instanced you have no way to re-instance it, although the action remains undoable. NOTE: Where you have de-instanced a node and cannot undo because DaVinci Resolve has since restarted, the only path to a fresh instance is to copy the original and paste an instance once more.

### De-Instancing and Re-Instancing Specific Parameters

Out of the box, each parameter on an instanced node ties back to the original node, so every change you make propagates across. Now and then, though, you will need to adjust just one or two parameters on their own while leaving the rest of that node’s parameters linked. With that in mind, in place of de-instancing the entire tool, you can break the link on individual parameters. To de-instance a single parameter:

- In the Inspector, right-click a parameter’s name or value and choose Deinstance from the contextual menu. If only individual parameters were de-instanced, you can re-link those parameters later on should you have second thoughts.

To re-instance a single parameter: In the Inspector, right-click that parameter’s name or value and choose Reinstance from the contextual menu. The parameter at once takes on the original node’s setting.

### Keeping Node Trees Organized

Much as with the files on your desktop, even the most basic of composites calls for a degree of organization. Here we will run through a handful of fundamental node operations, several of which you may well recognize already from your computer’s operating system or from other software.

### Moving Nodes

Picking one or more nodes and dragging relocates them, which ranks among the simplest ways to tidy a node tree — grouping nodes by position according to the part they play in the whole composition. Bear in mind that where nodes sit in the Node Editor is purely cosmetic and has no bearing on a composition’s output. Arranging the node tree exists solely for your own peace of mind, and that of anyone collaborating with you. TIP: After you have laid out a composition’s nodes in some sensible fashion, the Sticky Note and Underlay tools let you add notes about what is going on and tie clusters of nodes together more firmly by sight. These tools come up later in this section.

### Snapping Nodes to the Grid

By default you are free to drop nodes wherever you please. That said, keeping nodes and connection lines tidy and aligned can make them simpler to read. To aid alignment, the nodes you are dragging can be set to snap onto the grid by themselves. To make dragged nodes snap onto the grid:

- Right-click on a bare patch within the Node Editor; from the contextual menu, pick Arrange Tools > To Grid. From then on every node you drag snaps to its closest grid coordinate.
- Right-click on a bare patch within the Node Editor; from the contextual menu, pick Arrange Tools > To Connected. From then on every node you drag snaps to the horizontal or vertical line of whatever nodes it ties to.

TIP: You can make “Arrange to Grid” or “Arrange to Connected” the standing default for new compositions: pick Fusion > Fusion Settings in DaVinci Resolve or File > Preferences in Fusion Studio, then tick the Fusion > Node Editor > Arrange To Grid or Arrange to Connected checkboxes.

### Commands to “Clean Up” a Node Tree

The grid sitting behind the Node Editor serves to align nodes, whether by eye or automatically.

- To “clean up” a disorderly node tree: Right-click a bare section of the Node Editor; from the contextual menu, pick Line Up All Tools to Grid. Every node in the Node Editor then shifts to align and center itself along the closest grid lines.
- To “clean up” just one or more selected nodes: Right-click any of the selected nodes; from the contextual menu, pick Line Up to Grid. The selected nodes shift to align and center themselves along the closest grid lines, while every unselected node stays put.

### Renaming Nodes

Each node created gets a name assigned to it automatically (drawn from its function) plus a number (drawn from how many nodes of that type already exist). To illustrate, the first Blur node placed in a composition is called Blur1, the next is Blur2, and onward from there. Helpful as that is at the outset, bigger compositions can gain from giving key nodes more telling names — easing the job of recognizing what they actually do, or of referencing those nodes within expressions. To rename a node: 1 Do one of the following:

- Right-click a node and choose Rename from the contextual menu.
- Select a node and press F2.

2 Once the Rename dialog opens, key in a fresh name, after which you click OK or hit Return.

NOTE: With several nodes selected at once, a separate dialog pops up for each, prompting a name per tool.

Because Fusion lends itself to scripting and expressions, node names have to obey a scriptable syntax. Stick to alphanumeric characters only (no special characters), and avoid spaces entirely. On top of that, a node name cannot open with a number. Should you slip and form a name that strays from these rules, spaces and invalid characters get stripped out automatically. When you would rather view the original node types in place of the node names, press and hold Command-Shift-E.

### Changing Node Colors

Any node’s color can be changed by selecting it, opening the Inspector, and picking a fresh color from the Node Color pop-up in that node’s Inspector header. As an alternative, right-click a node and select a color out of the Set Color submenu. To restore a node to its usual color, right-click it and, from the contextual menu, pick Set Color > Clear Color, or open that node’s Node Color pop-up in the Inspector and pick Clear Color.

### Using Sticky Notes

One fine way to keep track of notes on the various parts of a composition, client feedback on assorted details, and any other information you want on hand, is to drop Sticky Notes into the Node Editor.

A Sticky Note in the Node Editor. Sticky Notes are yellow boxes into which you can type any text you like. They can be resized, moved, and collapsed while not being edited, but once made they stay pinned to the Node Editor background at the spot where you placed them until you move or delete them. Methods of working with Sticky Notes:

- To create a Sticky Note: Click the Node Editor spot where you would like a Sticky Note to land. Then press Shift-Spacebar, type sticky, and once the Sticky Note turns up in the Select Tool window, hit the Return key. Failing that, open the Effects Library, head into the Tools > Node Editor category, and either click or drag the Sticky Notes node to spawn a fresh one.
- To open a Sticky Note to full size: Give a minimized Sticky Note a double-click and it grows into a larger, resizable yellow box.
- To edit a Sticky Note: Where needed, double-click a Sticky Note to bring it up full size, then click once within the note’s body to drop a text cursor. Text inside a Sticky Note is edited the same way as in any text editor.
- To rename a Sticky Note: Right-click a Sticky Note, pick Rename, key a fresh name into the Rename dialog, and click OK. Failing that, select a Sticky Note, hit F2 to summon the Rename dialog, and press Return to close it once done.
- To resize a Sticky Note: Bring a Sticky Note up to full size with a double-click, after which you drag any edge or corner to grow or shrink it.
- To minimize a Sticky Note: Click the close box up in the Sticky Note’s top left corner, and it folds down into a small tile.
- To delete a Sticky Note: Either right-click a Sticky Note and pick Delete from the contextual menu, or select the Sticky note within the Node Editor and tap the Delete key.

### Using Underlay Boxes

Underlay Boxes give you a tidy way to associate a group of nodes that cooperate on one particular task in your composition. They amount to nothing more than colored rectangles you can drop nodes inside. After you set nodes within an Underlay, moving the Underlay carries every node inside it along too.

An Underlay in the Node Editor. Underlay Boxes can be given names to mark the purpose of that group of nodes, and can be colored so as to stand apart from other Underlay Boxes or to follow some color scheme across your compositions. Methods of working with Underlay Boxes:

- To create an Underlay Box: Click the Node Editor spot where you would like the Underlay Box to land. Then press Shift-Spacebar, type under, and once the Underlay Box turns up in the Select Tool window, hit the Return key. Failing that, open the Effects Library, head into the Tools > Node Editor category, and either click or drag the Underlay Box node to spawn a fresh one.
- To create an Underlay Box around specific nodes: Within the Node Editor, select the nodes that the Underlay Box should wrap. Then press Shift-Spacebar, type under, and once the Underlay Box turns up in the Select Tool window, hit the Return key. Failing that, open the Effects Library, head into the Tools > Node Editor category, and click the Underlay Box node, which gets added and sized so it wraps each selected node.
- To resize an Underlay Box: Drag any edge or corner to grow or shrink it.
- To rename an Underlay Box: Option-click the Underlay Box so just the box, not its contents, is picked, then right-click it and pick Rename (or hit F2). Key a fresh name into the Rename dialog and click OK or press Return.
- To recolor an Underlay Box: Option-click on it so just the box, not its contents, is picked, then right-click it and select a color out of the Set Color submenu.
- To put nodes inside of an Underlay Box: Pick the nodes you want set within an Underlay Box, then drag them so they sit inside. The Underlay Box has to be big enough to hold every node. As an alternative, set an Underlay Box beside a cluster of nodes you want enclosed, then resize the Underlay Box to enclose all of them.
- To move an Underlay Box and all its nodes: After nodes have been set inside an Underlay Box and then deselected, you can shift the whole cluster of nodes at once by dragging the Underlay Box by its title bar.
- To remove nodes from an Underlay Box: There are a couple of ways to take nodes back out of an Underlay Box. With both the Underlay Box and the nodes deselected, drag a bounding box or Command-click to pick every node in the box you want out, then drag them clear.

Shrink the Underlay Box until it is smaller than the cluster of nodes it first enclosed. The moment an Underlay Box gets so small that even the final node pokes past its edge, those nodes drop out of the Underlay Box automatically, and you are free to move or delete the Underlay Box without those nodes following.

- To delete an Underlay Box together with every node within: Pick an Underlay Box and tap the Delete key to wipe out both the Underlay Box and each node housed inside. Should you want the nodes spared, drag them clear of the box beforehand.
- To delete an Underlay Box yet retain every node within: Option-click the Underlay Box so it alone, not the nodes, is picked, then tap the Delete key. The enclosed nodes stay right where they sat.

### Node Thumbnails

After a source or an effect joins the Node Editor, a node stands in for it. By default nodes are thin rectangles, which makes it simpler to pack reasonably complicated grades into a fairly small space. Still, if you prefer, node thumbnails can be displayed instead.

A node in the Node Editor shown without and with a thumbnail. A node can appear as a small rectangle or as a larger square. In the rectangular form the node’s name runs through its middle, whereas the square form displays the tool’s icon or else a thumbnail of whatever image the node puts out. TIP: Even with node thumbnails switched off, you can swiftly pull up detailed information about a node and the data it is handling by hovering your pointer over it in the Node Editor and reading the tooltip bar below.

### Choosing Which Nodes Show Thumbnails

Should you want node thumbnails to help you pick out media and operations by sight within your node trees, the contextual menu that appears on a right-click anywhere in the Node Editor background offers an assortment of options for which nodes ought to display thumbnails.

### Force All Tile Pictures

Picking this option puts a thumbnail on every last node in the Node Editor. It can render simple node trees easier to read, yet it makes every node tree occupy a good deal more space. NOTE: With Show Thumbnails enabled, nodes might not refresh until the playhead is nudged in the Time Ruler.

### Force Active Tile Pictures

You also have the choice to show thumbnails only on the nodes currently selected, which can clarify which node you are working on. Once nodes are deselected, their thumbnails hide away again.

### Force Source Tile Pictures

This switches on thumbnails for all MediaIn and Loader nodes in the Node Editor, along with every generator, and offers a great way to spot at a glance where all the clips sit within a composition.

### Force Mask Tile Pictures

This switches on thumbnails for all Mask nodes throughout a composition, which can make them simpler to tell apart while you build intricate shapes assembled from several Mask nodes.

### Manually Showing Tile Pictures and Node Options

You also have the choice of picking by hand which nodes should show thumbnails. As an example, at certain key junctures of the node tree you might want a compact visual cue of how the composition is shaping up. Turning thumbnails on or off for one or more particular nodes works thus: 1 Within the Node Editor, select one or more nodes. 2 Right-click any of those selected nodes, and from the contextual menu pick one of these:

- Show > Show Tile Pictures
- Show > Show Modes/Options

Once you have switched thumbnails on by hand for various nodes, they stay visible regardless of whether those nodes are selected.

### Switching Thumbnails between Images and Icons
