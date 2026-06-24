# Using The Media Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using the Media Page

Within DaVinci Resolve, the Media page acts as the chief hub for bringing in media and arranging clips. It is likewise the spot where every timeline you cut in DaVinci Resolve or pull in from elsewhere gets arranged. Even though both timelines and clips live in the Media Pool, a core principle of how DaVinci Resolve operates is that a project's source media is kept apart from its timelines. That separation lets you handle and refresh the clips that timelines rely on without fuss — bringing clips in, rearranging them, flipping between offline and online media, and sorting out whatever issues crop up. The Media page also houses a great deal of the central machinery behind on-set workflows, along with the bulk of the functions involved in the ingest, organization, and sound-syncing steps tied to digital dailies workflows.

### Understanding the Media Page User Interface

Out of the box, the Media page splits into five separate regions, laid out to make finding, picking, and handling your project's media straightforward.

### The Media page

A large share of the functionality, and the majority of the commands, live inside the contextual menus that pop up when you right-click clips within the Media Storage browser or Media Pool.

### The Interface Toolbar

Running across the very top of the Media page sits a toolbar whose buttons reveal and conceal various pieces of the user interface. Listed from left to right, those buttons are:

### The Interface toolbar

- Media Storage full/half height button: Stretches the Media Storage browser to span your display's full height when you want extra browsing room, trading away a smaller Media Pool.
- Media Storage: Toggles the Media Storage browser between shown and hidden. Tucking the Media Storage browser away frees up additional space for the Viewer.
- Clone Tool: Reveals or conceals the Clone tool, which copies media off camera cards or hard drives.
- Audio Panel: Conceals or reveals the Audio Panel.
- Metadata: Conceals or reveals the Metadata Editor.
- Inspector: Conceals or reveals the Inspector Panels.
- Capture: Flips the Viewer and Audio Panel into Capture Mode, surfacing the controls needed

for cuing up a device-controllable deck, and batch recording from tape.

- Audio Panel/Metadata Editor full/half height button: Stretches the Audio Panel or Metadata

Editor to span your display's full height when you need extra room for either of those functions.

### Showing Which Panel Has Focus

Each time you click somewhere on the DaVinci Resolve interface with the pointer, or rely on a keyboard shortcut to “select” a given panel (as you might on the Edit page), you hand that panel of the user interface “focus.” A focused panel grabs particular keyboard shortcuts so they act inside that panel rather than somewhere else in the interface. Off by default, ticking the “Show focus indicators in the user interface” box within the UI Settings section of the User Preferences makes an orange highlight show along the top edge of the focused panel, helping you track which portion of the current page holds sway. You can shift focus as needed to accomplish whatever you set out to do.

Here the Focus indicator rides along the Media Pool's top edge, alongside a Viewer lacking focus

### The Media Storage Browser

Through the Media Storage browser you can view every volume hooked up to your workstation, scanning them for media you would like to preview and ultimately bring into your DaVinci Resolve project in some fashion. Where other applications lean on a kind of import dialog, DaVinci Resolve hands you the Media page for tackling involved media import tasks. So that media import goes smoothly, the Media Storage browser is split into two regions, the Volume List and the Media Browser.

### Media Storage browser with scrubbable clip view

### Playing Media in the Media Storage Browser

You can pick media in the Media Storage Browser and play it straight in the Media page Viewer, with no import needed, provided it sits in a format DaVinci Resolve handles. That comes in handy for previewing clips you are weighing for a project, and equally so for quality control review sessions of media you have exported out of DaVinci Resolve. Any clip played in the Media page Viewer is also sent out to video, assuming you have a supported Blackmagic output interface. You can additionally route the video to a second monitor by picking Workspace > Video Clean Feed and choosing your monitor. What's more, if you pick Workspace > Dual Screen > On, the second computer display can present a row of video scopes on the Media page, which can assist you in QC-ing a program you are delivering.

### Playing DCP and IMF Packages

The Media Storage Browser can likewise be used to pick and play DCP and IMF packages exported either through EasyDCP or through the native DCP/IMF export capabilities of DaVinci Resolve. Just track down the package, pick it, and play it in the Viewer as you would any other clip. It gets sent out to video and examined by the video scopes. DCP and IMF packages may also be brought in from Media Storage into the Media Pool for assorted workflows. For more information, see Chapter 188, “Delivering DCP and IMF.”

### The Media Storage Browser’s Volume List

Down the left side of the Media Storage browser runs a list of every volume presently reachable by your DaVinci Resolve workstation. Its purpose is to help you locate media you want to bring into your project by hand. Scratch volumes: Marked by a usage statistic to the right of the volume name reporting how full that volume is, these are the disks you have added in the Media Storage panel of the System Preferences window. The first of these scratch disks holds Gallery stills and cache files. Available volumes: Marked by disk icons, this lists every fixed, removable, and network volume currently reachable by your workstation. With the “Automatically display attached local and network storage locations” checkbox switched on in the Media Storage panel of the DaVinci Resolve Preferences, fresh volumes you attach to your workstation ought to surface in this list on their own. The list is hierarchical; clicking the disclosure triangle beside any volume reveals a further list of that volume's subdirectories, each carrying its own disclosure triangle. The Media Storage browser lets you burrow through as many subdirectories as you require.

### Adding Volumes That Don’t Appear in This List

Should you need to reach a storage volume that is absent from this list — for instance when you are running the version of DaVinci Resolve sold in the Apple App Store — you can right-click on any empty part of the Volume list's background and pick “Add New Location,” which brings up a dialog for choosing a volume to add.

When you are running the Apple App Store version of DaVinci Resolve, attached storage volumes are not auto-mounted by default. You can, however, switch it on within the DaVinci Resolve Preferences, over in the Media Storage panel. Further detail lives in the DaVinci Resolve Preferences section; consult Chapter 4, “System and User Preferences.” Media Storage Browser Favorites Below this lies the Favorites area. When there are particular directories you keep returning to, you can pin them to the Favorites so you avoid wading through tangled hierarchies every time you reach for the media you need. Customizing and working with the Favorites is straightforward. Ways to arrange favorite file system locations in the Media Storage Browser:

- To add a favorite: Within the Media Storage browser folder list, right-click whatever folder you want, then pick “Add folder to favorites” from the contextual menu. Your new favorite shows up at the bottom of the Favorites area.
- To open a favorite: Click any favorite to reveal that directory's contents inside the Media Storage browser.
- To remove a favorite: Right-click whichever favorite you want gone, and pick “Remove folder from favorites” from the contextual menu.

### The Media Storage Browser Area

After you have picked a volume or subdirectory in the Media Storage browser, you can take in its contents through List view, Thumbnail view, or Metadata view to dig through the media on hand as you hunt for what you need.

### List View

Within List view, these columns are on offer for sorting media before you bring it into the Media Pool:

- File name: The name of a file.
- Reel name: The reel name as it is presently derived per the Conform Options that are

currently chosen in the General Options panel of the Project Settings.

- Start TC: The first timecode value in the source media.
- Start: The first frame number in the source media.
- End: The last frame number in the source media.
- Frames: The duration of each clip in frames.
- Resolution: The frame size of the source media.
- Bit Depth: The bit depth of the source media.
- Video Codec: The codec used for the video track of supported media.
- Audio Codec: The codec used for the audio tracks of supported media.
- FPS: The frame rate of the source media.
- Audio Ch: The number of audio channels within the source media.
- Date Created: When the media file was created.
- Date Modified: When the media file was last altered and then saved.
- Shot: Additional metadata from media formats that support it.
- Scene: Additional metadata from media formats that support it.
- Take: Additional metadata from media formats that support it.
- Angle: Additional metadata from media formats that support it.
- Good Take: Additional metadata from media formats that support it.

