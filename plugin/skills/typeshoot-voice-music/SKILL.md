---
name: typeshoot-voice-music
description: "Make voiceovers, narration, dialogue, background music, jingles, songs and sound effects with Typeshoot. Use for any spoken or musical audio, or Foley and ambience."
---

# Voice, music and sound with Typeshoot

**Voiceover** (`generate_speech`): default ElevenLabs v4, voice Brian (deep, calm narrator). `get_model_params` with `model: elevenlabs-v4` lists voices with a short description each (Daniel: British newsreader; Rachel: calm female narrator; Roger: confident, casual...). Write exactly what to say; tags like `[calm]`, `[excited]`, `[laughs]` steer delivery. It returns `words` with timings: keep them for captions. About 20 credits per 1,000 characters.

**Music** (`generate_music`):
- Background bed, any mood: Lyria 3.5 (default, flat price per track, ~30 s).
- Exact length (to fit a video): `elevenlabs-music-v2.5` with `duration`, `instrumental: true` under speech.
- Sung lyrics: `minimax-music-3` (needs `lyrics`) or `mureka-v9.5`.
Describe genre, mood, tempo, instruments and what it's for.

**Sound effects** (`generate_sound_effect`): one sound per call, 0.5-30 s, `loop: true` for ambience. Be concrete: "heavy steel door slams in a concrete bunker, short echo".

Mix them onto video with `merge_media` (see `typeshoot-edit`).
