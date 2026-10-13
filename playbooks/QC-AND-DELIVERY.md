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

| Date | Rule |
|---|---|
| 2026-06-01 | Never FIFA or World Cup in customer-facing copy |
| 2026-10-13 | Brush approved on the Leonardo free tier only (A$0) |
| 2026-10-13 | Target A$2,000 per month (AUD) |
| 2026-10-13 | Printable PDFs sell through the central empire Gumroad account |

New rules from [FOUNDER-INTERVIEW.md](https://github.com/clawanthonyzed/kdp-colouring-books/blob/master/playbooks/FOUNDER-INTERVIEW.md) are added here, dated, once Anthony answers.
