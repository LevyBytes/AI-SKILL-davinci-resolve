# Ai Tools (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### AI Tools

### AI IntelliSearch

DaVinci Resolve 21 brings a capable new media organization tool named IntelliSearch. Leaning on AI technology, IntelliSearch delivers a thorough, near-instant media search for people and objects. The payoff in finding precisely the media you’re after, faster, is genuine and immediate. For all those moments when you wondered “where was that clip of …?” you can now simply ask DaVinci Resolve and it will track it down for you.

### Setting up IntelliSearch

Being an AI-driven operation, IntelliSearch needs an AI model downloaded from the Extras Download Manager. With that installed, you then have to analyze the media in your media pool before you can use IntelliSearch from the search bar in the Media Pool.

### Downloading the IntelliSearch Models

The IntelliSearch models can be grabbed from DaVinci Resolve > Extras Download Manager. Two models exist, one for the Faster Mode and one for the Better Mode. You’re free to grab one or both, but your available modes will be capped by whichever packages you’ve installed.

### IntelliSearch AI model packages for download

### Selecting the IntelliSearch Mode

To start, you’ll have to settle on whether you want IntelliSearch running in Faster or Better mode. What you’re trading off is processing time against the size of the model download. Once analysis wraps up, both models run equally quickly. Better can take a good deal longer to analyze your clips, but it returns more accurate results. You might begin by running a Faster analysis, then come back for a Better mode pass once your workstation is sitting more idle. The pick between Faster and Better lives in the Media Pool three-dot option menu, under IntelliSearch Mode.

### Choose Faster or Better mode for IntelliSearch

### Analyzing Media in IntelliSearch

With your model chosen, the IntelliSearch analysis still has to be run on your Media Pool clips, and that happens from the AI Clip Analysis tool. From this single spot you can selectively turn the various AI analysis models loose on your Media Pool clips for the whole spread of AI-driven features in DaVinci Resolve. By default the tool works through every clip in the Media Pool, yet the drop-down menu off to the right lets you confine it to only the selected clips. The AI Clip Analysis Icon in the Media Pool To set the IntelliSearch Analysis going, check that the toggle switch next to Analyze for IntelliSearch is on. An optional checkbox named Identify Faces is also there; switch it on and IntelliSearch can pick out individual humans. From there you can feed their names in as search criteria within the Manage Faces window of the IntelliSearch interface.

(Left) Confirm the toggle beside Analyze for IntelliSearch is switched on, (Right) The AI Clip Analysis progress bar Then simply hit the Analyze button and let your computer work through the analysis. A progress window pops up to give you a rough idea of when the process will wrap up. Once done, clips that got analyzed will carry the AI Analysis icon in their thumbnail, so at a glance you can tell which clips are already processed.

This icon appears after a clip has been analyzed for IntelliSearch

### Using IntelliSearch

You reach IntelliSearch just by clicking the search icon (magnifying glass) in the Media Pool. Doing so opens a search bar plus the toolset around it.

### The IntelliSearch toolbar

Search Parameters: Choose which flavor of search analysis to apply to your search terms. Search All: Hands back results drawn from every kind of AI analysis plus any metadata you entered. Search Visual Only: Hands back results drawn solely from the image analysis. This Visual search lets you hunt for objects and other things present in the scene. Search Transcript Only: Hands back results drawn solely from the audio transcript. This Transcription search confines the hunt to transcribed audio, handy when you’re after exact phrases. Metadata Search: Hands back results drawn from any, or all, of the metadata fields. This Metadata search lets you filter on keywords and other metadata (custom metadata included) along with clip properties. The mode also gives you a dropdown menu to scan every field, or narrow it to file name, timecode, and other metadata fields. Search Field: Here you type whatever you’re after, and it can be just about anything, an object, a person, a color, a camera number, even a line of dialog. Add as SmartBin: Hitting this icon opens the Create Smart Bin tool with the parameters you picked already loaded into the Smart Bin criteria. That lets you spin up a lasting Smart Bin holding your search results. Show Face Gallery: Brings up a thumbnail view of every human face that got detected. Click a thumbnail to see every shot featuring that human, or narrow a search result down to that human. Manage Faces: Opens the Manage Faces tool, which lets you label and curate the various faces detected. Search In: Lets you decide where the hunt runs, All Bins: Combs through every bin in the project. Selected Bins: Combs only through bins you’ve selected. Display: Decide how results show up (for Search All, Visual only, and Transcript only). Full Clips: Hands back the whole clip as a match, a yellow line flagging where the search term applies. Hover the thumbnail, then Press “X” to set an in-out range off that yellow line. Segments: Hands back only the matching stretch where the search term applies, in effect turning it into a subclip.

