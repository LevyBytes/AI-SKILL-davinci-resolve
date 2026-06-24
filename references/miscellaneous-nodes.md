# Miscellaneous Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Miscellaneous Nodes

Fusion's assorted nodes are the subject of this chapter.

The shorthand sitting beside each node name works inside the Select Tool dialog while you hunt for tools, and it carries over to scripting references too. Within these pages, node trees that depict MediaIn nodes in DaVinci Resolve may be swapped freely for Loader nodes in Fusion Studio, except where a note states otherwise.

### Auto Domain [ADoD]

### The Auto Domain node

### Auto Domain Node Introduction

Drawing on the bounds of the input image’s background Canvas color, the Auto Domain node fixes the image’s domain of definition (DoD) by itself. The image’s real physical dimensions remain unaltered. A handful of EXR images ship with their DoDs already tuned, while the rest of the formats do not. When you work with formats besides EXR, this node can hasten compositions by tuning the DoD to the actual content rather than to the frame’s dimensions. Take a CG character, which hardly ever fills an image’s whole frame. Faced with that sort of image, the Auto Domain node pins the DoD to a rectangular zone by checking image pixels against the Canvas color. What the Canvas color tells you is the color carried by the pixels that lie beyond the DoD. Where no Canvas color has been established through the Set Canvas Color node, the color falls back to black. Such a default suits an image that carries a premultiplied alpha channel. You wind up with a DoD that surrounds just the slice of the clip holding the character alone. To keep pace with motion, the DoD refreshes every frame, as when a character strolls nearer the camera. Yet should a clip lack an alpha channel, the Set Canvas Color node serves to set the Canvas color as solid alpha tinted to match the solid background. Further detail on the Set Canvas Color node lives in Chapter 94, "Color Nodes," of the DaVinci Resolve Reference Manual, or in Chapter 34 of the Fusion Reference Manual.

NOTE: The Domain of Definition names a bounding box drawn around the pixels holding a nonzero value. Its purpose is to confine image-processing math and to hasten rendering.

### Inputs

By way of its one input, the Auto Domain node takes a 2D image plus an effect mask, the latter handy for bounding the blurred area. Input: For the primary 2D image undergoing the blur, the orange input is the one to use. Effect Mask: Feeding the blue input is a mask shape drawn with polylines, basic primitive shapes, paint strokes, or bitmaps out of other tools. Wiring a mask here pins the blur down to only the pixels inside the mask.

### Basic Node Setup

The case shown below takes it that the image holds no alpha channel but instead shows a CG character rendered over a black background. You see this often across render passes such as specular or shadows. That image then runs into a Set Canvas Color node, which makes the Canvas color black with a solid alpha. From there the Set Canvas Color feeds the Auto Domain node, which picks out the pixels and pins the DoD. Were the source image already carrying a premultiplied alpha channel, you could skip the Set Canvas Color and wire the image straight into the Auto Domain node.

An Auto Domain node trims the region of image processing on its own.

### Inspector

### The Auto Domain Controls tab

### Controls Tab

Most of the time the Auto Domain node works out the DoD bounding box automatically; still, you can reshape that rectangle through the Controls tab in the Inspector. Left Marks the left edge of the ADoD’s search area. Pushing this slider up shifts the left edge rightward, dropping more data off the left margin. Here a value of 1 lands at the image’s right border, whereas 0 sits at its left border. The slider defaults to 0 (left border). Bottom Marks the bottom edge of the ADoD’s search area. Pushing this slider up shifts the bottom edge upward, dropping more data off the bottom margin. Here a value of 1 lands at the image’s top border, whereas 0 sits at its bottom border. The slider defaults to 0 (bottom border). Right Marks the right edge of the ADoD’s search area. Pushing this slider up shifts the right edge leftward, dropping more data off the right margin. Here a value of 1 lands at the image’s right border, whereas 0 sits at its left border. The slider defaults to 1 (right border).

Top Marks the top edge of the ADoD’s search area. Pushing this slider up shifts the top edge downward, dropping more data off the top margin. Here a value of 1 lands at the image’s top border, whereas 0 sits at its bottom border. The slider defaults to 1 (top border).

