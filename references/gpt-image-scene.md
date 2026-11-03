# GPT Image 2 Scene Variations

Use this workflow for GPT Image 2 variations of an established scene, normally created with [scene-design.md](scene-design.md). Read [scene-continuity.md](scene-continuity.md) for source/version selection, reusable location records, reference roles, new-view evidence, and correction of returned images. Preserve the chosen scene's actual medium. An explicit Midjourney revision uses that workflow's output rules; editing an unrendered MJ draft stays there too. Deliver prompt text, and generate images only when separately requested.

## Fixed view: preserve structure, change the requested state

- Identify the selected edit image and the few visible anchors that distinguish this place. For a fixed-view edit, preserve camera position, viewing direction, perspective, apparent field of view, horizon, aspect ratio, and composition without inventing lens measurements. Keep building and roof shapes, door/window placements, landmarks, path connections, terrain, vegetation placement, and relative scale wherever the request does not change them.
- State the requested time, weather, season, lighting, damage, or character/prop change concretely, including its location or extent. Preserve unaffected design, materials, people, signage, and accepted state. Do not redesign the place to illustrate a mood.
- Allow necessary consequences: night changes illumination and exposure; rain changes wetness, reflections, and visibility; snow changes coverage and possibly foliage; an inserted person changes local shadows, reflections, and occlusion. Preserve underlying structure while updating these effects. Do not freeze lighting and color values that the requested change needs to alter.
- A character identity image supplies face, build, hair, and costume, not its background or studio lighting. Describe placement, scale, pose, perspective, contact, and environmental light in the target scene. Reuse the integration and costume-completion rules in [scene-design.md](scene-design.md), omitting MJ syntax. Adding a person overrides an earlier empty-scene constraint; preserve existing people unless changed and exclude only unrequested new figures.
- For local removal or repair, continue the revealed background from adjacent visible structure and identify uncertain completion when relevant. Keep the correction and its dependent effects local. If a mask or annotation is supplied, describe its actual role without claiming a tool operation has run or guaranteeing unchanged pixels outside it.

## Requested viewpoint or frame changes

Use the new-view guidance in [scene-continuity.md](scene-continuity.md) when the camera moves: retain supported spatial relationships and current state, allow changed projection and occlusion, and identify new areas inferred from limited evidence. Replace fixed-view camera and composition clauses rather than appending contradictory instructions.

A crop changes framing without automatically moving the camera. For a wider canvas, preserve the original region's perspective, scale, and design and continue only the needed environment into the new area. Allow the aspect ratio and the original content's share of the total frame to change; do not rescale that content to keep its former occupancy. Follow [outpainting.md](outpainting.md) for edge continuity and crop limits. Do not stretch buildings or complete a cropped person to full body merely to fill added canvas.

## Prompt assembly and output

Use the user's requested language, otherwise the language of the request. Deliver one self-contained prompt per requested variation, each in its own fenced code block. Request one image per prompt rather than a comparison grid unless asked. Assemble only the relevant clauses in this order: input roles and selected version; specific anchors and accepted state; requested change and scope; necessary dependent effects; applicable camera, medium, and output constraints. For a correction, name the observed mismatch and the intended repair instead of repeating the entire scene design.

Describe the aspect ratio in natural language, normally retaining the source frame rather than resetting it to 16:9. Keep unrequested text absent, preserve established signage, and use exact replacement words only when supplied or readable. Remove MJ suffixes, reference codes, and weights, including `--ar`, `--raw`, `--s`, `--sref`, `--cref`, `--oref`, and `--no`. Do not translate them into invented GPT Image settings or claim UI/API configuration.

This scaffold is for an available source and a fixed-view edit. Fill it from actual inputs and omit irrelevant clauses. For a new view, crop, or extension, replace the affected locks. Without an attachment, describe the pending source rather than claiming it is present.

```text
以附件[实际编号或明确描述]的[底图或当前版本]为编辑对象，生成同一地点的一张变更图。[其他附件如有：说明各自提供的结构、其他视角、身份或画风依据，以及本次取用的内容。]

保留[实际可见且需保持的建筑特征、地标、道路连接与尺度关系]，延续当前版本已确认的[人物、道具、天气、灯光、损坏或已移除内容]。维持原机位、观察方向、透视、地平线、构图和画幅。

本次只改变[具体变化、位置与范围]，同步调整[必要的光照、阴影、倒影、地表状态或遮挡关系]。[人物入景时补充身份、尺度、姿态与环境融合要求。]

延续原图的[实际媒介、材质表现与完成度]，保留未受本次变化影响的内容。输出一张完整场景图，[实际需要的文字或其他排除要求]。
```

After the prompt, briefly clarify the chosen version, relevant reference limitations, or inferred hidden areas when useful. A simple edit does not need a location record or control-status report, and a prompt-only request omits extra notes. Inspect a returned image before reporting success or writing an evidence-based correction. Do not require a new MJ base for each variation or promise pixel-perfect preservation, exact unseen geometry, or guaranteed cross-image consistency.
