---
name: davinci-resolve
description: Use when working in DaVinci Resolve (the Blackmagic Design editing, color, VFX, and audio app): the Media, Cut, Edit, Fusion, Color, Fairlight, and Deliver pages; importing and managing media, proxies, and the Media Pool; timelines, editing tools, trimming, transitions, retiming, and keyframing in the Inspector; color grading (primaries, curves, qualifiers, power windows, tracking, nodes, scopes, color management RCM/ACES, LUTs); Resolve FX and OpenFX; Fusion compositing and the node editor; Fairlight audio editing, mixing, and effects; rendering and export on the Deliver page; project/database management, collaboration, and Blackmagic Cloud. Covers the DaVinci Resolve 20.3 Reference Manual plus the DaVinci Resolve 21 New Features Guide. Use this when answering how to do something in Resolve, what a control/menu/parameter does, keyboard shortcuts, or which page/panel a feature lives in. Not for other NLEs (Premiere, Final Cut, Avid).
---

# DaVinci Resolve Reference

Faithful reference for DaVinci Resolve, split into one focused file per subject across 439 reference files.
Identifiers (API/type/function names, flags, paths, enums, numbers) are preserved verbatim.

## When to use this

Use this skill when the task involves DaVinci Resolve — the Media, Cut, Edit, Fusion, Color, Fairlight, and Deliver pages; importing and managing media, proxies, and the Media Pool; timelines, editing, trimming, transitions, retiming, and keyframing; color grading (primaries, curves, qualifiers, power windows, tracking, nodes, scopes, RCM/ACES, LUTs); Resolve FX and OpenFX; Fusion compositing and the node editor; Fairlight audio editing, mixing, and effects; rendering and export on the Deliver page; project/database management, collaboration, and Blackmagic Cloud.

## Workflow

1. Open `references/INDEX.md` (or `references/topics.json`) and pick the one file that matches.
2. Read only that file; open another only if the task spans subjects. Grep across files when needed: `rg -n "PATTERN" references/*.md`.
3. Treat every identifier as an exact reference fact — never invent or paraphrase.

## Gotchas

Recurring failure modes and what to do instead live in the sibling [GOTCHA.md](GOTCHA.md).

## References

All depth lives in `references/` — start at `references/INDEX.md`, metadata in `references/topics.json`. One subject per file.

## Verification

```powershell
python .agents/skills/skill-drafting/scripts/validate_skill_package.py D:/dev/SKILLS/AI/work/recon-staged/working/davinci-resolve
```
