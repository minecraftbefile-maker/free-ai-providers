# AI 3D Generation — Hosted APIs

> Hosted text/image-to-3D API research. Free browser credits are not API credits.

## How to use this file

1. Open the provider's **official API/docs link** in its entry; do not start from an unofficial tutorial if official docs exist.
2. If the entry is marked **keyless/anonymous**, use only the documented public route. Do not add cookies, browser session tokens or guessed placeholder keys.
3. If an account is required, register on the provider's official site, verify the account only through its normal supported process, open its developer dashboard, and create an API key if the docs require one. Some providers require project creation or billing activation; the entry must say so.
4. Copy the exact endpoint, model ID, request fields and output format from the linked docs. Do not infer an endpoint from a model-list page.
5. Store keys in environment variables or a secret manager. Never commit keys into source code, Markdown, public repositories or client-side apps.
6. Send one small test request, inspect the actual generated output, then test streaming/polling if supported. A successful `/models` response is not a successful generation test.
7. Check remaining quota, reset period, shared-credit pool, card/billing requirement, data retention, output license and overage behavior before production use.

**Important:** this catalogue records documented/reported offers. Unless an entry explicitly says `GENERATION_OK`, the research did not independently run a live generation request. API schemas, registration flows and free quotas can change; follow the current official docs.

## Research inventory (preserved from the source catalogue)

# 3D Model Generation APIs and Self-Hosted Models

> Split edition of the original 23 November 2026 research ledger. Original source line range: 2341–2652, plus new audit. Provider claims and quota snapshots are time-sensitive; read each evidence label and caveat.

# Section 7 — 3D Model Generation API research (23 November 2026)

**Scope:** hosted AI services that generate downloadable 3D assets from text prompts, one or more images, or sketches. Count only an actual generation endpoint/API/MCP action when placing a provider in an API layer. Keep browser-only generators, free model libraries, local open-weight models and format-conversion tools in separate appendices. A free downloadable model library is not the same as a free generative API.

**Research allocation:** apply the standing 50% / 40% / 10% discovery effort split to Layer 1 strict keyless, Layer 2 recurring free quotas, and Layer 3 finite trial credits. This is the opening 3D pass; more discovery is required before closing the category.

## 3D Layer 1 — strict keyless / anonymous hosted generation

| Provider / endpoint | What the docs claim | Classification | Important boundaries |
|---|---|---|---|
| **three.ws — free 3D Studio / Forge** | Public free text-to-3D route and MCP endpoint; maintainer docs say no account, API key, wallet, token or payment. Generates downloadable textured GLB. The free text-to-3D lane is routed through hosted TRELLIS/NVIDIA NIM; image-to-3D may use public Hugging Face Spaces and fallback engines. An OpenAPI description is published for the free generation action. | `LAYER_1_KEYLESS / OFFICIAL_MAINTAINER_DOCS / CANDIDATE_UNTESTED` | This is a real API/MCP surface, not merely a browser UI. No numeric daily/monthly quota, concurrency guarantee or SLA was found in the reviewed docs; do not infer unlimited availability. Free lane may be busy/unavailable and higher-quality tiers are paid. Confirm output rights and endpoint stability before production use. Sources: https://github.com/nirholas/three.ws/blob/main/docs/mcp-studio.md ; https://three.ws/changelog/2026-07-18-the-free-3d-studio-now-publishes-a-machine-readable-api-description ; https://github.com/nirholas/forge |

**Layer 1 finding:** three.ws is the first strong keyless 3D-generation API candidate in this pass. Its no-auth claim is documented by the maintainer, but there has been no live generation request in this research. Do not count unrelated free browser tools as API providers.

## 3D Layer 2 — recurring / renewable free hosted API quotas

**No confirmed recurring free generation quota for a conventional 3D REST API has been established in this opening pass.** Several popular browser products advertise free guest or monthly generations, but their developer API is separately paid or not exposed on the free plan. Keep these out of Layer 2 until API entitlement is explicit.

