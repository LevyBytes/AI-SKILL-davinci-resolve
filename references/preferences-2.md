# Preferences (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Although the images get processed at a reduced size compared with their originals, the viewing scales shown in the viewers continue to reference the original resolutions. On top of that, image processing carried out in Proxy Scale mode can vary a little from rendering at full resolution. You can adjust the Proxy and Auto Proxy size ratios straight from the interface by right-clicking the Prx and APrx buttons above the toolbar and picking the value you want from the contextual menu.

### GPU

Only Fusion Studio offers the GPU preference. Within DaVinci Resolve, GPU processing is set up through Resolve's Memory and GPU preferences. Inside Fusion Studio, the GPU preference defines which GPU acceleration method handles processing, according to your computer platform and what your hardware can do. It additionally governs enabling caching plus debugging of GPU devices and tools.

### Options

Among the GPU options are radio buttons that decide whether the GPU is engaged during processing and, when it is, which computer framework handles communication with the GPU.

- GPU Tools: Three settings exist for this preference: Auto, Disable, and Enable. With Disable chosen, tools and third-party plugins get no GPU acceleration, though Fuses might still call for it. Pick Enable and GPU acceleration becomes available to tools and plugins, provided the right drivers are present.

### The GPU preferences

- API: Which GPU processing method is applied is chosen by the API setting.
- Device: When several GPUs are present, the Device setting picks which GPU hardware gets used.

With the Auto setting, GPU processing takes precedence; should it be unavailable, however, Fusion falls back on the platform default. As things stand, both the AMD and CPU options need one of two installs present. The first is the driver named AMD Catalyst 10.10 Accelerated Parallel Processing (APP) technology Edition; the alternative is ATI Stream SDK 2.1 or a later version. The Select setting hands you explicit choice of the device.

### Debugging

The higher-level preferences housed in this section exist for diagnostics and for examining how the GPU is operating.

- Verbose Console Messages: Switching this on prints information to the Console — Startup Logs, Compiler Warnings, and Messages, for instance.
- OpenGL Sharing: Turning this on pools system RAM together with onboard GPU RAM, yielding a bigger yet slower OpenGL memory pool.
- Clear Cache Files: Choosing this wipes the GPU code that's already compiled, after which the kernels get recompiled.

### Layout

You'll find the Layout preferences only in Fusion Studio. To store a Layout from DaVinci Resolve's Fusion page, go through the Workspace > Layout Presets menu. The Layout options govern the arrangement, size, and placement of the assorted windows in Fusion's interface at startup or when a comp gets created.

The options are numerous, yet in practice you just arrange the interface however you like it at startup and as each new composition opens, then bring up this Preferences panel and press the three buttons to capture the Program Layout, the Document Layout, and the Window Settings.

### The Layout preferences

### Program Layout

The Program Layout serves to store the overall Fusion interface window together with any floating windows that are open. Every fresh composition you open inside the larger overall Fusion interface window will conform to these preferences.

- Grab Program Layout: Hitting this button records the application's current overall position and size.
- Run Mode: From this menu you set the application's default startup mode, choosing among a Maximized application window, a Minimized application, or a Normal application display.
- Use the Following Position and Size: When ticked, Fusion Studio launches using the values captured at the time Grab Program Layout was pressed.
- Create Floating Views: When ticked, the floating viewers' position and size get recorded whenever the Grab Program Layout button is used.

### Document Layout

What the Document Layout stores is the arrangement of panels and windows for the Fusion comp you're currently in.

- Recall Layout Saved In Composition: When ticked, loading a saved composition brings back every Document Layout setting from the controls beneath.
- Grab Document Layout: Hitting this button records the whole interface setup, taking in all the inner positions and sizes of panels and work areas.
- Window: When a single composition uses several windows, this menu picks which window the Window Settings will affect.

### Window Settings

Instead of storing whole comp layouts, the Window Settings let you store the position and size of individual floating windows and panels within a comp.

