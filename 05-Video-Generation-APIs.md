# AI Video Generation — Hosted APIs

> Hosted video-generation API research only. Browser generators are in `06-Video-Generation-Web-UI.md`.

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

# Video-generation API research — focused pass 1 (23 November 2026)

This is the first dedicated video pass. It follows the same three-layer scheme used elsewhere in this directory. Only real programmatic video-generation endpoints are considered. Browser-only video generators, free playgrounds, model directories, self-hosted weights and general-purpose video editing/transcoding quotas are not counted as free video-generation APIs.

**Important billing rule:** a monthly credit balance is not the same as a guaranteed number of videos. Video cost changes by model, duration, resolution, audio, reference inputs and retries. Where a provider publishes a dollar balance, the approximate number of clips below is calculated only from the provider's stated example rate and is not a fixed entitlement.

## Layer 1 — keyless / anonymous video-generation APIs

**No new provider is confirmed in strict Layer 1.** The strict definition requires an actual video-generation request to succeed without an account, API key, placeholder key, cookie, browser session or delegated login. None of the reviewed video candidates met that standard with sufficiently reliable evidence.

- **Magic Hour web generator is not a keyless API.** Its FAQ advertises three free web generations per day, shared by users on the same network, but that is a browser allowance, not evidence of an anonymous developer endpoint. Do not list it in Layer 1. API access is separately documented and its free API credit amount was not established in the reviewed official material. Sources: https://magichour.ai/faq ; https://docs.magichour.ai/
- **Google Flow / Google Vids:** browser/app credits or free clip allowances do not transfer to Gemini/Veo API inference. The Gemini API pricing table must be checked per video model; the reviewed 2026 evidence lists video generation as unavailable in the API free tier. Sources: https://ai.google.dev/gemini-api/docs/pricing ; https://support.google.com/flow/
- **Pollinations and anonymous image endpoints:** do not infer that an image endpoint or historical anonymous text route also provides anonymous video generation.

## Layer 2 — recurring free video API quotas

| Provider | API model / exact free allowance | Access and recurrence | Classification, limitations and confidence | Official source |
|---|---|---|---|---|
| **Agnes AI** | `agnes-video-2.5-flash` is documented at **$0 per output second** as a limited-time promotion. The provider's model catalogue gives a free/default effective limit of approximately **1 executable request/minute** (public reference 2 RPM). | Agnes account and API key; OpenAI-compatible API base `https://apihub.agnes-ai.com/v1`. Video job creation uses `/v1/videos`; retrieve the result using the documented `video_id` polling endpoint. | `PROMOTIONAL_FREE_MODEL / RATE_LIMITED / NOT A PUBLISHED DAILY CREDIT`. This is the strongest current recurring-like API offer found in this pass, but it is explicitly a promotion and may be changed or withdrawn. Do not call it a permanent free tier or assume unlimited concurrency. The regular `agnes-video-2.5` model is paid. | https://github.com/AgnesAI-Labs/skills/blob/main/agnes-ai-models/references/model_catalog.md ; https://github.com/AgnesAI-Labs/AgnesAI-Models/blob/main/docs/FAQ.md |
| **Pixazo API — LTX Video 2.5** | Current Pixazo Free Tier page advertises **US$5/month for video**, with LTX Video 2.5 at **US$0.45 per 5-second 1280×704 video**, approximately **11 clips/month** if the whole video balance is used on that model. It says balances reset monthly and 60 requests/minute per API. | API account/key. The free-tier landing page says no card is needed; however, the site's Terms of Use state that the free tier requires at least one **US$10 wallet top-up**, and another API page says card or US$10 top-up is needed. | `RECURRING_MONTHLY_CREDIT / TERMS_CONFLICT`. Do **not** mark as no-card or universally free until the contradictory official pages are reconciled. Treat as a conditional monthly balance with a possible top-up gate. The video balance is separate from Pixazo's image and audio balances; do not double-count it. | https://www.pixazo.ai/pixazo-free-tier ; https://www.pixazo.ai/terms-of-use ; https://authv2.pixazo.ai/api/video-generation |

## Layer 3 — one-time trials, free runs and application grants