### Face Gallery

Click the Show Face Gallery icon over in the IntelliSearch bar and a thumbnail view of every human face spotted in your clips opens. Click a face and the search results narrow to just that human. As an example, you can click a face labeled “Chloe,” shown as a face thumbnail, then type “red dress” into the search bar. The search results then come back showing only images of Chloe in a red dress and none of the other actresses. By default the Face Gallery, with the woman’s face picked, shows only clips she appears in. Should you want to pin a name onto the face, head over to the Manage Faces tool. There you can label the faces by clicking beneath the face thumbnail and typing the name into the field. That name now becomes metadata attached to that face under the People field.

The Manage Faces tool; typing a name beneath the thumbnail pins it onto a face.

If Face Detection got something wrong, you can also patch that up in the Manage Faces tool. An automated process runs when you press the Improve Faces Grouping Result button, which will ask you to confirm who it reckons that person is. You can likewise assign a face by hand simply by right-clicking the thumbnail, picking “Not XXX,” and reassigning it to a different face from the dropdown menu.

The Improve Faces Grouping Result tool offers an automated yes / no interface for confirming faces.

Right-clicking on a thumbnail lets you reassign the face manually.

### AI Speech Generator

Speech Generator turns written text into high-quality spoken-word output, so you can build your own natural-sounding VO or narration for a project, drawing on a range of voices and performances you tailor to the edit. Timeline > AI Tools > Speech Generator Downloading the Speech Generator Model Since it’s an AI-driven tool, the Speech Generator Model has to be downloaded ahead of use. You can grab the Speech Generator model from DaVinci Resolve > Extras Download Manager.

### Using AI Speech Generator

Fire up the AI Speech Generator by heading to Timeline > AI Tools > Speech Generator. Next, type the text you’d like generated into the Text Input field. Speech Generator works best with shorter sentences or paragraphs. Feed it text that runs too long and the generated voice can wander into odd territory after a while. So keep it brief, or where you’ve got a big chunk of text, split it into smaller pieces. Then settle on the Voice Model you want reading your text. Four built-in voices are licensed for use, or you can craft your own custom voice as described below. You can shape the voice by tweaking the parameters in the settings section. Lastly you can name the generated audio clip’s file and decide which audio track the clip drops into. Press the Generate button and the Speech Generator processes and builds a new audio clip from your input, dropping it into your Media Pool.

### The Speech Generator tool

- Speech Input: This section feeds in the text and settles which voice will read it. Text Input: Enter, in this spot, the words you’d like the Speech Generator to voice. Briefer sentences and paragraphs fare better. Punctuation does shape the timing of the reading. Periods (full stops) make longer pauses, commas shorter ones. A carriage return may stretch a pause that follows a period. Voice Model: Pick a voice model to read your text from the dropdown list. Choosing Custom opens a file requester to load an audio file holding the voice you’d like to use (see Creating a Custom Voice below).
- Settings: These settings govern the voice’s modulation and performance. Speed: Tunes how fast the reading goes. Variation: Governs how much the reading’s prosody (the rhythm and intonation of speech) and emotion vary, with 0 staying closest to the prosody of the reference voice source.

Pitch: Governs how high or low the voice sits. Positive values push it higher, negative ones lower. Generation ID: Picture this number as a performance or take. Each number stands for a different reading carrying its own prosody. Choosing the very same number hands you the very same performance, so it comes in handy when you want to try other variations yet hold onto the same prosody, emotional emphasis included. Randomize: Tick this box to draw a random number for the Generation ID.

