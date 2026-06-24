# Particle Nodes (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Lifespan This control sets how many frames a particle lasts before it vanishes or 'dies.' Its default sits at 100 frames, though you may dial in any value. Plenty of other particle controls time themselves against the particle's Lifespan. As an example, you can have a particle's size grow across the final 80% of its life, by way of the Size Over Life graph on the pEmitter's Style tab. Lifespan Variance Much like Number Variance, the Lifespan Variance control lets you tweak the Lifespan of the particles being produced. Set Particle Lifespan to 100 frames and the Lifespan Variance to 20 frames, and the emitter's particles would run a lifespan of 90–110 frames. Color This lets you state where each particle pulls its color from. By default it sits at Use Style Color, which colors each particle per the settings on the pEmitter node's Style tab. The other choice, Use Color From Region, overrides the Style tab's color settings and instead takes its color from the underlying bitmap region. Use Color From Region only holds meaning when the pEmitter region is set to draw on a bitmap built by another node in the composition. Particles born in any region that isn't a bitmap region come out white once Use Color From Region is picked. Position Variance This control decides whether particles may be 'born' beyond the edges of the pEmitter region. Its value defaults to zero, which pens the birth area for new particles to the exact edges of the defined region. Push this control above 0.0 and a particle can be born a little past that region's edges. The larger the value, the 'softer' the region's edge grows. Temporal Distribution Ordinarily an effect gets processed once per frame, off the comp frame rate. Yet handling certain particles only at the precise frame boundaries can bring on pulsing. For subtly more lifelike behavior, particles can instead be birthed in subframe steps. The default At The Same Time setting renders on frame boundaries, whereas the remaining two settings lean on sub frame rendering. Randomly Distributed jitters birth times by +/- about the frame number — for example, birthing 10 particles one at a time at random sub times like 24.1 24.85, 24.21, 24.37 etc. As for Evenly Distributed, it births particles at uniform sub times — say, 10 particles, one apiece, at 24.0, 24.1, 24.2, 24.3, 24.4, 24.5 ... 24.8, 24.9. The Sub Frame Accuracy setting on the pRender node shapes these settings. How many in-between frames get computed between each frame is governed by the Sub Frame Accuracy slider. A larger value sharpens the particle calculation but stretches the render times.

### Velocity

The controls under the Velocity section govern the speed and heading of the particle cells as they spill from the emitter region. Velocity and Velocity Variance These fix the starting speed, or velocity, of fresh particles. By default a particle carries no velocity and stays put at its origin until some outside force acts on it. Set velocity to 10.0 and the particle clears the whole width of the image in a single step, so a velocity of 1.0 would have the particle traverse the image's width across 10 frames.

Velocity Variance shifts each particle's velocity at birth, the same way laid out for Lifespan Variance and Number Variance above. Inherit Inherit Velocity hands the emitter region's velocity down to the particles. This slider spans a broad range covering both negative and positive values. A negative value sends the particles off in the opposite direction, a value of 1 has the particles travel at a velocity equal to the emitter region's velocity, and a value of 2 pushes the particles out ahead of the emitter region. Angle and Angle Variance This fixes the angle that velocity-bearing particles head off at upon birth. Angle Z and Angle Z Variance Same as above, save that this control fixes the particles' angle along the Z space axis (toward or away from the camera).

### Rotation

Rotation controls serve to set the orientation of particle cells and to animate that orientation across time. Rotation Mode Through this menu control sit two options that help settle the orientation of the emitted particles. With spherical particles, this control's effect goes unseen.

- Absolute Rotation: The particles take whatever orientation the Rotation controls dictate, no matter their velocity and heading.
- Rotation Relative To Motion: The particles face the way the particle travels. From there the Rotation controls can turn the particle's orientation off of its heading.

Rotation XYZ and Rotation XYZ Variance These controls open up Rotation of the individual particles. That comes in especially handy with a bitmap particle type, since the incoming bitmap might not face the direction you want. Through Rotation XYZ Variance you can randomly nudge the rotation by a set amount around the center of the Rotation XYZ value, sparing you a batch where every particle faces the exact same way.

### Spin

Spin controls are auto-animated controls that shift the orientation of particle cells across time. Spin XYZ and Spin Variance These hand a spin to each particle at birth. A particle turns 'x' degrees per frame, as fixed by the Spin XYZ value. The Spin XYZ variances shift how much rotation lands on each frame, in the manner spelled out by Number Variance and Lifespan Variance covered above.

### Sets Tab

The settings on this tab bear on the physics of the particles the node emits. They have no direct say over how the particles look. What they shape instead is behavior such as velocity, spin, quantity, and lifespan.

### The pEmitter Sets tab

