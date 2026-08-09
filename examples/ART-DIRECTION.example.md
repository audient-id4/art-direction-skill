# Art direction — Backline

A booking service for band rehearsal rooms. Written as a worked example of
the artifact method: nothing here was chosen because it looked nice, and the
whole system falls out of one object.

---

## Artifact

**The patch bay** — the rack panel of quarter-inch jacks in every rehearsal
room, plus the gaffer-taped labels that always end up stuck under it.

What transfers: a strict repeating grid of identical sockets; hand-written
labels in a rigid frame; the tension between an engineered object and the
tape someone slapped on it at 2am. What does not transfer: metal textures,
knobs, or anything skeuomorphic. This is a booking site, not a plugin.

## 1. Concept

An engineered grid with human annotation on top — precise where the machine
speaks, hand-set where a person does.

## 2. Emotion

Recognition, then trust. A drummer should see it and think *these people have
been in a rehearsal room*. Not "premium", not "playful" — competent.

## 3. Recognition

The socket grid used as a room-availability display, and the two-voice
typography: everything factual in a tight mono, everything human in a wide
serif with real personality. Either one alone is unremarkable; together they
are the site.

## 4. Metaphor

- Availability grid = patch bay. Rooms are rows, hours are sockets. A booked
  hour is a filled socket, not a coloured rectangle.
- Room names = tape labels. Set slightly off-axis, on a warm neutral, always
  overlapping the panel edge by a few pixels.
- Booking confirmation = a patched connection. Two sockets, a cable between
  them, drawn in one stroke.

## 5. Typography

**Commit Mono** for anything the system states: times, prices, room numbers,
capacity. Mono because these are values a musician will scan in a column, and
tabular figures actually align. 13px/1.5, +0.02em.

**Fraunces** for anything a person says: room descriptions, the masthead,
empty states. Its optical-size axis is the reason it is here — at 96px the
display cut has the tight apertures the wide text cut lacks, so the masthead
reads as drawn rather than scaled. `opsz` follows size; `wonk` on for display,
off for body.

No neutral sans anywhere. The two voices are the identity, and a third face
would dissolve it.

Display 96px/0.92/−0.03em. Body serif 17px/1.6, measure 62ch. Mono as above.
Display-to-body ratio 5.6× — one large jump, no intermediate steps.

## 6. Geometry

Sockets: 3px. Almost square, because a jack socket is.
Panels: 2px. Rack gear has barely any radius and it matters.
Tape labels: 0. Torn edges are done with a clip-path, not a radius.
Buttons: 6px, the only genuinely soft thing on the page, so the one place you
click is the one place that gives.
Photos: 0, full-bleed, no frame.

Four values, all under 7px. The character comes from the near-absence of
rounding — a 12px radius anywhere on this page would look borrowed.

Nested rule: none needed, nothing nests deeply enough for concentricity to
show.

## 7. Spacing rhythm

Seeded from the socket: one unit = 14px, the socket pitch. Everything is a
multiple. The grid is relentless and that is the point — it is the machine
half of the concept.

The tape labels break it. They sit at arbitrary offsets, 3–9px off the grid,
different for each. That single inconsistency is what stops the page reading
as a spreadsheet.

Compression: the availability grid is dense, 14px gutters, no breathing room.
Expansion: 190px of nothing above the masthead. The contrast between those
two is the composition.

## 8. Colour

Ground: warm near-black `#151311`, hue borrowed from the accent. Not `#111`
— pure grey next to warm tape would look broken.

Signature: sodium orange `#E5622A`. One hue, from the streetlight outside
every rehearsal studio at load-out. It marks exactly one thing: an available
hour. Nothing else on the site is orange, so availability is legible at a
glance from across a room.

Tape: `#D8CDBA`, the only light surface.
Text: `#EFEAE2` on ground, 13.8:1. Mono values `#9C948A`, 5.1:1.
Booked hours: no colour at all — an empty outlined socket. Absence reads as
unavailable faster than red does, and it keeps the orange meaning one thing.

No gradient. The concept has no gradient in it.

## 9. Interaction language

Hovering a socket: the cable stub extends 4px, spring, 180ms. Physical — a
jack going in.

Selecting hours: sockets fill in sequence, 40ms apart, in the direction of
the drag. The stagger reproduces the feeling of patching a row by hand.

Confirmation: the cable draws between the two sockets, 320ms, eased. It is
the only motion over 200ms and the only one the system initiates.

Everything else: nothing. No scroll reveals, no fades. On a dense grid,
motion on load is noise.

Reduced motion: sockets change state instantly, the cable appears drawn.
Nothing is lost; the information was never in the animation.

## Signature detail

The cable. It is drawn as one continuous SVG stroke between the first and
last hour of a booking, it persists in the confirmation email as an inline
SVG, and it is how a multi-hour booking is *read* — length is duration. It
does navigational work, which is what keeps it from being a gimmick.

---

## Rejection log

| Obvious choice | Why rejected | Replaced with |
|---|---|---|
| Calendar grid with coloured availability blocks | Every booking product looks like this, and it wastes the one thing this domain owns visually | Patch-bay socket grid; same information, and it belongs to rehearsal rooms specifically |
| Hero photo of a band + headline + "Book now" | Puts a stock photo where the actual product should be, and pushes availability below the fold | Masthead left, live availability grid full-bleed right, bookable from the first screen |
| Inter for everything, serif for the logo only | Neutral sans is the default that erases the concept; a serif used only in a logo is decoration | Two working voices — mono for machine values, Fraunces for human copy — each with a job |

---

## Tokens

```
radius     socket 3 · panel 2 · label 0 · button 6 · photo 0
spacing    unit 14 (socket pitch); labels intentionally 3–9 off-grid
type       Fraunces 96/0.92/−0.03 · Fraunces 17/1.6/62ch · Commit Mono 13/1.5/+0.02
colour     ground #151311 · sodium #E5622A (available only) · tape #D8CDBA · text #EFEAE2
motion     socket spring 180 · stagger 40 · cable ease 320 · nothing else
```

---

## Functionality check

- Socket grid — **understanding**: density shows a week of availability in
  one screen, which a calendar cannot.
- Sodium orange on availability only — **usability**: the single question
  every visitor arrives with, answerable without reading.
- Cable length as duration — **understanding** and **brand memory**: encodes
  the booking and is the thing people describe to each other.
- Off-grid tape labels — **brand memory** only. The weakest item here, kept
  because it costs nothing functionally. First to go if it ever gets in the
  way.
