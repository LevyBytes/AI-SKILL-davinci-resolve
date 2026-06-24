# Adding And Organizing Media With The Media Pool (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Adding and Organizing Media with the Media Pool

Editing or grading any media first requires bringing it into the Media Pool, DaVinci Resolve's central clip repository. Packed with features, the Media Pool hands you a wide range of ways to bring clips into your project and arrange them.

### Copying Media Using the Clone Tool

A worthwhile step to take before media enters your project is cloning every piece of camera original media onto a dependable set of backup volumes, so a single volume's failure won't cost you. It's also wise to clone all media to an off-site backup on top of that. Be you a DIT on set or someone handling data ingest at a post house, the Clone Tool on the Media page copies media safely and accurately off SD cards, SSDs, or disk drives onto several destinations at once, writing a checksum report (drawn from a choice of six checksum options) to the root of every destination volume to confirm that the duplicate media stored at each destination is exactly accurate. To copy media with the Clone Tool: 1 Bring up the Clone Tool by clicking the Clone button at the far left end of the Media Pool toolbar, which exposes the Clone Tool palette. 2 Press the Add Job button at the lower left to start a new job. A job item shows up inside the Clone Tool palette, carrying overlays that walk you through its use. 3 Drag a volume or folder out of the Media Storage panel onto the "Drop source here" drop zone. As an alternative, right-click any volume or folder in the Media Storage panel and pick Set As Clone Source. 4 Then drag one or more volumes or folders from the Media Storage panel onto the "Drop destination here" drop zone. As an alternative, right-click any volume or folder in the Media Storage panel and pick Set As Clone Destination. More than one destination is allowed. 5 To keep the top-level folder name from the source volume or folder, open the Clone Tool panel's option menu and pick "Preserve Folder Name." The cloned media's overall folder structure is always kept intact. 6 To swap out the checksum method DaVinci Resolve uses for confirming each clip copied correctly, pick an option from the Checksum submenu within the Clone Tool's option menu. Every option strikes a balance between how fast your file copy runs and how secure the verification is. As a rule, tighter security comes with a slower copy. The options are: None: Switches off data verification, trading safety for speed. File Size: Quick, but only minimal data verification. It simply checks a duplicate file's size against the original's. "Collision resistance" concerns whether two files (or a file and a botched duplicate) might happen to share the same comparison value (be that file size, an error-detecting code, or a hash). File Size is extremely quick yet barely collision resistant. CRC 32: Quicker than MD5, though less secure. It's an error-detecting code rather than the hash the next three options employ. A "check value" comes from the remainder of a polynomial division of the file's contents. Lining up the check value from an original file against the one from a copy verifies data integrity. This scheme verifies data far faster than MD5 (the default) but is markedly less collision resistant. MD5: The default setting here. A sensible middle ground of speed and security. A hash function produces a 128-bit value unique to a given file; integrity is verified by matching the hash value from the original file against the one from the copied file. MD5 falls short of the SHA options for collision resistance, yet it runs faster, and such collisions are likely rare in everyday film and video workflows.

SHA 256, SHA 512: Slower, yet more secure. As a hash function, SHA resists collisions better than MD5; you get options to generate 256- and 512-bit values, where 512 is even more collision resistant than 256. These options, though, grow progressively slower than MD5 and lead to noticeably longer copy times. As with MD5, integrity is verified by matching the hash value from the original file against the one from the copied file. XXHASH64: Easily the quickest checksum method, and it still gives solid collision protection. That speed is a real boon when you're verifying terabytes of data. 7 Once you're set, press the Clone button to kick off the cloning process.

### The Clone tool with a job set up

For a fast media copy with the Clone Tool: 1. Right-click any volume or folder within the Media Storage panel and pick Set as Clone Source. A job item turns up inside the Clone Tool palette, filled with the volume or folder you chose. 2. Then right-click any volume or folder within the Media Storage panel and pick Set As Clone Destination. You may repeat this since several destinations are permitted. 3. To retain the source volume or folder's top-level folder name, open the Clone Tool panel's option menu and pick "Preserve Folder Name." The cloned media's overall folder structure stays intact at all times. 4. Once you're set, press the Clone button to begin the cloning process.

### Adding Media to the Media Pool

At the very least, the Media page is where you'll bring clips into a project to start editing, to get ready for dailies, or ahead of conforming a project with an EDL. Every clip you mean to work with has to land in the Media Pool first before it's available for grading and processing in DaVinci Resolve, whether or not edited project data accompanies it. Should you import XML or AAF projects, you have the option of pulling in all the accompanying media automatically during the import you launch from the Edit page. Still, whenever you have to swap in updated effects or stock footage on the Timeline, or you're asked to bring in extra media like animated titles or superimposed clips for compositing, the Media page is still where you'll do it.

