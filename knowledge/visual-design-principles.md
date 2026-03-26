# Visual Design Principles

Styling defaults, layout rules, and visual hierarchy patterns for asset production.

---

## Color Defaults

### Base Palette

| Role | Default | Usage |
|------|---------|-------|
| Background | #FFFFFF (light) / #1A1A2E (dark) | Canvas |
| Primary | #2563EB | Key elements, CTAs, emphasis |
| Secondary | #7C3AED | Supporting elements, accents |
| Success | #059669 | Positive states, completion |
| Warning | #D97706 | Caution, attention items |
| Error | #DC2626 | Failures, critical items |
| Text primary | #111827 (light) / #F9FAFB (dark) | Body text |
| Text secondary | #6B7280 | Captions, labels, metadata |
| Border | #E5E7EB | Separators, containers |

### Color Rules

- Maximum 3 accent colors per visual
- Use color to encode meaning, not decoration
- Maintain WCAG AA contrast ratio (4.5:1 for text, 3:1 for large text)
- Consistent color mapping across related visuals (same concept = same color)

---

## Typography

| Element | Size | Weight | Line Height |
|---------|------|--------|-------------|
| Title / H1 | 36-48px | Bold (700) | 1.2 |
| Subtitle / H2 | 24-32px | Semibold (600) | 1.3 |
| Body | 16-18px | Regular (400) | 1.5 |
| Caption | 12-14px | Regular (400) | 1.4 |
| Code | 14-16px | Monospace | 1.5 |

### Typography Rules

- One font family per visual (two maximum: one for headings, one for body)
- Sans-serif for digital, serif acceptable for formal PDF reports
- Never use more than 3 font sizes in a single visual
- Monospace for code, data, and technical labels only

---

## Layout Hierarchy

### Visual Weight Order

1. **Size** — larger elements draw attention first
2. **Color** — saturated/contrasting elements stand out
3. **Position** — top-left (LTR) or center for key elements
4. **Isolation** — whitespace around an element increases its importance

### Spacing System

| Scale | Value | Usage |
|-------|-------|-------|
| xs | 4px | Between related inline elements |
| sm | 8px | Between list items, tight groups |
| md | 16px | Between sections within a group |
| lg | 24px | Between major sections |
| xl | 48px | Between top-level sections |

### Alignment Rules

- Left-align text (never center body text)
- Center-align titles and single-line callouts
- Grid-align related elements (columns, cards)
- Consistent padding within containers

---

## Diagram Conventions

### Architecture Diagrams

| Element | Shape | Color |
|---------|-------|-------|
| Service / Application | Rounded rectangle | Primary |
| Database | Cylinder | Secondary |
| External system | Dashed rectangle | Text secondary |
| User / Actor | Person icon | Text primary |
| Queue / Stream | Parallelogram | Warning |
| Load balancer | Diamond | Primary |

### Flow Direction

- Left-to-right for data flow and process sequences
- Top-to-bottom for hierarchies and layer architectures
- Consistent arrow style: solid for data flow, dashed for async/optional

### Labels

- Every element has a label
- Every connection has a label describing what flows through it
- Labels use sentence case, not title case
- Font size for labels: 12-14px

---

## Animation Principles (Video)

| Principle | Rule |
|-----------|------|
| Entrance | Elements appear one at a time, building complexity incrementally |
| Duration | 0.3-0.5s per element transition, 1-2s per step hold |
| Pacing | Pause on key frames to let the viewer absorb |
| Emphasis | Highlight the active element, dim completed/upcoming elements |
| Exit | Completed elements stay visible but reduce to secondary color |
| Text | Appear with the visual it describes, never before |

---

## Anti-Patterns

| Pattern | Problem | Fix |
|---------|---------|-----|
| Rainbow color palette | No visual hierarchy | Limit to 3 accent colors |
| Centered body text | Harder to read | Left-align |
| Tiny labels on diagrams | Illegible | Minimum 12px, abbreviate if needed |
| Decorative gradients | Distraction | Flat colors, gradient only for depth cue |
| Shadows on everything | Visual noise | Shadow only on elevated elements (cards, modals) |
| Animations > 1s per step | Feels slow | 0.3-0.5s transitions |
| Text without visual | Wasted format | If text-only, use a document, not a visual |
