# Architecture

LayoutSense-X combines multi-modal understanding with marketing-aware layout generation. The pipeline is organized into layered components so engineering teams can swap models while preserving the strategy contract.

## Layer Overview
1. **Input Layer**
   - Accepts: user text briefs, images (logo, product, people, illustration), and reference layouts.
   - Derives: marketing semantics, visual syntax, asset traits, and provisional audience hints.

2. **Intent Parser (Marketing Semantic Extraction)**
   - Extracts marketing goal (brand, exposure, CTR, enrollment, conversion, etc.).
   - Identifies funnel stage (TOF/MOF/BOF), target audience (students, parents, designers, novices, age bands), style cues, CTA intensity, and whether AI copy is needed.
   - Produces weighted strategy signals that guide downstream layout rules.

3. **Vision Encoder (Multi-modal Analyzer)**
   - Detects subject position, bounding boxes, background complexity.
   - Measures color tendency, luminance, saturation, and composition (rule of thirds, visual gravity points).
   - Rates mood and style fit against requested design direction.

4. **Strategy Engine (Marketing × Visual Psychology × Audience)**
   - Marketing inference: maps goals to layout needs (e.g., enrollment → trust → highlight instructor, syllabus, CTA; promotion → price emphasis → contrast blocks and strong type).
   - Visual psychology: Z/F/Gutenberg scanning patterns, visual hierarchy, golden ratio/thirds positioning, color psychology.
   - Audience psychology: adjusts density, risk tolerance, and novelty per audience (students, advertising designers, visual novices).
   - Outputs: prioritized layout directives (weights for text/image, CTA prominence, whitespace targets, alignment rules, color constraints).

5. **Layout Generator**
   - Builds grid definitions, slot sizing/weights, alignment, spacing, and CTA placement using Strategy Engine directives.
   - Attaches rationale traces so each slot has a why behind its position and scale.

6. **Style Composer**
   - Selects typography sets, color palettes, backgrounds, decorative density, and image filters aligned to the strategy.

7. **Output Layer**
   - Returns: (a) structured layout rationale, (b) visual psychology + marketing explanations, (c) references, and (d) a Canva-compatible JSON schema ready for downstream editors.

## Data Flow
- User inputs → Intent Parser + Vision Encoder.
- Parsed intents + visual features → Strategy Engine.
- Strategy directives → Layout Generator + Style Composer.
- Final payload → Output Layer with rationale + Canva schema.

## Implementation Notes
- Keep strategy outputs explicit; avoid template-only generation.
- Ensure Vision Encoder signals are accessible to the Strategy Engine (e.g., dominant hue, subject centroid, complexity scores).
- Provide deterministic fallback presets for visual novices to avoid failure-prone creative outputs.
