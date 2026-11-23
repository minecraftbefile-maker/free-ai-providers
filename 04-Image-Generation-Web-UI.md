# AI Image Generation — Web UI

> Browser-based image generation inventory, preserving the original five-layer Web UI classification.

## How to use this file

1. Open the official product page linked in the provider entry.
2. If the entry says **anonymous/no signup**, try the public page without creating an account. If it requires login, use the provider's own sign-up flow; do not use unofficial account-sharing methods.
3. Check the actual free allowance shown in the product's current interface. Do not assume browser credits can be used through the API.
4. Generate a short sample first. Confirm whether preview, full generation, download/export, watermark removal and commercial use are included in the free tier.
5. Save/export the result only through the product's supported controls. Check whether outputs expire or are public by default.
6. Review privacy and retention terms before uploading personal audio, images, documents or other sensitive content.

**Important:** Web UI entries are browser products, not developer APIs, unless a separate API entry explicitly confirms an API entitlement.

## Research inventory (preserved from the source catalogue)

## Next Web UI category — AI Image Generation (research opened)

The next category is **browser-based AI image generation**, not image-generation APIs, local models, self-hosted frontends, or image editors unless the editor includes a genuine generative-image feature. Keep the same five-layer Web UI taxonomy:

1. Anonymous, free, and unlimited.
2. Anonymous, free but limited.
3. Account required, free and effectively unlimited.
4. Account required, free but limited/recurring.
5. One-time trial or non-renewing grant.

### Initial image-generation leads — not yet a final ranking

| Service | Initial likely layer | What the current evidence says | Verification still needed |
|---|---:|---|---|
| **Perchance.org AI Image Generator** | **1 — confirmed user-reported real use; vendor claims unlimited** | The official Perchance generator ecosystem exposes text-to-image through its `text-to-image-plugin`; public generators advertise free, no-login, no-daily-credit-limit image generation. The user independently reports having actually tried it and confirms that it works as a real generator. | Keep the exact distinction: no-login and working are user-confirmed; unlimited/no hard cap is supported by generator-page claims, not an independent sustained-load test. Capacity, queues, output dimensions, and service availability may vary. |
| **Raphael AI** | 1/3 split candidate | Its official About page says visitors can generate without signup, and a free account provides unlimited standard-quality images. Premium models such as Nano Banana Pro, Veo, and Kling consume credits. Free outputs are personal/non-commercial according to the page. | Determine whether anonymous generation has a numeric cap; distinguish guest from account-based standard-quality unlimited; check resolution, queue, privacy, and model choice. |
| **Craiyon** | 2 candidate | Current independent review reports no-signup image generation with limited output, watermark, and public images. | Verify the current official free quota, watermark, queue, public visibility, download resolution, and whether account creation changes the quota. |
| **nokeep** | 2 candidate | Current independent review reports 10 free images/day without an account, with results retained in the browser. | Verify the official site and current daily reset, image count per prompt, output resolution, and actual generation availability. |
| **Nebula / FreeBuff** | 1 unverified claim | Its page claims unlimited no-account generation using Stable Horde's anonymous shared key and volunteer GPU queue. | Treat as a strong lead, not confirmed: verify the actual generator route, model availability, real successful output, queue behavior, and whether the UI's claims match the underlying service. |
| **Bing Image Creator** | 4 candidate | Current 2026 roundup reports a recurring daily fast-generation allowance followed by slower standard generation; account required. | Verify Microsoft's official current quota, regional availability, boost/reset rules, and whether the no-cost standard mode remains usable after fast boosts run out. |
| **Ideogram Free** | 4 candidate | Current 2026 roundup reports a weekly free credit pool and account requirement. | Verify official current weekly credit amount, slow/fast generation, public-gallery visibility, and free-tier commercial-use terms. |
| **Recraft Free** | 4 candidate | Current 2026 roundup reports recurring daily credits and account requirement. | Verify official credit amount/reset, vector versus raster entitlements, download limits, and commercial-use rights. |
| **Leonardo.Ai Free** | 4 candidate | Current 2026 roundup reports 150 daily fast tokens on its free account tier. | Verify official token refill, model-specific costs, private/public generation, and free-tier licensing. |
| **Venice AI Free** | 4 candidate | Current 2026 roundup reports a recurring daily image allowance and account requirement. | Verify official daily cap, image model selection, privacy, and region availability. |

These are initial leads only. Third-party roundups are discovery sources, not final evidence. The image category needs a dedicated deep pass against each provider's official pricing/help/terms pages and, where possible, actual browser generation. Do not transfer an API quota or playground limit into a Web UI classification.


## Perchance classification correction — text + image Layer 1 (23 November 2026)

This addendum supersedes earlier statements that Perchance was only an image-generation lead or that its official route had not yet been confirmed. The user reports first-hand successful use and explicitly confirms that Perchance is a real, working generator, not merely a promotional claim or a trial/demo. Record that user evidence separately from the platform's own unlimited-use claims.

### Perchance — Layer 1 for browser image generation

