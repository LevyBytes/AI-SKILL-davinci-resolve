# Importing And Organizing Media In The Cut Page (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

On its own, DaVinci Resolve works to track how the clips in your project relate

to the source media for them sitting on disk. Should the source media tied to clips

in your project go missing for any reason — usually because it was moved — DaVinci Resolve offers a handful of ways to relink those clips back in the Media Pool. What this section covers is two of those relinking approaches,

the “Relink Media” command and the “Relink selected clips” command.

To read up on the other ways of conforming projects and relinking media, turn to Chapter 56, “Conforming and Relinking Clips.”

### Relink Media

Whenever DaVinci Resolve can’t locate your media, a Relink Media icon turns orange within the Media Pools of both the Cut page and the Edit page.

The Relink Media icon that appears for unlinked media Click this icon and a dialog box opens listing the volumes the missing files first lived on. With that detail in hand, you can hunt the media down on your file system, locate the particular hard drive, or check with a client about whether they handed you the media off this volume. Hitting the Locate button reconnects the missing clips to whatever new file location you point it at. Should the quick search the Locate buttons kick off fail to turn up media you’re sure is present, you can launch a thorough deep disk search for it by clicking the Disk Search button.

The Relink Media dialog listing the volume names that the missing clips came from

### Relink Selected Clips

Aptly titled, the “Relink selected clips” command is the most adaptable way to relink your project’s clips against clips in any directory you pick, leaning on file name and timecode as the main means of reestablishing the tie between each clip and the media file matching it on disk. Here is how to relink selected clips, or the clips inside a selected bin: 1 Do one of the following:

- Within the Media Pool browser, pick one or more clips for relinking; then, right-clicking either one of those selected clips or the selected bin, choose “Relink Selected Clips” from the contextual menu.
- From the Media Pool bin drop-down menu, pick a bin whose clips you want relinked; then, right-clicking that selected bin, choose “Relink Clips for Selected Bin” from the contextual menu.

2 Once the Relink File dialog opens, pick a volume and directory to search for the files you’re relinking to, then click OK. DaVinci Resolve sets out to locate every clip whose file name matches inside the subdirectories of the directory you picked, and to keep this fast it relies on the original file paths of the clips being relinked. Because it checks the directories the clips first came from to begin with, relinking can go pretty quickly. 3 Should any clips not turn up via the approach in step 2, a second dialog gives you the chance to run a “deep search.” Click Yes and DaVinci Resolve hunts for each clip within every subdirectory of the directory you picked back in step 2. That can take a good deal longer, yet it ought to succeed completely as long as the media you need sits somewhere inside the chosen directory structure. 4 Should there still be other clips that couldn’t be found, you’re given the choice of pointing at a different directory to keep searching, or quitting.

### Voiceover Tool

Built into the Cut page of DaVinci Resolve is a purpose-made voiceover and teleprompter interface you reach right in the Viewer by clicking the Voiceover icon. With the Voiceover tool, laying down precisely timed scripts straight into the Cut page timeline is easy. You can even bring in Voice Isolation and the Dialog Leveler as you go for strong results, even when the microphones and recording surroundings are subpar.

### The Voiceover icon (red) opens the Voiceover toolset

Laying down a VO audio track straight onto the Cut Page timeline by way of the Voiceover tool

### Using Voiceover on the Cut Page

At the simplest level, a recording can be “punched in” with nothing more than a microphone and an In point, though the Voiceover tool carries plenty of features that make the whole thing more exact and repeatable, teleprompter support and AI-based audio tools among them. What follows is a sample setup that gets the most out of the Voiceover features on the Cut page. 1 Hook an external microphone and headphones up to your computer, then prepare a plain text (.txt) script for the VO. 2 Hit the Voiceover tool icon in the Viewer. 3 Within the Voiceover settings, choose your microphone interface. 4 Choose the Audio Track you’d like the voiceover clip recorded onto. The Cut page makes a fresh track named VO by default. 5 More options let you handle countdowns and choose which file folder holds your saved voice recordings.

