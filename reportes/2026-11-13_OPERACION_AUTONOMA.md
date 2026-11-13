# Operación autónoma — 2026-11-13

**Corte:** 08:05 America/Mexico_City.  
**Alcance:** ChatGPT-migracion/main, CAPCOT/feature/capcot-video-discovery-continuity y Motor U6/alterno/cameo-pesos (rama activa por contrato). No se escribió en repositorios adicionales.

## 1. Auditoría, cuentas y repositorios

- Se leyeron `CONTINUIDAD_CHATGPT.md`, `ESTILO_DE_TRABAJO.md`, `BOT_DOT_AUTONOMIA.md`, `PROYECTOS_Y_ESTADO.md`, el mapa, el protocolo de memoria compartida, el checklist y el reporte operativo del 12-nov.
- El registro de auditoría transversal más reciente sigue siendo `reportes/2026-10-31_AUDITORIA_TRANSVERSAL.md`; el inventario de `reportes/` no contiene una auditoría transversal posterior. El reporte operativo anterior es el del 12-nov.
- GitHub `marcojpad-hash`: 11 repositorios visibles: `motor-u6-storage`, `capcot-capsulas-imaginantes`, `ChatGPT-migracion`, `orquestador-central`, `red-teaming-safety-u6`, `agente-cero-costo`, `baterias-tokens`, `baterias-memoria`, `memoria-compartida`, `microserie-heredera-sadtalker`, `microserie-heredera-voces`.
- GitHub `marcosabines-hash`: 0 instalaciones y 0 repositorios visibles, sin error.
- Los ocho repositorios adicionales se inspeccionaron únicamente en metadatos y README; ninguno recibió escrituras. Visibilidad observada: `orquestador-central` público, `red-teaming-safety-u6` privado y los otros seis públicos. `agente-cero-costo` documenta DeepSeek Harness; eso no constituye integración ejecutable en CAPCOT/feature o U6/alterno.

## 2. Automatizaciones

| Automatización | Último run / estado al corte | Próximo horario |
|---|---|---|
| Investigador CAPCOT | `da1861f5-beac-8332-8e94-88a13351ed3b`, IN_PROGRESS, iniciado 08:02:39 CDMX, sin `completed_at`. Último COMPLETED: 12-nov, `b2beb9a1-cf4c-832c-9bfe-263016e0708d`. | 14-nov 08:00 |
| Auditor CAPCOT | `91d11256-c27c-8320-9274-7b24fe5662a9`, COMPLETED 12-nov 15:59:15 CDMX. | 13-nov 15:00 |
| Operador general | `f4d5c766-dd78-8322-9b39-ed2281dc0980`, IN_PROGRESS desde 07:59:58 CDMX, sin `completed_at`. Último COMPLETED: 12-nov, `1b041e4c-40ec-8330-9b1c-2bcd677706a6`. | 14-nov 08:00 |

Los dos runs abiertos no se contabilizan como terminados. Dot no está conectado ni expuesto en esta sesión.

## 3. CAPCOT — lectura y handoff

Repositorio: `marcojpad-hash/capcot-capsulas-imaginantes`, rama `feature/capcot-video-discovery-continuity`.

### Proyecto más reciente

`proyectos/2026-11-12_dato-pedorreta-chimpances/storyboard.json` (blob `9cdf19e915274ca617d08c23a8c1b41639f4fdc9`):

- 8 escenas, 198 palabras, 84 s con cortinilla.
- `narrative_qa`: PASS/91, `review_basis=lectura_en_frio_solo_narracion`, siete checks true, `critical_flags=[]`.
- El DOI `10.1073/pnas.2606837123` sigue `PENDIENTE_RESOLVEDOR`; no se promovió.
- `cola/estado/2026-11-12_dato-pedorreta-chimpances.json` devuelve 404: **RECEPCION_GROK_NO_CONFIRMADA**.

### Paquete heredado de ratas topo

`cola/entrada/2026-11-11_dato-ratas-topo-damaraland/storyboard.json` (blob `2bf4e67b18ada612c7a090b452df27869a40dafc`):

- 8 escenas, 8 `asset_filename`.
- No contiene `narrative_contract` ni `narrative_qa`.
- `cola/estado/2026-11-11_dato-ratas-topo-damaraland.json` devuelve 404: **RECEPCION_GROK_NO_CONFIRMADA**.
- Permanece en su ruta actual; no se movió, promovió ni redispatchó.

### Workflow

Se releyó `.github/workflows/capcot-grok-dispatch.yml`. El trigger de push escucha `cola/entrada/*.json`; el selector usa `find cola/entrada -maxdepth 1 -type f -name '*.json'`. Por tanto, la carpeta anidada del paquete de ratas topo no es despachable mediante este workflow. El marcador `handoffs/grok_inbox` no sustituye el archivo individual `cola/estado/<project_id>.json` ni prueba recepción. No se disparó el workflow ni se escribió ningún estado Grok.

### Corrección del slot 23:30

