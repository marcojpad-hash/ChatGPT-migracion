# Proyectos y estado — corte 2026-11-01

## Fuente de verdad por proyecto

| Proyecto | Repositorio / ubicación | Estado actual | Pendientes reales |
|---|---|---|---|
| CAPCOT / Datos y ociosidades | `capcot-capsulas-imaginantes`, `feature/capcot-video-discovery-continuity` | Compuerta narrativa implementada. 33 project_id/116 archivos heredados en `cola/bloqueados/`; cero storyboards en `cola/entrada/`. | Reanudar con borradores en `proyectos/`, QA independiente PASS y promoción raíz; falta `GROK_WEBHOOK_URL`, radar 1-nov y acuse Grok. |
| Motor U6 / V15.3 | `motor-u6-storage`, `main` | F006 R7 registrado como reevaluación; protocolo de custodia independiente creado. Engine V5 y catálogo 244 intactos. | C01–C20 siguen pendientes; se requieren sujetos nuevos, fuente pre-Z y separación real entre preparador y custodio. |
| Orquestador Central | `orquestador-central`, privado | Repositorio adicional descubierto. PR draft #1 en `feature/core-mvp-l1`; 2 checks CI exitosos, 3 pruebas cada uno. | No está desplegado ni integrado; faltan pruebas HTTP, recuperación de tareas atascadas, adaptadores, runtime persistente y entrada/salida entre canales. No fusionar ni desplegar sin autorización. |
| Migración ChatGPT | `ChatGPT-migracion`, `main` | Continuidad, estilo, coordinación y auditoría transversal. | Mantener horarios, ejecuciones y estados reales actualizados. |
| Notion operativo Motor | Workspace Notion | Páginas antiguas conservadas como archivo histórico. | GitHub prevalece ante contradicciones; el workspace alcanzó el límite de bloques gratuitos. |
| Analítica social | Conector externo | No hay conexión privada confirmada. | Requiere autorización OAuth del titular para métricas privadas. |

## CAPCOT — estado y handoff

- Auditoría del 1-nov: [CONTROL_COLA](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-01_CONTROL_COLA.md), commit final `e8bd58a9066c1709d3e51709b6330871143a538f`.
- Cinco piezas asignadas a slots del 1-nov: Xolo, pulpo, cebolla, Baffin y tiburón; dato del día 23:30 sin paquete. Lectura en frío del auditor: Xolo 85 PASS narrativo; pulpo 72 FAIL; cebolla 84 FAIL; Baffin 78 FAIL; tiburón 89 PASS narrativo. Ninguno tenía `narrative_contract` ni `narrative_qa`; los PASS narrativos no eran PASS integral.
- Diez runs recientes de Actions fallaron; ocho logs inspeccionados reportan `Falta configurar GROK_WEBHOOK_URL.`. No hubo POST; no se llegó a comprobar `GROK_WEBHOOK_TOKEN`. No existe `cola/estado/`: recepción Grok no confirmada.
- Se implementó el staging: investigador escribe en `proyectos/<project_id>/storyboard.json`; auditor distinto del redactor oculta título, resumen, arco, notas y contrato narrativo y lee solo la narración. Solo PASS (>=85, siete checks true, flags vacíos) más validación estructural permite promoción a `cola/entrada/YYYY-MM-DD_slug.json`.
- La plantilla contiene `narrative_contract` con seis campos; el validador ahora exige esos campos y `narrative_qa` PASS. Las pruebas unitarias añadidas cubren ambos contratos.
- Se retiraron de cola 33 project_id y 116 archivos, conservando exactamente los SHA de blob, bajo `cola/bloqueados/`. Cero storyboard JSON permanece en `cola/entrada/`. El reingreso es reversible y requiere QA independiente registrado.
- Xolo permanece en `salidas/`, no en cola. Los estados Grok no se crean ni modifican.
- No se tocó `data/*.json`, workflow, secretos ni permisos. La falta de webhook requiere acción del titular.
- El run investigador del 1-nov sigue `in_progress`; no hay radar nuevo verificado. El auditor terminó antes de la actualización final del prompt; su próxima ejecución debe registrar los siete checks y el campo `narrative_qa`.


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
| Agente de investigación CAPCOT | Diario 08:00 hasta 24-nov | Run `eb74bc97-0478-832c-a823-25af9adab923` en `in_progress`; último resultado completado 31-oct. |
| Auditor CAPCOT — cola y rotación | Diario 15:00, flexible | Run `47f25beb-8e28-8324-b66b-c3923f3e90e3` completado 14:27; ejecutó 40 min antes del horario guardado. |

Las tres muestran `next_run_time=null`. Operador e investigador muestran `scheduled_for=14:20` aunque sus horarios guardados dicen 08:00; causa no identificada. Los prompts se actualizaron después del inicio de los runs.


## Dot

Dot nativo no está disponible desde esta sesión. El operador diario es sustituto parcial, no un agente persistente 24/7 ni una computadora autónoma.

## Regla de estado

Cada hecho debe marcarse como verificado, ejecutado, inferido o pendiente. Un prompt actualizado no prueba que el bot haya ejecutado; un archivo en cola no prueba recepción; un artifact no equivale a un registro versionado hasta que se incorpore al repositorio.
