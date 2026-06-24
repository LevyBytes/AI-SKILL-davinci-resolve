# System And User Preferences (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Use custom safe area overlays: Switching this on surfaces Action Area and Title Area fields where you set your own percentage for each. Their defaults stand at 93% for Action Area and 90% for Title Area.
- Retain sync and avoid overwrites with ripple edits: Tick this box and DaVinci Resolve tries to hold sync during ripple trimming whenever that means overwriting media on certain tracks. Leave it unticked and no media gets overwritten, but ripple trimming will throw clips out of sync.
- Align audio edits to frame boundaries: With this on, the In and Out points of audio clips always snap to whole frame boundaries, exactly as video clips do. With it off, you’re free to make subframe audio edits on audio-only clips, or on linked audio once you’ve suspended linked selection.
- Configure clips as multi-mono on import: Ticking this box lets you bring in any multichannel audio laid out as multiple mono. Any Stereo, 5.1, or other multichannel source then gets set up automatically as multiple mono files carrying the same track count the moment you drop it into the Media Pool.
- Limit Media Pool audio sync to first timecode match: Where a video clip shares timecode overlap with two or more audio clips, the usual behavior syncs every overlapping audio clip by spawning as many fresh tracks as required. Tick this box and that gives way to DaVinci Resolve picking the single audio track it judges most likely and syncing only that one clip, while the rest are left alone.
- Import Finder tags as Keywords (Mac only): With this on, whatever color tags Mac OS has assigned to a media file come in automatically as keyword metadata riding alongside that file.

NOTE: Even with Align audio edits to frame boundaries switched off, having linked selection on stops you from making subframe edits while you resize both the audio and video of linked clips at once.

### Text

Tick the Display Only Specific Fonts box to deliberately pare down the font choices offered for your text elements. That builds a white list of fonts you’re approved to use and tucks every other system font out of sight. To assemble an allowed fonts list: 1 Tick the box at Preferences > User > Editing > Text > Display Only Specific Fonts. 2 Pick a font filter file. Such a file is any UTF-8 text document that blends explicit font names with entries using asterisk wildcards to catch several fonts, listed one per line. _Gothic_ (matches any font name containing Gothic) Arial Helvetica\* (matches any font name that starts with Helvetica) Open Sans Default Fades The curves of Fairlight’s default audio fades are laid out by these settings.

- Fade In/Out: Lay out the curve type used for fade ins and outs.
- Crossfades: Lay out the curve type used for the ins and outs of the crossfade.

Checkboxes for None, Equal Power, and Equal Gain for crossfade type.

### Color

This panel’s settings steer various behaviors over on the Color page.

### General Settings

Shape an assortment of behaviors as you work on the Color page.

- Master reset maintains RGB balance: Sets how the DaVinci control panel’s trackball/ring reset buttons clear primary color adjustments. With this option off (its default), a press of the ALL Reset button brings the primary correction values back to their defaults. Switch the checkbox on and a press of the ALL Reset button (a) clears the YRGB values such that the overall levels stay put and the YRGB-to-each-other ratio holds, while (b) a press of the RGB Reset button drops the three color channels to the average of their former settings.
- Wipe wraps when viewing reference stills: Switching this on (its default) lets stills carry over the screen edge as you drag the wipe with the mouse, instead of halting at that edge. Should the behavior feel clumsy when you’re trying to whip up full-frame still comparisons to toggle on and off, you can turn it off.
- High-Visibility Power Window Outlines: Switching this on draws Power Window outlines in green (the center shape) and yellow (the softness shapes) so the windows read more easily in certain situations, in place of the default white and gray.
- Mattes display high contrast black and white: When this is on, the HILITE command — which shows the current key — renders a black and white matte (that is, high contrast) rather than the usual gray one.

For more on this setting and on working with the HILITE command, see Chapter 135, “ColorSlice.”

