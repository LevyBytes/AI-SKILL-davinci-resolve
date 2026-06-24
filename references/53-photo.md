# Photo (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Photo

Photo Image Editing Now Fully Integrated Within DaVinci Resolve.

### Photo Page

A capable new Photo page arrives with DaVinci Resolve 21. The page exists so users can organize, sort, and grade their photo projects through every powerful grading and color management tool that ships natively in Resolve. It stands as the very first image editor woven completely into a video editing pipeline, and so far the only one.

### Photo Page

At its core the Photo page is a photo editing app, yet its deep ties into the remainder of DaVinci Resolve's effects and toolset unlock creative options that still image editing usually can't reach. Photo Albums let you hand off full resolution stills to the Cut, Edit, Color, and Fusion pages for further work. A complete image management pipeline lives in the Photo page, covering tagging, favorites, ratings, and photo album collections. On top of that, you can tether a camera to the Photo page to grab images and adjust the camera's settings on the fly. The fresh IntelliSearch feature has the AI examine your images so you can then find them by content, objects, people, colors, and more. Built into the Photo page is a sizeable effects library, packing several of the strongest Resolve FX and Fusion FX ready for use. Bringing the Photo page into DaVinci Resolve means you can glide effortlessly between photos, video editing, color grading, VFX, and audio post, every bit of it in real time.

NOTE: Every grade and effect on still images inside albums gets applied at the source level. As a result, the grades on your stills carry across all of a project's albums, much like remote grades do.

### Using the Photo Page

### The Interface Toolbar

Across the very top of the Photo page runs a toolbar whose buttons let you reveal or conceal various parts of the interface. Reading left to right, the buttons go as follows: Photo Page Toolbar Media Pool: Reveals or conceals a compact version of the full Media Pool page, granting access to every image the project uses. Effects Library: Reveals or conceals the store of all transitions, generators, and effects usable on the Photo page. Photo Album: Brings up the Photo Album along the bottom of the interface. Quick Export: Brings up the Quick Export Dialog for an easy export of your photos. Metadata: Reveals or conceals the Metadata Editor. Capture: Reveals or conceals the capture interface that lets you grab still photos onto your computer while tethered to a camera. Inspector: Reveals or conceals the Inspector, which lets you tweak both RAW and debayered photo parameters along with any effects properties.

### The Media Pool

On the Photo page, the Media Pool holds only the still image media you've brought into the current project for editing, plus all the albums you'll use to keep your photos organized. Unlike the Media Pools on other pages, it surfaces no video, audio, timelines, or effects clips. Those still exist, naturally, merely concealed from sight, since the Photo Page is devoted exclusively to still images.

### The Media Pool in the Photo Page

Clicking the Bin list at the top left brings up a tiered list of bins for sorting your photos, which doubles as the means of sorting your albums. By default the Media Pool holds one bin called "Master," though you can add more as you need to keep timelines and clips organized by clicking the Bin List and selecting + Add Bin. Renaming any custom bin is done by double-clicking its name and typing a fresh one, or by right-clicking the bin's name and selecting Rename Bin.

Clicking on the Bins icon, opens the bin list dropdown.

Whatever folder is selected has its contents shown in the browser area. Each still photo, bin, and album turns up here. As many albums as you like can be made inside one project. Either Thumbnail or List view can display the Media Pool. While in List view, sorting the contents is possible by any of a subset of all the metadata that the Media page's Metadata Editor makes available. Importing Photos Into the Media Pool on the Photo Page True, putting photos into the Media Pool from the Media page gives you the most organizational flexibility and features, but if you find yourself over on the Photo page needing a handful of photos brought in quickly for right-now use, a pair of methods exist. Via the Import Media icon on the Photo page's Media Pool: 1 With that page open, click the Import Media list icon sitting atop the Media Pool. 2 Pick from these options:

- Import Media: Brings up a file requestor for importing the photos you chose.
- Import Media Folder: Brings up a file requestor that pulls in every photo within the folder you chose.
- Import from Photos (macOS only): Launches the macOS Photos app and has you

