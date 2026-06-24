# Immersive Audio Workflows (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Immersive Audio Workflows

DaVinci Resolve includes broad tooling for both object-based and channel-based surround and immersive audio formats. The pages that follow walk through configuring and mixing in these formats while you work in the Fairlight page.

### About Immersive Audio Formats

Surround formats rely on several audio channels to place sound sources at points around a listener, lending a creative spatial layer to sound design. The most basic of them — 5.1 and 7.1 surround, for example — let the mixer route differing levels of any track to a set of speakers, locating audio at various spots throughout an auditorium or living room: anchored up front, drifting in from behind, or leaning toward the listener's left or right. Richer immersive formats like Dolby Atmos™ or Ambisonics instead establish a virtual soundstage onto which you mix, with playback adapting to the speaker layout or listening rig in use.

### Dolby Atmos

Conventional surround sends sound to a defined group of monitoring channels, which calls for a set number of monitor speakers installed at specific spots in a room and can roughly locate audio within a ring surrounding the listener. Dolby Atmos advances on that approach as an objectbased sound system that works inside a 3D immersive space and supports a broader range of speaker layouts, with additional speakers arranged around the listener. The result is greater dimensionality and tighter sound placement, with height channels added so audio can arrive distinctly from overhead. For Dolby Atmos output, the render formats DaVinci Resolve handles run from 5.1.4 up to 9.1.6. You can hear how this differs in practice while panning a 7.1 mix: because you are routing signals to set points in a speaker array, those points stay fixed. Rooms vary in physical size, yet the mix always reaches those designated point speakers, which makes the experience uneven from one room to the next. Dolby Atmos, in contrast, lets re-recording mixers mix to an idealized space rather than to fixed speaker locations. So when a Dolby Atmos mix plays back in a Dolby Atmos room, it factors in the real dimensions of that room together with the count of speakers in use, recomputing playback to match the precise space and gear and thereby reproducing the mix far more faithfully, with much tighter placement of sound where that matters. As a concrete illustration of what Dolby Atmos offers, picture a modest theatre fitted with the usual left, center, and right front-screen speakers. Add to that four left surround and four right surround speakers, plus four overhead left and four overhead right. Suppose you have routed a sound to the surround left in Atmos and placed it roughly halfway between the screen and the back. Then relocate the Atmos mix into a far bigger room outfitted with double the monitor speakers. That larger theatre carries, on the surrounds, eight to the left and eight to the right, with eight overhead left and a matching eight overhead right. On playback in this revised layout, Atmos works out the proportions of the room against the new speaker array. So when the sound is replayed at the halfway point from the screen, Dolby Atmos derives the proportion of that sound relative to the new playback rig, letting the listener hear precisely what the re-recording mixer meant.

To stay with that illustration: to make the audio play back halfway to the screen in the small room, it sounds from the second surround speaker on the left side. When the identical audio plays in the bigger room, Atmos works out that the fourth surround speaker now sits halfway from the screen. What counts is not which speaker a sound is mapped to, but the spatial location where the sound ought to be perceived. Atmos derives the proportion between playback rooms and their monitor speakers so a mix reproduces faithfully, rather than tying sounds to one fixed speaker spot.

### Dolby Atmos Speaker Configurations

A key point is that the label Dolby Atmos does not denote any single fixed speaker arrangement. Dolby Atmos is an intricate metadata-driven system that reads the audio from a set-up Atmos mix, identifies the listener's playback rig, and recalculates the mix to suit each specific space and system. Given a Dolby Atmos compatible setup, a 7.1.4 Atmos mix played by someone with only a two channel rig will be intelligently folded down to stereo. Should a listener run a standard 5.1 monitor rig, that 7.1.4 Atmos track folds down to five channel surround plus a subwoofer. The way channel configurations are named in the Dolby Atmos format folds the height channels into the labeling. Configurations show as three digits split by periods — 7.1.4 being one common layout. The leading digit gives the count of main, or ear-height, monitoring channels ringing the listener. The middle digit gives the count of subwoofer channels. The final digit gives the count of height channels, which are speakers mounted on the ceiling or, with a soundbar, angled up at it.

