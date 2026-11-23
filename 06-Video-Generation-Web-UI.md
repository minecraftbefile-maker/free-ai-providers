# AI Video Generation — Web UI

> Browser-based video generation research, separate from developer APIs.

## How to use this file

1. Open the official product page linked in the provider entry.
2. If the entry says **anonymous/no signup**, try the public page without creating an account. If it requires login, use the provider's own sign-up flow; do not use unofficial account-sharing methods.
3. Check the actual free allowance shown in the product's current interface. Do not assume browser credits can be used through the API.
4. Generate a short sample first. Confirm whether preview, full generation, download/export, watermark removal and commercial use are included in the free tier.
5. Save/export the result only through the product's supported controls. Check whether outputs expire or are public by default.
6. Review privacy and retention terms before uploading personal audio, images, documents or other sensitive content.

**Important:** Web UI entries are browser products, not developer APIs, unless a separate API entry explicitly confirms an API entitlement.

## Research inventory (preserved from the source catalogue)

# AI Video Generation Web UI — first deep-research pass (23 November 2026)

This section begins the video Web UI category. It covers browser-facing consumer tools that create video or a finished narrated video from prompts, images, scripts or references. It does not treat APIs, local models, editing-only features or paid-only generation as free video generators. The same five-layer Web UI system is retained. No live account sign-in or generation was performed in this pass; `OFFICIAL` below means that a provider-owned page supports the stated entitlement, not that an output was generated in this research session.

## First findings: recurring free access and one-time trial

| Service | Layer | Free access currently supported by evidence | What it actually makes / limits | Export, watermark and rights | Evidence status |
|---|---:|---|---|---|---|
| **Google Flow (Veo 3.1 / Gemini Omni Flash)** | **4** | **50 Google Flow credits per day** without a Google AI subscription, using a Google account. | Official Flow page lists text-to-video, frames-to-video, ingredients-to-video, video extension, video-to-video editing and Scenebuilder. Credits are shared across models and tasks; the exact number of clips depends on the selected model, duration and settings. Veo 3.1 supports native audio according to the product page. | Flow page lists the free tier and creation tools but does not establish one universal free watermark/export rule. Regional and account eligibility may vary. The page warns that features vary by region/platform. | `OFFICIAL_ENTITLEMENT`; exact clip count `MODEL_COST_DEPENDENT`; live access not tested. https://labs.google/fx/tools/flow |
| **Dreamina (CapCut ecosystem)** | **4** | Free daily credits; the current Dreamina material says **120 credits/day for US free accounts**, with other regions receiving different amounts. | Text-to-video and image/reference-led video workflows. Credit cost depends on model, duration, resolution and generation mode; do not translate 120 credits into a fixed video count. | A Dreamina guide documents a free-account clip download with a visible watermark. The cited free-access article is a Dreamina-owned product guide, but the US quota must not be generalized to Libya or all regions. | `OFFICIAL_PRODUCT_GUIDE`; region-specific quota. https://dreamina.capcut.com/ai-video/free-text-to-video-tools-access ; https://dreamina.capcut.com/ai-video/free-ai-video-tools-compared |
| **PixVerse** | **4** | Official billing FAQ confirms daily credits exist and reset at **00:00 UTC**, expiring at the end of the day. The current public FAQ reviewed here does **not** itself give a universal number for the free Basic grant. | Video generation costs vary by model, resolution, duration and settings; the UI displays the charge before generation. Failed generations are automatically refunded, according to the FAQ. | Do not assume watermark-free export for Basic. An external 2026 comparison reports 60 initial credits plus 30/day and output up to 540p, but this exact amount is not confirmed by the official FAQ captured here; keep it `INDEPENDENT_REPORT / OFFICIAL_AMOUNT_NOT_CONFIRMED`. | Daily reset mechanics `OFFICIAL`; numeric free allowance `UNCONFIRMED`. https://docs.pixverse.ai/FAQ-Subscriptions-Billing-45723f6092f740bca8f0209878440ca1 |
| **Krea Video / Image-to-Video** | **4** | **100 compute units/day** on the free account; no credit card is required, according to Krea's current pricing page. | Access to all video models is listed in the free-plan feature list, but actual model/task costs vary. Krea's image-to-video page gives a practical example: about two 5-second 512p LTX-2 clips for 100 units. Kling, Veo 3.1, Seedance 2.5 and Wan 3.0 are stated as paid-plan models on that page; Hailuo 2.3 Fast and MiniMax H3 are described as available to free accounts only during a current promotion, and each costs more than one day's free units. | Download, watermark and commercial-use terms should be checked for the selected model and current account. Krea pricing separately advertises commercial licensing on Free, but model-specific third-party terms may still apply; do not assume one blanket license covers every upstream model. | `OFFICIAL_FREE_UNITS`; model eligibility/cost varies. https://www.krea.ai/pricing ; https://www.krea.ai/apps/image-to-video |
| **Adobe Firefly Video** | **4** | Free users receive a **limited daily generation allowance**, which resets daily. Adobe does not publish a single fixed number in the product page reviewed. | Text-to-video and image-to-video are included for the Firefly Video Model and selected partner models. Clip duration depends on model: most listed models generate up to 8 seconds, some up to 15 seconds. | Adobe says generated videos are downloadable as MP4, with resolutions up to 4K. Exact free-tier model access, daily quantity and output restrictions depend on the account/selected model; commercial use must be checked against the applicable Firefly terms and model-specific conditions. | `OFFICIAL_DAILY_ALLOWANCE / NUMBER_UNDISCLOSED`. https://www.adobe.com/products/firefly/features/ai-video-generator.html ; https://www.adobe.com/products/firefly.html |
| **HeyGen** | **4** | **3 videos/month** on the current free plan, each up to **1 minute**. Help Center notes some regions may receive **1–3 videos**, so the pricing page's three-video headline is not universal. | Primarily presenter/avatar and script-to-video production, not a general-purpose cinematic text-to-video model. Includes one custom video avatar, stock avatars and multiple languages. | Free output is watermarked; the pricing page lists the free video quota and duration. 720p sharing/export is described in Help Center material. | `OFFICIAL_RECURRING_MONTHLY_QUOTA`; regional variation. https://www.heygen.com/pricing ; https://help.heygen.com/en/articles/15125761-heygen-credit-based-pricing-plans-subscriptions-explained |
| **Fliki** | **4** | **3 credits/month** on the Free plan; Fliki's story-video page equates this to **3 video minutes/month**. No credit card is required. | Turns an idea, script, blog post or presentation into a scene-based narrated video with stock visuals, captions and AI voices. This is a finished-video assembler, not the same product category as a single-shot diffusion/video-model generator. | 720p exports with Fliki watermark. Its feature page says commercial rights are on paid plans, not the free plan. Maximum length per video is stated as 5 minutes, but the monthly free allowance is only 3 minutes. | `OFFICIAL_RECURRING_MONTHLY_QUOTA`. https://fliki.ai/pricing ; https://fliki.ai/features/ai-story-video-generator |
| **Runway** | **5** | **125 credits once**, non-expiring but non-renewing, plus 5 GB asset storage and access to a limited selection of generative tools. | Model availability changes; Runway explicitly tells users to sign in to see which models/tools are currently included in Free. Do not promise that a specific text-to-video model is included. | The current free-plan page is clear about one-time credits but the exact free export/watermark conditions should be checked against the tool/model selected. A current independent comparison reports watermark on free videos; record as independently reported until confirmed by the plan page. | `OFFICIAL_ONE_TIME_GRANT`; model access dynamic. https://help.runwayml.com/hc/en-us/articles/50404627334547-Free-plan-details ; https://help.runwayml.com/hc/en-us/articles/15124877443219-How-do-credits-work |
| **Vidu** | **5 + recurring-login candidate** | Official pricing FAQ confirms signup trial credits and daily-login credits as possible acquisition routes, but does not publish their universal amounts in the page reviewed. | Video-generation credits are used for generation; subscription credits last 30 days, purchased credits 2 years, and bonus credits 2 years. Daily login/event bonus eligibility and amounts may change. | Free download quality and watermark rules need a separate current confirmation; do not promise HD/no-watermark on free. | `OFFICIAL_SIGNUP_GRANT`; `DAILY_LOGIN_AMOUNT_UNDISCLOSED`. https://s.vidu.com/pricing |
| **Bing Video Creator** | **4** | Requires a personal Microsoft account. Standard creation is free; the initial launch announcement described 10 Fast creations, after which Fast uses Microsoft Rewards points or any offered promotional credits. | The current Microsoft feature page says 8-second videos with audio tracks, and permits up to 3 in-progress generations in the queue. The original launch announcement described 5-second portrait clips; use the current feature page for present duration and retain the old launch specification as historical context only. | Microsoft describes viewing and downloading creations through Bing's creation area. Availability differs by account/platform; Microsoft says Entra work/school accounts are not supported. No anonymous generation. | `OFFICIAL_FREE_STANDARD_MODE`; fast allowance from launch FAQ, potentially subject to change. https://www.microsoft.com/en-us/bing/features/Bing-video-creator ; https://blogs.bing.com/search/2025/6/Introducing-Bing-Video-Creator/ |
| **Hailuo AI / MiniMax** | **4 candidate** | An official-looking community-maintained GitHub repository says the Hailuo consumer app has free daily credits, watermark and slower queue, but this is not a MiniMax-owned policy page. A separate HailuoLabs domain advertises 160 monthly credits and up to 5 videos, but its relationship to the official MiniMax service is not established by the evidence captured here. | Hailuo is a hosted video model/app, not an open local model. Independent repo describes 6- or 10-second clips, up to 1080p depending on mode/model, but do not elevate those specs to official current free-plan facts without MiniMax first-party confirmation. | Watermark/queue are reported for free access; commercial rights and free download conditions remain unconfirmed. | `CANDIDATE_UNVERIFIED`; do not treat 160 credits/month as official MiniMax quota. https://hailuoai.video/ ; discovery/context: https://github.com/hailuo-official/Hailuo-AI |
| **Luma Dream Machine** | **4 candidate** | Luma's help/plan information indicates limited free draft access for Ray3.14 video draft, with watermark and personal-project limitation in the current plan guide. | Draft-quality video access, not a general promise of full-quality free generations. Exact number of free clips/credits was not stated in the official help page captured. | Watermark and personal-only use are stated in Luma's plan guide. The free allowance is limited; no universal free clip count is claimed here. | `OFFICIAL_LIMITED_DRAFT_ACCESS / QUOTA_UNDISCLOSED`. https://lumalabs.ai/learning-hub/payments-subscriptions ; https://lumalabs.ai/learning-hub/web-quick-start |

## Important exclusions and boundary cases