- **Provider/platform:** Perchance.org (the original Perchance generator platform).
- **Official image-generation component:** `text-to-image-plugin`, used by public generators built on Perchance.
- **Access:** public generator pages run without requiring a Perchance account; the platform account is optional and is mainly for creating/managing one's own generators.
- **Free-use claim:** public generator pages explicitly describe free image generation with no login and no daily credit limit. The platform is ad-supported; there is no consumer credit wallet or paid plan required on the standard public generator route.
- **Evidence:** official plugin page and official public generator source; additional independent 2026 review reports successful generation without an account and describes multiple images per prompt. The user separately confirms real successful use.
- **Classification:** `L1_NO_LOGIN / FREE / USER_CONFIRMED_WORKING / VENDOR_CLAIM_NO_DAILY_CAP / SUSTAINED_UNLIMITED_NOT_STRESS_TESTED`.
- **Important precision:** place it in Layer 1 under the agreed catalogue convention because the official public generator advertises no login and no daily credit limit, and the user confirms it genuinely generates. Do not overstate this as a guarantee of unlimited throughput: temporary throttling, queue delays, IP/network controls, maintenance, and changing model availability can still occur.
- **Official references:** https://perchance.org/text-to-image-plugin ; https://perchance.org/ (public generators are community-created; example public generator: https://perchance.org/uus69max0w).

### Perchance — Layer 1 for text generation (scope-qualified)

Perchance also provides hosted AI text generation through its official `ai-text-plugin`, which is embedded in ready-made public generators. This is not the same thing as claiming that every Perchance text tool is a universal general-purpose assistant: the best-supported first-party examples are story writing and text-adventure/RPG generation.

| Public text interface | What it does | Access / allowance evidence | Classification |
|---|---|---|---|
| **AI Story Generator** | Generates and continues stories using Perchance AI text functionality. | Official page title explicitly says “free, unlimited, no sign-up”; a normal public generator page is usable without logging in. | **Layer 1** — `L1_NO_LOGIN / VENDOR_CLAIM_FREE_UNLIMITED / USER_CONFIRMED_PERCHANCE_PLATFORM` |
| **AI RPG / Text Adventure** | Interactive text adventure with AI-generated narration and responses. | Official page title explicitly says “free, unlimited, no sign-up”; public interface does not require an account to start. | **Layer 1** — `L1_NO_LOGIN / VENDOR_CLAIM_FREE_UNLIMITED / USER_CONFIRMED_PERCHANCE_PLATFORM` |
| **AI Text Plugin** | The underlying text-generation plugin used by Perchance generators; it is a component/developer-facing plugin rather than a standalone chat product. | Official plugin page is public; public generators using it provide the actual consumer-facing interface. | Supporting technology, not a separate additional provider. |

**Text classification note:** include Perchance in the Text Generation category's Layer 1 as a text-generation platform, but tag the use case as `STORY / ROLEPLAY / GENERATIVE_TEXT`, not as a verified all-purpose Q&A/search/coding assistant. This avoids exaggerating its scope while still recognizing the free no-login text-generation capability the user pointed out.

**Official references:** https://perchance.org/ai-text-plugin ; https://perchance.org/ai-story-generator ; https://perchance.org/ai-rpg ; https://perchance.org/terms-of-service

### Why the earlier notes are superseded

Earlier rows described Perchance image generation as a candidate awaiting direct confirmation, and the initial text Layer 1 section said no provider was confirmed. Those statements were snapshots from before the user's first-hand confirmation and this official-source review. For the current catalogue state, Perchance is now listed in Layer 1 for both image generation and text generation, with the scope and evidence qualifications above. Keep older dated research notes as historical audit trail, but treat this addendum as the latest classification.


## AI Image Generation Web UI — deep research expansion (23 November 2026)

This is an additive research pass for the browser-based image-generator category. It does **not** replace the earlier API research. Classification uses the agreed five Web UI layers:

1. **Layer 1:** anonymous, free, no account, and vendor-claimed no fixed generation cap. A queue or anti-abuse throttle may still exist; do not call it guaranteed unlimited throughput.
2. **Layer 2:** anonymous and free, but with a daily, session, ad-reward, or shared-capacity limit. If the number is not disclosed, use `LIMIT_UNDISCLOSED`.
3. **Layer 3:** account required, free, and standard image generation explicitly described as unlimited/effectively unlimited. Separate relaxed/slow modes from premium models and tools.
4. **Layer 4:** account required, free with renewable but limited daily/weekly/monthly credits or a model/tool-specific usage cap. `QUOTA_UNDISCLOSED` is not unlimited.
5. **Layer 5:** one-time bonus, trial credits, or a non-renewing free grant.

### Executive findings

