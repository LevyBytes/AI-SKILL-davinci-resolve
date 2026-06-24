# Cut And Edit (part 1)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Cut and Edit

### Canva Affinity .af File Support

The DaVinci Resolve timeline can now read Canva Affinity .af files natively. Bring an Affinity file into the media pool and, by default, it arrives flattened and rasterized. From there the image behaves on a timeline exactly like any other still-image format. Yet once it sits on the timeline, you can break the Affinity file apart again into its separate layers, each one fanning out onto a fresh video track. Should the Affinity file hold several layer levels or groups, those start out composited onto one video track, though you can break them down further into separate layers whenever you need to. Here is how to split a Canva Affinity .af file on the timeline: 1 On the timeline, click the .af clip to select it. 2 Right-Click the clip, then choose “Split Layers in Place” As an illustration, this Affinity file consists of a group containing several layers, and those layers are in turn sub-grouped into head, body, and legs.

### The original layered Affinity file

Pulling the file into a Timeline rasterizes and flattens every one of the layers by default.

### The Affinity file in a Timeline

Right-click the image on the timeline and choose “Split Layers into Place” and the file fans out into its first tier of layer groupings on the timeline — here, Head, Body, and Legs.

The Affinity broken up into Head Body and Legs layers Should you want to, you can break the layers down into still more tracks by right-clicking one of the layers on the timeline and once more choosing “Split Layers in Place.” Below you can watch the Body group break apart into its separate layers.

The Body layer group expanded into its component layers At this point you can go on to adjust, animate, or edit each layer further inside DaVinci Resolve. Layers can also be folded back together by selecting them and turning them into a compound clip. Over in Affinity, you can keep altering and reshaping the image, and the moment you save those edits they will refresh automatically within DaVinci Resolve. That said, sweeping changes to the layer grouping and hierarchy in Affinity might not carry over cleanly into DaVinci Resolve, and when that occurs you should simply re-import the revised .af file into the media pool once more.

### Enhanced Retime Keyframing Controls

In the Keyframe Editor, the Retime parameter controls have been upgraded so they now share the same bezier easing tools the other parameters use. With these tools you can pull off intricate retime effects — easing into a freeze frame, say, or smoothing out non-linear speed ramps across a clip.

The Speed controls now lean on bezier easing so retime speed shifts come out smooth

### Keyframe and Add Curves for Selected Clips

Keyframe editing now handles multi-clip selection. No matter whether your clips run side by side or are stacked one above another, you can pick the clips you mean to work on, switch on Keyframe mode, and tweak their keyframes right away. The selected clips’ keyframes display at the same time when stacked, or one after another when side by side. That both saves you time when keyframing a run of clips and gives you a visual reference for how the various curves and keyframes stack up against one another between clips.

The Keyframe / Curves editor with multiple clips selected (sequentially).

### New Keyframing Ease Options

For advanced keyframing, fresh ease functions let you set behavior on a single keyframe or alter how interpolation is read between several keyframes. Step In/Out: Step in and out flip a keyframe’s state from one to the next instantly, with no interpolation. You might, for instance, want the second hand on a clock illustration to tick ahead rather than glide ahead. To step a run of keyframes, multi-select the keyframes you want to change and click either the Step In or Step Out icons up top in the Keyframe Editor.

Step In keeps the value of the keyframe before it, then leaps to the next keyframe. Here Step In is at work on a cluster of keyframes along a curve. Step Out leaps right at the keyframe and holds that value all the way to the next keyframe. Here Step Out is at work on a cluster of keyframes along a curve. Loop: Looping a run of keyframes makes it simple to build a repeating motion without slogging through the setup of each keyframe by hand. The motion of the originally selected keyframes is copied across the clip’s whole length. You might, for example, build a walking animation that carries on by itself once the first “step” is laid down. To Loop a run of keyframes, multi-select whichever keyframes you want repeated, then reach for Loop via the Option Menu > Loop Type inside the Keyframe Editor.

Across the clip’s full span, the first three keyframes here are Looped Ping Pong: Much like loop, Ping Pong likewise spins up a run of keyframes automatically, but rather than repeating the sequence, Ping Pong runs it in reverse on reaching the end, then reverses once more when it returns to the start. The textbook example is a bouncing ball.

To Ping Pong a run of keyframes, multi-select whichever keyframes you want bouncing back and forth, then reach for Ping Pong via the Option Menu > Loop Type inside the Keyframe Editor.

Across the clip’s full span, the first two keyframes here are Ping Ponged back and forth Reverse: Reverse could not be plainer — it grabs your keyframe selection and plays it backward along that same keyframe path. To Reverse a run of keyframes, multi-select whichever keyframes you want flipped, then reach for Reverse Keyframes via the Option Menu inside the Keyframe Editor. Shape Box: The shape box lets you tune the interpolation across several keyframes in a steady, measured way by enclosing them in a box whose edges you can manipulate. Keyframes inside that box stretch and squeeze as you drag the box’s edges. Grab the shape box from the toolset up top in the Keyframe Editor, then draw the box around whichever keyframes you want to shift. Hold the Option key and drag the box’s corners to skew the keyframes in a particular direction.

With the Shape Box icon (circled red), you draw a bounding box around a run of keyframes so as to stretch or grow them.

Hold the Option key and drag a corner of the box to skew the keyframes.

### Keyframe Fusion Effects, Generators and Text Tools in the Keyframe Editor

Fusion Effects, Generators, and Text tools can be keyframed through their Fusion parameters in the Keyframe Editor. Just pick one or more Fusion titles, effects, or transitions to bring these properties up in the keyframe editor. Fusion-based clips may carry a great many associated parameters, so you’ll want to pare those down to only the ones you mean to keyframe. The tool for that, Display Selected Parameters, sits within the Keyframe Parameters 3-dot option menu. NOTE: This holds only for Fusion effects living in the Cut and Edit pages. Ordinary Fusion clips and compositions will still rely on Fusion’s expansive keyframe editor instead.

The Keyframe editor modifying a Fusion Title.

### Subframe Support for Audio Keyframing and Markers

The DaVinci Resolve 21 Edit timeline brings several quality-of-life upgrades for audio work. Getting precise subframe audio adjustments calls for you to be zoomed almost all the way in on the timeline.

- On the edit page you can place and shift audio keyframes with subframe, audio sample precision. To add keyframes more easily, hold alt, press the left mouse button to drop the keyframe, then drag it where you want and release to lock in the action.
- You can likewise add and move markers and duration markers so they begin and end between frames. This works for both clip and timeline markers.
- Zoomed in, you can scrub the edit timeline in sub-frame steps with full audio feedback.

### Support for OGraf HTML Graphics and Lottie Animations

On macOS and Windows alike, DaVinci Resolve 21 now handles HTML-based animation in the OGraf (.json) and Lottie (.lottie) formats. An animation — whether you turned it up online or built it yourself — can now drop straight onto your timeline. Once you’ve exported the .json or .lottie file, just drag and drop it into your Media Pool the same as any other media. You can also drop it right onto the timeline, where it gets recognized and handled like a fully rendered animation clip. The alpha background is recognized too, so transparency holds. Simply drop the clip over another layer and it composites properly, which makes it ideal as a stinger or transition. On top of that, Fusion now ships a new node called OGrafLoader. This handy tool lets you load your OGraf or Lottie files into your composition with ease.

### Font Browser for Choosing Text and Subtitle Elements

When picking a font for text-based elements, users can now opt to bring up an expanded Font Browser. The Font Browser opens out and puts the spotlight on the text faces, making the perfect font easier to land on. You can open the Font Browser by clicking its icon near the font selection box across various tools. Clicking that icon (circled red) is what opens the Font Browser. A thorough view of your installed fonts is what the Font Browser lays out. To settle on a font, just pick it in the Font Browser, then press the Select button. That font then loads into the font selection field of your tool.

### The Font Browser in Thumbnail View

Clicking a font actually picks the whole font family. When the family carries several styles in thumbnail mode, tiny circular forward and back icons turn up beneath the font, letting you cycle through each font iteration. In List view a disclosure triangle near the font name reveals them all. There’s also a star icon you can click at the upper right of the font face, which drops the chosen font into the Favorites tab. With the Font Family picked, you can move through each iteration by clicking the left and right arrows. Clicking the star at the upper right Favorites the font. The Font Browser can be resized, and it carries a tidy toolset to help you pin down the perfect font.

### The Font Browser Toolbar

- All Fonts: Click this tab to display every font installed on your machine.
- Favorites: Click this tab to display only the fonts you’ve favorited by clicking their star.
- Scale: This slider grows or shrinks the size of the font boxes.
- Thumbnail View: Lays out fonts as a run of square thumbnails.
- List View: Lays out fonts as a run of long rectangles.
- Search Bar: When you know the name, or even a piece of the name, of the font you’re after, you can type it

here so only fonts matching those results come back.

- Light / Dark Mode: Pick light or dark text set against the opposite background.
- Filter: Tick individual classification and weight parameters to narrow fonts to just those types.
- Option Menu: Pick from the following options:

Display Default Text: Shows the “The Quick Brown Fox…” text string within the font windows. Display User Custom Text: Lets you key in your own text to show within the font windows. Reset User Custom Text: Clears any custom text you’ve keyed in.

### Show Font Previews Preference

While the Font Browser lets you weigh a range of fonts in fine detail, now and then you simply want a fast glance at the typefaces before you commit. That’s where the Preview Fonts preference steps in. Switched on by default, Preview Fonts displays an expanded window holding the font name, then the font name again rendered in that very typeface. Pick a font from this window and it drops into the Font Field across a range of text tools. You can switch this behavior off if you like by heading to DaVinci Resolve > Preferences > User > UI Settings and clearing the “Show font previews” box.

Choosing a font with the Show Font Previews preference turned on

### Spell Checking for all Text Elements

As a welcome quality-of-life lift for the spelling-challenged, DaVinci Resolve 21 ships a multi-language text spell checker. Spelling slip-ups get marked red in both the viewer and inspector. Right-click a word to peek at suggested swaps or to ignore the word.

A red underline marks each misspelled word. Right-click one and you’ll get a list of suggested fixes plus the choice to ignore it. A matching preference set also exists for Spell Checking under DaVinci Resolve > Preferences > User > Language and Spelling. The Spelling and Formatting Tool here lets you adjust the spell checker.

- Spelling Check: Tick this box to switch the spell checker on or off across the whole of DaVinci Resolve.
- Ignore Words: Opens a text box where you can feed words into the spell checker’s ignore list.
- Ignore words with numbers: Won’t flag a misspelled word when it contains numbers.
- Ignore words with ALL CAPS: Won’t flag a misspelled word when it’s in all capital letters.

TIP: You can switch off every red underline in the viewer to keep previews clean by choosing View > Show Spelling Errors on Viewer.

### Emoji and Color Fonts for Text+ and MultiText

Emoji support comes to both Text+ and MultiText, handing you the freedom to drop expressive icons and visual accents right inside your text for designs that feel more lively and engaging. Emoji go straight into the text fields with a keystroke: Control-Command-Space on macOS, and Windows key-. (period) on Windows. Beyond that, Text+ and MultiText carry sturdier font support; their handling improves for color fonts, bitmap fonts, and font styles. Where a color font is supported, extra controls for Color Palettes appear in the Text+ inspector under Advanced Controls, and there you can pick display options for the font.

### Multicam Clips can Include All Audio Tracks for Each Angle

When building a Multicam Clip there’s now an option to fold in every audio track from all the various angle source clips into the Multicam Clip. To go this route, set the Multicam Audio dropdown to “All Angles” within the New Multicam Clip dialog box. So if angle A carried four audio tracks while angle B carried five, all nine audio tracks would be on hand inside the Multicam Clip.

### Multicam Clips can Use Full Clip Extents on Creation and During Sync

When building a Multicam Clip there’s now an option to have every angle picked for the multicam clip use its full length (extents) no matter the length of the multicam clip. To go this route, tick “Use full clip extents” in the New Multicam Clip dialog box.

### Multicam and Nested Clip Match Frame Improvements

DaVinci Resolve 21 has further sharpened how match framing behaves with multicam and nested clips. Choose Clip > Match Frame to Source Clip and the underlying source clip for compound clips and multicams is located automatically. Depending on where the UI focus sits, this function operates on either the source or timeline viewer, and it will also drop out of source timeline mode automatically when that mode is active.

### Replay Control to Limit View to the Last 5 Minutes

The Replay Viewer interface gains a new Recent Five Minute button. Press it and only the last five minutes of a growing live file open in the viewer, letting you view, add markers, and so on, to just the newest five minutes of footage. This comes in especially handy when you’re cutting a long live event and need to spot something that just happened without scrubbing through the entire clip in the viewer.

### Recent Five Minute icon

### Replay Editor Allows Timeline Selection from Search Dial

You can now view and pick up to the last ten timelines in the Replay Editor. To do it, just hold the timeline button down and spin the search dial to the timeline you want on the monitor.

Replay timeline selection using Timeline button and the Search Dial.

### Replay now Allows Independent Start and End Stingers

When laying out stingers for Replay, you can now run different stingers for the start and end animations. To do it, just click the link icon to clear it, then drag the animations you want onto the start and end boxes in the interface. To go back to the default of matching start and end stingers, just click the link icon once more. Whatever animation sits in the start box copies automatically into the end box.

Once the Start and End Stinger link is broken (circled red), separate stingers can play on the way in and on the way out

### Replay Title Palette Allows Up to Six Favorite Titles

Within Replay, a six-slot favorite titles palette opens when you pick Show Titles Palette out of the Titles tab option menu. After that, just drag the title template you want into one of the numbered slots below. After that you can fire off that title template by pressing the matching title button on the Replay Editor.

### The Replay Titles Palette

### Mono Audio Appears on Both Left and Right Channels When Added to Stereo Tracks

DaVinci Resolve 21 has altered what happens when you add mono audio to stereo tracks. Drop a mono audio clip onto a stereo timeline now and the mono clip plays across both the left and right channels. It used to go to the left channel only. Within the Fairlight timeline, this clip shows in a darker shade on the right channel to signal that the effect is extrapolated across channels.

### Improved Waveforms, Markers and Fades Display for Shorter Edit Timeline Tracks

In DaVinci Resolve 21, when you work with shorter tracks on the edit page, the way those tracks display has been reworked to pack the most information onto even the tiniest track sizes. Specifically

- Audio waveforms stay visible.
- Markers shrink in size rather than just vanishing.
- Fade handles and transitions stay usable.
- The status icons and clip name won’t cover one another.
- Clip names can be switched off.

### The normal sized timeline tracks

### The smallest sized timeline tracks

### Source Timelines Support Destination Track Selectors

You can now put Destination Track selectors to work in Source Timelines to limit tracks while doing dual timeline editing.

### DRT Timeline Import Supports Link and Conform Options

Import a DaVinci Resolve Timeline (.drt) file into a project and a new Import Timeline dialog opens, laying out the timeline settings along with a checkbox option to set project settings from the imported timeline. You can now also tick the box “Automatically link to existing media pool clips” to spare yourself the step of relinking the files by hand in the Media Pool.

### The Import Timeline dialog

### Compare Timelines with Timeline Backup Snapshots

Should you want to see the changes you’ve made to a timeline measured against any of its earlier backed-up timelines, you can right-click the timeline and choose Compare with Timeline Backup to open the Compare Timeline window. The Compare Timeline window stacks the two timelines together and highlights where they differ. You pick which backup to measure against from the drop-down menu up top in the window. To dig deeper into the Compare Timeline window, turn to Chapter 34, “Creating and Working with Timelines” within the DaVinci Resolve Reference Manual. The current timeline set side by side with an earlier backup

### Subtitle Inspector Supports Find and Replace

You can now find and replace particular words or phrases across a whole subtitle track using the subtitle inspector. To switch on the find and replace tool, click the search icon sitting at the subtitle inspector’s upper right. That first selection option is where you decide whether to highlight any words that contain the text or to narrow it to finding the whole word only. Then key the text you want to find into the search field and press the Search button. Once a term turns up, it gets highlighted in yellow in the Caption tab, and you can move through found items by clicking the backward and forward arrows beside the search button. A numeric readout shows how many “hits” the tool turned up, along with which particular instance of that hit is currently picked. Tick the Replace box to open the replace tool, letting you key in the text you mean to swap for the original search tool. Click the Replace button to overwrite the chosen instance, while Replace All swaps every instance of that search in the subtitle track for the new term. Click any caption in the caption tab to load it straight into the Caption box, letting you adjust the found text.

A click on the search icon (circled red) within the Subtitle Inspector brings up the search and replace tools. Every match turns yellow across all the captions.

### Tracks Index Lets You Show or Hide Tracks

From the Tracks Index on the Edit page, you can now reveal or conceal tracks; just click the eye icon sitting to a track’s left. Concealing V1 by way of the Tracks tab within the Index

### Edit EDL Clip Name in the Edit Index

You can now edit the EDL Clip Name field straight in the Edit Index. Turn this column on by right-clicking the column header and ticking EDL Clip Name. Click in the column to add or change the clip name in the text field.

### Audio Transcription Offers External Subtitle Word Timing

DaVinci Resolve 21 can now run word timing analysis on captions you’ve keyed in by hand or imported. That means word-level highlighting no longer obliges you to generate subtitles within DaVinci Resolve, and when you fix internally generated subtitles, you can re-analyze the caption to land accurate word timing for animated subtitles.

Once you’ve made a change, hit Update Word Timings to bring the subtitle clip’s timing back in line.

Here is how to retime a subtitle / caption: 1 On the timeline, pick the subtitle clip you mean to retime. 2 Within the Video Inspector Caption tab, hit the Update Word Timings button. Pick Synchronize Word Timings off the context menu to retime every subtitle on a track Here is how to retime every subtitle clip on a subtitle track: 1 Right-Click the subtitle track header. 2 Pick Synchronize Word Timings off the context menu. In the same way, you can pull in transcriptions for media pool clips and let Resolve figure out the timing: right-click a clip and choose AI Tools > Audio Transcription > Import and Detect Timing. Pulling in a subtitle for a media pool clip and working out its timing.

### IntelliScript Supports Final Draft Imports

On top of plain text files, Intelliscript will now let you import Final Draft (.fdx) files to match and build a timeline from a script using clips in your media pool.

### Edit Page Timecode Display can Show Frames, Subframes or Audio Samples

Within the Edit page timeline, timecode can now be read carrying Frames, Subframes, and Audio Sample information instead of timecode on its own. To swap the display, right-click the Timecode display in the Timeline, then choose what you want off the dropdown menu. Picking a different timecode display type by right-clicking the timecode box.

### Up to 2x Faster Speed Warp Metal Option on macOS

DaVinci Resolve 21 on macOS now puts forward a Speed Warp Metal option for Motion Estimation within the Retime and Scaling controls. This is a purpose-built version of Speed Warp that leans on the Mac's hardware. It ought to massively quicken the DaVinci Neural Engine Speed Warp operations.

### Select all Transitions in the Cut and Edit Pages

There’s a new menu command that automatically picks every transition in a timeline, or within a set in-out range. The track selector controls can also rein it in. Timeline > Select Transitions

### Paste and Remove Attributes

### For Clip Color, Markers and Flags

Clip Color, Markers, and Flags are now parameters you can pick for the Paste Attributes and Remove Attributes commands.

### To Retain Image Position

When you’re in the Paste or Remove Attributes window, there’s now a new checkbox for Retain Image Position within the Crop section. This lets you decide whether to pin the crop parameters in place as you resize the image with the Transform tool.

### Switch Audio Channels for Multiple Selected Clips via the Context Menu

You can now switch audio channels for several clips in one go on the timeline by selecting and right-clicking the audio clips you want to change, then picking another channel option from Audio Channel in the context menu.,

### Switching the audio channels of multiple clips

### Edit Page Source Tape Supports Stereoscopic 3D and Multicam Clips
