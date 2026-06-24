# Mask Nodes (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

This tab’s controls govern both the resolution and the clipping approach applied to the mask that gets generated. Output Size The Output size menu determines the resolution at which the mask node renders. Its three choices are the comp’s default resolution, the resolution coming from the source input on nodes that accept an input, or a resolution you define yourself. Custom Picking Custom from the Output Size menu ties the new mask’s width, height, and pixel aspect to whatever the composition’s Frame Format preferences specify. Should those Frame Format preferences be altered, the mask’s resolution shifts to follow. Turning this option off comes in handy when you want to assemble a composition at a resolution that differs from the final render’s intended target.

- Width and Height: Together these two controls define the Width and Height that the mask being created will have.
- Pixel Aspect: With this control you state the Pixel Aspect ratio for the mask you are making. Choosing 1:1 yields a square pixel measuring the same on each side (as on a computer monitor), whereas 0.91 produces a mildly rectangular pixel (as on an NTSC monitor).
- Depth: Use the Depth drop-down menu to choose the pixel color depth of the mask’s output image. Although 32-bit pixels consume four times as much memory as 8-bit pixels, they deliver considerably more precision. Float pixels permit high dynamic range numbers beyond the usual 0..1 range, letting you describe colors lighter than white or deeper than black.

NOTE: A right-click on the Width, Height, or Pixel Aspect controls brings up a menu of the file formats configured under the preferences Frame Format tab. Choosing one of those entries applies that format’s width, height, and pixel aspect values.

Clipping Mode This setting controls the way edges are treated during domain of definition rendering. The Clipping mode matters most once blur or softness enters the picture, since those may need to sample regions of the image that lie beyond the current domain.

- Frame: Frame is the default, and it makes the node’s domain of definition span the entire frame of the image, in effect disregarding the current domain of definition. Where the upstream DoD falls short of the frame, whatever frame area is left over is rendered as black/transparent.
- None: Choosing None skips clipping of the source image altogether. Whatever data the node’s effect needs that would normally sit beyond the upstream DoD is rendered as black/transparent.

### Common Mask Settings controls

### Settings Tab

Every tool in the Mask category carries the Settings tab inside the Inspector, and even third-party plugin tools expose these Settings controls. They stay uniform and behave identically from tool to tool, though a handful of tools add one or two unique options, which this section addresses as well.

### Motion Blur

- Motion Blur: This switch turns the tool’s Motion Blur rendering on or off. Switched on, it draws on the tool’s predicted motion to generate the blur produced by the virtual camera’s shutter; switched off, no blur at all is generated.
- Quality: Quality sets how many samples go into building the blur. With a setting of 2 in place, Fusion lays down two samples on each side of an object’s true motion. Higher figures smooth the result further but lengthen render time.
- Shutter Angle: Shutter Angle dictates the angle of the virtual shutter behind the motion blur. Wider angles add blur while extending render times, and a value of 360 matches keeping the shutter open across one entire frame exposure. You may go above that for unusual effects.
- Center Bias: Center Bias shifts where the middle of the motion blur sits, making motion-trail looks achievable.
- Sample Spread: Tweaking this control alters how much weight each sample carries, which changes how bright the samples appear.

Use GPU This menu offers three choices. Picking Disable shuts off hardware-accelerated rendering that relies on your computer’s graphics card. Enabled draws on that hardware, while Auto taps a capable GPU whenever one exists and otherwise drops back to software rendering. Comments Into the Comments field you can attach notes for a tool: click the blank field and type your text. Once a note exists, a tiny red square shows in the node’s lower-left corner while the full tile is visible, or a little text-bubble icon shows on the right once the nodes are collapsed. Hovering the pointer over the node in the Node Editor brings up the tooltip so you can read the note. Scripts From the Settings tab, every Fusion tool exposes three Scripting fields. Each is an edit box where you place scripts that run while the tool renders. The Fusion scripting documentation covers node scripting in greater depth.
