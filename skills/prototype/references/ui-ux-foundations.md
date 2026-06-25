# UI/UX foundations — the rigor pack for `prototype`

Load this before designing. It is the quality bar every prototype meets, in any output mode
(HTML, Figma, iso-prod). Project tokens and conventions always win over the generic defaults here.

---

## 1 · The 4px grid + Tailwind scale

Every spacing, sizing, and radius value is a multiple of **4px**, on the Tailwind scale:

`4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 96` (px) — i.e. Tailwind `1 / 2 / 3 / 4 / 6 / 8 / 12 / 16 / 24`.

- **Project tokens win.** If the repo defines spacing tokens, use them; the grid is only the fallback
  when you compose a value the tokens don't cover.
- **Never an off-grid value.** No `13px`, no `padding: 17px`, no `gap: 10px`. If you're reaching for
  one, you're guessing — snap to the nearest step.
- **Type scale is intentional too.** Use the repo's type tokens/steps; don't invent `15.5px`.
- **One spacing rhythm per screen.** Pick a base step (often 4 or 8) and stay consistent; related
  things share a gap, unrelated things get a bigger one.

## 2 · Component sizing & consistency

- **Reuse the repo's real sizes.** Control heights (button / input / select), icon sizes, avatar
  sizes, radii, border widths — take them from the real components, don't redraw them.
- **One canonical component per role.** Don't place a one-off next to the real `Button`; don't build
  a `Tag` that's just a coloured `Badge`. Compose from primitives or flag a genuinely new component.
- **Same control = same size, everywhere.** All primary buttons are the same height; all body text
  is the same size; all cards share the same radius and padding. Inconsistency reads as "unfinished".
- **Touch targets ≥ 44px** for anything tappable (Fitts, below).
- **Align everything.** Shared left edge, shared baseline, consistent gutters. Misalignment is the
  fastest way a prototype looks "off".

## 3 · Information hierarchy

The viewer's eye should land on the most important thing first, then flow in priority order.

- **One primary action per screen.** Exactly one. Everything else is secondary / tertiary / ghost.
- **Rank with four levers, in order:** size → weight → colour → space. Reach for size and weight
  before colour; use colour sparingly so the accent actually means "act here".
- **Group with proximity and whitespace.** Things that belong together sit close; whitespace is the
  cheapest, strongest grouping tool. Don't box everything; let space do the work.
- **Establish a clear reading path.** Title → context → primary content → action. Don't make two
  things compete for "most important".
- **Progressive disclosure.** Show what's needed now; tuck advanced/rare options behind a step, a
  toggle, or a panel (Tesler, below). A long title goes in the body, not a cramped header.

## 4 · Laws of UX

Apply the ones relevant to the screen. Full reference: https://lawsofux.com

- **Hick's Law** — decision time grows with the number/complexity of choices. *Apply:* fewer options
  per screen; one primary action; break long forms into steps; sane defaults.
- **Fitts's Law** — time to hit a target depends on its size and distance. *Apply:* big, close,
  reachable targets for primary actions; ≥44px touch targets; don't strand the key button.
- **Jakob's Law** — users expect your product to work like the others they know. *Apply:* match
  platform/web conventions (nav placement, icons, patterns); innovate on value, not on the back
  button.
- **Miller's Law** — people hold ~7 (±2) chunks in working memory. *Apply:* chunk content; group nav;
  don't show 20 ungrouped items.
- **Law of Proximity** — things near each other are perceived as related. *Apply:* spacing encodes
  grouping; tighten within a group, loosen between groups.
- **Law of Similarity** — similar-looking elements are perceived as related. *Apply:* consistent
  styling for same-type items; different styling signals different function.
- **Law of Common Region** — elements in a shared boundary are grouped. *Apply:* use a card/panel to
  bind a group, but prefer whitespace first; don't over-box.
- **Von Restorff (isolation effect)** — the item that differs is remembered. *Apply:* make the one
  primary action visually distinct; don't dilute it with competing emphasis.
- **Aesthetic–Usability effect** — polished UIs are perceived as more usable (and forgive small
  flaws). *Apply:* spacing, alignment, and type consistency are not decoration; they buy trust.
- **Doherty Threshold** — keep system feedback under ~400ms to hold attention. *Apply:* instant
  hover/press feedback; optimistic UI; skeletons over spinners for known shapes.
- **Tesler's Law (conservation of complexity)** — some complexity is irreducible; decide who absorbs
  it. *Apply:* the product absorbs it (smart defaults, progressive disclosure), not the user.
- **Serial Position effect** — first and last items are remembered best. *Apply:* put the most
  important nav/actions at the start or end, not buried in the middle.
- **Peak–End rule** — people judge an experience by its peak and its end. *Apply:* nail the key
  moment and the final state (success, empty-done, confirmation).

## 5 · States & accessibility (don't skip)

- **Every screen handles the 5 states:** empty, loading, error, partial, ideal. A prototype that only
  shows the happy path is half a prototype.
- **Loading:** skeletons for known shapes, spinners only for indeterminate waits.
- **Accessibility:** full keyboard path, visible focus rings, correct ARIA roles/labels, sufficient
  contrast, ≥44px touch targets. Visible labels over placeholder-only fields.

---

**In one line:** snap to the 4px grid, reuse the real component sizes, give the screen one clear
hierarchy with a single primary action, and let the relevant Laws of UX decide the rest.
