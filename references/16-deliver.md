# Delivery Effects Processing, Using The Deliver Page

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

## Overview

Covers: Deliver; Delivery Effects Processing; Using the Deliver Page.

## Deliver

### Deliver

## Delivery Effects Processing

### Delivery Effects Processing

The way that various video effects get treated as you drive the Deliver page controls is the subject of this chapter.

The handling of effects in your finished output hinges on the choice between Single Clip and Individual Clips mode.

### When Rendering a Single Clip or When Outputting to Tape

No matter whether you produce a QuickTime or MXF master of the project as one clip, generate a DPX image sequence destined for film, or send signal straight to tape, every supported compositing, speed, and transform effect gets processed by DaVinci Resolve and “baked” into the resulting media. Anything unsupported is simply skipped over, never visible, and leaves no mark on the media you render and output.

### When Rendering Individual Source Clips for Round-Trip Workflows

When your goal is to render separate media files so the project can return to an NLE or finishing application for the last stages (laying in titles and similar effects ahead of delivery), DaVinci Resolve treats each category of effect on its own terms. Anything unsupported stays hidden inside DaVinci Resolve. That said, the underlying effects data is held onto internally, so once you export an XML or AAF file headed back to whichever NLE you prefer, those effects come back into view, sitting atop the color corrected media you rendered out of DaVinci Resolve and returned. The effects DaVinci Resolve actually supports — composite modes, opacity settings, speed effects, transitions and the like — get a separate treatment. While you can see them inside DaVinci Resolve during your session, they are never “baked” into the finished media you render ahead of handing it back to the NLE or finishing application. Rather, only the slice of each media clip your project draws on becomes its own rendered file, and the XML file you export from DaVinci Resolve carries every bit of effects metadata required to rebuild the rendered footage into a timeline whose Final Cut Pro effects ride on top of DaVinci Resolve-graded media.

### Color Corrections Composite Modes

### Alpha Channels

Transitions Opacity Settings Position, Scale, Rotation Linear Speed Effects Variable Speed Effects Long Duration Still Images Freeze Frames

The per-format status values are tabulated below, one value per cell.

| Format           |           |           |                     |           |           |             |           |           |     |          |
| ---------------- | --------- | --------- | ------------------- | --------- | --------- | ----------- | --------- | --------- | --- | -------- |
| EDL              | N/A       | N/A       |                     |           |           |             |           |           |     |          |
|                  | N/A       |           |                     |           |           |             |           |           |     |          |
|                  | Sent Back | N/A       | N/A                 | Sent Back | N/A       | N/A         | N/A       |           |     |          |
| FCP 7            | N/A       | Sent Back | Optionally Rendered | Sent Back | Sent Back | Conditional | Sent Back | Sent Back | N/A | N/A      |
| FCP X            | Rendered  | Sent Back | Optionally Rendered | Sent Back | Sent Back | Conditional | Sent Back | Sent Back | N/A | N/A      |
| Premiere Pro     | N/A       | Sent Back | Optionally Rendered | Sent Back | Sent Back | Conditional | Sent Back | Sent Back | N/A | N/A      |
| Media Composer\* | N/A       | Rendered  | Optionally Rendered | Sent Back | Sent Back | Conditional | Sent Back | Sent Back | N/A | Rendered |

- These effects come back solely during AAF round trips in the case where you refresh an AAF file that already exists, as opposed to producing a brand-new AAF file. What the table illustrates is which effects DaVinci Resolve renders versus which ones are handed back across the various round trip workflows.

Once the project has been reimported into your NLE or finishing application, you can tweak those effects again as you wrap up the program, with no requirement to re-render individual clips inside DaVinci Resolve. IMPORTANT: The single case where media and effects are not carried through round-trip workflows is nested sequences originating in Final Cut Pro 7 and Media Composer, which DaVinci Resolve cannot read; any XML and AAF files that hold nested sequences will fail to import. Conversely, projects from Final Cut Pro X that include compound clips do import fine.

### More About Rendering Speed Effects

Should your project include speed effects, keep in mind that DaVInci Resolve has the option to process them through Optical Flow, which yields crisp slow motion and fast motion results that come ready-made out of DaVinci Resolve. When Optical Flow processing inside DaVinci Resolve meets your needs, a round-trip export may be unnecessary if your sole motivation was handing slow motion clips to a separate application for rendering; choosing Single clip mode for the Timeline “bakes” the speed effects in according to the project-wide settings, or the per-clip values if you assigned individual Retime Process settings to particular clips. On the other hand, when your aim is to pass unrendered speed effects along to a different application, rendering in Individual source clips mode ensures that the entire span of every original media clip is rendered, with the speed effect itself carried inside the exported XML, AAF, or EDL file. NOTE: DaVinci Resolve tacks three frame handles onto any clip carrying speed changes, plus onto rendered clips whose frame rate differs from the project’s. The purpose is to ease reconform in NLEs that need handles stretching past the genuine length of each such clip.

