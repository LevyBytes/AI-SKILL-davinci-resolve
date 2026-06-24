# Color Page Timeline And Lightbox (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

When the supplied preset filters fall short, you're free to build your own custom Smart Filter that pulls clips out based on whatever intrinsic or user-entered metadata is on hand in the Metadata Editor, Media Pool, and Color page timeline. Smart Filters behave a lot like Smart Bins, and the same steps create and edit them. To dig deeper into how Smart Bins work, turn to Chapter 18, “Adding and Organizing Media with the Media Pool.” Smart Filters can in fact grow quite elaborate, letting you sort the Thumbnail timeline by several criteria at once and even by several groups of several criteria, useful when you need clips that satisfy every member of one criteria set yet only a single member of another. This lets you craft Smart Filters that address an enormous range of workflow needs while you operate inside the Color page. Worth stressing, though: while every clip in DaVinci Resolve already carries plenty of intrinsic metadata (clip properties such as frame rate, frame size, codec, file name, and the like), the more effort you put into adding extra metadata through the Metadata Editor to ready your project for editing and grading (say, logging scene and take details along with keywords covering such things as character names, day versus night, interior versus exterior, framing, and the rest), the more potent Smart Filters become at helping you sift and sort through a program you're grading. Picture filtering out every closeup tied to one particular person across a program, or rounding up all the establishing shots that go with a given location. Should you or an assistant invest the time to enter metadata on a project's source material flagging these traits, you'll move that much faster to pair shots and locate the clips a given situation calls for. To create a Smart Filter: 1 Over at the top right of the DaVinci Resolve UI, just past the Clips button, click the Timeline Filtering drop-down button, then pick Create Smart Filter. 2 Within the Create Smart Filter dialog, type a name for it and lean on the controls below to set up one or more filter criteria (there's no cap on how many filter criteria you add):

### The Create Smart Filter dialog

- Show in all projects checkbox: Lets you build a lasting smart filter that turns up across every project in your project library. Filters made this way land in the User Smart filters section within each project's Clips button on the Color page. Match options: When filtering on multiple criteria, picking All requires that each criterion you list be satisfied before a clip is filtered. Any means a clip gets filtered the moment just one of several criteria is satisfied. Filter criteria enable checkbox: Lets you switch any criteria on or off without deleting it.

Metadata category drop-down: Lets you pick which metadata category a criteria is drawn from. This drop-down menu offers every metadata category found in the Metadata Editor. On top of that, Color Timeline Properties (holding many properties exclusive to the Color page timeline) and Media Pool Properties (holding every column in the Media Pool) open up further metadata you can filter on. Metadata type drop-down: For selecting precisely which metadata type to apply, from the choices the chosen metadata category offers. Metadata criteria drop-down: Lets you set the criteria used to filter, which varies with the metadata you've picked. Choices span “true/false,” ranges of integers, ranges of dates, searches over strings, flag and marker colors, plus more. Add filter criteria button: Use it to append further criteria and build multi-criteria filters. You might, for instance, combine criteria to track down all clips from Scene 2, that also carry the keyword “Diana,” that also hold the keyword “CU,” thereby surfacing every Scene 2 close-up of Diana. What's more, Option-clicking this button inserts a nested match option so you can construct even richer filters where the filter has to satisfy all of one criteria set and any of another. An elaborate Smart Filter carrying several criteria plus an added match option setting While you tweak the filter criteria, the Thumbnail timeline refreshes on its own to show how the Smart Filter you're building behaves. 3 Once the filter criteria are set the way you want, click Create Smart Filter. Your new Smart Filter shows up at the foot of the Filter drop-down menu and is enabled by default.

### Submenus available for modifying Smart Filters

Methods of modifying existing Smart Filters:

- To rename a Smart Filter: Open the Timeline Filtering drop-down, pick the filter you're after from the Rename Smart Filter submenu, retype its name in the Smart Filter Name dialog, and click OK.
- To edit a Smart Filter: Open the Timeline Filtering drop-down, pick the filter you're after from the Edit Smart Filter submenu, adjust its filter criteria, and click OK.
- To delete a Smart Filter: Open the Timeline Filtering drop-down and pick the filter you're after from the Delete Smart Filter submenu, which removes it at once.

### Using the Lightbox

Through the Lightbox you view every Timeline clip as a thumbnail grid laid out in rows running left to right and top to bottom. That makes it fast to assess, compare, and hunt for clips as you build selections, form groups, flag clips, or scan for a certain scene or a single clip.

The Color page Lightbox puts all the Timeline's clips on display. Along the Lightbox's right edge runs a vertical Timeline Ruler that tells you the timecode at the start of each clip row. Up in the top right a Zoom slider lets you resize the thumbnails. Choosing a clip inside the Lightbox amounts to choosing that clip in the Timeline, and right-clicking a Lightbox clip pops the very contextual menu items you'd get from right-clicking the clip in the Timeline. Beyond that, you can grade the active clip right in the Lightbox with a control panel, or by bringing up the color controls to grade it via a mouse or another input device.

Methods of using the Lightbox:

- To show or hide the Lightbox: In the toolbar, click the Lightbox button.
- To show color controls in the Lightbox: Within the UI control bar sitting above the Lightbox, click the Show Color Controls button.

The Color Controls button, with the sidebar and Thumbnail Info buttons below

- To show thumbnail info in the Lightbox: Toggle each clip's thumbnail Info on or off by clicking the Clip Info button, the second control found at the Lightbox's upper left-hand corner.
- To resize clips in the Lightbox: Push the Zoom slider rightward to enlarge thumbnails, or leftward to shrink them.

The Lightbox button, Zoom slider, and Monitor Output buttons You can filter what the Lightbox holds with the same options offered for filtering the Thumbnail timeline. To filter the Lightbox:

- At the Lightbox's upper left-hand corner, click the Show sidebar button. Doing so exposes every filtering option the Lightbox offers, custom Smart Filters you've made included.
- Pick one of the choices listed in the sidebar. The Lightbox refreshes right away to display only the clips meeting your chosen criteria.
- Click All Clips whenever you want to return to viewing the whole Timeline. The Lightbox's contents can additionally be sent out to video so you can review them on a broadcast display or projector.

To output the contents of the Lightbox to video: At the Lightbox's upper right-hand corner, click the Output Lightbox to Video button.

### The button for outputting the Lightbox to video

To read further on clip selections, groups, and grade management, consult Chapter 142, “Grade Management.”

The Lightbox sidebar, with controls for filtering the Lightbox
