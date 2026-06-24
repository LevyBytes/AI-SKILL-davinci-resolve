# Working In The Node Editor (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Working in the Node Editor

Across this chapter you'll learn the ins and outs of working in the Node Editor, covering the several approaches to adding, connecting, rearranging, and deleting nodes so you can build whatever effect comes to mind.

### FUSION 1338

### Learning to Use the Node Editor

Sitting at the center of Fusion's compositing interface is the Node Editor (which used to go by the Flow or Flow Editor). It relies on a flowchart-style layout known as a node tree, letting you assemble a composition from interlinked nodes rather than stacking layers in a layer list. Every clip you bring into the composition, plus every image-processing operation you run on those clips, shows up as a node, and connections wire them all together to carry image data from one node onward to the next. Any single node does a fairly modest job on its own, yet taken together they add up to remarkably intricate results.

The Node Editor. Here the chapter digs deeper into working in the Node Editor, walking you through adding, connecting, rearranging, and deleting nodes to produce whatever effect you dream up. To bring up the Node Editor:

- Click the Nodes button on the UI toolbar.

The Nodes button in the UI toolbar.

### Navigating within the Node Editor

Everything to do with nodes and the assembly of your composites unfolds in the Node Editor. The better you get at moving around inside it, the quicker your work will go. A handful of conventional ways exist to pan and zoom across the Node Editor, and many of them carry over from other Fusion panels. Ways to pan the Node Editor:

- Hold middle-click and drag to roam around the Node Editor.
- Keep Shift and Command pressed, then click and drag inside the Node Editor to pan.
- Use two fingers on a track pad and drag to pan across the Node Editor

Ways to zoom the Nod4e Editor:

- Push the Middle and Left buttons at once and drag to rescale the Node Editor.
- Keep the Command key held and spin your pointer's scroll control to rescale the Node Editor.
- Right-click the Node Editor and pick something from the contextual menu's Scale submenu.
- Hit Command-1 to send the Node Editor back to its default size.
- Keep the Command key held while dragging two fingers on a track pad to rescale the Node Editor.

### Automatic Node Editor Navigation

Whenever a node that's currently off-screen in the Node Editor gets selected, whether through the Find command or by clicking a node's header in the Inspector, the Node Editor pans on its own to bring that node into the visible area.

### Using the Node Navigator

One more handy way to move about the Node Editor is the Node Navigator. This is a little rectangular overview tucked into the Node Editor's upper-right corner. It offers a bird's-eye look at the whole composition, and an inner outline marks which slice of that composition the panel is currently showing. Reach for the Node Navigator when you've zoomed into a node tree and want to scan around the composition.

The Node Navigator.

To show or conceal the Node Navigator, take one of these actions:

- Right-click an empty stretch of the Node Editor, then pick Options > Show Navigator.
- Tap the V key.

To let the Node Navigator pop back up automatically as needed after you've dismissed it:

- Right-click an empty stretch of the Node Editor, then pick Options > Auto Navigator.

To resize the Node Navigator, do this:

- Drag its lower-left corner to make it bigger or smaller.

Drag the corner to resize the Navigator. To restore the default Node Navigator size, do this:

- Right-click any spot inside the Node Navigator and pick Reset Size.

To pan the Node Editor by way of the Node Navigator, do this:

- Drag inside the Node Navigator to travel between the different regions of your node tree.
- Inside the Navigator, drag two fingers on a track pad to travel between the different regions of your node tree.

### Node View Bookmarks

Bookmarks give you yet another route for getting around the Node Editor. Each bookmark stores the Node Editor's position and scale, letting you leap fast and exactly from one cluster of nodes to viewing a different one. To create a bookmark, follow these steps: 1 Pan and scale within the Node Editor until a cluster of nodes you care about is in view. 2 From the Options menu at the Node Editor's upper right, pick Add Bookmark, or hit Cmd-D. 3 When the Manage Bookmarks dialog opens, type a name for the bookmark and click the Add button.

