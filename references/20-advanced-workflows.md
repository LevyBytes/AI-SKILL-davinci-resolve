# Workflow Integrations, Creating Dctl Luts, Tcp Protocol For Davinci Resolve Transport Control

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

## Overview

Topics in this file: Advanced Workflows; Workflow Integrations; Creating DCTL LUTs; and the TCP Protocol for DaVinci Resolve Transport Control.

## Advanced Workflows

### Advanced Workflows

## Workflow Integrations

### Workflow Integrations

The third party Workflow Integration plugins and Codec plugins available for DaVinci Resolve are documented in this chapter.

### DaVinci Resolve Renderer Plugin for OFX VFX Applications (Studio Version Only)

With the Open FX plugin called DaVinci Resolve Renderer, outside applications gain the ability to load and apply the color adjustments from DaVinci Resolve through exported DRX stills. In effect, your DaVinci Resolve Studio installation becomes a single sizable OFX plugin. The benefit shows up clearly during round trips with assorted VFX authoring tools, in situations where preserving the precise look you built inside DaVinci Resolve matters. A DRX still carries far richer grade data than a plain LUT would. Among the things a DRX file may hold are the full set of native color and sizing palettes plus any other elements saved in a Gallery still. As a result, whatever grade the colorist produced gets reproduced precisely within the VFX software. At the time of writing, these attributes WILL transfer via the DaVinci Resolve OFX Renderer Plugin:

- All native color palettes (Primaries, HDR, Curves etc.).
- All native sizing palettes (Input, Output, Node etc.).
- Most Resolve FX.
- Most third-party Open FX.

At the time of writing, these attributes WILL NOT transfer via the DaVinci Resolve OFX Renderer Plugin:

- Resolve and Open FX that are temporal based.
- Magic Mask.

How to configure the DaVinci Resolve OFX Renderer Plugin: 1 During the DaVinci Resolve Studio setup, pick Custom Install and tick the plugin checkbox within the program installer.

Pick Custom Install, and tick DaVinci Resolve Open FX Renderer so the plugin gets installed

2 Build a grade on a clip within the Color page, and then store a still into the Gallery. From within the Gallery, export out a .DRX file. 3 Over in the outside application, apply the DaVinci Resolve Renderer plugin at the spot that suits your composition.

Inserting the DaVinci Resolve Renderer OFX into a Nuke node tree 4 Inside the DaVinci Resolve Renderer plugin running in your application, pick the .DRX file you exported by browsing the file browser. Within the plugin, choose the .DRX file that you had exported out of DaVinci Resolve. Most Open FX-capable VFX software should handle the Color Grade Plugin fine, including Autodesk Flame as well as The Foundry’s Nuke.

In the image, the DaVinci Resolve Renderer OFX Plugin sits inside Nuke (below) and presents a balanced grade carrying green and orange Power Windows drawn from several nodes within DaVinci Resolve (above). IMPORTANT: Running the plugin requires that a DaVinci Resolve Studio license be present on whatever machine hosts the outside application.

### Workflow Integrations in DaVinci Resolve (Studio Version Only)

Through scripting languages, outside parties can build their own bespoke interface plugins for DaVinci Resolve. That capability enables DaVinci Resolve to talk directly to other software titles across a range of purposes. Several Integration plugins may run together simultaneously. Once installed, you turn plugins on inside DaVinci Resolve by heading to Workspace > Workflow Integrations and picking your plugin out of the dropdown menu.

### Creating Workflow Integration Plugins

Anyone can author their own Workflow Integration Plugin (which is an Electron app) by using the Resolve Javascript’s API together with Python or Lua scripts. To learn the details of building a Workflow Integration Plugin, head to Help > Documentation > Developer and open the Workflow Integrations folder, where the technical notes and sample code live.

### Workflow Integration Plugins

A number of Media Asset Management (MAM) systems are now reachable straight from inside DaVinci Resolve by way of the Workflow Integration Plugins.

### EditShare

