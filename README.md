# Free AI Providers — Modular Research Library

**Edition:** v3 — API / Web UI split + comprehensive audit
**Research snapshot inherited from source:** 23 November 2026
**Purpose:** a navigable Markdown reference for free or trial-based AI providers, separated by modality and by delivery method.

## Start here

Read `16-Registration-Usage-and-Integration-Guide.md` first. It explains API vs Web UI vs self-hosted, registration, API-key handling, testing, quotas, evidence labels, privacy and licensing. Then open only the modality and delivery type you need.

## Complete file map

| File | What it contains |
|---|---|
| `01-LLM-APIs.md` | Hosted LLM/text-generation APIs, keyless gateways, recurring quotas and trials. |
| `02-LLM-Web-UI.md` | Browser chat and text-generation products. |
| `03-Image-Generation-APIs.md` | Hosted image-generation APIs. |
| `04-Image-Generation-Web-UI.md` | Browser image generators and their free-plan layers. |
| `05-Video-Generation-APIs.md` | Hosted video-generation APIs. |
| `06-Video-Generation-Web-UI.md` | Browser video generators and free-plan layers. |
| `07-Music-Generation-APIs.md` | Hosted music-generation/composition APIs and API trials. |
| `08-Music-Generation-Web-UI.md` | Browser music products, exports, quotas and local-WebGPU tools. |
| `09-TTS-APIs.md` | Hosted text-to-speech APIs. |
| `10-TTS-Web-UI.md` | TTS browser evaluation guide; a complete provider inventory is not yet supported by the source. |
| `11-STT-APIs.md` | Hosted speech-to-text/transcription APIs. |
| `12-STT-Web-UI.md` | STT browser evaluation guide; a complete provider inventory is not yet supported by the source. |
| `13-3D-Generation-APIs.md` | Hosted 3D generation APIs. |
| `14-3D-Generation-Web-UI.md` | Browser 3D generators and studio plans. |
| `15-3D-Local-Models-and-Asset-Libraries.md` | Open-weight/self-hosted 3D models and free asset libraries. |
| `16-Registration-Usage-and-Integration-Guide.md` | Full registration, API usage, browser usage, testing, quota, security and evidence guide. |
| `17-Comprehensive-Audit-and-Research-Updates.md` | Retained layer definitions, new provider additions, corrections, evidence boundaries and cross-category audit checklist. |

## Navigation rules

- Need a programmatic endpoint? Open the `*-APIs.md` file for that modality.
- Need a website you can use manually? Open the `*-Web-UI.md` file.
- Need a local model or asset library? Open the 3D local/asset appendix.
- Need account setup or integration instructions? Open file 16.

## Layer systems

**API catalogues:** generally Layer 1 = truly anonymous/keyless endpoint; Layer 2 = recurring or continuing free API access; Layer 3 = finite signup/trial credits. Special cases and conflicts remain explicitly labeled.

**Web UI catalogues:** use a separate five-layer model documented inside the relevant UI files. Do not compare UI layers directly with API layers.

## Important accuracy rules

1. A free Web UI plan is not a free API plan.
2. A successful model-list endpoint is not proof of generation.
3. Credits, characters, requests, audio minutes, Neurons and tokens are different units.
4. Shared account balances must not be multiplied across modalities.
5. One-time signup credits are not recurring quotas.
6. An official pricing statement is not a live generation test. Only explicit `GENERATION_OK` means a usable output was generated.
7. Do not assume free means no payment card, no age/region restrictions, commercial rights or permanent availability.
8. Keep API keys private; never put secrets in Markdown or public code.

## Latest audit and additions

The v3 update retains the API three-layer and Web UI five-layer systems. It adds Kilo and OVH anonymous LLM routes, AI Horde as a separate public-placeholder route, Gizmo and SenseNova recurring API offers, BlazeAPI and Novita candidates, deAPI shared multimodal trial credits, and current corrections for Cloudflare, Groq TTS, Cohere and the ended ACLIDE project. See file 17 for the audit summary and sources.

## Research limitations

This v3 pack reorganizes, expands and audits the supplied research ledger. It preserves the original claims, source links, classifications and uncertainty rather than silently upgrading unverified entries. TTS and STT browser-only inventories were not comprehensively established in the source, so their UI files deliberately provide evaluation criteria instead of invented provider lists. No live API calls were run for the new v3 additions; their evidence labels remain documentation-backed or candidate-only.

## Source provenance

Derived from the Library document `Free AI - Music Providers Expanded.md` (originally about 574 KB) and the prior split research pack. Research snapshot: 23 November 2026. Recheck provider official docs and pricing before deployment.

## File list

- `01-LLM-APIs.md`
- `02-LLM-Web-UI.md`
- `03-Image-Generation-APIs.md`
- `04-Image-Generation-Web-UI.md`
- `05-Video-Generation-APIs.md`
- `06-Video-Generation-Web-UI.md`
- `07-Music-Generation-APIs.md`
- `08-Music-Generation-Web-UI.md`
- `09-TTS-APIs.md`
- `10-TTS-Web-UI.md`
- `11-STT-APIs.md`
- `12-STT-Web-UI.md`
- `13-3D-Generation-APIs.md`
- `14-3D-Generation-Web-UI.md`
- `15-3D-Local-Models-and-Asset-Libraries.md`
- `16-Registration-Usage-and-Integration-Guide.md`
- `17-Comprehensive-Audit-and-Research-Updates.md`

