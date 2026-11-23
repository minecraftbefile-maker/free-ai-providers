# Speech-to-Text (STT) — Hosted APIs

> Speech recognition/transcription APIs only. Browser transcription tools and local Whisper installations are not hosted API quotas.

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

# Section 5 — Speech-to-Text (STT) API research — initial deep-dive (23 November 2026)

**Scope:** Hosted speech-recognition/transcription APIs that accept recorded audio or live audio and return text. Keep speech-to-speech agents, audio understanding, browser transcription UI, and local models separate unless the provider offers an actual callable STT endpoint. Provider entries may overlap with TTS, but free balances must be counted once per account and shared pools must be labeled.

**Research allocation:** Layer 1 receives approximately 50% of discovery effort, Layer 2 approximately 40%, and Layer 3 approximately 10%. This is the opening STT pass; continue discovery before treating the category as closed.

## STT Layer 1 — strict keyless / anonymous hosted APIs

**Finding so far:** no STT endpoint in the current evidence set qualifies as a confirmed strict-keyless hosted API. Public transcription web pages and no-signup playgrounds are not enough: the exact API request must work without an account, key, placeholder credential, cookie or browser identity. TTS.ai's transcription interface is a website feature, while its documented API key is generated from an account; this does not qualify for strict Layer 1.

| Candidate | Why not promoted | Status |
|---|---|---|
| TTS.ai web transcription | Public web UI exists, but the current free API plan describes an account/key workflow; no anonymous API route for STT was established. | `LAYER_1_NOT_CONFIRMED` |
| Hugging Face public ASR Spaces | Spaces can expose callable endpoints, but no specific STT Space's exact anonymous endpoint and successful transcription were established in this pass. | `CANDIDATE_UNTESTED` |
| Public Whisper demos / browser tools | UI access is not proof of an anonymous hosted API endpoint. | `EXCLUDED_FROM_API_COUNT` |

## STT Layer 2 — recurring / renewable free hosted API access

| Provider | Free allowance / limits | API access and requirements | Classification / caveats |
|---|---|---|---|
| **Groq — Whisper Large v3 / Turbo** | Published free Developer-plan caps: 20 RPM, 2,000 requests/day, 7,200 audio seconds/hour and 28,800 audio seconds/day per listed Whisper model. | Hosted `/audio/transcriptions` API; account/API key. Maximum file size is 25 MB on free tier according to the STT docs. | `LAYER_2_FREE_RATE_LIMITED / OFFICIAL`. These are rate/usage ceilings, not a monthly audio-minute grant. Do not multiply request and audio caps or imply unlimited daily use. Multilingual Whisper models support transcription; model choice changes accuracy/speed. Sources: https://console.groq.com/docs/speech-to-text ; https://console.groq.com/docs/rate-limits |
| **Cartesia — Ink-2** | 20,000 credits/month shared with TTS. Ink-2 costs 3 credits/second, equivalent to about 111 minutes/month if the entire pool is used for STT. | Hosted batch endpoint and real-time WebSocket API; account/API key. | `LAYER_2_RECURRING / OFFICIAL_SHARED_CREDIT_POOL`. Free plan explicitly includes STT and TTS. Ink-2 language list currently states English, Spanish, French, Hindi and Japanese; it does not list Arabic. Source: https://www.cartesia.ai/pricing ; https://www.cartesia.ai/speech-to-text-api |
| **Google Gemini Developer API — Transcribe** | Current Gemini pricing lists `gemini-3.5-transcribe` and `gemini-3.5-transcribe-live` with Free Tier input/output at $0; model/project rate limits apply. | Gemini API key and eligible Free Tier project; live transcription uses WebSocket. | `LAYER_2_FREE_TIER / OFFICIAL / MODEL_RATE_LIMITED`. Google states free-tier content may be used to improve products. The pricing page does not give one universal monthly audio-minute quota; check exact model limits in the account. Sources: https://ai.google.dev/gemini-api/docs/pricing/ ; https://ai.google.dev/gemini-api/docs/rate-limits |
| **Google Cloud Speech-to-Text V1** | First 60 minutes/month free for the listed standard recognition SKU with data logging; the pricing page also shows 60 minutes free for the no-data-logging standard SKU. | Hosted API; Google Cloud project and billing configuration. | `LAYER_2_RECURRING / OFFICIAL / BILLING_SETUP_REQUIRED`. This is a monthly account-level price allowance, not an anonymous API. Billing setup and overage exposure must be checked; data-logging and privacy terms differ by SKU. Do not confuse with Gemini Transcribe. Source: https://cloud.google.com/speech-to-text/pricing |

## STT Layer 3 — one-time credits and finite trials

| Provider | Free offer | API scope | Classification / caveats |
|---|---|---|---|
| **Deepgram** | $200 signup credit, no card required and no stated expiry on official pricing. | Hosted STT (Nova, Flux) and TTS/voice-agent APIs. | `LAYER_3_OFFICIAL_TRIAL / SHARED_CREDIT`. The credit is shared across Deepgram speech products; it is not a dedicated STT-hours quota. Source: https://deepgram.com/pricing |
| **AssemblyAI** | Up to $50 in audio-processing credit on the free tier; official support confirms prerecorded `/v2/transcript` and streaming STT endpoints are available. | Hosted prerecorded and streaming STT; account/API key. | `LAYER_3_OFFICIAL_TRIAL`. Official support says no card is required to start; API access pauses after the $50 balance is consumed unless the account is upgraded. This is a finite trial, not a recurring quota. Sources: https://www.assemblyai.com/pricing/ ; https://support.assemblyai.com/articles/5370767329-can-i-sign-up-for-free |
| **Speechmatics** | $100 signup credits; pricing also states first 1 million TTS characters free. Credits last 12 months according to the current pricing page. | Hosted prerecorded and real-time STT; shared balance covers STT, add-ons and TTS. | `LAYER_3_OFFICIAL_TRIAL / SHARED_CREDIT`. Do not count TTS's first-million-character offer as STT minutes, and do not add it to the signup balance without confirming whether the offers overlap. Free concurrency currently 2 real-time sessions. Source: https://www.speechmatics.com/pricing |
| **Gladia** | €50 one-time credit, valid one year according to current specialist documentation; provider pricing supports pay-as-you-go transcription. | Hosted asynchronous and real-time transcription API. | `LAYER_3_REPORTED_OFFICIAL_CREDIT / VERIFY_IN_DASHBOARD`. Keep as finite credit, not recurring quota. Confirm current amount, expiry and country eligibility on provider onboarding before relying on it. Sources: https://www.gladia.io/pricing ; https://support.gladia.io/article/credit-based-billing |
| **Scaleway Generative APIs** | 60 minutes of audio transcription in its Serverless Free Tier, plus 1,000,000 tokens for token-billed models. | Hosted `/v1/audio/transcriptions` endpoint; API key and Scaleway account. | `LAYER_3_OR_FREE_TIER_ALLOCATION / OFFICIAL`. The free allowance is a finite included allocation, not a monthly renewal unless the current account console explicitly says so. Usage beyond the free tier is billed. Source: https://www.scaleway.com/en/docs/generative-apis/faq/ |
| **Amazon Transcribe** | 60 minutes/month for the first 12 months, beginning with the first transcription request. | Hosted AWS Transcribe API; AWS account/credentials. | `LAYER_2_TIME_LIMITED_RECURRING / OFFICIAL`. This belongs in Layer 2 because it renews monthly during the first 12 months, but it is time-limited and unused minutes do not roll over. Source: https://aws.amazon.com/transcribe/pricing/ |
| **Sarvam AI — Speech to Text** | ₹100 universal credits per verified user on signup; credits never expire. | Hosted real-time, streaming and batch STT API. | `LAYER_3_OFFICIAL_CROSS_API_CREDIT`. Same credit pool is shared with Bulbul TTS and other Sarvam APIs. API pricing lists ₹0.49/minute for standard STT and ₹0.59/minute for diarization on Pay-as-you-go. Verification required. Source: https://docs.sarvam.ai/api/getting-started/pricing |
| **TTS.ai account STT** | Free account includes 5 minutes of STT; pricing table does not clearly say whether this is monthly recurring or a one-time cap. STT costs 2,000 credits/minute. | Account/API key required; separate STT endpoint/model. | `LAYER_2_CANDIDATE / RESET_UNCLEAR`. Do not call it a monthly recurring quota. Keep the provider's 15K monthly TTS characters separate from its 5-minute transcription allowance. Source: https://tts.ai/pricing/ |

## STT cross-category and modality cautions

- **Hume AI EVI:** its free plan includes 5 minutes/month of speech-to-speech interaction. This is not equivalent to a raw transcription API or standalone STT quota. Keep in a voice-agent appendix unless Hume documents a distinct STT endpoint and entitlement. Source: https://www.hume.ai/pricing
- **Deepgram:** one provider across STT, TTS, voice agents and audio intelligence. Its $200 credit is shared; do not count four separate trial offers.
- **Speechmatics:** TTS and STT consume the same credit balance. The free TTS character offer is not an independent STT allowance.
- **Cartesia:** one monthly pool covers TTS and STT. Spending all 20K credits on one modality leaves none for the other.
- **Google:** Gemini Transcribe and Cloud Speech-to-Text are separate products with separate free terms, billing paths and data-use policies.
- **Amazon:** Polly and Transcribe have distinct first-year Free Tier allocations. They are separate APIs but still share the AWS account's billing configuration.
- **Scaleway:** its 60 transcription minutes are a Serverless Free Tier allowance; do not present the accompanying 1M LLM tokens as STT quota.

## STT initial findings and verification boundary

- No confirmed strict-keyless Layer 1 STT API has been found in this opening pass. Continue searching exact public endpoints, especially provider-operated anonymous routes and specific public Spaces, but do not promote UI demos.
- Layer 2 recurring access currently includes Groq's free rate-limited Whisper API, Cartesia's monthly shared credits, Gemini Transcribe's free model tier, Google Cloud's 60-minute monthly price allowance, and Amazon Transcribe's first-year monthly allowance.
- Layer 3 finite balances include Deepgram, AssemblyAI, Speechmatics, Gladia and Sarvam; Scaleway's 60-minute allocation is included as a finite/free-tier allocation pending clearer renewal language.
- TTS.ai has a 5-minute STT free-plan allowance, but the reset period is not sufficiently clear. Keep it as a candidate, not a confirmed recurring quota.
- No live transcription request, account registration, payment-card entry or identity verification was performed. All classifications are based on provider-owned documentation/pricing where available; Gladia's credit expiry and some account eligibility details remain to be reconfirmed in the provider dashboard.

### STT official source register

- Groq STT API: https://console.groq.com/docs/speech-to-text
- Groq rate limits: https://console.groq.com/docs/rate-limits
- Cartesia pricing: https://www.cartesia.ai/pricing
- Cartesia Ink-2 STT: https://www.cartesia.ai/speech-to-text-api
- Gemini API pricing: https://ai.google.dev/gemini-api/docs/pricing/
- Gemini API rate limits: https://ai.google.dev/gemini-api/docs/rate-limits
- Google Cloud STT pricing: https://cloud.google.com/speech-to-text/pricing
- Deepgram pricing: https://deepgram.com/pricing
- AssemblyAI pricing: https://www.assemblyai.com/pricing/
- AssemblyAI free tier details: https://support.assemblyai.com/articles/5370767329-can-i-sign-up-for-free
- Speechmatics pricing: https://www.speechmatics.com/pricing
- Gladia pricing: https://www.gladia.io/pricing
- Gladia credits: https://support.gladia.io/article/credit-based-billing
- Scaleway Generative APIs FAQ: https://www.scaleway.com/en/docs/generative-apis/faq/
- Amazon Transcribe pricing: https://aws.amazon.com/transcribe/pricing/
- Sarvam API pricing: https://docs.sarvam.ai/api/getting-started/pricing
- TTS.ai pricing: https://tts.ai/pricing/
- Hume AI pricing: https://www.hume.ai/pricing

# Section 6 — Reddit community review: TTS and STT provider experience (23 November 2026)

**Purpose:** add practitioner/community observations to the provider research without treating Reddit comments as proof of free API entitlement, official quota, licensing, or uptime. Reddit evidence is qualitative and anecdotal. Votes and comment counts are small, discussions may contain vendor promotion, and comments may describe local software or browser features rather than a hosted API. Provider pricing and API eligibility remain governed by the official-source sections above.

## 6.1 TTS — recurring themes from Reddit

| Theme / candidate | What Reddit users reported | How to use this evidence in the provider inventory |
|---|---|---|
| Naturalness vs cost | A recent r/TextToSpeech discussion describes a gap between cheap inference and natural-sounding speech; users still find affordable, consistently expressive TTS difficult. Kokoro is repeatedly suggested, but local hosting is a barrier for some. | Treat voice quality, pronunciation, prosody and long-form consistency as separate evaluation criteria. Do not infer that a model is a hosted API or that its local weights come with a free hosted endpoint. Source: https://www.reddit.com/r/TextToSpeech/comments/1xxj6jr/is_anyone_else_frustrated_with_the_current_state/ |
| Hosted API alternatives | Comments mention Unreal Speech hosting Kokoro, Murf Falcon, Deepgram Aura and Fish Audio as alternatives; the thread itself does not establish free-tier quotas for these services. | Add as discovery leads only. Verify each product's official API endpoint and free allowance independently; do not promote paid price-per-million-character discussion into free tiers. Source: https://www.reddit.com/r/tts/comments/1xxj645/is_anyone_else_frustrated_with_the_current_state/ |
| Browser read-aloud | Users suggest Microsoft Edge Read Aloud and device/browser reading features as zero-cost workarounds. | Keep these outside hosted API inventory: browser/OS read-aloud is not evidence of a supported public TTS API, server-side generation endpoint, or downloadable audio API. Source: https://www.reddit.com/r/TextToSpeech/comments/1xkfg9q/where_can_i_get_a_free_tts_without_having_to/ |
| Local model quality | A CPU comparison reports Kokoro 82M as the strongest naturalness option among the compared small local models, while Supertonic 3 is faster; the author notes licensing differences. | Preserve in a separate self-hosted appendix. Hardware, runtime, license and language coverage must be checked before recommending; it is not a hosted free API. Source: https://www.reddit.com/r/TextToSpeech/comments/1udgi9s/open_source_tts_comparison_kokoro_82m_vs/ |
| Practical integration | A voice-app discussion warns that running real-time STT, TTS and the application on one small free server can create CPU contention, cold starts and latency. | For app architecture, separate hosted API evaluation from local/server resource evaluation. Measure time-to-first-audio and p95 latency, not just whether one sample completes. Source: https://www.reddit.com/r/PythonLearning/comments/1vv9vib/any_free_stttts_apis_for_a_voice_ai_app/ |

**TTS Reddit conclusion:** Reddit does not reveal a new, well-evidenced anonymous hosted TTS API with a dependable recurring free quota in this review. The strongest community signal is about quality/cost trade-offs and local Kokoro/Qwen-family options, not new free API entitlements. Browser read-aloud and local models must remain separately classified.

## 6.2 STT — recurring themes from Reddit

