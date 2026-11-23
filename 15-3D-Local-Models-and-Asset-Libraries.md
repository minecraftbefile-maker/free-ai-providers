# 3D — Local Models and Free Asset Libraries

> Open-weight/self-hosted model families and downloadable asset libraries. These are not hosted free APIs.

## How to use this file

Use this file to evaluate model licenses, hardware requirements, deployment complexity and asset licenses. A local model may avoid per-call API charges, but requires compute and maintenance. Do not assume an open-weight model is commercially unrestricted; inspect the exact model and dependency licenses.

## Research inventory (preserved from the source catalogue)

## 3D free asset libraries — separate from generation

- **3D Valley CC0 library:** free account-based search/download of CC0 models, PBR textures and HDRIs. This is a useful free asset retrieval API, but not a free generation quota. Its generation tools consume paid credits. Sources: https://3dvalley.com/docs/api ; https://3dvalley.com/mcp-server
- When cataloguing model libraries, verify asset license per collection/source. Do not assume every model hosted by a directory is CC0 or commercially reusable unless its own license supports that.

## Self-hosted / open-weight 3D models — separate appendix, not hosted API layers

- **Microsoft TRELLIS / TRELLIS.2:** image-to-3D model families; TRELLIS.2 is reported as requiring high-end GPU memory (24 GB+ in current model notes). Open weights can remove hosted per-call charges but require local GPU infrastructure. Official model documentation should be checked for the exact variant and license before deployment. Source lead: https://huggingface.co/buckets/huggingface/skills/tree/skills/huggingface-spaces/references/3d-models.md
- **Tencent Hunyuan3D:** image-to-3D family with model/license restrictions; do not assume commercial permission or geographic eligibility. Review the exact model card/license for each version before use.
- **TripoSR / TripoSG / Stable Fast 3D:** local model candidates, with different quality, VRAM and license constraints. A local inference package is not a hosted free API.
- **Modly / TRELLIS.cpp / ComfyUI workflows:** community-reported local workflows. Useful as separate self-hosted research leads; they are not free cloud endpoints. Reddit reports mention geometry cleanup, flipped normals/non-manifold edges, topology repair and GPU requirements as practical issues. Sources: https://www.reddit.com/r/TopologyAI/comments/1v76483/free_opensource_desktop_app_for_local_imageto3d/ ; https://www.reddit.com/r/LocalLLaMA/comments/1waonrd/anyone_tried_selfhosting_3d_object_generation/ ; https://www.reddit.com/r/TopologyAI/comments/1w7m204/the_best_local_3d_ai_generator_runs_now_natively/

## 3D Reddit community review — opening pass

| Theme | Community signal | How to interpret it |
|---|---|---|
| Free web credits vs API access | A Reddit discussion of Tripo's free tier describes monthly credits and personal-use/non-commercial limitations; it also notes that free outputs may be public. | This is a warning to check visibility and license terms, not proof of API availability or current quotas. Official API pricing must be checked separately. Source: https://www.reddit.com/r/3DPrintingTools/comments/1wbskhr/the_ultimate_free_ai_3d_generator/ |
| Local model quality | Users compare TRELLIS.2, Hunyuan3D and Stable Fast 3D, with differing views on consistency, textures, topology and license constraints. | Treat quality comments as anecdotal. The exact image, model version, GPU and cleanup workflow can change results. Source: https://www.reddit.com/r/LocalLLaMA/comments/1waonrd/anyone_tried_selfhosting_3d_object_generation/ |
| Local no-credit workflows | Community posts describe Modly and local TRELLIS-based pipelines that avoid cloud credits by using the user's GPU. | Classify as self-hosted software, not hosted API. Check the hardware requirements before recommending. Source: https://www.reddit.com/r/TopologyAI/comments/1v76483/free_opensource_desktop_app_for_local_imageto3d/ |
| Mesh cleanup | Users report that generated meshes can need retopology, normal repair, hole filling and decimation before production or 3D printing. | Evaluate usable mesh quality, watertightness, topology and texture quality, not only preview appearance. Source: https://www.reddit.com/r/TopologyAI/comments/1w7m204/the_best_local_3d_ai_generator_runs_now_natively/ |
| Printability and export | A community discussion emphasizes checking the exported mesh, printability, formats and actual free limits rather than trusting the preview. | Add downstream validation and file export to any 3D benchmark. Source: https://www.reddit.com/r/TopologyAI/comments/1wfovow/which_free_ai_3d_model_generators_are_best_for/ |

