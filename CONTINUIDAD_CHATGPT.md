# Continuidad ChatGPT — corte 2026-11-01

## Fuente operativa

Este repositorio conserva la continuidad transversal. Los datos y archivos de cada proyecto permanecen en su repositorio especializado:

- CAPCOT: `capcot-capsulas-imaginantes`, rama `feature/capcot-video-discovery-continuity`.
- Motor U6: `motor-u6-storage`, rama `main`.
- Migración: `ChatGPT-migracion`, rama `main`.
- Orquestador Central: repositorio adicional descubierto en la cuenta GitHub conectada; no forma parte de los tres repositorios principales de este mandato y se mantiene en observación de solo lectura hasta inclusión expresa del propietario.

No copiar código canónico del motor a este repo. No duplicar entregables CAPCOT.

## Estado actual

- **CAPCOT:** la auditoría del 1-nov encontró fallos en pulpo, cebolla y Baffin; Xolo y tiburón pasaron solo la lectura narrativa, no el control integral. Los 33 project_id heredados (116 archivos) se movieron reversiblemente a `cola/bloqueados/`; cero storyboard JSON permanece en `cola/entrada/`. El investigador ya creó el [radar 1-nov](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-01_RADAR_CAPCOT.md) y el borrador `proyectos/2026-11-01_red-electrica-pulso-minuto/storyboard.json`: 8 escenas, 190 palabras, 84 s, contrato narrativo completo. El DOI del paper sigue PENDIENTE; la fuente institucional está verificada. No hay `narrative_qa`, no se ha promovido y no existe acuse en `cola/estado/`. El run investigador terminó 14:37 y verificó dos entregables: radar y borrador red-electrica en `proyectos/`. El DOI del artículo principal sigue PENDIENTE; no hay `narrative_qa`, no se promueve a cola y el slot 23:30 sigue sin paquete.
- **Motor U6:** F006 R7 sigue siendo reevaluación de Courbet, no caso independiente. El protocolo de custodia independiente está verificado. C01–C20 siguen pendientes; no se modificaron Engine V5, el catálogo de 244 patrones ni candados.
- **Orquestador Central:** repositorio privado adicional verificado, PR draft #1 abierto y sin fusionar. Se mantuvo en solo lectura.
- **Dot:** no se considera conectado ni disponible desde esta sesión. El operador diario es sustituto parcial, no Dot ni un agente 24/7.
- **Notion:** páginas V15 antiguas son históricas cuando contradicen Motor U6. GitHub prevalece.
- **Analítica social:** no hay conexión confirmada a métricas privadas de Meta, YouTube o TikTok.

Últimos registros:
- Auditoría transversal: [reportes/2026-10-31_AUDITORIA_TRANSVERSAL.md](reportes/2026-10-31_AUDITORIA_TRANSVERSAL.md).
- Operación autónoma: [reportes/2026-11-01_OPERACION_AUTONOMA.md](reportes/2026-11-01_OPERACION_AUTONOMA.md).


## Cuentas y repositorios GitHub comprobados

Comprobación actual de las dos conexiones:
- `marcojpad-hash`: una instalación visible; cuatro repositorios devueltos: `ChatGPT-migracion`, `capcot-capsulas-imaginantes`, `motor-u6-storage`, `orquestador-central`.
- `marcosabines-hash`: sin instalaciones ni repositorios devueltos.

Los tres repositorios principales de trabajo siguen siendo `ChatGPT-migracion/main`, `capcot-capsulas-imaginantes/feature/capcot-video-discovery-continuity` y `motor-u6-storage/main`. `orquestador-central` está clasificado como DESCUBIERTO_ADICIONAL y no recibió escrituras.


## Automatizaciones

| Automatización | Horario guardado CDMX | Último run observado |
|---|---:|---|
| Operador autónomo general | Diario 08:00, exact_schedule | `7dd18f1e-af70-8331-8d36-64854ab926b3`, iniciado 14:20; `in_progress` al último peek. |
| Agente de investigación CAPCOT | Diario 08:00 hasta 24-nov, exact_schedule | `eb74bc97-0478-832c-a823-25af9adab923`, completado 14:37; radar y borrador verificados. `scheduled_for` fue 14:20, no 08:00. |
| Auditor CAPCOT — cola y rotación | Diario 15:00, flexible_schedule | `47f25beb-8e28-8324-b66b-c3923f3e90e3`, completado 14:27; corrió 40 minutos antes del slot guardado. |

Las tres muestran `next_run_time=null`. Operador e investigador muestran `scheduled_for=14:20` aunque sus reglas guardadas dicen 08:00; causa no identificada. Los prompts se actualizaron después del inicio de los runs. El auditor debe revisar el borrador de red eléctrica y registrar los siete checks antes de cualquier promoción.


## Reglas de trabajo

- Resolver directamente lo reversible y autorizado.
- Mantener separados CAPCOT y Motor U6; sus métricas, decisiones y entregables no se mezclan.
- No inventar acceso, ejecución, datos, aceptación de Grok ni actividad en segundo plano.
- No publicar, enviar mensajes externos, gastar créditos, modificar permisos ni alterar archivos canónicos sin autorización.
- Separar evidencia verificada, ejecución, inferencia y pendiente.



