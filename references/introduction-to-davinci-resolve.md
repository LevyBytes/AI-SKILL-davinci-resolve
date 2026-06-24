# Introduction To Davinci Resolve (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Introduction to DaVinci Resolve

Within one application that does not take long to pick up, DaVinci Resolve brings together a full sweep of disciplines: editing; compositing and motion graphics; color correction; the recording and mixing of audio; and finishing. Seasoned artists arriving from other programs will recognize the editing, compositing, grading, and audio tools in DaVinci Resolve right away, while those new to post-production will still find them welcoming. On top of that, a set of purpose-built on-set tools folds jobs like media duplication, shot and metadata organization, and on-location look management into one cohesive toolset, carrying you seamlessly from the camera original media captured in the field through to organizing and using that footage across a broad spread of post‑production pipelines, all centered on DaVinci Resolve. Because DaVinci Resolve is woven together so tightly, you can glide from one stage of your project to the next without a hitch — backing up and sorting a shoot’s media, then plunging straight into the cut, ducking over to drop in a fast composite or grade a handful of clips mid-edit, hopping back to cutting, and adding a touch of mixing to confirm the sound holds up, none of it asking you to export the project or launch another program. You can push further still: the collaborative features of DaVinci Resolve let several artists — an editor, a colorist, and assistants, say — share one timeline at the same moment, the very height of an integrated workflow. Naturally, no post-production professional works in isolation, and DaVinci Resolve smooths the handoff with other facilities by importing projects and exporting project exchange formats plus rendered or managed media. Among the programs it interchanges with are these: Apple’s Final Cut Pro X; Premiere Pro from Adobe; Media Composer and Pro Tools by Avid; Autodesk’s Flame Premium; and a good many more — all riding on solid XML, AAF, and EDL import and export support. What this chapter sets out to do is walk you through the DaVinci Resolve user interface (UI): where each cluster of features sits, and how the sharply focused, closely knit Media, Edit, Fusion, Color, Fairlight, and Deliver pages work in concert so you can take on just about any post‑production workflow you might dream up. After this quick tour, the rest of Part 1 digs much deeper into project management, preferences, project settings, and other subjects worth knowing as you get under way.

### The Project Manager

For the majority of people, the Project Manager is the very first window that greets them on launching DaVinci Resolve. It acts as one central hub for handling every project owned by whoever is signed in at the moment — that person’s name shows up in the project title bar over at the top right. Through the Project Manager you also bring projects into and send them out of DaVinci Resolve, whether shuttling them between users or moving them from one DaVinci Resolve workstation onto another. On top of all that, the Project Manager, by way of the Project Library sidebar, lets you arrange the project libraries that DaVinci Resolve uses to keep track of everything. Double-click any project to open it. For a fresh one, double-click the Untitled Project icon or press the New Project button.

Every project owned by the signed-in user is on display in the Project Manager. To dig deeper into the Project Manager, turn to Chapter 3, “Managing Projects and Project Libraries.”

### Preferences and Project Settings

After a project is open, you may tune the System and User Preferences that steer how DaVinci Resolve is installed on your workstation, along with the Project Settings that steer the project currently open. The installer’s onboarding questions already pick the weightiest of these settings when you first install DaVinci Resolve. Still, on your very first launch of DaVinci Resolve it is wise to look these over and confirm they suit your system.

### Individual Preferences and Settings Based on Login

Beginning with DaVinci Resolve 16, every login account on a given computer carries its own preferences and settings. So several artists can each keep a personal login, and DaVinci Resolve holds onto distinct workspace layouts and preference states per artist, swapping them according to who is signed in.

### Preferences

Split into System preferences and User preferences panels, the Preferences window is where you shape the broad environment of your DaVinci workstation — deciding which hardware DaVinci Resolve should use and which user interface settings you favor while working.

The DaVinci Resolve preferences let you set up your environment

Below you will find a brief rundown of the System and User preferences that matter most, plus pointers on which settings to tackle first as you get DaVinci Resolve going on your workstation. For the full picture and further detail, though, consult Chapter 4, “System and User Preferences.”

### System Preferences

