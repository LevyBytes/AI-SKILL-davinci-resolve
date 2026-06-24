# Setting Up Tracks Busses And Patching (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Setting Up Tracks, Busses, and Patching

Among the earliest tasks when preparing a fresh project for mixing on the Fairlight page is establishing the audio tracks and busses required to route and merge the parts of your mix. This chapter walks through creating audio tracks and using busses to manage a mix as efficiently as possible. That said, the Fairlight page lets you add to or revise your setup whenever you like, so you can stay focused on the creative side and handle any necessary housekeeping as the mix develops. The FlexBus structure in Fairlight permits bus-to-bus, track-to-bus, or bus-to-track signal routing and adds broader Dolby Atmos support, covering import, export, and manipulation of Atmos ADM files.

### Audio Tracks

On a DaVinci Resolve timeline, every audio track maps to one channel strip along the left edge of the Mixer. Based on the way the track was configured, it adopts a specific audio format — among them mono, stereo, 5.1 or 7.1 surround, and Dolby Atmos. Through the lanes shown inside each track on the Fairlight timeline, track routing ensures the assorted audio channels within a track’s clips land at the right audio output for both monitoring and rendering. Although audio tracks in DaVinci Resolve frequently hold several channels from one clip, how those individual channels appear varies by page:

- On the Cut and Edit pages, each audio track shows a single clip “lane” in the Timeline no matter how many channels its clips carry. The waveform you see is a composite that blends the clip’s assorted channels together.
- The upside is that multichannel tracks become easier to handle without the clutter of multiple channel lanes that would make things look much “busier.” The downside is that you lose sight of detailed activity occurring on any individual channel of that track.
- The Fairlight page shows the same track count as the Edit page, except that each Fairlight track is split into lanes exposing every separate channel of a clip’s audio. That extra visual detail can aid both editing and mixing.

(Top) On the Cut and Edit pages, the 6 channel and stereo audio appears as single composite tracks. (Bottom) On the Fairlight page, that same audio shows the six channel and stereo tracks split into multiple lanes, one matching each of the file types.

Having grasped how tracks behave on the Fairlight page, the next key idea to master before you can fully tap the page’s power is FlexBus, which gives you several ways to combine audio tracks.

### What Is a Bus?

In plain terms, a bus is a shared signal connection point within an audio mixer. A bus can be mono, stereo, or any wider format such as 5.1 or Dolby Atmos 9.1.6 (which carries 16 audio signals). The bussed connections are summed into one signal that you steer from a single bus channel strip. By default, for instance, one bus named “Bus 1” sums the levels of every clip on every track of a timeline into the combined signal routed to your speakers or headphones. Busses let you organize how a timeline’s tracks are mixed in inventive ways. Suppose five audio tracks hold all the edited dialogue clips for a given program — you can send the outputs of all five to a dedicated submix bus. That lets the pooled levels of every contributing dialogue track be processed, tweaked, and mixed together through one channel strip’s controls. You can also stack busses to structure a mix, routing submix busses into further “main busses.” Individual tracks feed submix busses, and several submixes can then feed one or more “main output” busses. For example, picture four submix busses — German dialogue, English dialogue, Music, and Effects. You might route the German, Music, and Effects submixes into a Main 1 bus to deliver the German edition, and the English, Music, and Effects submixes into a Main 2 bus to deliver the English-language edition.

### Surround Panning and Bussing

For surround or immersive work, audio tracks from the Timeline reach busses through each channel strip’s multi-format surround panner, so a bus can be set up to suit a specific audio format such as mono, stereo, LCRS, 5.1 surround, or 7.1 surround, as well as immersive formats like Atmos. Routing across multiple busses even lets you output several formats at the same time.

### Bus to Bus Routing and Mixing

