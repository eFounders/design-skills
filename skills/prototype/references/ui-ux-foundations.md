# UI/UX foundations — the floor for `prototype`

Load this before designing. It is the **non-negotiable baseline** every prototype meets, in any mode
(HTML, Figma, iso-prod). It is the *floor*, not the ceiling — the ceiling comes from the craft bar in
SKILL.md §3 (references + concrete craft + iteration). **Project tokens and conventions always win**
over the generic defaults here.

---

## 1 · Snap to the repo — the 4px grid is only the fallback

- **Project tokens win.** If the repo defines spacing/type/radius tokens, use *those exact values*.
- **The grid is the fallback** for values the tokens don't cover: multiples of **4px** on the scale
  `4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 96` (Tailwind `1/2/3/4/6/8/12/16/24`).
- **Never an off-grid, invented value.** No `13px`, no `padding: 17px`, no `gap: 10px`, no `15.5px`
  type. If you're reaching for one, you're guessing — snap to the token or the nearest step.
- **One spacing rhythm per screen.** Pick a base step (4 or 8) and stay consistent: related things
  share a gap, unrelated things get a bigger one.

## 2 · Reuse the real component sizes — consistency reads as "finished"

- **Take sizes from the real components:** control heights (button/input/select), icon sizes, avatar
  sizes, radii, border widths. Don't redraw them.
- **One canonical component per role.** Don't place a one-off next to the real `Button`; don't build a
  `Tag` that's just a recoloured `Badge`. Compose from primitives or flag a genuinely new component.
- **Same control = same size everywhere.** All primary buttons the same height, all body text the same
  size, all cards the same radius/padding. Inconsistency reads as "unfinished".
- **Align everything.** Shared left edge, shared baseline, consistent gutters. Misalignment is the
  fastest way a prototype looks "off".
- **Touch targets ≥ 44px** for anything tappable.

## 3 · Information hierarchy — the eye lands on the right thing first

- **One primary action per screen.** Exactly one. Everything else is secondary/tertiary/ghost.
- **Rank with four levers, in order:** size → weight → colour → space. Reach for size and weight before
  colour; use colour sparingly so the accent actually means "act here".
- **Group with proximity and whitespace** before boxes and borders. Tighten within a group, loosen
  between groups.
- **Clear reading path:** title → context → primary content → action. Don't let two things compete for
  "most important".
- **Progressive disclosure.** Show what's needed now; tuck advanced/rare options behind a step, toggle,
  or panel.

## 4 · The 5 states + accessibility — don't skip

- **Every screen handles the 5 states:** empty, loading, error, partial, ideal. A prototype that only
  shows the happy path is half a prototype.
- **Loading:** skeletons for known shapes, spinners only for indeterminate waits.
- **Accessibility:** full keyboard path, visible focus rings, correct ARIA roles/labels, sufficient
  contrast, ≥44px touch targets, visible labels over placeholder-only fields.

## 5 · Laws of UX — the floor checklist, not a lecture

A frontier model already applies these; use them as a quick sanity check, not a syllabus. Full
reference: **https://lawsofux.com**

- **Hick** — fewer choices, one primary action, split long forms, sane defaults.
- **Fitts** — big, close, reachable primary targets; ≥44px; don't strand the key button.
- **Jakob** — match the conventions users already know; innovate on value, not the back button.
- **Miller** — chunk content; group nav; don't show 20 ungrouped items.
- **Von Restorff** — make the one primary action visually distinct; don't dilute it.
- **Aesthetic–Usability** — spacing, alignment, type consistency buy trust; they're not decoration.
- **Doherty** — keep feedback under ~400ms: instant hover/press, optimistic UI, skeletons over spinners.

---

**In one line:** snap to the repo's tokens, reuse the real component sizes, give the screen one clear
hierarchy with a single primary action, handle all 5 states — then let the craft bar do the rest.
