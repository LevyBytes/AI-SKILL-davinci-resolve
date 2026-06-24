# Using Open Fx And Resolve Fx

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

## Overview

Covers: Color Page Effects; Using Open FX and Resolve FX.

## Color Page Effects

### Color Page Effects

## Using Open FX and Resolve FX

### Using Open FX and Resolve FX

This chapter walks through working with Resolve FX and Open FX plugins. With them you can reach for the filters bundled into DaVinci Resolve, plus filters sold by outside vendors, to build elaborate looks and corrections that the standard palette tools of the Color page simply can't produce on their own.

### Resolve FX

Resolve FX are the plugins bundled directly inside DaVinci Resolve. Their range is broad: everything from blurs and intricate color work, through stylized treatments and lighting looks, to sharpening and repair tasks that would be far too involved to pull off with the Color page's palette controls alone.

An image before/after using the Abstraction Resolve FX filter The majority of Resolve FX plugins are tuned for real-time playback. That tuning lets you drop in demanding effects like Lens Flares, Light Rays, Film Grain, or Warping and tweak them with instant, high-quality feedback, so you can preview each version of a look while you build it rather than sitting through a render or cache pass first. Naturally, performance can drop off if your footage is very high-resolution or raw, if your machine is aging, or if you stack many Resolve FX together at once, which is when you'll want to lean on either the Smart Cache or User Cache.

### Open FX

Open FX (OFX) is an open plugin specification whose purpose is to make it simpler to author cross-platform visual effects plugins that run inside many different host applications. Widely used packages in this space include BorisFX Sapphire and Continuum Complete, Red Giant Universe, and NewBlue TotalFX, each a staple across feature and broadcast pipelines. The catalog of Open FX packages keeps expanding year over year as more developers adopt the standard. Because DaVinci Resolve supports Open FX, plugins let you achieve plenty of stylized results that its native toolset would struggle or fail to deliver. With the appropriate plugin set in hand you can tackle lens flares, optical blurs and prism looks, lens warp correction, film and video grain and damage effects, dead-pixel fixes, and a good deal more.

One of the many Sapphire OFX plugins from GenArts

Each vendor supplies its own installer that takes care of setting up and licensing its Open FX plugins. After that's done, those plugins show up inside the Library of the Open FX panel, which you reveal by clicking the FX button near the upper-right of the Color page or Edit page Interface toolbar.

### Where are OFX Installed?

The OFX specification dictates that every OFX plugin on a given machine lands in one agreed-upon directory, which is what keeps the plugins usable across more than one host application. The directories differ by platform. Under macOS the path is /Library/OFX/Plugins; for a Windows host it becomes C:/Program Files/Common Files/OFX/Plugins; and on a Linux box it resolves to /usr/OFX/Plugins instead.

### Open FX Plugins Can Be Processor Intensive

Given the enormous span of looks they produce, certain third-party Open FX plugins demand a great deal of processing power, and that demand only grows when you pile several of them onto one grade. Should playback start to stutter under an especially costly effect, the Smart Cache can step in and automatically cache the nodes and clips carrying Open FX plugins. After they're fully cached, those clips will replay at full speed, right up until you alter that clip's grade again. To dig deeper into caching and into boosting DaVinci Resolve's overall responsiveness, see Chapter 8, “Improving Performance, Proxies, and the Render Cache.”

### Browsing the Effects Library

Every one of these bundled plugins is sorted into categories near the top of the Effects Library.

Click the Effects button to open the Effects Library Clicking the Effects button slides the Effects panel out from the right edge of the Node Editor to display the Library, shrinking the Viewer, Gallery, and Node Editor to free up space. The arrangement of the Effects Library is hierarchical. A given vendor's plugins sit beneath a header carrying that collection's name, perhaps further split into categories, with Open or Close arrows to the right of each category name that toggle its contents in and out of view so you can keep the tree tight or expanded however you prefer.

To open and close Effects categories, do one of the following:

- Hover the pointer over whichever header you'd like to expand or collapse, then click the Close or Open arrow sitting to the right of the category name.
- Option-click an Open or Close arrow to expand or collapse every header in one go. Because a number of Open FX collections run quite large, you can also reveal an optional Search field at the top of the Library to locate plugins fast by full or partial name.

