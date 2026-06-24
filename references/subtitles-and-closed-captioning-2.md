# Subtitles And Closed Captioning (part 2)

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

After you have built several regions, the subtitle track behaves much like a small standalone timeline stacked four layers deep. Every subtitle region carries an independent Captions list along with its own Style settings — font among them, and, above all, where the text sits on screen. So you might, for instance, reserve the default region for your ordinary subtitle layout, use Region 2 for speakers positioned to the left of the frame, and assign Region 3 to those on the right. Should two or more regions sit on top of one another within the subtitle track, every subtitle occupying that spot stays on screen together. To shift a caption from one region into another, simply drag its subtitle clip upward or downward within the subtitle track. The illustration that follows shows a pair of subtitles riding a single ordinary subtitle track. Yet because both of these lines belong to one two-shot in which the actors partly overlap, presenting the two subtitles together reads more naturally than showing them one after the other. Introduce an extra subtitle region and slide the subtitle clip along the timeline to the precise moment the actress overlaps the actor’s line, and you tie the caption’s timing more closely to what is happening on screen. On top of that, the fresh subtitle region had its text position moved over to the right of the frame, the very side where the actress speaking the line stands. Doing so makes clear which of the pair is speaking at any given moment.

### The initial sequential subtitle track

That identical subtitle track after a new region was inserted, which permits both subtitles to display at once

### Naming Subtitle Tracks

Should you wish, a double-click on any subtitle track’s name lets you retitle it to better describe that track’s contents — perhaps the language it holds, plus whether it carries subtitles or closed captions. Established schemes already exist for labeling languages, depending on your pipeline and the delivery spec you are meeting; among them are ISO-639-1 (which governs 2-letter codes) and ISO-639-2/B (which governs 3-letter codes). The International Organization for Standardization publishes these on its site, at http://www.loc.gov/standards/iso639-2/php/code_list.php. Certain schemes call for a language code together with a country code. Facebook, as one case, expects SubRip (.srt) files carrying the naming format “VideoFilename.[language code]\_[country code].srt” so embedding works properly. Should you wish to apply such codes when identifying and outputting subtitle tracks, what follows is a sample alphabetical roster of standardized language and country codes drawn from across the globe:

### Language Amharic

### Arabic

ISO 639-1 Language Code am ar

ISO 639-2 Language Code amh ara

### ISO 3166-1 Country Code

ET (Ethiopia) EG (Egypt) AE (United Arab Emirates) LB (Lebanon)

### Language Bengali

### Chinese

### Danish Dutch

### English

Finnish French German Greek Modern Hausa Hebrew Hindi Indonesian Italian Japanese Malay Maori Norwegian Polish Portuguese Punjabi Russian Spanish Castilian Swahili

```text
ISO 639-1 Language Code bn zh da nl en fi fr de el ha he hi id it ja ms mi no pl pt pa ru es sw

ISO 639-2 Language Code ben chi (B) zho (T dan dut (B) nld (T) eng fin fre (B) fra (T) ger (B) deu (T) gre (B) ell (T) hau heb hin ind ita jpn may (B) msa (T) mao (B) mri (T) nor pol por pan rus spa swa

ISO 3166-1 Country Code IN (India) CN (China) HK (Hong Kong) TW (Taiwan) DK (Denmark) NL (Netherlands) GB (UK) IN (India) US (US) FI (Finland) CA (Canada) FR (France) DE (Germany) GR (Greece) NG (Nigeria) TD (Chad) IL (Israel) IN (India) ID (Indonesia) IT (Italy) JP (Japan) MY (Malaysia) NZ (New Zealand) NO (Norway) PL (Poland) BR (Brazil) PT (Portugal) IN (India) RU (Russia) CO (Columbia) ES (Spain) MX (Mexico) KE (Kenya)
```

### Language Swedish Tagalog Thai Turkish Urdu Vietnamese

```text
ISO 639-1 Language Code sv tl th tr ur vi

ISO 639-2 Language Code swe tgl tha tur urd vie

ISO 3166-1 Country Code SE (Sweden) PH (Philippines) TH (Thailand) TR (Turkey) PK (Pakistan) VN (Vietnam)
```

### Exporting Subtitles and Closed Captions

After you have built one or more subtitle tracks populated with subtitles or captions, several distinct routes are open to you for exporting them.

### Exporting Subtitles Via the File Menu

Pick File > Export Subtitle, then rely on the export dialog to set both a destination and a file type for the subtitle file you are writing out. The .srt and .vtt formats are both available for export.

### Exporting Subtitles Via the Subtitle Track Header

On the track header belonging to a subtitle track, right-click and pick Export Subtitle out of the contextual menu. From the export dialog, set where the subtitle file goes and which file type it takes. The .srt and .vtt formats are both available for export.

### Exporting, Burning, or Embedding Subtitles During Delivery

Once one or more subtitle tracks exist in a program, a cluster of Subtitle Settings appears low in the Video panel of the Render Settings on the Deliver page, and these govern whether and in what manner subtitles or closed captions ship alongside that timeline.

The choices you have for writing out subtitles sit at the foot of the Video panel within the Render Settings

The controls on this panel are as follows:

- Export Subtitle checkbox: Switches subtitle/closed caption output on or off.
- Format pop-up: Offers four ways to write out subtitles/closed captions.

As a separate file: Writes each subtitle track you pick to its own file, in whatever format the Export As pop-up names. A row of checkboxes lets you pick which subtitle tracks get written. Burn into video: Renders every frame of video with the subtitle track now selected baked permanently into the picture. As embedded captions: Writes the currently selected subtitle track as a metadata layer embedded inside media formats that support it. At present, CEA-608 closed captions are supported inside MXF OP1A and QuickTime files. The Codec pop-up that shows up lets you pick the subtitle format.

- Export As: (shown only while Format reads “As a separate file”) Lets you settle on which subtitle/closed captioning format gets written. The choices are IMSC1, DFXP, SRT, and WebVTT.
- Include the following subtitle tracks in the export: (shown only while Format reads “As a separate file”) A set of checkboxes activates the subtitle tracks you wish to write out.
- Codec: (shown only while Format reads “As embedded captions”) Determines how embedded closed captions are formatted; the choices are Text and CEA-608.

NOTE: At this time, neither analog (Line 21) nor digital (CEA-708) closed caption output is supported over Decklink or UltraStudio.
