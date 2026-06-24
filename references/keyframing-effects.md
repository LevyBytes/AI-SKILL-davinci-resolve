# Keyframing Effects (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Keyframing Effects

Both the Edit and Cut pages give you controls for keyframing the effects you place onto your timeline.

The Inspector lets you keyframe most of its parameters so you can build animated effects — for example zooming in through the Zoom parameter, fading out through the Opacity parameter, or sliding in from an edge to reveal the clip beneath through the Cropping parameters. On top of that, when you bring in a project from an NLE carrying keyframed sizing settings, DaVinci Resolve imports and surfaces those keyframes for you. You will find the core keyframing controls inside the Video Inspector. Each keyframeable parameter carries a gray keyframe button just right of its slider. When the playhead sits on a keyframe that button shifts to orange and tiny navigation arrows show up on either side; otherwise it remains gray.

Orange buttons throughout the Inspector signal how keyframes are being used. Zoom shows the playhead resting on the present keyframe while the gray navigation arrows reveal further keyframes both ahead of and behind it. Position shows the playhead resting on the lone keyframe placed (orange diamond, no arrows), and Rotation Angle shows that no keyframe exists (gray diamond). After you have keyframed a parameter or two inside some group of the Inspector, that clip picks up a Keyframe icon at the far left end of its name bar in the Timeline. This icon appears solely on keyframed clips.

Shown here on a keyframed clip in the Timeline: the Keyframe track button (circled)

### Basic Keyframing in the Video Inspector

You can handle most straightforward keyframing right in the Inspector with the three buttons that sit to the right of any keyframeable parameter. Creating an animated effect requires no fewer than two keyframes.

In the Inspector, reading left to right, the trio of keyframe controls is: Previous keyframe, Create/ Delete keyframe, Next keyframe Ways to keyframe parameters within the Inspector:

- To add a keyframe: Choose a clip, open the Inspector, then drag the Timeline playhead to the frame that should hold a keyframe, and press the Keyframe button beside whichever Inspector parameter you mean to animate. After you have set at least one keyframe on a parameter, every further tweak you make to Inspector parameters, or through the onscreen Transform/Crop controls in the Timeline Viewer, spawns fresh keyframes on its own whenever the playhead sits on a different frame.
- To move the playhead to the next or previous keyframe: Press the little left- or right-hand arrow flanking a parameter’s keyframe control to send the playhead to the next or previous keyframe. Alternatively, tap Right-Bracket ( [ ) and Left-Bracket ( ] ) to step between keyframes.
- To edit an existing keyframe of a parameter: Park the playhead directly over the keyframe you intend to change, then alter that parameter, either in the Inspector or with the onscreen controls of the Timeline Viewer.

Methods of changing keyframe interpolation in the Inspector:

- To change a keyframe to Ease In or Ease Out: Eased keyframes produce animated transitions that start gently and ramp up to full speed, or wind down gradually until they halt. This applies only when two or more keyframes are forming an animated effect. Using the next/previous keyframe controls, land the playhead on a keyframed frame; now right-click the orange keyframe button and select Ease In, Ease Out, or Ease In and Out, depending on the keyframe under edit and the result you are after.
- To change a keyframe to Linear: Drive the playhead onto a keyframed frame via the next/ previous keyframe controls; afterward, right-click the orange keyframe button and select Linear.

Methods of deleting keyframes and disabling keyframed effects:

- To delete a single keyframe: Open the Inspector, slide the Timeline playhead onto a frame carrying a keyframe, and press the orange Keyframe button in the Inspector to remove it.
- To delete all keyframes for one parameter: Press the reset button at the right of a parameter’s keyframe control in the Inspector.
- To delete all keyframes in a group of parameters in the Inspector: Press the reset button at the right of a parameter group’s title bar in the Inspector.
- To disable or enable a group of parameters in the Inspector: At the left end of a parameter group’s title bar within the Inspector, press the toggle control. Orange means the group is on; Gray means off.

### Keyframing Motion Paths in the Timeline Viewer

When you are keyframing a clip’s transform controls to generate motion, a motion path shows up once you switch on the Transform controls via the drop-down menu at the lower left of the transport controls.

