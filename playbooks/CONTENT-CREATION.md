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
- Covers in-house: Brush art + Press layout

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
- Off-limits ONLY: politics, explicit content, trademarked or licensed characters (angelic and faith themes approved)
- Sports titles only ahead of a major tournament; trademarked event names (FIFA, World Cup, Olympics) never in customer copy
- Thick closed lines, no near-duplicate pages, single-sided pages
4. Score against `QC-STANDARD.md`. Below 9.5: name the gap, fix it, score again.

## ✅ 4. DELIVER only with proof

1. Run `python3 /opt/openclaw/toolbox/formatters/proof_of_done.py <file> --github clawanthonyzed/kdp-colouring-books:<path>@master` and get **0 failures**.
2. The asset is complete: real copy, real files, no slots left for Anthony to fill.
3. Log: `python3 /opt/openclaw/toolbox/scripts/worklog.py Atlas "KDP Colouring Books" "<action>" "<GitHub link>"`
4. Report in one line with the clickable GitHub link.

## 📌 Founder Rules (permanent, from Anthony)

Source of truth: [FOUNDER-RULES.md](https://github.com/clawanthonyzed/kdp-colouring-books/blob/master/playbooks/FOUNDER-RULES.md). Summary:

| Type | Rule |
|---|---|
| 🔒 locked | Amazon KDP account under Cudan Studio Pty Ltd |
| 🔒 locked | Atlas proposes 3 pen names; Anthony picks one |
| 🔒 locked | Anthony approves the first 2 books; after that Atlas submits any book that passes QC at 9.5+ |
| 🔒 locked | Covers made in-house by Brush (art) and Press (layout) |
| 🔒 locked | Paperback list price A$9.99 to A$19.99 |
| 🔒 locked | Declare AI-generated content on KDP's internal checkbox every time; no AI badges or AI wording on customer-facing pages |
| 🔒 locked | Off-limits themes ONLY: politics, explicit content, trademarked or licensed characters. Angelic and faith themes are approved |
| 🔒 locked | No monthly volume cap: publish as many books as pass the 10/10 quality bar |
| 🔒 locked | Free sample pages are generated automatically for every book |
| 🔒 locked | EVENT-DRIVEN SPORTS: sports books are made ONLY ahead of a major world cup or tournament (e.g. the 2027 women's soccer tournament, Olympics), never year-round |
| 🛡️ floor | Tournament and brand names stay out of customer-facing copy (FIFA, World Cup, Olympics are trademarks); use descriptive wording like 'Women's Soccer 2027' |
| 🔒 locked | Leonardo: wait for the daily 150 free credits, or use a fallback tool of equal quality at A$0 |
