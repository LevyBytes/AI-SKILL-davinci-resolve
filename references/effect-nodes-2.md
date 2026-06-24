# Effect Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

To read more about the LUT Editor, turn to Chapter 69, “Using Viewers.” in the DaVinci Resolve Reference Manual, or to Chapter 7 in the Fusion Reference Manual.

### Hot Spot Radial tab

### Radial Tab

Radial On Turning this on switches the Radial splines into effect. With it off, the splines’ radial matte never reaches the hot spot, and the color controls’ Mix spline leaves the hot spot alone as well. Radial Mode Working much like the Color mode menu, this one lets you pick whether the radial hot spot tweaks are animated or held static, all through the compact curves editor in the Inspector.

- No Animation: As the default, this keeps one fixed curve adjustment across the whole range.
- Animated Points: With this picked, the radial curves within the spline area can change over time.

After choosing it, jump to whatever frame you want and edit something in the Spline Editor to drop a keyframe. The Interpolated Values option is largely outdated and sticks around only for backward compatibility. Radial Length and Radial Density Splines Inside the Spline window you’ll find curves describing the hot spot’s Length and Density — it functions as a scaled-down Spline Editor. What unlocks these splines is grasping that the horizontal axis in the Inspector’s Spline Editor maps to a location around the hot spot’s circumference. Here, 0.0 corresponds to 0 degrees and 1.0 to 360 degrees. Given that, length governs the radius of the light forming the hot spot around the circumference, while density reflects the brightness of that light around the circumference. Radial Repeat This control plays back the radial splines’ effect x number of times. As an example, a repeat of 2.0 makes the spline act between 0 and 180 degrees rather than 0 and 360, then echoes the spline from 180 to 360. Length Angle This spins the Radial Length spline’s effect around the hot spot’s circumference.

Density Angle This one spins the Radial Density spline’s effect around the hot spot’s circumference. NOTE: A right-click within the spline area brings up a contextual menu whose options relate to editing the spline curves. For an exhaustive account of what the LUT Editor offers, turn to Chapter 107, “LUT Nodes,” within the DaVinci Resolve Reference Manual; the parallel coverage sits in Chapter 47 of the Fusion Reference Manual.

### L1, L2, and L3 Tab

### L1 tab

### L2 tab

### L3 tab

### Lens Reflect Tabs

You use the three Lens Reflect tabs to switch on and shape extra lens flare elements that go beyond the primary and secondary hot spots. Lens Reflect 1-3 Ticking any of these three checkboxes turns on a pair of lens reflection elements you can then adjust with the controls in that tab. Every parameter here acts on all of the active Lens reflection elements within the tab. Element Strength This sets how bright the element reflections are. Element Size This sets how large the element reflections are.

Element Position This sets how far the element reflections sit from the axis, where the axis runs as a line drawn between the hot spot position and the image center. Element Type This bank of buttons picks the shape and density of the element reflections, with the available presets listed below.

- Circular: Produces reflections shaped as circles with mildly soft edges.
- Soft Circular: Produces circular reflections whose edges are extremely soft.
- Circle: Produces a circle shape with a crisp, hard edge.
- NGon Solid: Produces a solid-filled polygon whose side count can vary.
- NGon Star: Produces a star shape with very soft edges and a variable side count.
- NGon Shaded Out: Produces circular shapes with soft edges.
- NGon Shaded In: Produces a polygon of variable side count carrying a very soft

reversed (dark center, bright radius) circle.

- NGon Angle: This control fixes the angle at which the NGon shapes sit.
- NGon Sides: This control fixes how many sides are used whenever the Element Type is

set to Ngon Star, Ngon Shaded Out, and Ngon Shaded In.

- NGon Starriness: This control warps polygons toward star shapes; raising the value makes

the shape more star-like. Lens Color Controls These controls set the lens color, which in turn tints the colors of the reflections. To set a lens color, sample one from a shown image or type RGBA values into the sliders or input boxes.

### Common Controls

Settings Tab Because every Effect node shares the controls on the Settings tab, you’ll find them documented in the “The Common Controls” section that closes this chapter.

### Object Removal [ORm]

### The Object Removal node

### Object Removal Node Introduction