Set 1-32 To file the particles a pEmitter makes into a given set, just tick the checkbox of the set number you'd like to assign. One pEmitter node may belong to a single set or to several. Once they're assigned within the pEmitter, you can switch sets on in other particle nodes so those nodes touch only particles from particular pEmitters.

### Style Tab

How the particles look is governed by the controls on the Style tab. For a thorough rundown of the Style tab, turn to the "The Common Controls" section closing out this chapter.

### The pEmitter Style tab

### Region Tab

The Region tab steers the shape, size, and placement of the zone that emits the particle cells. People often call this the Emitter. A single pEmitter node admits only one emitter region. With the pRender set to 2D, the emitter region spills particles across a flat plane in Z Space. A 3D emitter region carries depth and can spill particles throughout a user-defined, three-dimensional zone. For fuller detail on the Region tab, turn to the "The Common Controls" section closing out this chapter.

### Common Controls

Conditions, Style, Region, and Settings Tabs Every Particle node shares the Conditions, Style, Region, and Settings tabs, so you'll find them described in the "The Common Controls" section that closes this chapter.

### pFlock [pFl]

The pFlock node pFlock Node Introduction You can call on the pFlock node to mimic how organic systems behave, like a flock of birds or a colony of ants. Putting it to work can lend an otherwise mindless particle system the look of something motivated, as though it acts under some guiding intelligence. Two basic principles drive the pFlock node. Every particle tries to hug the other particles, and every particle tries to keep a minimum gap from the others. How strongly these "desires" pull yields the seemingly purposeful behavior the viewer reads.

### Inputs

By default the pFlock node carries one orange input. As with most particle nodes, this orange input takes only other particle nodes. A green or magenta bitmap or mesh input shows up on the node once you switch the Region menu on the Region tab to either Bitmap or Mesh. Input: Output from other particle nodes feeds the orange background input. Region: Into the green or magenta region input goes a 2D image or a 3D mesh, hinging on whether the Region menu reads Bitmap or Mesh. Whichever option you pick first in the menu decides the input's color. Where the flocking takes hold is set by the 3D mesh or by a selectable channel off the bitmap.

### Basic Node Setup

Paired with pFollow, the pFlock node can generate natural swarming behaviors that shift direction.

A pFlock node lending more herd-type mentality to particles Inspector

### The pFlock controls

Randomize Any time a Fusion node leans on a random result, you'll see the Random Seed slider and Randomize button. A pair of nodes carrying matching seed values turns out matching random results. Hit the Randomize button to draw a new seed value at random, or work the slider to set one by hand. Flock Number This control's value stands for how many other particles the affected particle will try to trail. The larger the value, the more obvious the "clumping" across the particle system and the bigger the particle groups grow. Follow Strength This value stands for how strongly each particle wants to trail the others. Larger values make the particle look like it spends more energy and effort chasing the others. Smaller values raise the odds that a given particle peels off from the pack. Attract Strength This value stands for the pull between particles. Once a particle drifts farther from the others than the Maximum Space set in the pFlock node, it will try to close back in. Larger values have the particle guard its spacing energetically, settling spacing conflicts faster.

Repel Strength This value stands for the force put on particles that crowd nearer than the gap set by the pFlock node's Minimum Space control. Larger values drive particles away from their neighbors faster, firing them off from the pack. Minimum/Maximum Space This range control stands for the gap each particle tries to hold between itself and the others. Particles will try to sit no nearer and no farther than the gap set by this range control's Minimum/Maximum values. Tighter ranges read as more orderly motion. Wider ranges come across as disorderly and chaotic.

### Common Controls

Conditions, Style, Region, and Settings Tabs Since every Particle node holds the Conditions, Style, Region, and Settings tabs in common, their write-ups live in the "The Common Controls" section that closes this chapter.

### pFollow [pFo]

The pFollow node pFollow Node Introduction Dropping the pFollow node into a particle branch sets the particles springing back and forth toward a follow object. You can place that follow object in 3D or animate it to carve a fresh motion path for the particles.

### Inputs

By default the pFollow node carries one orange input. As with most particle nodes, this orange background input takes only other particle nodes. A green bitmap or mesh input shows up on the node once you switch the Region menu on the Region tab to either Bitmap or Mesh. Input: Output from other particle nodes feeds the orange input. Region: Into the green or magenta region input goes a 2D image or a 3D mesh, hinging on whether the Region menu reads Bitmap or Mesh. Whichever option you pick first in the menu decides the input's color. Where the particles trail the position point is set by the 3D mesh or by a selectable channel off the bitmap.

### Basic Node Setup

Paired with pFlock, the pFollow node can generate natural swarming behaviors that shift direction.

A pFollow node brings in a follow object that sways the particles' motion.

### Inspector

### The pFollow Controls tab

