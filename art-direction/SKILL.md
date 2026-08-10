---
name: art-direction
description: Design an interface with a visual language of its own instead of assembling one from defaults. Use when building a landing page, product UI, portfolio or marketing site where the look has to be distinctive — and whenever a design risks reading as template-generated. Derives the visual language from the subject, writes ART-DIRECTION.md and DESIGN-TOKENS.md before any code, then audits the built result against them. For products with flows or forms, run ux-direction first.
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

## Dependency

This skill defines **visual language**. It does not decide user flows,
information architecture or interaction priorities.

If `UX-DIRECTION.md` exists, it is upstream — read it first and treat it as
settled. The primary action it names is what the composition must make
dominant; the hierarchy it defines is the hierarchy the design expresses.

If it does not exist, make reasonable assumptions about behaviour and write
them down in `ART-DIRECTION.md` under **Assumed behaviour**, so the next
person can see what the visual system was designed against and correct it.

A landing page usually needs only this skill. Anything with flows, forms,
empty states or destructive actions wants `ux-direction` run first.

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

## Register

Decide this before anything else, because it calibrates every rule below.

**The default register is a modern product site that is obviously well made
— not an experiment.** Generous space, confident type, restrained colour,
surfaces that round softly, motion that is short and physical. The kind of
page people describe as expensive without being able to say why.

Distinctiveness is not achieved by breaking that register. It comes from
**one real difference, executed calmly, with everything around it ordinary
and excellent.** Usually the difference is committing to the product's own
material where every competitor ships a stock illustration.

Read the rest of this skill through that. The prohibitions exist to stop
defaults arriving unexamined, not to force unusual answers:

- Cards are fine. Three cards are fine. Make them unequal and give each one
  real content, and the "no template shapes" rule is satisfied — the failure
  was never the card, it was three interchangeable ones.
- Rounded corners are fine. A radius system with roles is the requirement;
  hard corners everywhere is a statement, and a statement is not the goal.
- A hero with a headline and a button is fine, provided the most valuable
  thing on the page is beside it rather than below it.

Two failures, and the second is the one that keeps happening:

*Template* — nothing was decided, so defaults decided it. Anonymous.

*Costume* — strangeness was pursued as proof of effort. Hard edges
everywhere, a clever scroll mechanic, pricing rendered as sculpture. It
reads as designed, which is not the same as good, and it costs the reader
something every time.

**Aim between them and closer to the first.** A page that looks like a very
good version of a normal thing beats a page that looks like an argument.

## The five passes

**Pass 1 — Discover.** Gather references, find the artifact, write
`ART-DIRECTION.md`. No component code.
**Pass 2 — Direct.** Three directions from that concept. Choose one, kill two
on the record.
**Pass 3 — Systemize.** Write `DESIGN-TOKENS.md` from the winner.
**Pass 4 — Build.** Implement them. Both documents bind.
**Pass 5 — Critique.** Render it, look at it, audit it, fix it.

The documents are the point. Without them, pass 1 is a nice paragraph that
evaporates the moment implementation gets difficult, and pass 3 has nothing
to judge against. Write them before writing components, and keep them in the
repo — the next person to touch the design needs them more than you do.

Two files, because they answer different questions and rot at different
speeds. `ART-DIRECTION.md` is intent: what this is, why, and what was
rejected. `DESIGN-TOKENS.md` is the values that intent produced. Intent
changes rarely; tokens get tuned. Mixing them means every tweak to a radius
edits the document that was supposed to be stable.

Templates: `templates/ART-DIRECTION.md`, `templates/DESIGN-TOKENS.md`.
Worked examples in `examples/`.

---

## Pass 1 — Discover

### Start with what is actually being bought

Before references, before the artifact, write one sentence: **what does this
person get, emotionally, that they could not get otherwise?**

In their words, not the product's. Not the category, not the feature list.

*Not:* "world authoring tools."
*Yes:* "the ability to turn a place that exists in their head into somewhere
other people can walk around."

*Not:* "rehearsal room booking."
*Yes:* "knowing the band can actually play on Thursday, before the argument
about Thursday starts."

Everything downstream is chosen to express this sentence. A metaphor that
does not is a metaphor about something else, however well made.

Ask it a second way, because the first answer is usually the expert's answer:
**what did they love about this before they got good at it?** People arrive
at world-building for impossible places, not for grid snapping. They become
precise later. A design that speaks only to the expert has removed the reason
anyone became one.

### Cast the net first: the inspiration map

