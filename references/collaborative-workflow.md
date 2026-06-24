# Collaborative Workflow (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Collaborative Workflow

When several people open one shared project, the multi-user collaborative workflow relies on “bin locking” to govern who is permitted to touch which items. Beyond that, this mode lets a group of artists edit, composite, grade, and enter metadata on clips belonging to a shared timeline, all inside one project where Collaboration has been switched on. A timeline inside a given project can be reached by many people at once for concurrent editing, compositing, and grading, and meanwhile assistants and other editors may open separate bins holding separate timelines in that same project to handle editorial tasks and media management. The pages that follow explain how several DaVinci Resolve workstations are configured to cooperate, and how bin locking lets them work as a team.

### Introduction to Collaborative Workflow

Within one project that has collaboration switched on, the multi-user collaborative workflow lets a number of people handle editing, compositing, grading, and Media Pool clip organization at the same time. There are three distinct shapes this collaboration can take:

- Through bin locking, several editors are able to edit separate timelines housed in separate bins of one shared project at once, and assistant editors can rearrange clips and revise the metadata living in the project’s other bins. A bin locks itself the moment a given user selects it and releases when that same user clicks away, though you can also force a bin into a locked or unlocked state by hand whenever the situation calls for it.
- Through clip locking, a group of colorists and compositing artists are free to share one timeline — whether on the Color page or the Fusion page — without worrying that they’ll clobber each other’s changes. Selecting a clip to work on locks it automatically, and choosing a different clip releases it (checking the work in as it goes). Because the Fusion page keeps its clip locks apart from those on the Color page, a colorist and a compositing artist are able to share a single shot.
- A trio consisting of one editor, one compositing artist, and one colorist can all share the same clip on the same Timeline within the same project without clashing.

By and large, using DaVinci Resolve in Collaborative Workflow mode feels no different from running it in noncollaborative mode. That said, a handful of collaboration-specific features deserve a mention.

### Collaborative Render Cache Support

The render cache format settings are matched automatically on every machine so that all collaborators on a project share identical ones. When your collaboration spans different operating systems (Mac, Windows, Linux), take care that the Render Cache Format points at a codec every one of those platforms can handle.

### Collaborative Support for Individual Monitoring

Should the need arise, any collaborator on a project may override that project’s output and monitoring settings just on their own workstation. Once a project is switched to Collaborative Workflow, a “Use Local Overrides” checkbox shows up within the Video Monitoring group of the Project Settings, giving you control over how monitoring happens at your own workstation.

### Collaborative Marker, Flag, and Clip Color Support

From the Color page, collaborative workflow lets you change markers, flags, clip metadata, and clip color. On top of that, FrameIO comment markers also work under collaborative workflow.

### Read Only Mode

Collaborative projects can be opened by users in Read Only Mode.

### Collaborative Support for HDR

As of DaVinci Resolve 16, collaborative workflows gained support for Dolby Vision and HDR10+.

### Collaborative Support for LUT and Colorspace Context Options

In multi-user projects you’re able to tweak LUTs and Colorspace settings straight from nodes — just right-click a node and pick the choice you’re after from the context menu, the same way you would in a single user project.

### Requirements for Collaboration

To make use of collaborative workflow:

- Every user has to be on a project saved either to the Blackmagic Cloud or to a correctly set up remote project library server. That remote project library server may live on one of the DaVinci Resolve workstations already in use, or on some other machine on your network whose only job is hosting the shared projects — but it ought to sit on a computer that never sleeps or powers down, so that projects don’t abruptly go missing.
- Every machine joining a collaborative workflow has to be networked together. A shared local area network (LAN) is fine, yet you’re equally able to link computers sitting on separate subnets.
- For the best results, shared projects ought to keep their media on a fast storage area network (SAN) of some kind, with each collaborator hooked into that SAN so every workstation tied to the collaborated project reaches the very same media directly. Shared volumes across a network can do the job when you’re stuck, though a proper SAN delivers a real performance boost. Sites running a mix of computer platforms (macOS, Windows, and Linux) side by side can lean on the Mapped Mount option in the Media Storage Locations list — located in the DaVinci Resolve System Preferences — to ease cross platform drive connections.
- As another option, every workstation can reach the same cloud storage folder over the internet, provided the correct Path Mapping has been arranged in the Project Settings.

To learn more about standing up a project library server, refer to Chapter 196, “Managing Project Libraries and Project Servers.”

### Enabling Multiple User Collaboration

