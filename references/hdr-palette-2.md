# Hdr Palette (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

Once your opening round of global tweaks is in place, you have the option of pushing further into tonally‑specific territory using the Zone-based color and contrast controls over on the left. Those split the picture into several overlapping “zones,” a notion that loosely echoes Ansel Adams’ zone system, where images are carved into tonally-specific bands by luminance: starting at pure black, climbing through ever-lighter shadows, arriving at 18% gray as the central value around which most images' midtones pivot, then continuing upward through ever-lighter highlights toward the final zone of pure white.

### Simplified illustration of Ansel Adams’ zone system

Whereas Adams’ zone system existed to coach people in thinking about how to use the photographic medium's available range while exposing a shot, the HDR palette's zones turn that idea into a working tool, letting you apply tonally-specific Color Balance, Saturation, and Exposure changes that touch only the shadows or highlights sitting inside that zone.

With the default preset loaded, your image's shadows break out into overlapping Shadow, Dark, and Black zones, and its highlights break out into their own overlapping Light, Highlight, and Specular ranges. How all of these zones relate is laid out in the chart that follows.

A rough depiction of the HDR palette's overlapping zones, each of which can be tuned on its own NOTE: Throughout this section, every example keeps Timeline to Output Tone Mapping set to None so the ramp gradient stays linear for the sake of this walkthrough.

### Zone-Based Color Adjustments

Grasping how the changes you make across these overlapping zones play off one another is central to knowing what the HDR palette can do for you. Bear in mind that every zone can be customized, but the following describes how the default zone definitions operate so you can dial in detailed image changes. To keep things clear, Zone adjustments here are demonstrated on a linear ramp gradient image, making it obvious which tonal slice of each image each control touches.

- The Light and Shadow zones carry the widest definitions of any zones. Between them they span your image's whole tonal range. The two gently overlap by two stops right at the middle of that range (50% gray or 18% exposure), and that is precisely where Light's changes blend into Shadow's, so both fade softly into one another. Adjusting exposure on this pair lets you shape overall image contrast by selectively squeezing or stretching contrast in the shadows and/or highlights against each other. Reaching for the color controls lets you push broad color shifts into the upper (highlights) and/or lower (shadows) end of the image's tonality.

A ramp gradient with color tweaks applied, marking out the Light zone (tinted green) and the Shadow zone (tinted orange)

- The Dark and Black zones sit over two successively lower luminance bands of the Shadow zone. Dark comes in handy for tuning the color or contrast of the deeper shadows, while Black serves as a trim for working the very darkest portions of an image. Every change you make to Dark folds in with whatever you have done to Shadow, and every change to Black folds in with what you have done to both Dark and Shadow. That way, all the color changes you make across the overlapping Shadow zones blend together cleanly into the final look, as the following ramp gradient shows.

A ramp gradient with color tweaks applied, where the Dark zone (tinted blue) laps over the Shadow zone (tinted orange)

- The Highlight and Specular zones sit over two successively brighter luminance bands of the Light zone. Highlight lets you tune the color and/or contrast of the brightest highlights, while Specular acts as a trim for working an image's very brightest highlights. Every change you make to Highlight folds in with whatever you have done to Light, and every change to Specular folds in with what you have done to both Highlight and Light. That way, all the color changes you make across the overlapping Highlight zones blend together cleanly into the final look, as the following ramp gradient shows.

A ramp gradient with color tweaks applied, where the Highlight zone (tinted yellow) laps over the Light zone (tinted green). As is apparent, each of these zones permits targeted adjustment of whatever parts of the image land inside that zone's luminance band (as set on the Zones panel), while also giving you a say over how gradually one change melts into the next so unwanted contouring is avoided. As you tweak each zone's Range and Falloff through the various sets of zone controls, they cooperate to massage the image's contrast and color seamlessly, much as a tighter, more restrained take on the Custom Curves would. You can in fact watch the exact change you are making by revealing the Zone graph.

(Left) Pushing the Light zone's Range up so the Shadow zone's reach grows, (Right) That very same change as it looks in the Zone graph Operating like this delivers enormous adjustment precision with no curves or qualifiers required. As one example, zone-specific Color Balance controls let you grade highlights and shadows independently via the Shadow and Light zone controls, swiftly conjuring a warm/cool split lighting look. The upshot is that building dynamic grades becomes both faster and more inventive.

(Left) The starting image, (Right) Warming the highlights and cooling the shadows by way of the HDR palette (overstated for print) For the next example, the Dark zone’s Color Balance control drops a touch of green into the image's darker shadows, while the Black control cancels that green back out in the very blackest shadows.

