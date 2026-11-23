# AI Music Generation — Web UI

> Consumer browser music generators, browser quotas, export/download conditions and local-WebGPU tools. These are not automatically API offers.

## How to use this file

1. Open the official product page linked in the provider entry.
2. If the entry says **anonymous/no signup**, try the public page without creating an account. If it requires login, use the provider's own sign-up flow; do not use unofficial account-sharing methods.
3. Check the actual free allowance shown in the product's current interface. Do not assume browser credits can be used through the API.
4. Generate a short sample first. Confirm whether preview, full generation, download/export, watermark removal and commercial use are included in the free tier.
5. Save/export the result only through the product's supported controls. Check whether outputs expire or are public by default.
6. Review privacy and retention terms before uploading personal audio, images, documents or other sensitive content.

**Important:** Web UI entries are browser products, not developer APIs, unless a separate API entry explicitly confirms an API entitlement.

## Research inventory (preserved from the source catalogue)

# AI Music Generation Web UI — focused deep research pass (23 November 2026)

**Scope:** consumer-facing browser music/song generators only. This section covers text-to-music, lyrics-to-song, vocal songs, instrumentals and browser-based music composition. It does not mix in TTS, speech recognition, music APIs, local model downloads, music editors, stock-music libraries or video generators. A service may appear in the API inventory elsewhere, but its Web UI quota is a separate entitlement.

**Layer definitions applied:**
1. Anonymous, free and unlimited — no account required, and the specific browser workflow claims no fixed generation cap. “Unlimited” remains a vendor claim unless independently load-tested; queue, device and compute limits are recorded separately.
2. Anonymous, free but limited — no account required, but a daily/session/finite limit exists or is undisclosed.
3. Account required, free and effectively unlimited — account required and basic generation explicitly described as unlimited; separate tool/model/download limits remain visible.
4. Account required, free but limited — account required and recurring daily/monthly quotas or limited free features.
5. One-time trial or non-renewing grant — finite signup/song/credit grant that does not refill.

## Layer 1 — anonymous, free and unlimited (vendor-claimed)

| Provider | What it makes | Free access and output | Important constraints / evidence status |
|---|---|---|---|
| **Swara Sound** | Full songs with sung vocals from lyrics/prompts and instrumentals; browser-local ACE-Step-based engine. | No account, no API key, no credits, no watermark; the provider says unlimited. MP3/WAV export is described. | **Runs locally in the browser using WebGPU**, not a cloud generation service. First load downloads about **1.9 GB** and needs a recent desktop/laptop browser (Chrome/Edge) and capable graphics hardware; the page says phones/tablets do not have enough memory. Songs/keys are stored in the browser unless optional Google Drive backup is enabled. This is a major device/storage caveat and must not be presented as a lightweight phone website. `VENDOR_CLAIM_UNLIMITED / LOCAL_WEBGPU / NOT_LIVE_TESTED_HERE`. Sources: https://swarasound.com/ ; https://swarasound.com/create ; https://swarasound.com/music ; https://huggingface.co/spaces/SwaraSound/swara-sound |
| **Boppy** | Full songs with AI-written lyrics, sung vocals or instrumentals. | Web page says no account, email or card; clean MP3 download and no watermark. | **Quota conflict:** the main FAQ says web users face a daily limit and tracks up to 2 minutes, while a dedicated landing page says “unlimited” and describes tracks up to 3 minutes. Do not promote the unlimited claim as confirmed. For conservative classification use Layer 2 until the exact web limit is published/observed. Included here only as a Layer 1 *claim candidate*, not a confirmed L1 provider. Sources: https://boppy.me/ ; https://boppy.me/free-ai-music-generator-no-sign-up ; https://boppy.me/about |
| **Sonauto AI** | Prompt-to-song and lyrics-to-song; vocals, tags, inpainting, extension and stem export are advertised. | Website claims free unlimited generations, no signup, tracks up to about 4:45 on its V3 Preview model. | Vendor claim; public page does not establish a guaranteed service-level quota or queue priority. Need to distinguish current `sonautoai.net` web service from similarly named/older Sonauto properties and from the underlying model. No live generation performed. `VENDOR_CLAIM_UNLIMITED / NOT_LIVE_TESTED`. Source: https://sonautoai.net/ |
| **Upsampler — Free AI Music Generator** | Text-to-music; instrumentals or songs with sung vocals, powered by MiniMax-Music3. | No account; advertises free generation, no watermark and downloadable 44.1 kHz stereo WAV. | Uses shared GPUs. A fixed daily count is not published on the surfaced page; shared capacity/queue may constrain throughput. Treat as `L1_CANDIDATE_LIMIT_UNDISCLOSED`, not proof of unlimited throughput. No live request performed. Source: https://upsampler.com/free-ai-music-generator-no-signup |
| **WaveSpeed AI — browser music tool** | Browser-based AI instrumental generation; quick mode creates editable pattern-based music. | Provider says generation runs on the user's device, no account, no credits, no daily cap and no watermark. | Main AI model downloads about **1.1 GB**, requires WebGPU and roughly 4 GB graphics memory on desktop/laptop; phones switch to a lighter “quick mode” that is pattern/synth composition rather than the same full AI model. Keep the two output modes distinct. `VENDOR_CLAIM_UNLIMITED / LOCAL_WEBGPU / MODE_DIFFERS_ON_PHONE`. Source: https://wavespeed.ai/free-tools/ai-music-generator |

**Layer 1 decision:** Swara Sound and WaveSpeed's full browser model are the clearest no-account/no-credit/no-fixed-cap claims, but both are local WebGPU experiences with large first-time model downloads and device requirements. Sonauto and Upsampler are no-account cloud candidates with unverified queue/throughput limits. Boppy is not confirmed Layer 1 because its own pages conflict about daily limits.

## Layer 2 — anonymous, free but limited (or limit undisclosed)

| Provider | Free anonymous path | Quota / output | Caveats and status |
|---|---|---|---|
| **YuE2 AI Studio** | No signup, no card; lyrics-to-song and prompt-to-song via YuE2 and MiniMax-Music3. | A free **daily allowance** is explicitly stated, but the exact number is not published; longer songs consume more allowance. MP3/FLAC/WAV download is advertised. | Daily cap undisclosed; generation may take minutes and depends on shared load. Site describes a local independent web studio, not the official model-hosting organization. `OFFICIAL_SITE_CLAIM / LIMIT_UNDISCLOSED / NOT_LIVE_TESTED`. Source: https://yue2.dev/ |
| **Boppy web generator** | No account, email or card for web use. | Daily limit stated in the FAQ; exact number not published there. Main FAQ says up to 2 minutes; dedicated landing page advertises up to 3 minutes. | Contradictory duration and unlimited-vs-daily-limit claims. Use conservative Layer 2 until clarified. Mobile apps are a different flow and should not be used to infer the web quota. Sources: https://boppy.me/ ; https://boppy.me/free-ai-music-generator-no-sign-up |

## Layer 3 — account required, free and effectively unlimited

**No additional provider was confirmed in this pass.** Do not infer “unlimited” from the absence of a visible credit counter. A service belongs here only when its free account entitlement explicitly describes basic song generation as unlimited and the actual account workflow supports that claim.

## Layer 4 — account required, free but limited (recurring quotas / restricted free features)

| Provider | Free allowance / features | Downloads, rights and restrictions | Evidence / classification |
|---|---|---|---|
| **Suno** | Free plan: **50 credits/day**, free models, shared queue; upload up to 8 minutes of audio. | Free plan has no commercial rights and pricing says no monthly song downloads. Songs remain playable/shareable in the service; do not promise downloadable files to new free accounts. | Official pricing. `L4_OFFICIAL_DAILY_QUOTA`. Sources: https://suno.com/pricing ; https://suno.com/ |
| **Udio** | Free account: **10 daily credits plus 100 monthly credits**; credit rules cap free users at three 130-second songs/day. | Downloading audio is disabled under the current service state reported by recent independent checks; terms and export availability should be rechecked before relying on it. | Official help documents the credit pool and 3-long-song daily cap; download restriction is a separate, time-sensitive service condition. `L4_OFFICIAL_QUOTA / EXPORT_STATUS_RECHECK`. Sources: https://help.udio.com/en/articles/10739134-credits-and-credit-limits ; https://udio.com/ |
| **ElevenMusic (standalone elevenmusic.io)** | Free plan: **25 songs/day**. | Up to **5 downloads/day** and 5 stem splits/day; free-plan songs may be used commercially only with reasonably prominent “Made with ElevenMusic” attribution. Free-created songs cannot be released through digital streaming platforms; that distribution route requires Pro. | Official standalone ElevenMusic terms and pricing; **do not confuse it with ElevenLabs Music inside the main ElevenLabs platform**, whose shared 10,000-credit plan and API access are separate products. `L4_OFFICIAL_DAILY_QUOTA / COMMERCIAL_WITH_ATTRIBUTION / STREAMING_RELEASE_RESTRICTED`. Sources: https://elevenmusic.io/ ; https://elevenmusic.io/terms-of-use |
| **Brev AI** | Free plan: **25 credits/day**, one concurrent job, access to Prime/Core models; free generations stored 7 days. | MP3 download available; WAV plan-based. Free users do **not** receive commercial usage rights; free generations are public. | Official pricing page. Do not convert credits into a fixed song count unless the exact model/length cost is specified. `L4_OFFICIAL_DAILY_CREDITS / NONCOMMERCIAL`. Source: https://brev.ai/pricing |
| **Stable Audio** | Free account: **50 credits/month**, described by provider as about 12 full-mix or 8 multi-track generations; credits renew on the first of each month. | Official provider says every plan, including Free, includes a commercial license. Supports tracks up to 6 minutes; exact credit cost varies by generation type. Account required to generate the exact custom mix; preview/remix exploration can be tried before signup. | Official pricing and licensing. `L4_OFFICIAL_MONTHLY_QUOTA / COMMERCIAL_LICENSE`. Sources: https://stableaudio.com/ ; https://kb.stability.ai/knowledge-base/stable-audio-commerical-and-usage-licensing |
| **AIVA** | Free Forever: **3 downloads/month**, tracks up to 3 minutes. | MP3 and MIDI downloads. AIVA owns copyright; non-commercial only; credit to AIVA required; no monetization. | Official pricing/legal page. This is composition-focused and MIDI export is a useful differentiator from full vocal song generators. `L4_OFFICIAL_MONTHLY_DOWNLOAD_CAP / NONCOMMERCIAL / MIDI`. Sources: https://www.aiva.ai/about-us ; https://www.aiva.ai/legal/1 |
| **Loudly** | Free plan includes a daily generation allowance; provider does not publish a single universal numeric quota in the FAQ reviewed. | Free tracks are limited to **30 seconds**. Download/licensing allowances are lower than paid tiers; do not assume free previews carry commercial rights. | Official FAQ confirms 30-second cap and daily usage allowance but not exact number. `L4_OFFICIAL_LIMIT_UNDISCLOSED / 30S_CAP`. Source: https://www.loudly.com/faq |
| **ElevenLabs Music (inside main ElevenLabs platform)** | Main Free plan lists **10,000 shared credits/month** across ElevenLabs tools; Music is estimated at 900 credits/minute on the music page. | Free plan is non-commercial; music API eligibility is not clearly guaranteed by the free plan. Do not merge this allowance with the standalone ElevenMusic product's 25 songs/day. | `L4_WEB_FREE / API_ENTITLEMENT_UNCONFIRMED / SHARED_POOL`. Sources: https://elevenlabs.io/music ; https://elevenlabs.io/pricing ; https://elevenlabs.io/pricing/api |
| **Google Flow Music** | Google says core features can be used at no charge with a Google account; extra credits/generations and newer models require paid membership. | **Not included as a recommendation or access path for this user:** Google's current eligibility documentation says users must be at least 18 and in a supported region. Do not attempt to bypass age or regional eligibility. | Official eligibility and plan docs: https://support.google.com/flow/answer/17083868 ; https://support.google.com/flow/answer/17083870 |

