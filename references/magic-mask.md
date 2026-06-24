# Magic Mask (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Magic Mask

Driven by the DaVinci Neural Engine and steered by where the user clicks, the Magic Mask palette builds precise masks on its own so you can single out people or objects, whole or partial, before applying secondary tweaks in DaVinci Resolve. The pages that follow explain how the stroke and tracking controls inside this palette let you direct these capabilities.

### Magic Mask v2 (Studio Version Only)

The AI engine beneath Magic Mask was rebuilt from the ground up, both to streamline the interface and to deliver markedly stronger output than before; this revision carries the name Magic Mask v2. Beyond sharper recognition of patterns and shapes, the gains show up most in tricky tracking scenarios, such as something crossing in front of the masked subject or other depth-related complications. The user-facing controls in Magic Mask v2 largely match the earlier Magic Mask, apart from these additions:

- Person and Object are no longer split into distinct modes. Magic Mask v2 copes with both

on its own.

- You no longer have to draw Strokes; that step now gives way to merely making

Clicks on the object to make a selection.

- A straightforward paint tool now lets you brush extra regions into or out of the

mask on a frame by frame basis. Using the DaVinci AI Neural Engine, the Magic Mask palette automagically produces a mask that singles out one or more people or objects within the frame, taking its cue from user-applied clicks that flag the subject to be separated out. You can generate masks covering a whole object or person, or limited to particular features of someone (their face, hair, arms, shoes, etc.). The two example image types below appear with Highlight switched on in the Viewer. A red onionskin overlay reveals exactly what Magic Mask has selected.

(Left) Magic Mask separating skin tones alone, (Right) Magic Mask separating the apron alone. Notice that although the apron and shirt share nearly the same color, Magic Mask reads the apron's form to build the mask. Although a mask from Magic Mask is frequently solid enough to drive high-quality isolated adjustments on its own, it will not always come out flawless. When that happens, the Matte Finesse controls allow you to soften and loosen the mask as much as you need to clean up the boundary of a tough subject you are separating with the aid of a second mask-building approach, like a qualifier key or window. To touch up a single frame in a hurry, the paint tool also lets you bring regions of the mask in or out by hand. When you are singling out particular features of someone, you can also combine different things you are separating to assemble precisely the mask you need. Following the earlier example, you might pull the face together with bare skin on the torso and arms, building a mask for one overall skin tone adjustment that leaves out the subject's hair and clothing.

Clicks you place to flag the subject drive this entire procedure. A standard workflow has you placing positive clicks (shown in blue) on top of the person or feature you intend to separate. After that, where needed, you can add subtractive clicks (shown in red) over portions of the picture that are not the person or feature being separated, fixing whatever flaws turn up in the resulting mask.

Blue clicks flag a person or feature to separate, whereas red clicks flag elements that ought to stay out of the mask. Here we placed one positive click (blue) to single out the wood cutting board, plus three subtractive clicks (red) on nearby objects that were also roughly wood-toned (the wood serving dish and pepper grinder at left, and her arm), guaranteeing they would not slip into the mask. As a rule, both positive and subtractive clicks ought to sit on the part of the person or object you mean to bring into the mask. Should a particular click you placed not produce the mask result you wanted, you can reposition it by dragging rather than clicking afresh; clicks stay live and can be picked with the pointer to be moved or removed.

One blue click on her back accurately masks her whole body, arms and hair included. Observe that Magic Mask v2 properly tells her apart from her mirror reflection, even where the two overlap.

While you work, every click appears in the Click list, where you can select, enable/disable, delete, and otherwise handle the various clicks you place to steer automatic mask generation.

The Click list keeps a record of every click you have placed.

### Tracking

Once you have placed one or more clicks to direct the analysis, the tracking controls inside this palette let you motion track those clicks so they trail the subject across that shot. When several clicks exist, all of them track together, and each click automatically rides along with whatever image detail sits right around it, so no setup is required. You merely place one or more clicks and then hit the track forward or backward button. As a click tracks, the overall tracking bar indicates which frames have already been tracked (tracked frames show blue).

Controls let you track every mask analysis click forward and backward across the shot. After you have added the clicks needed to single out the subject and motion tracked them to ride with the shot's movement, a mask is generated live and automatically for every frame of the shot. This matters because any edit you make, whether adding, removing, or hand-moving clicks, reshapes the resulting mask on the fly.

### Fixing Masks with the Paint Tool

Now and then the Magic Mask can drift during tracking and pull in something you did not want, or leave out something you did. A basic paint tool sits in the toolbar for patching gaps in the mask or stripping masked areas back out. Because the paint tool runs frame by frame, it does not track along with the mask. It works well for clearing brief mask glitches, but for anything beyond a handful of frames you are better off returning to the add and subtract tools to rework your mask.

