# AI Image Generation — Hosted APIs

> Hosted image-generation API research only. Consumer browser generators are separated into `04-Image-Generation-Web-UI.md`.

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

# Image and Video Generation APIs

> Split edition of the original 23 November 2026 research ledger. Original source line range: 754–1772. Provider claims and quota snapshots are time-sensitive; read each evidence label and caveat.

# Appendix — Credit-card requirement index for Layers 2 and 3

**Purpose:** Make payment-card requirements visible before a reader creates an account. This index distinguishes a card being required to claim/use the free offer from a card being optional for upgrades or later paid usage.

### Status definitions

- `NO_CARD_REQUIRED` — a current provider page or sufficiently direct offer documentation says a payment card is not needed for the listed free tier/trial.
- `CARD_REQUIRED` — a card or other payment card is required to activate/claim/use the listed offer.
- `CARD_OPTIONAL_FOR_PAID_UPGRADE` — the free offer starts without a card; a card/payment is only relevant if the user chooses paid usage or a paid upgrade.
- `UNKNOWN_NOT_PUBLISHED` — available sources do not establish the card requirement. This does **not** mean no card is needed.
- `CONFLICTED` — sources disagree or the offer's eligibility/activation conditions are unclear.
- `NOT_APPLICABLE` — the candidate is not a currently verified API trial/free allowance.

Do not infer card requirements from “free”, “$0”, or “API key” wording. “No card” does not mean “no identity/phone verification”; those are separate requirements. Do not add a card simply to test an uncertain offer.

## Layer 2 — Recurring free quotas

### No card required (documented/reported for the free tier)

| Provider | Card status | Notes |
|---|---|---|
| GroqCloud | `NO_CARD_REQUIRED` | Free tier does not require a card; phone verification may separately apply. |
| Google Gemini API / AI Studio | `NO_CARD_REQUIRED` | Free-tier project; do not confuse with paid Google Cloud billing. |
| Cloudflare Workers AI | `NO_CARD_REQUIRED` | Free Neurons allowance; paid Workers/features are separate. |
| OpenRouter | `NO_CARD_REQUIRED` | Basic `:free` model allowance; the larger 1,000 RPD tier requires a $10 lifetime purchase, not a card merely to use the basic free tier. |
| Vikasit Inference | `NO_CARD_REQUIRED` | Free daily model allowance. |
| xKiro / xKCode | `NO_CARD_REQUIRED` | Free plan; Telegram verification can increase the quota. |
| Requesty | `NO_CARD_REQUIRED` | Free-model request allowance. |
| AnyAPI | `NO_CARD_REQUIRED` | Vendor terms state no card for the free account; AnyTokens are internal units. |
| DreamPrompting | `NO_CARD_REQUIRED` | Pricing/docs state no card for free access. |
| Electron Hub | `NO_CARD_REQUIRED` | Official homepage says no card for the free plan; paid top-ups are optional. |
| Logfare | `NO_CARD_REQUIRED` | Official homepage says free account/key with no card. Discord membership is a separate access condition. |
| Aion Labs | `NO_CARD_REQUIRED` | Official pricing explicitly says its daily free allowance needs no card. |
| A4F | `NO_CARD_REQUIRED` | Official homepage says API key/free tier starts without a credit card. Its RPD quota documentation conflicts; card status is separate from that quota discrepancy. |
| Synap | `NO_CARD_REQUIRED` | Official account page says signup is free and needs no card; paid top-ups are optional after free allowance. |
| Gonka Broker | `NO_CARD_REQUIRED` | Official billing terms describe account/API key and phone verification for the monthly grant; no card requirement stated. |
| Clean APIs | `NO_CARD_REQUIRED` (vendor claim) | Vendor pricing says no card, but quota/status remains conflicted and is not a dependable recommendation yet. |
| Cohere Trial API | `NO_CARD_REQUIRED` | Free trial key is created at signup; paid production key is separate. |
| DGrid free route | `NO_CARD_REQUIRED` (reported) | Basic 100 RPD route is free; higher 1,000 RPD requires qualifying spend. Keep card status provisional if checkout requirements change. |
| APIBridge (MoBike) | `NO_CARD_REQUIRED` (provider/tracker claim) | SeaTalk identity verification is separately required/reported; this is not a card requirement. |
| 100milionseek | `NO_CARD_REQUIRED` (provider claim) | Email/human check/API key; young service, so recheck current onboarding. |

### Card required

| Provider | Card status | Notes |
|---|---|---|
| No confirmed Layer 2 recurring-quota provider in the currently reviewed evidence | — | Do not move one-time card-gated trials (for example Cerebras) into Layer 2 merely because a daily figure appears in a tracker. |

### Card requirement unknown or conflicting — do not assume no-card

| Provider / candidate | Card status | Notes |
|---|---|---|
| Free.ai | `UNKNOWN_NOT_PUBLISHED` | Account/key required; current developer docs reviewed here do not settle card requirement. |
| NaraRouter | `UNKNOWN_NOT_PUBLISHED` | Free plan is documented but may show out-of-stock; card requirement not established. |
| Kiosapi.id | `UNKNOWN_NOT_PUBLISHED` | Email/API key documented; card requirement not established. |
| Frenix | `UNKNOWN_NOT_PUBLISHED` | Telegram sign-in; no authoritative card statement captured. |
| PEKPIK LLM | `UNKNOWN_NOT_PUBLISHED` | Daily credit claim documented; card requirement not established. |
| iFlytek Spark Lite | `UNKNOWN_NOT_PUBLISHED` | APIPassword and possible real-name verification; card requirement not established. |
| Aiven AI Gateway | `UNKNOWN_NOT_PUBLISHED` | Organization enablement/early access; card requirement not established. |
| NVIDIA Build / NIM | `UNKNOWN_NOT_PUBLISHED` | Free prototyping access; no universal card statement captured for every endpoint/account. |
| Z.ai / GLM Flash | `UNKNOWN_NOT_PUBLISHED` | Zero-priced models listed; onboarding payment-card requirement not established. |
| SenseNova | `UNKNOWN_NOT_PUBLISHED` | Points-based free access reported; card requirement not established. |
| OpenTyphoon | `UNKNOWN_NOT_PUBLISHED` | Rate-limit page does not establish a daily free grant or card status. |
| SEA-LION | `UNKNOWN_NOT_PUBLISHED` | Free API key/trial access; card status not established in the reviewed source. |
| Hetzner Inference experimental API | `UNKNOWN_NOT_PUBLISHED` | Experimental availability; account/payment requirements need direct confirmation. |
| ModelScope API-Inference | `UNKNOWN_NOT_PUBLISHED` | Magicube/credit system; free recurring allowance and card status unresolved. |
| NFlashX, AMD Token Lab, Mango Inference, Regolo.ai, EXAONE, Baichuan, Baidu Qianfan, rout.my, BazaarLink, Flexlora, Mixlayer, Inferbase, FreeInference, InferAll, FreeTheAI, OrcaRouter, UnoRouter, GW BUS, EURI, WanAPIs, TokenFaucet, CrowLLM, LLM Gateway, Novita AI | `UNKNOWN_NOT_PUBLISHED` | Retained candidates; no reliable card requirement established in this research pass. |
| Tencent Cloud TokenHub | `CONFLICTED` | Reported activation/free balance may have a financial condition; verify official console before classifying as no-card. |
| FreeAIapikey, APInex, AIHubMix, Infron | `TOPUP_REQUIRED` / `CONFLICTED` | These are purchase/top-up gated, not clean no-payment recurring free tiers. A card or other payment method may be needed for the top-up; exact checkout methods vary. |

## Layer 3 — One-time trials and signup credits

### No card required (documented/reported for the trial)

| Provider | Card status | Notes |
|---|---|---|
| AI21 Labs / Jamba API | `NO_CARD_REQUIRED` | Current comparison says no card; expiry is conflicted (7 days vs 3 months). |
| Fireworks AI | `NO_CARD_REQUIRED` | $1 starter credit reported usable without payment method. |
| Upstage | `NO_CARD_REQUIRED` (tracker-reported) | $10 signup credit; official current terms still need confirmation. |
| Sarvam AI | `NO_CARD_REQUIRED` (account verification applies) | ₹100 wallet grant; identity/account verification is distinct from a card. |
| Perplexity API | `UNKNOWN_NOT_PUBLISHED` | Conditional $10 grant reported; card status not confirmed. |
| Inception Labs / Mercury | `UNKNOWN_NOT_PUBLISHED` | 100M token claim is tracker-only; card status not established. |
| Jina AI | `UNKNOWN_NOT_PUBLISHED` | 10M token claim is tracker-only; card status not established. |
| Hyperbolic | `UNKNOWN_NOT_PUBLISHED` | Phone verification reported; that is not evidence of a card requirement. |
| Camb.ai | `UNKNOWN_NOT_PUBLISHED` | Trial credit/API applicability and card terms unconfirmed. |
| MixRoute | `UNKNOWN_NOT_PUBLISHED` | $5 credit is tracker-only; card terms unconfirmed. |
| OpenAny | `UNKNOWN_NOT_PUBLISHED` | Conflicting $0.50/$1 credit claims; card terms unconfirmed. |
| ngrok AI Gateway | `UNKNOWN_NOT_PUBLISHED` | $1 credit claim is tracker-only; applicability and card terms unconfirmed. |
| NFlashX | `UNKNOWN_NOT_PUBLISHED` | Limited $1 promotion; card terms unconfirmed. |
| NovAI | `UNKNOWN_NOT_PUBLISHED` | $2 signup claim is tracker-only; card terms unconfirmed. |
| Nscale | `UNKNOWN_NOT_PUBLISHED` | $5 starter credit/early-user eligibility; confirm in console. |
| Anthropic API | `UNKNOWN_NOT_PUBLISHED` | Small account-specific credit claim is not confirmed; card requirement not established. |
| Tencent Cloud TokenHub | `UNKNOWN_NOT_PUBLISHED` | Regional promotion; card/payment setup requirements not resolved. |
| Volcano Engine Ark | `UNKNOWN_NOT_PUBLISHED` | Regional/model-specific free quota; card requirement not established. |

### Card required

| Provider | Card status | Notes |
|---|---|---|
| Cerebras Inference | `CARD_REQUIRED` | $5 one-time credit is reported to require adding a valid payment method and expires after 30 days. Not a recurring free tier. |
| NLP Cloud | `CARD_REQUIRED` | $15 pay-as-you-go trial credit is reported to require a card. Its separate limited free plan must not be conflated with this credit. |
| Alibaba Cloud Model Studio (Model Studio free quota) | `UNKNOWN_NOT_PUBLISHED` | Current product-specific documentation says the quota is automatically granted after account information is completed and does not state that a card is required. Older/general Alibaba free-trial policy may differ; do not apply it automatically to Model Studio. The current free quota is model/region-specific and valid for 90 days. |
| Nebius Token Factory | `UNKNOWN_NOT_PUBLISHED` | Do not mark card-required solely from conflicting third-party tracker entries; the program's current official onboarding needs confirmation. |

### Card status unknown / not confirmed

| Provider | Card status | Notes |
|---|---|---|
| Baseten | `UNKNOWN_NOT_PUBLISHED` | New-workspace evaluation credits; amount/expiry unpublished and payment method may affect continued deployment. |
| SiliconFlow | `UNKNOWN_NOT_PUBLISHED` | $1 claim varies by platform/region; international vs China console must be distinguished. |
| Replicate | `UNKNOWN_NOT_PUBLISHED` | Limited free runs reported; billing setup may be required after trial, but current card requirement was not established. |
| Baichuan AI | `NOT_APPLICABLE` | Historical 2024 credit only; not a current offer. |
| SambaNova Cloud | `CONFLICTED` | Free recurring tier vs historical signup credit reports conflict; do not assume trial credit or card status. |
| DeepSeek Platform | `NOT_APPLICABLE` | No current generally available signup credit verified. |
| Novita AI Agent Sandbox credit | `NOT_APPLICABLE_FOR_LLM_API` | Reported $100 credits apply to sandbox resources, not confirmed Model API inference. |
| AssemblyAI / Deepgram / Camb.ai speech offers | `UNKNOWN_NOT_PUBLISHED` | Non-LLM API credits; card requirements need separate official verification. |

### Quick count rule for the public-facing list

Show three clear buckets for each layer: **No card required**, **Card required**, and **Card requirement unknown**. Never merge “unknown” into “no card”. Add separate badges for phone/identity verification, region restrictions, top-up requirements, and paid-upgrade options. The status above describes the evidence captured on 23 November 2026; recheck provider onboarding before publication because payment requirements can change.

## Layer 3 — Additional providers discovered (research pass: 23 November 2026)

This subsection adds providers that were not adequately represented in the earlier Layer 3 inventory. It preserves the distinction between general LLM inference, embeddings/RAG, vision-language inference, speech APIs, and search APIs. A free credit for speech, embeddings, or search is not interchangeable with a general chat-completion credit.

### Officially documented offers

| Provider | Offer | API scope | Card status | Evidence / caveats |
|---|---:|---|---|---|
| Deepgram | $200 signup credit; official pricing says it does not expire | Speech-to-text, text-to-speech, voice-agent and audio-intelligence APIs; not a general text LLM | `NO_CARD_REQUIRED` | `OFFICIAL_TRIAL`. Official quickstart says free signup includes $200 and an API key; official pricing says no card and no expiry. Check regional eligibility at signup. |
| Mixedbread | $5 one-time starter credits | Embeddings, retrieval, reranking / search infrastructure; not general chat LLM inference | `NO_CARD_REQUIRED` | `OFFICIAL_TRIAL`. Official pricing explicitly says one-time $5 credits and no card. Starter has 100 queries/min and 6,000 uploads/min. |
| Speechmatics | $100 signup credits | Speech-to-text API / voice-agent transcription; not general text LLM inference | `NO_CARD_REQUIRED` | `OFFICIAL_TRIAL`. Official pricing says start with $100 and the free tier needs no card. Confirm credit expiry and country eligibility in portal. |
| Voyage AI | First 200M tokens free for selected embedding models; first 50M for selected legacy/specialized embedding models; multimodal embedding allowance also listed | Embeddings and multimodal embeddings, not chat-completion generation | `UNKNOWN_NOT_PUBLISHED` | `OFFICIAL_FREE_ALLOCATION`. Official pricing assigns an initial free-token allowance to every account. It is a one-time usage allowance rather than a recurring daily quota; the pricing page does not state card requirements or an expiry. |
| Sarvam AI | ₹100 free credits for each verified user; credits never expire | LLM, speech, translation and other Sarvam Model APIs | `UNKNOWN_NOT_PUBLISHED` | `OFFICIAL_TRIAL`. Official API pricing says ₹100 for every verified signup and usable across APIs. Verification is required; do not assume this means a payment card. |
| Exa | $10 onboarding bonus, in addition to $10 free credits every month | Search / agent research API, not a model-inference API | `NO_CARD_REQUIRED` | `OFFICIAL_MIXED_OFFER`. Official pricing says no payment method required. Put the $10 onboarding bonus in Layer 3; put the recurring $10/month allocation in Layer 2. Exa credits pay for Exa search/agent services, not arbitrary LLM tokens. |

### Promotional or tracker-reported candidates — keep unverified

| Provider | Reported offer | API scope | Card status | Evidence / caveats |
|---|---:|---|---|---|
| Fireworks AI — Muse Glimmer 30B SFT promotion | Selected model/API promotion advertised free through 30 November 2026 | Specific model and Serverless Training API promotion; not a general signup-credit balance | `NO_CARD_REQUIRED` (promotion listing) | `PROMO_REPORTED`; the current research source reports no card for the limited promotion. Do not treat the frequently repeated $1 starter-credit claim as confirmed unless the provider's current official signup/pricing page displays it. Promotion can end or change. |
| YepAPI | $5 one-time signup credit | Aggregated AI API access; exact model coverage needs checking | `UNKNOWN_NOT_PUBLISHED` | `TRACKER_ONLY`; reported as a one-time Google/GitHub signup grant. Keep outside the verified count until current official terms confirm credit amount, API scope, expiry, and card requirement. |
| SmarToken | $1 one-time credit for approved accounts | AI API credit; exact endpoint/model scope needs checking | `UNKNOWN_NOT_PUBLISHED` | `TRACKER_ONLY`; reported eligibility excludes accounts with prior top-ups or signup credits. Approval and current availability need confirmation. |
| Browser Use | $1 signup credit for eligible OAuth signups | Browser-use / agent execution API, not general LLM inference | `UNKNOWN_NOT_PUBLISHED` | `TRACKER_ONLY`; eligibility reportedly depends on Google, GitHub, or Microsoft sign-in. Confirm that credit applies to API calls and not only hosted agent/browser usage. |
| Helyx AI | $2 instant OAuth credit, with an additional $8 reportedly requiring support contact | AI gateway / model API; exact eligible models need checking | `NO_CARD_REQUIRED` (tracker-reported) | `TRACKER_ONLY`; current tracker says no card, but split-credit and support-contact terms should be confirmed before public recommendation. |
| Nscale | $5 starter credit for eligible/new accounts | Serverless inference / model API eligibility unclear | `UNKNOWN_NOT_PUBLISHED` | `TRACKER_ONLY`; eligibility and API applicability must be checked in the account console. |
| Inception Labs / Mercury | 100M free tokens claimed | Model inference | `UNKNOWN_NOT_PUBLISHED` | `TRACKER_ONLY`; no current official credit terms captured in this pass. Do not call it verified. |
| Jina AI | 10M free API tokens claimed | Embeddings / reranking / related APIs | `UNKNOWN_NOT_PUBLISHED` | `TRACKER_ONLY`; token amount and whether this is current for new accounts require official confirmation. |
| NFlashX | $1 promotional credit for first 100 accounts | AI API / free Flash model | `UNKNOWN_NOT_PUBLISHED` | `TRACKER_ONLY`; limited first-100 promotion, not a stable universal signup offer. |

### Layer 3 classification notes

- `NO_CARD_REQUIRED` means a current official provider page explicitly says no card/payment method is needed, or the offer's official onboarding clearly confirms it. A tracker claim alone remains `UNKNOWN_NOT_PUBLISHED` unless separately corroborated.
- Phone verification, email verification, OAuth, and identity verification are separate conditions from a credit card. Record them independently.
- A monthly recurring allocation with a one-time onboarding bonus belongs in both layers, but each component must be described separately (Exa is the example here).
- Free API credits for STT/TTS, embeddings, vision, search, and browser agents should be labeled by API category; do not present them as free general-purpose LLM tokens.
- The Deepgram, Mixedbread, Speechmatics, Voyage, Sarvam, and Exa entries above have official-page evidence. The remaining entries are intentionally retained as unverified candidates rather than silently promoted to verified status.


## Research expansion — additional verified offers (23 November 2026)

This pass adds only offers that have a provider-owned pricing, FAQ, or documentation page. It also records exclusions where a widely repeated claim does not match the official API terms.

### Layer 2 — recurring free quotas (additional verified providers)

| Provider | Recurring allowance | API scope / provider type | Card status | Evidence / caveats |
|---|---|---|---|---|
| Moondream Cloud | $5 usage credits added every month to each workspace | Hosted vision-language inference API; independent model provider, not a general text-chat API | `NO_CARD_REQUIRED` | `OFFICIAL_RECURRING`. Official pricing and Cloud pages state $5 monthly credits; official homepage explicitly says no credit card required. This is for hosted visual inference, not generic LLM chat tokens. Rate limits and credit carry-over are not established by the cited offer. |
| Vercel AI Gateway | $5 every 30 days for eligible free users who have not made a payment; credits begin with the first AI Gateway request | Multi-provider model gateway/aggregator; credit can be spent across supported upstream models | `UNKNOWN_NOT_PUBLISHED` / `CONFLICTED` | `OFFICIAL_RECURRING`. Vercel's pricing page says $5/month included and its announcement says $5 every 30 days; it also says making a first payment ends the free-credit eligibility. Vercel's own separate FAQ says a valid payment method is needed for some access paths, so do not claim universally no-card. No published per-account token amount because value depends on selected model prices. |

### Layer 3 — additional one-time trials / new-customer allocations

| Provider | One-time offer | API scope | Card status | Evidence / caveats |
|---|---:|---|---|---|
| Scaleway Generative APIs | 1,000,000 free tokens for new customers, plus 60 minutes of audio transcription for eligible audio models | Hosted text/code/vision inference and speech transcription; independent cloud inference service | `CARD_REQUIRED` for standard rate-limit access; KYC also reported by official page | `OFFICIAL_NEW_CUSTOMER_FREE_TIER`. Scaleway's official FAQ and pricing page document the free allowance and explain that usage beyond it is billed. The official page says a valid credit card and KYC are needed to benefit from official rate limits. Treat the million tokens as a new-customer allowance, not a monthly recurring quota. Check the console for regional/eligibility conditions and enable spending safeguards. |
| AssemblyAI | Up to $50 of free audio-processing usage on a free account | Speech-to-text and Speech Understanding APIs; not a general LLM inference API | `NO_CARD_REQUIRED` to start the free tier; card may be added later to upgrade | `OFFICIAL_TRIAL`. AssemblyAI's support article says a free-tier account can process up to $50 of audio and may add a card at any time to upgrade. The LLM Gateway is not included in the free tier. This is usage-based trial credit, not recurring. |

### Corrections and exclusions from this pass

- **Alibaba Cloud Model Studio:** The current product-specific free-quota page says account information must be completed, then the Singapore Model Studio service is activated and quota is automatically granted. It does not say that a payment card is required. The free quota is model-specific (typically 1M tokens per eligible model) and expires after 90 days. Therefore its card status is now `UNKNOWN_NOT_PUBLISHED`, not `CARD_REQUIRED`; do not infer the card rule from Alibaba's generic cloud free-trial policy. A separate OAuth-based allowance of 2,000 inference calls/day is mentioned in the product docs, but it is a distinct authentication path and should not be combined with the token quota without further eligibility verification.
- **Mistral API:** Do not list the free Studio/Vibe monthly budget as free API inference. Mistral's current official usage-limit documentation explicitly says Free mode does not include API access; API keys require billing activation and pay-as-you-go. The free monthly budget is for Studio/Vibe product usage, not an API allowance.
- **GitHub Models:** Remove from any active provider count. GitHub's official documentation says the service (playground, catalog, and inference API) was retired on 30 July 2026.
- **AgentRouter:** Its official $0 page describes free agent discovery/MCP tool calls and optional higher-rate API keys; it does not establish a free general-purpose LLM inference API or the $25 daily check-in credit claim. Keep the claimed credit out of verified LLM API counts unless the provider publishes an applicable model-inference offer.
- **Cerebras:** Current official pricing explicitly requires adding a valid payment method to receive the one-time $5 promotional credit; it expires 30 days after activation. Keep it in Layer 3 as `CARD_REQUIRED`, not as a permanent free tier.

### Source register for this research expansion

- Moondream: official pricing `https://moondream.ai/pricing`, cloud pricing `https://docs.moondream.ai/pricing/`, cloud product page `https://moondream.ai/cloud`.
- Vercel AI Gateway: official pricing `https://vercel.com/docs/ai-gateway/pricing`, official launch/FAQ `https://vercel.com/blog/ai-gateway-is-now-generally-available`.
- Scaleway: official FAQ `https://www.scaleway.com/en/docs/generative-apis/faq/`, pricing `https://www.scaleway.com/en/generative-apis/`, quickstart `https://www.scaleway.com/en/docs/generative-apis/quickstart/`.
- AssemblyAI: official support article `https://support.assemblyai.com/articles/5370767329-can-i-sign-up-for-free`.
- Alibaba Cloud Model Studio: official free quota docs `https://www.alibabacloud.com/help/en/model-studio/new-free-quota`, product pricing `https://docs.modelstudio.console.alibabacloud.com/en/model-studio/model-pricing`.
- Mistral: official usage-limit docs `https://docs.mistral.ai/admin/billing-usage/usage-limits`.
- GitHub Models retirement: official docs `https://docs.github.com/en/github-models`.
- AgentRouter: official pricing `https://www.agent-router.org/pricing`.
- Cerebras: official pricing `https://www.cerebras.ai/pricing`.

## Deep research expansion — broader provider audit (23 November 2026)

This is a broad audit pass, not a five-provider shortlist. It covers recurring hosted inference, aggregators, specialist APIs, and frequently repeated offers that fail the strict API test. Provider-owned documentation takes precedence over tracker summaries. No claim below means that a live API request was personally executed in this research pass unless explicitly stated.

### Layer 2 — recurring / renewable free API access: new and clarified findings

| Provider | Free access and renewal | API type | Card status | Research conclusion |
|---|---|---|---|---|
| SambaNova Cloud / SambaCloud | Free Tier is active when no payment method is linked. Official rate-limit documentation is model-specific; a current official-doc mirror and provider community clarification report 20 requests/minute, 20 requests/day and 200,000 tokens/day per model. | Independent hosted LLM inference; OpenAI-compatible chat completions at `https://api.sambanova.ai/v1`. | `NO_CARD_REQUIRED` for Free Tier, because linking a payment method moves the account out of the Free Tier. | `OFFICIAL_RECURRING`, but keep the per-model figures dated and check the model's live rate-limit table. This resolves the earlier “conflicted” label: the free tier and historical signup-credit rumours are separate things. Do not combine them. Official docs: `https://docs.sambanova.ai/docs/en/models/rate-limits`. Community clarification: `https://community.sambanova.ai/t/the-daily-limit-is-not-resetting-after-24-hours/1704/3`. |
| Ollama Cloud | Free plan includes light cloud-model usage. The official page says session limits reset every 5 hours and weekly limits every 7 days; Free has one concurrent cloud model. Exact token/request quota is not published as a fixed number and depends on model/compute. | Hosted cloud model API plus local Ollama runtime; not an aggregator. | `UNKNOWN_NOT_PUBLISHED` — official pricing page does not make a universal card statement for the cloud free plan. | `OFFICIAL_RECURRING`, quota `NOT_NUMERIC`. Keep local self-hosted unlimited usage separate from hosted cloud quota. Free cloud use is for light usage, smaller models, evaluation and assistants; Pro advertises 50x Free usage. Official pricing: `https://ollama.com/pricing`; docs: `https://docs.ollama.com/`. |
| Cohere (clarification) | Trial/evaluation key: 1,000 API calls/month; Chat API generally 20 requests/minute per model. | Independent model provider; chat, embeddings, reranking, transcription and related APIs. | `NO_CARD_REQUIRED` is commonly available for evaluation key signup, but the cited rate-limit page itself does not state the card rule; retain the existing card classification only where separately supported. | `OFFICIAL_EVALUATION_QUOTA`, not an unrestricted production free tier. Terms say evaluation keys are free/limited and production keys are paid; do not advertise for production or commercial use. Official rate limits: `https://docs.cohere.com/v1/docs/rate-limits`. |
| NVIDIA Build / hosted NIM endpoints (clarification) | A changing catalog of hosted “Free Endpoint” models exists; no universal per-account daily token grant or stable common RPM quota is published on the catalog page. | Model-hosting/API catalog. Some entries are NVIDIA-operated and others are partner endpoints; do not count each model as a separate provider. | `UNKNOWN_NOT_PUBLISHED` | `FREE_EVALUATION_ACCESS`, not a quantified recurring quota. The NIM software offering is free to use under its license, but that is distinct from hosted endpoint capacity. Hosted endpoint limits vary by model/account. Official catalog: `https://build.nvidia.com/models`; NIM offering terms: `https://docs.nvidia.com/nim/large-language-models/latest/about-nim-llm/nim-offerings.html`. |
| OpenRouter (clarification) | Free model IDs ending in `:free`: 20 requests/minute and 50 requests/day; tracker reports 1,000/day only after at least $10 lifetime credits purchased. | Aggregator/gateway, not an independent model provider. | `NO_CARD_REQUIRED` for the basic free-model tier; paid purchase is required for the higher daily cap. | Keep only 50 RPD in the clean no-purchase free allowance. The higher cap is `TOPUP_REQUIRED`, not a free recurring tier. Model availability is upstream-dependent and `:free` IDs can disappear. Official collection: `https://openrouter.ai/collections/free-models`. |
| Groq (clarification) | Free-plan limits are model-specific. Current official table lists GPT-OSS 120B/20B and Qwen 3.8 27B at 30 RPM, 1,000 RPD, 8K TPM and 200K TPD; other models have different limits. | Independent hosted inference provider. | `NO_CARD_REQUIRED` for the free developer plan, subject to account eligibility/verification. | `OFFICIAL_RECURRING`. Limits apply at organization level and the first exhausted dimension blocks requests. Official live table: `https://console.groq.com/docs/rate-limits`. |
| Gemini Developer API / AI Studio (clarification) | Free input/output tokens for selected models; RPM, TPM and RPD vary by model and project and are shown in AI Studio. | Independent model provider. | `NO_CARD_REQUIRED` for eligible Free Tier projects. | `OFFICIAL_RECURRING`. Important privacy caveat: Google states free-tier content may be used to improve products; do not send private or sensitive data under this tier. Official pricing: `https://ai.google.dev/gemini-api/docs/pricing`; rate limits: `https://ai.google.dev/gemini-api/docs/rate-limits`. |
| Cloudflare Workers AI (clarification) | 10,000 Neurons/day; reset at 00:00 UTC. Consumption is measured in Neurons, not tokens, and differs by model. | Hosted inference platform/edge compute; not an aggregator in the same sense as OpenRouter. | `NO_CARD_REQUIRED` for the basic daily allocation, but some models/features require paid Workers/billing. | `OFFICIAL_RECURRING`. Do not translate Neurons into a fixed token count. Official pricing: `https://developers.cloudflare.com/workers-ai/platform/pricing/`. |
| Z.ai / GLM Flash (clarification) | Selected Flash models are listed at zero price; the provider does not publish one universal daily quota in the reviewed pricing material. | Independent model provider. | `UNKNOWN_NOT_PUBLISHED` | Keep as a recurring free-model candidate with quota `NOT_PUBLISHED`; never invent a daily token allowance. Official pricing: `https://docs.z.ai/guides/overview/pricing`. |
| Moondream Cloud (scope clarification) | $5 credit every month per workspace. | Independent hosted vision-language API. | `NO_CARD_REQUIRED` according to official product/pricing information. | Monthly credit is a recurring allocation and belongs only in Layer 2. It is for image/vision tasks, not general chat-completion tokens. Official: `https://moondream.ai/pricing`; docs: `https://docs.moondream.ai/pricing/`. |
| Vercel AI Gateway (scope clarification) | $5 every 30 days for eligible free users; eligibility may end after making a payment. | Aggregator/gateway routing across upstream model providers. | `UNKNOWN_NOT_PUBLISHED` / `CONFLICTED` for universal no-card access. | Monthly credit belongs in Layer 2, not Layer 3. Do not present it as a model-provider token grant: it is a dollar credit consumed at model-specific gateway prices. Official: `https://vercel.com/docs/ai-gateway/pricing`. |

