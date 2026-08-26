# A Decent Conversation — illustration shot list

Reference doc for whoever produces L1–L5, H1–H3, F1, and F2. Written from the
site's own design tokens and copy voice (see `index.html`'s `<style>` block
and the "HOUSE STYLE" / "THE RULE THAT GOVERNS THIS SITE" comments at the top
of each page) — pull from the live CSS if any of this drifts out of date.

## The overall brief

**Subject.** Every piece is a moment from an ordinary Wednesday morning
around the table — never a portrait, never a specific person. The site's own
governing rule: *"This site describes the container, never its contents. No
comment threads, no member directory, no photos of the room."* That extends
to the art — figures are anonymous and unidentifiable on purpose, not just
as a style choice but as a hard constraint (real members haven't consented
to being drawn/depicted, only quoted anonymously in a few places on
`/history`). No faces, no likenesses, no identifying features.

**Point of view.** Figures are consistently shown from behind or from the
side/three-quarter at most — over-the-shoulder, seen from across or behind
the table. This is already established in the copy for H2 ("Generic figure,
no likeness") and should hold for the whole set, not just that one piece.

**Medium.** Line art, single consistent stroke weight throughout each piece,
no fill, no shading, no gradients. Economical — closer to a confident
gestural sketch than a detailed illustration. Think the restraint of a
single-line contour drawing, not clip art built from geometric primitives
(circles/arcs) — that reads as generic and cold, which is the opposite of
the vibe. The figures should feel observed, caught mid-gesture, slightly
imperfect — not measured and symmetrical.

**The table line.** The site treats every section break as a horizontal
rule (`.table-rule`) with the comment *"Every section break is a table, not
a divider."* Where a piece includes a table surface, rendering it as a
single clean horizontal line (echoing that same rule-line motif) ties the
illustrations back into the rest of the page rather than treating them as
separate decorative inserts.

**Color.** Single color (ink) by default — the CSS variable is literally
named for this: *"Drawings inherit currentColor."*

- Light mode ink: `#15181C` on ground `#DDE3E6`
- Dark mode ink: `#E7EBEC` on ground `#14181B`

Brass (`#8F6A15` light / `#D0A344` dark) exists in the system as "the low
sun, used sparingly" and is available as a rare one-spot accent if a
specific piece has an obvious single focal point that would benefit from it
— but the precedent set on L1 (the empty chair) was to skip it and keep the
whole set single-color. Default to no brass unless a piece really earns it.

**Diversity, without faces.** The copy repeatedly emphasizes that the group
spans "different ages, different career paths and stages, different
histories and backgrounds, different politics, different faiths" — and
since nobody's face is ever shown, that has to come through in build,
posture, hair, and silhouette rather than anything literal. Worth varying
figure proportions/posture across the set for this reason, not just for
visual rhythm.

**Tone.** From the HOUSE STYLE notes: *"Plain and dry beats earnest; the
page never explains its own significance."* Avoid anything that reads as
precious, sentimental, or overly symbolic. These are quick, dry sketches of
an ordinary morning, not emotional set-pieces.

**Technical delivery.** However these get produced, deliver **inline-SVG-
ready** artwork — `stroke="currentColor"`, `fill="none"`, no hardcoded
color. If delivering as standalone files rather than markup to paste inline,
provide **explicit separate light and dark exports** rather than relying on
an embedded `prefers-color-scheme` media query inside the SVG — that
doesn't reliably override `currentColor` across renderers/browsers (tested
and confirmed failing in at least one common SVG rasterizer). Inline SVG
embedded directly in the page is the more robust route and is what's
recommended.

---

## The pieces

### L1 — The Empty Chair
- **Where:** homepage hero, directly under the opening line
- **Aspect:** 16:7 (wide banner)
- **Brief:** Three or four figures mid-conversation, seen from behind, at a
  table. One seat pulled slightly out and unfilled, nearest the viewer —
  larger/closer than the seated figures, angled as though someone just got
  up or hasn't sat down yet. This is the site's masthead image; it needs to
  read instantly and hold up small.
