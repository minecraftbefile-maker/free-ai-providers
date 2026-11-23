# AI Music Generation — Hosted APIs

> Music composition and generation endpoints only. Music browser tools are catalogued separately in `08-Music-Generation-Web-UI.md`.

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

# AI Music Generation APIs and Web UI

> Split edition of the original 23 November 2026 research ledger. Original source line range: 1773–1963 and 3655–3751, plus new audit. Provider claims and quota snapshots are time-sensitive; read each evidence label and caveat.

# Section 2 — AI Music Generation API research (23 November 2026)

**Scope:** hosted music-generation APIs only. Distinguish full song generation, instrumental/background music, short audio/sound-effect generation, local/self-hosted models, and browser-only music tools. A service that merely renders supplied MIDI or notes is not text-to-music generation.

## Music Layer 1 — strict keyless / anonymous API

| Provider | Endpoint / capability | Evidence and limits | Classification |
|---|---|---|---|
| Audo AI | `POST https://audo.ai/api/try/generate-music`; multipart fields include `text` and `duration_seconds`; sample request saves the response body directly. | Public developer-facing page explicitly labels this a free API call with no key and no signup. It warns that a free result may be cut short and offers a link to finish the whole file. Files are deleted after 24 hours. This is a real hosted music-generation endpoint candidate, but the public page does not publish a stable daily quota, latency SLA, output format guarantee or commercial-use license. No independent end-to-end test was performed in this research pass. | `LAYER_1_KEYLESS_API_REPORTED`; strong official endpoint evidence, but mark reliability/quota as unpublished and generation completion as not independently tested. Source: https://audo.ai/ai-music-generator |

**Layer 1 exclusions:**
- **BlockRun Music API** does not qualify as free: no key/account is required, but each generation is paid in USDC. No-auth is not free. Source: https://blockrun.ai/tools/ai-audio-generator
- **AI SENSE audio renderer** is a free no-key API for rendering provided notes/MIDI/MOD into audio; it is a synthesizer/rendering endpoint, not generative AI music composition. Keep it outside AI music generation. Source: https://aisense.no/free-public-api-audio-render-api-endpoint
- **Hugging Face public music Spaces** may expose Gradio endpoints, but this pass did not establish a reliable anonymous end-to-end music-generation route with clear quota and no session/token requirement. Keep individual Spaces as discovery candidates until a real unauthenticated generation is demonstrated.
- Local Soundbox/MusicGen/ACE-Step installations are self-hosted software, not hosted APIs. Source: https://github.com/HamSanders/soundbox

## Music Layer 2 — recurring free API quota

| Provider | API | Recurring allowance | Classification and caveats | Official evidence |
|---|---|---|---|---|
| Daydream | `POST https://gen.daydream.live/v1/songs`; API key required; returns MP3/WAV and stems | Developer page states **10 songs/month free** on a free account, shared across API, MCP and generator. | `LAYER_2_RECURRING_MONTHLY`; account and API key required. Important documentation conflict: a separate API docs page says free account songs are for the generator/Studio and that API generation requires purchased credits (5¢/song). Keep marked `CONFLICTED` until a current free-account API call or support confirmation proves that the 10-song allowance applies to API calls. Do not count the web-only allowance as API quota without resolving the conflict. | https://daydream.live/developers ; https://gen.daydream.live/docs |

**Layer 2 verdict:** Daydream is a promising recurring API candidate, but the official documentation is internally inconsistent about whether the free monthly songs can be spent through the API. Therefore it is not yet a clean confirmed free API entry. No other provider in this pass had sufficiently clear official proof of a recurring free music-generation API quota.

## Music Layer 3 — one-time signup credits / finite API trials

