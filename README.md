# DumDum Maths — screens

What the app actually renders, next to the drawing it was built to.

Public on purpose: these are the pictures used to review the build. They
contain **no personal data** — no child's name, no account, no address,
no analytics. Every screen here is a fixed example question chosen for
the test, not anyone's real session.

The app itself is at **[app.dumdummaths.com](https://app.dumdummaths.com)**.

---

## 01 — the Year 2 question screen

The Infant frame: DumDum bottom-left, the question in his speech bubble,
one card in the middle holding the apparatus, the answers along the
bottom, and the garden underneath so the child can see what they are
growing.

The question is the mockup's: **8 add 5**, eight counters already in the
ten frame and five loose underneath.

| the drawing | the build | the difference |
|---|---|---|
| ![mockup](01-question/mockup.png) | ![built](01-question/built.png) | ![diff](01-question/diff.png) |

**2,366 pixels of 786,432 differ — 0.30%.**

In the difference image, **yellow is antialiasing** and **red is a real
difference**. Everything red is a glyph edge: the drawing's text was
rasterised by one engine and the build's by the browser, so the letters
never land on identical pixels. No box, outline, colour or shadow is out
of place — those are checked separately, to the pixel, by measuring
every element's bounding box against the coordinates in the SVG.

Built with a Playwright `toHaveScreenshot` comparison at 1024×768,
threshold 0.03, where the *expected* image is the mockup itself rather
than a snapshot of the app. A screenshot test that compares an app to a
picture of that same app always passes; this one can fail.

The picture is one of seven checks on this screen. The others read the
question's content, measure every box against the SVG's own coordinates,
read the computed colour and font of every part, hold the 64px touch
floor, and press each control to prove none of them is dead — because
the pixel budget has to be loose enough to survive Linux rasterising the
fonts differently, and a budget that loose would not notice one counter
turning the wrong colour.

### The same screen at other sizes

The frame is a fixed 1024×768 canvas scaled to fit, so nothing can
reflow into a layout nobody drew. Everything is present and centred at
every size — but the targets scale down with it, and below the design
size they fall under the 64px floor a child's finger needs.

| iPad portrait 768×1024 | phone 390×844 |
|---|---|
| ![portrait](01-question/sizes/tablet-portrait.png) | ![phone](01-question/sizes/phone.png) |

Smallest control: **67px** at 1024×768, **50px** in portrait, **26px** on
a phone. That is why this frame is on a design route and is not wired
into the app yet: it is a real blocker, written down, not a surprise
waiting for a child.
