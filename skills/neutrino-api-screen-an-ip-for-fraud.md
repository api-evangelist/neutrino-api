---
generated: '2026-08-09'
method: generated
name: Screen an IP address for fraud and abuse
description: Score an inbound IP address — geolocation, hosting/VPN/proxy detection, blocklist membership and DNSBL reputation — before letting a request through.
api: openapi/neutrino-api-openapi-3.1.json
operations: [IPInfo, IPProbe, IPBlocklist, HostReputation]
source: >-
  operationIds, parameters and response field names verified verbatim in
  openapi/neutrino-api-openapi-3.1.json; batch behaviour from
  https://www.neutrinoapi.com/api/batch-processing/.
---

# Screen an IP address for fraud and abuse

Four endpoints answer four different questions about the same IP. Call only the ones your decision needs —
each has its own daily quota.

## Auth
`user-id` + `api-key` headers. See `authentication/neutrino-api-authentication.yml`.

## Steps

1. **Where is it?** — `IPInfo` (`GET /ip-info`) with `ip`. Optional `reverse-lookup=true` adds a PTR lookup
   (and latency). Read `valid`, `country-code`, `region-code`, `city`, `latitude`/`longitude`, `timezone`,
   `is-bogon`. Use for geo rules and currency/language defaults (`currency-code`, `language-code`).
2. **What kind of network is it?** — `IPProbe` (`GET /ip-probe`) with `ip`. This is the realtime network probe,
   not a geo lookup. Read `is-hosting`, `is-isp`, `is-vpn`, `is-proxy`, `vpn-domain`, `provider-type`,
   `asn`, `as-description`, `as-age`. A datacenter/hosting ASN on a consumer signup is the classic signal.
3. **Is it on a blocklist?** — `IPBlocklist` (`GET /ip-blocklist`) with `ip`, optionally `vpn-lookup=true`.
   Read `is-listed` first, then the specific booleans: `is-bot`, `is-exploit-bot`, `is-malware`, `is-spyware`,
   `is-spam-bot`, `is-proxy`, `is-tor`, `is-vpn`, `is-hijacked`, `is-dshield`. `list-count`, `blocklists[]`
   and `sensors[]` tell you how many and which sources matched, and `last-seen` how fresh the signal is.
4. **What do third-party DNSBLs say?** — `HostReputation` (`GET /host-reputation`) with `host` (an IP, a
   domain or a URL). Optional `list-rating` filters to higher-quality lists; `zones` pins specific DNSBL zones.
   Read `is-listed`, `list-count` and `lists[]`.

## Scoring guidance
Treat step 3 as a hard signal (blocklist membership is an assertion about that IP), step 2 as a contextual
signal (hosting/VPN is normal for some products and disqualifying for others), and step 4 as advisory —
DNSBLs vary in quality, which is exactly why `list-rating` and `zones` exist.

## Doing this in bulk
`IPInfo`, `IPProbe`, `IPBlocklist` are all batch-enabled. POST JSON to `https://neutrinoapi.net/multi` with a
`data` array of up to 2500 elements, each carrying `endpoint` plus that endpoint's parameters, and attach your
own `id` field to correlate the responses. Batch is unavailable on the Free plan (`api-error: 22`).
See `conventions/neutrino-api-conventions.yml`.

## Errors
`1` missing/invalid parameter, `2` daily quota exhausted, `16` free-plan limit, `31` a cap you set yourself,
`43` (HTTP 403) bad credentials. Branch on the numeric `api-error`.
See `errors/neutrino-api-problem-types.yml`.

## Notes
- Accepts IPv4, IPv6, CIDR notation, compressed IPv6, proxy chains, 6to4 and IPv4-mapped IPv6 (returned
  normalized in the `ip` field).
- No rate-limit response headers exist; you learn you are out of quota by receiving `api-error: 2`.
- For a whole-dataset copy rather than per-IP lookups, use `IPBlocklistDownload` (`GET /ip-blocklist-download`)
  with `checksum=true` first to see whether the data changed, and `output-encoding=gzip` to save bandwidth.