An example of a 7.1.4 Atmos monitor speaker configuration:

- Seven surround channels
- Left
- Center
- Right
- Left Surround
- Right Surround
- Left Back Surround
- Left Right Surround
- One Subwoofer
- Four height channels

### Enabling Dolby Atmos

To switch Atmos on, open Preferences > Video and Audio I/O > Immersive Audio panel and turn on Enable Dolby Atmos. Once it is on, the Change Track Type contextual menu that appears when you rightclick a track gains the extra Atmos track types.

### The Components of a Dolby Atmos Mix

An Atmos mix is built from several distinctly named parts. Together they form an immersive mix, while each part lets the Dolby Atmos system tailor the sound to the room and speaker layout during playback.

They are made up of: The Bed track: Holds most of the mixed audio — dialog, ambient effects, and music. Audio of this kind carries panning data, but only in a broad sense. Wind, faraway traffic, room tones, and sync dialog would nearly always sit inside a typical bed track of 7.1.2 or 5.1. Object tracks: Lock down where sounds travel precisely across the immersive space. These dedicated tracks let users pan anywhere in the room. Sounds can soar through space, circle a room via height channels, and reach side and back channels, echoing how objects move onscreen. Object tracks draw on the Atmos metadata to run the calculations covered in the previous example. ADM files are Atmos exports paired with the IMF file type as master deliverables, stored in the broadcast wave file format. Users decide which tracks serve as Bed tracks and which serve as Object tracks; these track labels merely describe the intended use of the tracks you build. In the end the mixer decides which audio lives on Bed tracks and which lives on Object tracks. In principle a mix could be made up wholly of Object tracks, yet the usual split puts generally panned sounds into beds and reserves Object tracks for sounds needing exact room placement. Object tracks together with height channels unlock things that simply weren't achievable before Atmos. Picture a scene in which a man hides from Police as a helicopter circles above, or one where children in a basement freeze at the sound of heavy footsteps overhead. Atmos lets the audience share in these immersive sounds right alongside the characters. Those are real-world cases, but audio in animation, science fiction, and fantasy can roam space in ways bounded only by the maker's imagination. Soaring fairies or creatures can travel the space front to back and high to low. Maybe a scene follows a ship racing forward underwater, then bursting up into the sky to fly and weave past weapons fired from every direction. Object tracks suit pinpointing sound effects that demand spatial precision, but more crucially, Atmos guarantees the re-recording mixer that the final decisions in the mix carry over faithfully from theatre to theatre and room to room.

NOTE: Where Buses feed the Atmos master they turn into beds, while Tracks that feed it turn into objects.

### Predetermined Dolby Atmos Master Rules

By default, the opening ten tracks of every Dolby Atmos Master are designated a bed. The default bed there is a 7.1.2 bed, though it may be set anywhere from a 2.0 up to that 7.1.2 bed. You cannot add objects to those first ten tracks. Beginning at track eleven, the following tracks can then be turned into assorted beds or objects as the job requires. One easy way to picture it: buses routed to the Atmos Master count as beds, conveying several predefined sources. An Atmos bed is a fixed surround format able to hold height channels. Objects are usually mono, yet they can carry any format track DaVinci Resolve handles and travel through the metadata as one object element. Objects routed to the Atmos Master count as tracks, conveying dynamic audio content together with positional metadata. LFE has to go to a bed, since objects are positional metadata. If, say, the object is 5.1, its LFE channel must be routed into a Bed bus so it gets rendered in the Atmos master.