### Determining the Rendered Output Resolution of Clips in Mixed Timelines

As a rule, when you render individual source clips, each one comes out at either the project resolution or whatever the Resolution dropdown in the Render Settings dictates (that dropdown takes precedence over the project resolution), and clips whose size differs from the project resolution are scaled or left alone per your picks in the Image Scaling panel of the Project Settings. That said, when you generate dailies for a project whose clips carry mixed resolutions, you have the choice to keep each clip at its native resolution by enabling the “Render at source resolution” checkbox within the Video group of controls.

### Rendering Edit and Input Sizing Adjustments

Whether sizing ends up baked into your delivered media is governed by the “Disable sizing and blanking” checkbox found among the Advanced Settings options of the Render Settings panel. Sizing and blanking can be switched off whether you render the current Timeline as one clip or render individual clips. Leave “Disable sizing and blanking output” off and the following all get written into the finished media through the optical-quality sizing algorithms DaVinci Resolve provides: Output Blanking; the sizing adjustments made on the Cut and Edit pages; the Color page’s Input and Output Sizing adjustments; and Image Stabilization. That is the preferred route once your sizing adjustments are signed off and locked, and you intend to “bake” them into the media you deliver. Switch “Disable sizing and blanking output” on instead and those same items — Output Blanking, the Cut and Edit page sizing work, the Color page Input plus Output Sizing changes, along with Image Stabilization — stay out of the render; every clip then emerges either at the source resolution when “Render at source resolution” is active in individual clips mode, or at whatever resolution the Timeline or project currently specifies. The sizing adjustments you applied are still written into the XML or AAF file you export, though. That suits workflows in which the editor plans to keep refining sizing, measured against the clips’ original dimensions, after you have handed over the graded project. Bear in mind that to render Input Sizing adjustments into your output media, the “Force sizing to highest quality” checkbox makes certain DaVinci Resolve picks the top-tier sizing setting even when you have briefly opted for a quicker, lower-quality choice to suit a slower machine. NOTE: “Disable sizing and blanking output” leaves untouched any transform operations occurring inside the Fusion page, and likewise does not stop transforms produced by an Open FX or Resolve FX plugin attached to one or more clips on the Cut, Edit, or Color pages. Every one of those effects keeps getting rendered into the finished output.

### Rendering Mixed Frame Rate Timelines

DaVinci Resolve accommodates mixed frame rates as soon as you pick anything besides none in the “Mixed Frame Rate format” dropdown menu. You will find that dropdown two places: under Conform Options within the Project Settings’ General Options panel, or over in the Import AAF or XML dialog. Pick the entry matching the application you trade projects with (or DaVinci Resolve itself when you stay entirely inside DaVinci Resolve), and DaVinci Resolve will conform and process every clip on the Timeline so it plays at the rate chosen in the “Timeline frame rate” dropdown menu. By way of illustration, clips at 23.98, 29.97, 30, 50, 59.94, and 60 fps would each play at 24 fps if the “Timeline frame rate” in the Master Settings panel of the Project Settings is set there. The way clips on mixed frame rate timelines get rendered hinges on whether the Render Settings call for Individual source clips or a Single clip.

- Individual source clips: Every clip renders on its own at the frame rate it originally had.
- Single clip: Every clip is brought to the “Timecode calculated at” frame rate and written out as one media file. Conversion follows whichever method the Retime process dropdown specifies — that dropdown lives in the Project Settings under the Master Settings panel — unless a per-clip Retime process setting in the Video inspector overrides the project-wide choice. Selecting Optical Flow processing gives you the best-quality conversion DaVinci Resolve offers.

### Export Alpha Channels in Individual Clips Mode

You will only see this option when the target media format can hold alpha channels. Where your media carries an Alpha channel, the Export Alpha checkbox — sitting in the render settings’ Video panel — can be enabled whenever you render individual source clips. With that enabled, DaVinci Resolve outputs clips containing alpha channels under one of two conditions:

- If the clip’s source media already has an Alpha channel baked in, that embedded Alpha channel is carried over to the rendered copy of the clip.
- If the clip’s grade routes a key into an Alpha output, that Alpha output becomes an Alpha channel on the rendered clip.

Either way, exporting Alpha channels is possible solely when you render individual source clips into an RGBA format like TIFF, OpenEXR, ProRes 4444, ProRes 4444 XQ, or DNxHR 444.

### Export Alpha Channels in Single Clip Mode