| Provider / product | What is free | API status | Classification / decision |
|---|---|---|---|
| **Meshy** | Free web plan / Playground exists, but official API docs say a paid plan is required to create/manage personal API keys. API generation is pay-before-you-go credits. | Real API, but free-plan users cannot obtain their own API key; built-in Playground key is not a user entitlement. | `API_PAID_ONLY_FOR_USER_KEYS / EXCLUDE_LAYER_2`. Sources: https://docs.meshy.ai/en/api/quick-start ; https://docs.meshy.ai/en/api/pricing |
| **Sloyd** | Guest plan lists one AI 3D generation per day, with GLB/OBJ exports and personal-use license. | The free guest allowance is described as a web product feature; no public free API entitlement was established. | `WEB_UI_FREE_GUEST / API_UNCONFIRMED / EXCLUDE_LAYER_2`. Source: https://www.sloyd.ai/pricing |
| **3D Valley** | Search and download of its CC0 model/texture/HDRI library are free with an account. | Generation endpoints exist, but generation, retexture and remesh cost purchased credits (1 credit = $0.01); OAuth/account or API key is required. | `FREE_LIBRARY_NOT_FREE_GENERATION / EXCLUDE_LAYER_2`. Do not mistake its free asset search for free AI generation. Sources: https://3dvalley.com/docs/api ; https://3dvalley.com/docs/api/text-to-3d ; https://3dvalley.com/mcp-server |

## 3D Layer 3 — finite credits / trial allowances

- **Tencent Hunyuan3D API:** a third-party 2026 overview reports a one-time 200-credit API trial. This was not verified against a current first-party pricing page in this pass, so record only as `REPORTED_UNVERIFIED / CANDIDATE`; do not include it in the confirmed Layer 3 total until official API pricing or dashboard evidence confirms amount, eligibility and expiry. A browser demo is not proof of API credits. Source lead: https://voyager.so/blog/free-ai-3d-model-generator
- **3D Valley:** generation is paid by prepaid credits, not a documented free signup grant in the sources reviewed. Exclude from Layer 3 unless a free signup allocation is independently verified.
- **Meshy API:** generation API credits are prepaid/pay-before-use; the free web Playground does not grant a personal API key. Exclude from Layer 3.
- **Tripo / Rodin / other hosted generators:** keep as discovery candidates only until official developer pricing and a current free API grant are confirmed. Free browser plans, public demo access and free model downloads do not establish API credits.

# 3D Models — comprehensive research expansion (23 November 2026)

> **Scope and evidence rule.** This section separates hosted developer APIs from free browser interfaces, one-time credits, open-weight models, and free asset libraries. “Free to preview” is not “free to export”; “free web credits” are not API credits; API rate limits are not a recurring generation quota. No provider was marked as live-tested in this research. The source pages below were reviewed, but no account creation, API-key issuance, payment-card entry, or actual model-generation request was performed. All live-generation claims therefore remain untested unless the user independently reports use.

## Executive result

3D is unusually difficult to classify because providers expose several different products under one brand: a consumer web studio, a developer API, downloadable model weights, and sometimes a free demo. The research did **not** find a large pool of truly anonymous hosted APIs with guaranteed recurring quotas. The strongest no-key API candidate remains **three.ws Forge / 3D Studio**, whose public endpoint is documented as free-first and auth-free, but its availability depends on shared upstream engines and there is no published numeric quota or SLA. For recurring free hosted API access, no broadly usable, clearly documented monthly allowance was confirmed in this pass. Most familiar products either require paid API credits or expose their free allowance only in the browser.

The most useful free routes for actual files are therefore a mix of: (a) three.ws' shared free lane, (b) open-weight self-hosting when suitable GPU hardware exists, and (c) free web plans whose exports/rights are narrowly limited. These must not be merged into one “free API” list.

## 3D Layer 1 — anonymous/keyless hosted APIs (50% research priority)

### 1. three.ws Forge / 3D Studio — strongest candidate, not live-tested

