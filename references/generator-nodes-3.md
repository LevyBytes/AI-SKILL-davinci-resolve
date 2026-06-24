# Generator Nodes (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Extend Horizontal and Extend Vertical (Border only) This slider alters each border's dimensions. Round (Border Fill and Border Outline only) Use this slider to round off the border's corners. Color Types Apart from solid shading, you can also apply a gradient fill or wrap an external image onto the text. This menu decides whether the shading element's color comes from a color or gradient the user picked, or instead from an outside image source. Which controls turn up below depends on the Color Type you've chosen.

- Solid: With the Type menu in Solid mode, color selector controls appear so you can pick the text's color.
- Image: A node's output from the node tree gets used to texture the text. Which node serves is set through the Color Image control that surfaces once this option is picked.
- Gradient: With the Type menu set to Gradient, extra controls appear letting you customize the gradient colors and their direction.

Using the Gradient Color Bar You pick the gradient's colors with the gradient color bar. Its two default color stops fix the start and end colors. To swap the gradient's colors, select a color stop and then set a fresh color via the Eyedropper or the color swatch. The gradient bar lets you add, move, copy, and delete color. To recolor one of them, click the triangle beneath that color on the bar. Adding a color stop onto the gradient bar goes like this: 1 Click any point along the foot of the gradient bar. 2 Lean on the Eyedropper or the color swatch to choose what color that stop takes. Shifting a color stop across the gradient bar: Pull a stop left or right along it. Duplicating a color stop: Keep Command (macOS) or Ctrl (Windows) held down while pulling a stop. Removing a color stop: Pull it up and off past the gradient bar. Image Source (Image Mode only) Three options for getting the image that fills the text live in the Image Source menu.

- Tool: Shows a Color image text field into which you can drop a tool from the node tree as the text's fill.
- Clip: Offers a Browse button for picking a media file off your hard drive as the text's fill.
- Brush: Shows a Color Brush menu from which you can pick one of Fusion's paint brush bitmaps as

the fill for text.

Color Image/Color Brush (Image Mode only) You pick the tool or paint brush that fills the text through the Color Image text box and the Color Brush menu. Within the Color Image text box, type the name of the node tree node that supplies the image. You can key the name in by hand, drag the node out of the node tree into the text box, or right-click and pick Connect To off the contextual menu to choose the image to use. For the Color Brush, pick the Brush off the menu. Image Sampling (Image Mode only) This menu picks the sampling type used for rendering and transforming the shading. The Pixel shading default covers 90% of jobs just fine. To cut visible aliasing in the text, switch the sampling type to Area. That's slower yet can yield finer results. Set it to None and rendering goes faster, but with no extra sampling applied the quality drops. Image Edges (Image Mode only) This menu picks how transformations laid on image shading elements behave when they spill off the text's edges. Shading Mapping (Image Mode only) This menu chooses whether the whole image is stretched to fill the text or scaled to fit—holding the aspect ratio while cropping part of the image as required. Mapping Angle (Image and Gradient Modes only) Rotating the image or gradient around the Z-axis is what this control does. Mapping Size (Image and Gradient Modes only) Scaling the image or gradient is this control's job. Mapping Aspect (Image and Gradient Modes only) Stretching or squeezing the image or gradient up and down falls to this control. Mapping Level (Image and Gradient Modes only) The Mapping Level menu picks how the image gets mapped onto the text.

- Full Image: Applies the entire image to the text.
- Text: Applies the image to fit the entire set of text.
- Line: Applies the image per line of text.
- Word: Applies the image per each word of text.
- Character: Applies the image per individual character.

Softness X and Y How soft the text outline behind the shading element is gets set by these sliders. You control the X- and Y-axis on their own. Apply Softness to Fill Color Tick this checkbox and blur (softness) lands on the shading element. You see the result best on a shading element that draws on an external image. Softness Glow This slider lays a glow over the softened part of the shading element.

Softness Blend How much the softness control's result blends back in with the original is set by this slider. You can use it to ease off the soften operation's outcome. Priority Back/Front Live only when the Sort By menu sits on Priority, this slider overrides the priority setting and fixes the layering order of the shading elements. Slide it rightward to draw an element nearer the front. Push it leftward to slip one shading element behind another. Offset X, Y, and Z These controls lay an offset on the shading elements from the text's global center (the one fixed in the Layout tab). Set X0.0, Y0.1 in the coordinate controls and the shading element lands centered with 10 percent of the image pushed further down the screen along the Y-axis. Positive values on the Z-Offset slider shove the center further from the camera, while positive values draw it nearer the camera. Pivot X, Y, and Z These controls pin down the exact spot of the axis for whichever shading element is chosen. Out of the box the axis sits at the worked-out center of the line, word, or character. The axis control behaves as an offset, so that 0.1, 0.1 here would shove the axis down and to the right for the shading element. Positive values on the Z-axis slider push the rotation axis further along the axis (away from the viewer). Negative values pull the rotation axis nearer. Rotation X, Y, and Z These controls tune the angle of the chosen shading element in any of the three dimensions. Shear X and Y Tune these sliders to alter how the chosen shading element slants along the X and Y axis. Size X and Y Tune these sliders to alter the chosen shading element's size along the X and Y axis.

