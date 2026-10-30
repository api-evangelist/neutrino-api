# Neutrino API

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

Neutrino API is a general-purpose API collection that solves common but recurring software-development problems: data validation, telephony, geolocation, security and networking, e-commerce and imaging. It is a single flat REST-style HTTP API of 28 published operations — one verb path each, no resources and no stored state — accepting GET or POST and authenticated with two headers, user-id and api-key. The same operation set is served from seven hostnames: a default multicloud anycast endpoint, AWS-only and GCP-only endpoints, a backup on a separate TLD, and EU, Australia and USA geofence endpoints that guarantee in-boundary processing. Machine-readable definitions are published in eight formats from one source (OpenAPI 3.1, Swagger 2.0, RAML, WADL, WSDL, API Blueprint, Postman and Insomnia) and advertised through an RFC 9727 /.well-known/api-catalog. Bootstrapped and customer-funded, based in Auckland, New Zealand, operating since 2013 and serving more than 800 million API requests a day.

**Areas:** Data Validation · Data Tools · Telephony · Communications · SMS · Voice · Geolocation · IP Intelligence · Security · Networking · Fraud Prevention · E-Commerce

## Neutrino API on APIs.io

Everything profiled for Neutrino API is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/neutrino-api/](https://apis.io/providers/neutrino-api/)** — or go straight to one of the APIs or properties below.

### APIs (7)

- [Neutrino API Data Tools API](https://apis.io/apis/neutrino-api/neutrino-api-data-tools-api/) — APIs for processing, cleaning and validating data
- [Neutrino API Geolocation API](https://apis.io/apis/neutrino-api/neutrino-api-geolocation-api/) — APIs for geolocation tasks
- [Neutrino API Imaging API](https://apis.io/apis/neutrino-api/neutrino-api-imaging-api/) — APIs for imaging and rendering
- [Neutrino API Security and Networking API](https://apis.io/apis/neutrino-api/neutrino-api-security-and-networking-api/) — APIs for security and networking tasks
- [Neutrino API Telephony API](https://apis.io/apis/neutrino-api/neutrino-api-telephony-api/) — APIs for live telephony
- [Neutrino API WWW API](https://apis.io/apis/neutrino-api/neutrino-api-www-api/) — APIs for website and HTML processing
- [Neutrino API Ecommerce API](https://apis.io/apis/neutrino-api/neutrino-api-ecommerce-api/) — APIs for E-commerce tasks

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [neutrino-api](https://apis.io/servers/neutrino-api/neutrino-api/)

#### JSON Schema (6)

The data models the API reads and writes.

- [BINLookupResponse](https://apis.io/schemas/neutrino-api/neutrino-api-bin-lookup-response/)
- [EmailVerifyResponse](https://apis.io/schemas/neutrino-api/neutrino-api-email-verify-response/)
- [APIError](https://apis.io/schemas/neutrino-api/neutrino-api-error/)
- [IPBlocklistResponse](https://apis.io/schemas/neutrino-api/neutrino-api-ip-blocklist-response/)
- [IPInfoResponse](https://apis.io/schemas/neutrino-api/neutrino-api-ip-info-response/)
- [PhoneValidateResponse](https://apis.io/schemas/neutrino-api/neutrino-api-phone-validate-response/)

#### Collections (7)

Postman and Open Collection request collections.

- [Neutrino Data Tools API](https://apis.io/collections/neutrino-api/open-neutrino-api-data-tools-api/)
- [Neutrino E Commerce API](https://apis.io/collections/neutrino-api/open-neutrino-api-e-commerce-api/)
- [Neutrino Geolocation API](https://apis.io/collections/neutrino-api/open-neutrino-api-geolocation-api/)
- [Neutrino Imaging API](https://apis.io/collections/neutrino-api/open-neutrino-api-imaging-api/)
- [Neutrino Security and Networking API](https://apis.io/collections/neutrino-api/open-neutrino-api-security-and-networking-api/)
- [Neutrino Telephony API](https://apis.io/collections/neutrino-api/open-neutrino-api-telephony-api/)
- [Neutrino WWW API](https://apis.io/collections/neutrino-api/open-neutrino-api-www-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Neutrino Api Openapi 3.1 Overlay](https://apis.io/overlays/neutrino-api/neutrino-api-openapi-3.1-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Neutrino Api Authentication](https://apis.io/security/neutrino-api/neutrino-api-authentication/)
- [Neutrino Api Domain Security](https://apis.io/security/neutrino-api/neutrino-api-domain-security/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.neutrinoapi.com/)
- [Getting started](https://www.neutrinoapi.com/api/api-basics/)
- [Pricing](https://www.neutrinoapi.com/plans/)
- [Sign up](https://www.neutrinoapi.com/signup/)
- [Support](https://www.neutrinoapi.com/contact-us/)
- [Blog](https://www.neutrinoapi.com/updates/)
- [Compliance](https://www.neutrinoapi.com/data-processing-agreement/)
- [Terms of service](https://www.neutrinoapi.com/terms-and-conditions/)
- [Privacy policy](https://www.neutrinoapi.com/privacy-policy/)
- [GitHub](https://github.com/NeutrinoAPI)
- [Status](https://status.neutrinoapi.com/)

## API Evangelist rating

**Kin Score 54.1** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 76.8 |
| Contract quality | 53.9 |
| Contract governance | 18.2 |
| Operational transparency | 42.1 |
| Developer ergonomics | 70.8 |
| Access clarity | 52.6 |

**Agent readiness 33.2** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
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
| Operation Distinctiveness | distinct |

**Regulatory alignment 29.2** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/neutrino-api/](https://apis.io/providers/neutrino-api/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Neutrino API: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/neutrino-api/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
