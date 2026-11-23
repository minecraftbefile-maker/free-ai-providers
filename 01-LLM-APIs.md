# LLM / Text Generation — Hosted APIs

> API providers only: anonymous/keyless gateways, recurring free quotas, and one-time trial credits. Browser chat products are in `02-LLM-Web-UI.md`.

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

# LLM APIs, recurring free quotas and trials

> Split edition of the original 23 November 2026 research ledger. Original source line range: 1–753. Provider claims and quota snapshots are time-sensitive; read each evidence label and caveat.

# Free AI --- Section 1: Keyless AI APIs and Discovery Inventory

**Research snapshot:** 23 November 2026\
**Scope:** Section 1 only --- anonymous/no-key inference APIs, related
gateways, self-hosted projects, research repositories, trackers, and
excluded lookalikes.\
**Purpose:** Preserve every relevant name discovered so far. This is a
research ledger, not a claim that every endpoint currently works. No
fresh HTTP generation tests were run while creating this file.

## 1. Strict Keyless definition

Count a service as strict Keyless only if a real inference request
succeeds without an account, API key/Bearer token, public
placeholder/sentinel, cookie, browser session, or delegated identity. A
working `/models` endpoint alone is not proof. Do not count models as
providers: one gateway with 20 models is one gateway.

### Evidence tags

-   `GENERATION_OK`: real generation request succeeded.
-   `ANONYMOUS_VERIFIED`: generation succeeded without
    account/key/cookie/session.
-   `NO_AUTH_CONFIRMED`: no auth required for tested route.
-   `DOCS_VERIFIED`: official docs state auth behavior.
-   `SOURCE_VERIFIED`: source code confirms behavior.
-   `PUBLIC_ENDPOINT_FOUND`: public deployment found.
-   `MODELS_OK`: models route works; not generation proof.
-   `STREAMING_OK`, `TOOLS_OK`, `VISION_OK`: feature independently
    verified/documented.
-   `QUOTA_VERIFIED`: quota independently confirmed.
-   `KEYLESS_CANDIDATE`, `KEYLESS_GENERATION_REPORTED`, `UNVERIFIED`,
    `EXPERIMENTAL`, `LOW_RELIABILITY`, `DEAD`.
-   `INDEPENDENT_PROVIDER`, `AGGREGATOR`/`GATEWAY`, `SELF_HOSTED_ONLY`,
    `BROWSER_SESSION_REQUIRED`, `PUBLIC_PLACEHOLDER_CREDENTIAL`.

## 2. Public Keyless providers and gateways

### Pollinations

-   Endpoint: `https://text.pollinations.ai/openai/v1`
-   Type: public inference service/gateway.
-   Evidence: `GENERATION_OK`, `ANONYMOUS_VERIFIED` from the user's
    supplied successful HTTP 200 test.
-   Tested model: `gpt-oss-20b`; `POST /chat/completions` returned
    generated text and `user_tier: anonymous`.
-   Qualification: proof applies to that historical route/test, not
    every current Pollinations endpoint. Newer routes/docs may require
    keys. Re-test current endpoint.
-   Streaming, tools, vision, current quota: not verified.

### Kilo Gateway

-   Candidate base URLs: `https://api.kilo.ai/api/gateway/v1`;
    `https://ai-gateway.kilo.ai/api/v1`.
-   Type: `AGGREGATOR`/gateway.
-   Selected free models reportedly work anonymously; model IDs commonly
    end in `:free`.
-   Earlier reported limit: around 200 requests/hour/IP; confirm current
    policy.
-   Evidence: `DOCS_VERIFIED`/`KEYLESS_CANDIDATE`; endpoint versions
    need reconciliation.
-   A previous user test of one older route/config returned 401; do not
    claim that route worked.
-   Check prompt data/training policy.

### OVHcloud AI Endpoints

-   Candidate bases: `https://endpoints.ai.cloud.ovh.net/v1`;
    `https://oai.endpoints.kepler.ai.cloud.ovh.net/v1`.
-   Type: hosted inference provider.
-   Some public/free routes reportedly permit unauthenticated requests;
    sources conflict across endpoint generations.
-   Earlier reported limit: around 2 requests/minute/IP/model; confirm.
-   Evidence: `KEYLESS_CANDIDATE`, earlier `DOCS_VERIFIED`; current
    route and generation need rechecking.
-   Reported model families: Qwen, GPT-OSS, Llama, Mistral.

### JarvisClaw

-   Endpoint: `https://api.jarvisclaw.ai/v1`
-   Docs: `https://jarvisclaw.ai/zh/free-llm-api`
-   Type: gateway/provider.
-   Chinese docs reportedly say no account, key, or wallet; use
    `auto/free` and omit Authorization.
-   A placeholder Authorization value reportedly returns 401; test with
    Authorization omitted.
-   Evidence: `DOCS_VERIFIED`, `KEYLESS_CANDIDATE`; independently test
    generation.
-   IP limits reported.

### Vireonix

-   Endpoint: `https://vireonix.ai/v1`
-   Type: gateway/provider candidate.
-   Evidence: `KEYLESS_GENERATION_REPORTED`.
-   Russian Habr report: `https://habr.com/ru/articles/1085352/`;
    describes anonymous generation returning HTTP 200 and text.
-   Needs fresh independent test. A previous concern was
    canned/local-looking output; the Habr report is additional evidence,
    not conclusive proof.

### Free.ai

-   Endpoint: `https://api.free.ai/v1`
-   Type: gateway/provider candidate.
-   Anonymous access and about 9 models were reported in an earlier
    monitor.
-   Evidence: `KEYLESS_CANDIDATE`, `LOW_RELIABILITY`.
-   Earlier monitoring snapshot: 18 successful attempts out of 1,008
    over 14 days. Do not call dependable without fresh uptime check.

### mlvoca

-   Endpoint: `https://mlvoca.com/api/generate`
-   Docs: `https://mlvoca.github.io/free-llm-api/`
-   Type: hosted inference endpoint; Ollama-compatible.
-   Docs reportedly say no API key; TinyLlama and DeepSeek R1 1.5B were
    mentioned.
-   Streaming documented.
-   Educational/research-only, non-commercial terms were reported;
    recheck current terms.
-   Evidence: `DOCS_VERIFIED`, `KEYLESS_CANDIDATE`; current
    generation/model availability needs testing.
-   Earlier monitoring snapshot: 318/336 successes over 14 days; not a
    current guarantee.

### BlockRun

-   Endpoint: `https://blockrun.ai/api/v1`
-   Guide:
    `https://blockrun.ai/signal/free-llm-api-no-key-models-you-can-curl`
-   Type: `AGGREGATOR`/gateway.
-   Company guide claims selected free models work without login/key.
-   OpenAI-compatible; streaming, tools, vision claimed for selected
    models only.
-   Evidence: `DOCS_VERIFIED`, `KEYLESS_CANDIDATE`; needs independent
    generation test.

### llmfaucet

-   Repository: `https://github.com/llmfaucet/llmfaucet`
-   Reported endpoint: `https://api.llmfaucet.dev/v1`
-   Type: `AGGREGATOR`/public gateway, not independent inference
    provider.
-   OpenAI-compatible; Authorization reportedly optional for most cases,
    though some clients may send a public placeholder.
-   Reported upstreams include Pollinations, OVH, AI Horde; list may
    change.
-   Evidence: `PUBLIC_ENDPOINT_FOUND`, `SOURCE_VERIFIED` candidate; test
    actual generation with no Authorization header.
-   Count as one gateway, not each upstream.

### FreeAIXYZ

-   Repository: `https://github.com/AkshayCoder48/FreeAIXYZ`
-   Type: gateway/aggregator project.
-   Claims 75+ models, 17 providers, no signup/API key, streaming and
    tools.
-   Evidence: `EXPERIMENTAL`, `UNVERIFIED`.
-   Inspect auth code, public deployment, actual generation, upstream
    attribution, license, dependencies, maintenance. Do not treat
    model/provider claims as verified.

### free-llm-router

-   Repository: `https://github.com/Mr-Destructive/free-llm-router`
-   Type: router/gateway project; deployment status to be checked.
-   Reported sources: Gemini Guest, Kilo, OpenCode Zen, OVH, LLM7.
-   Some sources reportedly no-key; OpenCode Zen may use a public
    credential; guest routes may rely on undocumented web internals.
-   Evidence: `SOURCE_REVIEW_CANDIDATE`, `EXPERIMENTAL`, `UNVERIFIED`.
-   Gemini Guest may depend on ephemeral guest/browser sessions; do not
    present as stable official API.
-   Count as one project, not five providers.

### Gemini Guest (unofficial guest route)

-   Type: unofficial web/guest access, not official Gemini API Free
    Tier.
-   Reported to work without API key, but may depend on browser guest
    flow/session.
-   Status: `EXPERIMENTAL`, `UNVERIFIED`, possibly
    `BROWSER_SESSION_REQUIRED`.
-   Do not describe as official Google API.

## 3. Placeholder credentials / shared keys --- NOT strict Keyless

### AI Horde

-   Endpoint: `https://oai.aihorde.net/v1`
-   Type: volunteer-powered inference gateway.
-   Uses public sentinel `0000000000`.
-   Classification: `PUBLIC_PLACEHOLDER_CREDENTIAL`, not strict Keyless.
-   Volunteer queue, low priority, variable wait.

### LLM7.io

-   Endpoint: `https://api.llm7.io/v1`
-   Type: gateway/provider candidate.
-   Sources conflict: some say token required; another says certain
    routes accept `Bearer unused`.
-   Classification: `PUBLIC_PLACEHOLDER_CREDENTIAL`/`UNVERIFIED`; not
    strict Keyless until no-header generation is confirmed.

### Empero

-   Endpoint: `https://free.empero.org/v1`
-   Type: gateway.
-   Docs reportedly accept placeholder `free` or arbitrary key.
-   Classification: `PUBLIC_PLACEHOLDER_CREDENTIAL`, not strict Keyless.
-   Upstream 503s/model rotation reported; prompts may be used for
    training (check current policy).

### Y-API Daily Shared Key

-   Endpoint: `https://api.y-api.bestvirtualgoods.com/v1`
-   Type: shared-key gateway/reseller.
-   Uses shared key; not strict Keyless.
-   Include in a public shared-key list only if operator explicitly
    authorizes public use.

### OpenCode Zen

-   Type: gateway/provider route referenced by router projects.
-   Stable public endpoint not established in earlier inventory.
-   Login/Bearer requirements unclear; some projects describe a public
    value or guest access.
-   Classification: `UNVERIFIED`; do not count until direct no-header
    generation succeeds.

## 4. Projects, clients, self-hosted gateways, and research repositories

### Token-Free Gateway

-   Repository: `https://github.com/andeya/token-free-gateway/`
-   Type: self-hosted gateway/client.
-   Reportedly uses browser sessions for about 13 providers;
    streaming/tools supported.
-   Classification: `SELF_HOSTED_ONLY`, `BROWSER_SESSION_REQUIRED`; not
    strict Keyless.

### Dulus

-   Repository: `https://github.com/KevRojo/Dulus`
-   Arabic docs:
    `https://github.com/KevRojo/Dulus/blob/main/docs/README_AR.md`
-   Type: multi-source client/proxy.
-   Reported Gemini Guest session capture, multiple sources, tools,
    LiteLLM integration, local/Docker deployment.
-   Classification: `SELF_HOSTED_ONLY`/`KEYLESS_CLIENT_PROJECT`; some
    routes use sessions.

### OmniRoute Free AI Providers

-   Repository:
    `https://github.com/itsPremkumar/omniroute-free-ai-providers`
-   Type: research catalog.
-   Separates Tier A no-account/no-key from Tier B session/account
    routes.
-   Names surfaced: Pollinations, Puter, Z.AI, OpenCode Zen, Kilo,
    SiliconFlow, Tencent Hunyuan, Baidu ERNIE, UncloseAI, Liquid AI,
    Reka, StepFun, SenseNova.
-   Discovery only; earlier snapshot reportedly dated 17 June 2026. Many
    entries require keys/accounts/sessions and need individual
    verification.

### Free LLM RU

-   Repository: `https://github.com/neurostack-lab/free-llm-ru`
-   Type: Russian-language testing/research project, not provider.
-   Reported 28 models across 9 providers, with Russian/coding/response
    measurements.
-   Names/models surfaced: Qwen and Mistral via OVH; GPT-OSS via Groq;
    Kilo models; Cloudflare models.
-   Use for discovery; check each upstream's auth and quota.

### VLM Run / Qwen3.8-27B historical candidate

-   Reference:
    `https://github.com/mvalentsev/awesome-free-ai-coding/blob/main/models/qwen3.8-27b.md`
-   Type: historical public gateway candidate.
-   Historical claims: no account/key; 10 RPM, 30/hour, 100/day per IP.
-   A repository check reportedly observed anonymous requests returning
    403 and requiring key on 5 November 2026.
-   Classification: `DEAD` for strict Keyless as of that report; retain
    in historical records.

### Other repositories/lists to inspect

-   `https://github.com/surendranb/free-inference`
-   `https://github.com/peter123023/awesome-free-llm-api`
-   `https://github.com/PythonOtakus/FreeLLMAPI`
-   `https://github.com/nbhson/app-free-llm-gateway`
-   `https://github.com/lion231226/dsh-freellmapi`
-   `https://github.com/devanasolver/awesome-free-llm-apis`
-   `https://github.com/peter123023/awesome-free-llm-api/blob/main/README.en.md`

These are discovery leads, not verified providers. Inspect source,
deployment, auth, license, dependencies, activity, and real inference.
Never use stars as a quality filter.

## 5. Directories, trackers, and regional discovery sources

These are not providers; use them to discover candidates, then verify
each one.

-   FreeLLMAPI tracker: `https://freellmapi.link/` --- earlier snapshot
    reported 141 providers around 20 Nov 2026. Directory data is not
    proof of anonymous generation. Earlier notes say personal/research
    use allowed and bulk/commercial reuse may require permission;
    recheck terms.
-   FreeInference.dev: `https://freeinference.dev/free-keyless-api/` ---
    keyless directory/article, discovery only.
-   Stillworks guide:
    `https://stillworks.supercapybara.com/free-llm-api-no-key` ---
    discovery guide.
-   FreeLLMAPI.co: `https://freellmapi.co/free-llm-api-no-signup` ---
    discovery guide.
-   BlockRun guide:
    `https://blockrun.ai/signal/free-llm-api-no-key-models-you-can-curl`
    --- provider-authored discovery material.
-   Bayanat Labs Arabic tracker:
    `https://www.bayanatlabs.com/ar/tools/arabic-ai-model-tracker` ---
    tracks Arabic model releases, not an anonymous API provider.
-   Verbito AI Atlas --- directory, not provider.
-   LLMnow (Turkey): `https://llmnow.ai/` --- earlier research found
    private beta/API key requirement; not Keyless on that evidence.
-   F24 SALES: `https://www.f24-sales.com/de/` --- German-language
    free-model tracker; reports model/provider availability, not proof
    of Keyless auth.

### Search phrases to continue

-   Arabic: `واجهة ذكاء اصطناعي بدون مفتاح API`;
    `استدلال مجاني دون تسجيل`; `API نماذج لغوية بدون مفتاح`;
    `واجهة استدلال عامة دون مصادقة`.
-   Chinese: `无密钥 AI API`; `免费匿名大模型接口`; `免注册 大模型 API`.
-   Japanese: `APIキー不要 LLM API`; `登録不要 AI API`.
-   Korean: `API 키 없는 무료 AI API`; `가입 없는 무료 LLM API`.
-   Russian: `бесплатный LLM API без ключа`;
    `анонимный API нейросети без регистрации`.
-   Turkish: `API anahtarı gerektirmeyen ücretsiz yapay zeka API`;
    `kayıt gerektirmeyen LLM API`; `ücretsiz anonim yapay zeka API`.
-   German/Austrian: `kostenlose LLM API ohne Schlüssel`;
    `anonyme KI Inference API`; `OpenAI API ohne Anmeldung Österreich`.
-   English: `anonymous inference endpoint`;
    `public no-auth LLM gateway`.

Continue searching Codeberg, GitLab, Hugging Face Spaces, public Gitea,
university/research projects, developer forums, Hacker News, Reddit, and
regional communities. Zero-star and low-star projects must remain
eligible; stars are not a quality criterion.

## 6. Known non-Keyless services / false positives

Keep these records to avoid accidental reclassification. Some belong in
the recurring-free-quota or trial sections, not Keyless.

  -----------------------------------------------------------------------
  Service                             Reason it is not strict Keyless
  ----------------------------------- -----------------------------------
  Cloudflare Workers AI               Account and API token required for
                                      inference API.

  Hugging Face Inference              Account/token required.

  OpenRouter                          API key required.

  Vercel AI Gateway                   API key required.

  Routeway                            Account/key required in earlier
                                      research.

  SiliconFlow                         API key required.

  DeepSeek platform                   API key required.

  Z.AI                                API key required.

  Groq                                Account/key required; candidate for
                                      recurring free quota section.

  Puter                               Delegated identity/session; not
                                      anonymous raw HTTP inference.

  ReadyServer                         Only inside paid VPS/private
                                      network.

  LLMnow (Turkey)                     Earlier research found private beta
                                      and API key requirement.

  Hack Club AI                        External test reported 401.

  Naga                                External test reported 401.

  FriendliAI                          External test reported 401.

  iFlytek Spark                       External test reported 401.

  UncloseAI                           External test reported 403; do not
                                      include without new proof.

  Liquid AI                           External test reported 403; do not
                                      include without new proof.

  Reka                                External test reported 403; do not
                                      include without new proof.

  Blackbox API                        Previously tested path failed.

  g4f.space                           Earlier test returned 402; not
                                      confirmed genuinely free.

  VLM Run                             Reported changed to 403/API-key
                                      requirement on 5 Nov 2026.
  -----------------------------------------------------------------------

## 7. Historical source URLs retained

-   Kilo auth docs: `https://kilo.ai/docs/gateway/authentication`
-   OVH AI Endpoints: `https://endpoints.ai.cloud.ovh.net/`
-   JarvisClaw Chinese docs: `https://jarvisclaw.ai/zh/free-llm-api`
-   Vireonix Russian report: `https://habr.com/ru/articles/1085352/`
-   mlvoca docs: `https://mlvoca.github.io/free-llm-api/`
-   BlockRun guide:
    `https://blockrun.ai/signal/free-llm-api-no-key-models-you-can-curl`
-   llmfaucet: `https://github.com/llmfaucet/llmfaucet`
-   FreeAIXYZ: `https://github.com/AkshayCoder48/FreeAIXYZ`
-   Token-Free Gateway: `https://github.com/andeya/token-free-gateway/`
-   free-llm-router: `https://github.com/Mr-Destructive/free-llm-router`
-   Dulus: `https://github.com/KevRojo/Dulus`
-   OmniRoute catalog:
    `https://github.com/itsPremkumar/omniroute-free-ai-providers`
-   Free LLM RU: `https://github.com/neurostack-lab/free-llm-ru`
-   FreeLLMAPI tracker: `https://freellmapi.link/`
-   Arabic model tracker:
    `https://www.bayanatlabs.com/ar/tools/arabic-ai-model-tracker`
-   LLMnow: `https://llmnow.ai/`
-   F24 SALES: `https://www.f24-sales.com/de/`

## 8. Completion checklist for future research

1.  Revisit every candidate; never drop obscure or low-star projects.
2.  Verify current official endpoint and exact route.
3.  Test with Authorization omitted entirely.
4.  Check account, cookie, browser-session, and delegated-identity
    requirements.
5.  Test actual text generation; `/models` is insufficient.
6.  Record timestamp, HTTP status, model ID, and short response excerpt;
    never expose private credentials.
7.  Record quotas separately from authentication.
8.  Check streaming, tools, and vision independently.
9.  Review terms, privacy, prompt-training policy, license, and regional
    restrictions.
10. Separate independent providers, gateways, self-hosted projects, and
    discovery sources.
11. Preserve dead/changed services as historical records instead of
    deleting them.
12. Continue searching Codeberg, GitLab, Hugging Face Spaces, Gitea,
    forums, university projects, Hacker News, Reddit, and
    regional-language sources.
13. Never use GitHub stars as a quality criterion.
14. The Keyless inventory is the first section; Section 2 records recurring free API-key quotas. Keep one-time trials in Section 3.

**Preservation rule:** Do not remove a provider/project from this ledger
merely because it is currently down, has few stars, or is not itself a
public endpoint. Update its status and keep its record.

---

# Section 2 — Free API keys with recurring quotas (Daily / Weekly / Monthly)

**Research snapshot:** 23 November 2026  
**Scope:** Services that require an account and/or API key but publish an ongoing or periodically renewed free API allowance. This section is separate from anonymous Keyless access and from one-time trials.  
**Important:** This is a research ledger, not a guarantee of uptime or eligibility. A provider's own dashboard may show account-specific limits. No new live generation requests were performed as part of this update; “officially documented” means the vendor's public documentation or pricing page says so, not that this author independently consumed the quota.

## 2.1 Evidence and classification rules

- `OFFICIAL_QUOTA`: recurring API quota is stated on the provider's own site/docs.
- `OFFICIAL_RATE_ONLY`: official rate limit exists, but no daily/monthly usage grant is stated.
- `TRACKER_ONLY`: discovered in a tracker; official proof is missing or incomplete.
- `REPORTED_TEST`: a third-party researcher reports a real API test; not independently retested here.
- `CONFLICTED`: sources disagree, the offer is out of stock, or the displayed offer may not be claimable.
- `TOPUP_REQUIRED`: requires a purchase/deposit to unlock the ongoing free allowance.
- `CARD_REQUIRED`: requires payment details or a paid plan.
- `GATEWAY`: routes to other model providers; count it as one gateway, not as every upstream model.
- `INDEPENDENT`: provider operates its own inference service/model infrastructure.

A daily request cap is not the same as a token quota. RPM is not a daily quota. A monthly credit that renews every month is recurring; a signup balance that never renews belongs in Section 3 (Trials). “Tokens” may mean model tokens, internal billing units, neurons, or currency-equivalent credits; those are not interchangeable.

## 2.2 Strongest recurring daily allowances — official documentation

| Service | Free API allowance | Access / conditions | Type and evidence | API / official source |
|---|---|---|---|---|
| **GroqCloud** | Model-specific. Current published examples: GPT-OSS 120B and 20B, and Qwen 3.8 27B: 30 RPM, 1,000 RPD, 8K TPM, 200K TPD. Other models have different caps. | Account + API key; free tier, no card stated in the free tier. Exact organization limits shown in console. | `INDEPENDENT`, `OFFICIAL_QUOTA`. | Base `https://api.groq.com/openai/v1`; limits `https://console.groq.com/docs/rate-limits` |
| **Cloudflare Workers AI** | 10,000 Neurons/day, resets 00:00 UTC. Neurons measure compute and are not equivalent to a fixed number of model tokens. | Cloudflare account + API token/account ID. Some newer frontier models require Workers Paid or prepaid AI Gateway credits; not every catalog model is included in no-cost access. | `INDEPENDENT`, `OFFICIAL_QUOTA`. | `https://developers.cloudflare.com/workers-ai/platform/pricing/` |
| **Vikasit Inference** | 2,000,000 tokens/day on Vikasit Nova, free daily allowance. | GitHub sign-in, API key; no card. Free allowance subject to change/fair use. Other models in catalog are paid. | `INDEPENDENT`, `OFFICIAL_QUOTA`. | `https://api.vikasit.ai/v1`; `https://vikasit.ai/inference` |
| **xKiro / xKCode API** | Free plan: 500,000 free-model tokens/day; 1,000,000 after Telegram verification. Only free-tier models count. | Account + API key; no card on Free plan. Do not confuse with the much larger paid-plan allowances or rolling 5h/7d spend windows. | `GATEWAY`, `OFFICIAL_QUOTA`. | `https://docs.xkiro.com/guides/pricing/`; `https://docs.xkiro.com/api/rate-limits/` |
| **Requesty** | 200 requests/day for free models. Per-model free variants and expiry dates can change. | Account + key; no credit card for this free tier. | `GATEWAY`, `OFFICIAL_QUOTA`. | `https://www.requesty.ai/pricing`; terms `https://www.requesty.ai/terms` |
| **OpenRouter** | Models with `:free`: 20 RPM and 50 requests/day. 1,000/day only after at least $10 lifetime credit purchases — that higher tier is not a no-purchase offer. | Account + key. Free model inventory rotates and individual models may disappear. | `GATEWAY`, `OFFICIAL_QUOTA`. | `https://openrouter.ai/collections/free-models` |
| **Free.ai** | 30,000 tokens/day on its self-hosted models; also a 1,000 API-request/month cap and 60 RPM. External premium models are paid. | Signup + email confirmation + API key. | `GATEWAY` with own-hosted models, `OFFICIAL_QUOTA`. Formerly listed as a Keyless candidate; current developer docs require an account/key. | `https://free.ai/developer/`; `https://free.ai/api/` |
| **NaraRouter** | Pricing page advertises 7M tokens/day and 15 requests/minute, with Agnes 2.5 Flash listed in the Free plan. | Account + key. The live pricing page also labels the Free plan “Out of stock” in one display; availability is therefore `CONFLICTED` even though the plan/quota is documented. | `GATEWAY`, `OFFICIAL_QUOTA`, `CONFLICTED_AVAILABILITY`. | `https://router.bynara.id/pricing` |
| **Kiosapi.id** | 50 free requests/day per account; 5 RPM; resets at 07:00 WIB. Free request limits: roughly 24K input characters and 2,048 output tokens. | Verified email + API key; no top-up required for free models. Free allowance shared across free models. | `GATEWAY`, `OFFICIAL_QUOTA`; Indonesian provider, useful hidden-gem candidate. | `https://api.kiosapi.id/v1`; docs `https://kiosapi.id/docs` |
| **Frenix** | 500 requests/day, 5 RPM burst, one active API key on Free. | Telegram sign-in; gateway; free models tier. | `GATEWAY`, `OFFICIAL_QUOTA`. | `https://www.frenix.sh/` |
| **AnyAPI** | Up to 100,000 **AnyTokens** per calendar day, reset midnight UTC, non-rollover. AnyTokens are internal billing units, not model tokens. | Free account + API key; no card per published terms. Exact free model availability should be checked in the dashboard/catalog. | `GATEWAY`, `OFFICIAL_QUOTA`; distinguish internal credits from tokens. | `https://anyapi.ai/terms-of-service`; API base `https://api.anyapi.ai/v1` |
| **DreamPrompting** | 500,000 free tokens/day per account; 5,000 requests/day on a rolling 24-hour window; 100 requests/minute per IP burst. | Google sign-in + API key; no card. Routes across upstream free tiers, so availability/failover depends on upstreams and the live pool. | `GATEWAY`, `OFFICIAL_QUOTA`. | `https://dreamprompting.com/pricing`; docs `https://dreamprompting.com/api-docs`; base `https://dreamprompting.com/api/v1` |
| **Electron Hub** | $0.25 weekly credits, refilled Sunday 21:00 UTC; 5 RPM. Also up to 200 free-model requests/day **through ad rewards**. The 200/day is not the same as a guaranteed token grant. | Account + key; no card stated for Free. Weekly unused credit rollover is limited by the published Flex Wallet cap. | `GATEWAY`, `OFFICIAL_QUOTA`; separate weekly credits from ad-reward requests. | `https://www.electronhub.ai/pricing` |
| **Logfare** | New-account first 24h: 500 requests/day, then Standard account: 5,000/day, 1,000/hour, 40/minute. Shared network cap also applies. | Free account + API key; Discord account must remain in Logfare server for access. No card. Fair-use and data logging apply; provider says traffic is logged for research/data purposes. | `GATEWAY`, `OFFICIAL_QUOTA`; review privacy/data terms before use. | `https://logfare.ai/docs`; base `https://logfare.ai/v1` |
| **100milionseek** | 100,000,000 tokens per UTC day on its listed free model; up to 5 concurrent requests. A milestone reward temporarily raised this to 400M/day but ended Nov 20; normal 100M/day is stated to continue. | Email + human check + API key; no card; one model currently advertised. New/young service, so treat uptime and long-term continuity as uncertain. | `INDEPENDENT/PROVIDER CLAIM`, `OFFICIAL_QUOTA`; newly discovered, monitor stability. | `https://100milionseek.top/`; docs `https://devseek.space/docs`; base `https://100milionseek.top/v1` |
| **APIBridge (MoBike)** | 10,000 tokens/day, described as free forever. | API key requires SeaTalk identity verification; no card claimed. This identity check is a real eligibility requirement, not something to bypass. | `GATEWAY`, `OFFICIAL_QUOTA`; verify current campaign availability before depending on it. | `https://www.mobike.io/docs/`; offer `https://www.mobike.io/event.html`; API base shown in docs `https://api.apibridge.io/v1` |

