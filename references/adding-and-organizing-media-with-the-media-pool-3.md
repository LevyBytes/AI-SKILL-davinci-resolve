# Adding And Organizing Media With The Media Pool (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

To build a Smart Bin: 1 When required, reveal the Bin list, pick Show Smart Bins from the Media Pool option menu, then right-click any empty spot in the background of the Smart Bin region of the Bin list, and pick Create Smart Bin. 2 Within the Create Smart Bin dialog, type a name for the filter, and rely on the controls below to define one or more filter criteria (there is no limit to how many filter criteria you add):

### The Create Smart Bin dialog

- Show in all projects checkbox: Produces a persistent Smart Bin that shows up across every project in your project library. Smart Bins made in this fashion land in the User Smart Bins folder within each project’s Smart Bin region of the Media Pool.
- Match options: When filtering on several criteria, picking All requires that each individual criteria you list is satisfied before a clip passes the filter. Picking Any means a clip passes once a single one of the several criteria is satisfied.
- Filter criteria enable checkbox: Turns any criteria on or off so you don’t have to remove it entirely.
- Metadata category drop-down: Determines which category of metadata you’ll pull a criteria from. Every metadata category exposed in the Metadata Editor is reachable from this drop-down menu. On top of that, Color Timeline Properties (which holds many properties exclusive to the Color page timeline) and Media Pool Properties (which holds every column in the Media Pool) open up extra metadata available for filtering.
- Metadata type drop-down: Picks the precise type of metadata to apply, from those offered in the chosen metadata category.
- Metadata criteria drop-down: Sets the criteria used for filtering, based on the metadata you’ve picked. Possible choices cover such things as “true/false,” ranges of integers, ranges of dates, searches over strings, colors of flags and markers, and the like.
- Add filter criteria button: Appends extra criteria so you can assemble multi-criteria filters. Several criteria together might, for instance, surface all exterior clips that additionally carry the keyword “Sunset” and that aren’t closeups, letting you gather every exterior long and medium shot lit by sunset. Furthermore, Option-clicking this button inserts a nested match option, enabling still more advanced filters — for example, one where the filter has to satisfy all of one group of criteria along with any of a second group.

An intricate Smart Bin carrying several criteria plus a secondary match option setting While you tweak the filter criteria, the thumbnail timeline refreshes on its own to show how the Smart Bin you’re assembling behaves. 3 After you finish editing the filter criteria, click Create Smart Bin. The newly made Smart Bin shows up in the Smart Bin region of the Bin list, on the left side of the Media Pool’s browser area. After a Smart Bin exists, it sits in the lower portion of the Media Pool’s Bin list, together with every other Smart Bin belonging to that project. That arrangement keeps them tidy, set apart from the manually made bin shown above.

Every Smart Bin is grouped at the foot of the Bin list belonging to the Media Pool After you’ve built a Smart Bin, you’re free to revise it any time the need arises.

Ways to change Smart Bins that already exist:

- To rename a Smart Bin: Right-click whichever Smart Bin you’d like renamed, pick Rename from the contextual menu, type a new name, and press Return.
- To edit a Smart Bin: Double-click the Smart Bin, then alter the filter criteria, and click OK.
- To duplicate a Smart Bin: Right-click any Smart Bin and pick Duplicate from the contextual menu. This is handy for spinning off several variants of a Smart Bin you built with intricate rules, when you need variants by tweaking those rules rather than starting over from scratch every time.
- To delete a Smart Bin: Right-click whichever Smart Bin you’d like removed, then off the contextual menu pick Delete Smart Bin, and in the warning dialog that appears click Delete. Removing a Smart Bin leaves any gathered media tied to that bin untouched.

### Smart Bins Work Better With Metadata

