---
name: piv-review
description: Revisa el diff actual con un subagente contra las reglas del proyecto y escribe review.md junto al plan. Usar después de implementar, antes de commitear.
disable-model-invocation: true
---

# /piv-review

## Proceso
1. Identificá la feature: nombre de la rama o `docs/plans/active/` más reciente. Si hay duda, preguntá.
2. Obtené el diff (`git diff HEAD`, o `git show HEAD` si ya está commiteado).
3. Delegá a un subagente revisor (`code-reviewer` del proyecto si existe; si no, uno general) con: el diff, `AGENTS.md`, el plan y los docs relevantes. Debe revisar corrección, reglas del proyecto, tests y **docs desactualizados**.
4. Escribí el veredicto sin modificarlo en `docs/plans/active/<feature>/review.md`.

## Salida
Veredicto **PASS** o **CONCERNS**; si hay CONCERNS, los ítems bloqueantes.

## Cierre
Si PASS y todas las tareas del plan están `[x]`: mové `plans/active/<feature>/` a `plans/done/` (`git mv`) en el mismo PR y avisá.
Si CONCERNS: arreglá, y repetí `/piv-validate` y `/piv-review`.
