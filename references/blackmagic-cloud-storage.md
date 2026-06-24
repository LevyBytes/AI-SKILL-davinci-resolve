# Blackmagic Cloud Storage

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Blackmagic Cloud Storage

This chapter walks through configuring and working with your Blackmagic Cloud Storage.

Blackmagic Cloud Storage gives your media assets and proxies one secure, central home on the internet. What you do with that home is entirely your call — anything from a many-user collaboration spanning the globe, to a lone editor grabbing their laptop and walking away from the workstation, to nothing fancier than a safe backup of footage off an aging spinning hard drive. Blackmagic Cloud Storage ties in fully with DaVinci Resolve as well as the established Blackmagic Cloud service. Every Blackmagic Cloud user, whether brand new or long-standing, receives a capped allotment of free storage. Signing in at cloud.blackmagicdesign.com lets you reach that storage and buy project libraries and/or extra storage. The user plans and their prices are spelled out there. The Free Storage can be used to:

- Upload camera captures from the Blackmagic Camera app.
- Downloads require logging into the Blackmagic Cloud Website,

and pulling the clips down by hand. The Paid Storage can be used to:

- Sync media and proxies for DaVinci Resolve Cloud collaboration projects.
- Remote Camera Collaboration from the Blackmagic Camera app.
- Upload camera captures from the Blackmagic Camera app.

### The Cloud Storage interface

### Using the Blackmagic Cloud Storage Web App

Opening the cloud storage tab over on the Blackmagic cloud website brings up a media interface where you can browse and view the clips belonging to particular cloud projects.

### The Storage Spaces interface

### Selecting Storage Spaces

Your Storage Spaces appear in the left pane. They break down into your Cloud folders, Personal Storage, Project Libraries, plus any project libraries Shared With Me from other users. Beside the storage space picker sits a sort and search tool for locating and ordering your projects by name. Down at the bottom you'll see your usage data, laying out how much media you've consumed and how much Cloud Storage space remains free.

### Storage Space type selection

- All Storage: Surfaces every project library on offer plus your personal storage.
- Cloud Folders: Surfaces media held in your shared cloud storage folders — folders you can share around yet that aren't

attached to any specific project.

- Personal Storage: Surfaces media from your own personal folders, which carry no link to any

specific project.

- Project Libraries: Surfaces media drawn from your cloud project libraries.
- Shared With Me: Surfaces media out of the cloud project libraries belonging to other users that they've

shared with you.

### Using the Cloud Storage Media Interface

After you pick a Storage Space, every piece of media tied to it surfaces in the Cloud Storage Media interface. There you can view thumbnails of the clips, reach a clip's metadata, and download or remove clips.

### The Cloud Storage Media interface

Running along the top of the interface is a toolbar for navigating, sorting, and carrying out delete and download actions on your clips.

### The Media Interface toolbar

- Storage Space Panel: Pressing this icon flips the left Storage Spaces panel into view or out of it.
- Navigate Up one Level: Pressing the “<“ icon walks you one step higher within the file hierarchy.
- Navigate File Hierarchy : Lays out the file path within your project as a drop-down menu, so you

can leap straight to particular enclosing folders.

- Search: Lets you hunt down clips by their file name.
- Sort: Lets you arrange the clips on screen by name, size, modified and created times, plus

kind — running either ascending or descending.

- List View: Shows the clips in List view.
- Thumbnail View: Shows the clips in Thumbnail view.
- New Folder: Creates a new bin in the Project.
- Information: Shows the metadata associated with the clip.
- Option Menu: Shows media operations; currently these are:

Download: Pulls a chosen clip, or several, down from the cloud storage onto your computer. Delete: Removes folders or clips out of a project. There's no undoing this action.

Park the pointer above the thumbnail, then glide the mouse one way or the other to scrub the clip Scrubbing Video Clips Resting your pointer over a clip's thumbnail lets you scrub the clip both directions to take in its whole stretch of media. Just rest over the clip and drag the red line left and right across it with your mouse. Selecting Multiple Clips Picking several clips for an operation in the Media Interface works precisely the way it does in DaVinci Resolve. A blue outline ringing the chosen clips, plus an on-screen note along the bottom, tells you which clips are selected and how many.

- Selecting a Range of Clips: Shift-click, or drag a bounding box across whichever clips you mean to grab.
- Selecting Individual Clips: Command-click whichever clips you mean to grab.

### Viewing Clip Metadata

With the Information icon active in the toolbar, a clip's metadata shows up to the right of the Media Interface. You can read this metadata in the Blackmagic Cloud Storage web app, though you can't change it there. Editing a clip's metadata has to happen from the File inspector in DaVinci Resolve.

Choosing the Info icon on the Media Interface toolbar surfaces a clip's metadata for reading, though not for editing.

### Cloud Folders

Cloud Folders are shared online storage folders with no link to any single project. That lets you build up a stockpile of frequently reused media assets — music, title sequences, credits, and the like — and pass them around online rather than importing them one by one into every separate project.

