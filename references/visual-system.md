# Shared Visual System

Read this file with the selected workflow for character design, reference sheets, and new scenes. Style selection and visible rendering language apply to both engines; parameter presets are Midjourney-specific. For existing-scene variations and outpainting, preserve the supplied image's actual finish rather than applying a new default.

Every new image defaults to one unified semi-realistic 3DCG system with next-generation game-cinematic and commercial-animation production values. Characters are refined and stylized; environments are naturalistic and physically grounded. Both rest on the same art direction, rendering logic, material system, lighting behavior, color management, and cinematic post-processing. Different visual treatment is intended; looking like two different worlds is not.

## Style selection and parameters

- The current request's explicit medium, visual style, and parameters take priority. Otherwise carry forward a style explicitly chosen by the user for the relevant character or world. Accepting a workflow default or attaching an image alone does not select its medium for a new image.
- When the user assigns another character's sheet as a style reference, extract its actual medium, stylization, form modeling, brushwork, material treatment, lighting, and color handling. Keep the target character's identity, anatomy, costume, and palette independent; transfer shared faction motifs or layout only when requested. If the image is unavailable, use confirmed textual art direction or the workflow default and state that visual matching awaits the reference.
- If no style was chosen, use the unified 3DCG system below for character concepts, reference sheets, and new scenes. Explicitly matching an image's finish overrides it.
- An explicitly requested painting, anime illustration, or named medium such as ink wash or watercolor replaces the 3DCG default for that image. Use that medium's own language, and do not append PBR, subsurface-scattering, or global-illumination wording to a wholly painted image.
- Use one coherent medium unless the user explicitly asks for a blend. Within the 3DCG default, refined characters and more naturalistic environments are intentional and compatible; they do not require identical stylization.
- Default starting presets: character portraits `--ar 3:4 --raw --s 150`; reference sheets and scenes `--ar 16:9 --raw --s 150`. User-specified values override these; the presets do not guarantee a medium or rendering method.
- `--s` accepts 0-1000 and defaults to 100, so the preset 150 is a mild push toward art-directed interpretation. `--raw` is supported from V5.1. For an explicitly requested non-default medium, keep confirmed `--raw` and `--s` values associated with that medium, and add neither when none exist. Aspect ratio comes from the current workflow or current request, not a previous portrait.
- On V8.1 and V8.2, `--hd` renders 2048px instead of standard resolution, which suits reference sheets and wide scenes where fine material and facial detail matter. It caps aspect ratio at 4:1 and costs more GPU time, and Midjourney's inpainting and outpainting downscale their results to standard resolution. Add it only when the user wants the higher resolution. It is a generation parameter, not an upgrade switch for an image that already exists: rerunning a prompt with `--hd` returns a new image whose details differ, so say that rather than implying the same image at higher resolution. Confirm the user's model version instead of assuming V8.1 or V8.2.
- `--niji 7` or `--niji 6` selects Midjourney's anime model. It replaces this 3DCG system instead of combining with it, so use it only on an explicit request and drop the CG rendering clauses when you do.
- In V8.2 the Edit Model replaced Character Reference and Omni Reference, so do not add `--cref` or `--oref`.
- For revisions, keep the confirmed style unless asked to change it. An existing scene image assigned as the edit target establishes its actual medium, material treatment, and rendering finish. Preserve those during GPT Image 2 scene variations, including when they differ from this default. Changing time or weather can change lighting and color response without changing the medium. Scene editing and outpainting never become style conversions merely because these defaults changed.

## Characters: refined semi-realistic 3DCG

- Use premium character-asset quality: sculptural three-dimensional form, art-directed body proportions, and commercial-grade character design.
- Build the face on real bone and muscle logic, then refine it with coherent anime-informed features. Keep mature natural proportions for adults.
- Borrow surface craft from high-grade ball-jointed-doll work: clean sculpting, resin-like translucency blended with living skin, natural subsurface scattering, soft light transitions, and restrained microtexture. Never give a living character mechanical joints, seams, rigid plastic, wax, or toy materials.
- Eyes have detailed iris structure, real optical depth, and natural corneal highlights, without flat oversized cartoon eyes.
- Use individually groomed hair strands organized into designed locks, with highlights that follow the image's key light.
- Make costume materials specific: cloth thickness and weave, natural folds, embroidery, leather grain, jade or stone, controlled metal reflections. Include only materials present in the actual design.
- A character may be more refined and stylized than the environment, but keeps believable volume, lighting response, and physical material behavior. A realistic environment does not turn the character into a live-action actor.

Example finish clause, to adapt rather than paste mechanically:

> a premium semi-realistic 3DCG character with sculptural form and art-directed proportions, anatomically grounded facial structure refined toward coherent anime-informed features, BJD-grade surface refinement with resin-like translucency over living skin and natural subsurface scattering, volumetric eyes with detailed irises and natural corneal reflections, individually groomed hair locks, physically believable costume materials

## Environments: naturalistic next-generation 3DCG

- Use full-scale cinematic 3D environments with plausible construction, true object scale, material thickness, and layered spatial depth.
- Do not give the environment the character's doll-grade finish. Architecture, rock, timber, vegetation, water, ground, sky, cloud, and interior furnishing keep their own physical material behavior.
- Describe PBR-like behavior through visible evidence: stone edge wear and roughness variation, timber grain depth, controlled metallic reflections, translucent foliage, or water response as relevant. Allow natural irregularity, repairs, weathering, and traces of use.
- Keep art-directed composition, architectural rhythm, visual paths, and color organization, with detail density controlled across foreground, midground, and background. Aim for a high-budget game cutscene or animated feature rather than an uncomposed documentary photograph or a photographic backdrop.
- The environment may be more naturalistic than the character while holding the same CG rendering quality, color handling, and light logic.

Example finish clause:

> a naturalistic next-generation 3D environment at believable scale, structurally plausible architecture, physically based materials with natural roughness variation and weathering, coherent global and indirect illumination, controlled detail density and layered atmospheric depth

## Characters and environments in one frame

Describe the character and environment separately, then connect them with concrete shared conditions:

- One rendering base: PBR-like materials, global and indirect illumination, real reflection behavior, ambient occlusion, and natural shadows.
- One key-light direction, intensity, and color temperature, with compatible ambient fill, shadow direction, softness, and falloff. Skin, hair, costume, and accessories receive environmental bounce light and local color spill, with reflection and shadow colors adjusted to the surroundings. No independent character lighting, no warm character against a cool environment, no bright character in a dark scene.
- Shared material response and render finish. Skin may carry finer detail and local highlights than stone, as long as highlight strength, reflection logic, and gloss obey the scene's lighting.
- One exposure, white balance, contrast response, black-and-white point relationship, highlight handling, and filmic grade. A focal character stands out through composition and motivated lighting, not separate color processing.
- One camera position, perspective, focal-length logic, scale, and depth-of-field progression. Feet, hands, garments, and props have believable contact, occlusion, and contact shadows where they touch supporting surfaces. The character occupies the space instead of sitting on the background like pasted artwork.
- Distance-consistent haze, atmosphere, edge softness, and detail falloff. A character may be sharper than the background without cutout outlines, separate sharpening, or a floating silhouette. Do not blur the environment heavily to hide a mismatch.
- One weather, time of day, and air condition for character and scene alike.

Choose details relevant to the scene; do not recite every rendering term. For a wide view, prioritize recognizable silhouette, proportions, and material response over invisible iris microdetail.

Example integration clause:

> the refined 3D character retains her facial proportions within the naturalistic environment, both lit by one warm key light from the left with cool ambient fill, environmental color bounce on skin and clothing, grounded contact shadows, consistent scale and perspective, shared exposure and filmic color grading

## Prompt discipline

Select a short subject-specific finish clause and, when needed, a short integration clause. Add them to the workflow's actual design and composition rather than copying this whole document. Technical terms describe a target appearance; they do not configure or prove a rendering engine, PBR pipeline, color space, or exact physical simulation in Midjourney.

Prefer positive visual descriptions. State the wanted skin, material, and grounding qualities in the prompt body; that carries more weight here than a long exclusion list.

For Midjourney, use a short `--no` list only for concrete likely failures. Because `--no` reads each word separately, keep entries to single words that the image never needs: `plastic, waxy, low-poly, cutout, collage`. Do not write `doll`, `skin`, `figure`, or `seams` into `--no` under this system: `doll` fights the intended BJD-grade refinement, `skin` and `figure` negate the subject, and `seams` cancels the garment seams a sheet must repeat across views. Adjust per image, and drop an entry when the design actually calls for that material.

For GPT Image 2, express needed exclusions in natural language with the correct scope. Never globally exclude needed people, heads, hair, or costume elements, and keep clothing words out of `--no`. Defaults and exclusions cannot guarantee identity, physical accuracy, or multi-view consistency.
