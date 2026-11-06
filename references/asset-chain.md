# Two-Stage Asset Chain

Use this workflow when a character, scene, or prop reference image is being built as a reusable production asset rather than a single finished picture, and the user's pipeline runs Midjourney first and GPT Image 2 second. Read [visual-system.md](visual-system.md) for style priority and parameters.

The two stages have different jobs and are not interchangeable.

| Stage | Owns | Does not own |
| --- | --- | --- |
| Midjourney | art direction, medium, surface quality, lighting logic, palette relationships | layout, panel division, multiple views, precise structure, lettering |
| GPT Image 2 | structured asset images, multi-view layout, first-frame composition, localized edits | art direction, which it inherits from stage one |

The split follows capability. Midjourney is not reliable at "white background, left column, 2x2 grid" layout instructions. GPT Image 2 follows layout instructions, accepts multiple input images, and its edit path treats the first image as the edit target while the rest act as references.

One hard constraint makes the chain necessary rather than preferred: some video platforms reject reference images containing real human faces and accept only prior model output or licensed material. A synthesized chain is the way in.

## Stage one: the Midjourney style base

One image per asset. Its only purpose is to fix art direction. Do not attempt a layout, a turnaround, or complete structure here.

- State the medium and surface quality concretely. That is this stage's whole job; keep everything else brief.
- Characters: single figure, half or full body, simple composition.
- Scenes: main-camera wide view, no people.
- Props: single-object close view.
- Use one shared surface-quality description across the whole production. Writing a different one per asset is what makes assets look like they come from different worlds.

Parameters follow the shared rules: under the unified 3DCG default, characters `--ar 3:4`, scenes and props `--ar 16:9`, with `--raw --s 150`. An explicitly named medium keeps only the current aspect ratio.

Once confirmed, this image's actual appearance becomes the style evidence for stage two. The stage-one prompt records intentions; it does not prove every intended detail appeared.

**The Midjourney base is an intermediate, not a deliverable asset.** It establishes what the subject looks like stylistically. It is not the image submitted to a video model, and its portrait aspect ratio and composition are wrong for that use. Record it separately from the finished asset images.

## Stage two: GPT Image 2 asset images

Assign the Midjourney image as a **style reference**, not an identity source. Identity, structure, and palette come from the written design.

### Declare every input's role

For each input image, state what it supplies and what it must not carry in. When one image serves several roles, declare each separately.

| Input | Supplies | Must not carry in |
| --- | --- | --- |
| Midjourney style base | medium, surface quality, lighting tendency, palette relationships | its composition, pose, background, aspect ratio |
| Target identity image | face, bone structure, build, costume construction | its background, studio lighting, out-of-frame objects |
| Scene structure image | visible structure, landmarks, paths, scale | its people, its weather and time of day |
| Layout reference | panel division and arrangement | its characters, scene content, palette |

### Character asset images

Two outputs: an identity master that establishes the face, and a multi-view sheet that establishes costume and build across angles.

Two rules with mechanical reasoning behind them:

**Generate all views in a single pass.** Views produced in separate generations will drift, because two generations of the same text do not yield the same face. Only a single image containing every view can have views from one source.

**Use a neutral mid-gray ground, not pure white.** Pure white creates maximum subject-to-background contrast, and video models amplify small errors most at high-contrast edges — that is where halo, edge breathing, and contour instability get baked in once the still is read as a reference frame. Mid-gray lowers that contrast and extracts cleaner edges. Pair it with the opposite requirement for the subject: the background is neutral, the subject is **not** neutralized. Skin renders at its designed tone, never cooled or washed out by the backdrop.

Panel layout follows the production's needs. One workable default: front, exact 90-degree side, and back full-body views, plus frontal head-and-shoulders, 45-degree head-and-shoulders, side profile, and a closer frontal face. Every view shares one height proportion, one costume construction, and one key-light direction; only the viewing direction changes. Do not relight each view as frontal flat light.

### Scene asset images

A main-camera plate with no people, plus additional cameras added only when a shot needs one.

**Build extra cameras on demand and record which shot each was built for.** Do not pre-fill a turnaround or comparison grid; unused cameras are pure waste.

**Keep a separate written structure record**: landmarks, building-and-path connections, light-source bearings, scale relationships, and design the user specified that the image does not yet show. A drama reuses one location across many shots with changing cameras, and a new camera's consistency rests mainly on this written record — a plate of the original camera cannot serve as another camera's structure.

Draw movable parts such as doors and drawers in a stable default state, and edit from that plate when another state is needed.

### Prop asset images

A clean-ground single-object close view showing complete form and materials. Add a key structural detail view when the form is complex.

Holding relationships do not belong in a prop asset. Who holds it, in which hand, and how is handled at first-frame composition.

## First-frame composition

On platforms where reference images and first-frame mode are mutually exclusive, this is the only identity channel. Inputs are locked asset images; the output is the moment the shot begins.

- Write the state at the shot's start, not the shot's main action.
- Declare each input image's role.
- Write one sentence per character for position in frame, facing, and posture.
- State where the top and bottom frame edges fall on the body.
- Write fixed objects' visible form and open/closed state. Facts stated only in the scene plate do not carry over here automatically.

**Known failure modes with no verified fix**: left/right relationships with several characters in frame, which hand holds a prop, and door swing direction. Writing them explicitly may still produce errors. Enlarge and verify the actual image before delivery rather than treating "the prompt says so" as a pass. When a mirror or localized edit is used as the fix, record which design facts it changed — mirroring flips hinges, patterns, and accessories along with the pose.

## Medium consistency

**A named medium replaces the CG language rather than layering onto it.** For watercolor, ink wash, or painted work, do not mix in PBR, subsurface-scattering, or global-illumination terms.

**Presentation lighting and scene lighting are separate.** A sheet is a presentation image and uses neutral, slightly cool even light; a scene plate uses that scene's time and weather. Their material treatment and level of finish stay compatible.

**Photographic wording pulls a stylized project toward realism.** In animation or stylized work, avoid "real skin texture," "pores," and "photographic."

## Limits

This workflow delivers prompt text. Generate images only on a separate request.

**Identity retention has no measured evidence here.** Single-pass multi-view and the mid-gray ground have mechanical reasoning but no A/B data. GPT Image 2's actual behavior on this chain needs testing; do not promise it in advance.

**The localized-edit capability is not fully verified.** First-image-as-edit-target and mask-applies-to-first-image are documented behaviors; whether a specific edit succeeds has to be tested per case.

A written prompt does not guarantee the rendered result. Prompts, reference images, seeds, and style codes do not lock geometry or pixels. This skill does not generate control maps, reconstruct 3D, or configure image tools.
