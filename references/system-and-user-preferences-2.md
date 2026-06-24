# System And User Preferences (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- External Scripting Using: (Resolve Studio only) The choices here are None, Local, and Network. Left at None, only scripting from within the Console window is permitted. Set to Local, external scripts and applications sharing the same computer are able to drive DaVinci Resolve. Set to Network, external scripts and applications running on other machines across the network (or over the internet) are able to drive DaVinci Resolve.
- Use 10-bit precision in viewers if available: You'll only run across this checkbox on macOS installations of DaVinci Resolve. Switching it on permits DaVinci Resolve to show 10-bit images inside the Viewer.
- Use Mac Display Color Profile for viewers: When you run DaVinci Resolve on macOS, this checkbox tells every viewer in DaVinci Resolve to adopt whichever display profile sits chosen in the Displays panel of the System Preferences. That lets DaVinci Resolve lean on ColorSync on macOS so your Viewer image ought to line up more closely with your output display.

Viewers match QuickTime Player when using Rec.709 Scene: Tick this box so the viewers fall in step with the gamma characteristics of the QuickTime player. The effect is that the Resolve Viewers and what shows in QuickTime Player line up.

- Optimize project library cloud data traffic: Should reaching the Blackmagic Cloud through a corporate firewall give you trouble, tick this box to connect without having to arrange port mapping and firewall exceptions. https://blackmagicdesign.com still has to be whitelisted for access.
- Automatically Tag Rec.709 Scene Clips as Rec.709-A: Switch this checkbox on to have any Rec. 709 QuickTime files tagged on their own for Rec. 709-A playback. The setting comes in handy where your final QuickTime video parts ways with what shows in the Resolve viewers (gamma shift), and you'd rather export for the web than for broadcast.
- Automatically Scan other project libraries for remote rendering jobs: Switch this checkbox on so every connected project library gets scanned, not merely the current project library, for possible remote rendering jobs.
- Automatically Check for Updates: Switch this checkbox on to make staying on the newest version of DaVinci Resolve simpler. You may also pick DaVinci Resolve > Check For Updates to be alerted to new versions and pull them down once available.
- Automatically opt-in for new beta program notifications: Tips you off when public beta versions of DaVinci Resolve come out, should living on the edge appeal to you.
- Send report when application quits unexpectedly: Switched on, this setting lets DaVinci Resolve draw up a problem report on its own each time DaVinci Resolve quits unexpectedly. There's some information for you to fill in (do be as exact as you can about what you were up to when DaVinci Resolve ran into its trouble) before you press a button to dispatch the report.
- Limit Presentations upload speed to X KB/s: Lets you put a firm ceiling on the upload speed while you're on Presentations, so you don't soak up all your network bandwidth.
- Use Remote Monitoring without Blackmagic Cloud: Lets you run remote monitoring across your own network rather than routing through Blackmagic Cloud.
- Use TURN server for Remote Monitoring: Where Blackmagic Cloud is something you're avoiding for security reasons, and you instead lean on a self-configured or cloud-based TURN servers that route plus relay your monitoring streams, name that server here.
- Prevent sleeping when Blackmagic Cloud sync enabled project is open: On by default, this checkbox keeps your computer out of sleep mode for as long as a Blackmagic Cloud project stays active, ensuring every online data transfer finishes. Clear the box to let your computer drop off to sleep as it pleases.
- LUT Locations: Through this interface you add or pull directories where DaVinci Resolve will hunt for LUTs to apply across the application.

### Internet Accounts

The Internet Accounts panel acts as a login manager for the Blackmagic Cloud along with other social media sites. DaVinci Resolve carries close integration with YouTube, Vimeo, TikTok, Dropbox, and Frame.io, letting you render and push files straight to each service. Buttons on this panel let you log into your YouTube, Vimeo, TikTok, Dropbox, and Frame.io accounts and also name a local cache location for media being kept in sync with Frame.io. Every service you log into brings up a floating window holding the interface where you supply your login name and password to switch on integration, then complete any twofactor identification and the remaining required steps. After you've entered them, DaVinci Resolve logs into each of these services on its own whenever DaVinci Resolve launches.

Inside the DaVinci Resolve Preferences window, the Internet Accounts panel shown under its System tab

### Advanced

You turn to this tab for special Resolve configurations together with SAN parameters that bear on older file systems.

### User

Through this panel you pick user preferences tied to your own workstation. They govern keyboard shortcut mappings, control panel action, editing and color defaults, auto save settings, plus how the UI behaves and looks. TIP: A good many of the settings sitting in the User panel once lived in the Project Settings window before version 14, yet they were relocated here to support collaborative workflows in which each user keeps their own independent general, editing, and color settings along with their own keyboard shortcuts.

### Saving User Preference Presets

You can keep several presets on hand for one-click recall of differing User Preference settings, by way of the Option menu in the UI Settings window.

Found in the Option menu of the UI Seµttings window, the commands that handle User Preference presets Ways to handle User Preference presets:

- To save a preset: Settle on whatever settings you'd like to use, then open the UI Settings window Option menu and pick Save User Preferences as Preset. Type a name in the dialog, then press OK. That preset then turns up at the head of the Option menu.
- To load a preset: Open the UI Settings window Option menu, then pick Load Preset off the submenu of whichever preset you want to load.
- To update a preset: Load whichever preset you want to edit, adjust whatever settings you need, then pick Update Preset off that preset's submenu in the Option menu.
- To export a preset: Pick Export Preset off the submenu of any preset in the Option menu. A file carrying the .userprefs extension lands at the location you picked.
- To import a preset: Pick Import User Preferences as Preset in the Option menu, work the dialog to locate the exported .userprefs preset file you want to bring in, then press Open.
- To delete a preset: Pick Delete Preset off the submenu of any preset in the Option menu.
- To reset all presets: Pick Reset User Preferences off the Option menu to put every User Preference back to its default settings.

### UI Settings

A set of operational preferences.

- Language: At the top a Language dropdown lets you name which language the DaVinci Resolve user interface shows. As things stand, the languages DaVinci Resolve handles are Chinese, English, French, German, Italian, Japanese, Korean, Portuguese, Russian, Spanish, Thai, and Vietnamese.
- Reload last working project on startup: On its own reopens the last project a user had going each time that user logs back into DaVinci Resolve. You can only switch this checkbox on while editing a preset configuration in the Presets panel, so that it stays on no matter which project you open as long as you're running that particular preset.
- Use Optimized UI layouts for vertical video: Ticking this box has the UI refresh on its own to suit vertical timelines and video sources. Clearing this box keeps the normal UI whatever the video orientation.
- Show focus indicators in the user interface: Lets you switch on or off a red line atop each panel marking which panel currently holds focus.
- Use gray background for user interface: Out of the box, DaVinci Resolve runs a blue-gray UI background, meant to give a more pleasing experience to users centered on the less colorcritical sides of DaVinci Resolve, editing chief among them. Switching this checkbox on flips DaVinci Resolve over to a wholly neutral, desaturated gray UI, which can serve as a reference point for colorists worried the blue-gray UI might bias the eye amid the dark surroundings of the grading suite.
- Use gray background in viewers: Switched on, it paints the background of every viewer gray, making image blanking or slight sizing tweaks easier to judge than against the default dark background.
- Resize image in viewer to square pixels: This control picks between a square or nonsquare pixel aspect ratio inside the Viewer. It matters where you handle SD images, which lack a square pixel aspect ratio.
- Delay viewer display by X frames: Switched on, it lets you enter a count of frames by which to hold back the DaVinci Resolve Viewers as they show on your computer displays, so the image on your computer display syncs more closely with the same image shown on external displays held up by assorted signal processing processes.
- Output single field when paused: This setting cuts flicker while grading on a computer monitor or while working with interlaced material. By default, viewing interlaced material in Stop or Pause mode shows field one followed by field two. Depending on the image, that can leave a flicker on the display. With this option on, only field one shows on the monitor while playback sits paused; both fields, however, show once the clips play.
- Stop playback when a dropped frame is detected: Switched on, it tells DaVinci Resolve to halt playback any time a frame drops on output, alerting you to performance issues on your workstation. That's especially handy where you're outputting to tape.
- Stop renders when a frame or clip cannot be processed: Switched on, this stops a render the moment DaVinci Resolve spots an error in the encoding, rather than pressing on to try processing it.
- Show playhead shadow: Ticking this box switches on the playhead shadow, a transparent orange range for visually gauging that reaches a set number of frames ahead of and behind the playhead. You can tune the count of frames in the range before or after the playhead over in the Editing section of the User Preferences.
- 2D timeline scrolling: Ticking this box scrolls the Timeline vertically through all the Video or Audio tracks as you spin the mouse wheel. Clearing this box scrolls the whole Timeline horizontally as you spin the mouse wheel.
- Timeline sort order: A user setting that lets you fix the default sort order of the Timelines that show in the Viewer drop-down menus throughout DaVinci Resolve.

Alphabetic: Orders Timelines from A-Z by name. Creation Date: Orders Timelines with the oldest one made coming first. Recently Used (default): Orders Timelines according to the 10 most recently active timelines.

### Project Save and Load

Through the Project Save and Load panel you steer how projects get opened, along with how they get saved.

### Load Settings

By way of the Load Settings preference you steer one key facet of project opening performance: whether or not every timeline inside a given project loads into memory at the moment of opening.

