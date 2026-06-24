# Media, Color, Resolve Fx, Immersive

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

## Overview

Covers: Media; Color; Resolve FX; Immersive.

## Media

### Media

### Media Pool Tabbed Layouts

You can now pin tabs in the Media Pool that act as shortcuts straight to particular bins. Each tab sits in a dedicated tab bar along the top of the Media Pool, and the same bar appears in Media Pool windows on other pages. The feature works for ordinary bins along with smart and power bins. Spin up a new bin tab by right-clicking a bin and picking “Open as New Tab” from the contextual menu; clicking a tab's name jumps that bin open in the Media Pool right away. If you keep browsing inside an already-open tab, the active bin gets swapped for whichever bin you most recently selected.

### Media Pool Tabs, showing the right-click context menu

Right-click a tab and these choices appear:

- New Tab: Creates a new tab (Command T).
- Previous / Next Tab: Jumps to the tab before or after the current one along the tab bar.
- Close Tab: Shuts whichever tab is current (Command-W) (CTL-W on Windows and Linux).
- Close All Other Tabs: Shuts every tab apart from the one you're on.

Clicking the dropdown icon on the tab bar's right-hand side opens a tab search

Once a lot of tabs pile up, the dropdown on the tab bar's right edge lets you hunt down a particular one. Clicking that icon brings up both a roster of your open tabs and a search field. Keep in mind the search field looks only at tab names and won't surface any media pool clips.

### Thumbnail, List and Metadata Views Can Be Set Per Bin

You can now lock a bin into a chosen layout view (Thumbnail, Metadata, and List) so it always opens that way, no matter the prevailing bin view settings. That means, for instance, a bin packed with audio clips can always come up in List view, where thumbnails add little. Here's how to assign a layout view to a bin: 1 Pick the view you'd like the bin to always launch in. 2 Right-click the bin you want this view applied to. 3 Choose Always Open in XXX View, with XXX standing in for the view you selected. The choice persists across sessions in DaVinci Resolve, yet it leaves other users and machines on the same project unaffected.

### Star Ratings For Clips

Media Pool clips can now carry a rating of one to five stars assigned in the Shot & Scene Metadata Panel, and the same goes for still photos via several Photo Page controls.

Giving a clip a four star rating in the Shot & Scene metadata.

Set a rating by clicking the stars, and click an already-rated clip again to change it. To wipe a rating, click once more on its current level. Rating can serve to sort the media pool's List View, act as a Smart Bin criterion, and order an album within the Photo page.

### Cut Page Supports Smart Bin Views

In its Media Pool view, the Cut Page now supports both viewing and building Smart Bins. Reach any Smart Bin in a project through the Media Bin dropdown at the media pool's upper left, and make new smart bins by clicking the + sign within that same dropdown.

On the Cut Page, reach Smart Bins through the Media Bin dropdown menu over at the top left.

### Export Media Bin Thumbnails as a PDF

A Media Pool bin's thumbnails can now be written out to a PDF file. What you get is effectively a digital “contact sheet,” a fast way to glance at which clips a given bin holds. The PDF honors whatever thumbnail image size the Media Pool is using. By default it tries to pack the thumbnails onto a single-page PDF; for very large or custom-sorted bins, though, the export comes out as one tall, expanded document instead of being split into pages. To produce a PDF of a Media Pool bin's thumbnails: open the bin in question, open the Media Pool 3-dot option menu, choose Export as PDF from the context menu, and then pick a save location.

### A PDF export of a Media Pool bin

Choosing Export as PDF from the Media Pool option menu

### Automatic Smart Bin and Clip Filter for Offline Clips

A Smart Bin or Clip Filter (on the Color Page) can now be configured to round up every offline clip on its own. The result is a single bin you can use to relink media no matter where it sits across your project. To create an Automatic Smart Bin for Offline Clips: tick “Automatic smart bin for offline clips” under DaVinci Resolve > Preferences > User > Editing > Automatic Smart Bins.

### Use Custom Metadata in Smart Bins, Clip Filters, Data Burn-in and Naming Tags

Any Custom Metadata fields you built earlier in the Metadata Editor can now feed into Smart Bins, Clip Filters, Data Burn-ins and Tags as criteria.

