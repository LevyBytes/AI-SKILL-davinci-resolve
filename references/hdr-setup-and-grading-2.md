# Hdr Setup And Grading (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

With HDMI Tunneling you can watch Dolby Vision content on a consumer display in real time. Because every display type and brand brings its own processing quirks, HDMI tunneling is meant less for reference grading and more as a way to gauge, for QC purposes, roughly what home viewers will end up seeing. You can run HDMI tunneling inside DaVinci Resolve through the more affordable Blackmagic DeckLink cards rather than Dolby’s purpose-built eCMU hardware. As things stand, the DeckLink 8K Pro G2 is the single DeckLink card that handles tunneling of this kind. Here is the setup for Dolby Vision HDMI Tunneling inside DaVinci Resolve: 1 Under Preferences > System > Video and Audio I/O, confirm that the Capture Device and Monitor Device are both pointed at the DeckLink 8K Pro. 2 Within Project Settings > Master Settings > Video Monitoring, set up these parameters: Use 4:4:4 SDI: tick its box. Video bit depth: set it to 12 bit. Enable HDR metadata: tick its box as well.

The Project settings under Video Monitoring used to switch on Dolby Vision HDMI tunneling 3 Within Project Settings > Color Management > Dolby Vision, set up these parameters: Enable Dolby Vision: tick its box. Enable Dolby Vision HDMI tunneling: tick its box too. Enable L5 metadata on HDMI: likewise tick its box.

HDR Setup and Grading — within Setup and Workflows, under HDR Viewers

The Project settings under Dolby Vision used to switch HDMI tunneling on 4 On the Color page, inside the Dolby Vision palette, verify that Enable Tone Mapping Preview is turned off (its box left unchecked). Leave that box checked and HDMI tunneling will fail to operate.

Turn off the Enable Tone Mapping Preview box within the Color page’s Dolby Vision palette For further detail on Dolby Vision HDMI tunneling, head to Dolby’s website: https://professionalsupport.dolby.com/s/article/HDMI-Tunneling?language=en_US

### External Content Mapping Unit (eCMU) for Dolby Vision

For studios tackling heavier HDR mastering, DaVinci Resolve accommodates a Dolby External Content Mapping Unit (eCMU), which drives an HDR display alongside an SDR display so you can trim side by side at high resolutions in hardware. On top of that, the eCMU can show Dolby Vision live on a consumer display through HDMI tunneling, giving you a direct look at what home viewers will get.

### Auto Analysis is Available to All Studio Users

Whether or not they hold a license, Resolve Studio users can have the image analyzed automatically and Dolby Vision analysis metadata produced. That metadata serves both to deliver Dolby Vision content and to render the other HDR and SDR deliverables out of the HDR grade you built. As a result, any DaVinci Resolve Studio user is able to turn out Dolby Vision deliverables carrying Level 1 metadata. Trimming that analysis metadata by hand, though, calls for a license from Dolby.

HDR Setup and Grading — within Setup and Workflows, under HDR Viewers

Every Resolve Studio user can reach the commands that drive Dolby Vision auto-analysis; they sit both under the Color > Dolby Vision™ submenu and inside the Dolby Vision palette, and the list runs:

- Analyze All Shots: Runs analysis on every Timeline clip on its own and saves each result separately.
- Analyze Selected Shot(s): Confines the analysis to whichever shots are selected on the Timeline.
- Analyze Selected And Blend: Treats several selected shots as though they formed one continuous sequence. Each clip then receives the identical analysis result. Handy for cutting down time when the clips you analyze share the same content.
- Analyze Current Frame: A quick approach for clips where one frame stands in for the whole shot.

After a clip is analyzed, the Min, Max, and Average fields fill in on their own with the produced L1 data; you cannot edit those fields.

### The metadata fields for each clip

On top of that, an analyzed clip displays an HDR badge in the Thumbnail timeline, which helps you track at a glance which clips are done and which still await analysis.

### Analyzed clips have HDR badges to identify them

### Licensing DaVinci Resolve to Expose Dolby Vision Trim Controls

Surfacing the DaVinci Resolve Studio Dolby Vision controls that allow manual trims atop the automatic analysis every DaVinci Resolve Studio copy performs starts with emailing dolbyvisionmastering@dolby.com for details on securing a license. After Dolby hands you a license file, bring it in via File > Dolby Vision > Load License; once it installs cleanly the Dolby Vision controls become available on the Color page. You ought to receive a display configuration file as well, loadable through the File > Dolby Vision > Load Configuration command, which fills the Dolby Vision drop-down menus with the freshest options.

HDR Setup and Grading — within Setup and Workflows, under HDR Viewers

### Dolby Vision® Trim Controls in DaVinci Resolve

