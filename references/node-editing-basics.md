# Node Editing Basics (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Node Editing Basics

This chapter walks through the essentials of working with the Node Editor in DaVinci Resolve to organize every adjustment you choose to make to a clip, plus the core routines for editing and arranging nodes inside a tree, which form the foundation for building more elaborate effects.

### Node Editor Basics

Out of the box, each clip starts with a single node in the Node Editor that holds the initial corrections you apply. That said, nothing stops you from adding more nodes, with each one holding one or several corrections that act on the image.

The Node Editor showing a reasonably full-featured grade The particular way you lay out your nodes gives you fine control over the sequence in which your grade's operations run, and that brings plenty of benefits. The discussion here walks through assorted approaches to building, editing, and laying out node trees so you can tap the full capability of DaVinci Resolve.

### Thumbnail-Optional Nodes

Within the Node Editor option menu there's a Show Thumbnails entry that lets you turn off or turn on the thumbnails sitting on each Corrector node.

Turning thumbnails off through the Node Editor option menu shrinks the height of nodes How Many Nodes Do I Need to Use? Throughout this chapter and the ones to follow, you'll pick up a wide range of methods for blending adjustments and nodes in assorted ways to reach very particular results. Naturally, people new to DaVinci Resolve frequently ask themselves, just how far should I take this? No single correct answer exists, but it's fair to say that a handful of the planet's top colorists pull off gorgeous work in as few as three or four nodes, while others habitually assemble carefully structured stacks of ten to twenty nodes, or even more. How many nodes you reach for tends to hinge on the quality of footage you've been handed, since well-lit material generally demands less effort than run-and-gun footage shot with whatever light was around, which usually calls for far more tweaking before it looks acceptable. On top of that, the count of nodes you might reach for can also hinge on the type of project at hand, where commercial spots give the colorist enough room in the budget to construct enormous grades tuning every tiny detail, while narrative features and TV shows push you to move quicker and accomplish more inside fewer adjustments so you keep pace. So what's the true answer? Every grade calls for exactly as many nodes as it needs. Not one more, not one fewer.

### The Node Editor Interface

While working inside the Node Editor, you might want to zoom in or out for a closer or wider view of the node tree, and to scroll around the canvas when handling sizable groups of nodes. To grow the Node Editor's working canvas:

- Drag the divider between the Node Editor and the Viewer leftward or rightward to widen or narrow it.
- Right-click somewhere inside the Node Editor (anywhere but on a node) and pick Toggle Display Mode; that conceals the Viewer and shifts the Node Editor over to the right of the Gallery, growing it substantially. Right-click again and pick Toggle Display Node to go back to the standard layout.

To lay out the node tree so it fits your present working canvas:

- Right-click somewhere in the Node Editor (anywhere but on a node) and chose Cleanup Node Graph out of the contextual menu. That reshuffles your node tree to suit whatever sized canvas you've got at the time.

To zoom plus pan inside the Node Editor, try one of these:

- Drag the Node Editor's zoom slider to make the nodes smaller or bigger.
- Click the Pan tool (the hand icon) over at the top-left corner of the Node Editor, then drag inside the gray region of the editor to scroll the view.
- Hit the H key to flip between selection and pan modes.
- Middle-click and drag inside the editor to scroll the view.
- Right-click and choose Zoom In or Zoom Out.
- Right-click and pick Zoom to Window to size the node tree to the node graph's present dimensions.
- Right-click and pick Original Size to send the node graph back to its default scale.

### The Node Editor’s Pan (Hand) tool

### The Components of a Node Tree

