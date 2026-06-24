# Editing Adding And Copying Effects And Filters

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

## Overview

Covers: Editing Effects and Transitions; Editing, Adding, and Copying Effects and Filters.

## Editing Effects and Transitions

### Editing Effects and Transitions

## Editing, Adding, and Copying Effects and Filters

### Editing, Adding, and Copying Effects and Filters

Here you will learn the ways to locate and apply effects to Timeline clips,

duplicate them between clips, take them off again, and tweak their settings

through the Inspector after they have been placed.

To read up on which specific Resolve FX you have on hand, refer to “Resolve FX.”

### Using the Effects Library

Every effect available for your edit — filters, transitions, titles, and generators alike — lives within the Effects panel. That panel presents a tiered listing of each transition, title effect, generator, and filter on offer, grouped by category. If you want a preview of a video effect prior to dropping it onto a clip, first confirm that “Hover Scrub Preview” is enabled in the Effects option menu, and then glide your pointer over any thumbnail in the Effects tab, sliding it back and forth. That effect previews in the Viewer at its default parameters and scrubs through whichever clip is highlighted in the Timeline. Should nothing be selected, it falls back to the clip sitting beneath the playhead. Triggering a given video effect on a clip is as easy as dragging that effect’s thumbnail onto a Timeline clip. Alternatively, double click the thumbnail, or pull an effect straight into the Inspector, to apply it to the chosen clip. When you wish to fine-tune the effect’s parameters, bring up the Effects tab inside the Inspector.

Hovering across an Effect Thumbnail gives you a preview of that effect right in the Viewer. To hunt for a specific effect, click the magnifying glass icon sitting at the top of the Effects Library. The drop-down menu positioned just beside it lets you decide between searching the whole FX library (All Folders) or limiting the search to the current folder only. Category Names work as search terms when you are looking for effects and transitions. As an illustration, a search for “Stylize” surfaces every Resolve FX filed under the Stylize section. Searches can also be run using whatever language is set under DaVinci Resolve > Preferences > User > UI Settings, alongside English.

### Shift-Space to Display the Effects Search Dialog

Hitting Shift-Space now summons the Effects Search dialog across the Cut, Edit, Color and Fairlight pages, mirroring the behavior that the Fusion page always had. With a clip already selected, clicking an effect within the search list will apply it to that selected clip.

A press of Shift-Space brings up the Effects Search Dialog. Here, entering “film” surfaces every effect that has Film in its name.

### The Toolbox

This is where you find every video and audio transition, title, and generator bundled with DaVinci Resolve: Toolbox Surfaces all transitions, titles, generators, and effects together. Video Transitions: Holds each of the built-in transitions supplied by DaVinci, grouped by category. Near the foot of the list a User category surfaces whatever presets you have saved. Any video transition can be dragged onto any Timeline edit point with overlapping clip handles to fold it into your edit; you may drag the transition so it finishes on, sits centered on, or begins on the edit point. See Chapter 48, “Using Transitions,” for further detail. Audio Transitions: Holds audio transitions used to build crossfades. Titles: Titles edit into the Timeline the same way any other clip does. After a title is placed in the Timeline, its text and position can be changed straight in the Timeline Viewer, or you can reach its controls inside the Inspector for additional tailoring. Generators: Generators likewise edit into the Timeline just like any clip. Pick a generator and open the Inspector to reach its controls for additional tailoring. A default duration for generators can also be chosen within the Editing panel of the User Preferences. Effects: Effects act as placeholders in the Timeline that enable more specialized Fusion compositing, or that let you alter the tracks below by way of an adjustment clip.

### Open FX

Third-party Open FX filters, transitions, and generators are supported by DaVinci Resolve on the Edit page. After you install such effects on your workstation, they show up in this part of the Effects Library, grouped by type and group according to the metadata carried inside each effect.

### Open FX

