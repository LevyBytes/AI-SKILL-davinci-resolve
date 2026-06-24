# Transform Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Resize Node Introduction

Reach for the Resize node whenever you need to raise or lower an input image's resolution. It comes in handy for moving images between formats (say, from film to video resolution). What this node does is genuinely alter the image's resolution. NOTE: Since this node alters the image's physical resolution, animating its controls isn't advised.

### Inputs

A single input on the Resize node exists for hooking up a 2D image to resize. Input: The orange input takes the primary 2D image you intend to resize.

### Basic Node Setup

In the example below, the Resize node is dropped in between the MediaIn1 node and the background input of the Merge. In contrast to a Transform tool, resizing MediaIn1 alters the clip's resolution. With the resized MediaIn1 node wired into the orange background input, it also fixes the resolution of the Merge output.

With the Resize node, an image can be scaled and its resolution altered.

### Inspector

### The Resize Controls tab

### Controls Tab

Parameters for changing the image's resolution live on the Controls tab. It works in pixel values across the Width and Height controls. Width This governs the image's fresh resolution along the X-axis. Height This governs the image's fresh resolution along the Y-axis. TIP: The formatting contextual menu lets you grab a resolution off a list in a hurry. Rest the mouse pointer over the Width or Height controls, then right-click to bring up the contextual menu. Down at the foot of the menu sits a Select Frame Format submenu listing the available frame formats. Pick any of the entries from the menu to set the Height and Width controls on their own. Auto Resolution Switching this checkbox on sets the Width and Height sliders automatically to the Frame Format settings found within the Preferences window for Fusion Studio, or to the resolution in the DaVinci Resolve Timeline. Reset Size Returns the image dimensions to the image's original size. Keep Frame Aspect Switched on, the Resize node holds the original image's aspect, keeping the original ratio between width and height. Only Use Filter in HiQ For any non-HiQ renders, where speed counts for more than full accuracy, the Resize node will usually fall back on the fast Nearest Neighbor filter. Switch this checkbox off to force Resize to use the chosen filter across all renders. Change Pixel Aspect Switch this checkbox on to reveal a Pixel Aspect control that serves to alter the image's pixel aspect.

Filter Method When a pixel is being rescaled, the pixels around it often get drawn on to yield a more realistic result. A range of algorithms exists for combining these pixels, called filters. The more intricate filters can yield better results yet usually take longer to compute. Which filter suits the job best tends to hinge on how much scaling is involved and on the contents of the image itself.

- Box: A plain interpolation-based resize of the picture.
- Linear: Leans on a bare-bones filter that turns out fairly clean, fast results.
- Quadratic: Turns out a middling result from this filter. Between

speed and quality it strikes a fair balance.

- Cubic: Turns out stronger results on continuous-tone pictures. Where the pictures hold fine detail,

the outcome can come out blurrier than you'd want.

- Catmull-Rom: Turns out solid results on continuous-tone pictures scaled down.

On finely detailed pictures it yields sharp results.

- Gaussian: Sits very close to Bi-Cubic in both speed and quality.
- Mitchell: Resembles Catmull-Rom yet turns out stronger results on finely detailed pictures.

Compared to Catmull-Rom it runs slower.

- Lanczos: Sits very close to Mitchell and Catmull-Rom, just a touch cleaner and a touch slower as well.
- Sinc: A high-end filter delivering exceptionally sharp, detailed results; that said, it can throw

visible "ringing" under certain conditions.

- Bessel: Resembles the Sinc filter though it may run a shade faster.

Window Method (Sinc and Bessel Only) Certain filters, Sinc and Bessel among them, would need an endless supply of pixels to compute precisely. To hasten this operation, a windowing function steps in to approximate the filter and cap the count of pixels needed. This control shows up once a filter calling for windowing is chosen.

- Hanning: A plain tapered window.
- Hamming: Hamming is a lightly adjusted take on Hanning that stops short of tapering all the

way down to zero.

- Blackman: A window whose falloff tapers more sharply.
- Kaiser: A more intricate window yielding results between Hamming and Blackman.