Before settling on anything, collect twelve references — and none of them
from a website.

- **3 physical objects** from or near this domain
- **3 architectural references** — buildings, interiors, structures
- **3 editorial references** — books, magazines, records, posters, signage
- **3 motion references** — film, machinery, sport, dance, natural movement

Beside each, one line: *what specifically transfers*. Not "the mood" — a
property. The pitch of a grid. A joint detail. How a caption sits relative to
its image. The way a mechanism arrives at rest.

Two reasons for the rule against websites. Web references get copied at the
surface, because the surface is already in the right medium and lifting it
requires no translation. And a domain's real visual heritage is almost never
on the web — it is in the objects and printed matter the field actually used
before software arrived.

Twelve is deliberately more than you need. Most will not survive; the point
is range wide enough that the survivor was chosen rather than settled for.

### Derive from the subject, not from taste

"Invent a visual metaphor" is where most attempts stall, because taste has
nothing to push against. So do not start from taste. Start from the thing
itself.

### Two pools, and the bias between them

Candidate artifacts fall into two kinds, and they are not interchangeable.

**Apparatus** — the professional instrument of the domain. The ledger, the
patch bay, the drafting mylar, the track sheet. How the work gets done.

**Outcome** — what the person makes, and what it feels like to have made it.
The finished world, the room full of sound, the shelf of things that did not
exist last week.

**The method is biased toward apparatus, and you must correct for it.** Ask
for a physical object belonging to a domain and the professional instrument
is what surfaces first — it is concrete, photogenic and easy to name. Follow
that reflex and every product becomes an instrument panel.

That is right when the product *is* an instrument, where the job itself is
the value and precision is what the person is buying. It is wrong whenever
the value is what the user **makes**, because then the apparatus is the least
interesting thing in the room and the design ends up celebrating the process
instead of the result.

A world-building platform designed from drafting mylar becomes CAD software.
Coherent, well made, and about the wrong thing: it speaks of tolerance and
revision letters to someone who came to build a floating island. See
`examples/REJECTED-blocksmith.md` — a failure worth reading, because nothing
about it looks like a mistake from inside.

So name at least one candidate from **each** pool before choosing, and write
down which pool won and why. If the emotional purchase you wrote is about
making something, the outcome pool leads and the apparatus may supply
details — never the reverse.

### Promote one

From the twelve references, promote **one** to primary: the artifact whose
logic the whole design will follow. The other eleven stay available as
sources for individual details, but only one sets the system — two competing
metaphors produce a design that argues with itself.

Steal its visual logic, not its skeuomorphic surface.

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

### The soul test

Run this the moment a metaphor is chosen, before a single token is written.
A metaphor is not good because it is sophisticated, rare or intellectually
satisfying. It is good because it expresses the sentence you wrote first.

Reject it if any of these is true:

- **It makes the product feel like a professional tool when the product is
  about making things.** Precision is a virtue the design may carry. It is
  not the reason anyone showed up.
- **It substitutes the maker's craft for the user's emotion.** A design that
  is chiefly enjoyable to the person who made it has an audience of one.
- **It would describe another industry equally well.** Run the substitution:
  strip the product name and swap the domain nouns — worlds for buildings,
  tracks for invoices. If the design still fits, the metaphor was about the
  apparatus, and apparatus is shared across industries. That is precisely why
  it felt so clean.
- **It explains how the thing is produced and forgets why anyone wants it.**

And the plain version: **crop the logo, show it to someone. If it reads as
CAD, enterprise software or a documentation tool — and the product is not one
of those — the metaphor is wrong.** Not underdeveloped. Wrong. Go back to the
outcome pool.

### The anti-concept test

> Would this still be the right design if nobody ever saw your portfolio?

Where the answer is no, that part is there to be admired rather than to work.
Remove it. No decision in an interface exists to impress another designer,
and the ones that do are always the ones that survive review — they are the
most defensible and the least useful.

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

## Pass 2 — Direct

One concept supports more than one interface. Before committing, sketch
**three visual directions** from the artifact you chose, then pick one and
record why the other two lost.

Not brainstorming. The purpose is to prove the final direction was *chosen*
rather than arrived at — the first workable idea wins by default otherwise,
and a first idea that happens to be good is indistinguishable, in the
finished product, from one that was never tested.

Each direction needs enough substance to be judged against the others:

- what it makes dominant, and what it makes quiet
- its geometry and spacing character in a sentence
- which property of the artifact it leans on hardest
- what it is bad at — every real direction is bad at something

Sketch them however is fastest. Prose is legitimate; a paragraph per
direction that a reader can picture beats three half-built components.

Then choose, and write the two rejections down with reasons. "Weaker" is not
a reason. *"Direction B put the grid full-bleed and the density read as a
spreadsheet — the annotation layer had nowhere to sit, which is half the
concept"* is a reason.

**This is not the rejection log.** That one kills defaults — the obvious
choices you refused. This kills alternatives — three directions that were all
genuinely available. Different failure modes, both worth guarding: one is
arriving at the generic, the other is stopping at the first idea.

---

## Pass 3 — Systemize

Write `DESIGN-TOKENS.md` from the winning direction. Type, space, geometry,
motion, colour — every value carrying its **role**, not just its number.

Tokens come after the direction is settled, never before. Values tuned
against a design that is still moving get tuned twice, and the second pass
is always the one that reverts to round numbers.

Two rules make the difference between a token file and a list of variables:

**Every token states its job.** `radius-sm: 3px — sockets, because a jack
socket is almost square` survives a review. `radius-sm: 3px` is a number
nobody can argue with, which means nobody will, which means it will drift.

**The base unit comes from something in the design.** The type size, a grid
pitch, a component's height. A unit derived from the work holds up under
pressure; one picked because it is round gets abandoned the first time it is
inconvenient.

If two tokens share a role, they are one token written twice — merge them.

Template: `templates/DESIGN-TOKENS.md`.

---

## Pass 4 — Build

This is where concepts die. Implementation pressure pulls every value back
toward the default, one reasonable-looking shortcut at a time. Two defences:

Pick the stack before the first component. It does not make a design good —
decisions do, and everything here is reachable in plain HTML and modern CSS.
What it decides is *cost*: on the wrong stack, springs, reduced-motion
variants, optical font loading and token traceability all become work that
gets cut under deadline. `reference/stack.md` has the default, when to use
something else, and what modern CSS already does without a library.

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

Type is the voice of the product, and it is the first thing to go generic. A
face is correct only when it reinforces the metaphor — never because it is
popular, because a framework ships it, or because it looks clean in
isolation.

Choose in three steps: name the **role** (display / body / interface / data),
name the **personality** (neutral, warm, technical, editorial, luxurious,
experimental), then take the **smallest system that works** — one display
family plus one text family, mono only if the concept carries technical
values.

`reference/typography.md` has four reference directions with the canonical
faces for each, free equivalents that hit the same brief, and the licensing
rules that decide which you can actually ship.

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

### Show the output

If the product makes something, **the thing it makes goes in the first
screen** — bigger than the headline, before any claim about it. A world, a
chart, a track, a document, a room. Not a screenshot of the tool that made
it, and not an illustration standing in for it.

The tool itself appears once, further down, as evidence that it exists. It
is proof, not the argument.

**Generate it rather than illustrating it.** The reflex here is to specify a
beautiful custom render — and then either it never gets made, or a stock
approximation lands in its place and the page becomes every other page with
better art. Build the real thing instead: the actual geometry, the actual
chart from actual numbers, the actual document. It is usually less work than
commissioning the render, it cannot be bought by a competitor, and it can
move.

That last part matters. A rendered image is the same image on every visit; a
generated one can assemble itself in the first two seconds and respond to the
cursor. For a product about making things, *watching one get made* is the
entire pitch, and no illustration delivers it.

### Imagery, icons, emoji

An image earns its place by carrying an idea. Decorative stock, abstract
gradient blobs and generic Unsplash all fail that test. One strong visual
object beats twelve arbitrary ones.

An icon earns its place by improving comprehension faster than a word would.
An icon next to a label that already says the same thing is noise. If you do
use a set, use one set — mixed icon styles read as assembled from parts,
because they were.

Emoji as spacing filler is the most obvious generated-design tell there is,
and worth checking for explicitly. If they are not carrying meaning, none.

When they are, one set, never mixed. Two ways, and the first is usually
right:

**System rendering.** `font-family: "Apple Color Emoji", "Segoe UI Emoji",
"Noto Color Emoji"`. Everyone gets the set their own device draws, which is
the set they already read fluently. Costs nothing, loads nothing, never
breaks.

The instinct to force Apple's set on every platform is worth resisting: it
is the prettiest set, but on Windows it makes the glyphs read as foreign to
that reader rather than native — the opposite of belonging to one ecosystem.

