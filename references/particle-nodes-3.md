# Particle Nodes (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Out of the box, the pKill node carries one orange input. As with the bulk of particle nodes, that orange input will take nothing but other particle nodes. Switch the Region menu over in the Region tab to either Bitmap or Mesh and a green bitmap or mesh input shows up on the node. Input: Output from other particle nodes flows into the orange input. Region: Whether you point the Region menu at Bitmap or Mesh decides whether the green or magenta region input receives a 2D image or a 3D mesh. Which input color you see depends on whichever option you choose first from the menu. Where particles get killed is set by the 3D mesh or by a channel you pick from the bitmap.

### Basic Node Setup

You slot the pKill node between the pEmitter and pRender nodes. To build the region in which particles die, a Shape 3D node serves the purpose.

A pKill node that leans on a Shape 3D node to mark out where particles perish Inspector Only the common controls in the Conditions and Regions tabs live on this node. With the Conditions and Regions controls you spell out the location, the age, and the set of particles getting killed.

### Common Controls

Conditions, Style, Region, and Settings Tabs Since every Particle node shares the Conditions, Style, Region, and Settings tabs, you'll find them written up under "The Common Controls" toward the close of this chapter.

### pMerge [pMg]

The pMerge node pMerge Node Introduction Not a single control sits on this node. Its job is to fuse particles arriving from two streams. Downstream of the pMerge node, any node regards those two streams as a single one. Whatever sets were attached to the combined particles at creation time stay intact, which lets nodes after the pMerge pick out particular particles whenever that's needed.

### Inputs

A matched pair of inputs, one orange and one green, sits on the pMerge node. Both of these inputs will take nothing but other particle nodes. Particle 1 and 2 Input: Two particle streams arrive through the two inputs and get merged.

### Basic Node Setup

Two pEmitter nodes are wired together by the pMerge node. From the pMerge, the output can carry on to feed further particle nodes or head into a pRender.

A pMerge node combining two pEmitter nodes.

### pPoint Force [pPF]

The pPoint Force node pPoint Force Node Introduction A force radiating out from one point in 3D space gets applied to the particles by this node. Particles caught inside its sphere of influence can be pulled in or pushed away by the pPoint Force. Four controls belong specifically to the pPoint Force node.

### Inputs

By default a lone orange input sits on the pPoint Force node. Like the majority of particle nodes, that orange input accepts only other particle nodes. Setting the Region menu in the Region tab to Bitmap or Mesh makes a green bitmap or mesh input show up on the node. Input: Output from other particle nodes flows into the orange input. Region: Depending on whether the Region menu points at Bitmap or Mesh, the green or magenta region input receives a 2D image or a 3D mesh. The first option chosen in the menu dictates the input's color. The area in which the point force acts on the particles is set by the 3D mesh or by a channel selected from the bitmap.

### Basic Node Setup

You drop the pPoint Force node in between a pEmitter and a pRender node.

The pPoint Force node sets down a tangent force that pulls particles toward it or drives them away.

### Inspector

Randomize Anytime a Fusion node depends on a random outcome, the Random Seed slider and Randomize button appear. Identical seed values across two nodes yield identical random results. Hit the Randomize button to pick a fresh seed value at random, or move the slider to dial one in by hand. Strength The force the node throws out has its Strength set by this parameter. Attractive forces come from positive values, while negative values give repellent forces. Power This sets how steeply the force's Strength tapers off across distance. With a value of zero, strength never tapers. The bigger the value, the steeper the drop in the force's strength as distance grows. Limit Force The Limit Force control exists to offset possible trouble from temporal sub-sampling. Since a particle's position gets sampled just once per frame (barring increased sub-sampling in the pRender node), a particle could shoot past the Point Force's position and wind up flung off the other way. Raising this control's value cuts the chance of that occurring. X, Y, Z Center Position Within 3D space, these controls stand in for the point force's coordinates along X, Y, and Z.

### Common Controls