With a clip analyzed, you can go ahead and trim the outcome. The current Dolby Vision palette puts forward four groups of controls. First come the main controls:

- Target Display Output: This drop-down names what Dolby calls the Target Display, the one used to show the tone mapped image. Through the menu you pick particular display characteristics so you can preview how the trimmed image will read on assorted displays with differing gamuts and peak luminance ceilings. Clicking the small chain icon just left of the options links the Target Display Output and Trim Controls For fields together. Doing so makes the Trim Controls For field track whatever value you assigned in the Target Display Output, keeping your trim controls correct for the display in question.
- Trim Controls for: The particular Target Display you are trimming for right now. Its default state (100-nit, BT.709, BT.1886, Full) lets you watch an SDR rendition of the HDR image, revealing how the trim metadata tone maps it on televisions that are not HDR.
- Analyze controls: The commands behind Dolby Vision auto-analysis appear here as buttons that do exactly what their like-named entries in the Color > Dolby Vision submenu do. Note that the bulk of trim controls stay greyed out until an analysis has run, which is a required first step.

All: Runs analysis on every clip in the present Timeline and keeps each result separate. Selected: Restricts analysis to the shots picked on the Timeline. Blend: Handles several selected shots as though they were one unbroken sequence. Every clip ends up with the same analysis result. Reach for the blend option when two clips meet at a through edit that splits frames which are otherwise continuous. Blend is likewise the usual pick for a scene of clips shot at the same place and time, so that ordinary lighting shifts do not introduce unwanted differences between the analyses of clips meant to already match each other. Blend additionally trims time when the clips you analyze hold identical content. Frame: Comes in handy when a portion of a clip carries an extreme color or brightness atypical of the rest, throwing off the analysis and yielding a poor result. Parking the playhead on a frame that fairly represents the clip’s intended look and selecting the Frame option grounds the analysis in that frame alone. It is also a quick way to analyze clips where one frame stands in for the whole shot.

- Enable Tone Mapping Preview: Surfaces the target display output in the Color page Viewer and on the video output, letting you judge how the tone mapped version reads on your HDR display. The control switches off once you turn on “Use dual-outputs on SDI,” a toggle living in the Project Settings’ Master Settings, because the second SDI output then shows the target display output for you.
- Mid Tone Offset (CM v4.0 only): Use this control to line up overall exposure between the tone mapped SDR signal and the HDR master. The offset lands on the L1 Mid values, so you can nudge the mid tones while leaving blacks and highlights alone. It can shift the overall L1 analysis to best protect the artistic intent. Because the setting is shared across every trim pass at every nit level, if you ran two passes — say one at 100 nits and one at 1000 nits — changing it always moves both passes together. Whatever you do to this control gets logged into each clip’s L3 metadata.

Second come the Min, Mid, and Max metadata fields, filled in from the current clip’s analyzed values. Although you cannot edit these fields, analysis metadata may be copied and pasted between clips. The figures stand for the L1 analysis and feed the calculation of how the HDR image gets trimmed to fit the video standard the Target Display calls for. Third are the Primary Trims, editable only after an analysis has run and only when you hold a Dolby license. Exactly which controls appear comes down to the Dolby Vision version you chose in the Color Management panel of the Project Settings.

HDR Setup and Grading — within Setup and Workflows, under HDR Viewers

### Dolby Vision CM v2.9 Controls

Choose Dolby Vision 2.9 from the Project Settings’ Color Management panel and you switch on the 2.9 build of Dolby’s content mapping algorithm, which brings up the original Dolby Vision trim controls. Relying on these is no longer advised, given that you can analyze and trim with Dolby Vision 4.0 yet still export converted 2.9 metadata for legacy workflows.

- Lift/Gamma/Gain: These behave much like the Y-only Lift, Gamma, and Gain master wheels in the Color Wheels palette, giving you a way to trim the image’s overall contrast levels. According to the Dolby Best Practices Guide, you should cap positive Lift at 0.025 and lean chiefly on Gamma and Gain when the image needs brightening.
- Saturation Gain: Trims the saturation of a scene’s most heavily saturated regions. Areas with weaker saturation feel less of the change.
- Chroma Weight: Deepens the saturated portions of the image to keep color richness in spots that smaller gamuts clip because they lack the headroom for saturation up in the highlights.
- Tone Detail: Helps you hold onto contrast detail in the highlights that could otherwise disappear as highlights are mapped into lower dynamic ranges, generally from clipping. Raising Tone Detail Weight keeps more highlight detail intact. In use, it can sharpen highlight detail.

### Dolby Vision CM v4.0 Controls

Choose Dolby Vision 4.0 from the Project Settings’ Color Management panel and you switch on the 4.0 build of Dolby’s content mapping algorithm, which brings up the controls below.

