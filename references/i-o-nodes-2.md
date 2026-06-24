# I O Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Auto: draws on the Timeline color space, or — where Resolve Color Management (RCM) is switched on — whatever color space RCM hands over.
- Space: Space gives you a Color Space drop-down menu to pick a particular setting from, while a “horseshoe” graph paints a visual picture of whichever color space you’ve chosen.

Source Gamma Space Lets you pick a gamma setting for the image data that this MediaIn node puts out. Having set the gamma curve type, you may opt to strip the curve away so as to steer a linear workflow.

- Auto: Draws on the Timeline gamma, or — where Resolve Color Management (RCM) is switched on — whatever gamma RCM hands over.
- Space: Gives you a Gamma Space drop-down menu to pick a particular setting from, while a visual graph paints a picture of whichever gamma setting you’ve chosen.
- Log: Brings up the Log Type drop-down menu, where you pick a particular log encoding profile. A visual graph paints a picture of the log setting you chose off the menu. For finessing the gamma output, further options are offered: Lock RGB, Level, Soft Clip, Film Stock Gamma, Conversion Gamma, plus a Conversion table.
- Remove Curve: From the material, the matching gamma curve gets stripped away — or a log-lin conversion gets run on it — which in effect turns it into a linear output space.
- Pre-Divide/Post-Multiply: When the need arises, lets you turn “straight” Alpha channels into premultiplied Alpha channels.

### Audio Tab

An Audio tab lives in the Inspector for the MediaIn node, where you can opt to solo the clip’s audio or listen to every audio track on the Timeline.

What the Audio tab on the MediaIn node does is let you pick the track to play back, slip the audio timing, and reset the audio cache.

Should the audio drift out of sync while playing back in Fusion, the Sound Offset wheel on the Audio tab lets you slip the audio in subframe frame increments. That slipped audio changes only on the Fusion page. Every other page keeps the original audio placement.

### Audio with Media Pool Clips

By default, audio from a clip pulled in via the Media Pool stays muted. Getting that Media Pool clip’s audio to play takes two steps. To listen to audio from a clip pulled in via the Media Pool, go through the following: 1 Pick the clip in the Node Editor. 2 Within the Inspector, open the Audio tab and pick the clip name off the Audio Track drop-down menu. With more than one MediaIn node in the comp, what plays is the audio most recently picked in the Inspector. The Speaker icon in the toolbar lets you flip among the MediaIn node audio files. 3 Right-click that Speaker icon in the toolbar, then pick the MediaIn for whichever clip you want to listen to.

### Purging the Audio Cache

For quicker performance, the audio and its settings get cached. Change which audio tracks you want playing back in Fusion, or reach for the Sound Offset wheel to slip the audio tracks, and you’ll need to purge the audio cache. Likewise, head back to the Edit, Cut, or Fairlight page and tweak the audio levels, and the audio cache needs purging. To purge the audio cache following any audio playback change:

- Hit the Purge Audio Cache button in the Inspector.

Next time you play the composition back, the audio will be brought up to date.

### MediaOut Node [MO]

### The MediaOut node

NOTE: Only in DaVinci Resolve is the MediaOut node available.

### MediaOut Node Introduction

A MediaOut node has to be part of every composition you build on DaVinci Resolve’s Fusion page. What the MediaOut node does is send the finished output, on DaVinci Resolve’s Edit or Cut page, back to your Timeline. Most of the time it stands in for the Saver node that Fusion Studio uses when exporting clips.

Whatever the Fusion page’s MediaOut node outputs gets carried through by way of the Color page’s source inputs — the one exception being that, if you’ve applied transforms or plugins to that clip on the Edit or Cut page, the handoff running from the Fusion page over to the Color page goes like this:

### Fusion Effects

### Edit Page Plugins

### Color Effects

Where Resolve Color Management or ACES is in play, each MediaOut node turns the output image back into the Timeline color space before the handoff to the Color page.

