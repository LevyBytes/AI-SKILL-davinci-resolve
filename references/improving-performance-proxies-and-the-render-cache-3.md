# Improving Performance Proxies And The Render Cache (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

A watch folder is just a particular folder on your OS that the Blackmagic Proxy Generator keeps an eye on at all times. As soon as fresh files land in the watch folder, the Blackmagic Proxy Generator gets alerted and, with no further human involvement required, transcodes those files into proxy media on its own. There's no cap on how many watch folders you set up; all that's asked is that the storage the watch folder lives on carry enough room for both the original media files and the freshly made proxy media. IMPORTANT: The proxy media lands in a subfolder called “Proxy” sitting at the same tier of the file hierarchy as the original media file. So when all your original media shares a single folder, you'll end up with one “Proxy” folder housing every proxy clip. When your original media is split across separate folders (i.e., a folder per video clip), you'll wind up with several “Proxy” folders, each tucked inside its clip folder and holding a lone proxy clip. NOTE: A watch folder cannot be named “proxy.” The Proxy Generator has claimed that name. To Add a New Watch Folder At least one watch folder is required, and you may set up as many as you need. You might, for instance, keep distinct watch folders per card, per scene, per date, or by whatever scheme best fits how you work. 1 Click the Add button. 2 Either make a fresh folder or point to one that already exists within the file system window. 3 Press the open button. Your new watch folder then surfaces in the Watch Folders pane of the Blackmagic Proxy Generator, showing its location alongside its current status.

To Remove an Existing Watch Folder Once you're done with a particular watch folder, you can drop it from the Blackmagic Proxy Generator's watch list. Dropping a folder neither erases it nor its files from your drive; all it does is halt the Blackmagic Proxy Generator's monitoring of it. 1 Highlight the watch folder within the Watch Folders list. 2 Click the Remove button. Pulled the wrong watch folder by mistake? Just re-add it through the steps laid out above. Monitoring Watch Folders The state of every watch folder is visible within the Watch Folders section of the Blackmagic Proxy Generator. You can reorder how they appear by hand, dragging an entry higher or lower in the list. Below sits the estimated disk space the proxies will need, and three columns carry details on each folder.

- Volume: The logical volume (disk, network storage, usb drive, etc.) where the watch folder resides. This tells you which physical device has to be hooked up to the computer before the Blackmagic Proxy Generator will work.
- Folder: The name of the Watch Folder. Rather than its path, it displays only the watch folder's own name.
- Status: This column reports the present state of the watch folder's files. Waiting: This folder holds clips not yet transcoded into proxies. It's awaiting the Blackmagic Proxy Generator's launch or the completion of a folder queued ahead of it. Processing (x/x): This folder holds clips undergoing transcoding right now. Left of the slash is the current clip number; right of the slash is the total clip count slated for transcoding. Completed: This folder has wrapped up transcoding every proxy file for the media it contains.

The Watch Folders section of the Blackmagic Proxy Generator

### Setting the Proxy Format

Pick whichever proxy codec you want by choosing its format from this list.

Within the Blackmagic Proxy Generator's Proxy Media Format section Starting and Stopping the Blackmagic Proxy Generator With a watch folder in place and a proxy format chosen, the only remaining step is to hit the Start button in the Processing pane, which kicks off automatic transcoding and watch-folder monitoring. Should you need to halt the process at any moment, simply hit the Stop button. Pressing the space bar likewise toggles Start/Stop.

### The Processing pane of the Blackmagic Proxy Generator

The Processing pane also surfaces the current job's status. It charts the job's progress through a count of clips rendered (x of x), a progress bar, and a percentage readout. Alongside that, it shows the current clip's name, the frames-per-second (fps) at which the render is running, and an estimate of the time still remaining.

### Managing Proxies from the Blackmagic Proxy Generator

Two options exist for handling your proxy files after they're made. They only become available once Processing mode has been stopped. Delete Proxies: This wipes every proxy file (along with the Proxy folder) out of the chosen watch folders. Extract Proxies: This duplicates all proxy files from the chosen watch folders into a new spot picked in the file system dialog. It's handy for assembling a standalone proxy-only folder you can pass to someone else on a portable hard drive or push up to cloud storage. Linking Proxies from the Blackmagic Proxy Generator in DaVinci Resolve After your proxies exist, DaVinci Resolve links them to their original source media on its own the moment you bring the watch folder's original clips into the Media Pool. Manual linking and unlinking is also possible, as the Managing Proxy Media section covers later in this chapter.

### Generating Proxy Media in Other Applications

You can also build proxy files in software beyond DaVinci Resolve, such as other NLEs or assorted media asset management systems. For the proxy to link cleanly to its source media inside DaVinci Resolve, the proxy file has to satisfy these conditions:

- A proxy file's timecode must be identical to that of the source file.
- A proxy file's name must match the source file's (extensions aside).
- A proxy file's frame rate must equal the source file's.
- DaVinci Resolve must support whatever format and codec the proxy files use.

Provided your proxy file clears these conditions, you'll be able to hand-link proxy media made in other software to source clips within the Media Pool, as described below.

### Managing Proxy Media

The status and whereabouts of all your proxy media show up in the Media Pool's List view. Right-click any column heading and tick the boxes for “Proxy” and “Proxy Media Path.”

- Proxy: This column reports the proxy status as it stands. None: Signals that no proxy media exists yet. Offline: Signals that a proxy was made but isn't turning up at the Proxy Media path. (Resolution): A figure giving the made proxy's resolution and confirming it's online.
- Proxy Media Path: Where DaVinci Resolve expects to find the proxy file. Should that spot be wrong, you can hand-relink the proxy to a fresh path.

In List view the proxy columns lay out each clip's Proxy Media status and location Linking Clips to Proxy Media When you've built proxy media in another piece of software, or relocated the internally built proxy media away from its default home in “ProxyMedia,“ the proxies will need hand-linking to their source media files inside your Media Pool. Here's how to link proxy media onto a source clip: 1 Pick one or more clips in the Media Pool you want to attach proxy media to. 2 Right-click one of those chosen clips and pick “Link Proxy Media” off the contextual menu. 3 Through the file browser, locate the specific proxy file or directory (where several clips are involved) to establish a new Proxy Media path, then click Open. Pick a wrong file or directory and a warning dialog box pops up with no linking taking place. 4 When the linking succeeds, the proxy media icon turns up on the clip's thumbnail in the Media Pool.

The Proxy Icon sitting at the thumbnail's lower-left corner, a sign that proxy media is linked for this clip Here's how to unlink proxy media off a source clip: 1 Pick a clip or clips in the Media Pool you want to detach proxy media from. 2 Right-click any clip and pick “Unlink Proxy Media” off the contextual menu. Doing so severs the metadata link running from proxy to source and resets the Proxy column's status to “None.” NOTE: Unlinking a proxy file leaves it intact. The proxy file stays put on the hard drive where it was first made. At the time of writing, removing proxy files calls for deleting them by hand through your OS file system, outside DaVinci Resolve.

### Re-generating Proxy Media

Nothing stops you from making several proxy files for a single clip. That's handy when you want to dial in different Camera Raw parameters and weigh them against each other, or to turn out proxy files at varied resolutions. To generate a new proxy: 1 Apply whatever tweaks you like to the current clip's settings. 2 Right-click that same clip and pick “Generate Proxy Media” off the contextual menu. The new proxy file lands in the same directory as the proxy file linked before it, with “\_s00x” tacked onto its file name to set it apart. While the newest proxy is linked to the source file automatically, your earlier proxy versions stay on disk, leaving you free to relink the various versions by hand whenever you need.

### Switching Between Proxy Media and Original Media

To flip between playing back your original source media and the proxy media, use the Proxy Handling icon in the Viewer on the Cut page, or on the Edit page go to Playback > Proxy Handling and choose one of the options below.

- Disable All Proxies: This shuts the proxies off entirely and compels original-media playback alone. Where the original media is missing, the clip gives way to a Media Offline graphic.
- Prefer Proxies: This plays proxy files back, and where a clip has no proxy file, the original media steps in on its own. Where the original media is missing, the proxies serve instead, and the timeline carries a purple line for as long as the original clips are absent.
- Prefer Camera Originals: This plays the original media files back, and where a clip lacks an original media file, the proxy media steps in on its own, with the timeline carrying a purple line for as long as the original clips are absent.

TIP: No matter the proxy mode, a purple line across your timeline flags missing original media and serves as a visual cue to help you spot those absent clips.

### Using Proxy Files for Delivery

Out of the box, the Deliver page always falls back to the original source media for final output, guaranteeing the top-quality render. Ticking the “Use proxy media” box under the Advanced Settings of the Deliver page's Video Render settings flips this, so DaVinci Resolve turns to proxy media for final output instead. That can pay off when you need to trim rendering time while cutting dailies, or to quickly knock out timeline outputs for producers or audio engineers where master quality isn't strictly called for. You'll likewise have to tick the “Use proxy media” box whenever you're editing with proxies and lack access to the original source media.

### Moving Proxies Using a DaVinci Resolve Archive (.dra)

