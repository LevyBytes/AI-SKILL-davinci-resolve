# Blackmagic Cloud Presentations

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Blackmagic Cloud Presentations

This chapter walks through working with the Presentations application within the Blackmagic Cloud, which lets you run online review and collaboration sessions alongside people anywhere in the world.

### Blackmagic Presentations

Through nothing more than an internet browser, the Presentations application in Blackmagic Cloud enables real time collaboration on and review of DaVinci Resolve timelines. Its collaboration tools cover video conferencing for live communication, a chat interface that retains notes and comments, plus markers syncing straight to a DaVinci Resolve timeline. Using them, every user can watch a video with frame accurate sync while video conferencing simultaneously.

The Blackmagic Presentations application in a web browser Three parts make up the Presentations application. Along the left runs My Presentations, the column where your various presentations get created, kept, and arranged. The middle holds the Viewer, used to move through the clip, drop markers, and set the audio playback. Sitting above the Viewer is the Video Conferencing area, your space for collaborating live with fellow members. The right column breaks into three sections: Clips, Markers, and Chat. Clips lists every clip on hand to comment on and collaborate over. Markers presents a roster of markers and comments that sync with a DaVinci Resolve timeline. Chat brings up a plain chat interface so a record of your notes and comments exists. NOTE: At the time of writing, Presentations remains in beta. Being beta software, whatever features appear below could be altered, reworked, or dropped entirely before the final release.

### Creating and Managing Presentations

Two pieces make up online collaboration in Presentations: first the Presentation within the Blackmagic Cloud, and second a timeline coming from a DaVinci Resolve workstation (covered below). This section covers how Presentations get created and managed. NOTE: Presentations applies somewhat different terminology for clips than DaVinci Resolve does. Within Presentations, a “clip” means a DaVinci Resolve “timeline,” rather than a clip you'd come across in the Media Pool.

### Creating a New Presentation

Picture each presentation as akin to a project in DaVinci Resolve, only it centers on discussion instead of post production. Presentations hold several “clips” for review and carry an assortment of collaboration tools rather than editing/color/fx/audio tools. Spinning up a fresh presentation per project works fine, yet you may equally build presentations around other criteria, such as who's collaborating, a date, or a particular phase of post production. Here's how to build a Blackmagic Cloud Presentation: 1 Sign in to your Blackmagic Cloud account through a web browser at www.blackmagicdesign.com. 2 Click the Presentations icon at the upper center of the web page. 3 Within the My Presentations column, click the Add Presentation button down at the lower left. 4 Choose a Name for the presentation and click Add. 5 Click the Presentation inside the My Presentations column to open it.

### The My Presentations column

When you've amassed more presentations than the screen can hold, the My Presentations column sorts by name and date, ascending or descending, via the sort icon just off to the right. Searching the My Presentations column is possible too by clicking the magnifying glass on the right and typing your search terms. Only the presentations that match your terms appear. Up until you've uploaded a first clip from a DaVinci Resolve project, the Viewer reads “Upload clips from DaVinci Resolve to get started.” The “Sending a Timeline to Presentations” section further down covers that process.

### Sharing a Presentation with Another User

A presentation can be shared with as many as 10 other users. The single prerequisite is that every one of them holds a Blackmagic Cloud account of their own. Here's how to share a Blackmagic Cloud Presentation: 1 Click the information icon (the circled letter i) beside the presentation name. That opens a Members pane listing all the current users the presentation is shared with. Whoever holds the crown icon is the presentation administrator, and they alone can add or remove users. 2 Click the Share button at the foot of the Members pane. 3 Type the email address (the one used to set up the Blackmagic Cloud account) of the user you'd like to share the presentation with. 4 Click the Share button.

### The information panel of a presentation

That user's name then shows in the Members pane, and the presentation surfaces in their own My Presentations column once they sign in to the Blackmagic Cloud. From there they're free to watch any clips, video conference, or leave comments inside that presentation. On top of that, an email goes out to the user's email address, telling them about the presentation and giving a direct link to reach it. Removing a user from a presentation is simply a matter of clicking the “x” beside their name in the Members panel. Only the administrator may add or remove members.

### Enabling and Disabling a Presentation

The administrator may opt to disable a presentation for a while. This temporarily locks down access to it without erasing anything. Every clip, user, and comment stays put, and the only effect is that the presentation can't be viewed or changed until it's enabled once more. To Enable or Disable a Blackmagic Cloud Presentation 1 Click the Information icon (the circled letter i) beside the presentation name. 2 Click the Presentation enabled switch right under the presentation name to flip between enabling and disabling the presentation.

### Renaming a Presentation

