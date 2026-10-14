# <Proyecto> — guía para agentes

<Qué es el proyecto, en 1-2 líneas.>

> Fuente única para cualquier agente (Claude Code, Codex, Cursor, etc.). `CLAUDE.md` apunta acá.

## Gate
```bash
<comando>   # <qué corre>. Si no pasa, no está terminado.
```
Si el gate falla **antes** de empezar, arreglalo o avisá; no trabajes sobre una base rota.

## Comandos
| Comando | Para qué |
| ------- | -------- |
| `<cmd>` | <uso>    |

## Reglas
1. <Regla dura del proyecto: qué nunca hacer y por qué.>

## Documentación
Índice: [`docs/README.md`](docs/README.md). Leé solo lo que la tarea necesite.

**Gate de docs.** Al cerrar cualquier cambio, preguntate si algo documentado quedó desactualizado y actualizá solo esa fuente:
- Cambió cómo funciona → `docs/context/` o `docs/specs/`
- Se eligió entre alternativas → ADR nuevo en `docs/decisions/`
- Se halló o resolvió un problema → `docs/debt/`
- Fix no obvio → `docs/learnings.md`
- Cambió un procedimiento → `docs/runbooks/`

Lo vivo se edita en el lugar; lo histórico (`plans/done/`, ADRs, reports) no se edita.

## Flujo (opcional)
Features medianas o grandes: plan en `docs/plans/active/<feature>/`, al terminar pasa a `done/`. Hot-fixes y cambios chicos no llevan plan.
