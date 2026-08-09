# UX direction — <project>

Written before any screen. Upstream of `ART-DIRECTION.md`: the priorities set
here are what the visual system has to express.

---

## 1. User

Who, and what they already know. Not a persona with a name and a hobby —
what they can be assumed to understand, and what they cannot.

> 

## 2. Goal

What they came to accomplish.

> 

## 3. Moment of value

The point where the product has paid for the effort of opening it.

> 

## 4. Immediate understanding

What must be clear before anything is read.

> 

## 5. Decisions required

Every choice the interface forces. Each one is a cost.

> 

## 6. Deferrable

What can stay hidden until asked for.

> 

## 7. Response

How the product answers being used.

> 

---

## Mental model

The model this should build in someone's head. Describe how they think, not
what is on screen.

**Test: it must forbid something.** State what structure it rules out. A
model that permits every architecture has decided nothing.

> Model:

> Therefore ruled out:

---

## Goal hierarchy

| Level | What |
|---|---|
| Primary |  |
| Supporting |  |
| Secondary |  |
| Noise (deliberately absent) |  |

Visual weight follows this order. Handed to `art-direction` as a constraint.

---

## First ten seconds

What is this / why it matters / what can I do / what first — answerable
without help?

> 

## Journey

| Horizon | What happens |
|---|---|
| 10 seconds |  |
| First minute (a completed action) |  |
| First session (reason to return) |  |
| Long term (how it changes) |  |

---

## Architecture

What belongs together, from the user's expectation rather than the data
shape.

> 

## Disclosure

| Layer | Contains |
|---|---|
| Default |  |
| Advanced |  |
| Expert |  |

## Interaction language

One of: precise · calm · creative · technical. And what that means here.

> 

---

## States

| Surface | Empty | Loading | Error | Success |
|---|---|---|---|---|
|  |  |  |  |  |

Every empty state names a next action. Every error names what happened, why,
what to do, and what is still safe.

---

## Destructive actions

| Action | Protection | Adjacent to |
|---|---|---|
|  |  |  |

---

## Constraints for visual design

What `art-direction` must satisfy. Not suggestions.

- Dominant on first screen:
- Reachable in one step:
- Legible at a glance:
- Never adjacent:

---

## Validation

| Check | Target | Measured |
|---|---|---|
| Clicks to primary value |  |  |
| Decisions before first success |  |  |
| Errors with recovery path | 100% |  |
| Empty states with next action | 100% |  |
| Destructive actions protected | 100% |  |
| Core task without instruction | yes |  |
| Keyboard-reachable interactives | 100% |  |
| Actions with no feedback | 0 |  |
