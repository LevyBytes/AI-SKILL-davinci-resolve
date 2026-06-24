# Grade Management (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Bringing up a compound node inside a floating Node Graph window Copying Nodes by Way of Display Node Graph The steps that follow walk through opening the floating node graph under various circumstances. To pull individual nodes or settings out of any Gallery still: 1 In the Timeline, click the thumbnail of the clip you intend to copy nodes into. The Node Editor then displays its node graph. 2 Over in the Gallery, right-click a still you want to take nodes from and pick Display Node Graph. Up pops a floating Node Graph window holding that still's node tree. 3 (Optional) With the Gallery Node Graph window open, you may click any other still and the window refreshes to present whichever still is now selected, set for you to copy from. 4 Within the floating Node Graph window, pick Clip to copy a clip's attributes as a whole, or pick Node to copy attributes of one node. 5 Carry out one of the following to bring nodes or settings into the Node Editor.

- Under Clip mode, grab any node out of the floating node graph and drag it onto the Node Editor's current grade, dropping it over an existing node to replace that node's settings. Should you open the Node panel and pick out particular attributes, only those carry over to the node you drop onto.
- Under Clip mode, grab any node out of the floating node graph and drag it onto the Node Editor's current grade, dropping it on a connection line so it slots in as a new node. Should you open the Node panel and pick out particular attributes, only those carry over to the freshly made node.
- Under Clip mode, hit Apply Color to bring the whole grade across from the floating node graph and replace the Node Editor's current grade.
- Under Clip mode, hit Apply PTZR to bring the sizing across from the floating node graph and replace that of the current clip.
- Under Clip mode, hit Apply Source to bring the source settings across from the floating node graph and replace those of the current clip.
- Under Clip mode, hit Apply All to bring every setting across from the floating node graph onto the current clip.
- Under Node mode, mark which attributes to copy, then grab any node from the

floating node graph and drag it onto the Node Editor's current grade, dropping it over an existing node to replace, on that node, only the settings you marked.

- Under Node mode, mark which attributes to copy, then grab any node from the floating node graph and drag it onto the Node Editor's current grade, dropping it on a connection line so it slots in as a new node carrying only the settings you marked.

6 With the floating Node Graph window still open, you may likewise click any clip in the Thumbnail timeline to swap which grade the Node Editor shows, ready for copying onto. 7 Hit Close once you are done. To pull individual nodes or settings out of any Timeline clip: 1 In the Timeline, click the thumbnail of the clip you intend to copy nodes into. The Node Editor then shows its node graph. 2 Right-click the thumbnail of a different clip you wish to take nodes from and pick Display Node Graph. NOTE: The Display Node Graph command shows up in the contextual menu only for a Thumbnail timeline clip that is not the one currently selected. 3 (Optional) Inside the floating Node Graph window, pick Clip to copy a clip's attributes as a whole, or pick Node to copy attributes of one node. 4 Carry out one of the following to bring nodes or settings into the Node Editor.

- While in Clip mode, drag a node from the floating node graph over to the grade currently in the Node Editor and let it fall on an existing node, which overwrites that node's settings. Open the Node panel and select specific attributes, and just those attributes transfer to the node you dropped onto.
- While in Clip mode, drag a node from the floating node graph over to the grade currently in the Node Editor and let it fall on a connection line, where it is inserted as a brand-new node. Open the Node panel and select specific attributes, and just those attributes transfer to the new node that results.
- While in Clip mode, press Apply Color to carry the full grade from the floating node graph over, replacing the grade currently in the Node Editor.
- While in Clip mode, press Apply PTZR to carry the sizing from the floating node graph over, replacing that of the current clip.
- While in Clip mode, press Apply Source to carry the source settings from the floating node graph over, replacing those of the current clip.
- While in Clip mode, press Apply All to carry every setting from the floating node graph over onto the current clip.
- While in Node mode, choose the attributes to copy, then drag a node from the floating node graph over to the grade currently in the Node Editor and let it fall on an existing node, overwriting on that node just the settings you chose.
- While in Node mode, choose the attributes to copy, then drag a node from the floating node graph over to the grade currently in the Node Editor and let it fall on a connection line, inserting it as a new node holding only the settings you chose.

5 (Optional) With the floating Node Graph window still open, you may likewise click any clip in the Thumbnail timeline to swap which grade the Node Editor shows, ready for copying onto. 6 Hit Close once you are done.

### Rippling Adjustments Among Multiple Clips

