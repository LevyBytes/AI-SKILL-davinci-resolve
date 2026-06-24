# Understanding Image Channels (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Channel Boolean: A 3D node whose purpose is remapping and reworking the channels of 3D materials through an assortment of straightforward pre-defined math operations.
- Channel Booleans: Serves to shuffle or reorder RGBA and auxiliary channels inside one input image, or across two input images, producing a single output image. Should you wire only one image into this node, that image has to feed the background input so that everything functions properly.
- Copy Aux: The Copy Aux node serves to remap channels between RGBA channels and auxiliary data channels inside one 2D image. For the most part the Copy Aux node is a convenience node, since the same copying is achievable, with extra effort (and flexibility), through a Channel Booleans node.
- Matte Control: Built to carry out any mix of the following: (a) reassembling mattes, masks, and alpha channels in assorted ways, (b) reworking alpha channels by way of dedicated matte controls, and (c) writing alpha channels into the RGB stream of the image feeding the background input ahead of compositing. Particular channels can be copied from the foreground input over to the background input for use as an alpha channel, or you can hook masks up to the garbage matte input to serve as alpha channels too.

### Understanding Premultiplication

Having grasped how to steer and recombine RGB images and alpha channels within Fusion, it is now worth digging further into alpha channels so that you always pair RGB and alpha channels properly for every operation you carry out in your composite. It may look straightforward, yet tiny slip-ups happen easily and can leave behind ugly artifacts. This ranks among the most baffling corners of visual effects compositing, so don't bypass this section. Whenever a media file holds both alpha channel and RGB pixels — say a 3D rendered animation that carries RGB along with transparency, or a motion graphics movie file in which transparency is baked in — the pair can be joined in two distinct ways, and knowing which one applies matters.

- Unpremultipled (Straight): An RGB image left untouched by the semi-transparency data held in a fourth channel (alpha channel)
- Premultiplied: An RGB image whose every channel is multiplied by its alpha channel ahead of compositing.

Premultiplied alpha is a label editors, visual effects artists, and motion graphics designers have leaned on over the years, though it is loose. It is not the alpha channel that gets multiplied. Rather, the R, G, and B channels are multiplied by the alpha. Ultimately the alpha channel is unchanged, while the values held in the R, G, and B channels shift.

A RGB image (left) and its alpha channel (right)

Non-premultiplied images — at times referred to as “straight” alpha channels — carry RGB channels that the alpha channel has left untouched (not multiplied). As a consequence, the RGB image shows no anti-aliased edges and no semi-transparency. Typically you can plainly tell where the RGB image stops and the alpha matte starts. Below is an illustration of the ragged edges you get in the RGB channels with a non-premultiplied alpha channel. Note, though, the smooth semi-transparent edges present in the alpha.

A close-up showing, on the left, a non-premultiplied RGB image, with its alpha channel on the right With a premultiplied alpha channel, the RGB pixels have been multiplied by the alpha channel. That approach ensures the RGB image pixels carry semi-transparency where it is called for, such as anti-aliased edges. For the sake of convenience most computer-generated images come premultiplied, since that makes them simpler to review smoothly without ever dropping them into a composite.

A close-up showing, on the left, a premultiplied image, with its alpha channel on the right What is the upshot for compositing? A premultiplied image's edges look far smoother, which is what makes them preferable when you composite foreground over background in a merge. As a result, every alpha channel is rendered premultiplied within compositing operations if it was not already. Conversely, color correcting a non-premultiplied RGBA image is always the better course, because you would rather not disturb an image's pixel values once the RGB channels have been multiplied by the alpha channel. Looking at it through a mathematical lens:

- RGB pixel value x 0 = 0: The black transparent regions of an alpha channel hold a pixel value of 0. Take an RGB pixel's value, multiply it by 0 (n x 0 = 0), and by the rules of multiplication the RGB value drops to 0, or fully transparent.
- RGB Pixel value x 1 = RGB Pixel: The solid, opaque white regions carry a value of 1.0. Take an RGB pixel's value, multiply it by 1 (n x 1 = n), and the RGB value is unchanged, fully opaque.
- RGB Pixel value x 0.3 = A different color: Running along an alpha channel's edges are gray pixels that mark semi-transparency. Such semi-transparent pixels hold a value somewhere between 1.0 and 0.0. To carry the alpha channel's anti-aliased edges over to the RGB channels, you multiply the pixel values. That multiplication blends a certain proportion of the transparent pixels (black) into the RGB pixels. While this is what you want for clean anti-aliased edges, you cannot color correct the image afterward, since doing so disturbs the smooth semi-transparency you built once it is finished.

Multiplying RGB pixels against differing levels of transparency yields a changed RGB value.

### The Rules of Premultiplication

Building on what was laid out above, whenever you composite several images together and at least one carries a built-in alpha channel, you will want to stick to these broad rules so problems stay away:

- Always use premultiplied images with a Merge node.
- Only color-correct images that are not premultiplied.
- Always filter and transform images that are premultiplied.
- Never double premultiply an image.

### Premultiplication and the Merge Node

A Merge node's foreground input looks for a premultiplied RGBA image. Being an additive merge, it lays the foreground's semi-transparent regions over the background. Yet when the image is not premultiplied, the pixels meant to be transparent still get added in, which usually produces an unwanted bright fringe ringing your foreground subject's edges. Should you be compositing with a non-premultiplied alpha, you can cure these bright edges by switching the Merge over to a Subtractive merge in the Inspector.

On the left, nonpremultiplied edges within an additive Merge; on the right, premultiplied edges within an additive Merge

TIP: Suppose an RGB image and a Mask node are joined through, say, a Matte Control node; if the RGB image goes unmultiplied by the mask within the Matte control, the checkerboard background pattern in the viewer will look merely semi-transparent when it ought to be fully transparent.

### Color Correcting Premultiplied RGBA Images

Premultiplying an image binds any edits to the RGB pixels' brightness to the alpha channel pixels too. Raise the foreground image's brightness in any fashion, for instance, and you will lift the alpha channel's brightness as well, which is rarely what you want since it shifts the transparency the alpha channel produces. Viewed at the Merge node, the visible upshot is that the whole background grows brighter (or darker, had you dropped the RGB brightness) according to your color tweak. For that reason, the rule is to always divide the semi-transparent pixels before doing any color correction on an image bearing an alpha channel. You can pull this off by switching on the Pre-Divide/Post Multiply checkbox in any node that does color correction. Or you can lean on the Alpha Divide and Alpha Multiply nodes for the same effect. These approaches get fuller treatment later in this chapter.

On the left, color correcting a premultiplied foreground wrongly shifts the background; on the right, color correcting a nonpremultiplied foreground behaves correctly.

### Double Premultiplied RGBA Means Double Trouble

One frequent error many artists fall into is overcompensating for premultiplication. Premultiplying the alpha ahead of compositing within a Merge node is vital, yet just as vital is not premultiplying the alpha twice. Running a premultiply operation twice back to back can throw a darkened halo around your images. In effect you are multiplying by the gray semi-transparent pixels a second time; that is not ideal.

On the left, a double premultiplied image showing dark edges; on the right, a premultiplied image whose edges are correct

### Premultiplied Alpha Channels and Filtering

Where filtering is concerned, the RGBA channels' state ought to be irrelevant for the bulk of composites. An exception could crop up, though, when the filter algorithm you pick involves color modification. As an example, if a filter tries to mimic a defocus by blooming highlights the way a genuine light source would, that filter might over-brighten pixels close to a transparent edge, leaving some kind of artifact once that image is composited.

### Alpha Channel Status in MediaIn and Loader Nodes

Bringing a clip into the composite with a Loader node, you will find that the Import tab in the Inspector holds a set of checkboxes for deciding how an embedded alpha channel gets treated. These include a checkbox that makes the alpha channel solid (disregard transparency), one to Invert the alpha channel, and one to Post-Multiply the RGB channels against the alpha channel, where that proves necessary. With a MediaIn node, you can change how an embedded alpha channel is read by way of the Clip attributes window. The Clips Attributes window carries an Alpha Mode menu setting for picking whether the alpha channel is disregarded, taken as premultiplied, inverted, or taken as nonpremultiplied (straight).