Bear in mind that the more metadata you attach to each clip, the more ways you have to build custom Smart Bins (for editing) and Smart Filters (for grading) to home in on exactly the clips a given situation calls for. Not only does this make locating what you need simpler, it also speeds up your work. As a baseline, it’s worth using the Metadata Editor to tag each clip with details such as a Description, Shot and Scene designations, take information, and perhaps a few handy keywords like character names, shot framing, interior or exterior keywords, and so forth. As an example, once you’ve filled in enough metadata, you can construct multi-criteria Smart Bins or Smart Filters that turn up something along the lines of “each close-up of Sally inside the diner” or “each long shot of Antonio out in the parking lot.” On a documentary, pulling out “each interview shot of Louis from camera 1” or “each B-roll clip featuring Robyn” becomes effortless. Everything here speeds up locating media for editing, or rapidly pulls together comparable clips you need matched up for grading. For further detail on the Metadata Editor, refer to Chapter 19, “Using Clip Metadata.”

### Organizing Smart Bins

Smart Bins you’ve made by hand can be grouped into Folders and Sub-Folders for tidier sidebar handling, exactly the way ordinary bins are.

### Smart Bins organized into folders

To add a Smart Bin folder: Right-click within the Smart Bins region and pick Add Folder from the contextual menu to make folders that you can drag Smart Bins into. Every folder carries a disclosure triangle, letting you reveal or conceal what it holds.

A further upside of Folders is that selecting a Folder shows the complete contents of every Smart Bin within it in the Media Pool browsing area. Picking any single Smart Bin then limits the Media Pool to only the media referenced by that Smart Bin. Right-clicking a Folder and choosing commands from the contextual menu lets you rename it, remove it, open it as a new window, or sort it together with all the other Smart Bins.

### Duplicating Clips in the Media Pool

You can duplicate clips so as to spawn an instance of that media that behaves as a wholly new source clip, fully independent of the original instance of that clip imported into DaVinci Resolve. The duplicate can hold its own metadata and markers that stay fully separate from the original clip imported into your project. To make duplicates of one or several clips: 1 Pick the clip or clips you wish to duplicate. 2 Carry out one of these:

- Choose Edit > Duplicate Clip
- Keep the Option key pressed as you drag one or several selected clips over to a different bin
- In the Media Pool, right-click a clip, then off the Contextual Menu pick Duplicate Clip

Adding Clips From the Timeline to the Media Pool Equally, you may drag one or several clips out of the Timeline and back into the Media Pool to spawn a duplicate. Just as with duplicating clips inside the Media Pool, each duplicate comes into being as a new source clip that stays wholly apart from the original instance of that clip imported into DaVinci Resolve and can hold its own metadata and markers that remain fully separate from the original clip imported into your project. For instance, the original clip in the Timeline stays conformed to the original clip first imported into the Media Pool; removing the original clip from the Media Pool renders that clip “non-conformed” in the Timeline, whereas the duplicate you just made stays linked and on hand. Should you land in this situation, you can at any point turn Conform Lock Enabled off on that clip within the Timeline and then reconform that Timeline Clip onto the duplicate you’ve made, though that adds a step because DaVinci Resolve regards the duplicate clip as an entirely fresh piece of media that merely happens to share identical clip details. It may feel odd, yet a range of finishing workflows lean on this ability, so it’s worth knowing.

### Duplicating Timelines

Timelines may be duplicated for any number of reasons: to keep a backup of a timeline at a given date, to spin off a variation of an edit, or to produce separately graded versions. To duplicate a Timeline:

- Select a Timeline in the Media Pool, and choose Edit > Duplicate Timeline.
- Hit Command-4 so the Timeline takes focus, then choose Edit > Duplicate Timeline.

### Choosing How to Display Bins

After you’ve set up a bin structure for your project, you can tailor the way your bins display, according to how you prefer to work.

### Showing Bins in Separate Windows

When you right-click a bin in the Bin list, you can pick “Open As New Window” to launch that bin into a window of its own. That window amounts to a self-contained Media Pool, carrying a Bin list of its own, its own Power Bins and Smart Bins lists, plus display controls.

### Multiple Media Pool bins opened as new windows

When more than one Media Pool window is open, you can use the Workspace > Media Pool Windows submenu to surface a floating Media Pool window that sits open yet hidden. This pays off most when two displays are attached to your workstation, since you can drag these separate bins onto the second display while DaVinci Resolve runs in single screen mode. Hiding the Bin list not only frees up more space for clips, it also keeps you from accidentally jumping bins when you really mean to view just one bin’s contents in that window.

