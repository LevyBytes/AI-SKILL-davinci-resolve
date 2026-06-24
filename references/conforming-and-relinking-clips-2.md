# Conforming And Relinking Clips (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Accurate timecode: Vital for every clip. To start with, each clip ought to carry a valid timecode track, and — it hardly needs saying — that timecode should line up with the timecode borne by every other instance of the same media file within a given project. Where a clip’s timecode gives trouble, DaVinci Resolve offers tools for editing or offsetting timecode to allow for known discrepancies. Out of the box, the “Use Timecode” project setting reads “Embedded in the Source Clip,” so timecode is drawn from the embedded timecode track within a QuickTime file or an MXF file, or else out of a DPX frame file’s header data. You may instead pick the “From the source clip frame count” option, which lets timecode be taken from the Source clip’s frame count for image sequences.
- File names: With the “Assist using Reel Names” checkbox — found within the General Options panel of the Project Settings — switched off (its default), DaVinci Resolve is compelled to conform clips by file name as it brings in XML and AAF projects. File names come into play solely when conforming XML or AAF files, or when importing a DaVinci project; they are never used when conforming EDLs.
- Reel Name: Enters the conform process only when “Assist using Reel Names” sits on in the General Options panel of the Project Settings. Tagging your media with reel names is not mandatory, though it is advised, and it can smooth media management for certain operations — EDL workflows above all. Still, if conforming clips gives you grief while “Assist using Reel Names” is on, switching it off makes a sensible first troubleshooting move.

The way DaVinci Resolve pairs media files with clips in an imported project hinges on the manner in which you bring that project in.

### Defining Clip Metadata When Adding Media to the Media Pool

For pipelines in which you add media files to the Media Pool by hand — whether you are cutting from scratch in DaVinci Resolve, gearing up to process dailies, or taking a separate step ahead of importing EDL, XML, or AAF project files and reconforming them onto a higher-quality set of media than was first used to edit — the rules governing how clip metadata is set in readiness for conforming differ somewhat.

- Timecode: Worked out from the “Timeline Frame Rate” value, which lives in the Master Project Settings panel of the Project Settings.
- Reel Names: Settled by two things — whether the “Assist using Reel Names from the” checkbox sits on or off (you will find it in the General Options panel of the Project Settings), and which option you picked. Reel names may be pulled dynamically — so each time you alter this setting, the Media Pool’s reel names refresh to match — or they may be set by hand, in which case different clips can lean on different reel name extraction methods.
- Clip Names: Read and held; drawn on for AAF and XML imports, yet skipped for imported EDLs.

### How Reel Names Are Identified

Of the settings governing how conform behaves, the “Assist using Reel Names” checkbox — over in the General Options panel of the Project Settings — ranks among the weightiest. Out of the box it is off, with reel names blank. That suffices for conform workflows where the file path or file name plus source timecode is all it takes to pin each media file to its clip. Yet when reconforming your project’s clips demands more, ticking the “Assist using Reel Names” checkbox lets DaVinci Resolve fall back on one of four methods to set reel names automatically across every Media Pool clip.

### Automatically Defining Reel Names

Lean on the “Assist using Reel Names” options — these sit in the General Options panel of the Project Settings — and reel names are pulled dynamically. What that means is that whenever you switch the reel name extraction method in the Project Settings, the reel names across every Media Pool clip refresh on their own to match. You can watch this play out in the Reel Name column, which shows once the Media Pool is put into List view. Flip the “Assist using reel names” options from “Source clip file pathname” over to “Mediapool folder name,” for instance, and the Reel Name column’s contents visibly shift. It comes in handy when you import a project whose clips all settle their reel name the same way. Manually Choosing Reel Name Definitions for Individual Clips Through the Clip Attributes dialog you also get to choose by hand the criteria by which one or more selected Media Pool clips have their reel names set. That helps where particular clips in a project must lean on a different reel name extraction method, or on reel names typed in by hand.

To set reel names by hand for one or more clips: 1 In the Media Pool, pick one or more clips. 2 Right-click one of the chosen clips and pick Clip Attributes off the contextual menu. 3 Open the Reel Name panel within the Clip Attributes dialog, pick a fresh option, and click OK. After you have used Clip Attributes to rewrite a clip’s reel names, those clips cease refreshing automatically whenever you adjust the “Assist using Reel Names” options back in the General Options panel of the Project Settings. For more on wielding Clip Attributes, turn to Chapter 19, “Using Clip Metadata.” Methods of Defining Reel Names Five options exist for working out automatically how reel names are pulled from the source media while “Assist using Reel Names” is on, plus a single option in the Clip Attributes Reel Name panel for setting them by hand. Reel names matter a great deal in EDL and AAF workflows, though they carry less weight in XML‑centric ones.

