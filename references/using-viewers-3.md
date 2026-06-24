# Using Viewers (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

A rectangular region akin to the Domain of Definition, the Region of Interest is often shortened to RoI. Yet whereas the DoD informs the node which pixels truly exist within the picture, the RoI informs the node which pixels genuinely have to be rendered. As a node renders, it overlaps the present RoI against the present DoD so as to work out which pixels ought to be touched.

### Enabling RoI Controls

Switching on the RoI controls lets you confine rendering to a small region of the picture and markedly boost performance whenever you're focused on just a small portion of a high-resolution or intricate composition. As an example, when you're applying paint to patch a few holes in a matte across the floor of a composition holding many, many high-resolution layers, 3D, and Lighting operations, the RoI controls let you single out the patch of floor you're tackling, which speeds up caching of that part of the composition considerably. So as to switch on the RoI controls, do one of the following:

- Click the RoI button in the 2D Viewer toolbar.
- In a viewer, right-click and pick Region > Show Region off the contextual menu. Once RoI is switched on and Show Region has been picked from the menu, a rectangular RoI control shows up within the viewer. Should this mark the first occasion RoI has been switched on, it gets sized to the whole width and height of the picture. If not, the RoI's most recent position for that view applies. That said, should you wish to assign the RoI to a custom area inside the frame, you can do one of the following.

To adjust the RoI controls, do one of the following:

- Drag whichever edge of the RoI rectangle to shift one side of the RoI.
- Drag a corner so the RoI rectangle is resized starting from that corner.
- Drag the little circle sitting at the upper-left corner of the RoI rectangle to reposition the RoI while leaving its dimensions alone. Now and then it's quicker to just draw a rectangle wherever you'd like the RoI to land.

To quickly draw the RoI at the desired size: 1 Pick Set out of the viewer menu beside the RoI button, or right-click somewhere inside the viewer and choose Region > Set Region. 2 Once the pointer becomes an RoI drawing cursor, drag inside the viewer to lay out a RoI rectangle. As another route, an Auto command sizes the RoI to cover whatever pixels are on view at the present zoom/pan level inside the viewer. That lets you swiftly cap the RoI to whichever part of the composition you've zoomed in on. To automatically draw the RoI:

- Choose Auto from the viewer menu next to the RoI button.
- Right-click anywhere within the viewer and choose Region > Auto Region.
- Once you've no further need for the RoI, you can reset it.

So as to restore the RoI back to the whole width and height of the present picture, do one of the following:

- Choose Reset from the viewer menu next to the RoI button.
- Somewhere inside the viewer, right-click and pick Region > Reset Region, whether off the contextual menu or via the toolbar button menu.
- Disable the ROI control, which will also reset it.

### While the RoI Is Active

The RoI serves solely for previewing your composition as you work, not for output out of Fusion. As long as the RoI stays active, Fusion only asks for rendering of the pixels within the region whenever it puts an image up in that viewer. Flipbook Previews you make inside that viewer likewise honor the present RoI. MediaOut and Saver nodes invariably draw on the whole image dimensions while writing the image to disk, paying no mind to whatever RoI you've assigned within the viewers. The RoI lifts not only rendering speed and memory use but can additionally trim file I/O, given that Loaders and MediaIn nodes pull in pixels only from inside the RoI when one has been set. Doing so does demand that the file format in use permits direct pixel access. Cineon, DPX, and numerous uncompressed file formats accommodate this capability, along with OpenEXR and TIFF in restricted situations. Do keep in mind that shifts to the viewed image size or color depth will make the pixels beyond the RoI reset to the picture's canvas color. The same occurs while toggling in and out of Proxy mode, and likewise over Proxy mode switching whenever Auto Proxy is switched on. So long as the image size holds steady, so do the most recently rendered pixel values beyond the RoI. That can prove handy when contrasting changes made within the RoI against an earlier node state. TIP: Right-clicking in a viewer and selecting Options > Show Controls to bring up onscreen controls will trump the RoI, compelling renders of pixels across the whole image.

### Managing Viewer Lookup Tables (LUTs)

Lookup Tables, also called LUTs, serve to help line up a viewer's look with where it will eventually be output. In essence they're image-processing operations touching only the image previewed inside the viewer, leaving the image data itself untouched. LUTs can work out color transformations in two fundamental ways: the first being a plain 1D LUT, and the second a more advanced 3D LUT.