### Common Controls

Settings Tab The Inspector’s Settings tab repeats across the other miscellaneous nodes as well. You will find these shared controls spelled out fully where this chapter closes, under the “The Common Controls” section.

### Change Depth [CD]

### The Change Depth node

### Change Depth Node Introduction

A single plain purpose drives the Change Depth node, which is to alter the bits per color channel a node draws on for processing. You will often see it applied right after color correcting 32-bit floating-point image files, dropping them from float processing down to 16-bit per channel so as to spare both memory and performance. It earns its keep too when, beyond some spot in your node tree, you decide your images want working at a deeper bit depth than they began with, or when you trim the bit depth to conserve memory.

### Inputs

Through its lone input, the Change Depth node accepts a 2D image together with an effect mask, the latter useful for bounding the blurred area. Input: For the primary 2D image headed for conversion, the orange input is the one to use. Effect Mask: The blue input receives a mask shape made with polylines, basic primitive shapes, paint strokes or bitmaps out of other tools. Tying a mask to this input pins the blur down to only the pixels lying inside the mask.

### Basic Node Setup

In the example beneath this, a Loader node in Fusion Studio gets color corrected and is then stepped down from a floatingpoint image to a 16-bit image, sparing image-processing time and memory.

A Change Depth node set downstream of the color correction performed on a floating-point image.

### Inspector

### The Change Depth Controls tab

### Controls Tab

The pair of controls belonging to this node are the Depth menu and the Dither menu. That duo of menus serves to convert and fine-tune the image’s color depth. Depth The Keep setting leaves the image untouched and merely holds onto the input depth. Every other option swaps the image’s bit depth to whatever value it names. Dither While stepping down out of a higher bit depth, throwing in Error Diffusion or Additive Noise can prove handy for masking artifacts thrown off by troublesome (high-contrast) areas.

### Common Controls

Settings Tab This same Settings tab from the Inspector turns up again throughout the other miscellaneous nodes. A thorough rundown of these shared controls sits at the chapter’s close within the “The Common Controls” section.

### Custom Tool [CT]

### The Custom Tool node

### Custom Tool Node Introduction

Among all of Fusion’s nodes, the Custom Tool node stands out as both the most intricate and the most potent. Its job is to build custom expressions and filters that reshape an image. Beyond the three image inputs it hands you, the Custom Tool node permits hooking up as many as eight numeric inputs along with up to four XY position values pulled from other controls and parameters across the node tree. The images open up per-pixel calculations over a whole roster of channels: the Red, Green, and Blue trio, then Alpha, plus Z together with Z-Coverage; the UV texture coords sit alongside the XYZ Normals, while the RGBA background color and the XY motion vector round things out. A fair bit of experience with scripting, or with C++ programming, will help you make sense of the structure and terminology the Custom Tool node leans on.

### Inputs

Three image inputs, one matte input, and one effect mask input belong to the Custom Tool node. Input: To form your composite, the orange, green, and magenta inputs blend 2D images together. Once keyed into the Custom Tool fields, they go by c1, c2 and c3 (here c stands across all three of the R, G, B channels) Matte Input: A matte built with polylines, basic primitive shapes, paint strokes, or bitmaps out of other tools feeds the white input. Tying a matte to this input lets a matte fold into whatever equation you like. Keyed into the Custom Tool fields, that matte goes by m1. Effect Mask: The blue input takes a mask shape drawn with polylines, basic primitive shapes, paint strokes, or bitmaps out of other tools. Tying a mask to this input pins the Custom Tool effect down to only the pixels inside the mask.

### Basic Node Setup

Shown below, the Custom Tool draws in two image inputs and a matte input, then fuses them by way of some calculation. Its result may then pass along to a Merge or to further image-processing nodes. A Custom Tool serves to craft effects of your own out of C++ and scripting.

### Inspector

### The Custom Tool Controls tab

### Controls Tab