Working in List view hands you extra organizational control by revealing columns that display the metadata each clip carries, before any media reaches your timeline. These columns help you arrange your media. Ways to tailor metadata columns within List view:

- To show or hide columns: Right-click atop any column in the Media Storage browser and pick an entry from the contextual menu list to tick or untick a given column. Unticked columns stay out of sight.
- To rearrange column order: Drag any column header left or right to reorder the columns.
- To resize any column: Drag the boundary between two columns rightward or leftward to make that column narrower or wider.
- To sort by any column: Click whichever column header you want to sort on. Every further click on that same header flips the column between ascending and descending sort order.

You can likewise tailor column layouts within the Media Storage area. After you have built a column layout suited to your particular purpose, you can store it for later recall. Ways to save and apply a custom column layout:

- To create a column layout: Reveal, hide, resize, and reorder the columns a given task calls for, then right-click any column header in the Media Pool and pick Create Column Layout. Type a name into the Create Column Layout dialog, and click OK.
- To recall a column layout: Within the Media Pool, right-click on a column header and choose the name of whichever column layout you wish to apply. Every custom column layout sits at the top of the list.
- To delete a column layout: Within the Media Pool, right-click on a column header, then from the Delete Column Layout submenu choose the name of whichever column layout you wish to discard.

### Thumbnail View

While in Thumbnail view, scrubbing across a clip's icon reveals its contents; you can additionally click the Clip Info drop-down menu tucked into the lower right corner of any clip's thumbnail for a quick rundown of that clip's key information, such as:

- File name: The name of that file.
- In timecode: The first frame in the source media.
- Out timecode: The last frame in the source media.
- Duration: The total duration of the source media.
- Resolution: The frame size of the source media.
- Frame Rate: The frame rate, in fps, of the source media.
- Pixel Aspect Ratio: The aspect ratio of the source media.
- Codec: Which codec is used by the source media.
- Date Created: The date created metadata from the source media file.
- Flags: Flag metadata applied either by the camera that shot the media,

in the Metadata Editor, or in the Color page Timeline.

Also while in Thumbnail view, the Thumbnail Sort drop-down menu (sitting between the Search and Option menu) lets you pick a criteria for arranging the thumbnails. A broad assortment of metadata options turns up, among them: File Name, Reel Name, Start TC, FPS, Audio Ch, etc. You can sort in ascending or descending order too.

### Revealing a Finder Location in the Media Browser

Should you drag a folder out of the macOS Finder and into the Media Storage browser, the Media Storage browser refreshes at once to display that folder's location.

### Viewer

Whatever clips you pick across any region of the Media page display their contents in the Viewer. Where the playhead currently sits shows up in the timecode field at the Viewer's upper right-hand corner.

### The Media page Viewer

Underneath the jog bar you will find basic transport controls: among them Jump to First Frame, then Play Backward, Stop, Play Forward, plus Jump to Last Frame. Sitting just left of those buttons, a jog control helps you crawl through a lengthy clip; click it and drag leftward or rightward to advance a clip one frame at a time. Clicking the speaker icon toggles audio playback on or off, while right-clicking that icon and dragging the slider sets the level. Over on the right side of the transport controls sit In and Out buttons, which mark In and Out points on the current clip. The clip's timecode is shown at the top right as well.

Directly below the image runs a jog or scrubber bar, letting you drag the playhead about with the pointer. The whole span of the jog bar stands for the clip's entire duration in the Viewer. You can skim footage in any viewer across the Media, Cut, Edit, Color, and Deliver pages by holding the C key down and sweeping the pointer back and forth in the viewer. The Media Viewer carries an option menu shaped like three dots in the upper right corner. Clicking that menu opens the options below.

An optional info bar that reports the timecode along with the duration of a media section you have marked Media Viewer Option menu: Holds the following commands:

- Live Media Preview: On by default, it lets thumbnails you skim in the Media Pool show the skimmed frame inside the Viewer. While you skim with Live Media Preview on, the playhead shown in the thumbnail stays tied to the playhead displayed in the Viewer's jog bar.
- Show All Video Frames: When the processing power on hand cannot play the clip or clips at the playhead position owing to the grade, transforms, or effects applied at that point in the Timeline, you get to decide exactly how DaVinci Resolve performance falls off. Turned off, DaVinci Resolve favors audio playback and drops video frames when processing power runs short, yielding a more conventional playback experience. Turned on, audio quality takes a hit while every video frame plays in slower-than-real time to hold playback together.
- Show Timecode Toolbar: The Timecode Toolbar displays the In/Out point timecodes along with the total duration set.
- Show Audio Waveforms in Source Clip: Once enabled, it lays an audio waveform overlay along the bottom of the Source Viewer that shows the audio across the clip's whole duration.
- Show Audio Waveforms Zoomed In: Once enabled, it lays an audio waveform overlay along the bottom of the Source Viewer showing a zoomed-in slice of the audio around the playhead's current position.
- Previous Clip: Jumps to the previous clip in the Media Pool.
- Next Clip: Jumps to the next clip in the Media Pool.
- Clear Recently Viewed Clips: Wipes the memory of recent clips in the Source Viewer.
- Show Marker Overlays: On by default, markers that meet the playhead while playback is paused appear overlaid in the Viewer.
- Markers submenu: Whenever one or more markers sit on the clip in the Source Viewer, they list here in chronological order by Name and Note. Picking a marker from this menu sends the playhead to that marker in the Source Viewer.

You can also drop the Viewer into Cinema Viewer mode by picking Workspace > Viewer Mode > Cinema Viewer (Command-F), so that it covers the whole screen. That command switches Cinema Viewer mode on and off.

### Export The Current Frame from The Viewer

Across the Media, Cut, and Edit pages, you can now push out a still frame from the Viewer. To Export a Still Frame from the Viewer: 1 With the Viewer’s playback controls, move to whichever frame you intend to export. 2 Select File > Export > Current Frame as Still. 3 Within the File System viewer, type a name for the still frame. 4 Within the File System viewer, set the format you want for the still frame. 5 Press the Export button.

### Live Media Preview

