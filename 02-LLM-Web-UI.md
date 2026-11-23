# LLM / Text Generation — Web UI

> Browser-based AI chat and text-generation products. Do not treat their browser limits as API quotas.

## How to use this file

1. Open the official product page linked in the provider entry.
2. If the entry says **anonymous/no signup**, try the public page without creating an account. If it requires login, use the provider's own sign-up flow; do not use unofficial account-sharing methods.
3. Check the actual free allowance shown in the product's current interface. Do not assume browser credits can be used through the API.
4. Generate a short sample first. Confirm whether preview, full generation, download/export, watermark removal and commercial use are included in the free tier.
5. Save/export the result only through the product's supported controls. Check whether outputs expire or are public by default.
6. Review privacy and retention terms before uploading personal audio, images, documents or other sensitive content.

**Important:** Web UI entries are browser products, not developer APIs, unless a separate API entry explicitly confirms an API entitlement.

## Research inventory (preserved from the source catalogue)

# Text, Image and Video AI Web UI Catalogues

> Split edition of the original 23 November 2026 research ledger. Original source line range: 2653–3654. Provider claims and quota snapshots are time-sensitive; read each evidence label and caveat.

# Web UI research — text generation and AI chat (23 November 2026)

This section begins the next research category after the hosted 3D API audit. Scope is **ready-made AI text/chat interfaces that run in an ordinary web browser**, not developer APIs, SDKs, self-hosted frontends, model directories, or local inference apps. A service is counted only when it actually provides text generation/chat in its browser UI. A free web UI does not imply a free API entitlement.

## Classification rules for Web UI — revised five-layer system

Apply these five layers to browser-based text/chat services. Do not reuse the older three-layer labels in this Web UI section.

1. **Layer 1 — anonymous, free and unlimited:** no account or sign-in, and no stated daily/session/message quota or trial expiry. Ordinary abuse prevention may exist, but do not call a service unlimited if the provider documents a usage cap. A service with undisclosed limits is not automatically unlimited; require clear evidence.
2. **Layer 2 — anonymous, free but limited:** no account or sign-in, but a daily, session, message, model, or other usage limit applies. If the exact number is unpublished, record it as `LIMIT_UNDISCLOSED` rather than guessing.
3. **Layer 3 — account required, free and effectively unlimited:** account required, no paid subscription required, and ordinary text chat is explicitly described as unlimited or ongoing without a published usage quota. Separate model/tool/feature caps and abuse safeguards; if the basic text chat itself has a published cap, it does not belong here.
4. **Layer 4 — account required, free but limited:** account required and a recurring/ongoing free allowance exists, but message, points, compute, model, feature, or time-window limits apply. State reset cadence and whether exact quantities are published.
5. **Layer 5 — one-time trial or non-renewing grant:** finite signup credits/messages or time-limited access that does not renew. Clearly separate grants from trials that require a payment card or automatically convert to paid subscriptions. Do not call a permanent free tier a trial merely because it has an initial bonus.

**Evidence rule:** unknown quota does not mean unlimited. Put quota-undisclosed services in the limited layer when the provider only confirms free access but does not promise unlimited use; flag the missing number.

### Important exclusions

- Do not count a provider's API, Playground, or developer console as a consumer Web UI unless a normal browser chat interface exists.
- Do not count free model weights, local inference software, or open-source frontends as hosted AI chat services.
- Do not infer a precise daily message count from anecdotal user reports where the vendor does not publish one.
- Keep multi-model aggregators distinct from model creators. A chat aggregator is one UI/provider, even if it routes to many underlying models.
- Country availability, phone verification, and feature restrictions may differ. Record access conditions without inferring availability across regions.
- Privacy and training policies matter: do not paste passwords, private keys, identity documents, or confidential project material into public chat services.

## Layer 1 — anonymous, free and unlimited

**No provider is confirmed in this research pass.** The reviewed anonymous services either publish a daily/session limit or do not clearly promise unlimited anonymous generation. An unpublished quota is not evidence of unlimited access, so Duck.ai, logged-out ChatGPT, Gemini guest mode, Perplexity guest access and Venice remain in Layer 2 (or a clearly marked candidate within it).

## Layer 2 — anonymous browser chat, free but limited

| Service | Browser text capability | Anonymous allowance / restrictions | Evidence status | Official source |
|---|---|---|---|---|
| Duck.ai (DuckDuckGo) | Multi-model AI chat; writing, summarization, questions | Free with no account; daily cap exists but exact number is not published. Free model roster changes. Anonymous enforcement can behave differently on VPN/mobile networks. | `OFFICIAL_NO_ACCOUNT / DAILY_LIMIT_UNDISCLOSED` | https://duckduckgo.com/duckduckgo-help-pages/duckai ; https://safe.duckduckgo.com/duckduckgo-help-pages/duckai/usage-limits |
| ChatGPT logged-out mode | Standard text conversation | No account in supported countries/networks; only one active conversation at a time; chat is not saved after the session; availability varies by location/network. | `OFFICIAL_GUEST_MODE / REGION_DEPENDENT` | https://help.openai.com/en/articles/9125172-the-chatgpt-home-page |
| Gemini signed-out web mode | Basic text questions and simple text generation | Some web features work without Google sign-in in supported circumstances. No chat history, file upload, image generation, Gems, or other account-bound features; availability can vary by device/country. Android Gemini app requires sign-in. | `OFFICIAL_PARTIAL_GUEST_MODE / AVAILABILITY_DEPENDENT` | https://support.google.com/android/answer/13275745 ; https://support.google.com/gemini/answer/13275745 |
| Perplexity signed-out basic search/chat | AI answers with web citations | Secondary hands-on checks report basic anonymous questions work; Pro Search, saved history, uploads, and advanced model choice require account/paid tier. Exact anonymous allowance is not published by the official pricing page. Keep as a cautious candidate until repeated region-specific testing. | `CANDIDATE_GUEST_MODE / LIMIT_UNDISCLOSED` | https://www.perplexity.ai/help-center/en/articles/11187416-which-perplexity-subscription-plan-is-right-for-you |
| Venice AI text generation | Browser chat, writing, research | Vendor landing page says free to try without sign-up. Exact anonymous message allowance and persistence are not stated on the cited page; verify that generation remains available in a clean signed-out session before relying on it. | `OFFICIAL_NO_SIGNUP_CLAIM / QUOTA_UNDISCLOSED / LIVE_CHECK_NEEDED` | https://venice.ai/text-generation |

### Layer 2 notes — anonymous limited access

- **Duck.ai** is the strongest clearly documented anonymous option in this pass: DuckDuckGo says no account is required, anonymizes conversations, and publishes the existence (but not the numeric size) of a daily usage limit. Its privacy claims are provider claims, not an independent security audit.
- **ChatGPT guest mode** is official, but a logged-out user gets only one conversation at a time and cannot preserve history. Country/network gating means a result observed in one country is not proof of access from Libya.
- **Gemini guest mode** is partial. Do not describe it as the full Gemini experience or promise file/image features while signed out.
- **Perplexity** is best treated as a candidate because current official plan documentation describes the free plan but does not clearly promise anonymous access or publish a guest quota. Secondary browser checks are not a substitute for a current test from the user's region.
- **Venice** explicitly advertises no-sign-up text generation, but no stable quota is published in the cited page. Retain as a candidate rather than ranking it above services with a clearer quota statement.

## Layer 3 — account required, free and effectively unlimited

| Service | Browser text capability | Free-use status | Evidence status | Official source |
|---|---|---|---|---|
| ChatGPT Free — ordinary text chat only | General text conversation | The official Free Tier FAQ describes everyday text chat as unlimited subject to abuse-prevention safeguards. This classification applies only to ordinary text chat; model selection, reasoning, files, images, voice, search and other tools have separate limits and are not unlimited. | `OFFICIAL_UNLIMITED_BASE_TEXT_WITH_ABUSE_SAFEGUARDS / FEATURE_LIMITS_SEPARATE` | https://help.openai.com/en/articles/9275245-chatgpt-free-tier-faq |

**Layer 3 caution:** this is a narrow classification of the basic text-chat allowance, not a claim that every ChatGPT model or feature is unlimited. The official FAQ separates ordinary text from model, file, image, voice and analysis limits. No other service in this pass is promoted to Layer 3 merely because its quota is unpublished.

## Layer 4 — account required, free but limited / recurring

