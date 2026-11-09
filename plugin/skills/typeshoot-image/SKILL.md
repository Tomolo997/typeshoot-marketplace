---
name: typeshoot-image
description: "Make or edit images with Typeshoot: posters, product shots, social ads, infographics, logos-in-scene, photo edits, background removal and upscaling. Use for any single image or small set of images."
---

# Images with Typeshoot

1. **Pick the model** (default is fine for most):
   - Text in the image (posters, infographics, packaging, UI): **GPT Image 2.6** (`gpt-image-2.6-flare`).
   - Fast, cheap drafts and photo edits: the default model.
   - Unsure: `list_models` with `category: image`; read `cost` and `notes`.
2. **Write the prompt like a brief**: subject, setting, light, camera/style, exact text in quotes, what to avoid. One image per idea; use `count` (max 4) for variations.
3. **Edits and references**: pass the user's images in `image_urls` (upload first if attached). Say what to keep ("same product, same label").
4. **On brand**: `theme` (and `use_logo: true` to place the logo).
5. **After**: offer one next step: a variation, `upscale_image` (fast 4x, 2 credits; best 2x with added detail, 80), `remove_background` (2 credits; `subject: product|portrait|hair`), or animating it (`typeshoot-video`).

Shapes: `aspect_ratio` 1:1 feed, 4:5 Instagram, 9:16 stories/TikTok, 16:9 YouTube/web.
