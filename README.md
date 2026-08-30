# DumDum Maths — screens

What the app actually renders, next to the drawing it was built to.

Public on purpose: these are the pictures used to review the build. They
contain **no personal data** — no child's real name, no account, no
address, no analytics. Every screen here is a fixed example chosen for
the test.

The app itself is at **[app.dumdummaths.com](https://app.dumdummaths.com)**.

## How to read the difference images

**Yellow is antialiasing. Red is a real difference.** The comparison is
Playwright's `toHaveScreenshot` at 1024x768, threshold 0.03, where the
*expected* image is the mockup itself rather than a snapshot of the app —
a screenshot test that compares an app to a picture of that same app
always passes; these can fail.

The mockup PNGs are rendered by the same browser and the same font files
the app uses, so what is left is genuinely sub-pixel: a curve or a glyph
edge landing half a pixel differently.

| screen | difference | of 786,432 pixels |
|---|---|---|
| 01 — a question | **493** | 0.063% |
| 02 — one miss later | **1,133** | 0.144% |
| 03 — who's playing | **238** | 0.030% |
| 04 — finished for today | **119** | 0.015% |

---

## 01 — the Year 2 question screen

The Infant frame: DumDum bottom-left, the question in his speech bubble,
one card in the middle holding the apparatus, the answers along the
bottom, and the garden underneath so the child can see what they are
growing. **8 add 5**, eight counters in the ten frame and five loose.

| the drawing | the build | the difference |
|---|---|---|
| ![mockup](01-question/mockup.png) | ![built](01-question/built.png) | ![diff](01-question/diff.png) |

## 02 — the same question, one miss later

The card they pressed lights **sun, never red, and there is no cross**.
Two counters lift and dashed paths run into the two empty cells.

Nothing on this screen holds the number two: the engine decides that a
second miss shows the working, and the ten frame works out that the gap
to ten is 10 minus 8.

| the drawing | the build | the difference |
|---|---|---|
| ![mockup](02-wrong/mockup.png) | ![built](02-wrong/built.png) | ![diff](02-wrong/diff.png) |

## 03 — who's playing

One big card per child: a face to recognise before you can read the
name. The faces are art slots — a coloured disc until real avatars
exist.

| the drawing | the build | the difference |
|---|---|---|
| ![mockup](03-start/mockup.png) | ![built](03-start/built.png) | ![diff](03-start/diff.png) |

## 04 — finished for today

The garden fills the bottom of the screen, because it is the whole
reward: what grew is what they did. No score, no stars, no "7 out of
10". One way out, and it is a leaf.

| the drawing | the build | the difference |
|---|---|---|
| ![mockup](04-finished/mockup.png) | ![built](04-finished/built.png) | ![diff](04-finished/diff.png) |

---

## Held the wrong way up, or on a phone

A child screen is landscape. Rather than squeeze the drawing into a
shape nobody drew — which put every target at 50px in portrait and 26px
on a phone, against a 64px floor — the product shows a screen made for
the shape it is in.

The portrait one has **no words at all**: a Year 1 child may not read
yet, so DumDum turning inside an arrow is the whole message, and
"Turn me round!" is spoken.

| portrait on a tablet | on a phone |
|---|---|
| ![portrait](shapes/portrait.png) | ![phone](shapes/phone.png) |
