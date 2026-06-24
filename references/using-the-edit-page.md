# Using The Edit Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using the Edit Page

This chapter walks you through using and setting up the Edit page user interface so you’re ready to edit projects in DaVinci Resolve. To learn how the Edit page handles importing and conforming projects cut in other applications for color correction and finishing inside DaVinci Resolve, turn to Chapter 56, “Conforming and Relinking Clips.”

### The Edit Page User Interface

Over time the Edit page has grown into a source-record style NLE packing nearly every editorial tool you’ll want, from creative editing all the way through finishing. Three main regions make up the Edit page: the browsers along the left, the Viewers up top, and the Timeline down at the bottom. Together they let you import, edit, and trim timelines using a flexible range of tools and methods.

### The Edit Page in its entirety

### The Interface Toolbar

Running across the very top of the Edit page is a toolbar whose buttons reveal and conceal different parts of the user interface. Taken in order from the left: The Interface toolbar. Media Pool/Effects Library/Edit Index height button — this lets the area occupied by the Media Pool, Effects Library, and/or Edit Index stretch to your display’s full height (two can show at a time), handing you more browsing room while the timeline narrows. At half height, the Media Pool/Effects Library/Edit Index stay pinned to the top of the UI (only one shows at a time) and the timeline spans your display’s full width. Media Pool: Reveals or conceals a scaled-down version of the full Media Pool page, opening access to every video clip, audio clip, and image used in the project. Effects Library: Reveals or conceals the repository holding all the transitions, generators, OpenFX, and audio filters you can put to use on the Edit page.

Index: Reveals or conceals the Edit, Tracks, and Markers indexes. Sound Library: Reveals or conceals the libraries of sound effects and music registered with DaVinci Resolve. To learn more about working with the Sound Library, turn to Chapter 170, “Using the Fairlight Page.”

Keyframes: Brings up the Keyframes and Curves Editor. Quick Export: Brings up the Quick Export Dialog for delivering an export of your timeline straightforwardly. Mixer: Reveals or conceals the Audio Mixer, handing you graphical controls for tweaking your sound mix. Metadata: Reveals or conceals the Metadata Editor. Inspector: Reveals or conceals the Inspector, which lays out the transform and compositing effects on selected clips, or the editable options of selected effects like transitions or generators.

### Navigating the Edit Page

Every panel in the Edit page user interface can be handed focus through the Workspace > Active Panel Selection submenu. On top of that, the keyboard shortcuts below assign focus to a range of targets — select bins and clips, the Source and Timeline Viewers, plus the Timeline, the Effects Library, Edit Index, and Inspector.

Key Command-1 Command-2 Command-3 Command-4 Command-5 Command-6 Command-7 Command-8 Command-9 Q

Function — taking each key in turn: Media Folders, then Media Clips, next the Source Viewer, after that the Timeline, followed by the Timeline Viewer, then Effects, then the Edit Index, with n/a next, the Inspector after that, and finally Q, which performs Toggle between Source and Timeline Viewers

### Showing Which Panel Has Focus

Each panel you work in carries “focus,” which means that clicking an item or control inside a given panel turns it into the active panel and routes the keyboard shortcuts shared across many panels to the one you’re working in. To see which panel currently holds focus, switch on the “Show focus indicators in the User Interface” checkbox within the UI Settings panel of the User Preferences. Once it’s on, a red line across the top of the active panel signals that it has focus.

The focus indicator shown along the top edge of the Media Pool, sitting beside a viewer that lacks focus.

### The Media Pool

On the Edit page, the Media Pool holds every piece of video, audio, and still image media you’ve imported to edit into the project at hand, plus all the timelines you’ll be editing into. The Media Pool is mirrored across the Media, Cut, Fusion, Color, and Fairlight pages as well, letting you reach any audio or video clip, graphic, or timeline from whatever page they can be used on.

### The Media Pool in Thumbnail mode