- File Name: The label given to the new Speech Generator audio file. A default label is provided, with a numeric suffix tacked on automatically. In its place you can type your own label for the front of the string. Speech Generator audio files land in the DaVinci Resolve Media location you’ve designated, filed under their project name.
- Insert into Timeline: Ticking this box drops the reading in at the playhead spot on your timeline automatically.
- Audio Track: Pick which audio track on your timeline the reading lands on.

### Creating a Custom Voice for the Speech Generator

Crafting a custom voice for the Speech Generator is easy. All it takes is an audio file of the person speaking for roughly twenty seconds, captured as a clean, high-fidelity signal. After that, just bring the file into the Speech Generator via the Custom setting in the Voice Model dropdown menu. Pointers for capturing the best voice sample:

- A 10-20 second recording is all it takes. Indeed, anything longer gets trimmed back to its first 20 seconds for Speech Generator analysis.
- See to it that the voice recording stays clean, carrying good levels and little noise.
- Aim to keep your pacing steady, with no long gaps and no swings in volume or emotion if an

even result is what you’re after.

- Stuck on what to record? Give the “Harvard Sentences” a read aloud for twenty

seconds or thereabouts. They’re built to be phonetically balanced for the frequency of the English language.

- Experiment to see what works.

IMPORTANT: Be sure you’ve secured permission before using a real person’s voice, and that the creative voice talent is being paid fairly!

### Speech Generator vs. Voice Convert

Though their overall effect is alike, the input powering the two AI speech tools differs greatly. Speech Generator spins up a fresh audio file and performance out of written text, whereas Voice Convert takes an existing audio file and aims to match the tonality and performance of that exact clip, only with a different voice. On top of that, Speech Generator’s voices can be built from nothing more than a short snippet of audio, so it’s quick to deploy, while Voice Convert needs a longer source file and analysis time to build a voice model.

### AI CineFocus

CineFocus lets you build your own custom virtual lens that mimics realistic defocus and bokeh effects. It makes phone camera footage look as though it were shot on a real cinematic lens, or it can hand you added post-production control over professionally captured footage from any camera you like. The complete lens-build toolset teams up with an AI-generated Depth Map to construct a working depth model out of a 2D image, then wraps it in an easy-to-use graphical interface on the viewer. Switch on the Open FX overlay in the viewer and a split-prism icon becomes your pointer. As long as your shot came in entirely crisp, say off a phone camera, a single click on a region in the viewer “focuses” the lens onto that subject, while the remaining CineFocus parameters dictate what gets thrown out of focus, where, and in what manner.

The original phone footage, with everything in sharp detail.

The same image, with the focal point changed to the wall.

The same image, this time with the focal point moved onto the temple The effect runs left to right through the four mode tabs along the top of the inspector.

### Depth Mode

Press this button to bring up the depth map view and switch on the Depth Map toolset. Brighter objects sit “closer” to the camera, grey areas land in the mid-field, and darker areas fall into the distance. This view reveals what the AI judges to be nearer or farther from the camera, and it can be reshaped with the Depth Map controls below.

The CineFocus Depth Map view. Brighter areas are “closer” in depth.

### Focus Mode

Press this button to bring up the focus mode view and switch on the focus controls. The colored areas sit in focus, whereas grayer areas get defocused. While the OpenFX overlay is on, a click focuses an area in the viewer, and you can also click-drag the split prism icon to mark out a range of focus. From there the CineFocus controls act on the defocused (gray) parts of the image.

The CineFocus Focus view; the greyed-out areas fall out of focus. The split prism icon lets you click areas in the viewer to bring them into focus.

### Aperture Mode

Press this button to bring up Aperture mode. This view depicts the inner physics of the virtual CineFocus lens. It lets you visually sculpt your lens properties as you move the sliders. Along the diagram’s upper edge it traces the light path fanning out from the foreground that sits “in front” of the focal point (over on the left), passing through the focal point (that narrow middle), and on to the background “behind” the focal point (over on the right). Below the light path sit Bokeh “slices” drawn from the range above that let you see the Bokeh’s shape and size at a fixed distance.

The CineFocus Aperture view. Showing the virtual lens characteristics.

