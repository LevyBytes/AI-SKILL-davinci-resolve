# Getting Clips Into Fusion (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Trim: With the Trim range control you cut frames off a clip’s beginning or end. Move the Trim In to drop frames at the head, and set Trim Out to name the clip’s final frame. The numbers entered are offsets. Putting 5 into Trim In makes the sequence’s 5th frame the starting point and skips the first four. Setting Trim Out to 95 halts frame loading once the 95th has been read.
- Hold First Frame/Hold Last Frame: Using the Hold First Frame and Hold Last Frame controls, the clip’s first or last frame is held for however many frames you specify. When the footage loops, these held frames carry into the loop.
- Reverse: Tick this checkbox to play the footage backward, so the last frame leads off and the first frame comes at the end.
- Loop: Tick this checkbox to repeat the footage through to the project’s end. Whatever you add with Hold First/Last Frame or remove with Trim In/Out becomes part of the looped clip.

### Using Loader and Saver Nodes in the Fusion Page

Within the Fusion Page, the Loader and Saver nodes serve workflows built around multi-channel EXR files in particular. OpenEXR media is able to carry high-quality floating-point image data, several matte channels, and auxiliary channels output by 3D software. With the Loader node you pull OpenEXR files into a composition straight off the file system while keeping every channel stored inside that file. Saver nodes let you write all or some of a composition out to disk as EXR files, skipping past the DaVinci Resolve Deliver page. Here is how to bring a multi-channel EXR image sequence into the Fusion page: 1 Go to the Fusion page. 2 Bring up the Effects Library, pick the Tools > I/O category, and click the Loader node. 3 Within the OS navigation window that appears, choose the EXR image sequence for import, then click Open. 4 A Loader node tied to that EXR file turns up on the Fusion page, yet no clip arrives in the Media Pool.

### Loader Node Parameters

A Loader node’s image tab carries the same parameters that MediaIn nodes do, as covered earlier here. When a Loader node points at EXR files, though, the Format tab lets you turn specific auxiliary channels held in the file on or off.

Within a Loader node Inspector, the Format tab shows the Aux channels carried by EXR files.

### Outputting Images Using Saver Nodes

Straight from the Fusion page, Saver nodes write OpenEXR image sequences to disk. Because a Saver node attaches to any branch of a node tree, you can export one or several subsets of nodes within a composition. Drop as many Saver nodes as needed onto whatever branches of your composition’s node tree you want to send out, exporting several pieces of a composition. Say a given composition has one branch of nodes building an elaborate background and a second branch making a transparent foreground character: you could write the background and foreground branches to separate OpenEXR files through two Saver nodes. For that, just place a Saver node downstream of whichever nodes you wish to output, then open the Inspector and click Browse to pick a name and destination for the render.

As you name the file, you have to append the .exr file extension; Fusion then sets the output format to match. The software inserts a four-digit frame number ahead of the filename extension automatically. You may, however, dictate the frame padding by tacking on extra zeroes to signal how many digits you want. As an example, 000 stands for 001. With the Saver node configured, output one or more Saver nodes by choosing Fusion > Render All Savers.

The Inspector parameters for a Saver node.

### Manual Disk Caching Using Loader and Saver Nodes

On the Fusion page, the Loader and Saver nodes also help streamline compositions that are deeply complex and heavy on the processor. As an instance, you might use a Saver node to write out branches of a node tree that rarely need tweaking anymore to OpenEXR, then pull that result back in to stand in for the original branch and so lift your composition’s performance. Employed in this fashion, Loader and Saver nodes give you a rock-solid manual caching workflow whose media files are never purged on their own unless you delete them yourself. Provided you keep the original branch of nodes around, you can revisit and re-render these hand-cached portions of a composition whenever the need arises.

### Preparing Compositions in Fusion Studio

