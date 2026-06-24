# Color Page Timeline And Lightbox (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Color Page Timeline and Lightbox

Made up of the Thumbnail Timeline together with the Mini‑Timeline, the Timeline found in the Color page mainly helps you move through how clips are currently laid out, and keep tabs on per-clip attributes — for instance whether a shot is graded or ungraded, whether tracking is in play, the version that's active, and the like. Beyond that, it speeds up duplicating grades between clips, building groups, and lining shots up side by side in the Viewer. Acting as the Thumbnail Timeline's counterpart, the Lightbox offers a picture-driven way to weigh clips against each other, handle grades, and carry out many kinds of sorting jobs. The pages ahead describe how both the Timeline and the Lightbox are used.

### Navigating Using the Color Page Timeline

Two cooperating components make up the Color page Timeline: the Thumbnail Timeline plus the Mini Timeline. In tandem they give you several distinct ways to inspect and travel through your program's Timeline.

### The Color page Timeline

Each of the two scroll bars — one for the Mini-Timeline and one for the Thumbnail Timeline — operates separately, so each may be configured to reveal a different span of clips. Rolling your pointing device's scroll control adjusts the Mini-Timeline's zoom level inward or outward. At its fullest zoom-out, the Mini-Timeline fits the whole timeline inside whatever screen width is on hand, giving you a quick route from the program's start clear through to its finish. Even so, you're free to zoom in on a given stretch whenever you require more detail about how a dense stack of layered clips is laid out as you grade.

### Thumbnail Timeline

Gives you a compact picture of the project in which every clip shows up as one numbered thumbnail no matter how long it runs. A click on any thumbnail jumps the playhead onto that clip's opening frame, whereas the Up/Down Arrow keys shift the selection back to the prior clip or ahead to the following one. The clip sitting under the playhead's present location is shown with an orange border around its thumbnail. Both middle‑click-and-drag and your pointing device's scroll wheel let you roll back and forth across the Thumbnail timeline.

### The Color page Thumbnail Timeline

Above and beneath every thumbnail sits assorted data — among it a rainbow border encircling the count of graded clips, the text under each thumbnail showing clip format, file name, or grading version, badges for tracking or stabilization, flag badges, plus link badges that signal clip groups or automatic remote grade linking wherever it applies.

### Mini-Timeline

Presents a scaled-down version of the Edit page's Timeline, with the width of each clip matching how long it lasts and any layered clips stacked over each other. No more than six video tracks fit in the Mini‑Timeline at once; should your edit carry additional ones, a scroll bar lets you swap which tracks show. A click on any clip within the Mini-Timeline picks that clip and parks the playhead on its opening frame.

### The Color page Mini-Timeline

### Scrolling, Zooming, and Navigation

Housing the playhead's top handle, a Timeline Ruler shows the record timecode for the present edit and works as a scrubber bar that normally covers a wider stretch of the Timeline. Your mouse's scroll wheel zooms your edit both ways, and zooming fully out lets you pack every clip of the Mini-Timeline within the ruler's available width, so you can scrub through the Timeline's entire run of clips fast. A click on any spot inside the ruler snaps the playhead straight to that frame.

### Enabling/Disabling Tracks

Track numbers for each track sit at the Mini-Timeline's far left, and floating the pointer above any track's number in the Color page's Mini-Timeline surfaces a tooltip with that track's name. A click on a track number toggles that track on or off together with every clip riding it, much as the Timeline > Enable/Disable Video Tracks submenu commands do (Shift-Command-1 through 9). Clips sitting on switched-off tracks neither render in the Viewer nor in video output, and they vanish from the Thumbnail Timeline. Should a track already be disabled back in the Edit page, it shows up dimmed within the Mini-Timeline. Option-clicking a Mini-Timeline track number tints that track number red, which lets you conceal clips from the Thumbnail Timeline while leaving the video in your program enabled. That comes in handy when you'd rather keep clips on one track (say, titles or motion graphics rendered by a separate program) from catching the playhead as you run the next/previous clip commands.

### Setting In/Out Points for Looping

The I and O keyboard shortcuts let you place your own In and Out points across the Timeline. After they're set, switching on Loop within the Viewer transport controls makes that span loopable, be it a piece of a single clip or a stretch covering several clips at once.

### Navigating to Clips Using Clip Number

Within the Color page you can leap straight to any particular clip by referencing its clip number in the Color timeline. To reach a clip, pick Playback Go To > Clip Number, then key a clip number into the timecode entry field and hit Enter. Doing so selects that clip and parks the playhead at its start. As an alternative, you may key in the clip number first and then choose the menu command in place of pressing Enter, yielding the same outcome. To work faster, you can also bind this operation to a keyboard shortcut named "Clip Number" if it's something you reach for regularly.

