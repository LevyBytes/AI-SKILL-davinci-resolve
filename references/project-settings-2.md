# Project Settings (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

The “Motion estimation mode” drop-down, found in the Master Settings panel of the Project Settings, exposes extra “Enhanced” Optical Flow choices. Carried over unchanged from earlier DaVinci Resolve releases, the “Standard Faster” and “Standard Better” entries place lighter demand on the processor while still delivering quality good enough for the majority of jobs. By contrast, the “Enhanced Faster” and “Enhanced Better” entries tend to outperform the standard pair almost any time those exhibit artifacts, though they ask more of the system and therefore run slower on typical hardware. For top-tier slow-motion work driven by the DaVinci Neural Engine, reach for “Speed Warp Faster” and “Speed Warp Better.” How well this performs depends on what the clip contains, but under favorable conditions it produces cleaner, higher-fidelity output with fewer artifacts than even the Enhanced Better choice.

- Motion range: For timelines set to Optical Flow retiming that include clips of mixed frame rates, or whenever Optical Flow drives speed-change effects, this drop-down sets the default magnitude — small, medium or large motion — applied across every speed and motion

related computation, letting you tune the outcome to suit the kind of movement present in your source footage. You may also adjust this per clip from the Edit page Inspector.

Newly upgraded Motion estimation mode controls within the Project Settings’ Master Settings panel

### Blackmagic Cloud

Settings that govern how a project connects to the Blackmagic Cloud service live inside the Blackmagic Cloud panel.

### Project Media Location

Sets the destination where media tied to Blackmagic Cloud projects is kept.

- Folder Location: Displays the path on your machine that holds the Blackmagic Cloud media. To point it elsewhere, click the Change location button and pick a fresh destination through the file browser.

### Multi User Collaboration

Determines whether more than one person is permitted to edit this particular project.

- Allow multiple users to simultaneously access and work on this project: Tick this option to switch on the collaboration tools for the cloud project. Leave it clear when you alone are handling a cloud project.

### Blackmagic Cloud Storage Syncing

Use these controls to govern how Blackmagic Cloud Storage handles synchronization.

- For Media Files: Decide here which media gets pushed up and synchronized to your Blackmagic Cloud Storage account so collaborators can reach it. Don’t Sync media: Sends nothing at all to Blackmagic Cloud Storage. Sync proxies only: Pushes just the proxy media up to Blackmagic Cloud Storage. Sync proxies and originals: Sends the proxies together with the source media to Blackmagic Cloud Storage, which may consume a very large quantity of storage based on how much original media there is and how big it runs. Generate proxies automatically: Enable this option so DaVinci Resolve builds proxy media for your master clips on its own.
- Proxies are created as: Pick from these entries which codec the generated proxy files adopt.
- Display synced media in: Defines the timeframe used when showing synced media.

### Remote Cameras

Establishes access rights for people using the Blackmagic Cameras and the Camera app.

- Allow remote cameras to view this project and load media straight into the media pool: Lets project members on the Blackmagic Camera and Camera app push camera footage to the Blackmagic Storage account, which then lands straight in the project’s Media Pool.

### Blackmagic Cloud

Hit the Blackmagic Cloud Website button to reach the Blackmagic Cloud web interface, the place where you arrange, reach, and purchase the assorted Blackmagic Cloud services.

### Image Scaling

The conditions and methods by which clips get resized for assorted purposes are governed inside the Image Scaling panel.

### Image Scaling

The way clips are resized under different conditions is shaped by these settings.

- Resize Filter: This opening cluster of options picks which filtering approach interpolates pixels as clips are resized: Smoother: Can deliver better results for projects whose clips have to shrink down to an SD resolution frame size. Bicubic: Although Sharper and Smoother edge it out slightly in quality, Bicubic remains a remarkably capable resizing filter and demands less of the processor than either alternative. Bilinear: A reduced-quality option that taxes the processor less. Handy for checking your work on a slower machine ahead of rendering, after which you can move up to a finer-quality choice. Sharper: Generally yields the finest output for projects whose clips need enlarging to a bigger frame or shrinking to HD resolutions. Custom: Hands you direct command over the precise algorithm governing every resize. For the custom Resize Filter, your menu lists these algorithms: Bessel, Box, Catmul-Rom, Cubic, and Gaussian, plus Lanczos, Mitchell, Nearest Neighbor, Quadratic, and Sinc. Realistically, telling these approaches apart can be fairly subjective. Even so, when you must replicate a particular resize technique from a different program, this is where you do it. For routine work, the standard resizing filters within DaVinci Resolve will serve fine.
- Override input scaling: Ticking this box lets you select an Input Sizing preset for the project.
- Override output scaling: Ticking this box lets you select an Output Sizing preset for the project.
- Deinterlace quality: (only available in Studio version) A fourth cluster lets you balance quality against processing time when deinterlacing Media Pool clips via the Enable Deinterlacing checkbox of the Clip Attributes window. Three choices exist: Normal: A high-quality deinterlacing approach fit for the bulk of clips. With many clips, Normal can’t be told apart from High. During playback in Resolve, Normal always runs automatically. High: A heavier method on the processor that, with certain footage, may produce nicer results at the cost of longer render times.

