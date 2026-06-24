# 3D Nodes (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### 3D Nodes

Across this chapter we work through, at length, the nodes that go into building 3D composites.

Each node name carries an abbreviation beside it that serves in the Select Tool dialog while you hunt for tools and within scripting references. Throughout this document, treat node trees that show MediaIn nodes in DaVinci Resolve as equivalent to Loader nodes in Fusion Studio, except where a note says otherwise.

### Alembic Mesh 3D [Abc]

### The Alembic Mesh 3D node

### Alembic Mesh Node Introduction

There will be moments when you have to pull in 3D geometry out of programs such as Blender, Cinema4D, or Maya. Among the formats available for bringing in 3D geometry is the Alembic file format. That file type acts as a 3D scene interchange format carrying baked animation alongside its geometry. Put another way, it removes the animation calculation times by tucking fixed, uneditable animation in with 3D geometry. Such animation usually rides along inside a point cache, which preserves the dynamic data — velocity, for instance — once it has been worked out. An Alembic object may hold mesh geometry, cameras, points, UVs, normals, and baked animation. There are two routes to bring Alembic files (.abc) into Fusion:

- Within Fusion pick File > Import > Alembic Scene; over on DaVinci Resolve’s Fusion page the route is Fusion > Import > Alembic Scene instead.
- Add an AlembicMesh3D node to the Node Editor.

That first route is the one to favor; on their own, both Alembic and FBX nodes pull in the whole model as a single object. The Import menu, by contrast, splits the model, lights, camera, and animation apart into a chain of separate nodes. Doing so makes editing, tweaking, and reusing portions of the imported Alembic mesh straightforward. On top of that, transforms held in the file land in Fusion splines and in the Transform 3D nodes, which then save with the comp. Afterward, when the comp is reopened, those transforms come back from the comp rather than from the Alembic file. Meshes get treated another way by Fusion, which always pulls them anew out of the Alembic file. Whatever arbitrary user data exists shifts according to the software that authored the Alembic file, so this category of metadata is largely disregarded.

### Alembic Import Dialog

Picking the file to import brings up an Alembic Import dialog

### Alembic Import options

Up in the top half of the Import dialog you'll see details about the chosen file: the name of the plugin/application that authored the Alembic file, which version of the Alembic software developer kit handled the export, how long the animation runs in seconds where that figure exists, and the frame rate(s) carried in the file. You can pull in assorted objects and attributes by ticking the checkboxes within the Import section.

- Hierarchy: With this on, the entire parenting hierarchy gets rebuilt in Fusion through multiple Transform 3D nodes. With it off, the transforms held in the Alembic file collapse down into the cameras and meshes. That flattening leaves several meshes/cameras wired to one Merge node in Fusion. Keeping it off works best whenever the file carries animation. Turned on, the numerous rigs that drive objects through a scene spawn an equally hefty count of nodes in Fusion, so flattening trims how many nodes land in your node tree.
- Orphaned Transforms: Once the hierarchy option is on, an Orphaned Transforms setting shows up. Switching this Orphan Transforms setting on brings in transforms that parent a mesh or camera. Say you've got a skeleton plus its matching mesh model: the model arrives as an Alembic mesh while the skeleton arrives as a node tree of Merge3Ds. Leave it off and those Merge3Ds never get built.
- Cameras: With this on, bringing in a file pulls cameras along too, complete with Aperture, Angles of View, Plane of Focus, plus the Near and Far clipping plane settings. Whether the resolution Gate Fit comes across hinges on whether the application that exported the file tagged the resolution Gate Fit metadata correctly. Should your camera fail to import properly, look at the setting for the Camera3D Resolution Gate Fit. Bear in mind that 3D Stereoscopic information does not come across.
- InverseTransform: Imports the Inverse Transform (World to Model) for cameras.
- Points: A Points type is among what Alembic files can carry. It amounts to a set of 3D points, each holding position

information. Certain 3D programs push out particles as points. Keep in mind, though, that even though position carries over, the particles' direction and orientation drop away.