Your first nine saved bookmarks each receive a keyboard shortcut and appear in the Options menu. The Go To Bookmarks dialog lists them too, alongside whatever bookmarks you've saved past that initial nine.

The Node Editor Options menu with nine bookmarks added

TIP: To put the Node Editor back at default scale, right-click within it and pick Scale > Default Scale, or press Cmd-1. Should your Node Tree shift and you need to revise Bookmark names or drop bookmarks, the Manage Bookmarks dialog is where you handle that. To rename or remove a bookmark, follow these steps: 1 From the Options menu at the Node Editor's upper right, pick Manage Bookmarks. 2 In the Manage Bookmarks dialog that appears, right-click the bookmark and pick Rename or Remove. 3 Click OK to dismiss the Manage Bookmarks dialog.

### Using Bookmarks

Reaching a Bookmark view is a matter of picking a bookmark from the Options menu or selecting Go To Bookmarks to bring up the Go To Bookmarks dialog. That dialog shows every bookmark in the sequence it was made within the current composition. A double-click on any entry there shifts the Node Editor to that view and shuts the Go To Bookmarks dialog. When your bookmark list runs long, the search field along the bottom of the dialog lets you type the name of whichever bookmark you're hunting for.

Changing the Sort Order and Assigning Keyboard Shortcuts Both the Options menu and the Go To Bookmarks dialog present bookmarks in creation order. Whichever nine sit at the top get keyboard short cuts. Reordering the list is something you do in the Manage Bookmarks dialog. That comes in handy when you want certain bookmarks tied to particular keyboard shortcuts, or when you'd rather a bookmark you made early on not carry a shortcut at all. To rearrange the listed bookmarks, follow these steps: 1 From the Options menu at the Node Editor's upper right, pick Manage Bookmarks. 2 Within the Manage Bookmarks dialog, drag a bookmark higher or lower in the list. 3 An insert line shows where the bookmark will land. Let go of the mouse button once that insert line is at the spot you want the bookmark listed. The keyboard short cuts then refresh to match the new order. TIP: Holding the Shift key lets you grab several bookmarks at once and shift them together up or down within the Manage Bookmark list.

### Using Underlays as Bookmarks

Any Underlay you drop into the Node Editor becomes a bookmark automatically. The Options menu lists them beneath your custom bookmarks. To keep Underlays out of the bookmark list, open the Go To Bookmarks dialog and switch off its Show Underlays checkbox. With that checkbox off, Underlays stay absent from the Go To Bookmarks dialog and won't turn up in the Options menu either.

### Adding Nodes to a Composition

Several routes exist for placing nodes into the Node Editor, the right one hinging on which kind of node you're after and how much help you need locating it. Beyond that, the method you use to add a node to a composition can also come down to how that node needs to attach to the existing node tree.

### Make Sure You’re Adding Compatible Nodes

A solid habit is to confirm, any time you add or insert fresh nodes into the node tree, that the nodes you're adding will work with the ones you mean to hook them onto. As an example, dropping a Blur, Color, Filter, Paint, or Position node in after almost any 2D operation gives you no trouble. Try to place a Merge3D node after a Glow node, though, and it won't link up on its own, since those two nodes can't join directly.

### Adding, Inserting, and Replacing Nodes Using the Toolbar

Above the Node Editor sits the Fusion toolbar, which lays out a set of frequently-used nodes as buttons each bearing its own icon. Through these buttons you can quickly drop in Merge, Background, Paint, Mask, Transform, and plenty of other everyday nodes with a single click or a drag of your pointer. The Fusion page toolbar. TIP: When you're unsure which node an icon stands for, simply rest your pointer on any toolbar button and a tooltip spells out that tool's full name. Ways to add nodes by clicking toolbar buttons:

- To place a node following a selected one: Pick a node in the Node Editor, then click a toolbar button.
- To drop a disconnected node into the Node Editor: Clear all selections in the Node Editor, then click a toolbar button.

Ways to add nodes by dragging toolbar buttons:

- To slot a fresh node into your node tree: Drag a toolbar button across into the Node Editor, landing it over the connection line that joins any two compatible nodes. Once the connection lights up beneath the node, release it and the node gets inserted.
- To make a disconnected node: Drag a toolbar button to a vacant spot in the Node Editor. Dragging a toolbar button into the Inspector likewise produces a disconnected node.
- To slot a new node after one loaded into a viewer: Drag a toolbar button onto a viewer, and a new node is inserted after whatever node is being viewed, whether or not any nodes happen to be selected.

To swap a node in the Node Editor for one from the toolbar: 1 Drag a toolbar button until it hovers right on top of the Node Editor node you intend to replace. The moment the node beneath lights up, release it.

Hauling a toolbar node over so it takes the place of a tool already there. 2 Click OK in the dialog to approve the swap. TIP: Whenever one node takes the place of another, any settings the two nodes share carry over into the new node. Swap a Transform node for a Merge, for instance, and the current center and angle values move from the Transform across to the Merge.

### Adding Nodes Quickly Using the Select Tool Window

After that, the quickest route for adding or inserting nodes into the Node Editor is the Select Tool window, which lets you find any node Fusion offers by typing just a few characters. Once it clicks for you, this will likely turn into one of your go-to methods for adding nodes. To add nodes via the Select Tool window: 1 Take one of the following actions to decide whether you're inserting a node or making a disconnected one:

- For an inserted node, pick a node compatible with the one you're about to make, and the new node slots in right after it.
- For a disconnected node, clear every selection.

