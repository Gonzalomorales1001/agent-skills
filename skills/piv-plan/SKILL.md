---
name: piv-plan
description: Planifica una feature mediana o grande sin escribir código; deja docs/plans/active/<feature>/plan.md. Usar al inicio del loop PIV (opcional; no para hot-fixes ni cambios chicos).
disable-model-invocation: true
---

# /piv-plan <feature>

Planifica. **No escribe código.**

## Proceso
1. Leé `AGENTS.md` y `docs/README.md`; cargá solo los docs que la tarea necesite (usá los routers si existen).
2. Leé el código a modificar y su análogo más cercano.
3. Identificá riesgos: reglas de `AGENTS.md`, tests que quedan sin cubrir, docs que habrá que actualizar.
4. Escribí `docs/plans/active/<feature>/plan.md` (obligatorio, en disco, no solo en el chat).
5. Si algo es ambiguo y cambia el plan, preguntá antes de escribir.

## Formato de plan.md
```
# Plan: <feature>
## Objetivo        1-2 líneas
## Contexto        docs y código relevante, con paths
## Tareas          - [ ] qué · dónde (path) · cómo validar (comando)
## Riesgos
## Docs a actualizar
## Aceptación      criterios medibles
```
Tareas chicas, ordenadas por dependencia, cada una con su comando de validación.

## Salida
Path del plan, complejidad (baja/media/alta), riesgos clave. Siguiente: `/piv-implement`.
