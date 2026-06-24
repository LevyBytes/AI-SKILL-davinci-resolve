# Rendering Using Saver Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Press the Add Comp button, then browse to where the comp lives on your local disk.
- Within the queue list, right-click and pick Add Comp from the drop-down menu; afterward, browse to the comp on your local disk.
- From an OS window, drag a comp file directly onto the Render Manager’s queue list.

Pressing the Add Comp button inside the Render Manager places a comp into the queue so it can be batch rendered across the network.

### Removing a Composition from the Queue

To take a composition out of the queue, highlight it in the queue list and tap the Backspace/Delete key; alternatively, right-click the comp within the queue list and pick Remove Composition from the drop-down menu.

### Saving and Reloading Queue Lists

Preserving a queue list so you can revisit it later is often handy. Your active queue list lives in the Documents > Blackmagic Design > Fusion > Queue folder. If you want to store the active queue under a different name, pick File > Save Queue As from the Render Manager menu bar. Bringing back a stored queue is done by choosing File > Load Queue and browsing to where it was kept.

### Reordering the Queue Lists

While a job is underway, which composition needs to finish first can shift. When deadlines move around, a composition sitting lower in the queue might have to be rendered ahead of others. Relocating comps within the queue is as simple as dragging them around the queue list. Should a composition whose status reads Done be dragged further down, it won’t render again. Forcing a comp to render once more is done by right-clicking it in the queue and selecting Clear Completed frames from the drop-down menu.

### Working with Node Groups

You can organize Render nodes into Groups, which then come into play whenever you submit compositions. Picture, for instance, a setup with five Render nodes. Every one of those Render nodes belongs to the group named All. Because two of them have extra memory and quicker processors, you spin up a fresh group titled Hi-Performance. Any new Render nodes join All on their own, though you’re free to place them in additional groups too. To assign a Render node to a Group: 1 Launch the Render Manager, then highlight whichever Render nodes you’re placing in a group. 2 Pick Render Node > Assign Group, or right-click the chosen Render nodes and select Assign Group via the drop-down menu. 3 Within the Choose Group dialog, type a name for that group. 4 Should you want Render nodes in several groups, divide each group’s name with a comma (e.g., All, Local, or Hi-Performance). Priority follows the sequence in which the groups are listed. See “Using Multiple Groups” below. Whenever a render goes out to the network, it lands in the All group by default. You may, though, opt to direct it toward other groups shown in the list. Routing a comp into a group by way of the Render Manager goes like this: 1 Bring up the Render Manager. 2 Send in the comp. 3 Press the Pause Render button. 4 Right-click the comp within the queue list, then choose Assign Group. 5 Inside the Assign Group dialog, pick an existing group for rendering the comp and press OK. 6 Press the Resume Render button.

Sending a comp into a group by way of the Render Settings dialog works as follows: 1 Press the Render button over in the transport controls area. 2 Within the Render Settings dialog, tick the Use Network checkbox. 3 From the Available groups list, pick an existing group. 4 Press the Start Render button. Returning to the earlier example, the All group holds five Render nodes, and two of them additionally belong to the Hi-Performance group. Dispatch a render to the HiPerformance group and just those two networked computers do the work. Should a composition afterward go to the All group, the other three machines kick off rendering that new composition. As soon as the pair of Render nodes in the Hi_Performance group finish that first task, they pitch in on the render already running for the All group. Using groups is entirely optional. That said, they can streamline and add efficiency to the administration of sizable networks of Render nodes. Using Multiple Node Groups One Render node may belong to several groups at once. Likewise, a single composition can be sent to more than one group. Routing a composition to several groups causes it to render on every Render node within the chosen groups. Where a Render node sits in multiple groups, the sequence of those groups matters, since that sequence sets the priority that Render node observes. As an example, when a Render node’s groups are ordered All, Hi-Performance, then renders sent to the All group win priority. Anything already rendering that came from the Hi-Performance group gets superseded. Flip the order to Hi-Performance, All and the priority swaps the other way.

