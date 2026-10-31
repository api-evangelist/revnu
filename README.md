# Revnu

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

Revnu is an AI growth-automation platform for early-stage and technical founders, positioning itself as an "AI growth hire" that runs marketing work across channels so builders can stay in the codebase. The platform finds and qualifies leads from real signals, drafts cold outbound and partnership pitches, writes SEO content, runs paid ad experiments across Meta, LinkedIn, Reddit, and TikTok, turns product wins into short-form video and social posts, and tests pricing and landing-page copy. Founded in 2026 out of the Y Combinator Spring 2026 batch and based in San Francisco, Revnu is agent-first rather than API-first: it publishes no OpenAPI, but it does ship a live remote MCP server with a documented 49-tool surface, a first-party CLI, an authentication SDK for a customer's own app, an HMAC-signed webhook catalog, an RFC 9727 api-catalog, and machine-readable llms.txt context files across its hosts.

**Areas:** Company · Growth Automation · Marketing · Artificial Intelligence · Software-as-a-Service · Startups · Lead Generation · SEO · MCP · Agents · Commerce · A/B Testing

## Revnu on APIs.io

Everything profiled for Revnu is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/revnu/](https://apis.io/providers/revnu/)** — or go straight to one of the APIs or properties below.

### APIs (5)

- [Revnu MCP Server](https://apis.io/apis/revnu/revnu-mcp-server/) — A live remote MCP server over streamable HTTP that gives an AI assistant operator-level control of a Revnu store — 49 documented tools across store,…
- [Revnu Auth API](https://apis.io/apis/revnu/revnu-auth-api/) — The authentication API behind the @revnu/auth SDK, serving a Revnu store's buyers. Purchase-first — buying a product creates the account and sends a…
- [Revnu API Reference API](https://apis.io/apis/revnu/revnu-api-reference-api/) — The personal-token API at /api/v1: review queue, agent, results, workflows, leads, LinkedIn lookups and the block list, plus the no-token website preview.
- [Revnu Content API](https://apis.io/apis/revnu/revnu-content-api-api/) — Read-only JSON for the posts Revnu publishes, for rendering a blog on your own site.
- [Revnu Measurement API](https://apis.io/apis/revnu/revnu-measurement-api/) — Server-side conversion events, tied back to the visit that brought the customer.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Revnu Webhooks](https://apis.io/asyncapis/revnu/revnu-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [revnu](https://apis.io/servers/revnu/revnu/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Revnu Agentic Access](https://apis.io/agentic-access/revnu/revnu-agentic-access/)

#### JSON Schema (6)

The data models the API reads and writes.

- [BackgroundTask](https://apis.io/schemas/revnu/revnu-background-task/)
- [LinkedinPersonAccount](https://apis.io/schemas/revnu/revnu-linkedin-person-account/)
- [NavItem](https://apis.io/schemas/revnu/revnu-nav-item/)
- [ProviderUsage](https://apis.io/schemas/revnu/revnu-provider-usage/)
- [ResultsWindowResult](https://apis.io/schemas/revnu/revnu-results-window-result/)
- [ReviewCardWire](https://apis.io/schemas/revnu/revnu-review-card-wire/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Revnu Context](https://apis.io/jsonld/revnu/revnu-context/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Revnu Openapi Overlay](https://apis.io/overlays/revnu/revnu-openapi-overlay/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [Revnu API Rules](https://apis.io/rules/revnu/revnu-rules/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Revnu Authentication](https://apis.io/security/revnu/revnu-authentication/)
- [Revnu Domain Security](https://apis.io/security/revnu/revnu-domain-security/)
- [Revnu Trust Center](https://apis.io/security/revnu/revnu-trust-center/)
- [Revnu Vulnerability Disclosure](https://apis.io/security/revnu/revnu-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Revnu Plans Pricing](https://apis.io/plans/revnu/revnu-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Revnu Rate Limits](https://apis.io/rate-limits/revnu/revnu-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://revnu.com)
- [Documentation](https://auth.revnu.app/docs)
- [Getting started](https://auth.revnu.app/docs/getting-started)
- [API reference](https://auth.revnu.app/docs/mcp)
- [Pricing](https://revnu.com/pricing)
- [Sign up](https://revnu.com/book)
- [Support](https://revnu.com/faq)
- [Changelog](https://auth.revnu.app/changelog)
- [Blog](https://revnu.com/blog)
- [Terms of service](https://revnu.com/terms)
- [Privacy policy](https://revnu.com/privacy)
- [GitHub](https://github.com/revnu-app)

## API Evangelist rating

**Kin Score 48.6** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 39.0 |
| Contract governance | 4.5 |
| Operational transparency | 28.9 |
| Developer ergonomics | 63.7 |
| Access clarity | 65.8 |

**Agent readiness 37.6** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | verified |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 22.7** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/revnu/](https://apis.io/providers/revnu/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Revnu: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/revnu/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
