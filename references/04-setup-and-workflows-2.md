# Data Burn In, Frame Io And Dropbox Replay Integration

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

## Overview

Covers: Data Burn-In; Frame.io and Dropbox Replay Integration.

## Data Burn-In

### Data Burn-In

Working with the Data Burn-In window, which every page in DaVinci Resolve makes available, is the subject of this chapter.

Through the Data Burn-In window you can show chosen metadata as a timeline-wide “window burn” laid over the picture in the Viewer. That window burn becomes part of the files rendered out on the Deliver page, and it also goes out to video — whether for viewing on an external display or for sending to tape. To open the Burn-In window, choose Workspace > Data Burn-In.

### Data Burn-In window

Window burns have long served as a handy reference when building offline media you’ll need to keep tabs on down the line. Yet the Data Burn window goes far beyond that. To name a few uses, it can watermark review files you’d rather not see distributed by mistake — whether through custom text or alpha-channel graphics — it can paste graphical logos or “bugs” onto programs headed for broadcast (once more, alpha-channel graphics are an option), it can overlay your own reference guidelines of one kind or another atop the images under watch, or it can simply put timecode or clip names on screen for a while so you have something to reference on your monitor as you edit, mix, or screen graded dailies alongside a client.

Viewer displaying record timecode, source timecode, and source clip name

### Project vs. Clip Mode

A pair of buttons up top in the Data Burn window decides whether you’re editing a single batch of burned-in metadata shown across the whole Timeline, or editing burned-in metadata one clip at a time. The two can run together: you might hold timeline-wide window burn settings while keeping separate clip-specific window burn settings for a few clips inside that same timeline. During rendering on the Delivery page, window burns get applied whether you render timelines as separate source clips or render everything as a single clip.

A pair of distinct panels handle adjustments for project-wide window burns alongside clip-specific window burns

### Setting Up Burned-In Metadata

Arranging different clip and project metadata for output as a window burn is straightforward. Here’s how to set one up: 1 Choose Workspace > Data Burn-In. 2 Up at the top of the Data Burn-In window, click either Project or Clip. 3 Tick the checkboxes beside whatever metadata items you wish to show inside the “Add to Video Output” column. Fuller detail on the items offered comes later in this chapter. That first metadata item sits centered close to the frame’s bottom, just over Action Safe. Every further metadata item you switch on appears stacked above the ones already shown, no matter where it falls within the “Add to Video Output” list. 4 Click whichever enabled metadata item in the list you want highlighted black, then tweak that item’s Custom Output parameters off to the right. Fuller detail on the parameters offered comes later in this chapter.

To reset the current window burn setup: Press the Reset button sitting beside the Option drop-down menu, which clears the Data Burn window’s current mode.

### Saving and Loading Burn-In Presets

When certain metadata combinations come up often and you flip between them, each combination can be stored as a preset to reuse later. Saving one as a burn-in preset goes: 1 Open the Option menu and pick Save As New Preset. 2 In the Burn In Preset dialog that pops up, key a name, then click OK. Your new preset now sits among the saved presets listed under the Option menu. Removing a burn-in preset goes: 1 From the Option menu, pick a preset. 2 Open the Option menu once more and pick Delete. 3 You’ll get a dialogue box prompting you to confirm the deletion. Changing a burn-in preset goes: 1 From the Option menu, pick a preset. 2 Adjust it as you see fit. 3 Open the Option menu and pick Update.

### Data Burn-In Metadata

Running down the far-left column of the Data Burn-In window is a roster of every option you can lay onto the video output as a window burn. A checkbox beside each option toggles it on or off. The Option drop-down also lets you decide whether the item name prints as a prefix ahead of the burn-in data. NOTE: When a pair of clips overlaps on the Timeline, the metadata shown in the window burn belongs to whichever clip is currently visible in the Viewer.

- Record Timecode: Timecode measured against the Timeline, configured under the Conform Options section within the General Options panel of the Project Settings.
- Record Frame Number: How many frames sit between this point and the Timeline’s opening frame.
- Source Timecode: The individual timecode belonging to each clip.
- Source Frame Number: How many frames sit between this point and the clip’s opening frame.
- Record TC & Frame Num: A single line holding both metadata options together.
- Source TC & Frame Num: A single line holding both metadata options together.
- Source & Record TC: A single line holding both metadata options together.
- Feet + Frames 35mm: Shows a Feet + Frames translation of the program’s record timecode,

worked out for 35mm film.

- Feet + Frames 16mm: Shows a Feet + Frames translation of the program’s record timecode,

worked out for 16mm film.

