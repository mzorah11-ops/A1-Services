# A1 Services (Telford)

Single-page site for A1 Services: electrical, gas heating, plumbing, EICR and EPC. It keeps the colours and fonts of the
`crox.framer.website` design (grey, white, charcoal and orange, with the logo's blue) but is deliberately calm: normal-sized
type, thin light lines, one idea per section, and very little motion.

Everything lives in `index.html` (CSS and JS inline) plus `images/`.

## Live site

https://mzorah11-ops.github.io/A1-Services/ (GitHub Pages, rebuilt from `main` about a minute after every push)

## Run it locally

```
node serve.mjs        # http://localhost:8086/
```

## Sections

Each section has a plain heading and one sentence saying what it is for. The sections alternate white and grey so each one
reads as its own block, and the nav marks which one you are in.

| Nav name | Section | Purpose |
| --- | --- | --- |
| (top) | Hero | What A1 is, and the two next steps: call, or see the services |
| About | About A1 Services | Who we are and what we are registered with, with four key facts |
| Services | Our services | The five services and what each includes |
| Who we help | Who we help | Homes and businesses |
| Why choose us | Why choose us | The Google rating, what customers say, and the three promises |
| How it works | How it works | The four steps from first call to finished job |
| FAQs | FAQs | Quick answers before calling |
| (bottom) | Get in touch | Phone, address, email and opening hours |

## Fill in the missing details

Edit the `SETTINGS` block at the top of the last `<script>`. Anything left empty shows as a dashed `[Add ...]` placeholder.

| Setting | Shows in |
| --- | --- |
| `email` | Get in touch |
| `hours` | Get in touch |
| `niceic`, `gasSafe` | the footer line (registration numbers) |
| `phone`, `phoneText`, `address` | already filled from the Top Rated Electricians listing |

## Sources

- Logo: `brand_assets/A1 services logo.png` (white background cut out, trimmed, favicons made from it).
- Content: the Top Rated Electricians listing screenshot (5.0 from 10 Google reviews, 20+ years, NICEIC for electrical,
  Gas Safe for heating and plumbing, domestic and commercial, warranty on all jobs, services list, 3 FAQs, phone, address).
- Written by us from that listing, so please check them: the one-line descriptions under each service, the four
  "How it works" steps, the three FAQ answers (built from the listing's About text), and the purpose sentence under each heading.
- No customer review text, email address, opening hours or registration numbers were available, so none are shown.

## Motion

Only two things move: each block fades in once as you scroll, and the outline house in the hero turns slowly (it only runs
while on screen and in a visible tab, and is capped at 30 frames a second). Nothing loops anywhere else.

| Switch | Effect |
| --- | --- |
| `?fx=off` on the URL | no fades and the house stays still |
| `prefers-reduced-motion` | honoured automatically: the same as `?fx=off` |