- Meshes: This setting governs whether the import takes in 3D models out of the Alembic file. Switch it on and options to bring along UVs and normals appear.

### Animation

A single option lives in this section, the Resampling rate. As an Alembic animation is exported, it gets written to disk using frames per second (fps). On bringing Alembic data into Fusion, the fps get picked up and dropped into the Resample Rate field, unless you already altered it earlier in the current comp. The smart move is to hold the exported frame rate as the resample rate, keeping your samples aligned with the original. Up at the top of the dialog the Detected Sampling Rates information can hint at a good pick if you're uncertain. Even so, by way of this field you can shift the frame rate to produce effects such as slow motion. Within the Alembic file format, not every object and property in a 3D scene enjoys an agreed-upon universal convention. Given that, Lights, Materials, Curves, Multiple UVs, and Velocities currently go unsupported as you bring in Alembic files. Because the FBX file format does carry materials and lights, our advice is to reach for FBX where lights, cameras, and materials are concerned. Reserve Alembic for meshes alone.

### Inputs

Within the Node Editor the AlembicMesh3D node carries two inputs. Each one is optional, since the node is meant to run off the imported mesh. SceneInput: That orange input lets you wire in another 3D scene or model. The imported Alembic objects then join with the other 3D geometry. MaterialInput: The optional green input serves to put a material onto the geometry by wiring up a 2D bitmap image. It lays the connected image across the surface of the geometry in the scene.

### Basic Node Setup

The AlembicMesh3D node is built to sit within a bigger 3D scene. As a rule, once imported, a single node stands in for a 3D geometry model while any transforms live in a separate node. Those nodes brought in as part of the Alembic file feed into a Merge 3D node together with a camera, lights, and whatever else the scene happens to call for.

### Alembic node structure

### Inspector

### Alembic mesh 3D controls

### Controls Tab

Heading the Inspector is the Controls tab. Within it sits a run of distinct controls tied to the Alembic Mesh 3D node along with six clusters of controls shared by most 3D nodes. Over at the close of this chapter, the Common Controls section spells out the shared controls in full. What follows describes the controls specific to the Alembic Mesh 3D. Filename The full file path of the imported Alembic file shows up here. By way of this field you can swap or refresh the file tied to this node.

Object Name This text field lists the name of the imported Alembic mesh, the same name applied when renaming the Alembic Mesh 3D node in the Node Editor. As you import by way of the Alembic Mesh 3D node, leaving this text field empty causes the whole of the Alembic geometry to come in as one mesh. Where geometry is imported via File > Import > Alembic Scene, Fusion fills in this field for you. Wireframe Turning this option on makes the mesh show nothing but the wireframe for the object inside the viewer. Once on, a second option for wireframe anti-aliasing appears. These wireframes can even be rendered out to a file provided the Renderer 3D node has the OpenGL render type chosen.

### Common Controls

Controls, Materials, Transform, and Settings Tabs Within the Controls tab, several controls recur across many 3D nodes: Visibility, Lighting, Matte, Blend Mode, Normals/Tangents, and Object ID. Likewise, the Inspector's Materials tab, Transforms tab and Settings tab show up again on other 3D nodes. Full coverage of these shared controls waits at the close of this chapter inside the “The Common Controls” section.

### Bender 3D [3Bn]

### The Bender 3D node

### Bender 3D Introduction

You reach for the Bender 3D node to bend, taper, twist, or shear 3D geometry off the back of the geometry’s bounding box. It runs by wiring any 3D scene or object into the orange input on the Bender 3D node, then tuning the controls over in the Inspector. Only the geometry within the scene gets reshaped. Whatever lights, cameras, or materials pass straight through untouched. No fresh vertices come out of the Bender node; it merely shifts the vertices already in the geometry. So, when you apply the Bender 3D node to primitives such as the Shape 3D, or Text 3D nodes, raise the Subdivision setting over in the primitive’s node to land a finer result.

### Inputs

On the Bender 3D node within the Node Editor the inputs below show up. SceneInput: That orange scene input stands as the required input for the Bender 3D node. Through it you wire in another node that builds or holds a 3D scene or object.