### Using the Media Pool in Thumbnail View

When you work in Thumbnail view via the controls at the top right of the Media Pool, you’re able to resize the thumbnails for easier viewing, and you can pass the mouse pointer over each clip to hover scrub through what it holds. Clicking any clip to select it shows it in the Media page Viewer. Whatever clip is selected at the moment is also sent to video for monitoring. While in Thumbnail view, you control how clips get sorted through the Sort Order drop-down, which sits at the Media Pool’s upper right, positioned between the Icon Size slider and the Icon/List view buttons. Fourteen choices are on offer here. The naming-oriented ones are File Name, Reel Name, and Clip Name; timing-oriented are Start TC plus Duration; technical ones cover Type, FPS, and Audio Ch; then come Flags, followed by Date Modified together with Date Created, and finally the production fields Shot, Scene, and Take.

### Custom Sort of Clip Thumbnails in the Media Pool

You’re now able to reposition Media Pool clips by hand in Thumbnail view, so you can cluster clips together however makes visual sense to you.

You enable Custom Sort by picking Custom in the Sort menu of the Media Pool. Choose Thumbnail View in the Media Pool, and from the sort menu pick Custom. From there you can drag your thumbnails into any arrangement or grouping you like. With Snap to Grid picked in the Sort menu, the icons snap into orderly rows and columns. Switch off Snap To Grid to allow freeform placement. When two thumbnails overlap, whichever was moved last sits on top.

With Snap to Grid turned off you may rearrange thumbnails however you wish (overlapping included), and that layout is preserved throughout the Medial Pool across all pages. The placement of your icon thumbnails persists in the Media Pools across every page in DaVinci Resolve. The layout is also kept if you briefly switch to a different sort order and afterward come back to the Custom sort.

### Working With Columns in List View

When you work in List view via the controls at the top right of the Media Pool, you pick up extra organizational control by surfacing columns that display the metadata each clip carries, before media is added to your timeline. These columns are useful for organizing your media.

The Customize Columns window, reached by right‑clicking a column header while in List View Ways to customize metadata columns in List view:

- To show or hide columns: At the top of any Media Pool column, right-click to bring up the Customize Columns window. Within the Column Fields, tick the checkboxes for any columns you want shown or hidden. Unticked columns stay invisible. Once you’re done, click save.
- To rearrange column order: Drag any column header left or right to reorder the columns, or drag the column names into your preferred sequence in the Selected Fields section of the Customize Columns window.
- To resize any column: Drag the boundary between any two columns right or left to shrink or grow that column.
- To sort by any column: Click whichever column header you want to sort by. Each further click on the same header flips that column between ascending and descending sort order.

After you’ve dialed in a column layout suited to your specific purpose, you can store it to recall later.

Ways to save and apply custom column layouts:

- To create a column layout: Show, hide, resize, and reorder the columns you need for a given task, then right-click any column header in the Media Pool, and:
- Choose Customize Columns.
- Click on the option menu, and select Save as New Preset.
- Enter a new name for your column layout and press OK.
- To recall a column layout: In the Media Pool, right-click on any column header, then pick Load Custom Layout and, off the contextual menu, pick whichever column layout name you’d like to apply. Alternatively, pick Load Preset under the preset name within the Customize Columns option menu.
- To edit a column layout: Bring up the column layout you mean to edit, apply whatever changes are needed, then in the Media Pool right-click on any column header and pick Customize Columns. Inside the Customize Columns window, click the Save button. Another route is to pick Update under the preset name within the Customize Columns option menu.
- To delete a column layout: In the Media Pool, right-click on any column header, and pick Customize Columns . Next pick Delete Preset under the preset name within the Customize Columns option menu. To confirm, click delete a second time. Although the metadata columns offered match the fields shown in the Metadata Editor, the columns you get in the Media Pool on the Media and Edit pages amount to just a slice of all the metadata that’s present. You may put any metadata field — custom metadata fields among them — into your Column layouts.