Object Removal leans on the DaVinci Neural Engine to take out an object in the frame with as little manual effort as it can manage. The node performs best at erasing a moving object that travels across a background that stays steady over time, or lens dirt in a shot where the camera itself is moving. You’ll see better outcomes with smaller objects than larger ones, though much of the result hinges on the footage itself.

### Inputs

The Object Removal node accepts both masks and clean plates. Input: Feed the orange input the main footage from which you intend to erase an object. Clean Plate: The magenta input takes a clean plate image source when one is chosen in the controls. Mask: The green input takes a mask shape — polygon, ellipse, rectangle, and the like — that you’ve drawn around whatever object is leaving the scene. Effect Mask: Into the optional blue effect mask input goes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input confines the filter to just the pixels inside the mask. Such an effects mask gets applied to the tool only once the tool has finished processing.

### Basic Node Setup

Wire the footage you want the object erased from into the yellow Input, then send either a polygon shape into the green Mask input or an object-free frame into the clean plate input. The Object Removal tool node structure. What you need is either a polygon or some other shape on the green Mask input, or a clean plate on the pink clean plate input. To set up the Object Removal: 1 In the Polygon node, draw a polygon around whatever object you mean to take out of the scene. 2 Track that polygon by hand or with a tracker so the object you’re removing stays within its bounds for the whole length of the clip. 3 Click the Scene Analysis button found in the Object Removal tool controls. Those steps cover most basic object removal jobs; should trouble arise, you can fine-tune the tool’s parameters in the Inspector. The Object Removal tool doesn’t suit every scene and does its best work on small objects that drift across the frame rather than passing in front of or behind other objects.

Once a polygon is drawn and tracked around the cyclist and the Scene Analysis button in the Object Removal controls is clicked, the cyclist disappears from the background.

### Inspector

The Object Removal controls assist in stripping unwanted objects out of an image.

### Controls

The Object Removal controls give you a way to tune the parameters of the object analysis.

- Show Mask Overlay: Reveals the actual mask in play, tinted red, for the Object Removal.

### Analysis

- Scene Analysis: Clicking this button runs the analysis on the clip with the chosen parameters and swaps the object for a fitting background. Whenever you alter any parameter in this section, you’ll have to click it once more.
- Assume No Motion: When the camera stayed locked off during the shot while the object passed through, ticking this box makes the background analysis far simpler.
- Scene Mode: Offers several ways to analyze the scene, sharpening how the tool reads the motion of the region needing replacement so it can best work out how to fill the gap the removed object leaves.

Background: Analyzes the whole image apart from the object region. Boundary: Analyzes the boundary zone wrapping the object region. Object: Suited to analyzing an object that travels with the background, such as a sticker stuck on a window as the camera moves.

- Analysis Boundary: Sets how large the object’s boundary is for analysis.
- Show Scene Mask Overlay: Flips the scene mask overlay on or off so you can glimpse what sits

behind the mask.

### Render

- Search Range: Should you spot gray fringing on the object removal mask on certain frames as you play back the analyzed result, give the “Search Range” slider a try; it controls how many frames out from the current frame the Object Removal plugin looks for replacement image detail. With a Search Range of 20, for instance, it scans +/-20 frames either side of the current spot, 40 frames in all. The allowance of 10 frames means we look at every fourth frame. As a rule, the smallest range that still delivers an acceptable result is your best bet.
- Blend Mode: When the patch fills in fine but doesn’t sit well against the background, experiment with the Blend mode. Its default, Linear, is a straightforward cloning operation, yet Adaptive Blend is also on offer and can do better — except in cases where the replacement patch’s edges differ in color or brightness from the background.

### Clean Plate

- Clean Plate Source: Chooses where the clean plate comes from. The choices are Gray Image, which amounts to no source at all; Internal, which makes a “best guess” at building a background to fill the frame and blends that with frames it managed to fill; and External, which lets you wire your own plate into the pink input from another node.
- Build Clean Plate: Triggers construction of a fresh clean plate background according to the Clean Plate Source parameter you’ve set.
- Show Clean Plate: Ticking this box reveals the clean plate sitting behind the mask.

### Pseudo Color [PSCL]

### The Pseudo Color node

### Pseudo Color Node Introduction

The Pseudo Color node lets you generate shifts in an image’s color driven by waveforms that the node’s own controls create. You can produce these variances of the original image either static or animated.