### The Cloud Folders section of Cloud Storage

Making a fresh cloud folder goes like this: 1 Within the Storage Space type drop-down, pick Cloud Folders. 2 Press the Create Cloud Folder icon, sitting just to the right of the Storage Space drop-down. 3 Give the new Cloud Folder a name. 4 Drop in whatever media you'd like the folder to share. Sharing that cloud folder goes like this: 1 Over in the Cloud Folders interface, press the “i” information icon up in the toolbar's top right. 2 Open the Sharing tab. 3 Press the Sharing Settings button down at the foot of the tab. 4 Type in the user email addresses of whichever Blackmagic Accounts you'd like as recipients. 5 Press Save. Those users get a notification that the shared folder is now theirs to reach, and they can open it in DaVinci Resolve by hitting the “Import Blackmagic Cloud Folder” icon over in the Media Pool, covered later on in this chapter.

### Personal Storage Folders

You're also free to set up personal media storage folders that only your account can reach — not shared with anyone else and not bound to any single project. At the time of writing, personal folders live only in the web interface and have no tie-in with DaVinci Resolve. Making a fresh personal folder goes like this: 1 Within the Storage Space type drop-down, pick Personal Folders. 2 Press the Create Cloud Folder icon, sitting just to the right of the Storage Space drop-down. 3 Give the new Personal Folder a name. 4 Drop whatever media you'd like into the folder.

### Setting up a Blackmagic Cloud Project in DaVinci Resolve

Standing up a project built on Blackmagic Cloud became smoother and simpler with 18.6, which lets you settle every configuration option — Blackmagic Cloud Storage among them — on one no-fuss setup screen. NOTE: Before Blackmagic Cloud will work for you, register a Blackmagic Cloud account over at cloud.blackmagicdesign.com, after which you sign into that account from within DaVinci Resolve. Standing up a new Cloud Project goes like this: 1. Inside DaVinci Resolve's Project Manager, choose Cloud out of the Project Library options over in the top left. Your Blackmagic Cloud Library ought to be live (lit up in orange). 2. Press the New Project button, or right-click the background and choose New Project off the contextual menu. Alternatively, bring in a local DaVinci Resolve project you already have and want folded into the Blackmagic Cloud. 3. Set whatever options suit you in the Create New Cloud Project dialog. 4. Press the Create button.

Select Remove Unused Clips from the Media Pool optwion menu

Through the Create New Cloud Project dialog box you settle where your project's media lives and how it gets shared.

- Name Your Project: Key in a name for your Cloud Project.
- Choose a Location for your Project Media: Pick a spot on your file system to hold the imported

media files, graphics, and audio files you plan to draw on for the project.

- Share Project with Multiple Users?: Lets you decide whether this project gets shared out to

other users. Allow Multiple Simultaneous Users: Turns on collaboration mode so several people can work the same project at once. Set Project to Single User: Switches collaboration mode off, built for a lone person on the project at any given time.

- Synchronize Storage with Blackmagic Cloud?: Through these options you decide which media gets uploaded and synced to your Blackmagic Cloud Storage account so other users can reach it.

Don't Sync Media: Sends no media at all up to Blackmagic Cloud Storage. Sync Proxies Only: Pushes only proxy media to Blackmagic Cloud Storage. Sync Proxies and Originals: Pushes the proxies together with the original media to Blackmagic Cloud Storage. Depending on how much original media there is and how big it runs, this can eat a huge quantity of storage.

- Allow Remote Camera Access: Governs the access rights granted to people using the Blackmagic Camera app.
- Allow Remote Cameras Access: Lets Blackmagic Camera app users who belong to this

project send media off their phones up to the Blackmagic Storage account, dropping it straight into the project's Media Pool.

- Don't Allow Remote Cameras: Bars Blackmagic Camera app users from sending footage up to this project, even when they're members of it. Once Create is pressed, a fresh project comes into being carrying whatever parameters you dialed in above.

Should you ever want to revise these parameters once a project already exists, you can reach them again by opening the Project settings and choosing the Blackmagic Cloud tab.

Every cloud setting on an existing Blackmagic Cloud project stays adjustable from the Project Settings.

### Blackmagic Cloud Sync Manager

While you have a project open in a cloud library, a handful of the most-used cloud management functions are within reach straight away by clicking the Blackmagic Cloud Sync Manager down in the lower right of the interface. That icon surfaces only while you're working in a cloud library.

The Blackmagic Cloud Sync Manager brings up a spread of handy cloud management tools. Reading the top bar Left to Right, here's what's on hand: Pause/Resume Sync: Halts or restarts how media uploads and downloads from the host computer. Enable/Disable Multi User Collaboration: Brings up a dialog box for flipping between Set to Single User and Allow Multiple Users (collaboration mode). Enable/Disable Camera Capture: Brings up a dialog box for flipping between Allow and Don't Allow, governing whether Blackmagic Camera app users push footage to storage and bring the clips into the project's Media Pool. Open in Finder/File Explorer: Pops open the Project Media Location within the computer's file system. Open Settings: Pops open the Blackmagic Cloud tab inside the Project Settings window. Go to Blackmagic Cloud Storage: Launches your web browser onto the Blackmagic Cloud Storage page out on the internet.