The FlexBus structure in Fairlight grants full user freedom over bus types and signal routing, making bussing entirely user-definable and letting you patch outputs and/or sends in whatever manner your project demands. Each track can feed up to ten busses, plus sends with their own level and pan controls to ten more. Busses can cascade into other busses as many as six layers deep, which supports intricate stem building and processing and yields discrete deliverables. User-definable busses enable bus-to-bus, bus-to-track, or track-to-bus routing, with every bus capable of passing signals from mono all the way up to fully immersive formats such as Dolby Atmos. As with every track type in Fairlight, these bus types can be reassigned at any time when needed. The strength of the FlexBus system lies in letting you send signals to many destinations simultaneously, achieving elaborate mixing setups. Perhaps you need two mixes identical in content but differing in output level. You can set up two mix busses — one at an output level of -2dB true peak and one at -10dB true peak. The finished mix signal goes to one bus, which then splits into two more, one fitted with a limiter set to -2dB and the other to -10 dB, producing both versions at once.

Within the FlexBus structure, a wide assortment of bus track types can be created or reassigned.

### Using Legacy Fixed Bussing

If the older Fixed Bus mapping approach suits you better, you can turn it on for fresh projects: open the Fairlight panel within Project Settings and check the “Use fixed bus mapping” box. If a project already has Fixed Bussing turned on and you wish to switch to FlexBus, clear the “Use fixed bus mapping” checkbox. Be aware that after the switch, you won’t be allowed to revert to legacy bussing.

For more information see Chapter 177, “Mixing in the Fairlight Page.”

### Converting Older Fixed Bus Projects to FlexBus

To convert older Fixed Bus projects to FlexBus, follow these steps:

- Open Project Settings > Fairlight.
- Under the Bussing heading, uncheck “Use fixed bus mapping.”
- A dialog will appear allowing you to convert the project to FlexBus.

### Busses in Nested Timelines

When you place a timeline inside another timeline that already has busses configured for Fairlight mixing, every bus routing keeps functioning as intended inside the nested timeline, which surfaces all channels through the default main bus (Bus 1) within the enclosing timeline. From that angle, the nested timeline’s audio amounts to a submix whose resulting audio outputs to the audio track it was edited onto. You can alternatively decompose the nested timeline into its own bus structure inside the main timeline you imported it into, exposing all of the original tracks just as they were. That makes this a very powerful feature for combining work that was done at separate times or came from separate contributors — for more, consult Chapter 177, “Mixing in the Fairlight Page.” in section Nested Audio Timelines.

### Exposing Bus Tracks in the Timeline

Any bus can be surfaced as a track in the Timeline, which lets you see and edit the automation applied to that bus’s parameters. To show a bus in the Timeline: 1 Turn on the Toggle Automation button in the Fairlight toolbar. Every bus is shown by default. 2 To hide one, open the Index and click the eye button beside the bus you want hidden in the Timeline. 3 To work with automation on a bus, pick the automation curve you want to view from the dropdown in the track header controls.

### Controlling Signal Flow

A sound workflow for getting editing and mixing set up on the Fairlight page goes like this:

- Arrange and configure your timeline’s tracks as needed — for instance, tidy clips on tracks, set track types, color, grouping, and so on.
- Build the busses required to shape the mix’s desired signal flow.
- Send the audio tracks, or any submix busses, to the bus destinations the mix layout calls for.

### Defining Audio Track Types

When you create a new audio track, you must decide what kind it will be. Right-clicking in the lower audio portion of the Timeline track header brings up a contextual sub-menu offering the various audio track types you can create.

- Mono: Holds a single channel with only one lane.
- Stereo: Holds stereo left and right channels, with two lanes.
- 3.0: Carries three channels across three lanes, in either LRC (Left, Right, Center) or LCR

(Left, Center, Right) format.

- 4.0: Carries four channels across four lanes, in either LRCS (Left, Right, Center, Surround), LCRS (Left,

Center, Right, Surround), or Quad format.

- 5.x: A 5.0 track carries five channels for a 5.0 surround mix, spread over five lanes in total. Under the broadcast SMPTE layout the order is Left, Right, Center, Surround Left, and Surround Right; under the cinema layout (5.0 Film) the tracks run Left, Center, Right, Left Surround, and Right Surround.