## Actualización operativa — 2026-11-02

Esta sección prevalece sobre los estados del corte 2026-11-01 cuando haya diferencias. Registro detallado: [reportes/2026-11-02_OPERACION_AUTONOMA.md](reportes/2026-11-02_OPERACION_AUTONOMA.md).

- **Cuentas GitHub:** `marcojpad-hash` tiene una instalación (ID 174841554, selección all) y cuatro repositorios visibles: `ChatGPT-migracion`, `capcot-capsulas-imaginantes`, `motor-u6-storage`, `orquestador-central`. `marcosabines-hash` tiene cero instalaciones y cero repositorios visibles. Los tres repositorios principales permanecen en alcance; `orquestador-central` es DESCUBIERTO_ADICIONAL, solo lectura.
- **CAPCOT 2-nov:** existen dos proyectos cargados por Grok Bot el 31-oct: camarón mantis y pan duro. Tienen salidas y registros audiovisuales, pero sus storyboards en `proyectos/` no tienen `narrative_contract` ni `narrative_qa`. Los QA de `salidas/*/qa.json` son audiovisuales, no narrativos. Los dos estados de ejecución se corrigieron a BORRADOR_EN_PROYECTOS_NO_APTO_PARA_PROMOCION. No se redispatchará ninguno: ya hay salidas y registros de publicación.
- Para ambos proyectos falta `cola/estado/<project_id>.json`: RECEPCION_GROK_NO_CONFIRMADA según el contrato, aunque existan commits y salidas. `cola/entrada/` solo contiene `.gitkeep`.
- Los registros de YouTube conservan IDs anteriores descritos como todavía programados; existe riesgo de duplicado y no se canceló nada. El registro de rotación del camarón muestra 4 vistas mientras el snapshot de publicación conserva privacidad `private`; discrepancia abierta.
- **Motor U6:** el commit más reciente solo actualizó snapshots de auditoría Actions; no hay cambio de motor. C01–C20 siguen pendientes y los candados permanecen intactos.
- **Automatizaciones:** operador actual en `in_progress`; investigador sin run del 2-nov; auditor sin run del 2-nov y conserva `flexible_schedule`. `next_run_time=null` en las tres.


## Actualización de continuidad y migración — 2026-11-03

Esta actualización amplía el arranque para que una sesión nueva pueda continuar sin depender de la conversación actual.

- Mapa de herramientas y estado de conectores: [docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md](docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md).
- Memoria compartida y coordinación entre modelos: [docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md](docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md).
- Pruebas pendientes antes del fin de la promoción: [docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md](docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md).
- Bandeja: [bandeja/README.md](bandeja/README.md); usar [bandeja/PLANTILLA.md](bandeja/PLANTILLA.md) y dejar acuse observable. Un archivo no prueba que otro modelo lo haya leído.

**Modelo de continuidad:** ChatGPT-migracion guarda reglas y estado transversal; motor-u6-storage conserva la autoridad U6; capcot-capsulas-imaginantes conserva la autoridad CAPCOT. GitHub es memoria operativa persistente y espacio de trabajo, pero no es un bus de mensajería en tiempo real. No asumir que una sesión nueva hereda las conexiones; comprobar cuenta, permisos y recursos.

**Conexiones comprobadas el 3-nov:** GitHub marcojpad-hash accesible; GitHub marcosabines-hash sin repositorios visibles; vidIQ autenticado en marcosabines@gmail.com y devuelve cero canales; Dropbox responde con marco.jp@live.com.mx; Notion responde; Floot sin proyectos; Canva sin Brand Kits; Runway sin workflows guardados; Undermind sin workspaces; n8n skill disponible pero sin conector directo localizado. Las tres automatizaciones principales están habilitadas, aunque next_run_time devolvió null. Ver mapa para límites y acciones.

**No declarar migración terminada:** falta probar un handoff real entre dos modelos/cuentas, confirmar reconexión de GitHub en una sesión nueva y resolver las conexiones de vidIQ y automatizaciones.

## Últimos cortes verificados — 2026-11-03

