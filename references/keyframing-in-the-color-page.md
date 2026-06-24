# Keyframing In The Color Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Keyframing in the Color Page

A purpose-built Keyframe Editor lives on the Color page, sitting to the right of the palette area, and it lets you drive grading adjustments across frames over time. Since color work is a distinctly different job from cutting, this Keyframe Editor on the Color page behaves a bit unlike the Curve Editor you find over in the Edit page.

### Introduction to Keyframing

Call it keyframing, dynamics, or marks if you like; DaVinci Resolve gives you a way to smoothly interpolate color adjustment parameters through several methods, moving from one setting toward another. Say a clip drifts in exposure, for instance: you might roll a sequence of contrast tweaks with Dynamic keyframes so those exposure shifts feel less jarring.

The Keyframe Editor with dynamic keyframes animating the parameters of Node 2 Here's a second scenario: you're cutting a documentary, and one archival clip dropped into the middle of the Timeline is really six separate shots pulled from an eighties broadcast. Pressed for time, you can drop Static keyframes (marks) right at each shot's cut point, producing immediate single-frame jumps between the different tweaks applied to that clip's grade, so each shot inside the one clip gets its own treatment.

Round static keyframes dropped onto every parameter, letting shots that were combined into one clip each be tuned on their own Either way, the Keyframe Editor is where you build a run of keyframes that shift parameters from one value across to another. The pages ahead walk you through using the Keyframe Editor to construct these animated adjustments.

### The Keyframe Editor Interface

Every control you need to build and tweak keyframes for whichever clip is selected lives in the Keyframe Editor. When you want more room on a single-screen layout, just click its expand button (located at the top right of the Keyframe Editor) to widen it. With a pair of displays attached, the Color page's Dual Screen layout will park the Keyframe Editor on the second monitor and let it span that screen's full width, giving you a lot more workspace.

The Node Editor displayed wide, shoving every other palette over toward the left These are the pieces that make up the Keyframe Editor:

- Timeline Ruler: Reflects the record timecode of whichever clip is currently selected; drag inside the Timeline Ruler to reposition the playhead, while a timecode readout on the left reports the current frame.
- Keyframe track header: Every node in the active grade gets a matching keyframe track, Sizing carries its own keyframe track too, and the keyframing controls you'll manage are housed in the track header.

### The Keyframe track header

- Enable/Disable button: Toggling this round white button turns that track's matching node on or off.
- Lock button: Stops anything on that track's matching node from being altered. A lock icon marks any node you've locked. Locking and unlocking is also possible by right-clicking a node over in the Node Editor and picking Lock Node from the contextual menu.

Within the Color page's Keyframe Editor, Nodes 1 and 2 sit locked.

- Auto-Keyframe button: Flip this on so a Dynamic keyframe is generated automatically each time you tweak any parameter inside that node.
- Track disclosure triangle: Reveals separately keyframable parameter groups sitting below the primary keyframe track.
- Keyframe tracks: Sitting to the right of the track header, this is the area where keyframes that drive parameter changes get built and edited. At the very top, a "master keyframe track" surfaces every keyframe placed on any keyframe track in the Keyframe Editor, including ones on a keyframing track tucked away inside a track whose disclosure triangle is closed.
- Keyframes: A Dynamic keyframe shows up as a tiny diamond, whereas a Static keyframe shows up as a circle. Dissolves go with Dynamic keyframes, while Static keyframes (marks) take effect at once. Each grade ties back to the keyframe before it, possibly a default placed on the master clip's first frame. Click a keyframe to select it, or drag it elsewhere along the keyframe track to reposition.
- FX track: When Resolve FX or OFX plugins land in a grade as their own standalone node, they receive a dedicated track for building animated effects. That track's every parameter is keyframed through one combined keyframe track. Stack several plugins as separate nodes and each gets its own FX track.
- Sizing track: A wholly separate track exists for the Pan, Tilt, Zoom, Rotate, and Convergence (in Stereo 3D projects) parameter, meant for animating pan-and-scan moves.
- Track selection drop-down: A tinted bar marks the keyframing scope in effect right now: every track together, only the active correction node, or just the Sizing settings, governed by the Keyframe Timeline mode covered in the section that follows.

