# Typography directions

Type carries more character than colour does, and it is the first thing to go
generic. The reason is availability: the neutral grotesques are one line away,
so they win by default rather than by decision.

What follows is material to choose *from*, with what each conveys. Check the
licence before shipping — Google Fonts and Fontshare families are free for
commercial use, the rest vary.

## Why the default is a default

Inter, Helvetica-likes and the system stack are drawn to disappear. That is a
real virtue in dense product UI where the type should not compete with the
data. It is a liability anywhere the interface itself has to say something,
because a face designed to be invisible cannot also be memorable.

Use a neutral grotesque when neutrality is the decision. Not when it is the
absence of one.

## Directions

**Editorial serif.** Authority, patience, a publication rather than an app.
Works when the product involves reading, judgement or archive.
*Fraunces* (variable, with optical-size and a `wonk` axis — unusually
characterful), *Newsreader*, *Source Serif 4*, *Spectral*, *Libre Caslon*,
*Instrument Serif* for display only.

**Geometric with a flaw.** Warmth without whimsy. The irregularity is what
keeps it from reading as a logo template.
*Bricolage Grotesque* (variable, with a width axis), *Cabinet Grotesk*,
*General Sans*.

**Industrial grotesque.** Engineered, blunt, no apology. Suits tools,
infrastructure, anything that should look load-bearing.
*Switzer*, *Public Sans*, *Archivo* (variable width), *Geist*.

**Monospace as a text face.** Not for code — for values, timestamps, IDs,
anything a person scans in a column. Tabular figures actually align, and a
mono next to a serif is an instant two-voice system.
*Commit Mono*, *JetBrains Mono*, *Martian Mono* (wide, more display than
text), *IBM Plex Mono*.

**Display-only oddity.** One face used at exactly one size for exactly one
purpose. High risk, high identity.
*Clash Display*, *Boska*, *Redaction*, *Instrument Serif*.

## Pairing

Two faces with different jobs beats three faces with overlapping ones. The
strongest cheap pairing is a serif for human copy and a mono for machine
values — they are so unalike that no hierarchy work is needed to tell them
apart, and each one's weakness is the other's strength.

A single family used across a wide weight and optical range is also a
complete answer. Two weights of one face is not a system; 300 to 900 with a
real size jump is.

## Variable axes

If the family has an optical-size axis, drive it from the rendered size. This
is the cheapest possible way to look considered: display cuts have tighter
apertures and finer joins, text cuts are drawn to survive at 14px, and
scaling one to do the other's job is exactly the flatness that reads as
generated.

Width axes are underused. A condensed cut for a long headline preserves the
size relationship you designed instead of forcing a smaller display size.

## Numbers that hold regardless of face

- Measure 45–75 characters. Wider is harder to read, not more generous.
- Line-height moves inversely with size. Roughly 1.5–1.65 for body,
  0.9–1.1 for display.
- Negative tracking on large sizes, normal to slightly positive on small.
  Most faces are spaced for text and go gappy scaled up.
- One real jump in the hierarchy usually beats four small ones, and display
  within 2× of body tends to read flat — but this is a warning, not a
  threshold. A deliberately close scale is a legitimate direction if the
  document says so and something else carries the hierarchy.
- Optical alignment over mathematical. Hanging punctuation and a slight
  negative indent on a large quote are not fussiness; without them the block
  visibly does not start where it should.

## Loading

Self-host or preload. `font-display: swap` with a metric-matched fallback, or
the page reflows on load and every carefully judged size is wrong for the
first 400ms — on a slow connection that is the only impression most visitors
get.
