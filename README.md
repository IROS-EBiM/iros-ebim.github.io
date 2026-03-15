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
│   └── main.js             # Scroll effects, nav, animations
├── img/
│   └── favicon.svg         # Site favicon
│   ├── organizers/         # Organizer headshots — to be added (jpg/png, ~300×300px)
│   ├── speakers/           # Speaker headshots — to be added
│   ├── tasks/              # Benchmark task images — to be added
│   └── sponsors/           # Sponsor logos — to be added (png with transparency preferred)
├── CNAME                   # GitHub Pages domain → iros-ebim.github.io
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
3. If using a custom domain, update the `CNAME` file with your domain.

---

## Content To-Do

### Done
- [x] Speakers section: 8 confirmed speakers added with names, affiliations, and talk titles
- [x] Organizers section: Organizing Committee, Advisory Board, and Competition Support Team populated
- [x] Schedule: confirmed 8-talk half-day program with updated timings (08:30–13:30)
- [x] Branding: unified under IROS-EBiM across all files (site name, URLs, email, repo)
- [x] CNAME set to `iros-ebim.github.io`

### Still needed
- [ ] Add real headshots to `/img/organizers/` and `/img/speakers/` (currently using initials avatars)
- [ ] Confirm and fill in NIST Representative name (currently listed as "NIST Representative")
- [ ] Fill in TBD talk titles for Speakers 2 (He Wang), 6 (Kroeger), 7 (Chuchu Fan), 8 (Chalvatzaki)
- [ ] Fill in submission deadlines in the Call for Participation section
- [ ] Add sponsor logos to `/img/sponsors/` and update the Sponsors section
- [ ] Add Open Graph cover image (`img/og-cover.png`) for social sharing previews

## Image Guidelines

| Folder | Format | Recommended size |
|---|---|---|
| organizers/ | JPG or PNG | 300 × 300 px |
| speakers/   | JPG or PNG | 300 × 300 px |
| tasks/      | JPG or PNG | 800 × 500 px |
| sponsors/   | PNG (transparent bg preferred) | 400 × 160 px |

---

## License

Website code MIT licensed. Workshop content © 2026 the respective authors.
