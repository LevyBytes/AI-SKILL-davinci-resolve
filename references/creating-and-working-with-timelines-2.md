# Creating And Working With Timelines (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Adding several tracks to the Timeline at a chosen position: Anywhere within the Timeline header, right-click and pick Add Tracks. Once the Add Tracks dialog opens, set how many video and audio tracks you'd like, pick whether the tracks go in above or below, and pick the Audio Track Type you want when audio tracks are part of the addition. After that, click “Add Tracks.”
- Removing a track from the Timeline: Inside a track's Timeline header, right-click and pick Delete Track. Should the track you take out hold any clips, those clips are removed from the Timeline along with it.
- Clearing every unused track out of the Timeline: Anywhere across the track header area, right-click and pick Delete Empty Tracks. Every track lacking clips is deleted in one go.
- Shifting tracks, plus the clips riding on them, upward and downward: Inside a track's Timeline header, right-click; from the contextual menu, pick either Move Track Up or Move Track Down. That track, together with all of its clips, moves up or down relative to the other tracks in the Timeline. Track order can also be rearranged from the Tracks Index. Just click the track in the # field and drag it to wherever you want it.

The Add Tracks Dialog makes it possible to insert several tracks in one step and position them within the timeline.

### Naming Timeline Tracks

For those who care about staying organized, the tracks on a timeline can be named to spell out their purpose. To rename a track: 1 Confirm the Timeline View Options are set to either Filmstrip view or Thumbnail view, and that audio tracks stand tall enough, so track names show. 2 When changing any track's name, select it by clicking the default “Video X” or “Audio X” track name, after which you type whatever name you prefer and press the Return key.

### Using the Tracks Index

The Tracks Index offers a straightforward track list that lets you view and manage every track header from a single spot. It also surfaces more audio detail than the Timeline's track header section does. The Tracks Index comes into its own when you're handling projects packed with video and audio tracks. You reach it by clicking the Index pane and picking the Tracks tab. The list that appears displays all the timeline's current tracks plus their position and attributes. Every one of these is adjustable right within the Track Index.

### The Tracks Index

### Tracks Index Columns

Each track exposes several columns of information. Those columns can be reordered by dragging the column headers left or right, according to whichever information matters most to you. A click on a track row selects that track for modification. A right-click on a track or tracks lets you delete them via the contextual menu. Using the Tracks Index for video tracks:

- Color: Displays a bar in the track's assigned color. Right-clicking the track lets you change its color.
- #: Displays the track's number.
- Name: Displays the track's name. You can edit this field.
- Track Controls: Surfaces the Lock plus the Enable/Disable Video track toggle. Every one of these controls is active.

Using the Tracks Index for audio tracks:

- Color: Displays a bar in the track's assigned color. Right-clicking the track lets you change its color.
- #: Displays the track's number.
- Name: Displays the track's name. You can edit this field.
- Track Controls: Surfaces the Lock Solo, and Mute controls. Every one of these controls is active.
- Format: Displays the audio track type. Right-clicking this field lets you change the audio track type.
- ADC: Displays how much Automatic Delay Compensation is currently on the track. A click on the checkbox switches the automatic delay compensation on or off.
- VCA: Displays the track's VCA group number.
- Tags: Displays whatever tags have been assigned to the track.

Using the Tracks Index for subtitle tracks:

- Color: Displays a bar in the track's assigned color. Right-clicking the track lets you change its color.
- #: Displays the track's number.
- Name: Displays the track's name. You can edit this field.
- Track Controls: Surfaces the Lock plus the Enable/Disable Subtitle toggle. Every one of these controls is active.

Using the Tracks Index options:

- To search for a specific track: Click the search icon (magnifying glass) and type in your search terms.
- Choosing which track types appear in the Tracks Index: Click the Option menu to decide which track types the list carries. The choices are: Video, Audio, and Subtitle.

### Toggle Track Header Control States by Clicking and Dragging

In the Edit page you can flip several Track Header controls at once (Lock Track, Visibility, Auto Track Selection, and so on) just by clicking an icon and dragging the pointer up or down across the track headers. This works for one control type at a time, and not across both Audio and Video tracks together.

Click the Lock icon at A1 and drag the pointer down as far as A3 to lock every audio track that falls between them