Normally the Keyframe Editor occupies the bottom-right third of the Color page. You can still stretch it out for more working room whenever a scene demands intricate keyframing. So, to grow or shrink the Keyframe Editor:

- Click the Expand/Collapse button up in the top right corner of the Keyframe Editor. The Keyframe Editor expands or contracts to match.

To zoom into and out of the keyframe tracks:

- Drag the Zoom slider to scale the Keyframe Editor in or out.
- Right-click on a keyframe track and pick Maximum Zoom to zoom in completely.
- Right-click on a keyframe track and pick Reset Zoom so the whole clip fits across the Keyframe Editor's available width.

### All/Color/Sizing

Arguably the single biggest keyframing control, the Keyframe Timeline mode changes which tracks receive keyframes when you trigger the Start Dynamic or Add Static Keyframe commands, whether off the keyboard or through your control panel's buttons. The command cycles through three modes:

- All: This is the default. It drops keyframes onto every track in the Keyframe Editor, keyframing all parameters across all nodes simultaneously, Sizing settings included. An orange bar shows up here, calling out the uppermost "master keyframe track."
- Color: Keyframes land only on whichever node is active in the Node Editor. A green bar appears here, marking the keyframe track that belongs to the currently selected node.
- Sizing: Keyframes go only to the Sizing track, which comes in handy while you keyframe "pan and scan" style transforms. A blue bar appears here, calling out the Sizing track.
- EXT MATTE: Shows up solely when an external matte node sits in the node tree. It lets you keyframe parameters specific to the external matte over in the Key palette.

While All is what's set by default, switching over to the Color or Sizing keyframing modes can pay off by sparing you a pile of pointless keyframes. Keyframing it all in one shot may be quick, yet those surplus keyframes can drag on you later, once you have to revisit nodes that never warranted keyframing to begin with. So, to swap the keyframing mode, take one of these routes:

- Select something from the Keyframe mode drop-down located up at the Keyframe Editor's top right.
- Select something from the Mark > Keyframe Timeline mode submenu.

TIP: This control serves a second purpose. The mode you pick also governs what gets carried over when you reach for the assorted grade management tools inside DaVinci Resolve. Choose Color, say, and a clip's color grade copies without its sizing tagging along. Choose Sizing, and the sizing copies free of the color grade.

For more information, refrer to "Copying Grades" see Chapter 142, "Grade Management."

### Keyframing Methods

DaVinci Resolve relies on two distinct keyframe types to produce automated changes. The way each type interpolates parameters is different.

### Dynamic Keyframes (Dynamics)

The keyframe you'll lean on most is the Dynamic keyframe, and it's the variety meant for animating a transition from one state into another. If a grade must brighten gradually to offset shifting light, for example, Dynamic keyframes are the tool. Almost any parameter or control on the Color page accepts keyframes, though bear in mind the Interface controls won't animate alongside the dynamically keyframed changes underway. Rather, the visible Interface controls tied to keyframed changes snap from their starting spot at one keyframe to their ending spot once the playhead arrives at the following keyframe. Curves can make this especially baffling, since they too can be interpolated with Dynamic keyframes, the same as any control or parameter. Simply remember the underlying settings really are animating, despite the controls staying put. To animate a node using Dynamic keyframes: 1 Within the Keyframe Editor's Timeline ruler, drag the playhead to whichever frame ought to kick off a change. 2 Drop a Dynamic keyframe onto that frame through one of these methods:

- Choose Mark > Add Keyframe (Command-[).
- Switch on the Auto Keyframe button for the track you intend to animate in the Keyframe Editor. Dynamic keyframes are diamond-shaped.

3 If needed, tweak your clip at this opening spot of the animated change. With Auto Keyframe running, you'll have to make a tweak before a keyframe gets created.

4 Next, slide the playhead to the frame marking the second spot of the animated change you're building, and lay down another Dynamic keyframe if you're placing them by hand, or do another tweak if Auto Keyframe is active. 5 Once that second keyframe exists, apply whatever adjustments the clip needs to reach the final look you're after. From there, scrubbing from the first keyframe through to the second ought to reveal a smooth animated transition from the first adjustment into the second. After you wrap up, be sure Auto Keyframe gets switched back off if it had been on.

### Static Keyframes (Marks)

Static keyframes, also called marks, are the keyframes you reach for to produce sharp, single-frame jumps from one state into another. They're commonly placed to flag the edit points dividing one shot from the next where several shots live inside a single clip. That said, Static keyframes also help in any case calling for an instant switch from one setting to another, like building a lightning effect.

Static keyframes are round. To automate a node using Static keyframes: 1 Locate the frame where the sudden change should happen, and lay a keyframe at that frame with one of these methods:

- Choose Mark > Make Static Keyframe (Command-]).
- Static keyframes (marks) are round. 2 Slide the playhead to any frame ahead of the keyframe to alter the whole stretch of the clip running up to it, or slide it to any frame past the keyframe to alter the whole stretch of the clip that follows. The playhead need not sit right over the keyframe, though if it does, you'll be tweaking the clip's second portion.

NOTE: When Static keyframes are automating grading changes across several shots living inside a single clip, remember you can't tack on nodes from one keyframe to the next the way you could had you cut the clip apart on the Edit page.

### Mixing and Converting Dynamic and Static Keyframes

Generally, building several animated changes inside a clip means reaching for all Dynamic keyframes. Likewise, a run of sharp changes means all Static keyframes. Still, blending Dynamic and Static keyframes is allowed, provided you keep these rules in mind:

- Place a Dynamic keyframe just rightward of a Static keyframe: No interpolation happens going from the Static keyframe over to the Dynamic one. Flip it around, though, and dropping a Static keyframe rightward of a Dynamic keyframe does interpolate.

### No dynamic interpolation following the static keyframe

Should you create the wrong keyframe type by mistake, swapping it for the one you wanted is simple. To turn one keyframe variety into the other: 1 Select the keyframe you'd like to convert by clicking it. 2 Right-click that selected keyframe and pick either Change to Dynamic Keyframe or Change to Static Keyframe.

### Try Creating Keyframed Changes in a Separate Node

Worth remembering: keyframed changes don't have to live inside the very nodes handling your other adjustments. To add some automated changes while leaving the nodes you've already tuned untouched, just spin up a fresh node to hold your keyframed work. That way, if the outcome disappoints, or you end up hopelessly snarled in an absurdly intricate web of keyframes, resetting either the keyframes alone or the whole node stays easy and leaves the rest of your grade alone.

### Keyframed Nodes Have a Badge

Any node carrying keyframed parameters shows a keyframe badge over in the Node Editor so it's quick to spot. Keep in mind those badges hold off appearing when you merely add a keyframe and only surface once a real keyframed adjustment is in place.

Keyframed nodes display a badge in the Node Editor.

### Using Specific Keyframing Tracks

When you simply work in the Color mode of the All/Color/Sizing command for keyframing, every parameter on the active node picks up a keyframe each time you apply just one. Often that's more than you need, though, in cases where a single setting or a small group of settings is all that calls for keyframing. You might, for instance, want to keyframe a color tweak to shift color temperature and brightness as the camera sweeps past a window, while leaving the Windows palette controls unkeyframed because you'd rather tune them on their own. The way to do that is to open a Corrector track and reveal the keyframing tracks inside.

Individual keyframing tracks within a Color Corrector node Keyframing tracks make it possible to keyframe distinct groups of similarly behaving parameters apart from each other. One keyframing track, for example, handles every color adjustment parameter, while another oversees the parameters housed in the Qualifier palette. To reveal a node's keyframing tracks:

- Click the disclosure triangle beside the number of whichever node you're keyframing.

To keyframe an individual keyframing track manually: 1 Apply whatever tweaks the active node needs, then click its disclosure triangle so its keyframing tracks appear. 2 In the Keyframe Editor, move the playhead to the spot the first keyframe should occupy; now right-click within the keyframing track you mean to animate and choose Add Static Keyframe or Add Dynamic Keyframe (a Dynamic keyframe is used for illustration here). On that keyframing track, a keyframe materializes right where the playhead sits. 3 In the Keyframe Editor, advance the playhead to wherever the following keyframe should land. Right-click inside that same keyframing track once more, picking either Add Static Keyframe or Add Dynamic Keyframe (a Dynamic keyframe is shown for this illustration).

