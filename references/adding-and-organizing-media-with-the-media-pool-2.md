# Adding And Organizing Media With The Media Pool (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Bringing clips into the Media Pool from the Media page gives you the richest organizational tools and options, but when you happen to be on the Cut, Edit, Fusion, or Fairlight page and just want a handful of clips fast, there are a couple of routes available. Bringing media in by dragging clips out of the Finder and onto the Media Pool (this is macOS only): 1 Pick one or more clips inside the Finder. 2 Drop those clips onto the Media Pool of DaVinci Resolve, or onto a bin within the Bin list. The clips then join your project’s Media Pool. Relying instead on the Import Media command from within the Media Pool: 1 Anywhere in the Media Pool, right-click and pick Import Media. 2 In the Import dialog, pick one or more clips to bring in and click Open. The clips then join your project’s Media Pool.

### Removing Media From the Media Pool

When the Media Pool holds clips you want gone, clearing them out is simple, whether one at a time or as a whole group. To remove clips from the Media Pool, do one of the following:

- Pick one or more clips inside the Media Pool, then hit the Delete or Backspace key.
- Pick one or more clips inside the Media Pool, right-click one of the chosen clips, and then pick Remove Selected Clips.
- Anywhere within the Media Pool, right-click and pick Remove All Clips in Bin.

NOTE: When “Automatically match master timeline with media pool” has been switched on in the General Options panel of the Project Settings, the Media Pool won’t let you clear every clip while other timelines still draw on those same media files. Clearing clips off the Master Timeline (should it be exposed):

- Go to the Edit page, then pick one or more clips inside the Media Pool, right-click one of the chosen clips, and pick “Remove Selected Clips from Master Timeline.”

To read more about working with the Master Timeline, refer to Chapter 33, “Using the Edit Page.”

### Removing Unused Media from a Project

DaVinci Resolve can clear out unused media clips from the Media Pool on its own, getting things ready for archiving or for handing a tidy project off to another workstation. The pass loads every timeline, compound clip, and Fusion composition, then checks them all for media usage. Whatever clips that check fails to encounter are dropped from the Media Pool. The option erases nothing from your disk; it simply takes the clips out of the Media Pool and the Project. The action cannot be undone. Based on how large the Project is, the pass may run for several minutes. To remove unused media from a Project: 1 Click the Media Pool Option (3-dot) menu. 2 Pick Remove Unused Clips from the drop-down menu. 3 Click the Load All Timelines button to begin, or Cancel to call it off.

Pick Remove Unused Clips from the Media Pool Option menu, then click the Load All Timelines button to kick off the analysis

### Adding and Removing External Mattes

When you receive matte files meant to go with one or more media files in a program you are grading, you can bind them straight onto particular clips in the Media Pool so they serve as key sources for a Clip Grade inside the Node Editor of the Color page. You may even rely on matte files that bundle several mattes inside one piece of media. That is achieved either by writing distinct mattes to a clip’s red, green, and blue channels, or by packing several matte passes inside one OpenEXR file.

### Matching RGB and Matte images

With the Media Pool set to Icon view, any clips carrying clip mattes display a badge.

### A clip matte, seen in Icon view

When the Media Pool sits in List view, clip mattes show up nested below the clip they belong to.

### A clip matte, seen in List view

As another option, you can place a timeline matte into the Media Pool that is bound to no particular clip and can serve as a key source on the Color page inside any clip’s Clip grade, or inside a Timeline Grade. In the Media Pool, timeline mattes show up as clips that stand on their own.

### A timeline matte, seen in Thumbnail view

### What Are Mattes For?

