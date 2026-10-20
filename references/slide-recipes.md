# Slide Recipes

Each recipe is a complete `<section class="slide ...">` block. Paste into `<!-- SLIDES_HERE -->`,
replace all placeholder text, and update `chrome-min` page numbers. Never invent new `data-animate` values.

---

## R01 · Cover (IKB Full-Bleed)
**Use for**: Opening slide. `accent` variant with animated grid background.

```html
<section class="slide accent" data-animate="hero">
  <div class="canvas-card">
    <div class="chrome-min" style="position:relative;z-index:1">
      <div class="l">REPORT TITLE · PERIOD</div>
      <div class="r">TEAM · DATE · 01 / N</div>
    </div>
    <div style="flex:1;padding:0;display:grid;grid-template-rows:auto 1fr auto;gap:2.6vh;position:relative;z-index:1">
      <div class="t-meta" style="color:rgba(255,255,255,.78);letter-spacing:.22em">BIWEEKLY REVIEW · YYYY.MM.DD — MM.DD</div>
      <h1 style="align-self:center;font-family:var(--sans),var(--sans-zh);font-weight:200;font-size:min(6.4vw,11.2vh);line-height:.94;letter-spacing:-.025em;color:#fff">Main Headline</h1>
      <div style="display:grid;grid-template-rows:auto auto;gap:1.6vh;border-top:1px solid rgba(255,255,255,.22);padding-top:2vh">
        <div class="lead" style="max-width:52ch;color:rgba(255,255,255,.86)">One-line summary: N projects · Y commits · key highlights</div>
        <div style="display:flex;justify-content:space-between;align-items:end">
          <div class="t-meta" style="color:rgba(255,255,255,.6)">NAME · TEAM</div>
          <div class="t-meta" style="color:rgba(255,255,255,.6)">→ swipe / arrow keys</div>
        </div>
      </div>
    </div>
  </div>
</section>
```

---

## R02 · Agenda / Overview (Split IKB + List)
**Use for**: Table of contents. Left: IKB + grid. Right: project/agenda list.

```html
<section class="slide split" data-animate="split-statement">
  <div class="canvas-card">
    <div class="split-half">
      <div class="half b-accent" style="padding:5.6vh 3.6vw 4.4vh;justify-content:space-between;position:relative;overflow:hidden">
        <div class="chrome-min" style="margin-bottom:0;position:relative;z-index:1">
          <div class="l">02 / N</div>
          <div class="r">OVERVIEW</div>
        </div>
        <div style="display:flex;flex-direction:column;gap:2vh;position:relative;z-index:1">
          <div class="t-meta" style="color:rgba(255,255,255,.78);letter-spacing:.22em;margin-bottom:1.6vh">KEY OVERVIEW</div>
          <h2 style="font-family:var(--sans),var(--sans-zh);font-size:min(5.8vw,10.2vh);line-height:.94;letter-spacing:-.025em;font-weight:200;color:#fff">Summary<br><span style="font-style:italic;font-weight:300">Word</span></h2>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,1vw);line-height:1.6;color:rgba(255,255,255,.82);font-weight:400;max-width:36ch;margin-top:1.4vh">Two or three sentences summarizing this period's outcomes.</div>
        </div>
        <div style="display:flex;justify-content:space-between;align-items:end;border-top:1px solid rgba(255,255,255,.22);padding-top:2vh;position:relative;z-index:1">
          <div class="t-meta" style="color:rgba(255,255,255,.62)">NAME · TEAM</div>
          <div class="t-meta" style="color:rgba(255,255,255,.62)">DATE</div>
        </div>
      </div>
      <div class="half" style="padding:5.6vh 3.6vw 4.4vh;justify-content:space-between">
        <div class="chrome-min">
          <div class="l">AGENDA</div>
          <div class="r">N PROJECTS</div>
        </div>
        <div style="display:flex;flex-direction:column;gap:0">
          <!-- Repeat per agenda item; last item gets border-bottom:2px solid var(--accent) -->
          <div style="display:grid;grid-template-columns:auto 1fr;gap:1.6vw;align-items:start;padding:2.4vh 0;border-top:1px solid var(--border-subtle)">
            <div style="font-family:var(--sans);font-weight:200;font-size:min(3.2vw,5.6vh);line-height:.9;color:var(--accent)">01</div>
            <div>
              <h3 style="font-family:var(--sans),var(--sans-zh);font-weight:400;font-size:max(16px,1.4vw);line-height:1.2;color:var(--text-primary);margin-bottom:.8vh">Project Name</h3>
              <p style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.82vw);line-height:1.7;color:var(--text-secondary);font-weight:400">1. Sub-item<br>2. Sub-item<br>3. Sub-item</p>
            </div>
          </div>
        </div>
        <div class="t-meta" style="color:var(--text-helper);text-align:right">→ OVERVIEW · TABLE OF CONTENTS</div>
      </div>
    </div>
  </div>
</section>
```

