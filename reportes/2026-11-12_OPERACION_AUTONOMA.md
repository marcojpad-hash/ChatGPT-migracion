# Operación autónoma — 2026-11-12

**Fecha de corte:** 2026-11-12, America/Mexico_City  
**Repositorio de continuidad:** `marcojpad-hash/ChatGPT-migracion`, `main`  
**Resultado:** revisión de repositorios, automatizaciones, CAPCOT y Motor U6; actualización de continuidad. No se declara terminado ningún run que seguía `in_progress`.

## 1. Arranque y autoridad

Leídos en `ChatGPT-migracion/main`: `CONTINUIDAD_CHATGPT.md`, `ESTILO_DE_TRABAJO.md`, `BOT_DOT_AUTONOMIA.md`, `PROYECTOS_Y_ESTADO.md`, `docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md`, `docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md`, `docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md`, `bandeja/2026-11-03_RECUPERACION_MIGRACION.md`, el reporte operativo del 11-nov y la última auditoría transversal disponible.

La auditoría transversal más reciente sigue siendo [2026-10-31_AUDITORIA_TRANSVERSAL.md](2026-10-31_AUDITORIA_TRANSVERSAL.md). No se encontró una auditoría transversal posterior. Se leyó como antecedente, no como estado actual.

**Autoridad de ramas:**
- ChatGPT-migracion: `main`.
- CAPCOT: `feature/capcot-video-discovery-continuity`.
- Motor U6: `alterno/cameo-pesos` es la rama vigente de trabajo; `main` es `SOLO_CONSULTA` según `CONTRATO_OPERATIVO_RAMA_VIGENTE.md`.

## 2. Cuentas e inventario GitHub

Consultas realizadas a las dos conexiones autorizadas:
- **marcojpad-hash:** una instalación GitHub visible (ID `174841554`, selección `all`; el nombre de la App no se expone) y 11 repositorios visibles: `motor-u6-storage`, `capcot-capsulas-imaginantes`, `ChatGPT-migracion`, `orquestador-central`, `red-teaming-safety-u6`, `agente-cero-costo`, `baterias-tokens`, `baterias-memoria`, `memoria-compartida`, `microserie-heredera-sadtalker`, `microserie-heredera-voces`.
- **marcosabines-hash:** cero instalaciones y cero repositorios visibles; la consulta no devolvió error.

Los ocho repositorios distintos de los tres principales siguen clasificados `DESCUBIERTO_ADICIONAL`; no se escribieron, fusionaron ni desplegaron. No se infiere que una instalación con selección `all` sea Muse ni se deducen permisos de otra aplicación.

## 3. Automatizaciones — estado al último peek

| Automatización | Último run | Estado observado | Próxima ejecución guardada |
|---|---|---|---|
| Investigador CAPCOT | `b2beb9a1-cf4c-832c-9bfe-263016e0708d` | `in_progress`, inició 07:59:30 CDMX, sin `completed_at` | 12-nov 08:00 |
| Auditor CAPCOT | `40b928d7-2318-832e-8004-967167b8fa8d` | `completed`, 11-nov 15:33:58 CDMX | 12-nov 15:00 |
| Operador general | `1b041e4c-40ec-8330-9b1c-2bcd677706a6` | `in_progress`, inició 08:01:12 CDMX, sin `completed_at` | 12-nov 08:00 |

Las tres automatizaciones están habilitadas. A diferencia de cortes anteriores, `next_run_time` devolvió fechas concretas en esta consulta. Eso no prueba ejecución futura. Los dos runs abiertos no se contabilizan como terminados. El último resultado completo del investigador es del 11-nov (`5071a975-ac40-8326-9796-3fa1e185991e`); el último resultado completo del operador es del 11-nov (`978b41d5-4a30-832a-abcf-72323699d005`).

Dot no está conectado a esta sesión. Las automatizaciones de ChatGPT siguen siendo sustitutos parciales, no un agente 24/7.

## 4. CAPCOT — revisión de la rama activa

### Fecha 12-nov
- No existe `proyectos/2026-11-12_*` en el listado de `proyectos/` al momento de la consulta.
- No existe `docs/briefs/2026-11-12_RADAR_CAPCOT.md`.
- No existe `data/horario_2026-11-12.json`.
- El run del investigador de las 08:00 seguía `in_progress`; por tanto, la ausencia de esos entregables es un estado provisional del chequeo, no un resultado terminal del run.
- El prompt guardado del investigador todavía excluye explícitamente el slot 23:30. La instrucción permanente de preparar el dato del día y esa exclusión siguen en conflicto. No se generó un duplicado ni se cambió el prompt en esta operación.