- Automatically Open This Window: When ticked, the chosen window opens on its own for new flows.
- Grab Window Layout: Hitting this button records the chosen window's size and position.
- Run Mode: Pick the default run mode for the chosen window. Your choices are a

Maximized window, a Minimized window, or a Normal window display.

- Use Grabbed Position and Size: When ticked, the chosen window is created from the

stored position and size.

### Loader

You'll find the Loader preferences only in Fusion Studio. The Loader preferences let you configure the default Loader's color depth and aspect ratio and also set up the local and network cache settings.

### The Loader preferences

### Defaults

In the Defaults section there are two settings that govern how color depth and aspect ratio get handled for Loaders.

- Loader Depth: How color bit depth is treated when you add a Loader is governed by the Loader Depth. Pick Format and the proper bit depth is chosen for you, drawn from the file format and the data in the file's header. Pick Default and the bit depth takes whatever value the Frame Format preferences specify.

### Cache

Through the Cache preferences you manage how disk caching behaves in Fusion. You decide how and where the cache gets built, the point at which it's purged, the way it responds when source files go missing, plus numerous other cache-related options. Don't mistake this for the RAM cache, which the Memory preferences govern.

- Disable All Local Caching: Local caching is switched off by this setting.
- Cache Files from Network DiskCaches: When a tool has disk caching turned on and its disk cache

files live remotely on the network, turning this option on draws on a local copy of those cache files, much as a networked Loader's local cache does.

- Enable Local Caching of Loaders: Files get copied into whichever LoaderCache path is set below or in the Path Maps preferences.
- Cache Multi-Frame Files: Formats such as AVI or QuickTime are copied into the LoaderCache path, which can take a while for a large file.
- Don't Cache Files from Local Disks: Anything not residing on a network drive stays out of the LoaderCache path. You might switch this off when, say, you keep a fast SSD cache drive and want it serving local files too, speeding up file access during interactive work.
- Only Files Smaller Than xxx MB.: Anything bigger than the value entered here won't be copied into the LoaderCache path.
- Cache Path Separator Character: With Enable Local Caching of Loaders turned on, this setting lets you reconstruct the path of the source files within LoaderCache.

As an example, with the default "!" character in place, the original path X\Project\MyShots\ Shot0815\ becomes X!Project!MyShots!Shot0815! inside the LoaderCache path. You may employ different separator characters, the "\" character among them, which makes LoaderCache use subdirectories: X\Project\ MyShots\Shot0815\.

- If Original File Is Missing: Three choices here dictate how caching behaves once the source files turn up missing. With the Fail option, behavior matches Fusion's Default Loader exactly: the Loader won't process, possibly stalling the render. The Load Cache option pulls in the cache despite no original file being there. The Delete Cache option strips missing files out of the cache.
- Cache Location: As a convenience, this duplicates the LoaderCache path defined in the Path Maps preferences.
- Explore: Pressing this opens the LoaderCache path within a macOS X Finder window or a Windows Explorer window.
- Clear All Cache Files: Pressing this erases every cached file sitting in the LoaderCache path.

### Memory

You'll find the Memory preferences only in Fusion Studio. When you want to govern Fusion's memory as you work on DaVinci Resolve's Fusion page, head to DaVinci Resolve's Memory and GPU preferences. From time to time you'll need to tweak the Memory preferences so the computer's available memory is used to best effect. As an illustration, some users favor a larger cache memory for snappier interactive work, but for final renders they often cut the cache memory back, freeing up more memory for processing tools simultaneously or rendering several frames at once.

### Caching Limits

Among the Caching Limits are options covering Fusion's RAM cache operation. This is where you decide how much RAM goes to the RAM cache for playing comps back in the viewer.

- Limit Caching To: With this slider you fix what percentage of available memory the interactive tool cache may use. Here, available memory means the quantity of memory installed in the computer. Once the interactive cache hits the limit this setting defines, it begins evicting lower-priority frames from the cache to make room for new ones.
- Automatically Adjust In Low Memory Situations: Ticking this checkbox makes the caching adapt whenever memory runs short. Any cache purges get reported in the console.
- Leave At Least X MBytes: Use this setting to fix the hard ceiling on memory usage. Whatever the Cache Limit happens to be set to, this setting reserves how much physical memory stays free for other applications to use. As a rule, keep this value at no less than 25 MBytes.

