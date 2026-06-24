# Managing Project Libraries And Project Servers (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Managing Project Libraries and Project Servers

This chapter walks through configuring and working with project libraries at a deeper level, handing you finer control over the way projects get saved and arranged. It covers configuring local, network, and cloud project libraries that you can lean on to administer DaVinci Resolve projects shared across several DaVinci Resolve workstations.

### What is a Project Library?

A Project Library (once called the project database) is a database file that holds one or more DaVinci Resolve projects. Whenever you build or open a project from the Project Manager, or save the current one, you’re reading from or writing to a project library. One project library houses many projects, and each project in turn carries every timeline, grade, clip metadata, visual effect, audio mix, and so on for your film. What a project library doesn’t keep is the original media; it stores only the directions for turning that media into a finished film. DaVinci Resolve can reach many project libraries, yet it links to just one project library at any moment.

### Using Project Libraries

Laying out a scheme for how projects and project libraries get stored matters a great deal to building lean, efficient workflows. Spinning up a dedicated project library per TV series, commercial, or film a post house handles, for instance, keeps your clients compartmentalized and boosts performance by loading only what a given project actually needs. DaVinci Resolve reaches project libraries in three ways, and which one fits depends largely on how many people share a project and where in the world they sit. Each path is laid out below.

- Local Project Libraries: (the default option) Suits productions that finish the whole film on one workstation. Several people might contribute to one project, but they take turns on the same machine. Here your project libraries live locally on the computer that has DaVinci Resolve installed, and every media drive the project uses is attached locally.
- Network Project Libraries: Suits post houses or productions with several DaVinci Resolve workstations under one roof that want to tackle the same project from any room, or together at once. Here your project libraries sit on a separate computer that runs the DaVinci Resolve Project Server application. Every workstation has to join that computer over the same local area network (LAN), and each must either reach the same media drives through a NAS or MAM system or hold a locally attached copy (or proxies) of the media.
- Cloud Project Libraries: Suits post houses, companies, or productions whose DaVinci Resolve workstations are spread across different parts of the globe and that want to work the same project from each spot on their own, or jointly at the same time. Here your project libraries reside in the Blackmagic cloud service. Every workstation must have internet access, and each system needs a locally attached copy (or proxies) of the media on hand.

The three types of Project Libraries: local, network, and cloud Moving around and operating the Project Libraries sidebar plays out the same way for every type of project library above.

- Project Library: Every reachable project library shows by name, and a click on one hooks that library and the projects inside it up to DaVinci Resolve. Plenty of libraries are available to pick from, though only a single library stays active at once.

Project Libraries sidebar controls (L-R): Sort, Restore, Search

- Sort Libraries: Chooses the order in which the project libraries are listed; the options are Name, Schema (date), Status, and Location. Either Ascending or Descending order is available.
- Restore: Lets you load back a project library you backed up earlier.
- Search: Lets you hunt down a particular project library by text, with the search narrowable by

Name, Schema, Status, and Location.

### Local Project Libraries

Local project libraries are the most basic and widespread kind of project library, demanding no extra setup or configuration from the user beyond installing DaVinci Resolve. They’re saved locally on your workstation; out of the box they land in a folder named Resolve Disk Database, although you can put them by hand anywhere across your file system.

### Creating a New Local Project Library

Making a fresh local library is quick and uncomplicated. To Create a New Local Project Library: 1 Click the Show/Hide Project Libraries icon at the top left of the Project Manager to reveal the sidebar. 2 Pick the Local icon from the Project Library options. 3 Click the “Add Project Library” button along the bottom of the sidebar. 4 Pick the Create option to build a new project library. 5 Type a fresh name for your project library. 6 Hit the Browse button beside Location to choose where on your local computer the project library is saved. 7 Hit the Create button. From here you can build or import new projects straight into your new local project library.

### Creating a local project library

### Connecting to an Existing Local Project Library

You can hook back up to a project library that already exists by following the steps below. To connect to an existing project library: 1 Click the Show/Hide Project Libraries icon at the top left of the Project Manager to reveal the sidebar. 2 Pick the Local icon from the Project Library options. 3 Click the “Add Project Library” button along the bottom of the sidebar. 4 Pick the Connect option to reach the existing project library. 5 Type a fresh name for your project library. 6 Hit the Browse button beside Location to point to where on your local computer the folder holding the existing project library sits. It’s usually called “Resolve Disk Project library.” 7 Hit the Connect button. From here you can browse and use every existing project straight from the existing local project library.

### Connecting to an existing local project library

### Disconnecting from a Local Project Library

