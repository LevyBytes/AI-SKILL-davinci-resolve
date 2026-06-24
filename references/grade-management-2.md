# Grade Management (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

When you want to be completely certain no other grade can stand in for the one a clip carries, there's a quick path to wipe every version but the one in use, which then becomes the default. To clear either local or remote versions while sparing the current one: 1 Pick the local or remote version you want the clip to keep. 2 Right-click the thumbnail of the clip you're trimming versions from and pick Delete Unused Versions from the contextual menu. Had you picked a local version, every unused local version goes while remote ones stay; pick a remote version and the unused remote ones go while the local ones stay.

To clear all the other local and remote versions but the current one: 1 Pick the version you want the clip to keep. 2 Right-click the thumbnail of the clip you're trimming versions from and pick Delete All Versions from the contextual menu. No matter whether you picked a local or a remote version, every other local and remote version not in use is removed.

### Rendering Versions

Once you reach the Deliver page to render clips, whatever version each clip currently has selected is the one rendered. To render a different version for some clip, either confirm it's the selected one in the Color Page timeline before opening the Deliver page, or reach for the Versions submenu within the Color mode of the Deliver page Thumbnail timeline. That contextual menu likewise reaches the Stereo 3D commands, plus the Edit PAR (Pixel Aspect Ratio) command, along with one for refreshing the Render Window Timeline thumbnails so your recent changes show, in case they didn't refresh on their own. On top of that, the Deliver page's Commercial Workflow output option offers a way to render several versions per clip when your project goes out in Source Order (as individual media files). Two further options sit in the Version submenus of each Thumbnail timeline clip's contextual menu, governing which versions render under Commercial Workflow. Render Disabled: Switch this on and that version is left out of the render while Commercial Workflow is active. Enable Flat Pass: Switch this on and the chosen version renders with its grade off, so essentially the original media is what comes out. To read more about rendering versions through the Commercial Workflow option, consult “Rendering Media” at Chapter 187.

### Copying Grades

Several techniques exist for copying grades between clips, and the right one for you comes down to how you like to work in DaVinci Resolve.

### Protecting Adjustments with the Copy Grade Options

Ahead of the many ways grades travel from clip to clip, it helps to know about a set of options reached from the Gallery's contextual menu (right-click anywhere in the Gallery's gray area) that let you spell out exactly which grading, sizing, and stereo data survive when you overwrite grades on the clips you copy to. Three options exist: Copy Grade: Preserve number of nodes: Lets you set 0–10 nodes to shield while a grade is applied. At 1, the copied grade's first node is skipped while the rest carry over. At 5, the first five nodes of the copied grade are skipped, provided the clip you're copying to already holds at least five nodes. The option suits colorists who habitually devote the opening nodes to shot matching and scene balancing, leaving later nodes for individual or stylistic touches.

Copy Grade: Preserve Camera Raw Settings: Switch this on and the current clip's camera raw Source settings hold firm, so you can borrow stylistic grades from unrelated clips without trampling clip-specific source settings. Copy Grade: Preserve Input Sizing: Switch this on to keep Input Sizing adjustments safe from the copied grade's own. Copy Grade: Preserve Convergence: Switch this on so the Stereo 3D palette's Convergence adjustments stay put rather than yielding to the copied grade's. Copy Grade: Preserve Floating Windows: Switch this on so the Stereo 3D palette's Floating Windows adjustments aren't replaced by the copied grade's. Copy Grade: Preserve Auto Align: Switch this on so the Stereo 3D palette's Auto Alignment adjustments survive the copied grade. Copy Grade: Preserve Dolby Vision™ Analysis Metadata: Switch this on to keep the Dolby Vision Analysis Metadata clear of the copied grade's. It's only there once you're configured for Dolby Vision grading. The relevant background sits in “Data Levels, Color Management, and ACES,” which is Chapter 9. Copy Grade: Preserve Dolby Vision™ Trim Metadata: Switch this on to keep the Dolby Vision palette's Dolby Vision Trim Metadata clear of the copied grade's. It too only appears when you're configured for Dolby Vision grading. Again, Chapter 9 — “Data Levels, Color Management, and ACES” — has the fuller picture.

### Copy and Paste From One Clip to Another

Reaching for the very same Edit > Copy and Paste commands found in nearly every application ever built is the easiest route to lifting color adjustments off one clip and dropping them onto another. That plain functionality works one of two ways, though, depending on where the interface focus sits.

- Click the clip over in the Thumbnail Timeline and you carry the whole grade from one clip to the next.
- Click inside the Node Editor and only the selected node moves across to another selected node.

You can override this focus-driven behavior so that, no matter where the interface focus lands, copying defaults to node-to-node rather than whole grades. To do so, tick the “Always perform copy and paste on selected nodes” box found in the Color section of the User panel in Preferences.

