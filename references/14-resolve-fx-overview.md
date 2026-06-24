# Resolve Fx, Resolve Fx Blur

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

## Overview

Covers: Resolve FX Overview; Resolve FX; Resolve FX Blur.

## Resolve FX Overview

### Resolve FX Overview

## Resolve FX

### Resolve FX

Here you'll find a thorough breakdown of every Resolve FX filter offered on the Cut, Edit, Fusion, and Color pages.

To learn how each filter is applied and tuned on a given page, consult the relevant chapter: the Cut page is covered in Chapter 31, “Video and Audio Effects in the Cut Page”; the Edit page in Chapter 47, “Editing, Adding, and Copying Effects and Filters”; the Fusion page in Chapter 84, “Using Open FX, Resolve FX, and Fuse Plugins”; and the Color page in Chapter 151, “Using Open FX and Resolve FX.”

### Catalogue of Resolve FX Filters

A collection of Resolve FX filters ships with DaVinci Resolve, and a good number of them are tuned for real time playback. You'll find them grouped in a dedicated category within the Effects Library on the Cut, Edit, and Fusion pages, as well as in the Open FX browser on the Color page. Functionally, these filters behave the same as any other Open FX plugin. Each Resolve FX is represented by an icon that depicts the specific filter. Hold the mouse pointer over an icon to preview that filter in the Viewer, and slide the pointer across the icon to scrub the preview across the duration of the clip.

### Icons showing categorized Resolve FX filters

Beyond the unique parameters that each filter contains, a Blend parameter is present on absolutely every Resolve FX filter, blending that filter's result with the unprocessed source image. You'll find each filter's Blend control located at the very bottom of its settings.

The Blend slider found in the parameters of every Resolve FX filter

### Effects Search

Hitting Shift-Space opens the Effects Search dialog on the Cut, Edit, Color and Fairlight pages, working the same way it has long worked on the Fusion Page. With a node already selected, choosing an effect from the search results applies it straight to that selected node.

Hitting Shift-Space summons the Effects Search Dialog. Here, entering “film” surfaces every effect that contains the word Film somewhere in its name.

### Show Legacy Resolve FX

As the years pass, certain Resolve FX get deprecated for one reason or another — maybe their capabilities were folded into a different effect, or maybe they were entirely rebuilt. Even so, if you're returning to a project that leaned heavily on one of those older effects, or you simply have a soft spot for them, they remain reachable. To reveal the Legacy Resolve FX:

- Go to the Effects tab, open the Effects (3-dot) option menu, and then choose

Show Legacy Resolve FX.

- Toggling this setting off once more hides those effects from the list again.

## Resolve FX Blur

### Resolve FX Blur

Compared with what the Blur palette gives you, the plugins gathered here supply a broader assortment of distinct blurring techniques.

### Box Blur

An adjustable-quality blur spanning the range from extremely coarse to extremely soft.

- Horizontal and Vertical Strength: Use these sliders to set how wide and how tall the blur spreads.
- Same Horizontal/Vertical: Tick this checkbox to either link these parameters or control them on their own.
- Horizontal and Vertical Channel Adjustment: With these sliders you can tune the blur

separately for each color channel. Red: Sets how much the Red channel is blurred compared with the blur applied across the whole image. Green: Sets how much the Green channel is blurred compared with the blur applied across the whole image. Blue: Sets how much the Blue channel is blurred compared with the blur applied across the whole image. Alpha: Sets how much the Alpha channel is blurred compared with the blur applied across the whole image.

- Number of Iterations: Governs how smooth the final blur turns out — a setting of 1 gives the coarsest, most “boxy” result and 6 gives the finest, most fluid one. When the iteration count is low, the output of a box blur can look a fair bit like a lens blur.
- Border Type: Determines the way the blur treats the picture's edges; the choices are Black, Replicate, Reflect, and Wrap Around.
- Blur Alpha: Tick this box so the Alpha channel is blurred together with the picture's contents.

### Directional Blur

A blur locked to one single angle.

- Blur Strength: The quantity of blur you'd like.
- Blur Angle: Which way the blur points.
- Blur Type: With Blur Type set to Realistic, the blur reproduces the look of a photographic motion blur.

Set to Stylized instead, the blur becomes a clean, uncomplicated digital smear.

- Symmetric Blur: With the Symmetric checkbox enabled, the blur looks as though it's built

from both directions, yielding more of a double-image streaking along the blur angle, which mimics camera motion blur. With it disabled, the blur instead reads as travelling one way only, outward from the starting position along the blur angle.