A 5.1 track carries six channels for a 5.1 surround mix, spread over six lanes in total. Under the broadcast SMPTE layout the order is Left, Right, Center, LFE, Surround Left, and Surround Right; under the cinema layout (5.1 Film) the tracks run Left, Center, Right, Left Surround, Right Surround, and LFE.

- 7.x: A 7.0 track carries seven channels for a 7.0 surround mix, spread over seven lanes in total. The broadcast SMPTE layout orders them Left, then Right, then Center, then Left Surround, then Right Surround, then Back Left Surround, and finally Back Right Surround; the cinema layout (7.0 Film) instead orders them Left, then Center, then Right, then Left Surround, then Right Surround, then Back Surround Left, and finally Back Surround Right.

A 7.1 track carries eight channels for a 7.1 surround mix, spread over eight lanes in total. The broadcast SMPTE layout orders them Left, then Right, then Center, then LFE, then Left Surround, then Right Surround, then Back Left Surround, and finally Back Right Surround; the cinema layout (7.1 Film) instead orders them Left, then Center, then Right, then Left Surround, then Right Surround, then Back Surround Left, then Back Surround Right, and finally LFE.

- Adaptive: Holds up to 24 audio channels, each with its own lane inside the track. A single Adaptive track can carry clips with differing channel counts, up to the ceiling set for that track. You set that ceiling (1–24) yourself when the Adaptive track is created. If you edit a clip carrying more channels than the Adaptive track was made to hold, the surplus clip channels are muted.
- Dolby Atmos: Several Dolby Atmos formats are on offer: 5.1.2, 5.1.4, 7.1.2, 7.1.4, and 9.1.6. The naming of these channel configurations folds the height channels into the nomenclature. A configuration is written as three digits separated by periods, like 7.1.4. The first digit gives the count of main, or ear-height monitoring, channels encircling the listener. The second digit gives the count of subwoofer channels. The third digit gives the count of height channels — speakers placed on the ceiling, or, with a soundbar, aimed at it.

NOTE: The 9.1.4, 9.16, and 22.2 Dolby Atmos bus formats exist solely in DaVinci Resolve Studio, and on top of that they demand that Dolby Atmos first be switched on under Preferences > Video and Audio I/O > Immersive Audio.

Adding Tracks (Contextual Menu) The right-click contextual menu on any audio track’s header controls carries two track-adding commands:

- Add Track: Inserts one audio track of whatever type you pick from a submenu.
- Add Tracks: Lets you add as many tracks as you wish, specifying their type and where they sit

among the other tracks in the Timeline.

### Rearranging Tracks

You can reorder tracks by right-clicking inside a track’s header area and selecting either Move Track Up or Move Track Down from the contextual menu that opens. Tracks can also be moved within the Index by grabbing them and dragging them to where you want them. That second approach works for relocating several tracks at once.

### Duplicating Tracks

To duplicate a track, right-click its header and pick “Duplicate Track” from the contextual menu. You can duplicate several tracks at once by selecting them, right-clicking any of the group’s headers, and choosing “Duplicate Tracks” from the contextual menu. Duplicate tracks have the word “copy” appended to their names.

### Timeline contextual menu - Duplicate Tracks

### Duplicated tracks with appended names

### Deleting Tracks

Right-click within a track’s Timeline header and pick Delete Track. Any clips on a track you remove are deleted from the Timeline along with it, but they stay safe in the Media Pool. To remove a batch of tracks from the Fairlight timeline, right-click any of the selected headers and pick Delete Tracks from the contextual menu. To purge every empty audio track from that timeline, right-click any header and pick Delete Empty Tracks from the contextual menu.

### Timeline contextual menu - Delete Tracks

### Disabling Tracks

To disable an audio track, right-click its track header and select Disable Track from the contextual menu. To turn off several tracks at once, select them, right-click any header in the group, and choose Disable Tracks from the contextual menu.

### Timeline contextual menu - Disable Tracks

### Disabled tracks