- A LUT in its plainest form is a 1D LUT. Handling one color channel at a time, it can produce broad tonality shifts though not highly precise color shifts.
- A 3D LUT examines every conceivable color value (red, green, and blue) on its own. A 3D LUT permits sweeping global shifts plus highly precise color shifts to land on images very rapidly.

### How Lookup Tables Work in Fusion

A Lookup Table (LUT) amounts to a table of values employed to transform an image's color and luminance. Whereas a 1D LUT relies on a two-column table pairing input color with output color, a 3D LUT works more like a matrix. A LUT chiefly serves to compensate for differences in the monitor or in the image's source color space. You may opt to apply a LUT across all the viewers, or apply distinct LUTs to each viewer.

### Image LUTs

Image LUTs are applicable per viewer. You can indeed even apply separate Image LUTs to the A and B buffers belonging to one viewer. Such LUTs apply only to 2D images, never to 3D scenes. Routinely, Image LUTs serve to travel from one scene-referred color space across to another. For instance, when you're handling log-encoded media yet want a look at how the image will appear in the final color space, you can pick a LUT that transforms the image as a preview.

### Buffer LUTs

The Buffer LUT applies across the viewers no matter their contents, 3D scenes, 3D materials, and subview types included. No more than one Buffer LUT may apply. When a 2D image is shown carrying an Image LUT, the Buffer LUT then applies atop the result of that image LUT. Commonly, Buffer LUTs serve to emulate a different output color space particular to the display you're on—say, getting a DCI-P3 projector to render the image the way it would appear on an sRGB monitor. To use a Buffer LUT: 1 Turn off the LUT button sitting above the viewer. 2 Inside the viewer, right-click and pick Global Options > Buffer LUT > Enable. 3 Once more inside the viewer, right-click and pick Global Options > Buffer LUT > Type of LUT you want to apply. While handling nonlinear files out of many of today's digital cinema cameras, a current workflow would convert it all to linear at the head of the node tree, then build your composite, and then apply an Image LUT or Buffer LUT matching whatever color space you intend it to sit in for either grading on the Color page or for final output. In more involved production pipelines, though, you might have to apply several LUTs one after another.

### Types of Viewer LUTs

Beyond the industry standard 1D and 3D LUTs, further kinds of LUTs are accommodated, among them scriptbased Fuse node LUTs, OCIO files, and macros put together from standard nodes. As a rule, LUT processing runs on the graphics card's GPU in real time, though how macrobased LUTs perform hinges on the nodes inside them.

### Fusion View LUT

Serving as the default, the Fusion View LUT is a heavily used LUT type. It supplies an RGBA curve usable for assigning IN/OUT value pairs. This control matches the one offered by the Color Curve node. Because the View LUT exists to deliver a fixed correction for the monitor or the file's color space, however, its splines can't be animated.

### Log-Lin View LUT

The Log-Lin LUT turns logarithmic data into linear, and the reverse as well. That can come in especially handy alongside supplied LUT files that anticipate logarithmic data. It resembles the Cineon Log node.

### Gamut View LUT

The Gamut LUT turns a source color space into an output color space, offering choices for handling gamma settings, alpha channels, and premultiplication. The Gamut LUT is a heavily used LUT type for correcting the viewer while you work with Linear Gamma in the Node editor.

### Macro LUTs

Any macro node may serve as a viewer LUT too, merely by storing the macro's .setting file into the right Fusion directory. Within DaVinci Resolve, the storage spots for LUTs are these. Under macOS: Macintosh HD/Users/username/Library/Application Support/Blackmagic Design/ Fusion/LUTs/ Under a Windows host: C:\Program Files\Blackmagic Design\Fusion\LUTs Under Linux: home/username/.local/share/DaVinciResolve/Fusion/LUTs Over in Fusion Studio, the storage spots instead become these. Under macOS: Macintosh HD/Users/username/Library/Application Support/Blackmagic Design/ Fusion/LUTs/ Under a Windows host: C:\Users\username\AppData\Roaming\Blackmagic Design\Fusion\LUTs Under Linux: home/username/.fusion/BlackmagicDesign/Fusion/LUTs So that this works, the macro is required to carry one image input plus one image output. Whatever controls the macro surfaces will be on hand once the Edit option has been chosen for the LUT. For deeper detail on building macros, turn to Chapter 68, “Node Groups, Macros, and Fusion Templates,” over in the DaVinci Resolve Reference Manual, or else Chapter 6 within the Fusion Reference Manual.

