# Neutrino API (neutrino-api)

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

**APIs.json:** [https://neutrino-api.apievangelist.com/apis.yml](https://neutrino-api.apievangelist.com/apis.yml)

## Tags

- Data Validation
- Data Tools
- Telephony
- Communications
- SMS
- Voice
- Geolocation
- IP Intelligence
- Security
- Networking
- Anti-fraud
- E-commerce
- Payments
- Imaging
- Rendering
- Currency
- FX

## Timestamps

- **Created:** 2026-07-29
- **Modified:** 2026-08-09

## APIs

### Neutrino API Data Tools API

APIs for processing, cleaning and validating data

- **Human URL:** [https://www.neutrinoapi.com/api/](https://www.neutrinoapi.com/api/)
- **Base URL:** `https://neutrinoapi.net/`

#### Tags

- Data Tools

#### Properties

- [OpenAPI](openapi/neutrino-api-data-tools-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/neutrino-api-data-tools-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neutrino-api-data-tools-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Open A P I  Source](https://www.neutrinoapi.com/api/openapi-3.1.json)
- [Swagger](openapi/_original/neutrino-api-swagger-2.0.json)
- [Postman](postman/neutrino-api-postman-collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Insomnia](https://www.neutrinoapi.com/api/insomnia.json)
- [R A M L](https://www.neutrinoapi.com/api/raml.yaml)
- [W A D L](https://www.neutrinoapi.com/api/wadl.xml)
- [W S D L](https://www.neutrinoapi.com/api/wsdl.xml)
- [A P I Blueprint](https://www.neutrinoapi.com/api/apiblueprint.md)
- [Documentation](https://www.neutrinoapi.com/api/)
- [API Reference](https://www.neutrinoapi.com/api/index/)

### Neutrino API E Commerce API

APIs for E-commerce tasks

- **Human URL:** [https://www.neutrinoapi.com/api/](https://www.neutrinoapi.com/api/)
- **Base URL:** `https://neutrinoapi.net/`

#### Tags

- E-commerce

#### Properties

- [OpenAPI](openapi/neutrino-api-e-commerce-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/neutrino-api-e-commerce-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neutrino-api-e-commerce-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Open A P I  Source](https://www.neutrinoapi.com/api/openapi-3.1.json)
- [Swagger](openapi/_original/neutrino-api-swagger-2.0.json)
- [Postman](postman/neutrino-api-postman-collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Insomnia](https://www.neutrinoapi.com/api/insomnia.json)
- [R A M L](https://www.neutrinoapi.com/api/raml.yaml)
- [W A D L](https://www.neutrinoapi.com/api/wadl.xml)
- [W S D L](https://www.neutrinoapi.com/api/wsdl.xml)
- [A P I Blueprint](https://www.neutrinoapi.com/api/apiblueprint.md)
- [Documentation](https://www.neutrinoapi.com/api/)
- [API Reference](https://www.neutrinoapi.com/api/index/)

### Neutrino API Geolocation API

APIs for geolocation tasks

- **Human URL:** [https://www.neutrinoapi.com/api/](https://www.neutrinoapi.com/api/)
- **Base URL:** `https://neutrinoapi.net/`

#### Tags

- Geolocation

#### Properties

- [OpenAPI](openapi/neutrino-api-geolocation-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/neutrino-api-geolocation-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neutrino-api-geolocation-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Open A P I  Source](https://www.neutrinoapi.com/api/openapi-3.1.json)
- [Swagger](openapi/_original/neutrino-api-swagger-2.0.json)
- [Postman](postman/neutrino-api-postman-collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Insomnia](https://www.neutrinoapi.com/api/insomnia.json)
- [R A M L](https://www.neutrinoapi.com/api/raml.yaml)
- [W A D L](https://www.neutrinoapi.com/api/wadl.xml)
- [W S D L](https://www.neutrinoapi.com/api/wsdl.xml)
- [A P I Blueprint](https://www.neutrinoapi.com/api/apiblueprint.md)
- [Documentation](https://www.neutrinoapi.com/api/)
- [API Reference](https://www.neutrinoapi.com/api/index/)

### Neutrino API Imaging API

APIs for imaging and rendering

- **Human URL:** [https://www.neutrinoapi.com/api/](https://www.neutrinoapi.com/api/)
- **Base URL:** `https://neutrinoapi.net/`

#### Tags

- Imaging

#### Properties

- [OpenAPI](openapi/neutrino-api-imaging-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/neutrino-api-imaging-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neutrino-api-imaging-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Open A P I  Source](https://www.neutrinoapi.com/api/openapi-3.1.json)
- [Swagger](openapi/_original/neutrino-api-swagger-2.0.json)
- [Postman](postman/neutrino-api-postman-collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Insomnia](https://www.neutrinoapi.com/api/insomnia.json)
- [R A M L](https://www.neutrinoapi.com/api/raml.yaml)
- [W A D L](https://www.neutrinoapi.com/api/wadl.xml)
- [W S D L](https://www.neutrinoapi.com/api/wsdl.xml)
- [A P I Blueprint](https://www.neutrinoapi.com/api/apiblueprint.md)
- [Documentation](https://www.neutrinoapi.com/api/)
- [API Reference](https://www.neutrinoapi.com/api/index/)

### Neutrino API Security and Networking API

APIs for security and networking tasks

- **Human URL:** [https://www.neutrinoapi.com/api/](https://www.neutrinoapi.com/api/)
- **Base URL:** `https://neutrinoapi.net/`

#### Tags

- Security and Networking

#### Properties

- [OpenAPI](openapi/neutrino-api-security-and-networking-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/neutrino-api-security-and-networking-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neutrino-api-security-and-networking-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Open A P I  Source](https://www.neutrinoapi.com/api/openapi-3.1.json)
- [Swagger](openapi/_original/neutrino-api-swagger-2.0.json)
- [Postman](postman/neutrino-api-postman-collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Insomnia](https://www.neutrinoapi.com/api/insomnia.json)
- [R A M L](https://www.neutrinoapi.com/api/raml.yaml)
- [W A D L](https://www.neutrinoapi.com/api/wadl.xml)
- [W S D L](https://www.neutrinoapi.com/api/wsdl.xml)
- [A P I Blueprint](https://www.neutrinoapi.com/api/apiblueprint.md)
- [Documentation](https://www.neutrinoapi.com/api/)
- [API Reference](https://www.neutrinoapi.com/api/index/)

### Neutrino API Telephony API

APIs for live telephony

- **Human URL:** [https://www.neutrinoapi.com/api/](https://www.neutrinoapi.com/api/)
- **Base URL:** `https://neutrinoapi.net/`

#### Tags

- Telephony

#### Properties

- [OpenAPI](openapi/neutrino-api-telephony-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/neutrino-api-telephony-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neutrino-api-telephony-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Open A P I  Source](https://www.neutrinoapi.com/api/openapi-3.1.json)
- [Swagger](openapi/_original/neutrino-api-swagger-2.0.json)
- [Postman](postman/neutrino-api-postman-collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Insomnia](https://www.neutrinoapi.com/api/insomnia.json)
- [R A M L](https://www.neutrinoapi.com/api/raml.yaml)
- [W A D L](https://www.neutrinoapi.com/api/wadl.xml)
- [W S D L](https://www.neutrinoapi.com/api/wsdl.xml)
- [A P I Blueprint](https://www.neutrinoapi.com/api/apiblueprint.md)
- [Documentation](https://www.neutrinoapi.com/api/)
- [API Reference](https://www.neutrinoapi.com/api/index/)

### Neutrino API WWW API

APIs for website and HTML processing

- **Human URL:** [https://www.neutrinoapi.com/api/](https://www.neutrinoapi.com/api/)
- **Base URL:** `https://neutrinoapi.net/`

#### Tags

- WWW

#### Properties

- [OpenAPI](openapi/neutrino-api-www-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/neutrino-api-www-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/neutrino-api-www-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Open A P I  Source](https://www.neutrinoapi.com/api/openapi-3.1.json)
- [Swagger](openapi/_original/neutrino-api-swagger-2.0.json)
- [Postman](postman/neutrino-api-postman-collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Insomnia](https://www.neutrinoapi.com/api/insomnia.json)
- [R A M L](https://www.neutrinoapi.com/api/raml.yaml)
- [W A D L](https://www.neutrinoapi.com/api/wadl.xml)
- [W S D L](https://www.neutrinoapi.com/api/wsdl.xml)
- [A P I Blueprint](https://www.neutrinoapi.com/api/apiblueprint.md)
- [Documentation](https://www.neutrinoapi.com/api/)
- [API Reference](https://www.neutrinoapi.com/api/index/)

## Common Properties

- [Overlay](overlays/neutrino-api-openapi-3.1-overlay.yaml)
- [Domain Security](security/neutrino-api-domain-security.yml)
- [Authentication](authentication/neutrino-api-authentication.yml)
- [Packages](packages/neutrino-api-packages.yml)
- [S D Ks](packages/neutrino-api-packages.yml)
- [Well Known](well-known/neutrino-api-well-known.yml)
- [A P I Catalog](https://www.neutrinoapi.com/.well-known/api-catalog)
- [Conventions](conventions/neutrino-api-conventions.yml)
- [Error Catalog](errors/neutrino-api-problem-types.yml)
- [Conformance](conformance/neutrino-api-conformance.yml)
- [Compliance](https://www.neutrinoapi.com/data-processing-agreement/)
- [Data Model](data-model/neutrino-api-data-model.yml)
- [Lifecycle](lifecycle/neutrino-api-lifecycle.yml)
- [Deprecation](lifecycle/neutrino-api-lifecycle.yml)
- [Status Page](https://status.neutrinoapi.com/)
- [Changelog](changelog/neutrino-api-changelog.yml)
- [M C P Server](mcp/neutrino-api-mcp.yml)
- [L L Ms Txt](llms/neutrino-api-llms.txt)
- [Agent Skill](skills/_index.yml)
- [JSON Schema](json-schema/neutrino-api-ip-info-response.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/neutrino-api-ip-blocklist-response.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/neutrino-api-email-verify-response.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/neutrino-api-phone-validate-response.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/neutrino-api-bin-lookup-response.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/neutrino-api-error.json) — [JSON Schema](https://json-schema.org/specification)
- [Website](https://www.neutrinoapi.com/)
- [Developer Portal](https://www.neutrinoapi.com/api/)
- [Getting Started](https://www.neutrinoapi.com/api/api-basics/)
- [Code Samples](https://www.neutrinoapi.com/api/api-examples/)
- [Error Codes](https://www.neutrinoapi.com/api/api-errors/)
- [Rate Limits](https://www.neutrinoapi.com/plans/)
- [Pricing](https://www.neutrinoapi.com/plans/)
- [Sign Up](https://www.neutrinoapi.com/signup/)
- [Login](https://www.neutrinoapi.com/account/login/)
- [Support](https://www.neutrinoapi.com/contact-us/)
- [GitHub Organization](https://github.com/NeutrinoAPI)
- [Postman Workspace](https://www.postman.com/neutrinoapi/neutrino-api/overview)
- [LinkedIn](https://nz.linkedin.com/company/neutrino-api)
- [Terms of Service](https://www.neutrinoapi.com/terms-and-conditions/)
- [Privacy Policy](https://www.neutrinoapi.com/privacy-policy/)
- [Data Processing Agreement](https://www.neutrinoapi.com/data-processing-agreement/)

## Maintainers

**FN:** Neutrino API
**Email:** tech@neutrinoapi.com
**URL:** https://github.com/NeutrinoAPI/
