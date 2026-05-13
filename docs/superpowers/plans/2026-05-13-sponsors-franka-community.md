# Sponsors & Franka Community Update — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add four new sponsors across a new tier and two existing tiers, plus add Franka Community as an inline sub-link and a standalone resource card.

**Architecture:** Pure HTML edits across two static pages. All new logo assets already exist in `img/sponsors/`. No new CSS files — one new CSS rule added to competition.html's inline `<style>` block.

**Tech Stack:** Static HTML, inline CSS custom properties (`var(--accent-dark)`, `var(--text-muted)`, etc.), existing `.sponsor-logo` / `.sponsors-tier` class patterns.

**Spec:** `docs/superpowers/specs/2026-05-13-sponsors-franka-community-design.md`

---

## Files to Modify

| File | Changes |
|---|---|
| `index.html` | Wrap Franka card; insert Infrastructure tier; pluralize Computing heading + add Alibaba Cloud; add HHRI to Community |
| `competition.html` | Same sponsor changes as index.html (different max-height/opacity for community tier) + add `.community-resource-card` CSS + Community Resources section |

---

## Task 1: Update index.html Sponsors

**File:** `index.html`

### Step 1 — Wrap Franka Robotics card to allow sub-link

The Franka card is currently a bare `<a>` — a second `<a>` cannot be nested inside it. Wrap it in a flex `<div>` and add the Franka Community sub-link below.

- [ ] **Edit: replace Franka `<a>` with wrapper div + sub-link**

  old_string (lines 944–947, exact):
  ```html
          <a href="https://franka.de" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-lg sponsor-logo-link" style="flex:1.1;">
            <img src="img/sponsors/franka_robotics.svg" alt="Franka Robotics logo" width="995" height="162" loading="lazy" decoding="async" style="max-height:100px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">Mobile FR3 Duo platform provider</span>
          </a>
  ```

  new_string:
  ```html
          <div style="display:flex;flex-direction:column;align-items:center;gap:.45rem;flex:1.1;">
            <a href="https://franka.de" target="_blank" rel="noopener"
               class="sponsor-logo sponsor-logo-lg sponsor-logo-link" style="width:100%;">
              <img src="img/sponsors/franka_robotics.svg" alt="Franka Robotics logo" width="995" height="162" loading="lazy" decoding="async" style="max-height:100px;width:auto;display:block;margin:0 auto .6rem;">
              <span class="sponsor-desc">Mobile FR3 Duo platform provider</span>
            </a>
            <p style="font-size:.78rem;color:var(--text-muted);text-align:center;margin:0;">
              Also join the
              <a href="https://www.franka-community.de/" target="_blank" rel="noopener"
                 style="color:var(--accent-dark);font-weight:600;">Franka Community</a> →
            </p>
          </div>
  ```

### Step 2 — Insert Infrastructure & Framework tier (before Computing tier)

- [ ] **Edit: replace Computing tier comment + opening with Infrastructure tier + Computing tier**

  old_string (lines 951–953):
  ```html
      <!-- Tier 2: Computing Resources -->
      <div class="sponsors-tier fade-in">
        <div class="tier-label">Computing Resources Sponsor</div>
  ```

  new_string:
  ```html
      <!-- Tier 2: Infrastructure & Framework -->
      <div class="sponsors-tier fade-in">
        <div class="tier-label">Infrastructure &amp; Framework Sponsors</div>
        <div class="sponsors-logos">
          <a href="https://vrb.ease-crc.org/" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-link">
            <img src="img/sponsors/vrb.svg" alt="Virtual Research Building logo" loading="lazy" decoding="async" style="max-height:55px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">Research infrastructure framework</span>
          </a>
          <a href="https://robotics-institute-germany.de/" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-link">
            <img src="img/sponsors/rig.png" alt="Robotics Institute Germany logo" loading="lazy" decoding="async" style="max-height:55px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">German national robotics research infrastructure</span>
          </a>
        </div>
      </div>

      <!-- Tier 3: Computing Resources -->
      <div class="sponsors-tier fade-in">
        <div class="tier-label">Computing Resources Sponsors</div>
  ```

### Step 3 — Add Alibaba Cloud to Computing tier