The bulk of these filters earn their keep only when you're enlarging an image. For shrinking images, the Bi-Linear filter is the common pick; the Catmull-Rom filter, though, lends a measure of sharpening to the results and can help hold onto detail while scaling an image down.

### Example

Assorted resize filters, ordered left to right: Nearest Neighbor, Box, Linear, Quadratic, Cubic, then Catmull-Rom, Gaussian, Mitchell, Lanczos, Sinc, and Bessel.

### Common Controls

Settings Tab The Settings tab in the Inspector also has a duplicate across other Transform nodes. These shared controls get a full description toward the end of this chapter under the "The Common Controls" section.

### Scale [SCL]

### The Scale node

### Scale Node Introduction

The Scale node runs nearly identical to the Resize node, the difference being that Resize works in exact dimensions whereas the Scale node works in relative dimensions to spell out the change to the source image's resolution. What this node does is genuinely alter the image's resolution. NOTE: Since this node alters the image's physical resolution, animating its controls isn't advised.

### Inputs

A single input on the Scale node exists for hooking up a 2D image to scale. Input: The orange input takes the primary 2D image you intend to scale.

### Basic Node Setup

In the example below, the Scale node is dropped in between the MediaIn1 node and the background input of the Merge. In contrast to a Transform tool, scaling MediaIn1 alters the clip's resolution. With the resized MediaIn1 node wired into the orange background input, it also fixes the resolution of the Merge output.

Through the Scale node, an image can be scaled and its resolution altered.

### Inspector

### The Scale Controls tab

### Controls Tab

Parameters for changing the image's resolution live on the Controls tab. It works through a multiplier of size to set the fresh resolution. An Edges menu lets you settle how the frame's edges get handled should the scaling shrink. Lock X/Y When ticked, a single Size control alone appears, and any change to the image's scale applies equally to both axes. Clearing the checkbox brings up a separate Size control apiece for X and Y Size. Size What the Size control sets is the scale applied while adjusting the source image's resolution. At a value of 1.0 the image stays untouched, whereas 2.0 doubles the image's current resolution. Set to 0.5, the value cuts the image's resolution in half. Only Use Filter in HiQ For any non-HiQ renders, where speed counts for more than full accuracy, the Scale node will usually fall back on the fast Nearest Neighbor filter. Switch this checkbox off to force Scale to use the chosen filter across all renders. Change Pixel Aspect Switch this checkbox on to reveal a Pixel Aspect control that serves to alter the image's pixel aspect. Filter Method When a pixel is being rescaled, the pixels around it often get drawn on to yield a more realistic result. A range of algorithms exists for combining these pixels, called filters. The more intricate filters can yield better results yet usually take longer to compute. Which filter suits the job best tends to hinge on how much scaling is involved and on the contents of the image itself.

- Box: A plain interpolation-based resize of the picture.
- Linear: Leans on a bare-bones filter that turns out fairly clean, fast results.
- Quadratic: Turns out a middling result from this filter. Between

speed and quality it strikes a fair balance.

- Cubic: Turns out stronger results on continuous-tone pictures. Where the pictures hold fine detail,

the outcome can come out blurrier than you'd want.

- Catmull-Rom: Turns out solid results on continuous-tone pictures scaled down. On finely detailed pictures it yields sharp results.
- Gaussian: Sits very close to Bi-Cubic in both speed and quality.
- Mitchell: Resembles Catmull-Rom yet turns out stronger results on finely detailed pictures. It is

slower than Catmull-Rom.

- Lanczos: Sits very close to Mitchell and Catmull-Rom, just a touch cleaner and a touch slower as well.
- Sinc: A high-end filter delivering exceptionally sharp, detailed results; however,

it can throw visible "ringing" under certain conditions.

- Bessel: Resembles the Sinc filter though it may run a shade faster.

Window Method (Sinc and Bessel Only) Certain filters, Sinc and Bessel among them, would need an endless supply of pixels to compute precisely. To hasten this operation, a windowing function steps in to approximate the filter and cap the count of pixels needed. This control shows up once a filter calling for windowing is chosen.

