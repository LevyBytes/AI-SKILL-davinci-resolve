# Using Transitions (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using Transitions

When moving from one image to the next calls for something weightier than a plain cut, transitions act as the connective tissue that ties those moments together. The pages here lay out the various ways to add and edit transitions throughout your program.

### Working With Transitions

As another route for spanning the shift from one clip to the next, transitions frequently signal a jump in time or place as scenes change. The transitions DaVinci Resolve offers run from assorted takes on the classic cross dissolve through various kinds of wipes, giving you plenty of room to maneuver when polishing creative edits. On top of those, DaVinci Resolve also handles third‑party OpenFX transitions you install onto your system. You apply transitions at edit points, where they show up as editable objects within the Timeline.

### Video and audio transitions in the Timeline

### Previewing Transitions

If you want to see a transition before dropping it into the Timeline, first confirm that “Hover Scrub Preview” is ticked in the Transitions option menu, then rest your pointer on any transition — found in the Transitions tab (Cut page) or in the Effects Library Toolbox (Edit page) — and slide it across the thumbnail. The preview plays in the Viewer drawing on the two clips closest to the smart indicator on the Cut page, or the two clips closest to the playhead on the Edit page.

Scrubbing over a Transition Thumbnail previews the transition in the Viewer. Hit Shift-Space to summon the Effects Search dialog, which covers transitions too. Begin typing in the search field to surface the transitions you’re after. Clicking a transition in the search list applies it to whichever edit point lies nearest the playhead.

### Adding and Editing Transitions

The procedures that follow explain how to add and edit transitions in the Timeline through the mouse as well as keyboard shortcuts. Mouse-based ways to add transitions:

- To add a transition by dragging it from the Effects Library: Pull a video transition out of the Effects Library and onto an edit point in the Timeline so it sits centered at, ending at, or starting at that edit point. Without any overlap between the two clips’ heads and tails, placing a transition exactly where you want may not be possible.
- To add a transition by double-clicking its Effects Library icon: A double-click on that icon within the library drops the transition onto the edit point marked by the smart indicator (Cut page), or at the tail of whatever clip currently sits under the playhead (Edit page).
- To add a transition by clicking the Transition Alignment icons: On the Cut page, three Transition Alignment icons run along the bottom of the Transitions Library. Clicking any one of them lays the selected transition on the edit point flagged by the smart indicator, using the alignment you chose.
- To add a transition using the Effects Library contextual menu: Choose your edit points (capped at one per track), after which a right-click on a video transition inside the Effects Library lets you select Add to Selected Edit Points. With that, the transition lands on every chosen edit point simultaneously.

### The Transition contextual menu in the Effects Library

- To add a transition using the Edit Point contextual menu: On the Edit page, right-click any edit point between clips that have overlapping handles, then pick one of the four standard-transition durations on offer; those options — quarter-second, half-second, one second, and two seconds — are expressed in frames according to whatever the Timeline’s current frame rate happens to be.

The Transition contextual menu for an edit in the Timeline Keyboard-shortcut ways to add transitions:

- To add a video+audio transition using the Effects Search: Tap Shift-Space to open the Effects Search dialog, transitions included. Type into the search field to bring up the matching transitions, then click one in the result list to apply it to whichever edit point is closest to the playhead.
- To add a video+audio transition using the keyboard: Pick one or more edit points with the Selection tool — or park the playhead beside an edit you want and tap V to grab it — then press Command-T (Timeline > Add Transition) for the standard transition. The transition takes its length from the “Standard transition duration” set in the Editing panel of the User Preferences, which is one second out of the box, unless the selected edit point’s overlapping handles allow only less.
- To add a video or audio-only transition using the keyboard: Pick one or more edit points, then press Option-T (Timeline > Add Video Only Transition) for a video-only transition, or Shift-T (Timeline > Add Audio Only Transition) for an audio-only one. Again, the length follows the “Standard transition duration” set in the Editing panel of the User Preferences — one second by default, or whatever the selected edit point’s overlapping handles permit.
- To add a transition with specific alignment using the keyboard: Pick an edit, tap the U key to land on its start, center, or end, then press Command-T. The standard transition arrives aligned according to that edit selection: choosing the start of the edit drops a transition ending on the edit, choosing the end drops one starting on the edit, and choosing the center drops one centered the same way.