To locate an Effects filter by name: 1 Click the magnifying-glass button up in the top right corner of the Effects panel. 2 Enter your search text into the Search field that pops up. Just a handful of characters is usually plenty to narrow the list down to only the plugins whose names contain that string.

The Library in the Effects panel showing available effects

### Stars indicate a flagged favorite effect

### Effects Library Favorites

Clicking the far-right edge of any Resolve FX or OFX filter marks it with a star, tagging it as a favorite. Once tagged, picking Favorites from the Effects Library option menu hides everything that isn't a favorite, so the only effects on display are the ones you reach for most. Clicking a star again removes its highlight to “de-favorite” that effect.

### Using Resolve FX and Open FX in the Color Page

What follows is a high-level look at the procedures for handling Open FX plugins inside the Color page. Methods of working with Open FX:

- To add an Open FX plugin to a node: Drag any plugin out of the Open FX Library and drop it on a node. Dropping it on a node that already carries a plugin replaces whatever was there before.
- To remove an Open FX plugin from a node: Two approaches exist for stripping an Open FX plugin off of a node.

Right-click a node that's showing the FX badge and pick Remove OFX Plugin from the menu that appears. Or click the trashcan icon beside the effect's name over in the Effects Inspector.

- To edit the parameters of an Open FX plugin: Pick any node carrying an FX badge, then open the Open FX Panel so the Settings list is displayed. A click on the Library button switches you back to the Library.
- To sample a color parameter within an Open FX plugin: Certain OFX plugins include a color swatch parameter, which surfaces an eyedropper button within the Settings. Click that eyedropper and the pointer becomes an eyedropper you drag to sample whatever is shown in the Viewer.
- To use Open FX onscreen controls in the Viewer: Choose any node bearing an FX badge, and its onscreen controls, assuming it has any, ought to show up in the Viewer. If they don't, confirm the Viewer mode drop-down is set to FX.

### Applying Resolve FX and Open FX Plugins

After locating an Open FX plugin in the Library that you'd like to put to work, two routes are open for bringing it into the Node Editor of the Color page. Your choice between them hinges on the role you intend the plugin to play.

### Adding a Plugin to an Existing Corrector Node

When your goal is to merge an Open FX plugin and a grade inside one node, just drag it and release it onto a fresh corrector node so the plugin's effect attaches there. Any node that has an Open FX plugin on it carries an FX badge down in its lower-left corner.

### A node with an Open FX plugin mapplied

A single node holds only one Open FX plugin at any given moment, yet by chaining several nodes together you can fold as many Open FX plugins into a grade as the shot calls for. Inside a corrector node, Open FX run after Motion Blur and Noise Reduction but ahead of everything else. So you're free to let Motion Blur and Noise Reduction condition the image first, then pass it along to the Open FX plugin. It also follows that whatever other tweaks you perform in that node act on the Open FX plugin's result. That said, the chief payoff of dropping plugins into corrector nodes is that secondary tools, a window, a qualifier, or a key, can confine the plugin's reach in just the same way they'd rein in any other correction made within a corrector node.

### Adding a Plugin as a New Corrector Node

To bring an Open FX plugin into your grade as a self-contained effect, drag any plugin out of the Open FX Library and drop it into the Node Editor, or onto one of your grade's connection lines, and Resolve spins up a new Corrector Node already carrying that Open FX plugin. From that point the node exposes all the extra inputs and Alpha connectors the effect requires. Since color correction nodes now cover every case, there's no longer any reason to build separate FX nodes. The upshot is tidier node trees and far less hand-wiring of links between nodes.

### Adding a Plugin as a Stand-Alone FX Node (Legacy)

Because the Resolve FX system was reworked to feel more natural and approachable, pulling an effect from the Effects Library into the Node Editor now spawns it on a standard corrector node rather than an FX Node. FX nodes have been deprecated as of DaVinci Resolve 18.5. Building an FX node serves no purpose any longer, since everything FX nodes once did has been folded into the standard corrector node. Even so, for older projects, or simply if the former workflow suits you better, you can still compel an FX node to appear by option-dragging the effect out of the Effects Library into the Node Editor in place of an ordinary drag.

