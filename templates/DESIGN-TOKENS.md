# Design tokens — <project>

Written after the direction is chosen (pass 1.5), before any component.
Every value in the build traces back here; anything that cannot is a default
that slipped in.

Each token carries its **role**, not just its number. A value with no stated
job is a value nobody can argue with later.

---

## Type

| Scale | Size | Line-height | Tracking | Face / weight | Role |
|---|---|---|---|---|---|
| Display |  |  |  |  |  |
| Text |  |  |  |  |  |
| Label |  |  |  |  |  |
| Mono |  |  |  |  |  |

Measure (body): ___ch
Hierarchy: what the display-to-text relationship is doing, and why that gap
and not another.

> 

## Space

Base unit: ___ — and where it came from. A unit derived from something in
the design (the type size, a grid pitch, a component's height) holds up
better than one picked because it is round.

| Step | Value | Used for |
|---|---|---|
|  |  |  |

**Density rules** — what is tight, what is loose, and the rule that decides.

> 

**Section rhythm** — the vertical intervals down the page, and where the
composition deliberately breaks them.

> 

## Geometry

Two to five radii. Every one needs a role; if two share a role, they are one
radius written twice.

| Token | Value | Role |
|---|---|---|
| Small |  |  |
| Medium |  |  |
| Large |  |  |
| Container |  |  |

Nesting rule: `inner = outer − padding`, wherever radii nest.
Sharp corners: where, and what they signal.

> 

## Motion

| Token | Duration | Curve | Used for |
|---|---|---|---|
| Fast |  |  |  |
| Normal |  |  |  |
| Slow |  |  |  |

Springs: stiffness / damping / mass, and which interactions get them.
Rule of thumb — springs for user-initiated motion, eased curves for
system-initiated.

> 

Reduced-motion equivalents: what each becomes. If information lives only in
an animation, the animation is load-bearing and needs a static form.

> 

## Colour

| Token | Value | Contrast on ground | Role |
|---|---|---|---|
| Background |  | — |  |
| Surface |  |  |  |
| Text primary |  |  |  |
| Text secondary |  |  |  |
| Text tertiary |  |  |  |
| Accent |  |  |  |
| Success |  |  |  |
| Warning |  |  |  |
| Danger |  |  |  |

Neutrals: derived from which hue? Pure grey next to a warm accent reads as
unfinished.

> 

The accent marks exactly what? An accent used on more than one kind of thing
stops carrying meaning.

> 

Gradients: none, or exactly one — and what it is doing.

> 

---

## Floors

Checked, not assumed:

- [ ] Body text ≥ 4.5:1, large text ≥ 3:1 — measured
- [ ] Every motion token has a reduced-motion equivalent
- [ ] Focus state defined for every interactive token
- [ ] Touch targets ≥ 44px, or ≥ 24px with spacing