select photos for import.

- Import from Lightroom: Pulls in an Adobe Lightroom Catalog.
- Import Blackmagic Cloud Folder: Lets you link up a Blackmagic Cloud folder and

bring in the photos kept inside it. Via the Import Media command on the Photo page's Media Pool: 1 With that page open, right-click somewhere inside the Media Pool and select Import Media. 2 Through the Import dialog, choose one or more photos to bring in, then click Open. Those photos land in your project's Media Pool.

### Bins and Smart Bins

In fact, the Media Pool holds two sorts of bins, and each one shows up in its own area of the Bin list. The distinctions between the two kinds of bins are these:

- Bins: Plain, hand-filled bins. Drop whatever you wish into a bin, and that's its home until you choose to relocate it elsewhere. Since bins can nest hierarchically, you're free to build a Russian-doll arrangement of bins if that suits you. Making new bins takes nothing more than right-clicking inside the bin list and selecting Add Bin from the contextual menu.
- Smart Bins: These fill themselves procedurally, which means custom metadata-based rules dynamically sift the Media Pool's contents the moment you pick a Smart Bin. That turns Smart Bins into quick ways to organize the contents of projects where you (or an assistant) put in the effort to attach metadata to your photos via the Metadata Editor, adding exif data, keywords, comments, description text, and countless other details so you can locate what you want faster when the need arises. To build a new Smart Bin, click the bin list and pick + Add Smart Bin. Up comes a dialog where you can name the bin and define the rules it applies to filter clips, then click Create Smart Bin.

### Searching the Media Pool

Clicking the magnifying glass icon on the toolbar reveals a search field where you can hunt for particular image names. The new IntelliSearch feature covered elsewhere in this guide, however, lets you harness AI technology for thorough, almost instant searching of the people and objects you type into that field.

### Effects Library

Every effect you might add to your photos resides in the Effects panel. That panel presents a tiered list of all the assorted effects and filters on offer, arranged by category.

### The Photo Effects library

For a preview of an effect before you place it on a photo, confirm "Hover Scrub Preview" is ticked in the Effects option menu, then just hover your pointer over any thumbnail in the Effects tab and glide it across that thumbnail. Using its default parameters, the effect previews in the Viewer. To switch a particular effect on for a photo, simply drag the chosen effect's thumbnail onto a photo in the Album. Open the Effects tab in the Inspector to adjust that effect's parameters. A given effect is searchable by typing into the search bar atop the Effects Library. Hitting Shift-Space summons the Effects Search dialog on the Photo page. With a photo selected, clicking an effect in the search list applies it to that selected photo. Category Names work as search terms for finding effects and transitions. Search "Stylize," for instance, and every Resolve FX under the Stylize heading appears. You can likewise search for effects in whatever language is set under DaVinci Resolve > Preferences > User > UI Settings, alongside English. NOTE: Every effect gets a full write-up within the Resolve FX portion of the DaVinci Resolve Reference Manual Photo Albums Clicking this tab brings up the Photo Album along the bottom edge of the interface. As with their physical counterpart, Photo Albums on the Photo page are where you keep and arrange collections of still images. Inside DaVinci Resolve they amount to a special breed of timeline, assembled from user-curated stills. Sorting your media pool images into photo albums matters greatly for squeezing the most out of the still photo features in DaVinci Resolve 21. Photos stay independent of resolution and frame rate, whereas timelines do not. The Photo page leans on the Photo Album as its main organizational container, allowing your photos to engage with the rest of DaVinci Resolve's pages.

### The Photo Album Interface

### A Photo Album in the Media Pool

To create a Photo Album:

- Within the Media Pool, right-click and choose New Photo Album off the context menu.
- From the main menu, choose File > New Photo Album.

