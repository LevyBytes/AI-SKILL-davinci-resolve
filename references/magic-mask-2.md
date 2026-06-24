# Magic Mask (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Three groups of controls make up the Magic Mask palette: the Toolbar, the Stroke list, and the Mask Finesse panel. The very first time you open the Magic Mask palette it sits empty, prompting you to draw a stroke in the Viewer so a mask can be built.

The Magic Mask palette's controls shown while in Object mode Magic Mask Toolbar Most of the palette's interactive controls reside in a toolbar running along the top of the Magic Mask palette.

- Object Mode: Clicking this icon switches the Magic Mask tool to Object mode, meant for isolating subjects that aren't people.
- Person Mode: Clicking this icon switches the Magic Mask tool to Person mode, meant for isolating people along with portions of people. Over on the left, a tab control sets which kind of mask gets built, offering two options:

Person: Builds a mask that isolates whatever portion of a person the shot's framing leaves visible. Features: Builds a mask that isolates only a single area, such as someone's face, hair, or arms. While in Features mode, you may also fold several specific features together into one mask.

- Tracking Controls: The controls here let you track every available stroke so it follows camera or subject movement across the frame. Reading from left to right, they are:

Go To Reference Frame: Jumps the playhead to the frame where you first drew the strokes. Go To First Frame of Tracked Area: Jumps the playhead to the earliest tracked frame within a tracked range, setting you up to track backward when untracked frames remain at the clip's start. Track One Frame Backwards: Steps a single frame backward, then halts. This helps when you are tracking one frame at a time to watch how a tricky stretch of motion unfolds. Should anything go awry, return to the last frame where the stroke still tracked the subject cleanly, then drag the stroke with the pointer to a better spot so it locks back onto the subject. If you must, advance one frame at a time, nudging the stroke into a better position each time it loses the feature you mean to isolate. Track All Frames Backwards: Runs continuously from the present frame right back to the clip's start.

Stop Tracking: Halts the track whenever it runs into trouble and you need to make a change. Track Forwards and Backwards: Runs from the current frame through to the clip's end, then comes back to the original tracking point and runs backward to the clip's start. Track All Frames Forwards: Runs continuously from the present frame straight to the clip's end. Track One Frame Forwards: Advances a single frame, then halts. Handy when you are tracking one frame at a time to follow how an especially complicated stretch of motion plays out. As needed, move one frame at a time, sliding the stroke to a better position each time it drops the feature you are using it to isolate. Go To Last Frame of Tracked Area: Jumps the playhead to the final tracked frame within a tracked range, getting you ready to track forward when untracked frames sit at the clip's end.

- Stroke tools: A pair of tools on the right decides whether your strokes mark the feature you intend to isolate or mark what isn't the feature, the latter to trim unwanted overflow out of the finished mask. The plus eyedropper grows the mask by an area; the minus eyedropper trims an area away.
- Invert Mask: This button flips the finished mask, useful when you want the palette's feature analysis to isolate everything other than the feature or features it analyzed.
- Mask Overlay: Switches on an onion-skinned overlay so you can see which parts of the image fall inside the mask and which don't, letting you keep refining by adding, repositioning, or removing strokes. The isolated region of the mask carries a translucent red tint.

### Stroke List

As soon as you begin drawing strokes that mark features for mask generation, those strokes show up in this Stroke list.

- Stroke list header: Sitting on the left side of the Stroke list, the header holds controls for selecting, enabling/disabling, and naming each stroke, should you want that degree of organization. Right-click any stroke's header and you get controls to Reset Tracking Data and to switch the mask type between feature and not feature.
- Under Object mode, you simply get a flat list of strokes, each one helping to define either the object you intend to isolate or the background.
- Under Person mode, you likewise get a flat list of strokes, each one helping to define either the person you intend to isolate or the background.
- Under Features mode, an extra drop-down menu sets which particular feature a guidance stroke is meant to mark. The strokes are arranged hierarchically by their matching feature, so every Face stroke, for instance, sits beneath a Face title bar. Each feature's title bar carries a toggle that flips that feature off and on, and turning it off withdraws that feature's input to the overall mask being built.
- Stroke timeline area: A Timeline ruler lays out the length of the clip you are currently masking. Every stroke in this list owns a track showing how many of its frames have been tracked, and as you track a stroke its track fills with colored bars marking which frames now hold tracking data.

Strokes marking a person or object get blue tracks, whereas strokes marking what isn't the feature get red ones. This timeline lets you keep tabs on which strokes still need tracking and reshape the tracking data as required to land a usable result.

### Mask Adjustment Controls and Matte Finesse

Two groups of controls exist for refining whatever mask the Magic Mask palette outputs. The upper group governs how the mask is built from the analysis data, letting you tune the mask result according to the image's traits. Among them: Quality: A pair of options balances quality against performance. Faster turns out a lower-quality mask in a hurry, fine for garbage matting, while Better turns out a more detailed, higher-quality mask at greater processing cost. Smart Refine (Person Mode): This control grows or shrinks the resulting mask off the image analysis, in such a way that growing the mask won't push it far into neighboring image areas that aren't joined to that person. The operation adds no softness; rather, it scales the overall mask this palette produces up or down. Here 0.5 is unity, 0 is the most expansion, and 1 is the most contraction. Refine Range (Object Mode): This control tunes the resulting mask's sensitivity off the image analysis, letting you dial the mask to take in more or less of the chosen object. Here 30 is unity, 100 is the greatest sensitivity, and 1 is the least. The second group of mask controls works on the mask once it has been generated. Most of them are the very same Matte Finesse controls found in the Qualifier palette, handy for sorting out trouble masks or for softening edges when you need a more feathered outcome. For fuller detail on the Matte Finesse controls, turn to Chapter 137, “Secondary Qualifiers.”

One more control, though, belongs to the Magic Mask palette alone. Consistency: Once you have tracked each stroke so it follows the subject across the clip's length, this setting decides how much temporal smoothing is needed to tame jitter along the resulting mask's edges in low-confidence zones, such as frizzy hair or see-through clothing. Crank it up and more smoothing reaches the mask edges, but at higher processing cost and with a possible loss in how tightly the mask tracks motion in the image. Dial it down for speed and accuracy, accepting that more edge jitter may slip into the mask, which can prove distracting in the final adjustment you are making. The parameter starts at 0, so your opening pass with Magic Mask always launches from the most accurate (and possibly liveliest) use of this feature's analysis.

IMPORTANT: For Consistency to work as intended, a stroke must span at least a handful of frames. That means tracking each stroke so it follows the camera's and subject's motion, which lengthens the stroke's duration. Since Consistency sets out to wipe one- or two-frame “noise” from the mask's shape, strokes that last only briefly may find their effect canceled out entirely.

### Choosing What to Isolate

The pages here go deeper into the various isolation choices on offer and suggest where each one works best.

### Object Mode

Of all the options, Object mode is the simplest to settle on. In short, turn to it for any subject that isn't a person. Things like cars, pets, and food all make solid candidates for Object mode. The one clear exception is clothing such as shirts, hats, and the like worn by a human, since worn garments come out far better when isolated in Person mode instead. Positive strokes in Object mode grab regions of comparable contrast and color, which lets you stitch intricate shapes together. As a rule, an object demands more strokes to actively pin down than a person does, owing to the wider assortment of shapes at play. Negative strokes in Object mode carve away the parts of the object you would rather not isolate, whether that is something easy like pulling a car's wheels out of a mask or something trickier like dropping certain books from a mask of a bookshelf.

### Person Mode

With Person chosen, each stroke you lay over somebody works to isolate that person's whole body, or as much of them as the screen reveals. That sweeps in every garment they have on: a shirt or pants, shorts, a dress or skirt, a bathing suit, knickers, jumpsuits, a hat, footwear, and even armor or a space suit (yes, we have tried both), whatever the case. Clothing is, for the most part, correctly read as part of the isolation mask you are building. That said, very loose, flowing garments may call for an extra stroke or two to be recognized in busy visual compositions. Negative strokes, while you are in Person mode, flag everything that isn't the person being isolated, keeping the background and/or any other people out of the mask being built. They aren't required, though; reach for a negative stroke only when you spot a problem, such as a chunk of background sneaking into the isolation mask.

### Features Mode

Choosing Features brings a drop-down menu to the top of the Stroke list. Your first step is to pick from that menu the feature you want to isolate, after which you draw strokes over the chosen feature (face, hair, and so on) you mean to isolate. Every feature's set of strokes can be switched on or off to fold that feature into the overall mask under construction.

