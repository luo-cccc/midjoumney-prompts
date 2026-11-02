---
name: midjourney-prompts
description: Create and refine ready-to-use Midjourney prompts for characters, reference sheets, initial scene bases, and controlled outpainting. Create GPT Image 2 prompts for direct minor-character sheets with main-character style references and for consistent scene variations from existing base images. Use for prompt text, not image generation.
---

# Midjourney Prompt Studio

Turn the user's concept or reference image into a concise, copy-ready image prompt while preserving explicit visual choices and identity details. Use Midjourney by default, including the first scene base, with GPT Image 2 for direct minor-character sheets and subsequent scene variations from an established image. Default character portraits to semi-realistic anime painting, reference sheets to painted game-character concept art with CG-like volume, and new scenes to cinematic realistic 3DCG environments. An explicitly assigned style reference overrides the default finish; scene edits preserve the target image's actual finish.

## Select the workflow

Honor the user's explicitly requested engine and output first. For a new character explicitly described as minor or non-key, default to a GPT Image 2 reference-sheet prompt directly from the concept; do not infer importance from occupation, race, age, or appearance. An explicit portrait or Midjourney request overrides this default. New scene bases default to Midjourney; variations of an existing scene image default to GPT Image 2. Revising an unrendered scene prompt stays in the initial-design workflow.

For character designs, reference sheets, and new scenes, read [references/visual-system.md](references/visual-system.md) for shared style selection, rendering language, and integration. Its parameter presets apply only to Midjourney. For existing-scene variations and outpainting, use the source image's actual style instead of applying new-image defaults.

- For a GPT Image 2 character reference sheet, including direct minor-character design from text with a main-character style reference, read [references/gpt-image-sheet.md](references/gpt-image-sheet.md). Reuse the linked character-design decisions and sheet layout, not their Midjourney syntax or portrait defaults.
- For other character concepts such as a race, profession, archetype, or costume idea, read [references/character-design.md](references/character-design.md).
- For a Midjourney character model sheet, turnaround, asset sheet, multiple consistent views, or head/body breakdown, read [references/reference-sheet.md](references/reference-sheet.md).
- For GPT Image 2 variations of an existing scene image, including changes to time, weather, season, characters, props, or explicitly requested viewpoint and frame extensions, read [references/gpt-image-scene.md](references/gpt-image-scene.md). This is the default for existing-scene changes when no other engine is requested.
- For the first scene base, a new environment, location, or background, revisions before a scene image exists, or explicitly requested Midjourney scene revisions, read [references/scene-design.md](references/scene-design.md).
- For extending a supplied image or completing cropped anatomy, costume, props, or background, read [references/outpainting.md](references/outpainting.md).
- If the request spans modes, read each relevant reference and keep one consistent character design across all prompts.

## Prompt rules

1. Write concrete visual descriptions rather than a pile of isolated quality tags. Midjourney prompts default to English. GPT Image 2 prompts use the user's requested language, otherwise the language of the request.
2. For Midjourney prompts for new images, describe what should appear rather than writing "no" or "without" in the prompt text; Midjourney may still draw the negated item. Put concrete unwanted items in `--no` as a short comma-separated list. Keep clothing words out of `--no`, because moderation reads each word separately (`--no modern clothing` becomes "no modern" and "no clothing" and can trigger a warning); describe the wanted clothing instead. For GPT Image 2, write needed exclusions and local visibility rules in natural language instead of Midjourney flags.
3. Preserve explicit user choices, identity details, requested canvas shape, and confirmed revisions. Workflow defaults apply only when the user has not specified otherwise. Keep revisions focused on the requested changes.
4. Infer missing design details only when they support the stated character or world. For sheets from the target character's own image, preserve visible proportion relationships and complete hidden anatomy conservatively. For direct concept sheets, design the new character from the text; another character's style reference is not its identity source. Follow the selected sheet workflow without requiring a separate portrait, approval image, or per-view generation. When a scene requires body parts outside an existing portrait, follow the scene workflow's costume-completion rules; outpainting follows its own crop limits.
5. Assign references their requested roles: target identity, visual style, layout, or scene edit target. A main-character sheet used for style does not supply the new character's face, costume, or exclusive palette. A scene edit target supplies the established place's spatial structure and actual finish; a style-only image does not establish the same location. For new images, follow the shared visual system's style selection; attaching a character image alone does not request its medium. Preserve the original finish during scene edits and outpainting unless explicitly asked to restyle it.
6. Put the finished prompt in a fenced code block so it is easy to copy. Add analysis or layout guidance only when requested by the workflow or by the user.
7. Produce prompt text only. Do not generate an image unless the user separately asks for one.

For Midjourney, use the parameters requested by its workflow and `--no` as described in rule 2. For GPT Image 2, translate composition and constraints into natural language and omit Midjourney parameters. Do not invent pixel dimensions, stylization values, API settings, or other unsupported parameters.
