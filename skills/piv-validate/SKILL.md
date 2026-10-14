---
name: piv-validate
description: Corre el gate de calidad del proyecto (typecheck, lint, tests, build) y reporta PASS/FAIL por comando. Usar antes de commitear o abrir un PR.
disable-model-invocation: true
---

# /piv-validate

1. Buscá el gate en `AGENTS.md` (o `CLAUDE.md`, `package.json`, `Makefile`). Si no está definido, preguntá y proponé dejarlo en `AGENTS.md`.
2. Corré cada comando del gate.
3. Reportá:
```
typecheck : PASS/FAIL
lint      : PASS/FAIL
test      : PASS/FAIL (N pasaron, N fallaron)
build     : PASS/FAIL
Overall   : PASS/FAIL
```
Solo los pasos que el proyecto define.

**FAIL**: listá cada comando fallido con su primer error y arreglá. No lo ocultes ni lo declares "preexistente" sin verificarlo.
**PASS**: listo para commitear.
