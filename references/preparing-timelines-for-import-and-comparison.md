# Preparing Timelines For Import And Comparison (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Preparing Timelines for Import and Comparison

Broadly put, to “conform” a project is to bring in a project exchange file from a different post-production application and have every clip in the imported timeline relink, on its own, to the high-quality media files that each clip points to. Should you wish to keep editing, color correct, or wrap up a project assembled in another application, you can bring it in through the EDL, AAF, or XML project exchange formats. As you conform a project, the imported project data drives how the Media Pool clips get laid into a timeline, which becomes the program headed for grading. The pages here lead you through getting timelines ready in other applications before you move them into DaVinci Resolve, and they cover which effects map to something in the DaVinci Resolve timeline. They close with directions for setting up a comparison between a reference movie and the Timeline.

### Preparing to Move Your Project to DaVinci Resolve

As you get ready to bring a project over from another NLE into DaVinci Resolve, a handful of steps will help keep your work tidier.

### Move Clips to the Lowest Video Track

To organize clips while cutting a scene, editors frequently rely on the several tracks an NLE provides. Handy as that is for offline editorial, it gets in the way once you are trying to conform, grade, finish, and render a project’s media as swiftly and cleanly as you can. With that in mind, it is wise to drop every clip that is not stacked or superimposed for a compositing operation down onto track V1 of the Timeline in your NLE. The result is a streamlined edit that brings several benefits. With less media riding in the Timeline, the project grows smaller to transfer and quicker to render. The colorist, too, is spared confusion, since this clears out “hidden” media that nonetheless ties to visible clips. Once the Timeline is reworked, it also helps to clear away whatever empty tracks remain. You could do that inside DaVinci Resolve, yet handling it in your NLE makes the project import process even simpler.

### Organize Unsupported Media Files

Based on your workflow and on which NLE you use, some clips may rely on formats that DaVinci Resolve does not support. Unsupported generators, media formats, and other effects constructs might just not show up in DaVinci Resolve, turning into unlinked clips instead. Knowing this ahead of time, you can shift all such clips onto dedicated tracks where they stay isolated, then switch those tracks off to hide the unsupported clips and make timeline navigation easier. It also spares the colorist from wondering why offline clips sit in the Timeline at 3 o’clock in the morning, right as a render is about to begin.

### Creating an Offline Reference Movie

Although the colorist on any given workflow will most likely build fresh grades from scratch, having a reference movie that shows whatever color corrections, filters, or effects the offline editor put on during the cut can still be worthwhile. You can bring this offline reference into a DaVinci Resolve project and lean on it as a split-screen reference any time a look or effect from the offline edit is in question. Offline reference movies prove handy as well while you conform a project on the Edit page. Once the project conforms, you can hold the project shown in the Record Viewer against the synced offline movie shown in the Source Viewer with it set to Offline mode. That makes scrubbing a project simple, letting you confirm each clip came in correctly and stays in sync. Further detail on working with offline reference movies comes up later in these pages.

### Mixed Frame Sizes and Mixed Codecs

Nearly every NLE lets you mix media of varying frame sizes, varying codecs, and varying frame rates without restriction. How DaVinci Resolve copes with these blends varies with the choices you have made in the Project Settings. Mixing Frame Sizes: Mixed frame sizes pose little trouble. The current project resolution is governed by the Set Timeline Resolution To parameter found in the Project Settings panel of the Project Settings. A clip whose frame size differs from the project gets resized per whatever option is picked in the Image Scaling panel of the Project Settings. And naturally, you can always resize any clip by hand should you want a particular adjustment. Every resize draws on DaVinci Resolve’s optical-quality resizing algorithms. To read more, turn to Chapter 152, “Sizing and Image Stabilization.” Mixing Codecs: Mixed codecs likewise present no issue, so long as the assorted codecs the imported project’s media uses sit within the roster of codecs and formats DaVinci Resolve handles. For the latest roster of supported codecs and formats, look at the Blackmagic Design support page for DaVinci Resolve, a list that gets refreshed often as new formats gain support.

### Mixed Frame Rates

