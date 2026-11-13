# Proyectos y estado — corte 2026-11-01

## Fuente de verdad por proyecto

| Proyecto | Repositorio / ubicación | Estado actual | Pendientes reales |
|---|---|---|---|
| CAPCOT / Datos y ociosidades | `capcot-capsulas-imaginantes`, `feature/capcot-video-discovery-continuity` | Cola vacía; 33 project_id/116 archivos en `cola/bloqueados/`. Radar 1-nov y borrador red-electrica creados en `proyectos/`, sin QA todavía. | Auditor debe revisar siete checks; DOI principal pendiente; falta `GROK_WEBHOOK_URL`, slot 23:30 y acuse Grok. |
| Motor U6 / V15.3 | `motor-u6-storage`, `main` | F006 R7 registrado como reevaluación; protocolo de custodia independiente creado. Engine V5 y catálogo 244 intactos. | C01–C20 siguen pendientes; se requieren sujetos nuevos, fuente pre-Z y separación real entre preparador y custodio. |
| Orquestador Central | `orquestador-central`, privado | Repositorio adicional descubierto. PR draft #1 en `feature/core-mvp-l1`; 2 checks CI exitosos, 3 pruebas cada uno. | No está desplegado ni integrado; faltan pruebas HTTP, recuperación de tareas atascadas, adaptadores, runtime persistente y entrada/salida entre canales. No fusionar ni desplegar sin autorización. |
| Migración ChatGPT | `ChatGPT-migracion`, `main` | Continuidad, estilo, coordinación y auditoría transversal. | Mantener horarios, ejecuciones y estados reales actualizados. |
| Notion operativo Motor | Workspace Notion | Páginas antiguas conservadas como archivo histórico. | GitHub prevalece ante contradicciones; el workspace alcanzó el límite de bloques gratuitos. |
| Analítica social | Conector externo | No hay conexión privada confirmada. | Requiere autorización OAuth del titular para métricas privadas. |

## CAPCOT — estado y handoff

- Auditoría del 1-nov: [CONTROL_COLA](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-01_CONTROL_COLA.md), actualizado después del movimiento de cuarentena y del nuevo borrador.
- La auditoría encontró 5 piezas asignadas a slots del día: Xolo, pulpo, cebolla, Baffin y tiburón. Lectura narrativa: Xolo 85 PASS, pulpo 72 FAIL, cebolla 84 FAIL, Baffin 78 FAIL, tiburón 89 PASS; ninguno tenía `narrative_qa` ni `narrative_contract`, por lo que los dos PASS narrativos no eran PASS integral.
- Diez runs recientes de Actions fallaron; ocho logs inspeccionados reportan `Falta configurar GROK_WEBHOOK_URL.`. No hubo POST; no se llegó a comprobar `GROK_WEBHOOK_TOKEN`. No existe `cola/estado/`: recepción Grok no confirmada.
- Compuerta vigente: investigador escribe en `proyectos/<project_id>/storyboard.json`; auditor distinto del redactor oculta título, resumen, arco, notas y contrato narrativo y lee solo la narración. Solo PASS (>=85, siete checks true, flags vacíos) más validación estructural permite promoción a `cola/entrada/YYYY-MM-DD_slug.json`.
- Plantilla con `narrative_contract` de seis campos; validador exige ese contrato y `narrative_qa` PASS.
- Se retiraron 33 project_id y 116 archivos a `cola/bloqueados/`, preservando SHA de blob. Cero storyboard JSON queda en cola.
- Nuevo radar: [2026-11-01_RADAR_CAPCOT.md](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-01_RADAR_CAPCOT.md). Nuevo borrador: `proyectos/2026-11-01_red-electrica-pulso-minuto/storyboard.json`, 8 escenas, 190 palabras, 84 s, contrato narrativo completo. DOI de Nature Energy pendiente de validación directa; comunicado de Forschungszentrum Jülich verificado. No tiene `narrative_qa`, no está preparado ni en cola.
- El run investigador terminó 14:37; radar y borrador quedaron verificados, pero el borrador sigue sin QA y no se considera preparado. El slot 23:30 no tiene paquete.
- No se tocaron `data/*.json`, workflows, secretos, permisos ni estados Grok. No se generaron medios ni se publicó.


## Motor U6 — estado empírico

- F006 R7 reevalúa el mismo input de Courbet; no incrementa n.
- La evaluación de peso tiene n=1; no hay fundamento para ajustar pesos o motor.
- El protocolo `casos/ciegos/PROTOCOLO_CUSTODIA_INDEPENDIENTE.md` separa selector, preparador Z, custodio, runner y auditor.
- C01–C20 permanecen pendientes. B-01/N-02/C-03/H-01 son freezes históricos, no corridas del motor.
- No se modificaron Engine V5, `patterns_final_v14.json`, gate Z ni resultados originales.

## Orquestador Central — estado del prototipo

- Repositorio privado adicional devuelto por la cuenta conectada `marcojpad-hash`; la segunda conexión GitHub consultada no devolvió instalaciones ni repositorios.
- Rama `feature/core-mvp-l1`, HEAD `446d5277b9cc4896ee18d3d5216598835f9b274e`; [PR draft #1](https://github.com/marcojpad-hash/orquestador-central/pull/1) abierto, no fusionado.
- Dos ejecuciones/checks de GitHub Actions finalizaron en éxito. Cada una corrió 3 pruebas: creación de instrucción/tarea, idempotencia y rechazo de prioridad inválida.
- El prototipo usa servidor HTTP, Bearer de propietario y SQLite. No se desplegó; escucha en localhost por defecto. No tiene adaptadores de modelos/canales, worker persistente, entrada móvil ni memoria global como servicio.
- La idempotencia actualmente devuelve duplicado aunque la misma clave llegue con texto distinto; la cola no tiene lease/recuperación de tareas atascadas. Son riesgos de diseño pendientes, no correcciones ejecutadas en esta operación.
- No se escribió en este repositorio: no estaba incluido entre los tres repositorios principales autorizados para cambios.

## Automatizaciones activas

| Automatización | Horario guardado CDMX | Último estado observado |
|---|---:|---|
| Operador autónomo general | Diario 08:00 | Run `7dd18f1e-af70-8331-8d36-64854ab926b3` en `in_progress` al último peek. |
| Agente de investigación CAPCOT | Diario 08:00 hasta 24-nov | Run `eb74bc97-0478-832c-a823-25af9adab923` completado 14:37; radar y borrador verificados; `scheduled_for` fue 14:20. |
| Auditor CAPCOT — cola y rotación | Diario 15:00, flexible | Run `47f25beb-8e28-8324-b66b-c3923f3e90e3` completado 14:27; ejecutó 40 min antes del horario guardado. |

Las tres muestran `next_run_time=null`. Operador e investigador muestran `scheduled_for=14:20` aunque sus horarios guardados dicen 08:00; causa no identificada. Los prompts se actualizaron después del inicio de los runs.


## Dot

Dot nativo no está disponible desde esta sesión. El operador diario es sustituto parcial, no un agente persistente 24/7 ni una computadora autónoma.

## Regla de estado

Cada hecho debe marcarse como verificado, ejecutado, inferido o pendiente. Un prompt actualizado no prueba que el bot haya ejecutado; un archivo en cola no prueba recepción; un artifact no equivale a un registro versionado hasta que se incorpore al repositorio.



## Actualización operativa — 2026-11-02

Esta actualización prevalece sobre el corte 2026-11-01 en lo relativo a estados actuales.

### CAPCOT — proyectos 2-nov

- Dos proyectos existentes: `proyectos/2026-11-02_camaron-mantis/` y `proyectos/2026-11-02_comida-pan-duro/`. El historial de GitHub atribuye la carga inicial a Grok Bot (commit `c83c35814499ae0a73443beb4d02d84e0e62c144`, mensaje de lote 2-nov); no atribuirlos al investigador CAPCOT, cuyo último run registrado es del 1-nov.
- Ninguno de los dos storyboards tiene `narrative_contract` ni `narrative_qa`. Por tanto no hay PASS narrativo ni autorización para promoción. Sus `ESTADO_EJECUCION.md` se corrigieron de PREPARADO a `BORRADOR_EN_PROYECTOS_NO_APTO_PARA_PROMOCION`.
- Ambos tienen carpetas en `salidas/` con storyboard, `qa.json`, `publicacion.json`, metadata y licencias. Los `qa.json` son QA audiovisual de 21 checks, no lectura narrativa en frío. Duraciones: camarón mantis 75.35 s; pan duro 74.33 s. El QA local admite 60–120 s; el segundo queda 0.67 s por debajo del mínimo editorial de 75 s.
- El árbol GitHub no contiene los MP4 referenciados ni frames; no se afirma que estén versionados. Los dos proyectos también tienen snapshots en `cola/bloqueados/`; `cola/entrada/` solo tiene `.gitkeep`.
- No existe `cola/estado/2026-11-02_camaron-mantis.json` ni `cola/estado/2026-11-02_comida-pan-duro.json`: RECEPCION_GROK_NO_CONFIRMADA por contrato. No se infiere recepción de commits o salidas.
- `publicacion.json` registra YouTube `5sxxx0vuXFE` (privado, publishAt 07:00 CDMX) y `V9bO9EUN0JA` (privado, publishAt 13:30 CDMX), además de estados programados de TikTok/Facebook. En los dos historiales hay versiones antiguas que siguen descritas como programadas: camarón `tmxMkxA6nOw` y `d-tYvAM8hGE`; pan `TbZRvpiDjdk` y `sHjf4QF9QiM`. Riesgo de publicación duplicada; no se borró ni canceló nada.
- `endscreens_rotacion.json` a las 07:52 CDMX registra 4 vistas para `5sxxx0vuXFE`, mientras el snapshot de publicación conserva `privacyStatus=private`. Discrepancia pendiente; no declarar PUBLICADO.
- El auditor CAPCOT se actualizó para comprobar salidas/publicaciones preexistentes, no redispatchar, distinguir QA audiovisual de `narrative_qa` y cotejar valores con el JSON releído. No ha ejecutado todavía el 2-nov.
- No hay radar `docs/briefs/2026-11-02_RADAR_CAPCOT.md`; el investigador no tiene run del 2-nov registrado. No se lanzó un run adicional para evitar duplicar trabajo de CAPCOT.

### Motor U6 — snapshot 2-nov

- Último commit observado en `main`: `9fb12bcf18eaf46ada5d05684470a0f23608f138`, creado por GitHub Actions. Cambió únicamente `avances/auditoria_corridas/ULTIMO_ESTADO.json` y `.md`.
- Auditoría Actions: runs `41441459614` y `41427587700` en éxito; el snapshot también conserva varios fallos previos del 2-nov. Son auditorías/snapshots de Actions, no prueba de nuevas corridas empíricas del motor.
- No se modificó motor, patrones, candados ni casos. C01–C20 continúan pendientes.

### Descubrimiento GitHub — 2-nov

- Cuenta `marcojpad-hash`: instalación 174841554, selección all; 4 repositorios visibles: ChatGPT-migracion, capcot-capsulas-imaginantes, motor-u6-storage y orquestador-central.
- Cuenta `marcosabines-hash`: 0 instalaciones y 0 repositorios visibles.
- `orquestador-central` continúa DESCUBIERTO_ADICIONAL y solo lectura; no recibió cambios.

### Automatizaciones — 2-nov

| Automatización | Último run | Estado al corte |
|---|---|---|
| Operador general | `1248bd49-8db4-832f-aa14-3791363a9486` | `in_progress`, iniciado 08:04 CDMX; sin finalización. |
| Investigador CAPCOT | `eb74bc97-0478-832c-a823-25af9adab923` | Completado 1-nov; no hay run 2-nov. |
| Auditor CAPCOT | `cf090c46-78d8-8331-9739-7f99d23abc1c` | Completado 1-nov 18:33 CDMX; modo flexible, no hay run 2-nov. |

Las tres muestran `next_run_time=null`. No atribuir entregables del 2-nov a una automatización sin un run completado y un commit atribuible.



- El prompt del investigador CAPCOT también tiene una compuerta anti-duplicación: consulta project_id del día en proyectos/salidas/cola y valida fecha_objetivo/slot_local; no genera otro storyboard para un slot ocupado; puede crear solo el radar faltante. No se lanzó un run adicional el 2-nov.


## Actualización de infraestructura compartida — 2026-11-03

La continuidad transversal y el inventario de herramientas quedaron documentados en ChatGPT-migracion:
- [Mapa de herramientas por proyecto](docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md).
- [Protocolo de memoria compartida entre modelos](docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md).
- [Checklist de migración](docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md).

**Motor U6:** GitHub accesible; Floot no tiene proyectos configurados; investigación científica disponible mediante conectores, sin workspace Undermind. No se modificó el repositorio U6 en esta operación.

**CAPCOT:** GitHub accesible en la rama feature/capcot-video-discovery-continuity. vidIQ no devolvió canales para la cuenta conectada. Canva no muestra Brand Kits; Runway no muestra workflows guardados. No se generaron medios ni se consumieron créditos.

**Infraestructura:** n8n-workflow-check está disponible como skill para crear y revisar workflows JSON, pero no se encontró conexión directa a la instancia n8n. Automations mantiene las tres tareas principales habilitadas; next_run_time aparece null en las consultas del 3-nov, por lo que su próxima ejecución requiere verificación.

**Pendiente de migración:** probar un intercambio real con acuse de otro modelo; la bandeja y la plantilla ya existen. No confundir archivos preparados con un handoff recibido.

## Actualización de estado CAPCOT — auditoría posterior del 2-nov

El auditor completó una revisión posterior a la actualización de la mañana. Informe fuente: [CONTROL_COLA 2026-11-02](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-02_CONTROL_COLA.md), leído desde la rama vigente.

- Resultado general: NO DISPATCHABLE; cola/entrada contiene solo .gitkeep y no existe cola/estado. Recepción Grok no confirmada.
- Para el 2-nov se revisaron cuatro proyectos con producción/salidas/publicaciones preexistentes: camarón mantis, pan duro, murciélagos y sequías. Todos son PROCESAMIENTO_PREEXISTENTE_NO_REDISPATCHAR; no generar una segunda entrega.
- QA narrativo independiente: camarón PASS 90 pero falla estructura y tiene producción previa; pan FAIL 84; murciélagos FAIL 72/80 según versiones; sequías FAIL 56/54 según versiones. No se promovió ninguno.
- Las versiones larga y bloqueada de murciélagos/sequías difieren. No fusionar ni asumir equivalencia.
- No hay medios verificados en el árbol GitHub para los cuatro; los QA audiovisuales y logs no demuestran que los medios referenciados estén versionados.
- Hay IDs antiguos de YouTube descritos como programados, con riesgo de duplicación. No se canceló ni borró nada; no declarar publicaciones públicas a partir de los snapshots.
- La última ejecución de dispatch visible seguía siendo run 41306776689 (1-nov), FAILURE por falta de GROK_WEBHOOK_URL; el paso de entrega fue omitido. No se modificaron secretos.
- La agenda 5–7 nov tiene 12 slots de contenido; IDs de varios paquetes bloqueados no coinciden con IDs actuales y existen duplicaciones de carpeta/JSON, especialmente nubes. Reconciliar antes de QA o handoff; no renombrar ni duplicar por inferencia.
- La auditoría fue estática: no se ejecutó el validador Python ni se enviaron paquetes.

## Actualización de Motor U6 — snapshot de Actions observado el 3-nov

El archivo motor-u6-storage/main/avances/auditoria_corridas/ULTIMO_ESTADO.md se releyó. Muestra auditorías programadas completadas en éxito hasta 2026-11-02 23:05 CDMX. Son ejecuciones del workflow de auditoría, no corridas empíricas nuevas del motor. No se modificó el motor ni se alteraron patrones/candados en esta preparación.


## Actualización operativa — 2026-11-05

- **CAPCOT:** investigador completado 08:01:35 CDMX; commit del radar `1f1861afd5c76da18341253ce1d25c8ab016f8fd`. Auditor sin ejecución del 5-nov; último run completado 4-nov. El storyboard canónico de árboles sí corresponde a red micorrícica/Karst 2023; la variante de respiración nocturna es distinta y está bloqueada. No promover sin QA narrativo independiente PASS y validador estructural correcto. La ausencia de estado individual Grok significa `RECEPCION_GROK_NO_CONFIRMADA`.
- **Motor U6:** solo revisión documental; no hay cambios canónicos ni nueva corrida predictiva declarada.
- **Herramientas:** n8n no tiene skill verificada ni conector ejecutable en la sesión; mapa corregido.
- **Migración:** acuse de segunda sesión pendiente; no declarar completada.
- Reporte del corte: [2026-11-05_OPERACION_AUTONOMA.md](reportes/2026-11-05_OPERACION_AUTONOMA.md).

## Actualización operativa — 2026-11-06

Estado observado a las 08:04 CDMX. Detalle y pruebas: [reportes/2026-11-06_OPERACION_AUTONOMA.md](reportes/2026-11-06_OPERACION_AUTONOMA.md).

### Automatizaciones

| Automatización | Última ejecución observada | Estado y atribución |
|---|---|---|
| Operador autónomo general | Run 2ca94b58-8a38-8333-8b6a-e4111db09eec; programado 14:00:00Z, iniciado 14:04:16Z. | in_progress, sin completed_at; el último resultado completado sigue siendo el del 5-nov. No atribuirle resultado final. |
| Agente de investigación CAPCOT | Run eebd6c6b-a0cc-832f-bf43-0e8e3d6c0ac0; completado 13:59:40Z (07:59:40 CDMX). | completed, resultado NO_DUPLICAR; commit 7e989a533e5e058c8e67258bbb0982fc29f635c1, solo modificó docs/briefs/2026-11-06_RADAR_CAPCOT.md. |
| Auditor CAPCOT — cola y rotación | Run d92c234e-1888-8331-ab77-098ab84c71bd; completado 21:35:39Z del 5-nov (15:35:39 CDMX). | completed; no hay ejecución del auditor del 6-nov en este corte. El run del 5-nov auditó también el lote 5–7 nov. |

Las tres siguen habilitadas y las consultas devuelven next_run_time=null. El operador está en ejecución; no se declara terminado en este corte.

### CAPCOT — 6 de noviembre

El investigador terminó con NO_DUPLICAR: verificó los cuatro proyectos canónicos del día y no creó storyboards adicionales. El commit 7e989a5 cambió únicamente el radar; no se modificaron data/*.json, storyboards, estados Grok ni medios.

A las 14:13:42Z (lectura de vuelta verificada 14:14:05Z) (08:13:42 CDMX) se actualizó el prompt del investigador para releer narrative_qa existente y reportar sus valores reales, sin crearlo, editarlo ni promover proyectos. La corrección ocurrió después del run del 6-nov; se aplicará a ejecuciones posteriores.

Los cuatro storyboards canónicos ya contienen narrative_qa escrito por el auditor independiente el 5-nov a las 15:18:57 CDMX. La frase del resultado del investigador «esperando al auditor» no describe el estado actual de esos JSON:

| Proyecto / slot | QA narrativo releído | Estructura por escena | Estado Grok |
|---|---|---|---|
| Ballena azul — 07:00 | FAIL 80; payoff_cierre_apertura=false; flag PAYOFF_SOBREAFIRMA_CASI_SE_DETIENE. | FAIL: faltan los seis campos narrativos obligatorios en las 7 escenas. | 404; RECEPCION_GROK_NO_CONFIRMADA. |
| Aguacate — 13:30 | FAIL 79; progresión y transiciones causales false; flag REPETICION_ESCENAS_5_6_SIN_AVANCE_CAUSAL. | FAIL: faltan los seis campos narrativos obligatorios en las 7 escenas. | 404; RECEPCION_GROK_NO_CONFIRMADA. |
| Ranas congeladas — 17:00 | FAIL 83; progresión y transiciones causales false; flag REPETICION_ESCENAS_5_6_LIMITES_DE_ESPECIE_Y_CONDICIONES. | FAIL: faltan los seis campos narrativos obligatorios en las 7 escenas. | 404; RECEPCION_GROK_NO_CONFIRMADA. |
| Dunas cantantes — 17:45 | PASS 94; siete checks true y critical_flags vacío. | FAIL: faltan los seis campos narrativos obligatorios en las 7 escenas. | 404; RECEPCION_GROK_NO_CONFIRMADA. |

Los cuatro permanecen en proyectos/. cola/entrada/ solo contiene .gitkeep; no hay salidas para esos cuatro IDs. Todos conservan approved_assets=[], export.render_status=NOT_GENERATED y publicación pendiente. Ninguno es despachable. El PASS narrativo de dunas no supera por sí solo la compuerta estructural. No se crearon ni modificaron estados Grok.

### Dispatch y agenda CAPCOT

- El último run de capcot-grok-dispatch.yml sigue siendo el #147, run 41306776689, del 1-nov. Falló en el commit antiguo c2791e806fbf44940f4dd87b64753ba48e04da6f con el error literal Falta configurar GROK_WEBHOOK_URL.; el paso de entrega quedó omitido.
- El workflow actual usa webhook opcional y, sin webhook, escribe un marcador pendiente en handoffs/grok_inbox/. Esta versión no tiene una ejecución posterior que demuestre el nuevo camino. El marcador pendiente no equivale a recepción por Grok.
- El workflow se dispara por archivos cola/entrada/*.json; los cuatro paquetes actuales están en proyectos/ y la cola está vacía. No se disparó ni se forzó un dispatch.
- Inconsistencia de agenda: el horario semanal conserva un slot 23:30 dato-TBD-news; el prompt del investigador excluye explícitamente 23:30; el contrato y el Plan Maestro aún describen ventanas 19:00/23:30, mientras el horario 5–7 nov reubica intermedio_2 a 17:45 y marca 19:00 retirado. No se alteraron horarios, cupos ni prompts; requiere una decisión de autoridad antes de corregir documentos.

### Motor U6 — corte 6 de noviembre

- avances/auditoria_corridas/ULTIMO_ESTADO.md registra el run de auditoría Actions 42214636992 completado en éxito a las 06:03 CDMX. Es una auditoría/snapshot, no una corrida predictiva nueva.
- F006 R7 sigue siendo reevaluación de Courbet; no aumenta el denominador independiente. La calibración histórica deduplicada conserva 40 casos biográficos independientes.
- C01–C20 continúan PENDIENTE; B-01/N-02/C-03/H-01 son freezes históricos, no corridas U6.
- Las cinco comparaciones causales (guardianes ON/OFF, compuerta ON/OFF, set abierto vs. salida única, memoria ON/OFF y pipeline fijo/adaptativo) siguen incompletas. MCT continúa como especificación conceptual, no capacidad implementada.
- No se ejecutó el motor ni se modificó código, Engine V5 canónico, catálogo de 244 patrones, candados, casos o resultados.

### Cuentas y repositorios adicionales

marcojpad-hash devuelve una instalación y cinco repositorios visibles: los tres principales, orquestador-central y red-teaming-safety-u6. marcosabines-hash devuelve cero instalaciones y cero repositorios. Los dos repositorios adicionales son DESCUBIERTO_ADICIONAL; se revisó solo documentación/metadatos y no recibieron escrituras.

orquestador-central mantiene el PR #1 abierto, draft y sin merge; no hay despliegue verificado. red-teaming-safety-u6 documenta un circuito hermano U6 de subcorridas white-hat aisladas y ledger append-only; no se inspeccionó ni modificó su ledger.

### Notion y migración

Las búsquedas de Notion Motor U6 y U6 solo devolvieron páginas V15 de septiembre (19–22-sep-2026). No se encontró una actualización posterior que desplace la autoridad de motor-u6-storage/main.

bandeja/2026-11-03_RECUPERACION_MIGRACION.md sigue PENDIENTE: no hay acuse de una segunda sesión/modelo, prueba de recuperación ni verificación de entregables. La migración no está completa.

## Actualización operativa — 2026-11-07

### CAPCOT — lote del 7-nov

- El investigador completó `NO_DUPLICAR` en run `d3e9a290-2548-8321-ae11-719b50454afe`; commit `5425b467c3750fe17c314f58d764d234bc2a8870`, un solo archivo: `docs/briefs/2026-11-07_RADAR_CAPCOT.md`. No creó otro storyboard ni tocó cola, bloqueados, medios o publicación.
- Los cuatro proyectos canónicos están en `proyectos/`: huesos 07:00, hielo caliente 13:30, pulpos 17:00 y nubes 17:45. El horario vigente retiró 19:00.
- QA narrativo preexistente (lectura independiente del 6-nov): huesos FAIL 82; hielo caliente FAIL 81; pulpos FAIL 80; nubes FAIL 78. Cada storyboard tiene siete escenas y carece de los seis campos estructurales obligatorios en todas ellas (42 omisiones por archivo). Cero promociones.
- `cola/entrada/` contiene solo `.gitkeep`; no existen estados Grok individuales. Estado: `RECEPCION_GROK_NO_CONFIRMADA`. Auditor sin run del 7-nov al corte; último run completado 6-nov.
- La agenda conserva `dato-TBD-news` a las 23:30. La instrucción permanente `ajustes_entre_modelos/PARA_CHATGPT_dato_del_dia.md` exige un paquete del mismo día, pero el run investigador excluyó ese slot de sus cuatro proyectos. No se encontró paquete del 7-nov ni se creó desde el operador general; queda una brecha de asignación.
- Reporte y radar: [RADAR_CAPCOT 2026-11-07](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-07_RADAR_CAPCOT.md).

### Motor U6 — A5 y reevaluación F006

- [PR #2](https://github.com/marcojpad-hash/motor-u6-storage/pull/2) desde `a5-cableado-20261107` fue fusionado el 7-nov 03:19 CDMX (merge `d2a730c98f5abfdd54c52722b1ef80c28e79f08b`). Contents:write funcionó en Motor U6. El PR deja pendiente Workflows; el workflow de tests no incluye los tres tests nuevos.
- La corrida Actions `42359245993` ejecutó una reevaluación real de `CAL_F005_01_COURBET` en F006 R7: returncode 0, recibo COMPLETED, 6,310 simulaciones Monte Carlo y 9/9 observaciones convergidas. Engine V5 y patrones coincidieron con sus hashes; candados y compuertas CEB OK.
- No incrementa n: mismo input Courbet, muestra calibrable n=1. H1/H2 y destino no acertaron; el set sí. El desenlace sellado fue ruptura y la apuesta de destino fue auge.
- Caldero devolvió ocho fuentes sin fecha y el modo leniente conservó las ocho; no queda demostrada su anterioridad a Z. Filtro 017 solo se ejecutó en traza sin modificación; consulta dirigida sigue no configurada.
- El artifact actual conserva salida/recibo, pero el resumen/registro/manifiesto versionados en main siguen en estado del 30-oct. El manifiesto del artifact también referencia un artifact anterior. La evidencia nueva no está sincronizada al registro Git versionado.
- La última auditoría Actions `42375177549` terminó en éxito 07:04 CDMX; es auditoría automática, no corrida predictiva. C01–C20 siguen pendientes. Esta operación no modificó código ni documentos de U6.

### GitHub/Muse y migración

- `marcojpad-hash`: cinco repositorios visibles; `marcosabines-hash`: cero instalaciones/repositorios visibles. `orquestador-central` y `red-teaming-safety-u6` siguen `DESCUBIERTO_ADICIONAL`, sin escrituras.
- En CAPCOT no existe rama A5 ni PR; Contents:write de Muse allí no está verificado. La instalación 174841554 devuelve selección `all`, pero no expone el nombre de la App.
- Notion devolvió solo páginas V15 de 19–22-sep-2026; siguen históricas frente a Motor U6.
- `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` sigue PENDIENTE; no existe acuse de otra sesión/modelo. Migración no completa.
- Reporte: [2026-11-07_OPERACION_AUTONOMA.md](reportes/2026-11-07_OPERACION_AUTONOMA.md).


## Actualización operativa — 2026-11-08

Este corte prevalece sobre los estados anteriores cuando exista diferencia. Registro detallado: [reportes/2026-11-08_OPERACION_AUTONOMA.md](reportes/2026-11-08_OPERACION_AUTONOMA.md).

### CAPCOT — rama `feature/capcot-video-discovery-continuity`

- HEAD observado: `4451ccc27ed751295cea8f1566a4eb7fc973e8d9` (verificación de slots del 8-nov 07:53 CDMX).
- El auditor terminó el 7-nov (`8159484e-7a74-8329-b4f1-3c4c362d862a`): 12 storyboards canónicos, 2 PASS narrativos, 10 FAIL, 0 estructuralmente aptos y 0 promociones. No hay auditoría del 8-nov al corte.
- El registro del 8-nov muestra 07:00 palomitas como publicado en YT/TT/FB. El slot 23:30 referencia `2026-11-07_dato-clavo-te-cocina` como programado en las tres plataformas; es un registro interno, no una consulta directa de plataforma.
- El storyboard de clavo está en `cola/entrada/2026-11-07_dato-clavo-te-cocina/storyboard.json`, dentro de una carpeta anidada. No tiene `narrative_qa` y carece de los seis campos narrativos obligatorios en sus ocho escenas. El workflow escucha únicamente `cola/entrada/*.json` de primer nivel, así que esta carpeta no es despachable por el workflow vigente.
- `cola/estado/2026-11-07_dato-clavo-te-cocina.json` devuelve 404: `RECEPCION_GROK_NO_CONFIRMADA`. `ESTADO_EJECUCION.md` dice `publicación/programación: NO_REALIZADA`, mientras `data/horario_2026-11-08.json` y `ESTADO_SLOTS_2026-11-08.md` dicen que está programado. `data/publicaciones.json` y `data/rotacion.json` no contienen ese ID. Conflicto documental abierto; no se movió, canceló ni redispatchó el paquete por el registro de programación existente.
- No se encontró un storyboard objetivo 8-nov en `proyectos/`; el investigador del 8-nov seguía `in_progress` al corte, por lo que no se atribuye resultado ni se declara que el día quedó sin paquete.
- La rama feature no contiene `.mcp.json`, `docs/CODEBASE_MEMORY_MCP.md` ni `docs/DSH_CERO_COSTO.md`; sí contiene el gate de memoria compartida en `AGENTS.md` y `README.md`.

### Motor U6 — rama `main`

- HEAD observado: `9ba7ee07fe8fa7ce21da0e9defb0ada9ce952949`. El último commit inspeccionado modificó únicamente `AGENTS.md` para anclar el gate de memoria compartida; no modificó motores canónicos, patrones ni candados.
- `docs/CODEBASE_MEMORY_MCP.md` y `.mcp.json` están presentes. El documento reporta índice del 7-nov; queda pendiente reindexar después de cambios posteriores.
- `avances/auditoria_corridas/ULTIMO_ESTADO.md` muestra el contrato de arranque Actions `42485950750` en éxito (8-nov 07:38:52–07:39:02 CDMX) y auditorías programadas en éxito. Son comprobaciones/instantáneas, no nuevas corridas predictivas.
- No se ejecutó ni modificó el motor en este corte. C01–C20 y los pendientes metodológicos previos no se declaran resueltos por las auditorías Actions.

### Migración y continuidad

- El handoff `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` sigue `PENDIENTE`; no existe acuse verificable de una segunda sesión/modelo. La migración no está completa.
- La memoria compartida está anclada en `AGENTS.md` y `README.md` de los nueve repositorios visibles, pero el gate no sustituye una prueba real de recuperación por otra sesión.
- Los repositorios adicionales se mantienen `DESCUBIERTO_ADICIONAL` y en solo lectura. No se modificó `memoria-compartida`, `orquestador-central`, `agente-cero-costo`, `baterias-tokens`, `baterias-memoria` ni `red-teaming-safety-u6`.

## Actualización operativa — 2026-11-09

### CAPCOT — rama `feature/capcot-video-discovery-continuity`

- El investigador completó el 9-nov `NO_DUPLICAR` y guardó únicamente [RADAR_CAPCOT 2026-11-09](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-09_RADAR_CAPCOT.md), commit `e7c6e7eb652845c614f1b875348f8f0bd819647a`. No hay storyboard objetivo 9-nov en `proyectos/`, `salidas/`, `cola/entrada/` ni `cola/bloqueados/`.
- `data/horario_2026-11-09.json`: 07:00 corresponde al proyecto existente `2026-11-06_inter-ranas-congeladas`, registrado como publicado en YouTube y TikTok; no se volvió a subir. Facebook figura programado desde el lote del 7-nov, sin URL capturada en esta corrida. El slot 23:30 está `sin_paquete`; el horario no asigna 13:30, 17:00 ni 19:00.
- Se leyó `docs/GROK_STATUS_CONTRACT.md`. `cola/estado/2026-11-06_inter-ranas-congeladas.json` devolvió 404: `RECEPCION_GROK_NO_CONFIRMADA`. La evidencia de publicación en el horario no sustituye el acuse individual exigido por el contrato.
- El control de cola del 9-nov conserva 12 storyboards canónicos del lote 5–7 nov: 2 PASS narrativos, 10 FAIL, 0 aptos estructuralmente y 0 promociones. Se reportan seis campos narrativos ausentes en 85 escenas (510 omisiones). No se reescribieron ni movieron paquetes.
- El horario del 9-nov también registra el clavo de la noche anterior como publicado en YT/TT; sin embargo, `cola/entrada/2026-11-07_dato-clavo-te-cocina/ESTADO_EJECUCION.md` sigue diciendo `Publicación/programación: NO_REALIZADA`. Se conserva la discrepancia; no se alteró el paquete ni se creó un estado Grok.
- El workflow de dispatch no tiene una ejecución posterior que demuestre el buzón nuevo; el control del 9-nov reporta el último dispatch run 41306776689 (1-nov, fallo de configuración en la versión anterior). No se disparó Actions.
- Comparación actual de ramas: `main...feature/capcot-video-discovery-continuity` = `diverged`, feature +671 / -120. No se fusionó ni se cambió de rama.

### Motor U6 — rama `main`

- Último commit observado: `b89853486d924aac7b25a5f1ecd46424e92c202e` (9-nov, `audit: snapshot de corridas Actions`). Los cuatro registros más recientes de `avances/auditoria_corridas/ULTIMO_ESTADO.md` son auditorías programadas del 9-nov y terminaron `success` (runs 42614233378, 42606582903, 42593008593 y 42580689454). Son snapshots/auditorías de Actions, no corridas predictivas nuevas.
- No se ejecutó ni modificó el motor en esta operación. `Engine_V5_CANONICO_SOLO.py`, `patterns_final_v14.json`, motores canónicos y candados permanecen fuera de alcance y sin cambios.
- codebase-memory-mcp sigue documentado/configurado localmente en U6/main; índice 0.12.1 del 7-nov (13 531 nodos / 27 173 aristas), pendiente de reindexación. No hay servidor MCP vivo expuesto a esta sesión.
- DeepSeek Harness no está integrado en U6/main.

### Continuidad

- `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` sigue `PENDIENTE`, sin acuse de otra sesión/modelo. Migración incompleta.
- Seis repositorios adicionales continúan `DESCUBIERTO_ADICIONAL` y en solo lectura.

## Actualización operativa — 2026-11-10

Detalle: [reportes/2026-11-10_OPERACION_AUTONOMA.md](reportes/2026-11-10_OPERACION_AUTONOMA.md).

### CAPCOT — feature/capcot-video-discovery-continuity
- HEAD 91003f7c551e4e60700b39b8f94451f1126fcaf3 (10-nov 07:47 CDMX); último commit cambia registro de pantallas finales, no storyboard.
- Horario 10-nov: 07:00 aguacate publicado YT/TT; 17:00 capsaicina resub programado YT/TT; 23:30 dato del día sin paquete.
- El paquete 2026-11-09_dato-robot-ensambla-orbita conserva narrative_qa PASS 90, pero la ruta anidada no coincide con el workflow que solo escucha JSON planos en cola/entrada/*.json. cola/estado/2026-11-09_dato-robot-ensambla-orbita.json devolvió 404: RECEPCION_GROK_NO_CONFIRMADA. Frames no generados; no mover ni redispatchar.
- El clavo del 7-nov también carece de estado Grok. No se creó ni modificó ningún archivo cola/estado.
- La orden permanente de preproducción del dato 23:30 contradice la exclusión de ese slot en el prompt del investigador; queda brecha de asignación. El operador no duplicó investigación/storyboard.
- Investigador 10-nov IN_PROGRESS; auditor último run completado 9-nov 16:33, sin run del 10-nov al corte.

### Motor U6 — main
- HEAD d4af4d7629a79a24918325fdf9b89bc2f9c20821. Último commit actualiza solo snapshots de auditoría.
- Run Actions 42811851624 terminó success a las 06:00 CDMX; es auditoría/snapshot, no corrida predictiva.
- codebase-memory-mcp documentado/configurado localmente; índice del 7-nov pendiente de reindexación y proceso vivo no verificado. No hay integración DSH confirmada.
- Solo lectura; motores canónicos, patterns_final_v14.json y candados no modificados.

### Migración y cuentas
- marcojpad-hash: once repositorios visibles; marcosabines-hash: cero. Ocho repositorios DESCUBIERTO_ADICIONAL, solo metadatos/documentación; dos adicionales nuevos son microserie-heredera-sadtalker y microserie-heredera-voces.
- Handoff de recuperación sigue PENDIENTE, sin acuse verificable de segunda sesión/modelo. Migración incompleta.


## Actualización de entrega — 2026-11-10, 16:16 CDMX

Reporte: [ENTREGA_PENDIENTES 2026-11-10](reportes/2026-11-10_ENTREGA_PENDIENTES.md).

### CAPCOT — ASTRA y dato 23:30
- ASTRA: guion narrativo separado y releído en `capcot-capsulas-imaginantes/main/cola/entrada/2026-11-09_dato-robot-ensambla-orbita/GUION_NARRACION.md`. Nueve escenas, 210 palabras, 88 s total. No se regeneraron PNGs. El estado registra nueve frames generados por Grok y disponibles en el chat; no se afirma que los binarios estén subidos a `frames/`.
- Dato 23:30 del 10-nov: `2026-11-10_dato-adn-sincroniza-flujo`, storyboard + fuentes + estado en CAPCOT/feature. QA narrativo PASS 91/100; 8 escenas, 195 palabras, 84 s; seis campos obligatorios presentes en las ocho escenas. Revisión estructural estática contra el validador: PASS; el script Python no se ejecutó por falta de runtime local.
- El paquete permanece en `proyectos/`, no en `cola/entrada/`; no se disparó workflow ni se creó estado Grok. Recepción/selección/producción siguen sin confirmar.

### Migración — segunda sesión
- Reemitida solicitud en `bandeja/2026-11-10_SEGUNDA_SESION_RECUPERACION.md`.
- El acuse de destinatario continúa PENDIENTE; no hay evidencia de una sesión independiente que haya leído los tres repositorios o verificado conectores. **Migración INCOMPLETA**.

## Actualización de estado — 2026-11-11

### Motor U6
- Rama de trabajo vigente por contrato: `alterno/cameo-pesos`; `main` queda `SOLO_CONSULTA`.
- Hashes canónicos recalculados y coincidentes: Engine V5 `665c39a2861e58772522e91272563260d980908b1d4ab9f7092d3413d0c36082`; catálogo 244 `d827dcc3882634ec2d21b3a480d0fee811b28d8fa1b73bab04f0af2c2d6667a1`.
- Puente Schrödinger V0_1/V0_2 revisado de forma estática. Informe: [REVISION_SCHRODINGER_V0_1](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/informes/2026-11-11_REVISION_SCHRODINGER_V0_1.md). Dictamen `NO_APROBABLE`: bug p=0 en μ⁻, punto medio no equivalente al promedio de posiciones crudas, no se propaga no convergencia, lados vacíos y masa agregada mal caracterizados. El sensor está cableado, pero es lateral/diagnóstico y no decide H. Sin cambios de código ni ejecución de tests.
- La rama activa no tiene runs de Actions para estos tests. Los tests Schrödinger existen, pero no están incluidos en `run_tests_unico.py`.
- En `main`, el A/B Mozart del 10-nov tuvo dos intentos fallidos (SyntaxError y ModuleNotFoundError) y un run final exitoso que dejó resultados en `work/mozart-ab-20261110`; H1/H2 quedaron iguales con y sin Caldero. No se fusionó ese resultado a la rama activa. El snapshot Actions 43017260379 es auditoría, no corrida predictiva.

### CAPCOT
- No se produjo storyboard del 11-nov al último chequeo; investigador 08:00 seguía `in_progress`.
- Último storyboard: 10-nov DNA, narrative_qa PASS/91, en `proyectos/`; no existe estado Grok individual: `RECEPCION_GROK_NO_CONFIRMADA`.
- 10-nov comida/aprendizaje PASS/92 con campo `estado` obsoleto y sin slot oficial; 9-nov robot PASS/90 en entrada anidada sin estado Grok; 7-nov clavo en entrada anidada sin QA.
- Workflow de Grok: trigger de entrada solo a nivel superior; los paquetes anidados no se despachan por el workflow actual.
- Horario 11-nov: ballena publicada 07:00; Mpemba programado 13:30 YT/TT/FB; corneja programada 17:00 YT/TT; 23:30 sin paquete. El prompt investigador excluye 23:30. No se produjo duplicado.
- No se generaron medios ni se publicaron contenidos. No se gastaron créditos.

### Herramientas y migración
- codebase-memory-mcp configurado localmente en U6/alterno, pero sin proceso vivo ni índice actualizado de esa rama; ausente en CAPCOT/feature. DeepSeek Harness ausente en ambos repositorios activos; no hay conector ejecutable en esta sesión.
- La sesión Claude del 10-nov dejó acuse separado parcial (U6 + orquestador, no CAPCOT; cuenta/dudas pendientes). El acuse requerido en `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` sigue pendiente; migración incompleta.



## Actualización operativa — 2026-11-12

### CAPCOT — feature/capcot-video-discovery-continuity
- No había storyboard, radar ni horario fechado 12-nov al corte; el investigador del día seguía IN_PROGRESS, por lo que el chequeo es provisional.
- El paquete `2026-11-11_dato-ratas-topo-damaraland` se incorporó a `cola/entrada/<project_id>/` después de la auditoría del 11-nov. Tiene 8 escenas/212 palabras, pero no `narrative_contract` ni `narrative_qa`; incluye `asset_filename` y `export.filename`. Hay ocho PNG en `frames/`.
- No existe `salidas/<project_id>/` ni `cola/estado/<project_id>.json`. El ID `knAElNo4raI` aparece en endscreens del 12-nov con 220 vistas, pero no en `data/publicaciones.json` ni `data/rotacion.json`; publicación no confirmada. No se movió el paquete por la señal contradictoria de producción ya realizada.
- El workflow de dispatch solo procesa `cola/entrada/*.json` en profundidad 1; la carpeta anidada no es dispatchable.
- El slot 23:30 sigue en conflicto con la exclusión del prompt investigador. No se cambió agenda ni prompt.

### Motor U6 — alterno/cameo-pesos
- La rama activa contiene la entrega F003/F004 del 11-nov: manifiesto con 20 casos `ok:true` y recibos `COMPLETED`; la revisión reporta dos rutas faltantes en cada recibo, sin tabla de mortalidad y `NOT_CALIBRATED_NO_CASE_LEVEL_OUTCOMES`.
- Los cuatro hashes de `motor/runs/F003_F004_20261111/LECTURA.json` no coinciden con los documentos actuales. No se ejecutó el candado; el paquete queda pendiente de revalidación.
- La prueba del negativo con cinco hipótesis en Napoleón produjo 5→5 y cero descartes; el proxy Ricci no generó aristas negativas y ambos z quedaron bajo `Z_MIN=2.0`.
- Sin cambios a código, Engine V5, catálogo 244, candados ni tests.

### Migración
- `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` continúa PENDIENTE. El acuse separado de Claude no cumple la aceptación completa. Migración INCOMPLETA.


## Actualización operativa — 2026-11-13

### Motor U6 — rama `alterno/cameo-pesos`

- **Issue #64:** corrección en [PR #8](https://github.com/marcojpad-hash/motor-u6-storage/pull/8), abierto y sin merge. El runner incorpora el guardián Z90, rechaza post-Z con código 8 y deja `previo_error`/`visto_error` en `False` si no hay error. GitHub Actions `runner-contract` SUCCESS. No se modificaron `Engine_V5_CANONICO_SOLO.py` ni `patterns_final_v14.json`.
- **F003/F004:** 20 recibos COMPLETED. Erratas y discrepancias registradas en [PR #9](https://github.com/marcojpad-hash/motor-u6-storage/pull/9), abierto y sin merge: el resumen omitía 3 FIRME; la tabla deja Monte Carlo en null aunque recibos consultados muestran ejecución; `H1_rank_fusion` es null en el manifiesto aunque la tabla tiene valores. `consulta_dirigida` está `NO_CONFIGURADO/off`, 0 preguntas y `required=false`, por lo que no cumple el Issue #50.
- `LECTURA.json` conserva hashes de versiones anteriores de documentos. El candado compara SHA contra el árbol actual; no se ejecutó y no se declara aprobada la entrega. No se reescribió la evidencia histórica.
- La prueba negativa de Napoleón sigue 5→5, cero descartes. Sin cambio de resultado.

### CAPCOT — rama `feature/capcot-video-discovery-continuity`

- **ASTRA robot, 9-nov:** el registro de `main` ubica nueve PNG generados en la conversación de Grok.com del 9-nov. En el repositorio, `frames/` solo contiene `.gitkeep`; no hay binarios para convertir. Se indicó esa ubicación en el estado de ejecución mediante [PR #4](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/pull/4), abierto y sin merge. La subida JPEG sigue pendiente de recuperar los PNG desde Grok. El marcador `grok_inbox` sigue pending; no hay recibo `grok_done`.
- **Ratas topo Damaraland, 11-nov:** hay ocho PNG y dos publicaciones registradas (IDs `knAElNo4raI` y `WcTviUWqbes`). Marco autorizó conservar ambos videos publicados. La carpeta no tiene un estado individual/Grok receipt consistente; no se redispatcha ni se duplica.
- **Chimpancés, 12-nov:** candidato con narrative QA PASS 91, 198 palabras y 84 s, todavía en `proyectos/`, sin slot oficial ni promoción a cola.
- El workflow `capcot-grok-dispatch.yml` espera JSON plano en `cola/entrada/*.json`; no reconoce la estructura vigente `cola/entrada/<project_id>/storyboard.json`. Además, el workflow solo crea un handoff o llama un webhook opcional; no genera imágenes por sí mismo. No se ejecutó ni publicó nada.
- La exclusión de 23:30 en el prompt del investigador sigue en conflicto con la instrucción editorial de dato del día a esa hora.

### Integraciones y continuidad

- `codebase-memory-mcp`: configuración local en U6 y en CAPCOT/main; ausente en CAPCOT/feature. El `.mcp.json` apunta a una ruta absoluta de la máquina de Pecas. No hay herramientas de ese servidor disponibles en esta sesión; índice de main del 7-nov no equivale a índice de rama activa.
- DeepSeek Harness no está integrado de forma ejecutable en las ramas activas. FreeLLMAPI tiene 0 claves; la prueba Groq previa devolvió 429; Ollama no está verificado.
- PR #62 de `agente-cero-costo` contiene solo la plantilla parcial del supervisor. No hay wrappers `supervisor.yml` en los seis repos; no están implementados guardia/config estricta, cinco estados, compuerta ni creación de issue de fallo. Issue #36 sigue abierto. #37, #38 y #47–#50 también siguen pendientes.
- El handoff de recuperación `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` continúa PENDIENTE; no hay acuse verificable de una segunda sesión independiente.

### Archivos y automatizaciones

- El primer ZIP sigue siendo una copia de la Biblioteca de ChatGPT; el segundo `MOTOR_UNICO_ESTANDAR_20260928_FILTRO_ENTRADA.zip` no está en la Biblioteca. El conector de Google Drive aparece deshabilitado por administración; no se afirma acceso al Drive. El segundo archivo sigue pendiente de adjuntarse aquí.
- Investigador CAPCOT y operador general siguen programados a las 08:00 CDMX; auditor CAPCOT a las 15:00 CDMX. Los últimos runs disponibles son del 12-nov; todavía no hay ejecución del 13-nov al corte de esta actualización.