Before the collaboration toolset can be used, a project must have Multiple User collaboration mode turned on. To launch a project and kick off a collaborative workflow: 1 Start DaVinci Resolve on a machine wired to a remote project library or Blackmagic Cloud server. 2 Using the Project Manager, open whatever project lives on the remote project library that DaVinci Resolve currently points at. 3 With the project open, pick File > Multiple User Collaboration. As soon as collaboration switches on, a pair of extra buttons shows up at the bottom-right of the DaVinci Resolve interface, beside the Project Manager and Project Setting buttons. Those are the Collaboration Chat and Collaboration buttons.

At far left sits the Collaboration Chat button, with the Collaboration button just next to it (second from the left)

NOTE: Switching collaboration on disables, automatically, the Project Settings’ General Options panel setting labeled “Auto conform missing clips as media is added to Media Pool,” because it interferes with collaborative workflow. Live Save, meanwhile, gets enabled by itself within the Auto Save panel of the User Preferences, ensuring each collaborator’s work is saved at regular intervals and clashes between collaborators are avoided.

### Opening Projects to Collaborate

Once Collaboration is enabled on a project, its thumbnail in the Project Manager carries a badge that signals the project is open for collaboration.

Within the Project Manager, an icon flags a project as open for collaboration From this point, anyone else holding access to this remote project library server can launch the project and start collaborating with you. Every time someone joins whatever project you’re currently in, that Collaboration Chat button at the foot of the DaVinci Resolve UI brightens to flag a waiting message. When highlighted, the Collaboration Chat button alerts you to a message Open the Collaboration Chat window and you’ll see who you’re collaborating with.

In the Collaboration Chat window, an incoming message tells you which other person has opened your current project

### Customizing Your Collaborator Identification

After a project is configured for collaboration, you’ll want it to be simple to distinguish your collaborators from one another. A click on the Collaboration button brings up a roster of every collaborator, or project member, active in that project.

Opening the Collaboration list shows all the current project members You sit at the top of that roster, and you can revise the name you go by simply by typing into the text field. The image you picked in either your Blackmagic Cloud account or the DaVinci Resolve Project Server determines your user icon automatically. With no image selected, it falls back to the first two letters of your user name. You’re also shown each other member’s workstation OS, displayed as an icon just to the right of that member’s name.

### How Collaboration Works

In its most basic form, collaborative workflow leans on a “first come, first served” scheme to decide who is allowed to alter what. In practice, whoever is first to pick a bin in the Media Pool, open a timeline, or pick a clip on the Fusion page or Color page earns a “lock” over that item. After an item gets locked (shown by a tinted collaborator badge), the rest of the collaborators may view it but can’t alter it. Doing this keeps versioning conflicts from cropping up. A bin or clip lock lifts the moment a collaborator picks a different bin or timeline on the Media or Edit pages, or a different clip on the Fusion page or Color page. From there, whatever edits were applied to the formerly locked item get “checked in” and offered to every collaborator the next time they refresh their project (done by clicking a circular refresh icon that, within the Media Pool, sits to a bin’s right — or, on the Edit page Viewer, sits in its corner). Because every change a collaborator makes is committed to the project automatically as it happens, nothing you do will ever be lost while you collaborate with your team. Even so, each collaborator individually picks the moment to refresh whichever bin, timeline, or clip they’re currently on so they can take in everyone else’s changes — this keeps a never-ending swirl of shifting grades and compositions from pulling your attention away while you work. The sections coming up go deeper into Bin and Timeline locking and Clip locking.

### Automatic Bin and Timeline Locking

Each time a collaborator opens a given bin, that bin together with everything in it becomes locked, which blocks any other collaborators in the project from changing whatever lives inside it. That keeps versioning conflicts at bay while the work is underway. A locked bin still lets you look at its contents — handy when you simply need to learn where a certain clip ended up — but it won’t let you change anything. Although collaborators may open locked bins and view what’s inside for reference, they’re unable to make any editorial or organizational edits. Once a bin and its contents are locked, the only changes still permitted are building or revising clip compositions on the Fusion page and revising clip grades on the Color page. You can always spot that a collaborator holds a lock on a bin and its contents, because a badge surfaces beside the bin (on its right) within the Bin list, plus in the corner of whatever timeline thumbnails happen to be shown across the Media Pool browser area. Resting the pointer over that badge in the Bin list pops up a tooltip carrying that collaborator’s name.

When a fellow collaborator holds a lock on the Projects bin, an icon signals it. As soon as a collaborator (anybody but you) alters a bin’s contents or a timeline, a circular “refresh” badge turns up beside every affected bin in the Bin list of the Media Pool, next to that person’s collaborator icon. Click those badges any time you’d like to bring your copy of the shared project up to date with all of the editorial and organizational changes others made in that bin. Releasing a bin or timeline is as easy as picking a different bin or timeline. That’s all it takes.

When another collaborator has altered something, an icon flags it; a click refreshes your project so those alterations appear

### Managing Bin Locks Manually

The locked state of bins is also yours to steer by hand, for those occasions when you’d rather hold bins locked for later use, or stop them from locking at all when all you mean to do is glance through their contents.

### Keeping Bins Locked

When you’ve got one or more bins that you’ll be flipping back and forth between, and you want to stop other collaborators from changing them — or simply make sure no one else accidentally locks you out of them — you can right-click your selected bins and pick Lock Bins to lock them.

Bins locked this way stay locked even after you click away from them, right up until you right-click them once more and pick Unlock Bins. Because your collaboration icon is visible to other users too, they’ll be able to tell who currently holds the lock on the bin.

A bin you’ve locked by hand keeps its lock even after it’s deselected Keeping Bins Unlocked On top of that, you’re able to keep bins from locking when they’re selected. You might, for instance, only want to look over what’s in a bin without blocking anyone else from editing it. To do that, just Option-click any bin and it opens in read-only mode, flagged by an eyeball badge sitting at the left side of the bin within the Bin list. While you’re in this mode, any other collaborator remains free to lock that bin even as you look through its contents. Picking any other bin wipes out this read-only state.

Opening a bin in read only mode leaves your collaborators free to lock it as you look through what’s inside TIP: As long as a bin is open but you’ve manually left it unlocked, you can still load clips into the Source Viewer and tag them with markers — provided no other user picks that same bin and locks you out.

### Manually Locking and Unlocking Timelines

The locking of timelines is something you can also manage by hand. Opening a timeline locks every other collaborator out of changing that timeline, yet it still permits other users to alter the bin in which that timeline lives. That gives you more freedom in arranging your Media Pool and keeps you from locking media or other timelines sitting in the same folder. Individual Media Pool bins can still be locked by hand if you want to protect their contents on their own. To free a timeline so other collaborators can take it on:

- Right-click that timeline within the Media Pool and pick Timelines > Unlock Timeline from the contextual menu.

To lock a timeline and stop other collaborators from touching it: 1 Right-click that timeline within the Media Pool and pick Timelines > Lock Timeline from the contextual menu. 2 While you hold the lock, no other collaborator can alter the timeline, though they’ll still be able to alter any of the bin’s other clips and timelines.

### Automatic Clip Locking

On the Fusion and Color pages, clip locking behaves in much the same fashion. With many compositing artists at work on the Fusion page and many colorists at work on the Color page, whichever compositing artist or colorist is first to pick a particular clip automatically holds the lock over it. Every other compositing artist or colorist then sees a badge on that clip in the Thumbnail timeline indicating that it’s locked, along with who holds the lock. In the screenshot below, the SO badge in the corner of clip 7 on the Color page Thumbnail timeline signals that the clip is locked.

Within the Thumbnail timeline, badges show you which clips a collaborator has locked for grading Automatically Checking In Work When You Change Clips Once you’ve wrapped up the clip in front of you, you simply pick a different clip, and the edits you applied to the previous clip are saved automatically and pushed out to every other colorist working that timeline on the Color page. There’s no refresh to perform. That’s the key way clip locking on the Color page departs from bin locking.

### Compositing Artists and Colorists Can Work Together

Separate clip locks are kept by the Fusion page and the Color page apiece. So, across any group of compositing artists, just one of them can be on a given clip at any moment, and on the Color page only one colorist can be on a clip at any moment. Yet since Fusion and Color page clip locking is tracked independently, a single compositing artist and a single colorist are able to share one clip in the timeline at the same time — even with an editor also working that timeline.

### Receiving Changes Made by Collaborators

While you collaborate, it’ll often be the case that several compositing artists are running multiple compositions at once, the colorist and their assistants are busy with the grade, and the editor and their assistants are polishing the edit, with everyone pulling together inside the same project.

### Receiving Changes On the Edit Page

While compositors composite and colorists grade clips inside the same timeline of the same project, every clip touched on the Fusion or Color page fires off a Refresh badge in three spots on the Edit page, letting the collaborating editor(s) choose for themselves when to refresh their timeline and view what’s changed. In the top-right corner of the Timeline Viewer. A click on this badge refreshes the grades and composites for every clip in the open Timeline.

For any timeline whose edits, grades, and composites have changed, a clickable “update” badge shows in the Timeline Viewer’s corner To the right of the bin that holds the modified timeline within the Media Pool’s bin list. A click on this badge refreshes every clip in the Timeline inside that bin.

