# Decisions

## 2026-08-16 — Page weight

**Dropped the inline `MEENAKSHI` base64 blob.** It was 2,753,936 bytes — 96% of
`index.html` — defined, returned from the `__TNTM` bundle, and read by nothing. Being
inline in a render-blocking `<script>`, every visitor paid it before first paint.
`index.html` went 2.86MB → 110KB.

**Cutouts re-encoded to WebP; code points at `.webp`.** 152MB → 17MB across the 64
images. `full/` keeps native resolution (the gallery centre tower can render ~900px
tall CSS, 1800px at 2x, already above the 1448px source). `cut/` is capped at 1200px
wide — it only appears as the panel crown card, at most ~388px CSS, so 1200px still
covers 3x. Quality 82. The `.png` masters are kept on disk but nothing loads them.

**Preloader warms neighbours, not everything.** It used to request all 64 images at
boot. Now `_preloadAround(idx)` warms the centre and two towers either side, re-firing
on gallery movement; anything else loads on demand.

## 2026-08-16 — Dark mode removed

`toggleDark` and `darkLabel` were exposed by the view model but never referenced in the
markup, so there was no toggle and `state.dark` could never become true. Every
`th.dark ? A : B` was therefore unreachable and collapsed to its light branch — the
rendered page is unchanged. The `NEON` line palette existed only for the dark map and
went with it.

Watch out: the paper-noise data URI in `paperImageFor` concatenated a live
`(dark?"0.08":"0.16")` ternary *inside* what looks like a plain string. It reads as
data-URI text but is code, and missing it threw `ReferenceError: dark is not defined`
out of `renderVals()`, blanking the whole page.

## 2026-08-16 — Bells

**Three ghantas in rotation: `medium` (500Hz) → `deep` (380Hz) → `small` (880Hz).**
One strike per event, one shared counter, so the rotation carries across both the home
gallery and the story panel and no bell repeats twice running. Chosen by ear from a
comparison page built for the purpose; reference was a "soothing temple bell #ghanta"
recording.

**The old partials were a church bell.** The set included `1.183` — a minor third,
the interval that defines European bell tuning. That, more than anything, was why it
did not read as a temple. The new ratios are inharmonic and untempered.

**Soothing is a level-and-tone problem, not a tuning one.** The bell fires every 150px
of scrolling, and anything bright or loud grates on repeat. Two things do the work: a
shared output stage (high-shelf −7dB at 2.6kHz, low-pass at 4.2kHz, 0.72 trim) that
nothing bypasses, and a low `strikeGain` on the two ghantas so the clapper sings rather
than knocks. Partials are struck as detuned pairs, which puts the slow beating shimmer
in the tail that a single oscillator cannot produce.

**Opening a temple is silent.** The bell belongs to the reading — it rings as the story
is scrolled, not on arrival. An earlier `_ringPrayer()` peal on open was tried and cut.

## 2026-08-16 — Metadata

`<head>` had no title, lang, description, social tags or favicon; the site is linked
from the portfolio, so shared links rendered as bare URLs. Added all of them plus a
generated 1200×630 `og-image.png`. The favicon is an inline SVG of `GLYPH`, the same
gopuram path the map draws for its stations, so no icon file is needed.

## Open

- `Tamil Nadu Temple Metro.dc.html` is a byte-identical copy of `index.html` and is
  kept in sync by hand. If it is a tool export, editing `index.html` may be undone on
  the next regeneration.
- Tamil-first UI chrome (line names, buttons, station labels) — deferred.
