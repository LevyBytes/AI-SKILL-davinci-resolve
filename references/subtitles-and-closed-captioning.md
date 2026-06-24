# Subtitles And Closed Captioning (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Subtitles and Closed Captioning

The support DaVinci Resolve offers for subtitles and closed captioning is quite advanced, and bundling in automatic subtitling tools cuts down enormously on the time and labor it takes to assemble accurate subtitle tracks. Thanks to purpose-built subtitle/closed caption tracks you can reveal or hide, the ability to import and export subtitle files, capable subtitle editing and styling at both the track and clip level, and thorough export choices, layering subtitles and closed captions onto your finished project becomes a clear, uncomplicated workflow.

### Subtitles and Closed Captioning Support

In DaVinci Resolve, subtitles ride on specially typed subtitle tracks that hold purpose-designed subtitle generators for adding and editing a program's subtitles. As a rule, each subtitle track maps to one language or purpose, and you're free to rename a subtitle track so it reflects what it holds. Subtitle tracks can be locked, carry Track Selector and Sync Lock controls, and be switched on or off just like any other track. On top of that, a dedicated subtitle-only destination control lets you pick which subtitle track your subtitle clips get edited into. What's more, subtitle generator clips can be resized, moved, edited, and overwritten in the same way as most other clips.

Subtitle track with Track Selectors, Lock, Sync Lock, and enable/disable controls

### Viewing Subtitle/Caption Tracks

A key way subtitle tracks differ from other track types is that no more than one subtitle track can be on view at any moment. In practice, that means when you keep several subtitle tracks—each holding a different language—clicking the Enable control on one subtitle track switches all the rest off.

### Viewing one subtitle track at a time

### Adjusting QC Thresholds For Subtitle/Caption Timing

So you can stick to guidelines laying out the recommended duration, line length, and pace of captions and subtitles, the Subtitles panel of the Project Settings carries parameters you set to flag you whenever a given subtitle clip runs past the thresholds for Characters Per Line, Minimum Caption Duration, and Maximum Characters Per Second.

The Subtitles Setup parameters in the Subtitles panel of the Project Settings While you're editing a subtitle clip, these thresholds drive an automatic calculation of how many lines and characters a particular subtitle clip is allowed given its duration. As an instance, run past the calculated threshold and that caption's CPS value turns red as a warning.

A subtitle's CPS value has gone red here, signaling that it overshoots the current QC threshold Adjusting QC Thresholds for Individual Subtitle Tracks Although setting the subtitle QC thresholds in the Project Settings usually suffices for a single deliverable, those deliverables carrying multiple subtitle tracks across different languages might call for separate parameters on each track, permitting longer line lengths, more screen time, and so on to suit each language's distinct traits. To tune the subtitle settings per track on their own: 1 Pick the subtitle track in the Timeline you'd like to change. 2 Open the Inspector and choose the Track tab. 3 Within the Subtitle Settings pane, clear the Use Project Settings checkbox. 4 Make whatever changes you need to the Max Line Length, Min Duration, and Max CPS controls. From now on these settings override the Subtitle Project Settings for the selected track alone.

The Subtitle Settings sitting in the Inspector's Track pane let you tailor parameters on a per-subtitle-track basis.

### Importing Subtitles and Captions

More often than not, putting subtitles or closed captions onto a DaVinci Resolve timeline means importing a subtitle file prepared somewhere else. At present, DaVinci Resolve handles subtitle files in a number of formats, among them .srt, .srtx, .vtt, .xml, and .ttml. To bring in a subtitle or closed captioning file by way of the Media Pool: 1 Open the Media Pool. 2 Browse to the folder that holds your subtitles. Compatible subtitles turn up as a blank clip icon bearing a subtitle icon down in its lower left corner. 3 Pull the subtitle into the Media Pool by dragging, by importing through the contextual menu, or by any of the other methods you'd use to bring video clips into the Media Pool. To bring in a subtitle or closed captioning file by way of the Import Subtitle function: 1 Open the Media Pool. 2 Right-click any bin in the Bin list, or anywhere across the Media Pool browser's background, and pick Import Subtitle. 3 When the file dialog opens, locate and pick the subtitle file you'd like to import, then click Open. 4 The subtitle file shows up as a subtitle clip in the Media Pool, ready to be edited into a subtitle track. A badge marks it as a subtitle clip.

