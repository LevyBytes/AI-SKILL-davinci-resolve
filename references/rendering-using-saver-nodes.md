# Rendering Using Saver Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Rendering Using Saver Nodes

This section walks through rendering compositions by way of Saver nodes, both in Fusion Studio and on the Fusion page in DaVinci Resolve. It also explains how to spread rendering across several networked computers while working in Fusion Studio.

### Rendering Overview

Once a composition in Fusion is finished, you'll want to render its files out to disk so they can play back and slot into a larger timeline. The way you render differs sharply between Fusion Studio and the Fusion page in DaVinci Resolve. Wrapping up a composite on the Fusion Page means using a MediaOut node to cache the outcome into the Edit or Cut page Timeline, while the DaVinci Resolve Deliver page takes care of the final render of the whole Timeline. Pulling finished composites out of Fusion Studio, by contrast, starts with setting up and rendering from a Saver node in the Node Editor. Fusion Studio can also hand off an assortment of rendering tasks to other machines across a network.

### Rendering in the Fusion Page

On the Fusion page, you need a MediaOut node to carry your composite from the Fusion page back to the Edit or Cut page Timeline. Whatever appears at the MediaOut node when you view it is exactly what gets rendered back onto the Edit or Cut page. In DaVinci Resolve the process runs semi-automatically: the Smart Render Cache setting starts caching the MediaOut node almost as soon as you head back to the Edit or Cut page Timeline. The cache file format, along with any resolution scaling that fits the composition into the Timeline Resolution, is governed in the DaVinci Resolve Project Settings.

### Rendering in Fusion Studio

Within Fusion Studio, every render passes through Saver nodes. Much like MediaOut nodes on the Fusion page, Saver nodes usually hang off the end of a node tree to render the final composite. It is the Saver node that fixes the name, format, and location of the rendered files.

### Rendering with the Saver Node

Kicking off a render in Fusion Studio requires dropping at least one Saver node into the node tree. Typically you park one Saver node right at the tail of your tree to render the final image.

A lone Saver node sits at the end of a node tree to render the final composite. You're free to hook several Saver nodes anywhere along the node tree to render out separate parts of a composite. The example below places three Saver nodes at various spots in the node tree: the top pair render each half of the composite, while the bottom one renders the result of the whole composite.

Several Saver nodes can sit at different parts of a node tree. You may also branch several Saver nodes off the same node to produce a range of output formats. In the example beneath, the three Savers export differing formats of one shot.

Several Saver nodes can be added to produce different output formats. Dropping a Saver node into a node tree pops open a Save dialog automatically, where you name the file and browse to the spot the exported file lands. From there you turn to the Inspector to set up the output format. For fuller detail on the Saver node, the DaVinci Resolve Reference Manual covers it in Chapter 105, “I/O Nodes,” and the Fusion Reference Manual covers it in Chapter 45.

### Setting Filenames for Export

Tack a file extension onto the name and Fusion sets the output format to match. Name your file image_name.exr, for instance, and the Inspector is geared to output an EXR file; name one image_name.mov and the Inspector is geared for an H264 QuickTime movie. Should you want to switch or tweak the file type setting, the specific parameters for whichever format you pick live on the Saver's format tab in the Inspector.

### The Saver’s Format tab with controls for QuickTime

Choose to output an image sequence and a four-digit frame number gets slotted in automatically ahead of the filename extension. Name your file image*name.exr, say, and you wind up with files called image_name0000.exr, image_name0001.exr, and onward. To dictate the frame padding, append a run of zeroes that signals how many digits you want. Enter a filename as image* name*000.exr, for example, and you get an image sequence named Image_name_000.exr, Image* name_001.exr, Image_name_002.exr, and so forth. NOTE: The opening frame number always takes the Time Ruler start frame number.

### Using the Render Settings Dialog