| Service | What the free browser UI offers | Free limits / reset | Evidence status | Official source |
|---|---|---|---|---|
| Claude Free | Browser chat, web search, file creation/code execution, Artifacts and related features | Limited usage every 5 hours and every week; exact message count is dynamic and depends on model, length, complexity, and features. Account required. | `OFFICIAL_RECURRING_FREE / ROLLING_5H_PLUS_WEEKLY` | https://claude.com/pricing ; https://support.claude.com/en/articles/11647753-how-do-usage-and-length-limits-work |
| Gemini without Google AI subscription | Browser chat and standard features; selected tools may have separate access | Standard compute-based limits; current help page says limits can refresh every 5 hours until a weekly cap is reached. Prompt complexity, model, conversation length and features affect consumption. | `OFFICIAL_RECURRING_FREE / COMPUTE_BASED_5H_AND_WEEKLY` | https://support.google.com/gemini/answer/16275805 |
| Perplexity Standard | Search-focused AI answers with citations; basic file uploads | Practically unlimited basic searches; 3 Pro Searches/day and 1 Research query/month in the current plan comparison. Advanced models and image generation are not in Standard. | `OFFICIAL_RECURRING_FREE / PUBLISHED_DAILY_AND_MONTHLY_LIMITS` | https://www.perplexity.ai/help-center/en/articles/11187416-which-perplexity-subscription-plan-is-right-for-you |
| Meta AI | General text chat, writing help, coding help and web answers | Free everyday use. Meta says it is testing daily/monthly limits on some compute-intensive features; no universal numeric chat quota published. Requires an existing Meta account; service and features are not available everywhere. | `OFFICIAL_RECURRING_FREE / FEATURE_LIMITS_UNDISCLOSED / REGION_DEPENDENT` | https://ai.meta.com/meta-ai/assistant/ ; https://www.meta.com/help/artificial-intelligence/943942350800511/ |
| Qwen Chat | General chat, search, coding, artifacts and multimodal features | Official site says free and open to all; the reviewed page does not specify a numeric free quota or exact reset. Account and feature availability should be checked in the live UI. | `OFFICIAL_FREE_CLAIM / QUOTA_UNDISCLOSED` | https://qwen.ai/ |
| DeepSeek Chat | Browser chat with model/reasoning and search features depending on current rollout | Official product materials describe the assistant as free and account-based sign-in options; no stable numeric web-chat quota/reset was found in the reviewed official source. Do not infer unlimited access from “free”. | `OFFICIAL_FREE_CLAIM / QUOTA_UNDISCLOSED` | https://www.deepseek.com/en/download/ ; https://www.deepseek.com/news/deepseek-app/ |
| Poe | Aggregated chat with many official and user-created bots/models | Non-paying users receive a daily points pool that resets every 24 hours; points do not roll over. Cost per reply varies by bot and input/output length. | `OFFICIAL_RECURRING_FREE / DAILY_POINTS_POOL` | https://help.poe.com/hc/en-us/articles/19944206309524-Poe-FAQs |
| Grok on X | Browser text chat and X-context questions | Free access exists for X users, but exact free AI message quota was not specified in the reviewed official help page. Interactions may be used to train/improve xAI models unless the user opts out in privacy settings. | `OFFICIAL_FREE_ACCESS / QUOTA_UNDISCLOSED / DATA_USE_CAUTION` | https://help.x.com/en/using-x/about-grok |
| Mistral Vibe Chat (formerly Le Chat) | General conversational web UI | Free access is presented as a product tier in secondary comparisons, but the current official page reviewed mainly confirms the product rename and does not publish a reliable free-chat quota. Keep as `CANDIDATE` until the current plan page is verified; do not mix its developer API limits with consumer chat limits. | `PRODUCT_CONFIRMED / FREE_UI_QUOTA_NOT_RECONFIRMED` | https://help.mistral.ai/en/articles/682992-le-chat-is-now-vibe |

### Layer 4 notes — account-based limited access

- This layer contains the most useful recurring browser services. Some are general-purpose chatbots; Perplexity is more accurately a search/answer engine, while Poe is a multi-model aggregator.
- **Claude** and **Gemini** use compute-sensitive limits rather than a fixed number of messages. Long prompts and extended conversations can consume more allowance.
- **Perplexity** has the clearest explicit numbers in the reviewed official plan: 3 Pro Searches per day and 1 Research query per month, in addition to basic searches.
- **Poe** is not one model. Its daily points are shared across bots; the points required for each response vary, so a fixed number of daily messages cannot be promised.
- **Meta AI** is region-dependent and uses an existing Meta account. Do not count its availability in a particular country without checking the website there.
- **Qwen and DeepSeek** are worth retaining as free browser interfaces, but exact recurring message/token quotas were not disclosed in the official pages reviewed. Mark them as quota-undisclosed rather than inventing numbers.
- **Grok** needs an X account and has an important data-use caveat: X's help page says Grok interactions may be used to train/improve xAI models unless the relevant setting is changed. Do not paste private or sensitive information.

## Layer 5 — one-time grants and time-limited trials

| Service | Initial free offer | Expiry / renewal | Requirements and caveats | Evidence status | Official source |
|---|---|---|---|---|---|
| Zorvi AI Content Generator | 100 AI credits on signup; includes text/content workflows among other outputs | One-time grant; the $0 plan itself does not expire, but the initial credits do not renew. A separate 30-day trial is advertised. | Account required; no card claimed for starting. Multi-purpose content suite, not a general-purpose frontier-model chat service. | `OFFICIAL_ONE_TIME_CREDITS / NO_RECURRING_CREDIT_GRANT` | https://zorvi.ai/free-ai-content-generator |
| Textcrew | 100 starter credits | Credits last 14 days; no monthly renewal on Free. | Account required; product is an AI operator/workflow interface and can use connected AI plans or its own AI service. Do not count its credits as 100 chat messages. | `OFFICIAL_14_DAY_TRIAL_CREDITS` | https://textcrew.in/pricing |
| Chatari | 1,100 credits per eligible phone number | One-time; expires after 7 days. | US phone numbers only; SMS-based trial; not a practical global browser-only option and therefore not counted as generally available for the user's region. | `OFFICIAL_TRIAL / REGION_RESTRICTED / EXCLUDED_FROM_GENERAL_SHORTLIST` | https://www.chatari.com/ |
| Jasper | 7-day trial of selected plan | Time-limited; converts to paid unless canceled. | Requires a credit card and auto-charges after the trial if not canceled. Recorded for completeness only; not recommended as a no-cost option and not counted among accessible free picks. | `OFFICIAL_CARD_REQUIRED_AUTOCONVERT / CAUTION` | https://help.jasper.ai/hc/en-us/articles/18618674196891-Free-Trial |

### Layer 5 notes — non-renewing trials

- A one-time credit grant is not a recurring free plan. Keep the persistent $0 plan separate from the initial finite credits.
- Zorvi's 100 credits are useful to record, but the service is a content workflow suite, not necessarily a direct open-ended chat experience.
- Textcrew's 100 credits expire after 14 days and may be consumed by workflow actions, so do not translate them into a message count.
- Chatari's offer is tied to eligible US phone numbers and SMS; it is not a broadly accessible browser guest tier.
- Jasper's trial requires a payment card and automatically transitions to paid unless canceled. It is documented as a trial but excluded from the recommended free-access shortlist.

## Reddit/community review — text Web UI

Reddit was reviewed as qualitative evidence for actual usage patterns, not as proof of quotas or account entitlements.

1. **Duck.ai as a no-login multi-model front door:** users and DuckDuckGo's own community announcement repeatedly point to its anonymous access and privacy-oriented routing. The community thread supports discoverability and user interest, while the official help page remains the source for no-account and daily-limit claims. Sources: https://www.reddit.com/r/duckduckgo/comments/1j4vd06/out_of_beta_duckai_chat_and_aiassisted_search/ ; https://www.reddit.com/r/dealhunt/comments/1vypr96/use_gpt56_claude_for_free_on_duckai_no_account_or/
2. **Free stack is usually multi-service:** a community workflow post describes using Claude for long-form drafting, ChatGPT for quick tasks, and Perplexity for cited research. This is a useful role split, not a benchmark and not proof that each service's free limit is generous. Source: https://www.reddit.com/r/PromptEngineering/comments/1rxbq27/the_free_ai_stack_i_use_to_run_my_entire_workflow/
3. **Limits are experienced as variable and difficult to compare:** a free-plan discussion reports users cycling between providers when image uploads or message caps are hit. Another thread notes that Perplexity's free plan may stop accepting questions after only a few searches for some users. These are anecdotes and can reflect account, region, model, and time differences. Sources: https://www.reddit.com/r/LLM/comments/1x6l77r/what_free_llms_should_i_also_add_to_my_list_that/ ; https://www.reddit.com/r/perplexity_ai/comments/1v5d3yg/free_plan_internet_search/
4. **Old recommendation lists are stale:** long-running Reddit lists include services that may have changed login requirements or disappeared. Do not import their old entries as current candidates without a fresh official and live check. Source: https://www.reddit.com/r/ChatGPT/comments/14awyo3/best_chatgpt_website_alternatives_huge_list/
5. **Developer/API lists are not Web UI lists:** community recommendations for free API providers, AI Studio keys, OpenRouter, or Open WebUI were excluded from this section unless a separate consumer browser interface was independently identified.

## Practical shortlist — browser text chat

| Use case | Strong starting options | Why | Main caveat |
|---|---|---|---|
| Anonymous but limited, quick text chat | Duck.ai; ChatGPT guest; Gemini guest (where available) | Can start without a new account; Duck.ai offers multiple models and explicit daily-limit documentation. | ChatGPT/Gemini guest mode is region/device dependent; history is not saved. |
| No-account, web-grounded answers | Perplexity guest candidate | Search-first answers and citations. | Guest mode and quota need current live confirmation; free account plan has published Pro Search/Research limits. |
| Account-based basic text chat with effectively unlimited allowance | ChatGPT Free ordinary text only; limited recurring chat | Claude Free; Gemini Free; Qwen; DeepSeek | Ongoing free browser interfaces with differing model/feature limits. | Exact quotas often dynamic or unpublished; account required for full experience. |
| Multi-model access from one UI | Poe | One interface for many bots; daily free points renew. | Points are shared and model response costs vary. |
| Finite one-time testing | Zorvi; Textcrew | Published initial credit grants or time-limited starter credits. | Not recurring; credits are not equivalent to message counts. |

## Verification boundary and next work

- Research date: **23 November 2026**.
- Official product, help, and pricing pages were reviewed; Reddit was used for qualitative community signals.
- This pass did **not** create accounts, enter phone numbers, add payment cards, or run a systematic clean-browser test from Libya. Therefore region-sensitive guest access and undisclosed quotas remain marked as candidates or unknowns.
- No numeric quota is invented where the vendor does not publish one.
- This section is **text-only Web UI**. It does not yet cover image generation, video generation, music, TTS, STT, 3D web apps, coding environments, or self-hosted frontends.
- Next Web UI subcategory after text should be selected separately; keep the revised five-layer classification.


## Classification correction log — five-layer system

The earlier three-layer Web UI classification has been superseded by the five-layer system above. All Web UI entries in this section are now interpreted as follows: no confirmed Layer 1 service; previous anonymous/no-login entries move to Layer 2; ChatGPT Free ordinary text chat alone is separated into Layer 3 based on the official FAQ's unlimited-everyday-text wording (with safeguards and feature limits); previous account-based recurring free services move to Layer 4; and all non-renewing credits/trials move to Layer 5. This correction applies to the Web UI research section, not retroactively to the separate API research taxonomy.


## Web UI text research — deep Layer 1 audit and Logfare/AIFreeForever correction (23 November 2026)

This addendum corrects the earlier statement that Layer 1 had no candidates. The five-layer Web UI taxonomy remains:
- **Layer 1:** anonymous, free, and unlimited (or explicitly claimed unlimited; evidence confidence must be shown).
- **Layer 2:** anonymous and free, but limited or subject to fair-use throttling.
- **Layer 3:** account required, free, and genuinely unlimited.
- **Layer 4:** account required, free but limited.
- **Layer 5:** one-time trial/credits that do not renew.

Do not confuse “the provider says unlimited” with independently proven unlimited capacity. Keep vendor claim and verification status separate. Also distinguish the consumer chat UI from a provider's API: an API may require a key/account even when the website chat allows anonymous use.

### Layer 1 — anonymous, free, claimed unlimited

| Service | Evidence and features | Classification / caveat | Sources |
|---|---|---|---|
| **AIFreeForever** (`https://aifreeforever.com/`) | The official site explicitly says chat can be started without login, signup, or account; it advertises unlimited text chat and switching among models such as GPT, Gemini Flash, Qwen, Mistral and Meta Llama. It also advertises web search, document/image chat, and a broad set of AI tools. | `L1_VENDOR_CLAIM_UNLIMITED / NO_ACCOUNT_DOCUMENTED / LIVE_QUOTA_UNVERIFIED`. This is a valid Layer 1 entry based on the vendor's explicit promise. However, “no limits” has not been independently load-tested; the actual upstream model, fallback, fair-use enforcement, ad gating, and per-IP throttling are not fully documented. Treat model labels and “official API” claims as vendor statements, not independent proof that each upstream provider directly serves the user. | Official home: `https://aifreeforever.com/`; chat: `https://aifreeforever.com/tools/ai-chat` |
| **ROK guest chat** (`https://rok.rokteam.org/`) | Official page says guest chat needs no email or signup; browser-local chat history. It says a free account unlocks web search, image generation, code execution, uploads, full model lineup and about 8× daily usage. | `L1_ANONYMOUS_ACCESS / UNLIMITED_NOT_ESTABLISHED / AVAILABILITY_CONFLICTED`. Guest access is documented, but the public page does not establish unlimited usage. Its own page currently includes an offline/server-capacity notice and a model cooldown notice, so do not claim dependable always-on service. API is separate and requires a manually issued key; do not count API as keyless. | `https://rok.rokteam.org/` |
| **WKO AI / WebKitOnline** (`https://www.webkitonline.com/free-ai-chat-no-signup/`) | Site describes browser-local inference using WebLLM/WebGPU and open models, no account, no daily cap, and model download cached in the browser. | `L1_LOCAL_IN_BROWSER_CLAIM / DEVICE_DEPENDENT / NOT_HOSTED_INFERENCE`. Keep as a separate subcategory, not equivalent to a hosted AI service: the user's device performs inference and must support WebGPU and download model weights. No provider-hosted quota is consumed, but hardware, browser memory, download size, and performance constrain use. | `https://www.webkitonline.com/free-ai-chat-no-signup/` |

**Layer 1 conclusion:** AIFreeForever is the clearest newly identified hosted-chat candidate that explicitly claims no account and unlimited use. ROK also permits guest chat but does not prove unlimited use. WKO is unlimited-by-local-compute rather than hosted inference and must be labeled separately.

### Layer 2 — anonymous but limited / fair-use

| Service | Evidence and features | Classification / caveat | Sources |
|---|---|---|---|
| **Logfare Chat** (`https://chat.logfare.ai/`) | Separate browser chat product linked from Logfare's main site. Its chat page says “No login required” and exposes anonymous free-tier access. The anonymous tier is distinct from the account tier and premium opt-in. | `L2_ANONYMOUS_FREE / FAIR_USE_LIMITS / QUOTA_UNDISCLOSED`. The chat terms state fair-use throttling may apply; no numerical anonymous quota is published. The existence of a chat UI must not be conflated with Logfare's API: the API requires an account and API key. | Chat: `https://chat.logfare.ai/`; chat terms linked on that page. |
| **UsingOpen** (`https://usingopen.com/free-ai-chat/`) | Its official page describes anonymous, no-account browser chat with 23 open models, and explicitly states 10 prompts per user per day, counted per browser/IP and reset at midnight UTC. | `L2_ANONYMOUS_DAILY_QUOTA / DOCS_CLAIMED`. Strong Layer 2 candidate. A daily quota is explicitly stated, not unlimited. Individual models may be paused due to capacity. | `https://usingopen.com/free-ai-chat/` |
| **Lorik Roo AI Chat** (`https://www.lorikroo.com/ai-chat`) | Official page says no login, no API key, one shared model behind several modes, and up to 10 messages per minute per visitor. It says conversations are not saved between visits. | `L2_ANONYMOUS_RATE_LIMIT / 10_RPM_CLAIMED`. One shared model with different prompt/persona modes, not multiple distinct model providers. A per-minute limit is not the same as a daily quota. | `https://www.lorikroo.com/ai-chat` |
| **AskMe AI** (`https://www.ask-me-ai.app/`) | Official page advertises up to 50 questions per day without account, then offers Google/Apple sign-in to continue and unlock other features. | `L2_ANONYMOUS_50_DAILY_CLAIM`. Daily limit explicitly stated by vendor. | `https://www.ask-me-ai.app/` |
| **Quad Chat** (`https://www.quad.chat/`) | Official page allows anonymous first questions and says account signup is for chat history, files, projects and cross-device sync. | `L2_ANONYMOUS_ACCESS / NUMERIC_GUEST_QUOTA_UNPUBLISHED`. Do not assume unlimited because the public landing page does not publish a guest quota. | `https://www.quad.chat/` |
| **AlgoChat / OpenGPT** (`https://opengpt.chat/`) | Official page says no account and browser chat, with web search and file/image-related features described. | `L2_CANDIDATE / LIMITS_UNPUBLISHED`. No independently established unlimited quota or clear numeric limit. | `https://opengpt.chat/` |
| **Chatzam** (`https://chatzam.com/en`) | Official page advertises anonymous chat with no signup and locally stored chat history. | `L2_CANDIDATE / LIMITS_UNPUBLISHED`. Do not promote to unlimited without an explicit enforceable policy or sustained testing. | `https://chatzam.com/en` |

