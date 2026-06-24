# Apple Immersive Workflow (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Apple Immersive Workflow

This chapter walks through producing immersive material for the Apple Vision Pro VR headset out of footage captured on the Blackmagic URSA Cine Immersive camera.

### Blackmagic URSA Cine Immersive

Standing as the first commercial camera system built expressly to record immersive material for the Apple Vision Pro, the Blackmagic URSA Cine Immersive leads the field. A pair of 8K sensors capture 3D video across a 180-degree field of view, delivering genuine stereoscopic depth. Backed by 16 stops of dynamic range and 90 fps recording, it lets filmmakers craft ultra-realistic, high-fidelity cinematic experiences. Footage is recorded in the stereoscopic Blackmagic RAW Immersive format, which opens the door to precise color management and HDR postproduction within DaVinci Resolve Studio.

### Blackmagic URSA Cine Immersive

### Apple Vision Pro

The Apple Vision Pro, a mixed-reality headset, fuses virtual and augmented reality together with real-world interaction to deliver a seamless experience.

### Apple Vision Pro

### Immersive Video and Spatial Audio

As a next-generation cinematic format, Immersive Video is built to surround viewers in lifelike, three-dimensional experiences. Where conventional 360° or VR formats fall short, Immersive Video puts realism and depth first, captured through dual lenses and per-eye sensors at a fidelity nearing human 20/20 vision. Purpose-built encoding formats — MV-HEVC and AIVU — keep playback smooth and motion hyperrealistic. Paired with Spatial Audio, the format produces the feeling of actually standing inside the scene. Spatial Audio, for its part, is a transformative sound technology that yields a three-dimensional listening experience. Through advanced algorithms and object-based mixing, it places individual sounds within a virtual space. That permits exact positioning of voices, instruments, and effects, deepening immersion whether you’re watching a film, listening to music, or gaming. Thanks to head tracking, the soundscape shifts on the fly with the viewer’s movements, pinning audio to the live environment for a realistic effect.

### DaVinci Resolve Studio

As a comprehensive post-production application, DaVinci Resolve Studio knits together editing, color correction, visual effects, motion graphics, and audio postproduction in one place. It accommodates workflows shaped around the Blackmagic RAW Immersive format’s distinct traits – stereoscopic video at ultra high resolution, frame rates reaching 90 fps, plus mixing for Spatial Audio. Thoroughly capable of producing, monitoring, and delivering Apple Immersive Video, DaVinci Resolve Studio makes a potent tool for anyone creating immersive content.

### Davinci Resolve Studio Interface

### Workstation Recommendations

### Hardware recommendations

- Mac Studio M3 Ultra Desktop
- High refresh rate monitor (minimum 60Hz)

### Minimum system requirements

- macOS 15 or later
- 64 GB of system memory
- For monitoring, Blackmagic Design Desktop Video 12.9 or later
- Apple Silicon based computer or GPU which supports Metal

### Immersive monitoring requirements

- Apple Vision Pro
- High-speed wireless network (Wi-Fi 5 minimum; Wi-Fi 6 preferred)

### Project Setup

Ahead of importing Blackmagic URSA Cine Immersive raw media, it pays to step through DaVinci Resolve’s project settings so the footage is debayered and processed properly, giving you the best visual results and an easier edit.

### Master Settings

It matters greatly that you flag, while setting up a project, that your content is bound for the Apple Vision Pro. Doing so surfaces every correct setting and workflow option as you prepare, assemble, and deliver the project. 1 Launch DaVinci Resolve Studio. 2 At the Project Manager window’s bottom-right edge, click New Project. 3 Type a project name, set the Media Location (where required), and click Create. 4 Bring up the Project Settings by clicking the gear icon at the lower right of DaVinci Resolve Studio. 5 To begin, you’ll establish the project’s resolution and frame rate. 6 Pick Master Settings from the sidebar. 7 Within the Timeline Format section, tick ‘Enable Apple Immersive workflow’.

