# KDP COLOURING BOOKS — MASTER VENTURE DOC

> RULE: Read this before any work. Update after every change. This is the single source of truth.

---

## Venture Identity

| Field | Value |
|-------|-------|
| Venture | KDP Colouring Books |
| Manager | ATLAS |
| Server path | /opt/openclaw/business/config/workspace/production/kdp-colouring-books/ |
| GitHub | clawanthonyzed/kdp-colouring-books |
| Output path | clawanthonyzed/business-idea-dash/outputs/kdp-colouring-books/ |
| Revenue target | $2,000+/month passive |
| Entity | Cudan Studio PTY LTD |
| Platform | Amazon KDP (print-to-order) + Etsy + Gumroad + LemonSqueezy (printable PDF) |

---

## Active Books

| Book | Status | ASIN | Price (print) | Price (PDF) |
|------|--------|------|---------------|-------------|
| World Cup 2026 Adult Colouring Book | IN PRODUCTION | — | $12.99 USD | $6.99 USD |
| World Cup 2026 Kids Colouring Book (Under 12s) | IN PRODUCTION | — | $9.99 USD | $4.99 USD |

---

## Production Pipeline

```
Helium 10 (scout) → Niche + Keywords
        ↓
Quill → 40 page descriptions (per book)
        ↓
[EINSTEIN GATE] Brush → Leonardo AI → colouring page images (300 DPI, B&W line art)
        ↓
Press → PDF assembly (KDP spec: 8.5"x11", 300 DPI, CMYK)
        ↓
Herald → Listing copy (title, subtitle, keywords, description) per platform
        ↓
[MANUAL] Canva → KDP cover (front + spine + back, full bleed)
        ↓
Amazon KDP submit (print-to-order) + Etsy/Gumroad/LemonSqueezy (PDF)
```

---

## Workers

| Worker | Role | Skills |
|--------|------|--------|
| scout.md | Helium 10 niche + keyword research | claude-seo, seo-worker |
| quill.md | Colouring page description writer | humanizer, prompt-master |
| brush.md | Leonardo AI image generation | prompt-master [EINSTEIN GATED] |
| press.md | PDF assembly + KDP formatting | — |
| herald.md | Listing copywriter (all platforms) | humanizer, claude-seo, seo-worker |

---

## KDP Specs

### Interior
- Size: 8.5" x 11" (US Letter)
- Bleed: 0.125" all sides
- Resolution: 300 DPI minimum
- Color mode: Greyscale (interior) / CMYK (cover)
- File format: PDF/X-1a for print
- Pages: 40 colouring pages + front matter = ~84 pages total

### Cover
- Spine width formula: pages × 0.002252 inches (90gsm paper)
- Cover PDF: full bleed, 300 DPI, CMYK
- Front cover dimensions: 8.625" × 11.25" (with bleed)

---

## Platform Listing Status

| Platform | Adult Book | Kids Book |
|----------|------------|-----------|
| Amazon KDP | — | — |
| Etsy | — | — |
| Gumroad | — | — |
| LemonSqueezy | — | — |

---

## Revenue Tracking

| Month | Units (Print) | Units (PDF) | Revenue |
|-------|---------------|-------------|---------|
| — | — | — | $0 |

---

## QC Standard: 9.5/10 minimum. Reject and rework anything below.