### Viewing the Render Log

You’ll find the Render Log shown across the bottom portion of the Render Manager window, though it can equally appear in the console window. What the log records is the activity of the Render Manager: which frame went to which Render node, which Render nodes pulled in the queued compositions, and per-render statistics once each finishes. To view the Render Log in the console:

- Open the Render Manager and choose Misc > Show Render Log.

The Render Log offers two settings: a Verbose mode and a Brief mode. Under Verbose mode every Render Manager event is recorded, whereas Brief mode notes only the frame assignments per Render node along with their completion times. To disable Verbose mode:

- Choose Misc > Verbose Logging from the Render Manager’s menu bar.

### Using Third-Party Render Managers with Fusion Studio

Network rendering can be driven by third-party render manager software if you prefer. Doing so lets the many programs competing for your machine’s resources share them efficiently. Products in this category include Uberware LLC’s Smedge, Seriss’s Rush, plus GetRender’s Deadline. As a rule, these render managers rely on a command line renderer. Out of the box, Fusion’s Render nodes run as a service tied to the Fusion internal Render Manager. You can, however, launch the Render nodes from the command line so third-party render managers can drive them. Bear in mind that adopting a third-party render manager rules out certain Fusion network rendering capabilities, like generating network rendered Flipbook Previews and disk caches.

### Command Line Rendering

When a studio relies on third-party render farm managers such as Deadline, Smedge, or Rush, the Fusion Render node accepts invocation from the command line together with arguments and file paths. The Windows sample below invokes a Render node to open a composition named exampleV001 and produce 10 frames: //pathtoRN/FusionRenderNode.exe //pathtoProject/exampleV001.comp -render -start 101 -end 110 -quit That command launches, renders the span from 101 through 110, then exits. Further command line options appear in the table that follows.

Command "Fusion Server -i" "Fusion Server -S" (capital S) <filename.comp> -render -frames <frameset> -start <frame> -end <frame> -step <step> -quit -join <host> -listen

Description Sets up the license server as a service or daemon and starts it at boot ahead of any user login. Keeps the Fusion Server alive continuously in the background until it is force-quit. The comp name together with its full path, for example /storage/project/episode/shot/filename.comp. Instructs the Render Node to perform a render. Hands over a set of frame ranges for rendering—e.g., 101..110,120,121,130..150. Defines the render’s first frame. Defines the render’s final frame. Defaulting to 1, step skips frames during rendering. As an example, 2 renders every other frame Makes the Render Node exit once the render finishes. Directs the node to reach a manager at <hostname,IP> and (re)join whatever renders are in progress. Keeps the node alive, awaiting requests arriving from a manager.

Command -log <filename> -cleanlog -verbose -quiet -version -pri high|above|normal|below|idle -args <arg1> [, <arg2> ...]

Description Has the Render Node write render details out to a log file. The text is appended onto whatever the log file already holds. Wipes the current contents of a log file. Writes fuller detail into the log file. Hides pop-ups and interface buttons so nothing requires interaction. Reports the Render Node version number. Assigns the node’s process priority among high, above, normal, below, or idle. Lets you stash custom values retrievable through the script function GetArgs(), which hands back a table of { <arg1>, <arg2>, ... }

TIP: Running a headless Linux command line interface depends on having an X11 virtual frame buffer in place.

### Preparing Compositions for Network Rendering

How you assemble a composition inside Fusion Studio can either smooth or obstruct network rendering. The footage you load, the location of installed plugins, and the assortment of operating systems across your networked machines each influence how cleanly the network render proceeds. Before network rendering can function, your environment has to satisfy a handful of must-have conditions:

- The License dongle, the Render Master, and every Render node have to share one local network (subnet).
- Fusion Server must be running as a background service on the same

computer where the dongle is installed.

