# Managing Color For Visual Effects

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Managing Color for Visual Effects

The subjects of this chapter are LUTs, color space conversions, and why it pays to composite with linear gamma while you preview the image in the viewer using whatever gamma you prefer.

### Color Management

Put simply, the aim of color management is to guarantee that the image on your computer screen matches what your audience sees on a television, cinema screen, or mobile device. As basic as that aim sounds, it raises problems that you, the compositor, have to handle. Those problems start with the fact that our eyes perceive luminance one way while a computer display renders luminance another way. To bridge that gap, every capture device records images through a nonlinear tonal curve, or gamma curve. Specifically, Rec. 709 HD gamma curves are built so that, once shown on HD displays, the images already carry compensation for the display. As a result, HD images look normal to us on HD displays. Digital cinema cameras have pushed the gamma curve idea even further. They wield gamma curves as a means of squeezing the most out of an image's bit depth and holding a broader dynamic range. The gamma curve of digital cinema cameras (frequently lumped together under the term log gamma) devotes more attention to the darker midtones, where the human eye is keenest. That lets them keep images with brighter highlights and richer shadow detail. On the left, a Rec. 709 HD gamma curve; on the right, a nonlinear curve, also called log gamma The catch is that these images don't look normal on any monitor. Clips shot with a log gamma curve usually take on a low-contrast, low-saturation look when seen on an sRGB computer display or a Rec. 709 HD video monitor. This is an easy problem to remedy with a LookUp Table, or LUT. A LUT is a kind of gamma and color correction applied to the viewer so that how the image displays on your screen is normalized.

On the left, a clip shown through a nonlinear, log gamma curve; on the right, the same clip corrected in the viewer with a LUT

### All Compositing Is Math

A LUT applied to the viewer only fixes the problem within the viewer. Here's where the bigger problem comes in. The image data itself is still carrying a log gamma curve. Fusion, like every other image-processing application, runs on the assumption that the image data has linear gamma. The image-processing filters you put on images rely on ordinary math functions, like 1 + 1 = 2. Common operations, the ones that add pixels such as Brightness, or divide pixels (otherwise known as “unpremultiply”), or composite modes built on multiplication such as “screen,” plus a host of other compositing tasks, all assume 1 + 1 always lands at 2. To put it another way, if you run an operation that doubles brightness, then each pixel ought to come out twice as bright. But when you start from a nonlinear gamma curve, pixels aren't adjusted linearly, so a given pixel may finish at 1.2 x as bright, another at 1.7 x as bright, and yet another at 2.4 x as bright. Now the math reads 1 + 1 = 3. The farther your images sit from linear gamma, the more obvious the math error grows. There's less error in a Rec. 709 HD clip than in a log gamma clip out of a digital cinema camera. Still, an error is an error, and every additional compositing operation you run on the image compounds it further. A more down-to-earth example shows up when you apply filtering effects, such as a blur, to an image at any gamma setting. The image probably looks fine. Yet if you first convert the image to a linear gamma and then apply the blur, the images (above all those with extremely bright regions) get processed with greater accuracy, and you should spot a different, superior outcome. The remedy for all this is to manage your color ahead of compositing.

### Introducing Color Management in Fusion

By default, images brought into Fusion aren't color managed. The image goes straight from the file to the viewer with no interpretation or conversion. Fusion does, however, ship with nodes that convert each image's output to linear gamma at the start of your composite. Those same nodes can convert from linear back to whatever output gamma you want at the end of your composite, right before the Saver or MediaOut node.

A log clip converted to linear and then converted for output To set up a linear gamma workflow in Fusion by hand: 1 Place a Gamut or CineonLog node after every MediaIn or Loader node to convert them to linear. 2 Put a GAMUT View LUT on the viewers to correct how a linear image displays as sRGB or Rec. 709. 3 Ahead of a Saver or MediaOut node, drop in a Gamut or CineonLog node to convert from linear to your intended output format.

### Converting to Linear Gamma

No matter if an image comes in by way of the Edit page in DaVinci Resolve or through a Loader in Fusion Studio, its color and gamma get read straight into Fusion with nothing changed. For a few simple operations on sRGB or Rec 709 clips, that may be acceptable, though it isn't always the best way to work, especially with log-encoded media. The best approach for log-encoded media is converting images to linear gamma, because most image-processing operations in Fusion expect linear gamma and turn out better results. TIP: 3D rendered CGI images are frequently produced as EXR files with linear gamma, and converting them isn't required. Even so, you should inspect your particular files to confirm they're using linear gamma. Fusion bundles several kinds of nodes you can put to use taking each MediaIn or Loader node's image into linear gamma right at your composite's start, and then taking it from linear back to whatever output gamma you want at your composite's end. These include:

- CineonLog node: Sitting in the Film category of the Effects Library, the CineonLog node converts whichever of the formats listed in the Log Type menu you pick over to linear, and runs the process backward as well, restoring log gamma onto a clip. It's most often used for images from common digital cinema cameras such as BlackMagic Design, Arri, or Red. The CineonLog node goes directly after a MediaIn or Loader node. The Mode menu picks which direction the conversion runs, to or from linear.

Bring in a CineonLog tool to move log gamma curves into linear, and the reverse too.

- Gamut node: The Gamut node, located in the Color category of the Effects Library, lets you run linear conversions according to color space. It converts to linear or from linear and is frequently dropped in after a MediaIn or Loader node or just ahead of a MediaOut or Saver node. Which one you reach for, the Source Space controls or the Output Space controls, depends on where you place the node.

Bring in a Gamut tool to move gamma curves into linear according to color space. When taking media into linear gamma, point the Source Space menu at your source material's color space. As an example, should your media be full 1080 HD ProRes, then pick ITU-R BT.709 (scene) for gamma of 2.4. After that, switch on the Remove Gamma checkbox if it isn't already, so linear gamma is used.

Source Space is used to convert to linear gamma. When taking it from linear gamma for output, set the Gamut node ahead of whatever serves as your output node, namely a Saver in Fusion Studio or, on DaVinci Resolve's Fusion page, a MediaOut node. Confirm the Source Space menu reads No Change, and set the Output Space to your output color space. As an example, should your intended output be full 1080 HD, then pick sRGB, or else ITU-R BT.709 (scene), to land gamma of 2.4. After that, switch on the Add Gamma checkbox if it isn't already, so the Gamut node's output is shaped for your final output.

Output Space is used to convert from linear gamma.

- MediaIn and Loader nodes: MediaIn and Loader nodes carry Source Gamma Space controls in the Inspector that let you flag and strip the gamma curve without needing to add a second node. When your files carry gamma curve metadata, as RAW files do, the Auto setting on the Curve Type drop-down menu reads that metadata and uses it as it removes the gamma curve. For intermediate files or files lacking gamma curve metadata, you can pick either a log gamma curve by choosing Log on the Curve Type menu, or a specific color space through the Space option on the menu. Clicking the Remove Curve checkbox then takes the gamma curve away, converting the image to linear gamma.

MediaIn and Loader nodes include a Remove Curve checkbox in the Inspector.

- FileLUT node: The FileLUT node, located in the LUT category of the Effects Library, lets you run a conversion with any LUT you like, giving you the option of loading LUTs by hand in the ALUT3, ITX, 3DL, or CUBE format to carry out a gamma and gamut conversion. Although LUTs are very commonly parked at the end of a node tree for final rendering, more accurate gamma and color space conversions come from letting the Gamut and CineonLog nodes carry your MediaIn and Loader nodes into linear.

### Applying LUTs to a Viewer

Images that have been converted to linear gamma don't look right. They generally appear very dark, with extremely bright highlights and oversaturated colors. Fortunately, even though the image may seem wrong, the fact that Fusion can operate wholly on floating-point color data means you aren't actually clipping or shedding any image data. It merely looks completely off when you view the linear state of your image data directly.

On the left, a clip shown through a nonlinear, log gamma curve; on the right, that clip transformed into linear gamma Working would be impossible if you couldn't see the image the way it's meant to look within the final gamut and gamma you'll output. That's why each viewer carries a LUT menu that lets you switch on a “preview” color space and/or gamma conversion, while the node tree keeps processing correctly in linear gamma.

Put a Gamut View LUT in place to preview the image within the output color space you're aiming for.

To get a viewer preview of the images in sRGB or Rec. 709 color space: 1 Switch on the LUT button sitting above the viewer. 2 Out of the Viewer LUT drop-down menu, pick either a Gamut View LUT, or a LUT drawn from the VFX IO category that turns linear into Rec. 709 or sRGB. 3 If you go with the Gamut View LUT, then pick Edit at the bottom of the LUT menu to configure the LUT. 4 Within the LUT Editor, set the Output Space to whatever target color space you want. 5 Switch on the Add Gamma checkbox to apply the gamma curve tied to the chosen color space.

