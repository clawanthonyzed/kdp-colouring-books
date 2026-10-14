# 🛒 Playbook: MARKETPLACE LISTING | KDP Colouring Books

**Owner:** Atlas (manager, Venture #38) | **QC:** Draw | **Written:** 2026-10-13 | **Loop:** Assign ➔ Equip ➔ Execute & Self-Correct ➔ Deliver

## 🎯 1. ASSIGN

| Field | Value |
|---|---|
| Owner | Atlas |
| Input | An asset that passed QC-AND-DELIVERY |
| Output | A live listing URL logged in `CURRENT-STATE.md` |

**Where this venture sells:**

| Platform | Status |
|---|---|
| Gumroad | Central empire account (Anthony 2026-10-13): printable PDFs ship here first |
| Amazon KDP | Account under Cudan Studio Pty Ltd; first 2 books need Anthony's OK, then submit on 9.5+ |
| LemonSqueezy | Mirror store, Anthony OK on account |
| Etsy | US$0.20 per listing (A$0.29 converted): Anthony OK first |

**Pricing rule:** Paperback A$9.99 to A$19.99; printable PDFs A$6.90 to A$10.02. AI declared on KDP's internal checkbox, never on customer pages.

## 🧰 2. EQUIP (Toolbox first)

Check `/opt/openclaw/toolbox/INDEX.md` before writing anything new.

| Need | Tool |
|---|---|
| Push listing copy and screenshots to GitHub | `toolbox/scripts/gh_push.py` |
| Check copy before it goes live | `toolbox/formatters/proof_of_done.py` |

## ⚙️ 3. EXECUTE & SELF-CORRECT

1. Listing checklist: title with the buyer's search words, 3 preview images, what's inside, who it's for, A$ price, refund line.
2. Save the copy to `outputs/listings/<slug>.md` and run the Proof-of-Done checker on it.
3. Only list on a platform whose status above is cleared. Anything marked "Anthony OK" goes to Idea Lobster first, once per account.
4. After listing, open the live URL logged out and confirm price, images and delivery work.

## ✅ 4. DELIVER only with proof

1. Run `python3 /opt/openclaw/toolbox/formatters/proof_of_done.py <file> --github clawanthonyzed/kdp-colouring-books:<path>@master` and get **0 failures**.
2. The live listing URL opens logged out and shows the right price.
3. `CURRENT-STATE.md` lists the URL.
4. Log: `python3 /opt/openclaw/toolbox/scripts/worklog.py Atlas "KDP Colouring Books" "<action>" "<GitHub link>"`
5. Report in one line with the clickable GitHub link.

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