The Add/Subtract Paint Stroke tools and the Brush Size control With the plus and minus paint tools you can place strokes onto, or pull strokes off of, the mask as needed, and the paint brush size tool lets you enlarge or reduce the brush that draws those strokes.

(Left) On this frame, Magic Mask mistakenly pulled the silver rings on her fingers into the mask. Across most of the track it did not, so only a handful of frames need correcting. (Right) Choosing the Subtract Paint Stroke tool (green circle) and tuning its size, we gently paint a gap in the mask across her rings.

The final frame, with the rings correctly excluded from the mask

### The Magic Mask Interface

Three groups of controls make up the Magic Mask palette: the Toolbar, the Click list, and the Mask Finesse panel. The Magic Mask palette starts out blank when you first open it, with a prompt telling you to click inside the Viewer to build a mask.

### The controls of the Magic Mask palette

### Magic Mask Toolbar

Most of the palette's interactive controls live in a toolbar across the top of the Magic Mask palette.

- Tracking Controls: These controls let you track all available clicks so they trail camera or subject motion within the frame. Reading left to right, they are:

Go To Reference Frame: Moves the playhead to the frame where you first placed the clicks. Go To First Frame of Tracked Area: Sends the playhead to the earliest tracked frame of a tracked range, readying you to track backward when untracked frames remain at the clip's start. Track One Frame Reverse: Steps one frame back and halts. Handy when you are tracking frame by frame to follow the progress of an especially intricate piece of motion. Should anything fail, you can return to the last frame where the click tracked the subject cleanly and drag the click to a stronger spot with the pointer so it follows correctly. If you must, advance one frame at a time, dragging the click to a better position whenever it loses the feature you are using it to single out. Track Reverse: Tracks nonstop from the current frame right back to the clip's start. Stop Tracking: Pauses the track whenever the track misbehaves and you need to adjust it. Track Forward and Reverse: Runs from the present frame through to the close of the clip, then loops back to the original tracking point and runs backward to the clip's opening. Track Forward: Tracks without pause from the present frame straight through to the clip's close. Track One Frame Forward: Advances one frame and halts. Handy when you are tracking frame by frame to follow the progress of an especially intricate piece of motion. If you must, advance one frame at a time, dragging the click to a better position whenever it loses the feature you are using it to single out. Go To Last Frame of Tracked Area: Sends the playhead to the final tracked frame of a tracked range, readying you to track forward when untracked frames remain at the clip's end.

- Click tools: A pair of tools on the right let you decide whether your clicks flag the feature you want to single out or flag things that are not the feature so you can trim away unwanted spread in the resulting mask. The plus eyedropper brings an area into the mask; the minus eyedropper takes an area out of the mask.
- Paint tools: These three paint tools handle fast touchup on a mask frame by frame. The plus paint brush adds to the mask, while the minus paint brush takes away from the mask. The paint brush size control lets you alter the brush size.
- Invert Mask: A button flips the resulting mask for cases where you want this palette's feature analysis to single out everything other than the feature or features being analyzed.
- Mask Overlay: Switches on an onion-skinned overlay so you can see which parts of the image are masked and which are not, letting you keep refining the result by adding, moving, or deleting clicks. The separated portion of the mask is shaded translucent red.

### Click List

After you begin placing clicks to flag features for mask generation, they show up in this Click list.

- Click list header: Sitting at the left of the Click list, the header carries controls for choosing and removing individual clicks.
- Click timeline area: A Timeline ruler indicates the length of the clip you are currently masking. The Overall Track shows how many frames of each click have been tracked. A small colored mark (blue or red) sits on each click track to indicate where the reference frame falls.

### Mask Adjustment Controls and Matte Finesse

Two groups of controls handle refining the mask the Magic Mask palette puts out. The upper group lets you tune how the mask is built from the analysis data, refining the mask result around traits of the image. Quality: Two choices let you balance quality against performance. Faster builds a lower-quality mask in less time, fine for garbage matting. Better builds a higher-quality, more detailed mask that demands more processing. Smart Refine: While in Better mode, this control lets you grow or shrink the resulting mask using the image analysis, so growing the mask does not push it far into nearby image regions unconnected to that person or object. The operation adds no softness. Rather, it grows or contracts the overall mask this palette generates. A second group of mask manipulation controls handles the mask once it has been built. Most of them are the same Matte Finesse controls found in the Qualifier palette, handy for resolving trouble with problem masks or for feathering edges when you want a softer result.

- Mode/Shape: Lets you decide how to alter the Alpha channel/key. Pick Shrink or Grow to erode or dilate the matte edges with fine precision. Or pick Opening or Closing to fill or open holes for tidying a ragged matte. Shape lets you set the shape of that growth or contraction.
- Radius: this slider sets how far to shrink, grow, open, or close the edge's key.
- Smoothing: Smooths across the temporal frames.
- Blur Radius: In modest doses, blurring a key works nicely to soften problem edges. That said, blurring a key can also push a key's edges out past the subject border you are keying, leaving a visible "halo" around your subject, depending on the adjustment at hand.
- Clean Black: Clean Black is a dedicated operation that removes noise that appears as white speckling within the black region of a key. Turning Clean Black up lets you "fill holes" in the background part of a key and wear away translucent edges.
- Clean White: Clean White is a second dedicated operation that removes noise (appearing as black speckling when you view a high-contrast highlight) within the white part of a key covering the image regions you are separating, and it grows the key by making bright parts of a key brighter the higher you set it, nudging light gray key areas toward white. In practice, raising Clean White lets you "fill holes" in the foreground part of a key and extend translucent edges.
- Iterations: Refines the recognized shape.
- Denoise: Offers a separate route for post-processing pulled keys so you can selectively cut the noise within

a key, clearing away scattered patches of qualification and gently sealing gaps in a matte.

- In/Out Ratio: Reaching for In/Out Ratio can help cut down fringing. Turning In/Out Ratio up fills small black holes within the matte, while dropping In/Out Ratio under 0 removes speckling by nudging tiny white matte bits toward black.
- Black Clip: Turning Black Clip up applies a "lift" adjustment so that translucent matte regions (the gray areas you see when viewing a high-contrast highlight) are nudged toward black.
- White Clip: Dropping White Clip applies a "gain" adjustment so that translucent matte regions (the gray areas you see when viewing a high-contrast highlight) are nudged toward white.
- Post Filter: Runs one last cleanup of the key against the original image as reference; handy for recovering some fine detail along sharp edges or in hair.
- Consistency: Once you have tracked every click to ride with the subject for the clip's duration, this setting lets you decide how much temporal smoothing it takes to calm jitter along the resulting mask edges in low-confidence regions, like frizzy hair or sheer clothing. Larger settings smooth the mask edges more but cost more processing and may change how tightly the mask trails motion in the image. Smaller settings run faster and more precisely but may permit more edge jitter in the resulting mask, which can distract from the final adjustment at hand. This parameter defaults to 0, so your very first run of Magic Mask always starts with the most precise (and potentially most lively) pass of this feature's analysis.

IMPORTANT: For Consistency to work right, a click has to span at least a handful of frames. That means tracking each click to ride with the motion of the camera and subject so each click's duration is extended. Since Consistency aims to wipe out one- or two-frame "noise" in the mask shape, short-duration clicks may wind up having their contribution removed. NOTE: You can still reach the original Magic Mask in DaVinci Resolve 20 by choosing Legacy Object Mask from the Magic Mask 2 options menu.

### Magic Mask v1 (Legacy Version)

NOTE: As covered above, Magic Mask v2 now takes the place of the original Magic Mask v1. The v1 Magic Mask does, however, stay reachable for legacy projects, and it is covered below. To turn it on, choose "Legacy Object Mask" from the Magic Mask 2 options menu. Using the DaVinci Neural Engine, the Magic Mask palette automagically produces a mask that singles out one or more people or objects within the frame, taking its cue from user-applied paint strokes that flag the subject for separation. You can generate masks covering a whole object or person, or limited to particular features of someone (their face, hair, arms, shoes, etc.). The two example image types below appear with Highlight switched on in the Viewer. A red onionskin overlay reveals exactly what Magic Mask has selected.

(Left) Magic Mask separating a whole person, (Right) Magic Mask separating someone's face Once the Magic Mask palette has built a mask, the Matte Finesse controls let you tune the mask's size and feathering. That helps you handle awkward edges that could give you away, depending on the kind of adjustment you are after. Although a mask from Magic Mask is frequently solid enough to drive high-quality isolated adjustments directly, it will not always come out flawless. Bear in mind that Magic Mask serves the rapid building of detailed garbage masks just as much as it serves direct isolation. In those cases, the Matte Finesse controls allow you to soften and loosen the mask as needed to clean up the boundary of a tough subject you are separating with the aid of a second mask-building approach, like a Qualifier key or window. If you run the Magic Mask palette inside the very node where you are also pulling a key in the Secondary palette, or drawing a window in the Window palette, that key or window and Magic Mask combine into a boolean intersection on output. So the isolation is confined to regions where both kinds of masks coincide.

