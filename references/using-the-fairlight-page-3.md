# Using The Fairlight Page (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Bins: Plain bins that you fill by hand. Drop whatever you wish into a bin and there it stays, right up until you choose to shift it into a different bin. Bins can be arranged in a hierarchy, so feel free to nest one bin within another. Making a fresh bin is just a matter of right-clicking inside the bin list and picking Add Bin off the contextual menu.
- Power Bins: Tucked away by default. Power bins are common to every project in your current project library, which makes them a natural home for assets you reuse — shared title generators, then graphics movies plus stills, alongside sound effects library files, music files, and any other media you'd like to reach fast from any project. Whatever materials you drop into Power Bins go there by hand; it's a manual process. To start a new Power Bin, reveal the Power Bins region of the Bin list, then right-click inside it and pick Add Bin.
- Smart Bins: These bins assemble “custom collections” of media, leaning on metadata or analysis to fill themselves dynamically, so their contents shift according to whatever the Smart Bin is told to watch for. A sound effects Smart Bin, say, surfaces only sound effects, and that bin's contents swell or shrink with however many effects files the project has spotted, a figure that can move over time. Smart Bins make organizing a project's contents quick and tidy.

A handful of Smart Bin types get built automatically (look under Preferences > User> Editing > Automatic Smart Bins). You can let Resolve's Audio Classification analysis sort your files into categories (which builds “Collections” smart bins on its own). Alternatively, add metadata to your clips by hand through the Metadata Editor — Scene, Shot, and Take details, keywords, comments and description text, and so on — to speed up finding what you need later. You're also free to define your own rules for a Smart Bin. To build a new custom Smart Bin, confirm the Smart Bin region of the Bin list is on screen, then right-click inside it and pick Add Smart Bin. A dialog opens where you set that bin's name and the rules it applies to filter clips, after which you click Create Smart Bin.

NOTE: To see Smart Bins beyond Keywords and Collections, you first have to switch on any extra Smart Bin options under Smart Bin Preferences > User > Editing > Automatic Smart Bins.

### Showing Bins in Separate Windows

Right-click a bin in the Bin list and you can pick “Open As New Window” to pop that bin out into a window of its own. Every such window is a Media Pool in its own right, carrying its own Bin list, its own Power Bins and Smart Bins lists, and its own display controls. That comes in most handy with two displays hooked up to your workstation, since you can drag these separated bins onto the second display while DaVinci Resolve runs in single screen mode. Hiding the Bin list both frees up room for clips and stops you from switching bins by accident when you mean to view only one bin's contents in that window. You can keep open as many extra Bin windows as you like, on top of the main Media Pool docked in the primary window interface.

### Filtering Bins Using Color Tags

On a project loaded with bins, you can mark out specific ones using any of eight colors: right-click a bin and pick the color you want out of the Color Tag submenu. For instance, mark the bins holding the clips you reach for most with a red tag. From then on a bin's color tag shows up as a colored field behind that bin's name. After you've tagged one or more Media Pool bins, the Color Tag Filter dropdown menu (the dropdown control sitting to the right of the Bin List button) lets you hide every bin but one color. To return to seeing all the bins, pick Show All from the Color Tag Filter dropdown.

### Using color tags to identify bins

Using Color Tag filtering to isolate the red bins

### Sorting the Bin List

You can order the Media Pool's Bin list (along with the Smart Bin list) by Bin Name, Date Created, or Date Modified, going up or down. Just right-click anywhere inside the Bin list and pick what you want from the Sort by submenu of the contextual menu. That same contextual menu also offers User Sort, which lets you drag every bin in the Bin list by hand into whatever order suits you. While you drag bins this way, a red line marks where the bin will land on release. Once you've used User Sort in the Bin list to arrange your bins by hand, you can flip freely between any of the other sort methods (Name, Date Created, Date Modified) and User Sort. Your hand-set User Sort order is kept, so it's easy to switch to whichever sort method serves you best at the moment without giving up your custom bin arrangement.

