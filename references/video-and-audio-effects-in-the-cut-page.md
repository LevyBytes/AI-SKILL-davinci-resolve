# Video And Audio Effects In The Cut Page (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Video and Audio Effects in the Cut Page

As your edit takes shape, you'll regularly need to put effects on clips—to make titles, fold clips together through compositing, drop in plugins that lend clips a certain look, ramp clips faster or slower, or transform clips so as to zoom into them or shift them about the frame. The Cut page carries controls for all of this and then some.

### Adding Transitions

Transitions like dissolves or wipes can go on an edit to signal a shift in topic, a shift in

location, or time passing. A Smooth Cut transition can likewise be dropped in to mend unwanted cuts in

interview clips or other cases where the subject's position—or the background—doesn't shift much in

the frame. Three buttons over at the bottom right of the Media Pool make it simple to add

and clear away dissolves and Smooth Cut transitions.

### The Cut, Dissolve, and Smooth Cut buttons

### Adding Dissolves

Being the most standard, everywhere-seen kind of transition, dissolves are also the simplest to make. Park the playhead on or near an edit you'd like turned into a dissolve, then, down at the Media Pool's bottom left, click the Dissolve button. A one second Cross Dissolve gets added to whichever edit point lies closest to the edit point.

(Left) A playhead moved near an edit point, (Middle) A dissolve being added, (Right) An edit point that's selected

### Adding Dissolve Using Keyboard Shortcuts

A dissolve can also be added by picking one or more edit points (or by sliding the playhead near an edit you want and pressing V to grab the nearest one), then pressing Command-T to drop in a dissolve, which is the standard transition. The keyboard also lets you add a transition lined up with the start, middle, or end of the edit point. To do that, pick an edit point, tap the U key over and over so as to cycle among the start, center, or end of the edit being selected, then press Command-T for the standard transition. That standard transition lands with its alignment set by the edit selection you made; picking the start of the edit drops a transition ending on the edit; picking the end of the edit drops a transition starting on the edit, and choosing the center of the edit drops a transition centered the same way.

A transition lined up with an edit point's beginning, center, and end

### Changing a Transition to a Cut

To take out a dissolve and thereby turn a transition back into a cut, bring the playhead at or near the edit holding the dissolve, then click the Cut button—quick to do when you're on the DaVinci Resolve Editor Keyboard, which carries a dedicated Cut button.

TIP: As another route, you can pick one or more transitions in the Timeline and press the

Delete key to clear them.

### Adding Smooth Cuts

Smooth Cuts are special-purpose transitions built to render short jump cuts in the middle of a clip unnoticeable. The way it works is by drawing on AI powered Speed Warp processing to line up the same features on both sides of a cut, automatically morphing a subject from one position into another across the transition's span. To add a Smooth Cut: 1 Set the playhead on or near an edit. 2 Down at the Media Pool's bottom left, click the Smooth Cut button. A one second Smooth Cut gets added to whichever edit point lies closest to the edit point. A Mode dropdown menu hands you two choices: Faster and Better. Better is the default, with excellent quality and the knack for holding onto subjects' motion across the transition's span. Faster morphs between stills of the outgoing and incoming frames. In most real situations Better mode hands you the superior result, though some cuts or effects come out better with the Faster option. The Smooth Cut effect performs best on footage such as sit-down interviews and close-up head shots that carry minimal background and subject motion, and where the subject's position barely differs from one side of the cut to the other. Smooth Cut shines, for instance, when you're paring pauses, partial repeats, filler sounds like "um" or "you know," and other speech disfluencies from an interview clip so the dialog tightens, and your aim is to kill the small "jump" at the cut without cutting away to B-roll. A short two or four frame Smooth Cut transition laid on the edit can render this sort of edit invisible, provided the speaker doesn't move much during the cut. The busier the shot's background and the more the speaker shifts position, the tougher it gets to land a useful Smooth Cut result. Even though any transition defaults to one second, you'll find Smooth Cut transitions often fare far better kept short; 2- to 6-frame Smooth Cut transitions tend to do the best job of hiding jump cuts. NOTE: Beginning with DaVinci Resolve 20, Smooth Cut relies on a new AI powered Speed Warp to carry out the transition. Should you rather go back to the older optical flow version, just clear the Speed Warp box in the Transition inspector.

### Adding Other Kinds of Transitions

So that choosing transitions, titles, and effects feels more intuitive, DaVinci Resolve presents each effect as a thumbnail picture alongside the text name. That lets a user breeze through the many options and pick the right effect by sight rather than recall its name alone. Transitions and titles can be previewed ahead of dropping them on the Timeline, so you can quickly audition several options before settling on one.

### Transitions Thumbnails

