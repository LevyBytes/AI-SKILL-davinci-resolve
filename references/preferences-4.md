# Preferences (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Much like the ordinary viewer options that apply to 3D comps, these preferences govern the way a 3D comp shows up inside a VR headset.

### Light

- Disabled lighting is off.
- Auto will detect if lighting is on in the view.
- On will force lighting on in the VR view.

### Sort Method

- Z buffer sorting is OpenGL's quick approach to ordering polygons.
- Quick Sort orders polygon depth so transparency renders more cleanly.
- Full Sort applies a sturdy sort-and-render approach to draw transparency .
- Shadows can be on or off.
- Show Matte Objects toggles matte objects between visible and hidden in the view.

### Bins/Security

You'll only find Bins preferences inside Fusion Studio. They serve to administer the Bin users along with their permissions.

### The Bins Security preferences

### Users List

Each user and the permissions they hold are enumerated in the Users List. Pick any entry to revise its settings through the User and Password edit boxes.

- Add: Pressing the Add button registers a fresh user on the list once you supply a username and password.
- Remove: Click this button to remove the selected entry.

### User

For whichever Bin Server item is selected, this editable field displays its username. When the username isn't known, give “Guest” a try with no password.

### Password

Type into this field the password belonging to the Bin user listed in the Users list.

### Permissions

Distinct permission types can be assigned to users by the administrator.

- Read: Grants the user read-only access to the bins.
- Create: Lets the user make new bins.
- Admin: Hands the user complete authority over the bins system.
- Modify: Permits the user to alter bins that already exist.
- Delete: Lets the user take bins away.

### Bins/Server

Through these preferences you register Bin Servers on the roster of bins Fusion shows in the Bins dialog.

### The Bin Servers preferences

### Servers

Whatever servers currently sit in the connection list are shown by this dialog. Pick any entry to revise its settings.

- Add: Use this button to add a new server to the list.
- Remove: Click this button to remove the selected entry.

### Server

This editable field reports the name or IP address belonging to the server of the chosen list entry.

### User

The username tied to the selected Bin Server item appears in this editable dialog.

### Password

Type into this field the password for whichever server you listed in the Server list.

### Library

Naming the bins is handled through the Library field. To set up a bin per individual project, give it a name in the Library field and every project receives a bin of its own.

### Application

Through the Application field, bigger studios can nominate some other program to handle serving out the Bin requests.

### Bins/Settings

The default conduct of bins is governed by these preferences.

### The Bins Settings preferences

### Stamp Quality

A percentage slider, Stamp Quality fixes the compression ratio applied when Stamp thumbnails are made. Raising it improves quality at the cost of more storage.

### Stamp Format

Whether Stamp thumbnails get stored compressed or uncompressed is decided by this drop-down list.

### Options

- Open Bins on Startup: With Open Bins on Startup ticked, the bins spring open on their own the moment Fusion starts up.
- Checker Underlay: Switching on the Checker Underlay puts a checkerboard backdrop behind clips that carry alpha channels. Turn it off and a gray backdrop matching the Bin window stands in as the clip's background.

### EDL Import

The way compositions get built out of imported CMX‑formatted EDL files is dictated by the EDL Import options.

### The EDL Import preferences

### Flow Format

Three choices in this drop-down menu govern how the node tree gets assembled for the EDL file you've imported.

- Loader Per Clip: Every clip within the EDL file gets its own Loader.
- A-B Roll: A Dissolve tool is dropped into an automatically built node tree.
- Loader Per Transition: One Loader carrying a Clip list stands in for the imported EDL list.

### Use Shot Names

With this ticked, the shot names held in the EDL file serve to track down the footage.

### Customization

What this section addresses is customizing preferences that don't strictly belong to the Preferences window. By way of Fusion Studio's Hotkey Manager window you can tailor the keyboard shortcuts, which speeds up working in Fusion overall and can make it feel more familiar should you be coming over from a different software application. Fusion also accepts environment variables for swapping among different preferences files, so you can keep distinct working setups tied to different users or job types. Neither of these customization avenues exists outside Fusion Studio.

### Shortcuts Customization

Within Fusion Studio you're able to tailor keyboard shortcuts. Reach the Hotkey Manager by picking Customize HotKeys from the View menu.

### The Hotkey Manager

To draw your attention to certain interface regions, Fusion marks them as active windows, among them the Node Editor, the viewers, and the Inspector. Whichever one is selected gets framed by a gray border line. A region's shortcuts respond only while that region is active. As an illustration, Command-F in the View scales the image so it fits the view area; over in the Flow view, Command-F brings up the Find tool dialog; and inside the Spline editor it fits the splines to the window.

Off to the right sits a hierarchy tree covering every section of Fusion together with a roster of the hotkeys set so far. Selecting New or Edit raises a further dialog that hands you precise control over that hotkey.

### The Hotkey Editor

Making a new keyframe captures the key combo you press, after which this Edit Hotkey dialog opens, letting you define the Action at the top right as pressed, repeated, or released. You can set the Name and the abbreviated Short Name, and likewise the Arguments of the action.

### Customizing Preferences

The preferences in Fusion Studio set Fusion's general application defaults along with the settings carried by each new composition. You reach and adjust them via the Preferences window, yet Fusion stores them in a plain text format named Fusion.prefs. Sitting in a \Profiles\Default folder, these default preferences are shared by everyone using Fusion on the machine. You may, however, want each user to keep their own preferences and settings, which means writing the preferences to different spots according to a user login. Altering where the preferences file gets saved calls for environment variables.

### Setting the Preferences Location

The first time you open Fusion, the environment variable FUSION_PROFILE_DIR names the folder holding the Profiles folder. Should that variable point to a valid path, the preferences land in that folder. If FUSION_PROFILE_DIR isn't there, Fusion tries to make it. Failing to create the path, it falls back to keeping the preferences in the default Path Map location: AllData:\Profiles. As a rule, every user shares one set of preferences. To have each user keep separate preferences in their home folder, you'll need a second environment variable named FUSION_PROFILE (e.g., FUSION_PROFILE=jane). Armed with this second environment variable, Fusion hunts for the preferences in the PROFILE_DIR of that user profile. A login script lets you guarantee FUSION_PROFILE matches the name of whoever is logged in.

### Creating a Master Preferences File

Running a studio with several Fusion users may have you wanting to standardize a handful of settings. The FUSION_MasterPrefs environment variable lets you set up one or more site-wide preferences on top of your own local personal preferences. FUSION_MasterPrefs has to carry the full path to at least one preferences file. Where several preferences paths exist, divide them with semicolons. Fusion never writes back to these prefs files, and they may hold only a subset of every available setting. You're free to edit settings inside these files, and they take effect only where local prefs are absent unless the Locked flag is set.

### Locking Preferences

Should the line “Locked = true,” show up in a master file's main table, every setting in that file becomes locked and trumps any other preferences. The user cannot change locked preferences.