### Common Controls

Image and Settings Tabs The Inspector's Image and Settings tabs recur across many Generator nodes. These shared controls get a thorough write-up at this chapter's close, in the "The Common Controls" section.

### Text+ Toolbar

Pick the Text node and a toolbar shows up in the viewer. Below, each button is covered from left to right.

### Text+ toolbar

Allow Typing in Viewer Switch this on and you can type and edit text right in the viewer. A click on the text in the viewer drops the insert cursor inside the text. The Left and Right Arrow keys shift the insert cursor across characters. The Up and Down Arrows hop between text lines. Allow Manual Kerning The Manual Kerning button takes over from the automatic kerning text usually gets. A click on the small red handle under any character picks that character for kerning. You can also drag a selection rectangle around whichever characters you'd like to kern. With any characters picked, hold the Option (macOS) or Alt key (Windows) while tapping the Left or Right Arrow key to make tiny tweaks to the chosen characters' kerning. Hold the Alt + Shift (Windows) or Option + Shift (macOS) keys while tapping arrow keys to shift the character in bigger steps. To animate where each character sits, head into the Inspector's Advanced Controls, right-click the Manual Font Kerning control label, and pick Animate off the contextual menu. Each time a character moves, a fresh key lands on the animation spline. Every character is animated off the one spline, just as with polyline mask animation. No Text Outline Switch this button on and it stops any outline being drawn around the text's edges. That outline isn't part of the text; it's an onscreen control there to help mark where the text sits. Treat it as one part of a three-way toggle, its companions being Text Outline Outside Frame Only and Show Always Text Outline. Text Outline Outside Frame Only What this button does is trace a text-edge outline lying past the visible frame. It helps you find text that has drifted offscreen and no longer renders anything visible. Treat it as one part of a three-way toggle, its companions being No Text Outline and Show Always Text Outline. Show Always Text Outline What this button does is trace a text-edge outline regardless of whether the text shows within the frame. Treat it as one part of a three-way toggle, its companions being No Text Outline and Text Outline Outside Frame Only.

### Common Controls

Image and Settings Tabs The Inspector's Image and Settings tabs recur across many Generator nodes. These shared controls get a thorough write-up at this chapter's close, in the "The Common Controls" section.

### Text+ Modifiers

You assign text modifiers by right-clicking inside the Styled Text box and picking a modifier off the contextual menu. With a modifier chosen, its controls turn up in the Modifiers tab at the Inspector's top.

### Text+ modifiers

### Character Level Styling

The Character Level Styling modifier acts on Text+ nodes alone. Once it's applied, you can pick out single characters straight in the viewer and lay different text attributes on them via the Modifiers tab controls. NOTE: Character Level Styling can be applied directly only to Text+ nodes, never to Text 3D nodes. That said, styled text from a Text+ node can land on a Text 3D node by copying the Text+, right-clicking the Text 3D, and choosing Paste Settings.

### Inspector

### Character Level Styling Modifiers tab

### Text Tab

The Modifiers tab's Styled Text box shows the very text held in the Tools tab of the Text+ Inspector. You can't, however, pick the individual characters you want to change inside the Styled Text box; they have to be picked in the viewer. With text picked in the viewer, the Text tab offers the usual text formatting options, which act only on the chosen characters. Clear Character Styling on Selection Every change made to the chosen characters gets reset. Clear All Character Styling Every character attribute returns to its original value. Transform Tab and Shading Tab For the lowdown on these Text+ tabs, see the "Text+" section above.

### Comp Name

Comp Name makes the styled text turn into the current Composition Name. That comes in quite handy for automating burn-ins on daily renderings. See the TimeCode modifier as well. You apply it by right-clicking in a Text+ node's Styled Text field and picking Comp Name.

### Controls

This modifier has no controls.

### Follower

The Follower modifier lets you sequence text animations. You apply the modifier by right-clicking in a Text+ node's Styled Text field and picking Follower. Over in the Modifiers tab, you begin by animating the text's parameters (mind that altering any parameter in the Modifiers tab stays invisible unless a keyframe is added.) Then, in the Timing tab, you set how long the animation waits between characters.

