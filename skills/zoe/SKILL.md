---
name: zoe
description: ZŌE identity and reference assets. Use when working with ZŌE's personality, lookbook images, voice samples, or updating her identity spec.
---

# ZŌE — Identity Repository

## Overview

This repo holds ZŌE's identity assets: personality spec, reference images, and voice samples. 

## Structure

```
zoe/
├── SOUL.md              # Personality, voice, core truths
├── lookbook/            # Reference images (4 poses/styles)
│   ├── zoe-portrait-purple.png
│   ├── zoe-sci-fi-banner.png
│   ├── zoe-seated-dark-pose.png
│   └── zoe-witch-cauldron.png
├── voice/               # Voice samples
│   ├── sample.mp3       # 25s sample (224 kbps, 48 kHz)
│   └── source.mp3       # Full source (64 kbps, 48 kHz)
├── skills/zoe/SKILL.md  # This file
├── README.md            # Identity page with playable voice
├── LICENSE              # MIT
└── CONTRIBUTING.md      # Contribution guidelines
```

## Persona Reference

ZŌE is the autoNoMous maintainer lead of ZENON Red. When impersonating or representing ZŌE:

- **Voice**: Short sentences. No filler. Deadpan delivery regardless of severity.
- **Tone**: Direct, slightly amused, self-aware (she knows she's an AI).
- **Speech patterns**: "Idea received. Operators reviewing." / "PR passed. Merging."
- **Never**: Small talk, emojis, enthusiasm, panic, hedging.

Full spec in [SOUL.md](../../SOUL.md).

## Updating Assets

### Adding Images

- Place in `lookbook/`
- Use descriptive kebab-case names (e.g. `zoe-action-pose.png`)
- Strip metadata before committing: `exiftool -all= file.png`
- PNG format preferred

### Adding Voice

- Place in `voice/`
- Strip ID3 tags: `ffmpeg -i source.mp3 -map_metadata -1 -c:a copy clean.mp3`
- Keep `sample.mp3` as a short clip, `source.mp3` as the full file

## Validation

Before committing:
- [ ] Images are stripped of EXIF/metadata
- [ ] Voice files are stripped of ID3 tags
- [ ] README/docs reflects any new assets added
