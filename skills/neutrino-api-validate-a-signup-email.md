---
generated: '2026-08-09'
method: generated
name: Validate a signup email address
description: Two-stage email checking — a cheap syntax/domain parse first, then an SMTP-level mailbox verification, with domain reputation for the ones that matter.
api: openapi/neutrino-api-openapi-3.1.json
operations: [EmailValidate, EmailVerify, DomainLookup]
source: >-
  operationIds, parameters and response field names verified verbatim in
  openapi/neutrino-api-openapi-3.1.json; quota tiers from
  https://www.neutrinoapi.com/plans/.
---

# Validate a signup email address

Neutrino API splits email checking into two endpoints on purpose. `EmailValidate` is a parse; `EmailVerify`
actually talks SMTP to the receiving server. They have very different costs — on the same plan tier you get
roughly twenty times more `EmailValidate` calls than `EmailVerify` calls. Run them in that order.

## Auth
`user-id` + `api-key` headers. See `authentication/neutrino-api-authentication.yml`.

## Steps

1. **Parse and clean** — `EmailValidate` (`GET /email-validate`) with `email`, and `fix-typos=true` to
   auto-correct common domain typos. Read:
   - `valid`, `syntax-error`, `domain-error`, `domain-status` — is it even well-formed and is the domain usable
   - `typos-fixed` and `email` — the corrected address to store
   - `is-disposable` — throwaway provider; usually a block or a step-up
   - `is-freemail` / `is-personal` / `provider` — consumer vs. business signal for B2B signup flows
   Stop here for anything that fails. Most bad addresses die at this step for a fraction of the quota.
2. **Verify the mailbox exists** — `EmailVerify` (`GET /email-verify`) with `email` (and `fix-typos`). This
   opens an SMTP conversation with the receiving mail server. Read `verified`, `smtp-status`, `smtp-response`,
   `is-catch-all`, `is-deferred`, `mx-ip`. Note the semantics: `is-catch-all=true` means the domain accepts
   everything, so `verified` cannot distinguish a real mailbox — treat it as unknown, not as valid.
   `is-deferred=true` means greylisting; retry later rather than rejecting the user.
3. **(Optional) Judge the domain** — `DomainLookup` (`GET /domain-lookup`) with `host` set to the domain, and
   `live=true` for a realtime rather than cached answer. Read `is-malicious`, `blocklists[]`, `sensors[]`,
   `age`, `registered-date`, `mail-status`, `registrar-name`, `rank`. A domain registered last week with no
   mail configuration is a strong fraud signal even when the mailbox verifies.

## Doing this in bulk
`EmailValidate`, `EmailVerify` and `GeocodeAddress` are batch-enabled. POST JSON to
`https://neutrinoapi.net/multi` with a `data` array (max 2500) of `{"endpoint": "email-validate", "email": ...,
"id": "<your key>"}` objects — unknown fields like `id` come back on the matching response.
See `conventions/neutrino-api-conventions.yml`.

## Errors
`1` missing/invalid parameter, `2` daily quota exhausted, `16` free-plan limit, `43` (HTTP 403) bad
credentials. See `errors/neutrino-api-problem-types.yml`.

## Notes
- Neutrino API states it never stores or logs the data you send. If the address is EU or AU personal data you
  must keep in-region, call `https://eu.neutrinoapi.net` or `https://aus.neutrinoapi.net` instead of the
  default host — the geofence guarantee is at the endpoint, not a request parameter.
- Field names are kebab-case unless you set `output-case`.
