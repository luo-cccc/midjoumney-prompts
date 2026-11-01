# Character Design

Use this workflow when the user supplies a character concept and wants a Midjourney prompt. Generate an original design rather than copying a named artist's style.

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
- For the default CG medium only, apply the character finish in [visual-system.md](visual-system.md): premium semi-realistic animated-film 3DCG, idealized anime-influenced facial structure, BJD-inspired facial precision paired with natural skin, groomed strand hair, and physically believable costume materials. Use cinematic lighting motivated by the portrait's setting.
- Keep living skin and grounded anatomy; avoid plastic or waxy rendering, physical doll joints, flat cartoon features, excessive smoothing, and low-detail game models. Follow the shared style rules when the user chooses a different medium.
- Do not turn the portrait into a full-body image unless the user asks for one.

## Output

Write one coherent English prompt covering subject, identity, face, hair, costume, accessories, pose, framing, background, style, lighting, and camera treatment. Prevent the failures listed above by describing the wanted result, and put only exclusions that materially reduce likely failures in `--no`. Do not overstuff the prompt with synonymous quality words.

Default CG parameters:

`--ar 3:4 --raw --s 150`

Use the shared parameter rules for alternative media and user-specified values.

When the user supplies a reference image, preserve its character identity and requested art direction. When the user requests a revision, keep every other confirmed design detail unchanged.
