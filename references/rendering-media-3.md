# Rendering Media (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Plenty of scenarios make this worthwhile: Fast output of simple edits: Suppose you cut a basic cuts-only promo from footage lifted out of an already-rendered program in QuickTime ProResHQ 422 media, and you’re exporting back to that very same format. Where it’s feasible, Bypass re‑encode lets you push all that media out in a flash. Fast output of previously output timelines with small changes: Say a handful of shots need swapping inside an effects-heavy program that’s already been output. Pull the output media file into a new timeline and substitute only the shots that require it. DaVinci Resolve copies every previously rendered piece of media straight through, re-encoding nothing but the new clips and the effects and grading they carry. The payoff is a quick re-output of a high-quality master file without rerendering the whole program. Fast output of previously output timelines with new audio mixes: Imagine you’ve dropped an already-rendered Video+Audio clip onto a timeline and cut in a fresh audio mix clip to take the place of the old one. Here a new Video+Audio file gets written swiftly with the new audio, yet its video component skips re-encoding, once more yielding a fast export at top quality. TIP: To see which video formats work with Bypass Re-encode across macOS, Windows, and Linux — plus which ones support Alpha channels — consult the “Supported Codec List” on the DaVinci Resolve Support page at: https://www.blackmagicdesign.com/support/family/davinci-resolve-and-fusion.

- Use optimized media: Tick this checkbox and DaVinci Resolve leans on optimized media, where it exists, for the final render to shave off time. That’s convenient when your media was optimized to the same format you’re outputting to, or a better one. But if you optimized to a format below your output, clear the box so DaVinci Resolve falls back to the original media on every clip and secures the best quality on offer.
- Use proxy media: With this checkbox on, DaVinci Resolve reaches for the generated proxy media, when present, to speed up the final render. Should your proxies sit at a lower-quality format than your output, though, clear the box to make DaVinci Resolve handle each clip from the original media and lock in the best quality available.
- Use render cached images: Switch this checkbox on and DaVinci Resolve pours media straight from the cache into the output files to save time. Caching in the very format you’re outputting to — or a higher one — makes that handy. Caching below your output format, however, means you’ll want the box cleared so DaVinci Resolve processes all media live as it renders, writing at the top quality your output supports.
- Force sizing to highest quality: When you’ve kept the “When resizing and scaling:” option on Bilinear to keep slower workstations responsive, enabling this checkbox forces every clip to render with the “Uses Sharper filter” setting from the Image Scaling panel of the Project Settings.

Chapter 4, “System and User Preferences,” carries more on this.

- Force debayer res to highest quality: With camera raw media formats that permit variable-quality debayering, dropping the debayer quality to keep grading responsive in real time is common practice. Ticking this checkbox ensures media always renders at the best quality on hand, sparing you from forgetting to bump the debayer setting back up when you set up a render at 3am.
- Render All Video Tracks: (When rendering Single Clips) Clearing Render All Video Tracks and picking specific tracks in the Disable dropdown menu keeps those tracks out of the final output on a per-render-job basis.
- Enable flat pass: A trio of options decides whether each clip renders with its grade applied.

Off: DaVinci Resolve renders every clip with its grade in place, no exceptions. With clip settings: For each version of a clip, the system reads that version’s pass flat flag; where it’s set, color correction is switched off for that version, and otherwise the version renders with its grade untouched. You flag versions one at a time by right-clicking a clip’s thumbnail in the Timeline, opening the submenu for the version you mean to flag, and selecting Enable Flat Pass. Always On: Ticked, this has DaVinci Resolve strip the grade from every clip it renders.

- Disable sizing and blanking output: Left off, Output Blanking for letterboxing or pillarboxing is “baked” into the output, along with every sizing tweak made on the Cut, Edit, and Color pages, Image stabilization included. Switched on, it shuts off Output Blanking, the Cut and Edit page sizing tweaks, the Color page Input and Output Sizing, and Image Stabilization. The media then renders at the source resolution when “Render at source resolution” is on in individual clips mode, or otherwise at whatever resolution the Timeline or project currently specifies. Output through Final Cut Pro or Premiere Pro XML, or Avid AAF, and the sizing tweaks get written into the XML or AAF files produced to round-trip those tweaks as editable metadata back into an NLE.

Keep in mind that “Disable sizing and blanking output” leaves untouched any transform happening inside the Fusion page, and likewise any transform driven by an OpenFX or ResolveFX plugin sitting on one or more clips across the Cut, Edit, or Color pages. Every one of those effects keeps rendering into the final output.

