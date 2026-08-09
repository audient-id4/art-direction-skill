# Corrected — Blocksmith from the outcome pool

The same brief as `REJECTED-blocksmith.md`, re-entered after the process was
fixed. Read them as a pair: identical product, identical rules everywhere
except the artifact pool, and the two designs have nothing in common.

The failure chose drafting mylar — the apparatus of level design — and
produced architectural documentation. This one starts from what the person is
buying, takes the artifact from the outcome pool, and the whole system falls
out of it.

Note the register. It is a normal, well-made modern product page: soft radii,
generous space, three feature cards. The single real difference is that the
hero world is live geometry rather than a stock render. That is enough, and
an earlier draft that pushed further — zero radii everywhere, scroll digging
through strata, pricing rendered as volumes of blocks — was pulled back for
costing the reader something in exchange for looking designed.

---

## Assumed behaviour

No `UX-DIRECTION.md`. Assumed and designed against; correct here if wrong.

- Primary: **open the builder**. Secondary: **see what people built**.
  Tertiary: pricing.
- The visitor wants to know whether their idea is possible here. They are
  not evaluating tolerances.
- One built world outranks every sentence about worlds.

---

## Emotional purchase

> Turning a place that exists in your head into somewhere other people can
> walk around.

**Before they got good at it:** putting one block on flat ground and
realising nothing stops you continuing. Making something that should not be
able to stand up. Showing someone.

Nobody arrives for grid snapping. Precision is learned later, and a page that
speaks only to the expert has removed the reason anyone became one.

---

## Inspiration map

None from a website.

**Physical objects**

| Reference | What transfers |
|---|---|
| A geological core sample | a world has a *bottom* — strata, roots, voids — and it is the proof it is a volume rather than an image |
| A wooden block set on a floor | flat faces, no bevels, shadow doing all the work; the pleasure is that pieces are identical and the result is not |
| A terrarium on a desk | a whole small world, lit from outside, that you turn to look into |

**Architecture**

| Reference | What transfers |
|---|---|
| A cutaway architectural model | the cut face is honest — you see the fill, not a skin |
| Hill terracing | a slope made of discrete steps reads as *built*, not sculpted |
| A gallery plinth | the object is lit and the room is not; the ground stays quiet so the thing on it is the brightest surface |

**Editorial**

| Reference | What transfers |
|---|---|
| Field guide plates | a specimen centred on warm paper, named underneath, nothing else on the page |
| Lego instruction booklets | step numbers, the part count, and *the model photographed finished on the first page* |
| Stratigraphic column diagrams | layers labelled down the side, depth as the reading axis |

**Motion**

| Reference | What transfers |
|---|---|
| A block dropping the last centimetre onto a stack | short travel, hard stop, no float |
| Turning a model to see its far side | rotation as inspection, driven by the hand, no autoplay |
| A core being drawn up out of the ground | descending through layers as a way to move through content |

---

## Artifact

| Pool | Candidate | What it would give |
|---|---|---|
| **Apparatus** | the editor viewport — gizmo, grid snap, brush palette | precision, tool credibility, chrome |
| **Outcome** | **the diorama: a chunk of world lifted out and set on a table** | the finished place, seen from outside, turnable |

**Chosen: the diorama. Outcome pool.**

The emotional purchase is about making a place. Apparatus led last time and
produced architectural documentation — coherent, and about drafting. The
editor still appears, once, as evidence that the tool exists; it is never the
hero. Precision serves the world; the world is not evidence of precision.

**Properties that transfer**

- The cube. Flat faces, no bevel, no gradient — three tones per block, one
  per face direction, and the shape does the rest.
- The world is an *object*: it has edges, it ends, you can turn it.
- It has an underside. Strata, roots, cave voids.
- Colour belongs to the world, not to the brand.
- Terracing: everything steps. Slopes are made of decisions.

---

## Soul test

- [x] Does not make a making-product feel like a professional tool — the
      first thing rendered is a built place, and the editor appears once.
- [x] Expresses the user's emotion, not the maker's craft. The craft here is
      invisible: the world is doing the talking.
- [x] **Substitution.** Swap "worlds" for "buildings" and the design breaks —
      an architecture product does not show you the underside of terrain,
      does not colour itself from biomes, and does not let you turn the
      model to look into a cave. Previous direction survived this swap
      unchanged, which was the tell.
- [x] Explains why anyone wants this, not how it is produced.
- [x] Logo cropped, it reads as a place, not as CAD.

## Anti-concept test

Would this be right if nobody saw a portfolio? Yes — the hero is the
product's output, which is the most useful thing a page for this product can
show. The one part at risk was a scroll-driven cutaway of the whole planet;
dropped, because it exists to be admired and delays the primary action.

---

## The nine questions

**1. Concept.** A world, lifted out and set down on warm paper, that builds
itself and lets you turn it.

**2. Emotion.** Two seconds in: *I want to make one*. Not *this is
professional*.

**3. Recognition.** Coloured voxel volumes on a warm off-white ground, with
their undersides visible. Everything on the page is made of the same cube.

**4. Metaphor.** Above, and the underside is where it becomes ours rather
than generic voxel art.

**5. Typography.** *Bricolage Grotesque* for display — variable width and
optical size, drawn deliberately irregular; a product about making things by
hand should not be lettered by a face that hides its hand. *Instrument Sans*
for text: clean, not anonymous. *JetBrains Mono* for coordinates, block
counts and dimensions — machine values, tabular, small.