| Provider | Free video API allowance | Access / card | Classification and restrictions | Official source |
|---|---|---|---|---|
| **Replicate — Try for Free collection** | Selected models include `minimax/video-01` (text-to-video and image-to-video), `luma/reframe-video` (video reframing) and `topazlabs/video-upscale`. The collection allows a limited number of free runs; the provider does **not** publish one universal run count. | Replicate account. The collection says free runs can be used before purchasing credits; billing must be added after the free allowance is consumed. Initial card requirement is not stated clearly in the reviewed collection. | `FINITE_MODEL_SPECIFIC_FREE_RUNS`. This is genuine API inference for selected models, not a recurring monthly quota and not a promise that every hosted video model is free. Review the individual model license and commercial-use terms. | https://replicate.com/collections/try-for-free ; https://replicate.com/docs/topics/billing |
| **Runware — Starter startup credits / grant** | Up to **US$1,000** in credits for an approved bootstrapped or pre-seed startup; credits can be spent on Runware's video-generation APIs as well as image, audio, 3D and language models. The Starter award is assessed in US$100 steps and does not expire. | Application and approval. Provider asks for a real working product or credible MVP, a business email on the company's own domain, website, and a plan to build on Runware. No deposit for Starter; higher Growth/Scale tiers require large deposits and are not free. | `APPLICATION_GRANT / STARTUP_ONLY / NOT_AUTOMATIC`. Not a general individual signup bonus or a recurring personal quota. The program is for eligible early-stage teams; do not imply that an ordinary personal account qualifies. | https://runware.ai/startup-program ; https://runware.ai/grant-program |
| **Cloudinary Image-to-Video add-on** | The official beta documentation describes a one-time free allocation: **16 credits on the Free Cloudinary plan**, enough for up to 16 seconds without audio or 8 seconds with audio. The page also describes earning up to 20 additional credits through return/feedback tasks. | Cloudinary account and API credentials. The add-on must be enabled; API uses Basic Authentication with API key and secret. | `ONE_TIME_ADDON_TRIAL / BETA / ADDON_ACCESS_REQUIRED`. Although a programmatic API exists, this is a trial allocation, not a recurring free video API. The add-on is separately metered; do not confuse it with Cloudinary's general 25 monthly media credits. Verify current add-on availability before integration. | https://production.cloudinary.com/documentation/image_to_video_addon ; https://cloudinary.com/pricing |
| **Volcengine Ark / Seedance — disputed trial reports** | Several Volcengine-hosted articles describe Seedance trial campaigns (for example 1,000 tokens or about 100 seconds of 720p output, with short validity periods). However, the current official Seedance 2.5 API guide says the model must be enabled with account balance above RMB 200, a qualifying savings plan, or a purchased model resource package. Other official campaign material says some free allowances are activity-specific, real-name verified and limited to short clips. | Volcengine account, API key, model activation; China-oriented service. Some activity access requires real-name verification. | `CONFLICTED_CAMPAIGN / REGION_AND_IDENTITY_RESTRICTED / NOT_GENERAL_FREE_TIER`. Do not count the reported trial as a generally available free API quota. Only include a specific campaign after its current official campaign page, eligibility, validity and billing guard are confirmed. Never enable automatic overage billing based on an assumption that the trial is isolated. | https://docs.volcengine.com/docs/ark/seedance-2-5?lang=en ; https://docs.volcengine.com/docs/ark/create-video-generation-task-api?lang=zh ; https://www.volcengine.com/article/2687252 |

## Providers checked and excluded from free video API layers

| Provider / product | Finding | Why it is excluded | Official source |
|---|---|---|---|
| **Google Gemini API / Veo** | The reviewed API pricing table lists no free tier for video generation models. | Free Flow/Vids browser credits are not API credits. | https://ai.google.dev/gemini-api/docs/pricing |
| **Runway Dev API** | Developer API generations consume credits; credits are purchased at US$0.01 each. | Free website plan does not provide free developer API inference. | https://docs.dev.runwayml.com/guides/pricing/ |
| **Luma API** | Luma Agents API is pay-as-you-go from the first generation; official FAQ says there is no API free tier. | Free web-app draft credits do not transfer to the API. | https://docs.agents.lumalabs.ai/guides/faq/ |
| **HeyGen API** | API is pay-as-you-go and requires purchased API credits to unlock. | A free creator account is not a free video-generation API entitlement. | https://help.heygen.com/en/articles/10060327-heygen-api-pricing-credits-explained |
| **Magic Hour API** | Official FAQ says developers can get started with the API for free, but the reviewed official API/pricing pages did not state a numeric free API grant. The well-described three-per-day allowance applies to the web generator and is shared by network, not documented as API quota. | `API_FREE_AMOUNT_UNVERIFIED`; retain as a candidate until an API key can actually submit and complete a generation without payment. | https://magichour.ai/faq ; https://docs.magichour.ai/ ; https://magichour.ai/pricing |
| **fal.ai** | Some model playground pages advertise free test runs, but this pass did not verify a general free video API quota. | A free generator-page run is not automatically API inference. The separate Builder Grant is an application program, not a general free tier. | https://fal.ai/pricing ; https://fal.ai/builder-grant |
| **Kling / Pika / MiniMax / xAI video APIs** | Reviewed API pricing evidence lists paid usage or paid packages rather than a general recurring free API tier. | Do not copy website daily credits or mobile-app trial units into API layers. | https://klingai.com/global/dev ; https://pika.art/api ; https://platform.minimaxi.com/document ; https://docs.x.ai/docs/models |

## Discovery and verification notes