- **Perchance remains the strongest Layer 1 account-free option** in this inventory. The user has independently confirmed that the actual image generator works. Its own public generator/plugin pages advertise free use without sign-up and no daily credit cap. This is evidence for the catalogue's Layer 1 convention, not a guarantee of unlimited throughput or uptime.
- **Raphael AI has a useful split classification:** visitors can start basic generation without an account, and its official About page says a free account gives unlimited standard-quality images. However, free outputs are for personal/non-commercial use; paid models/features and higher-resolution access are distinct. A third-party November test reported a long queue and could not complete a generation during its 120-second observation, so its availability can be inconsistent.
- **Opera AI is the clearest documented anonymous limited option:** five images per day without signing in. Opera GX's official page separately says signed-in accounts can receive 100 images/day.
- **FreeWebImage is a strong Layer 2 find:** one anonymous generation/day, then two additional generations for every three rewarded ads, up to 30/day. Results are stored for 24 hours unless downloaded; shared-wall copies remain public for seven days.
- **IMAGEKA is another Layer 2 option:** no account, but a CAPTCHA/security code and a fair-use ceiling of 100 generations per person/day. Outputs remain in browser storage until downloaded.
- **Bing Image Creator is more generous after login than as a guest:** guest limits reset daily and can be at capacity; Microsoft's current page advertises 10 free Fast creations and unlimited Standard-mode creations after sign-in. This is a mode-specific free entitlement, not unlimited fast/high-priority output.
- **Gemini, ChatGPT, Firefly, Krea, Leonardo and Ideogram all have free image creation, but their image limits are separate from their text/chat quotas.** Do not infer an image allowance from a general free chat plan.
- **Mage's 300 Gems are a one-time signup bonus**, not a recurring free tier. Its own page says the bonus expires after 90 days and every image-generation run consumes Gems.
- **Local browser inference is excluded from hosted Web UI layers.** FreeGen runs models on the visitor's own GPU after a large model download; it is not a provider-hosted free generation service. Local Stable Diffusion, InvokeAI installations, Draw Things, and self-hosted interfaces likewise belong in a separate local/self-hosted category.

### Layer 1 — anonymous, free, no fixed quota advertised

| Service | What is actually offered | Access and limit evidence | Status / caveats | Official / discovery sources |
|---|---|---|---|---|
| **Perchance.org — AI Image Generator** | Text-to-image through the official `text-to-image-plugin` and public community generators. | No account required for public generators. The public generator/plugin ecosystem advertises free use without sign-up and no daily credit limit. User independently confirms successful real generation. | `L1_NO_LOGIN / USER_CONFIRMED_WORKING / VENDOR_CLAIM_NO_DAILY_CAP`. Do not translate this into a throughput guarantee; queues, pacing, model availability, network/IP controls and service outages remain possible. Check each public generator's own settings and content rules. | https://perchance.org/text-to-image-plugin ; https://perchance.org/ |
| **Raphael AI — anonymous Basic mode** | Hosted text-to-image plus a growing suite of image editing/restyling tools. | Official site says users can start without an account or card and describes basic generation as free with unlimited generations. | `L1_VENDOR_CLAIM_UNLIMITED / QUEUE_RELIABILITY_CONFLICT`. Third-party 27 Oct test could not get an output within 120 seconds because it remained queued; that does not disprove the free entitlement, but it shows availability/latency can be a practical limit. Free output is personal/non-commercial according to the official About page. Premium models, fast mode and higher resolutions are not part of the same free unlimited promise. | https://raphael.app/ ; https://raphael.app/about ; test report: https://veida.ai/blog/free-unlimited-ai-image-generator-no-sign-up |
| **Craiyon — free guest generator** | Basic text-to-image generation in the browser. | Third-party 2026 reviews report generation without an account and no published numeric daily cap. | Keep as `L1_CANDIDATE / LIMIT_NOT_PUBLISHED`, not fully confirmed unlimited: the current official pages found in this pass did not clearly establish an unlimited quota. Ads, queue/wait times, lower-resolution output and visible branding may apply. Public visibility and commercial rights must be checked against current terms before use. | https://www.craiyon.com/ ; discovery: https://nokeep.ai/best-free-ai-image-generator |
| **Aitubo — guest generator** | Multi-model image generation and image editing tools. | Third-party 2026 guides report no-login access and repeat the provider's unlimited-use claim. | `L1_VENDOR_CLAIM_UNLIMITED / OFFICIAL_QUOTA_RECHECK_REQUIRED`. Do not upgrade to confirmed Layer 1 until a current official pricing/terms page clearly states the guest limit and a real anonymous output is verified. | https://aitubo.ai/ ; discovery: https://thatpainter.com/7-best-free-ai-image-generators-with-no-sign-up-or-account-2026-guide/ |
| **DeepAI — guest image generator** | Hosted image generation from a browser prompt. | Recent third-party hands-on reports show at least one anonymous image generation, but further requests and model modes were not consistently tested. | `L1_CANDIDATE / LIMIT_UNDISCLOSED`. Do not infer unlimited use from one successful generation. Distinguish the standard free route from paid/Genius modes and check current terms. | https://deepai.org/machine-learning-model/text2img ; discovery/test notes: https://veida.ai/blog/free-unlimited-ai-image-generator-no-sign-up |

**Layer 1 conclusion:** Perchance is the strongest evidence-backed entry because the user has directly tested it and the public generator pages advertise no daily credit limit. Raphael is a strong provider-claimed unlimited Basic route but its queue and commercial-use restrictions matter. Other no-login services remain candidates until quota and current anonymous generation are better established.

### Layer 2 — anonymous, free but limited

| Service | Anonymous allowance | What counts / reset | Important caveats | Official source / evidence |
|---|---|---|---|---|
| **Opera AI Image Generator** | **5 images/day** without sign-in. | Daily allowance. Opera GX's official page separately reports 100 images/day for signed-in accounts. | Requires the Opera browser (including Opera GX); this is a browser-integrated feature, not a generic standalone web app. Image quota differs from other AI chat features. | https://www.opera.com/features/opera-ai-image-generator ; https://www.opera.com/gx/features/opera-ai |
| **FreeWebImage** | **1 generation/day**, plus **2 generations per 3 short rewarded ads**, up to **30/day**. | Rewarded ads unlock additional two-generation batches. | No account, API key or card. Images stored for 24 hours; shared community-wall copies remain public for 7 days. SFW-only. Prompts are sent to underlying inference providers. | https://freewebimage.com/ |
| **IMAGEKA** | **100 generations/person/day**. | Daily fair-use cap; security code/CAPTCHA required. | No account. Images remain in local browser storage until downloaded; clearing browser storage can remove them. Site says its model router uses several open models; quality varies by model and prompt. | https://www.imageka.com/ |
| **nokeep** | **10 images/day** according to its 5 Oct 2026 comparison/check. | One image per generation/edit action; allowance reported daily. | No account. Prompt and outputs are stored in the browser rather than a cloud account according to the site's explanation. Current official page/limit should be rechecked before relying on the exact count; the independent review is the clearest quota evidence found. | https://nokeep.ai/best-free-ai-image-generator |
| **Bing Image Creator — guest mode** | Guest access exists, but Microsoft does not give a stable numeric guest count in the captured FAQ. Guest capacity may already be exhausted. | Guest limits reset daily. | This is a genuine anonymous entry point, but the service may display “guest creation is at today's capacity.” After signing in, a different allowance applies: 10 Fast creations and unlimited Standard mode. Do not transfer signed-in limits to guest mode. | https://www.bing.com/images/create/ai-image-generator/faq |
| **Ngini** | Homepage advertises first 10–15 daily free images; its detailed text says the actual free credits are **6/day**, with model-dependent credit costs. | Daily credit reset; heavier models consume more credits. | No account or card. The same input may handle chat/video/music/code, so usage can be shared across services. One independent test reported the daily wall after three outputs; treat the quota as conflicted and use `ALLOWANCE_CONFLICTED` until the provider clarifies it. | https://ngini.com/en-us/free-ai-image-generator-no-signup ; conflicting 2026 test: https://veida.ai/blog/free-unlimited-ai-image-generator-no-sign-up |
| **Pollinations public image playground** | Anonymous web/API routes have changed; some legacy endpoints were accessible without a key, but the current generation service may require account/authentication. | No reliable current anonymous Web UI quota established. | Do not treat the old keyless image API as proof that the current browser playground is anonymous. Keep this out of confirmed Layer 2 until a current no-login UI session and output are reproduced. API classification remains in the API section. | https://pollinations.ai/ ; https://gen.pollinations.ai/ |

### Layer 3 — account required, free standard image generation effectively unlimited

| Service | Free account entitlement | What is and is not unlimited | Status / caveats | Official sources |
|---|---|---|---|---|
| **Raphael AI — signed-in Basic** | Official About page says a free account gives unlimited standard-quality images and free AI videos every day. | Standard image generation is described as unlimited; premium models, fast mode, higher resolution and other credit-based tools are separate. | `L3_VENDOR_CLAIM_UNLIMITED_STANDARD`. Free users may use images only for personal, non-commercial purposes. Anonymous Basic and signed-in Basic are separate access modes and should both be recorded without counting Raphael as two providers. | https://raphael.app/about ; https://raphael.app/ |
| **Veida AI — account-based Image v1** | An October 2026 third-party test reports that signing in with Google/email unlocks unlimited Image v1 generations and image edits on a free account. | Claimed unlimited only for the named base model; paid models and removal of watermark/commercial rights are separate. | `L3_REPORTED_UNVERIFIED`. The same report says free images carry a Veida mark and commercial rights are paid-plan only. Official current pricing/terms were not independently established in this pass; do not treat as confirmed. | Discovery/test: https://veida.ai/blog/free-unlimited-ai-image-generator-no-sign-up ; provider: https://veida.ai/ |

**Layer 3 conclusion:** Raphael is the clearest first-party-supported entry. Veida is a promising but not yet officially cross-checked candidate. Do not call a free account unlimited if only some models, relaxed mode, or edits are unlimited.

### Layer 4 — account required, free but limited / recurring

