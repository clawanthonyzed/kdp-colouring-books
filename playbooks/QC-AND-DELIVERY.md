# 🧪 Playbook: QC AND DELIVERY | KDP Colouring Books

**Owner:** Atlas (manager, Venture #38) | **QC:** Draw | **Written:** 2026-10-13 | **Loop:** Assign ➔ Equip ➔ Execute & Self-Correct ➔ Deliver

## 🎯 1. ASSIGN

| Field | Value |
|---|---|
| QC owner | Draw (backup: the venture's qc rubric agent) |
| Delivery owner | Atlas |
| Standard | `QC-STANDARD.md` (9.5 minimum, flagship 10) + `/opt/openclaw/orchestration/PROOF-OF-DONE-STANDARD.md` |

## 🧰 2. EQUIP (Toolbox first)

Check `/opt/openclaw/toolbox/INDEX.md` before writing anything new.

| Need | Tool |
|---|---|
| Automatic Proof-of-Done checks | `toolbox/formatters/proof_of_done.py <file> --github <repo>:<path>@<branch>` |
| Push and verify on GitHub | `toolbox/scripts/gh_push.py` |
| Work-log row | `toolbox/scripts/worklog.py` |

## ⚙️ 3. EXECUTE & SELF-CORRECT

**Venture checks (any fail = reject):**
- Every page passes line and repeat checks side by side
- KDP interior: 8.5 x 11 in, 0.125 in bleed, 300 DPI, greyscale
- Printable PDF: A4 + Letter, nothing clipped

**Universal checks:** no placeholders, no em dashes, no AI buzzwords, all links open, code and data ran with 0 errors, A$ prices.

**Rework rule:** Draw writes each gap as *where ➔ problem ➔ fix* and sends it back to the agent that made it. Two fails in a row = rewrite the brief, then rebuild.

## ✅ 4. DELIVER only with proof

1. Run `python3 /opt/openclaw/toolbox/formatters/proof_of_done.py <file> --github clawanthonyzed/kdp-colouring-books:<path>@master` and get **0 failures**.
2. The file is committed to `clawanthonyzed/kdp-colouring-books` and the checker confirms it on GitHub.
3. Only now may Anthony be told, and only with the link.
4. Log: `python3 /opt/openclaw/toolbox/scripts/worklog.py Atlas "KDP Colouring Books" "<action>" "<GitHub link>"`
5. Report in one line with the clickable GitHub link.

## 🚨 Escalate to Anthony (via Idea Lobster) only for

- 💳 Money, 🔑 accounts, ⚖️ legal
- ❓ A fact only Anthony knows: add it to `FOUNDER-INTERVIEW.md` as a new question, never guess

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