### Paquete ratas topo del 11-nov — apareció después de la auditoría
La auditoría CAPCOT del 11-nov terminó a las 15:33 CDMX y reportó cero borradores/entradas del día. Después se añadieron estos commits:
- [Storyboard](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/cola/entrada/2026-11-11_dato-ratas-topo-damaraland/storyboard.json), commit `0fc81d63a513e08c0e64465f2f3a8d8eec82e418`.
- [Fuente DOI](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/cola/entrada/2026-11-11_dato-ratas-topo-damaraland/fuentes.md), commit `6bf84e81239966e9b938eb9cb91b29c75f7ae395`.
- Ocho archivos `frames/frame_01.png`–`frame_08.png`, commit `a033a6b3325ecc9c2c2e0dfb638bece23fa0bd40`.

Inspección del storyboard releído:
- 8 escenas y 212 palabras de narración.
- No contiene `narrative_contract` ni `narrative_qa`; no hay revisión narrativa independiente registrada.
- Contiene `asset_filename` por escena y `export.filename`, incompatibles con el contrato de preproducción textual.
- Está dentro de una carpeta anidada `cola/entrada/<project_id>/storyboard.json`, no como JSON plano en `cola/entrada/*.json`.
- No existe `salidas/2026-11-11_dato-ratas-topo-damaraland/`.
- La carpeta `cola/estado/` devuelve 404; para este proyecto y los demás paquetes revisados: **RECEPCION_GROK_NO_CONFIRMADA**.

El workflow `.github/workflows/capcot-grok-dispatch.yml` escucha únicamente `cola/entrada/*.json` y su búsqueda manual usa `-maxdepth 1`; esta carpeta anidada no activa ni entra en ese dispatch.

Hay una señal contradictoria que impide mover el paquete sin más: el commit [de rotación de pantallas del 12-nov 07:47](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/commit/591283ce6ccab9d38aed4cc4a8518e1ef77b5a28) identifica el video `knAElNo4raI` como ratas topo y le atribuye 220 vistas. Sin embargo, `data/publicaciones.json` y `data/rotacion.json` no contienen el ID ni el project_id, y no hay carpeta en `salidas/`. No se pudo confirmar la publicación en plataforma. Se conserva como **DISCREPANCIA DE PRODUCCIÓN/PUBLICACIÓN**. Por la existencia de frames y la señal de un ID con vistas, no se movió ni alteró la carpeta; hacerlo podría interferir con trabajo audiovisual ya realizado.

### Otros paquetes heredados
- Robot orbital 9-nov: conserva `narrative_qa PASS/90`, pero está anidado y sin archivo individual de estado Grok.
- Clavo 7-nov: sigue anidado y sin `narrative_qa`; su historial mantiene discrepancias de programación/publicación.
- `cola/estado/` no existe en la rama revisada. No se creó ni modificó ningún estado Grok.
- No se creó `CONTROL_COLA` desde esta operación: corresponde al auditor de las 15:00, que ya había terminado su revisión antes de que apareciera el paquete de ratas topo.

## 5. Motor U6 — revisión documental de la rama vigente

Se leyó `CONTRATO_OPERATIVO_RAMA_VIGENTE.md`, `FEEDME_ACTUALIZADO.md`, el informe Schrödinger anterior, `CONTRATO_GUARDAR_CORRIDAS.md`, la entrega F003/F004 y la prueba de negativo.