Through the System preferences you set up the hardware that DaVinci Resolve talks to. Should your rig stay much the same over time, you may scarcely open the Preferences window at all. But if you run a mobile setup whose video interfaces, control panels, and scratch volumes keep shifting, you will likely turn to this window far more often. NOTE: Alter certain core System Settings in the Preferences and you may need to quit and relaunch DaVinci Resolve before those changes kick in. Memory and GPU Offers an array of options that govern how the GPUs in your computer get used and how Viewers are configured across the various pages. For reference, this panel also lays out every hardware and computer trait that bears on DaVinci Resolve running smoothly, the installed GPUs among them. Media Storage Here sits a list in which you spell out the scratch disk your system relies on. Because the first volume on this list holds Gallery stills and cache files, you will want to point it at the fastest connected storage volume. Decode Options These controls let you pick from assorted hardware options for decoding RAW files along with H.264/H.265. They also let you turn on the easy DCP decoder and the option to refresh growing files (those still being written) inside the Media Pool. Video and Audio I/O The settings in this panel decide which video and audio Capture and Monitor interfaces DaVinci Resolve draws on at your workstation. Where several Blackmagic Design I/O interfaces are hooked up, you get to choose among them. Video Plugins Any third-party Open FX plugins you have installed show up here, ready to be enabled or disabled. Audio Plugins Likewise, installed third-party VST plugins appear here for you to enable or disable. Control Panels Lets you select and, if need be, configure a connected control panel for use while grading in DaVinci Resolve.

General Gives you a spread of settings that tweak how DaVinci Resolve behaves. By way of the LUT Locations section you can direct DaVinci Resolve to whatever external folders hold the LUTs your project needs. Internet Accounts This panel acts as a login manager for the Blackmagic Cloud and various social media sites. Advanced You turn to this tab for special DaVinci Resolve configurations and for SAN parameters that pertain to older file systems.

### User Preferences

User preferences steer how the user interface in DaVinci Resolve is set up, so you can shape it to suit your taste. UI Settings Up top, a Language drop-down menu lets you state which language the DaVinci Resolve user interface shows. At present DaVinci Resolve handles English, Chinese, Japanese, and Spanish, Portuguese, French, Russian, Thai, Vietnamese, and Korean. Further checkboxes let you set which project opens at startup and how the Viewers on each DaVinci Resolve page are configured. Project Save and Load Here live the crucial auto-save controls, the Live Save option among them, which has Resolve save your work incrementally as you go. Editing A host of controls on this panel let you tailor the editing experience on the Edit page — defaults for building new timelines, plus general settings that rule standard effects durations and trim behaviors. Color This set lets you tailor grading on the Color page, offering control over video scope display, how UI overlays look, and assorted other color-specific functions. Fairlight Here you tailor editing on the Fairlight page by way of options for video offset, automation, and general settings. Playback Settings With these you shape how DaVinci Resolves handles video playback; when playback drags, adjusting them can sometimes help. Control Panels These let you tune the settings of whatever control surface you have attached. Metadata And these let you tune the Metadata Presets.

### Project Settings

After a project exists, every setting specific to it lives in the Project Settings window. Open that window by clicking the gear button down in the lower right of any page.

### Project Manager and Project Settings buttons

The Project Settings appear centered on screen, broken into a run of panels you pick from a sidebar on the left. Each panel gathers a set of related settings touching some category of DaVinci Resolve functionality. To bring up any panel, just click its name in that left-hand sidebar.

The Project Settings show all project-specific settings and attributes.

A project’s chief attributes — timeline resolution, timeline frame rate, color science, and bit depth — are laid down in the Master Settings. The Image Scaling settings dictate how clips whose size differs from the timeline resolution get scaled to fit. Additional panels cover Color Management, Camera Raw, Capture and Playback, and so on. For fuller detail on Project Settings, see Chapter 4, “System and User Preferences.”

### Switching Among Pages

Down at the bottom of the UI you will find the buttons that switch between pages. DaVinci Resolve breaks into seven principal pages of functionality, each serving a distinct specialty of the usual post production workflow, and each reachable through buttons along the very bottom of the DaVinci Resolve interface. Laid out in workflow order and always within reach, these buttons let you jump in a structured way from importing media to fast editing, detailed editing, compositing, grading, audio mixing, and finally outputting your project.

### Minimizing the Resolve Page Bar

Right-click anywhere inside the Resolve Page bar along the bottom of the DaVinci Resolve UI and a contextual menu offers two choices: “Show Icons and Labels” and “ Show Icons Only.” Opt for icons only and the Resolve Page bar down below occupies less space.

The Page bar showing icons only, to save space

### Switching Pages Using Keyboard Shortcuts

Pages can likewise be changed with the keyboard shortcuts listed here, all of which you can look up under the Workspace > Switch to Page submenu.

### Hide Pages You Don’t Use

It is possible to keep the page navigation bar in view while hiding only the buttons for certain pages. As an example:

- Perhaps you value this bar’s quick navigation yet there are pages you have no intention of touching
- Or perhaps you are configuring a DaVinci Resolve workstation for an artist with a narrow role on a

project, and you would rather hide ready access to pages of functionality they will not (or should not) be touching; this proves handy on collaborative workflow projects in particular. Each page’s buttons can be switched off or back on through the Workspace > Show Page submenu. Any effects and adjustments applied on hidden pages keep right on shaping the current project — they are merely out of sight — and you can still reach them via the Workspace > Switch to Page submenu commands or the keyboard shortcuts.

### Hide Page Navigation Altogether

Should you be an artist who works on just one page of the DaVinci Resolve experience, or should you crave more screen room because your monitor’s resolution is limited, choosing Workspace > Show Page Navigation will tuck away the page navigation bar along the bottom of the DaVinci Resolve user interface. Even with that bar closed, the other pages remain reachable through the Workspace > Switch to Page submenu commands or the keyboard shortcuts. To flip the Show Page Navigation function on or off: Check Workspace > Show Page Navigation. Once this interface element is hidden, keyboard shortcuts get you to the individual pages (Shift - 2 through 8), the Project manager (Shift - 1), and the Project settings (Shift - 9). These same functions are also available from DaVinci Resolve’s main menu bar.

### The Media Page

When it comes to bringing in clips, managing media, and organizing clips, the Media page is the main interface in DaVinci Resolve. A core principle of how DaVinci Resolve operates is that a project’s source media is kept apart from the project data you bring in and handle on the Edit page. That separation makes it easy to manage and refresh the clips your current project’s timelines depend on — flipping between offline and online media, rearranging clips, and sorting out whatever problems crop up.

### Media page

A good deal of the essential functionality for on-set workflows also lives on the Media page, as do the ingest, organizing, and sound-syncing steps of digital dailies workflows. These pages walk through most of what the Media page can do, detailing functions that get referenced all through this manual.

Six distinct areas make up the Media page, all arranged to help you locate, choose, and work on the media in your project. A large share of its functionality and the bulk of its commands sit inside the contextual menus that pop up on a right-click of clips within either the Library, the File Browser, or the Media Pool. To go deeper on working with the Media page, turn to Chapter 17, “Using the Media Page.”

### The Media Storage Browser

Every volume presently reachable by your Resolve workstation is listed in the Media Storage browser. You use it to track down media you intend to bring into your project by hand.

### Media Storage with scrubbable Clip view

### Viewer

Whatever clip you pick in any part of the Media page reveals its contents inside the Viewer. Along the bottom runs a jog bar that lets you drag the playhead straight with the pointer, while a jog control nestled between the mode drop-down and the transport controls lets you inch through a long clip more gradually. That jog bar’s entire width stands for the clip’s whole duration in the Viewer. Where the playhead currently sits is reported in the timecode field up at the Viewer’s top right corner. Beneath the jog bar sit straightforward transport controls for Jump to First Frame, Play/Stop, and Jump to Last Frame. To change audio levels, right-click the speaker icon and drag the slider. You may also send the Viewer into Cinema Viewer mode through Workspace > Viewer Mode > Cinema Viewer (Command-F) so it takes over the whole screen; that command switches Cinema Viewer mode on and off. With two monitors attached to your computer, you can have the Viewer fill one screen entirely while the Resolve UI stays on the other by choosing Workspace > Full Screen Viewer On and picking the display you want the Viewer on.

### Media page Viewer

### Media Pool

Every bit of video, audio, and still image media you bring into the current project resides in the Media Pool, as does whatever media rides in automatically alongside timelines imported into DaVinci Resolve. As a rule, media brought into a project lands in the Master bin, but you are free to split the Media Pool across as many bins of your own making as your needs call for. Inside the Media Pool, media moves from one bin to another without restriction. The Media Pool turns up on the Edit, Fusion, Color, and Fairlight pages too, so you can browse and open clips and timelines wherever they matter.

### Media Pool showing the selected bins’ clips

### Metadata Editor

Pick a clip anywhere on the Media page and its metadata shows up in the Metadata Editor. Should you select several clips, only the final one’s information is shown. Across the Metadata Editor’s header runs read-only information about the chosen clip — its file name, directory, duration, frame rate, resolution, and codec. Below that, a run of editable fields in the Metadata Editor lets you look over and revise whichever metadata items are on hand. A drop-down at the Metadata Editor’s top right offers a host of different sets of metadata fields and checkboxes, each bundled for a particular task or workflow.

### Clip Metadata Editor

### Audio Meters exposed

### Audio Panel

A pair of buttons above the audio meters flips the Audio panel between its two modes. Under the default Meters mode, Audio Meters appear and report the audio levels of whatever clips are playing. Switch to Waveform mode and you can lay audio clips next to the video clips open in the Viewer so as to sync them by hand. The Audio panel may also be tucked out of view.

### The Cut Page