Keyframing only the Circular Power Window by way of its own dedicated keyframe track Now you're free to make whatever changes the controls overseen by the keyframing track you keyframed require, building the animated effect you need. TIP: Individual keyframing tracks can also be animated through automatic keyframing, which gets covered more fully further along in this chapter.

### Corrector Keyframing Tracks

Every parameter that governs color and contrast control adjustments, plus assorted effects, Power Windows, and other tweaks, gets organized into various sub-tracks living within the Corrector track.

- Linear Win: Controls parameters corresponding to the Linear window.
- Circ Win: Controls parameters corresponding to the Circular window.
- Polygon Win: Controls parameters corresponding to the Polygon window.
- PowerCurve: Controls parameters corresponding to the PowerCurve window.
- Gradient Win: Controls parameters corresponding to the Gradient window.
- Color Corrector: Controls all parameters found in the Camera Raw, Color Wheels,

Primary Controls, RGB Mixer, and Curves palettes.

- Qualifier: Controls all parameters in the Qualifier palette.
- Defocus: Controls all parameters in the Blur and Key palettes.
- NR: Controls the Spatial and Temporal Noise Reduction and Motion Blur parameters

found in the Motion Effects palette.

- Open FX: Governs every parameter belonging to whatever OFX plugin sits on the active node.
- Node Format: Governs every parameter of the Sizing palette's node sizing mode tied to

the current node.

### ResolveFX Keyframe Tracks

Within the Color page, the Color Page Keyframe Editor can display and edit keyframes for ResolveFX and OpenFX plugins in either of two ways:

- Plugins dropped onto a Corrector node turn up inside the nested list of keyframe tracks living under that node's top-level keyframe track.

The keyframe track belonging to a Resolve FX plugin placed on a Corrector node

- Plugins dropped in as standalone nodes turn up inside a fresh FX track of the Keyframe Editor. Every plugin added as its own separate node carries a separate FX track.

The keyframe track belonging to a Resolve FX plugin set up as a standalone node

### The Sizing Keyframing Tracks

Separately from the color controls, the Sizing keyframing tracks handle sizing transforms along with stereoscopic adjustments.

- Input Sizing: Controls the Input Sizing parameters found within the Sizing palette.
- Convergence: Controls the Convergence parameter in the Stereo 3D palette.
- Float Window: Governs the Floating Windows parameters for Left, Right, Top, and Bottom Position/Rotate/Softness.

- Auto Align: Governs, within the Stereo 3D palette, the Pitch and Yaw parameters.

TIP: Keyframing Output Sizing is possible only once you select Timeline mode over in the Node Editor.

### The Ext Matte Node's Freeform Isolation Track

When your node tree holds an External Matte, the EXT MATTE node surfaces a Freeform Isolation track inside the Keyframe Editor. That comes in handy for time offsets or for Sizing repositioning applied to the Ext Matte image.

### Automatic Keyframing

An Auto-Keyframing button sits on every track in the Keyframe Editor, switchable on or off. With auto-keyframing turned on for a given track, each tweak made to a parameter or control belonging to that keyframe track spawns a keyframe on its own. You can put this to work in two ways:

- Paired with a keyframing track, auto-keyframing makes setting up animated changes to particular adjustments inside a node a breeze. That beats dropping keyframes one at a time by hand.
- Alternatively, switching on auto-keyframing for the Corrector track turns it on across every keyframing track that node owns. In that scenario, keyframes drop automatically onto whichever keyframing track matches the parameters or controls you tweak.

### Auto-keyframing selected for Circular window on Node 1

While auto-keyframing is off, the tweaks you make revise existing keyframes instead. How that revision plays out hinges on where the playhead sits and on the keyframe types present in the Keyframe Editor. The next section covers more.

### Modifying Keyframes

