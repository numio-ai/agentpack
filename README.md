# AgentPort

AgentPort translates [GearLoop](https://github.com/vkroz/gearloop) plugin artifacts into tool-specific configs for Cursor, Kiro, and GitHub Copilot.

GearLoop defines the canonical format. Write rules and skills once in `.claude/` — Babelport converts them to whatever your team uses.

## Why AgentPort

Teams adopting AI coding tools shouldn't rewrite configuration for each platform. AgentPort treats GearLoop's `.claude/` format as the source of truth and outputs tool-specific configs, keeping rules consistent across organizations, teams, projects, and repositories.

## Prerequisites

AgentPort requires an existing `.claude/` directory populated with rules, skills, and commands. If you don't have one, [GearLoop](https://github.com/vkroz/GearLoop) — a Claude Code plugin — scaffolds it using a spec-driven development workflow that covers the full development lifecycle.

## Installation
```bash
uv tool install git+https://github.com/vkroz/agentport
```

## Usage
```bash
agentport cursor
agentport kiro
agentport copilot
```

## Output

| Target | Output path |
|---|---|
| `cursor` | `.cursor/rules/*.md` |
| `kiro` | `AGENTS.md` |
| `copilot` | `.github/copilot-instructions.md` |


## Further reading

See `docs/user-guide.md` for full configuration reference.
