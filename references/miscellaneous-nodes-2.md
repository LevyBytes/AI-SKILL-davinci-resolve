# Miscellaneous Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

The Fields node is a sturdy all-around tool that bundles a number of operations tied to interlaced video frames. It can interpolate video fields up into frames or break video frames down into fields. Even though the interlace preference and method type gets set in the MediaIn or Loader, and generators, you can lean on this node to help with PAL-to-NTSC standards conversion, and it lets you process fields and frames over particular stretches of a node tree. The node is likewise able to weave two distinct images into one interlace image. Here the background input acts as the dominate field 1 while the foreground stands in as field 2.

### Inputs

The lone input on the Fields node lets you hook up a 2D image plus an effect mask, the latter handy for confining the blurred area. Stream1 Input: This orange background input takes the primary 2D image to be interpolated or converted. Stream2 Input: This optional green foreground input comes into play solely when you’re combining a pair of interlaced images.

### Basic Node Setup

The Fields node shown below takes the background image and turns it from a PAL interlaced format into progressive frames.

You can shift the background image into a range of interlaced formats.

### Inspector

### The Fields Controls tab

### Controls Tab

Two menus sit within the Controls tab. You pick the kind of field conversion to carry out from the Operation menu. The Process Mode menu, meanwhile, sets the field’s format for the resulting output image.

### Operatiion Controls

### Operation Menu

- Do Nothing: Leaves the images to be governed by the Process Mode selection and nothing else.
- Strip Field 2: Drops field 2 out of the input image stream, cutting the image down to half its original height.
- Strip Field 1: Drops field 1 out of the input image stream, cutting the image down to half its original height.
- Strip Field 2 and Interpolate: Drops field 2 from the input image stream and swaps in a field interpolated from field 1, keeping image height intact. Feed it frames rather than fields.
- Strip Field 1 and Interpolate: Drops field 1 from the input image stream and swaps in a field interpolated from field 2, keeping image height intact. Feed it frames rather than fields.
- Interlace: Merges fields drawn from the input image stream(s). Given a single image stream, every pair of frames merges into half as many double-height frames. Given two image streams, one frame from each merges into double-height images.
- De-Interlace: Splits the fields out of one input image stream. The result is twice as many half-height frames.

Reverse Field Dominance Turning this on flips the image’s Field Order or Dominance.

### Process Mode

### Process Mode Menu

- Full Frames: Compels Frame Processing. Handy when you need to process frames within a node tree region that otherwise runs field processing.
- NTSC Fields: Compels NTSC Field Processing. Handy when you need to process fields within a node tree region that otherwise runs frame processing.
- PAL Fields: Compels PAL Field Processing. Handy when you need to process fields within a node tree region that otherwise runs frame processing.
- PAL Fields (Reversed): Compels PAL-swapped Field Processing.
- NTSC Fields (Reversed): Compels NTSC-swapped Field Processing.
- Auto: Tries to mirror the mode of whatever input images arrive. When the input types are a mix, it falls back to Fields.

### Common Controls

Settings Tab You’ll find the Settings tab in the Inspector echoed across the other miscellaneous nodes as well. Full descriptions of these common controls appear later, in this chapter’s closing “The Common Controls” section.

### Frame Average [Avg]

### The Frame Average node

### Frame Average Node Introduction

The Frame Average node blends a run of frames together to mimic footage captured at long shutter speeds. Beyond motion blur-style looks, it can come in handy for time warps or stripping out noise.

### Inputs

The sole input on the Frame Average node is where you attach the 2D image that the averaging gets applied to. Input: The orange input carries the primary 2D image destined for averaging.

### Basic Node Setup

Whatever image feeds the orange input gets frame averaged according to the Inspector settings.

A Frame Average node merges the frames of the input image.

### Inspector

### The Frame Average Controls tab

### Controls Tab

Within the Controls tab live the parameters that govern the span and direction of the averaged frames. Sample Direction The Sample Direction menu decides whether the averaged frames come from before the current frame, after it, or some blend of both.

- Forward: Averages however many frames the Frames slider specifies following the current frame.
- Both: Averages however many frames the Frames slider specifies, drawing frames from both before and after the

current frame.

- Backward: Averages however many frames the Frames slider specifies preceding the current frame. Missing Frames This control sets what happens when a frame is absent from the clip.
- Duplicate Original: Holds on the last original frame until the next frame becomes available.
- Blank Frame: Leaves any missing frames empty. Frames This slider sets how many frames get averaged.

### Keyframe Stretcher [KFS]

### The Keyframe Stretcher node

### Keyframe Stretcher Node Introduction

You place the Keyframe Stretcher node downstream of animated nodes, so that as the comp’s duration changes the keyframes stretch along with it. Its job is to rescale the keyframes on the animation curve to the clip’s current duration. This proves especially valuable when you’re building title templates in Fusion meant for use on DaVinci Resolve’s Edit or Cut page.

TIP: To target just one parameter with the Keyframe Stretcher, apply the Keystretcher modifier.

### Inputs

The lone input on the Keyframe Stretcher node is where you connect a 2D image carrying keyframe animation. Input: The orange input accepts any node bearing keyframed animation. That input might be a Merge node that itself isn’t animated yet holds animated foreground and background nodes.

### Basic Node Setup

Place the Keyframe Stretcher right ahead of the Media Out or Saver node. Every node holding animation upstream of the Keyframe Stretcher gets reshaped whenever the comp’s duration shifts. A Keyframe Stretcher altering the animation across two text nodes. In the diagram below, a 50-frame original animation has been applied to a parameter. You’d set the Keyframe Stretcher Start and End to 0 and 50. Frame 10 holds the second keyframe, and frame 40 holds the third. Putting the Stretch Start at frame 11 and the Stretch End at frame 39 preserves the existing keyframes at their original speed (number of frames.) Everything in the middle then gets stretched.

### Original 50-frame animation

For the example below, the clip’s duration grows to 75 frames. The animation’s opening 10 frames and closing 10 frames keep the same speed as the original, whereas whatever sits in the middle is stretched to take up the extra length. NOTE: Within the Spline Editor itself, only the keyframe positions from the original are displayed. The Keyframe Stretcher leaves the splines untouched; what it alters is purely the animation.

Animation reworked to 75 frames yet only its middle portion stretched Inspector

### The Keyframe Stretcher Keyframes tab

### Keyframes Tab

The Keyframes tab carries Source controls that establish the source duration plus Stretch controls that pin down which region of the animation gets reshaped. Source Start/Source End You define a source range through the Source Start and Source End controls. As a rule these are dialed in to span the entire animation spline on the Keyframes control. Stretch Start/Stretch End With the Stretch Start and Stretch End controls you mark off a central band in which keyframes get stretched or compressed. Handles lying beyond that range escape scaling. Whatever keyframes fall outside the Stretch Start and End range hold a constant frame distance from the Start and End. Any tweak you make to a keyframe on the original control is scaled back onto the source curve accordingly, and it lines up with the original timing just as you’d expect. Stretch Edges Instead Ticking the Stretch Edges Instead checkbox supersedes the Stretch Start and Stretch End controls and instead stretches the animation’s edges.

### Run Command [Run]

### The Run Command node

### Run Command Node Introduction

The Run Command node fires off an external command or batch file at chosen moments throughout a render. A command can be set to run when a render begins or when it ends. Alternatively, you can have it fire once per frame. Among its many uses, the Run Command can net render other command line applications by way of the Fusion Render Manager.

### Inputs

The sole input on the Run Command node simply passes a 2D image through. Input: The optional orange image input isn’t needed for the node to function. That said, when it’s wired to a node‘s output, the Run Command holds off until that connected node finishes rendering before it launches. This often helps when it’s tied to a Saver, guaranteeing the output frame is fully written to disk beforehand. Should the launched application come back with a non-zero result, the node fails too.

### Basic Node Setup

You can wire the Run Command node downstream of a Saver and have it fire as soon as the last frame is done.

Run Command positioned downstream of a Saver node.

### Inspector

### The Run Command Frame tab

### Frame Tab

Within the Frame tab you choose and tweak the command that will execute. Hide Tick the Hide checkbox so the application or script throws up no window as it runs. Wait Tick this checkbox to make the node pause until a remote application or tool exits before it carries on. With this checkbox cleared, the Fusion keeps rendering and doesn’t wait on the external application. Frame Command Here you enter the path for the command meant to run once each frame finishes rendering. You can rely on the Browse button to locate the path. Interactive This checkbox sets whether the launched application runs interactively, accepting user input. Number A (%a) and Number B (%b) A variety of wildcards work with the frame commands; at render time these wildcards get swapped out for the appropriate values.

- %a: Emits the value held in the Number A thumbwheel control.
- %b: Emits the value held in the Number B thumbwheel control.
- %t: Emits the current frame number (with no zero padding).
- %s: Drops in the text taken from the large text entry field.

Should you wish to prepend zero padding to the numbers that %t produces, write the wildcard as %0x, with x standing for how many characters to pad the value to. The same trick applies to %a and %b. As an illustration, test%04t.tga would yield these values come render time: test0000.tga test0001.tga test0009.tga test0010.tga A value can also be padded with spaces by invoking the wildcard as %x, where x is the count of spaces you’d like to pad the value with.

### The Run Command Start tab

### The Run Command End tab

### Start and End Tabs

Each of the Start and End tabs holds a file browser for a command that runs as the composition begins rendering and as the composition wraps up rendering.

### Example

Suppose you want each rendered frame copied off to a different directory as it’s produced; into the root folder, namely C\, place a file named copyfile.bat carrying the text below. @echo off set parm=%1 %2 copy %1 %2 set parm= Build or open any node tree holding a Saver. This example presumes the Saver outputs D\ test0000.exr, test0001.exr, etc. You might need to adjust the example so it lines up. Tack a Run Command node onto the Saver so the Saver wraps up saving first. Now, in the Frame Command text box belonging to the Run Command node, key in: C\copytest.bat D\test%04f.exr C\ Tick the Hide Frame command checkbox so the Command Prompt window doesn’t flash up momentarily after each frame. As this node tree renders, every file gets copied to the C\ directory the instant it’s rendered. You could put the Run Command node to work shipping files over FTP to a remote network drive, printing each frame as it renders, or kicking off a custom imageprocessing tool. Plain batch files aren’t the limit of what the Run Command node can run, either. FusionScript, VBScript, Jscript, CGI, and Perl files are all fair game, to name a handful.

### Common Controls

Settings Tab This same Settings tab within the Inspector recurs on the rest of the miscellaneous nodes too. Detailed coverage of these common controls waits at the chapter’s end, under the “The Common Controls” section.

### Set Domain [DOD]

### The Set Domain node

### Set Domain Node Introduction

Set Domain serves to tweak or define an image’s active region — the part of the image regarded as holding valid data. The image‘s physical dimensions stay untouched. Anything beyond the Domain of Definition (DoD) goes unprocessed by downstream nodes, which speeds up rendering for computation-intensive nodes. The node offers an absolute mode for defining the domain of definition by hand, plus a relative mode for nudging the existing domain of definition.

### Inputs

The pair of inputs on the Set Domain node are where you attach 2D images. Input: The orange background input has to be wired up. It takes a 2D image whose DoD you intend to replace or adjust. Foreground: The green image input is optional yet likewise takes a 2D image. With the foreground input connected, the Set Domain node swaps the Background input’s domain of definition out for the foreground’s DoD.

### Basic Node Setup

The example below presumes an image is wired into a Set Domain node so the DoD can be configured by hand.

A Set Domain node defines, by hand, the region that bounds image processing.

### Inspector

### The Set Domain Controls tab in Set mode

### The Set Domain Controls tab in Adjust mode

### Controls Tab

Mode The Mode menu presents two options, the choice resting on whether you mean to nudge or offset the current domain or instead lock in exact values for it. Either Set or Adjust mode can carry out the same operations. Under Adjust mode, each slider sits at a default of 0, which marks its own full extent of the image. Positive values pull the DoD inward while negative values push the DoD outward to take in more data. Set mode starts out at the full extent of the visible image. By default the sliders run on a 0-1 scale, left to right and bottom to top. Left Sets the DoD’s left edge. Raising this slider drives the left edge rightward, leaving out more data along the left margin. Here 1 stands for the image’s right edge and 0 for its left edge. The slider’s default is 0 (left border). Bottom Sets the DoD’s bottom edge. Raising this slider drives the bottom edge upward, leaving out more data along the bottom margin. Here 1 stands for the image’s top edge and 0 for its bottom edge. The slider’s default is 0 (bottom border). Right Sets the DoD’s right edge. Raising this slider drives the right edge leftward, leaving out more data along the right margin. Here 1 stands for the image’s right edge and 0 for its left edge. Within Set mode, the slider defaults to 1 (right border). Top Sets the DoD’s top edge. Raising this slider drives the top edge downward, leaving out more data along the top margin. Here 1 stands for the image’s top edge and 0 for its bottom edge. Within Set mode, the slider defaults to 1 (top border).

### FUSION 2554

### Common Controls

Settings Tab Here again, the Settings tab in the Inspector shows up on the other miscellaneous nodes as well. These common controls get spelled out fully toward the chapter’s close, in the “The Common Controls” section.

### Switch [Swi]

### The Switch node

### Switch Node Introduction

Switch is a tool that lets artists flip among several input sources, picking a single output from whichever inputs they’ve chosen. That ability is particularly handy for flipping between different visual elements inside a composition. How many input connections there are can vary, since the node accommodates a dynamic count of inputs that you can rename whenever you like. Through controls on the Config tab, users add or drop inputs and edit their names. Most kinds of tools, Shapes and 3D included, work with Switch. On top of that, you’ll spot the Switch modifier under a control’s context menu — in both its Modify With submenu and its Insert submenu — so it can be attached to any supported control.

### Inputs

By means of the slider in the Config tools, you can attach as many as nine inputs to a Switch Node. Need more than nine sources? Just key the figure into the Number of Inputs field by hand.

### Basic Node Setup

Wire however many input sources you want into the Switch Node, then route its output onward into the rest of the node tree.

The Switch tool fed three media inputs, letting you pick a single one to carry on through the transform node

### Inspector

With the Switch Controls you select which source flows through the switch.

### The Switch Configuration

### Controls

The Switch Controls amount to a Source switcher with which you pick which source flows through the switch.

### Config

Through the Switch Configuration you set how many inputs there are and give them new names.

- Number of Inputs: Slide this to bring in as many inputs as you intend to use, up to nine. Should you want beyond nine inputs, click into the number field and type the figure by hand.
- Name X: Swap an input’s name from a plain number to something more telling.

### Time Speed [TSpd]

### The Time Speed node

### Time Speed Node Introduction

With the Time Speed node, image sequences can be quickened, slowed, run in reverse, or held back. Image Interpolation delivers smooth, high-quality output. Reach for Time Speed when you need fixed speed changes or want to add delays into the footage. For animated time changes — ramping time up or down, say — turn to a Time Stretcher instead. Running in Flow mode calls for Optical Flow data. This node won’t produce optical flow on its own. You’ll need to make it upstream with an Optical Flow node, or by pulling in the forward/reverse vector channels from the image. TimeSpeed leaves the aux channels uninterpolated and wipes them out instead. The Vector/ BackVector channels in particular are consumed and destroyed once computation finishes. Drop an Optical Flow downstream of the Time Speed node when you want flow vectors generated for the retimed footage.

### Inputs

The lone input on the Time Speed node is where the 2D image to be retimed gets connected. Input: The orange input carries the primary 2D image that’s going to be retimed.

### Basic Node Setup

Setting up the Time Speed node is no harder than feeding a 2D image into the node’s orange background input.

A MediaIn node whose speed is being altered within the Time Speed node.

### Inspector

### The Time Speed Controls tab

Speed With this control you set the Speed, expressed as percentages, of the outgoing image sequence. Negative values play the image sequence backward. A value of 2.0 equals 200% Speed, 1.0 equals 100%, 0.5 equals 50%, and 0.1 equals 10%. You cannot animate the Speed control. Delay Reach for this control to Delay the outgoing image sequence by however many frames you name. Negative numbers shift time backward, while positive numbers push it forward. Interpolate Mode This menu governs how the time speed gets processed to lift its visual playback quality, most of all on clips that have been slowed down. The menu holds three choices.

