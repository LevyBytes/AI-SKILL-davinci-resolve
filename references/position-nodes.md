# Position Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Position Nodes

Within this chapter you’ll find coverage of the Position nodes that Fusion provides.

Beside every node name sits an abbreviation, which you can type into the Select Tool dialog while hunting for tools and which also turns up in scripting references. Throughout this document, node trees that display MediaIn nodes in DaVinci Resolve may be read as equivalent to Loader nodes in Fusion Studio, except where a note states otherwise.

### Volume Fog [VLF]

### The Volume Fog node

### Volume Fog Node Introduction

For images that carry XYZ Position channels, the Volume Fog node builds elaborate volumetric fog. Rather than rendering volumetric fog in 3D, it operates over 2D images, which makes it far quicker and gives you interactive feedback while you dial in the fog. To learn more about how this technology operates and what imagery it expects, consult the “WPP Concept” section closing out this chapter.

### Basic Node Setup

An image feeds into the Volume Fog node; below, that image comes from a Renderer 3D whose output channels have World Position switched on. A second input carries the 3D scene holding the camera. The fog texture itself is produced by a Fast Noise node.

### Volume Fog Node Structure

A 3D scene and a rendered scene connected to Volume Fog Inputs Over in the Node Editor, the Volume Fog node presents the inputs listed here. Image: The fog gets applied to the primary image arriving at the orange input. A World Position Pass lives inside this image, held in the XYZ Position channels. Fog Image: Use the green Fog image input to build volumetric fog whose depth and reach vary; you can wire a 2D image into it. A solid place to begin is a Fast Noise kept at a modest 256 x 256 pixel resolution. Effect Mask: A mask shape — drawn from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools — feeds the blue input. Wiring a mask here confines the fog to particular regions. Scene Input: A 3D scene that holds a 3D Camera connects to the magenta scene input.

### Inspector

### The Volume Fog Shape tab

### Shape Tab

How big the fog volume is and where it sits are governed by the Shape tab. To set the position and orientation, you may either drag the Pick buttons into the viewer or work the Translation, Rotation, and Scale controls. Shape This menu toggles between a simple spherical or rectangular volume dropped into your image. Those volumes can be honed further through the Fog image and effect mask. Pick Pull the Pick button out into the viewer so you can grab the XYZ coordinates off any 3D scene or 2D image that holds XYZ values, such as a rendered World Pass, in order to set where the Volume object’s center goes. While picking off a 2D image, confirm it’s rendered in 32-bit float so you keep full precision. X, Y, Z Offset Use these controls to set the fog volume’s center by hand, or animate them, or wire them to other Fusion controls. Rotation Pick Drag the Pick button into the viewer to grab the rotational values off any 3D Scene or 2D image carrying them, such as an XYZ-Normal-Pass, in order to reorient the fog volume. While picking off a 2D image, like an XYZ Normal pass, confirm it’s rendered in 32-bit float so you keep full precision and accurate rotational values. X, Y, Z Rotation These controls spin the fog volume about its center.

X, Y, Z Scale Stretch the fog volume along any axis out from its center to refine the overall Size value named below further. Size How large the created fog volume is overall. Soft Edge Sets how strongly the fog volume fades inward from its outer edge toward its center, producing a softer look.

### The Volume Fog Color tab

### Color Tab

The fog’s detail and color are managed from the Color tab. Adaptive Samples Volume images are built from many stacked layers, so a single volume might hold 64 layers. Ticking this box tunes the rendering algorithm to find the best way of blending those layers.

- Dither: Lays a kind of noise over the result to better blend it and conceal visible differences between layers.

Samples Sets how many times a “ray” fired into the volume is evaluated before the final image is produced. Much like raytracing, larger numbers bring out more detail within the volume while also lengthening render times.

Z Slices Raising the Z Slices value pulls in more images from the connected Fog image sequence to assemble the volume’s depth. As one example, a Fast Noise running a high Seethe Rate can generate such an image sequence. Watch the resolution of those images carefully. Bigger resolutions can demand a great deal of memory. As a rough guide, a 256 x 256 pixel resolution paired with 256 Z Slices (that is, a 256 x 256 x 256 cubic volume, consuming up to 256 MB for full-color 32-bit float data) makes a sound starting point. First Slice Time Picks which frame of the Global Range supplies the opening slice taken from the connected fog image sequence. Confirm that Global In and Global Out, along with your source node’s valid range, all fall inside the span of First Slice Time + Z Slices. Color Lets you alter the color of the fog produced. This multiplies on top of whatever color the connected Fog image already supplies. Gain Raises or lowers the fog’s intensity. Greater Gain produces a stronger glow with less transparency in the fog. Smaller values render the fog less dense. Subtractive/Additive Slider As with the Merge node, this value governs whether the fog composites onto the image in Additive or Subtractive mode, yielding a brighter or dimmer fog look. Fog Only Outputs the generated fog against a black background, which you can then composite by hand or apply as a mask on a Color Corrector for further refinement.