No matter the kind of project at hand, you can pull clips into the Media Pool from as many separate volumes as you require. Each imported clip links back to the original media on whatever disks you located it; adding clips to the Media Pool moves, copies, or transcodes nothing. For that reason, it pays to confirm that any media you plan to import has already been copied onto a suitably fast volume beforehand.

### Basic Methods for Adding Media in the Media Page

Several routes exist for getting clips into the Media Pool. To bring single clips from the Media Storage panel into the Media Pool: 1 Locate a media file to import using the Media Storage panel. 2 When several bins sit in the Bin list, pick the one you want the incoming media to land in. 3 Do one of the following: Shift-click or Command-click several files, then right-click one of those selected files and pick "Add into Media Pool." Drag a clip out of the Media Storage panel browser onto the Media Pool or onto a particular bin in the Bin list. 4 Should a dialog pop up asking whether to change your project to match the criteria, press "Change" to adjust the project's settings, or press "Don't Change" to keep importing the media while the project stays at its earlier frame rate. After clips have entered the Media Pool, you can't alter the frame rate again, so decide with care. You also have the choice of dragging media straight out of supported platforms' file systems into the Media Pool. To pull one or more clips from the File System over to the Media Pool (supported platforms only): 1 Pick one or more clips within your File System. 2 Drag those clips into DaVinci Resolve's Media Pool or onto a particular bin in the Bin list. Those clips join your project's Media Pool. When you need every directory and subdirectory's contents brought into the Media Pool as one flat batch of media, that's done with ease. A fitting example is importing camera original media off a cloned file structure, where clips sit in subdirectories nested many levels down. DaVinci Resolve readily imports all those clips and drops them into a single bin. To bring one or more whole directories of clips into the Media Pool: 1 Using the Media Storage panel, locate and pick one or more directories holding media files you need to import. 2 When several bins sit in the Bin list, pick the specific bin you want the incoming media to land in. 3 Do one of the following:

- Right-click the chosen directory or directories within the Media Storage panel and pick "Add Folder into Media Pool" to pull in only the clips from that directory. Subdirectories get skipped.
- Right-click the directory within the Media Storage panel and pick "Add Folder and SubFolders into Media Pool" to pull in the clips from that directory plus those from every subdirectory inside.
- Drag one or more chosen directories out of the Media Storage panel's browser area onto the Media Pool's browser area to add its contents, together with everything in all the subdirectories inside, to whichever bin is currently selected in the Bin list.

You may likewise treat the directories and subdirectories that organize media within your file system as bins inside the Media Pool, preserving how your media was originally arranged. To bring every clip and folder in a directory into the Media Pool sorted into matching folders: 1 Locate the directory holding the files you need to import using the Media Storage panel. 2 Do one of the following: 3 Right-click the directory and pick "Add Folder and SubFolders into Media Pool (Create Bins)" 4 From the Media Storage panel, drag whichever folder you intend to import onto the Media Pool's Bin list to add that folder, plus every subfolder inside, as a new bin in the Bin list. A folder turns up in the Media Pool bearing the same name as the one you dragged in. Every clip and every subdirectory appears inside it, nested in the Media Pool's hierarchy precisely as the file system arranged them. Import Hierarchically Organized Nests of Empty Directories You're also able to bring in a nested run of directories and subdirectories that forms a default bin structure you'd like in your projects — even when those directories hold nothing — by dragging them out of your file system into a project's Media Pool Bin list. What you get is a hierarchically nested run of bins echoing the structure of the directories you imported. That's handy when you want to reuse such a run of directories as a preset bin structure for new projects.

### Adding Subclips From the Media Storage Panel

When you're looking through lengthy source clips in the Media Storage panel but only want a short piece of a far longer clip in the Media Pool, you can build subclips right from the Media Storage panel. To bring a subclip from a Media Storage panel clip into the Media Pool: 1 Give any clip in the Media Storage panel a single click to load it into the Viewer, which lets you build a subclip without first importing that clip into the Media Pool. 2 Drop In and Out points in the Source Viewer to mark the portion you want made into a subclip. 3 Do one of the following:

- Right-click the jog bar and pick Make Subclip from the contextual menu
- Drag the clip out of the Viewer onto the Media Pool to add it as a subclip

### Adding Individual Frames From Image Sequences

Whenever you handle image sequences, or sequentially numbered image files from any origin, DaVinci Resolve shows them as clips in the Media Storage panel on its own. That's fine when that's truly what they are, but sometimes batches of photos — where each frame is really a separate media file — carry sequential numbering too. On that account, you're able to import single frames rather than whole image sequences.

To decide between bringing in single frames from a numbered run of images or bringing them in as image sequence clips in the Media Storage panel: 1 Open the Media Storage panel option menu and pick Frame Display Mode. 2 Shut one of these drop-down choices: Auto: DaVinci Resolve picks Individual Frames or Image Sequence on its own according to file type. As an example, DPX and EXR files come in as image sequence clips, whereas JPG files come in as single frames. Individual: Every image sequence now breaks apart into its single frames, so you can pick just the frames you need. Sequence: Bundles sequentially numbered files into one image sequence clip, whatever the file type. 3 Apply any method described earlier to add the frames you want into the Media Pool as single clips or as image sequences.

### Adding Media Based on EDLs

Yet another approach to populating the Media Pool is leaning on an EDL to pull in only the clips it points to from a directory. That way you add nothing beyond the clips required to conform a given imported project ahead of conforming an EDL, sparing you from overloading the Media Pool — which could bog you down on projects that reference terabytes of media. On top of that, you can pick several EDLs to drive the import and many directories to scan. The EDLs point to clips through their timecode, and at times their reel name and path. Those settings, along with the conform frame rate you set earlier on the Configuration screen, are what now place images correctly into the Media Pool. To bring only the media an EDL uses into the Media Pool: 1 If need be, open the Project Settings' General Options panel, switch on the "Assist using reel names from the" checkbox, and pick a method for pulling reel name information out of the media files you're about to import. For more on this, see Chapter 19, "Using Clip Metadata." 2 Within the Media Storage panel, right-click a directory and pick one of these commands:

- Add Folder Based on EDLs into Media Pool
- Add Folder and SubFolders Based on EDLs into Media Pool

3 In the file dialog that opens, pick one or more EDLs to use. DaVinci Resolve combs the directory hierarchy — either a single level deep or every level deep — for each media file whose source timecode and reel ID match an event in one of the chosen EDLs.

### Splitting Clips Based on EDLs

EDLs can also serve to break a media file into several clips within the Media Pool, whether as another way of "preconforming" a flattened master media file or to bring in multiple stretches of a longer media file that an EDL happens to reference. To split and add clips from an EDL: 1 Within the Media Storage panel, right-click a directory and pick "Split and add into Media Pool." 2 In the file dialog that opens, pick an EDL to use and press Open. 3 In the "File Conform Frame Rate" dialog, pick a frame rate to conform the clips to and press OK. 4 In the "Enter handle size for splitting" dialog, pick a handle size in frames and decide whether to split unreferred clips, then press Split & Add. The media file gets broken into the component clips the EDL spells out and added to the Media Pool. TIP: Switching on the Split Unreferred Clips checkbox carves out the file's sections that the EDL you picked didn't reference and adds them to the Media Pool on their own, granting you access to every available piece of media.

### Import Clips With Metadata Via Final Cut Pro 7 XML

So that workflows involving media asset management (MAM) systems are covered, DaVinci Resolve offers two more Media Pool import workflows that rely on Final Cut Pro 7 XML to bring in clips along with metadata. To bring in clips with metadata through Final Cut Pro 7 XML files, take one of these routes: Right-click any empty spot in the Media Pool background, pick Import Media from XML, then within the import dialog pick the XML file you want guiding the import. From the macOS Finder, drag and drop any Final Cut Pro 7 XML file onto the Media Pool. Each clip that XML file references and that can be tracked down by its file path comes into the Media Pool, together with whatever metadata was entered for those clips. Should the file path prove invalid, you'll be prompted to browse to the directory holding the matching media. On top of that, the metadata below gets imported:

- Clips
- Browser metadata
- Subclips
- Clip Markers, with colors and duration
- Bin Hierarchy
- Comments

### Adding Media With Offset Timecode

Now and then source media ends up with wrongly offset timecode because of slip-ups made earlier in postproduction. When that offset stays consistent, the "Add Folder with Source Offset" command lets you bring media into the Media Pool as clips carrying a timecode offset. To bring a folder of clips into the Media Pool with offset timecode: 1 Within the Media Storage panel, right-click a directory and pick one of these commands:

- Add Folder with Source Offset
- Add Folder and SubFolders with Source Offset 2 In the "Change Frame Offset" dialog, pick how many frames the timecode should be offset by and press Apply.

The media enters the Media Pool as clips bearing offset timecode. The original source timecode of the clips on disk, however, stays unchanged. Any media you render from the Deliver page will carry the offset timecode.

### Import Blackmagic Cloud Shared Folders to Media Pool

Importing and syncing Blackmagic Cloud Folders into the Media Pool is now possible. Through this you can connect to one or more cloud media folders and pick and choose which media to pull down onto your local machine. Blackmagic Cloud Folders are shared online storage folders not bound to any one project. That lets you assemble a pool of frequently used media assets — title sequences, credits, bumpers, and so on — and share them online without importing them one by one into each separate project.

The Import Cloud Folder icon up at the Media Pool's top To attach a Blackmagic Cloud Folder onto your project: 1 Within DaVinci Resolve, sign into your Blackmagic Cloud account. 2 On any page, click the Import Blackmagic Cloud Folder icon up at the top of the Media Pool. 3 In the Blackmagic Cloud Folder dialog, click select to pick a Blackmagic Cloud Folder. The options shown here list any Blackmagic Cloud Folder you've created or that someone else has shared with you. Click the Add button. 4 Under Download Folder Location, pick a spot on your local system where the media from the Blackmagic Cloud Folder should be stored. 5 Decide whether to sync proxies alone or proxies plus used originals. 6 Press Download to bring the Cloud Folder into your Media Pool.

### The Blackmagic Cloud Folder link dialog

Opening the Blackmagic Cloud Folder in the Media Pool, you'll find it empty, filling one clip at a time as the clip names (not the media itself) come down from the cloud. What's more, the Blackmagic Cloud Folder isn't truly tied to your project yet; that link forms only once the first media clip gets "used." A "used" clip is fresh terminology in DaVinci Resolve, simply meaning a clip that's been changed in some way within the project. Sure, a clip counts as used when you drop it on a timeline, but other acts qualify too — flagging it, editing its metadata, transcribing it, and the like. As soon as a clip is used, its media begins downloading onto your local machine. Used clips are marked by a red dot beside them in the Media Pool. Clips left unused stay on as virtual clips in the Cloud Folder until they're used. After downloading, Cloud Folder clips work just like any other clip in the Media Pool.

The Cloud Folder shown linked in List view. Clips bearing red dots are "used," their original media downloaded. Unused clips offer only their proxies to view. The Cloud Sync column confirms the media is registered and in sync with the Blackmagic Cloud.

### Sync Media Pool Bins with File System Folders

A Media Pool bin can be kept in sync with a folder living on your computer's file system (MacOS, Windows, Linux, and the like). That way you can drop extra media into a folder on your computer and have it import to the matching bin in DaVinci Resolve by itself. To set up a folder for Automatic Syncing: 1 Over on the Cut page, use the top menu bar's Import Folder icon to establish matching folder and sub folder names. 2 Right-click the imported folder and pick "Automatically Resync Media Files."

Use the Import Media Folder icon in the Cut page

Right-click on the bin and select Automatically Resync Media Files

Fresh clips dropped into this folder join the media bin on their own. This proves handy with cloud-synced media files (such as when you're using DaVinci Resolve's Replay capabilities), or with any files that might get added to the folder down the line. To resync a Media Pool bin's contents once by hand, right-click a bin and pick "Resync Media Files."

Right-click the bin and choose Resync Media Files to run the sync by hand.

For both Resync actions, ensure that:

- At least one clip sits in the media bin.
- Every clip already in the media bin shares one common file path.
- The media bin's name matches the parent folder of the clip paths. To get this set up properly, rely on the Cut page's "Import Media Folder" command, or else the Media page's "Add Folder and SubFolders into Media Pool (Create Bins)" command.

A sync action pulls in new clips from sub-folders provided the matching sub-bins exist. Sub-folders newly created without matching media bins, though, go untracked, and new media bins lacking matching sub-folders get passed over. Picture, for instance, editing a sporting event where a graphics operator is building animated lower-thirds for each player. Set up a shared network folder named "CG" and sync it automatically in DaVinci Resolve, and every time a new lower-third is finished and saved it would show up in your Media Pool bin on its own, ready to use. Here's the way you'd set this up:

- Make a folder named "CG" on your network storage. The editor and the graphics operator both need access to this folder.
- Bear in mind that since this folder is empty for now, it can't take part in a Resync action yet. Only once the folder holds at least one media file can you run a Resync.
- The graphics operator wraps up his first animated lower third and saves it into the "CG" folder as a .mov file (though any media format DaVinci Resolve can read would do).
- The editor next brings the "CG" folder into the Media Pool in DaVinci Resolve and chooses Automatically Resync Media Files from the context menu.
- As the graphics operator wraps up and saves more lower thirds into that folder, they surface in the Editor's "CG" bin in the Media Pool on their own, with no need to import them specifically.
- To stay organized, the graphics operator then makes a new folder inside "CG" for the other team, named "Team B." Regrettably, since that folder structure wasn't part of the originally imported bin, it doesn't appear in the editor's media pool. Had they made this Team B folder before the editor imported, with media inside it, it would have been there.
- Here, then, the editor merely imports that same bin once more, chooses Automatically Resync Media Files, and the new folder along with all its media shows up as expected. Anything dropped into "Team B" afterward will surface in the editor's media pool.

IMPORTANT: Media entries for clips that get removed or can't be found on the file system are marked as offline media. This keeps the metadata around and comes in handy when the clip path is temporarily offline, sits on cloud storage where file status may be shifting, or has been moved aside by apps or workflows looking to write a new version in its place.

### Adding Media to the Cut, Edit, Fusion, and Fairlight Pages
