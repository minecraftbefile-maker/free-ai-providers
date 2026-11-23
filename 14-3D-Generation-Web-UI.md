# AI 3D Generation — Web UI

> Browser-based 3D generators and studio plans, separated from hosted developer APIs.

## How to use this file

1. Open the official product page linked in the provider entry.
2. If the entry says **anonymous/no signup**, try the public page without creating an account. If it requires login, use the provider's own sign-up flow; do not use unofficial account-sharing methods.
3. Check the actual free allowance shown in the product's current interface. Do not assume browser credits can be used through the API.
4. Generate a short sample first. Confirm whether preview, full generation, download/export, watermark removal and commercial use are included in the free tier.
5. Save/export the result only through the product's supported controls. Check whether outputs expire or are public by default.
6. Review privacy and retention terms before uploading personal audio, images, documents or other sensitive content.

**Important:** Web UI entries are browser products, not developer APIs, unless a separate API entry explicitly confirms an API entitlement.

## Research inventory (preserved from the source catalogue)

## 3D browser tools — not counted as hosted APIs

- **3D AI Studio:** advertises anonymous text/image-to-3D and GLB export, but its page describes a human Turnstile check and no public developer API contract was established. Record as `FREE_BROWSER_UI / API_UNCONFIRMED`, not Layer 1 API. Source: https://3daistudio.pro/
- **Sloyd Guest:** one generation/day is a browser/guest entitlement in the reviewed pricing page; no free API entitlement was established. Keep outside API layers. Source: https://www.sloyd.ai/pricing
- **Hunyuan3D Global/browser demos:** useful for trying the model, but a browser demo is not a callable anonymous developer API unless a documented endpoint and quota are supplied.
- **Meshy Playground:** its own built-in key supports testing; it does not mean free users can create their own API keys. Keep separate from API access. Source: https://docs.meshy.ai/en/api/quick-start

## Free browser generators — useful, but not API providers

| Product | What the free offer appears to cover | Why it is not an API-layer entry |
|---|---|---|
| **Sloyd** | Guest browser generation, advertised as one generation/day; exports and license are tied to the guest plan. | No public free developer API entitlement verified. Source: https://www.sloyd.ai/pricing |
| **Rodin / Hyper3D web workspace** | Generate/preview some lower-quality outputs for free; pay credits to confirm/export selected results. | Web preview workflow is separate from authenticated API credits. Source: https://hyper3d.ai/help/articles/how-many-credits-does-each-hyper3d-generation-cost |
| **Meshy Playground** | Test generation using an internal built-in key. | Free users cannot create their own API keys; the internal Playground key is not a user API entitlement. Source: https://docs.meshy.ai/en/api/quick-start |
| **3D AI Studio** | Anonymous/browser text or image generation may be available, with browser-side bot checks. | No documented public developer API entitlement confirmed. Source: https://3daistudio.pro/ |
| **Krea 3D / other multi-model studios** | Free plan access to selected 3D engines may be offered in the web app. | No evidence that free browser credits can be spent through a public 3D-generation API. Treat as UI only until docs say otherwise. Discovery source: https://www.krea.ai/ |
| **Tencent Hunyuan3D web demos** | Web demos and app promotions can allow trials. | The API's own one-time free package is a separate entitlement; do not infer a recurring quota from demo access. Sources: https://cloud.tencent.com/document/product/1804 ; https://cloud.tencent.com/document/faq/1804/120706 |
| **Tripo Studio** | Free consumer credits may be offered on its Studio plan. | API billing/wallet is separate from Studio balance. Source: https://platform.tripo3d.ai/docs/billing |

# 3D provider expansion — additional audit (23 November 2026)

## Current hosted API finding: three.ws

**three.ws Forge / 3D Studio** remains the strongest documented keyless hosted API candidate in this inventory. Its published OpenAPI announcement says the free text-to-3D endpoint is callable without an account, API key or payment. The Forge interface describes text and photo input, textured downloadable models and a free draft lane. The maintainer's pipeline document lists `POST /api/v1/ai/text-to-3d` and a quota of 10 generations per IP per day, with HTTP 429 above quota and a paid x402 upsell. Because separate examples in the ecosystem describe an account/key for a different `/api/3d/generate` route, do not confuse endpoints: record the exact path and authentication mode for the free flagship endpoint. No live generation request was made in this research. 

- OpenAPI announcement: https://three.ws/changelog/2026-07-18-the-free-3d-studio-now-publishes-a-machine-readable-api-description
- Forge interface: https://three.ws/forge
- Pipeline endpoint/quota documentation: https://github.com/nirholas/three.ws/blob/main/docs/forge-pipeline.md
- Separate MCP endpoint: https://github.com/nirholas/three.ws/blob/main/docs/mcp-studio.md

## Additional free web products — not free developer APIs

| Provider | Browser offer reported | API status | Correct classification |
|---|---|---|---|
| **Tripo AI Studio** | Basic plan reported as 200 credits/month (approximately eight models, depending on current credit costs); free outputs are public and attributed under CC BY 4.0 according to the reviewed plan description. | Tripo's API is a separate business line with usage-based billing; Studio credits do not prove API credits. | `FREE_WEB_APP_MONTHLY / API_SEPARATE_PAID_BILLING`; do not promote to API Layer 2. Official product: https://www.tripo3d.ai/ ; API billing: https://platform.tripo3d.ai/docs/billing |
| **Meshy** | Free web plan reported as 100 credits/month, with export/model limits and CC BY 4.0 attribution conditions. | Official API docs say API access requires a qualifying paid plan and API credits are separately purchased. | `FREE_WEB_APP_ONLY / API_PAID_OR_PLAN_GATED`. Sources: https://www.meshy.ai/pricing ; https://docs.meshy.ai/en/api/quick-start ; https://docs.meshy.ai/en/api/pricing |
| **Rodin / Hyper3D** | Third-party trackers report small starter credits, but the amount and export eligibility conflict. | No current free public API grant confirmed. | `WEB_TRIAL_REPORTED / API_UNCONFIRMED`; do not count as Layer 3 without official API-credit terms. Discovery source: https://tools.freeaivideo.app/ |
| **Hitem3D / Hi3D, Krea, YVO3D, Masterpiece X, VARCO 3D** | Surfaced in comparison directories as browser credits, previews or trial products. | No first-party proof found in this pass that the consumer free allowance can be spent through a public developer API. | `DISCOVERY_ONLY / API_FREE_ENTITLEMENT_UNVERIFIED`. |

## Updated 3D verdict

- Layer 1: retain three.ws as the documented no-key API candidate; keep its exact route, 10/IP/day maintainer claim, shared capacity and no-live-test caveat visible.
- Layer 2: no additional provider was confirmed with a recurring free hosted API quota in this audit.
- Layer 3: do not convert Tripo/Meshy/Rodin consumer Studio credits into API trials. A finite API trial requires an explicit API wallet/credit grant.
- Keep local/open-weight TRELLIS, Hunyuan3D, TripoSR and similar model weights in the self-hosted appendix; they are not hosted free APIs.

No live 3D generation, account creation, payment-card entry or identity verification was performed.
