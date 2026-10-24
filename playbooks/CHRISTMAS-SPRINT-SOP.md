# Playbook: Christmas 2026 Sprint (KDP Colouring Books, venture #38)

Written 2026-10-23 under the Autonomous Playbook Protocol. Owner: Atlas. Next run should follow this file unaided.

## Trigger
A seasonal book is approved for production. Christmas 2026 trigger: Anthony's instruction of 2026-10-23. Target: both books live on Amazon before Black Friday, 27 November 2026 (upload by 20 November).

## Inputs
| Input | Where |
|---|---|
| Verified KDP specs | outputs/AMAZON-KDP-PRODUCT-SPECS.md |
| Book specs and page plan | outputs/CHRISTMAS-2026-SPRINT-PLAN.md |
| Fact banks (the only facts allowed in the books) | Sprint plan, section 3 |
| Brush style guide and Draw rubric | Queue outputs linked in the sprint plan |
| Leonardo free tier | LEONARDO_API_KEY is set on the server (not printed or shared) |

## Steps (one owner each, in order)
| # | Owner | Job | Done when (proof) |
|---|---|---|---|
| 1 | Scout | Keyword niches and Amazon best sellers rank (BSR) data. Record the top 10 results for 5 chosen search phrases in the competitor table; apply the go or no-go rules | Filled competitor table committed; 7 backend keyword phrases per book chosen |
| 2 | Quill | Page-by-page plan: title, illustration description, one fact per page, 4 parts of 20 pages (40 pages per book) | 80 rows; every fact traces to the fact bank or has a named source |
| 3 | Brush | Line art from Quill's descriptions with the style-guide template. Thick even outlines, closed shapes, zero grey, zero shading, no text in the image, 2550 x 3300 px, art inside a 0.5 in margin | 80 PNG files, named bookN-pNN-subject.png, all pass Brush's own reject checklist |
| 4 | Draw | QC against the 10/10 rubric: closed boundaries, no trademark or character text, fact accuracy, age fit, page format | Score 95 or more per page; failed pages go back to the agent that made them with the exact fault |
| 5 | Press | Interior PDF (80 pages, 8.5 x 11, black and white) and the full cover wrap (17.430 x 11.250 in for 80 pages on white paper) | Both files open; page count even; spine matches paper type; Draw signs off the files |
| 6 | Atlas | Launch-day checklist, then hand the upload package to Anthony | Package folder on GitHub; checklist filled |

## Commands and tools
| Need | Use |
|---|---|
| Queue a step for the cloud runner | python3 /opt/openclaw/toolbox/scripts/overnight_queue.py tasks.json |
| Quality check on any text deliverable | python3 /opt/openclaw/toolbox/formatters/proof_of_done.py file.md |
| Push a file to GitHub with retry | toolbox/scripts/gh_push.py |
| Image to PDF assembly | Pillow, reportlab, PyMuPDF and Ghostscript are installed on the server |
| Image generation | Leonardo API from a script run by a full-tool session (the free cloud route writes text only) |

## Checks (10/10 loop)
1. Each text step: Proof-of-Done checker, 0 failures.
2. Each image: Brush reject checklist, then Draw's score.
3. Each file: opens, correct page size, correct page count, fonts embedded.
4. Fail means fix and retest by the owner. Never passed on.

## Outputs
Specs, plan and playbook: clawanthonyzed/kdp-colouring-books/outputs and playbooks. Page plans and rubrics land in second_brain/overnight/kdp-colouring-books while this repo is public. Images and PDFs: a private location until Anthony approves the upload.

## Hard stops
- No named copyrighted or trademarked characters (Rudolph, the Grinch, Frosty, Elf), no brand logos, no mascots, no "FIFA" or "World Cup" wording on anything customer-facing.
- Every image is AI-generated, so the KDP AI-disclosure answer is yes. The account holder answers it.
- Facts come only from the fact bank. A new fact needs a named source and Draw's check before it goes in.
- Nothing is uploaded, posted or priced without Anthony. Spending money or credits beyond the Leonardo free tier needs Einstein and Anthony.

## Escalation (only these go to Anthony)
| Item | Why |
|---|---|
| Amazon KDP account confirmed and logged in | Account is Anthony's |
| AI-disclosure answer and final upload click | Account holder action |
| Leonardo free-tier credit budget per day | Credits are limited; a batch of 80 images may need several days |
| Final price per marketplace | Money decision |

## Lessons from the first build (2026-10-24)
| Lesson | Rule for the next run |
|---|---|
| Leonardo's Lightning model returns photos, not line art | Use the Phoenix model with the "Coloring book page for kids" wording (toolbox/scripts/leonardo_batch.py) |
| Colour and mood words in a prompt (a red bow, morning light, golden) pull the picture into colour or solid black | Strip them; the batch script does this automatically |
| Roughly 1 in 3 first tries has solid black areas | The batch script checks each page with qc_pages.py and retries up to 4 times with simpler wording |
| The model sometimes prints a website name along the bottom edge | The bottom 6 percent of every image is blanked before it is placed on the page |
| AI cover art contains made-up text | Crop the picture to the animals and beach band and set all lettering ourselves |
| Interior PDF | build_book.py (reportlab) then Ghostscript to grey: `gs -sDEVICE=pdfwrite -sColorConversionStrategy=Gray ...`; check with pdfinfo, pdffonts, pdfimages |
| The KDP repo is public | Finished books and images go to the private second_brain repo until Anthony approves |

## Lessons from Book 2 (2026-10-24)
| Lesson | Rule for the next run |
|---|---|
| AI plates sometimes draw words on signs and cakes (a sign that read CHRISTMAAS) | Put "no signs, no words, no writing" in every prompt, then look at a contact sheet of every plate before building |
| A prompt with "soldiers" and "football" gave American football players | Name the clothes and the era ("long coats and soft caps") and look at the result |
| A page template that fits English can overflow in German and French | The builder prints a WARN line when a page runs out of room; fix before the PDF is accepted |
| Japanese crosswords place only 5 to 7 words | Kana words share few letters; give the generator a pool of 12 words and accept the entries that fit, or choose words with common letters |
| Cover art contains made-up lettering | Crop the picture to the artwork band and set all lettering yourself (same as Book 1) |
| Recipes are text only | Mark them as untested until an adult has cooked them |
| Facts | Search each fact in a published source and keep the register in BOOK2-QC-REPORT.md; claims with no source are listed, never hidden |

## Lessons from the colour revision (2026-10-24)
| Lesson | Rule for the next run |
|---|---|
| The reader said it is an activity book: no drawing boxes | In an activity or facts book the only pen work is in puzzles and quick checks. Never add blank "draw here" areas. A reviewer card should ask this before the build |
| Colour costs about double to print | Work out the print cost per marketplace with kdp_royalty.py BEFORE choosing colour, and price from the minimum list price |
| The picture tool draws on paid API credits | Check the Leonardo apiPaidTokens balance before and after a batch (about 11 credits per large colour plate) and tell Anthony the cost |
| Wide colour pictures can carry stray text and signatures | Look at every plate on a contact sheet, regenerate the faulty ones, and let the layout crop the bottom edge |
| Layout must flex | Pages measure first and then choose the largest font that fits, so German and French fit as well as English |
| A near-identical title may already exist | Search the title on Amazon before the cover is made |
