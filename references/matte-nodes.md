# Matte Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Matte Nodes

Here the chapter walks through the Matte nodes that Fusion provides. You can type the abbreviation beside each node name into the Select Tool dialog while hunting for tools, and it works in scripting references too. Throughout this document, treat node trees that show MediaIn nodes in DaVinci Resolve as equivalent to Loader nodes in Fusion Studio, except where stated otherwise.

### Alpha Divide [ADv]

### The Alpha Divide node

### Alpha Divide Node Introduction

True to its name, the Alpha Divide exists for one job alone: dividing an incoming image's color channels by its alpha channel. To color correct an image carrying a premultiplied alpha channel, first place an Alpha Divide node ahead of any color correction node so you get a nonpremultiplied image. With that done, you can color correct. Once the correction is finished, tack on an Alpha Multiply node to put the image back into its premultiplied state.

### Inputs

Inside the Node Editor the Alpha Divide node has two inputs. Input: The orange input takes a 2D image carrying a premultiplied Alpha. Effect Mask: The optional blue input looks for a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here confines the Alpha divide to certain pixels. An effects mask gets applied to the tool once the tool has been processed.

### Basic Node Setup

You insert the Alpha Divide node ahead of any color correction performed on an image with a premultiplied Alpha channel. Assume here the MediaIn node carries a premultiplied Alpha channel. With the Alpha Divide node inserted, the color correction nodes then work on the “straight” Alpha. At the chain's tail, an Alpha Multiply node restores the premultiplied Alpha channel. Should you be using just one color correction node, the Pre-Divide/Post-Multiply checkbox on the Options tab can stand in for the Alpha Divide/Alpha Multiple nodes.

Ahead of color correcting an image that has premultiplied alpha, an Alpha Divide node goes in.

### Inspector

This node has no controls.

### Alpha Multiply [AML]

### The Alpha Multiply node

### Alpha Multiply Node Introduction

True to its name, the Alpha Multiply exists for one job alone: multiplying an image's color channels by its alpha channel. To color correct an image carrying a premultiplied alpha channel, first place an Alpha Divide node ahead of any color correction node so you get a non-premultiplied image. With that done, you can color correct. Once the correction is finished, tack on an Alpha Multiply node to put the image back into its premultiplied state.

### Inputs

Inside the Node Editor the Alpha Multiply node has two inputs. Input: The orange input takes a 2D image carrying a “straight” or non-premultiplied alpha. Effect Mask: The optional blue input looks for a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here confines the Alpha multiply to certain pixels. An effects mask gets applied to the tool once the tool has been processed.

### Basic Node Setup

You place the Alpha Multiply node after color correction is done on an image with a premultiplied Alpha channel. Assume here the MediaIn node carries a premultiplied Alpha channel. With the Alpha Divide node inserted, the color correction nodes then work on the “straight” Alpha. At the chain's tail, an Alpha Multiply node restores the premultiplied Alpha channel. Should you be using just one color correction node, the Pre-Divide/Post-Multiply checkbox on the Options tab can stand in for the Alpha Divide/Alpha Multiple nodes.

Following color correction of an image that has premultiplied alpha, an Alpha Multiply node goes in.

### Inspector

This node has no controls.

### Chroma Keyer [CKy]

### The Chroma Keyer node

### Chroma Keyer Node Introduction

By stripping chosen colors out of the scene, the Chroma Keyer node builds an alpha channel (matte) for an image. While the Delta Keyer and Primatte carry particular optimizations for keying off blue and green, the Chroma Keyer handles any color just as well. NOTE: For blue- or green-screen shots, the Delta Keyer or Primatte node is the better choice over the more general-purpose Chroma Keyer node.

### Inputs

Inside the Node Editor the Chroma Keyer node carries four inputs. Input: The orange input takes a 2D image holding the color you want keyed for transparency. Garbage Matte: The gray garbage matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask here and any image areas inside the matte turn transparent. The garbage matte goes straight onto the image's alpha channel. Solid Matte: The white solid matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask here and any image areas inside the matte become fully opaque. Effect Mask: The optional blue input looks for a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here confines the alpha multiply to certain pixels. An effects mask gets applied to the tool once the tool has been processed.

### Basic Node Setup

The Chroma Keyer node accepts a 2D image such as the MediaIn node below, then strips out a color you specify by dragging across it in the viewer. As a result, the chosen color becomes transparency, letting you composite the image as the foreground inside a Merge node.

### Inspector

### The Chroma Key tab

### Chroma Key Tab

Use the Chroma Key tab to make the first color pick for keying. Key Type The Key Type menu sets which selection method drives the matte creation.

- Chroma: The Chroma method builds a matte off the RGB values of the chosen color range.
- Color: The Color method builds a matte off the hue of the chosen color range.

