# HelioFleet and HelioField at AGU26

A one-page site for AGU26 in San Francisco: three one-minute demos of
[HelioFleet](https://sr-dash.github.io/heliofleet/) and [HelioField](https://sr-dash.github.io/heliofield/),
with links that open each view, a QR code and a printable card.

Live at **https://sr-dash.github.io/agu2026/**. This repository is temporary and can be deleted after the meeting.

## Files

- `index.html`: the page (no build step; served as is by GitHub Pages).
- `media/`: the three demo clips (MP4, H.264) with their poster images, and `og.png`, the social preview.
- `qr.svg`, `qr.png`: QR code for `https://sr-dash.github.io/agu2026/?utm_source=qr`.
- `card.pdf`: a US Letter sheet of ten business cards with cut marks, one 3.5 × 2 in card, and a 4 × 3 in badge insert.
- `src/`: the sources of `card.pdf` and `og.png`.

## Rebuilding

```bash
CH="/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"
"$CH" --headless=new --no-pdf-header-footer --virtual-time-budget=5000 --print-to-pdf=card.pdf "file://$PWD/src/card.html"
"$CH" --headless=new --hide-scrollbars --window-size=1200,630 --virtual-time-budget=5000 --allow-file-access-from-files --screenshot=media/og.png "file://$PWD/src/og.html"
```

Links from the page carry `utm_source=agu2026` and the QR code `utm_source=qr`, so visits from AGU show up in analytics.