Elaborate grades can call for trees built from several nodes to produce the desired result. This part of the chapter covers how nodes get assembled into the arrangements detailed more fully later on. Each node you place is a "Corrector" node, able to perform either primary or secondary correction, based on whether you switch on the Qualifier/Window/Matte controls. Even so-called "Serial" and "Parallel" nodes are really just Corrector nodes connected in series or in parallel relative to the prior node in the tree; their labels simply reflect how they got added. Every Corrector node carries two inputs and two outputs, allowing you to handle the RGB image-processing channel apart from the Key channel, which marks regions of isolation for image processing or transparency used in compositing. The RGB connections show up as light green and sit at a node's upper left and right. Blue marks the Key connections, which sit along a node's lower left and right. A node's inputs take the form of triangles, while its outputs are squares. These inputs and outputs are how you steer the flow of image and isolation channels in and out of every node throughout the tree.

A lone node, where the RGB (green) plus key (blue) triangular inputs and square outputs stand out plainly

Nodes link to each other through "connections," which show up as lines joining one node to another. Image data travels left to right, beginning at the Source input way over on the left side of the Node Editor, passing through each node in turn, and finishing at the Node Tree output over on the right side of the Node Editor.

### A simple serial arrangement of corrections

Below is a rundown of the various pieces of a simple node tree in which every node sits in serial, one following the next, and how they cooperate:

- Source Input: The green source node way over on the left is the clip's image data after the Sizing and Source decode settings have processed it, ungraded. The Source input supplies RGB data into the grade, and links to the RGB input of the first node in your tree. When needed, you can wire the Source input into several Corrector nodes at once, spawning multiple parallel image-processing streams that branch off the image's original source state and that you can later merge back together in assorted ways with the Parallel or Layer Mixer nodes.
- Nodes: Every node in the node graph stands for a set of image processing operations that you can switch on or off independently of any other node in the graph. By splitting operations across multiple nodes, you gain precise command over the sequence of every image processing operation in DaVinci Resolve, letting you build many distinct corrections and effects. The green RGB inputs and outputs serve to wire these nodes to one another. Each node's thumbnail image reveals how the clip appears at that specific point in the grade, offering a visual cue about what each node accomplishes, and small badges beneath each node tell you which particular operations that node is applying.
- RGB Inputs and Outputs: Sitting at each node's upper right and left, the green inputs and outputs let you carry the RGB image coming out of one node into the next node's RGB input. For a Corrector node to do anything, you have to wire both its RGB input and its RGB output to adjacent nodes in the tree. On top of that, every single node in the Node Editor has to be connected for a grade to function; leaving any node disconnected in the tree shuts that grade off until everything is wired up.
- Key Inputs and Outputs: Sitting at each node's lower right and left, the blue inputs and outputs route the key channel produced by a node's Qualifier or Window controls, or pulled in via a Matte clip you'd earlier paired with a clip on the Media page. Wiring the key output of one node into the key input of another essentially duplicates the first node's key onto the second. You can additionally merge the key outputs from several nodes in assorted ways using the Key Mixer node.
- Node Tree Output: A tree's final node must have its RGB output wired into the green Node Tree output node, the step that "completes the circuit" of image processing and passes that correction along to the next stage of the DaVinci Resolve image processing pipeline. When the output stays unconnected, the node tree is shut off and does nothing to the clip. Only one RGB output can be wired into the Node Tree output at any given time.
- Second Source Input (for RED HDRx): You can reach the alternate highlight exposure of RED HDRx media by revealing this optional second Source input.

For further detail on “Mulit‑Channel RED HDRx Support,” turn to Chapter 147, “Channel Splitting and Image Compositing,”

- Second Source Input (from Fusion page): You're also able to spin up extra sources that route in masks or mattes built on the Fusion page so they can serve as keys over in the Color page.
- Alpha Output: You can carve out areas of transparency for compositing right inside DaVinci Resolve by wiring a key output into an optional Alpha output.

For more information, see Chapter 146, “Combining Keys and Using Mattes.”

### Node Badges and Labels

Nodes show up with assorted labels and badges that help you tell what each one is adding to the overall grade. The length of a label and the count of badges shown hinge on how big each node is, which is governed by the Node Editor's Zoom slider.

