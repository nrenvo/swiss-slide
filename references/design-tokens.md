# Design Tokens & Component Quick Reference

## Color Tokens

| Token | Value | Usage |
|-------|-------|-------|
| `--paper` | #fafaf8 | main background (light) |
| `--ink` | #0a0a0a | primary text color |
| `--grey-1` | #f0f0ee | light grey surface (grey slide) |
| `--accent` | #002FA7 | IKB Klein Blue (swappable theme color) |
| `--accent-on` | #ffffff | text on accent background |
| `--accent-bright` | #5B7BFF | lightened IKB for dark backgrounds |
| `--text-primary` | #0a0a0a | primary text |
| `--text-secondary` | #525252 | secondary text |
| `--text-helper` | #737373 | helper/label text |
| `--border-subtle` | #e0e0e0 | hairline dividers |
| `--border-strong` | #a3a3a3 | strong dividers |

## Slide Variants

| Class | Background | Text | Use for |
|-------|-----------|------|---------|
| `slide` | `--paper` | `--ink` | default light slide |
| `slide grey` | `--grey-1` | `--ink` | neutral content page |
| `slide dark` | `--ink` | `--paper` | high-contrast emphasis |
| `slide accent` | `--accent` | `--accent-on` | IKB cover / closing / highlight |
| `slide split` | — | — | left/right split layout (contains split-half) |
| `slide light` | `--paper` | `--ink` | same as default, semantically explicit |

## Typography Scale

| Class | Size | Weight | Use for |
|-------|------|--------|---------|
| `.h-hero` | 11vw | 200 | cover super-headline |
| `.h-xl` | 6vw | 200 | section main title |
| `.h-md` | 2.6vw | 300 | content page title |
| `.h-sub` | 2.2vw | 400 | subtitle |
| `.lead` | 1.55vw | 400 | intro/summary text |
| `.body` | max(18px,1.08vw) | 400 | body text |
| `.body-sm` | max(16px,.92vw) | 400 | small body text |
| `.meta` | max(14px,.82vw) | 400 | monospaced all-caps label |
| `.kicker` | 14px | — | section kicker (includes left rule) |
| `.t-meta` | — | — | chrome bar monospaced text |

## Core Components

### canvas-card (content container for every slide)
```html
<section class="slide [variant]" data-animate="[recipe]">
  <div class="canvas-card">
    <!-- accent slides get the CSS grid automatically -->
    <div class="chrome-min">
      <div class="l">LEFT LABEL · SUBTITLE</div>
      <div class="r">NN / TOTAL</div>
    </div>
    <!-- main content here -->
  </div>
</section>
```

### card-fill / card-accent / card-ink
```html
<div class="card-fill" style="padding:2.4vh 1.6vw;display:flex;flex-direction:column;gap:1.4vh">
  <div style="font-family:var(--mono);font-size:min(3.6vw,6.4vh);font-weight:200;line-height:.9;color:var(--text-helper)">01</div>
  <div style="font-family:var(--sans),var(--sans-zh);font-size:max(16px,1.1vw);font-weight:500;color:var(--text-primary)">Card title</div>
  <div style="font-family:var(--sans),var(--sans-zh);font-size:max(14px,.82vw);color:var(--text-secondary);font-weight:400;line-height:1.5">Description text.</div>
</div>
```
`card-fill` = neutral grey · `card-accent` = IKB blue (use max 1 per group) · `card-ink` = near-black inverse

### stat-card
```html
<div class="stat-card accent-top">
  <div class="stat-label">LABEL</div>
  <div class="stat-nb">42<span class="stat-unit">items</span></div>
  <div class="stat-note">Supporting note</div>
</div>
```

### step (node inside a pipeline)
```html
<div class="step accent-top">
  <div class="step-nb">01</div>
  <div class="step-title">Step title</div>
  <div class="step-desc">Description</div>
</div>
```

## Layout Grid

| Class | Description |
|-------|-------------|
| `grid-12` + `span-N` | 12-column responsive grid, N=2/3/4/5/6/7/8/9/12 |
| `grid-3` | 3 equal columns |
| `grid-4` | 2×2 grid (4 cards) |
| `grid-6` | 3×2 grid (6 cards) |
| `grid-2-6-6` | 50/50 split |
| `grid-2-8-4` | 8:4 split |
| `grid-2-4-8` | 4:8 split |
| `col` | flex column + gap |
| `row` | flex row + gap |
| `fill` | flex:1 |

## data-animate Recipes (must match an existing recipe)

| Recipe | Best for |
|--------|---------|
| `hero` | cover/closing accent slide |
| `split-statement` | split two-column slide |
| `timeline-h` | horizontal timeline / module list |
| `grid-reveal` | card grid reveal |
| `kpi-sweep` | data/metrics highlight slide |
| `compare` | before/after contrast |
| `pipeline` | slides using `.pipeline` class |

## Decorators

```html
<!-- hairline rule -->
<div class="rule"></div>
<div class="rule accent"></div>

<!-- dot matrix background -->
<div class="dots" style="position:absolute;inset:0;pointer-events:none"></div>

<!-- kicker label (includes left rule) -->
<div class="kicker accent">SECTION LABEL</div>

<!-- bordered tag -->
<span class="tag">TEXT</span>
<span class="tag accent">HIGHLIGHTED</span>

<!-- inline mark highlight -->
<span class="mark">keyword</span>

<!-- accent slides get the animated grid automatically; no canvas needed -->
```

