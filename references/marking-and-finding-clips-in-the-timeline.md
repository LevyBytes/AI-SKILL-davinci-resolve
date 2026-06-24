# Marking And Finding Clips In The Timeline (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Marking and Finding Clips in the Timeline

As your project moves along, it helps to flag key details about each clip, along with notable moments in each timeline, by combining Flags, Markers, and clip Label colors. You can attach these to source clips sitting in the Media Pool, or to clips already cut into timelines. Markers in particular can also go onto the Timeline ruler itself, which helps you track important moments or notes and assists with snapping. Along the way you’ll also be reshaping clips in assorted ways — unlinking and relinking the audio and video of various clips, and switching clips on and off in the timeline.

### Using Flags

A Flag tags a clip in its entirety, and it simultaneously flags every other clip in the Timeline drawing on the same Media Pool source clip, which makes it a convenient way to spot at a glance which clips in a given timeline trace back to one Media Pool source.

The Flag and Marker buttons and pop-ups. Clips can carry several flags at once, drawn from an assortment of colors. Beyond tagging particular media files, flags prove handy for timeline filtering on the Color page, column sorting in the Media Pool, and plenty of other operations. Ways to flag clips:

- To flag a clip from the toolbar: Pick one clip or several, then either click the Flag button to tag that clip with the active color, or open the Flag drop-down in the toolbar to pick another color before clicking the Flag button. On the Edit page, flags show up in the Timeline laid over the name bar of every clip.
- To flag a clip: Pick one clip or several, then choose Mark > Add Flag > Current Selected (G) to drop markers of a given color straight onto clips and the Timeline. You can map the individual flag color commands to specific keyboard shortcuts if you’d like to drop a particular flag color with a single keystroke.
- To flag a clip from within the Source Viewer: Bring a clip up in the Source Viewer; then, while focus rests on the Source Viewer, choose Mark > Add Flag > Current Selected (G). Each individual flag color command can be bound to its own keyboard shortcut if you want a given flag color available at a keystroke.
- To clear every flag off a clip: Pick the clip or clips whose flags you want gone, open the Flag drop-down in the toolbar, then choose the topmost “Clear All” option.
- To reveal or conceal one color of flags: From the View > Show Flags submenu, pick whichever flag color you’d like hidden; to bring every color back, choose View > Show Flags > All instead.
- To filter all flagged clips in the Edit Index: Open the Option menu of the Edit Index and choose Show Flags. Every flagged clip turns up in a list, with one column displaying the color(s) of the flags on each entry in that list.

### Using Markers

Markers serve to draw the eye to a single frame inside a particular clip. Each marker can take its own color and carry custom name and note text. Anytime you type text into a marker, that marker shows a small dot signaling that more information sits inside it. After placement, and provided snapping is turned on, a marker snaps onto In and Out points, onto edit points, onto the playhead, and onto fellow markers, which makes it simple to lean on markers to “measure” the edits and trims you perform in the Timeline.

### Adding Markers to Clips

You can drop markers along the jog bar belonging to source clips shown in the Source Viewer (or the Media page Viewer), and likewise onto clips you’ve selected inside a timeline.

Markers placed on a source clip

(Top) Markers set on a source clip; below them, markers set on a clip within the Timeline. Once you add markers to a source clip, those markers surface in the Media Pool too, as hierarchically disclosable items hanging off that clip in List view (Thumbnail view doesn’t show markers). Further detail on working with markers in the Media Pool’s List view comes later in this chapter.

When the Media Pool sits in List view, markers can be seen as separate clips, each identified by its marker name.

The steps that follow lay out how markers get added onto clips, and onto timelines, within DaVinci Resolve. When marking a source clip, whether in the Source Viewer or the Media Page Viewer, do one of these:

- To set a marker and nothing more, bring the playhead to the frame you want to mark, then press M.
- To set a marker and open the marker dialog straightaway during playback so you can type a name or note in it, press Command-M (or press M twice). Playback halts until you’ve entered the text you want and closed the marker dialog, whereupon playback resumes.
- Position the playhead over the frame you mean to mark; from there, right-click within the jog bar and pick a marker color out of the Add Marker submenu of the contextual menu.