The administrator can readily rename a presentation so it better captures its purpose or contents. To Rename a Blackmagic Cloud Presentation 1 Click the Information icon (the circled letter i) beside the presentation name. 2 Click the Settings icon (the small gear) beside the presentation name. 3 Choose Rename out of the drop-down menu. 4 Enter the presentation's new name. 5 Click the Save button. The presentation's name is then refreshed in the My Presentations column for every user.

### Deleting a Presentation

Once you're done with a presentation, the administrator may remove it from the Blackmagic Cloud. Deleting a presentation wipes out all of its clips and comments for good and can't be undone, so be certain you're entirely finished before deleting. To Delete a Blackmagic Cloud Presentation 1 Click the Information icon (the circled letter i) beside the presentation name. 2 Click the Settings icon (the small gear) beside the presentation name. 3 Choose Delete out of the drop-down menu. 4 Click the Delete button in the warning dialog box.

### Leaving a Presentation

You as a user may step away from a Presentation whenever you like. Doing so strips your permission to view and edit the presentation and clears it from your My Presentations column. Should you want back into a presentation after leaving, its administrator will need to re-share it with you. Here's how to leave a Blackmagic Cloud Presentation: 1 Click the Information icon (the circled letter i) beside the presentation name. 2 Click the Settings icon (the small gear) beside the presentation name. 3 Choose Leave out of the drop-down menu. 4 Click the Leave button in the warning dialog box.

### Using Presentations

At the core of Presentations sits the Viewer; from here you can both video conference and steer a clip's playback. The Viewer delivers a low latency, streaming video that you can mark and comment on precisely, with those comments appearing live for other users and on the DaVinci Resolve timeline.

### Video Conferencing

Across the top of the Viewer runs a simple video conferencing interface, where every user's video stream shows up in a live thumbnail. The camera and microphone start off switched off, so you'll have to enable them yourself.

The video conferencing interface; spot the Camera and Microphone on/off controls over in the upper right. Here's how to switch the Camera and Microphone on and off for a Blackmagic Cloud Presentation: 1 Click the Camera and/or Microphone icons up at the right of the Viewer. 2 Grant your OS and browser the permissions they need to use the devices. 3 To switch the Camera and Microphone back off, click their respective icons once more. With your camera and microphone running, every other connected user sees and hears you over their web browsers, so stay generous and discreet with your comments.

### Controlling a Clip in the Viewer

Every user can watch and comment on any clip (the same one included) in real time. Each user's Viewer runs independently of the rest, though the administrator may sync everyone's Viewer to theirs so the same clip plays for all at once.

### Selecting a Clip

Choosing a clip to watch is as simple as clicking its thumbnail in the Clips column. Clips can be sorted by date, duration, and name in ascending or descending order. Searching the Clips column is possible too by clicking the magnifying glass on the right and typing your search terms. Only the clips that match your terms appear. Hovering your pointer across a clip thumbnail also lets you scrub the video. Administrators may rename and remove clips from the presentation by hovering over the thumbnail and clicking the matching icons (pencil and trashcan) up at the right.

### The Clips column

### Viewer Controls

Along the bottom of the browser the Presentations Viewer carries a row of playback controls for placing your playhead exactly.

### The Viewer controls

Jog Bar: The long line spanning the bottom of the browser marks your present playhead position as a rectangle along with any markers already placed. Click and drag the playhead to scrub forward and back through the clip. Timecode: The current clip's timecode, which points back to the original DaVinci Resolve timeline. Previous Clip: (Up Arrow) Pulls into the Viewer whichever clip sits above the current one within the Clips column. Should the current clip already sit at the top of the stack, it wraps round to the clip at the bottom. Stop: Halts the clip's playback inside the Viewer. Play: Runs the clip forward inside the Viewer at 1x speed. Next Clip: (Down Arrow) Pulls into the Viewer whichever clip sits below the current one within the Clips column. Should the current clip already sit at the bottom of the stack, it wraps round to the clip at the top. Loop: Cycles among no looping (the default), Loop One which repeats the current clip endlessly, and Loop All which runs through every clip in the Clips column and loops back to the start of the stack. Volume: A click on this icon mutes the audio. The slider beside the icon, when dragged, sets the clip's volume. Start Sync: (Administrator only), a click on this icon makes your Viewer's contents appear for every member. The administrator's view takes over the Viewers of all the other users, so everyone watches the same thing together. Add Marker: A click on this icon drops a marker at the playhead position. Editing and commenting on that marker happens in the Markers column covered below. Full Screen: This grows the Viewer to fill the whole screen.

NOTE: The left and right arrow keys move the playhead one frame back and forward respectively.

### Using Markers

