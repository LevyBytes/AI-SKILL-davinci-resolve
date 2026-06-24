# Preparing Clips For Editing And Viewer Playback (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Preparing Clips for Editing and Viewer Playback

Ahead of any cutting, many tasks help you get footage ready. This chapter walks you through browsing, picking, and playing back the material you need to log — placing markers, marking In and Out points, and building subclips as you spot the pieces you intend to use further along in your edit.

### Keyboard Shortcuts in This Chapter

Below you’ll find several keyboard shortcuts that may prove useful for the subjects covered here.

Key Shortcut Arrow Keys (Media Pool)

### Function

Shifts the selection within the Media Pool; the left and right arrows additionally expand and collapse bins shown in the Bin list

Shift (modifier)

Keep Shift pressed as you click clips to grab an adjacent, unbroken range

Command (modifier)

Keep Command pressed as you click clips to gather scattered, non‑adjacent clips

### Command-A

Select all; grabs every clip in the Media Pool browser region

### Return or Enter

Loads the chosen clip or timeline into the Source Viewer (when in dual viewer mode) or the Viewer

### I, O

Mark an In or Out point within the Media Pool, Source Viewer, or Timeline

### Option-Shift-I, O

Mark a video-only In or Out point within the Media Pool, Source Viewer, or Timeline

### Command-Shift-I, O

Mark an audio-only In or Out point within the Media Pool, Source Viewer, or Timeline

### Shift-I, O

### Move playhead to in/out point

### Spacebar

### Play and stop

### J, K, L

Reverse playback, halt, forward playback; further applications appear later in this chapter

### Option-L

### Play again

### Option-K

Halt and return to the playhead’s previous spot

/

### Play around current selection

### Up, Down Arrow

### Go to previous clip/edit, go to next clip/edit

M

### Add marker; doesn’t stop playback

### Command-M

Place a marker, bring up modify marker while playback pauses, and then resume playing

### Shift-M

### Modify marker

### Option-M

### Delete marker

### Shift-Up, Down Arrow

### Go to previous/next marker

### Option-B

Build a subclip (within the Media Pool bin currently selected)

### Browsing Clips in the Media Pool

The steps below explain how to pick one or several clips inside the Media Pool for different editing jobs — whether you open a clip in the Source Viewer or gather a batch of clips for drag-and-drop work. We begin by covering the various ways to look through what the Media Pool holds, so you can locate the clips you want before settling on a selection for the next step. Ways to browse clips in the Media Pool: while Metadata View mode is active, every clip appears as its own card carrying a thumbnail alongside essential clip metadata. The intent of this view is to surface richer metadata than a plain thumbnail yet stay more focused than the List view. Paired with its Sort modes, this becomes a strong tool for arranging and rearranging the clips held in your Media Pool.

- Hover-scrubbing a thumbnail in the Media Pool’s Metadata view: slide the pointer across a thumbnail and its frames scrub past.

The Metadata View icon view (its icon lit up in the top bar), with the scrubbed thumbnail sitting beside that clip’s metadata

- Hover-scrubbing a thumbnail in the Media Pool’s Thumbnail view: move the pointer over a thumbnail and you’ll scrub through what it contains.

### Thumbnail hover scrubbing

- Working with the Media Pool Filmstrip in List view: turn on “Show Filmstrip” from the Media Pool’s option menu. Click a clip and it appears in the Filmstrip running along the top of the Media Pool; pass the pointer over the Filmstrip to see it play. Whenever you like, double-clicking a clip in the Filmstrip opens it into the Source Viewer.

Using the Filmstrip when the Media Pool is in List view

TIP: As you browse footage, a double-click in the Media Pool opens any clip you’d like to inspect more closely in the Source Viewer. At the same time, a single clip can keep loading other clips in the Filmstrip, letting you weigh several clips against the main one still sitting in the Viewer.

### Selecting Clips in the Media Pool to Edit

After locating one or more clips you intend to use, the next move is to highlight them so you can carry out an edit. Ways to choose clips in the Media Pool with the mouse:

- To grab a single clip: Click a clip in the Media Pool.
- To grab an unbroken span of clips: From Metadata, Thumbnail, or List view, drag a marquee across every clip you want, or click the first clip of a run and then Shift-click the last one to capture both ends plus everything between them.

### Selecting a contiguous range of clips

- To grab a scattered set of clips: Command-click every clip you’d like in the group. Alternatively, keep the Command key held while dragging marquees across unselected clips to fold them into the group, or across already-selected clips to drop them back out.

### Selecting a noncontiguous range of clips

Ways to choose clips from the keyboard:

- To move through the Bin list: Click any bin in the Bin list sitting left of the Media Pool, or hit Command-1 so the Bin list becomes the Edit page’s active pane, then run the Up and Down Arrow keys to travel through the bins on offer. The Right Arrow key reveals a closed bin, while the Left Arrow key shuts it again.
- To pick a single clip: Hit Command-1 so the Media Pool Bin list takes focus, and use the arrow keys to highlight and open bins. Next press Command-2 to jump into the clip browser area and step from clip to clip with the Arrow keys. With a clip highlighted, any of the edit keyboard shortcuts will cut that Media Pool clip directly into the Timeline that’s currently open.
- To pick several clips: Keep the Shift key held as you tap the Arrow keys, growing or shrinking an unbroken selection inside the Media Pool.
- To pick every clip in the Media Pool: Give the Media Pool focus by clicking a clip or clicking anywhere in its empty background, then press Command-A to take them all.
- To send a highlighted clip or timeline into the Source Viewer: Press the Return key. After a clip lands in the Source Viewer, the transport controls let you play right through it.

### Duplicating Clips in the Media Pool

To make copies of clips within the Media Pool, Option-drag one or several clips into a different bin. You can equally highlight the clip or clips you wish to copy and then choose Edit > Duplicate Clips. Those copies land in the same bin that holds the original media. Each duplicate keeps its own separate link back to the source media stored on disk.

### Viewer Playback and Navigation

Out of the box, the Edit page gives you a classic source/record editing setup. With the Source Viewer you inspect single clips drawn from the Media Pool and ready them for cutting. The Timeline Viewer, by contrast, plays your program back and displays whichever frame the Timeline’s playhead currently sits on.

### Source and Timeline Viewers

### Source and Timeline Viewers vs. Single Viewer Mode

Should you wish to rearrange the Edit page so the Source Viewer disappears, pick Workspace > Single Viewer Mode; one viewer then stands in, showing either a chosen Source Clip or the Timeline’s present frame depending on context.

### Single Viewer mode

While Single Viewer mode is on, your current pick in the Media Pool or Timeline drives which controls show up in the Viewer, so you can accomplish nearly all the same tasks you would with both viewers open at once.

### Opening Clips Into the Source Viewer to Prepare for Editing

After settling on which clips belong in your program, send them to the Source Viewer for a fuller look. The behavior here hinges on the Source Viewer’s Live Media Preview setting. To skim a Media Pool metadata or thumbnail and watch clips in the Source Viewer via Live Media Preview: 1 Switch on Live Media Preview (if it isn’t already) from the Source Viewer option menu by choosing Live Media Preview. 2 With the Media Pool showing in Metadata or Thumbnail mode, hover the pointer over a clip; after a brief pause its thumbnail begins to skim, and the portion you’re scrubbing shows up in the Source Viewer. Then do one of these: a) While you skim inside the thumbnail, the playhead in the thumbnail stays tied to the one on the Viewer’s jog bar, and as you skim you can drop markers and set In and Out points b) Keeping the pointer parked over that clip, drive the JKL keyboard shortcuts to play it through, adding markers and setting In and Out points however you wish 3 Because skimming waits a beat to kick in, you can dart the pointer off that clip and back to the Source Viewer without triggering any other clip. Switching Live Media Preview off returns you to the more deliberate, conventional ways of loading clips into the Source Viewer.

