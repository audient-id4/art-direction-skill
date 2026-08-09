---
name: ux-direction
description: Define how a product behaves before designing what it looks like — user intent, mental model, flows, decisions, feedback, empty and error states. Use when building an app, dashboard, tool or any interface with flows, forms or state, and whenever a design risks being visually good and behaviourally thoughtless. Writes UX-DIRECTION.md before any screen.
---

# UX direction

Visual quality without experience quality is decoration. An interface that
looks considered and does not understand what the person came to do has
failed at the only job it had.

The goal is not interactions that impress. It is a product that feels
inevitable — where the next step is obvious because the system already
understood the intent.

## Dependency

This skill defines **behaviour and experience**. It does not decide
typography, colour, geometry or visual style.

If `ART-DIRECTION.md` exists, respect it — work inside the visual language
already chosen rather than around it.

If it does not, define the functional requirements the visual design must
satisfy: what has to be dominant, what has to be reachable in one step, what
has to be legible at a glance, what must never be adjacent to a destructive
action. Hand those to `art-direction` as constraints, not as suggestions.

## UX is not UI

Do not start from pages, components, buttons, cards or a navigation bar.
Start from intent, mental model, workflow, information hierarchy and
emotional state.

A component is a solution. The problem comes first, and most interfaces are
assembled out of solutions to problems nobody stated.

## The three passes

**Pass 1 — Understand.** Who, what for, what matters. Write `UX-DIRECTION.md`.
**Pass 2 — Structure.** Flows, architecture, disclosure, decisions, states.
**Pass 3 — Validate.** Countable checks, then fix.

Template: `templates/UX-DIRECTION.md`. Worked example in `examples/`.

---

## Pass 1 — Understand

### Who, and what they are trying to do

Answer these in the document, plainly:

1. Who is the user?
2. What are they trying to accomplish?
3. What is the main moment of value — the point where the product has paid
   for the effort of opening it?
4. What must they understand immediately?
5. What decisions do they have to make?
6. What can stay hidden until needed?
7. How does the product respond to them?

### Mental model

Define the model the product should build in someone's head — not the
objects on screen.

The test of a mental model is that it **forbids something**. A model that
only sounds evocative constrains no decision and will not survive contact
with a deadline.

*Weak:* "The user clicks a card to open a memory."
Describes the interface. Says nothing about how anything should be arranged.

*Weak in the other direction:* "The user enters an archive and discovers
preserved fragments of their life."
Sounds like a mission statement. Still permits every possible structure.

*Strong:* "The user thinks in **sessions**, not files. What they saved on one
evening belongs together, and a thing pulled out of its evening loses most of
its meaning."
This forbids a flat searchable list as the primary view. It requires time to
be the top-level axis, makes 'recently added' the default sort, and makes a
tag-first architecture wrong. A model you can violate is a model that decides
something.

If the mental model conflicts with the product's structure, change the
structure. The model is what people actually hold; the structure is
negotiable.

### Goal hierarchy

- **Primary goal** — the one thing people came to do.
- **Supporting** — actions that serve the primary goal.
- **Secondary** — useful, not essential.
- **Noise** — everything competing for attention that earns none.

Visual weight follows this order, and unequal actions never get equal weight.
Two buttons of identical size and colour tell the eye the choice does not
matter — if that is untrue, the interface is lying about its own priorities.

### The first ten seconds

A first-time user should be able to answer, without help: what is this, why
does it matter, what can I do, what should I do first.

If answering needs documentation or a tour, the interface failed and the tour
is a patch over the failure. Teach through use.

### The journey

Design moments, not pages.

- **First ten seconds** — what is noticed.
- **First minute** — the first meaningful action that can be *completed*.
- **First session** — the reason to come back.
- **Long term** — how the relationship changes as the person's collection,
  history or skill grows.

---

## Pass 2 — Structure

### Information architecture

Organise around what people expect to find together, not around the shape of
the data. "The API has these objects, therefore the UI has these sections" is
the most common cause of navigation nobody can predict.

### Progressive disclosure

Three layers: the simplest useful **default**, an **advanced** layer for when
more power is wanted, and **expert** control that never intrudes on the first
two.

