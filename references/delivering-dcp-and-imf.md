# Delivering Dcp And Imf (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Delivering DCP and IMF

When a project calls for Digital Cinema Package (DCP) or Interoperable Master Format (IMF) mastering bound for digital cinema or broadcast distribution, DaVinci Resolve handles native DCP and IMF encoding and decoding so you can build and play back unencrypted DCP and IMF deliverables, and it can also tie into Fraunhofer's easyDCP application to master fully encrypted DCP files, replay them for testing, and produce Key Delivery Messages (KDMs) for theatrical distribution — every step right inside DaVinci Resolve. In other words, you can encode a DCP or IMF master directly off your program's source media, the whole job staying inside DaVinci Resolve's 32-bit floating point image processing pipeline, for the best quality achievable.

### Native IMF Encoding and Decoding (Studio Version Only)

Over in the Render Settings, the Video panel's Format dropdown now carries a native IMF option that exports to the SMPTE ST.2067 Interoperable Master Format (IMF) for tapeless deliverables headed to networks and distributors. Outputting to IMF takes no extra licenses or plugins. The IMF format handles several video tracks, several audio tracks, and several subtitle and closed caption tracks, all designed to carry multiple output formats and languages within one deliverable. Beginning with DaVinci Resolve 16, IMF export can also output IMF packages built on ST.2098 and Dolby immersive audio drawn from selected Main busses. The whole thing works by wrapping a timeline's various video and audio tracks (media essences) plus subtitle tracks (data essences) into a “composition” inside the Material eXchange Format (MXF). On top of that, a dropdown menu beside this preset supplies Generic, 20th Century Fox, and Netflix versions of it.

Within the Render Settings, the IMF Generic preset offers choices for various output resolutions Pick IMF from the Format dropdown and the Codec drop-down menu offers Kakadu or EasyDCP encoding, where Kakadu is the one bundled with DaVinci Resolve Studio. A Type dropdown lets you settle on the kind of JPEG2000 output you're after, among them RGB, YUV, Dolby Vision, and HDR Vivid. Further parameters take in:

- Package Type: Its default is App2 Extended (App2e), used to encode JPEG 2000 as high as 4K.
- Bit Depth: The bit depth of the encoded IMF video.
- Encoding Profile: A dropdown letting you pick among Auto, IMF, and Broadcast.
- Encoding Level: Offers varying choices depending on the Encoding Profile selection.
- Maximum bit rate: Lets you set how much the result is compressed.
- Lossless Compression: Lets you opt to encode with lossless compression.
- Slope-Rate Control: A checkbox for specifying lossless compression.
- QStep: (DCP, IMF) Lets you go with automatic or hand-set DCP quantization levels

at which the video signal compresses when the Kakadu JPEG 2000 encoder is in use.

Render settings in the Export Video section for the IMF format A distinct cluster of parameters called Composition Settings, sitting below the Advanced Settings, lets you attach metadata to your IMF package, among them:

- Composition name: The name of the exported composition.
- Issuer: The organization providing the composition.
- Use current date: A checkbox letting today's date stand in automatically as the Issue date.
- Issue date: The date the composition is issued.
- Content kind: A dropdown offering a list of valid options for defining the content.
- Content version label: Intended to flag which version of the content is being supplied.
- Annotate xml using composition name: Auto-populates Asset Map, Composition Playlist, and

Packing List from project data. If left off, you can edit those three fields by hand.

- Annotate media using filename: Fills Main Video Track and Audio Track 1 in automatically, drawing

on project data. If left off, you can edit those three fields by hand.

### Parameters for adding composition metadata

### Native Unencrypted DCP Encoding and Decoding (Studio Version Only)

DaVinci Resolve carries native DCP encoding and decoding support of its own, though only for unencrypted DCP files. So you can output and bring in (for test playback) unencrypted DCP files without having to buy an EasyDCP license. Should you hold a license, a setting in the System Preferences' Configuration panel lets you decide whether to lean on EasyDCP (for producing encrypted DCP output) or the native DaVinci Resolve encoding.

### Native DCP Encoding Parameters