Methods of copying and pasting grades and node adjustments.

- To copy and paste an entire grade: Pick a clip whose grade you want and press Command-C. Then, in the Thumbnail Timeline, select the destination clip and hit Command-V to drop the full grade in.
- To copy and paste a single node: Pick a clip whose node you want and press Command-C. Then select the destination clip in the Thumbnail Timeline, click anywhere within the Node Editor, and hit Command-V to paste the node you had selected at copy time onto the node currently selected in the node tree.

### Copy and Paste Specific Parameters Using Paste Value

With the Edit > Paste Value (Shift-Option-V) command you can drop only one parameter's value into another clip's node. To paste just a single value: 1 Select a Corrector node carrying the parameter you want and press Command-C to copy. The whole grade is what you actually copy, but that's fine. 2 Move to any other node in any grade and open the palette that holds the parameter you'll paste into. 3 Double-click the number field of the exact parameter that should receive the copied value. 4 Pick Edit > Paste Value (Shift-Option-V) to drop that value in. NOTE: Paste Value applies only to parameters inside palettes; it has no effect on OFX or Resolve FX over in the Inspector.

### Applying Saved Grades From the Gallery

Each still you stash in the Gallery or a memory carries both the Clip grade and, where one exists, the Timeline grade. Which of those a still applies through the Apply Grade or Append Node Graph commands hinges on the Node Editor's current mode, picked from the drop-down at the Node Editor's top-right corner.

### Node Editor Clip and Track selector

In Clip mode you pick up only the saved clip grade; in Timeline mode you pick up only the saved timeline grade. NOTE: The same mechanism covers saving and applying grades for clips that belong to Groups. Whichever group grade is active in the Node Editor decides which grade a still stores, and whichever mode is active in the Node Editor decides where a saved grade lands.

### Preparing to Copy or Apply Grades

For every other way of copying or applying grades laid out in this chapter, a handful of shared controls dictate how the adjustments from your source clip or still reach the destination clip. Picking the part of a grade that applies through All/Color/Sizing No matter which technique in this section you use to apply grades, the All/ Color/Sizing setting is on hand through the Mark > Keyframe Timeline Mode submenu — the dropdown over at the Keyframes Editor's upper-right. Copy a grade alongside this menu's settings and these rules hold:

- All: Pick All and both the grade and the sizing come across.
- Color: Only the grade transfers; the target clip keeps its own Input Sizing settings.
- Sizing: Only the Input Sizing transfers; the target clip keeps its own grade.

### Choosing How to Copy Keyframes

When the grades you copy or apply carry keyframes, you decide how those keyframes travel via a setting in the Gallery contextual menu — right-click anywhere in the Gallery's gray background and pick one of the choices in the Apply Grades Using submenu. Three choices await:

- No Keyframes: Nothing is copied keyframe-wise. The grade's state at the frame where the still was saved is what reaches the target clip or clips.
- Keyframes Aligning Source Timecode: The keyframes come across with the saved grade's source timecode matched up against the target clip's source timecode. It's the setting you want when returning a grade to the clip it first came from, or to a duplicate of that clip elsewhere on the Timeline, so the keyframes sit on the same frames as before. Where no source timecode overlaps, the keyframes paste against the edit's start frame instead, just like the third choice below.
- Keyframes Aligning Start Frame: The keyframes come across with the start frame of the clip the still was saved from matched against the target clip's start frame. It's the setting you want when carrying a keyframed grade from one clip onto an entirely different clip whose timecode differs.

From there on, any keyframes that exist get copied or applied by the chosen method whenever you copy a grade through any of the techniques described earlier.

### Copying Grades Using the Pointer

A remarkably quick route for moving a grade between clips — or from a Gallery still or memory onto a clip — is your mouse's third button, typically the “middle‑click” of the scroll wheel. To copy a grade from a clip or still onto one or more clips with the pointer: 1 In the Timeline, select the clip thumbnail meant to receive the grade; a lone selected clip glows orange. To target several clips, Command‑click various non-adjacent ones or Shift-click an unbroken run of them, and those multiple selected clips glow red. 2 Middle-click the clip thumbnail, Gallery still, or memory whose grade you want to lift.

Whatever clip you middle-clicked has its grade copied onto the clip or clips you'd selected beforehand. TIP: On a trackpad, third-party software might let you set up a “three‑fingerclick” acting as mouse button 3. Pen-and-tablet or trackball users may likewise assign a stylus or other button to the same button-3 action. Lacking a middle-click on your pointing device, a contextual menu command offers another way through. To copy a grade from a clip or still onto one or more clips via the Apply Grade command: 1 In the Timeline, select the clip thumbnail meant to receive the grade; a lone selected clip glows orange. To target several clips, Command-click various non-adjacent ones or Shift-click an unbroken run of them, and those multiple selected clips glow red. 2 Right-click the clip thumbnail, Gallery still, or memory whose grade you want, then pick Apply Grade from the contextual menu. Whatever clip you middle-clicked has its grade copied onto the clip or clips you'd selected beforehand.

