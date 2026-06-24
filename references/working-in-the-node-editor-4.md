# Working In The Node Editor (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Any time node thumbnails are switched on, you get to decide whether each thumbnail shows a picture of how the image looks at that node, or whether it shows the icon belonging to that node instead. This choice applies to every node at the same time. To swap thumbnails out for icons: Right-click on any empty background area of the Node Editor and clear Show Thumbnails from the contextual menu.

### Sometimes Nodes Only Show Icons

The further you build out a composition with extra nodes, the more you'll spot that certain nodes never put an image in their thumbnail. For those, the node's default icon shows up rather than a picture. The bulk of nodes belonging to the Particle and 3D categories behave this way. Two that don't are the pRender node and the Render 3D node. Provided your menu options are set so Thumbnails appear, these two are able to show a rendered thumbnail. Beyond that, whether a node shows an image in its thumbnail tends to depend on circumstances. Certain Transform nodes can chain their outcomes together, handing off the real processing to a node further downstream in the node tree. When that happens, the upstream Transform nodes aren't doing the image processing themselves, so no thumbnail comes from them. There are also cases where the Loader isn't pulling in a clip, or the clip has been trimmed out of range within the Keyframes Editor; either keeps the node from processing the image, and so no rendered Thumbnail image results. On top of that, any node switched to Pass Through mode is disabled and won't show a rendered Thumbnail image.

### Finding Nodes

The fine-grained nature of today's visual effects often leaves you with compositions running into hundreds of nodes. With node trees that big, hunting by eye would mean scrolling around the Node Editor for ages. Thankfully, the Find dialog lets you track nodes down inside the Node Editor in a hurry.

Using the Find dialog, you can rapidly pin down nodes no matter where they sit within the Node Editor.

### Performing Simple Searches

Running a basic search by node name is straightforward. To track down a node within the Node Editor: 1 Hit Command-F, or right-click an empty spot in the Node Editor and pick Find from the contextual menu. 2 Once the Find dialog opens, proceed as follows:

- Type a search term into the Find field.
- Set your search options, for instance whether the entire phrase in the Find field must match, whether

case should be matched, whether a sequence number is used, or whether a regular expression is entered in the Find field.

- Decide what gets searched. The choices cover tool name, tool type name, or tool type ID.

3 To run the find, take one of these actions:

- Click Find Next to attempt selecting a downstream node that fits the criteria.
- Click Find Previous to attempt selecting an upstream node that fits the criteria.
- Click Find All to attempt selecting every node in the Node Editor that fits the criteria.

At that point the Find window shuts. Whenever a Find Next, Find Previous, or Find All operation succeeds, the matching node or nodes become selected. Otherwise, a dialog pops up telling you the string couldn't be located. TIP: Rounding up every node of a given type comes in handy when, say, you'd like to disable all Resize nodes. Find All selects all the nodes that match the search term, and you can switch them off temporarily by hitting the Bypass shortcut, Command-P.

### Using Regular Expressions

For searches that get more involved, switch on the Regular Expression checkbox; it lets you type in basic expressions to build more elaborate find operations. Among the handier regular expressions worth knowing is the use of Character Sets.

### Character Sets

Whatever characters you place inside a pair of brackets [ ] become the search target. Below are a few sample character set searches that function in Fusion.

[a-z] Finds: Each node that uses a lower-case letter [a-d] Finds: Each lower-case letter spanning a to d, locating nodes with a, b, c, or d [Tt] Finds: Each node carrying an upper case T or a lower case t

[aeiou] Finds: Each vowel [0-9] Finds: Each numeral [5-7] Finds: Each numeral spanning five through seven, locating nodes numbered with 5, 6, or 7

### Custom Node Settings

Whenever a node lands in the Node Editor, its parameters take on the default values for that kind of node. If you keep retuning a node's parameters to some favored starting point the instant it joins the node tree, you can supersede the default node settings with custom ones of your own. To store new default settings for a given kind of node: 1 Make a new node. 2 Open the Inspector and tailor that node's settings to the new defaults you'd like. 3 Right-click the node in the Node Editor, or right-click its control header in the Inspector, then pick Settings > Save Default from the contextual menu. TIP: Using the Version buttons along the top of the Inspector, you can also keep six separate settings for a node in the Node Editor.

For fuller detail, consult Chapter 70, “Editing Parameters in the Inspector,” within the DaVinci Resolve Reference Manual, or else Chapter 8 of the Fusion Reference Manual.

### Managing Saved Settings

Your custom node default settings get written to a folder on your hard drive determined by the Path Map > Defaults preference in the Fusion Settings. That location can be changed, which suits facilities where several compositing artists share one set of house defaults kept somewhere everyone can reach. Here are the default paths: On a macOS system, this falls by default at: /UserName/Library/Application Support/ Blackmagic Design/DaVinci Resolve/Fusion/Defaults. On a Windows system, it sits by default under: C:\Users<username>\AppData\Roaming\ Blackmagic Design\DaVinci Resolve\Fusion\Defaults. On a Linux system, look by default in: ~/.fusion/BlackmagicDesign/DaVinci Resolve/ Fusion/Defaults. Should you look inside this directory, each node's settings are stored under a name following the pattern INTERNALNAME_PUBLICNAME.settings, in which INTERNALNAME stands for the Fusion tool's internal name and PUBLICNAME stands for the Node name derived from that internal Fusion tool. To give an example, a Blur node's default setting would carry the name Blur_Blur.setting. Part of the reason for this naming scheme is to keep third-party plugin nodes from clobbering the defaults of built-in Fusion nodes that share the same name.

### Resetting Defaults