### Using Timeline Snapping and Zooming

As you get ready to make an edit into the Timeline, the snapping and zoom controls can be set to whatever state best suits the task at hand. Say you're cutting an insert shot into a fast-paced stretch of edits in the Timeline; you might want to zoom in so you can better see exactly where the incoming clip should land. With so many edits clustered there, turning snapping off can help keep the clip from leaping to the closest edit point when you need to nudge the incoming clip onto one precise frame. Playhead Snapping: Switching clip and playhead snapping on or off is done by clicking the Snapping button in the toolbar, or by pressing N. While snapping is on, the In and Out points and markers of clips snap to each other and to the playhead. You can also press N to briefly toggle snapping while dragging a clip in the Timeline, or while scrubbing the playhead with the pointer (snapping goes back to its earlier state once you finish the operation). Timeline Zoom presets:

Arranged left to right: the Full Extent, Detail, and Custom Zoom controls Full Extent Zoom: As clips get added or removed, this mode adjusts the zoom level on the fly so the entire Timeline stays in view. As your timeline expands with added clips, the zoom level drops automatically so the new clips fit inside your Timeline Viewer. The opposite happens too: the zoom level rises automatically as clips are removed. Detail Zoom: This setting zooms the Timeline in on the Playhead down to the frame level so you can quickly make fine timing adjustments. Custom Zoom: Zooms the Timeline to whatever level the Zoom Slider just to its right is set at. Zoom Slider: Pull the zoom slider toward the left for zooming out, toward the right for zooming in. Pressing Command-Minus (–) and Command-Equal (=) also handles zoom out and zoom in. No matter the method, zooming always stays centered on the playhead's present position, even with the playhead off screen. To fit every clip across the Timeline's width: Press Shift-Z. Being a toggle, a press of Shift-Z fits your whole edited sequence across the width of the Timeline, while another press of Shift-Z brings the Timeline back to whatever zoom level you had earlier. That keyboard shortcut makes moving around the Timeline simple while zoomed in, because you can hit Shift-Z, send the playhead to a different part of the Timeline you'd like to work on, and hit Shift-Z again to zoom straight into that fresh location in the Timeline.

### Zoom Around Mouse Pointer

You can configure the Edit Timeline zoom controls to remain centered on the pointer as you zoom in or out, rather than centering on the Timeline playhead as they normally do, by choosing View > Zoom Around Mouse Pointer. That can come in handy when you're navigating longer timelines. With this option on, zooming the Timeline in and out using your pointing device's scroll control while you hold the Option key keeps the Timeline centered on the pointer. Turn this option off to go back to zooming in or out centered on the playhead position only.

### Scrolling Through the Timeline

Once you're zoomed into the Timeline, several approaches let you scroll around as you work.

- Dragging the Timeline's horizontal and vertical scroll bars lets you move left and right, or up and down.
- Moving left and right through the Timeline one “page” at a step at the present zoom level is done by choosing Playback > Next/Previous > Timeline Page. Where you call on these often, assigning them a keyboard shortcut helps.
- Moving up and down the Timeline's tracks is also possible with the scroll wheel, scroll ball, or scroll gestures of whatever mouse, trackball, trackpad, or other pointing device you use.
- You can also scroll within the Timeline by middle-clicking and dragging any direction, which behaves the same as panning around a viewer you've zoomed into. That spares you from relying on the scroll bars as you move among your edited clips. Should you scroll past where the playhead sits, a small playhead indicator shows up in the bottom scroll bar to tell you where it is relative to the full length of your edited sequence.

Should the playhead fall beyond the Timeline's visible area, a small indicator marks where it sits.

### Scroll Wheel Controls on Timeline

Extra scroll wheel and key-press combinations let you manipulate the Timeline on the Edit page. To work the Timeline, spin the scroll wheel while holding down: Shift: Grows or shrinks all the Video or Audio track heights, depending on which section the pointer sits over as you scroll. Option: Zooms the Timeline view in and out. Command: Moves forward and backward through the Timeline.

### Move Playhead to Mouse Pointer Using the C key

