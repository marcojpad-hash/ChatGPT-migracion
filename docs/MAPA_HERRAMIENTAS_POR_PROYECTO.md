# Mapa operativo de herramientas — Motor U6 y CAPCOT
Fecha de comprobación: 2026-11-08

Este mapa no es un catálogo general. Define qué herramientas sirven a los dos proyectos principales, qué se comprobó y qué límites deben respetarse.

## Arquitectura
- GitHub es la memoria operativa persistente y el espacio común de trabajo.
- Cada proyecto conserva código, datos, evidencias y entregables en su repositorio especializado.
- ChatGPT-migracion conserva continuidad transversal, reglas, mapa de herramientas y handoffs; no duplica código canónico ni medios.
- Un conector instalado no demuestra que la cuenta correcta, un recurso configurado o una ejecución estén disponibles.
- Estados obligatorios: INSPECCIONADO, ESTRUCTURALMENTE_VALIDADO, EJECUTADO, VERIFICADO_EN_DESTINO, PENDIENTE o BLOQUEADO.

## Motor U6
Repositorio: https://github.com/marcojpad-hash/motor-u6-storage — rama main, privado.

| Herramienta | Uso | Estado comprobado / límite |
|---|---|---|
| GitHub | Leer contratos, código, casos, hashes, commits, Actions y logs; registrar pruebas y resultados autorizados. | Acceso lectura/escritura confirmado. |
| Floot | Entorno potencial para pruebas aisladas, validación y prototipos. | Conector responde; cuenta sin proyectos. No existe runner U6 configurado allí. |
| Exa | Investigación técnica actual, documentación y diagnóstico. | Conector disponible; no se hizo búsqueda técnica en esta comprobación. |
| Consensus / SciSpace / Undermind | Literatura científica y metodológica. | Conectores disponibles. Undermind devolvió cero workspaces. |
| Notion | Consultar decisiones históricas. | Workspace accesible; GitHub prevalece si hay contradicción con el contrato U6 vigente. |
| Dropbox / Files | Recuperar informes y artefactos. | Dropbox autenticado; no se verificó aquí una carpeta U6. |
| Automations | Auditoría y continuidad. | Operador autónomo general habilitado; next_run_time devolvió null en la consulta del 3-nov. No equivale a agente 24/7. |
| n8n | Diseñar JSON importable para flujos auxiliares, si se solicita. | No hay skill n8n-workflow-check en el catálogo actual ni conector directo a una instancia n8n. JSON importable no equivale a importación o ejecución. |

### Restricciones U6
1. No modificar Engine_V5_CANONICO_SOLO.py, patterns_final_v14.json, candados ni archivos canónicos sin autorización expresa.
2. Seguir sincronización y contratos del repositorio antes de correr. Leer el JSON de salida junto con _RECIBO_EJECUCION.json.
3. Distinguir inspección de código, prueba sintética, prueba parcial y corrida empírica.
4. No inflar n con reevaluaciones del mismo input. No usar información posterior a Z para hipótesis anteriores.
5. Versionar propuestas en laterales/ramas y registrar hashes, pruebas y diffs.

## CAPCOT — Datos y ociosidades
Repositorio: https://github.com/marcojpad-hash/capcot-capsulas-imaginantes — rama feature/capcot-video-discovery-continuity.

