# IROS 2026 Workshop Website — IROS-EBiM

**Toward a Globally Coordinated Benchmark for Real-World Embodied Bimanual Manipulation**

IROS 2026 Half-Day Workshop · September 27 – October 1, 2026 · Pittsburgh, PA, USA

🌐 **Live site:** [iros-ebim.github.io](https://iros-ebim.github.io)
📧 **Contact:** [iros.ebim@gmail.com](mailto:iros.ebim@gmail.com)

---

## Project Structure

```
iros-ebim.github.io/
├── index.html              # Single-page site (all sections)
├── css/
│   └── style.css           # All styles
├── js/
│   └── main.js             # Scroll effects, nav, fade-in animations
├── img/
│   ├── favicon.svg         # Site favicon
│   ├── IROS_2026_logo.webp # IROS 2026 Pittsburgh logo (hero + footer)
│   ├── og-cover.png        # Open Graph / Twitter card image
│   ├── platform/           # Competition robot photos
│   │   ├── MFR3_Duo.png
│   │   └── MFR3_Duo_with_workbench.png
│   ├── organizers/         # Organizer headshots — to be added (jpg/png, ~300×300px)
│   └── sponsors/           # Sponsor logos
│       ├── agile_robots.svg        # Agile Robots (white; brightness(0) filter applied)
│       ├── agile_robots_dark.jpg   # Agile Robots dark variant
│       ├── franka_robotics.svg     # Franka Robotics
│       ├── franka_robotics_white.png
│       ├── tca.png                 # Taipei Computer Association
│       ├── mech_mind.png           # Mech-Mind (dark)
│       ├── mech_mind_white.png
│       ├── robotgym.webp           # RobotGym (dark)
│       ├── robotgym_white.webp
│       ├── amd.svg                 # AMD (white; brightness(0) filter applied)
│       └── google.svg              # Google (transparent bg; Computing Resources tier)
├── robots.txt              # Crawler directives + sitemap pointer
├── sitemap.xml             # Single-URL sitemap for Google Search Console
├── .nojekyll               # Disable Jekyll processing on GitHub Pages
└── README.md
```

## Setup

This is a plain HTML/CSS/JS static site — no build step required.

### Local preview

```bash
# Python 3
python -m http.server 8000
# then open http://localhost:8000
```

### GitHub Pages deployment

1. Push to the `main` branch of the `IROS-EBiM/iros-ebim.github.io` repository.
2. GitHub Pages will auto-deploy at `https://iros-ebim.github.io`.

---

## Sections

| Section | ID | Status |
|---|---|---|
| Hero | `#home` | ✅ Complete |
| Workshop Overview | `#overview` | ✅ Complete |
| Benchmark Framework | `#benchmark` | ✅ Complete |
| Competition Platform | `#platform` | ✅ Complete |
| Benchmark Tasks | `#tasks` | ✅ Complete (3 tasks) |
| Call for Participation | `#call-for-participation` | ✅ Complete |
| Schedule | `#schedule` | ✅ Complete |
| Organizing Committee | `#organizers` | ✅ Complete |
| Sponsors & Support | `#sponsors` | ✅ Complete |
| Contact / Key Dates | `#contact` | Dates TBC |

---

## Workshop Program (Final Proposal)

**Format:** Half-day morning session — exact date within September 27 – October 1, 2026

| Time | Session |
|------|---------|
| 08:30–08:40 | Opening Remarks |
| 08:40–09:00 | Invited Talk 1 — Prof. Abhinav Valada (Freiburg) |
| 09:00–09:20 | Invited Talk 2 — Prof. Roberto Martín-Martín (UT Austin) |
| 09:20–09:40 | Competition Highlights — Winner Teams (1st, 2nd, 3rd place) |
| 09:40–10:25 | Poster Session & Coffee Break |
| 10:25–10:45 | Invited Talk 3 — Prof. Georgia Chalvatzaki (TU Darmstadt) |
| 10:45–11:05 | Invited Talk 4 — Prof. Chuchu Fan (MIT) |
| 11:05–11:25 | Invited Talk 5 — Prof. He Wang (Peking University) |
| 11:25–11:55 | Panel Discussion — Host: Dr. Wenkai Chen |
| 11:55–12:30 | Best Poster Award & Competition Award |
| 12:30–13:30 | Sponsored Lunch & Networking |

---

## Benchmark Tasks (3 Core Tasks)

1. **Cable Routing & Plugging** — Contact-rich, sequential
2. **Deformable Material Handling (Thermal Pad Placement)** — Deformable, precision
3. **Caregiving & Feeding** — Human-centered, safety-critical

---

## Competition Platform

**Mobile FR3 Duo by Franka Robotics** — deployed at all four testbed sites:
Beijing · Hamburg · Munich · Pittsburgh

---

## Content To-Do

### Resolved
- [x] Schedule: final 5-talk + competition + panel program (08:30–13:30)
- [x] Benchmark tasks: narrowed to 3 core tasks (removed Table Cleaning, Clothes Folding, Cluttered Retrieval)
- [x] Organizers: Organizing Committee (12), Advisory Board (4), Competition Support Team (6) complete
- [x] Removed Chuchu Fan from organizers (invited speaker only)
- [x] Removed Dr. Torsten Kroeger and NIST ManipulationNet talk slots
- [x] He Wang talk title confirmed: "Learning Diverse Whole-Body Manipulation Skills for Humanoid Robots"
- [x] Chalvatzaki affiliation: TU Darmstadt / IEEE RAS TC on Mobile Manipulation
- [x] Robot Platform section added (Mobile FR3 Duo, specs grid, front + workbench photos)
- [x] Platform images updated to MFR3_Duo.png and MFR3_Duo_with_workbench.png (new brochure assets)
- [x] Platform description updated from new brochure; sensors corrected to 7× Cameras; spec label "Computing" → "User PC"
- [x] IROS 2026 logo added to hero and footer
- [x] Sponsors: Franka Robotics (Tier 1) and AMD (Community) added
- [x] Hamburg added as 4th testbed city throughout
- [x] Branding: unified under IROS-EBiM (site name, URLs, email, repo)
- [x] Sponsor logos: all 6 real logos live (Agile Robots, Franka, TCA, Mech-Mind, RobotGym, AMD)
- [x] Open Graph cover image (`img/og-cover.png`) added for social sharing previews
- [x] Stefan Schaal (Intrinsic) and Shaowei Cui confirmed as panelists (pending tags removed)
- [x] Chuchu Fan talk title confirmed: "Formal Visual Planning with Foundation Models"
- [x] Google added as Computing Resources Sponsor (Tier 2, between Hardware and Community)
- [x] SEO infrastructure added: `robots.txt`, `sitemap.xml`, `.nojekyll`, canonical link, JSON-LD Event schema
- [x] Google Search Console verified for `https://iros-ebim.github.io/` (HTML-tag method)
- [x] Organizers added: Shih-Chieh Chou (NYCU) → OC; Sven Parusel (Franka) → Advisory; Fatma Dhaoui (Franka) + Tianyi Wang (Agile) → Support Team
- [x] Removed redundant `CNAME` file (pointed at default github.io URL, not a real custom domain)

### Still Needed
- [ ] Add real headshots to `img/organizers/` (currently using initials avatars)
- [ ] Confirm exact workshop date within September 27 – October 1 window
- [ ] Fill in submission deadlines in the Call for Participation / Key Dates section

---

## Image Guidelines

| Folder | Format | Recommended size |
|---|---|---|
| organizers/ | JPG or PNG | 300 × 300 px |
| sponsors/ | SVG or PNG (transparent bg) | 400 × 160 px |
| platform/ | PNG | Original resolution |

---

## License

Website code MIT licensed. Workshop content © 2026 the respective authors.
