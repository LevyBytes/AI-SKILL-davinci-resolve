# Rendering Media (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Render speed: A dropdown that lets you rein in how fast media renders. Normally you'd keep it at its default of Maximum. That said, certain storage setups shared across several rooms in a facility rely on storage area networks (SANs) that lack the bandwidth for many real-time image streams at once. The blazing render speeds of DaVinci Resolve can trip up playback for other people hitting the SAN when there isn't enough bandwidth to go around. Here you can rein the render speed in, capping SAN bandwidth usage at somewhere between 1 to 50 percent of full rendering speed.
- Disk space currently used: Reports how much disk space remains free on the target volume.
- Disk space used after render: Reports the projected disk usage given the specified range of the session you're currently rendering.

### Additional Outputs

Every job you set up in the Render Settings starts out with one output. Even so, you can build several outputs whenever you have to deliver more than one version of media — each with its own video formats and codecs and distinct data burn-in settings — to render into separately named subfolders (optional).

The menu command that creates an extra output, displayed beside an output already present in panel 2 This comes in handy for arranging several rendered passes when a client wants two sets of media — say, QuickTime ProRes 422 (HQ) media together with MXF DNxHD media. It also helps when you have to put out two media sets, one carrying window burns and the other clean.

To add additional outputs in the Render Settings:

- Pick Create Additional Output off the Render Settings Option menu. Beneath the Filename and Location controls sits a row of numbers that opens each output you build so you can tune its settings. There's no cap on how many outputs you make.

To remove an additional output:

- Open the additional output panel you'd like gone, then click the Delete button along the bottom.

### How to Avoid Overwriting Clips When Rendering Output Media

The three options covered above — "Use unique filenames," "Place clips in separate folders," and "Use commercial workflow" — each give you a way to organize rendered media so rendered clips that share a file name don't overwrite each other. They're needed because every clip carries a single logical span of timecode, and because many clips frequently point back to one source media file bearing one name. As it renders a clip, DaVinci Resolve will overwrite any other media files carrying the same name automatically. So when you're aiming to hold onto the source media file's earlier filename, or putting out several versions of one clip, the clips you mean to output stand a real chance of clobbering one another, leaving only the last clip rendered. Those three options each head this off in their own way.

### Defining a Range of Clips and Versions to Render

With the Render Settings set, your next call is how much of the Timeline to render. A Mini-Timeline plus a Thumbnail timeline are on hand to help you move through your project's clips and settle on which to render. Track controls let you switch whole tracks in or out of the output; for instance, to render a textless version of a timeline where every title clip lives on track V4, just disable track V4. On top of that, these same controls let you decide which clip versions get rendered. To render the entire Timeline:

- Pick Entire Timeline off the Render dropdown in the Deliver page timeline. This choice surfaces only when clips aren't filtered.

To switch off a video or audio track so its clips stay out of the render:

- Click the Video or Audio Disable Track button on whichever tracks you mean to leave out.

To render only a filtered portion of the Timeline's clips: 1 Bring up the Color timeline if it isn't showing, then pick an option off the Timeline Filter dropdown sitting to the right of the Clips button in the Interface toolbar. The Thumbnail timeline then narrows to display only clips that fit the chosen criteria. Say you already rendered a session but have made changes since — you can reach for one of the "Show Modified Clips" options to surface just the clips altered within a certain stretch of time. Or pick the "Show Unrendered Clips" option to reveal every clip not yet rendered. 2 Pick "All Filtered Clips" off the Render dropdown in the Timeline toolbar.

To clear clip filtering:

- Pick All Clips off the Timeline Filter dropdown sitting to the right of the Clips button in the Interface toolbar.

To define a continuous range of clips to render: 1 To mark the first clip of the range you mean to render, take one of these steps:

- On a clip thumbnail within the Thumbnail timeline, right-click and choose Mark In.
- Park the playhead in the Timeline or the Viewer and tap the I key, or right-click the

Timeline ruler and choose Mark In. 2 To mark the last clip of the range you mean to render, take one of these steps:

- On a clip thumbnail (within the Color timeline) or a clip (within the Edit timeline) in the Thumbnail timeline, right-click and choose Mark Out.
- Park the playhead in the Timeline or the Viewer and tap the O key; alternatively right-click the Timeline ruler and choose Mark Out.

In and Out points show up within the Timeline ruler, and an orange bar marks out the range you've picked to render. The In and Out fields refresh with the first and last frame numbers, in timecode and frame count, while the Duration field refreshes with the total frame count you're about to render. IMPORTANT: When you're in Individual Clips mode, In and Out points snap by themselves to the nearest clip In or Out point on the Timeline. Partial clips can't be rendered in Individual Clips mode, though you can render them in Single Clip mode.

To render a single clip:

- Open the Thumbnail timeline if it's not up yet, right-click any clip thumbnail, and choose Render This Clip.
- An orange bar on the Timeline ruler signals that clip is queued for rendering. To render several clips one by one, pick each clip individually to add it as its own job to the Render Queue.

### Choosing Which Versions to Render for Each Clip

