# Compositing Layers In Fusion (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Having selected the DeltaKeyer, we'll turn to the Inspector controls and extract our key by briefly sampling the green tone out of the image's background. Pull a key from the green-screen color by dragging the Eyedropper out of the Inspector and over the screen color shown in the viewer. While you drag across the viewer, a read-out of whatever color the Eyedropper is currently sitting on shows up in a floating tooltip, hinting at the actual hue you are about to grab. At the same time, with the Merge displayed in a second viewer, we see an instant preview of both the transparency and the image we wired into the background.

At left, the untouched image; at right, the result once the green screen has been sampled with the Eyedropper from the Inspector. Once the preview looks right, letting go of the pointer button locks in the sample, and the Inspector controls refresh to show the value we picked.

At left, the DeltaKeyer Inspector refreshing to show the sampled color; at right, the DeltaKeyer loaded into the viewer with the Color button clicked so the alpha channel it generates is visible. However strong the composite appears, after you have chosen the screen color for the key you still have to load the DeltaKeyer node directly into the viewer. Doing so lets you judge how clean or dense the alpha channel produced by the key actually is. At the top of the viewer, hit the Color button on the viewer toolbar, or click inside the viewer and tap C, to flip the viewer back and forth between the image's RGB color channels and the alpha channel. In a matte, black stands for the see-through regions and white for the solid ones. The gray zones stand for partial transparency. Apart from cases involving glass, smoke, or fog, the majority of mattes ought to be solid white and solid black with no gray gray areas at all. Should a careful look at the alpha channel turn up some fringing around the white foreground of the mask, the DeltaKeyer comes with built-in controls for cleaning up the key afterward and tightening the matte. Here is a short rundown of the main tweaks worth making.

Once you have made the screen pick with the Eyedropper, work through the adjustments below to refine the key.

- Push the Gain slider up to intensify the screen color so it turns more transparent. Because this can also eat into the foreground's transparency, use a light touch.
- Use the Balance slider to bias the foreground toward one of the two colors that aren't the screen. With a green screen, that leans the foreground more to red or blue and alters how transparency falls across it.

Selecting the third tab among the seven control tabs in the DeltaKeyer Inspector reveals an assortment of controls for working the matte. Your first tweaks in the matte tab might cover these parameters:

- Move the lower and upper thresholds to build up density across the black and the white regions.
- With a very light hand, work the Clean Foreground and Clean Background sliders to plug tiny gaps in the

black and white matte. Pushing these parameters higher makes the edges of your matte progressively harsher. Tweaking the Clean Foreground slider within the DeltaKeyer's Matte panel: here, nudging the Clean Foreground slider up slightly clears out the inner fringing we want gone, while leaving the key's edges essentially intact.

At left, the key as it started; at right, the same key once the Clean Foreground slider has been applied

That done, the key satisfies us, so we drop the Merge1 node back into the viewer and tap C to return the viewer's Color control to RGB. The background graphic is now visible, though at the moment it is too small to fill the entire frame, which calls for one more adjustment.

The key itself is now solid; the background is what still needs attention

### Dealing with Spill

Whatever screen color bounces off the background and falls onto your subject, the DeltaKeyer is able to deal with it. That reflected screen light goes by the name spill. Still, rather than letting a single node take care of both building the matte and fixing the spill, think about switching this off inside the DeltaKeyer and stripping the spill out with a dedicated color correction node instead. Switch off spill suppression in the DeltaKeyer like so.

- Select the matte tab in the Inspector.
- In the Replace Mode drop-down menu, pick Source. Doing that draws on the color taken from the original

source image, effectively disabling any spill correction in the DeltaKeyer.

Within the DeltaKeyer, the Replace Mode menu is what governs the way spill suppression behaves

You can now take care of spill with a color correction node dropped straight after the DeltaKeyer, or split off from the original MediaIn or Loader node and joined back together through a MatteControl.

Splitting the original image into two paths, one feeding the DeltaKeyer and the other feeding color correction

### Masking a Graphic

It is now time to deal with the top video track: the news graphic meant to sit to the newscaster's left. Since the graphic we are using is really one sheet holding several logos, we have to isolate a single logo with a mask and drop it into position.

A single graphic carrying several logos, which has to be trimmed down so only one remains. The simplest route to cropping a MediaIn or Loader node is attaching one of the toolbar's mask shapes straight onto it. With the MediaIn or Loader node selected, clicking the Rectangle mask in the toolbar will crop, or mask off, the graphic.

Masking off the logo with a Rectangle mask wired straight into a Merge node

From here, the only remaining task is to drive the Rectangle mask's onscreen controls to trim down to the region we want, sliding the mask around with the center handle and scaling it by pulling the top/bottom and left/right handles along the outer border. On top of that, you can deal with rounded corners while masking a graphic by reaching for the Corner Radius slider in the Rectangle mask's Inspector controls to apply that same rounding.

Shifting and scaling the mask so it frames our logo, then softening the corners by way of the Corner Radius Inspector control. On a basic over-the-shoulder graphic, masking the image might be the whole job, yet masking an image leaves the graphic's real dimensions untouched. All it alters is the portion you can see. As a result, placing the graphic precisely relative to the composite's center grows trickier, and any sort of match move would come out wrong since the graphic's resolution differs from the background's. You can correct this resolution mismatch by adding a Crop node after the MediaIn so the graphic layer's actual dimensions change.

Placing a Crop node downstream of the masked MediaIn so the trimmed logo sits centered over the background. Once the Crop node is selected, a Crop tool appears in the viewer toolbar.

### Selecting the crop tool in the viewer toolbar

Crop the image by dragging a bounding box around it. Whereas a mask just opens a small window you peer through, a crop genuinely resets the graphic's resolution to match the size of the crop bounding box.

At left, a bounding box being dragged with the Crop tool; at right, the trimmed logo sitting centered in the frame. NOTE: An image's resolution is likewise altered by the Resize, Letterbox, and Scale nodes. We are now ready to move the logo into position. Since the logo feeds the foreground input of a Merge, you can pick the Merge2 node, load it into the viewer, and rely on the built-in Center X and Y controls or the onscreen controls to drop the logo wherever you like and size it appropriately.

Positioning the logo by way of the Merge2 node's foreground input transform controls
