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

**A binding artifact.** Pass 1 writes `ART-DIRECTION.md` to disk before any
component exists. Pass 2 must trace every value back to it. Pass 3 audits
against it. Without a written document, a concept evaporates the first time
implementation gets difficult, and the critique pass has nothing to judge.

**An audit you can actually run.** "Does this look AI-generated?" is not a
question anyone answers honestly about their own work. So the checks are
countable: distinct radius values, percentage of sections that are cards,
display-to-body ratio, gradient count, values not traceable to the document.

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
SKILL.md                          the process — three passes, rules, audit
templates/ART-DIRECTION.md        the artifact pass 1 fills in
examples/ART-DIRECTION.example.md a completed one, worked end to end
reference/typography.md           type directions and what each conveys
reference/escapes.md              replacements for the patterns worth avoiding
```

`SKILL.md` loads when the skill is invoked. The reference files load only
when something in them is needed, so the depth costs nothing until it is
used.

The example is a booking service for band rehearsal rooms, built from one
artifact — a patch bay. It exists to show the method producing a whole system
from a single object, including the rejection log and the functionality
check.

## Licence

MIT.