- Next scene switches to visible track: While grading a multi-track project, this option reshapes the “next scene” command so it behaves better where multi-clip composites are involved. With it off, pressing NEXT SCENE on the DaVinci control panel, or hitting the Down Arrow shortcut, carries the playhead to the very next clip in the Thumbnail timeline whether that clip sits ahead of or behind another. Switch it on and the NEXT SCENE command instead lands the playhead on the clip in the topmost track whenever the next clip belongs to a multi-clip composite of clips piled over one another.
- Previous or Next node navigates only to correctors: Node navigation picks out corrector nodes alone, stepping past mixer, splitter, combiner nodes, and the like.
- Preserve node numbers when adding nodes: Tick this box and node numbering rises in the order nodes were made, no matter where each sits in the node tree. Leave it unticked and the numbering reflows on its own according to each node’s spot in the tree.
- Always perform copy and paste on selected nodes: Sidesteps the interface focus-driven choice between copying and pasting full grades versus single nodes. When ticked, DaVinci Resolve copies and pastes only among selected nodes, whatever the interface focus happens to be.
- Use Legacy Auto Color: Since DaVinci Resolve 16, two tools — the Color Wheels palette’s A button together with the Shot Match command found in the Thumbnail Timeline contextual menu — both lean on advanced algorithms built on the DaVinci Neural Engine, yielding better outcomes when color balance and contrast are adjusted automatically. This checkbox points the A button back at the older algorithm.
- Use Legacy Shot Match: Beginning with DaVinci Resolve 16, the Shot Match command in the Thumbnail Timeline contextual menu draws on an advanced algorithm built on the DaVinci Neural Engine, yielding better outcomes when color balance and contrast are adjusted automatically. This checkbox points the Shot Match command back at the older algorithm.
- Histogram Background on Grading Tools: Through this drop-down menu you set the histogram shown behind the Curves palette to Off, to On based on the node’s Input (where curve edits leave the background histogram untouched), or to On based on the node’s Output (where curve edits do reshape the background histogram).
- Automatically cue x frames into timeline clips: This setting bears on how the Color page’s NEXT SCENE and PREV SCENE commands behave. By default, moving from one clip to the next cues on each clip’s first frame. Type a value here, in frames, and the default cue point shifts to that many frames past the first frame of every clip the playhead lands on. It comes in handy when the source carries black or camera rollup flashes at the head of each clip while you grade dailies.
- Neighboring Clips in Split Screen: Lets you set how many clips adjacent to the current ones appear in a grid within the Color page Viewer once you switch on the Neighbor Clips option of the Split-Screen shot comparison control.
- Switching clips: (this setting is also changeable from the Node Editor’s Option menu) On switching clips, DaVinci Resolve can move to the same node or a different one in the node graph. The four options below decide which node ends up selected:

Selects last adjusted node: The default, under which every Timeline clip keeps its own separate node selection that’s recalled each time you return to that clip. Selects first node: The first node is always chosen as you move to a different clip. Selects last node: The last node is always chosen as you move to a different clip. Selects same node: Should the clip you’ve jumped to hold as many nodes as the previous clip or more, the node bearing the matching number is chosen. Should it hold fewer nodes than the previous clip, the next highest node is chosen.

- Color picker: Alters how colors get chosen while you use the Secondary color correction controls. DaVinci Resolve is the standard, current mode, though some colorists at home with the legacy 2K lean toward the DaVinci 2K mode.

### Ripple Mode

This setting fixes how the Ripple command launched from the Color page behaves.

- Target clips are set to: The Ripple mode applied when you trigger a Ripple command on the Color page, whether through the RIPPLE button on the Advanced Panel or by choosing it from the Color menu.

For more on putting this function to use, see Chapter 142, “Grade Management.” Exact values changed: Edits to the current clip ripple out to the named clips using the very parameters you altered. Say the current clip’s Master Gain level is moved to 0.75 of its range — then every clip you ripple ends up with a Master Gain level of 0.75. Only the parameters you touch ripple. Percent value changed: Edits to the current clip ripple out to the named clips by the percentage shift you applied to the altered parameters. If, for instance, the current clip’s Master Gain level sits at 1.00 and you drop it to 0.90 units, the Master Gain level of each rippled clip falls 10% relative to its earlier value. Unit values changed: Edits to the current clip ripple out to the named clips by the same change delta, in whatever units suit the affected parameter. For example, if the current clip’s Master Gain ran 0.80 and you raised it to 0.90, each rippled scene’s Master Gain level climbs by 0.10. All values are copied: The current clip’s grade ripples to the named clips in full. No check is made against the original clip’s parameters, and every memory parameter ripples.

### Printer Light Step Calibration

On film projects where you’re closely tied to a film lab, the printer light calibration sets can be tuned to suit the lab you work with. Partner with your lab technician to dial in the Lab Aim settings, the Steps adjustments — an incremental value — and the Density Increment adjustment, which is how much correction each step applies. The Step and Density values usually match, but that rests with your lab and what you prefer.

### Fairlight

### Video I/O Offset

This section’s two preferences let you push overall video playback as much as 7 frames ahead of your audio playback, covering cases where image processing on your video output introduces delays that knock the video out of step with the audio. Picture your video output passing through a converter that tacks on a 1 frame delay and then reaching a projector that adds another 1 frame. Setting your Video Monitor Offset to 2 frames cancels that out and keeps audio/video sync rock solid.

- Video Monitor Offset: From this drop-down menu, pick an offset anywhere from 0 to 7 frames.
- Apply Offset during Jog and Shuttle: Switch this checkbox on and the offset you

picked applies as well when you use Jog and Shuttle to travel through your program.

### General Settings

