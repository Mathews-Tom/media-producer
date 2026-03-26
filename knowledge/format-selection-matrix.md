# Format Selection Matrix

Decision rules for routing concepts to the correct visual production skill.

---

## Primary Routing Table

| Concept Type | Default Skill | Output Format | Rationale |
|-------------|---------------|---------------|-----------|
| System topology / infrastructure | architecture-diagram | PNG/SVG | Purpose-built for component relationships and data flow |
| Static concept / comparison / illustration | concept-to-image | PNG | Single-frame visual, no temporal dimension |
| Algorithm / math / technical education | concept-to-video (Manim) | MP4 | Step-by-step reveals show complexity incrementally |
| Branded product demo / marketing | remotion-video (React) | MP4 | Polished motion graphics with brand consistency |
| Interactive data visualization / dashboard | static-web-artifacts-builder | HTML | User exploration requires interactivity |
| Talk / pitch / walkthrough | html-presentation | HTML | Sequential narrative with slide structure |

---

## Concept Type Classification

### System / Architecture

**Signals**: components, services, databases, APIs, data flow, infrastructure, deployment, topology, microservices, cloud resources

**Examples**: "show how our services communicate", "diagram the deployment pipeline", "visualize the database schema"

### Process / Workflow

**Signals**: steps, sequence, pipeline, state machine, flow, before/after, transformation

**Route**: If linear sequence → concept-to-video (Manim). If branching/parallel → architecture-diagram. If simple before/after → concept-to-image.

### Data / Comparison

**Signals**: metrics, benchmarks, performance, comparison table, feature matrix, statistics

**Route**: If interactive exploration needed → static-web-artifacts-builder. If static snapshot → concept-to-image. If time-series reveal → concept-to-video.

### Narrative / Story

**Signals**: product demo, explainer, walkthrough, pitch, onboarding, tutorial

**Route**: If branded/marketing → remotion-video. If educational/technical → concept-to-video. If sequential presentation → html-presentation.

### Abstract / Conceptual

**Signals**: mental model, framework, relationship map, hierarchy, taxonomy

**Route**: If hierarchical → architecture-diagram. If single-frame → concept-to-image.

---

## Decision Overrides

| Condition | Override |
|-----------|----------|
| User specifies format explicitly | Use specified format regardless of concept type |
| Simple concept + video requested | Warn that static may suffice, proceed if confirmed |
| Complex concept + static requested | Warn that animation may communicate better, proceed if confirmed |
| Multiple formats requested | Produce each through its respective skill sequentially |
| Concept has no temporal dimension | Never use video skills — static or interactive only |
| Concept requires user exploration | Always use static-web-artifacts-builder, never static image |

---

## Complexity Matching

| Content Complexity | Visual Complexity | Format |
|-------------------|-------------------|--------|
| Simple comparison (2-3 items) | Low | Static image |
| System with 3-5 components | Medium | Architecture diagram |
| Multi-step algorithm | Medium-High | Manim animation |
| Branded product narrative | High | Remotion video |
| Multi-dimensional data exploration | High | Interactive HTML |
| 10+ slide narrative | Medium | Presentation deck |

**Rule**: visual complexity should match content complexity. A simple before/after does not need an animated video. A multi-component architecture does not belong in a single static image.

---

## Output Specifications

| Skill | Default Dimensions | Duration | File Size Target |
|-------|--------------------|----------|-----------------|
| concept-to-image | 1920x1080 or 1080x1080 | N/A | < 2MB |
| architecture-diagram | Auto-sized to content | N/A | < 1MB |
| concept-to-video (Manim) | 1920x1080 | 30-120 seconds | < 50MB |
| remotion-video | 1920x1080 | 15-60 seconds | < 100MB |
| static-web-artifacts-builder | Responsive | N/A | < 5MB |
| html-presentation | 1920x1080 per slide | N/A | < 10MB |
