# Operación autónoma — 17-nov-2026

## Alcance y autorización

Se leyó primero en `marcojpad-hash/ChatGPT-migracion/main`:

- `CONTINUIDAD_CHATGPT.md`
- `ESTILO_DE_TRABAJO.md`
- `BOT_DOT_AUTONOMIA.md`
- `PROYECTOS_Y_ESTADO.md`
- último registro de auditoría transversal
- `docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md`
- `docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md`
- `docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md`
- orden de Puta3 en `bandeja/2026-11-17_PUTA3_CHECKPOINTS_MOTOR.md)

Se trabajó en lectura y verificación de los repositorios autorizados. Solo se escribieron artefactos de continuidad/handoff en `ChatGPT-migracion/main`. No se modificaron Motor U6, CAPCOT, Orquestador Central, motores canónicos, catálogo, candados, permisos, ramas ni credenciales.

## Cuentas, repositorios y conexiones

### GitHub

Instalación consultada: `marcojpad-hash`. Repositorios devueltos (11):

- `ChatGPT-migracion`
- `agente-cero-costo`
- `baterias-memoria`
- `baterias-tokens`
- `capcot-capsulas-imaginantes`
- `memoria-compartida`
- `microserie-heredera-sadtalker`
- `microserie-heredera-voces`
- `motor-u6-storage`
- `orquestador-central`
- `red-teaming-safety-u6`

La cuenta `marcosabines-hash` no devolvió una instalación GitHub elegible; por tanto no se afirma que no tenga repositorios. `orquestador-central` y `memoria-compartida` se clasificaron como `DESCUBIERTO_ADICIONAL`; se revisaron solo metadatos/documentación y no se escribieron.

### Conexiones

- GitHub: conectado y operativo.
- Notion: conectado. Las páginas V15 encontradas son de septiembre (20/22-sep) y se trataron como históricas, subordinadas al repo Motor U6.
- Dropbox: cuenta personal conectada; no apareció una cuenta de equipo.
- Google Drive: no se expuso un conector ejecutable en esta sesión.
- Dot: no se expuso un conector ejecutable. No se atribuyó acceso a Dot.
- n8n: la skill/workflow-check no equivale a un conector ejecutable; no apareció conector n8n.
- La Biblioteca personal de archivos sí permitió localizar y materializar los checkpoints indicados en el manifiesto.

No hubo cambio esencial de conexión; por eso no se alteraron `MAPA_HERRAMIENTAS` ni el checklist de migración.

## Estado de automatizaciones

Se consultaron estados y últimas ejecuciones antes de atribuirles trabajo.

| Automatización | Evidencia actual | Resultado operativo |
|---|---|---|
| Agente de investigación CAPCOT | Run `9832ba02-4954-8322-b8b2-2f5629fb5e20`, programado 08:00, iniciado 08:04:41, completado 08:21:19 CDMX | COMPLETED. Dejó radar y storyboard en `proyectos/`; no hizo QA narrativa ni recepción Grok. |
| Auditor CAPCOT — cola y rotación | Run `1194dae9-4e94-8324-aa93-9422e489f568`, programado 16-nov 15:00, iniciado 15:45:43, completado 16:08:15 CDMX | No hay corrida del 17-nov. No se atribuyó QA del día. |
| Operador autónomo general | Run `29d3cb8a-531c-8326-8222-3aed2965cd1f`, programado 08:00, iniciado 09:00:16 CDMX | IN_PROGRESS al momento de inspección; esta entrega corresponde a esa corrida. El resultado previo de la automatización era del 15-nov y no se contó como trabajo de hoy. |

**Tarea ausente:** la lista de automatizaciones activas solo devolvió esas tres; no aparece el monitor de bus GitHub solicitado para las 09:00.

**Dispatch Grok:** la última ejecución documentada del workflow falló por `GROK_WEBHOOK_URL` ausente. El código posterior permite el modo de inbox sin webhook, pero no se encontró una ejecución posterior que verifique ese cambio. No se inventó recepción.

No se creó ni deshabilitó ninguna automatización.

## CAPCOT — handoff del 17-nov

Repositorio `marcojpad-hash/capcot-capsulas-imaginantes`, rama `feature/capcot-video-discovery-continuity`, HEAD `c47a7ceab2cf75570943942570ec7afbd8ecc466`.

El agente de las 08:00 dejó exactamente dos archivos nuevos:

- [Radar 17-nov](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-17_RADAR_CAPCOT.md), commit `c47a7ceab2cf75570943942570ec7afbd8ecc466`.
- [Storyboard «El suelo tiene dos relojes»](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/proyectos/2026-11-17_dato-suelo-dos-relojes/storyboard.json), commit `ab468652710743bfc2012e15474c38a966c2bb03`.

El storyboard tiene 8 escenas, 214 palabras y 84 segundos incluyendo cortinilla. La compuerta estructural del agente pasó, pero `narrative_qa` no está escrito: estado `PENDIENTE_AUDITOR`. Está en `proyectos/`, no en `cola/entrada/`.

No existe `cola/estado/2026-11-17_dato-suelo-dos-relojes.json`; por contrato la recepción queda **RECEPCION_GROK_NO_CONFIRMADA**. No se creó ni modificó el archivo de estado de Grok. No se promovió a cola ni se generaron medios.

Otros puntos del radar:

- DOI del estudio principal: `PENDIENTE_RESOLVEDOR`; no se declara resuelto.
- Slot 23:30, candidato Lobesia botrana: `PENDING_SOURCE`, sin storyboard.
- Slots 07:00 del 18–21-nov: vacíos.
- `ESTADO_SLOTS` conserva LDL 19:00 como programado, pero `data/horarios.json` lo marca retirado; se trata ese dato de `ESTADO_SLOTS` como obsoleto para ese slot.
- Backup ornitorrinco 07:00: YouTube privado programado; TikTok/Facebook pendientes.
- Baffin 13:30: aparece programado.
- `data/publicaciones.json` llega hasta 31-oct y no confirma publicaciones de noviembre.

No se hizo QA narrativo en esta operación; corresponde al auditor de las 15:00, cuya última ejecución es del 16-nov.

## Motor U6 — inventario y comparación de checkpoints

Ramas verificadas:

- `main`: `976b67a55bbd4a755896a18eaa1d28d506755ceb`.
- rama de lectura activa `alterno/cameo-pesos`: `56513ab98c0af74291121bec4d5c954397355a63`.

Se materializaron e inspeccionaron **20 ZIPs**; todos pasaron `zipfile.testzip()`. Los hashes, tamaños, IDs de Biblioteca y rutas están en el manifiesto. No se copiaron ZIPs grandes al repo: se dejó manifiesto + resumen para evitar duplicación de archivos de varios MB/centenas de MB.

Hallazgos cronológicos:

- 14-sep y 24-sep: el Engine V5 incluido tiene hash antiguo; `patterns_final_v14.json` sí coincide con el catálogo canónico de 244 patrones.
- 16-sep: existe el ZIP completo por metadatos, pero la Biblioteca no permitió materializarlo; no se declara su contenido ni hash. PRE-SOURIAU y actualizaciones auxiliares sí fueron inspeccionados.
- 27-sep: el ZIP unificado ya contiene el Engine V5 canónico y el catálogo 244; tiene sensor y plugin de tokens, todavía sin el sidecar de filtro.
- 29-sep: las dos copias de `MOTOR_MODELO_AGNOSTICO_PRE_EJECUTABLE_V15_3.txt` tienen SHA-256 idéntico.
- 11-oct: los patches 14–19 y el checkpoint unificado contienen Engine V5/catálogo canónicos. PATCH19 y el unificado no incluyen `sidecar_sombrero_blanco_filtro_v1.py`; `PATCH19_REPAIR_REPORT.md` registra la ausencia y el error de salida.
- 19-oct: existe el paquete `SOMBRERO_BLANCO_FOTO_TEMPORAL_V1`. Su módulo evalúa fuente, cobertura, cronología, cortes y post-Z; no es la clasificación semántica original. El wrapper Espectro V2 lee el resultado después de correr el motor, por lo que no impone el bloqueo previo.
- 20-oct: R3/U6 unificado/Tortugas/R4 contienen el sidecar regex actual. El paquete compacto R4 de motor contiene el sidecar; el paquete de laterales no. La capa Foto Temporal no aparece en la rama activa.

### Función Sombrero Blanco: original frente a lo conectado

El contrato se reconstruyó desde las especificaciones del checkpoint del 14-sep y el documento actual [`SOMBRERO_BLANCO.md`](https://github.com/marcojpad-hash/orquestador-central/blob/main/docs/filtros_operativos/SOMBRERO_BLANCO.md):

- descomponer texto en unidades observables;
- preservar texto fuente y hechos útiles;
- separar afirmación/fuente, observación, interpretación, juicio, figura retórica, ruido y metadato;
- dejar traza de cada unidad;
- no decidir H ni alterar P/A/C.

La rama activa sí tiene un sidecar conectado a `laterales_unico`, pero no implementa ese contrato. Es un filtro por frases: si encuentra expresiones de protocolo como «juicio estético», excluye el texto completo del canal en vez de aislar la parte valorativa y conservar la parte factual. Restringe lo que reciben los laterales; no es un voto directo del predictor central.

Otras piezas:

- `plugin_sombrero_blanco_token.py`: post-apuesta; persiste tokens descubiertos en StinkBox, sin retroalimentación al predictor de la misma corrida.
- `sensor_perfil_narrador_v0_1.py`: diagnóstico, no filtro semántico.
- `guardianes_control_v1.py`: post-predictor; puede retener el cierre como `LATENTE` y disparar tortugas, pero no cambia H1/H2/top1.
- `protocol_quality=PASS/ENFORCED`: el sello no demuestra que se ejecutó la descomposición semántica.
- `plugin_metodo_rigor.py`: alarma corta; el controlador añade contexto, pero las cuatro preguntas completas siguen en protocolo/manual.
- `plugin_pregunta_detras_v2.py`: marca/explica, no decide H.
- Copi y Beristáin tienen módulos U6 posteriores; no equivalen a un runtime transversal de Orquestador.

La capa `sombrero_blanco_foto_temporal_v1.py` del paquete 19-oct **no está en la rama activa** y tampoco debe presentarse como la función original: su wrapper no hace cumplir `ready_for_engine=false` antes de ejecutar el motor.

### Evidencia de pruebas histórica

Los reportes del 20-oct indican:

- informe unificado: 148 PASS / 2 SKIP; la revisión independiente no reprodujo un único run combinado de 148.
- revisión independiente: motor 102 PASS / 2 SKIP y laterales 46 PASS / 0 SKIP por separado.
- compactación: 77 PASS / 2 SKIP.
- integración StinkBox: 84 PASS / 2 SKIP.
- calibrable: 92 PASS / 2 SKIP; motor + laterales 163 PASS / 2 SKIP.
- variante de hipótesis abiertas: 94 PASS / 2 SKIP.

Son resultados históricos. No se reejecutó el motor ni sus pruebas en esta operación; solo se verificó integridad de los ZIPs.

## Orquestador Central — descubierto adicional, solo lectura

Repositorio: `marcojpad-hash/orquestador-central`, `main` HEAD `736915b1c258c5a878192f72d000570f020d9dd8`.

Se leyeron `SOMBRERO_BLANCO.md`, `INVENTARIO_GUARDIANES_PROTOCOLO.md`, `runtime/README.md` y `ARCHETYPE-SEQUENTIAL-VERIFIABLE-v1.md`.

- No se encontró ZIP de checkpoint de Orquestador en la Biblioteca; los documentos del repo son la fuente disponible.
- `runtime/README.md` promete capacidad de bloqueo de guardianes, mientras que `ARCHETYPE-SEQUENTIAL-VERIFIABLE-v1.md` indica que el motor automático de guardianes aún no está implementado.
- PR #9 sigue siendo una suite/runner: `adapters.json` está vacío y los 15 casos aparecen `BLOCKED_NO_ADAPTER`. No es una integración semántica.
- Issue #8 sigue abierto.

No se escribió ni fusionó nada en Orquestador; queda fuera del alcance de escritura de esta operación y no se interfirió con el trabajo que pueda estar haciendo otro modelo.

## Estado de PRs y migración

- Motor U6: PR #8 (Z90) y PR #11 (supervisor) abiertos, ambos mergeable=true y no fusionados; no se tocó la rama.
- CAPCOT: PR #13 y PR #14 abiertos, ambos mergeable=true y no fusionados; no se modificaron.
- Orquestador: PR #9 abierto y mergeable=true (suite/runner), Issue #8 abierto; sin cambios.
- ChatGPT-migracion: PR #1 abierto y mergeable=false.
- El acuse de segunda sesión/modelo en `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` sigue pendiente; migración **NO COMPLETA**.

## Trabajo material realizado en esta corrida

Se crearon y verificaron en `ChatGPT-migracion/main`:

1. [Manifiesto de checkpoints](../bandeja/checkpoints/2026-11-17_MANIFEST_CHECKPOINTS.json) — IDs de Biblioteca, rutas, tamaños, SHA-256, integridad ZIP, referencias de código y límites.
   - Commit final del manifiesto: `d1a683d740ee9eebc126bea475231aec383bc3cf`.
2. [Resumen comparativo Motor/Sombrero Blanco](../bandeja/checkpoints/2026-11-17_RESUMEN_COMPARATIVO_MOTOR.md).
   - Commit: `8c53e65606164c99b78cc0fe077c12a76b11aca6`.
3. [Respuesta a Puta3](../bandeja/2026-11-17_RESPUESTA_PUTA3_CHECKPOINTS.md).
   - Commit: `7aa64d5b97d12d254a634fe85d0d11e49c98a57e`.

El manifiesto inicial se corrigió después de verificar los SHA actuales de los archivos de código y el HEAD de `memoria-compartida`; la versión final contiene esos valores corregidos.

## Límites, decisiones y pendientes

**Ejecutado:** lectura de documentos, inventario GitHub, verificación de conexiones, consulta de automatizaciones, inspección de checkpoints, materialización de 20 ZIPs, SHA-256 e integridad, comparación de código y creación de los tres artefactos de handoff.

**No ejecutado deliberadamente:** correr Motor U6; modificar Engine V5/catálogo/candados; tocar CAPCOT o hacer QA narrativa; escribir estado de Grok; modificar Orquestador; fusionar PRs; cambiar permisos/credenciales; enviar mensajes externos; consumir créditos.

**Pendiente verificable:**

- Auditor CAPCOT del 17-nov a las 15:00: debe revisar en frío el storyboard actual; hasta entonces sigue fuera de cola.
- Confirmación de recepción Grok: solo cuando exista `cola/estado/2026-11-17_dato-suelo-dos-relojes.json`.
- Resolver fuente/DOI del candidato 23:30 antes de preparar storyboard.
- Reconciliar la tarea de monitor de bus de las 09:00: no aparece entre las automatizaciones activas consultadas.
- Verificar el cambio de dispatch Grok con una ejecución real posterior al fallo por `GROK_WEBHOOK_URL`.
- Recibir acuse verificable de segunda sesión/modelo para completar migración.

No se deshabilitó ninguna automatización ni se creó otra. No se declararon completadas las tareas que siguen pendientes.