To preview a transition ahead of dropping it into the Timeline, make sure "Hover Scrub Preview" is ticked in the Transitions option menu, then just rest your pointer on any transition in the Transitions tab and slide it across the thumbnail. The transition previews in the Viewer using the two clips nearest the Smart Indicator on the Cut page, or the two clips nearest the playhead on the Edit page.

A scrub over a Transition Thumbnail previews that transition in the Viewer. Once you've settled on your transition, it can go onto any edit point by way of the methods below: Methods of adding different transitions:

- To add a transition by dragging it from the Transitions Browser: Out of the Effects Library, drag a video transition to an edit point on the Timeline so it centers at, ends at, or starts at the edit point. Where the heads and tails of the two clips don't overlap, you may be unable to place a transition where you'd like.
- To add a transition using the Transitions Browser's contextual menu: Choose one or several edit points (limited to one per track), then right-click a video transition over in the Effects Library and pick Add to Selected Edit Points and Clips. That one transition lands on each selected edit point together.
- To add a transition by double-clicking in the Transition Browser: A double-click on a transition in the Cut page's Transitions Browser applies it straight to the edit point that the Smart Indicator references.
- To add a transition through the Transition Browser's alignment icons: A double-click works on one of three transition alignment icons sitting at the bottom of the in the Cut page's Transition Browser.
- To add a transition to all edit points on a timeline: Click the Timeline Actions menu and pick Add Transition to All Edits. This drops the last used transition onto every edit point across a timeline.

### Favorited Transitions

Any transitions you've flagged as favorites (whether by clicking the star icon on the thumbnail or by picking Add to Favorites off the contextual menu) are reachable in the Favorites tab of the Effects library.

### Editing and Removing Transitions

After a transition is in place, you can edit it in a range of ways to suit your program best, whether from the Timeline itself or by way of the Transition Inspector. Methods of editing transitions in the Timeline:

To change a transition's duration: Drag the start or end of a transition in the Timeline so it grows or shrinks symmetrically around the current edit.

To move a transition from one edit to another: A transition can be dragged from where it currently sits onto another edit point.

To copy a transition from one edit to another: Pick a transition, then option-drag it onto another edit point to drop in a duplicate transition.

To change a transition's type: Drag a different transition out of the Transition Browser onto the current one in the Timeline.

To remove a transition: Pick a transition in the Timeline and press the Delete key.

To remove all transitions in a timeline: Click the Timeline Actions menu and pick Clear Transition from All Edits.

Editing transitions in the Transition Contextual menu: A transition's parameters can be edited right in the Timeline, by right-clicking the transition and picking one of the options off the contextual menu.

A right-click on a transition over in the Timeline surfaces the editing options above. Change Transition Type: Switch to any other installed transition by picking one out of the drop-down menu. Change Duration: Set the transition's duration, shown in both seconds and frames. Set as Default Transition: Makes the currently selected transition the Default Transition.

Alignment Options: Lets you set where the transition falls relative to the edit point it's on. The three on offer read "Start on Edit," "Center on Edit," along with "End on Edit." Cut/Copy/Paste: The standard cut, copy, and paste controls used when editing transitions in the timeline. Editing transitions in the Transition Inspector: For finer control over your transition, right down to every transition-specific parameter, lean on the Transition Inspector. To read more on each specific transition that ships with DaVinci Resolve, see Chapter 30, "Using the Inspector in the Cut Page."

### Setting the Default Transition

Out of the box, the default transition is a plain cross dissolve. Should you want to make some other transition the default, just right-click a transition thumbnail and pick Set as Standard Transition off the contextual menu.

Beyond the Default Transition type, you can also set its duration and alignment, either from the Timeline Options menu or by right-clicking the transition in the Timeline and picking "Set Default Transition."

### Changing the Default Transition

### Titles

The Titles Browser holds a collection of title clips you can draw on to add superimposed titles, slates, interstitial titles, lower thirds, or otherwise meet whatever textual needs your program carries.

### Titles Thumbnails

To audition titles ahead of dropping them into the Timeline, make sure "Hover Scrub Preview" is ticked in the Titles option menu, then just rest your pointer on any thumbnail in the Titles tab. Where the title is animated (i.e., Fusion titles), sliding the pointer across the thumbnail previews the animation. Once you've settled on your title, you can drag it from the Titles tab onto your Timeline on the Edit page or on the Cut page—either the upper or the lower Timelines—or instead rely on the editing selection modes along the bottom of the tab.

A scrub over a Title Thumbnail previews that title in the Viewer. The two categories hold two different kinds of titles. The "Titles" category holds simple, bare-bones titles you can customize in all sorts of ways. Among the choices, the Text title is the most flexible. The "Fusion Titles" category holds more elaborate titles that are visually richer and carry more preset animation.

### Adding Titles