- Every piece of source media belonging to the comp ought to sit on a network volume.
- That network volume has to be mounted on every Render node.
- Loaders need to reference the media residing on the mounted volumes.
- Savers have to output to a drive mounted on every Render node.
- Save the Fusion comp onto a volume that is mounted across every Render node.
- Both Render Nodes and Render Masters require read plus write permission for any volume named as a

source media location or render destination.

- Confirm that every font the comp’s Text+ and 3D text nodes draw on is present across all the

### Render nodes

- Verify that each Render node carries any third-party OFX plugins the comp happens to use.

A few of these points are expanded on below.

### Using Relative Paths

The paths that load a composition along with its media, and that write out the composition’s rendered output, sit at the heart of how network rendering operates. Every machine taking part in network rendering has to reach the media location each Loader in the comp points to. Savers need configuring so they write into folders visible to all Render nodes and where all Render nodes hold write permission. The composition itself, too, has to live in a folder every Render node can reach, and you should add it to the queue list via a path that all Render nodes can see. Suppose, for instance, you open a composition sitting at c:\compositions\test1.comp within Fusion Studio and drop that composition into the network rendering queue; the Render Manager then signals each Render node to load and render it. The catch is that every machine probably has its own c:\drive lacking the comp you built. More often than not, the Render nodes can’t load the composition, so it fails. Path Maps, found in Fusion Preferences, are virtual paths that swap out portions of file paths. They let the absolute paths Loader and Saver nodes use become relative ones. Fusion ships with several Path Maps, yet you’re also free to define your own. The path you’ll lean on most is the Comp:\ path. Comp:\ stands in for the folder housing the saved composition. Consequently, putting Comp:\ in a Loader renders the media file’s path relative to wherever the comp file was saved. Provided all your source media lives within the same folder as your comp file, or a subfolder of it, Fusion finds the media no matter what the physical hard drive is called. What follows is a sample file structure that lets you work with relative file references. The composition resides at this file path: Volumes\Project\Shot0810\Fusion\Shot0810.comp And your source media lives here: Volumes\Project\Shot0810\Fusion\Greenscreen\0810Green_0000.exr The screenshot below illustrates this entire directory layout:

Relative paths can be derived from where the saved comp file sits. Here, applying the Comp:\ path anchors your media location to your comp file’s spot. So the relative path entered in the Loader node becomes: Comp:\Greenscreen\0810Green_0000.exr

Swapping the start of the Loader’s path for Comp:\ yields a path relative to the comp file’s location.

When your source media’s real file path sits in a subfolder alongside the comp file’s folder: Volumes\Project\Shot0810\Footage\Greenscreen\0810Green_0000.exr the Loader node’s relative path becomes: Comp:\..\Footage\Greenscreen\0810Green_0000.exr The pair of dots .. tells the path to climb up a single folder.

TIP: Certain Path Maps don’t configure themselves on a Fusion Render Node. For example, if your comp uses macros, you’ll have to add an entry for macros by hand.

### Using Mapped Drives

Setting the comp and media to relative paths only addresses part of the issue. Every machine taking part in the render must reach the drive holding the comp and source media. Mapping a drive grants lasting access to a folder living on another computer or a network storage device. Windows hands that folder a fresh drive letter, after which you use it exactly like any other drive attached to your computer. A mapped drive ties one alphabet letter to a shared network resource. The drive letters of your shared drives must match across all Render nodes. For instance, should your media sit on drive Z, the network drive has to show up as letter Z on each Render node. Under macOS, mapping a network drive is done through Connect to Server on the Go menu. Typing the drive’s smb:// path mounts it onto the computer. Via Accounts > LogIn Items, you can additionally arrange for the network drive to mount itself automatically following a reboot.

### Installing All Fonts on Render Nodes

Whatever fonts the composition’s Text tools rely on have to be reachable by every node taking part in the render. Otherwise the render breaks down on any Render node lacking that font.

