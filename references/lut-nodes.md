# Lut Nodes

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### LUT Nodes

The LUT nodes that Fusion offers are covered in this chapter.

Each node name carries an abbreviation beside it, handy in the Select Tool dialog while hunting for tools and within scripting references. Throughout this document, treat node trees that show MediaIn/MediaOut nodes in DaVinci Resolve as equivalent to Loader/Saver nodes in Fusion Studio, except where a note says otherwise.

### File LUT [FLU]

### The File LUT node

### File LUT Node Introduction

The File LUT node lays a Lookup table (LUT) over the image, working with either a plain 1D LUT or a supported 3D LUT. In contrast to the Color Curves node, it skips a spline-based LUT entirely. Rather, it pulls the LUT out of a file held on your computer or server. Two benefits come from this. For one, the composition keeps nothing more of the LUT than the path pointing to the file. Because LUT files can run large, that can shrink a composition’s file size sharply whenever several LUTs are in play. The other benefit is that you can retune every File LUT node pointing at the same file all at once, simply by editing what that LUT contains. That comes in handy whenever the very same LUT-based color correction shows up across many separate compositions.

### Inputs

Two inputs sit on the File LUT node: one carries the main image, while the other takes an effect mask that confines where the LUT lands. Input: Only this orange input has to be wired up. It takes a 2D image output, which then has the LUT laid over it. Effect Mask: This optional blue effect mask input takes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools. Wire a mask into it and the LUT then touches only the pixels falling inside that mask. Such an effects mask kicks in on the tool once the tool itself has finished processing.

### Basic Node Setup

You can drop the File LUT node downstream of a MediaIn node in DaVinci Resolve, or of a Loader node in Fusion Studio. One use of this arrangement is shifting the camera-original image into linear color space ahead of compositing. Another, shown in the example beneath this, places the File LUT last as a grading LUT carrying a look handed down by the colorist.

A File LUT node sitting at the tail of a node tree, delivering a colorist’s look

### Inspector

### File LUT controls

### Controls Tab

On the Controls tab you’ll find choices for loading a LUT and tweaking the gain, color space, and Alpha channel where one is present. LUT File Type the path to the LUT file into this field. Rather than keying it in by hand to the LUT File field, click the Browse button to bring up a file-browser window and track the LUT file down. As of now this node handles LUTs that Fusion exports in .LUT and .ALUT formats, DaVinci Resolve’s .CUBE format, plus a handful of 3D LUT formats. Should it fail to find or load the file you named, the node throws an error message onto the Console. Pre-Gain: A gain tweak that this slider applies ahead of the LUT. It’s handy for reining in highlights before the LUT clips them off. Post-Gain Here the slider applies a gain tweak once the LUT has run. Color Space Use this menu to switch which color space the LUT operates in. By default the curves spelled out in the LUT hit the RGB color space, though YUV, HLS, HSV, and further choices are on offer too. Pre-Divide/Post-Multiply Tick the Pre-Divide/Post-Multiply checkbox and the image’s pixel values get divided by the Alpha values before the LUT runs, then multiplied back by the Alpha value once the correction is done. Doing so guards against producing illegally additive images, especially along the fringes of a blue/ green key or while handling 3D-rendered objects.

### Settings Tab

Other LUT nodes carry this same Settings tab in the Inspector. A thorough rundown of these shared controls waits in the “The Common Controls” section closing this chapter.

### LUT Cube Analyzer [LCA]

### The LUT Cube Analyzer node

### LUT Cube Analyzer Node Introduction

Fed an image that the LUT Cube Creator produced, the LUT Cube Analyzer lets you write out a 3D LUT file in ALUT3, ITX, or 3DL format. Pass the untouched LUT Cube Creator image straight into the node and you get back an unaltered, or 1:1, LUT file, with the viewer showing nothing. That said, you’re free to tweak, grade, and color correct that original cube image through as many nodes as you wish before handing the outcome to the LUT Cube Analyzer. The LUT it builds then mirrors your color pipeline exactly.

### Inputs

Just one orange input sits on the LUT Cube Analyzer. Input: That orange input receives the output from whatever node is reworking an image first made by the LUT Cube Creator.

### Basic Node Setup

In the example beneath, a node tree opens on a LUT Cube Creator node and runs through a couple of color adjustments. From there the adjusted image feeds a LUT Cube Analyzer, which writes out the LUT file.

A LUT begins its life at the LUT Cube Creator and finishes up at a LUT Cube Analyzer.

### Inspector

### LUT Cube Analyzer controls

### Controls Tab

On the LUT Cube Analyzer node, the Controls tab is where you pick the LUT output format you want, set a filename, and commit the 3D LUT to disk. Type Choose which output format the 3D LUT should take. Filename Type in the path where the file should land along with the name of the LUT file. As an alternative, click the Browse button to pop a file browser for choosing the location and filename. Write File Hit this button and the 3D LUT file is built from the settings above.

### Settings Tab

This Settings tab in the Inspector turns up on the other LUT nodes as well. You’ll find these shared controls laid out fully within the “The Common Controls” section that ends this chapter.

### LUT Cube Apply [LCP]

### The LUT Cube Apply node

### LUT Cube Apply Node Introduction