### LUT Presets

Every LUT on hand to DaVinci Resolve is reachable from the Fusion page as well, which takes in custom LUTs you've added along with preset LUTs that ship with DaVinci Resolve, like the highly handy VFX IO category carrying a broad assortment of miscellaneous to Linear and Linear to miscellaneous transforms. The whole set of these LUTs turns up by category within the viewer LUT menu.

### Fuse LUTs

Fuses are scriptable plugins that come bundled with the application or that you build inside Fusion. A fuse called CT_ViewLUTPlugin is applicable as a LUT on a viewer. You can additionally script fuses that draw on graphics hardware shaders baked into the LUT for real-time processing. Since fuse LUTs call for shader-capable graphics hardware, they can't run in software. To learn more about Fuses, consult the Fusion Scripting Guide found on the Blackmagic Design website.

### Using Viewer LUTs

Viewer LUTs can be switched on, edited, and switched off via the viewer LUT button and menu, plus through the viewer contextual menu. That menu lists every LUT on hand to Fusion, custom LUTs you've added yourself included.

The viewer LUT button alongside its menu, shown on the Fusion page inside DaVinci Resolve

To turn the current viewer LUT on and off:

- In the viewer toolbar, click the LUT button so the viewer LUT flips on and off.
- The LUT menu can additionally be reached as a submenu inside the viewer's contextual menu.

To choose another viewer LUT:

- Open the menu sitting to the right of the viewer LUT button and pick an option out of the viewer LUT menu.

To apply a Buffer LUT: 1 Somewhere inside the viewer, right-click and pick Global Options > Buffer LUT > Enable. 2 For a particular Buffer LUT, right-click yet again and select a LUT out of the Global Options > Buffer LUT submenu. Buffer LUTs frequently come in handy for applying monitor corrections, which tend not to shift between projects. To remove a Buffer LUT:

- Somewhere inside a viewer, right-click and pick Global Options > Buffer LUT > Enable so it gets unchecked.

### Editing Viewer LUTs

The viewers form the main spot where composites get judged, so it matters greatly that they give a faithful picture of how the content will appear once it's shown to an audience. The LUT Editor lets you tailor your viewer's output to fit the gamma and color traits of the playback device you'll eventually use, or to test how the present image looks within a wholly different color space, or how well it bears up across a span of differing color spaces. To bring up the Editor for any editable viewer LUT option: 1 In the viewer toolbar, click the LUT button so it's switched on. 2 Do one of the following:

- Choose Edit from the top of the viewer LUT menu.
- Inside the viewer, right-click and then pick LUT > Edit off the contextual menu.

### Editing the Fusion View Lookup Table

Much like the Color Curves node, the Fusion View LUT Editor relies on spline-based color correction. On top of letting you alter the separate color channels, the LUT carries Gain and Gamma sliders. The Gain slider helps with momentarily brightening or darkening the viewed image so shadow or highlight detail is easier to inspect. The Color Gamma and Alpha Gamma sliders serve to mirror the gamma values of the output device you'll eventually use. Video monitors, for instance, usually carry a gamma of 1.7, whereas computer monitors may span anywhere from 1.6 to 2.2. Alpha Gamma kicks in solely while you view an image's alpha channel, or while you view masks.

Shown is the LUT Editor belonging to the default Fusion View LUT. Editing the Gamut View LUT: through the Gamut View LUT Editor you pick a Source and Output color space that steers the viewer transform. The Remove and Add Gamma checkboxes let you decide to run the gamut conversion using linear or nonlinear gamma, or they let you merely strip or apply the relevant gamma values while leaving the color space alone. Ticking the Pre-Divide/Post-Multiply checkbox makes the image's pixel values get divided by the alpha values ahead of this conversion, then re-multiplied by the alpha value once it's done. That helps stave off the making of illegally additive images, especially along the edges of a blue/green key or while you handle 3D rendered objects.

### The Gamut View LUT Editor

### The Log-Lin LUT Editor

### Editing the Log-Lin View LUT

The Log-Lin LUT lets you run a Log to Lin or Lin to Log operation by way of the Mode pop-up menu. From the Log Type drop-down you pick which kind of log-encoding to process, and you decide whether the R, G, and B channels get locked together. A level adjustment lets you reset the digital span of output values, whereas the sliders for Soft Clip (Knee), Film Stock Gamma, and Conversion Gamma give you further command over the color transform. Finally, a Conversion Table field plus Browse button let you fold an extra LUT into this operation.