Even after you've defined new default settings for new nodes, you're always free to revert individual parameters back to the original default setting. Restoring the original default settings for new nodes you make is likewise simple. To return a single parameter to the original default settings: 1 Make a new node. 2 Open the Inspector and adjust a parameter to the new default value you want. 3 Right-click that parameter inside the Inspector and pick Set to Default from the contextual menu. To send every parameter of a node back to the original defaults, take one of these actions:

- Right-click the node and pick Settings > Reset Default.
- Right-click the node's control header in the Inspector and pick Settings > Reset Default.
- Remove the .setting file from the Defaults folder.

NOTE: Running the Settings > Reset Default command wipes out the default .setting file. Should you wish to keep a node's settings as alternate settings instead, reach for the Settings > Save As command.

### Saving and Loading Alternate Node Settings

After you alter a node's parameter values through the Inspector, those values can additionally be stored as an alternate setting for that node, ready to be reused down the road. To store alternate settings for a node: 1 Right-click a tool, then pick Settings > Save As from the contextual menu. 2 Once the Save File dialog opens, type a name for the Setting and write it to your hard drive. In contrast to saved defaults, the .settings files may live anywhere on the file system. There's no requirement for them to sit in the Default Settings folder. To bring a saved setting back into one or more nodes: 1 Right-click a node and pick Settings > Load from the contextual menu. 2 Through the Open File dialog, point to the settings you'd like to load into that node, then click Open. Those settings now take effect on that node.

### Adding Saved Settings from the File System

Settings saved in your File system can also spawn new nodes: just drag the .setting file out of an ordinary file browser and into the Node Editor. The moment you release it, that setting becomes a new node. TIP: Drop a setting straight onto a connection line and the new node gets inserted onto that connection.

### Node Modes Including Disable and Lock

When you right-click one or more nodes and bring up the contextual menu, the Modes submenu surfaces a set of commands, several of them with keyboard shortcuts attached, for governing control visibility and for disabling, locking, updating, and caching nodes.

- Show Controls: Determines whether the node exposes its parameters in the Inspector once selected and whether its onscreen controls turn up in viewers. On by default.
- Pass Through: (Command-P) Works just like the toggle switch in the Inspector that flips nodes off and on. A disabled node is skipped, with image data handed straight from the upstream node before it to the downstream node after it. On by default.
- Locked: (Command-L) Works just like the Inspector's lock button, which blocks a node from being edited in the Inspector. Off by default.
- Update: (Command-U) On by default. As long as this option stays on, every change you make to the node triggers a re-render. With Update switched off, you can still tweak the node's parameters, yet those tweaks won't process or refresh the image until Update is switched back on. While it's off, the node's last processed image stays put as a freeze frame. This proves handy, for instance, with a big or processor-heavy composition (say a particularly demanding particle system), where turning the option off for a while lets you rattle off several quick parameter changes across different nodes without waiting out a full node-tree re-render after each one. It's also useful when you want to glance at how animated downstream nodes behave while stopping upstream nodes that are too processor-heavy to play in real time from rendering more frames.
- Force Cache: With this on, the node's output for the current frame carries an extremely high cache priority, all but pinning it in memory. Off by default.

Flipping any of these node modes on or off puts a badge inside that node to signal its state.

### Node Editor Options

A right-click on a blank stretch of the Node Editor opens the contextual menu along with the Options submenu. Inside the Options submenu sit several choices for tailoring how the Node Editor looks and acts.

- Pipes Always Visible: Switching this on makes a connection pass over the top of a node rather than under it, which can make the connection's route easier to trace.
- Show Hidden Pipes: With this on, the Inspector's Hide Incoming Connections option on every node is overridden so that all connections show up in the Node Editor.
- Aspect Correct Tile Pictures: Aspect Correct Tile Pictures makes the thumbnail display render with aspect correction; it's slower but truer to the eye. This option is on by default.
- Full Tile Render Indicators: Turn this on and the thumbnail flashes green during rendering, which helps you spot which node is processing within a big, intricate node tree.
- Show Grid: This option lets you switch the Node Editor's background grid on or off.
- Show Instance Links: With this on, the Node Editor renders a green connection running between an

instanced node and its parent.

- Auto Remove Routers: Whenever routers get disconnected from a tool, they're deleted on their own

out of the Node Editor. This option ships on by default so you don't have to clear out orphaned routers yourself.

- Show Navigator: Switch this on to show a compact overview window of the whole node tree up in the Node Editor's top-right corner. The Navigator section later in this chapter covers it more fully.
- Auto Navigator: The Navigator surfaces only when at least one node lies beyond the visible portion of the Node Editor. Refer to this chapter's Navigator section for further detail.
- Build Flow Vertically/Horizontally: A node tree can grow either horizontally from left to right or vertically from top to bottom. Turning on one of these options sets whether fresh nodes attach below the current node or to the right of the current tool.
- Orthogonal/Direct Pipes: This pair of options lets you set how the links joining nodes get rendered — either as Direct (straight) lines or as Orthogonal (bent) lines.

### Node Tooltips and the Status Bar

Even with a straightforward node tree, some key fact about the nodes in your comp slips your mind easily. To jog your memory about what each one does, hover the pointer over any node in the Node Editor and the Status bar along the bottom of the Node Editor will show that node's name, frame size, pixel aspect, resolution, and color depth.

The Status bar located beneath the Node Editor. Wait a couple more moments and a richer rendition of that same information shows up inside a floating tooltip in the Inspector. That tooltip hands you extra detail concerning the Domain (Image and DoD) and the data range the clip uses.

The floating tooltip showing node information that appears within the Node Editor.