Tick the Enable Apple Immersive workflow option found within the Timeline Format section of the Master Settings window. That single choice sets numerous DaVinci Resolve settings to best suit immersive workflows. Whenever you start an immersive project, always select this option before anything else. 8 Switch the ‘Timeline resolution’ to ‘8160 x 7200 Immersive’ so the clips process at their native sensor resolution. Short on processing power? Pick ‘4080 x 3600 Immersive’ to halve the resolution and play back faster. The ‘Timeline frame rate’ ought to read 90 frames per second. Enabling Apple Immersive workflows sets this parameter for you automatically. 9 Put the ‘Playback frame rate’ at 90 frames per second for the truest reproduction of your Immersive video material. With limited processing power (or a monitor whose refresh rate is lower), drop the frame rate for steadier playback. The advice is to pick a frame rate that divides evenly into the native one, such as 30fps or 60fps.

### Timeline Format Settings

### Video Monitoring

Should you run an external monitor (through a capture/playback device such as Decklink or UltraStudio), set up the video monitoring settings according to that monitor’s specs. 1 Within the Video Monitoring section, make the Video Resolution equal your monitor’s resolution. E.g. 1920 x 1080 HD or 3840 x 2160 Ultra HD. Even though immersive video runs at a native 90 fps, that’s a frame rate few broadcast monitors can handle. 2 Make the Format equal your monitor’s frame rate. E.g. 30p.

### Video Monitoring Settings

### Image Scaling

The Image Scaling settings make certain the immersive media’s resolution and aspect ratio show up correctly in the viewer. Enabling the Apple Immersive workflow option back in the Master Settings would already have set these parameters, but it’s worth confirming they’re right. 1 Pick Image Scaling from the Project Settings sidebar. 2 Within the Output Scaling section, confirm that ‘Match timeline settings’ is unticked.

3 Confirm the ‘Output resolution’ is Custom and reads 4320 x 4320. Drop it by half (2160 x 2160) for smaller displays and/or quicker playback. Square aspect ratio resolutions like these are mandatory both for playing Apple Immersive video material inside DaVinci Resolve Studio and for streaming it to the Apple Vision Pro (over wifi or a developer strap). 4 Confirm that ‘Mismatched resolution files’ is set to ‘Stretch frame to all corners’.

### Image Output Scaling Settings

### Color Management

Because you need fine command over the peak output nit luminance, the recommended approach to color management leans on Color Space Transform (CST) nodes on the color page. What the color management settings in the Project Settings aim to do is pin down the color page’s timeline (or ‘working’) color space and define the color space metadata that travels with the rendered file. 1 Pick Color Management from the Project Settings sidebar. 2 Keep ‘Color science’ at DaVinci YRGB. 3 Set the ‘Timeline color space’ to DaVinciWG/Intermediate. As a future-proof wide gamut color space built for HDR workflows, it suits Blackmagic URSA Cine Immersive media and Apple Vision Pro deliverables perfectly. 4 Set the ‘Output color space’ to ‘P3-D65 ST2084 1000 nit.’ That color space supplies a fitting gamut when you monitor the DaVinci Resolve viewers via a Mac Studio Desktop, whose display is typically Display P3. Working on a grading monitor or under a different Apple ICC profile means changing the output color space to align with your display’s color standard. You’ll also have to alter the gamma (transfer function) so it maps onto the ICC profile correctly. 5 Just above the color space settings, click ‘Use separate color space and gamma’. That action breaks the color space and gamma dropdown fields into two. 6 Set the output gamma (over in the right column) to ‘Rec.2100 ST2084.’ 7 Tick ‘HDR mastering is for 1000 nits.’

Apply these Color Management settings. So that your next Apple Immersive project takes less time to set up, you can store the present settings as a preset. 8 Open the three-dot options menu at the upper right of the Project Settings window and pick ‘Save Current Settings as Preset’. 9 Give the preset a name and click Ok. Next time you handle Immersive media, configure the project settings in a snap: open the Project Settings window, click the options menu, and pick the listed preset. 10 Click Save to dismiss the Project Settings.

### About DaVinci Wide Gamut

Developed for DaVinci Resolve, DaVinci Wide Gamut is Blackmagic Design’s sophisticated internal color space, furnishing an unusually wide and accurate arena for color grading and image processing. Coupled with the DaVinci Intermediate gamma, it yields one cohesive working space that eases color management across a mix of camera formats and holds tone and saturation mapping consistent from input through output. Well suited to HDR and Immersive media, this wide gamut lets colorists make subtle tweaks without courting banding or tonal clipping while mastering for high-fidelity delivery formats.

