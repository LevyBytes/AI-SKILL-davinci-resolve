# Layer Nodes

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Layer Nodes

Here we look at how multilayer images are worked with and altered inside your compositions. Each node name carries an abbreviation alongside it, and those short codes are handy in the Select Tool dialog when you hunt for a tool, as well as throughout scripting references.

### Layer Muxer [LMx]

### The Layer Muxer node

### Layer Muxer Node Introduction

With this tool you can merge the layers belonging to one source into those of a different source. It exposes a pair of inputs, and once two multilayer sources feed into them, the layers coming from one are folded together with the layers from the other.

### Inputs

Two inputs feed the Layer Muxer tool. Image 1: Wire this orange input to a node carrying the multilayer data you intend to merge. Image 2: Wire this green input to a node carrying the multilayer data you intend to merge.

### Basic Node Setup

Fed by two nodes that each hold multilayer data, the Layer Muxer node blends them through several possible methods, governed by your choices about which layers to retain and which to skip.

Layer Muxer combines two multi layer images.

### Inspector

### Layer Muxer controls

### Controls Tab

Parameters for picking which layers get used live on the Controls tab.

- Layer: Choose layers out of the clip wired to the Image 2 input so they merge with the clip wired to Image 1. Using the pulldown control, you state which layer(s) should be folded in. Whenever you pick anything besides All Layers, a tiny layer icon shows up on the Layer Muxer node as a reminder that only a subset of layers is making it through. Default Layer: Should the Input 2 multilayer media file carry a default layer, that layer gets merged. All Layers: Merges every layer of the Input 2 multilayer image as a group. Custom: Brings up a checklist covering all the layers in Input 2 so you can toggle the individual layers on or off.
- Conflicts: This control lets you flip between Image 1 or Image 2, the pair of inputs on the tool; whichever Image you pick becomes the tool’s Default/[Main] layer on output.

### Common Controls

Settings Tab The Inspector’s Settings tab also recurs across the rest of the Layer nodes. Full coverage of these shared controls appears later, in the “The Common Controls” section that closes out this chapter.

### Layer Regex [LRx]

### The Layer Regex node

### Layer Regex Node Introduction

By using elaborate expressions, this tool screens the layers of multilayer files according to how those layers are named. After you set up a filter, any layers that satisfy the "expression" may be renamed, retained, or stripped away.

### Inputs

A pair of inputs feed the Layer Regex tool. Image 1: Hook this orange input up to a node holding the multilayer data you mean to filter. Image 2: Hook this green input up to a node holding the multilayer data you mean to filter.

### Basic Node Setup

Wired to two nodes that each carry multilayer data, the Layer Regex node enables you to sift through them with Regex according to the names of the layers.

Layer Regex filters layers from two multi layer images.

### Inspector

### Layer Regex controls

### Controls Tab

The Controls tab holds the parameters you use to pick which layers come into play.

- Expression: The filter responsible for matching or locating characters.
- Mode: Governs the manner in which the expression gets applied. Transform: The operation of renaming or replacing characters. Keep: Retains whichever layers the Expression rule names. Remove: Strips out whichever layers the Expression rule names.
- Name Template: The rule tied to the “Expression," letting you swap characters or give layers new names.
- Unmatched: Sets how layers that fall outside the expression are handled. Keep: Layers that don't satisfy the Expression stay put; every layer is kept. Remove: Layers that don't satisfy the Expression are dropped. That leaves only the layers the expression actually touches.
- Tester: A lightweight utility that shows what your expression produces while you tweak the parameters.
- Conflicts: This control flips between Image 1 or Image 2, the two inputs on the tool; whichever Image you choose is sent out as the tool’s Default/[Main] layer.

### Examples

Add a prefix to existing layer names Expression: (.\*) Name Template: Right.$1 Doing this prepends Right. onto every one of the layer names, so you end up with Right.Layer1 , Right.Layer2 NOTE: For a suffix instead, flip the order within the Name Template, $1.Right. That yields Layer1.Right , Layer2.Right