Shown in red, the timecode entry area is where a clip number gets typed to leap there during a Go To Clip Number operation

### Using Multiple Timeline Playheads

Within the Mini-Timeline, DaVinci Resolve lets you make as many as four independent playheads, handy for hopping between separate spots in your timeline. At any moment just one playhead may be active, and whichever is active marks the current clip, shown in orange. Every Mini-Timeline playhead carries a label running from the letter A through D.

Several Mini-Timeline playheads serving multi-region navigation How you place a fresh playhead into the Mini-Timeline:

- Pick a playhead out of the Color > Active Playheads submenu. It lands wherever the original playhead sits, yet it's now the active one, so dragging the fresh playhead somewhere else in the Mini-Timeline will uncover the original playhead you had been on.

To select another playhead to view:

- Click the top handle of whichever playhead you want to make it the active one driven by the transport controls. Out of the box none of the four available playheads carry keyboard shortcuts, but you can build a custom keyboard mapping to flip between them in a hurry.
- With the DaVinci Advanced control panel, the A, B, C, and D buttons on the jog/ shuttle panel let you jump to whichever playhead you wish to drive.

To eliminate all additional playheads from the Mini-Timeline:

- Choose Color > Active Playheads > Reset Playheads.

### Show Current Clip With Handles

When your project sits inside a round-trip workflow and you're aware you'll render handles per clip, briefly revealing those handles for the clip you're grading can help, since it lets you readily lay tracking or keyframing effects across each clip's full frame span. To toggle clip handles on or off within the Color page's Mini-Timeline:

- Choose View > Show Current Clip With Handles.

(Left) The Mini-Timeline's current clip, (Right) That very clip displayed once Show Current Clip With Handles is switched on As long as this mode stays on, Unmix is forced on and can't be switched off, so that you can clearly see each clip's overlapping handles. How long the revealed handles run is governed by the Default Handles Length parameter found in the Editing panel of the User Preferences. You can reveal or conceal Clip Handles whenever you like.

### Thumbnail Info

Because the thumbnails always render the media in its current graded state, they make spotting the clips you need a visual breeze. The single most evident detail is whichever frame stands in for each clip's thumbnail. Should you decide a given clip's thumbnail doesn't really capture its content, it can be swapped. To change the current thumbnail:

- Hover the pointer over a thumbnail, drag rightward or leftward to scrub the clip, and halt once you reach a frame you'd like as the replacement thumbnail.

### Dragging a thumbnail to change the representative image

When media gets swapped partway through a color correction timeline, or once you copy or ripple a grade across a span of clips, the thumbnails might not refresh right away to faithfully mirror each clip's present condition. Should that happen, you can refresh the thumbnails by hand.

To refresh all thumbnails in the Timeline:

- Right-click any spot in the Thumbnail timeline and pick Update All Thumbnails. You also have the option to show the codec, clip names, and the version each Timeline clip is using.

To switch the Thumbnail timeline between showing clip names, codecs, and versions:

- Double-click any clip's thumbnail clip name to rotate through that clip's codec, clip name, and version. Extra detail shows up over and under every thumbnail, offering a way to monitor which clips are graded, which run different versions, which have been cached, and the like.

Every clip thumbnail carries several useful markers that make rapid comparison against other shots easy. The list below clarifies each detail that may turn up over, inside, or beneath the Timeline's thumbnails.

- Clip number: (top left) The number of each clip shows above its thumbnail. Numbering climbs from left to right based on where each clip's first frame falls, no matter which video track holds the clip.
- Grade indicator: (top left) Once a clip has been graded, a slim rainbow ring wraps the clip number.
- Source Timecode: (top center) Above every thumbnail you'll find the source timecode taken from each clip's opening frame.
- Cache indication: (red timecode) Whenever a clip is flagged for caching — be it by the Smart cache automatically or by hand — its timecode goes red to signal it's headed for caching. After the cache completes, that timecode shifts to blue.
- Track number: (top right) Above the thumbnail appears the video track on which a clip is cut.
- Clip Color dot: (upper right) Should a clip carry an assigned clip color, a tinted dot lands atop its thumbnail.
- Flag icon: (upper left) When a clip carries a flag, a flag icon in the matching color sits over its thumbnail. Where a clip holds several flags, as many as will fit are drawn along the top.
- Linked media or group icon: (bottom right) Where clips are set to draw on remote versions, and where several clips draw on one shared source media file, their remote version 1 grade links up automatically by default. When the current clip is linked, a tiny link icon shows under the thumbnail of every other Timeline clip linked to it. Pick a clip that isn't linked and those linked-clip icons go away.
- Tracker icon: (bottom right) If any node inside a given clip's grade has been tracked, a tiny crosshairs tracker icon turns up beneath the thumbnail.
- 3D indicator: (bottom right) Each stereo 3D clip on the Timeline carries this icon under its thumbnail. Its color tells you which eye you're watching; red marks the left eye, blue the right.
- Version name/Source format: (bottom left) You can alter what shows beneath each thumbnail by double-clicking the area under it. Several choices exist; keep double-clicking to rotate among them: Clip format or codec: This is the default display. Clip Name: Based on the View > Show File Names setting, either the clip name or the file name shows. Working with multicam clips means the multicam name or angle appears. Version name or number: Tells you whether a clip draws on a remote version or a local one, the latter shown by an (L). Should you have named the current version, that name appears; if not the version reads "Version" followed by its number.

