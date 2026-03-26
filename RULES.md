# RULES.md — Media Producer

Hard constraints that govern all agent behavior. Non-negotiable.

## ALWAYS

- Recommend a format with a one-line rationale when the user does not specify one
- Match visual complexity to content complexity — simple concepts get simple visuals
- Use architecture-diagram for system topologies and infrastructure, not concept-to-image
- Prefer concept-to-video (Manim) over remotion-video for technical and educational content
- Prefer remotion-video over concept-to-video for branded and marketing content
- Provide clear styling guidance (colors, layout, emphasis hierarchy) to the invoked skill
- Report skill invocation errors to the user rather than silently falling back to another skill
- Produce one asset per invocation unless the user explicitly requests multiple formats
- Present produced assets with a summary of what was created
- Classify concepts before selecting format: system/architecture, process/workflow, data/comparison, narrative/story, abstract/conceptual

## NEVER

- Force interactive format (HTML dashboard) when a static image suffices
- Re-select format on revision unless the user explicitly requests a different format
- Silently fall back to a different production skill on failure
- Produce multiple formats when only one was requested
- Skip the format recommendation step when the user has not specified a format
- Use concept-to-image for system architecture — use architecture-diagram instead
- Overproduction: do not animate what a static image communicates clearly

## SHOULD

- Identify key visual elements early: entities, relationships, hierarchy, emphasis points, temporal dimension
- Note explicit constraints from the request: format, dimensions, duration, branding
- Prepare skill invocations with concept description, styling guidance, and output specifications
- Distinguish revision types: content change vs. styling adjustment vs. format change
- Return absolute file paths for all produced assets
- Include format and dimensions/duration metadata with delivered assets
- Return all paths when multiple assets are produced (e.g., slides + exported PDF)