### Editable Name, Description, Keyword, and Comments Columns

Beyond the Clip Name, when the Keyword, Description and Comments columns are shown by the Media Pool in List view, you can change what they contain by clicking once inside a clip’s Description or Comments field, pausing a beat, and then clicking a second time to select that field.

### Using Metadata View in the Media Pool

Within the Metadata View mode, each clip shows up as its own card displaying a thumbnail and basic clip metadata information. This view aims to carry more metadata information than a thumbnail yet more focused information than the List view. The feature, paired with its sort modes, gives you a powerful means of arranging and rearranging clips within the Media Pool. Reading the metadata fields of the Metadata view from top to bottom:

- Thumbnail: A scrubbable thumbnail image of your clip.
- Row 1: A primary description field whose contents shift depending on which sort order you’ve chosen.
- Row 2: Start Timecode, Date Created, Camera #.
- Row 3: Scene, Shot, Take.
- Row 4: Clip Name, Comment.

What makes the Metadata view powerful is the way it automatically clusters your clips by the sort order you pick in the Media Pool Sort By menu, in the very top-right corner of the Media Pool. Every distinct sort mode swaps out the main description field on the card and also reshuffles the Media Pool to mirror the chosen organization method.

The Metadata View icon view (its icon highlighted up in the top bar), with the thumbnail shown mid-scrub beside that clip’s metadata

### The Media Sort options

The sort modes offered within the Metadata view are:

- Bin: Clusters by bin, switches the primary description field over to clip name, and sequences everything by timecode.
- TImecode: Clusters by creation date, drives the primary description field to creation date plus start timecode, and sequences by timecode.
- Camera: Clusters by camera #, drives the primary description field to camera # alongside start timecode, with the sequence again by timecode.
- Date Time: Clusters by day, fills the primary description field with creation date and file name, and runs the sequence off timecode.
- Clip Name: Clusters by whatever first letter the clip name begins with, alphabetically, points the primary description field at clip name, and sequences by timecode.
- Scene, Shot: Clusters by scene, feeds the primary description field with scene-shot-take, and sequences by scene-shot-take.
- Clip Color: Clusters by clip color name, sets the primary description field to creation date and start timecode, and orders everything by timecode.
- Date Modified: Clusters by day, supplies the primary description field with creation date and file name, and sequences by whenever the OS filesystem last changed the clip.
- Date Imported: Clusters by day, fills the primary description field with creation date and file name, and sequences by the date the clip joined the Media Pool.
- Ascending: Arranges the Media Pool running from the smallest numerical value up to the largest, and alphabetically A through Z.
- Descending: Arranges the Media Pool running from the largest numerical value down to the smallest, and alphabetically Z back to A.

### The Metadata view with clips sorted by Scene-Shot-Take

The Metadata view with the same clips sorted by Camera

### Finding Clips, Timelines, and Media

A number of approaches exist for tracking down various items in the Media Pool and Media Storage, whether they’re clips, timelines, or media sitting on disk.

### Finding Clips and/or Timelines Within the Media Pool

Clicking the magnifying glass button at the top-right corner of the Media Pool brings up the Search Options, which by default let you find one or more clips within the currently selected bin or bins, going by the metadata picked in the Filter By drop-down menu just to its left.

The Search Options drop-down menu (pictured here in the Edit page Media Pool) governs which metadata your search targets A separate drop-down right beside the magnifying glass icon controls the breadth of that search. It governs whether the search combs through every bin in the active project for the stated criteria, or limits itself to the open bin alone, or to the bins picked out in the Bin list, useful when you’re after a media instance held at a specific hierarchical spot of the Media Pool. Sitting beside the magnifying glass icon, that drop-down is where the bin search parameters get set

To track down a clip in the Media Pool: 1 (Optional) Via the drop-down beside the Search button — the one that reveals the Media Pool’s Search and Filter by controls — pick either All Bins or Selected Bins. 2 (Optional) Should you be searching Selected Bins, reveal the Bin list and pick whichever bin or bins you mean to search. 3 (Optional) Pick a criteria off the Search Options drop-down menu at the Media Pool’s upper right; All Fields hunts across every metadata column in the Media Pool simultaneously, while a particular criteria narrows the search down. 4 Enter a search term into the Search field. As soon as your typing begins, any clip not matching the search criteria is hidden for the moment. Click the cancel button on the right side of the search field to restore the full set of clips in the Media Pool.

### Finding Synced Audio

Once dual-system audio and video clips have been synced together inside DaVinci Resolve, the steps below let you locate the audio clip a given video clip was synced with. To pin down the audio clip a particular video clip got synced with:

- Put the Media Pool into List view, and check the file name shown in the Synced Audio column.
- Right-click whichever video clip has been synced to audio, then pick “Reveal synced audio in

Media Pool” off the contextual menu. The bin housing the synced audio clip opens, with that clip selected.

### Finding Timeline Clips in the Media Pool

Got a clip in a timeline and need the matching clip it conforms to back in the Media Pool? Right-click the clip, then pick Find in Media Pool off the contextual menu.

### Finding Timelines in the Media Pool

To pin down where the open timeline lives within the Media Pool, head to Timeline > Find Current Timeline in Media Pool.

### Finding Media in the Media Storage Panel and Finder

Should you need to determine the on-disk location of a clip’s source media file, right-click the item within the Media Pool and pick Reveal in Media Storage panel. The Library jumps straight to the folder containing your chosen media file, which sits selected in the Library browser over on the right. There’s also a macOS-only capability: right-click an item in the Media Pool and pick Reveal In Finder. Up comes a file system window displaying the media file the clip is linked to.

Reveal Media Pool Bin from Multi-Bin or Search Displays After a clip search leaves you with hits scattered over several bins, you’re now able to surface that clip’s home in the Media Pool: right-click it and, from the contextual menu, pick Reveal Media Pool Bin.

### Going Immediately to a File System Location in the Media Browser

In reverse, dragging a folder out of the macOS Finder and onto the Media Storage panel makes the Media Storage panel refresh instantly to display that folder’s location.

### Tracking Media Usage

As clips get added to timelines, two mechanisms kick in for keeping tabs on which clips are used in which timelines.

### Thumbnail Clip Usage Indicators

Every time you open a timeline, all thumbnails in the Media Pool refresh automatically to display highlighted usage bars showing you which portions of that clip the timeline uses.

Two colored highlights along the bottom of the thumbnail mark which portions of a clip the currently open timeline uses If you right-click a thumbnail that displays usage, a Usage submenu presents a list of every instance of that clip in the currently open timeline. Picking an instance from that list sends the playhead to that clip in the Timeline.

### List View Clip Usage Column

Surfacing the Usage column while the Media Pool is in List view lets you read a value for how many times a clip turns up in the current timeline. This usage column now updates automatically; no user intervention is required.

Once analyzed, a Usage column reports the count of a clip’s appearances within a timeline.

### Updating Clip Usage for all Timelines

It’s also possible to review which clips have seen use throughout all the timelines in your project. Off the Media Pool Options menu, pick the “Update Usage for Entire Project” option.

### The Update Usage dialog

DaVinci Resolve may ask the user to load all timelines, when needed, and refresh usage counts for Media Pool clips. Depending on how many timelines you have in your project and how complex they are, this can take a while. Once it finishes, that cross-timeline usage tally appears within the Media Pool’s List view under the Usage column. NOTE: For every clip item showing up in the Timeline, the Usage column ticks upward by one. So a clip made of one video item joined with one video item will read 2 in the Usage column.

### Relinking Media Simply

DaVinci Resolve tracks the link between clips in your project and their matching source media on disk. If for any reason the source media tied to clips in your project goes missing, DaVinci Resolve offers several distinct ways to relink those clips in the Media Pool. This section recaps the relinking methods. For fuller coverage of conforming projects and relinking media, refer to Chapter 56, “Conforming and Relinking Clips.”

### Relink Media

Should DaVinci Resolve come up empty looking for your media, the Media Pool on the Cut and Edit page lights up its Relink Media icon in orange.