By default, whatever version is currently selected back on the Color page gets rendered per clip. To render a different one, the simplest move is making sure they're selected on the Color page Timeline before the Deliver page is opened. Still, a Versions submenu — sitting in the Thumbnail timeline's contextual menu for each thumbnail — also gives you options for managing grade versions. Those commands mirror what the Color page's Thumbnail timeline already offers. To pick the version that gets rendered:

- Right-click any clip thumbnail in the Thumbnail timeline, then pick a version off the Versions submenu.

TIP: From the Thumbnail timeline of the Color or Render screen you can right-click a clip and rename any version of a grade. That can smooth a facility's workflow when material moves between suites and applications.

### Using the Render Queue

After you've nailed down the settings needed to render the media you want, plus the slice of the current session to render, you add it all as a job to the Render Queue. Pile on as many jobs as you like, depending on which files you need to output. Each job can carry its own clip ranges and its own clip settings, covering different render directories, formats, resolutions, data levels, burn-in settings, and more. That means the Render Queue can line up renders of several sections of the current session, or several versions of the same media. You can even line up several sessions, if you've got a few differently graded ones. To add a job to the Render Queue: 1 Pick a timeline. 2 Dial in the settings you want over in the Render Settings, either through one of the Presets or by setting your own custom values. 3 Pick a range of clips to render via the Deliver page Timeline, following the steps laid out in the section above. 4 Click the Add to Render Queue button along the bottom of the Render Settings. 5 If no render location has been chosen yet, a File Destination dialog now prompts you for one, so pick a spot and click Ok. Should media already sit in the render location you named, a dialog may also warn you "This render may overwrite existing clips in this folder." To press on, click Yes; otherwise click No. That render setup now joins the Render Queue as a job, displaying the project and timeline name plus the location path the render will be written to.

### A selected job in the Render Queue

Media Offline Warning in Render Queue Should you try adding a job to the Render Queue whose timeline holds any offline material, DaVinci Resolve throws up a warning on its own. You can either back out of adding the job, or add it regardless, aware you're set to render one or more offline clips.

The Media Offline warning box that pops up when a timeline carrying offline clips or frames gets added to the Render Queue

To show more details about jobs in the Render Queue: Open the Render Queue Option menu (at the upper right-hand corner) and pick Show Job Details. Beneath the name and location path, every job then spells out its frame size and format, the frame rate, the audio channels alongside sample rate, plus the duration.

A selected job in the Render Queue with job details shown

To rename a job: A job takes a custom name when you simply click its default name (Job 1, Job 2, and so on) and type one of your own. That's handy for labeling jobs you expect to re-render again and again as a project moves along. To start rendering: 1 To limit rendering to only certain jobs in the Render Queue, pick one or more by clicking a job, then Command-clicking others for a scattered set, or Shift-clicking another to grab a whole stretch of jobs. Once you pick one or more jobs, only those selected get rendered. With nothing selected, the queue's every job gets rendered. 2 Click the Start Render button, found below the Viewer over on the right of the interface. 3 Should the Render Queue hold jobs already rendered, a dialog asks whether, since the selection includes items already rendered, you'd like to re-render those. Click Yes to re-render every job in the Render Queue. Click No to render only the jobs not yet done. Click Cancel to scrap the whole rendering operation. Rendering kicks off from the topmost job in the list. The Overall Progress bar begins filling, right to left, showing how much of the queue has rendered so far. As rendering runs, the Start Render button becomes the Stop Render button, which you can click any time to stop rendering. TIP: While a render is underway, a small progress bar appears over the DaVinci Resolve icon — in the Mac OS X dock, or down on the Windows taskbar.

To remove jobs from the Render Queue, do one of the following:

- To clear a specific job: In the Render Queue, click the X up at the top right of that job's entry.
- To clear all previously rendered jobs: Open the Render Queue Option menu (at the upper righthand corner) and pick Clear Rendered.
- To clear all jobs: Open the Render Queue Option menu (at the upper right-hand corner) and pick Clear All.

To flip a rendered job back to looking unrendered: Right-click any rendered job and pick Clear Render Status. Several jobs can also be grabbed to switch their rendered status all together. That makes re-running the exact same job simple. To edit a job, whether or not it's been rendered: 1 In the Render Queue, click the Pencil button to select it.

Clicking the pencil icon to revise a Render Queue job The chosen Render Queue's settings reload into the Render Settings list and reset the Timeline's selected range matching that job. 2 Adjust whatever settings you need. 3 Once you're done editing the job, click the Update Job button that shows up at the bottom of the Render Settings, or click Add New Job to spin up a fresh job carrying your changes while the earlier job stays put. NOTE: Click the Pencil button again without having clicked Update Job and you'll be prompted to Save, Cancel, or Don't Save.

To look over the clips tied to rendered jobs: To surface a rendered clip within the Media Storage browser: Right-click any rendered job and pick Reveal in Media Storage. To bring up a rendered clip within your computer's own file system (Mac OS only): right-click a rendered job, then pick Reveal in Finder.

### Rendering Jobs from Multiple Projects at Once