To send a clip to the Source Viewer with the mouse: Double-click any clip in the Media Pool, or one in its Filmstrip, and it opens into the Source Viewer. To bring the bin’s previous or next clip into the Source Viewer: 1 Click within the Source Viewer so it holds focus. 2 Tap the Up Arrow key to step back to the prior clip in the bin that’s open and load it into the Source Viewer. 3 Tap the Down Arrow key to advance to the following clip in that same bin and load it into the Source Viewer. To send a clip to the Source Viewer with the keyboard: 1 If needed, press Command-1 to land on the Bin list, then use the Up and Down arrows to pick a folder and reveal its contents. The Right Arrow key opens folders and exposes any nested ones within, while the Left Arrow key collapses folders and hides what they nest. 2 Press Command-2 to jump to the Media Pool browser, and shift the highlight from clip to clip across the Media Pool — up, down, left, and right — with the Arrow keys. 3 With your target clip highlighted, press Return to open it into the Source Viewer. To send a timeline to the Source Viewer: Drag a timeline and drop it onto the Source Viewer, ready either to gang it against the existing Timeline or to cut it, whole or partway using In and Out points, into the Timeline currently open. Monitoring with an External Video Display As you work on the Edit page, what shows on a connected external video display is governed either by the present Media Pool selection or by which portion of the Edit page interface holds focus. For instance, selecting a clip in the Media Pool so it appears in the Filmstrip sends that clip out to video. Opening it next into the Source Viewer routes the Source Viewer’s contents to video instead. Switch over to the Timeline Viewer and your timeline becomes the video output.

### Viewer Transport Controls

Two Viewers sit on the Edit page. While cutting, the Viewer on the left should be set to source video or source audio so it presents the source clip for whatever edit you’re building. On the right sits the Timeline Viewer, displaying the frame under the playhead’s current Timeline position. Between the Source and Timeline Viewers, you can assemble a broad range of edits. Transport controls run beneath each Viewer.

The transport controls at the bottom of the Source Viewer

Sitting right below the transport controls is a jog bar that lets you drag the playhead by hand with the pointer. The entire span of the Source Viewer’s jog bar maps to a clip’s whole length, whereas the entire span of the Timeline Viewer’s jog bar maps to the whole length of the current timeline. Each playhead’s present spot is reported in the timecode field tucked into the upper right-hand corner of its viewer. Off to the left of the other transport controls, a standalone jog control (<o>) offers a slower way to creep through lengthy clips or a long timeline. Dragging it left and right steps through a clip or the Timeline one frame per move. Below the jog bar you’ll find the transport controls. Within the Source Viewer they cover Jump to the First Frame, then Play Reverse, Stop, and Play Forward, plus Jump to the Last Frame. Within the Timeline Viewer the lineup shifts to move to the Previous Edit, then Play Reverse, Stop, and Play Forward, plus move to the Next Edit. Looping during playback is handled by a loop control.

### Simple Keyboard Shortcuts for Playback and Navigation

A whole assortment of keyboard shortcuts exists just for moving around clips and timelines and steering playback.

- Spacebar: The Spacebar both kicks off and halts playback.
- Skim Playhead: Footage can be skimmed in any viewer across the Media, Cut, Edit, Color, and Deliver

pages by keeping the C key down and dragging the pointer to and fro inside the viewer.

- Play Again: Hitting Option-L restarts playback at once from the playhead’s starting point without

a stop, handy when you want to quickly hear the opening of whatever you’re reviewing again.

- Step One Frame Forward/Step One Frame Back: A press of the Left Arrow or Right Arrow nudges the

playhead a single frame either direction, while Shift-Left Arrow and Shift-Right Arrow jump it in one-second steps.