### Basic Node Setup

The way the Bender 3D node operates is by wiring in a 3D node holding geometry, such as an image plane 3D, Shape 3D or Text 3D. Whatever element you feed into the Bender 3D node ends up warped according to the controls over in the Inspector. The Bender 3D node is meant to form part of a bigger 3D scene, its output as a rule feeding on into a Merge 3D.

### Bender 3D node structure

### Inspector

### Bender 3D controls

### Controls Tab

Heading the Inspector is the Controls tab. Within it sit all the controls for the Bender 3D node. Bender Type Through the Bender Type menu you pick which kind of deformation gets applied to the geometry. Four modes are on offer: Bend, Taper, Twist, and Shear.

Amount Dragging the Amount slider varies how strong the deformation is. Axis The Axis control sets which axis the deformation runs along. Its sense changes with the type of deformation in play. When bending, for one, it picks the elbow working together with the Angle control. In the remaining cases, the deform wraps around the named axis. Angle The Angle thumbwheel control fixes which direction about the axis a bend or shear runs. It stays hidden for taper or twist deformations. Range Through the Range control you can pen the reach of a deformation into a slim slice of the geometry. The Range control goes away once the Bender Type is set to Shear. Group Objects Should the input of the Bender 3D node hold several 3D objects, whether by way of a Merge 3D or chained together, the Group Objects checkbox handles every object in the input scene as one object, and the shared center drives the deformation of the objects rather than warping each component object on its own.

### Common Controls

Settings Within the Inspector the Settings tab is shared by every 3D node. Full coverage of this shared tab waits at the close of this chapter inside the “The Common Controls” section.

### Camera 3D [3Cm]

### The Camera 3D node

### Camera 3D Node Introduction

A virtual camera for looking into the 3D environment is what the Camera 3D node produces. It mirrors closely the settings found on real cameras, so that pairing live-action or 3D-rendered elements stays as seamless as it can be. Dropping any cameras into a 3D composite lets you frame the elements of a composite to taste and animate the camera over a scene to build moving camera shots.

### Camera Projection

The Camera 3D node also serves to carry out Camera Projection, casting a 2D image through the camera out into 3D space. Casting a 2D image works either as a plain Image Plane lined up with the camera, or as a genuine projection — much like how the Projector 3D node behaves — with the extra benefit that it lines up exactly with the camera. The Image Plane, Projection, and Materials tabs stay hidden until you wire a 2D image into the magenta image input on the Camera 3D node within the Node Editor.

### Stereoscopic

Built into the Camera node are stereoscopic features. They hand you control over eye separation and convergence distance. A separate camera node wired into the green left/right stereo camera input can stand in for the right-eye camera. On top of that, the plane of focus control for depth of field rendering lives here as well. Drag the camera icon off the toolbar onto the 3D view and the camera you add hooks up on its own to the Merge 3D you happen to be viewing. What's more, the current viewer gets pointed through the new camera. As another path, you can copy the current viewer onto a camera (or spotlight or any other object) by picking the Copy PoV To option within the viewer’s contextual menu, down under the Camera submenu.

### Inputs

Three optional inputs sit on the Camera 3D node within the Node Editor. SceneInput: That orange input serves to wire in a 3D scene or object. Once wired, the geometry ties to the camera’s field of view. It behaves much like an image hung off the Image Plane input. Where the camera’s Projection tab has projection switched on, the image hung off the orange image input casts onto the geometry. ImageInput: The optional magenta input serves to wire in a 2D image. With camera projection switched on, the image can stand in as a texture. As another path, where the camera’s image plane controls come into play, the parented planar geometry ties to the camera’s field of view. RightStereoCamera: The green input ought to be wired into a second Camera 3D node while crafting 3D stereoscopic effects. It serves to override the internal camera that drives the right eye across stereoscopic renders and viewers.

### Basic Node Setup