- **Alt text on file:** "Four people talking around a table, with one chair
  pulled out and empty."

### L2 — The Listener
- **Where:** homepage, "What it is" section (paired with body copy)
- **Aspect:** 1:1 (square)
- **Brief:** A single figure, seen from behind, leaning slightly in —
  forearms suggested, attentive posture. Quiet, close-cropped, no other
  figures in frame.
- **Alt text on file:** "A person seen from behind, forearms on a table,
  leaning in to listen."

### L3 — Hands
- **Where:** homepage, "Where and when" section
- **Aspect:** 5:1 (very wide, shallow banner)
- **Brief:** Forearms and hands only, resting on the table line — no heads,
  no bodies. One hand mid-gesture. Reads almost abstract at this aspect
  ratio; the table line itself should be a strong horizontal anchor running
  the full width.
- **Alt text on file:** "Forearms and hands resting on a table, one
  mid-gesture."

### L5 — Arriving
- **Where:** homepage, "How you join" section
- **Aspect:** 2:3 (portrait)
- **Brief:** A figure standing at the edge of the frame, coat still on,
  about to sit down — the table and an already-occupied group visible
  beyond them, smaller/further back. Sense of just walking in, mid-arrival.
- **Alt text on file:** "A person standing at the edge of the frame, coat
  still on, about to sit down at an occupied table."

### H1 — Two at a Table, 2015
- **Where:** `/history`, "How it started" section
- **Aspect:** 3:2
- **Brief:** Two figures only, at a small table, with a lot of empty space
  around them — sparse, a little tentative. This is the founding moment
  (September 2015, first meeting), so it should feel notably smaller-scale
  and less settled than the later pieces (H3 especially).
- **Alt text on file:** "Two people at a small table with plenty of empty
  space around them."

### H2 — The Interruption
- **Where:** `/history`, "An undercover priest and an amateur rabbi..."
  section
- **Aspect:** 3:2
- **Brief:** A standing figure, leaning in, mid-question, at the edge of a
  table; the already-seated group turned up toward them. This depicts the
  moment Andy joined on the spot — generic figure, explicitly no likeness
  (per the page's own consent notes, this can't read as a portrait of any
  real person).
- **Alt text on file:** "A person standing at the edge of a table, leaning
  in to ask the seated group a question."

### H3 — The Full Table Now
- **Where:** `/history`, "The first decade did what decades do" section
- **Aspect:** 16:7 (wide banner, same ratio as L1 — the visual bookend/
  contrast to H1's sparse two-person table)
- **Brief:** A dozen-plus figures, the table line running the full width,
  abundant and slightly noisy — figures overlapping, a full and busy table.
  This is the "island of misfit toys" image; the point is scale and density
  contrasted against H1's near-empty table.
- **Alt text on file:** "A crowded table of many people, figures
  overlapping, mid-conversation."

### F1 — Favicon
- **Where:** browser tab icon, all pages (currently missing even a
  `<link rel="icon">` tag in the markup — that needs adding once this
  exists)
- **Aspect:** square, needs to work legibly at 16×16 and 32×32 px
- **Brief:** Not separately spec'd in the placeholder comments beyond "F1
  favicon" — needs its own simple mark. Given the site has no logo beyond
  the wordmark, options: a radically simplified version of the empty-chair
  motif from L1, or an abstracted single table-line-plus-seat glyph. Needs
  to survive being shrunk to 16px, so keep it to one or two strokes at
  most — most of the detail in any of the other pieces won't survive that
  scale.

### F2 — Social preview
- **Where:** `og:image` meta tag, all four pages (`/img/social-preview.png`)
- **Format:** 1200×630 PNG
- **Brief:** Per the comment already in `index.html`: **this is L1, cropped
  to 1200×630 and exported as a flat PNG** — not a separate commission.
  Produce it once L1 exists; no independent brief needed beyond making sure
  the crop still reads with the empty chair roughly centered/legible at
  link-preview thumbnail size.
