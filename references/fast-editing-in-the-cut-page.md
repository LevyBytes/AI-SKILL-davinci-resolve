# Fast Editing In The Cut Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Fast Editing in the Cut Page

The Cut page's editing methods have been streamlined to make editing fast,

and this page's interface, along with the ways clips are assembled together using

various edit types, is built to be quick to pick up and quick to work with.

### Creating and Modifying Timelines

Once you've imported and organized the media your program needs, the next step is to create a timeline. Timelines are the organizational entities holding the edited sequences of clips that make up your program. Your project can carry as many timelines as you'd like, each one an independent arrangement of clips. Like clips, timelines live in the Media Pool and can be organized with bins.

### Creating New Timelines

The moment you edit your first clip into the Timeline, a timeline is created automatically. An icon for the new timeline shows up in the Media Pool, where it can be renamed.

A new timeline can also be created by either picking File > New Timeline (Command-N), or by right-

clicking the Media Pool background and choosing Create New Timeline. A dialog opens

letting you choose a start timecode (01:00:00:00 is the default), a name, the count of video and

audio tracks it should carry, the kind of audio (stereo is the default), and whether or not you

want an empty timeline, or one automatically holding every clip in the Media

Pool with or without selected In/Out points (a quick, easy route to a stringout of all the clips

you've imported).

By default, every timeline takes the same frame rate, resolution, and monitoring settings as the project overall. Should you prefer, you can click the Use Custom Settings button to pick individual frame rate, resolution, and monitoring settings for that timeline.

After a new timeline is created, double-clicking it opens it into the Timeline Editor.

### Opening Timelines

When your project holds only one timeline, the Timeline Editor always shows that timeline. Where several timelines exist, double-clicking any of them in the Media Pool opens it into the Timeline Editor, set for editing. Shifting from one timeline to another is also possible via the drop-down list near the top of the Cut page Viewer. Doing so aligns Viewer Timeline Selection behavior across the Cut, Edit, Color, and Deliver pages.

The Timeline Selection drop-down near the top of the Cut page Viewer

A timeline track's header carries the Enlarge, Lock, Audio Enable, and Video Enable buttons

### About Tracks in the Cut Page Timeline

For convenience, tracks in the Cut page timeline merge a clip's audio and video into one track, which makes keeping audio and video organized and in sync simple as many clips get superimposed together. So tracks carry both video and audio enable controls in the track header controls, letting you selectively disable video and mute audio when you need to. Each track additionally has a lock control, which stops clips on that track from being changed in any way.

### Enlarging Tracks

Clicking the Track Sizing icon on the left side of the track header enlarges or minimizes a track. An expanded video track displays a full size video and audio track, where one is attached. This makes focusing on just the track you want easier. Only one track at a time can be expanded.

A click on the Track Sizing icon enlarges the track so the clip's full audio track is shown

### Adding Tracks

When your timeline is short on tracks, click the Timeline Actions menu and pick Add Video/Audio/Subtitle track, or right-click anywhere on the Timeline and choose "Add Track," and a fresh track joins above whatever tracks are already present.

TIP: A new clip dragged onto the undefined gray region atop the Timeline likewise adds a fresh track.

### Deleting Tracks

To remove one specific track together with all of its clips, right-click somewhere in that track's header and choose "Delete Track." Should your timeline hold too many empty tracks, right-click somewhere in the track header and choose "Delete Empty Tracks," and every empty track is cleared away.

### Navigating Clips in the Viewer and Timeline

Before editing can begin, you need to find which parts of which clips to use and define where in the currently open timeline to make an edit. The Single Viewer on the Cut page offers different options that let you choose which media to play through using the transport controls along the bottom.

### Viewer Options

Three options, picked through buttons sitting at the Viewer's upper left, govern what gets displayed in the Viewer.

The Viewer option buttons, reading left to right: Source Clip, Source Tape, Timeline, and Multi Source

### Source Clip

This option displays the clip currently selected in the Media Pool. It's the mode the Viewer automatically

switches into whenever you double-click a clip in the Media Pool. Within Source Clip, a scroll area shows up

at the bottom of the Viewer, its width standing in for the duration of the currently open clip.

Within the scroll area a playhead lets you scrub the clip as a zoomed-in waveform while playing back

whatever audio falls within the clip. Handles at the left and right of the scroll area let you reposition

In and Out points within the clip to pick a section you'd like edited into the Timeline. These In and Out

points can also be set with the I and O keys. Once they're set, you can drag In and Out points to shift them.

### The Viewer showing Source Clip

The Source Clip option's scroll area, In and Out points placed on either side of the playhead Source Tape Under this option, every single clip in the currently open bin of the Media Pool, plus any subfolders within that bin, is presented in the Viewer as a "stringout" within the scroll area running along the Viewer's bottom. Within that scroll area, each clip follows the next in a long strip, ordered by the Sort order. This makes scrubbing through a whole batch of clips easy while you figure out what to use. As you play through, whichever clip the playhead crosses is selected in the Media Pool, so you know which clip is on screen.

### The Viewer showing Source Tape

The Source Tape's scroll area, a thin line dividing each clip from the next Timeline This option displays the current frame wherever the playhead sits in the Timeline. The instant you click, drag, or adjust a clip within the timeline area, the Viewer flips over to the Timeline. With this option there's no scroll area; you have to use the timeline area to scrub through your program. However, where the scroll area would otherwise sit, icons appear to signal when the playhead lands on the first or last frame of a clip in the Timeline.

### The Viewer showing the Timeline

Multi Source Where you have multiple clips synced either by timecode or waveform, you can view them all together, even across multiple bins in your project. Picking this option opens the Multi Source viewer within the Source Tape. It lays every synced media item out in a grid, with all media ganged together as you scrub through. In this mode, the In and Out points you set hold constant across the various angles, so swapping cameras leaves those same In and Out points valid on every clip. Such features let you rapidly settle on the best angle for a multi-camera shoot.

### The Viewer showing the Multi Source

In and Out points set within the Multi Source. They stay put as you change camera angles. Along the right side sit these Viewer controls, in order: Safe Area first, followed by Proxy Handling, next the Timeline Resolution control, and finally Bypass Color Grades and Fusion Safe Area This drop-down menu drapes a host of helpful framing guides across the Viewer so you can see which portion of the image stays in and which portion gets cropped off should the Timeline's aspect ratio change. Toggling the Safe Area Framing Guide icon in the Viewer switches the framing guides on and off, while the exact guides are picked from the drop-down menu.

Social Media: 1:1, 4:5, 9:16, 1.91:1, 16:9. Broadcast and Film: Default (your current timeline aspect ratio), 1.33, 1.66, 1.77, 1.85, 2.35. Safe Area Guides: These options drop additional guide lines onto the Viewer so your composition isn't at risk of being clipped at the outermost edges of a physical cathode ray tube. Though a touch anachronistic in this era of flat screen digital televisions, plenty of legacy programs still observe these guidelines. Safe Areas can still serve as useful guides for making sure your image isn't unintentionally cropped by the range of mobile devices and social media sites around today.

- Extents: Show the full boundary of the frame.
- Action: Keep all movement and important action within this box.
- Title: Keep all on screen text within this box.
- Center: Designates the exact middle of the image.

The extents Safe Area overlay can be toggled on or off, as can the Action, Title, and Center overlays. You can reach these features at View > Safe Area > Extents.

The Safe Area Framing Guide icon and the possible framing options

### Custom Guides and Snapping in the Timeline Viewer

The Timeline Viewer is where you can build your own custom guides. That gives you full customization to set specific geographic spots in the frame, then have the image snap to those spots during other operations. You can build Guides, which are colored lines crossing the frame either horizontally or vertically, plus Rulers, supplying measurement metrics down the frame's edges. As overlay tools for tuning your video position, both Guides and Rulers appear in the viewer alone, never in your final project output.

### The Timeline Viewer with Guides and Rulers enabled

Each of Guides and Rulers can be displayed separately by clicking its icon within the Ruler Guides section of the Timeline Viewer's Viewer Guides drop-down menu. Switching them on separately is also possible by way of the View > Rulers menu and the View > Guides menu. The Ruler Guides part of the Viewer Guides dropdown To Show and Modify a Ruler: 1 Turn the Ruler on by choosing View > Rulers > On, or by clicking the Ruler Icon in the Timeline Viewer's Viewer Guides dropdown. 2 Choose the metric the Ruler should use within View > Rulers, or by right-clicking the Ruler in the Viewer. Pixel: Renders the ruler as a pixel count measured out from the origin point (0,0) sitting at the frame's middle on a standard x/y cartesian coordinate graph, echoing the Position field in the Video Inspector. Percentage: Renders the ruler as a percentage distance measured out from the origin point (0%, 0%) at the frame's top-left. From left to right the top ruler spans 0% to 100%, while top to bottom the side ruler gauges 0% to 100%. To take an example, a point dead center in the frame would land at (50%, 50%).

### The Add/Edit Guide dialog

To Show and Create a Guide Line:

1 Activate the Guides by choosing View > Guides > On, or by clicking the Guides Icon in the Viewer

Guides dropdown on the Timeline Viewer.

2 To produce a fresh Guide, either choose View > Guides > Add Guide, or right-click the Ruler within the Viewer and pick Add Guides.

3 In the Add Guide dialog, pick the position and orientation you want the new guide to have, and click Add.

Units: Choose the metric the guide line should adopt. Pixel reports the pixel count out from the guide's origin point, whereas Percentage reports the percentage distance out from the frame's top left at 0%,0%. Position: Type a value for the spot in the frame the guide line should cross. The line can also be clicked and dragged in the viewer to place it by eye (as you move it, a small popup surfaces the exact position value). If you like, click the lock icon so this guide can't be nudged by accident. Orientation: Choose a horizontal or vertical orientation for the line. Color: Choose the guide line's color out of the available options.

To Modify a Guide Line:

- Drag the line wherever you like in the viewer, and a small pop-up window surfaces to reveal the exact position value.
- For legibility, recolor the Guide Lines by right-clicking within the Ruler and choosing a fresh color out of the Guide Color context menu.
- Delete a line by right-clicking it in the viewer and choosing Remove Guide.
- Reposition and reorient an existing line by right-clicking it in the viewer and choosing Edit Guide.
- Remove all lines, the horizontal ones only, or the vertical ones only, by choosing View > Guides > and picking the relevant lines to clear. The ruler's right-click menu does this too.
- Pin Guides in place against accidental movement by clicking the small lock icon at the Ruler's upper-left, or by choosing View > Guides > Lock Guides.

A right-click on the Ruler opens a context menu through which every parameter of the Rulers and Guide lines can be tuned

### Snapping to Guide Lines

By default, when you move the clip inside the frame using the Transform Viewer controls, whenever the image edge nears a Guide line it will snap the image edge to it automatically, turning the Guide line purple to let you know it's exactly placed. If you'd like to switch this behavior off, just hold the option key down while moving the image in the viewer to bypass the snapping.

The Guide lines shift to purple once the image's edge snaps onto that location

### Proxy Handling

You can flip between using your original source media and the proxy media for playback on the Cut page via the Proxy Handling icon in the Viewer, choosing one of the following options: Disable All Proxies: This option turns proxies off entirely and forces original media playback only. Where the original media isn't available, the clip is swapped for a Media Offline graphic. Prefer Proxies: This option uses proxy files for playback, and where there's no proxy file for a clip, the original media gets used automatically instead. Prefer Camera Originals: This option uses the original media files for playback, and where there's no original media file for a clip, the proxy media gets used automatically instead. The Proxy Handling icon in the Cut page Viewer lets you pick how you'd like to use proxy files.

### Timeline Resolution

This drop-down menu, at the top-right of the Viewer, lets you quickly pick which resolution to work at. A Custom option lets you open the Timeline Settings panel to choose your own options. For more about the Timeline Settings, see Chapter 6, "Project Settings."

### The Project Settings quick menu

### Bypass Color Grades and Fusion

With the Bypass Color Grades and Fusion Effects button/drop-down you can turn off every grade and effect applied on the Color page and/or Fusion page, lifting playback performance on low power computers. Click the button (Shift-D) to switch grading and effects off or back on, or right‑click it to reach a menu where you choose which things the button governs.

The Bypass Grades and Fusion button, captured mid right-click to reveal its options

### Playing Clips and Navigating the Timeline in the Viewer

Several controls run along the Viewer's base. They give you various ways to play through and otherwise move around clips and the Timeline. What follows describes the controls left to right.

### The toolbar at the bottom of the Viewer

- Tools button: The Tools button brings up an assortment of controls; among them are transform and crop, audio, speed effects, then camera stabilization plus lens correction, dynamic zoom, and compositing as well, all detailed more fully later in this chapter.
- POI and Add POI: These tools handle selecting and modifying Points of Interest in Replay, which gets its own manual. For further detail on them, consult the "DaVinci Resolve Replay Editor Instruction Manual."
- Fast Review button: Built to help you watch through a big media collection in a hurry, a click on this button kicks off accelerated playback over the Source Tape or the Timeline, the playback speed scaling with how long each clip you're running through is. Lengthy clips race by, while shorter ones run nearer real time. This lets you take in a great deal of material very fast.
- Jog control: Clicking then dragging inside the jog control lets you scrub very precisely across the Viewer's content.
- Transport controls: A cluster of buttons supply clickable control over playback of source clips and the Timeline, whichever one the Viewer happens to show; every button has its own matching keyboard shortcut. Among them are Previous Edit (Up Arrow), then Stop (Spacebar), Play (Spacebar) too, plus Next Edit (Down Arrow), along with Loop Playback (Command /).
- Mark In/Out: Clickable controls for setting In and Out points respectively.
- Playhead timecode: A number field shows the timecode value sitting at the playhead of a clip or of the Timeline, handing you a numeric reference for your position. The Cut page also has its own dedicated timecode entry mode.

DaVinci Resolve can be told you intend a timecode action in three ways, regardless of how the numeric keypad keys are mapped within the Keyboard Customization preferences.

- Select Playback > Goto > Timecode (=) and enter your timecode value.
- Hit the "+" or "-" keys, then type your timecode value to shift the current position

ahead or back by that amount.

- Click the Viewer's Timeline Timecode display, then type your timecode value.
- Skim Playhead: You can skim footage in any viewer across the Media, Cut, Edit, Color, and Deliver pages by holding the C key down and scrubbing the pointer back and forth in the viewer.

### Full Screen Viewer

Up in the Cut page's upper right is a Full Screen Viewer icon; clicking it turns on Full Screen view. Hit Escape to return to your usual view mode.

### The Full Screen Viewer icon

### Enhanced Viewer

On the Cut page the Enhanced Viewer offers an alternative. This larger viewer claims the screen's upper half, with the timeline area left where it is. Pressing Option-F toggles the Enhanced Viewer.

### The Enhanced Viewer in the Cut page

### Scrolling Through the Timeline

The Cut page keeps the playhead fixed. While you play, shuttle, or jog through your program, the Timeline's clips flow past the playhead right to left during forward play, or left to right during backward play. The upshot is that for playback, editing, or trimming, you carry the frame you'd like to see over to the playhead, instead of carrying the playhead over to the frame (the way you do on the Edit page).

To scroll or scrub through the Timeline, do one of the following:

- Have the Viewer display the Timeline, then reach for any transport or playback controls or keyboard shortcuts to shuttle the Timeline's clips back and forth, the playhead flagging the current frame.
- Drop the pointer inside the Upper Timeline's Timeline Ruler, then drag left or right to scrub across your whole program.
- Drop the pointer inside the Timeline Ruler of the larger Timeline Editor underneath, then drag left or right to scrub around the area close to the current frame.
- The navigation tools Playback > Previous / Next > Clip (Up Arrow/Down Arrow) or

Marker (Shift - Up Arrow/Shift - Down Arrow) serve to move around the Cut page Timelines.

TIP: Whenever you have to analyze the video in the Viewer, DaVinci Resolve's complete set of scopes can be reached on the Cut page by selecting Workspace > Video Scopes > On (Shift‑Command-W).

### Display Clip Names and Status in the Timeline

Should you want, clip names and clip status icons can appear directly atop your Timeline clips, making them easier to identify. To Display Clip Names for Clips in the Cut Timeline:

- Click on the Timeline Options icon.
- Select Display Clip Names from the drop-down menu.

To Display Clip Status Icons for Clips in the Cut Timeline:

- Click on the Timeline Options icon.
- Select Display Clip Status from the drop-down menu.

### Scene Cut Detection in the Cut Timeline (Studio Version Only)

The Scene Cut functionality can be put to work directly within a Cut timeline. It comes in handy where you've brought in video files of an already finished program and want it automatically chopped back into individual clips. For further detail on using Scene Cut Detection, consult Chapter 23, "Using Scene Detection." To run Scene Cut Detection on a Cut Page Timeline: 1 Pick the video clips on the Timeline you'd like split back into multiple cuts. 2 Pick the Timeline Actions icon and choose Detect Scene Cuts off the drop-down menu.

### The Boring Detector

A live analysis of how long each of your Timeline clips runs is what the Boring Detector performs, then it flags stretches too long or too short that might want your attention. To reach it, click the Timeline Options icon and pick Boring Detector. Clicking the icon a second time toggles it off. The Boring Detector icon alongside the Timeline displaying its results Analyze Timeline Edits CUT You adjust the Boring Detector's parameters within its Analyze Timeline Edits window.

- Boring Clips: Adjusting this slider sets the minimum number of seconds a clip's duration must reach before being flagged as too long. Clips exceeding this length are highlighted in light gray on the Upper Timeline.
- Jump Cuts: Dragging this slider fixes the most frames a clip's duration may carry before it gets flagged as too short. Clips falling below this length show up in red on the Upper Timeline. Set it to 2 frames and it can automatically surface accidental "flash frames" for you.
- Cancel: Closes the window while leaving the Boring Detector's analysis untouched.
- Analyze: Kicks off the live analysis of your timeline against the criteria you picked above.

Being persistent, the Boring Detecter carries on working as you go on editing on the Cut page. A further click on the Boring Detector icon turns it off.

### The Boring Detector's Analyze Timeline Edits window

### Setting In and Out Points

As a rule, source media stretches well beyond the actual clips you'll put into a program, so being able to mark off the range of media you'd like edited into the Timeline matters. You do this by laying In and Out points, whether in the Media Pool under Thumbnail or Filmstrip mode, or in the Viewer under Source Clip or the Source Tape.

### Setting In and Out Points Using the Keyboard

As you scrub a thumbnail or filmstrip within the Media Pool, hit the I (In) or O (Out) keys to mark off a range of media. Those edit points appear laid over the clip's thumbnail area, and over the Viewer's scroll area too whenever the clip is mirrored there. Marking off a range of media in the Media Pool with In and Out points (in white) As you scrub or shuttle media within the Viewer under Source Clip or the Source Tape, or run through your program with the Viewer set to Timeline mode, hit the I (In) or O (Out) keys to mark off a range of media. Marking off a range of media in the Viewer with In and Out points As you scrub or shuttle the Timeline while dragging the ruler left and right, hit the I (In) or O (Out) keys to mark off a range for incoming edit operations. That range gets indicated across both the upper and lower regions of the Timeline.

Marking off a range of the Timeline for editing operations with In and Out points

### Setting In and Out Points Using the Pointer