Adding one or more images to a Photo Album goes like this: 1 Select an image, or several, inside the Media Pool. 2 Right-click an image and choose Add Photo(s) to Album 3 Your selected photos join the current Photo Album Removing one or more images works similarly: 1 Select an image, or several, inside the Media Pool. 2 Right-click an image and choose Delete Selected. 3 Your selected photos leave the current Photo Album After an album is built and stocked with photos, the Photo Album toolset lets you rapidly arrange, sort, and label still images for later use in DaVinci Resolve. You can attach flags, colors, and tags to images in the Viewer, then lean on the Photo Album's filter tools to arrange and sort them.

### The Photo Album filtering icons

Filter By: When active, the Icons glow white. Tags: Clicking this icon lets you filter the album's photos by tag. Right-clicking it lets you set the criteria to Good Take, Untagged, or Rejected flags, or some combination of those tags. Rating: Clicking this icon lets you filter the album's photos by rating. Right-clicking it lets you set the criteria using one of three comparisons (equal to; is less than or equal to; is more than or equal to), followed by the precise star rating you want as the base criteria. Flags: Clicking this icon lets you filter the album's photos by flag. Right-clicking it lets you pick which color flag or flags serve as the criteria. Color: Clicking this icon lets you filter the album's photos by clip color. Right-clicking it lets you pick which color or colors serve as the criteria.

Keywords: Clicking this icon lets you filter the album's photos by keyword. Right-clicking it lets you pick which keywords serve as the criteria. Sort Photos: Clicking this icon flips the album's photo sort order between ascending and descending value. Right-clicking it lets you pick which metadata value drives the sort criteria. Photo Album thumbnails additionally carry icons telling you whether certain operations have been applied to the photo.

### The Photo Album thumbnail icons

Photo Album list of thumbnail icons and their meanings:

- Rainbow Rectangle around image number: Signals that a RAW or Photo operation is in place.
- Star Rating: The rating the user gave the clip. Click the rating to alter it.
- Flag: Up at the thumbnail's top right, a tinted flag icon tells you which flags belong to the photo.
- Color: Down at the lower right, the little tinted capsule shape reveals which colors belong to the photo.
- Heart or X: This reveals whether the photo carries a favorite or a rejected tag.
- Image Format: Beneath the thumbnail at the lower left, this reveals the photo's image format.
- FX: Beneath the thumbnail at the lower right, this reveals that an effect is in place on the photo.
- Transform: Beneath the thumbnail at the lower right, the rectangle icon reveals that a transform operation is in place on the photo.
- Crop: Beneath the thumbnail at the lower right, the overlapping angles icon reveals that a crop operation is in place on the photo.

### Advanced Filtering

Should you want richer Filtering choices, you can sort and filter photos through the dropdown menu beside the Photo Album tag. Attributes you can filter on include things like People, Graded vs. Ungraded photos, or Photos changed within the past X hours, among others.

### Using Photo Albums in other DaVinci Resolve Pages

Photo Albums serve as a way to shuttle still photos at their native resolution among the different pages within DaVinci Resolve. That means beyond the Photo page, the tools on the Cut, Edit, Color, and Fusion pages can be used on your still photos too.

### The Viewer

The Photo Viewer gives you a close look at a single photo as you edit it, and it also carries its own toolset for working with your photos.

### The Photo Viewer

### Top Toolbar

### The Photo Viewer top toolbar

- Photo Album: Displays whichever image is selected.
- Capture Live View: Brings up the live view while shooting tethered.
- Zoom %: Lets you set the viewer's zoom level.
- Album List: Displays the current Album. Use the dropdown menu to jump straight to a

recent album.

- Single View: Brings up a large single viewer.
- Lightbox: Switches into Lightbox mode, displaying resizable thumbnails for every image in your album.
- Viewer Guides: Brings up guides for various aspect ratios, safe areas, plus user-customizable rulers

and guidelines.

- Bypass Color and Fusion: Skips over any Color or Fusion effects that might be in place. The dropdown menu lets you

skip only Color, or only Fusion.

### Lightbox

Clicking the Lightbox icon swaps the single photo view for a spread of resizable thumbnails, one per photo in your album. This lets you view larger versions of many photos at once and gives a broad sense of your album's contents. You can even grab any image and grade it live while watching the results ripple across the entire collection in real time.

### The Photo Viewer Lightbox