### Customize Project Poster Frames

Straight from the Media Pool, you can now assign a custom Poster Frame to the Project thumbnail shown in the Project Manager. That makes it easy to tell your projects apart visually at a glance. To assign a Project Poster Frame: 1 In the Media Pool, choose the clip you want the new poster frame drawn from. 2 Scrub through that clip until the frame you're after appears in the thumbnail. 3 Right-click the clip and choose Clip Operations > Set Project Poster Frame.

### Transcription Column in List View

The Media Pool list view now includes a Transcription Column, present mainly as a visual cue. For a transcribed clip, only the opening few words show up in the Transcription column, yet searches against the transcription still match its full text.

### Keyboard Shortcuts to Set Thumbnail List or Metadata Views

Keyboard shortcuts can now be bound to flip the Media Pool view into Thumbnail or Metadata views. Look for these entries within the Keyboard Customization panel, under Panels > Media Pool > View Type.

### Reset Audio Clip Attributes

Clip Attributes now carries a simple icon for returning the Audio Clip Attributes to how they started. Click that red reset icon and the audio clip attributes snap back to their original state.

## Color

### Color

### MultiMaster Trim Manager

In DaVinci Resolve 21, the new MultiMaster Trim Manager streamlines how you handle HDR grade trims. The tool lets you steer several grade trims from one timeline. Your timeline's hero grade is the main node graph — Pre and Post Group plus node stack layers included — while each extra trim layer is a grade laid over that hero grade for a specific deliverable. So you might grade your master 4000 nit HDR timeline and, at the same time, set up and oversee trims for HDR 1000 and SDR Rec.709 output. Turn the MultiMaster Trim Manager on through Color > MultiMaster Trim Manager, which opens the window pictured below; to begin, flip the trim passes switch at the window's top left.

### The MultiMaster Trim Manager

From this window you can build and oversee as many trims as your timeline calls for. Use the relevant button to add or drop a trim. Rename one by clicking its name in the list and typing a replacement. You can also give each trim its own monitoring, output, and color management output color space settings.

Out of the box every trim switches on these node graphs: After Clip, then Before Group, plus After Group, alongside Before Timeline, and finally an After Timeline node graph. Any of those node graph elements can be toggled on or off through the 3-dot option menu of the Trim Manager window.

### The Enable Trim On Selector

Switch which trim is active through the 3-dot option menu in the Color page node graph. The chosen trim's name shows at the top of the node graph so you can see at a glance which trim is live.

Select Trim Pass in the Node Graph option menu You can also dial blanking per trim — at either a clip or timeline level — within the Output Sizing palette. For that, tick the Use Trim blanking checkbox so the blanking is set at the trim level. Bear in mind this works separately from the node stack layers you turn on for the main clip grade. Lastly, when output time arrives in the Deliver page, you can pick the exact Trim Pass grade to render for each output under video settings.

Within the Deliver page Video Render settings, choose the Trim Pass you want to output.

### Render AI Magic Mask 2 as an External Matte

A Magic Mask can now be rendered out as its own matte node. The rendered magic mask frames are then available externally to serve as an alpha source across all sorts of effects and uses. The external matte node produced by rendering the Magic Mask — to make it, pick Render in Place Magic Mask out of the 3-dot option menu and then choose where the cached frames should be rendered.

To build the external matte, choose Render in Place Magic Mask from the option menu

### Clip Groups Support Grade Versioning

Grade versioning now extends to clip groups, not just single clips. Versioning a clip group lets you build and juggle several looks shared across every common clip in that group. With node stack layers you can now keep multiple versions of your Pre-Clip and Post-Clip node graphs too. Members of a group can't hold differing group versions — choosing a version for the group sweeps across all of its clips. Create or change versions by right-clicking a grouped clip in the timeline and working through Groups and its submenus.

Making a fresh Clip Group version via the context menu of a clip on the Color page timeline

### Node Graphs can be Viewed as a Layer List

A fresh Layer List view now lives in the node graph, reached by clicking its icon at the node graph's upper left. The mode lays every one of your nodes out as a stacked list of layers, ordered from bottom to top according to your node order. The bottom-most layer is Node 1, and each further node piles on top as you create or rearrange it within the node tree. Using their respective icons, layers let you enable or disable, lock, and add or remove nodes. Further capability is slated for upcoming releases. Each layer also carries a preview thumbnail plus an icon list of the tools added to that node.