### Result

Press this button to view the CineFocus tool’s final outcome and tweak any parameter in the effect further.

### Focus

With this toolset you reshape the virtual lens’s focus parameters. Reaching for the Focus mode view above can show you these tools’ results in finer detail.

- Bokeh Quality: Enhanced scales quality off the source resolution, yielding finer detail though it can drag at a high aperture size. Better turns out softer bokeh while running more efficiently. “Faster” ramps up the optimizations alongside frame resolution.
- Aperture Size: Move this slider to alter the virtual aperture. Higher values pile more blur onto the image’s out-of-focus areas.
- Focus Distance: Set this to fix the virtual lens’s focal point, working off the data from the depth map. This virtual lens can’t focus in units of meters or feet; instead it’s a percentage value keyed to the Depth Map. Keyframing and animating this value lets you “pull focus” between one distance and the next.
- Depth of Field: Depth of Field (”DoF“ in photography) gauges the range of depths counted as in-focus. Within CineFocus this can be stretched artificially to hold a subject perfectly in focus without your having to dial down the strength of the near/far defocus”.
- Track Focus to Point: Tick this box so focus trails a point you set in the FX Overlay over in the viewer. The FX Tracker can then take that point and track focus across the whole clip.
- No Foreground Blur: Tick this box to strip the blur off the foreground, keeping it sharp. That makes it simpler to be sure a foreground subject stays in focus when that’s the aim, and the option can also lift performance.
- Focus Peaking: Tick this box to switch on focus peaking lines that flag the parts of the frame that are in focus. This echoes the same function real cameras carry.
- Boost Highlights: Raise the brightness of the highlights. It steers the balance of dark and bright regions where they’re blurred together. This can help brighten bokeh set against dark backgrounds, and it can broadly tune the result depending on your color management

### Depth Map

With this toolset you tweak the Depth Map, surfacing a simulated depth inside a 2D image. Reaching for the Depth mode view above can show you these tools’ results in finer detail.

- Source: Pick Internal to build a Depth Map within the CineFocus tool, or From Alpha Input if you’ve made a Depth Map in another node.
- Quality: Decide whether to favor speed (Faster) or quality (Better).
- Invert: Tick this box to flip the Depth Map, swapping what counts as near versus far in

the image.

- Adjust Map Levels: Tick this box to fine-tune the Depth Map and switch on the toolset below.

Far Limit: Tunes the Depth Map’s black levels, setting the cap on how “far away” the map reaches. Near Limit: Tunes the Depth Map’s white levels, setting the cap on how “close up” the map reaches. Gamma: Tunes the Depth Map’s gamma curve, letting you decide the relative “distances” between near and far objects.

- Post Processing: Tick this box to make tweaks to the black-and-white Depth Map and switch on the toolset below. Post Filter: Drag this slider to ease the Depth Map smooth following the contours of the image. Contract / Expand: Drag this slider to pull in or push out the Depth Map’s white foreground areas. Blur: Drag this slider to soften the Depth Map, a help where it carries jagged edges in need of smoothing, though it can throw off artifacts at the borders of image objects. Reach for this option only when repairing a troublesome depth map Separate Layers: Drag this slider to crisp up the depth edges wherever one object stands in front of another. This can help tease distances apart on depth maps that aren’t quite sharp. With an external Depth Map in play, be sure this stays at 0.0.

### Lens Properties

With this toolset you nudge the virtual lens toward being less than perfect. That yields a more realistic result and makes matching the traits of a real lens easier.

- Chromatic Aberration: Tick this box to mimic Chromatic Aberration, the fact that different frequencies of light come to focus at different depths. Strength: Tunes how strong the color separation is. Phase: Tunes the relative bending of the various frequencies, hinging on the lens optics.
- Spherical Aberration: Tick this box to mimic Spherical Aberration, the fact that large apertures can spread the focal point across a range of differing depths. Lens Model: Pick the lens construction type to mimic. Strength: Tunes the light dispersion.

### Aperture

With this toolset you tune the virtual lens’s Aperture traits. Reaching for the Aperture mode view above can show you these tools’ results in finer detail