## 2.3 Monthly recurring allowances — official or vendor-published

| Service | Recurring allowance | Conditions / caveats | Type and evidence | Source |
|---|---|---|---|---|
| **Gonka Broker** | At least 1M tokens/month of any catalog model, renewed on the 1st of each calendar month; cheaper models yield more. Unused grant expires monthly. | Email/Google account + API key; no card. Current official billing docs say free tier is tied to a verified mobile phone number, one tier per number; phone verification is required to receive the grant. | `GATEWAY` to decentralized Gonka GPU network, `OFFICIAL_QUOTA`; phone requirement noted. | `https://gonkabroker.com/free-llm-api/`; docs `https://docs.gonkabroker.com/guides/billing-and-deposits/`; base `https://proxy.gonkabroker.com/v1` |
| **Clean APIs** | Vendor pricing page says 5M tokens/month, no card; third-party tracker history reports the offer was reduced to 0.5M/month and flags it as suspicious/unverified. | Account required. Conflicting vendor/tracker status and risk flag mean do not present as reliable until the live account/dashboard confirms the amount. | `GATEWAY`, `CONFLICTED`, not counted as a dependable recommendation. | Vendor `https://www.cleanapis.com/pricing`; tracker review `https://aifree.dev/provider/clean-apis` |
| **Cohere Trial API** | 1,000 API calls/month; Chat 20 RPM and Embed 5 RPM. | Trial key; evaluation/non-production only. Monthly allowance, not daily. | `INDEPENDENT`, `OFFICIAL_QUOTA`. | `https://docs.cohere.com/v1/docs/rate-limits` |

## 2.4 Ongoing free API access, but no universal daily/monthly number published

| Service | What is actually documented | Classification / caveat | Source |
|---|---|---|---|
| **Google Gemini API / AI Studio** | Free tier exists for selected models; RPM/TPM/RPD vary by model and project, displayed in AI Studio; daily quota resets at midnight Pacific. No single universal number. | `INDEPENDENT`, `OFFICIAL_RATE_AND_MODEL_QUOTAS`. Free-tier data may be used to improve Google products; do not send confidential data under free-tier terms. | `https://ai.google.dev/gemini-api/docs/pricing` |
| **Z.ai / GLM Flash** | Selected Flash models (GLM-4.7-Flash, GLM-4.5-Flash, GLM-4.6V-Flash) are listed at zero input/output price; amount/period not published. | `INDEPENDENT`, `OFFICIAL_FREE_MODELS`, no numeric daily grant confirmed. | `https://docs.z.ai/guides/overview/pricing`; API `https://api.z.ai/api/paas/v4` |
| **SenseNova** | SenseNova 6.8 Flash Lite reported with console Points quota; exact amount/period not published. A zero-star project author reported signup and a successful generation test (Oct 31, 2026). | `INDEPENDENT`, `REPORTED_TEST`; not independently tested here, and Points are not necessarily tokens. | `https://token.sensenova.ai/v1`; report `https://github.com/aditya1271/free-llm-list` |
| **NVIDIA Build / NIM** | Free hosted NIM endpoints for prototyping; per-model limits/concurrency vary and are not a stable universal daily allowance. | `INDEPENDENT`, free prototyping access; keep separate from a guaranteed daily quota or trial-credit claim. | `https://build.nvidia.com/`; API `https://integrate.api.nvidia.com/v1` |
| **OpenTyphoon** | Official rate-limit page states 200 RPM for selected Typhoon models and 20 RPM for OCR; no daily token grant established from that page. | `INDEPENDENT`, `OFFICIAL_RATE_ONLY`; do not mislabel RPM as daily quota. | `https://docs.opentyphoon.ai/en/rate-limits/` |
| **SEA-LION (AI Singapore)** | Free API key/trial access and 10 RPM/user reported in docs; no recurring daily allowance published. | `INDEPENDENT`, trial/prototyping access; daily quota unspecified. | `https://docs.sea-lion.ai/guides/inferencing/api` |
| **Nous Portal** | Portal lists free models only with standard rate limits and $0 monthly credits; current portal's free inference availability differs from older claims of a dedicated free API model allowance. | `GATEWAY/PORTAL`, `CONFLICTED_SCOPE`; do not count as a quantified daily quota until a usable API key and model entitlement are confirmed. | `https://portal.nousresearch.com/` |
| **Hetzner Inference API (Experiments)** | Experimental hosted inference reported free while the API is experimental; no published daily allowance located. | `INDEPENDENT`, experimental; quota/continuity unspecified. | `https://inference.hetzner.com/api/v1` |
| **ModelScope API-Inference** | Uses Magicubes/credits and dynamic concurrency; no verified recurring free daily token allocation in this research. | `INCOMPLETE`; do not count as a recurring free API tier without current official credit terms. | `https://www.modelscope.cn/` |

## 2.5 Free-looking offers that are not clean recurring no-payment tiers

| Service / candidate | Current finding | Correct classification |
|---|---|---|
| **OpenRouter higher free limit** | 1,000 free-model requests/day requires at least $10 lifetime credit purchase. | `TOPUP_REQUIRED` for the higher limit; the basic 50/day remains no-purchase. |
| **InferAll** | Free daily request table exists, but its pricing page says ongoing free NIM access requires a $5 activation (credited to spendable balance). The no-card key is a trial allowance, not the same as activated recurring tier. | `TOPUP_REQUIRED`; keep out of strict no-payment recurring list. |
| **SambaNova** | Historic free-tier figures circulate, but current plan information indicates payment method/credit purchase is needed to run requests. | `CARD_REQUIRED/TOPUP_REQUIRED`; not a dependable no-card free tier. |
| **Cerebras** | The commonly quoted 1M tokens/day belongs to a trial/activation offer in current sources, not a guaranteed no-purchase recurring tier. | Move to Section 3 (Trials) unless current official free-tier terms prove otherwise. |
| **Token Harbor** | Rolling free model allowance is documented. | `ACCOUNT_REQUIRED / FREE_API_ALLOWANCE`; see current official terms and API documentation for account conditions. |
| **NVIDIA** | Prototyping endpoints are free, but there is no stable universal daily quota. | Free access, not a numeric daily quota; Section 2.4. |
| **Mistral** | Current Free Mode does not include API access; API usage requires billing activation. | Exclude from no-cost API list. |
| **GitHub Models** | Retired July 30, 2026. | `EXPIRED/SHUT_DOWN`. |
| **Hugging Face Inference Providers** | Earlier free monthly credits no longer apply under current free-account terms found in this research. | Exclude from current recurring free list. |
| **LLMTR** | Daily allowance campaign ended Nov 5, 2026. | `EXPIRED`; preserve as historical record. |
| **FreeTheAI** | Earlier daily quota claims conflict with reports that the free tier was disabled for most accounts in November. | `CONFLICTED/NEEDS_RECHECK`; not counted as confirmed. |
| **FreeAIapikey** | Advertised daily allowance appears gated behind a $5 top-up. | `TOPUP_REQUIRED`. |
| **APInex** | Large daily token allowance only after a qualifying top-up. | `TOPUP_REQUIRED`. |
| **AIHubMix** | Daily shared allowance requires at least $1 top-up; small initial trial calls are one-time. | `TOPUP_REQUIRED`; initial calls belong in Section 3. |
| **Infron** | Free models require a $5+ balance/top-up under current reported terms. | `TOPUP_REQUIRED`. |
| **BlazeAPI** | Official Free plan lists zero daily tokens; a separate free endpoint may exist but needs proof. | Not counted; `CONFLICTED/NEEDS_API_VERIFICATION`. |
| **Onomeo** | 30 free calls per five hours are described for its reward/chat flow, but no proof that this quota applies to the API using the user's own key. | Not counted as API quota; `NEEDS_API_VERIFICATION`. |
| **LLM7** | Auth requirements conflict; bearer placeholder behavior is not proof of a free personal API key tier. | `NEEDS_API_VERIFICATION`. |
| **OrcaRouter** | Third-party test ledger reports 50 requests/day per workspace and 10 RPM; established GitHub account linkage is required. Free model inventory was not currently enumerated in the reviewed provider page. | `GATEWAY`, `REPORTED_TEST`; provisional, verify current model list and key access. |
| **UnoRouter** | Tracker reports 105 `:free` models and 1 RPM/model, but a clear daily account allowance and current official terms were not established. | `GATEWAY`, `TRACKER_ONLY`; do not equate 1 RPM with a daily quota. |
| **GW BUS** | Tracker reports $5 signup credit plus 1M tokens/day; official terms and the separation between recurring daily quota and one-time signup credit were not confirmed. | `GATEWAY`, `TRACKER_ONLY`; signup credit belongs in Section 3. |
| **EURI by Euron** | Tracker reports 10K tokens/day, but official current quota documentation was not found. | `GATEWAY/PROVIDER UNCLEAR`, `TRACKER_ONLY`. |
| **WanAPIs** | Daily check-in credit reported; amount and API applicability not verified. | `TRACKER_ONLY`; possibly reward credit rather than guaranteed free inference. |
| **TokenFaucet** | Daily lucky-draw token rewards reported; API endpoint and guaranteed amount unclear. | `TRACKER_ONLY`; variable reward, not a fixed quota. |
| **CrowLLM** | Free model variants reported, but numeric allowance unclear. | `GATEWAY`, `TRACKER_ONLY`. |
| **LLM Gateway** | Zero-priced models and per-model short-window limits reported; no clear daily account allowance verified. | `GATEWAY`, `TRACKER_ONLY`. |
| **Clean APIs** | Vendor claims 5M/month; third-party offer history says 0.5M/month and flags the offer as suspicious/unverified. | `CONFLICTED`; don't count as reliable until resolved. |
| **FreeInference (Harvard MadSys Lab)** | Research service discovered, but current public API quota/terms were not verified in this pass. | `RESEARCH SERVICE`, `NEEDS_RECHECK`. |
| **100milionseek milestone bonus** | Temporary 400M/day window ended Nov 20, 2026; current advertised base is 100M/day. | Bonus is expired; base quota remains listed separately above. |
| **Alibaba Cloud Model Studio** | New-user 1M-token-per-model offers for a limited period/region are promotional onboarding credits, not perpetual recurring quota. | Move to Section 3 (Trials/promotions). |
| **Tencent EdgeOne Makers** | 500K/month claims appear tied to a limited promotion and need current eligibility confirmation. | `PROMOTIONAL/NEEDS_RECHECK`; likely Section 3 unless renewal terms are explicit. |
| **IteraCompute** | Temporary free Auto access campaign ends Nov 24, 2026. | `TIME_LIMITED_PROMOTION`; not a permanent recurring tier. |
| **GonkaRouter** | 1M free tokens reported as one-time new-account credit, unlike Gonka Broker's monthly recurring tier. | Section 3 (one-time signup credit), not recurring. |
| **SiliconFlow** | New-account $1 credit is one-time. | Section 3. |
| **Cerebras trial credit** | Time-limited/activation-linked. | Section 3. |

## 2.6 Additional candidates preserved for further verification

These names were found during tracker, repository, or community discovery. They are deliberately retained even where no reliable recurring quota has been established. Do not promote them to the confirmed table without checking current official terms and making a real API call where feasible.

- **DGrid** — official docs now establish API-key access and a free `dgridai/free` route with 10 RPM / 100 RPD before any qualifying top-up. `GATEWAY`, `OFFICIAL_QUOTA`; do not use the higher 1,000 RPD tier as a free allowance because it requires qualifying spend. The underlying model can change.
- **NFlashX** — new candidate; recurring API quota not established.
- **AMD Token Lab** — new candidate; free API access/renewal details not established.
- **Mango Inference** — new candidate; current allowance not established.
- **Regolo.ai** — new candidate; current recurring free API allowance not established.
- **EXAONE API Platform / LG K-EXAONE 2.5** — new candidate; account, region, and free API quota need checking.
- **Baichuan AI** — new candidate; current free API quota needs checking.
- **Baidu Qianfan** — new candidate; distinguish free model quotas from new-account promotional credits.
- **rout.my** — free-labelled models reported; API daily allowance not established.
- **BazaarLink** — free models and trial credits reported; recurring quota vs one-time trial not resolved.
- **Flexlora** — candidate from discovery sources; current API route and allowance need checking.
- **Synap** — official product page advertises 100K model tokens/day, 50 requests/day and 10 RPM for its free Qwen3 Coder 30B route. Free capacity may be exhausted and return 503; verify live dashboard and reset terms. `GATEWAY/ROUTER`, `OFFICIAL_QUOTA` (published offer; not independently load-tested).
- **Typhoon API** — official 200 RPM limits for selected models, but daily free grant not found; classify as rate-limit-only pending quota proof.
- **ModelScope API-Inference** — credit-based service; no verified recurring free quota.
- **Tencent Cloud TokenHub** — reported free model activation may freeze a balance; not a clean no-cost allowance until financial requirement is clarified.
- **FreeAIapikey** — keep historical daily-quota claim, but mark top-up-gated pending fresh official proof.
- **APIBridge** — 10K/day offer is documented, but identity verification and campaign eligibility should be checked at signup.
- **Kiosapi.id** — retain as a regional hidden gem; verify API key generation and live free model availability before production use.

### Newly reviewed additions (23 November 2026) — retain uncertain entries explicitly

The entries below are deliberately not all promoted to the confirmed-quota table. “Official page found” means a vendor page exists; it does not mean the API was independently called or that a free quota is universally available.

- **A4F** — `https://api.a4f.co/v1`; gateway. Official pricing page advertises a free plan with 5 RPM and 300 RPD, while its rate-limit documentation says the typical free limit is 100 RPD. Mark `OFFICIAL_QUOTA`, `CONFLICTED`; use 100 RPD as the conservative documented figure until the account dashboard resolves the discrepancy. No independent generation test in this research pass.
- **Logfare** — `https://logfare.ai/v1`; gateway. Official docs state 500 RPD during the first 24 hours, then 5,000 RPD on Standard, with 40 RPM and 1,000/hour. Requires free account/key and continued membership in Logfare Discord; usage is logged for research/data purposes. Mark `OFFICIAL_QUOTA`; no independent generation test in this pass.
- **Aion Labs** — `https://api.aionlabs.ai/v1`; independent provider. Official rate-limit docs state Free tier defaults to 15 RPM, 20K TPM and 20K daily tokens; official pricing says no card. Mark `INDEPENDENT`, `OFFICIAL_QUOTA`; quota is small and should not be confused with a 20K requests/day allowance. No independent generation test in this pass.
- **PEKPIK LLM** — aggregator/gateway. Official page describes a daily claim of credit (up to $20 accumulated over the first 40 days, with daily claims continuing); 10 RPM. This is a recurring daily credit reward, not a fixed model-token quota. Mark `GATEWAY`, `OFFICIAL_RECURRING_CREDIT`; verify that the claim button and API balance remain available.
- **iFlytek Spark Lite** — `https://spark-api-open.xf-yun.com/v1`; provider API with APIPassword. Spark Lite is advertised as free, but the exact recurring allowance was not published in the sources reviewed. Identity/real-name verification may apply and should be checked in official signup flow. Mark `FREE_MODEL_QUOTA_UNPUBLISHED`, `NEEDS_RECHECK`; do not invent an RPD or token figure.
- **Aiven AI Gateway (`aiven-model` router)** — official docs describe this router as free when AI Gateway is enabled for an organization and an API key is configured. No numeric daily/monthly quota was published in the reviewed docs; organizational enablement/early-access approval may be required. Mark `OFFICIAL_FREE_ROUTE`, `QUOTA_UNPUBLISHED`, `ACCESS_RESTRICTED`; not a quantified daily quota.
- **ModelScope API-Inference** — Magicube-metered inference; current quota is dynamic and the old blanket 2,000 calls/day claim was removed from the official limits. Daily login rewards are reported by third parties, but recurring free API allocation was not established from current official documentation. Mark `TRACKER_ONLY`, `NEEDS_OFFICIAL_QUOTA_CONFIRMATION`; do not quote 2,000 RPD.
- **LG EXAONE API Platform** — discovered in current free-API trackers as a no-expiry/free API offer, but a reliable official numeric quota, region eligibility and API-key onboarding were not established in this pass. Mark `TRACKER_ONLY`, `UNVERIFIED`; do not present as a confirmed free API until official docs and API access are checked.
- **NFlashX** — tracker reports a $1 welcome credit for the first 100 accounts and a free Flash model, with 2 RPM and 4K output. No clear recurring daily/monthly grant was established; the welcome credit belongs in Section 3 unless recurring terms are found. Mark `TRACKER_ONLY`, `TRIAL_OR_PROMOTION`, `UNVERIFIED_RECURRING`.
- **Baidu Qianfan / AppBuilder** — sources mention 100 uses/day for a specific AppBuilder service or search component, but that does not establish a general LLM inference API quota. Mark `SERVICE_SPECIFIC_CANDIDATE`, `UNVERIFIED_FOR_GENERAL_LLM_API`; require the exact endpoint and model before inclusion as a general inference provider.
- **Novita AI** — included in strict no-card/free-tier discovery lists, but this pass did not establish a current, recurring, no-purchase API allowance with an exact quota from official docs. Mark `UNVERIFIED_RECURRING_QUOTA`; keep separate from signup/trial credits.
- **Mixlayer** — discovery sources mention free access to selected small models (including Qwen family), but exact account requirements, daily/monthly quota and renewal were not established from official docs in this pass. Mark `TRACKER_ONLY`, `UNVERIFIED`.
- **Inferbase** — third-party quota table reports 5K requests/month plus a 100-request / $0.50 shared daily usage figure. Official terms and the meaning of the shared $0.50 wallet were not verified. Mark `TRACKER_ONLY`, `UNVERIFIED`; do not state this as a guaranteed free quota.
- **FreeInference (Harvard MadSys Lab)** — research/education API candidate; current public quota, account eligibility and recurring renewal were not verified. Mark `RESEARCH_SERVICE`, `UNVERIFIED`.
- **InferAll** — sources conflict on whether it offers 25 initial calls plus 25/day. The API route, renewal behavior and current eligibility were not confirmed. Mark `CONFLICTED`, `UNVERIFIED`.
- **FreeTheAI** — earlier tracker reports 50 requests/day plus a Discord reward, but reports indicate the free tier may be disabled for many accounts. Mark `CONFLICTED`, `NEEDS_LIVE_RECHECK`; do not include in confirmed totals.
- **OrcaRouter** — reported 50 requests/day and 10 RPM, but current official free-model inventory and key eligibility remain unclear. Mark `GATEWAY`, `REPORTED_TEST`, `UNVERIFIED_CURRENT_AVAILABILITY`.
- **UnoRouter** — tracker lists many `:free` models and per-model short-window limits, but no verified daily allowance. Mark `GATEWAY`, `TRACKER_ONLY`, `DAILY_QUOTA_UNKNOWN`.
- **GW BUS** — tracker reports a daily token allowance alongside a signup credit; official terms and the recurring component are not confirmed. Mark `GATEWAY`, `TRACKER_ONLY`, `UNVERIFIED`; keep signup balance separate in Section 3.
- **EURI by Euron** — tracker reports 10K tokens/day, but current official quota documentation was not located. Mark `TRACKER_ONLY`, `UNVERIFIED`.
- **WanAPIs / TokenFaucet** — daily check-in or lucky-draw credits are reported, but API applicability, guaranteed amount and renewal conditions are unclear. Mark `TRACKER_ONLY`, `REWARD_CREDIT_UNVERIFIED`.
- **CrowLLM / LLM Gateway / rout.my** — free model labels or short-window limits are reported, but no dependable recurring daily/monthly API grant was verified. Mark each `GATEWAY_OR_PROVIDER_UNCLEAR`, `TRACKER_ONLY`, `QUOTA_UNVERIFIED`.
- **AMD Token Lab, Mango Inference, Regolo.ai, BazaarLink, Flexlora** — retained as discovery candidates; current official API routes and recurring free allowances were not established. Mark `UNVERIFIED`; BazaarLink may mix one-time trial credits with free-model routing.
- **Tencent Cloud TokenHub** — reported free model activation may freeze or require a balance; whether it is a genuinely no-payment recurring API allowance is unresolved. Mark `CONFLICTED`, `FINANCIAL_CONDITION_UNVERIFIED`.
- **KRAFTON Raon-1 mini** — free launch offer appears time-limited rather than a stable recurring allowance. Keep as `PROMOTIONAL`, likely Section 3, pending current campaign terms.
- **OpenAI API data-sharing allowance** — third-party trackers report an opt-in data-sharing program with an account-specific free token allowance, but this pass did not confirm the claim in current official OpenAI API pricing/terms. Mark `UNVERIFIED`, `DATA_SHARING_CONDITION_REPORTED`; do not recommend enabling data sharing solely for credits until official terms are checked.


## 2.7 High-value discovery sources used in this expansion

These are discovery/research sources, not substitutes for official provider terms:

- Free LLM API Tracker: `https://freellmapi.link/`
- llmlatency free tiers and testing: `https://llmlatency.dev/`
- aiymao credits tracker: `https://aiymao.com/api-credits/`
- aifree offer history and verification: `https://aifree.dev/`
- mvalentsev's provider-level test ledger (includes obscure providers and real probe dates): `https://mvalentsev.github.io/awesome-free-ai-coding/`
- zero-star / low-star API test repository: `https://github.com/aditya1271/free-llm-list`
- F24 SALES live API probe catalogue: `https://www.f24-sales.com/`
- Requesty free API guide: `https://www.requesty.ai/blog/free-llm-apis`

## 2.8 Practical notes before sharing publicly

1. State the date checked beside every quota; free tiers change frequently.
2. Say whether a limit is requests/day, model tokens/day, internal credits/day, compute Neurons/day, or a monthly wallet. Never call all of these “tokens”.
3. Clearly mark gateways and resellers; the upstream model owner and its privacy/data policy may differ from the gateway.
4. A free API key is a secret. Do not paste it into a public Facebook post, browser frontend, public GitHub repository, or shared screenshot.
5. Read the provider's privacy/training terms. Free-tier prompts may be logged, reviewed, or used to improve models. Logfare explicitly describes research/data logging; Gemini's free-tier terms permit product improvement use.
6. Treat 429/503 as a reason to back off and respect `Retry-After`; do not rotate accounts, keys, IPs, or identities to evade quotas.
7. Never treat a model catalogue, playground, browser chat reward, or `/models` response as proof that the same free allowance applies to API inference.
8. Recheck the exact model ID and free label before integration. Free model IDs can rotate or expire.
9. Keep one-time trial balances and promotions in Section 3, even if the same vendor also has a recurring free tier.
10. Do not use GitHub stars as a quality or trust signal. Inspect docs, terms, API routes, actual responses, maintenance, and ownership.

**Section 2 status:** substantially expanded, but not fully closed. The confirmed tables are supported by vendor-published quotas; tracker-only and conflicted candidates remain preserved below them for follow-up. Section 3 (one-time trials/promotions) has not been added in this update.

# Section 3 — One-time API trials, signup credits, and temporary promotions

**Scope:** this section contains credits or token allowances that are granted once, expire, run down, or are tied to a temporary campaign. They are not recurring free tiers. A provider may appear in both Section 2 and Section 3 only when it genuinely has two separate offers; never add its trial balance to its recurring quota.

## 3.1 Evidence labels for trial offers

- `OFFICIAL_TRIAL`: the provider's own current documentation or pricing page describes the grant.
- `OFFICIAL_CAMPAIGN`: official campaign page, but eligibility, region, or dates may be limited.
- `OFFICIAL_AMOUNT_UNPUBLISHED`: provider confirms credits but does not disclose the amount or expiry.
- `TRACKER_ONLY`: amount or terms come from a third-party tracker; not yet confirmed in current official terms.
- `CONFLICTED_TERMS`: official pages or credible sources disagree on amount, expiry, or eligibility.
- `CARD_REQUIRED`: a payment method must be attached to activate/use the trial. This is not the same as a charge, but it is a financial-risk condition.
- `REGION_RESTRICTED`: the offer is limited to a country/region or a specific regional console.
- `STALE_OR_HISTORICAL`: offer is old, expired, or not confirmed to remain available.
- `NON_LLM_API`: speech, audio, image, or general cloud credit rather than text-LLM inference; retained in a clearly separate subsection.

A listed credit is not a promise that every new account qualifies. Always check the live console before relying on it. Do not attach a payment method merely to claim a trial unless the user independently understands the billing and auto-charge implications.

## 3.2 Strong candidates — provider-published or official-page-backed trials

| Provider | Trial offer reported | Conditions / caveats | Classification |
|---|---|---|---|
| **Cerebras Inference** — `https://cloud.cerebras.ai/` | $5 one-time promotional credit | Current third-party verification says a valid payment method is required; credit expires 30 days after grant. No permanent free tier. Treat card attachment as a material condition. | `OFFICIAL_TRIAL`, `CARD_REQUIRED` |
| **AI21 Labs / Jamba API** — `https://www.ai21.com/` | $10 trial credit for new accounts | Expiry conflicts: pricing page reportedly says 7 days while docs say 3 months. No card required according to the current comparison source. Confirm the actual grant/expiry in the account. | `OFFICIAL_TRIAL`, `CONFLICTED_TERMS` |
| **Nebius Token Factory** — `https://nebius.com/` | $25 Token Factory credit through the free Nebius Builder Program | Requires joining the program and email verification; reported expiry is 90 days after issuance. The program may include additional partner credits, which are not Token Factory inference credit. | `OFFICIAL_CAMPAIGN`; expiry/eligibility recheck |
| **Sarvam AI / Token Factory** — `https://www.sarvam.ai/` | ₹100 free credits for each verified user | Official API pricing docs say credits can be used across its APIs, do not expire, and stop when exhausted. This is a one-time wallet grant, not a recurring monthly/daily quota. Official OpenAI-compatible Token Factory endpoint is `https://api.sarvam.ai/v2`. | `OFFICIAL_TRIAL`, `VERIFIED_USER`, `NO_EXPIRY_STATED` |
| **Volcano Engine Ark / Doubao** — `https://www.volcengine.com/` | New-user free inference quota; official docs show model-specific initial free usage, including 500,000 tokens in an example | Per-model allocation, shared under the main account; the amount/availability depends on model and region. Do not generalize the example to every model or every region. Primarily mainland-China platform. | `OFFICIAL_CAMPAIGN`, `REGION_RESTRICTED`, `MODEL_SPECIFIC` |
| **Tencent Cloud TokenHub** — `https://cloud.tencent.com/` | Reported 1,000,000 free tokens per language model, once per account | Current third-party survey says valid for one year after claiming and campaign runs through 31 December 2026; official eligibility and precise model coverage still need a fresh check. Mainland-China platform. | `OFFICIAL_CAMPAIGN_REPORTED`, `REGION_RESTRICTED`, `NEEDS_RECHECK` |
| **Fireworks AI** — `https://fireworks.ai/` | $1 starter credit for new accounts | Credit is one-time; after exhaustion, continued API use requires paid credits/payment setup. Current trackers report no ongoing free allowance from this credit. | `OFFICIAL_TRIAL`, amount cross-checked by current trackers |
| **Baseten** — `https://www.baseten.co/` | New workspaces receive evaluation/deployment credits | Baseten confirms new-workspace credits in billing documentation but does not publish amount or expiry; it explicitly has no perpetual free tier. Without a payment method, models may be deactivated when credits run out. | `OFFICIAL_AMOUNT_UNPUBLISHED` |
| **Upstage** — `https://www.upstage.ai/` | $10 free credit on signup | Third-party comparison reports this amount; expiry was not stated. Needs current official pricing/signup confirmation before being called fully verified. | `TRACKER_ONLY`, `NEEDS_OFFICIAL_RECHECK` |
| **Perplexity API** — `https://www.perplexity.ai/` | $10 signup credit for some new accounts | Not every account reportedly receives it; reported expiry is 60 days after grant. Treat as conditional, not guaranteed. Confirm on the account billing page. | `TRACKER_ONLY`, `ELIGIBILITY_CONDITIONAL` |
| **SiliconFlow** — `https://siliconflow.com/` | $1 credit reported for new accounts | Offer/terms vary between the international platform and China platform; free model offers on the China site are not automatically available to international API accounts. | `TRACKER_ONLY`, `REGION_OR_PRODUCT_VARIANT` |
| **Alibaba Cloud Model Studio / DashScope** — `https://www.alibabacloud.com/` | Typically 1,000,000 free tokens per eligible model for new users | Reported validity: 90 days. Current comparison describes Singapore region and International deployment scope specifically. Per-model grant; do not assume all models or regions qualify. | `OFFICIAL_CAMPAIGN_REPORTED`, `REGION_RESTRICTED`, `MODEL_SPECIFIC` |
| **Nscale Serverless Inference** — `https://www.nscale.com/` | $5 starter credit for new accounts | Docs changelog reportedly mentions the credit; quickstart says early users may be eligible. The official tracker says confirm it appears in the console. No daily quota; requests fail when credit is exhausted. | `OFFICIAL_TRIAL_REPORTED`, `ELIGIBILITY_UNCERTAIN` |
| **Novita AI** — `https://novita.ai/` | $100 promotional credits for eligible Novita Agent Sandbox usage | Important: the current verified tracker says this is for Agent Sandbox CPU/RAM/storage, and does **not** establish that the credits apply to Model API inference. Do not count as LLM API credits. | `OFFICIAL_CAMPAIGN_REPORTED`, `NOT_CONFIRMED_FOR_MODEL_API` |
| **NLP Cloud** — `https://nlpcloud.com/` | $15 trial credit on pay-as-you-go | Reported to require a card. Its separate free plan allows limited testing of selected models; do not merge that free plan with the paid-plan trial credit. | `OFFICIAL_TRIAL_REPORTED`, `CARD_REQUIRED` |
| **Anthropic API** — `https://www.anthropic.com/` | A small amount of free credit reportedly appears for some new API users | Amount and expiry not published in the current comparison. Do not confuse Claude.ai chat access with API credit. | `TRACKER_ONLY`, `AMOUNT_UNPUBLISHED` |
| **OpenAI API** — `https://openai.com/` | No reliable generally available new-account trial grant established in this pass | Do not list a signup credit as guaranteed. Third-party claims about opt-in data-sharing allowances are not confirmed here and remain in Section 2's unverified ledger. | `NOT_CONFIRMED` |