- Step One Second Forward/Step One Second Reverse: A press of Shift-Left Arrow or Shift-Right Arrow moves the playhead one second backward or forward.
- Next Edit/Previous Edit: Up Arrow drops the playhead on the previous edit and selects that edit point, whereas Down Arrow drops it on the next edit and selects that edit point.
- First Frame/Last Frame of the Current Clip: The Semicolon key sends the playhead to the opening frame of whichever clip it crosses, while the Apostrophe key sends it to that clip’s closing frame.
- Previous Keyframe/Next Keyframe: When keyframes are shown in the Timeline, Shift-Semicolon hops the playhead to the prior keyframe on the left, and Shift-Apostrophe hops it to the next keyframe over on the right.
- Previous Marker/Next Marker: Where markers exist in the Timeline Ruler or inside Timeline clips, Shift-Up Arrow and Shift-Down Arrow carry the playhead left and right between consecutive markers.
- Previous Gap/Next Gap: When Timeline tracks with Auto Select enabled hold gaps between clips, Option-Command-Semicolon and Option-Command-Apostrophe walk the playhead left and right from gap to gap.
- Timeline Start/Timeline End: The Home key parks the playhead on the opening frame within the Source or Timeline Viewer, while the End key sends it to that viewer’s closing frame instead. Go to
- In Point/Go to Out Point: Shift-I jumps the playhead to the In point marked in either the Viewer or the Timeline. Shift-O jumps it to the Out point.

TIP: Within the Editing panel of the User Preferences window, the “Always highlight current clip in the media pool” option controls whether your current Timeline selection is echoed back in the Media Pool.

### Using JKL to Control Playback

Shared across countless editing programs, the JKL keyboard shortcuts rank among the handiest playback and editing controls seasoned editors rely on. What follows lays out the many ways these three keys let you run through clips and timelines while you work.

### J K L Press J repeatedly

### Press L repeatedly

### Shift-J Shift-L Shift-K Press and hold K+J

### Press and hold K+L

Holding K as you tap J Holding K as you tap L Command-J alongside Command-L

### Plays 100% backward

### Stops playback

### Plays 100% forward

Each additional press of J ramps the reverse speed up, giving you a spread of fast-reverse rates Each additional press of L ramps the forward speed up, giving you a spread of fast-forward rates Runs fast in reverse Runs forward at speed Play Slow at 1/2, 1/4 or 1/8 speeds Reverses in slow motion (audio plays back in slow motion too) Runs forward in slow motion (audio is pitch-corrected on macOS) Steps the playhead back by one frame Steps the playhead ahead by one frame Keeping Command held as you work the J and L shortcuts lets you dynamically stretch or trim the chosen edit points or clips at 100 percent speed or quicker, governed by whether the Selection or Trim tool is active. To learn more about dynamic trimming, consult Chapter 44, “Trimming.”

Whenever the JKL commands drive playback above or below real-time speed, a speed indicator shows up just right of the Viewer’s frames-per-second readout.

Above the Viewer, a speed indicator reports playback running at 4x speed Once all the various JKL playback techniques become second nature, they’ll likely turn into one of your primary means of driving the playhead around in DaVinci Resolve.

### Special-Purpose Playback Commands

Beyond the usual transport controls sit several extra playback commands — reachable through keyboard shortcuts or the Playback menu — that carry out different playback actions.

- Loop: Command-Forward Slash (/). Flips looped playback on or off. With looping active, anything you start using the commands below keeps repeating on its own until you halt playback.
- Play around selection: Forward Slash (/). The behavior of this command shifts with whatever is chosen in the Timeline. It plays a stretch of the Timeline reaching from x frames before to y frames after (a) the playhead (when nothing is chosen), (b) the chosen edit point, (c) the chosen clip, (d) the chosen transition, (e) a multi-clip selection. It’s handy for seeing how the current selection sits among the clips right around it. You can adjust the pre-roll and post-roll time in the Editing panel of the User Preferences.
- Play around current frame: Plays a stretch of the Timeline from x frames before to y frames after wherever the playhead now sits. It’s handy for seeing how edits sit among the clips right around them. You can adjust the pre-roll and post-roll time in the Editing panel of the User Preferences.
- Play around current clip: (no default key assigned). Plays a stretch of the Timeline from x frames before to y frames after the clip the playhead is currently crossing. You can adjust the pre-roll and post-roll time in the Editing panel of the User Preferences.
- Play Around In: Option-Space. Plays a stretch of the Timeline from x frames before to y frames after the In point now assigned, so you can preview the handoff from one clip to the next. You can adjust the pre-roll and post-roll time in the Editing panel of the User Preferences.
- Play Around Out: Shift-Space. Plays a stretch of the Timeline from x frames before to y frames after the Out point now assigned, so you can preview the handoff from one clip to the next. You can adjust the pre-roll and post-roll time in the Editing panel of the User Preferences.
- Play In to Out: Option-Forward Slash (/). When a portion of a clip or timeline carries In and Out points, this command previews how that portion will play.
- Play to In: (no default key assigned). Starts playback and halts at the current In point.
- Play to Out: Option-Command-Forward Slash (/). Starts playback and halts at the