### Logfare — resolve the API vs Web UI distinction

Logfare is two related but distinct surfaces:
1. **Logfare Chat (`chat.logfare.ai`)**: the browser UI has an anonymous mode, but its own terms state fair use applies. It belongs conceptually in Layer 2, not Layer 1, because anonymous access is subject to fair-use controls and no unlimited entitlement is proven.
2. **Logfare API (`logfare.ai/v1`)**: this is not anonymous/keyless. API requests require account registration and an API key. Current API docs describe standard/premium/pro model tiers, shared request budgets and concurrency controls; current terms also require Discord membership. Do not classify the API as unlimited just because an older or top-level landing-page heading says “No Limits.” The detailed docs and terms describe fair-use/request budgets and access gates.

Sources: `https://logfare.ai/`; `https://logfare.ai/docs`; `https://logfare.ai/tos`; `https://chat.logfare.ai/`.

### Other leads reviewed

- **NoTrack AI** claims anonymous chat; retain its published access and quota claims as vendor statements, with the service terms recorded separately if relevant to a general eligibility audit. `https://notrack.ai/`.
- **EmoCare** is a specialized emotional-support chatbot, not a general-purpose text assistant; do not count it as a general chat model. `https://emo.care/`.
- **Unknown.chat** is an AI-persona/companion chat product rather than a general-purpose assistant; exclude from the general text-chat leaderboard. `https://unknown.chat/`.
- **TapToAgent** is a directory/curation site, not itself a model provider; use its listings only as discovery leads and verify each destination independently. `https://taptoagent.com/`.

### Verification and confidence rules

- AIFreeForever: vendor's no-login/unlimited claim is clear, but no independent quota test or full upstream-provider audit was performed. Keep in Layer 1 with an explicit unverified marker rather than silently downgrading or treating the claim as proven fact.
- ROK: guest access is clear, but the site itself showed server-capacity/offline and model-cooldown notices in the retrieved page; service availability is not stable enough to call it unlimited.
- WKO: no server-side account or API quota is advertised because inference runs locally; classify separately from hosted services.
- Logfare Chat: anonymous UI access and age/fair-use conditions are stated on its own chat page. API and web UI must remain separate entries.
- No live clean-browser test from Libya, systematic long-run quota test, or independent model-routing audit was performed in this pass. Do not mark `GENERATION_OK` or `UNLIMITED_VERIFIED` based only on a landing page.


## Web UI text research — deep account-unlimited audit and new candidates (23 November 2026)

This pass expands the account-based unlimited layer and rechecks the user's Token Harbor discovery. It also separates explicit unlimited claims from capped services whose marketing uses “unlimited” loosely. This is desk research against currently indexed first-party pages; it is not a controlled live test from Libya, and no service below is marked independently unlimited-verified.

### Layer 3 — account required, free and effectively unlimited

| Service | What is actually offered | Quota / restrictions | Evidence status | Official sources |
|---|---|---|---|---|
| **Rudder.chat (Token Harbor)** | Consumer browser chat. A free account is needed to receive an answer: the page allows typing first, then prompts sign-in. Sign-in methods listed are Google, GitHub or email. | Token Harbor explicitly says TH-Rudder text conversations are unlimited during the campaign. The web-chat speed ceiling is 10 messages/minute and 200/hour. Other features are separately capped: 100 voice messages/day, 10 images/day, 5 short videos/day, 200 web searches/day, 20 generated files/day; document storage is 10 MB and conversation storage is capped at 200 conversations. No credit card is required. The text entitlement is campaign-based and the FAQ says the campaign may change; do not call it a permanent contractual guarantee. | `L3_VENDOR_CONFIRMED_UNLIMITED_TEXT_DURING_CAMPAIGN / SPEED_LIMITS_PUBLISHED / CAMPAIGN_DEPENDENT` | Help: `https://rudder.chat/help`; chat: `https://rudder.chat/chat`; Token Harbor FAQ: `https://tokenharbor.ai/faq`; limits: `https://status.tokenharbor.ai/docs/web-chat/limits`; Terms: `https://tokenharbor.ai/terms` |
| **ChatGPT Free — ordinary everyday text only** | General-purpose text chat in browser after account sign-in. | OpenAI's current Free Tier FAQ explicitly says everyday text chats are unlimited subject to abuse-prevention safeguards. Model access and advanced features have separate limits. | `L3_OFFICIAL_UNLIMITED_BASE_TEXT / SAFEGUARDS_AND_FEATURE_LIMITS` | `https://help.openai.com/en/articles/9275245-chatgpt-free-tier-faq` |
| **Tusk Central AI — account models labelled Free Unlimited** | Multi-model chat. Brainiac auto-routing works without login; the other models require a free account. The official page says 20+ of its 49 models are labelled Free Unlimited. | Vendor says those models have no daily cap and no payment details are required. Deep-thinking models and image generation instead use monthly credits. This is a strong Layer 3 candidate for the account-required models, but model-by-model entitlement and live account behavior have not been independently checked. Brainiac is a separate no-login route and should be assessed under Layer 1 only if its anonymous quota is clearly established; the page says it works without login but does not clearly publish a numeric or enforceable anonymous cap. | `L3_VENDOR_CLAIM_FREE_UNLIMITED_MODELS / MODEL_LIST_AND_LIVE_ACCESS_UNVERIFIED` | `https://hello.tuskcentral.ai/free-ai-chat` |
| **BestContent Chat** | Account-based browser chat aggregating GPT, Gemini, Claude and other models. Official page says account creation is required and no card is needed. | The same page makes broad “unlimited messages/no limits” claims, but also says the free account has “limited features” and users upgrade “if they want more.” It does not clearly identify whether the unlimited claim covers every free model, all model tiers, or only a subset. Do not treat the headline as proof that all model access is unlimited. Keep as a Layer 3 candidate pending clarification of the exact free chat allowance; if the free text quota is in fact capped, move it to Layer 4. | `L3_CANDIDATE_VENDOR_UNLIMITED_CLAIM / FREE_FEATURE_SCOPE_AMBIGUOUS` | `https://bestcontent.ai/products/chat`; sign-in/start: `https://social.bestcontent.ai/` |


### Layer 1 — anonymous, free and unlimited: additional candidates

| Service | Anonymous text-chat evidence | Caveat / classification | Official source |
|---|---|---|---|
| **Yiaho** | Official English page says its online AI is free, requires no account, and is available “without limits”; it lists general-purpose chat and several specialized text assistants. | `L1_VENDOR_CLAIM_NO_ACCOUNT_UNLIMITED / LIVE_QUOTA_UNVERIFIED`. Explicit vendor claim is sufficient to list as a Layer 1 candidate, but there is no independent sustained-use test or detailed anti-abuse policy confirmation in this pass. | `https://www.yiaho.com/en/` |
| **UnlimitedAI** | Official landing page claims no signup, no paywall, no daily limit, and unlimited chat across a multi-model interface. | `L1_VENDOR_CLAIM_NO_SIGNUP_UNLIMITED / BACKEND_AND_QUOTA_UNVERIFIED`. The page does not provide enough transparent detail about upstream model routing, fair-use enforcement, or infrastructure limits to mark independently verified. | `https://unlimitedai.online/` |
| **FreeAnonymousAI** | Official page claims unlimited free AI text chat without account, sign-in, or a daily message cap; follow-up turns retain session context. | `L1_VENDOR_CLAIM_NO_ACCOUNT_UNLIMITED / OPERATOR_AND_BACKEND_REVIEW_NEEDED`. Treat as a candidate, not confirmed capacity: the page's claim is not accompanied by a clearly documented quota policy or independent generation test in this pass. | `https://www.freeanonymousai.com/chat/ai-chat-free` |
| **NoTrack.ai** | Official page advertises anonymous, no-account everyday text chat without a daily message cap. | `L1_VENDOR_CLAIM_UNLIMITED / QUOTA_AND_SUSTAINED_ACCESS_UNVERIFIED`. | `https://notrack.ai/free-ai-chat` |