DaVinci Neural Engine: Drawing on the sophisticated machine-learning algorithms of the DaVinci Neural Engine, this choice studies the motion between an interlaced frame’s fields and rebuilds them as one combined frame. Though extremely demanding to compute, it should ideally hand you an even more visually pleasing outcome than the “high” option.

### Input Scaling

Holds a single control, Mismatched resolution files, which governs the treatment of clips whose resolution differs from the project’s current resolution. Four choices exist:

- Center crop with no resizing: Clips at a different resolution receive no scaling whatsoever. Anything smaller than the present frame size gets framed by blanking, while anything larger than that frame is cropped.
- Scale full frame with crop: Clips at a different resolution are scaled until the clip’s narrowest side aligns with the frame. The leftover pixels get cropped.
- Scale entire image to fit: The default setting. Clips at a different resolution are scaled until the clip’s widest side aligns with the frame. Blanking fills the narrower side (either letterboxing or pillarboxing).
- Stretch frame to all corners: Handy for projects built on anamorphic media. Clips of varying resolution get compressed or pulled to meet the frame size across every dimension. Through this, anamorphic footage can be expanded to fill full raster, while full raster footage can be compressed into an anamorphic frame. A nice side effect is how readily it lets you blend anamorphic and non-anamorphic clips within one project.

### Output Scaling

Should you wish, these settings let you pick a separate resolution to send out through your video output hardware — whether for monitoring, tape output, or rendering. Specifically, when you set the resolution inside the Render Settings list on the Deliver page to anything besides the Timeline Resolution, these settings carry out that conversion (for instance, when you render a downconversion of the present timeline). It comes in handy when your project sits at a high 4K resolution yet you wish to monitor on an HD display and ship HD media out for sign-off.

- Match timeline settings: On by default, which keeps these settings aligned with the Timeline Resolution, Image Scaling, and Input Image Scaling settings covered above. Clear this checkbox to assign separate settings for monitoring, tape output, or rendering through the remaining controls in this cluster.
- Output resolution: Lets you pick an alternate resolution.
- For: Lets you state a different custom alternate resolution.
- Pixel aspect ratio: Lets you state an alternate pixel aspect ratio matching the alternate

timeline format.

- Mismatched resolution files: Lets you pick an alternate approach to handling mismatched resolution

files, given the alternate resolution you settled on. These options behave exactly like those in the “Input Image Scaling” cluster.

- Super Scale: Engages an extremely processor-heavy, high-quality upscaling algorithm that genuinely fabricates new pixels for the enlarged image. Its allowed values are: None, 2-3-4x, 2-3-4x Enhanced, and Auto.

Additional Super Scale details appear in Chapter 11, “Image Sizing and Resolution Independence.”

### Color Management

The assorted controls in the Color Management panel let you set up DaVinci Color Management (RCM) or ACES once either is switched on, and they additionally let you apply pre- or post-processing to the DaVinci Resolve image processing pipeline through LUTs and Broadcast Safe settings, so a broad spread of color workflows can be supported.

### Color Space and Transforms

Selecting DaVinci YRGB Color Managed or ACES from the Color Science menu up top switches on the remaining drop-down menus throughout this section. To dig deeper into DaVinci Resolve Color Management together with ACES, turn to Chapter 9, “Data Levels, Color Management, and ACES.” Anyone fresh to color or color management is urged to study that chapter. Once you opt for Resolve Color Management (RCM), ACEScc, or ACEScct, the controls in this panel grant broad authority over how color gets transformed: it begins with picking the default color treatment for your project’s source media (through the Input Color Space), moves on to dictating how you want the DaVinci Resolve grading controls to respond (through the Timeline Color Space), and finishes by defining how the final color appears on your monitor and output device (through the Output Color Space).

- Color science: Four selections decide whether color management runs manually or automatically. DaVinci YRGB color science: The founding color science of DaVinci Resolve, where every color transform from one space to another is handled by hand, using LUTs or manual tweaks. DaVinci YRGB Color Managed: Switches on the Resolve color-managed workflow (RCM) for grading. ACEScc or ACEScct: A pair of standardized color-management approaches offered to shops running ACES workflows. Among the options, ACEScct suits most colorists best, since it raises shadows in a way that proves creatively handy.

Further coverage of Color Management plus ACES sits in Chapter 9, “Data Levels, Color Management, and ACES.”