- Hanning: A plain tapered window.
- Hamming: Hamming is a lightly adjusted take on Hanning that stops short of tapering all the

way down to zero.

- Blackman: A window whose falloff tapers more sharply.
- Kaiser: A more intricate window yielding results between Hamming and Blackman.

The bulk of these filters earn their keep only when you're enlarging an image. For shrinking images, the Bi-Linear filter is the common pick; the Catmull-Rom filter, though, lends a measure of sharpening to the results and can help hold onto detail while scaling an image down.

### Example

A spread of resize filters, reading left to right: Nearest Neighbor, Box, Linear, Quadratic, Cubic, followed by Catmull-Rom, Gaussian, Mitchell, Lanczos, Sinc, and Bessel. NOTE: Since this node alters the image's physical resolution, animating its controls isn't advised.

### Transform [XF]

### The Transform node

### Transform Node Introduction

You can put the Transform node to work for straightforward 2D transformations of the image, including moving, rotating, and scaling. The image's aspect, too, can be reshaped through the Transform node. The Transform node concatenates whatever it produces with neighboring Transformation nodes. The Transform node leaves the image's resolution alone.

### Inputs

A pair of inputs on the Transform node serve to hook up a 2D image and an effect mask, which can serve to confine the transformed area. Input: The orange input takes the primary 2D image that gets transformed. Effect Mask: The blue input takes a mask shape built from polylines, basic primitive shapes, paint strokes, or bitmaps coming from other tools. Wiring a mask into this input confines the transform area to nothing but the pixels inside the mask. An effects mask gets applied to the tool after the tool has been processed.

### Basic Node Setup

The Transform node in the example below is dropped in between the MediaIn2 node and the foreground input of the Merge. In contrast to a Scale or Resize tool, transforming MediaIn2 leaves the clip's resolution untouched. That makes it the tool most often reached for to scale, move, and rotate a clip.

Via the Transform node, an image can be scaled while its resolution stays the same.

### Inspector

### The Transform Controls tab

### Controls Tab

A range of approaches to transform, flip (vertical), flop (horizontal), scale, and rotate an image sits on the Controls tab. Reference size controls ride along too, able to reinterpret the width and height coordinates — from relative values of 0-1 over into pixel values keyed to the image's resolution. Center X and Y Where the image sits on the screen is set here. Its default, 0.5, 0.5, drops the image dead center on the screen. Whatever value appears is always the real position multiplied by the reference size. A rundown of the reference size follows below. Pivot X and Y Where the axis of rotation and scaling lands is set here. Its default, 0.5, 0.5, falls on the image's center. Use Size and Aspect This checkbox settles whether the Transform node hands you independent Size controls for the X and Y scale, or whether Size and Aspect controls get used instead. Size This reshapes the image's scale. Values run from 0 to 5, though any value above zero can be typed into the edit box. With the Use Size and Aspect checkbox ticked, this control scales the image equally along both axes. With the Use Size and Aspect option off, separate control is supplied for X and Y. Aspect An image's aspect ratio gets altered by this control. Push the value above 1.0 and the image stretches along the X-axis. Keep it between 0.0 and 1.0 and the stretch falls along the Y-axis instead. Only while the Use Size and Aspect checkbox is enabled does this control stay on hand.

Angle This control spins the image around the axis. Raising the Angle spins the image counterclockwise. Lowering the Angle spins the image clockwise. Flip Horizontally and Vertically Toggle this control on and the image flips along either the X- or Y-axis. Edges How the image's edges get treated, once the raster's edge is exposed, is what this menu settles.

- Canvas: Whatever image edges get revealed are made to display the current Canvas Color. Its default is black carrying no Alpha, and the Set Canvas Color node is what sets it.
- Wrap: This wraps the image's edges around the borders of the image. It comes in handy for seamless images meant to be panned, building an endless moving background image.
- Duplicate: This makes the image's edges get duplicated as best as it can, carrying the image on past its original size.
- Mirror: To fill out to the frame's edge, the image's pixels are mirrored.