The Dolby Renderer renders the file once it is dragged from the Media Pool onto a track in the Timeline. There it renders the media along with its embedded metadata to the master's output format. This gives a straightforward way to audition pre-mastered content and to carry out basic tasks like trimming or syncing for fresh packaging and deliverables. Bringing in a Dolby Master file via the Fairlight menu, Fairlight > Immersive Audio > Import Master File, pulls out all the audio and metadata so you can keep creating content. Importing this way into Fairlight lays out every piece of metadata, plus the tracks, beds, and objects from the master file across the Timeline, so you can tweak, process, and work it further — rewriting panning, doing punch-ins, adding fresh media, and producing a new Atmos Master. Dolby Atmos files form a bundle of items. Merely linking files does not yield an Atmos Master file. You cannot, say, grab a rendered group of twelve tracks, link them, and then route their outputs to a 7.1.4 Atmos bed. Bear in mind that 7.1.4 is not an Atmos bed type. That linking-and-routing method is how ordinary PCM audio gets handled, but it does not apply to Atmos content, which amounts to much more than a mere set of tracks. The renderer takes the 128 channels made up of the beds and objects and renders them. Those channels come either from internal sources or from inside the master file. A plainly linked file will not play back through the Renderer. It has to play back the way every linked file does in Fairlight — by way of the native monitor. Playing, rendering, and extracting Atmos Master files is the job of the Dolby Atmos Renderer. The file types .atmos, ADM, and IMF may all be imported into Fairlight and run through the Renderer.

NOTE: As noted earlier, because of the Dolby Atmos specification, rendering the LFE into an Atmos master requires that it travel as part of a bed.

### Dolby Atmos Integration

The internal Dolby Atmos workflow is natively supported on Mac M1, Windows, and Linux, covering:

- Input
- Content creation
- Internal renderer
- Export of Dolby Atmos Master Files

A purpose-built Dolby Atmos Master bus format supplies a master fader in the Mixer for the Dolby Atmos Renderer and carries the Dolby logo in its header. It likewise shows a loudness history graph in its Timeline view, reporting integrated, momentary, and short term loudness figures. The Bus Format window reveals that this track has no outputs; it serves to control the Dolby Atmos Renderer. You may create only one master bus, and it will at all times reflect the format and metering of the internal renderer. With no patches present on the Dolby Atmos Sends, every source routed to a Dolby Atmos Master bus aims at the master, just as a traditional bus workflow would. Within this send workflow, buses turn into beds while tracks turn into objects. On Mac and Windows systems, the external Dolby Atmos Renderer integration has been refreshed for a much tighter fit when you run an external workflow. That has brought the tools of the internal renderer workflows into line with those of the external renderer. It covers:

- External Renderer discovery within the preferences.
- UI enable to switch between the internal and external workflow.
- Tally of the master connection state and master file status.
- Saving and recalling the program metadata inside the DaVinci Resolve Timeline, taking in every input

configuration, trims, down-mix, and binaural settings.

- Hands-on control over the renderer's metadata plus the binaural controls inside DaVinci Resolve, with two-way control of that program metadata reaching back from the server.
- Tally of the input configuration within the Patch page.
- Support for multi-client workflows, so several DaVinci Resolve instances can run while attached to

the same server for larger workflows.

- A tally, on the Patch page, of the bed and object assignments currently active on the Dolby Atmos Sends.

As you map a bed or track to the Atmos Master on the Patch page, a purple marking flags beds and a green marking flags objects.

### Binaural Audio Monitoring

To monitor your Dolby Atmos Master in Binaural, pick Binaural in the monitor section.

### The Binaural monitoring option

According to your monitoring rig, you can additionally build a parallel speaker monitoring setup alongside Binaural. You might, say, run a 5.1. external monitor mix together with a binaural headphone mix. Under Preferences > Video and Audio I/O, within the Audio I/O panel you can route Binaural to the headphone outs, and set a 5.1 monitor under the Monitor Speaker configuration. After that, in the Patch Input/Output panel, you can route to whichever positional channels suit your system and settings while also assigning the channels available for the headphones.

Using the Patch Input/Output to assign parallel binaural monitoring

### Binaural Render Options

Binaural rendering models the gap between a sound source and the listener. The Index offers choices for how you would like the binaural objects rendered. Mid is the default choice, but Off, Near, or Far are also available, according to the binaural rendering you want. Every one of these choices is saved into the Dolby Atmos file.

