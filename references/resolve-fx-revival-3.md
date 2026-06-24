# Resolve Fx Revival (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Clone: Just duplicates the source patch onto the target patch. With Clone chosen, the Replacement Detail slider (its default value is 1) lets you dial down the source patch, Region Shape gives you a different shape to apply, and Blur Shape Edges softens this operation's border so the source merges into the target area more believably.
- Blend Clone: A far more refined way to cover the target area with pixels drawn from the source patch, and one that often delivers cleaner results faster than plain cloning. It writes the source patch onto the target patch so that the source's detail fuses with the lighting already present in the target area, which usually yields a quick, invisible match. Tick the Keep Original Detail checkbox and detail from both the source and target patches gets blended into a composite instead of a simple fill. With the Variability slider you control how firm the patch's middle is. The Blur Shape Edges slider behaves a little differently once Blend Clone is active, though its purpose holds, softening the effect inward from its edges to mask any spot where the target area shows an obvious seam.
- Fast Mask: Drops the source patch entirely, swapping in a fast blend of nearby pixels that suits small patches but may reveal a grid-like pattern across bigger ones. You can adjust both Region Shape and Blur Shape Edges.
- Blend Mask: Drops the source patch and basically runs the Blend Clone operation minus the source. It does well on small patches but tends to over-blur once patch sizes grow. It opens up the Variability slider from the Blend Clone.

### Patch Positions

You get Source X and Y, Target X and Y, plus Target Width and Height as direct controls, partly so you can punch in numbers whenever that's called for, and partly so you can keyframe them when the position and/or size of the source and fill patches has to shift across time. Bear in mind the source and target patches will follow motion when tracked through the FX tracker, yet a pair of checkboxes, Source Follows Track and Target Follows Track, let you switch off FX tracker match moving as needed. Pressing the Align Source to Target button drops the source patch right on top of the target patch, a quick way to reset and rework where the source patch sits.

### Onscreen Controls

Through the Control Visibility pop-up menu you decide whether the source and target onscreen controls stay on view while you work. Show, the default, keeps every onscreen control on view at all times. Auto Hide tucks away all onscreen controls the moment you start dragging one, so you can watch the image change as you tweak it without the controls obstructing your view. Hide turns every onscreen control invisible, giving you a clean look at the image plus its effect, though you can still adjust the effect provided you recall where the controls sit.