### Layer 3 — one-time trial credits / new-account allocations: verified or corrected

| Provider | One-time offer | API scope | Card status | Research conclusion |
|---|---|---|---|---|
| Cerebras Inference | $5 initial promotional credit; official pricing page confirms a free trial. Current detailed terms in the official pricing research state a valid payment method is required and the credit expires 30 days after activation. | General LLM inference, limited developer/evaluation tier. | `CARD_REQUIRED` | One-time credit, not a permanent free daily tier. The current official page confirms the $5 trial; retain the stricter card/expiry note and verify it in the signup flow before relying on access. Official: `https://www.cerebras.ai/pricing`. |
| Voyage AI | First 200M tokens on selected embedding models; 50M for selected specialized/older models; multimodal embedding allowance includes 200M text tokens and 150B pixels. | Embeddings, multimodal embeddings and reranking; not chat generation. | `UNKNOWN_NOT_PUBLISHED` | Per-account initial free allocation, not recurring. The official pricing page explicitly says “free for every account” for the listed models. Official: `https://docs.voyageai.com/docs/pricing`. |
| Exa | $10 onboarding bonus plus a separate $10/month recurring allowance. | Web search / agent research API; not LLM token inference. | `NO_CARD_REQUIRED` according to official pricing. | Split the $10 onboarding component into Layer 3 and keep the monthly $10 in Layer 2. Never describe Exa credits as free LLM tokens. Official: `https://exa.ai/pricing` and `https://docs.exa.ai/reference/pricing`. |
| Scaleway Generative APIs | New-customer allocation reported as 1,000,000 tokens plus 60 minutes of eligible audio transcription. | Hosted LLM/code/vision inference and speech transcription. | `CARD_REQUIRED` for standard rate-limit access; KYC may also apply. | New-customer allowance, not a monthly recurring quota. Verify country eligibility and the current console terms. Official FAQ: `https://www.scaleway.com/en/docs/generative-apis/faq/`; pricing: `https://www.scaleway.com/en/generative-apis/`. |
| AssemblyAI | Up to $50 of audio-processing usage on a free account. | Speech-to-text and Speech Understanding; not general LLM chat inference. | `NO_CARD_REQUIRED` to start free tier; card may be added later to upgrade. | Trial usage allowance. The LLM Gateway is not included in the free tier; do not claim the $50 covers every AssemblyAI product. Official: `https://support.assemblyai.com/articles/5370767329-can-i-sign-up-for-free`. |
| Deepgram | $200 signup credit; official pricing says it does not expire. | Speech-to-text, text-to-speech, voice-agent and audio intelligence. | `NO_CARD_REQUIRED` | One-time speech API credit; not general LLM inference. Official pricing: `https://deepgram.com/pricing`; quickstart: `https://developers.deepgram.com/docs/quickstart`. |
| Mixedbread | $5 one-time starter credit. | Embeddings, retrieval and reranking. | `NO_CARD_REQUIRED` | Specialist search/RAG API, not chat-completion inference. Official pricing: `https://www.mixedbread.com/pricing`. |
| Speechmatics | $100 signup credits. | Speech-to-text / transcription. | `NO_CARD_REQUIRED` | Specialist speech API trial; expiry not stated in the reviewed pricing source. Official: `https://www.speechmatics.com/pricing`. |
| Sarvam AI | ₹100 credit for each verified user; credits do not expire. | LLM, speech, translation and other model APIs. | `UNKNOWN_NOT_PUBLISHED`; account verification required. | Separate account/identity verification from card requirements. Official: `https://docs.sarvam.ai/api-reference-docs/getting-started/pricing`. |

### Exclusions and disputed claims: do not count as active free API offers

| Provider / claim | Result of official-source check | Correct handling |
|---|---|---|
| Mistral AI / La Plateforme “free API” | Current official usage-limit page says Free mode includes monthly usage for Vibe/Studio but does not include API access; API keys and API usage require billing activation and pay-as-you-go. | Exclude from free API providers. Do not mistake free Vibe/Studio usage for API inference. Official: `https://docs.mistral.ai/admin/billing-usage/usage-limits`. |
| Hugging Face Inference Providers free monthly credits | Current free-account pricing reports no included monthly inference credit; paid PRO includes a small monthly credit. | Exclude from free-account recurring API quotas unless a new official free grant appears. Official pricing: `https://huggingface.co/docs/inference-providers/pricing`. |
| Together AI | Current pricing research does not establish a general free API quota or signup credit; prepaid balance is required for ordinary hosted API usage. | Do not list as free. A free playground/model demo is not proof of API access. Official pricing/docs: `https://www.together.ai/pricing` and `https://docs.together.ai/`. |
| DeepInfra | Current pricing research does not establish a general free API allowance. | Exclude from active free API list; do not confuse downloadable open weights or third-party hosted copies with DeepInfra's own free API. Official: `https://deepinfra.com/pricing`. |
| Fireworks AI — generic $1 signup credit | Current official pricing research does not confirm a universal $1 new-account API credit; model-specific promotions may appear and disappear. | Keep generic $1 claim unverified. List only a named, dated, provider-confirmed model promotion if its terms are still live. Official: `https://fireworks.ai/pricing`. |
| xAI API / Grok | Free web chat/playground does not establish a free API quota; ordinary API usage is paid. | Exclude from free API tier unless the provider publishes a separate API promotion. Official: `https://x.ai/api`. |
| GitHub Models | Retired on 30 July 2026; no active API service. | Remove from active provider counts and retain only in the expired-offers ledger. Official docs: `https://docs.github.com/en/github-models`. |
| Mistral free model hosts / community gateways | A third-party host offering a Mistral model for free is not a free Mistral API tier. | Attribute the offer to the actual host/gateway, not to Mistral. |
| NVIDIA downloadable NIM containers | NIM software can be free to use under its license, but running a container requires compatible hardware and compute. | Do not count downloadable software as a free hosted API endpoint. Keep hosted Build endpoints separately with unknown/variable quotas. |
| Ollama local runtime | Running models locally on user-owned hardware is not a hosted free API quota. | Keep local/self-hosted inference in its own category; only Ollama Cloud's limited hosted Free plan belongs in Layer 2. |

### Candidate discovery sweep — not yet promoted to verified provider entries

The following names surfaced in current directories and comparison trackers. They need their own official pricing/API documentation check and, where possible, a successful unauthenticated or authenticated generation test before they can be counted as confirmed: Teapot Router, Qora API, Flonno, HPC-AI Model APIs, Baichuan AI, Baidu Qianfan, AMD Token Lab, 100milionseek, IteraCompute, NFlashX, Mango Inference, Regolo.ai, FreeInference (Harvard MadSys Lab), InferAll, Inferbase, BazaarLink, Flexlora, Mixlayer, UnoRouter, OrcaRouter, EURI, TokenFaucet, WanAPIs, CrowLLM, LLM Gateway, FreeTheAI, and rout.my.

A tracker listing is discovery evidence only. For each candidate, record: legal provider name; official API base URL; exact model ID; authentication requirement; whether a real generation request succeeds; recurring quota and reset window; RPM/TPM/RPD separately; card requirement; identity/phone requirements separately; geography restrictions; data-retention/training terms; and date last verified. Do not count a directory as a provider or count every model from one gateway as a separate provider.

### Research methodology and confidence labels

- `OFFICIAL_RECURRING`: provider documentation explicitly describes a renewable free allowance or no-cost model access.
- `OFFICIAL_EVALUATION_QUOTA`: official trial/evaluation key with a finite recurring request cap; production restrictions must be stated.
- `OFFICIAL_TRIAL`: one-time signup credit or initial free allocation.
- `FREE_EVALUATION_ACCESS`: free endpoint exists but no universal numeric allowance is published.
- `TRACKER_ONLY`: third-party tracker claim; not confirmed by provider-owned terms.
- `EXCLUDED`: official evidence contradicts the claim or the offer is not API inference.
- A rate limit (RPM/TPM) is not a daily/monthly free quota. A model priced at $0 is not automatically available without signup or a key. A free playground is not an API. A no-card claim must be supported separately from phone/identity verification.

### Sources used in this expansion

- Current dated comparison / discovery: `https://llmlatency.dev/free-llm-api`, `https://freellmapi.link/`, `https://freeinference.dev/`, `https://freellm.today/`, `https://plugsky.com/free-llm-api`, `https://www.requesty.ai/blog/free-llm-apis`.
- SambaNova: `https://docs.sambanova.ai/docs/en/models/rate-limits`; `https://community.sambanova.ai/t/the-daily-limit-is-not-resetting-after-24-hours/1704/3`.
- Ollama: `https://ollama.com/pricing`; `https://docs.ollama.com/`.
- Cohere: `https://docs.cohere.com/v1/docs/rate-limits`.
- NVIDIA: `https://build.nvidia.com/models`; `https://docs.nvidia.com/nim/large-language-models/latest/about-nim-llm/nim-offerings.html`.
- OpenRouter: `https://openrouter.ai/collections/free-models`.
- Groq: `https://console.groq.com/docs/rate-limits`.
- Gemini: `https://ai.google.dev/gemini-api/docs/pricing`; `https://ai.google.dev/gemini-api/docs/rate-limits`.
- Cloudflare: `https://developers.cloudflare.com/workers-ai/platform/pricing/`.
- Z.ai: `https://docs.z.ai/guides/overview/pricing`.
- Moondream: `https://moondream.ai/pricing`; `https://docs.moondream.ai/pricing/`.
- Vercel: `https://vercel.com/docs/ai-gateway/pricing`.
- Cerebras: `https://www.cerebras.ai/pricing`.
- Voyage: `https://docs.voyageai.com/docs/pricing`.
- Exa: `https://exa.ai/pricing`; `https://docs.exa.ai/reference/pricing`.
- Scaleway: `https://www.scaleway.com/en/docs/generative-apis/faq/`; `https://www.scaleway.com/en/generative-apis/`.
- AssemblyAI: `https://support.assemblyai.com/articles/5370767329-can-i-sign-up-for-free`.
- Deepgram: `https://deepgram.com/pricing`; `https://developers.deepgram.com/docs/quickstart`.
- Mixedbread: `https://www.mixedbread.com/pricing`.
- Speechmatics: `https://www.speechmatics.com/pricing`.
- Sarvam: `https://docs.sarvam.ai/api-reference-docs/getting-started/pricing`.
- Mistral: `https://docs.mistral.ai/admin/billing-usage/usage-limits`.
- Hugging Face: `https://huggingface.co/docs/inference-providers/pricing`.
- Together AI: `https://www.together.ai/pricing`; `https://docs.together.ai/`.
- DeepInfra: `https://deepinfra.com/pricing`.
- Fireworks: `https://fireworks.ai/pricing`.
- xAI: `https://x.ai/api`.
- GitHub Models retirement: `https://docs.github.com/en/github-models`.

## Regional research addendum — MENA / North Africa providers (23 November 2026)

Scope: this pass deliberately excludes global/international-only providers and focuses on services built for, headquartered in, or explicitly offering local/regional infrastructure and billing in the Middle East and North Africa. Regional availability does not automatically mean the service is accessible from Libya; signup eligibility, phone verification, payment rails, and service geography must be checked separately.

### Regional API providers with a published free offer

| Provider | Base / region | Free offer | Classification | Card / payment status | Important caveats |
|---|---|---|---|---|---|
| Bunyan Inference Hub | Saudi Arabia; Riyadh live, UAE/Jordan/Iraq locations shown as coming soon | 14-day trial with $30 credit for tokens and APIs including OCR/document intelligence | Regional inference platform; one-time trial → Layer 3 | Card requirement not stated on public pricing page (`UNKNOWN_NOT_PUBLISHED`) | Official page describes sovereign inference hosted in Saudi Arabia and an OpenAI-compatible API. The $30 is a finite trial credit, not a recurring free quota. Confirm whether signup is open to individuals and whether accounts from Libya are accepted. |
| XToken by Vaenex | Dubai, UAE; built for UAE/Saudi/GCC | $5 signup credit plus 1,000 free API calls | Regional multi-model API gateway / aggregator; one-time trial → Layer 3 | Official page says no credit card required (`NO_CARD_REQUIRED`) | OpenAI-compatible endpoint `https://www.vaenex.com/v1`; routes to 200+ upstream models. This is gateway credit and call allowance, not 200 independent providers or recurring free inference. Verify whether 1,000 calls are included in addition to or consumed alongside the $5 balance. |
| Sigmix Inference | Riyadh, Saudi Arabia; separate Saudi-only sovereign route and international route | $2.00 free credit, valid 30 days for new accounts | Regional inference gateway; one-time trial → Layer 3 | Official page says no card (`NO_CARD_REQUIRED`) | Sovereign base URL: `https://inference.sigmix.sa/ksa-sovereign-route-only/v1`. The international route is separate and should not be counted as local inference. Credit expires after 30 days; not recurring. Public page lists chat and speech/transcription model availability on the sovereign route. |
| SovereignEG | Egypt; regional MENA inference API, standard route currently uses upstream providers; Egypt-hosted deployment is separately identified per model | Earlier site material advertised a 20 EGP welcome credit, but the current Terms (effective 16 Oct 2026) say there is no general free plan or free token allowance; only a Student-plan daily allowance (where offered) and allowances bundled with paid Developer Packs are exceptions | Regional API gateway; `CONFLICTED / NOT A GENERAL FREE TIER` | Account and mobile verification; EGP prepaid billing. Card status depends on local top-up method. | Do not count the old 20 EGP signup credit as currently available until the dashboard confirms it. Current pricing/docs describe prepaid EGP balance and per-model billing. OpenAI-compatible base URL and partial API compatibility; only models explicitly marked Hosted in Egypt are processed on its Egyptian GPUs. |

### Regional infrastructure providers — no qualifying free inference quota confirmed

| Provider | Region / service | Free status | Classification | Why not counted as a free API provider |
|---|---|---|---|---|
| Bonya | Saudi Arabia and Egypt; sandboxes, jobs, Actions runners, GPU compute; inference is marked Beta | No specific free inference credit or recurring free token quota published in the reviewed public page | Regional AI cloud / compute platform | “Free to start” is not evidence of free hosted model inference. Public description says billed by the second; do not count as a free LLM API until a zero-cost inference allowance is documented. |

### Regional leads not yet verified enough to list as active free APIs

- Saudi/UAE/Jordan/Iraq sovereign-cloud announcements and national AI platforms: infrastructure announcements, model launches, and enterprise contact forms do not establish a public self-serve inference API or a free quota.
- Arabic-language model availability is not itself proof of a regional provider; a global provider serving Arabic models remains in the global list, not this regional addendum.
- No qualifying Libya-based public hosted LLM API with a documented free developer quota was found in this pass.

### Regional research sources

- Bunyan official site and pricing: https://bunyan.ai/ — states Saudi/Riyadh live infrastructure, 14-day free trial, and $30 credit.
- Vaenex / XToken official site: https://www.vaenex.com/ — states Dubai-based operator, $5 credit, 1,000 API calls, no card, and OpenAI-compatible endpoint.
- Sigmix official inference page: https://sigmix.ai/inference — states Riyadh gateway, $2 free credit, 30-day validity, no card, and distinct sovereign/international routes.
- SovereignEG official site: https://dev.sovereigneg.com/ — states 20 EGP welcome credit, email/mobile verification, EGP prepaid billing, and OpenAI-compatible API; docs: https://dev.sovereigneg.com/docs.
- Bonya official site: https://bonya.ai/ — states Saudi/Egypt infrastructure and per-second billing; no specific free inference allocation found.

Research note: these are regional candidates and offers documented by their own public pages as of 23 November 2026. No account creation, payment, or live inference call was performed in this research pass. Availability from Libya remains unconfirmed; do not assume that “Middle East” coverage guarantees Libyan signup or payment support.

## Expanded discovery pass — international and non-directory research (23 November 2026)

This pass deliberately broadens discovery beyond searching for the exact phrase “free LLM API”. It checks provider documentation, regional cloud/model platforms, developer reward programs, research grants, model-hosting catalogs, API status/latency monitors, CORS/browser tests, and specialist APIs. International providers remain in scope; regional offers are included when their geographic, identity, and billing restrictions are explicit. This section adds leads and verified terms without replacing earlier entries.

### Newly confirmed or materially clarified provider offers

| Provider / program | Layer | Offer and scope | Geography / eligibility | Card / identity | Classification and caveats | Official evidence |
|---|---|---|---|---|---|---|
| Alibaba Cloud Model Studio (DashScope / Bailian) | Layer 3 | New-user free inference quota, commonly 1,000,000 tokens **per eligible model**, including selected Qwen text, coder, vision, translation, embedding and multimodal models. | The cited free-quota page says the quota is only for China (Beijing) region; do not apply this quota to Singapore or other international endpoints. | Identity verification is explicitly required before activation. Card requirement is not stated by the cited page: `UNKNOWN_NOT_PUBLISHED`. | `OFFICIAL_TRIAL`, not recurring. Valid 90 days from activation/model release/approval (whichever later); unused balance expires. Quota applies to real-time inference only, not batch/fine-tuning/deployment/storage. Free quota is model-specific and does not roll over. Enable “Free Quota Only” to avoid automatic paid usage after quota depletion. | https://help.aliyun.com/en/model-studio/new-free-quota ; https://help.aliyun.com/en/model-studio/model-pricing |
| Alibaba Cloud Model Studio — Qwen-MT-Uni | Layer 3 | 1,000,000-token free allowance for multimodal translation (text, documents, images and audio). | China (Beijing) service region; verify the console's region and account eligibility. | Identity verification required at Model Studio activation; card unknown. | `OFFICIAL_TRIAL`. 90-day validity; this is a translation API, not general chat inference. The model page also publishes 162 RPM and 2,592,000 TPM; those are rate limits, not extra free credits. | https://help.aliyun.com/en/model-studio/qwen-mt-uni |
| Alibaba Cloud Model Studio — embeddings | Layer 3 | Selected Qwen text embedding and multimodal embedding endpoints each have a 1,000,000-token free allowance. | Model/region-specific; some quotas are Beijing-only. | Card unknown; account identity verification required. | `OFFICIAL_TRIAL`. Do not count each model as a separate provider. Embeddings are not chat completion. The 90-day clock and eligible model list should be checked in the console. | https://help.aliyun.com/en/model-studio/text-embedding-synchronous-api ; https://help.aliyun.com/en/model-studio/multimodal-embedding-api-reference |
| Volcengine Ark (火山方舟) | Layer 3 | New accounts receive free inference calls/credits, with per-model allocations. The “safe experience” mode documents a 500,000-token free boundary for eligible new users. | China-oriented Volcengine Ark service; account and model availability depend on region and activation. | Account registration required. Identity verification is needed to activate paid service after the free quota is exhausted; the docs do not establish a universal card requirement: `UNKNOWN_NOT_PUBLISHED`. | `OFFICIAL_TRIAL`. Per-model quota is not one global pool; each model has its own free allowance. The safe mode pauses service near the free boundary to prevent paid overage. Quota amount varies by model and must be read in the Ark console. Do not describe it as recurring. | https://docs.volcengine.com/docs/ark/free-inference-quota?lang=en ; https://docs.volcengine.com/docs/ark/activation-management?lang=en |
| AMD AI Developer Program / AMD Developer Cloud / Token Lab | Layer 3 (program) | Program advertises complimentary cloud credits, premium training, developer resources, and API access through Token Lab; some rewards are unlocked through program activities/points. | International developer program, subject to account and program availability. | Card requirement and exact credit amount/expiry not stated on the program page: `UNKNOWN_NOT_PUBLISHED`. | `PROGRAM_LEAD`, not a guaranteed recurring free inference quota. Distinguish AMD Developer Cloud compute credits from API credits and from instant Token Lab access; only count an API credit after the account dashboard confirms it can be spent on model inference. | https://developer.amd.com/ai-developer-program/ |
| OpenAI Researcher Access Program | Layer 3 (research grant) | Eligible research projects may apply for up to $1,000 in API credits; credits valid for 12 months. | Active affiliation with an academic institution/research organization, or nonprofit conducting research; applicant must be in a country supported by the API. This is not a general signup offer. | Application required; payment-card condition not specified in the FAQ. | `RESEARCH_GRANT`, not a public free tier. The stated purpose is research on responsible AI deployment, risk mitigation, and societal impacts. Do not list as an automatic credit or imply all individual developers qualify. | https://help.openai.com/en/articles/10139500-researcher-access-program-faq ; https://openai.com/form/researcher-access-program/ |

### Regional and model-platform leads found through alternate discovery methods

| Provider / platform | Potential offer | Current status | Why it is not promoted as a confirmed general free API yet | Follow-up evidence |
|---|---|---|---|---|
| AMD Radeon Cloud China public model APIs | Directory reports recurring free OpenAI-compatible model endpoints including DeepSeek, Qwen, GLM, MiMo and specialist models. | `REGIONAL_CANDIDATE` | A third-party monitor describes a China developer portal; this pass did not capture a corresponding AMD official quota/eligibility page for the reported public endpoint roster. Keep separate from AMD's official Developer Program credits. | https://aiaiai.help/en/free |
| SiliconFlow China (`api.siliconflow.cn`) | Older reports describe permanently free small models in the China platform. | `REGIONAL_CANDIDATE` | Free-model availability and identity requirements vary; no current official model-by-model zero-price quota was verified in this pass. International SiliconFlow signup credits must not be confused with the China offer. | https://docs.siliconflow.cn/ |
| ModelScope API-Inference | Magicube-based model inference and possible daily-login rewards. | `UNRESOLVED_CANDIDATE` | No current official source in this pass established a stable daily API quota usable for arbitrary inference. Playground/notebook access is not equivalent to a public API. | https://modelscope.cn/ |
| Baidu Qianfan / Wenxin Workshop | Regional model APIs and developer promotions. | `UNRESOLVED_CANDIDATE` | Search surfaced no sufficiently clear current official free inference quota applicable to ordinary new API accounts. Do not reuse old promotional figures without current documentation. | https://cloud.baidu.com/product/wenxinworkshop |
| StepFun | Regional model API and model catalog. | `UNRESOLVED_CANDIDATE` | A current, durable free API quota was not established from an official pricing/rate-limit source in this pass. A free chat site or model download does not count. | https://platform.stepfun.com/ |

### New discovery channels and how to use them

1. **Provider documentation first:** search exact pricing, quota, rate-limit, activation, billing and data-retention pages. This is the evidence source for the final entry; directories only reveal candidates.
2. **Developer-program and rewards search:** inspect AMD, accelerator, cloud, model-lab, university, research and startup programs. Record whether the reward is API inference, GPU compute, storage, training, or a discount; these are not interchangeable.
3. **Regional cloud catalogs:** inspect China, India, Korea, Japan, Southeast Asia, Turkey, MENA, Latin America and Africa developer portals. Record the actual service region and identity verification conditions; hosting location alone does not imply eligibility.
4. **Model-catalog price filters:** search for models whose input and output prices are both zero, then verify that the endpoint is callable by API and not just a playground. Check whether the free model is a provider-hosted model or a third-party gateway listing.
5. **API status and real-request datasets:** use endpoint monitors and reproducible request logs to identify newly live providers. A 401/403/429 response can establish that a host responds, but not that generation is free or anonymous. Require a successful completion request for `GENERATION_OK`.
6. **Browser/CORS testing:** check whether an API can be called from a browser, but treat CORS as a technical property only. It does not establish free quota, no-key access, or safe key handling. Never expose a private API key in a public frontend.
7. **Specialist API search:** search separately for embeddings, rerankers, OCR, speech-to-text, text-to-speech, translation, image generation, video, search and vision. Keep each in its own scope so a $50 transcription credit is never misrepresented as $50 of LLM tokens.
8. **Historical change tracking:** preserve ended promotions and retired endpoints in an expired ledger with end dates; do not silently remove them or present old blog posts as current offers.

### Research sources used for candidate discovery (not proof of provider terms)

- Free LLM API tested list: https://github.com/aditya1271/free-llm-list
- Awesome Free LLM APIs: https://github.com/devanasolver/awesome-free-llm-apis
- Free AI credits / student / startup programs: https://github.com/aifree-dev/awesome-free-ai-credits
- FreeInference directory (50 providers / 367 models, snapshot dated 22 Nov 2026): https://www.freeinference.dev/
- APIFreeLLM catalog (86 models, 9 providers, snapshot dated 22 Nov 2026): https://apifreellm.com/
- Free LLM API token tracker (141 entries, snapshot dated 20 Nov 2026): https://freellmapi.link/
- LLM latency and availability measurements: https://llmlatency.dev/free-llm-api
- Browser CORS and real-request test methodology: https://cors.dev/guides/free-ai-api
- Regional recurring-access monitor: https://aiaiai.help/en/free

**Important evidence rule:** counts shown by directories (for example, 50 providers or 141 APIs) are not counts of verified free providers. A catalog can contain IDE subscriptions, playgrounds, self-hosting projects, aggregators, trials, expired offers and paid endpoints. Only provider-owned pricing/docs plus a valid API route can move a candidate into a confirmed layer.


## MENA follow-up verification — changed terms and regional eligibility (23 November 2026)

This update prioritizes regional providers and corrects stale or ambiguous claims in the preceding regional table. A regional API gateway is not automatically a free provider: only the exact published allowance belongs in a free layer.

### Confirmed regional offers and corrections

| Provider | Layer / offer | Current evidence and status | Important details |
|---|---|---|---|
| Bunyan Inference Hub (Saudi Arabia) | Layer 3 — 14-day trial, $30 credit | Official site currently advertises 14 days free and $30 credit usable for tokens and APIs including OCR. | Riyadh is the live location; UAE (Abu Dhabi/Dubai), Jordan (Amman) and Iraq (Baghdad) are shown as coming soon, not live. OpenAI-compatible inference. Card requirement, Libyan signup eligibility and trial auto-conversion are not published; verify in the account terms before relying on it. Not recurring. |
| XToken by Vaenex (UAE / GCC) | Layer 3 — $5 signup credit + 1,000 free API calls | Official Vaenex site currently states both the $5 credit and 1,000 free calls on signup, with no credit card required. | Regional multi-model gateway, not an independent model provider. One OpenAI-compatible key routes to 200+ upstream models. The public page does not clearly explain whether the 1,000 calls are additive to the $5 balance or subject to the same balance; treat the call count as a separate advertised signup benefit but flag its accounting as unclarified. Credit is one-time, not recurring. |
| Sigmix Inference (Saudi Arabia) | Layer 3 — $2.00 signup credit, 30 days | Current official pricing page says each new account receives $2.00 for models marked “Free trial”, valid 30 days. | Prepaid gateway; the Sovereign route is Saudi-only and the international route is distinct. Streaming requires a minimum available balance of $20 (a balance requirement, not a fee). Do not confuse the $2 trial with a free recurring plan. Card/identity requirements not stated on the cited pricing page. |
| SovereignEG (Egypt) | Not confirmed as a general free tier | **Correction:** an earlier page/FAQ advertised a 20 EGP welcome credit, but current Terms of Service (effective 16 October 2026) explicitly state there is no general free plan or free token allowance. Exceptions: a daily allowance on the Student plan where offered, and daily allowances bundled with paid Developer Packs. | Keep the old welcome-credit claim as historical/conflicted, not a currently confirmed Layer 3 offer. Current model usage is prepaid EGP and billed by model. Mobile verification is required. The platform offers chat, embeddings, image generation and model listing; it does not offer every OpenAI API (for example Responses, Assistants, Audio, Files, Batch and fine-tuning). Standard route may use upstream providers; only models explicitly marked “Hosted in Egypt” are in-country. |
| Bonya (Saudi Arabia and Egypt) | No free inference quota confirmed | Official platform says “Free to start”, but its Inference product is beta, requires early access, and bills GPU replicas per second (published A10/A100/H100 hourly rates). | Regional compute / inference deployment platform, not a free hosted inference API. Do not list “Free to start” as free tokens or free API calls. |

### Libya and MENA access caveat

Regional branding does not establish that a provider accepts Libyan residents, Libyan phone numbers, or Libyan payment methods. None of the four regional trial pages above explicitly confirms Libya eligibility. Before marking any as “available in Libya”, require a provider-owned supported-country list or a successful ordinary signup/API test that does not bypass regional or identity controls.

OpenAI's official API supported-country page is also a useful regional eligibility check for upstream services. The current published list should be checked directly; do not infer support from Arabic-language availability or from a regional gateway's marketing. A gateway may have its own supported-country rules independent of its upstream vendors.

### Official sources for this update

- Bunyan: https://bunyan.ai/ — 14-day / $30 trial, Riyadh live and planned MENA locations.
- Vaenex XToken: https://www.vaenex.com/ — $5 credit, 1,000 free calls, no card; gateway model catalog: https://www.vaenex.com/models.html.
- Sigmix pricing: https://sigmix.ai/inference/pricing — $2 credit, 30-day validity, route-specific pricing and streaming balance requirement.
- SovereignEG current pricing: https://dev.sovereigneg.com/pricing ; current Terms: https://dev.sovereigneg.com/legal/terms ; API docs: https://dev.sovereigneg.com/docs.
- Bonya inference beta and pricing: https://bonya.ai/products/inference/ ; platform: https://bonya.ai/.
- OpenAI API supported countries: https://developers.openai.com/api/docs/supported-countries.

**Verification boundary:** this was a public-documentation review on 23 November 2026. No accounts were created, no identity or payment checks were attempted, and no inference requests were sent. Therefore, card status or Libyan eligibility remains unknown wherever the official page does not say otherwise.

## Additional global verification pass — API status changes and new candidates (23 November 2026)

This section records newly checked changes from current trackers and cross-checks. It intentionally separates official provider claims from directory reports. A provider can appear in a tracker without having a current free allowance; an offer is not promoted solely because a third-party list labels it “free”.

### Corrections and status changes

| Provider / service | Layer / status | Current finding | Classification and caveat | Evidence |
|---|---|---|---|---|
| Maritaca AI (Brazil) — S5-free | **Ended / do not count as active free API** | A November 20 tracker update reports that S5-free is no longer listed on Maritaca's official pricing page and that S5 API models are billed per token. | Earlier November claims that S5-free tokens were temporarily unbilled are stale. Preserve as an ended/withdrawn offer, not Layer 2. The exact end date and any account-specific exceptions are not established here. | Tracker change log: https://freellmapi.link/new ; provider pricing/docs should be checked before any future reinstatement. |
| Bonya Inference (Saudi Arabia / Egypt) | **Not a free API** | Official product page describes beta model deployment with API endpoints, but charges per running GPU replica: A10 $1.13/hour, A100 $2.34/hour, H100 $3.97/hour. Early access is enabled per organization. | Compute/deployment platform, not a free hosted-model quota. “Free to start” or a console chat does not establish free API inference. No published free token/call allocation found. | Official: https://bonya.ai/products/inference/ |
| Inception Labs / Mercury | Layer 3 — time-limited offer, expiry warning | Current tracker reports that the API remains available through **28 December 2026** and will not be served after that date. | Do not describe the 100M-token promotion as permanent or recurring. Keep under trial/promotion with a firm service sunset warning; verify provider terms and remaining balance before use. | Tracker change log: https://freellmapi.link/new ; discovery listing: https://freeai.alexai.top/ |
| OpenRouter `:free` models | Layer 2 — recurring request cap | Official collection page confirms free model variants ending in `:free` are $0, require an API key, and are limited to 20 requests/minute and 50/day. The daily cap rises to 1,000 only after buying at least $10 in credits. | Gateway/aggregator, not an independent model provider. Do not classify the 1,000/day post-purchase limit as a no-purchase free tier. Other zero-priced model entries may have different conditions. | Official: https://openrouter.ai/collections/free-models |
| Gemini Developer API | Layer 2 — selected free models, model-specific | Official pricing page confirms free input/output tokens for selected models on the Free tier, while premium models such as Gemini 4 Argon are explicitly excluded. | Do not imply every Gemini model is free. Free-tier prompts may be used to improve Google products; the pricing page distinguishes this from paid-tier data handling. Check the exact model row and AI Studio project limits before use. | Official: https://ai.google.dev/gemini-api/docs/pricing |

### Newly surfaced candidates — not yet promoted to confirmed free tiers

| Candidate | Discovery signal | Status | What must be verified before promotion | Discovery source |
|---|---|---|---|---|
| SambaNova / SambaCloud | November 2026 third-party reports describe a free, rate-limited API tier with daily token limits and no payment method linked. | `CANDIDATE_NEEDS_OFFICIAL_RECHECK` | Current SambaNova official pricing and rate-limit pages; exact models and daily limits; whether the no-payment condition is still current; account-country eligibility; whether limits reset daily. Do not reuse older limits without current official confirmation. | https://perq.sh/blog/free-llm-api-tiers-november-update |
| Flonno | Added to a November 18 tracker snapshot as a new API listing. | `UNVERIFIED_CANDIDATE` | Official API endpoint, current zero-price model IDs, whether a recurring quota exists, and card/phone requirements. A tracker entry alone is insufficient. | https://freellmapi.link/new |
| HPC-AI Model APIs | Added to a November 18 tracker snapshot. | `UNVERIFIED_CANDIDATE` | Official hosted inference pricing, quota amount/reset, model availability, account requirements, and whether access is public self-serve rather than a gated compute product. | https://freellmapi.link/new |
| Teapot Router | Added to a November 17 tracker snapshot. | `UNVERIFIED_CANDIDATE` | Official gateway documentation, free-model route, request/token quota, upstream provider identity, and whether the offer is recurring or a trial. | https://freellmapi.link/new |
| Ant Ling / Ling-3.2-Flash | Tracker changelog says the launch free window ran for two weeks from 5 November 2026; the 19 November official pricing update lists paid rates and does not publish a remaining free quota. | `PROMOTION_ENDED_OR_UNCONFIRMED` | Do not list as active free access unless a current official quota is published. Preserve the launch promotion as historical. | https://freellmapi.link/new |

### Research quality notes

- The current LLM latency tracker snapshot dated 23 November reports 42 APIs checked, with only seven free tiers/models it classifies as having no end date; it is a useful measurement and discovery source, not a substitute for each vendor's own terms: https://llmlatency.dev/free-llm-api.
- A separate tracker snapshot reports 141 entries, but its own changelog records ended offers and model removals; use it to find changes, not to assume every row is currently free: https://freellmapi.link/.
- Another November tracker reports 54 providers / 66 model rows, but only 17 fully verified and 49 partially verified. This is a useful warning that “provider count” and “verified usable free API count” are very different: https://plugsky.com/free-llm-api.
- OpenRouter's own pricing and collection pages should take precedence over old blog posts for current free-model limits: https://openrouter.ai/pricing ; https://openrouter.ai/collections/free-models.

**Verification boundary:** this pass reviewed public pages and tracker updates on 23 November 2026. It did not create accounts, attach payment methods, complete identity checks, or send live API requests. Any candidate still marked unverified must remain outside the confirmed-provider count.

## International verification pass — Hetzner, SambaNova, Mistral and NVIDIA (23 November 2026)

This pass uses provider-owned documentation to resolve several commonly repeated claims. It does not promote a service merely because a directory labels it free.

### Confirmed experimental free API

| Provider | Layer | Confirmed offer | Access / limits | Important conditions | Official source |
|---|---|---|---|---|---|
| Hetzner Inference API | **Layer 2 — recurring while experiment remains free** | Hetzner explicitly says its OpenAI-compatible hosted inference API is free of charge for as long as the service remains experimental. | Base URL: `https://inference.hetzner.com/api/v1`; API token required. Models listed in the current docs: `Qwen/Qwen3.6-35B-A3B-FP8` (text + image) and `Qwen3.8-27B` (text + image). Per API key: 4,000,000 input tokens / 60 seconds, 100,000 output tokens / 60 seconds, and 10 requests / 60 seconds. | This is a temporary experimental status, not a contractual permanent free tier. Hetzner says it will notify users by email before changing the free status. Availability/performance are not guaranteed and it is not recommended for production. Docs say request/response content is not stored; usage metadata such as timestamps and token counts is retained. Card requirement is not stated on the inference page; account/token issuance may require a Hetzner account. | https://docs.hetzner.com/general/company-and-policy/experiments/inference/ |

### Corrections — not a free inference API

| Provider | Previous common claim | Current official finding | Classification / action | Official source |
|---|---|---|---|---|
| SambaNova Cloud | “Free API tier” with daily free tokens and no card. | Current Plans page says the Free plan requires adding a payment method and purchasing credits to run the first requests; it includes pay-as-you-go credits and production model access. | **Do not count as a recurring $0 API allowance.** Reclassify as payment-method-gated paid usage unless a separate official free credit/quota is published. The page does not establish a no-card free tier. | https://cloud.sambanova.ai/plans |
| Mistral La Plateforme | “Free API mode” based on the free mode for Studio/Vibe. | Current official usage-limits docs explicitly say Free mode includes a monthly budget for trying Vibe and Studio but **does not include API access**; creating API keys and using the API require billing activation and pay-as-you-go. | **Exclude from Layer 2 API free tiers.** A free chat/IDE/Studio allowance is not API inference. Keep historical reports in the change log only. | https://docs.mistral.ai/admin/billing-usage/usage-limits |
| NVIDIA NIM / API Catalog | “NIM is a free hosted API with unlimited access.” | Official NIM docs distinguish no-charge NIM software/self-hosting under applicable licenses from hosted API Catalog access. Developer membership provides access to self-hosted NIM software; it does not by itself prove a recurring free hosted API quota. | Keep hosted API Catalog under evaluation/prototyping with console-specific limits unless a current hosted endpoint quota is explicitly published. Do not count self-hosting as a hosted free API. | https://docs.nvidia.com/nim/large-language-models/latest/about-nim-llm/nim-offerings.html ; https://docs.nvidia.com/nim/vision-language-models/latest/introduction.html |

### Evidence and classification notes

- Hetzner is a real provider-hosted API, not a self-hosting guide or an aggregator. Its “free while experimental” status is conditional and may end; check the official experiment page before depending on it.
- SambaNova's Free plan label does not mean zero-cost requests: the current plan page requires a payment method and purchased credits before first requests.
- Mistral's free monthly Studio/Vibe allowance is a product/IDE allowance, not API access. Do not infer API eligibility from the existence of a free console mode.
- NVIDIA's free NIM software and a hosted NVIDIA API Catalog endpoint are separate delivery models. Count only the hosted endpoint when a current hosted quota and terms are confirmed.

**Verification boundary:** public official documentation was reviewed on 23 November 2026. No Hetzner account was created, no payment method was added to SambaNova, and no live API request was sent. Hetzner's current model roster and account eligibility may change.


## Multimodal and specialist-generation APIs — expanded inventory (23 November 2026)

This section extends the same three-layer system to image generation, music/audio generation, 3D asset generation, text-to-speech (TTS), speech-to-text (STT), embeddings and reranking. These are **API offers**, not merely free web apps. The same provider may appear in more than one modality, but its allowance must be classified per product and must not be counted as multiple independent providers.

### Category map

| Category | What qualifies | Common false positive to exclude |
|---|---|---|
| AI image generation | An API endpoint that returns generated image bytes, URLs or an asynchronous image-generation job. | Free image playground or chat UI with no API entitlement. |
| AI music generation | API endpoint generating music/audio from text, lyrics, prompts or reference audio. | A free music website whose API is paid or unavailable. |
| AI 3D model generation | API endpoint returning a 3D mesh/asset from text or images. | Free web-app credits that do not include API access; open-source model requiring the user's own GPU. |
| TTS | API endpoint converting text into synthesized speech. | Browser read-aloud or a free voice feature without API access. |
| STT / transcription | API endpoint transcribing uploaded or streamed audio. | Local Whisper installation or a manual transcription website. |
| Embeddings | API endpoint returning vector representations for text, image or multimodal inputs. | A vector database free plan that does not include hosted embedding inference. |
| Reranking | API endpoint scoring/reordering candidate documents for a query. | A search product's UI feature with no callable rerank endpoint. |
| Audio effects / voice tools | API endpoint for sound effects, voice conversion, isolation, dubbing or audio transformations. | Free editor UI without API access. |

### Layer 1 — keyless / anonymous specialist APIs

Strict Layer 1 definition remains unchanged: no account, API key, placeholder/sentinel key, cookie, browser session or delegated identity. A public models list or an image website that happens to be free is not enough; the exact generation endpoint must work anonymously.

| Provider / endpoint | Modality | Status | Qualification / caveat | Evidence |
|---|---|---|---|---|
| Pollinations image API (`https://image.pollinations.ai/prompt/{prompt}`) | Image generation | `KEYLESS_CANDIDATE / historically anonymous` | A specialist API test guide reports that the legacy image host returned images without a key, at approximately one new image every 45 seconds per IP. Treat this as endpoint-specific and potentially changeable; verify a fresh anonymous image request before relying on it. This does not automatically prove that every Pollinations model or newer API route is keyless. | Browser/API test guide: https://cors.dev/guides/free-ai-image-api ; provider: https://pollinations.ai/ |
| Pollinations text endpoint already listed in Layer 1 | Text generation | Retain existing entry | Existing anonymous text-generation evidence does not itself prove the image route or every modality. Keep modality-specific evidence separate. | Existing Pollinations entry and endpoint notes above. |

**No other specialist modality is promoted to strict keyless in this pass.** Public web tools and anonymous playgrounds are not counted as TTS/STT/music/3D/embedding APIs without a reproducible anonymous API response.

### Layer 2 — recurring free quotas / free daily or monthly budgets

| Provider | Modality | Free allowance | Access and limit type | Card / eligibility / caveats | Official source |
|---|---|---|---|---|---|
| Cloudflare Workers AI | Image generation | Shared Workers AI free allowance: 10,000 Neurons per account per day. Flux.1 schnell is in the model catalog; published model pricing is 4.80 Neurons per 512×512 tile plus 9.60 Neurons per step. | Account ID + API token; daily reset. Image usage consumes the same Neuron budget as other Workers AI models, including text, speech and embeddings. Approximate image count depends on resolution, tiles, steps and other model use. | Account required. Do not treat 10,000 Neurons as 10,000 images or tokens. Confirm whether an eligible Workers account can invoke the exact model in its region. | https://developers.cloudflare.com/workers-ai/platform/pricing/ ; model catalog: https://developers.cloudflare.com/workers-ai/models/ |
| Cloudflare Workers AI | TTS | Same shared 10,000 Neurons/day. Hosted models include Deepgram Aura family. | API token; daily shared compute allowance, not a separate TTS bucket. | The free budget is shared across every Workers AI workload. Model-specific Neuron costs apply. | https://developers.cloudflare.com/workers-ai/models/ ; https://developers.cloudflare.com/workers-ai/platform/pricing/ |
| Cloudflare Workers AI | STT / ASR | Same shared 10,000 Neurons/day. Hosted speech-recognition models are listed in the catalog. | API token; daily shared compute allowance. | Do not count this as an additional 10,000 Neurons for transcription. | https://developers.cloudflare.com/workers-ai/models/ ; https://developers.cloudflare.com/workers-ai/platform/pricing/ |
| Cloudflare Workers AI | Embeddings | Same shared 10,000 Neurons/day. Catalog includes BGE, BGE-M3, Qwen3 Embedding and EmbeddingGemma models. | API token; daily shared compute allowance. Model pricing is per million input tokens in Neurons; for example `@cf/qwen/qwen3-embedding-0.6b` is listed at 1,075 Neurons per million input tokens. | Shared budget, not a separate embedding quota. Different models have different Neuron rates. | https://developers.cloudflare.com/workers-ai/platform/pricing/ ; https://developers.cloudflare.com/workers-ai/models/ |
| Google Gemini Developer API | TTS | Official pricing lists `gemini-3.8-flash-tts` with free-of-charge standard input and audio output on the Free tier. | API key; model-specific free rate limits. This is API inference, not just AI Studio's playback UI. | Free-tier data may be used to improve Google products. The page publishes pricing status, while actual RPM/RPD may be shown in AI Studio and can change. | https://ai.google.dev/gemini-api/docs/pricing |
| Google Cloud Text-to-Speech | TTS | Monthly free usage: first 4 million characters for Standard voices and first 1 million characters for WaveNet voices. | Google Cloud API; monthly account-level allowance. | A Cloud project and billing configuration may be required; payment-card/verification requirement varies by account and is not asserted here. Free characters are model/voice-class specific. | https://cloud.google.com/text-to-speech/pricing |
| Google Cloud Speech-to-Text | STT | Published pricing shows 60 minutes/month at $0 for the listed standard speech-recognition SKU with data logging. | Google Cloud API; monthly allowance. | The zero-price row is specifically the SKU with data logging; without-data-logging pricing differs. Cloud billing setup may be required even when usage remains within free quota. | https://cloud.google.com/speech-to-text/pricing |
| ElevenLabs | TTS, STT, music, sound effects and image tools | Free plan lists 10,000 credits/month shared across products. | Account required; monthly allowance. TTS and STT are explicitly API products; the general plan page includes Music and other creative features. | **API scope differs by product.** The public API pricing page confirms API pricing/products, but the free plan's product matrix does not unambiguously guarantee API access for every creative endpoint (especially music/image). Count TTS/STT as free-plan/API candidates; keep Music API entitlement `UNCONFIRMED` until the specific API endpoint accepts a Free-plan key. Credits are shared: current page estimates TTS 1 credit/character, STT 330 credits/minute and Music 900 credits/minute. Free plan is personal use; do not imply commercial rights. | https://elevenlabs.io/pricing ; API pricing: https://elevenlabs.io/pricing/api ; music pricing: https://elevenlabs.io/music |
| FreeTTS | TTS | 15,000 characters/month; 5,000 characters/day; 5,000 max per request; 10 requests/minute. | Free API key required; free REST endpoint. | Personal/non-commercial only; generated audio carries a spoken FreeTTS tag; files are retained for one hour. API key required, so Layer 2. | https://freetts.org/developers |
| Groq | STT | Existing Groq free tier includes rate-limited hosted Whisper transcription models. | API key; model-specific RPM/RPD/TPM caps are shown in Groq console/docs. | No separate fixed monthly audio-hours allowance is asserted here; distinguish request/rate caps from a guaranteed monthly audio quota. | https://console.groq.com/docs/rate-limits |
| Cohere | Embeddings and reranking | Trial API key includes free evaluation access; official limits list Embed at 2,000 inputs/minute and Rerank at 10 requests/minute. | Trial key; rate-limited free evaluation access, not a published monthly token balance. | Trial keys are for evaluation and not production/commercial use. The high RPM figure is a rate cap, not a monthly free quota. | https://docs.cohere.com/v1/docs/rate-limits |