Point in 1-4, X and Y This set of four controls are 2D X and Y center controls that expressions keyed into the Setup, Intermediate, and Channels tabs can reach as variables p1x, p1y, ...., p4x, p4y. Behaving as ordinary positional controls, they may be animated or tied to modifiers just as any other node could. Number in 1-8 Whatever these controls hold becomes reachable by expressions keyed into the Setup, Intermediate, and Channels tabs as variables n1, n2, n3, ..., n8. Behaving as ordinary slider controls, they too may be animated or tied to modifiers precisely as any other node could. LUT in 1-4 What the Custom Tool node supplies here is 4 LUT splines. Whatever these controls hold reaches expressions keyed into the Setup, Intermediate, and Channels tabs by way of the getlut# function. As one example, pointing the R, G, B, and A expressions at `getlut1(r1)`, `getlut2(g1)`, `getlut3(b1)`, and `getlut4(a1)`, in turn, would have the Custom Tool node act like the Color Curves node. The options under the Config tab let you rename these controls so their meaning reads more plainly, yet expressions go on reading the values as n1, n2, ..., n8.

### The Custom Tool Setup tab

### Custom Tool Setup Tab

Setup 1-4 As many as four distinct expressions can be worked out within the Custom Tool node’s Setup tab. The Setup expressions run a single time per frame ahead of every other calculation. Their results then reach the rest of the Custom Tool node’s expressions as variables s1, s2, s3, and s4. NOTE: Since these expressions fire just once per frame rather than for each pixel, reaching for per-pixel variables such as X and Y or channel variables such as r1, g1, b1 serves no purpose. The values you may use take in constants, variables such as n1..n8, time, W and H, plus functions such as `sin()` or `getr1d()`.

### Custom Tool Intermediate Tab

Intermediate 1-4 One more set of four expressions can be worked out within the Inter tab. The Inter expressions run once per pixel after the Setup expressions have run yet ahead of the Channel expressions. You may use per-pixel channel variables such as r1, g1, b1, and a1. Their results come through as variables i1, i2, i3, and i4.

### The Custom Tool Intermediate tab

### Custom Tool Config Tab

Random Seed Lean on this to fix the seed behind the `rand()` and `rands()` functions. A click of the Randomize button drops a random value into the seed. You might call on this control whenever several Custom Tool nodes are wanted, each yielding its own different random results.

### The Custom Tool Config tab

Number Controls Eight sets of Number controls are present, each lining up with one of the eight Number In sliders in the Controls tab. Clearing the Show Number checkbox tucks away the matching Number In slider, while editing the Name for Number text field renames it. Point Controls Four sets of Point controls are present, each lining up with one of the four Point In controls in the Controls tab. Clearing the Show Point checkbox tucks away the matching Point In control along with its crosshair in the viewer. In like manner, editing the Name for Point text field renames the control.

### The Custom Tool Channel tab

### Custom Tool Channels Tab

RGBA, Z, UV Expressions, and XYZ Normal Expressions Through the Channel tab you lay out one expression for every channel the image makes available. Each such expression runs once per pixel. Out of that comes the value carried by that pixel in the image’s output. As a rule, Color Channel expressions (RGBA) ought to hand back floating-point values between 0.0 and 1.0. Anything past that gets clipped should the destination image be an integer. The remaining expression fields ought to yield values fitting their channel (e.g., between -1.0 and 1.0 for Vector and Normal fields, 0.0 to 1.0 for Coverage, or any value at all for Depth). The Channel expressions are free to draw on the results of both the Setup expressions (as variables s1–s4) and the Inter expressions (as variables i1–i4).

### Custom Tool Node Syntax

### Value Variables n1..n8 p1x..p4x p1y..p4y s1..s4

Numeric Inputs Position Values (X-axis) Position Values (Y-axis) Setup Expression Results

Value Variables i1..i4 time x y w (or w1..w3) h (or h1..h3) ax (or ax1..ax3) ay (or ay1..ay3)

