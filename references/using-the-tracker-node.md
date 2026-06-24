# Using The Tracker Node (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Using the Tracker Node

This chapter walks through everything the Tracker node in Fusion can do, opening with how trackers wire into your node trees and closing with the various jobs they can carry out.

### Introduction to Tracking

For any compositor, tracking ranks among the handiest and most indispensable techniques around. Loosely put, it's the building of a motion path by analyzing a particular region of a clip across time. Fusion ships several distinct tracking nodes so you can analyze different sorts of motion. Once a clip's motion is tracked, the resulting data feeds stabilization, motion smoothing, matching one object's movement to another's, and plenty of other vital jobs. Types of tracking nodes in Fusion: Tracker: Trails a comparatively small, recognizable feature or pattern within a clip to derive a 2D motion path. People sometimes call this point tracking. Planar Tracker: Trails a flat, unchanging surface region of a clip to derive a 2 ½D motion path that includes perspective. A planar tracker also copes better than a point tracker when some tracked pixels slip offscreen or get hidden. Camera Tracker: Trails several points or patterns across a clip and runs a more elaborate analysis by comparing how those patterns move. The payoff is a faithful rebuild of the live-action camera inside virtual 3D space. In this manual each tracker type is given a chapter of its own. The Tracker node and its tracking techniques are what the present chapter addresses.

### Tracker Node Overview

The Tracker node is a single node that actually handles tracking, stabilizing, match moving, and corner-pinning operations. Because the Tracker node can transform the foreground input, it can generate tracks and then stand in as a Merge within a match move or corner-pin setup. Alternatively, you can have it produce tracking data alone and then publish that data to other nodes in the Node Editor.

### Modes of the Tracker Node

The Tracker node is a remarkably versatile tool, often dropped into a composite several times to assist with dozens of jobs. Most of those jobs, though, distill down to a handful of operations. The Tracker node provides four operation modes that span the bulk of tracking situations.

### Stabilizing

One or more tracked patterns can serve to strip all motion out of a sequence, or to even out vibration and shakiness. Stabilizing from a single tracker pattern fixes only the X and Y position. Combine multiple patterns and you can stabilize position, rotation, and scaling.

### Match Moving

Stabilizing's opposite is match moving, which reads position, rotation, and scaling within a clip from one or more patterns. Rather than removing that motion, it lays the motion onto another image so the two images can be composited as one.

### Corner Positioning

Corner positioning tracks four patterns, which then map the four corners of a fresh foreground into the background. The technique is typically used to swap out signs or mobile phone screens. For tasks of this sort, the Planar Tracker node is frequently the better opening move.

### Perspective Positioning

Perspective positioning likewise tracks four patterns to pinpoint the four corners of a rectangle. Each corner then maps to a corner of the image, rescaling and warping it to strip away all apparent perspective. For removing perspective from a clip, the Planar Tracker node is frequently the better opening move.

### Basic Tracker Node Operation

Three fundamental steps underlie every tracking workflow. 1 Wire whatever image you wish to track into the yellow background input of the Tracker node. 2 Define the tracking pattern, then analyze the clip so a path is created. 3 Put the resulting tracking data toward stabilizing, match moving, corner pinning, or removing perspective.

### Connect to a Tracker's Background Input

The starting move is to wire the output of whatever image you want to track into a Tracker node's background input. The Tracker node analyzes the image attached to its background input. You can slot the Tracker node serially among other nodes if you mean to use the Tracker node itself for a simple stabilization, or to have it carry out a Merge node's role within a match move or corner-pin operation.

A serially connected Tracker node that can both track and transform the images coming in. However, when you're merely using a Tracker node to analyze data destined for several nodes elsewhere in the comp, you might branch it and leave its output unconnected to signal that the Tracker node is a data repository. Note that this isn't required; serially connected Tracker nodes can link to multiple other nodes as well.

A branched Tracker connection, signaling that it ties to other nodes rather than being used on its own

### Analyze the Image to be Tracked

With the node tree built and the Tracker inserted where you want it, you can set the tracker up in the viewer. You pick out one or more features in the image to track (these are called patterns) by adding trackers (one comes by default) and, using the viewer's onscreen controls, positioning them. Once the clip has been analyzed by the Tracker node, the tracking data that results lives inside that Tracker node. Keyframes, one for each frame, mark the Tracked Center X and Y data that's been saved, while a motion path traces the tracked data's route in the viewer.

A motion path marking the tracked motion, together with tic marks flagging keyframes of tracking data

### Apply the Tracking Data

Two routes let the tracking data held inside the Tracker node go toward stabilizing, match moving, corner pinning, or removing perspective. Method 1: Use the Tracker node to match move and merge A foreground image can be attached to the Tracker node, with the motion drawn from the analyzed background image then applied to it.