After you begin laying down keyframes to animate a grade's changes, plenty of approaches exist for navigating and editing those keyframes to refine the effects further. This section walks through the various ways to move among, change, and delete keyframes.

### Navigating Among Keyframes

Many actions require parking the playhead squarely over the keyframe you mean to modify. You can always rely on the transport controls or the pointer to shift the playhead, but commands also exist for leaping straight to a particular keyframe. To move the playhead among a series of keyframes:

- Choose Playback > Next > Keyframe, bound to the right bracket key, or its counterpart Playback > Previous > Keyframe on the left bracket key.

### Moving Keyframes

When the timing of a keyframe run needs adjusting, you can relocate any keyframe and carry whatever values it holds along with it. To move a single keyframe using the onscreen interface:

- Drag any keyframe to a different spot with the pointer.
- Drag keyframes on a top-level Corrector or Sizing track to shift, all at once, every other keyframe sharing that frame within that corrector.

To move multiple keyframes at the same time: 1 If needed, open the keyframe track holding the keyframes you intend to move. 2 Draw a bounding box around the keyframes you want to move. The selected keyframes turn red to show they're chosen. 3 Drag any of the selected keyframes to slide them leftward or rightward.

### Changing Keyframe Values

Unlike a lot of other software, DaVinci Resolve permits altering keyframe values even while the playhead isn't sitting right on an existing keyframe. The behavior depends on where the playhead is relative to the keyframes present in the Keyframe Editor, and on which keyframe type you're working with.

- When the playhead sits left of, or right on, the first Dynamic keyframe: whichever Dynamic keyframe lies at or rightward of the playhead picks up the newly adjusted values.
- When the playhead sits left of, or right on, the last Dynamic keyframe: whichever Dynamic keyframe lies at or leftward of the playhead picks up the newly adjusted values.
- When the playhead falls between a pair of Dynamic keyframes: the Dynamic keyframe leftward of it absorbs the new values, leaving the one rightward unaffected.
- When the playhead falls between a pair of Static keyframes (marks): any tweak made there always lands on the keyframe leftward of the playhead. Everything from that keyframe up to the following one shifts together.

### Changing Dynamic Attributes

Out of the box, the move from one Dynamic keyframe to the next runs linear. Should you need to reshape how value interpolation speeds up between one Dynamic keyframe and the one after it, though, the dynamic attributes of that keyframe can be edited. Here's how to edit them: 1 In the Keyframe Editor, select a keyframe by clicking it. 2 Right-click the keyframe you selected, then choose Change Dynamic Attributes. 3 Once the Dynamic Attributes window opens, take either or both of these actions:

- Set a fresh outgoing acceleration curve via the Start slider, which shapes the interpolation happening on that keyframe's right.
- Set a fresh incoming acceleration curve via the End slider, which shapes the interpolation happening on that keyframe's left.

As you try out different acceleration curves, the display on the right updates with the resulting curve graph.

Changing the dissolve profile 4 Once the curve satisfies you, click OK. Mixing varied Start and End values lets you make animated adjustments "ease in" or "ease out" around a given keyframe, producing a softer or sharper transition. TIP: Each new keyframe's default dynamic profile start and end are configurable using the Dynamics Profile values, found under Project Settings within the General Options panel.

### Deleting Keyframes

You may remove keyframes one by one, or wipe out every keyframe inside a particular grade in one go. To delete individual keyframes, do one of the following:

- Park the playhead over the keyframe you want gone, then choose Mark > Delete Keyframe (Option-]). Every keyframe sitting at the playhead's position is removed.
- Using the pointer, select a keyframe over in the Keyframe Editor by clicking it; next, right-click on that keyframe and pick Delete Selected Keyframe. Only the keyframe you chose disappears.

To delete every keyframe for the current clip:

- Choose Mark > Delete All Keyframes.

### Copying Keyframes

You can duplicate a batch of keyframes from one node onto another, whether inside the current grade or over in an entirely different clip. Copying a whole grade complete with keyframes from one clip to another is also doable. To copy a set of keyframes from one node to another: 1 Pick a node to copy keyframes from, then choose Edit > Copy (Command-C). 2 Do one of the following:
