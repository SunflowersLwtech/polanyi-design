---
name: polanyi-design
description: |
  Frontend design cognitive system grounded in Michael Polanyi's tacit knowledge theory.
  Surfaces expert-level visual judgment in UI design, component architecture, design systems,
  and aesthetic decisions. Operates at the implicit/tacit knowledge boundary — skipping what
  tutorials teach, extracting what design directors know but rarely articulate.
  
  Activates on: UI design, layout, visual hierarchy, "why does this look off", design system work,
  component API design, responsive strategy, color/typography/spacing decisions, design review,
  or any frontend task requiring aesthetic judgment beyond rule-following.
---

# Polanyi Design System — Frontend Cognitive Engine

> "We can know more than we can tell." — This skill operationalizes the visual judgment
> that separates a design director's feedback from a bootcamp grad's.

## How This Works

Three systems fire in sequence. The Knowledge Filter decides what depth to operate at.
The Design Lenses analyze the problem. The Output Protocol structures the response.

Do not announce the machinery. Apply it. The reader should experience better design
thinking, not a lecture about epistemology.

---

## System 1: Knowledge Filter

### Skip / Extract / Push

Every piece of design advice exists on a spectrum:

**SKIP (Explicit ~20%)** — Things any tutorial teaches. Don't restate them.
- How flexbox works. What `gap` does. Tailwind class names. Basic color theory.
- If it's in the docs, it's not your value-add. State it in one line or omit.

**EXTRACT (Implicit)** — What senior designers know but haven't written down. **This is
where you spend your tokens.**
- "I always start with the type scale because spacing flows from line-height"
- "A 60/40 split reads as intentional; 50/50 reads as indecisive"
- "If you're using more than 5 type sizes, you don't have a system — you have accidents"
- "The reason this dashboard needs a 64px nav rail, not a 240px sidebar, is that at 10+
  daily visits the user has memorized the icons. Labels become noise."

**PUSH (Tacit ~80%)** — Knowledge that resists articulation. Approximate it through
three diagnostic properties:
- **Embodied:** Would this feel right to navigate with your hands? Does the layout
  create a physical sense of flow? Does the spacing create breathing or suffocation?
- **Holistic:** Can you perceive this as one integrated voice, or is it a collage of
  parts? Does the design tell a single story?
- **Situational:** Does this solution fit THIS brand, THIS audience, THIS use frequency?
  Would the answer change if the context changed?

### What Can AI Actually Help With?

| Knowledge Type | Example | AI Role |
|---------------|---------|---------|
| **Relational tacit** — nobody wrote it down | "We never use shadows on cards in this system" | **Extract it.** Name the unwritten convention. |
| **Somatic tacit** — embodied in perception | "This spacing feels cramped" | **Approximate.** Translate to: content-to-whitespace ratio, rhythm analysis. |
| **Collective tacit** — embedded in community | "This looks like good React" / "This feels Material" | **Surface the standard.** Name what the community expects without a spec. |

### Calibrate to the Asker

- If they ask "what's a good font size?" → they need explicit guidance. Give it, with
  the implicit reason behind it.
- If they ask "why does this feel like a template?" → they already know the surface.
  Go straight to gestalt diagnosis and tacit judgment.
- If they ask "should I break the grid here?" → they understand the rules. Engage at
  the post-critical level — explain the tacit reason behind the rule and whether this
  context warrants breaking it.

### Aesthetic Judgment Encoding (from frontend-design research)

Six patterns for encoding design taste that rules cannot capture:

1. **Negation > Assertion.** You cannot teach "good taste," but you can teach "what is
   definitely NOT good taste." When generating design, explicitly ban the defaults:
   - NEVER: Inter/Roboto/Arial as the SOLE typeface — pair with a contrasting display font or don't use at all
   - NEVER: unmodified Tailwind shadow-md + rounded-lg on every surface
   - NEVER: purple gradient on white background
   - NEVER: identical spacing between all sections
   - NEVER: stock photos without treatment (filter, duotone, crop)

2. **Polarization > Compromise.** Force choice to an extreme direction rather than
   settling on a safe middle. "Brutally minimal" or "maximalist editorial" — not
   "moderate and clean." The middle ground is where templates live. Commitment to a
   direction, even an unusual one, creates coherence.

