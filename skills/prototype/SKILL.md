---
name: prototype
description: The single prototyping skill. Frame the intent and pick the output mode up front (an HTML sketch, Figma screens, or iso-prod in the real codebase), then use THIS repo's real design system as the source of truth (it discovers the stack, tokens, components, conventions), propose options, and build with UI/UX rigor (4px grid, component consistency, information hierarchy, Laws of UX). Use whenever the user wants to prototype, mock up, design screens, "show options for X", "build a clickable demo", or build a feature/flow as a throwaway to evaluate. Frontend-only, mock data, no prod. Works in any repo.
---

# prototype — spec → options → HTML, Figma, or iso-prod code, on your repo

One skill for all prototyping: a single screen or a full flow, in **three output modes** the user
picks up front. It is **spec-driven**, uses the project's **real code as the source of truth**,
gives the team **options** to choose from, and bakes in **UI/UX rigor** (4px grid, hierarchy, Laws
of UX). It works in **any repo**: it discovers the stack and adapts, never assuming a framework or
design system.

## 1 · Frame it: intent + output mode (light, bias to action)

Get a quick read, fill from the prompt, then move. Keep it short:

- **Objective / JTBD** — what problem, for whom, what success looks like.
- **User + context** — who, when, what they're trying to do.
- **Scope** — one screen, or the hero flow (3–5 screens); the must-haves.
- **Ambition** — minimal (stick to the brief, zero extras) vs divergent (bolder, different
  directions). Default to minimal; never add features the user didn't ask for (suggest in text).
- **Pick the output mode up front** (the user chooses; infer + confirm if obvious):
  - **A · HTML sketch** — fast, on-brand, throwaway. Best to explore look and flow quickly.
  - **B · Figma** — visual, team-facing handoff.
  - **C · Iso-prod (in the codebase)** — the real app with real components; highest fidelity, a
    handoff a dev finalizes. Pick when fidelity matters or it will become real.

**Reference or sharper brief — only if the direction is unclear.** A clear brief or a reference (a
screenshot, a link, a product that nails it) is enough: go. If it is genuinely vague, ask for ONE of
a reference example or a two-line sharper brief, plus maybe one targeted question. Do not gate or
interrogate: a vague brief causes "approximate" output, but a long question list is worse than a
sensible default plus a quick check-in. A sharp spec + sensible defaults beats a long interview.

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

Then: **use the repo's real components.** If one genuinely doesn't exist, **say so** and compose
from primitives, flagged as a new component to add. **Never silently fake one.** No design system at
all? Say so, and offer: prototype against a minimal neutral default (labelled not-yet-on-brand), or
set one up first. *(If it's an @efounders repo: shadcn + `@efounders` components, tokens in
`globals.css`; pull missing ones from the `@efounders` registry. One possible setup, not a
requirement.)*

## 3 · Apply UI/UX rigor (every mode, every screen)

Read `references/ui-ux-foundations.md` before designing, and apply it. The short version:

- **4px grid + Tailwind scale.** Every spacing / sizing / radius is a multiple of 4 on the Tailwind
  scale (`4/8/12/16/24/32/48/64`). Project tokens win; the grid is the fallback. Never a `13px` /
  `padding: 17px`.
- **Component sizing & consistency.** Reuse the repo's real sizes (control heights, icon sizes,
  radii). One canonical component per role; the same control is the same size everywhere.
- **Information hierarchy.** ONE primary action per screen. Rank by size → weight → color → space.
  Group with proximity and whitespace; align to a grid; the eye should land on the key thing first.
- **Laws of UX.** Apply the relevant ones (Hick, Fitts, Jakob, Miller, Proximity / Similarity /
  Common-region, Von Restorff, Aesthetic-Usability, Doherty, Tesler). The reference file lists each
  with a one-line "how to apply".
- **The 5 states** (empty, loading, error, partial, ideal) and **a11y** (keyboard, visible focus,
  ARIA, contrast, 44px touch targets).

## 4 · Propose options

Give **2–3 distinct directions** (different layouts / IA / emphasis) — each a real take, not a
variant of one. One line of trade-offs per option, so the team can pick.

## 5 · Build in the chosen mode

**A · HTML sketch** — fast, interactive, prod-free.
- Self-contained file(s); tokens on `:root`; every value via `var(--…)` (or the repo's mechanism).
- 4px grid, no arbitrary values (see §3). Real component classes/structure; mock data; hash routing
  for flows; no external runtime deps (a Google Font only if the DS specifies one).

**B · Figma** — visual, team-facing. Via the **Figma MCP** (`figma-generate-design` / `use_figma`).
- **Auto-layout everywhere** (no absolute positioning). **Real library components** (Code Connect);
  if one isn't in the library, compose + flag it, never fake. **Variables = token names.** 4px grid,
  no off-grid values. Clean layer names; prefix exploration frames `_wip/`. Code stays the truth.

**C · Iso-prod (in the codebase)** — the real app, real components. The highest-fidelity handoff.
- **Build in the real repo, reusing the REAL components** (not redrawn). Mirror with the exact real
  classes only what's coupled to router / API / i18n and can't run standalone.
- **Throwaway branch** (`design/<slug>`), never merged: a handoff a dev refines, not a feature.
- **Compare directions with a runtime toggle.** A tiny context + a floating switch to flip between
  options live, on the same data, changing **one variable at a time**. This is what makes the choice
  real: the team feels each option in the same environment instead of guessing.
- **Fake data at ONE seam.** Map the page's data hooks first, then inject fixtures at the single API
  chokepoint (e.g. the client `get()`), **gated to dev + a specific record**, removable in one place.
  The real pages then render real-looking content. Don't seed the DB or redraw the UI.
- **Keep it green.** Typecheck + lint pass at every step, so it's a credible handoff, not throwaway
  HTML someone must rewrite.
- **Local-first.** Make it work on `localhost`. A deploy / preview is for *sharing* with others,
  never for the designer to see her own work. (Gotcha: a dev-server restart can white-screen on a
  stale bundler cache — clear it, e.g. `node_modules/.vite`, and hard refresh.)

## 6 · Deliver + iterate

- HTML → `**[Open →](file:///absolute/path/…)**`. Figma → the link. Iso-prod → the local URL(s) +
  how to flip the toggle; say it's a throwaway branch.
- A short summary **per option** (what it is, trade-offs, what to try).
- Iterate on the picked option **as a dialogue** — the first output starts the conversation, never
  the final deliverable. Never dump code in chat: write the file / create the frames / point to the
  running screen, return the link.

## Rules
- **Code = source of truth**, always. Figma reflects it, never the reverse.
- **Three modes, picked up front** (HTML / Figma / iso-prod); adapt the whole workflow to the mode.
- **Adapt to the repo.** Discover stack, tokens, components, conventions; never assume a framework
  or design system.
- **Real components only** (from THIS repo); state explicitly when something must be invented.
- **Stick to the brief.** No extra features the user didn't ask for; minimal by default, suggest the
  rest in text. Ask for a reference/sharper brief only when the direction is genuinely unclear.
- **UI/UX rigor, always** (§3 + `references/ui-ux-foundations.md`): 4px grid + Tailwind scale,
  component consistency, information hierarchy, Laws of UX, the 5 states, accessibility.
- **Mock data, no prod** — explore any state freely.
- **Honor whatever the repo documents** (`CLAUDE.md` / `README` / Storybook). Don't invent rules it
  doesn't state.