A camera 3D node's output ought to feed into a Merge 3D node. You then look at the Merge 3D node and choose the camera out of the viewer’s right-click menu or by right-clicking on the axis label within the viewer.

Camera node connected to and viewed through the Merge 3D Putting a camera node straight into the viewer reveals only a bare scene; the camera has nothing to look at. To peer through the camera at the scene, look at the Merge 3D node where the camera hooks up, or any node downstream of that Merge 3D. After that, right-click on the viewer and pick Camera > [Camera name] off the contextual menu. Right-clicking on the axis label down in the lower corner of each 3D viewer likewise brings up the Camera submenu.

The viewer's aspect can differ from the camera's aspect, so the camera view might not line up with the true bounds of the image that the Renderer 3D node puts out. Guides can be switched on to stand for the slice of the view the camera takes in and help you frame the shot. Right-click on the viewer and pick an option off the Guides > Frame Aspect submenu. By default that option draws on the format switched on in the Composition > Frame Format preferences. To flip the guides on or off, pick Guides > Show Guides off the viewers’ contextual menu, or reach for the Command-G (macOS) or Ctrl-G (Windows) keyboard shortcut while the viewer is active.

### Inspector

### Camera 3D controls

### Controls Tab

Six tabs run across the top of the Camera3D Inspector. The opening one, named the Controls tab, holds several of the most basic camera settings; among them you'll find stereoscopic properties together with the camera’s focal length, its field of view, and its clipping plains. Certain tabs stay hidden until a needed connection reaches the Camera 3D node. Projection Type Through the Projection Type menu you pick between Perspective and Orthographic cameras. By and large, real-world cameras are perspective cameras. An orthographic camera leans on parallel orthographic projection, an approach where the view plane sits perpendicular to the viewing direction. The upshot is a parallel camera output free of perspective distortion. Orthographic cameras surface controls just for the near and far clipping planes, alongside one control that sets the viewing scale. Near/Far Clip By way of the clipping planes you bound which geometry in a scene gets rendered, going by an object’s distance from the camera’s focal point. Clipping planes make sure that objects sitting extremely close to the camera, together with objects too distant to matter, drop out of the final rendering.

By default the perspective camera pays this setting no mind unless the Adaptive Near/Far Clip checkbox sitting under the Near/Far Clip control is switched off. The clip values run in units, so a far clipping plane of 20 means any object beyond 20 units from the camera goes unseen by the camera. A near clipping plane of 0.1 means any object nearer than 0.1 units likewise goes unseen. NOTE: Keeping a tighter range between the near and far clipping planes affords more precision throughout every depth calculation. Should a scene start to throw odd artifacts on distant objects, try pushing the distance for the Near Clip plane higher. Adaptive Near/Far Clip Switched on, the renderer tunes the camera’s near/far clipping plane on its own to fit the reach of the scene. This setting trumps the values of the Near and Far clip range controls covered above. The option is missing for orthographic cameras. Viewing Volume Size Once the Projection Type sits at Orthographic, the viewing volume size adjustment surfaces. It fixes the size of the box forming the camera’s field of view. An orthographic camera's Z-distance from the objects it takes in has no bearing on how those objects are scaled; the viewing size alone governs that. Angle of View Type Reach for the Angle of View Type buttons to settle how the camera’s angle of view gets measured. Certain applications go by vertical measurements, some by horizontal, others by diagonal measurements. Switching the Angle of View type makes the Angle of View control below recompute. Angle of View Angle of View sets out the slice of the scene viewable through the camera. As a rule, the human eye takes in more of a scene than a camera does, and assorted lenses record differing shares of the whole image. A big value yields a wider angle of view, while a smaller one yields a narrower, or more tightly framed, angle of view. Exactly as on a real-world camera, the angle of view and focal length controls tie directly together. Shorter focal lengths yield a wider angle of view, so nudging one control nudges the other to keep pace. Focal Length Out in the real world, a lens’ Focal Length measures how far the film plane sits from the lens's center. The briefer that focal length, the nearer the focal plane draws to the back of the lens. Focal length gets measured in millimeters. The angle of view and focal length controls tie directly together. Shorter focal lengths yield a wider angle of view, so nudging one control nudges the other to keep pace. The bond between focal length and angle of view runs angle = 2 \* arctan[aperture / 2 / focal_length]. Feed in the vertical aperture size to land the vertical angle of view and the horizontal aperture size to land the horizontal angle of view. Plane of Focus (For Depth of Field) Much like a focal point on a real-world camera, this setting fixes the span from the camera out to an object. The OpenGL renderer within the Renderer 3D node draws on it to work out depth of field.

