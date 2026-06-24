# Text Based Editing (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Text Based Editing

Improvements in Machine Learning now let you sort, trim, and polish clips by examining the dialog that's spoken and turning that speech into written text. This chapter walks through how DaVinici Resolve's Text Based Editing toolset is used.

### Audio Transcription (Studio Version Only)

Knowing what was actually said in a clip is among the most valuable pieces of metadata you can have. A complete transcript of a take helps on narrative projects by letting you locate particular clips from script dialog, yet it matters even more on unscripted documentary and news shoots — both for grasping which parts of the story made it to camera and for assorted organizational, creative, and legal needs. Not long ago, producing a transcript meant a person sat listening to a clip at normal speed and typed the spoken words into a log sheet by hand. Thanks to progress in the DaVinci Resolve Neural Engine, that monotonous transcription chore is now handled by your computer for each clip, done automatically and — what counts most — with precision. On top of that, attaching text transcripts to your project's clips unlocks fresh text-based editing capabilities for choosing, finding, and dropping clips onto your timeline.

### Transcribe Audio

Reachable from the Media Pool on the Media, Cut, Edit, and Fairlight pages, the Transcribe Audio feature runs entirely on its own.

The Transcribe Audio icon in the Media and Edit pages To have a clip's audio transcribed automatically: 1. In the Media Pool, pick one or more clips that contain audio you wish to transcribe. 2. Right-click any clip you've selected and choose AI Tools > Audio Transcription > Transcribe from the contextual menu. As an alternative, click the Transcribe Audio icon on the Media Pool toolbar.

### The Transcribing Audio window

Now the Transcribing Audio window opens, telling you the count of clips still awaiting analysis, how fast the analysis is running compared to real time, and roughly the remaining time before the chosen clips finish. A button lets you abort the process whenever you like.

The speech balloon icon showing that a clip has been transcribed Whenever a clip carries a transcription, a tiny speech balloon icon shows up at the bottom left of that clip's thumbnail within the Media Pool. To strip a transcription off a clip: 1 In the Media Pool, choose the clip whose transcription you intend to remove. 2 Right-click the chosen clips and pick AI Tools > Audio Transcription > Clear Transcription from the contextual menu.

### Audio Transcription of Timelines

Beyond clips, Audio Transcription functions for timelines too, operating exactly as outlined earlier. Putting a timeline into text form serves a number of real-world legal and organizational purposes. That said, when your goal is producing subtitles or captions for the Timeline, a purpose-built tool exists just for that. To read up on the Create Subtitles from Audio feature, turn to Chapter 52, "Subtitles and Closed Captioning."

### The Transcription Window

Holding the displayed text together with its timecode, options, and editing tools is the job of the Transcription window. To keep things convenient, you can drag the Transcription window anywhere across the GUI, including onto a second display.

The Trascription window with several clips displayed and the Search pane open. Yellow marks the text that was searched for. Teal marks the clip's In and Out range, while a red triangle points out where the playhead currently sits in the Viewer. To open the Transcription window:

- Right-click any transcribed clip or clips, then choose Transcribe Audio from the contextual menu. You can instead click the Transcribe Audio icon found on the Media Pool toolbar.

Here are the sections and tools the Transcription window contains: Export: Pressing this icon opens a file browser in which you can store a .txt file holding the transcription results so other programs can read them. Search: Pressing this icon brings up a Search and Replace dialog that lets you track down particular words or phrases throughout every selected clip in the Clips panel. Matching words turn yellow. Partial-word search and replace is supported within the Transcription window as well. To adjust how the search behaves, open the search bar and choose either Contains or Full Word from the drop-down menu on the left.

Partial-word searches are also possible inside the Transcription window when you pick the Contains option.

