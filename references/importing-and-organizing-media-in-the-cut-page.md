# Importing And Organizing Media In The Cut Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Importing and Organizing Media in the Cut Page

Editing can't begin until you've brought the clips you intend to use for your program into the Media Pool, which acts as your project's central repository of clips. That can take in video, audio, and graphics files of any format DaVinci Resolve supports. After import, the Cut page's Media Pool gives you a host of organizational tools that speed up reaching and sifting your project's media as you track down the clips you need to build your program.

### Importing Media

Sitting atop the Media Pool, two Import buttons open import dialogs you use to pick the media you want to pull into the Media Pool for your project.

### The Import Media and Import Folder buttons

To import individual clips:

1 Do one of the following:

a) Click the Import Media button.

b) Press Command-I.

c) Right-click the Media Pool and choose Import Media.

2 Within the Import dialog, pick one or several clips to import, then click Open. 3 Should a prompt offer to switch the frame rate of an empty project so it matches the incoming media, click Change.

Whatever media you import—be it video, audio, or graphics—shows up as a single clip in the Media Pool. A whole folder of media can also come in as a bin within the Media Pool.

Here's how to bring a whole folder of media in as a bin: 1 Click the Import Media Folder button. 2 Within the Import dialog, pick a folder holding the media you'd like to import, then click Open. 3 Should a prompt offer to switch the frame rate of an empty project so it matches the incoming media, click Change.

Every folder you bring in shows up as a bin inside the Media Pool. Double-click a bin and its contents open into the Media Pool, where you can look over each clip one by one.

TIP: When you want richer media-import options, turn to the Media page, which brings its Media Storage browser along with a fuller-featured take on the Media Pool.

### Removing Media

When a project holds clips you've no further use for, just select them and tap the Delete or Backspace keys. A Dialog checks whether you mean to remove the chosen clip or clips; click Remove and they leave the Media Pool while staying untouched on your media storage device. To clear out every clip in the bin that's currently open (the Master bin included), you can instead right-click anywhere inside the Media Pool and pick Remove All Clips in Bin off the contextual menu.

### Organizing Media into Bins

On short projects, keeping every clip together in one bin (the Master bin being the Media Pool's top level) can be quick. On longer ones, though, splitting your media into clip subsets across separate bins makes browsing each bin's contents through the Viewer's Source Tape easier to handle. TIP: Clips you're sure you won't use—say where the camera rolled on unusable scenery or moments, or takes that are wholly unusable—can be shifted into another bin so they stay out of the Source Tape for the bins that hold the clips you do want.

### Master Bin

The Master bin sits at the top level of your project hierarchy. Every piece of media

content (clips, timelines, graphics, other bins, and so on) for your project lives in the Master bin. On the Cut page, the Master bin

additionally surfaces all of your project's timelines for quick reach, no matter where in

your project they were created.

### Creating and Using Bins

To organize your media you can spin up bins by choosing File > New Bin (Shift-Command-N), or by right-clicking inside the Media Pool and picking New Bin off the contextual menu. Bins can be nested inside other bins, and that lets you arrange the clips you need hierarchically in all sorts of ways.

### Bins seen in the Media Pool

After a bin exists, you can drag and drop one or more selected clips into it, much the way you would on the desktop of your operating system's file manager.

### Opening Bins

Open any bin you can see in the Media Pool by double-clicking it, or by clicking the Bin dropdown at the Media Pool's upper-left corner and picking a bin to open from the menu (those appear as a hierarchical list). Once open, a bin's contents fill the Media Pool, and a path indicator atop the Media Pool reveals how many levels down you've gone wherever you've nested bins within bins. Click any level of that path to climb back up the hierarchy, or grab a different bin from the Bin drop-down.

### The hierarchical Bin drop-down menu

### Create Bin With Selected Clips

Creating a bin and loading clips into it can also happen in a single move. Pick one or several clips in the Media Pool, right-click one of those selected clips, and pick Create Bin With Selected Clips off the contextual menu. A fresh bin titled “Bin X” shows up (with X being the next free number), now holding the clips you'd selected.

### Renaming Bins

Renaming a bin starts with clicking its name once, then clicking a second time slowly (click too quickly and it counts as a “double-click,” which opens the bin); the name then lights up, ready for editing. You can also right-click a bin and pick Rename Bin off the contextual menu, which likewise lights up the bin's name for editing. After you've typed the new name, hit Return (or Enter).

### Import and Export Specific DaVinci Resolve Project Bins

Specific bins can be imported and exported between one DaVinci Resolve project and another, which lets you hand bins off rapidly among projects and workstations that reach the same media. The clips in a bin carry along all Metadata, In/Out points, Timelines, and so on, yet none of the actual media files travel with them. To export bins from the Media Pool: 1 Pick one or several bins in the Media Pool. 2 Right-click your selection and pick “Export Bin,” or go to File > Export > Export Bin. 3 In the file system dialog, decide where to save the DaVinci Resolve Bin file (.drb), then click Save.

To import bins into the Media Pool: 1 Right-click inside the Media Pool and pick “Import Bin,” or go to File > Import > Import Bin. 2 Do one of the following:

- Choose a DaVinci Resolve Bin file (.drb) from the file system dialog.
- Double click the .drb file in your file system.

That bin—or bins—then shows up in the Media Pool. Anything imported this route gets the word “import” tacked onto its name so duplicate names are avoided. Import a bin holding clips that already sit in the Media Pool, and those would-be duplicates are left out of the import and instead relinked to the media your project references. That keeps your Media Pool tidy. That said, where the bin or bins have moved to a different computer, relinking offline media may fall to you.

### Import and Export Individual DaVinci Resolve Timelines

Individual timelines can be exported and imported from one DaVinci Resolve project into another, already existing DaVinci Resolve project, which lets you hand timelines off rapidly among projects and workstations without generating extra imported project files. Only the timeline plus its related clip information gets exported; none of the actual media files come along.

To export a timeline from the Media Pool:

1 Pick a timeline from the Media Pool.

2 Choose File > Export > Export AAF, XML, DRT (Shift-Command-O).

3 In the file system dialog, set the format options drop-down to “DaVinci Resolve Timeline Files (\*.drt).”

4 In the file system dialog, decide where to save the DaVinci Resolve Timeline file (.drt), then click Save.

To import a timeline into the Media Pool: 1 In the Media Pool, pick the bin where you'd like the imported timeline kept. 2 Do one of the following:

- Go to File > Import Timeline > Import AAF, XML, DRT (Shift-Command-I); next, in the file system dialog, pick a DaVinci Resolve Timeline file (.drt) and click Open.
- Double click the .drt file in your file system.

The timeline then surfaces in the Media Pool together with every clip tied to it. Anything imported this route gets the word “import” tacked onto its name so duplicate names are avoided. That imported timeline is automatically conformed to whatever matching media already sits in the Media Pool. That said, where the timeline has moved to a different computer, you may have to reimport or relink missing or offline media to bring the imported timeline fully online.

NOTE: This method handles just one timeline per import or export. Where you need several timelines moved at once, fall back on the Import/Export Bin function covered above.

### Sync Media Pool Bins with File System Folders

A Media Pool bin can now be synced to a folder on your computer's file system (MacOS, Windows, Linux, and so on). With that, dropping more media into a folder on your computer makes it import on its own to the matching DaVinci Resolve bin. Setting up a folder for Automatic Syncing goes like this: 1 Over on the Cut page, use the Import Folder icon up on the top menu bar to line up matching folder and sub-folder names.

Use the Import Media Folder icon in the Cut page 2 Give the imported folder a right-click and pick ”Automatically Resync Media Files.“

Right-click on the bin and select Automatically Resync Media Files Whatever clips you add fresh to this folder get pulled into the media bin on their own. That helps when you're dealing with cloud-synced media files (as you are when using DaVinci Resolve's Replay capabilities), or any files that might land in the folder down the road. For a one-time manual resync of a Media Pool bin's contents, right-click a bin and pick ”Resync Media Files.”

Right-click on the bin and select Resync Media Files to carry out the sync by hand.