### Stereo

Within the Stereo section sit options for arranging 3D stereoscopic cameras. The way 3D stereoscopic composites operate is by grabbing two slightly different views, shown apart to the left and right eyes. Through the mode menu you settle whether the current camera runs as a stereoscopic setup or a mono camera. Left at the default mono setting, the camera takes in the scene the way a traditional 2D film camera would. Three further options in the mode menu fix which method drives the 3D stereoscopic cameras. Toe In Under a toe-in setup, both cameras swing inward toward a single focal point. The outcome is stereoscopic, yet the vertical parallax this method brings in can leave the audience uncomfortable. Toe-in stereoscopic holds up for convergence around the middle of the images but shows keystoning, or image separation, toward the left and right edges. Such a setup can come into play when the focus point and the convergence point have to coincide. It also serves in cases where it stands as the only route to match a live-action camera rig.

### Toe In 3D camera setup

### Off Axis

Held to be the proper way to build stereo pairs, this is the method Fusion picks by default. Off Axis brings in no vertical parallax, thereby producing stereo images that ease eye strain. At times dubbed a skewed-frustum setup, it parallels a lens shift out in the real world. Rather than swinging the two cameras inward as a toe-in setup does, Off Axis slides the lenses inward.

### Off Axis 3D camera setup

### Parallel

Here the cameras slide parallel to one another. Because this amounts to a purely parallel shift, no Convergence Distance control exists, which caps how much say you have over placing objects ahead of or behind the screen. That said, Parallel brings in no vertical parallax, thereby easing the strain on the eyes.

### Parallel 3D camera setup

Rig Attached To Through this drop-down menu you steer which camera drives the transform of the stereoscopic setup. According to this menu, transform controls turn up in the viewer either on the right camera, the left camera, or in between the two cameras. Being able to swing the transform controls around through rigging can help in matching the animation path to a camera crane or some other live-action camera motion. The Center option plants the transform controls between the two cameras and shifts each one evenly as the separation and convergence get tuned. Left drops the transform controls on the left camera, and the right camera moves while separation and convergence get tuned. Right places those same controls on the right camera, leaving the left camera to move while separation and convergence are adjusted. Eye Separation Eye Separation fixes the gap between both stereo cameras. Pushing Eye Separation past 0 surfaces controls for each camera in the viewer while this node is picked. Note there's no Convergence Distance control in Parallel mode. Convergence Distance Through this control you set the stereoscopic convergence distance, framed as a point sitting along the Z-axis of the camera that fixes where both left- and right-eye cameras meet. The Convergence Distance controls only surface when the Mode menu sits at Toe-In or Off Axis.

### Film Back

Film Gate How big the film gate is stands for the dimensions of the aperture. Rather than setting the aperture’s width and height, you can pick it off the list of preset camera types in the Film Gate menu. Choosing one of those options sets the aperture width and aperture height to suit on its own. Aperture Width/Height Through the Aperture Width and Height sliders you steer the dimensions of the camera’s aperture, or on a real-world camera the slice of the camera that admits light. Across video and film cameras, the aperture is the mask opening that marks the slice of each frame laid bare. The Aperture control runs in inches as its unit of measurement. Resolution Gate Fit Fixes how the film gate sits inside the resolution gate. This bears on things only where the aspect of the film gate parts ways with the aspect of the output image. NOTE: This setting lines up with Maya’s Resolution Gate. The modes Overscan, Horizontal, Vertical, and Fill line up with Inside, Width, Height, and Outside.
