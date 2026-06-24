# Flow Nodes, Flow Organizational Nodes, Fuses

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

## Overview

Covers: Flow Nodes; Flow Organizational Nodes; Fuses.

## Flow Nodes

### Flow Nodes

This chapter walks through the Sticky Note and Underlay capabilities that Fusion offers.

The short code shown beside each feature's name works in the Select Tool dialog while you hunt for tools, and within scripting references as well. Throughout this document, you can read node trees that display MediaIn nodes in DaVinci Resolve as equivalent to Loader nodes in Fusion Studio, except where a note says otherwise.

### Sticky Note [NTE]

### The Sticky Note

### Sticky Note Introduction

A Sticky Note isn't really a node. Rather, it offers a handy way to pin notes, comments, and history onto a particular region of a comp. Adjusting their dimensions and color lets them serve as either understated remarks or prominent warnings, whatever you need. Sticky Notes pair nicely with the Comments tab over in the Inspector.

### Usage

Dropping a Sticky Note into a node tree lets you leave an explanation for collaborators or a note to your future self. To make a Sticky Note, click an open spot in the Node Editor at the place you'd like it to show up. After that, head to the Effects Library and click the Sticky Note effect found under the Tools > Flow category, or press Shift-Spacebar and look up Sticky Note inside the Select Tool window. As with Groups, a fresh Sticky Note arrives compact and collapsed. A double-click opens it up. Once open, you can drag any edge or corner to resize it, or move it about by grabbing the name header. Clicking the icon at the top-left corner collapses the Sticky Note once more. Right-clicking the note brings up a contextual menu from which you can rename it, delete it, copy it, or recolor it. That same menu also lets you lock the note so it can't be changed. Editing the words inside a Sticky Note means first opening it with a double-click anywhere on it, then clicking just under its title bar. As long as the note stays unlocked, its text is yours to edit.

### Underlay [UND]

### The Underlay

### Underlay Introduction

Underlays give you a handy way to lay out regions of a composition visually. Much like Groups, Underlays can make a comp easier to read by carving it into labeled, purpose-driven blocks. Where Groups tidy a comp's appearance by folding intricate layers into single nodes, Underlays draw attention to areas instead of concealing them, and they place no limits on connections reaching in from outside.

### Usage

### Underlay node structure

Just like Sticky Notes, you bring an Underlay into a comp either by picking it out of the Flow category within the Effects Library or by looking it up in the Select Tool window. The Underlay lands in the Node Editor with its title bar centered over wherever you last clicked. You can resize Underlays by dragging any edge or corner, and doing so leaves the nodes untouched. Underlays can double as straightforward selection groups too. Clicking an Underlay's title activates it and grabs every tool sitting entirely inside it, so the whole bunch can be moved, duplicated, routed through, and the like. Renaming an Underlay starts with making sure none of the nodes inside it are selected. After that, Option-click the Underlay title to grab the Underlay on its own without grabbing the nodes it holds. With it selected, right-click the title and pick Rename. The very same right-click contextual menu lets you give an Underlay a color.

## Flow Organizational Nodes

### Flow Organizational Nodes

This chapter covers the Groups, Macro, and Pipe Router nodes, all built to help you keep compositions tidy and to render the node tree clearer to view and grasp.

Throughout this document, node trees that display MediaIn nodes in DaVinci Resolve may be read as equivalent to Loader nodes in Fusion Studio, except where a note states otherwise.

### Groups

### The Group node

### Groups Introduction

Groups serve to keep tangled node trees in order. Pick out however many nodes you want from the node tree, then group them so they collapse into one node icon in the Node Editor. Because Groups are nondestructive, you can reopen them whenever you like.

### Usage

- To group nodes, pick them out in the Node Editor, then right-click on any node in the selection and pick Group from the contextual menu.

### Selecting nodes to group

- To work on the separate nodes inside a group, right-click and pick Expand Group from the contextual menu. Every node held in the group then shows up in a floating node tree window. Opened groups float above whatever's already there, letting you edit the nodes they enclose.

### An opened node group

- To dissolve a group while holding onto its separate nodes, right-click the group and pick Ungroup.

### Macro

Strictly speaking, a Macro isn't a node. Rather, it's a cluster of nodes that behaves as though it were one node.

### Macro Introduction

With Macros you can merge several nodes together and surface a set of controls you get to define yourself. The idea behind them is to make crafting custom nodes quick and painless.

### Usage

To build a Macro, pick the nodes you want it to contain. Whatever sequence you select them in sets the sequence they'll show up in within the Macro Editor. Right-click any node in the selection and pick Macro > Create Macro from the contextual menu.

### Select the nodes to include in the macro