(Left) The starting image, (Right) Adding green to a slim band of shadows by way of the HDR palette

### Zone-Based Exposure Adjustments

Every zone carries its own Exposure control, letting you pull image contrast out from that zone’s Min or Max range boundary either downward into the shadows or upward into the highlights. On the Zone graph (over on the Zone panel), these exposure changes ride a scale graduated in stops, which makes grading wide dynamic range material feel more like working with photography.

The Zone graph's scale lays out the shadow and highlight ranges in stops, anchored to 0 standing for 18 percent photographic gray On that scale, 0 stops lines up with photographic 18% gray, sitting at the center of every image's tonal range. From there shadows run leftward across -8 stops and highlights run rightward across +8 stops, with each stop standing for either double the light (stopping up) or half the light (stopping down). Paired with Resolve Color Management, this range is built to cover whatever SDR or HDR target you intend to master to. Across the board, the HDR palette controls are built to span as much as 16 stops of exposure. For context, the bulk of today's digital cinema cameras claim a capture range somewhere in the 13-19 stops of dynamic range bracket, whereas an ASC white paper puts modern film negatives at 14 stops of dynamic range. In contrast to the Lift/Gamma/Gain or Log master level controls, each zone's Exposure adjustment begins at a fixed boundary of image tonality and extends fully out through the highlights or shadows, reaching the highest or lowest signal level permitted. Because Shadow and Light are the pair of zones anchored on the image's midtones, they are the clearest zones for watching how all this behaves. For that same reason, they are likely the first two you will reach for when making more pointed exposure tweaks. With the default preset, Shadow exposure changes act on everything in the image from stop 1 on down to absolute black.

(Left) The starting image, (Right) Pulling every shadow darker by dialing down the Shadow exposure adjustment

Light exposure changes, on the other hand, act on everything in the image from -1 stops on up to maximum white.

(Left) The starting image, (Right) Brightening every highlight by raising the Light exposure adjustment Being able to make open-ended contrast moves across these different overlapping bands of shadow and highlight tonality is exactly what makes these controls so well-matched to HDR grading, and they remain perfectly at home grading at SDR levels too. Note as well that every contrast move in the HDR palette holds saturation steady whether contrast goes up or down. That really pays off on big contrast moves to HDR images, where a 300 nit stretch of highlight contrast done with the Lift/Gamma/Gain or Log controls would send saturation soaring. Expanding highlight contrast through the HDR palette instead keeps the image's saturation looking the same to the eye, while still handing you zone-specific saturation controls to decide whether to raise or drop the saturation inside that zone. When a zone overlaps others, its Exposure changes merge together smoothly to enable targeted contrast work, and they make it fairly easy to dodge unwanted artifacts such as contouring or solarizing that overzealous curve inversion in these operations can introduce.

### An Example of Zone-Based Exposure Adjustment

To watch this play out, let's observe what occurs as we layer some overlapping changes onto the Light, Highlight, and Specular zones to grade a few HDR highlights, keeping our eyes on the Waveform scope since HDR grades are hard to read in print. Remember that you rarely make Zone-based Exposure changes in isolation. The example image here got a Contrast/Pivot move that pressed the midtones and shadows downward to lend the shadows more definition. After that, Black Offset is nudged up to raise the darkest shadows ever so slightly so they have room to breathe. The result is an image that mostly sits below 200 nits at the outset — an ideal launch point for sculpting those highlights.

(Left) The starting image; (Right) Once Contrast/Pivot has been changed and Black Offset raised With the default preset, applying an exposure change to the Light zone gently lifts everything in the source image that sits above -1 stops on the Zone graph. In practical terms it is pulling up every level above 10 nits on the HDR scope. The brighter portion of the image rises smoothly while the shadows stay parked where we left them.

(Left) The previous adjustment; (Right) After raising Light Exposure Now an exposure change to the Highlight zone lifts every level above 1.5 stops on the Zone graph. Once more in practical terms, every level above 100 nits gets boosted, brightening the topmost highlights. Looking at the image, you can see we are widening the gap between dimmer and brighter highlights, building highlight contrast with more detail where before there were only flat pools of light.

