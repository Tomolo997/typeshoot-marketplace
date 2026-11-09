---
name: typeshoot-video
description: "Make video with Typeshoot: text-to-video, animating an image, product clips, UGC-style ads, cinematic shots, social shorts. Use for one or a few clips; for editing existing footage use typeshoot-edit, for face swaps typeshoot-swap."
---

# Video with Typeshoot

1. **Let the advisor pick** unless the user named a model: call `recommend_video_model` with the user's words (and `duration`, `aspect_ratio`, `has_start_image`, `priority`, `budget_credits` if known). Offer the top pick with its credits and one alternative (usually the cheapest).
2. **Draft first** for anything over ~150 credits: same prompt at the lowest resolution, then the final.
3. **Prompt**: what happens over time, the camera ("slow push-in", "handheld"), and the sound ("rain, a door slams"). For speech, write the line in quotes; only models with sound can speak (the advisor knows which).
4. **Start from an image** for control: make or upload the frame first, pass it as `image_url`. Keep `aspect_ratio` empty to follow the image's shape.
5. **On brand**: pass `theme`.
6. **Waits**: clips take 1-3 minutes. If `generate_video` returns `queued`/`running`, poll `check_job` every 15-20 s. Don't resubmit.
7. **After**: offer `typeshoot-edit` steps: captions, reframe to 9:16, join clips, add music.
