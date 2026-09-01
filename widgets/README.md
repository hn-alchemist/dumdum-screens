# The four apparatus, measured against the contract

Every image here is a **real engine question**, rendered inside the
Infant frame at the two sizes that matter — a tablet in landscape
(1024×768) and the short one a browser's chrome leaves you (1024×600) —
at each of the three CPA stages.

Produced by `npm run widget-gate`, which checks each render against
[the widget contract](https://github.com/hn-alchemist/dumdummaths/blob/main/docs/WIDGET-CONTRACT.md):
it fills its box and nothing is clipped, every target is at least 64px
with 16px between them, colour comes from tokens, tapping works before
dragging, it registers on touch-down, the apparatus shows numerals
rather than sentences, and nothing is red or a cross.

| apparatus | 18 renders |
|---|---|
| **tenframe** | passes every clause |
| **numberpad** (counters) | passes every clause |
| choice | 3 misses |
| shapes | 7 misses |

`choice` and `shapes` were run unmodified and are listed, not fixed.

## What these pictures caught

The ten frame and the counters both used to be **scaled down to fit the
card** — the ten frame to 0.898 — because they claimed a box 30px
larger than the room they were given. A 64px target is 56.5px of glass
at that scale, so the touch floor was being lost silently to a layout
that never fitted.

Before that could even be seen, the gallery these are rendered from was
loading none of the widgets' own stylesheets, so what earlier
measurements reported on was unstyled markup.
