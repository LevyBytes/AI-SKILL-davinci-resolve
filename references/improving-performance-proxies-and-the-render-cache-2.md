# Improving Performance Proxies And The Render Cache (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

In practice, this acts as a “pre-Color page” cache. Caching every processor-intensive clip in the Timeline brings you hugely better trimming and grading performance. That said, you can also flip the Fusion Output Cache on or off for individual clips, or for a batch of selected clips together. Doing so lets you flip between drawing on each clip's native source with live effects, or the cached clip held in the cache format you've picked. Where the Fusion Output Cache wins out over Optimized Media is that only clips actually used in a timeline get cached, which suits finishing workflows perfectly. Even so, the Smart and User caches do nothing to speed up work with source media in the Media Pool and Source Viewer right at the outset of an edit; handling that is the job of Optimized Media (covered in the previous section). Where Optimized media is on hand for a given clip, and “Use Optimized Media if available” sits on, then Optimized media steps in ahead of the Fusion Output Cache so long as no Speed effects or Fusion Effects ride on that particular clip.

### Second, Node Caching

The Node Cache stands as a level of caching apart from the Fusion Output Cache, and you can set it off in several different ways, each matching one of the three distinct purposes it covers.

- Switch the Smart Cache on and nodes carrying processor-intensive operations (together with every node sitting upstream within that grade’s node tree) get cached on their own, which means, say, with Nodes 1 and 2 cached, you can keep tweaking Nodes 3, 4, and 5 to your heart’s content without having to re-render your grade to the cache. Among the operations that set caching off are Noise Reduction, Motion Blur, and any Resolve FX or OFX plugin dropped onto a node. Should you have put a Resolve FX onto a node able to play in real time, yet that node still gets flagged for caching, you can force caching off for it by right-clicking the node and picking Node Cache > Off off the contextual menu.
- Any node can be forced to cache by hand where it and its upstream nodes are dragging performance down but somehow escaping automatic flagging, done by right-clicking a node and picking Node Cache > On off the contextual menu.
- You can likewise switch the “Render Cache Color Output” option on, applied to a clip you've placed in the Timeline on either the Edit or Color pages. That forces the clip’s whole grade to be cached by way of the Node Cache, right through to the Node tree’s output. The upshot can be higher real time performance over in the Edit page, at the cost of having to fully re-cache that clip any time you touch part of its grade.
- Should you apply Resolve FX or OFX filters to clips on the Edit page, these too get cached by way of the Node Cache. Which OFX gets cached is your call through the Render Cache OFX Filter submenu within the contextual menu for clips in the Timeline. That helps where a mix of realtime and non-realtime filters rides on a clip; caching only the non-realtime ones lets you carry on tuning realtime filters with no need to re-cache. Bear in mind, though, that altering a filter being cached on the Edit page timeline forces that clip’s grade to be re-cached over on the Color page, and the reverse holds too.

Where several nodes get flagged for caching within one node tree, each node ends up cached on its own. That way, you can flip a cached node off and on for a before-and-after look without having to re-cache the entire node tree. Where a clip belongs to a group on the Color page, a Group Cache can be switched on while you sit in the Group Pre-Clip and Group Post-Clip Node Editor modes; doing so caches those portions of a group grade as part of the Node Cache.

### Third, the Sequence Cache

The Sequence Cache stands as a separate cache for effects applied specifically within the Timeline on the Edit page. Counted among these are transitions, opacity adjustments, adjustment layers and composite mode superimpositions, along with clips carrying Speed or Retime effects. Sequence Cache effects can autocache across both the Smart and User caches.

### Choosing a Cache Format and Location

You pick the cache format yourself by opening the Master Settings panel of the Project Settings, then reaching for the “Render Cache Format” drop-down menu to land on whichever you want among these: ProRes, DNxHR, or the uncompressed 10- or 16-bit float uncompressed .dvcc formats. Picking a higher quality cache format secures high quality image playback, but leans harder on the throughput and size of your available disk storage. Conversely, picking a more heavily compressed cache format opens real time playback up to weaker computers with slower and smaller storage, at the cost of slightly dented image quality. The smart move is to settle on the highest quality cache format your workstation’s storage can carry. Whatever format you land on by way of the “Render Cache Format” menu decides one thing: does image data lying out of bounds — “super white” or HDR strength highlights among it — survive once the signal is cached? Within this menu, formats ending in “– HDR” keep out-of-bounds image data, whereas formats that don't, wont. Should you notice image data (typically bright highlights) getting clipped after caching or optimizing, switch over to 16-bit float, ProRes 4444, ProRes 4444 XQ, or DNxHR 444; any of those codecs in particular suit HDR grading. As for where cache files go, that defaults to whichever volume you first add to the Scratch Disks list, found in the Media Storage panel within the System Preferences. Where no scratch disk gets named, your System disk steps in, which may bring capacity and/or performance trouble depending on the size and type of System disk you're on, plus the media format you elect to cache to. For that reason, it's almost always wise to point your first scratch disk at the largest, fastest storage volume your workstation can reach.