- ACES version: This drop-down surfaces only after you select one of the DaVinci ACES choices in the Color science drop-down menu. It lets you move among the various releases of the ACES specification, so you can pick whichever older ACES version fits when reopening a legacy project.
- Use Separate Color Space and Gamma: While this checkbox stays off (the default), the Color Management panel of the Project Settings shows a single drop-down apiece for the Input, Timeline, and Output Color Space settings, and each one converts gamut and gamma together according to whatever option you pick. Switch the checkbox on and the Color Management panel shifts so the Input, Timeline, and Output Color Space settings each present two pop-ups. The leading drop-down sets the gamut on its own, whereas the second drop‑down sets the gamma on its own.

A dedicated chapter walks through the basic and advanced global controls that Resolve Color Management (RCM) offers, supplying fuller detail. You’ll find it at Chapter 9, “Data Levels, Color Management, and ACES.”

### Dolby Vision™

A GPU-accelerated software build of the Dolby Vision CMU (Content Mapping Unit) ships within DaVinci Resolve, supporting Dolby Vision grading and finishing workflows directly inside either the free edition of DaVinci Resolve or DaVinci Resolve Studio. You switch it on and configure it from the Color Management panel of the Project Settings through the Enable Dolby Vision checkbox.

s Dolby Vision controls shown within the Project Settings Color Management panel; the available count is five:

- Enable Dolby Vision: Switches Dolby Vision on and off. While active, this checkbox surfaces the Dolby Vision palette over in the Color page.
- Dolby Vision version drop-down: Picks which release of the Dolby Vision algorithms is in use. As of this writing, the choices cover 2.9 and 4.0.
- Analysis tuning: Pick among assorted choices governing how Dolby Vision examines and manages highlight retention.
- Master Display drop-down: Picks the nit level and gamut belonging to the master HDR display you grade against.
- Use External CMU: This checkbox decides whether the built-in software CMU or a connected hardware CMU on your DaVinci Resolve workstation does the work.

NOTE: Every DaVinci Resolve user has access to the Dolby Vision controls for monitoring and for auto-generating Dolby Vision metadata, which lets you build additional HDR and SDR deliverables out of the HDR grade you produced. That said, to layer manual trims atop the auto-generated analysis, licensing is required: write to dolbyvisionmastering@dolby.com to learn how one is obtained.

### HDR10+

The fresh HDR10+ HDR format from Samsung is supported by DaVinci Resolve. Be aware that, since this is a new standard, the support remains a work in progress. Once switched on, an HDR10+ palette presents trimming parameters with which you can trim an automatic downconversion of HDR to SDR, producing metadata that dictates how HDR-strength highlights render across the range of compatible televisions and displays. You enable and configure this from the Color Management panel of the Project Settings using the Enable HDR10+ checkbox. Switching HDR10+ on surfaces the Dolby Vision palette within the Color page.

HDR10+ settings in the Color Management panel of the Project Settings

### HDR Vivid

Put out by the China UHD Video Industry Alliance (CUVA), HDR Vivid is an HDR video technology standard. Working in this format guarantees broad compatibility across HDR televisions, phones, computers, and additional devices throughout China.

HDR Vivid settings in the Color Management panel of the Project Settings

### Lookup Tables

This cluster of controls lets you attach LUTs to the Resolve image processing pipeline so that every timeline across the whole project is affected together. Such LUTs serve numerous purposes — trimming Timeline grades, performing Log to Linear conversions, mimicking film output, and clamping the signal to satisfy Broadcast Safe requirements among them. Various options let you slot image processing into separate pipeline stages, illustrated in this diagram: Monitored Image

### DISPLAY LUT

### Raw Image Data

### Camera Raw Decoding

### INPUT LUT

### Color Page Image Processing

### OUTPUT LUT

### Deliver Page Output Media

Bear in mind that because 1D and 3D LUTs can both be applied at once, the 1D LUTs at any given step always run ahead of the 3D LUTs.

- Input Lookup Table: A pair of drop-down menus lets you attach 1D and/or 3D LUTs that act on the current Timeline ahead of every other image processing operation in DaVinci Resolve.
- Output Lookup Table: A pair of drop-down menus lets you attach 1D and/or 3D LUTs that act on the current Timeline after the Color page operations finish, yet ahead of the briefly applied Display LUT.
- Video Monitor Lookup Table: A pair of drop-down menus lets you attach 1D and/or 3D LUTs that act on the current Timeline after every other image processing operation in DaVinci Resolve. That said, Display LUTs apply only briefly for monitoring purposes; they never touch rendered media nor the signal sent to tape via the Deliver page controls. Display LUTs prove especially handy for applying a film print emulation LUT inside a Log workflow, or for applying a monitor calibration LUT when you output to one display and lack dedicated outboard calibration hardware.