Conditions, Style, Region, and Settings Tabs Every Particle node alike carries these four tabs—Settings, Region, Style, and Conditions—so look for their descriptions in "The Common Controls" portion at the end of this chapter.

### pRender [pRn]

The pRender node pRender Node Introduction Turning the particle system into either an image or geometry is the pRender node's role. By default it produces a 3D particle system, which has to be hooked up to a Renderer 3D before it yields an image. That lets the particles blend with other pieces of a 3D scene ahead of rendering.

### Inputs

There's one orange input on the pRender node, plus a green camera input and a blue effects mask input. As with most particle nodes, the orange input accepts only other particle nodes. Set the Region menu in the Region tab to Bitmap or Mesh and a green bitmap or mesh input appears on the node. Input: Output from other particle nodes flows into the orange input. Camera Input: A camera node connected directly, or a 3D scene carrying a connected camera, can feed the optional green camera input, which frames the particles as they render. Effect Mask: A mask shape built from polylines, simple primitive shapes, paint strokes, or bitmaps coming from other tools is what the optional blue input wants. Hooking a mask to this input on 2D particles trims the particle output so the particles show up only inside the mask.

### Basic Node Setup

A particle branch always finishes with the pRender node sitting at its end. With the pRender set to 2D, its output ties into other 2D nodes such as a Merge node. With the pRender set to 3D, its output ties into a 3D node such as a Merge 3D.

All particle branches end with a pRender node.

### Inspector

### The pRender controls

Output Mode (2D/3D) The pRender defaults to 3D output, yet you can make it render a 2D image instead. The 3D and 2D buttons on the Output Mode control handle that. When the pRender isn't tied to a 3D-only or 2D-only node, you can also flip it by picking View > 2D Viewer from the viewer's pop-up menu.

In 3D mode, just a handful of the pRender node's controls do anything at all: Pre-Generate frames, Sub-Frame Calculation Accuracy, Restart, plus Pre-Roll and Automatic Pre-Roll. Every other control touches 2D particle renders alone. On the node tree, the pRender node additionally carries a Camera input that lets a Camera 3D node be connected. Across both 2D and 3D modes, this governs the viewpoint from which an output image renders. Render and the Viewers Select the pRender node within a node tree and the viewers present every onscreen control belonging to the Particle nodes wired into it. That gives a quick, easily tweaked picture of the forces acting on the particle system overall. Pre-Roll Options Before they can work out how the applied forces affect them on the current frame, particle nodes usually need to know each particle's position on the previous frame. That makes shifting current time by hand in anything other than single-frame steps prone to yielding an inaccurate image. The controls here help with this by offering ways to compute the frames in between. Restart This control functions in 3D as well. Click the Restart button and the particle system restarts at the current frame, clearing out any particles made up to that point and beginning the particle system anew at the current frame. Pre-Roll This control functions in 3D as well. Click this button and the particle system recomputes, running from the render range's start through to the current frame. The image produced isn't rendered. Only each particle's position gets calculated. That offers a fairly fast way to confirm the particles shown in the views sit correctly. When the pRender node is on display as the Pre-Roll button gets clicked, the pre-roll's progress appears in the viewer with each particle drawn in point style alone. Automatic Pre-Roll Tick the Automatic Pre-Roll checkbox and the particle system auto-pre-rolls the particles to the current frame each time the current frame changes. That spares you from manually clicking the Pre-Roll button every time you skip through time by more than one frame. So you aren't distracted by visual disruptions, the particle system's progress during an Automatic Pre-Roll isn't shown in the viewers.

### About Pre-Roll

Pre-Roll matters because a particle system's state hinges entirely on the last known position of the particles. Should current time jump to a frame where the prior frame's particle state isn't known, the particle's display is worked out from the last known position, giving inaccurate results. To see it in action: 1 Drop a pEmitter plus a pRender node into the composition. 2 Show the pRender inside one of the viewers. 3 Dial the particles' Velocity to 0.1. 4 Park the pEmitter along the screen's left edge. 5 Bring the Current Frame to 0.