With the Add Gamma checkbox switched on, the Gamut View LUT Output Space here reads Rec. 709 for HD TIP: When your monitor is calibrated differently, you have to pick a LUT that lines up with your calibration. No matter whether you reach for the Gamut View LUT or a LUT matched to your particular monitor calibration, you're able to store the viewer setup as the default. Saving this Gamut LUT arrangement as the default viewer setup:

- Right-click in the viewer, and then choose Settings > Save Defaults.

From now on, for every comp, the viewer arrives preconfigured from the saved defaults. Should you want more detail on Viewer LUTs, turn to Chapter 69, “Using Viewers.” within the DaVinci Resolve Reference Manual, or to Chapter 7 of the Fusion Reference Manual.

### Using Resolve Color Management

If you're working on the Fusion page inside Davinci Resolve, you have the choice of turning on DaVinci Resolve's scene-referred color management rather than dropping in Gamut and CineonLog nodes. With DaVinci YRGB Color Managed (RCM) turned on, the color of MediaIn nodes on the Fusion page is treated differently. The RCM works out on its own the input color spaces of every file feeding all the MediaIn nodes on the Fusion page, which then get converted to linear gamma automatically. The MediaOut node afterward gets converted back into the Color Processing mode so it can be graded on the Color page or further edited in the Edit page Timeline. For all that color management seems involved, using RCM is genuinely straightforward. At bottom, all you do is (A) turn RCM on, and (B) pick whichever Color Processing mode and Output Color Space pairing you'd like. Switching Resolve Color Management on: 1 Within the Project Settings, open the Color Management panel. 2 Pick DaVinci YRGB Color Managed from the Color Science drop-down menu. 3 Tick the Automatic color management box for a simplified choice, or clear the box to set the Color Processing mode and Output color spaces by hand. 4 Set the options you want for the Color Processing mode and Output Color Space RCM settings.

With DaVinci YRGB Color Managed turned on, the Timeline color space applies to every MediaIn node on the Fusion page. To override the input color space for clips recorded differently in the Media Pool: 1 Turn on DaVinci YRGB Color Management as covered above. 2 Save and close the Settings dialog. 3 Within the Media Pool, highlight whichever clip or clips should receive a fresh Input Color space. 4 On one of those highlighted clips, right-click. 5 From the contextual menu, pick the Input Color Space that matches those clips. Leaning on RCM trims a few steps, because the input color space math used to transform the source keeps all the wide-latitude image data intact, leaving highlights easy to recover with no extra steps. With RCM on, there's no call to drop in CineonLog or Gamut nodes while on the Fusion page. The transforms to and from linear happen automatically based on the RCM settings. Moving to the Fusion page converts the images to linear and switches on the LUT button in the viewers with the Managed LUT picked. The Managed LUT leans on the RCM settings to take a linear image and display it according to the RCM output color space.

Should you want more detail on Resolve Color Management, turn to Chapter 9, “Data Levels, Color Management, and ACES.”

### Using ACES Color Management in Resolve

The ACES (Academy Color Encoding Specification) color space is yet another standard for handling color across an entire production. It's built to make start-to-finish, scene-referred color management achievable for digital cinema workflows. Much like DaVinci's RCM, ACES makes it simpler to draw high-precision, wide-latitude image data out of raw camera formats, to safeguard high-quality image data from acquisition all the way through color grading, and to deliver data of high quality for broadcast viewing, for film printing, or for digital cinema encoding. The way ACES operates is by assigning an IDT (Input Device Transform) to each camera and to each acquisition device. That IDT lays out how media from the device gets converted into the ACES color space. At the tail of the pipeline, an ODT (Output Device Transform) does the work of moving image data out of ACES color space and into the gamut of your final output. As with setting up RCM, DaVinci Resolve's color management project settings can be set for ACES, which flows through the Edit, Fusion, and Color pages. NOTE: When you're on Fusion Studio, the OpenColorIO (OCIO) framework handles ACES color management. Setting up ACES color management in DaVinci Resolve happens through the Color Science drop-down menu, found in the Project Settings' Color Management panel.

With ACES switched on, input and output devices are pinned down by the IDT and the ODT.

- Color Science: Through this drop-down menu, you can pick either ACEScct or ACEScc color science. This comes down mostly to personal preference, since the two are largely identical, though the shadows react differently to grading operations. On the Fusion page, images get converted to linear automatically, so whoever handles the grading has more reason to favor one over the other.

ACEScc: Pick ACEScc color science to put a standard Cineon-style log encoding onto the ACES data before DaVinci Resolve processes it. ACEScct: This take on ACEScc tacks on a roll-off at the toe of the image so that color-correction lift operations “feel” closer to how they do with film scans and LogC encoded images.

