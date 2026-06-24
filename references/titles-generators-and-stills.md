# Titles Generators And Stills (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Titles, Generators, and Stills

From the Edit page you can drop titles, effects generators, and stills onto your timelines. Customized titles, generators, and stills can also be stored back into the Media Pool so you can reuse them down the line.

### Adding Titles

The Toolbox holds an assortment of titles and generators handy for building leader when you output to tape, dropping in slates, building subtitles, and otherwise meeting whatever text needs your program throws up. To pick and preview titles before dropping them into the Timeline, confirm that "Hover Scrub Preview" is ticked in the Titles option menu, then just glide your pointer across any thumbnail in the Titles tab. Where a title is animated (Fusion titles, that is), sweeping the pointer over the thumbnail previews the animation. After you've settled on your title, you can drag it out of the Titles tab onto your Timeline in the Edit page, or in the Cut page onto either the upper or lower Timelines, or lean on the editing selection modes along the bottom of the tab.

Scrubbing over a Title Thumbnail previews the title in the Viewer. You can edit titles and generators much as you would any other clip. On top of that, when selected, both titles and generators surface the same Composite, Transform, and Cropping parameter groups that any other clip does; with those parameters you can composite titles and sweep them around to build assorted text effects. Ways to add and edit generators and titles:

- To drag and drop a generator directly into the Timeline: Drag and drop titles or generators straight into the Timeline and the resulting clip lands with a default duration of 5 seconds. That duration is adjustable in the Edit panel of the User Preferences.
- To edit a generator using the edit overlays of the Timeline Viewer: On the clip you mean to edit a generator into, click its destination control, then lay down Timeline In and Out points to fix how long the resulting edit runs, and drag the generator you mean to edit onto whichever edit overlay of the Timeline Viewer matches the kind of edit you're after.
- To reposition the text of a title in the Timeline Viewer: In the Timeline, pick the title generator you'd like to edit, then click its visible text within the Timeline Viewer so its bounding box gets selected; in that state you're free to reposition, scale, and rotate the text item. As you move text, it snaps to key spots in the frame such as the Viewer's vertical and horizontal center; hold the Option key to switch off snapping when you'd rather place the text freely.
- To edit the text of a title in the Timeline Viewer: In the Timeline, pick the title generator you'd like to edit, then double-click its visible text within the Timeline Viewer to drop in a text editing cursor. From there you can select, delete, or add any text you like by typing right in the Timeline Viewer.
- To edit the parameters of a generator or title: With the Inspector open, pick whichever generator or title you'd like to edit so it loads into the Inspector.

### Using Safe Area Overlays

This drop-down menu lays plenty of handy framing guides over the Viewer so you can see which part of the image stays in and which part gets cropped away should you alter the Timeline's aspect ratio. You switch the framing guides on and off via the Safe Area Framing Guide icon in the Viewer, and you pick the precise guides from the drop-down menu. Social Media: 1:1, 4:5, 9:16, 1.91:1, 16:9. Broadcast and Film: Default (your current timeline aspect ratio), 1.33, 1.66, 1.77, 1.85, 2.35. Safe Area Guides: These choices lay extra guide lines over the Viewer to keep your composition from getting clipped at the far edges of a physical cathode ray tube. Although it feels a bit dated now that flat screen digital televisions rule, plenty of legacy programs still honor these guidelines. Safe Areas can still earn their keep as guides for making sure the spread of mobile devices and social media sites around today don't accidentally crop your image.

- Action: Hold all movement and important action inside this box.
- Title: Hold all on screen text inside this box.
- Center: Marks the precise middle of the image.

The Safe Area Framing Guide icon (circled), plus the safe area overlays and the framing options you can pick from

### Custom Action and Title Safe Areas

The Editing panel of the User Preferences now carries a "Use custom safe area overlays" checkbox; switch it on and Action Area and Title Area fields appear, letting you dial a custom percentage into each. By default these sit at 93% for Action Area and 90% for Title Area.

