# Usd Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### USD Nodes

This section walks through the Universal Scene Descriptor (USD) nodes that ship inside Fusion.

You can type the short code printed alongside each node name into the Select Tool dialog while hunting for a tool, and those same codes turn up in scripting references too. Within this text, whenever a node tree pictures MediaIn nodes in DaVinci Resolve, treat them as equivalent to Loader nodes in Fusion Studio, except where a difference is explicitly called out.

### Universal Scene Descriptor (USD) Files

The Universal Scene Descriptor USD framework is a collection of open standards for laying out, assembling, and simulating a 3D environment. Rather than being merely a basic container, the USD file format is an open source 3D scene description meant for authoring and exchanging 3D content between many different applications. Both DaVinci Resolve and Fusion are able to read USD (.usdc, .usdz, and .usda) 3D data, covering geometry, lighting, cameras, materials, and animation. Fusion now includes a fresh set of USD tools that let you reshape, re-light, and render these USD files.

### The USD Loader

With the uLoader you can bring USD files in and tweak their options.

### The uLoader node

To Import a USD file: 1 Drop a uLoader tool into your Fusion Composition. 2 Pick the USD file you intend to bring in using the File Browser. Should you need to swap that file later on, you can do it from the uLoader Inspector without breaking your node tree. 3 Wire the output of the uLoader into a uMerge tool. 4 Attach whatever other USD tools you need, such as uCamera or any of the uLights, to work on the scene. 5 Route the output of the uMerge tool to a uRenderer. 6 Send the output of the uRenderer along to the MediaOut tool.

### A very simple USD import node tree

### USD Scene Tree Dialog for Object Selection in USD Files

Acting as an easy-to-read visual hierarchy, the Scene Tree window depicts USD scenes. From it you can pick out and edit single elements within a USD scene. The USD Scene Tree matters for targeted effects driven by the uVisibility, uVariant, uReplace Material, and uTransform nodes, and it also serves to override imported scene objects within uCamera and the assorted USD light tools. You bring up the USD Scene Tree by clicking the Pick button inside the Prim Selection box on certain USD tools.

### The Prim Selection Pick button

The tree lays out the USD hierarchy, while the type column tells you which sort of asset each entry is. You can pick, filter, isolate, and single out particular elements within a USD scene so you can concentrate on logical components and apply precise adjustments. Hold Command to toggle-select several objects at once, and use Shift to grab a range of objects with one click.

The USD Scene Tree dialog

### uCamera [uCa]

The USD Camera Node uCamera Node Introduction The uCamera node builds a virtual camera so you can look at the USD scene inside its 3D environment. It mirrors the controls found on actual cameras closely, which makes lining up live-action or 3D-rendered elements as smooth as it can be. Placing cameras into a 3D composite lets you frame the elements of that composite however you like and animate the camera across a scene to produce moving camera shots.

### Inputs

A single yellow Scene Input is provided for hooking up a USD scene. From there you can fine-tune whatever cameras already live inside the scene.

### Basic Node Setup

You should wire the output of a uCamera node into a uMerge node so it becomes part of a USD 3D scene alongside other assets and nodes.

Hooking the uCamera node up to a uMerge node hands standard camera controls over to a USD scene. If you show a uCamera node on its own in the viewer, you see nothing but an empty scene, because the camera has nothing to look at. To watch the scene through the camera, display the uMerge node that the uCamera feeds into, or any node positioned downstream of that uMerge. Next, right-click within the viewer and pick uCamera > [Camera name] from the contextual menu. You can also right-click the axis label in the lower corner of each USD viewer to bring up the Camera submenu. Because the viewer aspect can differ from the camera aspect, the camera view might not line up exactly with the real edges of the image that the uRenderer node produces. Turning on guides marks out the slice of the view the camera captures and helps you frame the shot. Right-click within the viewer and pick an option under the Guides > Frame Aspect submenu. The default choice adopts the format set in the Composition > Frame Format preferences. To switch the guides on or off, choose Guides > Show Guides from the viewers’ contextual menu, or press the Command-G (macOS) or Ctrl-G (Windows) keyboard shortcut while the viewer is active.

### Inspector

### The uCamera Controls tab