### Inputs

The Pseudo Color node carries two Inputs: one image and one effects mask. Input: The orange input handles the main 2D image whose color gets altered. Effect Mask: The blue input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Hooking a mask up here keeps the pseudo color confined to the pixels lying inside the mask. The effects mask gets applied to the tool only after the tool has finished processing.

### Basic Node Setup

Since the Pseudo Color node can’t work on its own as a generator, it needs an image fed to its input from which to derive the color variations.

### Inspector

### Pseudo Color node applied to an image

### Pseudo Color RGBA controls

### Red/Green/Blue/Alpha Tabs

This node splits its controls across four matching tabs, one per RGBA color channel. Color Checkbox With this on, the Pseudo Color node acts on that color channel. Wrap With this on, waveform values that run past the permitted parameter limits fold back to the opposite extreme. High and Low Together, High and Low set the range within a given color channel that the node touches. Soft Edge This slider governs how soft the color transition’s edge is. Waveform This picks which waveform the generator builds. There are four to choose from: Sine, Triangle, Sawtooth, and Square. Frequency This sets the frequency of the chosen waveform, where larger values raise how many times the variances occur. Phase This shifts the waveform’s Phase, and animating it yields color-cycling effects. Mean This fixes the level of the selected waveform; raising it lifts the channel’s overall brightness up to its permitted ceiling. Amplitude Amplitude turns the waveform’s overall power up or down.

### Common Controls

### Settings Tab

Every Effect node carries the same Settings tab controls, which is why their write-ups live in the “The Common Controls” section wrapping up this chapter.

### Rays [CIR]

### The Rays node

### Rays Node Introduction

Rays is a reworked zoom blur effect that streams through an object outward from a point you designate.

### Inputs

The Rays node carries two inputs — an image one alongside an effects mask one. Input: The orange input handles the main 2D image that receives the rays. Effect Mask: The blue input takes a mask shape made from polylines, basic primitive shapes, paint strokes, or bitmaps out of other tools. Wiring a mask in here holds the rays to the pixels inside the mask. This effects mask is applied to the tool after the tool has been processed.

### Basic Node Setup

The Rays node performs best when whatever image or graphic you feed into the orange input carries an Alpha channel for the rays to radiate from.

Rays node set up to emit from a line of text Inspector

### Rays node controls

### Controls Tab

All the main controls you need to tailor the rays sit on the Controls tab. Center X and Y This pair of coordinate controls, along with their viewer crosshair, places the center point of the light source.

Blend Sets what percentage of the original image mixes in with the light rays. Decay Determines how long the rays extend. Weight Governs the rays’ falloff. Exposure Dials in the brightness of the rays. Threshold Marks the luminance level above which the rays begin to form.

### Common Controls

Settings Tab The controls on the Settings tab are shared by all Effect nodes, so you’ll find them described within the “The Common Controls” section near this chapter’s end.

### Shadow [SH]

### The Shadow node

### Shadow Node Introduction

Shadow is a flexible node for building a drop shadow off of an image’s Alpha channel. If you wish, a second image can serve as a depth matte that warps the shadow according to the changing depth in a background image.

### Input

The Shadow node’s three inputs let you attach a 2D image that produces the shadow. A depth map input plus an effect mask can each rein in the area where trails show up. Usually the shadow’s output then gets merged over the real background within the composite. Input: The orange input handles the main 2D image carrying the Alpha channel that originates the shadow. Depth: Fed a 2D image, the green Depth map input pulls a depth matte out of a chosen channel. From there, the light Position and Distance controls reshape the shadow’s look based on depth. Effect Mask: The blue input takes a mask shape made from polylines, basic primitive shapes, paint strokes, or bitmaps out of other tools. Wiring a mask in here restricts where the shadow shows up. That effects mask is applied to the tool after the tool finishes processing.

NOTE: The Shadow node is meant for plain 2D drop shadows. For genuine 3D shadow casting, reach for a Spot Light node together with an Image Plane 3D node.

### Basic Node Setup

In the example below, the Shadow node draws on the output of an image with Alpha and feeds into the foreground of a Merge, with the shadow appearing over the Merge’s background input.

### Inspector

A Shadow node is generated from the MediaIn2 and shown over MediaIn1

### Shadow node controls

### Controls Tab