Shifting proxies from one DaVinci Resolve system over to another can prove slow and troublesome if you hand-copy a host of separate assets (proxies, graphics, source files, etc.) out of scattered folders and locations. The simplest route by a wide margin for relocating whole projects between systems is to hand that file management off to DaVinci Resolve, by building a DaVinci Resolve Archive (.dra). An archive file holds not just your project but every piece of its media too, preserving the original project's file paths and organization. To build a DaVinci Resolve Archive file, right-click any project in the Project Manager and pick “Export Project Archive” off the drop-down menu. Inside this mechanism, a new Archive setting in DaVinci Resolve renders proxy handling clean and effortless.

### Creating a Proxy-Only Archive to Share

Within the Archive Options dialog, ticking Proxy Media while unticking Media Files and Render Cache tells DaVinci Resolve to build an Archive from the proxy media alone. That lets you assemble a slim, easily shipped version of your project, whether to carry to another computer or to pass to an editor working from afar. Where a clip has no proxy media (a graphic, say, or a media file you never made a proxy for to begin with), the original media exports automatically so that nothing winds up offline.

### Archive Setting options for exporting only Proxy Media

What you end up with, the .dra, is a folder holding a wholly self-contained copy of your project together with its proxy media. You can readily shuttle this folder between drives, or compress it and ship it over the internet.

### Working Remotely Using Proxy Media

DaVinci Resolve's proxy workflow unlocks plenty of fresh avenues for editing collaboration and media handling. A frequent pattern, for example, keeps the RAW camera master source clips in the edit suite while spinning off low-resolution proxies to carry home for laptop editing. Here's how to put together a portable proxy set for laptop editing: 1 Configure the proxies' Resolution and Format settings within the Project Settings. Here you'll likely want “Choose Automatically” paired with a low-bandwidth, edit-friendly codec such as ProRes LT or DNxHR LB. 2 In the Media Pool, select every source clip and run Generate Proxy. 3 Send a DaVinci Resolve Archive (.dra) out to an external drive, ticking Proxy Media by itself. 4 Head off. Back home, plug that drive into your home laptop and run the Restore Project Archive command in the Project Manager to pull in the archive. 5 Once you've wrapped your home session, export a timeline, bin, or project from the laptop and carry just that single file back to the edit suite to resume work against the original source media. A second common case involves shipping proxies over the internet to an editor in a different city or country. Here's how to dispatch a project to a fellow editor across the internet: 1 Configure the proxies' Resolution and Format settings within the Project Settings. Here you'll likely want a low resolution such as “quarter” or “one-eighth,” paired with a low-bandwidth, heavily compressed codec like H.265 to keep file sizes as tiny as possible. 2 In the Media Pool, select every source clip and run Generate Proxy. 3 Send out a DaVinci Resolve Archive (.dra), ticking Proxy Media by itself. 4 With your OS's file compression tools, zip the archive folder down into one big file. 5 Push the resulting .zip up to whichever online file sharing service you favor, and pass the download link to the remote editor. 6 After the other editor unzips and imports the archive, the two of you can then trade timelines, bins, and/or project files back and forth to work together. Such files run small enough to send over email or an instant messaging service. Beyond that, your editing computer may sit on ethernet wired to a Media Asset Management system capable of producing its own proxies. To edit fluidly across the network, you have to lean on low-bandwidth proxies rather than the source media. Here's how to build proxy media externally for editing across a local network: 1 Pull the original source media files into your Media Pool from whatever network storage system you're on. 2 Configure the proxy-generation settings in your Media Asset Management software to suit the amount of network bandwidth you expect to have on hand. 3 Confirm the proxies' timecode and frame rate line up with the original source media, then render the proxies to a network location. 4 Pick every one of your original source media files in the Media Pool, then choose “Link Proxy Media.” 5 Point it at the proxy media sitting at the network location where they were rendered.

### Proxy Media vs. Other Playback Optimizations in DaVinci Resolve

DaVinci Resolve still carries other ways to optimize real-time performance, so it's only natural to wonder how this stacks up against Optimized media, Timeline Proxy Mode, and the rest of the performance-optimization techniques DaVinci Resolve offers. What chiefly sets proxy media apart is that it stands on its own, travels freely, and, if you wish, can be produced by software outside DaVinci Resolve.

### Proxy Media vs. Timeline Proxy Mode

Among the earliest performance-optimization options, the one called “Proxy Mode” in earlier DaVinci Resolve releases was relabeled “Timeline Proxy Mode” as of DaVinci Resolve 17 to keep it distinct from Proxy Media. Where the newer Proxy Media feature writes genuine media files to disk, “Timeline Proxy Mode” merely drops the timeline's resolution on the fly to squeeze out better real-time playback. Make no mistake: Proxy Media and Timeline Proxy Mode are two altogether separate features, fully independent of each other.

### Proxy Media vs. the Render Cache

