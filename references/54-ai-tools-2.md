# Ai Tools (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

For now, Face Age Transformer puts age onto the face alone; there’s no promise the subject’s neck, ears, or hair color will shift along with it. Now and then, areas beyond the face do get touched. Should that happen, you may want to lay a separate tracking mask over the face so the effect stays penned to the face by itself. Faces that are deliberately dirtied or thrown into shadow can likewise trip up the AI analysis. Running the Face Age Transformer breaks into two parts. Part one is pinpointing and tracking the face you mean to age; part two is dialing in how much aging gets laid on.

### Face Location and Tracking

This set of tools pinpoints the face you mean to age and follows it across the clip.

- Face Location: Tells the tool where to hunt for the face being aged. Detected: Locate the face by tracking it through the effect’s own internal tracking tools. From Input Alpha: Locate the face by drawing on an alpha channel input fed from another node. Should you need it, there’s a choice to preview that alpha channel.
- Detect Faces in Frame: Press this button and the tool rings every recognizable face in the frame with a bounding box. Where several faces show up, click a box to settle on the one you want aged. The face box in play goes green, while the rest, left untouched, sit in red.
- Track Reverse: Runs the face box backward from where you are now to the very start of the clip.
- Track Reverse 1 Frame: Steps the face box one frame backward from where you are now.
- Find in Frame: Locks the face box onto a face in the present frame, which helps when tracking got broken off.
- Track Forward then Reverse: Drives the face box back to the clip’s start, then

ahead to its end, making certain it’s been tracked across the clip from end to end.

- Track Forward: Runs the face box forward from where you are now out to the end of the clip.
- Track Forward 1 Frame: Steps the face box one frame forward from where you are now.
- Show Overlay: Tick this box to flip the face box overlay on or off inside the viewer.
- Manual Adjustments: A keyframable attribute through which you can override the tracking data driving the

face position.

### Age Shift

This set of tools steers the AI aging parameters. Every value reads in human years.

- Subject’s Age: Set this slider to match how old the subject in the frame looks to you.
- Age Offset: Set this slider to however many years you’d like added onto or pulled off the subject. From there the Face Age tool ages the subject’s face up or down on its own.

NOTE: When the Subject’s Age field carries a fairly low number (say 30), pushing the Age Offset toward lower values eventually stops doing anything, since the model can only reach so far.

### AI Face Reshaper

With the Face Reshaper you can resize and reshape the various features of a subject’s face while holding the result temporally consistent right across the clip. A light hand suits the Face Reshaper best, leaning on small, understated tweaks. Evolution has left us acutely tuned to faces, so leaning on this toolset too hard sends the result tumbling into the uncanny valley in no time.

### The original image

The Face Shape operation shrinking the size of her mouth.

Running the Face Reshaper splits into two parts. Part one is pinpointing and tracking the face you mean to shape; part two is dialing in the actual shaping you want laid on.

### Tracking

- Detect Faces in Frame: Hit this button so the tool boxes each recognizable face in the frame inside a bounding box. When more than one face appears, click a box to pick the one you’d like reshaped. Whichever face box is active turns green, and the others, left alone, stay red.
- Track Reverse: Carries the face box backward from your current spot all the way to the clip’s opening.
- Track Reverse 1 Frame: Nudges the face box a single frame backward from your current spot.
- Find in Frame: Pins the face box to a face within the present frame, handy whenever tracking got cut off.
- Track Forward then Reverse: Sends the face box back to the clip’s opening, then

onward to its close, so that it ends up tracked over the clip’s full span.

- Track Forward: Carries the face box forward from your current spot out to the clip’s close.
- Track Forward 1 Frame: Nudges the face box a single frame forward from your current spot.
- Show Overlay: Mark this box to switch the face box overlay on or off within the viewer.

### Face Location

- Manual Adjustments: A keyframable attribute letting you override the tracking data behind the face position.
- Interpolate: Should tracking errors crop up, you can plant your own start and end points for the face’s movement and let the tool fill in the frames between on its own. For the start frame, move to a frame and tick this box. For the end frame, move to a frame, drag the face box onto the face’s spot, then clear this box.

### Face Shape

- Adjust Face: Ticking this box turns the Face Shape toolset on or off.
- Size : Scales the face’s overall size up or down.
- Width : Scales the face’s width up or down.
- Length : Scales the face’s length up or down.
- Cheek Position : Sets the cheek bones higher or lower on the face.
- Chin : Scales the chin’s size up or down.
- Jaw : Scales the jaw’s size up or down.
- Forehead : Scales the forehead’s size up or down.

### Eyes

- Adjust Eyes Separately: Ticking this box breaks the toolset into left and right eyes handled on their own.
- Adjust Eyes: Ticking this box turns the Eyes toolset on or off.
- Size: Scales the eyes’ overall size up or down.
- Height: Scales how wide open the eyes sit.
- Separation: Sets how far apart the eyes are.
- Position: Shifts the eyes higher or lower on the face.
- Angle: Sets the tilt angle of the eyes.
- Eyebag: Shifts where the bags beneath the eyes sit.

### Nose

- Adjust Nose: Ticking this box turns the Nose toolset on or off.
- Size: Scales the nose’s overall size up or down.
- Width: Scales the nose’s width up or down.
- Height: Scales the nose’s vertical height on the face up or down, rather than how far it juts