- **Pixazo requires a conflict flag:** its Free Tier marketing page says US$5 video credit each month and no card to start, while the official Terms of Use and API video page describe a minimum US$10 wallet top-up or card to unlock. Keep the monthly video balance visible, but classify the eligibility as conflicted/top-up-gated until the account flow and terms agree.
- **Agnes is not a confirmed forever-free offer:** the model catalogue calls the $0 video price a limited-time promotion and warns that prices and limits can change. It is a useful API candidate, but recheck the model page before relying on it.
- **Replicate's free runs are finite:** no universal number is published, and the free collection can change. Do not multiply the free-run allowance by the number of models or assume it resets monthly.
- **Cloudinary's general monthly credits are not video-generation credits:** only the separate Image-to-Video add-on allocation counts here.
- **Runware's startup grant is not a personal free plan:** it is application-based and requires a credible product/company presence. The no-deposit Starter grant is distinct from Growth/Scale tiers that require deposits.
- **Volcengine campaign claims conflict with model-activation documentation:** campaign trials are not equivalent to a public default free tier. Require an explicit currently open campaign and account-specific quota before counting it.
- **No API test was executed using a live provider account in this pass.** These classifications are based on published documentation and pricing, not a claim that an authenticated video job was successfully rendered during this session.

## Video discovery sources (for finding candidates, not proof of free access)

- https://aifree.dev/learn/free-video-generation-api — recent video API offer tracker; use for discovery and compare every claim with provider documentation.
- https://blog.laozhang.ai/en/posts/best-free-ai-video-api — provider-by-provider overview; use as a lead list, not as final billing evidence.
- https://www.veed.io/learn/best-image-to-video-api — image-to-video API discovery overview; free-plan statements need model/provider confirmation.
- https://replicate.com/collections/try-for-free — live finite-free-run collection maintained by Replicate.

## Video pass 1 inventory

- **Layer 1:** zero newly confirmed strict-keyless video APIs.
- **Layer 2:** Agnes `agnes-video-2.5-flash` (limited-time $0 promotional model, approximately 1 effective request/minute); Pixazo LTX Video 2.5 monthly balance (US$5/month advertised, but card/top-up eligibility conflicts across official pages).
- **Layer 3:** Replicate selected finite free runs; Runware startup grant (application-only); Cloudinary Image-to-Video add-on one-time credits; Volcengine Seedance campaign reports retained as disputed/conditional, not confirmed general access.
- **Explicit exclusions:** Google Veo API, Runway Dev, Luma API, HeyGen API and ordinary Kling/Pika/MiniMax/xAI API access are not listed as free general-purpose video APIs based on the reviewed official pricing pages. Magic Hour and fal remain candidates where API-specific free quota was not established.

**Next modality in the requested sequence: AI music generation.**

### Layer 1 deep search — public anonymous video inference (23 November 2026)

This pass deliberately searched beyond free-API directories: Hugging Face Spaces API documentation and live Space repositories, ZeroGPU quota documentation, independent anonymous-generation measurements, GitHub integration code, and public video-generator wrappers. The strict Layer 1 definition remains unchanged: the caller must be able to submit an actual generation request without creating an account, supplying an API key or placeholder key, sending a cookie/browser session, or delegating an authenticated login. A public endpoint is not automatically reliable or production-safe.

#### Layer 1 finding: Hugging Face public Gradio Spaces on ZeroGPU — confirmed platform-level keyless route, experimental

Hugging Face documents that public Gradio Spaces expose API endpoints callable from Python, JavaScript, or raw HTTP. Its current ZeroGPU documentation explicitly publishes an **unauthenticated allowance of 2 minutes of GPU time**, separate from the free-account allowance of 5 minutes. Unauthenticated calls use a shared pool and stricter limits. This means a public ZeroGPU Space can qualify for Layer 1 when its own app is public and does not impose an additional visitor login/token requirement. It is a shared demo/compute platform, not a dedicated commercial video API provider, and its GPU quota is time-based rather than a number of clips.

Official platform references:
- Spaces as API endpoints: https://huggingface.co/docs/hub/spaces-api-endpoints
- ZeroGPU quota and anonymous access: https://huggingface.co/docs/hub/main/spaces-zerogpu

Specific video-generation Spaces discovered:

| Public Space / model | Video task | API and keyless evidence | Quota / reliability | Layer 1 status |
|---|---|---|---|---|
| **Lightricks / ltx-video-distilled** | LTX text/image-to-video demo; Space metadata says it is running on ZeroGPU. | Public Gradio Space; public Spaces expose Gradio API endpoints. No visitor token is documented as a prerequisite for public Space access. | Uses shared ZeroGPU; anonymous platform allowance is 2 GPU minutes per 24-hour usage window (the quota reset is 24 hours after first use). Queue availability and the Space's current health can change. | `KEYLESS_PLATFORM_ENDPOINT / ANONYMOUS_QUOTA / EXPERIMENTAL` |
| **zerogpu-aoti / wan2-2-fp8da-aoti-faster** | Wan 2.2 image-to-video. | A November 11, 2026 community measurement explicitly called the public Space through `gradio_client` from a CPU-only Linux machine **without a Hugging Face token**. The article provides the exact Space ID and API function `/generate_video`. | The same measurement recorded anonymous ZeroGPU quota exhaustion after a small number of attempts and replica-routing problems. It is a real working proof, but not a dependable high-volume endpoint. | `ANONYMOUS_GENERATION_REPORTED / LIMITED_AND_FRAGILE` |
| **Wan-Animate-2 public demo on wan2.video** | Image + audio/speech to animated video; the public Space exposes `/animate`. | Its documentation says anonymous access is possible and that it can be called through the public Gradio `/animate` endpoint. | Anonymous users have a smaller two-minute daily quota and stricter shared pool; current UI controls limit clips to 1–5 seconds and 320–640 px. This is a public demo, not a separate vendor API SLA. | `KEYLESS_PUBLIC_SPACE / EXPERIMENTAL` |
| **AnimateLCM-SVD public ZeroGPU Space(s)** | Still-image animation / image-to-video. | The November 11 measurement article reports anonymous calls to public Spaces and successfully generated clips without an HF token. | In that test, the selected SVD Space requested 180 GPU seconds and was rejected when the remaining anonymous quota was lower. Treat it as a candidate only when the current Space's requested duration fits the anonymous allowance. | `ANONYMOUS_GENERATION_REPORTED / SPACE_AND_QUOTA_DEPENDENT` |

