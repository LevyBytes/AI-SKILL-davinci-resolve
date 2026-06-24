# Editing Basics In The Fairlight Page (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Whenever a workflow calls for writing clips out of the Timeline into external files while still giving you broad control over how those files are altered, reach for the Export Audio Files command. To export clips to external files: 1 Pick one or more clips within the Timeline. 2 Right-click the files you've selected and pick Export Audio Files from the contextual menu. 3 As the Export Audio Files dialog comes up, set these: a) Click Browse to point at where the exported audio files should be saved. b) (Optional) Type in a tag plus one of the assorted Name options. c) Set a File Format, Sample Rate, and Bit Depth for what you're exporting. d) Set a Channel Format — either Multi-Mono or Interleaved — for the exported files. e) Set a Source of Individual Clips or Consolidated Clips; a dropdown menu then pins down the ranges, covering the whole timeline, a selected range, or only the selected clips. f) Checkboxes let you narrow things further to just the chosen tracks, fold in hidden tracks, and pad out to frame boundaries. g) On export you're free to bundle in several attributes: Clip Level, Clip Fades, Clip EQ and FX, plus Clip iXML. h) Those exported files can be normalized to preset target levels and target loudness figures using every one of the standards the Fairlight page makes available.

The dialog where you pick the settings for writing clips out to files 4 Click Export. The audio files you selected get written to the spot you picked.

### Sample Editing

On the Fairlight page timeline you can magnify audio clips a long way in, far enough that the separate samples making up each clip's audio waveform become visible. Once you've zoomed deeply enough, those samples show up as control points.

Zooming deeply enough surfaces the separate samples of an audio clip as control points You're able to edit these control points non-destructively to wipe out clicks and pops and to apply other repairs to troublesome audio clips. Ways to edit audio samples:

- To see the editable audio samples: Magnify fully into an audio clip until the sample control points appear, whether by way of Command-Plus or Command-Minus, the scroll wheel on your pointing device, or by pressing and holding the ZOOM button on your Fairlight editing panel while spinning the JOG/EDITING wheel.
- To edit a single audio sample: Grab that audio sample and drag it up or down to alter how tall it is.
- To edit a section of samples: Drag horizontally to the left or right across whichever samples you mean to edit, “redrawing” the waveform however you please.
- To reset all edited samples to their original state: Right-click a clip whose samples you've edited and pick Reset Edited Samples from the contextual menu.

Black points mark the earlier levels wherever samples in a clip have been edited Editing samples is reversible, the same as any other editing step, since the edited sample points sit non-destructively inside the DaVinci Resolve project.

### Waveform Zero Crossing Indicator

Every waveform carries a zero crossing indicator line. Because a waveform is a visual depiction of sound that keeps swinging from positive to negative, the zero crossing point marks the level where that swing passes through. As you magnify a waveform down to the sample level, it shows the zero crossing line so you can edit with precision. That zero crossing comes in handy during audio editing, since making clean cuts right at the zero crossing keeps you from triggering clicks or pops. When two audio clips crossfade, the software automatically pulls both ends of the fade to the zero crossing.

Within the waveform indicator, the middle line represents the zero crossing.

### Voice Convert (Studio Version Only)

DaVinci Resolve ships with a remarkably advanced AI-powered voice conversion feature that essentially lets you trade one speaking voice for a different one. Where you'd apply this tool ranges widely and is even a touch contentious, yet the Voice Convert toolset can prove enormously useful in post production. With it you take a generated voice model that DaVinci Resolve has captured and “drive” that voice model off the back of a separate voice recording. At the simple end, you might swap your own voiceover tracks for a voice with greater depth and authority, or even flip the gender of your own voice should that suit the material better. Maybe you recorded in a noisy room and would rather build a clean rendition using your own voice as the model, standing in for your original noisy tracks. At the more involved end, you can train a voice convert model of your own on the vocal patterns of your actor, then use it to alter and replace their earlier voiceover without dragging them back into the booth. Ultimately, you can even shift an actor's voice entirely to a wholly different one while holding flawless sync against the picture. The original's inflection, pitch swings, and emotion all carry over; it simply sounds like another person. It goes without saying that wielding such a capable tool demands a measure of accountability from whoever uses it. Privacy, copyright, and union laws and regulations all remain unsettled right now where AI-generated content is concerned, so you must tread carefully through the ethics of using it professionally.

### The Voice Convert tool

NOTE: Voice Convert leans heavily on your processor and won't switch on until your system has at least 8GB of video RAM, a threshold meant to stave off crashes and instability. Even on a powerful machine, building a Voice Model ties up CPU and GPU resources intensively for a long stretch, so juggling other work while it runs can be tough.

### Using Voice Convert