Mixed frame rates are supported in DaVinci Resolve too, though one setting needs picking to get the best outcome for whichever NLE you import from. Out of the box, support for mixed clip frame rates is switched on through the “Mixed frame rate format” pop-up menu, which shows up in either the Master Project Settings or the Import AAF or XML dialog. The choices on that “Mixed frame rate format” pop-up exist so you can conform projects with the mixed frame rate calculation method belonging to the NLE the project was first cut in; NLEs differ in how they mix frame rates, and the approach in Final Cut Pro 7 is not the same as the one in Final Cut Pro X or Avid Media Composer. Changing this setting must happen before any media reaches the Media Pool; after the Media Pool fills up, the setting is locked.

### Mixed frame rate format selection

You will also find this Mixed frame rate format pop-up menu inside the Load AAF and Load XML dialogs. DaVinci Resolve picks a “Mixed frame rate format” pop-up menu setting on its own to fit the project file you bring in, yet there are times when you may override it. For projects coming from Final Cut Pro, pick either “Final Cut Pro 7” or “Final Cut Pro X” to suit the kind of project you import. By contrast, go with “Resolve” for projects arriving from Premiere Pro, Smoke, Media Composer, or other NLEs. Set “Mixed frame rate format” to anything other than None and DaVinci Resolve conforms and processes every Timeline clip to run at the project’s frame rate. To illustrate, 23.98, 29.97, 30, 50, 59.94, and 60 fps clips will all run at 24 fps when that is what “Timeline frame rate” reads in the Master Project Settings. Clips whose source frame rates differ get retimed to the Timeline conform frame rate. You can switch the Retime process used to render clips of differing frame rates per clip through the Retime Process parameter in the Edit page Inspector, or across the whole project through the Retime Process parameter sitting in the Frame Interpolation panel of the Master Project Settings. For detail on how each of the three available options behaves, see the “Frame Interpolation” section see Chapter 4, “System and User Preferences.” Pick “None” and clips whose frame rates do not equal the Timeline frame rate disregard their own frame rate and run at the Timeline rate, which yields faster or slower motion according to the gap between the original and Timeline frame rates. NOTE: Since DPX files frequently carry no frame rate data, or wrong data, in the header, you may have to pick None when conforming a project of image sequences so your media is read correctly.

Just how clips in mixed frame rate timelines render hinges on whether the Render Settings call for individual source clips or one single clip. Render the Timeline as ”Individual Source Clips” and every clip renders on its own at its native frame rate. Choose ”Single Clip” and every clip converts to the “Timeline frame rate” frame rate setting and renders out as one media file.

### Importing Effects when Conforming Edits

A portion of the effects carried inside XML, AAF, and EDL project files can be turned by DaVinci Resolve into their DaVinci Resolve equivalents. The chart below shows which effects come across, and for which project import formats. Effects that are unsupported get neither imported nor shown in DaVinci Resolve. Even so, most unsupported effects are held internally and written back into exported XML or AAF files, so those effects surface again in your NLE the moment the project is reimported.

Color Corrections Composite Modes Multiple Tracks Video Transitions Audio Transitions

### EDL No No No Yes No

### Opacity Settings

### No

### Position, Scale, Rotation No

### Flip and Flop

### No

### Pitch and Yaw

### No

### Linear Speed Effects

### Yes

### Variable Speed Effects

### No

### Still Image Clips

### No

### Freeze Frames

### No

### Nested Sequences

### No

### Linked Clip Audio

### Yes

### Mixed Frame Rates

### No

### Text Generators

### No

### FCP 7 XML No

### FCP X XML Yes

### AAF No

### Yes

### Yes

### Overlay only

### Yes

### Yes

### Yes

### Yes

### Yes

### Yes

### No

### No

### Yes

### Yes

### Yes

Yes, via 3D Warp

or Superimpose

### Yes

### Yes

### Yes, via 3D Warp

### Yes, via Flip, Flop, or

### No

### No

### Flip‑Flop effects

### No

### No

### Yes, via 3D Warp

### Yes

### Yes

### Yes

### Yes

### Yes

### Yes

Every supported format Every supported format All supported

in Resolve

in Resolve

formats in Resolve

### No

### No

### Yes

### Yes

### Yes

### No

### Yes