Pick DCP from the Format dropdown menu and these extra parameters come into view:

- HDR: (DCP, IMF) Marks the package as carrying HDR content.
- Use interop packaging: (DCP only, located under Type parameter) Lets you build an Interop

DCP package, founded on an older DCP delivery standard that isn't forward compatible with SMPTE DCP packages.

- Maximum bit rate: (DCP, IMF) Lets you set how much the result is compressed.
- Lossless Compression: (IMF) Lets you opt to encode with lossless compression.
- Slope-Rate Control: (DCP, IMF) A checkbox for specifying lossless compression.
- Quality: (DCP, IMF) Lets you go with automatic or hand-set DCP quantization levels at which the video signal compresses when the Kakadu JPEG 2000 encoder is in use.

### Native DCP settings in DaVinci Resolve

Having picked DCP from the Format dropdown menu, you'll find a Composition Settings group appears — click the disclosure control — bringing these parameters so you can fill in standard DCP composition metadata:

- Composition name: The name of the exported composition. DCPs follow particular naming conventions for the composition name, baking in metadata about the file itself for DCP projectors and playback gear. DaVinci Resolve includes a tool, the Composition Name Generator, to build these names correctly for you; reach it through the “Edit” button beside this field. Just complete the fields and press OK, and DaVinci Resolve renames your composition to match these standards.

For you, the Composition Name Generator hands a standards-compliant name over into the Composition Name field.

- Issuer: The organization providing the composition.
- Use current date: A checkbox letting today's date stand in automatically as the Issue date.
- Issue date: The date the composition is issued.
- Content kind: A dropdown offering a list of valid options for defining the content.
- Content version label: Intended to flag which version of the content is being supplied.
- Annotate xml using composition name: Auto-populates Asset Map, Composition Playlist, and

Packing List using project data. Otherwise, those three fields stay editable by hand.

- Annotate reel index as suffix: Auto-populates Reel Annotation off project data.

Otherwise this one stays editable by hand.

- Annotate media using filename: Fills Main Video Track and Audio Track 1 in for you, pulling

from the project. Otherwise, those three fields stay editable by hand.

### Parameters for adding composition metadata

### Rendering IMF Segments and DCP Reels

Beyond rendering media as one file, DaVinci Resolve can split IMF and DCP projects into separate segments and reels. That helps when you need to chop your timeline down to fit allowed file sizes on legacy file systems, to peel marketing and studio assets away from the final film, or simply to swap out certain stretches of the film without re-encoding the whole thing. To Render an IMF Segment or DCP Reel: 1 Pick IMF or DCP in the format settings on the Render Settings panel's Video tab. 2 Head to the composition settings' “Segment list” or “Reel list” section. 3 Pick from these options: Single segment/reel: Encodes the Timeline as one file (the default). Regular intervals of: Encodes the Timeline as several segments/reels, each one as long as the value you enter in the “mins” field. Align to clips on the first video track: Splits the Timeline into several segments/reels, turning each individual clip sitting on the Timeline's V1 track into a separate file of its own. Keep audio as single segment (IMF only): Tick this checkbox to hold the IMF's audio portion as one file no matter which segment options you chose above. 4 Click the Add to Render Queue button.

### IMF Segment options

### Creating DCP/IMF Supplemental Packages

After one is created, DaVinci Resolve can reimport a DCP or IMF so you can overwrite parts needing fresh media, then export a “Supplemental Package” — in effect a new version of the program marrying its newly overwritten parts to the old version, letting you deliver only what changed. NOTE: Supplemental packages work solely with the Kakadu encoder and decoder; they don't work with DCP or IMF packages made through EasyDCP. To steer clear of trouble, turn “Use easyDCP decoder” off within the DaVinci Resolve System Preferences, over in its Decode Options panel.

### Importing a DCP or IMF Into a Timeline

1 In the Media page, use the Media Storage browser to locate and pick the DCP or IMF, then look at the Metadata Editor's header to confirm your media can serve as the basis for a supplemental package. The Metadata Viewer lists the IMF profiles that are supported.