You can likewise drop several projects from the open PostgreSQL or local project library into the render queue all in one go. That proves especially handy when you've split a program into multiple reels, each reel a separate project. Rendering output across several projects in one pass goes like this: 1 Open each project, line up whichever jobs you want rendered in the Render Queue, and save that project without rendering it. 2 After the last project is set up, open the Render Queue Option menu (at the upper right-hand corner) and pick Show All Projects. Every queued item across projects owned by the currently selected user (on a network project library) or held in the currently named disk location (on a local project library) now shows in the Render Queue.

3 Hit Start Render and rendering runs through every job across every project queued up. 4 Once you're done, switch Show All Projects off to return to showing only the current project's render queue items.

### Remote Rendering

When several DaVinci Resolve workstations share one network, you can hand a job in the Render Queue off from the machine you're on (called the "artist workstation") to one of the network's "remote workstations" through remote rendering. This puts any of your idle secondary workstations to work rendering your jobs while you keep going on your main one. To make use of remote rendering, you have to meet the following three criteria:

- DaVinci Resolve Studio has to be installed on both the artist workstation and the remote workstation. The free version of DaVinci Resolve won't do remote rendering.
- The artist workstation and the remote workstation can both draw on the same shared network project library, or any other Postgres project library tied to either machine, or to a dedicated Remote Project Library Server.

For a fuller account of configuring and working with shared project libraries, turn to Chapter 196, “Managing Project Libraries and Project Servers.”

- Both the artist workstation and the remote workstation have to reach the same media files, whether on the same storage volumes or on identically named ones.

### Using Multiple Project Libraries in Remote Rendering

Remote renders can be set up for projects across every connected Davinci Resolve project library, not solely the one that's active. To switch this on, tick the "Automatically scan other project libraries for Remote Rendering jobs" box under the General settings of the System tab, within the DaVinci Resolve Preferences.

### Sharing Storage

For remote rendering to behave, it matters that both the artist and remote workstations can reach the same media on the same named storage volume. One route is shared storage of some kind, such as a SAN. Another is mounting the same volume across your network. That's slower, but it does the job. When remote rendering spans a mix of Mac OS X, Windows, and Linux workstations, you'll need the Mapped Mount column found in the Media Storage Locations list, which sits within the System Preferences' Media Storage panel; there you add each volume's path as the workstation it's attached to understands it. As an example, on a Windows workstation reaching volumes off a Linux workstation, enter the Linux-style file paths in the Mapped Mount column for every scratch disk shown.

### Setting Up and Using Remote Rendering

Remote rendering is simple to use, though it takes a little setup. 1 Confirm the storage volume holding the media the project you mean to render points to is mounted on both the artist and remote workstations. 2 Launch DaVinci Resolve on the remote workstation, then take one of these steps:

- As the Project Browser opens, right-click anywhere and choose Remote Rendering.
- If a project is already open in DaVinci Resolve, you can instead choose Workspace >

Remote Rendering. DaVinci Resolve jumps straight to the Deliver page on its own, sitting ready for jobs to be handed over for automatic rendering. 3 Back on the artist workstation, queue up a job in your usual way. 4 For that job in the Render Queue, click the Remote Rendering button and one of the choices the list presents: Any: Hands the job off automatically to whichever workstation isn't busy rendering at the moment. Should every remote rendering workstation already be busy, it queues the job to run next. YourComputer.local: The artist workstation bearing the name "YourComputer." Pick this to render the job right here locally rather than out on the network. Other Workstations on Network: Every other remote rendering workstation appears below, letting you point the job at one particular machine.

Clicking the Remote Render button to send a job out for remote rendering 5 Click Start Render. The job heads off to the remote workstation you chose and renders there, leaving you free to keep working at your artist workstation.

### When You’re Finished Remote Rendering

After you've finished running a given DaVinci Resolve workstation in Remote Rendering mode and want it back as an artist workstation, choose Workspace > Remote Rendering to leave remote rendering and head back to the Project Manager.

### Setting Up a “Headless” Remote Rendering Workstation

DaVinci Resolve lets remote rendering clients run in a so-called "headless" mode without any GUI. You pull this off from the command line: open the directory where the app sits, then launch DaVinci Resolve in Remote Rendering (–rr) mode with the command line syntax that fits your operating system. Launched like this, DaVinci Resolve sits silent and out of sight on that machine, ready for any remote rendering jobs routed to it. On macOS Launch Terminal. Switch into the directory: cd /Applications//DaVinci\ Resolve/DaVinci\ Resolve.app/ Contents/MacOS/ Then issue: ./Resolve -rr On Windows Launch the Command Prompt. Switch into the directory: C:\Program Files\Blackmagic Design\DaVinci Resolve\ Then issue: Resolve.exe -rr On a Linux CentOS 6.8 system Launch Terminal. Switch into the directory: cd /home/resolve/Cyclone/ Then issue: ./script.start -rr On a Linux CentOS 7.x system Launch Terminal. Switch into the directory: cd /opt/resolve/bin Then issue: ./resolve -rr
