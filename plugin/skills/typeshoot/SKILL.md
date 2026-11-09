---
name: typeshoot
description: "Route any creative request through Typeshoot (images, video, voiceover, music, sound effects, face swaps, video editing, brand kits, credits). Use when the user mentions Typeshoot, wants several kinds of media, asks about credits or their library, or the right Typeshoot skill isn't obvious. Prefer a focused typeshoot-* skill for one clear outcome."
---

# Typeshoot

Typeshoot makes and edits media with the best current models and bills in **credits**.

## House rules (always)

- **Quote prices in credits only** ("about 90 credits"). Never convert to dollars. If asked what credits cost in money, call `get_credits_link` and show the packs.
- **Estimate before anything over 100 credits** (`estimate_generation`, `recommend_video_model`, or `swap_video_characters` with `estimate_only`), say the number, and wait for a yes.
- **Draft first** for video: 360p or the advisor's cheapest pick, then the final once the user likes it.
- **Never regenerate without asking.** If a job seems lost, call `check_job` with no job id to list recent jobs; finished work also lands in the library (`search_assets`).
- **Attached files**: upload with `get_upload_url` → PUT the file → `confirm_upload`, then pass the returned url. Never ask the user for a public link first. Uploads are deleted after use; results are kept in the library.
- **On brand**: if the user has brand kits (`list_themes`), pass `theme` to generate tools.

## Which skill

| The user wants | Skill |
|---|---|
| An image, poster, product shot, edit, cut-out or upscale | `typeshoot-image` |
| A video clip, animated image, ad or short | `typeshoot-video` |
| To put themselves into a TikTok / Reel | `typeshoot-swap` |
| To trim, reframe, join, caption or add music to video | `typeshoot-edit` |
| A voiceover, music or sound effects | `typeshoot-voice-music` |
| To save or use their brand | `typeshoot-brand` |

When a result is ready, Typeshoot shows it in a card in the chat; describe it in a line and offer one concrete next step instead of pasting the link.