- Source clip file pathname: Derives the reel name by pulling it from each media file’s path. With this you can draw a reel name out of the whole file name or part of it, or out of the whole — or part — of any folder name along the path that wraps the file. You spell out that extraction through the Pattern field.
- Pattern: A code setting out how a reel name ought to be pulled from the source clip pathname. Fuller notes on building patterns come later in this chapter.
- Media Pool folder name: Here the reel name is taken from whichever bin in the Media Pool holds the clip. In a stereoscopic workflow, say, you might export offline stereo media using the “Left” and “Right” bin names — the bins they live in — as reel names. Another instance: VFX undergoing incremental processing, filed into individually named bins like “VFX_Tuesday_10-12.”
- Embedding in Source clip file: Handy with file formats that bury the reel name inside the media file. Among the formats able to carry reel name header data are Blackmagic RAW (and other digital cinema cameras), QuickTime files born of Final Cut Pro, and DPX frame files.
- Source clip filename: Where no reel number is defined, it is frequently simplest just to fall back on the Source clip filename.
- User Defined: This choice surfaces solely when you hand-edit the Reel Name for one or more selected Media Pool clips by way of the Clip Attributes dialog. Picking User Defined lets you type whatever text string you wish to serve as the reel name.

One more checkbox is on hand, “Extract reel names from EDL comments,” which chiefly serves legacy workflows where you conform an EDL exported out of Final Cut Pro 7 against camera original R3D media. Extract reel names from EDL comments: Certain media file formats — R3D among them — carry reel names, taken from the file names, that run longer than the eight characters a standard EDL permits. This option lets DaVinci Resolve lift reel names out of suitably formatted EDL comments, like those Final Cut Pro 7 produces.

### Using the Pattern Field

When the Pattern option is your route to pulling the reel name out of a clip’s source file pathname, you are free to craft your own search pattern, letting DaVinci Resolve lift the reel name in very precise ways that suit more unusual workflows. A pattern is read from right to left, working through a clip’s file path piece by piece — beginning at the file name, then weighing each enclosing directory’s name to its left. Every pattern is a string of text characters and “wild card” operators in distinctive combinations that mirror the length and the names along the file path. Below are the search characters at your disposal.

### Extraction Pattern Operators

Hunts for any single character. Drop in one question mark for every ? character you mean to catch. ?? catches two characters, 02 for instance; ???? catches four, such as 0002.

- A wildcard matching any run of zero or more characters.

%R

Marks where the reel name truly sits. A reel name may hold any character, yet it must not include a directory separator (forward slash).

%\_R

Pulls the reel name while stripping away the R3D file name underscores seen in EDLs from Final Cut Pro 7 or older.

%D

Catches any directory name or file name. Where it stands as a pattern’s final operator, leave off the forward slash.

/ Serves to part any two operators

Should you be building a fresh extraction pattern for some one-off workflow, a test dialog lets you trial different patterns before turning them loose on your project. To test the extraction path: 1 Switch on “Assist using reel names from the” and click the Test button beside the current Pattern in the General Options panel of the Project Settings. Up opens the “Specify Reel Extraction Pattern” dialog. 2 Key the extraction patten you wish to trial into the Pattern field. 3 By whatever means you favor, locate the file path of the media file the pattern is to be trialed against, then paste or type that path into the Sample Path field. 4 Click Test. 5 Where the reel name shown beneath proves correct, click Apply, which drops the pattern into the Pattern field over in the Project Settings’ General Options panel. Where it proves wrong, tweak the pattern and have another go.

### Examples of Reel Name Extraction Patterns

For a clearer grasp of how this works, the examples below lay out the assorted ways reel names get extracted. Between control parameters, the / acts as the separator.

### Example 1

In this example the reel name lives inside the clip’s parent folder name.

- Pattern: \*/%R/%D
- File path: vol0/MyMovie/Scans/004B/Frame[1000-2000].dpx
- Reel name: 004B

Since parsing runs right to left, begin your read of this pattern at its right end. Here the %D lands on the file name “FrameNNNN.dpx,” where NNNN is the frame number carried by each file of the clip. Step left past the file name and the /%R/ chunk of the string comes next. It declares that the reel name will be the full name of the parent directory sitting immediately above the file. Then the \* leading the string tells it to match any pathname ahead of the directory name holding the reel name. Such a string would locate the parent directory no matter how many levels deep it lies along the directory path.

### Example 2

This time the reel name sits inside the clip’s parent folder name and carries the reel name as a prefix.

- Pattern: _/????%R/%D or alternatively _/Reel%R/%D
- File path: /vol0/MyMovie/Scans/Reel1234/Frame[1000-2000].dpx
- Reel name: 1234

Both of these extraction patterns yield an identical result, and both echo the first example. The reel name still rests in the parent directory name, but here the fixed characters “Reel” precede it. That first pattern, with its ????, would in fact match any 4 characters ahead of the reel name. The second pattern is tighter, matching only the word “Reel” within the directory name.

### Example 3

Here the reel name resides in the parent folder name found two directory levels above.

- Pattern: \*/%R/%D/%D
- File path: /vol0/MyMovie/Scans/004B/134500-135000/Frame[1000-2000].dpx
- Reel name: 004B

Once more this mirrors Example 1; what sets Example 3 apart is that here the reel name is the directory name standing two levels up from the clip, where in Example 1 it sat just one level up in the directory name.

### Example 4

Last of all, the reel name turns up buried within the material’s clip name.

- Pattern: \_/Reel%R\_\_
- File path: /vol0/MyMovie/Scans/Reel004B\_[1000-2000].dpx
- Reel name: 004B

This case demonstrates one way to pull the reel name from the clip’s file name. Once again reading from the right, the two pattern characters “_\*” catch any string of characters running up to the first underscore. Here that sweeps in the file extension (.dpx) along with the frame number slice of the file name. After that, the “/Reel%R” characters mark the reel name as whatever falls between the “/Reel” and the _ character. The \* heading the pattern will match a file path nested any number of directories deep ahead of the file name.

### Conform Missing Clips by Importing Their Source Media

A timeline holding one or more missing clips means the tie between that timeline clip and the Media Pool has snapped, because no matching clip exists in the Media Pool. Should you choose to import clips by hand into the Media Pool to stand in for missing ones, the outcome rests on one checkbox — “Automatically conform missing clips added to Media Pool” — located in the General Options panel of the Project Settings. Do bear in mind that the “Auto conform clips with media added into Media Pool” setting has to be off if you work collaboratively. While that “Auto conform clips with media added into Media Pool” setting stays on in the General Options panel of the Project Settings, DaVinci Resolve refreshes the conformed tie between the clips you drop into the Media Pool and the missing clips across your project’s timelines on its own. At the same moment, DaVinci Resolve also refreshes the conform tie of every other timeline clip whose Conform Lock Enabled is off. The whole of this happens the instant you import the clips. If, however, “Auto conform clips with media added into Media Pool” is off as you import extra clips into the Media Pool, DaVinci Resolve will make no automatic reconform attempt, leaning on you instead to reconform offline or missing clips by hand through one of the many manual reconforming methods on offer — Reconform From Bins or Conform Lock With Media Pool Clip among them. For more on adding clips to the Media Pool by hand, turn to Chapter 18, “Adding and Organizing Media with the Media Pool.”

### Using the Import Additional Clips Command

When a timeline turns out to be riddled with missing clips that have no matching Media Pool clips, a simple remedy exists that automates compiling the list of what is absent so every missing clip can be imported and conformed in one stroke. It applies to missing clips alone, never to unlinked clips (for those, reach for the Media Pool’s Relink command).

### Conformed Timeline showing missing clips

To bring in missing clips and reconform them to the Timeline: 1 On the Edit page, right-click a timeline in the Media Pool that carries missing clips, and from the Timelines > Import submenu pick one of these: Timelines > Import > Additional Clips With Loose Filename Match: Sweeps the Timeline for every missing clip and asks you to name a media directory to try conforming them against, pulling only the needed media into the Media Pool. The “Loose Filename Match” command turns a blind eye to file extensions, so you can swap offline media for online media in another format. Timelines > Import > Additional Clips With Tight Filename Match: Sweeps the Timeline for every missing clip and asks you to name a media directory to try conforming them against, pulling only the needed media into the Media Pool. The “Tight Filename Match” command hunts solely for media whose file extensions match exactly. 2 In the dialog that opens, pick the directory holding the remaining media to be conformed and click OK. Provided the media files in your chosen directory satisfy the conditions for matching the current Timeline’s missing clips, the required clips drop into the Media Pool and conform to the timeline automatically.

### Using Conform Lock As a Command

If, for any reason, an unlinked timeline clip flatly refuses to conform to a Media Pool clip even when you are sure it is there, the “Conform Lock with Media Pool Clip” command lets you force a Timeline clip to conform to a Media Pool clip of your choosing. This command quietly sets aside a target clip’s Conform Lock Enabled setting and disregards file names and reel names, conforming the target clip instead to another clip you handpicked, while timecode still serves to align the clip being conformed with the one originally in the Timeline. To conform lock a Timeline clip to another clip in the Media Pool: 1 Pick a clip in the Media Pool. For Force Reconform to work, the Media Pool clip you pick must run as long as — or longer than — the Timeline clip you pick. 2 Right-click an unconformed Timeline clip and pick “Conform Lock with Media Pool Clip” off the contextual menu. The chosen Timeline clip then conforms to your chosen Media Pool clip one of two ways: Where the chosen Media Pool clip’s timecode matches the chosen Timeline clip’s: the new clip conforms flawlessly to the original. Where it does not match: the new clip conforms so that the Media Pool clip’s first frame lines up with the first frame of the reconformed Timeline clip and fills the same duration. 3 Right-click that clip once more and you will find Conform Lock Enabled switched on, a sign the clip has been conform locked to media it did not originally match.

### Relinking Clips to Media Files on Disk

The simplest and most familiar way to relink project clips that have either dropped offline or bonded to the wrong set of media files on disk is the aptly titled “Relink Media” or “Relink selected clips” command. Mind you, the Relink command serves only clips that are unlinked; it does nothing for missing clips, which have no matching clips in the Media Pool at all. The Relink command is the most pliable route to tying your project’s Media Pool clips back to clips in a file system directory you nominate, leaning on file name and timecode as the chief criteria for rebuilding the link between each clip and its media file on disk. It is a strong choice for relinking media that has been shifted elsewhere or rearranged under a different file structure on disk. To relink all unlinked media: 1 Click the orange Relink icon in the page’s Media Pool. 2 Click the Locate button beside whichever volume(s) are missing, and point to a directory where the absent files now live 3 Should the quick search the Locate buttons kick off fail to turn up media you know is present, you can launch a thorough deep disk search by clicking the Disk Search button. 4 If still other clips elude the search, you are asked either to nominate a wholly different directory and press on, or to quit. To relink selected clips: 1 Highlight one or more offline clips to relink, or highlight a bin in the Media Pool bin list holding clips you want relinked, then right-click one of the chosen clips or the chosen bin and pick “Relink Selected Clips” off the contextual menu. 2 Once the Relink File dialog opens, point to a directory in which to hunt for the files you mean to relink to, and click OK. DaVinci Resolve sets out to find every clip bearing a matching file name within the subdirectories of the directory you named, using the relinked clips’ original file paths to do so as swiftly as it can. Because it first checks the directories the clips originally lived in, relinking can move quite quickly. 3 Where any clips slip past the step-2 method, a second dialog offers you a “deep search.” Click Yes and DaVinci Resolve combs every subdirectory of the directory you picked in step 2 for each clip. That can run a good deal longer, yet it ought to succeed outright so long as the needed media lies somewhere inside the chosen directory structure. 4 If yet more clips still cannot be located, you are asked either to nominate a wholly different directory and carry on, or to quit.

### Using “Change Source Folder” to Relink Clips

When you have used your file system to relocate media belonging to a DaVinci Resolve project yet left the directory structure organizing it untouched, the “Change Source Folder” command will swiftly relink selected Media Pool clips to the media’s new file path on disk, taking the original file paths as its guide. Where possible, it is a sound relinking method for projects living on a SAN, where you would rather not court the painfully long search times the Relink command’s more flexible trawl through a nested folder hierarchy can invite. To relink your Media Pool clips to a fresh location: 1 Highlight one or more Media Pool clips, then right-click one of them and pick “Change Source Folder” off the contextual menu. The Relink Media window opens, showing the material’s original path together with controls that let you name a fresh directory. 2 To the right of the “Change To” field, click the “Browse” button, then use the file navigation dialog to track down the media file’s new location, select it, and click Open. 3 Having found the right media file, click Change; otherwise click Cancel.

### Using the “Reconform From Bins” Command

The “Reconform From Bins” command offers a way to reconform several timeline clips in one go to a particular bin (or bins) of clips whose metadata matches. Using it begins with selecting the timeline clips you want reconformed (all of them, or merely a subset) and switching off Conform Lock Enabled; then, via the Reconform From Bin command, you handpick another bin of Media Pool clips to reconform against. A key trait of the Reconform From Bins command is that DaVinci Resolve reconforms only the timeline clips it can match to source clips in the selected Media Pool bins. Every timeline clip it cannot match is left untouched. That makes Reconform From Bins the perfect command when you have imported a subset of clips to the Media Pool that needs reconforming to clips scattered through an existing timeline. You could, for example, turn to this method to:

- Swap transcoded versions of a timeline’s clips for the original camera raw clips.
- Swap a timeline’s earlier VFX clip versions for newer ones.
- Swap the offline-quality media you have worked with thus far for online‑quality media.
- Swap the temp clips you were first handed for rescanned or recaptured
