# Copying And Importing Grades Using Colortrace

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Copying and Importing Grades Using ColorTrace

ColorTrace ranks among DaVinci Resolve's standout features: it lets you shift grades fast and painlessly off the clips of one timeline onto the clips inside another, keyed to each clip's source timecode (or to clip names while you're in Automatic mode). ColorTrace can even carry grades across timelines that share one project, and it can ColorTrace a single stereo timeline onto another.

### Copying Grades Using ColorTrace

Whichever version of a clip's grade got applied in the Source timeline you copy from — local or remote — is what ColorTrace brings across, decided by which grades each clip in that Source timeline is set to draw on. On top of that, ColorTrace carries Group Pre-Clip and Group Post-Clip grades along with Fusion compositions. Thanks to these gains, the tool is a thoroughly dependable way to move grades from one timeline onto another across all sorts of scenarios. To use ColorTrace: 1 Open the Media page and pick, out of the Media Pool, the Timeline you intend to run ColorTrace against, then open it and head to Timelines > ColorTrace > ColorTrace From Timeline.

### Choosing ColorTrace for a selected Timeline

Up comes the ColorTrace Setup window, laying out every project library, user, project, and timeline in one nested list. 2 Through the Project List browser, pick the exact Timeline whose grades you want to copy. To get at it, you'll have to click the disclosure triangle beside the project library, user name, and project that holds that Timeline.

ColorTrace project and Timeline selection window

3 (Optional) When you run ColorTrace on a project loaded with VFX clips, in a workflow where each of those VFX clips carries a distinct reel name marking it, you can type those names — with asterisks (_) serving as wildcards standing in for the parts of each reel name that may shift — into the “Effects Shot Definitions” field. Doing so quickens automatic ColorTrace runs, letting DaVinci Resolve lean on fuzzy string matching once a clip's reel number flags it as a VFX shot, so the strongest match surfaces at the top of the list. You're free to enter several VFX reel names with wildcards, one to a line, for string matching all at once. Whatever reel name text fits your workflow will do; a few sample VFX reel names look like this: **COMP** VFX_ EFFECTS\* 4 Click Continue. The ColorTrace window opens carrying two tabs that set how you work. 5 Pick your working mode by clicking either the Automatic or Manual tab:

- Under Automatic mode, ColorTrace hunts on its own for clips that line up between the chosen Timeline and the current Timeline. Every clip gets color coded by the correspondence it lands.
- Under Manual mode, you handle the grade copying yourself, by way of the Copy and Paste procedures, or by dragging and dropping with your mouse.

There's a lot to the ColorTrace window; how each mode runs gets its own treatment in the sections below. 6 Once you're done with ColorTrace, click Close.

### Using ColorTrace in Automatic Mode

Under Automatic mode, ColorTrace works out on its own the links between the clips in the chosen Timeline you're pulling grades from (the Source timeline) and those in the current Timeline you're pushing grades to (the Target timeline).

### Selecting the Automatic or Manual ColorTrace

A colored outline rings each clip in the Target Timeline Thumbnail timeline, signaling its status. Red: Nothing matched whatsoever. Usually the case for clips in the current Timeline that went unused in the Timeline you're ColorTrace matching against. Blue: Owing to timecode and reel names that overlap, several links turned up (much like a reel conflict), and you have to point out the right one per clip. This crops up often with VFX and motion graphics clips you brought in with timecode beginning at 00:00:00:00. Green: Something matched.

ColorTrace Thumbnail outlines indicate matching, overlapping, and non matching clips. Under Automatic mode, the link between every clip in the Source timeline and each one in the Target timeline ought to form by itself. That said, timecode and reel names that overlap can throw it off. The remaining controls in the ColorTrace window are there to help you tackle the handful of clips that won't match on their own, or that matched wrongly. Those controls are:

### The ColorTrace window shown in Automatic mode

Matching Source Clips list: Presents a scrollable set of thumbnails that may line up with the clip you've chosen in the Target timeline. Target Timeline: Presents each clip in the Timeline you're pushing grades to, color coded by how strong a match it is. Clip Info pane: Lays out two columns of properties covering the source clip alongside the target clips you picked. Among those properties, for each clip, are its reel, source timecode, record timecode, clip name, project names, plus timeline names — all laid out for easy side-by-side checking. Attributes and options checkboxes: A row of checkboxes lets you spell out which clip attributes ride along in the ColorTrace operation.

- Color: Enables the copying of grades.
- Preserve Num Nodes: As grades copy across, this keeps the leading X nodes belonging to the target clip's

grades safe from being clobbered by the leading X nodes of the source clip's grades.

- Input Sizing: Enables the copying of Input Sizing attributes.
- Convergence: Enables the copying of Convergence for Stereo 3D projects.
- Floating Windows: Enables the copying of Floating Windows for Stereo 3D projects.
- Auto Align: Switches on carrying the Auto Align settings across, for Stereo 3D projects.
- All Versions: Brings every version across from source to target, not solely the current one,

for the clips. The version currently chosen on each source clip always copies across correctly.

- Version Camera Raw Settings: Switches on copying of versioned Raw settings, in place of merely

the present Raw setting.

- Track Marks: Enables the copying of keyframes.
- Flags and Markers: Enables copying of all flags and markers.
- Hide Matching Clips: Tucks away every clip that matched cleanly, leaving on view only the clips with multiple matches or none. That lets you zero in on the troublesome subset inside a potentially lengthy timeline.
- Ignore Reel Names: Should you suspect the reel names are wrong, switching this checkbox on disregards them, lining up all source and target clips by timecode by itself.

Copy Grades: Carries the matched source grades onto each green and purple target clip. Copy Grades & Exit: After you've made all the grade matches you can, click this button to carry the matched source grades onto each green and purple target clip and shut the ColorTrace window. Here's the way to wield these controls to work out which source clips feed each blue and red target clip in the Target timeline. To hand-pick the source grades that should land on particular target clips: 1 Click any blue clip thumbnail over in the Target timeline.

Surfacing several candidate links over within the Matching Source Clips Timeline Up turns a batch of clips sharing overlapping timecode and reel names. Should you wish to set the reel names aside because you suspect they're wrong, switch on the Ignore Reel Names checkbox. 2 If holding the Source and Target thumbnails side by side doesn't settle the choice, then click any clip in the Matching Source Clips timeline to bring up its metadata for comparison across the source/target columns underneath.

Source and Target clip metadata for comparison

3 With a clip link settled on, double-click the Matching Source Clip thumbnail you mean to copy from. When no clip in the Matching Source Clip pane fits well, double-click the “Set As New Shot” box. Both the Source and Target thumbnails go purple, marking the link you've forged.

The matching Source and Target clips now both marked with purple outline Keep working through every thumbnail bearing Blue and Red Xs until you've turned up matches for as many clips in the Timeline as can be done. 4 Once finished, click Copy Grades & Exit.

### Using ColorTrace in Manual Mode

Manual mode shines whenever you need to carry grades between programs whose clips share no timecode or reel name link at all. The Manual ColorTrace interface is built to walk you across two separate timelines, either one clip at a time or in matched batches of clips, carrying grades off the Source timeline onto the Target timeline. Say you're trying to bring grades over from a timeline conformed out of individual media files onto a second timeline conformed from a single flattened master media file — the ColorTrace Manual mode gets that done. Two banks of controls make up the manual interface, one tied to the Source timeline (its label reads “Timeline to copy from”) and one to the Target timeline (its label reads “Timeline to paste to”). Broadly, you step through both timelines a single clip at a time, or in matched batches, ferrying grades off the “Copy from” timeline onto the “Paste to” timeline.

### ColorTrace Manual window

Manual mode has the following controls:

- Source timeline: Presents every clip in the Source timeline you chose — the clips you're pulling grades from. Click a single clip thumbnail to select it, or click one thumbnail and then Shift-click another to grab an unbroken range of clips. A noncontiguous range of clips can't be selected.
- Copy Range controls: A pair of fields shows the range of clips in the present selection you'll be copying from, named by their numeric place in the Source timeline. You can reset the range by the numbers, either keying fresh values into the fields or nudging the value by one with the up/down arrow buttons. The First button automatically folds in every clip from the Timeline's first one into the present selection. The Last button automatically folds in every clip out to the Timeline's last one into the present selection.
- Target timeline: Presents every clip in the Target timeline you chose — the clips you're pushing grades to. Selecting clips here behaves exactly as it does on the Source timeline.
- Paste Range controls: A pair of fields shows the range of clips in the present selection you'll be pasting to, named by their numeric place in the Source timeline. Every control behaves exactly like the Copy Range controls.
- Attributes and options checkboxes: Clear the checkboxes of any clip characteristics you'd rather leave out of the ColorTrace operation. A fuller rundown of these options sits in the section covering the Automatic ColorTrace mode.
- Paste button: After you've chosen one or more source clips plus a matching count of target clips, clicking Paste carries over the grades, PTZR settings, and marks (subject to the matching checkboxes).
- Undo Last: Lets you undo the most recent paste action.
- Undo All: Lets you undo all paste actions in Manual mode.
- Done: Finishes the operation and closes the ColorTrace window.

Whenever you're cherry-picking lone grades off one timeline to drop onto shots elsewhere, the copying can go one grade at a stretch. To move a single source grade onto a single target clip:

- Pick a thumbnail up in the Source timeline (the top one) as your source, next pick a thumbnail down in the Target timeline (the bottom one), then hit Paste.

You can equally carry the grades of whole scenes' worth of clips from one timeline onto another in one move. As an example, when you're bringing grades over from an originally graded timeline onto a re-edited cut of that same program, you can carry every grade off a 10-clip scene in the Source timeline onto those same 10 clips in the Target timeline that have been shoved later in the Timeline.

To move a batch of source grades onto a batch of target clips: 1 Settle on an unbroken run of source clips through one of these routes:

- Select the range's first clip, after which you Shift-click the range's last clip.
- Type the clip number of that first clip into the left “Copy Range” field, then type the clip

number of the last one into the field on the right.

- Select a clip, then hit First so every clip from there back to the Timeline's first one comes in.
- Select a clip, then hit Last so every clip from there out to the Timeline's last one comes in. 2 Settle on an unbroken run of Target clips following the identical steps from before, except this time on the “Paste Range” controls.

IMPORTANT: The Paste button only switches on once your tally of target clips equals the tally of source clips you picked.

Group copy and paste of grades 3 With your selections made, click Paste. The grade settings off the source clips land on the destination clips in order. Put differently, if you copy from clips 5 through 9 onto clips 11 through 15, then grade 5 lands on shot 11, grade 6 lands on shot 12, grade 7 lands on shot 13, and so forth.

### Importing CDL Data Using ColorTrace

By way of the ColorTrace CDL command you can pull ASC CDL file formats out of other applications and into DaVinci Resolve. DaVinci Resolve is likewise able to read DRX filenames out of CDL files, which lets a CDL load exported DaVinci Resolve grades. Three file formats are supported: CMX EDL: An EDL whose comments point at CCC/CDL XML files, or even Slope, Offset, and Power (SOP) data tucked inside the comment area. CCC and CDL XML: A file format holding assorted color correction looks, plus references too.

Pulling CDL data into DaVinci Resolve goes like this: 1 Where what you're bringing in is CCC/CDL XML correction looks:

- Open the Gallery page, right-click somewhere inside the Stills tab, and pick Import off the contextual menu.
- Once the Import Stills dialog shows up, open the CDL/CCC files. As they finish coming into the Gallery, an ASC logo turns up next to them.

2 Open the Edit page and pick, in the Timeline list, the Timeline you mean to run ColorTrace against. 3 Right-click somewhere inside the Timeline, and pick ColorTrace from CDL. 4 Pick an EDL through the Select EDL dialog, and click Open. 5 Pick its matching CDL and CCC files through the Select CDL Files dialog. Where no CDL or CCC files exist (which holds when there are inline SOP comments inside the EDL), you ought to click Cancel. 6 Through the ColorTrace With CDL window, carry the source grades off the CMX EDL/CCC & CDL XML files onto the Target timeline. From here on, the ColorTrace window behaves exactly as laid out earlier.

As a formatting guide, below are a few sample CMX, CCC, and CDL files.

### Example CMX EDL File

TITLE: Final EDL FCM: NON-DROP FRAME 010 001 V C 01:19:28:16 01:19:28:16 01:00:41:18 01:00:42:18 *ASC_CC_XML test_cc.102 011 001 V C 00:00:00:00 01:19:28:16 01:00:42:18 01:00:43:18 *ASC_SOP (0.9 1.2 0.5)(0.4 -0.5 0.6) (1.0 0.8 1.5) Example CCC File <ColorCorrectionCollection xmlns:”urn:ASC:CDL:v0.5” > <InputDescription> test corrections for ref_input_image.1920 </InputDescription> <ViewingDescription> for mathematical analysis only </ViewingDescription> <ColorCorrection id=”test_cc.100”> <SOPNode> <Description> for ref_output_image.0100 </Description> <Slope> 1.0 1.0 1.0 </Slope> <Offset> 0.0 0.0 0.0 </Offset> <Power> 1.0 1.0 1.0 </Power> </SOPNode> </ColorCorrection> <ColorCorrection id=”test_cc.101”> <SOPNode> <Description> for ref_output_image.0101 </Description> <Slope> 1.0 1.5 0.6 </Slope> <Offset> 0.0 -0.1 0.01 </Offset> <Power> 1.0 1.5 0.5 </Power> </SOPNode> </ColorCorrection> </ColorCorrectionCollection>

Example CDL File <ColorDecisionList xmlns=<94>urn:ASC:CDL:v0.5<94> > <InputDescription> GeneralProducts M1 std thru GP M1 LUT4 </ InputDescription> <ViewingDescription> GP P1, DCI P3, Pathe color emul </ ViewingDescription> <ColorDecision> <MediaRef ref=<94>/some/Project/frame%250900-0954%5B.dpx<94>/> <ColorCorrection id=”cc03340”> <SOPNode> <Description>change +1 red, contrast boost</Description> <Slope>1.2 1.3 1.4</Slope> <Offset>0.3 0.0 0.0</Offset> <Power>1.0 1.0 1.0</Power> </SOPNode> </ColorCorrection> </ColorDecision> </ColorDecisionList>

### Using CDL Adjustments

After you've imported a CDL (Color Decision List), the CDL adjustment for each clip becomes reachable through a contextual menu command in the Thumbnail timeline of the Color page.

### Calculating CDL Functions

To convert the SOP values into a primary correction, DaVinci Resolve runs the following math: Output = (Input \* Slope + Offset)Power Output stands for the finished grade. Input is each pixel's value within each color channel (on a 0–1 scale). Slope rests at a detent of 1 while Offset rests at a detent of 0 and Power again at a detent of 1.
