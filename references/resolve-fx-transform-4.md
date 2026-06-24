# Resolve Fx Transform (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Shrink Progress: (manual key framing only) When animated, this slider scales a tile anywhere from nothing up to its present size. At a value of 0.000 the tile sits at its largest state. At a value of 1.000 the tile collapses to nothing.
- Rotate Progress: (manual key framing only) When animated, this slider sends a tile flying into or away from the frame. At a value of 0.000 the tile rests in its default grid position. At a value of 1.000 the tile sits completely off screen.
- Fade Progress: (manual key framing only) When animated, this slider sends a tile flying into or away from the frame. At a value of 0.000 the tile rests in its default grid position. At a value of 1.000 the tile sits completely off screen.

### Easing & Blur

You’ll find these controls within Tiles mode. They give you a way to tweak the easing on the tile animation built by the preceding group of controls.

- Motion and Size Ease: This set of controls defines the curve governing simulated momentum as the tiles’ Tile Position and Size keyframes animate. None: No curves get applied. Animation jumps straight from one keyframe to the next. Linear: No easing curves get applied; motion neither speeds up nor slows down. In: The animation curve begins slowly and finishes quickly. Out: The animation curve begins quickly and finishes slowly. In & Out: The animation curve begins slowly, picks up speed midway, and eases off toward the end.
- Animation Effects Ease: This set of controls defines the curve governing simulated momentum as the tiles’ Tile Animation keyframes animate. None: No curves get applied. Animation jumps straight from one keyframe to the next. In: The animation curve begins slowly and finishes quickly. Out: The animation curve begins quickly and finishes slowly. In & Out: The animation curve begins slowly, picks up speed midway, and eases off again toward the end.
- Ease Amount: How strongly the animation curve influences the acceleration and deceleration. The values range from 0.000 to 1.000.
- Motion Blur: This slider governs how much motion blur is layered onto the animation so it reads smoother and more organic. Its scale runs between 0.000, where no motion blur is present, up to 1.000 for the maximum motion blur.

### Global Blend

- Blend: This slider governs the total opacity of the whole Video Collage effect. Its scale runs between 0.000, which is completely transparent, and 1.000, which is completely opaque.