---

## R03 · Project Overview (Grey · Timeline)
**Use for**: Single-project summary. Grey background, horizontal 4-column module list.

```html
<section class="slide grey" data-animate="timeline-h">
  <div class="canvas-card">
    <div class="chrome-min">
      <div class="l">PROJECT · MODULE</div>
      <div class="r">NN / N</div>
    </div>
    <div style="flex:1;padding:0;display:grid;grid-template-rows:auto 1fr;gap:4vh">
      <div style="display:flex;flex-direction:column;gap:1.4vh">
        <div class="t-meta">PROJECT · N COMMITS / N FILES</div>
        <h2 style="font-family:var(--sans),var(--sans-zh);font-weight:200;font-size:min(5.2vw,9.2vh);line-height:.94;letter-spacing:-.02em">Core Theme Title</h2>
      </div>
      <div style="display:grid;grid-template-columns:repeat(4,1fr);gap:1.6vw;align-items:start;padding-top:2vh">
        <!-- First column: accent top border -->
        <div style="display:flex;flex-direction:column;gap:1.4vh;border-top:2px solid var(--accent);padding-top:1.6vh">
          <div style="font-family:var(--mono);font-size:max(14px,.9vw);color:var(--accent);font-weight:600">MODULE A</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(16px,1vw);font-weight:500;color:var(--text-primary)">Module Title</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.82vw);color:var(--text-secondary);font-weight:400;line-height:1.5">Point 1<br>Point 2</div>
        </div>
        <!-- Remaining columns: grey top border -->
        <div style="display:flex;flex-direction:column;gap:1.4vh;border-top:2px solid var(--border-strong);padding-top:1.6vh">
          <div style="font-family:var(--mono);font-size:max(14px,.9vw);color:var(--text-helper);font-weight:600">MODULE B</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(16px,1vw);font-weight:500;color:var(--text-primary)">Module Title</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.82vw);color:var(--text-secondary);font-weight:400;line-height:1.5">Point 1<br>Point 2</div>
        </div>
        <div style="display:flex;flex-direction:column;gap:1.4vh;border-top:2px solid var(--border-strong);padding-top:1.6vh">
          <div style="font-family:var(--mono);font-size:max(14px,.9vw);color:var(--text-helper);font-weight:600">MODULE C</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(16px,1vw);font-weight:500;color:var(--text-primary)">Module Title</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.82vw);color:var(--text-secondary);font-weight:400;line-height:1.5">Point 1<br>Point 2</div>
        </div>
        <div style="display:flex;flex-direction:column;gap:1.4vh;border-top:2px solid var(--border-strong);padding-top:1.6vh">
          <div style="font-family:var(--mono);font-size:max(14px,.9vw);color:var(--text-helper);font-weight:600">MODULE D</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(16px,1vw);font-weight:500;color:var(--text-primary)">Module Title</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.82vw);color:var(--text-secondary);font-weight:400;line-height:1.5">Point 1<br>Point 2</div>
        </div>
      </div>
    </div>
  </div>
</section>
```

---

