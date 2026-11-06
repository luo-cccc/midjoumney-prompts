# Scene Design

Use this workflow for the first Midjourney scene base, revisions to its prompt before an image exists, or an explicitly requested Midjourney revision of an existing scene. Generate an original scene rather than copying a named artist's style or a location from an existing franchise. For existing scenes, repeated viewpoints, or returned-image corrections, read [scene-continuity.md](scene-continuity.md) for source selection, reference evidence, and checks. Once a scene image exists, subsequent variations default to [gpt-image-scene.md](gpt-image-scene.md), unless the user specifies another engine. For GPT Image 2 frame extensions, use that workflow; Midjourney extensions and other crop-completion requests use [outpainting.md](outpainting.md).

## Design decisions

- Derive architecture, terrain, vegetation, materials, and a coherent color palette from the place's culture, era, climate, and function.
- Make the place recognizable through one or two strong visual motifs, such as a landmark structure, a signature plant, or a distinctive material.
- Keep construction plausible for the setting. Show wear, repairs, or traces of use where the place's history calls for them.
- Give the image one clear focal point. Do not add random props, unrelated characters, or decorative clutter.
- Choose a time of day, season, and weather that support the intended mood. Describe the light concretely, including its source, direction, and color, such as low warm sunlight from the left.

## Initial base and later variations

- Make the base easy to reuse: choose a few distinguishing structures, describe connections between buildings and paths, and establish terrain, materials, and camera placement. When later reuse is planned, make those anchors legible rather than hiding every connection behind atmosphere or foreground clutter. Leave suitable open space for planned character insertion; do not add extra views, grids, or mandatory approval images.
- The scene image designated by the user becomes the visible structural source. Extract supported spatial anchors when it is supplied; the first prompt records design intentions, not proof that every intended detail appears. Keep a short location record under [scene-continuity.md](scene-continuity.md) only when repeated use or correction benefits from it.
- If both stages are requested before an image exists, provide the MJ base prompt and provisional GPT Image 2 variation prompts from known design intentions. Explain that image-based matching awaits the eventual base.
- Putting a character into a scene that has not been rendered yet is the exception: there is no edit target, so write it as a second Midjourney prompt in this workflow, using the people, integration, and `--ar` rules below. Those rules are MJ syntax and apply only on this path. Offer the GPT Image 2 edit version as well when the user will have the base shortly, and label it as awaiting that image.
- For an explicitly requested MJ revision, preserve the selected scene's confirmed structure, camera, framing, people, signage, state, and medium except as changed by the request. A new camera view replaces fixed-view locks; follow the shared guidance for target-view evidence and inferred areas. For a returned-image correction, focus on the observed defect and the unaffected content to retain instead of redesigning the scene.

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

Follow [visual-system.md](visual-system.md) for style priority and parameters. By default, use a naturalistic next-generation 3DCG environment with full-scale construction, material thickness, natural roughness and weathering, global and indirect illumination, controlled detail density, and layered atmospheric depth. Use only the materials actually present. Keep cinematic art direction and the scene's time-of-day lighting rather than a reference sheet's studio lighting.

When a character appears, use the shared refined semi-realistic 3DCG character finish within that naturalistic environment. Preserve facial design and proportions rather than turning the character into a live-action actor; keep architecture and vegetation physically grounded rather than giving them the character's doll-grade finish, a dollhouse look, or a flat-painted backdrop. Different stylization levels are intentional within the same CG medium.

Include a concise integration clause: a common light direction and color temperature, environmental bounce on skin and clothing, contact shadows at actual contact points, consistent scale and camera perspective, coherent depth of field, and shared exposure and color grading. Adapt these to the scene's actual conditions and visible character scale.

For an explicitly requested painting or named medium, use the shared alternative-medium rules instead of the CG clauses. Do not append cinematic-render or CG skin-shading language to a wholly painted scene. An explicit request to match an attached image's medium takes priority over defaults.

Default CG parameters for a new base: `--ar 16:9 --raw --s 150`. A current aspect-ratio request takes priority; otherwise an existing-image revision inherits the scene source's frame. Never copy a character portrait's ratio merely because it is attached. Preserve confirmed style parameters under the shared rules.

## Notes to the user

After the prompt, add these short notes when they apply:

- If a place reference is used, identify its role and any supplied scene-edit target. Recommend the appropriate supported image-input or editing mode when known; do not claim the reference is bound or an edit is configured. A style reference or seed alone does not establish the location's layout.
- When the user's character appears in the scene: attach the identity image through the selected interface's supported image input, generating it from the design prompt first only if needed, and retain the known scene `--ar`. Do not guess version-specific reference flags.
- When parts of the character's costume were inferred: say which parts, and that a reference sheet would fix the full costume.
- Only when creating a new image under the unified CG default, if an attached or previously accepted default image uses another medium and no style-match was requested: briefly explain that the new prompt retains identity but uses the CG medium, and that the reference may still influence the result. For revisions, retain the confirmed medium unless a change is requested. Do not issue a style-mismatch note merely because the CG character is more refined than its environment.
- When signage uses Chinese or another non-Latin script: warn that the text may come out wrong.

## Output

For a new base, write one coherent English prompt covering the place, focal point, foreground/midground/background, relevant structures and materials, state, lighting, mood, and camera treatment. For an existing-scene edit or correction, lead with the selected source and the specific change; include only the anchors, state, and output constraints needed to preserve continuity. Use positive descriptions and a short `--no` list only for material, correctly scoped exclusions; avoid synonymous quality tags.

For `--ar`, use the current requested ratio, otherwise the known scene-source ratio for an existing-image revision, otherwise 16:9 for a new base. Include the known ratio even when images are attached, so a character reference does not supply the scene frame. If a revision's source ratio is unavailable, say to retain that frame and leave its numeric flag unspecified rather than guessing 16:9. In V8.2 the Edit Model replaced Character Reference and Omni Reference, so do not add `--cref` or `--oref`.

When the user supplies a reference of the place, preserve its supported layout, landmarks, and requested art direction. When it belongs to an established character or world, match the confirmed palette, culture, and motifs. A revision changes only the requested design or state and its necessary effects on light, surfaces, reflections, or occlusion; keep unaffected details.