### Layer 2 — anonymous, free but limited or throttled: additional candidates

| Service | Anonymous allowance / restrictions | Evidence status | Official source |
|---|---|---|---|
| **Hoodgen AI — Unlimited AI page** | No account is required and the page claims no numbered message cap, but its own FAQ acknowledges a per-visitor rate limit and a shared daily capacity. Those are real usage controls even if a normal user may not hit them. | `L2_ANONYMOUS_FREE / SHARED_CAPACITY_AND_RATE_LIMIT / EXACT_NUMBERS_UNDISCLOSED`. Do not classify as Layer 1. | `https://hoodgen.com/unlimited-ai` |
| **Unrestrictable** | No account required for three free turns/day on 93 models, with a human check. A free account adds 10 messages/day and 5 images/day. | `L2_ANONYMOUS_3_TURNS_DAILY / ACCOUNT_TIER_SEPARATE`. This is a clearly capped anonymous service. | `https://unrestrictable.ai/chat` |
| **PLAI.chat** | Anonymous free chat is capped at 20 messages/day. A free account adds a one-time welcome credit; unlimited free-model chat is associated with its paid plai Plus tier, not the ordinary free account. | `L2_ANONYMOUS_20_DAILY / FREE_ACCOUNT_BONUS_NONRENEWING / UNLIMITED_REQUIRES_PAID_TIER`. | `https://plai.chat/` |

### Layer 4 — account required, free but limited / recurring: additional candidates

| Service | Free account allowance | Evidence status | Official source |
|---|---|---|---|
| **FreeTheAI Chat** | Account required. The official page says every free account gets 10 chat messages/day; after those, messages draw on the account's daily free requests. Free models require a daily check-in. No card required. | `L4_FREE_ACCOUNT_DAILY_ALLOWANCE / CHECK_IN_REQUIRED / EXACT_POST_10_MESSAGE_POOL_NEEDS_CLARIFICATION`. Do not describe as unlimited. | `https://chat.freetheai.org/` |
| **xeg** | Guest chat exists. Free signed-in plan advertises unlimited light models plus 100 messages/day across selected higher-tier models. Paid Pro removes that cap. | `L4_ACCOUNT_FREE_MIXED_MODEL_LIMITS / 100_DAILY_ON_SELECTED_MODELS / LIGHT_MODELS_VENDOR_CLAIM_UNLIMITED`. Model-specific labels matter; do not generalize to all models. | `https://www.xeg.io/` |
| **ZeroTwo AI** | Free account provides access to popular models with daily message limits; the site explicitly says unlimited messages and full model catalogue require Pro. | `L4_ACCOUNT_FREE_DAILY_LIMIT / EXACT_FREE_COUNT_NOT_PUBLISHED_ON_LANDING_PAGE`. | `https://zerotwo.ai/chst` |
| **Girli** | Free account is limited to 10 lifetime messages, not 10 per day; the vendor explicitly corrects older pages that claimed a daily allowance. | `L4_ACCOUNT_FREE_NONRENEWING_LIFETIME_CAP / NOT_RECURRING`. Strictly, if no renewal exists, this may be better cross-listed as a non-renewing grant in Layer 5; do not mislabel as a daily recurring free tier. | `https://girli.app/unlimited-free-ai-chat` |

### Additional exclusions and category boundaries

- **Zalt.me local browser inference**: its page says the model runs on the user's own device through WebGPU. It is not a hosted inference service. Keep it outside the hosted Web UI provider ranking, in a separate local-in-browser note. `https://zalt.me/tools/free-ai-chat-online`.
- **JanitorAI / Perchance / SpicyChat**: these are character/roleplay chat platforms rather than general-purpose assistant chat. Do not mix them into the general AI assistant list. Any separate research into them must follow age-appropriate safety and platform age requirements.
- **DeepSeek lookalike domains**: third-party domains that imitate the DeepSeek brand are not counted as official DeepSeek web UI unless ownership is independently established. Do not confuse a third-party marketing page with `https://chat.deepseek.com/`.
- **Token Harbor API**: separate from Rudder.chat consumer web UI. The API requires an account and API key; its free model pool and rolling 7-day value allowance belong in the API research section, not in this Web UI layer. The API and chat also have different rate limits and policies.
- **Unlimited wording is not a guarantee of unlimited capacity**: Hoodgen itself discloses shared daily capacity and visitor rate limits; Rudder discloses hourly/minute speed limits; account/model feature limits must be recorded separately from basic text chat.

### Community evidence and confidence notes

Search surfaced Reddit discussions describing services advertised as unlimited, but the posts are anecdotal and may be promotional or stale. They are discovery leads only; do not use them to establish a numeric quota or promote a service to a confirmed layer. For each candidate above, the cited first-party page is the primary evidence. None of these candidates was subjected to a scripted long-session test, network-level inspection, or repeat testing across multiple days and IP addresses. Mark live status as `NOT_INDEPENDENTLY_TESTED` unless a future test is actually performed.

### Research conclusion for this pass

- **Layer 1 now has multiple explicit vendor-claim candidates**, not zero: AIFreeForever (previous addendum), Yiaho, UnlimitedAI and FreeAnonymousAI. They remain claim-verified, not capacity-verified.
- **Layer 3 gains Rudder.chat / Token Harbor** as a clear account-required unlimited-text campaign, with published speed limits and separate daily tool caps; with campaign terms and speed limits recorded separately. ChatGPT Free remains the other clear Layer 3 entry.
- **Tusk Central AI** is a strong Layer 3 candidate because it advertises 20+ free-unlimited models after account creation, but per-model live entitlements remain untested.
- **BestContent Chat** uses unlimited language while also saying its free account has limited features; keep it a candidate until the scope is clarified.
- Hoodgen is Layer 2, not Layer 1, because it acknowledges shared capacity and visitor rate limiting.
- FreeTheAI, xeg and ZeroTwo belong in Layer 4 with model-specific or daily limits. Girli's 10 lifetime messages are non-renewing and should be treated as Layer 5 rather than recurring free access.

## Web UI text research — practical deep-dive and high-demand services (23 November 2026)

This addendum prioritizes services ordinary users are most likely to need: general chat, study and explanations, coding help, web research with citations, multi-model comparison, and anonymous quick access. It does not treat API gateways, model directories, or local inference software as ordinary hosted chat websites. All quota claims below are based on the cited first-party pages unless explicitly marked otherwise. A vendor's “unlimited” wording is recorded as a vendor claim, not proof that the service can sustain unlimited throughput. No long-duration load test or multi-day account test was performed in this research pass.

### Layer 1 — anonymous, free and unlimited: further candidates and qualification

| Service | Useful purpose | What the first-party page claims | Important qualification | Status |
|---|---|---|---|---|
| **Yiaho** | General chat plus task-focused assistants for writing, rewriting, study, and common questions. | Its English homepage says the chat is free, unlimited, and does not require signup. | The page does not publish a measurable quota or detailed fair-use policy. Keep as a strong vendor-claim candidate, not independently proven unlimited. | `L1_VENDOR_CLAIM_NO_ACCOUNT_UNLIMITED / SUSTAINED_USE_UNTESTED` — https://www.yiaho.com/en/ |
| **AI Free Forever** | General-purpose chat and multi-model access. | Previously identified in this research: the site advertises free chat without registration and unlimited use. | Backend/model routing, sustained-use limits and exact anti-abuse rules remain unverified. | `L1_VENDOR_CLAIM / BACKEND_AND_QUOTA_UNVERIFIED` — https://aifreeforever.com/ |
| **UnlimitedAI** | General text chat with a multi-model presentation. | Its landing page claims no signup and no daily limit. | No transparent per-model routing or capacity policy located in this pass. | `L1_VENDOR_CLAIM / NOT_INDEPENDENTLY_TESTED` — https://unlimitedai.online/ |
| **FreeAnonymousAI** | Quick anonymous chat. | Its page claims free chat without an account or daily message cap. | Operator/backend and sustained availability need further validation. | `L1_VENDOR_CLAIM / NOT_INDEPENDENTLY_TESTED` — https://www.freeanonymousai.com/chat/ai-chat-free |
| **NoTrack.ai** | Privacy-oriented anonymous general chat. | The site describes account-free, stateless chat and says the limits that exist are published. | Do not infer unlimited from “no account” or “stateless”; inspect the live limits and terms before promoting it as truly unlimited. | `L1_CANDIDATE / LIMIT_POLICY_REQUIRES_RECHECK` — https://notrack.ai/ |