Primary evidence for these entries:
- Lightricks Space page and ZeroGPU status: https://huggingface.co/spaces/Lightricks/ltx-video-distilled
- Independent measured Wan 2.2 and SVD anonymous API calls (Nov 11, 2026): https://huggingface.co/blog/Jacob123222/image-to-video-huggingface
- Wan-Animate-2 public demo, endpoint, anonymous quota and control limits: https://wan2.video/wan-animate-2
- Hugging Face API docs explain that public Gradio Spaces can be called via the generated API endpoints and that an Authorization header is for private Spaces / better public rate limits, not a universal requirement for public Spaces: https://huggingface.co/docs/hub/spaces-api-endpoints

**Important interpretation:** the 2-minute anonymous ZeroGPU quota is a platform-wide GPU-time allowance, not 2 minutes per Space and not a fixed number of generated videos. A single long job can consume the allowance or be rejected before generation if the Space requests more GPU time than remains. Do not promise a daily video count. The Space owner can pause, change, gate or delete the app; shared replicas can also make queued jobs unreliable. Avoid sending private images, faces, documents or other sensitive media to public community demos.

#### Layer 1 candidates found but not promoted to confirmed

- **CVRON public WAN 2.2 I2V proxy** — its public repository documents `GET https://cvron.alwaysdata.net/cvronai/wan22.php?prompt=...&image=...` and claims a video URL response without an API key. However, this is a community-operated relay rather than a model vendor, and this pass did not establish current uptime, successful generation, operator identity, retention policy, or whether the upstream is still active. Keep as `UNVERIFIED_PUBLIC_RELAY`, not a confirmed provider. Discovery source: https://github.com/cvroon-api/FreeAiAPIs
- **Veo AI Free (`veoaifree.com`)** — a GitHub integration describes a WordPress AJAX wrapper that obtains a CSRF nonce from the page, then posts to `wp-admin/admin-ajax.php`; it claims six requests/hour/IP. Because the flow uses browser cookies/session state and a CSRF nonce, it fails this project's strict no-cookie/no-session Layer 1 definition. Keep it in the excluded/wrapper notes, not the confirmed Layer 1 list. Source: https://github.com/diegosouzapw/OmniRoute/issues/2365
- **Wan2.Video main generator and other no-signup websites** — the website offers no-signup text/image-to-video generation through public queues, but a website UI by itself does not establish a callable API endpoint. Only the specifically documented public Gradio Space `/animate` path above is retained as an API candidate. Source: https://wan2.video/
- **LTX AI no-signup web generator** — its page advertises browser-based generation without signup or API key, but no independently documented public developer endpoint was established. Exclude from API Layer 1 until an actual public API route is documented. Source: https://www.ltx-ai.net/api
- **Agnes AI** — excluded from Layer 1 because its real video API requires an Agnes API key, even though the key is free and its generation model is temporarily priced at $0. It belongs in Layer 2 while the promotion remains active. Source: https://video.lichuanyang.top/en/api-docs

#### Layer 1 conclusion after expanded search

The earlier statement “zero newly confirmed strict-keyless video APIs” is refined: **there is now one confirmed keyless access class — public Hugging Face Gradio Spaces running on ZeroGPU — with multiple video Space examples.** It is not a dedicated vendor-wide video API; it is an anonymous, quota-limited public demo/API route. Wan 2.2 anonymous generation has a documented real-call measurement without an HF token. Wan-Animate-2 documents the public `/animate` API and anonymous use. Lightricks' public ZeroGPU Space is an additional live candidate whose public API follows the official Spaces API mechanism. All remain experimental, shared-capacity endpoints, not production guarantees.

No standalone commercial video vendor was verified in this pass to offer a stable, direct, anonymous REST video-generation API with no key, cookie, session or account. Keep that distinction explicit rather than inflating Layer 1 with free websites or cookie-backed wrappers.

### Layer 1 deep-search supplement — additional public video Spaces and endpoint verification (23 November 2026)

