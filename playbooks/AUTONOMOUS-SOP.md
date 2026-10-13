# ⚙️ Autonomous SOP | KDP Colouring Books Assembly Line

**Owner:** Atlas | **QC:** Draw | **Written:** 2026-10-13 | **Applies to:** every book, page, file and listing
**Loop:** EXECUTE ➔ TEST ➔ REFINE ➔ SHIP. Nothing skips a station.

---

## 🏭 The Line at a Glance

| # | Station | Agent | Output (saved to) | Gate |
|---|---|---|---|---|
| 1 | 🔎 Research | Scout | 10 to 20 keywords + 3 competitor books (`outputs/research/`) | |
| 2 | ✍️ Pages | Quill | 30 to 40 descriptions + Leonardo briefs (`outputs/content/`) | |
| 3 | 🎨 Art | Brush | 300 DPI black and white line art (`books/<slug>/pages/`) | 🛑 Brush hold |
| 4 | 📄 Assemble | Press | Printable PDF (A4 + Letter) + KDP interior (`books/<slug>/`) | |
| 5 | 📣 Listing | Herald | Copy for each platform (`books/<slug>/listing.md`) | |
| 6 | ✅ QC | Draw | Scorecard vs `QC-STANDARD.md` (`outputs/qc/`) | 9.5+ |
| 7 | 🚀 Ship | Atlas | Live URLs in `CURRENT-STATE.md` + work log | 🛑 Anthony on accounts |
| 8 | 📈 Learn | Scout | Day-7 and Day-30 keep / fix / kill note | |

---

## 1️⃣ EXECUTE

1. Atlas opens the week in [90-DAY-AGENT-ROADMAP.md](https://github.com/clawanthonyzed/kdp-colouring-books/blob/master/outputs/90-DAY-AGENT-ROADMAP.md), then dispatches:
   - Live session: `POST http://localhost:8400/agents/{worker}/tasks/send`
   - Laptop-shut: `python3 /opt/openclaw/orchestration/queue_task.py --agent <worker> --venture "KDP Colouring Books" --title "<title>" --brief "<brief>"`
2. Every brief has 5 lines: **book, age group, inputs (file links), output path, done-when.**
3. Free route: about 50 calls a day; ask for parts of **70 lines or fewer** (e.g. pages 1 to 15, then 16 to 30).
4. Brush, Press and file work need a full-tool session. Free route drafts text only.

## 2️⃣ TEST (Draw)

| Check | Pass mark |
|---|---|
| 📊 `QC-STANDARD.md` weighted score | **9.5 of 10**, flagship 10 |
| ✏️ Lines | Thick, closed, no broken edges (ages 4 to 8 need thicker still) |
| 🧒 Repeats | No two pages near-identical; Press lays all pages side by side |
| 📄 Print | Single-sided pages, 8.5 x 11 in, 0.125 in bleed, 300 DPI, greyscale |
| 🖨️ Printable PDF | A4 + US Letter, nothing clipped |
| 🇦🇺 Theme | Aussie books: zero snow, real Aussie scenes |
| ⚖️ Trademark | No FIFA, World Cup, club crests, player names |
| ✍️ Copy | humanizer + stop-slop PASS, no em dashes, A$ prices |

## 3️⃣ REFINE

1. Draw writes each gap as **page / field ➔ problem ➔ fix.**
2. Rework goes back to the **same worker** (bad page ➔ Brush regenerates that page only).
3. Re-test after every fix. Two fails on the same page = Quill rewrites that page's brief.

## 4️⃣ SHIP

1. 🛑 Anthony OKs each account once (KDP, Gumroad, LemonSqueezy, Etsy fee, social) via Idea Lobster.
2. Order: **Gumroad PDF first** (live in hours) ➔ KDP paperback (up to 72 hours review) ➔ mirrors.
3. Log the live URL in one line:
   `| [YYYY-MM-DD HH:MM AWST] | Atlas | KDP Colouring Books | Shipped <book> PDF A$<x> / paperback A$<y> | <link> |`
4. Update the Book Pipeline table in `CURRENT-STATE.md` and the listing table in `VENTURE.md`.

---

## 🧭 Daily Rhythm (Atlas)

| When | Do |
|---|---|
| 🌅 Start | Read `memory/README.md`, `VENTURE.md`, `CURRENT-STATE.md`, last 20 work-log rows |
| ☀️ Mid | Inspect drafts, run TEST, send REFINE orders |
| 🌙 End | Update `CURRENT-STATE.md`, one work-log line per finished task |

## 🚨 Escalate to Idea Lobster when

- 🎨 Brush is needed while the hold is on
- 💳 Money, 🔑 accounts or ⚖️ trademark questions come up
- 📉 0 sales 14 days after a launch
- ❓ A fact cannot be verified (say so, never guess)
