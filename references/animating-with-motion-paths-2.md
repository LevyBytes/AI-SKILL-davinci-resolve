# Animating With Motion Paths (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

With the Record mode, you can capture a control’s spatial and temporal data together in one pass. That comes in handy whenever nailing both placement and pacing matters for the look you’re after. Right-click the path you want and pick Record off the contextual menu, which opens a submenu listing the data types you’re able to capture. Pairing the Record Time option with the Draw Append mode lets you build intricate motion paths that play the movement back exactly as you trace it out. Whatever timing got captured during recording might not line up cleanly with a given project’s requirements. In that case, reshape the path’s Displacement spline within the Spline Editor so the motion better fits what you need.

### Importing and Exporting Polylines

Polyline shapes can move in and out of either a widely supported editable ASCII text file or the program’s own native format. Workflows like these let you stash an especially handy or all-purpose mask or path so you can reuse it later or pull it into a different application, such as Maya or LightWave. Bringing in FXF, SSF, or Nuke shape files is supported as well.

### Native Format

To store a polyline shape using Fusion’s native ASCII format, right-click the header of the Mask node over in the Inspector, then choose Settings > Save As off the contextual menu. Give the file a name and location, then click OK to write out a file carrying the .setting extension. What gets stored is the mask or path geometry together with whatever animation splines drive its points or controls. Bringing that saved setting back into Fusion means first spinning up a fresh polyline of the matching type, then picking Settings > Load from the mask’s context menu, or simply dropping the .setting file straight onto the Node Editor. Should you need to relocate a polyline across compositions, another route is to copy the node onto the clipboard, switch over to your other composition, and paste it in there from the clipboard.
