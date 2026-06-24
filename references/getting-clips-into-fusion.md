# Getting Clips Into Fusion (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Getting Clips into Fusion

As you assemble your compositions, this chapter walks through the several routes for bringing clips into Fusion.

### Preparing Compositions in the Fusion Page

Most of the time, a clip reaches the Fusion page from the Edit or Cut page Timeline either on its own or as several layers wrapped inside a Fusion clip. Clips can also be dropped into a composition straight from DaVinci Resolve’s Media Pool. The route a clip takes into a Fusion composition can shape both how it behaves there and the resolution that composition hands back to the rest of DaVinci Resolve.

### Working on Single Clips in the Fusion Page

Set the playhead above a clip on the Edit or Cut page Timeline, press the Fusion page button, and that clip appears on the Fusion page as one MediaIn node wired to a MediaOut node. Fusion only pulls in the topmost visible clip. Any clip hidden because it sits on a lower track beneath others is skipped, unless you switch off the clips or tracks stacked above it. This manual informally calls these bare-bones default setups “single-clip compositions.” The MediaIn node stands for the picture handed to the Fusion page for more work, while the MediaOut node stands for the finished output passed along to the Color page for grading.

The default node tree shown the moment you open the Fusion page with the playhead resting on a clip. With this starting node layout, it’s simple to jump quickly onto the Fusion page and build fairly basic effects by leaning on the procedural freedom of node-based compositing. Say you have an establishing shot with no camera move that needs a touch of quick paint to hide some stray junk in the background; you can open the Fusion page, drop in a Paint node, and use the Stroke tool’s Clone mode to paint it away fast.

A basic paint pass laid over a static shot that has no camera move. TIP: When a single clip is pulled into Fusion through the Edit or Cut page Timeline, its resolution is that of the source clip rather than the Timeline resolution.

When you’re done, just return to the Edit or Cut page and keep cutting, since the whole Fusion composition stays bundled inside that clip, much the way Color page grades are also bundled inside a clip. Whether that clip gets slipped, slid, rippled, rolled, or resized, the Fusion effects you built along with the Color page grades you applied travel with it wherever it lands across your edited Timeline. TIP: Although you’ll generally want to handle all the compositing for a greenscreen-style effect on the Fusion page, you can also drop a keyer, like the superb DeltaKeyer node, on its own between the MediaIn and MediaOut nodes. Pulling a key this way attaches the alpha channel to the MediaOut node, so your clip on the Edit page gains transparency, which lets you put a background clip on a lower track of your Edit page Timeline.

### How Nodes Are Named

Even though the documentation calls nodes by their plain name, like “MediaIn,” the real node names in the Fusion Node Editor carry a number on the end, so you can tell one apart from another whenever several copies of the same node type are present.

### Turning One or More Clips into Fusion Clips

When you already know you’re building a more elaborate composited effect that needs several layers cut together with exact timings, you can spin up a “Fusion clip” straight off the Timeline. For instance, given a foreground greenscreen clip, a background clip, and one more graphic clip, you can pile them all onto the Timeline as superimposed clips. From there the Edit page slip and slide features let you line up their timings so they work together however you need. You can likewise cut several back-to-back clips together that you mean to use in a composition as a string of clips. With that done, you can select every clip in the stack to build a Fusion clip, making it simple to draw on all these layered tracks inside a Fusion composite. To create a Fusion clip: 1 Cut every clip you intend to use into the Edit page Timeline. 2 Highlight, all at once, each clip you want in the same composite. 3 Right-click any one of the highlighted clips and pick New Fusion Clip off the contextual menu. 4 A fresh clip called “Fusion Clip X” (with X being a number that climbs automatically) shows up in the Media Pool’s currently selected bin and on the Timeline, taking the place of the clips you had selected. 5 Rest the playhead above that clip and open the Fusion page to view how those clips are now laid out in the Fusion page Node Editor.

