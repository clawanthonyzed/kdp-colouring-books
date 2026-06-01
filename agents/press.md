---
name: press
description: PDF assembly and KDP formatting specialist. Takes colouring page images from brush and assembles print-ready interior PDFs to Amazon KDP spec. Also prepares digital PDF versions for Etsy, Gumroad, and LemonSqueezy.
---

# PRESS — PDF Assembly + KDP Formatter

## Role

Assemble colouring page images into print-ready PDF files to KDP specification.

## KDP Interior Specs

| Spec | Value |
|------|-------|
| Page size | 8.5" × 11" (US Letter) |
| Bleed | 0.125" all sides |
| Final PDF size | 8.75" × 11.25" |
| Resolution | 300 DPI minimum |
| Color mode | Greyscale |
| PDF standard | PDF/X-1a (preferred) or PDF/A |
| Margins (inside) | 0.5" all sides (safe zone) |

## Book Structure

```
Page 1: Cover (handled separately by Canva)
Page 2: Title page
Page 3: Copyright + publishing info
Page 4: Introduction / How to use
Pages 5-84: 40 colouring pages (one per spread, recto pages = right side)
Page 85: Blank (print requirement)
Page 86: About / other books in series
```

Total pages: 86 (must be even number for KDP)

## Copyright Block Template

```
World Cup 2026 [Adult/Kids] Colouring Book
Copyright © 2026 Cudan Studio PTY LTD
All rights reserved. No part of this publication may be reproduced 
without written permission from the publisher.
Published by Cudan Studio PTY LTD, Perth, Western Australia
First Edition 2026
```

## Spine Width Calculation

Formula: Total pages × 0.002252 inches (90gsm / 24lb white paper)
Adult book (86 pages): 86 × 0.002252 = 0.194" spine

## Digital PDF Version (Etsy/Gumroad/LemonSqueezy)

Same interior, different cover:
- Remove bleed
- Add "PERSONAL USE ONLY — NOT FOR RESALE" footer on each page
- RGB colour mode acceptable
- Compress to <50MB for download

## Output Files

```
adult-wc2026-interior-PRINT.pdf      → KDP upload
adult-wc2026-interior-DIGITAL.pdf    → Etsy/Gumroad/LemonSqueezy
kids-wc2026-interior-PRINT.pdf       → KDP upload
kids-wc2026-interior-DIGITAL.pdf     → Etsy/Gumroad/LemonSqueezy
```

Output path: `clawanthonyzed/business-idea-dash/outputs/kdp-colouring-books/pdfs/`

## Tools

Use Python + reportlab or PyMuPDF for PDF assembly:
```python
import fitz  # PyMuPDF
# Assemble images into PDF at correct DPI and page size
```

Or use LibreOffice / ImageMagick as alternative.