## 3.3 Other trial candidates — keep, but do not present as fully verified

These are useful leads from current trackers and comparisons. They remain visibly unverified until the official offer page, eligibility, expiry, and API applicability are confirmed.

| Provider | Reported offer | Why it remains unverified / caveat | Classification |
|---|---|---|---|
| **Inception Labs / Mercury** — `https://inceptionlabs.ai/` | 100 million free tokens with each new API key | Reported by current offer trackers, but this research pass did not capture a directly inspected official terms page establishing duration, model scope, or whether every new key qualifies. | `TRACKER_ONLY`, `UNVERIFIED` |
| **Jina AI** — `https://jina.ai/` | 10 million free tokens with every new API key | Reported by a current comparison pack; exact API products covered, expiry, and current official terms were not confirmed in this pass. | `TRACKER_ONLY`, `UNVERIFIED` |
| **Hyperbolic** — `https://www.hyperbolic.ai/` | $1 credit after phone verification | Reported as a one-time credit; the same report says phone verification is required to use the API. Do not attempt to bypass identity/phone checks. | `TRACKER_ONLY`, `PHONE_VERIFICATION_REPORTED` |
| **Sarvam AI** — `https://www.sarvam.ai/` | Separate reports mention a 60-minute free dubbing allowance | This is an audio/dubbing product allowance, not the same thing as the ₹100 API credit. Current official docs show the 60-minute allowance for new accounts. Keep it separate from LLM tokens. | `OFFICIAL_CAMPAIGN`, `NON_LLM_API` |
| **Camb.ai** — `https://www.camb.ai/` | 5,000 one-time credits across speech, dubbing, and translation tools | Third-party source reports no monthly renewal; precise API applicability and expiry were not confirmed in this pass. | `TRACKER_ONLY`, `NON_LLM_API`, `UNVERIFIED` |
| **Replicate** — `https://replicate.com/` | Free runs on selected models for a limited period | Amount, model list, and duration are not stated in the current survey; billing setup may be required after trial. | `TRACKER_ONLY`, `UNVERIFIED` |
| **MixRoute** — `https://mixroute.ai/` | $5 signup credit | Tracker reports one-time credit; current official expiry and API conditions not checked. | `TRACKER_ONLY`, `UNVERIFIED` |
| **OpenAny** — `https://openany.si/` | $0.50 signup credit; launch post reportedly said $1 | Conflicting advertised amount; current homepage reportedly says $0.50 and no expiry. Gateway/aggregator, not an independent model provider. | `TRACKER_ONLY`, `CONFLICTED_AMOUNT`, `GATEWAY` |
| **ngrok AI Gateway** — `https://ngrok.com/` | $1 credit for new accounts | Current tracker reports this, but direct official credit terms and whether the credit is restricted to AI Gateway calls were not verified. | `TRACKER_ONLY`, `UNVERIFIED` |
| **NFlashX** — `https://nflashx.cc.cd/` | $1 welcome credit for the first 100 accounts plus a free Flash model | Credit is limited to the first 100 accounts per tracker; recurring allowance and current availability are unclear. The free Flash model may belong in Section 2 only after its ongoing quota is documented. | `TRACKER_ONLY`, `LIMITED_PROMOTION`, `UNVERIFIED` |
| **NovAI** — `https://aiapi-pro.com/` | $2 signup credit after email verification plus several free Zhipu Flash models | Gateway/aggregator. The recurring/free-model terms and current official credit grant were not independently confirmed. | `TRACKER_ONLY`, `GATEWAY`, `UNVERIFIED` |
| **Nscale** — `https://www.nscale.com/` | $5 starter credit | Early-user eligibility may apply; verify current account dashboard. Kept above as official-page-backed but not universal. | `OFFICIAL_TRIAL_REPORTED`, `ELIGIBILITY_UNCERTAIN` |
| **Baichuan AI** — `https://www.baichuan-ai.com/` | Historical ¥80 signup credit | The available offer is dated May 2024 and reportedly valid for three months from registration. It is not a current 2026 offer unless a new campaign is found. | `STALE_OR_HISTORICAL` |
| **SambaNova Cloud** — `https://cloud.sambanova.ai/` | Some trackers report signup credits/community-earned credits | Other current surveys classify its main API access as a recurring free tier or say the old signup credit is not current. Keep any signup bonus unverified and separate from Section 2's recurring-tier investigation. | `CONFLICTED`, `NEEDS_OFFICIAL_RECHECK` |
| **DeepSeek Platform** — `https://platform.deepseek.com/` | Historical / account-specific credit claims | No current generally available signup credit verified. Do not treat chat-app promotions as API credit. | `NOT_CONFIRMED` |

## 3.4 Non-LLM inference credits — optional adjacent list

These are APIs, but they are primarily speech/audio or general AI services rather than text-LLM chat completion. Keep them separate if the public list is specifically titled “Free LLM APIs.”

- **AssemblyAI** — current tracker reports a $50 signup credit for speech-to-text and Speech Understanding; LLM Gateway is excluded. `TRACKER_ONLY`, `NON_LLM_API`, verify official current offer.
- **Deepgram** — signup credits reported for speech APIs; exact amount/expiry should be checked on the official pricing page before publication. `UNVERIFIED`.
- **Camb.ai** — 5,000 one-time credits reported for speech/dubbing/translation; see Section 3.3. `NON_LLM_API`.
- **Sarvam dubbing** — official docs describe 60 minutes for new accounts; separate from the ₹100 Model API wallet. `OFFICIAL_CAMPAIGN`, `NON_LLM_API`.

## 3.5 Explicit exclusions and traps

- **Together AI:** current research sources disagree; one source claims two zero-priced endpoints, while another says there is no trial and a minimum prepaid purchase is needed. Do not list it as a trial or a free API until a specific endpoint is verified at `$0` and can generate without a balance.
- **DeepInfra:** current sources say pay-as-you-go and require a card or prepayment; no free signup trial established.
- **Hyperbolic:** the $1 phone-verification offer is only a small trial, not a permanent free tier; phone verification must not be bypassed.
- **Hugging Face Inference Providers:** free accounts reportedly have no included monthly inference credits; paid PRO includes a small monthly credit. Not a free trial for a standard free account.
- **GitHub Models:** retired on 30 July 2026; do not list as active.
- **Modal:** reported $30/month compute credit is a recurring compute product allowance, not a ready-made hosted LLM inference API credit. Mention only in a separate “run your own inference” category if needed.
- **AWS / Azure / Google Cloud general startup credits:** broad cloud credits may be used for hosted AI in some circumstances, but are not equivalent to a universally available LLM API trial. Put them in a separate cloud-credit appendix with eligibility, payment, region, and expiry conditions.
- **NVIDIA Build / NIM:** limited hosted-model prototyping access is not necessarily a spendable signup credit. Keep in Section 2's limited evaluation access unless a specific one-time credit balance is shown in the account.

## 3.6 Sources used for this pass (discovery vs official evidence)

