# Lote CAPCOT 5–7 nov — staging y compuerta Auditor

Fecha de operación: 2026-11-02 (CDMX)  
Fuente de instrucciones: [PARA_CHATGPT_5-7nov_PASS_auditor.md](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/ajustes_entre_modelos/PARA_CHATGPT_5-7nov_PASS_auditor.md)  
Commit de la instrucción: `ca29f89630292e5666ee1e02c86988563562ec8e`

## Resultado ejecutado

Se crearon y releyeron 12 archivos canónicos en `proyectos/<project_id>/storyboard.json` en la rama `feature/capcot-video-discovery-continuity`.

Commit de staging: `7a415426f5907c2ab03687a47f3d160a595cb669`  
[Ver commit de staging](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/commit/7a415426f5907c2ab03687a47f3d160a595cb669)

| Fecha | Slot CDMX | ID canónico | Resultado |
|---|---:|---|---|
| 5-nov | 07:00 | `2026-11-05_kids-dia-en-venus` | Staged |
| 5-nov | 13:30 | `2026-11-05_comida-palomitas` | Staged |
| 5-nov | 17:00 | `2026-11-05_inter-arboles-se-comunican` | Bloqueado: el borrador fuente trata respiración nocturna, no red micorrícica/wood-wide web de Karst et al. 2023 |
| 5-nov | 17:45 | `2026-11-05_inter-rayo-globular` | Staged; hora antigua 19:00 corregida a 17:45 |
| 6-nov | 07:00 | `2026-11-06_kids-ballena-azul-corazon` | Staged |
| 6-nov | 13:30 | `2026-11-06_comida-aguacate-negro` | Staged |
| 6-nov | 17:00 | `2026-11-06_inter-ranas-congeladas` | Staged |
| 6-nov | 17:45 | `2026-11-06_inter-arena-cantante` | Staged; hora antigua 19:00 corregida a 17:45 |
| 7-nov | 07:00 | `2026-11-07_kids-huesos-bebe` | Staged |
| 7-nov | 13:30 | `2026-11-07_comida-hielo-caliente` | Staged |
| 7-nov | 17:00 | `2026-11-07_inter-pulpo-suenos` | Staged |
| 7-nov | 17:45 | `2026-11-07_inter-nubes-pesan` | Staged; ID canónico inter |

## Compuertas y verificación

Los 12 JSON se releyeron desde GitHub y pasaron las comprobaciones mecánicas siguientes:
- `project_id`, `fecha_objetivo`, `slot_local` y `slot_cesta` corresponden a los 12 slots del horario.
- Los seis campos de `narrative_contract` están presentes y no vacíos.
- Siete escenas por storyboard.
- No existe `narrative_qa`: ChatGPT no se autoevaluó.
- `approved_assets=[]`, `export.render_status=NOT_GENERATED` y `publicacion.status=PENDIENTE_DECISION_GROK`.
- No se escribió ningún archivo en `cola/entrada/` ni se modificó `data/horario_semana_2026-11-01_07.json`.

### Excepciones documentadas

1. `2026-11-05_inter-arboles-se-comunican`: el borrador disponible no corresponde al tema asignado. Se conserva en `proyectos/` con estado `BORRADOR_BLOQUEADO_POR_DESAJUSTE_DE_TEMA`; el prompt del Auditor exige FAIL por este desajuste. Necesita un storyboard correcto sobre red micorrícica/wood-wide web antes de promoción.
2. `2026-11-07_inter-nubes-pesan`: se eligió una sola versión canónica. Se fusionó el ejemplo cuantitativo y la fuente específica USGS de la variante inter con la distinción nube pequeña/tormenta y la explicación de suspensión de la variante extra. La variante extra no se volvió a crear como proyecto.
3. Los originales en `cola/bloqueados/` se conservaron como archivo fuente; no se borraron. Las 12 rutas nuevas en `proyectos/` son las únicas copias canónicas de trabajo para el Auditor.

## Automatizaciones actualizadas

- **Investigador CAPCOT** (`6ae5827ecc808191a36a8c773cc2990a`): prompt actualizado para reconocer las 12 rutas canónicas, no duplicarlas ni reescribirlas, respetar el bloqueo temático de árboles y excluir dato 23:30, kids 3-nov y Machu Picchu 4-nov.
- **Auditor CAPCOT** (`6adcf23ae7208191b09e51ebca9eba4a`): prompt actualizado para revisar los 12 IDs en cada ejecución, incluso antes de la fecha del slot; hacer lectura en frío solo de narración, comprobar los siete checks, el contrato, la estructura y la correspondencia tema-slot; promover solo PASS.
- Se guardó el DTSTART del Auditor para el 3-nov-2026 a las 15:00, zona `America/Mexico_City`. La automatización sigue reportando `timing_mode=flexible_schedule`; por tanto, la hora exacta no queda garantizada por la configuración expuesta. El último run registrado terminó antes de esta actualización; no se atribuye a ese run el nuevo lote ni el nuevo prompt.
- El investigador no se ejecutó manualmente para evitar duplicar trabajo. No se ejecutó manualmente el Auditor; el primer run con el nuevo prompt queda para su siguiente ciclo.

## Fuera de alcance

- No se crearon slots 23:30 de dato del día.
- No se incluyó kids 3-nov 07:00.
- No se incluyó Machu Picchu 4-nov 19:00.
- No se creó `narrative_qa`, no hubo PASS simulado, no hubo promoción a cola, no se modificó el horario, no se generaron medios, no se publicó ni se afirmó recepción Grok.
- No se eliminaron archivos fuente ni se modificaron secretos, permisos o workflows.

## Estado final

**12 copias canónicas staged; 11 esperan QA independiente; 1 bloqueada por desajuste tema-slot. 0 promovidas.**  
**Handoff Grok:** se comprobaron las 12 rutas `cola/estado/<project_id>.json`; las 12 están ausentes. Resultado: `RECEPCION_GROK_NO_CONFIRMADA` para todos. Se leyó `docs/GROK_STATUS_CONTRACT.md`: Grok es el único responsable de crear/actualizar esos estados; ChatGPT solo los lee. No se creó ni modificó ningún archivo de estado. Ningún commit ni presencia en cola equivale a recepción.