- [ ] **Edit: add Alibaba Cloud card after Google, before closing `</div></div>`**

  old_string (lines 955–960):
  ```html
          <a href="https://cloud.google.com" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-lg sponsor-logo-link">
            <img src="img/sponsors/google.svg" alt="Google Cloud logo" width="272" height="92" loading="lazy" decoding="async" style="max-height:70px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">Computing resources support</span>
          </a>
        </div>
      </div>
  ```

  new_string:
  ```html
          <a href="https://cloud.google.com" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-lg sponsor-logo-link">
            <img src="img/sponsors/google.svg" alt="Google Cloud logo" width="272" height="92" loading="lazy" decoding="async" style="max-height:70px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">Computing resources support</span>
          </a>
          <a href="https://www.alibabacloud.com/" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-lg sponsor-logo-link">
            <img src="img/sponsors/alibaba_cloud.svg" alt="Alibaba Cloud logo" loading="lazy" decoding="async" style="max-height:70px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">Cloud computing resources support</span>
          </a>
        </div>
      </div>
  ```

### Step 4 — Add HHRI to Community Sponsors tier

- [ ] **Edit: add HHRI card after AMD, before closing `</div></div>` of Community tier**

  old_string (lines 978–983):
  ```html
          <a href="https://www.amd.com" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-link">
            <img src="img/sponsors/amd.svg" alt="AMD logo" width="140" height="33" loading="lazy" decoding="async" style="max-height:55px;width:auto;display:block;margin:0 auto .6rem;filter:brightness(0);">
            <span class="sponsor-desc">Community Sponsor</span>
          </a>
        </div>
      </div>
  ```

  new_string:
  ```html
          <a href="https://www.amd.com" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-link">
            <img src="img/sponsors/amd.svg" alt="AMD logo" width="140" height="33" loading="lazy" decoding="async" style="max-height:55px;width:auto;display:block;margin:0 auto .6rem;filter:brightness(0);">
            <span class="sponsor-desc">Community Sponsor</span>
          </a>
          <a href="https://hhri.foxconn.com/" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-link">
            <img src="img/sponsors/hhri.webp" alt="Hon Hai Research Institute logo" loading="lazy" decoding="async" style="max-height:55px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">Community support · Foxconn research arm</span>
          </a>
        </div>
      </div>
  ```

---

## Task 2: Update competition.html Sponsors (sponsor cards only)

**File:** `competition.html`

Note: competition.html de-emphasizes the Community tier with `style="opacity:.92;"` on the tier div, `style="font-size:.78rem;"` on the tier label, and `max-height:42px` / `font-size:.78rem` on each community card. Match these exactly. The Infrastructure & Framework tier uses 55px (not de-emphasized, it's above Community).

### Step 5 — Wrap Franka card (same as index.html, lines 981–984)

- [ ] **Edit: wrap Franka card in flex div + add sub-link**

  old_string (lines 981–984, exact — identical to index.html version):
  ```html
          <a href="https://franka.de" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-lg sponsor-logo-link" style="flex:1.1;">
            <img src="img/sponsors/franka_robotics.svg" alt="Franka Robotics logo" width="995" height="162" loading="lazy" decoding="async" style="max-height:100px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">Mobile FR3 Duo platform provider</span>
          </a>
  ```

  new_string (identical to Task 1 Step 1):
  ```html
          <div style="display:flex;flex-direction:column;align-items:center;gap:.45rem;flex:1.1;">
            <a href="https://franka.de" target="_blank" rel="noopener"
               class="sponsor-logo sponsor-logo-lg sponsor-logo-link" style="width:100%;">
              <img src="img/sponsors/franka_robotics.svg" alt="Franka Robotics logo" width="995" height="162" loading="lazy" decoding="async" style="max-height:100px;width:auto;display:block;margin:0 auto .6rem;">
              <span class="sponsor-desc">Mobile FR3 Duo platform provider</span>
            </a>
            <p style="font-size:.78rem;color:var(--text-muted);text-align:center;margin:0;">
              Also join the
              <a href="https://www.franka-community.de/" target="_blank" rel="noopener"
                 style="color:var(--accent-dark);font-weight:600;">Franka Community</a> →
            </p>
          </div>
  ```

### Step 6 — Insert Infrastructure & Framework tier (before Computing tier)

- [ ] **Edit: replace Computing tier comment + opening with Infrastructure tier + Computing**

  old_string (lines 988–990):
  ```html
      <!-- Tier 2: Computing Resources (prominent) -->
      <div class="sponsors-tier fade-in">
        <div class="tier-label">Computing Resources Sponsor</div>
  ```

  new_string:
  ```html
      <!-- Tier 2: Infrastructure & Framework -->
      <div class="sponsors-tier fade-in">
        <div class="tier-label">Infrastructure &amp; Framework Sponsors</div>
        <div class="sponsors-logos">
          <a href="https://vrb.ease-crc.org/" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-link">
            <img src="img/sponsors/vrb.svg" alt="Virtual Research Building logo" loading="lazy" decoding="async" style="max-height:55px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">Research infrastructure framework</span>
          </a>
          <a href="https://robotics-institute-germany.de/" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-link">
            <img src="img/sponsors/rig.png" alt="Robotics Institute Germany logo" loading="lazy" decoding="async" style="max-height:55px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">German national robotics research infrastructure</span>
          </a>
        </div>
      </div>

      <!-- Tier 3: Computing Resources (prominent) -->
      <div class="sponsors-tier fade-in">
        <div class="tier-label">Computing Resources Sponsors</div>
  ```

### Step 7 — Add Alibaba Cloud to Computing tier

- [ ] **Edit: add Alibaba Cloud card after Google**

  old_string (lines 992–997):
  ```html
          <a href="https://cloud.google.com" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-lg sponsor-logo-link">
            <img src="img/sponsors/google.svg" alt="Google Cloud logo" width="272" height="92" loading="lazy" decoding="async" style="max-height:70px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">Computing resources support</span>
          </a>
        </div>
      </div>
  ```

  new_string:
  ```html
          <a href="https://cloud.google.com" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-lg sponsor-logo-link">
            <img src="img/sponsors/google.svg" alt="Google Cloud logo" width="272" height="92" loading="lazy" decoding="async" style="max-height:70px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">Computing resources support</span>
          </a>
          <a href="https://www.alibabacloud.com/" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-lg sponsor-logo-link">
            <img src="img/sponsors/alibaba_cloud.svg" alt="Alibaba Cloud logo" loading="lazy" decoding="async" style="max-height:70px;width:auto;display:block;margin:0 auto .6rem;">
            <span class="sponsor-desc">Cloud computing resources support</span>
          </a>
        </div>
      </div>
  ```

### Step 8 — Add HHRI to Community Sponsors tier

Note: competition.html Community tier uses `max-height:42px`, `margin:0 auto .5rem`, and `font-size:.78rem` on `.sponsor-desc`. Match these.

- [ ] **Edit: add HHRI after AMD card**

  old_string (lines 1015–1020):
  ```html
          <a href="https://www.amd.com" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-link">
            <img src="img/sponsors/amd.svg" alt="AMD logo" width="140" height="33" loading="lazy" decoding="async" style="max-height:42px;width:auto;display:block;margin:0 auto .5rem;filter:brightness(0);">
            <span class="sponsor-desc" style="font-size:.78rem;">Community Sponsor</span>
          </a>
        </div>
      </div>
  ```

  new_string:
  ```html
          <a href="https://www.amd.com" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-link">
            <img src="img/sponsors/amd.svg" alt="AMD logo" width="140" height="33" loading="lazy" decoding="async" style="max-height:42px;width:auto;display:block;margin:0 auto .5rem;filter:brightness(0);">
            <span class="sponsor-desc" style="font-size:.78rem;">Community Sponsor</span>
          </a>
          <a href="https://hhri.foxconn.com/" target="_blank" rel="noopener" class="sponsor-logo sponsor-logo-link">
            <img src="img/sponsors/hhri.webp" alt="Hon Hai Research Institute logo" loading="lazy" decoding="async" style="max-height:42px;width:auto;display:block;margin:0 auto .5rem;">
            <span class="sponsor-desc" style="font-size:.78rem;">Community support · Foxconn research arm</span>
          </a>
        </div>
      </div>
  ```

---

## Task 3: competition.html — CSS + Community Resources section

**File:** `competition.html`

### Step 9 — Add `.community-resource-card` CSS to inline style block

The inline `<style>` block ends at line 330. Add the new rule before `</style>`.

- [ ] **Edit: insert CSS rule before closing `</style>`**

  old_string (line 330):
  ```html
    </style>
  ```

  new_string:
  ```html
      .community-resource-card {
        display: flex;
        gap: 1.1rem;
        align-items: flex-start;
        background: var(--bg-light);
        border: 1px solid var(--border);
        border-radius: var(--radius);
        padding: 1.25rem 1.5rem;
        max-width: 640px;
        text-decoration: none;
        transition: border-color var(--transition), box-shadow var(--transition);
      }
      .community-resource-card:hover {
        border-color: var(--accent);
        box-shadow: 0 4px 20px rgba(0,212,255,.08);
      }
    </style>
  ```

### Step 10 — Add Community Resources section before `sponsor-cta`

- [ ] **Edit: insert Community Resources tier before `<p class="sponsor-cta">`**

  old_string (lines 1022–1023):
  ```html
      <p class="sponsor-cta fade-in">
        Interested in sponsoring?
  ```

  new_string:
  ```html
      <!-- Community Resources -->
      <div class="sponsors-tier fade-in">
        <div class="tier-label">Community Resources</div>
        <div style="display:flex;justify-content:center;">
          <a href="https://www.franka-community.de/" target="_blank" rel="noopener"
             class="community-resource-card">
            <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" fill="none"
                 viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.6"
                 aria-hidden="true"
                 style="flex-shrink:0;color:var(--accent-dark);margin-top:.1rem;">
              <path stroke-linecap="round" stroke-linejoin="round"
                    d="M17 20h5v-2a4 4 0 0 0-4-4h-1M9 20H4v-2a4 4 0 0 1 4-4h1m4-4a4 4 0 1 1-8 0 4 4 0 0 1 8 0Zm6 0a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"/>
            </svg>
            <div>
              <div style="font-weight:700;font-size:.95rem;color:var(--text-dark);margin-bottom:.25rem;">
                Franka Community
              </div>
              <p style="font-size:.82rem;color:var(--text-mid);line-height:1.5;margin:0 0 .45rem;">
                Online platform for Franka Robotics researchers and developers.
                Discuss FR3 Duo integration, share code, and connect with other competitors.
              </p>
              <span style="font-size:.82rem;font-weight:600;color:var(--accent-dark);">Join →</span>
            </div>
          </a>
        </div>
      </div>

      <p class="sponsor-cta fade-in">
        Interested in sponsoring?
  ```

---

## Verification

- [ ] **Step 11: Check tier count in index.html**

  Run: `grep -n "tier-label" index.html`

  Expected — 4 tier labels in order:
  ```
  Hardware &amp; Platform Sponsors
  Infrastructure &amp; Framework Sponsors
  Computing Resources Sponsors
  Community Sponsors
  ```

- [ ] **Step 12: Check tier count + Community Resources in competition.html**

  Run: `grep -n "tier-label\|community-resource-card" competition.html`

  Expected — 5 tier-label lines + 2 community-resource-card lines (CSS def + HTML usage):
  ```
  Hardware &amp; Platform Sponsors
  Infrastructure &amp; Framework Sponsors
  Computing Resources Sponsors
  Community Sponsors
  Community Resources
  .community-resource-card {   (CSS)
  class="community-resource-card"   (HTML)
  ```

- [ ] **Step 13: Verify all new links have target + rel**

  Run: `grep -n "alibabacloud\|vrb.ease\|robotics-institute-germany\|hhri.foxconn\|franka-community" index.html competition.html`

  Expected: every URL appears with `target="_blank" rel="noopener"` on the same `<a>` tag.

- [ ] **Step 14: Verify no nested `<a>` tags (invalid HTML)**

  Run: `grep -n "franka.de" index.html competition.html`

  Expected: the `franka.de` link is inside a `<div>` wrapper, not a bare `<a>`.
