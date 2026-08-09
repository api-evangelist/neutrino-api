---
generated: '2026-08-09'
method: generated
name: Check a card BIN at checkout
description: Identify the issuer, brand and type behind a card's first digits, cross-check it against the shopper's IP, and price the order in the issuer's currency.
api: openapi/neutrino-api-openapi-3.1.json
operations: [BINLookup, Convert, BINListDownload]
source: >-
  operationIds, parameters and response field names verified verbatim in
  openapi/neutrino-api-openapi-3.1.json; 8-digit BIN guidance and historical FX
  from https://www.neutrinoapi.com/updates/.
---

# Check a card BIN at checkout

`BINLookup` resolves the Bank Identification Number — the leading digits of a card — into the issuer, brand,
type and country, and will simultaneously screen the shopper's IP against that issuer's country. It never sees
a full PAN and is not a payment API: it does not authorize, capture or decline anything.

## Auth
`user-id` + `api-key` headers. See `authentication/neutrino-api-authentication.yml`.

## Steps

1. **Look up the BIN** — `BINLookup` (`GET /bin-lookup`) with `bin-number`. Pass the shopper's IP as
   `customer-ip` in the same call to get the cross-check for free. Read:
   - Card facts: `valid`, `card-brand`, `card-type`, `card-category`, `is-commercial`, `is-prepaid`,
     `is-reloadable`
   - Issuer facts: `issuer`, `issuer-website`, `issuer-phone`, `country`, `country-code`, `currency-code`
   - IP cross-check: `ip-matches-bin`, `ip-country`, `ip-city`, `ip-region`, `ip-blocklisted`, `ip-blocklists`
2. **Decide.** `ip-matches-bin=false` plus `ip-blocklisted=true` is the high-risk combination. `is-prepaid=true`
   matters for subscriptions and for chargeback exposure; `is-commercial=true` routes a B2B checkout differently.
3. **Price it in the issuer's currency** — `Convert` (`GET /convert`) with `from-value`, `from-type` (your
   settlement currency) and `to-type` set to the `currency-code` returned in step 1. Read `result`,
   `result-float`, `to-name` and `to-symbol` for display. Pass `historical-date` to reconcile an older order at
   the rate that applied on that day.

## Bulk / offline use
`BINLookup` is batch-enabled via `https://neutrinoapi.net/multi` (max 2500 per call). If you need the data
resident in your own systems, `BINListDownload` (`GET /bin-list-download`) returns the whole BIN database as
CSV; use `include-all=true` for every field and `output-encoding=gzip` on the transfer.

## Errors
`1` missing/invalid parameter, `2` daily quota exhausted, `10` endpoint not enabled on your account,
`16` free-plan limit, `43` (HTTP 403) bad credentials. See `errors/neutrino-api-problem-types.yml`.

## Notes
- Use **8-digit** BINs. The payments industry moved off 6-digit BINs; Neutrino API accepts 6, 8, 10 and 12
  digits, and issuer accuracy is materially better at 8+.
- Send only the BIN, never the full card number — this endpoint does not need it and you do not want it in
  a third-party request.
- Neutrino API is not PCI-certified itself; it states cardholder data for its own billing is handled by
  third-party PCI-certified gateways. See `conformance/neutrino-api-conformance.yml`.