- Trigger script at: Ticking the “Trigger script at” box now lets you fire a script either before or after a timeline renders.

Start: Runs the script ahead of the render job. End: Runs the script once the render job finishes. Script: Names the particular script to run, which you choose from the matching dropdown menu. Any script has to target the Resolve scripting framework in either Python or Lua, and each platform expects it in a particular spot. On MacOS: /Library/Application Support/Blackmagic Design/DaVinci Resolve/Fusion/Scripts/Deliver/ — on Windows: C:\ProgramData\Blackmagic Design\DaVinci Resolve\Fusion\Scripts\Deliver — and on Linux: /opt/resolve/Fusion/Scripts/Deliver

- Render full extents: (When rendering Individual Clips) Ticking this box renders the whole original media clip in full rather than only the stretch bounded by the timeline clip’s In and Out points.
- Add X frame handles: (When rendering Individual Clips) Lets you set front and rear handles, expressed in frames, to be output. It pays off in round trips, where the finishing editor may want spare handles for rolling edit points or slotting in transitions while polishing the graded edit.
- Tone Mapping: (On hand in Single clip mode once Dolby Vision or HDR10+ has been switched on under Project Settings) At None, the timeline goes out under the current color management settings. Set to either Dolby Vision or HDR10+, you can send the timeline out at a chosen peak nit level, color space, gamma, and Data Level, drawing on the available Dolby Vision or HDR10+ metadata to steer the tone mapping operation you picked. That makes spinning up several jobs to output HDR at differing levels straightforward whenever needed.

### DCP and IMF Composition Settings

Pick either DCP or IMF from the Format, click the disclosure control, and a Composition Settings group surfaces carrying the parameters below — together they let you fill in generic DCP and IMF composition metadata along with assorted studio-specific settings:

- Composition name: What the exported composition is called.
- Issuer: The organization supplying the composition.
- Use current date: A checkbox that automatically adopts today’s date as the Issue date.
- Issue date: The date on which the composition goes out.
- Content kind: A dropdown listing the permitted choices for defining the content.
- Content originator: A text field naming whoever is accountable for this content.
- Include volume index and output profile list: Tick this box to fold those xml files into

the package.

- Content version label: Intended to mark which version of the content is being supplied.
- Annotate xml using composition name: Fills Asset Map, Composition Playlist, and

Packing List automatically from project data. Left off, you edit those three fields by hand.

- Annotate reel index as suffix (DCP only): Fills Reel Annotation automatically from project

data. Left off, this one is hand-editable.

- Annotate media using filename: Fills Main Video Track and Audio Track 1 automatically from

project data. Left off, you edit those three fields by hand.

### Subtitle Controls

Controls in the Subtitle Settings group dictate how your program’s subtitles get exported:

- Export Subtitle checkbox: Toggles subtitle/closed caption output on or off.
- Format pop-up: Offers four routes for outputting subtitles/closed captions.

As a separate file: Writes each subtitle track you pick to its own file in whatever format the Export As pop-up names, with a bank of checkboxes governing which subtitle tracks get output. Burn into video: Bakes the currently selected subtitle track right into all the rendered video. As embedded captions: Tucks the currently selected subtitle track into supported media formats as an embedded metadata layer. CEA-608 closed captions are presently handled within MXF OP1A and QuickTime files, and the subtitle format comes from the Codec pop-up that turns up.

- Export As: (Surfaces solely with Format on “As a separate file.”) Picks which subtitle/closed captioning format to write out, among IMSC1, DFXP, SRT, and WebVTT.
- Include the following subtitle tracks in the export: (Shown only while Format sits on “As a separate file.”) A row of checkboxes flags which subtitle tracks to output.
- Codec: (Only available when Format is set to “As embedded captions.”) Sets how embedded closed captions are formatted, choosing between Text and CEA-608.

NOTE: At present, neither analog (Line 21) nor digital (CEA-708) closed caption output over Decklink or UltraStudio is supported.

### Audio Panel

Every audio-oriented parameter lives in this panel.

- Export audio: Tick this checkbox to render the source audio — or audio you synced inside DaVinci Resolve — alongside whatever media DaVinci Resolve outputs.
- Format: Choose which audio format to render. Your choice of format brings up different audio codec options beneath it.