Within Fusion Studio, you launch a render by clicking the Render button, which brings up the Render Settings dialog. That dialog sets the render's quality, frame range, and network usage. To Render a comp in Fusion Studio: 1 Wire a Saver node onto the end of your composition. 2 Type a name and a location for the saved file(s) into the Save window. 3 Where needed, set the format via the Format tab in the Inspector. 4 Click the Render button over in the transport controls area, or pick File > Render All Savers. Up comes the Render Settings dialog, offering options for the rendered output.

### The Render Settings dialog options

Double-check that the frame range and the other parameters are right, then click Start Render.

### Saver nodes in the DaVinci Resolve Fusion page

A Saver node lives on the Fusion page as well, though it serves a different end than its Fusion Studio counterpart. On the Fusion page, the MediaOut node carries the bulk of rendering duties. No Render Settings dialog appears here, because DaVinci Resolve's cache settings already fix the rendering location and format. Saver nodes on the Fusion page are a special case, reserved for rendering OpenEXR files alone. After dropping in a Saver node, you type the filename followed by the extension. exr. Click the Browse button to choose where the EXR sequence goes, then pick Fusion > Render All Savers. The Saver node proves handy for streamlining wildly complex, processor-hungry compositions. You might, for example, use a Saver node to render specific branches of a node tree that no longer need regular tweaking out to OpenEXR, then reimport that result in place of the original branch of nodes to lift your composition's performance. Or you can render out multi-channel mattes or EXR images holding Arbitrary Output Variables (AOVs) for use in other applications.

### Render Settings Dialog Options

A lot of what the Fusion Studio Render Settings dialog offers comes into play when you want a quick preview or a test render. The dialog's options let you boost performance by switching off some of the image-processing operations that eat time yet yield higher-quality results. More often than not, the Configurations section is where you set things first. That section decides whether you're after a final high-quality render or a speedier preview render. Pick Final and you're locked out of the options that would cap the quality.

### Settings

With the Configuration section on Preview, the Render dialog's Settings section carries three options that shape the overall quality and look of your final output. These buttons weigh heavily on render times too. With the Configurations setting on Final, you can't switch these options off HiQ: Switched on, this setting renders at full image quality. When you need to preview how a node's final output would look, you'd enable the HiQ setting. When you're knocking out a rough preview to test animation, switching it off saves you time. MB: The MB here is short for Motion Blur. Switched on, this setting renders with motion blur in place wherever a node is set to generate it. When you're putting together a rough preview and aren't worried about motion blur on animated elements, switching it off saves you time. Some: With Some switched on, only the nodes strictly required to build the image of the node you're previewing get rendered.

### Size

With the Configurations section on Preview, the Size options let you render frame sizes below full resolution. That comes in handy when you're using the Render dialog to build proxies or simply to keep the file size down.

### Network

How rendering gets spread across multiple computers is governed by the Network setting. For fuller detail, turn to this chapter's network rendering section.

### Shoot On

Once more, this option surfaces only while Configurations is on Preview. The Shoot On setting lets you skip frames during a render. You might render every second, third, or fourth frame to trim render time and get quicker feedback. The Step parameter is what you use to set the interval at which frames render.

### Frame Range

Whether Configurations rests on Final or on Preview, this option starts out at whatever current Render In/Out Range the Time Ruler holds, and from that it derives the render's start and end frames. You're free to change the range to render more frames or fewer.

### Configurations

On Final, the Render Settings are geared to turn out the highest-quality results, and most of the dialog's options are off-limits to you. On Preview, you can dial the options for quicker rendering performance. Once you've built a preview configuration worth keeping, save it for later by clicking the Add button, naming it, and clicking OK.

### Rendering Previews

Flipbook previews can be rendered straight into a viewer. Such Flipbook previews reside wholly in RAM. To make one, right-click a node in the Node Editor and, from the drop-down menu, follow Create > Play/Preview on > Left viewer/Right viewer. Up comes the Render Settings dialog, where you set up the preview and start the render. Another route is to Option-drag a node right out of the Node Editor into a viewer; the Render Settings dialog shows up and the preview lands on whichever viewer you aimed for. For fuller detail on rendering RAM previews, the DaVinci Resolve Reference Manual handles it in Chapter 69, “Using Viewers.” and the Fusion Reference Manual handles it in Chapter 7.