### Yes

### Yes

### Yes

### Yes

### Yes

### Yes

### Yes

### No

### Effects supported with imported AAF, XML, and EDL

### About Supported Color Corrections

As of this writing, Final Cut Pro X XML projects alone can export color correction data that arrives in DaVinci Resolve as primary grades. For plain reasons, bringing color correction in runs only one direction, and imported color corrections cannot be sent back out to Final Cut Pro. Color adjustments imported from Final Cut Pro X land on the Color page as primary corrections. To pull color correction information from other applications there are further routes, using ColorTrace to import grade data out of CDLs (Color Decision Lists). For deeper coverage, turn to Chapter 186, “Copying and Importing Grades Using ColorTrace,” and its “Copying Grades Using ColorTrace” section.

### About Supported Transitions

When it comes to transition support in DaVinci Resolve, EDLs allow the least, since only Cross Dissolves get read. As an EDL imports into DaVinci Resolve, every other transition in it is turned automatically into a Cross Dissolve running the same length. By contrast, DaVinci Resolve will bring in ten distinct transitions from XML project files made by Final Cut Pro X and legacy Final Cut Pro 7, or nine distinct transitions from AAF files made by Avid Media Composer or Symphony.

The columns cover Clock Wipe, then Center Wipe, then Cross Dissolve, then Additive Dissolve, then Dip to Color Dissolve, then Edge Wipe, then Venetian Blind Wipe, then Cross Iris, then Diamond Iris, then Oval Iris Transitions that import from EDL, XML, and AAF

EDL No No Yes No No No No No No No

FCP XML Yes Yes Yes Yes Yes Yes Yes Yes Yes Yes

AAF Yes Yes Yes No Yes Yes Yes Yes Yes Yes

### Transition Names

So you can ready projects for export, bear in mind that transition names are not the same across XML and AAF project files. Below are the supported transitions under the names they carry in Avid Media Composer and Symphony.

### Dip to Color Dissolve Edge Wipe Center Wipe

### Dip to Color effect in the Blend category

Within the Edge Wipe category, the Horizontal/Vertical/Lower Left/Lower Right/Upper Left/Upper Right Diagonal effects, plus the Horizontal Open and Vertical Open effects, also belonging to that Edge Wipe category

### Clock Wipe

### Clock effect in the Shape Wipe category

Venetian Blind Wipe maps to the Vertical Blinds and Horizontal Blinds effects found under the Shape Wipe category

Cross Iris

### 4 Corners effect in the Shape Wipe category

### Diamond Iris

### Diamond effect in the Shape Wipe category

### Oval Iris

### Circle effect in the Shape Wipe category

### About Supported Opacity, Position, Scale, and Rotation Settings

Bringing in XML project files made by Final Cut Pro X, by Premiere Pro, or by legacy Final Cut Pro 7, DaVinci Resolve will accept Opacity, Position, Scale, and Rotation settings. The imported Composite and Transform settings for any clip turn up either in the Edit page Inspector or in the Edit Sizing mode of the Color page’s Sizing palette. Where those settings carry keyframes, the animation comes through in DaVinci Resolve. As it brings in AAF files from Media Composer or Symphony, DaVinci Resolve accepts Opacity, Resize, and 3D Warp effects, turning them into Pan, Tilt, Zoom, and Rotate settings inside DaVinci Resolve, found in the Edit page Inspector or the Edit Sizing mode of the Color page’s Sizing palette.

### About Flip and Flop Support

As it brings in AAF project files from Media Composer or Symphony, DaVinci Resolve turns Flip, Flop, and Flip-Flop effects into the matching horizontal and vertical Flip toggles, found in the Edit page Inspector or the Edit Sizing mode of the Color page’s Sizing palette.

### Pitch and Yaw

As it brings in AAF files from Media Composer or Symphony, DaVinci Resolve accepts Pitch and Yaw 3D Warp effects and turns them into matching Pitch and Yaw settings inside DaVinci Resolve, found in the Edit page Inspector or the Edit Sizing mode of the Color page’s Sizing palette.

### About “Ken Burns Effect” and Dynamic Zoom

