# design-skills

Two Claude Code skills for designing products that decide something, instead
of assembling themselves out of defaults.

- **`ux-direction`** — what the person is doing, and how the system helps.
- **`art-direction`** — how that meaning becomes a visual language.

They are deliberately separate. Not because of length: because they answer
different questions, are invoked at different moments, and are judged by
different criteria. A skill that tried to be both would be summoned for both
and sharp at neither.

## The problem each one solves

**Generated interfaces rarely fail by being ugly. They fail by being
anonymous.** Inter, `rounded-xl`, a soft shadow, three equal cards, a violet
gradient, a hero with a subtitle and a button. Every decision defensible, the
whole thing forgettable. The cause is not bad taste — it is that no decision
was ever made. Defaults filled every slot before anyone asked what the thing
should feel like.

**And visual quality without experience quality is decoration.** An interface
that looks considered and does not understand what someone came to do has
failed at its only job. Beautiful empty states that say "No items found".
Errors that say "Something went wrong". A primary action three clicks deep
because the navigation mirrored the database.

## What makes these different from a list of rules

Most "make it good" prompts are prohibitions. Forty things not to do produces
work that avoids those forty things and is otherwise arbitrary, because
nothing in the list generates anything. Three things are missing, and they
are what these add.

**A way to generate.** In `art-direction`, the visual language is derived from
the subject rather than from taste: name a physical artifact belonging to the
domain and steal its logic. A ticketing product takes perforation and seat
maps from ticket stubs. The artifact supplies geometry, colour semantics and
vocabulary at once, already coherent — which is what taste alone cannot fake.
In `ux-direction`, the mental model must **forbid** something; a model that
permits every architecture has decided nothing.

**Binding artifacts.** Documents get written to disk before any component
exists, and later passes trace back to them. Without that, a concept
evaporates the first time implementation gets difficult and the critique pass
has nothing to judge.

**Audits that can be answered.** "Does this look AI-generated?" and "is it
clear to a first-time user?" are not questions anyone answers honestly about
their own work. So the checks count things: distinct radius values, share of
sections that are cards, clicks to primary value, decisions before first
success, errors with a stated recovery path. The contamination check names
the actual signature of Linear, Stripe, shadcn and five others, so the
question becomes *which of these traits did I borrow*.

## How they compose

```
                    PRODUCT
                       │
          ┌────────────┴────────────┐
    ux-direction              art-direction
    user behaviour            visual language
          └────────────┬────────────┘
                  DESIGN SYSTEM
```

| Building | Sequence |
|---|---|
| App | `ux-direction` → `art-direction` → build |
| Dashboard | `ux-direction` → `art-direction` → build |
| Landing page | `art-direction` → build |

Each skill declares its dependency and works alone. `art-direction` reads
`UX-DIRECTION.md` if it exists and documents its assumptions if it does not;
`ux-direction` respects an existing `ART-DIRECTION.md` and otherwise hands
down functional constraints the visual design must satisfy.

## Passes

**ux-direction** — Understand · Structure · Validate
→ `UX-DIRECTION.md`

**art-direction** — Discover · Direct · Systemize · Build · Critique
→ `ART-DIRECTION.md`, `DESIGN-TOKENS.md`

## Functionality wins

Experimental design is permitted only where it improves understanding,
emotion, usability or brand memory.

> A strange design that confuses people has failed.
> A strange design that feels inevitable has succeeded.

> The goal is not to make something nobody has seen.
> The goal is to make something nobody could have made differently.

There are hard floors — contrast ratios, `prefers-reduced-motion`, visible
focus, keyboard reach, touch targets — that no concept overrides.

## Install

```bash
git clone https://github.com/audient-id4/design-skills /tmp/design-skills
cp -r /tmp/design-skills/art-direction /tmp/design-skills/ux-direction ~/.claude/skills/
```

Or copy either folder on its own — they do not depend on each other's files.
For a single project, use `.claude/skills/` instead.

Invoke with `/art-direction` or `/ux-direction`, or just describe the task —
the descriptions trigger them.

Other agents: each `SKILL.md` is self-contained markdown. Paste it or point
the tool at it.

## Layout

```
ux-direction/
  SKILL.md                          three passes, structure, countable checks
  templates/UX-DIRECTION.md
  examples/UX-DIRECTION.example.md

art-direction/
  SKILL.md                          five passes, rules, audit
  templates/ART-DIRECTION.md        intent: references, artifact, directions
  templates/DESIGN-TOKENS.md        values: type, space, geometry, motion, colour
  examples/ART-DIRECTION.example.md
  examples/DESIGN-TOKENS.example.md
  reference/typography.md           directions, open alternatives, licensing
  reference/escapes.md              replacements for patterns worth avoiding
  reference/stack.md                what to build on, and what CSS already does
```

`SKILL.md` loads on invocation; reference files load only when needed, so the
depth costs nothing until it is used.

## The example

All four example documents describe one product: **Backline**, a booking
service for band rehearsal rooms.

The UX document establishes that people think in *nights*, not calendar
slots — which rules out a month view, hour-by-hour booking, and any flow
where you pick a date before seeing availability. The art direction takes a
**patch bay** as its artifact: sockets become the availability grid, gaffer
tape becomes the annotation layer, and a drawn cable encodes booking duration.
The tokens derive their base unit from the socket pitch.

It exists to show both methods producing a whole system, and to show the
handoff — the UX constraints ("dominant on first screen: availability";
"never adjacent: cancel and book") are visible as visual decisions on the
other side.

## Licence

MIT.