MXF OP1A(IMF): Produces media files matching the OP1a (Operational Pattern 1a) SMPTE 378M flavor of MXF media for file exchange. MXF OP-Atom: Produces media files matching the SMPTE 390M flavor of MXF media for file exchange. QuickTime: Surfaces every audio format QuickTime can handle. MP4: Produces media in the MPEG-4 file format. WAVE: Produces media in the WAVE file format. MP3: Produces media in the MPEG-3 file format. FLAC: Produces media in the FLAC file format.

- Codec: Pick among Linear PCM (the default), AAC audio, IEEE Float, or MP3. Encoding to AAC audio is offered on macOS only.
- Sample Rate: Sets the audio output’s sample rate, given in Hz.
- Bit Rate Strategy: (Available for AAC encoding) Pick from Constant Bit Rate,

Average Bit Rate, Variable Bit Rate Constrained, and Variable Bit Rate.

- Quality: (Open during AAC encoding once Bit Rate Strategy rests on Variable Bit Rate) Five settings that balance speed against quality while encoding AAC audio.
- Data Rate: (Open during AAC encoding once Bit Rate Strategy rests on Constant, Variable, or Variable Constrained) Picks the ceiling data rate for AAC encoding.
- Bit Depth: Sets the bit depth used when outputting the source audio.
- Render one track per channel checkbox: This checkbox decides whether each channel is exported as its own track within the exported file’s structure. Multi-channel formats can be named (2.0, 5.1, etc.), or the output can take the form of flat multi-mono files.
- Render as discrete audio tracks checkbox: Much like the one above, this checkbox still writes one channel per track. Discrete tracks, though, carry no positioning info and don’t cluster into multi-channel clips (2.0, 5.1, etc.). A mono file exported via Render one track per channel, for instance, arrives front and centered, whereas the same file exported as a discrete audio track holds no built-in position information.
- Output Track #: This dropdown menu picks which Main or Submix bus to output. The Plus button on its right lets you tack on further tracks for export within this job, so exporting several Mains or several Subs just means adding more Track pop-ups.

Selecting a track that carries several audio channels brings up a field reporting how many channels will be output, and a virtual slider lets you alter that count. Under Single Clip Mode, choosing “All Timeline Tracks renders every audio track in the present timeline as its own track inside the media file you’re outputting. Tracks holding multi-channel clips emit output tracks with the same channel count, so you can put out mixed sets of mono, stereo, 5.1 or 7.1, and adaptive audio tracks, with each independently rendered track mirroring identical channel mappings.

- Language: (Only available when outputting to the IMF format) This dropdown sets the language of a given output track as you output to IMF. Because an IMF file can hold several audio tracks bearing different mixes for different regions, labeling each output track by language matters.
- Content: (Only available when outputting to the IMF format) This dropdown sets the content of a given output track as you output to IMF. Because an IMF file can hold several audio tracks bearing different mixes and content, tagging each output track by content matters.
- Audio Normalization: Loudness standard presets chosen from the Audio tab of the Delivery page’s Render settings have the deliverable normalized to suit automatically. These controls govern audio normalization one output at a time, and clearing this box skips audio normalization and optimization altogether.

Normalize to Standard: Tick this box to bring loudness or peak (whichever crosses thresholds first being scaled) into line with a standard. Optimize to Standard: Tick this box to optimize loudness and peak together against a standard, holding loudness within the wanted range while keeping peaks under threshold. Standard: Pick the normalization standard to apply. Target Level: Enter the normalization level in dBFS. Output Track #: Tick the box to direct the normalization at these outputs.

### File

Every remaining parameter sits in this panel.

- Filename Uses: Three options handle naming the output media file(s) for you.

Use Custom Filename: Lets you type a name of your own into the Custom name/File prefix field. Use Timeline Name: (Applies while a Single Clip renders) Pick this and the Timeline’s name is used. Use Source Filename: (Applies while Individual Clips render) Pick this and the filename of each clip’s matching source media file is duplicated and applied to the media DaVinci Resolve outputs. It’s the go-to choice when you’re making offline media for an editor that you later plan to reconform back to the original DaVinci Resolve project. Clear this checkbox and you can shape filenames through the other options in this batch of settings.

- Custom name: Lets custom text name all rendered files. As long as you’re neither using the source filename nor rendering to a timecode-based file format, you can type a filename here. While editing the Custom Name or File Prefix (or File Suffix), “metadata variables” are available — graphical tags you drop in to surface clip metadata. That comes in especially handy when rendering Individual Source Clips. Add the metadata variable tags %scene*%shot*%take, say, and the File Prefix would read “12_A_3” provided “scene 12,” “shot A,” “take 3” sat in the source clip’s metadata.