Every main control you need to shape the shadow’s appearance lives on the Controls tab. Shadow Offset This control places the shadow at an X and Y position. With the Shadow node selected, you can also nudge the Shadow Offset’s position via the crosshair in the viewer. Softness Softness dictates how blurry the shadow’s edges look. Shadow Color Pick the shadow’s color with this control; the most believable shadows tend not to be pure black or perfectly sharp. Light Position This control situates the light relative to the object casting the shadow. The Light Position only matters while the Light Distance slider sits at something other than infinity (1.0). Light Distance This slider shifts the light’s apparent distance anywhere from infinity (1.0) down to zero distance from the shadow-casting object. Dialing in the Light Distance pays off in a more lifelike shadow, where the parts of the shadow farther away stretch longer than the nearer parts. Minimum Depth Map Light Distance This control becomes available once an image is wired into the shadow’s Depth Map input. Its slider sets how much the depth map feeds into the Light Distance. Darker regions of a depth map deepen the shadow, while white regions pull it nearer the camera. Z Map Channel Through this menu you choose which color channel of the image attached to the node’s Depth Map input builds the shadow’s depth map. Choices cover the RGB and A, Luminance, and Z-buffer channels. Output This menu decides whether the output image holds the picture with its shadow applied or just the shadow alone. The shadow-only route comes in handy when color correction, perspective, or other effects must hit the resulting shadow before it’s merged back onto the object.

### Common Controls

Settings Tab The Settings tab’s controls turn up identically on all Effect nodes, so look for their descriptions over in the “The Common Controls” section closing out this chapter.

### Trails [TRLS]

### The Trails node

### Trails Node Introduction

The Trails node makes a ghostly after-trail follow the image. Applied to moving images that carry an Alpha channel, it yields a striking effect. In contrast to a directional blur, the effect surfaces only the image’s earlier motion. Because the trail effect draws on an image buffer, you have to play it or kick off the pre-roll across a number of frames before the effect becomes visible.

### Input

The Trails node’s two inputs let you hook up a 2D image plus an effect mask that can confine where the trails turn up. Input: The orange input handles the main 2D image that the trails get applied to. Effect Mask: The blue input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps out of other tools. Wiring a mask in here confines where the trails effect shows. This effects mask gets applied to the tool once the tool has been processed.

### Basic Node Setup

Here the output of an animated Text node feeds into the Trails node’s input, and trails arise from how the text moves. Be sure to press the Reset button in the Inspector between previews; otherwise the trails pile up.

A Trails node generates trails for the animation in the Text node

### Inspector

### Trails node controls

### Controls Tab

All the primary controls for shaping the trails reside on the Controls tab. Restart This control wipes the image buffer and shows a clean frame free of any ghosting. Preroll This has the Trails node pre-render the effect across however many frames the slider specifies. Reset/Preroll on Render With this checkbox on, the Trails node resets itself whenever a preview or final render begins, pre-rolling the set number of frames. This Time Only Ticking this checkbox limits the pre-roll to the current frame alone, ignoring the earlier frames. Preroll Frames This fixes how many frames to pre-roll. Lock RGBA Ticking this checkbox lets the Gain of each color channel be steered on its own, which makes tinting the Trails effect possible.

Gain The Gain control governs the overall intensity and brightness of the buffered image. Lower settings here yield a far shorter, fainter trail, while higher settings yield a longer, more solid one. Rotate The Rotate control turns the buffered image before the current frame merges into the effect, with the offset accumulating from one trail element to the next. That isn’t the same as each trail element spinning on its own pivot; the pivot stays over the original object. Offset X/Y These controls shift the buffered image before the current frame merges into the effect, giving you independent command of each axis, and the offset accumulates across the trail’s elements. Lock Scale X/Y Ticking this checkbox lets the image buffer’s X- and Y-axis scaling be handled separately per axis. Scale The Scale control resizes the buffered image before the current frame merges into the effect, with the size accumulating across each trail element. Lock Blur X/Y Ticking this checkbox lets the image buffer’s blur be steered separately per axis. Blur Size The Blur Size control lays a blur over the buffered trails before the current frame merges into the effect, the blur accumulating across each trail element. Apply Mode The Apply Mode setting picks the math used to blend or combine the overlapping trailing objects.
