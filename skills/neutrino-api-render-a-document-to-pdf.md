---
generated: '2026-08-09'
method: generated
name: Render a document to PDF or image
description: Turn HTML into a PDF, JPG or PNG with Chromium, then resize, watermark or add a QR code to the output.
api: openapi/neutrino-api-openapi-3.1.json
operations: [HTMLRender, ImageResize, ImageWatermark, QRCode, BrowserBot]
source: >-
  operationIds and parameter names verified verbatim in
  openapi/neutrino-api-openapi-3.1.json; renderer engine, transparency, `exec`
  and C128 barcode support from https://www.neutrinoapi.com/updates/.
---

# Render a document to PDF or image

The imaging endpoints return **binary**, not JSON — the HTTP `Content-Type` tells you what you got. Errors
still come back as the usual JSON envelope, so branch on content type before parsing.

## Auth
`user-id` + `api-key` headers. See `authentication/neutrino-api-authentication.yml`.

## Steps

1. **Render** — `HTMLRender` (`POST /html-render`) with `content` (the HTML or a URL). Key options:
   `format` (PDF / JPG / PNG), `page-size`, `landscape`, `title`, `margin` (plus per-side `margin-left`,
   `margin-right`, `margin-top`, `margin-bottom`), `zoom`, `grayscale`, `css` for an injected stylesheet,
   `bg-color` (transparent PNG is supported), and `exec` to run custom JavaScript against the page before the
   final render. Chromium-based, so HTML5, CSS3, SVG and JavaScript all work.
2. **Resize** — `ImageResize` (`POST /image-resize`) with `image-url`, `width`, `height`, `format`,
   `resize-mode` (including pad and crop modes for exact output dimensions) and `bg-color` for padding.
   `image-url` accepts a base64 data URI as well as an http(s) URL, or upload the bytes as
   `multipart/form-data`.
3. **Watermark** — `ImageWatermark` (`POST /image-watermark`) with `image-url` and `watermark-url`, plus
   `opacity`, `position`, `width`, `height`, `resize-mode`, `format`, `bg-color`.
4. **Add a code** — `QRCode` (`POST /qr-code`) with `content`, and `width`, `height`, `fg-color`, `bg-color`.
   Set `code-format` to generate a C128 barcode instead of a QR code.

## When the page needs driving, not just rendering
`BrowserBot` (`POST /browser-bot`) with `url` loads the page in a real browser and can wait (`delay`,
`timeout`), target elements with a CSS `selector`, run JavaScript via `exec`, spoof a `user-agent` and
`ignore-certificate-errors`. It returns JSON — `elements[]`, `exec-results[]`, `url-components`, `url-valid`,
`title` — rather than a rendered file. Use it to extract content or click through a flow; use `HTMLRender`
when you want the picture.

## Errors
`17` rendering failed / could not generate the output file, `3` invalid URL, `44` request too large (5MB data,
25MB upload), `2`/`16`/`31` quota, `43` (HTTP 403) bad credentials.
See `errors/neutrino-api-problem-types.yml`.

## Notes
- Imaging endpoints have the tightest quotas on every plan (roughly 100 / 1K / 10K per day by tier) — budget
  accordingly. See `conventions/neutrino-api-conventions.yml`.
- None of the imaging endpoints are batch-enabled; `/multi` will return `api-error: 21`.
- `html5-render` (HTML5 Render) is the **legacy** WebKit renderer and is not in the OpenAPI. Use `HTMLRender`.
  See `lifecycle/neutrino-api-lifecycle.yml`.
