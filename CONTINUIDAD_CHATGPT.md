# Continuidad ChatGPT — corte 2026-11-01

## Fuente operativa

Este repositorio conserva la continuidad transversal. Los datos y archivos de cada proyecto permanecen en su repositorio especializado:

- CAPCOT: `capcot-capsulas-imaginantes`, rama `feature/capcot-video-discovery-continuity`.
- Motor U6: `motor-u6-storage`, rama `main`.
- Migración: `ChatGPT-migracion`, rama `main`.
- Orquestador Central: repositorio adicional descubierto en la cuenta GitHub conectada; no forma parte de los tres repositorios principales de este mandato y se mantiene en observación de solo lectura hasta inclusión expresa del propietario.

No copiar código canónico del motor a este repo. No duplicar entregables CAPCOT.

## Estado actual

- **CAPCOT:** investigación diaria 08:00 y auditoría de cola 15:00. El storyboard de pardelas del 31-oct tiene `approved_assets=[]`, `render_status=NOT_GENERATED` y publicación pendiente; no existe estado Grok. Los paquetes del 1-nov están en carpetas anidadas y contienen rutas `asset_filename` sin archivos de frame. El workflow de despacho solo selecciona JSON de primer nivel; la entrega externa sigue bloqueada por secretos webhook ausentes. Recepción Grok no confirmada.
- **Motor U6:** F006 R7 sigue siendo reevaluación de Courbet, no caso independiente. Se creó y verificó el protocolo de custodia independiente. C01–C20 siguen pendientes; no se modificaron Engine V5 ni el catálogo de 244 patrones.
- **Orquestador Central:** repositorio privado adicional verificado. La rama `feature/core-mvp-l1` tiene PR draft #1 abierto. Dos checks de GitHub Actions terminaron en éxito, con 3 pruebas unitarias cada uno. Es un prototipo no desplegado, sin adaptadores de proveedores ni entrada móvil universal; no se fusionó a `main`.
- **Dot:** no se considera conectado ni disponible desde esta sesión. El operador diario es sustituto parcial, no Dot ni un agente 24/7.
- **Notion:** páginas V15 de septiembre son históricas cuando contradicen Motor U6. GitHub prevalece. El workspace no acepta nuevas páginas/bloques según el estado documentado.
- **Analítica social:** no hay conexión confirmada a métricas privadas de Meta, YouTube o TikTok.

## Cuentas y repositorios GitHub comprobados

La conexión de la cuenta `marcojpad-hash` devolvió cuatro repositorios: `ChatGPT-migracion`, `capcot-capsulas-imaginantes`, `motor-u6-storage` y `orquestador-central`. La segunda conexión GitHub consultada no devolvió instalaciones ni repositorios. No declarar inexistente un repositorio sin repetir esta comprobación.

Los tres repositorios principales de trabajo siguen siendo los enumerados en la fuente operativa. `orquestador-central` se registró como DESCUBIERTO_ADICIONAL y no recibió escrituras en esta operación.

## Automatizaciones

| Automatización | Horario CDMX | Estado observado al corte |
|---|---:|---|
| Operador autónomo general | Diario 08:00 | Habilitada. Run `178fd744-a9ac-8329-94e8-eaa81aaf8b76` del 1-nov en `in_progress`; no declarar completado. `next_run_time` nulo. |
| Agente de investigación CAPCOT | Diario 08:00 hasta 24-nov | Habilitada. Último run observado: 31-oct, completado. El horario guardado se corrigió de 08:30 a 08:00 el 1-nov a las 08:01:44 CDMX, después del slot de las 08:00; no hay run del 1-nov confirmado al corte. `next_run_time` nulo. |
| Auditor CAPCOT — cola y rotación | Diario 15:00 | Habilitada. Último run del 31-oct completado; el resultado fue un CONTROL_COLA estático. El prompt actual se reforzó el 1-nov después de ese run; todavía no hay ejecución registrada bajo esa versión. `next_run_time` nulo. |

Una programación guardada no equivale a una ejecución futura confirmada. Consultar el historial antes de atribuir trabajo.

## Reglas de trabajo

- Resolver directamente lo reversible y autorizado.
- Mantener separados CAPCOT y Motor U6; sus métricas, decisiones y entregables no se mezclan.
- No inventar acceso, ejecución, datos, aceptación de Grok ni actividad en segundo plano.
- No publicar, enviar mensajes externos, gastar créditos, modificar permisos ni alterar archivos canónicos sin autorización.
- Separar evidencia verificada, ejecución, inferencia y pendiente.