TIP: Option-Shift-dragging a node into a viewer bypasses the Render dialog and reuses your previous settings.

### Setting Up Network Rendering in Fusion Studio

Fusion Studio can parcel out an assortment of rendering tasks to any number of networked computers, letting several machines pitch in on network-rendered previews, disk caches, and final renders. Through the Render Settings dialog or the built-in Render Manager, you can hand compositions off to other Fusion Studio copies, and likewise to a Fusion Render node or several. You can also drive rendering from the command line to tie in with third-party render managers such as Deadline, Rush, and Smedge. Render nodes are machines lacking the full Fusion application but carrying the Fusion Render node software. That software isn't laid down by default when you install Fusion Studio, yet you can add it whenever you like through the Fusion Render node Installer. Look for that installer bundled inside the Blackmagic Fusion Studio installer.dmg (on macOS) and, for Linux and Windows, inside the Blackmagic Fusion Studio.zip. Since Fusion Studio is licensed for an unlimited number of Render nodes, you can put the Render node software on however many macOS, Windows, and Linux machines you'd like pitching in on a network render. To install a Render node: 1 Download the Blackmagic Fusion Studio archive, unzip it, then track down the Render Node Installer. 2 Copy the Install Fusion Render Node [version] onto every networked computer you want carrying out rendering operations. 3 Install the Render node. Out of the box, the Render node application lands in the Start Menu on Windows under Blackmagic Design. On macOS it joins the menu bar, and on Linux it shows up in the app launcher. The Render node application fires up on its own each time you log in to the computer. To stop it from launching automatically, pick Quit at the Render node icon over in the macOS menu. Under Linux, right-click the icon and pick Kill Process; under Windows, delete the shortcut from the Windows Startup directory.

### Licensing for Network Rendering

Most editions of Fusion Studio get their license by plugging a single-seat hardware key (dongle) into the very computer where Fusion is installed. Every dongle carries an unlimited supply of cross-platform Render node licenses, which you may install on as many macOS, Windows, and Linux machines as you require. So that Fusion Studio can reach the Render nodes, the machine holding the Fusion Studio dongle must sit on the same local network subnet as those Render nodes. This network licensing needs no individual license files; the Render nodes hunt down the dongle on the subnet by themselves, which keeps setup simple. Single-seat dongles won't “float” across a network — they have to stay plugged into the same machine running Fusion Studio.

### Multi-License Dongles

With a multi-license dongle, plugging it into any machine on the same subnet licenses 10 copies of Fusion Studio. Because these licenses “float” across a network, Fusion Studio needn't run on the very machine holding the dongle. So long as Fusion Studio shares the subnet, it locates the license server on its own and checks out a free license.

You can stack multi-seat dongles together to dial in the number of Fusion seats at a larger facility. Three dongles each licensed for 10 Fusion Studios, for instance, would deliver 30 licenses. It also buys you redundancy: in that same example, three machines can serve as license servers, and should the first server go down for any reason, Fusion Studio falls through to the next one automatically. As another option, you can plug several dongles into one computer.

### Setting Up a License Server

Getting the license ready for network rendering starts by plugging either a single-seat or multi-seat dongle into a machine that will host the license server. The Render node installer lays down Fusion Server to act as that license server, though the Render node itself needn't run on the same machine. Fusion Server is configured to launch at startup and sit quietly in the background as a service/daemon, standing by to dish out licenses and Fusion bins. Because Fusion Server is what hands out the various licenses, it has to be running any time you want to run Fusion Studio or use the Render nodes for network rendering. By default it starts on its own and keeps running for as long as another machine holds a license or a Render node is working. With nothing drawing on it, Fusion Server shuts down after 30 seconds. You'll need your network administrator to write firewall rules that let the Fusion Server, FusionScript, and the Fusion Render node applications talk to and verify licensing with the machine carrying the Fusion Studio dongle. Should you pull a dongle or should the network cut out for any reason, the licenses on every connected Fusion Studio application drop as well. The moment it loses its license, Fusion Studio sets off looking for another one, whether locally or on a different machine. Turn up no license and Fusion halts rendering, presenting a dialog that lets you retry the search or autosave the comp and quit. Render nodes only look for a network license once, at startup, so removing the dongle or hitting network trouble leaves them unaffected.