| Herramienta | Uso | Estado comprobado / límite |
|---|---|---|
| GitHub | Radar, fuentes, storyboards, validadores, cola, reportes y Actions. | Acceso confirmado en rama de trabajo. No cambiar main ni data/*.json fuera de contrato. |
| vidIQ | Keywords, tendencias, outliers, competencia y rendimiento Shorts. | Conector disponible, autenticado como marcosabines@gmail.com; devolvió cero canales. No se confirmó Datos y ociosidades. |
| Exa | Buscar fuentes recientes, comunicados y páginas originales. | Disponible; validar cada fuente primaria. |
| Consensus / SciSpace / Undermind | Localizar papers y estudios originales. | Disponibles; Undermind sin workspace guardado. No sustituyen validación DOI/Crossref. |
| Canva | Diseños, plantillas, gráficos, miniaturas y recursos. | Conector disponible; cero Brand Kits en la cuenta consultada. |
| Runway | Generación/edición audiovisual y workflows propios. | Conector disponible; cero workflows guardados. Generar puede consumir créditos. |
| Floot | App o scripts auxiliares de preproducción. | Cuenta sin proyectos; no hay app CAPCOT configurada. |
| Dropbox / Files | Almacenamiento y recuperación de activos. | Dropbox autenticado; no se inspeccionó biblioteca CAPCOT en esta comprobación. Mantener medios pesados fuera de GitHub según contrato. |
| Automations | Investigación, auditoría independiente y continuidad. | Investigador y auditor habilitados. Auditoría del 2-nov encontró cero paquetes dispatchables y riesgo de duplicados; no redispatchar producción existente. |
| n8n skill | Diseñar flujos importables para RSS, validación y alertas. | No hay conector directo n8n detectado; la skill no importa ni ejecuta en la instancia del usuario. |

### Restricciones CAPCOT
1. Rama vigente: feature/capcot-video-discovery-continuity. No asumir main sincronizada.
2. Investigador redacta en proyectos/<project_id>/storyboard.json; no se autoevalúa ni promueve.
3. Auditor independiente realiza lectura en frío y registra narrative_qa. Solo PASS con todos los checks y validación estructural permite promoción.
4. QA audiovisual no sustituye QA narrativo.
5. Antes de promover, inspeccionar salidas/, cola/, bloqueados/ y registros de publicación. No redispatchar si ya existe producción/publicación.
6. Solo Grok escribe cola/estado/<project_id>.json. Sin acuse, recepción no confirmada.
7. No publicar, gastar créditos ni alterar secretos/permisos sin autorización.

## Estado real de conectores — 2026-11-03
- GitHub marcojpad-hash: acceso confirmado a los repositorios relevantes.
- GitHub marcosabines-hash: sin instalaciones/repositorios devueltos.
- Dropbox: autenticado como marco.jp@live.com.mx.
- Notion: workspace disponible; usuario owner de un teamspace.
- Floot: cero proyectos.
- Runway: cero workflows guardados.
- Canva: cero Brand Kits.
- vidIQ: autenticado como marcosabines@gmail.com; cero canales.
- Undermind: cero workspaces.
- n8n: sin skill n8n-workflow-check en el catálogo actual y sin conector directo localizado; no hay ejecución remota disponible.
- Automations: las tres automatizaciones principales habilitadas; next_run_time null en la lectura. El prompt guardado no garantiza ejecución futura.

## Prioridades
1. Reconectar vidIQ con la cuenta del canal Datos y ociosidades y verificar canal por ID.
2. Confirmar cuenta/Brand Kit de Canva y workspace/créditos de Runway.
3. Conectar una instancia n8n si se requiere importación y ejecución remota. Mientras tanto, generar JSON importable y procedimiento de prueba.
4. Crear un proyecto Floot solo cuando exista un caso de uso definido y un entorno aislado.
5. Actualizar este mapa cuando cambie una conexión o capacidad real.

## Corrección verificada — 2026-11-05

La consulta actual del catálogo de skills devolvió cero skills y la lista de herramientas no contiene un conector n8n ejecutable. La mención anterior a `n8n-workflow-check` como skill disponible era incorrecta/desactualizada. No confundir generar JSON importable con importar o ejecutar un workflow en una instancia del usuario.

## Descubrimiento de cuentas y repositorios — 2026-11-06

Consulta de las dos conexiones GitHub autorizadas:
- **marcojpad-hash:** una instalación GitHub App (ID 174841554, selección all) y cinco repositorios visibles: ChatGPT-migracion, capcot-capsulas-imaginantes, motor-u6-storage, orquestador-central y red-teaming-safety-u6.
- **marcosabines-hash:** cero instalaciones y cero repositorios visibles. La consulta no devolvió error; el resultado solo describe lo que expone esta conexión.

Los tres repositorios principales no cambian. Los otros dos son **DESCUBIERTO_ADICIONAL** y permanecen fuera del alcance de escritura:

| Repositorio adicional | Relación observada en documentación | Límite aplicado |
|---|---|---|
| [orquestador-central](https://github.com/marcojpad-hash/orquestador-central) | Prototipo documental de gateway, router, memoria y coordinación. PR #1 abierto, draft y sin merge; no hay despliegue verificado. | Solo metadatos y documentación; sin código, PR, merge ni despliegue. |
| [red-teaming-safety-u6](https://github.com/marcojpad-hash/red-teaming-safety-u6) | Repositorio hermano de U6 para subcorridas adversariales white-hat aisladas y control de deriva semántica mediante ledger append-only. La SPEC figura ACTIVA desde 2026-11-03. | Solo README y SPEC; no se inspeccionó el ledger operativo ni se escribió en el repositorio. |

**Notion — comprobación 2026-11-06:** las búsquedas Motor U6 y U6 devolvieron páginas V15 fechadas entre el 19 y el 22 de septiembre de 2026. No apareció una actualización posterior que contradiga el repositorio U6. Se mantienen como antecedentes históricos; motor-u6-storage/main conserva la autoridad técnica.

La incorporación de un repositorio a este inventario no autoriza su modificación.

## Estado de GitHub App/Muse — comprobación 2026-11-07

- El conector GitHub de ChatGPT conserva lectura/escritura en los repositorios de la cuenta `marcojpad-hash`; ese permiso no se transfiere a Muse.
- El trabajo atribuido en el repositorio a Pecas (Muse) sí llegó a `motor-u6-storage`: rama `a5-cableado-20261107`, [PR #2](https://github.com/marcojpad-hash/motor-u6-storage/pull/2) fusionado el 7-nov 03:19 CDMX, merge commit `d2a730c98f5abfdd54c52722b1ef80c28e79f08b`. Esto demuestra que Contents:write funcionó en Motor U6.
- El cuerpo del PR declara pendiente `Workflows` para modificar `.github/workflows/test-motor-contracts.yml`. El archivo sigue con SHA `165bfdee43ec5e6275e2f159d52b86860cfa56ca`; los tres tests nuevos de A5 no están en el workflow actual.
- En CAPCOT no existe la rama `a5-cableado-20261107` ni un PR con ese head. Contents:write de Muse en CAPCOT queda **no verificado**.
- La instalación visible `174841554` tiene selección `all`, pero el conector no expone el nombre de la App; no se afirma que sea Muse ni se deducen sus permisos de esa selección.
- No se cambiaron permisos ni credenciales en esta comprobación.


## Corrección verificada — 2026-11-08

### Cuentas e inventario GitHub

Consulta de ambas conexiones autorizadas e instalaciones:
- `marcojpad-hash`: una instalación visible (ID `174841554`; el conector no expone el nombre de la App) y nueve repositorios visibles: `ChatGPT-migracion`, `capcot-capsulas-imaginantes`, `motor-u6-storage`, `orquestador-central`, `red-teaming-safety-u6`, `agente-cero-costo`, `baterias-tokens`, `baterias-memoria` y `memoria-compartida`.
- `marcosabines-hash`: cero instalaciones y cero repositorios visibles; la consulta no devolvió error.
- Los seis repositorios distintos de los tres principales son `DESCUBIERTO_ADICIONAL`. Se revisaron únicamente metadatos y documentación para entender su relación; no se inspeccionó ni modificó código, no se abrieron PR y no se desplegó nada.

| Repositorio adicional | Relación documental observada | Límite aplicado |
|---|---|---|
| `orquestador-central` | Contrato transversal multi-modelo, arquitectura de coordinación y registro de capacidades. | Solo README/contratos/capacidades; sin escrituras ni despliegues. |
| `red-teaming-safety-u6` | Repo hermano de U6 para subcorridas adversariales white-hat y ledger de deriva. | Solo README; sin ledger ni escrituras. |
| `agente-cero-costo` | Stack auxiliar con Groq bridge, DeepSeek Harness, memoria, conector y orquestador. | Solo README/documentación; sin código ni configuración local. |
| `baterias-tokens` | Registro de proveedores, límites y rotación. | Solo README; sin credenciales ni escrituras. |
| `baterias-memoria` | Registro de máquinas y requisitos de RAM/modelos. | Solo README; sin infraestructura ni escrituras. |
| `memoria-compartida` | Gate universal, índice y hechos durables compartidos. | Lectura del protocolo/índice/hechos; sin escrituras por el límite de alcance a repos adicionales. |

### Memoria compartida obligatoria

- Se leyó `memoria-compartida/PROTOCOLO_MEMORIA_COMPARTIDA_OBLIGATORIA.md`, `INDICE.md` y los hechos pertinentes (`proyectos.md`, `decisiones.md`, `estado.md`, `correcciones.md`, `tokens.md`).
- Se verificó el gate en `AGENTS.md` y `README.md` de los nueve repositorios visibles. En los tres repositorios principales también se verificaron los archivos de la rama autorizada: migración `main`, U6 `main` y CAPCOT `feature/capcot-video-discovery-continuity`.
- El gate ordena leer memoria antes de cualquier tarea y sincronizar hechos durables al cerrar. No auto-inyecta los archivos en una conversación ordinaria ni demuestra que otra sesión los haya leído.
- No se escribió en `memoria-compartida`: es un repositorio adicional fuera del alcance de escritura de este mandato. La sincronización del nuevo corte queda pendiente de inclusión expresa; la continuidad de este trabajo sí se registró en `ChatGPT-migracion/main`.

### codebase-memory-mcp

- **Motor U6/main:** existen `docs/CODEBASE_MEMORY_MCP.md` y `.mcp.json`. El documento registra binario local 0.12.1 en la máquina de Pecas y un índice del 7-nov de 13 531 nodos / 27 173 aristas, reconstruido desde un espejo de `main` archivo por archivo. `.mcp.json` apunta a `/home/hatch/workspace/codebase-memory-mcp/bin/codebase-memory-mcp`.
- **CAPCOT/main:** también existen `docs/CODEBASE_MEMORY_MCP.md` y `.mcp.json`; el documento registra versión 0.12.1 e índice del 7-nov de 12 129 nodos / 13 879 aristas.
- **CAPCOT/feature/capcot-video-discovery-continuity:** no existen `docs/CODEBASE_MEMORY_MCP.md` ni `.mcp.json` (ambos 404 en la rama activa). Por tanto, el MCP no está integrado en la rama de trabajo de CAPCOT aunque sí aparezca en `main`.
- El índice de ambos proyectos es una fotografía del 7-nov. El propio documento exige reindexar cuando cambian los repositorios. U6 recibió cambios documentales el 8-nov; CAPCOT feature también cambió el 8-nov. La vigencia de ambos índices queda pendiente.
- Esta sesión de ChatGPT no expone ninguna herramienta MCP `codebase-memory` ni `DeepSeek Harness`; la configuración local no equivale a conexión viva en esta interfaz.
- `codebase-memory-mcp` es un servidor MCP de grafo/consulta estructural; complementa un agente de código, no sustituye por sí solo a Claude Code o a un harness.

### DeepSeek Harness

- `CAPCOT/main` contiene `docs/DSH_CERO_COSTO.md`, pero la rama activa `feature/capcot-video-discovery-continuity` no contiene ese documento ni configuración DSH. `motor-u6-storage/main` tampoco muestra integración DSH.
- El repo adicional `agente-cero-costo` documenta dsh `0.2.2-rc.1`, proveedor Groq por puente y una prueba de humo. La prueba no completó una tarea: el primer llamado planeó correctamente, el segundo recibió 429 por el límite gratuito de 8 000 TPM y `hola.txt` no se creó. No es una prueba de agente funcional de punta a punta a costo cero.
- La documentación de CAPCOT/main y del stack auxiliar no acredita que DSH esté conectado a la rama CAPCOT activa ni a U6.

### Divergencia de ramas CAPCOT

- Comparación `main...feature/capcot-video-discovery-continuity`: estado `diverged`, feature 650 commits por delante y 103 por detrás de `main`.
- `ajustes_entre_modelos/DELEGACIONES.md`, `docs/CODEBASE_MEMORY_MCP.md`, `.mcp.json` y `docs/DSH_CERO_COSTO.md` están en `main`; esos archivos no están en la rama feature consultada.
- El tablero de `main` contiene cinco pendientes, pero no se trató como tablero vigente de la rama feature. No se fusionó ni cambió ninguna rama.

## Corte verificado — 2026-11-09

### Cuentas GitHub e inventario

Consulta de ambas conexiones:
- `marcojpad-hash`: nueve repositorios visibles: `motor-u6-storage`, `capcot-capsulas-imaginantes`, `ChatGPT-migracion`, `orquestador-central`, `red-teaming-safety-u6`, `agente-cero-costo`, `baterias-tokens`, `baterias-memoria` y `memoria-compartida`.
- `marcosabines-hash`: cero repositorios visibles; la llamada terminó sin error.
- Los seis últimos son `DESCUBIERTO_ADICIONAL`. Se consultaron únicamente metadatos y README/documentación; no se escribieron ni alteraron.

Relación documental observada:
- `orquestador-central`: plano de control y coordinación transversal.
- `red-teaming-safety-u6`: subcorridas white-hat aisladas y ledger append-only, separado del U6 de producción.
- `agente-cero-costo`: stack auxiliar con DeepSeek Harness, puente Groq y orquestador.
- `baterias-tokens` y `baterias-memoria`: documentación de proveedores/límites y capacidad de máquinas.
- `memoria-compartida`: hechos verificados, decisiones y correcciones persistentes.

### codebase-memory-mcp

- **Motor U6/main:** `docs/CODEBASE_MEMORY_MCP.md` y `.mcp.json` presentes. El documento registra versión 0.12.1, binario local `/home/hatch/workspace/codebase-memory-mcp/bin/codebase-memory-mcp` e índice del 7-nov de 13 531 nodos / 27 173 aristas. El índice es anterior a los cambios documentales posteriores; reindexación pendiente.
- **CAPCOT/main:** `docs/CODEBASE_MEMORY_MCP.md` y `.mcp.json` presentes. El documento registra índice del 7-nov de 12 129 nodos / 13 879 aristas.
- **CAPCOT/feature/capcot-video-discovery-continuity:** ambas rutas devolvieron 404. La configuración de main no está integrada en la rama operativa.
- La configuración apunta a una ruta absoluta de la máquina de Pecas; no prueba que el proceso esté activo en otra máquina. Esta sesión no expone herramientas MCP de codebase-memory ni acceso al índice local.
- No se reindexó ni se instaló nada durante este corte.

### DeepSeek Harness

- **CAPCOT/main:** existe `docs/DSH_CERO_COSTO.md`; la rama feature activa no contiene ese documento. **Motor U6/main:** no se encontró integración DSH.
- El README y `dsh/DSH_PRUEBA_HUMO.md` de `agente-cero-costo` documentan que dsh 0.2.2-rc.1 arranca y el modelo planea herramientas, pero la tarea mínima no termina: el segundo llamado falla con HTTP 429 por el límite de 8 000 TPM de Groq gratuito; `hola.txt` no se creó. Ollama local no se probó.
- Por tanto, separar: configuración/arranque comprobados; ejecución de agente de punta a punta gratuita **NO VERIFICADA / FALLIDA con Groq gratis**. El dictamen afirmativo de configuración en CAPCOT/main no prevalece sobre el resultado de la prueba de humo.
- Esta sesión tampoco expone un conector/herramienta DSH. No se usaron claves, créditos ni proveedores de pago.

### Divergencia CAPCOT

La comparación actual `main...feature/capcot-video-discovery-continuity` devuelve `diverged`: feature 671 commits adelante y 120 detrás. No se cambió de rama ni se fusionó. Los archivos MCP/DSH que están en main no deben considerarse disponibles en feature.

## Corte verificado — 2026-11-10

### Inventario GitHub
- marcojpad-hash: 1 instalación visible (ID 174841554, selección all; nombre de App no expuesto) y 11 repositorios: motor-u6-storage, capcot-capsulas-imaginantes, ChatGPT-migracion, orquestador-central, red-teaming-safety-u6, agente-cero-costo, baterias-tokens, baterias-memoria, memoria-compartida, microserie-heredera-sadtalker y microserie-heredera-voces.
- marcosabines-hash: 0 instalaciones y 0 repositorios visibles, sin error.
- Los ocho repositorios fuera de los tres principales son DESCUBIERTO_ADICIONAL y permanecen fuera de escritura. Los dos nuevos microserie se revisaron solo por README/metadatos.

### Estado de herramientas
| Proyecto | Herramienta | Estado actual |
|---|---|---|
| U6/main | codebase-memory-mcp | docs/CODEBASE_MEMORY_MCP.md y .mcp.json presentes; versión documentada 0.12.1, índice del 7-nov (13 531 nodos / 27 173 aristas), binario en ruta local de Pecas. Sin proceso vivo verificado en esta sesión; índice pendiente de reindexar. |
| U6/main | DeepSeek Harness | Sin integración confirmada. Prueba previa con Groq gratuito falló con HTTP 429/8 000 TPM; Ollama no probado. |
| CAPCOT/feature | codebase-memory-mcp | .mcp.json y docs/CODEBASE_MEMORY_MCP.md ausentes en la rama activa; no está integrado aquí. |
| CAPCOT/feature | DeepSeek Harness | docs/DSH_CERO_COSTO.md/configuración ausentes en la rama activa; no está integrado aquí. |
| Ambos | Conector MCP en esta sesión | No se expone herramienta codebase-memory ni DSH en ALL_TOOLS; documentación/configuración local no equivale a conexión viva. |

### Estado operativo 10-nov
- CAPCOT: 23:30 sin paquete; paquete robot 9-nov anidado en cola y sin estado Grok (404), por lo que RECEPCION_GROK_NO_CONFIRMADA. No se movió ni redispatchó.
- Motor U6: HEAD d4af4d7629a79a24918325fdf9b89bc2f9c20821; último snapshot Actions 42811851624 success a las 06:00 CDMX; no es corrida predictiva.
- Automatizaciones: investigador y operador IN_PROGRESS al corte; auditor último COMPLETED 9-nov 16:33. next_run_time=null en las tres.
