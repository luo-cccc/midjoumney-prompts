# Controlled Outpainting

Use this workflow when a user supplies an image and wants an English Midjourney outpainting prompt. Do not generate the image unless separately requested.

## Analyze the image

1. Identify the person, face, hairstyle, costume, pose, props, setting, and composition.
2. Assess art style, color, lighting, camera angle, perspective, and figure scale.
3. Inspect each image edge and report only structures actually cut off. Do not assume a complete pose that the image does not show.
4. Choose the nearest natural composition boundary:
   - If the figure is cut at the chest, waist, or thigh, prioritize the adjacent torso, arms, garment opening, belt, hem, and necessary background, ending at a sensible half-body portrait boundary.
   - Do not turn a torso crop into a full-body portrait unless the visible image already establishes or clearly implies the lower body.
   - If only a prop, garment edge, or background is cut, complete that local element without extending the body.
5. Do not add anatomy, props, scenery, or body parts merely because the selected canvas is large.

## Extension rules

- Preserve the subject's identity, facial features, hairstyle, costume, pose, and existing details.
- Continue the garment's structure, layers, material, colors, patterns, metal parts, and decoration consistently.
- Match the original art style, palette, lighting, depth of field, lens distance, and perspective.
- Preserve head size, shoulder width, body scale, and subject-to-frame ratio. Do not stretch or reshape the figure to fill the selection.
- Treat the goal as naturally completing cut-off structures, not filling the whole canvas.
- If the selection exceeds the needed extension, continue the environment, atmosphere, or background instead of adding more body.
- Avoid seams, duplicated patterns, material shifts, incorrect occlusion, new characters, and unrelated objects.

## Required visual constraints

Include this meaning in the English prompt:

> Extend only as far as necessary to complete the anatomy and garment forms visibly cut off by the frame, ending at the nearest natural portrait boundary. Preserve the original head size, shoulder width, subject scale and camera distance. Do not stretch, lengthen or rescale the figure to fill the selected canvas area, and do not turn a torso crop into a full-body portrait unless the visible composition already implies one. Treat any excess extension area as matching atmospheric background rather than additional body.

Also require seamless continuation, consistent perspective, consistent lighting, and unified scale and anatomy. Make the description specific to the actual image rather than using only the generic constraint paragraph.

## Output format

When analysis is useful, provide:

1. A concise Chinese analysis of the visible crop.
2. The natural boundary where extension should stop.
3. A copy-ready English Midjourney outpainting prompt in a code block.
4. A brief Chinese selection recommendation.

If the correct selection size is uncertain, recommend a smaller natural extension first, then another pass after checking the result. Never invent pixel values or fixed body ratios in place of visual judgment.