As a tight, focused space for fast editing, the Cut page shines when you must rapidly cut a news segment, assemble an episode of web content, edit a no-frills program, try out several arrangements of a scene, or throw together a first assembly edit. It also serves as a friendly first editing interface for newcomers, putting forward a pared-down toolset that learns fast and stays simple. No matter where you come from, the Cut page proves a worthwhile addition to how you edit in DaVinci Resolve. By default its workspace gathers the Media Pool, a lone Viewer, and the Timeline area. Across those three regions you can swiftly import and sort clips, edit them, and even export what you have made — all without stepping outside the Cut page.

### The Cut page

To learn more about the Cut page, head to Chapter 26, “Using the Cut Page.”

### The Media Pool

On the Cut page too the Media Pool turns up, holding all the video clips, audio clips, graphics, and other media you import into your project. To keep that media tidy and quick to locate, you can spin up Bins, which open from the bin drop-down at the top left corner. Whatever you import — video, audio, or graphics — appears as its own clip, and each one can be selected, scrubbed for a fast look, shuffled into bins, opened in the Viewer for playback, or dropped into a timeline by way of the edit buttons or a drag and drop. Since the Cut page is built to speed editing up, the Media Pool brings along its own viewing options (the Strip view among them) and ways to customize.

### The Strip View mode

### The Viewer

Through the Viewer you watch clips from the Media Pool or those in the Timeline play back, and it carries a wealth of controls over what you see and how playback runs.

### The single Viewer in the Cut page

Four mode options live in the Viewer. Four buttons up in the Viewer’s top left corner both show which one is active and let you swap between them.

### The Viewer modes buttons

A range of actions drops you into each of these options on its own (reading left to right):

- Double-click any clip and it opens in the Viewer as a Source Clip.
- A whole bin’s worth of clips can be viewed at once via the Source Tape.
- Your edited program plays back in the Timeline.
- Every piece of your synced material can be seen together through the Multi Source Viewer.

Press the Tools button at the Viewer’s lower left and an effects toolbar opens, letting you add and tweak clip effects straight inside the Viewer with no Inspector required. That Tools button surfaces an assortment of controls for sizing, cropping, audio, speed effects, stabilization, dynamic zoom, and compositing.

### The Tools bar shown opened

### Audio Meter

Off to the Viewer’s right, an audio meter paints a graphical picture of the audio levels coming from the current clip or the Timeline as playback runs through the Viewer, using animated vertical bars whose tint signals how loud things are.

### The Timeline

“Timeline” does double duty: it names an edited sequence of clips that forms a program kept in the Media Pool, and it also names the part of the Cut page interface where you open that sequence to inspect its contents, play it back, and edit it. As far as the Cut page user is concerned, the timeline splits into an Upper Timeline up top and, down below, a bigger, more detailed Timeline Editor that zooms into the stretch of timeline around the playhead. Paired up, these two views of your edited sequence let you move across the whole project while cutting in fine detail.

The Cut page Timeline, made up of the Upper Timeline together with the zoomed in Lower Timeline Three icons sitting at the Timeline’s top left corner give you a range of timeline tasks to pick from; they consist of Timeline Options, Timeline Actions, and Edit Actions. The Timeline breaks into several tracks, each one able to carry a sequence of clips that together form a program. For simplicity, the main tracks — numbered — fold a clip’s video and audio into one item on the Timeline. Adjust a clip’s In or Out point and you adjust its video and audio as a unit.

### The Action icons in the Cut page

### Video+Audio tracks in the Cut page Timeline

TIP: On the Edit page, Video+Audio clips break apart into separate Video and Audio items living on different tracks. Open the Fairlight page and audio instead appears on tracks with lanes, each audio channel visible on its own. So every page hands you a distinct set of controls over the timeline’s contents, fitted to that page.

### The Edit Page

What the Edit page presents is a source-record style NLE packed with specialized features for both creative editing and finishing. It splits into three principal regions — the browsers along the left, the Viewers up top, and the Timeline at the bottom — which together let you import, edit, and trim timelines using a flexible mix of tools and approaches.

### The Edit page

To learn more about the Edit page, turn to Chapter 33, “Using the Edit Page.”

### The Media Pool

Just as it does everywhere else throughout DaVinci Resolve, the Media Pool here lets you arrange and browse all of a project’s media and timelines. A DaVinci Resolve project can hold one or several edited timelines (what some other applications call a sequence). On the Edit page the Media Pool matches the one shown on the Media, Fusion, Color, and Fairlight pages, presenting every source clip and timeline open for editing. Down the left, a Bin list lays out a nested set of folders for organizing your media. Out of the box the Media Pool holds one bin called “Master,” though you may tack on more bins as needed to sort your clips, popping any open to reveal its contents in a single click. Toggle that Bin list off or on with the button at the Media Pool’s upper-left. Over on the right, a browser displays whatever sits in the bin you have selected.

### The Media Pool in Thumbnail mode

### Effects Library Browsing