### Toggle Extents for Selected Safe Area Overlays

Beyond the Action, Title, and Center overlays, you can also flip the Extents Safe Area overlay on or off. That feature lives at View > Safe Area > Extents.

### Types of Title Generators

Once opened into the Inspector, a title exposes a batch of text parameters letting you style what sits in that clip's Text field right inside the Inspector. Every one of the titles handles rich text, so you can style words, lines, or paragraphs of text on their own using the parameters on hand, Color, Font, and Size among them. Other attributes—Alignment, Anchor, Position, and Shadow—act on the whole title. These titles are on offer: L Lower 3rd: (supports rich text) Drops two lines of text automatically into the bottom left corner of title safe, each carrying its own rich text plus Position/Zoom/Rotation controls for sizing and animating on their own. M Lower 3rd: (supports rich text) Drops two lines of text automatically into the bottom middle of title safe, each carrying its own rich text plus Position/Zoom/Rotation controls for sizing and animating on their own. R Lower 3rd: (supports rich text) Drops two lines of text automatically into the bottom right corner of title safe, each carrying its own rich text plus Position/Zoom/Rotation controls for sizing and animating on their own. Scroll: (supports rich text) Automates a scrolling title run climbing from the bottom of the screen to the top. How long the generator clip lasts in the Timeline sets how fast the scroll moves. Shares the Simple title's parameters. Text: (supports rich text) Good for building titles made of a word, a line, or a paragraph of text. One body of text draws on a single set of rich text controls that let you style chosen portions of the title text differently. Text+: (does not support rich text) A sophisticated title generator drawing on the Fusion page's title generation tools. Compared with the simple title generator above, this one packs far broader control over styling, rendering, and animating, though all title text rides on a single style. Fusion Titles: A range of ready-made title templates put together in Fusion. DaVinci Resolve ships with a library of pre-built Fusion titles, yet you can roll your own to show up in this category of the Effects browser too.

### DaVinci Resolve Title Generators

The original title generators bundled with DaVinci Resolve all carry similar controls, and every one of them can handle rich text styling.

### Editing Titles Within the Timeline Viewer

After you drop a title generator onto the Timeline, the original title generators bundled with DaVinci Resolve give you onscreen controls for editing text and for transforming and placing blocks of text right inside the Timeline Viewer.

### Positioning and Transforming Text

As long as the Timeline playhead sits over a text generator stacked atop one or more background clips, clicking the text in the Timeline Viewer brings up onscreen transform controls matching the Position, Zoom, and Rotation parameters in the Inspector.

Drag the text to position it in the Viewer As you drag text to a new spot, snapping kicks in at the frame's X and Y center, as well as around the frame's outer third. Holding the Shift key while you drag a text object pins movement to just the X or Y axes.

### Editing Text

Double-clicking text in the Timeline Viewer flips that text into an editable state, where you can drop in a text cursor or select characters to edit the text the way you would in any text editor.

Double-click on the text to edit it in the Viewer

### Title Generator Panels

Within the Video Inspector, a text generator's parameters fall across a pair of panels: the Title panel alongside the Settings panel.

- The Title panel holds every text editing, styling, and sizing control used to shape the contents and look of a title in your project, the Rich Text, Drop Shadow, Stroke, and Background parameters included.
- The Settings panel holds the same Composite, Transform, and Cropping parameters that every other clip in DaVinci Resolve carries. Those parameters exist for compositing and animating a title.

### Shared Title Generator Parameters

Apart from the Text+ generator, every other title generator in DaVinci Resolve can do rich text styling. What that means is you can grab any stretch of a generator's text and style it differently. You might, for instance, run three lines of text inside one generator and style each line on its own to land a particular design.

A lone generator holding three lines of text, each styled its own way Every title generator leans on the same parameters within the Inspector's Video Title panel for editing and styling text:

- Rich Text: A control group made up of a text entry field plus parameters for styling different stretches of the text on their own. Text: A text entry field where you edit the title being generated. With no characters selected, the styling controls hit the whole block of text. Select a particular run of characters, though, and the styling controls touch only that selection. Text in this field is also editable directly in the Timeline Viewer. Font family: A pop-up where you select whichever font family your workstation has installed. Font face: A pop-up where you select which face within the currently chosen font family to apply. Color: Summons the standard color picker so you can settle on a font color. Size: Slider that dials in the text size. Tracking: Slider governing how much space sits between characters. Line spacing: Slider governing how much space falls between the selected line of text and the one directly under it.

Font style: Buttons that lay styling onto the text—underline, plus overhead line, strikethrough, then superscript along with subscript. Font case: A pop-up that pushes the text selection toward any one of these: Mixed Case (the default), or All Caps, or All Lowercase, or Small Caps, or else Title Caps. Alignment: Buttons fixing the alignment method, where your choices run left, then centered, then right, then justified. Anchor: Buttons fixing how text anchors against the current position—on the horizontal axis between top, centered, bottom, and on the vertical axis between right, centered, left. Position: A pair of X and Y parameters pinning the bottom left-hand corner (under the default Anchor settings) of the rich text block being generated. It mirrors what happens as you drag a selected text box around inside the Timeline Viewer. Zoom: A pair of X and Y parameters pinning the text's scale. There's a link button to hold the X and Y parameters locked together. It mirrors what happens as you resize a selected text box inside the Timeline Viewer, be it from the corners (for proportional resizing) or by way of the top, bottom, and sides (where you stretch or squeeze the text). Rotation Angle: A slider that spins the text's orientation. It mirrors what happens when you rotate a selected text box inside the Timeline Viewer by way of the rotation handle.

- Drop Shadow: A cluster of controls letting you lay a customizable drop shadow over every character of text being generated.

Color: Summons the standard color picker so you can settle on a drop shadow color. Offset: A pair of X and Y parameters pinning how far the drop shadow strays from where the original text sits. Blur: A slider that softens the drop shadow. Opacity: A slider that sets how see-through the drop shadow becomes.

- Stroke: Lets you wrap an outline around every character of text being generated. Color: Brings up the standard color picker for picking the stroke color. Size: A slider lets you pick the stroke thickness, in pixels.
- Background: This cluster of controls hands you an exceptionally flexible rectangle or rounded rectangle shape you can use to drop in a background, bar, outline, or other intersecting shape while designing a title.

Color: Summons the standard color picker so you can settle on the interior color of the background shape. Outline color: Summons the standard color picker so you can settle on the outline color of the background shape. Outline width: A slider where you dial in how thick, in pixels, the background shape outline runs. Width: A slider where you dial in how broad the background shape becomes. Height: A slider where you dial in how high the background shape rises. Corner radius: A slider where you dial in how rounded the rectangle edges turn out. Center: A pair of X and Y parameters handy for nudging the background shape away from the text being generated. Opacity: A slider where you dial in how see-through the background shape is.

### Title Generator Settings Parameters

Beyond that, the Video Inspector's Settings panel gives each generator its Composite, Transform, and Cropping parameters, which you use to composite, resize, and animate titles over other Timeline clips when you're chasing motion graphics effects. Those parameters match the ones available for every clip, covered later in this chapter.

### The Text+ Title Generator

A fresh kind of title generator, called Text+, lives within the Effects Library toolbox under the Titles category. This is the wildly full-featured 2D text generator out of Fusion, ready for editing and customizing right in the Edit page. It handles most of what the Text generator manages, rich text editing and on-screen controls in the Timeline Viewer included. It also brings far more styling and animation controls than the Text generator. TIP: As of this writing, the Text generator stays plenty useful for quickly knocking out text pages carrying multiple styles, whereas the Text+ generator shines at building text for animated motion graphics.