| Service | Free allowance | Reset / scope | Important limitations | Official source |
|---|---|---|---|---|
| **Bing Image Creator / Microsoft Designer** | **10 Fast creations** plus **unlimited Standard-mode creations** on the signed-in free route, per Microsoft's current page. | Fast and Standard are separate modes; Microsoft Rewards can provide additional Fast credits. | “Unlimited” applies only to Standard mode, which can be slower; guest mode has a separate daily-capacity message. Watermark can be configured in settings. Country/region availability varies. | https://www.bing.com/images/create/ai-image-generator/faq |
| **Google Gemini image generation** | Image creation is available on the free plan; the official product page advertises free access to Nano Banana. | The precise current image quota is not clearly published in the official product page captured in this pass. | `QUOTA_UNDISCLOSED_OFFICIAL`. Do not repeat third-party claims such as 100 images/day without first-party confirmation. Google account required; model availability and caps can vary by region and demand. | https://gemini.google/overview/image-generation/ ; general Gemini help: https://support.google.com/gemini/ |
| **ChatGPT Free** | Image creation is included in the Free plan. | Separate tool-specific usage limit; the official FAQ says users are notified when they reach it but does not state a fixed image count in the reviewed page. | `QUOTA_UNDISCLOSED_OFFICIAL`. Do not infer the image quota from unlimited everyday text chat. Limit resets are shown in product when available. | https://help.openai.com/en/articles/9275245-chatgpt-free-tier-faq |
| **Adobe Firefly Free** | Limited free daily image/video generations; current page does not publish one universal fixed image count in the captured plan table. | Daily, shared generative allowance across eligible image/video features. | `DAILY_LIMIT_UNDISCLOSED`. The free plan includes limited access to top models and editor/workflow tools; don't confuse paid monthly credits with the free daily grant. | https://www.adobe.com/products/firefly/plans.html |
| **Krea Free** | **100 units/day**. | Daily refill; unit cost varies by model and task. | Not 100 images/day. Different image/video/upscaling/3D tasks consume different units. No credit card required for Free. Check which models are available at Free level. | https://www.krea.ai/pricing |
| **Leonardo.Ai Free** | **150 Fast Tokens/day**. | Daily refill. Token cost varies by model, image size, generation count and post-processing. | Not 150 images/day. Free creations are public; Leonardo's pricing/terms say it retains rights in free-tier outputs while granting the user a non-exclusive royalty-free license, including commercial use. | https://leonardo.ai/pricing |
| **Ideogram Free** | Weekly slow credits for eligible free accounts; the official pricing page confirms weekly credits but the exact quantity may vary by eligibility/account. | Weekly refill; model and rendering settings consume different credits. | Free tier is slow/queued and does not include private generations. Some accounts sign in through Google, Apple or Microsoft. Do not assume the same credit amount for every account. | https://ideogram.ai/pricing/ |
| **Mage Free** | No recurring free image quota established. It gives a **one-time 300-Gem signup bonus**. | Gems are consumed by each generation and expire 90 days after being credited. | Correctly classify under Layer 5, not Layer 4. No watermark and private-by-default outputs are advertised, but this does not make the grant recurring. | https://www.mage.space/free-ai-image-generator |
| **Canva AI image generation** | AI image generation is available within Canva's free plan, but a clear image-specific recurring allowance was not established from the current official page in this pass. | Shared AI usage limits may apply across Magic Studio tools. | Keep as `L4_QUOTA_UNDISCLOSED / NEEDS_IMAGE_SPECIFIC_CONFIRMATION`; do not claim a number or equate total Canva AI usage with image generations. | https://www.canva.com/ai-image-generator/ |
| **Recraft Free** | Free account image generation exists, but a current first-party daily credit number was not captured in this pass. | Exact refill/cost must be rechecked in current pricing/help. | Keep as `L4_QUOTA_UNDISCLOSED / OFFICIAL_RECHECK_REQUIRED`; also record the free-plan output-license limitations separately from generation count. | https://www.recraft.ai/ ; https://www.recraft.ai/pricing |
| **Venice AI Free** | Free account includes image generation, but the current exact daily image quota was not independently confirmed from first-party evidence in this pass. | Do not treat third-party quota numbers as official. | `L4_QUOTA_UNDISCLOSED_OFFICIAL`; image model access and daily usage can differ from text chat. | https://venice.ai/ |

### Layer 5 — one-time trial / non-renewing grants

| Service | One-time allowance | Expiry / restrictions | Classification | Official source |
|---|---|---|---|---|
| **Mage** | **300 bonus Gems** on a free account. | Bonus Gems expire 90 days after crediting; each generation consumes Gems. Basic paid plan is what removes the counter for covered models. | `L5_ONE_TIME_SIGNUP_GRANT`. | https://www.mage.space/free-ai-image-generator |
| **Stability AI Platform** | **25 free API credits** for new accounts, usable for Stable Image/Stable Audio API tests. | API key/account required; this is an API trial, not a browser Web UI allowance. | Keep in the API Layer 3 table only; explicitly exclude from Web UI Layer 5. | https://platform.stability.ai/ ; https://platform.stability.ai/docs |
| **Replicate selected model trials** | Selected models may offer a limited number of free test runs for eligible new users. | Number of runs is model-specific and not a stable recurring allowance. This is an API/developer experience rather than a general-purpose consumer image Web UI. | Keep in API Layer 3, not Web UI Layer 5. | https://replicate.com/collections/try-for-free |

### Additional candidates and exclusions

