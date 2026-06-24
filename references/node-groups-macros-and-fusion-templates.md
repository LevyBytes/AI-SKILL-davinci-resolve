# Node Groups Macros And Fusion Templates (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Node Groups, Macros, and Fusion Templates

What this chapter shows is how groups, macros, and templates work in Fusion, so that handling complex effects turns out tidier, faster, and less of a chore.

### Groups

As you tackle complex visual effects, node trees have a way of growing sprawling and hard to handle, so bundling tools together helps you keep all the nodes and connections in better order. A group is a container within your node tree able to hold several nodes, much the way a folder on your Desktop holds several files. No cap exists on how many nodes one group may contain, and you can even build subgroups inside a group.

### Creating Groups

Making a group amounts to little more than picking the nodes you wish to bundle and running the Group command. To create a group: 1 Highlight whichever nodes you intend to bundle. 2 Give one of the chosen nodes a right-click and pick Group off the contextual menu (Command-G).

A handful of nodes highlighted ahead of building a group (top), alongside the group that results (bottom). The chosen nodes fold down into a group, which appears as one single node within the Node Editor. Depending on how the nodes inside it connect, the Group node may carry inputs and outputs. Only for nodes already wired to nodes outside the group does the Group node surface inputs. An unconnected input inside the group shows no Input knot on the Group node.

### Deleting Groups

Removing a group works just like removing any other node in the Node Editor. Pick a group and hit Delete, Backspace, or Forward-Delete, and that group, along with every node held inside it, drops out of the node tree.

### Expanding and Collapsing Groups

In the node tree, a collapsed group appears as one single “stack” node. Should you wish to alter any node held inside the group, open the group with a double-click, or by picking the group node and hitting Command-E.

An open group window showing the minimize button. Opening a group brings up a floating window that shows the nodes inside it. That floating window is a Node Editor in its own right, one you can resize, zoom, and pan apart from the main Node Editor. Inside the group window you can pick and tweak whatever node you want, and even add, insert, and remove nodes while it stays open. Once you’re set to collapse the group once more, hit the minimize button up in the floating window’s top left corner, or reach for the keyboard shortcut (Cmd-E).

### Panning and Scaling within Open Group Windows

The same mouse buttons that pan and scale the main Node Editor also pan and scale an open group window. That said, while you work inside an expanded group and are at the same time altering the main node tree, you might wish to keep the expanded group from being panned or scaled on its own. Switching off the Position button over at the right of the group title bar pins the group nodes to the size of the nodes throughout the rest of the overall node tree. Switching this Position button on lets you scale group nodes apart from the rest of the node tree.

### Ungrouping Nodes

Should you conclude a given group is no longer needed, or you just find constant access to all its nodes at once more convenient, you can break apart or “ungroup” the group without losing the nodes inside it, doing away with the group while its contents stay put in the Node Editor. To ungroup nodes, proceed thus: 1 Give the group a right-click. 2 Off the contextual menu, pick Ungroup. Whatever nodes were inside the group return to the main node tree.

### Saving and Reusing Groups

Among the strongest points of groups is that any group, settings and all, can be stored for reuse later in other shots or projects. There are several ways to bring groups and their settings back. One good case for wanting to Save and Load a group is a studio staffing two or more compositing artists. The lead artist at your studio might assemble the master comp and build a group made specifically for keying greenscreen. That key group can then be handed off to another artist, who tightens the key, constructs the mattes, and tidies up the clips. The setting can then be exported and reloaded into the master comp. As newer versions land, these settings can be reloaded to refresh the master comp. Ways to store and reuse groups run as follows: To save a group: On a group, right-click and choose Settings > Save As off the contextual menu. To reuse a group: Pull it straight out of your computer’s file browser and into the Node Editor. Doing so spawns a fresh group node in the node tree carrying every node the group you saved held. To load the settings from a saved group to another group built on the same nodes: On a group within the Node Editor, right-click and choose Settings > Load off the contextual menu. Within Fusion Studio, groups can also be stored and reused by way of the Bins window: To save a group: Drag the group out of the Node Editor and into the opened Bin window. A dialog comes up so you can name the group setting file and pick where on disk it gets stored. The .setting file lands at the location you named and goes into the bins, ready for quick access down the road.

