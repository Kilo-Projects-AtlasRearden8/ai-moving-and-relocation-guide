# STATUS

## What was built

A beginner manual and static HTML site on using AI for moving and relocation, published by Asdale Dynamics, LLC.

**Project files**

- `LICENSE` — MIT License, copyright line exactly `Copyright (c) 2026 Asdale Dynamics, LLC`
- `README.md` — project overview, credits Asdale Dynamics, LLC, links to the manuals
- `.gitignore` — standard ignores (no secrets committed)
- `.markdownlint.yaml` — lint config (MD013 line-length disabled; prose/URLs left unwrapped)
- `verify.py` — verification script: HTML structure, internal links, license/credit lines, required docs, no `.github/workflows`, no secrets patterns
- `docs/` — beginner manuals in Markdown
  - `privacy.md` — golden rule: no sensitive IDs or financial details with AI; stranger test; local-first; not legal/financial advice
  - `intro.md` — what AI is, where to start, how to prompt, starter routine, what's inside
  - `packing-checklists.md` — week-by-week moving timeline, room-by-room packing list, essentials box, what not to pack, AI prompts
  - `address-change-timeline.md` — who to notify and when, address-change tracker, what to have ready, AI prompts
  - `utility-transfers.md` — electricity, gas, water, internet, phone, trash timeline; transfer tracker; AI prompts
  - `budget-tracking.md` — common expense categories, fill-in-yourself budget table (example amounts only), tracking tips, AI prompts
  - `room-by-room-inventory.md` — how to inventory, room-by-room checklist, inventory table, photos, insurance, AI prompts
  - `printable-moving-planner.md` — printable planner: timeline checklist, essentials box, address/utility/budget trackers, inventory, tips
- `site/` — same manuals as a static HTML website
  - `index.html` — home page with privacy callout and full navigation
  - one HTML page per doc (`privacy`, `intro`, `packing-checklists`, `address-change`, `utility-transfers`, `budget-tracking`, `room-by-room`, `printable-moving-planner`)
  - `style.css` — shared warm, print-friendly styles with `@media print` and print page-break rules

**Credit & privacy**

- Asdale Dynamics, LLC credited in `README.md`, every HTML footer, and every doc's closing line.
- Hub site referenced: dylanasdale.github.io (behind *The Massive AI Manual*).
- Privacy-first throughout: golden rule (no sensitive IDs or financial details with AI) appears on the privacy page, home page, and as callouts/reminders across docs.
- All dollar amounts and values in tables are clearly marked examples/placeholders ($0.00, EXAMPLE). No real account numbers, credit card numbers, or personal data anywhere.
- No secrets, API keys, or personal data in any file. No `.github/workflows` files. No remote repos created. Nothing pushed.

## How to run it

- **Read the manuals:** open any file in `docs/` in a Markdown viewer or text editor. Start with `docs/privacy.md`.
- **View the website:** open `site/index.html` in any browser. No build step, no server required — plain static HTML + CSS.
- **Print the planner:** open `site/printable-moving-planner.html` (or print `docs/printable-moving-planner.md`), press `Ctrl+P` (or `Cmd+P`), and print. In the print dialog, turn off headers/footers and set margins to None/Minimum.
- **Host anywhere:** the `site/` folder is deployable to any static host as-is. Not done here per instructions (no remote, no publish).

## Verification results

- `python3 verify.py` — VERIFICATION PASSED: all checks ok (9 HTML pages structure-valid, all internal links resolve, LICENSE exact copyright line present, README credits Asdale Dynamics, LLC, all docs credited, no `.github/workflows`, no secret patterns found).
- `npx htmlhint "site/*.html"` — 9 files scanned, no errors.
- `npx markdownlint "docs/*.md"` — no errors (config in `.markdownlint.yaml`).
- No test runner or build script exists in this project (static site + Markdown manuals); verification is lint + the verify.py script.
- No secrets/API keys/personal data present (verify.py grep-confirmed absent).
- Local AI app recommendations (Ollama, LM Studio) are mentioned but not bundled or tested in this repo.

## Known gaps

- No automated test suite or CI (intentionally none — no `.github/workflows`). Verification is lint + verify.py only.
- HTML not run through a formal validator (W3C) — htmlhint used instead; pages are simple, well-formed HTML5.
- The external hub link (dylanasdale.github.io) and MIT license link (opensource.org) were not fetched/live-checked.
- Printable planner physical layout depends on printer and paper; print a test page first.
- Single commit only; no release tagging.
- Not legal, financial, or medical advice; a disclaimer appears in the README, privacy page, and site footers.