Inter Expression Results Current Frame The current pixel’s horizontal co-ordinate, lying between 0.0 and 1.0 The current pixel’s vertical co-ordinate, lying between 0.0 and 1.0 Width of Image (for image1..image3) Height of Image (for image1..image3) Image Aspect X (for image1..image3) Image Aspect Y (for image1..image3)

NOTE: Drop any trailing number off w, h, ax, and ay to pull the primary image’s dimensions and aspect.

Channel (Pixel) Variables c1..c3 r1..r3 g1..g3 b1..b3 a1..a3 z1..z3 cv1..cv3 u1..u3 v1..v3 nx1..nx3 ny1..ny3 nz1..nz3 bgr1..bgr3 bgg1..bgg3 bgb1..bgb3 bga1..bga3 vx1..vx3

Current Channel (for image1..image3) Red (for image1..image3) Green (for image1..image3) Blue (for image1..image3) Alpha (for image1..image3) Z-Buffer (for image1..image3) Z Coverage (for image1..image3) U Coordinate (for image1..image3) V Coordinate (for image1..image3) X Normal (for image1..image3) Y Normal (for image1..image3) Z Normal (for image1..image3) Background Red (for image1..image3) Background Green (for image1..image3) Background Blue (for image1..image3) Background Alpha (for image1..image3) X Vector (for image1..image3)

### Channel (Pixel) Variables vy1..vy3 nz1..nz3

Y Vector (for image1..image3) Z Normal (for image1..image3)

NOTE: Reach for c1, c2, c3 whenever you want a pixel’s value within whichever channel is current. Doing so eases the copying and pasting of expressions. Say you key `c1/2` in as the red expression: the outcome is half the red pixel’s value out of image 1, yet paste that same expression into the blue channel and it now carries the blue channel pixel’s value instead.

For the red value of the current pixel sitting in input 1, key in r1. Where that image sits in input 2, it turns into r2.

- `get[ch][#]b(x, y)` Fetch the pixel at x,y, or 0 when it falls out of bounds—e.g., `getr1b(0,0)`
- `get[ch][#]d(x, y)` Fetch the pixel at x,y, or the edge pixel when out of bounds—e.g., `getr1d(0,0)`
- `get[ch][#]w(x, y)` Fetch the pixel at x,y, or wrap it when out of bounds—e.g., `getr1w(0,0)`

NOTE: Several different approaches exist for pointing at pixels somewhere other than the present one inside an image.

Within the description above, `[ch]` stands as a letter naming the channel you wish to reach. The `[#]` stands as a number naming the input image. Thus, to grab the red component of the current pixel (the same as r), you would reach for `getr1b(x,y)`. And to grab the alpha component of whatever pixel sits dead center in image 2, you would reach for `geta2b(0.5, 0.5)`.

- `getr1b(x,y)` Return the red value belonging to the pixel at position x, y, supposing a valid pixel were there. Should the position fall past the image’s boundaries, it would return 0.0 (all channels).
- `getr1d(x,y)` Return the red value belonging to the pixel at position x, y. Were the named position to land outside the image’s boundaries, the result would be drawn from the image’s outer edge (RGBA only).
- `getr1w(x,y)` Return the red value belonging to the pixel at position x, y. Were the named position to land outside the image’s boundaries, the x and y coordinates would wrap over to the image’s opposite side and carry on from there (RGBA only).

So as to reach other channel values through these functions, swap the r in the examples above for the right channel variable (r, g, b, a and, with the `getr1b()` functions alone, z, and so forth), per the examples above. Swap the 1 for either a 2 or a 3 in those examples so as to reach the images coming from the other image inputs.

### Mathematical Expressions pi

The value of pi

e

The value of e

log(x)

The base-10 log of x

ln(x)

The natural (base-e) log of x

sin(x)

The sine of x (x is degrees)

cos(x)

The cosine of x (x is degrees)

tan(x)

The tangent of x (x is degrees)

asin(x)

The arcsine of x, in degrees

acos(x)

The arccosine of x, in degrees

atan(x)

The arctangent of x, in degrees

atan2(x,y)

The arctangent of x,y, in degrees