- Shaped Bokeh: Tick this box to tune the virtual lens’s Bokeh and unlock the toolset below. Leaving this box unticked yields perfectly circular Bokeh. Number of Blades: Move the slider to set how many blades the virtual lens’s aperture has. Each blade reshapes the Bokeh accordingly. Rotation: Move it to spin the aperture shape left or right. Curvature: Tunes the curve of the aperture blades. Pinwheel: Tunes how much of the blade tips show. The Pinwheel name points to a ratchet-style shape inside the bokeh (those out-of-focus highlights) that some lenses show at wide-aperture, looking like a pinwheel fan.
- Anamorphic Lens: Tick this box to give the Bokeh an anamorphic shape. Anamorphism: Move this slider to set how much anamorphic stretch is applied.

### Lens Distortion

With this toolset you tune the virtual lens’s distortion traits. This recreates the fact that lenses build Bokeh at differing sizes depending on its distance from the lens center.

- Curved Lens: Tick this box to lay artificial curvature onto the lens and switch on the toolset below. Curvature: Tune the strength of the distortion around the frame’s edges. Lateral Aberration: Tunes the color distortions within the blurring at the frame’s edges. Phase: Tunes the relative spread of the various colors, hinging on the lens optics.

### Foreground Edge Overlap

With this toolset you set how the foreground edge overlap blends into the rest of the image. Where the foreground doesn’t overlap, these tools do nothing. In a real optical system, objects sitting close to the lens get “blurred-out” and turn transparent. As an example, hold the tip of a pen pointing up close to your eye and you can see straight through it. That physics doesn’t carry over to 2D video, so these tools offer a workaround that fakes the phenomenon.

- Overlap Preview: Tick this box to spot where the foreground edge overlaps the rest of the image.
- Overlap Boost: Move this slider to make the overlapping foreground denser so it better hides the transition edge. You can only reach this tool when Automatic Edge Handling is switched off.
- Automatic Edge Handling: Tick this box to build clean defocused overlaps on its own, at the price of some background detail in the overlapping regions. Using this tool switches off Overlap Boost.

### Remove and Replace Grain

In real footage, film grain and video noise stay independent of depth of field, scattered evenly throughout the frame. As the CineFocus tool blurs the background, the grain across those regions blurs out too, yet partially-blurred grain lingers through the slightly-blurred regions (hinging on the blur and the grain), which becomes awkward to handle afterward. With this toolset you can first strip grain out of the image to defocus the background more accurately, then drop it back in once the defocus is done, for the look of an image that had defocus by depth before it was ever captured to film

- Remove Grain: Ticking this box switches on the Remove and Replace toolset.
- Grain Detection: Pick the method that studies and strips the grain. Enhanced Spatial, or

AI Ultra Noise Reduction.

- Estimate Best Thresholds: With AI Ultra Noise Reduction picked above, this button is yours to press

so the AI can work out the grain vs detail threshold.

- Split Luma Chroma Thresholds: Tick this box to set separate grain thresholds for Luma and

Chroma signals.

- Threshold: Move this slider to set the dividing line between what counts as grain and what counts as edge detail.
- Preview Grain: Tick this box to see a preview of just the grain in the viewer, making it easier

to gauge what the parameters in this toolset are doing.

- Replace Grain After Defocus: Tick this box to drop all the grain you just stripped back into the

defocused areas once processing is done.

- Grain Replacement: Lets you decide just how much of the grain gets added back.

### Additional Grain

With this toolset you lay a grain layer across the whole image.

- Add Grain: Tick this box to switch on this toolset.
- Strength: Move this slider to set how much grain gets added to the image.
- Size: Move this slider to set the size of the grain particles.
- Softness: Move this slider to set how blurry or crisp the grain particles are.
- Saturation: Move this slider to set how colorful the grain particles are.

### AI Face Age Transformer

The Face Age Transformer lets you artificially age or de-age your subject’s face. Being an AI tool, the Face Age Transformer will automatically add or take away wrinkles, skin tautness, and other aging-related traits on your subject, and keep them tracking consistently along with their head movements and position.

### The original footage

### The model aged by 30 years

### The model de-aged by 20 years