A visible motion path resulting from animated Position X and Y parameters Every keyframed shift in the Position X and Y parameters lays a control point onto the surface of the motion path, which defaults to linear and so produces a sharp corner. Even so, you can right-click any control point and pick Smooth from the contextual menu to attach Bezier handles to it, turning that sharp corner into an adjustable curve.

Changing the linear control point into a Bezier curve You may drag the control points that form any motion path wherever you like to reroute the course the chosen clip follows. The dots running along the motion path’s surface convey how fast the motion is; dots packed close together signal slower motion, while dots spread apart signal faster motion. Pulling one motion path control point further from a neighbor accelerates the animation between the two, whereas pulling it nearer slows the animation, since you are making the chosen clip cover a greater or smaller distance over the same keyframed span of time.

Along the motion path the dots reveal slow motion across its left portion and quicker motion across its right You can likewise reshape any control point’s curve by clicking to select it, which reveals its Bezier handles, and then dragging those handles to tune the curve. After the handles are revealed, a range of approaches is available for adjusting them and shaping the motion path. Lastly, you can tune the motion’s acceleration via the Acceleration handle on the stem of any Bezier curve. Pulling an acceleration handle in toward a control point yields an eased keyframe, where motion eases to a halt or starts up from a halt. Pulling an acceleration handle out from a control point yields more linear motion, where the object passes steadily through that control point.

Sitting on a curve’s Bezier handle, an acceleration handle produces eased motion when you pull it inward toward the control point under adjustment Ways to adjust the Bezier handles on motion paths:

- Drag any control point to reshape the motion path.
- Drag any Bezier handle to change the shape of the curve.
- Command-drag any Bezier handle to sever the tangent linking it to the Bezier handle opposite. Once you let go of the Command key, the two Bezier handles lock back together at whatever angle you set.

To remove a motion path control point together with its keyframe:

- Right-click any control point and choose Delete Keyframe.

To switch a control point between sharp and curved angles:

- Right-click whichever control point you want and pick Linear to get a sharp angle, or Smooth to get a curve.

### Keyframing in the Edit Timeline and Curve Editor

You can work with keyframes straight in the the Timeline; or, when you need keyframe editing more involved than the fairly basic controls of the Inspector and Timeline permit, turn to the Keyframe tracks and Curve Editor that live in the Edit Timeline. Once one or more clip parameters carry keyframes, the far-right edge of that clip’s Timeline name bar gains two tiny buttons: a Curve button and a Keyframe button. Through these buttons you reach dedicated keyframe editors built for different jobs.

### Keyframe Directly in the Timeline During Playback

You can drop keyframes straight onto clips in the Timeline as playback runs. Keyboard shortcuts let you add and remove a clip’s keyframes, and DaVinci Resolve does its best to read the clip’s context and set the right keyframe. With this approach you can rapidly and accurately lay down retime and audio gain Keyframes during playback, then return later to work the points you marked. To Add a Keyframe to a Clip in the Timeline:

- Play the clip on the Timeline, and as the playhead crosses the frame of the clip where the keyframe belongs.
- Choose Mark > Add Keyframe (Command-[).

To Delete a Keyframe in a Clip in the Timeline:

- Pick the keyframe or keyframes you intend to remove from the clip.
- Choose Mark > Delete Keyframe (Option-]).

Although dropping a keyframe onto a timeline clip is a single keypress, how does DaVinci Resolve figure out which exact parameter, among all the choices in the inspector, you meant to keyframe? In short, the keyframes are now context aware: the keyframable attribute (Zoom, Position, Volume, etc.) that DaVinci Resolve picks rests mainly on the last thing you worked with, or otherwise on the one used most often. DaVinci Resolve’s keyframe selection hierarchy walks the keyframable options from the top downward; whenever no keyframe fits the context of the topmost entry, it moves on to the next entry below, and so forth. The DaVinci Resolve Keyframe Selection Order:

- The Retime Controls (if already active)
- The active effect curve in the Keyframe Editor (if already open)
- The last Inspector control that was manipulated
- Audio Gain