### Setting Up a License Server with Environment Variables

Environment variables give you a route to declaring flexible or “variable” configuration options. While network rendering in Fusion, they help when you need to set a location for a moment or single out a preference file. Through the FUSION*LICENSE_SERVER environment variable, you can point to different locations for the File Server. Rather than searching one place for the Fusion Server, you can list several license servers split by semicolons. Take, for example, fu:SetPrefs("Global.EnvironmentVars.FUSION_LICENSE* SERVER", "192.168.1.12; 192.168.10.55;_") The environment variable also lets you sweep a subnet for license servers—as in, “bobs-mac.local;10.0.0.23;_;license.mystudio.com”. An asterisk (_) thrown in calls for a broadcast search of the local subnet. As with most environment variables, the license server can be lodged in the Global Preferences by editing the Prefs text file. EnvironmentVars: `fu:SetPrefs("Global.EnvironmentVars. FUSION_LICENSE_SERVER", "10.0.0.23;_")` `fu:SavePrefs()`, and for more on wielding environment variables, the DaVinci Resolve Reference Manual devotes Chapter 75, “Preferences,” to it while the Fusion Reference Manual devotes Chapter 15. NOTE: Those straight quotes (" ") shown in the environment variables above are deliberate and must not be swapped for typographer's, or curly, quotes (“ ”).

### Configuring the Render Master and Render nodes

Machines taking part in network rendering fall into two roles.

- The Render Master keeps the list of compositions awaiting render (the queue) and parcels out frames to the Render nodes for rendering. Picture the Render Master as the traffic cop of the whole operation.
- The Render nodes are the workhorse machines that carry out the rendering. Every machine in a network render has to share one network subnet, and each must be able to reach the various files (Fonts and third-party plugins among them) that built the composite. That file path has to read the same on every machine taking part in the render.

### Preparing the Render Master

The Render Master holds the queue of compositions awaiting render and doles out frames to the Render nodes. On top of that, it keeps the Render node list current and pushes updates out to the various Render nodes whenever the need arises. At least one machine in the render farm has to be configured as the Render Master, and any copy of Fusion can fill that role once you've set up the Fusion Network Preferences.

The Network panel is where machines get designated as Render Masters. Taking on the Render Master role barely dents render performance, since the system resources it draws are negligible. Even so, a few particular steps stand between you and turning one of your machines into a Render Master.

Here's how you configure the Render Master: 1 Put a copy of Fusion Studio onto whichever machine you've earmarked as the Render Master. 2 From within Fusion Studio, on macOS pick Fusion Studio > Preferences, while on Windows and Linux pick File > Preferences 3 Inside the Preferences dialog, head to the Global > Network Preferences panel. 4 Type the Render Master's name into the Name field and enter the IP address. 5 Tick the Make This Machine a Render Master checkbox. 6 Want this machine pulling its weight in the render farm too? Then also tick the checkbox labeled Allow This Machine to Be Used as a Render Node. To have the Render Node act as the Render Manager:

- Highlight a node within the Render Manager, then from its contextual menu choose Set Default Master. After a machine is cleared to act as the master, lean on the Render Manager to add the Render nodes it will oversee. A thorough rundown of the Render Manager dialog comes later in this chapter.

### Preparing Render Nodes

Before any network render can start, the Render nodes have to be set up to take orders from the Render Master. Fusion Studio gives you two ways to clear a machine for use as a Render node:

- Pick File > Allow Network Renders.
- Over in the Global > Network Preferences, switch on the option named Allow This Machine to Be Used as a Network Render Node.

On a macOS Render Node computer:

- Click the Render Node icon in the menu bar and pick Allow Network Renders.

Reaching the Render Node menu by way of the macOS menu bar When you're on a Linux Render Node computer:

- Inside the App Launcher, right-click the Fusion Render Node icon, then pick Allow Network Renders.

On a Windows Render Node computer:

- Within the taskbar Notification area, right-click the Fusion Render Node icon, then pick Allow Network Renders.

### Setting Up the Render Manager

You watch rendering progress through the Render Manager window. It also lets you reorder, add, or drop compositions from a queue and tend the list of Render nodes doing the rendering. To bring up the Render Manager window in Fusion Studio, pick File > Render Manager.

The Render Manager is where you reorder, add, and drop compositions in a render queue. The Render Master always heads the Render Node list down the right side as the first machine. That lets the Render Manager render local queues without touching the network. For the Render Master to drive extra Render nodes, those nodes have to join the Render Node list. Right-click in the Render Node list to add Render nodes by typing a Render node's name or IP address. You can also pick Scan and have the Render Manager hunt for Render nodes across the local network.

The Render Manager is where you add Render nodes.

### Scanning for Render Nodes

While the Render Manager is open, you can launch a scan for Render nodes: right-click inside the Render Manager's Render Node list, then pick Scan for Render Nodes from the drop-down menu. The scan combs every IP address on the network subnet to see whether other machines on the local network are actively answering on the port Fusion reserves for network rendering. For the scan to spot a remote machine, a copy of the Fusion Render node has to be running there.

### Manually Adding Render Nodes

To add a Render node to the Render Node list by hand, right-click in the Render Manager's Render Node list and pick Add Render Node from the drop-down menu.

The Add Render Node dialog lets you type a Render Node name or IP address by hand to find it on the subnet. In the Add Render Node dialog that appears, type the remote Render node's name or its IP address. The Render Manager will try, on its own, to turn names into IP addresses and IP addresses into names. This approach lets you list Render nodes even while they aren't currently reachable on the network.

### Removing Render Nodes

To drop a machine from the Render Node list, right-click the Render Node within the Render Node list and pick Remove Render Node(s) from the pop-up menu. Hold Command on macOS or Ctrl on Windows and Linux to pick several Render nodes for removal at once.

### Loading and Saving Render Node Lists

When you quit the Render Manager, your Render node list is saved automatically into the Documents > Blackmagic Design > Fusion > Queue folder. To store and bring back alternative Render node lists, the menu offers Render Node > Save Render Node List together with its counterpart Load Render Node list.

### Submitting Comps to Network Render

Sending a comp off to render on the network can go by way of three avenues: the Render Manager, the Render Settings dialog, or some third-party render farm application. Speed favors the first of those dialogs, whereas richer feedback and tighter control over the process come from the Render Manager and from third-party render farm applications.

### Using the Render Settings Dialog for Network Rendering

As you launch a preview or a final render, ticking the Use network checkbox in the Render Settings dialog and submitting the job tacks a composition onto the tail of the current queue in the Render Manager. Which Render Master gets used follows the Fusion preferences of the workstation that submitted the comp.

The Use Network checkbox turns on network rendering from the Render Settings dialog.

NOTE: Distributed network rendering handles image sequences such as EXR, TIFF, and DPX. It won't work for Quicktime, H264, ProRes, or MXF files.

### Using the Render Manager Window for Network Rendering

The Render Manager runs a render queue that lets you batch render comps. Compositions render in whatever order they sit in the Render Manager — the top entry first, then the one beneath it, and onward. Several comps in a queue can render at the same time, depending on which group of Render nodes they draw on and on the priority each comp carries. Here's how a comp joins the queue within the Render Manager:
