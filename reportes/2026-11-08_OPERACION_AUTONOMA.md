# Operación autónoma — 2026-11-08

**Corte:** 2026-11-08, `America/Mexico_City`.
**Escritura autorizada:** únicamente `ChatGPT-migracion/main`.
**CAPCOT y Motor U6:** solo lectura.

## 1. Repositorios, ramas y cuentas

| Repositorio | Rama | HEAD observado antes de esta operación |
|---|---|---|
| [ChatGPT-migracion](https://github.com/marcojpad-hash/ChatGPT-migracion) | `main` | `895b65749a882df5b20d46b8c87d024d43468236` |
| [CAPCOT](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes) | `feature/capcot-video-discovery-continuity` | `4451ccc27ed751295cea8f1566a4eb7fc973e8d9` |
| [Motor U6](https://github.com/marcojpad-hash/motor-u6-storage) | `main` | `9ba7ee07fe8fa7ce21da0e9defb0ada9ce952949` |

Se consultaron ambas conexiones GitHub e instalaciones. `marcojpad-hash` devuelve una instalación visible (ID `174841554`, nombre de App no expuesto) y nueve repositorios: los tres principales más `orquestador-central`, `red-teaming-safety-u6`, `agente-cero-costo`, `baterias-tokens`, `baterias-memoria` y `memoria-compartida`. `marcosabines-hash` devuelve cero instalaciones y cero repositorios; la consulta no devolvió error. Los seis adicionales se clasificaron `DESCUBIERTO_ADICIONAL`; solo se revisaron README/documentación y metadatos. No se escribió en ellos.

## 2. Memoria compartida

- Leídos `memoria-compartida/PROTOCOLO_MEMORIA_COMPARTIDA_OBLIGATORIA.md`, `INDICE.md` y los hechos pertinentes: `proyectos.md`, `decisiones.md`, `estado.md`, `correcciones.md`, `tokens.md`.
- Verificado el gate en `AGENTS.md` y `README.md` de los nueve repositorios visibles, incluidos los tres repositorios y ramas de autoridad de este mandato.
- El gate está anclado, pero no se auto-inyecta en una conversación ordinaria ni demuestra que una segunda sesión lo haya leído. El handoff de recuperación sigue sin acuse.
- No se escribió en `memoria-compartida` porque es un repositorio adicional fuera del alcance de escritura de este mandato. La sincronización del nuevo corte allí queda pendiente de inclusión expresa; la continuidad se registró en este repositorio.
- Se corrigió en `ChatGPT-migracion/README.md` un defecto de formato: el banner del gate tenía los caracteres literales `\n\n` en lugar de saltos de línea reales.

## 3. CAPCOT

### Auditoría y automatización

- El auditor `8159484e-7a74-8329-b4f1-3c4c362d862a` terminó el 7-nov a las 15:53:56 CDMX. Su reporte `docs/briefs/2026-11-07_CONTROL_COLA.md` registra 12 storyboards canónicos: 2 PASS narrativos, 10 FAIL, 0 estructuralmente aptos y 0 promociones. No hay run de auditor del 8-nov al corte.
- El investigador del 8-nov, run `5157ac9d-4c8c-8327-b7e0-1974d934f415`, inició a las 08:00:50 CDMX y seguía `in_progress`, sin `completed_at`. Su último resultado completado sigue siendo `NO_DUPLICAR` del 7-nov; no se atribuyó trabajo nuevo.

### Paquete clavo / slot 23:30

- El storyboard `cola/entrada/2026-11-07_dato-clavo-te-cocina/storyboard.json` existe dentro de una carpeta anidada; SHA `a32671cf27bbe6a96a7a2b3a050c52813e4bf2e6`.
- El JSON no tiene `narrative_qa`. Sus ocho escenas carecen de los seis campos obligatorios: `dramatic_beat`, `scene_function`, `causal_bridge_from_previous`, `question_state`, `reason_to_continue`, `new_information`.
- El workflow vigente `.github/workflows/capcot-grok-dispatch.yml` (SHA `47bbd228cfce5a1d402dc952e283e8d0f8e37030`) solo selecciona JSON de primer nivel en `cola/entrada/*.json`; la carpeta anidada no es despachable por ese workflow.
- `cola/estado/2026-11-07_dato-clavo-te-cocina.json` devolvió 404: `RECEPCION_GROK_NO_CONFIRMADA`. No se creó ni modificó estado Grok.
- `cola/entrada/.../ESTADO_EJECUCION.md` dice `publicación/programación: NO_REALIZADA`. En cambio, `data/horario_2026-11-08.json` y `ajustes_entre_modelos/ESTADO_SLOTS_2026-11-08.md` registran el slot 23:30 como programado en YT/TT/FB. El ID no aparece en `data/publicaciones.json` ni en `data/rotacion.json`. Es un conflicto documental; no se consultaron directamente las plataformas y no se movió, canceló ni redispatchó el paquete.
- El registro del 8-nov dice que el slot 07:00 de palomitas ya estaba publicado en las tres plataformas y que no se volvió a subir. Es evidencia documental del registro, no una consulta directa de las plataformas.
- No hay storyboard con fecha objetivo 8-nov en `proyectos/` al corte. No se creó otro; el investigador del día seguía `in_progress`.

### Divergencia CAPCOT main/feature

- `main...feature/capcot-video-discovery-continuity` devuelve `diverged`: feature 650 commits adelante y 103 detrás.
- CAPCOT/main contiene `docs/CODEBASE_MEMORY_MCP.md`, `.mcp.json`, `docs/DSH_CERO_COSTO.md` y `ajustes_entre_modelos/DELEGACIONES.md`. Esos archivos no existen en la rama activa feature (404).
- El tablero de main declara cinco pendientes (montaje Mpemba, montaje Barreleye, workflows de seguridad, seguridad nativa de GitHub y cuenta Clayzo); no se trató como tablero vigente de feature ni se actuó sobre ellos.
- No se cambió rama, no se fusionó y no se modificó CAPCOT.

## 4. Motor U6

- `main` contiene `docs/CODEBASE_MEMORY_MCP.md` (SHA `760e4e473e00c3c89e3c11919210e3be49d59891`) y `.mcp.json` (SHA `93f6ef5077168bef51f6dd989921fbd732e4f26c`). La configuración apunta al binario local `/home/hatch/workspace/codebase-memory-mcp/bin/codebase-memory-mcp`.
- El documento reporta versión 0.12.1 e índice del 7-nov de 13 531 nodos / 27 173 aristas. Es un registro de instalación/indexación en la máquina de Pecas, no una conexión viva en esta sesión de ChatGPT. El índice debe actualizarse tras cambios del repo; el commit del 8-nov añadió el gate en `AGENTS.md` después del snapshot.
- El último commit observado `9ba7ee07fe8fa7ce21da0e9defb0ada9ce952949` modificó únicamente `AGENTS.md`. No se tocaron `Engine_V5_CANONICO_SOLO.py`, `patterns_final_v14.json`, motores canónicos ni candados.
- `avances/auditoria_corridas/ULTIMO_ESTADO.md` registra el workflow `ChatGPT startup contract` run `42485950750` como `success` (07:38:52–07:39:02 CDMX) y la auditoría programada `42483106817` como `success` (07:03:23–07:04:43 CDMX). Son checks/snapshots de Actions, no nuevas corridas predictivas.
- No se ejecutó ni modificó Motor U6.

## 5. codebase-memory-mcp y DeepSeek Harness

- `codebase-memory-mcp` está documentado/configurado en U6/main y CAPCOT/main; CAPCOT feature no lo tiene. Los índices documentados son del 7-nov y requieren reindexación tras cambios. No hay herramientas MCP de codebase-memory expuestas en esta sesión.
- `DeepSeek Harness` está documentado en CAPCOT/main y configurado como componente del repo adicional `agente-cero-costo`; no está integrado en CAPCOT feature ni U6 main.
- La prueba de humo documentada para dsh `0.2.2-rc.1` con Groq gratuito falló al segundo llamado por límite de 8 000 TPM / HTTP 429; el archivo de prueba no se creó. Por tanto, no se cuenta como agente funcional de punta a punta a costo cero.
- La distinción se corrigió en `docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md`: codebase-memory es un MCP de grafo estructural; DSH es un harness de agente.

## 6. Automatizaciones

| Automatización | Run observado | Estado |
|---|---|---|
| Investigador CAPCOT | `5157ac9d-4c8c-8327-b7e0-1974d934f415`; iniciado 8-nov 08:00:50 CDMX. | `in_progress`, sin `completed_at`; último resultado completado 7-nov. |
| Auditor CAPCOT | `8159484e-7a74-8329-b4f1-3c4c362d862a`; completado 7-nov 15:53:56 CDMX. | `completed`; no run 8-nov al corte. |
| Operador autónomo general | `34d391e0-4918-832b-9fdb-6f3531295c37`; iniciado 8-nov 07:57:17 CDMX. | `in_progress`, sin `completed_at`; último resultado completado 7-nov. |

Inventario general: 16 automatizaciones, 3 habilitadas y 13 deshabilitadas. Las tres habilitadas devuelven `next_run_time=null`. No se atribuyó éxito a los dos runs `in_progress`. Dot no está conectado a esta sesión.

## 7. Migración y handoff

`bandeja/2026-11-03_RECUPERACION_MIGRACION.md` fue releído: estado `PENDIENTE`, acuse del destinatario vacío y verificación del emisor pendiente. La migración no está completa.

## 8. Cambios ejecutados en ChatGPT-migracion/main

| Archivo | Cambio | Commit |
|---|---|---|
| `README.md` | Corregidos saltos de línea literales del banner de memoria compartida. | `37602f451c45743c0ed43adeb7b93901703d113a` |
| `docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md` | Inventario de nueve repositorios, gate universal, estado real de codebase-memory-mcp/DSH y divergencia CAPCOT. | `10e696c4d977bdd2d7873bc282e48e36fbdd41f7` |
| `PROYECTOS_Y_ESTADO.md` | Corte vigente CAPCOT/U6 y bloqueos de rama/handoff. | `e1850357ced6bffe76ca7a06e6d69b0ed4aa7cf5` |
| `BOT_DOT_AUTONOMIA.md` | Últimos runs, estados terminales y límites de Dot. | `eeecb2e736fa3d2627f3a104576b3047916ce98b` |
| `docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md` | Aceptaciones completadas y pendientes actualizadas. | `01476ec1a8f81467756fff004d00e01be9291ad0` |
| `CONTINUIDAD_CHATGPT.md` | Corte operativo y enlace al reporte. | `aaae4443f13a1b88536bc97db5b5bb6cbc975e14` |

Nota de historial: el commit intermedio `4b177f191435751741818d6fb4a3a972f1a8dbef` conservó el mismo blob del reporte y no cambió su contenido.

Se releyeron desde GitHub los seis documentos actualizados. Blobs verificados: README `1172661c549e41b4b2ecb9eb40e5ef3ca92b02be`; mapa `4ba4729725dad6778696207f6ce2aba0650062d9`; estado `f0a1d45e5664c7fd04a8a10a372cfd350960e181`; automatizaciones `37337507ad26003f8dac1fbf27215eab49c51aea`; checklist `eddd8855c28f21ea8f0d56cc6a9e338766da2990`; continuidad `7a55a62a0b39b3b41da6cf46f9ad22d34d0114c1`. No hubo cambios en CAPCOT, Motor U6 ni repositorios adicionales. No se cambiaron permisos, credenciales, ramas, workflows, datos, medios ni publicaciones.

## 9. Bloqueos abiertos

1. Segundo modelo/sesión no ha acusado el handoff de migración.
2. Los runs de investigador CAPCOT y operador general del 8-nov seguían `in_progress` al corte.
3. El paquete clavo carece de QA narrativo, estructura requerida y estado Grok; el registro de programación contradice su estado de ejecución.
4. La rama activa CAPCOT no contiene la integración MCP/DSH que sí aparece en `main`; las ramas están muy divergidas y no se fusionaron.
5. Los índices codebase-memory documentados son del 7-nov; no se reindexaron ni se verificaron desde esta sesión.
6. DeepSeek Harness no completó la prueba gratuita de extremo a extremo con Groq.
7. La memoria compartida no recibió este nuevo corte porque su repositorio es adicional y no está autorizado para escritura en este mandato.