- Audio Timecode: The timecode belonging to the clip’s audio track.
- Keycode: Sometimes called edge-code, these are the identification codes printed along the edge of film stocks, supplying a fixed reference that maps which digital frames line up with which film frames.
- Source File Name: The complete file path — file name included — of the media file tied to the present clip.
- Record File Name: Whatever file name is set within the Render Settings list over on the Deliver page.
- Source Clip Name: The media file’s file name that’s tied to the present clip,

minus the file path.

- Synced Audio File Name: The file name belonging to the audio clip synced against this clip.
- Synced Audio Timecode: The timecode belonging to the audio clip synced against this clip.
- Custom Text1: A line of text you key into the Text field within the Custom Output parameters.

Whatever characters you wish are fair game. As you edit any of the three custom text fields on offer, you can drop in “metadata variables” — graphical tags you add to surface clip metadata. As an example, dropping in the matching metadata variable tags %scene*%shot*%take makes the custom text read “12_A_3” when the metadata happens to be “scene 12,” “shot A,” “take 3.” For a deeper look at using variables, along with the full roster of variables that DaVinci Resolve provides, see Chapter 16, “Using Variables and Keywords.”

- Custom Text2: A second line of text open to customization.
- Custom Text3: A third line of text open to customization.
- Logo1: Lets you lay a graphic over the picture at a position you choose. Among the

graphics formats it accepts are PNG, TGA, TIF, BMP, and JPG. For transparency within logos, alpha channels work too.

- Logo2: Lets you lay a second graphic over the picture.
- Logo3: Lets you lay a third graphic over the picture.
- Reel Name: Whatever reel number is presently assigned to the current clip.
- Shot: Shot metadata, should a camera have written it to the file, or should it have been keyed into the Metadata Editor over on the Media page.
- Scene: Scene metadata, should a camera have written it to the file, or should it have been keyed into the Metadata Editor over on the Media page.
- Take: Take metadata, should a camera have written it to the file, or should it have been keyed into the Metadata Editor over on the Media page.
- Angle: Angle metadata, should a camera have written it to the file, or should it have been keyed into the Metadata Editor over on the Media page.
- Day: Day metadata, should a camera have written it to the file, or should it have been keyed into the Metadata Editor over on the Media page.
- Date: Date metadata, should a camera have written it to the file, or should it have been keyed into the Metadata Editor over on the Media page.
- Good Take: Maps to Good Take metadata, should a camera have written it to the file, or should it have been keyed into the Metadata Editor over on the Media page.
- Camera: Maps to the Camera metadata, should a camera have written it to the file, or should it have been keyed into the Metadata Editor over on the Media page.
- Roll/Card: Maps to the Roll/Card metadata, should a camera have written it to the file, or should it have been keyed into the Metadata Editor over on the Media page.
- Clip Flags: Sends out whatever colored flags are attached to the clip.
- Clip Color: Sends out whatever color is attached to the clip.

### Custom Output Options

Using the parameters within the Custom Output panel, you can adjust the appearance, placement, and at times the content, of the chosen metadata item. Each metadata item carries its own adjustable Pan and Tilt.

- Display During First x frames: Switching this checkbox on lets you set a frame count over which the present metadata item shows before it dissolves out across one second. Once enabled, the present metadata item cuts on screen as each fresh clip starts, holds on screen for the span you set, and then dissolves away.
- Display During Last x frames: Switching this checkbox on lets you set a frame count, just ahead of every clip’s end, across which the present metadata item shows up on screen after fading in over one second, then cuts away as the clip ends.
- Font: Starts out as Courier, though you may pick any font present on your system.
- Size: Starts out at 48, though you may pick standard increments from 6 to 72.
- Alignment: Starts out as Center. Left is the sole alternative.
- Font (color): Starts out white, though a spread of predefined colors is available from this drop-down menu.
- Background: Starts out black, though the visible color shifts with the Opacity setting. For a louder look, a spread of predefined colors is available from this drop-down menu.
- Text Opacity: Starts out at 1.00. Lets you set how transparent the burned-in metadata’s text is.
- Background Opacity: Starts out at 1.00. Lets you set how transparent the burned-in metadata’s background color is.
- X-Y Position: Lets you shift the present metadata item’s horizontal and vertical placement. By default the horizontal value lands at the frame’s center, measured against the current project’s frame size. That first metadata item sits centered vertically close to the frame’s bottom, just over Action Safe. Each later metadata item you enable drops in automatically above the earlier metadata item, no matter its sequence within the “Add to Video Output” list.
- Text: (shown only when one of the Custom Text options carries a check) A text field where you key in custom text to appear as one of three available custom text items.
- Logo: (only if one of the Logo options is checked) A field showing the file path of whichever graphic is presently selected for display as one of the three available Logo graphics. The graphics formats it accepts include PNG, TGA, TIF, BMP, and JPG. For transparency within logos, alpha channels are supported as well.
- Import File button: (only when one of the Logo options carries a check) Lets you pick a graphics file to serve as a logo.

