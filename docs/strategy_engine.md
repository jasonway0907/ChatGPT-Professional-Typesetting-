# Strategy Engine Specification

The Strategy Engine fuses marketing intent, visual psychology, and audience psychology into actionable layout directives. It is deterministic: given parsed intents and visual features, it should produce repeatable strategy outputs that justify each design decision.

## Inputs
- Marketing intent: goal, funnel stage, CTA strength, brand constraints, required copy tone.
- Audience profile: segment (student, advertising designer, visual novice), age band, preferences, risk tolerance.
- Visual features: subject position, color palette, luminance range, composition analysis, mood scores.
- Style preferences: requested style tags (minimal, editorial, playful), brand kit options.

## Outputs
- Layout weights: text vs. imagery ratio, focal element priority, CTA prominence.
- Flow model: preferred scan path (Z, F, Gutenberg) and anchor points.
- Spatial rules: positioning guidance (thirds, golden ratio bands), whitespace targets, alignment constraints.
- Color and type strategy: palette bias, contrast requirements, typography tiers.
- Rationale: bullet-point explanations tied to marketing and psychology principles.
- References: sources that support the chosen patterns (e.g., Nielsen Norman, Gestalt, AIGA, Material Design ratios).

## Decision Heuristics
### Marketing Mapping
- Enrollment/education → trust-first: include instructor/authority imagery, curriculum highlights, and a confident CTA.
- Promotion/discount → urgency-first: high-contrast price badge, short headline, CTA in primary scan path.
- Brand/awareness → consistency-first: brand color dominance, reduced decoration, higher whitespace.

### Visual Psychology
- **Z-pattern** for balanced hero sections guiding attention to CTA.
- **F-pattern** for information-dense layouts where scanning begins top-left and descends.
- **Gutenberg** when distributing weight evenly for modular grids.
- **Rule of Thirds / Golden Ratio** to place primary subjects or CTAs at strong focal points.
- **Visual hierarchy tiers** (1 = CTA/headline, 2 = hero image, 3 = supporting details).

### Audience Differentiation
- **Students:** emphasize clarity, modularity (achievement/reflective modules), and generous whitespace; prefer 1:1 or text-forward ratios.
- **Advertising designers:** allow higher variance and style-forward choices, expose rationale, and provide multiple layout variants or moodboard hooks.
- **Visual novices:** lock to safe presets, low color complexity, bold CTA and headlines, reduced content density.

## Rationale and Traceability
Every directive must include:
- The principle applied (e.g., "Z-pattern guides eye to CTA").
- The marketing or audience need it satisfies (e.g., "MOF conversion → CTA priority").
- The visual or psychological rule invoked (e.g., "Rule of Thirds"), with an optional reference link.

## Example Output Skeleton
```json
{
  "layout": "hero_left_z_flow",
  "strategy": {
    "marketing_goal": "increase CTR",
    "funnel_stage": "MOF",
    "visual_psychology": [
      "Z-pattern guides eye to CTA",
      "Rule of Thirds for hero placement",
      "High contrast CTA for conversion"
    ],
    "audience": "visual novice",
    "rationale": [
      "Visual novice → safer Z layout with generous whitespace",
      "High contrast CTA to reduce decision friction",
      "Hero aligned to upper-left third for immediate focus"
    ],
    "references": [
      "Nielsen Norman Group – F/Z-pattern behaviors",
      "AIGA layout best practices",
      "Gestalt proximity/similarity"
    ]
  },
  "canva": { "schema_version": "1.0", "elements": [] }
}
```
