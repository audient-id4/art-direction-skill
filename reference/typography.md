# Typography

Typography is not a styling choice. It is the voice of the product, and it
carries more of the character than colour does.

A typeface is correct only when it reinforces the metaphor in
`ART-DIRECTION.md`. Never choose one because it is popular, because it turns
up in modern SaaS products, because a framework ships it, or because it looks
clean in isolation. Clean in isolation is what every neutral grotesque is for.

## The questions

- Mechanical or human?
- Historical or futuristic?
- Precise or expressive?
- Quiet or authoritative?
- Dense or spacious?
- Editorial or functional?

The answers should already be implied by the artifact. If they are not, the
concept is thinner than it looked.

## Why the default is a default

Inter, the Helvetica-likes and the system stack are drawn to disappear. In
dense product UI, where type must not compete with data, that is a real
virtue and the right answer. It is a liability anywhere the interface itself
has to say something, because a face designed to be invisible cannot also be
memorable.

Use a neutral grotesque when neutrality is the decision. Not when it is the
absence of one.

## Decision process

**1. Identify the role.** Display and identity / reading and body /
interface and utility / data and technical.

**2. Decide the personality.** Neutral / warm / technical / editorial /
luxurious / experimental.

**3. Choose the smallest system that works.** One display family plus one
text family. Add a mono only when the concept genuinely carries technical
information — values, times, IDs, code. A third face with no distinct job
dissolves the identity rather than enriching it.

Two faces with different jobs beats three with overlapping ones. The
strongest cheap pairing is a serif for human copy and a mono for machine
values: so unalike that no hierarchy work is needed to tell them apart, and
each one's weakness is the other's strength.

A single family across a wide weight and optical range is also a complete
answer. Two weights of one face is not a system; 300 to 900 with a real size
jump is.

---

## Reference directions

The named references are the canonical faces for each direction — worth
knowing even when the budget will not reach them, because they define what
the category *is*. Beside each, free families that hit the same brief.

Licensing reality: almost every reference face below is commercial, and web
licences are sold separately from desktop ones, usually priced by traffic. A
desktop licence does not permit self-hosting a webfont. See **Licensing**
below before shipping any of them.

### Editorial / archival / cultural

Humanist forms, strong stroke contrast, a literary feeling. For products
involving reading, judgement, archive or authorship.

*References:* Canela · Tiempos · Lyon · Noe Display · Ivar

*Free equivalents:*
- **Fraunces** — variable, with optical-size and a `wonk` axis. The most
  characterful free serif available; the closest thing to a Canela-grade
  display voice at zero cost.
- **Newsreader** — a Tiempos-adjacent text face, drawn for screen reading.
- **Source Serif 4** — variable, quieter, excellent at body sizes.
- **Spectral** — warmer, slightly more literary than Source Serif.
- **Instrument Serif** — display only, high contrast, no text cut. Pair with
  a separate body face.
- **Gambetta** (Fontshare) — calligraphic contrast, closer to Lyon's warmth.

### Precision / engineering / tools

Controlled shapes, neutral voice, high information density. For anything that
should read as load-bearing.

*References:* Neue Haas Grotesk · Söhne · Graphik · GT America · ABC Diatype

*Free equivalents:*
- **Switzer** (Fontshare) — the closest free thing to Söhne's temperature.
- **General Sans** (Fontshare) — Graphik-adjacent, slightly warmer.
- **Public Sans** — variable, institutional, drawn for exactly this.
- **Geist** — geometric, tight, technical.
- **Archivo** — variable width, which matters: a condensed cut lets a long
  headline keep the size relationship you designed.
- **Inter** — legitimately belongs in this category. Using it *here*, on
  purpose, is different from using it everywhere by default.

### Digital / futuristic / experimental

Unusual geometry, technical personality, strong display character.

*References:* PP Neue Machina · Whyte · Druk · Space Grotesk ·
Departure Mono

*Free equivalents:*
- **Space Grotesk** — already free.
- **Departure Mono** — already free. Pixel-grid mono, very specific voice.
- **Clash Display** (Fontshare) — condensed and heavy, the free answer to
  Druk's poster weight.
