# Recuperación independiente de ChatGPT — 2026-11-11

## Resultado

**Estado de esta recuperación: INSPECCIONADO; reporte listo para relevo. Migración global: INCOMPLETA.**

Esta sesión reconstruyó el contexto desde GitHub, leyó los documentos de arranque en el orden solicitado, consultó memoria compartida y abrió las ramas especializadas autorizadas. No ejecutó código de U6 ni Actions, no creó ni programó publicaciones CAPCOT y no modificó ninguno de los repositorios especializados.

## 1. Documentos leídos en el orden pedido

Todos se leyeron desde `marcojpad-hash/ChatGPT-migracion/main`:

| Orden | Ruta | Blob SHA |
|---:|---|---|
| 1 | [README.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/README.md) | `1172661c549e41b4b2ecb9eb40e5ef3ca92b02be` |
| 2 | [CONTINUIDAD_CHATGPT.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/CONTINUIDAD_CHATGPT.md) | `2a69d2e66d1b533b21ec095bb6a68b5759591ef7` |
| 3 | [ESTILO_DE_TRABAJO.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/ESTILO_DE_TRABAJO.md) | `47917e6978927779bcef9c8f32c72b3e0c6a826d` |
| 4 | [PROYECTOS_Y_ESTADO.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/PROYECTOS_Y_ESTADO.md) | `c293ee85537b5e2da2ef4e4b24338e4407ee3a4d` |
| 5 | [docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md) | `1e16e8860b3404c3494d6c990f368775c1950c26` |
| 6 | [docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md) | `e4ffd93c94b0430397ca8f8266d1ea67ecc2a0e0` |
| 7 | [docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md) | `4eac0065ca3b86b8c618da15ed7c67ed1846a635` |
| 8 | [bandeja/2026-11-03_RECUPERACION_MIGRACION.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/bandeja/2026-11-03_RECUPERACION_MIGRACION.md) | `f9af4d1d72584099e695451cea0b777dafe98ebb` |

También se leyó `bandeja/PLANTILLA.md` (blob `9d39e80daef91bcd84a93de136eb78340b296a27`), el gate `AGENTS.md`, el protocolo y el índice de `memoria-compartida`, los hechos pertinentes y el contrato transversal de `orquestador-central`.

## 2. Repositorios, ramas y autoridad

