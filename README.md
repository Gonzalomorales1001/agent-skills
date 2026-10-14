# agent-skills

Skills personales para agentes de código (Claude Code, Codex).

| Skill | Para qué |
|---|---|
| `docs-structure` | Estructura y mantenimiento de docs (`AGENTS.md`, `docs/`, gate de docs) |
| `piv-plan` · `piv-implement` · `piv-validate` · `piv-review` | Loop Plan → Implement → Validate → Review (opcional) |

## Usar
```bash
git clone https://github.com/Gonzalomorales1001/agent-skills.git
```
Copiar o enlazar cada carpeta de `skills/` a:
- `~/.claude/skills/` (Claude Code, global) o `<proyecto>/.claude/skills/`
- `<proyecto>/.agents/skills/` (Codex)

Actualizar: `git pull` y volver a copiar (o usar symlinks).