### Apple Immersive Processing

Within the Project Settings sidebar, the Apple Immersive section lets you supply custom ILPD (Immersive Lens Profile Data) to change how the immersive content gets calibrated and projected. 1 Pick Apple Immersive from the Project Settings sidebar. 2 Click Open Calibration Folder. 3 Drop in or refresh a custom ILPD file. 4 Click Update Lists so the ILPD content reachable in the Media Pool is refreshed. 5 Click Save to dismiss the Project Settings. 6 Over in the Media Pool, right-click an immersive clip. 7 From the contextual menu, head to Apple Immersive Calibration; here your choices are the source ILPD (‘No Apple Immersive Calibration File Selected’), a custom ILPD, or the gap ILPD. TIP: Out of the box, the folder holding the custom ILPD Calibration lives within ProIM, right beside the default LUT folder.

### Ingesting

As you import raw immersive content, both eyes plus every bit of associated immersive metadata come along inside the imported .braw clip. 1 Head to the media page. 2 In the Media Storage panel, browse to where the immersive video content lives. 3 Drag the media down into the Media Pool below. TIP: To preserve the original folder layout, drag folders out of the Media Storage panel onto the Media Pool sidebar. Dropped into the Master bin (or any bin you’ve made), the folders and their subfolders stay intact.

Select an Apple Immersive video clip and the codec parameter atop the Metadata panel labels it an Immersive Video, right next to its native frame rate and resolution. On top of that, a 3D icon down in the lower left of the video thumbnail likewise verifies it as a 3D clip.

The Metadata Panel displaying an immersive video The icon at lower left marking a 3D stereo clip

NOTE: The first time you drag immersive media into the Media Pool, a dialogue window may ask whether you want to Keep Settings or Change Settings. Picking Change Settings makes the Project Settings take on the source media’s frame rate and resolution on their own.

### Editing

While handling immersive content, the editing tools and actions stay largely identical to those you’d use on ordinary 2D video formats. The instructions that follow cover edit features and actions found only in immersive video workflows.

### Assembly

As you preview clips while assembling the timeline, you can switch which eye (left or right) the source viewer shows. Apart from that, building a cut on the timeline works just as it does in standard NLE workflows. 1 Head to the edit page. 2 Double-click a clip so it loads into the source viewer on the left. A label across the top of the viewer tells you which eye is on display.

The label up top tells you the left eye is what you’re viewing

3 To swap the eye shown in the viewer, right-click the source clip over in the Media Pool and pick Stereoscopic 3D > Stereoscopic 3D Mode > Left Eye/Right Eye/Both Eyes.

TIP: Hovering over the thumbnails in the Media Pool also scrubs clips in the source viewer, provided Live Media Preview is switched on in the source viewer options. 4 Lean on the I and O shortcuts to mark out a range in the source viewer. 5 Hit Insert Clip on the toolbar (or the F9 shortcut) to drop clips onto the timeline.

TIP: Dragging clips out of the Media Pool onto the timeline panel works as well. 6 Trim clips on the timeline with your mouse (while in Selection or Trim Edit mode).

### Backdrops

Tick ‘Enable Apple Immersive workflow’ in the Project Settings and a Backdrops track (‘BD’) shows up on its own beneath the Video 1 track. The term backdrops describes whatever the viewer sees once they look past the edge of the immersive video content, an edge usually capped at a 180–210 degree field of vision. That zone is black by default, yet you can drop custom background imagery (in the .usdz format) onto the backdrops track.

Pull a .usdz backdrop file onto the Backdrops track to place it on the timeline. A backdrop image’s duration has to line up with the clip boundaries over in the video tracks. One backdrop file may cover a single clip, several clips, or the whole timeline, but it can’t break partway through an immersive .braw clip (the so-called ‘L-cut’). Reach for the usual trimming controls to set the backdrop file’s length. Drag the .usdz file’s edge (while in Selection or Trim Edit mode) to change its length.

### Trim Controls