- Channel Adjustment: Lets you set how strong the blur is within one particular channel, measured against the strength of the blur as a whole. Red: Sets the Red channel's blur amount as a proportion of the blur applied overall. Green: Sets the Green channel's blur amount as a proportion of the blur applied overall. Blue: Sets the Blue channel's blur amount as a proportion of the blur applied overall. Alpha: Sets the Alpha channel's blur amount as a proportion of the blur applied overall.
- Border Type: Determines the way the blur treats the picture's edges; the choices are Black, Replicate, Reflect, and Wrap Around.
- Blur Alpha: Tick this box so the alpha channel is blurred together with the picture's contents.

### Gaussian Blur

Delivers a gentle blur that's like viewing the picture through frosted glass, softening fine detail and noise.

- Horizontal and Vertical Strength: A pair of sliders lets you control the Horizontal and Vertical Strength on their own.
- Same Horizontal/Vertical: This checkbox keeps the Horizontal and Vertical Strength figures locked to one another.
- Horizontal and Vertical Channel Adjustment: Use these sliders to fine-tune the blur on a per channel basis. Red: Sets the Red channel's blur amount as a proportion of the blur applied overall. Green: Sets the Green channel's blur amount as a proportion of the blur applied overall. Blue: Sets the Blue channel's blur amount as a proportion of the blur applied overall. Alpha: Sets the Alpha channel's blur amount as a proportion of the blur applied overall.
- Border Type: Determines the way the blur treats the picture's edges; the choices are Black, Replicate, Reflect, and Wrap Around.
- Blur Alpha: Tick this box so the Alpha channel is blurred together with the picture's contents.

### Lens Blur (Studio Version Only)

A premium recreation of how an optical lens defocuses. Its adjustable parameters let you reach assorted “bokeh” looks, comparable to those that arise from various pairings of aperture geometry and lens spherical-aberration correction, both of which shape the “circle of confusion” responsible for the visible forms that appear in picture regions holding tiny pinpoint highlights.

### Shape

Within the Shape group you pick which aperture shape gets simulated, and that choice governs the shape the bokeh takes in this effect.

A user-supplied shape feeding a color node tree to build bespoke bokeh within the Lens Blur plugin

- Shape Type: Determines which kind of aperture is used. Three choices exist: Real Apertures: Pick a true-to-life option from the Aperture Shape pop-up menu beneath, to shape the resulting bokeh. The Aperture Shape choices here are Triangle, Square, Pentagon, Hexagon, Heptagon, or Octagon shaped aperture.

Creative: Pick a more whimsical option from the Aperture Shape pop-up menu beneath, to shape the resulting bokeh. Such choices mimic the bokeh you might genuinely capture by mounting a blackout filter with a custom-cut hole at its center in front of the lens. The Aperture Shape choices here are Heart, Star, Starfish, Starburst, Petals, Lip, Eye, Droplet, and Leaf. External Input: Takes any graphic of your choosing — ideally with a small white form set on a black field — and uses it to shape the bokeh. That form has to be supplied as a graphic or matte clip placed into the Node Editor, after which you connect the image into the second RGB input of the Lens Blur node.

- Aperture Shape: Offers a selection of aperture forms that govern the look of this plugin's simulated bokeh blur.
- Preview Shape: Tick this checkbox to view the exact shape you've chosen to apply.

### Speed

Use the Speed Options group to dial in the balance between quality and speed for this plugin.

- Quality: Three settings — Full, Half (Faster), and Quarter (Fast) — let you strike the right compromise between picture quality and how fast the plugin runs.
- Blur Alpha: Tick this box so the Alpha channel is blurred together with the picture's contents.
- Horizontal and Vertical Crop: Trims down the External Input shape image driving the

bokeh, which is handy when an oversized graphic is bogging things down and you'd like to cut away surplus black around its edges. The result won't visibly shift until you begin trimming into the white portion of the shape.

### Controls

Which parameters show up in the Controls group depends on the Shape Type you currently have chosen.

- Blur Size/Scale: Sets how much blur there is overall. Push it higher and the bokeh's shape grows more distinct.
- Blade Curvature: (Only available with Real and Creative Apertures) Softens the corners of whichever Aperture Shape you picked.
- Rotation: Sets the angle at which the shape is oriented.
- Anamorphism: Adjusts this effect's aspect ratio so it can replicate the lens blur

that anamorphic lenses produce.

- Chroma Shift: Lets you reproduce chromatic aberration inside the blur.
- Highlights: Controls the degree to which the picture's highlights drive the blur, expanding or shrinking the

image to a greater or lesser extent according to how high Smooth Strength is set.

- Apodization: (Only available with Real and Creative Apertures) A slider for tuning the

