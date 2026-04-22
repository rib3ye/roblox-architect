# roblox-architect

An agent skill for [Cursor](https://cursor.com) / [Claude Code](https://docs.anthropic.com/en/docs/claude-code) that turns the agent into an elite Roblox engineering architect.

The persona is opinionated, terse, and obsessed with long-term maintainability. Its defining axioms:

- **Organization is the product.** Spaghetti is unacceptable.
- **The [Order](https://order.atomichorizon.net/) framework is the default skeleton** for every project — `client/` / `server/` / `shared/` / `first/` / `character/` roots, `tasks/` subfolders, `shared("ModuleName")` instead of `require()`.
- **Server-authoritative, single source of truth, one-way data flow.**
- **Community packages over bespoke code** — Wally + Rojo + Rokit, plus opinionated picks for persistence (ProfileStore), networking (ByteNet/Red), state (Matter/Vide/Fusion), UI (Fusion/Vide/Iris/TopbarPlus), concurrency (Promise/Signal/Janitor/Trove), testing (Jest-Lua), and lint/format (Selene/StyLua).
- **Strict dependency direction**, one concern per module, pure functions in `lib/`.

Pairs nicely with a security-focused sibling skill (e.g. a `roblox-opsec` persona) — the architect handles structure and maintainability; the opsec persona handles exploit surface.

## When the agent activates

The skill self-triggers when you ask the agent to:

- design or restructure a Roblox/Luau project
- plan a new system or scaffold a new project
- review code organization or run an architecture audit
- pick a community library (Wally / Rojo / Rokit / ProfileStore / Matter / Fusion / Knit / Promise / Signal / Janitor / TestEZ / Jest-Lua / Selene / StyLua / Lune / etc.)
- decide where code should live

…or any time you say "architect", "structure", "organize", "refactor", or "scaffold" in a Roblox context.

## Install

### Claude Code (personal skills)

```bash
git clone https://github.com/rib3ye/roblox-architect.git ~/.claude/skills/roblox-architect
```

### Cursor (personal skills)

```bash
git clone https://github.com/rib3ye/roblox-architect.git ~/.cursor/skills/roblox-architect
```

### Cursor (project-shared skills)

From the root of a Roblox project:

```bash
git clone https://github.com/rib3ye/roblox-architect.git .cursor/skills/roblox-architect
```

After cloning, the skill becomes available immediately — no further configuration needed. The agent will activate it automatically when relevant.

## What's in the box

- [`SKILL.md`](SKILL.md) — the entire skill. Frontmatter + persona + Order rules + ecosystem toolkit + decision workflow + audit checklist + voice/output format.

That's it. One file. No scripts, no nested references.

## Order framework

This skill leans heavily on [Order](https://order.atomichorizon.net/) by Atomic Horizon — a configurable module-loader framework for Roblox with first-class support for cyclic dependencies, customizable init pipelines, and multi-place universes. If you're not already using it, the skill will recommend you adopt it as the project skeleton.

## License

[MIT](LICENSE)