| Service / feature | Classification decision | Reason |
|---|---|---|
| **Canva AI — Create a Video Clip (Veo-powered)** | **Exclude from free generation layers** | Canva's own page says this specific cinematic clip generator is available to Pro, Business, Enterprise and Nonprofit users with a limited monthly number of clips. It creates up to 8-second 16:9 clips with synchronized audio. Canva's separate Magic Video can assemble uploaded photos/clips into a 60-second edited video on all plans, including Free, but that is not the same as free prompt-generated cinematic video. https://www.canva.com/features/ai-video-generator/ ; https://www.canva.com/help/video-clip/ ; https://www.canva.com/help/magic-video/ |
| **CapCut AI video generator / editor** | **Keep as a mixed/conditional candidate, not confirmed unlimited** | CapCut's public pages advertise text-to-video and image-to-video with Veo 3.1/Sora 2, but do not establish a stable, universal free generation allowance for all regions/accounts. Its free editor and script-to-video assembly should not be conflated with unlimited access to premium generative models. Record model availability and generation cost shown inside the account before treating it as free. https://www.capcut.com/tools/ai-video ; https://www.capcut.com/tools/free-ai-video-generator |
| **Pika** | **Do not list as a recurring free video generator** | Current independent November 2026 checks report the Free account has 0 monthly generation credits; account access alone does not mean free generation. Keep it out of recurring free layers unless a provider-owned page or a live account later confirms a usable free grant. https://pika.art/ ; independent cross-check: https://cicadas.ai/blog/free-ai-video-generators |
| **Kling AI** | **No stable recurring free entitlement confirmed** | Kling's official credit policy says credits are earned through promotions, subscriptions and special events; daily login credits during an event are explicitly described as subscriber credits. Free users should not be promised a daily credit grant. A generation may be free only when a promotion or UI-specific free channel is active. https://kling.ai/docs/point-policy |
| **Gemini app video generation** | **Not counted as a separate free Web UI offer** | The free Flow page is the confirmed route for a recurring video allowance. Do not infer that video generation in the ordinary Gemini app is free merely because the underlying model is Veo. |

## Anonymous / no-account video generators — first-pass conclusion

No major hosted video-generation service in the first-party pages reviewed in this pass was confirmed to offer a reliable, ongoing anonymous/no-signup generation allowance. Bing requires a Microsoft account; Flow requires a Google account; Dreamina, PixVerse, Krea, Adobe Firefly, Runway, Vidu, HeyGen and Fliki use accounts for their documented free access. Some third-party directories advertise anonymous services such as ZSky or public Qwen demos, but those require separate first-party verification of accountless generation, quotas, downloads and current uptime before they can be placed in Layer 1 or Layer 2.

**Layer 1 status at the time of that earlier pass:** no confirmed anonymous unlimited provider had been identified. This was superseded by the later Flyne AI discovery recorded below.

**Layer 2 status at the time of that earlier pass:** no confirmed anonymous limited provider had been identified. Later expansions added candidates.

## Useful distinction: generated clips versus finished videos

- **Generative scene/video models:** Google Flow, Dreamina, PixVerse, Krea, Adobe Firefly Video, Runway, Vidu, Hailuo, Luma and Bing Video Creator. These generate a short scene/clip from prompts, images or references.
- **Avatar/presenter video:** HeyGen. The free quota is three videos/month (regional range 1–3), up to one minute, with watermark.
- **Script-to-video assembly:** Fliki. Free plan has 3 minutes/month, 720p and watermark; it assembles scenes, stock visuals, narration and captions.
- **Editor/assembly tools:** Canva Magic Video and CapCut editing. They can create or assemble a finished timeline, but this must not be misreported as free access to every premium generative video model.

## Video quota and quality cautions

1. **Credits are not videos.** Keep daily credits, monthly credits, seconds, generations and compute units in separate fields. Model, duration, resolution, audio and number of outputs change the cost.
2. **A free account is not a free generation.** Pika is a current example where the free account has no monthly generation credits according to current independent checks.
3. **Promotional credits are not recurring.** Kling's policy distinguishes promotional credits from subscriber benefits and event-specific login credits.
4. **The same brand can have multiple products.** Canva Magic Video, Canva AI Video Clip and Canva's editor are distinct entitlements. Likewise, CapCut editor access is not proof of free Veo/Sora generations.
5. **Regional quotas matter.** Dreamina publishes 120 daily credits for US free users and says other regions differ. HeyGen says free video quota can vary by region. Do not transfer those counts to Libya without account-level confirmation.
6. **Clip duration matters.** Bing's current feature page says 8 seconds; the 2025 launch blog said 5 seconds. Prefer current product documentation over the launch announcement.
7. **Watermark and commercial rights are separate.** Fliki explicitly watermarks free exports and reserves commercial rights for paid plans. HeyGen free videos are watermarked. Krea's platform license and upstream model terms need to be distinguished.
8. **Queue and generation access can be conditional.** Google Flow's feature availability varies by region/platform and non-subscriber generation may be affected by peak-time restrictions described in current product guides. Do not treat an available credit balance as guaranteed immediate throughput.
9. **No live generation was performed in this pass.** This is a documentation-led research pass, not a hands-on benchmark. It does not claim that every provider was opened, registered, generated and downloaded successfully.

## First-party source register — video Web UI

- Google Flow free tier, models and tools: https://labs.google/fx/tools/flow
- Microsoft Bing Video Creator feature page and original launch details: https://www.microsoft.com/en-us/bing/features/Bing-video-creator ; https://blogs.bing.com/search/2025/6/Introducing-Bing-Video-Creator/
- Runway Free plan and credit policy: https://help.runwayml.com/hc/en-us/articles/50404627334547-Free-plan-details ; https://help.runwayml.com/hc/en-us/articles/15124877443219-How-do-credits-work
- Dreamina free video access: https://dreamina.capcut.com/ai-video/free-text-to-video-tools-access ; https://dreamina.capcut.com/ai-video/free-ai-video-tools-compared
- PixVerse credit FAQ: https://docs.pixverse.ai/FAQ-Subscriptions-Billing-45723f6092f740bca8f0209878440ca1
- Krea pricing and image-to-video free usage: https://www.krea.ai/pricing ; https://www.krea.ai/apps/image-to-video
- Adobe Firefly Video free access and product page: https://www.adobe.com/products/firefly/features/ai-video-generator.html ; https://www.adobe.com/products/firefly.html
- HeyGen Free plan and regional quota notes: https://www.heygen.com/pricing ; https://help.heygen.com/en/articles/15125761-heygen-credit-based-pricing-plans-subscriptions-explained
- Fliki free plan and story-video quota: https://fliki.ai/pricing ; https://fliki.ai/features/ai-story-video-generator
- Vidu signup and daily-login credits: https://s.vidu.com/pricing
- Kling credits policy: https://kling.ai/docs/point-policy
- Luma plan and draft access: https://lumalabs.ai/learning-hub/payments-subscriptions
- Canva generated clip versus Magic Video: https://www.canva.com/features/ai-video-generator/ ; https://www.canva.com/help/video-clip/ ; https://www.canva.com/help/magic-video/
- CapCut AI video tools: https://www.capcut.com/tools/ai-video ; https://www.capcut.com/tools/free-ai-video-generator

