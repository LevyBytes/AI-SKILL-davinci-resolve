# Using The Gallery (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using the Gallery

The Gallery gives you a way to store, browse, and draw on saved still frames pulled from a program's various clips. Every project keeps its own separate set of stills, and each still you store is made up of a DPX image of the saved frame plus the grade metadata. Saved stills come in handy as reference while matching one clip against another, or you can lean on them to copy grades onto other clips or other timelines. Two avenues exist for working with what's in the Gallery. The Color page carries a small Gallery, sitting left of the Viewer, that puts saved stills and grades within easy reach as you work. The Gallery window, which opens from a button at the Gallery's top right, hands you a dedicated interface for organizing your grades, ferrying grades and memories between projects, and reaching a dedicated collection of DaVinci Resolve looks.

The Color page's Gallery and the larger Gallery window environment share a good many of the same commands for organizing stills. That said, the commands for saving stills and for tailoring split-screen views stay confined to the Color page.

### Color page Gallery

### Saving Stills

Among the most frequent operations is storing a clip as a still (carrying that clip's embedded grade) for later reference and reuse. To store a single still on the Color page, take one of these actions:

- Choose Color > Stills > Grab Still (Option-Command-G).
- Right-click the Viewer and choose Grab Still.
- Press GRAB STILL on the Transport panel of any DaVinci Resolve control panel.

Stills can also be stored automatically for every clip across the whole Timeline. That comes in handy when you're set to export a batch of grades to pass off to another colorist, or when you have to apply a run of grades by hand from one project into another while ColorTrace™ won't cooperate. To store a still covering each clip across the current timeline, right-click the Viewer and pick from these:

- Grab All Stills > From First Frame: The first frame of every clip gets stored to the Gallery.
- Grab All Stills > From Middle Frame: The middle frame of every clip gets stored to the Gallery.
- Grab Missing Stills > From First Frame: Only the first frame of clips that have no stills in the Gallery gets

stored to the Gallery.

- Grab Missing Stills > From Middle Frame: Only the middle frame of clips that have no stills in the

Gallery gets stored to the Gallery.

You can halt the Grab All Stills operation whenever you like by clicking the Cancel button in the "grabbing stills" dialog box. That's useful when you spot a clip needing a change after the tool has started and you'd rather not sit through the whole timeline being grabbed before you fix it. With your correction made, simply fire off Grab All Stills again. By default, any stills you store are named "TrackNumber.ShotNumber. VersionNumber" with dots between each number. If you prefer, the General Options panel of the Project Settings offers an option to "Automatically label Gallery stills" along assorted lines. That's spelled out more fully later in this chapter.

### Selecting Stills

To select a range of stills, take one of these actions:

- Click one still, then Shift-click another to grab a contiguous range of stills.
- Command-click whichever stills you like to build a noncontiguous selection.
- Right-click any still and pick one of these commands; Select All: Grabs every clip in the Gallery. Select Current to Last: Grabs every still running from the one you clicked through to the last still in the Gallery. Select First to Current: Grabs every still running from the one you clicked through to the first still in the Gallery.

### Deleting Stills

When you need to clear one or more stills, that's only doable through the Gallery's contextual menu. To delete one or more stills, take one of these actions: 1 In the Gallery, select one still or several. 2 Right-click any one of those selected stills and pick Delete Selected. Each still further carries an assortment of metadata that DaVinci Resolve relies on to manage what's in the Gallery in various ways. That metadata can serve for searching and sorting too, and you view it by opening the Still Properties window. To show a still's properties: Right-click a still in the Gallery and pick Properties. A floating translucent window pops up showing the date the still came into being, which clip supplied it, the moment it was grabbed, plus the source and record timecode readings of the frame it originated from.

### Right-click on a still to choose Still Properties

### Where are Stills Saved?

By default, every grade/still you store lands in the DPX format and goes into the directory path set in the "Gallery stills location" field, which sits inside the Master Settings panel's Working Folders section over in the Project Settings. That path defaults to a hidden ".gallery" directory built at the spot of the first Media Storage Volume you name in the Media Storage panel of the System Preferences window.

### Changing the PowerGrade Still Directory

Optionally, you can shift where PowerGrade stills get stored by opening the Gallery Option menu and choosing Change PowerGrades Path. A "Select PowerGrades Folder" dialog then prompts you to pick a directory where all PowerGrades get stored.

### Live Previews of Gallery Stills

The Live Preview option, found within the Gallery option menu, gives you a preview of how the current clip would appear once a given Gallery Still grade is applied to the currently selected clip, all by gliding the pointer across the still you'd like to preview. Enabling and Disabling the Gallery Live Preview: 1 Open up the Gallery option menu and pick Live Preview.

With the Live Preview option for the Gallery browser, hovering over a saved grade previews it on the current clip inside the Viewer 2 Within the Node Editor, click whichever node you'd like to preview applying the still's grade onto. The live preview reveals how the current clip will look once the grade of the still you pick reaches the currently selected node of the current grade, which shapes the result. 3 Glide the pointer across the still you'd like to preview. The Viewer image refreshes, revealing how that clip would appear with that still's grade reaching the currently selected node.

### Hover Scrub in the Gallery

With Live Preview switched on in the Gallery option menu, the Hover Scrub Preview submenu lets you decide how Live Preview gets shown by a thumbnail in the Gallery, and in the Viewer, as the pointer passes over a still or LUT inside the LUT Browser:

- You can opt to scrub both the thumbnail under your pointer along with the Viewer, which previews the current still's grade or a LUT across the span of the current clip in the thumbnail as well as in the Viewer.
- You can opt to scrub the thumbnail by itself, so the Viewer keeps showing only the grade or LUT across whatever frame the playhead currently sits on.
- You can switch scrubbing off entirely, whereupon the thumbnail and the Viewer both show only the grade or LUT across whatever frame the playhead currently sits on.

The Hover Scrub Preview options when Live Preview is enabled

### Playing Stills and Setting Up Image Wipes

Plenty of routes exist for playing a still on the Color page, surfacing it as an image wipe in the Viewer and on the external display wired to your video interface. To play a still, showing it as an image wipe or full screen, take one of these actions:

- Double-click a still in the Gallery.
- Select a still in the Gallery, then click the Image Wipe button on the top Viewer toolbar.
- Click a still in the Gallery, after which you right-click within the Viewer and pick Show Reference Wipe.
- Out of the Color > Stills menu, pick Next Still (Option-Command-N), or pick Previous Still (OptionCommand-B), to select a still within the Gallery, and after that pick Wipe On/Off (Command-W) so it plays.
- On the DaVinci Resolve Advanced Search Dial panel—or else on the DaVinci Resolve Advanced control panel—press PREV STILL or NEXT STILL to select a still, then hit PLAY STILL. Hitting PLAY STILL a second time sends the still away.

Any time you play a still, the Viewer mode's drop-down menu shifts to Split mode. After it appears, you can slide and reorient, in various ways, the wipe separating the current clip from the still under reference. When you want a full-screen view so you can toggle back and forth between the still and the current clip, just nudge the split until the still takes over the whole Viewer. To adjust a wipe in the Viewer, take one of these actions:

- Drag the pointer inside the Color page's Viewer to move the wipe.
- On the DaVinci Resolve Advanced control panel's T-bar panel, push the T-bar lever up and down.

To tailor the kind of image wipe shown in the Viewer, take one of these actions:

- Click whichever of the controls sit at the top right of the Viewer toolbar to select among Horizontal, Vertical, Mix, Alpha, Box, and Difference types of wipe.
- Out of the Reference Wipe Mode submenu within the Viewer's option menu, pick Gallery, Timeline, or Offline.
- Pick from Horizontal, Vertical, Mix, Alpha, Difference, and Box by way of either the Wipe Style submenu within the Viewer's option menu, or else the style icons up at the top of the Viewer.
- Pick Invert Wipe (Option-W) from the Viewer's option menu.

### Timeline Wipes

A timeline wipe happens when you reach for the Wipe Timeline Clip command in the Thumbnail timeline (you'll find it in the contextual menu after right-clicking a clip other than the current one) to wipe the current clip against another clip in the Timeline, with no need to store a still beforehand. Switch a timeline wipe on and the timeline clip being wiped gets outlined in blue.

### Gang Timeline Wipe With Current Clip

A "Gang timeline wipe with current clip" option, reachable from the Viewer option menu, holds steady the offset separating the current clip from whatever timeline clip you're wiping against as you shift the current clip selection onto other clips. With this option switched on, the offset between the timeline wiped clip and the current clip holds steady as you move the clip selection. With this option switched off, the timeline wiped clip stays put no matter which clip you select.

### Change a Timeline Wipe Using the Timelines Album of the Gallery

As you lean on the Wipe Timeline Clip to display a wipe of the current clip set against any other Timeline clip, opening the Gallery's Timelines album and clicking different clips swaps which Timeline clip you wipe against (outlined in blue) while leaving the current clip alone (outlined in orange). Just confirm that the same timeline is selected across both the Timeline album and the Color page.

### Labeling and Searching for Stills and Sources

By default, a three-number code tags every still. That opening number names the video track carrying the clip, the next number gives the clip's position number within the current Timeline, and the final number gives the grade's version number. Once you've stored a heap of stills, it can pay to label the important ones with whatever text proves helpful. After labeling, you can hunt down stills by label through the Search field, over at the upper right-hand corner of the Gallery.

### All stills are numbered Track.Shot.Version

### Automatic Labeling

If you prefer, the Color group inside the General Options panel of the Project Settings offers options to "Automatically label Gallery stills" along assorted lines. The choices run deep:

- Clip Name: Stores the Clip Name, which falls back to the File Name unless you've customized it.
- Clip Version Name: Automatically stores the name of the current version.
- Source timecode (HH.MM.SS.FF): Stores the source timecode of the current frame.
- Timeline timecode (HH.MM.SS.FF): Stores the timecode for where the playhead sits

in the Timeline.

- Timeline Name: Stores the name of the Timeline currently open.
- Display LUT Name: Stores the name of the Display LUT currently in use, where one is applied.
- Custom label using tags: Pick this option and a field appears where you can either type custom

text or drop in metadata variables to store automatically updated information tied to the currently selected clip and timeline. For fuller detail on working with metadata variables, see Chapter 16, "Using Variables and Keywords." Across all options, there's also a checkbox you can flip:

- Append still number on export: Switch this checkbox on and you can decide how to fold in the default still number while exporting stills with the "Use labels on export" option active, either as a prefix or a suffix.

### Manual Labeling

Sometimes the simplest move is just to hand a given still a custom name that captures what that still stands for, like "SeemedLikeAGoodIdea." While naming stills by hand, steer clear of the forward slash character in case you end up exporting these stills with file names. As a matter of fact, it's wise to dodge the forward slash character for nearly any text you key into DaVinci Resolve. To label a still by hand: 1 Right-click a still in the Gallery and pick Change Label, or instead double-click in the area just below the Still ID. 2 Key a name into the Change Still Label dialog, then click OK.

The new label turns up beneath the still number.

### You can also label stills for easier identification

### Searching For Stills

After labeling, you can track down the stills you need in the Gallery. To hunt a still by its label: Click the Magnifying Glass button so the Search field opens, click once to set the cursor inside it, then type whatever name or description you're after. The moment you begin typing, DaVinci Resolve starts filtering the results of the currently selected album in the Gallery down to match what you've keyed in.

### Match Reference Wipe Frame

You can right-click any Gallery still and pick Match Reference Wipe Frame to automatically jump the playhead to the precise frame matching that still, and select that clip in the Color page Timeline.

### Gallery Options

Up in the upper right corner of the Gallery palette sit several options letting you adjust how your stills are viewed and organized.

- Still Size Slider: Drag this slider left and the still thumbnails shrink; drag it right and they grow.
- Sort Stills: Pick an option from this submenu to reorder every clip in the Gallery. Your choices: Still ID: Orders the stills by the ID number assigned to each (track, clip number, grade version). Label: Orders the stills by each one's text label. Record Timecode: Orders the stills by where each lands in the program. Source Timecode: Orders the stills by the timecode of whichever source clip they came from. Grab Date: Orders the stills by the date each was first grabbed. Create Time: Orders stills according to the moment you stored each one.
- Thumbnail View: Press this icon to put the gallery into Thumbnail view; each still shows up as an image.
- List View: Press this icon to put the gallery into List view; each still shows up as columns of text attributes.
- Search: Brings up a search dialog box for finding stills by their text label.
- Gallery View: Brings up the full Gallery Management window.

The Gallery options, reading left to right: Still Size Slider, then Sort Stills, Thumbnail, List, Search, Expand, and Options

Right-click the gray area of the Gallery, behind the Still icons, and you open a contextual menu offering a range of extra options for steering how many stills get stored, how they're shown, and how they're arranged in the Gallery. The options are as follows:

- Switch Wipe Mode: Flips the Reference mode among showing a "Gallery" still, a "Timeline" clip, or an "Offline" reference movie.
- Trace Timeline: When switched on, selecting a clip in the Timeline also auto-selects the first still that was stored from that clip to the Gallery.
- One Still Per Scene: When switched on, holds the Gallery to storing just one still per clip in the Timeline. Should several stills already have been stored before you flip this option on, those stills linger in the Gallery until you store another still from the same clip, at which point every other still from that clip vanishes.
- Apply Display LUT: When a Display LUT sits selected within the Project Settings, over in the Color Management panel's Lookup Tables panel, it reaches the video output through a connected video interface, and reaches the Viewer too. As a rule you wouldn't want that Display LUT reaching stills you're storing as well, given it's meant to stay temporary. So stills get stored with a LUT-free image. Still, for cases where you might also want to keep a reference to the Display LUT currently in use, switching on "Apply Display LUT" stores the Display LUT alongside the still and applies that LUT whenever the still serves for split-screen reference. Bear in mind that the internally stored Display LUT only kicks in while playing that still in the Viewer; the DPX image that's stored stays untouched.
- Apply Grades Using: This submenu holds three options governing how the keyframes automatically stored within each saved grade get applied.

No Keyframes: No keyframes get copied. Whatever state the grade held at the frame used to store the still is what lands on the target clip or clips. Keyframes Aligning Source Timecode: Keyframes get copied with the source timecode of the saved grade lined up against the source timecode of the target clip. This is the ideal pick while copying a grade back onto the clip it originally came from, or onto a duplicate of that clip elsewhere in the Timeline, where you want the keyframes lining up with the same frames as before. Where no source timecode overlap exists, keyframes get pasted lined up with the edit's start frame, matching the third option (below). Keyframes Aligning Start Frames: Keyframes get copied with the start frame of the clip the still was stored from lined up against the start frame of the target clip. This is the ideal pick while copying a grade carrying keyframes from one clip onto an entirely different clip with different timecode.

- Use labels on still export: Lets you fold labels you've attached to stills into the file name of exported stills.
- Show All Stills: This command surfaces every available still in the current album should any have been hidden, by searching or by the Show Current Timeline Only command, for instance.
- Show Current Timeline Only: Pick this option to hold the Gallery to showing only the stills stored from the currently selected Timeline. Every other still from other Timelines stays hidden until you switch over to that Timeline.

NOTE: A range of other commands live in this contextual menu and get covered elsewhere in this chapter.

### Organizing Stills Using Albums

Every still you store always drops into the Gallery's currently open album, which for new projects defaults to "Stills 1." That said, you can spin up extra albums for sorting your stills by whatever categories suit you. Showing, creating, and removing albums all happen through the Gallery in either the Color page or the Gallery windows.

### Use albums to organize your stills

To show or hide the Albums list: Over at the Gallery's top left, click the Album button. With the Albums list hidden, clicking the Album button surfaces the Albums list, left of the Gallery, holding every album currently available in the open project, plus the PowerGrade album down at the bottom. With the Albums list already showing, it goes hidden instead, freeing up more room for still thumbnails in the Gallery. Once the Albums list is up, several quick and easy ways exist to work with albums. Ways to work with albums:

- To add a new album: Right-click the Albums list and pick Add Still Album from the contextual menu. A new album springs up, numbered in sequence.
- To add a new PowerGrade album: Right-click the Albums list and pick Add PowerGrade Album from the contextual menu. A new album springs up, numbered in sequence.
- To rename an album: Double-click any album in the list, and once it's selected, type a new name and press Return.
- To navigate albums: Click any album to make it the current one. On the DaVinci Resolve Advanced control panel, the PREV PAGE/NEXT PAGE buttons let you move up and down the Album list.
- To move clips from one album to another: Take a still from the Gallery and drag-and-drop it onto an album.
- To remove an album: Right-click any album, pick Remove Current Album, and click Delete at the prompt. Every clip inside that album gets deleted right along with the album, so tread carefully here.

### PowerGrade Albums

PowerGrade albums are built to hold grades you mean to reuse often, or stills you have to reference across multiple projects—say while grading a series that carries common looks from one episode to the next.

### PowerGrades are associated with your user login

Unlike stills stored in the list's other albums, which are usually on hand only to the project where they were stored, stills stored to a PowerGrade album are shared across every project kept within a given project library. Each project library carries its own unique PowerGrade album. Building a new project library builds a new PowerGrade album, which begins as a blank slate. Even so, the Gallery window is always there to copy PowerGrade stills out of other projects and project libraries into the current one, and you can spin up however many PowerGrade albums you need to organize your grades. For fuller detail covering project management plus project libraries, see Chapter 3, "Managing Projects and Project Libraries." In function, PowerGrade albums are no different from any other album, and you can store, organize, and use stills in PowerGrade albums just as you would with other albums. Because PowerGrade albums are special in that DaVinci Resolve maintains them, the last PowerGrade album can't be deleted.

### Browse all Grades from the Current Timeline

The Gallery carries a Timelines album, found at the bottom of the Album list, that lets you browse every grade in the current timeline, or in other timelines of the current project (by way of a drop-down menu that appears atop the Gallery browser area), making it simple to lift grades from points earlier or later along your timeline, or out of other timelines drawing on the same media. This proves especially handy on reality shows or documentaries where the same clips can crop up several times across different parts of a program. Being able to just surface every existing grade in the Gallery spares you from storing a still for every grade you suspect you might reuse down the road.

The Gallery's Timelines grade browser surfaces, on its own, every grade across the current timeline

### The Gallery Management Window

Although a fair bit of stills management is possible through the Gallery as it appears on the Color page, the Gallery window brings extra capability: copying stills across separate projects and project libraries, organizing your stills along with your memories, plus reaching the DaVinci Resolve looks bundled with the application. To open the Gallery window: At the upper right-hand corner of the Gallery, click the Gallery View button, or else select Workspace > Gallery.

### Gallery window

The Gallery opens into a floating window, split into four areas:
