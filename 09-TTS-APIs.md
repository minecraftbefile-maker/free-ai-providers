# Text-to-Speech (TTS) — Hosted APIs

> Text-to-speech synthesis APIs only. Browser voice tools are not API entitlements.

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

# Text-to-Speech and Speech-to-Text APIs

> Split edition of the original 23 November 2026 research ledger. Original source line range: 1964–2340, plus new audit. Provider claims and quota snapshots are time-sensitive; read each evidence label and caveat.

# Section 3 — AI Text-to-Speech (TTS) API research (23 November 2026)

**Scope:** Hosted text-to-speech inference APIs only. Count a provider when a real API endpoint synthesizes text into audio. Keep browser-only voice generators, local SDKs/models, unofficial protocol clients, speech-to-text, voice cloning, and generic voice-agent bundles distinct. A free account or a free playground is not proof that the TTS API itself is free.

**Research allocation:** Layer 1 receives approximately 50% of discovery effort, Layer 2 approximately 40%, and Layer 3 approximately 10%. These are research-effort shares, not provider counts.

## TTS Layer 1 — strict keyless / anonymous hosted API

Strict Layer 1 means no account, API key, placeholder credential, cookie, browser session, or delegated identity is needed for the actual synthesis request. A rate limit is not a recurring quota; record lifetime trial credits separately.

| Provider / endpoint | API and output | Free allowance | Classification and caveats |
|---|---|---|---|
| TTS.ai | `POST https://api.tts.ai/v1/tts/`; REST JSON API. Its official docs identify free hosted models `piper`, `vits`, `melotts`, and `kokoro`. | Up to 5,000 characters/day per IP, 500 characters/request, free tier 10 RPM and 2 concurrent requests. | `LAYER_1_KEYLESS_DAILY_QUOTA / DOCS_VERIFIED / CANDIDATE_UNTESTED`. Official docs explicitly say anonymous POST requests work without authentication. This is the strongest strict-keyless TTS candidate found in this pass. The free models are neural TTS models; premium models require an account/key. No independent live generation test was run. Confirm current route, audio format, language/voice availability and terms before relying on it. Source: https://tts.ai/api/ |
| Abena AI | `POST https://abena.mobobi.com/playground/api/v1/tts/synthesize/`; returns Base64 WAV. | Current API docs say first 30 requests are free without account/key; another indexed version describes 20 free TTS credits with character-based costs. | `LAYER_1_KEYLESS_TRIAL / CONFLICTED_ALLOWANCE / CANDIDATE_UNTESTED`. Official docs show a complete no-key curl request and actual synthesis response shape, so it is a real API rather than only a playground. The exact trial allowance is inconsistent across the provider's documentation snapshots; it is a finite starter allowance, not a daily/monthly renewable quota. Maximum 500 characters/request; capacity and voice availability can vary. Strong African-language specialization (including Ghanaian English, Twi, Ewe, Hausa, Yoruba, Swahili and Nigerian Pidgin). Sources: https://abena.mobobi.com/playground/sdk/docs/ ; https://abena.mobobi.com/playground/sdk/rate-limits/ ; https://github.com/abenaai/abena-ai-api |

### Layer 1 leads reviewed but not promoted

- **Edge TTS / Microsoft Edge online voices:** community libraries such as `edge-tts` use an undocumented or reverse-engineered Edge Read Aloud WebSocket flow without a conventional API key. This is not a stable, officially published public TTS API with a published free quota; classify as `UNOFFICIAL_PROTOCOL_CLIENT`, not a confirmed independent hosted API. Source: https://github.com/rany2/edge-tts
- **Public Hugging Face Gradio TTS Spaces:** Hugging Face documents public Spaces as callable API endpoints and says unauthenticated access uses a shared pool with stricter limits; ZeroGPU's unauthenticated allowance is platform-level. However, the generic platform documentation does not prove that a particular TTS Space accepts anonymous generation today. Keep individual Spaces as candidates until the exact synthesis endpoint is checked. Source: https://huggingface.co/docs/hub/spaces-api-endpoints
- **KittenTTS Web:** runs locally in the browser or Node.js and generates audio on the user's device. It is not a hosted inference API and therefore does not qualify for this hosted Layer 1 inventory. Source: https://github.com/KittenML/KittenTTS-web
- **Loudness TTS:** local/offline Piper-based runtime and SDK, not a provider-hosted free API. Source: https://github.com/Loudness-ai/loudness-tts

## TTS Layer 2 — recurring / renewable free hosted API quotas

| Provider | Recurring allowance | API access and requirements | Classification / caveats |
|---|---|---|---|
| Speechify API | 500,000 characters every month; free tier pauses until the next monthly reset after the allowance is exhausted. | Hosted TTS API; free plan says no credit card. API supports multiple synthesis endpoints. | `LAYER_2_RECURRING / OFFICIAL`. One of the largest clearly published monthly TTS character allowances found. Free limits: 3 concurrent requests, 1 sustained request/second and burst 10. Current model/language coverage differs: self-serve supports English with Simba 3.2 and six languages with Simba 3.0; broader coverage may require sales. Do not confuse Speechify's consumer reader app with the developer API. Sources: https://speechify.ai/pricing ; https://docs.speechify.ai/build/guides/concepts/api-limits |
| Gradium | 45,000 credits/month; TTS consumes 1 credit/character, approximately 1 hour of speech. Credits are shared across TTS, STT and translation. | Hosted REST/WebSocket API; free account and API key; official API page says no credit card required. | `LAYER_2_RECURRING / OFFICIAL`. Monthly credits expire at month-end; unused credits do not roll over. Free concurrency: 2 TTS requests. Free plan excludes commercial use; paid plans add commercial rights and more concurrency. Sources: https://gradium.ai/pricing ; https://gradium.ai/api |
| Cartesia | 20,000 credits/month on Free; TTS and STT share product credit framework. | Hosted TTS API; account/API key required. | `LAYER_2_RECURRING / OFFICIAL_QUOTA / CARD_STATUS_UNCONFIRMED`. Free plan explicitly includes TTS and 20K monthly credits. Do not assume a no-card rule unless confirmed during signup. Free-plan commercial rights are not included; commercial license appears on Pro. Source: https://www.cartesia.ai/pricing |
| **Fish Audio** | **8,000 points/month**, based on the user's firsthand report: the user has the service installed, actively uses it, and sees this monthly allocation. | Fish Audio hosted TTS service; the user's report confirms practical access to the service, but this document has not independently verified whether all 8,000 points are usable through the public API, the exact point-to-character/audio conversion, or the reset date. | `LAYER_2_USER_REPORTED_RECURRING / FIRSTHAND_USER_CONFIRMATION / API_SCOPE_AND_UNIT_CONVERSION_UNVERIFIED`. Count the 8K monthly points as a user-confirmed recurring service allowance, but do not translate them into characters or minutes and do not claim API eligibility until verified separately. Official site: https://fish.audio/ |
| Google Gemini Developer API — Gemini TTS | Free-of-charge Standard API inference for eligible TTS models, including `gemini-3.8-flash-tts`, `gemini-3.1-flash-tts-preview`, and `gemini-2.5-flash-preview-tts`; model-specific rate limits apply. | API key and eligible Free Tier project required. | `LAYER_2_RECURRING / OFFICIAL_FREE_TIER / QUOTA_MODEL_SPECIFIC`. The official pricing page lists free input and audio output, but does not provide one universal fixed daily character quota in the pricing table; current RPM/TPM/RPD must be checked for the model/project. Google says Free Tier content may be used to improve products, so do not send private or sensitive material. Sources: https://ai.google.dev/gemini-api/docs/pricing ; https://ai.google.dev/gemini-api/docs/rate-limits |
| Google Cloud Text-to-Speech | Monthly: first 4 million characters for Standard voices and first 1 million characters for WaveNet voices. | Hosted REST/gRPC API; Google Cloud project and billing account must be enabled. | `LAYER_2_RECURRING / OFFICIAL / BILLING_ENABLED_REQUIRED`. The allowance renews monthly, but billing must be enabled and over-quota usage is billed. Do not classify as no-card or no-billing. The Gemini TTS product is a separate API/product and should not be merged with these character quotas. Sources: https://cloud.google.com/text-to-speech/pricing ; https://docs.cloud.google.com/text-to-speech/docs/get-started |
| Microsoft Azure AI Speech | 500,000 neural TTS characters/month on Free F0. | Hosted Azure Speech API; Azure subscription/resource and key/region configuration required. | `LAYER_2_RECURRING / OFFICIAL`. Free F0 allowance is recurring monthly; verify current regional availability and resource quota. Card/verification requirements are account-dependent and not asserted here. Source: https://azure.microsoft.com/en-us/pricing/details/speech/ |
| Cloudflare Workers AI — Deepgram Aura-1 | 10,000 Neurons/day shared across Workers AI models and tasks; TTS model `@cf/deepgram/aura-1` is available as a hosted API model. | Cloudflare account, account ID and API token/binding required. | `LAYER_2_RECURRING / OFFICIAL_SHARED_COMPUTE_QUOTA`. Daily reset at 00:00 UTC. This is not 10,000 TTS-specific units: chat, image and other Workers AI inference consume the same daily allocation. Aura-1's published unit price is $0.015/1,000 characters; do not convert the daily Neuron pool into an exact character allowance without the applicable model-unit conversion. Sources: https://developers.cloudflare.com/workers-ai/platform/pricing/ ; https://developers.cloudflare.com/workers-ai/models/aura-1/ |
| Amazon Polly | Free Tier during the first 12 months for eligible new customers: 5 million Standard characters/month, 1 million Neural, 500,000 Long-Form, or 100,000 Generative characters/month. | AWS account and Polly API credentials; AWS Free Tier eligibility applies. | `LAYER_2_TIME_LIMITED_RECURRING / OFFICIAL`. Monthly allowances are time-limited to the first 12 months for new Polly customers, not a permanent free tier. Check AWS account age, current Free Tier rules, region, billing alerts and any general AWS free-trial credit interactions. Sources: https://aws.amazon.com/polly/pricing/ ; https://aws.amazon.com/polly/faqs/ |
| ElevenLabs | Free plan lists 10,000 credits/month shared across products; TTS consumes credits based on characters/model. | Account/API key required for API; free plan and API entitlements are not identical to every feature in the consumer Studio UI. | `LAYER_2_CANDIDATE / API_FREE_PLAN_ELIGIBILITY_PARTLY_UNCLEAR`. Official pricing lists the monthly free credit pool, and ElevenAPI provides TTS endpoints. However, the free plan's product matrix and API feature availability need endpoint-level confirmation; voice library is unavailable to free-tier API users. Free plan is personal-use only; commercial rights require paid plan. Do not count Studio free credits as API credits unless the free key successfully calls the TTS API. Sources: https://elevenlabs.io/pricing ; https://elevenlabs.io/pricing/api ; https://elevenlabs.io/docs/overview/capabilities/text-to-speech |

## TTS Layer 3 — one-time credits and finite trials

| Provider | Trial offer | API scope | Classification / caveats |
|---|---|---|---|
| Deepgram | $200 signup credit, no credit card and no stated expiry. | Deepgram's public pricing includes TTS endpoints (Flux TTS, Aura-2 and Aura-1) as well as STT. | `LAYER_3_TRIAL / OFFICIAL`. The credit is a shared account balance, not a TTS-specific free character quota. Provider examples often express the value in transcription minutes; do not convert that figure into TTS characters without applying the selected TTS model's current rate. Source: https://deepgram.com/pricing |
| Abena AI | Finite no-account TTS starter allowance (see Layer 1). | Hosted TTS API. | Keep its trial value in Layer 1's keyless table because the request itself is anonymous; do not count the same allowance again as a separate provider in Layer 3. Its published trial amount is inconsistent across documentation versions. Source: https://abena.mobobi.com/playground/sdk/docs/ |
| TTS.ai | 15,000 bonus characters after free account signup, in addition to the anonymous daily allowance. | Hosted API; premium models and higher limits require account/key. | `LAYER_3_BONUS / OFFICIAL`. Keep the anonymous 5,000/day allowance in Layer 1; count the 15,000 signup bonus only once here. Source: https://tts.ai/api/ |

## TTS services and offers deliberately not counted as free hosted API quotas

- **FreeTTS:** genuine REST TTS API, but a free account and API key are required. Its free allowance is 5,000 characters/day and 15,000/month, with 5,000 max per request and 10 RPM. Personal/non-commercial only and output carries a spoken FreeTTS tag. This is a valid Layer 2 candidate only if the current free key can use the API; keep it separately marked pending a live key-based request, not Layer 1. Source: https://freetts.org/developers
- **Edge TTS libraries:** unofficial client implementations of Microsoft's Edge Read Aloud protocol are not the same as an officially supported public Microsoft TTS API or quota. Keep them in an unofficial-client appendix, not provider counts. Source: https://github.com/rany2/edge-tts
- **KittenTTS / Piper / Kokoro / MeloTTS local installations:** open-source model runtimes are self-hosted/local inference, not free hosted API offers. A hosted third-party endpoint running one of these models may qualify independently, but the model project itself does not. Sources: https://github.com/KittenML/KittenTTS-web ; https://github.com/rhasspy/piper
- **ElevenLabs free web playground:** web UI credits do not automatically establish API entitlement. Keep API access distinct and test the Free-plan key against the TTS endpoint before upgrading its classification.
- **Google Cloud demo / Try this API page:** browser demonstration is not the API quota; only the monthly Cloud TTS quota above is counted, with billing enabled.
- **Deepgram Playground:** a no-signup playground is not anonymous API access. The API requires account and API key; its $200 account credit belongs in Layer 3.
- **Speechify consumer reader app:** its subscription/app allowance is not the developer API. Only SpeechifyAI's developer API pricing is included.

## TTS research verdict and verification boundary

- Layer 1 currently has one strong documented daily anonymous API candidate (**TTS.ai**) and one finite anonymous trial with inconsistent published allowance (**Abena AI**). Neither was independently live-tested in this pass; keep both below `GENERATION_OK`.
- Layer 2 has several recurring offers: Speechify, Gradium, Cartesia, Google Gemini TTS, Google Cloud TTS, Azure Speech, Cloudflare Workers AI, and Amazon Polly's first-12-month offer, plus Fish Audio's 8,000 monthly points as firsthand user-reported evidence. Fish Audio's point conversion and API applicability remain unverified. Their quota units and conditions differ and must not be added together as if they were one common character pool.
- ElevenLabs is retained as a candidate until Free-plan API entitlement is directly confirmed; do not assume its website credits are automatically usable through API.
- FreeTTS is a key-required candidate, not keyless. Deepgram is a one-time credit offer, not a recurring free quota.
- No live API generation requests, account registrations, card entries or phone/identity checks were performed in this research pass. `DOCS_VERIFIED` means the provider's published documentation was reviewed; it does not mean the API was executed successfully.

### TTS official source register

- TTS.ai API and authentication: https://tts.ai/api/
- Abena AI API docs: https://abena.mobobi.com/playground/sdk/docs/
- Abena AI rate limits: https://abena.mobobi.com/playground/sdk/rate-limits/
- Hugging Face Spaces API: https://huggingface.co/docs/hub/spaces-api-endpoints
- Speechify API pricing: https://speechify.ai/pricing
- Speechify API limits: https://docs.speechify.ai/build/guides/concepts/api-limits
- Gradium pricing: https://gradium.ai/pricing
- Gradium API: https://gradium.ai/api
- Cartesia pricing: https://www.cartesia.ai/pricing
- Gemini API pricing: https://ai.google.dev/gemini-api/docs/pricing
- Gemini API rate limits: https://ai.google.dev/gemini-api/docs/rate-limits
- Google Cloud TTS pricing: https://cloud.google.com/text-to-speech/pricing
- Google Cloud TTS setup: https://docs.cloud.google.com/text-to-speech/docs/get-started
- Azure Speech pricing: https://azure.microsoft.com/en-us/pricing/details/speech/
- Cloudflare Workers AI pricing: https://developers.cloudflare.com/workers-ai/platform/pricing/
- Cloudflare Deepgram Aura-1 model: https://developers.cloudflare.com/workers-ai/models/aura-1/
- Amazon Polly pricing: https://aws.amazon.com/polly/pricing/
- Amazon Polly FAQ: https://aws.amazon.com/polly/faqs/
- ElevenLabs pricing: https://elevenlabs.io/pricing
- ElevenLabs API pricing: https://elevenlabs.io/pricing/api
- ElevenLabs TTS docs: https://elevenlabs.io/docs/overview/capabilities/text-to-speech
- Deepgram pricing: https://deepgram.com/pricing
- FreeTTS API: https://freetts.org/developers


# Section 4 — Cross-provider service audit and expanded TTS inventory (23 November 2026)

This update addresses a recurring inventory problem: a provider first discovered for one capability may expose several other APIs. The provider must be recorded once as a company/platform, then cross-referenced in every relevant category. Do not count the same provider as several independent providers, and do not assume that every endpoint or model inherits the same free tier.

## 4.1 Logfare.ai — multi-service provider audit

**Logfare is a genuine multi-service API gateway, not just an LLM endpoint.** Its official API documentation currently lists OpenAI-compatible endpoints for chat/responses/messages, image generation and editing, text-to-speech, speech-to-text transcription, embeddings, and video generation. It requires a registered Logfare account and API key; the account must remain a member of Logfare's Discord server to retain access. This is therefore **not Layer 1** and must not be described as keyless or anonymous. Sources: https://logfare.ai/docs ; https://logfare.ai/ ; https://logfare.ai/models

| Capability | Official endpoint / current model evidence | Free access status | Inventory decision |
|---|---|---|---|
| Image generation | `POST /v1/images/generations`; the live model catalogue currently shows `sdxl-lightning` as `images/generations` **Free**. Other listed image models (e.g. Leonardo Lucid Origin and Phoenix 1.0) are Premium-gated. | Standard account tier is free; SDXL Lightning currently appears in the free model catalogue. New accounts have a lower first-24-hour request budget. | **Include in image generation Layer 2 (free account/key, fair-use request limits)**, but pin the model ID and re-check `/models` because model access changes. Image editing is a separate endpoint and only works for models that advertise `images/edits`; do not infer free editing from free generation. |
| Text-to-speech | `POST /v1/audio/speech`; live catalogue currently lists `aura-2-en` (Deepgram Aura 2) under TTS as **Premium / opt-in to unlock**. | Not part of the default Standard/free model set in the current catalogue. Premium unlock requires opting into model training. | **Do not list as ordinary free TTS.** Put in a gated/consent-required appendix until a standard/free TTS model is actually listed. |
| Speech-to-text | `POST /v1/audio/transcriptions`; current catalogue lists `nova-3` and `whisper-large-v3-turbo` as **Premium / opt-in to unlock**. | Not default Standard access in the current catalogue. Premium unlock requires training opt-in. | **Do not list as ordinary free STT.** Keep as a conditional premium model, not a recurring free quota. |
| Video generation | `POST /v1/videos/generations` is documented, but endpoint existence alone does not establish a free model. | Current model availability and tier must be checked in `/models`. | Cross-reference only; do not add to free video inventory without a currently listed Standard/Free video model. |

**Important Logfare caveats:**
- Its docs say all three tiers are free in monetary price, but Premium requires consent to model training and Pro requires consent to both training and data sale. “Free tier” does not mean every model is available without a privacy trade-off.
- The free Standard tier has fair-use request limits: a new account starts at 10 requests/minute, 200/hour and 500/day for its first 24 hours; the regular Standard account schedule is 40/minute, 1,000/hour and 5,000/day. These budgets are shared across all unlocked models/endpoints, not a separate pool for each model. Shared network limits also apply.
- Logfare says API traffic is logged for research/data purposes. Read its Privacy Policy and Terms before sending personal, private, or sensitive content. Do not opt into training or data sale merely to unlock a model without understanding those choices.
- `/v1/models` is public, but a public model-list response is not proof that a synthesis/generation request is authorized or succeeds. Verify the model's `endpoints`, `tier`, `premium_unlocked`, and `requires_training_optin` / `requires_data_sale_optin` fields with the user's own account.
- No live Logfare inference request was executed in this research pass. Status: `DOCS_AND_LIVE_CATALOGUE_REVIEWED / NOT_LIVE_GENERATION_TESTED`.

## 4.2 Additional TTS providers and corrections

### Layer 1 — strict anonymous/keyless hosted TTS

No additional provider was promoted to Layer 1 in this pass. The current Layer 1 candidates remain TTS.ai and Abena AI, with their previously stated verification caveats. A provider having a free plan, public model list, or browser demo is not enough to qualify as anonymous API access.

### Layer 2 — recurring or continuously available free API access

| Provider | Additional service coverage | Free API allowance / access | Classification and caveats |
|---|---|---|---|
| Groq — Orpheus TTS | TTS plus Whisper STT (already a cross-service provider). | Official TTS API supports `canopylabs/orpheus-v1-english` and `canopylabs/orpheus-arabic-saudi`; request text is capped at 200 characters. Groq publishes model-specific free Developer-plan rate limits (Orpheus: 10 RPM, 100 RPD; Whisper models: 20 RPM, 2,000 RPD, 7,200 audio seconds/hour and 28,800/day). The model pricing page also publishes paid per-character rates, so do not interpret rate-limit tables as a separate character grant. | `LAYER_2_FREE_DEVELOPER_ACCESS / MODEL_RATE_LIMITED / ACCOUNT_KEY_REQUIRED`. Include as a free rate-limited API candidate, not as an unlimited free quota. Arabic coverage is specifically Saudi dialect, not general Libyan Arabic. Confirm current free-plan model access in the Groq console. Sources: https://console.groq.com/docs/text-to-speech/orpheus ; https://console.groq.com/docs/rate-limits ; https://console.groq.com/docs/models |
| Speechmatics TTS | TTS and STT. | Official pricing page states the first 1,000,000 TTS characters are free; it also advertises $100 signup credits for the Speechmatics platform. One credit balance covers STT, add-ons and TTS. The page does not present the 1M characters as a monthly renewable allowance. | `LAYER_3_TRIAL_OR_STARTER_ALLOWANCE / SHARED_CREDIT_BALANCE`. Do not promote to recurring Layer 2. The 1M-character statement and signup-credit balance may overlap; do not add them together without confirmation. API key/account required. Sources: https://www.speechmatics.com/pricing |
| TTS.ai — expanded cross-service coverage | TTS, STT, voice cloning, voice changer, audio enhancement, vocal removal/stem splitting, speech translation, voice chat, plus free audio conversion and key/BPM tools. | Current official pricing page says 15,000 free characters/month plus 15,000 signup bonus characters; free account includes 5 minutes of STT. Anonymous TTS separately allows 5,000 characters/day per IP. The free account also has an OpenAI-compatible REST API. STT consumes 2,000 credits/minute; do not convert this into characters. | TTS remains Layer 1 for anonymous requests and Layer 2 for the account's 15K monthly character allowance. STT is included in the free account, but its 5-minute quantity is not clearly described as a monthly renewal; mark `STT_ALLOWANCE_RESET_UNCLEAR`, not recurring. The official pricing page supersedes the older 10K/month figure recorded earlier. Do not count the same provider twice in aggregate provider totals. Sources: https://tts.ai/api/ ; https://tts.ai/pricing/ ; https://tts.ai/speech-to-text/ |

### Layer 3 — additional finite trials / credits

| Provider | TTS / related free offer | Conditions |
|---|---|---|
| Speechmatics | First 1M TTS characters free and $100 signup credits on its platform. | Shared credit balance with STT and add-ons; the free TTS characters should not be treated as recurring monthly quota. Confirm whether the 1M-character offer is included within or additional to the signup balance before calculating total free usage. Source: https://www.speechmatics.com/pricing |

## 4.3 Cross-category provider map — do not duplicate provider records

This is a cross-reference index, not a claim that every feature is free. The category-specific sections remain the authoritative place for quota and tier details.

| Provider / platform | TTS | STT | Image generation | Other relevant services | Free-access interpretation |
|---|---|---|---|---|---|
| **Logfare.ai** | Yes; current Aura 2 model is Premium-gated | Yes; current Nova-3 and Whisper Turbo are Premium-gated | Yes; SDXL Lightning currently listed Free | Chat, embeddings, video endpoint | API key + Discord membership; standard free account. Only the currently Free image model is a clear default-free media generation entry. TTS/STT require training opt-in at present. |
| **TTS.ai** | Yes; anonymous daily and monthly free account quotas | Yes; 5-minute free plan allowance | No image-generation endpoint evidenced in the current API docs | Voice cloning, voice changer, audio enhancement, stem splitting, translation, voice chat | Strong cross-audio provider; TTS has documented keyless access. STT free allowance exists but reset terms need clarification. |
| **Groq** | Yes; Orpheus English and Saudi Arabic | Yes; Whisper Large v3 / Turbo | No first-party image generation endpoint evidenced | LLM inference | Account/API key and free Developer-plan model limits; TTS request cap 200 characters. |
| **Cartesia** | Yes | Yes; Ink-2 | No image generation evidenced | Voice agents / voice design | 20,000 credits/month shared across TTS and STT; current STT page estimates up to 111 minutes/month. |
| **Gradium** | Yes | Yes | No image generation evidenced | Voice design / translation | 45,000 monthly credits shared across audio services. |
| **Speechmatics** | Yes | Yes | No image generation evidenced | Speech add-ons | $100 signup credits; 1M TTS characters free claim; shared balance, not a recurring quota. |
| **Deepgram** | Yes | Yes | No image generation evidenced | Voice-agent / real-time audio stack | $200 one-time signup credit shared across products; Layer 3. |
| **Cloudflare Workers AI** | Yes; MeloTTS and Aura-1 | Yes; hosted transcription models available | Yes; hosted image models are in the Workers AI catalogue | LLM inference, embeddings, audio/image models | 10,000 Neurons/day shared across all Workers AI workloads; never describe it as 10,000 TTS or image credits. |
| **Scaleway Generative APIs** | No TTS free offer established in this audit | Yes; Whisper transcription | No free image generation established in this audit | LLM/embedding inference | Free Tier includes 60 minutes of audio transcription and 1M tokens; overage becomes billable. |
| **AssemblyAI** | TTS endpoint exists, but it is billed | Yes | No image generation evidenced | Speech understanding, realtime/voice-agent features | $50 trial credits for audio transcription; do not treat TTS as free just because STT has trial credits. |
| **Gladia** | No TTS offer evidenced | Yes | No image generation evidenced | Translation, diarization, audio intelligence | €50 one-time credit valid one year; STT-focused. |
| **Speechify** | Yes | No qualifying STT API offer established in this audit | No image generation evidenced | Voice / reader products | 500K monthly TTS characters on its developer free plan; do not infer other API categories from its consumer app. |
| **Google** | Gemini TTS and Cloud TTS | Cloud Speech-to-Text | Gemini API image-generation models are not currently a free API offer in the reviewed material | Gemini text/vision models | Keep Gemini TTS, Cloud TTS and Cloud STT as separate products with separate quotas and billing conditions. |
| **Amazon AWS** | Polly | Transcribe | No qualifying free image API offer established in this audit | Other AWS AI services | Polly and Transcribe are time-limited first-year offers; separate service-specific free tiers. |

## 4.4 Additional STT providers discovered for the upcoming STT category

These are recorded now to prevent overlooking multi-service providers when the dedicated STT phase is expanded. Do not count them as recurring free plans unless the source explicitly says the allowance renews.

- **Groq Whisper:** hosted `/audio/transcriptions` API, `whisper-large-v3` and `whisper-large-v3-turbo`; published free Developer-plan limits are 20 RPM, 2,000 RPD, 7,200 audio seconds/hour and 28,800/day. API key required. This is a recurring rate-limited free access path, not a separate monthly minutes grant. Source: https://console.groq.com/docs/rate-limits
- **AssemblyAI:** free account allows up to $50 of audio processing; official support page says pre-recorded `/v2/transcript` and streaming STT are available on the free tier. This is a finite trial balance, not a monthly quota. No credit card is required to start according to the current pricing/support pages. Sources: https://www.assemblyai.com/pricing ; https://support.assemblyai.com/articles/5370767329-can-i-sign-up-for-free
- **Speechmatics:** $100 signup credits, shared across STT, add-ons and TTS; free TTS character offer is not a separate renewable pool. Source: https://www.speechmatics.com/pricing
- **Gladia:** €50 one-time credits, valid one year, for asynchronous and real-time transcription; no monthly reset. Source: https://www.gladia.io/pricing ; https://support.gladia.io/article/credit-based-billing
- **Scaleway Generative APIs:** 60 minutes of audio transcription in its free tier, plus 1M tokens for token-billed models. The FAQ says usage beyond the free tier is billed; check billing controls before use. Source: https://www.scaleway.com/en/docs/generative-apis/faq/
- **Cartesia Ink-2:** 20,000 free monthly credits shared with TTS; transcription costs 3 credits/second, giving approximately 111 minutes if the entire monthly pool is spent on STT. Supported languages on the STT API page are English, Spanish, French, Hindi and Japanese. Source: https://www.cartesia.ai/speech-to-text-api ; https://www.cartesia.ai/pricing
- **Google Cloud Speech-to-Text:** first 60 minutes/month free on listed SKUs; Google Cloud project/billing setup applies. This is distinct from Google Cloud Text-to-Speech and Gemini TTS. Source: https://cloud.google.com/speech-to-text/pricing
- **Amazon Transcribe:** 60 free minutes/month for the first 12 months for eligible new customers; time-limited AWS Free Tier. Source: https://aws.amazon.com/transcribe/pricing/

## 4.5 Research and verification notes

- The new additions above are documentation/catalogue-verified, not live generation-tested. No `GENERATION_OK` label is assigned.
- For every multi-service provider, inspect its current model catalogue and per-model tier. A platform's free account does not imply every API endpoint or model is free.
- Do not add monthly quotas, daily request limits, shared compute units, and one-time credits into one combined number. Keep their units and reset rules separate.
- Do not infer STT access from a TTS API or image generation from a model directory. Require an endpoint plus a currently eligible model and a stated free allowance.
- Logfare's model catalogue is dynamic. Recheck it immediately before integration, especially the `tier`, `premium_unlocked`, and consent flags.


## TTS research continuation — additional providers and corrections (23 November 2026)

This continuation closes several gaps in the initial TTS pass. It prioritizes providers with explicit API endpoints and free entitlements, and separates monthly free usage from one-time signup credits.

### Additional TTS Layer 2 — recurring free API access

| Provider | Free allowance | API scope / access | Classification and caveats |
|---|---|---|---|
| **Hume AI — Octave TTS** | 10,000 characters/month (about 10 minutes), plus 5 minutes/month of EVI speech-to-speech. Free plan shows 15 RPM and one concurrent connection. | Hosted TTS API; account required. Hume pricing lists monthly included characters and a free $0 plan. | `LAYER_2_RECURRING / OFFICIAL_QUOTA`. The 5 EVI minutes are speech-to-speech/voice interaction, not plain STT minutes; do not classify them as transcription. Free tier has no published overage amount on the free row; do not assume overages are automatically free. Check the current API key/product access and terms. Source: https://www.hume.ai/pricing |
| **TTS.ai account tier — corrected** | 15,000 characters/month plus a separate 15,000 signup bonus characters; free models cost 1 credit/character. The 5,000/day anonymous route remains separate. | OpenAI-compatible REST API is documented on all plans, including Free; account key required for the monthly pool. | `LAYER_2_RECURRING / OFFICIAL_QUOTA`, plus `LAYER_3_SIGNUP_BONUS`. Unused characters roll over indefinitely according to the current pricing FAQ. The anonymous daily route and account monthly quota are separate access modes; avoid summing them into one guaranteed daily/monthly amount. Source: https://tts.ai/pricing/ |

### Additional TTS Layer 3 — one-time account credits

| Provider | Trial / credit | API scope | Classification and caveats |
|---|---|---|---|
| **Sarvam AI — Bulbul TTS** | ₹100 worth of universal credits per verified user on signup; credits never expire. At current pay-as-you-go rates, Bulbul v4 Flash is ₹1/1,000 characters and Bulbul v3 is ₹3/1,000 characters. | REST, HTTP streaming and WebSocket TTS; API key/account. | `LAYER_3_OFFICIAL_CROSS_API_CREDIT`. This is not a recurring TTS-only character quota: the same ₹100 balance is shared across STT, TTS, translation and other Sarvam APIs. Verification is required; do not equate verified-user onboarding with no identity checks. Commercial-production rights need separate review. Sources: https://docs.sarvam.ai/api/getting-started/pricing ; https://www.sarvam.ai/try/text-to-speech |
| **Hume AI — signup credit** | A free account starts on the $0 tier; specialist trackers report an additional $20 credit, but the current official pricing table confirms the monthly 10K TTS characters and does not clearly show the $20 grant. | TTS and EVI speech-to-speech APIs. | `TRACKER_REPORTED / CREDIT_AMOUNT_NOT_CONFIRMED_ON_CURRENT_OFFICIAL_PRICING`. Do not add $20 to the confirmed free allowance until the dashboard or official onboarding confirms it. The 10K monthly TTS quota above is independently official. Source: https://www.hume.ai/pricing |

### TTS candidates retained but not promoted

- **IBM Watson Text to Speech Lite:** older articles and directories mention a 10,000-character/month Lite plan. This research pass did not establish a current, generally claimable Lite API entitlement from IBM's current pricing/onboarding material. Keep `HISTORICAL_OR_UNCONFIRMED`; do not count it as an active provider until IBM confirms the present Lite plan and API access.
- **PlayHT / PlayAI:** TTS API exists, but no current free recurring API allowance was confirmed from provider-owned pricing evidence in this pass. Do not mistake a web demo or temporary promotion for an API quota.
- **Fish Audio:** the user reports firsthand that they have Fish Audio installed, actively use it, and receive 8,000 points/month. Promote it from an unverified discovery lead to the TTS Layer 2 user-reported recurring allowance. The exact points-to-characters/audio conversion, monthly reset timing, and whether the full allocation is available through the public API remain unverified; do not label the API quota `OFFICIAL_QUOTA` or claim a live API test.
- **Hume EVI:** speech-to-speech minutes are a voice-agent interaction product, not a raw audio-to-text transcription API. Keep separate from STT minutes.

### TTS revised verdict

- Strict keyless Layer 1 remains TTS.ai (5,000 characters/day/IP) and Abena AI (finite anonymous trial, allowance conflict). Hume and Sarvam require account/API access and do not qualify for Layer 1.
- Recurring Layer 2 is expanded by Hume AI (10K TTS characters/month), the corrected TTS.ai account quota (15K/month), and Fish Audio (8,000 monthly points, firsthand user-reported; API applicability and unit conversion still unverified). Existing Speechify, Gradium, Cartesia, Gemini TTS, Google Cloud TTS, Azure Speech, Cloudflare Workers AI and Amazon Polly entries remain subject to their earlier conditions.
- Layer 3 now includes Sarvam's ₹100 shared API credit. Hume's reported $20 extra credit remains unconfirmed and is not counted.
- No live TTS generation was performed in this continuation. These are documentation-based classifications, not `GENERATION_OK` results.

### New TTS official sources

- Hume AI pricing: https://www.hume.ai/pricing
- TTS.ai current pricing and API quota: https://tts.ai/pricing/
- Sarvam API pricing and universal credits: https://docs.sarvam.ai/api/getting-started/pricing
- Sarvam TTS product: https://www.sarvam.ai/try/text-to-speech

---

# Cross-provider audit correction — TTS models and shared compute (23 November 2026)

- **Groq Orpheus:** retain as Layer 2 free Developer-plan access only within the published model-specific request limits. The official endpoint is `https://api.groq.com/openai/v1/audio/speech`; maximum input is 200 characters and output is WAV. Arabic model `canopylabs/orpheus-arabic-saudi` is specifically Saudi Arabic, not a promise of Libyan dialect quality. Official docs list paid per-character prices; free access depends on the active Developer-plan limits and account eligibility. Sources: https://console.groq.com/docs/text-to-speech/orpheus ; https://console.groq.com/docs/rate-limits
- **Cloudflare Workers AI:** the free allowance is 10,000 Neurons/day shared across all eligible Workers AI tasks, not a TTS-only balance. The previously listed MeloTTS model is deprecated (20 November 2026); keep it as historical/transition-only and check the live catalogue for currently supported speech models. Sources: https://developers.cloudflare.com/workers-ai/platform/pricing/ ; https://developers.cloudflare.com/ai/models/%40cf/myshell-ai/melotts/
- **Do not add TTS.ai, Abena AI or Groq as confirmed live-working solely from documentation.** Their entries remain below `GENERATION_OK` unless an actual audio response is saved and played.
