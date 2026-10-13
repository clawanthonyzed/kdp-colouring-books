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
| Amazon KDP | Paperback; account not yet confirmed: interview Q1 |
| LemonSqueezy | Mirror store, Anthony OK on account |
| Etsy | US$0.20 per listing (A$0.29 converted): Anthony OK first |

**Pricing rule:** Kids PDF A$6.90 to A$7.15, adult PDF A$10.02; paperbacks A$12.99 to A$18.61 (US$ list prices converted at RBA rate).

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

| Date | Rule |
|---|---|
| 2026-06-01 | Never FIFA or World Cup in customer-facing copy |
| 2026-10-13 | Brush approved on the Leonardo free tier only (A$0) |
| 2026-10-13 | Target A$2,000 per month (AUD) |
| 2026-10-13 | Printable PDFs sell through the central empire Gumroad account |

New rules from [FOUNDER-INTERVIEW.md](https://github.com/clawanthonyzed/kdp-colouring-books/blob/master/playbooks/FOUNDER-INTERVIEW.md) are added here, dated, once Anthony answers.
