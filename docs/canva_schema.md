# Canva-Compatible Schema

The output JSON should be directly ingestible by Canva-like editors. Keep fields explicit and traceable.

## Top-level Structure
```json
{
  "schema_version": "1.0",
  "layout": "hero_left_z_flow",
  "canvas": { "width": 1080, "height": 1920, "units": "px" },
  "elements": [ ... ],
  "strategy": { ... }
}
```

## Element Fields
- `id`: stable identifier.
- `type`: `text` | `image` | `shape` | `cta` | `background`.
- `content`: text string or asset reference.
- `position`: `{ "x": <number>, "y": <number>, "relative": "canvas|parent" }`.
- `size`: `{ "width": <number>, "height": <number>, "unit": "px|%" }`.
- `alignment`: `left|center|right|justify`.
- `style`: typography, color, opacity, filters.
- `z_index`: stacking order.
- `constraints`: e.g., `thirds_anchor`, `golden_ratio_band`, `scan_path_anchor` for traceability.

## Strategy Payload
Embed the rationale to keep traceability beside the layout.
```json
"strategy": {
  "marketing_goal": "increase CTR",
  "funnel_stage": "MOF",
  "visual_psychology": ["Z-pattern", "Rule of Thirds"],
  "audience": "visual novice",
  "rationale": [
    "Z-pattern guides eye to CTA",
    "Hero aligned to upper-left third",
    "High contrast CTA for conversion"
  ],
  "references": ["Nielsen Norman", "AIGA", "Gestalt"]
}
```

## Validation Guidelines
- Enforce element-level `constraints` to mirror strategy decisions.
- Validate contrast ratios for text/CTA per WCAG AA.
- Reject layouts where CTA is not on the primary scan path for MOF/BOF goals.
- Ensure `schema_version` bumps when adding required fields.