**A shipped image set**, only when the same glyph must be identical
everywhere — a product screenshot, a brand mark, a legend where the shape
carries meaning. Then use an openly licensed set: **Noto Emoji** (OFL),
**OpenMoji** (CC BY-SA) or **Fluent Emoji** (MIT). Apple's artwork is
licensed to Apple; packages that redistribute it as PNGs are widely used and
are not clean, and a commercial client site is the wrong place to find out
how much that matters.

Self-host whichever you pick. An emoji set on a third-party CDN is a
dependency in the critical path that disappears in whole countries.

### Motion

**Motion is required, not optional, and it comes from the metaphor.** A
static page has declined to answer how this world behaves. Define three
things in `ART-DIRECTION.md` and implement all three:

**Arrival** — how information enters. From the metaphor, not from a library
default. A world assembling from fragments. Layers uncovering in order.
Terrain generating outward from a seed. Parts snapping into a structure.

**Transformation** — how interaction feels. Terrain deforming. A coordinate
system expanding. A hidden layer lifting. Moving between two states of the
same place.

**Feedback** — how the interface answers. Objects reacting to each other.
Connections completing. A rule becoming briefly visible.

Every major section needs at least one motion behaviour that means something.
Not decoration on every section — *meaning* on each one. A section whose only
motion is a fade-up has not been designed, and a page where every section
fades up on scroll is a template with a plugin installed.

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

## Pass 5 — Critique

### Render it first

A design is not finished when the code compiles. It is finished when the
rendered pixels defend themselves.

Run the thing. Capture desktop, tablet and mobile. Look at the images, not
at the source — reading CSS tells you what you intended, and the whole
purpose of this pass is to find where intent and result parted company.
Anything that drives a browser will do.

Then compare each screenshot against `ART-DIRECTION.md`. Go section by
section and ask which document line each part of the composition is
honouring. The parts nobody can account for are where the defaults crept
back in, and they always do creep back in — usually in the places that were
hardest to build.

Mobile gets judged as its own composition, not as evidence that nothing
overflowed.

### The generated defaults

Check this before the contamination table, because it catches a different
disease. Contamination is copying a specific product. This is landing on
what *every model produces right now*, having copied nobody.

Generated design currently clusters into three looks. They appear regardless
of subject, which is the tell:

| Cluster | What it is |
|---|---|
| **Warm editorial** | cream ground near `#F4F1EA`, high-contrast serif display, terracotta accent, generous whitespace |
| **Acid dark** | near-black ground, one bright acid-green or vermilion accent, everything else grey |
| **Broadsheet** | hairline rules, zero border-radius, dense newspaper columns, monospace annotation, plate numbers |

All three are legitimate for some briefs. Where the brief asks for one, give
it — the brief always wins. Where the brief leaves the axis free, **do not
spend that freedom on one of these**, because the freedom is the only place a
choice could have been made.

Two things make this check worth running separately from the contamination
table:

It catches convergence rather than imitation. You can arrive at the cream
ground honestly, with a reasoning chain you believe, and still be sitting in
the same square as everything else generated that week. A good justification
is not evidence of a distinctive result; it is what makes the default
invisible.

And it catches both directions of the earlier failure. A world-building
platform drawn as drafting mylar — plate numbers, hairlines, zero radius — is
cluster three. Redrawn on warm paper with a serif, it becomes cluster one.
Two attempts, opposite in character, both landing on this list, neither
copying anyone.

If a cluster matches, do not repaint it. Ask which decision was left open,
and answer it from the artifact.

### Reference contamination

Then check what you borrowed. "Does this look like Linear?" is unanswerable
as asked, so name the signature instead — each of these products has traits
specific enough to point at.

| Borrowed from | What it actually is |
|---|---|
| Linear | near-black ground, high-chroma violet accent, 6–8px radii everywhere, very tight display tracking, hairline gradient borders |
| Apple | system stack, huge centred display type, symmetric generous whitespace, full-bleed product photography, everything on axis |
| Vercel | absolute black and white, mono for accents, triangle motif, chrome stripped to nothing, geometric sans |
| Stripe | gradient mesh backgrounds, indigo-to-cyan, layered offset cards, code as hero content |
| Notion | warm off-white ground, flat outline illustration, serif display over sans body, emoji as interface elements |
| Arc | saturated multi-hue gradients, oversized playful rounding, spatial and depth metaphors |
| Raycast | dark glass panels, keyboard-shortcut chips, small sharp radii, red-orange accent |
| shadcn | neutral-950 ground, uniform `rounded-md`, muted 1px borders, Inter, card-and-badge vocabulary |

