# Scene Design

Use this workflow for the first Midjourney scene base, revisions to its prompt before an image exists, or an explicitly requested Midjourney revision of an existing scene. Generate an original scene rather than copying a named artist's style or a location from an existing franchise. Once a scene image exists, subsequent consistency-preserving variations default to [gpt-image-scene.md](gpt-image-scene.md), unless the user specifies another engine. For a GPT Image 2 scene frame extension, follow that workflow's extension rules; Midjourney extensions and other crop-completion requests use [outpainting.md](outpainting.md).

## Design decisions

- Derive architecture, terrain, vegetation, materials, and a coherent color palette from the place's culture, era, climate, and function.
- Make the place recognizable through one or two strong visual motifs, such as a landmark structure, a signature plant, or a distinctive material.
- Keep construction plausible for the setting. Show wear, repairs, or traces of use where the place's history calls for them.
- Give the image one clear focal point. Do not add random props, unrelated characters, or decorative clutter.
- Choose a time of day, season, and weather that support the intended mood. Describe the light concretely, including its source, direction, and color, such as low warm sunlight from the left.

## Initial base and later variations

- Make the base easy to reuse: describe the main landmark, connections between buildings and paths, terrain, material palette, and camera placement clearly. Leave suitable open space if later character insertion is planned. Do not add extra views, grids, or mandatory approval images.
- The actual scene image designated by the user becomes the structural source for later variations. Extract its visible spatial anchors when it is supplied; the first prompt describes design intentions, not proof that every intended detail appears in the result.
- If the user requests both stages before the image exists, provide the MJ base prompt and clearly provisional GPT Image 2 variation prompts using known design intentions. Say that image-based matching requires the eventual base image rather than claiming to have inspected it.
- For an explicitly requested MJ revision of an existing image, preserve its confirmed scene structure, camera, framing, people, signage, and actual medium unless the user changes them. The new-scene defaults below must not replace existing details. Change the requested state and its necessary effects on light, surfaces, reflections, or occlusion.

## People and characters

- For a new scene with no people requested, describe the space as empty and put `people` in `--no`. When revising an existing image, preserve its people unless removal is requested.
- Add small background figures when they are central to the requested activity, such as a busy market or festival. A village or ferry crossing alone does not require extra residents or travelers. An explicit request for an empty scene takes precedence.
- When the user's established character belongs in the scene, keep their confirmed design, state their position and scale in the frame, and keep the place as the main subject unless the user asks for a character-focused illustration.
- When the scene shows parts of the character that the confirmed design does not cover, such as legs and footwear after a head-to-waist portrait, take them from the character's reference sheet if one exists. Otherwise infer them from the design's colors, materials, and role, and describe them briefly.
- When the user plans to add a character later, leave an open, uncluttered area where the character will stand.
- Whenever people appear in the scene, keep `people` out of `--no`.

## Composition

- For a new base, default to a wide, eye-level establishing shot at full scale, with the focal point off center. Existing-image revisions preserve the source camera and composition unless a change is requested.
- Build depth with a framing element in the foreground, the focal point in the midground, and layered silhouettes in the background. Use atmospheric haze to separate distances, and leading lines such as roads, rivers, or stairs to guide the eye to the focal point.
- Show scale with familiar objects such as doors, stairs, lanterns, or windows.
- Avoid cluttered composition without a clear focal point, muddy colors, flat lighting, warped architecture, inconsistent perspective, and generic stock-photo or mobile-game backdrops.
- For readable signage, put confirmed exact words in double quotation marks and add "with the words" or "written". Short Latin-alphabet words render most reliably. For a new scene with no signage requested, leave signs and lettering out of the description and put text, letters, and watermarks in `--no`. Existing-image revisions preserve established signs unless removal is requested; keep `text` and `letters` out of `--no` when retaining them, and do not invent wording that cannot be read or is not confirmed.

## Style and integration

Follow [visual-system.md](visual-system.md) for style priority and parameters. By default, use a cinematic realistic 3DCG environment with full-scale construction, material thickness, natural roughness and weathering, indirect illumination, and layered atmospheric depth. Use only the materials actually present. Keep cinematic art direction and the scene's time-of-day lighting rather than a reference sheet's studio lighting.

When a character appears, use the shared idealized semi-realistic 3DCG character finish within that realistic environment. Preserve facial design and proportions rather than turning the character into a live-action actor; keep architecture and vegetation realistic rather than making them a dollhouse or anime-painted backdrop. Different stylization levels are intentional within the same CG medium.

Include a concise integration clause: a common light direction and color temperature, environmental bounce on skin and clothing, contact shadows at actual contact points, consistent scale and camera perspective, coherent depth of field, and shared exposure and color grading. Adapt these to the scene's actual conditions and visible character scale.

For an explicitly requested painting or named medium, use the shared alternative-medium rules instead of the CG clauses. Do not append cinematic-render or CG skin-shading language to a wholly painted scene. An explicit request to match an attached image's medium takes priority over defaults.

Default CG parameters for a new base: `--ar 16:9 --raw --s 150`. A current aspect-ratio request takes priority; otherwise an existing-image revision inherits the scene source's frame. Never copy a character portrait's ratio merely because it is attached. Preserve confirmed style parameters under the shared rules.

## Notes to the user

After the prompt, add these short notes when they apply:

- When the user's character appears in the scene: attach the character's image under "Attach to prompt" in the Imagine bar, generating it from the design prompt first if needed, and keep `--ar` in the prompt.
- When parts of the character's costume were inferred: say which parts, and that a reference sheet would fix the full costume.
- Only when creating a new image under the unified CG default, if an attached or previously accepted default image uses another medium and no style-match was requested: briefly explain that the new prompt retains identity but uses the CG medium, and that the reference may still influence the result. For revisions, retain the confirmed medium unless a change is requested. Do not issue a style-mismatch note merely because the CG character is more idealized than its environment.
- When signage uses Chinese or another non-Latin script: warn that the text may come out wrong.

## Output

Write one coherent English prompt covering location, focal point, foreground, midground, background, architecture or terrain, materials, time of day, weather, lighting, color palette, mood, framing, and camera treatment. Prevent the failures listed above by describing the wanted result, and put only exclusions that materially reduce likely failures in `--no`. Do not overstuff the prompt with synonymous quality words.

For `--ar`, use the current requested ratio, otherwise the known scene-source ratio for an existing-image revision, otherwise 16:9 for a new base. Include the known ratio even when images are attached, so a character reference does not supply the scene frame. If a revision's source ratio is unavailable, say to retain that frame and leave its numeric flag unspecified rather than guessing 16:9. In V8.2 the Edit Model replaced Character Reference and Omni Reference, so do not add `--cref` or `--oref`.

When the user supplies a reference image of the place, preserve its layout, landmarks, and requested art direction. When the scene belongs to a character or world already established in the conversation, match its palette, culture, and motifs. When the user requests a revision, keep every other confirmed scene detail unchanged.