### Macros

Certain effects come together not from a single tool but from a whole chain of operations, at times across complex branches whose parameter controls interlink. Fusion hands you a wealth of individual effects nodes to work with, yet also lets users re-bundle them in assorted combinations as self‑contained “bundles,” which are either macros or groups. Such “bundles” bring a few benefits:

- They reduce visual clutter in your node tree.
- They keep user interaction on track by letting you limit which controls drawn from each node of

the macro are available to the user.

- They lift productivity by letting artists swiftly tap ready-made answers to everyday compositing

challenges and creative adjustments that have already been built and saved. Although macros and groups serve much the same function, they part ways a little in how each is made and shown to the user. You can regard a group as a fast means of tidying a composition by trimming the visual complexity of a node tree. A macro, by contrast, takes longer to build owing to how customizable it is, yet it’s simpler to reuse across other comps.

### Creating Macros

Even though macros let you bank complex functions for reuse in highly customized ways, building one is honestly fairly straightforward. To make a macro from nodes in the Node Editor: 1 Pick the nodes you intend to fold into the macro you’re building. Since the macro you’re building serves a particular purpose, the nodes you pick ought to be wired together so they yield a specific output out of a specific set of inputs. TIP: Should you wish to govern the sequence in which each node’s controls turn up in the macro you’re building, Command-click each node in the sequence you want it to appear. 2 Give one of the chosen nodes a right-click and pick Macro > Create Macro off the contextual menu. A Macro Editor window comes up, listing each node you picked, ordered by the sequence in which each node was picked.

The macro editor with a Blur node and Color Corrector node.

3 To begin, type a name for the macro into the field up at the top of the Macro Editor. Keep this name brief yet telling of what the macro is for. Spaces aren’t permitted, and you’d do well to steer clear of special characters. 4 After that, open the disclosure control to the left of every node whose controls you wish to expose to the user, and, for each node output, node input, and node control you intend to expose, tick its checkbox over on the right. Whatever controls you tick get exposed to users following the sequence they hold in this list, which shows why governing the sequence in which you pick nodes back in Step 1, ahead of editing your macro, pays off. On top of that, the inputs and outputs already wired in your node tree come pre-ticked, so if you’re happy with those serving as the inputs and outputs of the macro you’re building, that bit is handled for you. For every control checkbox you switch on, a row of fields to the left of that control’s line lets you set the default value of that control plus the minimum and maximum values it will allow to start. 5 Having settled on your controls, click Close. 6 Click Yes when a dialog prompts you to store the macro. 7 Up comes a Save Macro As dialog in which you can revise the Macro Name (if need be) and pick a location for your macro. To make a macro show up in the Fusion page Effects Library Tools > Macros category, store it in these locations: On macOS: `Macintosh HD/Users/username/Library/Application Support/Blackmagic Design/ DaVinci Resolve/Fusion/Macros/` On Windows: `C:\Users\username\AppData\Roaming\Blackmagic Design\DaVinci Resolve\ Support\Fusion\Macros` On Linux: `home/username/.local/share/DaVinciResolve/Fusion/Macros` To make a macro surface within the Fusion Studio Effects Library Tools > Macros category instead, store it at these spots: On macOS: `Macintosh HD/Users/username/Library/Application Support/Blackmagic Design/ Fusion/Macros/` On Windows: `C:\Users\username\AppData\Roaming\Blackmagic Design\Fusion\Macros` On Linux: `home/username/.fusion/BlackmagicDesign/Fusion/Macros` 8 Once you’re finished, click Save.

### Using Macros

A macro can be brought into a node tree by way of the Add Tool > Macros or Replace Tool > Macros submenus on the Node Editor contextual menu.

### Re-Editing Macros

To rework a macro that already exists, simply right-click anywhere inside the Node Editor and pick the macro you wish to edit off the Macro submenu of that same contextual menu. Up comes the Macro Editor, where you can apply your changes and store the outcome.

### Groups Can Be Accessed Like Macros

