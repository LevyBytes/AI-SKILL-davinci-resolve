# Take Selectors Compound Clips And Nested Timelines

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Take Selectors, Compound Clips, and Nested Timelines

This chapter runs through several distinct ways to collapse multiple clips into one object within the Timeline, suiting a range of different editing jobs. Take Selectors, compound clips, and nested timelines each show up as a lone clip in the Timeline, yet each one bundles its multiple clips by a different scheme. Take Selectors stack multiple clips vertically, which makes it simple to tie clips together so you can flip between them with ease. Compound clips and nested timelines instead lay multiple clips out horizontally, letting you handle long or short runs of clips inside an edit as a single clip whenever that's handy.

### Take Selectors

DaVinci Resolve's Take Selectors hand you a means of juggling several takes or versions of one particular clip within the Timeline. They shine when you want to keep a number of strong takes on hand for scenes where you or the client can't settle on the best one, or when you're holding onto several versions of VFX clips that keep getting revised. Drop a batch of clips into a Take Selector and only one of them shows in the Timeline, but you can open that Take Selector and flip to whatever other take or version is tucked inside, changing which clip the Timeline displays at any moment you like. A Take Selector displayed open, holding a number of alternate takes inside it Building, using, and filling take selectors is straightforward. Once you've dropped a batch of clips into the Take Selector, dragging any take slips that clip's media range until it lines up with the rest of the takes, or clicking a take makes that clip within the Take Selector the one shown in the Timeline, after which closing the Take Selector locks in your change.

A closed Take Selector looks like an ordinary clip carrying a badge Once closed, multi-take clips behave like any other single clip in the Timeline, ready to be edited, trimmed, composited, graded, and rendered. A Take Selector badge sits to the left of the name on whichever clip carries it, signaling its status; a double-click on that badge opens the Take Selector so you can tweak what's inside.

Methods of using Take Selectors:

- To create a Take Selector: Right-click whatever clip isn't a title or generator, then pick Take Selector off the contextual menu. Up comes the Take Selector interface, which switches off the rest of the Timeline for the moment while you handle the Take Selector's contents.
- To populate a Take Selector: Drag whatever clip you like out of the Media Pool into the Take Selector, where it shows up “stacked” atop the original clip in the Timeline.
- To choose the current take: Click any clip inside the Take Selector to highlight it, then click the close button up at the Take Selector's top-left corner. The next time you open the Take Selector, the current clip sits at the foot of the stack, marked by a star in its top-left corner. With no choice made, the current take falls back to whichever clip was added to the Take Selector last.
- To make a Take Selector ripple the Timeline whenever you pick a take of a different length: Hit the Ripple Take button, found in the top-right corner of the Take Selector panel, immediately to the left of the trash can button. Switched on, picking a take longer or shorter than the current one ripples the Timeline. Switched off, picking a longer or shorter take will either write over the next clip to the right, or leave a gap behind.
- To slip a clip within the Take Selector: Drag any clip leftward or rightward to slip the media range that shows up across the Take Selector's span in the Timeline. This comes in handy for lining other takes up to land on the same narrative beat as the first take you went with.
- To remove a clip from a Take Selector: Click whichever clip you'd like gone to select it, then click the trash can button at the Take Selector's top-right corner. That take vanishes from the Take Selector.
- To close a Take Selector: Click the X close button, or hit the escape key. Whatever take was selected becomes the clip that the Timeline now shows.
- To reopen a Take Selector: Double-click the Take Selector badge sitting just before a clip's name, or right-click a multi-take clip and select Take Selector from the contextual menu.
- To eliminate a Take Selector leaving only the take you want: Shut the Take Selector if it's open, then right-click that clip in the Timeline and pick Finalize Take off the contextual menu.

### Compositing and Grading Take Selectors

Because compound clips behave as a single clip within the Timeline, they show up as a single MediaIn node on the Fusion page, and you grade them just as you would any other single clip on the Color page. For Take Selectors, though, the composite or grade lands on the Take Selector itself; flip to any other take and it carries that same composition and grade. NOTE: Whatever keyframing you perform is measured against the Timeline of the Take Selector as a whole. So if you build a keyframed effect on either the Fusion or Color pages with take 1, then flip over to takes 2, 3, or 4, the timing may not line up precisely and you might have to tweak things.

### Compound Clips

You can grab a run of clips in the Timeline, whether they're edited back-to-back in serial or layered and stacked in parallel, and convert them into a compound clip, a single Timeline clip that's really made up of numerous other audio and video clips packed inside. This lets you treat a block of clips as though it were one unit, run by a single set of Inspector controls, and joinable to another clip in your timeline through a single transition. Editing a compound clip plays out just like editing any other clip type. The same methods edit, trim, and delete them. On top of that, you can rename compound clips and decompose them back into their constituent clips right within the Timeline. Building a compound clip from a selection: 1 Select a range of clips.

Picking a stretch of clips to fold into a compound clip 2 Right-click whichever of the selected clips you like and pick New Compound Clip. 3 Optionally type a start timecode along with a name, then click Create.