### LUT Processing Order

Within involved workflows, facilities might apply several LUTs back to back ahead of the image being seen. Their order counts, since every LUT yields different outputs. As an instance, for a Cineon file sitting in Log color space you may often apply three LUTs. First comes a Log to Lin conversion, then a Fusion View LUT that lays down a color calibration, and a third that corrects it for showing on an sRGB monitor, or you swap that last one for a 3D DCP LUT when you're viewing on a projector. Once you pick a node to be shown, the image it yields gets processed before it appears in the viewers. That processing order differs a little across 2D images and 3D scenes. With 2D images the image LUT goes on first, and the outcome gets composited over the checker underlay. 3D scenes are instead rendered using OpenGL.

### Image Output

### Image LUTs

### Macro LUTs Fusion View LUT

### Post Processing

### Checker underlay Dithering

Buffer LUT (single)

### Viewer Output

Order of processing. How processing is ordered across 2D images alongside 3D scenes. Whether 2D or 3D, the outcome may be drawn into an offscreen buffer where a Buffer LUT can apply, accompanied by dithering, a full view checker underlay, and any stereo processing. That final outcome is then drawn into the viewer, and any onscreen controls get drawn on top of it.

### Applying Multiple LUTs

By way of the viewer contextual menu you can stack several image LUTs into a processing chain. So as to add a further LUT, proceed thus: 1 Somewhere inside the viewer, right-click. 2 Off the viewer's contextual menu, pick LUT > Add New. 3 From within the Add New submenu, pick a LUT to bring in. So as to drop a LUT besides the first LUT, proceed thus: 1 Somewhere inside the viewer, right-click. 2 Off the viewer's contextual menu, pick LUT > Delete. 3 From within the Delete submenu, pick a LUT to drop. An entire stacked LUT configuration can be stored to and loaded out of a .viewlut file, as the text below explains.

### Saving Custom LUTs

Fusion offers an assortment of ways to build and use various viewer LUTs. You can store LUTs as you store viewer settings, you can import LUTs that were exported out of Fusion or other applications, and you can open any one of the many supported LUT file types. On top of that, you can draw on the standard nodes inside Fusion to build macros, which can then be stored and used as a LUT.

### LUT Settings

The simplest route to store a LUT you've built with the Fusion View LUT Editor is to reach for the LUT > Save menu sitting in the viewer contextual menu. Those settings get stored as an ASCII file carrying the extension .viewlut inside the LUTs folder. Whatever files bearing this extension turn up in that folder will appear within the Image LUT menus for easy loading. You can additionally load settings absent from the menu by picking LUT > Load out of the viewer's contextual menu.

### Using Viewer Settings

After you've altered a LUT, picking Settings > Save New out of the viewer's contextual menu will store the whole of the viewer's settings, every LUT curve and gain/gamma value included. You can store these under various names, and each settings file can be reloaded whenever you like by picking Settings > filename out of the viewer's contextual menu. Picking Save Default off that same menu will turn these settings into the standard for every new comp.

### Using LUT Curves

The Viewer LUT Edit dialog serves to import and export LUT curves. You can export the LUT curves in either ASCII or Saved format. The ASCII (.alut) file format comes in handy for passing LUT curves to other software, whereas the Saved (.lut) file format gets the nod for Fusion, since it stays more compact, accurate, and amenable to later tweaking. So as to export a LUT, work through these: 1 Click the viewer LUT button so it switches on. 2 Click the viewer LUT menu, then pick Edit. 3 Right-click on the LUT Curve Editor, then pick Export LUT. 4 Pick a LUT format down at the bottom of the file browser window. 5 Type in a name for the LUT, then click Save. Via the Import LUT option, LUT files get loaded back into the Curve Editor; or else, after the file has landed inside Fusion's LUTs folder, it surfaces within the LUT drop-down menu list. TIP: That makes one route for moving LUTs between viewers, or back and forth with the Color Curves node, or with whatever other LUT Editor sits inside Fusion.

### LUT Files

Whatever supported LUT files sit in the LUTs folder can be used by picking them either off the LUT dropdown menu or the viewer's contextual menu. This covers 1D and 3D LUTs like Fusion's .lut, .alut and .alut3 formats, plus .cube, .shlut, .look, .3dl, and .itx formats. That makes a handy route to reach standard format LUT files across different projects.

### Settings and Macros

