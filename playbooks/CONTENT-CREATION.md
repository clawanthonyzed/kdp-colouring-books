# ✍️ Playbook: CONTENT CREATION | KDP Colouring Books

**Owner:** Atlas (manager, Venture #38) | **QC:** Draw | **Written:** 2026-10-13 | **Loop:** Assign ➔ Equip ➔ Execute & Self-Correct ➔ Deliver

## 🎯 1. ASSIGN

| Field | Value |
|---|---|
| Owner | Atlas (helpers: scout, quill, brush, press, herald) |
| Input | A research file with a Decision (RESEARCH playbook) |
| Output | `outputs/products/<slug>/` (or the venture's existing book / release folder) |

**What this venture makes:**
- 30 to 40 page descriptions + Leonardo briefs (Quill)
- 300 DPI black and white line art (Brush, Leonardo free tier)
- Printable PDF A4 + Letter and KDP 8.5 x 11 interior (Press)
- Listing copy for each platform (Herald)
- Cover brief for Canva

**Voice:** Warm, simple, parent-friendly. Aussie scenes for Aussie books; never snow in an Australian Christmas book.

## 🧰 2. EQUIP (Toolbox first)

Check `/opt/openclaw/toolbox/INDEX.md` before writing anything new.

| Need | Tool |
|---|---|
| Markdown to print-ready PDF | `toolbox/formatters/md_to_pdf.py` |
| Copy and shot templates | `toolbox/prompt-templates/` |
| Background drafting while the laptop is shut | `toolbox/scripts/queue_task.py` |

## ⚙️ 3. EXECUTE & SELF-CORRECT

1. Write a 5-line brief: goal, buyer, inputs (links), output path, done-when.
2. Build the full asset. Free-route drafts come back in parts of 70 lines or fewer; join them verbatim.
3. Guardrails (any fail = rebuild):
- Customer-facing copy never says FIFA or World Cup (commit e63e182)
- No club crests, player names or licensed characters
- Thick closed lines, no near-duplicate pages, single-sided pages
4. Score against `QC-STANDARD.md`. Below 9.5: name the gap, fix it, score again.

## ✅ 4. DELIVER only with proof

1. Run `python3 /opt/openclaw/toolbox/formatters/proof_of_done.py <file> --github clawanthonyzed/kdp-colouring-books:<path>@master` and get **0 failures**.
2. The asset is complete: real copy, real files, no slots left for Anthony to fill.
3. Log: `python3 /opt/openclaw/toolbox/scripts/worklog.py Atlas "KDP Colouring Books" "<action>" "<GitHub link>"`
4. Report in one line with the clickable GitHub link.

## 📌 Founder Rules (permanent, from Anthony)

| Date | Rule |
|---|---|
| 2026-06-01 | Never FIFA or World Cup in customer-facing copy |
| 2026-10-13 | Brush approved on the Leonardo free tier only (A$0) |
| 2026-10-13 | Target A$2,000 per month (AUD) |
| 2026-10-13 | Printable PDFs sell through the central empire Gumroad account |

New rules from [FOUNDER-INTERVIEW.md](https://github.com/clawanthonyzed/kdp-colouring-books/blob/master/playbooks/FOUNDER-INTERVIEW.md) are added here, dated, once Anthony answers.
