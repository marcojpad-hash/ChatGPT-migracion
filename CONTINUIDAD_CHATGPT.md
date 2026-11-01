# Continuidad ChatGPT — corte 2026-11-01

## Fuente operativa

Este repositorio conserva la continuidad transversal. Los datos y archivos de cada proyecto permanecen en su repositorio especializado:

- CAPCOT: `capcot-capsulas-imaginantes`, rama `feature/capcot-video-discovery-continuity`.
- Motor U6: `motor-u6-storage`, rama `main`.
- Migración: `ChatGPT-migracion`, rama `main`.
- Orquestador Central: repositorio adicional descubierto en la cuenta GitHub conectada; no forma parte de los tres repositorios principales de este mandato y se mantiene en observación de solo lectura hasta inclusión expresa del propietario.

No copiar código canónico del motor a este repo. No duplicar entregables CAPCOT.

## Estado actual

- **CAPCOT:** la auditoría del 1-nov detectó 5 piezas para slots del día y un slot 23:30 sin paquete. Lectura en frío: Xolo 85 PASS narrativo, pulpo 72 FAIL, cebolla 84 FAIL, Baffin 78 FAIL, tiburón 89 PASS narrativo; ninguno tenía registro machine-readable `narrative_qa` ni `narrative_contract`. Se implementó la compuerta: el investigador deja borrador en `proyectos/`; el auditor revisa solo la narración y promueve a cola raíz solo con PASS y validador correcto. Los 33 project_id heredados (116 archivos) se movieron reversiblemente a `cola/bloqueados/`; no queda storyboard JSON en `cola/entrada/`. El reingreso exige QA independiente. El workflow sigue bloqueado por falta de `GROK_WEBHOOK_URL`; no hay `cola/estado/`, por tanto recepción Grok no confirmada. El radar del 1-nov no existía al último corte; el run investigador sigue en progreso.
- **Motor U6:** F006 R7 sigue siendo reevaluación de Courbet, no caso independiente. El protocolo de custodia independiente está verificado. C01–C20 siguen pendientes; no se modificaron Engine V5, el catálogo de 244 patrones ni candados.
- **Orquestador Central:** repositorio privado adicional verificado, PR draft #1 abierto y sin fusionar. Dos checks de GitHub Actions pasaron 3 pruebas cada uno. Prototipo no desplegado; permanece solo lectura.
- **Dot:** no se considera conectado ni disponible desde esta sesión. El operador diario es sustituto parcial, no Dot ni un agente 24/7.
- **Notion:** páginas V15 antiguas son históricas cuando contradicen Motor U6. GitHub prevalece.
- **Analítica social:** no hay conexión confirmada a métricas privadas de Meta, YouTube o TikTok.

Últimos registros:
- Auditoría transversal: [reportes/2026-10-31_AUDITORIA_TRANSVERSAL.md](reportes/2026-10-31_AUDITORIA_TRANSVERSAL.md).
- Operación autónoma: [reportes/2026-11-01_OPERACION_AUTONOMA.md](reportes/2026-11-01_OPERACION_AUTONOMA.md).


## Cuentas y repositorios GitHub comprobados

Comprobación actual de las dos conexiones:
- `marcojpad-hash`: una instalación visible; cuatro repositorios devueltos: `ChatGPT-migracion`, `capcot-capsulas-imaginantes`, `motor-u6-storage`, `orquestador-central`.
- `marcosabines-hash`: sin instalaciones ni repositorios devueltos.

Los tres repositorios principales de trabajo siguen siendo `ChatGPT-migracion/main`, `capcot-capsulas-imaginantes/feature/capcot-video-discovery-continuity` y `motor-u6-storage/main`. `orquestador-central` está clasificado como DESCUBIERTO_ADICIONAL y no recibió escrituras.


## Automatizaciones

| Automatización | Horario guardado CDMX | Último run observado |
|---|---:|---|
| Operador autónomo general | Diario 08:00, exact_schedule | `7dd18f1e-af70-8331-8d36-64854ab926b3`, iniciado 14:20; `in_progress` al último peek. |
| Agente de investigación CAPCOT | Diario 08:00 hasta 24-nov, exact_schedule | `eb74bc97-0478-832c-a823-25af9adab923`, iniciado 14:20; `in_progress`. El último resultado completado sigue siendo 31-oct. |
| Auditor CAPCOT — cola y rotación | Diario 15:00, flexible_schedule | `47f25beb-8e28-8324-b66b-c3923f3e90e3`, completado 14:27; corrió 40 minutos antes del slot guardado. |

Las tres muestran `next_run_time=null`. Los runs de operador e investigador aparecen programados a las 14:20 aunque sus reglas guardadas dicen 08:00; la causa no está identificada. Los prompts se actualizaron después de iniciar esos runs. El auditor produjo el CONTROL_COLA antes de recibir la nueva regla de staging; la próxima ejecución debe registrar `narrative_qa` con siete checks y promover solo PASS.


## Reglas de trabajo

- Resolver directamente lo reversible y autorizado.
- Mantener separados CAPCOT y Motor U6; sus métricas, decisiones y entregables no se mezclan.
- No inventar acceso, ejecución, datos, aceptación de Grok ni actividad en segundo plano.
- No publicar, enviar mensajes externos, gastar créditos, modificar permisos ni alterar archivos canónicos sin autorización.
- Separar evidencia verificada, ejecución, inferencia y pendiente.