To switch your tracks back on, run through one of the selection methods according to how many tracks are involved, then pick Disable Track or Disable Tracks from the contextual menu.

### Changing Track Type

If you set your timeline up with one type of audio track but later realize a different type is what you need, you can change it whenever you like. Just right-click anywhere within that track’s Timeline header and select a choice from the contextual menu’s Change Track Type To submenu.

### Link Grouping

The Link Group function lets you tie together related mono tracks of material and handle them as one entity driven by a single fader on a single channel strip. A link group can only be built from mono tracks; the other types — stereo, 5.1, 7.1, Atmos, or Adaptive — are ineligible. Where a multi-channel track uses lanes, a link group of mono tracks instead acts as separate, editable tracks in the Timeline. Even so, each track gets mapped when you pick a track type, following one of the usual multi-channel mappings (stereo, 5.1, 7.1, Adaptive). Link groups come in extremely handy — say, when you’ve received separate “.L/.R” halves of a stereo mix, or a batch of six related audio files that must be assembled into one 5.1 surround mix, or when surround channels must be re-edited one channel at a time. To create a Link Group from individual mono tracks: 1 Make two or more Mono audio tracks you’d like grouped together. If you want a link group with a specific channel mapping such as 5.1, be sure to create enough tracks (here, 6). 2 Choose Fairlight > Link Group. 3 Once the Link Group dialog opens, mono audio tracks show up as active buttons (every other track type is grayed out, since those can’t be linked). Click to enable the button for each track you want in the link group you’re building. Which track-type mappings are available for your group depends on how many tracks you selected.

Selecting six tracks to use for creating a link group 4 After all the required tracks are picked, press one of the “Link as” buttons shown below. In this case six tracks are chosen, so 5.1 Film or 5.1 would be valid clicks.

Selecting enough tracks lets you build groups linked as particular surround mappings.

After that, the tracks you chose should merge into a single block, signaling they’ve been linked.

The Link Group window displays the link indicator line beside the track names. Depending on how many mono channels you selected, Fairlight presents the possible linking options. For example, with ten channels selected, both Atmos 7.1.2 and 5.1.4 appear as choices.

The Link As option hinges on how many channels are being linked. 5 Close the Link Group window once you’re done. Once a link group is in place, one bar stretches down the headers’ left edge, covering the whole group. Provided the tracks are tall enough, every one carries a label showing its assigned channel per the track mapping you chose in step 4 — for a 5.1 surround mapping, say, L, R, C, LFE, Ls, Rs, and so on. You’re also free to edit extra or alternative contributing elements of a surround mix into whichever track stands for that channel.

Within a Link Group, each track is labeled so you can tell which one stands for which surround channel.

### Working Separately with Multichannel Audio File Elements

If you’ve edited a multichannel audio clip onto a multichannel track, that track and its contents can be converted into a Link Group of mono tracks, each holding a single clip for one of the track’s channels. This helps when you need to repair a multi-channel surround clip whose track mapping is wrong. Convert it into a Link Group, and you can then rearrange the channels with ease. Turning one multichannel timeline into a Link Group works like this: right-click the header of a multichannel audio track and select Convert to Linked Group from the contextual menu. Doing so immediately produces one fresh audio track for each channel, all bound together. Converting a 5.1 track, for example, gives six new tracks each carrying a separate audio clip (one per channel), all linked. Where required, a linked group can also be broken apart to bring back separate mono tracks. To unlink one: 1 Choose Fairlight > Link Group. 2 In the Link Group dialog that opens, pick the link group you wish to unlink. 3 Click Unlink. 4 Close the Link Group window when finished. SMPTE and Film order Standards The differences in how the multichannel files get routed stem from the path order of the SMPTE or Film standards. They are:

- 5.1 film order: L, C, R, Ls, Rs, LFE
- 5.1 SMPTE order: L, R, C, LFE, Ls, Rs
- 7.1 film order: L, C, R, Lss, Rss, Lsr, Rsr, LFE
- 7.1 SMPTE order: L, R, C, LFE, Lss, Rss, Lsr, Rsr