| Theme / candidate | What Reddit users reported | How to use this evidence in the provider inventory |
|---|---|---|
| Groq + Whisper | Several discussions recommend Groq-hosted Whisper for fast, inexpensive/free API transcription. Reports are positive but anecdotal and do not independently establish current quotas. | Keep Groq in Layer 2 only on the strength of Groq's official free rate limits; Reddit adds a positive usability signal, not quota proof. Sources: https://www.reddit.com/r/macapps/comments/1osuxl1 ; https://www.reddit.com/r/ProductivityApps/comments/1u5aes9/speech_to_text_apis_for_agents/ |
| Deepgram latency / accuracy | Individual developers describe Deepgram as fast and accurate, including for streaming; another discussion reports it worked better than Whisper for streaming in that user's setup. | Treat Deepgram as a strong candidate for a live benchmark, but remember its free $200 is a one-time shared speech credit, not a recurring free quota. Sources: https://www.reddit.com/r/LocalLLaMA/comments/1sm6z60/ ; https://www.reddit.com/r/LocalLLaMA/comments/1ld08xa |
| Batch vs real-time | Users distinguish batch transcription from real-time voice-agent use. Whisper is often treated as a baseline for batch jobs; hosted streaming services are favored when low latency, partial transcripts, diarization and endpointing matter. | Keep separate benchmark columns for batch and streaming. A provider can perform well in one mode and poorly in the other. Source: https://www.reddit.com/r/AI_Agents/comments/1udet7k/is_whisper_still_the_best_default_for/ |
| Noisy / overlapping speakers | Reddit comments identify overlapping speakers, noise, accents, and diarization as difficult cases; one comment recommends evaluating Modulate/Velma for multi-speaker overlap, but this is not evidence of a free API. | Add difficult-audio tests to the evaluation checklist. Keep Modulate as an unverified discovery lead until official free API terms are confirmed. Source: https://www.reddit.com/r/AIVoice_Agents/comments/1u4idkq/speech_to_text_apis_for_agents/ |
| Local Whisper / Parakeet | Users recommend Whisper, faster-whisper, whisper.cpp and Parakeet for privacy and avoiding per-minute API costs; comments also note practical trade-offs such as hardware, memory, number formatting and dictionary support. | Put these in a self-hosted STT appendix, never in hosted API Layer 1/2/3. Local inference is not zero-cost in compute or operations. Sources: https://www.reddit.com/r/LocalLLaMA/comments/1gr7p1c/sota_speech_to_text/ ; https://www.reddit.com/r/macapps/comments/1osuxl1 |
| Production pipeline | A voice-agent thread emphasizes measuring the entire pipeline: first partial transcript, final transcript, LLM first token, first TTS audio, playback and interruption handling. | Add end-to-end latency and barge-in metrics to any future benchmark rather than ranking STT by transcript accuracy alone. Source: https://www.reddit.com/r/SelfHostedAI/comments/1vn98mt/what_sttllmtts_stack_are_you_using_for_production/ |

**STT Reddit conclusion:** Groq/Whisper appears repeatedly as a popular low-cost API starting point; Deepgram is repeatedly praised for latency/streaming in individual reports. These are qualitative signals, not a universal accuracy ranking. For multilingual/Arabic audio, the current threads do not provide enough controlled Arabic benchmark evidence to rank providers. Run the same Arabic clips, dialects, noise conditions and speaker configurations through each API before making a quality claim.

## 6.3 New discovery leads from Reddit — not promoted to free-provider status

| Lead | Modality | Why it appeared | Required verification before inclusion in a free layer |
|---|---|---|---|
| Unreal Speech (hosted Kokoro) | TTS | Mentioned as a hosted Kokoro option. | Confirm first-party API endpoint, current free quota (if any), auth, card requirement, model availability and output license. |
| Murf / Falcon | TTS | Mentioned as a lower-cost hosted alternative. | Confirm exact API product and whether any recurring free API quota exists; a low paid price is not a free tier. |
| Fish Audio | TTS | A user reports positive API experience. | Confirm API free-plan entitlement and whether free credits are usable through API rather than only the web app. |
| Modulate / Velma | STT | Mentioned for multi-speaker/overlap handling. | Confirm public hosted API, free allowance and terms; Reddit comment alone is insufficient. |
| Soniox | STT | Mentioned for real-time multilingual transcription and low latency. | Verify official free API quota and exact model/region availability; user comments about price are not a free-tier claim. |
| Smallest AI / Pulse | STT | Mentioned as a real-time STT candidate. | Verify exact public endpoint, free API entitlement and current pricing. |
| Qwen3 TTS | TTS | Recommended in a TTS discussion. | Determine whether the referenced route is local/open-weight, a hosted demo, or a provider API; do not conflate these. |

## 6.4 Reddit evidence quality and limitations

- Reddit comments are not provider documentation. They cannot establish API availability, quota renewal, no-card status, commercial rights, data retention or age/region eligibility.
- Several threads are older than the current pricing snapshot; comments about a provider's speed or quality may refer to earlier model versions.
- Some posts are low-engagement, and some comments may be promotional or self-referential. Treat them as leads, not endorsements.
- No provider was moved into Layer 1, Layer 2 or Layer 3 solely because of Reddit discussion.
- Reddit evidence does not replace controlled testing. For a meaningful comparison, use the same short and long prompts/audio files, languages/dialects, noise levels and network conditions; record latency, error rate, language support, rate-limit responses and output quality.

**Review boundary:** Reddit threads surfaced and reviewed on 23 November 2026. This was a qualitative review, not a controlled benchmark and not a live API test. The official quota tables remain authoritative for free-access classification.

## STT research closure addendum — keyless discovery (23 November 2026)

### New Layer 1 discovery: Audo anonymous transcription API

| Provider / endpoint | Free access | Classification | Important boundaries |
|---|---|---|---|
| **Audo — `POST https://audo.ai/api/try/transcribe`** | First minute of each audio/video file, up to 3 uses per UTC day; no account and no API key. The provider's docs say the endpoint returns a transcript directly and may return `200` or an asynchronous `202` job response. | `LAYER_1_KEYLESS_DAILY_ALLOWANCE / OFFICIAL_DOCS / CANDIDATE_UNTESTED` | This is a real provider-documented HTTP endpoint, not merely a web playground. It is a deliberately limited free preview: only the first minute per file, three uses/day. Whole-file transcription requires an API key and paid credits. Docs list 60 languages, word-level timestamps and speaker labels for the full service; do not assume every feature is enabled identically on the anonymous route without testing. No successful live request was performed in this research. Source: https://audo.ai/docs/transcription-api ; https://audo.ai/docs/api |

**Layer 1 conclusion update:** Audo is the first well-documented strict-keyless hosted STT API found in this search. It satisfies the no-account/no-key requirement on its `/api/try/transcribe` route, but it is a small daily preview rather than a high-volume free tier. No other candidate found in this pass met the same evidence threshold.

### Additional STT candidate audit and exclusions

- **TranscriptFox:** its free HTTP API does not perform speech recognition. It reads captions/transcripts already saved in its shared cache; it cannot download audio or start transcription. Exclude from STT generation APIs. Source: https://www.transcriptfox.com/docs/api
- **Cantonese.ai:** its STT API requires an API key. Docs describe 10 requests/day up to 5 minutes each on accounts without an STT plan, resetting at 00:00 UTC. It is an authenticated recurring daily free allowance, not Layer 1. Language/product scope is Cantonese-focused; validate supported audio languages before treating it as general multilingual STT. Source: https://docs.cantonese.ai/speech-to-text
- **Audo:** do not confuse its anonymous first-minute endpoint with its paid full-file API. The no-key route is capped at three free runs/day and does not establish unlimited transcription.
- **Groq:** retain in Layer 2 as a free rate-limited API, not as a fixed free-minute grant. The model-specific caps are rate/usage ceilings.
- **Google Cloud Speech-to-Text:** retain the published 60-minute monthly free price allowance with the existing billing/project caveat; this is distinct from Gemini audio models.

### STT final status after expansion

- **Layer 1:** Audo is `DOCS_VERIFIED / CANDIDATE_UNTESTED`, first minute per file, 3/day, no account/key. No live inference was tested. No other strict-keyless provider was promoted.
- **Layer 2:** retain Groq Whisper (free rate limits), Cartesia Ink-2 (20K monthly credits shared with TTS), Gemini Transcribe free model access (model-specific limits), Google Cloud STT (60 min/month price allowance), Amazon Transcribe (first-year offer), and Cantonese.ai (10 requests/day, up to 5 min each, API key). Keep TTS.ai's 5-minute STT allocation as `RESET_UNCLEAR`, not a confirmed monthly quota.
- **Layer 3:** retain Deepgram, AssemblyAI, Speechmatics, Gladia, Sarvam and the previously documented finite allocations. Do not add new one-time offers merely because a provider has a free UI demo.
- **Quality/testing gap:** none of these findings establishes Arabic dialect accuracy. No live provider benchmark, account creation, card entry or identity verification was performed. A future benchmark should compare the same Arabic clips (Libyan dialect included), Modern Standard Arabic, background noise, multiple speakers, punctuation/numerals, and both batch and streaming modes.

### New STT sources