A group can likewise be loaded off the Insert Tool > Macros submenu provided you store a group’s setting file in the Macros folder somewhere on your file system. As an example, on macOS, the `Macintosh HD/Library/Application Support/Blackmagic Design/DaVinci Resolve/Fusion/ Macros/` directory.

### Other Macro Examples

A macro can serve as a custom LUT too. Simply copy the macro’s .setting file into the LUTs: folder, and the macro becomes pickable as a LUT within the viewers. Such LUT macros stretch well past a mere color tweak; you could build a macro handling YUV 4:2:2 resampling, or a resize, or a sharpening filter, or even plain watermarking.

### Creating Fusion Templates

Folding Fusion into DaVinci Resolve opened the door to making Fusion Titles, Transitions, Effects, and Generators templates meant for the Edit page. These templates can be authored on the Fusion page or within Fusion Studio, then copied across into DaVinci Resolve. At heart, Fusion Titles, Generators, and Transition templates are comps authored in Fusion yet editable, with custom controls, on the Edit page Timeline. This section walks you through the process.

### Getting Started with a Fusion Title Template

Step one in making a Fusion title template is assembling a Fusion composition out of Fusiongenerated objects put together to form just about any title or generator you can dream up. If you’re feeling really ambitious, animation can go in too. Here, 3D titles and 2D titles have been merged into a show opener.

Building a composition to turn into a title template.

### Saving a Title Macro

At bottom, macros are Fusion compositions converted into self-contained nodes. As a rule, such nodes act as building blocks within Fusion, letting you fold the compositing tricks you reach for constantly into nodes of your own. Even so, you can put this macro capability toward making title templates for the Edit page. With your composition assembled, pick every last node you want folded into that template apart from the MediaIn and MediaOut nodes in DaVinci Resolve, or, over in Fusion Studio, the Loader and Saver nodes. Picking out the nodes destined to become a title template. TIP: Should you wish to govern the sequence in which node controls show up afterward, Command-click each node you mean to fold into the macro, one after another, following the order you want controls from those nodes to appear. It’s one more step, yet it keeps matters tidier later on. With that selection made, give one of the chosen nodes a right-click and pick Macro > Create Macro off the contextual menu.

Up comes the Macro Editor window, packed to the gills with a tiered listing of every single parameter belonging to the composition you’ve just picked.

The Macro Editor filled out with the parameters drawn from all the nodes you picked. Daunting as this list may seem, collapsing the disclosure control of the topmost Text1 node lays bare what’s actually happening.

A simple list of all the nodes we’ve selected. Collapsing the top node’s parameters lays bare a plain list of all the nodes we’ve picked. The point of the Macro Editor is to let you decide which parameters get exposed as custom editable controls for that macro. Whatever controls you settle on turn up in the Inspector each time you pick that macro, or the node or clip the macro becomes.

So the only thing left now is to switch on the checkboxes of every parameter we’d care to customize. Here, our ticks will land on the Styled Text checkbox belonging to the Text3D node, then the Diffuse Color, Green, and Blue checkboxes on the Cloth node, plus the Z Rotation checkbox over on the SpotLight node — leaving just the template’s middle word open to edits, though we get to recolor it and tip its lighting too (which makes a “swing-on” effect attainable).

Ticking the checkboxes for whichever parameters we mean to adjust once this serves as a template. After switching on all the parameters we want in the eventual template, we hit the Close button, and a Save Macro As dialog comes up. To make the Title template show up in the Effects Library > Titles category of DaVinci Resolve, store the macro in these locations: On macOS: `Macintosh HD/Users/username/Library/Application Support/Blackmagic Design/ DaVinci Resolve/Fusion/Templates/Edit/Titles` On Windows: `C:\Users\username\AppData\Roaming\Blackmagic Design\DaVinci Resolve\ Support\Fusion\Templates\Edit\Titles` On Linux: `home/username/.local/share/DaVinciResolve/Fusion/Templates/Edit/Titles`

Picking the spot to store an Edit page title template within DaVinci Resolve.

### Using Your New Title Template

With your macro saved, you’ll have to quit DaVinci Resolve and launch it again. Opening the Edit page Effects Library, you should spot your new template within the Titles category, set to go in the Fusion Titles list.

Within the Effects Library, the Fusion Titles section is where custom titles turn up. Once this template is edited onto the Timeline and the Inspector is opened, the parameters we made editable become visible, and they let us tailor the template to suit our own ends.

Customizing the template we made.

### And that’s it!

### Getting Started with a Fusion Transition Template

In building a Fusion transition template, the smoothest route is to begin from an existing transition template and extend it. The Fusion Transitions category of the DaVinci Resolve Effects Library holds three transitions. Of these, the Cross Dissolve is the plainest, whereas the Slice Push stands as the most involved example.

The Fusion transition templates located in DaVinci Resolve’s Effects Library.

### Creating a Fusion Transition Template

At their core, the three Fusion Transitions sitting in the DaVinci Resolve Effects Library are Fusion compositions that were turned into macros. As a rule, macros act as building blocks within Fusion, letting you fold the compositing tricks you reach for constantly into nodes of your own. Even so, you can put this macro capability toward making transition templates for the DaVinci Resolve Edit page. With a Fusion Transition applied on the Edit page, a right-click on it lets you pick Open in Fusion Page.

Right-clicking over a Fusion Transition in the DaVinci Resolve Edit page.

Up comes the Fusion page, showing off the node tree behind the Fusion transition.

The Cross Dissolve node tree in Fusion. On the Edit page Timeline, the outgoing clip is stood in for by the MediaIn 1 node. The incoming clip is what the MediaIn 2 clip stands for. The Cross Dissolve effect can be tweaked or swapped out wholesale to craft a transition of your own using any of Fusion’s nodes.

The Fusion Cross Dissolve node tree swapped out for Transforms plus a Merge node. TIP: To change how long the Fusion transition runs from the Edit page Timeline, the Resolve Parameter Modifier has to be applied to whatever parameter is animated. Rather than keyframing the transition, you construct it through the Scale and Offset parameters of the Resolve parameter modifier.

### Updating a Fusion Transition

Having altered the transition in Fusion, you can opt to refresh the transition in the Timeline, or else make a fresh transition that you store into the Edit page Effects Library. To refresh the transition, simply head back to the Edit page. Whatever changes you apply on the Fusion page show through in the Edit page Timeline transition.

### Saving a New Fusion Transition

When, after altering the transition in Fusion, you need to store it to the Effects Library for reuse on other transitions or other projects, you must build a macro and store it in the Transitions folder. Begin by picking every node in the Node Editor you want folded into the transition template, the two MediaIn nodes and the MediaOut node included. TIP: Because the transition template has to carry the MediaIn and MediaOut nodes, the closing steps of saving a transition template must happen on DaVinci Resolve’s Fusion page and can’t happen in Fusion Studio.

With that selection made, give one of the chosen nodes a right-click and pick Macro > Create Macro off the contextual menu.

The Macro Editor displaying the parameters of all the nodes you selected. Up comes the Macro Editor window, laying out a hierarchical list of every parameter in the composition you’ve just picked. The node order follows the sequence in which they were picked in the Node Editor before the macro was made. The point of the Macro Editor is to let you decide which parameters get shown as custom controls in the Edit page Inspector once the transition is applied. With transitions, you may opt to show no controls at all in the Inspector, leaving only duration tweaks in the Timeline. Alternatively, you can settle on a pared-down set of parameters for customization by ticking the checkboxes beside any parameter name. After switching on every parameter you want in the eventual template, hit the Close button, and a Save Macro As dialog comes up. Here you can type the transition’s name, as it ought to read in the Edit page Effects Library. To make the transition template show up in the Effects Library > Fusion Transitions category of DaVinci Resolve, store the macro in these locations: On macOS: `Macintosh HD/Users/username/Library/Application Support/Blackmagic Design/ DaVinci Resolve/Fusion/Templates/Edit/Transitions` On Windows: `C:\Users\username\AppData\Roaming\Blackmagic Design\DaVinci Resolve\ Support\Fusion\Templates\Edit\Transitions` On Linux: `home/username/.local/share/DaVinciResolve/Fusion/Templates/Edit/Transitions`