For both Resync actions, ensure that:

- At least one clip is present in the media bin.
- All existing clips in the media bin share the same file path.
- The media bin's name lines up with the parent folder of the clip paths. To be sure this is configured right, lean on the Cut page's “Import Media Folder,” or instead reach for “Add Folder and SubFolders into Media Pool (Create Bins)” over on the Media page.

Sync actions pull in new clips out of sub-folders wherever the matching sub-bins are present. Even so, freshly

made sub-folders that lack matching media bins go untracked, and new media bins that lack

their matching sub-folders are passed over.

Imagine, for instance, that you're cutting a sporting event while a graphics operator builds animated lower-thirds for every player. Set up a shared network folder called “CG” and have DaVinci Resolve sync it automatically, and each freshly finished, saved lower-third would surface on its own in your bin in the Media Pool, ready to use.

Here’s how you would set this up:

- On your network storage, make a folder named “CG.” Both the editor and the graphics operator must be able to reach this folder.
- Keep in mind that since this folder is empty right now, it isn't eligible for a Resync action yet. A Resync becomes possible only once the folder holds at least one media file.
- The graphics operator wraps up his first animated lower third and saves it into the “CG” folder as a .mov file (though any media format DaVinci Resolve can read would do).
- Next the editor brings the “CG” folder into the Media Pool within DaVinci Resolve and picks Automatically Resync Media Files off the context menu.
- Each time the graphics operator wraps and saves more lower thirds into that folder, they surface on their own in the Editor's “CG” bin in the Media Pool, with no need to import them specifically.
- For tidiness, the graphics operator then makes a fresh folder within “CG” for the other team, naming it “Team B.” Unfortunately, since that folder structure wasn't part of the originally imported bin, it stays absent from the editor's media pool. Had they instead built this Team B folder ahead of the editor's import, with media inside it, it would have shown up.
- In that case, the editor just imports the same bin once more, picks Automatically Resync Media Files, and the new folder along with all its media shows up as expected. Anything further dropped into “Team B” thereafter will turn up in the editor's media pool.

IMPORTANT: Whenever a clip is removed or can't be located on the file system, its media entry gets flagged as offline media. That preserves the metadata and proves handy when a clip path is offline for the moment, sits on cloud storage where file status keeps shifting, or has been moved aside by apps or workflows aiming to write a fresh version in its spot.

### Import Blackmagic Cloud Shared Folders to Media Pool

Blackmagic Cloud Folders can now be imported and synced into the Media Pool. That lets you

hook up to one or more cloud media folders and pull media down from them selectively to your

local machine. Blackmagic Cloud Folders are online shared storage folders not bound to any

one project. With them you can build a pool of media assets you reach for often, such as title sequences,

credits, bumpers, and so on, and share those online instead of importing them one by one into each

separate project.

The Import Cloud Folder icon at the top of the Media Pool Linking a Blackmagic Cloud Folder to your project goes like this: 1 Within DaVinci Resolve, log into your Blackmagic Cloud account. 2 On any page, click the Import Blackmagic Cloud Folder icon atop the Media Pool. 3 Inside the Blackmagic Cloud Folder dialog, click select to pick a Blackmagic Cloud Folder. What you see listed here are any Blackmagic Cloud Folder you've made or that someone else has shared your way. Click the Add button. 4 Under Download Folder Location, pick a spot on your local system where you'd like the media from the Blackmagic Cloud Folder kept. 5 Decide whether to sync proxies alone, or proxies plus used originals. 6 Hit Download to bring the Cloud Folder into your Media Pool.

### The Blackmagic Cloud Folder link dialog

Open the Blackmagic Cloud Folder in the Media Pool and it starts out empty, filling one clip at a time as their clip names (not their media) come down from the cloud. The Blackmagic Cloud Folder also isn't truly tied to your project yet; the link only forms once the first media clip gets “used.” A “used” clip is fresh terminology in DaVinci Resolve and simply refers to a clip that's been changed in some way inside the project. Dropping a clip onto a timeline certainly counts as using it, but so do other actions—flagging it, editing its metadata, transcribing it, and the like. The moment a clip is used, its media begins downloading to your local machine. Used clips are marked by a red dot beside them in the Media Pool. Any clip left unused stays a virtual clip in the Cloud Folder until that changes. After download, clips in Cloud Folders behave just like every other clip in the Media Pool.