### Controls Tab

The Controls tab holds several of the most essential camera settings, including its film back properties, focal length, and clipping plains. Override Selection Clicking the Pick button lets you pick out a camera that already exists in an attached USD file, so you can adjust the cameras within an imported scene. Projection Type Use the Projection Type menu to switch between Perspective and Orthographic cameras. As a rule, cameras in the real world are perspective cameras. An orthographic camera relies on parallel orthographic projection, an approach in which the view plane sits perpendicular to the viewing direction. The result is a parallel camera output free of perspective distortion. For orthographic cameras, the only controls shown are those for the near and far clipping planes plus one that sets the viewing scale. Near/Far Clip Clipping planes restrict which geometry in a scene gets rendered according to how far an object sits from the camera’s focal point. They make sure that objects sitting right up against the camera, along with objects so distant they serve no purpose, are left out of the final rendering. The default perspective camera disregards this setting unless you turn off the Adaptive Near/Far Clip checkbox sitting beneath the Near/Far Clip control. Because the clip values are expressed in units, a far clipping plane of 20 means anything farther than 20 units from the camera stays invisible to it. Likewise, a near clipping plane of 0.1 means anything nearer than 0.1 units is hidden as well. NOTE: Keeping a tighter span between the near and far clipping planes yields better precision across every depth calculation. Should a scene start rendering odd artifacts on far-off objects, try pushing the Near Clip plane farther out.

Exposure With this turned on, the renderer sets the camera’s Near/Far Clipping plane on its own to fit the bounds of the scene. Doing so supersedes whatever you entered in the Near and Far clip range controls covered earlier. Orthographic cameras cannot use this option. Focal Length On an actual lens, the focal length measures the gap from the lens’s center out to the film plane. A shorter focal length places the focal plane nearer the rear of the lens. Focal length is given in millimeters. The angle of view and the focal length controls tie directly together. A shorter focal length widens the angle of view, so adjusting either control updates the other automatically to stay in sync. You can express how angle of view relates to focal length with the formula angle = 2 \* arctan[aperture / 2 / focal_ length]. Plug in the vertical aperture size for the vertical angle of view, and the horizontal aperture size for the horizontal angle of view. Focal Distance Much like the focal point on a real camera, this setting sets how far the camera sits from an object and feeds into the depth-of-field calculation. F Stop This sets the aperture size of the synthetic lens; it has an impact on exposure and also factors into the depth-of-field calculation.

### Film Back

Here you can manage the technical parameters belonging to the part of the camera that isn’t the lens. Horizontal/Vertical Aperture The Horizontal Aperture Width and Vertical Aperture Height sliders govern the size of the camera’s aperture, which on a real camera is the part that admits light. On video and film cameras, the aperture refers to how wide the opening is that determines the exposed area of each frame, a measurement also known as sensor size. Lens Shift X/Y Gives you controls for manually shifting the camera lens in width and in height. Shutter Close/Open These set the moments at which the camera shutter opens and shuts; they bear on Exposure and Motion Blur. Stereo Role When the camera is stereo, this picks the center of role for the pair of cameras, choosing left, center, or right.

### Control Visibility

From here you can pick and choose which of the onscreen controls shown beside the camera get turned on.

- Show View Controls: Shows or conceals every onscreen camera control in the viewers.
- Frustum: Shows the camera’s actual viewing cone.
- View Vector: Shows a white line running through the viewing cone that you can use to find the

center of the frame.

- Near Clip: The Near Clipping plane. You can subdivide this plane to see it more clearly.
- Far Clip: The Far Clipping plane. You can subdivide this plane to see it more clearly.
- Focal Plane: The plane established by the Focus Distance. You can subdivide this plane to see it

better.

- Convergence Distance: Where convergence occurs while in Stereo mode. You can subdivide this plane

to see it more clearly.

### Common Controls

Transform and Settings Tab The Inspector’s Transform and Settings tab is repeated across the other USD nodes as well. You’ll find a thorough description of these shared controls in the “The Common Controls” section near the close of this chapter.

### uDuplicate [uDp]

### The USD Duplicate node

### Introduction