**Layer 2 classification notes:** Cloudflare is one shared compute budget, not five separate free plans. ElevenLabs' 10,000 credits are one shared monthly pool and API entitlement is product-specific; do not assume the music website's free generation count is also an API quota. A rate limit (RPM) is not a promise that the provider will supply that many requests indefinitely.

### Layer 3 — one-time signup credits, trial balances and temporary promotions

| Provider | Modality | Free offer | Expiry / access | Card / other caveats | Official source |
|---|---|---|---|---|---|
| Stability AI Platform | Image generation, music/audio generation, sound effects and 3D-related testing | 25 free credits for new accounts. The platform says the credits can be used for Stable Image and Stable Audio API testing. | One-time new-account balance; API key required. | Official FAQ says no card is required to sign up. Credit consumption depends on model, operation and audio duration; do not translate 25 credits into a fixed number of songs/images without checking current endpoint pricing. | https://platform.stability.ai/ ; pricing/docs: https://platform.stability.ai/docs |
| Deepgram | STT and TTS | $200 signup credit (previously recorded in this file). | One-time trial balance; API. | The free-credit guide reports no card at signup; confirm the current dashboard balance and expiry before use. It is audio API credit, not general LLM credit. | https://deepgram.com/pricing ; https://developers.deepgram.com/docs |
| AssemblyAI | STT, streaming transcription and voice/audio APIs | $50 signup credit (previously recorded in this file). | One-time trial credit. | No card was reported at signup in the November 2026 specialist comparison; expiry/eligibility should be checked in the account. | https://www.assemblyai.com/pricing ; https://www.assemblyai.com/docs |
| Speechmatics | STT and speech APIs | $100 signup credit (previously recorded in this file); specialist comparison reports 12-month validity. | One-time trial credit. | No card reported in the November 2026 comparison. Verify eligible endpoints and remaining expiry. | https://www.speechmatics.com/pricing ; https://docs.speechmatics.com/ |
| Gladia | STT / transcription | €50 one-time credit; specialist comparison estimates up to about 312 hours depending on selected model/features. | One-time credit; comparison reports one-year validity. | No card reported in the comparison. Actual minutes vary by endpoint and optional features; do not treat the estimate as a guaranteed number of hours. | https://www.gladia.io/pricing ; https://docs.gladia.io/ |
| Voyage AI | Text/code embeddings and reranking | First 200 million tokens on eligible current embedding and reranking models, as recorded by the November 2026 specialist comparison. | One-time token balance; API key. | This is not a recurring monthly quota. Verify eligible model IDs and current account balance. Commercial use terms differ from providers with non-commercial trial restrictions; read the provider terms. | https://www.voyageai.com/pricing ; https://docs.voyageai.com/ |
| Jina AI | Embeddings and reranking | 10 million free API tokens (previously recorded in this file). | One-time/free-key balance, not a daily refill. | Earlier research noted non-commercial licensing for the relevant free-key models; check model-specific license and current API terms before using outputs commercially. | https://jina.ai/embeddings/ ; https://jina.ai/reranker/ |
| QwenCloud | Text embeddings and other eligible model inference | Typically 1,000,000 tokens per eligible model for new users; quota validity typically 90 days. | One-time new-user/model quota; API key and Singapore-region endpoint required by the current quota page. | Region-specific: the page says quota is available only in Singapore and only for real-time inference. After exhaustion/expiry, calls may be billed; enable quota safeguards and do not assume the older Alibaba Model Studio Beijing offer is the same program. | https://docs.qwencloud.com/resources/free-quota |
| Alibaba Cloud Model Studio (Qwen) | Text and multimodal embeddings; translation and other eligible models | Existing file entry: 1,000,000 tokens per eligible model, typically 90 days, under the separate Model Studio new-user offer. | One-time new-user/model quota; regional eligibility depends on the specific Model Studio region. | Earlier documented Beijing-only eligibility and identity verification must remain attached to this Model Studio offer. Do not merge it with QwenCloud's Singapore-only quota. | https://help.aliyun.com/en/model-studio/new-free-quota ; https://help.aliyun.com/en/model-studio/text-embedding-synchronous-api ; https://help.aliyun.com/en/model-studio/multimodal-embedding-api-reference |
| Replicate | Image, audio and video model inference | Selected models provide free test runs for new users / eligible accounts; number of runs is not published as a stable quota. | Trial/test access; asynchronous prediction API. | No card was reported for the free test runs in the November 2026 specialist comparison, but model availability and the number of free runs are not guaranteed. Do not present this as a recurring free tier. | https://replicate.com/pricing ; https://replicate.com/docs |
| Sarvam AI | Speech and language APIs (including speech services where available) | Existing file entry: ₹100 credit for each verified user, never expires. | One-time credit. | Card status remains unknown; identity/phone verification is part of account eligibility. Use only for the API products covered by the balance. | https://www.sarvam.ai/ ; https://docs.sarvam.ai/ |

### 3D generation — important API vs web-app distinction

| Provider | Web-app free offer | API free offer | Classification |
|---|---|---|---|
| Meshy | Official pricing says the web Free plan includes 100 credits/month, no card; credits reset monthly. Free-plan outputs are CC BY 4.0 with attribution. | The official Meshy API page says an API user must be on Pro or higher; the API pricing docs say API generation is pay-before-you-go and credits must be purchased. | **Do not put Meshy in Layer 2 as a free 3D API.** Record it as `FREE_WEB_APP_ONLY / API_PAID_OR_PLAN_GATED`. The 100 monthly credits apply to the web plan, not proof of API entitlement. | Official web pricing: https://www.meshy.ai/pricing ; API access: https://www.meshy.ai/api ; API credit pricing: https://docs.meshy.ai/en/api/pricing |
| Tencent Hunyuan 3D | A third-party comparison mentions free app generations at launch. | The comparison also mentions 200 free API credits at launch, but this pass did not establish a current official free API balance or current API terms. | `HISTORICAL_OR_UNVERIFIED_PROMOTION`; do not count as an active layer until current Tencent official documentation confirms the quota. | Discovery only: https://3d.sleipner.ai/blog/ai-3d-generators-compared ; official cloud catalog should be checked for current terms: https://cloud.tencent.com/ |
| Hyper3D / Rodin | Public generation experience and limited private assets are described by third-party comparison. | No current official free API quota confirmed in this pass. | `API_FREE_QUOTA_UNCONFIRMED`; keep out of confirmed layers. | Discovery only: https://3d.sleipner.ai/blog/ai-3d-generators-compared ; provider: https://hyper3d.ai/ |
| Tripo | Free web-app access is mentioned by third-party comparison. | No sufficiently clear current official recurring free API quota confirmed in this pass. | `API_FREE_QUOTA_UNCONFIRMED`; web credits do not establish API credits. | Discovery only: https://3d.sleipner.ai/blog/ai-3d-generators-compared ; provider: https://www.tripo3d.ai/ |

**3D result:** this research pass did not find a 3D generation service whose current official documentation clearly proves an ordinary, recurring, free, self-serve hosted API quota. Meshy is a useful free web app, but its API is paid/plan-gated. Keep the API category open rather than misclassifying free web credits as free API access.

### Music generation — API evidence and limits

- **Stability AI Stable Audio:** included in Layer 3 above. Its official platform FAQ confirms the 25-credit new-account grant applies to the platform and describes music, sound effects, ambience and loops generated from text or reference audio. It is the clearest provider-documented music/audio API trial found in this pass. Exact track count depends on duration/model and current credit pricing. https://platform.stability.ai/
- **ElevenLabs Music:** its Free plan lists Music and 10,000 shared credits/month, and the pricing page estimates 900 credits per generated minute. However, the public plan matrix does not clearly establish that the music-generation API endpoint is enabled for a Free-plan API key. Keep as `LAYER_2_WEB_FREE / API_ENTITLEMENT_UNCONFIRMED` until the API docs or a real free-key request confirms it. Personal-use restrictions apply to the free plan. https://elevenlabs.io/music ; https://elevenlabs.io/pricing/api
- **Replicate:** selected audio/music models can be tried with free test runs, but the number is unpublished and model-specific; Layer 3 trial only, not recurring. https://replicate.com/pricing
- **Do not count** a free music website, a prompt-to-song playground, or an open-source music model that must be run on the user's own GPU as a hosted free music API.

### Specialist API discovery sources (discovery, not final proof)

- Free image-generation API comparison, last checked 22 Nov 2026: https://aifree.dev/learn/free-image-generation-api
- Browser image API tests and anonymous Pollinations endpoint notes: https://cors.dev/guides/free-ai-image-api
- Free TTS API comparison: https://aifree.dev/learn/free-text-to-speech-api
- Free STT API comparison: https://aifree.dev/learn/free-speech-to-text-api
- Free embeddings/reranking comparison: https://aifree.dev/learn/free-embeddings-api
- Independent embedding/reranking directory: https://free-web-services.com/web-services/ai/embeddings/
- 3D generation comparison (use only to discover vendors; confirm terms on official docs): https://3d.sleipner.ai/blog/ai-3d-generators-compared

### Verification rules for all modalities

1. **Verify the actual API route.** A free web generator is not an API. A model catalog, playground or SDK install is not proof of a successful generation request.
2. **Keep allowances in their native units.** Characters, audio minutes, credits, tokens, Neurons, requests and 3D credits are not interchangeable. Never convert them to a generic “free tokens” number without a documented conversion.
3. **Separate shared pools.** If image, TTS, STT and music all draw from one 10,000-credit/Neuron pool, record one shared pool and list the supported modalities beneath it; do not multiply the allowance by the number of categories.
4. **Separate recurring from one-time.** Monthly credits belong in Layer 2; signup credits and finite test runs belong in Layer 3. A model's RPM limit is only a rate limit, not a recurring balance.
5. **Check the license.** Free-plan audio/image/3D outputs may be personal-use-only, non-commercial, attribution-required or watermarked. State the actual license rather than assuming free means unrestricted.
6. **Check data handling.** Audio, prompts, images and embeddings can contain personal information. Read retention/training terms, especially for free tiers.
7. **Do not imply local-model hosting is an API offer.** Self-hosted Stable Diffusion, Whisper, XTTS, MusicGen, TRELLIS or similar projects are useful software, but they belong in a separate self-hosted appendix, not these hosted API layers.
8. **Do not overstate coverage.** This pass found several confirmed image/TTS/STT/embedding offers, a small number of music API trials, and no clearly confirmed recurring free 3D-generation API. That is a finding, not a reason to fill gaps with unverified directory claims.

**Verification boundary:** public provider documentation and specialist comparisons were reviewed on 23 November 2026. No accounts were created, no payment methods or identity checks were attempted, and no live image/audio/3D/embedding requests were sent in this pass. Entries whose free API entitlement is unclear remain explicitly marked unconfirmed.

---

## Focused research pass 1 — AI image-generation APIs (23 November 2026)

This is the first modality-specific deep dive in the new research sequence. It covers **image-generation APIs only**. Video, music, TTS, STT, embeddings and 3D will be researched in separate passes so their quotas and API eligibility are not mixed together.

### Layer 1 — keyless image-generation APIs

| Provider / route | Status | What the evidence actually says | Classification decision |
|---|---|---|---|
| Pollinations legacy image route: `https://image.pollinations.ai/prompt/{prompt}` | `LEGACY_KEYLESS_CANDIDATE` | Older browser/API tests and a current Pollinations repository skill still describe a keyless GET route. However, the current main API documentation points users to `gen.pollinations.ai` and a secret key; current repository docs say the supported current API authenticates requests, while the old raw publishable-key flow is legacy and rate-limited. | Do **not** treat all Pollinations image generation as keyless. Keep only this exact legacy host/path as a candidate pending a fresh anonymous request test. The current supported API belongs in Layer 2/3 only if its Pollen balance/free grant is documented. |

**Layer 1 conclusion:** no image endpoint was newly promoted to fully verified strict-keyless status in this pass. An older URL working historically is not proof that the current route still works anonymously.

### Layer 2 — recurring free image API quotas

| Provider | API / model | Free allowance | Access / recurrence | Card, region and important caveats | Official evidence |
|---|---|---|---|---|---|
| Cloudflare Workers AI | Hosted image models, including FLUX-family options in the model catalogue | Shared allowance of **10,000 Neurons per account per day**, reset at 00:00 UTC. This is a shared Workers AI budget, not 10,000 images. | Workers account + account ID/API token; recurring daily allowance. Actual image count depends on the model, resolution, tiles and inference steps. | No separate image-only pool. Other Workers AI text, audio, speech and embedding calls consume the same daily allocation. Some newer frontier models require a paid Workers plan or prepaid AI Gateway credits; check the exact image model's pricing before use. | https://developers.cloudflare.com/workers-ai/platform/pricing/ ; https://developers.cloudflare.com/workers-ai/models/ |
| SiliconFlow | `Kwai-Kolors/Kolors` image generation API | Official pricing page labels the Kolors model **free**. No numeric daily/monthly cap was published in the reviewed pricing evidence. | Account/API key; callable image endpoint is documented at `POST /v1/images/generations`. Treat as ongoing free model pricing, but record quota as `UNPUBLISHED`, not unlimited. | China-oriented service and regional endpoint/docs. Account/card/identity requirements were not conclusively established by the reviewed API/pricing pages. Do not confuse the separate ¥16 voucher (real-name verification, 180-day validity, promotional) with the model's free per-call price. | https://siliconflow.cn/pricing ; https://api-docs.siliconflow.cn/docs/api/images-generations-post ; https://docs.siliconflow.cn/docs/userguide/capabilities/images |

### Layer 3 — one-time image API trials and signup credits

| Provider | API / model | Free offer | Access / expiry | Card and caveats | Official evidence |
|---|---|---|---|---|---|
| Stability AI | Stable Image API | **25 free credits** for new accounts. Current pricing says 1 credit = US$0.01; the number of images depends on the selected endpoint (for example, Stable Image Core is cheaper than Ultra). | One-time account grant; create an API key and call the REST API. | Official platform FAQ says signup does not require a card. Not a recurring allowance. Credits are shared with other Stability API products where applicable, including Stable Audio; do not count the same 25 credits again under music/audio. | https://platform.stability.ai/ ; https://platform.stability.ai/pricing ; https://platform.stability.ai/docs/api-reference/ |
| Replicate | Selected image models in the official “Try for Free” collection, including Imagen 4 and selected FLUX / Ideogram models | Limited free runs; exact number is unpublished. | Account required; one-time/limited evaluation access, not a daily or monthly quota. | Replicate explicitly says the free runs are limited and stop when the allowance is used; adding billing/credits is needed to continue. Card requirement for the initial free runs is not stated clearly in the official collection page, so record `UNKNOWN_NOT_PUBLISHED`. Model licenses vary. | https://replicate.com/collections/try-for-free ; https://replicate.com/pricing |
| Pollinations | Current authenticated image API | A first-key Pollen grant is reported by specialist comparison sources; amount and eligibility can change. | API key via Pollinations Connect; finite Pollen balance, not strict keyless access. | Keep the exact current grant as `PROVISIONAL` unless the user's account dashboard/provider terms show the amount. Current docs require authentication for supported API use; do not rely on old anonymous endpoint claims. | https://gen.pollinations.ai/ ; https://enter.pollinations.ai/keys ; https://github.com/pollinations/pollinations |