**3D Reddit conclusion:** Community reports reinforce the separation between free browser credits and developer API access, and highlight mesh cleanup/license issues. They do not establish a new recurring free API quota. No provider was promoted solely from Reddit comments.

## 3D evaluation checklist for the next research pass

- Input mode: text-to-3D, single-image-to-3D, multi-view-to-3D, sketch-to-3D; do not combine these into one score.
- Output: GLB/glTF, OBJ, FBX, STL, USDZ; whether textures/materials and UV maps are included.
- Geometry: watertightness, non-manifold edges, flipped normals, disconnected shells, polygon count, retopology and decimation options.
- Quality: shape fidelity, backside hallucination, texture consistency, fine details and repeatability.
- Usability: job polling, output URL expiry, file size, generation latency, concurrent jobs and failure/refund behavior.
- Entitlements: no key/account, recurring quota, finite trial, paid API only, or browser-only free plan.
- License/privacy: model weights license, generated asset rights, commercial-use limits, public visibility, uploaded-image retention and training use.
- Hardware: for self-hosted models, record VRAM, RAM, OS/CUDA requirements and practical runtime; never label local compute as a hosted free API.

## 3D official-source register — opening pass

- three.ws free MCP Studio docs: https://github.com/nirholas/three.ws/blob/main/docs/mcp-studio.md
- three.ws public OpenAPI announcement: https://three.ws/changelog/2026-07-18-the-free-3d-studio-now-publishes-a-machine-readable-api-description
- three.ws Forge SDK and free lane: https://github.com/nirholas/forge
- Meshy API quick start: https://docs.meshy.ai/en/api/quick-start
- Meshy API pricing: https://docs.meshy.ai/en/api/pricing
- Sloyd pricing: https://www.sloyd.ai/pricing
- 3D Valley API: https://3dvalley.com/docs/api
- 3D Valley text-to-3D prices: https://3dvalley.com/docs/api/text-to-3d
- 3D Valley MCP: https://3dvalley.com/mcp-server
- 3D AI Studio browser tool: https://3daistudio.pro/
- Hugging Face 3D model deployment notes: https://huggingface.co/buckets/huggingface/skills/tree/skills/huggingface-spaces/references/3d-models.md

**Research boundary:** This 3D section is an opening discovery pass, not a completed category audit. No live 3D generation request, account creation, payment-card entry or identity verification was performed. The three.ws no-auth API claim is documented but untested. Continue searching Layer 1 and Layer 2 before closing the 3D category.

## Open-weight / self-hosted 3D models — separate from hosted API layers

These are important because they can eliminate per-generation provider charges, but they require suitable hardware, setup, storage and maintenance. They are not “free cloud APIs.”

### Microsoft TRELLIS.2
- **Task:** image-to-3D; produces detailed textured 3D assets. It is not a native prompt-only text-to-3D model in the same sense as a hosted text generator; a text-to-image stage can be chained before it.
- **License:** Microsoft repository states MIT for the model and code, while warning that dependencies have separate licenses. Check all dependency and encoder terms before redistribution or commercial deployment.
- **Hardware:** demanding GPU/CUDA stack; do not promise it will run on low-memory integrated graphics or a CPU-only laptop. Community posts describe VRAM use varying by implementation and optimization, with some reports of 6–12 GB implementations, but those are community-specific ports/workflows, not the official baseline guarantee.
- **Source:** https://github.com/microsoft/TRELLIS.2
- **Status:** `OPEN_WEIGHT_SELF_HOSTED / MIT_WITH_DEPENDENCY_CAVEATS / HARDWARE_HEAVY`.