### Inspector

### Follower Timing tab

### Timing Tab

With the text animated via the Modifiers tab controls, the Timing tab serves to pick the animation's direction and offset. Range The Range menu picks whether every character is affected or just a chosen span. To fix the range, you can drag-select across the characters right in the viewer. Order Which direction the characters get affected in is set by the Order menu. Keep in mind that blank spaces count as characters too. The options on hand include:

- Left to right: Across every character, the animation rolls leftward to rightward.
- Right to left: Across every character, the animation rolls rightward to leftward.
- Inside out: The animation ripples symmetrically from the center point of the

characters toward the margin.

- Outside in: The animation ripples symmetrically from the margin toward the center

point of the characters.

- Random but one by one: Picked at random, characters receive the animation, yet it only

influences one character at a time.

- Completely random: The animation is applied to randomly selected characters, influencing

multiple characters at a time.

- Manual curve: The affected characters can be specified by sliders.

Delay Type Sets which kind of delay the animation gets. The options on hand include:

- Between Each Character: The more characters your text holds, the longer the animation runs before finishing. A setting of 1 means character one kicks off the animation, character two follows 1 frame later, character three follows 1 frame after the second, and onward.
- Between First and Last Character: However many characters your text holds, the animation always wraps up within the chosen span of time.

Clear All Character Styling Each character attribute drops back to whatever value it started with.

Text Controls, Alignment, Transform, and Shading Tabs Within these tabs is where the characters' actual animation gets done. Note that merely altering a value in these tabs does nothing at all. For the effect to appear, the value has to be animated. For a full rundown of the various parameters, see the Text+ node documentation.

### Text Scramble

Text Scramble swaps the characters at random for others drawn from a set you define. You apply it by right-clicking into a Text+ node's Styled Text field and picking Text Scramble. The Text Scramble's Controls then get tuned in the Modifiers tab.

### Inspector

### Text Scramble modifier Controls tab

### Controls Tab

The Text Scramble modifier's Controls tab serves to enter text and scramble it via the Randomness control. The scrambled characters come from the Substitute Chars field down at the Inspector's foot. Randomness Sets how many characters get swapped at random. Set 0 and not a single character changes. Set 1 and every character in the text changes. Animate this thumbwheel from 0 to 1 and all the characters get swapped bit by bit. Input Text This mirrors the original text in the Text+ Styled Text field. You can enter text either here or in the Text+ node. Animate on Time Switch this on and the characters get scrambled at random on each new frame. The switch does nothing while Randomness sits at 0. Animate on Randomness Switch this on and the characters get scrambled at random on each new frame whenever the Randomness thumbwheel is animated. The switch does nothing while Randomness sits at 0.

Don't Change Spaces Switch this on and spaces stay unscrambled, so each word keeps its length even as its characters get shuffled around. Substitute Chars This field holds the characters used to scramble the text.

### Text Timer

Text Timer turns the Text+ node into a Countdown, a Timer, or a Clock. That's handy for onscreen real-time displays or for burning a frame's creation time into the picture. You apply it by right-clicking in a Text+ node's Styled Text field and picking Text Timer.

### Inspector

### Text Timer modifier Controls tab

### Controls Tab

The Text Timer modifier's Controls tab serves to set up which kind of time display this modifier turns out. Mode This menu fixes which mode the timer runs in. The choices are CountDown, Timer, and Clock. Under Clock mode, the present system time shows. Hrs, Mins, Secs (Checkboxes) Fixes which parts of the clock should appear onscreen. Hrs, Mins, Secs (Sliders) Fixes the start time for the CountDown and Timer mode. Start Sets the Counter or Timer running. Flips to Stop once the timer is going. Reset Returns the Counter and Timer to the values the sliders set.

### Time Code

Time Code acts on Text+ nodes alone. It makes the Styled text become a counter keyed to the present frame. That comes in quite handy for automating burn-ins on daily renderings. You apply it by right-clicking in a Text+ node's Styled Text field and picking Time Code.

### Inspector

### Time Code modifier Controls tab

### Controls Tab

The Time Code modifier's Controls tab serves to set up the time code display this modifier turns out. Hrs, Mins, Secs, Frms, Flds Switch these options on or off to tailor the time code display so it shows hours, minutes, seconds, frames, and fields, respectively. Switching frames on gives you nothing but a plain frame counter. Start Offset Add a positive or negative offset to Fusion's present time so it lines up with existing time codes. Frames per Second This ought to line up with your composition's FPS setting to give accurate time measurement. Drop Frame Switch this checkbox on to align the time code with footage carrying drop frames—certain NTSC formats, say.

