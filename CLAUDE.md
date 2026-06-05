# CLAUDE.md — build-skills

## Project Overview

A curated collection of Agent Skills for frontend build tools, part of the
[Full Stack Skills](https://github.com/partme-ai/full-stack-skills) ecosystem.
Each skill is a self-contained `SKILL.md` file that AI agents load on-demand.
Distributed as a Claude Code plugin via `.claude-plugin/plugin.json`.

## Skills (6)

| Skill       | Tier | Description |
|-------------|------|-------------|
| `dart-sass` | Rich | Sass syntax, compilation, mixins, functions, modules, source maps |
| `rspack`    | Rich | Rust-based bundler — config, loaders, plugins, optimization, webpack compat |
| `vite`      | Rich | Dev server, HMR, config, plugins, SSR, backend integration |
| `parcel`    | Thin | Zero-config bundler — assets, HMR, code splitting |
| `rollup`    | Thin | Library bundler — config, plugins, tree shaking |
| `webpack`   | Thin | Classic bundler — loaders, plugins, code splitting, optimization |

**Rich** skills use progressive disclosure (SKILL.md → api/, examples/, templates/).
**Thin** skills embed everything in a compact SKILL.md.

## Directory Structure

```
skills/<name>/
  SKILL.md          # Entry point with YAML frontmatter (name, description, license)
  LICENSE.txt       # Apache 2.0 license text
  api/              # API reference files (rich skills only)
  examples/         # Topic-specific docs mapped 1:1 with official docs (rich only)
  templates/        # Project scaffolding/config templates (rich only)
```

## SKILL.md Conventions

- **YAML frontmatter**: `name` (kebab-case), `description` (one sentence + trigger phrases), `license`
- **Sections**: `## When to use this skill`, `## How to use this skill`, `## Best Practices`, `## Resources`, `## Keywords`
- **Rich skills** include doc mapping tables linking local files to official URLs, and `Load <filepath>` directives for progressive disclosure
- **Keywords** include both English and Chinese terms for bilingual discovery
- **Thin skills** keep everything in SKILL.md (no subdirectories); use Chinese body text
- Body content must be neutral — no partisan political statements or imagery

## Agent Instructions (AGENTS.md)

The project conforms to the Agent Skills specification at [agentskills.io](https://agentskills.io).
Key rules for agents authoring skills:
- One skill per directory under `skills/`, named with kebab-case
- `SKILL.md` is the only required file; keep it under 500 lines
- Use progressive disclosure: move detailed docs into `examples/`, `api/`, `templates/`
- Include `keywords` covering both English and Chinese terminology
- No scripts required — all skills are markdown-based knowledge files

## Key Files

| File | Purpose |
|------|---------|
| `.claude-plugin/plugin.json` | Plugin manifest registering all 6 skills |
| `README.md` / `README.zh-CN.md` | Public project README (bilingual) |
| `AGENTS.md` | Authoring conventions for AI agents (Chinese) |
| `AGENTS_EN.md` | Authoring conventions for AI agents (English) |
| `LICENSE` | Apache 2.0 |