Options Menu: Brings up the Transcription window options. Speaker Detection: Switching this on analyzes a particular voice and gives it a speaker number. That speaker is then retained across every clip in a project. Display Speakers: Toggles the Speaker column on or off within the Transcription window. Transcribe Missing Clips in Timeline: When the timeline holds clips not yet run through speech to text (transcription pending), choosing this option transcribes them and slots them correctly into the Transcription window. Remove Silent Portions: Clears every silence (…) the Transcription window has detected. Create Subtitles from Audio (Timeline only): Builds a fresh Subtitle track and lays subtitles down for you. To read up on the Create Subtitles from Audio feature, consult Chapter 52, "Subtitles and Closed Captioning." Import Subtitles (Clip only): Lets you bring in a subtitle saved as .srt format (covered further on in this chapter). Export Subtitles: Lets you send out your subtitles as .srt format (covered further on in this chapter). Reset Speaker Data: Wipes every stored speaker detection record from the project. Clips: This pane displays each selected clip whose transcription you elected to view. Clicking a thumbnail brings that clip's transcription into the Transcript window. An orange outline marks the active clip. Should you have picked only a single clip, this pane is hidden. Transcript: Shows the transcription text. This box also serves to position the playhead and to fix a clip's in and out points, as covered in the Text Based Editing section below. Remove Silent Portions: Clears every detected silence (…) from the transcript. Text View Controls: Lets you govern the font size along with the high contrast settings of the text inside the Transcript window.

Create Subclip: Produces a new subclip of the shot from the In and Out points that the highlight in the Transcript window establishes. Marker: Drops a marker at the word position highlighted in red; should an In/Out range be highlighted instead, it lays down a duration marker spanning that range. Stop: Halts playback of the clip within the Viewer. Play: Runs the clip forward at realtime in the Viewer. Play in to Out: Plays forward only across the set In and Out range.

Place on Top: Carries out a Place on Top edit of the chosen range into the timeline. Insert: Carries out an Insert edit of the chosen range into the timeline. Append: Carries out an Append edit of the chosen range onto the end of the timeline.

### Editing Text in the Transcription Window

Some of what gets transcribed from a clip's audio isn't helpful or desired in the finished transcription. You can strip out crew chatter, blown lines, and lengthy pauses, and you can also correct slip-ups that the Audio Transcription process itself produced.

### Selecting Text

Before you can edit any text, it has to be selected within the Transcription window. Several approaches exist, varying with how much text you intend to grab. To pick out one particular word in the transcription: Double-click that word, which selects it and turns it teal. To grab a span of transcription text: Drag across the text you wish to edit, selecting it and tinting it teal. To capture a whole sentence in the transcription: Click any word in the sentence and hit the X key, selecting the entire sentence and shading it teal. To grab a full paragraph in the transcription: Triple-click any word in the paragraph, selecting the whole paragraph and coloring it teal. To select the transcription's entire text: Hit Command-A, which selects all the text and highlights it teal. To clear the all-text selection in the transcription: Press Option-X to drop the selection of all the text and highlight it in teal.

### Editing Text

With any text selected (highlighted in teal), a right-click on it surfaces the editing choices. The action runs the moment you click one of the editing tools.

Right-clicking any selected text surfaces these editing tools of the Transcription window (l-r): Edit, Delete, Undelete, Copy, and Assign To.

Edit: Choosing this tool opens a text field in which you can make minor corrections to the selected text. It's good for fixing wrong words, spelling errors, and tidying up proper names in the transcription. Drastically rewriting the text — say, swapping a full paragraph for a two- or three-word summary — produces erratic results when used for editing. The action can be undone. Delete: Unlike a word processor, this tool doesn't erase the selected text from the Transcription window; rather, it tags the text orange with a strike-through. Text marked that way stays out of the exported transcript and won't have its range placed into the Timeline by any edit operation. As a result, a cut shows up in the Timeline at the spot where the deleted text range sits in the transcript. Because every word is still present in the audio clip exactly as recorded, it's often clearer to regard this as an "exclude" operation instead of a true deletion. Undelete: Picking this tool undoes a prior deletion. It restores the orange strike-through text to normal text, lets it back into the exported transcription, and brings its range back in for editing. Copy: Duplicates the selected range so it can be used in other applications. The Transcription window has no Paste command. Assign To: When the automatic speaker detection has misidentified who spoke a line, you can hand-assign it to another speaker by choosing one from the drop-down menu.