- **Surface:** public HTTP endpoint and MCP endpoint; official SDK `@three-ws/forge`.
- **Auth:** maintainer documentation describes the free route as requiring no account, API key, wallet, payment or token. The Forge SDK describes a public auth-free `/api/forge` endpoint.
- **Input/output:** text prompt, image or sketch depending on route/backend; output is a downloadable GLB, with viewer link. The SDK describes textured geometry and optional auto-rigging. Do not assume every route/backend supports every input mode.
- **Free routing:** text prompts default to a free NVIDIA NIM / TRELLIS lane. Image-to-3D may route through public Hugging Face Spaces and fallback engines. The free lane can be busy/unavailable; higher-detail routes and bring-your-own-key geometry backends (Meshy, Tripo, Rodin) are separate paid/keyed paths.
- **Interfaces:** `https://three.ws/api/mcp-studio` (MCP Streamable HTTP); OpenAPI description announced at `https://three.ws/.well-known/3d-studio-openapi.yaml`; SDK repository `https://github.com/nirholas/forge`.
- **Quota (final audit correction):** the maintainer's current Forge pipeline documentation identifies a flagship free TRELLIS draft endpoint at `POST /api/v1/ai/text-to-3d` with **10 generations per IP per day**, returning HTTP 429 above quota and presenting a paid x402 upsell. This is a documented endpoint-specific limit, not an unlimited quota and not a guarantee that every Forge input/backend receives the same allowance. The broader `/api/forge` orchestrator still has backend/tier-specific routing and health/capacity conditions.
- **Status:** `LAYER_1_KEYLESS / MAINTAINER_DOCS_VERIFIED / 10_PER_IP_PER_DAY_DOCUMENTED / CANDIDATE_UNTESTED / SHARED_UPSTREAM_CAPACITY`.
- **Caution:** this is one gateway/service, not multiple independent providers just because it routes to TRELLIS, Hugging Face Spaces or other engines. Confirm output retention, download URL lifetime, rate limits, acceptable-use rules and rights before production use.
- **Sources:** https://github.com/nirholas/forge ; https://github.com/nirholas/three.ws/blob/main/docs/mcp-studio.md ; https://three.ws/changelog/2026-07-18-the-free-3d-studio-now-publishes-a-machine-readable-api-description ; https://three.ws/forge

### Layer 1 conclusion — final API pass

No second independent, strict anonymous hosted 3D-generation API was established. The strongest result is still three.ws, now with a documented **10 text-to-3D generations/IP/day** quota on its flagship free draft endpoint. This is enough to classify the route as a documented recurring daily keyless allowance, but not enough to claim a successful live call: this research did not submit a generation request or verify the current rate-limit response. The public Hugging Face TRELLIS.2 Space is a browser demo and may expose a Gradio route, but a public Space endpoint is not automatically a stable, quota-guaranteed anonymous service; it is not promoted as a second provider. See the final audit addendum below.

## 3D Layer 2 — recurring free hosted API quotas (40% research priority)

### Finding: no confirmed recurring free API quota yet

The following well-known services have genuine 3D APIs, but the reviewed official documentation does not establish a free recurring API generation allowance for ordinary developers:

| Provider | Genuine API? | Free web offer | API entitlement / pricing evidence | Decision |
|---|---|---|---|---|
| **Meshy** | Yes, REST API | Free web plan and Playground | Official quickstart says a paid plan is required to create/manage personal API keys; Playground uses a built-in key. API generation is pay-before-use credits. Pricing lists separate costs for text-to-3D, image-to-3D, texture refinement and related operations. | `API_PAID_PLAN_REQUIRED / EXCLUDE_LAYER_2`. Do not treat Playground access as a free user API key. Sources: https://docs.meshy.ai/en/api/quick-start ; https://docs.meshy.ai/en/api/pricing |
| **Tripo AI** | Yes, REST API | Consumer Studio has separate free-plan credits reported by its product pages | Official API billing documentation prices P1 text-to-3D at 30 credits without texture / 40 with standard texture; image-to-3D at 40 / 50. Studio credits and API wallet are separate product lines; a free Studio allowance does not prove free API balance. | `API_REAL / API_CREDITS_PAID_OR_SEPARATE / EXCLUDE_LAYER_2_UNLESS_API_GRANT_CONFIRMED`. Sources: https://platform.tripo3d.ai/docs/billing ; https://platform.tripo3d.ai/docs |
| **Hyper3D / Rodin** | Yes, authenticated HTTP API | Web workspace allows free generation/preview for some lower-quality settings; charges credits when confirming output. | API requires Bearer API key. API pricing is usage-based credits. The web “generate before confirm” workflow is not a free API quota. | `API_REAL / AUTH_AND_CREDITS / EXCLUDE_LAYER_2`. Sources: https://docs.hyper3d.ai/en ; https://hyper3d.ai/features/api ; https://hyper3d.ai/help/articles/how-many-credits-does-each-hyper3d-generation-cost |
| **Tencent Hunyuan3D API** | Yes, Tencent Cloud API | Separate browser/app promotions may exist; do not infer API entitlement from them. | Tencent official FAQ says first-time service activation can claim 100 free points/credits. Official billing says a one-time free package, valid for one year; after exhaustion it does not renew monthly. New services are being migrated to TokenHub and old platform new purchases are being stopped. | `LAYER_3_ONE_TIME_TRIAL / OFFICIAL / NOT_RECURRING`. Sources: https://cloud.tencent.com/document/faq/1804/120706 ; https://cloud.tencent.com/document/product/1804/123461 ; https://cloud.tencent.com/document/product/1804/120701 |
| **3D Valley** | Yes, API/MCP | Free CC0 asset-library search/download | Generation, retexture and remesh consume purchased credits; account/OAuth or API key required. Free library access is not generation. | `FREE_ASSET_LIBRARY_ONLY / GENERATION_PAID`. Sources: https://3dvalley.com/docs/api ; https://3dvalley.com/docs/api/text-to-3d ; https://3dvalley.com/mcp-server |
| **Sloyd** | No free API entitlement established | Guest web plan lists one generation/day, with export options and personal-use terms | The free allowance is described as a browser/guest feature. No public developer API with free guest entitlement was verified. | `WEB_UI_FREE_GUEST / API_UNCONFIRMED`. Source: https://www.sloyd.ai/pricing |

**Layer 2 conclusion:** Do not list Meshy, Tripo, Rodin, Tencent Hunyuan or Sloyd as recurring free hosted APIs based solely on free web plans, trial credits or free previews. No confirmed recurring free API quota was found among these audited services. Continue checking for newly launched providers and account-specific grants, but preserve the distinction between Studio and API balances.

## 3D Layer 3 — one-time / finite free API credits (10% research priority)

1. **Tencent Hunyuan3D API — 100 free points/credits on first activation (official).** Tencent FAQ says users can claim 100 free credits after first opening the service. The billing page describes a one-time free resource package valid for one year; it does not renew monthly. Tencent's API overview confirms actual task-submission and query endpoints. The service migration to TokenHub and platform changes mean availability and onboarding may vary by region/account. Status: `LAYER_3_CONFIRMED_DOCUMENTED_ONE_TIME / NOT_TESTED`. Sources: https://cloud.tencent.com/document/faq/1804/120706 ; https://cloud.tencent.com/document/product/1804/123461 ; https://cloud.tencent.com/document/product/1804/120838
2. **Tencent legacy per-call package:** older billing docs describe a first-activation free package for the original Hunyuan3D interface, also one-time and valid one year. Do not add this to the 100-point offer as if it were a separate independent grant; the billing system/product family has changed. Source: https://cloud.tencent.com/document/product/1804/120700
3. **Hyper3D/Rodin web preview:** free generation/preview before confirmation for selected models/quality tiers, but not free API credits. Exclude from API Layer 3. Source: https://hyper3d.ai/help/articles/how-many-credits-does-each-hyper3d-generation-cost
4. **Hitem3D / Hi3D, Krea, Tripo, Meshy, VARCO 3D, YVO3D, Masterpiece X and 3D AI Studio:** surfaced in third-party comparisons as having free web credits, preview access, or trial plans. They are not promoted to API Layer 3 without first-party proof that a free grant is usable by the public developer API. A free downloadable model or free browser generation is not enough. Discovery lead source (not entitlement proof): https://voyager.so/blog/free-ai-3d-model-generator ; https://martinolszanecki-dot.github.io/ai3dtracker/guides/meshy-alternatives/

## 3D API final audit — 23 November 2026 (category closed)

This final pass revisited the three highest-value uncertainties: the actual three.ws free quota, whether a Hugging Face TRELLIS.2 Space is a second anonymous API provider, and whether familiar free Studio credits can be used through developer APIs.