### The node graph in node view

The same graph in Layer View (top left arrow)

### Node Stacks Support up to Eight Layers

DaVinci Resolve 21 raises the ceiling on node stack layers, doubling it from four up to eight.

### Film Look Creator adds Aurora Preset and Fade Rolloff Controls

DaVinci Resolve 21 gives the Film Look Creator a new Aurora preset built to mimic a high-contrast, vivid film look that echoes today's common film stocks. The headline Aurora preset demonstrates how the core look is meant to be applied, although you may want to pile on extra contrast for the best outcome.

### The original footage

### The new Aurora core look applied

The effect also gained two new controls. Color Settings Fade Rolloff: This slider sets how softly the black level is halted at the fade threshold. Film Gate Softness: Controls how blurry the film gate's edges are.

### Shared Node Support for Stereoscopic 3D Clips

Just as ordinary 2D clips do, Stereoscopic 3D clips can now make use of Shared Nodes — a node whose changes propagate at once to every other instance of it within the grades of other clips.

### Customizable HDR and Nit Scopes Ranges

Within HDR projects, the HDR Parade scopes can now take custom ranges. Reshaping those ranges stretches the waveforms in the scope so you can zero in on one particular slice of the waveform.

Ticking the Scale Display Range box narrows the parade scope onto one particular stretch of the waveform.

### HDR Vivid Improvements

DaVinci Resolve 21 brings several enhancements to HDR Vivid support, among them:

- HDR Vivid tooling can now be driven from the DaVinci Resolve Mini Panel.
- A Color timeline filter that surfaces clips by their HDR Vivid analysis and trim status.
- A fallback to the last working trim whenever a manual trim runs past the HDR threshold.
- An HDR badge added to each timeline thumbnail once analysis is done.
- A Mastering display dropdown choice within the HDR Vivid project settings.
- A new Tone mapping mode option for low-light grading inside the Color page HDR Vivid controls.

### ACES AMF Improvements

Handling of ACES AMF sidecar files picks up further refinements in DaVinci Resolve 21.

- Shows the AMF transform name.
- Lets you point to a custom ACES AMF folder in project settings.
- Offers AMF tree selection via the project settings ACES AMF option menu.
- Adds support for look transforms at the project level.
- Includes an indicator showing the current working location.

### Reset Dolby Vision and HDR Analysis from the Option Menu

Both the Dolby Vision and the other HDR analyses can be cleared from the three-dot option menu sitting in each of their tabs on the Color page.

### Adobe RGB Colorspace and Gamma Support

Alongside the Photo page debut, DaVinci Resolve 21 adds support for the Adobe RGB colorspace and gamma.

### OpenFX 1.5 Color Management APIs for Colorspace Aware Effects

Support for the OpenFX 1.5 Color Management APIs has landed in DaVinci Resolve, promising sturdier, more precise color handling whenever you use or build OpenFX tools.

### Advanced Color Panel Controls for 2.39 and 2.4 Safe Area

For the Safe Area display, the DaVinci Resolve Advanced Panel now offers 2.39 and 2.4 aspect ratios. To get there, use shift down and the A/C Mode (Safe) selection found on the T-Bar panel, after which you select 2.39 or 2.4 directly on the center panel screens.

### Multiple User Projects Support Color Management Bypass

DaVinci Resolve 21 now lets you skip Color Management in a Multi User project exactly as you would in a Single User project. Right-click a clip in the Color timeline and pick Bypass Color Management from the context menu.

### Pasting Tracking Data Between Power Windows Retains Original Shape

With DaVinci Resolve 21, pasting tracking data from one Power Window to another now keeps the shape it started with.

## Resolve FX

### Resolve FX

### Resolve FX Video Collage Updated

The Video Collage Resolve FX now carries independent tile fill and border controls, much like the Picture in Picture effect covered above.

### Picture in Picture