Proxy Media exists to put easy-to-edit primary source material onto the Timeline, lifting performance before you ever begin editing. The Render Cache exists to lift the real-time performance of clips weighed down by enough heavy effects (Resolve FX, color corrections, noise reduction, compound clips, fusion compositions, and so on) to bog playback down even at the current Timeline resolution. Proxy Media stands alone and travels freely (move clips wherever you please; you just relink them after), whereas Render Cache media was never meant to be moved or touched externally and serves only the project it was built for.

### Proxy Media vs. Optimized Media

At first glance, Proxy Media and Optimized Media seem to do much the same job. Each is built to turn out lower-bandwidth, easier-to-edit renditions of source media. Yet Optimized Media is handled internally by DaVinci Resolve, can't be exported, and stays out of the user's reach. Proxy Media, by contrast, produces wholly portable, independent media that the user can manage with ease.

### Using Optimized Media, Proxy Media, and Caching Together

Exactly how you combine DaVinci Resolve's assorted performance-boosting features is left up to you, but bear in mind they aren't an either/or choice. You could, for instance, generate optimized media from your project's camera raw original clips, then switch on Timeline Proxy Mode playback to lift the performance of your 4K timeline, and flip on Smart Cache to hurry your Color page work along as you pile Fusion effects, noise reduction, and Resolve FX or OFX onto every clip. Each of these optimization methods cooperates cleanly and seamlessly with the others to raise your performance while holding your project's image quality as high as the Optimized, Proxy, and Cache formats you've chosen in the Master Settings panel of the Project Settings allow.

### Which Playback Optimization Method Should I Use?

DaVinci Resolve's array of playback optimization features exists expressly to push performance higher and offset shortfalls in hardware, storage, and bandwidth, yet knowing the right moment to reach for each one is key to making them work properly. A quick reference follows below.

- Timeline Proxy Mode: My timeline plays, but the pace is just a touch sluggish.
- Cache Clip: A handful of my clips carry heavy effects and I'd like help running them back in real time.
- Optimized Media: I'd like help running all my source footage back in real time, and this is the only machine

I'll be cutting on.

- Proxy Media: I'd like help running all my source footage back in real time, plus I have to collaborate and pass this media around to other users, programs, or external storage spots.

### Other Project Settings That Improve Performance

On top of leaning on proxies, dropping raw decoding quality, building optimized media, and switching on the Smart and User caches, the Project Settings window offers five further options, and the User Preferences adds one more within its UI Settings panel, all of which you can call on to push real-time performance further on an underpowered machine, trading away some image quality as you work. You can then flip these settings back to their higher-quality modes ahead of rendering.

- Set timeline resolution to: (Master Project Settings, Timeline Format) Since DaVinci Resolve is resolution independent, you may switch the resolution whenever you like, and every window, track, sizing change, and piece of keyframe data is recomputed automatically to suit the new size. Dropping the Timeline resolution as you grade lifts real-time performance by cutting how much data gets processed, though you'll want to raise Timeline resolution back to the size you need before rendering. It amounts to much the same thing as the Proxy command, except here you pin down precisely which resolution you'd like to work at.
- Enable video field processing: (Master Project Settings, Timeline Format) Even on interlaced material, you may keep this option off to gain real-time performance. Once you're done, flip the setting back on ahead of rendering. Whether field processing truly needs to be on, though, hinges on the sort of corrections you're making. Should you apply any filtering or sizing such as blur, sharpen, pan, tilt, zoom, or rotate, then field processing ought to be on for rendering. Should you only be tweaking color and contrast, field processing isn't needed.
- Video bit depth: (Master Project Settings, Video Monitoring) Monitoring at 8-bit lifts real-time performance, at the risk of possibly bringing banding into the monitored image.
- Monitor scaling: (Master Project Settings, Video Monitoring) Lets you pick which transform filter handles scaling video to fit the Video format resolution you've set. The choices are Bilinear and Basic.
- Resize Filter: (Image Scaling) A drop-down menu through which you select a different image transform filter (Bilinear, say) that trades quality for being lighter on the processor. A “Force sizing highest quality” checkbox in the Deliver page's Render Settings list, however, helps guard against your final media getting rendered at this reduced-quality setting by accident.
- Hide UI overlays: (User Preferences, Playback Settings) Off by default. If a single GPU is handling both display and CUDA or OpenCL processing, or your display GPU is underpowered, or you don't have the PCIe bandwidth the current resolution or frame rate demands, switching this option on may win you better real-time performance. With it on, onscreen controls like the cursor, Power Window outlines, and split-screen views are turned off and hidden throughout playback. Pause playback and all onscreen controls return.
- Minimize interface updates during playback: (User Preferences, Playback Settings) On by default. With it on, this setting lifts real-time performance by tucking away the Viewer's on-screen controls (cursor, Power Window outlines, split-screen views among them) for the duration of playback. Stop playback and the onscreen controls return.