### The Volume Fog Noise tab

### Noise Tab

The form and pattern of the noise added into the fog are controlled by the Noise tab.

Detail Push this slider higher to coax more detail out of the noise result. Bigger values stack on extra layers of progressively finer noise without disturbing the broad pattern. High values render slower yet can deliver a more natural look. Gain This control raises or lowers the brightest regions of the noise map. Brightness This control shifts the noise map’s overall brightness ahead of any gradient color mapping. Under Gradient mode, it behaves much like the Offset control. Translation Work the Translation coordinate control to slide and shift the noise pattern. Noise Rotation Work the Rotation controls to orient the noise pattern across 3D. Seethe Spin this thumbwheel control to interpolate the noise map toward a different noise map. The effect is a creeping shift in the noise, as though it were drifting or flowing. To affect the noise over time, this control has to be animated. Discontinuous By default, the Noise function interpolates among values to form a smooth, continuous gradient of results. Turn this checkbox on to carve sharp discontinuity lines along certain noise contours. What results is a strikingly different effect. Inverted Tick this checkbox to invert the noise, making a negative image of the original pattern. It works best when Discontinuous is enabled too.

### The Volume Fog Camera tab

### Camera Tab

To evaluate a fog volume flawlessly, you can wire a camera or 3D scene into the node’s Scene input.

Camera Should the connected Scene input carry several cameras, this menu lets you pick the right one needed to evaluate the fog volume. In place of wiring up a camera, position values may be supplied by hand or by linking the XYZ values onto separate controls. Translation Pick Slide the Pick button into the viewer to grab XYZ coordinates off any 3D scene or 2D image carrying XYZ values, like a rendered World Pass, in order to set the camera’s center. While picking off a 2D image, confirm it’s rendered in 32-bit float so you keep full precision. X, Y, Z Offset Use these controls to set the camera’s center by hand, or animate them, or wire them to other Fusion controls.

### The Volume Fog Light tab

### Light Tab

Putting the Light tab’s controls to use requires real lights inside your 3D scene. Wire that scene — Camera and Lights included — into the node’s 3D input. Do Lighting Switches lighting calculations on or off. Bear in mind that when OpenCL isn’t in use (that is, rendering on the CPU), these calculations may run somewhat slow. Do In-Scattering Switches light-scattering calculations on or off. The volume still receives light per the Do Lighting checkbox state, yet no scattering takes place. Light Samples Sets how precisely the lighting gets calculated. Larger values mean a more accurate calculation traded against longer render times.

Density Like scattering, this makes the fog read as thicker. Yet with heavy scattering, the light gets cast out of the volume before traveling far through the fog, so it won’t gather much of the transmission color. With high density instead, the fog still reads thicker, but the light is given a chance to transmit, picking up the transmission color before being scattered out. Light direction affects Scattering whenever Asymmetry isn’t 0.0. Density, by contrast, never responds to light direction. Scattering Sets how much of the light ricocheting through the volume ends up scattered out of the fog. When the light scatters more, or more precisely, the odds of it being cast out of the volume rise, so less light remains to keep moving through the fog. This option can make the fog seem denser. Asymmetry Sets the direction in which the light scatters. A value of 0 gives uniform, or isotropic, scattering, where every direction is equally likely. Above 0 it causes “forward scattering,” throwing the light more along the path of the light rays. That resembles what water droplets do inside clouds. Below 0 it gives “back scattering,” where the light scatters more back toward its original source. Transmission Sets the color carried through the fog. Light that escapes being scattered out drifts toward this color. Because it acts as a multiplier, though, a red light paired with blue transmission shows no blue at all. Reflection Alters the intensity of the light cast back out. You can use Reflection to shape the overall color before Emission joins in. It gets combined with the volume texture’s color channels and then scales the values. Since the color options and the volume texture’s color channels multiply together, a red volume texture with the Reflection color options set to blue would not turn the result blue. There, they multiply to give black. Emission This injects a touch of “glow” into the fog, returning energy/light into the calculation. With no lights present in the scene and fog emission set to 1.0, the outcome resembles having no lighting — much like turning the Do Lighting option off. Glowing can also be achieved for a different sort of look by pushing Transmission above 1. That, however, could never occur in the real world.

### Common Controls

Settings Tab The Inspector’s Settings tab is mirrored across the other Position nodes as well. A thorough description of these common controls appears at this chapter’s close, under “The Common Controls” section.