### Using Your New Transition Template

With your macro saved, you’ll have to quit DaVinci Resolve and launch it again. Opening the Effects Library on the Edit page, the new transition template shows under the Video Transitions category, in the Fusion Transitions list.

A custom Fusion Transition stored within the Edit page Effects Library. Drop this transition onto a cut in the Timeline, open the Inspector, and whatever parameters you left editable show up, should there be any.

### Getting Started with a Fusion Generator Template

The Effects Library holds a single, simple Noise Gradient Fusion Generator you can take as a launching point for building generators of your own.

The Fusion Generator templates sitting inside the DaVinci Resolve Effects Library. To bring the Fusion Noise Gradient Generator up on the Fusion page, do this: 1 Over on the Edit page, pull the Fusion Noise Gradient Generator from the Effects Library onto the Timeline. 2 Right-click over the Noise Gradient Generator and pick Open in Fusion Page off the pop-up menu.

Up comes the Fusion page, laying out the node tree behind the Fusion Generator.

### Creating a Fusion Generator Template

Simple as it is to start from the Noise Gradient Generator template, you can just as readily begin by dropping a Fusion Composition Effect onto a Timeline on the Edit page. To set out making a Fusion Generator Template from an empty Fusion composition, go like this: 1 Over on the Edit page, pull the Fusion Composition Effect from the Effects Library onto the Timeline. 2 Right-click over the Composition Effect and pick Open in Fusion Page off the pop-up menu.

An empty Fusion page carrying one solitary MediaOut node opens, set for you to build a Fusion Generator. The Fusion Generator is a solid image produced from however many tools you combine to form a static or animated background. You may opt to blend gradient colors, masks, paint strokes, or particles in 2D or 3D to form the background generator you’re after.

The Fusion Generator node tree creating concentric circles.

### Saving a New Fusion Generator

Having built the generator you want in Fusion, you’ll need to store it to the Effects Library for reuse across other projects from the Edit page. Doing so means building a Macro and storing it in the Generator folder. As a rule, macros act as building blocks within Fusion, letting you fold the compositing tricks you reach for constantly into nodes of your own. Even so, you likewise put this macro capability toward making Generator templates for the DaVinci Resolve Edit page. Begin by picking every node in the Node Editor you want folded into the Generator template, the MediaOut node included. With that selection made, give one of the chosen nodes a right-click and pick Macro > Create Macro off the contextual menu.

The Macro Editor displaying the parameters of all the nodes you selected. Up comes the Macro Editor window, laying out a hierarchical list of every parameter in the composition you’ve just picked. The node order follows the sequence in which they were picked in the Node Editor before the macro was made. The point of the Macro Editor is to let you decide which parameters get shown as custom controls in the Edit page Inspector once the Generator is applied. You can settle on a pared-down set of parameters for customization by ticking the checkboxes beside any parameter name. After switching on every parameter you want in the eventual template, hit the Close button, and a Save Macro As dialog comes up. Here you can type the Transition’s name, as it ought to read in the Edit page Effects Library.

To make the Generator template show up in the Effects Library > Fusion Generators category of DaVinci Resolve, store the macro in these locations: On macOS: `Macintosh HD/Users/username/Library/Application Support/Blackmagic Design/ DaVinci Resolve/Fusion/Templates/Edit/Generators` On Windows: `C:\Users\username\AppData\Roaming\Blackmagic Design\DaVinci Resolve\ Support\Fusion\Templates\Edit\Generators` On Linux: `home/username/.local/share/DaVinciResolve/Fusion/Templates/Edit/Generators`

### Using Your New Generator Template

With your macro saved, you’ll have to quit DaVinci Resolve and launch it again. Opening the Effects Library on the Edit page, the new Generator template shows under the Generators category, in the Fusion Generators list.

A custom Fusion Generator stored within the Edit page Effects Library. Drop this Generator onto the Timeline, open the Inspector, and whatever parameters you left editable show up, should there be any.

### Creating a Fusion Effect Template