Here’s an example. When grading toward film output under a Log workflow, it’s typical to reach for the Display LUT drop-down menu and apply a film emulation LUT that mimics how the image emerges from the film recorder — factoring in the film lab and print stock involved — so that the image you’re grading sits as near as it can to how the final release print will appear on the cinema screen.

- Color Viewer Lookup Table: A pair of drop-down menus lets you attach 1D and/or 3D LUTs that act on the picture shown in the Viewer on your computer display, apart from the Display LUT used for output to your broadcast display. By default this tracks the Video Monitor LUT setting, though you may also use this option to apply a particular calibration transform for your computer monitor. As an alternative, you might use it to strip color from the GUI Viewer so you can judge image contrast specifically, or to avoid quarreling with your client over which display reads correctly.
- Scopes Lookup Table: Normally, the internal software video scopes in DaVinci Resolve deliver an unbiased read of the genuine video data levels inside the Resolve image processing pipeline. You can, however, direct the software scopes to adopt the Video Monitor LUT selection, or any other LUT present on your system, so this read reflects the monitored output.
- 3D Lookup Table Interpolation: Picks the processing quality used for both LUT and DCTL operations across DaVinci Resolve. 3D Lookup tables (LUTs) are three-dimensional grids of red, green, and blue values, each input color mapped to an output color value, thus offering a way to perform color transformations from pre-calculated data. Powerful though they are, 3D LUTs hold finite detail; one might, say, carry a 17x17x17 LUT defining 4913 individual color transforms. Applied to a floating point image holding more data than the LUT defines transforms for, the color values that land between the 17x17x17 color transforms named by the LUT must be interpolated. Two methods are available, each weighing processing efficiency against greater quality:

Trilinear: (Default) Trilinear stays backward compatible with grades relying on LUTs from earlier DaVinci Resolve versions and reproduces how those LUTs appear within other applications. Tetrahedral: Tetrahedral leans a touch harder on the processor, but it yields finer image quality in LUT and DCTL processing with less color-banding. Tetrahedral suits projects that have no need for backward compatibility with earlier DaVinci Resolve versions or with LUTs built in other applications.

- Update Lists button: Reloads the LUT drop-down menus whenever you’ve added new LUTs to your system after DaVinci Resolve was already running.
- Open LUT Folder button: Choosing this opens the master folder within your file system, as covered in the list of DaVinci Resolve LUT paths shown above.

Adding Lookup Tables to Your DaVinci Resolve Installation The drop-down menus inside the Color Management panel carry a set of factory preset LUTs shipped alongside DaVinci Resolve, plus whatever LUTs DaVinci Resolve has produced or that you’ve dropped into the correct directory for your operating system.

- On macOS: Library/Application Support/Blackmagic Design/DaVinci Resolve/LUT/
- On Windows: C:\ProgramData\Blackmagic Design\DaVinci Resolve\Support\LUT
- On Linux: /opt/resolve/LUT Should you have grabbed the non-studio edition of DaVinci Resolve through the Apple App Store, the LUTs reside in a separate spot so that DaVinci Resolve stays completely self-contained. Here, clicking the “Open LUT Folder” button within the Lookup Tables panel of the Project Settings opens a Finder window right where those LUTs live. From that window, you can duplicate LUTs you’d like Resolve to reach, or remove LUTs you no longer want. Drop a LUT into one of these directories once DaVinci Resolve is already open and you can click the Update Lists button to reload the drop-down menu contents. Both 1D and 3D LUTs are used by DaVinci Resolve. The 3D LUTs that DaVinci Resolve generates come in the .cube format, set up as 33x33x33 cubes with 32-bit floating point processing. DaVinci Resolve is likewise able to read and apply LUTs in the Shaperlut format.

### Broadcast Safe

You can switch on Broadcast Safe settings during grading to hold the video signal’s luma and chroma alike within three permitted bands of overshoot and undershoot tolerance. Broadcast safe IRE (mV) levels: From this drop-down menu, pick one among three intensities for clamping the signal. Pick whichever range fits your QC requirements. Make Broadcast Safe: A checkbox toggling broadcast safe limiting on or off. NOTE: The clipping that Broadcast Safe applies carries no inherently soft roll‑off of its own. To get the best outcome, pair Broadcast Safe with the Soft Clip controls over in the Color page.

### General Options

A range of general preferences shaping the interface and behavior of DaVinci Resolve is gathered in this panel.

### Conform Options

How clips are conformed so imported project files line up with source media on disk — by pulling timecode, reel names, file names, file paths, and the like — is decided by the settings in this cluster. Conforming and relinking get fuller treatment over in Chapter 56, “Conforming and Relinking Clips.”
