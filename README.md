# Horizon-Money Apify Store Pay-Per-Event (PPE) Actor Suite (42 Actors)

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
| 12 | `security-txt-caa-dmarc-posture-auditor` | `domain_audited` | `$0.002` | RFC 9120 `/.well-known/security.txt` & HTTP hardening headers posture scorer |
### Wave 5 Actors (#13–#14)
13. **`jp-denchoho-filename-ledger-validator`** (`record_validated` @ `$0.001`) — Normalize messy Japanese invoice/receipt strings (Wareki `令和`/`R`/full-width) into Revised Electronic Books Preservation Act `YYYYMMDD_Partner_Amount.pdf` filenames with NTA Mod-9 T-number check.
14. **`oss-sbom-copyleft-license-auditor`** (`manifest_audited` @ `$0.003`) — Screen `package.json`, `requirements.txt`, and SBOM package records for strong/network copyleft licenses (`AGPL`/`GPL`/`SSPL`/`BUSL`), weak copyleft (`MPL`/`LGPL`), unknown SPDX fields, and unpinned dependencies.

### Wave 6 Actors (15-16)
- `jp-appi-privacy-gaibusoshin-auditor`: Japan APPI (Art.17/23/27/28/32) & Telecom Art. 27-12 external transmission SDK auditor (`policy_audited` @ `$0.003`).
- `openapi-agent-tool-readiness-auditor`: OpenAPI 3.x & MCP agent tool schema readiness auditor (`spec_audited` @ `$0.003`).

### Wave 7 Actors (17-18)
- `jp-withholding-tax-shiharai-auditor`: Japan Art. 204 withholding (`10.21%`/`20.42%`), NTA No. 6929 check, net gross-up solver, & Oct 2026 `50%` Invoice transitional cost auditor (`payment_audited` @ `$0.002`).
- `github-actions-workflow-supplychain-auditor`: GitHub Actions CI supply-chain auditor checking unpinned 3rd-party actions, `pull_request_target` head checkout, script injection, excessive permissions, and `curl|sh` (`workflow_audited` @ `$0.003`).

### Wave 8 Actors (19-20)
- `jp-labor-notice-overtime-36-auditor`: Japan April 2024 Employment Notice, Supreme Court 3-part fixed overtime, >60h 1.50x overtime math, min wage & Art. 36 rolling 80h auditor (`notice_audited` @ `$0.003`).
- `dockerfile-compose-k8s-security-auditor`: Dockerfile, Docker Compose & Kubernetes manifest hardening auditor detecting `:latest`/untagged images, root containers, ENV/ARG secrets, privileged/host networks, and `curl|sh` (`manifest_audited` @ `$0.003`).

### Wave 9 Actors (21-22)
- `jp-jis8341-wcag-accessibility-auditor`: Japan Revised Disability Discrimination Act & JIS X 8341-3:2016 / WCAG 2.2 AA auditor checking sRGB contrast math (4.5:1 / 3.0:1), alt/label/lang/title/heading order, viewport zoom locks, and skip links (`page_audited` @ `$0.004`).
- `terraform-hcl-security-finops-auditor`: Terraform HCL security & FinOps auditor catching public 0.0.0.0/0 SGs, wildcard IAM policies, unencrypted S3/RDS/EBS volumes, hardcoded cloud credentials, and unpinned/oversized GPU/DB instances (`module_audited` @ `$0.003`).

### Wave 10 Actors (23-24)
- `jp-meti-supplychain-security-auditor`: Japan METI Supply Chain Security (Star 3/4), PPC breach reporting SLA (3-5d / 30-60d), Unfair Competition Trade Secret 3 requirements, & SPF/DMARC (RFC 7208 10-lookup limit) auditor (`checksheet_audited` @ `$0.004`).
- `postgres-mysql-migration-lock-safety-auditor`: PostgreSQL & MySQL zero-downtime SQL migration lock safety auditor catching non-CONCURRENTLY indexes, CONCURRENTLY inside transactions, TYPE rewrites, FK validation locks, unacknowledged DROP/TRUNCATE, and unbounded DML (`migration_audited` @ `$0.003`).

### Wave 11 Actors (25-26)
- `jp-meti-ai-governance-copyright304-auditor`: Japan METI/MIC AI Guidelines v1.1, Copyright Act Art. 30-4 (non-enjoyment & artist style mimicry), Shadow AI opt-out, EU AI Act risk tier & OSS model license auditor (`guideline_audited` @ `$0.004`).
- `web-csp-cors-cookie-hardening-auditor`: HTTP security headers & Next.js/Nginx config auditor catching wildcard/reflected CORS credentials, unsafe CSP inline/eval, missing clickjacking guards, weak HSTS, insecure cookies, and X-Powered-By/Server leaks (`config_audited` @ `$0.003`).

