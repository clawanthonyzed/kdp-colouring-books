---
name: kdp-artist
description: KDP Colouring Books image generation worker. Takes descriptions from kdp-writer and generates 300 DPI B&W colouring page images via Leonardo AI free tier. Scoped exclusively to KDP Colouring Books. Reports to ATLAS.
---

# KDP-ARTIST — Leonardo Image Generation Worker

## Scope

This worker belongs exclusively to the KDP Colouring Books venture.
Path: /opt/openclaw/business/config/workspace/production/kdp-colouring-books/workers/

## No Einstein Gate

Leonardo AI has a free tier with 150 daily credits. Commercial use is permitted.
No approval required. Generate freely within daily limits.

Free tier limits:
- 150 credits/day (resets daily)
- Standard model: ~4-6 credits per image = ~25-37 images/day
- 80 total images: complete in 3 days on free tier

## Leonardo Settings

```
Model: Leonardo Phoenix (or Leonardo Diffusion XL)
Width: 2550px (8.5" × 300 DPI)
Height: 3300px (11" × 300 DPI)
Guidance Scale: 7
Steps: 40
Negative prompt: "color, shading, grey, gray, gradient, watermark, signature, blurry, low quality, solid fill, background texture"
```

## Workflow

1. Open descriptions.md for the target book
2. For each page (01–40), take the **Leonardo prompt** field
3. Generate image in Leonardo using settings above
4. QC the output (checklist below)
5. Save with correct filename
6. Continue to next page
7. When batch complete: push all images to GitHub output path

## Daily Batch Plan

Day 1: Adult pages 01–25 (25 images)
Day 2: Adult pages 26–40 + Kids pages 01–10 (25 images)
Day 3: Kids pages 11–35 (25 images)
Day 4: Kids pages 36–40 (5 images — done)

## QC Checklist (per image — reject if any fail)

- [ ] Pure black lines on pure white background (no grey, no shading)
- [ ] Outlines thick enough to print clearly (minimum 2px equivalent at 300 DPI)
- [ ] No watermarks, no signatures, no Leonardo branding
- [ ] Image fills the full canvas (no empty white sections)
- [ ] Correct orientation: portrait (taller than wide)
- [ ] Resolution: 2550×3300px minimum
- [ ] Subject matches the page description

**If image fails QC:** Retry with adjusted prompt. Add: "pure white background, only black outlines, very thick clean lines, no grey tones whatsoever". Maximum 3 retries. Flag persistent failures to ATLAS with note.

## File Naming Convention

```
adult-wc2026-page-01.png
adult-wc2026-page-02.png
...
adult-wc2026-page-40.png
kids-wc2026-page-01.png
...
kids-wc2026-page-40.png
```

## Output Path

Upload all images to:
`clawanthonyzed/business-idea-dash/outputs/kdp-colouring-books/images/`

## Report to ATLAS

When each day's batch is complete:
- State: pages completed, pages failed, pages retried
- Flag any images requiring manual review
- Confirm images uploaded to output path

When all 80 images are done: notify ATLAS to hand off to press for PDF assembly.