### Creating Busses

Picking Fairlight > Bus Format opens the Bus Format window, where you create the busses you need (within your system’s limits) to organize your program’s tracks and channels. The Bus list lets you rename a bus, set the format of each one (a dropdown shows up in the Format column of every list entry), reports how many channels a bus has, and lets you color-code each bus (a Color dropdown picks that bus’s color). Just click any item on the Bus list to select it and pick different choices from the Format and Color dropdowns, or click a bus’s Name to select it and type a custom name. Three buttons sit at the bottom of the list, letting you Add Bus, Duplicate, or Remove selected busses. When you’ve finished adjusting the available busses, click OK to keep the changes and close the Bus Format window, or Cancel to close it without applying anything (though all pre-existing busses stay put). The bottom button row additionally shows a Used tally of what’s in use and what remains available on your workstation.

### The depth of options in the FlexBus system

Immersive Formats (Studio Version Only) To enable the immersive formats, head to Preferences > Video and Audio I/O > System Panel > Immersive Audio and select from the appropriate options. Once turned on, the various immersive bus formats become available in the Bus Format panel’s Bus list.

From the Video and Audio I/O panel you can switch the Immersive Audio options on or off.

### Legacy Fixed Bussing

Working with the FlexBus topology is strongly advised for its flexibility, and some newer features only function under FlexBus. At some point, though, you might have to use legacy Fixed Bussing in a new project. To enable Fixed Bussing in a freshly created project, before adding any timeline, open Project Settings > Fairlight, and under the Bussing heading tick “Use fixed bus mapping.” From then on, all bussing runs through the legacy Fixed Bus topology.

### Bus formatting with Fixed Bus

The legacy Bus Format window carries four buttons for creating the various Fixed Bus types. Whenever you create a new bus — whether a Main, Sub, Aux, or Multi Track — it gets added to the list that shows beneath. The legacy Bus list behaves just like the FlexBus list, offering rename, format, color code, and so on, plus buttons to Duplicate or Remove selected busses. When you’ve finished adjusting the available busses, click OK to keep the changes and close the Bus Format window, or Cancel to close it (though any busses you made stay put). The bottom button row additionally shows a Used tally of what’s in use and what remains available on your workstation.

### Assigning Busses

After you’ve made one or more busses, you can route various tracks to specific busses, and likewise busses to busses, busses to tracks, and the final Main bus destinations.

### Bus Assignment Using the Mixer

Assigning your track(s) to any available bus is easy using the plus (“+”) icon on a Mixer channel strip:

- Pick a mixer channel, then click the plus (“+”) icon within either the Bus Output or Bus Sends section.
- From the dropdown menu, pick whichever destination you want.
- A rectangle bearing the bus’s name shows up, confirming the bus has been assigned.

### Bus routing dropdown menu on a channel strip

TIP: To rapidly route a bus to a chosen group of tracks — or to every track — hold a modifier before you carry out the action: the Option key (Mac) or the Alt key (Windows) covers all selected tracks, while Command‑Option (Mac) or Control-Alt (Windows) covers all mixer channel strips. Such shortcuts can shave plenty of time off your workflow.

### The Bus Assign Window

When there are plenty of busses or tracks to deal with, the Bus Assign window makes it simple to connect to all of them in one place. Choose Fairlight > Bus Assign to open the window. You can build several bus assignments inside the dialog, and those new assignments turn up in the Bus Outputs section on the Mixer’s channel strips. The top displays the Send and the Out of each available bus, while the bottom lists every available track and bus you can connect to. By default the Bus Assign window opens in List view, where each bus and track appears as a list, but the icon in the window’s upper right switches it to Icon view, where Available Tracks show up as buttons.

### Making Bus Assignments

Assigning Using List View Click a button in the Busses section to pick the Send or Out of that bus, then click any destination in the tracks/busses list below, or drag across a group of tracks or busses to assign them all. Once assigned, the bus number shows up in the Bus Sends or Bus Outputs column.
