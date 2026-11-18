# Apify Pay-Per-Event (PPE) Actors — Zero-CAPTCHA Python Suite

A production-ready monorepo of lightweight, **zero-CAPTCHA, zero-browser** Python Apify Actors priced on the **Pay-Per-Event (`PAY_PER_EVENT`)** model. Each subdirectory is 100% self-contained with its own `.actor/` metadata, `pay_per_event.json`, `input_schema.json`, `requirements.txt`, and `Dockerfile` for direct 1-click **Apify Console -> Import from GitHub**.

## Included Pay-Per-Event Actors

| Directory | Actor Name | Primary Charge Event | Price (USD) | Target Workflow |
|---|---|---|---:|---|
| [`jp-llm-compliance-pii-guard/`](./jp-llm-compliance-pii-guard/) | `jp-llm-compliance-pii-guard` | `document_processed` | `$0.002` | Check-digit-verified Japanese Invoice (`T+13`), Corporate ID, MyNumber, card/phone/email redaction + bilingual prompt-injection screening |
| [`podcast-rss-transcript-extractor/`](./podcast-rss-transcript-extractor/) | `podcast-rss-transcript-extractor` | `episode_extracted` | `$0.004` | Apple Podcasts ID / iTunes Search resolution, safe RSS XML parsing, clean show notes, chapters & normalized Podcasting 2.0 transcripts (`SRT`/`VTT`/`JSON`/`TXT`) |
| [`japan-corporate-ir-press-extractor/`](./japan-corporate-ir-press-extractor/) | `japan-corporate-ir-press-extractor` | `filing_extracted` | `$0.003` | Real-time Japanese TDnet, JPX, BOJ, METI & PR RSS/Atom/JSON extraction with TSE stock codes (`7203`, `141A`), NTA Corporate Number enrichment & IR categorization |

## Monetization & Revenue-Share Model

All three Actors are configured with Apify **Pay-Per-Event (`PAY_PER_EVENT`)** pricing (`isPPEPlatformUsagePaidByUser: false` and `minimalMaxTotalChargeUsd: 0.05` in `.actor/pay_per_event.json`):

- **Zero Browser / Zero Proxy Compute Overhead**: Pure `httpx` + Python 3.11 XML/JSON/text engines minimize Apify platform compute costs per run, maximizing creator net margin under Apify's Store payout model (`80%` gross revenue share minus underlying platform usage costs).
- **Deterministic Checkpointing**: `Actor.charge(event_name=..., count=1)` is invoked only as each validated record is pushed to the dataset via `Actor.push_data(...)`.
- **No Anti-Bot or CAPTCHA Fragility**: Relies strictly on public APIs (`itunes.apple.com`), official RSS/Atom/RDF feeds (`jpx.co.jp`, `boj.or.jp`, `meti.go.jp`, `prtimes.jp`), public timely disclosure JSON (`webapi.yanoshin.jp`), and deterministic local compliance algorithms.

## Apify Console Import Instructions (GitHub)

To deploy any Actor directly into your Apify Console account with zero local CLI setup:

1. Open **Apify Console -> Actors -> Create new -> Link Git repository**.
2. Set **Git URL** to `https://github.com/pecopeko/apify-ppe-actors` and **Branch** to `main`.
3. Set **Folder** to one of the three self-contained actor directories:
   - `jp-llm-compliance-pii-guard`
   - `podcast-rss-transcript-extractor`
   - `japan-corporate-ir-press-extractor`
4. Click **Build**, verify `.actor/pay_per_event.json` in **Monetization**, and publish to the Apify Store.

## Security & XML Safety

- All XML feed parsers (`podcast-rss-transcript-extractor`, `japan-corporate-ir-press-extractor`) explicitly reject `<!DOCTYPE` and `<!ENTITY` declarations outside CDATA blocks to prevent XML entity expansion (Billion Laughs) attacks.
- HTTP(S) scheme validation is enforced on all feed, transcript, and chapter URLs.