The Metadata Editor's header displaying an IMF fit for building a supplemental package 2 Start a new project and bring the DCP/IMF package you mean to alter into the Media Pool. Should a dialog ask whether to switch your timeline frame rate to match the incoming media, click Change so the project lines up with the media. 3 Build a timeline off the composition playlist (XML) held inside the imported DCP or IMF: right-click that imported package within the media pool and pick “Create New Timeline Using Composition Playlist” from the contextual menu.

A right-click on an imported IMF or DCP clip within the Media Pool surfaces, on the contextual menu, a command for making a fresh timeline from the composition playlist 4 The New Timeline dialog carries an “Import Dolby Vision Project Settings” checkbox. Switch it on and clicking Create does this: a) Dolby Vision turns on in the Project Settings' Color Management panel, and the Mastering Display menu is set to match the IMF package's. b) When Resolve Color Management (RCM) is off, the Timeline Color Space is set to match the Dolby Vision metadata. But when RCM is already on, you have to set this yourself by enabling “Use Separate Color Space and Gamma,” then changing the Timeline settings to P3-D65” and “ST.2084” respectively.

5 Building the Timeline brings in Dolby Vision metadata (where it applies). That lets a Tone Mapping preview on the Color page draw on the original metadata.

Dolby Vision metadata will be imported if present when importing an IMF After import finishes, every video and audio clip from the DCP or IMF lands in a new bin named for the package. Its icon marks the resulting timeline as a DCP/IMF timeline.

The imported media and timeline when you import an IMF

### Editing the Resulting Timeline

From here you can edit the program in the Timeline however you need.

- You can overwrite stretches of the Timeline with new clips. Every change folds into the supplemental package on its own.
- You can reach for the Blade tool or the Insert Edit command to carve out stretches of the existing program where Fusion effects, audio grading, or color correction are needed. Whenever you do, you must right-click that stretch and pick “Include in Supplemental Package” so it exports properly.

A right-click on a section of the program followed by picking Include In Supplemental Package With IMF Dolby Vision packages, be sure every change sits on the first video track (V1). NOTE: When RCM is in play, confirm that the inserts' input color space and gamma are right.

### Dolby Vision Metadata

You can reuse the Dolby Vision metadata from the imported DCP/IMF file by picking “Original Metadata” in the Tone Map Using dropdown menu of the Color Page's Dolby Vision palette

Setting a clip to Original Metadata in the Color Page As an alternative, you can bring this metadata in on its own from an existing XML through the “Import Metadata from XML” command in the option menu of the Color page's Dolby Vision palette. On success, “Imported Metadata” switches on.

### Exporting

To export a supplemental package, switch on “Supplemental Package” in the video panel of the Deliver page Render Settings list.

### Setting an export to be a Supplemental Package

The codec type and profile are chosen automatically to match the original DCP/IMF package, and the audio tracks are set to mirror the Timeline tracks. Be sure the remaining audio settings line up with the original version, since they begin at their default values.

Setting the audio settings of a Supplemental Package export

### Photon Validation of IMF Packages

For IMF App2/App2e packages, Photon is Netflix's validation software. The Photon validation option appears only on Resolve Studio when JDK/JRE version 1.8 or higher is installed, available at https://github.com/Netflix/photon. NOTE: Please switch off “Use easyDCP decoder” under “Preference,” since decoding IMF packages can run into trouble without an easyDCP license.

### Validating in the Media Pool

To validate an existing IMF package with Photon, bring it into the Media Pool, then right-click it and pick “Perform Photon Validation” from the context menu.

### Validating an IMF in the Media Pool

A report dialog shows up once validation wraps.

### A validation report

### Validating on Export

You can switch Photon validation on in the File panel of the Deliver page Render Settings; picking the “IMF Netflix” preset turns this option on as well. Once enabled, DaVinci Resolve runs Photon validation after exporting the IMF package. The validation report saves to a text file inside the IMF package folder, and a report dialog appears should any error turn up.

### Enabling Photon validation on export

### Using and Licensing EasyDCP