## Layer 5 — one-time trial / non-renewing grant

| Provider | One-time free offer | What is actually included / caveat | Evidence status |
|---|---|---|---|
| **Neume** | One free song, with two versions to choose from; no card reported by the November 2026 independent comparison. | Not a recurring daily/monthly quota. The same comparison says the provider's terms allow personal and commercial use, but the exact current official plan/terms were not independently confirmed in this pass. | `L5_ONE_SONG_REPORTED / TERMS_NEED_FIRST_PARTY_RECHECK`. Discovery: https://aifree.dev/learn/free-ai-music-generator |
| **Soundverse** | New-account grant reported as **1,000 tokens**, approximately three songs in an independent November 2026 comparison. | One-time/non-renewing; conversion depends on the selected generation and current token cost. Do not describe as a recurring free plan. | `L5_REPORTED_TRIAL / TOKEN_TO_SONG_ESTIMATE_NOT_GUARANTEED`. Discovery: https://www.datacamp.com/blog/best-free-ai-music-generators |
| **Artlist AI Music** | Independent November 2026 comparison reports a free trial of **2 AI music tracks**. | Trial tracks reportedly cannot be downloaded; no continuing free plan established. Do not treat as useful exportable free generation unless official terms change. | `L5_REPORTED_TRIAL / DOWNLOAD_RESTRICTED / NOT_FIRST_PARTY_VERIFIED`. Discovery: https://enkitools.com/guides/free-ai-music-generators |

## Important exclusions and product distinctions

- **Open models are not hosted free Web UI plans.** ACE-Step, YuE model weights, Stable Audio Open and MusicGen belong in the self-hosted/local section unless a named hosted website is separately assessed. Local model licensing differs by model; for example, MusicGen's license is not equivalent to a commercial-use grant for every output.
- **Swara Sound and WaveSpeed AI are browser-local WebGPU tools.** Their no-credit claim is possible because inference runs on the user's own device. Count their first-download size, GPU/browser compatibility and mobile fallback as core limitations, not as hidden unlimited cloud capacity.
- **ElevenMusic and ElevenLabs Music are two distinct products.** Standalone ElevenMusic has a 25-song/day free plan and attribution-based commercial use; ElevenLabs Music in the main platform is part of a shared credit pool and has different non-commercial/API restrictions.
- **Stable Audio Web UI vs Stable Audio API:** the 50-credit monthly Web UI plan is not the same as Stability's separate API new-account credit grant. Do not duplicate one balance across the two products.
- **Suno credits are not songs.** The actual number of songs depends on model and generation settings. Free plan download and commercial rights are restricted.
- **AIVA creates compositions and MIDI**, whereas Suno/Udio/ElevenMusic/Brev primarily target rendered full songs. Keep MIDI export visible as a separate capability.
- **A free preview is not necessarily a downloadable song.** SOUNDRAW's free mode is commonly preview-only; Artlist's reported trial is download-restricted. Do not count these as exportable tracks without first-party confirmation.
- **No live generation was performed in this research pass.** Quotas and feature statements above are based on provider documentation and identified independent comparisons. Provider claims, independent reports and unresolved conflicts are explicitly separated.

## Current music Web UI layer summary