Having graded a run of clips, if you discover you need a fast change pushed across several of them at once, the Color > Ripple Node Changes to Selected Clips/Current Group commands let you swiftly copy one clip's changes onto a number of others. These commands do, though, demand that you observe a few rules to land the outcome you are after. Rippling keys off each node's number to work out which changes flow to which nodes. Put differently, a change on Node 3 flows to the matching Node 3 on each remaining selected clip, or alternatively onto Node 3 across the rest of the current group's clips (which of the two depends on the command you pick). For changes to ripple from one clip onto several, all the clips must carry the same node count, at least for whichever nodes you are rippling. Attempt to ripple a change onto one or more clips lacking a node whose number matches the one you are rippling, and those clips receive no change at all. To ripple one node's change onto several selected clips: 1 Pick the clip you will use to make the change so it becomes the current clip, outlined in orange. 2 Then Command-click or Shift-click to pick the span of clips you want the change rippled onto, leaving them all selected in red.

The orange-outlined clip is the current one you are modifying, while the red-highlighted clips are those receiving the rippled change There is no requirement to pick the destination clips before you make the change, yet staging it all ahead of time can make it simpler to track what you are doing. The clip under modification ought to be outlined in orange, and the clips taking the rippled change ought to be highlighted in red. 3 Choose a node to alter. Ideally each selected clip carries a node whose number matches the one you are altering. Where a clip lacks that, it will not pick up the change you are about to ripple. 4 Apply whatever changes are needed, working any of the Color page's palette controls you require, apart from Camera Raw, Sizing, and Data Burn, which are not node‑specific. 5 Once the change satisfies you, pick Color > Ripple Node Changes to Selected Clips.

Your change ought to ripple onto every other selected clip that has a node of that same number, and within moments those clips' thumbnails ought to refresh to reflect it. Where you have built a group, rippling node tweaks onto the group's other clips is easier still. To ripple one node's change onto the current group: 1 Pick the clip you will use to make the change so it becomes the current clip, outlined in orange. For this to function it has to belong to a group. 2 Choose a node to alter. Ideally each selected clip carries a node whose number matches the one you are altering. Where a clip lacks that, it will not pick up the change you are about to ripple. 3 Apply whatever changes are needed, working any of the Color page's palette controls you require, apart from Camera Raw, Sizing, and Data Burn, which are not node‑specific. 4 Once the change satisfies you, pick Color > Ripple Node Changes to Current Group. Your change ought to ripple onto every other clip in the current group that holds a node of that same number, and within moments those clips' thumbnails ought to refresh to reflect it.

### Appending a Node to Multiple Clips

When you have tweaked a node on one clip and would like that tweak on several others, the Color > Append Node to Selected Clips command gets it done in a hurry. Run it ahead of one of the Ripple Node Change commands as a fast way to ensure several as-yet-ungraded clips share the same nodes, or run it on its own as a fast way to push the same node change onto several clips whether or not their node trees line up. To append a node onto other selected clips: 1 Pick the clip you will use to make the change so it becomes the current clip, outlined in orange. 2 Pick the node you wish to append onto other clips. 3 Then Command-click or Shift-click to pick the span of clips you want the change rippled onto, leaving them all selected red. The clip you copy from ought to be outlined in orange, and the clips taking the rippled change ought to be highlighted in red. 4 Pick Color > Append Node to Selected Clips. The chosen node ought to land at the tail of each selected clip's node tree, and within moments those clips' thumbnails ought to refresh to reflect it.

### Using Shared Nodes

