# Horizon-Money Apify Store Pay-Per-Event (PPE) Actor Suite (12 Actors)

Low-overhead, zero-API-key, Pay-Per-Event Python Actors ready to link per subdirectory in Apify Console.

| # | Actor Folder / Slug | Primary PPE Event | Price / Event | Domain / Focus |
|---|---|---|---|---|
| 1 | `jp-llm-compliance-pii-guard` | `document_processed` | `$0.002` | Japanese T+13 / MyNumber check-digit PII redaction & prompt-injection guard |
| 2 | `podcast-rss-transcript-extractor` | `episode_extracted` | `$0.004` | Apple Podcast & RSS 2.0 `podcast:transcript` (SRT/VTT/JSON/TXT) normalizer |
| 3 | `japan-corporate-ir-press-extractor` | `filing_extracted` | `$0.003` | JPX/TDnet/METI/BOJ/PR Times corporate IR disclosure extractor + Corporate ID enrichment |
| 4 | `jp-yakki-keihyo-ad-auditor` | `ad_copy_audited` | `$0.003` | Japanese Yakki-ho (薬機法), Keihyo-ho (No.1/Pricing), & stealth-marketing auditor |
| 5 | `jp-qualified-invoice-zengin-validator` | `record_validated` | `$0.001` | NTA Mod-9 Invoice/Corporate ID validator, Zengin half-width kana converter & 120B checker |
| 6 | `shopify-public-catalog-feed-extractor` | `product_extracted` | `$0.002` | Fast browserless Shopify `/products.json` catalog, SKU, price & stock extractor |
| 7 | `sec-edgar-8k-10k-item-extractor` | `filing_extracted` | `$0.004` | Official SEC `data.sec.gov` 8-K/10-K/10-Q filings + US-GAAP XBRL snapshot extractor |
| 8 | `mcp-registry-llms-txt-auditor` | `domain_audited` | `$0.002` | Domain AI agent readiness (`/llms.txt`, `/.well-known/mcp.json`, AI bot `robots.txt`) scorer |
| 9 | `jp-b2b-contract-keiyaku-auditor` | `contract_audited` | `$0.004` | Japanese Subcontract Act (60d), Freelance Act, Liability/IP & Stamp Tax auditor |
| 10 | `geo-sitemap-jsonld-citation-auditor` | `site_audited` | `$0.002` | GEO Schema.org JSON-LD `@type`, XML sitemap freshness & AI search citation readiness scorer |
| 11 | `jp-tokushoho-darkpattern-ec-auditor` | `page_audited` | `$0.003` | Japanese Tokushoho (Art.11 / Art.12-6) & recurring checkout dark-pattern auditor |
| 12 | `security-txt-caa-dmarc-posture-auditor` | `domain_audited` | `$0.002` | RFC 9118 `/.well-known/security.txt` & HTTP hardening headers posture scorer |
### Wave 5 Actors (#13–#14)
13. **`jp-denchoho-filename-ledger-validator`** (`record_validated` @ `$0.001`) — Normalize messy Japanese invoice/receipt strings (Wareki `令和`/`R`/full-width) into Revised Electronic Books Preservation Act `YYYYMMDD_Partner_Amount.pdf` filenames with NTA Mod-9 T-number check.
14. **`oss-sbom-copyleft-license-auditor`** (`manifest_audited` @ `$0.003`) — Screen `package.json`, `requirements.txt`, and SBOM package records for strong/network copyleft licenses (`AGPL`/`GPL`/`SSPL`/`BUSL`), weak copyleft (`MPL`/`LGPL`), unknown SPDX fields, and unpinned dependencies.

### Wave 6 Actors (15-16)
- `jp-appi-privacy-gaibusoshin-auditor`: Japan APPI (Art.17/23/27/28/32) & Telecom Art. 27-12 external transmission SDK auditor (`policy_audited` @ `$0.003`).
- `openapi-agent-tool-readiness-auditor`: OpenAPI 3.x & MCP agent tool schema readiness auditor (`spec_audited` @ `$0.003`).

### Wave 7 Actors (17-18)
- `jp-withholding-tax-shiharai-auditor`: Japan Art. 204 withholding (`10.21%`/`20.42%`), NTA No. 6929 check, net gross-up solver, & Oct 2026 `50%` Invoice transitional cost auditor (`payment_audited` @ `$0.002`).
- `github-actions-workflow-supplychain-auditor`: GitHub Actions CI supply-chain auditor checking unpinned 3rd-party actions, `pull_request_target` head checkout, script injection, excessive permissions, and `curl|sh` (`workflow_audited` @ `$0.003`).