Nodes displaying the sorts of labels and badges on offer for telling which operations each node carries out Node number: Each node bears a number matching the order in which it appears in the node graph. Adjustment badges: As you run various operations inside a node, small badges show up below the thumbnail marking which palettes were used on that node. The number of badges you can see hinges on how far in or out you've zoomed into the Node Editor, and whether Color Space or HDR labels are already eating up some of that space. With bigger nodes, more badges fit across the node's width. Every palette on the Color page carries its own distinct badge. Should you run more operations than a node has room to show, one lone "downward arrow" badge shows up. Animation badge: Nodes carrying animated parameters show a keyframe badge.

### Labeling Nodes

You can give nodes labels to mark what a given node does within your grade. That can make revisiting a grade months down the line far simpler. Node labels also get stored whenever you save a still, so labels can likewise make a saved grade easier to read much later. At each node's default size in the Node Editor, nodes can show up to 12 characters of text, though bigger nodes can hold more.

To label a node: 1 Right-click a node and pick Change Label. 2 Enter whatever label text you'd like, then hit Return. What you typed appears above that node within the Node Editor. To edit a node's label:

- After a node carries a label, you're free to revise that label whenever you like by double-clicking it.

### Selecting Nodes

Whichever node is currently chosen in the Node Editor gets highlighted in orange, and goes by the name current node. Whenever you tweak any parameter or setting on the Color page, you're tweaking parameters inside the current node. Only a single node can be selected at once. To pick a node, turning it into the current node, do one of the following:

- Click any node in the node graph.
- For the prior one, pick Color > Nodes > Previous Node (Option-Shift-Semicolon); for the following one, pick Color > Nodes > Next Node (Option-Shift-Apostrophe). Used this way, the final node loops back to the first, and likewise in reverse.

The chosen node shows up highlighted in orange. You're also able to pick several nodes at once, getting ready to do things such as relocating them or building compound nodes (covered later in this chapter). To select multiple nodes:

- Command-click each of the nodes you want to simultaneously select.
- With the Node Editor Selection tool active (found at the editor's top-left corner), just drag a bounding box across the nodes you want to select.

### The Node Editor’s Selection tool

When several nodes are selected, each shows up highlighted in white, save for the current node, which stays orange.

### Selecting three nodes by dragging a bounding box

Whenever you pick a different clip in the Timeline, the standard behavior has the last node that was active when you last worked that clip become the one selected when you revisit it. That said, a setting named "Switching clips," found both in the Node Editor's option menu and in the User Preferences Color panel, lets you change how this works. To learn more about this setting, refer to Chapter 4, “System and User Preferences.”

### Disabling Nodes

As you build a node tree, it's frequently handy to switch one or more chosen nodes off so they stop affecting your grade. It's likewise handy to switch the whole node tree off and on so you can view "before and after" looks at the current clip. Disabled nodes get skipped during rendering, and they stay disabled when you store that grade with a still in the Gallery and then apply that grade to a different shot.

### Disabling Individual Nodes

Switching off a single node comes in handy for temporarily parking adjustments you suspect you won't keep but aren't ready to throw away (though bear in mind it's frighteningly easy to accidentally switch these nodes back on). It's also great for showing your client a before and after look at the most recent adjustment. To flip a single node off and on, try one of these:

- Click any node's number in the node graph to switch off that one node on its own.
- Pick one node, then choose Color > Nodes > Enable/Disable Selected Nodes (Command-D).

### Disabling Multiple Nodes All At Once

When you've selected more than one node in the node tree, using any of the techniques for switching nodes off and on covered above (Command-D included) toggles Enable/Disable Selected Nodes. Keep in mind that the current node ringed in orange always counts as part of the selection. This makes before/after comparisons easy for any mix of nodes doing intricate adjustments by selecting them, while leaving the un-selected nodes that handle base adjustments you want kept enabled untouched.

### Disabling All Nodes

Beyond the Bypass All Grades command, switching off every node in a grade at once is another simple route to disabling a grade so you get a before and after of the clip's original state (or its color managed state if Resolve Color Management (RCM) is turned on). More to the point, it's a solid way to switch off all of a grade's nodes ahead of guiding your client through each operation in that grade node by node, switching each one on in sequence as you describe how it's enhancing the image. To flip every node off and on simultaneously, try one of these:

- Pick Color > Nodes > Enable/Disable All Nodes (Option-D), which flips every node off and on.

IMPORTANT: When you switch every node off and then back on, every node gets re-enabled, including ones you'd previously disabled one at a time.

### Turning Grades and/or Fusion Effects Off

Living in the Viewer's title bar, the Bypass Color Grades and Fusion Effects button/drop-down commands can likewise be reached via the View > Bypass Color and Fusion menu commands. Switching off Fusion effects over on the Color page is a simple way to boost playback performance on underpowered machines when all you need is to knock out a few quick grading adjustments. Flipping grades off and on is also a handy way to grab a fast before and after view of a shot where the "before" goes right back to the source itself. Picking Toggle Bypass, or clicking the Viewer control, disables whatever happens to be checked in the optional menu, leaving you to decide whether to bypass both Color and Fusion together, or only one of the pair.

(Left) The menu commands that bypass Color and Fusion; (Right) the Timeline Viewer controls on the Edit page

### Resetting Nodes

When you're unhappy with your present operations and want a fresh start, there are three approaches to resetting nodes in the Node Editor. These show up as entries in the Color menu.

- Reset Selected Node Grade: Returns whichever node is currently selected to its default parameter settings, wiping out every keyframe along the way.
- Reset Grades and Keep Nodes: Sends every node across the current tree back to the default parameter settings while leaving the tree's structure untouched; each node stays put right where it sat, just reset.
- Reset All grades and Nodes: Wipes out every node and keyframe and brings back one lone node set to the default parameter settings. Resetting nodes via the mouse is another option, and it's a fast move if you happen to already be in the Node Editor handling other tasks.

Methods of resetting nodes with the mouse:

- To reset a selected node: Right-click the node in question, then pick Reset Node Grade out of the contextual menu.
- To reset all grades and nodes: Right-click on any empty backdrop of the Node Editor, then pick Reset All Grades and Nodes out of the contextual menu.

Methods of resetting nodes with the keyboard:

- To reset a selected node: Press (Shift-home).
- To reset all grades and nodes: Press (Command-home).
- To reset all grades and keep nodes: Press (Shift-Command-home).

### Previewing and Restoring Node Trees

There are two more ways to swiftly handle unwanted changes you've applied to node trees, with no need to lean on undo. Preview Memory: Gives you a preview of how any saved grade would look on the current clip. For a preview, pick Color > Preview Memory (Option-Shift-P), then right-click whatever saved still sits in the Gallery (or Memory) and pick Add Correction. You can in fact lean on Add Correction to sample as many stills as you wish. Should you like any still's look, just leave it as is. If none of the stills you sampled appeal to you, then picking Color > Preview Memory once more returns the clip to its original grade. Original Memory: This command lets you swiftly send a clip's grade back to the state it had when you first picked that clip. You reach it by choosing Color > Original Memory (OptionShift-O). It's handy for jumping straight back to a clip's original grade after you've made a run of changes you now regret. Picking a different clip in the Timeline and then reselecting the clip you changed resets what counts as the current grade.

### Caching Specific Nodes to Improve Performance

You can mark particular nodes for caching, together with every node sitting upstream of them in that node tree. By caching nodes that run processor-heavy effects, you reclaim real time headroom for the remaining downstream nodes in a grade. Picking Playback > Render Cache > User caches only the nodes you've marked for caching. Pick Playback > Render Cache > Smart mode and DaVinci Resolve handles caching on its own for any nodes running Motion Blur, Noise Reduction, or OFX plugins, with no effort on your part. To mark a node, plus every correction in upstream nodes, for caching:

- Right-click whatever node you want and pick Node Cache > On out of the contextual menu.

### Editing Node Trees

You face no cap on how many nodes you can build and wire to one another, and you can dial in as many or as few parameter adjustments as you please inside each node. The procedures below describe how you can add nodes to the node graph while assembling each grade's node tree.

### Adding Nodes

The most basic way to grow a node tree's complexity is to tack on more nodes, so you can heap further adjustments onto the current grade. You can add nodes such that they automatically attach to nodes already in the tree, ready for immediate tweaking, or you can drop unattached nodes into empty spots of the tree while gearing up to build a particularly complex and specific node tree for a tough job.

Ways to drop nodes into the tree with a mouse, tablet, or trackpad:

- To place any sort of node into the graph with the mouse: Right-click a node within the tree, then pick the node type you'd like from the contextual menu's Add Node submenu.
- To place a disconnected node into the graph: Right-click on the empty backdrop of the node graph, then pick Add Node > Corrector out of the contextual menu. A disconnected node does nothing to a tree until it's wired in.

Ways to add a node onto a currently selected node in the tree by keyboard:

- For a serial node placed after the selected node: hit Option-S key, or via the menu pick Color > Nodes > Add Serial.
- For a serial node tacked onto the tree's very end: hit Option-K, or via the menu pick Color > Nodes > Append Node.
- For a serial node placed ahead of the selected node: hit Shift-S, or pick Color > Nodes > Add Before Current.
- For nodes set in parallel with the selected node: hit Option-P, or via the menu pick Color > Nodes > Add Parallel.
- To layer a node onto the selected node: hit Option-L, or via the menu pick Color > Nodes > Add Layer.
- For an outside node attached to the selected node: hit Option-O, or via the menu pick Color > Nodes > Add Outside Node.

### Adding Nodes with Windows Turned On

For convenience, there are also dedicated commands that drop in serial nodes with Circular/Linear/Polygon/Curve windows already switched on. To place a node into the tree with its Window turned on automatically: pick whichever Nodes menu entry lines up with the following:

- Node + CPW: Circular Power window (Option-C)
- Node + LPW: Linear Power window (Option-Q)
- Node + PPW: Polygonal Power window (Option-G)
- Node + PCW: PowerCurve window (Option-B)

Any time you add a node to a tree, it gets numbered in sequence right after the most recent node you'd added, no matter where it lands in the tree. As an example, if you've already placed three nodes, and you then decide to slot another one between Nodes 1 and 2, the fresh node becomes Node 4, and the node order reads 1, 4, 2, and 3.

### Deleting Nodes

When there's a node you no longer want, you can opt to strip it out of the tree entirely to wipe out its effect for good. To delete a node, do one of the following:

- Select a node, then press the Forward-Delete key.
- Right-click a node, and choose Delete Node.

Once you've deleted a node, the nodes on either side of the one you removed get wired together automatically so the tree stays unbroken. On top of that, every node in a tree gets renumbered following any node's deletion, so there's no gap in node order. For instance, if a tree holds three nodes numbered in sequence and you delete the second, the node that used to be number 3 becomes 2.

### Connecting and Disconnecting Nodes

For a node tree to function, every node in the Node Editor has to be wired into a working node tree, running from the Source input, through each node along the way, to the Node Tree output. Any node left disconnected will cause that clip's grade to be disabled. Even so, you may find you need to detach parts of a node tree so you can rewire them differently. To connect two disconnected nodes:

- Drag a connection out from one node's RGB or key output across to the matching RGB or key input on another node, and once the line lights up, let go of the mouse button.

To change the connection from one node to another:

- Hover the pointer above the latter half of any connection line joining two nodes until it lights up blue, then click and drag to wire it instead into a different input, whether on that same node or a different one.

To disconnect two nodes, do one of the following:

- Place the pointer above the right-hand portion of a node connection so it lights up, then click it to remove it.
- Click a link to select it (a selected link turns orange), then hit the Delete or Forward-Delete key.
- Right-click a link and choose Delete Link.

To overwrite a node’s previous connection:
