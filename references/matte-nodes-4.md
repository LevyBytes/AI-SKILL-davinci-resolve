# Matte Nodes (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Running a modest count of passes (four, say) yields a high-quality blur, frequently quicker than the Gaussian filter and free of ringing.

- Gaussian: Gaussian lays down a smooth, symmetrical blur filter by way of a refined constant-time Gaussian approximation algorithm. Under extreme conditions that algorithm can show ringing, which is covered below. This serves as the default filter method.

Blur Softens the matte's edge with an ordinary, constant-speed Gaussian blur. Set it to zero and you get a crisp, cutout-style hard edge. Raise the value and progressively more blur gets applied to the matte.

Clipping Mode This setting governs the treatment of edges while domain of definition rendering takes place. It matters enormously when you blur the matte, since that can demand samples drawn from parts of the image beyond the present domain.

- Frame: Frame is the default, automatically configuring the node’s domain of definition to span the image's full frame and thereby disregarding the current domain of definition. When the upstream DoD comes in smaller than the frame, the leftover frame area counts as black/transparent.
- Domain: Switching this to Domain honors the upstream domain of definition as the node’s effect is applied. With a large filter in play, that can produce undesirable clipping.
- None: Picking None skips source image clipping entirely. Consequently, whatever data the node’s effect needs that ordinarily lies beyond the upstream DoD is taken as black/transparent.

Contract/Expand Shrinks or grows the matte much like an Erode Dilate node does. Pulling the matte in exposes more of the foreground input, whereas pushing it out exposes more of the background input. A value over 0.0 expands the matte; a value under 0.0 contracts it. Gamma Lifts or drops the matte's values throughout the semitransparent regions. Larger values render the gray areas more opaque, smaller values render them more transparent, while fully black or white parts of the matte stay untouched. Threshold Anything beneath the lower threshold turns black or transparent in the matte; anything above the upper threshold turns white or opaque. Everything in between holds onto its relative transparency. Restore Fringe Brings back the matte's edge surrounding the keyed subject. Keying frequently clips away the subject's edge wherever hair appears; Restore Fringe recovers that edge yet keeps the matte solid. Invert Matte Ticking this checkbox flips the image's alpha channel, so every transparent area turns opaque and every opaque area turns transparent. Solid Matte A solid matte is a mask node or image wired into the node's solid matte input. It feeds straight onto the image's alpha channel. Typically a solid matte holds out regions you want kept opaque, like someone with blue eyes shot against a blue screen. Turning on Invert flips the solid matte ahead of merging it with the source alpha. Garbage Matte A garbage matte is a mask node or image wired into the node's garbage matte input. It too feeds straight onto the image's alpha channel. Typically a garbage matte strips out unwanted items that resist keying, such as microphones and booms. It also fills in regions holding the keyed color that you nonetheless want to keep.

You can't blend garbage mattes of differing modes inside one tool. A Matte Control node frequently sits after a Keyer node to introduce a garbage matte whose effect opposes the matte fed to the keyer. Turning on Invert flips the garbage matte ahead of merging it with the source alpha. Post-Multiply Image Choosing this multiplies the image's color channels against the alpha channel it builds for the image. It's normally enabled and on by default. Clear this checkbox and the image stops counting as premultiplied for the sake of merging it with others. Reach for the Subtractive option of the Merge node rather than the Additive one. For fuller detail on these Merge node settings, turn to Chapter 95, "Composite Nodes," within the DaVinci Resolve Reference Manual, or else to Chapter 35 of the Fusion Reference Manual.

### The Matte Control Spill tab

### Spill Tab

Spill suppression in the Matte Control is managed by the Spill tab. Spill suppression is a flavor of color correction aimed at stripping the screen color out of the matte's fringe. Spill refers to the screen color passing through the alpha channel's semitransparent zones. With blue- or green-screen keying, this generally lets the background's color show up along the foreground subject's edges. Spill Color This menu picks the color that serves as the foundation for every spill suppression technique. Spill Suppression With this slider at 0, no spill suppression touches the image; raising it strengthens the spill method.

Spill Method This picks how aggressive the algorithm is that applies spill suppression to the image.

- None: Pick None whenever no spill suppression is needed.
- Rare: Strips away barely any of the spill color and is the gentlest of the methods.
- Medium: Performs best on green screens.
- Well Done: Performs best on blue screens.
- Burnt: Performs best on blue screen. Reserve this mode for especially difficult shots.