### The New Compound Clip Properties dialog

A compound clip gets built that stands in for the original clips you'd selected on the Timeline. On top of that, a copy of that compound clip turns up in the Media Pool's currently selected bin.

### The resulting compound clip

To create a compound clip by In-Out range: 1 Mark off a run of clips with In and Out points on the Timeline. This lets you grab partial stretches of a clip for the compound, instead of the whole clip. Every track inside the In-Out range gets included, even where a track is disabled or auto select is off.

Marking off a span of clips by In and Out points to fold into a compound clip. Bear in mind that this marking grabs only portions of the range's opening and closing clips.

2 Right-click on the timeline range and pick Convert In and Out to Compound Clip.

A right-click on the In-Out range (the gray bar) over on the Timeline pops the context menu up 3 Optionally type a start timecode along with a name, then click Create.

How the compound clip's bounds end up, carrying only the media that fell inside the precise In-Out range. To rename a compound clip: Click the compound clip's name twice in the Media Pool to select the name text. Type a fresh name, then press the Return key to confirm the change.

To edit a compound clip: 1 Right-click any compound clip and pick Open in Timeline off the contextual menu. The Timeline refreshes with that compound clip's contents, which you're free to re-edit however you like.

An open compound clip in the Timeline 2 Once you're finished and want the original timeline back, double-click the name of the enclosing timeline in the path control over at the Timeline's bottom left-hand corner.

The path control that lets you shut the compound clip Breaking a compound clip down into its separate clips within the Timeline:

- Right-click any compound clip and pick Decompose in Place off the contextual menu. The individual clips it was built from take the compound clip's place.

Editing a compound clip out of the Media Pool onto the Timeline as separate clips: 1 Pick Edit > Decompose Compound Clips on Edit so a check appears beside the menu item. 2 Apply whichever editing command suits you, apart from Fit to Fill or Place on Top, to bring a compound clip out of the Media Pool or Source Viewer onto the Timeline, editing it as a run of individual, decomposed clips. To change the timecode of a compound clip: Both multicam and compound clips let you alter the starting timecode. To do it, right-click the multicam or compound clip in the Media Pool and pick Starting Timecode off the context menu. A Set New Start Timecode box appears, where you type the fresh starting timecode you'd like and click OK.

### Individual Destination Controls with Decompose on Edit

Under Edit > Edit Options, with the Decompose Compound Clips on Edit setting switched on, compound clips and timelines that are either selected in the Media Pool or loaded into the Source Viewer gain track destination controls drawn from the underlying clip. In practice, that means once you load into the Source Viewer a timeline holding three video tracks and two audio tracks, the timeline track destination controls then offer up, for track destination patching, three video tracks plus two audio tracks.

The tracks that become available for track destination tracking once Edit > Edit Options > Decompose Compound Clips on Edit is enabled

### Compositing With and Grading Compound Clips

Given that a compound clip acts as one clip inside the Timeline, it surfaces as a single MediaIn node on the Fusion page, and on the Color page you grade it as a lone clip. Even so, should you want to apply effects individually, tweak the RAW camera options, or grade the source clips packed within that compound clip, run the Open in Timeline command to reach its building-block clips, then open up the Fusion or Color pages, where each separate clip waits for compositing or grading on its own. With that finished, return to the Edit page, shut the compound clip, and from then on it reverts to a lone clip every time you open up the Fusion and Color pages.

### Nested Timelines

Whole timelines, and parts of them, can be edited inside other timelines, either in part or entirely. As an example, when you've cut a program into scenes or reels so that each reel lives in its own separate timeline, you can edit every one of those timelines together, back-to-back, into a single timeline so as to put together a finished program.

Multiple timelines edited together into a single sequence

Clips that are nested timelines turn up with a distinctive badge sitting left of the timeline name.

### The badge that indicates a nested timeline

Timelines edit much like any other clip; you can pick one or more timelines and drag-and-drop them onto another timeline, drop them onto the Timeline Viewer editing overlay, or wield the toolbar editing buttons or keyboard shortcuts to edit them, exactly as you would any other clip. Beyond that, selecting several timelines within the Media Pool, then right-clicking and choosing Create Timeline Using Selected Clips, quickly gathers a batch of timelines into one nested sequence. The lone exception: you have to drag-and-drop a timeline into the Viewer if you mean to use it for setting In and Out points, given that double-clicking a timeline, or selecting a timeline and pressing Return, merely opens it into the Timeline Editor. You can, however, set In and Out points for timelines within the Filmstrip of the Media Pool, or you can edit one timeline into another in full, then trim its head and tail down to only what you need. A double-click on a nested timeline opens it into the Source Viewer for trimming, precisely like any other clip.

### Re-Editing a Nested Timeline

When you'd like to edit a nested timeline's contents, right-click it and pick Open in Timeline. In contrast to compound clips, no path control turns up here, since all you've done is open the original timeline. To get back to the timeline you came from, find and double-click it in the Media Pool, or select it via the Timeline drop-down sitting atop the Timeline Viewer. Editing an original timeline leaves untouched the running length of nested instances of that timeline living inside other timelines. Should you trim or delete clips in the original timeline that also show up in nested instances of it, then those stretches of the nested timeline simply go black.

