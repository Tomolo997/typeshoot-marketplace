---
name: typeshoot-edit
description: "Edit video with Typeshoot without regenerating it: trim, reframe to 9:16/1:1/4:5/16:9, join clips, lay music or a voiceover under them, and burn word-by-word captions. Use to finish a short or fix an existing clip."
---

# Editing with Typeshoot

Inputs can be a `media_id` (import/upload), a library asset id or url, or a public video link. Each edit saves a new file to the library; nothing is overwritten.

| Step | Tool | Credits |
|---|---|---|
| Cut to a part | `trim_video` (`start`, `end` in seconds) | 2 |
| Change shape | `reframe_video` (`aspect_ratio`; `fit: crop` with `focus` 0-1, or `fit: blur`) | 2 |
| Join clips, add music/voiceover | `merge_media` (`clips`, `audio`, `audio_mode: mix|replace`, `audio_volume`) | 2 |
| Captions | `add_captions` (`words` from `generate_speech`, or let Typeshoot transcribe; `style: bold|clean`) | 6/min, min 2 |

**A short, in order:** clips → `merge_media` (with music at ~0.25 under speech, or `replace` with a voiceover) → `reframe_video` to 9:16 if needed → `add_captions` last, so captions sit on the final framing.

When you made the voiceover with `generate_speech`, pass its `words` to `add_captions`: exact timing, no transcript cost.