### Tencent Hunyuan3D 2.1
- **Task:** image-to-3D, with geometry and PBR texturing components.
- **License:** Tencent Hunyuan 3D 2.1 Community License is not a blanket permissive MIT license. The published license explicitly excludes the EU, UK and South Korea from its territory and imposes usage/distribution conditions. Do not recommend it as legally unrestricted or assume the restriction only affects hosting; the license text also governs use of outputs/results outside the territory.
- **Hardware:** substantial GPU/model storage requirements; exact VRAM depends on shape/paint configuration and optimizations. Read the model README and license for the exact revision.
- **Sources:** https://huggingface.co/tencent/Hunyuan3D-2.1 ; https://huggingface.co/tencent/Hunyuan3D-2.1/blob/main/LICENSE
- **Status:** `OPEN_WEIGHT_SELF_HOSTED / RESTRICTIVE_TERRITORIAL_LICENSE / NOT_UNIVERSALLY_USABLE`.

### TripoSR
- **Task:** single-image reconstruction, fast geometry; not equivalent to a full high-end textured text-to-3D system.
- **License:** repository states MIT for code and pretrained model.
- **Hardware:** designed for fast inference; actual speed and memory depend on GPU and settings. It is a useful lightweight baseline to compare against newer, heavier models.
- **Sources:** https://github.com/VAST-AI-Research/TripoSR ; https://github.com/VAST-AI-Research/TripoSR/blob/main/LICENSE
- **Status:** `OPEN_WEIGHT_SELF_HOSTED / MIT / IMAGE_TO_3D_BASELINE`.

### Additional local candidates
- **TRELLIS.cpp:** community C++/GGML-style port; useful for CPU/alternative-GPU experimentation, but community claims of quality/performance must be tested against a fixed benchmark. Source: https://github.com/pwilkin/trellis.cpp
- **Stable Fast 3D:** image-to-3D candidate; verify current code/weight license and dependencies before deployment. Do not infer commercial permission from the name “open source.”
- **Hunyuan3D older versions:** separate version-specific license terms apply; do not reuse 2.1 license assumptions for 2.0 or vice versa.
- **ComfyUI nodes and community wrappers:** orchestration layers, not new models or hosted APIs. Count the underlying model once.

## Free 3D asset libraries — separate from generative AI

These services can supply existing models, not create a new model from a prompt. They belong in an asset retrieval category, not in text-to-3D/image-to-3D quotas.

- **3D Valley:** free CC0 model/texture/HDRI library access is separate from paid generation/retexture/remesh endpoints. Verify the individual asset's license and source metadata. Sources: https://3dvalley.com/docs/api ; https://3dvalley.com/mcp-server
- **Other asset catalogues:** Sketchfab, Poly Haven, Kenney, ambientCG and public repositories may provide free assets under differing licenses. This is not an API-generation allowance; license must be checked asset by asset. Do not label all assets from a catalogue “CC0” unless the provider explicitly does so.

## Reddit / community review — deeper 3D signals

Reddit is useful for discovering practical failure modes and hardware constraints, but posts are anecdotal and cannot establish a provider's current free quota, API entitlement or legal license.

