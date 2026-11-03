# Scene Continuity

Read this file when editing an established scene, planning repeated views of a place, or correcting a returned scene image. For a first image, apply the reusable-base guidance in [scene-design.md](scene-design.md); a location record is optional until an image or confirmed design exists. Keep the selected engine's prompt syntax and the source image's actual medium.

## Choose the source and the kind of change

- Identify the edit target by its actual attachment order, filename, or a clear description. It supplies the current visible scene and state. Separate it from an original structural reference, another view, a character identity image, and a style reference. A reference name identifies an image, not a calibrated place or camera.
- For independent alternatives such as day, night, and snow, start each from the designated base. For cumulative changes, edit the selected current version and retain its accepted changes. An older image can support structure but must not restore removed props or undo later damage, lighting, people, or signage changes.
- Using the image the user selects requires no extra approval step. Treat their adoption or selection of a result as acceptance; incidental additions in unadopted outputs do not become requirements for the place. A new explicit design change supersedes the corresponding earlier constraint.
- Distinguish a fixed-view state edit, a crop, a canvas extension, and a new camera view. A combined request replaces only the affected locks: cropping changes framing; extension adds outside the original region; moving the camera changes projection and occlusion. Do not keep contradictory framing or pixel-position requirements.
- If the source is unavailable, use confirmed text for a provisional prompt and state that it has not been checked against the image. Keep unknown geometry unspecified. Do not invent attachments, observations, measurements, or claims of achieved consistency.

## Keep a small location record when useful

For a place reused across several edits or viewpoints, or when drift needs correction, reuse an existing record or summarize only the facts needed for the task. A one-off edit does not need a separate record. Keep it in the conversation or deliver it as text when useful; do not create project files unless requested.

Include the source and selected version, a few distinguishing structures and supported spatial connections, the current accepted state, and relevant unknown areas. Separate what is visible, what the user specified as design, and what was inferred. The initial prompt expresses design intentions; the actual image shows which details were realized. An overlap alone does not prove an object's location behind another, and image-left does not establish a compass direction.

Example record shape; replace fields from actual inputs and omit unused lines:

```text
地点：[已知名称或简短描述]
结构依据：[实际图片或用户确认的文字设计；未见图片时注明]
当前版本：[本次选定的编辑图或文字状态]
已观察：[可见的建筑特征、尺度关系、道路连接；不从遮挡臆测]
设计指定：[用户明确给定、但图中未显示的关系或造型]
当前状态：[仍需继承的人物、道具、灯光、天气、损坏及已移除内容]
未知或推断：[未观察的背面、遮挡区，以及本次需要补全的部分]
```

Update only the facts affected by an adopted result or the user's explicit revision. Reuse confirmed views that help the requested shot, rather than requiring a full turnaround, comparison grid, or additional approval images. Do not invent a version ID or filename and imply that a saved asset exists.

## Assign references and describe the available control

Use the smallest relevant set of inputs. Tell the model what each input supplies and which image receives the edit. If the current version and an older base differ, keep the current accepted state and use the older image only for the intended structural evidence. If a material conflict cannot be resolved from the request or the selected version, ask one focused question; do not silently merge incompatible layouts.

| Available basis | What it supports | Boundary to preserve |
| --- | --- | --- |
| Confirmed text | Design and state requirements | No claim that a supplied or generated image was inspected |
| Scene or other-view reference | Visible appearance, layout, and evidence about that view | Unseen geometry remains unknown; style references alone do not establish location identity |
| Layout sketch or floor plan | Explicit placement or design relationships | A picture of a plan is visual guidance, not automatic camera calibration or 3D reconstruction |
| Target-view edge, depth, segmentation, or mask input | More direct structure or edit-region guidance when the chosen tool supports that input | An uploaded image is not proof that a control module or mask operation was applied |
| Shared 3D scene and its renders | A common geometric source for target-camera projection and occlusion | Coverage and geometry may still be incomplete or wrong; only claim a shared scene if it actually exists |

When the distinction affects the task, briefly identify the basis actually available and any missing target-view evidence. Distinguish supplied references, requested operations, and operations known to have run. For example: `依据：当前场景图；新机位结构来自单图推断；背面尚未确认。` Keep this outside the copy-ready prompt unless it informs the model's instructions. Skip a separate status block for a straightforward edit or a request for prompt text only.

Use masks, annotations, or structure inputs only as the selected tool supports them. A drawn box or an ordinary reference image is not automatically a mask, ControlNet input, or precise placement constraint. Do not invent API fields, reference bindings, weights, or tool actions. Seeds and style codes can document a run, but do not lock a location. This skill writes prompts; it does not generate control maps, reconstruct a scene, or run a renderer.

## New views and newly revealed areas

- Preserve supported world relationships, building design, relative scale, and accepted state. Let screen positions, apparent size, perspective, and occlusion change with the requested camera. Specify the camera's relation to known landmarks rather than guessing lens values or coordinates.
- Prefer relevant existing views or target-camera renders when available. A source-view edge or depth map describes that view and cannot simply become the structure of a different view. A floor plan can supply design relationships without proving a matching perspective image.
- With only one source, complete newly exposed areas conservatively from established construction. Briefly identify the inferred area instead of claiming recovered geometry. If the task requires exact unseen details, request the missing view or design information; for an ordinary concept variation, proceed with a clearly identified inference.
- A new view is provisional evidence about previously unknown regions until the user adopts it. After adoption, carry those design decisions into relevant later views without treating every generated detail as automatically correct. If adopted views conflict, resolve the specific conflict before reusing it.

## Check returned images and repair drift

Review only images actually available. Without a returned result, supply the prompt or relevant check points without declaring a visual pass. Compare the chosen source, requested change, and result on these axes:

- **Structure:** for a fixed view, check silhouettes, door/window placement, landmark scale, path connections, perspective, framing, signage, and unaffected people or props. An overlay can help when available; do not claim to have made one unless you did.
- **State and integration:** verify the requested change and inherited additions/removals; allow its necessary lighting, reflection, surface, contact-shadow, and occlusion changes. A global weather edit should not fail solely because many pixels changed.
- **New view or extension:** for a moved camera, check supported spatial relationships and newly visible design, not equal pixel positions. For outpainting, check scale and perspective within the original region, edge continuity, and newly added content; allow the original region's share of the enlarged frame to change.
- **Finish:** check that the medium, material treatment, and level of detail remain compatible with the source unless restyling was requested. Similar color or style alone is insufficient evidence of the same place.

If an error is local, describe the specific difference and issue a focused correction prompt from the selected result or a suitable earlier source. If drift is broad, suggest returning to the last suitable version and reapplying all still-required accepted changes explicitly; do not silently discard the current state. Decompose changes only when it helps isolate an observed failure or the user asks for stages.

Mention only observed issues and relevant unknowns. For strict preservation outside a local edit, a supported mask plus compositing can be recommended as a separate tool operation; generation instructions alone do not guarantee unchanged pixels. Do not perform image generation or editing without the user's separate request.