### Copy Forward Commands

Yet another easy approach uses the equals (=) and minus (–) keys to pull a grade forward from one or two clips back of the one currently selected. It works beautifully in shot-reverse-shot scenes, where you cut between two coverage angles that share the same grade. To copy grades forward:

- To pull a grade forward from the clip one back: use the Color > Apply Grade From One Clip Prior menu item, or just press Equals (=).
- To pull a grade forward from the clip two back: use the Color > Apply Grade From Two Clips Prior menu item, or just press Minus (–).

### Copying Using Memories

Memories are all but the same as stills, save that each one wears a letter (A–Z) for quick recall through keyboard shortcuts. A memory bank above the Gallery browser shows at a glance which saved grade is tied to which letter. That keeps a pile of saved memories straight when you're spreading them across many clips throughout a scene or program. You might, say, stash a memory per coverage angle in a knotty scene so grades copy forward effortlessly. Or you might stash a memory holding the grade on each interview subject's headshot in a documentary, then copy that grade forward as the documentary unfolds. To stash the current clip's grade in a memory for later, do one of the following:

- Choose Color > Memories > Save Memory A–H (Option-1–8).

Save a grade into a memory that's already occupied and the old memory is overwritten.

To drop a memory onto one or several timeline clips, take any of these routes: 1 Over in the Thumbnail timeline, choose the destination clip or clips — the current one, or a range gathered through Command-Clicking or Shift-Clicking. 2 Then copy a grade onto the selected clips one of these ways:

- Right-click a memory and choose Apply Grade.
- Choose Color > Memories > Load Memory A–H (Command-1–8).

To clear a memory:

- Right-click a memory, then choose Clear.

### Copying Using Preview Memory

You can also trial a memory or saved grade on the current clip, then keep it if it lands or fall back to the prior grade if it doesn't. To Preview Memory: 1 Park the playhead on the clip where a memory is to be trialed. 2 Pick Color > Preview Memory (Option-Shift-P). 3 Take one of these routes:

- Right-click any saved still in the Gallery and choose Apply Grade.
- Choose Memories > Load > Memory A–H (Command-1–8). Your chosen grade or memory is now showing as a preview. 4 Now, take one of these two paths to accept or reject the memory:
- Pleased with the look? Leave it be and move along to the next clip.
- Unconvinced? Choosing Color > Preview Memory (Option-Shift-P) once more rolls

the clip back to its original grade.

### Copying from Stills in the Gallery

As noted earlier, every still kept in the Gallery holds the grading information together with a picture of the frame it was grabbed from. That saved grade can land on any Timeline clip. IMPORTANT: A copied grade overwrites whatever grades already sit on the clip or clips you copy onto. To drop a still's grade onto one or several selected timeline clips: 1 Over in the Thumbnail timeline, choose the destination clip or clips — the current one, or a range gathered through Command-clicking or Shift-clicking. 2 Then copy a grade onto the selected clips one of these ways:

- Drag the still out of the Gallery and into the Viewer.
- Right-click a still in the Gallery and choose Apply Grade.
- Middle-click a still in the Gallery.
- Double-click a still so it wipes against the current Timeline clip inside the Viewer, then right‑click

the Viewer and pick whichever entry you need from the Apply Grade submenu.

### Append Node Graph

A saved grade can also be appended to any timeline clip. Doing so tacks the saved still's whole node graph onto the tail of the current clip's node tree. Put differently, the current clip's grade survives intact and the applied grade simply joins on at its end. With a little forethought you can stash partial grades that pull off specific effects or adjustments out of just a handful of nodes. Those fragments then become a toolkit you bolt onto other grades to mix and match assorted adjustments and effects. You might, for instance, build a three-node glow effect, save it, and later drop that effect onto the end of an entirely different clip's grade.

### Appending grades places them after the original nodes

To tack a saved grade or memory on as separate nodes, take either route:

- Drag a still or memory out of the Gallery onto a connection line within the Node Editor; once the plus icon shows, let go and its nodes append into the node tree beginning at that connection.
- In the Gallery, right-click a still or memory and pick Append Node Graph. Normally, appending a memory or still's node graph onto another node graph dumps a whole pile of fresh nodes in. That may be precisely what you're after, yet when you'd rather keep things tidier, you can instead append node graphs as compound nodes.

To append a saved grade or memory as a compound node:

- Command-drag a still or memory out of the Gallery onto a connection line within the Node Editor; once the plus icon shows, let go and its nodes append to the node tree as one compound node.

NOTE: When you append a gallery still's nodes onto a grade, how the keyframes land depends on the Gallery's “Apply Grades Using” setting. For more information, see Chapter 141, “Using the Gallery.”

### Aligning Keyframes to a Specific Frame While Copying Grades

When you need a keyframed grade copied so its opening keyframe sits on one particular Timeline frame, the steps below get you there: To copy a grade and pin its keyframes to a specific Timeline frame: 1 Right-click the Viewer, choose Grab Still, and a keyframed grade is stashed as a Gallery still. 2 In the Thumbnail timeline, pick the clip that should receive the saved grade. 3 Double-click the Gallery still to wipe it in the Viewer against the current clip. 4 Park the playhead on the frame of this clip where you want the saved grade's first keyframe to fall. 5 Right-click in the Viewer and walk through Apply Grade > Align Keyframes to Current Frame.

### Copying Individual Nodes and Settings

Copy a grade between clips and everything transfers but the keyframes and motion tracking. There is, though, a single way to bring motion tracking from one clip to another: by copying and pasting individual node settings. The trick saves time while you assemble intricate node trees, since you can reuse particular nodes or node settings drawn from earlier grades.

### Copying and Pasting All Settings From One Node to Another

The most basic move is to grab all of one node's settings and drop them onto another node. That makes it painless to clone things like windows, qualifier settings, keyframing, or motion tracking you want to reuse in another node as the footing for a fresh operation. It's also a fast manual way to ripple a change made in a node out to that same node within another clip's grade. To shift a node's settings across from clip to clip, take either route:

- Option-drag one node atop another. On release, the dragged node's settings overwrite those of the node you dropped onto.
- Pick a node whose settings you want and choose Edit > Copy (Command-C). Then pick a destination node — in the current grade, in another clip's grade, or a node you create fresh — and choose Edit > Paste (Command-V) to lay the copied settings in. The pasted node settings replace whatever that node held before.

### Paste Attributes on the Color Page

You can lift one node's settings and paste only a portion of them onto another selected node through Edit > Paste Attributes (Option-V). Up comes a Paste Attributes window that names the node you're copying from and the node you're pasting to, and hands you controls for whether keyframes should paste and how they line up (Start Frames or Source Timecode), plus a row of checkboxes picking which palettes, windows, and OFX/ResolveFX you want

to apply. A given palette pastes only in full; there's currently no facility for pasting individual parameters from inside a palette, the lone exception being specific windows along with their attached trackers.

### The Paste Attributes window on the Color page

### Copying from the Node Graph of Other Clips or Gallery Stills

As you build new grades, it can pay to lift existing nodes or node settings from another clip's grade or a gallery still. That's straightforward: expose the node tree of any still saved in the Gallery, or of any clip in the Thumbnail timeline, then use the floating node graph's controls to copy individual nodes or node adjustments onto the current clip's grade displayed in the Node Editor.

### Copying Clip Settings Using Display Node Graph

While in Clip mode, the floating Node Graph window gives you four control sets for deciding how nodes and adjustments copy:

- Clip Node Graph: The Clip node graph sits on the left by default. Drag any node out of the floating node graph onto the current grade shown in the Node Editor, dropping it on an existing node to overwrite that node's settings or on a connection line to slot it in as a new node.
- Timeline Node Graph: (Available only where a Timeline grade exists) Jump to a Timeline grade, when one is present, either by clicking the second title-bar button on the Node Graph or by choosing Timeline from the drop-down at the floating Node Graph window's top-right corner.
- Apply Color/PTZR/Source/All buttons: With the Clip panel active, four buttons let you copy across just the full grade, just the sizing, just the source settings, or everything at once onto the current clip.

Dragging one node out of another clip's node graph onto the grade of the clip currently selected in the Node Editor Copying Node Settings Using Display Node Graph While in Node mode, the floating Node Graph window lays out every Color Attribute living inside each node in place of the Apply Color/PTZR/Source/All buttons:

- Node Settings: The checkboxes let you mark which node adjustments copy and which stay behind. With the settings you want ticked, dragging a node from the floating node graph onto Node Editor nodes copies or appends only the marked attributes into the target node and leaves the rest untouched. For Windows and OpenFX, you can additionally bring along any motion tracking on offer.

The Node panel showing, with the Color Corrector and Blur attributes ticked for copying

Ability to Open Compound Nodes in “Display Node Graph” After right-clicking a Gallery still or thumbnail and choosing Display Node Graph for a grade built on compound nodes, right-click any compound node and pick “Show compound node” — or Command-double-click that compound node — to crack it open and view the individual nodes inside.