This supplement expands the public-space sweep without changing the strict Layer 1 definition. A public Space counts only when the actual Gradio inference endpoint can be called without a Hugging Face token, account cookie, browser session, or placeholder credential. The official Hugging Face documentation confirms that public Gradio Spaces expose API endpoints and that the Authorization header is required for private Spaces or may improve public rate limits; it is not a universal requirement for public Spaces. The same documentation states that unauthenticated ZeroGPU callers receive a small shared GPU allowance (2 minutes), while free authenticated accounts have a separate 5-minute daily allowance. These are platform compute-time quotas, not per-model clip quotas.

Official API mechanics and quota:
- Public Space API endpoints and REST/Gradio client access: https://huggingface.co/docs/hub/spaces-api-endpoints
- ZeroGPU quota and anonymous usage: https://huggingface.co/docs/hub/main/spaces-zerogpu
- The API endpoint name and input schema are Space-specific; inspect the Space's “Use via API” page or `/gradio_api/openapi.json` before calling it. Do not assume every Space uses `/predict`.

#### Additional public Spaces discovered

| Public Space | Video task / endpoint evidence | Strict-keyless assessment | Status and cautions |
|---|---|---|---|
| `Hamzakhan1/wan2.2-text-image-to-video` | Wan 2.2 TI2V-5B Space README describes text-to-video and image-to-video, with ZeroGPU support. Gradio public API can expose its generation callback. | Public Space is eligible for anonymous API use only if the live endpoint does not add its own visitor authentication. | `PUBLIC_SPACE_CANDIDATE`; no independent successful no-token request was found in this pass. Do not promote to confirmed generation. Source: https://huggingface.co/spaces/Hamzakhan1/wan2.2-text-image-to-video |
| `yuknassty/wan2-2-image-to-video` | Source code exposes a Gradio `generate_video` callback for Wan 2.2 I2V; the app is configured for ZeroGPU. | Public Space / Gradio route, but the repo page alone does not prove anonymous successful generation at the current time. | `PUBLIC_SPACE_CANDIDATE`; needs a fresh no-token API call. Source: https://huggingface.co/spaces/yuknassty/wan2-2-image-to-video |
| `r3gm/wan2-2-fp8da-aoti-preview` | Identified as a backup Wan 2.2 I2V Space in the November 11 anonymous measurement. | Anonymous invocation was attempted as part of the same multi-Space test. | `ANONYMOUS_TESTED_BUT_FRAGILE`; the measurement describes replica-routing and quota problems, so do not claim reliable completion for every request. Source: https://huggingface.co/blog/Jacob123222/image-to-video-huggingface |
| `Saravutw/WAN2.2_I2V_LIGHTNING_4-8step_custom` | Identified as another Wan 2.2 I2V backup in the November 11 test. | Included in the no-token test sweep. | `ANONYMOUS_TESTED_BUT_FRAGILE`; retain as an experimental Space, not a stable provider. Source: https://huggingface.co/blog/Jacob123222/image-to-video-huggingface |
| `Lightricks/ltx-video-distilled` | Official Lightricks Space source code exposes `text_to_video`, `image_to_video`, and `video_to_video` generation callbacks. | Public Gradio endpoint with ZeroGPU; eligible for the platform's anonymous shared allowance unless the live Space changes its access settings. | `PUBLIC_KEYLESS_ROUTE / SHARED_QUOTA`; source code confirms endpoint names and modes, but this pass did not execute a fresh generation. Source: https://huggingface.co/spaces/Lightricks/ltx-video-distilled |
| `OpenKing/wan2-video-generation` | A public Space catalog validator lists `/generate_video` as its endpoint. | Public endpoint is discoverable, but anonymous access alone does not prove a completed generation. | `PUBLIC_SPACE_CANDIDATE / QUEUE_FULL_AT_LAST_CHECK`; catalog smoke test on Nov 22 reported `Queue is full`. Source: https://huggingface.co/datasets/gradio/workflow-curated/blame/main/curated.json |
| `makiblek/Wan_2.2_I2V_14B_Custom_Lora_Wow` | Public catalog identifies an image-to-video Space and `/generate_video`. | Public ZeroGPU Space; eligible in principle for anonymous shared capacity if no extra auth is configured. | `PUBLIC_SPACE_CANDIDATE`; catalog validator reported status `ok` on Nov 22, but this is not proof of a full no-token generation. Source: https://huggingface.co/datasets/gradio/workflow-curated/blame/main/curated.json |
| `multimodalart/ltx2-audio-to-video` | Public catalog identifies a ZeroGPU LTX audio-to-video Space with `/generate`. | Public endpoint candidate; audio-conditioned video is a separate task from text-to-video. | `PUBLIC_SPACE_CANDIDATE`; catalog validator reported status `ok` on Nov 22, but no independent no-token output was captured here. Source: https://huggingface.co/datasets/gradio/workflow-curated/blame/main/curated.json |

#### Independent anonymous-generation evidence and limits

A November 11, 2026 community measurement called public Wan 2.2 and Stable Video Diffusion Spaces through `gradio_client` on a CPU-only Linux machine without a Hugging Face token. Across 24 attempts, five produced a clip, five were lost to replica-routing problems, and fourteen were rejected by quota or run limits. This is useful proof that public video inference can work anonymously, but it also demonstrates why these endpoints must be labelled experimental rather than dependable. In that measurement, an SVD Space requesting 180 GPU-seconds was rejected when the remaining anonymous allowance was only 159 seconds; an AnimateLCM-SVD request using 60 seconds fit more often. Source: https://huggingface.co/blog/Jacob123222/image-to-video-huggingface

#### Exclusions and classification safeguards

- **Hugging Face Inference Providers video task** is not Layer 1: its documented example uses an `HF_TOKEN` and a provider API key. Public model weights or a model card do not create a free hosted API. Source: https://huggingface.co/docs/inference-providers/tasks/text-to-video
- **Wan2.Video and other no-signup generator websites** are not automatically API providers. Include only an actual public API endpoint with a documented request schema; a browser UI or a link to a Space is insufficient. Source: https://wan2.video/
- **Sisif** is not free: its no-account path returns a payment challenge and charges $1 for a five-second clip. Do not place it in Layer 1 merely because it can initiate a payment without a prior account. Source: https://sisif.ai/api/
- **Agnes AI** remains Layer 2, not Layer 1, because its REST API requires a free API key. Source: https://video.lichuanyang.top/en/api-docs
- **Open-source model repositories, Xinference, MAX, ComfyUI, and local Wan/LTX deployments** are self-hosted software, not hosted free anonymous APIs. They belong in a self-hosted appendix, not Layer 1. Sources: https://inference.readthedocs.io/en/v4.0.1/models/model_abilities/video.html ; https://max.modular.com/serve/video-generation/

#### Revised Layer 1 verdict — video generation

The broader search found several public Gradio/ZeroGPU Spaces and one independently measured no-token generation route class. The strongest evidence remains the anonymous Wan 2.2/SVD test and the official Hugging Face statement that unauthenticated ZeroGPU use has a shared compute allowance. Additional Wan/LTX Spaces are listed as candidates, not as independently confirmed working endpoints. **There is still no verified stable, commercial, anonymous video REST API with guaranteed free output.** Layer 1 here means experimental public inference endpoints, subject to shared queues, short GPU-time quotas, replica issues, app-owner changes, and possible outages. Never count each Space as a separate daily quota: the anonymous ZeroGPU allowance is shared at the platform level.

### Layer 1 expansion — additional anonymous video-generation Spaces (23 November 2026)

This is an additive research pass. It does not replace the existing Layer 1 entries and does not claim that every listed Space has completed a fresh anonymous generation test. The useful distinction is between (a) the platform's documented anonymous API/compute capability, (b) a live public Space whose app exposes a video-generation function, and (c) a successful end-to-end no-token generation measured by an independent tester.

#### Newly discovered public video endpoints / Spaces

| Public endpoint / Space | Video capability shown by its public project page or catalog | Layer 1 classification | Evidence / operational notes |
|---|---|---|---|
| `victor/lingbot-video` | LingBot-Video MoE 30B-A3B; text-to-video and image-to-video; public Gradio Space running on ZeroGPU. | `PUBLIC_ZERO_GPU_CANDIDATE`; anonymous API use is plausible under public Space rules, but no fresh anonymous video completion was verified in this pass. | Space README says it is running on ZeroGPU and describes T2V/I2V. It skips the refiner stage to fit ZeroGPU and targets short clips (up to 4 seconds at 24 fps). Source: https://huggingface.co/spaces/victor/lingbot-video/blob/main/README.md |
| `wingsjiang/wan22-video-generation` | Wan 2.2 ComfyUI workflows; README lists text-to-video, image-to-video, text+image-to-video and speech-to-video modes. | `PUBLIC_SPACE_CANDIDATE`; check the live Space's API tab and actual anonymous request before calling it confirmed. | Public project README documents the modes and ZeroGPU deployment, but the search/open pass did not independently confirm a no-token completed output. Source: https://huggingface.co/spaces/wingsjiang/wan22-video-generation/blob/main/README.md |
| `Blizzma/LTX-2.5-demo` | LTX-2.5 text-to-video and image-to-video with synchronized audio/video. | `PUBLIC_ZERO_GPU_CANDIDATE`; no-token completion not independently verified here. | Space README describes a community ZeroGPU deployment adapted from Lightricks' official model workflow. Treat it as a hosted demo endpoint, not a commercial SLA/API. Source: https://huggingface.co/spaces/Blizzma/LTX-2.5-demo/blob/main/README.md |
| `multimodalart/Helios-Distilled` | Helios Distilled Gradio demo; source code explicitly describes T2V, I2V and V2V. | `PUBLIC_SPACE_CANDIDATE`; endpoint availability and anonymous generation need a live API call. | Public app source documents the video modes and ZeroGPU/Spaces target. The page has also shown runtime-error states in some snapshots, so availability is volatile. Source: https://huggingface.co/spaces/multimodalart/Helios-Distilled |
| `FastVideo/FastH3-Omni` | Video + audio generation/conditioning workflow; catalog identifies a `/generate` endpoint. | `PUBLIC_SPACE_CANDIDATE / INPUT-CONDITIONED`; not a simple text-only T2V provider. | Gradio curated catalog's Nov 22, 2026 smoke check returned an app-level error saying at least one image or video reference was required. This indicates the endpoint was reached, but not a successful generation. Source: https://huggingface.co/datasets/gradio/workflow-curated/blame/main/curated.json |
| `multimodalart/ltx2-audio-to-video` | Audio-to-video workflow; catalog lists `/generate` and ZeroGPU. | `PUBLIC_SPACE_CANDIDATE / AUDIO-CONDITIONED`; not a general text-to-video substitute. | Catalog validator marked the endpoint `ok` on Nov 22, 2026 (about 14.6 seconds latency); this is endpoint smoke evidence, not proof of anonymous completed video output. Source: https://huggingface.co/datasets/gradio/workflow-curated/blame/main/curated.json |
| `makiblek/Wan_2.2_I2V_14B_Custom_Lora_Wow` | Wan 2.2 image-to-video, with `/generate_video` listed by the public catalog. | `PUBLIC_SPACE_CANDIDATE / I2V`; no fresh no-token output captured here. | Catalog validator marked the endpoint `ok` on Nov 22, 2026 (about 25.8 seconds latency). A successful schema/smoke check does not equal a full generation. Source: https://huggingface.co/datasets/gradio/workflow-curated/blame/main/curated.json |
| `OpenKing/wan2-video-generation` | Wan 2.2 text-to-video; catalog lists `/generate_video`. | `PUBLIC_SPACE_CANDIDATE / QUEUE_FULL`; do not present as currently usable. | Catalog validator reported `QueueError: Queue is full! Please try again` on Nov 22, 2026. This confirms the route was reached but it was not available for generation at that check. Source: https://huggingface.co/datasets/gradio/workflow-curated/blame/main/curated.json |

#### Stronger independent evidence for anonymous generation

A community measurement published November 11, 2026 reports real image-to-video calls to public Wan 2.2 and Stable Video Diffusion Spaces using `gradio_client` from a CPU-only Linux machine **without a Hugging Face token**. The author reports 24 attempts: five returned clips, five were lost to multi-replica routing problems, and fourteen were blocked by quota or run limits. The report is particularly useful because it distinguishes successful inference from merely opening a model page. It proves that anonymous video generation can work on public Spaces, while also showing a poor success rate under shared quota and routing conditions. Source: https://huggingface.co/blog/Jacob123222/image-to-video-huggingface

#### Layer 1 API access and quota facts

- Hugging Face documents that public Gradio Spaces expose callable API endpoints and can be called using Python, JavaScript or HTTP. The API schema and function names are Space-specific; inspect the Space's “Use via API” section or `/gradio_api/openapi.json`. Source: https://huggingface.co/docs/hub/spaces-api-endpoints
- Current ZeroGPU documentation states that unauthenticated users receive **2 minutes of GPU time per daily quota window**, while free authenticated accounts receive 5 minutes. Unauthenticated queue priority is low. The allowance is shared platform compute time, not a separate clip allowance for every Space. Source: https://huggingface.co/docs/hub/main/spaces-zerogpu
- The official video task page for Hugging Face Inference Providers shows an `HF_TOKEN` in its API example. That paid/credentialed Inference Providers route is therefore not strict Layer 1, even though public Gradio Spaces can be anonymous. Source: https://huggingface.co/docs/inference-providers/tasks/text-to-video
- A public Space may still add its own sign-in, token, or session requirement. Do not classify a Space as strict keyless solely because its repository is public or it has a Gradio API. Confirm the actual endpoint accepts a fresh unauthenticated request.

#### Updated count and verdict

This pass adds **eight distinct Space candidates** across Wan 2.2, LTX-2.5, LingBot, Helios, FastH3 and audio-conditioned LTX workflows. They are not eight independent commercial API vendors, and they do not create eight independent GPU quotas. The best-supported Layer 1 option remains the public Hugging Face Gradio/ZeroGPU route class, with independently measured anonymous successes but severe quota and reliability constraints. Keep each individual Space marked as candidate unless its live endpoint has a current successful no-token generation test.

No dedicated commercial provider was confirmed in this pass to offer a stable, anonymous, unlimited or guaranteed-free video REST API. Keep Agnes in Layer 2 because its documented REST API requires a free API key; do not move it into Layer 1 just because its promotional model price is $0.

# Video generation — Layer 2 and Layer 3 expansion (research pass 23 November 2026)

This section expands the existing video inventory without changing the strict Layer 1 definition. A free browser playground is not an API, a provider's free key is not keyless, and an API trial is not a recurring allowance.

## Layer 2 — recurring or ongoing free API access