- Audo transcription API: https://audo.ai/docs/transcription-api
- Audo free REST API and anonymous limits: https://audo.ai/docs/api
- TranscriptFox API scope: https://www.transcriptfox.com/docs/api
- Cantonese.ai STT API and daily free tier: https://docs.cantonese.ai/speech-to-text
- Reddit STT community discussions remain in Section 6; no Reddit comment alone was used to promote a provider.


---

# TTS and STT provider expansion — additional audit (23 November 2026)

## TTS additions and corrections

| Provider / model | Free API offer | Correct classification and caveats | Official source |
|---|---|---|---|
| **Groq Orpheus TTS** | API endpoint `https://api.groq.com/openai/v1/audio/speech`; English and Saudi Arabic models. Input is capped at 200 characters/request. Groq publishes free Developer-plan rate limits (10 RPM / 100 RPD for Orpheus in the reviewed rate-limit snapshot). | `LAYER_2_FREE_RATE_LIMITED / ACCOUNT_AND_KEY_REQUIRED`. This is a model-specific rate-limited API, not a character balance. Arabic model is Saudi dialect; do not assume Libyan dialect support or equivalent pronunciation quality. Existing Groq entry is retained; this addendum records the current endpoint and language caveat. | https://console.groq.com/docs/text-to-speech/orpheus ; https://console.groq.com/docs/rate-limits |
| **Unreal Speech** | Official pricing page advertises a $0 Free plan with 250,000 characters (about six hours of audio by its estimate). | `FREE_API_PLAN / RESET_PERIOD_UNPUBLISHED`. The pricing page reviewed does not clearly say whether 250K characters renew monthly or are a one-time allocation. Keep it outside a confirmed recurring layer until reset/renewal and API eligibility are explicitly established. | https://unrealspeech.com/pricing |
| **FreeTTS** | Existing API page describes a free API key, 5,000 characters/day, 15,000/month, 5,000 characters/request and 10 RPM. | Keep in Layer 2, but label personal/non-commercial, spoken FreeTTS tag, one-hour file retention and shared website/API counter. A successful live request was not performed in this audit. | https://freetts.org/developers |
| **Speechify — Simba 3.5 correction** | A November 20 provider comparison reports Simba 3.5 dropping from 500,000 to 333,000 characters/month effective 21 November 2026; Simba 3.0/3.2 remain reported at 500,000/month. | Update the model-specific figure rather than replacing the whole Speechify row with one number. Recheck the provider's current dashboard/docs before integration. | https://freellmapi.co/free-text-to-speech-api ; https://docs.speechify.ai/build/guides/concepts/api-limits |
| **Cloudflare Workers AI — MeloTTS** | Model `@cf/myshell-ai/melotts` uses the shared Workers AI daily Neuron allowance; published unit price was 18.63 Neurons/audio minute. | **Do not recommend as a current active route:** Cloudflare marks this model deprecated, with deprecation date 20 November 2026. Keep as a historical/transition record only; check the live model catalogue for replacement models. | https://developers.cloudflare.com/ai/models/%40cf/myshell-ai/melotts/ ; https://developers.cloudflare.com/workers-ai/platform/pricing/ |

## STT additions and clarifications

