# Titles Generators And Stills (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Inside the Generators panel, the Fusion Generators section holds Fusion effects that have been turned into reusable generators. Out of the box, just one generator, Noise Gradient, is present to demonstrate how they behave. Fusion Generators behave the same as any generator. After you edit one into the Timeline, it behaves like any other clip, and selecting it surfaces adjustable parameters in the Inspector so you can shape its effect to fit your needs. Yet Fusion Generators offer an enormous amount of customization. Just opening the Fusion page while the playhead sits over a Fusion Generator on the Timeline's uppermost track reveals every Fusion node that builds that generator's effect, which lets you reconstruct the effect to suit whatever you have in mind. On top of that, anyone who knows how to build effects in Fusion can author their own generators by creating Fusion Macros and storing them in the Effects Library, where they then turn up in the Fusion Generators section of the Effects Library. To learn how, refer to Chapter 68, “Node Groups, Macros, and Fusion Templates,”

### Using Stills

Still images can be brought into the Media Pool and cut into the Timeline as clips whose durations you set yourself. Imported stills default to 10 seconds, yet you can stretch a still image's Out point all the way to 17 hours and 40 minutes, which should be plenty for nearly any project you have in mind, unless of course you happen to be Andy Warhol. In the same vein, DaVinci Resolve can pull in still image clips that XML or AAF project files point to, provided they sit in a supported format. The still formats DaVinci Resolve works with are:

File Format .tif .png .jpg .dpx .exr .dng .psd .tga .heif .NEF .CR2

Alpha Channel Support (by format, in order): Yes Yes No No Yes No No Yes No No No

After a still image clip is edited into the Timeline, it carries the very same Composite, Transform, Cropping, Retime, and Scaling attributes that any other clip has.

### Viewer Updates to Still Images by other Applications

When a still image is open in a Viewer inside DaVinci Resolve, you are now able to edit that exact image in a separate image editing application, save the change, and watch the Viewer refresh on its own to show the updated version.

Editing the image inside a separate app, here sketching a red circle within Pixelmator Pro, and then saving

Once the still image is saved in that separate app, DaVinci Resolve refreshes it on its own

### Photoshop File Support

At first a Photoshop (.psd) file shows up as one clip presenting only the bitmapped layers across the Edit page and Color page of DaVinci Resolve. That said, while you are on the Edit page, you can right-click an Adobe Photoshop Document (.psd) sitting in a timeline and pick Split PSD Layers in Place to break out each of the file's layers onto its own track. However many layers the file holds is how many new tracks you end up with.

Right-click Photoshop PSD layers and pick Split PSD Layers in Place to break them out onto separate tracks

### The results of splitting a PSD file

Because DaVinci Resolve interprets and divides rasterized flattened layers, you have to do a bit of prep on the source PSD asset ahead of importing it. Flattening layers in Photoshop to produce flattened layers is usually done by hand. The goal is to keep the image structure simple, bake in Photoshop-specific effects, and rasterize fonts so the file plays nicely with DaVinci Resolve. Here is how the process breaks down: Rasterize transparency and effects When your layers or fonts carry effects such as shadows or gradients, merging them may occasionally shift how they look. It is worth rasterizing first. To do that, pick one or more layers, right-click, and choose Rasterize Layer Style. Doing the same with text layers is advised too. Merge and flatten similar layers Group related layers next to each other and pick the ones you intend to merge. Right-click the chosen layers and choose Merge Layers (Cmd/Control+E) to fuse them into a single ‘flat’ layer. Where the Photoshop document is more involved, you might reach for the option: File > Scripts > Flatten All Layer Effects. Name layers Give the layers names that reflect the image, effect, or element beneath them. Labeling the flattened layers now lets DaVinci Resolve carry those names into the split clips.