2 Hit Shift-Spacebar to bring up the Select Tool dialog. 3 As the window opens, type characters that spell out part of the node's name you're after. A list of probable matches surfaces on its own, and the Up and Down arrow keys let you land on the right node (unless it's already chosen). If the exact tool's name escapes you, you can instead enter familiar keywords and categories (keyer, materials, and so on) to pull up a set of tools matching what you typed. 4 With the correct node chosen, press the Return key (or click OK), and that node gets inserted or added.

The Select Tool dialog finds any node in a flash when you know its name. TIP: Each time you call up the Select Tool window, it holds onto the text you typed for the next time you open it, so to add a second node of the same type—say you want two Blur nodes back to back—you can simply press Shift-Spacebar followed by Return to drop in that second Blur node.

### Adding Nodes from the Effects Library

Where the toolbar surfaces many of the most common nodes you'll reach for in any composition, the Effects Library holds every tool Fusion has, sorted by category, each one ready to drop quickly into the Node Editor. When you want extra help tracking down a node, or you'd just like to poke around and see what's on hand, the Effects Library makes an ideal starting point. To open the Effects Library:

- Click the Effects Library button on the UI toolbar across the top of the Fusion window. The Effects Library opens in the Fusion window's upper-left corner and is built from two panels. The category list on the left presents every available category of nodes and presets, while the list on the right reveals everything inside whichever category you've selected.

The Tools bin of the Effects Library exposing 3D nodes. Out of the box, the category list displays the main effect groups: Tools, Open FX, Templates, and LUTs; with disclosure controls on the left that reveal, in a hierarchy, every subcategory nested in each one.

Here are the categories:

- Tools: This holds all the effects nodes you draw on to assemble compositions, grouped under headings like 3D, Blur, Filter, Mask, Particles, and the rest.
- Open FX: Everything from Resolve FX plus any third party Open FX plugins you've installed lands here.
- Templates: While you're on the Fusion page in DaVinci Resolve, templates take the form of presets,

macros, and utilities built to get you up and running fast. Backgrounds, for one, gathers an assortment of tweakable generators assembled from a mix of Fusion tools. Lens flares serves up a broad range of multi-element lens flares you can drop into any composition. Particles offers a selection of ready-made particle systems you can adapt to your own needs. Shaders supplies an array of materials usable as texture maps for the 3D text and geometry you build in Fusion. And countless further categories hold useful presets and macros you can study and put to work in your own projects.

- LUTs: Here you'll find a collection of pre-installed Look Up Tables covering gamma, gamut, and colorspace conversions. Dropping a LUT into the Node Editor spawns a new FileLUT (FLUT) node with the chosen LUT file already loaded.

For more on stocking this list with your own LUTs, the place to look is Chapter 150, “Using LUTs.” Now, regarding how to add, insert, and replace tools by means of the Effects Library: when you pull nodes into the Node Editor out of the Tools category in the Effects Library, the process closely mirrors adding them from the toolbar. Ways to add nodes by clicking in the Effects Library:

- To place a node following a selected one: Pick a node in the Node Editor, then click a node within the Effects Library browser.
- To drop a disconnected node into the Node Editor: Clear all selections in the Node Editor, then click a node within the Effects Library browser.

Ways to add nodes by dragging out of the Effects Library:

- To slot a new node into the node tree: Drag a node out of the Effects Library browser into the Node Editor and over the connection line joining any two compatible nodes. Once that connection lights up beneath the node, release it and the node gets inserted.
- To make a disconnected node: Drag a node out of the Effects Library browser to a vacant spot in the Node Editor. Dragging a toolbar button into the Inspector likewise produces a disconnected node.
- To slot a new node after one loaded into a viewer: Drag a node out of the Effects Library browser onto a viewer, and a new node is inserted after whatever node is being viewed, whether or not any nodes happen to be selected.

To swap a node in the Node Editor for one from the Effects Library: 1 Drag a node out of the Effects Library browser until it hovers right on top of the Node Editor node you want replaced. As that node lights up, release it. 2 Click OK in the dialog to approve the swap.

Adding, Inserting, and Replacing Templates Using the Effects Library Bringing in items from DaVinci Resolve's Fusion page Templates category often plays out a little differently. At times, like when you add a Lens Flare, a lone node can be added or inserted into the Node Editor. In that situation, adding nodes behaves exactly as it does from the Tools category. Adding a Lens Flare effect. At other times, like when what you're adding comes out of the “How to” category, hauling one lone item from the Node Editor pulls a whole node tree into the Node Editor. Helpfully, every node of that incoming node tree is selected automatically when you do this, making it easy to drag the whole tree to a roomier spot in the Node Editor. When that occurs, the incoming effect's nodes are laid bare so you can rewire and reconfigure it however you need to fold the effect into the rest of your composition.

Pulling in a LightWrap effect out of the “How to” bin within the Effects Library's Templates category.

### Adding, Inserting, and Replacing Nodes Using the Contextual Menu

Yet another approach for adding, inserting, and replacing nodes leans on the Node Editor's contextual menu, whose dedicated submenus let you spin up any sort of node Fusion provides. It's handy when your pointer is already in the Node Editor busy selecting, moving, or wiring nodes. Ways to add nodes through the contextual menu:

- To add a node: Right-click a blank area of the Node Editor and pick a node from the Add Tool submenu.
- To insert a node: Right-click an existing node in the Node Editor and pick a node from the Insert Tool submenu.
- To replace a node: Right-click an existing node in the Node Editor and pick a node from the Replace Tool submenu.

TIP: Replacing one node with a different one carries over whatever settings the pair have in common into the replacement. Swapping a Transform node out for a Merge, say, brings the Transform's current center and angle values along to the Merge.

### Deleting Nodes

To remove one or several selected nodes, hit Delete (macOS) or Backspace (Windows), or right-click the selected node(s) and pick Delete from the contextual menu. The node leaves the Node Editor, and whatever was wired to its primary input and output gets joined to each other. Anything tied to its other inputs (mask inputs, for example) ends up disconnected.

A node tree shown just before one node is deleted (top), and afterward once the upstream and downstream nodes have rejoined on their own (bottom).

### Disconnected Nodes

There's nothing wrong with leaving disconnected nodes, or even whole disconnected branches of a node tree, sitting in the Node Editor next to the rest of a composition. Every disconnected node is just passed over yet kept around in case it proves useful down the road. That helps when you're holding onto nodes you tailored but later concluded you don't need. It also serves for keeping tree branches you've since exported as self-contained media that gets re-imported to stand in for the original effect, while you preserve the original nodes in case you ever have to redo the work.

### Selecting and Deselecting Nodes

Before you can do anything with nodes in the Node Editor, or tweak node parameters over in the Inspector, you first have to get the hang of selecting whichever node or nodes you mean to work on.

### Selecting Nodes

Selecting nodes ranks among the most basic moves for repositioning them or singling them out for various operations. Several techniques are at your disposal. Ways to select nodes: To grab a single node: Click any node in the Node Editor. To grab several nodes one by one: Command-click each node you'd like included. To grab an entire region of nodes: Drag a bounding box around every node you want. To grab all upstream or downstream nodes: Right-click a node and pick Select > Upstream Nodes/Downstream Nodes from the contextual menu. To grab every node in the Node Editor: Press Command-A. To grab a node by way of the Keyframe Editor: Click any layer there, and the matching node in the Node Editor is selected.

### The Active Node

Pick a single node through any of the techniques above and that node becomes the active node, glowing orange to signal its parameters are right then editable in the Inspector (assuming the Inspector is open). The orange also tells you that node is the one certain operations (like inserting new nodes) will act on. You can have many nodes selected, but only ever one active node. To keep them distinct, the active node stays orange while every other selected node turns white. Nodes that aren't selected wear plain black outlines.

Orange marks the active node, whereas the other selected nodes show white. To designate the active node while several nodes are selected:

- Option-click one of the selected nodes in the Node Editor, and that one becomes active.
- Open the Inspector if you must, then click a node's header bar to promote it to active.

### Deselecting Nodes

Deselecting nodes, when you need to, behaves about how you'd guess. Ways to deselect nodes:

- A single click on the Node Editor's background clears every selection.
- Pressing Command-Shift-A clears every selection.
- Command-click peels off selected nodes one at a time.
- A Command-drag bounding box clears a batch of selected nodes all at once.

### Loading Nodes into Viewers

Once a composition is underway, your next lesson is how to view the particular nodes you intend to work on. This matters because the pairing of which node you're viewing with which node is selected (and they aren't always one and the same) frequently decides which onscreen controls show up and what they look like. The example below has you rigged to rotoscope an image with a Polygon node hooked into the garbage mask input of a MatteControl node that's bringing the mask in as an alpha channel.

