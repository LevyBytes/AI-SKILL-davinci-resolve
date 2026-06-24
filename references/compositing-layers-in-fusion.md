# Compositing Layers In Fusion (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Compositing Layers in Fusion

The aim of this chapter is to ground you well enough to shift comfortably from a layer-driven compositing program over to the node‑based workflow of Fusion. You will find down-to-earth guidance on how a node tree can be organized for straightforward layered composites.

### Applying Effects

Rather than jumping straight into composites built from many layers, we'll begin with a few really basic effects and grow our knowledge outward from there. When you open the Effects Library and click the disclosure control sitting to the left of Tools, a set of categories appears that holds every node Fusion offers. Recall that an individual node performs a single task, and when several of them work together you can assemble remarkably intricate output starting from modest pieces. Click the Effect category and its items appear. For this walkthrough we'll work with the TV effect.

Browsing the Effect category to find the TV node

### Adding a Node to the Tree

Suppose the MediaIn node on the Fusion page (or the Loader node in Fusion Studio) happens to be selected at that moment inside the Node Editor; a single click on, say, the TV node within the Effects Library drops that node into the tree just downstream of whatever was selected. Over on the Fusion page it shows up in the viewer right away, and that's because the MediaOut1 node is the one being viewed—so everything feeding into MediaOut1 from upstream gets processed and displayed.

### A new node added from the Effects Library

Within Fusion Studio you have to hit either the 1 or the 2 key to push the selected node into the viewer. Plenty of other techniques exist for placing nodes into a tree, yet learning your way around the Effects Library is a worthwhile starting point.

### Editing Parameters in the Inspector

If you want to refine an effect, head to the Inspector on the right and tweak that node's parameters. Whatever node is selected presents its controls there in the Inspector, where the majority of nodes carry a handful of control tabs shown as tiny icons sitting right below the node's title bar.

The Inspector displaying the TV effect's parameters Clicking the final panel on any given node brings up the Settings panel. A Settings panel belongs to every node, and it holds the parameters common to all nodes—things like the Blend slider together with the RGBA buttons. With these you decide which image channels get touched, and you can mix between the original picture and the applied effect.

