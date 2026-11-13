# Kimberley Cleaning private L0 demo

## Scope

Local-only static concept. It is not published, customer-approved, an operational website or an outreach asset.

- Audience: commercial facilities and remote-area sites in the Kimberley.
- Primary action: `tel:+61891922581`; secondary action: the published business email.
- Verified content retained: locally owned statement, Broome address, 15+ years, broad availability, commercial/remote service, specialist cleaning methods.
- Not included: forms, submissions, quotes, booking, scheduling, pricing, staff claims beyond the source, CMS, tracking, analytics, payment, server logic, deploy configuration or third-party access.

## First-principles and red-team review

| Question | Result |
|---|---|
| Root goal | Show a clearer commercial and remote cleaning story in one static page. |
| Necessary conditions | A visitor immediately understands the audience, capability and direct contact route on desktop and 390px mobile. |
| Abuse risk | A concept could be mistaken for a live customer site or imply unverified availability, certification, reviews or quoted prices. |
| Blocking evidence | No deployment, no form endpoint, no tracking script, no third-party booking and no unsupported proof claims in the page. |
| Residual risk | Customer must verify copy, service scope, contact preference and generated-image suitability before any private sharing or publication. |

## Assets

All concept images were generated with the built-in image generation tool on 2026-08-16. Five distinct images are visible in the page, and each placement uses a distinct file. They are not customer originals and are not licensed customer-approved production assets.

| Asset | Placement | Alt text | Final-use status |
|---|---|---|---|
| `assets/hero-cleaning-remote-v1.png` | Hero and process visual | Professional cleaning team caring for a polished regional facility | Private concept only |
| `assets/community-entry-v1.png` | Service visual | Clean regional community facility entry | Private concept only |
| `assets/residential-cleaning-v1.png` | Residential service visual | Professional cleaner caring for a tiled home interior | Private concept only |
| `assets/commercial-cleaning-v1.png` | Commercial service visual | Professional cleaner preparing a commercial reception area | Private concept only |
| `assets/vehicle-pindan-v1.png` | Vehicle service visual | Work vehicle being cleaned of red pindan dust | Private concept only |
| `assets/vehicle-interior-detail-v1.png` | Vehicle service visual | Vehicle interior being professionally cleaned and detailed | Private concept only |

## Run locally

From this directory: `python3 -m http.server 4179 --bind 127.0.0.1` then open `http://127.0.0.1:4179/`.

## Verification

- Desktop browser: rendered with all generated images loaded.
- 390px browser: `scrollWidth` and `bodyWidth` remained within the layout width; no horizontal overflow observed.
- Reduced motion: CSS removes smooth scrolling and button transitions when requested.