out from the face.

### Mouth

- Adjust Mouth: Ticking this box turns the Mouth toolset on or off.
- Size: Scales the mouth’s overall size up or down.
- Position: Shifts the mouth higher or lower on the face.
- Width: Sets how wide the mouth is.
- Smile: Bends the angle of the mouth toward a smile or a frown.

### Eyebrows

- Adjust Eyebrows Separately: Ticking this box opens up a separate left / right Eyebrow toolset.
- Adjust Eyebrows: Ticking this box turns the Eyebrow toolset on or off.
- Position: Slides the brow higher or lower along the face.
- Separation: Sets how far apart the eyebrows are.
- Thickness: Scales the eyebrows’ thickness up or down.
- Tilt : Sets the angle of the eyebrows.

### AI Blemish Removal

Blemish Removal is an AI powered tool aimed at clearing facial and skin blemishes such as acne, scars, and other imperfections. As the resolution of video cameras climbs, a face in close-up can blow up even the faintest skin flaw into a glaring distraction. This is a dead-simple skin-smoothing tool, and your actors will love you for it.

- Strength: Sets how much Blemish Removal is applied.

### The original footage

### After Blemish Removal

NOTE: Faces deliberately dirtied (think a firefighter with soot across their face) can throw Blemish Removal off.

### AI Slate Finder and AI Slate ID

Slate Finder leans on AI to spot slates (clapper boards) on its own and flag where they sit across your clips, the clapper close point included. Slate ID reads off the Scene, Take, Angle, Shoot Day and whatever else is written on the slate, then hands you choices for filling in a clip’s metadata. Being an AI based operation, Slate Finder and Slate ID first need an AI model pulled down from the Extras Download Manager. To work through slates, in the Media Page pick the clip or clips bearing the slates you’re after, then rightclick one of them and choose AI Tools > Analyze for Slate. Alternatively, switch on Analyze for Slate inside the AI Clip Analysis tool, whose icon sits up top of the Media Pool.

Slate Finder has pinned down the frames the slate turns up in and tagged them with a yellow duration marker. NOTE: At this beta stage, Slate Finder and Slate ID remain works in progress, so not every function may be fully there yet.

### AI UltraSharpen

UltraSharpen is built to deliver exceptionally high-quality sharpening across moving video images. Because UltraSharpen is an AI tool, it sharpens selectively, hitting only the spots it judges need it rather than blanketing the whole image. Put plainly, a shot that’s a touch soft or out of focus may well be salvageable through UltraSharpen. It can likewise lift the resolution of low resolution footage in a smart way.

The subject in this frame is slightly out of focus

The subject with UltraSharpen — see how detail climbs across the face and hair while the background is left alone. The tool couldn’t be simpler, carrying just one control. Sharpen Amount: Dial in how much sharpening lands on the image.

### AI Motion DeBlur

Motion DeBlur is an AI tool built expressly to clear away the usual motion blur artifacts, softness in a clip among them. The payoff is crisper, sharper-focused images out of footage captured at slow shutter speeds. Being an AI based operation, Motion DeBlur first needs an AI model pulled down from the Extras Download Manager. Motion DeBlur renders fresh media clips onto your workstation and drops them into your Media Pool, leaving the original footage in place.

The original footage with motion blur.

The crisper footage after the Motion DeBlur operation.

To run Motion DeBlur on a clip: 1 In the media pool, pick one or more clips. 2 Right-click one of them and choose AI Tools > Remove Motion Blur 3 Set the file name, codec, and mode within the Remove Motion Blur dialog 4 Hit Render. NOTE: Motion DeBlur leans hard on your resources, and analysis can run as long as 60 seconds for every second of footage.

### The Remove Motion Blur Dialog

Within the Remove Motion Blur dialog you can set these parameters:

- File Name: Where you name the file for the new DeBlurred media clip.
- Format: Pick the video format the new DeBlurred media clip takes.
- Codec: Pick the video codec the new DeBlurred media clip takes.
- Type: Pick the video codec type the new DeBlurred media clip takes.
- Mode: Decide how much blur to strip from the clip — standard or extreme, hinging on how much motion blur you began with.
- User selected mark in and out: Tick this box and only the media sitting between the clip’s set In and Out points renders, which keeps render times in check. Clear it and the whole clip renders.
- Render at source resolution: Tick this box and the new DeBlurred media clip renders at its source resolution. Clear it and it renders at the timeline resolution instead.
- Use more GPU memory for higher quality: Tick this box to throw more GPU ram at the operation, buying higher quality results.

A few pointers for getting more out of Motion DeBlur:

- The model usually copes well with mild motion blur that comes from slow camera panning.
- Clips carrying obvious camera shake can land fine too, as long as the main subject stays in view across every frame. Footage that keeps the subject close to the frame’s center for the whole clip especially tends to fare better. Minor shifts in framing are fine and can still turn out good results.

As an instance, capturing a city scene while strolling slowly or standing put with a bit of handheld wobble can do the trick.

- Clips holding at least a few sharp frames tend to deblur more strongly. A video might, for example, blur briefly during a step or a movement while its other frames stay reasonably clear.
- Bumping up the frame rate can help in tougher cases, though motion blur that’s extremely severe may still sit past what the model can manage.
- Steer clear of very fast camera movement, above all when the subject tears across the frame — say, corner to corner inside a handful of seconds.