The new Text+ title generator, along with new Fusion titles below You work the Text+ generator the same way you work any generator in the Edit page. Just drop it onto a Timeline video track, select it, and head into the Inspector to edit and keyframe the many properties it carries so you can build whatever sort of title you're after. On top of its far larger pile of styling options, the fact that the Text+ generator grew out of a compositing tool means it brings many more panels' worth of keyframable parameters, advanced animation controls baked right in. Among them are keyframable Write On/Write Off controls; shape-driven layout and animation (the choices here being point, frame, circle, and path); transforms and animation at the character, word, and line level; shading of an advanced sort; plus interlacing support that's full.

A quartet of the Text+ title generator's panels, namely Text, Layout, Transform, and Shading

Better still, once the playhead rests on your new Text+ "Fusion Title," opening the Fusion page lets you get at its parameters from there too, should you care to start expanding this one generator into a multi-layered motion graphics extravaganza.

Open the Text+ node on the Fusion page and it shows up there as a genuine Fusion page operation NOTE: Should you receive a project carrying a Text+ title while a specific font used in that title is missing from your local machine, an overlay surfaces on the Viewer letting you know.

### Text+ Viewer Controls

You can carry out assorted editing actions on Text+ straight in the viewer overlay—editing text, showing a cursor, and selecting text among them. That reach extends to the viewer inside the Edit page once the Fusion overlay is switched on.

The Text+ Viewer controls switch on when you pick Fusion Overlay (circled) from the Timeline Viewer Overlay menu.

- To enable Text+ Viewer controls: Pick Fusion Overlay from the Timeline Viewer Overlay drop-down menu. From there your mouse can work the text in the Viewer to select and edit it, plus shift it around within the frame.

For fuller detail on the wide reach of the Text+ generator, see Chapter 104, "Generator Nodes."

### Fusion Titles and Fusion Templates

The many additional Fusion titles you'll find across the Effects Library are custom-built text compositions, animation baked in, that surface custom controls in the Inspector.

A Fusion title that builds an animated lower third, its controls sitting open in the Inspector In truth, these text generators amount to Fusion templates—Fusion compositions turned into macros that ship alongside DaVinci Resolve for use inside the Edit page like any other generator. All sorts of Fusion title compositions can be crafted on the Fusion page and kept for Edit-page use: build a macro and place it inside the directory at /Library/Application Support/ Blackmagic Design/DaVinci Resolve/Fusion/Templates/Edit/Titles, though that's a story for another time. Text+ generators carry one further perk: they can be graded like any other clip, with no need to build a compound clip first.

### MultiText Titles

Built atop Text+, the MultiText tool in the Titles category hands you more room to add and format several text layers, all inside the one tool. It brings in a Text List along with a mild reshuffle of controls, putting functionality first based on what editors need.

The MultiText tool in the Titles section lets you build several text layers and styles and composite them all inside a single interface.

### Text

The Text List acts as a master panel, laying out every text layer you've made. The list and its controls stay on hand across the Inspector tabs, giving you quick reach to adjust both the text and its properties whenever you like. Right under the Text List, the Add Text buttons present three commonly used layout types: Point, Text Box, and Circle, making it painless to drop in your preferred input style.

- Point: The text springs from a single point on the screen, with no horizontal or vertical limits.
- Text Box: The text is held in horizontally and vertically by a bounding box. With Text Box

selected, the Wrap to Text Box and Clip to Text Box checkboxes turn up under the Layout tab. With Wrap to Text Box on, your text automatically rolls onto the next line once it reaches the text box edge. With Clip to Text Box on, any text spilling past the text box's boundaries gets visually trimmed away, heading off overflow while leaving the surplus content intact.

- Circle: The text is laid along an arc you define.
- CSV: Pulls a Comma Separated Value (.csv) spreadsheet into MultiText and formats it automatically as columned aligned text. Once it's in MultiText, you can rework the titles however suits you.

### A simple spreadsheet saved in .csv format