The Bin list along the left presents a hierarchical list of bins for organizing your media, and it organizes your timelines too. The Media Pool starts out with one bin, named “Master,” yet you can add as many further bins as you need to sort timelines and clips by right-clicking anywhere

in the Media Pool’s empty area and picking Add Bin. To rename a custom bin, double-click its name and type a new one, or right-click the bin’s name and pick Rename Bin. Up in the Edit page toolbar’s upper left-hand corner, a button reveals or conceals the Bin list. Off to the right, the browser area displays the contents of whichever folder is selected. Each timeline you build, and each AAF, XML, or EDL file you bring in, turns up here. Within a single project you can build or import however many timelines you require. Just as on the Media page, the Media Pool can appear in Metadata, Icon, or List view. List view lets you sort the contents by any one of a subset of the full metadata available in the Metadata Editor of the Media page. Editors will find particular value in the columns covering Name and Reel Name, the various timecode streams, then Description, Comments, Keyword, Shot, Scene, Take, Angle, and Circled — followed by Start KeyKode, Flags, Usage, Resolution, and Frames Per Second. To learn more about the Media Pool’s many features, turn to Chapter 18, “Adding and Organizing Media with the Media Pool.” The sections coming up summarize a few key Media Pool features for your convenience.

### Importing Media Into the Media Pool on the Edit Page

Adding clips to the Media Pool over on the Media page gives you the richest organizational flexibility and feature set, but when you’re sitting on the Edit, Cut, Fusion, Color, or Fairlight page and need a few clips imported quickly for immediate use, a couple of routes are open to you. To add media by dragging clips out of the Finder onto the Edit page Media Pool (macOS only): 1 Pick one or more clips in the Finder. 2 Drag them into the Media Pool of DaVinci Resolve, or onto a bin in the Bin list. Those clips join your project’s Media Pool. To lean on the Import Media command found in the Media Pool of the Edit page: 1 Having opened the Edit page, right-click in the Media Pool anywhere and pick Import Media. 2 In the Import dialog, pick one or more clips to bring in and click Open. Those clips join your project’s Media Pool. To learn more about the Media Pool’s many features, turn to Chapter 18, “Adding and Organizing Media with the Media Pool.” Below, a few key Media Pool features are summarized for your convenience.

### Bins, Power Bins, and Smart Bins

The Media Pool actually holds three kinds of bins, each one occupying its own section of the Bin list. You can reveal or conceal the Power Bin and Smart Bin areas of the Bin list by ticking or unticking Show Smart Bins and Show Power Bins in the Media Pool option menu. Here’s how the bin kinds differ:

Bins: Plain, manually populated bins. Drag and drop whatever you want into a bin, and there it stays until you choose to move it to another. Bins can be nested hierarchically, so you’re free to build a Russian-dolls nest of bins. Making new bins is as simple as right-clicking within the bin list and, from the contextual menu, picking Add Bin. Power Bins: These stay hidden by default. They too are manually populated bins, yet they’re shared across every project in your current project library, which makes them perfect for shared title generators, for graphics movies and stills, for sound effects library files, for music files, and for other media you want to reach quickly and easily from any project. To make a new Power Bin, reveal the Power Bins area of the Bin list, then right-click inside it and pick Add Bin. Smart Bins: These are procedurally populated bins, meaning custom rules built on metadata dynamically filter the Media Pool’s contents each time you select a Smart Bin. That turns Smart Bins into quick ways of organizing projects for which you (or an assistant) has invested the time to attach metadata to your clips through the Metadata Editor — supplying Scene, Shot, and Take information, along with keywords, comments and description text, plus countless other details that speed up finding what you’re after when you need it. To make a new Smart Bin, reveal the Smart Bin area of the Bin list (if it isn’t showing), then right-click inside it and pick Add Smart Bin. A dialog opens where you can edit that bin’s name and the rules it applies to filter clips, then click Create Smart Bin.

### Showing Bins in Separate Windows