Coming up, the next handful of sections walk through getting a project ready and dropping clips into a composition while working in Fusion Studio. We call the Fusion project file a composition, or comp for short. Launching the Fusion Studio application spawns a fresh empty composition by default. Inside a composition you may hold single frames, image sequences, or movie files across various resolutions and bit depths. The opening moves of compositing are learning which files you can bring in, configuring a composition to accept them, and at last reading those files in.

### Opening, Closing, and Saving Compositions

The moment Fusion Studio opens, a fresh empty composition appears. Should you need them, you can also make or open several compositions together. Every extra composition opens as its own tab on the main Fusion Studio window.

Three compositions opened as tabs in Fusion Studio.

To create a second new composition:

- Choose File > New.

To open an existing composition, do one of the following:

- Choose File > Open.
- Choose File > Open Recent, then pick from the roster of comps opened lately.
- Drag a composition file out of an OS file browser onto the tabbed composition strip at the top of the Fusion Studio window.
- Double-click a composition file within the OS file browser.

Any of these approaches will close the composition you have open:

- Choose File > Close from the menu running along the top of the Fusion window.
- Click the Close X icon at the right end of the composition’s tab. Should the composition hold unsaved edits, a dialog box pops up offering to save before it closes.

TIP: Any composition holding unsaved edits shows an asterisk (\*) beside its name both in the Fusion Studio title bar and on the composition’s tab. These are the ways to save the composition you currently have open:

- Choose File > Save and supply a name when the comp has not been named yet.
- Choose File > Save As to store it under a different name.
- Choose File > Save Version to write out the open composition with a three-digit version number appended to its name. With every version you save, that number steps up on its own and the comp file lands in the same folder as the original version.

### Auto Save

At fixed intervals, auto save writes the composition out to a temporary file on its own. This guards your work against power outages, software trouble, or an accidental close. Turn it on for new compositions by choosing Fusion Studio > Preferences, then finding Global > General > Auto Save inside the Preferences dialog. The auto-save file leaves the current composition on disk untouched. It puts a same-named file in the composition’s folder but gives it the extension .autosave rather than .comp. For compositions never saved, the autosave file goes to the default folder named by the Comp: path under the Paths panel of the Global Preferences. When Fusion Studio loads a composition and an auto-save file exists, a dialog asks whether to bring in the auto-saved or the original version.

### The Composition File Format

A composition file is stored as a human-readable plain text file. Describing a composition in plain text makes it simpler to fold Fusion into organized visual effects pipelines and asset management systems. You can open and edit a composition file in any ordinary text editor. That said, never open one in a word processor like Microsoft Word or Apple Pages, since those tend to embed extra formatting data that leaves the composition unreadable to Fusion.

Importing and Exporting a Composition from DaVinci Resolve Even though compositions built on DaVinci Resolve’s Fusion page live inside the DaVinci Resolve project library as .drp project files, you are free to import and export Fusion composition files while on the Fusion page. That makes passing Fusion compositions between the two applications quite simple. Here is how to export a Fusion composition out of DaVinci Resolve: 1 Inside DaVinci Resolve, move to the Fusion page holding the composition you wish to export. 2 Choose File > Export Fusion Composition. 3 A Save dialog opens where you supply a name and place for the exported Fusion composition. The filename gets a .comp extension appended. What exports is solely the node tree built on the Fusion page. Any clips left out of the Node Editor will not show up in the Fusion Studio bins. Likewise, ResolveFX placed in the comp do not carry over from the Fusion page to Fusion Studio. DaVinci Resolve’s MediaIn nodes convert to Loader nodes automatically, and when the file path stays the same the media relinks on its own. MediaOut nodes turn into Saver nodes. You can run the trip in reverse too, writing a composition file out of Fusion Studio and bringing it into the Fusion page inside DaVinci Resolve. Here is how to import a composition from Fusion Studio onto the Fusion page within DaVinci Resolve: 1 Inside Fusion Studio, open the composition you intend to bring over to the Fusion page. 2 Inside DaVinci Resolve, move to the Fusion page that holds an empty composition. Whatever you import will entirely supplant the composition already sitting in that page’s Node Editor. 3 Choose File > Import Fusion Composition. 4 From the Open dialog, browse to the Fusion comp and click Open. That new comp loads into the Node Editor and takes the place of the one that was there. TIP: To preserve an existing comp on the Fusion page while folding in a new comp from Fusion Studio, open Fusion Studio, select every node in the Node Editor, and press Command-C to copy them. Next, open DaVinci Resolve, switch the Fusion page to the composition you want, click an empty spot in the Node Editor, and press Command-V to paste in the Fusion Studio nodes. Then wire the pasted node tree into the existing one through a Merge or Merge 3D node.