## Independent discovery and cross-check sources — not substitutes for provider terms

- November 2026 free video tier comparison and provider-page audit: https://cicadas.ai/blog/free-ai-video-generators
- November 2026 free generator comparison, including anonymous-access caveats: https://vidfare.com/guides/free-ai-video-generators/
- Free tool discovery list (ZSky, Qwen, Bing, Vidu): https://videotoolmap.com/free-tools
- Community-maintained Hailuo overview (not MiniMax policy): https://github.com/hailuo-official/Hailuo-AI

**Research status:** first deep pass completed for the best-known video Web UI platforms. Strong recurring free account routes currently include Google Flow (50/day), Krea (100 compute units/day), Dreamina (regional daily credits), Adobe Firefly (daily but undisclosed count), Fliki (3 minutes/month), and HeyGen (3 videos/month, regional 1–3). PixVerse and Vidu have confirmed daily-credit mechanics but their exact free grants remain insufficiently documented in the official pages captured. Runway is a one-time 125-credit trial. Bing offers free Standard generation after the Fast allowance but requires a Microsoft account. No anonymous unlimited or anonymous limited service has yet passed first-party verification.

**Next video research pass:** focus on anonymous/no-signup browser video generation and smaller hosted services (including ZSky, Qwen Studio and public community demos), then investigate the precise current PixVerse/Vidu/Hailuo free-account balances and export rules. Do not promote any candidate to a confirmed layer until the provider's own current page or a clearly documented live account entitlement supports it.

---

# AI Video Generation Web UI — second expansion (23 November 2026)

This expansion prioritizes (1) anonymous/no-signup browser generators, (2) recurring free account access, and (3) newly surfaced aggregators. It preserves the five-layer Web UI taxonomy. A hosted web interface is not an API, a locally hosted model, or merely an editor. A listing or product claim is not treated as a hands-on generation test.

## Newly identified anonymous / no-signup video candidates

| Service | Provisional layer | What is supported | Limits / caveats | Evidence status |
|---|---:|---|---|---|
| **Wan2.Video** | **2 — anonymous limited candidate** | Its own landing page explicitly advertises free text-to-video and image-to-video with Wan and LTX models, no signup, and downloadable results in the browser. It also links to a speech-to-video public demo and a MiniMax H3 synchronized-audio public Space. | The site warns that public GPU queues and usage limits may apply but does not publish a stable number of clips, seconds, or daily quota. Avoid uploading sensitive images or audio to a public demo. No live generation was performed in this research pass. | `OFFICIAL_NO_SIGNUP_CLAIM / LIMIT_UNDISCLOSED / NOT_LIVE_TESTED`. https://wan2.video/ |
| **Omni-Video-Factory (Hugging Face Space)** | **2 candidate — anonymous access reported, account/quota boundary unclear** | Space exposes text-to-video, image-to-video and video extension, with 1–4 scenes and 3- or 5-second scene choices. Its own description says it is an experimental OmniVideo + ComfyUI + Hugging Face ZeroGPU workflow. | Space description says runs depend on Hugging Face account quota and ZeroGPU availability, while an independent anonymous test reported a playable 3-second text-to-video result without a login wall. Download was not verified by that tester; only text-to-video was tested. Research-only use is stated; generated production content should not be used commercially. Treat anonymous access as `CONFLICTED / FLOW-DEPENDENT`, not a confirmed permanent guest entitlement. | `SPACE_FEATURES_OFFICIAL / ANONYMOUS_FLOW_INDEPENDENTLY_REPORTED / QUOTA_AND_DOWNLOAD_UNVERIFIED`. https://huggingface.co/spaces/FrameAI4687/omni-video-factory ; https://taptoagent.com/agents/omni-video-factory.html |
| **Pika H3 Flex (official Pika Hugging Face Space)** | **2 candidate — anonymous access reported** | Independent test reports the default text-to-video mode worked without an account and produced a 5-second 832×480 clip with sound in one test. The Space is distinct from Pika's main commercial web app and its account-based Free plan. | The reported test covers only the default text mode and one prompt. A download link appeared but the downloaded file was not byte-verified. No numeric quota was published or encountered; this is not evidence of unlimited use. Hugging Face shared capacity can queue. | `INDEPENDENT_SINGLE_TEST / NOT_PROVIDER_QUOTA_CONFIRMATION`. https://huggingface.co/spaces/Pika-Labs/pika-h3-flex ; https://taptoagent.com/agents/pika-h3-flex.html |

### Anonymous category update

The earlier statement “no major hosted service was confirmed” remains accurate for the major first-party consumer platforms, but the expanded search has found smaller public demos and hosted model frontends. Do not merge them with the main commercial sites of their model brands. The current anonymous shortlist is:

- Wan2.Video: explicit no-signup claim by its own landing page, but public queue and numeric quota undisclosed.
- Omni-Video-Factory: independent no-login test, but its Space description references Hugging Face account quota; treat accountlessness as conflicted and flow-dependent.
- Pika H3 Flex Space: independent no-login test of one mode; separate from pika.art's normal account flow and free-plan credits.

