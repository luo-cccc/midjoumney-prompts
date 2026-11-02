# Shared Visual System

Read this file with the selected workflow for character design, reference sheets, and new scenes. Style selection and visible rendering language apply to both engines; parameter presets are Midjourney-specific. For existing-scene variations and outpainting, preserve the supplied image's actual finish rather than applying a new default.

## Style selection and parameters

- The current request's explicit medium, visual style, and parameters take priority. Otherwise carry forward a style explicitly chosen by the user for the relevant character or world. Accepting a workflow default or attaching an image alone does not select its medium for a new image.
- When the user assigns another character's sheet as a style reference, extract its actual medium, stylization, form modeling, brushwork, material treatment, lighting, and color handling. Keep the target character's identity, anatomy, costume, and palette independent; transfer shared faction motifs or layout only when requested. If the image is unavailable, use confirmed textual art direction or the workflow default and state that visual matching awaits the reference.
- If no style was chosen, use the workflow's default: character concepts use semi-realistic anime painting; reference sheets use painted game-character concept art with CG-like volume as detailed in [reference-sheet.md](reference-sheet.md); new scenes use cinematic realistic 3DCG. Explicitly matching an image's finish overrides these defaults. Pure 3D rendering or animated-film CG requests select the CG sections below; game-character concept art alone does not imply photorealistic rendering.
- A painterly or anime-illustration request uses painting language. A named medium such as ink wash or watercolor uses that medium. These replace the workflow's default finish; do not append PBR, subsurface-scattering, or rendered-environment wording to a wholly painted image.
- Use one coherent medium unless the user explicitly asks for a blend. Within the default CG medium, idealized characters and more realistic environments are intentional and compatible; they do not require identical stylization.
- Default starting presets: anime-painted character portraits `--ar 3:4 --raw --s 150`; painted game-character reference sheets and CG scenes `--ar 16:9 --raw --s 150`. Explicitly requested CG portraits also start with `--ar 3:4 --raw --s 150`. User-specified values override these; the presets do not guarantee a medium or rendering method.
- For a non-default medium, keep confirmed `--raw` and `--s` values associated with that medium. If none exist, add neither; default anime-painted portraits and painted game-character sheets retain their presets above. Aspect ratio comes from the current workflow or current request, not a previous portrait.
- For revisions, keep the confirmed style unless asked to change it. An existing scene image assigned as the edit target establishes its actual medium, material treatment, and rendering finish. Preserve those during GPT Image 2 scene variations, including when they differ from the new-scene CG default. Changing time or weather can change lighting and color response without changing the medium. Scene editing and outpainting never become style conversions merely because these defaults changed.

## CG characters: when the selected medium is 3DCG

- Use premium animated-feature-film character design: anatomically grounded three-dimensional structure, idealized anime-influenced facial proportions, refined facial contours, and expressive living features.
- Describe a living character with continuous anatomy and natural skin response. Avoid physical doll joints, porcelain or glass-like skin, and toy materials. Keep facial refinement grounded in bone structure, soft tissue, and natural expression.
- Keep mature natural proportions for adults. Eyes have believable volume, detailed irises, and natural corneal reflections; expressiveness comes from design, not flat oversized anime eyes.
- Describe soft natural skin with subtle subsurface scattering, restrained microtexture and roughness variation, and gentle light transitions. Keep skin refined without waxy smoothing, plastic highlights, or documentary-style random facial defects.
- Use individually groomed hair strands organized into designed locks and a clear hairstyle silhouette.
- Make costume materials specific: woven cloth and fabric thickness, natural folds, leather grain and roughness, controlled metal reflections. Include only materials present in the actual design.
- A realistic environment does not turn the character into a live-action actor. Retain the confirmed face, proportions, and idealized character appeal.

Example finish clause, to adapt rather than paste mechanically:

> a premium semi-realistic 3D animated-film character, anatomically grounded with idealized anime-influenced facial proportions and refined natural facial contours, living skin with subtle subsurface scattering, expressive volumetric eyes, individually groomed hair strands, physically believable costume materials

## Environments: cinematic realistic 3DCG

- Use full-scale cinematic 3D environments with plausible construction, true object scale, material thickness, and layered spatial depth.
- Describe PBR-like material behavior through visible evidence: stone edge wear, timber grain, variable roughness, restrained metallic reflections, translucent foliage, or water response as relevant. Allow natural irregularity, repairs, weathering, and traces of use.
- Keep art-directed composition, architectural rhythm, visual paths, and color organization. Aim for an animated-feature-film environment or high-end game cutscene rather than an uncomposed documentary photograph.
- Keep skin terminology local to characters. Architecture, vegetation, and props retain their own physical materials instead of becoming dollhouse, plastic, ceramic, or anime-painted scenery.

Example finish clause:

> a cinematic realistic 3D environment at believable scale, structurally plausible architecture, physically based materials with natural roughness variation and weathering, coherent indirect illumination and layered atmospheric depth

## CG characters and environments in one frame

Describe the character and environment separately, then connect them with concrete shared conditions:

- One key-light direction, color temperature and intensity; compatible ambient fill, shadow direction, and falloff. Character skin, hair, and clothing receive environmental bounce light and local color spill.
- Shared PBR-like material responses, indirect illumination, reflection quality, and render finish. Skin may be more refined than stone without appearing to belong to a different rendering system.
- One exposure, white balance, contrast response, highlight handling, and filmic color grade. A focal character can stand out through composition and motivated lighting, not independent color processing.
- One camera position, perspective, lens treatment, scale, and depth-of-field progression. Feet, hands, garments, and props have believable contact, occlusion and contact shadows where they touch supporting surfaces.
- Distance-consistent haze, atmosphere, edge softness, and detail. Maintain comparable image quality and post-processing, without cutout outlines, separate sharpening, excessive bloom, or pasted-on figures.

Choose details relevant to the scene; do not recite every rendering term. For a wide view, prioritize recognizable silhouette, proportions and material response over invisible iris microdetail.

Example integration clause:

> the idealized 3D character retains her facial proportions in the realistic environment, both receiving warm key light from the left and cool ambient fill, environmental color bounce on skin and clothing, grounded contact shadows, consistent scale and perspective, shared exposure and filmic color grading

## Prompt discipline

Select a short subject-specific finish clause and, when needed, a short integration clause. Add them to the workflow's actual design and composition rather than copying this whole document. Technical terms describe a target appearance; they do not configure or prove a rendering engine, PBR pipeline, color space, or exact physical simulation in Midjourney.

Prefer positive visual descriptions. For Midjourney, use a short `--no` list only for concrete likely failures. For GPT Image 2, express needed exclusions in natural language with the correct scope. Never globally exclude needed people, heads, hair, or costume elements. Defaults and exclusions cannot guarantee identity, physical accuracy, or multi-view consistency.