There are two purposes matte files serve. By tradition, a matte is a grayscale media file marking out regions of differing opacity, where white stands for solid areas and black stands for transparency. As an example, clips exported from a compositing application sometimes arrive alongside one or more matte files matching keys or rotoscoped mattes from that composite. Bringing these matte files in with the “Add as Matte” command binds them to the clips they accompany in the Media Pool, so each is available only to the clips it has been synced with. That said, mattes also work as creative devices for laying grain and texture down for effect. Just what a matte accomplishes hinges on the way you wire it in the Node Editor of the Color page. Because these are media files you might wish to apply as mattes to virtually any clip, they can likewise enter the Media Pool as a so-called timeline matte, which you can drop onto whatever clip you like. TIP: Where it helps, LUTs may also be laid onto clip mattes as well as timeline mattes within the Media Pool — simply right-click a matte and pick a LUT out of the 1D LUT or 3D LUT submenus. That proves useful for fixing up mattes that came in formatted incorrectly.

### Adding Mattes

Mattes have to be added by very particular steps before you can use them. To assign a matte to a clip in the Media Pool: 1 Pick the clip in the Media Pool you intend to attach an external matte to. 2 Within the Media Storage panel, locate the matching external matte file, give it a right-click, and pick Add to Media Pool as a Matte. That binds the matte to the clip as a clip matte. A badge marks the clip as having a matte while the Media Pool is in Icon view, and the matte itself becomes visible — appearing as a nested item below the clip it is bound to — after the Media Pool is switched over to List view. Stripping mattes back off clips within the Media Pool: 1 Set the Media Pool over into List view. 2 Give a right-click to whichever external matte file should go and pick Remove Selected Clips. Taking out an external matte clip also strips that matte’s key from any clip grades relying on it, so that any clip using it as a key input shifts from a secondary operation back to a primary operation, where the color change touches the whole image. To add a timeline matte to the Media Pool: 1 Confirm that no clip is selected in the Media Pool. 2 Within the Media Storage panel, locate an external matte file, give it a right-click, and pick Add to Media Pool as a Matte. The external matte then shows up in the Media Pool as a timeline matte. Mattes can also be assigned to clips right on the Color page, which is sometimes quicker.

To assign a matte to a clip in the Color page:

- Drag any clip from the Media Pool to the Node Editor.

In the Node Editor the dragged clip then acts as an External matte feeding the grade of whichever clip is current, and that same clip is assigned for you automatically to the current clip back in the Media Pool. To read more about putting external matte clips to work as keys while grading, refer to Chapter 146, “Combining Keys and Using Mattes.”

### Using Embedded Mattes in OpenEXR Files

When you bring in OpenEXR files that carry embedded matte passes, no extra step is required, since those mattes already live inside the clip you just imported into the Media Pool. To read more about working with mattes inside OpenEXR files, refer to Chapter 146, “Combining Keys and Using Mattes.”

### Adding Offline Reference Movies

While shifting a project out of another application and into DaVinci Resolve, it helps to render the whole program as one media file to serve as an Offline Reference Movie. You can then bring that file in by a special route for dual Viewer comparison on the Edit page, or for a split-screen fade wipe comparison on the Color page. As of DaVinci Resolve 16 importing reference movies this way is no longer required for an offline comparison, yet it can still prove handy when you are juggling many timelines and versions that demand pinpoint precision. Adding a clip as an offline reference clip works like this: right-click the clip within the Media Storage panel and pick “Add As Offline Clip.” The clip then shows a small checkerboard badge on its Media Pool icon, or it appears as the icon over to the left of the Media Pool.

Checkerboard icon indicating an Offline comparison video To read more about putting an offline video to use against an imported Timeline on the Edit page, refer to Chapter 55, “Preparing Timelines for Import and Comparison.” To read more about split-screen reference of Offline video on the Color page, refer to Chapter 126, “Using the Color Page.”

### Extracting Audio in Media Storage

When a video clip in the Media Storage panel carries audio you want but the picture is of no interest, the Extract Audio command builds a standalone audio clip you can then bring into the Media Pool on its own. Pulling the audio out of a media file goes like this: 1 Within the Media Storage panel, right-click a clip and pick Extract Audio. 2 Inside the Extract Audio dialog, hit the Browse button to settle on a different disk spot for the extracted clip. 3 Click Extract. The audio channels are pulled out and saved as a .WAV file at the chosen destination. 4 Once that standalone .WAV file exists, you will have to import it into the Media Pool before you can use it in your project.

### Manually Organizing the Media Pool