- `https://llmlatency.dev/free-llm-api` — current comparison of free tiers and signup credits; useful for leads and observed conditions, not a provider's contract.
- `https://freellmapihub.com/collections/free-signup-credit` — current trial-credit directory; verify its linked provider terms.
- `https://freellmapihub.com/` — provider-by-provider verification notes.
- `https://freellmapi.link/` — discovery tracker; do not treat it as official evidence.
- `https://docs.sarvam.ai/api/getting-started/pricing` — official Sarvam API credit amount, non-expiry, and exhaustion behavior.
- `https://docs.sarvam.ai/api/token-factory` — official OpenAI-compatible endpoint and supported models.
- `https://docs.volcengine.com/docs/ark/free-inference-quota?lang=en` — official Volcano Engine free inference quota conditions.
- `https://docs.volcengine.com/docs/ark/list-model-activations-api?lang=en` — official model activation response showing model-specific initial free usage.
- `https://docs.volcengine.com/docs/arkclaw/Limited-timeTokenEventPurchaseArkClawandreceivea50MmonthTokenExperiencePackage?lang=en` — separate paid ArkClaw campaign; not a free signup offer.

**Section 3 status:** added as a first-pass trial inventory. Officially documented offers are separated from tracker-only claims, conditional offers, and stale promotions. The list is not exhaustive; continue verifying official credit terms and regional eligibility before publishing.

# Research expansion — fresh provider audit (23 November 2026)

This addendum preserves the API three-layer system. New entries are classified by the access method actually documented; gateways are counted once, not once per model.

## Layer 1 — anonymous / keyless API access (new and corrected)

| Provider | Access and current published limits | Models / API surface | Evidence and cautions | Official / primary sources |
|---|---|---|---|---|
| **Kilo AI Gateway** | Anonymous requests to free models, no account or API key; **200 requests/hour/IP**. Free model IDs are marked `:free` or selected stable `kilo-auto/free` routing IDs. | OpenAI-compatible base `https://ai-gateway.kilo.ai/api/v1`; `GET /models`; chat completions. Free roster changes dynamically. | `LAYER_1_KEYLESS_DOCS_VERIFIED / GENERATION_NOT_LIVE_TESTED`. Count Kilo as one gateway. Do not confuse free models with paid models on the same gateway. Kilo's docs say free requests can be routed to upstreams with their own data policies; some NVIDIA trial routes are logged for product improvement. Keep confidential prompts out. | https://kilo.ai/docs/gateway/authentication ; https://kilo.ai/docs/gateway/models-and-providers ; https://kilo.ai/docs/gateway/usage-and-billing |
| **OVHcloud AI Endpoints — anonymous route** | Anonymous access documented at **2 requests/minute/IP/model**. Authenticated tier is 400 RPM/project/model but requires a Public Cloud project and payment method. | OpenAI-compatible API. Public model inventory is dynamic; the reviewed catalogue included Qwen, GPT-OSS, Llama and Mistral text models. | `LAYER_1_KEYLESS_DOCS_VERIFIED / MODEL_SPECIFIC_FREE_CATALOG / GENERATION_NOT_LIVE_TESTED`. The 2-RPM anonymous limit is official. Check the exact model's current price and lifecycle; a rate limit alone does not prove every model is free. Prefer the current OVH API host shown in docs rather than copying older endpoint variants. | https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-getting-started ; https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-troubleshooting ; https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-capabilities |

## Layer 1 companion — public placeholder credential (not strict keyless)

| Provider | Access and quota | Why it is separated | Evidence / source |
|---|---|---|---|
| **AI Horde — OpenAI-compatible text gateway** | Anonymous Bearer sentinel `0000000000`; community volunteer GPU workers; queue priority is lowest for anonymous users and no fixed response-time guarantee is published. Model list and availability change with worker supply. | `PUBLIC_PLACEHOLDER_CREDENTIAL`, not strict no-credential keyless: the request still sends a public placeholder value. Treat every prompt as potentially visible to a volunteer worker; do not send private data. | `LAYER_1B_PUBLIC_SENTINEL / DOCS_AND_CATALOG_REPORTED / NOT_LIVE_TESTED`. API route reported as `https://oai.aihorde.net/v1/chat/completions`. Sources: https://aihorde.net/ ; https://freellmapi.co/free-llm-api-no-signup |

## Layer 2 — recurring free API quotas (new candidates and corrections)

| Provider | Free allowance | API / access | Classification and caveats | Sources |
|---|---|---|---|---|
| **Gizmo Platforms** | Free plan states **1,000 free-model API requests per calendar month**, plus **$1/week included usage** for eligible metered models; zero-cost models remain $0 within quota. API limit 20 requests/minute. | Account and API key. OpenAI-compatible multi-provider gateway; text and selected other model routes. | `LAYER_2_RECURRING / OFFICIAL_PLAN / GATEWAY`. The 1,000-request pool is shared across free-model API calls, not per model. The $1 weekly usage credit is a separate shared dollar-denominated pool and must not be represented as 1,000 extra free calls. Free plan adds a 5% platform fee to paid upstream usage; no card is required to start. Check model roster and plan page before each integration. | https://gizmoplatforms.com/ ; https://gizmoplatforms.com/developers |
| **SenseNova Token Plan** | Official public-beta page lists **1,500 calls per model per rolling 5-hour window** for SenseNova 6.8 Flash Lite and SenseNova U1 Fast; special models excluded. | Account and API key; token plan platform and API documentation. | `LAYER_2_BETA_RECURRING / OFFICIAL_VENDOR_CLAIM / REGION_AND_MODEL_ELIGIBILITY_CHECK`. Beta access can change or end; do not call it permanent. Verify signup, account region, exact model IDs and current API route in the console. Existing older reports of an unspecified “Points” balance are superseded by this published beta quota where the plan applies. | https://www.sensenova.ai/token-plan |
| **BlazeAPI — DeepSeek free route** | Current pricing page advertises **200,000 tokens/day** on DeepSeek models, no card required. | Account/API key; provider gateway. | `LAYER_2_CANDIDATE / OFFICIAL_PRICING_CLAIM / MODEL_AND_GENERATION_TEST_PENDING`. The page does not clearly document every eligible model ID, exact API endpoint, context/rate caps or whether all routes share the same pool. Do not mark `GENERATION_OK` until a real completion succeeds and response usage confirms the free plan. | https://blazeapi.org/pricing |
| **Novita AI — Apodex 1.1 Mini** | A current third-party model catalogue lists this model at $0, but the duration of the free price and any recurring quota are not stated. | Account/key likely required; verify current Novita console and API route. | `LAYER_2_CANDIDATE / ZERO_PRICE_REPORTED / RECURRING_QUOTA_UNDISCLOSED`. Do not describe it as a confirmed permanent free tier until official pricing and generation behavior are checked. | https://novita.ai/ ; discovery snapshot: https://llmlatency.dev/free-llm-api |

## Layer 3 — one-time credits / trial (new cross-modality entry)

| Provider | Offer | API scope | Classification and caveats | Source |
|---|---|---|---|---|
| **deAPI** | New account receives **$5 one-time credits** after email verification; no card; credits expire after **90 days** for the image offer (some model-specific product pages may state a different expiry, so use the dashboard's actual grant expiry). | One API key and shared balance across the platform's LLM, image, video, music and voice model families where enabled. | `LAYER_3_SHARED_SIGNUP_CREDIT / MULTIMODAL_GATEWAY`. Do not count $5 separately in every modality. Model prices differ; the balance is not a recurring allowance. Verify the exact model endpoint and price API before sending. | https://deapi.ai/ ; https://deapi.ai/lp/en/free-image-generation-api |

## Audit corrections and false positives

- **ACLIDE:** its current official documentation says the project has ended and signups/purchases are closed. Remove it from active Layer 2 lists; preserve only as `ENDED / HISTORICAL`. Earlier pages advertising €20/month free credits are stale. Source: https://aclide.com/en/documentation
- **Kilo:** its official docs confirm anonymous free-model access at 200 requests/hour/IP. A `GET /models` success is catalog evidence only; it does not independently prove a specific completion route is healthy at the moment of use.
- **OVHcloud:** anonymous 2 RPM is a real official rate limit. Do not infer a zero-price entitlement for every model; verify the current free model roster and billing label.
- **Cloudflare Workers AI:** current official pricing states 10,000 Neurons/day, resetting at 00:00 UTC. Some newer/high-compute models now require a Workers Paid plan or prepaid AI Gateway credits; do not claim the entire model catalogue is included in the Free plan. Sources: https://developers.cloudflare.com/workers-ai/platform/pricing/ ; https://developers.cloudflare.com/changelog/post/2026-07-28-models-require-workers-paid/
- **Cohere:** evaluation keys are free but limited to 1,000 calls/month (endpoint-specific RPM limits apply); they are intended for evaluation, not production. Keep in the evaluation/trial category, not an unrestricted commercial production tier. Sources: https://docs.cohere.com/v1/docs/rate-limits ; https://docs.cohere.com/v1/docs/cohere-faqs
- **Do not count models as separate providers.** Kilo, OpenRouter and similar gateways are one provider each even when their free model roster contains dozens of model IDs.
- **Do not count self-hosted router software as hosted inference.** FreeLLMAPI is a self-hosted routing application; the upstream provider supplies the actual inference and free quota.

**Verification boundary:** this addendum reviews public documentation and pricing pages dated/retrieved 23 November 2026. No new account was registered and no live generation request was sent. New entries therefore retain `DOCS_VERIFIED`, `VENDOR_CLAIM`, `CANDIDATE` or `NOT_LIVE_TESTED` status rather than being upgraded to `GENERATION_OK`.