A pile of clips destined for a composite (Top), with that pile converted into a Fusion clip on the Edit page (Bottom). What’s great about building a Fusion clip is that every layered clip in a stack gets wired automatically into a cascading chain of Merge nodes that produce the layout of clips you want. Keep in mind that whichever clips sat at the bottom of the stack on the Edit page show up at the top of the Node Editor on the Fusion page, yet the layout of background and foreground input connections is set up to rebuild the very same compositional order.

The starting node tree built from the three clips we converted into a Fusion clip.

TIP: Fusion clips switch the working resolution of the individual clips so it lines up with the Timeline resolution. Say two 4K clips are layered one above the other in an HD Timeline; building a Fusion clip drops the clips down to HD. Fusion won’t give you the full resolution of the individual 4K clips. To keep the full resolution of source clips, take just one clip into the Fusion composition off the Edit or Cut page Timeline, then pull the rest into the Fusion composition through the Media Pool.

### Fusion Referenced Compositions

A newer, capable approach to putting Fusion composites on your clips goes by the name “Referenced Composition.” With this approach you can recycle your work across many clips or even across timelines. You build a referenced composition on the Edit page by picking one clip, or a stack of clips, then choosing “Create Referenced Composition” from the contextual menu. Doing so spawns a Fusion Referenced Composition in the Media Pool. You can step into the Fusion page and begin compositing, or give the Referenced Composition in the Media Pool a double-click to open it. To link referenced comps to other clips in any timeline, select the referenced comp, then right-click the target clip and pick “Link to Referenced Composition.” Whatever edits you make spread to every connected clip, because they’re all “referred” or “linked” to that one composition. Referenced Compositions offer a reliable, safe way to keep your work backed up and tidy, since they sit in the Media Pool and stick around even after the original referenced clip is removed from the timeline.

### Creating and Managing Referenced Compositions

To create a Referenced Composition: 1 Pick one or more timeline clips that sit “stacked” across tracks in an Edit window timeline (the clips must overlap in time at least to some degree). 2 Right-click and choose “Create Referenced Fusion Composition.” 3 The fresh reference composition, tied to the top selected clip, now turns up in the Media Pool. Double-clicking it in the Media Pool opens the referenced composition on the Fusion page. The Media nodes line up with where the source track clips sat relative to one another in the Edit timeline. Whatever the video track holds is handled as a source, so clips can be shaped creatively before they head onward to Fusion for compositing. Right-clicking a referenced composition in the Media Pool and picking the Usage option lets you survey and jump to its target linked clips. For iterating, you can also duplicate your referenced composition. The example that follows builds a basic reference composition from three clips, swapping out a logo on a truck.

Building a reference composition by picking several overlapping clips, then choosing Create Referenced Composition off the contextual menu.

### The Reference Composition thumbnail in the Media Pool

A double-click on the Reference Node takes us into Fusion, where we drop in a few Corner Positioner nodes to align the green stripe and logos so they fit.

With the referenced composition now in place, swapping the logo is easy; we just run a replace edit putting the new logo onto V3 in the timeline. That fresh logo is applied to the Fusion comp on its own, carrying the same settings.

### The sBSpline controls

### Adding Additional Referenced Clips

Once a referenced composition is established, you can hook on clip(s) that lean on the referenced composition to act on the other clips. To add clip references to a referenced composition: 1 Pick the referenced composition you’d like to tie to another clip. 2 Pick a target clip on the timeline, then right-click and choose “Link to Referenced Composition.” 3 Bring in further clips, one at a time if you prefer, drawing even from other timelines.

### Referenced Composition Behaviors and Rules

A handful of extra behaviors and rules are worth knowing when you put referenced compositions to use.

- Referenced compositions maintain the original source resolution of your clips.
- When you pick several clips, make certain each one shares some overlap with the top selected clip.

Lacking that overlap, the context menu command for building a referenced composition across layers won’t be offered.

- Make a project composition out of several overlapping clips and you get one composition tied to the top selected clip.
- The referenced composition brings along extra Media In nodes (one for each track). Media In 1 points to the top selected clip. The Media In nodes after it point to timeline tracks (layers) sitting beneath the top clip.
- Deleting a timeline clip leaves the composition it was tied to intact.
- Edit what sits inside a referenced composition’s track, and the matching Media In updates on its own to surface the new clips, edits, effects, and transitions.