On the Edit page, you can snap the playhead instantly to wherever your pointer rests on the timeline by pressing the “C” key on the keyboard. That lets you move around the timeline fast without having to steer the mouse up to click on the upper timeline ruler. A menu action works too: Playback > Go To > Mouse Pointer.

### Resizing the Timeline’s Video and Audio Track Regions

When you want to see more of the video or audio tracks within the Timeline's available area, drag the horizontal divider separating the audio and video tracks up or down so room opens where it's needed. Drag the Timeline's center divider to free up additional space for either audio or video tracks

### Tabbed and Stacked Timelines

The Timeline now offers the choice of having tabs that let you browse multiple timelines in a hurry. With tabbed timeline browsing on, a second option lets you bring up stacked timelines so two (or more) timelines appear at once, one above another.

### Tabbed Timelines

The Timeline View Options menu in the toolbar holds a button that switches on tabbed browsing and the stacking of timelines.

A button in the Timeline View Options enables tabbed timelines.

The first time you turn this on, a Timeline tab bar shows up above the Timeline, presenting a tab for the currently open timeline that holds a Close button and a Timeline drop-down menu. After Tab mode is on, opening another timeline from the Media Pool brings it up in a new tab. Beyond whatever tabs already exist, an Add Tab button lets you spin up more tabs, each one starting out at “Select Timeline.” Click any tab's drop-down menu to pick the timeline that tab shows.

Sitting above the Timeline Editor, tabs let you jump among several timelines fast Right-clicking a tab brings up a contextual menu that hands you several frequently used Timeline functions. Tabbed timeline contextual menu options: Close Timeline: Shuts the current tab's timeline and clears the tab. Same as clicking the “x” inside the tab. Close All Other Timelines: Shuts every open timeline and tab apart from the one on which you right-clicked and picked this option. Rename Timeline: Brings up the tab's text editing field so the name of the timeline inside the tab can be changed. That changes the timeline's name throughout the project in the Media Pool too. Find Timeline in Media Pool: Opens the bin where the timeline lives in the Media Pool and highlights the timeline in orange. Duplicate TImeline: Makes a duplicate of the chosen timeline in the same bin, with the word “copy” tacked onto the timeline name. It also opens the copied timeline in a new tab on its own.

A right-click on a tab surfaces the timeline options. Methods of working with tabbed timelines:

- Click any tab to switch to that timeline.
- Use the drop-down menu inside any tab to switch that tab over to a different timeline from the Media Pool. Every tab's drop-down menu lists all the project's timelines alphabetically, though a given timeline can only be open in one tab or stack at any moment.
- Drag any tab left or right to reorder the timeline tabs.
- Click any tab's Close button to close that timeline and take the tab away.
- Middle-click any tab to close that timeline and take the tab away.

### Stacked Timelines

While tabbed browsing is on, an Add Timeline button shows up at the far right of the tab bar, letting you stack two (or more) timelines one above another. That lets you keep two (or more) timelines open simultaneously, which makes editing clips from one timeline into another easy. A solid example of where this helps is when you've built a timeline that holds a stringout of selects drawn from one particular interview. Two Timeline Editors can be stacked, one over the other, with the Selects Timeline brought up on top and the Timeline you're cutting into placed on the bottom. With that layout, it's simple to play through the top timeline to spot clips you want, then drag and drop them into the bottom timeline to cut into your program.

### The button for closing a stacked timeline

Switching stacked timelines on or off: Click the Add Timeline button sitting at the right end of the Timeline tab bar.

### The button for adding a stacked timeline

After you've switched stacked timelines on, every timeline gets its own tab bar, and the selected one is flagged by an orange underline. Over at the right end of each tab bar, beside the Add Timeline button, sits a Close Timeline button that lets you close any timeline and lift that timeline browsing area off the stack.

### Stacked Timelines

### View and Edit Dual Timelines Using the Source Viewer

You can now operate on two timelines at the same time in the Edit page, with one loaded into the Source Viewer and one in the Timeline Viewer. This makes it easy to compare two timelines or shift content from one timeline to another.