### Macro Editor

The Macro Editor is where you pick out and rename the controls that the finished macro tool surfaces. In the sample shown below, the tool carries the name Light_Wrap at the top. The Blur slider belonging to Matte Control 1 is switched on and given the new name Softness, which is how it'll read in the Inspector.

### The Macro Editor

Once the macro is arranged the way you want, click the Close button down in the dialog's lower-right corner. After that, the Save dialog offers Yes to store the macro, No to exit Macro Editor while discarding your edits, or Cancel to head back into the Macro Editor.

### The Macro Editor save dialog

Dropping the macro into your node tree is a matter of right-clicking anywhere on the node tree and picking Macro > [NameOfYourMacro] via the contextual menu. (How to store a macro as an Edit Page title template in DaVinci Resolve.) Within DaVinci Resolve, the only place macros surface is the Fusion page. That said, should the macro happen to be a title animation, you're able to stash it in the Titles Templates folder so it turns up over in the Edit page Effects Library. For a title macro to appear there in the Edit page Effects Library, drop the macro into this location — on macOS: `Users > UserName > Library > Application Support > Blackmagic Design > DaVinci Resolve > Fusion > Templates > Edit > Titles` and on Windows: `C Drive > Users > UserName > AppData > Roaming > Blackmagic Design > DaVinci Resolve > Support > Fusion > Templates > Edit > Titles`

### The Final Macro

Your finished macro appears and operates exactly like any other Fusion node. For a second example, you might grab one Channel Boolean, switch it to Add mode, and turn it into a macro that surfaces no controls whatsoever, which gives you something equivalent to an Add Mix node of the sort found in applications such as Nuke.

### Pipe Router

Pipe Routers are yet another organizing aid that helps you clean up how the node tree is laid out and how it looks.

### Router Introduction

Routers let you tidy up your comps by adding “elbows” to the node tree, which keeps connection lines from crossing over nodes and makes everything clearer to follow. They have no bearing whatsoever on render times.

### Usage

### A Pipe Router usage example

### Router

Adding a router onto a connection line takes an Option- or Alt-click directly on that line. From there you can drag the router around to lay out the connections however suits you. Routers carry no real controls of their own, yet they still come in handy for attaching comments to a comp.

### An example comment in a Router node

## Fuses

### Fuses

This chapter presents Fuses — scriptable plugins you can run inside Fusion.

### Fuses [Fus]

### A Fuse node

### Fuses Introduction

A Fuse is a plugin. What sets a Fuse apart from an Open FX plugin is that you build a Fuse from a Lua script. You can edit Fuses right inside Fusion or DaVinci Resolve, and your edits compile on the spot. Because they rely on a Lua script, even people who aren't programmers find it straightforward to prototype and build custom nodes. You can drop a new Fuse into a composition, edit it, and reload it without ever closing the composition you're in. Fuses also work as modifiers to drive parameters, curves, and text in a hurry. ViewShader Fuses are able to tap the GPU to run faster. All of this makes Fuses far handier than an Open FX plugin built on Fusion's OFX SDK. That flexibility, though, isn't free. A Fuse compiles on the spot, so it can run markedly slower than the same node produced with the Open FX SDK. To illustrate, a Fuse might build a mask out of the blown-out regions of an image, or set up starting particle positions from the XYZ position kept inside a text file. To obtain the SDK (Software Developer Kit) documentation, get in touch with Blackmagic Design.

### Installing Fuses

Fuses live in the Fusion:\Fuses path map. Out of the box, that folder sits at Users/ User_Name/Library Application Support/Blackmagic Design/Fusion (or DaVinci Resolve)/Fuses under macOS, or at C:\Users\User_Name\AppData\Roaming\Blackmagic Design\Fusion (or DaVinci Resolve)\ Fuses under Windows. A file has to carry the extension .fuse, otherwise Fusion passes over it.

### Working with Fuses in a Composition

You can set a Fuse up to show under whichever category you like in the Effects Library. After installation, you place one into a composition the same way you would any built-in or third-party plugin node. But because a Fuse is nothing more than a text document, you can edit it by clicking the Edit button that shows at the top of the Inspector while the Fuse node is selected. That action opens the Fuse in whatever default script editor you've named in the Global Preferences/Scripting panel. NOTE: Edits you make to one Fuse's script won't right away carry over to other copies of that same Fuse node already placed in a composition. To push the revised Fuse script onto every matching Fuse in the composition, either shut and reopen the composition or hit the Reload button inside each Fuse's Inspector. Opening a composition that holds a Fuse node loads whatever version of the Fuse script was most recently saved. The simplest way to be certain a composition runs the latest Fuse is to close it and open it again.