### Setting Up a Composition

Your source media may arrive in many formats, among them HD, UHD, and 4K or bigger. A single comp frequently holds a mixture of formats. Every format carries its own traits, spanning resolution, color depth, and gamma curve. While Fusion happily blends material of differing formats inside one composite, it pays to understand how Fusion Studio sets up and combines materials of differing formats as it loads and merges them. Opening Fusion Studio gives you an empty composition. Your very first task on a fresh composition is to set the preferences so they match the output format you ultimately want. Those preferences fall into two distinct groups: the global preferences and the preferences belonging to whichever composition is currently open.

Even though the Node Editor settles the final output resolution, the Frame Format preferences govern the default resolution given to new Creator tools (such as text, background, fractals, and the like), the aspect ratio, and the frame rate used during playback.

Frame Format preferences for images generated in Fusion. When you work with the same frame format every day, your global Frame Format preferences ought to reflect the footage you reach for most. As an example, on a project where most source content is 1080p high definition, lining up the global preferences with the frame format of that HD source content you commonly use makes sense. To define the default Frame Format for new compositions, proceed as follows: 1 Choose Fusion Studio > Preferences. 2 In the sidebar, click the disclosure triangle for Global and Default Settings so the Globals group expands. 3 Pick the Frame Format category so its options come into view. Choices you make in the Global Frame Format category fix the default frame format for every new composition you build. They leave existing compositions and the one presently open alone. To alter an existing composition, you must open that comp, then choose the Frame Format controls shown beneath the comp’s name in the sidebar. To dig deeper into preferences, consult the DaVinci Resolve Reference Manual at Chapter 75, “Preferences,” or else the Fusion Reference Manual at Chapter 15.

### Reading Clips into Fusion Studio

With the Frame Format preferences in place, you typically kick off a composite by reading in source media. As Fusion reads media, it neither converts nor relocates the original files; it just reads them where they sit, on whatever storage volume holds them. Throughout, you stay tied to the original source files in their original spot. A Loader tool is what reads source media into a comp. Even though Fusion Studio offers other tools that generate imagery such as gradients, fractals, or text, every still image, image sequence, or movie file has to enter your comp through a Loader tool.

Loader and Saver tools handle bringing media into Fusion Studio and rendering it back out. Use any of these to add media to your comp:

- Hit Effects to bring up the Effects Library, then pick Tools > I/O > Loader.
- Click the Loader icon in the toolbar.
- Over the Node Editor, right-click and then pick Add Tool > I/O > Loader.
- Drag a file out of an OS file browser window onto the Node Editor.

Drag several files onto the Node Editor and each one gets its own Loader. Yet drag a single frame belonging to an image sequence and the whole image sequence reads into the comp through one Loader, provided the numbering runs in order. To pull in just one frame of an image sequence:

- Hold Shift as you drag a single frame from an image sequence onto the Node Editor. That is useful for reading in sequentially numbered photographs from a digital camera.

Whatever clip, image file, or graphic you carry into Fusion is represented by a Loader. Still, Fusion Studio can take in other media types as well. The File > Import menu accepts Photoshop PSD files and SVG splines, plus 3D models saved in the Alembic, FBX, and OBJ format. TIP: Choosing File > Import > Footage spawns a fresh composition together with a Loader node for that footage, and the chosen media supplies the composition’s name automatically.

To learn more about the Loader node, turn to Chapter 105, “I/O Nodes,” within the DaVinci Resolve Reference Manual, or Chapter 45 of the Fusion Reference Manual.

### Aligning Clips in a Fusion Studio Composition

Drop a clip into a composition and its Loader node lands at frame 0 of that composition. The part of the clip that actually matters to you, though, might not kick in until a handful of frames or several seconds further on. So that you can line up the timing of every media element, each Loader carries timing and trimming options in the Inspector. On top of that, you can hold the first or last frame longer than the original media runs, and reverse or loop the clip to stretch your composition’s range. The Inspector’s upper region holds the Global In and Global Out settings. That range slider fixes where in your composition the clip starts and stops, working just like dragging a clip along a track in a Timeline. Down at the bottom of the Inspector, the Hold First Frame and Hold Last Frame dials let you freeze frames when the clip falls short of the composition’s global time.

Drag the Global In/Out range slider to shift a clip in time so it shows up at the right moment in a comp. Just under the filename in the Inspector sits a Trim In and Out range slider, which fixes the clip’s start frame and end frame. Pulling the Trim In strips frames off the clip’s head, while pulling the Trim Out strips frames off its tail. Even when you strip frames from a clip’s head, the Global In is always what decides where in time the clip starts in your comp. Take a Loader whose Global In sits on frame 0: trim the clip to begin on frame 10, and frame 10 of the source clip lands at the comp’s start on frame 0.

Use the Trim In/Out to drop needless frames off a clip’s head or tail. Rather than fiddling with timing in the Inspector, the Keyframes Editor makes it far clearer visually. To dig further into the Keyframes Editor and changing a clip’s time, turn to Chapter 71, “Animating in Fusion’s Keyframes Editor,” within the DaVinci Resolve Reference Manual, or Chapter 9 of the Fusion Reference Manual.

### Loader Node Inputs

A Loader node carries a single Effects mask input plus a single output. As for that Effects mask input, wiring a mask node like a Polygon or B-Spline node into it spawns an alpha channel on the Loader node automatically. TIP: Connect a Mask node that has no shapes drawn and the mask puts out total transparency, which leaves the image coming from the MediaIn node empty. To rotoscope over a MediaIn node, start by making a Mask node that is left unconnected; with that Mask node selected and the Media In node showing in the viewer, draw your mask. After you close the shape you are drawing, wire the Mask node into the MediaIn node’s input and you are set.

### Using Proxies for Better Performance

For increased performance, you can do one of two things:

- Build smaller media files and store them on disk through Optimized Media in DaVinci Resolve
- Render out proxy files using Saver nodes in Fusion Studio

On top of that, both applications can make proxies on the fly, with no new files written to disk, by way of the Proxy and Auto Proxy options found in the transport controls area. Switching on the Proxy and Auto Proxy options takes one of two routes, which depends on the Fusion version you run:

Proxy and Auto Proxy options in the transport controls right-click menu.

- On the Fusion page, right-click the blank region behind the transport controls to switch on the Proxy option.
- Within Fusion Studio, hit the Proxy (Prx) button found in the transport area, which turns proxy usage on.

What the Proxy option does is lower the image resolution while you view and work. Rather than drawing every pixel, it interactively handles one pixel out of every x. Within Fusion Studio, you fix the value of x by right-clicking the Prx button and picking a proxy ratio from the drop-down menu; pick 5 from that menu, for instance, and the ratio becomes 5:1. On the Fusion page, you set the proxy ratio by choosing Fusion > Fusion Settings and adjusting the Proxy slider in the General panel.

