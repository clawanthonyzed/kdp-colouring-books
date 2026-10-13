# 🔬 Playbook: RESEARCH | KDP Colouring Books

**Owner:** Atlas (manager, Venture #38) | **QC:** Draw | **Written:** 2026-10-13 | **Loop:** Assign ➔ Equip ➔ Execute & Self-Correct ➔ Deliver

## 🎯 1. ASSIGN

| Field | Value |
|---|---|
| Owner | Atlas (helpers: scout, quill, brush, press, herald) |
| Run when | Before any new product, book, release or price change |
| Output | `outputs/research/<YYYY-MM-DD>-<topic>.md` |

**Questions this playbook answers:**
- Which colouring theme is rising in the next 60 days (season, holiday, school calendar)?
- For the top 10 to 20 keywords: how many strong competitor books, their prices, page counts and 1-star complaints?
- Is any wording a trademark risk (teams, leagues, tournaments, characters)?

## 🧰 2. EQUIP (Toolbox first)

Check `/opt/openclaw/toolbox/INDEX.md` before writing anything new.

| Need | Tool |
|---|---|
| Public web page (blocked or not) | `toolbox/scrapers/stealth_fetch.py <url> --out file.md` |
| Video or post transcript | `toolbox/scrapers/media_ingest.py` (run with its own venv, see INDEX) |
| Turn notes into a PDF | `toolbox/formatters/md_to_pdf.py` |

**Sources for this venture:**
- Amazon.com.au + Amazon.com search and best-seller pages (read only)
- Etsy search pages (read only)
- `research/niche-analysis.md` + `research/helium10-strategy.md`
- Helium 10 only when credentials exist (Einstein gate)

## ⚙️ 3. EXECUTE & SELF-CORRECT

1. Write the question at the top of the file.
2. Collect evidence: at least 3 sources, each with a working link and the date checked.
3. Put findings in a table: claim, number, source link.
4. End with **Decision**: one recommendation the next playbook can act on, with the reason.
5. Self-check: every number has a source; anything unproven is removed, not guessed.

## ✅ 4. DELIVER only with proof

1. Run `python3 /opt/openclaw/toolbox/formatters/proof_of_done.py <file> --github clawanthonyzed/kdp-colouring-books:<path>@master` and get **0 failures**.
2. Every claim in the table has a link that opens.
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