Bring in a Final Cut Pro X project whose clips lean on the Ken Burns effect to build pan and scan animation, and the Dynamic Zoom parameters (which sit in the Edit page Inspector once a clip is selected) for every affected clip get filled with a matching animated effect.

### About Speed Effects

Speed effects from various applications can come into DaVinci Resolve, though how much speed effect support you get changes with the project format.

- EDL: From EDLs, DaVinci Resolve takes in linear speed effects only.
- XML: Both linear and variable speed effects come into DaVinci Resolve when you

bring in XML project files authored by Premiere Pro, by Final Cut Pro 7, or by Final Cut Pro X. Starting with DaVinci Resolve version 11.1, XML from Final Cut Pro X can additionally report whether frame blending or optical flow is in use, along with detail on the Bezier curve transitions of speed effects.

- AAF: Both linear and variable speed effects come into DaVinci Resolve when you bring in AAF files from Media Composer or Symphony that rely on Timewarp effects.

DaVinci Resolve converts variable-speed speed effect data from other applications with high fidelity, laying down a single speed keyframe on every frame of each affected clip. You might still notice slight differences between the speed effect that results in DaVinci Resolve and an offline reference movie exported from the source NLE, should you have left the Retime Process setting on a speed interpolation type other than the one the source NLE used. Put another way, if you made a Timewarp speed effect in Media Composer that uses FluidMotion for smooth slow motion, you will want to switch either the project-wide or the clip-specific Retime Process setting to Optical Flow so DaVinci Resolve’s speed effects line up as closely as possible with those in Media Composer.

To read more about speed effects in DaVinci Resolve, see Chapter 51, “Speed Effects.”

### About Nested Sequences and Compound Clips

Compound clips from Final Cut Pro X and nested sequences from legacy Final Cut Pro 7 can both come into DaVinci Resolve, where each shows up as a compound clip across both the Timeline and the Media Pool. Compound clips holding mixed frame rates work in DaVinci Resolve, as do multicam and A/V synchronized clips out of Final Cut Pro X, all of which DaVinci Resolve represents as compound clips. For deeper coverage of building and working with compound clips inside DaVinci Resolve, turn to Chapter 43, “Take Selectors, Compound Clips, and Nested Timelines,” specifically its “Compound Clips” section.

### About Supported Composite Modes

Bringing in XML project files made by Final Cut Pro 7, by Premiere Pro, or by Final Cut Pro X, DaVinci Resolve will accept eight distinct composite modes. As it brings in AAF files from Media Composer, the Overlay composite mode comes across whenever the source AAF file carries a Superimpose effect.

Add Subtract Difference Multiply Screen Overlay Lighten Hardlight Softlight Darken

### FCP 7/X XML

Yes Yes Yes Yes Yes Yes Yes Yes Yes Yes

### Supported composite modes with imported XML and AAF

### AAF

No No No No No Yes No No No No

### About Supported Still Image Formats

Still image files lasting more than a single frame, in the TIF, JPG, PNG, DPX, TGA, and DNG formats, will come into DaVinci Resolve when they sit inside Final Cut Pro X, Final Cut Pro 7, or Premiere Pro XML files, as well as AAF files exported out of Media Composer. On the DaVinci Resolve Timeline these clips behave as ordinary clips. Exporting still images, however, is confined to the Final Cut Pro 7 and Final Cut Pro X XML formats.

### About Supported Alpha Channels

Media carrying embedded alpha channels works for any project as long as its media format is one DaVinci Resolve handles; that covers TIFF, OpenEXR image sequence formats, and four-channel QuickTime formats like ProRes 4444, DNxHR 444, and QuickTime Animation. Those alpha channels switch on by themselves and serve compositing right inside the DaVinci Resolve Timeline. In round-trip workflows you can export alpha channels while rendering individual source clips. Render a program as a single clip, though, and every composited effect renders together into one output media file.

To read more about rendering clips that carry alpha channels, see Chapter 185, “Delivery Effects Processing.”

### About Imported Text Effects

Text generators come into DaVinci Resolve when you bring in XML project files from either Final Cut Pro X or Final Cut Pro 7. Every imported text effect lands on the DaVinci Resolve Timeline as a Basic text generator. Which formatting parameters carry over is partial rather than complete, varying with the project file format you import.

