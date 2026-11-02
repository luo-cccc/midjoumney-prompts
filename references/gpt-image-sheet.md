# GPT Image 2 Character Reference Sheet

Use this workflow when a minor or non-key character should be designed directly as a complete sheet for GPT Image 2, or when the user explicitly requests a GPT Image 2 sheet. Deliver one copy-ready prompt. This workflow writes the prompt; image generation still requires the user's request to generate.

## Design source and reference roles

- For a new character, take identity, age cues, species, build, role, face, hairstyle, costume, and palette from the user's concept and established world. Reuse the design decisions in [character-design.md](character-design.md), not its half-body framing. Fill gaps coherently and preserve explicit choices. Do not require a portrait, outpainting, full-body approval, or separately generated views first.
- A main-character sheet assigned as a style reference supplies visual treatment: actual medium, degree of stylization, form modeling, brushwork, edge treatment, material detail, lighting, and color handling. Describe the observed treatment concretely. The new character's face, hair, clothing construction, personal symbols, body shape, and exclusive colors come from its own design. Shared uniforms or faction motifs transfer only when requested or established by the world.
- If the target character also has an identity image, identify it separately and apply the source-preservation and conservative-completion rules in [reference-sheet.md](reference-sheet.md). A style-only image is never evidence of the target's original proportions or hidden costume.
- Describe each attachment by its actual image order and role, or by a clear distinguishing description when order is unavailable. Do not invent an attachment or claim to have extracted an unseen image's style. Without the requested style image, use confirmed textual art direction or the sheet default, and briefly state that matching awaits the reference.
- Minor narrative importance changes the amount of design exploration, not image finish. Costume complexity and ornament density follow occupation, status, and the user's choices. Keep the style reference's level of finish and material clarity rather than automatically making every minor character plain or low-detail.

## Reuse the sheet's visual logic

Read the layout and body occupancy, dynamic character description, and default finish sections of [reference-sheet.md](reference-sheet.md). Apply their presentation and consistency rules to the newly designed target, rather than treating the style-reference character as the subject. Use [visual-system.md](visual-system.md) for style priority and medium-specific language; skip its Midjourney parameter presets.

Unless overridden, request one white 16:9 landscape sheet. Left 55%: front, exact 90-degree side, and back neck-to-foot costume views. Right 45%: a 2x2 grid of frontal, 45-degree, exact side, and closer frontal portraits. Keep the reserved head space above each left-side neck crop, uniform scaling, shared anatomical levels and contact baseline. Hide hair and hair ornaments only in the left costume views while preserving clothing layers; keep hair visible in the right portraits, preserving its design and identifying features with framing appropriate to each view. Enlarging portraits changes display scale, not intrinsic head-neck-shoulder relationships.

For a new concept, establish one coherent anatomy and complete costume, then repeat them across all views. Do not describe the new design as recovered from the main-character sheet. A belt, armor edge, garment waist, or robe hem does not determine anatomical waist position or leg length. For an existing target, preserve its visible identity and build and briefly disclose inferred hidden structure. User-requested proportions, anatomy, poses, layout, and garment lengths take priority.

## Convert the Midjourney prompt logic

- Keep the visual requirements: character identity, reference roles, canvas and panels, body occupancy, view alignment, costume construction, materials, selected medium, and lighting.
- Write the aspect ratio as a natural-language composition request, such as "16:9 landscape canvas." It is a requested composition, not a claim that output pixel dimensions or UI settings were configured.
- Remove Midjourney parameters, reference codes, URL prefixes used as command syntax, and weights. Omit `--ar`, `--raw`, `--s`, `--sref`, `--cref`, `--oref`, `--no`, and similar suffixes. Do not translate a stylization number into an invented GPT Image setting.
- Express exclusions in natural language and scope them to the correct panel. For example, hide hair in the left costume views while keeping it in the portraits; request a clean sheet without text, labels, logos, or watermarks when labels were not requested. Do not globally exclude heads, hair, or clothing needed elsewhere.
- Keep the actual reference medium. A painted reference does not acquire PBR or skin-shader terminology just because the source workflow supports CG. Describe observed lighting rather than overwriting an explicit style match with default studio lighting.

## Prompt assembly and output

Use the language requested by the user, otherwise the language of their request. Write one self-contained prompt in a fenced code block, ordered as: generation goal and input-image roles; target identity and complete design; canvas and panel layout; view and proportion consistency; style and lighting; local visibility and other exclusions. Produce one character and one sheet per prompt unless the user requests a group or batch.

The following scaffold shows the structure for a new character with a style attachment. Replace every bracketed field with the actual brief; omit absent inputs and irrelevant traits. For an existing target, replace the new-design language with identity-preservation instructions.

```text
生成一张完整的[目标角色]角色设定图。附件[实际编号或明确描述]中的重要角色设定图作为画风参考，借鉴其中的[实际观察到的媒介、造型风格、笔触、材质表现与光照]。本张图的角色身份、五官、体型、发型、服装和专属配色依据以下文字设计。

角色设计：[年龄特征、种族、体型、职业与世界观；具体五官和发型；完整服装层次、结构、鞋履、配色与实际存在的材质]。各个视角表现同一个角色，服装结构、层次、扣件、装饰位置与配色保持一致。

纯白背景，16:9横版画布。左侧55%为正面、严格90度侧面、背面的颈部至脚部服装三视图；右侧45%为2×2头像网格，依次展示正面、45度、严格侧面和正脸近景。

左侧每个视图放在相同大小的完整人物展示区域中，保留原本属于头部的上方留白，在颈部形成整洁的展示裁切。颈下身体保持完整人物中的尺度，仅通过统一缩放和间距适应版面。[适合本角色解剖结构的中性站姿与肢体安排]。对应解剖高度与接触基线对齐，采用一致的弱透视。仅在左侧隐藏头发和发饰，保留披风、领口和所有服装层次，衣物长度与设计一致。

右侧头像保留本角色的发型设计与识别特征，头发在此区域正常显示，保持同一张脸和相同的头颈肩关系。放大只改变展示倍率，按各视角合理取景。所有区域采用一致的[选定画风、材质处理、光照和完成度]。画面[按实际要求填写局部排除项及文字要求]。
```

After the prompt, briefly identify newly designed details or inferred structure and explain which attachment supplies style versus identity. Do not append Midjourney settings, API configuration, or promises of exact layout, identity isolation, or multi-view consistency. Corrections to an individual result remain local unless the user requests a general rule.