### An imported .srt subtitle file

TIP: Within the Media Pool, subtitle files relink the same way video clips do.

To put a subtitle clip onto the Timeline: 1 To drop a subtitle clip onto a timeline automatically and line its position up by timecode:

- Right click the subtitle and pick "Insert Selected Subtitles to Timeline Using Timecode." The subtitle clip breaks apart into individual subtitles that land in the subtitle track, with each subtitle lined up against the timeline's timecode.

2 To put a subtitle clip onto a timeline by hand when you lack matching timecode, do one of the following:

- Drag a subtitle file you've imported up into the empty gray strip above your video tracks, and a subtitle track gets created automatically to hold those subtitles
- Drag a subtitle file you've imported onto an existing subtitle track As you drag the subtitle clip, it gets broken apart on the spot so each title lands on the Timeline as a separate subtitle clip, its timing offset reckoned against where the first frame of that file's first subtitle sits.

(Top) The Timeline as it began, (Bottom) The same Timeline once dragging a subtitle file in has spawned a fresh subtitle track 3 Line the imported subtitles up so they sit against the first frame of your program they're meant to match, then drop the titles into the track. Should you accidentally drop the subtitles in the wrong spot, no problem—you can always select them all and slide them earlier or later, the same as any other clips. 4 If you've brought in a new subtitle track, you can rename it to spell out which language and country that track answers to. Bear in mind that subtitle track names get used while exporting or encoding subtitles, so be sure your tracks are named properly ahead of export/delivery. 5 Should you wish to restyle every subtitle you've just put in—say, to shrink them or swap the font—then click the header of the subtitle track you'll work on, open the Track panel of the Inspector, and choose the formatting you want that track to adopt. For a rundown of every subtitle clip you've added, select the header of the subtitle track you just created and open the Captions panel in the Inspector. Down at the bottom of the Captions panel, a list hands you a handy means of moving through a track's subtitles (with the Prev and Next buttons) and making selections. Set the Inspector to full height and you'll get even more room to browse the subtitle list.

The Captions list lays out each caption or subtitle riding a track, ready for you to select, edit, delete, or move through

### Adding Subtitles and Captions Manually

At other points, you might have to build subtitles yourself. Before you do, you'll first need to put in one or more subtitle tracks. With those tracks in place, you can attach subtitle generators to them by a number of routes. Add as many subtitle tracks as the job demands, one per language you need. To add new subtitle tracks:

- Right-click in any track header of the timeline that's currently open, then pick Add Subtitle Track. An empty subtitle track appears atop the Timeline, carrying the name "Subtitle 1," and should Subtitle Tracks have been hidden, they become visible now. Once you've put in a new subtitle track, you can rename it to spell out which language and country that track answers to. Bear in mind that subtitle track names get used while exporting or encoding subtitles, so be sure your tracks are named properly ahead of export/delivery. You're able to show and hide subtitle tracks whenever you need to clear room in the Timeline for working on other tracks. Subtitles on whichever subtitle track is currently selected stay visible all the same, no matter whether the subtitle tracks are shown.

Showing and hiding subtitles tracks:

- Open the Timeline View options, then click the Subtitle button to flip the visibility of subtitles tracks on and off.

The show/hide subtitle tracks button in the Timeline View Options To put individual subtitles onto a subtitle track: 1 Should you want to adjust a particular subtitle track's default style before you begin adding subtitles, click the header of the subtitle track you'll work on, open the Track panel of the Inspector, and choose the formatting you want that track to use. 2 With several subtitle tracks present, click the destination control of whichever subtitle track you mean to add titles to. They carry labels ST1, ST2, ST3, etc. 3 Move the playhead to the frame where the new subtitle should start.

Placing the playhead at the spot where a fresh subtitle ought to start 4 To add a new subtitle clip, take one of these routes:

- Open the Inspector and click Create Caption within the Captions panel of the Inspector. If one or more captions already sit in that subtitle track, click the Add New button over the caption list instead.
- Right-click anywhere across the subtitle track and pick Add Subtitle to drop in a subtitle clip beginning at the playhead's position
- Open the Effects Library, click the Titles category, then drag a Subtitle generator onto whichever Subtitle track you want it to land on.

Manually adding a subtitle

5 If you need to, you can now edit the clip so it better matches the dialog being spoken or the sound being described, by dragging the clip left or right, or by dragging the clip's start or end to resize it. 6 With the new subtitle clip you've made still selected, turn to the Captions panel in the Inspector to type that particular subtitle's text. The text shows up on the subtitle clip as you type it.

Editing the text of the subtitle we just created Each time you add a subtitle, an entry lands in the subtitle list down at the bottom of the Captions panel in the Inspector. That list gives you yet another handy way of moving through a track's subtitles (with the Prev and Next buttons) and making selections.

### Create Subtitles from Audio (Studio Version Only)

Thanks to recent strides in AI and expert-system technology, it's now within reach to produce strikingly accurate, flawlessly timed subtitles of spoken text via DaVinci Resolve's Create Subtitles from Audio function. Create Subtitles from Audio examines the speech across a timeline and automatically builds a subtitle track holding all the spoken dialog turned into text subtitle clips. Create Subtitles from Audio doesn't merely translate phonetic speech straight into text. It also reads the context of that speech correctly and carries it over into proper punctuation and grammar for the subtitle. As an instance, Create Subtitles from Audio singles out proper names and capitalizes them, tacks a question mark onto a sentence's end when your subject poses a question, drops quotation marks into the right spots when your subject quotes something, and when it picks up music in the background, it inserts a [Music Playing] subtitle. It copes with accents and recognizes when more than one person is talking in a scene. You might be taken aback at just how precise the Create Subtitles from Audio tool can be.

The whole subtitling process runs hands-off under Create Subtitles from Audio. To run Create Subtitles from Audio on a timeline: 1 In the Edit page, open whichever Timeline you'd like Create Subtitles from Audio to work on. 2 Mark an In-Out range for the subtitles on the Timeline, or leave it empty to Create Subtitles from Audio across the whole Timeline. 3 Choose Timeline > AI Tools > Create Subtitles from Audio. 4 Within the Create Subtitles from Audio dialog, set the following options:

- Language: Which language the spoken text is in. Picking Auto has DaVinci Resolve work out the language on its own.
- Caption Preset: Whichever Caption Preset style you'd like the subtitles formatted with.
- Max Characters per Line: The ceiling on how many characters a subtitle line may hold. Bigger

figures yield longer on-screen lines of text. Smaller figures yield shorter ones.

- Lines: Decides whether the subtitle runs as a single line or a pair of lines of text.
- Gap Between Subtitles: How many frames get dropped in between subtitle clips. The default sits at 0.

5 Click the Create button.

### The Create Subtitles from Audio options

Create Subtitles from Audio then sets about transcribing the spoken text, with a dialog box showing you how far along it is. Once it wraps up, the resulting subtitles get dropped onto the Subtitle track. Where your Timeline holds no Subtitle track, it makes one for you automatically. Where more than one subtitle track sits on your Timeline, Create Subtitles from Audio always writes to the topmost track. The single spot where the Create Subtitles from Audio tool still commonly stumbles is overlapping dialog clips spread across multiple tracks. To get around that, you can mute any audio track on the Timeline you'd rather leave out of the subtitle analysis. With the Create Subtitles from Audio finished, you can hand-edit the captions to clean up any small mistakes using the tools laid out earlier in the Adding Subtitles and Captions Manually section.

### Create Subtitles from Audio Language Support

At the time of writing, Create Subtitles from Audio handles the languages below:

- English, French, German, Italian, Spanish, Portuguese, Dutch, Danish, Norwegian, Swedish, Russian, Japanese, Korean, and Chinese (Simplified Mandarin).
- Plenty of further languages can be reached too by way of the Extended AI Transcription Support Package in the Extras Downloads Manager. The roster runs: Arabic, Afrikaans, Armenian, Azerbaijani, Belarusian, Bulgarian, Bosnian, Catalan, Croatian, Czech, Finnish, Estonian, Greek, Galician, Hindi, Hebrew, Hungarian, Indonesian, Icelandic, Kazakh, Kannada, Lithuanian, Latvian, Malay, Macedonian, Maori, Marathi, Nepali, Polish, Persian, Romanian, Slovak, Serbian, Slovenian, Swahili, Tamil, Tagalog, Turkish, Thai, Urdu, Ukrainian, Welsh, and Vietnamese.

### Editing Subtitles and Captions

Subtitle clips can be picked one at a time or in groups, and slipped, slid, resized, rolled, and rippled exactly like any other clip on the Timeline, whether with the mouse or with keyboard commands, using the Selection, Trim, or Razor tools. You can select subtitle clips whole, or only their edit points, in readiness for nudging or dynamic trimming. Put simply, subtitle clips can be edited, in most respects, just the way any other clips can.

### Styling Subtitles and Captions

For styling subtitle text, a rich array of styling controls lives in the Track Style panel of the Inspector. To change the styling of every title on a given subtitle track: 1 Click the header of the subtitle track you'll work on, or else pick a clip belonging to a given subtitle track—whether from within the subtitle track itself or out of the Captions panel's subtitle list in the Inspector. 2 Open the Inspector, then open the Track panel that turns up within it. 3 Edit whichever parameters you need to fix the default style of all the subtitles and closed captions that show up on that track. The Track panel carries far more options than the Captions panel, including a cluster of Style and Position controls covering Color, Font and Font Face, Size, Kerning, Line Spacing, Alignment, Zoom X and Y, Position X and Y, Text Anchoring, and Opacity.

Choosing a Font Case over in the Subtitle Inspector's Track tab Do remember that additional clusters of controls let you add a Drop Shadow, Stroke, and/or Background to every bit of text on that track, sitting at the bottom of the Track panel of the Inspector. You're also free to alter how each subtitle clip looks one by one, right down to a single word or letter, whatever the Track panel's settings happen to be.

To change the styling of a single subtitle on a given subtitle track: 1 Choose a clip belonging to a given subtitle track, taken either from the subtitle track itself or from the Captions panel's subtitle list within the Inspector. 2 Tick the Customize Caption check box beneath the Caption. 3 Edit whichever parameters you need to fix the style of this one subtitle alone. Every other title in the track keeps the original track style. To change the styling of a single word or words within a given subtitle: 1 Select a clip riding a given subtitle track, drawn either out of the subtitle track or out of the subtitle list found in the Inspector's Captions panel. 2 Tick the Customize Caption check box beneath the Caption. 3 Highlight the text you'd like to change in the Caption panel. 4 Edit whichever parameters you need to fix the style of this subtitle's highlighted text. Every other title in the track keeps the original track style.

Ticking the Customize Caption box brings up the tools that let you restyle one individual subtitle or its text.

### Using Subtitle Track Style Presets

Should you wish to store and reuse a particular subtitle style, you can drop it into the Subtitle Style Preset menu, reached by clicking the Subtitle option menu (3 dots) up in the top-right corner of the Subtitle Inspector. You can likewise export and import presets so a subtitle style can be shared between systems. To add a new subtitle style preset: 1 Build a subtitle track and tune its style as to fonts, position, colors, etc. 2 Click the option menu (3 dots) up in the top-right corner of the Subtitle Inspector. 3 From the drop-down menu, choose Save Track as Preset. 4 Hand your preset a fresh name. From that point on, the Subtitle Inspector's option menu lists your subtitle style preset. To switch a subtitle track over to a different style preset: 1 Pick an existing subtitle track you'd like to change. 2 Click the option menu (3 dots) up in the top-right corner of the Subtitle Inspector. 3 Pick the subtitle style preset from the drop-down menu. 4 Pick Load Preset from the submenu. Your subtitle track updates instantly to the new style preset. This command can be undone. To update a subtitle style preset: 1 Out of the Subtitle Inspector option menu, load whichever subtitle style preset you want. 2 Make whatever changes you need to the style as to fonts, position, colors, etc. 3 Click the option menu (3 dots) up in the top-right corner of the Subtitle Inspector. 4 Pick the subtitle style preset you'd like to update from the drop-down menu. 5 Pick Update Preset in the submenu. 6 Pick Update from the dialog box. Your subtitle style preset then replaces the existing preset bearing the same name. This action has no undo. To delete a subtitle style preset: 1 Click the option menu (3 dots) up in the top-right corner of the Subtitle Inspector. 2 Pick the subtitle style preset you'd like to delete from the drop-down menu. 3 Pick Delete Preset in the submenu. 4 Pick Delete from the dialog box. The subtitle style preset gets removed from the Subtitle Inspector's option menu. This action has no undo. To export a subtitle style preset: 1 Click the option menu (3 dots) up in the top-right corner of the Subtitle Inspector. 2 Pick the subtitle style preset you'd like to export from the drop-down menu. 3 Pick Export Preset in the submenu. 4 Using the file browser, pick the spot where the ".preset" file should land. 5 Press Save. That writes the subtitle style preset file onto the user's computer, the file taking the preset's name plus a .preset extension.

To import a subtitle style preset: 1 Click the option menu (3 dots) up in the top-right corner of the Subtitle Inspector. 2 Pick Import Preset in the submenu. 3 Choose where the ".preset" file lives from the file browser. 4 Press Open. The subtitle style preset gets added to the Subtitle Inspector's option menu.

The Subtitle Style Preset menu, which lives within the Subtitle Inspector's option menu

### AI Animated Subtitles (Studio Version Only)

In the Titles tab there's a collection of Fusion Title Templates called Animated. You can drop these templates onto subtitle tracks, making it simple to build animated subtitle effects. They work hand in hand with DaVinci Resolve's transcription engine to match and highlight spoken audio against subtitle timing. You can preview the prebuilt templates in the Animated section of the Titles tab, and naturally, with Fusion you can craft your own custom templates as well. To animate your subtitles, just drag the animated template out of your Titles library onto the header of the subtitle track. Their parameters are yours to customize in the Inspector.

Here the Word Highlight animated template is in use, lighting up each word in red at the moment it's spoken in the clip.

### Subtitle Tracks Using Fusion Templates for Styling

You're able to style a subtitle track with a Fusion template. To do so, simply drag any Fusion title template out of the effects library onto the subtitle track header. The Fusion effects then take precedence over any track-level or per-caption styling the Inspector applied to the track, letting you craft finely tuned text looks out of the underlying Fusion compositions.

### Using a Fusion template to create stylized subtitles

### Linking Subtitles to Clips

If you'd like, you can tie one or more subtitles to the clip they go with, so that when you re-edit a subtitled scene, each clip's subtitles travel along with the clips. This setup doesn't always behave the way you'd anticipate while trimming, but it shines when you're shuffling clips around. To link a subtitle to another clip: 1 Select a clip together with its subtitles all at once.

Picking a video clip together with the subtitle that goes with it so the two can be linked 2 Choose Clip > Linked Clips (Option-Command-L). A Link icon then appears, marking that the subtitle clips are now tied to the video/audio clip.

Carrying link badges, the freshly linked clip and subtitle make their tied state plain

### Using Subtitles in Nested Timelines

Subtitles carry over with their original timelines as part of a nested timeline. Just drag one subtitled timeline either out of the Media Pool or the Source Viewer into a fresh timeline. Should you want the original timeline's subtitles folded into the new timeline's caption list, you have to Decompose in Place the nested timeline.

### Subtitle Regions

Now and then you'll need several subtitles shown on the screen all at once. A frequent case is two characters on screen whose dialog overlaps. By placing the subtitles thoughtfully, where each sits on the screen can signal who is speaking which subtitle. Subtitle regions let you keep multiple subtitle clips active and overlapping simultaneously, all the while held inside one overall subtitle track.

### Adding and Deleting Subtitle Regions

By default, every subtitle made within a subtitle track sits in Region 1 (R1) at the track's base layer. Wishing to add another subtitle region means you must create a fresh subtitle region in the subtitle track. A subtitle track can hold no more than three subtitle regions (R1, R2, R3), which means up to three separate subtitles can be on screen at once. To add a new subtitle region: 1 Right click within the present subtitle track—the timeline track body itself, that is, rather than its track header. 2 Pick Add Subtitle Region. This splits the subtitle track horizontally and builds a new region. To delete a subtitle region: 1 Right click somewhere on the present subtitle track (meaning the timeline track itself, not the track header). 2 Pick Delete Subtitle Region, then from the submenu single out whichever region you want gone. To rename a subtitle region: 1 Right click over the present subtitle track itself (the timeline track, not its header). 2 Pick Rename Subtitle Region and key in a name for that particular region.

Adding and deleting subtitle regions from the subtitle track

### Using Subtitle Regions
