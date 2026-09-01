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

| apparatus | renders | misses |
|---|---|---|
| **tenframe** | 342, every skill-band | 3, all on the one skill that asks for 50 and 100 cells |
| **numberpad** (counters) | 636, every skill-band | 3 |
| choice | 60 | 5 |
| shapes | 54 | 3 |

`choice` and `shapes` were run unmodified and are listed, not fixed.

Two of the six misses on the rebuilt apparatus **do not close**. Fifty
64px cells is 3,200px of cell in a 673px-wide card. A Reception
question with three counters and an eleven-key pad wants 270px of a
263px card. Both are decisions about the drawing, not layout bugs.

## What these pictures caught

The ten frame and the counters were both **scaled down to fit the
card** — the ten frame to 0.898 — because they claimed a box 30px
larger than the room they were given. A 64px target is 56.5px of glass
at that scale, so the touch floor was being lost silently to a layout
that never fitted.

Before that could even be seen, the gallery these are rendered from was
loading **none of the widgets' own stylesheets**, so what earlier
measurements reported on was unstyled markup.

And the gate that found it was itself certifying on **one skill of the
nineteen** that use a ten frame, always at band 1 — so it had never
seen `ceiling: 20`, which thirteen Year 1 and Year 2 skills use. It
walks every skill and band now.

Every image is taken **before** the touch probe presses anything; the
first set showed pressed states, including a ten frame emptied by the
probe under a bubble saying seven were in it.