NOTE: From the Effects Library, extra MediaOut nodes can be dropped into the Node Editor. Those extra MediaOut nodes serve to pass mattes over to the Color page.

### Inputs

The MediaOut node’s lone input is where you wire up the finished composite image you’d like rendered back to the Edit page. Input: That orange input is a required one. Any 2D image you want rendered back to the Edit page is what it accepts.

### Basic Node Setup

A single comp can hold several MediaOut nodes. It’s always the first MediaOut node that renders the image back to the Edit page Timeline. To pass mattes over to the Color page, you can put extra MediaOut nodes to work.

Here the MediaOut1 node renders to the Edit page while MediaOut2 passes mattes over to the Color page

### Inspector

### The MediaOut controls

For viewing on the Fusion page, the MediaOut node offers a range of Color Grade options.

- None: The default view, this one shows nothing but the output of the Fusion composition.
- Color: This one shows the Fusion composition’s output, Color page adjustments included, at timeline resolution.
- Mix: This one shows the Fusion composition’s output together with Cut and Edit page effects plus Color page adjustments, at timeline resolution.

NOTE: These options serve only as previews, putting your current comp in the context of whatever other effects may have been added beyond Fusion. The MediaOut node’s own actual output stays as it was.

### The Color Grade tab set to None

None shows nothing but the output of the Fusion composition. Notice that the display sits at the source media/composition resolution.

### The Color Grade tab set to Color

Color shows the Fusion composition, taking in whatever adjustments got applied on the Color page. Notice that once the MediaOut view is on Color, the display moves to the timeline resolution.

### The Color Grade tab set to Mix

Mix shows the Fusion composition, taking in whatever effects got applied on the Cut or Edit page along with whatever adjustments are on the Color page. Notice that once the MediaOut view is on Mix, the display moves to the timeline resolution.

### Saver Node [SV]

### The Saver node

NOTE: Within DaVinci Resolve, the Saver node serves only to export EXR files.

### Saver Node Introduction

The final composition output coming out of Fusion Studio is what the Saver node stands for. Its job is rendering out movie files or sequential images, though you can drop it into a composition at any point to render out a composition’s intermediate stages. Any number of Saver nodes can live inside one composition, for rendering a comp’s different branches as well as different formats. The Saver node can additionally tack scratch track audio onto your composition, audible during interactive playback.

### Inputs

The lone input on the Saver node is meant for the finished composition you’re after rendering. Image Input: Use that orange input to wire up the resulting image you want rendered.

### Basic Node Setup

You position the Saver node at the composition’s end. Several Savers can sit in one comp to render different formats or to render a composition’s different parts.

A Saver node placed at a node tree’s end so as to render the composition

### Inspector

### Saver File tab

### File Tab

What the Saver File tab does is set where the rendered file lands and what format it takes. Filename The Filename dialog is where you settle on the name and path for the rendered image output. Click the Browse button to bring up a file browser and pick a spot for the output. When you render a sequential image file format, sequence numbering gets tacked onto the filename for you. As an example, enter c\renders\image.exr as the filename and render 30 frames of output, and the files get numbered automatically as image0000.tga, image0001.exr, image0003.exr... and onward. Numbers below 10000 automatically get four-digit padding. By typing the digits straight into the filename you can dictate how many digits the padding uses. For instance, image000000.exr would put 6-digit padding on the numbering; meanwhile image.001.exr gives you 3-digit padding, whereas image1.exr gives none whatsoever. Output Format Picking which image format to save is the job of this menu. Keep in mind that picking a fresh format off this menu won’t change the filename’s extension to match. Edit the filename by hand to line up with that format’s expected extension, so name and image format don’t end up mismatched. Save Frames This control picks between two rendering modes: Full Renders Only or High Quality Interactive.

- Full Renders Only: For most situations this is the usual setting. Images land on disk once a final render kicks off with the Start Render button in the Time Ruler.
- High Quality Interactive: Built for real-time rendering during painting and rotoscoping, this render mode has Fusion write each frame to disk as it’s processed interactively. Put to use properly, the feature can do away with the need for a final render once rotoscoping is done.