## R04 · Four Cards Grid (Light · grid-reveal)
**Use for**: 4 parallel capabilities or deliverables. Use `card-accent` on the most important card.

```html
<section class="slide light" data-animate="grid-reveal">
  <div class="canvas-card">
    <div class="chrome-min">
      <div class="l">TOPIC · SUBTITLE</div>
      <div class="r">NN / N</div>
    </div>
    <div style="flex:1;padding:0;display:grid;grid-template-rows:auto 1fr;gap:4vh">
      <div style="display:flex;flex-direction:column;gap:1.4vh">
        <div class="t-meta">CONTEXT · DATA SUMMARY</div>
        <h2 style="font-family:var(--sans),var(--sans-zh);font-weight:200;font-size:min(5.2vw,9.2vh);line-height:.94;letter-spacing:-.02em">Page Headline</h2>
      </div>
      <div style="display:grid;grid-template-columns:repeat(4,1fr);gap:1.6vw;align-items:start">
        <div class="card-fill" style="padding:2.4vh 1.6vw;display:flex;flex-direction:column;gap:1.4vh">
          <div style="font-family:var(--mono);font-size:min(3.6vw,6.4vh);font-weight:200;line-height:.9;color:var(--text-helper)">01</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(16px,1.1vw);font-weight:500;color:var(--text-primary)">Card Title</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.82vw);color:var(--text-secondary);font-weight:400;line-height:1.5">One or two sentences.</div>
        </div>
        <div class="card-fill" style="padding:2.4vh 1.6vw;display:flex;flex-direction:column;gap:1.4vh">
          <div style="font-family:var(--mono);font-size:min(3.6vw,6.4vh);font-weight:200;line-height:.9;color:var(--text-helper)">02</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(16px,1.1vw);font-weight:500;color:var(--text-primary)">Card Title</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.82vw);color:var(--text-secondary);font-weight:400;line-height:1.5">One or two sentences.</div>
        </div>
        <div class="card-fill" style="padding:2.4vh 1.6vw;display:flex;flex-direction:column;gap:1.4vh">
          <div style="font-family:var(--mono);font-size:min(3.6vw,6.4vh);font-weight:200;line-height:.9;color:var(--text-helper)">03</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(16px,1.1vw);font-weight:500;color:var(--text-primary)">Card Title</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.82vw);color:var(--text-secondary);font-weight:400;line-height:1.5">One or two sentences.</div>
        </div>
        <!-- card-accent: use for the most important item only -->
        <div class="card-accent" style="padding:2.4vh 1.6vw;display:flex;flex-direction:column;gap:1.4vh">
          <div style="font-family:var(--mono);font-size:min(3.6vw,6.4vh);font-weight:200;line-height:.9;color:var(--accent-on)">04</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(16px,1.1vw);font-weight:500;color:var(--accent-on)">Key Card</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.82vw);color:rgba(255,255,255,.82);font-weight:400;line-height:1.5">One or two sentences.</div>
        </div>
      </div>
    </div>
  </div>
</section>
```

---

## R05 · Before / After Contrast (Dark · compare)
**Use for**: Architectural refactors, security upgrades, UX improvements.