**6. Geometry.** The register is a well-made modern product, not a
manifesto. Hard corners everywhere would be a statement, and the statement
is not the point — the world is. So: surfaces round softly and the *content*
stays cubic. Panels 16, cards 14, thumbnails 10, buttons 10, chips 8. Four
values with roles, all in the same family, so nothing reads as borrowed from
a different design.

The cube shows up where it belongs — in the worlds, the icons and the
capability objects, all of which are actual geometry with flat faces and no
bevel. Soft frames around cubic content is the whole visual idea in one
sentence.

**7. Spacing rhythm.** Base unit 8px, the block edge at display scale.
Everything is a whole number of blocks. Sections 96 apart, the hero opens
with 160 of air above the world, because a thing on a plinth needs room and
that generosity is most of what reads as expensive.

**8. Colour.** Warm paper ground `#F6F3EE`. The ground is the quietest thing
on the page so the world is the brightest — a dark UI would compete with the
worlds and every world would have to fight it. Ink is warm near-black.
Accent is **not a brand colour**: it is grass green, taken from the block
palette, used only on the primary action and the live counters, so the
interface and the worlds are visibly made of the same material. No gradient.
No violet.

**9. Interaction language.** Physical and short. Blocks arrive by falling the
last few pixels and stopping hard. Nothing floats, nothing eases in from
nowhere, nothing fades up on scroll.

---

## Motion

| | From the metaphor | Where |
|---|---|---|
| **Arrival** | the world assembles: blocks drop in from above, bottom layer first, and land hard | hero on load; each section's voxel object on first view |
| **Transformation** | turning the model to inspect it — drag rotates the diorama, and the rotation persists as you scroll | hero, and the showcase thumbnails |
| **Feedback** | a face lifts a block-height and drops a shadow on its neighbours | every hoverable: buttons, world cards, plan rows |

Per section, at least one behaviour that means something:

- **Hero** — assembly, then drag-to-turn.
- **Capabilities** — each card holds a small voxel object that builds when it
  enters view; the three build in sequence, not together.
- **Editor** — the screenshot is the tool's own evidence; it arrives by
  clip-wipe, not fade.
- **Showcase** — thumbnails tilt slightly toward the cursor, as objects on a
  shelf do when you lean.
- **Closing** — one block drops onto empty ground. That is the whole product,
  and it is the only motion on that band.

Pricing stays a plain, quiet table. It was going to render plans as volumes
of blocks; cut — clever where the reader wants a number, and it delays the
one decision the page is asking for.

Springs for anything the hand started; a short hard ease for anything the
system started. Reduced motion: worlds appear built, thumbnails hold a fixed
angle, hovers become instant tone changes. No information lives only in
movement.

---

## Signature detail

**The world is real, not a render.** Every site in this category ships a
beautiful static image of its output. Ours ships the output: actual geometry,
assembled block by block in front of you on load, and turnable by hand. A
product about building worlds shows a world being built, once, in the first
two seconds — and then lets you pick it up.

That is the entire difference from a template, and it is enough. A stock
render can be commissioned by anyone; a world you can turn cannot.

Its **underside** is visible — soil, stone and cave void in the cut face,
because the diorama sits above the plinth rather than on it. Not a mechanism,
just the detail that proves this is a volume rather than a picture of one.
It was going to drive the scroll; cut for being clever at the reader's
expense.

---

## Rejection log

| Obvious choice | Why rejected | Replaced with |
|---|---|---|
| Hero screenshot of the editor, headline left | Puts the tool where the output should be, and every tool site looks like this. The editor proves the product exists; it is not why anyone wants it | The built world as hero; the editor appears once, further down, as evidence |
| Dark UI, neon accent, "creative tool" register | Competes with the worlds. Every world would have to be lit to survive the background, and the palette would belong to us instead of to them | Warm paper ground, worlds as the only saturated thing |
| Three equal feature cards | Says the three matter equally, which is untrue | Kept as three cards — the register is a modern product page and this is the clearest shape for it — but unequal: different widths, each holding a voxel object at its own scale, sequenced rather than simultaneous |
| Making it strange to prove it is not a template | Novelty at the reader's cost. The brief is a modern product site that does not look generated, not an experiment | One real difference — the world is live geometry — executed calmly, with everything around it ordinary and well made |

---

## Directions considered

**A — Diorama on paper.** The world as an object on a quiet ground, lit from
outside, turnable. Dominant: the built place. Quiet: everything else. Leans
on the terrarium and the plinth. *Bad at:* conveying that this is a tool with
depth — risks reading as a gallery.

**B — Inside the world.** First person, standing in a built place, UI as
overlay. Leans on the immersive half. *Bad at:* it becomes a game page, which
is explicitly what this product is not, and it cannot show the underside.

**C — The infinite chunk field.** Chunks assembling outward forever, systemic
and cool. Leans on scale. *Bad at:* it is the apparatus trap again in a
prettier coat — a systems diagram, cold, about the engine rather than the
place.

**Chosen: A**, with the editor screenshot borrowed from B's honesty about
being a tool.

**Rejected, and why:** B fails the product truth test — the brief says this
is not a game page, and first person is the visual grammar of one. C fails
the soul test: swap worlds for cities and it still fits, because a chunk
field is apparatus.

---

## Score

| | | |
|---|---|---|
| Product truth | 9 | The page is made of the product's own material |
| Emotional truth | 9 | The first thing seen is a place worth exploring |
| Recognition | 9 | Warm paper, coloured voxels, visible undersides — no other tool site shows the bottom |
| Restraint | 9 | The planet cutaway was the 20%; it is already cut |
| Motion | 9 | Assembly, turning and stratum descent all carry meaning |