From the timeline clip’s context menu, you can:

- Reset Reference Composition: To reset the composition. This affects all referenced clips.
- Unlink Reference Composition: Strips the composition reference off the selected clip. The composition stays put in the Media Pool, yet the clip’s effect is wiped. Handy when you mean to link to a different referenced composition.
- Find Reference Composition in Media Pool: Locates, within the Media Pool, the reference composition this clip belongs to.

NOTE: Referenced compositions don’t support clips that run at different frame rates or clips carrying speed changes.

### Adding Fusion Composition Generators

A Fusion Composition generator lives in the Generator category of the Edit page Effects Library. It’s handy for dropping an empty placeholder onto the Timeline that you plan to flesh out afterward on the Fusion page into a fuller Fusion composition. Here’s how to make a blank Fusion clip over on the Edit page: 1 Open the Effects Library and pick the Effects category. 2 Cut a Fusion Composition clip into the Timeline by whatever route suits you best. a) Drag a Fusion Composition clip onto the Timeline and you’ll get a clip running as long as the “Standard generator duration” preference, which defaults to 5 seconds. b) Or set In and Out points on the Timeline and drag the Fusion Composition clip onto any of the Timeline viewer’s editing overlays to carry out that kind of edit, inserting, overwriting, “place on top,” or ripple overwriting it into a particular spot on the Timeline for a particular length. 3 A fresh clip called “Fusion Composition” shows up on the Timeline. At first it reads as pure black in the Timeline viewer, being a blank composition holding nothing. 4 Rest the playhead above that clip and open the Fusion page. Because this composition is empty, the Node Editor holds nothing but one MediaOut node. From here, you can drop in whatever media, generators, and other effects you need.

### Creating a Fusion Composition Clip in a Bin

Inside any bin of the Media Pool you can spin up an empty Fusion Composition clip without ever making a Timeline. This route can be handy for building motion graphics or titles when no Timeline exists or when you expect to reuse the clip across several Timelines. To create a blank Fusion Composition clip in a bin: 1 Pick the Media Pool bin where you’d like the Fusion Composition saved. 2 Right-click an empty spot in the bin and pick New Fusion Composition. 3 Inside the New Fusion Composition clip dialog, fill in a Name for the clip, a duration, and a frame rate, then press Create. 4 The clip turns up in the bin. To open it in Fusion, take one of these routes:

- Double-click the Fusion Composition
- Right-click the Fusion Composition clip and pick Open in Fusion Page

### Resetting a Fusion Clip

To send a Fusion clip back to how it started out, right-click the Fusion clip on the Edit page Timeline and pick Reset Fusion Composition. You’re free to select several Fusion clips and reset them all in one go.

### Using Fusion Transitions

Certain Fusion transitions can be found in the Edit page Effects Library. With these transitions you can carry two clips plus the transition joining them into the Fusion Page. From there the transitions can be reworked and saved back onto the Edit page Timelines, or saved as a fresh, reusable Fusion Transition that turns up in the Edit Page Effects lIbrary. Here’s how to apply one and open it: 1 Open the Effects Library and pick the Video Transitions category. 2 Scroll down to the foot of the transition list, then drag any one of the Fusion Transitions onto a Timeline cut. 3 Right-click the Fusion Transition on the Timeline and pick Open in Fusion Page. 4 The Fusion page opens carrying two MediaIn nodes that stand for the two halves of the transitions. Those MediaIn nodes feed into a cross dissolve or a cluster of nodes that build the transition. From here you can rework the transition with masks or other nodes, then head back to the Edit page to view the outcome.

A Noise Dissolve Transition opened in the Fusion page.

To learn how to build your own custom Fusion Transitions that appear in the Effects Library, turn to Chapter 68, “Node Groups, Macros, and Fusion Templates,” found in the DaVinci Resolve Reference Manual, or to Chapter 6 over in the Fusion Reference Manual.

### Adding Clips from the Media Pool