The Cloud Folder linked in List view. A red dot marks a “used” clip whose original media has come down. Clips left unused offer only their proxies for viewing. The Cloud Sync column indicates the media is registered and kept in sync with the Blackmagic Cloud.

### Media Pool Views

After you've brought some clips into the Media Pool, three controls over at the upper-right let you steer how they appear, according to what you're trying to do.

### The View Mode buttons

### Metadata View

Under the Metadata view mode, every clip gets its own card carrying a thumbnail plus basic clip metadata on display. This view aims to surface more metadata than a thumbnail does, yet more focused information than the List view. Paired with its sort modes, this feature gives you a strong way to organize and rearrange your clips in the Media Pool. The Metadata view's metadata fields, running top to bottom:

- Thumbnail: A scrubbable thumbnail image of your clip.
- Row 1: A main description field whose content shifts depending on which sort order you've selected.
- Row 2: Start Timecode, Date Created, Camera #.
- Row 3: Scene, Shot, Take.
- Row 4: Clip Name, Comment.

What makes the Metadata view shine is how it automatically clusters your clips in the Source Tape according to the sort order you set in the Media Pool Sort By menu at the Media Pool's far upper-right corner. Those same sort options are available in the Thumbnail, List, and Filmstrip views too.

The Metadata View icon view (its icon lit up in the top bar), with the thumbnail shown mid-scrub alongside the clip’s metadata

### The Media Sort options

The sort modes you can pick within the Metadata view are:

- Timecode: Groups clips according to creation date, sets the main description field to creation date plus start timecode, and arranges the list by timecode.
- Camera: Groups clips according to Camera #, sets the main description field to camera # plus start timecode, and arranges the list by timecode.
- Date Time: Groups clips by day, sets the main description field to creation date plus file name, and arranges the list by timecode.
- Clip Name: Groups clips by the opening letter of the clip name alphabetically, sets the main description field to clip name, and arranges the list by timecode.
- Bin: Groups clips according to bin, sets the main description field to clip name, and arranges the list by timecode.
- Scene, Shot: Groups clips according to scene, sets the main description field to sceneshot-take, and arranges the list by scene-shot-take.
- Clip Color: Groups clips according to clip color name, sets the main description field to creation date plus start timecode, and arranges the list by timecode.
- Date Modified: Groups clips by day, sets the main description field to creation date plus file name, and arranges the list by when the OS filesystem last modified the clip.
- Date Imported: Groups clips by day, sets the main description field to creation date plus file name, and arranges the list by the date the clip joined the Media Pool.
- Online Status: Groups clips according to proxy or original status.
- Ascending: Arranges the Media Pool running from the lowest numerical value up to the highest, and alphabetically

from A to Z.

- Descending: Arranges the Media Pool running from the highest numerical value down to the lowest, and alphabetically

from Z to A. Each sort mode swaps out the card's main description field and reorders the Source Tape to match the organization method you've picked.

### The Metadata view with clips sorted by Scene-Shot-Take

The Metadata view with the same clips sorted by Camera

### Thumbnail View

A scrubbable thumbnail stands in for each clip. Hover the playhead across a thumbnail and slide it left and right to watch the clip's image play, and tap the I and O keys to flag the stretches of a clip you'd like to use. You can switch hover scrub on and off from the Media Pool option menu over on the Edit page.

### The Icon View mode

A filmstrip of back-to-back frames running the Media Pool's length stands in for each clip. Hover the playhead over the clip and slide it left and right to watch the clip's image play, and tap the I and O keys to flag the stretches of a clip you'd like to use.

### The Filmstrip View mode

### List View

Each clip turns up as an entry in a multi-column list laying out an assortment of metadata about it. Within list view, click any column's header to sort the contents by that column's data (click once more and the sort order flips between Ascending and Descending). Scroll rightward to uncover further columns of information. Clicking an entry on the list may let you alter its value, depending on which column it is.

### The List View mode

### Metadata Display Palette

While you're in the Source Tape or Source mode within the Viewer, a small tag icon turns up just left of the search bar in the Media Pool. Click that icon and it switches on the Metadata Display palette atop the Media Pool. The display lays out basic information about whichever clip is selected so you can quickly skim the details of the clips you've selected.

Beside the search bar in the Cut page Media Pool sits a small tag icon (circled red) that opens the Metadata display panel atop the Media Pool. What the display shows takes in: Camera Name, Scene/Shot/Take, Frame Rate, and Resolution.

### Sorting and Searching

After media has come into your project, searching and sorting controls help you turn up what you're after.

### Searching

A search field lets you key in a term for locating one or more clips that fit that criteria. The instant you type something, the Media Pool's contents narrow down to just the clips meeting your criteria.

### Navigable Clip Paths

The Cut page's Media Pool carries a navigable

title bar laying out a clip's Media Pool hierarchy.

While you move around the Media Pool, the current clip stays

highlighted, and its hierarchy then turns up at the top of the Media Pool title bar. Clicking straight on bins along this bin path lets you swiftly widen or tighten the Media Pool's scope, say from Shoot Day to

The Media Pool title bar laying out a clip’s Media Pool hierarchy. A direct click on any of these bins tightens or widens which clips the Source tape covers.

Camera to Card to Clip and the reverse.

### Sort Media By

A Sort Media By drop-down menu lets you pick which criteria sets the order in which the Media Pool arranges its clips. Among the choices you'll find Custom, Timecode, and Camera, plus Date Time, Clip Name, and Bin, along with Scene Shot, Clip Color, Date Modified, Date Imported, and Online Status; on top of that you can sort either Ascending (bottom to top) or Descending (top to bottom). Finally, a search field lets you key in a term for locating one or more clips that fit that criteria. The instant you type something, the Media Pool's contents narrow down to just the clips meeting your criteria.

TIP: To sort by some criteria the drop-down menu doesn't list, flip the Media Pool over to List view, sort by whatever column suits you (“Date Created,” for instance), then flip back to Icon or Filmstrip view.

### The Media Pool Sort options

### Finding Timeline Clips in the Media Pool

Now and then you'll want to locate the source clip in the Media Pool that goes with a clip in the Timeline. You might, for instance, want to revisit a stretch of an interview clip you've already used so you can dig up another phrase on the same subject. To find a timeline clip in the Media Pool:

- Give a clip in the Timeline a right-click and pick Find in Media Pool off the contextual menu. Its matching clip becomes selected in the Media Pool, which scrolls into view to reveal that clip where needed.
- Where you've got several synced clips, right-click a clip in the Timeline and pick Find in Multi Source off the contextual menu. The matching clip is selected in the Media Pool and opens in the Multi Source Viewer, letting you switch to a different camera angle of the same shot.

### Clip Color

Clip colors serve as an organizational tool that makes it simpler to track different sorts of clips at a glance.

You might, for example, assign colors by good takes, by the characters or subjects in the

program, by media type (b-roll versus a-roll, say), or through any of a host of

organizational approaches—whatever helps you stay on top of the things you need to stay on top of.

Changing clip colors:

- Assign colors to clips by right-clicking one or several selected clips in the Media Pool or Timeline, then picking one of 16 available colors from the contextual menu's Clip Color submenu.

Removing clip colors:

- Strip clip colors away by right-clicking one or several selected clips in the Media Pool or Timeline, then picking Clear Color from the contextual menu's Clip Color submenu.
- Within Thumbnail view a clip color shows up as a colored dot on the clip thumbnail; within Filmstrip view it shows as a clip color; and within Column view it appears as a patch over in the Clip Color column.

### Clip color in – Thumbnail

### Clip color in – Filmstrip

### Clip color in – Column views

- Clips you've colored also appear tinted in the Timeline, much like the Filmstrip tint over in the Media Pool.

A timeline whose video clip has been given a color so the editor can tell at a glance what it is

### Relinking Media