You can detach and drop an existing project library from the Project Libraries list with the steps below. To disconnect from a project library: 1 Click the Show/Hide Project Libraries icon at the top left of the Project Manager to reveal the sidebar. 2 Pick the Local icon from the Project Library options. 3 Right-click the project library you’d like to detach from, and choose disconnect off the context menu. 4 Hit the disconnect button in the confirmation dialog. Detaching a project library merely strips it from the available options in the Project Libraries sidebar. It leaves the project library itself intact. You can either remove it by hand in the OS filesystem, or reconnect to it via the steps outlined in Connecting to an Existing Local Project Library.

### Duplicating Project Libraries

Local Project Libraries may be duplicated within the same database for backup or iteration purposes. 1 Right-click the Library and choose Duplicate from the dropdown menu. 2 Choose the Resolve Database Folder in the file system browser. That can be the very one you use for the original project or a brand new one. 3 Click the Open button. 4 Give the new Library a name in the Clone Library dialog.

### Backing up a Local Project Library

You can likewise back up project libraries by exporting them and reimporting them down the line. To backup/export a project library: 1 Choose the library you intend to back up. 2 Click the Display Project Library Details icon — that’s the “i” inside a circle, sitting just right of the library.

The Display Project Library Details icon 3 Choose the Back Up button. 4 Within the Backup Project Library dialog, settle on a save location, then click Save.

### Restoring a Local Project Library

Bringing in project libraries that already exist lets you carry multiple projects across systems. To restore/import a project library: 1 Up along the top of the Project Libraries sidebar, click the Restore button.

The Restore button 2 Through the file import dialog, find the library you wish to import, and click Open. 3 Within the Add Project Library dialog, handle the following: a) Into the Name field, enter a name for the new project library. That renames the imported one while leaving its contents alone. Nothing stops you from reusing the same name as the original project library. b) Click inside the Location field and, via the Filesystem navigation dialog, point to the directory where the existing DaVinci Resolve project libraries reside. 4 Click Create; the imported local project library then appears within the Local section of the Project Libraries sidebar.

### Upgrading a Local Project Library

A selected library shows an upgrade warning in the Project Manager only once you’ve installed a newer DaVinci Resolve build and you hold project libraries made under older DaVinci Resolve versions that are due for upgrading.

The upgrade warning in the Project Manager signals that a project library is due to be upgraded. As a rule it’s smart to back up a project library before upgrading it, in case anything goes sideways. Broadly, going from one whole version release of DaVinci Resolve to the next whole version release usually calls for an upgrade, whereas moving to a dot release of the same version might or might not. Should the project library in use need updating, you’ll hear about it when the application launches. To bring a project library forward from an outdated DaVinci Resolve build: Click whichever project library needs updating, then choose the Upgrade Project Library button. A dialog pops up to make sure you truly intend to upgrade that project library. Click Upgrade to carry on.

### Network Project Libraries

Several DaVinci Resolve workstations can reach the same project once you stand up a Project Server that shares one or more network project libraries across a local network. With that in place, there are two approaches to using a shared project library.

### Multiple Users Sharing Projects

The most straightforward case has users just open a project on the Project Server and get to work. Working like this, should you ever need to switch rooms or workstations, you can readily open that same project from any machine joined to the server on the same network, with no need to export and import it first. As an example, an assistant might team up with a colorist to ready files for the next reel — conforming shots, handling VFX replacements, doing dust busting repairs, and the like — within an unsupervised editing suite somewhere in the building, then save and close the project so the colorist can open that same project right away in the grading theater across the hall. A second way to capitalize on shared Project Servers is to carve large projects into sections, letting several artists work in parallel on different chunks of the whole across different suites, passing them off as required. For instance, a feature film might be carved into reels, or a film can be separated from

the trailer and electronic press kit projects with which it shares media. Here each project can be cut, mixed, and graded by different people tapping into the Project Server. When someone opens a shared project that another person already has open, a dialog tells you it’s opening in Read-only mode so that multiple users can’t reach the project simultaneously. If you load a Read-only project yet decide you want to make edits regardless, you’ll have to use the Save As command to spin off a duplicate project file under a fresh name in order to keep your work.

### Using Collaborative Workflow for Network Project Libraries

As an alternative, the Collaborative Workflow features in DaVinci Resolve let several collaborators on several workstations across several rooms open and work the exact same project at the same time. For example, one editor can cut a project’s main timeline in one room while an assistant arranges media and adds metadata within the same project in a second room, and a colorist grades dailies in that same project in a third, all reaching the same Project Server that lets them work side by side in parallel. For more detail, refer to Chapter 197, “Collaborative Workflow.” Everyone taking part in a Collaborative Workflow has to be on a network project library hosted by a properly configured Project Server.