6 Define a Render Range that runs from 0–100 and click the Play button. 7 Watch the way the particle system behaves. 8 Pause playback and roll the current time back to frame 0. 9 Within the pRender node, switch off the Automatic Pre-Roll option. 10 With the current time number field, leap to frame 10, then on to frames 60 and 90. See how the particle system merely adds onto the particles it already made and won't try to produce the particles that should have emitted across the in-between frames. Now try clicking the Pre-Roll button in the pRender node. The particle system state now reads correctly. With simple, fast-rendering particle systems, leaving the Automatic Pre-Roll option on is advised. With slower particle systems spanning long time ranges, you may prefer to PreRoll only by hand, when needed.

### Only Render in Hi-Q

Tick this checkbox and the particles' style is overridden whenever the Hi-Q checkbox is off, yielding only fast-rendering Point-style particles. That comes in handy while you deal with a big batch of sluggish Image-based or Blob-style particles. To view the particles the way they'd look in a final render, just switch the Hi-Q checkbox on.

### View

This drop-down list offers options that set where the camera view sits within a 3D particle system. Its default, Scene (Perspective), renders the particle system from a virtual camera's viewpoint, whose position you can change through the Scene tab's controls. The remaining options deliver orthographic views of the particle system's front, top, and side. Bear in mind this control leaves the position of the onscreen controls for Particle nodes untouched. While in 2D mode, the onscreen controls always draw as though the viewer were displaying the front orthographic view. (In 3D mode the control positions stay correct throughout.) The View setting gets ignored when a Camera 3D node is wired to the pRender node's Camera input on the node tree, or when the pRender sits in 3D mode.

### Conditions

Blur, Glow, and Blur Blend During 2D particle generation, these sliders lay a Gaussian blur, glows, and blur blending over the image as it renders, handy for softening the particles and blending them. The result matches what you'd get by dropping a Blur downstream of the pRender node within the node tree. Sub-Frame Calculation Accuracy This sets how many sub-samples get taken between frames while the particle system is computed. Raising the value sharpens the calculation's accuracy yet also lengthens how long the particle system takes to render. Pre-Generate Frames This control makes the particle system pre-generate a chosen number of frames ahead of its first valid frame. It's there to hand the particle system a starting state to launch from.

A handy case for this is a shot where particles build the smoke drifting up from a chimney. Dial Pre-Generate Frames high enough that the smoke is already in the scene as the render starts, instead of having it merely begin to creep from the emitter over the opening few frames. Kill Particles That Leave the View Tick this checkbox control and any particles wandering past the image's visible edges get destroyed automatically. That can trim render times. Particles wiped out this way never come back, no matter what external forces push on them.Generate Z Buffer Tick this checkbox and the pRender node turns out a Z Buffer channel in the image. Each particle's depth is captured in the Z Buffer. That channel then feeds further depth operations such as Depth Blur, Depth Fog, and Downstream Z Merging. Switching this option on tends to push the particle system's render times up sharply. Depth Merge Particles Switch this option on and the particles get combined through Depth Merge techniques in place of layer-based ones.

### Scene Tab

Z Clip With the Z Clip control you place a clipping plane out in front of the camera. Particles passing through that plane get clipped, which keeps them from striking the camera's virtual lens and overrunning the scene.

### The pRender Scene tab

### Grid Tab

None of these controls touch 3D particles. The grid is a useful, non-rendering display aid for orienting the 2D particles in 3D space. It never turns up in renders, much as a center crosshair never appears in a render. You set the width, depth, line count, and grid color through the controls in this tab. Animating these controls isn't possible.

### The pRender Grid tab

### Image Tab

This tab's controls let you dial in the rendered image's resolution, its color depth, and its pixel aspect as produced by the node.

### The pRender Image tab