As an illustration, suppose you had earlier tweaked the Zoom parameter on a clip, then dropped a fresh keyframe onto it by pressing Option-[ ; it would skip past the Retime Controls and the Effect Curves (if those were closed in the inspector) and lay down a new Zoom keyframe, since that was the last tool you touched. By the same token, adding a keyframe to a plain clip on a timeline that has no modifications gives you an Audio Gain Keyframe. Should you want richer keyframing, or should DaVinci Resolve misread the context, you can fall back on the Keyframe Editor.

### Keyframe and Curve Editor

DaVinci Resolve’s Keyframe and Curve Editors exist to hand you precise control over intricate animations too detailed for the Inspector. You can reach the Keyframe and Curve Editor from both the Cut and Edit pages as a panel of its own. Just click the Keyframes tab in the upper left to bring it up. The Keyframe Editor appears by default, presenting every keyframable parameter from the Video Inspector alongside any keyframes already placed there. Clicking the Curve icon in the upper left carries you over to the Curve Editor.

### The Keyframe Editor

Within the Timeline, the Keyframe Editor is the strongest means of laying out all of a clip’s keyframes and fine-tuning their timing and interpolation.

The Keyframe Editor showing all the video attributes found in the Inspector For each parameter that can be keyframed on the chosen clip, the Keyframe Editor lays out one keyframe track. At first glance this resembles a long list of fiddly items to track (no pun intended), yet it does hand you a solid survey of everything animatable on your clip. That said, the Keyframe Editor offers several tools for clearing away needless clutter so you can zero in on just the parameters you care to animate. These keyframe tracks let you edit keyframes against the real clip durations in the Timeline.

Keyframe Tracks: Transform serves as the track group (revealed via the disclosure triangle), with Zoom and Position XY being tracks nested in it. An outline and white fill mark the selected keyframes. The tracks are likewise sorted by parameter category. As an example, every Transform, Cropping, and Speed parameter is wrapped inside group tracks. Had you keyframed the Zoom and Position parameters, those keyframes would also surface inside one keyframe track named Transform, while Crop Left and Crop Right changes would land on a separate group keyframe track named Cropping. Shifting a keyframe on a group track moves the keyframes sitting at that same spot across all of its contained parameters together. Every group keyframe track carries a disclosure arrow letting you reveal or conceal each separate parameter inside that group. As an example, clicking the Transform keyframe track’s disclosure arrow exposes the Zoom and Position tracks, so you can work their individual keyframes.

### Organizing the Keyframe Editor

Keyframing on its own is a reasonably simple business, but the sheer count of keyframable attributes can be daunting, so unless you intend to animate something fiendishly complex, you are likely better off narrowing the Keyframe Editor’s interface down to only what you require.

### To show or hide tracks by parameter group

- Click the little disclosure triangle beside the group track’s name. As an example, if you only meant to keyframe parameters within the Transform group (Zoom, Position, etc.), you could shut the disclosure triangles in the Cropping and Speed groups to tuck away the surplus tracks.
- Click the 3-dot option menu at the right of the parameters column, and pick Expand All Parameters to throw open every group track and reveal its enclosed parameters.
- Click the 3-dot option menu at the right of the parameters column, and pick Collapse All Parameters to shut all group tracks.

### To show only tracks that already have keyframes

- Click the 3-dot option menu at the right of the parameters column, and pick Display Parameters with Keyframes. This reveals only those tracks already holding at least one keyframe, plus their enclosing group tracks.

### To show only Video related tracks

- Click the 3-dot option menu at the right of the parameters column, and pick Display All Video Parameters. This conceals any keyframe tracks driving audio-related functions from the Audio Inspector.

### To show only specific tracks

- Click the 3-dot option menu at the right of the parameters column, and pick Display Selected Parameters. Then you can tick checkboxes for Video and Audio. Clicking those reveals a further set of checkboxes letting you pin down exactly which tracks to show.

### To undock and resize the Keyframe Editor

- Click the undock icon in the Keyframe Editor to pop it out as a standalone window. From there you can resize the window to grow the Keyframe Editor to whatever dimensions you need.

### Using the Keyframe Editor

With the Keyframe Editor open and the parameters you mean to animate revealed, you have plenty of ways to add, remove, and reshape the keyframes sitting on these tracks. Reading left to right, the Keyframe Track controls run: Toggle Curve Visibility, then Toggle Keyframe Lock, next Track Color, followed by Track Name, then Keyframe, then Reset Keyframes, and finally Keyframe position. The Keyframe Track Controls are:

Toggle Curve Visibility: Click this icon to switch this track’s curve visibility on or off in the Curve Editor.

Toggle Keyframe Lock: Click this icon to switch the keyframe lock on or off and guard against unintended changes.

Track Color: A tiny colored dot indicates the color of the track’s curve in the Curve Editor.

Track Name: The name of the track parameter.

Keyframe: Clicking the diamond drops a new keyframe at the present position. When a keyframe is active at that position the diamond shows orange, otherwise white. The left and right arrows jump to the previous and next keyframes respectively.

Reset Keyframes: Clears every keyframe in the track. Keyframe Position: Displays all the track’s placed keyframes and where they fall within the clip.

Methods of adding and selecting keyframes in the Keyframe Editor:

- To add new keyframes to the Keyframe Editor: Move the playhead to where the keyframe should go, then click the grey diamond beside the parameter’s name. The diamond shifts to orange to confirm a keyframe was added, and it also turns up on the parameter track at the playhead position. You can lay further keyframes on this track by pressing Command [ to add another keyframe.
- To select a single keyframe: Click a single keyframe to select it.
- To select multiple discontiguous keyframes: Command-click each keyframe you want, whether or not they sit beside one another.
- To select multiple contiguous keyframes: Drag a bounding box inside the keyframe track around several keyframes to grab them all together.
- To move one or more keyframes: Pick one or more keyframes and drag left or right.
- To nudge keyframes: Pick the keyframe(s) you intend to move. They can be nudged up/down/

left/right by one frame, via the Mark > Move Selected Keyframe … menu items. You can (and, for the sake of usability, probably should) bind these commands to keyboard shortcuts.

- To toggle all keyframe parameters at once: Shift click the lock or show curve icons in the curve editor.
- To “solo” a keyframe parameter: Option-click the lock or show curve icons in the curve editor to “solo” the chosen parameter exclusively. Option-click once more to exclusively switch off the chosen parameter and turn the rest back on.

Methods of Cutting, Copying, Pasting, and Deleting keyframes:

- To cut or copy, and paste one or more keyframes: Build a selection of keyframes, and reach for the Cut (Command-X) or Copy (Command-C) key shortcuts. Next, slide the playhead to where the first of the copied keyframes should begin, and hit Paste (Command-V).
- To delete one or more keyframes: Pick the keyframe(s) you want gone and press Delete.

IMPORTANT: Keyframes on the Timeline can live beyond a clip’s present extents. As an example, if you place several keyframes on a clip and then trim its Timeline duration past one of them, that keyframe shows up as a directional arrow rather than a point. You can still reach these keyframes through the Previous “[“ and Next “]” keyframe commands or via the keyframe controls in the Inspector.

From left to right, these Keyframe Editor controls appear: Curves Editor, then Keyframe Editor, next Detail Zoom, followed by Full Extend Zoom, then Zoom Slider, then Expand, and lastly Option Menu.

Curves Editor: Click this icon to open the Curves Editor.

Full Extend Zoom: Zooms the Keyframe Editor out far enough to show the whole clip’s range.

Parameters: Click this icon to open the Keyframe Editor.

Zoom Slider: Lets you pick a custom zoom level for the Keyframe Editor

Detail Zoom: Zooms the Keyframe Editor in around the playhead position.

Expand: Opens the Keyframe and Curves Editor in its own resizable window.

Option Menu:

- Display Time Ruler in Seconds: Renders the time ruler in HH:MM:SS:FF timecode format drawn from the timeline.
- Display Time Ruler in Frames: Renders the time ruler as a frame count measured from the timeline start.
- Snap Keyframes to Grid: Once turned on in the Curve Editor, this snaps keyframe control points onto the playhead position.
- Show Curve Tooltips: Once turned on in the Curve Editor, hovering the pointer over a curve reveals its track name and value at that point.

Parameters: Shows a list of keyframable parameters. Option Menu:

- Display Parameters with Keyframes: Reveals only tracks holding existing keyframes and hides the rest.
- Display All Video Parameters: Reveals every keyframable track from the Video Inspector and hides the rest.
- Display Selected Parameters (Video & Audio): Brings up a checkbox for switching individual track visibility on or off. Moreover, when you have added a keyframable Open FX or Resolve FX onto the clip, you can pick those parameters here.

Expand All Parameters: Throws open every group track to reveal its enclosed parameters. Collapse All Parameters: Shuts every group track to hide its enclosed parameters.

### Opening the Keyframe Tray in the Timeline

Apart from the dedicated Keyframe Editor panel, a keyframe tray can be summoned right on the timeline: on both the Cut and Edit pages, click the Show Keyframe Tray icon found on the main timeline toolbar. Every keyframe belonging to the timeline’s currently selected clip is laid out by this keyframe tray, which works just like the Keyframe Editor.

You can bring the Keyframe Editor up directly in the timeline by clicking the Show Keyframe Tray icon (circled red). Clicking the curves icon in the keyframe tray lets you tune the values and timings of a timeline keyframe using the very same keyframing controls found in the keyframe editor.

Reaching the Curves editor on the timeline is a matter of clicking this keyframe-tray icon

### The Curve Editor open in the timeline

Opening the Keyframe and Curve Editor in Its Own Window When your keyframing work in the Edit page is extensive (this is not offered in Cut), you can pop the Keyframe and Curve editor out into its own resizable window for more room to operate. To do that, click the Expand icon at the upper right of the Keyframe Editor.

You can expand the Keyframe and Curve Editor out into a resizable window all its own.

### The Curve Editor

When you need to handle keyframes in even finer detail, the Curve Editor is the tool. On a click, the the Curve Editor opens out to fit a large graph where you can freely tune both the timing and the value of selected keyframes, while also offering optional Bezier spline controls for building smooth curves to shape the acceleration of animated transitions from one value to another.

Here the Curve Editor displays the timing and values for the parameters you have selected. To open the Curve Editor: At the upper left of the Keyframe Editor, click the Curve icon. Once open, every track holding keyframes shows up as a colored line on the graph, with control points sitting along the line at each keyframe position. Hovering the pointer over a line brings up its track name (and its present value) in a pop up. The line’s color also mirrors the track color in the Keyframe Editor. You can reveal and hide several parameters in the Curve Editor through the Parameters menu, which lets you toggle which tracks appear via checkboxes. Along the bottom of the Curve Editor runs a keyframe track matching the Keyframe Editor that shows the keyframes for the chosen curve. You can only edit one curve at a time, but you choose which one is selected by clicking any dimmed curve in the Curve Editor. Through the control points each curve exposes, you can edit parameters, reposition keyframe timing, and reset each control point’s interpolation to craft custom easing effects that govern how the change speeds up as it travels between adjacent keyframes. Ways to add and select keyframes within the Curve Editor:

- To change which curve you’re editing: Click the Parameters menu and pick which curves to bring up for work. With several curves open at once in the Curve Editor, clicking any dimmed background curve brings it forward for editing.
- To add new keyframes to a curve: Option-click anywhere along a curve to drop a new control point. You can also choose the Add Keyframes icon at the top of the toolbar, which lets you add several keyframes to a curve just by clicking on it.
- To duplicate one or more keyframes: Build a selection of keyframes, then press Command-C to copy, slide the playhead to your paste point and press Command-V. This can be a handy way to swiftly loop a repeating animated effect you have built.
- To select a single keyframe: A single click on one control point selects it. That same action also works on the keyframe track running along the very bottom of the Curve Editor.
- To select multiple discontiguous keyframes: Command-click each control point you want, whether or not they sit beside one another. The same move works on the keyframe track running along the very bottom of the Curve Editor.
- To select multiple contiguous keyframes: Click the first keyframe you want, then shift-click the last keyframe you want, and every keyframe in between joins the selection too; or drag a bounding box inside the Curve Editor around several keyframes to grab them all together. The same move works on the keyframe track running along the very bottom of the Curve Editor.
- To select all keyframes: When the Keyframe Editor is open and has focus (from clicking somewhere inside it), pressing Command-A selects every keyframe within that Keyframe Editor.