| Provider / endpoint | Free allowance | Classification and caveats | Official source |
|---|---|---|---|
| **Cloudflare Workers AI — Whisper / Whisper Large v3 Turbo** | Workers AI free usage includes 10,000 Neurons/day shared across the account's Workers AI models. Published pricing lists 41.14 Neurons/audio minute for `@cf/openai/whisper` and 46.63 for `@cf/openai/whisper-large-v3-turbo`. | `LAYER_2_SHARED_DAILY_COMPUTE_QUOTA / ACCOUNT_AND_TOKEN_REQUIRED`. The theoretical all-STT-only conversion is roughly 243 minutes/day for Whisper or 214 minutes/day for Large v3 Turbo, but this is only arithmetic from the published unit rate and assumes no other model uses the pool. Do not present it as a guaranteed transcription-minute grant. | https://developers.cloudflare.com/workers-ai/platform/pricing/ ; https://developers.cloudflare.com/workers-ai/models/whisper/ |
| **Google Cloud Speech-to-Text V1** | First 60 minutes/month free per account under the published Free Tier; standard pricing applies beyond it. | `LAYER_2_RECURRING_MONTHLY / BILLING_PROJECT_REQUIRED`. The pricing page distinguishes V1 and V2; do not assume the same 60-minute grant applies to every V2 model. A Google Cloud project and billing setup are required. | https://cloud.google.com/speech-to-text/pricing ; https://docs.cloud.google.com/speech-to-text/docs/v1/speech-to-text-requests |
| **Amazon Transcribe** | 60 audio minutes/month for the first 12 months, beginning with the first transcription request. | `LAYER_2_TIME_LIMITED_RECURRING / AWS_ACCOUNT_REQUIRED`. Unused minutes do not roll over; after the first 12 months or overage, standard billing applies. This is not a permanent free tier. | https://aws.amazon.com/transcribe/pricing/ ; https://aws.amazon.com/transcribe/getting-started/ |
| **Audo anonymous transcription** | Existing closure addendum records the provider-documented first minute/file and up to three uses/day without an account or key. | Retain as Layer 1 `DOCS_VERIFIED / CANDIDATE_UNTESTED`; the free route is only a preview and is not equivalent to full-file paid API access. | https://audo.ai/docs/transcription-api ; https://audo.ai/docs/api |

## Cross-category cautions

- **Cloudflare quotas are shared.** Do not add TTS Neurons and STT Neurons together as separate 10,000-Neuron pools; all Workers AI model calls draw from the same daily account allowance.
- **TTS and STT units are not interchangeable.** Characters, audio minutes, requests, Neurons and currency credits must remain separate in tables.
- **FreeTTS, Unreal Speech and Speechify have different commercial terms and reset rules.** Never infer commercial permission from a free price label.
- **Arabic coverage is not dialect-neutral.** Groq's Orpheus Arabic offering is explicitly Saudi Arabic. The catalogue does not establish that it handles Libyan dialect reliably.
- **No live TTS or STT generation was performed in this addendum.** These are documentation/research findings, not `GENERATION_OK` results.

### New source register

- Groq Orpheus TTS: https://console.groq.com/docs/text-to-speech/orpheus
- Groq rate limits: https://console.groq.com/docs/rate-limits
- Unreal Speech pricing: https://unrealspeech.com/pricing
- FreeTTS API: https://freetts.org/developers
- Speechify API limits: https://docs.speechify.ai/build/guides/concepts/api-limits
- Cloudflare Workers AI pricing: https://developers.cloudflare.com/workers-ai/platform/pricing/
- Cloudflare Whisper: https://developers.cloudflare.com/workers-ai/models/whisper/
- Google Cloud STT pricing: https://cloud.google.com/speech-to-text/pricing
- Amazon Transcribe pricing: https://aws.amazon.com/transcribe/pricing/

# Cross-provider audit correction — STT and shared quota accounting (23 November 2026)

- **Groq Whisper:** retain in Layer 2 as a free, account/key-required, model-specific rate-limited API. The published request/audio ceilings are not a fixed monthly transcription allowance. Check the current Groq console before deployment. Sources: https://console.groq.com/docs/speech-to-text ; https://console.groq.com/docs/rate-limits
- **Cloudflare Workers AI:** its 10,000 Neurons/day is one shared account pool across eligible text, image, audio and other model tasks. Do not list the same daily balance as independent free credits in LLM, image, TTS and STT. MeloTTS is deprecated as of 20 November 2026 and must not be presented as a current recommended model. Sources: https://developers.cloudflare.com/workers-ai/platform/pricing/ ; https://developers.cloudflare.com/ai/models/%40cf/myshell-ai/melotts/
- **Deepgram:** the current official pricing page still advertises $200 signup credit, no credit card and no expiry. This is a one-time shared balance for STT, TTS, voice-agent and audio-intelligence products; it is not $200 per modality. Source: https://deepgram.com/pricing
- **Arabic quality note:** model support for “Arabic” or “Saudi Arabic” does not establish reliable Libyan dialect transcription. Test with representative Libyan clips and compare the same audio across providers; do not claim a dialect-specific accuracy result without a benchmark.