El contrato operativo CAPCOT §3 autoriza cinco slots diarios, incluido `dato_del_dia` a las 23:30; el horario del 11-nov registra ese slot como `sin_paquete_en_esta_ventana`. El prompt del investigador excluía globalmente 23:30. Se actualizó la automatización `Agente de investigación CAPCOT` (ID `6ae5827ecc808191a36a8c773cc2990a`) para:
- evaluar ocupación por slot, no por fecha global;
- crear un storyboard independiente 23:30 solo si el slot está libre;
- exigir fuente publicada en la misma fecha CDMX y dentro de las 48 horas previas;
- no adelantar noticias y dejar `PENDING_SOURCE` si no hay fuente apta;
- dejar el borrador en `proyectos/` para QA en frío del auditor, sin escribir QA, cola o estado Grok.

**Límite temporal:** el run del 13-nov empezó a las 08:02:39; el prompt se actualizó a las 08:03:28. No se afirma que el run en curso haya cargado el prompt nuevo. La primera aplicación verificable queda pendiente para el run del 14-nov 08:00. No se creó storyboard del 13-nov para evitar duplicar al investigador en curso.

## 4. Motor U6 — documentación, sin ejecución

Contrato vigente: `alterno/cameo-pesos`; `main` es `SOLO_CONSULTA`.

### F003/F004

Se revisaron `motor/runs/F003_F004_20261111/` y los 20 recibos individualmente:

- 20/20 tienen `status=COMPLETED`.
- En los 20, `stages[8]` es `consulta_dirigida`; las claves `adaptador` y `verificacion_no_escribe_H` existen, ambas con `DATO_AUSENTE_REQUIERE_CLASIFICACION`.
- La frase previa `receipt_missing_paths` era imprecisa como ausencia estructural. El problema verificado es el valor sentinel no clasificado; no demuestra que el adaptador esté configurado ni que la verificación de no escritura se haya ejecutado.
- `LECTURA.json`: 3/4 SHA-256 no coinciden. No coinciden `casos/REGLAS.md`, `CONTRATO_CARPETAS.md` y `casos/fabrica/README.md`; `PROTOCOLO_EJECUCION_Y_LECTURA_LLM.md` sí coincide. No se alteró `LECTURA.json` para no simular una lectura contemporánea de la entrega original.

### Documentación corregida en la rama activa

- `CONTRATO_GUARDAR_CORRIDAS.md`: ejemplo de lectura y §6 reconciliados.
  - Commit `c0a6980c5505846dc7d14e325d935e05b9c3cb83`.
- `motor/runs/F003_F004_20261111/README.md`: deja de describir el lote como excepción.
  - Commit `e4e37c412c9b2c6a52f6f3488d15c14b731462c7`.
- `motor/runs/F003_F004_20261111/REVISION.md`: corrección de los campos sentinel y de la evidencia LECTURA.
  - Commit `85971f5d904819f08cd9219cfd239ad7aada1129`.
- Entrada de avance: [2026-11-13_ChatGPT_normalizacion_contrato_corridas.md](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/avances/2026-11-13_ChatGPT_normalizacion_contrato_corridas.md), commit `9b72987aed3b56e3364525118b20927bee2bfc8a`.

No se ejecutaron `scripts/candado_entrega.py`, tests ni el motor. No se modificaron Engine V5, catálogo 244, código canónico ni candados. El estado sigue `NO_CALIBRADO`.

### Memoria de código y DSH

- U6/alterno conserva `.mcp.json` apuntando a `/home/hatch/workspace/codebase-memory-mcp/bin/codebase-memory-mcp`; la documentación describe un índice de `main` del 7-nov. No prueba que el binario exista en esta sesión, que el proceso esté vivo o que la rama activa esté reindexada.
- CAPCOT/feature devuelve 404 para `.mcp.json` y `docs/CODEBASE_MEMORY_MCP.md`.
- No existe configuración `docs/DSH_CERO_COSTO.md` en U6/alterno ni CAPCOT/feature. DeepSeek Harness está documentado en el repositorio adicional `agente-cero-costo`, fuera del alcance de escritura.
- No se expone herramienta MCP de codebase-memory ni DeepSeek Harness en esta sesión.

## 5. Continuidad actualizada

Se actualizaron y releyeron:

| Archivo | Commit |
|---|---|
| `CONTINUIDAD_CHATGPT.md` | `2bfb7f18fb53991ff1c749dd55fa79b1d1a35855` |
| `BOT_DOT_AUTONOMIA.md` | `4c75bcbba74d5904e8ac0f3bd519d942b5d9fe6f` |
| `PROYECTOS_Y_ESTADO.md` | `f70470be33d5ef50ab283d5af8e7403fe956bcc6` |
| `docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md` | `252a15994b400f67b14adaac8db2b797ee76c0f7` |
| `docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md` | `a866d0e7db1d68244e9888ebf17fdb5b2901f671` |
| `docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md` | `0dbfd29d42deaf72e6653de03032266b1d4c10fa` |

Se corrigió la fila de autoridad de U6 en el protocolo: `alterno/cameo-pesos` es la rama activa; `main` es `SOLO_CONSULTA`.

El handoff original `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` sigue sin acuse verificable de una segunda sesión que cubra CAPCOT y los conectores. El acuse separado de Claude sigue parcial. Migración **INCOMPLETA**.

## 6. Acciones no ejecutadas

No se escribió en CAPCOT ni en repositorios adicionales; no se creó ni modificó `cola/estado/`; no se promovió ni redispatchó ningún paquete; no se dispararon workflows; no se publicó ni programó contenido; no se generaron medios ni se consumieron créditos; no se cambiaron permisos, credenciales o ramas; no se ejecutó motor, candado ni tests U6.