### Resolve FX and Open FX Settings

Selecting a node that has a Resolve FX or Open FX plugin on it flips the Open FX panel over to its Settings, where every parameter tied to that plugin is laid out and ready to tune. Move any of the usual controls to shape how the plugin acts on the image.

### The parameters of the Glow Resolve FX

### Editing Effects Using the Full Screen Viewer

Since the Open FX panel is frequently too cramped to fit the complete control set of the more elaborate filters, it stays on screen even after you flip the Color page into Full Screen Viewer mode. Enter that mode by choosing Workspace > Viewer Mode > Full Screen Viewer (Shift-F). With this layout, precise work gets a lot easier because you're looking at a bigger image while every one of your effects sits in a taller panel along the side. TIP: While Full Screen Viewer mode is active you can still open and close the Node Editor whenever you need to jump between nodes during effects work.

In the Color page's Full Screen Viewer mode, the Settings panel stays available while you keep working

### Resolve FX and Open FX Onscreen Controls

On all three of the Edit page, Fusion page, and Color page, both Resolve FX and Open FX surface on-screen controls that let you adjust an effect visually. Within the Edit and Color pages, picking an Open FX plugin node, or a plugin in the Inspector that carries onscreen controls, automatically flips the Viewer over to Open FX Overlay mode with those controls ready at hand. Each plugin surfaces its own set of custom controls, so what you can steer, the effect itself or the image, varies with the plugin's purpose.

Adjusting the onscreen controls exposed by the GenArts Sapphire Glint Rainbow plugin Should the Viewer end up on some other onscreen control mode for any reason (say, displaying the Window or Image Wipe controls), getting back to the Open FX controls is always a matter of picking Open FX Overlay mode from the onscreen control drop-down menu beneath the Viewer.

