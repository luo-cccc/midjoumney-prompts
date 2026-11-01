---
name: midjourney-prompts
description: Create and refine ready-to-use Midjourney prompts for original character design, multi-view character reference sheets, scene and environment design, and controlled outpainting from reference images. Use for prompt text, not image generation.
---

# Midjourney Prompt Studio

Turn the user's concept or reference image into a concise, copy-ready English Midjourney prompt while preserving explicit visual choices and identity details. Default new images to idealized semi-realistic 3DCG characters and cinematic realistic 3DCG environments in one coherent visual world.

## Select the workflow

For character designs, reference sheets, and new scenes, first read [references/visual-system.md](references/visual-system.md) for shared style selection, rendering language, integration, and parameter presets. For outpainting, use the source image's actual style instead.

- For a character concept such as a race, profession, archetype, or costume idea, read [references/character-design.md](references/character-design.md).
- For a character model sheet, turnaround, asset sheet, multiple consistent views, or head/body breakdown, read [references/reference-sheet.md](references/reference-sheet.md).
- For a new scene, environment, location, or background, read [references/scene-design.md](references/scene-design.md).
- For extending a supplied image or completing cropped anatomy, costume, props, or background, read [references/outpainting.md](references/outpainting.md).
- If the request spans modes, read each relevant reference and keep one consistent character design across all prompts.

## Prompt rules

1. Write concrete visual English rather than a pile of isolated quality tags.
2. In prompts for new images (character designs, reference sheets, and scenes), describe what should appear rather than writing "no" or "without" in the prompt text; Midjourney may still draw the negated item. Put concrete unwanted items in `--no` as a short comma-separated list. Keep clothing words out of `--no`, because moderation reads each word separately (`--no modern clothing` becomes "no modern" and "no clothing" and can trigger a warning); describe the wanted clothing instead.
3. Preserve explicit user choices, identity details, requested canvas shape, and confirmed revisions. Workflow defaults apply only when the user has not specified otherwise. Keep revisions focused on the requested changes.
4. Infer missing design details only when they support the stated character or world. When a scene requires body parts outside an existing portrait, follow the scene workflow's costume-completion rules; outpainting follows its own crop limits.
5. Use references to preserve identity and any requested style. For new images, follow the shared visual system's style selection; attaching a character image alone does not request its medium. Preserve the original finish during outpainting.
6. Put the finished prompt in a fenced code block so it is easy to copy. Add analysis or layout guidance only when requested by the workflow or by the user.
7. Produce prompt text only. Do not generate an image unless the user separately asks for one.

Use the exact Midjourney parameters requested by the workflow, and `--no` as described in rule 2. Do not invent pixel dimensions, stylization values, or other unsupported parameters.