```html
<section class="slide dark" data-animate="compare">
  <div class="canvas-card">
    <div class="chrome-min">
      <div class="l">TOPIC · CONTRAST</div>
      <div class="r">NN / N</div>
    </div>
    <div style="flex:1;padding:0;display:grid;grid-template-rows:auto 1fr;gap:4vh">
      <div style="display:flex;flex-direction:column;gap:1.4vh">
        <div class="t-meta" style="color:var(--text-placeholder)">UPGRADE / MIGRATION</div>
        <h2 style="font-family:var(--sans),var(--sans-zh);font-weight:200;font-size:min(5.2vw,9.2vh);line-height:.94;letter-spacing:-.02em">Improvement Title</h2>
      </div>
      <div style="display:grid;grid-template-columns:1fr 1px 1fr;gap:2.4vw;align-items:start">
        <div style="display:flex;flex-direction:column;gap:2vh">
          <div style="font-family:var(--mono);font-size:max(14px,.9vw);color:var(--text-placeholder);font-weight:600;letter-spacing:.14em">BEFORE</div>
          <div style="border-top:1px solid var(--border-strong);padding-top:2vh;display:flex;flex-direction:column;gap:1.6vh">
            <div style="font-family:var(--sans),var(--sans-zh);font-size:max(18px,1.2vw);font-weight:400;color:var(--paper);line-height:1.5">Previous approach description</div>
            <div style="font-family:var(--sans),var(--sans-zh);font-size:max(16px,.94vw);color:var(--text-placeholder);font-weight:400;line-height:1.6">Issue 1<br>Issue 2<br>Issue 3</div>
          </div>
        </div>
        <div style="width:1px;height:100%;background:var(--border-strong)"></div>
        <div style="display:flex;flex-direction:column;gap:2vh">
          <div style="font-family:var(--mono);font-size:max(14px,.9vw);color:var(--accent-bright);font-weight:600;letter-spacing:.14em">AFTER</div>
          <div style="border-top:2px solid var(--accent-bright);padding-top:2vh;display:flex;flex-direction:column;gap:1.6vh">
            <div style="font-family:var(--sans),var(--sans-zh);font-size:max(18px,1.2vw);font-weight:400;color:var(--paper);line-height:1.5">New approach description</div>
            <div style="font-family:var(--sans),var(--sans-zh);font-size:max(16px,.94vw);color:rgba(250,250,248,.7);font-weight:400;line-height:1.6">Improvement 1<br>Improvement 2<br>Improvement 3</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
```

---

## R06 · Plans / Next Steps (Light · grid-reveal)
**Use for**: Upcoming work, roadmap items. 2–3 columns. First item uses accent border.

```html
<section class="slide light" data-animate="grid-reveal">
  <div class="canvas-card">
    <div class="chrome-min">
      <div class="l">NEXT STEPS · ROADMAP</div>
      <div class="r">NN / N</div>
    </div>
    <div style="flex:1;padding:0;display:grid;grid-template-rows:auto 1fr;gap:4vh">
      <div style="display:flex;flex-direction:column;gap:1.4vh">
        <div class="t-meta">UPCOMING · N INITIATIVES</div>
        <h2 style="font-family:var(--sans),var(--sans-zh);font-weight:200;font-size:min(5.2vw,9.2vh);line-height:.94;letter-spacing:-.02em">Next Steps</h2>
      </div>
      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:2vw;align-items:start">
        <!-- First plan: accent border -->
        <div style="display:flex;flex-direction:column;gap:1.6vh;border-top:2px solid var(--accent);padding-top:1.8vh">
          <div style="font-family:var(--mono);font-size:min(3.2vw,5.6vh);font-weight:200;line-height:.9;color:var(--accent)">01</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(17px,1.15vw);font-weight:500;color:var(--text-primary);line-height:1.3">Plan Title</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.88vw);color:var(--text-secondary);line-height:1.6">One or two sentences describing the goal and value.</div>
          <div style="display:flex;gap:.6vw;flex-wrap:wrap;margin-top:.4vh">
            <span class="tag">tag1</span>
            <span class="tag">tag2</span>
          </div>
        </div>
        <!-- Remaining plans: grey border -->
        <div style="display:flex;flex-direction:column;gap:1.6vh;border-top:1px solid var(--border-strong);padding-top:1.8vh">
          <div style="font-family:var(--mono);font-size:min(3.2vw,5.6vh);font-weight:200;line-height:.9;color:var(--text-helper)">02</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(17px,1.15vw);font-weight:500;color:var(--text-primary);line-height:1.3">Plan Title</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.88vw);color:var(--text-secondary);line-height:1.6">Description.</div>
          <div style="display:flex;gap:.6vw;flex-wrap:wrap;margin-top:.4vh">
            <span class="tag">tag</span>
          </div>
        </div>
        <div style="display:flex;flex-direction:column;gap:1.6vh;border-top:1px solid var(--border-strong);padding-top:1.8vh">
          <div style="font-family:var(--mono);font-size:min(3.2vw,5.6vh);font-weight:200;line-height:.9;color:var(--text-helper)">03</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(17px,1.15vw);font-weight:500;color:var(--text-primary);line-height:1.3">Plan Title</div>
          <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.88vw);color:var(--text-secondary);line-height:1.6">Description.</div>
          <div style="display:flex;gap:.6vw;flex-wrap:wrap;margin-top:.4vh">
            <span class="tag">tag</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
```

---

## R07 · Closing (Accent · hero)
**Use for**: Final slide.

```html
<section class="slide accent" data-animate="hero">
  <div class="canvas-card">
    <div class="chrome-min" style="position:relative;z-index:1">
      <div class="l">N / N · END</div>
      <div class="r">TEAM · DATE</div>
    </div>
    <div style="flex:1;display:flex;flex-direction:column;justify-content:center;gap:2.4vh;position:relative;z-index:1">
      <div class="t-meta" style="color:rgba(255,255,255,.7);letter-spacing:.22em">THANK YOU</div>
      <h1 style="font-family:var(--sans),var(--sans-zh);font-weight:200;font-size:min(6.4vw,11.2vh);line-height:.94;letter-spacing:-.025em;color:#fff">Closing Word</h1>
      <div style="border-top:1px solid rgba(255,255,255,.22);padding-top:2vh;margin-top:1.6vh">
        <div class="lead" style="color:rgba(255,255,255,.78)">One-sentence closing note.</div>
      </div>
    </div>
    <div style="display:flex;justify-content:space-between;align-items:end;position:relative;z-index:1">
      <div class="t-meta" style="color:rgba(255,255,255,.55)">NAME · TEAM</div>
      <div class="t-meta" style="color:rgba(255,255,255,.55)">DATE</div>
    </div>
  </div>
</section>
```

---

## R08 · KPI / Stats Page (Grey · kpi-sweep)
**Use for**: Metrics highlight slide with large numbers.

```html
<section class="slide grey" data-animate="kpi-sweep">
  <div class="canvas-card">
    <div class="chrome-min">
      <div class="l">STATS · METRICS</div>
      <div class="r">NN / N</div>
    </div>
    <div style="flex:1;padding:0;display:grid;grid-template-rows:auto 1fr;gap:4vh">
      <div style="display:flex;flex-direction:column;gap:1.4vh">
        <div class="t-meta">PERIOD · SCOPE</div>
        <h2 style="font-family:var(--sans),var(--sans-zh);font-weight:200;font-size:min(5.2vw,9.2vh);line-height:.94;letter-spacing:-.02em">By the Numbers</h2>
      </div>
      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:3vw;align-items:start">
        <div class="stat-card accent-top">
          <div class="stat-label">METRIC A</div>
          <div class="stat-nb">42<span class="stat-unit"> items</span></div>
          <div class="stat-note">Supporting note</div>
        </div>
        <div class="stat-card thin">
          <div class="stat-label">METRIC B</div>
          <div class="stat-nb">1.2K<span class="stat-unit"> lines</span></div>
          <div class="stat-note">Supporting note</div>
        </div>
        <div class="stat-card thin">
          <div class="stat-label">METRIC C</div>
          <div class="stat-nb">99<span class="stat-unit">%</span></div>
          <div class="stat-note">Supporting note</div>
        </div>
      </div>
    </div>
  </div>
</section>
```

---

## Authoring Notes

1. **Page numbers**: `chrome-min` right shows `NN / TOTAL`; TOTAL must match actual slide count
2. **Accent column**: In a 4-col grid, first column uses `border-top:2px solid var(--accent)` + `color:var(--accent)`; the rest use `var(--border-strong)` + `var(--text-helper)`
3. **card-accent vs card-fill**: Maximum one `card-accent` per group; all others use `card-fill`
4. **Content depth**: Max 5 points per slide; body text max 2 lines
5. **Typography**: `chrome-min` and `.t-meta` are always all-caps English; card titles and body are in the language of the content

