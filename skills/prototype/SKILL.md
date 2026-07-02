---
name: prototype
description: The single prototyping skill. Frame the intent and pick the output mode up front (an HTML sketch, Figma screens, or iso-prod in the real codebase), then use THIS repo's real design system as the source of truth (it discovers the stack, tokens, components, conventions), propose options, and build with UI/UX rigor (4px grid, component consistency, information hierarchy). Use whenever the user wants to prototype, mock up, design screens, "show options for X", "build a clickable demo", or build a feature/flow as a throwaway to evaluate. Frontend-only, mock data, no prod. Works in any repo.
---

# prototype — spec → options → HTML, Figma, or iso-prod code, on your repo

One skill for all prototyping: a single screen or a full flow, in **three output modes**. It is
**spec-driven**, uses the project's **real code as the source of truth**, gives the team **options**,
and bakes in **craft + UI/UX rigor**. It works in **any repo**: it discovers the stack and adapts,
never assuming a framework or design system.

**Who uses this:** often founders, not designers. They won't notice when a prototype is subtly off —
so the framing gate (§0) and the craft bar (§3) are not optional polish, they are what keep the
output usable.

## 0 · Frame it first — STOP before building

Do **not** produce anything until four things are locked. Ask them in **one** exchange (a short
salvo, not an interrogation), fill what you can from the prompt, then confirm:

1. **Existing or new?** Are we starting from a screen/flow that exists, or a blank page?
2. **The job.** What must the user be able to do, and what does success look like?
3. **A reference OR a flow.** At least one visual/product example that inspires them, OR agreement
   on the user flow.