Moving a bin to a fresh spot within the Bin list while User Sort mode is active

### Filtering Clips With Audio in the Fairlight Page

On the Cut, Edit, Color, Fusion and Fairlight pages, the Media Pool can surface Audio Only clips through the Collections smart bin named “Audio Only,” which lives in the Collections area of Smart Bins. That makes it simple to track down the audio clips you're after when they're buried among a heap of video clips in the same bin.

### Sort mode

### The Audio Only Smart Bin

The Media Pool filter options in the option menu

Should you want a few extra options, the Media Pool on the Fairlight page can also screen out audio-only clips, or video clips that carry audio, within whichever bin is selected. To do this, click the Media Pool's Option menu and pick from its choices: Show All Clips, then Show Audio Only Clips, or else Show Clips With Audio, plus Show Audio Waveforms, along with Show Non-Rectified Audio Waveforms.

### Effects Library

The Fairlight page's Effects Library lists both the built-in Fairlight FX audio plugins that ship with DaVinci Resolve on macOS, Windows, and Linux, as well as whichever Audio FX happen to live on your workstation.

- Fairlight FX are built-in audio processing effects that run cross-platform across every platform DaVinci Resolve supports.
- Under macOS and Windows, third-party VST audio plugins are supported by DaVinci Resolve.
- On macOS, DaVinci Resolve supports Audio Unit (AU) audio plugins.

After you install third-party effects on your workstation, they show up in this Effects Library panel next to the Fairlight FX that are always on hand. With audio plugins you can drop effects onto audio clips, or run one as a real-time process across a whole audio track (touching every clip on it), to apply basic dynamics, or tonal work like compression, limiting or EQ and noise reduction, or else inventive spatial effects such as delay or reverb.

### The Effects Library

Much like the Media Pool, you open or close the Effects Library's Bin list with a button up at the top left.

### Effects Library Favorites

To mark an effect as a Favorite:

- Move the pointer over the far right of any effect until a star shows up
- Click that star to drop the effect into the Favorites effects list.
- Favorites turn up in their own region at the lower left, beside the Effects Library Bin list.

Stars indicate a flagged favorite effect, all favorites are currently filtered NOTE: Whatever you flag as Favorites in the Effects Library list also rises to the top of the Mixer's Effects dropdown menu effects list.

### ADR

DaVinci Resolve's Fairlight page carries a refined yet approachable interface for “ADR” (Automated Dialog Replacement) work. Thorough cue list handling, industry-standard audio beeps and visual cues, plus refined take handling with star ratings and layered take grouping all help you stay on top of your work while pulling the best moments from each performance. Once open, the ADR interface presents, just left of the Timeline, a trio of panels: a List panel, then a Record panel, and finally a Setup panel.

### The List Panel

Here is where you assemble a list of the cues you need to re-record, whether you build it inside the Fairlight page or bring it in from a .csv file someone hands you. It offers controls for adding, editing, importing, and exporting the cues you mean to record.

### The List panel of the ADR interface

### The Record Panel

Here is where you actually carry out the ADR recording session you've prepared, working from the dialog cues you placed in the Cue list. It offers controls for showing and choosing which cues to record, for previewing and kicking off recording, and for attaching metadata to rate the various takes you've captured and to track which cues are done.

### The Record panel of the ADR Interface

### The Setup Panel

The Setup panel is where your ADR session gets configured. Pick your audio input, your record track, and the tracks to monitor. Then reach the beeps, video streamers, and onscreen text the actors will watch on the video output display to help keep their performance on time.

### The Setup panel of the ADR interface

For more on working with the ADR panel, refer to Chapter 174, “ADR (Automated Dialog Replacement).”

### Sound Library Browser