The , (comma) and . (period) commands are another option for inching the trim edge along a single frame per press. TIP: So that backdrops stay locked to the Immersive Video edits, switch on Snap mode from the edit page toolbar.

### Using the Viewer

As a default, the DaVinci Resolve page viewers present immersive clips inside the circular ‘lens space’. The visual lens calibration that projects the image comes from the camera and differs for each individual clip.

The DaVinci Resolve page viewers presenting an immersive clip inside the circular ‘lens space’ You can also flip the view mode over to LatLong or Viewport. 1 Down at the lower left of the timeline viewer, click the drop-down arrow beside the onscreen controls button. 2 Pick Immersive.

Pick Immersive from the timeline viewer’s drop-down menu to switch your view mode A fresh toolbar shows up over the viewer carrying further view options.

3 Click LatLong for an equirectangular projection of the image. This mode bends the image so it sits closer to the proportions of traditional 2D media, which smooths certain post-production tasks like tracking and compositing.

The LatLong option presents an equirectangular projection of an image 4 Click Viewport for a center cutout of the immersive scene framed as a square. This mode lets you read the scene’s correctly-proportioned details plainly on a standard monitor, though you’ll want to stay alert so no off-frame action slips by. Up top, the transform controls in the immersive toolbar let you tilt and pan the stereoscopic image within the frame and dial in the horizontal and vertical fields of view.

Picking Viewport gives you a center cutout of the immersive scene framed as a square

### Transitions

Moving from one immersive video clip to the next, you can make a straight cut, drag the handles flanking the clip to fade in or out, or apply a Dip To Color Dissolve effect. Transitions ought not be baked into the footage; instead the Apple Vision Pro renders them itself at playback. 1 Open the Effects panel. 2 In the sidebar, work your way to Toolbox > Video Transitions. 3 Pull Dip To Color Dissolve onto a cut point sitting between two clips.

### Dip To Color Dissolve effect

NOTE: Applying a transition demands sufficient trim data past the cut points of both clips. Without enough trim data (the ‘handles’), the transition won’t take. 4 Within the Inspector panel, open the Transition tab and tick Render Bypass. That guarantees the Apple Vision Pro renders the dissolve correctly. 5 From there, the rest of the parameters in the Dip To Color Dissolve Inspector let you change the transition’s duration, alignment, animation speed, and color.

Further parameters within the Dip To Color Dissolve Inspector panel

### Apple Immersive Motion Data

With immersive content, fast or abrupt camera moves can throw the viewer off. For the sake of viewer comfort, steer clear of takes that have snappy pans/tilts, rotating motion, or crooked horizons. The Apple Immersive Motion Data feature plots the x, y, and z acceleration along with gyroscope position values, giving an objective picture of where the camera’s motion may be too forceful. Editors lean on that readout to steer away from disorienting stretches of footage. 1 Right-click an immersive clip out on the timeline. 2 Pick Apple Immersive Motion Data.

Pick the Apple Immersive Motion Data feature as an aid for steering clear of disorienting stretches of footage

A graph turns up in the video track charting the x, y, z acceleration rates In this case, the camera kept rolling while the operator was still rigging it. Those spikes in the graph mark abrupt movement as the camera got lifted, turned, and set on his shoulder. The better choice is the back half of the video, where the readouts flatten out once the camera has settled. Up at the graph’s top left, click the displacement arrow.

### Select the Axis to view

Readouts can be switched on or off depending on what the shot contains and how the camera was moving.

### Titles

On the edit page, text can be laid into an immersive scene with any of the Effects panel’s title tools – Text, Text+, MultiText, Scroll, and the various lower third options. Set above an immersive clip, the title generator draws on that clip’s ILPD (Immersive Lens Profile Data) to bend the text precisely to the scene’s lens warp. Where no ILPD exists (say, when you put text over a black backdrop or an immersive CGI scene), default lens distortion steps in so the text still looks suitably warped through the Apple Vision Pro. 1 Within the Effects panel, head to Toolbox > Titles. 2 Drag the Text generator onto the timeline. Drop it on a video track above an immersive clip to fold it into the scene. Like backdrops, Text generators can’t straddle clip boundaries. Since every clip renders with its own lens space, any title spilling across shots risks getting warped between them. 3 Trim the title back to the video edit point(s). 4 Turn to the Inspector to compose and style the title text. 5 Open the Settings tab and work the Convergence slider to place the text within 3D space. Slide it left to push the title deeper, or right to pull it nearer.