### Image services deliberately not counted as free hosted APIs

- **Bing Image Creator, Ideogram, Recraft, Leonardo, Venice and similar browser generators:** free web-plan access does not prove a free developer API. Keep them in a separate “free web tools” appendix unless an official API entitlement and a free API balance are documented.
- **Meshy:** its free monthly web credits do not grant free API access; its API is plan-gated/paid according to the already-recorded official API documentation. Keep it out of the free image API layers.
- **StudioLM:** the browser generator is free, but the public developer API is prepaid at a per-image price. Not a free API.
- **SiliconFlow's ¥16 voucher:** a one-time regional voucher requiring real-name verification is separate from the `Kolors` model marked free in its API pricing table. Do not merge the voucher into the recurring model allowance.
- **OVHcloud SDXL anonymous/free endpoint:** specialist comparison material reports a limited free SDXL route and a retirement date of 10 February 2027, but this pass did not capture sufficiently direct current official pricing documentation for the exact free image entitlement. Keep as `OFFICIAL_QUOTA_RECHECK_REQUIRED`, not confirmed.
- **Agnes AI free image routes:** found in specialist directories, but this pass did not obtain provider-owned pricing/terms that establish a stable free image API quota. Candidate only.
- **Hugging Face, OpenRouter, Together, DeepInfra, fal.ai, Runware and other image gateways:** do not inherit a free API label from a model card, playground, web plan or historical credit offer. Require current provider pricing evidence for the exact inference route; paid-only or top-up-required routes remain excluded from free layers.

### Image-specific verification notes

1. The strongest current recurring image API evidence found in this pass is Cloudflare's shared 10,000-Neuron daily allocation and SiliconFlow's free-priced Kolors API model. Neither publishes a guaranteed number of images per day.
2. Stability AI's 25 credits and Replicate's limited free runs belong in Layer 3, not Layer 2.
3. Pollinations has changed authentication semantics over time. Keep the old image host/path separate from the current authenticated `gen.pollinations.ai` API.
4. A free image-generation website is not automatically a free image-generation API. API keys, endpoint access, quotas, terms and model licenses must be checked independently.
5. No fresh generation request was sent to these providers in this pass. “Officially documented” means the provider's current public docs/pricing support the stated offer; it does not mean an account-specific live request was tested.

### Sources used for image discovery (not all are proof)

- 2026 image API comparison with offer checks dated 22 November 2026: https://aifree.dev/learn/free-image-generation-api
- Image API endpoint directory (discovery only; verify all rows against official provider docs): https://github.com/yir-ai/free-image-generation-apis
- Cloudflare Workers AI official pricing, updated 18 November 2026: https://developers.cloudflare.com/workers-ai/platform/pricing/
- Stability AI official platform, pricing and API reference: https://platform.stability.ai/ ; https://platform.stability.ai/pricing ; https://platform.stability.ai/docs/api-reference/
- Replicate official Try for Free collection: https://replicate.com/collections/try-for-free
- SiliconFlow official image API and pricing: https://siliconflow.cn/pricing ; https://api-docs.siliconflow.cn/docs/api/images-generations-post
- Pollinations current API documentation and authentication notes: https://gen.pollinations.ai/ ; https://github.com/pollinations/pollinations


### Image deep-dive expansion — additional provider checks (23 November 2026)

The previous image pass was too narrow. This expansion adds providers discovered through independent API-specific research, then checked against provider-owned pricing/docs. It does **not** count free browser apps as free APIs, and it does not claim an API offer is globally available if eligibility is unpublished.

#### Additional Layer 1 — strict keyless

| Provider / exact route | Finding | Decision |
|---|---|---|
| OVHcloud AI Endpoints — anonymous model requests | Official documentation explicitly publishes an anonymous limit of **2 requests/minute/IP/model**, compared with 400 RPM for authenticated API keys. The official product page says the model playground can be tested for free, but the official sources reviewed here do not clearly establish that every anonymous image model request is zero-priced for all users. An independent API audit reports an anonymous SDXL route with a limited free window and a model retirement date of 10 February 2027. | `KEYLESS_API_ROUTE_CONFIRMED / FREE_IMAGE_BILLING_NOT_FULLY_CONFIRMED`. Keep as a high-priority candidate, not a fully verified free service. Confirm the selected model's price and retirement status before use. Sources: https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-getting-started ; https://www.ovhcloud.com/en/public-cloud/ai-endpoints/ ; discovery/audit: https://aifree.dev/learn/free-image-generation-api |
| Pollinations legacy image endpoint | Historical anonymous route remains a candidate, but current supported API docs use authenticated keys/Pollen. | Do not promote to strict keyless until a fresh unauthenticated generation request succeeds on the exact legacy host. See prior row and current docs: https://gen.pollinations.ai/ |

**Layer 1 result:** no newly verified globally usable, strict-keyless image API was established by this expansion. OVHcloud is a documented anonymous route but the exact free billing entitlement for image inference needs confirmation; Pollinations' legacy route needs a fresh test.

#### Additional Layer 2 — recurring free image API

| Provider | API capability | Recurring free allowance | Requirements / caveats | Classification and source |
|---|---|---|---|---|
| Cloudinary Image Generation add-on | Text-to-image and image-guided generation through `POST https://api.cloudinary.com/v2/generate/<CLOUD_NAME>/text_to_image`; API output can be temporary or saved as a managed asset. | **Not confirmed as a recurring free generation quota.** Cloudinary's standard Free plan has 25 monthly credits for transformations/storage/bandwidth, but the Image Generation add-on has its own separate quota and paid plans. Do not reuse the standard 25-credit allowance as image-generation credits. | Account and API credentials required. The add-on must be registered. A free trial allocation exists, but the official docs describe it separately from the base Cloudinary monthly credits; check the account's Add-ons quota. | `API_CONFIRMED / FREE_TRIAL_CONFIRMED / RECURRING_IMAGE_QUOTA_UNPUBLISHED`; keep the trial in Layer 3 until a recurring image-specific allowance is documented. Sources: https://production.cloudinary.com/documentation/image_generation_addon ; https://cloudinary.com/pricing ; https://cloudinary.com/documentation/billing_and_plans |

#### Additional Layer 3 — one-time / finite image API trials

| Provider | API / free grant | Card / eligibility | What is actually verified | Source |
|---|---|---|---|---|
| Runware | **US$2 free credits** for new users signing up with a **business email**. Supports image-generation APIs across many models. | Business email required for the published grant. Card requirement is not stated in the official pricing FAQ; record `UNKNOWN_NOT_PUBLISHED`, not “no card”. | Official pricing FAQ explicitly states the $2 grant. This is a one-time trial balance, not recurring free inference. | https://runware.ai/pricing ; https://runware.ai/docs/models-api/pricing |
| WaveSpeedAI | **US$1 free credits** for eligible new accounts. Image and video models are both available through APIs. | Official pricing page says no credit card required and qualifies the grant as for eligible new accounts. Exact eligibility/region exclusions are not fully described on the pricing page. | Official provider pricing states “Eligible new accounts get $1 in free credits”. One-time trial, not daily/monthly free quota. | https://wavespeed.ai/pricing |
| Cloudinary Image Generation add-on | Free trial allocation for image generation; official docs expose an add-on-specific quota and API route. | Free Cloudinary account can register for the add-on; standard account signup is no-card. The amount of image-generation trial credit can vary by account/plan and is not stated as a universal recurring quota. | Real API documented. Keep Layer 3 as `TRIAL_AMOUNT_ACCOUNT_SPECIFIC`; do not claim 25 monthly base credits are usable for generation. | https://production.cloudinary.com/documentation/image_generation_addon ; https://cloudinary.com/tools/image-generation-api |
| Runway / Leonardo API | Not added as free API offers. Their browser plans/free tokens are separate from developer API billing. | API is pay-as-you-go / paid credit balance. | Explicitly excluded to prevent web-app free credits being misreported as API credits. Leonardo's API docs say purchase API credits; Runway has no confirmed current free API balance in this pass. | https://docs.leonardo.ai/me/docs/getting-started ; https://leonardo.ai/api |

#### Corrections and exclusions after the deeper image search

- **Cloudinary:** the standard Free plan's 25 monthly credits are for transformations, storage and bandwidth. Image Generation is a separately metered add-on with its own free trial quota and paid plans. Keep the image-generation trial distinct; do not call it a confirmed recurring monthly image API quota.
- **Runware:** add the documented $2 business-email trial to Layer 3. Do not call it a free recurring tier, and do not claim no-card because the provider's pricing FAQ does not explicitly say so.
- **WaveSpeedAI:** add the documented $1 eligible-new-account grant to Layer 3. Its pricing page explicitly says no card required. It supports both image and video APIs; record the video applicability again in the later video pass, but do not double-count the same $1 balance as two separate credits.
- **Replicate:** the official Try for Free collection explicitly says selected image/video/audio models can run without purchased credits for a limited number of runs, then billing is required. The number of runs is unpublished; it is not a perpetual free tier. https://replicate.com/collections/try-for-free ; https://replicate.com/docs/topics/billing
- **OVHcloud:** anonymous rate limits are real, but RPM is not a free balance. Keep the exact anonymous SDXL free claim provisional until model-specific official pricing and retirement status are checked. https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-getting-started
- **Cloudflare:** its 10,000 Neurons/day is a shared Workers AI pool. The current pricing table gives image models their own per-tile/per-step costs; never convert this into a fixed daily image count without specifying model, resolution and steps. https://developers.cloudflare.com/workers-ai/platform/pricing/
- **Leonardo:** its consumer website free plan (150 Fast Tokens/day) does not give API access. API docs require purchasing API credits; exclude from free API layers. https://leonardo.ai/pricing?plan=api ; https://docs.leonardo.ai/me/docs/getting-started

#### Expanded image discovery sources (discovery, then provider verification)

- Image/video API catalogue with links to official pricing pages: https://github.com/yir-ai/free-image-generation-apis
- Current image API free-tier comparison: https://aifree.dev/learn/free-image-generation-api
- Browser-origin API/CORS tests (useful for identifying exact callable routes; CORS success is not proof of free billing): https://cors.dev/guides/free-ai-image-api
- Cloudinary image-generation API guide and quota details: https://production.cloudinary.com/documentation/image_generation_addon

**Updated image-pass conclusion:** the confirmed list is now broader: Cloudflare and SiliconFlow Kolors remain the recurring candidates; Stability AI, Replicate, Runware, WaveSpeedAI and Cloudinary have finite or account-specific trial paths. OVHcloud is a strong anonymous-route candidate but is not promoted to confirmed free image inference without exact model billing proof. No additional strict-keyless provider was verified. This is a deliberate evidence-based result, not an attempt to inflate the provider count.

### Image deep-dive expansion 2 — broader provider discovery (23 November 2026)

This pass deliberately searched beyond the usual Stability / Replicate / Cloudflare shortlist. New entries below are included only where an API route and an explicit free allocation or trial are documented by the provider. A service's browser playground, free web plan, or open model listing is not sufficient.

#### New Layer 1 — keyless image generation

No additional provider was promoted to fully verified strict-keyless status in this pass. Pollinations' old `image.pollinations.ai` route remains a legacy candidate only: current supported API documentation directs developers to authenticated `gen.pollinations.ai` and Pollen balances. OVHcloud's anonymous rate limit is documented, but rate limits alone do not prove that the selected image model is free of charge. Keep both separate from confirmed free/keyless providers until a live anonymous image-generation call and its billing terms are verified.

#### New Layer 2 — recurring free image API quotas

| Provider | API and published free amount | Access / recurrence | Caveats and classification | Official source |
|---|---|---|---|---|
| **Pixazo API** | **US$10/month image-generation balance** for the image category. Provider estimates up to 2,500 FLUX Schnell or SDXL images at its published rates. | Create a Pixazo API account and API key; allowance is automatically added and resets on the 1st of each month. | `RECURRING_MONTHLY_API_CREDIT`. No card required to start. Image balance is a separate category from its $5 video and $2 audio balances; do not count those under images. The free amount is an API allowance, not the consumer app's free plan. Rate limit published as 60 requests/minute for free-balance APIs. When the image balance is exhausted, further requests use wallet funds or are rejected if the wallet cannot cover them; avoid enabling top-ups unless intended. | https://www.pixazo.ai/pixazo-free-tier |
| **Kindly API** | Its API documentation states a free monthly allowance of **100 image generations** (and a separate 1,000 text responses). | API key obtained after signup; monthly allowance. | `RECURRING_MONTHLY_QUOTA_REPORTED_BY_PROVIDER`. This is a smaller/less independently corroborated provider than the major platforms. The docs do not clearly state card, region, model identity, output license, or whether all image sizes/styles consume one unit. Keep those fields `UNKNOWN_NOT_PUBLISHED`; verify the live dashboard before production use. | https://docs.kindly.dev/ |

**Important:** Cloudinary's standard Free plan has 25 monthly credits for transformations, storage and bandwidth, not a guaranteed recurring image-generation quota. Its separate Image Generation add-on has an API and a free trial allocation, but the image-generation amount is account/plan-specific in the documentation reviewed here. Therefore it remains Layer 3 / account-specific trial, not a confirmed monthly image quota. Sources: https://cloudinary.com/pricing ; https://cloudinary.com/documentation/billing_and_plans ; https://production.cloudinary.com/documentation/image_generation_addon ; https://cloudinary.com/tools/image-generation-api

#### New Layer 3 — one-time image API credits and grants

| Provider | Exact image API offer | Eligibility / card | Classification and limits | Official source |
|---|---|---|---|---|
| **Runware** | **US$2 trial credits** for new users signing up with a business email. Image API supports multiple hosted models. | Business email required. Card requirement is not explicitly stated in the provider FAQ (`UNKNOWN_NOT_PUBLISHED`). | `ONE_TIME_TRIAL`. Do not describe as recurring or available to every personal-email signup. | https://runware.ai/pricing?category=image |
| **WaveSpeedAI** | **US$1 free credits** for eligible new accounts; image generation is available through the REST API. | Official page says no credit card is required to start; eligibility may vary and is not exhaustively described. | `ONE_TIME_TRIAL`; shared balance across the platform's image/video/other model endpoints. Do not duplicate the same $1 balance as a separate video credit in the later video section. | https://wavespeed.ai/pricing ; https://wavespeed.ai/docs/image-generator |
| **fal — Builder Grant** | Application-based **US$25–US$250** credits for indie builders; credits can be used across fal's image, video, audio and 3D model library. | Official program currently says teams based in **Europe and Asia**; application/approval required. This is not an automatic signup credit. | `APPLICATION_GRANT / REGION_RESTRICTED`. User location in Libya is outside the currently published Europe/Asia eligibility, so do not present it as an available personal offer for a Libyan applicant. For the global directory, retain it as a conditional program. The separate Startup Program starts at $1,000 and is for scaling startups, not a general free tier. | https://fal.ai/startups ; https://fal.ai/builder-grant |
| **Cloudinary Image Generation add-on** | Image Generation API has a separate free trial allocation. | Free account signup is no-card, but the add-on's specific trial amount is not published as a universal number. | `ACCOUNT_SPECIFIC_TRIAL`; do not transfer Cloudinary's 25 base monthly credits to this add-on or claim recurring image-generation credits. | https://production.cloudinary.com/documentation/image_generation_addon ; https://cloudinary.com/tools/image-generation-api |

#### Further exclusions and corrections from this broader pass