A title goes onto the Timeline when you open the Titles Browser and drag and drop titles into the Timeline wherever you'd like them, just as you would any other clip. A title clip lasts 5 seconds by default. This standard "generator" duration is adjustable over in the User Preferences' Editing panel. After being edited onto the Timeline, titles move, resize, and superimpose much as any other clip would. Beyond that, once selected, titles and generators alike surface the very same Transform, Cropping, Speed, and Composite controls any other clip carries; those controls let you composite titles in various ways to build different text effects.

### Editing Titles

After a title is on the Timeline, the original title generators that came with DaVinci Resolve carry onscreen controls letting you edit text and transform and position blocks of text right inside the Timeline Viewer.

### Positioning and Transforming Text

As long as the Timeline playhead sits over a text generator that's atop one or more background clips, clicking the text in the Timeline Viewer surfaces onscreen transform controls matching the Position, Zoom, and Rotation parameters in the Inspector.

### Transforming a title's text box in the Viewer

As you drag text to reposition it, snapping kicks in at the X and Y center of the frame, as well as

around the frame's outer third. As you drag a text object, holding the Shift key down restricts

its travel to the X or Y axes alone. Holding the Option key down switches snapping off.

### Editing Text

A double-click on text within the Timeline Viewer makes that text editable, so you can drop in a text cursor or select characters and edit just as you would inside any text editor.

Editing a title's text in the Viewer Editing Titles Using the Video Inspector For tighter control over your titles, double-clicking any title surfaces its parameters in the Video Inspector. There you can switch fonts, colors, drop shadows, backgrounds, and so on. Basic transform parameters and cropping are adjustable there too. To read more about Editing Titles, see Chapter 49, "Titles, Generators, and Stills."

### The Title settinµgs of Video Inspector

### Adding Resolve FX and Other Plugins

The Effects Browser surfaces video and audio plugins you can drag and drop onto your clips. On the video side, several categories of Resolve FX plugins ship with DaVinci Resolve, but should you have installed Resolve-compatible OFX plugins, those turn up here too, sorted into their own categories. On the audio side, a set of Fairlight FX plugins comes with DaVinci Resolve, but should you have installed VST plugins on macOS or Windows, or have Audio Units installed on macOS, those appear in the Audio category as well. When your video or audio plugins pile up, a search field makes the one you're after easy to track down.

### Video Effects

Each available category of video plugins builds a different sort of image effect—blurs, lighting effects, or stylization of various kinds. To preview a video effect ahead of placing it on a clip, make sure "Hover Scrub Preview" is ticked in the Effects option menu, then just rest your pointer on any thumbnail in the Effects tab and slide it across the thumbnail. The effect previews in the Viewer with its default parameters, scrubbing through whichever clip is selected in the Timeline. Where no clip is selected, it falls back on the clip currently under the playhead. To turn on a particular video effect for a clip, just drag the chosen effect's thumbnail onto a clip in the Timeline. On the Cut page, double-clicking the thumbnail will likewise put the effect onto the selected clip. To tune the effect's parameters, open the Effects tab in the Inspector.

Scrubbing over an Effect Thumbnail previews that effect in the Viewer.

### Audio Effects

Audio plugins let you treat your audio in various ways—shaping the tone with equalization, reworking dynamics through compression, or layering on effects such as echo, reverb, flange, or modulation. To turn on a particular audio effect for a clip, just drag the chosen effect's thumbnail onto a clip in the upper or lower Timelines on the Cut page; on the Edit page, drag it onto a clip sitting in an audio track. As soon as the effect lands on a clip, its audio plugin controls open so you can tune the plugin's parameters.

### Generators

The assorted video generators bundled with DaVinci Resolve can be previewed when you rest your pointer on any Generators-tab thumbnail. To bring a generator into your Timeline, just grab the thumbnail of the generator you want and set it into your Timeline on the Edit page, or into either the upper or lower Timelines on the Cut page.

To read more on putting all the bundled video and audio effects of DaVinci Resolve to use,

see Chapter 47, "Editing, Adding, and Copying Effects and Filters."

### Interactive Resolve FX and Fusion Effect Overlays in the Viewer

When you've applied a Resolve or Fusion effect that relies on on screen controls, those controls become usable within the Cut Page viewer. The way in: open the Tools panel on the Cut page and pick the Effects Overlay icon at the far right. Two options below let you handle either the Open FX or Fusion Overlays; pick the version that fits your effect. The on screen controls then show up in the Viewer.

A click on the Effects Overlay icon (circled) switches on the on screen controls belonging to Resolve or Fusion effects within the Cut Screen viewer.

### Clip Tools

Clicking the Tools button in the Viewer toolbar opens further categories of controls that let you put various effects on the current clip, or adjust whatever effect already sits on the current clip. Many of these effects' parameters carry matching onscreen controls that let you make visual adjustments right in the Viewer.

### The Tools button

### Shared Controls

Every effect category along the bottom of the Viewer carries two shared controls. Over at the far

left, a toggle control lets you turn an effect on or off without dropping whatever custom adjustments you've made. Over at the far right, a reset control returns every parameter inside a given category of controls to

its default settings.

The Toggle button (at left) and Reset button (at right)

### Transform

Pick Transform and onscreen transform controls surface, letting you work the image directly in the Viewer. A drag anywhere within the clip's bounding box adjusts pan and tilt; a drag on any diagonal corner resizes proportionally; a drag on any top/bottom/left/right side squeezes or stretches the width or height; and a drag on the center handle rotates.

### Onscreen Transform controls in the Viewer

TIP: As you drag a clip with the onscreen controls to reposition it, holding the Shift key down pins movement to just the X or Y axes. Those onscreen controls also match the editable parameters below, the same ones you can edit over in the Video Inspector as well as in the Edit Sizing mode of the Color page's Sizing palette: Zoom Width and Height: Enlarges the image or scales it down. Link the X and Y parameters to lock the image's aspect ratio, or unlink them to stretch or squeeze the image along a single direction. Position X and Y: Repositions the image inside the frame for pan and scan adjustments. X slides the image left or right; Y slides it up or down. Rotation Angle: Spins the image about the anchor point.

Pitch: Tilts the image toward or away from the camera about an axis that runs through the image center, left to right. Positive values send the image's top backward and draw its bottom forward. Negative values draw the top forward while sending the bottom back. Larger values stretch the image to a greater extreme. Yaw: Tilts the image toward or away from the camera about an axis that runs through the image center from top to bottom. Positive values draw the image's left side forward and send its right side back. Negative values send the left side back and bring the right side forward. Larger values stretch the image to a greater extreme. Flip Image: A pair of buttons lets you flip the image across different dimensions.

- Flip Horizontal control: Mirrors the image along the X axis, left to right.
- Flip Vertical control: Mirrors the clip along the Y axis, flipping it upside down.

### Crop

The Cut page carries a set of onscreen controls for cropping the image straight in the Viewer. Each side of the image has its own handle for cropping that side alone. These parameters are likewise editable in the Video Inspector and the Color page Sizing palette.

### Onscreen Crop controls in the Viewer

The Crop effects also match an extra set of cropping parameters, with one more control for softness: Crop Left, Right, Top, and Bottom: Trims the image's four sides by a chosen number of pixels. Because cropping a clip introduces transparency, whatever lies beneath shows through. Softness: Blurs a crop's edges. A negative value softens the edges within the crop box, whereas a positive value softens the edges beyond the crop box.

### Dynamic Zoom

The Dynamic Zoom controls, off by default, make pan and scan effects that zoom into or out of a clip quick and easy. A pair of onscreen controls lets you build a Dynamic Zoom effect. A green box marks where the animated transform starts in size and position, while a red box marks where it ends. Drag anywhere inside either bounding box to reposition the start or the end of the animated effect, and drag any corner to set the size at the start or end. A motion path surfaces to show you the motion being built. Touching the Dynamic Zoom controls turns dynamic zoom on automatically. These controls live in the Video Inspector as well.

### Dynamic Zoom controls in the Viewer

These controls match two parameters in the toolbar (Dynamic Zoom is editable in the Video Inspector too). Zoom/Pan/Angle Presets: Let you turn preset positions on or off for this effect's zoom level, pan location, and angle. Swap: This button flips the start and end transforms that make the dynamic zoom effect. Ease Buttons: Let you set how the motion these controls build speeds up. The choices are Linear, Ease In, Ease Out, and Ease In and Out. TIP: As you drag dynamic zoom outlines to reposition them, holding the Shift key down pins movement to just the X- or Y-axis.

### Composite

Two controls let you build transparency and apply composite modes for different compositing effects (also known as Blend modes or Transfer modes). These controls are editable in the Video Inspector too.

### Composite controls in the Viewer

Composite Modes: Composite modes blend two superimposed clips on the Timeline through different kinds of math to land on differing results, building transparency effects, lifting image exposure, and merging several clips into one image in many inventive and useful ways. Every Composite mode acts in concert with the Opacity slider. For a rundown of what the individual Composite modes do, see Chapter 50, "Compositing and Transforms in the Timeline." Opacity: Across a span from 0 (totally transparent) up to 100 (totally opaque), this slider renders a clip more transparent. Set under 100, the chosen clip blends with whatever video clip lies beneath it on the Timeline, following the Composite mode currently selected. Where no clip appears under the Timeline, the clip blends with black and behaves much like a fade.

TIP: Where a superimposed video or still image clip in the Timeline carries an alpha channel, that alpha channel automatically introduces transparency within the clip, compositing it against whatever sits in the track beneath. You don't need to do a thing for this to work.

### Speed
