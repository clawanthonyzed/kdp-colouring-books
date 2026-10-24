# Playbook: Localisation engine (KDP Colouring Books, venture #38)

Written 2026-10-24 under the Autonomous Playbook Protocol. Owner: Atlas. Proven on Book 2 (English plus Spanish, German, Italian, French, Japanese). The next run should follow this file unaided.

## Trigger
A finished English master book whose pictures contain no words, to be sold on other Amazon marketplaces.

## Inputs
| Input | Where |
|---|---|
| English master text as content units | lang_en.py (one dictionary: ui strings, countries, gift bringers, recipes, stories, quizzes, word banks, crossword clues) |
| Language-neutral data | book2_common.py (page order, art plate names, quiz answer keys) |
| Shared art | Text-free plates, one per content unit, generated once |

## Steps
| # | Owner | Job | Done when (proof) |
|---|---|---|---|
| 1 | Quill | Copy lang_en.py to lang_xx.py and translate every unit into natural local phrasing. Keep the same keys and counts. Greetings and place names keep their local form | book2_qc.py reports the same content units as English |
| 2 | Quill | Write native word banks (10 words per word search, 8 crossword entries with clues). Words with accents are stored with accents, the grid strips them | Word searches and crosswords build with 0 errors |
| 3 | Press | Run make_book2_all.sh: builds every edition, converts to grey with Ghostscript, builds covers, runs QC | TOTAL FAILS 0 |
| 4 | Draw | Look at a contact sheet of each edition, compare the same page across languages (BOOK2-LANGUAGES-COMPARE.png), check overflow and fonts | No clipped text, no missing glyphs |
| 5 | Native reviewer | Read the translation and the word banks | Reviewer's corrections applied and the edition rebuilt |
| 6 | Atlas | Marketplace listing per language (title, subtitle, keywords chosen in that language) | Listing text approved by Anthony |

## Commands
| Need | Use |
|---|---|
| Build everything | bash book2-work/src/make_book2_all.sh |
| Puzzle generators | puzzles.py (make_wordsearch, make_crossword, both self-verifying) |
| QC | book2_qc.py out_dir work_dir |
| Fonts | Noto Sans and Noto Serif for Latin, IPAGothic for Japanese, Noto Sans Ethiopic for Amharic greetings |

## Hard stops
- No machine translation goes to print without a native review.
- Nothing is uploaded or priced without Anthony. The AI-disclosure answer is yes and is given by the account holder.
- Do not re-generate art for a translation; the plates must stay text-free.

## Escalation
| Item | Why |
|---|---|
| Budget for a native reviewer per language | Money decision |
| Which marketplaces to launch | Anthony's call |