Using a Tracker node in line for a match move

Set the Operation parameter on the Operation tab of the Inspector to Match Move, Corner Position, or Perspective Position, and the motion always lands on the foreground input (where one is connected). For simple cases the workflow is straightforward. Here a Merge node's role can fall to the Tracker node, given that Tracker nodes carry all the same functionality a Merge does. Handling a match move and merge together in one Tracker node. Method 2: Connect specific parameters to the Tracker Node Another path is to feed the Tracker node's tracking data into the specific parameters of other nodes that handle the real work, useful where a match move setup amounts to more than merely transforming a foreground image. Without any direct wiring in the node tree, each Tracker node—and each pattern inside it—publishes its data for other nodes to draw on. To illustrate, the node tree below puts an Ellipse node to work isolating a glow effect on the ray gun prop.

A Tracker set up as a branch, wired through the Connect To menu. Because the ellipse has to track the ray gun's motion, a Tracker node analyzes how the gun tip moves, and that tracking data then drives the ellipse's animation. Rather than tying to the tracker directly through the foreground input, the ellipse connects indirectly, by way of the Connect To contextual menu.

Lighting a ray gun by wiring tracking data into the center position of an Ellipse node. Things go more smoothly after you rename the Tracker you built to something that describes whatever's being tracked.

Renaming trackers in the Tracker List—double-click one and type descriptive text. After the ray gun's tip is tracked, that tracking data feeds into the Center parameter of an Ellipse node confining a Glow effect; you do this by right-clicking the Center parameter's label over in the Inspector and picking Tracker1 > Ray Gun Glow: Offset position out of the Connect to submenu on the contextual menu. Within that submenu appear the data from every Tracker node across your node tree along with each tracking pattern, and since the Tracker was named, finding it is simple. Offset position is our pick because it drops the ellipse's center squarely onto the path. It still, though, leaves us free to offset the ellipse if needed, by way of the offset controls in the Inspector.

A right-click on a parameter's label is what lets tracking data hook into it for animation. A Tracker node's data can be routed into any other node's parameter, though most often you'll wire track data into center, pivot, or corner X/Y style parameters. Using tracking data in this fashion, you needn't connect the Tracker node's own output to anything else across your node tree; once you link it via the Connect To submenu, the data flows from the Tracker straight to the Center parameter.

### Viewing Tracking Data in the Spline Editor

Within the viewer, tracking data turns up either as a path or, over in the Spline Editor, as a displacement spline. Either place lets you shape that tracking data. The Tracker's default is a displacement spline, which tells you how far the tracking point has drifted from where it began. That suits velocity adjustments well, yet it says nothing about direction. When you need to nudge a handful of points one way or another, the displacement spline can be converted into an X and Y coordinate spline. A right-click on a parameter's label is what lets tracking data hook into it for animation. A right-click in the viewer brings up a contextual menu. Sitting at its very bottom is a reference to the path the Tracker created, named Tracker1Tracker1Path:Polyline. Pick it and a longer submenu opens where Convert to XY Path is available. To read more about Displacement Splines, turn either to the DaVinci Resolve Reference Manual, Chapter 72, "Animating in Fusion's Spline Editor," or else to the Fusion Reference Manual, Chapter 10.

### Tracker Inspector Controls

How the Tracker node's tabs are laid out in the Inspector mirrors this workflow. It breaks into three principal Tracker tabs, plus the common Settings tab.

- The Tracker Control tab: This is where you build onscreen trackers to aim at patterns, and where the controls for running the required track analysis live.
- The Operations tab: This is where you settle how the tracking data gets used.
- The Display Options tab: This is where you tailor how the onscreen controls

look in the viewer.

The Tracker Operations tab The Tracker Display Options tab

### The Tracker Control tab

### Motion Tracking Workflow In Depth

Tracker nodes serve a pair of purposes. They give you a way to analyze an object you want to follow, and they act as a container for the track data that results. That lets you use one node for the analysis and hand that analysis off to any other node that needs it. What follows is a closer breakdown of the tracking process.

### Connect the Image to Track

Whether or not you actually put the Tracker node itself to work on the tracking data, a successful analysis still depends on the image you mean to track being wired into the background input (yellow) of a Tracker node. The Tracker node does carry a foreground input, but for purposes of tracking analysis it's disregarded at the outset, so even with a foreground attached, only the background gets drawn on throughout the analysis process.

Wiring the output of a MediaIn node into the background input on a Tracker node

### Add Trackers

Although each Tracker node opens with a single tracker pattern, one node can analyze several tracking patterns added to the Tracker List, so several features of an image get tracked together for later use while supporting different kinds of transforms. To add more trackers, click the Add button sitting just above the Tracker List control.