### The Common Controls

Image-generating nodes share several identical controls in the Inspector. This section covers the controls held in common across Generator nodes.

### Inspector

### Background node Image tab

### Image Tab

This tab's controls serve to fix the resolution, color depth, and pixel aspect of the image the node turns out. Process Mode This menu control picks the Fields Processing mode Fusion uses to render changes to the image. The default choice is governed by the Has Fields checkbox control over in the Frame Format preferences. Global In and Out This control fixes where this node sits inside the project. Use Global In to fix which frame starts the clip and Global Out to fix which frame ends the clip (inclusive) inside the project's Global Range. The node turns out no image on frames beyond this range. Use Frame Format Settings Tick this checkbox and the width, height, and pixel aspect of the image the node builds get locked to the values set in the composition's Frame Format preferences. Should the Frame Format preferences shift, the resolution of the node's image shifts to match. Switching this option off can help when you build a composition at a resolution other than the eventual target resolution for the final render.

Width/Height This pair of controls fixes the Width and Height dimensions of the image the node will build. Pixel Aspect This control fixes the Pixel Aspect ratio of the built images. A ratio of 1:1 yields a square pixel matching on every side (like a computer display monitor), while an aspect of 0.9:1 yields a slightly rectangular pixel (like an NTSC monitor). NOTE: Right-click the Width, Height, or Pixel Aspect controls to bring up a menu listing the file formats set in the preferences Frame Format tab. Pick any listed option and the width, height, and pixel aspect snap to that format's values accordingly. Depth The Depth drop-down menu fixes the pixel color depth of the image the Creator node builds. 32-bit pixels eat 4X the memory of 8-bit pixels yet carry far greater color accuracy. Float pixels permit high dynamic range values outside the usual 0…1 range, for showing colors brighter than white or darker than black. Source Color Space The Source Color Space menu lets you set the footage's Color Space to help reach a linear workflow. Unlike the Gamut tool, this performs no actual color space conversion; rather it folds the source space data into the metadata if that metadata is missing. Further down the chain, a Gamut tool set to the From Image option can lean on that metadata, as can a Saver where explicit output spaces have been defined. There are two options to pick from:

- Auto: On its own, reads any metadata the image carries and passes it along.
- Space: Brings up a Color Space Type menu from which you can pick the image's right color

space. Source Gamma Space Through the Curve type menu, you can fix the footage's Gamma Space and choose to strip it via the Remove Curve checkbox while working in a linear workflow. The Curve type menu holds three choices:

- Auto: By itself, reads whatever metadata sits in the image and hands it onward.
- Space: Brings up a Gamma Space Type menu from which you can pick the image's right gamma

curve.

- Log: Brings up the Log/Lin settings, similar to the Cineon tool.

For a fuller account, turn to the DaVinci Resolve Reference Manual's Chapter 99, "Film Nodes," or to the Fusion Reference Manual's Chapter 39. Remove Curve Hinging on the chosen Gamma Space or on whatever Gamma Space Auto mode turns up, the Gamma Curve gets stripped from the material, or a log-lin conversion runs on it, effectively turning it into a linear output space.

### Fast Noise Image Tab Options

The controls below belong to the Image tab in the Fast Noise Node. Mask Map Inputs These outside connections let you use masks to steer the value of the Noise Detail and Brightness controls separately for each pixel. That can open the door to some intriguing, creative effects. Noise Detail Map Wire a soft-edged mask into the Noise Detail Map and you get a flat noise map (zero detail) wherever the mask is black, full detail wherever it's white, and in-between values that smoothly ease off in detail. It takes effect ahead of any gradient color mapping. That can really help when you want maximum noise detail in one spot while it falls off smoothly elsewhere. Noise Brightness Map A mask wired into this input can steer the noise map outright—boosting it in certain spots, blending it with other textures, or, where Detail sits at 0, standing in for the Perlin Noise map entirely.

### Common Generator settings

### Settings Tab

You'll find the Inspector's Settings Tab on every tool in the Color category. The Settings controls even turn up on third-party Color-type plugin tools. They stay consistent and behave the same across each tool, though some tools do throw in one or two individual options, covered here as well. Blend What the Blend control does is mix the tool's starting image input with the tool's finished, altered output image. With a blend value of 0.0, the outgoing image matches the incoming one exactly. As a rule this makes the tool skip processing altogether, copying the input straight across to the output. Process When Blend Is 0.0 The tool gets processed even when the input value is zero. That can help if this node's processing is scripted to set off another task while the node's value is parked at 0.0.