Right-clicking a bin in the Bin List lets you pick “Open As New Window” to break that bin out into a window of its own. Every such window is a Media Pool in its own right; it carries a Bin List of its own, the Power Bins and Smart Bins lists, plus its own display controls.

### Media Pool bins opened as new windows

This pays off most when two displays hang off your workstation, since you can drag these separate bins onto the second display while DaVinci Resolve runs in single screen mode. Hiding the Bin list not only frees up more room for clips, it also keeps you from accidentally switching bins when all you want is to view one particular bin’s contents in that window. You may keep as many extra Bin windows open as you like, on top of the main Media Pool docked in the primary window interface.

### Filtering Bins Using Color Tags

When a project carries a great many bins, color tags let you mark particular bins with one of eight colors. Tagging a bin is as easy as right-clicking it and picking the color you want from the Color Tag submenu. You might, say, mark the bins holding the clips you reach for most often with a red tag. A bin’s color tag then shows up as a colored background behind that bin’s name. After you’ve tagged one or more Media Pool bins, the Color Tag Filter drop-down menu (the drop-down control just right of the Bin List button) filters away every bin but a single color. To return to seeing all the bins on hand, pick Show All from the Color Tag Filter drop-down.

### Using Color Tags to identify bins

Using color tag filtering to isolate the red bins

### Sorting the Bin List

The Media Pool’s Bin list (and Smart Bin list) can be sorted by Bin Name, Date Created, or Date Modified, ascending or descending. Just right-click anywhere within the Bin list and, from the contextual menu’s Sort by submenu, pick the options you want. That same contextual menu also offers User Sort, which lets you drag every bin in the Bin list by hand into whatever order suits you. While you drag bins in this mode, a highlighted line shows the new position a bin will take when you drop it. Once you’ve used User Sort in the Bin list to arrange your bins by hand, you can flip back and forth among the remaining sorting methods — Name, Date Created, Date Modified — and User Sort, with your manual User Sort order preserved, so you can lean on whichever bin-sorting method serves you best at the moment without losing your custom bin organization.

Within User Sort mode, dragging a bin into a fresh spot in the Bin list.

### More About Timelines and Grading

A DaVinci Resolve project holds one or more edited timelines (other applications sometimes call these a sequence), which are organized in the Media Pool as well and presented in the Timeline Editor (known as “the Timeline”). Timelines are made of clips whose source media lives in the Media Pool, and those clips also turn up as edit events in the Edit Index that you can surface at the right of the Timeline.

### Timelines, Grades, and Versions

Inside any given timeline, grades are tied to the timecode of the source clip they sit on. So as you reshape the timeline, each clip’s grade travels with it, which makes shuttling between editing and grading as your needs dictate remarkably easy. By default, every timeline in a project keeps its own independent grades through local versions; that holds even when your timelines are duplicates. In other words, each clip in every timeline carries a wholly independent grade. Switch the clips in one or more timelines over to Remote versions, though, and a clip’s grades become shared by every instance of that clip across all timelines whose clips likewise use Remote versions. Import a new timeline that reshuffles clips into a different order and set it to Remote versions, and grades follow the clips automatically, so the clips in each new timeline inherit the grades applied to those same clips in other timelines. You can flip a timeline between Local and Remote grades whenever you wish. To learn more about Local versus Remote versions, turn to Chapter 142, “Grade Management.” You can also carry grades from one timeline to another with the ColorTrace feature. For more on ColorTrace, turn to Chapter 149, “Copying and Importing Grades Using ColorTrace.”

### Enabling the Use of a Master Timeline

Earlier releases of DaVinci Resolve carried a Master Timeline — one long timeline holding every clip in the Media Pool, arranged by default in ascending timecode order. The Master Timeline served a range of tasks, but architectural improvements have made it unnecessary, so by default it doesn’t show up in new projects created under DaVinci Resolve version 10 or later. Even so, if you want a Master Timeline to keep a single timeline that always contains every clip currently in the Media Pool, there’s a way to create one. You have to do it the instant you create a new project, before any media goes into the Media Pool. Once one or more clips land in the Media Pool, the option you need turns disabled. To build a fresh Master Timeline: 1 Start a new project; open the General Options panel within the Project Settings; then switch on the “Automatically match master timeline with media pool” checkbox. If you’d also like all clips to default to Remote versions as you grade, the way earlier DaVinci Resolve releases did, switch off the “Use local version for new clips in timeline.”

The option to use a Master Timeline lives in the Color section, itself part of the General Options panel within the Project Settings. 2 Click Save to dismiss the Project Settings window. 3 Head to the Edit page and choose File > New Timeline (Command-N). 4 As the New Timeline Properties window comes up, switch the Empty Timeline checkbox off, then click Create New Timeline. Now, alongside the new timeline, a Master Timeline shows up in the Timeline list. TIP: To guarantee you always get a Master Timeline whenever you create new projects, you can edit the Project Setting preset for your user account to carry these settings, or build a fresh Project Setting preset with these settings that you can switch to with ease.

The Master Timeline is one long sequence gathering every clip in the Media Pool, laid out in ascending timecode order. Each clip in the Master Timeline shows at its full duration, no matter the duration of the matching clips in an EDL-, AAF-, or XML-imported timeline. Any time you add more clips to the Media Pool, they join the Master Timeline automatically.

### Creating a Master Timeline

The Master Timeline comes in handy for organizing media that hasn’t been edited yet, as when you’re grading digital dailies. It’s also handy for picking out a band of similar clips by their similar timecode ranges. You might, for instance, find all the talking head shots from one section of tape gathered together within the Master Timeline.

### Using the Effects Library

Every effect you can drop into your edit — filters, transitions, titles, and generators included — lives in the Effects Library, which breaks into two parts. On the left sits a bin list presenting a hierarchical list of all the available Transitions, Title Effects, Generators, and Filters, grouped by category. On the right is a browsing area where you see the contents of whichever bins are selected. As with the Media Pool, a button at the top left opens or closes the Effects Library’s bin list, while a menu just right of that button sorts the list into different categories.

### The Effects Library

### The Toolbox

All the video and audio transitions, titles, and generators bundled with DaVinci Resolve show up in the Effects Library’s Toolbox category. Toolbox: Surfaces all Transitions, Titles, Generators, and Effects at once. Video Transitions: Holds every built-in transition DaVinci Resolve offers. You can drag any video transition onto any Timeline edit point that has overlapping clip handles to add it to your edit; you’re free to drop the transition so it ends on, centers on, or starts on the edit point. For more, turn to Chapter 48, “Using Transitions.” Audio Transitions: Holds audio transitions for building crossfades. Titles: Titles edit into the Timeline like any other clip. With one in the Timeline, you can edit its title text and position straight in the Timeline Viewer, or reach its controls in the Inspector for further customization. Generators: A generator, too, edits into the Timeline just as any other clip would. Select a generator, then open the Inspector, and its controls become available for further customization. You can also set a standard duration that generators appear with in the Editing panel of the User Preferences. Effects: Holds distinctive placeholder effects such as Adjustment Clip and Fusion Composition, which can be customized to apply sophisticated effects to your programs.

### OpenFX

On the Edit page, DaVinci Resolve supports third-party OpenFX filters, transitions, and generators. Once you install these effects on your workstation, they show up in this section of the Effects Library, sorted by type and group according to the metadata inside each effect. OpenFX: Brings up, all at once, every Resolve FX along with the third-party OpenFX sitting on your workstation. Filters: Holds the Resolve FX filters bundled with DaVinci Resolve, plus any third-party OFX plugins you’ve installed on your workstation. Drag a filter onto a video clip to apply its effect to that clip. With one applied, you can edit and customize the filter by opening the OpenFX panel of the Inspector. Transitions: Holds any third-party OFX transitions installed on your workstation. OFX transitions work much like any other transition, but they additionally surface an OpenFX panel beside the Transition panel in the Inspector, where you tailor settings unique to that transition. Generators: Holds any third-party OFX generators installed on your workstation. These edit into the Timeline just like the native generators bundled with DaVinci Resolve, but they additionally surface an OpenFX panel beside the Transition panel in the Inspector, where you tailor settings unique to that transition.