Much like the 2D and 3D Duplicate nodes, the uDuplicate node lets you copy any USD asset within a scene, stacking a transformation onto each successive copy to build repeating models and elaborate arrays of objects. Settings on the Jitter tab make non-uniform transformations possible, for instance randomized placement or sizing.

### Inputs

By default the uDuplicate node offers just one input, into which you plug a USD scene. Depending on how the node is configured, an optional Mesh input may also show up. SceneInput: The orange Scene Input must be connected. Whatever scene or object you feed into this input gets duplicated according to the settings on the Inspector’s Control tab. MeshInput: A green optional mesh input shows up once the Region menu on the Region’s tab is set to mesh. That mesh may be any 3D model, whether built inside Fusion or brought in from elsewhere.

### Basic Node Setup

Most of the time the output of a uDuplicate node feeds a uMerge node, folding it into a bigger scene. The USD scene you’d like copied, here a USD scene of a Tokyo shophouse, gets wired into the orange input.

A USD scene of a Tokyo shophouse is duplicated.

### Usage

### The uDuplicate controls

### Controls Tab

On the Controls tab you’ll find every parameter for making, offsetting, and scaling copies of the USD object plugged into the node’s scene input. USD Instancing Switch this on and Fusion reuses the same USD data for every copy as an efficiency gain. That said, there are cases where the copies vary so much from one another that efficiency drops instead, in which case you can switch this setting off. Copies This range control determines how many copies get produced. Every copy derives from the previous one, so if you set the control to [0,3], first the parent gets duplicated, next that duplicate gets duplicated, after which the duplicate of the duplicate is duplicated, continuing onward. This opens the door to interesting effects once you apply transformations to each copy via the controls underneath. Raising the First Copy above 0 leaves the original object out and displays only the copies.

Time Offset The Time Offset slider shifts whatever animations sit on the source geometry by a fixed amount for each copy. As an illustration, set the value to -1.0 and feed in a cube animated to spin on the Y-axis as the source. The first copy plays the animation one frame back; the second copy plays it from one frame earlier still, and so on. Used on textured planes this can be striking—say, when each successive frame of a clip is put on display.

### Transform Method

- Linear: With Linear chosen, each transform is scaled by that copy’s number, and the overall scale, rotation, and translation are applied one after another, with no dependence on the other copies.
- Accumulated: With Accumulated chosen, every object copy begins where the previous object ended and is transformed onward from there. That outcome is then transformed again to produce the next copy

Transform Order This menu lets you set the sequence in which the transforms are worked out. Its default is ScaleRotation-Transform (SRT). Picking other orders lands your final objects in different positions.

Translation The X, Y, and Z Offset sliders fix the offset position given to each copy. An X offset of 1 shifts every copy 1 unit along the X-axis away from the preceding one. Rotation The row of buttons at the top of this rotation control group sets the sequence in which rotations hit the geometry. Choosing a rotation order of XYZ rotates around the X-axis first, then around the Y-axis, and finally around the Z-axis. The trio of Rotation sliders decides how much rotation each copy receives. Pivot The pivot controls fix where the pivot point sits as each copy is rotated.

### Scale

- Lock: With the Lock XYZ checkbox ticked, whatever you change on the duplicate scale takes effect on all three axes together. Untick the checkbox and the single Scale slider gives way to separate sliders for the X, Y, and Z scales.
- Scale: The Scale controls inform Duplicate how much scaling each copy should get.

uDuplicate Jitter tab Jitter Settings on the Jitter tab let you randomize the placement, rotation, and size across all the copies produced on the Controls tab. Random Seed The Random Seed slider seeds a random starting point for how much jitter lands on the duplicated objects. Take two Duplicate nodes with matching settings but distinct random seeds and they’ll yield two utterly different outcomes. Randomize Hit the Randomize button to have a random seed value generated for you. Jitter Probability Moving this slider sets what fraction of the copies the jitter touches. A setting of 1.0 reaches 100% of them, and a setting of 0.5 reaches 50%. Time Offset The Time Offset slider nudges whatever animations sit on the source geometry by a fixed amount for each copy. For instance, set the value to –1.0 and supply a cube animated to spin on the Y-axis as the source. The first copy plays the animation one frame back; the second copy plays it from a frame earlier still, and so on. On textured planes this works wonderfully—for example, when each successive frame of a clip is shown. Translation Jitter With these three controls you dial in the degree of variation across the X, Y, and Z translation applied to the duplicated objects.

