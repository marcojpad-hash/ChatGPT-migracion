# Mapa operativo de herramientas — Motor U6 y CAPCOT
Fecha de comprobación: 2026-11-03

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
