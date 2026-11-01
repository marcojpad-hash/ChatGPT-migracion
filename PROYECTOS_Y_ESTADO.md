# Proyectos y estado — corte 2026-11-01

## Fuente de verdad por proyecto

| Proyecto | Repositorio / ubicación | Estado actual | Pendientes reales |
|---|---|---|---|
| CAPCOT / Datos y ociosidades | `capcot-capsulas-imaginantes`, `feature/capcot-video-discovery-continuity` | Investigación 08:00; auditoría 15:00. Hay paquetes del 1-nov en cola anidada y salidas. | Confirmar recepción Grok; resolver dispatchabilidad de paquetes anidados y falta de secretos webhook; corregir rutas asset_filename no materializadas; auditar rotación/QA sin tocar `data/*.json`. |
| Motor U6 / V15.3 | `motor-u6-storage`, `main` | F006 R7 registrado como reevaluación; protocolo de custodia independiente creado. Engine V5 y catálogo 244 intactos. | C01–C20 siguen pendientes; se requieren sujetos nuevos, fuente pre-Z y separación real entre preparador y custodio. |
| Orquestador Central | `orquestador-central`, privado | Repositorio adicional descubierto. PR draft #1 en `feature/core-mvp-l1`; 2 checks CI exitosos, 3 pruebas cada uno. | No está desplegado ni integrado; faltan pruebas HTTP, recuperación de tareas atascadas, adaptadores, runtime persistente y entrada/salida entre canales. No fusionar ni desplegar sin autorización. |
| Migración ChatGPT | `ChatGPT-migracion`, `main` | Continuidad, estilo, coordinación y auditoría transversal. | Mantener horarios, ejecuciones y estados reales actualizados. |
| Notion operativo Motor | Workspace Notion | Páginas antiguas conservadas como archivo histórico. | GitHub prevalece ante contradicciones; el workspace alcanzó el límite de bloques gratuitos. |
| Analítica social | Conector externo | No hay conexión privada confirmada. | Requiere autorización OAuth del titular para métricas privadas. |

## CAPCOT — estado y handoff

- El storyboard `2026-10-31_pardelas-jetlag-solar.json` se releyó desde GitHub: `approved_assets=[]`, `export.render_status=NOT_GENERATED`, `publicacion.status=PENDIENTE_DECISION_GROK`; SHA de contenido `018cdca9cc8591fe787601c296b9047291d90b9b`.
- No existe `cola/estado/2026-10-31_pardelas-jetlag-solar.json`: **RECEPCION_GROK_NO_CONFIRMADA**. El contrato `docs/GROK_STATUS_CONTRACT.md` reserva ese archivo a Grok.
- El archivo adicional `*_fuentes.md` del paquete de pardelas ya no está en la rama actual (404); las fuentes están dentro del JSON.
- Los storyboards anidados del 1-nov para cebolla y pulpo tienen 8 escenas, 231/228 palabras y 90 s incluyendo cortinilla; voz correcta y `approved_assets=[]`. Sin embargo, cada uno contiene ocho `asset_filename` apuntando a `frames/scene_00X.jpg`, y no hay archivos de frame correspondientes.
- Esos dos paquetes viven en `cola/entrada/<project_id>/storyboard.json`. El workflow `.github/workflows/capcot-grok-dispatch.yml` solo escucha `cola/entrada/*.json` y el modo `all` busca archivos de primer nivel (`maxdepth 1`). Por tanto, los dos paquetes anidados no son seleccionados por el despacho actual.
- El workflow fue reparado y ampliado para lote, pero la prueba real de entrega se detuvo antes del envío por falta de `GROK_WEBHOOK_URL`; no llegó a comprobar `GROK_WEBHOOK_TOKEN`. No hay ACK ni estado Grok confirmado.
- No modificar `data/*.json`, no crear estados Grok, no inferir recepción desde cola/salidas/programación de plataforma y no generar medios desde el operador general.

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

| Automatización | Horario CDMX | Último estado observado |
|---|---:|---|
| Operador autónomo general | 08:00 | Run del 1-nov `in_progress`; no declarar completado. |
| Agente de investigación CAPCOT | 08:00 | Último run completado 31-oct; el horario guardado se corrigió de 08:30 a 08:00 el 1-nov. Run del 1-nov no confirmado al corte. |
| Auditor CAPCOT — cola y rotación | 15:00 | Último run completado 31-oct bajo el mandato de auditoría. |

`next_run_time` aparece nulo en las tres consultas. Una programación habilitada no garantiza por sí sola que el siguiente run haya sido creado.

## Dot

Dot nativo no está disponible desde esta sesión. El operador diario es sustituto parcial, no un agente persistente 24/7 ni una computadora autónoma.

## Regla de estado

Cada hecho debe marcarse como verificado, ejecutado, inferido o pendiente. Un prompt actualizado no prueba que el bot haya ejecutado; un archivo en cola no prueba recepción; un artifact no equivale a un registro versionado hasta que se incorpore al repositorio.