### Wave 12 Actors (27-30)
- `jp-hansha-ubo-whistleblower-auditor`: Japan Anti-Social Forces exclusion clauses (past-5yr rep, Kyoseisha, immediate termination, damage waiver), Criminal Proceeds Act >25% indirect UBO tree calculator + 7yr retention, and Revised Whistleblower Protection Act auditor (`screening_audited` @ `$0.004`).
- `graphql-schema-dos-introspection-auditor`: GraphQL SDL & server config auditor catching exposed introspection/GraphiQL, missing depthLimit on nested object cycles, unguarded query batching, unprotected sensitive fields (`passwordHash`/`myNumber`), unbounded Query lists, and disabled CSRF protection (`schema_audited` @ `$0.003`).

29. `jp_fefta_export_control_actor/` (`jp-fefta-export-control-deemed-export-auditor` — FEFTA Lists 1-15, Catch-All 16, Deemed Export Categories 1-3, US EAR De Minimis `export_screening_audited` @ `$0.004`)
30. `oauth_jwt_oidc_hardening_actor/` (`oauth2-oidc-jwt-security-hardening-auditor` — OAuth2/OIDC & JWT `alg=none`/claim bypass/PKCE/redirect URI/token TTL auditor `auth_config_audited` @ `$0.003`)

### Wave 14 Actors (31-32)
31. `jp-ssbj-ghg-carbon-greenwash-auditor/` (`ghg_disclosure_audited` @ `$0.004` — Japan SSBJ S1/S2, SHK 3,000 t-CO2 EEGS threshold, Scope 1/2 Location vs Market minus non-fossil certs, Scope 3 Cat.1 & Greenwash claim auditor)
32. `mcp-agent-tool-poisoning-security-auditor/` (`mcp_config_audited` @ `$0.003` — MCP server manifest & agent tool schema auditor detecting hidden prompt-injection poisoning, unpinned `npx -y`, leaked secrets, unsafe host mounts, cleartext HTTP, and unconstrained schema sinks)

### Wave 15 Actors (33-34)
33. `jp-construction-kensetsugyo-2024-compliance-auditor/` (`construction_contract_audited` @ `$0.004` — Japan Revised Construction Business Act Art. 19 written terms, Standard Labor/Welfare breakdown & no-dumping, price escalation consultation, 2025 Tokutei 50M/80M JPY license thresholds & 2024 overtime caps)
34. `llm-rag-prompt-leak-vector-poisoning-auditor/` (`rag_chunk_audited` @ `$0.003` — LLM RAG knowledge chunk & vector-index auditor detecting indirect injection, Markdown exfiltration beacons, multi-tenant ACL bypasses, leaked keys, oversized chunk_size/top_k, and unverified ingestion)

### Wave 16 Actors (35-36)
35. `jp-logistics-2025-butsuryu-hakobi-auditor/` (`logistics_contract_audited` @ `$0.004` — Japan Revised Logistics Efficiency Act 90,000t/yr Specific Shipper CLO, wait+handling <=2h rule, Truck Act Standard Tariff 90% floor & Actual Carrier <=Tier 2, 2024 driver binding/rest caps)
36. `cicd-slsa-vex-provenance-auditor/` (`provenance_audited` @ `$0.003` — SLSA Provenance, OpenVEX & Build-Install supply-chain auditor catching curl|sh remote installers, dangerous npm/pip install hooks, skipped attestation checks, mutable @main/:latest refs, and unjustified VEX suppressions)

### Wave 17 Actors (37-38)
37. `jp-toriteki-2026-subcontract-act-auditor/` (`toriteki_contract_audited` @ `$0.004` — Japan 2026 Toriteki Act Revised Subcontract Act, 300/100 employee headcount scope, promissory note & discount-fee ban, 60-day cash settlement, bilateral cost pass-through talk & unpaid mold custody auditor)
38. `kubernetes-rbac-networkpolicy-pss-auditor/` (`cluster_policy_audited` @ `$0.003` — Kubernetes RBAC wildcard/cluster-admin, ServiceAccount token automounting, NetworkPolicy open-CIDR/podSelector, PodSecurity privileged/baseline, Admission webhook failurePolicy: Ignore & quota auditor)

### Wave 18 Actors (39-40)
39. `jp-fsc-kyc-aml-fatf-cryptopayment-auditor/` (`aml_compliance_audited` @ `$0.004` — Japan Payment Services Act 50% security deposit over ¥10M unused prepaid balance, Type 2 ¥1M remittance limit, Criminal Proceeds Act 7-year KYC/STR/JAFIC & FATF Travel Rule auditor)
40. `ai-agent-prompt-tool-guard-eval-auditor/` (`agent_trace_audited` @ `$0.003` — AI agent prompt-injection, system-prompt/env leak, cloud metadata SSRF, unsandboxed shell/eval, webhook exfiltration & missing HITL gate auditor)

### Wave 19 Actors (41-42)
41. `jp-asbj34-new-lease-accounting-auditor/` (`lease_contract_audited` @ `$0.004` — Japan ASBJ Statement No. 34 New Lease Accounting (Apr 2027) on-balance PV Lease Liability, short-term <=12m / low-value <=¥3M exemptions & embedded SaaS/logistics lease auditor)
42. `ci-env-secret-key-leak-entropy-auditor/` (`secret_scan_audited` @ `$0.003` — CI/workflow log, `.env`, and app config scanner detecting cloud/API secret exposures and unsafe TLS/debug overrides)
