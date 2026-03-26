# Tool Routing Guide

Capabilities, constraints, and invocation patterns for each production skill.

---

## Skill Inventory

| Skill | Input | Output | Best For |
|-------|-------|--------|----------|
| concept-to-image | Text description + style params | PNG/SVG | Static illustrations, comparisons, conceptual visuals |
| concept-to-video | Text description + style params | MP4 (Manim) | Technical animations, math reveals, step-by-step education |
| remotion-video | Scene spec + brand params | MP4 (React) | Branded motion graphics, product demos, marketing videos |
| architecture-diagram | Component list + relationships | PNG/SVG | System topology, infrastructure, data flow diagrams |
| html-presentation | Content outline + styling | HTML slides | Talks, pitches, walkthroughs, sequential narratives |
| static-web-artifacts-builder | Data + layout spec | HTML | Interactive dashboards, infographics, data explorations |

---

## concept-to-image

### Strengths

- Fast single-frame output
- Flexible styling (illustration, diagram, infographic)
- Controllable composition and layout

### Constraints

- No animation or interactivity
- Single output frame — cannot show temporal progression
- Complex multi-component systems better served by architecture-diagram

### Invocation Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| concept | Yes | What to visualize |
| style | No | Visual style guidance (minimal, technical, illustrated) |
| dimensions | No | Output size (default: 1920x1080) |
| color_scheme | No | Palette preferences |

---

## concept-to-video (Manim)

### Strengths

- Step-by-step mathematical and technical animations
- Precise control over element entrance/exit timing
- Educational content with incremental complexity reveal

### Constraints

- Not suitable for branded/marketing content (use remotion-video)
- Limited typography and branding customization
- Longer production time than static outputs

### Invocation Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| concept | Yes | What to animate |
| steps | No | Ordered list of animation steps |
| duration | No | Target duration in seconds (default: 30-60) |
| style | No | Color and emphasis preferences |

---

## remotion-video (React)

### Strengths

- Full React component model for complex motion graphics
- Brand-consistent video with custom fonts, colors, animations
- Web-quality typography and layout

### Constraints

- Higher production complexity than Manim
- Overkill for simple technical explanations
- Requires brand parameters for best results

### Invocation Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| scenes | Yes | Scene descriptions with content and transitions |
| brand | No | Colors, fonts, logo, visual identity |
| duration | No | Target duration (default: 15-30s) |
| dimensions | No | Output size (default: 1920x1080) |

---

## architecture-diagram

### Strengths

- Purpose-built for system topology and component relationships
- Automatic layout for complex component graphs
- Standard notation for services, databases, queues, external systems

### Constraints

- Not for non-architectural concepts (use concept-to-image)
- Limited animation support
- Layout may need manual adjustment for very large systems

### Invocation Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| components | Yes | List of system components with types |
| relationships | Yes | Connections between components with labels |
| layout | No | Direction preference (LR, TB) |
| style | No | Color and shape overrides |

---

## html-presentation

### Strengths

- Web-native slides with transitions and animations
- Speaker notes support
- Exportable to PDF for distribution

### Constraints

- Sequential format — not suitable for non-linear exploration
- Limited to slide-based layouts
- One idea per slide discipline required

### Invocation Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| outline | Yes | Slide content and order |
| theme | No | Color scheme, font, layout style |
| speaker_notes | No | Notes per slide |

---

## static-web-artifacts-builder

### Strengths

- Full interactivity (hover, click, filter, zoom)
- Responsive layout adapts to screen size
- Combines data visualization with narrative text

### Constraints

- Requires browser to view — not embeddable in PDF or slides
- Higher production complexity
- Overkill for static data that does not need exploration

### Invocation Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| data | Yes | Data to visualize |
| layout | Yes | Dashboard/infographic layout spec |
| interactivity | No | Interaction types (filter, hover, drill-down) |
| style | No | Color and typography |

---

## Routing Decision Tree

```
Is it a system/infrastructure topology?
  → Yes: architecture-diagram
  → No: Does it have a temporal dimension?
    → Yes: Is it branded/marketing?
      → Yes: remotion-video
      → No: concept-to-video (Manim)
    → No: Does it need user interaction?
      → Yes: static-web-artifacts-builder
      → No: Is it a sequential narrative?
        → Yes: html-presentation
        → No: concept-to-image
```