| Provider | API and music task | Free offer | Classification and caveats | Official evidence |
|---|---|---|---|---|
| Stability AI — Stable Audio | Text-to-audio and audio-to-audio generation; music, loops, ambience and sound effects | New API accounts start with **25 free credits**; no card required according to the platform FAQ. Stable Audio 2.5 costs 20 credits per generation and Stable Audio 3.0 costs 26 credits, so the grant may cover one eligible 2.5 generation, but not a 3.0 generation at the listed rate. | `LAYER_3_SIGNUP_CREDITS`; finite one-time account grant, not recurring. Requires account and API key. Commercial-use statement is provider-specific; review current terms. | https://platform.stability.ai/ ; https://platform.stability.ai/pricing |
| MusicAPI.ai | Hosted API: Sonic vocal songs, Producer instrumental/background music, Studio generation | New accounts receive **75 free credits**, no card required. Their FAQ estimates examples such as three Sonic generations (up to six songs) or six Producer generations, depending on the endpoint/credit cost. | `LAYER_3_SIGNUP_CREDITS`; finite evaluation balance, not recurring. Account/API key required. Playground demo key is separate from a user's own production API key; don't mistake playground access for anonymous production API access. | https://docs.musicapi.ai/faq ; https://musicapi.ai/docs |
| AIMusicAPI | Hosted music-generation API (Suno-compatible task flow) | Provider's developer article describes **30 free credits**, approximately three generations, for evaluation. | `LAYER_3_SIGNUP_CREDITS_REPORTED`; finite trial, not recurring. Confirm current dashboard grant and current API terms before relying on the amount; this is a provider article rather than a clearly surfaced pricing contract. | https://aimusicapi.ai/en/blog/free-music-api-for-developers |

## Music browser plans that are not free APIs

| Service | Free browser allowance | API status | Correct classification |
|---|---|---|---|
| ElevenLabs Music | Free plan lists 10,000 shared credits/month and limited browser music generation. | Official documentation says Music API is available only to paid subscribers; the API quickstart explicitly says paid users only. | `FREE_WEB_APP_ONLY / API_PAID`; do not place in free API Layer 2. Sources: https://elevenlabs.io/music ; https://elevenlabs.io/docs/overview/capabilities/music ; https://elevenlabs.io/docs/eleven-api/guides/cookbooks/music |
| Suno | Free browser plan lists 50 song credits/day. | No official public developer API was established in this pass. Third-party Suno-compatible APIs are separate providers and must be evaluated on their own terms. | `FREE_WEB_APP_ONLY / OFFICIAL_API_UNCONFIRMED`; do not treat the daily browser credits as API quota. Source: https://suno.com/ |
| Udio | Browser music product. | No official public free developer API confirmed in this pass. | `WEB_APP_ONLY / API_UNCONFIRMED`; exclude from free API layers unless official API docs emerge. Source: https://udio.com/ |

## Music discovery and verification notes

- Audo AI is currently the strongest Layer 1 music API lead found: the provider itself publishes a no-key, no-signup HTTP example. Its free output may be truncated; exact limits and license are not published on the page reviewed.
- Daydream's stated 10 songs/month could make it a valuable Layer 2 entry, but the docs conflict on API eligibility. Preserve the conflict rather than choosing the more generous interpretation.
- Stability AI, MusicAPI.ai and AIMusicAPI belong in Layer 3 because their free balances are signup/trial credits, not recurring monthly quotas.
- ElevenLabs and Suno show why browser credits must not be copied into API tables: the former explicitly gates its Music API to paid subscribers, while the latter's public free allowance is presented as a consumer web plan.
- No account registrations, payment-card checks, identity checks or live generation calls were performed during this research pass. `DOCS_VERIFIED` means the provider page states the offer; it does not mean the generation endpoint was independently exercised.


# Section 2A — Expanded AI Music API providers (23 November 2026)

This is an evidence-led expansion of the music section above. It adds providers only where a hosted music-generation API and a concrete free allowance or trial are documented. Free web generators, local model weights, and paid-only APIs are not promoted into the free API layers.

## Newly discovered Layer 2 candidates — recurring free API allowance

| Provider | API / output | Free allowance | Classification and caveats | Evidence |
|---|---|---|---|---|
| **Daydream** (re-evaluated) | `POST https://gen.daydream.live/v1/songs`; instrumental generation, MP3/WAV and five stems; API key | The developer page says **10 songs/month free**, shared across API, MCP and generator. | `LAYER_2_RECURRING_MONTHLY — CONFLICTED`. The API docs page separately says free songs are for generator/Studio and that API calls require purchased credits (5¢/song); another newer page says 5 free songs in the first week then 2/week. Do not treat the 10/month API quota as settled until a free-key API call or explicit support confirmation resolves the contradictory official pages. Instrumental only; no sung lyrics. | https://daydream.live/developers ; https://gen.daydream.live/docs ; https://gen.daydream.live/developers |

**Layer 2 finding:** No additional cleanly confirmed recurring free music-generation API quota was found in this pass. Daydream remains the only strong candidate, but its own docs conflict. Do not fill this layer with browser-only daily credits from Suno, Udio or ElevenLabs.

## Expanded Layer 3 — signup credits and finite API trials

| Provider | API / models | Free offer | Classification and caveats | Evidence |
|---|---|---|---|---|
| **deAPI** | REST `POST https://api.deapi.ai/api/v2/audio/music`; hosted ACE-Step 1.5 variants and MiniMax Music 3; vocals and instrumentals, configurable duration/lyrics | **$5 signup credit**, no card according to provider; credits expire after 90 days on the documented account offer. | `LAYER_3_SIGNUP_CREDITS`. Requires account/email verification and bearer API key. A unified GPU gateway, not the model owner. Trial balance is shared with other deAPI workloads; number of tracks depends on model and duration. Strong new addition: explicit endpoint, example request, and current model pages are published. | https://deapi.ai/use-cases/music-generation ; https://deapi.ai/models/ace-step-15-xl-turbo ; https://deapi.ai/models/minimax-music-3 |
| **Apiframe** | REST `POST https://api.apiframe.ai/v2/music/generate`; Suno-compatible generation, async job and two-track results | **100 free credits** reported for new accounts. | `LAYER_3_SIGNUP_CREDITS_REPORTED`. Phone verification OR a one-time $1 payment is reported as the unlocking condition, so it is not a clean no-card/no-verification trial. Confirm current onboarding and credit grant before listing as frictionless. Gateway provider; commercial rights depend on the selected upstream model and plan. | https://apiframe.ai/guides/ai-music-api-guide |
| **MusicAPI.ai** (retained; clarified) | Sonic vocal generation, Producer instrumentals (including Lyria 3 Pro), Studio-style generation; REST API | **75 free credits**, no card; provider FAQ estimates three Sonic calls (up to six outputs) or six Producer calls depending on endpoint cost. | `LAYER_3_SIGNUP_CREDITS`. Requires account and API key. The anonymous playground uses a scoped demo key and is not an unrestricted anonymous production API. Pricing page confirms paid plans begin after the evaluation balance. | https://docs.musicapi.ai/faq ; https://musicapi.ai/docs ; https://musicapi.ai/pricing |
| **Stability AI — Stable Audio** (retained; corrected shared-credit note) | Stable Audio text-to-audio / audio-to-audio REST API; music, loops, ambience and sound effects | **25 free credits**, no card at signup. | `LAYER_3_SIGNUP_CREDITS`. Requires account and API key. This balance is shared across Stability platform products; do not count it again in image/audio categories. The currently published credit cost varies by model and duration; do not convert credits into a fixed number of tracks without checking current pricing. | https://platform.stability.ai/ ; https://platform.stability.ai/pricing |
| **AIMusicAPI** (retained; lower confidence) | Hosted music-generation API with Suno-compatible task workflow | Provider article reports **30 free credits**. | `LAYER_3_SIGNUP_CREDITS_REPORTED`. The grant is described in a developer article rather than a clearly surfaced contractual pricing table; mark the exact amount as needing dashboard confirmation. | https://aimusicapi.ai/en/blog/free-music-api-for-developers |

## Layer 1 re-check — strict anonymous API

- **Audo AI** remains a reported candidate because its page documents a no-key/no-signup HTTP generation example. However, the page does not publish a dependable quota, SLA, commercial-use license, or independent proof of successful generation in this pass. Keep it `LAYER_1_KEYLESS_API_REPORTED / UNTESTED`, not confirmed.
- **MusicAPI.ai Playground** exposes a no-signup browser playground and says it calls a real API using a scoped demo key. This is not a strict keyless public API for arbitrary client applications: the demo credential is scoped/managed by the provider and playground access is not equivalent to a general anonymous endpoint. Keep it in a separate `PUBLIC DEMO / SCOPED DEMO KEY` note, not Layer 1.
- **Daydream pay-per-song** accepts no-account requests but charges $0.05 per song via payment (HTTP 402 / MPP / x402). It is anonymous paid access, not free Layer 1. The free account's recurring web allowance and API allowance are described inconsistently across official pages; see Layer 2 conflict above.
- No additional strict keyless hosted music API was verified in this pass. Do not promote Hugging Face Spaces or public model demos without showing a successful generation request that needs no account, key, cookie, or browser session.

## Important exclusions and corrections

| Service / model | What is free | Why it is not a free API layer entry |
|---|---|---|
| **Suno** | Consumer web plan advertises 50 song credits/day. | No official general-access developer API was established. Do not count third-party Suno wrappers as Suno's own API. https://suno.com/pricing |
| **ElevenLabs Music** | Music web experience is available on its site. | Official docs say Music API is available only to paid subscribers. Exclude from free API layers. https://elevenlabs.io/docs/overview/capabilities/music |
| **Udio** | Consumer web generator may offer free browser credits. | No official free public music-generation API was verified. Web allowance is not API quota. https://udio.com/ |
| **ACE-Step / MusicGen / Stable Audio open weights** | Open models can be run locally or self-hosted. | Local weights are not a hosted free API. Include only in a separate self-hosting section, not provider API counts. ACE-Step can be served by third-party hosts such as deAPI, whose own trial is listed above. |
| **AI SENSE audio renderer** | No-key audio rendering of supplied MIDI/notes. | It renders user-supplied musical data; it is not generative text-to-music composition. |

## Quality and verification notes

1. **Best documented new trial provider:** deAPI, because its official music use-case page, model pages and request example establish a real hosted API and $5 signup credits without a card.
2. **Most useful trial for full vocal songs:** deAPI's MiniMax Music 3 / ACE-Step routes and MusicAPI.ai Sonic; compare model-specific credit consumption rather than comparing headline credit counts.
3. **Instrumental/stem workflow:** Daydream is attractive if its free API eligibility is confirmed; its API documents MP3, WAV and five stems. Until then, preserve the `CONFLICTED` status.
4. **Do not overstate Apiframe's trial:** its reported 100 credits are conditional on phone verification or a one-time $1 payment; it may be unsuitable for users who cannot complete that requirement.
5. **No live API generations, account registrations, phone checks or payment-card checks were performed in this pass.** `OFFICIAL_DOCS` means the cited provider page states the offer; it does not mean the API was independently exercised.
6. **License caution:** free credits do not automatically grant commercial rights. Check the provider's current terms and the upstream model's license for each API route, especially multi-model gateways.

## Updated music section verdict

- **Layer 1:** Audo AI is still the only no-key candidate located, and remains untested / quota and license unpublished. No new strict keyless provider was confirmed.
- **Layer 2:** Daydream is the only meaningful recurring-free API lead, but its official pages conflict on whether free allowance is usable through the API. Mark it conflicted rather than claiming a confirmed quota.
- **Layer 3:** deAPI ($5), MusicAPI.ai (75 credits), Stability AI (25 credits), AIMusicAPI (reported 30 credits), and Apiframe (reported 100 credits with a phone-check or $1 condition) provide a more useful trial shortlist. Amounts are not directly comparable because models, duration, and cost per generation differ.

# Section 2B — Further AI Music API research (23 November 2026)

This pass prioritizes discovery in the agreed 50/40/10 order: Layer 1 (50% effort), Layer 2 (40%), Layer 3 (10%). It deliberately separates true music generation from music-catalogue/search APIs, local model deployments, and browser-only demos.

## Layer 1 — strict keyless hosted music-generation API

| Candidate | Hosted endpoint / model | Anonymous access evidence | Limits and status | Classification |
|---|---|---|---|---|
| **ACE-Step 1.5 public Hugging Face Space** | Public Gradio Space `ACE-Step/Ace-Step-v1.5`; documented asynchronous generation endpoints include `/v1/music/generate`, `/v1/jobs/{job_id}`, and `/v1/audio`. Supports text prompts, lyrics, instrumental generation and audio editing tasks. | Hugging Face says public Gradio Spaces can be called through HTTP/Gradio API, and that unauthenticated ZeroGPU requests receive a shared daily GPU allowance (2 minutes/day). The ACE-Step Space publishes its own HTTP generation API documentation. Public Space API use can be anonymous where the Space has no additional auth gate. | **Strong Layer 1 candidate, not independently generation-tested in this pass.** Shared ZeroGPU allowance is very small; queue, GPU availability and Space-specific authentication/configuration may affect success. Verify that the live Space endpoint accepts an unauthenticated POST before calling it confirmed. This is a hosted community/demo Space, not a guaranteed production service. | `LAYER_1_KEYLESS_HOSTED_SPACE_API / CANDIDATE_UNTESTED` |
| **Audo AI** (retained) | Reported no-key/no-signup music-generation HTTP endpoint. | Provider page claims public no-key/no-account API access. | Exact generation route, current anonymous request success, quota, output limits and license remain insufficiently documented in the sources reviewed. Keep as a reported lead only. | `LAYER_1_KEYLESS_API_REPORTED / UNTESTED` |

**Layer 1 exclusions:**
- **MusicAPI.ai anonymous playground:** its changelog describes a no-signup playground with free credits, but the production API documentation requires an API key. A provider-managed/scoped playground credential is not a generally reusable anonymous API. Do not count as strict Layer 1.
- **Daydream no-account endpoint:** an unauthenticated request receives HTTP 402 and requires a payment in USDC. Anonymous paid access is not free Layer 1.
- **Free To Use API:** genuinely keyless and free, but it searches/streams/downloads an existing royalty-free music catalogue; it does not generate new music. Keep in a separate `MUSIC LIBRARY / CATALOGUE API` category, not AI Music Generation.
- **ACE-Step self-hosted API / local MusicGen:** open-source model/API software does not itself provide a free hosted endpoint. Only the public hosted Space above is a Layer 1 candidate.

## Layer 2 — recurring free music-generation API quotas

| Provider | API / capability | Recurring allowance | Evidence status and caveats | Classification |
|---|---|---|---|---|
| **Daydream** (re-audited) | REST API `POST https://gen.daydream.live/v1/songs`; instrumental tracks up to two minutes, MP3/WAV and five stems. | One official developer page says 10 songs/month free and shared across API/MCP/generator; another current API docs page says the free monthly songs are for the generator/Studio and API calls require purchased credits. A separate docs version describes 5 songs in the first week then 2/week and says those free songs are not available through the API. | Official documentation is contradictory. The strict API interpretation is **not confirmed** until a free account's API call succeeds using only its recurring free allowance, or the provider resolves the conflict in writing. The generator's free allowance must not be silently counted as API quota. | `LAYER_2_RECURRING / CONFLICTED_API_ELIGIBILITY` |

**Layer 2 result:** no additional cleanly documented recurring free quota for a hosted AI music-generation API was verified in this pass. This is a research gap, not proof that no such providers exist. Do not fill the table with browser-only daily credits or API rate limits that do not include a free generation allowance.

## Removed from this AI music inventory

- **Free To Use API — removed at the user's request.** It is a catalogue/search/streaming API for pre-existing music, not an AI model that generates new music. It must not appear in the AI music provider count, shortlist, or provider tables. This document intentionally does not maintain a separate catalogue-API recommendation for it.

## New verification and source notes

- Hugging Face's official Spaces API documentation states that public Gradio Spaces expose HTTP/API endpoints and that unauthenticated ZeroGPU users share a daily quota of 2 minutes. This makes public ZeroGPU Spaces a plausible route for genuinely anonymous inference, but each Space's own API and auth configuration must still be checked. Source: https://huggingface.co/docs/hub/spaces-api-endpoints
- The ACE-Step 1.5 public Space publishes a concrete asynchronous API workflow: submit a generation job, poll its job status, then download the resulting audio. Source: https://huggingface.co/spaces/ACE-Step/Ace-Step-v1.5/blob/main/docs/en/API.md
- ACE-Step's API implementation shows that authentication can be optional depending on server configuration; this is not proof that every deployment disables authentication. Source: https://github.com/ace-step/ACE-Step-1.5/blob/main/acestep/ui/gradio/api/api_routes.py
- Daydream official docs conflict on free API eligibility. Sources: https://daydream.live/developers ; https://gen.daydream.live/docs
- MusicAPI.ai's official FAQ confirms 75 signup credits without a card, but that is a one-time trial, not Layer 2. Source: https://docs.musicapi.ai/faq
- MusicAPI.ai changelog describes an anonymous playground, but the documented production API uses an API key. Source: https://musicapi.ai/changelog