On by default, the Live Media Preview setting in the Viewer options menu (the three-dots menu at the Viewer's upper right-hand corner) lets thumbnails you skim within either the Media Storage browser or Media Pool show the skimmed frame inside the Viewer. While you skim with Live Media Preview on, the playhead shown in the thumbnail stays tied to the playhead displayed in the Viewer's jog bar. You can flip Live Media Preview on or off.

With Live Media Preview switched on via the Viewer options menu, thumbnail skimming is echoed in the Viewer

### Media Pool

The Media Pool sits at the heart of the DaVinci Resolve experience. It holds every piece of media you bring into the current project, along with all the timelines you build. It also holds whatever media gets imported alongside Projects, Timelines, or Compositions that have themselves been brought into DaVinci Resolve. On the Media page, the Media Pool is granted ample room, making it a fine place to sort, sift through, and arrange your project's clips. That said, the Media Pool is also mirrored across the Cut, Edit, Fusion, Color, and Fairlight pages, so you can reach clips while you assemble timelines, composites, grades, and sound design.

### Media Pool with the Bin list open

### The Bin List

Normally, every piece of media brought into a project lands in the Master bin, which always sits at the top of the Bin list and takes in everything across a given project. You can, however, add bins of your own, and the Media Pool can be arranged into as many user-definable bins as you wish, depending on what you need. Media moves freely from one bin to another right inside the Media Pool. When your project holds several bins, two approaches let you bring the bin structure into view: Bin list open: Found at the Media Pool's upper left-hand corner, the Bin List button opens a separate List view that shows every bin in your project, hierarchically. Bins holding other bins display a disclosure button to their left, which you use to reveal or hide the contents. With the Bin list surfaced, arranging clips across a large set of bins is easy. Bin list closed: Once the Bin list is shut, all bins vanish, and the contents of whichever bin is currently picked fill the Media Pool browser.

### Showing Bins in Separate Windows

When you right-click a bin in the Bin list, you can pick “Open As New Window” to throw that bin into a window of its own. Every such window is a Media Pool in its own right, with its own Bin, Power Bins and Smart Bins lists, plus display controls. This proves most handy when two displays are hooked up to your workstation, since, with DaVinci Resolve running in single screen mode, you can pull these separate bins over onto the second display. Hiding the Bin list not only buys you more room for clips, it also keeps you from accidentally flipping bins when all you really want is to view one particular bin's contents in that window. You can keep as many extra Bin windows open as you please, on top of the main Media Pool docked in the primary window interface.

### Media Pool bins opened as new windows

### Bins, Power Bins, and Smart Bins

In truth the Media Pool offers three sorts of bins, and each turns up in its own part of the Bin list. You can reveal or hide the Power Bin and Smart Bin regions of the Bin list through the Media Pool option menu by selecting or deselecting Show Smart Bins and Show Power Bins. Here is how the various kinds of bins differ: Bins: Plain, hand-filled bins. Drop whatever you like into a bin, and there it stays until you decide to shift it to another bin. Bins can be nested hierarchically, so you can build a Russian dolls stack of bins if you wish. Spawning new bins takes no more than a right-click inside the Bin list followed by picking Add Bin off the contextual menu. Power Bins: Off by default. They too are hand-filled bins, yet they get shared across every project sitting in your current project library, which makes them ideal for things like shared title generators, graphics movies plus stills, sound effects library files, music files, and whatever other media you want within quick, easy reach from any project. To build a new Power Bin, surface the Power Bins region of the Bin list, then right-click within it and pick Add Bin. Smart Bins: These bins fill themselves procedurally — that is, custom rules drawing on metadata dynamically sift through the Media Pool's contents the moment you pick a Smart Bin. That turns Smart Bins into fast ways to organize the contents of projects where you (or an assistant) have invested time tagging your clips with metadata through the Metadata Editor, supplying Scene, Shot, plus Take information, along with keywords, comments and description text, and a host of other details so that locating what you seek happens faster when the need arises. To build a new Smart Bin, surface the Smart Bin region of the Bin list (if it is not already shown), then right-click within it and pick Add Smart Bin. Up comes a dialog where you set that bin's name together with the filtering rules it applies to clips, then click Create Smart Bin.

### Filtering Bins Using Color Tags

When you are on a project loaded with bins, you can apply color tags to flag particular bins with one of eight colors. Tagging bins is as simple as right-clicking any bin and picking the color you want from the Color Tag submenu.

### Using Color Tags to identify bins

Using Color Tag filtering to isolate the blue bins

As an example, you might flag the bins holding the clips you reach for most often with a red tag. A bin's color tag then shows up as a colored backdrop behind that bin's name. Once one or more Media Pool bins carry tags, you can rely on the Color Tag Filter drop‑down menu — that drop-down control sitting just right of the Bin List button — to hide every bin save a single color. To return to seeing all available bins, pick Show All from the Color Tag Filter drop-down.

### Sorting the Bin List

The Media Pool's Bin list (and Smart Bin list) can be ordered, ascending or descending, by one of bin Name, Date Created, or Date Modified. Simply right-click somewhere inside the Bin list and, from the contextual menu's Sort by submenu, choose the options you are after. That same contextual menu also offers User Sort, which turns you loose to hand-drag every bin in the Bin list into any order you fancy. While you drag bins this way, an orange line marks where a bin will land once dropped. Should you use User Sort in the Bin list to reorder your bins manually, switching among the remaining sorting methods — Name, Date Created, Date Modified — and User Sort keeps your hand-set User Sort order intact, so leaning on whichever bin sorting method suits the moment costs you none of your customized bin organization.

Relocating a bin within the Bin list while User Sort mode is active

The Media Pool now lets you enable waveform thumbnails, which Live Media Preview can scrub.

### Thumbnail, List, and Metadata Views in the Media Pool
