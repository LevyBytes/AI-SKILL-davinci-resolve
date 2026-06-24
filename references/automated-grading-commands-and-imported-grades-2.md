# Automated Grading Commands And Imported Grades (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Shot Match command run against whichever clip should serve as the target for your other highlighted clips Should the automated match it produces look right and play back nicely, then well done: you now hold a fine foundation for further grading. Bear in mind, though, that even when the match it produces falls short of perfect, it may already have resolved enough of the discrepancies between your target clip and the clips being matched that only minor, readily noticeable tweaks remain before the shots across a scene line up. In either situation, time is saved.

### Suggestions for Using Shot Match

You can absolutely highlight every clip in a scene and run Shot Match, and the outcome might turn out beautifully according to the sort of imagery the scene holds. For certain other scenes, however, this won’t reliably deliver your strongest results. Be deliberate about which clips you pick to match against each other. Avoid running Shot Match on shots you already know carry identical lighting, because you risk Shot Match introducing a small tweak that could in fact leave the shots matching one another worse. Regard Shot Match as an instrument for reconciling clips that appear different. Working through Shot Match one angle at a time can help too, as can running a brief test before you commit to matching a whole batch of clips. As an example, picture a scene built from angle A (which is an over on character 1), together with angle B (an over covering character 2), plus angle C (serving as a master shot), where you wish to match the scene entire scene to angle C because its lighting is best. To begin, match a single shot from angle B against your

favorite shot from angle C, and judge whether you like how it came out. If you do, then proceed to highlight all the angle B clips and match them against angle C, then turn next to testing one shot from angle A. Working this way, whenever some angle refuses to behave under Shot Match, you can attempt matching it against one of the scene’s other angles you have already matched and check whether the result improves. NOTE: Bear in mind that, because every clip in the Timeline carries its own undo stack, a shot match operation applied to several clips together cannot be undone in one step. Watch out for clips holding broad regions of background color that match none of a scene’s other angles, for instance a shot-reverse-shot sequence cutting back and forth between a person standing in a back yard and a person standing in front of a purple wall. Trying it to see the outcome is fine, yet color spread like this can frequently skew Shot Match results.

### Broadcast Safe

Whenever you routinely deliver against strict QC standards, you can switch on Broadcast Safe within the Color Management panel of the Project Settings as you grade, holding the video signal’s luma as well as its chroma inside one among three tiers of permissible overshoots and undershoots.

The Broadcast Safe settings, located inside Project Settings under the Color Management panel

- Broadcast safe IRE (mV) levels: This drop-down menu lets you pick one of three degrees of aggressiveness for clamping the signal. Select whichever range matches your QC requirements. Your choices are “–20 - 120” (permissive), “–10 - 110” (conservative), and “0 - 100” (very conservative).
- Make Broadcast Safe: This checkbox switches broadcast safe limiting on or off.

NOTE: On its own, the clipping that Broadcast Safe applies carries no naturally soft rolloff. To get the best outcome, pair Broadcast Safe with the Soft Clip controls on the Color page, or with a Soft Clip LUT.

Further detail appears in Chapter 4, “System and User Preferences.”

### Using CDL Grades

Two situations exist in which primary grading changes can land on a clip apart from the changes you carry out inside the Node Editor of the Color page. When you import a CDL (Color Decision List), the CDL adjustment belonging to each clip becomes accessible through a contextual menu command in the Thumbnail timeline of the Color page. Additional detail is in Chapter 149, “Copying and Importing Grades Using ColorTrace.”

### Using ARRI Looks

Should you have brought in ARRIRAW media or QuickTime-wrapped Apple ProRes off an Amira, Alexa SXT or Alexa LF, or MXF-wrapped Apple ProRes off an Alexa Mini LF that carries embedded ARRI Look metadata (CDL + LUT), that embedded look can be transferred onto whichever node is currently selected on the Color page. To transfer an ARRI look out of the source media and onto the current node: 1 In the Node Editor, select the node you want the look data applied to. 2 Right-click the thumbnail of that clip and pick Apply ARRI CDL and LUT. The selected node then receives a LUT and Color Wheels adjustment.

Invoking the Apply ARRI CDL and LUT command brings a look across from the source media onto a node sitting in the Node Editor
