# Bright Bus Tours public-front-end mirror status

Captured on: 2026-08-14

Authority: user confirmed authority to copy the public front-end content and assets.

## Captured

- `index.html` — Bright Bus Tours - Home
- `bus-tours.html` — Bright Bus Tours - Tours
- `our-buses.html` — Bright Bus Tours - Our Buses
- `contact.html` — Bright Bus Tours - Contact
- `bright-stylesheet.css`
- 4 Open Sans font files and 27 image assets referenced by the captured pages.

The source uses static HTML/CSS. The only observed visual behaviour is an
`opacity 0.5s` CSS transition on links; no video or CSS/JS animation asset was
observed in the captured pages.

## Not captured / not locally reproducible

- `tours.html`: referenced by `index.html`, but navigation to the origin timed
  out during this capture run. It is therefore absent, rather than replaced
  with an error page.
- `images/bright-and-district-leisure-tours-favicon.ico`: referenced by the
  captured HTML but did not appear in the browser's available asset inventory.
- Google Analytics (`ssl.google-analytics.com/ga.js`) and CDN jQuery
  (`ajax.googleapis.com/.../jquery.min.js`) remain external URLs. They were not
  copied locally.
- Contact-page reCAPTCHA and its Google-hosted iframe/script remain external.
  A local offline copy cannot perform CAPTCHA validation or submit the original
  form safely.
- Server-side source code, form endpoint handling, database, booking/payment
  systems, login-protected content, and third-party pages are outside this
  public-front-end mirror.

## Verification status

- Asset download: 0 reported asset-transfer failures for the four captured
  pages.
- HTML, stylesheet, image, and font paths are retained in their source-relative
  locations.
- Status: PARTIAL — do not label as a full one-to-one offline copy until the
  missing `tours.html`, favicon, and explicitly external dependencies are
  resolved and the mirror is checked in a browser.