Surfaces every Resolve FX and third-party Open FX present on your workstation together. Filters: Holds the Resolve FX filters bundled with DaVinci Resolve, plus whatever thirdparty OFX plugins you have installed on your workstation. Filters drag onto video clips to apply an effect to that clip. After application, filters can be tweaked and tailored by opening the Open FX panel of the Inspector. Generators: Holds whatever third-party OFX generators you have installed on your workstation. These edit into the Timeline exactly like the native generators shipped with DaVinci Resolve, yet they additionally surface an Open FX panel beside the Transition panel in the Inspector, letting you tailor settings that belong only to that transition. Transitions: Holds whatever third-party OFX transitions you have installed on your workstation. OFX transitions behave much like any other transition, yet they also surface an Open FX panel beside the Transition panel in the Inspector, where settings unique to that transition can be tailored.

### Audio FX

Across every platform, DaVinci Resolve ships a collection of built-in Fairlight FX, a native audio plugin format that puts assorted audio tools and effects within reach on macOS, Windows, and Linux. Under macOS and Windows, DaVinci Resolve handles third-party VST audio plugins, covering most of the professional third-party tools and effects relied upon throughout the audio postproduction field. Under macOS, DaVinci Resolve handles Audio Unit (AU) audio plugins. After you install these effects on your workstation, they show up in this panel of the Effects Library. Audio plugins let you put effects onto audio clips or whole tracks of audio, whether to add creative texture such as echo or reverb, or to fix mastering problems through noise reduction, compression, or EQ.

### Effects Library Favorites

Clicking the far right of any transition, title, or generator lets you flag that effect with a star as a favorite effect. Once you do, the favorited effects collect in their own Favorites zone at the foot of the Effects Library Bin list. Favorited effects are sorted into categories automatically within the list.

Stars mark a flagged favorite effect; every favorite is filtered and sorted into categories automatically.

### Converting Fusion Compositions to Edit Effects

Should you have built a Fusion Composition you would like to reuse across several projects, it can now be saved to the Effects toolbox on the Edit page. That way the effect stays within easy reach on the Edit page, and drops readily onto Timeline video clips. Turning a Fusion composition into an Edit effect goes like so: 1 In Fusion, output the composition as a macro by right clicking a node and picking Create Macro out of the contextual menu. 2 Store the macro file (.setting) under the directory matching your platform — MacOS: `/Library/Application Support/Blackmagic Design/DaVinci Resolve/Fusion/ Templates/Edit/Effects` Windows: `C:\ProgramData\Blackmagic Design\DaVinci Resolve\Fusion\Templates\Edit\Effects` Linux: `/opt/resolve/Fusion/Templates/Edit/Effects` From then on the effect appears, ready to drag and drop, within the toolbox’s “Fusion Effects” section inside the Effects Library on the Edit page.

### Seeing Effects in the Timeline

Whenever you put any sort of effect on a Timeline clip — be it an Inspector adjustment, a speed effect, a plugin you have applied, and so on — clips carrying that effect take on a darker shade of whatever color they already are, signaling that an effect is present. Stripping all effects off a clip (for instance, with the Remove Attributes command) restores that clip to its original color. This lets you tell at a glance which clips carry effects and which do not.

An effect-bearing clip, darkened in shade, sitting between a pair of normally-shaded clips that carry no effects

### Using the Inspector

After effects are placed on a timeline, the Effects Inspector is the spot for editing their parameters. The Inspector serves as the hub for adjusting every setting tied to filters, compositing, sizing, titling, transitions, generators, and effects of all sorts.

Which parameters the Inspector shows hinges on your Timeline selection; (left) a clip’s parameters, (right) a title’s parameters.

A great many of the procedures in this section depend on the Inspector, which opens or closes when you click the Inspector button sitting at the far right end of the Edit and Cut page toolbars, or when you doubleclick a transition or generator within the Timeline. There are three ways the parameters of Timeline clips end up shown in the Inspector:

- When no clips are selected in the Timeline, the clip sitting in the topmost auto-select-enabled track that crosses the playhead has its parameters presented in the Inspector.
- The Inspector always presents the parameters of one or more items selected in the Timeline, which takes precedence over the clip in the highest track that crosses the playhead, when needed. Altering the selection alters which parameters appear, and any parameters you edit in the Inspector affect only the currently selected clip. With several clips selected, the Inspector shows “Multiple Clips” and lets you tune the parameters of every selected clip together.
- Picking Timeline > Selection Follows Playhead tells DaVinci Resolve to keep selecting whichever clip crosses the playhead in the Timeline. Consequently the Inspector keeps showing the parameters of whichever clip sits at the playhead, and as an added benefit that same clip becomes selected for your other editing operations too. When several stacked clips cross the playhead simultaneously, the uppermost video clip whose Auto Select control is enabled gets selected, surfacing its parameters in the Inspector, while every other clip is disregarded.

### Inspector Effects Controls

Different Effects clips in the Timeline expose different controls. Whatever panels are surfaced, the parameters inside each panel are sorted into groups, each carrying a title bar that names the group, alongside additional controls letting you govern every parameter inside that group together.

### The Effects Inspector controls

These controls include:

- Enable button: A toggle control positioned left of the parameter group’s name lets you, in a single move, disable and re-enable each parameter belonging to that group. Orange means that track’s enabled. Gray is disabled.
- Parameter group title bar: Double-clicking any parameter group’s title bar collapses or opens them. More usefully still, Option-double-clicking one parameter group’s title bar collapses or opens every parameter group together.
- Keyframe and Next/Previous Keyframe buttons: This button lets you add or strip keyframes at the playhead’s position to or from every single parameter inside the group. While the button glows orange, a keyframe sits at the playhead’s current position. While it is dark gray, no keyframe is present. The left and right arrow buttons let you hop the playhead between keyframes for additional tuning.
- Reset button: Lets you restore every parameter inside that group to its default settings.

### Adding Filters to Video Clips

For generating assorted effects, DaVinci Resolve handles built-in Resolve FX as well as third-party OFX plugins. You can put these effects on Edit page clips and equally on Color page nodes. This section walks through applying, editing, and removing these filters on the Edit page. For more on video effects in the Color page, consult Chapter 151, “Using Open FX and Resolve FX.” For a thorough rundown of each Resolve FX plugin shipped with DaVinci Resolve, consult Part 12, “Resolve FX Overview.” Ways to apply video filters on the Edit page: To apply a video filter to a clip:

- Pull any filter out of the Effects Library and drop it onto whichever Timeline clip should receive it.
- Double Click a filter within the Effects Library to place it on the currently selected clip.
- Pull the Filter from the Effects Library across to the Inspector to place it on the chosen clip.
- Pull the Filter from the Effects Library across to the Viewer to place it on whatever clip is on view.

To apply a video filter to multiple clips: Highlight all the clips you intend to filter in the Timeline, then drag any filter out of the Open FX category of the Effects Library onto any one of the selected clips. This action can be undone.

Applying a video filter to a single clip in the Timeline

To edit a clip’s video filters: Highlight that clip and open the Inspector’s Effects tab. The effects get further sub-grouped by type: Fusion, Open FX, or Audio. When a clip carries no effects, this panel appears dimmed.

Resolve FX controls show up in the Effects panel of the Inspector. Certain video filters carry custom onscreen controls adjustable in the Viewer. Those can be surfaced on the Edit page through the OFX mode of the Viewer.

Switching on the onscreen controls for Resolve FX within the Edit page Timeline Viewer

After they are enabled, the OFX onscreen controls show up in the Viewer.

Modifying onscreen controls foµr Resolve FX in the Edit page Timeline Viewer A good number of audio filters carry custom controls that show up in a floating window. To surface a filter’s custom controls: Open the parameters, if they are not already open, by double-clicking that filter’s title bar. For filters carrying custom UI, a button should show up at the top of the parameters. Clicking that button opens a floating window holding every custom control. Once you have finished tuning the custom controls, close the window.

### The Fairlight FX Noise Reduction custom UI interface

Ways to work with video filters in the Inspector:

- To reorder several video filters placed on a clip: Click the move up or move down buttons within any filter’s title bar, just left of each filter’s Trash Can button.
- To switch a filter off or back on: Hit the toggle control found at the leftmost edge of each filter’s heading row. Orange means that track’s enabled. Gray is disabled.
- To remove a filter: Click the Trash Can button.
- To reset a filter: Press the Reset button positioned at the far right of that filter’s title bar.
- To open or collapse a filter’s parameters: Give the title bar a double-click.
- To open or collapse the parameters of all filters: Hold Option and click the title bar.

Once placed on a clip, video filters can likewise be keyframed or automated the same as any other Inspector setting, producing dynamic effects that evolve over time.

### Render in Place

Render in Place lets you render and bake in every effect placed on a single clip in the Edit page Timeline. This command, available only on the Edit page, generates a brand-new media file that swaps in for the original clip on the Timeline. That new file is written into the very folder holding the original source file, and gets added to the Media Pool by itself. Render in Place can help you boost playback performance on a computationally heavy clip, or serve to build a fresh high-quality master media with effects finalized and baked in. Suppose, for instance, you have assembled a clip carrying an elaborate speed ramp, and you intend to pass it along to a fellow editor or to a vfx artist within a round-trip rendering workflow, yet you are uneasy about how other programs might read those speed effects. In that case you could render the clip in place at master quality, then go on to render and hand off the program. This operation does not run in only one direction. Later on, should the clip turn out not to have been as locked-down as you had hoped and a change becomes necessary, the “Decompose to Original” choice restores the original clip carrying its original effects. To Render in Place: 1 On the Edit Page timeline, pick one or more clips. When several clips are picked, each one is rendered in place separately, though the whole thing runs as one batch operation. 2 Right-click that selection and pick “Render in Place” out of the contextual menu. 3 Set the appropriate Render Clip Options, after which you click the “Render” button. Start Timecode: Establishes the clip’s opening timecode value. Format: Picks the media file format. Codec: Picks the video codec. Type: Lays out the compression parameters belonging to the chosen codec. Include Handles: Lets you state how many frames ahead of and behind the clip In/Out points get rendered. Include Video Effects: Tick this checkbox to bake in every effect placed on the clip, among them sizing, Open FX or Resolve FX, and speed effects. Leaving this checkbox off renders the clip with the speed effects baked in but none of the others.

Include Fusion Composition: Switch this checkbox on to bake in whatever compositions are attached to the clip. Include Color Grading Effects: Switch this checkbox on to bake in whatever color grading is attached to the clip out of the Color page. Render at Source Resolution: When ticked, the freshly rendered media matches the resolution of the original source media instead of the timeline resolution.

The Render in Place options 4 In the File dialog that pops up, pick where the resulting media should be saved. Settle on a location and click Open. A progress bar surfaces to indicate how long the operation runs. After it wraps up, your new media is kept at the chosen spot, added to the Media Pool, and proceeds to swap in for each matching source clip on the Timeline. If you have run Render in Place and then have second thoughts, or some last-minute change reaches you afterward, you can easily decompose back to the original clip with its editable effects so as to make the change. To Decompose to Original: 1 On the Edit Page timeline, pick one or more clips that have previously been Rendered in Place. 2 Right-click that selection and pick “Decompose to Original” out of the contextual menu. Back onto the Timeline comes the original clip, along with every one of its editable effects. Media generated through the Render in Place process is neither deleted from the source folder nor pulled out of the Media Pool. In effect it is a new clip.

### Fusion Effect Templates Cache

Fusion effect templates placed on timeline clips offer more granular caching plus automatic render caching options. Within the timeline clip context menu, the Render Cache Fusion Effect Filter menu carries an Auto option switched on by default. While render cache is set to Smart, any Fusion effects and templates placed on a clip cache themselves automatically. Switching auto off lets you cherry-pick which effects to cache individually. While render cache is set to User, the Auto option caches the Fusion effects automatically, provided the project setting to Automatically Cache Fusion Effects in User mode is on. With that project setting off, Auto mode caches no Fusion effects unless you pick them out one by one.

