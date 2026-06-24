# Node Editing Basics (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- A connection can be dragged onto a node input or output that already has one, and doing so replaces the existing connection with whatever new one you're dragging in. As you do, the connection due to be replaced lights up in orange.
- Any node's RGB or Key output can feed as many inputs as you please, yet a node's input takes only a single connection. The lone exception is a node carrying multiple inputs, built to merge the output of several nodes. Among these are the Parallel, Mixer, and Key Mixer nodes.

### Extracting a Node

Now and then you'll want to pull a node out of where it currently sits in the node tree, so that whatever nodes flank it on the left and right rejoin one another on their own, sparing you a manual reconnect. The term for this is extracting a node. To extract a node, do one of the following:

- Select a node, and choose Color > Nodes > Extract Current Node.
- Select a node, and press E.

Bear in mind that a disconnected node in the node tree halts grading entirely, so you'll want either to rejoin that node to some other part of the node tree or to delete it; leaving it disconnected in the Node Editor isn't an option.

### Inserting a Node

Whenever a disconnected node sits in the Node Editor, dropping it into the node tree between any two other nodes is straightforward. The same holds for nodes you drag in from elsewhere — say, out of a Gallery still's exposed node tree. Here's how to slot a disconnected node in between two others:

- Drag a disconnected node, or one out of a different node tree, onto the connection that joins two other nodes within a node tree; the moment a plus icon shows over the node under your cursor, let go to drop it in.

### Rearranging Node Order

How your tree's nodes are wired in sequence shapes what a grade produces. Suppose, for instance, you lift the highlights in the first node, then go to isolate a region of the picture in a second node only to realize it's already been clipped; you might have to rework your order of operations to get the best corrections. To swap the contents of two nodes:

- Command-drag any node and let it fall onto another node so the operations inside each one trade places. The nodes themselves seem not to budge, but the node badges below should make clear that the operations have been swapped.

Relocating a node anywhere else within the node tree goes like this: 1 In the node tree, Double-click a node and hit E to extract it, lifting it out of the tree so it sits unattached. 2 Drag that now-loose node onto the connection line between any two other nodes in the tree, and as a small plus icon shows, drop it so the node wires itself into that spot in the node tree.

### Copying and Pasting All Settings From One Node to Another

The most basic move is to copy every one of a node's settings and paste them into a different node. That makes it painless to replicate things such as windows, qualifier settings, keyframing, or motion tracking you'd like to reuse in another node as the starting point for a fresh operation. It's likewise a fast route to manually rippling a tweak you made in a node out to that same node in a different clip's grade. Copying a node's settings between one clip and another can be done in either of these ways:

- Option-drag one node onto another. On release, the dragged node's settings replace those of the node you dropped onto.
- Select a node holding settings you'd like to copy and choose Edit > Copy (Command-C). Next, select a node to receive those settings — within the current grade or within another clip's grade — or build a new node, then choose Edit > Paste (Command-V) to drop in the settings you copied. These pasted node settings supersede whatever settings that node carried before.

NOTE: There are additional methods of copying nodes and individual node settings.

For more information, see Chapter 142, “Grade Management.”

### Node Context Menu Actions Can Have Assigned Shortcut Keys

Shortcut keys can be tied to frequently used Node Context menu actions such as Lock Node, HDR Mode, Clean Up Selected Node Graph, and so on. Head to Keyboard Customization > Commands > Panels > Color Nodes to set those shortcuts up.

### Keeping Node Trees Organized

Keeping how your nodes sit in the node graph tidy and orderly pays off. A neat tree is far easier to read should you come back to a grade down the road, and it also helps other colorists on the same project make sense of your work. The procedures that follow lay out how to shuffle the nodes in your tree, plus the node tree working area, so you stay on top of your grades. To move nodes within the Node Editor:

- Drag any node to a new position.
- Command-click or pull a bounding box around several nodes you'd like to move, then drag the lot to a new position. Naturally, it's all too easy to overdo it. After a frenzied stretch on a complex grade, if you wind up gazing at a jumble of disorganized nodes, putting your node graph back in order is quick thanks to a pair of commands in the Node Editor contextual menu.

For tidying up the node graph, right-click within the Node Editor and pick:

- Cleanup Node Graph: Shifts every node in the node graph into an evenly spaced grid. Connection lines get rerouted around nodes so clutter is kept down.

### Before/after using “Cleanup Node Graph”

Should your grading have drifted only a little out of hand, the Cleanup Node Graph command can run across several clips at once. To do that, pick the clips whose node graphs need tidying in the thumbnail timeline, then right-click inside one of those node graphs and, off the drop-down menu, choose “Cleanup Selected Node Graphs.” That carries out a Cleanup Node Graph operation across all the selected clips together.

### Track Node Changes Using Color

On the Color Page node graph (3-dot) option menu sits an option labeled Track Node Changes Using Color. It's a per system setting where you pick the node color to be applied to nodes that are newly created or modified. Within a multi-user collaboration environment, every colorist can assign their own preset node color. From there, the node color tells you at a glance who last touched a given node. For single user cases, the feature works to track which nodes and grades changed past some moment in time, such as a client review session.

Picking Track Node Changes Using Color off the Node Graph option menu will, going forward, recolor a node's color bar after any change you make to it. Here, the Highlights node's color bar has turned Violet now that the Violet user has altered it.

On top of that, timeline clips can be filtered by their node colors too. For this, just click the Down Arrow in the Clips tab, move over Node Color, and click the color you'd like to filter by. Run through the same steps again to filter several colors. Once set, the timeline shows only the clips bearing the chosen node colors. Resetting node colors across several selected clips at once is possible too, rather than doing each one on its own. For that, pick the clips whose node colors need clearing and, off the Node Graph Option (3-dot) Menu, choose “Reset all node colors.” You'll get a warning dialog to confirm the choice.

### Using Node Stack Layers

Node Stack Layers make complex grading workflows manageable by spinning up multiple sequential node graphs that let you carve grades into distinct sections. Users can thereby split apart related functions — stabilization, corrections, hero grades, and display trims — into separate node layers. Grade operations such as ripple, reset, and editing can run on a per-layer basis as well. Grab a still to the Gallery and every one of the Node Stack Layers is stored along with that still. Because Node Stack Layers apply in sequence (from lowest up to highest), you can also wield them as highly customizable, reusable filters for your grades.

The Node Stack Layers number and naming options in the Project Settings By way of Project Settings > General Options > Node Stack Layer Count, users set how many clip node layers there are. Custom names for the layers — “primaries,” “secondaries,” “finishers,” and the like — are an option too. NOTE: Should you for any reason go back to the settings and reduce the count of node stack layers afterward, every grade in those layers is wiped across your whole project. Recovering them is just a matter of restoring the layer numbers.

You navigate the Node Stack Layer by clicking the dots above the node graph or choosing the active layer's name from the drop-down menu on the right. From there users can pick individual layers either via the navigation dots over the node graph or through that layer drop-down menu on the right. IMPORTANT: Every node layer hits the clip in this order — pre-clip, L1, L2, L3, L4, post‑clip, and then Timeline.

### Copying Node Stack Layers

It's possible to copy — not just apply — a Gallery Timeline Clip's Active Node Stack layer. To do so, right-click a Timeline Clip in the Gallery and pick Copy Active Layer.

### Post Group Node Stack Layer

Inside Project Settings beneath General Options > Color sits a checkbox named Post Group Node Stack Layer. Tick this checkbox and the final node stack layer gets processed after the Group PostClip node graph. The function lets you reserve that last node stack layer for post group grades and transforms.

Checking the Post Group Node Stack Layer box in Project Settings > Color

With the order revised, the node stack now runs Layer 3 Special Sauce after the Group Post-Clip layer (the one spun up automatically when you group clips). Ordinarily the Group Post-Clip layer would come last.

### Using Compound Nodes

One more node structure handy for keeping complex node trees in order is the compound node. Command-click to pick any number of nodes in the node tree (the picked nodes turn white), then invoke the “Create Compound Node” command to tuck all the selected nodes inside a single node.

### Before/after creating a compound node

The compound node that comes out of this carries however many inputs and outputs are needed to take on the connection lines that joined your selected nodes to the rest of the node tree. Compound nodes help you tidy complicated node trees by tucking groups of nodes that cooperate on one task inside a single node. You can likewise convert a set of nodes you're using to build a specific effect into a compound node before saving it to the Gallery. Assembling an effects library this way makes reusing them via the Append Grade command simple, sparing you the burden of piling lots more nodes into your grade later. Methods for creating and working with compound nodes:

- To create a compound node: Command-click every node bound for the compound node so each takes a white highlight, or drag a bounding box over a cluster of nodes. Next, from the contextual menu opened by right-clicking one of those selected nodes, pick Create Compound Node.
- To edit a compound node: Either double-click whichever compound node you mean to open, or, from the contextual menu reached by right-clicking any compound node, pick Show Compound Node. That node's contents appear in the Node Editor, standing in for the overall node tree.
- To exit a compound node you're editing: Returning to the top level node tree takes a double-click on the leftmost entry in the path control along the bottom of the Node Editor, or a click on the compound node's name. You can instead, from the contextual menu opened by right-clicking in the compound Node Editor, pick “Exit Compound Node.”
- To label a compound node: With a compound node right-clicked, pick Change Label off the contextual menu and type a fresh label for it. Tap the Return key once finished.
- To decompose a compound node: From the contextual menu raised by right-clicking whichever compound node is to be decomposed, pick “Decompose Compound Node.” The compound node vanishes, giving way to the original nodes it held. Note that any adjustment you'd made on the compound node itself gets discarded the moment you decompose it back into its component nodes. To keep that compound node adjustment, copy it first, decompose the node, then build a new node and paste in what you copied.

### Adding Inputs and Outputs to Compound Nodes

Once you open a compound node's contents using the Show Compound Node command, you're free to make whatever changes you wish to the node tree inside, but you also get the choice of rightclicking within the Node Editor and choosing Add Source to attach an input to the compound node, or Add Output to attach an output. Tacking on more inputs and outputs lets you wire the node into the rest of your node tree in more involved ways. Inputs and outputs that stay disconnected don't affect your grade. Beyond that, the Add Alpha Source and Add Alpha Output contextual menu commands let you tack KEY inputs and outputs onto a compound node, making it simple to route key or alpha channel data to other connections in the surrounding node tree.

### Nesting Compound Nodes

Compound nodes can also be nested within other compound nodes, if necessary.

### Grading Compound Nodes

Once a compound node exists, selecting it lets you apply one or several adjustments by way of the compound node itself, which in effect layers those adjustments after every other adjustment carried out by the nodes housed inside it. That gives you the chance to “trim” the impact that compound node has on your grade, or to confine it with a qualifier or window. To adjust the individual nodes tucked inside a compound node, you must first open the compound node. After that, you can select and adjust any node just as you normally would.

### Identifying Nodes

As you apply various adjustments to nodes, small badges show up beneath them signaling what each node is up to. Because nodes can hold several adjustments, any one node may carry multiple badges; how many a node displays hinges on the Node Editor's zoom level. Bigger nodes display more badges, while smaller ones display fewer, concealing whichever badges won't fit. Another handy organizational touch in the Node Editor is an automatic tooltip that pops up whenever you rest the pointer on a given node, presenting a tidy rundown of every operation applied to that node.

(Left) Beneath every node, badges signal which adjustments it holds. (Right) Driving a node into HDR mode through that node's contextual menu

### Putting Nodes into HDR Mode

While using the Color page's various grading controls to grade wide-latitude images for HDR output, switching on the HDR mode of the node at hand can prove handy: right-click the node within the Node Editor, then off the contextual menu choose HDR Mode. The setting retunes that node's controls so they operate across an expanded HDR range. In practice, that eases work on wide-latitude signals via controls letting you adjust separate tonal ranges — Lift/Gamma/Gain, Custom Curves, Soft Clip, and the like.

### Clip vs. Timeline Grading

As a rule, the Node Editor offers two modes. The default Clip mode lets you build separate grades for each clip or group in the Timeline. The Timeline grade mode, by contrast, lets you lay a single grade over every clip in the Timeline at once, as the Thumbnail timeline shows in the screenshot that follows.

A paragon of sophisticated grading, the author lays a red edge vignette over every clip across the project at once by way of the Timeline grade Plenty of reasons might lead you to do this. Working on a commercial spot, for instance, you could lean on Clip grades for general correcting and scene-to-scene balancing, then turn to the Timeline grade to lay one stylistic grade over the whole spot at once. That way, whatever style changes the client requests can land across the entire spot in an instant.

A further case would be reaching for the Timeline grade to apply corrections aimed at QC issues that thread through a whole program — desaturating highlights or selectively darkening one particular shade of red anywhere it shows up. To switch between Clip and Timeline grading modes:

- Pick the mode out of the drop-down menu over at the Node Editor's top right.

### Selecting Track mode in the Node Editor

- Click whichever dot on the Node Editor toolbar maps to the Clip or Timeline mode

Two dots indicate whether you're in Clip or Timeline mode, and clicking them switches between the two NOTE: Resetting the Timeline grade via the Color > Reset All Grades and Nodes command resets the Output Sizing parameters along with it. A pair of dots atop the Node Editor lets you flip between Clip and Timeline modes with one click. Working on a clip that belongs to a group, you'll see four dots instead, granting quick access to the Pre-Clip and Post-Clip Group modes as well.

Group grading gets a fuller account in Chapter 142, “Grade Management.” Timeline Grades and Saved Stills Saving a Gallery still stores both the Clip and Timeline grades. When you apply a grade out of that still, though, only one lands — either the Clip grade or the Timeline grade — according to which mode the Node Editor happens to be in. Saving and applying grades is documented in greater detail in Chapter 143, “Node Editing Basics.”
</content>
