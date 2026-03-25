# Website Status Update — Sorted Live + Coach Fred TestFlight

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Update ghplabs-website to reflect Sorted is publicly available on the App Store, add Coach Fred as a new experiment in TestFlight, and introduce an "In the wild" tier for shipped apps.

**Architecture:** Static HTML site — all changes are in `index.html`. Add a new top tier "In the wild" for Sorted with its App Store link, add Coach Fred (#008) to the "Ready to launch or kill" tier as a TestFlight app, and bump the experiment count to 8.

**Tech Stack:** HTML, CSS (existing `styles.css` already has all needed classes)

---

## File Structure

- Modify: `index.html` (lines 33, 38-71 tier restructuring, add Coach Fred card)
- No new files needed — all existing CSS classes support the new layout

---

### Task 1: Add "In the wild" tier with Sorted

Move Sorted out of "Ready to launch or kill" into a new top-level tier called "In the wild". Change its CTA from TestFlight to the App Store link.

**Files:**
- Modify: `index.html:33` (experiment count 7 → 8)
- Modify: `index.html:37-71` (restructure tiers)

- [ ] **Step 1: Update experiment count**

Change line 33 from:
```html
<span class="lab-note">7 experiments, various stages</span>
```
to:
```html
<span class="lab-note">8 experiments, various stages</span>
```

- [ ] **Step 2: Replace the current Tier 1 block (lines 37-71) with the new "In the wild" tier + updated "Ready to launch or kill" tier**

Replace everything from `<!-- TIER 1: READY TO LAUNCH OR KILL -->` through the closing `</div>` of that tier (line 71) with:

```html
  <!-- TIER: IN THE WILD -->
  <div class="tier">
    <div class="tier-label">In the wild</div>
    <div class="experiment-grid">
      <div class="experiment-card">
        <div class="experiment-meta">
          <span class="experiment-id">#002</span>
        </div>
        <div class="experiment-name">Sorted</div>
        <div class="experiment-tagline">Style confidence in seconds</div>
        <div class="experiment-desc">Quick outfit check before you walk out the door. Feedback that's actually useful.</div>
        <a href="https://apps.apple.com/us/app/sorted-ai-style-check/id6758172664" class="cta-btn">Get it on the App Store</a>
        <div class="legal-links">
          <a href="/sorted/privacy.html">Privacy</a>
          <span class="dot">&#9679;</span>
          <a href="/sorted/terms.html">Terms</a>
        </div>
      </div>
    </div>
  </div>

  <!-- TIER 1: READY TO LAUNCH OR KILL -->
  <div class="tier">
    <div class="tier-label">Ready to launch or kill</div>
    <div class="experiment-grid">
      <div class="experiment-card">
        <div class="experiment-meta">
          <span class="experiment-id">#001</span>
        </div>
        <div class="experiment-name">ClipCook</div>
        <div class="experiment-tagline">Your AI sous chef</div>
        <div class="experiment-desc">Save recipes from any video, get personalized cooking guidance, and remix dishes to your taste.</div>
        <a href="https://testflight.apple.com/join/FTNNurwK" class="cta-btn">Join the beta</a>
        <div class="legal-links">
          <a href="/clipcook/privacy.html">Privacy</a>
          <span class="dot">&#9679;</span>
          <a href="/clipcook/terms.html">Terms</a>
        </div>
      </div>

      <div class="experiment-card">
        <div class="experiment-meta">
          <span class="experiment-id">#008</span>
        </div>
        <div class="experiment-name">Coach Fred</div>
        <div class="experiment-tagline">Your team's smartest assistant coach</div>
        <div class="experiment-desc">AI-powered game day toolkit for youth sports. Lineups, walk-up music, announcements, and coaching — so you can focus on the kids.</div>
        <a href="https://coachfred.app" class="cta-btn">Try the beta</a>
        <div class="legal-links">
          <a href="https://coachfred.app/privacy">Privacy</a>
          <span class="dot">&#9679;</span>
          <a href="https://coachfred.app/terms">Terms</a>
        </div>
      </div>
    </div>
  </div>
```

Note: Coach Fred's legal links point to `coachfred.app/privacy` and `coachfred.app/terms` (its own domain) since it doesn't have pages on ghplabs-website yet.

- [ ] **Step 3: Verify the HTML structure**

Open `index.html` in a browser or run a quick validation:
```bash
# Verify no broken HTML structure
python3 -c "from html.parser import HTMLParser; HTMLParser().feed(open('index.html').read()); print('HTML OK')"
```

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: sorted → app store, add coach fred to testflight tier"
```

---

## Open Questions

1. **Coach Fred TestFlight link** — Currently linking to `coachfred.app`. If there's a TestFlight join URL, swap it in and change the CTA to "Join the beta".
2. **Coach Fred legal pages on ghplabs-website** — Currently pointing to `coachfred.app/privacy` and `coachfred.app/terms`. If those pages don't exist yet, they'll need to be created (either on the Coach Fred web app or as `/coachfred/privacy.html` on ghplabs-website).
3. **Coach Fred tagline** — BRAND.md says "Tagline TBD". I used "Your team's smartest assistant coach" from the positioning section. Adjust if you have a preferred tagline.