On the Fusion page you can open the Media Pool and drag clips right onto the Node Editor to slot them into your node tree. Dragging a clip into a blank spot of the Node Editor turns it into one more MediaIn node, left unconnected, sitting ready for you to merge into your current composite in any number of ways.

Pulling a clip out of the Media Pool (Top), then dropping it into your composition (Bottom). TIP: When you drag a clip from the Media Pool over a connection line joining two other nodes in the Node Editor, that clip is added as the foreground clip on a Merge node. As you bring in further clips from the Media Pool, those clips join the composition, much the way Ext Matte nodes you put into the Color page Node Editor become part of that clip’s grade.

### Audio with Media Pool Clips

By default, audio from a clip pulled in via the Media Pool is silenced. Getting that Media Pool clip’s audio to play takes two steps. To hear audio from a clip brought in through the Media Pool, proceed like so: 1 Pick the clip in the Node Editor. 2 Over in the Inspector, open the Audio tab and choose the clip’s name from the Audio Track drop-down menu. 3 On the toolbar, right-click the speaker icon, then choose the MediaIn belonging to the Media Pool clip to solo its audio. The speaker icon contextual menu now lets you flip back and forth among all the MediaIn nodes.

### Finding Clips in the Media Pool from the Node Editor

Elaborate Fusion Compositions may hold several MediaIn nodes to keep tabs on. You can pinpoint the exact clip in the Media Pool tied to a MediaIn node by selecting that node, then picking Clip > Find Clip in Media Pool (Option-F).

### Adding Clips from the File System

There’s also the option to drag clips out of the file system straight onto the Node Editor. Do that and they get added to the currently selected bin of the Media Pool on their own. So if you keep a library of stock animated background textures and have just tracked down the one you want with your file system’s search tools, you can simply drag it right onto the Node Editor and put it to use immediately.

### Using MediaIn Nodes

On the Fusion Page, the MediaIn nodes form the bedrock of every composition you build. This section goes deeper into the controls on hand for tuning MediaIn and Loader nodes.

### MediaIn Node Inputs

A MediaIn node carries a single Effects mask input plus a single output. Where the Effects mask input is concerned, attaching a mask node such as a Polygon or B-Spline node produces an alpha channel on the MediaIn node. TIP: Hook up a mask node with no shapes drawn and that mask puts out full transparency, so the picture the MediaIn node outputs comes out uselessly blank. If you mean to rotoscope over a MediaIn node, first make a disconnected mask node, then with that mask node selected (its controls showing in the Inspector) and the MediaIn node loaded in the viewer, draw your mask. Once you’ve closed the shape you’re drawing, you can wire the mask node into the MediaIn node’s input, and you’re set.

### Inspector Properties of MediaIn Nodes

Exactly which Inspector options show up for your composition’s MediaIn nodes hinges on the way you brought the media in.

### MediaIn Node Parameters for Clips in a Timeline

Build a composition from clips off the Edit page Timeline, and the MediaIn nodes for those clips show fewer parameters than ones imported straight from the Media Pool, since the timing of clips already cut into a Timeline is already locked in.

The parameters on the Inspector Image tab for a Timeline-sourced clip Image Tab

- Clip Name: Displays the name of that clip.
- Process Mode: Lets you decide whether the clip that node stands for is handled as

Full Frames, or through one of the named interlaced approaches.

- Media Source: With this control you pick where the media comes from; the three

choices on offer are: Timeline, Background, and Media Pool. Timeline: Ties the clip to the Edit Timeline (default). Background: This draws frames from the edit’s lower video tracks. Flip the Media Source over to Background and the composited result of every lower track becomes visible. Media Pool: Ties the clip straight to the Media Pool, skipping past the Edit Timeline.

- Layer: With Multilayer or Photoshop PSD files, this picks which layer inside the file gets used. On a Fusion Clip built from several video layers on the timeline, it instead points to each layer’s index number.

### Source Color Space

To support a linear workflow, the Color Space Type menu assigns the media’s color space. In contrast to the Gamut tool, it carries out no real color space conversion; instead it writes the source space info into the metadata whenever that metadata isn’t already there. Downstream, that metadata can then be picked up by a Gamut tool set to the From Image option, or by a Saver where explicit output spaces have been defined.

- Auto: Passes along any metadata that might be in the incoming image.
- Space: Lets the user choose the color space out of an assortment of options.

### Source Gamma Space

To support a linear workflow, the Curve Type menu works out, or lets you pick, the Gamma setting for the picture and offers the choice of stripping the Gamma curve away.

- Auto: Passes along any metadata that might be in the incoming image.
- Space: Lets you pick a particular setting from a Gamma Space drop-down menu, while a

visual graph shows you a depiction of the gamma setting you’ve picked.

- Log: Much like the Log-Lin node, this choice exposes particular log-encoded gamma profiles so

you can pick whichever one fits your content. A visual graph offers a depiction of the log setting you have chosen. Pick Cineon from the Log Type menu and, for fine-tuning the gamma output, extra options appear: Lock RGB, Level, and Soft Clip, plus Film Stock Gamma, Conversion Gamma, and a Conversion table.

- Remove Curve: Based on whichever gamma space is chosen, or on the gamma space turned up in Auto mode, the matching gamma curve is stripped off the material, in effect converting it so it outputs in a linear color space.
- Pre-Divide/Post-Mujltiply: When the need arises, lets you turn “straight” alpha channels into pre-multiplied alpha channels.

TIP: Everything on the DaVinci Resolve Fusion page is processed at 32-bit floating-point bit depth, no matter what the content’s real bit depth happens to be.

### Audio Tab

The MediaIn node’s Inspector holds an Audio tab, from which you can opt to solo just that clip’s audio or listen to every audio track on the Timeline.

### The MediaIn Audio tab

On the MediaIn node, the Audio tab is where you pick the playback track, slip the audio timing, and clear the audio cache If the audio falls out of sync during Fusion playback, the Audio tab’s Sound Offset wheel lets you nudge the audio in subframe frame increments. That slipped audio is changed only on the Fusion page. Every other page holds onto the original audio placement. Purging the Audio Cache The audio together with its settings is cached so things run faster. Whenever you alter which audio tracks you want playing in Fusion, or use the Sound Offset wheel to slip the audio tracks, you have to purge the audio cache. Likewise, going back to the Edit, Cut, or Fairlight page and changing the audio levels means you have to purge the audio cache. Whenever the audio playback shifts in any way, clear it by pressing the Purge Audio Cache button over in the Inspector. Your audio then refreshes the next time the composition plays back.

### Aligning Clips from the Media Pool

Drop a clip from the Media Pool or your file system straight into a composition, and the MediaIn node you end up with carries more options than clips taken off the Edit page Timeline do. Those extra options make it simpler to line up the Media Pool clips with other clips off the Edit or Cut page Timeline. On top of that you can trim clips, hold the first or last frame longer than the source media runs, and reverse or loop the clip to gain more range for your composition.

The Inspector parameters for a clip imported from the Media Pool

What follows is a rundown of the controls tacked on beyond those that show up when a clip comes from the Edit or Cut page Timeline.

- Global In/Out: This control sets where this node sits inside the composition. As an example, a clip dropped into the comp from the Media Pool lands at frame 0. The MediaIn node from the Edit page Timeline, though, might not begin until a far later frame, depending on where it was cut into the Timeline. Reach for Global In to name the frame the clip begins on so it lines up with media off the Edit page Timeline. Checking and changing how various clips in the comp line up is easiest while the Keyframes Editor is open.

To shift the clip in time or align it with other clips without altering its length, set the mouse pointer in the center of the range control and drag it to the new spot, or type the value in by hand into the Global In value control. Should the Global In and Out values be dialed down until the span between the In and Out values falls below the n number of frames the clip has available, Fusion trims the clip on its own by tweaking the Clip Time range control. Should the Global In/Out values be raised until the span between the In and Out values runs past the number of frames the clip has available, Fusion lengthens the clip on its own by tweaking the Hold First/Last Frame controls. Those added frames are shown in the range control by turning the held frames purple in the control.
