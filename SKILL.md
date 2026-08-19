---
name: ip-as-logo-plus
description: Generate highly simplified personified IP mascot logos with flat-first geometry, rounded heavy forms, two IP colors plus one background color, and continuous-gradient neo-skeuomorphic micro-volume. Includes brand-inspired preset library (Tencent, Alibaba, ByteDance, Apple, etc.) for recognizable industry directions. Use when creating animal, creature, robot, ghost, plant, object, or character logos, or when the user asks for a logo in the style of a well-known company mascot.
---

# IP as Logo Plus

Create a **logo first**, character second. Reduce the subject to a compact symbol readable at `32 × 32`; do not produce a character illustration.

> **Plus enhancement:** When the user names a company, industry, or brand vibe, consult `references/brand-presets.md` for silhouette, color, and personality anchors. Always create an **original** mascot — never reproduce trademarked logos.

## Quick start

| User says | Agent does |
|-----------|------------|
| "腾讯风格的企鹅 logo" | Load Tencent preset → propose 3 treatments → 6 candidates |
| "做一个 fintech 吉祥物" | Load industry template → infer directions from product context |
| "参考 B 站小电视" | Load Bilibili preset as **style anchor only**, output original design |
| No subject given | Inspect repo README/docs → propose 3 IP metaphors tied to product |

## Workflow

1. Parse the request for an explicit IP subject, brand reference, or product context. Do not ask the user to choose a color mode unless they explicitly want to control it.
2. **If user mentions a known company or brand style**, read `references/brand-presets.md` and extract: silhouette cue, default palette, personality, and anti-patterns (what NOT to copy). Treat presets as **direction anchors**, not trace targets.
3. When the user has not specified an IP subject and the current workspace is a product repository, inspect relevant read-only context before asking questions. Prefer README, product docs, package metadata, landing copy, manifests, and design tokens.
4. When product context is insufficient, ask **one consolidated round** covering: what the product does, who it serves, and how it should feel. Do not start a second questionnaire.
5. Once context is sufficient, present **three concise directions** and propose **six independent logo candidates** in one batch. Do not generate until the user agrees, unless they already authorized six outputs.
6. Choose directions deliberately:
   - **Explicit IP subject:** three distinct treatments (composition, silhouette, secondary color region, personality).
   - **Brand reference given:** keep the brand's *category metaphor* (e.g., penguin = friendly social) but vary silhouette treatment; never clone trademark shapes.
   - **Open subject:** three genuinely different IP subjects tied to different product attributes.
7. Interpret user response:
   - Accept all three + six images → `A1`, `A2`, `B1`, `B2`, `C1`, `C2`
   - Select one direction + six images → `A1` through `A6`
   - User overrides → follow replacement instructions
8. Default every candidate to **three semantic colors**: two IP colors + one background. Follow user overrides when specified.
9. Determine available image-generation path before promising output. In Codex, use ImageGen when available. Else use any configured generator; if none, ask the user to enable one. **Never fabricate results.**
10. Parallelize six candidates via subagents when supported; otherwise separate generation calls. **Never compose a contact sheet or grid.**
11. If user supplies a background palette, reserve supplied colors for backgrounds unless stated otherwise. Keep two IP base colors distinct from background.
12. Inspect every output against evaluation rules. Retry with one targeted correction when practical. Report deviations honestly.
13. Preserve and label every result. Report: label, direction rationale, saved path, prompt/color mapping, dimensions, background mode, deviations. Ask which candidate to refine.

**Direction format:** `<IP subject> — <product/brand connection> — <defining silhouette>`

## Brand preset integration

When `references/brand-presets.md` applies:

1. Match company name (CN/EN/alias) to preset entry.
2. Use preset **silhouette vocabulary** and **OKLCH palette bands** as defaults.
3. Apply preset **personality adjectives** in the prompt skeleton.
4. Enforce preset **do-not-copy** list — reject outputs that reproduce trademark geometry.
5. If multiple presets fit (e.g., "腾讯游戏"), merge compatible cues; prefer the most specific entry.

For industry-only requests (no company named), use `references/industry-templates.md`.

## Complexity budget

- One dominant continuous outer silhouette from roughly `6–10` basic geometric shapes.
- At most **one** species-defining feature (pouch beak, curled horns, broad visor, etc.).
- At most **two** internal color regions. Face = two eyes + one mouth; omit eyebrows, highlights, nostrils, texture unless essential.
- Prefer head or compact upper-body crop. Do not explain full anatomy, costume, or story.
- Remove repeated feathers, scales, fur tufts, armor plates, buttons, screws, labels.
- Require readable black silhouette and recognizability at `32 × 32`.

## Shape language and composition

- Thick, rounded, weighty contours and broad color masses.
- Forbid sharp corners, pointed ears/beaks, needle tails, thin antennae, thin smiles, narrow gaps, acute tips. Blunt every necessary tip.
- Show **both** members of paired identifying features (ears, horns, wings, gills, bells).
- IP emerges from lower-left or lower-right, filling `75–85%` of canvas. Bottom/side crop intentional; do not crop paired identifiers.
- Keep artwork upright; never rotate without explicit request.

## Flat-first geometry, continuous-gradient micro-volume

- Flat semantic shapes first. Each IP color region = one continuous base shape with one outer silhouette.
- Depth via **one uninterrupted low-frequency diffuse gradient** per large region. Never as additional shape/layer/band.
- One shared light direction: upper-left → lower-right. Coherent across head, ears, body, secondary region.
- Each tonal transition spans ≥ `50%` of dominant form width. Local highlights broader than ~`20%` of form.
- Gradient stays inside semantic color family: OKLCH hue drift ≤ `3°`, chroma drift ≤ `0.015`, highlight L `+0.025–0.04`, shadow L `-0.03–0.05`, total peak-to-peak L variation ≤ `0.08`.
- Small facial marks nearly flat; same global illumination as parent region.
- Shallow contact darkening only as soft gradient continuation at region joins. No closed shadow blobs or AO seams.
- Background visually flat. No vignette, spotlight, or directional background gradient.
- Micro-volume visible at full res, nearly disappears at `32 × 32`.

## Color and canvas

- Default: **three semantic colors** — two IP base + one background.
- Two-color logo only when explicitly requested: one IP base + background, facial marks as negative-space cutouts.
- Prefer warm off-white (cream/parchment) over pure white; charcoal/deep navy over pure black.
- Prefer chromatic backgrounds with restrained saturation: terracotta, muted coral, dusty plum, sage, glaucous blue, ochre. Avoid neon/candy/primary intensity unless requested.
- OKLCH default bands:
  - chromatic mid-tone bg: `L 0.45–0.75`, `C 0.08–0.16`
  - dark chromatic bg: `L 0.18–0.35`, `C 0.05–0.14`
  - cream/parchment bg: `L 0.92–0.98`, `C 0.01–0.06`
- Contrast: ≥ `3:1` silhouette-to-background; ≥ `4.5:1` facial marks to surface beneath.
- Second IP color = one large continuous region (face mask, hat, shell, belly, visor). No scattered patches.
- Opaque edge-to-edge background by default. Preserve transparent results when generator returns them.
- Direct `1:1` square, ~`1536 × 1536`; accept native `1254 × 1254`. Never resample merely to hit target size.

## Prompt skeleton

### Route constraints by generator capability

Determine image model and schema from runtime metadata. Do not guess unsupported parameters.

- **Modern models** (GPT Image, Nano Banana Pro, Seedream 5.0 Pro): express exclusions as natural-language `Constraints:` in main prompt.
- **Legacy with `negative_prompt`:** deliver exclusions via dedicated parameter; omit duplicate `Constraints:` line.
- **Single-prompt legacy:** retain concise `Constraints:` line.
- Record model, constraint-delivery mode, and exact constraint text in generation report.

**Legacy negative prompt (adapt syntax as needed):**

```text
text, watermark, borders, frames, cards, App-icon masks, extra subjects, scenery, thin fragile lines, sharp tips, photorealistic materials, strong three-dimensional rendering, external cast shadows, trademark logos, existing brand marks
```

**Complete positive prompt:**

```text
Create one complete full-bleed 1:1 square IP mascot logo artwork.
Backdrop: cover the entire canvas with one visible, fully opaque solid <background>. Keep <background> clearly visible in all four square corners and every open area surrounding the mascot.
Subject: place one highly simplified <subject> mascot over the backdrop, reduced to one rounded continuous silhouette and one defining feature.
Brand direction (if applicable): <personality adjectives from preset>; inspired by <industry/category> but fully original — not a copy of any existing trademark.
Complexity: use 6–10 broad basic shapes, at most two internal color regions, and a face with two eyes and one mouth. Keep the symbol readable at 32 × 32.
Color count: use exactly three semantic colors in the complete artwork: two IP base colors plus the backdrop color. Reuse one IP color for facial marks and keep the second IP color in one large continuous region.
Color behavior: choose a softened but clearly chromatic backdrop, with warm off-white and charcoal or deep navy as preferred neutrals. Maintain silhouette-to-backdrop contrast of at least 3:1 and facial-detail contrast of at least 4.5:1. Treat continuous same-family tonal variation as modeling within each selected IP base color.
Composition: keep the mascot upright, emerging from the lower-left or lower-right, filling 75–85% of the square, with both paired identifying features visible.
Style: use Flat-first geometry with gentle continuous-gradient micro-volume. Apply one uninterrupted, low-frequency, same-family gradient inside each large IP color region, sharing one upper-left-to-lower-right light direction. Make each transition span at least 50% of the dominant form. Keep total OKLCH lightness variation at or below 0.08, hue drift within 3 degrees, and chroma drift within 0.015. Keep the backdrop visually uniform and let the tonal modeling become subtle at icon size.
Finish: show only the mascot over the full-canvas backdrop, with clean geometric surfaces and normal square outer corners.
Constraints: Use no text or watermark. Add no borders, frames, cards, or App-icon masks. Include one mascot only, with no extra subjects or scenery. Keep the contours thick and rounded, without fragile lines or sharp tips. Keep the finish graphic and softly dimensional, without photorealistic materials, strong three-dimensional rendering, or external cast shadows. Do not reproduce any existing company logo or trademark.
```

See `examples/prompts.md` for ready-made prompt variants.

## Mark as non-recommended when

- Reads as illustration rather than symbol; exceeds complexity budget; fails at small size.
- Wrong color count; second IP color scattered; shading introduces unrelated hue.
- Background color appears as painted IP region (unless negative-space cutout).
- Opaque chromatic background is neon/muddy; facial marks lack contrast.
- Thin, sharp, spiky, or fragile contours.
- Missing or cropped paired identifier.
- IP too small, sticker-centered, tilted, framed, or excessive empty space.
- Highlight/shadow has closed contour or readable shape instead of continuous gradient flow.
- Tonal modeling divides one color into stacked layers, bands, or flat swatches.
- Gradient changes direction between parts, transitions < 50% of form, or creates glossy hotspot.
- At `32 × 32`, tonal modeling reads as extra color region.
- Lacks gentle gradient modeling or becomes noticeably volumetric.
- Opaque background becomes scene, texture, halo, or strong gradient.
- **Reproduces recognizable trademark geometry** (Apple bite, Nike swoosh, Tencent penguin silhouette, etc.).

Background transparency alone is permitted. State exact findings for every candidate; never silently repair with code.

## Reference files

| File | Purpose |
|------|---------|
| `references/brand-presets.md` | 20+ company/industry mascot direction presets |
| `references/industry-templates.md` | Vertical-specific IP suggestions |
| `examples/prompts.md` | Copy-ready prompt examples (CN/EN) |
