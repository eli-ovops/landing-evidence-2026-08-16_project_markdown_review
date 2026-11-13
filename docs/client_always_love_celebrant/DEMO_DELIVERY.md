# Always Love Celebrant Services · L0 Demo Delivery

## Status

`待 PMO / 用户验收`。本地高级静态单页 Demo 已实现并完成构建与浏览器验证；未发布、未部署、未改动原站。

## Design outcome

- Direction: botanical cinematic storytelling with a modern wedding editorial register.
- Structure: full-bleed hero, asymmetric ceremony composition, Victoria portrait split, Mudgee place collage, horizontal real-story gallery, social proof and final contact scene.
- Palette: cool pearl, eucalyptus-charcoal and one dusty-rose action accent.
- Motion: native CSS, pointer parallax and IntersectionObserver reveals; non-essential motion is disabled for reduced-motion users.

## Asset result

- Candidate set: 25 non-duplicate core photos from the current public site.
- Used: 20 photos, exactly 80%, plus 2 public logo variants.
- All 20 retained photos are referenced by the built page.
- Copyright and depicted-person permissions remain `待客户确认`; this blocks any public preview or production release.
- Detailed register: `demo/docs/素材分配与版权登记表.md`.

## Static-only boundary

- Included: semantic single page, responsive navigation, page anchors, `mailto:`, `tel:`, light client-side motion.
- Excluded: CMS, database, login, form handler, booking, payment, availability calendar, dynamic pricing and year-specific booking claims.
- Contact decision can be completed from the page before any external action.

## Implementation choice

The demo uses Vite Vanilla and native browser APIs. This was selected after reviewing the official repositories for [Vite](https://github.com/vitejs/vite), [Astro](https://github.com/withastro/astro), [Eleventy](https://github.com/11ty/eleventy) and [GSAP](https://github.com/greensock/GSAP). Astro and Eleventy add unnecessary content-framework weight for this single static page; GSAP was not needed for the restrained motion model.

Pinned toolchain:

- Node: v22.16.0 observed locally
- pnpm: 10.34.5
- Vite: 8.0.16
- Playwright: 1.62.1, using the installed Chrome channel for QA

## Evidence

- `corepack pnpm@10.34.5 check`: passed, 20/20 photos referenced, no form, reduced-motion handling present.
- `corepack pnpm@10.34.5 build`: passed.
- Build output: HTML 13.77 kB, CSS 18.70 kB, JS 2.13 kB before image assets.
- Playwright desktop 1440×1000: HTTP 200, no console/page errors, no horizontal overflow, no broken images.
- Playwright mobile 390×844: same checks passed; mobile menu opened with correct expanded state.
- Machine-readable report: `demo/evidence/qa-report.json`.
- Visual evidence: `demo/evidence/desktop-1440.png`, `demo/evidence/mobile-390.png` and viewport captures.

## Correct local preview

For a direct local preview, open `demo/dist/index.html`. The production CSS and JavaScript are inlined and image paths are relative, so the built page works through `file://`. For development, run `corepack pnpm@10.34.5 preview --host 127.0.0.1` and open the printed `http://127.0.0.1:<port>/` address. Never open the source-level `demo/index.html` directly because it intentionally depends on Vite.

## Remaining gates

1. PMO / user visual acceptance of this L0 direction.
2. Customer confirmation of final copy, package naming and contact details.
3. Traceable copyright, logo and depicted-person approval for every retained asset.
4. Separate authorization and target contract before any preview or production publication.

## Visual iteration · 2026-08-15

- Replaced the two-row fixed-ratio gallery with a single-row editorial film strip.
- Each gallery card now follows its source image ratio and uses `object-fit: contain`, preventing secondary cropping of people.
- Mobile cards are limited to the visible viewport width so a complete photo is visible before swiping.
- Static checks, production build and Playwright QA at 1440px and 390px passed after the change.

## Message and private-pitch iteration · 2026-08-15

- Hero now identifies Victoria Smith-Webb, Mudgee and the stable ceremony range directly instead of relying on a generic wedding headline.
- The vague `Life’s Moments` label was replaced with the explicit `Funerals & Memorials` service category.
- Added a static three-step enquiry path: share the essentials, talk it through, shape the ceremony. It uses only `mailto:` and creates no availability or ongoing-content obligation.
- Rebuilt and reran Playwright QA at desktop 1440 and mobile 390: passed with no broken images, console errors or horizontal overflow.
- Created a separate 18-second HyperFrames private proposal composition under `pitch-video/`. It communicates understanding, respect for existing real stories and a clearer enquiry path; it is not embedded in the customer-facing site.
- HyperFrames `check` passed for lint, runtime, layout, motion and 43/43 WCAG text contrast checks. Three midpoint snapshots and an animation map were reviewed.
- ImageGen was attempted twice for an optional people-free botanical background; both calls returned service-side HTTP 500 errors. No generated asset was used and no CLI/API fallback was attempted.
- The HyperFrames Studio preview is local only. MP4 rendering remains behind user approval.