### Examples

Across these examples, we view a volume from outside. To the left, you see the Volume Fog under straight accumulation. That is, the Do Lighting option has been switched off.

To the right, the same volume appears with lighting/scattering switched on and a single point light. Here the Volume grows a little more complex.

On the left, straight accumulation; in the middle, lighting, scattering, and a single point light; and on the right, the scene’s light has been repositioned, which likewise alters the volume’s appearance.

### Volume Mask [VLM]

### The Volume Mask node

### Volume Mask Node Introduction

Out of images carrying XYZ Position channels, the Volume Mask node fashions volumetric masks. One use, for instance, is isolating objects for color correction without having to track or rotoscope the scene. For a fuller account of how this technology operates and what imagery it expects, see the “WPP Concept” section appearing later in this chapter.

### Inputs

These three inputs show up on the Volume Mask node in the Node Editor: Image: A 2D image carrying a World Position Pass in the XYZ Position channels feeds the orange image input. Mask Image: To refine the mask, you can wire an image into the green mask image input. Effect Mask: A mask shape — built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools — feeds the blue input. Wiring a mask here confines the volume mask to particular regions.

### Basic Node Setup

In the example, a MediaIn labeled RGBA holds the principal rendered image drawn from a 3D scene. A World Position Pass coming from a 3D-rendered scene carries the label WPP_PASS. The Channel Booleans node maps the X position pass onto the red channel, Y onto the green channel, and Z onto the blue channel. Pulling the 3D position data out of the World Position Pass, the Volume Mask tool drops a mask into 3D space. That mask then serves as an effect mask on a color corrector, letting you selectively color correct objects within a 3D scene.

For color correction within a 3D scene, a Volume Mask tool puts the World Position Pass to work Inspector

### The Volume Mask Shape tab

### Shape Tab

How big the Volume Mask is and where it sits are governed by the Shape tab. To set the position and orientation, you may either drag the Pick buttons into the viewer or work the Translation, Rotation, and Scale controls. Shape This menu toggles between a spherical or rectangular mask dropped into your image. You can refine the mask further through the mask image input. Translation Pick Slide the Pick button into the viewer to grab XYZ coordinates off any 3D scene or 2D image carrying XYZ values, like a rendered World Pass, in order to set the Volume Mask’s center. While picking off a 2D image, confirm it’s rendered in 32-bit float so you keep full precision. X, Y, Z Offset Use these controls to set the mask’s center by hand, or animate them, or wire them to other Fusion controls. Rotation Pick Drag the Pick button into the viewer to grab rotational values off any 3D scene or 2D image carrying them, like an XYZ Normal pass, in order to reorient the mask. While picking off a 2D image, like an XYZ Normal pass, confirm it’s rendered in 32-bit float and use World Space coordinates so you keep full precision and the correct rotational values. X, Y, Z Rotation These controls spin the mask about its center. X, Y, Z Scale Stretch the mask along any axis out from its center to refine the overall Size value named below further. Size How large, across X, Y, and Z, the created mask is overall. Soft Edge Sets how strongly the Volume fades inward from its outer edge toward its center, producing a softer look.

### The Volume Mask Color tab

### Color Tab

The color and blending of the mask image are managed from the Color tab.

Color Lets you alter the color of the generated Volume Mask. This adds onto whatever color the connected mask image already supplies. Subtractive/Additive Slider As with the Merge node, this value governs whether the mask composites onto the image in Additive or Subtractive mode, yielding a brighter or dimmer mask look. Mask Only Outputs the generated mask against a black background, which can then serve as a mask on a Color Corrector for further refinement.

### The Volume Mask Camera tab

### Camera Tab

To evaluate a Volume flawlessly, you can wire a camera or 3D scene into the node’s Scene input. Camera Should the connected Scene input carry several cameras, this drop-down menu lets you choose the right one needed to evaluate the Volume. In place of wiring up a camera, position values may also be supplied by hand or by routing the XYZ values onto separate controls. Translation Pick Slide the Pick button into the viewer to grab XYZ coordinates off any 3D scene or 2D image carrying XYZ values, like a rendered World Pass, in order to set the camera’s center. While picking off a 2D image, confirm it’s rendered in 32-bit float so you keep full precision. X, Y, Z Offset Use these controls to set the camera’s center by hand, or animate them, or wire them to other Fusion controls.

### Common Controls

Settings Tab The Inspector’s Settings tab is mirrored across the other Position nodes as well. A thorough description of these common controls appears at this chapter’s close, under “The Common Controls” section.

### Z to World Pos [Z2W]

### The Z to World Position node

### Z to World Pos Node Introduction