To mark a clip in the Timeline, do one of the following:

- Pick the clip or clips you mean to mark, bring the playhead to the frame of a selected clip in the Timeline, then click the Marker button in the toolbar (or press M) to drop a marker at that frame in the active color (when several overlapping clips are selected, the marker lands on every one of them).
- To set a marker mid-playback and pop open the marker dialog right away for a name or note, pick the clip or clips you mean to mark, run playback through the selection until you reach the spot to mark, then press Command-M (or press M twice). Playback stops until you type some text and close the marker dialog, after which playback carries on.
- Pick the clip or clips you mean to mark, then open the Marker drop-down to pick another color, and click the Marker button.

In the Timeline, markers show up at the top of the title bar of whichever clip carries them.

### Adding Markers to Timelines

Markers of any color can likewise be dropped into the Timeline ruler to flag particular times for later reference, or to jot notes about issues you want to follow.

### Timeline markers placed for future reference

Keep in mind that every marker you set on clips or in the Timeline also turns up inside the Mini-Timeline of the Color page, which makes leaving notes for later reference while grading straightforward.

Clip and Timeline markers, here shown within the Color page’s Mini-Timeline. After one or more markers are set on clips, and as long as snapping is on, they snap onto clip In and Out points, onto edit points, onto the playhead, and onto fellow markers. To mark the Timeline itself, first confirm all clips are deselected, then do one of these:

- Press M.
- Click the Marker button to drop a marker in the active color into the Timeline ruler.
- To set a marker mid-playback and immediately open the marker dialog for a name or note, pick the clip or clips you mean to mark, then press Command-M (or press M twice). Playback halts until you type some text and close the marker dialog, after which playback carries on.
- Open the Marker drop-down to pick another color, then click the Marker button.
- Right-click in the Timeline ruler and pick a marker color from the Add Marker submenu of the contextual menu.
- Choose Mark > Add Marker > Current Color (M) to apply the active marker color. As an alternative, choose Mark > Add Marker > Blue/Cyan/Green/and so on to drop a marker of a particular color straight onto clips or the Timeline. Each of these commands can be tied to a specific keyboard shortcut if you’d like a given marker color available at a keystroke.

### Individually mappable marker color commands

### Saving In and Out Point Ranges As Markers with Duration

You can also build markers with duration to keep tabs on any stretch of a clip or timeline you’ve bounded with In and Out points. This gives you a way to flag several stretches of a clip you might later cut into a program. To turn a pair of In and Out points into a duration marker: 1 On the Source Viewer jog bar, set In and Out points to mark out a region you’d like to log for later reference.

Setting In and Out points so as to log that portion of the clip. 2 Then do one of these:

- Right-click the jog bar and pick Convert In and Out to Duration Marker
- A marker with duration shows up above the In and Out points. Want to revise its name or notes? Double-click the marker, hit Shift-M, or else choose Mark > Modify Marker.

A marker with duration is created from the In and Out points. By this means you can log several stretches within one clip for later use.

A clip with multiple logged sections identified via markers with duration. This logging technique earns its keep for a couple of reasons. For one, you can search markers with duration in the Media Pool through the All Fields, Marker Name, and Marker Notes Filter by options. For another, Smart Bins can filter them via the Marker Name and Marker Notes Media Pool Properties options.

### Editing Marker Information and Keywords

After you’ve set a few markers, you may want to revise their contents to make them more useful. To bring up a marker’s edit dialog and change its properties: 1 Do one of these:

- Press Command-M to set a marker during playback and open its edit dialog at once.
- Double-click whichever marker you want to edit.
- Bring the playhead to the frame holding the marker you want to annotate using Shift-Up

Arrow/Down Arrow, then press M.

- Select a marker anywhere in the Source Viewer or Timeline, then press Shift-M.

2 With the marker dialog open, you can change several properties across separate fields. For quick editing, press Tab to jump to the next field, or Shift-Tab to jump to the previous one.

### Editable properties in the Marker dialog