### Newly verified / corrected facts

1. **three.ws has a documented numeric daily quota.** Its Forge pipeline source lists the flagship free text-to-3D route as `POST /api/v1/ai/text-to-3d`, backed by the TRELLIS draft lane (NVIDIA NIM first, own GPU worker fallback), at **10 generations per IP per day**. Above quota it documents HTTP 429 and an x402 paid upsell. This corrects the earlier statement that no numeric quota was published. It remains one provider/gateway, not separate NIM, TRELLIS and Hugging Face providers. The quota is documented by the maintainer but was not independently exercised in a live request. Sources: https://github.com/nirholas/three.ws/blob/main/docs/forge-pipeline.md ; https://github.com/nirholas/forge ; https://three.ws/.well-known/3d-studio-openapi.yaml

2. **Hugging Face Spaces are callable APIs in principle, but this does not create a second confirmed free 3D API.** Hugging Face documents that Gradio Spaces expose API endpoints and an OpenAPI document. The Microsoft TRELLIS.2 Space exposes a Gradio interface that accepts an image, runs generation, and returns a GLB file. However, its public availability, queue/capacity, token requirements, and stable anonymous usage allowance were not confirmed in this audit. Keep it as `PUBLIC_SPACE_API_CANDIDATE_UNVERIFIED`, not a confirmed Layer 1 provider. Sources: https://huggingface.co/docs/hub/spaces-api-endpoints ; https://huggingface.co/spaces/microsoft/TRELLIS.2/blob/main/app.py

3. **Meshy Playground is not a personal free API entitlement.** Reddit users reported that the Playground became accessible on free accounts, allowing a browser test and copying the generated request. That is useful for inspecting request shape, but it does not override Meshy's official documentation that creating/managing personal API keys requires a paid plan. Status remains excluded from free API layers. Sources: https://www.reddit.com/r/meshyai/comments/1w3jhqc/the_api_playground_is_now_open_on_the_free_plan/ ; https://docs.meshy.ai/en/api/quick-start

4. **Tripo Studio credits and Tripo API credits are separate.** Its Studio pricing page lists a free monthly Studio allocation; API docs have their own prepaid credit wallet and task costs. The developer API pricing page currently mentions 300 free credits in a two-week context, but the exact eligibility/claim mechanics were not verified in a dashboard. Keep this as a finite Layer 3 lead only, not a recurring API quota. Sources: https://tripo3d.ai/product-doc/getting-started/pricing-credits ; https://docs.tripo3d.ai/get-started/pricing.html ; https://developers.tripo3d.ai/en/pricing

5. **Rodin free previews are still browser-only evidence.** Hyper3D's pricing table shows no API access on the Free tier; API access is tied to higher plans and Bearer-key authentication. Free preview-before-confirmation in the web workspace must not be counted as API generation. Sources: https://hyper3d.ai/pricing ; https://docs.hyper3d.ai/en/get-started/quick-start

6. **Tencent's API allowance remains a one-time grant, not monthly.** Official billing identifies a 200-credit one-time resource package for Tencent HY 3D Global, valid one year. Earlier Tencent Hunyuan3D product pages/FAQ also describe a 100-credit first-activation grant for a legacy product route. These are product/version-specific; do not add them together as if one account receives both. Verify the exact product in the Tencent console before relying on either. Sources: https://www-sg.tencentcloud.com/document/product/1281/74121 ; https://cloud.tencent.com/document/faq/1804/120706 ; https://cloud.tencent.com/document/product/1804/123461

### Final API classification

| Layer | Final result | Status |
|---|---|---|
| Layer 1 — anonymous/keyless | three.ws Forge flagship free text-to-3D endpoint; 10 generations/IP/day documented | `DOCS_CONFIRMED / LIVE_CALL_UNTESTED / SHARED_CAPACITY` |
| Layer 1 — additional candidates | Microsoft TRELLIS.2 public Hugging Face Space | `CANDIDATE_UNVERIFIED / NOT_COUNTED_AS_SECOND_PROVIDER` |
| Layer 2 — recurring API quota | No independent provider with a clearly documented recurring free API balance confirmed | `NO_CONFIRMED_PROVIDER_FOUND` |
| Layer 3 — finite API credits | Tencent HY 3D one-time package (200 credits for Global product; legacy 100-credit Hunyuan route is separate); Tripo 300-credit API trial wording requires dashboard confirmation | `DOCUMENTED_ONE_TIME / CANDIDATE_TRIAL` |