A workflow integration plugin built by EditShare lets DaVinci Resolve connect straight to their FLOW media management system. Through this plugin you can add comments, run searches, and preview media inside FLOW while staying within DaVinci Resolve. On top of that, you can push up revisions, handle proxy media, and keep full metadata support intact across the whole workflow.

### EditShare’s FLOW Integration Plugin

To learn more about this plugin, and about the way FLOW operates together with DaVinci Resolve, visit: editshare.com/say-hello-to-flow-and-davinci-resolve-studio/

### Studio Network Solutions (SNS)

The ShareBrowser Integration Plugin, built by Studio Network Solutions (SNS), bridges DaVinci Resolve with their ShareBrowser media asset management software that ships alongside SNS EVO media servers. With this plugin your group can search, tag, preview, comment on, organize, and bring in media while never stepping outside the DaVinci Resolve interface. Media can be imported straight into a DaVinci Resolve project by your team, and whatever metadata you typed travels along with the media.

### SNS ShareBrowser Integration Plugin

To learn more about this plugin, and about the way SNS’s high-speed server or cloud offerings operate together with DaVinci Resolve, visit: www.studionetworksolutions.com.

### Codec Plugins (Studio Version Only)

By using Codec plugins, outside parties can add fresh codecs for encoding within the Deliver page that the core DaVinci Resolve software does not currently handle. That capability makes room for highly specialized deliverables which would otherwise demand trips through several separate programs to produce.

### MainConcept

Using the MainConcept Codec Plugin, you can output your DaVinci Resolve Studio timelines across an assortment of fresh codecs:

- AS-11 UK SD plus AS-11 UK HD, bundled with an XML metadata file, so you can produce AS-11 UK DPP compliant content.
- MainConcept’s software HEVC Main and Main 10 profiles, allowing H.265 files in 8-bit/10-bit 4:2:0/4:2:2 at up to 8K resolution.
- The MXF and MP4 formats from MainConcept, which permit encoding into the camera-native formats of Sony XAVC/XDCAM and the Panasonic P2 AVC-based cameras.

More details about the MainConcept Codec Plugin for DaVinci Resolve are available here: www.mainconcept.com/blackmagic-plugins

The MainConcept Codec Plugin for DaVinci Resolve options in the Deliver page

## Creating DCTL LUTs

### Creating DCTL LUTs

How you build DCTL LUTs to run your own bespoke mathematical transforms inside DaVinci Resolve is the subject of this chapter.

### About DCTL

A DCTL file is in fact a color transformation script that DaVinci Resolve recognizes and applies the same way it would any LUT. Whereas other LUTs are 1D or 3D lookup tables whose values approximate image transforms by interpolation, a DCTL file instead consists of actual computer code that transforms images directly through whatever combination of math functions you assemble. On top of that, because a DCTL file executes natively on your workstation’s GPU, it can run quickly. Making and installing a DCTL is open to anyone who has the math background for it. You just type your transformation code in a syntax resembling C (more detail follows below) into any text editor that can save a plain ASCII text file, then make certain the filename ends in “.dctl” (DaVinci Color Transform Language). With that finished, relocate the file into your workstation’s LUT directory. Its location varies according to your OS: On Mac OS X: `Library/Application Support/Blackmagic Design/DaVinci Resolve/LUT/` On Windows: `C:\ProgramData\Blackmagic Design\DaVinci Resolve\Support\LUT` On Linux: `/home/resolve/LUT` Provided your .dctl syntax is valid, the entries show up the moment DaVinci Resolve launches, inside the Color page Node contextual menu under the DaVinci CTL submenu.

### DCTL Syntax

Every function you author has to be prefixed with `__DEVICE__`. As an illustration:

```c
__DEVICE__ float2 DoSomething()
```

Place the primary entry function (transform) following every other function, and give it this format argument:

```c
__DEVICE__ float3 transform(float p_R, float p_G, float p_B)
```

A float3 return value is also mandatory for the primary entry function. When you want these floating point math functions, apply the syntax shown:

```c
float _fabs(float) float _powf(float x, float y float _logf(float) float _log2f(float) float _log10f(float) float _exp2f(float) float _expf(float) float _copysignf(float x, float y) float _fmaxf(float x, float y) float _fminf(float x, float y) float _saturatef(float x, float minVal, float maxVal) float _sqrtf(float)
```