Time: The frame at which the marker sits relative to that clip or timeline. It’s editable, letting you reposition a marker numerically. Duration: Optional; the length of a marker that’s carrying a duration. This too is editable, so you can hand a marker a duration numerically, or adjust one that already has duration. Name: The marker’s name; by default this reflects where the marker fell in the sequence of additions (Marker 1, Marker 2, etc.). Notes: A field for typing whatever information you want to track. Color: A row of buttons for picking the marker’s color. Keyword: A keyword field that lets you keyword markers the same way you keyword clips in the Metadata Editor, which can be a potent means of flagging clip sections you’ll want to locate later in Smart Bins or Search operations. As you type into the Keyword field, it searches the dictionary for matching keywords on its own. Press Return to take a found keyword (the Arrow keys let you pick from a list), or press the Up Arrow key back up to the Keyword field to type your own fresh variation by hand instead. For more on working with and editing Keywords, see Chapter 16, “Using Variables and Keywords.” Remove Marker: Wipes out that marker. Done: Shuts the marker edit dialog. 3 Once you’re done, click Done. After you add notes to a marker, a small symbol appears over that marker to indicate it holds information.

A small dot on a marker is the sign that it holds notes.

### Changing Marker Timing

After you’ve set one or more markers, several routes let you shift them around to better align with key events in source footage or the Timeline, or remove them once they’ve outlived their use. On top of that, you can switch on or off whether markers ripple alongside other clips in parts of the Timeline touched by rippling operations. To shift one or more markers in the Timeline or Source Viewer:

- Click one marker, or Command-click several markers you want to shift, and drag them somewhere new.
- Drag a bounding box up from the Timeline into the Timeline ruler to grab several markers, then drag them somewhere new.
- Open a marker’s edit dialog and edit the time and duration timecode fields by hand to move that marker numerically, or to build a marker of a particular duration. Beyond that, the timecode in these fields can be copied out of or pasted into.

To enable marker rippling:

- Choose Timeline > Ripple Timeline Markers. With it checked, every marker sitting to the right of a clip that’s being ripple edited, trimmed, or ripple deleted ripples leftward together with the rest of the Timeline. This behavior is yours to switch on and off whenever you like.

### A marker with duration in the Timeline

To modify marker duration:

- Option-drag any marker rightward or leftward to turn it into a marker with duration.
- Bring the playhead to the frame holding the marker you want to change and press M, or double-click the marker you mean to edit, then enter a number in the duration field and click Done.
- A marker with duration shows up as a bar in the Timeline ruler or on the Source Viewer’s jog bar. Drag the middle of such a marker to shift it, or drag its left or right edge to resize its duration.
- To strip a marker of its duration, open the marker dialog and key its numeric duration down to 00:00:00:00, or else drag one end until it meets the other as a single marker.

Ways to delete markers:

- To remove one or more markers with the mouse: Click to select a marker, or Command-click to select several; then press the Delete key. Another route is to double-click a marker, which opens its dialog, and from there click the Delete button.
- To remove a marker with the keyboard: Bring the playhead to the marker you want gone and press Option-M.
- To clear every marker off a clip: Pick the clip or clips whose markers you want removed, then either press the Backspace key or open the Marker drop-down in the Toolbar and choose Clear All.
- To clear every marker out of the Timeline: First deselect all clips. Then either choose Clear All out of the marker drop-down menu sitting in the Toolbar, or instead right-click the Timeline ruler and, from the contextual menu, choose Remove All Markers.

### Copy and Paste Multiple Markers in the Viewers and Timeline

On the Edit page, you can grab several markers at once by Shift- or Command-Clicking them, or by dragging a boundary box around them. With them selected, pressing Command-C copies these markers to the clipboard. From there, pressing Command-V pastes them all into another clip, timeline, or compound clip at the playhead position. When a timeline clip is selected for Paste, DaVinci Resolve lays clip markers onto the clip. With nothing selected, DaVinci Resolve produces timeline markers instead. This comes in handy for keeping essential marker information easy to share across various iterations of media and across timelines. You can run the copy and paste operations in either the Source and Timeline Viewers, or in the Timeline itself.

### Marker Notes in Data Burn-Ins