### When Caching Happens

While caching is on, cache indicators running along the bottom of the Timeline Ruler of the Edit page timeline report the state of the cache. Red stands for “to be cached,” while blue stands for “has been cached.”

Source, Clip, and Sequence Cache bars as they appear within the Edit page's Timeline; the red ones mark stretches still awaiting caching, while the blue ones mark stretches already cached Over on the Color page, cache indicators run node by node, marking the node in your grading node tree (every upstream node included) at which caching will occur.

Node Cache indicator showing up as a red-tinted node number, here on node two within the Color page's Node Editor

Two routes lead to caching. First, while either Smart or User caching is on, caching always fires whenever you play clips bearing red caching indicators. Second, where background caching sits on in the Project settings (on by default), and you leave your project untouched for a user-definable number of seconds (tunable over in the Master Settings panel of the Project Settings), caching kicks off on its own through stretches of user inactivity. So take that as your cue to grab those coffee, mate, or tea breaks; DaVinci Resolve will carry on working in your stead.

### The Difference Between the Smart Cache and User Cache Modes

The Smart Cache option of the Render Cache submenu hands you the simplest experience when you'd rather “set it and forget it.” Picking Smart fires off an assortment of automatic caching behaviors built to sharpen DaVinci Resolve playback; it does so by rendering whatever clip formats, timeline effects, and grading operations are known to tax performance, while still letting you flag by hand clips you'd like cached that the Smart Cache passed over. The User Cache, by contrast, does not on its own cache clips in processor-intensive formats, making it a solid pick when your workstation can play every media format you're running in real time. As a rule, the User cache leans on you to govern what gets cached and what doesn't by flagging specific clips and effects by hand. The Master Settings panel of the Project Settings does, however, hold three options you can switch on so that, with User Cache mode active, Fusion Effects, composites, and transitions get cached on their own (you'll find these options in the Optimized Media and Render Cache group). Of those settings, only “Automatically cache Fusion Effects in User Mode” sits on by default. What follows lays out the differences between the Smart and User cache modes for each kind of caching DaVinci Resolve performs.

### Fusion Output Caching

- In Smart mode: Take every clip whose “Render Cache Fusion Output” reads either Auto (the default) or On; for those, three kinds of effects get rendered. First, H.264, H.265, DCP, JPEG2K, or camera raw clips edited into a timeline get cached. Camera Raw clips get cached using the currently chosen project or clip debayer settings. Second, Speed effects get cached at the source level, which makes shifting cached speed effects clips around the Timeline possible without having to re‑cache them. Last, Fusion Clips or clips carrying Fusion Effects get cached too, and clips flagged by hand likewise get cached in Smart mode.
- In User mode: Clips with Render Cache Fusion Output set to On get cached, while clips set to Auto get skipped, save for clips carrying Fusion Effects, which cache on their own in Auto mode once the “Automatically cache Fusion Effects in User Mode” Project Setting is on.

### Caching Specific Nodes in the Color Page

- In Smart mode: On its own DaVinci Resolve caches every node that uses Motion Blur, Noise Reduction, or Resolve FX and OFX plugins. Nodes flagged by hand also get cached in Smart mode.
- In User mode: DaVinci Resolve caches only nodes flagged by hand, done by rightclicking them and picking Node Cache > On to force that node to cache in User mode, together with every upstream node to the left of them.

Cache Color Output Is Actually Node Caching for the Whole Grade

- In Smart mode: Clips flagged by hand with Render Cache Color Output switched on cache the entire output of the Color page node graph, in effect caching that clip’s whole grade. This pays off most where you want sharper trimming and playback performance over on the Edit page. Flagging a clip for caching also brings about caching of EVERY SINGLE VERSION tied to that clip as well.
- In User mode: Clips flagged by hand with Render Cache Color Output switched on likewise cache the entire output of the Color page node graph.

Within the Edit Page, Caching of Resolve FX and OFX Counts as Node Caching Too When such filters ride on clips over in the Edit page, their caching can be set by hand only, whether you sit in Smart or User mode. Cached are only those filters you've flagged by right-clicking the clip they ride on and picking them in the Render Cache OFX Filter submenu.

### Sequence Caching

- In Smart mode: On its own DaVinci Resolve caches every superimposed clip riding a composite mode that isn't “Normal,” every transition, plus any clips bearing opacity or speed effects. Clips can't be flagged by hand for Sequence caching.
- In User mode: Where you've switched User mode on and discover your workstation lacks the muscle to play composite and opacity effects on the Edit page, you can force these classes of effects to cache on their own while in User mode; a set checkboxes does it, sitting in the Optimized Media and Render Cache section under the Master Settings of the Project Settings. Once those options are on, you also pick up the means to keep specific tracks out of caching, by right-clicking the track header of any video track you'd like excluded from caching and picking Exclude track from caching. Keeping a whole track out of caching offers a tidy way to stop a track packed with effects that already play in real time on your workstation, a track of titles for instance, from burning time and storage by being cached where there's no need.

### Manually Controlling the Cache

This section walks through how to govern by hand each kind of caching that is manually controllable in DaVinci Resolve.

### Controlling Fusion Output Caching

You can govern by hand which clips in the Timeline get cached and which don't. Pick a clip or several, whether from the Edit page's Timeline or the Color page's Thumbnail Timeline, then right-click one of those chosen clips or thumbnails and pick an option off the Render Cache Fusion Output submenu. Three options are on offer:

- Auto: The clip caches in Smart mode only where it's a format earmarked for caching or where a speed effect rides on it. The clip caches in User Mode only where “Automatically cache transitions in User Mode” sits on.
- On: The clip caches in either Smart or User mode, whatever format or effects ride on it.
- Off: The clip won't cache at all, under either Smart or User modes.

### Controlling Node Caching

You can govern by hand which nodes in a grade get cached and which don't. Right-click any node in a node tree, then pick an option off the Node Cache submenu. Three options are on offer:

- Auto: The flagged node and every upstream node cache in Smart mode only where it holds an operation earmarked for caching.
- On: The node always caches in either Smart or User mode, whatever operations it carries out.
- Off: The node won't cache, under either Smart or User modes. That lets you keep nodes out of caching in Smart mode where they manage real time operation on your system.

### Controlling Color Output Caching

Every clip in the Timeline (Adjustment clips included) carries a Color Output setting you can flip on or off: over on the Edit page, right-click the clip where it sits in the Timeline and pick Render Cache Color Output off the contextual menu. A check mark marks when this setting sits on.

### Controlling Edit Page Filter Caching

You can pick which of the Resolve FX or OFX filters riding on a particular clip ought to be cached: over on the Edit page, right-click the clip where it sits in the Timeline, then pick which of the filters in the Render Cache OFX Filter submenu you'd like cached. Each filter riding on that clip turns up in this submenu in the order it rides on the clip, and you can flip the caching of specific filters on and off (chosen filters show with a check mark to the left of their menu item).

### Using Cached Media When Rendering in the Deliver Page

Over on the Deliver page, within the Render Settings, the Video panel holds a “More options” section, and there the “Use Render Cached Images” option lets you write media straight from the cache, rather than re‑rendering the effects from the ground up, to save rendering time as you output your project. Should you intend to lean on this option, it's wise to set the cache format to a suitably high-quality format so as to secure the best results.

### Clearing Cached Media

Each project’s cache sticks around; the cache is held for later use even once the project gets closed and reopened down the road. Should you need to wipe a project’s cache to win back space on a storage volume, three options sit in the Delete Render Cache submenu:

- All: Wiping all media in the cache lets you reset every single cached clip.
- Unused: You can opt to wipe only Unused cache clips that no longer line up with clips or

effects in the Timeline.

- Selected clips: You can make a hand-picked selection of clips in the Timeline, then wipe the cache

tied to just those clips. To clear a project’s cache: with the project open, pick Playback > Delete Render Cache > All, Unused, or Selected Clips.

### The Cache Manager

There's an advanced render cache management window on hand to help you readily eye the size of, and tend, your cache data across various projects spanning all your project libraries. You reach this cache manager from Playback > Manage Render Cache. The Cache Manager window hooks into the Project Manager, letting you pick cached media from any library your system can reach, not merely the current project library. Here's what the Cache Manager does: Location: Through this drop-down menu you settle which type of project library to connect to. The choices are: Local, Network, Cloud, and All. Project Library: Through this drop-down menus you settle which project library's projects you want to tend. It lists every project library in the chosen Location, and you can pick one for management. You can also pick All to surface every project library in that location. Project: The main window lays out every project in the Project Libraries chosen above. It's broken into sortable columns by Location, Project Library, Project Name, and Render Cache. Tick the box in the Render Cache column to mark any projects whose cache you'd like to wipe. Clear Selected Cache: Press this button to wipe the Cache for all the marked projects. At the time of writing this function offers neither a warning dialog nor an undo, so be sure you've marked the right caches for deletion. Close: Shuts the Cache Manager.

### The Cache Manager

### Automatic Cache Deletion

A User Preference lets you wipe your local cache on its own after a set number of days, keeping your drive from clogging up with older projects. You'll find it at DaVinci Resolve > Preferences > User > Cache Management > Delete cache older than xx days. Tick the box to wipe on their own any cache files older than the number of days entered in the field. Tending these files by hand stays open to you from the Playback > Manage Render Cache menu, yet this new preference lets you arrange a cleanup operation and forget it.

### Using Proxy Media

DaVinci Resolve carries a Proxy Media workflow that supplies a playback optimization option, easing the trade of projects online, work on projects from afar, and work alongside external media asset management systems. It builds a plain yet flexible system for editing collaboration that you can tailor to your specific requirements.

### Creating and Using Proxy Media

Proxy Media boils down to more heavily compressed (and possibly lower resolution) renditions of your source media, tied to your source media in DaVinci Resolve through metadata. It's done so that flipping back and forth between the original and proxy media as your needs dictate stays easy. As a rule this lets you lean on lower bandwidth proxy media for stronger real-time effects performance and full speed playback while editing, then readily return to source media — heavier on bandwidth and the processor — once you reach color correction, finishing, and final output. Beyond delivering better performance, these proxy files are wholly portable, which lets you shift your entire project with ease from workstation to workstation, even across the internet, alongside far more compact proxy media. Your proxies' resolution and format get fixed over in the Optimized Media and Render Cache section, which lives in the Master Settings panel under the Project Settings. Two settings govern the actual media files turned out by the Generate Proxy Media command. Proxy Media Resolution: Pick “Original” to keep proxies at the same resolution as the source media. Should you prefer, trim the resolution of the proxy media files by picking Half, Quarter, Eighth, or Sixteenth to spare bandwidth. The “Choose Automatically” option weighs visual quality against efficiency by trimming the resolution only of media files larger than the currently chosen Timeline resolution, applying whatever reduction ratio best fits the Timeline resolution. Proxy Media Format: Lets you pick the specific QuickTime format and codec your proxy files come out in. Several ProRes and DNxHR varieties are there to pick from, plus H.264 and H.265 options. Whichever format you pick comes down to the bandwidth and quality tradeoffs a particular project calls for. Say you merely want better playback speed off RAW media while holding image quality; you might lean toward a high‑quality codec like ProRes 422 HQ, or DNxHR HQX. Where your aim is shipping your media over the internet to another editor, a more compressed format might suit — ProRes Proxy, say, or even H.264 or H.265 — so that file sizes stay small.

### The Proxy Media Resolution and Format settings

To generate proxy media in DaVinci Resolve: 1 Within the Media Pool, select every clip for which you'd like proxies built. 2 Right-Click any chosen clip and pick “Generate Proxy Media” off the contextual menu. DaVinci Resolve will throw up a progress bar and hand you a time estimate for completion as it renders your chosen clips out to the format and codec set by the Proxy Media Resolution and Format settings. NOTE: Where, inside the Media Pool, a separate audio file sits synced to your source clip, whatever proxies come out of that clip will carry the synced audio, though that audio rides embedded within the video clip rather than emerging as a separate file.

### Where is Proxy Media Saved?

Proxy media gets created at the “Proxy generation location” destination; you'll come across it in the Working Folders section, sitting under the Master Settings of the Project Settings. The proxies then get sorted further into subfolders by original source clip location. Holding enough free space on this drive to fit the proxies matters. Once made, these proxy files can be shifted to any other drive location on the system, should you wish, then re-linked to their source files. This location can be overridden: tweak the Proxy Generation Location options, which sit among the Media Storage settings within the DaVinci Resolve Preferences.

### Proxy Handling Display

Across both the Media Pool and the Timeline, down in the lower left corner of a clip, a proxy status icon can be found. That icon shifts to tell you precisely which kind of media DaVinci Resolve is drawing on at the moment.

### The Proxy Only icon

Purple PXY Only: This icon flags that only proxy media is on hand; the camera original media has gone missing.

### The Proxy Preferred icon

Purple PXY over a White Background: This icon flags that both camera originals and proxy media for this clip are present, and that proxy media is the one in use.

### The Camera Original Preferred icon

White HQ over a Purple Background: This icon flags that both camera originals and proxy media for this clip are present, and that original media is the one in use.

### The Camera Original with no icon

No Icon: An absent icon means proxy workflow has been switched off, and every bit of media is Camera Original.

You can pick which media you'd rather use through the Proxy Handling selector, sitting at the Viewer's upper right. Being a global setting, it shifts proxy handling for all the viewers across DaVinci Resolve.

Through the Proxy Handling Selector found in the Viewer you settle which kind of media to draw on.

### Creating Proxy Files with the Blackmagic Proxy Generator

The Blackmagic Proxy Generator stands as a separate program able to turn out proxy media on its own from master video files dropped into a watch folder. It's a small, lightweight application you can leave running in the background while bringing media in. That frees your DaVinci Resolve program up for more creative tasks while the proxies get generated.

### Using Watch Folders
