# Operación autónoma — 2026-11-20

Corte de trabajo: 2026-11-20, madrugada CDMX. Esta bitácora registra operaciones comprobadas, no una declaración de cumplimiento general.

## CAPCOT — auditoría ejecutada

- Repositorio: `marcojpad-hash/capcot-capsulas-imaginantes`.
- Rama: `feature/capcot-video-discovery-continuity`.
- Se leyeron contrato operativo, Plan Maestro, Receta, Guía, Flujo Externo, QA narrativo, contrato Grok, plantilla, catálogo, `registro_editorial.py`, `procesar_cola.py`, workflow dispatch, briefs y storyboards relevantes.
- Se releyeron los dos storyboards del 19-nov. Oro poroso: narrative_qa PASS 91, 8 escenas, 188 palabras, 84 s con cortinilla de 6 s; DOI sigue PENDIENTE_RESOLVEDOR. Estrella dentro de estrella: PASS 90, 8 escenas, 197 palabras, 84 s; DOI pendiente, geometría celeste incompatible con el validador geográfico y estilo repetido el mismo día. Ninguno se promovió.
- No hay proyecto ni radar del 20-nov en el inventario al corte.
- La cola de feature tiene tres carpetas anidadas (7, 9 y 11-nov), no JSON planos en la raíz. El workflow `capcot-grok-dispatch.yml` solo detecta `cola/entrada/*.json` y usa `find -maxdepth 1`; por eso las tres rutas son NOT_DISPATCHABLE para ese workflow. `procesar_cola.py` sí acepta `*/storyboard.json`: existe discrepancia real entre procesador y dispatch.
- Run preexistente del trabajador: [44688912590](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/actions/runs/44688912590), rama main, commit `05e842dc55577461e63d8f5de13fba96c46ff5f1`, comando `python3 scripts/trabajador_cola.py`, salida literal `[trabajador] sin trabajo en cola.`. No acredita que se haya leído/procesado la rama feature.
- Los dos estados `cola/estado/<project_id>.json` del 19-nov devolvieron 404: `RECEPCION_GROK_NO_CONFIRMADA`. No se crearon estados.
- Control completo creado y releído: [2026-11-20_CONTROL_COLA.md](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-20_CONTROL_COLA.md). Commit `25caf2fd209ad2418f24ef93650d2e5fcb97ceb0`; blob releído `08f6287f81b7921c2e887a191cfd9283999b72b5`.

No se generaron cápsulas, imágenes, frames, voz, audio, video ni renders. No se publicaron piezas, no se consumieron créditos, no se modificó `data/*.json`, workflow, secretos, permisos, estados Grok ni main de CAPCOT.

## Motor U6 — estado real y discrepancia de asignación

- Rama de trabajo vigente: `alterno/cameo-pesos`. `main` es SOLO_CONSULTA, según `CONTRATO_OPERATIVO_RAMA_VIGENTE.md`.
- La orden permanente está en [issue #465](https://github.com/marcojpad-hash/agente-cero-costo/issues/465) y en `DELEGACIONES.md`: meta aproximada 30 corridas/día de casos nuevos e independientes F007+, con fuentes, Z congelado, custodia independiente, recibos y resumen en el repo. No se permite inflar n con re-corridas.
- La ficha del operador unificado vigente no incluía explícitamente esta orden y describía Motor U6 como revisión documental en main. Esto es una divergencia operativa que debe corregirse en la ficha de ejecución.
- `casos/fabrica/semillas_lote_F007.py` contiene 8 semillas, pero solo 2 cortes por sujeto y las fuentes declaradas son Wikipedia secundaria. `destinos_lote_F007.py` se titula “ensayo metodológico: mismo actor”; no acredita custodia independiente. La carpeta `casos/fabrica/cola/` solo contiene directorios F001–F005; no hay cola F007 preparada. Por tanto F007 no acredita casos independientes listos ni corridas.
- Run preexistente de auditoría Actions: [44666733628](https://github.com/marcojpad-hash/motor-u6-storage/actions/runs/44666733628). Checkout de `main` commit `77cd9d83b0b2f8e84a8bba6ab33e403ab5fbe291`; comando `python scripts/auditar_corridas_actions.py`; salida literal `AUDIT_UPDATED runs=99 failures=2`; commit generado por workflow `c867c88` en main. Es snapshot de auditoría de Actions, no corrida nueva del motor ni evidencia de 30 casos. Se registra como proceso preexistente, no ejecutado por esta sesión.
- Últimos commits observados en `alterno/cameo-pesos`: PR #34–#36 integrados el 19-nov; HEAD `e7a732ee9fb5d1773756a54cfd782cdcf73e15e3`.
- No se ejecutó Motor U6 en este run: no se preparó un caso nuevo válido con fuentes primarias ni custodia independiente, y no se presentó un recibo de corrida. No se tocaron motor canónico, patterns 244, pesos, FREEZE ni PRs.

## Automatización — estado de la corrección

Se solicitó actualizar la ficha de Operador único para que lea y ejecute la orden #465 en la rama `alterno/cameo-pesos`. Las llamadas disponibles de actualización de automatización devolvieron `HTTP 404: Action not found`; por ello no se afirma que la ficha haya quedado corregida. La lectura actual de la ficha confirma que su sección U6 sigue describiendo revisión de documentación/pruebas y no incorpora el objetivo de corridas nuevas. El run manual solicitado se lanzó con `run_now`, pero el registro de ejecuciones consultado no expuso un nuevo run completado; no se declara como ejecución completada de la automatización.

## Resultado comprobable

- Un entregable de auditoría CAPCOT creado y releído en GitHub.
- Un defecto concreto de dispatch identificado: las carpetas anidadas no coinciden con el selector del workflow.
- Dos storyboards del 19-nov preservados fuera de cola por bloqueos reales.
- La orden #465 y el lote F007 contrastados con el estado del repositorio; no se inventaron corridas ni custodia.
- La ficha programada todavía necesita que su prompt incorpore el alcance U6 correcto; el intento de actualización falló y no se presenta como resuelto.