You have three avenues for voicing your view on a clip in Presentations. The first is talking straight through video conferencing as covered above; the second and third run through markers and chat. Markers let you pin written comments to a specific frame of video. That way your targeted notes land exactly where they belong. The chief upside of markers is that they likewise carry over at once to the DaVinci Resolve timeline the clip was built from. That guarantees your comments reach the editor/colorist/audio engineer while they work the project.

### The Markers column

To drop a marker onto a clip at wherever the playhead sits, take one of these routes:

- Click on the Add Marker icon in the Viewer.
- Tap the letter M on your keyboard.
- In the Markers column, write your comment in the text

box down at the bottom and click the Add Marker button. A marker shows up as a triangle sharing the tint of the colored dot linked to that user's thumbnail over in the Video Conferencing pane. Here's how to revise a marker's text: 1 Float over the marker within the Markers column and tap the Pencil icon. 2 Enter your comment into the text box. 3 Click save. Here's how to remove a marker from a clip: 1 Float over the marker within the Markers column and tap the Trashcan icon. 2 Click Delete in the warning dialog.

### Using Chat

The Chat column hands you a plain text-based conversation tool that's kept around permanently. With it you can drop notes and comments and look back at earlier sessions when needed. Rather than belonging to any one clip, the Chat column belongs to the presentation overall. To Leave a Chat Comment: 1 Type your message in the text box at the foot of the Chat column. 2 Press the Send icon. Your message lands in the chat window in chronological order. The chat messages you've sent show up unattributed and right justified. Messages from other members show up left justified, carrying their names and User icon. For now the chat is visible to every member of the presentation, and a chat message can't be deleted once sent, so be kind.

### The Chat column

### Presentations in DaVinci Resolve

The Presentations application is built to operate hand in hand with DaVinci Resolve. Every “clip” in Presentations ties to a DaVinci Resolve timeline. Whatever markers members add inside Presentations get pushed to the timeline in DaVinci Resolve automatically, and the reverse holds as well.

### Sending a Timeline to Presentations

Every “clip” in Presentations is a DaVinci Resolve timeline. To fill the Clips column with footage to work on, you first have to export your timeline out of DaVinci Resolve into Presentations.

The Presentations Render Preset sitting on the Deliver page. Here's how to push a DaVinci Resolve Timeline over to Presentations: 1 Confirm you're signed in to your Blackmagic Cloud account within the Internet Accounts section of the DaVinci Resolve Preferences. 2 Confirm you belong to the presentation you intend to send the timeline to. 3 Open the timeline you intend to send. 4 On the Deliver page, choose the Presentations render preset. 5 In the File Name field, type the name your timeline should carry inside Presentations. 6 In the Upload to field, choose the presentation you'd like the timeline uploaded to. Should the presentation be missing from the list, revisit steps 1 and 2. 7 Click the Add to Render Queue button at the foot of the Render Settings. 8 Click the Render All button beneath the Render Queue.

No video or audio codec parameters need setting, and DaVinci Resolve goes ahead to render your timeline and upload it automatically to the chosen presentation. Uploading a timeline to a presentation is open to any member, not the administrator alone. Your timeline now turns up as a “clip” within the presentation's Clips column.

### Using Markers Between Presentations and DaVinci Resolve

A major plus of Presentations is markers that persist between a presentation and a DaVinci Resolve timeline. After a timeline has been uploaded to a presentation, it's linked behind the scenes automatically, and whatever markers get added, whether inside the Presentations app or in DaVinci Resolve, sync to one another. On the DaVinci Resolve end, that sync happens whenever a timeline is open and the user is signed in to the Blackmagic Cloud. As an example, members might add markers overnight, and they'll then sync once the editor opens the timeline come morning. Live collaboration with a presentation is also possible when the members are online and the editor is working the timeline, updating markers in real time.

Presentations markers carry a circular shape and stay synced between the timeline and its paired Presentations clip. Markers tied to Presentations render as circular on the DaVinci Resolve timeline, setting them apart from ordinary markers, which are triangular. Presentations Markers also take on the color of the member who created the marker. The flow of markers isn't only one way from Presentations into DaVinci Resolve. While working a timeline in DaVinci Resolve, the user can drop special Presentations markers that sync and appear inside the Presentations application for every member to see. Here's how to place a Presentations marker on a DaVinci Resolve Timeline: 1 A timeline must already have gone up to Presentations per the steps above. 2 Park the playhead at the Timeline spot where the Presentations marker belongs. 3 Choose Mark > Add Marker > Presentations. Here's how to clear a Presentations marker from a DaVinci Resolve Timeline: 1 Pick the circular Presentations marker sitting on the Timeline. 2 Hit the Delete key. 3 Click the Delete button in the warning dialog. Removing a Presentations marker takes it off both the Timeline and the presentation itself. This action can't be undone. The timeline user may delete a Presentations marker belonging to any member, not just their own.