### Controlling Premultiplication in Color Correction Nodes

The majority of nodes that make you explicitly handle an RGBA image's premultiplication state carry a “Pre-Divide, Post-Multiply” checkbox. That covers basic color correction nodes like Brightness Contrast and Color Curves, plus the Color Correct node, which keeps the “Pre-Divide/ Post-Multiply” checkbox inside the Options panel of its Inspector settings.

Shown in the Inspector, the Color Curves node's Pre-Divide/Post-Multiply checkbox This checkbox lets you wire an RGBA premultiplied image into the node and run a color correction operation. It takes in the RGBA image, runs a divide operation to strip out the semi-transparency, and then runs a multiplication operation before sending out the color corrected image. That way, the color correction happens on a nonpremultiplied image while the output that comes back is a Merge-friendly premultiplied image.

### Controlling Premultiplication With Alpha Divide and Alpha Multiply

The Alpha Divide and Alpha Multiply nodes, sitting in the Matte category of the Effects Library, come into play when several operations in succession expect a “straight” alpha channel. Rather than repeating Pre-Divide/Post Multiply operations on every node, you can deploy these two nodes to bracket the rest. Just drop in the Alpha Divide node when you want the RGBA image data left non-premultiplied, and drop in the Alpha Multiply node when you want the image data premultiplied once more. As an example, when you rely on third-party OFX nodes that perform color adjustments, you might have to govern premultiplication by hand both before and after such an adjustment.

A node tree with explicit Alpha Divide and Alpha Multiply nodes

### Multi Channel Compositing

If you have headed to the cinema for any recent superhero movie, you will have witnessed the fruits of advanced 3D rendering paired with a great deal of compositing. 3D applications can produce strikingly realistic images, but the time needed to render each frame of those realistic images runs into hours rather than minutes. Any tweak to the 3D images — even fairly basic moves such as color adjustments, focus changes, filtering, or extra masking — forces a full re-render of those images, which leaves you waiting, frequently again and again. For the sake of efficiency, it is far quicker to make iterative changes achievable through 2D image processing operations in Fusion instead. So that you keep the freedom to make routine after-the-fact changes to 3D images, the assorted attributes making up the 3D scene get split apart and rendered as separate image sequences, commonly called render passes. As an example, render passes are routinely produced for attributes such as raw color, shadows, and reflections, which can then be reassembled as a 2D composite to deliver the finished result. Rendering different attributes into different image sequences hands you a great deal of flexibility, since each image attribute can now be color corrected, blurred, or otherwise processed apart from the image's other attributes, using fast-processing operations in Fusion. The render passes most commonly produced come out of the 3D scene's RGBA channels. Together these are called beauty passes and may take in attributes like color, shadows, lighting, reflections, environment, and more. Render passes can likewise hold non-RGB data. Across effects applications these passes carry assorted names — among them Data Channels, or AOVs (Arbitrary Output Variables). Within Fusion these channels are termed Auxiliary Channels, and the 3D data they hold runs to things like Depth, Normals, Motion Vectors, and UV Coordinates (these being just a handful). When you composite a 3D render made up of several render passes, the beauty passes get handled one way while the Auxiliary Channels get handled another. Because Fusion nodes carry RGBA channels by default, beauty passes come first here, with how to handle Auxiliary Channels explained later in this chapter.

### Compositing with Beauty Passes

Every attribute of a beauty pass can be rendered into its own image sequences, so you wind up with a numbered run of images: a diffuse pass here, a reflection pass there, a shadow pass alongside them, and so on. As an alternative, all the passes can live inside a multi-part EXR image sequence. Multi-part EXRs have the upside of demanding slightly less file management, though Fusion handles the passes much the same whichever method you choose.

One MediaIn or Loader node deals with only a single beauty pass, since just one set of RGBA channels comes out of each node. Building your composite in Fusion therefore calls for a separate MediaIn or Loader node per pass.