Color Range You make colors transparent by selecting the Chroma Keyer node in the node tree, then dragging a selection over the colors in the viewer. The range controls refresh on their own to mirror your current color pick. Although you can nudge the range sliders a little, picking colors in the displays is usually all it takes. Lock Color Picking Switch this checkbox on and color picking from the viewer is turned off, guarding against accidental additions to the range. Turning it on once you've made the matte's color pick is wise. Every other control in the node stays editable. Soft Range This control eases the chosen color range outward, pulling extra colors into the matte. Reset Color Ranges Click this button to reset the Chroma Keyer's range controls and drop every color pick. All the remaining sliders and controls keep their values.

### The Chroma Key Image tab

### Image Tab

Mostly the Image tab deals with stripping spill color off the foreground subject. Spill happens when light carrying the color you're removing bounces onto the foreground subject. Spill Color This menu picks the color serving as the foundation for every spill suppression technique. Spill Suppression This slider sets how much spill suppression hits the foreground subject. At a setting of 0, no spill suppression applies. Spill Method This menu picks the strength of the algorithm that applies spill suppression to the image.

- None: Pick None when there's no spill suppression to do.
- Rare: This takes off very little of the spill color and is the gentlest method of all.
- Medium: This performs best on green screens.
- Well Done: This performs best on blue screens.
- Burnt: This performs best on blue. Reserve this mode for the most troublesome shots. You'll most likely

need to add heavy color correction after the key to recover, say, your skin tones. Fringe Gamma This control tunes the brightness of the fringe or halo ringing the keyed image. Fringe Size This grows and shrinks the fringe or halo around the keyed image. Fringe Shape Fringe Shape pushes the fringe toward the image's outer edge or toward the fringe's inner edge. The effect shows most clearly while the Fringe Size slider sits at a large value. Cyan/Red, Magenta/Green, and Yellow/Blue Reach for these three controls to color correct the image's fringe. They help fix semitransparent pixels that still hold color from the old background so it matches the new one.

### The Chroma Key Matte tab

### Matte Tab

Through the Matte tab you refine the resulting matte's softness, its density, and how well it fits overall. Filter This control picks the filtering algorithm applied when blur hits the matte.

- Box: The fastest method, though quality drops. Box suits small amounts of blur best.
- Bartlett: Also called a Pyramid filter, Bartlett strikes a fine balance between speed

and quality.

- Multi-box: Choose this filter and the Num Passes slider shows up, letting you govern the

quality. At 1 and 2 passes, results match Box and Bartlett in turn. From 4 passes upward, results usually rival Gaussian, in less time and with no edge “ringing.”

- Gaussian: Built on a genuine Gaussian approximation, the Gaussian filter delivers excellent results, albeit a touch slower than the others. Now and then it yields an extremely slight edge “ringing” on floating-point pixels.

Blur Matte Blur softens the matte's edge according to the Filter menu setting. A value of zero gives a sharp, cutout-style hard edge. Higher values pile more blur onto the matte. Clipping Mode This option sets how edges get handled during domain of definition rendering. It matters a great deal when blurring the matte, which may need samples from parts of the image beyond the current domain.

- Frame: The default, Frame, automatically sets the node's domain of definition to span the image's full frame, in effect disregarding the current domain of definition. Where the upstream DoD is smaller than the frame, the leftover frame area counts as black/transparent.
- Domain: Set this option to Domain to honor the upstream domain of definition while applying the node's effect. That can cause unwanted clipping wherever the node uses a large filter.
- None: Set this option to None and no source image clipping happens at all. So any data the node's effect needs that would ordinarily fall outside the upstream DoD counts as black/transparent.

### FUSION 2459

Contract/Expand This slider trims or enlarges the matte's semitransparent areas. Values over 0.0 enlarge the matte; values under 0.0 trim it. You'd usually pair this control with the Matte Blur to soften a matte's hard edge and cut fringing. Because it touches only semitransparent areas, it does nothing to a matte's hard edge. Gamma Matte Gamma lifts or drops the matte's values across the semitransparent areas. Higher values push the gray areas toward opaque, lower ones push them toward transparent. Fully black or white regions of the matte are left alone. Because it touches only semitransparent areas, it does nothing to a matte's hard edge. Threshold This range slider fixes the lower threshold via the left handle and the upper threshold via the right handle. Anything under the lower threshold setting goes black or transparent in the matte. Anything over the upper threshold setting goes white or opaque in the matte. Everything inside the range keeps its relative transparency. This control often serves to knock out salt and pepper noise in the matte. Restore Fringe This brings back the matte's edge around the keyed subject. Keying often clips out the subject's edge where there's hair. Restore Fringe returns that edge while keeping the matte solid. Invert Matte Tick this checkbox and the keyer's alpha channel flips, so every transparent area turns opaque and every opaque area turns transparent. Solid Matte Solid Mattes are mask nodes or images wired into the node's solid matte input. The solid matte goes straight onto the image's alpha channel. As a rule, solid mattes hold out keying in areas meant to stay opaque, like someone with blue eyes against a blue screen. Turning on Invert flips the solid matte ahead of it being combined with the source alpha. Garbage Matte The garbage mattes are themselves mask nodes or images wired into the node's garbage matte input. The garbage matte goes straight onto the image's alpha channel. As a rule, garbage mattes strip out unwanted bits that can't be keyed, such as microphones and booms. They also serve to fill in areas holding the keyed color that you'd rather keep. You can't mix garbage mattes of differing modes inside a single tool. A Matte Control node frequently follows a Keyer node to add a garbage matte whose effect opposes the matte applied at the keyer. Turning on Invert flips the garbage matte before it's combined with the source alpha. Post-Multiply Image Pick this option so the keyer multiplies the image's color channels against the alpha channel it builds for the image. This option is generally enabled and on by default.