| Name | Research result | Correct handling |
|---|---|---|
| **AI Horde / ArtBot** | Browser-based volunteer-compute image generation; queue/Kudos system and anonymous use can vary by frontend and worker availability. Zero-Kudos access can be slow and is not a dependable fixed daily image allowance. | Keep as `L2_SHARED_VOLUNTEER_CAPACITY / LIMIT_VARIABLE`; do not call it guaranteed unlimited. Official: https://aihorde.net/ ; frontend: https://artbot.site/ |
| **Hugging Face ZeroGPU Spaces** | Some public image Spaces permit anonymous browser use through a shared compute budget; exact access and queue depend on each Space. Anonymous and free-account time budgets differ and the shared pool is not a per-Space quota. | Candidate Layer 2 only, not a single stable image-generator provider. Each Space needs a fresh no-login end-to-end test. Official: https://huggingface.co/docs/hub/en/spaces-zerogpu |
| **FreeGen.ai** | Runs Janus-Pro/FLUX.2 Klein in the user's own browser using WebGPU; model download can be 1.5 GB or about 6.4 GB. | Exclude from hosted image Web UI layers; label `LOCAL_BROWSER_INFERENCE / USER_DEVICE_COMPUTE`. Official: https://freegen.ai/ai-image-generator |
| **InvokeAI / Draw Things / Krita AI Diffusion** | Local or self-hosted software. | Exclude from hosted Web UI catalogue; keep in a separate local/self-hosted section. |
| **Magic Studio, FreeImgGen, FreeForAI, NeonSnap, FreeArtGen, Genbox, Z-Image AI** | Discovered in 2026 comparisons, but no sufficiently consistent current official quota and live availability evidence was captured for all of them. Some third-party tests report sign-in walls, global capacity limits or contradictory “unlimited” claims. | Retain as `CANDIDATE_UNVERIFIED` only; do not promote to confirmed layers until the official entitlement and anonymous/account workflow are checked. |
| **Aitubo, Craiyon and Raphael** | Multiple independent guides disagree about exact no-login limits, watermarks and queue behavior. | Keep each as a separate product and preserve evidence conflicts; do not silently harmonize claims from different dates. |

### Practical shortlist by user need

| Need | Strong starting point | Why / limitation |
|---|---|---|
| Most repeated generation without creating an account | **Perchance** | User-confirmed working; public pages advertise no daily credit cap. Quality/model transparency and queue can vary. |
| No-account image generation with a defined daily ceiling | **Opera AI** | Five images/day and official no-sign-in support; requires Opera browser. |
| No-account generation with a clear ad-supported path to more output | **FreeWebImage** | One free daily generation plus rewarded ads, up to 30/day. Outputs expire from the service after 24 hours. |
| Browser-only image generation with explicit fair-use number | **IMAGEKA** | 100 generations/person/day, no account, local browser storage. |
| Account-based standard mode with unlimited claim | **Raphael AI** | Free account has unlimited standard images per official About page; free output is personal/non-commercial and queues can be slow. |
| Large recurring daily compute budget across creative tasks | **Krea** | 100 units/day, but units are shared across tasks and not equivalent to 100 images. |
| Clear daily image-generation token budget | **Leonardo.Ai** | 150 Fast Tokens/day; actual image count varies with token cost. Free outputs are public. |
| Weekly image-generation credits | **Ideogram** | Weekly slow credits; useful for text-in-image design, but outputs are not private on free tier. |
| Free generation with a high-volume Standard mode after login | **Bing Image Creator** | 10 Fast creations plus unlimited Standard mode according to Microsoft's current page; Standard is slower and region availability varies. |
| Privacy-oriented account-free local inference | **FreeGen** | Not hosted: all compute occurs on the user's own compatible GPU and requires a large one-time model download. |

### Verification, privacy, rights and reliability checklist

1. **A successful generation is different from an unlimited entitlement.** Record separately: whether the generator opened, whether a full output was returned, how many consecutive generations were completed, and whether the page showed a quota/queue wall.
2. **No account does not mean no tracking or private.** IP-based abuse controls, cookies, analytics, provider-side prompt retention and public galleries may still apply. IMAGEKA and nokeep say results stay in browser storage; FreeWebImage keeps outputs temporarily on its service; free Ideogram generations are not private.
3. **Commercial-use rights are a separate field.** Raphael's official About page says free users are limited to personal, non-commercial use. Leonardo's free-tier terms grant a royalty-free commercial license while Leonardo retains rights. Ideogram free generations are public and do not include private generation. Never infer commercial rights from “free”.
4. **Watermarks are model/plan-specific.** Some providers add watermarks only on free outputs, while others allow a setting toggle or no watermark. Record the actual downloaded file, not only a marketing statement.
5. **Resolution and image count are not interchangeable.** A “generation” may return multiple variants; editing, upscaling, background removal and reference-image edits may consume separate credits or count as another generation.
6. **Regional availability matters.** Bing and some Google/Adobe features may vary by country. A page being publicly visible does not prove that image generation is enabled in Libya or every region.
7. **No live account-based quota test was performed in this research pass.** The entries above are separated into official documentation, independent reports, and user-confirmed use. `OFFICIAL` means public provider documentation supports the claim; it does not mean a fresh generation was completed from this research session.

### Sources — official first-party evidence

- Perchance image plugin: https://perchance.org/text-to-image-plugin
- Raphael AI official About / terms: https://raphael.app/about ; https://raphael.app/
- Opera AI image generator and Opera GX quota FAQ: https://www.opera.com/features/opera-ai-image-generator ; https://www.opera.com/gx/features/opera-ai
- FreeWebImage anonymous quota and rewarded-ad rules: https://freewebimage.com/
- IMAGEKA no-account workflow and 100/day fair-use limit: https://www.imageka.com/
- Bing Image Creator guest/signed-in allowance: https://www.bing.com/images/create/ai-image-generator/faq
- Adobe Firefly free daily allowance: https://www.adobe.com/products/firefly/plans.html
- Krea 100 units/day: https://www.krea.ai/pricing
- Leonardo 150 Fast Tokens/day and free-tier rights: https://leonardo.ai/pricing
- Ideogram weekly slow credits: https://ideogram.ai/pricing/
- ChatGPT Free image-generation entitlement and separate limits: https://help.openai.com/en/articles/9275245-chatgpt-free-tier-faq
- Gemini image-generation product page: https://gemini.google/overview/image-generation/
- Mage 300 one-time Gems and 90-day expiry: https://www.mage.space/free-ai-image-generator
- FreeGen local browser inference: https://freegen.ai/ai-image-generator

