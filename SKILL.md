---
name: swiss-slide
description: >
  Generates polished work-report slide decks in IBM Carbon + Swiss International Style
  (IKB accent, extreme type contrast, animated CSS grid, arrow-key navigation).

  Best for project updates, quarterly reviews, architecture reviews, incident
  postmortems, requirements reviews, OKR/goals, and decision memos — whenever work
  needs to be presented with authority and visual clarity.

  Trigger on: "make slides", "turn this into a deck", "create a presentation",
  "build a report page", "visualize my work", "make a report", "postmortem page".

  Output: single self-contained HTML file, opens in any browser.
---

# Swiss Slide Generator

## Design Language

**Style**: IBM Carbon Design System + Swiss International Style.
- Accent color: configurable (see Color Palettes below) — default IKB Klein Blue `#002FA7`
- Surfaces: warm off-white `#fafaf8` (light) · near-black `#0a0a0a` (dark)
- Type: Inter + JetBrains Mono + system CJK fallback
- Rules: right angles · hairline rules · extreme size contrast · generous whitespace · no shadows · no rounded corners

**Navigation**: horizontal full-viewport slides · square dot nav at bottom · animated CSS grid background · ← → / spacebar

---

## Color Palettes

Pick one based on context, or let the user choose. Only `--accent` and `--accent-bright` need to change.

| Name | --accent | --accent-bright | Character |
|------|----------|-----------------|-----------|
| IKB Klein Blue (default) | `#002FA7` | `#5B7BFF` | authoritative, technical |
| Vermillion | `#CC3300` | `#FF6644` | energetic, bold |
| Forest | `#1A6B3A` | `#3DAA6A` | calm, growth |
| Slate | `#2D3A4A` | `#5A7A99` | neutral, corporate |
| Violet | `#5B2D8E` | `#9B6DCC` | creative, premium |
| Amber | `#B35A00` | `#E87A22` | warm, approachable |

If user doesn't specify, ask: *"Any color preference? Or I'll use the default blue."*
Apply by replacing `--accent` and `--accent-bright` in the `:root` block of `assets/template.html`.

---

## Slide Structure (enforced)

**Always follow this order.** The first two slides are non-negotiable design decisions.

### Slide 1 — Cover (R01, always first)
Full-bleed accent slide. One headline, one summary line. Never put an agenda here.

### Slide 2 — Agenda / Overview (R02, always second)
**Must use the split layout**: left half = IKB grid background with the summary statement; right half = numbered project/section list. This is a core visual design choice — do not collapse it into a single column or replace with cards.

### Slides 3–N — Content
One slide per major topic. Choose from:
- **R03** — 4-column horizontal module list (grey bg) — best for "what was done in project X"
- **R04** — 4-card grid (light bg) — best for parallel deliverables or features
- **R05** — Before/after contrast (dark bg) — best for migrations, refactors, security upgrades
- **R08** — KPI/stats (grey bg) — best when there are meaningful numbers to show

### Second-to-last — Plans / Next Steps (R06)
3-column plan list. First column accent-bordered, others grey.

### Last — Closing (R07)
Accent slide, mirrors the cover visually.

**Minimum deck**: Cover → Agenda → 1–2 content slides → Closing (4 slides).
**Typical deck**: 6–8 slides.

---

## Workflow

### Step 1: Understand Content + Choose Color

Take whatever the user provides. Do not ask for metadata (names, team, dates) unless explicitly given.
If no color is specified, briefly offer the palette table and ask, or proceed with IKB blue.

### Step 2: Map Content to Slides

Follow the enforced structure above. Identify:
- The headline and one-line summary (→ Cover)
- The list of topics/projects (→ Agenda right column)
- The 1-3 sentence overview statement (→ Agenda left column big type)
- Per-topic details (→ R03/R04/R05/R08)
- Upcoming items if any (→ R06)

### Step 3: Build the HTML

1. Read `assets/template.html` (relative to this skill's directory)
2. Apply chosen `--accent` and `--accent-bright` in the `:root` block
3. Build slides using `references/slide-recipes.md`
4. Replace `<!-- SLIDES_HERE -->` with all `<section>` blocks
5. Update `<title>`
6. Output to user-specified path, or `./report_<YYYYMMDD>.html`

---

## Authoring Rules

### `chrome-min` convention
Left: `TOPIC · SUBTITLE` (all-caps) · Right: `NN / TOTAL`

### Visual hierarchy per slide
- `h2`: `font-size:min(5.2vw,9.2vh)` + `font-weight:200` — one headline per slide
- `.t-meta` kicker above the headline
- `card-fill` (neutral grey) for all cards; max **one** `card-accent` per group
- First column in any grid: `border-top:2px solid var(--accent)` + `color:var(--accent)`

### `data-animate` — must use existing values only
`hero` · `split-statement` · `timeline-h` · `grid-reveal` · `kpi-sweep` · `compare` · `pipeline`

---

## Reference Files

| File | Contents |
|------|----------|
| `assets/template.html` | Minified CSS/JS shell — insert slides at `<!-- SLIDES_HERE -->`, update `--accent`/`--accent-bright` in `:root` |
| `references/slide-recipes.md` | R01–R08 complete slide HTML |
| `references/design-tokens.md` | Token quick reference, typography scale, component guide |