Both preferences in the General Settings section let you shape the Loop Jog behavior, which for now lives only on the Fairlight page. Picking Timeline > Loop Jog makes a short sample preview audible as you scrub the playhead along the Timeline. That can ease the job of catching snippets of dialog or music while you quickly scrub through tracks hunting for particular lines or music cues. It likewise lets that short sample preview loop without end when you park the playhead on a frame, so you can pause mid-scrub and hear (by default) the 80 ms just before the playhead cycling around. Two settings let you tailor how this works.

- Loop Jog Alignment: Three choices decide whether your audio loops Pre the playhead position, Centered on the playhead, or Post the playhead position.
- Loop Jog Width: A field lets you set how many milliseconds of audio loop while Loop Jog is on. How many milliseconds map to a single frame hinges on the video’s frame rate. At 25 fps, for instance, you get 1000/25 = 40 ms per frame, so the 80 ms default works out to two frames of looping.
- Enable auto patching: Tick this box and the first of your system audio inputs routes to whichever track has “arm for record” active.
- Mixer follows selected track: Tick this box and the selected track shows up focused and farthest left in the Mixer pane.
- Include mixer events in Undo history: Tick this box and you’ll be able to undo mixer events (changes to panning or to a track’s mute state, say).

### Automation

The Automation section’s two preferences let you set the Glide Time between Automation events and decide whether Automation events ride along when you recall a preset or copy and paste.

- Glide Time: Type a millisecond value to set the Glide Time used for automation.
- Write on Preset or Clipboard Paste: Tick this box and Automation events get

written to the track as you recall a track preset or copy and paste. Bear in mind that with it on, what actually gets written still depends on which master automation is switched on or off. Disable plugin automation, for example, and no plugin automation will be written.

### Playback Settings

These preferences help you lift realtime performance in DaVinci Resolve by switching off particular UI features and tuning the quality of certain operations.

- Hide UI overlays: If a lone GPU is handling both display and CUDA, OpenCL, or Metal processing, or your display GPU is weak, or you’re short on the PCIe bandwidth the current resolution or frame rate demands, switching this option on may bump up real time performance. With it on, onscreen controls — the cursor, Power Window outlines, split-screen views — are switched off and hidden during playback. Pause playback and every onscreen control comes back.
- Minimize interface updates during playback: With this on, real time performance takes precedence during playback as user-interface updates are pared back. It helps when you’re building elaborate grades on low-powered systems or working on high-resolution projects.
- Performance Mode Automatic/Manual: A set of three radio buttons lets you pick Automatic (the default) or Manual (user-selectable) behavior when you switch Performance Mode on in DaVinci Resolve, or turn Performance Mode Off entirely. Under Automatic, Performance mode tunes a range of operations on its own to weigh speed against the image quality you need, keeping onscreen performance brisk while always holding video output at top quality. Under Manual, three separate settings can be switched off for those moments when a given performance tradeoff Resolve makes brings an unwelcome, obvious drop in image quality within Performance Mode:

Optimized Sizing: Concerns how image resizing gets handled. Optimized Decode Quality: Concerns how clip resolution against timeline resolution gets handled. Optimized Image Processing: Concerns how image processing operations get handled.

### Control Panels

This panel’s parameters let you tailor how the DaVinci Control panels behave.

### Panel Sensitivity

Lets you set where red sits on the trackballs, how responsive the trackballs and rings feel, and how responsive the qualifier knobs feel.

- Classic DaVinci trackball alignment: Switch this checkbox on and every color balance control in DaVinci Resolve takes the long-standing orientation it has always used — near, though not quite identical, to the vectorscope alignment of hues. Switch it off and the color balance controls line up exactly with the vectorscope alignment of hues, much as other color grading apps do. Go with whichever mode you know best.
- Grading style: Sets how the trackballs are oriented against the corrections they produce. Two options exist:

DaVinci: Most people will recognize the standard DaVinci controls, since this echoes the vectorscope (how faithfully depends on the Classic DaVinci trackball alignment setting). Rank: The Rank settings differ a fair bit, so this option suits anyone at home with the color controls the Rank control system offered. Here the orientation of red and green is flipped.

