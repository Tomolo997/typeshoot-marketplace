---
name: typeshoot-brand
description: "Save a brand once (logo, colours, fonts, tone, do and don't) and keep every Typeshoot image and video on brand. Use when the user says \"my brand\", \"on brand\", shares a logo or brand guide, or wants campaign assets for a business."
---

# Brand kits with Typeshoot

1. **Check what exists**: `list_themes`. Use the default kit unless the user names another.
2. **Save a brand** with `update_theme` (leave `theme` empty to create): `name`, `colors` (hex, main first), `fonts` (`heading`, `body`), `tone` (how it sounds), `notes` (do and don't), `website`, and `logo_url` (upload an attached logo first; a transparent PNG works best). Ask only for what's missing; a name and two colours are enough to start. Saving is free.
3. **Use it**: pass `theme` to `generate_image` / `generate_video`; add `use_logo: true` on images where the logo should appear (packaging, ads, end cards).
4. **Edit later**: `update_theme` with `theme` set to the kit's name; `delete_theme` to remove.

For a campaign, make one hero image first, confirm the look, then the rest with the same `theme` and prompt style.