### About Imported Audio in AAF Projects

No matter how you combine audio track types, the channel map order, MXF alongside QuickTime files, plus rendered or unrendered clips, the whole lot should come in without trouble. NOTE: While exporting an AAF project, DaVinci Resolve can write mono media into stereo tracks. Preparing Unsupported Clips and Effects You Want to Grade Where your chosen NLE holds an unsupported effect that you still want to carry into DaVinci Resolve for grading (clips bearing effects filters native to one particular NLE, for instance), here is a straightforward workflow. To “bake” an effect into a clip bound for DaVinci Resolve: 1 Write that clip out as a self-contained media file using whichever DaVinci Resolve-compatible mastering codec you like. 2 Bring the resulting media file back into your project. 3 Cut it into your project’s timeline in place of the original effects clip. 4 Write out a version of the resulting sequence for DaVinci Resolve to use. This works well for prepping the titles and effects of projects you intend to finish in DaVinci Resolve. Make self-contained media files for every title clip and effect, and those elements import smoothly and easily, after which you can export a full, texted version of your program out of DaVinci Resolve. What is more, when a composited clip leans on unsupported effects (say, a filtered still image with animated position superimposed via the Overlay composite mode at 70% opacity), a fine way to ready it for XML export to DaVinci Resolve is to switch the composite mode to Normal, set Opacity to 100%, then write the clip out as a self-contained QuickTime movie. Bring the result back, cut it into the Timeline to stand in for that original superimposed clip, then return its composite mode to Overlay with Opacity at 70% so the original settings are matched. The unsupported effects are now “baked” into the clip, yet the effects DaVinci Resolve does handle stay live and open to readjustment in context as you grade.

### Verifying Imported Timelines Using Offline References

For holding two versions of a program against each other, DaVinci Resolve offers a dedicated interface. It removes any need to cut a rendered timeline in as a superimposed clip within your own timeline and brings many other features that aid the comparison without crowding your timeline. Switch the Edit page Source Viewer to Offline mode and you can set an Offline Reference Clip or Timeline beside a timeline you have open, both playheads ganged, shown side by side or as a split screen, a box wipe, or a difference operation, every option visible through your video output device. Play the Timeline and the Offline Reference Clip or timeline runs right along with it, so differences between the two are easy to catch. IMPORTANT: Be certain the media you imported or are using as an Offline Reference Clip carries a valid timecode track whose start time lines up with the timecode of the Timeline you compare against; otherwise an offset opens up between the Timeline and offline reference that makes comparing them hard to outright impossible. Small offsets you can patch using an offset field that the Source Viewer provides during offline mode, yet large ones simply prove impractical to fix.

### Why Set Up An Offline Comparison?

No matter how you arrange an offline reference, it gives you a handy way to weigh two versions of a program against each other. Several motives exist for holding an Offline Reference Clip up against a timeline:

- Verifying the clip order: When you are not certain you have cleanly settled reel conflicts or other snags that cropped up while conforming a timeline, you can set each edit beside the program’s offline version to catch problems and pin down which media truly belongs to any clip.
- Recreating effects: Where offline effects exist, such as temporary grades done in the NLE or pan and scan transforms you want to check, Offline reference mode lets you split-screen your present grade against the Offline Reference Clip on the Color page.
- Comparing two versions of a timeline: You can visually hold one timeline beside another version of itself to catch differences worth evaluating.
- Filling holes in timelines with missing or unlinked clips: Living under Preferences > User > Editing > General settings, a pair of options, namely “Show offline clips through conform gaps” plus “Show offline clips through missing clips,” direct DaVinci Resolve to surface Offline Reference Clip media that plugs Timeline gaps or stands in for the contents of unlinked clips. You generally reach for this in a pinch, when a screening or review session has to go ahead even though some media is missing for one reason or another.

To read more, see Chapter 4, “System and User Preferences.”

NOTE: As a rule, the flattened version of the program handed to you runs a low-quality codec and holds effects and color correction that are not final, which is exactly why it goes by Offline Reference Clip.

### Assigning a Clip or Timeline for Offline Comparison