Because LUTs amount to a form of color correction, you can on top of that press any node, macro, or cluster of nodes into service as a viewer LUT. So as to press a node, group, or macro into use as a viewer LUT, work through these: 1 Pick the node, group, or macro. 2 Right-click over the chosen node, then pick Settings > Save As off the menu. 3 Inside the file browser, navigate over to the LUTs folder named under Preferences > Global > Path Map > LUTS. 4 Hit Save so the .settings file gets stored. That lets nearly any blend of nodes serve as a viewer LUT. While this is the most flexible route, it's also potentially the slowest. Those LUT nodes have to render solely on the CPU, whereas other approaches are GPU-accelerated. Setting a Default LUT The default LUT that goes on once a new composition gets made can be assigned within the Viewer panel of the Fusion Settings window. Ticking the Enable Display LUT checkbox lets you pick a LUT out of the Display LUT plugins list.

The default LUT settings sitting within the View panel of the Fusion Settings window

### Viewer Preferences and Settings

Each viewer's default settings can be changed via the Viewer panel within the Preferences. The position plus size of every floating viewer can additionally be stored via the Layout menu within the Preferences.

### Viewer Settings

Frequently it's preferable to flip between wholly different viewer configurations as you work. For instance, while keying, the image might sit in the main viewer with the alpha channel in a subview. Toward a project's close, viewer settings may take in the histogram, vectorscope, and waveform, plus the image in a view set to Quad view. Fusion gives you a fast way to load and store viewer settings, trimming the work involved in swapping between one layout and the next. So as to store a viewer setting, proceed thus: 1 Over the viewer you'd like to keep, right-click. 2 From the contextual menu, pick Setting > Save New. 3 Type a name for the settings, then click Save. So as to load a viewer setting, proceed thus: 1 Over the viewer you'd like to load a setting into, right-click. 2 From the contextual menu, pick Settings > filename. Loading and Saving Defaults for a Viewer: the viewer is able to keep fresh defaults and be reverted to its defaults using the Load Defaults plus the Save Defaults options that sit in the Settings portion of the View contextual menu.

### The Viewer Options Menu

The viewer's Options menu holds several ways you can tailor the viewer's look and behavior. Many of these options live in the viewer contextual menu too. Show Controls Whenever onscreen controls aren't needed or are obstructing your view of the image, you can briefly hide them via the Show Controls option. This option toggles using Command-K. Checker Underlay The Checker Underlay puts a checkerboard underneath transparent pixels to make spotting transparent areas easier. This is the default option for 2D viewers. Turning this option off swaps the checkerboard for black. Show Pixel Grid Switching this option on will display a faint black grid tracing the precise pixel boundaries within the image once the image gets scaled past a certain threshold. The default is Off.

Smooth Resize The Smooth Resize option applies a smoother bilinear interpolated resizing method as you zoom into an image inside the viewer. With Smooth Resize switched off, scaling falls back on the nearest neighbor method and reveals obvious aliasing artifacts but proves more helpful for seeing the actual pixels of the viewed image once you zoom all the way down to a pixel level, since no interpolation occurs. This option is switched on by default and toggles by clicking the SmR button within the viewer toolbar. Show Square Pixels Hinging on the frame format preferences and the kind of footage loaded, many images may carry pixels that are rectangular rather than square. The NTSC and PAL video standards alike, plus certain anamorphic film formats, rely on rectangular pixels. A computer monitor relies on perfectly square pixels. To make up for this, aspect correction runs automatically while you view non-square pixels. That keeps non-square pixel images from looking squashed or stretched within the viewer. You can switch on the Show Square Pixels option to trump the aspect correction. Show Square Pixels likewise toggles on and off via the 1:1 button within the viewer toolbar. Gain/Gamma Surfaces or conceals a plain pair of Gain and Gamma sliders that let you tune the viewed image. Particularly handy for “gamma slamming” a composite so you can gauge how well it holds together under a spread of differing gamma values. The default leaves things unchanged. 360° View Configures the Fusion page viewer so spherical imagery shows correctly across a spread of formats you pick out of this submenu. Disable flips 360 viewing on or off, whereas the Auto, LatLong, Vert Cross, Horiz Cross, Vert Strip, and Horiz Strip choices let you render the various formats of 360º video properly.

### Locking the Viewer (Command-L)

You can lock a viewer so it won't update. The node loaded into that viewer keeps processing and the fresh image gets queued for display within the viewer, but until you unlock it, the viewer holds still. By default, the viewer sits unlocked.
