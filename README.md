# Babelport

Babelport translates [GearLoop](https://github.com/vkroz/gearloop) plugin artifacts into tool-specific configs for Cursor, Kiro, and GitHub Copilot.

GearLoop defines the canonical format. Write rules and skills once in `.claude/` — Babelport converts them to whatever your team uses.

## Why Babelport

Teams adopting AI coding tools shouldn't rewrite configuration for each platform. Babelport treats GearLoop's `.claude/` format as the source of truth and outputs tool-specific configs, keeping rules consistent across organizations, teams, projects, and repositories.

## Prerequisites

Babelport requires an existing `.claude/` directory populated by GearLoop. Run GearLoop first — Babelport has nothing to translate without it.

## Installation
```bash
uv tool install git+https://github.com/vkroz/babelport
```

## Usage
```bash
babelport translate --target cursor
babelport translate --target kiro
babelport translate --target copilot
```

## Output

| Target | Output path |
|---|---|
| `cursor` | `.cursor/rules/*.md` |
| `kiro` | `AGENTS.md` |
| `copilot` | `.github/copilot-instructions.md` |

## Hierarchical inheritance

Rules compose across levels: global → org → project → repo → user. Each level overrides or extends the one above without breaking the chain. Babelport preserves this hierarchy in all output formats.

## Further reading

See `docs/user-guide.md` for full configuration reference.