As with the bulk of DaVinci Resolve's AI tools, Voice Convert is straightforward to operate, since the voice model takes care of all the intricate processing behind it. To use Voice Convert to change one voice to another: 1 Drop the clip or clips whose voice you'd like to change onto the timeline and select them. 2 Right-click the clip and pick Voice Convert off the context menu, or go to Clip > AI Tools > Voice Convert in the main menu. 3 Pick the track where the new audio should land (this can include overwriting the original). 4 Pick the file name the new audio ought to carry. 5 Pick the Voice Model you'd like applied to the new audio (custom voice models of your own are possible, as described further down), along with its parameters. 6 Click Render to kick off the Voice Convert process.

### Voice Convert analyzing a clip

Now the Voice Convert dialog opens and reports how far the conversion has gotten. How long this lasts hinges on the length and count of the clips you picked. After it wraps

up, the new audio shows up on the timeline at precisely the same spot as the original audio (or at the matching spot on a different track, if you'd chosen that). Those new audio clips land in the Media Pool too. Just play the timeline back to audition the fresh voice. To return the audio to how it started, right-click a clip and pick Revert to Original Voice from the context menu. TIP: Although you can drive voices that carry different accents, Voice Convert usually can't reproduce a separate accent. Say you have a voice model of a speaker with a British accent and you drive it using an American accent — what you get leans toward an American take on the British-accented speaker. Drive that British voice model while speaking with a British accent, though, and the results come out well.

### Voice Convert Settings

Every voice conversion involves picking setup parameters that steer the model.

- Track: Choose which track the new audio should sit on. The default, Render in Place, overwrites the original audio.
- File Name: Establish the file name for the new audio clip. You can key in a particular name or lean on the metadata variables to build a naming template. Out of the box, the name reads ClipName-(Voice Model Name).
- Voice Model: Choose which voice model gets applied to the new audio. A handful of built-in choices ship with DaVinci Resolve, and whatever custom ones you build turn up here as well.
- Tight Matching to Source: Tick this box to hew closely to the pitch, intonation, and loudness swings of the source voice. Clear it for a looser reading driven by the Pitch Variance tool.
- Pitch Variance: This tool wakes up once the Tight Matching to Source box is cleared. Smaller values yield a flatter, more monotone reading, whereas larger values bring greater pitch variation.
- Pitch Change: This slider deepens (negative values) or raises (positive values) the voice off the model. Its values are measured in semitones and step in 100 cents (.1 semitone) increments.

### Creating Your Own Voice Models

You're able to build voice models of your own to use alongside Voice Convert. They might capture your own voice, or even someone else's provided you hold the rights to it. This section walks through a few best practices for landing a clean, usable voice model.

### Preparing the Voice Model Assets

Your strongest results come from roughly ten minutes of clean, high-quality recordings of whatever voice you're modeling. Keep that audio clear of heavy room ambiance and noise, with little or no dynamics processing applied. Aim for steady material that comes across as natural. Capturing a spread of emotions can help too, if you'd like to hear how those carry into the driven voice. Approach it the way you would a voiceover audition and show off your range. These voice assets needn't sit in one long clip, but when you're dealing with many separate files, gathering them all into a single bin keeps things organized. Across those several clips, quality should stay even, with no audio variation among the recorded sources.

### Creating the Voice Model

To build a voice model of your own, pick one or more clips for analysis within the Media Pool, then from the right-click context menu head to AI Tools > DaVinci AI Tools Voice Training. The very first time you run this tool, DaVinci Resolve launches the Resolve Extras Download Manager to fetch the support files it needs.

### Voice Model generation

To begin, a warning splash screen comes up so that you accept full responsibility for the way you'll use this tool. After you click accept, The DaVinci AI Voice Training dialog opens with two settings for you to configure.

- Voice Model Name: Type a descriptive name for the new model you're making.
- Quality: Pick either Faster or Better mode for the analysis. Better runs roughly 3x as long as faster,

and around 10 minutes of material can stretch to several hours depending on how powerful your computer is. Creating a voice model starts off as a foreground process, then after the opening analysis finishes it hands off to a background process, freeing you to keep working in DaVinci Resolve on other things or in other apps while it wraps up.

### Voice Model Progress

You can track how the model is coming along via the Voice Model Generation Progress indicator down in the bottom right corner, or by going to Workspace > Voice Model Progress. The Voice Model Generation Progress indicator gradually fills with blue as the voice model completes. Hovering over the top surfaces a tooltip with an ETA and the amount finished. As an alternative, you may instead opt to pause or throw away the model while it's still in progress. Closing DaVinci Resolve likewise pauses the background process, which then picks back up on its own the next time DaVinci Resolve starts. As soon as the model is done, the new voice preset becomes available for use in the Voice Convert dialog.
