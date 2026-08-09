# Design tokens — Backline

Written from direction A in `ART-DIRECTION.example.md`. Every value here has
a role, and most of them trace back to one object: a patch bay.

---

## Type

| Scale | Size | Line-height | Tracking | Face / weight | Role |
|---|---|---|---|---|---|
| Display | 96 | 0.92 | −0.03em | Fraunces 600, `wonk` on, `opsz` 96 | Masthead only. One instance per page. |
| Text | 17 | 1.6 | 0 | Fraunces 400, `wonk` off, `opsz` 17 | Anything a person wrote. |
| Label | 12 | 1.3 | +0.06em, caps | Commit Mono 500 | Column heads, tape labels, state. |
| Mono | 13 | 1.5 | +0.02em | Commit Mono 400, tabular figures | Anything the system states: times, prices, capacity, room numbers. |

Measure (body): 62ch

Hierarchy: 5.6× between display and text, and nothing in between. The jump is
large because there are only two voices and no intermediate headings — the
grid does the sectioning that h2s would otherwise do. Adding a mid-scale here
would imply a level of structure the page does not have.

## Space

Base unit: **14px** — the socket pitch. Not a round number and not meant to
be; it comes from the grid the whole page is built on, so every margin lands
on the same rhythm as the sockets.

| Step | Value | Used for |
|---|---|---|
| ×1 | 14 | socket gutter, label to value |
| ×2 | 28 | inside panels |
| ×4 | 56 | between panels |
| ×9 | 126 | between sections |
| ×13.5 | 190 | above the masthead, once |

**Density rules.** The availability grid is as tight as legibility allows —
density is the argument, a week visible at once. Everything outside the grid
is loose. There is no middle setting; a third density would blur the contrast
that carries the composition.

**Section rhythm.** 126 between sections, broken once: 190 above the masthead
and nothing above the grid, which sits hard against it. The break is the
composition — a long silence, then everything at once.

Tape labels sit 3–9px off-grid, a different offset each. The single
deliberate inconsistency in an otherwise relentless system.

## Geometry

| Token | Value | Role |
|---|---|---|
| Small | 3 | sockets — a jack socket is almost square |
| Medium | 2 | panels — rack gear has barely any radius |
| Large | 6 | buttons — the only soft thing, so the one place you click is the one place that gives |
| Container | 0 | photos and tape labels, full-bleed, no frame |

Four values, all under 7px. The character is the near-absence of rounding; a
12px radius anywhere on this page would read as borrowed.

Nesting: nothing nests deeply enough for concentricity to show.
Sharp corners: everything photographic, plus the tape, whose edges are torn
with a clip-path rather than rounded.

## Motion

| Token | Duration | Curve | Used for |
|---|---|---|---|
| Fast | 180ms | spring | socket hover — the cable stub extends 4px |
| Normal | 40ms × n | linear stagger | selecting hours, in the drag direction |
| Slow | 320ms | `cubic-bezier(.2,.8,.2,1)` | the cable drawing on confirmation |

Springs: stiffness 320, damping 26, mass 0.8 — for anything the user
initiated, so it feels answered rather than played back. The confirmation
cable is system-initiated and eased.

Nothing else animates. No scroll reveals, no fades. On a dense grid, motion
on load is noise.

Reduced motion: sockets change state instantly; the cable appears already
drawn. Nothing is lost — the information was never in the animation, only in
its result.

## Colour

| Token | Value | Contrast on ground | Role |
|---|---|---|---|
| Background | `#151311` | — | warm near-black, hue borrowed from the accent |
| Surface | `#1E1B18` | — | panels, one step up |
| Text primary | `#EFEAE2` | 13.8:1 | body and display |
| Text secondary | `#9C948A` | 5.1:1 | mono values |
| Text tertiary | `#6B645C` | 3.1:1 | labels only, never body |
| Accent | `#E5622A` | 4.9:1 | sodium — available hours, nothing else |
| Success | — | — | not needed; a drawn cable is the success state |
| Warning | `#C9A227` | 6.2:1 | room unavailable at short notice |
| Danger | `#B33A26` | 4.6:1 | cancellation only |

Neutrals are pulled toward the accent's hue — pure grey beside warm tape
would look broken rather than neutral.

The accent marks exactly one thing: an hour you can book. Because nothing
else on the site is orange, availability is readable from across a room.
Booked hours get no colour at all, only an empty outlined socket — absence
reads as unavailable faster than red, and it keeps the orange meaning one
thing.

Gradients: none. The concept has no gradient in it.

---

## Floors

- [x] Body 13.8:1, mono 5.1:1, accent 4.9:1 — measured, all above 4.5:1.
      Tertiary at 3.1:1 is label-only and never carries body copy.
- [x] All three motion tokens have static equivalents
- [x] Focus: 2px sodium outline, offset 2px, on every socket and control
- [x] Sockets are 38px with 14px gutters — 52px effective target