No matter whether you are doing onset work, building digital dailies, sorting media to edit, or ingesting media to conform to an imported project, keeping things in order is absolutely critical. The Media Pool hands you a great many tools for that. This section looks at how bins let you organize collections of clips by hand.

### To Select Clips in the Media Pool

You have several ways to pick clips in the Media Pool ahead of relinking, unlinking, moving, duplicating, deleting, or carrying out any other operation on them.

- Click any clip to select it.
- Drag a bounding box around several clips to select them all.
- With either the Command or the Shift key held, draw a bounding box across a separate

discontiguous group of clips so as to either add them to the current selection or take them out of it.

- Click one clip, then Shift-click another so both clips plus everything between them form one continuous selection. A further Shift-click can grow or shrink the selection.
- Command-click clips one by one to build a discontiguous selection. A Command-click on a clip that is already selected drops just that clip while the rest of the selection stays put.
- With a single clip selected, hold the Shift or Command keys and use the Arrow keys to extend the selection onto neighboring clips.

### Organizing Media into Bins

Sorting clips into separate bins in the Media Pool is straightforward. Certain workflows demand it, while in others it is entirely up to you. Methods of working with bins in the Media Pool:

- To add a bin to the Media Pool: Within the Bin list, right-click and pick Add Bin. For a bin nested inside another, right-click whichever bin and pick Add Bin.
- To move selected clips into a new bin: Pick every clip you intend for the new bin, then right-click one of those chosen clips and pick Create Bin With Selected Clips.
- To rename a bin: Pick the bin you want renamed, then click its name once more to make it editable. With the name highlighted, type a fresh name and press Return. As an alternative, right-click a bin, pick Rename Bin, then type a fresh name and press Return.
- To route incoming clips toward one particular bin: Click a bin in the Media Pool so it is selected, then lean on any of the methods covered above to pull media out of the Media Storage panel straight into that bin.
- To move media from one bin to another: Drag one or more chosen clips out of their present spot in the Media Pool and into that bin. Several clips can be picked in the Media Pool through Shift‑clicking or Command-clicking, or by drawing a bounding box across a group. One bin may also be dragged into another.
- To delete a bin: Pick the bin you want removed, then tap the Backspace or Delete key. As an alternative, give a bin a right-click and pick Delete Bin. Wiping a bin that holds nested bins takes that whole set of bins with it.
- To sort bins: Right-click any bin and pick an option from the Sort By submenu. The choices are Name, Date Created, Date Modified, and User Sort.
- To reorganize bins manually: Right-click somewhere in the Bin list and pick Sort By > User Sort. Then drag bins up or down within the Bin list into whatever order you prefer. An orange dividing line marks where the dragged bins will land when dropped and helps reveal whether a bin you are dragging is about to nest inside another or not. Your User Sort order persists even after you switch to a different sort order, and choosing User Sort once more brings your custom order back.

### Import and Export DaVinci Resolve Project Bins (.drb)

Particular bins can be imported and exported from one DaVinci Resolve project to another, letting you move bins quickly between projects and workstations that share the same media. Every bit of Metadata, In/Out points, Timelines, and so on travels along with the clips in the bin, though none of the actual media files come with it. Sending bins out of the Media Pool goes like this: 1 In the Media Pool, pick one or more bins. 2 Give that selection a right-click and pick “Export Bin,” or instead pick File > Export > Export Bin. 3 In the file system dialog, decide where the DaVinci Resolve Bin file (.drb) goes and click Save. Bringing bins back into the Media Pool goes like this: 1 Within the Media Pool, right-click and pick “Import Bin,” or instead pick File > Import > Import Bin. 2 Do one of the following:

- Choose a DaVinci Resolve Bin file (.drb) from the file system dialog.
- Double click the .drb file in your file system.

The bin or bins then turn up in the Media Pool. Whichever bins you import this way get the word “import” tacked onto their name to head off duplicate names. Should an imported bin hold clips that already lived in the Media Pool, those possible duplicates are skipped during import and instead relinked to the media your project references. That keeps the Media Pool clean. Even so, if the bin or bins were moved onto a different computer, you may need to relink offline media.