The Settings panel, holding the channel-limiting plus mask-handling controls common to every node With the TV effect, as an instance, the output carries quite a bit of transparency, since the scan lines that get drawn in are likewise written into the alpha channel, which produces alternating transparent rows. Switching off the Alpha checkbox yields a more opaque picture, and if you open the Controls tab (that's the first tab) and push the Scan Lines slider rightward so its value climbs to 4 you'll get a stronger television look.

The TV effect as it started (left), alongside tweaks to the TV effect that render the clip more opaque (right)

### Replacing Nodes

Inside the Effect category of the Effects Library there's also a Highlight node, which scatters glints across an image's brightest spots. Rather than clicking the Highlight node—that would tack it on after whatever node is selected—you can drag a node out of the Effects Library and drop it directly onto a node inside the Node Editor, which swaps out the node there in the Node Editor.

Dropping a node out of the Effects Library over a node within the Node Editor so it gets swapped Here the Highlight1 node steps into the spot held by the TV node within the tree, and the fresh effect shows up in the viewer—in this case star-shaped highlights sitting over the image's lights. Now it's a matter of reaching for the Inspector controls to tailor the effect.

### Adjusting Fusion Sliders

As you drag any slider over in the Fusion Inspector—here that's the Number of Points slider—a small dot shows up below it. That dot marks where the slider's default value sits and additionally doubles as a reset control whenever you click on it.

Adjusting a slider reveals a reset button underneath it Every slider has its own particular span of minimum and maximum values, tied to whichever parameter is being changed. Here the Number of Points slider tops out at 24. That said, plenty of sliders (though not all of them) can have their range remapped if you type a bigger figure into the number field beside the slider. The moment you do, the slider's handle slides leftward as the range stretches to fit the value you just supplied.

Typing a bigger figure to widen the span across which a slider can work

### Compositing Two Clips Together

Fun as it may be to drop in single nodes for simple effects, sooner or later you'll want to bring in extra layers of footage so they can be merged into composites. Let's shift focus to a different scenario where a background clip needs to be combined with a foreground clip carrying a built-in alpha channel, so we can watch basic layering at work.

### Adding Additional Media to Compositions

It happens regularly that what begins as a fairly modest idea ends up requiring more media before you achieve the look you're after.

- Within Fusion Studio you handle this by bringing in more Loader nodes. Drop a fresh Loader node onto a blank spot in the Node Editor and you'll get a free-floating Loader2 node (numbered upward so it stays unique), which you can then wire up however you like.
- On the Fusion page you can pull up the Media Pool and drag clips straight onto the Node Editor to bring them into your tree. Drag a clip out of the Media Pool onto a blank region of the Node Editor and you'll get a free-floating MediaIn2 node (numbered upward so it stays unique), which you can then wire up in whatever fashion suits you.

The Media Pool as seen in the Fusion page

### Automatically Creating Merge Nodes

Should you want the arriving clip hooked up right away as the uppermost layer—the foreground—of a composite, then in Fusion Studio pick the Loader1 node and add a second Loader node. On the Fusion page, drag the new clip out of the Media Pool directly onto any connection line. Either way, the incoming MediaIn or Loader node turns automatically into the "foreground input".

Pulling a node out of the Media Pool over a connection (left), then releasing it so a Merge node composite forms (right) The Node Editor is packed with shortcuts of this sort so your compositions come together faster. Here's one for the case where a disconnected node needs compositing against a different node via a Merge node. Pull a connection out of the output of whichever node should be the foreground, and let go of it on top of the output of whichever node should be the background. That action spawns a Merge node automatically to assemble the composite. Don't forget: background inputs show up orange, while foreground inputs show up green.

Pulling a connection out of a disconnected node toward a second node's output (left), then releasing it so a Merge node composite forms (right) Adding Clips to a Fusion Composition From the File System Drag clips from your file system straight into the Node Editor and they get folded into the DaVinci Resolve Media Pool for you. So when you keep a collection of stock animated background textures and you've located one you'd like to use through your file system's search tools, just drag it directly into the Node Editor and it lands in whatever bin of the Media Pool is currently active.

### Fixing Problem Edges in a Composite

In the majority of cases the Merge node handles things flawlessly when fed a foreground image with premultiplied alpha transparency to lay over a solid background. Every now and then, though, you might spot a thin band of fringing right along the border between a foreground element and the transparent region, like what you see in the close-up below. That faint brightening along the edge is a giveaway that the clip most likely wasn't premultiplied. Every foreground image carrying an alpha channel is assumed by the Merge node to be premultiplied. Happily, this is a simple thing to remedy.

A touch of fringing along the border of a foreground element ringed by transparency Click on the Merge node belonging to that specific composite to select it, then hunt down the Subtractive/ Additive slider.

The Subtractive/Additive slider, handy for correcting or reducing fringing within composites Pull the slider fully leftward into the Subtractive position, and the fringing goes away.

An alpha-carrying clip showing fringing (left), and that fringing resolved after pulling the Subtractive/Additive slider leftward (right) That Subtractive/Additive slider—available only while the Apply mode sits on Normal—governs whether Normal mode runs an Additive merge, a Subtractive merge, or some mixture of the two. By default the slider sits on Additive merging, which presumes every input image with alpha transparency is premultiplied (true most of the time). In case the distinction between Additive and Subtractive merging isn't clear to you, here's a brief rundown:

- An Additive merge—slider pushed fully right—is what you want when the foreground image is premultiplied, that is, when the color-channel pixels have already been multiplied against the alpha-channel pixels. Because of that, transparent pixels come out black every time, given that anything times 0 equals 0. The background gets hidden (through multiplication by the inverse of the foreground alpha), and then the foreground's pixels are simply added on top.
- A Subtractive merge—slider pushed fully left—is what you need whenever the foreground image isn't premultiplied. The approach resembles an Additive merge, except the foreground image first gets multiplied against its own alpha to strip away any background pixels lying beyond the alpha region.

The Additive/Subtractive slider gives you a way to mix between the two flavors of the merge—one Additive, the other Subtractive—so you can hit the right balance for your specific composite. Mixing the two now and then helps with troublesome composites whose edges draw the eye by being either too bright or too dark. As an example, applying Subtractive merging to a premultiplied image can darken the edges, while applying Additive merging to a non-premultiplied image causes any non-black region beyond the foreground's alpha to be summed into the output, which brightens the edges. Sliding between Additive and Subtractive lets you dial the edge brightness in until it looks just right for your case.

### Using Composite Modes in the Merge Node

In layer-based programs, you frequently reach for Blend modes to make a composite more believable. Those Blend modes live inside the Merge node, since the Merge node is the place where one layer is laid over another. Imagine a case where you'd like the Screen mode to give a foreground image more of a reflection-like quality. Built into the Merge node is a whole assortment of controls for producing nearly any compositing effect you might want. The things you'd recognize as Blend modes sit in the Apply Mode pop-up menu. These mathematical compositing modes let you fuse the foreground and background layers together. A Blend slider is on hand for dissolving the foreground input into the background. Tweaking the Merge node's Apply Mode together with its Blend slider over in the Inspector NOTE: Pick any Apply Mode setting apart from Normal and the Subtractive/Additive slider vanishes, since the underlying math wouldn't hold up. That's nothing out of the ordinary; the Inspector hosts plenty of controls that tuck themselves away when they aren't needed or when some input is left unconnected. The Screen node works beautifully for faking reflections, and dropping Blend down a touch lets you even out the foreground against the background. The effect is gentle, yet it does help sell the shot. TIP: It may not have escaped you that the Merge node likewise carries a group of Flip, Center, Size, and Angle controls, which let you transform the foreground image without bringing in a separate Transform node. That's a tidy shortcut for streamlining node trees of any size.

### Creating and Using Text

For the next exercise, we'll look at building a basic text object by means of the Text+ node. After that, we'll see how the text generator's alpha channel can be pushed into a second image to assemble a richer composite.

### Creating Text Using the Text+ Node

For making 2D text on the Fusion page, the Text+ node is the go-to tool. When you're in DaVinci Resolve, this is the very same Text+ generator you'll find on the Edit page. You can grab it conveniently right from the toolbar. As a text-effects tool the Text+ node runs incredibly deep, packing six tabs of controls that cover everything from styling the text, to various ways of laying it out, to an array of shading options—fills, outlines, shadows, and borders among them. Powerful as it is, this exercise will only graze its surface. We'll begin with a MediaIn node acting as our background, selected within the Node Editor. Click the Text+ button and a new Text+ node is created automatically, wired in as the foreground input of a Merge node. You'll get the very same behavior in Fusion Studio, only with a Loader node.

Picking the node onto which you intend to tack a further node (top) Pressing the Text+ button along the toolbar spawns a Merge composite on its own, with the text wired in as the foreground input connection (bottom) When you select a Text node, the Inspector opens to its default Text panel parameters, and a toolbar specific to that node also appears across the top of the viewer. Click the leftmost tool and you can type straight into the viewer, or alternatively type into the Styled Text field over in the Inspector.

The Text node's viewer toolbar, offering tools that handle text entry, kerning, plus outline controls

While the Merge is the thing on display, the text surfaces in the viewer sitting atop the background clip. Controls appear right onscreen for spinning the text (via the circle) and shifting its position (using the red center handle plus the two arrows), and a dim cursor is there as well, allowing us to edit and kern the text by means of the viewer toolbar's remaining tools.

Text entered directly into the viewer, accompanied by onscreen controls for transforming the text

### Styling and Adjusting Text

For styling the text, turn to the Inspector controls, adjusting text-style options such as Font, Size, and Tracking to alter how far apart the letters sit.

### The restyled text

TIP: Keep the Command key pressed as you drag any Inspector control and the change becomes "geared down," letting you fine-tune in smaller, more gradual steps.

Choosing the Manual Kerning tool over in the viewer toolbar (it's the second tool from the left) brings up small red dots beneath every letter of the text. Click the red dot below a given letter and a kerning highlight lands over that letter.

### The Manual Kerning tool in the viewer toolbar

To make manual kerning adjustments: 1 Option-drag the red dot beneath any letter to shift that character's kerning, with the letter's motion held to the left and right. Letters can also be dragged up and down to achieve other looks. On some systems the kerning of the letter being adjusted won't refresh until you release the red dot into position. 2 If the result isn't to your liking, you can open up the Advanced Controls in the Inspector and wipe out either the kerning on just the selected letters or every manual kerning adjustment, then start fresh.

Option-dragging the small red dot exposed by the Manual Kerning tool so kerning can be tuned by hand

### Using Text as a Mask

The text can be filled with a solid color or a gradient, or it can serve as a matte that cuts its letters out of a different image. To begin, we'll drag a second clip—a chalkboard covered in math—out of the Media Pool onto the Node Editor as a free-floating MediaIn2 node.

### Disconnecting and Reconnecting Nodes

Picking up from the earlier example, where a MediaIn served as the background and the Text+ as the foreground into a Merge, a bit of rearranging is in order. Click the latter half of the connection running from the Text1 node to the Merge foreground input and it detaches.

Clicking a connection's latter half to detach it (previous page), and how things look once the text node is detached (above) Once a MediaIn2 or Loader2 node is wired onto the Merge1 node's foreground input, the whole viewer fills with the MediaIn2 (granting that we're still looking at the Merge node). Now we have to feed the Text1 node's image in as an alpha channel into the connection for the MediaIn2 node, and a MatteControl node is how we pull that off.

The revised composite, where two video images are now wired in and the text node sits detached

### Using Matte Control Nodes

Pick the MediaIn2 node, then click the Matte Control button on the toolbar to drop it in between the MediaIn2 and Merge1 nodes. (For tidiness I've nudged the nodes around a little in the screenshot.) The MatteControl node serves all sorts of purposes. One of them is gathering up one or more alpha channels, mattes, or images fed into the Garbage Matte, Solid Matte, and/or foreground inputs, combining them, and then applying the result as an alpha channel onto whatever image is wired into the background input. It's essential to confirm that the image you intend to give an alpha channel is plugged into the background input of the MatteControl node, otherwise the MatteControl node simply won't do its job.

The second image properly connected to the MatteControl node's background input Once that's set, wiring the Text+ node's output (which carries the alpha channel) into the MatteControl node's Garbage Matte input is a shortcut for building a mask, matte, or alpha that knocks a transparent area out of an image. Bear in mind it's all too easy to plug into the wrong input by accident. Since the inputs shuffle around based on what's connected and where the node sits (and, honestly, the colors are tough to track while you're still learning), it's vital to keep an eye on the tooltips for whichever input you're dragging a connection toward, so you can be certain you've got the right one. If you don't, the effect falls flat, and whenever an effect isn't behaving, the very first thing to confirm is whether the correct inputs are connected.

Option-dragging a node connection and letting it fall onto a second node brings up a node input menu

There's another way to link nodes: hold the Option key as you drag a connection from one node's output and let it fall onto the body of a second node. Doing so brings up a popup menu where you can pick, by name, exactly which input you want. Keep in mind the menu only surfaces once you've dropped the connection on the node and let go of your pointing device's button. As soon as the Text1 node is correctly tied to the MatteControl node's Garbage Matte input, a text-shaped transparent region appears for the graphic when you load the MatteControl node into the viewer.

Wiring the Text node into the MatteControl node's Garbage Matte input (previous page), along with the hole that gets knocked through the image as a result (above) Customizing Matte Control Nodes The Inspector lets you tweak a few parameters until you land on the result you're after. Within the Inspector controls for the MatteControl node, opening up the Garbage Matte controls exposes parameters that govern how the Garbage Matte input gets applied to the image. For instance, you might decide to fill the text mask with the image rather than punching a hole through it.

### Using Transform Controls in the Merge Node

Living in the Inspector, the Merge node carries a group of transform parameters that act specifically on the foreground input's image. That makes it fast and simple to nudge a foreground image into alignment with the background without bringing in another node.

The Merge node's transform controls, which act upon the foreground input's image NOTE: Should you feed two differently sized images into a Merge node, it's the background image's resolution that sets the node's output resolution. Bear that in mind whenever resolution problems crop up. The Size slider is there to scale the foreground.

### The final composite

### Building a Simple Green-Screen Composite

Pushing compositing one notch further, the upcoming example demonstrates how a multilayered Timeline—like the kind found on DaVinci Resolve's Edit page—maps onto nodes within Fusion's node tree. We'll lean on DaVinci Resolve here, but grasping how layers translate into nodes can help anybody just getting comfortable with a node-based interface. For this example we'll put together a simple composite from a green-screen key plus two additional layers to build a news story.

### Mapping Timeline Layers to Nodes in Fusion

Three layers within a Timeline make up this composite. Within that Timeline sit a background graphic riding video track 1, a green-screen clip riding video track 2, plus a foreground graphic riding video track 3.

The background riding video track 1 (top left), the green-screen clip riding video track 2 (bottom), and the graphic file riding video track 3 (top right) Built into any timeline-based system is the idea that video tracks with higher numbers sit more toward the front—nearer the viewer. Video track 1 acts as the background beneath all the rest. Video track 3 lies ahead of video track 1 as well as video track 2. TIP: Working in DaVinci Resolve, you're able to carry all three layers off the Edit page and into Fusion by turning them into a Fusion clip. To read more about building Fusion Clips, consult Chapter 65, "Getting Clips into Fusion." within the DaVinci Resolve Reference Manual, or else Chapter 3 of the Fusion Reference Manual.

A pile of clips destined for a composite (previous page), and that pile being converted into a Fusion clip on DaVinci Resolve's Edit page (above) Over in Fusion, every video clip stands for a MediaIn on the Fusion page or a Loader in Fusion Studio. In the example down below, the MediaIn2 corresponds to video track 2, and MediaIn 1 corresponds to video track 1. Those two pieces get composited through a Merge node (foreground laid over background, in that order). The combined output of that pair becomes the first Merge node's output, which in turn feeds in as the background to a second Merge. Chaining Merges one after another costs you nothing in quality and involves no precomposing. MediaIn3 stands for video track 3 and serves as the ultimate foreground in the tree, being the layer on top.

The starting node tree formed from the three clips we converted into a Fusion clip Now that this node tree has been built to echo the video layers, we can spend the remainder of the example adding whatever nodes each branch of the tree requires to produce the green-screen composite.

### Pulling a Green-Screen Key Using the Delta Keyer

For this composite you have to generate transparency behind the newscaster. As you work inside a node tree, you'll grow used to shifting existing nodes aside to clear room for new ones. Frequently you'll slide nodes off to one side or up overhead to open up space for the extra nodes.

Opening up room past the MediaIn nodes and picking the second of them, getting ready to drop in a node Green-screen keying's primary tool is the DeltaKeyer node. It hooks onto the output of whichever node stands in for the green screen—here that's the MediaIn2 node. With MediaIn2 selected, hit Shift-Space to bring up the Select Tool dialog, where any node can be searched for and inserted. Down below we've placed the DeltaKeyer right after the MediaIn2 node but ahead of the merge with the background.

Adding a DeltaKeyer node inline after the MediaIn2 node As a keyer the DeltaKeyer node is quite advanced, able to deliver striking results by blending various sorts of mattes alongside a clean-plate layer, yet it can also be driven very simply provided the background needing the key is well lit. And once the DeltaKeyer has pulled a key, it bakes the resulting alpha channel right into its output, so for this simple scenario it's the lone node we have to add. It's also worth pointing out that even though we're using the DeltaKeyer on a green screen, it isn't confined to keying only green or blue; the DeltaKeyer can pull striking keys off any color in your image.

Dragging the Eyedropper to the viewer samples the screen color
