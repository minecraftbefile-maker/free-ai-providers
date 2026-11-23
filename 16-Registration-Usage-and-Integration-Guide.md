# Provider registration and integration guide

## 1. Choose the correct product type

- **API:** for integration into an application, script, agent or backend. It needs an endpoint and a supported request format.
- **Web UI:** for a person to use through a browser. Its free plan does not automatically grant API access.
- **Local/self-hosted:** software or model weights that run on your own machine/server. This is not a hosted provider quota.

## 2. Understand the free-access layers

### Hosted API layers

1. **Layer 1 — keyless/anonymous:** actual inference endpoint works without account, key, placeholder credential or browser identity.
2. **Layer 2 — recurring free access:** account/key may be required; allowance renews daily, monthly or is continuously free under published rate limits. The native unit must be preserved.
3. **Layer 3 — one-time trial:** signup credits, limited test runs or temporary grants. These do not renew unless the provider explicitly says so.

Some catalogues contain special cases (shared gateway credits, time-limited first-year tiers, or disputed entitlements). Read each row's classification rather than forcing it into a generic quota.

### Web UI layers

The text/image/video/music browser catalogues use their own five-level system: anonymous unlimited/claimed-unlimited; anonymous limited; account-based effectively unlimited; account-based limited/recurring; and one-time trials. These Web UI layers are not the same as API layers. The relevant file defines its local layer labels.

## 3. Typical account registration workflow

1. Open the official provider website linked in the relevant file.
2. Select Sign up / Create account if the offer requires an account.
3. Use the provider's supported email or identity sign-in process. Do not bypass age, regional, phone, identity or payment eligibility checks.
4. Confirm the email if requested.
5. For APIs, open the developer dashboard or console and create a project/workspace if required.
6. Create an API key only if the official docs require it. Some keyless endpoints do not use keys; some cloud providers require project credentials or billing activation.
7. Read the free-tier page and check whether a payment card is required. Never assume “free” means no card or no overage billing.
8. Store credentials securely. If a key is exposed, revoke and rotate it.

## 4. Typical API integration workflow

1. Select the correct modality file and provider.
2. Read the provider's official quickstart/API reference.
3. Confirm base URL, endpoint path, HTTP method, authentication header, model ID, request body, accepted media format and output schema.
4. For asynchronous generation, create a task, save its task ID, then poll the documented status endpoint or use the documented callback/webhook.
5. For streaming, use the documented streaming protocol; do not assume all endpoints support SSE or WebSocket.
6. Test one short input. Validate the returned bytes/text/file, not just HTTP 200 or a model-list response.
7. Log request ID, model, usage, latency and error class without logging secrets or private input.
8. Add timeout, retry/backoff, rate-limit handling, file-size validation and cost/quota guards.

## 5. Typical Web UI workflow

1. Open the provider's official product page from the Web UI file.
2. Confirm guest access or sign in normally.
3. Check free plan limits inside the product before generating.
4. Run a short sample and confirm export/download availability.
5. Review watermark, privacy, visibility, retention and commercial-use rules.

## 6. Quota and billing safety

- Do not convert credits to songs/minutes/images unless the provider publishes the conversion for the exact model and settings.
- Shared balances must be counted once across every modality using that pool.
- A requests-per-minute ceiling is a rate limit, not a daily or monthly free balance.
- “First 12 months free” is not a permanent recurring tier.
- If billing activation or a payment method is required, mark it clearly and do not treat it as no-card access.
- Set provider-side budget alerts or hard limits where available.

## 7. Quality and compatibility checks

- LLM: text completion, streaming, tool calling/structured output, context limits and model availability.
- Image: prompt adherence, dimensions, formats, generation latency and safety filters.
- Video: clip duration, resolution, frame rate, queue time, task polling and output expiry.
- Music: full song vs instrumental/loop, vocals, duration, stems, MIDI and export format.
- TTS: language, dialect, voice quality, pronunciation, streaming and audio format.
- STT: language/dialect, noise, timestamps, diarization, streaming and file limits.
- 3D: geometry quality, topology, textures/materials, file format, mesh limits and editability.

## 8. Evidence labels and confidence

- **OFFICIAL/DOCS_VERIFIED:** provider documentation states the feature or allowance; not necessarily live-tested.
- **REPORTED:** third-party report or user report; verify with provider.
- **CONFLICTED:** official pages or sources disagree. Keep the uncertainty visible.
- **CANDIDATE_UNTESTED / NOT_LIVE_TESTED:** no successful real generation request was performed.
- **GENERATION_OK:** only use when an actual generation call returned a usable output.
- **WEB_UI_ONLY / API_UNCONFIRMED:** browser product exists, but API entitlement was not established.

## 9. Security, privacy and legal checks

Never publish API keys. Avoid sending confidential or personal data to providers without reviewing retention/training terms. Check output licensing, attribution, redistribution, commercial use, geographic eligibility and age requirements. Free output does not automatically mean unrestricted rights.

## 10. Source and date discipline

The provider inventory is based on the original catalogue research snapshot dated **23 November 2026**. Every quota, plan, endpoint, region and feature can change. Re-open official pricing/docs before depending on an offer. Discovery directories and community posts are leads, not proof of provider policy.