### Gang Rendered Text Styles

Whether each metadata item can be styled on its own hinges on whether the Gang Render Text Styles option carries a check within the Data Burn-In window’s Option menu. Switched on, every text metadata item shares one font, size, color, background, justification, and opacity. Switched off, each metadata item may carry its own settings.

### Prefix Render Text

A further option inside the Data Burn-In window’s Option menu lets you switch the prefixes, or headers, on or off across all metadata flagged for burning in.

## Frame.io and Dropbox Replay Integration

### Frame.io and Dropbox Replay Integration

Built specifically for the postproduction trade, advanced integrations tie DaVinci Resolve into the Frame.io and Dropbox Replay video review and collaboration services.

### Enabling Frame.io Integration in Preferences

Under the System tab of the DaVinci Resolve Preferences, an Internet Accounts panel lets you log in to your Frame.io account and name a local cache location where media syncing with Frame.io lands. Activating Frame.io integration calls for your login name and password, yet after they’re entered, DaVinci Resolve logs in on its own each time DaVinci Resolve launches.

Within the DaVinci Resolve Preferences window, the System tab’s Internet Accounts panel (its login deliberately obscured) That local cache location holds the clips you bring into a DaVinci Resolve project off the Frame.io volume found in the Media Storage panel of the Media page.

### Deliver and Upload to Frame.io

Sitting at the top of the Deliver page’s Render Settings panel, a Frame.io preset lets you render a program and push it up for review. Every option across the Render Settings panel refreshes to show controls fit for this purpose. Pick the Frame.io preset and the Location field becomes an Upload To field, while the Browse button lets you select the project and folder path that the exported result uploads to.

### Choosing the Frame.io preset

Choosing a Frame.io account to deliver a program to

Exporting to Frame.io trims the selectable entries in the Resolution, Format, Video Codec, and Type pop-up menus down to those best matched for Frame.io file sharing. Set the export options you want, then press the Add to Render Queue button to drop this job into the Render Queue just as you would for any other export. After that job renders, it moves on by itself to upload to Frame. io, and the job listing shows an upload percentage indicator marking how far the upload has gotten. Upon completion, the job reads “Upload completed.”

Inside the Render Queue, the job reports what percentage of the file has gone up so far Because this upload runs in the background, you can keep busy with other tasks in DaVinci Resolve as the file goes up. To check how long the upload needs from any other page, choose Workspace > Background Activity and open the Background Activity window.

### Frame.io Comments Sync with Timeline Markers

Render a timeline straight to Frame.io and that timeline links automatically to the movie pushed up to Frame.io, so every comment, “Like,” and graphical annotation (drawings and arrows) that reviewers add online through the Frame.io interface syncs automatically to Frame.io markers on your timeline (provided your computer holds an active internet connection). Frame.io markers stand apart from all the other markers and may be shown, hidden, or deleted on their own. Drawings and arrows out of Frame.io get translated into their matching DaVinci Resolve annotation graphics so they’re visible in DaVinci Resolve.

On your DaVinci Resolve Timeline, comments and graphical annotations out of Frame.io show up as markers carrying their matching overlays Working With Frame.io Markers Double-click any Frame.io marker on the Timeline to open a dialog where you can fire back replies to the comments living on Frame.io, letting editors answer commenters straight away. You may likewise drop Frame.io markers onto the Timeline so they sync automatically back to Frame. io, granting you the means to return your own comments to commenters (be kind). Delete one or more Frame.io markers on the DaVinci Resolve timeline and those same markers vanish in Frame.io too. The Mark > Delete All Markers > Frame.io command falls under this. There’s no undoing it.

An editor holding a one-sided conversation through the Frame.io comment dialog surfaced upon opening a Frame.io marker

### Frame.io Marker Navigation

While inside the comment dialog of a Frame.io marker, you can step through only the markers born in Frame.io, leaning on the Previous Marker (Shift-UpArrow) and Next Marker (Shift-DownArrow) commands. That lets you leap straight from one Frame.io comment to the next without trudging through every in-between marker or double-clicking each Frame.io marker on its own to reply. Frame.io interoperability is a Studio Only feature.

### Importing Media from Frame.io

Within the Media Storage panel of the Media page, a Frame.io volume turns up that opens access to the media your Frame.io account holds. Inside that Frame.io volume, a top-level directory stands for your account directory, and beneath it every project you’ve built in Frame.io shows up as a sub-directory.

Reaching a Frame.io account’s directories by way of the Media Storage browser Whatever media files Media Storage can reach may be brought into the Media Pool through the usual means. After it joins the Media Pool, that media file downloads quietly in the background to the named local cache location, yet it’s ready at once over your internet link before the download wraps, letting you dive in right away. To check how long the download needs, choose Workspace > Background Activity and open the Background Activity window.