- Load all timelines when opening projects: To sharpen the performance of longer projects holding several timelines, the “Load all timelines when opening projects” checkbox over in the Project Save and Load panel of the User Preferences sits off by default. With this checkbox off, opening a project brings only the last timeline you worked on into memory; the rest stay out of RAM. That quickens the opening of large projects. You may, though, hit brief pauses on opening other timelines inside that project, as each fresh timeline has to load into RAM the moment you open it. Open a truly enormous timeline and a progress bar shows up telling you how long the load will take. A further upside is the smaller memory footprint of each project, which pays off especially while juggling several projects through Dynamic Project Switching.

Switch this on and every timeline loads into RAM, so you'll meet no pauses on opening timelines you haven't opened yet. Projects with many timelines, however, may run slower to open and save.

### Save Settings

The Save settings let you steer how DaVinci Resolve handles automated saving and project backups. Such features can spare you the heartache of work lost to an unexpected problem.

- Live Save: Switched on out of the box, Live Save runs as a quick, progressive, ever-present autosave mechanism that “saves as you go.” Every change across the Cut, Edit, and Fairlight pages gets saved the moment you make it. Every change across the Fusion and Color pages saves on its own when you move to another clip, and also at intervals and unseen in the background as you work, so your work stays saved even where you haven't switched clips in a while.
- Project Backups: Found within the User Preferences, over in the Project Save and Load panel, the Project Backups checkbox — switch it on and DaVinci Resolve writes several backup project files at recurring intervals, by a method akin to a GFS (grandfather father son) backup scheme. This works whether or not Live Save sits on. Each project backup is a full project file, leaving out stills and LUTs. After you've had Project Backups on long enough, whatever saved project backups exist can be pulled back in the Project Manager via the contextual menu that pops up when you right-click a project, by picking Project Backups. Opening a project backup leaves the original project untouched; project backups always open as independent projects.

### Restoring a project backup in the Project Browser

- Timeline Backups: Found within the User Preferences, over in the Project Save and Load panel, the Timeline Backups checkbox — switch it on and DaVinci Resolve writes several backups of a timeline at recurring intervals, by a method akin to a GFS (grandfather-father-son) backup scheme. This works whether or not Live Save sits on.

### Restoring a timeline backup in the Media Pool

Should you wish to roll back to an earlier backup of a timeline, just right-click the timeline in the Media Pool, pick Restore Timeline Backup off the contextual menu, then settle on the backup from the list of options. Backups come arranged by date and time, so locating the particular timeline you want to restore is easy. Restoring a timeline backup leaves your current timeline untouched. Rather, the chosen backup arrives in the Media Pool as a fresh timeline, with the name “Backup” tacked onto it. Project and Timeline backups get saved only once changes have been made to a project. Should DaVinci Resolve sit idle for any stretch, as when your smart watch nudges you to step outside and walk around the block, no further project backups get saved, which keeps DaVinci Resolve from writing over useful backups with needless ones. Three fields let you set how often a fresh backup gets saved, while the fourth lets you pick where the backups land. Both Project and Timeline backups fall under these settings. Perform backups every X minutes: How often a fresh backup gets saved within the last hour you've worked is what this opening field sets. By default a fresh backup gets saved every 10 minutes, yielding six backups inside the last hour. Once an hour of work has gone by, an hourly backup gets saved and the per-minute backups start being dropped, first in and first out. By default that leaves you holding only ever six backups at once, standing for the most recent hour of work. Hourly backups for the past X hours: How many hourly project backups you wish to keep is what this next field sets. By default two hourly backups get kept for the current day. Beyond that count, hourly backups start being dropped, first in and first out. Daily backups for the past X days: Across how many days you wish to keep backups is what this further field sets. The final backup saved on any given day is held as the daily backup for that day, and by default daily backups get kept for two days only. Beyond that count, daily backups start being dropped, first in and first out. Working on a project across a longer stretch, you can always bump this number up. Backup location: Press the Browse button to pick a spot where these backups get saved. By default they land in a “ProjectBackup” directory on your scratch disk, though you could point this at a volume that fits your data backup methodology better. This folder holds both Project and Timeline backups.

### Cache Management

Through this section you can have your local cache deleted on its own after a set number of days, keeping your drive from clogging up with older projects. Naturally, tending these files by hand stays possible through the Playback > Manage Render Cache menu, yet this new preference lets you arrange a cleanup operation and then forget it.

### Media Cache Settings

Delete Cache files older than xx days: Tick the box and pick the number of days past which the automatic deletion of the Cache files happens.

### Editing

What this panel's settings reach into are frame interpolation settings, timeline UI appearance, trim behaviors, editorial default values, plus new timeline settings.

### New Timeline Settings

These settings fix the presets that fill the New Timeline Options window each time you build a new timeline.

- Start Timecode: The Start Timecode can be changed whenever a particular start time is called for.
- No. of Video Tracks: Type in how many video tracks you'd like. You can also drag inside this

field to set the number of video tracks with a virtual slider.

- No. of Audio Tracks: Type in how many audio tracks you'd like. You can also drag inside this

field to set the number of audio tracks with a virtual slider.

- Audio Track Type: Pick the channel mapping you'd like the new audio tracks to adopt.

### Automatic Smart Bins

These settings let DaVinci Resolve build Smart Bins on its own whenever clips bearing relevant metadata land in the Media Pool, or whenever such metadata gets added to clips already sitting in the Media Pool. Through a run of checkboxes you choose which Smart Bins get built automatically.

### General Settings

These settings fix the timing of resolve-generated effects along with editing operations.

- Standard generator duration: Sets, whether in Seconds or Frames, how long generators run by default once you edit them into the Timeline. Out of the box that value sits at 5 seconds.
- Standard transition duration: Fixes the duration of transitions, in Seconds or Frames, that you add at an edit point in DaVinci Resolve. The default value is 1 second.
- Standard still duration: Sets, whether in Seconds or Frames, how long imported stills last — TIFF, PNG and the other supported graphic file formats among them. Out of the box that value sits at 5 seconds.
- Pre-roll time: Sets how much of the Timeline ahead of the current playhead position plays while you run the Play Around command.
- Post-roll time: Sets how much of the Timeline beyond the current playhead position plays while you run the Play Around command.
- Audio subframe nudge: Sets the count of milliseconds or subframes nudged when you use the Subframe Left/Right controls.
- Default handles length: The value applied while building a timeline with handles. The default is one second worth of frames.
- Default fast nudge length: The count of frames nudged when you use the Shift-Comma (,) and Shift-Period (.) keyboard shortcuts.
- Pre-playhead shadow length: The count of frames in the Timeline ahead of the playhead that the Playhead Shadow covers, where switched on by ticking the “Show playhead shadow box” in the User UI Settings preferences.
- Post-playhead shadow length: The count of frames in the Timeline beyond the playhead that the Playhead Shadow covers, where switched on by ticking the “Show playhead shadow box” in the User UI Settings preferences.
- Automatically switch to single viewer mode when opening trim editor: Switch this checkbox on where you'd like DaVinci Resolve to always bring up the trim editor in one larger viewer while you carry out trim operations. Clearing this box keeps dual viewer operation going even during trimming.
- Timeline overlay retains the last performed action: Switch this checkbox on where you'd like DaVinci Resolve to always recall the last edit type you used in the Timeline Viewer Overlay and flag it on this Overlay each time you drag another clip over the Timeline Viewer, signaling that the last edit you carried out is the new default edit should you drop clips to the left of the overlay.
- Always highlight current clip in the media pool: Switched on, any clips sitting at the playhead position on the Edit or Color pages get flagged on their own in the Media Pool.
- Limit timecode display to 24 hours: With this box ticked, timecode loops back round to 00:00:00:00 after 23:59:59:xx instead of running on. That keeps time of day timecode more consistent to work with.
- Prioritize pasting to the in and out range: As a rule, pasted clips show up at the playhead position in the timeline. Tick this box should you want them pasted according to the timeline in and out points instead.
- Sync the Master Timeline to the current frame: Where you switched on “Automatically match master timeline with media pool” over in the Color settings, this option then lets you make certain that each time you open the Master Timeline, the playhead lands on the same clip and frame it held in the previous Timeline you had going.
- Show offline reference for timeline gaps: Where a missing clip in a conformed timeline leaves a gap in the Timeline Editor, switching this option on tells DaVinci Resolve to show the matching frames of an “offline reference movie,” if one has been tied to that timeline, in place of black. That can rescue you in emergencies where timeline clips go missing right before a screening or review session; the feature lets you play or output the missing frames off the matching media from the offline reference movie rather than outputting black.

To read further on putting Offline Reference Movies to work and assigning them, turn to Chapter 55, “Preparing Timelines for Import and Comparison.”

- Show offline reference for non-conformed edits: Where missing media in a project leaves an unlinked clip in the Timeline Editor (shown by a red exclamation point overlay on that clip), switching this option on tells DaVinci Resolve to show the matching frames of an “offline reference movie,” if one has been tied to that timeline, in place of black. That can rescue you in emergencies where source media goes missing right before a screening or review session; the feature lets you play or output the missing frames off the matching media from the offline reference movie rather than outputting black.

For deeper guidance on applying Offline Reference Movies and assigning them, head to Chapter 55, “Preparing Timelines for Import and Comparison.”
