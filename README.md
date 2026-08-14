# Tamil Nadu Temple Metro · தமிழ்நாடு கோயில் மெட்ரோ

An interactive, subway-style map of 32 great temples across Tamil Nadu, drawn as a
sacred transit network — paired with a gallery *home* where the temple towers float
over their own stories. Tap a station (or swipe through the towers) and a full-height
*kopuram* panel opens with the temple's telling cascading down the page in a vintage
sepia "waterfall," Tamil leading and English beneath, a temple bell ringing softly.

**Live map:** https://nishyajoylin-s.github.io/Tamil-Nadu-Temple-Metro/

---

## Why I made this

I built this as a personal project — a love letter to the temple towns of Tamil Nadu,
the places I grew up hearing about and visiting. I wanted the *kopurams* to feel the way
they do in person: rising above everything, with all the stories, names and legends
pooling at their feet. Framing them as a metro map came from the way pilgrims actually
move between these temples — line by line, junction by junction — so the network is both
a real geography and a way to wander.

## Inspiration

The floating-architecture-over-cascading-text look — and the idea of a soft bell as you
move — is inspired by **Marina Budarina** ([@marina_uiux](https://www.instagram.com/marina_uiux/))
and her *Chimes* concept. This project is my own interpretation of that idea, applied to
the gopurams and temple lore of Tamil Nadu.

---

## What you're looking at

There are two views, switchable in the top bar:

- **Temples** (home) — a gallery carousel. The centre gopuram stands large with its story
  cascading beneath; the previous and next towers peek in small on either side.
- **Map** — the full metro network. The temples are grouped into thematic **lines**:

| Line | Theme |
|------|-------|
| **Golden Trunk** | The spine linking the greatest temple cities |
| **Pancha Bhoota** | The five element temples (earth, water, fire, air, sky) |
| **Arupadai Veedu** | The six abodes of Lord Murugan |
| **Navagraha** | The nine planetary temples around Kumbakonam |
| **Chola Country** | The great living Chola temples |
| **Shakti / Devi** | Major goddess temples |

- **Stations** are temples. A small coloured dot is a single-line stop; a brown
  **double-ring** marks an *interchange* — a temple that sits on more than one line.
- **Interchange temples** (Madurai, Kumbakonam, Chidambaram…) are where the great
  pilgrimages cross.
- The faded shape behind the network is the real **Tamil Nadu state boundary**, so
  the schematic still sits roughly where the temples are on the ground.

## How to use it

**Temples (home)**
- **Two-finger swipe** (trackpad) or the **‹ ›** arrows to move between towers.
- **Tap a side tower** to step to it. A temple bell chimes as you switch.
- **Tap the centre tower** to open its full story panel.

**Map**
- **Drag** to pan, **scroll / pinch** to zoom, or use the **+ / − / fit** buttons.
- **Search** any temple, town, or deity in the top bar.
- **Tap a station** to open its tower panel — scroll down to let the story reveal,
  with a temple bell ringing softly as you go.
- **Line filter chips** highlight one line at a time.
- **Pilgrimage mode** auto-travels a line, stopping at each temple in turn.

## Files

| File | What it is |
|------|-----------|
| `index.html` | The whole application (self-contained). |
| `support.js` | The runtime that renders the map. |
| `temples-data.js` | All temple data + the embedded tower photographs. |
| `uploads/cut/` | Background-removed *kopuram* cutout images, one per temple. |

Everything runs client-side — no server, no build step. Opening `index.html`
directly in a browser works too.

## Publishing (GitHub Pages)

1. Push these files to the repo root.
2. **Settings → Pages → Source: Deploy from a branch → `main` / `(root)` → Save.**
3. The site goes live at the URL above within a minute or two.

## Credits

Temple photographs are cropped from public images of each shrine. Tamil temple names
and descriptions accompany every station. Inspired by Marina Budarina's *Chimes*.
Built as a design piece — a love letter to the temple towns of Tamil Nadu.