Clear this checkbox and the image no longer counts as premultiplied when you merge it with other images. Reach for the Merge node's Subtractive option rather than the Additive one. For further detail about these Merge node settings, consult the DaVinci Resolve Reference Manual, Chapter 95, "Composite Nodes," or else the Fusion Reference Manual at Chapter 35.

### Common Controls

Settings Tab Other matte nodes carry a copy of the Inspector's Settings tab as well. The chapter's closing “The Common Controls” section walks through these shared controls thoroughly.

### Clean Plate

### The Clean Plate node

### Clean Plate Node Introduction

A pre-keying node, the Clean Plate tool builds an image of the green or blue color screen so as to even out lighting differences. Later the Clean Plate's output feeds the Clean Plate input on the Delta Keyer, so the Delta Keyer can key fine detail without choking or clipping the matte.

### How to Create a Clean Plate

Making a clean plate works the reverse of making a key. Keying has you removing the green or blue color, whereas making a clean plate has you preserving as much of the blue- or green-screen as you can. Box-selecting stretches of the screen color in the viewer leaves you with an image of the green/blue screen. Everything outside the blue or green screen reads as a transparent cutout.

With the selection in hand, the Erode control widens the pre-matte, clearing away stray small pixels of non-green/blue screen near the edges. Growing the pre-matte then plugs the holes until you've got a solid blue or green image.

### Inputs

Inside the Node Editor the Clean Plate node carries three inputs. Input: The orange input takes a 2D image holding the green or blue screen. Garbage Matte: The white garbage matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask here and any image areas inside the matte get left out of the clean plate. For a clean plate, garbage mattes ought to cover whatever lies outside the blue or green screen. Effect Mask: The optional blue input anticipates a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here confines where the clean plate is generated to certain pixels. An effects mask gets applied to the tool once the tool has been processed.

### Basic Node Setup

The Clean Plate node and the Delta Keyer form two distinct branches springing from the main image you mean to key. The green-screen or blue-screen clip is branched off so it feeds the orange image input on the Clean Plate as well as the matching orange image input over on the Delta Keyer. From there the clean plate's output wires into the magenta clean plate input on the Delta Keyer. The Delta Keyer's output then serves as the foreground into a Merge.

### Inspector

### A Clean Plate connected to a Delta Keyer

### The Clean Plate tab

### Plate Tab

The Plate tab holds the main tools for making a clean plate. From this tab you drag over the areas in the viewer, then use the Erode and Grow Edges sliders to build the clean plate. Method The Method menu picks which kind of color selection you use while sampling colors in the viewer.

- Color: Color leans on a difference method to split off the background color. It works well where the screen colors are even.
- Ranges: Ranges leans on a chroma range method to split off the background color. It's the stronger pick for a shadowed screen or screens carrying different colors.

Matte Threshold This range slider fixes the lower threshold with the left handle and the upper threshold with the right handle. Anything below the lower threshold goes black or transparent in the matte. Anything above the upper threshold goes white or opaque in the matte. Everything inside the range keeps its relative transparency. This control frequently serves to throw out salt and pepper noise from the matte. Erode Use the Erode slider to shrink the screen area. It's there to nibble away small non-screen color pixels that might get in the way of a smooth green- or blue-screen clean plate. Crop Crop pulls in from the image's edges. Grow Edges The Grow Edges slider spreads the edge color outward to plug holes until a full green or blue screen forms. Fill The Fill checkbox plugs leftover holes using color drawn from the nearby screen color.

### Time Mode

- Sequence: Builds a fresh clean plate on every frame.
- Hold Frame: Holds the clean plate on one single frame.

### The Clean Plate Mask tab

### Mask Tab

Use the Mask tab to invert the mask wired into the node's garbage mask input. You can apply the garbage mask to clear areas ahead of growing edges or filling leftover holes.

Invert Invert draws on the mask's transparent parts to clear the image.

