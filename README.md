# Design Skills

Reusable AI skills for **doing design work** — exploring directions, prototyping, and improving them — directly inside a product's own codebase.

They are **design-system-agnostic**. Each skill discovers and respects whatever the project already has (its tokens, components, conventions, stack). Nothing here is tied to a specific design system or starter: drop a skill into any company's repo and it works against that company's own DS.

## The flow

From intent to refined screens, a simple loop:

1. **`da-exploration`** — guides anyone (designer or not) through exploring 3 distinct art directions for a brand or screen: pull angles from an idea, hunt reference images (Cosmos/Mobbin/Pinterest/Instagram), then render each as an HTML graphic universe + an intention screen at iso-content. Choose a visual direction. *(Explore)*
2. **`prototype`** — turn the idea into concrete, reviewable screens, using the project's real tokens and components. HTML, Figma, or iso-prod code. *(Explore)*
3. **`product-review`** — a senior UX/UI critique of those screens: prioritized findings, named UX laws ([lawsofux.com](https://lawsofux.com/)), concrete fixes. *(Improve)*

**Steps 2 and 3 loop both ways**: `prototype → review → back to prototype`, until the direction holds.

## Install

Public and free — no GitHub account or SSH key needed. Run these in your **Terminal** (the macOS
Terminal app), not inside Claude Code, so there is **no leading slash**.

**Step 1 — add the marketplace once:**

```bash
claude plugin marketplace add eFounders/design-skills
```

**Step 2 — install the skill(s) you want, one command each:**

```bash
# Prototyping — build screens & flows against the project's real design system
claude plugin install prototype@efounders-design

# Product review — senior UX/UI critique of a screen or flow, written for founders
claude plugin install product-review@efounders-design

# Art-direction exploration — explore 3 distinct visual directions
claude plugin install da-exploration@efounders-design

# Design-system audit — score a project's DS (clean codebase + AI-native)
claude plugin install ds-audit@efounders-design

# Design-system bootstrap — set up a DS from the shared base
claude plugin install ds-bootstrap@efounders-design

# Figma sync — generate/refresh a Figma DS from the code
claude plugin install ds-figma@efounders-design
```

Then **restart Claude Code**. Use a skill by simply describing what you want — e.g. *"prototype a
screen for X"* or *"critique this screen"* — the matching skill runs on its own.

**Update** — pull the latest version of a skill any time (same pattern for any skill name):

```bash
claude plugin update prototype@efounders-design
```

> Prefer to work inside Claude Code's terminal session instead? The same commands work there with a
> leading slash, e.g. `/plugin marketplace add eFounders/design-skills`. (This slash form only exists
> inside the `claude` terminal REPL — not in every app.)

**Manual (no plugin).** Copy a skill folder from `skills/` into a project's `.claude/skills/` — or
`~/.claude/skills/` to have it everywhere.

## Feedback & license

Open, and better with your input. Star it if it helps, and open an issue if something breaks. [MIT](LICENSE): use it, fork it, brand it.

---

*Author: Nelly Seiglan · Hexa*