**Layer 1 rule:** a service is only a Layer 1 candidate when the vendor explicitly claims both no account and unlimited/free chat. “No account” alone is not enough. If the page admits a visitor rate limit, shared capacity cap, daily cap, or per-session message limit, move it to Layer 2 even if the cap is undisclosed.

### Layer 2 — anonymous, free but limited: practical additions

| Service | Useful purpose | Anonymous access and limit | Status / source |
|---|---|---|---|
| **UsingOpen** | Choose among open-weight models; compare two model answers side by side; useful for coding, reasoning, writing, and learning. | No account, email, phone, or card. The official FAQ says 10 prompts per user per day, reset at midnight UTC. A failed request that never reaches a model does not count. | `L2_ANONYMOUS_10_PROMPTS_DAILY / VENDOR_QUOTA_PUBLISHED` — https://usingopen.com/free-ai-chat/ |
| **Lorik Roo AI Chat** | General assistant with modes for writing, coding, tutoring, creativity, and explanations. | No login or API key. The site publishes a limit of 10 messages per minute per visitor; it says all modes use one shared model, not separate underlying models. | `L2_ANONYMOUS_RATE_LIMIT_10_PER_MINUTE / SHARED_MODEL` — https://www.lorikroo.com/ai-chat |
| **Hoodgen AI** | Quick anonymous assistant. | No account; its own FAQ acknowledges shared capacity and a visitor rate limit, while exact numbers are not clearly disclosed. | `L2_ANONYMOUS_SHARED_CAPACITY / LIMIT_UNDISCLOSED` — https://hoodgen.com/unlimited-ai |
| **Unrestrictable** | Try a broad set of models without registering. | Three anonymous turns/day across the model catalogue; a free account is a separate tier with its own allowance. | `L2_ANONYMOUS_3_TURNS_DAILY` — https://unrestrictable.ai/chat |
| **PLAI.chat** | Basic general chat. | Anonymous access is capped at 20 messages/day. Its paid tier must not be confused with the free anonymous allowance. | `L2_ANONYMOUS_20_MESSAGES_DAILY` — https://plai.chat/ |
| **Duck.ai** | Privacy-oriented chat with a choice of model providers. | No account; daily limit exists but the exact number is not published. Chats are not saved by default. | `L2_ANONYMOUS_DAILY_CAP_UNDISCLOSED` — https://duck.ai/ |
| **ChatGPT guest mode** | Quick general questions without account creation. | Guest access is available only in supported locations and is session-limited; one active conversation, no normal saved history. OpenAI does not publish a fixed guest message count. | `L2_GUEST_ACCESS / LIMIT_UNDISCLOSED / LOCATION_DEPENDENT` — https://chatgpt.com/ |
| **Gemini guest web access** | Quick general questions using Google's default web chat experience. | Some web access may work signed out; feature set and availability vary, and no fixed guest message quota is published. | `L2_GUEST_ACCESS / LIMIT_UNDISCLOSED / AVAILABILITY_DEPENDENT` — https://gemini.google.com/ |
| **Perplexity guest access** | Web-answer engine with cited sources. | Guest search/chat access may work without login, but history and advanced features are restricted; no fixed guest message cap is published. | `L2_GUEST_ACCESS / LIMIT_UNDISCLOSED` — https://www.perplexity.ai/ |

### Layer 3 — account required, free and effectively unlimited: practical additions

| Service | Useful purpose | What is free | Quota and caveats | Status / source |
|---|---|---|---|---|
| **Rudder.chat (Token Harbor / TH-Rudder)** | Strong all-rounder: everyday chat, writing, study, coding, web search, files, and some media tools in one interface. | A free account is needed to receive answers. TH-Rudder text chat is explicitly unlimited during the current campaign and does not consume Token Harbor Pass allowance, rolling free-model allowance, or wallet balance. No credit card is required. | Published speed ceilings: 10 messages/minute and 200/hour. Separate features have separate caps: 100 voice messages/day, 10 images/day, 5 short videos/day, 200 web searches/day, 20 generated files/day; document storage 10 MB and up to 200 conversations. Campaign availability may change. This is not an API entitlement. | `L3_VENDOR_CONFIRMED_UNLIMITED_TEXT_DURING_CAMPAIGN / SPEED_LIMITED / CAMPAIGN_DEPENDENT` — https://rudder.chat/help ; https://tokenharbor.ai/faq ; https://team.tokenharbor.ai/docs/web-chat/limits |
| **ChatGPT Free** | General-purpose assistant for writing, learning, coding explanations, everyday Q&A, and web search. | OpenAI's current FAQ explicitly says everyday text chats are unlimited on Free, subject to abuse-prevention safeguards. | Model switching, file/image uploads, image generation, voice, data analysis, and other tools have separate limits. “Unlimited everyday text” does not mean unlimited access to every model or tool. | `L3_OFFICIAL_UNLIMITED_EVERYDAY_TEXT / TOOL_AND_MODEL_LIMITS_SEPARATE` — https://help.openai.com/en/articles/9275245-chatgpt-free-tier-faq |
| **Tusk Central AI — selected Free Unlimited models** | Multi-model choice and task routing; useful when a user wants to compare model families. | The vendor says 20+ of its 49 models are free and unlimited after a free account; Brainiac auto-routing is available without login. No card is required. | Deep-thinking models and image generation use monthly credits. Confirm the individual model's Free Unlimited label before relying on it; live per-account entitlements were not tested. Brainiac's guest quota is not sufficiently clear to classify as unlimited anonymous. | `L3_VENDOR_CLAIM_SELECTED_MODELS_UNLIMITED / ACCOUNT_ENTITLEMENT_UNTESTED` — https://hello.tuskcentral.ai/free-ai-chat |

### Layer 4 — account required, free but limited / recurring: high-demand services and multi-model tools

| Service | Useful purpose | Free allowance / limits | Why users may still want it | Official source |
|---|---|---|---|---|
| **Perplexity Standard** | Research and web search with citations; especially useful for finding sources rather than relying on a bare model answer. | Free plan has practically unlimited basic searches, 3 Pro Searches/day, 1 Research query/month, and limited file uploads. Advanced model selection and image generation are not included in Standard. | One of the more useful free choices for source-backed web research, even though advanced research is capped. | https://www.perplexity.ai/help-center/en/articles/11187416-which-perplexity-subscription-plan-is-right-for-you |
| **Poe Free** | Try many official and community bots/models in one interface. | Non-paying users receive a daily pool of points; points reset every 24 hours and do not roll over. Each bot has its own point cost, which can vary with input/output length or task. | Good for model variety, but not a predictable unlimited chat service. Check the point cost before using a bot. | https://help.poe.com/hc/en-us/articles/19944206309524-Poe-FAQs |
| **Quad Chat Free** | Compare many model families in one chat app; useful for model comparison and mixed text/image workflows. | Its current Free page says 100 credits/month shared across chats, models, web search and image generation; 31 chat variants from 17 labs are included. Credits reset monthly and do not roll over. | Broad model selection in one place, but credits are shared and expensive models consume more. Not unlimited. | https://www.quad.chat/free-ai-models |
| **Gemini Apps Free** | General assistant, writing, study, multimodal tasks, and integration with Google services. | Google documents standard limits for accounts without an AI plan; limits can change based on availability, experiments, and demand. The official page does not promise unlimited prompts. | Useful mainstream assistant, but quota is dynamic and model/feature access may vary. | https://support.google.com/gemini/answer/16275805 |
| **Claude Free** | High-quality writing, analysis, and coding explanations. | Free plan has usage limits; actual usage depends on message length, conversation length, model, and features. Limits reset according to the product's usage system. | Useful for careful writing and analysis, but not an unlimited free option. | https://support.claude.com/en/articles/11647753-how-do-usage-and-length-limits-work |
| **Grok Free** | General chat and real-time web/X-oriented questions. | Free access is available within limits, which can vary by location and service conditions. The official pages do not state a universal fixed free message quota. | Useful as an additional model/search perspective; classify as limited with quota undisclosed, not unlimited. | https://x.ai/pricing ; https://x.ai/legal/faq |
| **Microsoft Copilot Free** | Everyday chat, writing, brainstorming, summaries, and web-grounded answers. | Microsoft says sign-in is not required for basic Copilot chat at its current web entry point; signing in unlocks history, image creation, longer conversations, voice and other features. | Keep guest and signed-in access as distinct experiences; feature access differs. Do not assume a permanent unlimited allowance. | https://support.microsoft.com/en-us/microsoft-365-copilot/what-s-the-difference-between-microsoft-copilot-free-and-copilot-in-microsoft-365 |
| **xeg** | Multi-model chat with a mix of lighter and stronger models. | Free signed-in plan advertises unlimited access to selected light models and 100 messages/day for selected higher-tier models. | The model-by-model distinction matters: this is a mixed free plan, not unlimited access to every model. | https://www.xeg.io/ |
| **FreeTheAI Chat** | Free model access and everyday chat. | Official page says 10 chat messages/day for free accounts, with daily check-in requirements for free models and further request mechanics that need clarification. | Recurring daily access, but friction and unclear secondary allowance should be disclosed. | https://chat.freetheai.org/ |
| **ZeroTwo AI** | Multi-model assistant. | Free accounts have daily limits; the site says unlimited messages and full model catalogue require Pro. Exact free count not clearly published on the landing page. | Candidate only when the user is comfortable with an undisclosed daily cap. | https://zerotwo.ai/chst |

### Layer 5 — one-time or non-renewing grants

| Service / offer | Grant | Classification note |
|---|---|---|
| **Girli** | 10 lifetime free messages according to the provider's own correction. | This is a lifetime cap, not a daily reset. Put it in Layer 5 rather than describing it as a recurring free plan. | https://girli.app/unlimited-free-ai-chat |
| **BestContent Chat** | The site advertises broad “unlimited” messaging but also describes free features as limited and offers upgrades for more. | Do not count as a confirmed Layer 3 service until the exact free allowance is clarified. Retain as `CONFLICTED_SCOPE`; if its free allocation is a fixed grant, classify only after the actual grant is documented. | https://bestcontent.ai/products/chat |

### Popular-service verification notes

- **Poe:** the official help page confirms a daily points pool for non-paying users, with no rollover. The number of points and effective message count depend on the bot and its point price. Do not report a fixed number of daily messages without checking the selected bot's current rate.
- **Perplexity:** its free plan is best understood as high-volume basic search plus a small number of advanced research actions. The official help page gives 3 Pro Searches/day and 1 Research query/month; this is a more useful description than the vague phrase “free AI chat.”
- **Gemini:** Google's official limits page says standard limits apply without an AI plan and explicitly warns that access can change. Do not turn “standard limits” into an invented fixed daily message count.
- **Claude:** official usage guidance explains that free access is capped and depends on message/context size and features. Avoid quoting an old fixed message number as if it were permanent.
- **Grok:** the official pricing page calls the free tier generous but does not provide one universal message count; the legal FAQ says free access depends on location. Record as recurring but variable/undisclosed.
- **Microsoft Copilot:** the official support page currently describes basic chat without sign-in and additional features after sign-in. Guest mode is therefore not equivalent to a full account-based free tier.
- **Quad Chat:** it is a genuine browser chat product, not just a model directory, but its 100 monthly shared credits mean it belongs in Layer 4.
- **UsingOpen:** it is a browser chat front end for open-weight models, not a self-hosted UI the user must deploy. It is still limited to 10 anonymous prompts/day, so Layer 2.
- **Tusk Central AI:** selected models are marketed as Free Unlimited after account creation. The claim applies to selected model variants only; deep-thinking and image functions use credits. Do not generalize it to the full catalogue.
- **Rudder.chat:** its TH-Rudder route is a campaign-specific consumer chat entitlement. Token Harbor's developer API is separate and must not be counted as a web-chat plan.

### What ordinary users most need — practical shortlist by task

| Need | Best-fit free web UI candidates from this research | Main trade-off |
|---|---|---|
| Everyday chat with no account | Yiaho (vendor claims unlimited); Duck.ai (daily cap undisclosed); UsingOpen (10 prompts/day); ChatGPT guest where available | Anonymous access usually has less history, fewer features, and unclear or explicit caps. |
| Everyday chat after free signup | Rudder.chat TH-Rudder; ChatGPT Free; Tusk Central AI selected models | Rudder's unlimited text is campaign-based and speed-limited; Tusk's unlimited label applies only to selected models. |
| Web research with citations | Perplexity Standard; Rudder.chat web search | Perplexity limits Pro Search/Research; Rudder has a daily search cap. |
| Compare several model families | Quad Chat; Poe; Tusk Central AI; UsingOpen | Quad/Poe consume credits or points; UsingOpen has 10 daily anonymous prompts; Tusk's unlimited claim is model-specific. |
| Coding and technical explanations | ChatGPT Free; Rudder.chat; Tusk Central AI; UsingOpen; Claude Free | Claude and many advanced models have usage limits; check which model is active. |
| Writing, rewriting and study | ChatGPT Free; Yiaho; Rudder.chat; Tusk Central AI; Claude Free | Quality and quota vary; verify outputs and sources for factual work. |
| Privacy-oriented quick chat | Duck.ai; NoTrack.ai (verify exact limits) | Anonymous does not mean the service or upstream model provider processes no data; read privacy terms. |

### Quality, reliability, privacy, and quota fields to track in future passes

For every newly discovered service, record these separately rather than compressing them into a single “free/unlimited” label:

1. **Access:** anonymous guest, email account, social login, phone verification, or payment method required.
2. **Free entitlement:** no published cap, daily messages, rolling 24-hour cap, monthly credits, weekly pool, one-time grant, or promotional campaign.
3. **Rate limits:** messages/minute, messages/hour, concurrency, queue priority, IP/browser throttles. These are not the same as a renewable message quota.
4. **Model scope:** all models, selected free models, one router-selected model, or only a basic default model.
5. **Feature scope:** ordinary text, web search, files, images, voice, video, coding tools and agent actions each need separate quota notes.
6. **Reset semantics:** midnight UTC, rolling 24 hours, fixed weekly reset, monthly billing date, or no renewal.
7. **Regional availability:** whether access or guest mode differs by country/network. Libya availability has not been directly tested in this pass.
8. **Privacy:** retention, training use, upstream providers, account history, and whether browser storage is local or server-side.
9. **Reliability:** queueing, outages, 429 responses, temporary campaign conditions, and whether a service can answer a real prompt (not merely show a model list).
10. **Evidence confidence:** official policy, live page observation, actual generation test, repeat test, and independent community reports must remain distinct evidence types.

### Evidence sources for this addendum

- Token Harbor / Rudder official FAQ and limits: https://tokenharbor.ai/faq ; https://team.tokenharbor.ai/faq ; https://team.tokenharbor.ai/docs/web-chat/limits ; https://rudder.chat/help
- OpenAI Free Tier FAQ: https://help.openai.com/en/articles/9275245-chatgpt-free-tier-faq
- Yiaho official homepage: https://www.yiaho.com/en/
- UsingOpen official chat and quota FAQ: https://usingopen.com/free-ai-chat/
- Lorik Roo official chat: https://www.lorikroo.com/ai-chat
- Quad Chat free model catalogue and credit terms: https://www.quad.chat/free-ai-models
- Tusk Central AI free chat: https://hello.tuskcentral.ai/free-ai-chat
- Perplexity Standard plan limits: https://www.perplexity.ai/help-center/en/articles/11187416-which-perplexity-subscription-plan-is-right-for-you
- Poe daily points policy: https://help.poe.com/hc/en-us/articles/19944206309524-Poe-FAQs
- Gemini usage limits: https://support.google.com/gemini/answer/16275805
- Claude usage and length limits: https://support.claude.com/en/articles/11647753-how-do-usage-and-length-limits-work
- Grok free/paid overview: https://x.ai/pricing ; https://x.ai/legal/faq
- Microsoft Copilot free access: https://support.microsoft.com/en-us/microsoft-365-copilot/what-s-the-difference-between-microsoft-copilot-free-and-copilot-in-microsoft-365

### Research conclusion

