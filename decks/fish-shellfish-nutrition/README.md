# Lipid Nutrition & Feed Additives in Aquaculture

A 28-slide lecture deck covering **Topic 3 — Lipid Nutrition** and **Topic 8 — Feed Additives** from the *Fish and Shellfish Nutrition* syllabus, built for a 4th-year Fisheries presentation.

Every slide is native and editable in PowerPoint: real text boxes, real vector shapes, real pictures. Nothing is a screenshot of a slide.

---

## Download

**[`Lipid-Nutrition-and-Feed-Additives.pptx`](Lipid-Nutrition-and-Feed-Additives.pptx)** — 2.6 MB, 28 slides, 16:9 (13.333 × 7.5 in).

Speaker notes are embedded on all 28 slides. Open **View → Notes Page**, or the presenter view during the talk.

---

## What is in the deck

| # | Section | Content |
|---|---|---|
| 00 | Cover | Title block, course and candidate details |
| 01–02 | Introduction | Learning objectives; aquaculture production context (FAO SOFIA 2024) |
| 03 | **Topic 3 divider** | Lipid Nutrition |
| 04–06 | 3.1 Definition & functions | What a lipid is; what it does; dietary lipid levels by species |
| 07–09 | 3.2 Classification | Simple / compound / derived lipids; phospholipid bilayer; lipid sources and their fatty acid profiles |
| 10–13 | 3.3 Fatty acids | Anatomy and *n*-notation; SFA / MUFA / PUFA; omega-3 vs omega-6 pathways; EPA, DHA and ARA |
| 14–16 | 3.4–3.5 Roles, requirements, deficiency | Essential fatty acid functions; species-specific requirements table; deficiency signs and biomarkers |
| 17 | Transition | Bridges Topic 3 into Topic 8 |
| 18 | **Topic 8 divider** | Feed Additives |
| 19–20 | 8.1 Types | Four functional groups; six groups in detail with indicative inclusion levels |
| 21–22 | 8.2 Functions | Probiotic mechanisms (gut diagram); where each additive intervenes |
| 23–24 | 8.3 Nutraceuticals | Definition and limits; applications with an evidence-status column |
| 25 | 8.4 Application | Feed safety in Bangladesh — aflatoxin and heavy metals vs legal limits |
| 26 | Conclusion | Six takeaways |
| 27 | References | APA 7th edition, 17 sources with DOIs |

### Species covered

Nile tilapia (*Oreochromis niloticus*), Indian major carp (*Labeo rohita*, *Catla catla*), pangasius (*Pangasianodon hypophthalmus*), Asian seabass (*Lates calcarifer*), black tiger shrimp (*Penaeus monodon*), freshwater prawn (*Macrobrachium rosenbergii*).

### A note on the numbers

Requirements are given **per species and per life stage** — the deck deliberately refuses to quote a single universal lipid requirement, because one does not exist. Where a value is a range drawn from commercial practice rather than a published requirement, the slide says so. Every measured value carries a citation.

The Bangladesh feed-safety slide uses published survey data (Tabassum et al., 2025; Bhowmik et al., 2023) against the limits in the **Fish Feed and Animal Feed Act 2010**. The measured aflatoxin figure is roughly 100× the legal maximum; chromium more than 1,700×.

---

## Design

| | |
|---|---|
| **Palette** | Dark navy `#04121F` → deep ocean `#0E4D6B` → teal `#1898A0` → sand `#E7C87E` on white `#F7FAFB` |
| **Type** | Gelasio (Georgia-metric serif) for headings; Carlito (Calibri-metric) for body |
| **Grid** | 12.09 in content width, 0.62 in margins |
| **Rhythm** | Alternating dark and light slides; topic dividers use full-bleed imagery |

Both typefaces are metric-compatible with fonts already installed on Windows and macOS, so the deck reflows correctly if you edit it. The TTFs are bundled in `assets/fonts/` if you want to install them for pixel-exact editing.

---

## Repository layout

```
decks/fish-shellfish-nutrition/
├── Lipid-Nutrition-and-Feed-Additives.pptx   ← the deliverable
├── build/
│   ├── run.sh              build entry point
│   ├── build.js            slide collection, collision + fit checks
│   ├── prep-images.js      image grading pipeline
│   ├── lib/
│   │   ├── kit.js          primitives, text layout, collision detection
│   │   ├── system.js       masthead, footer, citation, section index
│   │   ├── diagrams.js     fatty acid chains, bilayer, arrows
│   │   ├── preview.js      SVG → PNG proof renderer
│   │   └── emit-pptx.js    pptxgenjs emitter
│   └── slides/             one file per slide group (00-cover.js … 11-close.js)
└── assets/
    ├── raw/                generated source plates
    ├── img/                graded derivatives
    └── fonts/              bundled TTFs
```

## Rebuilding

The deck is generated, not hand-drawn. To rebuild after an edit:

```bash
cd decks/fish-shellfish-nutrition
./build/run.sh --png          # render proof PNGs to build/out/proof/
./build/run.sh --pptx         # export the .pptx
./build/run.sh --only 15 --png   # rebuild a single slide
```

Requires Node 18+ with `pptxgenjs`, `sharp` and `fontkit` available. `build/run.sh` sets `FONTCONFIG_FILE` so the proof renderer resolves Carlito/Gelasio and the DejaVu glyph fallback for maths symbols.

Two automated gates run on every build:

- **collision check** — flags overlapping text boxes and off-canvas objects
- **fit check** — flags any text block that overflows its box

A clean build reports `0 collisions / 0 fit problems`. The current deck is clean.

---

## Author

**MD. Nahian Islam** — Student ID 22903022
4th Year, Department of Fisheries

*Fish and Shellfish Nutrition — Topics 3 and 8*