NOTE: Paired with a node tree carrying spline-animated parameters, the High Quality Interactive setting can readily breed confusion. Should those splines get altered such that frames already saved interactively change, the frames already on disk won’t re-render on their own. Either walk through each frame once more or run a final render to be sure the result is right Frame Offset With this thumbwheel control you can set an explicit start frame for the number sequence put on the rendered filenames. As an example, set Global Start to 1 and render frames 1-30 so that files normally get numbered 0001-0030. With the Sequence Start Frame set to 100, the rendered output would instead carry numbers from 100-131.

### Saver Export tab

### Export Tab

Process Mode Reach for this menu to pick which Fields Processing mode Fusion uses while saving the images or movie file to disk. Both the default option and the default height come from the Has Fields checkbox control in the Frame Format preferences. The options on offer take in:

- Full frames
- NTSC fields
- PAL/HD fields
- PAL/HD fields (reversed)
- NTSC fields (reversed).

Those two reversed options write fields in the reverse order, so the fields wind up spatially swapped both in time order and in vertical order. Export Mode Use this menu either to render the file out normally or to put a SMPTE standard 3:2 pulldown on the footage, taking the footage from 24 fps up to 30 fps.

Clipping Mode This menu — sometimes thought of as source image clipping — lays out how the image’s edges ought to be handled.

- Frame: By default, the Frame setting clips to whichever parts of the image fall inside its visible dimensions. Any infinite-workspace behavior gets broken. Where the upstream DoD is smaller than the frame, whatever area is left in the frame counts as black/transparent.
- None: No source image clipping at all happens with this setting. So any data ordinarily called for beyond the upstream DoD counts as black/transparent. Mind that this may spawn humongous images able to eat up a considerate amount of disk space. So reach for this option only where it’s truly needed.

To learn more about ROI, DoD, and Infinite Workspace, turn to Chapter 69, "Using Viewers." within the DaVinci Resolve Reference Manual, or to Chapter 7 within the Fusion Reference Manual. Save Alpha to Color Switch this control on and the Alpha channel gets written into the color channels as a grayscale image. Doing so wipes out any color information already there. Color Space Type Setting the output file’s Color Space is what this menu does, so that you could, say, color space convert images from linear to Rec709, and the like, thereby putting out linear EXRs, 709 Quicktimes, and so on from one source. Nothing gets converted within the Comp; only the images written to disk get converted.

- Auto: Carries along whatever metadata might sit in the rendered image.
- Space: Lets the user fix the color space according to the output format.

Curve Type Picking a Gamma curve for the rendered file is the job of this menu. Having set the gamma curve type, you may opt to apply the curve for output.

- Auto: Carries along whatever metadata might sit in the incoming image.
- Space: Lets the user fix the gamma curve according to the chosen file format.
- Log: Brings up the Log/Lin settings, much like the Cineon Log node.

For fuller detail on the Log settings, turn to Chapter 99, “Film Nodes,” within the DaVinci Resolve Reference Manual, or to Chapter 39 within the Fusion Reference Manual. Apply Curve Depending on which Curve Type you chose, or on the Gamma Space turned up in Auto mode, the matching Gamma Curve gets applied, which in effect converts away from a linear working space.

### Audio Tab

NOTE: This tab shows up only in Fusion Studio’s Saver node.

### Saver Audio tab

The audio capability ships in Fusion Studio purely for scratch track use (lining up effects with audio and clip timing). Final renders ought, almost every time, to run without audio. Keep your audio files as small as they can be, since Fusion pulls the whole audio file into memory so it can show the waveform efficiently in the Timeline. Pick a Quicktime file format and the audio track gets folded into the saved image. As things stand, Fusion can play back WAV audio. Source Filename Into the Source Filename field you can type, for whatever audio clip you intend to use, both its file path and its name. You can equally click the Browse button to open a file browser window and track down the audio scratch track. Pick the WAV file you want, then over in the keyframes panel expand the Saver bar to bring up the audio waveform. Drag the pointer across the audio wave within the Timeline layout, and you’ll hear the track. Sound Offset Drag this control either way, left or right, to shift the audio clip’s Timeline position relative to the Node Editor’s other nodes.

