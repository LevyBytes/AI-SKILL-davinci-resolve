# Resolve Fx Refine (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

The Relight node tree holds a pair of Relight nodes, the first named Surface Map and the second named Relight. The RGB output coming off the Magic Mask routes into the upper RGB inputs on each of those nodes. On top of that, the Magic Mask’s Alpha output runs into the Relight node. Wired this way, the Relight effect touches only the model we isolated with the Magic Mask while the backdrop stays untouched.

Within that first node (Surface Map), the Surface Map option is set to Use Internal. We also tick the Output Surface Map checkbox so the map it builds reaches the second node (Relight). To finish wiring it up, drag the Surface node’s RGB output into the lower RGB input on the Relight node. Over in the Relight node, switch the Surface Map option inside the Inspector to Use Input 2.

The surface map produced by the Surface Map node With the node tree wired up properly, the Surface Map gets built inside its own node; confirm that node cache is switched to On for it. From there you can operate right in the Relight node and pick a Directional light. The Relighting Map Preview checkbox together with the on-screen controls reveals precisely where the lighting lands and how it traces the contours of your subject. While the Relighting Map Preview box stays ticked, you get a clear read on where and how the Relight reshapes the subject. Clear that box and the finished color result comes into view instead. All that remains is to dial in the fresh light qualities themselves, so working the Primaries Wheels controls inside the Relight effect, we push the gain up, tint it toward a faint yellow/orange, and raise the saturation to fake a golden-hour shaft of light striking our subject in place of the flat, overcast scene we started with.

Working the Primaries gain and saturation wheels within the Relight node to lend the light its character, convincing the eye that the model is bent over the fence and caught in a sunbeam.