Methods of moving and duplicating transitions:

- To move a transition from one edit to another: Pick a transition, then drag it over to a different edit point.
- To copy a transition from one edit to another: Pick a transition, then option-drag it across to another edit point.

To duplicate a single transition across several edit points at once: 1 Right-click the transition you wish to duplicate and choose copy (or press Command-C). 2 With the Command-Key held down, click every edit point in the Timeline you’d like the transition copied to until they glow green, then let go of the Command-Key. 3 Right-click any of those green-highlighted edit points and choose Paste (or press Command-V), which copies the chosen transition onto all of the selected edit points. Timeline-based ways to alter transitions:

- To change a transition’s type: Drop a different transition from the Effects Library on top of the existing one in the Timeline.
- To change a transition’s duration: In the Timeline, drag the transition’s start or end to lengthen or shorten it evenly around the current edit. Or instead, take one of these actions:
- Right-click any transition and pick Change Transition Duration, or select it and press Command-D, then set a new duration in the dialog that opens and click Change.
- Double-click any transition to bring it up in the Inspector, where you can enter a fresh duration in seconds or frames.
- Drag a transition’s edge along the Timeline to resize its duration. Keeping the Command key pressed as you drag lets you reshape just one side of the transition’s duration.
- To change a transition’s alignment: In the Timeline, right-click the transition and select a different alignment method from its contextual menu. Alternatively, double-click any transition to open it in the Inspector and pick a fresh option from the Alignment drop-down.
- To remove a transition: Pick a transition in the Timeline and tap the Delete key. Failing that, give it a right-click within the Timeline and pick Delete off the contextual menu.

### Adding Transitions When There’s Not Enough Handles

When the overlapping outgoing and incoming handles at an edit point lack the frames to hold the standard transition duration, and you go to add a transition — whether by picking one or more edit points then hitting Command-T, or by right-clicking an edit point to reach its contextual-menu transition options — a dialog pops up with three choices:

- Trim Clips: This automatically trims the incoming and outgoing sides of each chosen edit point to build the overlap the standard transition requires.
- Skip Clips: Leaves the chosen edit points that lack enough overlap without any transition.
- Cancel: Calls off the operation altogether.

### Adding Transitions By

### Dragging to Create Overlap

Another approach makes building transitions easy during drag-and-drop editing: simply overlap the start and end of two clips at the spot where you want a transition to land. While you drag a clip or edit to overlap another clip, hold the Option and Shift keyboard modifiers down together. Three variations are open to you:

Grab a clip’s In or Out point, then with Option-Shift held down drag that edit point so it overlaps a neighboring clip where the transition should form.

Making a transition by Option-Shift dragging an edit point so two clips overlap Grab a clip, then with Option-Shift held down drag the whole clip so it overlaps a neighboring clip where the transition should form. Making a transition by Option-Shift dragging a full clip so it overlaps another one

With the Option-Shift keys held down, drag a clip out of the Media Pool so it overlaps a clip already sitting in the Timeline.

Making a transition by Option-Shift dragging a Media Pool clip onto a clip that already lives in the Timeline

### Transition Properties in the Inspector

Double-click a transition in the Timeline to bring up its Transition tab inside the Inspector. Every transition exposes the editable properties below.

- Transition Type: Whichever transition is active at the moment. Swap in any other installed transition by picking one from the drop-down menu.
- Duration: How long the transition runs, displayed in both seconds and frames.
- Alignment: A drop-down for setting where the transition sits relative to the edit point it’s

attached to. The options are “Start on Edit,” “Center on Edit,” and “End on Edit.” Below those, a separate group holds extra properties unique to each transition type. Because the Cross Dissolve transition sees the most use, its properties serve as the example here.

- Style: The various Dissolve transitions (Cross Dissolve, Additive Dissolve, and the rest) surface this drop-down, which governs how the outgoing clip blends into the incoming one over the dissolve. Six options are available:

Video: A plain linear dissolve where the outgoing clip fades out while the incoming clip fades in. Film: A logarithmic dissolve that mimics the film dissolves an optical printer would produce. Additive: The outgoing and incoming clips cross fade through the Additive composite mode, which makes the transition appear to brighten at its midpoint. Subtractive: The outgoing and incoming clips cross fade through the Subtractive composite mode, which makes the transition appear to darken at its midpoint. Highlights: The outgoing and incoming clips cross fade through the Lighten composite mode, so the brightest portions of each clip stand out during the transition. Shadows: The outgoing and incoming clips cross fade through the Darken composite mode, so the darkest portions of each clip stand out during the transition.

- Start Ratio: Sets how far along the transition already is on its first frame, on a 0 to 100 percent scale. Giving the Start Ratio any value above 0 makes the transition open right away in a more fully cross-dissolved state on that very first frame.
- End Ratio: Sets how far along the transition has gotten by its last frame. Giving the End Ratio any value above 0 keeps the transition from ever resolving completely to the incoming shot on its final frame.
- Reverse: Flips the transition around. Dissolve transitions have this parameter turned off.
- Ease: A drop-down for applying nonlinear acceleration to a transition’s start, finish, or whole

span. It lends inertia to the move from the outgoing clip into the incoming clip and softens how each clip enters and exits the transition. None: The outgoing clip dissolves to the next shot at a steady, linear pace. In: The outgoing clip holds on as the transition’s opening dissolves more slowly than its close. Out: The outgoing clip drops away sooner, the transition’s opening dissolving faster than its close. In & Out: Both clips ease in slowly at the start and end of the dissolve, which leaves the dead center of the transition running faster. Custom: Hands you manual control over the fade’s parameters by way of the Transition Curves below.

- Transition Curve: Lets you place keyframes by hand to steer how the transition advances across its duration. Transitions of other types show properties tied to their own particular effect, all covered in detail in the section coming up.

### Favorite Transitions

Even though DaVinci Resolve ships with a broad assortment of transitions, most editors lean on only a handful of them day to day. It’s also common to stash customized versions of a given transition so that one specific set of transition settings can be reused again and again. To mark a transition or other effect as a favorite in the Effects Library: Hover over any transition and click the star button as it appears to favorite that transition. Click a transition’s star again to “un-favorite” it. Your favorites turn up in the Favorites area of the Effects Library bin list on the Edit page, or in the Favorites tab of the Transitions panel on the Cut page.

### Changing the Standard Transition

One project may call for a different transition to serve as the standard transition than the next. DaVinci Resolve hands you a few ways to manage that. To change the standard transition: Right-click any transition or effect and pick “Set as Standard Transition.” From then on, the standard transition carries an orange indicator just left of its name in the Effects Library.

The Effects Library open on the Edit page, where favorited transitions wear stars and the standard transition shows an orange indicator just left of its name

The Transitions tab open on the Cut page, where favorited transitions wear stars and the standard transition shows an orange indicator just left of its name To change the standard transition duration: Head into the User Preferences, open its Editing panel, and revise the “Standard transition duration” setting, with the length expressible in either Seconds or Frames. Click Save once you’re done.

### Creating Transition Presets

When you keep reaching for one transition tweaked a certain way throughout your work, you can build a Preset of it for quick recall. After it’s saved, a Preset can be favorited or named the Standard Transition to keep it close at hand. To save a transition preset for future use: 1 Drop a transition onto the Timeline, then double-click it to open it in the Inspector and dial its settings in exactly as you need them. 2 (Optional) where it matters, open the transition’s Curve Editor and choose the curve shape you want the transition to follow; that customized transition curve gets stored within the transition’s preset. 3 Right-click the transition you’re saving and pick Create Transition Preset. 4 Enter a name for the transition preset in the dialog that appears, then click OK. The transition then lands in the User section at the foot of the Toolbox Video Transitions area, ready to be applied just as you would any built-in transition. To remove a transition preset: give any preset a right-click and pick Delete Transition Preset.

### Changing Transitions to Fusion Compositions