Rotation Jitter With these three controls you dial in the degree of variation across the X, Y, and Z rotation applied to the duplicated objects. Pivot Jitter With these three controls you dial in the degree of variation in the rotational pivot center of the duplicated objects. This bears only on the extra jitter rotation, not on the rotation coming from the Rotation settings on the Controls tab. Scale Jitter This control lets you tune how much spread there is in the scale of the duplicated objects. Untick the Lock XYZ checkbox to vary the scale spread on each of the three axes on its own.

uDuplicate Region tab Region Tab Settings on the Region tab let you mark out a zone in the viewer where copies are either allowed to show up or kept from doing so. As with most Fusion parameters, you can animate this zone so the copied object pops on and off the screen according to the region’s shape and setting. Region Tab The Region section carries two settings that govern the region’s shape and how the region acts on the duplicate objects.

- Region Mode: The Region Mode menu offers three choices. Its default, “Ignore region,” skips the node altogether and leaves the object copies exactly as the Controls and Jitter tabs set them. The choice “When inside region” makes the copied objects show up only while their position lies within the region marked out on this tab. The final choice, “When not Inside region,” makes the copied objects show up only while their position lies beyond the region marked out on this tab.
- Region: The Region menu picks the region’s shape. Among its five choices are the cube, sphere, and rectangle primitive shapes. The mesh choice lets you wire a 3D model into the node’s green mesh input. That green input only turns up once the Region menu is set to Mesh. The All choice covers the whole scene. This lets the copies pop on and off whenever the Region mode is animated. Setting the Region menu to Mesh brings up two more options, covered just below.

Limit by Object ID: Once a scene holding several meshes is wired into the node’s green Mesh input, every mesh serves as the region. Tick this checkbox and you can use the Object ID slider to pick the ID of whichever mesh you want as the Region. Object ID: With the Limit by Object ID checkbox ticked, this slider chooses the number ID of the mesh object you intend to use for the Region.

### uExport [uEx]

The uExport node uExport Node Introduction The uExport node exists to write scenes out in the Universal Scene Description (USD) format. Through it you can save your USD scene—geometry, materials, animations, and lighting included—into a USD file. This addition is a notable step forward for Fusion, letting you pass complex USD assets around effortlessly and making collaborative workflows run more smoothly. The node provides controls for picking among the various USD formats, namely usd, .usda, .usdc, and .usdz. You can also write out chosen nodes from the source tree as a hierarchy of linked USD files.

### Inputs

The Background node carries a single input meant for a USD scene.

### Inspector

### The uExport controls

### Export

Use the Export controls to choose the format that your exported USD scene is saved in.

- Export Stage: Click this button to bring up a file browser where you choose where your USD scene is saved.
- Format: Pick a format for your USD scene.
- USD (\*.usd)
- USD UTF-8 (\*.usda)
- USD binary (\*.usdc)
- USD packaged (\*.usdz)

### Common Controls

Settings Tab The Inspector’s Settings tab is repeated on the other USD nodes too. A full account of these shared controls appears in the “The Common Controls” section toward the end of this chapter.

### uImage Plane [uIm]

The USD Image Plane node uImage Plane Node Introduction Within 3D space, the uImage Plane node builds flat 2D geometry. Its most typical job is to show 2D images on “cards” inside the 3D space. The aspect ratio of the image plane follows the aspect ratio of whatever image you feed in.

### Inputs

This node’s input takes the image that gets texture mapped onto the plane. Input: The yellow input is where you wire in a MediaIn image.

### Basic Node Setup

The uImage Plane Node takes in a 2D image and drops it into a 3D USD scene.

### Inspector

### The uImage Plane controls

### Controls Tab

Common controls fill most of the Controls tab. The handful of Image Plane-specific controls sitting at the top of the Inspector handle small tweaks.