Marker notes can be surfaced through Data Burn-Ins. Here’s how: 1 Build a Marker, then drop a word or two into its Notes section. 2 Head to Workspace > Data Burn-In. 3 Tick one of the Custom Text options. 4 In the field that appears, type the “%” sign, then begin spelling out the word “marker.” 5 Pick Marker Notes from the list. 6 Tune the font/position/opacity parameters as needed. From now on, whatever text you place in the Marker Notes section displays as a Data Burn-In. Should you want the notes to persist beyond one frame, be sure to switch the marker to a duration marker instead.

The marker note “Stock Footage” now appears as a Burn-In, by way of the % metadata tags in a Custom Text field.

### Drawn Annotations on the Viewer

These days the Timeline Viewer’s Annotations mode lets you sketch arrows, plus strokes of varying weights and colors, right on the video frame, so as to point out or highlight things needing a fix. Markers hold these annotations, much as they hold marker names and notes. To begin, just pick Annotations mode from the Timeline Viewer mode drop-down menu.

Choosing Annotations from the Viewer Mode drop-down menu. Once you’re in Annotations mode, an Annotations toolbar shows up presenting these options. Draw tool with line weight drop-down: hitting the Draw tool lets you freeform draw on the Viewer; the Line Weight drop-down beside it offers three line weights to pick among for drawing. Arrow tool: hitting the Arrow tool produces straight-line arrows that point at features you want to spotlight. Whatever weight you’ve set for the Line tool, arrows always emerge at one fixed weight. Line Tool: hitting the Line tool produces straight lines on the Viewer. Rectangle Tool: hitting the Rectangle tool produces boxes on the Viewer. Color drop-down: here you settle on a color for your drawing or lines. Ways to make and edit annotations:

- To make an annotation: Just switch Annotations mode on, rest the playhead on whatever Timeline frame you like, and begin drawing. At that frame, a marker is added to the Timeline automatically, and that marker holds the annotation data. Should the playhead sit over a marker that’s already in the timeline, the annotations attach to that marker.
- To edit a stroke or arrow you’ve drawn already: Move the pointer onto a stroke or arrow, click to select it, then pick a fresh line weight or color from the matching drop-down menu, or drag that stroke or arrow elsewhere to reposition it.
- To delete a stroke or arrow: Move the pointer onto a stroke or arrow, click to select it, then press the Delete or Backspace keys.

### Drawing annotations to highlight feedback

### Reading Marker Information

After you’ve set a number of markers carrying custom information, you have two ways to review that information short of opening the marker dialog. To read marker notes with your pointer:

- Double-click a marker to bring up its marker dialog.
- Hover the pointer over any marker in the Source Viewer or Timeline to surface a tooltip carrying that marker’s information.

Hovering the pointer over a marker brings its information up in a tooltip. To read marker information directly inside the Source and/or Timeline viewers: 1 From the option menu of the Source or Timeline Viewer, switch on Show Marker Overlays. 2 Halt playback and bring the playhead to a marker. That marker’s information then appears superimposed in the Viewer.

### Marker information shown in the Source Viewer

### Using Markers for Navigation

Markers can assist with navigation through two keyboard shortcuts that hop the playhead from one marker to the next. As the playhead travels among markers, Clip and Timeline markers get treated as one combined set. To send the playhead to the next or previous marker:

- Press Shift-Up Arrow to send the playhead to the next marker to the left in the Timeline.
- Press Shift-Down Arrow to send the playhead to the next marker to the right in the Timeline. Whichever marker the playhead lands on is then selected automatically.

To send the playhead to a particular marker via the Source or Timeline Viewer’s Marker list:

- On a source clip or timeline holding several markers, you can jump the playhead straight to a particular marker by opening the Source or Timeline Viewer’s Option menu and picking a marker from the Markers submenu, which lays out every marker on offer in that Viewer, by name and note.

Every marker belonging to the clip you have open, shown via the Markers list in the Source Viewer Option menu.

### Using Timeline Markers for Chapters

