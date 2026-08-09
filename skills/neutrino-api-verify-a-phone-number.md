---
generated: '2026-08-09'
method: generated
name: Verify a phone number with a one-time code
description: Validate a phone number, send a one-time security code by SMS or voice call, then check the code the user typed back.
api: openapi/neutrino-api-openapi-3.1.json
operations: [PhoneValidate, SMSVerify, PhoneVerify, VerifySecurityCode]
source: >-
  operationIds and parameter names verified verbatim in
  openapi/neutrino-api-openapi-3.1.json; cost and abuse-control behaviour from
  https://www.neutrinoapi.com/plans/ and https://www.neutrinoapi.com/api/api-errors/.
---

# Verify a phone number with a one-time code

Neutrino API issues the code for you and remembers it — you never generate, store or expire it yourself.

## Auth
Send `user-id` and `api-key` as HTTP headers (or one combined `API-Key: <user-id>:<api-key>` header).
See `authentication/neutrino-api-authentication.yml`.

## Cost and safety — read before you call
`SMSVerify`, `PhoneVerify` and `PhonePlayback` place real SMS and voice calls and bill on demand
(SMS from $0.0150, voice from $0.0200, destination-dependent). There is **no idempotency key** on this API.
A retried POST sends a second message. Guard every call:

- Set `limit` (max sends to this number) and `limit-ttl` (the window, in hours) on `SMSVerify` / `PhoneVerify`.
- Set `limit-by` on `VerifySecurityCode` for brute-force protection on the check side.
- Telephony must be enabled on the account or you get `api-error: 8`; exceeding the per-number limit gives
  `api-error: 14`. See `errors/neutrino-api-problem-types.yml`.

## Steps

1. **Pre-check the number for free** — `PhoneValidate` (`GET /phone-validate`) with `number`, optionally
   `country-code` for national-format input. Read `valid`, `is-mobile` and `type`. Stop here if the number is
   not valid or not mobile — this costs nothing and avoids a wasted paid send.
2. **Send the code** — `SMSVerify` (`POST /sms-verify`) with `number`. Useful options: `code-length`,
   `brand-name` (shown in the message), `language-code`, `limit`, `limit-ttl`. You may pass your own
   `security-code` if you want to own the value. Read `number-valid` and `sent` from the response.
   - For landlines or when SMS fails, use `PhoneVerify` (`POST /phone-verify`) instead — same parameters plus
     `playback-delay`. It calls the number and reads the code aloud.
3. **Check what the user typed** — `VerifySecurityCode` (`GET /verify-security-code`) with `security-code`
   set to the value the user entered, and `limit-by` set to throttle guessing. The response is a single
   boolean: `verified`.

## Optional enrichment
`HLRLookup` (`GET /hlr-lookup`) queries the live mobile network for the number's real status, current carrier
and portability before you spend anything on a send. It is billed at a fixed $0.0070 per valid lookup.

## Errors
Branch on the numeric `api-error`, not the HTTP status — almost everything is a 400.
`8` telephony not enabled, `11` too many simultaneous calls, `14` number is rate-limited, `15` call in progress,
`13`/`19` payment method declined, `43` (HTTP 403) bad credentials.
Full table: `errors/neutrino-api-problem-types.yml`.

## Notes
- Response field names are kebab-case by default; set `output-case=snake|camel` if your client needs it, and
  pin it — the field names change. See `conventions/neutrino-api-conventions.yml`.
- These endpoints are **not** batch-enabled; `/multi` does not accept them.
- Use a geofenced host (`https://eu.neutrinoapi.net`, `aus.`, `usa.`) if the phone number is personal data you
  must keep inside a jurisdiction.