### Installing Third-Party Plugins on Render Nodes

Every third-party plugin and tool a composition draws on has to be present in the plugins directory of each Render node. Any Render node that tries to render a composition relying on an uninstalled plugin will not render. Each Render node needs its licensed plugins in place.

### Other Uses of Network Rendering

Even though your main reason for configuring network rendering is likely to speed up the delivery of final renders, Fusion can put the network to work in other ways too. The Render nodes across your network can likewise hasten the building of Flipbook Previews and disk caching.

### Flipbook Previews

Fusion Studio can enlist Render nodes to speed up generating Flipbook Previews, delivering previews at blistering pace. When previews aren’t network rendered, their frames render straight into memory. Tick the Use Network checkbox plus the Render nodes so the preview frames render into the folder defined at Preferences Global > Path > Preview Renders. Every Render node joining the network render should be able to reach this folder. Its default value is Temp\, a virtual path aimed at the system’s default temp folder. You’ll have to alter this before network rendered previews can work. After the preview render wraps up, the frames each Render node produces are spooled into memory on the local workstation. The moment a frame lands in memory, it’s erased from disk.

### Disk Cache

When you right-click a node within the Node Editor and select Cache to Disk, a dialog appears for building the disk cache. Should you have ticked the Use Network checkbox and then press the Pre-Render button to send the disk cache, the networked Render nodes pitch in to speed up building that disk cache.

Beyond final renders, Render nodes serve for disk caching too.

### When Renders Fail

Render queues failing now and then is simply unavoidable. Common triggers include a flawed composition, a power outage, or a machine that gets unplugged from the network by accident. When nobody’s around to watch the render, the danger of a whole queue stalling idle for hours can turn into a real headache. Fusion Studio bundles in several safeguards meant to shield the queue and keep the render going through even the harshest circumstances.

### Automatic Rejoining of the Queue

Should a Render node drop off the Render Master’s radar for whatever reason, the frames it was handling get redistributed to the other Render nodes on the list. Once that Render node is back in service, it tells the Render Master it’s ready again, and fresh frames flow to it.

That’s precisely why configuring the Render Master within the Render nodes’ network preferences matters. Leave the master unset and a Render node has no idea which master to reach out to once it’s available again. Inside the Fusion Render Node Preferences, open the Tweaks panel. The Last Render Node Restart Timeout field lets you specify how many seconds Fusion holds on after the final Render node drops offline before it abandons the queue and pauses for hands-on intervention.

### Relaunching Render Nodes with Fusion Server

Fusion Server is a compact helper that ships alongside Fusion Studio and the Render node. The application is Fusion Server, a lightweight tool bundled with both Fusion Studio and the Render node. The application is brought up quietly by every Fusion Render node at startup. What Fusion Server does is keep an eye on the Render node to confirm it stays alive throughout a render. Its appetite for CPU cycles and RAM is tiny. Should the watched Render node vanish from the system’s process list without a clean shutdown signal — which can occur following a crash — Fusion Server fires the Render node back up so it can return to the render. Fusion Server picks up only the cases where a Render node has terminated abnormally. Where the Render node is still listed in the processes yet has gone unresponsive for some cause, Fusion Server has no way to spot the trouble. Stalled processes of that kind get caught and dealt with through frame timeouts, covered below.

### Frame Timeouts

Frame timeouts act as a safety net that halts a Render node’s render whenever a frame runs past the set duration (which defaults to 60 minutes, or one hour). This timeout guarantees an overnight render presses on if some composition stalls or starts swapping heavily and can’t finish the frame it was given. You set the timeout on a per-composition basis within the queue. To shift a composition’s timeout away from the 60-minute default, right-click that composition in the Render Manager’s queue list and pick Set Frame Timeout from the contextual menu.

Right-click a comp inside the Render Manager to define a timeout value. To adjust the frame timeout value, select Set Frame Time Out from the Render Manager’s Misc menu and type the number of seconds you’d like for the Time Out.