### Audio FX

Across every platform, DaVinci Resolve supports Fairlight FX, the built-in audio plugins that ship with DaVinci Resolve. Beyond those, DaVinci Resolve supports third-party VST audio plugins under macOS as well as Windows, and Audio Unit (AU) audio plugins under macOS. Install these effects on your workstation and they show up in this panel within the Effects Library. With audio plugins you can apply effects to single audio clips, or to a whole track’s worth of audio, lending creative qualities like echo or reverb, or sorting out mastering issues through noise reduction, compression, or EQ.

### Effects Library Favorites

Clicking the far right of any transition, title, or generator marks that effect with a star as a favorite. Once you do, the favorited effects collect in a separate Favorites area down at the bottom of the Effects Library Bin list.

Stars mark a flagged favorite effect; here all favorites are filtered.

### Index

The index lays out information about your timeline in a stripped-down spreadsheet format, serving both as a reference and as a means of timeline navigation. It splits across the Edit Index, Tracks, and Markers tabs.

### Edit Index

Clicking the Edit Index button brings up the Edit Index. By default it presents an EDL-style list view of every edit event in the current timeline. Whichever timeline is selected in the Timeline list shows its events here. That said, you can filter the Edit Index’s contents through commands in the Option drop-down, covered later in this section. Each clip and transition appears as its own event, every one carrying several columns of information. Re-edit a timeline and your changes turn up in this list too. The Edit Index helps creative editors hunting for particular effects used in the current timeline, as well as finishing editors who need more information about a specific clip, or who may have to filter the whole edit by particular criteria to troubleshoot assorted issues.

### Edit Index List shown open

### Navigating the Timeline Using the Edit Index

Any time you move the Timeline playhead across a clip, the Edit Index refreshes to show only the clips on the video track that clip sits on, and that clip’s event gets highlighted in the Edit Index. This makes the link between a Timeline clip and its event easy to read, which helps when you’re troubleshooting problems. The Option menu additionally holds commands that narrow the view down to clips on enabled tracks alone, to video clips alone, or to audio clips alone.

### Edit Index Columns

Each event fills several columns of information. You can reorder these columns by dragging them left or right, according to which information matters most to you. The columns of information on offer are:

- #: The event number (matching the clip number shown in the Color page’s Thumbnail timeline).
- Reel: The corresponding clip’s reel name.
- Match: Flags clips carrying clip conflicts, which show a question mark in this column.

The flag vanishes once the clip conflict is resolved.

- V: Video event.
- C: The event type (C for cut, D for dissolve or transition).
- Dur: A number giving a transition’s duration in frames.
- Source In/Source Out: The Source In and Source Out timecode marking the span of timecode

that clip references; it corresponds to where each clip’s In and Out point sits in timecode relative to the source media it draws from.

- Record Duration: The clip’s duration in the Timeline, set by the Record In/Out timecodes.
- Record In/Record Out: Record In and Record Out timecode marking that clip’s place in the Timeline.
- Name: The clip’s name.
- Comments: Whatever comments rode along in the EDL that got imported. For example, clip names exported from the original NLE to serve as reel names in RED workflows using EDL import.
- Source Start/ Source End: The very first and last frame of media on hand in the Source Media for that clip.
- Source Duration: The duration, in timecode, of the whole source media available in that clip.
- Codec: The corresponding clip’s codec.
- Source FPS: The corresponding clip’s frame rate.
- Resolution: The corresponding clip’s frame size.
- Color: The color of the flags or markers on that clip.
- Notes: Notes typed inside markers applied to clips or the Timeline.
- EDL Clip Name: Shows the imported EDL’s name, where that’s on hand.
- Marker Keywords: Lists every keyword found in a particular marker.