Locate certain characters or words within the current layer names, then prepend a prefix Expression: (Right._) Name Template Stereo-$1 Here the operation finds whichever layers hold the word Right, then tacks the word Stereo- onto the front of each of those layer names, producing Stereo-Right.Layer1 Swapping text out Expression: right(._) Name Template: Left$1 With this, layer names that include right get found and that layer name is exchanged for Left. As a result, layers labeled right.1 , right.2 , right.3 become renamed to Left.1 , Left.2 , Left.3 . Bear in mind that with this approach, any layer name carrying the letters right (for instance, copyright) gets caught by the expression and is renamed too. If you want to pin down a specific run of characters, reach for the expression ^right(.\*) NOTE: The ^ stands for matching the very start of the text. That makes it screen right yet leave copyright alone, since copyright opens with a copy.

Match one word or the other, then strip them out (or retain them) Expression: (copy|right) Mode: Remove (copy|right) picks out copy and right , and with the mode at Remove, any layers holding copy or right get stripped from the layer list. An expression like this comes in handy for catching variants of a word, such as (copy|Copy|COPY) NOTE: Switching the mode to Keep instead preserves the layers that satisfy the Expression. Taking the example above, if the Mode reads Keep, the layers holding copy or right are the ones left behind while everything else is removed.

Find characters, ignoring case Expression: (?i)(right) This grabs every character in the word right, regardless of upper case. In practice that means any capitalized form of the word right: Right, RIGHT or riGth gets grabbed. RegEx Cheat Sheet To read more about working with RegEx https://www.debuggex.com/cheatsheet/regex/pcre Common Controls Settings Tab The Inspector’s Settings tab likewise shows up on the other Layer nodes. A thorough rundown of these shared controls sits at the chapter’s end within the “The Common Controls” section.

### Layer Remover [LRm]

### The Layer Remover node

### Layer Remover Node Introduction

Using this tool, you get an easy means of disabling or stripping layers out of a source that's connected to it.

### Inputs

A single input feeds the Layer Remover tool. Image 1: Connect this orange input to a node holding the multilayer data from which you intend to strip a layer.

### Basic Node Setup

Fed by a node that carries Multilayer data, the Layer Remover node lets you pull out particular layers ahead of handing the image downstream.

Layer Remover lets you disable specific layers of a multilayer file.

### Inspector

### Layer Remover controls

### Controls Tab

On the Controls tab you'll find a plain checklist covering every layer in the multilayer clip. Ticking a box disables or removes the corresponding layer(s) from the layer list.

### Common Controls

Settings Tab Like the others, the Inspector's Settings tab is shared with the rest of the Layer nodes. You'll find these common controls explained thoroughly at the close of this chapter under the “The Common Controls” section.

### Swizzler [Swz]

### The Swizzler node

### Swizzler Node Introduction

With this tool you can fold one or more image layers and/or channels into a custom-built layer or set of layers. Much like Channel Booleans, Swizzler is able to take channels from a source and route them into a destination channel; the key distinction, though, is that Swizzler works with layers, whether it draws on layers as a source or spins up new ones. Put plainly, the tool can manufacture new layers, drive source layers or channels into a layer, or pull channels out of a source.

### Inputs

The Swizzler tool takes several inputs. Input 1: Wire this orange input to a node holding the image data you'd like folded into a new layer. Input X: The white inputs get wired to further nodes whose image data you'd like folded into a new layer.

### Basic Node Setup

Fed by several nodes that each carry image data, the Swizzler node merges them to form new layers.

### Inspector

Swizzler combines multiple images into new layers.

### Swizzler controls

### Controls Tab

The Controls tab carries the parameters used to pick which layers are applied.

- Layer List: Through the layer list you can browse and pick custom layers. The button beneath it lets you append a fresh layer to the list, bringing in a new custom layer. For whichever layer you've highlighted in this list, the

