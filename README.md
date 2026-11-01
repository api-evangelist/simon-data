# Simon Data

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Simon Data — now trading as Simon AI, and acquired by Monetate on 30 July 2026 — is a composable, AI-first customer data platform for marketing teams. It reads customer data directly from a cloud warehouse (Snowflake, BigQuery, Redshift, Azure) without ETL, resolves identity into unified profiles, and activates segments across email, SMS, push, paid media and 70-plus downstream tools including Braze, Iterable, Attentive, Klaviyo, Salesforce Marketing Cloud, Amazon Ads and The Trade Desk. Two callable APIs are published: the Simon Signal Event Ingestion API, which accepts fourteen documented behavioural and transactional event types at a single collect endpoint, and the premium Audience API, which returns one contact profile at a time for send-time personalisation. Outbound webhooks and a Real-Time Content client cover the reverse direction, calling customer endpoints at send time.

**Areas:** Customer Data Platform · CDP · Marketing Automation · Audience Segmentation · Event Tracking · Data Ingestion · Personalization · Marketing Technology · Identity Resolution · Customer Profiles · Journey Orchestration · Snowflake

## Simon Data on APIs.io

Everything profiled for Simon Data is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/simon-data/](https://apis.io/providers/simon-data/)** — or go straight to one of the APIs or properties below.

### APIs (2)

- [Simon Data Contacts API](https://apis.io/apis/simon-data/simon-data-contacts-api/) — Contact profile lookup.
- [Simon Data Events API](https://apis.io/apis/simon-data/simon-data-events-api/) — Event collection into the Simon Signal pipeline.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Simon Data Webhooks](https://apis.io/asyncapis/simon-data/simon-data-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [simon-data](https://apis.io/servers/simon-data/simon-data/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Simon Data Agentic Access](https://apis.io/agentic-access/simon-data/simon-data-agentic-access/)

#### JSON Schema (2)

The data models the API reads and writes.

- [Simon Data Contact](https://apis.io/schemas/simon-data/simon-data-contact/)
- [Simon Data Event Payload](https://apis.io/schemas/simon-data/simon-data-event-payload/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Simon Data Context](https://apis.io/jsonld/simon-data/simon-data-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Simon Data Vocabulary](https://apis.io/vocabularies/simon-data/simon-data-vocabulary/)

#### Examples (3)

Example requests and responses.

- [Simon Data Get Contact Example](https://apis.io/examples/simon-data/simon-data-get-contact-example/)
- [Simon Data Identify Example](https://apis.io/examples/simon-data/simon-data-identify-example/)
- [Simon Data Track Transaction Example](https://apis.io/examples/simon-data/simon-data-track-transaction-example/)

#### Collections (2)

Postman and Open Collection request collections.

- [Simon Data Audience API](https://apis.io/collections/simon-data/open-simon-data-audience-api/)
- [Simon Data Event Ingestion API (Simon Signal)](https://apis.io/collections/simon-data/open-simon-data-event-ingestion/)

#### Overlays (2)

OpenAPI overlays, including conversational phrasing for each operation.

- [Simon Data Audience Api Overlay](https://apis.io/overlays/simon-data/simon-data-audience-api-overlay/)
- [Simon Data Event Ingestion Overlay](https://apis.io/overlays/simon-data/simon-data-event-ingestion-overlay/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [Simon Data — jsonschema rules](https://apis.io/rules/simon-data/simon-data-jsonschema-spectral-rules/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Simon Data Authentication](https://apis.io/security/simon-data/simon-data-authentication/)
- [Simon Data Domain Security](https://apis.io/security/simon-data/simon-data-domain-security/)
- [Simon Data Trust Center](https://apis.io/security/simon-data/simon-data-trust-center/)
- [Simon Data Vulnerability Disclosure](https://apis.io/security/simon-data/simon-data-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Simon Data Scopes](https://apis.io/scopes/simon-data/simon-data-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Simon Data Plans Pricing](https://apis.io/plans/simon-data/simon-data-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Simon Data Rate Limits](https://apis.io/rate-limits/simon-data/simon-data-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Simon Data Finops](https://apis.io/finops/simon-data/simon-data-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.simon.ai/)
- [Documentation](https://docs.simondata.com/)
- [Getting started](https://docs.simondata.com/reference/ingestion-and-egress-in-5-minutes)
- [API reference](https://docs.simondata.com/reference/getting-started)
- [Pricing](https://www.simon.ai/pricing)
- [Support](https://docs.simondata.com/docs/support-center)
- [Changelog](https://docs.simondata.com/changelog)
- [Blog](https://www.simon.ai/blog)
- [Security](https://www.simon.ai/terms/security)
- [Compliance](https://www.simon.ai/terms/security)
- [Terms of service](https://www.simon.ai/terms/terms-of-service)
- [Privacy policy](https://www.simon.ai/terms/privacy-policy)
- [GitHub](https://github.com/Radico)
- [Status](https://status.simondata.com/)

## API Evangelist rating

**Kin Score 64.8** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 76.7 |
| Contract quality | 69.9 |
| Contract governance | 28.0 |
| Operational transparency | 65.8 |
| Developer ergonomics | 44.6 |
| Access clarity | 75.0 |

**Agent readiness 46.8** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 45.1** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/simon-data/](https://apis.io/providers/simon-data/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Simon Data: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/simon-data/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
