# ghplabs-website — Status

**Last synced:** 2026-02-20
**Author:** Jet

## Current State

Static website for GHP Labs (ghplabs.ai). Hosted via GitHub Pages or similar static hosting.

### Structure
- `/` — Main GHP Labs landing page (`index.html`, `styles.css`)
- `/rosie/` — Rosie product pages:
  - `index.html` — Redirect to rosiefamilyassistant.com
  - `privacy.html` — Privacy Policy (effective 2026-02-13)
  - `terms.html` — Terms of Service (effective 2026-02-13)
  - `sms.html` — SMS disclosure page for A2P/CTIA compliance

## Changes — 2026-02-13 (3 commits)

1. **c1e4bc0** — `[Jet] Add Rosie privacy policy and terms of service for A2P campaign`
   - Added `rosie/privacy.html` (141 lines) — full privacy policy covering data collection, SMS terms, sharing, retention
   - Added `rosie/terms.html` (150 lines) — ToS with AI disclaimer, SMS terms, shared family features, STOP/HELP keywords

2. **eb7bcd7** — `[Jet] Add Rosie landing redirect to rosiefamilyassistant.com`
   - Added `rosie/index.html` — meta-refresh redirect to rosiefamilyassistant.com

3. **caae2d0** — `Add Rosie SMS disclosure page for A2P compliance`
   - Added `rosie/sms.html` (218 lines) — CTIA-compliant SMS disclosure with brand ID, message types, frequency, consent language, opt-out keywords, sample messages, data handling
   - Phone number: +1 (415) 548-4794
   - Links to privacy/terms pages

**Total:** 4 files added, 520 insertions. All Rosie-related pages for A2P 10DLC campaign compliance.

## Changes — 2026-02-15 (1 commit)

1. **02ca428** — `[Jet] chore: add STATUS.md with project state and recent Rosie compliance pages`

**Total:** 1 commit. STATUS.md added.