- **Continuidad:** `ChatGPT-migracion/main`. HEAD visible al iniciar: [`e1437f5d73398a2fc27af9113602c9be23c7937e`](https://github.com/marcojpad-hash/ChatGPT-migracion/commit/e1437f5d73398a2fc27af9113602c9be23c7937e).
- **Motor U6:** `motor-u6-storage/alterno/cameo-pesos`. La rama existe y su contrato `CONTRATO_OPERATIVO_RAMA_VIGENTE.md` (blob `161bf2a2a67e094d541074ec5a7c5df2e6b1cd11`) declara `main` SOLO_CONSULTA. No se trabajó en `main`.
- **CAPCOT:** `capcot-capsulas-imaginantes/feature/capcot-video-discovery-continuity`. La rama existe y los contratos locales le asignan el trabajo textual a ChatGPT; producción, QA audiovisual y publicación corresponden a Imaginantes/Grok.

El contrato U6 mantiene protegidos Engine V5 (`665c39a2…`) y catálogo de 244 patrones (`d827dcc3…`). No se escribieron ni recalcularon sus archivos.

## 3. Pendiente actual de Motor U6

El [informe CAMEO de la rama](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/informes/2026-11-11_cameo-alterno.md), blob `536c0e59eff262a990b14888aac3daa95e7d6266`, y el plugin [`plugin_cameo_institucional.py`](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/motor/motor/plugin_cameo_institucional.py), blob `4c93a8a0b185c27dbe81c5e71cfe39c268e108c2`, muestran que los pesos por los 76 códigos se calculan y aparecen en la salida, pero todavía no alimentan `cameo_activity`; en el caso Napoleón documentado, el ranking H1 no cambió y hubo cero hits explícitos. El propio informe deja la integración como decisión pendiente de Mj. No la implementé.

Además, el nuevo contrato de rama exige que los pesos, componentes y puntajes publicados vivan en 0.01–0.999 y que sumas crudas fuera de escala se marquen `FALLO_ESCALA`. La evidencia de Napoleón contiene `rank_fusion=28.74557` y `selected_peso_efectivo_sum=42.56`; deben tratarse según esa regla, no como valores normalizados ni probabilidades. Esta observación requiere reconciliación/normalización dentro del diseño autorizado; no modifiqué el runner ni la lógica predictiva.

## 4. Pendiente actual de CAPCOT

El [radar del 11-nov](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-11_RADAR_CAPCOT.md), blob `a11c32eae4ac76da6a568b58b7b6f2f676b8b27f`, concluye `NO_DUPLICAR`: no identifica un slot libre y autorizado para crear storyboard. El horario [`data/horario_2026-11-11.json`](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/data/horario_2026-11-11.json), blob `e5264bdb8e3608697875d07a18e4bb9b03d6b430`, registra 13:30 ocupado por el extra Mpemba, 17:00 por la resub de corneja y 23:30 sin paquete/excluido; el radar describe además la ventana 19:00 como retirada y solo utilizable con OK explícito.

Hay una discrepancia operativa por resolver: el último commit visible de CAPCOT, [`ed957dd2842e1a1dca0942a887870f4d7a165960`](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/commit/ed957dd2842e1a1dca0942a887870f4d7a165960), anuncia arroz programado en YouTube a las 19:00 CDMX, en tensión con el radar y la política horaria antes citada. No he cambiado agenda, registro de publicaciones ni publicación en plataforma. Se requiere reconciliar la autorización/estado antes de considerar ese slot disponible o duplicarlo.

El radar recomienda ratas topo de Damaraland para el próximo slot que esté realmente libre y autorizado; no es una orden de staging. No creé storyboard ni promoví entradas. El radar también contabiliza 59 storyboards únicos sin `narrative_qa` de 83 revisados; quedan en manos del auditor independiente, no se los marqué como aprobados.

## 5. Herramientas y conectores: estado real en esta sesión

| Capacidad | Estado | Evidencia / límite |
|---|---|---|
| GitHub — lectura | CONFIRMADO | `fetch_file` leyó archivos en los tres repositorios y ramas exactos. |
| GitHub — escritura de contenidos | CONFIRMADO a nivel de permiso | Metadatos de los tres repos devuelven `push=true`; esta recuperación usará `create_file` solo en el repo de migración. |
| GitHub — Actions/workflow_dispatch | NO_DISPONIBLE en esta interfaz | No hay acción para despachar workflows; sí hay consultas de estados/artefactos/logs. No se ejecutaron Actions. |
| Shell/runtime de U6 o CAPCOT | NO_DISPONIBLE | No hay checkout local del repo ni terminal conectada a esos entornos en esta sesión; no corrí scripts, suites ni renderizadores. |
| codebase-memory-mcp | NO_DISPONIBLE | No hay herramienta MCP ejecutable expuesta en esta sesión. |
| DeepSeek Harness / dsh | NO_DISPONIBLE | No hay conector/acción ejecutable en el entorno actual. |
| Dot persistente 24/7 | NO_DISPONIBLE | No está expuesto en esta sesión; no atribuyo trabajo a Dot ni a las automatizaciones del usuario. |
| Producción audiovisual / publicación | NO_DISPONIBLE | CAPCOT reserva esas acciones a Imaginantes/Grok; no se usaron. |
| Secretos, permisos y configuración de Actions | NO_MODIFICADOS | No se consultaron valores de secretos ni se alteraron permisos. |

La distinción es importante: que un recurso esté documentado/configurado en un repositorio no demuestra que el proceso esté vivo o que esta sesión pueda ejecutarlo.

## 6. Cambios realizados y no realizados

- No hubo cambios en `motor-u6-storage` ni en `capcot-capsulas-imaginantes`.
- No se tocó `main` de CAPCOT, ningún workflow, `data/*.json`, estado Grok, motores canónicos, catálogo, patrones, candados, secretos, permisos ni publicaciones.
- No se generaron medios, no hubo QA audiovisual, no se despacharon handoffs a Grok y no se consumieron créditos.
- Los únicos cambios de esta recuperación son el acuse y este reporte en `ChatGPT-migracion/main`.

## 7. Criterios de recuperación y estado de migración

**Comprobado por esta sesión:** lectura ordenada; lectura del gate de memoria; acceso GitHub de lectura a los tres repositorios; autoridad de ramas; un pendiente U6 y uno CAPCOT; límites de herramientas; reporte persistible.

**Aún no probado:** que otra sesión/cuenta distinta pueda recuperar estos mismos repositorios y permisos; conexión MCP viva/reindexada; ejecución de una prueba funcional U6 desde un runtime real; acuse independiente de un segundo destinatario; reconciliación del desacuerdo horario CAPCOT.

Por tanto, la migración continúa **INCOMPLETA**. Este reporte no modifica ni reemplaza el handoff original del 3-nov; el destinatario de aquella solicitud sigue siendo la siguiente sesión/modelo que pueda dejar su propio acuse independiente.