Process Mode This menu control lets you pick the Fields Processing mode Fusion applies when rendering image changes. The Has Fields checkbox control in the Frame Format preferences decides the default option. Use Frame Format Settings Tick this checkbox and the width, height, and pixel aspect of the images the node renders get pinned to the values laid out in the composition's Frame Format preferences. Should those Frame Format preferences change, the resolution of the node's output image shifts to keep pace. Turning this option off can help when you want to build a composition at a resolution different from the eventual target resolution for the final render. Width/Height You set the rendered image's Width and Height dimensions with this pair of controls. Pixel Aspect This control sets the Pixel Aspect ratio of the rendered particles. A 1:1 aspect ratio yields a square pixel measuring the same on every side (like a computer display monitor), whereas a 0.9:1 aspect yields a slightly rectangular pixel (like an NTSC monitor). NOTE: Right-click the Width, Height, or Pixel Aspect controls to bring up a menu listing the file formats set in the preferences Frame Format tab. Picking any listed option sets the width, height, and pixel aspect to that format's values accordingly. Depth The Depth menu sets the particles' pixel color depth. A 32-bit pixel eats 4X the memory of an 8-bit pixel but carries far better color accuracy. Float pixels permit high dynamic range values past the usual 0…1 range, for depicting colors brighter than white or darker than black. Source Color Space The Source Color Space menu lets you set the footage's Color Space to support a linear workflow. Unlike the Gamut tool, this performs no real color space conversion; instead it writes the source space data into the metadata when that metadata is absent. A downstream Gamut tool using the From Image option, or a Saver where explicit output spaces are defined, can then draw on that metadata. Two options are on offer:

- Auto: On its own, reads whatever metadata the image holds and carries it forward.
- Space: Brings up a Color Space Type menu from which you pick the image's right color

space. Source Gamma Space Through the Curve type menu you assign the footage's Gamma Space, and the Remove Curve checkbox lets you take it off while in a linear workflow. Three options live in the Curve type menu:

- Auto: On its own, reads whatever metadata the image holds and carries it forward.
- Space: Brings up a Gamma Space Type menu from which you pick the image's right

gamma curve.

- Log: Brings up the Log/Lin settings, similar to the Cineon tool.

For deeper detail, turn to Chapter 99, "Film Nodes," within the DaVinci Resolve Reference Manual, or to Chapter 39 over in the Fusion Reference Manual. Remove Curve Based on the Gamma Space you picked, or the one detected under Auto mode, the Gamma Curve is either pulled off the material or run through a log-lin conversion, which effectively recasts it as a linear output space. Motion Blur As with Fusion's remaining 2D nodes, you turn Motion Blur on from within the Settings tab. Quality, Shutter Angle, Sample Center, and Bias are all yours to set, and Blur then applies to each moving particle. NOTE: When Motion Blur runs on 3D mode particles (those rendered via a Renderer 3D), the identical motion blur settings must likewise be set on the Renderer 3D node.

### pSpawn [pSp]

The pSpawn node pSpawn Node Introduction The pSpawn node turns each affected particle into an emitter in its own right, capable of spawning one or more particles. The source particle carries on to the close of its lifespan, while every particle it throws off turns fully independent, holding a lifespan and properties all its own. For as long as a particle stays under the pSpawn node's effect, it keeps producing particles. Reining in the node's reach matters: use limiters such as Start and End Age, Probability, Sets and Regions, and animate the emitter's parameters so the node only kicks in when it should.

### Inputs

The pSpawn node ships with a single orange input by default. As with most particle nodes, that orange input accepts only other particle nodes. An image input becomes available once you pick Bitmap from the Style menu in the Style tab. On top of that, switching the Region tab's Region menu to Bitmap or Mesh makes a pair of region inputs—one for bitmap, one for mesh—appear on the node. Which colors these inputs take depends on the order in which they're switched on. Input: Output from other particle nodes feeds the orange input. Style Bitmap Input: A 2D image meant to serve as the particles' image goes into this image input. Because that image gets duplicated into potentially thousands of particles, keeping these images small and square is wise—say, 256 x 256 pixels.

Region: Whether the Region menu is set to Bitmap or Mesh decides whether the region inputs take a 2D image or a 3D mesh. The first option picked in the menu sets the input's color. Where particles get emitted is defined by the 3D mesh or by a channel chosen from the bitmap.