Through the Proxy menu you set how many pixels get skipped during processing. The Auto Proxy button tells Fusion to degrade the image interactively only during the moments you are making an adjustment, after which it snaps back to full resolution once you let go of the control. Much as with the Prx button in Fusion Studio, you set the Auto Proxy ratio by right-clicking the APrx button and picking a ratio off its menu. With a Loader node selected, the Inspector shows a Proxy Filename field, letting you name a clip that loads whenever Proxy mode is active. That way, smaller copies of the image can load to quicken file I/O off disk and processing. It really helps with high-resolution files such as EXR that may sit on a remote server. Keeping lower-resolution copies of the elements locally cuts network bandwidth, interactive render times, and memory consumption. The proxy clip you build must carry the same frame count as the original clip, and where image sequences are involved, that clip’s sequence numbers must begin and end on the same frame numbers. Should the proxies share the original files’ format, they will draw on the same format options in the Inspector as the originals do.

### Presetting Proxy Quality

In Fusion Studio, instead of right-clicking the Proxy button to fix proxy quality, you can preset both the standard and the Auto Proxy quality from the Fusion Preferences window. Within that window, the General pane holds sliders for standard Proxy files as well as Auto Proxy files. Those sliders set the default ratio that builds proxies whenever the Proxy and Auto Proxy modes are switched on. None of this touches the final render quality. TIP: Although the proxies get processed at a smaller size than the originals, the viewers scale the pictures so they still read at the original resolutions.

### File Format Options

Across DaVinci Resolve and Fusion Studio, the Fusion interface surfaces format-specific options in slightly differing ways. Whereas Fusion Studio keeps most file-specific options on the Loader’s Format tab, the Fusion page generally puts those options on the main Image tab of the MediaIn node. OpenEXR stands as the lone exception: its many options get their own separate tab even within the Fusion page’s MediaIn node. Options are not present for every file format. Extra options appear on load only for the DPX, OpenEXR, PSD, and QuickTime formats.

### DPX

For DPX files, the Format tab on Fusion Studio’s Loader node serves to turn image data from logarithmic into linear. Many people leave these settings on bypass and instead handle the Log to Linear conversion with a Cineon Log node.

### OpenEXR

OpenEXR delivers a compact, adaptable high dynamic range (float) format. It accommodates an assortment of extra non-RGBA channels along with metadata. You can view and switch on those channels from the Inspector’s Format tab.

Inside a Loader node Inspector, the Aux channels belonging to EXR files appear on the Format tab.

### Photoshop PSD

Photoshop PSD files come in by way of two approaches. You may bring in the PSD file so it shows as one single node in the Node Editor, or bring in the PSD so each layer shows as its own node in the Node Editor. When you have no need for separate control of each layer, or no blend modes went into building the PSD, importing the PSD as a single node keeps things tidier. When you do need per-layer control, or the Blend modes inside the PSD are essential, then import the file so every layer turns into a node in the Node Editor. Below, each approach is laid out for the Fusion page and for Fusion Studio.

Using the Media Pool in DaVinci Resolve’s Fusion page: Whatever PSD file you add to the Media Pool in DaVinci Resolve becomes reachable from the Fusion page. Once you drag that PSD file out of the Media Pool onto the Node Editor, the image shows up as a MediaIn node. From there the Inspector’s Layer drop-down menu lets you choose which layer of the PSD file to use. Using a Loader node in Fusion Studio: This route reads in Photoshop PSD files and lets you pick which layer of the PSD file the comp uses. Fusion can pull in any single layer held in the PSD file, or the finished image with all of its layers. It does not support transformation and adjustment layers.

Within the Inspector, the Format tab presents controls particular to a Photoshop PSD file. To pull in every layer separately from a PSD file with the right blend modes, take one of these routes:

- Inside DaVinci Resolve, move to the Fusion page and choose Fusion > Import > PSD.
- In Fusion Studio, choose File > Import > PSD. Either route above builds a node tree in which a node stands for each PSD layer and one or more Merge nodes join the layers together. Those Merge nodes adopt the Apply mode found in the PSD file and get named automatically from that Apply mode setting.

Here a Photoshop PSD file’s two layers come in and wire into a Merge node whose Apply mode is set to Screen.

### QuickTime

A QuickTime file may hold several tracks. The Inspector’s Format tab lets you pick which one of those tracks to use.