Adding another tracker by clicking the Inspector's Add button. Multiple patterns prove useful while you stabilize, match move, or strip perspective out of a clip. They also spare the Node Editor from clutter, folding into a single node what would otherwise call for several nodes.

Working in the Tracker list:

- To select a tracker: Click whichever Tracker name you'd like to select.
- To rename a tracker: Renaming trackers makes them easier to refer back to down the line. Say you're tracking a car door handle—name that Tracker "Car Handle" and it'll be simple to locate later. The way to do so: just double-click the Tracker's default name in the Tracker list, type a fresh one, and press Return.
- To delete a tracker: Select a tracker and click the Delete button.
- To disable, suspend, or re-enable trackers: Beside each tracker's name in the Tracker List sits a checkbox—click it. The checkbox is a three-way toggle cycling among Enabled, Suspended, and Disabled.

Enabled: Each time the track runs, an Enabled tracker re-tracks its pattern. Other nodes have its path data on hand, and that data is available for stabilization and corner positioning. Suspended: A gray checkbox means it's Suspended. In this state the pattern isn't re-tracked when the track runs. While the data is locked against further changes, the path's data remains on hand for other nodes. It's also available for advanced tracking modes such as stabilization and corner positioning. Disabled: When tracking runs, a Disabled tracker produces no path. Neither other nodes nor advanced tracking operations like stabilization and corner positioning can reach its data.

### Position the Pattern Boxes

A pattern is the patch of pixels targeted for tracking within an image by way of a pattern box. In the viewer, a rectangle marks out the pattern box whenever a tracker is active. A single Tracker node can hold many pattern boxes, each aimed at a different pattern. Every tracked pattern produces a motion path of its own. Click on any portion of a tracker's onscreen controls and it gets selected. Selected pattern boxes turn red, while deselected ones turn green.

A pattern box positioned over an eye you want to track

When you add a Tracker node to the Node Editor, you begin with one pattern box shown in the viewer as a small rectangle. Bring the cursor over the pattern rectangle and the control grows, revealing two rectangles. A dashed line forms the outer rectangle, and a solid line forms the inner one. The outer rectangle is the search area; the inner rectangle is the pattern. To pick a new pattern, you can shift the pattern box by dragging the small (and easily overlooked) handle at the top left of the inner pattern box.

Dragging from its upper-left corner to reposition a pattern in the viewer.

As you move the pattern box, an overlay pop-up appears showing a magnified view of the pixels inside the rectangle to help you place the pattern precisely via the crosshairs within.

A magnified view that surfaces as you drag a pattern box, aiding placement. Sizing a pattern box around the tracking point on the ray gun.

The pattern rectangle can be resized as well by dragging on its edges. Aim to size the pattern box so it wraps the detail you intend to track while excluding whatever is irrelevant. Ideally, see to it that each pixel of the pattern under track sits on one common plane, and that no portion of the pattern is in fact an occluding edge standing ahead of what you truly mean to track. Resizing the pattern box happens outward from the center, so one drag builds any rectangle you require.

TIP: The magnified pattern box pays no attention to viewer LUTs. With Log content, placing the tracker may go easier if you briefly drop a Brightness Contrast node between the source content and the tracker's yellow input. The Brightness Contrast node can then temporarily boost the visibility of the region you're tracking.

### Refine the Search Area

A second rectangle, this one with a dotted border, encloses the pattern box. This is the search area. As tracking advances from one frame to the next, the Tracker examines the region the search area defines, which surrounds the last known tracker position, trying to relocate the pattern. A larger search area improves your odds of successfully tracking fast-moving objects, but it lengthens the track. There are, however, ways to tune tracking for particular content. Tracking a pattern that races across the screen from left to right, for one, calls for a wide search area but not a very tall one, since all the movement is horizontal. Should the search area be smaller than the pattern's frame-to-frame movement, the Tracker will likely fail and latch onto the wrong pixels, so it pays to weigh the motion's speed and direction as you set the search area. To resize the search area, drag along the edges of that dotted outline

### Perform the Track Analysis

Before analysis begins, you'll want a render range laid down in the Time Ruler that covers the stretch of frames where the pattern stays visible. That might be an entire clip or just a small slice of it. According to the kind of motion under track, you may wish to bring in the Adaptive Mode option as an analysis aid (more on that below). With your options settled, any of the tracking transport buttons up at the top of the Inspector will kick off tracking. With tracking underway, the Node Editor stays off-limits until it finishes.

### The tracking transport buttons and analysis parameters

To begin tracking, do one of the following:

- Click the Track Reverse button, which begins tracking at the render range's very end.
- Click the Track Backward from Current Frame button, which tracks backward starting at the playhead's present position.
- Click the Track Forward button, which begins tracking at the render range's very start.
- Click the Track Forward from Current Frame button, which tracks forward starting at the playhead's present position.

On its own, pattern tracking stops once it hits the render range's end (or its start when you're tracking backward), though you're free to cut in and halt tracking at any moment. To stop tracking, do one of the following:

- Click the Stop Tracking button in the tracker transports.
- Click Stop Render at the bottom of the Fusion window.
- Press the Escape key.

Once tracking finishes, the path attaches to the pattern. That pattern's path can now be wired into another node or put toward more advanced operations like stabilization and corner positioning. With the track complete and presumably good, you can apply the various techniques in this chapter to put the track to work in your composition.

### Tips for Choosing a Good Pattern

The Tracker operates by hunting each frame for the pixels held in the pattern. For a track to succeed, a reasonably high-contrast and distinctive region of the image has to be present in the footage. This step is known as pattern selection. The first part of pattern selection is to screen the footage you'll track several times over. Keep an eye out for candidate patterns that stay visible through the whole range of frames, where the contrast runs high and the pattern's shape holds steady over time. The more distinctive the pattern, the better the odds the track succeeds. Along with spotting high-contrast, well-defined patterns, watch for the frames where the pattern travels the most. Pinning down the full extent of a pattern's motion helps you settle on the right size for the pattern search area. It's not unusual for a scene to need several different patterns to build one path. Most often this happens because the pattern leaves the frame or is briefly hidden by another scene element. Merging patterns into a single pattern is covered later in the chapter.

### Selecting the Pattern's Image Channels

When a patch of pixels is selected as a pattern, the Tracker automatically picks the color channel used for tracking it, drawing on an analysis of each channel for contrast, clarity, and reliability. Within the node controls, the bars off to the right of the Pattern display window highlight whichever channels were chosen. To override that automatic channel choice, click the buttons beneath each channel's bar and thereby decide which channel does the tracking.

For tracking a pattern, you're free to pick any single color channel, either luminance channel, or the alpha channel.

Highlighted channel bars indicate which channel is selected for tracking When picking a channel, the aim is to choose the cleanest, highest-contrast channel for the track. Steer clear of channels carrying lots of grain or noise. Bright objects against dark backgrounds frequently track best on the luminance channel.

### Selecting Patterns for Stabilization

Picking patterns for stabilization can be a delicate affair. Where a pattern sits at the moment it's selected determines exactly how the image gets stabilized. Correcting for rotation needs at least two patterns; three patterns will correct for scaling, and more usually sharpens the solution. Resist the urge to grab just any seemingly valid pattern in the sequence, since some patterns degrade the solution rather than improve it. To steer your choices, lean on the following guidelines while selecting patterns for stabilization.

- Place patterns at the same relative depth within the image. Objects deeper in the background travel by greater amounts than objects in the foreground, thanks to perspective distortion. That can throw off the stabilization calculations, which don't account for depth.
- Place patterns whose positions are fixed relative to one another. Patterns shouldn't be able to move with respect to each other. A sign's four corners would make excellent candidates, whereas the faces of two different people in the scene would be terrible choices for patterns.

### Using the Pattern Flipbooks

Every pattern carries a pair of thumbnail windows shown in the Inspector. The left window displays the selected pattern, while the right window refreshes during the track to display the actual pattern acquired for each frame.

### The Tracker Pattern Selection and Flipbook thumbnails

Each stored pattern joins a Flipbook. After the render finishes, you can play this Pattern Flipbook to gauge how accurate the tracked path is. Spot any jumps between frames and you'll know something probably went wrong.

### Using Adaptive Pattern Tracking

Even the most ideal pattern usually goes through shifts in profile, lighting conditions, and other variables. Such changes can damage pattern recognition to the point where a pattern stops being usable. To help offset these conditions, the Tracker provides three pattern-acquisition modes you can apply while tracking. Those modes are set through the Adaptive Mode options in the Inspector.

### The Adaptive Mode options

### None

With the Adaptive mode set to None, the pattern inside the rectangle is acquired the moment the pattern is selected, and that becomes the lone pattern used throughout the track.

### Every Frame

With Every Frame chosen, the pattern inside the rectangle is acquired the moment the pattern is selected, then reacquired at each frame. The pattern found at frame 1 drives the search on frame 2, the pattern found on frame 2 drives the search on frame 3, and onward. This approach helps the Tracker keep pace with changing conditions in the pattern. Every Frame tracking is the slower route and can drift when the pattern undergoes sub-pixel shifts from one frame to the next. Its use is therefore not recommended unless other methods fail.

### Best Match Tracking
