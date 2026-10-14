---
name: piv-implement
description: Ejecuta un plan de docs/plans/active/<feature>/plan.md tarea por tarea, validando cada una, y escribe report.md. Usar después de /piv-plan.
disable-model-invocation: true
---

# /piv-implement <ruta-al-plan>

## Proceso
1. Leé el plan completo y `AGENTS.md` antes de tocar código.
2. Por cada tarea: leé el archivo antes de editarlo, implementá, corré su comando de validación. Si falla, arreglalo antes de seguir. Nunca saltees una validación.
3. Marcá la tarea `[x]` en el plan solo si la probaste.
4. Al final, corré el gate completo (`/piv-validate`).
5. Aplicá el **gate de docs** (skill `docs-structure`): actualizá lo que cambió.
6. Escribí `report.md` junto al plan.

## Formato de report.md
```
# Reporte: <feature>
## Hecho         tareas y archivos cambiados
## Gate          resultado por comando
## Desvíos       qué cambió respecto del plan y por qué
## Docs          qué se actualizó
```

Siguiente: `/piv-review`.
