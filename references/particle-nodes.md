# Particle Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Particle Nodes

This chapter walks through the Particle nodes on offer in Fusion.

Each node name carries an abbreviation beside it that serves in the Select Tool dialog while you hunt for tools and within scripting references. Throughout this document, treat node trees that show MediaIn nodes in DaVinci Resolve as equivalent to Loader nodes in Fusion Studio, except where a note says otherwise.

You reach for the Particle nodes to spawn a great many duplicated objects that animate on their own. They serve to build elements such as falling rain, fireworks, smoke, pixie dust, and a whole lot besides. The possibilities run on without end. In Fusion, particles amount to a set of nodes chained together for spawning, reshaping, and rendering particles within a 2D or 3D scene. As a starting point, each particle system you build has to hold two fundamental nodes:

- pEmitter: Spawns the particles and governs their basic look, motion. and behavior.
- pRender: Turns the pEmitter's output into a rendered 2D or 3D scene. When creating

particles, you only ever view the pRender node.

Whatever particle nodes are left reshape the pEmitter results to mimic natural phenomena such as gravity, flocking, and bounce. Every particle node's name opens with a lowercase p, setting them apart from non-particle nodes. You'll find them in the particles category within the Effects Library.

### pAvoid [pAv]

The pAvoid node pAvoid Node Introduction You reach for the pAvoid node to carve out a region or area inside the image that affected particles try to keep from entering and crossing. Two primary controls govern it. The first fixes how far from the region a particle ought to be before it starts drifting away from the region. The second fixes how firmly the particle drifts away from the region. What a pAvoid node plants in a particle is a “desire” to drift away from a specific region. Where the velocity of the particle outweighs the combined distance and strength of the pAvoid region, the particle’s urge to steer clear of the region fails to beat its momentum, and the particle crosses that region all the same.

### Inputs

By default the pAvoid node carries a single orange input. As with most particle nodes, only other particle nodes feed this orange input. Set the Region tab's Region menu to Bitmap or Mesh and a green bitmap or mesh input then surfaces on the node. Input: Fed by the output of other particle nodes is the orange input. Region: A 2D image or a 3D mesh is what the green or magenta region input takes, hinging on whether the Region menu reads Bitmap or Mesh. Which color the input wears comes down to whichever you pick first in the menu. The area particles avoid is set by the 3D mesh or a selectable channel out of the bitmap.

### Basic Node Setup

The pAvoid node slots in between the pEmitter and pRender. A Shape 3D node serves to carve out the region the particles will avoid.

A pAvoid node leaning on a Shape 3D node to mark out the region to steer clear of Inspector

### The pAvoid controls

Randomize The Random Seed slider plus the Randomize button turn up any time a Fusion node leans on a random result. A pair of nodes sharing the same seed values will turn out the same random results. Press the Randomize button to draw a fresh seed value at random, or work the slider to settle a fresh seed value by hand. Distance Fixes how far from the region a particle ought to be before it starts drifting away from the region. Strength Fixes how firmly the particle drifts away from the region. Negative values drive the particles toward the region instead.

### Common Controls

Conditions, Style, Region, and Settings Tabs These four tabs turn up on every Particle node alike, so a full account of them waits in the “The Common Controls” section at this chapter’s close.

### pBounce [pBn]

The pBounce node pBounce Node Introduction You reach for the pBounce tool to carve out a region off which affected particles will bounce the moment they touch it.

### Inputs

By default the pBounce node carries a single orange input. As with most particle nodes, nothing but other particle nodes feeds this orange input. Dial the Region tab's Region menu over to Bitmap or Mesh and a green or magenta bitmap or mesh input then appears on the node. Input: What the orange input draws in is the output of other particle nodes. Region: Depending on whether that Region menu reads Bitmap or Mesh, the green or magenta region input accepts a 2D image or a 3D mesh. Which color the input wears comes down to whichever you pick first in the menu. The area particles bounce off is set by the 3D mesh or a selectable channel out of the bitmap.

### Basic Node Setup

The pBounce node slots in between the pEmitter and pRender. A Shape 3D node serves to carve out the region the particles bounce off.

A pBounce node leaning on a Shape 3D node to set the region off which particles rebound

### Inspector

### The pBounce controls

Randomize The Random Seed slider plus the Randomize button turn up any time a Fusion node leans on a random result. A pair of nodes sharing the same seed values will turn out the same random results. Press the Randomize button to draw a fresh seed value at random, or work the slider to settle a fresh seed value by hand. Elasticity Elasticity bears on the strength of a bounce, that is, how much velocity the particle keeps after striking the Bounce region. A value of 1.0 leaves the particle carrying the same velocity after the bounce as it brought entering the bounce. A value of 0.1 strips the particle of 90% of its velocity as it bounces off the region. This control runs from 0.0 to 1.0 by default, yet larger values can be typed in by hand. That makes the particles pick up momentum after an impact rather than shed it. Negative values get accepted but yield no useful result. Variance By default, particles that hit the Bounce region reflect evenly off the edge of the Bounce region, going by the vector or angle of the region. Pushing the Variance past 0.0 brings a measure of variation into that angle of reflection. You can lean on this to fake the effect of a rougher surface. Spin By default, particles that hit the region come away with their angle or orientation untouched. Raising or lowering the Spin value makes the Bounce region hand the particle a spin keyed to the angle of collision, or alters whatever spin the particle already carries. Positive values hand over a forward spin, while negative values hand over a backward spin. The bigger the value, the quicker the spin laid on the particle. Roughness This slider varies the bounce off the surface to nudge particle direction a touch at random. Surface Motion This slider makes the bounce surface act as though it carried motion, thereby bearing on the particles. Surface Motion Direction This thumbwheel control fixes the angle relative to the bounce surface.

### Common Controls

Conditions, Style, Region, and Settings Tabs Each of these four tabs is common to all the Particle nodes, which is why their write-up lives in the “The Common Controls” section ending this chapter.

### pChangeStyle [pCS]

The pChange Style node pChange Style Node Introduction The pChange Style node hands you a means of shifting the appearance or style of particles that meet a defined region. Its primary controls echo those sitting in the Style tab of the pEmitter node. Particles that cross into or enter the defined region shift according to the parameters of this node. Save for the pCustom node, this stands as the only node that reworks the particles’ appearance rather than its motion. It often serves to set off a shift in appearance in answer to some event, such as hitting a barrier.

### Inputs

By default the pChange Style node carries a single orange input. As with most particle nodes, only fellow particle nodes feed this orange input. Once the Region tab's Region menu gets set to Bitmap or Mesh, a green or magenta bitmap or mesh input then turns up on the node. Input: The output of other particle nodes is what arrives at the orange input. Region: Whether that Region menu is set to Bitmap or Mesh decides if the green or magenta region input accepts a 2D image or a 3D mesh. Which color the input wears comes down to whichever you pick first in the menu. The area where the custom particle node takes effect is set by the 3D mesh or a selectable channel out of the bitmap.

### Basic Node Setup

Counter to what you might expect, to bring about a style change that looks like the work of some physical event, the pChange Style node ought to sit ahead of the node that brings about the event. Take the case below, where the particles spawned by the Emitter node shift style after bouncing off a pBounce. The pChange Style and pBounce both lean on the same Shape 3D node as the region. The pChange Style has to sit ahead of the pBounce. Place the pChange Style node after the pBounce and the particles bounce off the region before the pChange Style works out its effect. The particle never gets the chance to cross into the pChange Style node’s region, so the style never shifts.

A pChange Style node placed before the pBounce node Inspector

### The pChange Style controls

