# Managing Projects And Project Libraries (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Managing Projects and Project Libraries

What this chapter walks through is using the Project Manager to keep the projects you have underway in DaVinci Resolve in order, plus handling the project libraries that act as the organizational backbone of the Project Manager. It also shows the steps for exporting and importing projects, and for archiving a project together with its media so it can be kept over the long term.

### Using the Project Manager

As a rule, the Project Manager is the very first window that greets you once DaVinci Resolve launches. It serves as a handy, single hub for making, arranging, and overseeing every project you have. Whereas other applications lean on your file manager to keep projects in order, DaVinci Resolve expects you to carry out the bulk of project organization inside the Project Manager.

### Project Manager

When a project is already open, you can bring the Project Manager back up whenever you like by clicking the Home button down in the lower right-hand corner of the DaVinci Resolve window, on the Page Navigation bar. Should you have tucked the Page Navigation bar away at the foot of the DaVinci Resolve window, the Project Manager can be opened through File > Project Manager.

Down in the bottom-right corner of the DaVinci Resolve interface sits the Project Manager button Launching DaVinci Resolve for the First Time? When DaVinci Resolve is freshly installed and you’ve just launched it the first time, the moment has come to set the preferences so you can declare your language, scratch disk volume, and the hardware setup for video and audio I/O and control panels (should you own one). To read more about configuring the preferences in DaVinci Resolve, see Chapter 4, “System and User Preferences.”

### Creating a New Project

Your initial move in DaVinci Resolve is making a new Project within the Project Manager, which handily is the very thing that appears when the program starts. Every project holds links to all the media, graphics, and sound files that go into your film, plus timelines on which the editing, color correction, motion graphics, and audio post tasks are carried out. A number of settings, options, and preferences ride along with each project (reach them by clicking the small gear icon down in the far bottom right of the interface), and every one of them gets a full description further along in this section. Even so, bringing a project into being really comes down to only four steps. Creating a New Project: 1 Down at the foot of the Project Manager, hit the New Project button. 2 Enter a name for the project you’re making. 3 Note the folder shown in Media Location where DaVinci Resolve will keep any media it creates. Confirm there’s room to spare on that drive. A click on the Change Location button lets you pick a different drive/folder rather than the default. 4 Click the Create button.

### The Create New Project dialog

### Project Management

For making, renaming, and removing projects, the Project Manager supplies an in-application interface. A good many of these commands sit in the contextual menu that appears once the Project Manager’s background gets a right-click. Methods of project management:

- To create a new project: Give the Default Project icon a double-click, or hit the New Project button at the foot of the window. A fresh project appears, and DaVinci Resolve brings up the Media page. With a project open, its project settings can be changed by clicking the gear icon.
- To open a previously saved project: Give any Project icon a double-click, or an Item if you happen to be in List view. Selecting a project and clicking the Open button works too.
- To open a project in Read-Only Mode: Give a Project icon or Item a right-click, then pick Open in Read Only Mode. That opens a project with no risk of changing it. Should you make edits, the Save As command will store a fresh copy of the project under a new name.
- To rename a project: Right-click a Project icon or Item, pick Rename, and type a fresh name into the dialog that pops up, clicking OK once you’re done.
- To load project settings from another project to the currently open project: On a Project icon or Item (any one besides the project that’s currently open), right-click and pick “Load Project Settings to Current Project.” That lets you adjust a project’s settings before opening it, handy when those settings are triggering some sort of issue that keeps the project from opening.
- To update the thumbnails of a project in the Project Manager: On any project, right-click and pick “Update Thumbnails.”
- To delete a project: Pick one or more projects, then either tap the Backspace key, or right-click one of the chosen projects and pick Delete. Click OK once a dialog prompts you to confirm the action.

NOTE: The project that is currently open or loaded cannot be moved or deleted.

### Importing and Exporting DaVinci Resolve Projects (.drp Files)

The file extension DaVinci Resolve gives saved projects is .drp, which lets you trade files with fellow DaVinci Resolve users. Double-clicking a DaVinci Resolve .drp file within the Windows or macOS file system will, on its own, launch DaVinci Resolve, bring that project into the Project Manager no matter which kind of project library is in use, and open it so you can get straight to work. Importing and Exporting Projects in Local Project Libraries When local project libraries are how you manage your projects, you can copy and import projects through the project folders in either the macOS or Windows file manager. On DaVinci Resolve for Linux this approach doesn’t function. Shifting projects out of one local project library and into another by way of macOS or Windows: 1 Track down the local project library directory in which the project you mean to copy sits. If you’re not sure where the designated local project library directory lives, open DaVinci Resolve and read the directory path for the current local project library off the Project Libraries sidebar. 2 Copy the project folder off the source workstation and into the designated local project library directory on the destination workstation. If you’re still unsure where the designated local project library directory lives, open DaVinci Resolve on whichever workstation you’re copying the project to, then check that workstation’s current local project library directory path inside the Project Libraries sidebar. 3 After the project folder is copied into the right spot, you’ll have to quit DaVinci Resolve and start it again. The imported project ought to turn up in the Project Manager afterward. Importing and Exporting Projects in Network Project Libraries When a network project library is in use, a separate group of commands handle importing and exporting projects via the .drp file format. You may likewise export .drp files out of local project libraries should you wish to send out a more self-contained item for transport. To import a .drp project file, do one of the following:

- Click the Import button at the foot of the Project Manager, then locate and pick a .drp project file by way of the Import Project File dialog, and click Open.
- Take the .drp file you intend to import from your file system and drop it anywhere within the Project Manager window.
- Right-click any blank spot of the Project Manager and pick Import, then locate and pick a .drp project file by way of the Import Project File dialog, and click Open.

To bring in a .drp project file while also resetting the gallery path in one go:

- Keep the Option key held while right-clicking any blank spot of the Project Manager, and pick Import+, then locate and pick a .drp project file, and click Open. As it opens, the gallery path is set automatically to match your workstation’s.

To export the currently open project as a .drp file:

- Pick File > Export Project, and once the Save dialog appears, settle on a location, type a name, and click Save. What you get is a self-contained file carrying a .drp file suffix stored at the location you picked.

To export a .drp project file from the Project Manager:

- Click the Export button at the foot of the Project Manager, and once the Save dialog appears, settle on a location, type a name, and click Save. What you get is a self-contained file carrying a .drp file suffix stored at the location you picked.
- Right-click a Project icon or Item within the Project Manager, then pick one of the commands below;

Export Project: Exports the project data carrying no LUTs and no stills. Ideal when the smallest possible file is what you need to export. Export Project With Stills and LUTs: Exports the project together with both the still frames in the Gallery and the LUTs your grades rely on. Ideal when you want the most self-contained export and can’t be sure the recipient holds the same LUTs you do.

- Once the Save dialog appears, settle on a location, type a name, and click Save. What you get is a self-contained file carrying a .drp file suffix stored at the location you picked.

TIP: Several projects can be exported from the Project Manager at once, either by command-clicking or lassoing the projects, right-clicking one of them, and choosing Export Projects off the drop-down menu. Every project lands at the same location.

### Project Manager View Options

Up at the top right, four buttons govern the way projects display inside the Project Manager.

### Select Thumbnail or List View

- Zoom slider: (Shows up only in Thumbnail view) Lets you change the thumbnails’ size within Thumbnail view.
- Project Sort Order drop-down: (Shows up only in Thumbnail view) Lets you set the order in which projects sort within Thumbnail view.
- Information: (Shows up only in Thumbnail view) Lets you reveal or conceal extra project information shown beneath each project’s thumbnail, taking in the frame size, how many timelines it holds, and the date that project was last modified.
- Thumbnail view: A large image stands in for each project, and you can hover-scrub it to bring out five sample images drawn from that project.

### Hover-scrub over Project icon; information is enabled

- List view: Each project shows up as a list entry, and the row carries these seven columns — Name, Last Modified, Timelines, Format, Frame Rate, Date Created, plus Note. Click any column header to order the Project Manager’s contents by that field; a second click on the header flips that column between ascending and descending order.

### Project List view

### Searching for Projects

A click on the magnifying glass button up at the Project Manager’s top right-hand corner reveals the Search Options, which serve to track down one or more projects by way of the metadata picked in the Filter By drop-down menu just to its right. Search field open with Filter by search criteria selected Through that drop-down menu you can opt to search by name or by project format. With a criteria chosen, start typing in the search field, and the Project Manager begins filtering by your search text instantly and on the fly.

### Organizing Projects in Folders

When you have a lot of projects to keep in order, folders can be made to hold them.

### A folder in the Project Manager

Methods of working with project folders:

- To create a folder: Hit the New Folder button, then type a name into the Create New Folder dialog and click Create.
- To delete a folder: Right-click a folder, pick Delete, and click Yes at the prompt. Every project sitting in a deleted folder gets deleted along with it.
- To rename a folder: Right-click a folder, pick Rename, then type a fresh name and click OK.
- To copy a folder: Right-click a folder and pick Copy off the drop-down menu, or select the folder and tap Command-C. Whatever projects sit inside that folder are copied as well.
- To paste a folder: With a copy made, right-click the Project Manager’s background and pick Paste off the drop-down menu, or tap Command-V. You may paste into other project libraries, into other folders, or into the very same spot, where a fresh copy of the folder picks up the word (Copy) at its end. Every enclosed timeline copies over too.
- To open a folder: Give a folder a double-click to open it and see what’s inside. Up at the Project Manager’s top left-hand corner, a folder path view tells you which folder stands open, along with your spot inside a nested chain of folders if that’s how you’ve arranged things.
- To exit a folder: Reach for the path control along the top of the Project Manager and click a higher tier in the folder hierarchy.
- To move a project into a folder: Drag the project over a folder icon and drop it there to set it inside the folder.
- To move a project out of a folder: Open a folder, pick one or more projects you intend to move, then right-click the selection and pick Cut off the contextual menu. Next, head to the next spot in the Project manager where you want the cut projects placed, right-click the Project Manager’s background, and pick Paste. The projects ought to show up in their new spot.

### Managing Project Libraries

Whereas other applications write self-contained project files to whatever user-specified spots you choose across your file system, DaVinci Resolve leans toward a more centrally arranged style of project management built on project libraries. Out of the box, DaVinci Resolve relies on a local project library to keep tabs on each project you make. The Project Libraries sidebar is where you manage the projects held inside this project library, all of which are stored to a particular directory on your system (specific to that project library). Where this local project library sits by default hinges on which operating system you run.

That said, you’re free to make extra project libraries for holding other projects if you wish. As an example, you might set up one project library for each year you work. If your work is series television, you could spin up multiple project libraries, one per program you handle. Or you might keep a separate project library for every client you serve. No rigid rule applies; in the end, the way you put project libraries to use comes down entirely to you and your own organizational tastes.

### Project Library Types

There are three different project library types in which project libraries can be kept, each functioning much the same but offering extra connectivity and sharing features that depend on how your network is set up. You pick the Library Type over at the upper left of the Project Manager.

- Local: Keeps your project libraries on your workstation locally. It is the default and suits individual users or single systems best.
- Network: Keeps your project libraries on an outside computer wired to several workstations across the same local network. It also lets you govern who may access the project library. It suits a facility made of multiple workstations in one building working on the same material best.
- Cloud: Keeps your project libraries within the Blackmagic Cloud. This lets several workstations reach the same project library across the internet. It also lets you govern who may access the project library. It suits multiple people working on one project from scattered locations around the globe best.

The three types of project libraries: local, network, and cloud. To read more about setting up and configuring the various project library types, see Chapter 196, “Managing Project Libraries and Project Servers.”

### Opening the Project Libraries Sidebar

When several project libraries already exist, a click on the button up in the Projects Browser’s upper-left hand corner reveals a sidebar down the left side of the Project Manager that lists every project library on your workstation, complete with assorted options for managing those project libraries and for browsing the projects inside them. This sidebar serves to open different project libraries and to browse the projects held within.

### Project Libraries sidebar button

Project Manager with the Project Libraries sidebar displayed

### Moving Projects From One Project Library to Another on the Same Workstation

Having relied on multiple project libraries to keep your projects in order, you can browse what each project library holds to hunt down whatever you’re after, then copy one or more projects between project libraries should you need to shuffle how they’re arranged. To view the contents of a project library: 1 Open the Project Libraries sidebar via the button up in the Projects window’s upper-left hand corner. 2 Click a project library in the sidebar to select it, and an orange highlight will show up If a project was already open, a prompt asks whether to save it before closing, because every open project must be shut before another project library’s contents can be inspected. After that, the projects belonging to that user inside the selected project library show up in the Project Manager window.

To pull a project in from a different project library by way of the Project Libraries sidebar: 1 Reach for the button in the upper-left hand corner of the Projects window and open the Project Libraries sidebar with it. 2 Click a project library in the sidebar to select it, and if you must, use the drop-down menu over at the right of the project library listing to settle on a specific user. The projects belonging to that user inside the selected project library show up in the Project Manager window. 3 Pick a project you intend to import, and tap Command-C to copy it. 4 Click the current project library once more to select it (the project library you mean to work inside). 5 Tap Command-V to paste the project you copied. A copy lands in the current project library. For fuller detail on how shared project libraries are set up and run, consult Chapter 196, “Managing Project Libraries and Project Servers.” To bring Project Settings in from another project through the Project Libraries sidebar: 1 Using the button tucked in the Projects window’s upper-left hand corner, bring up the Project Libraries sidebar. 2 Pick a project you intend to import Project Settings into so that it’s highlighted. 3 Right-click any project and pick “Load Project Settings to Current Project.” The settings of that project get copied onto the project you picked back in step 2.

### Managing Project Libraries in the Project Libraries Sidebar