### The Memory preferences

### Interactive Render

The Interactive Render option lets you tune how Fusion processes based on how much RAM your system has installed.

- Simultaneous Branching: When ticked, several tools get processed concurrently. Clear this checkbox should you keep running short on memory.

### Final Render

These settings govern memory usage throughout a rendering session, whether preview or final, and have no bearing on an interactive session.

- Render Slider: This slider tunes how many frames render concurrently.
- Simultaneous Branching: When ticked, several branches of a node tree get

rendered concurrently. When memory is tight, switch this off to boost rendering performance.

### Network

You'll find the Network preferences only in Fusion Studio. Their purpose is to configure and manage network rendering within Fusion Studio. You'll come across most of the settings in the Render Manager dialog.

### The Network preferences

### Submit Network Render Compositions

Into these fields you type the Master Name and IP address of the computer set to handle every network render dispatched from this machine. When a standalone render master operates on the network, these fields might come pre-filled and locked against editing. The point is to stop each person at a facility from spawning multiple unauthorized render masters. To make the master name and IP editable again, create the environment variable FUSION* NO* MANAGER and set the value to True. Refer to your operating system user guide for instructions on creating environment variables.

### General

The General preferences put the most-used options up top within the General section. What these options establish is the role the system plays during network rendering.

- Make This Machine a Render Master: Once enabled, Fusion takes in network render compositions from other computers and oversees the render. That doesn't necessarily put this computer to work on the render itself; rather, it dispatches the job to the render nodes named in the Render Manager dialog.
- Allows This Machine to Be Used as a Network Slave: Once enabled, this computer can serve as a Render node and will take in compositions for network rendering. Untick it to keep others from sending compositions to render on this computer.
- Render on All Available Machines: Tick this checkbox to disregard the groups and priorities set up in the Render Manager. Any composition this computer submits for network rendering then goes out to every available slave.

### Email Notification

The Email Notification section is where you arrange who receives status updates about the render jobs and the network.

- Notify Options: Ticking these checkboxes triggers emails when particular render events occur. The events on offer are Queue Completion, Job Done, and Job Failure.
- Send Email to: Type the address or addresses that should receive notifications, separating several addresses with a semicolon.
- Override Sender Address: Type an email address to act as the sender address. Leave this option unticked and no sender address is applied, which can lead certain spam filters to block the message from reaching the recipient.

### Server Settings

Clustering and Network Rendering are dealt with in this section. For deeper coverage of these settings and of clustering, see the DaVinci Resolve Reference Manual's Chapter 66, "Rendering Using Saver Nodes," or the Fusion Reference Manual's Chapter 4.

### Path Maps

Path Maps are virtual paths that swap out portions of file paths for variables. As an example, you might define the path 'movie_x' as really residing in X\Shows\Movie_X. Following that example, Fusion would read the path 'movie_x\scene_5\ scan.000.cin' as actually pointing to X:\Shows\ Movie_X\scene_5\scan.000.cin. Within Fusion Studio, virtual path maps offer two principal benefits over literal file paths. The first is that you can readily alter the path to media tied to Loaders (say, when relocating a comp from one drive to another) without touching the composition at all. The second benefit comes during network rendering, where you can sidestep the differing OS filename conventions.

- Enable Reverse Mapping of Paths Preferences: You'll find this checkbox up at the top of the Path Map settings. With it enabled, Fusion draws on the built-in path maps for the path's settings entries as it maps existing filenames. Fusion Studio gains the most from this. Ticking the checkbox makes Loaders adopt paths relative to where the saved composition lives the moment they're dropped into the Node Editor.