Randomize The Random Seed slider plus the Randomize button turn up any time a Fusion node leans on a random result. A pair of nodes sharing the same seed values will turn out the same random results. Press the Randomize button to draw a fresh seed value at random, or work the slider to settle a fresh seed value by hand. Change Sets Through this option the user can shift the particle’s Set so it falls under the sway of forces apart from the original particle. Turn to “The Common Controls” in this chapter to read more about Sets. Style Through this option the user can shift the particle’s Style and thereby the look. Turn to “The Common Controls” in this chapter to read more about Styles.

### Common Controls

Conditions, Style, Region, and Settings Tabs Every Particle node shares this same set of four tabs, so you’ll find them detailed within the “The Common Controls” section that closes the chapter.

### pCustom [pCu]

The pCustom node pCustom Node Introduction You reach for the pCustom node to write custom expressions that bear on the properties of particles. This node parallels the Custom node, except that the calculations bear on particles rather than pixels.

### Inputs

The pCustom node carries three inputs. As with most particle nodes, only fellow particle nodes feed this orange input. For custom image calculations there are the green and magenta inputs, both of them 2D image inputs. Optionally, teal or white bitmap or mesh inputs appear on the node the moment the Region tab's Region menu gets set to Bitmap or Mesh. Input: Arriving at the orange input is the output of other particle nodes. Image 1 and 2: 2D images come in through the green and magenta image inputs, where they drive per pixel calculations and compositing functions. Region: A 2D image or a 3D mesh reaches the teal or white region input, hinging on whether that Region menu reads Bitmap or Mesh. Which color the input wears comes down to whichever you pick first in the menu. The area where the custom particle node takes effect is set by the 3D mesh or a selectable channel out of the bitmap.

### Basic Node Setup

The pCustom node slots in between the pEmitter and pRender. A Shape 3D node serves to carve out the region where the Custom particle event occurs.

A pCustom node leaning on a Shape 3D node to mark the region where the custom event plays out

### Inspector

Every one of the operators, functions, and conditional statements laid out for the Custom node carries over to the pCustom node as well, Pixel-read functions for the two image inputs included (getr1w(x,y), getz2b(x,y), and the rest).

### The pCustom controls

Number 1-8 Numbers are variables fitted with a dial control that can be animated or wired to modifiers exactly as any other control could. Within particle equations the numbers can stand in either for the current moment as n1, n2, n3, n4, … or for an arbitrary moment as n1_at(float t), n2_at(float t), n3_at(float t), n4_at(float t), with t standing for whichever time you mean. These controls' values lie open to expressions in the Setup and Intermediate tabs.

pCustom Position tab

### Position 1-8

These eight point controls carry 3D X,Y,Z position controls. They behave as ordinary positional controls and can be animated or wired to modifiers as any other node could. They lie open to expressions typed in the Setup, Intermediate, and Channels tabs.

pCustom Setup tab Setup 1-8 As many as eight separate expressions can be worked out in the Setup tab of the pCustom node. The Setup expressions get evaluated once per frame, ahead of any other calculations. Their results then become reachable, as the variables s1, s2, s3, and s4, by the node's remaining expressions. Picture them as global setup scripts that the intermediate and channel scripts can call on.

pCustom Intermediate tab

### Inter 1-8

A further eight expressions can be worked out in the Intermediate tab. The Intermediate expressions get evaluated once per frame, after the Setup expressions get evaluated. Results lie open as variables i1, i2, i3, i4, i5, i6, i7, i8, which channel scripts can call on.

Particle Particle position, velocity, rotation, and the rest of the controls live in the Particle tab. The particle properties below are laid open to the pCustom control:

px, py, pz vx, vy, vz rx, ry, rz sx, sy, sz pxi1, pyi1 pxi2, pyi2 mass size id r, g, b, a rgnhit rgndist condscale rgnix, rgniy, rgniz rgnnx, rgnny, rgnnz w1, h1 w2 h2 i1, i2, i3, i4 s1, s2, s3, s4 n1..n8 p1x, p1y, p1z .. p4x, p4y, p4z time age lifespan

