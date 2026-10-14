---
name: docs-structure
description: Organiza y mantiene la documentación de un proyecto (AGENTS.md, docs/, qué va en cada carpeta, cuándo actualizar). Usar al crear, auditar o reorganizar docs, y al cerrar cualquier cambio que pueda dejarlos desactualizados.
---

# Docs structure

Contenido en español; nombres de carpetas y archivos en inglés.

## Principio
- **Vivo**: dice cómo es hoy. Se edita en el lugar.
- **Histórico**: dice qué pasó. No se edita al cerrarse.

## Estructura
```
AGENTS.md          fuente única: comandos, gate, reglas, mapa
CLAUDE.md          puntero a AGENTS.md (≤5 líneas)
docs/
  README.md        índice "pregunta → fuente"
  context/         [vivo] cómo funciona el sistema, por área
  specs/           [vivo] comportamiento esperado, una por área
  decisions/       [histórico] ADRs numerados
  plans/active/    [histórico] trabajo en curso, por feature
  plans/done/      [histórico] trabajo terminado
  debt/            [vivo] problemas conocidos
  runbooks/        [vivo] procedimientos paso a paso
  reports/<tema>/<fecha>/   [histórico] evidencia
  learnings.md     [vivo] errores no obvios y su causa
```
Crear solo las carpetas que el proyecto necesita.

## Plantillas
Proyecto nuevo: copiar `templates/AGENTS.md` y `templates/CLAUDE.md` a la raíz y completar los `<…>`. El gate de docs va dentro del `AGENTS.md`, así funciona con cualquier agente aunque no tenga esta skill.

## Nombres
- `kebab-case`, por tema y no por tipo: `judge-voting.md`, no `spec-2.md`.
- Sin versión ni fecha en el nombre, salvo ADRs (`0003-<tema>.md`) y reports (carpeta fechada).
- Un archivo = un tema. Mismo nombre de tema en `context/` y `specs/` si es la misma área.

## Gate de docs (siempre, al cerrar un cambio)
Preguntar: ¿cambió algo documentado? Actualizar solo la fuente que corresponde:
- Cambió cómo funciona → `context/` o `specs/`
- Se eligió entre alternativas → ADR nuevo (si revierte uno, enlazarlo; no borrarlo)
- Se halló o resolvió un problema → `debt/`
- Fix no obvio → `learnings.md`
- Cambió un procedimiento → `runbooks/`

## Planes (opcionales)
Solo para features medianas o grandes. Hot-fixes y cambios chicos no llevan plan.
Un plan nuevo vive en `plans/active/<feature>/`; al terminar, moverlo a `done/` y avisar.
Modificar algo terminado: nunca editar `done/`. Cambio chico → editar el doc vivo.
Cambio grande → plan nuevo que enlaza al anterior.

## Reglas
1. Una fuente principal por dato; enlazar, no copiar.
2. Fechar lo que cambia (versiones, costos, métricas).
3. Separar confirmado de hipótesis.
4. Nunca guardar secretos, solo nombres de variables.
5. Nada suelto en la raíz de `docs/` salvo `README.md`.
6. Área con más de ~5 módulos → router: tabla "tarea → archivos mínimos".
7. Cada doc corto y escaneable; si crece, partirlo.
8. Al agregar un doc de entrada, actualizar `docs/README.md`.

## Auditar un repo existente
Listar `docs/`, marcar cada archivo como vivo o histórico, y reportar: archivos sueltos, duplicados, planes terminados en `active/`, fuentes duplicadas. Proponer, no mover sin aprobación.
