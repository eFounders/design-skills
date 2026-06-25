# Design Skills

Reusable AI skills for **doing design work** — exploring directions, prototyping, and improving them — directly inside a product's own codebase.

They are **design-system-agnostic**. Each skill discovers and respects whatever the project already has (its tokens, components, conventions, stack). Nothing here is tied to a specific design system or starter: drop a skill into any company's repo and it works against that company's own DS.

## The flow

From intent to refined screens, a simple loop:

1. **`da-exploration`** *(draft)* — explore 2-3 distinct art directions (mood, typography, color, density). Choose a visual direction. *(Explore)*
2. **`prototype`** — turn the idea into concrete, reviewable screens, using the project's real tokens and components. HTML or Figma. *(Explore)*
3. **`product-review`** — a senior UX/UI critique of those screens: prioritized findings, named UX laws ([lawsofux.com](https://lawsofux.com/)), concrete fixes. *(Improve)*

**Steps 2 and 3 loop both ways**: `prototype → review → back to prototype`, until the direction holds.

## How to use

Drop a skill folder into a project's `.claude/skills/` (or `~/.claude/skills/` to have it everywhere), then invoke it, e.g. `/product-review`.

---

*Author: Nelly Seiglan · Hexa*