The most useful additions in this pass are **UsingOpen** (10 anonymous prompts/day and model comparison), **Lorik Roo** (anonymous shared-model assistant with a published 10/minute rate limit), **Quad Chat** (31 free chat model variants under a 100-credit monthly pool), and a more precise official comparison of **Perplexity, Poe, Gemini, Claude, Grok, and Copilot**. The strongest account-based unlimited-text entries remain **Rudder.chat during its TH-Rudder campaign** and **ChatGPT Free everyday text**; **Tusk Central AI** is a promising model-specific Layer 3 option but still needs per-model live entitlement checks.

This remains desk research. It does not claim that the assistant opened accounts, generated test outputs, ran long conversations, or verified availability from Libya. Future entries should only be promoted to `GENERATION_TESTED` after a real prompt is sent and a usable response is received; a successful homepage or models-list load is not sufficient.

---

## Final deep-research pass — Text Generation / AI Chat Web UI (23 November 2026)

This is the closing audit for the text-chat category before moving to the next Web UI category, AI image generation. It adds high-utility services that were missing or under-classified and tightens the evidence distinctions. The five-layer Web UI taxonomy remains unchanged.

### New and corrected findings

| Service | Layer | Practical value | Current evidence and caveats | Status / official source |
|---|---:|---|---|---|
| **Brave Leo** | 2 | General chat, explainers, writing, translation, summarizing webpages/PDFs and working alongside browser tabs. | Brave officially says free Leo needs no account and is available on desktop and mobile. It has “reasonable” rate limits, while Premium gets higher limits; no fixed free message quota is published. Chat history can remain local on the device. Model availability depends on free/premium status and may change. | `L2_ANONYMOUS_FREE_RATE_LIMIT_UNDISCLOSED / OFFICIAL` — https://brave.com/ai/ ; https://support.brave.app/hc/en-us/articles/20958609786637-How-do-I-use-Brave-Leo |
| **Proton Lumo guest** | 2 | Private general chat, summarization, translation, code help, and small-file questions. | Proton explicitly allows a limited chat without creating an account. A Proton account unlocks the separate Free plan with more prompts, saved encrypted history, limited Max model usage, limited messages, limited image generations, and one Project. Guest access is not unlimited. Proton does not publish a simple guest message count in the cited support page. | `L2_GUEST_LIMITED / LIMIT_UNDISCLOSED / OFFICIAL` — https://proton.me/support/lumo-getting-started |
| **Quad Chat guest** | 2 | Compare answers from multiple models side by side without first creating an account. | The homepage explicitly offers first-question guest access with no account, login, or card. It invites users to create an account to retain/sync chats, files and projects. The anonymous guest quota is not published on the cited page; do not infer that guest access inherits the account plan's monthly 100-credit pool. | `L2_GUEST_ACCESS / LIMIT_UNDISCLOSED / OFFICIAL` — https://www.quad.chat/ |
| **Yiaho** | 1 | General chat plus task-specific assistants for rewriting, spelling, school writing, email replies, and explanations. | The official English page explicitly claims free, no-signup, unlimited chatbot use; it also says image creation belongs to Yiaho+ (a separate paid/ad-free offer, with a trial). Treat its text-chat unlimited status as a vendor claim, not an independently stress-tested fact. The English page says its ChatGPT access is in English; language-specific versions exist. | `L1_VENDOR_CLAIM_UNLIMITED / NO_ACCOUNT / NOT_STRESS_TESTED` — https://www.yiaho.com/en/ |
| **NoTrack.ai** | 2 | Anonymous general chat with a privacy-focused, stateless-session positioning. | The service states no account is required and describes its limits as published, but the landing page reviewed here did not expose a clear numeric text-message quota. It is also an adult-oriented service, so this is retained only as a market-research record, not a recommendation or access instruction. Do not promote to Layer 1 without a clearly evidenced unlimited entitlement. | `L2_ANONYMOUS / LIMIT_UNDISCLOSED_IN_REVIEWED_PAGE / NOT_PROMOTED_TO_L1` — https://notrack.ai/ |

### Important corrections to the existing shortlist

- **Brave Leo belongs in Layer 2**, not an unqualified “unlimited anonymous” list. The official help page says the free tier has reasonable rate limits and Premium has higher limits. No fixed free quota is stated.
- **Lumo has two distinct experiences:** limited guest chat (Layer 2) and account-based Free (Layer 4). Do not merge them into one tier. Proton's Free plan is explicitly limited in messages, Max model usage, chat history, and image generations.
- **Quad Chat also has two distinct experiences:** an anonymous first-question entry point (Layer 2, quota undisclosed) and a signed-in Free plan (Layer 4, 100 monthly shared credits across models, chat, web search, and image generation). The 100-credit account allowance must not be attributed to anonymous guest access.
- **Yiaho remains a Layer 1 candidate based on its own explicit unlimited/no-registration claim.** This is stronger evidence than a vague “free” badge, but still not proof from a prolonged independent load test. Keep the exact status `VENDOR_CLAIM_UNLIMITED` rather than `GENERATION_TESTED_UNLIMITED`.
- **NoTrack.ai remains Layer 2** until a numeric or explicit unlimited text quota is established from a current official policy. Privacy claims and anonymous access do not prove unlimited usage.
- **Rudder.chat remains Layer 3** because the unlimited text entitlement requires a free account and is tied to the current TH-Rudder campaign; its published speed ceilings are not a daily message quota. Keep campaign expiry/change risk visible.
- **ChatGPT Free remains Layer 3 only for ordinary text chat as described in the official FAQ.** Do not extend that label to image generation, advanced models, file analysis, voice, or other separately limited features.
- **Tusk Central AI remains a qualified Layer 3 entry only for the specific models marked Free Unlimited.** Do not generalize the claim to every model or to credit-consuming image/deep-thinking functions.

### Best-fit shortlist after the final text pass

| Common user need | Strong candidates | What to check before relying on them |
|---|---|---|
| No-account general chat | Yiaho; Brave Leo; Duck.ai; Lumo guest; Quad Chat guest | Yiaho's unlimited claim is vendor-stated; Brave/Duck/Lumo/Quad guest use has limits or undisclosed quotas. |
| Free account for ongoing everyday text | ChatGPT Free; Rudder.chat TH-Rudder; Tusk Central AI selected models | Separate plain text from model/tool quotas; Rudder is campaign-dependent; Tusk is model-specific. |
| Private or local-history-oriented chat | Brave Leo; Duck.ai; Proton Lumo | Privacy architectures differ. Read retention and upstream-model terms; “private” is not synonymous with “nothing is processed.” |
| Compare several models | Quad Chat; Poe; Tusk Central AI; UsingOpen | Compare shared credits/points and anonymous versus signed-in access. |
| Web research with citations | Perplexity Standard; Brave Search/Leo; Rudder.chat web search | Search caps and AI-chat caps are separate. Verify citations at source level. |
| Writing and study support | Yiaho task-specific assistants; ChatGPT Free; Claude Free; Rudder.chat | Check language support, free-model scope, and message limits. |
| Coding help | ChatGPT Free; Claude Free; Brave Leo; Rudder.chat; selected Tusk models | Stronger reasoning models may be separately capped; do not infer coding-agent access from ordinary chat. |

### Evidence quality and unresolved work

1. A provider's explicit policy or pricing page is stronger than a third-party roundup. A current homepage claim is useful but should be tagged as a vendor claim if no quota policy backs it.
2. A real prompt answered successfully establishes only that the service worked once. It does not establish unlimited use, long-term availability, or regional access.
3. A model catalogue, login page, or landing page is not proof that generation is available to a free account.
4. Rate limits (for example, 10 messages/minute) are not equivalent to daily or monthly quotas. Record both fields separately.
5. Guest mode, account-free mode, and signed-in free plans must have separate rows when their entitlements differ.
6. No service in this pass was independently stress-tested with long conversations, repeated sessions, or multiple IPs. Libya availability was not directly tested.
7. This category is now considered sufficiently covered for the current research cycle. Reopen it only when there is a new lead, a policy change, or a live-test opportunity; do not keep adding weak directory entries merely to inflate the count.

### Official sources added in this final pass

- Brave Leo free access and rate-limit distinction: https://support.brave.app/hc/en-us/articles/20958609786637-How-do-I-use-Brave-Leo ; https://brave.com/ai/
- Proton Lumo guest and Free-plan distinction: https://proton.me/support/lumo-getting-started ; https://proton.me/lumo/pricing
- Quad Chat anonymous entry point: https://www.quad.chat/
- Quad Chat Free plan and shared-credit scope: https://www.quad.chat/free-ai-models
- Yiaho English page and explicit no-account/unlimited claim: https://www.yiaho.com/en/
- NoTrack.ai account-free positioning: https://notrack.ai/
