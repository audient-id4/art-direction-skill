---
name: art-direction
description: Design an interface with a visual language of its own instead of assembling one from defaults. Use when building a landing page, product UI, portfolio or marketing site where the look has to be distinctive — and whenever a design risks reading as template-generated. Runs a three-pass process that writes its art direction to disk before any code.
---

# Art direction

Most generated interfaces fail the same way. Not ugly — *anonymous*. Inter,
`rounded-xl`, a soft shadow, three equal cards, a violet gradient, a hero
with a subtitle and a button. Every decision defensible, the whole thing
forgettable.

The cause is not bad taste. It is that no decision was ever *made*. Defaults
filled every slot before anyone asked what the thing should feel like.

This skill forces the question first, records the answer, and then checks
the built result against it.

## Functionality wins

Read this before the rest, because everything below is subordinate to it.

Experimental design is permitted only where it improves understanding,
emotion, usability or brand memory. Novelty that costs any of those is not a
trade-off worth making — it is a failure wearing a concept as a disguise.

**A strange design that confuses people has failed. A strange design that
feels inevitable has succeeded.**

Inevitability is the target, not strangeness. The most distinctive interfaces
do not feel arbitrary; they feel like the only sensible answer to their
subject, and the reason they look unfamiliar is that nobody had bothered to
answer it properly before. If a decision cannot survive the question "does
this help someone use or understand this thing better", it is decoration with
a manifesto attached.

## The three passes

**Pass 1 — Invent.** Write `ART-DIRECTION.md`. No component code.
**Pass 2 — Build.** Implement it. The document binds.
**Pass 3 — Critique.** Audit against countable tests, then fix.

The document is the point. Without it, pass 1 is a nice paragraph that
evaporates the moment implementation gets difficult, and pass 3 has nothing
to judge against. Write the file before writing components, and keep it in
the repo — the next person to touch the design needs it more than you do.

Template: `templates/ART-DIRECTION.md`. Worked example:
`examples/ART-DIRECTION.example.md`.

---

## Pass 1 — Invent

### Derive from the subject, not from taste

"Invent a visual metaphor" is where most attempts stall, because taste has
nothing to push against. So do not start from taste. Start from the thing
itself.

Name a physical artifact, a historical document or a working object that
belongs to this domain. Then steal its visual logic — not its skeuomorphic
surface.

- A ticketing product → ticket stubs. Perforation as a divider. Seat maps
  as a layout grid. Serial numbers set in a monospace face.
- A financial tool → the ledger. Hairline rules, tabular figures, red and
  black as semantics rather than decoration, columns that actually align.
- A reading app → the printed page. A measure that respects the eye, wide
  margins, running heads, footnotes as a real interface element.
- A studio portfolio → the contact sheet. Frame numbers, crop marks, images
  edge to edge, captions in the margin.

The artifact gives you geometry, colour semantics, typography and a
vocabulary of parts at once — all of them coherent, because they were
coherent in the original. That coherence is what taste alone cannot fake.

If the subject genuinely has no artifact, derive from its *behaviour*: what
does the product do to time, to attention, to the user's material? A tool
that compresses becomes dense. A tool that reveals becomes layered.

### The nine questions

Answer each in `ART-DIRECTION.md`, in a sentence or two. Vague answers here
produce a vague interface; if you cannot say it plainly, you have not
decided it.

1. **Concept** — what is the visual language, in one sentence?
2. **Emotion** — what should someone feel in the first two seconds?
3. **Recognition** — what would let someone identify a screenshot of this
   with the brand name cropped out?
4. **Metaphor** — the artifact above, and which of its properties transfer.
5. **Typography personality** — the faces, and what they are *for*. Not
   "modern and clean".
6. **Geometry language** — the radius system, the corner logic, when edges
   go sharp and why.
7. **Spacing rhythm** — the intervals, and where the composition compresses
   and where it opens.
8. **Interaction language** — how this interface responds to being touched.
9. **Signature detail** — the one thing that is not standard.

### The rejection log

List three obvious choices you considered and killed, with the reason and
what replaced them. Example: *"Hero with centred headline and CTA — rejected:
puts the product's most interesting artifact below the fold. Replaced with a
left-aligned masthead and the artifact full-bleed to the right."*