Picture in Picture is a fresh Resolve FX that drops a smaller video window over a full-frame video clip beneath it. With Picture in Picture you can watch several subjects together, each lending context to the others. The trick goes back nearly to the dawn of television as an analog effect, and it now arrives fully reworked in the digital realm, packed with settings and parameters for tuning the exact look you're after. Start in either the Cut or Edit pages by laying out a timeline whose full-sized background video sits on the main track and whose intended smaller picture rides a track above it. Reaching into the effects tools, drop the Picture in Picture effect onto the upper clip — the one meant to shrink — and tweak it in the inspector. The inspector's parameters then let you land precisely the framing and shape you want. The Open FX Overlay view also lets you reposition, change the ratio of, and scale the Picture in Picture right inside the viewer. Arranging the clips on the timeline: the background footage sits on the lower track, with the smaller picture stacked above.

### RESOLVE FX

Another route is the Color page, where you bring the Picture in Picture effect into the node tree from the Effects Library; at first, though, the node's background renders black rather than transparent. To carry the transparency through to the timeline, an Alpha Output has to be added to the node graph. Right-click anywhere in the Node Graph and pick Add Alpha Output from the context menu, which drops a small blue output box onto the node graph; then wire the Picture in Picture node's blue alpha output across to that Alpha output to finish the effect, as the example below shows. Adding an Alpha Output, then routing the blue alpha channel of the Picture in Picture into it. The inspector's parameters then let you nail the precise framing and shape you want. As before, the Open FX Overlay view lets you move, re-ratio, and scale the Picture in Picture straight inside the viewer.

### RESOLVE FX

### The Picture in Picture output in the viewer

### Content

Tunes the source video feeding the smaller picture.

- Zoom: Pushes the PiP source in or pulls it out.
- Pan: Slides the PiP source side to side.
- Tilt: Shifts the PiP source up or down.

### Position

Sets where the Picture in Picture sits and how large it is. These same parameters can be nudged in the viewer by dragging while in Open FX Overlay mode.

- Position X/Y: Places the PiP window within the frame.
- Width: Sets how wide the PiP window is.
- Height: Sets how tall the PiP window is.

### Style

This set of tools shapes and lays out the window itself.

- Rounding: Sets how rounded the PiP window's corners are, running from right angles (0) up to a circle (1).
- Rotation: Lets you spin the PiP window.
- Opacity: Fixes the PiP window's opacity.
- Border: Ticking this box wraps a colored border around the PiP window and

activates the toolset below. Border Width: Sets how thick the window's border is. Border Color: Picks the hue of the window's border. Border Opacity: Sets how opaque the window's border is.

- Fill Matches Border: Tick this box to make the window's background take on the same color as the border.
- Fill: Tick this box to paint a background behind transparent content in the frame, which reveals the toolset below. Fill Color: Picks the fill's hue. Fill Opacity: Sets how opaque the fill is.
- Drop Shadow: Tick this box to lay a drop shadow beneath the PiP window, opening the toolset below. Strength: Governs how pronounced the drop shadow is. Color: Sets the drop shadow's hue. Drop Angle: Sets the direction from which the drop shadow falls. Drop Distance: Sets the gap separating the PiP window from its drop shadow. Expand: Enlarges or contracts the drop shadow. Blur: Controls how soft the drop shadow's blur is.
- Use Alpha: Tick this box to draw on the tool's alpha channel during compositing.

### RESOLVE FX

## Immersive

### Immersive

### VR180 and VR360 Standard Immersive Workflow Support

For standard immersive formats, DaVinci Resolve 21 now handles VR180 and VR360 workflows. That opens up editing and producing content for a broad range of VR headsets and platforms without locking you to one manufacturer. Within immersive timelines you can even blend VR180 and VR360 together, with cropping and refitting done automatically. That said, the wide spread of resolutions, formats, and frame rates that VR brings does call for some setup at the outset.

### Immersive Project Settings

Ahead of bringing VR media into the media pool, head into Project Settings and choose Master Settings > Immersive workflows > Standard Immersive. Flipping that switch turns on the immersive toolset in DaVinci Resolve. With the Standard Immersive Workflow chosen, set the resolution — VR180 uses a 1:1 ratio while VR360 uses a 2:1 aspect ratio.

### IMMERSIVE