A MediaIn or Loader node is needed for each beauty pass. TIP: Fusion's handling of the EXR format is optimized when several Loaders read the same EXR file. The file loads just once to reach all the channels.

### Beauty Pass Setup

Split-out components of 3D renders — diffusion, shadows, or reflections, for instance — can each be rendered on their own using RGB channels. When you are handed separate image sequences for every image component, they import and open in Fusion and can show in the viewer just like any other clip. When you work with multi-part EXR files, you essentially hold several RGB images bundled in one file. The MediaIn and Loader nodes, however, can only draw on one set of RGB channels at a time. To composite multiple RGB beauty passes with one another, you have to bring in several MediaIn or Loader nodes pointing at the same image sequence yet assigned to different passes held in the EXR file.

Several Loader or MediaIn nodes feeding off one multi-part EXR image sequence TIP: It pays to rename each Loader or MediaIn after the beauty pass it carries.

Mapping Each Set of Beauty Passes to a Particular Node Whether you sit on a MediaIn node or instead a Loader node, mapping beauty passes onto RGB channels happens through one of the Inspector's Image tab, Channels tab, or Format tab. On a Loader node, it is the Loader's Format tab that handles it.

Within a Loader node, beauty passes assigned across the red, green, and blue channels The MediaIn's Image tab carries a Layer menu. Any pass held in a multi-part EXR image sequence can be picked from this menu and assigned to the RGBA channels automatically.

Inside a MediaIn node, the Layer menu listing headings for the combined channel passes Most of the time the menu lists the combined channel passes, which means the separate red, green, blue, and alpha channels are not selectable. Since the alpha channel is missing from many beauty passes, now and then you must borrow the alpha channel from another beauty pass. That is why the Channels tab is frequently the better place for mapping a beauty pass's individual channels onto the MediaIn node's channels.

Reaching the individual channels is done through either the Channels tab on the MediaIn node or the Format tab on the Loader. That same channel mapping functionality lives in both the DaVinci Resolve MediaIn node and a Loader node's Format tab. Up at the tab's top, individual RGBA menus appear on the Channels tab as well as on the Format tab. These menus let you map the RGBA channels off any pass held in the multi-part EXR. To map the Ambient Occlusion pass onto the RGB channels, for instance, pick AO. R (Red) out of the Red channel menu; next set AO. G (Green) by way of the Green channel menu; then assign AO. B (Blue) using the Blue channel menu. Within the MediaIn node, a pass' individual channels assigned across the red, green, blue, and alpha channels TIP: Beauty passes get labeled differently from one 3D application to the next. For example, an Ambient Occlusion beauty pass might be named AO, AM_OCC, or some other abbreviation. No alpha channel comes with the Ambient Occlusion beauty pass. To composite it, the alpha channel pass from another beauty pass can be reused. In the image below, the alpha channel is drawn from the combined render pass' alpha channel.

An alpha channel borrowed from another beauty pass joined onto the Ambient Occlusion pass

TIP: With the Format tab in the Loader node, the checkbox beside each channel has to be switched on for that channel to surface in the node's output.

### Compositing Multiple Beauty Passes in the Node Editor

After all your passes are imported and mapped to RGBA channels, you will be left with a string of MediaIn or Loader nodes. Just how many MediaIn and Loader nodes really comes down to your workflow. No fixed count of passes is set in stone. Each studio settles on its own standard set. Even so, certain render passes turn up in the majority of composites. What follows is a roster of commonly used render passes alongside their generic names.

### Commonly used beauty passes, compared

Compositing several beauty passes down to one output image is fairly painless. 3D rendering applications generally put out linear gamma, so no Gamut or other color space conversion nodes are needed provided you keep the image in a linear color space for easy compositing. The core compositing gets done with either a Merge node or a Channels Booleans node. Both support additively combining render passes. There is no hard requirement to composite each pass any particular way, though in most cases a plain additive composite ought to do fine. To start compositing render passes by way of a Merge node: 1 Feed a Color pass into a Merge node's background input. 2 Feed a Direct Lighting pass into the foreground input. 3 Tune the Alpha gain and Blend parameters until the look suits you.

