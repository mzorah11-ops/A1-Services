# A1 Services (Telford)

Single-page site for A1 Services: electrical, gas heating, plumbing, EICR and EPC. It is a clone of the layout of
`crox.framer.website` (grey/charcoal/orange, 4px frame lines, giant wordmark) re-themed for A1, with the logo's blue as a
second accent and the sections reordered trust-first.

Everything lives in `index.html` (CSS and JS inline) plus `images/`.

## Run it

```
node serve.mjs        # http://localhost:8086/
```

## Fill in the missing details

Edit the `SETTINGS` block at the top of the last `<script>`. Anything left empty shows as a dashed `[Add ...]` placeholder.

| Setting | Shows in |
| --- | --- |
| `email` | footer contact column |
| `hours` | footer contact column |
| `niceic`, `gasSafe` | footer bottom bar (registration numbers) |
| `phone`, `phoneText`, `address` | already filled from the Top Rated Electricians listing |

## Sources

- Logo: `brand_assets/A1 services logo.png` (white background cut out, trimmed, favicons made from it).
- Content: the Top Rated Electricians listing screenshot (5.0 from 10 Google reviews, 20+ years, NICEIC for electrical,
  Gas Safe for heating and plumbing, domestic and commercial, warranty on all jobs, services list, 3 FAQs, phone, address).
- Written by us from that listing, so please check them: the one-line descriptions under each service, the four
  "How a job works" steps, and the three FAQ answers (built from the listing's About text).
- No customer review text, email address, opening hours or registration numbers were available, so none are shown.

## Motion

Only `transform` and `opacity` are animated, except two small canvases (the wireframe house and the circuit band) and the
stroke-draw on the line art. The canvases only run while on screen and in a visible tab.

| Switch | Effect |
| --- | --- |
| `?fx=off` on the URL | turns every animation and canvas off, shows the final state |
| `?lite=1` on the URL | the lighter version weaker phones get automatically (fade instead of stroke-draw, 30fps canvases) |
| `prefers-reduced-motion` | honoured automatically: nothing moves, final state shown |

The canvases also tune themselves: if a device can't hold the frame rate they drop to 30fps, then 1x resolution, then a still frame.
