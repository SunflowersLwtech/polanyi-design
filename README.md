<div align="center">

# polanyi-design

> *"We can know more than we can tell."*
> — Michael Polanyi, *The Tacit Dimension* (1966)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/code)

**A frontend design cognitive engine.** Not a role-play — an operational thinking system
that surfaces the visual judgment senior designers *know* but rarely articulate.

</div>

---

## What This Does

When activated, this skill changes *how* Claude reasons about frontend design:

- **Skips tutorials** — doesn't restate what Tailwind docs say
- **Extracts implicit** — surfaces the unspoken "why" behind expert design decisions
- **Pushes toward tacit** — articulates "this feels off" as structural diagnosis + concrete fix
- **Gestalt-first** — diagnoses the whole before examining parts
- **Convention judgment** — knows when to follow rules and when to break them

## Install

```bash
npx skills add sunfl/polanyi-design
```

## Example

**Q:** My landing page looks like a template. It uses Inter, Tailwind blue-500, default shadows, Unsplash photos.

**Without skill:** Lists five fixes — swap font, shift color, add illustration, break grid, micro-interactions.

**With skill:** "Every design decision is the statistical mode of its category — the gestalt
voice test fails because there is no single adjective that describes your page. The fix is
subtraction and specificity, not addition. Kill `shadow-md` entirely; replace with `1px
border-slate-200`. Set h1 to `48px/600/-0.025em` — the negative tracking alone separates
you from the default stack. The middle is where templates live: pick sharp corners OR soft
corners and commit."

Same problem, different depth. The skill doesn't give *different* advice — it gives
advice that transfers *understanding*.

## Side-by-Side: With vs Without Skill

> Prompt: "Design a SaaS pricing page (3 tiers: Hobby/Pro/Enterprise). Make Pro the obvious choice. Premium, not template-y."

### Without Skill (Baseline)

```
Visual Strategy: "Asymmetric emphasis — Pro card physically dominates."

Layout: Pro card 380px wide (vs 340px others). Cards at 32px padding,
16px radius, 24px gap. Dark background.

Toggle: Segmented control with sliding indicator. Price does vertical
slide-fade (150ms). [Full CSS + JS provided]

Anti-Template: Pro wider not taller. Gradient on 1px border only.
CTA above features. Dark mode by default.
```

Verdict: Correct, implementable, but **never explains WHY** any decision was made.
No accessibility. No CLS prevention. No escape hatch.

### With Skill (polanyi-design)

```
Design Thesis: "Pro is the protagonist. Hobby and Enterprise exist to
make Pro's value obvious through contrast."

Layout: Pro at lg:scale-[1.02] with shadow-[0_24px_48px_-12px].
Price block has FIXED h-[72px] — prevents layout shift on toggle.

Toggle: Savings badge uses emerald, not brand indigo — "emerald encodes
'money saved', a different semantic than brand identity. Using brand
blue here would flatten the information hierarchy."

"Most Popular" badge: absolute -top-3.5 — "breaks the card boundary
intentionally. A badge inside padding is subsidiary; a badge that
breaches the boundary is focal."

Accessibility: focus-visible:outline-2 on all buttons. aria-hidden on
decorative icons. role="list" on features.

What NOT to do:
- "Don't hover-lift pricing cards — they imply the whole card is
   clickable, but only the CTA is"
- "Don't list 15+ features — group into 2-3 categories"

Escape hatch: "If your product has equal adoption across tiers,
flatten the hierarchy. This strategy assumes Pro is the business model."
```

Verdict: Same technical quality, **plus** explains the tacit reasoning behind
every choice. Includes accessibility, CLS prevention, anti-patterns, and
knows when its own advice shouldn't apply.

### What the Skill Adds (Blind A/B, Evaluated by Independent Agent)

| Dimension | Without | With | What Changed |
|-----------|---------|------|-------------|
| Technical | 7.4 | 8.6 | Production-aware choices (h-[72px] for CLS, focus-visible) |
| Design | 6.6 | 7.8 | Badge breaking card boundary, emerald semantic differentiation |
| Reasoning | 5.6 | 8.0 | Explains WHY — "protagonist/supporting cast" thesis |
| Actionable | 8.0 | 8.8 | Same specs + rationale that prevents wrong implementation |
| **Tacit** | **4.6** | **8.8** | **+4.2** — Surfaces judgment tutorials never teach |

> [View the full showcase page](showcase/index.html) for rendered comparison.

---

## How It Works

Three systems fire in sequence:

| System | Purpose |
|--------|---------|
| **Knowledge Filter** | Classifies advice by depth (skip explicit, extract implicit, push toward tacit) |
| **Five Design Lenses** | Gestalt → Subsidiary-Focal → Token Hierarchy → Tacit Translation → Convention Judgment |
| **Output Protocol** | Ensures every insight pairs with concrete implementation (px, hex, font names) |

## Theoretical Foundation

Built on Michael Polanyi's tacit knowledge framework (1958-1966), operationalized through:

- **Gestalt Psychology** — perceptual integration principles applied to visual design
- **Dreyfus Skill Model** — calibrating advice depth to the user's expertise level
- **Collins' Taxonomy** — distinguishing what AI can extract vs what requires human practice

## Measured Impact

Evaluated via blind A/B testing across 5 design scenarios (landing page diagnosis,
dashboard layout, token architecture, component API review, responsive strategy):

| Dimension | Avg Improvement |
|-----------|----------------|
| Technical Correctness | **+1.6** |
| Design Quality | **+1.6** |
| Depth of Reasoning | **+2.0** |
| Actionability | **+1.6** |
| Tacit Articulation | **+2.8** |
| **Overall** | **+30.0%** |

Validated across 3 rounds of blind A/B testing on 5 design scenarios.
Trajectory: R1 +23% → R2 +31% → R3 +30% (stable plateau, production-ready).

## Credits

This is an original work. It draws inspiration from:

- **[enzyme2013/polanyi-skill](https://github.com/enzyme2013/polanyi-skill)** — First public
  Polanyi skill, built with [nuwa-skill](https://github.com/alchaincyf/nuwa-skill). Our work
  takes a different direction (cognitive engine vs role-play) but was inspired by their approach.
- **[Google Design MD (Stitch)](https://stitch.withgoogle.com/docs/design-md/format)** —
  Structured design system specification format.
- **Michael Polanyi** — *Personal Knowledge* (1958), *The Tacit Dimension* (1966)
- **The Polanyi Society** — [polanyisociety.org](https://polanyisociety.org/)

See [references/CREDITS.md](references/CREDITS.md) for full attribution.

## License

MIT

---

<div align="center">

*The easier knowledge is to codify, the less valuable restating it becomes.*
*This skill operates where documentation ends and judgment begins.*

</div>
