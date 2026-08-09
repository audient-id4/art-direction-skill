# art-direction

A Claude Code skill for designing interfaces that have a visual language of
their own, instead of assembling one out of defaults.

## The problem

Generated interfaces rarely fail by being ugly. They fail by being
anonymous — Inter, `rounded-xl`, a soft shadow, three equal cards, a violet
gradient, a hero with a subtitle and a button. Every decision is defensible.
The whole thing is forgettable.

The cause is not bad taste. It is that no decision was ever made: defaults
filled every slot before anyone asked what the thing should feel like.

## What this does differently

Most "make it look good" prompts are lists of prohibitions. Forty things not
to do produces an interface that avoids those forty things and is otherwise
arbitrary, because nothing in the list generates anything.

This skill adds the three parts a prohibition list is missing.

**A way to generate a concept.** The visual language is derived from the
subject, not from taste. Name a physical artifact that belongs to the domain
and steal its logic: a ticketing product takes perforation and seat maps from
ticket stubs; a finance tool takes hairline rules and tabular figures from the
ledger. The artifact supplies geometry, colour semantics and vocabulary at
once, already coherent — which is the thing taste alone cannot fake.

**Binding artifacts.** Before any component exists, pass 1 writes
`ART-DIRECTION.md` (intent, and what was rejected) and pass 1.5 writes
`DESIGN-TOKENS.md` (the values that intent produced, each with its role).
Pass 2 traces every value back to them. Pass 3 audits against them. Without
written documents a concept evaporates the first time implementation gets
difficult, and the critique pass has nothing to judge.

**An audit you can actually run.** "Does this look AI-generated?" is not a
question anyone answers honestly about their own work. So the checks are
countable: distinct radius values, share of sections that are cards, gradient
count, values not traceable to the documents. The contamination check names
the actual signature of Linear, Stripe, shadcn and five others, so the
question becomes *which of these traits did I borrow* rather than *does this
feel derivative*.

**Proof the direction was chosen.** Pass 1.5 requires three real directions
from the concept, one picked and two killed with reasons. A first idea that
happens to be good is indistinguishable, in the finished product, from one
that was never tested.

## Functionality wins

Experimental design is permitted only where it improves understanding,
emotion, usability or brand memory.

> A strange design that confuses people has failed.
> A strange design that feels inevitable has succeeded.

Inevitability is the target, not strangeness. There are hard floors — contrast
ratios, `prefers-reduced-motion`, visible focus, touch targets — that no
concept overrides.

## Install

Claude Code, per user:

```bash
git clone https://github.com/audient-id4/art-direction-skill ~/.claude/skills/art-direction
```

Or per project, into `.claude/skills/art-direction`.

Then invoke it with `/art-direction`, or just describe a design task — the
description triggers it.

Other agents (Cursor, Codex, anything that reads a markdown instruction file):
`SKILL.md` is self-contained. Paste it or point the tool at it.

## Layout

```
SKILL.md                            the process — four passes, rules, audit
templates/ART-DIRECTION.md          intent: references, artifact, directions
templates/DESIGN-TOKENS.md          values: type, space, geometry, motion, colour
examples/ART-DIRECTION.example.md   a completed one, worked end to end
examples/DESIGN-TOKENS.example.md   its tokens, every value with its role
reference/typography.md             type directions and what each conveys
reference/escapes.md                replacements for the patterns worth avoiding
```

`SKILL.md` loads when the skill is invoked. The reference files load only
when something in them is needed, so the depth costs nothing until it is
used.

The example is a booking service for band rehearsal rooms, built from one
artifact — a patch bay. Sockets become the availability grid, gaffer-tape
labels become the annotation layer, and a drawn cable encodes booking
duration. It exists to show the method producing an entire system from a
single object: twelve references, three directions with two killed, tokens
whose base unit is the socket pitch, and a functionality check on every
distinctive decision.

## Licence

MIT.
