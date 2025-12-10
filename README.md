# LayoutSense-X

LayoutSense-X is a multi-modal, marketing-aware layout system that acts like a visual ChatGPT plus a strategist and a Canva-ready layout generator. It explains why each decision works, cites design references, and adapts layouts for different audiences such as students, advertising designers, and visual novices.

## Key Capabilities
- **Multi-modal understanding:** Ingest text, user-uploaded images, and reference layouts to extract marketing intent and visual cues.
- **Strategy-first generation:** Couples marketing goals, audience psychology, and visual design heuristics before drawing any boxes or grids.
- **Reasoned outputs:** Every layout includes the underlying rationale, visual psychology cues, and references (e.g., Nielsen Norman reading patterns, Gestalt principles, Golden Ratio).
- **Canva-ready:** Produces a structured JSON schema that can be ingested by Canva-like editors for immediate editing.

## System Layers
1. **Input Layer** – Accepts copy, images (logo, product, portraits), and prior references, deriving marketing semantics and asset traits.
2. **Intent Parser** – Extracts marketing goals, funnel stage, target audience, style cues, and CTA intensity to guide strategy.
3. **Vision Encoder** – Analyzes subject placement, color bias, tonal range, composition (rule of thirds, visual gravity), and mood to inform layout and styling.
4. **Strategy Engine** – Merges marketing strategy, visual psychology (Z/F/Gutenberg flows, hierarchy), and audience psychology into weighted layout directives.
5. **Layout Generator** – Builds grids, slot weights, alignment, spacing, and CTA placement based on strategy outputs.
6. **Style Composer** – Selects typography, color palettes, backgrounds, decorative density, and filters to reinforce the strategy.
7. **Output Layer** – Emits layout + rationale + references along with a Canva-compatible JSON payload.

## Audience-specific Modes
- **Students (learning portfolios):** Modular information blocks, generous whitespace, 1:1 or text-forward ratio, and clear headline hierarchy to highlight achievements.
- **Advertising designers:** Style-consistent, high-editability layouts, moodboard support, and explicit strategic reasoning for critique.
- **Visual novices:** Safe layout presets, low complexity palettes, bold CTA and headings, and reduced information density.

## Repository Structure
- `docs/` – Formal architecture, strategy engine specs, design principles, prompt formats, and Canva schema definition.
- `examples/` – Sample outputs for each audience mode with rationale and Canva-like payloads.

## Getting Started
This repository currently provides implementation-ready specifications. Use the docs to wire your preferred LLM/VLM stack, then plug the generated Canva schema into your editor runtime.

- Read `docs/architecture.md` for the end-to-end system blueprint.
- Implement the logic in `docs/strategy_engine.md` to keep outputs strategy-driven.
- Follow `docs/canva_schema.md` for the target JSON contract.
- Explore `examples/` to see how reasoning and schema appear together for different audiences.