- Nearest: The most processor efficient yet least refined approach; frames are simply dropped for fast motion or repeated for slow motion.
- Blend: Likewise processor efficient, though capable of smoother output; neighboring duplicated frames dissolve into one another to even out slow or fast motion effects.
- Flow: The most processor intensive but top-quality way of producing speed effects. Drawing on vector channels pre-generated by an Optical Flow node, fresh frames are synthesized to build slow or fast motion effects. Output can turn out remarkably smooth where a clip’s motion is linear. That said, two moving elements crossing in opposite directions, or erratic camera movement, can throw up unwanted artifacts.

Sample Spread This slider appears solely when Interpolation is set to Blend. It governs how strongly the interpolated frames weigh on the current frame. At a value of 0.5, the blend draws 50% from the frame before, 50% from the frame ahead, and 0% from the current frame. Depth Ordering This menu appears solely when Interpolation is set to Flow. Depth Ordering decides which portions of the image render on top. An example makes it clearest. Take a locked-off camera shot with a car moving through the frame: the background stays put, so it yields small, slow vectors. The car yields larger, faster vectors. Depth Ordering here is Fastest on Top, since the car paints over the background. Now in a shot where the camera pans along with the car, the background carries faster vectors and the car carries slower ones, so the Depth ordering method becomes Slowest on Top. Clamp Edges This checkbox appears solely when Interpolation is set to Flow. In some situations, this option clears away the transparent gaps that can crop up along the edges of interpolated frames. Clamp Edges may bring on a stretching artifact near the frame edges, most noticeable when objects pass through them or the camera moves. Owing to these artifacts, reserve clamp edges for patching only the slim gaps that ring an interpolated frame’s borders. Edge Softness This slider shows up only when Interpolation is set to Flow and Clamp Edges is on. It works to tame the stretchy artifacts that Clamp Edges might bring in. Should you switch on two or more of the Source Frame and Warp Direction checkboxes, the edge stretching can compound on itself. In that event, keep the softness fairly low, around 0.01. With just one checkbox on, a larger softness near 0.03 is fine. Source Frame and Warp Direction These checkboxes appear solely when Interpolation is set to Flow. The controls dictate which frames and which vectors go into building the in-between frames. Whichever method you tick on gets blended into the result.

- Prev Forward: Grabs the previous frame and leans on the Forward vector to interpolate the new frame.
- Next Forward: Grabs the sequence’s next frame and leans on the Forward vector to interpolate the new frame.
- Prev Backward: Grabs the previous frame and leans on the Back Forward vector to interpolate the new frame.
- Next Backward: Grabs the sequence’s next frame and leans on the Back vector to interpolate the new frame.

Freeze Frame A press of this button automatically sets the Speed and Delay controls so playback freezes on the frame you’ve got selected.

### Common Controls

Settings Tab Once more, the Inspector’s Settings tab is mirrored across the remaining miscellaneous nodes. You’ll find these common controls laid out in full at the chapter’s end, within the “The Common Controls” section.

### Time Stretcher [TST]

### The Time Stretcher node

### Time Stretcher Node Introduction

The Time Stretcher node resembles the Time Speed node, except it lets the clip’s speed be animated. You get full spline control over the effect, smoothing included. Thanks to that, the Time Stretcher can animate a single clip up to 200, back to normal speed, hold for a second, then run backward (much like a VCR rewinding). Image interpolation yields smooth, high-quality output, all by way of a spline curve that adjusts time nonlinearly. For steady time changes such as frame rate changes, go with a Time Speed instead. Running in Flow mode demands Optical Flow data; the node generates no optical flow on its own, so you must build it by hand upstream using an Optical Flow node or by reading the forward/ reverse vector channels off disk. Time Stretcher doesn’t interpolate the aux channels and destroys them instead. The Vector/BackVector channels especially are consumed/destroyed. Place an Optical Flow downstream of the Time Stretcher when you want flow vectors generated for the retimed footage.

### Inputs