options underneath let you decide which channels belong in the layer. On top of that, you're able to rename layers right inside this list. Add Layer: Generates a new layer and tacks it onto the layer list. Keep Main Input Layers: Ticking this box holds onto the layers already present in the source clip wired to Input1. With it switched on, the Input1 layers carry through to the Swizzler output, leaving you free to stack further layers atop an existing multilayer source.

- Channels: With this control you decide which channels get added to whichever layer is selected in the layer list. All Channels: Moves every channel into the selected layer. Color/Aux: Surfaces extra "Color" and "Aux" options that split RGBA apart from AUX channels. That split lets you name a source for the RGBA and a separate source for the AUX channels, so in the end RGBA comes from one input while AUX comes from another. Two further options, “RGB/A“ and “R/G/B/A,” hand you even finer control over channels and widen the source choices for individual channels.
- Source: Pick an input from this drop-down to feed layers or channels into your chosen layer. The chosen layer here is whatever you've highlighted in the layer list above.
- Source Layer: With a multi-layer file wired to one of the inputs, this control lets you target a particular layer. Every layer offered by the Source Input control is shown.
- Source Channels (Color/Aux mode): Pick which channels of the chosen layer should feed the Aux channel. Should the chosen layer lack Aux channels and have been rendered as RGB only, fall back instead on the color values — that is, RG for UV Texture or RGB for XYZ Normal.

### Examples

### Assigning Aux channels

For the example below, several RGB sources are on hand. Every one of them is a pre-rendered pass that we'd like to route to an Aux channel.

### Connecting multiple RGB sources to the Swizzler

Every RGB pass gets wired into its own fresh input on the Swizzler.

### Creating a new layer in the Swizzler

A fresh layer has been appended to the layer list; since it's the only layer present, it takes on the role of the new ‘default layer’

Assigning sources in the channel controls for the new layer

Within the channel controls for the new layer, set the right source for each of the Aux channels.

### Previewing the new channels in the viewer

After every one of the Aux channels has had an input assigned to it, you can preview the channels in the viewer. Creating a multilayer clip For this example, several RGB sources are available. Each one is a pre-rendered pass that we'd like to route to a new layer, building a multilayer clip in the process.

### Connecting multiple RGB sources to the Swizzler

Each RGB pass feeds into a separate new input on the Swizzler.

### Creating new layers in the Swizzler

Inside the layer list, append a new layer for each pass and assign it a custom name. Highlight a layer in the layer list, then in the controls set the appropriate source input for that layer. As an illustration, the UV pass has been wired to Input 4; by selecting the custom layer named “UV-Texture” and picking Input 4 from the Input list, all of the channels from Input 4 are driven into the “UV-Texture” layer.

### Selecting the new layers in the viewer

After each of the inputs has had a custom layer assigned to it, you can preview them in the viewer and put them to work in the comp.

### Common Controls

Settings Tab As with the other nodes, the Inspector's Settings tab reappears throughout the Layer nodes. These shared controls get a detailed treatment near the chapter's end in the “The Common Controls” section.

### The Common Controls

### Settings Tab

### The Settings tab

You'll come across the Common Settings tab on the majority of tools in Fusion. The controls below are settings tied specifically to Deep Image nodes. Hide Incoming Connections Turning on this checkbox lets you conceal the connection lines arriving from upstream nodes, which keeps a node tree tidier and more legible. With it active, the Inspector shows an empty field for each of a node's inputs. If you drag a connected node out of the node tree and into that field, the incoming connection line is hidden for as long as the node stays unselected in the node tree. The moment the node becomes selected in the node tree, the line shows up again.

Comments Tab Just one text control sits on the Comments tab, and you use it to attach comments and notes to the tool. As soon as a note is attached to a tool, a small red dot icon shows up beside the setting's tab icon and a text bubble surfaces on the node. To read the note within the Node Editor, rest the mouse pointer over the node briefly. Should you need it, the material on the Comments tab can be animated across time. Scripting Tabs Every tool in Fusion carries the Scripting tab. Within it are several edit boxes where you can enter scripts that run while the tool renders. For fuller detail on what this tab offers, refer to the scripting documentation.