### Reddit final review

The final Reddit pass added three useful signals, none of which establishes a free quota:

- **Local image-to-3D pipelines:** community users describe local toolkits combining TRELLIS.2, Hunyuan3D and Stable Fast 3D with mesh repair, Blender cleanup and texture work. This is self-hosted software, not a hosted API. Source: https://www.reddit.com/r/TopologyAI/comments/1wqq4lf/a_free_local_imageto3d_pipeline_with_mesh_cleanup/
- **Meshy Playground:** a free-plan Playground report describes browser generation and request-code export, but official API-key requirements still govern direct API entitlement. Source: https://www.reddit.com/r/meshyai/comments/1w3jhqc/the_api_playground_is_now_open_on_the_free_plan/
- **Output quality remains variable:** users report that GLB size, polygon count, texture size, seed sensitivity and geometry cleanup can dominate whether an asset is actually usable. Source: https://www.reddit.com/r/ROCm/comments/1xu24o5/trellis_pixal_hunyuan/

Reddit remains anecdotal and is not used to infer account entitlements, quota numbers or licenses.

### Closure boundary

The **hosted 3D-generation API research phase is now closed** at the evidence level requested: one strong documented keyless daily API route, no confirmed recurring account-based free API quota, and a small number of one-time trial routes. This is not a claim that every API was live-tested. No account was created, no card/identity check was entered, and no model was generated or downloaded during this research pass. A future hands-on test should call three.ws, save the returned GLB, inspect it in Blender, and verify the 10/IP/day behavior before production reliance.

### Next research category: Web UI

The next phase is **Web UI**. Treat it as a separate category from model-generation APIs: research hosted web interfaces, browser-based AI workspaces and free web tools on their own merits, and do not count a Web UI free allowance as API access. The API inventory is complete for this pass; do not reopen it unless new first-party evidence appears.

## Current 3D category status

- **Layer 1:** one documented anonymous hosted API candidate (three.ws), with 10 text-to-3D generations/IP/day documented in the maintainer pipeline; not live-tested; shared capacity applies.
- **Layer 2:** no confirmed recurring free hosted API quota found among audited providers. Popular free browser tiers are kept separate.
- **Layer 3:** Tencent HY 3D Global one-time 200-credit package (plus a separate legacy Hunyuan route documented at 100 credits); Tripo API 300-credit trial wording remains dashboard-unconfirmed; none is recurring.
- **Self-hosted:** TRELLIS.2, Hunyuan3D 2.1, TripoSR and TRELLIS.cpp are documented separately with license/hardware caveats.
- **Asset libraries:** separated from generation.
- **API research phase closed, not live benchmarked.** Real outputs were not generated, downloaded or checked in Blender. Next category is Web UI; keep Web UI allowances separate from API entitlements.


---

# 3D provider expansion — additional audit (23 November 2026)

## Current hosted API finding: three.ws

**three.ws Forge / 3D Studio** remains the strongest documented keyless hosted API candidate in this inventory. Its published OpenAPI announcement says the free text-to-3D endpoint is callable without an account, API key or payment. The Forge interface describes text and photo input, textured downloadable models and a free draft lane. The maintainer's pipeline document lists `POST /api/v1/ai/text-to-3d` and a quota of 10 generations per IP per day, with HTTP 429 above quota and a paid x402 upsell. Because separate examples in the ecosystem describe an account/key for a different `/api/3d/generate` route, do not confuse endpoints: record the exact path and authentication mode for the free flagship endpoint. No live generation request was made in this research. 

- OpenAPI announcement: https://three.ws/changelog/2026-07-18-the-free-3d-studio-now-publishes-a-machine-readable-api-description
- Forge interface: https://three.ws/forge
- Pipeline endpoint/quota documentation: https://github.com/nirholas/three.ws/blob/main/docs/forge-pipeline.md
- Separate MCP endpoint: https://github.com/nirholas/three.ws/blob/main/docs/mcp-studio.md