- Lift/Gamma/Gain: These act much the same as the Y-only Lift, Gamma, and Gain master wheels found in the Color Wheels palette, letting you trim the picture’s overall contrast levels. Per the Dolby Best Practices Guide, hold positive Lift to a ceiling of 0.025 and rely mostly on Gamma and Gain whenever the image has to be lightened.
- Saturation Gain: Trims saturation across the most strongly saturated areas of a scene. Values with lower saturation are touched less.
- Chroma Weight: Darkens the saturated regions of the picture to retain color vividness where smaller gamuts clip the image for want of saturation headroom in the highlights.
- Tone Detail: Preserves highlight contrast detail that might otherwise vanish as the highlights drop into lower dynamic ranges, typically through clipping. Pushing Tone Detail Weight up retains a greater share of highlight detail. Applied, it can lend highlight detail extra sharpness.
- Mid Contrast Bias: Shapes picture contrast in the band surrounding the computed average picture level. It lets you raise or lower contrast within the image’s midtones.
- Highlight Clipping: Cuts detail and alters the roll-off of the picture’s brighter region by clipping highlights to the degree needed. Handy when the tone mapped image surfaces unwanted detail.

HDR Setup and Grading — within Setup and Workflows, under HDR Viewers

The Primary Trims controls sitting in the Dolby Vision palette light up only after you have authorized your system with a special license that Dolby supplies. A fourth control group lives in a second palette mode, the Secondary Trims. They too become editable only once an analysis has been run and only when you hold a Dolby license.

- Secondary Saturations: A bank of slider-based vector-style controls (akin to the Hue vs. Sat curve) lets you tune the Saturation of Red, Yellow, Green, Cyan, Blue, and Magenta so you can selectively refine the outcome.
- Secondary Hues: A further bank of slider-based vector-style controls (akin to the Hue vs. Hue≈controls) lets you tune the Hue of Red, Yellow, Green, Cyan, Blue, and Magenta as you fine tune the outcome.

The Secondary Trims controls, viewed on a licensed Dolby Vision system Taken together, all this trimming metadata gives the colorist a way to steer how the iCMU or eCMU converts the image from the Mastering Display named in the Project Settings to the Target Display named in the Dolby Vision palette. The metadata travels across the whole ecosystem so your artistic intent holds up over a range of platforms and displays.

HDR Setup and Grading — within Setup and Workflows, under HDR Viewers

### Previewing and Trimming At Different Levels

On top of that, you can call on the iCMU or eCMU to preview 100 nit, 600 nit, 1000 nit, and 2000 nit renditions of your program under various gamuts, should you wish to observe how the master scales across those pairings of peak luminance level and standard. Naturally this means your DaVinci Resolve workstation or eCMU has to be hooked up to a display that can be driven to those peak luminance output levels. While far from common practice, you can also set the “Trim Controls For” drop-down menu to assorted mixes of peak luminance, gamut, and color temperature so as to visually trim your program’s grades at as many as four separate peak luminance levels, the 100 nit, 600 nit, 1000 nit, and 2000 nit reference points among them. Picking an entry from the “Trim Controls For” drop-down menu readies you to tweak trim metadata for that entry. Swapping among entries in the “Trim Controls For” drop-down menu then lets you tailor a program’s look to the peak luminance and color volume behavior of many different televisions with far finer control. Should you go to the extra trouble of running a full trim pass of your program across multiple nit levels (via the Dolby Vision controls), the Level 2 or Level 8 metadata each pass produces keeps the artistic intent as faithful as possible across a broad span of displays, striving to give the viewer the truest possible take on the director’s intent wherever it turns up. As an example, were a program graded against a 4000 nit display together with one 100 nit BT.709 trim pass, a Dolby Vision-compatible television peaking at 750 nit would lean on the 100 nit trim pass metadata to work out the best way to “split the difference” and output the signal correctly. By contrast, if the colorist ran three trim passes — the first at 100 nits, the second at 600 nits, and a third at 1000 nits — then a 750 nit-capable Dolby Vision television could draw on the 600 and 1000 nit trim metadata to put out more accurately scaled color volume and HDR-strength highlights that, relative to the colorist’s tweaks, make fuller use of that set’s 750 nit output.

### Managing Dolby Vision™ Metadata

While you work through analyzing and trimming the HDR grades shown on your Master Display so they read right on your Target Display, there will be moments when copying and pasting metadata from one clip to the next proves handy. Analysis Metadata can be copied and pasted on its own, apart from Trim Metadata and Mid Tone Offset, and when you trim across several passes you may either copy and paste metadata for all Target Displays, or — if you only mean to overwrite a single pass — copy and paste metadata for just the current Target Display. Here are the ways to move Dolby Vision Metadata between clips by copy and paste. For Analysis Metadata, do this: Pick the clip to copy from, choose Copy Analysis Metadata in the Dolby Vision palette option menu, then pick the clip to paste onto and choose Paste Analysis Metadata from that same Dolby Vision palette option menu. To handle Trim Metadata across all Target Displays, take any one of these routes:

- Pick the clip to copy from, choose Edit > Dolby Vision > Copy Trim Metadata, then pick the clip to paste onto and choose Edit > Dolby Vision > Paste Trim Metadata.
- Pick the clip to copy from, choose Copy Trim Metadata in the Dolby Vision palette option menu, then pick the clip to paste onto and choose Paste Trim Metadata from that same menu.
- Pick the clip to paste onto, then hold the Option-Shift keys down and middle-click the clip you intend to copy from.

HDR Setup and Grading — within Setup and Workflows, under HDR Viewers

- For Trim Metadata limited to the current Target Display, take any one of these routes: Pick the clip to copy from, choose Copy Trim Metadata in the Dolby Vision palette option menu, then pick the clip to paste onto and choose Paste Trim Metadata to Current from that same menu.

Pick the clip to paste onto, then hold the Option key down and middle-click whichever clip you want to copy from.

- To copy and paste Mid Tone Offset: Pick the clip to copy from, choose Copy Mid Tone Offset in the Dolby Vision palette option menu, then pick the clip to paste onto and choose Paste Mid Tone Offset from that same menu.

### Setting Up Resolve Color Management for Grading HDR

With the hardware in place, configuring Resolve itself to put out HDR for Dolby Vision mastering goes smoothly through Resolve Color Management (RCM). The steps stay largely identical regardless of the HDR mastering technology in play; only certain Output Color Space settings change. 1 In the Color Management panel of the Project Settings, set Color Science to DaVinci YRGB Color Managed. 2 Next, open the Color Management panel and point the Output Color Space drop-down at the ST.2084 setting matching the peak luminance, in nits, of your grading display. For instance, grading on a Sony BVM X300 calls for ST.2084 1000 nit, whereas grading on a Flanders Scientific XM310K calls for ST.2084 3000 nit, so that each display’s full capability is tapped. Keep in mind that whatever HDR setting you select enforces a hard clip at that setting’s top nit value. The point is to keep you from inadvertently overdriving HDR displays where doing so carries negative consequences (this limitation does not apply to every HDR display).

- ST.2084 300 nit
- ST.2084 500 nit
- ST.2084 800 nit
- ST.2084 1000 nit
- ST.2084 2000 nit
- ST.2084 3000 nit
- ST.2084 4000 nit

That setting governs nothing more than the output EOTF (think of it as a kind of gamma transform, to borrow the wording DaVinci Resolve’s UI has employed thus far). 3 After that, pick a Timeline Color Space entry that lines up with the gamut you intend to grade in and send to output. As an illustration, if your plan is to treat the Timeline as a log-encoded signal during grading and “normalize” it yourself, ARRI Log C or Cineon Film Log are the picks (this approach comes strongly advised for top results). Should you instead prefer to save effort by letting DaVinci Resolve normalize the Timeline to P3-D65 and grade like that, you can select that option too. As for setting the output gamut, the principle is this: with “Use Separate Color Space and Gamma” switched off, the Timeline Color Space setting establishes your output gamut. Switch “Use Separate Color Space and Gamma” on and you are free to name any gamut you like in the left Output Color Space drop-down menu while picking the EOTF over in the right dropdown menu (just as step 2 spelled out).

HDR Setup and Grading — within Setup and Workflows, under HDR Viewers

4 Note that, when output correctly, HDR ST.2084 signals take on a very “log-like” appearance so that a wide dynamic range can be squeezed into the bandwidth of an ordinary video signal. The job of “normalizing” this log-encoded picture into its proper look falls to the HDR display itself. Because of that, what shows in your Color page Viewer will look flat and log-like even while the same picture on your HDR reference display reads vivid and correct. When you are on a run-of-the-mill SDR computer display and want the Color Page Viewer image to look “normalized” at the cost of clipping the HDR highlights (only in the Viewer, never in the grade), the 3D Color Viewer Lookup Table setting — found under the Project Settings’ Color Management panel — lets you assign the right ST.2084 setting whose peak nit level matches the HDR broadcast display you are outputting toward. 5 One more thing: the “Timeline resolution” and “Pixel aspect ratio” your project uses (in the project settings) are written into the Dolby Vision metadata, so confirm your project sits at the final Timeline resolution and PAR before grading gets under way.

### DaVinci Resolve Grading Workflow For Dolby Vision