Filter Method When a pixel is being rescaled, the pixels around it often get drawn on to yield a more realistic result. A range of algorithms exists for combining these pixels, called filters. The more intricate filters can yield better results yet usually take longer to compute. Which filter suits the job best tends to hinge on how much scaling is involved and on the contents of the image itself.

- Box: A plain interpolation-based resize of the picture.
- Linear: Leans on a bare-bones filter that turns out fairly clean, fast results.
- Quadratic: Turns out a middling result from this filter. It strikes a fair balance

between speed and quality.

- Cubic: Turns out stronger results on continuous-tone pictures. Where the pictures hold fine detail,

the outcome can come out blurrier than you'd want.

- Catmull-Rom: Turns out solid results on continuous-tone pictures scaled down.

On finely detailed pictures it yields sharp results.

- Gaussian: Sits very close to Bi-Cubic in both speed and quality.
- Mitchell: Resembles Catmull-Rom yet turns out stronger results on finely detailed pictures. It is

slower than Catmull-Rom.

- Lanczos: Sits very close to Mitchell and Catmull-Rom, just a touch cleaner and a touch slower as well.
- Sinc: A high-end filter delivering exceptionally sharp, detailed results; that said, it can throw

visible "ringing" under certain conditions.

- Bessel: Resembles the Sinc filter though it may run a shade faster.

Window Method (Sinc and Bessel Only) Certain filters, Sinc and Bessel among them, would need an endless supply of pixels to compute precisely. To hasten this operation, a windowing function steps in to approximate the filter and cap the count of pixels needed. This control shows up once a filter calling for windowing is chosen.

- Hanning: A plain tapered window.
- Hamming: Hamming is a lightly adjusted take on Hanning that stops short of tapering all the way

down to zero.

- Blackman: A window whose falloff tapers more sharply.
- Kaiser: A more intricate window yielding results between Hamming and Blackman.

The bulk of these filters earn their keep only when you're enlarging an image. For shrinking images, the Bi-Linear filter is the common pick; the Catmull-Rom filter, though, lends a measure of sharpening to the results and can help hold onto detail while scaling an image down.

### Example

Various resize filters shown left to right: Nearest Neighbor, Box, Linear, Quadratic, Cubic, next Catmull-Rom, Gaussian, Mitchell, Lanczos, Sinc, and Bessel.

Invert Transform Pick this control to invert any position, rotation, or scaling transformation. This option earns its keep when you wire the Transform to a tracker's position so as to reintroduce motion back into a stabilized image. Flatten Transform What the Flatten Transform option does is stop this node from concatenating its transformation with neighboring nodes. The node may still concatenate transforms arriving from its input, yet it won't concatenate its own transformation with the node sitting at its output. Reference Size The controls beneath the Reference Size menu don't touch the image directly. Rather, they let you govern how Fusion depicts the position of the Transform node's center. Coordinates are normally depicted as values between 0 and 1, where 1 spans a distance equal to the image's full width or height. This affords resolution independence, since you can resize the image without having to change the center's value. One drawback to this approach is that it makes pixel-accurate adjustments to an image more complicated. To illustrate, picture an image measuring 100 x 100 pixels. To shift the image's center 5 pixels to the right, we'd change the transform center's X value from 0.5, 0.5 to 0.55, 0.5. We know the change has to be 0.05 because 5/100 = 0.05. The Reference Size controls let you state the image's dimensions. This alters the way the control values get displayed, so that the Center shows the actual pixel positions across the X and Y number fields of the Center control. Carrying our example on, if you set the Width and Height to 100 apiece, the Center would now read as 50, 50, and we'd shift it 5 pixels to the right by entering 55, 50. Under the hood, the Transform node still keeps this value as a number between 0 to 1, and were you to query the Center control's value through scripting, or publish the Center control for other nodes to use, you'd get back the original normalized value. The change shows up only in the value displayed for Transform Center within the node control. Reference Width and Height Sliders Match these to the image's width and height, and you change how the Center control's values get shown by Fusion for the Transform node. Auto Resolution Tick this checkbox so that the Reference Width and Reference Height values draw on whatever frame format settings Fusion Studio currently holds, or on the timeline resolution within DaVinci Resolve.