### Basic Node Setup

You position the pSpawn node between the pEmitter and pRender nodes. With the Age parameter inside the pSpawn's Conditions tab, fresh particles can spawn as the older ones expire. That's one route to sending a trail of particles rocketing skyward and bursting into glittering fireworks.

A pSpawn node set up to spawn fresh particles at chosen moments across the lifespan of the older ones Inspector A great many controls sit on the pSpawn node, the bulk of them precise duplicates of those in the pEmitter node. A handful are unique to the pSpawn node, and what they do is laid out below.

### The pSpawn controls

Affect Spawned Particles Tick this checkbox and particles born from spawning fall under the pSpawn node's effect too on later frames. That can balloon the system's particle count exponentially, shoving render times to an unreasonable level. Treat this checkbox with care.

Velocity Transfer This control sets how much of the source particle's velocity carries over to the particles it spawns. At its default of 1.0, each new particle inherits 100 percent of the source particle's velocity and direction. Lower the value and less of the original motion passes to the new particle.

### Common Controls

Conditions, Style, Region, and Settings Tabs Every Particle node carries the Conditions, Style, Region, and Settings tabs in common, so their write-ups appear in "The Common Controls" section at this chapter's end.

### pTangent Force [pTF]

The pTangent Force node pTangent Force Node Introduction This node serves to apply a tangential force to the particles—one that acts at right angles to the vector running between the pTangent Force's region and whichever particle it touches.

### Inputs

A lone orange input sits on the pTangent Force node by default. Like the bulk of particle nodes, this one will only take, through that orange input, the output of fellow particle nodes. Set the Region tab's Region menu to either Bitmap or Mesh and the node gains a green bitmap or mesh input. Input: Output from other particle nodes feeds the orange input. Region: When the Region menu sits on Bitmap, or alternatively Mesh, the green or magenta region input ends up receiving either a 2D image or else a 3D mesh. The first option chosen in the menu fixes the input's color. The area where the tangent force acts on the particles is defined by the 3D mesh or by a channel selected from the bitmap.

### Basic Node Setup

You drop the pTangent Force node in between a pEmitter and a pRender node.

The pTangent Force node sets a tangent force that particles steer around.

### Inspector

### The pTangent Force controls

This node's controls let you place the offset in 3D space and set the tangential force's strength along each axis on its own. Randomize The Random Seed slider and Randomize button turn up whenever a Fusion node leans on a random outcome. Two nodes sharing the same seed values turn out the same random results. Click the Randomize button to draw a fresh seed value at random, or shift the slider to choose one by hand. X, Y, Z Center Position Within 3D space, these controls stand for the Tangent force's coordinates across X, Y, and Z. X, Y, Z Center Strength Within 3D space, these controls fix the Tangent force's Strength.

### Common Controls

Conditions, Style, Region, and Settings Tabs These four tabs—Settings, Region, Style, and Conditions—are shared across all Particle nodes, so their descriptions appear in "The Common Controls" section at the close of this chapter.

### pTurbulence [pTr]

The pTurbulence node pTurbulence Node Introduction The pTurbulence node lays a frequency-driven chaos onto each particle's position, making the motion turn erratic and uneven. This node's controls govern the Turbulence's strength and density along each axis.

### Inputs

By default the pTurbulence node carries a single orange input. Like most particle nodes, this one accepts, by way of that orange input, nothing but the output of other particle nodes. Set the Region tab's Region menu to either Bitmap or Mesh and a green bitmap or mesh input shows up on the node. Input: Output from other particle nodes feeds the orange input. Region: When the Region menu rests on Bitmap, or instead on Mesh, the green or magenta region input correspondingly receives a 2D image or else a 3D mesh. The first option chosen in the menu sets the input's color. The region of turbulence is defined by the 3D mesh or by a channel picked from the bitmap.

### Basic Node Setup

You drop the pTurbulence node in between a pEmitter and a pRender node.

The pTurbulence node breaks up the stiff flow of particles to give a more natural motion.

### Inspector