The controls inside the Project Libraries sidebar make it straightforward to spin up new project libraries (through the button at the bottom), upgrade project libraries that carry a flag (through circular badges), import and export project libraries (through buttons at the top), and surface extra information about each project library (through buttons up at the top of this sidebar).

### Project Libraries sidebar controls

The trio of controls up at the top of the Project Libraries sidebar serve these purposes:

- Sort Order drop-down menu: Through this menu you decide the way the assorted local and network project libraries in the sidebar get ordered. The available keys are Project Library Name, Schema (by date), Status, or Location, each usable in either Ascending or Descending order.
- Restore: Imports .resolve.backup files to restore a backed up project library.
- Show Search Field: Brings up a search field plus a search criteria drop-down letting you hunt for project libraries in the sidebar by Name, Schema, Status, or Location. A click on the Display Project Library Details icon (the circled letter “i” over to the right of the project library) brings up extra information below each project library in the sidebar. Exactly what information depends on the project library’s type. Local project libraries show their status (compatible/incompatible) plus their location (directory path). For network and cloud project libraries, what’s shown is the schema (its created and modified dates), the status (compatible/incompatible), the IP location, and underneath, whichever members can reach the project library.

### Creating and Connecting to Project Libraries

Local, network, and cloud libraries can run side by side so you can switch over to one or the other as your needs dictate. The instructions here cover setting up local project libraries. Network and cloud libraries call for extra configuration and setup beforehand. Network and cloud project library setup and operation are covered more fully in Chapter 196, “Managing Project Libraries and Project Servers.” To build a fresh local project library: 1 In the Projects window’s upper-left hand corner, click the button that opens the Project Libraries sidebar. 2 Hit the Add Project Library button down at the foot of the sidebar. 3 Move to the Create tab and click it. The Add Project Library window ought to resemble the screenshot below:

Creating a local project library 4 Across the remaining fields, proceed as follows: a) Into the Name field, enter a name for your new project library b) Click inside the Location field and lean on the Filesystem navigation dialog to pick the spot for the directory destined to contain every DaVinci Resolve project directory 5 Hit Create, after which the new local project library appears within the local project library portion of the Project Libraries sidebar. To hook up with a local project library that already exists: 1 Click the Projects window’s upper-left hand corner button, the one that brings up the Project Libraries sidebar. 2 Hit the Add Project Library button down at the foot of the sidebar. 3 Switch over to the Connect tab and click it. The Add Project Library window ought to resemble the screenshot below:

Connecting to an existing local project library 4 Across the remaining fields, proceed like so: a) Into the Name field, type a name for the new project library. b) Click inside the Location field and lean on the Filesystem navigation dialog to point at where the existing project library you mean to connect to resides. 5 Click Connect, and the new local project library surfaces inside the local project library section of the Project Libraries sidebar.

### Duplicating Project Libraries

Inside one and the same database, you can duplicate Local Project Libraries for backup or iteration purposes. 1 Give the Library a right-click, then pick Duplicate off the drop-down menu. 2 In the file system browser, choose the Resolve Database folder. That may be the very one backing the original project, or else a fresh one. 3 Click on the Open button. 4 Give the new Library a name inside the Clone Library dialog.

### Backing Up and Restoring Project Libraries

Project libraries can also be backed up by exporting them and then reimported at a later time. To backup/export a project library: 1 Open the Project Libraries sidebar through the button sitting in the upper-left hand corner of the Projects window. 2 Choose whichever project library you mean to back up. 3 Hit the Display Project Library Details icon (that circled letter “i” over to the right of the project library).

The Display Project Library Details icon 4 Click the Back Up button. 5 In the Backup Project Libraries dialog, settle on a location to store the backup, and click Save.

To import a project library: 1 Hit the button over in the upper-left hand corner of the Projects window so the Project Libraries sidebar opens. 2 Up at the top of the Project Libraries sidebar, click the Restore button.

The Restore button 3 Locate, through the file import dialog, the project library you need to bring in, and click Open. 4 Within the Add Project Library dialog, carry out the following: a) Into the Name field, supply a name for the new project library. That renames the project library you’re importing without disturbing what it holds. Giving it the original project library’s name is fine too. b) Click inside the Location field and turn to the Filesystem navigation dialog to settle on whichever directory contains the DaVinci Resolve project libraries already present. 5 Hit Create, and the local project library you imported turns up in the Local section of the Project Libraries sidebar.

### Upgrading Project Libraries

A selected library shows an upgrade warning within the Project Manager only once you’ve installed a fresh version of DaVinci Resolve while holding project libraries built under older versions of DaVinci Resolve that are due for upgrading.