- **Chillax** (Fontshare) — soft geometric, Whyte-adjacent.
- **Bricolage Grotesque** — variable width and optical size, deliberately
  irregular. Its flaws are the point.
- **Martian Mono** — wide mono, more display than text.

### Luxury / premium

Restraint, elegance, slow confidence. The hardest direction to reach with
free faces, and worth saying plainly: this category is where paid type
actually earns its price. High-contrast serifs need careful drawing at every
weight, and the free options thin out fast.

*References:* Optimo's catalogue · Editorial New · Saol · Noe

*Free equivalents:*
- **Bodoni Moda** — variable with an optical-size axis, genuinely good at
  display sizes.
- **Prata** — single weight, high contrast, quiet.
- **Boska** (Fontshare) — display serif with real restraint.
- **Playfair Display** — variable and capable, but so widely used that it now
  reads as a template signal. Only with a reason.

If a project's whole identity rests on this direction, price a licence into
the work rather than approximating it. An approximated luxury serif does not
read as restrained; it reads as cheap, which is the one thing the direction
cannot survive.

---

## Variable axes

If the family has an optical-size axis, drive it from the rendered size. This
is the cheapest possible way to look considered: display cuts have tighter
apertures and finer joins, text cuts are drawn to survive at 14px, and
scaling one to do the other's job produces exactly the flatness that reads as
generated.

Width axes are underused. Reach for a condensed cut before shrinking a
headline.

## Numbers that hold regardless of face

- Measure 45–75 characters for body copy. Wider is harder to read, not more
  generous.
- Line-height moves inversely with size. Roughly 1.5–1.65 for body,
  0.9–1.1 for display.
- Negative tracking on large sizes, normal to slightly positive on small.
  Most faces are spaced for text and go gappy scaled up.
- One real jump in the hierarchy usually beats four small ones, and display
  within 2× of body tends to read flat — a warning, not a threshold. A
  deliberately close scale is legitimate if the document says so and
  something else carries the hierarchy.
- Weights carry hierarchy, not decoration. A weight used once, for emphasis,
  in one place, is a system. Four weights scattered is noise.
- Optical alignment over mathematical. Hanging punctuation and a slight
  negative indent on a large quote are not fussiness; without them the block
  visibly does not start where it should.

## Licensing

The most common way a client site acquires a legal problem is a webfont
downloaded from a free-fonts aggregator that had no right to distribute it.
The second most common is self-hosting a face the studio owns a *desktop*
licence for.

- **Google Fonts** (OFL / Apache) — free for commercial use, self-hostable.
- **Fontshare** (Indian Type Foundry) — free for commercial use, including
  webfonts. Satoshi, Switzer, General Sans, Clash Display, Cabinet Grotesk,
  Gambetta, Boska, Chillax.
- **Retail foundries** — Klim, Commercial Type, Grilli, Pangram Pangram,
  Colophon, Dinamo, ABC Dinamo. Web licences are separate from desktop and
  typically tiered by monthly pageviews. Read the tier before quoting a
  client.

If a paid face is the right answer, put it in the estimate. It is a smaller
line item than the hours spent approximating it badly.

## Loading

Self-host and preload, or use `font-display: swap` with a metric-matched
fallback. Otherwise the page reflows on load and every carefully judged size
is wrong for the first several hundred milliseconds — which, on a slow
connection, is the only impression most visitors get.

---

## Typography audit

- Is the choice explained in `ART-DIRECTION.md`?
- Are display and body roles clearly separated?
- Is the measure readable?
- Is tracking intentional at every size, or inherited?
- Do weights carry hierarchy rather than decorate?
- Is there a third family with no distinct job?

Then the one that decides it:

> **Swap the display face for a plain system font. If the identity survives
> unharmed, the typography decision was never strong enough.**

This is not an argument for exotic type. It is a test of whether type was
doing work. A design whose character is entirely in its layout and colour can
pass every other check here and still have no voice.

## On Apple

Do not reach for SF Pro to get an Apple-like result. Apple's typography is
strong because of hierarchy, spacing, restraint and optical judgement — the
face is the smallest part of it, and it is the only part that transfers by
copying. Take the discipline, not the font.