current Out point.

### Custom Guides and Snapping in the Timeline Viewer

The timeline viewer lets you lay down guides of your own. With them you can pin down precise spots in the frame and then have the image snap to those spots during other work. There are Guides — colored lines running across the frame either horizontally or vertically — and Rulers, which lay out measurement marks along the frame’s edges. Guides and Rulers alike are overlay aids for tweaking your video’s placement, and they appear only inside the viewer, never in the finished project output.

### The Timeline Viewer with Guides and Rulers enabled

Each of Guides and Rulers can be displayed on its own by clicking its icon within the Ruler Guides section of the Timeline viewer’s Viewer Guides dropdown menu. They may likewise be switched on separately through the View > Rulers and View > Guides menus.

Within the Viewer Guides dropdown sits its Ruler Guides section To Show and Modify a Ruler: 1 Turn the Ruler on by selecting View > Rulers > On, or by clicking the Ruler Icon in the Viewer Guides dropdown of the Timeline Viewer. 2 Pick the metric the Ruler should use under View > Rulers, or by right-clicking the Ruler in the Viewer. Pixel: Renders the ruler as a pixel count from the origin point (0,0) at the frame’s center on a conventional x/y cartesian grid, mirroring the Position field found in the Video Inspector. Percentage: Renders the ruler as a percentage distance from the origin point (0%, 0%) at the frame’s top-left. The upper ruler spans 0% on the left to 100% on the right, and the side ruler reads 0% at the top down to 100% at the bottom. As an example, a point dead-center in the frame would land at (50%, 50%).

### The Add/Edit Guide dialog

To Show and Create a Guide Line: 1 Turn the Guides on by selecting View > Guides > On, or by clicking the Guides Icon in the Viewer Guides dropdown of the Timeline Viewer. 2 Add a fresh Guide via View > Guides > Add Guide, or by right-clicking the Ruler in the Viewer and choosing Add Guides. 3 within the Add Guide dialog, set the position and orientation you’d like for the new guide, then click Add. Units: Pick the metric the guide line should follow. Pixel reports how many pixels lie from the guide’s origin point, while Percentage reports the percentage distance from the frame’s top left at 0%,0%. Position: Type a value for where across the frame the guide line should sit. You can also drag this line in the viewer to place it by eye (a little popup will surface the exact position value while you drag). If you like, click the lock icon so the guide can’t be nudged by accident. Orientation: Set the line to run horizontally or vertically. Color: Pick the guide line’s color from the choices on offer. To Modify a Guide Line:

- Drag the line wherever you want inside the viewer; a small pop-up window surfaces to report the exact position value.
- For better legibility, recolor the Guide Lines by right-clicking in the Ruler and picking a new color from the Guide Color context menu.
- Remove a line by right-clicking it in the viewer and selecting Remove Guide.
- Adjust an existing line’s position and orientation by right-clicking it in the viewer and selecting Edit Guide.
- Clear all lines, only the horizontal ones, or only the vertical ones through View > Guides > and choosing which lines to drop. Right-clicking the ruler does the same.
- Pin Guides down against accidental movement by clicking the little lock icon at the ruler’s upper-left, or via View > Guides > Lock Guides.

A right-click on the Ruler brings up a context menu where you can tune every parameter of the Rulers and Guide lines

### Snapping to Guide Lines

Out of the box, as you reposition the clip in the frame with the Transform Viewer controls, the image edge will snap to a guideline the moment it draws near one, and the guide line turns purple to confirm exact placement. To switch this off, just keep the option key held while moving the image in the viewer and the snapping is skipped.

When the image edge snaps onto a spot, the Guide Lines there shift to purple.

### Optimized UI Layouts for Vertical Editing