On its foreground input the LUT Cube Apply node accepts an image the LUT Cube Creator made, then lays that LUT onto whatever image is wired to the background input. Send the original image through and the node hands back an unaltered, or 1:1, output. Even so, you may tweak, grade, and color correct that original cube image across as many nodes as you please before passing the result to the LUT Cube Apply. Alternatively, feed it a LUT image graded ahead of time so the LUT applies without your ever writing a real 3D LUT by way of the LUT Cube Analyzer.

### Inputs

Three inputs live on the LUT Cube Apply: a green input that the LUT Cube Creator’s output plugs into, an orange input carrying the image you want the LUT laid onto, and a blue effect mask input Input: That orange input takes a 2D image, which then receives the LUT. Reference Image: Wire the green input to either the LUT Cube Creator’s output or to a node reworking the image that began at the LUT Cube Creator. Effect Mask: The optional effect mask input takes a mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps from other tools. Hook a mask here and the LUT Cube Apply confines itself to just the pixels inside that mask. This kind of effects mask hits the tool once the tool has wrapped up processing.

### Basic Node Setup

The example beneath opens with a LUT Cube Creator node and passes through a pair of color adjustments. That adjusted image then plugs into the green Reference input on the LUT Cube Apply, while the image you want carrying the LUT goes to the orange Input.

A LUT made by the LUT Cube Creator gets laid onto an image by means of the LUT Cube Apply node.

### Inspector

The LUT Cube Apply node carries no controls at all. Whatever LUT feeds the green foreground input gets laid onto the image feeding the orange background input, and no real 3D LUT need ever be written through the LUT Cube Analyzer.

### Settings Tab

You’ll see this same Settings tab in the Inspector echoed on the other LUT nodes. The “The Common Controls” section wrapping up this chapter covers these shared controls in full.

### LUT Cube Creator [LCC]

### The LUT Cube Creator node

### LUT Cube Creator Node Introduction

The LUT Cube Creator builds an image meant to be used downstream by the LUT Cube Analyzer or LUT Cube Apply nodes. Its output is fair game for grading, color correction, or reworking with any tool, whether inside Fusion or out. Should you work outside Fusion, hold the image at 32-bit floating point so color accuracy survives. Run the untouched LUT Cube Creator image into the LUT Cube Analyzer node and you end up with an unaltered, or 1:1, LUT file, the viewer left blank.

### Inputs

No inputs sit on the LUT Cube Creator. This node exists to build an image from which a LUT can be made.

### Basic Node Setup

Below, the example begins at a LUT Cube Creator node and threads through two color adjustments. That adjusted image then plugs into a LUT Cube Analyzer, which spits out the LUT file. The whole LUT-making path kicks off at the LUT Cube Creator and wraps up at a LUT Cube Analyzer.

### Inspector

### LUT Cube Creator controls

### Controls Tab

The Controls tab lays down a kind of test pattern that goes toward building a 3D LUT. What you set here governs how intricate the pattern is that ultimately feeds a LUT through the LUT Cube Analyzer. Type: Reach for the Type menu to build a pattern of color cubes.

- Horizontal: Builds a long, horizontal strip standing in for a color cube.
- Vertical: Builds a long, vertical strip standing in for a color cube.
- Rect: Builds a rectangular image, pictured beneath, standing in for a color cube.

### A Cube image created with the Rect type

### The resulting color cube

Size Sets how much resolution the color cube carries. Common Size choices for color cubes run to 33 (33 x 33 x 33) or 65 (65 x 65 x 65). Each figure counts the samples along one side of the cube. So a 33 x 33 x 33 cube works out to roughly 35,937 color samples. NOTE: Pushing resolution higher sharpens the result, yet it leans harder on memory and computation alike.

### Settings Tab

This Settings tab in the Inspector recurs on the other LUT nodes too. The “The Common Controls” section coming up next walks through these shared controls.

### The Common Controls

Across the Inspector, the LUT nodes hold a set of matching controls in common. What this section covers are the controls shared among LUT nodes.

### Inspector

### Common LUT Settings Inspector

### Settings Tab

Every tool in the LUT category carries this Settings tab in the Inspector. The controls stay uniform and behave identically from one tool to the next, though a tool here or there throws in an option or two of its own, which get covered here as well.

Use GPU There are three choices on the Use GPU menu. Pick Disable to shut off hardware-accelerated rendering on your computer’s graphics card. Enabled puts the hardware to work. Auto leans on a capable GPU whenever one’s around and falls back to software rendering when none is. Hide Incoming Connections Tick this checkbox to tuck away the connection lines arriving from upstream nodes, leaving a node tree that reads cleaner and easier. With it on, the Inspector shows a blank field for every input on a node. Drag a connected node out of the node tree onto that field and the incoming connection line stays hidden, so long as the node isn’t selected in the node tree. Select the node in the node tree and the line comes back. Comments Use the Comments field to jot notes onto a tool. Click into the blank field and type away. Once a tool carries a note, a small red square turns up in the node’s lower-left corner while its full tile shows, or a small text-bubble icon appears off to the right when the nodes are collapsed. To read that note inside the Node Editor, hover the mouse pointer over the node so the tooltip appears. Scripts From the Settings tab, every Fusion tool offers three Scripting fields. Each holds an edit box where you drop scripts that run as the tool renders. For fuller detail on scripting nodes, turn to the Fusion scripting documentation.