Hide complexity. Do not remove capability. An interface that exposes
everything is not powerful, it is unsorted.

### Decision design

For every decision the interface asks someone to make:

- What do they need to know to decide?
- What are the options?
- Which is recommended, and does the interface say so?
- What happens after choosing?
- Can it be undone?

Then remove the decisions that did not need to exist. A confident interface
removes hesitation; most hesitation is a decision that should have had a
default.

### Interaction language

Pick one behavioural personality and hold it:

- **Precise** — fast response, explicit states, minimal animation.
- **Calm** — slow reveals, soft transitions, generous space.
- **Creative** — direct manipulation, playful feedback, exploration.
- **Technical** — explicit states, detailed feedback, powerful controls.

Mixed interaction styles read as assembled by different people, because
that is usually what happened.

### Feedback

Every action needs an answer. For each interaction define what is expected
**before**, what confirms progress **during**, what confirms success
**after**, and what explains recovery **on failure**.

Nobody should ever have to ask whether it worked.

### Loading

Loading is part of the experience, not a gap in it. Match the treatment to
the wait: instant transition; a subtle state change for a short wait; real
explanation or useful context for a long one.

No spinner farms, no blank screens, no fake progress bars. A fake progress
bar is a small lie that trains people to distrust the honest ones.

### Empty states

An empty state is a first interaction, not a placeholder. Each one answers:
why is this empty, what can be done, and why it is worth doing.

*Bad:* "No items found."
*Good:* "This archive is empty. Save your first memory to start the
collection."

### Errors

Errors are where trust is decided. Every error says what happened, why, and
what to do next.

*Never:* "Something went wrong."
*Prefer:* "The upload stopped because the file is over 2 GB. Your original
file is untouched — try again with a smaller export."

Naming what is *safe* matters as much as naming what failed.

### Navigation

Navigation is a map of the mental model, not a list of pages. What is needed
often, what can disappear, what deserves permanent presence, what deserves to
be remembered between sessions.

Never add navigation because applications usually have some.

### Forms

Forms are conversations. For every field: why is this needed, can the system
infer it, can it be asked later, and how does validation behave — on blur, on
submit, and what it says when it fails.

Every field removed is a measurable increase in completion.

### Mobile

Not desktop compressed. Re-decide priorities, navigation, interaction,
density and gestures.

The useful question: what is the one-handed version of this experience?

### Accessibility

Part of the experience, not a checklist at the end: keyboard navigation,
visible focus, readable contrast, reduced-motion support, semantic structure,
meaning that survives a screen reader.

An interface some people cannot use is unfinished, not "accessible later".

---

## Pass 3 — Validate

### Countable checks

"Is it clear to a first-time user?" is not a question anyone answers honestly
about their own work. These are answerable:

| Check | Target |
|---|---|
| Clicks from landing to primary value | as few as the task allows — state the number |
| Decisions required before first success | 0 unless the task genuinely needs one |
| Errors with a stated recovery path | 100% |
| Empty states with a next action | 100% |
| Destructive actions with undo or confirmation | 100% |
| Destructive action adjacent to a common one | 0 |
| Core task completable with no instruction | yes |
| Interactive elements reachable by keyboard | 100% |
| Actions with no feedback | 0 |

Write the numbers down. A target you did not measure is an opinion.

### The six qualities

- **Clarity** — can a first-timer understand the product?
- **Confidence** — does every action answer?
- **Efficiency** — is the goal reachable without unnecessary steps?
- **Recovery** — can mistakes be undone?
- **Memory** — will someone remember how it works next week?
- **Emotion** — does the interaction feel right for what this is?

### Anti-pattern audit

Reject: dashboards with no purpose; menus where everything has equal weight;
onboarding that exists because the interface is unclear; hidden primary
actions; decorative animation; confirmation dialogs on obvious actions; empty
states with no guidance; errors with no recovery; settings exposed before
anyone needs them.

---

## The rule underneath all of it

The best interface does not demonstrate how powerful it is. It makes
difficult things feel obvious.

The question is not how many capabilities can be exposed. It is how little
effort can produce meaningful progress.

A product is not a collection of screens. It is a designed relationship
between a person and a system, and every screen is just where that
relationship happens to be visible.
