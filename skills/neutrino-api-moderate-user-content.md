---
generated: '2026-08-09'
method: generated
name: Moderate and sanitize user-submitted content
description: Strip profanity from user text and sanitize untrusted HTML before you store or render it.
api: openapi/neutrino-api-openapi-3.1.json
operations: [BadWordFilter, HTMLClean, URLInfo]
source: >-
  operationIds, parameters and response field names verified verbatim in
  openapi/neutrino-api-openapi-3.1.json; catalog modes and file-upload support
  from https://www.neutrinoapi.com/updates/.
---

# Moderate and sanitize user-submitted content

Two different jobs that both sit on the write path of any user-generated-content feature: what the text *says*
(`BadWordFilter`) and what the markup *does* (`HTMLClean`).

## Auth
`user-id` + `api-key` headers. See `authentication/neutrino-api-authentication.yml`.

## Steps

1. **Filter profanity** — `BadWordFilter` (`POST /bad-word-filter`) with `content`. Options:
   - `catalog` — `strict` (built for educational and children's content) or `obscene` (only the severe terms,
     for adult audiences). Pick deliberately; this is the single most consequential parameter.
   - `censor-character` — the replacement character used in `censored-content`.
   Read `is-bad`, `bad-words-total`, `bad-words-list[]` and `censored-content`. Store the original and display
   the censored version, or reject on `bad-words-total` above your threshold.
   If `content` is HTML, the endpoint extracts the plain text automatically before matching.
2. **Sanitize the markup** — `HTMLClean` (`POST /html-clean`) with `content` and a required `output-type`
   selecting how aggressive the clean is (plain text through to safe HTML). This is what makes untrusted HTML
   safe to render; do not hand-roll it and do not skip it because step 1 passed.
3. **(Optional) Vet any link the user submitted** — `URLInfo` (`GET /url-info`) with `url` and
   `fetch-content=true`. Read `valid`, `real`, `http-ok`, `http-status`, `http-redirect`, `title`,
   `content-type`, `content-size`, `server-country`, `language-code`, `is-timeout`, `is-error`. Set an explicit
   `timeout` and `retry`. Pair with `DomainLookup` or `HostReputation` when the link is going to be shown to
   other users.

## Uploads
`BadWordFilter` and `HTMLClean` both accept direct binary uploads via `multipart/form-data` (max 25MB for
uploads, 5MB for data) — useful for moderating a file rather than an inline string.

## Doing this in bulk
`BadWordFilter` and `HTMLClean` are batch-enabled through `https://neutrinoapi.net/multi`, up to 2500 items
per call. Attach your own `id` to each element to correlate results.
See `conventions/neutrino-api-conventions.yml`.

## Errors
`1` missing/invalid parameter, `2`/`16`/`31` quota, `44` request too large (5MB data / 25MB upload),
`43` (HTTP 403) bad credentials. See `errors/neutrino-api-problem-types.yml`.

## Notes
- `html-extract-tags` (HTML Extract) is a **legacy** endpoint and is not in the OpenAPI. Use `HTMLClean` or
  `BrowserBot` instead. See `lifecycle/neutrino-api-lifecycle.yml`.
- Neutrino API states it does not store or log request data, which matters when the payload is user content.