The Z to World Pos node serves either to build a World Position Pass out of a Z channel plus a 3D Camera, or to derive a Z channel out of a World Position Pass plus a 3D Camera. Producing a World Position Pass from Z-depth comes in handy when your 3D application can’t create a WPP on its own. It’s also useful when 3D-tracking software emits a per-pixel Z-depth alongside the 3D Camera. In that way, the Volume Mask and Volume Fog can be brought to bear on real-world scenes. How good the resulting WPP turns out hinges chiefly on how good the incoming Z channel is. For a fuller account of how this technology operates and what imagery it expects, see the “WPP Concept” section.

### Inputs

These inputs show up on the node tile within the Node Editor: Image: Depending on the operation you want, the orange image input accepts an image holding either a World Position Pass or a Z-depth pass. Effect Mask: A mask shape — built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools — feeds the blue input. Wiring a mask here confines the World Position Pass to particular regions. Scene Input: A 3D scene input holding a 3D Camera connects to the magenta scene input.

### Basic Node Setup

In the example, a MediaIn labeled RGBA holds the principal rendered image drawn from a 3D scene. A Z-depth pass coming from a 3D-rendered scene carries the label Z_PASS. The Channel Booleans node maps the Aux Z channel into the red, green, or blue channel. After the Channel Booleans node comes the Z to World Position node, and an imported 3D camera matching the RGBA image is wired into the 3D camera input on the Z to World Position node. Following the Z to World Position node sits a Channel Booleans node, which can remap the X, Y, and Z positions for use by other nodes.

Out of a Z-depth pass, a Z to World Position node builds a World Position Pass Inspector

### The Z to World Position Controls tab

### Controls Tab

Whether you’re producing a World Position Pass or a Z channel is set in the Controls tab. When the connected scene holds more than one camera, this tab additionally chooses which camera drives the calculation. Mode This menu toggles between making a Z channel out of a World Position Pass or the reverse. Camera Should the connected Scene input carry several cameras, this drop-down menu lets you choose the right one needed to evaluate the image.

### Common Controls

Settings Tab The Inspector’s Settings tab is mirrored across the other Position nodes as well. A thorough description of these common controls appears at this chapter’s close, under “The Common Controls” section.

### WPP Concept

For footage carrying XYZ Position channels, the Position nodes in Fusion open up a wholly fresh approach to working with masks and Volumetrics. Z to World provides the means to build those channels out of a Z channel together with 3D Camera information. Across this overview, we call the World Position Pass the WPP.

### What Is a WPP?

Every pixel’s XYZ position in 3D space is read by the WPP as an RGB color value. For example, a pixel located at 0/0/0 produces a pixel whose RGB value is 0/0/0, so it comes out black. A pixel located at 1/0/0 within the 3D scene yields a pixel that’s fully red. Naturally, when a pixel’s coordinates run to something like -60/75/123, the WPP reads those numbers as RGB color values too. Given how vast a 3D scene can become, the WPP channel ought always to be rendered in 32-bit floating point to deliver the needed accuracy. The image below presents a 3D rendering of a scene centered at 0/0/0 in 3D Space together with its matching WPP. For clearer viewing, the WPP here has been normalized.

### Different Coordinate Spaces

WPPs can be rendered across different Coordinate Spaces. Among these are World Space, Eye Space, and Object Space. The image below shows how those various spaces look, though the nodes in Fusion call for the WPP to be rendered in World Space.

### The Scene Input

These nodes provide a Scene input, which may be either a 3D camera or a 3D scene that holds a camera. While the Z to World node depends on the camera, Volume Mask and Volume Fog can produce their output with no camera attached at all, or with the camera position left at 0/0/0. Even so, attaching a camera that aligns with the original camera the WPP was rendered from, or setting the camera’s position yourself, sharpens the accuracy and look of the resulting fog or mask dramatically.

### The “Invisible Sphere”

So far the example scene carries an empty background, meaning nothing sits in the scene beyond the ground plane and the cubes. Apply fog to a scene like that, one larger than the ground plane, and the outcome resembles the “w/o Sphere” example below, since, lacking any WPP information out past the ground plane, the value that results comes to 0/0/0, so the fog spills into that region as well.

To work around that, drop an invisible bounding sphere into your scene so it generates “dummy” WPP values that help the Fog node build the right volume, as the “with Sphere” example below demonstrates.

### The Common Controls

Several identical controls in the Inspector are shared by the nodes that perform Position operations. This section covers the controls common across Position nodes.

### Inspector

### Position nodes Common Settings tab

### Settings Tab

Found on every tool in the Position category, the Settings tab lives in the Inspector. Its controls stay consistent and behave the same way for each tool.