### Understanding Silence (…) in the Transcription Window

For the majority of shots, a sizable stretch of the audio clip carries no spoken dialog whatsoever. The Transcription window flags these quiet stretches with ellipses (…). Locating where the talking happens matters, but so does spotting where it doesn't. Within the Transcription window these silences (…) behave much like words do, so you're free to delete them and leave them out of any editing operation. Imagine, for instance, a lengthy interview broken up by repeated gaps between questions. One way would be to chop that long clip apart by hand, dropping In and Out points and isolating each question and answer individually. Yet if you run Audio Transcription, delete every silence (…) in the Transcription window, and then edit that span into the Timeline, you'd immediately end up with a string of separate clips containing nothing but the questions and the answers. That way the program drops in all the pertinent clips for you in one move, sparing you the tedious scrubbing and edit-point placement for each single portion of the clip in the Viewer.

Shown here are the original Interview clip (Tracks V1, A1 violet) plus the identical media after every silence was stripped via the Transcription window (Tracks V2, A2). Observe how it splits on its own into separate question and answer clips.

Stripping silences inside the Transcript window proves handy both when exporting a transcript and during text based editing, which is why a dedicated tool exists to clear them all at once.

To delete all the silences (…) in the Transcription window:

- Click the Remove Silent Portions icon sitting immediately to the left of the Font Controls,

in the Transcription window.

- Click the Option menu (three dots) at the top right of the Transcription window, then

select Remove Silent Portions from the contextual menu.

- Highlight the range you intend to use in the transcription window.
- Cut the range into the timeline by clicking one of the editing icons at the lower right of the

transcription window.

### Detect Speakers During Transcription (Studio Version Only)

While transcribing a clip, DaVinci Resolve is now able to recognize separate speakers, presenting each speaker's individual timecode span alongside their text. Aside from yielding richer text transcription exports, speaker detection can serve as a reference for text based editing. Because Speaker Detection operates per project, once you switch it on it stays active for every later transcription job, whether on clips or timelines.

Switching on Speaker Detection from a clip's context menu. To Enable Speaker Detection for Transcriptions:

- Right-click a clip or timeline, then choose AI Tools > Audio Transcription >

Speaker Detection.

- Or select Speaker Detection from the Transcription window's Option menu.
- Click on the Transcribe option to start the operation.

### Transcription and Speaker Detection in Timelines

There's also the option to Transcribe and Detect Speakers for a timeline. Doing so examines the timeline and transcribes the media underneath. It then hands you a timeline transcription drawn from the In and Out points of each timeline clip and tags every segment with a speaker. Timeline Transcriptions are opened in Timeline Transcription mode, as described below.

The Transcription window shown with Display Speakers active. To rename a speaker, double-click the name and type a replacement into the text field. Once Speaker Detection is on, every following audio transcription you produce for clips and timelines will identify the separate speakers. The project keeps all of a speaker's voice signatures stored across multiple clips. Should you return the following day to bring more audio clips into your project, DaVinci Resolve recalls the voices it analyzed earlier and tags them to the correct speaker on its own. To clear the stored speakers from your project, choose Reset Speaker Data from the Transcription window's Option menu. Inside the Transcription window, speakers start out labeled by number (Speaker 1, 2, 3 etc.). Renaming a speaker is done by double-clicking the speaker name and typing a fresh name into the text field. Every other appearance of that speaker updates to the new name. When Speaker Detection misjudges who's talking, you can hand-reassign a passage of text to a different speaker: select the text, right-click it, and pick the Assign To icon from the pop-up menu. A second dialog box then opens so you can shift the attribution to any of the other detected speakers.

