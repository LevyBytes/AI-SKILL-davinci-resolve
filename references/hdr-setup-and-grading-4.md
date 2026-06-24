# Hdr Setup And Grading (part 4)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

A second approach to encoding HDR video came out of a collaboration between the BBC and NHK, and it carries the name Hybrid Log-Gamma (HLG). Its designers set out to master HDR footage so that screens with widely varying peak luminance could all show it without carrying any extra metadata, so that a single data stream could be broadcast, so that everything stayed within a 10-bit signal, and — as the ITU-R Draft Recommendation BT.HDR puts it — so that the format stays somewhat workable on older legacy screens by hewing more closely to the television transfer curves that came before. In essence, across roughly the lower 0 to 0.6 portion of the signal (assuming a normal 0–1 range) the HLG EOTF behaves almost the same as BT.1886, and then from 0.6 up to 1.0 it gradually transitions into a logarithmic curve to handle the brightest tones. Practically speaking, feeding an HDR Hybrid Log-Gamma signal straight to an SDR display still lets you view a large part of the picture just as an HDR screen would render it, with the brightest areas squeezed down so that a reasonable amount of detail survives for SDR broadcast.

Setup and Workflows | HDR Viewers HDR Setup and Grading

When that same signal reaches an HDR display that supports Hybrid Log-Gamma, by contrast, only the log-shaped highlights — not the BT.1886-like lower span of the signal, just the bright end — get expanded again, scaled to whatever peak luminance the particular HDR television can produce, so the picture is restored to its full HDR splendor. That behavior contrasts with the HDR10 distribution approach covered earlier, where the graded signal is tied to the absolute luminance values defined by ST.2084, so any level the display cannot reproduce simply gets clipped. This ability to serve many HDR screens of differing peak luminance does loosely resemble how Dolby Vision adapts its HDR output to each individual Dolby Vision-compatible television’s peak luminance, but HLG carries no extra metadata directing how the bright tones get scaled — which, depending on your perspective, is either an advantage (less effort) or a drawback (no creative direction ensuring the highlights scale as well as they could). As with almost everything, there is no free lunch here. BBC White Paper WHP 309 reports that a 2000 cd/m2 HDR display whose black level sits at 0.01 cd/m2 can reach as much as 17.6 stops of dynamic range before visible quantization artifacts (“banding”) appear. BBC White Paper WHP 286 reports that the proposed HLG EOTF ought to accommodate screens up to roughly 5000 nits. In part, then, the backward compatibility HLG offers comes at the cost of abandoning long-term support for 10,000 nit displays. Whether anything beyond 5000 nits even matters for the average viewer, though, remains debatable. Sony, LG, Panasonic, JVC, Phillips, Hisense, Hitachi, and Toshiba have each either announced or begun shipping consumer HDR televisions able to play HLG encoded footage, and DaVinci Resolve naturally supports the format by way of Resolve Color Management.

### Grading Hybrid Log­‑Gamma in DaVinci Resolve

To monitor an ST.2084 image, you need only obtain a Hybrid Log-Gamma-compatible HDR display and route the output of your video interface into that display’s input. Configuring Resolve Color Management for an HLG grade works exactly the same way as configuring it for a Dolby Vision grade, the one difference being that the Output Color Space offers four HLG options to pick from:

- Rec.709 HLG ARIB STD-B67
- Rec.2020 HLG ARIB STD-B67
- Rec.2100 HLG
- Rec.2100 HLG (Scene)

As an alternative, turning on “Use Separate Color Space and Gamma” lets you set your gamut to either Rec. 2020 or Rec. 709 while assigning Rec. 2100 HLG as the EOTF. In that case the values shown on your scopes won’t match the data-to-nit table given earlier for grading against the PQ EOTF.

### Ouputting Hybrid Log-Gamma

After you finish building an HLG grade for your program, that grade can be rendered out to any high-quality media format that handles 10-bit.

Setup and Workflows | HDR Viewers HDR Setup and Grading

### Generate HDR Light Level Report (Studio Version Only)

It is now possible to produce HDR Light Level reports straight from the Media Pool. Begin by selecting a clip in the Media Pool, then right-click and pick Generate HDR Report from the context menu. You’ll then be asked where to store the resulting HDR Light Level report, which is written as a .pdf file. Behind the scenes the tool examines every frame of rendered HDR clips and reports light level figures such as MaxCLL and MaxFALL. The report also embeds a still of the frame holding the brightest luminance, marked with a box around the spot where those peak values occurred.

An HDR Light Level report exported from DaVinci Resolve

Setup and Workflows | HDR Viewers HDR Setup and Grading