Through the Background Activity window you can watch whatever the background is doing as you keep working

### Linking Media Pool Clips and Timelines with Frame.io Clips

Frame.io reach within the Media Storage panel of the Media page can also be used to tie clips or timelines to media you’ve already pushed up to your Frame.io account. Simply find and select a Frame. io clip inside Media Storage, then right-click the clip or timeline in the Media Pool you’d like it tied to and pick Link to Frame.io Media off the contextual menu. Once you’ve tied a Frame.io clip to a timeline, comments left on that Frame.io clip surface on the linked timeline as Frame.io markers, exactly as though you had exported that timeline straight to Frame.io.

### Enabling Dropbox Replay Integration in Preferences

Under the System tab of the DaVinci Resolve Preferences, an Internet Accounts panel lets you log in to your Dropbox account. Activating Dropbox integration calls for your login name and password, yet after they’re entered, DaVinci Resolve logs in on its own each time DaVinci Resolve launches.

The Dropbox Login window, sitting inside the Internet Accounts panel under the System tab within the DaVinci Resolve Preferences window.

### Deliver and Upload to Dropbox Replay

Sitting at the top of the Deliver page’s Render Settings panel, a Dropbox Replay preset lets you render a program and push it up for review. Every option across the Render Settings panel refreshes to show controls fit for this purpose. NOTE: The Dropbox Replay Render settings stand apart from the ordinary Dropbox Render settings, and this particular set of presets is the one you must use to hook into Dropbox Replay.

The Dropbox Replay Render settings (highlighted); bear in mind they aren’t the same as the ordinary Dropbox Render settings sitting over to the left. Exporting to Dropbox Replay trims the selectable entries in the Resolution, Format, Video Codec, and Audio pop-up menus down to those best matched for Dropbox Replay. Set the export options you want, then press the Add to Render Queue button to drop this job into the Render Queue just as you would for any other export. After that job renders, it moves on by itself to upload to Dropbox Replay, and the job listing shows an upload percentage indicator marking how far the upload has gotten. Upon completion, the job reads “Upload completed.” Within the Render Queue, the listing reports the file’s upload percentage and signals you once it has wrapped. Because this upload runs in the background, you can keep busy with other tasks in DaVinci Resolve as the file goes up. To check how long the upload needs from any other page, choose Workspace > Background Activity and open the Background Activity window.

### Unlinking a Timeline from Dropbox Replay

Should you want a particular timeline to stop using Dropbox Relay integration, just right-click on the Timeline and pick Unlink from Dropbox Media off the contextual menu.

### Upload New Versions to Dropbox Replay

The versioning features within Dropbox Replay are supported by DaVinci Resolve. This makes it simple for the Replay user to comment on and flip between the various versions of one clip. After the original timeline is rendered and pushed up to Dropbox via the Replay preset on the Deliver page, an extra checkbox surfaces within the preset, named “Upload as new version.” With that box ticked, every later render of this timeline lands automatically on the clip’s version stack inside Dropbox Replay. Within the Replay interface, the newest version stays the clip’s default every time.

### Dropbox Replay Comments Sync with Timeline Markers

Render a timeline straight to Dropbox Replay and that timeline links automatically to the movie pushed up to Dropbox Replay, so every comment and graphical annotation (drawings and arrows) that reviewers add online through the Dropbox Replay interface syncs automatically to Dropbox markers on your timeline (provided your computer holds an active internet connection). Dropbox markers stand apart from all the other markers and may be shown, hidden, or deleted on their own. Drawings and arrows out of Dropbox Replay get translated into their matching DaVinci Resolve annotation graphics so they’re visible in DaVinci Resolve.

On your DaVinci Resolve timeline, comments and graphical annotations out of Dropbox Replay surface as markers bearing their matching overlays.

### Working With Dropbox Markers

Double-click any Dropbox marker on the Timeline to open a dialog where you can fire back replies to the comments living on Dropbox Replay, letting editors answer commenters straight away. The Dropbox Replay comment dialog surfaced upon opening a Dropbox marker You may likewise drop Dropbox markers onto the Timeline so they sync automatically back to Dropbox Replay, granting you the means to return your own comments to commenters (be kind). Delete one or more Dropbox markers on the DaVinci Resolve timeline and those same markers vanish in Dropbox Replay too. The Mark > Delete All Markers > Dropbox command falls under this. There’s no undoing it Dropbox Marker Navigation While inside the comment dialog of a Dropbox marker, you can step through only the markers born in Dropbox Replay, leaning on the Previous Marker (Shift-UpArrow) and Next Marker (Shift-DownArrow) commands. That lets you leap straight from one Dropbox Replay comment to the next without trudging through every in-between marker or double-clicking each Dropbox marker on its own to reply.