(Left) The previous adjustment; (Right) After raising Highlight Exposure This could be a perfectly good stopping point, but because we want to crank this image's HDR up to 11, we can take the highlights over the edge with one further Exposure change, this time on the Specular zone. The Specular zone kicks in at 4 stops and exists to let you raise or lower only the very brightest, hardest highlights — the sort tied to specular details like chrome reflections, eye glints, and light sources shot head-on. It is not a control you will always need, but it is worth knowing. Here, the default Specular Zone Min Range control falls beyond the image's available data (visible as the histogram's right edge in the Zone graph), so adjusting it accomplishes nothing. Drag the Min Range control over so it crosses the histogram's end, though, and these controls gain a grip on the image's very brightest pixels.

(Left) How the zones are spread out to begin with in the Zone Graph; (Right) Pulling the Specular Min Range handle across so it meets the image histogram's brightest highlights, opening up that part of the image to the Specular controls

At this point the Specular Exposure control lets us drive our image's very brightest pixels upward, setting them further apart from the rest of the highlights and broadening how strongly the audience feels the highlight contrast. (Left) The prior step; (Right) Once Specular Exposure has been raised so the very brightest highlights reach 1000 nits Having now selectively lifted the Highlight and Specular zones, you may find you like the separation achieved among the various highlight brightnesses yet feel the highlights overall are simply too bright. The fix is easy: dial back the Light zone’s Exposure adjustment. That single move scales every highlight down, while the work you put into the Highlight and Specular zones keeps its proportional grip on the regions it is brightening. The Shadow, Dark, and Black controls behave the same way, only for the shadows. (Left) The prior step; (Right) Once Light Exposure is lowered, every level eases downward together to dim the highlights while holding onto the separation you built with the Highlight and Specular controls. Having now seen how all the overlapping Zone changes cooperate to form one seamless adjustment, it is time to examine the Zone controls more closely.

### Zone Controls

Every single zone additionally carries Color Balance and Saturation controls, letting you make pinpoint changes confined to particular bands of image tonality with no qualifier needed. Working all these zones in concert, you can apply quick, precise, smooth changes to the image that come across as remarkably natural. The palette's name notwithstanding, this supports careful work on SDR images as readily as creative shaping of the dramatic highlight range that HDR opens up. Flanking each control cluster on the left and right are Range and Falloff controls that let you redraw each zone's area of influence even while the Zone graph stays hidden.

The Shadow and Light zone controls sitting side by side; the Min and Max indicators are visible, as is the Range value (in stops) up at the top left of each control group.

- Range indicator: Up in the top-right corner of each zone control cluster, an icon and a value report that zone's range. The numeric value is the range value — the Luminance level of image tonality where that zone's adjustment kicks in. It is given in stops, and the icon tells you whether this is a maximum range (working the shadows) or a minimum range (working the highlights).

Click the icon to pop a brief preview into the Viewer of which image areas that zone's controls will touch. The affected areas show up in full color while everything else turns black.

- Zone-specific Color Balance: A color balance control lets you rebalance the comparative strength of the red, green, and blue channels inside the current band of image tonality.
- Zone-specific Exposure: These controls operate alongside a movable pivot that fixes the Luminance level from which each exposure change departs. So both shadow and highlight work are covered, there are two pivot varieties, labeled Maximum and Minimum range and flagged by an icon. Max Range controls — the Shadow control among them — begin at a maximum value, their exposure changes pulling image contrast downward toward the shadows. Min Range controls, Light being one, begin at a minimum value, their exposure changes pulling contrast upward toward the highlights. Every zone additionally has a falloff dictating how far that zone laps over its neighbors (measured from the pivot level) so overlapping changes blend gently enough to keep contouring at bay.
- Zone-specific Saturation: Tunes how intense the color is within the current band of image tonality.
- Min/Max Range: Sets the level of image tonality where that zone's adjustment begins. It is given in stops. The same as the Min or Max Range slider over in the Zone panel. Handy for nudging Range while the Zones graph is out of view.
- Zone Falloff: Sets how gently this zone melts into every overlapping zone. The same as the Falloff slider over in the Zone panel, with its value shown in the virtual slider beneath. Handy for nudging Falloff while the Zones graph is out of view.
- Zone-specific Color Balance Values: A pair of values puts the current color balance operation into numbers. Via the option menu you can have these shown either as X and Y or as Angle and Strength.

### Customizing Zones Using the Zone Panel

Much as with the Log palette's controls, the way these zones overlap is adjustable, letting you tune each zone's controls to suit the tonal spread of whatever scene you are on. That overlap is steered by separate Range and Falloff control pairs, so precise adjustment is possible regardless of how tonality is distributed in the image you are grading. You organize and customize all the zones through the Zone panel, which splits into the Zones sidebar on the left and the Zone graph on the right.

### The Zone panel of the HDR palette

### The Zone Sidebar

The Zone sidebar presents a list of every zone in the current preset. The list is ordered by range value, putting minimum range zones (working the shadows) up top and maximum range zones (working the highlights) further down. Clicking any entry in the list selects that zone and at the same time picks out its boundary handle over in the Zone graph on the right. The Zone sidebar offers these controls:

- Enable Zone toggle: These toggles flip each zone on or off. A disabled zone is left out of the render.
- Max/Min button: Decides whether a given zone's adjustment works the image from its current range value on down (Max) or from its current range value on up (Min). You normally set this while building a custom preset, to declare which zones reach down toward the shadows and which reach up toward the highlights.
- Show/Hide Zone button: This button tucks away sets of zone controls you have no further interest in adjusting, which frees room within the UI, and on your control surface, for whichever zones still matter to you. Say you decide the default Black and Specular zones are unnecessary; hide them and only the Dark, Shadow, Light, and Highlight zones remain to switch between. Any zone controls that already carry adjustments keep affecting the image even once hidden.
- Delete Zone button: Removes that zone. This mostly comes up while you are crafting your own zone preset. As of this writing, none of the default zones in the default Zone preset can be deleted. On top of that, you can add zones and save zone presets to invent your own custom approaches to adjusting the image.

To create a new zone: 1 Open the Zones panel. 2 Hit Create Zone at the foot of the Zones sidebar. 3 Once the Create Zone dialog opens, pick the Zone type you want for it (Dark/Min Zone or Light/Max Zone), type in a Name, and set the Range and Falloff values. Range, Falloff, and Zone type all stay editable afterward, so there is no harm in not nailing them on the first pass. 4 Hit Create. The zone shows up appended to the list, which orders itself by how Range is defined — Dark Zones up top, Light Zones at the bottom.

### The Create Zone dialog

### Zones Graph

The Zone graph is central to how you work the HDR palette. Across the bottom runs a stops scale marking the range the HDR palette covers. Up top sit handles for adjusting the editable range boundaries that delimit each zone's tonal range, all laid over a histogram of the current image as it feeds into the current node. Down the middle of the Zone graph runs a curve depicting every Global and Tonal color and contrast change the HDR palette is applying in the current grade. How those range boundaries line up against the source image histogram in this graph matters enormously. A given zone's range boundary has to cross the slice of the source histogram you mean to adjust before that zone's controls do anything at all. Should any zone boundary sit beyond the histogram, that zone's controls accomplish nothing. In the screenshot above, every one of the zone's range boundaries falls inside the visible histogram, so each zone's controls deliver a predictable adjustment to the image data in that stretch of the histogram.

### The Zone graph

In the screenshot below, the Zone graph reveals that the Specular zone boundary sits beyond the image's source histogram, so anything you do with the Specular controls produces no effect. That is why it pays to confirm the zone boundaries cross the image areas you intend to adjust before you start moving controls; and if you spot a particular zone's controls doing less to the image than you would like, you can always shift the zone boundary afterward to widen the image range that zone reaches.

. With the Specular zone boundary sitting beyond the source histogram, the Specular controls are shut out from touching the image. Tailoring zone boundaries like this ranks among the HDR palette's most potent capabilities, yet do not fear you will be forever dragging boundaries to and fro on every shot. As a rule, most well-shot scenes carry comparable tonal ranges from shot to shot, so boundaries you have customized for one shot in a scene will probably serve most of that scene's clips well. Even so, reworking zone boundaries is yet another strong way to tune a grade specifically for a clip whose contrast range is unusual.

### Zone Controls

- (Min/Max) Range: Sets the level of image tonality where that zone's adjustment begins. The value is given in stops.
- Falloff: Governs how gently that zone's adjustment merges into the image. At a value of 0 the change in the current zone arrives instantly, making the color adjustment a sharper effect. Larger values ease the current zone's adjustment into the image more softly, for a gentler, more seamless transition into the effect.
- Customizing and Saving Presets

When you have shaped the Zone graph in a way that might serve other grading situations too, you can store the Zone settings as a preset to reuse later. Saving, recalling, and managing those presets is straightforward. Ways to manage presets:

- To save a preset: Shape the Zone graph however you need, then pick Save As New Preset from the HDR palette Option menu.
- To load a preset: From the HDR palette Option menu, follow Presets > Name of Preset > Load Preset. Doing so saves a fresh preset.
- To update a preset: Load a preset, apply whatever Zone graph changes you need, then pick Presets > Name of Preset > Update Preset from the HDR palette Option menu.
- To delete a preset: Pick Presets > Name of Preset > Delete Preset from the HDR palette Option menu.
- To select the default preset: Pick Default Preset > Name of Preset from the HDR palette Option menu. That preset becomes the one the HDR palette loads at startup from then on.

### Resetting Color and Zone Adjustments