Filename The uImagePlane carries an input so an image can be routed straight into the node. The node can also load an image directly when you browse for one, after which it shows the name and path in the filename. Click the Browse button to bring up the file browser and choose an image. Size Size sets how big the image plane is within the USD 3D scene.

### Common Controls

Transform and Settings Tab You’ll also find the Inspector’s Transform and Settings tab repeated on the other USD nodes. These shared controls are spelled out fully in the “The Common Controls” section at the end of this chapter.

### uLoader [uLd]

The USD Loader node uLoader Node Introduction You rely on the uLoader node to pull USD files into your Fusion Composition. It handles the .usd, .usda, .usdc, and .usdz formats.

### Replacing Materials with Imported MaterialX files

You can bring MaterialX files (.mtlx) in through the USD Loader and then call on the uReplaceMaterial tool to apply those imported materials to a chosen USD object and reach the look you’re after.

### Inputs

None.

### Basic Node Setup

After the uLoader node brings in a USD scene, it combines that scene with a USD Camera so you can control the view.

### Inspector

### The USD Loader controls

### Controls Tab

Filename With this control you point to a USD file to pull into the Fusion project. Click the Browse button to bring up the file browser and choose a USD file (.usd, .usda, .usdc, or .usdz). Trim Lets you mark an In and Out point on a USD file so only that span comes into the Fusion project. Time Scale With time scale you can speed up or slow down the playback of animated .usd scenes. Frame Offset Sets the point at which an animation begins, letting you slide its timing along the timeline. Reverse Tick this and the animation of the USD file plays backward. Loop Tick this and the animation of the USD file repeats. Reload Clicking this button reloads the USD file named in the Filename field above. That way you can edit the USD file in some other application and view the results in Fusion simply by reloading it.

### Common Controls

Settings Tab You’ll also see the Inspector’s Settings tab on the other USD nodes. A detailed write-up of these shared controls sits in the “The Common Controls” section at this chapter’s end.

### uMaterialX [uMX]

The uMaterialX node uMaterialX Node Introduction All the uMaterialX node does is read in a MaterialX (.mtlx) definition file and produce a USD scene file holding nothing but those materials.

### Inputs

The uMaterialX node has no inputs at all—just a file requester for loading the .mtlx file.

### Basic Node Setup

Wire the material output into the remaining USD tools.

Here a node tree depicts a MaterialX definition (.mtlx) file named Material4 being read into a uMaterialX node, which hands the material on to a uReplaceMaterial node so the material gets swapped within a USD scene named JogBackwards.

### Inspector

### The uMaterialX controls

### Controls

There’s only one control here: a a Material File selector paired with a browse button for loading the .mtlx file off your computer. Settings Tab The Inspector’s Settings tab turns up on the other USD nodes as well. These shared controls get a thorough explanation in the “The Common Controls” section near the end of this chapter.

### uMerge [uMg]

The USD Merge node uMerge Node Introduction The uMerge node is Fusion’s main node for bringing distinct 3D elements together into one shared 3D environment. Take a scene built from an image plane, a camera, and a light: the camera couldn’t see the image plane and the light couldn’t touch it until all three objects are gathered into the same environment by way of the uMerge node. The uMerge carries the same standard transformation controls that most nodes in Fusion’s USD suite have. What sets it apart is that adjusting the uMerge’s translation, rotation, or scale alters every object wired into the uMerge. That behavior is what underpins all parenting throughout Fusion’s 3D environment.

### Inputs

At first the uMerge node shows three inputs, yet every time you fill one, another input pops up on the node, so there’s always a spare for adding a fresh element to the scene. SceneInput[#]: You use these inputs to attach USD image planes, 3D cameras, lights, whole USD scenes, and other uMerge nodes too. The node places no cap on how many inputs it will take. It keeps adding inputs on the fly as required, guaranteeing that at least one input is always open for a connection.

### Basic Node Setup

The uMerge node pulls together the 3D USD scene coming from the uLoader, two light sources, and the camera, then hands that view off to the uRenderer node, which flattens it down into a 2D image.

### Common Controls

Transform and Settings Tab Here too the Inspector’s Transform and Settings tab is shared with the other USD nodes. You can read a full description of these common controls in the “The Common Controls” section at the close of this chapter.

### uRenderer [uRn]