- **Google Gemini / Imagen / Nano Banana API:** image models are not part of the free API tier in the reviewed 2026 provider pricing evidence. A free AI Studio browser experience does not make the image API free. Exclude from image Layers 1–3 unless Google changes the model-specific API pricing. (Official pricing: https://ai.google.dev/gemini-api/docs/pricing)
- **Together AI:** do not reuse old `$5 signup credit` or `FLUX.1-schnell-Free` claims. Current image API is paid; the old free serverless image model was removed. (Provider pricing and model catalogue: https://www.together.ai/pricing ; https://www.together.ai/models)
- **Hugging Face Inference Providers:** free accounts currently have no general inference credit allocation for hosted image generation; do not confuse public Spaces demos with the Inference Providers API. (https://huggingface.co/pricing ; https://huggingface.co/docs/inference-providers/index)
- **Leonardo API:** the consumer website's daily free tokens do not transfer to the developer API. API use requires a separate paid credit balance. Exclude from free API layers. (https://leonardo.ai/pricing?plan=api ; https://docs.leonardo.ai/me/docs/getting-started)
- **fal default self-serve API:** no automatic general signup grant was established in the reviewed official pricing evidence. The Builder Grant is a separate application program with geographic eligibility; do not describe fal as universally free. (https://fal.ai/pricing ; https://fal.ai/startups)
- **Runway API:** free browser credits and conflicting third-party claims do not establish a free API allowance. Keep out unless official API billing terms show a usable free balance. (https://docs.dev.runwayml.com/guides/pricing/)
- **Cloudinary standard plan:** 25 monthly credits are for media management/transformation/storage/bandwidth. Image Generation is a separately metered add-on. Do not count the same base credits as image-generation credits.
- **Prodia, Dezgo, StarryAI, Craiyon, Segmind, AirBrush and similar names:** found in broad GitHub directories, but this pass did not find sufficiently current provider-owned evidence for the exact free API quota and conditions. Keep them in a candidate queue, not the confirmed layers. A directory's quoted daily numbers are not proof.
- **APImage and Sikasio Image Gen API:** public pages expose API/quota claims, but this pass did not establish enough independent/provider business and terms evidence to place them among confirmed providers. Keep as `LOW_CONFIDENCE_CANDIDATE` pending identity, privacy, terms, and live API checks.

#### Broader discovery sources used (discovery only; official provider pages remain the evidence)

- https://github.com/yir-ai/free-image-generation-apis — image/video API catalogue with provider pricing links; useful for discovering new vendors and spotting removed free tiers.
- https://www.freecredits.ai/guides/image-generation — image API offers and explicit notes distinguishing recurring credit from trials.
- https://cors.dev/guides/free-ai-image-api — tested browser-origin requests/CORS; CORS success is not proof of free billing.
- https://freellmapi.co/free-image-generation-api — discovery list; every claimed provider still needs its own pricing/docs check.

#### Current image-only inventory after expansion 2

- **Layer 1 (strict keyless, confirmed):** no new provider confirmed in this pass. Pollinations legacy route and OVHcloud anonymous SDXL remain conditional candidates only.
- **Layer 2 (recurring):** Cloudflare Workers AI (shared 10,000 Neurons/day, not image-only); SiliconFlow Kolors (free-priced model, numeric quota unpublished); **Pixazo API ($10 image balance/month, no card to start)**; **Kindly API (100 images/month according to its API docs; card/region/terms unknown)**.
- **Layer 3 (finite/application):** Stability AI (25 credits); Replicate (limited free runs); Runware ($2 business-email trial); WaveSpeedAI ($1 eligible-account trial, no card); Cloudinary Image Generation add-on (account-specific free trial); fal Builder Grant ($25–$250, application and Europe/Asia eligibility).

The larger count is not achieved by relabeling web-app plans as APIs. The new recurring additions are Pixazo and Kindly; the new finite additions are Runware, WaveSpeedAI, Cloudinary's separate image add-on trial, and fal's conditional grant. All other candidates remain explicitly unconfirmed.

### Image provider research — focused verification pass 3 (23 November 2026)

This pass was intentionally limited to image-generation APIs. It searched provider pricing/docs, image-specific API catalogs, and independent request/CORS audits. New services are added only when an API route and a usable free grant can be distinguished from a free website, playground, or model listing. Existing providers are not counted again as new vendors merely because they host several image models.

#### Layer 1 — strict keyless image generation

No new provider is promoted to confirmed strict-keyless status in this pass.

- **OVHcloud AI Endpoints:** official docs confirm anonymous access is rate-limited to 2 requests/minute/IP/model, but a rate limit is not proof that image inference is free. Keep as `ANONYMOUS_ROUTE_CONFIRMED / FREE_BILLING_UNCONFIRMED`; check the exact SDXL model price and lifecycle before treating it as free. Official docs: https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-getting-started and https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-troubleshooting
- **Pollinations:** current supported API documentation uses authenticated API keys/Pollen. Do not list the current API as keyless. The old image host is historical only until a fresh no-auth generation call is tested. https://gen.pollinations.ai/

#### Layer 2 — recurring free image API quotas

| Provider | Exact API offer | Recurrence / access | Conditions and cautions | Evidence / classification |
|---|---|---|---|---|
| **Pixazo API** | **US$10/month dedicated image-generation balance**. Official page lists Flux Schnell, SDXL, SDXL Lightning, SD 1.5 Inpainting, PixelForge 1.0, PixelForge Relighting and Qwen Image Edit. Provider estimates up to 2,500 Flux Schnell or SDXL images at listed rates; this is an estimate, not a fixed image count. | Automatically added to each Pixazo API account; resets on the 1st of each month. API key required. | Official page says no card needed to start. The free image balance is separate from its $5 video and $2 audio balances. After the image balance is exhausted, requests may charge wallet funds; do not enable/assume auto top-up. | `RECURRING_MONTHLY_API_CREDIT / NO_CARD_TO_START`. Official: https://www.pixazo.ai/pixazo-free-tier |
| **Kindly API** | API docs state **100 image generations/month** plus a separate 1,000 text responses/month. | Account signup and API key; monthly free tier. | Card requirement, supported image model, region, output license and whether all resolutions cost one unit are not stated in the reviewed docs. Treat the 100-image quota as provider-published but lower-confidence until confirmed in a live account. | `RECURRING_MONTHLY_QUOTA_PROVIDER_DOCS / CARD_UNKNOWN`. Official: https://docs.kindly.dev/docs/setup |
| **OpenRouter — Recraft V4.1 Flash V2** | `recraft/recraft-v4.1-flash-v2:free`, via the dedicated image generation endpoint `POST https://openrouter.ai/api/v1/images`. The model page lists $0 image generation. | API key required; free-model pool rules are 20 RPM and 50 RPD for `:free` variants (higher 1,000 RPD only after buying at least $10 in credits; that higher tier is not free and must not be counted). | **Temporary model listing:** provider page says it is going away **28 November 2026**. Generation-only; no image input/style reference support. It is an aggregator route, not a separate Recraft-owned free quota. Not available through EU in-region routing. Do not assume it remains available after removal. | `TEMPORARY_FREE_MODEL / AGGREGATOR / 50_RPD_BASE_CAP`. Official model: https://openrouter.ai/recraft/recraft-v4.1-flash-v2:free ; official free-model limits: https://openrouter.ai/collections/free-models/ |

#### Layer 3 — one-time or finite image API credits

| Provider | Free API grant | Access / card | Classification and caveats | Official source |
|---|---|---|---|---|
| **WaveSpeedAI** | **US$1** for eligible new accounts, usable on supported image models (also video/audio models, but the same balance must not be counted again in later sections). | Google/GitHub sign-in; no credit card required to sign up. Eligibility is account-qualified; registering a new email alone does not guarantee the grant. | `ONE_TIME_TRIAL / NO_CARD_TO_START / ELIGIBILITY_FILTERED`. Some premium models may not accept trial credit. The service is pay-per-use after the balance. | https://wavespeed.ai/pricing ; https://wavespeed.ai/docs/faq |
| **Cloudinary Image Generation add-on** | Free add-on plan for image-generation API; the API response exposes a separate `image_generation` quota. A sample official response shows a quota limit of 50 units, but the reviewed docs do not establish that 50 is universal for every account or model. | Cloudinary account, API key + secret, and add-on registration. The base Cloudinary free account can register; no card required for basic signup. | `ACCOUNT_SPECIFIC_FREE_TRIAL / IMAGE_ADDON_SEPARATE_FROM_BASE_PLAN`. The standard Cloudinary monthly media credits are not image-generation credits. The add-on free allocation is finite; paid add-on subscription is required after exhaustion. | https://production.cloudinary.com/documentation/image_generation_addon ; https://cloudinary.com/tools/image-generation-api |
| **Runware** | **US$2 trial credits** for new users with a business email. | Business email required. Card requirement is not explicitly stated in the provider FAQ (`UNKNOWN_NOT_PUBLISHED`). | `ONE_TIME_TRIAL`; do not imply personal-email eligibility or a recurring allowance. | https://runware.ai/pricing ; https://runware.ai/docs/models-api/pricing |
| **Stability AI** | **25 free API credits** for new developer accounts. | Account and API key. Card status should be checked in account onboarding; do not infer from web playground. | `ONE_TIME_TRIAL`. Credit usage depends on model: official price table shows Stable Image Core at 3 credits, SD 3.5 Large at 6.5 credits, and other model-specific costs. It is not 25 free images. | https://platform.stability.ai/pricing |
| **Replicate** | Selected public models can run for free a limited number of times; exact number is not published as a universal quota. | Account required; billing setup is required after the free allowance is exhausted. Card requirement for the initial free runs is not stated clearly in the reviewed billing page. | `FINITE_FREE_RUNS / MODEL_SPECIFIC`. Replicate is pay-as-you-go after the limited free runs; not a recurring free tier. | https://replicate.com/collections/try-for-free ; https://replicate.com/docs/topics/billing |
| **fal Builder Grant** | Application-based grant of **US$25–US$250** for approved indie builders; credits can be spent on supported image models as well as other modalities. | Application and approval required. Published eligibility currently targets teams based in Europe and Asia; Libya is not within the published eligible regions. | `APPLICATION_GRANT / REGION_RESTRICTED`; retain for directory completeness, but do not present as an available personal grant for applicants in Libya. fal's ordinary self-serve API is not automatically free. | https://fal.ai/builder-grant ; https://fal.ai/startups |

#### Provider/model findings that must NOT be misclassified as free

- **Google Gemini image models (Nano Banana family / Imagen):** the current official Gemini API pricing page lists image generation models with `Free Tier: Not available`. A free AI Studio playground does not create free API inference. Exclude from image Layers 1–3 unless the provider changes model-specific pricing. https://ai.google.dev/gemini-api/docs/pricing
- **OpenRouter free-model catalog:** the existence of a free chat model catalog does not mean image generation is free. The specific Recraft V4.1 Flash V2 `:free` image listing above is a time-limited exception. OpenRouter's own image tutorial says there is no general free image-generation tier when no image model has a `:free` suffix. Recheck after 28 November. https://openrouter.ai/blog/tutorials/image-generation-models/ ; https://openrouter.ai/collections/free-models/
- **Replicate:** free runs are limited to selected models and then require billing; do not label all hosted models free. https://replicate.com/docs/topics/billing
- **Cloudinary:** its Image Generation add-on is a real API, but it has its own credits and billing separate from the general Cloudinary Free plan. Do not transfer the general plan's monthly media credits to image generation. https://production.cloudinary.com/documentation/image_generation_addon
- **WaveSpeedAI:** $1 is an eligibility-filtered one-time balance shared across supported model families; not a recurring image quota. https://wavespeed.ai/pricing
- **OVHcloud:** anonymous RPM is an access/rate-limit property, not a free credit grant. https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-troubleshooting
- **Zhipu CogView-3-Flash and SiliconFlow Kolors:** third-party image API trackers currently list free model access, but this pass did not retrieve sufficiently clear official pricing/eligibility evidence for the exact current free entitlement. Keep them as `OFFICIAL_QUOTA_RECHECK_REQUIRED`, not fully confirmed. Discovery pages: https://ai-resource-radar.github.io/ai-resource-radar/en/scenarios/free-image-generation-api/ ; official docs to recheck: https://docs.bigmodel.cn/ ; https://docs.siliconflow.cn/

#### Research quality and inventory summary

This pass adds **new provider entries** rather than counting each model as a new vendor:

- New recurring/API-layer additions documented here: **Pixazo API**, **Kindly API**, and the temporary **OpenRouter/Recraft V4.1 Flash V2** model route.
- Additional finite grants or trial clarifications: **WaveSpeedAI**, **Cloudinary Image Generation**, **Runware**, **Stability AI**, **Replicate**, and the region-limited **fal Builder Grant**.
- The OpenRouter/Recraft offer has a scheduled removal date of 28 November 2026; mark it for a post-expiry check.
- No new strict-keyless image provider was proven. Anonymous rate limits and old unauthenticated URLs do not establish a free service.
- No image API was called with a live personal account in this research pass. All entries are based on public provider documentation/pricing; account-specific entitlement and actual generation success remain untested unless stated otherwise.

#### Sources for this focused pass

- Pixazo API monthly free-tier details: https://www.pixazo.ai/pixazo-free-tier
- Kindly API quota and endpoint docs: https://docs.kindly.dev/docs/setup
- OpenRouter/Recraft model, free pricing, expiry and endpoint: https://openrouter.ai/recraft/recraft-v4.1-flash-v2:free
- OpenRouter free model rate limits: https://openrouter.ai/collections/free-models/
- WaveSpeedAI official $1 offer and no-card statement: https://wavespeed.ai/pricing ; https://wavespeed.ai/docs/faq
- Cloudinary Image Generation API, free add-on and quota reporting: https://production.cloudinary.com/documentation/image_generation_addon
- Runware API pricing: https://runware.ai/pricing
- Stability AI API credits/pricing: https://platform.stability.ai/pricing
- Replicate billing and free-run restrictions: https://replicate.com/docs/topics/billing ; https://replicate.com/collections/try-for-free
- fal Builder Grant eligibility: https://fal.ai/builder-grant
- Cloudflare current image-model neuron prices and 10,000-Neuron daily allocation: https://developers.cloudflare.com/workers-ai/platform/pricing/
- Google Gemini API image-model pricing: https://ai.google.dev/gemini-api/docs/pricing
- OVHcloud anonymous rate-limit documentation: https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-troubleshooting

---

# Research expansion — deAPI image API (23 November 2026)

## Layer 3 — one-time signup credits (additional provider)

| Provider | Free offer | API route / models | Classification and caveats | Official source |
|---|---|---|---|---|
| **deAPI** | **$5 one-time signup credit** after email verification; no card; the image offer states 90-day expiry and up to 100 image requests/day until the first top-up. | `POST /api/v2/images/generations`; examples include `Flux_2_Klein_4B_BF16`, `ZImageTurbo_INT8`, `ZAnimeDistill_8Step_INT8`, `Flux1schnell`. Async job returns a request ID/result URL. | `LAYER_3_SHARED_MULTIMODAL_CREDIT / OFFICIAL_VENDOR_PAGE`. $5 is a shared platform balance, not $5 for each modality. Price varies by model, image size and steps; daily request cap does not mean the account receives 100 free images independent of credit balance. The provider also documents an OpenAI-compatible image route for selected models. | https://deapi.ai/lp/en/free-image-generation-api ; https://deapi.ai/lp/en/flux-2-klein ; https://deapi.ai/lp/en/z-image-turbo |

**Cross-modality accounting:** deAPI is also listed in LLM, video and music sections. Its single signup balance must be counted once across eligible model calls. The provider's browser Playground allowance is not an anonymous API entitlement; API calls require a registered account and API key.
