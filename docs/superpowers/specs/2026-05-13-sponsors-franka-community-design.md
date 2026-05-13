# Sponsors & Franka Community Update — Design Spec

**Date:** 2026-05-13  
**Status:** Approved — ready for implementation

---

## Goal

Add four new sponsors across new and existing tiers, and add two Franka Community placements — one inline sub-link under the Franka Robotics card and one resource callout card at the bottom of the competition.html sponsors section.

---

## Scope

Both `index.html` and `competition.html` sponsors sections receive all tier changes. The Franka Community resource card (Placement 2) is **competition.html only**.

---

## New Tier Structure (both pages)

| # | Tier Label | Members after change |
|---|---|---|
| 1 | Hardware & Platform Sponsors | Agile Robots, Franka Robotics |
| 2 | Infrastructure & Framework Sponsors *(new)* | VRB, RIG |
| 3 | Computing Resources Sponsors *(pluralized)* | Google, Alibaba Cloud *(new)* |
| 4 | Community Sponsors | TCA, RobotGym, Mech-Mind, AMD, HHRI *(new)* |

Tier 2 is inserted between Tier 1 and (what was) Tier 2. The existing Tier 2 and 3 shift down.

---

## New Sponsor Cards

All new sponsors use real logo image files (already in `img/sponsors/`).

### VRB — Virtual Research Building
- File: `img/sponsors/vrb.svg`
- URL: `https://vrb.ease-crc.org/`
- Description: `Research infrastructure framework`
- Tier: Infrastructure & Framework
- Size class: `.sponsor-logo .sponsor-logo-link` (no `-lg`; same as Community tier)
- max-height: `55px` (index.html), `42px` (competition.html)

### RIG — Robotics Institute Germany
- File: `img/sponsors/rig.png`
- URL: `https://robotics-institute-germany.de/`
- Description: `German national robotics research infrastructure`
- Tier: Infrastructure & Framework
- Size class: `.sponsor-logo .sponsor-logo-link`
- max-height: `55px` (index.html), `42px` (competition.html)

### Alibaba Cloud
- File: `img/sponsors/alibaba_cloud.svg`
- URL: `https://www.alibabacloud.com/`
- Description: `Cloud computing resources support`
- Tier: Computing Resources
- Size class: `.sponsor-logo .sponsor-logo-lg .sponsor-logo-link` (same prominence as Google)
- max-height: `70px` (both pages)

### HHRI — Hon Hai Research Institute
- File: `img/sponsors/hhri.webp`
- URL: `https://hhri.foxconn.com/`
- Description: `Community support · Foxconn research arm`
- Tier: Community Sponsors
- Size class: `.sponsor-logo .sponsor-logo-link`
- max-height: `55px` (index.html), `42px` (competition.html)

---

## Franka Community — Placement 1 (both pages)

The Franka Robotics card is currently a full `<a>` element. Nesting a second `<a>` inside it is invalid HTML. Solution: wrap the Franka card and the community link together in a `<div>` flex column.

**Replace** the bare `<a href="https://franka.de"...>` with:

```html
<div style="display:flex;flex-direction:column;align-items:center;gap:.45rem;flex:1.1;">
  <a href="https://franka.de" target="_blank" rel="noopener"
     class="sponsor-logo sponsor-logo-lg sponsor-logo-link"
     style="width:100%;">
    <img src="img/sponsors/franka_robotics.svg" alt="Franka Robotics logo"
         width="995" height="162" loading="lazy" decoding="async"
         style="max-height:100px;width:auto;display:block;margin:0 auto .6rem;">
    <span class="sponsor-desc">Mobile FR3 Duo platform provider</span>
  </a>
  <p style="font-size:.78rem;color:var(--text-muted);text-align:center;margin:0;">
    Also join the
    <a href="https://www.franka-community.de/" target="_blank" rel="noopener"
       style="color:var(--accent-dark);font-weight:600;">Franka Community</a> →
  </p>
</div>
```

---

## Franka Community — Placement 2 (competition.html only)

Add a "Community Resources" sub-tier at the bottom of the Sponsors section, **before** the `<p class="sponsor-cta">` closing element.

The tier uses the standard `.sponsors-tier` + `.tier-label` pattern but contains a single resource card instead of sponsor logos.

```html
<!-- Community Resources -->
<div class="sponsors-tier fade-in">
  <div class="tier-label">Community Resources</div>
  <div style="display:flex;justify-content:center;">
    <a href="https://www.franka-community.de/" target="_blank" rel="noopener"
       class="community-resource-card">
      <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28"
           fill="none" viewBox="0 0 24 24" stroke="currentColor"
           stroke-width="1.6" aria-hidden="true"
           style="flex-shrink:0;color:var(--accent-dark);margin-top:.1rem;">
        <path stroke-linecap="round" stroke-linejoin="round"
              d="M17 20h5v-2a4 4 0 0 0-4-4h-1M9 20H4v-2a4 4 0 0 1 4-4h1
                 m4-4a4 4 0 1 1-8 0 4 4 0 0 1 8 0Zm6 0a3 3 0 1 1-6 0
                 3 3 0 0 1 6 0Z"/>
      </svg>
      <div>
        <div style="font-weight:700;font-size:.95rem;color:var(--text-dark);
                    margin-bottom:.25rem;">Franka Community</div>
        <p style="font-size:.82rem;color:var(--text-mid);
                  line-height:1.5;margin:0 0 .45rem;">
          Online platform for Franka Robotics researchers and developers.
          Discuss FR3 Duo integration, share code, and connect with other competitors.
        </p>
        <span style="font-size:.82rem;font-weight:600;color:var(--accent-dark);">
          Join →
        </span>
      </div>
    </a>
  </div>
</div>
```

CSS for `.community-resource-card` — add to competition.html inline `<style>`:

```css
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
```

---

## Heading Change

Both pages — rename the Computing tier label:  
`Computing Resources Sponsor` → `Computing Resources Sponsors`

---

## Verification Checklist

1. Five logical groupings appear in the sponsors section: Hardware & Platform, Infrastructure & Framework, Computing Resources, Community Sponsors, Community Resources (the last one only in competition.html)
2. All new sponsor `<a>` tags have `target="_blank" rel="noopener"`
3. Tier labels use consistent capitalization and the `::after` rule draws the horizontal line automatically (no inline changes needed — the `.tier-label::after` CSS rule handles it)
4. Franka Robotics card is wrapped in a `<div>` and the community sub-link appears beneath it
5. `community-resource-card` CSS rule is present in competition.html inline `<style>` block
6. Alibaba Cloud uses `.sponsor-logo-lg` (same size class as Google)
7. VRB, RIG, HHRI use plain `.sponsor-logo` (Community-tier size)