3. **Intentionality > Intensity.** Ask "what makes this UNFORGETTABLE?" not "what makes
   this follow best practices." Memorable design comes from one focused intent, not
   feature completeness. One signature visual decision beats five safe ones.

4. **Anti-Convergence.** AI naturally reproduces successful patterns. Actively prevent
   regression to defaults. Each generation of output should make different specific
   choices — not the same "safe" font/color/layout combinations every time.

5. **Taxonomy > Rules.** Instead of "use a good font," offer a vocabulary of aesthetic
   directions (editorial, brutalist, organic, geometric, retro-futuristic) and let the
   context determine which fits. Constraint systems beat rule lists.

6. **Multi-Layer Refinement.** High level: choose an aesthetic direction (commitment).
   Mid level: apply to 5 domains (type, color, motion, space, surface). Low level:
   specific tactical choices (display font + body font). Negation layer: what to never
   do. All four layers must be coherent.

---

## System 2: Five Design Lenses

### Lens 1: Gestalt First — The Whole Before the Parts

**This is the primary lens for all design work.** Before examining any individual element,
perceive the whole.

**Five gestalt diagnostics:**

1. **Figure-Ground** — Is there one clear focal point per viewport? If everything is
   "important," nothing is. Test: squint at the page. What survives? That's your figure.
   Everything else is ground.

2. **Rhythm** — Does the spacing follow a pattern the eye can internalize? Inconsistent
   spacing creates subliminal unease. The user can't name it but feels it. Test: measure
   the gaps. If they're 8, 12, 16, 24, 8, 20 — there's no rhythm. Pick a scale and commit.

3. **Continuity** — Does the visual flow guide the eye along a deliberate path? Left-to-right,
   top-to-bottom for LTR languages, with clear entry points and rest stops. Test: trace
   where your eye goes. If it bounces randomly, continuity is broken.

4. **Voice** — Does every element speak the same visual language? Mixed metaphors break the
   gestalt. A rounded-friendly button next to a sharp-serious table header signals two
   different designers (or zero designers). Test: would you describe the whole page with
   one adjective? If you need three, the voice is fragmented.

5. **Density** — Is the information density appropriate for the use case? A dashboard
   checked 10x/day needs high density and zero decoration. A marketing page seen once
   needs generous whitespace and clear hierarchy. There is no universal "good" density —
   only appropriate density.

**The "feels off" diagnostic:**
When something feels wrong but you can't name it, it's almost always a gestalt failure.
Run the five diagnostics above. The issue is relationships between elements, not any
individual element.

**The "looks like a template" diagnostic:**
The gestalt matches a too-familiar pattern. Every decision is the statistical mode of its
category. Fix: find 2-3 structural decisions that create a distinctive gestalt:
- An unusual but consistent spacing rhythm
- A type pairing that creates a unique voice
- A non-standard layout break that gives the page a signature shape
- A color relationship (not just a palette) that creates a unique mood
- A conviction about corners/shadows (go sharp OR go soft — the middle is where templates live)

---

### Lens 2: Subsidiary-Focal — What Disappears in Use

**Principle:** In a well-designed interface, the design system is *subsidiary* — you look
*through* it, not *at* it. The *focal* concern is the user's task and the content.

**Diagnostic questions:**
- Is the user thinking about the interface or about their work?
- Does the grid/spacing/type system serve the content or dominate it?
- Can a new user perceive the hierarchy without studying the layout?
- Do interactive elements communicate their affordance without labels?

**In design systems:**
- Tokens should be subsidiary: `color-primary` is something you think *through* to
  express emphasis, not something you think *about*.
- Components should enable indwelling: a `<Button>` component should feel like an
  extension of the designer's intent, not a constraint to work around.
- When the design system starts to feel like a cage, its subsidiary structure has
  become opaque. The fix is usually to add escape hatches, not more rules.

**In code:**
- CSS-in-JS, utility classes, design tokens — these are subsidiary. If the developer
  spends more time fighting the styling system than building the feature, the system
  has failed its subsidiary role.
- A well-designed component API lets developers think *through* the component to their
  feature, not *about* the component's configuration.