You reach a Sound Library panel from the Interface toolbar to browse the sound effects libraries you have at hand, whether on your own system or on network storage you're attached to (a SAN, for one). It can scan file paths you specify to catalog the sound files it finds along with their metadata, tucking that data into the currently chosen project library (or any other project library you point it at) for later use when you go hunting your library for the right sound effect. Once your sound effects collection is cataloged, searching for sounds, previewing the hits in the list, and cutting your favorite into the Timeline all come easily. TIP: You can grab the Fairlight sound library — a royalty-free set of over 500 professionally recorded foley sounds free for your own projects — straight from the Sound Library panel. The Fairlight sound library spans everything from atmospheric ambient beds to foley such as foot steps, hits, effects, and the like. This free sound library is built to pair with the Fairlight FX Foley Sampler plugin, which lets a MIDI keyboard trigger sounds so they land at exactly the right instant in your program.

### The Sound Library panel

### Library Controls

Clicking the Library button (to the right of the Search field) brings up a menu where you pick which project library handles searching (and cataloging) of sound effects collections. Every network project library can hold its own catalog. NOTE: The Sound Library results pane stays empty until you run a search. The Sound Library can lean on the Mapped Mount option in the Preferences' Media Storage panel to reach sound effects sitting on remote volumes run by other operating systems.

### Choosing a library to search

To catalog every audio file inside a given file path so the Sound Library can search them: 1 With the Project Manager, build an empty network project library to hold the sound effects catalog. 2 Open a project, go to either the Edit or the Fairlight page, and then bring up the Sound Library. 3 (Optional) Press the Library button (sitting to the right of the Search field), then choose the project library you built from the dropdown menu that appears. By default the current project library is chosen. When you're inside a local project library instead, the highest compatible project library on the list becomes the default. 4 Do one of these: a) When no library of sound effects is connected yet, an Add Library button shows in the middle of the Sound Library. Click it, and from the file dialog that opens, choose the top-most directory of a file path holding sound effects; pick a directory with subdirectories inside and each one gets checked for content. b) When you're adding more sound effects to a library that already exists, click the Option menu and pick Add Library. From the file dialog that opens, choose the top-most directory of a file path holding sound effects; pick a directory with subdirectories inside and each one gets checked for content. 5 Click Open. A progress bar reports how long the job will run. Once it's done, a dialog tells you how many clips landed in the current library.

### Display Controls and the Search Field

The Sound Library title bar carries controls for ordering the sound effects list, for showing it in List or Icon view, and an Option menu holding assorted other settings and commands.

Display controls give you a say in how the Sound Effects list's contents get shown

Below that, a text field takes your search terms, while a dropdown menu off to the right lets you decide whether to comb the current project library for sound effects by name, by description metadata, or by all.

### The Search field and Filter By menu

To hunt down a particular sound effect and cut it into the Timeline:

- Enter a search term in the Search field. Letter case in your terms is disregarded, save for boolean operators.

To help you weed out false positives, the search field copes with a range of search styles: literal searches, then and/or/not boolean searches, plus wildcard searches, as well as character ranges. NOTE: For Boolean searches, the Boolean operators have to be typed entirely in upper caps, as in “AND,” “OR” and “NOT.” Type them lower case and “and,” “or” and “not” count as plain search words instead.

### Or/And/Not Searches

Just typing words split by spaces runs as a string of OR searches, each word looked for on its own, whether as a standalone or buried inside another word. For instance, type either of these: car door car OR door and you get the same hits. Every sound effect in your library that holds the letters “car” or “door” (or both) turns up, regardless of whether those letters stand alone or sit inside other words. Hits will take in files like “CarExDoorClose,” “Doormouse_Squeak,” “Carburetor dropped on cement,” and “Carpet Shake.” AND (which has to be upper caps) lets you stack multiple criteria onto a search, so each returned file must hold every word you type somewhere inside, in whatever order. For instance, type: car AND door and every sound effect in your library carrying both the strings “car” and “door” shows, whether those words appear alone, together, or tucked within other words, like “NewCarDoorSlam” and “Carpet_Footsteps_Indoors,” and “GarageDoorHitsCar.” NOT lets you drop sound effects that hold a given word. For instance, type: car NOT door and only sound effects with “car” surface, while every sound effect with “door” is dropped.

### Literal Searches

Quotation marks call for a literal search of just the named term, set off from surrounding text by a space. For instance, type: “cat” and every sound effect in your library carrying the lone word “cat” shows up. Sound effects with “cats” and “caterpillar” drop out. Hits will take in “Space cat drone” or “Cat meowing.” Wildcard and Range Searches The _ (asterisk) calls for a wildcard search across any number of characters. Drop an _ between two search terms and it finds any sound effect where those two terms are joined by any number or mix of characters with no spaces (even none at all). For instance, type: close*door and the hits cover “Door-Wood Cheap-Wooden-Closet-Door-Kick-In-Flimsy-Rattle,” as well as “ElevatorCabinCloseDoor,” plus “LatchSwingCloseSqueakDoorSecur.” Type instead: door*close and the hits take in “DoorHvyMetalCloseSlam,” “DoorLidWoodenChestCloseAntique,” and “ElevatorDoorCloseSlam.” Type instead: c\*r and the hits take in “lectrohummin,” “KiaShumaEXTBootCloseTrunkaka,” and “Ambience with Piana, Louder.” The ? (question mark) calls for a wildcard search of just one character. However many question marks you type sets how many wildcard characters get matched. For instance, type: door?close and you may turn up nothing at all, unless a sound effect named “door-close” exists. Yet type: door????close and the hits take in “DoorWoodClose,” since wood runs four letters, matching the count of wildcard letters you set. TIP: Typing “\*\*\*” surfaces every file in your Sound Library

### Preview and Audition Controls

Choose an item in the Sound Effect list and it loads into the preview player, where the controls beneath the search field let you play it or audition it in your timeline.

- Clip name: The name of the clip you've got selected right now.
- Next/Previous buttons: A pair of buttons that step you to the next or previous sound effect clip in the

Sound Effect list.

- Duration display: Reports how long the current clip runs, or how long the stretch marked off with

In and Out points runs.

- Playhead timecode display: Where the playhead sits right now.
- Waveform overview display: Here the whole sound effect's waveform appears, giving you a

pulled-back look at the selected clip. Every channel is summed together in this view.

- Zoomed in waveform display: A magnified slice of the selected clip that reveals finer waveform detail for placing In, Out, and Sync points.
- Jog bar: Lets you move through or scrub across the clip.
- Transport controls: Play, stop and loop buttons hand you command of playback, though you can equally

reach for the space bar and JKL controls. Right-click the Stop button to flip it into “Stop and Go to Last Position” mode.

- Marking controls: The Sync Point button lets you flag a particular frame on the sound effect that you want lined up with the Timeline's current playhead spot when you reach for the Audition controls. The In and Out buttons let you flag which stretches of the sound effect clip you mean to cut into the Timeline.
- Audition controls: The Audition button drops you into Audition mode, where the sound effect clip you've got selected is set down automatically at the playhead's spot on whichever Timeline track is active. You can then head over to the timeline and hear the clip within your mix. Cancel and Confirm buttons let you decide whether to pull the clip out of the Timeline and try another one, or keep the sound effect clip where it is.