For Media Pool bins holding timelines whose edits, grades, and composites have changed, a clickable “update” badge shows over them In the top-right corner of every modified clip within the Timeline. Over any clip in the Timeline whose edits, grades, and composites have changed, a clickable “update” badge shows

### Receiving Changes On the Fusion and Color Pages

For anyone working the Fusion or Color pages, additional badges flag when editors have altered the Timeline, or when fellow compositing artists or colorists have altered other clips in that timeline. A timeline you’re shut out of because another collaborator holds its lock is flagged by a badge in the top-right corner of the Viewer, while alterations editors made to the Timeline on the Edit page are flagged by a refresh badge in that very spot. A click on this badge refreshes every clip in the Timeline.

Within the Viewer, a badge signals that someone else holds a lock on this timeline Open up the Media Pool and a badge turns up to the right of any bin in the Bin List that’s been rearranged or that holds a modified timeline. A click on this badge refreshes every clip in the Timeline inside that bin.

For Media Pool bins whose timelines have changed, a badge shows up on their right A badge surfaces in the top-right corner of each clip in the Thumbnail timeline that a fellow compositing artist or colorist has altered. Clicking a single clip’s badge refreshes that clip on its own.

Over any clip in the Timeline whose grade has changed, a badge shows. Clicking it refreshes that one clip alone.

### Examples of Collaborators Working Together

Whoever opens a timeline first is the sole person allowed to make editorial changes to it on the Edit or Fairlight pages. Anyone else who opens that project is “locked out” of editing on the Edit or Fairlight pages, yet they can still view the Timeline and apply grading changes on the Fusion or Color pages. So whenever you’d like several editors going at one project, a good approach is to split your program into separate “reels,” with each reel sitting as its own timeline in its own bin.

### Multiple Editors Working Together

Whoever opens a timeline first is the sole person allowed to make editorial changes to it on the Edit or Fairlight pages. Anyone else who opens that project is “locked out” of editing on the Edit or Fairlight pages, yet they can still view the Timeline and apply grading changes on the Fusion or Color pages. So whenever you’d like several editors going at one project, a good approach is to split your program into separate “reels,” with each reel sitting as its own timeline in its own bin. If, however, a couple or more editors truly have to work the same timeline, you can pull it off by duplicating the timeline and stitching the changes back together afterward. As an illustration, collaborating editor Anne might take these steps to revise a timeline that editor Erin already has open:

- To start, Anne can copy the locked timeline into a bin separate from the one Erin holds a lock on. Or Erin might get ahead of it and duplicate the timeline into a separate bin beforehand.
- Next, Anne re-edits her duplicate timeline, making whatever adjustments are needed to a scene other than the one Erin is busy with at the moment. Tackling different scenes is the tidiest and simplest way to run this workflow.
- Then, Anne uses Collaborative Chat to let Erin know the changes are done.
- Finally, Erin refreshes the project so Anne’s updated duplicate timeline shows up in the Media Pool,

then right-clicks it and picks Compare With Current Timeline from the contextual menu to bring up the Timeline Comparison window, which lets her fold the altered portion of the duplicate timeline into the original timeline Erin still has open. In the screenshot below, the changes Erin highlighted (made while Anne was busy) appear on the left, and Anne’s highlighted changes appear on the right. A right-click inside the right-hand highlighted region surfaces an Accept Change command, letting that scene’s edits move from the duplicate timeline over to Erin’s original timeline.

With the Compare With Current Timeline command you can spot how two separately edited takes on one timeline diverge, then fold a single scene’s worth of a collaborator’s edits (shown at right) into the original timeline

To read more about putting timelines side by side, refer to Chapter 34, “Creating and Working with Timelines.”

### Editors and Assistant Editors Working Together

Editing metadata, building new bins, and rearranging clips is something collaborators can only do inside unlocked bins. That means your project ought to be laid out so that an editor is able to lock the contents of whichever bins they need at a particular moment, while the assistants press on with extra timelines and media inside that project’s other bins. Beyond copying timelines out of a locked bin into a bin under your control, though, you can also copy clips from one timeline into another. So if you genuinely must alter source clips while the original source clips sit locked, you can apply your edits to copies of them instead.

### Editors and Compositing Artists Working Together

There’s plenty of room for editors and compositing artists to collaborate tightly, because a compositing artist can build compositions for one or more clips on a timeline even as it’s being edited — and even though that timeline, along with the bin holding it, is locked away from other editors. What follows is an example of an editor cutting a commercial spot loaded with greenscreen footage while teaming up with one or more compositing artists.
