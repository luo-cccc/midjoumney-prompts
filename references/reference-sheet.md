# Character Reference Sheet

Use this workflow for a model sheet, turnaround, asset sheet, or multi-view presentation of one character. Read [visual-system.md](visual-system.md) for style priority and parameters.

This is the Midjourney sheet workflow. For GPT Image 2, follow [gpt-image-sheet.md](gpt-image-sheet.md), reusing the layout, body occupancy, and multi-view consistency rules here while applying that workflow's design-source and natural-language output rules.

## Direct generation from the supplied image

- Produce one English prompt for one complete sheet directly from the supplied portrait, extended image, or full-body image. Do not require a separate full-body generation, approval image, or per-view generation and compositing stage. Use an existing full-body reference if supplied, but do not make it a prerequisite.
- Extract the character's identity, visible head-neck-shoulder relationships, upper-body shape, costume construction and palette. Preserve the visible build and requested stylization rather than imposing a universal head count, tall silhouette, adult age or slender body.
- Complete unseen anatomy and costume conservatively, consistent with visible anatomy, established age, build and function. State briefly after the prompt what was inferred; do not claim exact recovery of hidden proportions. If exact measurements are requested but unsupported, explain the limitation without inventing them or automatically switching workflows.
- Separate anatomy from costume: a high belt, armor edge, high-waisted garment, robe hem or long image canvas is not a measurement of anatomical waist position, leg length or body height. Use this clarification in the finished prompt only when relevant to the reference.
- Keep the same underlying anatomy across views, with a neutral balanced stance and consistent weak perspective. Normalize the source pose and photographic foreshortening without redesigning body shape. Align corresponding neck-base, shoulder, waist, hip and knee levels, and the supporting feet or equivalent contact points.

## Layout and body occupancy

Default to a pure white 16:9 landscape canvas: left 55% for costume views, right 45% for portraits. Percentages guide layout; they are not exact placement guarantees.

### Left: three neck-to-foot costume views

- Arrange front, exact 90-degree side and back views side by side.
- Place each within an equally sized complete-figure presentation area that reserves the space its omitted head would occupy. Leave that upper space white, with a clean neck-level crop below it. The neck-to-foot figure retains its scale and position within the complete figure. Fit views by uniform scaling and spacing, not stretching the body upward into the omitted head space or narrowing it to fit columns.
- Show the collar or equivalent upper costume boundary, a short neck section, torso, arms, lower garments and footwear where applicable. Preserve garment length, trains and the design's relationship to feet; do not shorten clothing just to expose shoes.
- For these costume views only, hide hair and hair ornaments, including hanging locks, so shoulders and costume backs remain readable. Preserve capes, collars and all clothing layers. This is local display visibility, not a hairstyle change or anatomical cutaway.
- Default to relaxed shoulders, arms slightly separated from the torso and naturally formed empty hands. Adapt limb count, digits, stance and contact points to established anatomy, including nonhuman characters. User-requested poses and accessories override defaults.
- Repeat the same garment overlaps, structural seams, fastenings and accessory attachment points across angles. Honor explicit removals instead of restoring objects from the reference.

### Right: four enlarged portraits

- Use a precise 2x2 grid with narrow white gutters: frontal head-and-shoulders, 45-degree head-and-shoulders, exact 90-degree side profile, and closer frontal facial portrait.
- Preserve intrinsic head, neck and shoulder relationships; only display magnification changes. Keep face identity, features, skin tone, hairstyle and identifying accessories consistent, framed appropriately for each view.
- Use a composed neutral expression unless the user specifies another. Adapt framing to the design rather than prescribing a fixed face-to-chest ratio or a universal long-hair crop.
- Portraits are intentionally enlarged. Do not compare their on-page pixel size with the left bodies to calculate head count, and do not require matching on-page head sizes across sections.

## Dynamic character description

Describe only the particular reference's actual or established features:

1. Face and visible anatomy: age cues, face shape, eyes, skin tone and distinctive features.
2. Hair or equivalent silhouette: color, structure, arrangement and identifying ornaments, where present.
3. Costume: major layers, neckline, shoulder volume, waist construction, lower garments, fastenings and accessories.
4. Palette and materials actually present, with matching ornament placement and structural logic across angles.

Do not transfer example-specific traits or materials to other characters. A separate style or layout reference supplies only its assigned role. Complete hidden backs and footwear with necessary functional structure rather than new decorative focal points; generated additions remain inferred until adopted.

## Default finish

Use high-end semi-realistic game character concept art, digitally painted with convincing three-dimensional form and a refined CG-like finish. Use clearly modeled facial planes and softly blended natural tones, distinct hair locks with controlled highlights where appropriate, readable material structure, painterly surface detail and selectively sharp edges. Differentiate only materials present, with restrained material-specific highlights. Use neutral slightly cool studio illumination, coherent light-and-shadow separation and subtle ground contact shadows.

This is a painted finish with dimensional modeling, not a requirement for photorealistic 3D rendering or skin shaders. Do not append PBR or subsurface-scattering terms to this default. Explicit media such as ink wash, watercolor or pure 3DCG replace it according to the shared style rules. Preserve character proportions while changing presentation lighting or finish.

## Assembly and output

Use this order: reference identity and visible proportion anchor; conservative completion and any relevant costume/anatomy distinction; overall canvas; left occupancy and views; right portraits; character-specific face and costume; finish; parameters. Write the occupancy and intrinsic-proportion controls in the final prompt, not just in analysis. Avoid repeating anatomical assurances or lengthy decorative lists.

The following is an assembly scaffold, not a prompt to paste unchanged. Replace bracketed fields from the current reference, omit inapplicable features, and deliver a complete copy-ready prompt without placeholders:

```text
A professional character reference sheet of [character] in the supplied [portrait / extended image / full-body reference]. Preserve [identity, visible head-neck-shoulder relationships, build, costume and palette]. Complete unseen anatomy conservatively, consistent with the visible figure and established character design.

Pure white background, 16:9 landscape canvas: left 55% costume views, right 45% portraits.

LEFT: front, exact 90-degree side and back neck-to-foot costume views. Place each in an equally sized complete-figure presentation area, leaving white space for the omitted head above the neck crop. Retain the body's scale within the complete character. Fit views by uniform scaling and spacing, preserving width-to-height relationships. Hide hair and hair ornaments only in these costume views; preserve clothing layers. [Character-appropriate neutral stance and complete anatomy.] Consistent weak perspective, corresponding anatomical levels and one shared contact baseline.

RIGHT: a 2x2 portrait grid, frontal, 45-degree, exact side profile and closer frontal facial portrait. Preserve the same intrinsic head, neck and shoulder relationships; only display magnification changes. Frame identifying features appropriately.

[Reference-specific face, hair, costume construction, palette and materials. Conservative completion of hidden design details, consistently repeated across views.]

[Selected finish and lighting.] --ar 16:9 --raw --s 150 --no text, labels, logos, watermarks
```

Default parameters: `--ar 16:9 --raw --s 150`. User choices override them; explicitly selected alternative media follow shared parameter rules. Keep people, heads, hair and necessary costume elements out of global `--no`. Add only relevant concrete exclusions requested by the user or likely to prevent a material failure.

After the prompt, briefly identify inferred anatomy or costume and how to attach the supplied reference. Do not add a full-body approval checkpoint, fixed measurement claims or promises of exact identity, proportion and layout fidelity. Corrections to an individual result remain local unless the user requests a general rule.