TIP: During a session you'll often want to briefly hide or reveal the onscreen controls in the Viewer to get a clean, unobstructed view of the image you're working on. Rather than picking Off from the menu, you can flip any set of onscreen controls off and back on in an instant by pressing Shift-` (tilde).

### Keyframing Resolve FX and OFX in the Inspector

You can keyframe Resolve FX and Open FX across the Edit, Fusion, and Color pages. On the Edit and Color pages, though, the only way to keyframe them (as of this writing) is through the keyframing controls living in the Inspector. The good news is that the bulk of straightforward keyframing chores can be handled with the three buttons sitting to the right of any keyframeable parameter. You'll need a minimum of two keyframes for an effect to animate.

The Inspector's trio of keyframe controls, reading left to right: Previous keyframe, Create/Delete keyframe, Next keyframe

Methods of keyframing parameters in the Inspector:

- To add a keyframe: Pick a clip, open the Inspector, park the Timeline playhead on the frame that should hold a keyframe, then click the Keyframe button beside the Inspector parameter you intend to animate. After a parameter has at least one keyframe on it, any further changes you make to Inspector parameters, or with the onscreen Transform/Crop controls in the Timeline Viewer, will lay down new keyframes on their own whenever the playhead sits on a different frame.
- To move the playhead to the next or previous keyframe: Click the little left- or right-pointing arrow flanking a parameter's keyframe control, or hit Right-Bracket ( [ ) or Left-Bracket ( ] ), to send the playhead to the adjacent keyframe.
- To edit an existing keyframe of a parameter: Park the playhead directly over the keyframe you mean to change, then alter that parameter either from the Inspector or by way of the Timeline Viewer's onscreen controls.

Methods of changing keyframe interpolation in the Inspector:

- To change a keyframe to Static: (Color page only) A Static keyframe produces an abrupt, single-frame jump right at the keyframe it sits on, which works well for snappy, sudden effects. Use the next/previous keyframe controls to land the playhead on a frame that has a keyframe, then right-click the orange keyframe button and pick “Change to Static Keyframe.” The keyframe control turns into a round button, signaling the keyframe is now Static.
- To change a keyframe to Dynamic: Use the next/previous keyframe controls to bring the playhead to a frame holding a keyframe, then right-click the orange keyframe button and pick “Change to Dynamic Keyframe.” The keyframe control becomes a diamond button, signaling the keyframe is now Dynamic.

Methods of deleting keyframes and disabling keyframed effects:

- To delete a single keyframe: Open the Inspector, bring the Timeline playhead to a frame carrying a keyframe, and click the orange Keyframe button in the Inspector to remove it.
- To delete all keyframes for one parameter: Click the reset button just to the right of that parameter's keyframe control in the Inspector.
- To delete every keyframe across a whole parameter group in the Inspector: Click the reset button sitting beside the title bar of that group within the Inspector.
- To disable or enable a single parameter’s keyframed effect: Within the Timeline, click the toggle control at the left edge of a parameter's keyframe track. A white dot signals it's on, whereas the absence of a dot means it's dimmed and switched off.
- To switch a whole parameter group's keyframing off or on from the Inspector: Click the toggle control sitting at the left end of that group's title bar within the Inspector. Orange indicates the group is on; gray means it's off.

### Motion Tracking Resolve FX and Compatible OFX Plugins

Working with Resolve FX in the Color page, any Resolve FX carrying position parameters, such as Dent, Lens Flare, Light Rays (with “From a Location” chosen), Mirrors, Radial Blur, Ripples, Vortex, and Zoom Blur, can be motion tracked so it rides along with a moving subject in the frame, either through the simpler and more dependable IntelliTrack mode (covered just below) or the older point-based approach found in the Tracker palette's FX mode. To match-move a Resolve FX onto a feature by way of the FX tracker: 1 Build a fresh node and drag the Resolve FX filter you intend to use onto it so the effect is applied. For this walkthrough we're laying down a Lens Flare effect, which supplies the position parameters required to be match moved against the shot's motion, and we're picking the MIR-I 2.8/37 preset, which resembles a sun.

Applying a Lens Flare to the shot 2 Should it prove necessary, use the Viewer's onscreen controls or the X Position and Y Position sliders to nudge the Resolve FX effect to wherever you want it.

Moving the Lens Flare using the onscreen controls

3 Next, bring up the Tracker Palette and click the fx icon at top right. Opening the Tracker palette's FX tracker mode 4 Click the Add Tracker Point button over at the lower-left of the Tracker palette to drop tracker crosshairs onto the middle of the Viewer.

Adding a point tracker 5 Pull the crosshairs over to a high-contrast detail (a small object or a corner, for instance), then click the Track Forward button. Here, a rock sitting out at sea serves as a solid plane of motion for following a distant sun. No inner or outer box needs positioning or resizing as you go; all you do is drag the crosshairs so they're centered on the feature you mean to track.

Centering the point tracker over the feature you intend to follow 6 Now click the Track Forward button, and DaVinci Resolve traces the feature. The Resolve FX on that node travels right along with the track, and once tracking wraps up you're done.

A successful track 7 With tracking complete, you're free to nudge the Resolve FX anywhere you like to offset it from the track.

To read more on single-point tracking, consult the “Point Tracker Workflows” section over in Chapter 140, “Motion Tracking Windows.”

### IntelliTrack AI Point Tracker (Studio Version Only)

Driven by the DaVinci Neural Engine, the IntelliTrack point tracker lives in the FX tracker of DaVinci Resolve Studio. You can lean on the IntelliTrack setting to track your Resolve FX. Much like other AI-based tools, IntelliTrack leans on neither fixed rule sets nor heuristics; rather, it learns from real-world footage. That training makes it far less prone to stumbling in tricky situations, for example following a subject that briefly disappears behind an obstruction. In the majority of shots it proves both sharper and sturdier than the ordinary Point Tracker. Using IntelliTrack: Every bit of IntelliTrack's analysis runs out of sight, and the only thing you have to supply is to select the IntelliTrack setting, lay the tracking crosshairs over high-contrast regions on the one moving subject, and then tap any of the tracker's direction buttons. Choosing IntelliTrack mode for the window tracker on the Color page