a particle's position along the x, y, and z axis a particle's velocity along the x, y and z axis a particle's rotation along the x, y, and z axis a particle's spin along the x, y, and z axis a particle's 2d position, adjusted for image 1’s aspect a particle's 2d position, adjusted for image 2’s aspect nothing makes use of this right now a particle's present size the identifier of the particle the red, green, blue and alpha color values of the particles this value reads 1 where the particle struck the pCustom node’s defined region this variable holds how far the particle lies from the region how strong the region is at the particle’s position values marking where on the region the particle struck the region's surface normal at the spot the particle struck it the width and height of image 1 the width and height of image 2 the outcome of the intermediate calculations 1 through 4 the outcome of the setup calculations 1 through 4 whatever numeric inputs 1 through 8 hold whatever position inputs 1 through 4 hold the composition's frame or time as it stands now how old the particle is right now the lifespan of the current particle

### Common Controls

Conditions, Style, Region, and Settings Tabs This quartet of tabs recurs across all Particle nodes, and a description of each sits in the “The Common Controls” section near the chapter’s end.

### pCustomForce [pCF]

The pCustom Force node pCustom Force Node Introduction Through the pCustom Force node you can alter the forces brought to bear on a particle system or subset. This node ranks among the most intricate and the most potent node in Fusion. Anyone at home with scripting or C++ programming ought to find the structure and terminology the Custom Force node uses familiar. A particle's forces within a system can see their positions and rotations swayed by forces. The position in XYZ along with the Torque, which is the spin of the particle, fall under independent custom equations. You reach for the Custom Force node to write custom expressions and filters that rework the behavior. On top of supplying three image inputs, this node opens the door to wiring up as many as eight numeric inputs plus as many as four XY position values out of other controls and parameters in the node tree.

### Inputs

The pCustom Force node carries three inputs. As with most particle nodes, nothing other than fellow particle nodes feeds this orange input. Serving custom image calculations, a green and magenta stand as 2D image inputs. Optionally, teal or white bitmap or mesh inputs surface on the node the instant the Region tab's Region menu is set to Bitmap or Mesh. Input: Reaching the orange input is the output of other particle nodes. Image 1 and 2: Through the green and magenta image inputs come 2D images, which then power per-pixel calculations and compositing functions. Region: A 2D image or a 3D mesh lands at the teal or white region input, hinging on whether that Region menu reads Bitmap or Mesh. Which color the input wears comes down to whichever you pick first in the menu. The area where the pCustom Force takes effect is set by the 3D mesh or a selectable channel out of the bitmap.

### Basic Node Setup

The pCustom Force node drops in between a pEmitter and pRender node to act as a catalyst for particles by way of advanced C++ and scripting.

A pCustom Force is applied to the particles generated by the pEmitter.

### Inspector

### The pCustom Force controls

The tabs and controls sitting in the Inspector resemble the controls found on the pCustom node. Turn to the pCustom node in this chapter for more information.

### Common Controls

Conditions, Style, Region, and Settings Tabs All Particle nodes carry these four tabs in common, so their explanation is gathered in the “The Common Controls” section toward the end of this chapter.

### pDirectionalForce [pDF]

The pDirectional Force node pDirectional Force Node Introduction This node brings a unidirectional force to bear that tugs the affected particles in a named direction. Its primary controls govern how strong the force is, plus the pull's angle along each of the X, Y, and Z axis. Because the everyday use of this node is faking gravity, by default the pull heads downward on the Y axis (-90 degrees), while the default behavior skips over regions and acts on every particle.

### Inputs

By default the pDirectional Force node carries a single orange input. As with most particle nodes, only fellow particle nodes feed this orange input. Set the Region tab's Region menu to Bitmap or Mesh and a green or magenta bitmap or mesh input then appears on the node.

Input: The output of other particle nodes is what the orange input draws in. Region: A 2D image or a 3D mesh is accepted at the green or magenta region input, decided by whether that Region menu reads Bitmap or Mesh. Which color the input wears comes down to whichever you pick first in the menu. The area where the directional force takes effect is set by the 3D mesh or a selectable channel out of the bitmap.