### Import and Export Power Bins

Power Bins (bins that carry over from one project to the next) can be imported and exported as .drb files exactly like ordinary bins. Power Bins stay hidden by default and are turned on by clicking the Media Pool Option (3-dot) menu and picking Show Power Bins.

### Import and Export DaVinci Resolve Timelines (.drt)

Single timelines can be exported and imported from one DaVinci Resolve project into another already-existing DaVinci Resolve project, letting you move timelines quickly between projects and workstations without generating extra imported project files. Only the timeline together with its related clip information is exported; none of the actual media files travel with it. Sending one timeline out of the Media Pool goes like this: 1 In the Media Pool, pick a timeline. 2 Choose File > Export > Export AAF, XML, DRT (Shift-Command-O). 3 In the file system dialog’s format options popup, pick “DaVinci Resolve Timeline Files (\*.drt).” 4 In that same dialog, decide where the DaVinci Resolve Timeline file (.drt) goes and click Save. Sending several timelines out at once goes like this: 1 In the Media Pool, pick multiple timelines. 2 Give a timeline a right-click and pick Timelines > Export > DaVinci Resolve Timeline Files. 3 From your file browser, pick the folder they should be saved to. Compared with the single-timeline route, a multi-timeline export gives you no chance to rename the .drt files as they go out. Every one keeps the timeline name it carries in the Media Pool. Bringing a timeline back into the Media Pool goes like this: 1 In the Media Pool, pick a bin where the imported timeline should land. 2 Do one of the following:

- Choose File > Import Timeline > Import AAF, XML, DRT (Shift-Command-I); next, out of the file system dialog, pick a DaVinci Resolve Timeline file (.drt) and click Open.
- Double click the .drt file in your file system.

The timeline then turns up in the Media Pool together with every clip tied to it, including any media sync information. Whichever timelines you import this way get the word “import” tacked onto their name to head off duplicate names. The imported timeline is conformed automatically to matching media already present in the Media Pool. Even so, if the timeline was moved onto a different computer, you may need to reimport or relink missing or offline media to bring the imported timeline fully online. NOTE: This method handles only one timeline per import or export. To bring in or send out several timelines, use the Import/Export Bin function covered above.

### Sharing Media Among Projects Using Power Bins

Power Bins offer a means of importing and arranging media that you want on hand for every project in DaVinci Resolve. They occupy a distinct region of the Media Pool, set off by resizable dividers from both the ordinary bins and the Smart Bins regions. Power Bins follow a hierarchy, just as regular bins do, and you may nest as many as you like, one within another. As with regular bins, you create Power Bins by hand, right-clicking inside the Power Bins region and picking Add Bin. The distinction is that any clips you import into Power Bins are shared across every project in a single-user installation, or across all projects owned by a given user in a multiuser installation. That makes them akin to Power Grades in the gallery of the Color page. It also makes Power Bins perfect for holding shared media reused all the time, such as stock video, sound effects, stills, and items like company slates plus the network graphics and animations that open every episode of a series.

### The Power Bins area of the Bin list

You build and work with Power Bins the same way as any other bin, following the steps covered already. To show or hide the Power Bin area of the Bin list: Pick Show Power Bins from the Media Pool option menu to flip the visibility of all power bins on or off.

### Automated Organization Using Smart Bins

A fully automatic route to organizing media in the Media Pool is to lean on Smart Bins, created either automatically or by hand, which round up every clip and timeline in the Media Pool sharing traits drawn from any of the intrinsic or user-editable metadata exposed in the Metadata Editor and Media Pool. If you know the Color page, you will find Smart Bins behave much like Smart Filters, and they are built and edited through nearly the same steps. To read more about Smart Filters, refer to Chapter 126, “Using the Color Page.” Smart Bins bend to almost any need. Built on one or more metadata-based rules, they can be as plain or as elaborate as you wish. They can even apply several groups of several rules for cases where you must round up clips meeting every condition in one set yet only a single condition from a second set. In this way, Smart Bins let you handle a broad range of organizational needs while you cut your program.