Convergence reads most clearly while you monitor on the Apple Vision Pro. Relying on other monitoring methods, you can alter how text convergence shows in the viewer by switching the Vision mode of the video layer beneath it on the color page. 6 Head to the color page. 7 Open the 3D palette. Mid-palette, the Vision column lets you swap the stereoscopic standard that projects the immersive media. 8 Pick the Stereo tab. 9 Set the Out mode to Anaglyph (Color).

Adjusting the text generator’s Convergence parameter back in the edit page’s Inspector panel becomes far more intuitive once you view it through anaglyph (or anachrome) glasses.

### Creative Considerations

So early in the life of the Blackmagic URSA Cine Immersive camera, with Apple Vision Pro production just beginning, the encouragement to filmmakers is to play with the format, surfacing best practices, setting fresh rules, and uncovering workflows that conventional filmmaking never pictured before.

Keeping that in view, several facets of immersive production have already been singled out for extra care, all toward keeping audiences fully absorbed and visually at ease.

- The edit should be in mind from pre-production onward. Given the particular demands of shot length and audience motion comfort, filmmakers have to shoot scenes already thinking of the final cut.
- Keep clips with fast camera moves to a minimum or skip them, since they can disorient the viewer. Favor locked-off shots or gentle pans and dollies instead.
- Tilted or extreme camera angles can disorient too – go with takes that sit level to the subject and at an easy distance (not crowded in close).
- Fresh environments take more time to take in within immersive media than they do in a 2D scene. Slow your cuts down so the viewer can adjust to each new setting.
- As you cut from clip to clip, keep track of where the viewer was likely looking during the earlier shots. Don’t stage key action on the left of the frame if the audience’s gaze was just drawn toward the right.
- Spatial Audio carries a great deal of the storytelling – think of it as one more character in immersive productions.

### VFX Compositing

Switch ‘Apple Immersive workflow’ on in the Project Settings and purpose-built Fusion parameters open up smooth stereoscopic workflows and immersive-compliant compositing. MediaOut nodes offer left and right eye output choices, while the Immersive Patcher tool handles equirectangular projection and composition.

### MediaOut nodes

The first time you step onto the Fusion page with an immersive clip loaded, the Nodes graph holds a pair of MediaIn nodes wired to their two matching MediaOut nodes.

The nodes graph carries two MediaIn nodes wired to two MediaOut nodes Inside the MediaOut Inspector, the Stereo Eye parameter serves to route the eye signal output.

### The Stereo Eye parameter

Out of the box, MediaOut1 maps to the Left eye and MediaOut2 to the Right. With that arrangement you can dive straight into building stereo-compliant composites and graphic overlays. Those twin MediaOut nodes also push two signal variants into the color page’s node editor for additional image refinement. Reach the MediaOut2 signal on the color page by right-clicking in the node editor and picking ‘Add Source’.

Adding the MediaOut2 source into the node editor. Set the Stereo Eye parameter to Auto and the MediaOut node merges the signals, handing them to the correct eyes on the timeline. That lets you run Fusion’s multilayer workflow to feed both left and right signals into one MediaOut node.

### Renderer3D

For 3D graphics or CGI on an immersive timeline, the Renderer3D node provides several eye setups along with the capacity to process both left and right layers.

That opens the door to building elaborate 3D titles or whole CGI scenes and feeding them straight onto a stereoscopic timeline in immersive projects With this setup in play, the drop-down menu at the top right of the Fusion viewers lets you toggle between the left and right eye of your composition.

The Fusion viewers’ drop-down menu lets you toggle between the left and right eye

### Compositing with the Immersive Patcher

The Immersive Patcher tool lets you briefly ‘undistort’ a stretch of an immersive clip so tracking, painting, and compositing become easier on a flat plane. When you’re done, a second Immersive Patcher re-distorts the immersive signal and folds the freshly composited elements back into the scene. 1 Drop Immersive Patcher into the node pipeline. The immersive patcher 2 Within the Inspector, click Undistort.