4. **How do you want to see it?** The output mode (§1) — but explain it in **plain, founder
   language**, not jargon. They won't know what "iso-prod" means. Say it like this:
   - **A quick mock-up (HTML)** — I sketch fast, several directions, in a separate page. Best to
     explore and decide the look. It's throwaway and not yet a perfect match to your real app.
   - **Straight in your real app (your actual code)** — I build inside your real application with
     your real buttons, colours, components. Slower, but high fidelity and it can become real. It
     lives on a **separate throwaway branch** — it does **not** touch your live app; a developer
     finalises it later if you decide to ship it.
     *(Whatever language your app uses — React, Next, Vue… — I adapt. The mode is not about the
     language, it's about the result living in your real app.)*
   - **In Figma** — only if you want something to share or present to your team in Figma.

   Recommend a default so they're never stuck: **HTML to explore, real code once the direction is
   locked.** They pick; you confirm.

Then **restate the flow in 1–2 lines and wait for a "yes" before building.** Founders often can't
describe a flow — so **propose it yourself** and let them react:

> "Here's the flow I understand: Home → Choose plan → Confirm. Shall we go with that?"

🚩 **Red flag — STOP:** you're about to build and you don't know if it's existing-vs-new, the flow
isn't agreed, or the founder never understood which output mode they picked. A vague brief produces
"approximately right" output the founder can't diagnose. One round-trip of framing is cheap; a wrong
prototype is not. (This is a gate, not a long interview — the four points above plus a flow
confirmation, then go. Any extra detail like exact prices or plan count waits for their next reply —
don't pile it on now.)

## 1 · Pick the output mode

This table is **your** reasoning; §0.4 is what you actually *say* to the founder (plain language).
The user chooses; infer + confirm if obvious.

| Mode | Choose it when | Gain / risk |
| --- | --- | --- |
| **A · HTML sketch** | Explore **fast and wide**, early, several directions at once | Quick, throwaway, roughly on-brand. **Risk: DS drift** — it reinvents values. Watch for it. |
| **C · Iso-prod (in the codebase)** | Refine **inside the real DS**, high fidelity, it may become real | Precise, guaranteed on-brand, real components. **Costs more tokens/time.** |
| **B · Figma** | The deliverable must **live in Figma**: team handoff, async review, shareable link — or you're already working there | Shareable, team-facing. Only when Figma is already the playground. |

Default to A for early exploration; reach for C when fidelity matters; use B only when the artifact
belongs in Figma.

## 2 · Discover the design system — adapt to THIS repo (code = source of truth, 100%)

Do NOT assume a stack. Discover what the repo uses, then match it exactly:

1. **Detect the stack.** `package.json` (or equivalent) + layout: framework (Next, Vite, Remix,
   Astro, Vue, SvelteKit, plain HTML…) and styling (Tailwind, CSS vars, CSS modules,
   styled-components, SCSS, a theme object…).
2. **Find the token source of truth.** CSS custom properties (`globals.css` / `tokens.css`), a
   Tailwind config, a theme file, SCSS vars, a JSON token set. Use those exact values.
3. **Find the real components.** The repo's own library (`components/`, `ui/`, a registry, a
   Storybook). Match them exactly.
4. **Find the conventions.** `CLAUDE.md` / `AGENTS.md` / `README` / Storybook. Honor what IS
   documented (states, primary actions, icon set, tone). Don't impose rules the repo doesn't state.

Then: **use the repo's real components.** If one genuinely doesn't exist, **say so** and compose from
primitives, flagged as a new component to add. **Never silently fake one.** No design system at all?
Say so, and offer: prototype against a minimal neutral default (labelled not-yet-on-brand), or set
one up first. *(If it's an @efounders repo: shadcn + `@efounders` components, tokens in `globals.css`;
pull missing ones from the `@efounders` registry.)*

🚩 **Red flag — STOP:** you're reaching for a Tailwind/Bootstrap default, an invented hex, or a
made-up component because discovery was slower. That's DS drift. Go find the real value first.

## 3 · The craft bar — this is what makes it feel high-end

High-end quality does **not** come from reciting UX theory. It comes from **references + concrete
craft + iteration**. Apply, in order:

- **Start from a reference, always.** The bar you match is a real example, not a principle. Pull the
  reference from §0; mirror its density, palette, type rhythm, and spacing before adding your own.
- **Anti-generic.** Actively avoid the "default AI / Bootstrap" look: even grey cards, one flat blue,
  centered everything, timid spacing. Make a *decision* about density, contrast, and personality.
- **Real content, never lorem.** Realistic names, numbers, edge-case lengths. Fake content hides the
  hard layout problems and makes everything look plausible when it isn't.
- **Restraint reads as premium.** Generous whitespace, a restrained palette, **one** accent that
  means "act here". A confident type scale with real contrast between levels. Let space do the
  grouping before you reach for borders and boxes.
- **One intentional motion detail.** A single considered transition/hover beats motion everywhere.
- **Iterate against a screenshot.** The first output opens the conversation — take a screenshot,
  critique it against the reference, refine. Quality comes from the loop, not the first pass.

**The floor** (4px grid, information hierarchy, one primary action per screen, the 5 states, a11y) is
the non-negotiable baseline — see `references/ui-ux-foundations.md`, read it before designing.

*Bonus:* if the `impeccable` skill is available in this environment, call it to push the craft ceiling
further. This prototype stands on its own without it — the bar above is self-contained.

## 4 · Propose options

Give **2–3 distinct directions** (different layouts / IA / emphasis) — each a real take, not a variant
of one. One line of trade-offs per option, so the team can pick.

**Don't ask "one screen or several?" up front** — it's a false question. The number of screens falls
out of the user flow (§0.3), and single-screen-vs-split is itself a design decision worth *testing*:
a form, say, can be one dense screen or a stepped multi-screen flow. When it matters, make it one of
the options here (e.g. Option A = single screen, Option B = 3 steps), not a framing question.

## 5 · Build in the chosen mode

**A · HTML sketch** — fast, interactive, prod-free.
- Self-contained file(s); tokens on `:root`; every value via `var(--…)` (or the repo's mechanism).
- 4px grid, no arbitrary values. Real component classes/structure; mock data; hash routing for flows;
  no external runtime deps (a Google Font only if the DS specifies one).

**B · Figma** — visual, team-facing. Via the **Figma MCP** (`figma-generate-design` / `use_figma`).
- **Auto-layout everywhere** (no absolute positioning). **Real library components** (Code Connect); if
  one isn't in the library, compose + flag it, never fake. **Variables = token names.** 4px grid, no
  off-grid values. Clean layer names; prefix exploration frames `_wip/`. Code stays the truth.

**C · Iso-prod (in the codebase)** — the real app, real components. The highest-fidelity handoff.
- **Build in the real repo, reusing the REAL components** (not redrawn). Mirror with the exact real
  classes only what's coupled to router / API / i18n and can't run standalone.
- **Throwaway branch** (`design/<slug>`), never merged: a handoff a dev refines, not a feature.
- **Compare directions with a runtime toggle.** A tiny context + a floating switch to flip between
  options live, on the same data, changing **one variable at a time** — the team feels each option in
  the same environment instead of guessing.
- **Fake data at ONE seam.** Map the page's data hooks first, then inject fixtures at the single API
  chokepoint (e.g. the client `get()`), **gated to dev + a specific record**, removable in one place.
  Real pages then render real-looking content. Don't seed the DB or redraw the UI.
- **Keep it green.** Typecheck + lint pass at every step, so it's a credible handoff.
- **Local-first.** Make it work on `localhost`; a deploy/preview is for *sharing*, never for the
  designer to see her own work. (Gotcha: a dev-server restart can white-screen on a stale bundler
  cache — clear it, e.g. `node_modules/.vite`, and hard refresh.)

## 6 · Deliver + iterate

- HTML → `**[Open →](file:///absolute/path/…)**`. Figma → the link. Iso-prod → the local URL(s) + how
  to flip the toggle; say it's a throwaway branch.
- A short summary **per option** (what it is, trade-offs, what to try).
- Iterate on the picked option **as a dialogue** — the first output starts the conversation, never the
  final deliverable. Never dump code in chat: write the file / create the frames / point to the
  running screen, return the link.

## Guardrails (the non-obvious rules)

- **Frame before building** (§0). No prototype without existing-vs-new, the job, the mode, and an
  agreed flow.
- **Code = source of truth**, always. Figma reflects it, never the reverse.
- **Real components only** (from THIS repo). State explicitly when something must be invented; never
  silently fake one.
- **No DS drift.** Snap to the repo's real tokens/sizes; never an invented hex or off-grid value.
- **Stick to the brief.** No extra features; minimal by default, suggest the rest in text.
- **Mock data, no prod** — explore any state freely.