### Legal Tab

For producing “broadcast safe” saturation and video range files to output, the Legal tab holds the relevant settings.

### Saver Legal tab

Video Type Reach for this menu to pick which standard gets used for broadcast legal color correction. The choices are NTSC, NHK, or PAL/SECAM. Action Reach for this menu to decide how Fusion handles illegal colors in the image.

- Adjust to Legal: This has the images saved with legal colors suited to the chosen Video Type.
- Indicate as Black: This has the illegal colors shown as black in the views.
- Indicate as White: This has the illegal colors shown as white in the views.
- No Changes: This has the images saved untouched.

Adjust Based On Reach for this menu to decide whether Fusion makes the image legal to 75% or 100% amplitude. Hardly any broadcast markets allow 100% amplitude, so for the most part leave this at 75%. Soft Clip What the Soft Clip control does is pull out-of-range values back into the image. It manages that by easing the conversion curve at its top and bottom, so more values can be represented.

### Format Tab

Information, options, and settings tied to whichever image format is being saved fill the Format tab. The controls for an EXR sequence look nothing like the ones shown when a MOV file is saved.

### Saver Format tab

EXR is displayed above for reference.

Once the Saver node is set to DPX, it pays to grasp why the Bypass Conversion > Data is Linear option exists. When you’re writing log data into a DPX without leaning on the Saver node’s own lin-log conversion (that is, with Bypass Conversion ticked), the Data Is Linear option ought to be off. This signals whether Bypass Conversion got ticked because the data is linear, or because it’s already log. Switch Data Is Linear on and the DPX gets flagged in its header as holding linear data. That in turn means that when the DPX gets loaded back into Fusion, or into other apps that read the header, those apps take the data for linear and skip any log‑lin conversion.

### Common Controls

Settings Tab Because the Settings tab controls are shared between the Loader and Saver nodes alike, you’ll find them described in the “The Common Controls” section at this chapter’s end. Clipping Mode This menu — sometimes thought of as source image clipping — lays out how the image’s edges ought to be handled.

- Frame: By default, the Frame setting clips to whichever parts of the image fall inside its visible dimensions. Any infinite-workspace behavior gets broken. Where the upstream DoD is smaller than the frame, whatever areas are left in the frame count as black/transparent.
- None: No source image clipping at all happens with this setting. So any data ordinarily called for beyond the upstream DoD counts as black/transparent. Mind that this may spawn humongous images which can eat up a considerable amount of disk space. So reach for this option only where it’s truly needed.

To learn more about ROI, DoD, and Infinite Workspace, turn to Chapter 69, "Using Viewers." within the DaVinci Resolve Reference Manual, or to Chapter 7 within the Fusion Reference Manual. Save Alpha to Color Switch this control on and the Alpha channel gets written into the color channels as a grayscale image. Doing so wipes out any color information already there. Color Space Type Setting the output file’s Color Space is what this menu does, so that you could, say, color space convert images from linear to Rec709, and the like, thereby putting out linear EXRs, 709 Quicktimes, and so on from one source. Nothing gets converted within the Comp; only the images written to disk get converted.

- Auto: Carries along whatever metadata might sit in the rendered image.
- Space: Lets the user fix the color space according to the output format.

Curve Type Picking a Gamma curve for the rendered file is the job of this menu. Having set the gamma curve type, you may opt to apply the curve for output.

- Auto: Carries along whatever metadata might sit in the incoming image.
- Space: Lets the user fix the gamma curve according to the chosen file format.
- Log: Brings up the Log/Lin settings, much like the Cineon Log node.

