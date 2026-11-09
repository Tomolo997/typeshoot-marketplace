---
name: typeshoot-swap
description: "Put the user into an existing video (the TikTok/Reels trend where the person is replaced and the clip plays back the same) or have them perform a clip's dance. Use when the user shares a TikTok, Instagram, YouTube or X link and wants to be in it, or asks what's in a video."
---

# Face swaps with Typeshoot

1. **Consent first.** Ask the user to confirm the face photos are of them, or of people who agreed, and that no one is a minor or a public figure. Without a clear yes, stop. Pass `faces_consent: true` only after it.
2. **Get the face**: an attached selfie → `get_upload_url` → PUT → `confirm_upload`. Front-facing, good light, one photo per person.
3. **Import** the link with `import_media` (free). Optionally `analyze_video` to see shots and words (a couple of credits).
4. **Limits** (mode `recast`, the default, keeps the scene and sound): 5-30 s, no single shot over 15 s. Use `start`/`end` to pick a part. For a single dancer, mode `motion` follows the movement instead.
5. **Price**: call `swap_video_characters` with `estimate_only: true`, tell the user the credits (60/s at 768p, 90/s at 1080p for recast; 34/s for motion), and wait for a yes. Suggest 768p and 5-8 s for a first try.
6. **Run** with the same arguments plus `faces_consent: true`. It returns a job id at once; swaps take a few minutes, so poll `check_job` every 20-30 s. If the id is lost, `check_job` without an id lists recent jobs.
7. Results carry an "AI-generated" label. Offer captions or reframing (`typeshoot-edit`) next.