### Entrega F003/F004
La rama `alterno/cameo-pesos` contiene [motor/runs/F003_F004_20261111/](https://github.com/marcojpad-hash/motor-u6-storage/tree/alterno/cameo-pesos/motor/runs/F003_F004_20261111), commit de entrega `be98ec8645364b1330104de996fbd6339033547c`. El manifiesto enumera 20 casos; en cada registro declara `ok:true` y `receipt_status:COMPLETED`. La carpeta contiene entradas, resultados interpretables, recibos, manifiesto, tabla completa, revisión y `LECTURA.json`. Los RESULT crudos no están versionados; el manifiesto conserva sus hashes y tamaños por el límite de tamaño documentado.

La propia `REVISION.md` registra:
- 20 recibos con dos rutas ausentes: `$.stages[8].adaptador` y `$.stages[8].verificacion_no_escribe_H`.
- Ningún caso tiene tabla de mortalidad; `predictive_validation` permanece `NOT_CALIBRATED_NO_CASE_LEVEL_OUTCOMES`.
- 1 caso FRAGIL y 16 AJUSTADA; tres casos con `EVIDENCIA_SEPARADA` no son AJUSTADA.
- `tortugas_ejecutado=false` en Faraday, Law y Mendel, además de la excepción de Caravaggio en la revisión.
- Los resultados son soporte estructural, no probabilidades calibradas.

### Incidencia del candado de entrega
`LECTURA.json` registra hashes de cuatro documentos leídos. Recalculé SHA-256 contra los archivos actuales de la rama; los cuatro difieren:

| Documento | SHA registrado | SHA actual |
|---|---|---|
| `casos/REGLAS.md` | `9c2dec25…` | `cb54dc0c…` |
| `CONTRATO_CARPETAS.md` | `8e5c4b16…` | `fef4ef74…` |
| `casos/fabrica/README.md` | `9cc7ab20…` | `614a5c92…` |
| `PROTOCOLO_EJECUCION_Y_LECTURA_LLM.md` | `d05320f0…` | `3b8e15e1…` |

`CONTRATO_GUARDAR_CORRIDAS.md` §5 exige que los hashes de `LECTURA.json` coincidan con los documentos actuales. Por lectura estática, esta evidencia no satisface la condición de hash vigente. **No ejecuté `scripts/candado_entrega.py`**, así que no declaro un resultado terminal del candado.

Además, §6 de `CONTRATO_GUARDAR_CORRIDAS.md` todavía dice que los tres documentos de almacenamiento están pendientes de actualizar, pero el commit `8f2f6ea423c14720cfe882573dc94da5c02484a5` ya actualizó `casos/REGLAS.md`, `CONTRATO_CARPETAS.md` y `casos/fabrica/README.md`. La sección §6 está desactualizada.

### Prueba del negativo
[PRUEBA_NEGATIVO_5_HIPOTESIS_NAPOLEON.md](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/PRUEBA_NEGATIVO_5_HIPOTESIS_NAPOLEON.md), commit `74334f23f795528201b219baee2ceba86c6a7f0a`: resultado 5→5, cero hipótesis descartadas. Las 50 aristas observadas tienen Ric_F positivo; Billar z=0.825 y Ricci z=1.3885, ambos debajo de `Z_MIN=2.0`. El proxy documentado no es Forman-Ricci exacto y no produjo señal negativa en esa prueba.

No se ejecutó el motor ni los tests. No se modificaron Engine V5, catálogo 244, motores canónicos, candados ni código U6.

## 6. Migración y conectores

`bandeja/2026-11-03_RECUPERACION_MIGRACION.md` sigue `PENDIENTE`; no contiene acuse de destinatario. El acuse separado de Claude continúa siendo parcial y no acredita recuperación completa de CAPCOT ni los conectores de la segunda sesión. Migración **INCOMPLETA**.

Codebase-memory-mcp/DeepSeek Harness: el mapa conserva la última verificación; esta sesión no expone un servidor MCP vivo de codebase-memory ni una conexión ejecutable de DeepSeek Harness. No se infirió acceso a Dot ni a n8n.

## 7. Acciones, verificaciones y límites

**Ejecutado:** lectura de contratos y fuentes; inventario de cuentas; consulta de automatizaciones; inspección de rutas, workflow, storyboard, frames, estado Grok, manifiesto, recibos documentados, LECTURA, revisión y prueba de negativo; recálculo SHA-256 de los cuatro documentos citados en LECTURA; actualización de continuidad en este repositorio.

**Verificado en fuente:** rutas/SHAs de los archivos citados y commits indicados; ausencia de `cola/estado/`, horario y radar 12-nov; presencia de ocho PNG; contenido del storyboard y del manifiesto.

**No ejecutado:** QA narrativo independiente nuevo, validador CAPCOT, dispatch, candado U6, motor, tests U6, publicación, programación, generación de medios o consumo de créditos.

**Decisiones preservadas:** no mover el paquete de ratas topo por la señal de producción/publicación sin reconciliar; no crear estado Grok; no cambiar prompts/horarios ni resolver el slot 23:30 por inferencia; no modificar ramas, permisos, credenciales o canónicos.