### Independent discovery / cross-check sources (not substitutes for provider terms)

- nokeep's 3 October 2026 comparison: https://nokeep.ai/best-free-ai-image-generator
- 2026 no-sign-up generator comparison: https://thatpainter.com/7-best-free-ai-image-generators-with-no-sign-up-or-account-2026-guide/
- October 2026 cross-tool hands-on test with conflicting queue/limit observations: https://veida.ai/blog/free-unlimited-ai-image-generator-no-sign-up
- November 2026 broad tool comparison: https://techunbloated.com/best-free-ai-image-generators/
- November 2026 no-sign-up roundup: https://rottenwifi.com/7-best-free-ai-image-generators-with-no-sign-up-or-account/

**Research status:** this pass substantially expands the image Web UI inventory and replaces the earlier “initial leads only” status. It does not claim a complete census of every community generator. Perchance remains the top anonymous unlimited-claim entry; Raphael is the main account-based unlimited-standard candidate; Opera, FreeWebImage and IMAGEKA are the strongest documented anonymous limited alternatives; the major account-based platforms are catalogued with their actual recurring or undisclosed image-specific limits.

### Final image-category expansion — additional first-party checks (23 November 2026)

This pass adds newly verified provider-owned details and corrects several quota descriptions. It does not overwrite the earlier evidence ledger: where pages conflict or a quota is not numerically published, that uncertainty remains visible.

#### Additional recurring account-based image generators

| Service | Layer | Current free offer found | Reset / what the number means | Important caveats | First-party evidence |
|---|---:|---|---|---|---|
| **PixAI** | **4** | **10,000 free credits daily** for a free account; the official signup page and documentation both state the daily grant. | Daily claim after sign-in. Credits are not images: default-model examples show about 3,600 credits for a four-image batch, while higher-quality models and priority modes cost more. Unused credits can roll over according to PixAI's own explanatory article. | Strong addition for anime/illustration, community models and LoRAs, image-to-image, character consistency, upscaling and animation. No card required. First app sign-in may add a separate 25,000-credit bonus; do not count it as recurring daily allowance. Check current license/attribution terms before commercial use. | https://pixai.art/en/sign-up ; https://docs.pixai.art/docs/introduction/first-image ; https://docs.pixai.art/docs/pricing/credits-earn ; https://blog.pixai.art/en/best-free-anime-ai-generator/ |
| **NightCafe** | **4** | Official site confirms free credits are dropped daily and community activities can earn more. | Daily recurring grant; the current official pages reviewed here do not state one universal fixed number of credits for every account/model. | Multi-model art community with image and video tools, daily challenges and browser/mobile access. Do not copy third-party claims such as “5 credits/day” into the confirmed quota column until a current first-party page confirms the exact amount and eligibility. | https://nightcafe.studio/ ; https://help.nightcafe.studio/ |
| **Opera AI / Opera GX** | **2 and 4** | Official Opera page says image generation is available without sign-in: **5 images/day** for accountless use. Opera GX's official FAQ says signed-in users can generate **100 images/day**. | Daily image count; keep anonymous and signed-in entitlements separate. | Requires the Opera browser / Opera GX experience, not a standalone universal web app. This is a useful browser-integrated image generator. Do not list it as unlimited. | https://www.opera.com/features/opera-ai-image-generator ; https://www.opera.com/gx/features/opera-ai |

#### Quota corrections and source conflicts

| Service | Corrected finding | How to record it |
|---|---|---|
| **Bing Image Creator — signed in** | Microsoft's current FAQ snapshot says **10 free Fast creations** and **unlimited Standard-mode creations**. Older comparison pages and earlier snapshots report 15 Fast creations. | Prefer the current first-party FAQ's 10 Fast figure and keep the older 15 figure in the historical/conflict note only. Standard mode is slower and is a distinct mode; do not call the entire service unconditionally unlimited. Official: https://www.bing.com/images/create/ai-image-generator/faq |
| **Ideogram Free** | Official Quick Start states **30 credits/week** only for Google and Apple sign-ups. Microsoft/email sign-ups receive no free credits according to that page. | Record the sign-in-method eligibility, not just “30 credits/week for everyone.” Official: https://docs.ideogram.ai/quick-start-guide |
| **Krea Free** | Official product page states **100 units/day**, not 100 images. | Keep units separate from generated-image count; model and task costs vary. Official: https://www.krea.ai/features/ai-image-generator |
| **PixAI** | Third-party listings describe “10,000 credits/day”; PixAI's own signup, documentation and credit-earning pages independently confirm it. | Promote from directory-only candidate to official recurring free plan. Do not convert credits into a fixed number of images without model/settings assumptions. |

#### Further anonymous and shared-capacity candidates

| Service | Provisional layer | What the evidence says | Status / caution | Source |
|---|---:|---|---|---|
| **AI Horde / ArtBot** | 2 candidate | Volunteer-powered image generation through a browser frontend; jobs wait for available community workers and can be slow when the queue is busy. | Free/shared compute is real, but there is no guaranteed fixed throughput. Anonymous access and zero-Kudos behavior depend on the frontend and current network policy. Keep `L2_SHARED_VOLUNTEER_CAPACITY / VARIABLE_QUEUE`, not unlimited. | https://aihorde.net/ ; https://artbot.site/ |
| **Craiyon** | 2 candidate | Multiple recent independent no-signup checks report free browser generation without an account. | No stable official numeric guest quota was established here; ads, watermark/quality and queue can vary. Do not call it unlimited just because a number is absent. | https://www.craiyon.com/ ; discovery: https://nokeep.ai/best-free-ai-image-generator |
| **nokeep** | 2 | Independent hands-on comparison reports 10 anonymous images/day, with browser-local storage for prompts and outputs. | Useful privacy-oriented candidate, but the exact daily count is not yet supported by a first-party quota page captured in this pass. Keep `INDEPENDENTLY_REPORTED / OFFICIAL_QUOTA_NOT_CAPTURED`. | https://nokeep.ai/best-free-ai-image-generator |
| **Ngini** | 2 conflicted | Its page says the first 10–15 images/day are free, while detailed credit wording says 6 credits/day and image cost varies; an independent test reports a different practical stop point. | Keep `ALLOWANCE_CONFLICTED`; do not present a single exact quota. | https://ngini.com/en-us/free-ai-image-generator-no-signup ; https://veida.ai/blog/free-unlimited-ai-image-generator-no-sign-up |
| **FreeImgGen / FreeForAI / Magic Studio / NeonSnap / FreeArtGen** | 1 or 2 candidates | Several independent no-signup tests report working image generation, but first-party quota, retention, terms and ongoing availability are not consistently established. | Keep as `CANDIDATE_UNVERIFIED`; do not promote into confirmed unlimited Layer 1. | Discovery: https://findtheperfectai.com/free-ai-image-generator-no-sign-up/ |

#### Image category practical additions

- **Anime, character art and community models:** PixAI is now a major Layer 4 recommendation because its daily credits and browser generation are documented by PixAI itself.
- **Browser-integrated generation:** Opera AI is a documented Layer 2 guest service and Layer 4 signed-in service, with different daily caps.
- **Community art and daily challenges:** NightCafe is confirmed as recurring daily free access, but the exact universal credit count remains unpublished in the official pages reviewed.
- **Volunteer-powered generation:** AI Horde is worth keeping in the directory because it offers a different free-compute model; its queue means it is not a dependable unlimited service.
- **Anonymous alternatives:** Craiyon and nokeep remain useful candidates, but their quota claims should not be elevated above the strength of their evidence.

#### Final image-category status before moving to video

The image section now covers: anonymous unlimited claims (with Perchance as the user's personally tested anchor), anonymous limited services, account-based unlimited-standard claims, recurring daily/weekly credit plans, one-time grants, volunteer/shared compute, local-browser inference exclusions, privacy, public-gallery visibility, watermarking, commercial-use terms, regional access and quota conflicts.

The image research is ready to close as a documented inventory, not as a claim that every generator on the internet has been exhaustively tested. No account creation or live image generation was performed by this research pass. Perchance's actual operation is user-confirmed from the user's own experience; other entries retain their evidence labels.

---

## Next category — AI Video Generation Web UI (research queue)

The next phase is **ready to begin**. Scope is consumer-facing browser interfaces that generate video from text, images or existing clips. Do not mix video APIs, SDKs, self-hosted models, editing-only websites or stock-video libraries into the main Web UI provider tiers.

Use the same five-layer Web UI classification:
1. Anonymous, free and unlimited (require evidence of no declared usage cap; an undisclosed cap is not proof of unlimited).
2. Anonymous, free but limited (record guest quota, session/IP restrictions, queue and reset; use `LIMIT_UNDISCLOSED` if no number is published).
3. Account required, free and effectively unlimited (only if ordinary video generation is explicitly unlimited; separate model, duration, resolution and queue limits).
4. Account required, free but limited (daily/weekly/monthly credits, generations, seconds, compute units or free-tier duration; record reset and model costs).
5. One-time trial or non-renewing grant (signup credits, introductory generations, temporary promotions and expiring trials).

For each video service, capture these fields separately: text-to-video, image-to-video, video-to-video, video extension, maximum seconds per clip, resolution, frame rate if stated, audio generation, watermark, queue/priority, daily/monthly credits, credit cost per second/model, account requirement, phone/card requirements, region restrictions, commercial rights, prompt/output retention and whether exports are actually downloadable on the free plan.

Initial discovery queue only — **not yet classified or confirmed**: Bing Video Creator, Google Flow / Veo, Kling AI, Hailuo AI, PixVerse, Pika, Luma Dream Machine, Runway, Adobe Firefly Video, Canva AI Video, CapCut AI video tools, Vidu, Wan-based hosted generators, and community-hosted video demos. Each must be checked against its current first-party pricing/help pages before inclusion. A free video editor, stock-video library, or API trial does not qualify as a free video-generation Web UI.

Research order for video: first anonymous guest generators; then recurring free account credits; then one-time signup grants. Prioritize tools that let users export a usable video without paying, and record the real clip duration and watermark rather than only the advertised model name.

---
