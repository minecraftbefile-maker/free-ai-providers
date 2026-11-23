# Comprehensive audit and research update — 23 November 2026

## 1. Layer system: retained

The project still uses two separate classification systems. Do not compare API Layer 1 with Web UI Layer 1 as if they mean the same thing.

### Hosted API catalogues — three layers

| API layer | Meaning | Required proof / handling |
|---|---|---|
| **Layer 1** | Truly anonymous/keyless inference endpoint. | A real generation route must work without an account, API key, placeholder credential, cookie, browser session or delegated login to qualify as strict keyless. If a public sentinel such as `0000000000` is required, record it separately as `Layer 1B — public placeholder credential`, not strict keyless. Rate-limited free endpoints still belong here. |
| **Layer 2** | Recurring or continuing free API access. | Daily/monthly/rolling quota, ongoing zero-priced model or documented continuing free plan. State the exact unit and reset cadence. Rate limits alone are not a free quota. Model-specific and shared pools must be explicit. |
| **Layer 3** | One-time trial credits, signup balances, limited free runs or temporary grants. | State amount, expiry, card/phone/identity conditions and eligible product. Application-only startup grants must not be presented as ordinary personal signup offers. |

### Browser Web UI catalogues — five layers

| Web UI layer | Meaning |
|---|---|
| **Layer 1** | Anonymous, free, vendor-claimed unlimited access; label claims and unverified capacity separately. |
| **Layer 2** | Anonymous, free but limited or subject to fair-use throttling. |
| **Layer 3** | Account required, free and effectively unlimited for the specific basic feature being classified. |
| **Layer 4** | Account required, free but limited / recurring. |
| **Layer 5** | One-time trial, finite credits or non-renewing grant. |

The Web UI system remains documented inside the relevant UI files. It must not be collapsed into the API three-layer system.

## 2. New and clarified providers in this revision

| Provider | Modality | Layer | New finding / correction | Evidence status |
|---|---|---:|---|---|
| Kilo AI Gateway | LLM API | 1 | Official docs: anonymous free-model access, 200 requests/hour/IP; dynamic free roster. | Official docs; no fresh live generation test in this pass. |
| OVHcloud AI Endpoints | LLM API | 1 | Official docs: anonymous access at 2 requests/minute/IP/model; exact free entitlement still model-specific. | Official docs; verify current model price. |
| AI Horde | LLM API | 1B | Public sentinel key `0000000000`, volunteer worker queue; privacy and latency caveats. | Community API/catalog evidence; not strict keyless. |
| Gizmo Platforms | LLM API | 2 | 1,000 free-model API requests/month, $1 weekly included usage pool, 20 API RPM. | Current official plan/docs. |
| SenseNova Token Plan | LLM API | 2 | Public beta says 1,500 calls/model/rolling 5 hours for named models. | Official beta page; temporary beta conditions. |
| BlazeAPI | LLM API | 2 candidate | Pricing page advertises 200,000 tokens/day on DeepSeek models, no card. | Official pricing claim; endpoint/model/generation verification pending. |
| Novita AI / Apodex 1.1 Mini | LLM API | 2 candidate | $0 model listing found; duration and quota undisclosed. | Third-party catalogue only; not promoted to confirmed tier. |
| deAPI | LLM, image, video, music APIs | 3 | $5 one-time signup credit; shared multimodal balance. Image page states no card and 90-day expiry; video model page documents a model-specific daily cap. | Provider pages; do not multiply the same credit across modalities. |
| Groq Orpheus | TTS API | 2 | Official TTS endpoint and 200-character input cap; free access is request-limited and account/key required. | Official docs; no live audio test in this pass. |
| Cloudflare Workers AI | LLM, image, TTS/STT, embeddings | 2 | 10,000 Neurons/day shared across eligible tasks; selected new models require Paid plan/prepaid credits. MeloTTS deprecated 20 Nov 2026. | Official docs/changelog. |

## 3. Corrections discovered during audit

1. **ACLIDE is no longer active.** The official documentation says the project ended and signups/purchases are closed. Any €20/month free allowance from older pages must be marked historical/ended, not active Layer 2.
2. **Cloudflare model access is not uniform.** 10,000 Neurons/day remains the Free allocation, but some named high-compute models require a Workers Paid plan or prepaid credits. A model being in the catalogue does not prove it is available on Free.
3. **Cloudflare quota must not be multiplied.** One Neuron balance is shared across LLM, image, audio, embedding and other eligible inference tasks.
4. **Cloudflare MeloTTS is deprecated.** Do not list it as a current active speech model after 20 November 2026; preserve the history and check replacements.
5. **Kilo and OVH anonymous limits are not equivalent.** Kilo's free models have a 200/hour/IP cap; OVH's anonymous access is 2/minute/IP/model. Neither cap guarantees uptime or proves every model is free.
6. **AI Horde is not strict keyless.** It requires a public sentinel credential and has volunteer-worker privacy/queue constraints. Keep it in a separate public-placeholder subcategory.
7. **Gizmo has two different free pools.** 1,000 zero-cost-model API requests/month and $1 weekly covered usage are separate pools; neither is per model or per modality.
8. **deAPI's $5 is one shared balance.** Cross-list its supported modalities, but count the signup credit once only. The daily model request cap does not make each request free after the balance is exhausted.
9. **Cohere trial keys are evaluation-only.** 1,000 API calls/month and endpoint-specific RPM limits should not be described as a general production free tier.
10. **No live test was run for the newly added entries.** The new records remain documentation-backed or candidates. Do not change them to `GENERATION_OK` without a real completion/image/audio/video/3D output.

## 4. Cross-category quality review checklist

Use this checklist whenever a provider is added or re-audited:

- [ ] Identify the legal provider/operator and distinguish the model owner from the API gateway/reseller.
- [ ] Confirm the exact API endpoint and the exact generation operation, not only a model list or playground.
- [ ] Test one real generation request where an account and safe test are available; record date, request type, status, returned output and usage/billing metadata.
- [ ] Keep `GENERATION_OK`, `DOCS_VERIFIED`, `VENDOR_CLAIM`, `SOURCE_VERIFIED`, `CANDIDATE` and `UNTESTED` distinct.
- [ ] Record the precise access type: no auth, public placeholder, account/key, cookie/session, OAuth, or paid billing activation.
- [ ] Record limits in native units: tokens, requests, credits, characters, audio seconds, Neurons, clips or 3D credits.
- [ ] Record reset cadence, expiry, shared balances, concurrency, RPM/RPD/TPM and overage behavior separately.
- [ ] Separate personal-use, evaluation-only, non-commercial, commercial and attribution requirements.
- [ ] Check data retention, training use, public-worker exposure and regional processing.
- [ ] Check signup requirements separately: email, phone, card, identity verification, business email, geographic restrictions and age rules.
- [ ] Verify current model ID, endpoint version, deprecation status and model-specific availability.
- [ ] Do not count one gateway or one shared credit pool as several independent providers or grants.
- [ ] Keep browser plans, API plans, local models and asset libraries in their own files.

## 5. Known coverage gaps retained honestly

- `10-TTS-Web-UI.md` and `12-STT-Web-UI.md` remain evaluation guides rather than provider inventories. The current source evidence is not sufficient to add a reliable browser-only inventory without a dedicated first-party research pass.
- No new recurring free hosted 3D-generation API was confirmed in this revision. The existing three.ws entry remains a documented keyless candidate with its own daily cap and shared-backend caveats; other 3D providers should not be promoted from free web plans to API layers.
- No new strict-keyless video API was confirmed. Free web video generators and one-time API credits remain separate.
- No new strict-keyless music API was confirmed in this pass. deAPI is an account/key-based Layer 3 shared-credit entry, not an anonymous music endpoint.
- Existing image/video/music provider lists already contain multiple candidate and trial records; do not pad the catalogue with paid-only services, expired promotions, or unsupported “unlimited” claims.

## 6. Source register for this audit

- Kilo anonymous access, models and quota: https://kilo.ai/docs/gateway/authentication ; https://kilo.ai/docs/gateway/models-and-providers ; https://kilo.ai/docs/gateway/usage-and-billing
- OVH anonymous access and rate limits: https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-getting-started ; https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-troubleshooting
- AI Horde anonymous placeholder route discovery: https://aihorde.net/ ; https://freellmapi.co/free-llm-api-no-signup
- Gizmo free plan and developer API: https://gizmoplatforms.com/ ; https://gizmoplatforms.com/developers
- SenseNova public beta: https://www.sensenova.ai/token-plan
- BlazeAPI pricing: https://blazeapi.org/pricing
- deAPI image/video/API: https://deapi.ai/lp/en/free-image-generation-api ; https://deapi.ai/lp/en/minimax-h3 ; https://deapi.ai/
- Cloudflare Workers AI pricing/model exclusions: https://developers.cloudflare.com/workers-ai/platform/pricing/ ; https://developers.cloudflare.com/changelog/post/2026-07-28-models-require-workers-paid/
- Groq Orpheus TTS: https://console.groq.com/docs/text-to-speech/orpheus ; https://console.groq.com/docs/rate-limits
- Deepgram shared signup balance: https://deepgram.com/pricing
- ACLIDE project ended: https://aclide.com/en/documentation
- Cohere trial/evaluation limits: https://docs.cohere.com/v1/docs/rate-limits ; https://docs.cohere.com/v1/docs/cohere-faqs

**Research boundary:** source pages were reviewed on 23 November 2026. No provider accounts were created, no payment methods were entered and no live generation requests were made in this revision. This audit is documentation-based; it does not claim universal live availability from Libya or any other region.