### Hand Mode

Press and hold the H key in the viewer to enter hand mode. While hand mode is on, the image view scales to 100% and dragging the hand around the viewer shifts the picture. Double-click an area to inspect individual pixels. Double-click again to zoom out and fit the image to the viewer.

### Bottom Toolbar

### The Photo Viewer Bottom toolbar

- Tools: Brings up the Transform, Crop, and Effects Overlay interfaces.
- Exif Data: Displays the ISO, Shutter Speed, Aperture, and Lens metadata.
- Favorite: Marks the image a favorite with a tiny heart icon.
- Untag: Strips the favorite or reject tag off an image.
- Reject: Marks the image rejected with a tiny x icon.
- Version Selector: Pick a different saved version of the image.
- Rating: Lets you give the image a one-to-five star rating.
- Color: Lets you attach a color tag to the image. Color tags serve organizational

operations on DaVinci Resolve's other pages.

- Flag: Lets you attach a color flag to the image. Flags serve organizational operations on

DaVinci Resolve's other pages.

### Transform Toolbar

Choosing Transform brings up onscreen transform controls that let you work the image directly in the Viewer. Drag anywhere within the clip's bounding box to set pan and tilt, drag a diagonal corner to resize proportionally, drag a top, bottom, left, or right side to squeeze or stretch the width or height, or drag the center handle to rotate.

### The Transform Toolbar

NOTE: While the onscreen controls are active, the tool keeps the original photo size visible beneath the transform grid. The intent is to let you still see the regions beyond the frame as you make adjustments. Shutting the tool bar back down commits the transform operation and applies it to your image. These onscreen controls also map to the following editable parameters, themselves editable in the Video Inspector too.

- Toggle Button: Lets you switch an effect off or on without surrendering any custom adjustments you've put in.
- Zoom Width and Height: Lets you enlarge the image or scale it down. Link the X and Y parameters to lock the image's aspect ratio, or unlink them to stretch or squeeze the image along one direction alone.
- Zoom Link: Engage this lock to bind width and height zoom together so a zoom keeps the same proportions. Disengage it to zoom width and height on their own.
- Position X and Y: Shifts the image inside the frame so pan and scan adjustments are possible. X slides the image left or right; Y slides it up or down.
- Rotation Angle: Spins the image around the anchor point.
- Pitch: Tilts the image toward the camera or away from it about an axis crossing the

image's center from left to right. With positive values, the image's top swings away while the bottom comes forward. With negative values, the top comes forward while the bottom swings away. The larger the value, the more extreme the stretch.

- Yaw: Tilts the image toward the camera or away from it about an axis crossing the image's center from top to bottom. With positive values, the image's left comes forward while the right swings away. With negative values, the left swings away while the right comes forward. The larger the value, the more extreme the stretch.
- Flip Image: A pair of buttons flips the image along different dimensions. Flip Horizontal control: Mirrors the image along the X axis, left to right. Flip Vertical control: Mirrors the clip along the Y axis, flipping it upside down.
- Reset: Lets you return every parameter inside a given control category to its default settings.

### Crop Toolbar

A set of onscreen controls on the Photo page lets you crop the image straight in the Viewer. Every side of the image carries its own handle for cropping just that edge. These parameters are editable in the Video Inspector as well.

### The Crop Toolbar

NOTE: While the onscreen controls are active, the tool keeps the original photo size visible beneath the crop grid. The intent is to let you still see the regions beyond the frame as you make adjustments. Shutting the tool bar back down commits the crop operation and applies it to your image.

- Toggle Button: Lets you switch an effect off or on without surrendering any custom adjustments you've put in.
- Aspect Ratio: Lets you select common aspect ratios for still photo and video formats, or set a custom ratio of your own. Defaults to As Shot, your camera's native aspect ratio.
- Lock Aspect Ratio Engage this lock to fix the chosen aspect ratio across any crop operations. Release it to crop at a freeform aspect ratio.
- Crop Left, Right, Top, and Bottom: Lets you trim away, in pixels, each of the image's four sides.
- Reset: Lets you return every parameter inside a given control category to its

