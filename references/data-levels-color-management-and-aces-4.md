# Data Levels Color Management And Aces (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

DCDM (P3D60 Limited): Emits a P3 hard-limited signal carrying a D60 white point. DCDM (P3D65 Limited): Emits a P3 hard-limited signal carrying a D65 white point. P3 D60: Emits RGB-encoded image data tied to a D60 white point, meant for viewing on a P3-compatible display set to a D60 white point. P3 D65: Emits RGB-encoded image data tied to a D66 white point, meant for viewing on a P3-compatible display set to a D66 white point. P3 D65 (D60 sim.): Emits RGB-encoded image data that mimics how a P3‑compatible display set to a D60 white point would look when shown on a display whose white point is D65. P3 D65 (Rec.709 Limited): Emits RGB-encoded image data anchored to a D65 white point inside a P3 gamut that has been hard-limited down to the color range of Rec. 709. P3 D65 ST2084 (108/1000/2000/4000 nits): Emits an image suited to the P3 color gamut, applying the SMPTE standard PQ tone curve meant for High Dynamic Range (HDR) post‑production. You get three settings covering three separate peak luminance ranges; the right one to pick hinges on how bright your display's maximum white level goes. Early-stage standards cover HDR displays whose peak luminance reaches 1000 nits, 2000 nits, and 4000 nits. The 108 nits setting exists to mimic an HDR signal clamped down into an SDR range. P3 DCI (D60 sim.): Emits RGB-encoded P3 image data that looks as though it carries a D60 white point when shown on a DCI projector running a DCI white point. P3 DCI (D65 sim.): Converts RGB-encoded image data on a D61 white point (the DCI mastering standard) so it looks as though it carries a D65 white point. P3-D65 ST2084 (1000/2000/4000 nits): Converts an image suited to the P3 color gamut, applying the SMPTE standard PQ (ST.2084) tone curve meant for High Dynamic Range (HDR) post-production. You get three settings covering three separate peak luminance ranges; the right one to pick hinges on how bright the maximum white level is on the display used to author the media. Early-stage standards cover HDR displays whose peak luminance reaches 1000 nits, 2000 nits, and 4000 nits. Rec.2020: This ODT exists for compatibility with the entire span of this wide-gamut standard built for consumer and broadcast television. Rec.2020 (P3D65 Limited): Emits a P3D65 hard-limited signal inside this wide-gamut standard built for consumer and broadcast television. Rec.2020 (Rec.709 Limited): Emits a Rec. 709 hard-limited signal inside this wide-gamut standard built for consumer and broadcast television. Rec.2020 HLG: Emits the complete Rec. 2020 gamut conformed to the HDR Hybrid Log-Gamma standard. Rec.2020 HLG (1000 nits, P3D65 Limited): Emits a 1000 nit, P3D65 hard-limited signal inside the Rec. 2020 gamut, conformed to the HDR Hybrid Log-Gamma standard. Rec.2020 ST2084 (1000/2000/4000 nits): This ODT converts media authored inside the widegamut standard built for consumer and broadcast television, applying the SMPTE standard PQ (ST.2084) tone curve meant for High Dynamic Range (HDR) postproduction. You get three settings for HDR televisions of varying peak luminance capability. Rec.2020 ST2084 (1000/2000/4000 nits, P3D65 Limited): This ODT converts media inside the wide-gamut standard built for consumer and broadcast television, yet it clips hard at the edge of the P3 gamut for televisions confined to the narrower P3 gamut of digital cinema; it likewise applies the SMPTE standard PQ (ST.2084) tone curve meant for High Dynamic Range (HDR) post-production. You get three settings for HDR televisions of varying peak luminance capability. Rec.709: This ODT serves standard monitoring along with deliverables bound for TV.

Rec.709 (D60 Sim): A standard transform built to carry media sitting in the Rec. 709 color space on a D60 white point over into the ACES color space. sRGB: A standardized transform built for media produced for computer viewing in a consumer setting. sRGB (D60 Sim): A standardized ODT built for media headed to computer viewing in a consumer setting. A good fit for monitoring while grading material aimed at the web. ACEScc/ACEScct/ACEScg: Standardized transforms covering each of these ACES standards. While you operate in ACES, you have to hand-pick an ODT that lines up with your workflow and the layout of your room.

- Process Node LUTs in: Through this drop-down menu you decide how CLF LUTs attached to nodes in your grades get processed while you work in ACES — for example Look LUTs used in on-set or VFX workflows. Two options are offered: ACEScc AP1 Timeline Space (which is the default), and ACES AP0 Linear. ACEScc AP1: Suits LUTs built to accept the particular range of ACEScc data expressed in the AP1 primary coordinates. ACES AP0: Suits LUTs built for ordinary ACES data spanning floating point values from 65504 to -65504.

NOTE: Grades done in ACES call for CLF LUTs that were authored expressly for ACES workflows. To bring an ordinary LUT into a grade, you first run a color space transform that takes the image out of ACES and into whatever space that LUT was meant to operate in, then a second color space transform that brings the image back to ACES; this approach, though, doesn't always yield the best outcome. The Initial State of Clips When Working in ACES There's no cause for concern if each image file's starting appearance differs from what you originally watched on set. The key point is that as long as the camera original media was exposed properly, the IDT applied in ACES mode holds on to as much image data as possible and hands you the widest grading latitude available, no matter how the picture first looks on the Timeline.

### ACES AMF 2.0

DaVinci Resolve can import and export ACES AMF 2.0 files. An ACES AMF is a sidecar file authored in XML that spells out the clip's input and output transforms. It guarantees that the right input and output transforms get applied all the way through the post production pipeline. You can load these files either at the project level or the clip level. A clip whose “applied” attribute reads true is flagged accordingly and carries no transforms applied. When that attribute reads false instead, DaVinci Resolve applies the transform itself. NOTE: AMF files call for version 1.3 or higher of the ACEScc or ACEScct Color Science.

### Working with AMF Files

Project level AMF: Here every transform ends up applied. (That is, whatever input, look, or output transforms are defined with their “applied” attribute reading false get applied.) Those input and output transforms come in through the project settings “ACES Input Transform” and “ACES Output Transform” menus, and either menu reads “From AMF” whenever it's pulling a transform out of the loaded AMF file. Clip level AMF: You load an AMF from the Color page clip thumbnail context menu, by way of the Clip AMF menu. That same list draws from the ACES Transforms AMF subfolder too. An AMF at the clip level skips the output transform, which is something only project settings can apply. Whatever input or look transforms it holds carry their “applied” attribute reading false. Those look transforms get applied inside a compound node called AMF LMTs. ACES Gamut Compression: Should the AMF name the ACES reference gamut compress algorithm within a look transform, it ticks the “Apply ACES reference gamut compress” checkbox on. You can review which input, gamut compress, look, and output transforms are in effect by clicking the “View Transforms” button down at the foot of the “Color Space & Transforms” area under the Settings > Color Management section. To Import an AMF 1 Drop your AMF files into the ACES Transforms/AMF directory on your machine. You'll locate that folder at: MacOS: the user's `Library/Application Support/Blackmagic Design/DaVinci Resolve/Aces Transforms/AMF` Windows: the user's `AppData\Roaming\Blackmagic Design\DaVinci Resolve\Support\ACES Transforms\AMF` Linux: `opt/resolve/Developer/DaVinciCTL/AcesTransforms/AMF` 2 Within the Project Settings, switch the Color Management > Color Science setting over to ACEScc or ACEScct. 3 Pick an ACES version of 1.3 or higher. 4 Click the ACES AMF drop-down menu and choose the AMF off the list.

### Exporting AMF Files

When exporting an AMF file, you pick from one of three options. Source Master mode:

- Every applied attribute gets switched to false.
- A source master ties to no clips or images at all. Dailies Request mode:
- You get to pick which folder holds the exported AMFs.
- One dailies AMF is generated for each clip and bound to it, and its applied attribute is

set to false. VFX Request mode:

- A VFX AMF holds only the input transform, whose applied attribute is set to false.

### AMF Delivery Behaviors

- To deliver an AMF, tick the export AMF option found in the Deliver page render settings.
- Under Source Master, the images render to ACES AP0 or Linear masters carrying only their

input transforms applied, while every other transform is marked applied false.

- The AMF this produces stays unbound to any clips or images, its purpose being to spell out and pass along a

color pipeline together with its post production look beside ACES AP0 or Linear data.

- Under Dailies Request, the rendered images have all transforms applied, and every transform is

marked applied true.

- The AMF this produces is bound to each clip across the project.
- Under VFX Request, the clips render to ACES AP0 or Linear bearing only the input transform

applied, while all the rest are set to false. To Export an AMF 1 Right-click your timeline within the Media Pool. 2 Pick Timelines > Export > AMF from the contextual menu. 3 Settle on the export type for your AMF — Source Master, Dailies Request, or VFX Request. 4 Type the AMF file's name and where to save it in the file browser. 5 Click the Save button.

### The Timeline Color Space in ACES Workflows is Fixed

While you operate in ACES, changing the Timeline Color Space isn't an option the way it is under Resolve Color Management. The ACES working color space happens to be a log-encoded color space, which nudges you toward a more classic, film-style way of grading.

### Tips for Rendering Out of an ACES Project

As you settle on an output format over in the Deliver page, bear these points in mind:

- For graded media headed to broadcast, set the ACES Output Device Transform to Rec. 709, after which you're free to output to whatever media format suits your workflow.
- For graded media files going to a different ACES-capable facility through the DCDM or ADX ODCs, choose, within the Render Settings, the OpenEXR RGB Half (uncompressed) format, then switch the ACES Output Device Transform over to “No Output Device Transform.”
- For media you're rendering toward long-term archival, choose, within the Render Settings, the OpenEXR RGB Half (uncompressed) format, then switch the ACES Output Device Transform over to “No Output Device Transform.”