Shared nodes exist to bring the payoff of automatically rippled changes across clips to colorists who favor a node layout flatter than Group Grading permits. Convert individual Corrector nodes into Shared nodes and copy them onto multiple clips, and you switch on linked adjustments straight from inside the clip grade. What that means is the clip grade is free to blend both clipspecific nodes and Shared nodes together inside one node tree. That keeps Shared nodes quick to work with, since you need not build groups or jump to a group node tree (the next section's topic) to enjoy linked adjustments across several clips.

A grade carrying an Unshared node (at left) and a Shared node (at center); a badge flags the Shared node, which is locked as well

### What Are Shared Nodes Good For?

A Shared node resembles a group grade, save that it asks for no grouping and drops into any ordinary grade. Whatever you change on a Shared node ripples on its own to every other copy of that node sitting in other clips' grades. On top of that, you may add as many Shared nodes to a grade as you wish and order them however you like to govern the sequence in which their operations run. And naturally you can scatter them among run-of-the-mill Corrector nodes Shared nodes are tremendously flexible. As examples, Shared nodes let you:

- Place a Color Space Transform Resolve FX or a LUT at the front of every clip drawn from one particular source
- Place a base correction on every talking-head shot of one particular interviewee
- Place a shot-matching tweak on each clip shot from one particular coverage angle

within a scene

- Place a stylistic tweak on every clip in one specific scene
- Lay down your base adjustments while grading with remote versions, so those adjustments

stay linked once you copy your remote versions onto local versions for fine tuning You can in truth mix and match Shared nodes across differently overlapping clip sets to pull off any or all of the above in one go. For instance, add one Shared node to adjust every clip from a given camera, add a second onto whichever of those clips fall in a given scene, then add a third onto whichever of those happen to be closeups of the lead actress, before tacking on one or two regular, unshared Corrector nodes for clip-specific tweaks.

### Creating Shared Nodes

Making a Shared node is simple, provided you have already built a node holding an adjustment you would like spread across several clips. To make a Shared node:

- Right-click any Corrector node and pick Save as Shared node.

### Locking Shared Nodes

The moment you convert a node into a Shared node, it locks on its own, which stops you from inadvertently adjusting it in ways that would hit every other grade relying on that same Shared node. To flip a Shared node's lock state, take one of these routes:

- Right-click any Shared node and pick Lock Node from the contextual menu.
- Bring up the Keyframe Editor, then within that node's keyframe track click the Lock icon sitting in its track header.

### Copying Shared Nodes

Since Shared nodes are at bottom just Corrector nodes living inside clip grades, handling them is painless. Having built one or more Shared nodes, you have several routes for copying them onto other clips' grades throughout your program so you can cash in on the linked adjustments they afford. Routes for copying Shared nodes across several clips: Adding a Shared node onto a different clip's grade through the Node Editor contextual menu: As soon as a node is saved as a Shared node, it turns up at the foot of the Node Editor contextual menu's Add Node submenu, so dropping any Shared node onto any clip is trivial. Give the Shared node a custom label and that label is what shows in the contextual menu, making it quicker to spot. Folding Shared nodes into a basic grade bound for copying onto other clips: Build one or more Shared nodes while first assembling a grade, and copying that grade onto other clips brings the Shared nodes along by default. Storing a Shared node as a Gallery still and putting it on other clips: Stash a grade containing a Shared node in the Gallery, and each time you copy that Gallery still onto another clip its Shared node rides along. Building a Shared node and tacking it onto a batch of further clips: If you have already graded a handful of clips in a scene, drop a Shared node at the tail of one clip's grade, keep it selected, then select every other clip in the scene and pick Append Node to Selected Clips. Leaning on Shared nodes to hold linked adjustments while copying remote grades onto local grades: Lay your base adjustments with Shared nodes while grading via Remote Versions to auto-copy those grades onto other clips sharing the same source media, and the adjustments hold their link once you copy the remote versions onto local versions for fine tuning. The Gallery also offers options governing what occurs when you copy a grade that holds shared nodes inside it.

### Converting Shared Nodes Back to Corrector Nodes

Now and then you have to halt a node's sharing. Say you want to copy a grade from another scene as the seed for a new one; odds are you do not want its shared nodes staying shared while you tailor that grade to the new scene. For that case, convert the Shared node back into a plain Corrector node, apply whatever tailoring the new scene calls for, and then promote that node into a fresh Shared node specific to the new scene. To convert a Shared node back into a Corrector node:

- Right-click any Shared node and pick Convert to Corrector from the contextual menu.

### Deleting Shared Nodes

When you have a Shared node in use across multiple clips and decide to sever the link binding them so each runs on its own, you can “delete” that particular Shared node. Doing so leaves the now-unlinked nodes sitting in every node tree where they appear yet wipes out their effect. The Shared node is also dropped from the Add Node submenu. To Delete a Shared node:

- Right-click any Shared node and pick a node to delete from the Delete Shared Node submenu.

### Using Adjustment Clips

Another way to put one grade onto multiple Timeline clips is with Adjustment clips laid over a number of other clips in the Timeline. Use them to drop one grade onto every clip in a scene, or to pile extra color tweaks or trims onto a stretch of clips through a second grade riding above the per-clip grades already in place.

An Adjustment clip (seen selected within the Mini Timeline) putting a cooler grade onto four further clips of a scene

Adjustment clips shine when you need to push adjustments onto a set of clips you expect to keep revising. Edit a grade inside an Adjustment clip and that edit lands automatically on every clip sitting below it in the Timeline. Grades coming from adjustment layers can also be switched off by disabling the layers, whether one by one or by disabling a whole track that contains adjustment layers. You edit Adjustment clips into the Timeline over on the Edit page, and they live in the Effects bin of the toolbox within the Effects Library. With an Adjustment clip stacked above one or more Timeline clips, every effect placed on the Adjustment clip carries down to all the clips beneath it. The kinds of effects Adjustment clips can apply are:

- ResolveFX and OpenFX plugins
- Inspector parameters, including Composite, Transform, Cropping, and Dynamic Zoom
- Fusion page effects
- Color page grading and sizing

Effects clips give you a fast, easily reworked means of laying one or more grades and effects across a band of clips. TIP: You can group several adjustment layers together so Group and Clip grades reach the adjustment layers, chaining multiple adjustment layers when you want the very same trim or stylistic move spread over multiple scenes scattered across noncontiguous parts of the Timeline.

### Using Groups

Among DaVinci Resolve's strongest tools for arranging grades across many clips is grouping. A group is a hand-built collection of clips bound by automatic linking, which lets you readily steer how grades ripple across the clip sets you mark out. With clips grouped, picking any one member surfaces a group “linked” badge at the top right of every group clip's thumbnail.

The green link icon indicates this clip is in a group Build as many groups inside a single project as you require. You may add or pull shots out of the current group, and the current group is set by the last shot you selected (should it belong to a group, that becomes the new current group).

With clips grouped, you have four Node Editor modes to pick from when grading the current clip. Your pick decides whether that grade ripples automatically to every other member of the group or stays confined to that single clip. By that route you can stack several node trees — some that ripple, one that does not — to arrive at each group clip's final look. As one example, you might group every clip shot from the same coverage angle in a scene. You might equally group every clip from a stretch of B-roll bound for the same treatment. Done this way, any time you change or otherwise update one group member through one of the rippled Node Editor modes, every clip in the group shifts together. This section covers building and managing groups, how to get the most from them, and the pitfalls to watch for so groups serve you best.

### Creating and Managing Groups

The steps below cover building, loading, editing, and removing groups. To build a new group: 1 Mark one or more clip thumbnails in the Timeline. Grab a contiguous stretch of clips by clicking one and Shift-clicking another, or assemble a noncontiguous set by Command-clicking individual thumbnails anywhere across the Timeline. 2 Right-click one of the marked thumbnails and pick Add Into New Group. 3 Enter a name in the Group Name dialog's field and click OK. The new group comes into being, and the clips you had marked now carry the “linked” group badge above their thumbnails. To bring up a different group, take one of these routes:

- Slide the playhead onto another clip that belongs to that group.
- Right-click any clip in any group and pick Group > “Name of group” > Load. That group now becomes the current one. The Add Into Current Group command will then drop a clip into the just-loaded group.

To drop one or more clips into an existing group: 1 Bring up the group you want to add clips to. 2 Mark one or more clip thumbnails in the Timeline. Grab a run of adjacent clips by clicking one then Shift-clicking another, or build a scattered set by Command-clicking individual thumbnails anywhere in the Timeline. 3 Right-click one of the marked thumbnails and pick Group > “Name of group” > Assign to Group. The marked clips now show the “linked” group badge above their thumbnails. To pull one or more clips out of an existing group: 1 Mark, in the Timeline, one or more clip thumbnails you want gone from a group. Grab an unbroken span of clips by clicking one and Shift-clicking another, or form a discontiguous set by Command-clicking individual thumbnails wherever they sit in the Timeline. 2 Right-click one of the marked thumbnails and pick Remove From Group.

To rename a group: 1 Right-click any clip in any group and pick Group > “Name of group” > Rename. 2 Enter a fresh name in the Group Name dialog's field and click OK. The group takes the new name. That name turns up as a new submenu under the Timeline contextual menu. To remove a group:

- Right-click a clip in the group you want gone and pick Group > “Name of group” > Delete.
- This wipes the group while holding onto the last grade applied within each clip.

DaVinci Resolve builds a default smart filter covering every clip in the current group. You will find it in the Clips drop-down beneath Grouped > Current Group.

### Using Group Modes to Control Which Grades Ripple and Which Don’t

After you build a group and then click any clip belonging to it, extra Node Editor modes open up that let you layer several tiers of grades onto that group's clips.

### Available options in the Node Editor modes drop-down

When a clip is not grouped, two dots atop the Node Editor let you flip between Clip and Timeline modes with one click. When you are on a clip that belongs to a group, four dots appear instead, opening quick access to the Pre-Clip and Post-Clip Group modes too.

The four dots up top in the Node Editor are where you pick the mode you want to work in

Any node tree you build in the Group Pre-Clip and Group Post-Clip modes ripples its changes automatically onto every member of a group. A node tree built in Clip mode stays tied to its own clip. A node tree built as the Timeline grade hits the whole Timeline in one stroke. Stacking node trees from these various modes makes it easy to fuse clip-specific changes with group-wide ones and speed up grading.