### Heartbeats

At steady intervals the Render Master pings each node with a heartbeat signal and waits for the node to answer. In essence, a heartbeat is the manager asking the Render node whether it remains responsive and in good shape. When a Render node misses several heartbeats back to back, Fusion concludes that node is gone. Its assigned frames then shift to the other Render nodes on the list. Both the count of consecutive missed heartbeats that triggers the manager to drop a Render node from the list, and the gap of time between heartbeats, are adjustable in the master’s Network Preferences panel. For roughly 90% of situations the defaults on these settings work fine. Where the rendered compositions tend to demand more memory than the machine physically holds, memory gets swapped out to disk. In that case raising these two settings a bit can be worthwhile, offsetting the laggy response until you can fit more RAM into the Render node.

### Managing Memory Use

Frequently a network is a mix of machines sporting all kinds of CPU and memory setups. Whatever memory settings the workstation that authored a composition used might not suit every Render node across the network. The Render node software lets you override the memory settings baked into the composition and substitute custom ones better matched to a given Render node’s system configuration. Reaching a node’s preferences is done by right-clicking its icon in the Windows Notification area, or on the macOS menu bar, and selecting Preferences. Within the Preferences dialog, open the Memory panel.

### Override Composition Settings

Switch this option on so the Render node’s own local settings drive the rendering of whatever compositions arrive. Turn it off to fall back on the default settings stored inside the composition.

### Render Several Frames at Once

Fusion can process several frames in parallel to boost render throughput. This slider sets how many frames render at the same time. Whatever value shows multiplies memory consumption (a setting of 3 eats three times the memory of a setting of 1). Typical values run 2 or 3, though well-equipped machines may gain from higher numbers, while memory-starved machines might need the value held at 1.

### Simultaneous Branching

Turn this option on to have all layers render in parallel. The throughput payoff can be considerable, yet it may also consume far more memory, particularly when a composition stacks up many layers. On memory-constrained machines you may have to switch Simultaneous Branching off while rendering compositions that carry lots of layers.

### Limitations of Render Nodes

Keep in mind a handful of significant constraints as you build compositions and render them across a network.

### Time Stretching

Compositions leaning on the Time Stretcher and Time Speed tools can run into trouble during a network render. Accelerating or decelerating compositions and clips means pulling several frames both ahead of and behind the frame currently rendering, which drives up I/O against the file server. That can deepen network bottlenecks and make rendering inefficient. When a composition employs the Time Stretcher or Time Speed tools, confirm the network can handle the load, or pre-render that portion of the composition ahead of network rendering.

### Linear Tools

Some tools simply won’t network render correctly. Third-party particle systems like Genarts’s Smoke and Rain, along with the Fusion Trails node, can’t be rendered properly across the network. Such tools typically retain the result from the prior render and feed it into the next frame’s render, making each frame reliant on the one rendered just before. Because that data stays local to the tool, these tools fail to render correctly over a network.

### Saving to Multi-Frame Formats

A single QuickTime file can’t be rendered by several machines together. Render instead to discrete sequential file formats such as EXR, DPX, JPEG, and the like. After the render finishes, one workstation can pull in the image sequence in order and export it to whatever compiled format you want. NOTE: None of this pertains to network rendered previews, which are previews built over the network using spooling so that multi-frame formats render successfully. This limitation touches final renders alone.

### Troubleshooting

A few recurring traps show up when rendering across a network. Nearly every network rendering issue traces back to either path names or plugins. Revisit this chapter’s “Preparing Compositions for Network Rendering” section to go over the key setup requirements again. Make sure each Render node can load both the compositions and the media, and that every Render node has the plugins the composition relies on installed. Should trouble linger, get in touch with Blackmagic Design’s technical support through the support area on the Blackmagic Design website. Keep a copy of the render.log file to forward to technical support.

### Checking the Render Log