Random Seed Any time a Fusion node leans on a random result, you'll see the Random Seed slider and Randomize button. A pair of nodes carrying matching seed values turns out matching random results. Hit the Randomize button to draw a new seed value at random, or work the slider to set one by hand. Position XYZ The position controls serve to carve the new path by placing the follow object. Shifting the XYZ parameters reveals the onscreen position of the follow object. Animating those parameters carves the new path that will sway the particles. Spring The Spring setting sets the particles moving back and forth along the path. The reach of that spring motion widens over the particles' life according to the gap between the particles and the follow object. Larger spring settings boost the elasticity, while smaller ones cut it back. Dampen This value tames the spring action. A smaller setting puts up less resistance to the back-and-forth spring action. A larger setting puts up more.

### Common Controls

Conditions, Style, Region, and Settings Tabs Because all Particle nodes carry the Conditions, Style, Region, and Settings tabs alike, you'll find their descriptions in the "The Common Controls" section wrapping up this chapter.

### pFriction [pFr]

The pFriction node pFriction Node Introduction The pFriction node lays resistance on a particle's motion, dragging the particle's movement as it passes through a defined region. The node turns out two kinds of Friction. One kind cuts the velocity of any particle that intersects/crosses the defined region, and the other cuts or wipes out spin and rotation.

### Inputs

By default the pFriction node carries one orange input. As with most particle nodes, this orange input takes only other particle nodes. A green or magenta bitmap or mesh input shows up on the node once you switch the Region menu on the Region tab to either Bitmap or Mesh. Input: Output from other particle nodes feeds the orange input. Region: Into the green or magenta region input goes a 2D image or a 3D mesh, hinging on whether the Region menu reads Bitmap or Mesh. Whichever option you pick first in the menu decides the input's color. Where the friction happens is set by the 3D mesh or by a selectable channel off the bitmap.

### Basic Node Setup

The pFriction node sits between the pEmitter and pRender. A Shape 3D node serves to build the region the particles rebound from.

A pFriction node leaning on a Shape 3D node as the region where friction meets the particles.

### Inspector

### The pFriction controls

Random Seed Any time a Fusion node leans on a random result, you'll see the Random Seed slider and Randomize button. A pair of nodes carrying matching seed values turns out matching random results. Hit the Randomize button to draw a new seed value at random, or work the slider to set one by hand. Velocity Friction This value stands for the Friction force laid on the particle's Velocity. The bigger the value, the heavier the friction, and so the more the particle slows. Spin Friction This value stands for the Friction force laid on the particle's Rotation or Spin. The bigger the value, the heavier the friction, and so the more the particle's rotation slows.

### Common Controls

Conditions, Style, Region, and Settings Tabs Every Particle node, without exception, carries these four tabs in common, so look for their descriptions in the "The Common Controls" section at this chapter's end.

### pGradientForce [pGF]

The pGradient Force node pGradient Force Node Introduction A force born of the gradients in the input image's alpha values acts on the particles. Particles pick up speed along the gradient, traveling from white toward black (high values toward low values). You can lean on this node to give particles the look of rolling downhill or tracing the contour of a supplied shape.

### Inputs

The pGradient Force node takes two inputs: the default orange input off a particle node, plus one off a bitmap image bearing an alpha channel gradient. A magenta or teal bitmap or mesh input shows up on the node once you switch the Region menu on the Region tab to either Bitmap or Mesh. Input: Output from other particle nodes feeds the orange input. Input: Into the green input goes the 2D image holding the alpha channel gradient. Region: Into the magenta or teal region input goes a 2D image or a 3D mesh, hinging on whether the Region menu reads Bitmap or Mesh. Whichever option you pick first in the menu decides the input's color. Where the gradient force happens is set by the 3D mesh or by a selectable channel off the bitmap.

### Basic Node Setup

The pGradient Force node sits between the pEmitter and pRender nodes. A Fast Noise node serves to build the alpha gradient that shifts the particles' velocity. A pGradient Force node leaning on a Fast Noise node as the gradient that reshapes the particles' motion Inspector

### The pGradient Force controls

Randomize Any time a Fusion node leans on a random result, you'll see the Random Seed slider and Randomize button. A pair of nodes carrying matching seed values turns out matching random results. Hit the Randomize button to draw a new seed value at random, or work the slider to set one by hand. Strength Gradient Force carries just one control of its own, which governs how strong the force and acceleration laid on the particles are. Negative values here flip the Gradient Force so it runs from black toward white (low values toward high values).

### Common Controls

Conditions, Style, Region, and Settings Tabs Every Particle node shares the Conditions, Style, Region, and Settings tabs, so their write-ups can be found in the "The Common Controls" section closing this chapter.

### pImage Emitter [pIE]