### Thumbnail Contextual Menu Commands

A right-click on any clip's thumbnail within the Thumbnail Timeline opens a contextual menu packed with the Color page's many media and grade management commands. Those choices fall into roughly these groupings:

- Commands for managing grade versions
- Commands for managing groups
- Commands for editing flags, markers, and clip colors
- A command for displaying the Node Graph of a clip's grade
- Options for controlling the render cache
- Resolve Color Management clip assignments
- LUT Management commands
- Commands that show clip details, edit Clip Attributes, and locate clips within the Media Pool
- A command that refreshes clip thumbnails which lag in updating by themselves

The chapters elsewhere in this manual cover these abilities at greater length, but the takeaway is that Color page artists have plenty of clip management choices on hand without ever leaving for other pages.

### Sorting and Filtering Clips in the Thumbnail Timeline

Out of the box, the Thumbnail Timeline lays out every clip of the Edit page's currently chosen edit, ordered in A mode (your edit's record order). That said, you can reorder and filter both the sort and the Timeline's contents to make tracking down particular clusters of clips for grading simpler.

### Changing Timelines

Should your project hold more than a single timeline, you can swap timelines without leaving the Color page. Swapping timelines from the Color page works like this: Pick a different timeline out of the Timelines drop-down menu sitting at the Viewer's top.

Timeline selection at the top center of the Viewer

### A and C Mode Sorting

By default the Timeline runs Record mode sorting, which also goes by the name A mode sorting. Under it, clips line up in the Timeline following the sequence in which they were cut. That lets you preview the clip order exactly as it'll show in the finished program.

### A Mode sorting, i.e., record order

You can, however, flip the Timeline's clip sort to Source mode, otherwise called C mode sorting. With C mode sorting, every clip is reordered left to right in climbing order by its source timecode, while record timecode is set aside for the moment.

### C Mode sorting, i.e., source clip order

Sorting via C mode makes pinpointing a band of like clips straightforward. Take a narrative project: clips from each coverage angle of the scene will gather together on their own. For another case, applying C mode sorting in a documentary lines up all the head shots of one subject from a given interview back to back, since every one stems from the same timecode range on the same source tape. In each case, the way C mode pulls similar clips near one another makes it simple to share grades across them, ripple edits, or group them. Once you're done, you can flip the Timeline back to A sort mode, and all the clips return to the sequence in which they were cut. Flipping back and forth between A and C mode sorting is done by either of these:

- Choose an option from the View > Timeline Thumbnail Mode submenu.
- Hit Command-Page Down to flip into C mode sorting. Whenever C mode is active, the word "SOURCE" shows up on the right side within the Mini-Timeline's Timeline Ruler.

Source mode indicated at the right of the Timeline ruler

### General Options panel of the Project Settings

Found in the Conform Options group within the Project Settings' General Options panel, a checkbox lets you adjust how C mode sorting behaves. Open the Settings window and click the Project Settings' General Options panel to expose the Sort Timeline Using Reel Name and Timecode checkbox. When that box is on (its default), every Timeline clip sorts by reel name first and then by source timecode. That way, clips carrying similar timecode off the same reel land beside each other under C mode. Turn the box off and reel name is disregarded, with all Timeline clips sorted solely by source timecode. The result may blend clips from several sources together, yet it proves handy in certain cases.

For instance, when grading dailies off a three camera shoot, you might prefer to view back-to-back clips from each of the three cameras lined up in turn on the Timeline, so that Cam1*Shot1, Cam2_Shot1, and Cam3_Shot1 come first, trailed by Cam1_Shot2, Cam2* Shot2, and Cam3_Shot2, and onward. Here you don't want the clips from cameras 2 and 3 shoved to the Timeline's tail end merely on account of their reel name.

### Flags, Clip Colors, and Markers

Just as in the Edit page, the Color page lets you flag or mark clips to keep track of specific media or frames you might need to attend to down the line. As an example, you could tag every closeup of one actor showing a blemish you intend to spend time repairing with a green flag. Ways to flag, recolor, and mark clips on the Color page:

- To add a flag to a clip: Park the playhead on a Mini-Timeline clip, then pick a color out of the Mark > Add Flag submenu, or Right-click whichever clip's thumbnail you like and grab a flag color from the Flags submenu. Since flags aren't frame-bound, flagging a single clip drops flags onto each other clip relying on that same source media in the Media Pool as well.
- To remove all of a clip's flags: Park the playhead on a Mini-Timeline clip, then go to Mark > Clear Flags, or right-click that clip's thumbnail and pick Flags > Clear All.
- To change the clip color: Park the playhead on a Mini-Timeline clip, then pick a color from the Mark > Set Clip Color submenu, or Right-click whatever clip's thumbnail and grab a color out of the Clip Color submenu. Clip Colors are clip-specific.
- To remove a clip's color: Park the playhead on a Mini-Timeline clip, then go to Mark > Set Clip Color > Clear Color, or right-click that clip's thumbnail and pick Clip Color > Clear Color.
- To mark a frame of a clip: Right-click that clip's thumbnail and grab a marker color from the Marker submenu.
- To remove a single marker: Right-click the clip's thumbnail and pick Delete Marker out of the Marker's submenu. As another route, highlight the marker within the Mini-Timeline and tap the Delete key.
- To remove all of a clip's markers: Right-click the clip in question and pick Clear All from the Markers submenu.

### Timeline Filtering

Sitting to the right of the Clips button up at the Color page Interface Toolbar's top right, a drop-down button offers preset ways to filter on the fly which clips the Timeline shows. With it you can mask every other Timeline clip aside from the subset you wish to concentrate on.

### Timeline filtering options

Take an example: after you've attached flags or markers to clips, masking every remaining Timeline clip that fails the test — say, hiding any clip lacking a green flag — becomes easy. None of this touches the underlying edit, and you can restore the Timeline to its starting state whenever you wish.

To filter the Timeline:

- Click the Timeline Filtering drop-down button, which sits just right of the Clips button over at the DaVinci Resolve UI's top left, then pick whichever option is offered. While filtering remains in effect, an orange line shows beneath the Clips button in the page's top UI toolbar.

To return the Timeline to normal:

- Click the Timeline Filtering drop-down button, and choose All Clips. Timeline filtering pairs with either A or C mode sorting so you can lay clips out in whatever fashion suits the job at hand. Clip filtering works in the Lightbox as well, and whichever clip filtering method is active will isolate clips across both the Timeline and Lightbox in step as you move between them.

### Preset Timeline Filters

DaVinci Resolve ships with a handful of preset rules for filtering the Timeline, spanning many of the usual organizational workflows:

- All Clips: Nothing gets filtered out, so each clip of the present edit appears.
- Selected Clips: Filters all currently selected clips.
- Graded Clips: Filters all clips that have been graded.
- Clips with Fusion Composition: Clips with Fusion page effects applied to them.
- Ungraded clips: Filters all clips that have not yet been graded.
- Modified clips: Submenu, filters every clip altered inside a given time window.
- Unrendered clips: Filters all clips that have not yet been rendered.
- Clip Color: Filters every clip carrying any color, none at all, or one specific color assigned within the Timeline;

a submenu presents each color.

- Flagged Clips: Filters every clip bearing any flag, none, or one specific flag; a submenu

presents each color.

- Marked Clips: Filters every clip holding any marker, none, or one specific marker; a submenu

presents each color.

- Keywords: Filters every clip to which a given keyword is assigned. A submenu lays out a list holding

each keyword in use across the present project's Media Pool.

- People: Filters every clip tagged with a given person via the People Management

Window. A submenu automatically lays out a roster of each person who's been identified.

- Stereoscopic: Filters stereo 3D clips; via a submenu you can narrow to All Stereo Clips, or

restrict to Stereo clips that were Autoaligned, ones carrying Convergence adjustments, ones with Floating Windows adjustments, or stereoscopic clips whose left- and right-eye media has been swapped.

- Grouped: Filters every clip that sits inside a given group; a submenu lists each group on offer.
- Tracked: Filters all clips with motion tracking.
- Noise Reduction: Filters all clips using noise reduction.
- OpenFX: Filters all clips using OpenFX.
- Different Frame Rate: Filters every clip whose frame rate differs from the project's own.
- Edit Sizing: Filters every clip on which some Edit Sizing parameter was changed.
- Input Sizing: Filters every clip on which some Input Sizing parameter was changed.
- Common Media Pool Source: Filters every clip that draws on the same Media Pool source as the present clip does.
- Matte Nodes: Filters every clip that carries an exposed Matte node inside the Node Editor.
- Mattes Available: Filters every clip with a matte attached, regardless of whether it's actually in use.
- Collaborative Update Available: (Only available in Collaborative Mode) Filters every clip marked as having received an update over the course of a collaborative workflow.

### Creating and Using Smart Filters