A demo version of easyDCP ships with both DaVinci Resolve and DaVinci Resolve Studio. You'll find the demo version's operation details and restrictions later in this chapter. The fully functional easyDCP runs on licensing modules bought from http://www.easyDCP.com (info@ easyDCP.com), and every new DaVinci Resolve system (server) requires its own license plus specific certificates for DCP and KDM generation and for DCP playback.

### Requesting Your Server Certificate Set

Before your DaVinci Resolve system can produce DCPs and KDMs, you must request a particular set of configuration files known as the Server Certificate Set. Start by buying your encoding, encryption, decoding, and decryption modules from easyDCP. They'll hand you a password for your easyDCP account. Next, from the DaVinci Resolve File menu, pick easyDCP > Request Server Certificate Set. Complete the details on the request form and save it to your desktop or wherever you can find it readily. You can email this html file to info@easyDCP.com. Once the html is sent, a Server Certificate Set tailored to your installation gets generated and posted for download in your easyDCP Website User Account. The Server Certificate Set built for your DaVinci Resolve holds files keyed to your purchased modules and your particular DaVinci Resolve server hardware. The table below lists the modules along with the licenses and certificates produced, then a short rundown of each item.

DCP Encoder DCP Encoder with Encryption DCP Player DCP Player with Encryption

### License X X X X

### Server Certificate ­ X

X

### Signer Certificate X X

License: The License serves to activate the purchased modules on one specific hardware server. Server Certificate: Every DCP render (the industry calls it an “Instance”) that uses encryption or decryption carries its own server certificate. You need this certificate to receive Key Delivery Messages (KDMs), the things that unlock encrypted DCPs. Signer Certificate: A Signer Certificate signs particular files inside a DCP package and/or Key Delivery Message (KDM) to confirm which authority generated the DCP instance.

### Importing Your Server Certificate Set

Once it's been generated and downloaded onto your DaVinci Resolve server, the Server Certificate Set has to be imported into DaVinci Resolve.

To import your server certificate: 1 Pick File > easyDCP > Import License and Certificates. 2 Through the Import Server Certificate dialog, select the file, type your Certificate Set password, and click Import. 3 To confirm your easyDCP license and the Server Certificates, pick easyDCP > About easyDCP. From here on out, the controls within the Settings window, the Deliver page, and the File menu let you master and play DCPs.

### Limitations of the Demo Version of easyDCP

In the demo version, the DCP encoder bakes visible DaVinci Resolve and easyDCP logo watermarks into the rendered Digital Cinema Package (DCP) images. Since the demo version offers no encryption, these DCPs are fine for screening in a digitally equipped cinema. The demo version's DCP playback module runs 15 seconds at full quality. Past that, playback quality drops sharply. What's more, no audio renders beyond 15 seconds of playback.

### Switching Between Native DCP and EasyDCP Encoding

In the System Preferences' Configuration panel, the “Use EasyDCP Encoder” checkbox lets you decide between DaVinci Resolve's native DCP/IMF encoding and your licensed EasyDCP software. Either way, all the setup takes place inside DaVinci Resolve's Deliver page.

### EasyDCP Color Management

The Project Settings' Color Management panel offers a Timeline Colorspace dropdown menu that's active for EasyDCP encoding whether or not DaVinci Resolve Color Management is in use on the current project (the one setting covers both color management jobs). Set it to the color space your current DaVinci Resolve timeline uses. Say you're grading on a Rec. 709 monitor for television deliverables but also want a DCP — pick Rec. 709 Gamma 2.4 and DaVinci Resolve renders the DCP with the proper Rec. 709 to XYZ matrix.

### EasyDCP Output in the Deliver Page

To master a DCP on the Deliver page, walk through the steps below, which cover every easyDCP setting found in the Render Settings list. To master a DCP or IMF: 1 Put “Render timeline as” on Single clip. 2 Pick easyDCP in the Video Format dropdown. 3 In the Codec dropdown, pick whichever option suits your intended output — its type (DCP or IMF), its resolution (2K or 4K), plus its aspect ratio (native, scope, or flat). 4 Set the Composition Name. Into this field goes a standardized name identifying the DCP under encoding. Type a name in directly, or else hit the “...” button, which brings up the easyDCP Composition Name Generator window. An editable Film Title field shows up, together with several dropdown menus that let you pick various DCP attributes — content type, aspect ratio, language of audio and subtitles, and the like. As you fill in each attribute, the name being built appears at the top of the window, and clicking OK copies the finished Composition Name into the Render Settings' Composition Name field. 5 If needed, set the “Maximum DCP bit rate” you want by typing or dragging in the field (its range runs 50 to 250 Mbit/sec). When you're unsure which data rate to pick, check with the client or distributor you're delivering the DCP to. 6 You can output two DCP package types, governed by the “Use Interop packaging” checkbox:

- The standard package follows the “Interop” specifications for DCPs and is on by default. With “Use Interop packaging” on, though, your output's frame rate is capped at either 24fps or 48fps, so make certain your timeline sticks to those frame rates.
- To build DCP packages at other frame rates matching your timeline, switch “Use Interop packaging” off to make a SMPTE-standard DCP. This allows added frame rates such as 25, 30, 50, and 60 fps. That said, SMPTE-Standard-DCPs don't play on every JPEG2000-based playback system, so the Interop standard is generally the safer pick unless you know the player handles SMPTE-Standard DCPs.

7 Switch on the “Encrypt package” checkbox to encode an encrypted DCP. This tells the encoder to build a Digest holding the keys used during encryption. That Digest lets you play the resulting DCP on your system and generate KDMs so the DCP can play on other servers. NOTE: Leave the DCP unencrypted and it plays on any DCP player/decoder freely. 8 Set the Subtitles Path. With a properly formatted subtitle file on hand, click the Browse button to link it. 9 To fold an audio mix into the DCP, head to the Audio section, switch on the Render audio checkbox, and in the “Render channels of audio” dropdown menu pick the channel count matching the number of Audio Mixer output channels set on the Edit page. 10 Click the Browse button beneath the “Render to” field and choose where the resulting DCP goes. Be sure to pick a drive with room enough for the final DCP's estimated size. 11 Pick whatever options you need from the Output Options to get the quality you want. 12 Click the Add Job to Render Queue button, then click Start Render to build your DCP. A DCP gets created and placed where you chose, ready for playback or delivery.

### KDM Generation and Management

Key Delivery Messages (KDMs) are the means by which an encrypted DCP is allowed to run on a named projector, in a given theater, at an appointed time. DaVinci Resolve can create KDMs, which is handy for exporting them for select screenings, but commercial distributors may need thousands of KDMs. Happily, easyDCP lets you tap external Distribution KDM (DKDM) utilities to generate KDMs for your clients, so your DaVinci Resolve workstation isn't tied up doing it.

### Publishing Your Encrypted Digital Cinema Package

You can play your encrypted DCP on the very DaVinci Resolve system that made it, but to publish the DCP so other players can decode and play it, you have to generate a KDM to send the player. Whoever runs the other player, or players, must generate a Server Certificate for each of their players and send it to you, so that when you generate the KDM it's meant for those players alone. Pick the DCP in the Media page Library. Right-click and pick Generate KDMs. From the dropdown, choose where the Server Certificate file lives if the KDM is for a single player, or a folder for several players. Set the start and end dates over which the KDM stays valid, an output folder for the KDM, then pick Generate. Now you can send your DCP and the KDMs to the player you authorized. Its user imports the KDM, and the DCP plays between the start and end dates.

### Playing Your Digital Cinema Package

When you want to play a DCP that DaVinci Resolve produced, head to the Media page, drop it into the Media Pool, and cut it into a timeline just as you would any clip. Decoding the JPEG2000 images held inside the DCP in real time is heavy on computation. On an underpowered system you can drop the files' decoded resolution by choosing Half or Quarter Resolution Decode out of the File > easyDCP menu. A smaller, less bandwidth-hungry version of the JPEG2000 files gets decoded by tossing some levels of the wavelet stage within the decoder, which directly boosts playback performance.
