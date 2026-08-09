# UX direction — Backline

A booking service for band rehearsal rooms. Same project as the
`art-direction` example, written first — the priorities here are what that
visual system was built to express.

---

## 1. User

Someone in a band, usually the one who ended up organising things because
nobody else would. They know rehearsal rooms: what a backline is, that the
good room goes first, that the drummer will be late. They do not want to
learn a product.

Booking happens on a phone, often in a group chat, often at night, usually
after someone has said "who's free Thursday".

## 2. Goal

Get a room, at an hour the band can all make, before someone else takes it.

## 3. Moment of value

Seeing that Thursday 7pm is free at the room they like — before booking, not
after. The booking is admin; the *answer* is the product.

## 4. Immediate understanding

What is free, when, and where. Nothing else competes for the first screen.

## 5. Decisions required

Which room and which hours. That is all. Everything else — deposit, gear,
access code — is either inferred, deferred to confirmation, or already known
from the last booking.

## 6. Deferrable

Account creation, payment details, room specifications, cancellation policy,
gear inventory. None of it belongs before the hour is held.

## 7. Response

Immediate and physical. Selecting hours should feel like taking them, not
like filling a form that will be validated later.

---

## Mental model

**Model:** people think in *a night*, not in a calendar. "Thursday evening"
is one object — a block of two to four hours in one room with the same people
— and splitting it into hour rows the way a booking system does breaks the
thing they are actually arranging.

**Therefore ruled out:**
- A month calendar as the primary view. A month is the wrong grain; nobody
  books a rehearsal four weeks out, and the view hides the only thing that
  matters, which hours are contiguous.
- Booking one hour at a time with a confirmation each. The unit is the block.
- Sorting rooms by price. Bands return to the room they know; price is a
  tiebreaker, not a sort key.
- Any flow where you pick a date first and then discover the room is taken.
  Availability has to be visible before commitment, or the product is a
  series of rejections.

This model is why the interface is a dense grid of contiguous hours rather
than a calendar, and why a booking is drawn as one continuous object.

---

## Goal hierarchy

| Level | What |
|---|---|
| Primary | See what is free and take it |
| Supporting | Compare two rooms on the same night; see the last booking to repeat it |
| Secondary | Change or cancel; add gear; invite the band |
| Noise (deliberately absent) | Studio marketing copy, room photo galleries, reviews, a blog, an account dashboard |

## First ten seconds

Answerable without help. The grid is the entire explanation: rooms down the
side, hours across, filled means gone. Nobody has to be told what an empty
socket means once they have seen a full one beside it.

## Journey

| Horizon | What happens |
|---|---|
| 10 seconds | Sees this week's availability across every room, without logging in |
| First minute | Holds a block. Account is created from a phone number *after* the hours are reserved, on a 10-minute timer |
| First session | Comes back to check whether the drummer confirmed — the booking link shows who has seen it |
| Long term | The rooms they use rise to the top; "same as last time" becomes a one-tap booking |

---

## Architecture

Grouped by night, then by room — which is how a band talks about it. Not by
studio, not by room type, not by the shape of the availability table
underneath.

## Disclosure

| Layer | Contains |
|---|---|
| Default | The grid. Rooms, hours, free or gone |
| Advanced | Gear requests, recurring slots, splitting the cost across the band |
| Expert | Studio-side: pricing rules, blackout dates, deposit policy |

## Interaction language

**Precise.** Fast, definite, minimal animation. Motion only where it explains
a state change — the socket filling, the cable drawing on confirmation.
Nothing fades in on scroll. A person choosing hours at midnight in a group
chat wants the interface to keep up, not to perform.

---

## States

| Surface | Empty | Loading | Error | Success |
|---|---|---|---|---|
| Availability grid | "No rooms free this week. Next opening: Tuesday 6pm — show that week" | Skeleton grid at real dimensions, no spinner | "Couldn't reach the studio's calendar. Showing last night's data from 11:42pm — refresh before you book" | Grid renders; free hours are the only coloured thing |
| A booking | "No bookings yet. Take a block above and it appears here" | — | "That hour was taken 40 seconds ago. The rest of your block is still held for 9 minutes" | Cable drawn between first and last hour |
| Band invite | "Nobody invited yet. Send the link — they don't need an account to see it" | — | "That number didn't accept the message. The booking is unaffected" | Avatars fill as people view |

The grid error is the one that matters most: it says what broke, how stale
the data is, and does not pretend the booking is safe when it might not be.

---

## Destructive actions

| Action | Protection | Adjacent to |
|---|---|---|
| Cancel a booking | Undo for 60s, no dialog. Refund state stated before the tap | Nothing. Lives inside the booking detail, not on the grid |
| Release one hour of a block | Undo for 60s | The block itself — low stakes, easily reversed |
| Delete account | Typed confirmation, 30-day recovery | Nothing. Buried in settings, as it should be |

No confirmation dialog on cancel. A dialog on an action with a working undo
is friction that trains people to click through dialogs.

---

## Constraints for visual design

- **Dominant on first screen:** the availability grid. Not a logo, not a
  headline, not a photograph of a band.
- **Reachable in one step:** taking a block, from any entry point.
- **Legible at a glance:** free versus gone, from across a room, on a phone
  at arm's length in bad light.
- **Never adjacent:** cancel and book.

*(These became the socket grid, the single sodium accent reserved for
availability, and the decision to keep cancellation off the grid entirely.)*

---

## Validation

| Check | Target | Measured |
|---|---|---|
| Clicks to primary value | 0 — availability is the landing page | 0 |
| Decisions before first success | 2: room, hours | 2 |
| Errors with recovery path | 100% | 100% |
| Empty states with next action | 100% | 100% |
| Destructive actions protected | 100% | 100% (undo, not dialogs) |
| Core task without instruction | yes | yes — tested on three people who book rooms |
| Keyboard-reachable interactives | 100% | 100%; the grid is arrow-navigable |
| Actions with no feedback | 0 | 0 |