This is not paperwork. The rule "if a decision looks obvious, find a better
one" is unenforceable without evidence that alternatives were considered.
The log is that evidence, and reviewing it is faster than reverse-engineering
intent from CSS.

---

## Pass 2 — Build

This is where concepts die. Implementation pressure pulls every value back
toward the default, one reasonable-looking shortcut at a time. Two defences:

**Every value traces to the document.** If a number cannot be justified from
`ART-DIRECTION.md`, it is a default that slipped in.

**Comment the five most visible decisions** in the code with the reason, not
the value. `/* 34px: the shell radius less its padding, so the nested panel
curves on the same centre */` — not `/* border radius */`.

### Spacing

Build a scale that belongs to this design. 4/8/12/16/24/32/48/64 is a fine
scale — it is not the only one, and reaching for it reflexively is the
problem, not the numbers themselves. Ratio-based scales, a scale seeded from
the type size, or an irregular scale with a stated logic are all legitimate.

Asymmetry is a tool: a section can breathe on one side and press against the
other. Optical alignment beats mathematical alignment — a circle and a square
of equal box size do not look aligned, and the circle wins the argument.

Whitespace is composition. An expanse of nothing next to a dense block is a
decision; even padding everywhere is the absence of one.

### Typography

Type carries more of the character than colour does, and it is the first
thing to go generic. See `reference/typography.md` for concrete directions
and why each one reads the way it does.

Rules that hold regardless of face:

- Set the display size against the composition, not against a scale you
  memorised. Read it at the actual viewport before accepting it.
- A hierarchy needs contrast. If display and body sit within 2× of each
  other, the page reads flat — one real jump does more than four small ones.
- Measure: 45–75 characters for body copy. Wider is not more generous, it
  is harder to read.
- Line-height moves inversely with size. Display type set at body leading
  looks loose; body copy set at display leading looks cramped.
- Negative tracking on large type, normal or slightly positive on small.
  Most faces are drawn for text sizes and go gappy when scaled up.
- Variable fonts: use the optical size axis if the face has one. This is the
  single cheapest way to look considered.

A composition can be typography alone. If it works without ornament, stop.

### Geometry

One radius everywhere is a tell. Radius is a function of an element's size,
weight and role — a 4px chip and a 900px panel curved identically will look
wrong at one of the two, always.

Nested radii must be concentric: `inner = outer − padding`. Get this wrong
and the gap between shell and panel visibly pinches at the corners. It is
the most common invisible-until-you-see-it defect in generated UI.

Sharp corners are available. So is asymmetry — one corner squared on an
otherwise-round card can become the signature detail, if it means something.

Three to five distinct radii, each with a stated role. Fewer is a system
that has not been thought about; more is noise.

### Colour

Build a system, not a palette. Colour needs hierarchy (what dominates),
semantics (what a colour *means* here), temperature, and a contrast strategy.

Restraint reads as expensive. One unexpected hue used consistently will
carry an identity further than a full spectrum. Derive the neutrals from
the accent's hue rather than using pure greys — off-hue neutrals make a
page look tinted and intentional; `#888` makes it look unfinished.

Gradients: at most one, and only if the document names it as part of the
concept. A gradient applied because a flat colour "looked plain" is the
signature of a design with no other idea.

### Components

A card is not the default container. It is one answer to "this content is a
discrete unit", and it is overused because it is easy.

The alternatives are not exotic: full-bleed sections, overlapping elements,
content that sits directly on the page, asymmetric grids, editorial columns,
elements that break the grid deliberately, floating panels, typographic
compositions with no container at all.

A component exists because the content demands it. If a library offers it
and the content does not need it, that is not a reason.

### Imagery, icons, emoji

An image earns its place by carrying an idea. Decorative stock, abstract
gradient blobs and generic Unsplash all fail that test. One strong visual
object beats twelve arbitrary ones.

An icon earns its place by improving comprehension faster than a word would.
An icon next to a label that already says the same thing is noise. If you do
use a set, use one set — mixed icon styles read as assembled from parts,
because they were.

Emoji: native system rendering or none. No packs, no 3D, no Twemoji mixed
with system glyphs. Emoji as spacing filler is the most obvious AI tell there
is, and it is worth checking for explicitly.