At the time of this pass, none of the listed candidates qualified as Layer 1. This conclusion is superseded by the later discovery of Flyne AI’s dedicated no-signup generator page, documented in the fourth expansion below.

## VidoGrid — browser studio and app cross-check

**Correct product identity:** `vidogrid.ai` (VidoGrid), not `videogrid.ai` (a different AI video-model news/tracker site). Search results also surface `videogridai.homes`; do not assume it is the same official domain. The VidoGrid API documentation is hosted separately at `docs.vidogrid.ai`.

| Field | Finding |
|---|---|
| Web UI category | Multi-model AI video and image generation studio / aggregator. |
| Provisional layer | **Layer 4 — account required, free but limited/undisclosed**, based on an independent review describing a $0 web plan. Exact free clip count is not established by the official docs captured in this pass. |
| Free web entitlement | Independent review says selected models, one video generation at a time, and no video extension. It says the website does not publish a fixed free-video count in the pages checked; treat this as a useful free trial tier, not a quantified recurring daily allowance. |
| Models shown | Official API docs list Veo 3.1 / Fast, Omni Flash variants, Grok Imagine Video 1.5 and Lite, and Muse AI. The Google Play app listing additionally advertises Veo 3.1 Fast/Lite, Grok Imagine Video and Muse AI. Model availability can differ between web UI, app and API. |
| Generation modes | Text-to-video, image-to-video, first/last-frame control on supported models, reference images, and video extension on supported paid/API workflows. Do not assume all modes are enabled on the free web tier. |
| Output | Google Play listing says 4–15 seconds and up to 1080p across supported models; exact duration varies by model. The independent web review reports 720p–1080p and aspect ratios from 9:16 to 21:9. Treat these as product-wide capabilities, not a guarantee for every free model. |
| Audio | Some models can generate video with sound; app listing says this explicitly. Model-specific audio support varies. |
| Download/history | App listing says creations are stored in History and can be downloaded to the gallery in full quality. Web-plan export/watermark details were not conclusively documented in this pass. |
| Signup / card | Web free plan is described as a $0 plan by an independent source; account requirements and card requirement were not conclusively established from a readable first-party web pricing page. App is account-based for saved history; exact card requirements not stated. |
| Quota | No verified exact daily/monthly web free clip allowance. Do not import the app developer's Reddit reply into the web quota field. |
| Privacy | App's Google Play Data Safety section says the developer reports sharing app activity with third parties and collecting personal info, photos/videos and other data; it says data is encrypted in transit and deletion can be requested. This is app-store disclosure, not a full independent privacy audit. |
| Commercial rights | Not confirmed from the first-party terms in this research pass. Do not assume commercial rights for free outputs. |
| API distinction | VidoGrid API is a separate paid-credit interface: API docs require an API key, queue jobs, and bill generation requests in VidoGrid credits. Do not count API credit billing as a free Web UI entitlement. |

**Quota conflict / important separation:** the developer's Google Play description says the app offers free generations every day, but does not state a number. In a Reddit reply, the developer reportedly said the app free tier offered 20 videos/day, or up to 100/day with Muse, resetting at midnight. That is an app-specific developer comment, not an official published Web UI quota. The independent web-plan review says the website's free plan has selected models and one video at a time, but no fixed clip count was visible. Therefore record:

- **Web UI:** `L4_CANDIDATE / FREE_PLAN_REPORTED / CLIP_QUOTA_UNDISCLOSED / NO_EXTENSION_REPORTED`.
- **Android app:** `DAILY_FREE_GENERATION_CLAIM_OFFICIAL / EXACT_COUNT_NOT_IN_PLAY_STORE_DESCRIPTION`; `20/day or 100/day Muse` is `DEVELOPER_REPORTED_ON_REDDIT`, not independently verified.
- **API:** separate paid-credit product; do not mix into Web UI layers.

**Official / primary sources:**
- Google Play app listing, features, app data-safety disclosures and developer identity: https://play.google.com/store/apps/details?id=com.vidogrid.ai.video.generate
- VidoGrid API documentation and model/mode list: https://docs.vidogrid.ai/
- Developer's Reddit launch post and quota clarification: https://www.reddit.com/r/droidappshowcase/comments/1xyo7n4/vidogrid_ai_video_image_maker_veo_grok_and_muse/

**Independent web-plan cross-check (not first-party):**
- PowerfulAI.tools, updated 16 Nov 2026: https://www.powerfulai.tools/blog/is-vidogrid-free
- AmonFun review: https://amonfun.com/tool/vidogrid

## ZSky AI — new account-based unlimited-claim candidate

| Field | Finding |
|---|---|
| Layer | **3 — account required, free and vendor-claimed unlimited** (subject to fair-use, standard queue and storage limits). |
| Access | Official press kit says permanent free tier, account required, no payment card required. |
| Allowance | Official site and pricing page claim unlimited free image and video generations, with no credit meter. This is a vendor claim, not an independently load-tested unlimited guarantee. |
| Output / watermark | Free video output carries a small ZSky wordmark. Site describes HD video with synchronized audio; Pro/Max plans unlock higher resolution and watermark removal. |
| Queue | Free tier uses standard/slow queue; paid plans advertise instant priority. “Unlimited” therefore does not mean immediate or equal throughput. |
| Storage | Official pricing page says free creations are deleted after 7 days; paid storage differs. |
| Commercial rights | Official site and press/security pages claim commercial use on every plan, including Free. Confirm current terms before relying on this for a business deliverable. |
| Account | Required; no card required according to the official press kit. Therefore not Layer 1 or 2. |
| Verification | No live generation performed in this research pass. Keep the unlimited status as `VENDOR_CLAIM / NOT_INDEPENDENTLY_LOAD_TESTED`. |

Official sources:
- Homepage and product capabilities: https://zsky.ai/
- Pricing and free-tier retention/queue details: https://zsky.ai/pricing
- Press kit with account/no-card and permanent free-tier description: https://zsky.ai/press
- Security and commercial-use statements: https://zsky.ai/security
- Official GitHub organization profile: https://github.com/zsky-ai

## Other important discoveries and classification boundaries

| Service / route | Layer / decision | Evidence and reason |
|---|---:|---|
| **Qwen Studio** | Not yet placed in a video layer | Official Qwen landing page now visibly lists “Video Generation” among product tools and says Qwen is free to use. The landing page alone does not specify whether video generation is free, how many clips are included, or whether the video tool requires an account/region access. Keep `CANDIDATE_UNVERIFIED` until the dedicated video-generation route and quota are checked. https://qwen.ai/ |
| **Hugging Face public video Spaces** | 2 candidate / per-Space | The directory contains many independent video Spaces, including Omni Video Factory, LTX Video Fast, Stable Video Diffusion, Wan 2.2 I2V and LTX-2 Turbo. Every Space has different model, account, GPU queue and quota rules; do not assign one Hugging Face-wide video allowance based on a single Space. https://huggingface.co/spaces?search=video |
| **VidoGrid API** | Excluded from Web UI free layers | Requires an API key and bills each generation in VidoGrid credits. It is a developer API, not evidence of free browser video generation. https://docs.vidogrid.ai/ |
| **VidoGrid app** | Separate app record | The Play Store listing claims daily free video/image generations and says some models include audio; it does not publish a numeric daily cap. Do not infer the web studio's quota from the app or vice versa. https://play.google.com/store/apps/details?id=com.vidogrid.ai.video.generate |
| **videogrid.ai** | Excluded as unrelated | This domain is an AI video-model news/tracker sheet that aggregates public release sources; it is not VidoGrid's generation studio at `vidogrid.ai`. https://vidogrid.com/ |

## Updated video research status

- **Layer 1 — anonymous, free and unlimited:** no provider had yet been identified in this earlier VidoGrid pass. This historical status is superseded by Flyne AI, added in the fourth expansion below.
- **Layer 2 — anonymous, free but limited:** Wan2.Video is a promising provider-claimed no-signup option with public queue and undisclosed limits. Omni-Video-Factory and Pika H3 Flex are independent single-test candidates with unresolved account/quota/download boundaries. None should be called unlimited.
- **Layer 3 — account required, free and effectively unlimited:** ZSky AI is a strong vendor-claimed candidate with permanent free unlimited generation, no card, wordmark, standard queue and 7-day free storage. This is a vendor claim and not a measured throughput guarantee.
- **Layer 4 — account required, free but limited:** VidoGrid web studio is a free-plan candidate, but the exact number of free clips is undisclosed; one-at-a-time and no-extension restrictions are reported by an independent review. The app separately advertises daily free generations without a number.
- **Layer 5 — one-time trial:** no new confirmed provider added in this expansion.

**Method note:** This is documentation and source review, not a hands-on generation benchmark. Independent anonymous tests are labeled as such; vendor marketing claims are not upgraded to verified performance. The strongest next verification targets are: (1) whether Wan2.Video can repeatedly generate and download without signing in, (2) whether ZSky's free account can generate multiple videos over several days and what the actual queue/storage behavior is, and (3) the exact VidoGrid web free-plan balance and whether it resets daily. Do not spend money or enter payment details to establish a free-tier fact.

---

# AI Video Generation Web UI — third expansion (23 November 2026)

This pass adds newly surfaced browser generators and tightens the VidoGrid classification using a first-hand user report. The five-layer taxonomy remains mandatory: Layer 1 anonymous unlimited; Layer 2 anonymous limited; Layer 3 account-required free/effectively unlimited; Layer 4 account-required recurring limited; Layer 5 one-time/non-renewing trial. A provider's own marketing statement, an independent review, and a user's direct experience are recorded as different evidence types.

## VidoGrid — user-reported web/app equivalence and reliability caveat

The user reports from direct experience that the Android app and the browser interface are effectively the same VidoGrid service/experience, so the earlier strict separation between app quota and web quota should not be treated as a hard product boundary. Record this as `USER_FIRSTHAND_REPORT: WEB_AND_ANDROID_SHARE_THE_SAME_SERVICE/EXPERIENCE`.

- Keep VidoGrid in **Layer 4 — account-required free but limited/undisclosed**. The exact free daily web allowance still lacks a first-party published quota table in the evidence reviewed.
- The developer's Reddit reply reporting 20 free videos/day, or up to 100/day with Muse, is still `DEVELOPER_REPORTED`, not a published service-level guarantee. The user's report supports applying the same observed service behavior to web and Android, but does not independently establish those exact numbers.
- Reliability: the user reports intermittent `Internal Server Error` / server-side failures or service drops. Record as `USER_REPORTED_INTERMITTENT_SERVER_ERRORS`; this is a useful reliability observation, not a measured uptime statistic or proof of a permanent outage.
- Therefore, describe VidoGrid as a potentially generous free Layer 4 service with an undisclosed/contested exact quota and intermittent availability, not as reliably unlimited.
- Do not conflate the separate VidoGrid API credit billing with the consumer Web UI.

Sources retained from the previous pass: https://play.google.com/store/apps/details?id=com.vidogrid.ai.video.generate ; https://www.reddit.com/r/droidappshowcase/comments/1xyo7n4/vidogrid_ai_video_image_maker_veo_grok_and_muse/ ; independent web-plan review: https://www.powerfulai.tools/blog/is-vidogrid-free

## Newly found anonymous browser generators — Layer 2 candidates