abs(x)

The absolute (positive) value of x

int(x)

The integer (whole) value of x

frac(x)

The fractional value of x

sqrt(x)

The Square Root of x

rand(x,y)

A random value between x and y

rands(x,y,s)

A random value between x and y, based on seed s

min(x,y)

The minimum (lowest) of x and y

max(x,y)

The maximum (highest) of x and y

dist(x1,y1,x2,y2)

The distance between point x1,y2 and x2,y2

dist3d(x1,y1,z1,x2,y2,z2) The distance between 3D points x1,y2,z1 and x2,y2,z2

noise(x)

A smoothly varying Perlin noise value based on x

noise2(x, y)

A smoothly varying Perlin noise value based on x and y

noise3(x, y, z)

A smoothly varying Perlin noise value based on x, y and z

if(c, x, y)

returns x if c not 0, otherwise y

Mathematical Operators

```c
!x -x +x
```

1.0 should x = 0, else 0.0 (0.0 - x) (0.0 + x) which, in effect, accomplishes nothing

Mathematical Operators

```c
x^y x*y x/y x%y x+y x-y x<y x>y x <= y x >= y x=y x == y x <> y x != y x&y x && y x|y x||y
```

x raised to the y power x times y x divided by y x taken modulo y, that is, the remainder left over from (x divided by y) x and y added x with y subtracted yields 1.0 should x sit below y, else 0.0 yields 1.0 should x rise above y, else 0.0 yields 1.0 should x be no greater than y, else 0.0 yields 1.0 should x be no less than y, else 0.0 yields 1.0 should x equal y exactly, else 0.0 yields 1.0 should x equal y exactly, else 0.0, the same as the line above yields 1.0 should x differ from y, else 0.0 yields 1.0 should x differ from y, else 0.0, that is, the same as the line above yields 1.0 should neither x nor y be 0.0, else 0.0 yields 1.0 should neither x nor y be 0.0, else 0.0, that is, the same as the line above yields 1.0 should x or y (or each) be something other than 0.0, else 0.0 yields 1.0 should x or y (or each) be something other than 0.0, else 0.0

### Examples

What follows is a set of examples meant to deepen your grasp of the Custom Tool node’s various pieces.

### Rotation

Spinning an image around calls for the standard 2D rotation equations:

```c
x’ = x * cos(theta) - y * sin(theta) y’ = x * sin(theta) + y * cos(theta)
```

Pressing the n1 slider into service for the angle theta, plus a sample function, lands us at this (for the red channel):

```c
getr1b(x * cos(n1) - y * sin(n1), x * sin(n1) + y * cos(n1))
```

What this works out is the current pixel’s (x,y) position turned about the origin at (0,0) (that bottomleft corner), after which it pulls the red component off the source pixel sitting at this turned position.

To rotate about the center, we have to knock 0.5 off our x and y coordinates ahead of the rotation, then tack 0.5 back on once it is done:

```c
getr1b((x-.5) * cos(n1) - (y-.5) * sin(n1) + .5, (x-.5) * sin(n1) + (y.5) * cos(n1) + .5)
```

That ushers in the next lesson: Setup and Intermediate Expressions. They earn their place by hastening things along, since they pare down the work shouldered by the Channel expressions. The Setup expressions fire just one time, and what they yield holds steady across every pixel, so you can press these into service for s1 and s2, in turn:

```c
cos(n1) sin(n1)
```

Intermediate expressions fire once for each pixel, so you can press these into service for i1 and i2:

```c
(x-.5) * s1 - (y-.5) * s2 + .5 (x-.5) * s2 + (y-.5) * s1 + .5
```

These supply the x and y parameters feeding the `getr1b()` function shown earlier, only now with the Setup results, s1 and s2, swapped in so the trig functions fire just once per frame instead of every pixel. From here you can lean on these intermediate results inside your Channel expressions:

```c
getr1b(i1, i2) getg1b(i1, i2) getb1b(i1, i2) geta1b(i1, i2)
```

Once the Intermediate expressions are swapped in, all those additions, subtractions, and multiplications fall to a single pass per pixel rather than four. The rule of thumb runs thus: whatever holds steady, compute it but once. This rotation here is a plain one that pays the image aspect no mind whatever. Folding that in is left to you as an exercise (sorry). One further refinement would be to let the rotation pivot on points other than the center.

### Filtering

This second example of ours reproduces what a 3 x 3 Custom Filter node does once it is set to average the current pixel alongside the eight pixels ringing it. To reproduce that through a Custom Tool node, drop a Custom Tool node onto the node tree, then key the following expressions into the Setup tab. (Keep the node unconnected so it holds off any updating until we are good and ready.)

```c
S1 1.0/w1 S2 1.0/h1
```

This pair of expressions gets worked out as each frame begins. S1 splits 1.0 by the frame’s present width, while S2 splits 1.0 by its height. Out of that comes a floating-point value between 0.0 and 1.0 standing for the span from the current pixel over to the next pixel along each axis.

Now key the following expression into the Channel tab’s first text control (r).

```c
(getr1w(x-s1, y-s2) + getr1w(x, y-s2) + getr1w(x+s1, y-s2) + getr1w(x+s1, y) + getr1w(x-s1, y) + r1 +getr1w(x-s1, y+s2) + getr1w(x, y+s2) + getr1w(x+s1, y+s2)) / 9
```

What this expression does is sum the nine pixels above the current pixel, calling the `getr1w()` function nine times over and handing it values measured against the current position. Take note that we named the pixels through x+s1, y+s2, in place of x+1, y+1. Because Fusion names pixels as floating-point values between 0.0 and 1.0, that is the very reason we built the expressions placed into the Setup tab. Had x+1, y+1 gone in instead, the expression would have kept sampling that one same pixel again and again. (The function we leaned on wraps the pixel position around the image whenever the offset values stray out of range.) With the red channel settled, now turn to the following expressions for the green, blue, and alpha channels.

```c
(getg1w(x-s1, y-s2) + getg1w(x, y-s2) + getg1w(x+s1, y-s2) + getg1w(x+s1, y) + getg1w(x-s1, y) + g1 +getg1w(x-s1, y+s2) + getg1w(x, y+s2) + getg1w(x+s1, y+s2)) / 9
(getb1w(x-s1, y-s2) + getb1w(x, y-s2) + getb1w(x+s1, y-s2) + getb1w(x+s1, y) + getb1w(x-s1, y) + b1 +getb1w(x-s1, y+s2) + getb1w(x, y+s2) + getb1w(x+s1, y+s2)) / 9
(geta1w(x-s1, y-s2) + geta1w(x, y-s2) + geta1w(x+s1, y-s2) + geta1w(x+s1, y) + geta1w(x-s1, y) + a1 + geta1w(x-s1, y+s2) + geta1w(x, y+s2) + geta1w(x+s1, y+s2)) / 9
```

Now the moment has come to look over the results. Drop in a Background node set to a solid color, then shift that color to a pure red. Drop in a hard-edged Rectangular effects mask and wire it to the expression you have just built. By way of contrast, drop in a Custom Filter node and mirror the settings from the image shown above. Run a pipe into this node from the background, then look over the results. Flip back and forth between the Custom Tool node and the Custom Filter, zoomed in tight on the effects mask’s top corners. Granted, the Custom Filter node renders far quicker than the Custom Tool node we put together, yet the real edge of the Custom Tool node lies in its flexibility. As one case, you might take an image wired into input 2 and let it steer the median applied to input one, swapping every instance of getr1w, getg1w, and getb1w throughout the expression for getr2w, getg2w, and getb2w, all while leaving the r1, g1, and b1s untouched. That is but a single case; what the Custom Tool node can do knows no bounds.

### Common Controls

Settings Tab Here again the Inspector’s Settings tab is mirrored across the rest of the miscellaneous nodes. Every one of these shared controls is laid out at length where the chapter ends, inside the “The Common Controls” section.

### Fields [FLDs]

### The Fields node

### Fields Node Introduction
