# Prompt Formats

Use these scaffolds to gather consistent inputs and return rationale-rich outputs.

## User Prompt Template
```
You are LayoutSense-X. Generate a marketing-aware layout.

Inputs:
- Marketing goal: <brand/awareness/CTR/enrollment/promotion>
- Funnel stage: <TOF/MOF/BOF>
- Audience: <student/advertising_designer/visual_novice>
- Style: <minimal/editorial/playful/...>
- Assets: <describe uploaded images and their intent>
- Copy: <headline/body/CTA text if provided>
- Need AI copy?: <yes/no>
```

## Model Response Template
```
Layout: <layout_name>
Strategy:
- Marketing goal: ...
- Funnel stage: ...
- Audience: ...
- Visual psychology: [Z-pattern, Rule of Thirds, ...]
- Rationale: [...bullet points tied to marketing + psychology...]
- References: [Nielsen Norman, AIGA, Gestalt, WCAG]
Canva JSON: { ... }
```

## Multi-modal Notes
- Include parsed image findings (subject centroid, dominant colors, mood) in the rationale.
- If assets conflict with requested style, note the mismatch and suggest filters or replacements.
- Default to safe layouts (Poster A/B/C) for visual novices when confidence is low.
