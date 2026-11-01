# Scene Design

Use this workflow when the user supplies a scene, environment, or location concept and wants a Midjourney prompt. Generate an original scene rather than copying a named artist's style or a location from an existing franchise. To extend a supplied image, use the outpainting workflow instead.

## Design decisions

- Derive architecture, terrain, vegetation, materials, and a coherent color palette from the place's culture, era, climate, and function.
- Make the place recognizable through one or two strong visual motifs, such as a landmark structure, a signature plant, or a distinctive material.
- Keep construction plausible for the setting. Show wear, repairs, or traces of use where the place's history calls for them.
- Give the image one clear focal point. Do not add random props, unrelated characters, or decorative clutter.
- Choose a time of day, season, and weather that support the intended mood. Describe the light concretely, including its source, direction, and color, such as low warm sunlight from the left.

## People and characters

- By default, show the place without people: describe the space as empty, and put `people` in `--no`.
- Add small background figures when they are central to the requested activity, such as a busy market or festival. A village or ferry crossing alone does not require extra residents or travelers. An explicit request for an empty scene takes precedence.
- When the user's established character belongs in the scene, keep their confirmed design, state their position and scale in the frame, and keep the place as the main subject unless the user asks for a character-focused illustration.
- When the scene shows parts of the character that the confirmed design does not cover, such as legs and footwear after a head-to-waist portrait, take them from the character's reference sheet if one exists. Otherwise infer them from the design's colors, materials, and role, and describe them briefly.
- When the user plans to add a character later, leave an open, uncluttered area where the character will stand.
- Whenever people appear in the scene, keep `people` out of `--no`.

## Composition

- Use a wide, eye-level establishing shot at full scale, with the focal point off center.
- Build depth with a framing element in the foreground, the focal point in the midground, and layered silhouettes in the background. Use atmospheric haze to separate distances, and leading lines such as roads, rivers, or stairs to guide the eye to the focal point.
- Show scale with familiar objects such as doors, stairs, lanterns, or windows.
- Avoid cluttered composition without a clear focal point, muddy colors, flat lighting, warped architecture, inconsistent perspective, and generic stock-photo or mobile-game backdrops.
- For readable signage, put the exact words in double quotation marks and add "with the words" or "written". Short Latin-alphabet words render most reliably. When no signage is requested, leave signs and lettering out of the description and put text, letters, and watermarks in `--no`.

## Style

Use the scene's explicit style request first. If the scene has no style request, carry forward a style explicitly chosen by the user for its character or world. Otherwise use game-CG. Accepting a workflow's default or attaching a character design image does not count as choosing its finish. Preserve the character's identity, palette, culture, and motifs across styles.

- **Painterly.** For a painted, painterly, or anime-illustration request without another named medium, use high-quality semi-realistic anime environment painting with a refined painterly finish, believable material texture, readable light and shadow, and cinematic lighting. This includes explicitly matching a character design's painted look. Use `--ar 16:9 --raw --s 150` unless the user chose different style parameters.
- **Other chosen style.** For a named medium such as ink wash or watercolor, describe that medium without adding game-CG or anime-painting wording. Keep previously confirmed `--raw` and `--s` values associated with it; if none exist, add neither. Use the scene's aspect ratio.
- **Game-CG (default).** Use high-quality semi-realistic game-CG finish, crisp rendered forms, physically believable materials, detail on the materials actually present, volumetric atmosphere where appropriate, and soft contact shadows on supporting surfaces. Frame it as a cinematic still. Keep the scene's time-of-day lighting instead of the reference sheet's studio lighting. Favor full-scale architecture and natural material variation over toy-like dioramas, repetitive textures, and plastic surfaces. Use `--ar 16:9` without `--raw` or `--s` unless the user explicitly requests different values; optionally add `HUD` to `--no` if interface elements are a likely failure.

Use one finish unless the user requests a blend. The design, people, and composition rules apply to every style. Only the game-CG finish calls for a cinematic still.

## Notes to the user

After the prompt, add these short notes when they apply:

- When the user's character appears in the scene: attach the character's image under "Attach to prompt" in the Imagine bar, generating it from the design prompt first if needed, and keep `--ar` in the prompt.
- When parts of the character's costume were inferred: say which parts, and that a reference sheet would fix the full costume.
- When a scene for a character or world designed in the painterly finish falls back to the game-CG style: say that the scene's finish differs from the character design's, and offer to rewrite it in the painterly style.
- When signage uses Chinese or another non-Latin script: warn that the text may come out wrong.

## Output

Write one coherent English prompt covering location, focal point, foreground, midground, background, architecture or terrain, materials, time of day, weather, lighting, color palette, mood, framing, and camera treatment. Prevent the failures listed above by describing the wanted result, and put only exclusions that materially reduce likely failures in `--no`. Do not overstuff the prompt with synonymous quality words.

Preserve the user's desired aspect ratio in place of 16:9. Keep `--ar` in the prompt even when an image is attached, because the Edit Model otherwise matches the first attached image's aspect ratio. In V8.2 the Edit Model replaced Character Reference and Omni Reference, so do not add `--cref` or `--oref`.

When the user supplies a reference image of the place, preserve its layout, landmarks, and requested art direction. When the scene belongs to a character or world already established in the conversation, match its palette, culture, and motifs. When the user requests a revision, keep every other confirmed scene detail unchanged.