### Smart Bins Are Only As Good As Your Metadata

Worth stressing, though, is that while plenty of intrinsic metadata attaches to every clip in DaVinci Resolve on its own (clip properties like frame rate, frame size, codec, file name, and the rest), the more effort you put into entering extra metadata in the Metadata Editor as you prepare a project for editing and grading, the more potent Smart Bins become at helping you sift and sort through the contents of the program you are grading. Metadata entries that pay off immediately with Smart Bins include scene, shot, and take information, plus keywords that flag central descriptors — among them day versus night, interior versus exterior, framing, and the like — alongside Face Detection put to work attaching character names. Such categories of metadata can drive the automatic creation of Smart Bins, but they can equally be mixed together when you hand-build Smart Bins that are even more pointed. Picture being able to round up every clip in one scene, locate all the interview clips for one subject, or surface all the edited timelines matching one name, simply by clicking a Smart Bin that scans the current Media Pool on its own. When you or an assistant invest the time to enter metadata for a project’s source material that captures these traits, you will find the clips you need for any situation far faster.

### Smart Bins Update Their Contents Dynamically

Smart Bins stay current at all times and pull in whatever fresh media lands in the Media Pool. That keeps organization effortless even on projects where new media arrives in the Media Pool daily, as happens while editing during a shoot. Drawing on metadata entered in-camera, by the DIT or media wrangler handling ingest, or by an Assistant Editor working with you, Smart Bins automatically take in every Media Pool clip whose criteria match, no matter whether the clip arrived a month back or a minute back.

### Automatic Smart Bin Creation

Adding metadata to your clips can power the automatic creation of sets of “Smart Categories,” which are Smart Bins generated and arranged by the presence of particular categories of metadata and shown in the Smart Bins section of the Media Pool sidebar. Turning this behavior on or off is a matter of opening the User Preferences to its Editing panel, where the checkboxes within the Automatic Smart Bins group let you decide which metadata spawns Smart Bins on its own.

Preferences that set which metadata is allowed to spawn Smart Bins on its own. The metadata that can give rise to Smart Bins covers:

- Clip Keywords
- Marker Keywords
- People Keywords (added via People Detection)
- Scene metadata
- Shot metadata

These categories follow a hierarchy, with each one collapsed by default to conserve space. Click the disclosure triangle on any category to expose all the Keyword, People, Scene, or Shot Smart Bins available in the current project. Choosing the Smart Category’s top bin lets you view every clip referenced by every Smart Bin nested inside it, whereas choosing individual Smart Bins shows only the clips that particular Smart Bin references.

A Smart Category as it appears within the Smart Bins region of the Media Pool sidebar. Dragging and dropping clips can hand them Automatic Smart Bin Properties, since metadata entry need not flow in one direction alone, starting from keystrokes in the metadata editor. With certain Automatic Smart Bin categories (keywords, shot, and scene), dragging several clips out of the Media Pool onto an existing smart bin passes that bin’s properties to all those clips in one move.

To automatically assign Smart Bin Properties to a range of clips: 1 Build a Smart Bin in one of these categories: Keywords, Shot, or Scene. 2 Pick every clip you want the Smart Bin property applied to. 3 Drag those clips out of the Media Pool and drop them onto the Smart Bin. As an example, you might build a smart bin with the Keyword: “Sunset.” That bin would show up on its own beneath the Keywords category in the Smart Bins. You could then pick all the sunset shots in your Media Pool and drag them onto that bin to hand the “sunset” keyword to every one of those clips at the same moment.

NOTE: Dragging and dropping clips to assign Smart Bin properties works only with the Automatic Smart Bin Keywords, Shot, or Scene categories. Dragging clips onto any other Smart Bin does nothing.

### Manual Smart Bin Creation

Hand-building Smart Bins with custom rules to filter very specific collections of media and timelines you want to work with is easy. To show or hide the Smart Bin area of the Bin list:

- Pick Show Smart Bins from the Media Pool option menu to flip the visibility of all Smart Bins on or off.
