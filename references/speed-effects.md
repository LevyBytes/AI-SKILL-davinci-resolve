# Speed Effects

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Speed Effects

Whether you bring in linear and nonlinear speed changes from other software or build these effects yourself, the aim is to quicken or slow the clips in your programs. DaVinci Resolve offers a full suite of controls for making such effects by way of dedicated Retime controls, curves, and particular edit types. After an effect exists, DaVinci Resolve further gives you several methods of processing it so that playback comes out as smooth as it can possibly be.

### Speed Effects and Retiming

The term speed effects covers any effect that quickens, slows, or in some other way alters how fast clips play back in the Timeline. DaVinci Resolve gives you four fundamental routes to producing speed effects.

- Importing speed effects: DaVinci Resolve can pull linear speed effects out of imported EDL, AAF, and XML projects, plus nonlinear ones out of XML and AAF project files. Wherever such effects exist, DaVinci Resolve runs the clips at whatever speed has been specified. Your own speed effects can likewise be built with controls on the Edit page. Two avenues exist for adjusting a clip’s speed: the Change Speed dialog and the Retiming effect in the Timeline.
- Creating speed effects using Fit to Fill edits: A clip’s speed can also be altered in the Timeline by editing it with the Fit to Fill command, which retimes the clip so it spans whatever arbitrary duration you decide on in the Timeline. To read more about working with Fit to Fill, turn to Chapter 39, “Threeand FourPoint Editing.”
- Creating freeze frames: The freeze frame command lets you convert a whole clip into a freeze frame of whichever frame the playhead happens to cross.
- Creating simple linear speed effects: Straightforward fast or slow-motion effects can be made either through the Change Clip Speed command or by dragging the left and right handles of the Retime controls in the Timeline. This section walks through both approaches.
- Creating variable speed effects: For far more intricate variable speed effects, where a single clip quickens and slows several times by varying degrees, turn to either the Retime controls or one of the two available speed curves. These techniques get coverage later in this section as well.

### Speed Effects and Audio

Every technique DaVinci Resolve provides for making linear speed effects — among them the Retime controls, the Fit to Fill edit, and the Change Clip Speed command — retimes a clip’s audio alongside its video, doing so without pitch correction on Linux and Windows but with pitch correction on Mac OS X (Yosemite and above). Audio paired with variable speed effects, on the other hand, gets muted.

### Creating Freeze Frames

Several routes lead to a freeze frame, but the quickest is to park the playhead on the frame you’d like frozen, then choose Clip > Freeze Frame or press Shift-R. The whole clip turns into a freeze frame of the frame the playhead was sitting on. To undo the freeze frame effect, you can either select the clip and strip the speed effect away through the Remove Attributes dialog, or just open the Change Clip Speed dialog and clear the Freeze Frame checkbox.

### Creating Simple Linear Speed Effects

When your only goal is to play a clip in slow motion, run it faster, reverse it, or freeze a frame, a simple speed effect applied through either the browser or the Change Speed dialog does the job. To change a clip’s speed, do one of the following:

- With a clip selected, choose Clip > Change Clip Speed and work the controls in the Edit Speed Change dialog.
- Right-click a clip in the Timeline, pick Change Clip Speed, and operate the controls in the Edit Speed Change dialog.
- The speed of several selected clips can be altered all at once by way of either the Inspector or the Change Clip Speed dialog box.

The options offered by Change Clip Speed operations are:

- Change Clip Speed parameters: Resets the chosen clip’s speed by any percentage, frame rate, or duration you prefer.
- Ripple Sequence checkbox: Tick this checkbox if you’d like the upcoming speed change to ripple the Timeline, shoving every clip after the current one along to make room for the clip’s altered size.

### Speed effect parameters shown in the Speed dialog

- Reverse Speed checkbox: Ticking this box flips the present speed to a negative figure, sending the clip’s motion into reverse.
- Freeze Frame checkbox: Turns the whole clip into a freeze frame of whatever frame the playhead currently rests on.
- Pitch Correction checkbox: Tick this box and pitch correction runs on the clip’s attached audio, so that even as the audio’s length shifts to match the picture speed it keeps sounding natural. Keep in mind that pitch correction across large speed adjustments may not sound as pleasing as it does on small ones.
- Maintain Timing/Stretch to fit radio buttons: Picking Maintain Timing keeps every keyframe in the clip pinned where it began, whereas picking Stretch Keyframes squeezes or stretches all Composite, Transform, and Cropping keyframes by the same percentage as the clip throughout a speed change.

### Speed Change Controls in the Video Inspector

A clip’s speed can equally be tweaked right within the Video Inspector’s Speed Change controls. One advantage of this route is that it works on both the Cut and Edit pages.