Binaural choices in the Tracks Index for assigning perceived distance You can rely on Clip Attributes to render a Dolby Atmos Master in Binaural. Just right click the file to bring up Clip Attributes, choose Binaural, then right-click to spin up a new Timeline containing the file. In the case below, a 7.1.4 file gets rendered out to a Binaural audio file.

Using Clip Attributes to render to a Binaural file

### Ambisonics

As a full-sphere, multi-channel, immersive “adaptive” audio format, Ambisonics enables placement of sounds throughout both the horizontal and the vertical planes. Set against other surround formats, the transmission channels of Ambisonics are not tied to particular speakers; they convey a whole sound field that a specialized microphone captures for a precise positional rendering of “sound in space,” or that sophisticated encoders generate out of channel-based sources. That flexibility lets Ambisonics work with a range of speaker layouts — 5.1 and 7.1.4, headphones, and big arrays — across many uses, among them theme parks, art installations, video games, and virtual reality. You can even mix and move between channel-based and Ambisonics formats with no third-party audio plugins required. The full Ambisonics support in DaVinci Resolve Fairlight covers spherical panning, Ambisonic bussing, Fairlight, AU, and VST Ambisonics effect plugins, precision reaching fifth order High Order Ambisonics (HOA), along with decoding — both channel and binaural — out to headphones.

### Ambisonic Orders

The “orders” of Ambisonics set the mathematical precision and the count of discreet channels used to depict the sound field, spanning the first through the seventh order. First order draws on four discreet audio channels, whereas higher orders call on more channels and thus more processing power. DaVinci Resolve Fairlight goes up to fifth order Ambisonics — which needs 36 channels — yet you can achieve strong results with third order and 16 channels.

### Ambisonic File Support

For Ambisonic files, the formats DaVinci Resolve accepts are WAV, BWAV, and .caf (1OA AMB and AmbiX included). Dropping a Media Pool clip onto the timeline, or building a new timeline that points at a clip, generates a track of the matching type, mirroring the file's Ambisonic order and channels.

### Enabling Ambisonics

Switch Ambisonics on by opening Preferences > Video and Audio I/O and ticking the Enable Ambisonics checkbox within the Immersive Audio section.

### Ambisonic Metering Options

Mixer and Track Header Meters Fairlight Ambisonic metering relies on one composite bar-graph meter across the Mixer, Track header, and Meter panel. In contrast to other audio formats, these do not map to particular speaker positions or levels that we would visually track to read what the signal is doing. As an alternative, you may prefer bar-graph meters that present Ambisonic signals as separate, discrete bus streams by choosing Fairlight > Immersive Audio > Ambisonics Channel Metering.

Default Ambisonics metering (left) and Discrete Channel metering (right)

### Ambisonics Metering

This Fairlight FX audio plugin provides two distinct visual metering views for examining your audio. You can drop the Ambisonics meter onto an audio track or bus through the Effects section of the channel strip. For details about the Ambisonics Meter, consult Chapter 181, “Fairlight FX.” Video Viewer Overlay On the Fairlight page, Ambisonic metering is likewise offered as overlays sitting on top of the Video viewer, so you can weigh the sound intensity against the picture. To switch on the Ambisonics Meter overlay:

- Activate 360 Viewer Mapping in the Video Viewer tools menu.
- Open the Ambisonics Meter submenu, click On, then pick one of the available metering modes.

### Enabling the Ambisonics Meter overlay

### Ambisonic Effects

Most Fairlight FX plugins — the Multiband Compressor, Limiter, Reverb, and Channel Dynamics and EQ among them — are Ambisonic-native, and DaVinci Resolve additionally works with compatible Ambisonic-native third-party AU and VST effects. To read up on the Channel Dynamics and EQ plugins, turn to Chapter 177, “Mixing in the Fairlight Page.”

To learn how Audio Effects plugins can be put to use within DaVinci Resolve, turn to Chapter 180, “Audio Effects.” And for the individual Fairlight FX plugins, turn to Chapter 181, “Fairlight FX.”

### Setting Up an Ambisonic Mix

To arrange and configure your Ambisonic mix:

- Begin by deciding which Ambisonic order you wish to work in. A higher one such as third order (16 channels) suits precise positioning best.
- Build Ambisonic busses and route your source tracks or other busses into them. Ambisonic busses can be assigned to other Ambisonic busses, even where the orders differ. The Fairlight engine and FlexBus take care of any up- or down-mixing needed automatically.
- Apply the 2D or 3D Spherical Panners on each channel to set the placement of your sources within the Ambisonic space. Any channel-based format works, from mono through stereo up to, say, 7.1.2, and you can position them freely across the spherical sound field.

To read up on the 2D and 3D Panners, turn to Chapter 177, “Mixing in the Fairlight Page.”

- Click the Bus Monitoring menu at the far right of the Transport control, and pick the source you wish to monitor.

### Monitoring Source selection

- Pick your output format from the Monitor section dropdown beside the speaker output level control. The options on offer include Binaural for headphone monitoring. As soon as you choose a format, the matching decoder is dropped into the monitoring path automatically, and the audio is routed to your Audio I/O and out to your speaker system.

### Output Format selection

### Binaural Monitoring with Head Tracking

When Binaural is your chosen output format, you can also monitor your Ambisonics mix over headphones with Head Tracking support for a richer monitoring experience.

### Head Tracker preferences

### Enabling Head Tracking

Turn head tracking on by going to Preferences > Control Panels > Head Tracker. Doing so places two buttons to the left of the Monitor Bus Source dropdown, just beneath the docked Video Monitor panel:

- HT: Switches Head Tracking on and off.
- CAL: Sets the present tracker heading as the “Front,” treating it as the point of origin.

### Head Tracking Video Viewer Overlay

Binaural Head Tracking also lets you place an overlay on the video viewer to study your mix against the picture: click Headtracking Display > On to add an onscreen crosshair that marks the present head (headphone) orientation. This submenu further holds a Show Torso option that adds a head and torso to the video viewer, which turn as the head tracking angles and positions shift.

### Head Tracking Video Viewer overlay

### Parallel Ambisonic and Channel-based Workflows

Within a single timeline you can build both Ambisonic and channel-based mixes and render several outputs in different formats at once. Thanks to the shared panning data, you can also stand up a parallel mix inside an Ambisonic timeline by converting an existing production of another surround format (e.g., Dolby Atmos) to Ambisonics and pulling that into your production.

### Ambisonic Rendering

On the Deliver page, Ambisonic mixes can render either as a multichannel adaptive file whose stream count follows the Ambisonic order of the mix (e.g., 1OA, 2OA, etc.) or as a downmix to whatever format you pick, such as 7.1.4.

### Immersive Format Configuration

Within Preferences > Video and Audio I/O > Immersive Audio, you can switch on the various Immersive options on offer. The choices include Dolby Atmos, Ambisonics, and Auro 3D; Audio Vivid and MPEG-H Audio; plus BS.2051, 22.2 Surround, SMPTE ST 2098, and 360 Reality Audio. Within Preferences > Video and Audio I/O > Dolby Atmos, you can configure an external Dolby Atmos Renderer to handle the monitoring and mastering for Dolby Atmos. Type the server's IP address in yourself, or choose a discovered server using the dropdown menu. You should also pick the base audio output — the one from among your audio outputs that carries the audio over to the external renderer.

The toggles, under the Video and Audio I/O preferences, that turn on immersive audio formats

### Exporting ADM BWF

Right from the Fairlight timeline, a Dolby Atmos master file can be exported as an audio-only ADM BWF. Those same options are present on the Deliver page too. When you export a Dolby Atmos master file from the Fairlight timeline, the filename comes from the Timeline name. Be sure to rename the Timeline to the filename you want.

- In the Media Pool, locate the current Timeline.
- Change the Timeline name to your desired export filename.
- Just like every other bouncing and delivery method, a range has to be marked in the

Timeline to export.

- Hit R to bring up the Range Selection tool. To set a range spanning a whole clip, double-click any Timeline clip

for the entire clip.

- Choose Fairlight > Immersive Audio > Export Master File.

### Export Immersive Master options