- Lift RGB balance: Governs how fast moves on the Lift trackball (over on the left) drive the Lift Color Balance parameters on the Color page. The setting carries over to third-party panels.
- Lift master: Governs how fast moves on the Lift ring (encircling the leftmost trackball) drive the Lift Contrast parameter on the Color page. The setting carries over to third‑party panels.
- Gamma RGB balance: Governs how fast moves on the Gamma trackball (second in from the left) drive the Gamma Color Balance parameters on the Color page. The setting carries over to third-party panels.
- Gamma master: Governs how fast moves on the Gamma ring (encircling that second trackball from the left) drive the Gamma parameter on the Color page. The setting carries over to third‑party panels.
- Gain RGB balance: Governs how fast moves on the Gain trackball (third in from the left) drive the Gain Color Balance parameters on the Color page. The setting carries over to third-party panels.
- Gain master: Governs how fast moves on the Gain ring (encircling the third trackball from the left) drive the Gain Contrast parameter on the Color page. The setting carries over to third-party panels.
- Cursor offset: Governs how fast moves on the fourth trackball act on the cursor, the window position, the log-mode offset, and the other controls that trackball can drive.
- Cursor master: Governs how fast moves on the fourth ring act on the log-mode master offset and the other controls that ring can drive.
- Hue/Saturation/Luminance qualifier: Governs how responsive the HSL panel’s control knobs are.
- Jog: Governs how responsive the jog wheel is.
- Shuttle: Governs how responsive the shuttle dial is.

### Display Settings

Lets you tune the display on your Blackmagic Design control panels.

- LCD brightness: Governs the overall brightness of the DaVinci control panel displays.
- Key backlighting: According to which control panel you’ve chosen, two controls let you

set LCD Brightness and Key backlighting on the DaVinci Resolve Mini panel, while three controls let you tune the color balance of the lit buttons on the DaVinci Resolve Advanced control panel (its default is red).

### Metadata

Through the metadata panel you can assemble your own sets of metadata parameters that then surface in the Metadata Editor. For more on working with this panel, see Chapter 19, “Using Clip Metadata.”

### Keyboard Customization

Picking DaVinci Resolve > Keyboard Customization brings up the standalone Keyboard Customization window. There you can settle on which set of keyboard shortcuts to run, find out which shortcuts exist, or roll your own custom keyboard mappings that hew closer to how you prefer to work across whatever pages you happen to be in.

### The Keyboard Customization window

### Choosing Keyboard Shortcut Emulation Presets

A drop-down at this menu’s top right lets you pick the default DaVinci Resolve set or any of the others that aim to imitate other NLEs you may know better. Keep in mind that shortcuts can be remapped only to commands that genuinely exist inside DaVinci Resolve, so where a given feature of another NLE has no counterpart here, that key shortcut might not map the same way. Happily, DaVinci Resolve’s editorial feature set overlaps heavily with what’s common across other NLEs, so most of the features you’re accustomed to should have a working equivalent.

You can settle on one of the preset keyboard mappings to imitate an NLE you know or fall back on the default DaVinci Resolve keyboard mapping.

You can likewise put together your own custom sets of keyboard shortcuts. The Commands list underneath presents a tiered roster of commands grouped by the menu each lives in. From this list you select individual commands to remap, and you can search it whenever the item you’re after proves hard to spot. More detail on that follows later in this section.

### Viewing Commands Assigned to Specific Key Combinations

To learn which command a given key is bound to, click whatever combination of modifier and ordinary keys you like on the window’s virtual keyboard up top. The keys you’ve currently chosen show their binding in the “Active Key” list beneath. Choosing keys and modifiers on the virtual keyboard surfaces their command mapping below TIP: From DaVinci Resolve 15.2 onward, a command can carry several keys or key combinations, and the number keys on an extended keyboard’s numeric keypad can be bound separately from the keys along the top row.

### Panel-Specific Keyboard Mappings

As you customize shortcuts, you can bind one to the “Application” so it behaves the same throughout every applicable corner of the DaVinci Resolve UI, or you can map a particular shortcut to fire a particular command inside one specific panel.

Shortcuts can now be bound per panel, so one shortcut may carry out a different action in each panel that holds it

Panel-specific shortcuts let a single key behave differently depending on which panel holds focus; one key, for instance, might trigger separate actions in the Media Pool, do something else again in the Edit Timeline, and act differently still in both the Metadata Editor and the Sound Library — to cite a handful of Edit Page cases. That brings huge flexibility, yet taking this path means you have to keep track of which panel has focus. Helpfully, from DaVinci Resolve 15.2 onward, focus is flagged by a colored highlight along the top of each panel.

### Searching for Keyboard Shortcuts

Whether you want to survey the available shortcuts or track down a single command to customize, a Search field sitting above the Commands list lets you search whichever command group you choose (All Commands included). To hunt down specific keyboard shortcuts: 1 Pick DaVinci Resolve > Keyboard Customization. 2 From the Commands list, pick a command group to search inside. To comb through the whole of DaVinci Resolve, pick “All Commands.” 3 Enter a term in the Search field, and the Command/Keystroke list refreshes to display whatever commands fit the criteria you typed.

With “All Commands” chosen, running a search that turns up every shortcut tied to the word “ripple”

### Managing Keyboard Mappings

From the Option menu within the Keyboard Customization menu, DaVinci Resolve offers these ways to build and manage keyboard mappings:

Through the Keyboard Customization window’s Option menu you can export, import, and remove keyboard mappings