For every row you recognise in your build, do not simply swap the value.
Find out *why* it arrived: which decision was left unmade, so that a known
solution filled the gap. Then answer that decision from the primary artifact.
Changing violet to teal leaves Linear's design underneath wearing a different
colour.

Being similar in one respect is not automatically failure — dark grounds are
not owned by anyone. Three or more rows matching is not similarity, it is a
port.

### Then the panel

Look at the result as four people: an Apple product designer, Dieter Rams, a
working art director, and a hostile critic. Find at least five decisions that
can be better. Fix them.

### Then the audit These are countable, which is the point — "does it look
AI-generated" is not a question anyone answers honestly about their own work.

| Test | Threshold |
|---|---|
| Distinct border-radius values | 2–5, each with a stated role |
| Display-to-body hierarchy | deliberate and stated in the document — big jumps encouraged, not required |
| Top-level sections that are cards | under 40% |
| Gradients | ≤ 1, named in the document |
| Contamination rows matching | ≤ 2 |
| Generated-default cluster matched | 0, unless the brief asked for it |
| Elements breaking the grid | ≥ 1, deliberate |
| Font families | ≤ 2, plus mono if the concept needs it |
| Display face swapped for a system font | identity visibly degrades |
| Icons with an adjacent label saying the same thing | 0 |
| Emoji used as spacing or decoration | 0 |
| Values not traceable to the document | 0 |

Then the removal test: name the 20% you would cut. If cutting it would make
the design stronger, it was decoration. Cut it now.

### Simplicity

The interface must not communicate *look how considered this design is*. It
must communicate *this product makes a complicated thing feel simple*.

Those two produce very different pages from the same concept. The first
shows the system: the grid, the apparatus, the craft. The second shows the
result and keeps the system underneath, load-bearing and mostly invisible.

Remove anything that exists only to demonstrate skill. What should be
noticed is clarity, confidence, emotion and quality — not grids, effects and
concepts. A viewer who can describe your concept back to you after ten
seconds is looking at the concept instead of the product.

### Score it

Rate each out of ten. **Anything under 9 goes back.**

| | |
|---|---|
| **Product truth** | Does this feel like the natural interface for *this* product, rather than a good interface applied to it? |
| **Emotional truth** | Does it communicate why someone wants this? |
| **Recognition** | Identifiable with the logo cropped out? |
| **Restraint** | Would removing 20% improve it? |
| **Motion** | Does interaction reveal meaning, or just move? |

When a score is low, do not add decoration to raise it. **Find the missing
idea.** A low emotional-truth score is never fixed by a gradient; it means
the concept is about the wrong thing and pass 1 has to be re-entered.

### Language

Write reasoning in mechanisms, never adjectives. "Premium", "futuristic",
"immersive", "elegant" and "clean" are conclusions dressed as arguments — they
describe how you hope it will be received, and they justify anything.

*Not:* "a premium, immersive hero."
*Yes:* "the world renders before any text, so the first thing read is the
product's output rather than a claim about it."

If a sentence in `ART-DIRECTION.md` cannot be checked against the built page,
it is not a design decision.

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

- `reference/typography.md` — type directions, open alternatives, licensing
- `reference/escapes.md` — replacements for the patterns worth avoiding
- `reference/stack.md` — what to build on, and what CSS already does
- `examples/REJECTED-blocksmith.md` — a coherent design about the wrong thing
- `examples/CORRECTED-blocksmith.md` — the same brief done again, from the outcome pool
- `templates/ART-DIRECTION.md` — the artifact to fill in
- `examples/ART-DIRECTION.example.md` — a completed one

## The rule underneath all of it

Optimise for intentionality, not familiarity.

Between safe-and-familiar and unusual-and-coherent, take coherent. Between
more decoration and stronger composition, take composition. Between the
popular pattern and the new idea, try the idea first — and keep it only if
it survives pass 3.

And the test that contains every other one here:

> The goal is not to make something nobody has seen.
> The goal is to make something nobody could have made differently.

Novelty is easy and worth little; anyone can be strange on purpose. What is
hard is a design so completely answered by its subject that every other
version looks like a version — where the type, the geometry, the colour and
the motion could not be swapped for alternatives without the thing becoming
about something else. That is why the artifact comes before taste, why three
directions get compared, and why the rejected ones are written down. Not to
prove the result is original. To prove it was inevitable.