- Direction: Picks the clip’s intended motion — forward, backward, or freeze frame.
- Speed %: Moving this slider shifts the clip’s motion on a percentage basis.

This value can be keyframed.

- Frames Per Second: Moving this slider alters the clip’s motion by raising or lowering how many frames per second it plays back at. This value can be keyframed.
- Duration: Decide outright how long the clip should run by entering a specific duration here using HH:MM:SS:FF format. Resolve then automatically tunes the clip’s speed so every frame plays within exactly that span of time.
- Ripple Sequence checkbox: Tick this checkbox when you want the upcoming speed change to ripple the Timeline, shoving every clip after the current one along to accommodate the clip’s revised size.
- Pitch Correction checkbox: Tick this box and pitch correction is applied to the clip’s attached audio, so even though the audio’s length shifts to match the picture speed it still sounds natural. Bear in mind that, across large speed adjustments, pitch correction can sound less convincing than it does on small ones.

### The Speed Change controls in the Video Inspector

### Clip Retiming Controls

A further way to change clip speed in the Timeline is by applying the Retime effect. This style of retiming hands you a handy control overlay for tuning clip speed right in the Timeline, and it also supplies the controls you need to build variable-speed effects. To bring up the Retime controls on a clip:

- With a clip selected, choose Clip > Retime Controls (Command-R).
- Right-click a clip and pick Retime Clip out of the contextual menu.

The Retime controls then sit over that clip in the Timeline. They comprise a Retime control track stretching across the top of the clip, its arrows signaling playback speed and direction (the default blue right-facing arrows mean normal 100% playback), together with a Clip Speed pop-up menu centered at the clip’s bottom that also reports the clip’s present speed.

### The Speed effect controls in the Timeline

### Retiming an Entire Clip

Using the Retiming effect at its most basic means changing the playback speed of the whole clip, which in turn ripples everything in the Timeline lying to the right of the retimed clip as its length grows from stretching or compressing it. To retime a clip by dragging: Bring the pointer over to either end — left or right — of the Speed Change name bar atop the clip, and once it becomes a Retime cursor, drag that side to stretch or squeeze the clip into its new timing. To retime by an exact amount: 1 With a clip selected, press Command-R. 2 Click the pop-up that sits beside the speed percentage text along the bottom of the clip. 3 Do one of the following:

- Pick a fresh playback speed out of the Change Speed submenu.
- Pick reverse segment so the clip runs backward. Reverse speed appears in the Retime

control track as arrows that point left rather than right. To send a clip back to its original speed: Click the pop-up beside the speed percentage text along the bottom of the clip and pick Reset to 100%.

### Rippling or Overwriting the Timeline When Using Retime

Whether the clips lying to the right in the Timeline ripple to absorb the duration change brought on by the speed adjustments you make with the Retime controls comes down to which tool is active: the Selection tool/mode leaves the Timeline unrippled, while the Trim tool/mode makes it ripple.

### Reading Clip Speed Arrows

As you retime a clip, the Clip Speed pop-up menu reports the present speed of the whole clip. The arrows along the Retime control track, meanwhile, convey playback speed and direction. Drop clip speed under 100% and the Retime control track displays yellow playback triangles set farther apart. Push it above 100% and the track instead shows blue triangles packed closer together. Right at 100% normal speed, the track presents blue triangles evenly spaced, whereas blue arrows pointing left signal reverse playback. Here three clips each carry a different speed; reading left to right, the yellow arrows mark 100% speed, then slow motion, then fast forward.

### Creating Variable Speed Effects Using the Retime Controls

The Retime controls also let you drop freeze frames into the middle of a clip and craft other bespoke variable speed effects by means of speed points. Among the extra variable speed choices are rewind and speed ramp effects, which lay down speed points on their own to produce preset results. To freeze a frame at one specific instant: 1 With the Retime controls on display, bring the playhead to the frame within that clip you want frozen. The classic use is an effect where a character in motion abruptly halts on a chosen frame. 2 Open the Clip Speed pop-up menu (the one beside the speed percentage text along the bottom of the clip) and pick Freeze Frame. A pair of new speed points joins the clip, marking out a span over which it stays frozen on that frame. The vertical red bars in the Retime control track make this visible. Beyond the second speed point, the clip picks up playback from the very next frame onward.

3 Drag the second speed point either way to set how long the freeze frame lasts. The upshot is that the clip runs normally until the first speed point, holds on that frame through to the second speed point, and then carries on. To create variable-speed effects: 1 With the Retime controls showing, bring the playhead to the frame where you want the clip’s speed to shift, and pick Add Speed Point out of the Clip Speed pop-up menu. 2 Advance the playhead to the next frame where the clip speed should change again, and drop in another speed point. At least two speed points are required before any speed effect takes shape. 3 To change the speed of the clip segment falling between those two speed points, do one of the following:

- With the pointer, drag the top handle of the second speed point rightward to slow that segment’s playback, or leftward to quicken it, all within that one segment. The move either trims or extends the clip and, depending on whether the Selection or Trim mode is active, either overwrites or ripples the neighboring clips.
- Again with the pointer, you can drag any speed point’s bottom handle to broaden the stretch of clip running at that specific speed. That action shifts frames from before and after the segment being adjusted so all the speed segments keep the same speed, and it too trims or extends the clip, though by a different margin.
- Through the Clip Speed pop-up menu, select a new speed for the segment from the Change Speed pop-up menu. Any segment can also be made to run backward by selecting Reverse Segment.

4 To wipe out a speed point and drop that clip’s speed segment from the effect, pick Clear Speed Point from any Clip Speed pop-up menu, which removes whichever speed point sits to its left. While you’re building variable-speed effects, the arrows along the Retime control track help you stay oriented, and each segment’s speed pop-up reveals the real numeric speed. The shift in speed from one segment to the next is eased automatically, giving a smooth handoff between speeds.

Speed controls arranged to ramp across three distinct playback speeds; the spacing of the arrows conveys the timing Two further command sets exist for building preset speed effects that draw on multiple speed points.

To add a rewind effect: With a clip’s Retime controls showing, open any Clip Speed pop-up menu and pick a preset percentage out of the Rewind submenu. Two more speed points get appended past the rightmost speed point of the current segment, which makes that segment play in fast reverse at the chosen percentage and then run through a second time from its start.

Speed effect controls shown before and after a “rewind” effect is built To build a speed ramp: With a clip’s Retime controls on display, open any Clip Speed pop-up menu and pick one of the two entries in the Speed Ramp submenu, swapping the current speed effect for a run of five speed segments beginning at 10% and climbing in steps to 30%, 50%, 70%, and finally 90%. After it’s built, you can drag the speed points to tailor the effect to whatever durations you need.

Speed effect controls arranged to build a gradual ramp running from 0 up to 100 percent playback speed

### Closing Retime Controls

Once your Retime effect is complete, you can dismiss the Retime controls so the clip looks normal once more. Dismissing them changes nothing about the clip’s timing; it merely keeps you from accidentally nudging the clip’s speed with the mouse. To close the Retime controls in the Timeline:

- Click the X button up in the top left-hand corner of the Retime control box.
- Press the escape key.
- Pick the retimed clip, then either go to Clip > Retime Controls or hit Command-R.

Whenever a retimed clip has its Retime controls hidden, a Retime badge shows up just left of that clip’s name in the Timeline. The Retime controls can be reopened any time you need to make further changes.

The Speed Effect badge that shows a clip is being retimed To bring the Retime controls back in the Timeline: pick the retimed clip, then either go to Clip > Retime Controls or hit Command-R. Once a clip has been retimed with the Retime effect, that clip’s Retime Process parameter in the Inspector lets you set how its retiming is handled — through the low quality Nearest option, through Frame Blending, or through Optical Flow.

### Using Retime Curves

Optionally, curves can also retime clips, working either alongside the Retime controls or on their own. You might, for instance, lean on the simpler retiming controls first to lay down the broad speed effect you want, then bring in one of the available Retime Curves to fine-tune things by dragging Bezier curve handles that shape the handoff from one speed to another; alternatively, you could open either Retime Curve up front and build your speed effect from nothing by adding and tweaking control points and curve segments. Whatever your preferred approach, every speed curve’s control points line up 1:1 with the speed points shown in the Retime controls, and edits to a curve segment are echoed by speed point shifts in the Retime controls whenever both are open together. The practical payoff is that, when assembling complex variable retiming effects, it’s simple to grab whichever control most readily dials in the quality of speed you’re after.

With their handles, the Retime Curves let you shape the handoff between one speed and the next On top of that, two varieties of Retime curve are available for maximum flexibility. The better pick hinges on which you find more comfortable and on which more readily handles the kind of motion you intend to create:

- The Retime Frame curve presents a diagonal line standing in for a time graph. It’s the same sort of curve seen across many other post-production tools, where the vertical axis stands for each frame of that clip’s source media and the horizontal axis stands for each frame of playback in the Timeline. On the default diagonal graph, each frame of source media maps one-to-one with each frame of timeline playback, which equals 100% speed. Adding control points, though, changes how source frames map onto the Timeline. Take any two control points on the Retime Frame curve: as long as the left one of a curve segment sits lower than the right one, motion runs forward, with longer shallow segments yielding slower motion and steeper shorter segments yielding faster motion in the clip.