The pImage Emitter node pImage Emitter Node Introduction Feeding an input image to the pImage Emitter node, it handles each of that image's pixels as though it were a particle. What chiefly sets the pImage Emitter apart from the ordinary pEmitter is that, rather than scattering particles at random inside a given region, this node lays pixels out on a regular 2D grid, coloring them off the input image.

### Inputs

The pImage Emitter node carries three inputs. As with most particle nodes, the orange input takes only other particle nodes. For custom image calculations, the green and magenta inputs serve as 2D image inputs. There may also be teal or white bitmap or mesh inputs, surfacing on the node once the Region menu on the Region tab is set to Bitmap or Mesh. Input: In a departure from most other particle nodes, the pImage Emitter's orange input accepts a 2D image that acts as the emitter of the particles. Where a region is defined for the emitter, this input sets the particles' color. Style Bitmap Input: This image input takes a 2D image to serve as the particles' image. Because that image can multiply into thousands of particles, holding these images small and square works best—say, around 256 x 256 pixels. Region: Into the teal or white region input goes a 2D image or a 3D mesh, hinging on whether the Region menu reads Bitmap or Mesh. Whichever option you pick first in the menu decides the input's color. Where the particles are emitted is set by the 3D mesh or by a selectable channel off the bitmap.

### Basic Node Setup

The pImage Emitter node sits at the head of a particle branch, taking the place a pEmitter node would hold. Below, a MediaIn node serves to emit particles using the clip's colors.

A pImage Emitter node emits particles off an image wired into the orange input.

### Inspector

### The pImage Emitter controls

The overwhelming bulk of this node's controls match those on the pEmitter, and you'll find them documented back in that earlier section. Below you'll find write-ups for the controls that belong to the pImage Emitter node alone. X and Y Density Through the X and Y Density sliders you set how particles map onto pixels along each axis. They govern how dense the sampling grid is. A value of 1.0 on either slider means 1 sample for every pixel. Smaller values yield a looser, more pointillistic spread of particles, while values past 1.0 spawn several particles per pixel across the image. Alpha Threshold The Alpha Threshold serves to rein in particle generation so that pixels carrying semitransparent alpha values won't spawn particles. You can lean on it to firm up the edges of an otherwise soft alpha channel. The larger the threshold value, the more opaque a pixel has to be before it spawns a particle. Note that the default threshold of 0.0 spawns particles for every pixel no matter its alpha, though many may sit transparent and unseen. Lock Particle Color to Initial Frame Tick this checkbox to make the particles hold the color they were born with across the particle's whole life. Leave it off, and as the input image shifts over successive frames, the particles will recolor to track the image. That permits video playback across a grid of particles. Create Particles Every Frame Switch this on and a whole fresh set of particles spawns every frame, rather than just one set on the frame. That can balloon into very large particle systems but opens the door to some intriguing effects—for instance, when the particles get some starting velocity or when emitting off an animated source. Try a small velocity, an

Angle Z of -90, and a seething Fast Noise as the source to land smoothly shifting clouds of particles you could fly through. Note that with this checkbox left off, only a single set of particles ever spawns, so animating any of the emitter's other controls does nothing. X/Y/Z Pivot These controls let you place the grid of emitted particles. Use Z Channel for Particle Z Where the input image driving the particles carries a Z depth channel, that channel can set the particle's starting position in Z space. That can yield an intriguing hollow shell effect when paired with camera rotation on the pRender node.

### Sets Tab

### The pImage Emitter Sets tab

NOTE: A pixel with a black (transparent) alpha channel still spawns invisible particles, unless you push the Alpha Threshold past 0.0. Doing so can drag rendering down badly. An Alpha Threshold value of 1/255 = 0.004 works well for clearing out every fully transparent pixel. The pixels go out on a fixed-size 2D grid across the XY plane, centered on the Pivot position. Switching the Region off its All default lets you pen particle creation to tighter areas. Should you need to resize this grid, drop a Transform 3D node after the pRender. Bear in mind that the various emitter controls touch particles only as they're emitted. That is, they fix the particle's starting state and leave it untouched for the rest of its lifespan. Since pImageEmitter, by default, lets particles out on the first frame alone, nothing comes of animating these controls. Turn the Create Particles Every Frame checkbox on, though, and fresh particles get emitted each frame, taking the stated starting settings for that frame.

### Common Controls

Conditions, Style, Region, and Settings Tabs All Particle nodes share these four tabs alike, so their descriptions sit in the "The Common Controls" section that ends this chapter.

### pKill [pKI]

The pKill node pKill Node Introduction The Kill node exists to destroy (kill) any particle that crosses or intersects its region. It carries no controls of its own, since it has just one possible effect on a particle. The controls on the Region tab usually serve to rein this node in by holding its effect to particles inside a certain region, age, or set, or by lowering the odds of the node acting on a given particle.

### Inputs