- ACES Version: Once you've selected one of the ACES color science options, this menu opens up so you can pick which version of ACES to use.
- ACES Input Device Transform: This menu lets you pick which IDT (Input Device Transform) to use for the dominant media format you're working with.
- ACES Output Device Transform: This menu lets you pick an ODT (Output Device Transform) to transform the image data so it matches the deliverable you need.
- Process Node LUTs In: This menu lets you set how LUTs are processed on the Color page; it has no bearing on the Fusion page.
- Disable tone mapping for Fusion conversion: Ticking this box strips any tone mapping out of the ACES color management.

To dig deeper into ACES inside DaVinci Resolve, turn to Chapter 9, “Data Levels, Color Management, and ACES.”

### Using OCIO for ACES Color Management in Fusion

On Fusion Studio, or whenever color management isn't in play in DaVinci Resolve, you have the option of bringing OpenColorIO nodes into Fusion so you can composite inside an ACES color space. Built for visual effects and computer animation work, OpenColorIO (OCIO) is an open-source color management framework. It's compatible with the Academy Color Encoding Specification (ACES). A trio of OCIO nodes, sitting in the Color category of the Effects Library, let you apply OCIO color space transforms in Fusion.

- OCIO CDL Transform node lets you create, save, load, and apply a Color Decision List (CDL) grade.
- OCIO Color Space delivers refined color space conversions that draw on an OCIO config file.
- OCIO File Transform lets you load and apply an assortment of LookUp Tables (LUTs).

Using OCIO to convert MediaIn or Loader nodes to linear gamma relies on the OCIO Color Space node. Dropping the OCIO Color Space node right after a Loader (or a MediaIn in DaVinci Resolve) shows the OCIO Source and Output controls in the Inspector.

To operate within an ACES color managed environment, you can lean on OCIO Color Space nodes.

Inside the Inspector for the OCIO Color Space node, Fusion supplies default Source and Output transforms for standard color spaces. To tap the full OCIO standard, though, you'll have to download and install the OCIO config file. That config file is available from the OCIO website. https://opencolorio.org Clicking the Browse button in the Inspector lets you navigate to the config file you downloaded. From the download, find the ACES 1.0.3 or later folder and pick the file config.ocio.

Whatever fills the Source and Output menus comes from the config.ocio file you download. As for the Source menu, it picks the color profile that applies to your Loader or MediaIn node. With the default raw setting, an untouched image appears, which essentially leaves the clip with no color management at all. Whatever you pick from the menu hinges on the recording profile of your media. The Output menu is set according to your deliverables. While working in Fusion Studio, the Output picked is typically ACEScg, so you work in a scene linear space.

### Applying OCIO LUTs in the Viewer

The viewer also carries OCIO View LUTs for calibrating the viewers. Once the OCIO Color Space View LUT is picked from the LUT menu above the viewer, choosing Edit on that same menu opens a dialog where the OCIO config file can be loaded.

Within Fusion Studio, you'll find the OCIO Color Space View LUT sitting in the Viewer LUT menu.

By default, the View LUT offers the same standard options. Clicking the Browse button, though, lets you load the very config file you loaded into the OCIO Color Space node. After it's loaded, all the expanded OCIO options become available. Having set the OCIO Color Space node to output ACEScg, you'd then turn to the OCIO View LUT, taking a source setting of linear sRGB across to an output of either sRGB or Rec. 709 in the majority of situations.

When you're working with the OCIO Color Space node in the Node Editor, the OCIO Color Space View LUT dialog is what configures the viewer. TIP: When your monitor is calibrated differently, you'll have to pick a LUT that lines up with your calibration. Setting the LUT by way of OCIO: 1 Open the LUT menu, then pick the OCIO Color Space View LUT from it. 2 Off that same menu, choose Edit. 3 Within the View LUT editor that opens, point the source's color space at lin sRGB 4 Point the output space at sRGB or REC 709, assuming a standard computer monitor is what you're viewing on. A normalized image now appears in the viewer, even though every color operation stays on linear images. No matter whether you reach for the OCIO Color Space LUT or a LUT matched to your particular monitor calibration, you're able to store the viewer setup as the default. Saving this OCIO ColorSpace LUT arrangement as the default viewer setup:

- Right-click in the viewer, and then choose Settings > Save Defaults. From here on, for each comp, the viewer comes preconfigured from the saved defaults.