| Layer | Findings from this pass |
|---|---|
| **1 — Anonymous, free and unlimited** | Swara Sound (browser-local WebGPU, ~1.9 GB initial download); WaveSpeed AI browser music tool (local WebGPU, ~1.1 GB); Sonauto (vendor-claimed unlimited cloud generation, not live-tested); Upsampler (no-signup shared-GPU candidate, exact quota undisclosed). |
| **2 — Anonymous, free but limited** | YuE2 AI Studio (daily allowance, amount undisclosed); Boppy (no-account but daily-limit statement conflicts with “unlimited” landing page; conservative L2). |
| **3 — Account required, free and effectively unlimited** | No new confirmed provider. |
| **4 — Account required, free but limited** | Suno (50 credits/day); Udio (10/day + 100/month, max 3 long songs/day); ElevenMusic standalone (25 songs/day, 5 downloads/day); Brev (25 credits/day); Stable Audio (50 credits/month); AIVA (3 downloads/month); Loudly (daily allowance undisclosed, 30-second tracks); ElevenLabs Music inside main platform (10,000 shared credits/month, non-commercial/API caveat). Google Flow Music is documented separately as age/region restricted and is not an access recommendation. |
| **5 — One-time trial** | Neume (one song, reported); Soundverse (1,000-token grant, reported); Artlist (two-track trial, reportedly no download). |

## Sources and research boundary

Provider-first sources used for the core entitlements:
- Suno pricing: https://suno.com/pricing
- Udio credit rules: https://help.udio.com/en/articles/10739134-credits-and-credit-limits
- ElevenMusic standalone pricing and terms: https://elevenmusic.io/ ; https://elevenmusic.io/terms-of-use
- Brev pricing: https://brev.ai/pricing
- Stable Audio pricing and licensing: https://stableaudio.com/ ; https://kb.stability.ai/knowledge-base/stable-audio-commerical-and-usage-licensing
- AIVA pricing and license: https://www.aiva.ai/about-us ; https://www.aiva.ai/legal/1
- Loudly FAQ: https://www.loudly.com/faq
- Swara Sound product, create page and model card: https://swarasound.com/ ; https://swarasound.com/create ; https://huggingface.co/spaces/SwaraSound/swara-sound
- WaveSpeed AI browser music tool: https://wavespeed.ai/free-tools/ai-music-generator
- Boppy: https://boppy.me/ ; https://boppy.me/free-ai-music-generator-no-sign-up
- Sonauto: https://sonautoai.net/
- Upsampler: https://upsampler.com/free-ai-music-generator-no-signup
- YuE2: https://yue2.dev/
- Discovery/cross-check only (not provider policy): https://aifree.dev/learn/free-ai-music-generator ; https://www.datacamp.com/blog/best-free-ai-music-generators ; https://enkitools.com/guides/free-ai-music-generators

**Verification boundary:** research performed 23 November 2026. No accounts were created, no age/identity checks were attempted, and no live music generations/downloads were executed. The entries marked `VENDOR_CLAIM`, `REPORTED`, `CONFLICT` or `NOT_LIVE_TESTED` must not be described as independently confirmed output quotas or quality results.


---

## Web UI inventory — additional distinctions

- **Neume:** one free song is reported by a November 2026 comparison. This is a one-time browser entitlement, not a recurring API quota; official current terms and download rights still need first-party confirmation. Discovery source: https://aifree.dev/learn/free-ai-music-generator
- **Soundverse:** a 1,000-token new-account grant is reported by a third-party comparison. Treat it as a one-time browser/product trial unless the provider confirms a developer API entitlement. Discovery source: https://www.datacamp.com/blog/best-free-ai-music-generators
- **Artlist AI Music:** a two-track trial is reported, but downloads are reportedly restricted. Do not count it as an exportable free API or as a recurring browser plan without checking current official terms. Discovery source: https://enkitools.com/guides/free-ai-music-generators
- **Truly local browser inference:** Swara Sound and WaveSpeed browser music tools use local WebGPU execution according to their product descriptions. Their apparent lack of a cloud credit cap is not an anonymous cloud API quota. Record initial model download size, browser/GPU compatibility, device storage and mobile fallback as practical limitations. Sources: https://swarasound.com/ ; https://wavespeed.ai/free-tools/ai-music-generator

## Music audit result

No new provider was promoted to recurring free hosted API in this addendum. The correct outcome is to preserve the existing evidence hierarchy: Audo is a documented keyless candidate; Daydream remains conflicted on whether its free monthly allowance applies to API calls; the named API trial providers remain finite Layer 3 offers; browser-only and local-WebGPU products stay outside the hosted API layers. No live music generation was performed.