### Swapping the Contents of the Source Viewer and Timeline

While you edit part of one timeline into another, it can help to view the contents of a timeline that's open in the Source Viewer inside the Timeline Editor. To pull that off, pick Timeline > Swap Timeline and Source Viewer (Command-Page Up). Whatever timeline sat open in the Source Viewer moves into the Timeline Editor, while the one that had occupied the Timeline Editor moves into the Source Viewer. That makes marking In and Out points easier as you watch the precise clip boundaries, ahead of hitting Command-Page Up once more, which trades the two panels' contents back and readies you for the next edit.

### Editing Source Media From a Timeline or Compound Clip

When you've got a timeline holding clips you'd like edited into another timeline, but as source clips rather than nested timeline segments, you can switch on Edit > Decompose Compound Clips on Edit. This mode decides whether a timeline gets edited into another as a nested timeline, or instead immediately broken down into its constituent source clips. Switching the mode on lets you edit source clips out of a timeline by drag-and-drop, 3-point edits, or whatever other method suits you. To return to editing nested timelines, switch Edit > Decompose Compound Clips on Edit off. The mode is particularly handy for workflows where you're piecing together “selects” timelines holding the best bits of various interviews or performances, which you intend later on to edit as sources into the actual program you're cutting. Marking Clips in Timelines Loaded into the Source Viewer As you edit Source Media out of a timeline that's loaded into the Source Viewer, you can rely on Mark Clip (the X key) to drop Viewer In and Out points lining up with the start and end of whichever clip crosses the playhead inside that timeline. This makes it simple to edit a single clip out of a Timeline in the Viewer into your program, entirely on its own.

(Left) a timeline sitting in the Source Viewer; (Right) a press of X drops In and Out points onto the clip under the playhead, set to edit

### Decomposing Nested Timelines

There are two principal ways to turn a nested timeline back into its constituent clips.

### Decomposing in Place

To break a nested timeline apart once it's already sitting edited inside another timeline, right-click it and choose Decompose in Place. The same works across several selected nested timelines all at once.

### A nested timeline

### The result of using Decompose In Place

Should the decomposed clip end up with extra audio, video, or subtitle tracks, then more tracks get added to the Timeline to fit them. If that poses a problem, you can rearrange the clips Decomposing Nested Timelines While Editing When you'd like to edit a whole timeline into another timeline purely as the source clips, switch on Edit > Decompose Compound Clips on Edit, then edit that timeline into your program by whatever method suits you, as laid out earlier in this chapter.

### Compositing and Grading Nested Timelines

Much like compound clips, nested timelines behave as a single clip within the Timeline; they turn up as a single MediaIn node on the Fusion page for compositing, and you can grade them as one clip on the Color page. That said, when you'd like to add effects to or grade the original clips inside a nested timeline one by one, you can either open that timeline out of the Media Pool, or right-click that clip and pick Open in Timeline so as to reach its constituent clips for compositing or grading.

### Audio Buses in Nested Timelines

Nest a timeline inside another timeline that's got buses configured for mixing on the Fairlight page, and every Sub and Aux routing behaves as intended within the nested timeline, which surfaces all channels of Main 1 in the enclosing timeline. Seen in this light, the nested timeline's audio works out to a submix that routes its resulting audio onto whatever audio track it lands on when edited. To read more about Buses and audio mixing broadly, consult Part 13, “Fairlight.”

### Match Frame for Nested Timelines and Compound Clips

The Match Frame to Source Clip feature works for compound clips along with nested timelines. Depending on the context, the relevant underlying source clip gets loaded into the Source Viewer. With a compound clip or timeline loaded into the Source Viewer, running a match frame (from the Source Viewer) has DaVinci Resolve give priority to locating a nested copy of the clip in the timeline so as to carry out the match frame. Where no nested copy turns up, the match frame runs automatically to line the underlying source clip up against a timeline instance. In the same way, running the match frame from the timeline (or timeline viewer) has DaVinci Resolve first try to locate the same underlying clip and frame inside the compound clip or nested timeline loaded into the Source Viewer. Should the frame prove impossible to locate, then match frame to source runs automatically as usual. This proves especially handy while you compare two different versions of a timeline and bounce between them.

### Converting Compound Clips or Timelines to Multicam Clips

Compound clips and timelines can be converted into multicam clips for smoother editing by way of the Edit page's Multicam Editing interface. The conversion only runs one way. There's no converting a multicam clip back into a timeline or compound clip. Should you want the original timeline or compound clip kept, be sure to duplicate it first and convert the duplicate. To dig deeper, consult Chapter 42, “Multicam Editing.” Turning a compound clip or timeline into a Multicam clip: Right-click the clip or timeline in the Media Pool and pick “Convert Compound Clips (Timelines) to Multicam Clips” off the drop down menu.