6 Work out where along the timeline this voiceover belongs. In a basic setup, simply drop the playhead at the spot where you want the VO to begin. You can also place an In point on the timeline that acts as a cue point the Voiceover tool comes back to on later takes. 7 You may optionally switch on Voice Isolation and Dialog Leveler when recording in a poor audio environment (say, straight into your laptop microphone in an office) so your audio gets cleaned up as it’s captured. 8 Click the Record button to launch the teleprompter and start recording onto the chosen track. The interface goes red to signal you’re “on the air.” 9 Click Stop to finish the recording. The playhead snaps back to your start position on its own, so you can play your new voiceover right there. 10 To have another go, hit the Cue button to jump back automatically to the In point, then press Record once more for a new take. That new voiceover overwrites the previous take on the timeline automatically. Even so, every one of your earlier VO takes remains saved in the Media Pool if you’d like to return to them.

### Using the Prompter

CUT A Prompter toolset is built into the Voiceover tool, letting you bring in a text (.txt) script; as you record, the text rolls across the picture so your voiceover stays on cue and well placed.

### The built-in Prompter in the Voiceover tool

To use the Prompter while recording voice over: 1 Open and configure the Voice Over tool as laid out above. 2 Within the Script Settings, switch on the Prompter Overlay and load the Script File. Further settings cover how the script gets formatted in the Viewer. 3 You can drop In and Out points on the timeline to define the VO range for the teleprompter. From there the teleprompter sets its own speed, beginning its scroll at the In point and finishing at the Out point. Should no In or Out points be set, by default the script’s scroll length spans the whole timeline. 4 As you press record, the text rolls across the image while your voice over is captured.

### Voiceover Settings

A number of optional settings on the Voiceover tool let you fine-tune your VO session.

A click on the Voiceover icon (red) brings up the Voiceover toolset along the bottom of the Viewer

### Voiceover Settings

- Audio Input: Pick which computer interface your microphone plugs into.
- Record Track: Pick which audio track on the timeline the VO records onto. The Cut page makes a fresh track named VO by default, though this setting lets you redirect it to a different track yourself.
- Monitoring

Timeline & Microphone: Lets the timeline audio and your voice input both reach your ears

as you’re recording.

Timeline Audio Only: Routes just the timeline audio to your ears as you’re recording.

Microphone Audio Only: Routes only your voice input to your ears and silences the timeline as you’re recording.

Mute Monitoring When Recording: Silences every bit of audio playback as you record. Handy for sidestepping audio feedback in some headphone-less recording setups.

- No Countdown: No visual countdown shows up — once you hit Record, just start talking.
- 3 Secs Countdown: Shows a three second visual countdown on the viewer ahead of the

recording, leaving you a brief moment to get set first.

- 5 Secs Countdown: Drops a five second visual countdown onto the viewer ahead of the recording, giving you a moment to get set first.
- Voiceover Recording File Location: Pick where your new audio files get saved.

### Script Settings

- Enable Prompter Overlay: Switches the loaded script’s text overlay on or off.
- Load Script File: Brings up a file selector for picking a text file to load into the prompter.
- Clear Script File: Takes the text file back out of the prompter.
- Font Size: Lets you set the font size of the on screen text.
- Line Spacing: Lets you set the line spacing of the on screen text.
- Side Margin: Lets you set how wide a margin the on screen text uses.
- Background Opacity: Lets you set how transparent the on screen text is.

Audio Meters: A small bank of audio meters reports your microphone’s audio levels. Input Monitoring: Click the headphone icon to switch between hearing your microphone input as you record and muting it.

Cue: Snaps the playhead back to the initial record In point.

Record: Begins recording audio onto the timeline. Stop: Halts the audio recording. Voice Isolation: Switches on the Voice Isolation effect while you record to cut down background noise. Dialog Leveler: Switches on the Dialog Leveler effect while you record to hold your track at a steady volume. Stereo Fixer: Switches on the Stereo Fixer effect while you record to clear up the usual channel errors that crop up when converting between mono and stereo sources.

### ATEM Switcher Integration