## Research outcome and next verification priorities

1. **Layer 1:** ACE-Step public Space is the strongest new candidate because there is a public hosted inference surface, a documented generation API, and a documented anonymous ZeroGPU quota. It remains `CANDIDATE_UNTESTED` until an actual no-auth generation request completes. Audo AI remains reported/unverified.
2. **Layer 2:** Daydream remains conflicted. Do not advertise its monthly web allowance as API quota without resolving the official-doc contradiction. No second recurring free API quota was verified in this pass.
3. **Layer 3:** No need to expand this layer heavily in this pass; retain the existing providers and their finite signup-credit classifications above.
4. **No live generation request, account registration, card check, phone verification or identity check was performed for this update.** Documentation evidence is not equivalent to a successful inference test.


# Section 2C — Further AI Music API discovery (23 November 2026)

This pass continues the agreed priority allocation: Layer 1 receives the largest search effort, Layer 2 the next largest, and Layer 3 only a smaller trial-focused audit. Catalogue/search APIs are excluded entirely from this AI-generation inventory. No live generation requests or account registrations were performed.

## Layer 1 — strict keyless hosted generation

| Candidate | API / generation task | Evidence | Classification and limitations |
|---|---|---|---|
| **Audo AI** (re-audited) | `POST https://audo.ai/api/try/generate-music`; multipart `text` and `duration_seconds`. | The provider's developer-facing page explicitly shows a free API call with no key and no sign-up, with an example `curl` request. It also says a free result may be cut short and links to complete the file. | `LAYER_1_KEYLESS_API_REPORTED / CANDIDATE_UNTESTED`. Strongest direct provider statement for a keyless music-generation endpoint found in this pass, but no independently completed anonymous generation test, stable quota, output guarantee, or clear commercial license was established. Source: https://audo.ai/ai-music-generator |
| **ACE-Step 1.5 public Hugging Face Space** (retained) | Public Gradio Space with async music generation/job/audio routes. | Space documentation exposes the generation workflow; Hugging Face documents public Gradio HTTP endpoints and a shared unauthenticated ZeroGPU allowance. | `LAYER_1_KEYLESS_HOSTED_SPACE_API / CANDIDATE_UNTESTED`. The Space's live auth configuration and successful anonymous generation remain unverified. Shared GPU quota/queue makes this experimental rather than dependable production capacity. Sources: https://huggingface.co/spaces/ACE-Step/Ace-Step-v1.5/blob/main/docs/en/API.md ; https://huggingface.co/docs/hub/spaces-api-endpoints ; https://github.com/ace-step/ACE-Step-1.5/blob/main/acestep/ui/gradio/api/api_routes.py |

**Layer 1 discovery result:** no additional independent keyless hosted music-generation API was promoted in this pass. Search results that merely offered a free browser generator, an anonymous paid endpoint, a local model, or a MIDI renderer were not counted.

## Layer 2 — recurring free hosted API allowance

| Provider | API and free allowance | Classification |
|---|---|---|
| **Daydream** (official-page conflict retained) | Its developer pricing page says 10 songs/month free and shared across API/MCP/generator, while its API documentation says free account songs are for Studio/generator and API calls require purchased credits; another docs revision describes a different web-only weekly allowance. | `LAYER_2_RECURRING / CONFLICTED_API_ELIGIBILITY`. Do not count the free web allowance as API quota until a free-account API generation is confirmed or the provider resolves the conflict. Sources: https://daydream.live/developers ; https://gen.daydream.live/docs |

**Layer 2 discovery result:** this pass did not find another provider with clean, unambiguous official evidence of a recurring free music-generation API quota. This is a bounded research result, not proof that no other service exists.

## Layer 3 — additional API trials (finite, not recurring)

| Provider | API capability | Free offer | Classification and caveats | Official evidence |
|---|---|---|---|---|
| **Sonilo** | Hosted REST API for text-to-music, video-to-music, text/video sound effects and audio workflows. Text-to-music streams NDJSON; API key required. | Official docs are inconsistent in presentation: the text-to-music page advertises **2 free calls** with no card, while the API overview advertises **17 free trial calls (1–2 per endpoint)**. The provider describes the API as a pay-as-you-go prepaid-balance service after the trial. | `LAYER_3_API_TRIAL / OFFICIAL_AMOUNT_CONFLICT`. Treat as a finite API trial, not recurring free access. Require account/API key; no card is stated for the free trials. Confirm the dashboard's actual remaining trial calls before use. Commercial-use claims apply to eligible API output under provider terms; separate restrictions apply to film/TV/broadcast and streaming-service releases. | https://platform.sonilo.com/docs ; https://platform.sonilo.com/docs/text-to-music ; https://sonilo.com/help/is-there-a-sonilo-api-and-how-is-it-priced ; https://platform.sonilo.com/docs/quickstart |

### Additional leads reviewed but not promoted

- **Taan AI:** real hosted music API with text-to-music, input-to-music, refinement and MIDI-to-music endpoints. Its official docs require an API key and say generation consumes credits; the reviewed page did not establish a free recurring quota or a free signup grant. Therefore exclude from active free layers until a provider-published offer is found. Source: https://taan.ai/docs/
- **Lacuna:** official pricing advertises 120 monthly credits on its Free plan, but the reviewed evidence does not establish that those credits can be used through its developer API rather than the consumer product. Keep as `API_ELIGIBILITY_UNCONFIRMED`, not Layer 2. Source: https://www.lacuna.fm/pricing
- **Sonilo consumer Free plan:** its recurring 2,000 credits every two weeks and browser music minutes are not automatically API credits. Only the separately documented API trial calls belong in Layer 3. Source: https://sonilo.com/pricing
- **Taan API credit usage:** an API key and credits are required; do not infer a free allowance merely because API docs and endpoints are public. Source: https://taan.ai/docs/

## Updated research verdict

1. **Layer 1:** Audo AI and ACE-Step public Space remain the only meaningful keyless hosted leads in this inventory. Both are candidates, not independently verified successful anonymous generation.
2. **Layer 2:** Daydream remains conflicted; no second recurring-free API has been verified. Lacuna's monthly consumer credits are not counted because API eligibility is unclear.
3. **Layer 3:** Sonilo adds a documented finite API trial; the provider's own docs disagree between two free text-to-music calls and 17 total trial calls across endpoints. Keep the discrepancy visible. Existing Stability AI, MusicAPI.ai, AIMusicAPI, deAPI and Apiframe entries remain finite trial offers.
4. **Removed:** Free To Use is not an AI generator and has been removed from this document's AI music inventory as requested.
5. **Verification boundary:** no live API generation, account creation, payment-card check, phone verification or identity check was performed. Official documentation is evidence of a published offer, not proof of a successful live generation.

# Music provider expansion — additional audit (23 November 2026)

This addendum is intentionally conservative. The existing catalogue already contains Audo AI, Daydream, Stability AI, MusicAPI.ai, AIMusicAPI, deAPI, Apiframe and Sonilo, plus a separate browser-only music inventory. The new search did not establish another clean recurring-free API with stronger first-party evidence, so it records useful leads without promoting browser credits into API entitlements.

## Additional API leads and exclusions

| Provider | What the current evidence supports | Layer decision |
|---|---|---|
| **Taan AI** | Official docs expose text-to-music, input-to-music, refinement and MIDI-to-music endpoints. An API key is required and generation consumes credits. The reviewed docs do not publish a free recurring quota or a free signup grant. | Keep in the excluded/discovery ledger; not a free layer. Source: https://taan.ai/docs/ |
| **Sonilo** | Existing API docs describe a finite trial; the text-to-music page and general API overview disagree about the number of free calls. | Keep in Layer 3 as a conflicted finite trial; do not treat its separate consumer Free plan as API credits. Sources: https://platform.sonilo.com/docs ; https://platform.sonilo.com/docs/text-to-music ; https://sonilo.com/pricing |
| **ElevenLabs Music API** | The main ElevenLabs Music API documentation says API availability is restricted to paid subscribers. Free consumer-platform credits are not free developer API credits. | Exclude from free API layers. Sources: https://elevenlabs.io/docs/overview/capabilities/music ; https://elevenlabs.io/docs/eleven-api/guides/cookbooks/music |
| **Suno / Udio browser products** | Free consumer access does not establish an official public developer API. Unofficial compatibility gateways must be assessed as separate providers with their own pricing, privacy and reliability. | Keep in Web UI section only; do not promote browser credits into API layers. Sources: https://suno.com/ ; https://udio.com/ |