When that .csv file lands in MultiText, every column arrives as its own separate text list item The Text tab additionally bundles an array of animation and text formatting tools much like those in a word processor. Layout This set of parameters decides where the text lands. Shading This set of parameters decides the text's attributes—drop shadows and outlines among them. Page This set of parameters lets you set a custom-colored background behind the text layers. Image This set of parameters lets you manage the overall image: aspect ratio, along with color and gamma spaces. Settings This set of parameters supplies the standard Settings controls for Fusion Generator Nodes. To dig further into the assorted options, turn to Text+ Tool in MultiText see Chapter 104, "Generator Nodes."

### Saving Titles in the Media Pool for Future Use

When you've built a title in a style you'd like to reuse later—say a distinctively formatted lower third meant to seed each lower-third across your program—dragging any title out of the Timeline into the Media Pool stores it there as its own clip. Title clips in the Media Pool show a thumbnail previewing the text they hold. If you've keyframed any animated text or video adjustments, those keyframes ride along with this clip too. Once stored in the Media Pool, text generators open in the Source Viewer and edit just like any other clip.

A text generator saved as a clip in the Media Pool

### Using Generators

Generators—Solid Color aside—offer no editable parameters beyond the Composite, Transform, Cropping, and Dynamic Zoom parameters standard on every clip. On top of that, generators carry a Display Name field in the Inspector letting you hand a given clip a custom name that surfaces in the Timeline. Gliding your pointer across any thumbnail in the Generators tab previews the various video generators bundled with DaVinci Resolve. To bring a generator into your timeline, simply seize the thumbnail of the one you want and drop it onto your Timeline on the Edit page, or onto either the upper or lower Timelines on the Cut page. These generators are on offer:

- 10 Step: A grayscale ramp broken into 10 steps running black to white.
- 100mV Steps: A grayscale ramp broken into segments of exactly 100mV apiece.
- BT.2111 Color Bar HLG Narrow: Reach for these bars when your HDR timeline runs a Hybrid Log Gamma

curve (HLG). This one turns up most in broadcast for its easy backward compatibility with SDR televisions.

- BT.2111 Color Bar PQ Full: Though PQ Full belongs to the Rec. 2100 (BT.2100) specification, it isn't widely used right now. Pick this setting only when you know you need it.
- BT.2111 Color Bar PQ Narrow: Reach for these bars when your HDR timeline runs a format carrying a PQ gamma curve (DolbyVision or HDR10, that is). This one turns up most for video streaming services and Blu-ray discs.
- EBU Color Bar: For PAL-using countries, a set of color bars at a 1.77:1 aspect ratio.
- Four Color Gradient: A gradient blending four different colors at each corner of the frame. You

can shift the Center X and Center Y parameters to move the point where all four colors blend together, and you can swap the four colors showing at each corner via the matching color parameters.

- Grey Scale: A plain grayscale ramp running black to white.
- SMPTE Color Bar: For NTSC-using countries, a refreshed set of color bars at a 1.77:1 aspect ratio.
- Solid Color: A plain fullscreen color generator. A Color parameter lets you pick what color this generator puts out.
- Window: A plain white-on-black shape generator, defaulting to a white rectangle over a black background.
- YCbCr Ramp: A gradient built to test the Y'CbCr signal.

### ITU-R BT.2111-1 Color Bar Generators

For HDR video, DaVinci Resolve now bundles a Color Bar Generator following the ITU-R BT.2111-1 specification. Reach for these color bars whenever you're calibrating, analyzing, or mastering a Rec. 2100 (BT.2100) HDR signal. Saturation on these new color bars is pinned at 100% up top, dropping to 75% through the middle section. Down in the lower corners they also carry Rec. 709 (BT.709) color bars, keeping things compatible with HD SDR signals. Levels people reference most often are flagged on the image below. You'll find the full color bar specification over on the ITU's web site: https://www.itu.int/rec/R-REC-BT.2111/en.

The BT.2111-1 color bars together with a handful of the levels referenced most

The BT.2111-1 color bars shown on the Vectorscope, landing on their targets at 100% levels around the outside and 75% levels toward the middle, the Rec. 709 bars meanwhile sitting in the interior

### Fusion Generators