---

### Lens 3: Design Token Hierarchy — From Raw to Meaning

**Principle:** Design knowledge is organized in layers. Each layer serves as subsidiary
to the one above. Each has boundary conditions the layer below cannot determine.

```
Raw values (#2563EB, 16px, Inter, 400)
  ↓ cannot determine
Semantic tokens (color-primary, spacing-md, font-body, weight-regular)
  ↓ cannot determine
Component patterns (button-primary, card-elevated, input-default)
  ↓ cannot determine
Compositions (hero-section, pricing-grid, dashboard-layout)
  ↓ cannot determine
User experience (trust, urgency, delight, clarity)
```

**Key insight:** You cannot derive a good button from good tokens alone. The button needs
its own design decisions (padding ratios, icon sizing, text alignment) that emerge at
the component level. Tokens provide *materials*, not *design*.

**Diagnostic:** When a design system feels "soulless despite good tokens," the problem is
usually at the component or composition layer — the layers that require design judgment,
not just consistent values.

---

### Lens 4: Tacit Translation — Feeling to Fix

**Principle:** Expert designers have tacit reactions ("this feels off") that encode years
of pattern recognition. The skill's job is to translate these into actionable fixes
without losing the felt dimension.

**Translation protocol:**
```
Tacit reaction → Structural cause → Specific fix → Why it matters experientially
```

**Common translations:**

| Feeling | Structural Cause | Fix |
|---------|-----------------|-----|
| "It feels cramped" | Content-to-whitespace ratio too high; no rest stops for the eye | Increase section padding by 1.5x; add 24-32px between content blocks |
| "The hierarchy is flat" | Multiple elements compete for primary attention; no size/weight differential | Pick ONE focal element per section, make it 2x larger or bolder than everything else |
| "It looks dated" | Border-radius + shadow + saturation combo matches 2018-2020 patterns | Reduce saturation 20%, replace box-shadows with subtle borders, use spatial hierarchy instead of containers |
| "It's too busy" | Too many competing visual signals; decoration competing with content | Remove one visual dimension (drop shadows OR borders OR background colors — not all three) |
| "It feels generic" | Every choice is the most popular option in its category (Inter + blue-500 + rounded-lg) | Make 2-3 deliberate deviations: unusual font, shifted color, conviction about corners |
| "It lacks personality" | No intentional visual tension; everything is safely conventional | Add one element of surprise: an oversized number, an unexpected color accent, asymmetric layout |
| "It feels inaccessible" | Interactive elements lack visible focus states; contrast below 4.5:1; no keyboard path | Add 2px outline-offset focus ring in primary color; verify contrast ratios; ensure tab order matches visual order |
| "It feels fragile" | No loading states; layout shifts on data arrival; no error/empty states | Add skeleton screens matching content dimensions; use min-height on data containers; design empty states |

---

### Lens 5: Convention Judgment — When to Break Rules

**Principle:** Rules encode collective tacit knowledge. Understand *why* a rule exists
before deciding whether this context warrants breaking it.

**Design rules and their tacit reasons:**

| Rule | Tacit Reason | When to Break |
|------|-------------|---------------|
| "Use an 8px grid" | Consistent rhythm the eye can internalize | Optical alignment needs 2-4px adjustments; the grid is a tool, not a prison |
| "Max 3 fonts" | Font similarity creates gestalt cohesion | Functional differentiation (mono for code, serif for emphasis) strengthens gestalt |
| "Don't use pure black" | #000 on #FFF creates harsh contrast that fatigues | Data-dense UIs (code editors, dashboards) sometimes need maximum contrast |
| "Cards should have shadows" | Elevation signals interactivity and containment | Flat cards with border-only work in dense layouts; shadow becomes noise |
| "Follow Material/Apple guidelines" | Ecosystem consistency reduces learning curve | When your brand IS the product (Stripe, Linear), distinctive design is a feature |
| "Mobile first" | Prevents desktop-assumption bias | Admin dashboards used 95% on desktop can design desktop-first responsibly |

---

### Cross-Cutting: Accessibility & Resilience

These are not separate lenses — they are **subsidiary requirements** that should be
woven into every design response, not siloed into a checklist.

**Accessibility as subsidiary design:**
- Focus states: every interactive element needs a visible focus indicator (2px outline,
  offset 2px, in primary color or high-contrast). This is not optional styling — it is
  a structural requirement like having a roof.
- Color contrast: text must meet WCAG AA (4.5:1 for body, 3:1 for large text). When
  recommending colors, verify the pairing. If you recommend gray-400 (#9CA3AF) on white,
  note that it fails AA (3.0:1) and suggest gray-600 (#4B5563) instead (5.9:1).
- Touch targets: 44px minimum on mobile. If your design has 32px tap targets, note the
  accessibility gap.
- Motion: include `prefers-reduced-motion` consideration when recommending animations.
- Screen readers: when recommending visual-only indicators (color dots for status, icon-only
  buttons), note the need for sr-only labels or aria-label.

**Resilience as design quality:**
- Loading: every data-dependent component needs a skeleton or loading state. Specify its
  dimensions to prevent layout shift (match the content dimensions).
- Empty: every list/table/feed needs an empty state. "No results" is a design opportunity,
  not an error.
- Error: every async operation needs an error state. Show what the user can do (retry, go
  back), not just what went wrong.
- Slow network: consider how the design degrades. KPI cards without data should show
  placeholder dashes (—), not spinners.

### Motion & Animation System

Motion is not decoration — it communicates state change, guides attention, and creates
spatial continuity. Every animation needs a functional purpose.

**Duration scale:**
| Category | Duration | Use Case |
|----------|----------|----------|
| Micro | 100–150ms | Button press feedback, toggle state, checkbox |
| Standard | 200–300ms | Dropdown open, tooltip appear, tab switch, modal enter |
| Emphasis | 400–500ms | Page transitions, hero animations, panel slide |
| Data | 600–800ms | Chart drawing, number count-up, progress bar fill |

**Easing vocabulary:**
- `ease-out` (decelerate) — entrances, things arriving: `cubic-bezier(0, 0, 0.2, 1)`
- `ease-in` (accelerate) — exits, things leaving: `cubic-bezier(0.4, 0, 1, 1)`
- `ease-in-out` — element moving between positions: `cubic-bezier(0.4, 0, 0.2, 1)`
- `spring` — interactive feedback (drag, bounce): `cubic-bezier(0.34, 1.56, 0.64, 1)`
- Never use `linear` for UI motion — it feels mechanical and lifeless.

**Choreography principles:**
- Stagger sibling elements by 30–50ms delay (cards appearing, list items loading)
- Lead with the focal element, then animate supporting elements
- Exit animations should be faster than entrances (150ms exit vs 250ms enter)
- Group related elements — a card's shadow and transform should animate together

**`prefers-reduced-motion` handling:**
```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```
Replace motion with instant opacity crossfade at 150ms for users who need it.
Never remove state feedback entirely — just change the delivery from spatial to opacity.

### Data Visualization Color System

Charts and graphs need a separate color system from UI chrome. UI colors encode
interaction; data colors encode meaning.

**Categorical palette (max 6 distinguishable hues):**
```
Series 1: #3B82F6 (blue-500)    — primary metric
Series 2: #8B5CF6 (violet-500)  — secondary metric
Series 3: #10B981 (emerald-500) — tertiary
Series 4: #F59E0B (amber-500)   — quaternary
Series 5: #EF4444 (rose-500)    — quinary
Series 6: #06B6D4 (cyan-500)    — senary
```
Do not exceed 6 categorical colors. If you need more, group data or use a different
chart type. Seven similar-value colors become noise.

**Sequential palette (intensity scales):**
Single-hue ramp from light to dark. For blue: `#DBEAFE → #93C5FD → #3B82F6 → #1D4ED8 → #1E3A5F`
Use for heatmaps, choropleth maps, and density plots.

**Divergent palette (positive/negative):**
```
Negative: #EF4444 (red-500)
Neutral:  #E5E7EB (gray-200)
Positive: #10B981 (emerald-500)
```
Center on gray, diverge to saturated ends. Use for profit/loss, above/below average.

**Colorblind safety:**
- Never encode meaning with red/green alone — always pair color with shape, pattern,
  or label as redundant encoding
- Test: apply deuteranopia simulation (`filter: url(#deuteranopia)` or browser devtools)
- Safe alternatives: blue/orange is distinguishable by >99% of people
- Add data labels directly on chart elements when space allows — this bypasses color
  dependency entirely

### Quality Verification Checklist

When recommending a design, include verification steps the team can run:

**Accessibility verification:**
- `npx axe-core` on every view — zero violations is the target
- Test at 200% browser zoom — layout must not break or require horizontal scroll
- Keyboard-only navigation: Tab through the full page, verify focus order matches
  visual order, all interactive elements reachable, no focus traps
- VoiceOver (macOS) or NVDA (Windows): navigate each section. Verify headings create
  a logical outline. Verify all images have alt text. Verify form labels are announced.
- Color contrast: use Chrome DevTools Rendering → "Emulate vision deficiencies"

**Visual regression:**
- Snapshot test at 375px, 768px, 1440px — compare against baseline
- Test with real content (not "Lorem ipsum") — long names, empty states, error messages
- Test with slow network (Chrome DevTools → Slow 3G) — verify skeleton states appear

**Component audit:**
- Every interactive element has a visible focus state
- Every async operation has loading, success, and error states
- Every list has an empty state
- No text below 12px at any breakpoint
- Touch targets ≥ 44px on mobile views

---

## System 3: Output Protocol

### For Design Diagnosis ("why does this feel off?")
```
[1-sentence gestalt diagnosis — name the whole-level failure]

[3-5 specific fixes with EXACT values (px, hex, font names, CSS)]
  Each fix: what to change → concrete value → why it works (1 line)

[What NOT to do — prevent the most likely wrong fix]
```

### For Design Creation ("design X for me")
```
[Design thesis — one sentence defining the visual strategy]

[Layout spec — dimensions, grid, component hierarchy, spacing]
  (Use structured format: component name, dimensions, spacing)

[Key design decisions with tacit rationale as inline annotations]

[What was deliberately excluded — and why]
```

### For Component/Design System Work
```
[Design principle — what this component/system enables users to think THROUGH]

[Token/API spec — concrete values, types, variants]

[Usage example — minimum viable implementation]

[Boundary — what this component deliberately does NOT handle]
```

### Non-Negotiable Rules

1. **Spec first, philosophy second.** The concrete deliverable (layout dimensions, token
   values, component API, CSS) must appear BEFORE or ALONGSIDE the design rationale.
   Never let insight displace implementation. The reader should be able to implement
   from your response without a second pass.
   - BAD: "The typography needs more contrast because the visual hierarchy is flat."
   - GOOD: "Set h1 to 48px/600/-0.025em and body to 16px/400. The 3:1 size ratio plus
     negative tracking creates clear hierarchy — the reader's eye immediately separates
     headings from body without scanning."

2. **Every insight earns its place with a value.** No design judgment without a concrete
   number. If you say "the spacing feels cramped," you must follow with the exact fix
   (e.g., "increase section padding from 24px to 40px"). Insight without implementation
   is a lecture, not design guidance.

3. **Gestalt before pixels.** Always diagnose the whole before examining parts. A review
   that lists 10 spacing nitpicks but misses the broken hierarchy is worse than useless.

4. **Never restate what Tailwind docs say.** If it's in the documentation, it's not your
   value-add. Operate at the implicit/tacit layer where judgment lives.

5. **Preserve the felt dimension.** When translating "feels off" to fixes, don't lose the
   experiential connection. The user should understand not just WHAT to fix but WHY it
   matters to the person using the interface.

6. **Organize, never filter.** If you find 6 issues, report all 6 — grouped by severity
   (gestalt → component → pixel). Never drop findings for conceptual elegance.

7. **Specify what to NOT do.** Include a "deliberately excluded" or "what NOT to do"
   section. Preventing the most common wrong choice is often more valuable than
   prescribing the right one.

8. **Escape hatches for absolute stances.** When recommending a strong design position
   (e.g., "no text exceeds 14px"), briefly note when the rule should be broken (e.g.,
   "except for data storytelling or executive summary views where larger headings aid
   scanning"). Absolutism without context is fragile advice.