For deeper coverage of using relative paths for Loaders, see the DaVinci Resolve Reference Manual's Chapter 105, "I/O Nodes," or the Fusion Reference Manual's Chapter 45.

### The Path Map preferences

Like the other preferences in Fusion Studio, path maps come in both Global and Composition flavors. Global preferences carry over to all new compositions, whereas Composition path maps are stored only with the composition at hand. A Composition path map will take precedence over a Global path map bearing the same name. The Global path maps break down into three sections:

- System Path Maps: System path maps are set by the operating system and lay out Fusion's global locations. Particular System path maps can be overridden through the Defaults or the current Composition Path Map settings. Should you later reconsider, the System path maps always let you revert to Fusion's "factory" defaults. The System Path Map settings put several top-level path maps in place.

AllData: Where Fusion stores every bit of shared application data. AllDocs: Where Fusion stores the public/shared document folder. AllLUTs: The nested LUTs path within the Defaults section, the spot Fusion uses to store LUTs. Fusion: Where the Fusion Studio app lives once installed. As an example, open Fusion from C:\Program Files\Fusion and the path Fusion:\Help points at C:\Program Files\Fusion\Help. Had you instead run a copy of Fusion located at \\post-server\fusion\16, then Fusion:\Help would resolve to \\post-server\fusion\16\Help. FusionLibs: The Fusion libraries the application relies on. Profile: Where the default Fusion preferences file gets stored. Profiles: Where Fusion keeps each individual user's preferences. Programs: Where Fusion Studio or DaVinci Resolve resides. SystemFonts: Where the OS keeps the fonts that show up for Text+ and Text 3D nodes. Temp: Points at the temporary folder belonging to the system. UserData: Where Fusion stores all the user-specific assorted roaming data. The Default Path Maps section enumerates the separate pieces making up that roaming data. On Windows with Fusion Studio, this is "C:\Users\username\AppData\Roaming\". Under Linux, it's "$HOME/Blackmagic/Fusion". Under macOS, it's "Users/UserName/Library/Application Support/Blackmagic Design/Fusion". UserDocs: Where Fusion keeps the user's document folders.

- Default Path Maps: The Defaults are path maps you can edit yourself. As part of their paths they may point at the System paths. For example, the Temp folder, defined in the System path, is drawn on by the Default DiskCache path map to pin down the nested location (Temp:DiskCache). Default path maps can likewise redirect paths without leaning on the Global System path maps. Once you alter a Default, the new setting becomes selectable in the Preferences window, and a Reset button at the foot of the Preferences window restores the changed setting to the System default.

AutoSaves: Fixes where the Fusion Comp AutoSave document goes, as configured in the Fusion General preferences. Bins: Fixes where Fusion Studio bins reside. Because bins hold pointers to the content, the content itself isn't stored with the bin; only the metadata and pointers go into the bins. Brushes: Directs Fusion to the folder holding custom paintbrushes. Comps: Where Fusion Studio compositions get stored. Under macOS or Windows, the default spot is Users/YourUserName/Documents/Blackmagic Design/Fusion. Config: Holds Configuration files that Fusion Studio uses while running. Defaults: Marks where node default settings sit so they can be brought back if overwritten. DiskCache: Fixes where files land on disk when the Cache to Disk feature is in use. The Cache to Disk window can override this location.

