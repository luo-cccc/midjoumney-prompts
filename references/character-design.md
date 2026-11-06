# Character Design

Use this workflow when the user supplies a character concept and wants a Midjourney prompt. Generate an original design rather than copying a named artist's style.

For direct GPT Image 2 minor-character sheets, reuse the design decisions below, then follow [gpt-image-sheet.md](gpt-image-sheet.md). The portrait composition, output format, and Midjourney parameters on this page do not apply to that sheet workflow.

## Design decisions

- Derive hairstyle, hair color, facial features, costume, accessories, silhouette, and a coherent color palette from the character's identity and world.
- Make the design recognizable through one or two strong visual motifs. Keep costume construction plausible and consistent with the role.
- For adult characters, use mature natural facial proportions; do not make them childlike.
- For fantasy characters, make racial traits readable, such as ears, tail, horns, wings, markings, or nonhuman eyes.
- Do not add random props, unrelated companion characters, or decorative clutter.

## Default composition and style

- Use a centered half-body portrait from head to waist, shown from the front or a slight three-quarter angle.
- Show the complete head, hairstyle, accessories, both shoulders, and upper-body clothing.
- Use a simple background that separates the character without competing for attention.
- Default to the refined semi-realistic 3DCG character finish in [visual-system.md](visual-system.md): sculptural form, art-directed proportions, BJD-grade surface refinement over living skin, volumetric eyes, groomed hair locks, and specific costume materials under cinematic lighting.
- Keep mature facial proportions and grounded anatomy; avoid plastic or waxy skin, mechanical doll joints, excessive smoothing, flat lighting, and generic low-detail game-model aesthetics. An explicitly requested painting or named medium replaces this default under the shared style rules.
- Do not turn the portrait into a full-body image unless the user asks for one.

## Output

Write one coherent English prompt covering subject, identity, face, hair, costume, accessories, pose, framing, background, style, lighting, and camera treatment. Prevent the failures listed above by describing the wanted result, and put only exclusions that materially reduce likely failures in `--no`. Do not overstuff the prompt with synonymous quality words.

Default portrait parameters:

`--ar 3:4 --raw --s 150`

Use the shared parameter rules for alternative media and user-specified values.

When the user supplies the target character's identity reference, preserve its character identity and requested art direction. A different character's style reference supplies only the assigned visual treatment. When the user requests a revision, keep every other confirmed design detail unchanged.