```c
// Absolute Value // Compute x to the power of y // Natural logarithm // Base 2 logarithm // Base 10 logarithm // Exponential base 2 // Exponential base E // Return x with sign changed to sign y // Return y if x < y // Return y if x > y // Return min(max(x, minVal), maxVal) // Square root
```

```c
int _ceil(float
```

```c
// Round to integer toward + infinity
```

```c
int _floor(float)
```

```c
// Round to integer toward - infinity
```

```c
float _fmod(float x, float y)
```

```c
// Modulus. Returns x – y * trunc(x / y)
```

```c
float _fremainder(float x, float y) // Floating point remainder
```

```c
int _round(float x)
```

```c
// Integral value nearest to x rounding
```

```c
float _hypotf(float x, float y)
```

```c
// Square root of (x^2 + y^2)
```

```c
float _atan2f(float x)
```

```c
// Arc tangent of (y / x)
```

```c
float _sinf(float x)
```

```c
// Sine
```

```c
float _cosf(float x)
```

```c
// Cosine
```

```c
float _acosf(float x)
```

```c
// Arc cosine
```

```c
float _asinf(float x)
```

```c
// Arc sine
```

```c
float _fdivide(float x, float y)
```

```c
// Return (x / y)
```

```c
float _frecip(float x)
```

```c
// Return (1 / x)
```

These functions accept an integer type: `min, max, abs, rotate`. Additional supported C Math functions are: `acosh, acospi, asinh, asinpi, atan, atanh, atanpi, atan2pi, cbrt, cosh, cospi, exp10, expm1, trunc, fdim, fma, lgamma, log1p, logb, rint, round, rsqrt, sincos, sinh, sinpi, tan, tanh, tanpi, tgamma`. The vector types `float2`, `float3`, and `float4` all work. Their data fields are: `float x float y float z float w`. To build a vector value, call `make_floatN()` where N = 2, 3, or 4. You can also declare your own structure with “typedef struct.” As an illustration:

```c
typedef struct { float c00, c01, c02; float c10, c11, c12; } Matrix;
```

When declaring constant memory, apply `__CONSTANT__`. As an illustration:

```c
__CONSTANT__ float NORM[] = {1.0f / 3.0f, 1.0f / 3.0f, 1.0f / 3.0f};
```

To hand the constant memory over as a function argument, use the `__CONSTANTREF__` qualifier, for instance:

```c
__DEVICE__ float DoSomething(__CONSTANTREF__ float* p_Params)
```

Every float value has to end with the ‘f’ character (for example `1.2f`).

### A Simple DCT LUT Example

This code below illustrates how a basic color gain transform can be built with the DCT LUT syntax.

```c
// Example to demonstrate simple color gain transformation __DEVICE__ float3 transform(float p_R, float p_G, float p_B) { const float r = p_R * 1.2f; const float g = p_G * 1.1f; const float b = p_B * 1.2f; return make_float3(r, g, b); }
```

### A Matrix DCT LUT Example

This code below illustrates the construction of a matrix transform via the DCT LUT syntax.

```c
// Example to demonstrate the usage of user defined matrix type to transform RGB to YUV in Rec. 709 __CONSTANT__ float RGBToYUVMat[9] = { 0.2126f , 0.7152f , 0.0722f, -0.09991f, -0.33609f, 0.436f, 0.615f , -0.55861f, -0.05639f }; __DEVICE__ float3 transform(int p_Width, int p_Height, int p_X, int p_Y, float p_R, float p_G, float p_B) { float3 result; result.x = RGBToYUVMat[0] * p_R + RGBToYUVMat[1] * p_G + RGBToYUVMat[2] * p _B; result.y = RGBToYUVMat[3] * p_R + RGBToYUVMat[4] * p_G + RGBToYUVMat[5] * p _B; result.z = RGBToYUVMat[6] * p_R + RGBToYUVMat[7] * p_G + RGBToYUVMat[8] * p _B; return result; }
```