### Adjusting Multiple Clips at the Same Time

There is a simple route to tuning the Inspector parameters of several clips together, without resorting to Paste Attributes (covered later in this chapter). All it takes is selecting every clip you wish to change at once, then modifying the Inspector parameter you want to adjust. The upshot is that every selected clip shifts by the same amount. This holds for compositing effects, transforms, text parameters, filters, and audio settings — pretty much anything that can be surfaced in the Inspector for several selected clips at once. Once several clips are selected, the Inspector shows “Multiple Clips” as its title. Should the selected clips hold differing values in the parameter you are tuning, that parameter shows two dashes in its value field. You have two routes for adjusting multiple clips:

- When you want a relative adjustment across all selected clips while preserving their original offsets from one another, drag the virtual slider in the parameter field, which will show a + or – ahead of however many units your adjustment is.
- When instead you want every selected clip set to the same value, double-click in the number field, type the value, and press Return.

Performing a relative shift of plus 4.9 to the Rotation Angle across every selected clip

### Adjustment Clips

You can likewise put all manner of effects onto multiple Timeline clips using Adjustment clips, found in the Effects bin of the Toolbox in the Effects Library. Whenever an Adjustment Clip is stacked over one or more Timeline clips, whatever filters or additional effects you place on that Adjustment clip propagate down to each clip below. The kinds of effects you can apply with Adjustment clips include:

- Resolve FX and Open FX plugins
- Inspector parameters including Composite, Transform, Cropping, and Dynamic Zoom
- Fusion page effects
- Color page grading and sizing

Adjustment clips offer a quick and readily revisable means of applying one or more effects and grades across a span of clips. Adjustment clips that struggle to play back in real time can be rendered to cache, the same as any ordinary video clip. Adjustment Clips can be named through the Inspector. To stash an Adjustment clip, simply drag it from the Timeline into the Media Pool. From there you can manage the Adjustment clip the same as any other media type.

An Adjustment clip casting the vignette of a Prism Blur Resolve FX down onto a pair of clips below

### Paste Attributes

The Paste Attributes command lets you copy and paste video and audio attributes, along with color corrections, from a single clip onto several clips. It is a quick route to spreading video and audio tweaks and effects out of one clip onto numerous others throughout the Timeline. To copy attributes: 1 Pick a clip whose attributes you wish to push to other clips, then hit Command-C. 2 Pick one or more further clips as the paste destinations. 3 Go to Edit > Paste Attributes (Option-V), or right-click any of those selected clips and pick Paste Attributes from the contextual menu. 4 Once the Paste Attributes window opens, tick the checkbox for each attribute you intend to paste, then hit Apply when finished.

### The Paste Attributes window

The Paste Attributes window presents at the top the clip you are copying from and the clip(s) you are pasting onto, and supplies checkboxes for choosing which attributes to paste.

### Keyframe Options for Pasting Keyframed Attributes

A pop-up menu underneath lets you pick how any keyframes belonging to the attributes being pasted should be applied; the choices are Maintain Timing or Stretch to Fit.

### Option to Ripple the Timeline for Pasting Speed Effects

While using Paste Attributes to copy speed effects between clips, the Ripple Sequence checkbox lets you decide whether or not the pasted speed effect ripples the Timeline.

### Remove Attributes

Specific attributes can also be cleared from one or more clips through a window that mirrors the opposite of the Paste Attributes window.

### The Remove Attributes window

To remove attributes: 1 Pick one or more clips carrying effects you wish to strip away. 2 Go to Edit > Remove Attributes, or right-click any of those selected clips and pick Remove Attributes from the contextual menu. 3 Once the Remove Attributes window opens, the checkboxes for removable effects become active, so switch on whichever attributes you want gone. 4 (Optional) Should one of the attributes being stripped be a retime effect, the Ripple Sequence checkbox lets you decide whether the Timeline ripples as a consequence. 5 Hit Apply when finished.