Edit templates: Where Fusion macros are kept so they turn up as templates inside the DaVinci Resolve Effects Library. Filters: Aims at a folder holding Convolution filters such as sharpen, usable by the Custom Filter node. Fonts: The default Fonts path map aims at the operating system fonts folders. Altering it shifts which fonts are on hand in the Text+ or Text 3D nodes, plus any Fusion Title Template. In DaVinci Resolve. This path map leaves untouched the five extra Edit page titles: L Lower 3rd, R Lower 3rd, plus M Lower 3rd, together with Scroll and the Text title. Fuses: Aims at a folder holding Fusion Fuses plugins. FusionTemplates: Where Fusion macros are kept so they appear as templates in Fusion's Effects Library. Guides: Where custom viewer guide overlays get stored. Help: Marks where Fusion Studio PDF files sit. Layouts: Where Fusion Studio custom window layouts are kept. Libraries: Aims at a support folder able to hold custom Effects Library items. LoaderCache: Fusion Studio's Loader preferences permit the Loader to cache while reading from a slow network. This path map aims at the local drive spot used for that cache. LuaModules: Where Lua Scripting modules reside. LUTs: Aims at a folder holding Look Up Tables (LUTs). Macros: Aims at the spot for user-created macros. Macros stored there show up in the Effects Library's macros category and in the right-click Edit Macro contextual menu. Plugins: Denotes user-specific OpenFX plugins you'd rather not have loaded for everyone. Previews: The path map serving the older-style, file sequence flipbook previews. Queues: Where the Render manager list lives. Scripts: Where Lua and Python scripts reside. This path can be narrowed further into particular scripts for tools (nodes), comps, and other specific script types. Settings: Where custom Node settings are kept. Stamps: Where preview movies built in a Fusion Studio bin go. This path map is now obsolete given that bins carry the Studio Player. Templates: Where the Templates folder sits. Saving Macros into the Template folder makes them appear in the Effects Library under a Templates category. Within Fusion Studio, that Templates category stays hidden until a Macros is saved into the folder. Thumbs: Where clip thumbnails built in a Fusion Studio bin go. A leftover path map by now, seeing as the Studio Player ships inside bins. UserPaths: Serves spots for studio- or facility-specific tools, such as custom plugins and scripts kept on a central server.

- User Path Maps: User paths are fresh paths you've defined that aren't already in the Defaults settings. Comp denotes the folder holding the current composition. As an example, keeping media folders alongside your Fusion Studio comp file lets Loaders rely on relative file paths rather than literal ones.

### Modifying a System Path Map

To change an existing System path map, pick the path map within the System section. Press the folder icon at the foot of the Preferences window, then type the path map's name into the From field below. Type the path map's value into the To: field.

### Modifying a Default Path Map

To change an existing Default path map, pick the path map within the Default section. Press the folder icon at the foot of the Preferences window, then type the path map's name into the From field below. Type the path map's value into the To: field.

### Creating a User Path Map

To build a path map, press the New button and type the path map's name into the From field below. Type the path map's value into the To: field.

### Deleting a Path Map

To remove a path map you created, choose it from the list and press the Delete button. System and Default path maps can't be removed; only the path maps a user created can be taken out of the Path Maps list.

### Nesting Path Maps

While defining a path map of your own, you may incorporate an existing path map into the new definition. As an example, define a path map named 'Episode' pointing to MyDrive\ Projects\Episode1. Then build new path maps named Renders and Stills pointing to Episode\ Renders_v1 and Episode\Stills_v1.

### Preview

Preview exists only in Fusion Studio. Within DaVinci Resolve, previews rely on the Scratch Disk setting found in the Media Storage preferences. The Preview preferences are where you set up the creation and playback options for preview renders.

### The Preview preferences

### Options

- Render Previews Using Proxy Scaling: When ticked, this option shrinks the images down to preview size for the Loader and Creator tools, which renders far quicker. Leave it off and frames render at full size before being scaled down.
- Skip Frames to Maintain Apparent Framerate: When ticked, frames get dropped while Flipbooks and file sequences play, holding the frame rate setting steady.
- Show Previews for Active Loaders: This setting decides whether the preview playback controls appear beneath the Inspector once a Loader carrying a valid file is activated.
- Show Previews for Active Savers: This setting decides whether the preview playback controls beneath the Inspector appear once a Saver carrying a valid file is activated.
- Display File Sequences On: This setting decides which viewer or external monitor handles the interactive and file sequence playbacks, plus the scrubbing function within the bins.

### QuickTime

The QuickTime preferences exist only in Fusion Studio on macOS. These settings establish the default QuickTime codec settings for when you choose QuickTime as the rendering file format in the Saver node.

### The QuickTime preferences