The first move in compositing beauty passes is wiring a background and a foreground into a Merge node Should you rather, the same composite can be built with a Channels Booleans node. In that case nothing technical separates the two nodes. To composite render passes via a Channels Booleans node: 1 Feed a Color pass into a Channels Booleans node's background input. 2 Send a Direct Light pass to the foreground input. 3 Out of the Operations menu, pick Add 4 Out of the Alpha To menu, pick Do Nothing.

Here Channel Booleans sits on Add, blending the foreground input with the background input. Shadow passes — Ambient Occlusion among them — count as exceptions to the steps above. For those, a multiply Apply mode is the customary pick. To composite an Ambient Occlusion render pass via a Merge node: 1 Wire the last in a chain of Merge node render passes into a Merge node's background input. 2 Send an Ambient Occlusion pass to the foreground input. 3 Out of the Apply Mode menu, pick Multiply. 4 Tune the Gain and Blend parameters until the look suits you. Simple as that may sound, compositing by a fixed recipe does not pan out for every shot. With different images, you may have to try out various compositing techniques to land the best results.

### Embedding Alpha into Beauty Passes

Not every beauty pass carries an alpha channel. When a shot calls for laying your assembled beauty passes over live-action or some other backdrop, supplying the alpha channel from a pass that does carry one may fall to you. To work an alpha channel into your assembled beauty pass composite, proceed as follows: 1 Wire the final Merge or Channel Booleans output into a Matte Control node's background input. 2 Wire the render pass holding the alpha into the green Foreground input on the Matte Control node. 3 Over in the Matte Control's Inspector, pick Combine Alpha from the Combine menu. 4 Out of the Combine Op menu, pick Copy.

The color pass' alpha channel restored into the finished beauty pass node tree TIP: Alpha channels off 3D renderings tend to be premultiplied. With that in mind, make sure the Pre Divide/Post Multiply checkbox is switched on for any node doing color correction. If more than one node in a row handles color correction, reach for the Alpha Divide and Alpha Mult nodes instead.

### Working with Auxiliary Channels

Auxiliary channels are not RGB images; rather they form a family of special-purpose 3D image data that generally conveys position, orientation, and object information for use in 2D composites. As an example, Z-Depth channels record how deep each pixel of an image sits along a Z-axis, while an XYZ Normals channel records the orientation (facing up, facing down, facing left or right) of every pixel in an image. As with the use of multiple beauty passes, one of the chief motives for using auxiliary data is to do away with re-rendering computationally costly 3D imagery, by letting still more facets of rendered images be manipulated after-the-fact. Since 3D rendering is computationally costly and slow, putting out descriptive information about a 3D image permits refined alterations to take place in 2D compositing, which is quicker to do and to adjust. Auxiliary channel data can be obtained in two ways:

- First, auxiliary data can be embedded inside a clip rendered out of a 3D application, most often through the EXR file format. In that case, your best bet is to check your 3D application's documentation to learn which auxiliary channels it can produce and output.
- Auxiliary channel data can also be had by producing it inside Fusion through 3D operations — those put out by the Renderer 3D node, those from the Optical Flow node, or those from the Disparity node.

An RGBA 3D rendered scene that also contains auxiliary channels TIP: While hunting for information on auxiliary channels in other software, bear in mind that some 3D applications call auxiliary channels Arbitrary Output Variables (AOVs), render elements, or secondaries.

### Aux Channel Setup

With a MediaIn or Loader node tied to a multi-part EXR file holding auxiliary channel data, the Inspector's Channels or Format tab carries a pre-defined set of auxiliary channels meant for mapping. Each pre-defined channel comes with a menu listing every attribute held in a multi-part EXR. From that menu you pick the render pass to assign to the matching channel. As covered earlier, RGB beauty passes such as diffuse, shadow, and reflection get mapped onto the red, green, and blue channels. Auxiliary passes arrive with preset mappings.

Inside a MediaIn node, a multi-part EXR file whose embedded render passes are assigned to their aux channels

### Displaying Channels in the Viewer