Fringe Gamma This control adjusts how bright the fringe or halo ringing the keyed image appears. Fringe Size This grows and shrinks the fringe or halo around the keyed image. Fringe Shape Fringe Shape nudges the fringe out toward the image's outer edge or draws it in toward the fringe's inner edge. A large Fringe Size value is when its effect reads most plainly. Cyan/Red, Magenta/Green, and Yellow/Blue Reach for these three controls to color correct the image's fringe. They help fix semitransparent pixels still carrying color from the original background so they match the new background.

### Common Controls

Settings Tab The Inspector's Settings tab is repeated across the other Matte nodes as well. The common controls it holds are laid out fully toward the end of this chapter within “The Common Controls” section.

### Primatte [Pri]

### The Primatte node

NOTE: Primatte is offered only within Fusion Studio.

### Primatte Node Introduction

Primatte is a sophisticated keying tool for Fusion Studio. Getting good mileage out of Primatte means grasping how it operates. By way of a set of selection buttons, Primatte sorts RGB pixels into one of four distinct zones.

Zone 1: The background image in full. Zone 2: The foreground image carrying spill suppression plus transparency. Zone 3: The foreground image carrying spill suppression alone. Zone 4: The foreground image in full. According to the variety of blue- or green-screen footage, you might discover the Delta Keyer or the Primatte keyer does a better job on a given keying task. Keying has no universal fix, and now and then pairing the two keyers turns out to be the strongest answer. NOTE: Licensing and distribution of Primatte are handled by IMAGICA Corp. of America, Los Angeles, CA, USA. The tool was created by IMAGICA Corp., Tokyo, Japan, which holds Primatte as a trademark.

### Inputs

Within the Node Editor the Primatte node carries six inputs. In contrast to every other Fusion tool, its principal orange input bears the name Foreground input, because it takes the green-screen or blue-screen image. On the Primatte node the green input acts as the background input; this optional input lets Primatte assemble the final merged composite. Foreground Input: The orange input takes a 2D image holding blue or green screen. Background Input: The green (optional) input takes a 2D image placed as the composite's background layer. With nothing connected, Primatte puts out the keyed foreground. Wiring an image into the background input switches on Primatte’s advanced edge blending options. Replacement Image: The magenta (optional) input takes a 2D image that feeds the color correction Primatte applies during spill suppression. Garbage Matte: A mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks goes into the gray garbage matte input. Wiring a mask here renders transparent any image areas falling inside the matte. That garbage matte feeds straight onto the image's alpha channel. Solid Matte: The white solid matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here renders fully opaque any image areas falling inside the matte. Effect Mask: The optional blue input anticipates a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here confines the pixels at which keying happens. An effects mask gets applied to the tool once the tool has finished processing. NOTE: Wiring the background input while leaving the replacement image input unconnected makes the background image double as the replacement image surf spill suppression.

### Basic Node Setup

It's rare for one Primatte keyer alone to nail flawless results, since the majority of green- or blue-screen shots carry issues the keyer wasn't built to tackle. Keyers commonly lean on garbage mattes or solid mattes drawn with a Polygon or B-Spline node. A shot might also call for more than a single keyer before results are perfect. In the example below, the Primatte node has its blue-screen content wired to the orange input. Departing from other Fusion nodes, the foreground attaches to the orange input. What emerges is an image carrying alpha, which you can then feed into the foreground of a Merge node.

A Primatte node paired with a polygon matte acting as its garbage matte, then routed into the foreground of a Merge Primatte Tab View Mode The View Mode menu sits at the top of the Inspector. Its default choice presents the finished Composite result; switching it lets you inspect assorted intermediate stages of the keying process.

### The Primatte tab View mode

- Black: Shows the foreground subject against a black or transparent background.
- Composite: The finished keyed image with spill suppression, laid over whatever image is wired

to the green Background Input on the node.

- Defocus Foreground: Shows what the Pre Matte key outputs.
- Processed Foreground: Shows the key's alpha prior to being merged with the solid and

garbage masks. While viewing the matte, configure the viewer to reveal the alpha channel.

- Hybrid Matte: Shows the matte produced once the Hybrid Rendering checkbox is turned on.

It's best examined as you tweak the Hybrid Blur and Hybrid Erode sliders.

- Lighting Foreground: Shows the foreground subject atop the optimized artificial backing screen

built by the Adjust Lighting mode.

- Lighting Background: Shows the optimized artificial backing screen produced by the Adjust Lighting

mode.

### The Primatte tab Inspector

### Primatte Tab

Primatte's central capabilities live within the Primatte tab. At its heart, the workflow comes down to choosing one of the operational mode buttons and then scrubbing across regions in the viewer. Lock Color Picking Switch this button on after you've wrapped up tuning your key, so you don't make stray changes in the viewer. Auto Compute The Auto Compute button is probably the first one you'll press as you begin keying your footage. Primatte automagically studies the original foreground image, works out the backing color, and assigns it as the central backing color. Following that, a further analysis using that data pins down the foreground areas. A Clean FG Noise operation runs against the freshly identified foreground areas, after which Primatte renders the composite. NOTE: Pressing Auto Compute can make the trio that follows it—Select Background Color, Clean Background Noise, and Clean Foreground Noise—unnecessary, greatly simplifying your keying job. Pressing Auto Compute detects the backing screen color on its own, removes it, and even clears out a measure of foreground and background noise. Should the results look good, skip straight to the Spill Removal tools. Should they fall short, carry on from here with the three buttons covered below. Select Background Color Pressing the Select Background Color button lets you choose the screen color by scrubbing in the viewer. It applies Primatte's classic approach: take the sampled backing screen color, cast a line the opposite way across the hue wheel, and fabricate artificial pixels that may stand in for the FG object. Then, drawing on those artificially made foreground pixels, it internally runs the Clean FG Noise operation and forms the shape of the middle and outer polyhedrons. With those generated polyhedrons it renders the composite. It won't engage the Adjust Lighting functionality on its own, since that has to be chosen in a separate step. Clean Background Noise Pressing this button helps clear any white patches within the dark screen region (“noise”), along with shades of the screen color the first sample didn't catch. After you press the button, drag the mouse pointer over areas in the viewer to sample the whitish noise regions.

Clean Foreground Noise When dark transparent patches sit amid the largely white opaque foreground object, press the Clean Foreground Noise button and scrub across the dark pixels in the foreground until that region turns as white as it can. Spill Sponge The Spill Sponge is the fastest route to clearing color spill off your subject. Press the Spill Sponge button, drag the mouse pointer over a screen color pixel, and the screen color vanishes from the chosen color region, swapped for a complementary color, a selected color, or a color drawn from a replacement image. You configure these choices in the Replace tab. On top of that, the tools beneath the Fine Tuning tab, or the Spill(+) and Split(-) features, let you fine-tune the spill. Matte Sponge Now and then during the Primatte operation a 100% opaque foreground region (pure white) drifts slightly transparent (gray). To tidy those transparent areas, press the Matte Sponge button and drag across the gray pixels; every bit of the spill-suppression data is left intact. Restore Detail Pressing Restore Detail and scrubbing across background regions in the viewer nudges fully transparent areas toward translucency. The operation helps recover lost hair details, faint wisps of smoke, and similar elements. Make Foreground Transparent With this button active, the opaque foreground color region you sample in the viewer turns a touch translucent. The operation suits the delicate tuning of foreground subjects that are otherwise 100 percent obscured by smoke or clouds. You may apply it just once to a particular color. For a more adaptable way to thin a color region and to gather several samples, turn to the Matte(-) tool. Spill(+) Pressing the Spill(+) button restores color spill to the sampled pixel color (and every color resembling it) by one Primatte increment. The tool can shift the sampled color nearer to its hue in the original foreground image, and it can cancel out a Spill(-) step. Spill(-) Pressing the Spill(-) button subtracts from the sampled pixel color (and every color resembling it) by one Primatte increment. If spill color lingers, another press of this operational mode tool strips away more of it. Keep pressing until every trace of color spill is gone from the sampled color region. Matte(+) Pressing the Matte(+) button renders the matte more opaque for the sampled pixel color (and every color resembling it) by one Primatte increment. When the matte stays too translucent or thin, a further press of this operational mode tool makes the sampled color region more opaque still. You can use it to thicken smoke or deepen a shadow so it matches shadows in the background imagery. It only alters the density of the color region on the original foreground image, and it can undo a Matte(-) step. Matte(-) Pressing the Matte(+) button renders the matte more translucent for the sampled pixel color (and every color resembling it) by one Primatte increment. When the matte stays too opaque, a further press of this operational mode tool makes the sampled color region more translucent still. You can use it to thin smoke or lighten a shadow so it matches shadows in the background imagery.