A handful of file types, QuickTime among them, support chapter-based navigation in the finished video. That lets a viewer jump back and forth through the video, landing on precise points the video’s creator laid out. Such chapter-based navigation pays off especially in instructional videos or lengthy presentations. In DaVinci Resolve, timeline markers define the chapter points. For now, only the QuickTime and MP4 formats handle chapter markers in DaVinci Resolve. To build a chapter marker in the Timeline:

- Park the playhead at the spot in the Timeline where you want a chapter point, then choose Add Marker (M).
- Edit the marker by double-clicking it, or by picking Modify Marker (Command-M).
- Edit the Name field to set the chapter name that will appear in the player.
- Pick a color for the marker. Every chapter marker has to share the same color.

To export embedded chapter markers in a QuickTime movie:

- On the Deliver page, set Quicktime or MP4 as the Format in the Video Panel.
- Tick the box beside Chapters from Markers, then pick the chapter marker color you settled on earlier from the drop-down menu.

Within the Deliver page, the QuickTime Export Video settings hold the Chapters from Markers checkbox.

### Using Markers in the Marker Index

The Marker Index gives you a single handy spot to view, edit, and organize all your timeline and clip markers. You reach the Marker Index by clicking the Index panel and selecting the Markers tab. Ways to work with markers in the Marker Index:

- To filter markers in the Marker Index: From within the Marker Index, open the Option menu; pick Show All there, or pick Show Only to settle on a particular color. Every clip carrying a matching marker turns up in a list, where the columns map across to each timeline and clip marker’s color(s), information, and notes. Clicking a column header sorts the columns in ascending or descending order. You can switch individual columns on or off by right-clicking the column header and ticking or unticking the column name.
- To send the playhead to where a marker sits via the Marker Index: In the list, double-click that marker’s entry.
- To edit marker information: You can revise a marker’s values by clicking into the Name, Notes, or Keyword fields and changing the text. The Marker Index won’t let you edit the other values; change those in the timeline marker’s Edit dialog.
- To hunt for a particular marker: Click the search icon (magnifying glass) and type your search terms. The search pulls results from every field in the Markers window, the Name, Notes, and Keywords fields included.
- To flip between Thumbnail and List view: Up in the Marker Index’s top bar, click whichever you want of the Thumbnail or List View icons.

The Marker Index in List View mode gives you one place to edit and organize all your timeline’s markers.

### Exposing Markers in Lists

The Edit Index, too, can sift out a list of the markers that fall within the current Timeline. You can filter every marker at once, in which case columns reveal the notes and colors on each marker. You can instead filter by a particular marker color when you only care to see one kind of marker. Ways to work with markers in the Edit Index:

- To filter all marker-bearing clips through the Edit Index: Within the Edit Index, click the Markers tab; from the Option menu, then choose Show All or single out a particular color. Every clip carrying a matching marker turns up in a list, where the columns map across to each Timeline and Clip marker’s color(s) and notes.
- To send the playhead to a marker’s position in the Edit Index: Click that marker’s entry in the list.
- To reveal hidden marker columns: Right-click any column header and switch on any of the selections to surface that column. Where needed, you can reorder columns by dragging them left or right.

You can also export marker lists as an EDL, a .txt, or a .csv file. Exporting marker lists:

- To export Timeline markers as an EDL: In the Media Pool, right-click that timeline; from the menu, choose Timelines > Export > Timeline Markers to EDL. The Export Edit Index dialog then lets you pick a location and an export format, after which you click Save. Every Timeline marker shows up in the resulting EDL, any notes riding along plus a duration where applicable.
- To send every filtered Edit Index marker out as a .txt or .csv file: Having already chosen Show Markers in the Edit Index option menu, reopen that Option menu and choose Export Edit Index. The Export Edit Index dialog then lets you pick a location and an export format, after which you click Save.

### Using Markers in the Media Pool

Having attached markers, one or several, onto source clips sitting in the Media Pool, you can put them to work in editing far more directly than merely shuttling the playhead about with them. The Media Pool’s List view can surface markers; once surfaced, each one opens into the Source Viewer, edits into the Media Pool, or becomes a subclip just like any other clip. To surface markers within the Media Pool:
