# Fast Editing In The Cut Page (part 3)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

- Timecode: Pressing this button attempts to line up every clip in the Sync Clips window according to timecode, and it's the option selected by default.
- Audio: Pressing this button attempts to line up every clip in the Sync Clips window by examining each one's audio tracks. For it to succeed, each clip needs at least some stretch of the same audio track captured cleanly enough to be analyzed. Any tracks that couldn't be synced this way are reported back to you through an error message.
- In Point: Pressing this button attempts to line up every clip in the Sync Clips window using the In point each user has set. It comes in handy when a shared mark was filmed across all cameras, say a slate clapping shut or a camera flash.
- Out Point: Pressing this button attempts to line up every clip in the Sync Clips window using the Out point each user has set. It comes in handy whenever there was a shared tail slate.
- Sync: Pressing this button runs the Sync By method you chose above.

After every clip in the window has been synced properly, press the Save Sync button over at the lower-right of the window.

The Sync By icons within the Media Pool, running left to right: Timecode, Audio, In point, Out point

### Manually Syncing Clips in the Sync Clips Window

Should none of the Sync By tools suit the clips sitting in your bin, you're free to sync them by hand

by dragging each clip into the right spot along the Sync Clips Window timeline. For greater precision,

highlight the clip you mean to sync and tap the Comma (,) or Period (.) keys, which shift the clip

one frame at a time, either back or ahead. Holding Shift-Comma (,) or Shift-Period (.) moves the clip by 5 frames

(the default), or by however many frames the “Default fast nudge length” setting specifies, found under the General

Settings portion of the Editing panel within the User settings of the Resolve Preferences. Every clip occupies its

own track, and turning on sync lock in the right-hand Viewer keeps things from slipping by accident.

After every clip in the window has been synced properly, click the Save Sync button down in the lower-right corner of the window.

### Using Your Newly Synced Clips

Once you've saved the sync across your clips, a fresh Multicam clip turns up in the Media Pool. Switch to the Thumbnail View and a Sync icon shows on each clip you altered. Wanting to adjust the sync, right-click a thumbnail and pick Open Sync Group to bring your clips back up in the Sync Clips window. As soon as you drop your first clip onto the Timeline to serve as a reference, you're set to edit with the Sync Bin.

Sync icons (upper left arrows) identifying synced media clips

### Sync Bin Editing

What the Sync Bin layout is really about is that, rather than separately scrubbing your timeline and clips the old way, you need only scrub the timeline itself. Over in the Media Pool, every clip sharing that same timecode value scrubs along in lockstep with the playhead. That keeps the precise clips destined to slot neatly into your timeline ready and within reach at all times. Choosing this mode reshapes the Media Pool and Viewer layout on its own to better suit multi camera editing on the Cut page.

Edit in Your First Clip from the Media Pool Pick a clip to act as your base layer and drop it onto Track 1. Every other clip in the Sync Bin treats this one as its reference. After that, click the Sync Bin icon.

### The Sync Bin icon

### Media Pool in the Sync Bin

Every clip held in the bin, along with those in its subfolders, shows up in filmstrip mode. These clips get ganged together by timecode automatically and arranged in camera-number order. A further playhead sits at wherever the timeline currently is, and shifting any one of the Cut page's three playheads scrubs through all the Sync Bin clips together.

### Viewer in the Sync Bin

The Viewer changes over to a live Multi Viewer handling as many as nine cameras. Every camera carries a label and number,

while the one currently active in the Timeline gets marked in red. Any camera that wasn't active at the present

playhead time is blacked out.

You can throw the Sync Bin camera selection up full screen in the Cinema Viewer by tapping “P” on the keyboard, which gives you a bigger, more detailed look at each individual camera. Within this fullscreen mode, the Sync Bin view controls behave exactly as they do back in the normal Viewer.

The Sync Bin view as shown across the Media Pool and Viewer Select Your Timeline In Point Set the In point on your timeline by dragging the timeline playhead to wherever you'd like your media to begin. While you do, every clip in the Sync Bin scrubs right along with the playhead's position. Locating and picking edit points in the Sync Bin becomes far easier, since all the synced media options open to you sit there ready in an instant. Turn on the “Video Only” mode on the Cut page and the audio coming from the Sync Bin sources falls silent, leaving audio playback to come solely from the Timeline clips.

### Select Your Camera

Within the Multicam Viewer, choose the camera angle you intend to draw on as source material in one of these ways:

- Clicking the camera you want inside the Multicam Viewer
- Clicking that camera's number icon over in the Filmstrip Viewer
- Hitting that camera's number key on the keyboard

At that point the Viewer drops into Single Clip mode and displays the camera you picked. Heading back to the Multi Viewer takes either a click on the circled X close icon or a simple press of the Escape key. The clip lays down an In point on its own at your present timeline position, running a default duration of five seconds. From there you're free to place the clip's Out point by hand wherever you like.

### The Multicam Viewer selection

### Make the Source Overwrite Edit

With the clip's edit points settled, click the Source Overwrite button and the camera clip you chose lands perfectly in sync along your timeline. The playhead then advances on its own to that clip's Out point and the Multi Viewer comes back, leaving you instantly set for the next edit.

Camera 2 chosen with the Playhead at the In point along the Timeline, set for a Source Overwrite edit.

The finished Source Overwrite edit, with Camera 2 now cut in and the Timeline awaiting the next edit

TIP: Since it's the actual media in the Sync Bin, rather than the Timeline, that fixes how far the clips can reach, you're able to scroll beyond the Timeline's end to perform an edit. Once you're out past the Timeline's end, the playhead stands in for the Out point instead, which lets the clip backfill itself to match the precise duration needed to fill the Timeline.

### Resync Misaligned Synced Clips

When you're cutting with synced Multicam clips and a shot drifts out of sync with the timeline by accident, a warning icon flags it down in the clip's lower left. Bringing that clip back into step with the timeline is easy: click the Edit Actions icon and pick Resync Clip from the contextual menu.

Should a clip slip out of sync within Multicam footage by accident, a red sync warning indicator surfaces in the clip's lower left.

### Live Overwrite with a Mouse Drag

Lacking a Speed Editor, you can still drive the paint on capability of Live Overwrite across multicam material with your mouse. Start by opening all your multi camera angles in either the Sync Bin or the Multi Source viewers. Then just click the angle you'd like and drag sideways across the image to live paint that angle onto the timeline at the playhead's spot. Click a different angle next and drag to lay down the following camera. Thanks to the Sync Bin's distinctive way of holding every bit of footage locked together, an entire multicam production comes together remarkably fast from nothing but plain mouse drags.

Clicking and dragging on camera angle 1 in the Viewer “paints” that angle onto the timeline across a stretch matching the length of the drag. Keep clicking and dragging further angles for a speedy multicam production.

### Audio Transcription and Text Based Editing (Studio Version Only)

Knowing exactly what people said in a clip is the single most important piece of metadata it can carry. Having a shot fully transcribed helps in narrative film, where it lets you track down particular clips by the dialog written in the script, yet a transcript matters even more in unscripted documentary and news work, both for grasping which parts of the story you genuinely got on tape and for meeting an assortment of organizational, creative, and legal needs. Not long ago, transcribing audio demanded plenty of effort: a person had to play a clip in real time and key out the spoken words into a log sheet. Owing to recent strides in the DaVinci Resolve Neural Engine, your machine now handles that tedious transcription of each clip for you automatically, and crucially, with accuracy. On top of that, attaching text transcripts to your project's clips unlocks powerful new text-based editing tools for selecting, searching, and dropping clips into your timeline. CUT For a fuller treatment of Text Based Editing, turn to Chapter 40 “Text Based Editing.“