To audition clips you've picked in the Sound Library against the Timeline: 1 Pick a sound effect clip you've found in the list that you'd like to audition in the Timeline. 2 (Optional) Within the Sound Library, slide the scrubber bar so the playhead reaches whichever part of the sound effect you'd sync to, then click the Sync Point button to drop a sync mark on that clip. Say you're syncing the sound of a car door closing — you might line up the first frame of the door fully shut with the peak of the “slam,” rather than any earlier door squeak in the sound effect. 3 (Optional) Set In and Out points to mark off the stretch of the sound effect you might use. 4 Pick a track to preview the sound effect on by clicking its track header or Mixer channel strip. 5 Park the playhead at the spot in the Timeline where the clip should go. 6 Click the Audition button in the Sound Library. The clip now shows up, for the moment, in the Timeline, and you can play that part of the Timeline to judge how the sound effect sits alongside the rest of the mix. 7 If the sound effect works, click Confirm to keep it in the Timeline. If it doesn't, click Cancel and it leaves the Timeline.

NOTE: Before the Audition function will run, a track must be selected first. On top of that, picking another sound effect after an audition without first confirming the prior one cancels the Audition process, and the prior sound is pulled from the timeline.

### Sound Effect List

Every sound effect clip matching the current search criteria turns up in this scrollable list. Double-click anywhere on a list item to play that sound effect from start to finish.

- Clip Name: The name that sound effect file carries in the storage system.
- Description: Whatever metadata sits embedded inside the files of professionally produced sound effect

libraries shows up here.

- Duration: How long that sound effect file runs.
- Audio Channel: How many channels that sound effect file holds.
- Star Rating: A clickable control for rating sound effects inside DaVinci Resolve.

Star rating data isn't stored anywhere outside of DaVinci Resolve.

- Waveform: The full sound effect library's overall waveform is stretched or squeezed

to fit the width the Sound Library has on hand, no matter the true length of each clip.

### Index

The Index hands you a convenient interface for listing every clip in the current edit, every track in the current Timeline, and every marker in the current Timeline. Through these lists you can select several items at once, manage tracks, and check marker notes with ease. Each of the three information categories sits in its own panel: the Edit Index, Tracks, and Markers.

### Edit Index

Shows the Edit Index just as it looks on the Edit page. Each audio clip in the open Timeline gets its own Edit Index row, whose columns cover video track, Source In and Out, Record In and Out, Name, plus further descriptive metadata. Any selected clip (those grabbed automatically for crossing the playhead among them) shows as selected over in the Edit Index. Through the Option menu you can screen the Edit Index along various lines — say, showing only clips bearing a certain flag, marker, or color, only clips carrying speed effects, only clips with audio filters, or compound audio clips.

In the Tracks panel, every track in the Timeline gets its own row of information

### Tracks

Every track in the open Timeline lines up with a row of controls and information in this panel. Reading left to right, a track offers a color control, then a visibility control, plus a number, a name, its track controls, a format, ADC, Tags, and — where a VCA is at work — that VCA group's number. These controls let you hide or reveal tracks, color-code them, rename them, switch track controls on singly or by dragging over several, alter their format, place them onto (or take them off) the audio monitor list, and shuffle their order by dragging one or several rows up or down the list, plus flip the automatic delay compensation (ADC) on or off (on by default).

Within the Tracks panel, each Timeline track is represented by one row of information.

NOTE: The ADC column (automatic delay compensation) carries a check box that lets you switch ADC on track by track.

### Audio Monitor Checkbox

A monitor checkbox shows up next to each bus or track in the Tracks list. Check it and that track or bus joins the Audio Monitoring dropdown menu as a monitoring choice. Every bus is checked on by default and appears in the list unless you uncheck it here.

### MPEG-H Options in the Tracks Panel

When MPEG-H is switched on for immersive audio authoring in the Video and Audio I/O preference pane, extra columns appear in this panel. Among those columns are:

- Track Type: Lets you define either a static component or a dynamic object. Choose dynamic and that track's dynamic track-level pan automation gets exported as well. Only a track can be set to dynamic.
- Kind: A content type label — Mixed content, Music, Dialogue, Effect, and so on. Once Kind is set for a bus (instead of the default Undefined state), that bus is bounced automatically through the export process.

With MPEG-H switched on, the Tracks panel surfaces extra columns of metadata for defining each track in the Timeline.