A diagonal Retime Frame curve (green) holding two segments: a long shallow one on the left producing slow motion and a short steep one on the right producing fast motion

- Should a curve segment’s left control point sit higher than its right one, the motion flips and that segment runs backward.

A Retime Frame curve (green) whose inverted curve produces reverse motion

- The Retime Speed curve presents a flat line standing for 100% speed. Speed changes when you add pairs of control points and drag each segment up or down — and it’s the segments you drag, not the control points themselves. Lifting a curve segment shortens it and quickens that stretch of the clip, while dropping a segment lengthens it and slows that stretch. As you work each curve segment, a tooltip reveals the precise speed percentage it stands for. Bear in mind that reverse motion can’t be made with the Retime Speed curve; for that you must fall back on either the Retime controls or the Retime Frame curve covered above.

A Retime Speed curve (blue) where raising the line between two keyframes boosts the speed, while the flat line along the 0 axis on either side marks normal 100% speed. Ways to handle speed curves: To bring up a clip’s speed curves within the Timeline: 1. Pick a clip in the Timeline and choose the Keyframes tab at the top of the interface. 2. Click the Keyframe Curves icon, which opens the Curve Editor for that clip. 3. Pick Retime Speed and Retime Frame out of the parameter list, after which you can edit them just like any other curve — adding, moving, and deleting control points.

### Speed Effect Processing

After retiming a clip, you gain the further option of changing how that clip gets processed so its visual playback quality improves — something that matters most for clips that have been slowed down. Two paths let you set this. The first is a project-wide setting found in the Master Settings of the Project Settings. The second is a per-clip setting in the Inspector that adjusts how clips are retimed. To set the Retime Process value across a whole project: 1 Open the Project Settings, then click into the Master Settings panel. 2 Pick an option out of the Frame Interpolation group’s Retime Process pop-up menu. For a single clip’s Retime Process value instead: choose the clip, open the Inspector, and pick an option from the Retime Process pop-up within the Retime and Scaling group. If you go with Optical Flow, you can additionally pick an option from the Motion Estimation pop-up. The various choices you have for processing speed effects are as follows: Retime Process: Lets you set a default way of processing clips in mixed frame rate timelines and those carrying speed effects (fast forward or slow motion), handled clip‑by-clip. Its default value is “Project Settings,” so every speed-affected clip is treated alike. Three options exist — Nearest, Frame Blend, and Optical Flow — each spelled out further in the Frame Interpolation section, see Chapter 4, “System and User Preferences.”

- Nearest: The leanest on the processor and the least refined method; frames simply get dropped for fast motion or duplicated for slow motion.
- Frame Blend: Likewise light on the processor yet capable of smoother output; neighboring duplicated frames are dissolved into one another to even out slow or fast motion effects. It can give better results in cases where Optical Flow throws up unwanted artifacts.
- Optical Flow: The heaviest on the processor but the top-quality way to process speed effects. Through motion estimation, brand-new frames are synthesized from the original source frames to build slow or fast motion. Output can be remarkably smooth when a clip’s motion is linear. That said, two moving elements passing in opposite directions or erratic camera movement may trigger unwanted artifacts.

Motion estimation mode: While Optical Flow handles speed change effects or clips whose frame rate differs from the Timeline’s, the Motion Estimation pop-up lets you settle on the rendering option that looks best for a given clip. Every method carries its own artifacts, and the top-quality option isn’t invariably the right pick for a given clip. Its default value is “Project Settings,” so all speed-affected clips get handled the same. A handful of options are offered.

- “Standard Faster” and “Standard Better” match the options carried over from earlier DaVinci Resolve releases. They lean lighter on the processor and deliver good quality fit for most situations.
- “Enhanced Faster” and “Enhanced Better” ought to outperform in almost every instance where the standard options show artifacts, the trade-off being heavier computation and therefore slower runs on most systems.
- “Speed Warp Faster” and “Speed Warp Better” exist for even higher-quality slow motion built on the DaVinci Neural Engine. How this setting turns out depends on the clip’s content, but under ideal conditions it delivers better visual quality with fewer artifacts than even the Enhanced Better setting.

### Optical Flow Quality Settings Affecting Speed Effects

Found in the Master Settings panel of the Project Settings, the “Motion estimation mode” pop-up lets you weigh quality against processing speed for slow motion and frame rate retiming effects that rely on optical flow. The “Standard Faster” and “Standard Better” settings carry over from earlier DaVinci Resolve releases. They lean lighter on the processor and deliver good quality fit for most situations. By contrast, “Enhanced Faster” and “Enhanced Better” ought to outperform in nearly every instance where the standard options show artifacts, the trade-off being heavier computation and therefore slower runs on most systems.