- CAPCOT: la auditoría posterior del 2-nov está en [CONTROL_COLA 2026-11-02](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-02_CONTROL_COLA.md). Resultado NO DISPATCHABLE; cuatro proyectos con producción/publicación preexistente no deben redispatcharse; agenda 5–7 nov requiere reconciliar IDs/duplicados.
- Motor U6: el snapshot [ULTIMO_ESTADO.md](https://github.com/marcojpad-hash/motor-u6-storage/blob/main/avances/auditoria_corridas/ULTIMO_ESTADO.md) muestra auditorías programadas exitosas hasta 2-nov 23:05 CDMX. Son auditorías Actions, no nuevas corridas empíricas.
- Preparación de migración: [reporte 2026-11-03](reportes/2026-11-03_PREPARACION_MIGRACION.md). El handoff de recuperación permanece PENDIENTE hasta que otra sesión/modelo deje acuse observable.


## Actualización operativa — 2026-11-05, 12:04 CDMX

Esta actualización prevalece sobre cortes anteriores para automatizaciones y CAPCOT al momento indicado. Reporte: [reportes/2026-11-05_OPERACION_AUTONOMA.md](reportes/2026-11-05_OPERACION_AUTONOMA.md).

- Operador autónomo: run `f9aff71c-1fac-832d-8436-7b07bd3516e4` completado 08:07:07 CDMX; el estado in_progress mostrado en una consulta anterior ya fue superado por el resultado final.
- Investigador CAPCOT: run `85130fc3-cbf8-8329-85ad-c0f8c4812825` completado 08:01:35; commit `1f1861afd5c76da18341253ce1d25c8ab016f8fd`, radar NO_DUPLICAR.
- Auditor CAPCOT: último run conocido `e38f5799-375c-832b-b07f-c9c367f5e0e5`, completado 4-nov; no hay auditoría del 5-nov.
- Árboles 5-nov: el storyboard canónico `proyectos/2026-11-05_inter-arboles-se-comunican/storyboard.json` sí trata redes micorrícicas comunes y Karst et al. 2023 (blob SHA `854c12ed9b77f82f66ec736797dea4d700983d78`). La afirmación de que el canónico trataba respiración nocturna era errónea; esa variante es un artefacto distinto bloqueado. El canónico sigue sin autorización de promoción hasta QA narrativo independiente PASS y validación estructural correcta.
- Para los proyectos del 5-nov sin `cola/estado/<project_id>.json`, mantener `RECEPCION_GROK_NO_CONFIRMADA`; no crear estados Grok.
- n8n: la consulta actual devuelve cero skills y no hay conector ejecutable. El mapa fue corregido; no existe acceso operativo a una instancia n8n.
- GitHub devuelve cinco repositorios en marcojpad-hash y cero en marcosabines-hash; `orquestador-central` y `red-teaming-safety-u6` son DESCUBIERTO_ADICIONAL, solo lectura.
- La migración sigue pendiente del acuse verificable de una segunda sesión/modelo.


### Corrección verificada posterior — 2026-11-05

- Se corrigió el radar CAPCOT: commit `d5452fde92d2ea7ac46394c728a04db533dd6236`; blob releído `1c4dcf8cb79f014e6456759675ccd19837dad2d3`. El storyboard canónico de árboles sí corresponde al tema asignado; su QA es FAIL 78 por apertura genérica, no por desajuste temático.
- Se corrigió el prompt del Auditor CAPCOT y se verificó que el texto guardado ya no ordena marcar árboles como desajuste temático. El último run del auditor sigue siendo el del 4-nov; la corrección del prompt aún no ha sido ejercida por una ejecución programada completada.
- El validador estructural exige seis campos narrativos por escena que faltan en los paquetes revisados. No se rellenaron automáticamente porque requieren decisiones narrativas, no una corrección mecánica.

## Actualización operativa — 2026-11-06

El corte detallado está en [reportes/2026-11-06_OPERACION_AUTONOMA.md](reportes/2026-11-06_OPERACION_AUTONOMA.md); el estado por proyecto quedó actualizado en [PROYECTOS_Y_ESTADO.md](PROYECTOS_Y_ESTADO.md).

- **CAPCOT:** el investigador completó NO_DUPLICAR y solo actualizó el radar (7e989a5). Los cuatro storyboards del 6-nov ya tenían QA narrativo independiente del 5-nov: ballena FAIL 80, aguacate FAIL 79, ranas FAIL 83 y dunas PASS 94. Los cuatro fallan estructura por seis campos ausentes en cada escena; cola vacía y recepción Grok no confirmada en los cuatro. No se promovió ni redispatchó nada. El prompt del investigador se actualizó después del run para leer y reportar narrative_qa preexistente sin escribirlo; la regla aplica a futuras ejecuciones.
- **Dispatch:** el último run (#147, 1-nov) falló en la versión antigua del workflow por Falta configurar GROK_WEBHOOK_URL. La versión actual hace webhook opcional y usa buzón interno como fallback, pero todavía no tiene una ejecución que verifique ese camino. Un marcador interno no es acuse de Grok.
- **Agenda:** persiste el conflicto documental 19:00/17:45/23:30. No se cambió la política ni la agenda.
- **Motor U6:** auditoría Actions exitosa a las 06:03 CDMX; no es una corrida predictiva. C01–C20 y las cinco comparaciones causales siguen pendientes; canónicos intactos.
- **GitHub:** marcojpad-hash expone cinco repositorios. orquestador-central y red-teaming-safety-u6 son DESCUBIERTO_ADICIONAL, solo lectura. marcosabines-hash no devuelve instalaciones ni repositorios.
- **Automatizaciones:** investigador completado; auditor con último run 5-nov; el operador de este corte estaba in_progress al último peek, sin resultado final registrado. Las tres siguen habilitadas y next_run_time=null.
- **Migración:** el handoff bandeja/2026-11-03_RECUPERACION_MIGRACION.md continúa PENDIENTE; falta acuse verificable de otra sesión/modelo. Dot no está conectado a esta sesión.