### Connecting to a Network Project Library on a DaVinci Resolve Project Server

What chiefly sets a local project library apart from a network project library is that the network project library lives on another computer joined to the same network and running the DaVinci Resolve Project Server. Configuring the Project Server itself is dealt with further on, yet anyone who works network projects within DaVinci Resolve should understand the way a local workstation connects out to the Project Server. Once the hardware and software are installed (in essence, every computer joined to the same network, all running DaVinci Resolve, with one computer running the Project Server), you must authorize your computer to reach the network project libraries on the Project Server, and that’s managed through “keys.” To gain access to a network project library you have to be handed a key for it that the Project Server generates. The key is nothing more than an .xml file bearing the extension “.resolvedbkey”. To rely on an access key for a hassle-free connection to a Project Server: 1 Start DaVinci Resolve, and once the Project Manager appears, reveal the Project Libraries sidebar. 2 Grab the .resolvedbkey file and let it drop at any spot inside the Project Manager. 3 At this point the shared project library ought to surface in the Project Libraries sidebar, and selecting it reveals all the projects sitting in that project library on the Project Server. You might also have been registered as a Member of the Project Server and given your own username and password. Where that applies, consult the section “Connecting to an Existing Network Project Library” below. After you’ve joined a network project library, managing it works just as it would if you were connected locally.

### Creating a New Network Project Library

Spinning up a fresh network project library is quick and uncomplicated. To create a new network project library: 1 At the upper left of the Project Manager, click the Show/Hide Project Libraries icon so the sidebar appears. 2 From the Project Library options, choose the Network icon. 3 Along the bottom of the sidebar, click the “Add Project Library” button. 4 Choose the Create option to build a new project library. 5 Give your project library a fresh name. 6 Supply the IP address for whatever DaVinci Resolve Project Server you’re connecting to. 7 As a Member of the Project Server, enter your Username and Password; otherwise lean on the default user: postgres and password: DaVinci. 8 Click the Create button. From here, fresh projects can be built or imported right into your new network project library.

### Creating a network project library

### Connecting to an Existing Network Project Library

Joining a project library already present on a Project Server is a matter of working through the steps below. To connect to an existing project library on a Project Server: 1 At the upper left of the Project Manager, click the Show/Hide Project Libraries icon so the sidebar appears. 2 From the Project Library options, choose the Network icon. 3 Along the bottom of the sidebar, click the “Add Project Library” button. 4 Choose the Connect option so as to reach the existing project library. 5 Enter the project library’s name as it sits on the Project Server. 6 Provide the IP address for whatever DaVinci Resolve Project Server you’re connecting to. 7 As a Member of the Project Server, enter your Username and Password; otherwise lean on the default user: postgres and password: DaVinci. 8 Hit the Connect button. From here, every existing project can be browsed and used right from the existing network project library.

### Connecting to an existing network project library

### Disconnecting from a Network Project Library

You can detach and drop an existing project library from the Project Libraries list with the steps below. To disconnect from a network project library: 1 At the upper left of the Project Manager, click the Show/Hide Project Libraries icon to reveal the sidebar. 2 From the Project Library options, choose the Network icon. 3 Single out the library you mean to detach. 4 Click that Display Project Library Details icon — the circled “i” positioned to the library’s right. 5 Choose the Remove button. 6 In the confirmation dialog, hit the disconnect button. Detaching a project library merely strips it from the available options in the Project Libraries sidebar. It leaves the project library itself intact. You can either remove it by hand in the OS filesystem, or reconnect to it via the steps outlined in Connecting to an Existing Local Project Library.

### Backing up a Network Project Library

Exporting project libraries and pulling them back in later is another route to backing them up. To backup/export a network project library: 1 Single out the library you intend to back up. 2 Click that Display Project Library Details icon — the circled “i” over to the library’s right. 3 Choose the Back Up button. 4 Inside the Backup Project library dialog, name a destination for the backup, then click Save.

### Restoring a Network Project Library

Bringing in project libraries that already exist is how you shuttle multiple projects from one system to another. To restore/import a network project library: 1 At the top left of the Project Manager, click the Show/Hide Project Libraries icon so the sidebar appears. 2 From the Project Library options, choose the Network icon. 3 Up at the top of the Project Libraries sidebar, click the Restore button.

The Restore button 4 Through the file import dialog, track down the library you want imported, and click Open. 5 Within the Add Project Library dialog, do this: a) Give your project library a fresh name. b) Key in the IP address of whichever DaVinci Resolve Project Server you’re reaching. c) Should you be a Member of the Project Server, hand over your Username and Password. If not, rely on the default user: postgres and password: DaVinci. d) Click the Create button, whereupon the imported local project library shows up in the Network section of the Project Libraries sidebar.