Switch on Display Stacked Timelines within the Timeline View options before working with dual timelines To squeeze the most from this feature, begin by enabling Display Stacked Timelines through the Timeline View Options icon at the upper left of the timeline. With that view turned on, each timeline gets its own tab, and the Viewer redirects focus by itself according to which tab is active. Next, loading a timeline into the Source Viewer means right-clicking a clip's timeline over in the Media Pool and picking “Open in Timeline with Source Viewer.” That timeline shows up in the Source Viewer as a fresh tab, its name and playhead turning blue so you can keep straight which timeline lives in which Viewer. The timeline in the Source Viewer is read only. You move between the timelines by clicking the tabs, pressing Q, or clicking in the relevant Viewer.

A dual-timeline editing layout: one timeline loaded in the Source Viewer (blue) alongside a second one in the Timeline Viewer. Each tab switch hands focus to whichever viewer is relevant.

You can change which timeline shows up in the Source Viewer either by right-clicking a different timeline in the Media Pool and picking the “Open in Timeline with Source Viewer” option, or by picking one of the timelines from the dropdown menu atop the Source Viewer. Ordinary cut and copy moves carry content from the read-only source timeline into the actual timeline, and dragging out of the Source Timeline viewer (left) and into the Timeline viewer (right) also makes an edit. TIP: For playback purposes, a particular track in the Source Timeline Viewer timeline can be soloed. As one case, you might simply wish to hear the boom mix track, or a single specific ISO of a character's wireless mic, as you cut from the Source Timeline. Just click the “S” solo button on whichever audio track you want soloed. Shortcuts exist as well that make shifting focus between viewers that much faster:

- To toggle between the Source and Timeline viewers, press Q.
- To turn on and off the Source Timeline view, press Option-Q.
- To bring a particular timeline into the source viewer, right-click its tab and pick Load Timeline to Source Viewer.

TIP: You can likewise right-click an ordinary media clip and pick Open in Timeline with Source Viewer to bring that clip into the Viewer as a timeline. Such “timelines” will be read only, yet will still permit the same timeline-to-timeline editing operations available now. This mode comes in handy for very long clips such as interviews.

### Duplicate Frame Detection

For clips in the Timeline, Duplicate Frame Detection (often shortened to Dupe Detection) is switched on by choosing View > Show Duplicate Frames. That places colored bars atop Timeline clips anywhere a range of frames has been reused.

Wherever a frame range gets used more than once in a timeline, Duplicate Frame Detection marks it with colored bars.

### Comparing Timelines

For cases where you're bringing in several versions of a timeline edited in another application, or where you and other editors are working on different versions of the same Timeline in collaborative mode or across separate DaVinci Resolve installations, DaVinci Resolve gives you a way to compare two timelines against each other. Through the Timeline Comparison window, you can both see a visual comparison of where two timelines diverge and assemble a more traditional change list by opening the Difference Index. To set two timelines side by side: 1 Bring up the first of the timelines you mean to compare. 2 Over in the Media Pool, right-click a second timeline and pick Compare With Current Timeline. Up comes a Timeline Comparison window, laying the currently open Timeline across the bottom and the Timeline you right-clicked across the top.

### The Timeline Comparison Window

The first time you open the Timeline Comparison window, the first thing in front of you is a pair of miniature timelines. The currently open Timeline sits at the bottom while the Timeline you right-clicked sits at the top.

### The Timeline Comparison window

### Comparison Window Playhead Output

Out of the box, the two playheads are ganged together, the top playhead appearing in the Source Viewer and the bottom playhead appearing in the Timeline Viewer. You can ungang these playheads to compare different parts of both timelines, simply by switching off Sync Playheads in the option menu.

### Highlighting Differences

Special highlights point out the sections of both timelines that differ. Individual changes aren't highlighted one by one, though they remain visible, on the assumption that you care more about a section-by-section read of what your collaborating editor has been up to, so you can decide whether to fold in changes or reversions based on this comparison.

Each section of differences between the two timelines are highlighted While using this tool, you can bring the bottom Timeline in line with the top Timeline, one section at a time: right-click a highlighted section, then pick Accept Change off the contextual menu. The moment you do, the currently open Timeline updates straight away to fold in the altered section from the Timeline you're comparing against. You can undo this if you have to.

### The Change List

Clicking the Diff Index button opens the change list, which gives you a more conventional item-by-item comparison of where the two timelines differ.

### The change list of the Timeline Comparison window