Beneath that toolbar sit two status areas. The upper one names the user signed into the Blackmagic Cloud account along with how much Blackmagic Cloud Storage is spent and how much remains. Its ring display puts the grand total of all media in the outer ring, the share synced locally in the middle ring, and the amount still waiting to upload in the inner ring. The lower one tracks how the media sync is coming along over the internet. Its top display carries the progress bar for the sync status plus how much material is yet to sync. Right below that, the media list calls out the clip syncing right now together with a roll of media already synced.

### Automatic Proxy Generation and Upload to Blackmagic Cloud Storage

While you're on the Media, Cut, Edit and Fairlight pages, DaVinci Resolve is able to spin up proxies on its own in the background to push to Blackmagic Cloud. No matter which page you're on, you can still trigger proxy media generation by hand from the media pool to set uploads going. Switching automatic proxy generation and upload on goes like this: 1 Within the Project Settings, press the Blackmagic Cloud tab. 2 Inside the “For media files” section, press “Sync proxies only.” 3 Tick the “Generate proxies automatically” box. 4 Inside the “Proxies are created as” section, choose the codec you'd like the proxy format rendered into. 5 Press the Save button. Switching automatic proxy generation and upload off goes like this: 1 Within the Project Settings, press the Blackmagic Cloud tab. 2 Inside the “For media files” section, press “Don't sync media.” 3 Clear the “Generate proxies automatically” box. 4 Press the Save button.

### Cloud Storage Sync Icons

Whenever you work inside a cloud library, Sync icons ride at the upper left of a clip in the Media Pool, telling you where each clip stands in the cloud.

### The Proxy Processing icon in the upper left

White Cloud with 3 Dots: Signals that proxy media is in the middle of being processed right now.

### The Upload Queue icon in the upper left

### The Successful Sync icon in the upper left

Yellow Cloud with an Up Arrow: Signals that the clip is waiting its turn in line to head up to the cloud.

White Cloud with a Checkmark: Signals that the clip made it up and synced to the cloud without a hitch.

### Sync Specific Media Originals in Proxy Synced Cloud Projects

Within Blackmagic Cloud projects that sync only proxies up to Blackmagic Cloud, you're able to sync originals for particular files in the Media Pool. That comes in handy when you have to upload or download originals for a few files but not the whole set. Just right-click the Media Pool clips whose originals you want, and pick Sync Original Media from the context menu.

Picking out single media proxies lets you pull down the originals for only those particular clips

### Import Blackmagic Cloud Shared Folders to the Media Pool

You're now able to import and sync Blackmagic Cloud Folders straight into the Media Pool. This lets you hook up to one or several cloud media folders and pull media down from them to your local machine on a pick-and-choose basis. Blackmagic Cloud Folders are shared online storage folders with no tie to any single project. That lets you assemble a stockpile of frequently reused media assets — title sequences, credits, bumpers and so on — and pass them around online instead of importing them one by one into every separate project.

The Import Cloud Folder icon sitting atop the Media Pool Tying a Blackmagic Cloud Folder to your project goes like this: 1 Sign into your Blackmagic Cloud account from within DaVinci Resolve. 2 On any page, press the Import Blackmagic Cloud Folder icon up at the top of the Media Pool. 3 Within the Blackmagic Cloud Folder dialog, press select to pick a Blackmagic Cloud Folder. What shows up here is every Blackmagic Cloud Folder you've built yourself or that another person has shared your way. Press the Add button. 4 Under Download Folder Location, point to a spot on your local system where the media out of the Blackmagic Cloud Folder should land. 5 Decide whether you'd rather sync proxies alone, or proxies plus used originals. 6 Hit Download to fold the Cloud Folder into your Media Pool.

### The Blackmagic Cloud Folder link dialog

When you first open the Blackmagic Cloud Folder in the Media Pool, it starts out empty and fills in a clip at a time as the clip names (rather than the media itself) arrive from the cloud. On top of that, the Blackmagic Cloud Folder isn't truly tied to your project yet; the link forms only once the first media clip gets “used.” The term “used” clip is fresh terminology in DaVinci Resolve, meaning nothing more than a clip that's been changed in some fashion within the project. Dropping a clip on a timeline counts as using it, of course, but so do other moves like flagging it, editing its metadata, transcribing it, and similar. As soon as a clip is used, its media begins downloading to your local machine. A red dot beside a clip in the Media Pool marks the ones that are used. Whatever clips go unused stay on as virtual clips inside the Cloud Folder until they're used. After they download, clips in Cloud Folders behave just like any other clip in the Media Pool.

The Cloud Folder shown linked in List view. A red dot marks the “used” clips, whose original media has come down already. Clips left unused offer only their proxies for viewing. Over in the Cloud Sync column, you can confirm the media is registered and in sync with the Blackmagic Cloud.