default settings.

### Open FX and Fusion Overlays

When you've applied an Open FX or Fusion Effect carrying onscreen viewer controls, those controls become reachable here by pressing the right icon.

### The Overlay Toolbar

### Adding Versions in a Photo Album

Among a Photo album's handier capabilities is its versioning feature. Make edits to a photo, save it as a version, then attempt something wildly different on that same image, secure in knowing the original version stays safely kept. Save as many versions of an image as you wish.

### The New Version dialog Box

Creating a version is straightforward: just make your edits, right-click a photo in the Photo Album, and pick New Version from the context menu. That brings up the New Version dialog box, where you can type a descriptive name for the version and then hit the OK button.

The Version Dropdown at the bottom of the Photo Viewer Switching versions is just as effortless. Any version you've saved becomes available in the very same right-click context menu you made it from. A simple dropdown selector also sits along the Photo Viewer's lower edge for the same purpose. IMPORTANT: At export time, only whichever version is selected goes out through Quick Export and the Deliver page; the rest are left out.

### Quick Export

A delivery window tailored specifically to still images is what Quick Export opens. You merely choose the image format you want from the left side, enter the file's parameters on the right, then click export.

### Quick Export tab in the Photo Page

Exactly which file parameters appear hinges on the image format you choose, but the usual ones are:

- Export: Choose whether to export the whole Album of photos or only the selected ones.
- File Name: Lets you supply text that serves as a file name prefix.
- Scale: Pick either original resolution or a percentage-reduced resolution to shrink file sizes.
- Include Metadata: Tick this box to bake the photo's metadata into the final image.

TIP: When you need finer control over your photo export, the Deliver page tools are an alternative.

### Metadata

On the Photo page, the Metadata Editor appears in the same spot as the Inspector. Select a photo in the Media Pool or Album and its metadata shows up inside the Metadata Editor. Select several clips and only the first clip's information is displayed. Up in the Metadata Editor's header sit uneditable details about the chosen clip, among them the file name, directory, duration, frame rate, resolution, and codec.

Given how very many metadata fields exist, a pair of drop-down menus at the top let you switch which set of metadata the Metadata Editor displays. Metadata Presets (on the left): If you built your own custom metadata sets through the Metadata panel of the User Preferences, this drop-down picks which one to surface. Rather amusingly, this sits at "Default" by default. Metadata Groups (on the right): This drop-down menu lets you jump between the assorted metadata groups available, sorted for particular tasks or workflows. At the heart of the Metadata Editor lies a run of editable fields below the header that let you review and revise the various metadata criteria on offer.

### Capture

This tab opens up the Capture Live View interface for tethered shooting straight from your camera into DaVinci Resolve. It lets you immediately move your shots into the Media Pool or a Photo Album for editing, client review, or simply to view your image at higher resolution on a bigger screen.

### Setting up Camera Tethering

To begin, you'll have to set up Camera Tethering on the camera itself. Every camera make and model handles this differently, so do consult your camera's manual for the specifics. After that, connect the camera to your DaVinci Resolve Workstation with a USB cable. Lastly, a little additional configuration may be required on your local computer: BETA NOTES For this Beta release, tethered live capture works at present with Canon and Sony cameras alone.

- macOS: Both Canon and Sony cameras are supported natively.
- Windows: Canon cameras are supported natively. Sony cameras are supported,

but require additional software to be installed: https://creatorscloud.sony.net/catalog/en-us/ ie-desktop/index.html

- Linux: Tethering is not supported.
- iPad: Tethering is not supported.

Should your camera give you trouble connecting to DaVinci Resolve, here are a few troubleshooting pointers:

- Confirm that no other software, such as photo editing applications, is open and

grabbing the camera connection on its own.

- On occasion, restarting DaVinci Resolve may be needed before it will connect to your camera.

Once your camera and computer system are configured, hitting the Capture tab links to your camera on its own, and hitting the Capture Live View icon atop the viewer brings you into the Capture Live View interface.

### Capture Live View