simulated “Airy disk” pattern within the defocus being produced. Pulling the slider leftward into negative territory emphasizes the concentric rings circling the bokeh pattern, recreating optical diffraction and laying a pattern over the result; pushing it rightward into positive territory steadily softens the simulated bokeh pattern's edges, for an increasingly smooth outcome.

- Catadioptric: (Only available with Real and Creative Apertures) A slider that recreates how a shaped mirror element inside a Catadioptric telescope “improves” focus within the defocused bokeh this plugin generates. As the value climbs, the source image grows steadily sharper while still being warped by the bokeh shape in play, producing gentle image overlays and a markedly different flavor of simulated optical defocus.

### Mosaic Blur

A plain, blocky blur well suited to concealing the face of an anonymous witness.

- Pixel Frequency: Sets each pixel's size, which in turn dictates how dense and detailed the resulting grid of pixels becomes.
- Cell Shape: Sets the underlying form of the mosaic. The choices are Square, Hexagon, and Triangle.
- Aliasing: Sets how tightly each cell samples whatever sits beneath it.
- X Offset: Slides the grid horizontally.
- Y Offset: Slides the grid vertically.
- Aspect: Tunes the cells' aspect ratio.
- Antialias Result: When this box is ticked, the effect does additional work to produce cleaner edges

between the cells.

- Blur Alpha: Tick this box so the Alpha channel is blurred together with the picture's contents.
- Whole Cells Only: Restricts the cells shown to only those falling entirely inside a

window.

### Radial Blur

A blur that imitates the streaking you'd get if the picture were rotating about its central point.

- X and Y Position: Repositions the center of the blur.
- Smooth Strength: Sets how much blurring takes place.
- Blur Type: With Blur Type set to Realistic, the blur reproduces the look of a photographic motion blur.

Set to Stylized instead, the blur becomes a clean, uncomplicated digital smear.

- Blur Symmetry: There are three choices.

Symmetric: The blur reads as built in both directions, yielding more of a double-image arcing around the X/Y Position, mimicking camera motion blur. Clockwise: The blur reads as moving one way, clockwise. Anti-Clockwise: The blur reads as moving one way, counter-clockwise.

- Channel Adjustment: Lets you set how strong the blur is within one particular channel, measured against the strength of the blur as a whole. Red: Sets the Red channel's blur amount as a proportion of the blur applied overall. Green: Sets the Green channel's blur amount as a proportion of the blur applied overall. Blue: Sets the Blue channel's blur amount as a proportion of the blur applied overall. Alpha: Sets the Alpha channel's blur amount as a proportion of the blur applied overall.
- Border Type: Determines the way the blur treats the picture's edges; the choices are Black, Replicate, Reflect, and Wrap Around.
- Move with Sizing: Tick this box so the blur center holds its relative spot in the frame whenever the Input and Editing sizing get altered.
- Blur Alpha: Tick this box so the Alpha channel is blurred together with the picture's contents.

### Zoom Blur

A blur that imitates the streaking you'd get if a camera were pushing in toward the picture.

- Zoom Amount: With Blur Type set to Realistic, this slider works in both directions. Its midpoint is 0, meaning no blur whatsoever. Pulling it rightward pushes the blur outward away from the position, while pulling it leftward draws the image inward toward the Position, blurring outward from that point.
- Blur Type: With Blur Type set to Realistic, the blur reproduces the look of a photographic motion blur. Set to Stylized instead, the blur becomes a clean, uncomplicated digital smear.
- Smooth Strength: With Blur Type set to Stylized, this slider governs how strong the effect is. Its left end is 0, meaning no blur whatsoever. Pulling it rightward pushes the blur outward away from the position, while pulling it leftward draws the image inward toward the Position, blurring outward from that point.
- Center Exclusion: Sets how far out from the XY position the Zoom Blur kicks in.
- Channel Adjustment: Lets you set how strong the blur is within one particular channel, measured against

the strength of the blur as a whole. Red: Sets the Red channel's blur amount as a proportion of the blur applied overall. Green: Sets the Green channel's blur amount as a proportion of the blur applied overall. Blue: Sets the Blue channel's blur amount as a proportion of the blur applied overall. Alpha: Sets the Alpha channel's blur amount as a proportion of the blur applied overall.

- Center Position: Repositions the center of the blur.
- Quality: Pick from Faster, Better, and Enhanced. The Better and Enhanced modes serve to

sharpen up crisp picture detail when blur values are low. Where that's not relevant to your footage, Faster does the job just fine.

- Border Type: Determines the way the blur treats the picture's edges; the choices are Black, Replicate, Reflect, and Wrap Around.
- Move with Sizing: Tick this box so the blur center holds its relative spot in the frame whenever the Input and Editing sizing get altered.
- Blur Alpha: Tick this box so the Alpha channel is blurred together with the picture's contents.