| Community signal | What users report | Research interpretation |
|---|---|---|
| TRELLIS.2 local quality and resource use | Users report promising image-to-3D results, but VRAM, setup difficulty, model versions and quality vary significantly. | Benchmark the exact commit/workflow and hardware; do not copy a community VRAM number as an official minimum. Sources: https://www.reddit.com/r/LocalLLaMA/comments/1waonrd/anyone_tried_selfhosting_3d_object_generation/ ; https://www.reddit.com/r/LocalLLaMA/comments/1m1yj6y |
| TRELLIS.cpp | A community maintainer reports improved asset quality after fixes and a CPU-capable path, but comments still mention performance and quality variation. | Candidate for low-cost local experimentation, not a guaranteed replacement for hosted GPUs. Source: https://www.reddit.com/r/LocalLLaMA/comments/1uyw64s/trelliscpp_now_produces_high_quality_assets/ |
| 6 GB VRAM ports | Community projects claim optimized TRELLIS.2 pipelines on 6 GB NVIDIA GPUs, including texturing/cleanup. | Treat as implementation-specific reports; verify code, supported OS/GPU, memory peaks, and output quality before citing as a baseline. Sources: https://www.reddit.com/r/StableDiffusion/comments/1v4k3je/trellis2_can_now_generate_a_highquality_3d_asset/ ; https://www.reddit.com/r/TopologyAI/comments/1vtp9ti/trellis2_can_now_run_a_full_local_imageto3d/ |
| Quality vs usable topology | Users report that attractive previews may still export meshes needing cleanup, decimation, remeshing, normal repair or manual work. | A 3D benchmark must inspect downloaded geometry, not only rendered previews. Source: https://www.reddit.com/r/ROCm/comments/1xu24o5/trellis_pixal_hunyuan/ |
| Comparing models | Community comparisons show that faster geometry-only generation and slower textured/PBR generation are different workloads; results depend on settings and hardware. | Compare geometry-only and textured outputs separately. Source: https://www.reddit.com/r/TopologyAI/comments/1w1xbt1/i_tested_4_opensource_imageto3d_models_on_the/ |
| Multi-view reconstruction | Users describe improved consistency from four-view inputs and view fusion, but these are implementation-specific pipelines. | Multi-view should be a separate category from single-image generation; do not claim all services support it. Source: https://www.reddit.com/r/TopologyAI/comments/1wcopfv/i_got_trellis2_real_4view_fusion_running_in_8_gb/ |

**Reddit conclusion:** The recurring practical theme is that “looks good in the viewer” does not equal a production-ready asset. Mesh quality, texture consistency, backside geometry, topology, polygon count, UVs, file size and cleanup effort matter. Community posts did not establish a new anonymous hosted API or recurring free API quota.

## 3D benchmark specification — what a serious comparison must test

1. **Task categories:** text-to-3D; single-image-to-3D; multi-view-to-3D; sketch-to-3D; part/scene generation; texturing of an existing mesh; retopology; auto-rigging. Never rank unlike tasks in one table.
2. **Inputs:** identical prompt, same source image(s), same image resolution, same seed where supported, same camera views, and record number of retries. Keep a simple-object test and a difficult asymmetric object test.
3. **Geometry:** silhouette fidelity; front/back consistency; missing or invented parts; watertightness; manifold edges; normals; disconnected shells; self-intersections; polygon count; scale/origin; symmetry where expected.
4. **Materials:** texture resolution; UV layout; PBR maps (base color, roughness, metallic, normal); seams; texture stretching; color fidelity; whether texture is baked or merely shown in the viewer.
5. **Exports:** GLB/glTF, OBJ/MTL, FBX, STL, USDZ; confirm that textures and materials survive download/import. A preview image is not a model export.
6. **Production suitability:** editability in Blender/Unity/Unreal; retopology; LOD/decimation; rigging; animation; 3D-printability. STL printability requires separate checks (watertightness, wall thickness, scale and mesh repair).
7. **Operational behavior:** median and p95 generation latency; queue time; concurrency; polling frequency; failed-job behavior; retry/refund policy; output URL expiry; file size; rate limit; job retention.
8. **Free entitlement:** exact account requirement, API key requirement, card requirement, country restrictions, recurring reset date, per-task credit cost, free export eligibility, model-version restriction and commercial-use restriction.
9. **Privacy:** uploaded-image retention, public gallery defaults, training use, deletion controls, signed download URL lifetime and whether user prompts/images are shared with upstream inference providers.
10. **Evidence labels:** `GENERATION_OK` only after a real API generation and download; `DOCS_VERIFIED` for official docs; `CANDIDATE_UNTESTED` where no call was made; `REPORTED_UNVERIFIED` for community reports; `CONFLICTED` where official pages disagree.