A node tree set up to handle a straightforward rotoscoping task.

The screenshot above shows why you'd send the upstream MediaIn or Loader node to a viewer while keeping the Polygon node selected for editing: it lets you see the whole image you're rotoscoping and still keep the Polygon node's spline on display.

### Viewed Nodes When You First Open Fusion

The first time you open the Fusion page in DaVinci Resolve, viewer 2 typically shows the output of the present empty composition (the MediaOut1 node). In Dual-viewer mode, viewer 1 stays blank until you hand a node to one of them. The first time you launch Fusion Studio with an empty comp, both viewers stay blank even after you've read in media through a Loader node. The viewers show content only once you assign a node to one of them. A handful of different methods exist for putting a node in a viewer, and which you pick comes down to your own working style.

### Node View Indicators

Sitting beneath every node, the View indicators do two jobs. For one, they act as a clickable means of pushing a node's output into one of the viewers. For another, they signal which nodes in the Node Editor are currently being viewed. By default you get two round indicators standing in for the two viewers. The left one maps to the left viewer and the right one to the right viewer, no matter whether both viewers are on screen or only one.

A viewer indicator switched on for the right viewer and off for the left one. To send a node to a viewer by way of the Node View indicators:

- A click on an indicator turns it white, signaling that node now sits in the matching viewer. Click once more and the indicator goes black, pulling the node out of the viewer. A node only shows its View indicators while it's being viewed. To bring the indicators up otherwise, hover the pointer over the node and they appear, ready to click.
- Keyboard shortcuts can toggle each View indicator as well. The two default viewers carry the numeric shortcuts 1 and 2. Press the matching number once to send the selected node to the right display, and press it again to clear that display.