Chapter 16, “Using Variables and Keywords,” covers how variables are used and lists every variable DaVinci Resolve makes available.

- File suffix: Lets custom text and/or metadata variables (covered above) attach to the tail end of all rendered files.
- Use unique filenames: (Applies as Individual Clips render, and only with Filename uses on Custom name) Switched on, extra characters get appended to each rendered media file so that every one ends up with a wholly distinct name. That keeps several rendered clips off the same source media file from clobbering one another in a shared directory. A “uniquely” named clip tacks the track and clip number — pinpointing the clip’s slot in the active session — onto the clip name. A clip tied to a media file called “DropThatThingCU.mov,” cut in as the twenty-fifth clip on track V2, renders out as “DropThatThingCU_V2-0025.mov.” Turning it on also unveils two further options.

Use unique filename prefix/Use unique filename suffix: (Shown once Use Unique Filenames is active) Radio buttons govern whether the unique identifier lands at a clip’s start or finish. Pick Prefix and you’d get “V2-0025 \_DropThatThingCU.mov,” while Suffix would render as “DropThatThingCU_V2-0025.mov.”

- Add source frame count to filename: (Active as Individual Clips render, provided Filename uses sits on Custom name) Switched on, each clip’s source frame number gets stuck onto the end of the rendered file name — yet another safeguard against custom-named rendered clips overwriting each other.
- Use filename digits: Sets how many digits to use when rendering an image sequence, though the count you pick carries over to any media format. It’s handy when your output feeds an application with strict image sequence numbering rules. The default is eight digits.
- Each clips starts at frame: (When rendering Individual Clips) This allows timecode in the header and a frame count in the filename of the image sequences, well suited to VFX workflows.
- Start timeline timecode at: (When rendering Single Clip) Available only when you render clips in Single clip order, this names the timecode written into the media DaVinci Resolve outputs. With DPX files, the timecode goes into the header data and is at the same time turned into a frame count slotted into each frame file’s name, giving a logical tally of the frame numbers. For other media formats the timecode lands in the appropriate metadata container. Custom start times can prove useful — kicking off each reel of a project at a set value, for instance, according to the standards your shop follows.
- Place clips in separate folders: (When rendering Individual Clips) Comes in handy for holding onto the filenames of your output when clips drawn from one source media file would otherwise overwrite each other. It also sees frequent use rendering VFX shots bound for further post-production, letting the VFX department spot clips fast and parcel out the work.
- Preserve Source directory levels: (When rendering Individual Clips) Keeps a depth you choose of the original directory structure behind a clip’s matching source media file, rebuilding it as new output files render. Your chosen number governs how many subdirectory levels DaVinci Resolve auto-creates inside the active “Render job to” directory to echo the path the source files use. The default is 0, which creates no matching subdirectories.

After Head/From Tail: As you decide how many directory levels of each clip’s file path to keep (via the “Preserve x levels” parameter), one of these buttons marks whether that level count is reckoned from the head or the tail of each media file path. Preserved Path: Gives you a preview of the preserved path you’ve built so you can confirm it’s right.

- File Subfolder: (Only appears in Additional Output panels) Names a subdirectory to render the output media files into. Where that subdirectory is missing, a new one bearing the name is built inside the active “Render job to” directory.
- Use commercial workflow: (When rendering Individual Clips) Auto-renders every version riding on each clip in the session, leaving out any version marked with the “Render Disabled” flag in the Version submenu for that clip in the Timeline. You’d typically reach for it after grading several versions of a clip for VFX work and wanting each grade delivered as its own media file. It also serves when rendering programs for commercial broadcast where each scene carries two or more grade versions. Switch it on and alternate methods for outputting each rendered media file kick in, while four extra settings appear.

Alternative pass offset: Spaces out the timecode values stamped into each version of a clip by an offset. Say the default version timecode is 01:00:20:00 and you set a 10 minute offset in the Alternative Pass Offset timecode entry: the clip’s second graded version then begins at 01:10:20:00, the third at 01:20:20:00, and onward until every version renders. The offset value is yours to pick, the aim being to let editors and VFX artists locate each grade’s versions with ease. Hand the clips to a finishing artist who knows the passes sit 10 minutes apart, and switching clip version is just a matter of adding 10 minutes to the referenced timecode. The next three options streamline things further by sorting separate source reels into separate folders. Place reels in separate folders: Drops all media output under a given reel name into its corresponding folder automatically.

Place clips in separate folders: Files alternate grades of clips into separate folders on its own. Use version name for folders: Names each folder after the version while the Commercial Workflow option is active.
