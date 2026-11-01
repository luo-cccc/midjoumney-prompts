# Character Reference Sheet

Use this workflow for a professional character model sheet, turnaround, asset sheet, or multi-view presentation that must preserve one character's identity. Read [visual-system.md](visual-system.md) for style priority and parameter rules.

## Default layout

Use a clean 16:9 landscape canvas, pure white background, and two clearly separated sections. Reserve approximately 55% of the width for costume turnarounds on the left and 45% for portraits on the right. Separate portrait panels with narrow white gutters.

### Left section: neck-down costume turnaround

- Arrange front, exact 90-degree side, and back full-body costume views side by side.
- Begin each figure at a clean horizontal crop through the neck, showing the collar and a short neck section with white space above. Confine all heads, hair and hair ornaments to the portrait section so the shoulders and costume back remain unobstructed. This is a presentation crop, not an anatomical cutaway.
- Describe this positively in the prompt: "three neck-down costume views, each beginning at a clean neck-level crop, with collars and the complete costume back clearly visible; all hairstyles appear only in the portrait panels". Do not put head or hair in `--no`, because it applies to the entire image.
- Show the complete torso, arms, hands, lower garments, hems and footwear. Use the same figure height, body proportions and scale, with feet on one horizontal baseline.
- Preserve the character's garment lengths, silhouette and relationship to footwear. Make costume boundaries readable without redesigning hems, trains or shoes to fit the presentation.
- Use relaxed arms slightly separated from the torso, empty hands and five naturally formed fingers per hand.
- Keep collars, shoulder layers, closures, waist wrapping, embroidery, sleeve construction and garment overlaps consistent across angles. Preserve any user-requested removal of weapons or accessories rather than restoring them from an identity reference.

### Right section: 2x2 portrait grid

- Top left: frontal head-and-shoulders portrait.
- Top right: approximately 45-degree head-and-shoulders portrait.
- Bottom left: exact 90-degree side profile showing the nose, jaw, ear and hairstyle.
- Bottom right: closer frontal facial portrait, differentiated from the top-left head-and-shoulders view.
- Fit each view to its purpose while preserving the hairstyle silhouette and identity-defining accessories. Adapt framing to the character's actual design rather than imposing a fixed face-to-chest ratio or a rule for cropping long hair.
- Maintain identical face shape, features, skin tone, hairstyle, hair color and accessories. Use a neutral expression by default, or preserve an explicitly requested expression.

## Default finish: painted game-character concept art

- Use high-end semi-realistic game character concept art, digitally painted with convincing three-dimensional form and a refined CG-like finish. The volume comes from painted light and shadow, not a mandatory photorealistic 3D rendering pipeline.
- Model facial planes clearly around the eyes, nose, cheeks and jaw, with softly blended natural skin tones and restrained variation. Keep eyes, lips and facial identity precise without waxy smoothing or doll-like facial design.
- Organize hair into distinct flowing locks with broad controlled highlights and selective fine strands rather than uniform strand-by-strand detail.
- Use readable form, controlled painted edges and visible brush texture where appropriate. Adapt folds, surface detail and decorative density to the actual materials and costume design; rigid armor, soft cloth and richly ornamented clothing need different treatment.
- Differentiate only materials actually present: restrained silk sheen, cloth thickness, leather roughness or controlled metal reflections. Preserve the character's own palette and costume; a style or layout reference does not supply unrelated character traits, costume elements or accessories.
- Concentrate crisp detail on the face, hair silhouette, collar and costume construction; soften less important painted transitions. Use neutral slightly cool studio illumination with clear light-and-shadow separation, restrained highlights and subtle floor contact shadows. Keep light consistent across panels rather than carrying over a dramatic portrait's rim light.
- Explicitly chosen media such as watercolor, ink wash or pure 3DCG override this default finish while retaining the requested layout. Do not append skin-shader, PBR or subsurface-scattering language to the default painted finish.

Example finish clause, adapted to the actual character:

> high-end semi-realistic game character concept art, digitally painted with convincing three-dimensional form, clearly modeled facial planes and softly blended skin tones, distinct hair locks with controlled highlights, readable material structure and painterly surface detail adapted to the costume, selectively sharp edges, neutral slightly cool studio illumination

## Identity and output

- Use the character image for face, hairstyle, costume and colors. If a separate reference specifies layout or finish, state its role and transfer only those qualities.
- When lower garments, shoes or back construction are undefined, infer them conservatively from established materials and function, repeat them consistently across views, and briefly state which details were inferred.
- Distinguish confirmed design from inferred details. Reuse a generated sheet as the design authority only when the user adopts it; displaying a result for review does not approve its additions. Carry confirmed details forward and keep unsupported additions provisional.
- Treat feedback on an individual result as a correction for that result. Do not turn its costume, expression, accessory or cropping fixes into universal defaults without an explicit request to standardize them.
- Include only the specified character. Put text, labels, logos and watermarks in `--no`; keep people, heads and hair out of it. Add concrete exclusions requested by the user when needed.

Write one coherent English prompt unless the user requests another language or segmented prompts. Put the layout before long character and finish descriptions so the neck-down crop and portrait grid remain prominent. Default parameters: `--ar 16:9 --raw --s 150`. Preserve user-specified values; for explicitly selected alternative media, follow the shared parameter rules. View counts and width percentages guide composition but do not guarantee exact placement.
