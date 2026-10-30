# FireHydrant

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

FireHydrant is an incident management platform, now part of Freshworks, that covers the whole incident lifecycle — declaring and driving incidents from Slack or Microsoft Teams, Signals on-call scheduling and alerting, automated runbooks, a service catalog with environments and functionalities, its own hosted status pages, AI-enriched incident summaries, and retrospectives with analytics. Its REST API at api.firehydrant.io/v1 is a 373-operation, 228-path surface covering incidents, alerts, teams, runbooks, changes, integrations, webhooks and SCIM 2.0 provisioning, authenticated with a single organization API key sent as a Bearer token. FireHydrant also ships an official MCP server, first-party TypeScript and Go SDKs, a Terraform provider, and the fhcli change-event CLI.

**Areas:** AIOps · Incident Management · On-Call · Alerting · Status Pages · Runbooks · Site Reliability Engineering · Observability · Retrospectives · DevOps

## FireHydrant on APIs.io

Everything profiled for FireHydrant is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/firehydrant/](https://apis.io/providers/firehydrant/)** — or go straight to one of the APIs or properties below.

### APIs (28)

- [FireHydrant Audits API](https://apis.io/apis/firehydrant/firehydrant-audits-api/) — The Audits API from FireHydrant — 1 operation(s) for audits.
- [FireHydrant Change Events API](https://apis.io/apis/firehydrant/firehydrant-change-events-api/) — The Change Events API from FireHydrant — 2 operation(s) for change events.
- [FireHydrant Changes API](https://apis.io/apis/firehydrant/firehydrant-changes-api/) — The Changes API from FireHydrant — 1 operation(s) for changes.
- [FireHydrant Conversations API](https://apis.io/apis/firehydrant/firehydrant-conversations-api/) — The Conversations API from FireHydrant — 1 operation(s) for conversations.
- [FireHydrant Environments API](https://apis.io/apis/firehydrant/firehydrant-environments-api/) — The Environments API from FireHydrant — 2 operation(s) for environments.
- [FireHydrant Functionalities API](https://apis.io/apis/firehydrant/firehydrant-functionalities-api/) — The Functionalities API from FireHydrant — 1 operation(s) for functionalities.
- [FireHydrant Incidents API](https://apis.io/apis/firehydrant/firehydrant-incidents-api/) — The Incidents API from FireHydrant — 5 operation(s) for incidents.
- [FireHydrant Ping API](https://apis.io/apis/firehydrant/firehydrant-ping-api/) — The Ping API from FireHydrant — 1 operation(s) for ping.
- [FireHydrant Priorities API](https://apis.io/apis/firehydrant/firehydrant-priorities-api/) — The Priorities API from FireHydrant — 1 operation(s) for priorities.
- [FireHydrant Runbooks API](https://apis.io/apis/firehydrant/firehydrant-runbooks-api/) — The Runbooks API from FireHydrant — 2 operation(s) for runbooks.
- [FireHydrant Scheduled Maintenances API](https://apis.io/apis/firehydrant/firehydrant-scheduled-maintenances-api/) — The Scheduled Maintenances API from FireHydrant — 1 operation(s) for scheduled maintenances.
- [FireHydrant Services API](https://apis.io/apis/firehydrant/firehydrant-services-api/) — The Services API from FireHydrant — 2 operation(s) for services.
- [FireHydrant Severities API](https://apis.io/apis/firehydrant/firehydrant-severities-api/) — The Severities API from FireHydrant — 1 operation(s) for severities.
- [FireHydrant Signals API](https://apis.io/apis/firehydrant/firehydrant-signals-api/) — The Signals API from FireHydrant — 1 operation(s) for signals.
- [FireHydrant Teams API](https://apis.io/apis/firehydrant/firehydrant-teams-api/) — The Teams API from FireHydrant — 2 operation(s) for teams.
- [FireHydrant Account Settings API](https://apis.io/apis/firehydrant/firehydrant-account-settings-api/) — Operations related to Account Settings
- [FireHydrant Alerts API](https://apis.io/apis/firehydrant/firehydrant-alerts-api/) — Operations related to Alerts
- [FireHydrant Communication API](https://apis.io/apis/firehydrant/firehydrant-communication-api/) — Operations related to Communication
- [FireHydrant Incident Settings API](https://apis.io/apis/firehydrant/firehydrant-incident-settings-api/) — Operations related to Incident Settings
- [FireHydrant Integrations API](https://apis.io/apis/firehydrant/firehydrant-integrations-api/) — Operations related to Integrations
- [FireHydrant Metrics API](https://apis.io/apis/firehydrant/firehydrant-metrics-api/) — The metrics API from FireHydrant — 1 operation(s) for metrics.
- [FireHydrant Metrics/Reporting API](https://apis.io/apis/firehydrant/firehydrant-metrics-reporting-api/) — Operations related to Metrics/Reporting
- [FireHydrant Retrospectives API](https://apis.io/apis/firehydrant/firehydrant-retrospectives-api/) — Operations related to Retrospectives
- [FireHydrant SCIM API](https://apis.io/apis/firehydrant/firehydrant-scim-api/) — Operations related to SCIM
- [FireHydrant Status Pages API](https://apis.io/apis/firehydrant/firehydrant-status-pages-api/) — Operations related to Status Pages
- [FireHydrant Tasks API](https://apis.io/apis/firehydrant/firehydrant-tasks-api/) — Operations related to Tasks
- [FireHydrant Users API](https://apis.io/apis/firehydrant/firehydrant-users-api/) — Operations related to Users
- [FireHydrant Webhooks API](https://apis.io/apis/firehydrant/firehydrant-webhooks-api/) — Operations related to Webhooks

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Firehydrant Webhooks](https://apis.io/asyncapis/firehydrant/firehydrant-webhooks/)

#### GraphQL (1)

GraphQL schemas.

- [Moved to /providers/firehydrant/](https://apis.io/graphqls/firehydrant/firehydrant-graphql/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [FireHydrant](https://apis.io/servers/firehydrant/firehydrant/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Firehydrant Agentic Access](https://apis.io/agentic-access/firehydrant/firehydrant-agentic-access/)

#### Collections (16)

Postman and Open Collection request collections.

- [FireHydrant REST API](https://apis.io/collections/firehydrant/open-firehydrant/)
- [FireHydrant REST Audits API](https://apis.io/collections/firehydrant/open-firehydrant-audits-api/)
- [FireHydrant REST Audits Change Events API](https://apis.io/collections/firehydrant/open-firehydrant-change-events-api/)
- [FireHydrant REST Audits Changes API](https://apis.io/collections/firehydrant/open-firehydrant-changes-api/)
- [FireHydrant REST Audits Conversations API](https://apis.io/collections/firehydrant/open-firehydrant-conversations-api/)
- [FireHydrant REST Audits Environments API](https://apis.io/collections/firehydrant/open-firehydrant-environments-api/)
- [FireHydrant REST Audits Functionalities API](https://apis.io/collections/firehydrant/open-firehydrant-functionalities-api/)
- [FireHydrant REST Audits Incidents API](https://apis.io/collections/firehydrant/open-firehydrant-incidents-api/)
- [FireHydrant REST Audits Ping API](https://apis.io/collections/firehydrant/open-firehydrant-ping-api/)
- [FireHydrant REST Audits Priorities API](https://apis.io/collections/firehydrant/open-firehydrant-priorities-api/)
- [FireHydrant REST Audits Runbooks API](https://apis.io/collections/firehydrant/open-firehydrant-runbooks-api/)
- [FireHydrant REST Audits Scheduled Maintenances API](https://apis.io/collections/firehydrant/open-firehydrant-scheduled-maintenances-api/)
- [FireHydrant REST Audits Services API](https://apis.io/collections/firehydrant/open-firehydrant-services-api/)
- [FireHydrant REST Audits Severities API](https://apis.io/collections/firehydrant/open-firehydrant-severities-api/)
- [FireHydrant REST Audits Signals API](https://apis.io/collections/firehydrant/open-firehydrant-signals-api/)
- [FireHydrant REST Audits Teams API](https://apis.io/collections/firehydrant/open-firehydrant-teams-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Firehydrant Api Overlay](https://apis.io/overlays/firehydrant/firehydrant-api-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Firehydrant Authentication](https://apis.io/security/firehydrant/firehydrant-authentication/)
- [Firehydrant Domain Security](https://apis.io/security/firehydrant/firehydrant-domain-security/)
- [Firehydrant Trust Center](https://apis.io/security/firehydrant/firehydrant-trust-center/)
- [Firehydrant Vulnerability Disclosure](https://apis.io/security/firehydrant/firehydrant-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Firehydrant Plans Pricing](https://apis.io/plans/firehydrant/firehydrant-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Firehydrant Rate Limits](https://apis.io/rate-limits/firehydrant/firehydrant-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Firehydrant Finops](https://apis.io/finops/firehydrant/firehydrant-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://firehydrant.com)
- [Documentation](https://docs.firehydrant.com)
- [Getting started](https://docs.firehydrant.com/docs/admin-quickstart)
- [API reference](https://docs.firehydrant.com/reference/firehydrant-api)
- [Pricing](https://firehydrant.com/pricing/)
- [Sign up](https://app.firehydrant.io/registrations/new/)
- [Support](https://docs.firehydrant.com/docs/contacting-support)
- [Changelog](https://firehydrant.com/changelog/)
- [Blog](https://firehydrant.com/rss.xml)
- [Security](https://firehydrant.com/security/)
- [Compliance](https://firehydrant.com/security/)
- [Terms of service](https://firehydrant.com/legal/ssa/)
- [Privacy policy](https://firehydrant.com/legal/privacy/)
- [GitHub](https://github.com/firehydrant)
- [Status](https://status.firehydrant.com/)

## API Evangelist rating

**Kin Score 64.9** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 71.7 |
| Contract quality | 59.0 |
| Contract governance | 4.5 |
| Operational transparency | 65.8 |
| Developer ergonomics | 51.8 |
| Access clarity | 92.1 |

**Agent readiness 35.1** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | mostly |

**Regulatory alignment 35.3** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/firehydrant/](https://apis.io/providers/firehydrant/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for FireHydrant: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/firehydrant/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
