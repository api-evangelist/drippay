# Drippay

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

Drippay, Inc. is a Y Combinator company (YC P26) that operates two connected products. dreach — renamed from drip in 2026, with usedrip.ai now redirecting to dreach.ai — is a local-first Mac app for staffing, recruiting and executive search firms: an Opportunity Radar that watches hiring demand and leadership changes, drafts outreach in the user's voice, follows up, and books meetings, with a hosted MCP server at mcp.drippay.dev exposing seven outbound tools to any HTTP MCP client over OAuth. The Drip API is a separate usage-based billing and execution-ledger platform for AI agents — a Stripe-like metering and monetization backend covering customers, subscriptions, pricing plans, billable metrics, usage events, invoices, credit notes, coupons, entitlements, charges, dunning, tax, contracts, drift detection and webhooks across 245 REST operations at api.drippay.dev. It ships official Node, Python and C++ SDKs and a drip-cli binary, an idempotencyKey contract, cursor pagination, role-scoped secret keys, an x402 payment-required flow for agent self-settlement, and a SOC 2 Type I posture monitored with Vanta.

**Areas:** Company · Billing · Usage-Based Billing · Metering · Monetization · Payments · AI Agents · Developer Tools · Webhook · MCP · CRM · Sales Automation

## Drippay on APIs.io

Everything profiled for Drippay is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/drippay/](https://apis.io/providers/drippay/)** — or go straight to one of the APIs or properties below.

### APIs (23)

- [Drippay Business API](https://apis.io/apis/drippay/drippay-business-api/) — Business-level settings and configuration.
- [Drippay Charges API](https://apis.io/apis/drippay/drippay-charges-api/) — View charge history and settlement status.
- [Drippay Contracts API](https://apis.io/apis/drippay/drippay-contracts-api/) — Per-customer commercial agreements with custom pricing, prepaid commits, and spend caps. All contract endpoints require a secret key (`sk_*`) with the…
- [Drippay Coupons API](https://apis.io/apis/drippay/drippay-coupons-api/) — Coupons and promotion codes for discounts.
- [Drippay Credit Notes API](https://apis.io/apis/drippay/drippay-credit-notes-api/) — Create, issue, and void credit notes.
- [Drippay Customer Portal API](https://apis.io/apis/drippay/drippay-customer-portal-api/) — Self-service customer portal for profile, subscriptions, and address management.
- [Drippay Customers API](https://apis.io/apis/drippay/drippay-customers-api/) — Create and manage billable customers.
- [Drippay Drift API](https://apis.io/apis/drippay/drippay-drift-api/) — The Drift API from Drippay — 6 operation(s) for drift.
- [Drippay Dunning API](https://apis.io/apis/drippay/drippay-dunning-api/) — Automatic retry + dunning email flow for failed payments. Configure a per-business retry schedule, list failed charges in collections, and manually…
- [Drippay Entitlements API](https://apis.io/apis/drippay/drippay-entitlements-api/) — Quota management and pre-request access checks.
- [Drippay Events API](https://apis.io/apis/drippay/drippay-events-api/) — Record execution events for observability.
- [Drippay Integrations API](https://apis.io/apis/drippay/drippay-integrations-api/) — Manage billing, CRM, and marketplace integrations (Stripe, Xero, Salesforce).
- [Drippay Internal API](https://apis.io/apis/drippay/drippay-internal-api/) — The Internal API from Drippay — 1 operation(s) for internal.
- [Drippay Invoices API](https://apis.io/apis/drippay/drippay-invoices-api/) — Generate, issue, and manage invoices. Supports usage-based and subscription-based billing periods.
- [Drippay Pricing Plans API](https://apis.io/apis/drippay/drippay-pricing-plans-api/) — Define per-unit pricing for usage types. Creating, updating, and deleting plans requires a secret key (`sk_*`) with the `ADMIN` role.
- [Drippay Product Categories API](https://apis.io/apis/drippay/drippay-product-categories-api/) — Controlled taxonomy for strict-products governance. Groups pricing plans into service-line categories for ARR rollups and revenue reporting.
- [Drippay Runs API](https://apis.io/apis/drippay/drippay-runs-api/) — Start, update, and inspect agent runs.
- [Drippay Subscriptions API](https://apis.io/apis/drippay/drippay-subscriptions-api/) — Recurring billing and subscription lifecycle management.
- [Drippay Tax API](https://apis.io/apis/drippay/drippay-tax-api/) — Sales tax configuration: customer tax addresses, exemptions, business registrations, and jurisdiction rates. Requires a secret key with ADMIN role and full…
- [Drippay Usage API](https://apis.io/apis/drippay/drippay-usage-api/) — Record metered usage. Creates charges when a pricing plan matches.
- [Drippay Webhooks API](https://apis.io/apis/drippay/drippay-webhooks-api/) — Manage webhook endpoints for real-time event notifications.
- [Drippay Workflows API](https://apis.io/apis/drippay/drippay-workflows-api/) — Define workflow templates for agent execution.
- [Drippay Billable Metrics API](https://apis.io/apis/drippay/drippay-billable-metrics-api/) — Evaluate and preview billable metrics.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Drippay Webhooks](https://apis.io/asyncapis/drippay/drippay-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [dripos-cloud](https://apis.io/servers/drippay/dripos-cloud/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Drippay Agentic Access](https://apis.io/agentic-access/drippay/drippay-agentic-access/)

#### Collections (23)

Postman and Open Collection request collections.

- [Drip BillableMetrics API](https://apis.io/collections/drippay/open-drippay-billablemetrics-api/)
- [Drip BillableMetrics Business API](https://apis.io/collections/drippay/open-drippay-business-api/)
- [Drip BillableMetrics Charges API](https://apis.io/collections/drippay/open-drippay-charges-api/)
- [Drip BillableMetrics Contracts API](https://apis.io/collections/drippay/open-drippay-contracts-api/)
- [Drip BillableMetrics Coupons API](https://apis.io/collections/drippay/open-drippay-coupons-api/)
- [Drip BillableMetrics Credit Notes API](https://apis.io/collections/drippay/open-drippay-credit-notes-api/)
- [Drip BillableMetrics Customer Portal API](https://apis.io/collections/drippay/open-drippay-customer-portal-api/)
- [Drip BillableMetrics Customers API](https://apis.io/collections/drippay/open-drippay-customers-api/)
- [Drip BillableMetrics Drift API](https://apis.io/collections/drippay/open-drippay-drift-api/)
- [Drip BillableMetrics Dunning API](https://apis.io/collections/drippay/open-drippay-dunning-api/)
- [Drip BillableMetrics Entitlements API](https://apis.io/collections/drippay/open-drippay-entitlements-api/)
- [Drip BillableMetrics Events API](https://apis.io/collections/drippay/open-drippay-events-api/)
- [Drip BillableMetrics Integrations API](https://apis.io/collections/drippay/open-drippay-integrations-api/)
- [Drip BillableMetrics Internal API](https://apis.io/collections/drippay/open-drippay-internal-api/)
- [Drip BillableMetrics Invoices API](https://apis.io/collections/drippay/open-drippay-invoices-api/)
- [Drip BillableMetrics Pricing Plans API](https://apis.io/collections/drippay/open-drippay-pricing-plans-api/)
- [Drip BillableMetrics Product Categories API](https://apis.io/collections/drippay/open-drippay-product-categories-api/)
- [Drip BillableMetrics Runs API](https://apis.io/collections/drippay/open-drippay-runs-api/)
- [Drip BillableMetrics Subscriptions API](https://apis.io/collections/drippay/open-drippay-subscriptions-api/)
- [Drip BillableMetrics Tax API](https://apis.io/collections/drippay/open-drippay-tax-api/)
- [Drip BillableMetrics Usage API](https://apis.io/collections/drippay/open-drippay-usage-api/)
- [Drip BillableMetrics Webhooks API](https://apis.io/collections/drippay/open-drippay-webhooks-api/)
- [Drip BillableMetrics Workflows API](https://apis.io/collections/drippay/open-drippay-workflows-api/)

#### Overlays (24)

OpenAPI overlays, including conversational phrasing for each operation.

- [Drippay Billable Metrics Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-billable-metrics-api-phrasing-overlay/)
- [Drippay Business Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-business-api-phrasing-overlay/)
- [Drippay Charges Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-charges-api-phrasing-overlay/)
- [Drippay Contracts Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-contracts-api-phrasing-overlay/)
- [Drippay Coupons Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-coupons-api-phrasing-overlay/)
- [Drippay Credit Notes Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-credit-notes-api-phrasing-overlay/)
- [Drippay Customer Portal Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-customer-portal-api-phrasing-overlay/)
- [Drippay Customers Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-customers-api-phrasing-overlay/)
- [Drippay Drift Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-drift-api-phrasing-overlay/)
- [Drippay Dunning Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-dunning-api-phrasing-overlay/)
- [Drippay Entitlements Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-entitlements-api-phrasing-overlay/)
- [Drippay Events Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-events-api-phrasing-overlay/)
- [Drippay Integrations Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-integrations-api-phrasing-overlay/)
- [Drippay Internal Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-internal-api-phrasing-overlay/)
- [Drippay Invoices Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-invoices-api-phrasing-overlay/)
- [Drippay Openapi Overlay](https://apis.io/overlays/drippay/drippay-openapi-overlay/)
- [Drippay Pricing Plans Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-pricing-plans-api-phrasing-overlay/)
- [Drippay Product Categories Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-product-categories-api-phrasing-overlay/)
- [Drippay Runs Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-runs-api-phrasing-overlay/)
- [Drippay Subscriptions Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-subscriptions-api-phrasing-overlay/)
- [Drippay Tax Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-tax-api-phrasing-overlay/)
- [Drippay Usage Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-usage-api-phrasing-overlay/)
- [Drippay Webhooks Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-webhooks-api-phrasing-overlay/)
- [Drippay Workflows Api Phrasing Overlay](https://apis.io/overlays/drippay/drippay-workflows-api-phrasing-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Drippay Authentication](https://apis.io/security/drippay/drippay-authentication/)
- [Drippay Domain Security](https://apis.io/security/drippay/drippay-domain-security/)
- [Drippay Trust Center](https://apis.io/security/drippay/drippay-trust-center/)
- [Drippay Vulnerability Disclosure](https://apis.io/security/drippay/drippay-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Drippay Scopes](https://apis.io/scopes/drippay/drippay-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Drippay Plans Pricing](https://apis.io/plans/drippay/drippay-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Drippay Rate Limits](https://apis.io/rate-limits/drippay/drippay-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.dreach.ai/)
- [Documentation](https://docs.usedrip.ai/)
- [Getting started](https://docs.usedrip.ai/quickstart)
- [API reference](https://docs.usedrip.ai/api-reference)
- [Pricing](https://dreach.ai/pricing)
- [Sign up](https://dreach.ai/register)
- [Support](https://dreach.ai/contact)
- [Blog](https://dreach.ai/guides)
- [Security](https://dreach.ai/security)
- [Compliance](https://dreach.ai/security)
- [Terms of service](https://dreach.ai/terms)
- [Privacy policy](https://dreach.ai/privacy)
- [GitHub](https://github.com/DripYCx26)
- [Status](https://status.usedrip.ai/)

## API Evangelist rating

**Kin Score 72.3** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 56.4 |
| Contract governance | 18.2 |
| Operational transparency | 52.6 |
| Developer ergonomics | 86.9 |
| Access clarity | 92.1 |

**Agent readiness 64.5** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | verified |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | yes |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | distinct |

**Regulatory alignment 41.1** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/drippay/](https://apis.io/providers/drippay/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Drippay: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/drippay/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