## Newly surfaced hosted music APIs — Layer 2 / Layer 3 audit

| Provider | API capability and free allowance | Layer and caveats | Source |
|---|---|---|---|
| **Doseedo** | JSON/HTTPS music-composition API with an OpenAPI document and MCP tools. Free account advertises **120 credits/month**; a 30-second rendered part costs 10 credits. It can create short sketches from prompts, but its core differentiator is controllable score/band composition from notes, parts, genre, key, length and seed rather than one-click full vocal songs. | `LAYER_2_RECURRING_MONTHLY / SPECIALIST_COMPOSITION_API`. The monthly pool is shared with its web product. Do not compare one credit or one part directly with a full song generation. Commercial output rights are claimed by the provider's terms; verify exact rights and model behavior before production. | https://doseedo.com/music-api |
| **SoundGen** | REST API for music generation, stem separation, voice synthesis and MIDI workflows. Official API page says new accounts start with **100 free credits**; music generation costs 20 credits per 30 seconds, billed by duration. API and app draw from the same credit balance. | `LAYER_3_SIGNUP_CREDITS / ACCOUNT_AND_API_KEY_REQUIRED`. Finite trial, not recurring. Do not count the same 100 credits once for music and again for TTS/stems; all actions draw from the same balance. | https://soundgen.ai/api |
| **Kie AI Music API** | API task flow for full songs, vocals or instrumentals; provider's developer page reports **80 free credits** for new users, with asynchronous task creation and polling/callbacks. | `LAYER_3_REPORTED_SIGNUP_CREDITS / API_KEY_REQUIRED / TERMS_AND_CARD_STATUS_RECHECK`. The cited page is a developer feature page; verify the live dashboard's credit grant, cost per selected model and current API terms. | https://dev.aimusic-so.pages.dev/features/ai-music-api ; https://docs.kie.ai/ |
| **Sunor** | Unofficial Suno/Udio-compatible aggregation API; site advertises **25 free signup credits**, with async task processing and pay-as-you-go after the starter balance. | `LAYER_3_SIGNUP_CREDITS_REPORTED / UNOFFICIAL_AGGREGATOR`. Not affiliated with Suno or Udio. Treat it as a separate gateway, not an official Suno API; review upstream rights, terms, privacy and uptime. Card requirement was not established by the page reviewed. | https://www.sunor.cc/ |
| **Treblo** | API pricing page advertises **3,000 free credits** (about 30 songs) after verifying a payment card; 100 credits per song. | `LAYER_3_CARD_REQUIRED / NOT_A_NO-CARD_TRIAL`. This is not a no-payment-details offer. Do not add a payment method just to claim it; include only as a caveated research record. | https://treblo.com/developers/pricing |
| **Vercel AI Gateway — Eleven Music v2** | Gateway model page advertises **$5 of credits every 30 days** for users who have not made a payment, usable through its API gateway for Eleven Music v2. | `LAYER_2_RECURRING_GATEWAY_CREDIT_REPORTED`. This is a Vercel gateway credit, not an ElevenLabs free Music API entitlement. Verify that the account is eligible and that the selected model is charged against the free credit before relying on it. | https://vercel.com/ai-gateway/models/music-v2 |

### Music API layer summary — revised

- **Layer 1:** Audo remains the leading documented anonymous API candidate; no new no-key provider was confirmed in this pass.
- **Layer 2:** Add Doseedo's 120-credit/month specialist composition API and Vercel AI Gateway's advertised $5/30-day Eleven Music v2 credit, both with product/gateway-specific caveats. Daydream remains a separate documentation-conflict case.
- **Layer 3:** Add SoundGen (100 credits), Kie AI (80 reported credits), and Sunor (25 reported credits). Treblo is separately recorded as card-required and is not a no-card recommendation.
- These additions do not imply a common “song count”: each vendor meters different actions, durations, models and shared balances.
- No live music generation was performed for these additions.