### The Common Controls

Several identical controls in the Inspector are shared by nodes that carry out Transform operations. The controls common across Transform nodes are described in this section.

### Inspector

### The Transform Common controls

### Settings Tab

Every tool in the Transform category carries the Settings tab in the Inspector. Even third-party Transform-type plugin tools have the Settings controls. The controls stay consistent and behave the same way from one tool to the next. Blend The Blend control mixes between two things: the image the tool took in to begin with and the finished, altered image the tool puts out. With the blend value at 0.0, the outgoing image matches the incoming image. Ordinarily this leads the tool to bypass processing altogether, copying the input straight through to the output.

Process When Blend Is 0.0 The tool runs its processing even when the input value sits at zero. This can come in handy if the node is scripted to fire off a task while the node's value rests at 0.0. Red/Green/Blue/Alpha Channel Selector These four buttons serve to confine the tool's effect to particular color channels. This filter typically gets applied after the tool has finished processing. To give an example, if the Red button on a Blur tool is switched off, the blur gets applied to the image first, and then the red channel from the original input is copied back over the result's red channel. There are a few exceptions, such as tools where switching these channels off makes the tool skip processing that channel outright. Tools that behave this way will generally carry a set of identical RGBA buttons on the Controls tab within the tool. Here the buttons on the Settings and the Controls tabs are one and the same. Apply Mask Inverted Switching the Apply Mask Inverted option on inverts the tool's complete mask channel. The mask channel is the pooled result of every mask wired into or generated within a node. Multiply by Mask Picking this option makes the masked image's RGB values get multiplied by the mask channel's values. As a result, any image pixel the mask excludes (in other words, set to 0) goes black/transparent. Use Object/Use Material (Checkboxes) Certain 3D software is able to render into file formats supporting extra channels. The EXR file format notably supports Object ID and Material ID channels, which can serve as a mask for the effect. These checkboxes settle whether those channels get used, where present. Which specific Material ID or Object ID is affected gets chosen through the next set of controls. Correct Edges This checkbox surfaces only once the Use Object or Use Material checkboxes are ticked. It flips the method used to deal with the overlapping edges of objects within a multi-object image. With it switched on, the Coverage and Background Color channels serve to separate and sharpen the effect around the object's edge. With this option switched off (or where neither Coverage nor Background Color channels are present), the mask's edge may show aliasing. To read further about the Coverage and Background Color channels, turn to Chapter 78, "Understanding Image Channels," within the DaVinci Resolve Reference Manual, or to Chapter 18 of the Fusion Reference Manual. Object ID/Material ID (Sliders) Turn to these sliders to pick which ID will build a mask out of the object or material channels of an image. Put the Sample button to work the same way you would the Color Picker: to lift IDs off the image shown in the viewer. The image or sequence must have come out of a 3D software package with those channels rendered in.

### Motion Blur

- Motion Blur: This switches the rendering of Motion Blur on the tool on or off. With this control switched on, the tool's predicted motion serves to produce the motion blur the virtual camera's shutter brings about. With the control switched off, no motion blur gets created.
- Quality: Quality sets the count of samples used to build the blur. A quality setting of 2 will have Fusion build two samples to either side of an object's actual motion. Bigger values yield smoother results yet drive up the render time.
- Shutter Angle: Shutter Angle governs the angle of the virtual shutter put to use in producing the motion blur effect. Wider angles build more blur yet drive up the render times. A value of 360 amounts to holding the shutter open for one full frame exposure. Higher values are within reach and can serve to build interesting effects.
- Center Bias: Center Bias reshapes the position of the center of the motion blur. This opens the door to building motion trail effects.
- Sample Spread: Tweaking this control reshapes the weighting handed to each sample. This bears on the brightness of the samples.