| Service | Provisional layer | Free browser allowance and modes | Output / restrictions | Evidence status |
|---|---:|---|---|---|
| **Magic Hour** | **2 — anonymous limited** | Official FAQ says text-to-video works without sign-up and that Text-to-Video, Image-to-Video, AI Video Editor and other video/audio tools share **3 free generation requests per day**. The allowance is shared by users on the same network. | Free clips are 3 seconds, 480p, with audio and a watermark. Signing up unlocks account-specific credits/rewards and saved projects. The shared-network rule can make the actual available requests lower in homes, schools or shared networks. | `OFFICIAL_FAQ / NO_SIGNUP / 3_SHARED_REQUESTS_DAILY`; not live-tested in this research pass. https://magichour.ai/faq |
| **FreeGenVideo** | **2 — anonymous limited candidate** | Official page advertises no login and **1 free video/day**, reset at 00:00 UTC; supports text-to-video and image-to-video, with optional start/end image input. | The page shows a 5-second workflow and 540p in one input configuration, but says available output options depend on the current model. Privacy page says prompts and starting images are sent to the upstream provider. Commercial rights are not guaranteed; review terms and upstream model rules. | `OFFICIAL_SITE_CLAIM / 1_PER_DAY / NOT_LIVE_TESTED`. https://freegen.video/ |
| **MoveFrame** | **2 — anonymous limited candidate; quota details conflict** | Official pages advertise no account, no email and no card. The facts page says 10 credits/day, equivalent to two 5-second Standard 480p videos, plus one 720p upscale/day. Other landing pages say first video free and, in many regions, one more daily video depending on load; a dedicated page says 2 videos/day. | Free output is 480p and some pages say a small watermark; another page says the first video has no watermark. Daily availability varies by region and load. Text-to-video and image-to-video are advertised, with a strong emphasis on photo-animation presets. Uploads are said to be deleted after 24 hours and generated videos after 30 days. | `OFFICIAL_PAGES_CONFLICT / L2_CANDIDATE / QUOTA_AND_WATERMARK_NEED_LIVE_CHECK`. Do not state one universal daily count or watermark rule. https://moveframe.app/ ; https://moveframe.app/facts/ ; https://moveframe.app/free-image-to-video-no-signup/ ; https://moveframe.app/privacy/ |
| **Rendastic** | **2 — anonymous limited** | Official site says no account/email is needed and gives **1 free creation per UTC day**, shared across its tools. Supports text-to-video and image-to-video. | Free path is Rendastic 1.0 at 480p and 4 seconds; no guaranteed audio; clean export without Rendastic watermark. Capacity is released hourly and subject to availability. The site says photos are deleted locally within an hour, while an upstream APIMart/APIMODELS reference copy may be stored up to 30 days. Commercial use is conditional on input rights, applicable law and upstream model terms. | `OFFICIAL_SITE_CLAIM / 1_PER_UTC_DAY / NO_LOGIN / NOT_LIVE_TESTED`. https://rendastic.com/ ; https://rendastic.com/about |

### Layer 2 comparison update

The current strongest official no-login claims now include:

1. **Magic Hour:** 3 shared-network requests/day; 3-second, 480p, audio, watermark.
2. **Rendastic:** 1 creation/UTC day; 4-second, 480p, no Rendastic watermark; availability-dependent.
3. **FreeGenVideo:** 1 video/day; model-dependent output; no signup.
4. **MoveFrame:** multiple conflicting official descriptions of daily credits, region and watermark; retain as conflicted until a live flow clarifies it.
5. **Wan2.Video:** no-signup claim, public queues and undisclosed limits.
6. **Omni-Video-Factory and Pika H3 Flex Spaces:** anonymous generation independently reported in limited tests, but quota/account/download behavior remains less certain.

The services in this particular Layer 2 table remain Layer 2; Flyne AI is a separate Layer 1 entry added in the fourth expansion below. A finite daily cap is Layer 2 even if it renews every day; a public queue or server capacity restriction should be recorded separately from the daily allowance.

## Layer 3 and Layer 4 status unchanged

- **Layer 3:** ZSky AI remains the leading account-required, vendor-claimed unlimited free candidate. It is not independently load-tested; free queue, watermark and 7-day retention remain important restrictions.
- **Layer 4:** VidoGrid remains a free account-based multi-model studio candidate. The user reports web and Android are the same service experience and reports intermittent server errors. Exact quota remains unconfirmed in first-party documentation; developer-reported 20/day or 100/day with Muse remains a separate evidence label.
- **Layer 4 / established services:** Google Flow, Krea, Dreamina, Adobe Firefly, Fliki and HeyGen retain their previous records and caveats. Do not infer video counts directly from compute units or credits without model-specific conversion.
- **Layer 5:** no new one-time-only trial provider added in this pass.

## Updated layer inventory (video Web UI)

