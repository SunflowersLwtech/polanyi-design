<div align="center">

# polanyi-design

> *"We can know more than we can tell."*
> — Michael Polanyi, *The Tacit Dimension* (1966)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/code)

**A frontend design cognitive engine** that surfaces the visual judgment<br>
senior designers *know* but rarely articulate.

Not a role-play. Not a template generator.<br>
An operational thinking system grounded in tacit knowledge theory.

[Install](#install) · [See the Difference](#-see-the-difference) · [How It Works](#-how-it-works) · [Measured Impact](#-measured-impact) · [Credits](#credits)

</div>

---

## Install

```bash
npx skills add SunflowersLwtech/polanyi-design
```

---

## 👁 See the Difference

> **Same prompt, same model, different depth.**

Open both demo pages side-by-side to see the actual rendered output:

| Without Skill | With Skill |
|:---:|:---:|
| [demo-baseline.html](showcase/demo-baseline.html) | [demo-enhanced.html](showcase/demo-enhanced.html) |
| Correct layout, standard patterns | Every choice has a *reason* |

### Prompt: *"Design a SaaS pricing page — 3 tiers, make Pro the obvious choice, premium not template-y."*

<table>
<tr>
<th width="50%">❌ Without Skill (Baseline)</th>
<th width="50%">✅ With polanyi-design</th>
</tr>
<tr>
<td>

**Visual Strategy**<br>
"Asymmetric emphasis — Pro card physically dominates."

**Layout**<br>
Pro 380px wide vs 340px. Cards 32px padding, 16px radius.

**Toggle**<br>
Segmented control, slide-fade animation.

**Anti-Template**<br>
• Pro wider not taller<br>
• Gradient on 1px border only<br>
• CTA above features<br>
• Dark mode by default

</td>
<td>

**Design Thesis**<br>
*"Pro is the protagonist. Hobby and Enterprise exist to make Pro's value obvious through contrast."*

**Layout + Reasoning**<br>
Pro at `scale-[1.02]`. Price block has **fixed `h-[72px]`** to prevent layout shift on toggle.

**Toggle + Semantic Color**<br>
Savings badge uses `emerald` not indigo — *"emerald encodes 'money saved', a different semantic than brand identity"*

**Boundary-Breaking Badge**<br>
*"`absolute -top-3.5` — breaks the card boundary intentionally. A badge inside padding is subsidiary; a badge that breaches is focal."*

**Accessibility**<br>
`focus-visible:outline-2`, `aria-hidden` on icons, `role="list"` on features.

**What NOT to Do**<br>
• *"Don't hover-lift pricing cards — they imply the whole card is clickable"*<br>
• *"Don't list 15+ features — group into categories"*

**Escape Hatch**<br>
*"If your product has equal tier adoption, flatten the hierarchy. This assumes Pro is the business model."*

</td>
</tr>
<tr>
<td>

🔍 Correct and implementable.<br>
Never explains *why*.

</td>
<td>

🎯 Same specs + tacit reasoning<br>
that prevents wrong implementation.

</td>
</tr>
</table>

---

## 🧠 How It Works

Three systems fire in sequence:

### System 1: Knowledge Filter

```
┌─────────────────────────────────┐
│  SKIP (Explicit)                │  Don't restate Tailwind docs.
├─────────────────────────────────┤
│  EXTRACT (Implicit) ★          │  Senior designer reasoning.
│  This is where you spend tokens │  The unspoken "why."
├─────────────────────────────────┤
│  PUSH (Tacit)                   │  "This feels off" → structural
│  Embodied · Holistic · Context  │  diagnosis + concrete fix.
└─────────────────────────────────┘
```

### System 2: Five Design Lenses

| Lens | What It Does | Example |
|------|-------------|---------|
| **Gestalt First** | Perceive the whole before parts | *"The gestalt voice test fails — no single adjective describes this page"* |
| **Subsidiary-Focal** | Design system should be invisible | *"Users notice the interface → it has failed its subsidiary role"* |
| **Token Hierarchy** | Raw → Semantic → Component | *"Good tokens ≠ good design. Tokens provide materials, not judgment."* |
| **Tacit Translation** | Feeling → Cause → Fix → Why | *"Feels cramped" → content-to-whitespace ratio → increase padding 1.5x* |
| **Convention Judgment** | Know when to break rules | *"8px grid exists for rhythm — break it for optical alignment (2-4px)"* |

### Cross-Cutting Modules

| Module | Coverage |
|--------|---------|
| **Accessibility** | Focus states (2px outline), contrast verification (AA 4.5:1), touch targets (44px), `prefers-reduced-motion`, screen reader guidance |
| **Motion System** | Duration scale (100ms micro → 800ms data), easing vocabulary (ease-out entrances, spring feedback), choreography (stagger 30-50ms), reduced-motion fallback |
| **Data Visualization** | Categorical (6 hues max), sequential (single-hue ramp), divergent (red ← gray → emerald), colorblind safety (blue/orange, redundant encoding) |
| **Quality Verification** | axe-core, 200% zoom test, keyboard navigation, VoiceOver flow, visual regression at 375/768/1440px |

### System 3: Output Protocol

Every response follows: **Spec first, philosophy second.**

```
[1-sentence gestalt diagnosis]
[Concrete fixes with EXACT values — px, hex, font names]
[Tacit rationale — why it matters experientially]
[What NOT to do — prevents the most likely wrong fix]
[Escape hatch — when this advice shouldn't apply]
```

---

## 📊 Measured Impact

Evaluated via **blind A/B testing** — an independent evaluator agent scored baseline
vs enhanced responses without knowing which was which.

### Per-Dimension Improvement

| Dimension | Δ | What This Means |
|-----------|:---:|----------------|
| Technical Correctness | **+1.6** | Production-aware choices (CLS prevention, `focus-visible`, `asChild`) |
| Design Quality | **+1.6** | Badge focal tension, semantic color differentiation, shadow conviction |
| Depth of Reasoning | **+2.0** | Explains *why* — "protagonist/supporting cast" design thesis |
| Actionability | **+1.6** | Same specs + rationale that prevents wrong implementation |
| **Tacit Articulation** | **+2.8** | Surfaces judgment tutorials never teach |

### Iteration Trajectory

```
R1  ████████████████████████░░░░░░░░░░░░░░░░  +23.0%  AC regression found
R2  ████████████████████████████████░░░░░░░░░  +31.0%  AC fixed (+3.0 swing)
R3  ███████████████████████████████░░░░░░░░░░  +30.0%  Production ready
    ─────────target: +20%──────────
```

> *"The skill has moved from 'gives better answers' to 'gives answers that think*
> *the way a senior designer thinks.'"*
> — Independent evaluator agent

---

## Theoretical Foundation

Built on **Michael Polanyi's tacit knowledge framework** (1958-1966):

- **Tacit Knowledge** — "We know more than we can tell." Expert judgment resists full codification.
- **Subsidiary-Focal Awareness** — We attend *from* tools (subsidiary) *to* tasks (focal). Great design systems are subsidiary — you look *through* them.
- **Gestalt Integration** — Polanyi drew from Gestalt psychology. UI design IS gestalt — figure/ground, proximity, continuity, closure.
- **Indwelling** — Mastery = the tool becomes part of the mind. A well-designed API lets developers think *through* it, not *about* it.

Operationalized through:

| Researcher | Contribution | How We Use It |
|-----------|-------------|--------------|
| **Dreyfus Brothers** | 5-stage skill acquisition model | Calibrate advice depth to user expertise |
| **Harry Collins** | Tacit knowledge taxonomy | Distinguish what AI can extract vs what requires practice |
| **Nonaka (critique)** | SECI model's misreading of Polanyi | Acknowledge what *cannot* be fully codified |

---

## Credits

This is an **original work**, not a fork. We gratefully acknowledge:

- **[enzyme2013/polanyi-skill](https://github.com/enzyme2013/polanyi-skill)** — First public Polanyi skill. Built with [nuwa-skill](https://github.com/alchaincyf/nuwa-skill). Inspired our approach of encoding cognitive patterns as operational frameworks.
- **[Google Design MD (Stitch)](https://stitch.withgoogle.com/docs/design-md/format)** — Structured design system specification format.
- **Michael Polanyi** — *Personal Knowledge* (1958), *The Tacit Dimension* (1966)
- **The Polanyi Society** — [polanyisociety.org](https://polanyisociety.org/)

See [references/CREDITS.md](references/CREDITS.md) for full attribution.

---

## License

```
MIT License

Copyright (c) 2026 sunfl

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

<div align="center">

*The easier knowledge is to codify, the less valuable restating it becomes.*<br>
*This skill operates where documentation ends and judgment begins.*

<br>

**[View Live Demo](showcase/index.html)** · **[SKILL.md](SKILL.md)** · **[Full Credits](references/CREDITS.md)**

</div>