| Provider | API access and allowance | Classification | Important caveats | Official evidence |
|---|---|---|---|---|
| Agnes AI Open API | Free API key; video REST endpoints include `POST /v1/videos` and task polling at `/agnesapi`. Documentation states 16 requests/minute and no paid tier or purchased generation quota; service runs on a shared free inference queue. | `LAYER_2_FREE_ONGOING_KEYED`; rate-limited, not a published daily/monthly credit grant. | Requires signup and Bearer API key, so not Layer 1. Queue can return HTTP 503 when busy. Documentation pages vary on model version/duration: newer guide describes `agnes-video-2.5-flash`, up to 720p and 20 seconds; API reference example still uses `agnes-video-v2.0`. Confirm current model IDs and output cap in the live API before integration. | https://video.lichuanyang.top/en/api-docs ; https://video.lichuanyang.top/en/guides/getting-started ; https://video.lichuanyang.top/en/faq |

**Layer 2 verdict:** Agnes is the clearest ongoing free keyed video API found in this pass. Its free access is described as having no purchased credits or per-second billing, but it is capacity/rate-limited rather than backed by a guaranteed recurring number of videos. Do not describe it as unlimited dependable capacity: the provider itself documents a shared queue and peak-time 503 responses.

No other major commercial video API was confirmed in this pass to provide a stable recurring free API quota. Hugging Face ZeroGPU's unauthenticated shared GPU allowance is already documented under Layer 1; do not count it again as a second provider or separate quota.

## Layer 3 — signup credits, finite trials and free test runs

| Provider | API product | Free offer | Classification and caveats | Official evidence |
|---|---|---|---|---|
| Magic Hour | REST APIs for text-to-video, image-to-video and multiple hosted models, including Seedance 2.0, Kling, LTX and others | New developer accounts receive free signup credits usable across API endpoints; provider says no credit card is required. Exact credit amount is not clearly published on the pages reviewed. | `LAYER_3_SIGNUP_CREDITS`; finite one-time starting balance, not a monthly free allowance. Model eligibility differs: Wan 3.0 is explicitly paid-plan-only, while Wan 2.2 and several other model pages describe free-tier availability. Check model-specific restrictions and the dashboard balance before assuming a model is covered. | https://magichour.ai/api/text-to-video ; https://magichour.ai/api/seedance-2-0 ; https://magichour.ai/api/wan-2-2 ; https://magichour.ai/api/wan-3-0 |
| Replicate | Hosted prediction API for video models | Existing provider pricing information describes selected free test runs for eligible new accounts/models; a fixed, permanent run count is not published. | `LAYER_3_TEST_RUNS_UNPUBLISHED`; model-specific and finite. The public model page/pricing must be checked at the time of use; do not infer that every video model is free. | https://replicate.com/pricing ; https://replicate.com/docs |

### Video offers deliberately not counted

- **Runway Free plan:** 125 one-time credits are for the Runway creative product. The developer API has separate pay-as-you-go credit pricing; do not transfer consumer-plan credits into the API layer. Sources: https://runway.com/pricing ; https://dev.runwayml.com/pricing
- **Pika Free plan:** current pricing page shows 0 monthly credits and packs-only on Free. A free account/UI is not evidence of free API generation. Source: https://pika.art/pricing
- **Google Veo API:** official Gemini API pricing lists no free tier for Veo 3.1 generation. Source: https://ai.google.dev/gemini-api/docs/pricing
- **Luma API:** no current free recurring API quota was established in this pass. Source: https://lumalabs.ai/pricing
- **fal:** current developer tutorial says new accounts start without free credits and require a prepaid top-up for hosted models. Source: https://fal.ai/learn/tools/how-to-build-an-ai-image-generator-app

### Video layer summary

- Layer 1: public Hugging Face Spaces/ZeroGPU can provide anonymous experimental inference, but with a shared low-priority compute allowance and volatile queues; not a dependable commercial API.
- Layer 2: Agnes AI is a keyed, ongoing free API with a shared inference queue and a 16 RPM documented rate limit; no fixed recurring video count is promised.
- Layer 3: Magic Hour signup credits and Replicate's unpublished model-specific test runs are finite trials.
- The existence of a free web app, model weights, or a free plan must never be used as proof of free API access.

# Research expansion — deAPI video API (23 November 2026)

## Layer 3 — shared signup credit, video-capable route

| Provider | Free offer | API capability | Classification and caveats | Official source |
|---|---|---|---|---|
| **deAPI — MiniMax H3 Turbo INT8** | Uses the same **$5 one-time deAPI account credit** recorded in the image/LLM sections. Provider page states up to **3 MiniMax H3 clips/day** on a free account; an example 768×768, 5-second clip costs about **$0.106**. | REST text-to-video and image-to-video; asynchronous request and MP4 result. | `LAYER_3_SHARED_MULTIMODAL_CREDIT / MODEL_SPECIFIC_DAILY_CAP`. Do not multiply the $5 balance by modality or count three daily clips as free of charge regardless of balance. The three-clip limit is an upper request cap; the shared balance still controls whether the job can be paid. Verify current price, duration, resolution and audio settings before use. | https://deapi.ai/lp/en/minimax-h3 ; https://deapi.ai/ |

**Accounting correction:** deAPI's $5 is a shared platform signup balance, not a separate image/video/music/LLM trial for each section. This is a cross-reference, not a second $5 grant.
