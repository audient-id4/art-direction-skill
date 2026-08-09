# Stack

The stack does not make a design good. Decisions do, and every technique in
this skill is reachable with plain HTML and modern CSS.

What the stack decides is **cost**. On the wrong one, the right version gets
expensive — springs, reduced-motion variants, optical font loading, container
queries, token traceability — and expensive work gets cut under deadline.
That is the actual failure path: not a stack that cannot do it, a stack where
doing it properly is enough friction that nobody does.

## Default

**Next.js (App Router) · React · TypeScript · Tailwind · Motion**

Each earns its place against something the skill demands.

**Next.js.** `next/font` self-hosts, preloads and generates a metric-matched
fallback, which is the typography chapter's no-layout-shift requirement
solved by configuration rather than by hand. `next/image` handles AVIF and
intrinsic sizing. Static export covers landings; server components cover
products. Routing exists so navigation can follow the mental model rather
than whatever was easy.

**Tailwind.** The real argument is not utility classes — it is that
`DESIGN-TOKENS.md` maps onto a theme one-to-one, so every value in the markup
is traceable *by construction*. Tailwind v4's `@theme` emits CSS custom
properties directly, which means the token file, the theme and the runtime
variables are the same three names. The audit line "values not traceable to
the document: 0" stops being an inspection and becomes a property of the
setup.

The cost: arbitrary values (`p-[13px]`) are an escape hatch that silently
undoes this. Allow them only where the document names the number.

**Motion** (the library formerly called Framer Motion; the package is now
`motion`, and `framer-motion` still resolves). Springs with real stiffness
and damping, layout animation, gesture state, and `useReducedMotion` as a
hook rather than a media query you remember to write. The skill asks for
springs on user-initiated motion and a static equivalent for every animation
— both are one line here and a small project in CSS.

**TypeScript.** Token names as a union type. A radius that is not in the
system fails to compile, which is a cheaper reviewer than a person.

## When the default is wrong

**A single static page, little interactivity.** Astro. Ships zero JavaScript
by default, islands where you need it, and the same Tailwind setup. A
marketing page that loads a React runtime to render text is paying for
nothing.

**One page, no state, no reuse.** Plain HTML and modern CSS is genuinely the
right answer, and faster to build. Do not reach for a framework to make a
business card feel serious.

**An existing codebase.** Work in what is there. A visual language does not
require a rewrite, and a rewrite proposed as a design task is a design task
that will not ship.

## What modern CSS already does

Reach for these before installing anything. Several are the *better* answer,
not just the lighter one.

- **Container queries** — components respond to their own width. This is what
  "responsive art direction" actually needs; viewport breakpoints cannot
  express a card that is wide in one slot and narrow in another.
- **`:has()`** — parent and sibling selection. Removes most of the state
  JavaScript written to toggle a class on an ancestor.
- **View Transitions** — spatial transitions between states and pages, with
  the shared-element behaviour that used to need a layout-animation library.
- **Scroll-driven animations** (`animation-timeline`) — no scroll listener, no
  jank, degrades to nothing where unsupported.
- **`@property`** — typed custom properties, which makes gradients, angles and
  colour stops animatable at all.
- **`text-wrap: balance` / `pretty`** — headline ragging and orphan control.
  Small, and directly visible in exactly the display type this skill spends
  its typography chapter on.
- **`clamp()`** — fluid type and space between stated bounds, so the scale in
  the token file survives every viewport instead of stepping at breakpoints.
- **`color-mix()` and oklch** — derive tints, shades and neutrals from the
  accent in perceptual space. This is how a palette stays on one hue instead
  of drifting grey.
- **Subgrid** — real alignment across component boundaries, which is what
  editorial layouts need and flexbox cannot do.
- **Anchor positioning** and the **popover** attribute — tooltips and menus
  without a positioning library.

## Component libraries

Do not build a distinctive design on a styled component library. shadcn/ui is
on the contamination list for a reason: adopting its vocabulary and then
trying to escape its look is backwards, and the escape is never complete.

Use **unstyled primitives** where accessibility is hard and unrewarding to
redo — dialogs, comboboxes, menus, date pickers, focus traps. Radix UI, Base
UI or React Aria give you keyboard behaviour, ARIA wiring and focus
management with no opinion about appearance. That is the trade worth making:
borrow the parts nobody sees, own every part they do.

Everything visible — buttons, cards, inputs, layout — you write. It is less
work than it sounds and it is the entire difference.

## Build rules

**One source of tokens.** `DESIGN-TOKENS.md` → theme config → CSS variables.
Never a value in a component that does not exist upstream.

**One motion module.** Export the durations, curves and spring configs from a
single file, named to match the token file. Ad-hoc `transition-all
duration-300` scattered through components is how a motion language becomes
noise.

**`useReducedMotion` at the root**, with each animation's static equivalent
defined where the animation is defined — not as a global override that
disables everything and loses information the motion was carrying.

**Fonts before anything else.** Wrong font metrics make every size judgement
in the design invalid for the first paint, and that first paint is what a
visitor on a slow connection sees.

**Animate transform and opacity.** Anything else repaints. Blur is expensive;
use it deliberately and never on a large scrolling surface.

## By project type

| Building | Stack |
|---|---|
| Landing page, static | Astro + Tailwind, or Next.js static export |
| Marketing site with a CMS | Next.js App Router + Tailwind + Motion |
| Product UI, dashboard | Next.js + Tailwind + Motion + unstyled primitives |
| One page, no state | HTML + modern CSS |
| Existing codebase | Whatever is already there |

Whatever the stack, the documents bind. The audit in pass 5 does not care
what rendered the pixels.