### Common Controls

Settings Tab Other matte nodes carry a copy of the Inspector's Settings tab too. The closing “The Common Controls” section of this chapter explains these shared controls in detail.

### Cryptomatte [Cry] (Studio Version Only)

### The Cryptomatte node

### Cryptomatte Node Introduction

Fusion's Cryptomatte tool lets you read embedded mattes rendered into an EXR. Instead of leaning on manually-assigned masks or color keying, Cryptomatte reads the encoded IDs and pulls each one out so that selecting it becomes easy. With this tool you can build mattes for particular objects or materials within a 3D-rendered scene.

### Inputs

The Cryptomatte node has just one input in the Node Editor. Input: The orange input takes a 2D EXR image carrying embedded mattes.

### Basic Node Setup

The Cryptomatte node accepts an EXR image holding embedded mattes, then lets you pick which mattes carry on to the rest of the comp.

Cryptomatte accepting an EXR, picking out its mattes, and then handing them off to the Color Corrector and Bitmap tools

### Inspector

### The Cryptomatte Controls

With these parameters you steer the matte selection of an EXR file.

- View Layer: Swap the layer and matte type to pick (Object, Material etc). This shapes which matte type the Pick control lets you choose.
- View Mode: Alters the Cryptomatte tool's output. Colors: Renders the layer IDs as distinct colors. Edges: Renders the source EXR with the mattes outlined over the image. Beauty: Renders the source EXR. Matte: Puts out a black and white image of the chosen matte.
- Select Matte: Pick mattes from the viewer or off a list. Pick: Click to bring up a pick window holding a matte list selection. Click-drag, or use Cmd/Control-clicks, to grab several mattes from the list. Mode: Click and drag the control to summon an eye dropper cursor for picking or dropping mattes in the viewer.
- Selected Matte List: The Selected Matte List shows your chosen mattes in a list view. The selection lights up yellow in the viewer. Clear: Click the bin icon to drop the chosen mattes. Clear All: Click this button to drop every matte from the Selected Matte List. Clear Selected Layer: Click to drop all mattes off the layer. Expression: Into this field you can add regular expressions to pick layers within the tool. Matte Layers: Cycle among only the Selected layers, View, and All.

### Common Controls

Settings Tab Other matte nodes carry a copy of the Inspector's Settings tab as well. The closing “The Common Controls” section of this chapter covers these shared controls in detail.

### Delta Keyer

### The Delta Keyer node

### Delta Keyer Node Introduction

A sophisticated color difference keyer, the Delta Keyer packs plenty of features and controls for tuning the matte and pulling the subject off a blue or green screen. Several keying systems live inside it: as the master difference keyer you've got the Key tab, while Pre-Matte serves as a built-in clean plate for evening out screen color. Tuning, Fringe, and Matte round out the keying process. The tabs sit roughly in the order you'd normally work through them.

### Inputs

Inside the Node Editor the Delta Keyer node carries five inputs. Input: The orange input takes a 2D image holding the color you want keyed for transparency. Garbage Matte: The gray garbage matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask here and any image areas inside the matte turn transparent. The garbage matte goes straight onto the image's alpha channel. Solid Matte: The white solid matte input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wire a mask here and any image areas inside the matte become fully opaque. Clean Plate: Takes in whatever image the Clean Plate node produces. Effect Mask: The optional blue input anticipates a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps masks. Wiring a mask here confines the keying to certain pixels. An effects mask gets applied to the tool once the tool has been processed.

### Basic Node Setup

Getting going with the Delta Keyer starts by opening it in the Inspector; from there, click and drag the background color eyedropper tool over into the Viewer to pick the color you want keyed out. That color then goes gray in the Viewer. One Delta Keyer rarely nails perfect results, since most green- or blue-screen shots carry issues the keyer wasn't built to take on. Keyers commonly need a hand from garbage mattes or solid mattes drawn with a Polygon or B-Spline node. Some shots also call for more than a single keyer to reach perfect results. That's shown in one of the examples below, where the first Delta Keyer builds a hard inner white matte while a second Delta Keyer captures the soft edges. The core matte below then wires into the solid matte input on the second Delta Keyer. Color correction, spill suppression included, is best run as its own branch in your node tree. Keeping your matte separate from your color correction through underlays makes plain which branch of nodes is doing what.

### Starting point for a Delta Keyer setup

A larger key setup using two Delta Keyers, Polygon and B-Spline nodes to supply mattes, plus a separate branch handling color correction Inspector

### The Delta Keyer View Mode menu

### Key Tab View Mode

The View Mode menu sits at the top of the Inspector. Its default pick shows the final result. You can switch the view to inspect various midway stages of the keying process.

- Pre Matte: Shows the output of the Pre Matte key.
- Matte: Shows the key's alpha before it's combined with the solid and garbage masks.