Detail(+) With this button active, foreground detail grows less visible for the sampled pixel color (and every color resembling it) by one Primatte increment. If detail is still excessive, another press of this operational mode tool erases more of it. You can use it to clear smoke or wisps of hair out of the composite. Sample where detail shows, and it fades. The purpose is to push color regions into the 100% background region, and it can cancel a Detail(-) step. Detail(-) With this button active, foreground detail grows more visible for the sampled pixel color (and every color resembling it) by one Primatte increment. If detail is still absent, another press of this operational mode tool brings detail out further. You can use it to recover lost smoke or wisps of hair. Sample right where the smoke or hair drops away and it comes back into view. Use it to reclaim color regions that had been pushed into the 100% background region. It may begin pulling in background noise when shooting conditions on the foreground image weren't ideal. Algorithms The Primatte keyer offers three keying algorithms:

- Primatte: The Primatte algorithm mode produces the finest results and backs both the Solid Color and the Complement Color spill suppression methods. It relies on three multifaceted polyhedrons (covered further on in this section) to carve up the 3D RGB colorspace. As the default algorithm mode, and being computationally heavy, it can be the slowest to render.
- Primatte RT: Primatte RT is the most basic algorithm and consequently the fastest. It leans on just one planar surface to carve up the 3D RGB colorspace (covered further on in this section), so it doesn't pull the foreground away from the backing screen as meticulously as the Primatte algorithm above. A further drawback of the Primatte RT algorithm is that it struggles with less saturated backing screen colors and offers no Complement Color spill suppression method.
- Primatte RT+: Primatte RT+ falls between the two preceding options. It employs a six planar surface color separation algorithm (covered further on in this section) and lands between the other two in both quality and performance. A further drawback of the Primatte RT+ algorithm is that it struggles with less saturated backing screen colors and offers no Complement Color spill suppression method.

Hybrid Rendering Once you've sampled the backing screen color and arrived at decent edges around the foreground object, a transparent patch occasionally shows up inside the foreground subject. It tends to happen when the foreground subject holds a color near the backing screen color. Clearing that transparency through the Clean FG Noise mode can leave the foreground subject's edge with a fringe close to the backing screen color, and shedding that fringe without giving up quality elsewhere on the image is quite hard. The Hybrid Render mode internally spins up two keying operations: Body and Edge. The tuned Edge operation secures the cleanest edge around the foreground subject with no fringe effect, while the Body operation tackles transparency within the foreground subject. The final matte comes from combining the two mattes, then blurring and eroding the foreground subject in the Body matte and joining it to the edge matte. To put Hybrid Rendering to work, first key the main foreground area through the Select Background Color mode (or any other Primatte backing screen detection method). Turn on the Hybrid Rendering checkbox. Finally, choose the Clean FG Noise button and scrub across the transparent area. The Hybrid Render mode carries out the “Body/Edge” operation, yielding a final composite with flawless edges around a solid foreground subject.

Hybrid Blur Softens the Body matte that gets built automatically whenever Hybrid Rendering is switched on. Hybrid Erode This slider dilates or erodes the Hybrid matte. To review the outcome, choose Hybrid matte in the View Mode menu. Adjust Lighting Ahead of running the Adjust Lighting operation, you have to establish the backing screen color with Auto Compute or Select Background Color. With one of those done, click the Adjust Lighting button. Primatte fabricates an artificial clean plate and uses it to render an evenly lit backing screen behind the foreground object. By default it ought to catch every area holding foreground pixels and supply a smooth backing screen for keying. Lighting Threshold If Adjust Lighting doesn't yield a smoother backing screen, move the Lighting Threshold slider while watching the Lighting Background setting in the View Mode menu, which displays the optimized artificial backing screen the Adjust Lighting mode creates. Crop This button exposes the Crop sliders for drawing a rectangular garbage matte with the Primatte node. Unlike Fusion’s Crop tool, it leaves the actual image size unchanged. Reset Returns all the Primatte key control data to a blue- or green-screen state. Soft Reset Returns only the Primatte parameters touched since the Select Background Color operation last finished.

### The Primatte Fine Tuning tab

### Fine Tuning Tab

The Fine Tuning tab lets you make precise tweaks to the spill suppression, the matte's density, and the semitransparent regions. Its sliders hand you a little more granularity than the Spill(+)(-), Matte(+)(-) and Detail(+)(-) buttons over in the Primatte tab.

### Selected Color