## 3D source register — expanded

### Official hosted API / pricing / product docs
- three.ws Forge SDK: https://github.com/nirholas/forge
- three.ws MCP Studio: https://github.com/nirholas/three.ws/blob/main/docs/mcp-studio.md
- three.ws OpenAPI changelog: https://three.ws/changelog/2026-07-18-the-free-3d-studio-now-publishes-a-machine-readable-api-description
- Meshy API quickstart: https://docs.meshy.ai/en/api/quick-start
- Meshy API pricing: https://docs.meshy.ai/en/api/pricing
- Tripo API billing: https://platform.tripo3d.ai/docs/billing
- Hyper3D API docs: https://docs.hyper3d.ai/en
- Hyper3D API product/pricing: https://hyper3d.ai/features/api
- Hyper3D web credit behavior: https://hyper3d.ai/help/articles/how-many-credits-does-each-hyper3d-generation-cost
- Tencent Hunyuan3D overview: https://cloud.tencent.com/document/product/1804
- Tencent Hunyuan3D FAQ: https://cloud.tencent.com/document/faq/1804/120706
- Tencent Hunyuan3D credit billing: https://cloud.tencent.com/document/product/1804/123461
- Tencent Hunyuan3D API overview: https://cloud.tencent.com/document/product/1804/120838
- Sloyd pricing: https://www.sloyd.ai/pricing
- 3D Valley API: https://3dvalley.com/docs/api

### Official open-weight model repositories and licenses
- Microsoft TRELLIS.2: https://github.com/microsoft/TRELLIS.2
- Tencent Hunyuan3D 2.1 model card: https://huggingface.co/tencent/Hunyuan3D-2.1
- Tencent Hunyuan3D 2.1 license: https://huggingface.co/tencent/Hunyuan3D-2.1/blob/main/LICENSE
- TripoSR repository: https://github.com/VAST-AI-Research/TripoSR
- TripoSR MIT license: https://github.com/VAST-AI-Research/TripoSR/blob/main/LICENSE
- TRELLIS.cpp community port: https://github.com/pwilkin/trellis.cpp

### Community and comparison leads (not quota proof)
- Voyager free model comparison (Nov 2026): https://voyager.so/blog/free-ai-3d-model-generator
- Sleipner comparison (Oct 2026): https://3d.sleipner.ai/blog/ai-3d-generators-compared
- Reddit local 3D generation: https://www.reddit.com/r/LocalLLaMA/comments/1waonrd/anyone_tried_selfhosting_3d_object_generation/
- Reddit TRELLIS.cpp: https://www.reddit.com/r/LocalLLaMA/comments/1uyw64s/trelliscpp_now_produces_high_quality_assets/
- Reddit 6GB TRELLIS.2 workflows: https://www.reddit.com/r/StableDiffusion/comments/1v4k3je/trellis2_can_now_generate_a_highquality_3d_asset/
- Reddit optimized TRELLIS.2 pipeline: https://www.reddit.com/r/TopologyAI/comments/1vtp9ti/trellis2_can_now_run_a_full_local_imageto3d/
- Reddit model comparison: https://www.reddit.com/r/TopologyAI/comments/1w1xbt1/i_tested_4_opensource_imageto3d_models_on_the/
- Reddit output quality/topology: https://www.reddit.com/r/ROCm/comments/1xu24o5/trellis_pixal_hunyuan/
- Reddit multi-view fusion: https://www.reddit.com/r/TopologyAI/comments/1wcopfv/i_got_trellis2_real_4view_fusion_running_in_8_gb/