| Layer | Current findings |
|---|---|
| **1 — Anonymous, free and unlimited** | Flyne AI dedicated free video generator (`flyne.ai/free-ai-video-generator`): no account and no published generation cap claimed for the dedicated 5-second/480p workflow; free queue and verification step may apply. |
| **2 — Anonymous, free but limited** | Magic Hour (3 shared requests/day), Rendastic (1/day), FreeGenVideo (1/day), MoveFrame (conflicted daily-credit claims), Wan2.Video (limit undisclosed), plus limited/conflicted Hugging Face Spaces (Omni-Video-Factory, Pika H3 Flex). |
| **3 — Account required, free and effectively unlimited** | ZSky AI — vendor-claimed unlimited, with watermark/slow queue/7-day retention; not independently load-tested. |
| **4 — Account required, free but limited** | VidoGrid (web and Android same service according to user's firsthand report; intermittent server errors reported; exact web quota unresolved), Google Flow, Krea, Dreamina, Adobe Firefly, Fliki, HeyGen, PixVerse, Vidu and other previously documented recurring/free-account tiers. |
| **5 — One-time trial or non-renewing grant** | Runway and other previously documented one-time credit/trial services; no new addition in this pass. |

## Research quality and unresolved checks

- This pass used provider pages and FAQ material, not a live account or generation benchmark. Do not claim these sites were personally tested.
- Magic Hour, FreeGenVideo, MoveFrame and Rendastic are newly discovered Layer 2 candidates; their public pages do not prove uptime or successful access from every country/network.
- MoveFrame's own pages conflict on the number of daily free videos and watermark. Keep the conflict visible rather than selecting the most generous statement.
- VidoGrid's server errors are a user-reported observation. No independent uptime measurement was performed.
- No conclusion about Libya-specific access, payment eligibility, or regional quota is established by this web research.

## Sources for this expansion

- Magic Hour official FAQ (daily anonymous generation and shared-network quota): https://magichour.ai/faq
- FreeGenVideo official generator and allowance/FAQ: https://freegen.video/
- MoveFrame official homepage, facts, dedicated no-signup page and privacy policy: https://moveframe.app/ ; https://moveframe.app/facts/ ; https://moveframe.app/free-image-to-video-no-signup/ ; https://moveframe.app/privacy/
- Rendastic official generator and about/privacy explanation: https://rendastic.com/ ; https://rendastic.com/about
- Independent comparison used only for discovery/cross-check, not as provider policy: https://taptoagent.com/agents/video/ ; https://getvideoai.app/best-free-ai-video-generators ; https://vidfare.com/guides/free-ai-video-generators/


---

# AI Video Generation Web UI — fourth expansion (23 November 2026)

## Flyne AI — Layer 1 addition (dedicated free video generator)

**Classification:** **Layer 1 — anonymous, free and unlimited (provider-claimed; constrained output/queue).** The user identifies `https://flyne.ai/free-ai-video-generator/` as a Layer 1 provider. This is a dedicated no-signup video-generation route and must be distinguished from Flyne AI’s broader logged-in platform and its credit-based pricing page.

| Field | Finding |
|---|---|
| Access | The dedicated page is presented as a free video generator with no account/signup requirement. An independent November 2026 product listing also reports that no account is required. A verification step/CAPTCHA may still be requested; that is not the same as account registration. |
| Quota | The dedicated workflow is described as having no generation-count cap and no credit charge for its free mode. Treat “unlimited” as a **provider claim**, not a measured guarantee of continuous throughput. |
| Generation | Text-to-video, or image-to-video using a start image and an end image. The free route is reported as a 5-second clip at 480p, with 16:9, 9:16 and 1:1 aspect ratios. |
| Watermark | The dedicated free page is reported as offering downloads without a watermark. This is specific to the dedicated free route; do not generalize it to every model or paid-platform workflow. |
| Queue / reliability | A free queue may delay requests. Queue wait, verification, server availability and throttling are operational constraints, but are not evidence of a fixed daily generation quota. |
| API | No public API was identified for this dedicated free tool in the independent listing. Do not count it as a free API provider. |
| Broader Flyne platform | The separate `flyne.ai/pricing/` page describes a logged-in Free plan with 40 new-user credits, 20 daily check-in credits, low-quality generations, shared queue and other tool limits. That credit-based platform plan is **not the same access path** as the dedicated no-signup video generator. Keep the two offers separate in the catalogue. |

**Evidence labels:** `L1_NO_ACCOUNT_REPORTED / VENDOR_CLAIM_NO_GENERATION_CAP / FREE_QUEUE / 5S_480P_REPORTED / NOT_LIVE_TESTED_IN_THIS_RESEARCH_PASS`.

**Important classification note:** Layer 1 here means anonymous access with no stated fixed generation quota on this specific free page. It does not mean unlimited resolution, clip duration, queue priority, speed or guaranteed uptime. If future first-party terms reveal a daily cap or require an account, downgrade the entry to Layer 2 or Layer 4 as appropriate.

Sources:
- Official dedicated free generator: https://flyne.ai/free-ai-video-generator/
- Official general video generator interface: https://flyne.ai/ai-video-generator/
- Official broader platform pricing (separate logged-in credit plan): https://flyne.ai/pricing/
- Independent November 2026 description of the dedicated free workflow (5 seconds, 480p, no account, no credits/no watermark, queue and verification caveats): https://amplibee.com/launches/free-ai-video-generator

## Corrected video-layer inventory

| Layer | Current findings |
|---|---|
| **1 — Anonymous, free and unlimited** | **Flyne AI dedicated free video generator** — no-signup route; no generation-count cap claimed for its 5-second/480p workflow; verification/free queue may apply. Provider claim, not independently load-tested. |
| **2 — Anonymous, free but limited** | Magic Hour (3 shared requests/day), Rendastic (1/day), FreeGenVideo (1/day), MoveFrame (conflicted daily-credit claims), Wan2.Video (limit undisclosed), plus limited/conflicted Hugging Face Spaces (Omni-Video-Factory, Pika H3 Flex). |
| **3 — Account required, free and effectively unlimited** | ZSky AI — vendor-claimed unlimited, with watermark/slow queue/7-day retention; not independently load-tested. |
| **4 — Account required, free but limited** | VidoGrid (web and Android same service according to user's firsthand report; intermittent server errors reported; exact quota unresolved), Google Flow, Krea, Dreamina, Adobe Firefly, Fliki, HeyGen, PixVerse, Vidu and other previously documented recurring/free-account tiers. Flyne’s separate general-platform credit plan also belongs here, but it is not the dedicated free generator route. |
| **5 — One-time trial or non-renewing grant** | Runway and other previously documented one-time credit/trial services. |

**Research-quality note:** The user’s correction establishes Flyne as the intended Layer 1 entry in this catalogue. The public page and independent listing support the no-signup/no-cap description, but no live repeated-generation test was performed in this research pass. Keep provider claims, independent descriptions and hands-on user confirmation distinct.


---