When you want a transition more intricate than the Inspector can deliver, you can now turn any transition into a Fusion Composition right on the Edit page Timeline. The conversion from a Resolve transition into a Fusion composition goes like this: 1 Place a transition between two clips on your Timeline. 2 Right-click that transition and choose “Convert to Fusion Cross Dissolve.” 3 Right-click it once more and choose “Open in Fusion Page.” A fresh Fusion composition opens with the base Cross Dissolve nodes and tools already in place. From there, the full arsenal of Fusion page tools is yours to customize the transition.

The starting node tree produced once a transition has been converted into a Fusion cross dissolve

### Video Transitions

Listed below are the transitions DaVinci Resolve includes out of the box, each shown with the parameters the Inspector exposes for it:

### Dissolve

Within film’s visual grammar, a dissolve usually signals that time or place has moved on. It tells your audience that one scene has wrapped up while another gets under way.

- Additive Dissolve: Start Ratio tunes how far into the transition you are at its outset. End Ratio tunes how far the transition reaches by its close.
- Blur Dissolve: Horizontal/Vertical Strength controls how much blurring happens along the X and Y axes over the span of this transition. Start Ratio tunes how far into the transition you are at its outset. End Ratio tunes how far the transition reaches by its close.
- Cross Dissolve: Style lets you select the kind of cross dissolve, with choices including: Video, Film, Additive, Subtractive, Highlights, Shadows. Start Ratio tunes how far into the transition you are at its outset. End Ratio tunes how far the transition reaches by its close.
- Dip to Color Dissolve: Start Ratio tunes how far into the transition you are at its outset. End Ratio tunes how far the transition reaches by its close. Color lets you select which color the dissolve dips through at its midpoint.
- Non-Additive Dissolve: Start Ratio tunes how far into the transition you are at its outset. End Ratio tunes how far the transition reaches by its close.
- Smooth Cut: A purpose-built transition for softening short jump cuts that fall in the middle of a clip. It leans on AI powered Speed Warp processing to align matching features on both sides of a cut, automatically morphing a subject from one position into another across the length of the transition.

A Mode drop-down menu offers two settings: Faster and Better. Better is the default; it delivers excellent quality and can hold onto subject motion throughout the transition. Faster, by contrast, morphs between stills of the outgoing and incoming frames. For most real-world cases Better mode yields the stronger result, though some cuts or effects come out better under Faster. Smooth Cut shines on footage like sit-down interviews and tight head shots where background and subject movement stays minimal and the subject barely shifts position across the cut. A textbook use is paring pauses, partial repeats, filler words such as “um” or “you know,” and similar speech disfluencies from an interview clip to tighten its dialog, all while wiping out the small “jump” the cut introduces and never resorting to a B-roll cutaway. Laying a brief two- or four-frame Smooth Cut transition over the edit can render that kind of edit invisible, provided the speaker doesn’t move much during the cut. As background motion grows and the speaker shifts more, getting a usable Smooth Cut result becomes tougher. Even though any transition defaults to one second, Smooth Cut transitions fare far better kept short; 2- to 6-frame Smooth Cut transitions often do the best job of disguising jump cuts. NOTE: Starting with DaVinci Resolve 20, the transition is carried out by a new AI powered Speed Warp inside Smooth Cut. If you’d rather fall back on the earlier optical flow version, simply clear the Speed Warp box in the Transition inspector.

### Iris

Irises are directional transitions that serve both to draw the eye toward a particular spot in the frame and to tell the audience one scene has closed and another opened. Back in the silent film era, irises were used heavily in place of the more technically demanding dissolve.

- Arrow Iris: Color sets the hue of the border, when one is present. Border sets how wide the border is, in pixels, where 0 yields no border at all. Aspect Ratio lets you reshape the proportions of the shape. Offset to center lets you move the center point where this transition is anchored. Rotation adjusts the iris’s angle. Feather is a checkbox that, once enabled, draws on the Border slider to set how much feathering appears at the transition’s edge. The Reverse checkbox flips the transition’s direction.

Preset lets you pick from one of these presets:
