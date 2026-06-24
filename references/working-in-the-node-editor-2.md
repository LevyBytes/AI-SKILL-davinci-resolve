# Working In The Node Editor (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

With elaborate compositions you might find yourself opening extra viewers. As an illustration, you could devote one viewer to the finished comp's end result, hand a second viewer the source, point a third at a mask, and turn a fourth into a broadcast monitor wired through a Blackmagic DeckLink card or some other display hardware. The moment you go past two viewers, further View indicators get added, each tagged with a running number somewhere between 3 and 9.

As the viewer count climbs, it can get harder to recall which View indicator stands for which viewer. Park the pointer over the View indicator in question and a tooltip pops up naming the viewer it stands for.

### Drag and Drop Nodes into a Viewer

Should the View indicators be too tiny a target to click dependably, and you're not the keyboard type, there's another route for loading a node into a viewer: drag it and drop it straight onto the viewer you mean to fill. This gives a fast, deliberate way to hand a node off to a viewer, handy above all for pen and tablet users. Bear in mind that during the drag the node looks like it's moving at first, yet it snaps right back to where it started the instant the pointer exits the Node Editor.

### Using the Contextual Menu

Another option is to right-click a node and then pick View On > Left or Right to throw the node onto the right viewer.

### Clearing Viewers

Each time you load a node into a viewer, you trigger a render of that node, every node upstream of it, and other related nodes too. Load nodes into both viewers and that workload doubles. To stop your computer from grinding through views you don't currently need, you can empty each viewer. Ways to clear viewers:

- Press 1 or 2 to clear the left or right viewers when they're loaded.
- Press ` (the Accent key) to clear both viewers.

### Create/Play Preview

You can right-click a node and pick an entry from the contextual menu's Create/Preview Play On submenu to render and play back a preview of any node's output on one of the viewers on hand. Up comes the Render Settings dialog, and once you accept the settings, the tool renders and the frames it produces get held in RAM for snappy playback on that view. TIP: Hold the Shift key as you choose the viewer from the menu to skip the Render dialog and kick off the preview straight away using the default settings or whatever settings you last used to build a preview.

### Connecting and Disconnecting Nodes

After you've begun dropping nodes into your composition, they have to be connected before they can carry out what you intend.

### Node Basics

Every node shows little colored knots ringing its edges. The arrows, one or more, mark inputs, while the square marks the tool's processed output, of which there's never more than one. An output reads white when it's wired up correctly, gray when it's left unconnected, or red to flag that something's off and the node can't process as it should.

A Blur node with a Foreground Input, Mask Input, and Output. Every node feeds on the output handed to it by the node ahead of it. Wire a MediaIn node's output into a Blur node and you push image data from the MediaIn node across to the Blur node, which works on the image before the Blur node's own output gets relayed onward to the next node in the tree.

Two nodes connected together.

### How to Connect Nodes

To hook one node to another by hand, click a node's output and pull a connection line across, dropping it onto another node's input. Which way you drag the node connections doesn't matter; pulling a connection from one node's input to another node's output works exactly as well and lands the same result.

The view before (top) and after (bottom) a connection line is pulled and dropped to join two nodes.

### Dropping Connections on Top of Nodes

To save yourself a little effort, you can instead pull a connection line and let it fall right onto a node's tile to auto-wire it to that node's default input, which usually carries the label "background" or "input." In the example below, a connection is pulled from a MediaIn node's output and dropped onto a Blur1 node's tile, and the background input gets connected first.

The view before (top) and after (bottom) a connection line lands atop a node. Drop a connection onto a node whose background input is already wired, and the next-most-important connection gets attached instead, which on multi-input nodes is the foreground input, while on other single-use nodes it may be the Effects Mask input.

The view before (previous page) and after (above) a connection line is dropped onto a node whose background input is already wired up. A few multi-input nodes can grow extra inputs to take on many connections, the Merge3D node among them. Such nodes simply spawn another input each time you drop a connection onto them.

The result once a connection line has been dropped atop a Merge3D node.

### Attaching Connections to Specific Inputs

When you want to be sure you don't land a connection on a node's default input, you have to drop it squarely onto the particular node input you're after. Spot the input's label in the tooltip bar and you know you're lined up to make a clean connection. There's a fallback method, though, for when several inputs compete and you need to be certain you're picking the right one. Hold the Option key while you pull a connection out of one node's output and drop it onto the body of another node. That brings up a pop-up menu where you can name the exact input you want to wire to. Keep in mind this menu shows up only once you've dropped the connection on the node and let go of your pointing device's button.

Pulling a node connection with Option held and dropping it onto another node surfaces a node input menu.

### Automatically and Manually Attaching Mask Nodes

Mask nodes—the Polygon, B-Spline, Ellipse, or Rectangle, say—behave differently on their own when you wire them to other nodes. Pull a connection from a Mask node onto the body of another node and it auto-wires itself to the default mask input, typically the effect mask input. The presumption is that you're using the mask to rein in the node's effect somehow. That's not always so, though, so stay mindful of this behavior to be sure your mask lands on the input that truly delivers the effect you're chasing.

The view before (top) and after (bottom) a connection from a Mask node is pulled and dropped atop a MatteControl node.

### Identifying Node Inputs

While you're still getting the hang of all the nodes and their inputs, resting the pointer over any knot brings up a node tip carrying the knot's name. TIP: Instead of memorizing the various knot types, hold the right mouse button, press Option, and drag from a node's output to the center of another tool. Let go of the mouse and a tooltip surfaces, letting you pick the knot you want to connect to.

### Node Order Matters

The sequence in which nodes get wired together sets the sequence in which each image-processing operation hits the image. In the example below, a MediaIn node brings a clip into the composition, a Defocus node softens the image, and then a TV node lays in scanlines and vertical distortion. Those effect nodes then feed into the MediaOut node on the Fusion page in DaVinci Resolve, or into a Saver node in Fusion Studio.

Adding a Defocus effect first, then the TV node second. As the figure shows, wiring the Defocus node first and the TV node after means the base image is softened while the TV effect stays sharp. Flip the order of these two nodes, though, and the TV effect warps the image, after which the Defocus node now blurs the whole result, leaving the TV effect every bit as soft as the image it lands on. The deliberate order of operations you set up makes an enormous difference.

Adding a TV effect first, and a Defocus second. As you can tell, the node tree behind each composition is a schematic of operations carrying enormous flexibility. On top of that, the node tree's structure aids compositing by letting you steer each node's output into its own branch, which can be processed on its own and later rejoined in countless ways, building ever more intricate composites while sparing you the need to precompose, nest, or otherwise lump layers together—any of which would muddy your composition's readability. In the example below, several graphics layers are transformed one by one and joined with a string of Merge nodes. The final Merge node's result is then transformed, letting you shift the whole stack of earlier layers at once. Because the node tree spells out each of these operations plainly, it's simple to see all that's going on, and why.

A single Transform node reworks the merged output of five Text nodes that Merge nodes have joined.

### Upstream and Downstream Nodes

Because nodes can sit anywhere in the Node Editor and get added in any direction, they're spoken of as being upstream and downstream of each other. Once you select a node, every other node that ties into its input, directly or by way of others, counts as upstream. Any nodes hooked to its output, directly or indirectly, are said to be downstream. This distinction carries weight because, unlike layer-based systems, where you visually place nodes in your node tree has no effect on that composition's order of operations. What counts is solely whether nodes sit upstream or downstream of one another.

Tools upstream (left) and downstream (right) of the Merge node. TIP: To keep yourself organized, the Node Editor contextual menu offers Select > Upstream/Downstream commands for grabbing every upstream or downstream node so you can move them, group them, or handle other organizational chores.

### Disconnecting and Reconnecting Nodes

Node trees stay perpetually in flux, calling for steady revision and reshuffling as you turn up fresh details that want finessing, or things you can pull off better once the whole composition has come together. To make quick edits easy, each connection between two nodes is split into two halves: the output half (tied to the upstream node's output) and the input half (tied to the downstream node's input). You only catch sight of this while you hover the pointer over a connection. Whichever half your pointer sits over lights up in blue.

A connection line's two halves, brought into view as your pointer hovers above it. Through clicking and/or dragging those two halves, you can swiftly disconnect, reconnect, and overwrite node connections, which is vital to reshuffling your node tree quickly and efficiently. To disconnect two nodes, take one of these actions:

- Click once on the input half of the connection running between two nodes.
- Click the input arrow that a connection lands on, then drag to peel the connection off the tool and drop it anywhere on an empty stretch of the Node Editor.

To overwrite an existing connection:

- Drag the output or input half of a connection and drop it squarely onto another node's input or output. That both severs the old connection and wires up the one you're dragging in one motion.

To reroute a connection from one node to another:

- Drag the output or input half of a connection to peel it off one node, and let the connection fall right on another node's input or output.

### Tracing Connections Through the Node Tree

Resting the pointer over a node lights up the connections tied to that node, making it plainer which nodes it links to. What's more, lit-up connections take on the color of the input they feed, so it's easy to tell whether they run to a foreground, a background, or some particular kind of mask.

Resting the pointer on a node lights up every connection in its color, revealing which kinds of inputs are wired in.

On top of that, parking the pointer over a connection summons a tooltip spelling out the output and input that connection joins.

Resting the pointer on a node lights up the connection running between it and the other nodes.

### Branching

A node's input can hold just one connection. A tool's output, on the other hand, can run to inputs on as many nodes as you like. Splitting a node's output across inputs on several nodes is what's called branching. Countless reasons exist for wanting to branch a node's output. One easy example is processing an image in a handful of different ways before bringing those results back together further down the node tree.

A MediaIn node split across two node operations and afterward rejoined by way of a Merge node. As another use, it lets you put one image to several different purposes—say, sending the RGB down one branch for keying and compositing while routing the A channel into another node's Effects Mask input to rein in its effect, or feeding RGB to a tracker to pull out motion data.

A MediaIn node branched to two different kinds of inputs, used separately.

### Connecting Merge Nodes

The Merge node is the chief tool on hand for compositing images together. Each Merge node can fold two inputs into a third, drawing on standard compositing methods and composite modes. For a fuller account of the Merge node, consult Chapter 105, "I/O Nodes," within the DaVinci Resolve Reference Manual, or else Chapter 45 over in the Fusion Reference Manual. Here, the only thing to grasp is that if you attach a background image to the Background input (a landscape, say) and a foreground image with an alpha channel to the Foreground input (a graphic with an alpha channel, say), the Merge node folds them into a single image ready for further compositing.

A pair of MediaIn nodes plus a DeltaKeyer node wired into a Merge node, building a composite. Every Merge node carries three inputs:

- Background (orange): The default input. Whatever image lands on this input sets the Merge node's output resolution.
- Foreground (green): The secondary input, intended for whatever image you want sitting "on top."
- Effect Mask (blue): An optional input where you can attach a mask or matte to rein in the Merge node's effect.

Getting the right nodes onto the right inputs matters if you want the result you're after, so keep these inputs front of mind whenever you wire to a Merge node. You can of course always drag a connection to a specific input to be sure you're wiring things the way you need. But if you're rushed and just drop connections straight onto a Merge node:

- The first connection lands on the background input.
- The second connection lands on the foreground input.
- The third connection lands on the effect mask input.

TIP: Whether you append a Merge node to a selected node via the toolbar's Merge button, via the Effects Library's Merge icon, or by right-clicking a node within the node tree and picking Insert Tool > Composite > Merge off the contextual menu, that fresh Merge node always shows up with its background tied to the upstream node sitting ahead of it.

### Automatically Creating a Merge Node When Adding Nodes

There's a tidy shortcut for wiring Merge nodes when you want the incoming clip slotted into your node tree right away as a composite's top layer: drag a clip out of an Operating System window—or pull a Generator out of the Effects Library—straight onto any connection line. Drop the resulting node and a Merge node is built automatically, its background input wired to the next node left of the connection you dropped onto, and its foreground input wired to the new node standing for the clip or Generator you just added.

Pulling a node out of the Media Pool onto a connection (left), then dropping it to spin up a Merge node composite (right). What's more, pull two or more nodes out of an OS window into the Node Editor all at once and Merge nodes get built automatically to tie them all together, making this a quick way to lay down a composite at the start.

Pull three nodes from an OS window into the Node Editor (left) and Merge nodes spring up on their own to tie them all together (right).

### Automatically Creating a Merge Node by Connecting Two Outputs

Here's a perpetually handy shortcut for when you've got a stray node you want composited over another. Pull a connection from the output of the node you mean to be the foreground layer and drop it onto the output of the node you mean to be the background layer, and a Merge node gets built automatically to assemble that composite.

Pulling a connection out of a stray node onto another node's output (top), then dropping it to spin up a Merge node composite (bottom).

### Connection Options and Routers

Out of the box, the Node Editor uses linear connections drawn as a straight line between any two wired nodes. Efficient as that is, it can sometimes leave connection lines crossing over nodes, which some folks feel clutters the view of the Node Editor.

Linear connections between nodes. If you prefer, you can switch how connections are drawn by turning on orthogonal connections, which auto-draws lines with right angles so connections steer clear of overlapping nodes.

Optional orthogonal connections between nodes. As far as your composition goes there's no difference; this only changes how your node tree looks. To switch how connections are drawn in the Node Editor:

- Right-click the Node Editor background and pick one of the following from the contextual menu.
- Options > Direct Pipes
- Options > Orthogonal Pipes

### Using Routers to Reshape and Branch Connections

When you want to push a given connection into an angle to keep your node tree neat, a router dropped onto either a linear or an orthogonal connection will impose that angle, so the line draws however you'd like.

A router dropped in to bend a connection into an angle. Routers are minuscule nodes sporting a lone input and an output, but with no parameters beyond a comments field (found in the Inspector), where you can jot notes about what's unfolding in that stretch of the composition. Even handier, you can branch a router's output across multiple nodes, which makes routers all the more useful for keeping node trees tidy when you want to branch one part of your node tree's output to other nodes sitting clear across at the far end of that same node tree.

A router branching its output to multiple nodes.

Ways to work with routers:

- To add a router to a connection: Option-click anywhere along a connection.
- To move a router: Drag the router somewhere new, and the connection reshapes itself as needed.
- To branch a router's output: Pull a connection out of the router output onto some other node's input. There's no cap on how often you can branch one router's output.
- To remove a router: Highlight any router and hit the Delete key, or else right-click a router and pick Delete off the contextual menu.

### Swapping Node Inputs

On multiple-input nodes like the Merge, Merge 3D, and Dissolve nodes, there's a fast way to swap the Primary and Secondary inputs—the foreground and background inputs of a Merge tool, for instance—when you realize you've wired them up backwards by mistake. Should a node have more than two of its inputs wired, only the foreground and background inputs trade places. To swap the primary inputs of a multi-input node, take one of these actions:

- Select a node and press Command-T to flip its inputs.
- Right-click a node and pick Swap Inputs from the contextual menu.

With node inputs before the swap (left) and after the swap (right), the connections stay put while the colors shift. Inputs can slide freely around the node, so swapping two of them leaves the connection lines in place; instead, the inputs switch color to show you've flipped the background (orange) and foreground (green) connections.

### Extracting and Inserting Nodes

As you build a composition, you'll regularly hit a point where nodes you've already laid down need rearranging so you can wire them differently for a better outcome. Happily, that's easy: extract one or more nodes from one stretch of a node tree and slot them into another stretch. To extract one or more nodes from where they sit in the node tree:

- To extract a single node: Hold the Shift key, drag a node up or down out of the node tree to disconnect it, then drop the node before you let go of the Shift key. That node is now loose, and the next upstream node's output auto-wires to the next downstream node's input to close the gap in the node tree.
- To extract multiple nodes: Select the nodes you mean to pull out, hold Shift, and move any one of those selected nodes upward or downward to cut them loose, then drop the node before you let go of the Shift key. Those nodes are now loose (though still wired to one another), and the next upstream node's output auto-wires to the next downstream node's input to close the gap in the node tree.

The view with a pair of nodes still in place (left), then with that pair pulled out (right). Once a node has been extracted, you can set it back down into another connection somewhere else. Only a single node goes in at a time. To wedge a disconnected node into the Node Editor between two compatible nodes: 1 Holding Shift, drag the disconnected node so it sits squarely over a connection joining two other nodes. 2 The instant that connection lights up, drop the node, then release the Shift key. That node is now wired into the nodes coming before and after it.

Before inserting a node (left), and after inserting a node (right). TIP: Hold the Shift key and you can extract a node and slot it in somewhere else in one single drag.

### Cut, Copy, and Paste Nodes

The familiar cut, copy, and paste operations are on hand in the Node Editor as well. You can lean on them to pull nodes out of the Node Editor for a moment, spin up duplicate nodes, or even lift the settings off one node and drop those settings onto another node whose settings are compatible.

### Cut, Copy, and Paste in the Node Editor

The usual commands all work, though with a few extra touches particular to the Node Editor. To copy one or more selected nodes, take one of these actions:

- Right-click a node and pick Copy from the contextual menu.
- Choose Edit > Copy from the Edit menu (Command-C).

To cut one or more selected nodes, take one of these actions:

- Right-click over the node and pick Cut from the contextual menu.
- Choose Edit > Cut from the Edit menu (Command-X).

Pasting into the Node Editor produces a copy of the last node or nodes you cut or copied. As you paste, a few different moves let you steer where the pasted nodes land. To paste one or more selected nodes, take one of these actions:
