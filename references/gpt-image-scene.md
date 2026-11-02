# GPT Image 2 Scene Variations

Use this workflow for GPT Image 2 variations after a scene base has been created, normally with the Midjourney workflow in [scene-design.md](scene-design.md). Write prompts for consistent changes to that established place. Preserve the source image's actual medium and scene identity instead of reapplying new-scene defaults. An explicit Midjourney revision uses that workflow's output rules instead. This workflow delivers prompt text; generate images only when requested.

## Source image and version

- Identify the edit target: the image the user wants changed. It supplies scene geometry and the current state, not merely a broad style reference. Distinguish it from an original scene base used for structural reference, a character identity sheet, and any separate style reference. Name each attachment by its actual order or a clear distinguishing description.
- For independent alternatives, such as separate day, night, and snow versions, use the designated base for each unless the user specifies otherwise. For cumulative changes such as "add a traveler to the rain version," edit the selected rain version and retain its confirmed state. An older base may support structural identity but must not undo later accepted changes.
- A user's instruction to use a particular image selects that edit source; do not add a separate approval checkpoint. Unadopted additions in intermediate generations do not become universal scene requirements.
- If the image is missing, produce a provisional prompt from confirmed textual facts when useful and say it has not been visually checked against the source. Retain the text's level of specificity, leaving unknown geometry unspecified rather than borrowing details from other scenes or examples. Do not invent visible landmarks, attachment numbers, pixel dimensions, or a claim of achieved consistency. Editing a text-only MJ draft before any base exists stays in [scene-design.md](scene-design.md).

## Fixed view: preserve structure, change the requested state

- For state changes or local edits within the same frame, preserve camera position, viewing direction, perspective, apparent field of view, horizon, aspect ratio, and composition without inventing lens measurements. Keep buildings, roof silhouettes, door and window placements, landmarks, paths, terrain, vegetation placement, and their relative scale and spatial connections, except where the user requests a structural change. A requested new viewpoint, crop, or canvas extension replaces the corresponding camera and framing locks as described below.
- State the actual requested changes concretely: time, weather, season, a light being switched on, damage to a specified area, or adding, removing, or moving a particular character or prop. Preserve unaffected scene design, materials, and details; do not redesign the location to illustrate the new mood.
- Allow necessary consequences. Night changes illumination, exposure, and shadow behavior; rain changes wetness, reflections, and visibility; snow changes surface coverage and possibly foliage; an inserted person changes local shadows, reflections, and occlusion. Keep the underlying structures while updating effects that depend on the requested state. Do not lock the source's exact lighting and color values when the requested change requires them to vary.
- A character identity image supplies that character's face, build, hair, and costume, not the background or its studio lighting. Describe the character's placement, scale, pose, perspective, contact shadows, and environmental light in the source scene. Reuse the relevant integration and costume-completion rules in [scene-design.md](scene-design.md), omitting its MJ syntax. A request to add a person overrides an earlier empty-scene constraint. Preserve people already present unless the user changes them; do not add other unrequested figures.
- For local removal or repair, continue the revealed background from visible neighboring structure. Treat previously hidden content as conservative completion rather than exact recovery. Localize changes where the request is local; a global weather or time change can affect the whole frame.

## Requested viewpoint or frame changes

- Change the camera only when requested. For a new view of the same location, preserve world-space relationships, architectural structure, landmark identities, scale, and confirmed design. Allow screen positions, perspective, occlusion, and framing to change with the camera. Do not require a landmark to stay at the same pixel location after moving the viewpoint, or assume a changed view is a mirrored image.
- A single source cannot establish all hidden sides. Complete newly exposed areas conservatively from established construction and explain what was inferred; use additional user-supplied views when available. Do not invent exact spatial measurements or promise a recovered 3D model.
- A wider canvas is distinct from a new camera view. For an extension, preserve the existing region's perspective, scale, and design and continue only the needed environment into the new area. The new canvas can change aspect ratio and the original content's share of the total frame; do not rescale that content to keep its former frame occupancy. Use the relevant continuity rules in [outpainting.md](outpainting.md); do not stretch buildings or expand a cropped person into a full body merely to fill added canvas.

## Prompt assembly and output

Use the user's requested language, otherwise the language of the request. Deliver one self-contained prompt per requested variation, each in its own fenced code block. Request one image per prompt rather than a comparison grid unless asked. Use this order: input-image roles and chosen version; scene anchors to preserve; explicit changes; necessary dependent effects; camera, medium, framing, and other output constraints.

Describe the aspect ratio in natural language, normally preserving the source frame rather than resetting it to 16:9. Keep unrequested text absent; preserve established signage or use exact replacement text when requested. Remove MJ parameter suffixes, reference codes, and weights, including `--ar`, `--raw`, `--s`, `--sref`, `--cref`, `--oref`, and `--no`. Do not turn them into invented GPT Image settings or claim UI/API settings were configured.

The following scaffold is for a fixed-view edit with an available source image. Replace every bracketed field from the actual input and omit irrelevant clauses. For a requested new view, crop, or canvas extension, replace the affected camera, composition, and aspect-ratio clauses instead of retaining contradictory fixed-frame instructions. Without an attachment, describe the pending source instead of claiming it is already present.

```text
以附件[实际编号或明确描述]的[底图或当前版本]为编辑对象，生成同一地点的一张变更图。[其他附件如有：分别说明原始场景结构参考、角色身份参考或画风参考的用途。]

保留原图中的[实际可见且需保留的建筑、地标、道路、地形及相互位置关系]，保持建筑形制、结构比例、材质和未要求修改的场景细节。维持原有机位、观察方向、透视、地平线、构图和画幅。

本次改变：[明确的时间、天气、季节、局部状态或人物道具变化及其位置范围]。保留当前版本中已确认的[仍需延续的状态或剧情变化]。

随本次变化同步调整[实际需要变化的光源、明暗、阴影、倒影、地表状态、环境遮挡或局部接触关系]，使变化与场景自然融合。[人物入景时补充身份、尺度、姿态和环境光照要求。]

延续源图实际的[媒介、造型与材质表现、细节完成度]，只改变本次指定内容及其必要影响。输出一张完整场景图，[按实际要求说明文字或其他排除项]。
```

After the prompt, briefly identify the chosen source, requested changes, and any inferred hidden content when relevant. Do not require a new MJ base for every variation or promise pixel-perfect preservation, exact unseen geometry, or guaranteed cross-image consistency. Keep corrections local unless the user requests a reusable rule.