When you’ve captured a multi-camera event on the ATEM Mini Pro ISO or ATEM Mini Extreme ISO, the whole project can be brought across into DaVinci Resolve. An ATEM project carries the master program clip, plus the “ISO” (isolated) clips from each separate camera, along with the audio captured for every camera angle. Every transition, all the timecode, and the camera number metadata come over, along with whatever graphics had been kept in the ATEM’s Media Pool. With the project loaded, you can pick your multi-camera edit right back up in the Cut page. Pairing this opening live recording with later post-production editing is a workflow commonly known as “Live to Tape.” Live to Tape hands you all the spontaneity, verisimilitude, and quick turnaround that come with live production, while adding the freedom to insert or cut sections afterward and reshape the program’s editorial flow. Live to Tape also lets you patch up minor slip-ups, like swapping in a better camera angle or refreshing a title or graphic. That flexibility is why Live to Tape is the go-to method for shooting nearly every broadcast network game show, current events show, and sitcom. In short, any multicamera production whose core purpose doesn’t hinge on being live in real time (the way news or sports does) gets shot Live to Tape instead. Everything the Live to Tape workflow calls for is supplied by the ATEM Mini Pro ISO and ATEM Mini Extreme ISO:

- A program master clip shot live that holds all the mixed camera angles, audio, transitions, and so on, running from the show’s opening to its close, kept for reference.
- A separate ISO recording from each camera that fed the program master clip. An ISO is an isolated (ISO) camera recording covering the whole show from that single camera’s point of view, start to finish and uninterrupted.
- A timeline of the live-recorded show marking where every camera angle got switched, which transitions were applied, and which graphics took part.

NOTE: Only on MacOS can you get the ATEM’s live webcam view.

### Importing ATEM Mini Pro ISO Projects

Bringing in an ATEM project basically reconstructs the master program clip as a timeline within DaVinci Resolve out of the camera ISOs, transitions, and graphics. The resulting timeline lines up with the master program clip in every respect, only it’s assembled from the original source materials rather than delivered as one compressed video file. Consult your ATEM’s own documentation on configuring ISO recording, but one key setting is making sure the “ISO Record All Inputs” setting is checked in the ATEM software control before shooting begins. Here is how to import an ATEM Mini Pro ISO Project: 1 Ahead of shooting, confirm that, within the ATEM software control, the “ISO Record All Inputs” setting is turned on. 2 Now record your show on the ATEM device and take note of where the project’s folder lives. 3 Select File > Import Project. 4 In the file browser, choose the DaVinci Resolve Project file (.drp) sitting in the ATEM project folder. 5 Click on the Open button.

An ATEM Mini Pro project opened in the Cut page Sync bin

### Relinking Blackmagic Camera Masters to ATEM ISOs

The ATEM captures every camera’s ISO as an H.264 HD video stream, whose resolution or quality may fall short for certain needs. You can swap your ATEM camera ISOs over to the original camera recordings made on a Blackmagic Camera in an instant instead. This workflow unlocks the top visual quality of Blackmagic RAW plus the option to deliver at higher resolutions (4K or UHD, for example) beyond what the ATEM handles internally. In effect, the ATEM can point to an extra set of higher-quality ISOs recorded inside the cameras rather than the ones from the ATEM itself. The feature works only with Blackmagic Cameras. This workflow adds one more step, which is making certain each camera has enough recording space attached to capture the entire show. Consult your ATEM’s own documentation on configuring ISO recording and camera control, but one key setting is making sure both the “ISO Record All Inputs” and the “Record in All Cameras” settings are checked in the ATEM software control before shooting begins.

Here is how to relink to Blackmagic Camera masters from ATEM ISO recordings: 1 Ahead of shooting, confirm within the ATEM software control that the “Record in All Cameras” setting is on. 2 Ahead of shooting as well, confirm that the same control has the “ISO Record All Inputs” setting on. 3 Now record your show on the ATEM device and take note of where the project’s folder lives. 4 Copy every resulting camera master off each camera’s memory card into the ATEM project’s “Video ISO Files” folder, then import the project into DaVinci Resolve. 5 DaVinci Resolve makes a separate Blackmagic RAW folder in your project on its own and shifts all the camera masters there. 6 Through the menu Timeline > Switch to Camera Originals, you can flip in an instant between pointing at the ATEM H.264 ISOs and pointing at the Blackmagic Camera masters.

After your project comes into DaVinci Resolve successfully, you can cut it with the array of dedicated Multicam editing tools the Cut page provides, the Sync Bin, Live Overwrite, and the DaVinci Resolve Speed Editor included.

To read up on putting these tools to work, turn to Chapter 28, “Fast Editing in the Cut Page.”