- Face: Isolates only the face and ears, eyes and glasses included, while leaving out the hair and the neck (which counts as part of the torso). Facial hair, big beards especially, usually falls outside an opening stroke placed on bare facial skin, so you can keep to just the skin if that is what you want; a further stroke on the beard, however, brings it into the face isolation.
- Hair: Isolates the hair alone, ending at the bangs and ears and shedding as much of the face as it can. Curly, frizzy, or wispy hair yields oversized masks that try to take in as much hair detail as possible. This tool won't produce fine transparency. Delicate, irregular hair detail can give rise to jittery edges, though the Consistency control can rein that in.
- Torso (Exposed Skin): Isolates the bare skin sitting above the waist and below the face, leaving the arms out. Enable this selection when you need to isolate the neck, neckline, and whatever part of the chest shows through v-necks, plunge necks, tank tops, crop tops, or bikini tops.
- Clothing (Top): Whatever clothing sits above the waist; bare skin is left out.
- Clothing (Bottom): Whatever clothing sits below the waist; bare skin is left out.
- Arms (Exposed Skin): The bare stretches of arms or hands. Shirt and dress sleeves are left out,

as are sun sleeves.

- Shoes: Shoes of most styles will be isolated.
- Legs (Exposed Skin): Isolates the bare skin below the torso, while skipping socks and leggings.
- Hat: Hats of most styles will be isolated, though slim accessories like trailing ribbons or

feathers may be left out. Bear in mind that whichever feature you have set out to isolate, you can always lay down negative strokes to drop other parts of the person or their clothing that are wrongly creeping into the mask. IMPORTANT: While drawing strokes in Features mode, accidentally placing a stroke over some feature other than the one picked in the drop-down menu atop the Stroke list will yield a thoroughly wrong mask. Should that occur, delete the stroke you just drew, confirm which feature is currently selected, and then either redraw the stroke or switch to the correct feature you want to isolate.

### Identifying More Than One Person

Within either Person or Feature mode, you may add strokes that mark more than one person, or the features of more than one person. No special trick is involved; just draw strokes over each person you want to isolate, or over the matching feature of each person you want to include (say, drawing a stroke across three people's faces while in Face mode).

Strokes drawn over several people will isolate them all together inside a single mask.

### Using Matte Finesse Controls

Plenty of times a mask that looks troublesome can be salvaged with the Smart Refine and Matte Finesse controls over on the right of the Magic Mask palette. When the mask misses by only a few pixels and the color change you have in mind is fairly gentle, you can likely lean on Blur Radius and In/Out Ratio to build a soft edge that tapers off right at the subject's outer boundary (avoiding any halo) to carry your adjustment.

(Top) The initial mask's hard edges don't quite reach the edges of the woman's arm closely enough for a subtle adjustment, (Bottom) Calling on the Blur Radius and In/Out Ratio controls to form soft edges that stay within the subject and yield a usable mask

### Using Magic Mask as a Garbage Matte

When a person's outer edge isn't being picked up tightly enough for Magic Mask to deliver a usable result for a more drastic color change, you are generally better served by growing the result into a snugly fitting garbage matte, then isolating the person or features through other means, such as a keyer in the Qualifier palette. Even here, you will find that

Magic Mask usually beats rotoscoping a reasonably tight garbage matte over a moving figure with windows.

(Top) The initial mask doesn't sit close enough to the edges for a drastic adjustment, (Bottom) Reaching for the Mode/Shape/Radius/Iterations/Blur Radius controls to grow the matte into a garbage matte suited to other keys

### Dealing With Hair

Wispy or frizzy hair, stray strands flung back, and the tips of dreadlocks or heavily moussed hair that taper to points will frequently call for extra care with this tool. Bear in mind that the Magic Mask tool isn't built for soft, translucent mask edges the way a keyer is. For hair that hangs loose and free, you can often coax out a workable result by using the Matte Finesse controls to grow a softened copy of the matte until it covers the whole hairstyle. Should that bleed too much into the edges of other features on the subject you are isolating, build a dedicated hair mask in Features mode by drawing Hair strokes. From there, the Matte Finesse controls on the right of the palette let you fashion softened edges that sit well against the outer boundary of the hairstyle you are isolating.

### Creating a soft-edged hair mask

From here you might attempt separate color adjustments across two distinct correction nodes, one handling the subject's hair and another using Magic Mask to isolate everything except the hair. Or, if you would rather have one matte that isolates the whole subject, bring in extra instances of the Magic Matte tool (one to a node): let one node isolate just the face and body minus the hair, and a third node isolate the entire subject but with a very soft edge. After that, a Key Mixer node can merge all these masks together with the original hair mask you made, feeding a complete key into yet another node that carries out the correction.

(Left) Nodes 2, 3, and 4 build three separate masks that a key mixer combines and routes into the Key input of Node 5 for an adjustment, (Right) The end result of this three-mask method. Soft-edged hair can be tough, yet Magic Mask shines on plenty of elaborate hairstyles full of intricate shapes and hair accessories, jewelry and ribbons included. The stylized coiffures seen in European and Chinese period movies and shows, for instance, give the DaVinci Neural Engine no trouble whatsoever, all the more so because such styles are typically bound tight with no wispy hair. Lopsided hairstyles may need additional strokes to pick up hair that runs noticeably longer on one side of the face. The same can hold for offbeat styles, like hair molded into pronounced sculptural forms. Finally, tight braids that lay bare scalp skin also test the kind of hard masks Magic Mask turns out, so in those cases you are better off treating Magic Mask as a garbage matte and bringing in a keyer to craft a detailed soft mask.

### About Hats

Magic Mask copes with a remarkably broad range of hats drawn from every era. Trouble can arise from a hat's tassels or fine touches like feathers (in our tests, that feather perched on Errol Flynn's Robin Hood cap couldn't be brought in reliably, even while the cap itself posed no difficulty). On top of that, veils attached to hats may or may not register easily, though one more stroke usually clears the issue up.

### Dealing With Accessories

Objects a person holds, handkerchiefs or umbrellas say, are best handled in Object mode. Jewelry and watches raise a particular difficulty, since they tend to be so slim and small that leaving them out is hard, yet depending on the adjustment you intend you may not want them in at all. How things turn out depends on how thick the items are and how your subject is framed, but on the whole you will probably fare better by just adding a stroke or two to fold these items into the isolation, given that dropping fine detail like a necklace can get messy.

### Adding Strokes to Guide Mask Creation

What follows are a few pointers on drawing strokes to analyze the image. To pick out people, begin with one short positive stroke (blue) placed over the center of the face or body.

Drawing the first stroke to mark an entire person Based on what you get, you may need further strokes to tell an arm or frizzy hair apart from the background. When adding a stroke to an arm or hair, keep it off the very edge; the aim isn't to outline the subject but to use strokes inside the subject's body to spell out which features belong to it and which do not.

Adding a stroke to the arm so it gets included too As you go, fight the temptation to pile on strokes. A single one may be all it takes, or perhaps two or three, but going past five strokes on any one subject or feature is liable to create more trouble than it cures.

### Adding negative strokes to the reflection to remove

For faces, open with one short stroke across the middle of the face, running along the nose, or from the eyes down to the lips. Depending on what comes back, you may want more strokes to mark the chin, a beard, or to set the forehead apart from wispy hair.

Drawing strokes to mark a face; note that extra strokes are required to take in the beard. A sound approach is to lay down a single stroke and then track it across the clip's full length (covered further along in this section). Watching the whole clip reveals which portions of the mask might act up, and that tells you where to drop additional strokes so the person reads more clearly against the background, tidying up the resulting mask. Each time you add a stroke, track it too and observe how it goes. If you catch background areas wrongly slipping into the mask, drop a negative stroke (red) to signal that those image regions ought not be isolated. Short strokes, longer ones, and zig zags all serve backgrounds well. Because strokes merely nudge the analysis to refresh the mask, you can experiment with different stroke types to discover what serves best, then delete any stroke that fails to deliver. Just as with positive strokes, never use more than are strictly required to reach the result you are after.

(Left) The microphone wrongly read as part of the woman being interviewed, (Right) Drawing negative strokes to brand the microphone as background, sweeping a zig-zag pattern to tag the whole microphone

In much the same way, when you are isolating features like a face and some other feature, hair perhaps, keeps intruding, you can place a negative stroke on the hair to declare it no part of the face. If the resulting mask contains a “hole” that actually belongs to the background rather than the subject, try drawing a stroke that links that hole back to the rest of the background.

Drawing strokes to join the background to itself, clearing away part of the mask that doesn't belong to the person If an “island” turns up in the mask that genuinely belongs to the subject and not the background, try drawing a stroke across the island that ties one solid stretch of the mask back to itself.

Drawing strokes to fill an island within the subject being isolated Naturally, pulling a mask out with strokes is only the opening stage of making a usable mask. The Quality, Consistency, and Smart Refine controls let you tune the image's stroke analysis to strike the best balance between performance and quality for the mask type you need. Those controls work in close partnership with whatever strokes you draw to pull out a mask. A bank of Mask Finesse controls then lets you work the resulting mask, reshaping and softening it to better fit whatever adjustment you are attempting. Each of these controls was covered earlier in this section.

### Managing Strokes in the Stroke List