(Left) Magic Mask building a mask, (Right) Pairing the Magic Mask with a circular window, where the resulting mask becomes an intersection of the pair

Magic Mask can also single out objects, letting you build elaborate masks of intricate shapes that other tools might struggle to separate. As an example, running Magic Mask in Object mode to alter only the wood grain part of this guitar.

(Left) Several Object-mode strokes separating the guitar's wood grain while leaving the musician's arm alone, (Right) The completed shot, its wood grain warmed When you are singling out particular features of someone, you can also combine different things you are separating to assemble precisely the mask you need. As one example, you might pull the face together with bare skin on the torso, arms, and legs, building a mask for one overall skin tone adjustment that leaves out the subject's hair and clothing.

(Left) Magic Mask separating a face, (Right) Magic Mask separating every bit of exposed skin As noted earlier, strokes you draw to flag the subject drive this entire procedure. A standard workflow has you drawing brief positive strokes (shown in blue) over the person or feature you intend to separate. After that, where needed, you can paint brief subtractive strokes (shown in red) over portions of the picture that are not the person or feature being separated, fixing whatever flaws turn up in the generated mask.

Blue strokes flag a person or feature to separate, whereas red strokes flag elements that ought to stay out of the mask.

As a rule, both positive and subtractive guidance strokes ought to be fairly brief and placed on the part of the person or object you mean to bring into the mask. Where a stroke sits tends to matter more than how long it is, and in fact, if a particular stroke you drew does not give you the mask result you wanted, you can drag it elsewhere rather than redrawing it; strokes stay live and can be picked with the pointer to be moved or removed.

Choosing a stroke with the pointer; chosen strokes turn highlighted. Very long paint strokes are rarely much help and can backfire down the line when you try to track strokes so they follow motion in the clip. That holds especially true when a stroke has to trail something whose shape shifts as it moves, like an arm. What is more, although you may make as many strokes as you wish, fewer strokes outperform many, and as a general guideline you should not need more than five strokes to single out one person or feature (nor should you have to). While you work, every stroke appears in the Stroke list, where you can select, enable/disable, delete, and otherwise handle the various strokes you create to steer automatic mask generation.

(Left) Several Features-mode strokes separating exposed skin, (Right) The Stroke list records each stroke you have drawn. But what becomes of camera and/or subject motion, you wonder? Once you have painted one or more strokes to direct the analysis, the stroke tracking controls inside this palette let you motion track those strokes so they trail the subject across that shot. When several strokes exist, all of them track together, and each stroke automatically rides along with whatever image detail sits right around it, so no setup is required. You merely draw one or more strokes and then click the track forward or backward button. As a stroke tracks, the tracking bar for that stroke in the Stroke list indicates which frames have already been tracked (tracked frames show blue).

Controls let you track every mask analysis stroke forward and backward across the shot. After you have added the strokes needed to single out the subject and motion tracked them to ride with the shot's movement, a mask is generated live and automatically for every frame of the shot. This matters because any edit you make, whether adding, removing, or hand-moving strokes, reshapes the resulting mask on the fly.

### What Magic Mask Is Good For, and What It's Not

Bear in mind that the Magic Mask tool is not built for soft translucent mask edges of the sort the HSL, Luma, or 3D Keyers produce (when handled with care). It does, on the other hand, shine at building form-fitting masks that single out human features in cases where an ordinary keyer struggles. As an example, Magic Mask can separate bare skin in shots where the person stands before a backdrop of wood, stone, or soil sharing that person's color range. It can separate beige clothing against a beige backdrop. It can even separate a person inside a black-and-white clip. After you have drawn one or more strokes to single out a mask, a range of controls let you tune the resulting mask to better suit the subject when needed. Depending on the adjustment you are making to the subject in question, you may discover that the keys Magic Mask produces are enough to convincingly single out the person you are grading, especially while you work in Better mode. Still, real-world projects throw plenty of surprises your way. Bear in mind that, depending on your aim, the resulting automated mask will not always be flawless enough to stand in for careful rotoscoping on demanding secondary color adjustments. It has, however, been built to easily produce tight-fitting garbage masks for use alongside secondary keys or windows, with which to shut out the background surrounding a hard-to-separate subject. When you turn to Magic Mask for a garbage mask, bear in mind that the Faster mode is tuned to build looser masks faster for cases where you will pair it with a keyer or window to single out a particular region for special grading. TIP: The Magic Mask palette can even single out people in photos and paintings. That said, figurative artwork must carry a minimum of shadow rendering and anatomical detail before a figure or feature can be recognized. For that reason, cartoony or abstract artwork will not separate especially well.

### The Magic Mask Interface