### A More Complex DCT LUT Example

This code below illustrates the construction of a mirror effect, demonstrating the way pixels can be reached spatially.

```c
// Example of spatial access for mirror effect __DEVICE__ float3 transform(int p_Width, int p_Height, int p_X, int p_Y, __ TEXTURE__ p_TexR, __TEXTURE__ p_TexG, __TEXTURE__ p_TexB) { const bool isMirror = (p_X < (p_Width / 2)); const float r = (isMirror) ? _tex2D(p_TexR, p_X, p_Y) : _tex2D(p_TexR, p_ Width - 1 - p_X, p_Y); const float g = (isMirror) ? _tex2D(p_TexG, p_X, p_Y) : _tex2D(p_TexG, p_ Width - 1 - p_X, p_Y); const float b = (isMirror) ? _tex2D(p_TexB, p_X, p_Y) : _tex2D(p_TexB, p_ Width - 1 - p_X, p_Y); return make_float3(r, g, b); }
```

## TCP Protocol for DaVinci Resolve Transport Control

### TCP Protocol for DaVinci Resolve Transport Control

Building outside utilities that drive Transport Control through DaVinci Resolve is what this chapter explains.

### About the TCP Protocol Version 1.2

The communication standard between outside applications (“Client”) and DaVinci Resolve (“Server”) over the TCP protocol is set out by this protocol. The server uses port number 9060. This protocol does not employ SSL. Exchanges happen as request-response messages, in which the Client kicks off a command and the Server answers as appropriate. Before you can use this protocol, you first have to enter the string below into the Advanced panel of the DaVinci Resolve System Preferences: `System.Remote.Control = 1`

### Data Types

This protocol makes use of the following data types:

- float (f): A 4-byte IEEE 754 single precision float
- int (i): A 4-bytes signed int
- unsigned char (uc): A 1-byte unsigned char (0–255)
- string (s): A UTF-8 encoded string. There is no terminator defined for it. This string forms a composite

type, sent as one int (i) that gives the count of characters in the string (N), trailed by N unsigned chars (uc) that hold the string’s letters.

NOTE: The float and int types have their bytes sent over in little endian order.

### Command Format

A command goes out as a single string (limited to characters a–z (0x61 – 0x7A)), trailed by whatever extra payload the command’s definition calls for.

### Response Format

Any command’s response is made up of a status byte (unsigned char), trailed by whatever extra payload the response calls for.

### Communication Delays

After the command string’s first byte goes out, the remainder of the command string plus the payload data has to come along without delay. When COMMAND finishes, the server has to answer right away. Should this process stall for over 5 seconds, whichever party is awaiting data may drop the connection, taking it that the peer has stopped responding. At present no cap exists on how long the gap between two successive commands can be.

NOTE: As an alternative, a maximum allowable delay can be set, in which event the client may fire periodic ‘connect’ commands to hold the connection open.

### Status Response Values

Here is what the status values signify:

- 0x00: Command was executed successfully. Any additional payload is sent as expected.
- 0xFF: Command could not be executed successfully. No additional payload will follow.

### TCP Protocol Stream

These are the commands you can transmit across the protocol stream.

### connect

To begin the stream, the client transmits a connect command string. No payload accompanies it. A status value of 0x00 comes back from the server.

### goto

The client transmits a goto command string trailed by four unsigned chars that stand for the timecode’s hour, minute, second, and frame. The server returns a fitting status byte reflecting how the command ran.

### play

The client transmits a play command string trailed by a floating point value. Real-time playback is 1.0, a stop is 0.0, reverse is -1.0, 2x is 2.0, and so on. The server returns a fitting status byte reflecting how the command ran.

### gettc

The client transmits a gettc command string. The server returns a fitting status byte (for example, the status byte can be 0xFF when no timeline is present). When the status byte reads 0x00, four unsigned chars follow that stand for the timecode’s hour, minute, second, and frame.

### getframerate

The client transmits a getframerate command string. The server returns a fitting status byte. When the status byte reads 0x00, a floating point value for the frame rate follows.