### Basic Node Setup

The pDirectional Force node slots in between the pEmitter and pRender and often serves to build gravity.

A pDirectional Force node placed between the pEmitter and pRender nodes Inspector

### The pDirectional Force controls

Randomize The Random Seed slider plus the Randomize button turn up any time a Fusion node leans on a random result. A pair of nodes sharing the same seed values will turn out the same random results. Press the Randomize button to settle a fresh seed value at random, or work the slider to settle a fresh seed value by hand. Strength Fixes the power of the force. Positive values drive the particles in the direction the controls set; negative values drive the particles the opposite way. Direction Fixes the direction in X/Y space. Direction Z Fixes the direction in Z space.

### Common Controls

Conditions, Style, Region, and Settings Tabs Held in common by every Particle node, these four tabs get their coverage in the “The Common Controls” section wrapping up this chapter.

### pEmitter [pEm]

The pEmitter node pEmitter Node Introduction The pEmitter node stands as the chief source of particles (pImage Emitter is another) and will as a rule be the first node put to work in any fresh particle system. This node holds controls for fixing the initial position, orientation, and motion of the particles, plus controls for the visual style of each particle. Like every other Particle node (the pRender node aside), the pEmitter turns out a particle set, not a visible image, and so cannot be shown straight in a viewer. To view the output of a particle system, drop a pRender node in after the pEmitter.

### Inputs

By default the pEmitter node holds no inputs whatsoever. You can switch an image input on by picking Bitmap off the Style menu in the Style tab. As well, set the Region tab's Region menu to Bitmap or Mesh and two region inputs then appear on the node, one for bitmap and one for mesh. These inputs' colors shift according to the order in which they get switched on. Style Bitmap Input: This image input takes a 2D image to serve as the particles’ image. Since this image multiplies into potentially thousands of particles, it's wise to keep these images small and square—say, 256 x 256 pixels. Region: The region inputs take a 2D image or a 3D mesh according to whether you set the Region menu to Bitmap or Mesh. Which color the input wears comes down to whichever you pick first in the menu. The area where the particles are emitted is set by the 3D mesh or a selectable channel out of the bitmap.

### Basic Node Setup

The pEmitter node opens the branch of a particle system that always closes with a pRender node. The pEmitter can run straight into a pRender node to feed other particle nodes.

Wiring a pEmitter node into a pRender node makes for the usual arrangement behind most particle systems.

### Inspector

The pEmitter inspector splits into four main tabs plus a common settings tab. The controls tab is the first one shown, and it holds settings touching the general setup of the particle cells the node emits. These settings bear no direct effect on the appearance of the cells or shape of the emitter region. They rework fundamental behaviors such as quantity, duration, speed, and rotation of the particle cells.

### The pEmitter controls

Randomize and Random Seed The Random Seed slider serves to seed every variance and random number generator the node draws on while building the particle system. Two pEmitter nodes carrying exactly the same settings across all controls and the same random seed will spawn exactly the same particle system. Shifting the random seed brings variation between the nodes. Press the Randomize button to set a randomly chosen value for the Random Seed on its own. Number This control serves to fix the count of new particles spawned on each frame. A value of 1 would spawn one new particle each frame. Come frame 10, a total of 10 particles would be in existence (unless Particle Lifespan sat at fewer than 10 frames). Animate this parameter to name the count of particles spawned in total. Say only 25 particles in total are wanted; animate the control to put out five particles on frame 0–4, then drop a key on frame five to spawn zero particles across the rest of the project. Number Variance This reworks the count of particles spawned for each frame as named by the Number control. Say Number sits at 10.0 and Number Variance sits at 2.0; the emitter will then put out anywhere from 9-11 particles per frame. Where the value of Number Variance runs more than twice as large as the value of Number, it's possible no particles get spawned for a given frame.