Choose Standard Immersive for the Immersive workflows setting prior to loading clips into the media pool Clip Attributes With your project settings in place and all of your immersive clips imported into the media pool, you then have to flag them as VR clips by hand through the clip attributes. Select every clip, right-click one of them, and pick Clip Attributes from the context menu. Over in the Video tab of Clip Attributes, confirm that the Stereoscopic Mode and Projection Format attributes line up with your particular VR Camera's footage, then click OK.

Across all your clips, configure the Stereoscopic Mode and Projection format within Clip Attributes.

### Immersive Viewer

A new Immersive Viewer mode arrives in DaVinci Resolve 21, usable across the Media, Edit, Color and Fairlight pages. The mode swaps between an ordinary 2D view and, via Viewport mode, a simulated VR headset, so you can check your VR footage without strapping a headset on. While in this mode you can also click and drag within the viewer to spin the view around. Do note that it is purely a preview — it does not genuinely reorient your footage.

### IMMERSIVE

The Immersive Viewer (red rectangle) shown in LatLong view, presenting an equirectangular 360 image.

The Immersive Viewer (red rectangle) shown in Viewport mode, presenting that same 360 image as simulated within a headset.

### Immersive Viewer Selection

Determines the way VR content is presented within the Viewer.

- LatLong: Presents the content using an equirectangular projection.
- Viewport: Mimics a VR headset inside the viewer and lets you tweak head position and

field of view.

- Tilt: Pivots the head view about the Y (vertical) axis. Drag left or right within

the numeric field, or up and down inside the viewer, to shift the view.

- Pan: Pivots the head view about the X (horizontal) axis. Drag left or right

in the numeric field, or left and right inside the viewer, to shift the view.

- H. FoV: Adjusts the horizontal field of view to line up with the headset's FoV.

Clicking the little link icon ties the Horizontal and Vertical fields of view to one another.

- V. FoV: Adjusts the vertical field of view to line up with the headset's FoV. You can

tap that small link icon to bind together both the Horizontal and Vertical view fields.

### IMMERSIVE

### Immersive Transform

Choosing a Standard Immersive project setting brings the Immersive Transform tool to life in the Video Inspector. Its parameters point the VR video clip a particular way, letting you decide what greets the viewer when they first face forward in the headset. The tool is also handy for aligning two immersive clips so the cut between them feels visually right. Although the parameters are keyframable and can be animated, you're better off keeping them fixed and letting viewers tilt, pan, and roll through their own head movements — pushing forced directional motion in VR tends to bring on nausea.

### The Immersive Transform tool in the Video Inspector

### Immersive Transform

Sets where the footage starts out within the VR content.

- Tilt: Pivots the footage about the Y (vertical) axis. Drag the slider to reposition it.
- Pan: Pivots the footage about the X (horizontal) axis. Drag the slider to reposition

the footage.

- Roll: Pivots the footage about the Z (roll) axis. Drag the slider to reposition it.

### Immersive Delivery

The Deliver page now offers a new VR 180/360 delivery preset built to work with the broadest spread of VR headsets, Meta Quest among them. You're still free to adjust the settings to fit your specific headset more closely. This Delivery setting tacks extra VR format data onto the file name on its own, and that data cues the right playback behavior in most VR players.

### The VR 180/360 delivery preset

### IMMERSIVE

### Apple Immersive Workflows Now Support Foveated Rendering

Apple Immersive Workflows now let you employ and fine-tune the Foveated Rendering parameters. Foveated rendering boosts the perceived pixel density in one chosen region of the image while easing off on the rest. That way the scene keeps its full visual punch even as its size and bandwidth needs drop sharply — handy for, say, streaming across the internet. Reach the Foveation settings by opening a clip in the Color Page, choosing 3D from the toolbar, and then clicking the Foveation icon. Two tabs, Clip and Timeline, adjust foveation for a lone clip or for every clip on the timeline respectively, and the controls let you mark out the Foveation area within the immersive viewer.

### IMMERSIVE

The Foveation settings (circled red) in the Color Page

### Fusion LatLong Patcher and PanoMap Support for Standard Immersive Workflows

Within Fusion, reach for the LatLong Patcher, PanoMap, and related tools to work with and reshape VR180 and VR360 video sources.

- LatLong Patcher gives you a field of view you can tailor to your headset.
- Panomap brings immersive rotation along with ILPD retargeting.