In Single Clip mode, DaVinci Resolve will render Alpha channels provided the chosen codec is one that handles an Alpha channel (i.e., ProRes 4444, DNxHR 444, etc.). That makes it possible to attach one Alpha channel across a whole timeline at export time instead of working clip by clip. To Render an Alpha Channel in Single Clip Mode: 1 Switch the Render Settings to “Single Clip” mode. 2 Within the Video tab’s Codec and Type selection boxes, pick a codec capable of an Alpha channel. 3 Tick the “Export Alpha” checkbox that shows up beneath the Frame rate selector. 4 Where the codec permits it, you can chose the Alpha Mode type; Premultiplied serves as the default. Should the codec you picked lack Alpha channel support, no “Export Alpha” box will surface as a choice.

## Using the Deliver Page

### Using the Deliver Page

After grading is complete, the project still has to be rendered or sent to tape so it can reach your client. That is precisely the role of the Quick Export window and the Deliver page. The pages ahead cover working with Quick Export, navigating the Deliver page interface as a whole, and offer some background on how DaVinci Resolve outputs effects across various scenarios.

### Using Quick Export

Plenty of jobs do not call for an elaborate delivery configuration. For those moments when a fast export is all you want and the Deliver page’s full capability is overkill, File > Quick Export lets you pick from an assortment of export presets to send your program out from any DaVinci Resolve page. Quick Export can even push your program straight to one of the supported video sharing services — among them YouTube, Vimeo, and Frame.io. Your own presets can be added to the Quick Export window too. To use Quick Export: 1 (Optional) On the Cut, Edit, Fusion, or Color page, mark In and Out points along the Timeline to isolate the portion of the current program you want exported. With no timeline In or Out points placed, the whole timeline goes out. 2 Choose File > Quick Export. 3 From the top row of icons in the Quick Export dialog, pick a preset and hit Export. 4 In the export dialog, point to a directory and type a file name, then click Save. A progress bar dialog comes up to indicate the export’s remaining duration.

A custom preset as it appears in the Quick Export Dialog. Here is how you build a fresh Custom Preset and place it into Quick Export: 1 Over on the Deliver page, choose Custom Export within the Render Settings, then tune the Video, Audio, and File settings for the preset you are building. Custom Presets can only be built from Single Clip settings, never Individual Clips. 2 From the Render Settings 3-dot option Menu, choose Save as New Preset. 3 Enter a name for the new Preset and pick a preset icon to stand for it. 4 Tick the Add to quick export box. 5 Click Save. From now on your preset and its icon appear in the Quick Export Dialog on every DaVinci Resolve page, and they also join the Render Settings on the Deliver Page.

The Quick Export Dialog with its List View icon circled. To switch the Quick Export choices over to List View: 1 Bring up the Quick Export Dialog. 2 Within the Render Settings, click the List View icon.

### Assign Icons to User Presets

As you build a new Custom Preset on the Deliver page, beyond supplying a name you may now select an icon from the list so it can stand for the preset in both the Render Settings and the Quick Export dialog.

Creating a new Custom Preset in the Deliver page

### The Deliver Page

Five functional zones make up the Deliver page, and each one lets you configure a separate aspect of a render or a tape output.

### Deliver page

### The Interface Toolbar

Running along the top edge of the Deliver page sits a toolbar whose buttons toggle the visibility of various interface sections. Reading left to right, those buttons are:

### The Interface toolbar

Delivery full/half height button: Expands the Render Settings panel so it occupies your display’s entire height when you want more room to scroll through the various render settings, trading away some Timeline width in return. Render Settings: This panel enumerates every render setting on offer for configuring rendering jobs in DaVinci Resolve. Out of the box you get a brief list, with further options revealed once you click “Advanced Settings.” Tape: Switches the Deliver page over to Tape Output mode.

Clips: Toggles the Thumbnail timeline shown above the Deliver page timeline Render Queue: A roster of every job you have queued for rendering in the current project. Jobs that were rendered earlier stay put in the queue — handy for reference or for re-rendering them later — until you remove them by hand. Render Queue full/half height button: Stretches the Render Queue across your display’s full height when you need extra space to list render jobs, again at the cost of a slimmer Timeline.

### The Render Settings

Within the Render Settings live the adjustable controls that dictate how DaVinci Resolve renders media out. Selecting the Tape option greys these controls out. The Render Settings break down into four broad sections:

- Render Presets: Up top sits a scrollable strip of icons from which you can grab one of several presets to rapidly configure the kind of render you are after. Picking the Custom option reveals every render setting so you can build a render by hand.
- Render Location: Clicking the Browse button brings up a dialog for selecting the volume and directory you will render into.
- Render: A pair of options lets you render the Timeline’s whole selected region as one clip fit for review or mastering, or as a run of individual clips better aligned with round-trip workflows. Whichever you select shifts which render settings show up underneath.
- Video, Audio, and File Render Settings Panels: Every remaining render setting is spread across three panels. At the top of the Video and Audio panels, checkboxes let you turn off video export on its own (when only the audio should go out) or turn off audio export on its own (when only the video should go out).

For a fuller account of all these settings, refer to Chapter 187, “Rendering Media.”

### Render Settings

### Rendering Files vs. Outputting to Tape

Since the Deliver page serves two purposes, the Tape button in the Interface toolbar is what you use to switch between rendering files and sending output to tape. Pressing it swaps the Viewer’s usual controls for tape controls.

### Render or Edit to Tape modes

### The Deliver Page Timeline

The Timeline on the Deliver page is where you mark out which clips to render or send to tape and which version of each clip should be output. This Timeline is built from a Thumbnail timeline up top — toggled by the Clips button — that makes picking single clips or clip ranges for rendering straightforward, plus a more conventional timeline beneath it on which you place In and Out points to render any arbitrary stretch of your program. A Timeline toolbar handles setting the render range, tweaking how the Timeline looks, and zooming in or out.

### The Deliver page’s Timeline and Thumbnail timeline

TIP: Hitting Shift-Z scales the whole program to fill the Timeline’s available width.

### Filtering the Thumbnail Timeline

On the Deliver page, the Thumbnail timeline also carries a Timeline Filter dropdown, sitting just to the right of the Clips button within the Interface toolbar.

The Deliver page’s Thumbnail timeline matches the Color page

Filtering the Timeline’s contents through this dropdown lets you narrow, in several ways, the span of media you intend to output. As an example, when a timeline has already been rendered but you have made edits since, one of the “Modified Clips” options can be set to surface only the clips altered inside a given timeframe. A second popular choice, “Unrendered Clips,” singles out every clip not yet rendered — useful in workflows where you render only a portion of the Timeline at a time. With the Thumbnail timeline filtered, jobs can be queued solely in Individual Clips mode. Whether Thumbnail filtering is active is indicated by an orange underline beneath the Clips button in the UI toolbar. That orange line below the Clips button signals filtering is on

### The Viewer

As file-based media is rendered, the Viewer presents an exact preview of how the output media will appear under the present settings, while the transport controls drive the playhead across the current Timeline. Clicking the speaker icon toggles audio playback on or off, and right-clicking that same speaker icon and dragging the slider sets the level.

### Deliver page Viewer

During tape output, the Viewer displays the tape signal so you can lay in insert or assembly edit points, and provided device control is on, the transport controls run the tape inside the deck. The Viewer can also be expanded to fill the whole screen via Cinema Viewer mode, reached by choosing Workspace > Viewer Mode > Cinema Viewer (P). That command flips Cinema Viewer mode on and off.

### Skimming in the Viewer

To skim footage within any viewer across the Media, Cut, Edit, Color, and Deliver pages, hold the C key down while dragging the pointer to and fro inside the viewer.

### Disabling Viewer Updates While Rendering

Inside the Render page Viewer option menu, an Updates During Renders submenu gives you the choice to disable, minimize, or enable Viewer updates as a program renders. Cutting Viewer updates to minimal or off speeds up rendering, particularly on less powerful workstations.

### The Render Queue

Every job you have lined up for delivery appears in the Render Queue. A job can carry its own clip range and render settings, letting you output several sections or clips of one timeline, push the same timeline to multiple formats, or handle several timelines. The Render Queue can be set to display only the jobs in the current project, or instead every job queued and stored across all projects held in the open SQL network project library (for the current user) or the local project library (at the disk location presently selected). That proves especially handy when a program has been split into several reels, each reel living as its own project. Toggle it through the “Show All Projects” entry of the Render Queue Option menu. A job sitting in the Render Queue can be edited via its pencil button, routed to remote rendering workstations, or removed. Jobs already rendered may stay in the Render Queue so they can be re-rendered down the road.

### The Render Queue displays all jobs

TIP: Choosing “Show Job Details” from the Render Queue Option menu surfaces the Render Settings for each entry in the Render Queue. It lays out the particulars of every job — its dimensions, frame rate, codec and so on. At a glance, this is a real aid when you are juggling a complex render queue.

### Drag to Reorder Jobs in the Render Queue

Reordering the Render Queue by hand is a matter of dragging a job up or down within the stack. The job numbers hold their numerical sequence, yet the render settings tied to each will swap accordingly.

In the Render Queue, Job 3 (H.264) being dragged ahead of Job 2 (ProRes)