### Motion

Motion explains a change of state. It is not proof that CSS is working.

Ask what physically happens: does the element arrive, expand from its
origin, or was it always there and now revealed? The answer picks the
technique — transform and clip for spatial change, opacity for presence,
blur for depth, scale for emphasis.

Springs for anything the user initiated; they carry momentum and feel
answered. Eased curves for anything the system initiated. Durations between
roughly 150ms and 400ms for interface motion; longer needs a reason.

Do not animate everything. A page where every element fades up on scroll
reads as a template with a plugin installed.

### Microinteractions

This is where an interface starts to feel expensive, and it is the first
thing skipped. Every interactive element needs hover, active, focus and
disabled. Every async surface needs loading, empty, success and error.

Empty states are a design opportunity that almost everyone wastes.

Focus must be visible and must not be the browser default ring bolted onto a
custom design. Keyboard navigation is part of the interaction language, not
an accessibility checkbox.

### Responsive art direction

Mobile is a different composition, not a narrower one. Revisit the type
scale, the hierarchy, the navigation model, image placement and the
component structure. A display size that carries a 1440px composition is
usually wrong at 390px — not too big, *wrong*, because the relationship to
everything around it changed.

---

## Pass 3 — Critique

Look at the built result as four people: an Apple product designer, Dieter
Rams, a working art director, and a hostile critic. Find at least five
decisions that can be better. Fix them.

Then run the audit. These are countable, which is the point — "does it look
AI-generated" is not a question anyone answers honestly about their own work.

| Test | Threshold |
|---|---|
| Distinct border-radius values | 3–5, each with a stated role |
| Top-level sections that are cards | under 40% |
| Display-to-body size ratio | at least one jump ≥ 2.5× |
| Gradients | ≤ 1, named in the document |
| Elements breaking the grid | ≥ 1, deliberate |
| Font families | ≤ 2, plus mono if the concept needs it |
| Icons with an adjacent label saying the same thing | 0 |
| Emoji used as spacing or decoration | 0 |
| Values not traceable to the document | 0 |

Then the removal test: name the 20% you would cut. If cutting it would make
the design stronger, it was decoration. Cut it now.

Then the recognition test. Crop the logo out of a screenshot. Could someone
tell this apart from a hundred other sites? If not, the concept did not
survive pass 2 — go back to the document and find where it was dropped.

Finally, the inevitability test, and it outranks every other test here. Walk
the interface as someone seeing it for the first time with something to get
done. Does any distinctive decision slow them down, hide what they came for,
or need explaining? Each one that does is novelty charging rent it cannot
pay — remove it, however good it looks in isolation. What should remain is
an interface that is unlike the others and yet feels like the obvious way to
have built this particular thing.

---

## Hard floors

These hold regardless of concept. Unusual has to stay usable; a design that
is distinctive and unreadable has failed at the only job it had.

- Body text contrast ≥ 4.5:1, large text ≥ 3:1. Measure, do not eyeball —
  low-contrast grey-on-grey is itself a generated-design cliché.
- Honour `prefers-reduced-motion`. Vestibular disorders are not a style
  preference.
- Focus is always visible, on every interactive element.
- Touch targets ≥ 44px, or ≥ 24px with adequate spacing around them.
- Text remains selectable. Cursor experiments must not break selection or
  scrolling.
- Fonts load without layout shift: `font-display: swap` with metric-matched
  fallbacks, or self-host and preload.
- The signature detail must do work — carry meaning, aid navigation, or
  reveal content. A detail that only surprises is a gimmick, and gimmicks
  age in weeks.

## Reference

- `reference/typography.md` — concrete type directions and what each conveys
- `reference/escapes.md` — replacements for the patterns worth avoiding
- `templates/ART-DIRECTION.md` — the artifact to fill in
- `examples/ART-DIRECTION.example.md` — a completed one

## The rule underneath all of it

Optimise for intentionality, not familiarity.

Between safe-and-familiar and unusual-and-coherent, take coherent. Between
more decoration and stronger composition, take composition. Between the
popular pattern and the new idea, try the idea first — and keep it only if
it survives pass 3.