### Duplicating a Network Project Library

You can also clone a network project library for an extra backup, or as a save point partway through a large project. To duplicate a network project library: 1 Single out the library you intend to duplicate. 2 Click that Display Project Library Details icon, the circled “i” sitting to the library’s right. 3 Choose the Duplicate button. 4 Pick a fresh, one-of-a-kind name for the duplicated library and click OK.

### Optimizing a Project Library

Now and then, project libraries in DaVinci Resolve swell to a size that drags on performance. When that happens you may have to optimize them to quicken access by “vacuuming” the project library of needless spaces and reindexing it. The Optimize command can also prove a worthwhile troubleshooting move in certain situations where you’re struggling to open, import, or otherwise work with projects held in network project libraries. To optimize a project library: 1 Single out the library you mean to optimize. 2 Click that Display Project Library Details icon — the circled “i” to the right of the library. 3 Click the Optimize button. 4 Up comes a warning dialog. Hit Optimize to carry on, or click cancel to leave the project library exactly as it is.

### Sharing a Key to a Network Project Library

If you wish, your access key for a network project library can be handed to a fellow user sharing the same local network. To send a network project library’s key outward: 1 At the upper left of the Project Manager, click the Show/Hide Project Libraries icon so the sidebar shows. 2 From the Project Library options, choose the Network icon. 3 Single out the library whose key you intend to share. 4 Click that Display Project Library Details icon — the circled “i” to the right of the library. 5 Click the Share Key button. 6 Choose the file-system directory where the key should be saved and click save. 7 Pass the resulting .resolvedbkey file on to the other user.

### Using the DaVinci Resolve Project Server Application

A stand-alone application, DaVinci Resolve Project Server hands you the means to create, manage, backup, restore, and — above all — share project libraries on any workstation. Thanks to it, firing up DaVinci Resolve just to manage your project libraries becomes unnecessary.

### Installing the DaVinci Resolve Project Server

The hardware and software needed to install the DaVinci Resolve Project server is spelled out in the User’s Guide document bundled with the program download. The first time it launches, you’re shown a screen for setting up an Admin account for the server. That account grants you full permissions to tweak any facet of the project libraries and to change the Project Server itself.

The first time it launches, the DaVinci Resolve Project Server prompts you to create an administrator account.

### The DaVinci Resolve Project Server Interface

The DaVinci Resolve Project Server interface closely mirrors the DaVinci Resolve Project Manager with the Project Libraries sidebar open. It does, however, surface every project library management tool there is for creating and handling project libraries, including controls for sharing project libraries and minting access keys that are key to quickly and easily creating and joining Project Servers.

### The DaVinci Resolve Project Server window

Three principal UI areas make up this window:

- Project libraries list: Within the Project Server application, the Project libraries list lays out each DaVinci Resolve network project library present on your machine — disconnected ones included. That ease of view helps you locate libraries you’d like to reconnect.
- Projects browser: Displays all projects and folders inside the currently selected project library, either as icons or as a hierarchical list.
- Toolbar: A toolbar across the top of the window presents the functions on hand for managing DaVinci Resolve project libraries on your workstation.

Project Libraries toolbar controls (L-R): Sort, Restore, Search

The three controls along the top of the Project Libraries toolbar serve these purposes:

- Sort Order dropdown menu: Through this menu you decide the ordering of the assorted local and network project libraries shown in the sidebar. You can sort on Database Name, on Schema (by date), on Status, or on Location, each in either Ascending or Descending order.
- Restore: Brings in .resolve.backup files to restore a backed up project library.
- Show Search Field: Reveals a search field plus a search criteria dropdown that lets you find project libraries in the sidebar by Name, Schema, Status, or Location.

Clicking the Display Project Library Details icon — the circled “i” found to the library’s right — opens up further information below each database in the sidebar and brings out the Backup and Optimize buttons.

### The Display Project Library Details icon

The controls surfaced within the Project Library details serve these purposes:

- Project Library Settings: A click on this gear icon lets you opt to Rename, Delete, or Export an Access Key for the library.
- Project Library Enabled: This toggle switches the project library sharing on or off.
- Project Library Information: Surfaces the library’s metadata — among it Location (the Project Server’s IP address), Status (either compatible or upgrade required), plus the dates it was created and modified.
- Backup: A click on this button lets you export the project library out to a backup file.
- Optimize: A click on this button lets you optimize the project library for stronger performance.
- Members: This region shows you which members hold access to the project, and the Manage Members button lets you grant or revoke their access.