Reassigning a speaker by hand is done by right-clicking the text and choosing the Assign To icon.

Should you want to conceal the speakers once more to tidy up the Transcription Window, you can switch their display on or off through the Transcription window's Option menu under Display Speakers. Flipping this setting leaves intact whatever speaker associations have already been made.

### Export Audio Transcriptions with Speaker and Timecode Information (Studio Version Only)

When you export a transcription in DaVinci Resolve Studio, the text file you get back carries the speaker name plus timecode details for every speech block. Having that information makes searching through and moving around transcriptions far simpler.

Transcripts include speaker and timecode information for dialog blocks.

### Audio Transcription Supported Languages

The language used to build the transcription is chosen in the Project Settings > Subtitle and Transcription> Transcription Setup section. Pick any of the supported language models, or leave it set to Auto and let DaVinci Resolve work out who's saying what. At the time of writing, Audio Transcription and Text-Based Editing handle these languages:

- English, French, German, Dutch, Danish, Swedish, Norwegian, Italian, Spanish, Portuguese, Russian, Japanese, Korean, and Mandarin (Simplified Traditional).
- A great many additional languages can be obtained through the Extended AI Transcription Support Package found in the Extras Downloads Manager. Among them: Arabic, Afrikaans, Armenian, Azerbaijani, Belarusian, Bulgarian, Bosnian, Croatian, Catalan, Czech, Finnish, Estonian, Galician, Greek, Hindi, Hebrew, Hungarian, Indonesian, Icelandic, Kazakh, Kannada, Lithuanian, Latvian, Malay, Macedonian, Maori, Marathi, Nepali, Polish, Persian, Romanian, Slovak, Serbian, Slovenian, Swahili, Tamil, Tagalog, Turkish, Thai, Urdu, Ukrainian, Vietnamese, and Welsh.

### IntelliScript for Creating Timelines from Scripts (Studio Version Only)

In DaVinci Resolve 20, the capable AI-driven IntelliScript tool taps the Transcription Engine to align an original script and build a timeline from it. The feature lets you rapidly put together rough cuts of scenes and even sorts multiple takes for you within the timeline. IntelliScript grasps context well enough that if your performer improvises with a comparable phrase rather than the precise wording in the script, it should locate it anyway.

A simple text file script to feed into IntelliScript To put IntelliScript to work building a timeline from a script: 1 Build a script file as plain text (.txt) holding only the spoken words. IntelliScript wants nothing but the bare spoken text with full stops (.) closing each sentence. Conventional script formatting — scene descriptions, parentheticals, character names — is apt to trip up transcription. 2 Highlight every clip you mean to feed IntelliScript, right-click, and pick AI Tools > Create New Timeline Using IntelliScript. 3 At that point DaVinci Resolve asks you to load the text script file. Press Open. After the transcription finishes, IntelliScript builds a fresh timeline and, on track one, arranges the strongest clips in sequence according to the dialog in the script file. Alternate takes land on extra tracks generated for them, switched off by default. With the timeline assembled, you can examine the top take on track one and audition alternate takes across particular regions, turning them on and off as you go.

The IntelliScript results in the timeline. Strongest takes go on track one, alternates onto separate tracks, all of them off by default. Here, at the very end, we overrode its picks and manually switched on the take we judged best. NOTE: IntelliScript settles on the "best" take purely by matching spoken dialog. It draws on no good take metadata and bases its decisions on nothing beyond dialog matching.

### Text-Based Video Editing (Studio Version Only)

Following a Transcribe command, DaVinci Resolve now has the precise timecode location of every word in the clip, and that knowledge unlocks several handy text-based editing tools through the Transcription window. Text-based video editing can be used on both the Cut and Edit pages. A link exists between the Transcription window's cursor and the Viewer's playhead. Moving the cursor through the text drives the playhead to the matching spot in the Viewer's clip. That way you can drop the playhead with precision on whatever spot you choose by the text word, instead of scrubbing forward and back across the audio track. To send the playhead to a particular word in the clip:

- Click a word in the Transcript window and a red arrow highlights it. The viewer playhead then leaps straight to the end of that word within the clip in the Viewer. Besides the cursor and playhead being tied together, a clip's In and Out points are likewise tied to whatever text range you select in the Transcription window.

To set an In and Out range in the clip:

- Drag across the text in the Transcription window to tint it teal. The clip's In point lands just ahead of the first word, and its Out point lands just past the last word in the highlighted text.

To set a sentence's In and Out range:

- Click any word in the sentence and hit the X key, which selects the full sentence and shades it teal.

Highlighting a span of text in the Transcription window (R) sets In and Out points for that span automatically on the Viewer's clip (L). With an In and Out range in place, the Transcription window's editing tools let you perform a handful of everyday editing and media management chores. The Create Subclip and Add Marker tools in the Transcription window To make a fresh subclip out of a selected range: 1 In the Transcription window, drag to highlight a span of text in teal. 2 Hit the Create Subclip icon at the lower left of the Transcription window. 3 Within the Create Subclip window, type a name for the subclip and click the Create button. To put a marker on a clip: 1 For a standard marker, pick a single word in the Transcription window (red arrow); for a duration marker, drag to highlight a span of text in teal. 2 Click the Marker icon sitting at the Transcription window's lower left. Within the Transcription window, the Place on Top, Insert, and Append Edit icons To cut an In and Out range into the current timeline: 1 In the Transcription window, drag to highlight a span of text in teal. 2 Click one of the Edit icons at the lower right of the Transcription window. Place on Top: Drops the chosen edit range onto a track above whichever one is currently active in the timeline. Insert Edit: Slots the chosen edit range into the timeline at the timeline In point. Append: Tacks the chosen edit range onto the timeline's end.

### Edit Timelines Based on Source Clip Transcription

The transcription you produced from the original source clip can afterward be used to alter that same clip on the timeline. Switching to this mode in the Transcription window lets you pick, cut, and paste text and then push those edits through to the timeline. For Timeline mode to work in the Transcription window, the timeline clips have to be transcribed back in the Media Pool. You enter Timeline Transcription mode by clicking the Timeline icon at the top left of the Transcription window.

The Timeline Transcription Mode icon, located at the upper right of the Transcription window Once Timeline Transcription mode is active, the window's text editing tools become usable and the edits you make appear on the timeline too. As an example, in the clip below we chose a sentence within the Transcription window, and as shown, that sentence's In and Out points were set automatically in the Timeline sitting behind it.

Choosing a sentence in the Transcription window establishes the matching In and Out points on the timeline. Once the text is selected, you can manipulate that selection with the usual Cut, Copy, Paste, and Delete tools and have those edits reflected on the timeline. The example below has us slicing one sentence out of a clip and relocating it to an earlier place in the timeline.

Choosing the second clip's first sentence, then right-clicking and applying the Cut tool Here the sentence has been excised from the timeline and swapped for silence (…) inside the Transcription window.

Next we fix the new In point on the timeline by choosing the first clip's opening sentence fragment within the Transcription window. We then right-click and select the Paste command.

The footage of the sentence we removed gets pasted into that location and now leads off the Transcription window.

Now we target the timeline gap left behind where the sentence was first cut, selecting the (…) silence in the Transcription window. Then right-click and pick Delete.

The finished timeline, sentence relocated and gap closed. Achieved entirely by working the text inside the Transcription window.

### Adding Clips to Timeline Transcriptions

You're free to keep dropping un-transcribed clips into the timeline as you edit. Whenever an un‑transcribed clip turns up, the Transcription window labels it "Transcription Pending"; in that situation just choose "Transcribe Missing Clips in Timeline" from the Option menu to kick off the transcription of every missing clip.