For fuller detail on the Log settings, turn to Chapter 99, “Film Nodes,” within the DaVinci Resolve Reference Manual, or to Chapter 39 within the Fusion Reference Manual. Apply Curve Depending on which Curve Type you chose, or on the Gamma Space turned up in Auto mode, the matching Gamma Curve gets applied, which in effect converts away from a linear working space.

### The Common Controls

Across the Inspector, I/O nodes have a number of identical controls in common. The controls shared among I/O nodes are what this section lays out.

### Inspector

### Common Saver settings inspector

### Settings Tab

You’ll find the Inspector’s Settings tab on the Loader, Saver, MediaIn, and MediaOut nodes. Its controls stay consistent and behave the same on each tool, though a handful of parameters live on only certain nodes — they’re still covered here. Blend What the Blend control does is mix the tool’s original image input together with whatever modified output image the tool finally produces. Set the blend value to 0.0 and the outgoing image matches the incoming one exactly. Ordinarily this has the tool bypass processing altogether, copying the input straight across to the output. Process When Blend Is 0.0 The tool runs even where the input value is zero. That can come in handy if this node’s processing is scripted to set off another task while the node’s value sits at 0.0. Red/Green/Blue/Alpha Channel Selector These four buttons serve to confine the tool’s effect to certain color channels. The filter usually goes on once the tool has finished processing. As an example, deselect the red button on a Blur tool and the blur first goes onto the image, after which the red channel from the original input gets copied back over the result’s red channel. There are a few exceptions — tools where deselecting these channels has the tool skip processing that channel outright. Tools that behave this way generally carry a matching set of RGBA buttons on their Controls tab. In that case, the buttons on the Settings and the Controls tabs are one and the same. Apply Mask Inverted Switch the Apply Mask Inverted option on and the tool’s entire mask channel gets inverted. That mask channel is the combined product of every mask connected to or generated within a node. Multiply by Mask Pick this option and the masked image’s RGB values get multiplied by the mask channel’s values. As a result, every pixel of the image left out of the mask (that is, set to 0) turns black/transparent. Use Object/Use Material (Checkboxes) Certain 3D applications are able to render into file formats that carry extra channels. The EXR file format notably supports Object and Material ID channels, usable as a mask for the effect. Whether those channels get used, when present, is what these checkboxes decide. Which particular Material ID or Object ID is affected gets picked with the next set of controls. Correct Edges This checkbox turns up only once the Use Object or Use Material checkboxes are on. It flips the method used to handle overlapping edges of objects within a multi-object image. With it on, the Coverage and Background Color channels serve to separate and sharpen the effect around the object’s edge. Leave this option off (or have no Coverage or Background Color channels available) and aliasing may show up on the mask’s edge. For more on Coverage and Background Color channels, turn to Chapter 78, "Understanding Image Channels," within the DaVinci Resolve Reference Manual, or to Chapter 18 within the Fusion Reference Manual.

Object ID/Material ID (Sliders) Reach for these sliders to pick which ID builds a mask out of an image’s object or material channels. Put the Sample button to use just as you would the Color Picker: to grab IDs off the image shown in the view. That image or sequence has to have been rendered from a 3D software package with those channels folded in. Hide Incoming Connections Switch this checkbox on to tuck away connection lines coming from incoming nodes, which makes a node tree look tidier and read more easily. With it on, the Inspector shows an empty field for each input on a node. Drag a connected node out of the node tree into the field and that incoming connection line hides, so long as the node stays unselected in the node tree. Select the node in the node tree and the line comes back. Comments Adding notes to a tool is what the Comments field is for. Click in the empty field and type your text. Add a note to a tool and a small red square turns up in the node’s lower-left corner when the full tile is shown, or a small text bubble icon turns up on the right when nodes are collapsed. To read the note in the Node Editor, rest the mouse pointer over the node to bring up the tooltip. Scripts From the Settings tab, every tool in Fusion offers three Scripting fields. Each holds edit boxes for adding scripts that run as the tool renders. For fuller detail on scripting nodes, please refer to the Fusion scripting documentation.
