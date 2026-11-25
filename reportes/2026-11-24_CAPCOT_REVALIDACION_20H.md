# Revalidación CAPCOT — 24 de noviembre de 2026, 20:00 CDMX

## Alcance y fuentes de verdad

- Rama de trabajo CAPCOT: `feature/capcot-video-discovery-continuity`, HEAD observado `962178fbf7400638b61ddd1dbde4c3cff23419ff`.
- `main` consultada en solo lectura, HEAD `7df97a20c8924401b663b91b9393487a42034601` (revalidado a las 20:03 CDMX).
- Se relevaron de nuevo el radar y el control de cola del día, la programación de `main`, las fuentes de ingesta y el estado de los PR abiertos.
- La auditoría independiente de cola del 24-nov terminó antes de este corte y su resultado quedó leído de vuelta en `docs/briefs/2026-11-24_CONTROL_COLA.md`. No se repitió QA narrativo ya registrado.

## Cambios de main desde el corte de auditoría anterior

La comparación de `main` desde `6bce6166d424a8a793a81e1f44cbc71031c88462` hasta `7acd845aba9949311c6c34ce49895eaa290b5431` devolvió cuatro commits y dos archivos. Después, el commit `7df97a20c8924401b663b91b9393487a42034601` (20:03 CDMX) modificó únicamente `data/endscreens_rotacion.json`:

- `data/endscreens_rotacion.json`
- `tools/orquestador/reporte.md`

No aparecen cambios en proyectos, entradas de cola, salidas, publicaciones ni programación. La ocupación y los bloqueos documentados en el corte de las 18:00 permanecen vigentes; no se detectó un slot nuevo.

## Ingesta RSS y Google Trends

Se reintentaron tres endpoints definidos en `scripts/tendencias.py` o en el contrato de ingesta:

| Fuente | Resultado exacto |
|---|---|
| Google Trends RSS México | `URL https://trends.google.com/trending/rss?geo=MX is not accessible via this tool` |
| NASA News Release RSS | `400 Unsupported content-type: application/rss+xml` |
| ScienceDaily Science RSS | `400 Unsupported content-type: application/xml` |

El corte anterior de las 18:00 conserva los errores de DNS del runtime y los resultados de los demás feeds. No se atribuyen estos fallos al contenido de los proveedores: son errores de acceso del lector disponible.

Como respaldo se abrió la vista HTML oficial de [Google Trends México](https://trends.google.com/trending?geo=MX). El corte visible indica **197 tendencias de las últimas 24 horas**. Los primeros 25 términos están dominados por fútbol, entretenimiento, noticias y consultas generales; no aparece un tema admisible de ciencia, naturaleza, cocina, cuerpo o espacio. Trends se usa solo como señal de demanda, nunca como fuente científica.

## Revalidación de fuentes primarias y DOI

- **Agujeros negros de baja masa / supernovas fallidas:** la ficha primaria de [Physical Review D](https://journals.aps.org/prd/abstract/10.1103/mnzq-w1b5) está accesible y muestra el DOI `10.1103/mnzq-w1b5`, publicación del 10-nov-2026 y el análisis de 153 observaciones GWTC-4.0. El artículo presenta la subpoblación de agujeros negros de supernovas fallidas como interpretación compatible, no como observación directa del mecanismo.
- **Recubrimientos adhesivos de un pecio romano:** la ficha primaria de [Frontiers in Materials](https://www.frontiersin.org/journals/materials/articles/10.3389/fmats.2026.1758862/full) está accesible y muestra el DOI `10.3389/fmats.2026.1758862`. El artículo original se publicó el 24-abr-2026; la novedad del corte de noviembre es el comunicado, no la publicación del estudio. Su encaje editorial sigue siendo dudoso.
- **Bar galáctica / onda de choque y virus HK97:** las páginas de Nature redirigen a la pasarela de autorización y devuelven HTTP 500.
- **Muestras lunares Chang'e-6:** la página de Science devolvió HTTP 403.
- **FRB MNRAS:** la página editorial agotó el tiempo de espera en este intento.
- **Crossref REST y DOI resolver:** las llamadas directas a `api.crossref.org` y `doi.org` no fueron accesibles en esta sesión para los DOI comprobados. Por tanto, la presencia del DOI en una página editorial no se eleva a verificación Crossref/resolvedor.

Los candidatos existentes permanecen en el radar con sus estados diferenciados. Los DOI que no superaron Crossref/resolvedor continúan `PENDING_RESOLVEDOR` o `PENDING_SOURCE`; no se reclasifican por inferencia.

## Decisión editorial y de producción

- El radar del 24-nov ya contiene cinco candidatos recientes y cortes complementarios; no hace falta duplicar el brief ni inventar otro candidato para completar el mínimo.
- El 24-nov sigue sin slot libre autorizado; la rama de trabajo no contiene storyboard nuevo para esa fecha.
- No se creó storyboard, no se promovió una copia a `cola/entrada/`, no se creó ni editó estado Grok y no se redispatchó el paquete preexistente de `main`.
- No se generaron medios, placeholders ni publicaciones. No se disparó ningún workflow ni se envió payload externo.
- No se modificaron `data/*.json`, `main`, secretos ni permisos.

## Estado

- **VERIFICADO:** comparación de ramas, lectura de vuelta del control vigente, vista HTML de Trends, fichas editoriales primarias APS y Frontiers.
- **PENDIENTE:** acceso a RSS por un lector compatible, resolución Crossref/DOI de los candidatos marcados, recepción Grok individual y liberación de un slot real.
- **NO EJECUTADO:** validador Python local, generación de storyboard, promoción y cualquier producción audiovisual.


## Revalidación posterior — 24 de noviembre, 20:03–20:10 CDMX

### Main, cola e historial

- El nuevo commit de main `7df97a20` solo cambia `data/endscreens_rotacion.json`. Añade el corte `snapshot_2026-11-24_20` y una propuesta marcada `pendiente_studio`; no cambia proyectos, programación, publicaciones ni cola.
- El registro `data/publicaciones.json` contiene tres entradas con fecha 24-nov. El archivo de alineación del día documenta además dos publicaciones a las 07:00, cinco Shorts programados sin MP4 local y una publicación ya programada a las 17:00. Dos elementos compiten por las 17:00; el paquete de magnetismo de las 17:15 aparece aparte en `programacion.json`. El inventario del corte anterior suma nueve elementos previstos/publicados. No se redistribuye ni cancela ninguno.
- No hay archivo separado `historial_youtube` en el árbol actual; la evidencia disponible está en `data/publicaciones.json`, `data/tt_fb_alineacion_2026-11-24.json` y snapshots de rotación.
- Los dos marcadores de `handoffs/grok_inbox/` en main tienen `status=pending`. Son marcadores de buzón, no acuses de Grok. No existe estado individual `cola/estado/` para el paquete preexistente de 17:15.
- La ejecución programada del trabajador de cola en main, run [45530346824](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/actions/runs/45530346824), terminó SUCCESS pero el log exacto fue `[trabajador] sin trabajo en cola.`. Es una ejecución de main y no acredita procesamiento de la rama feature.
- La acción `capcot-grok-dispatch.yml` continúa limitada a JSON planos `cola/entrada/*.json`; el selector usa `find -maxdepth 1`. El procesador `scripts/procesar_cola.py` sí acepta carpetas anidadas con `storyboard.json`. La discrepancia de profundidad sigue sin corregirse. El workflow usa el secreto `GROK_WEBHOOK_URL`; el último diagnóstico disponible ya lo identificó como ausente. No se consultaron ni expusieron valores de secretos.

### Seguridad y Actions

- En el nuevo commit de main, Gitleaks terminó SUCCESS (run [45530165821](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/actions/runs/45530165821)).
- Semgrep volvió a FALLAR con **37 hallazgos bloqueantes** (run [45530165792](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/actions/runs/45530165792)); el job escaneó 1,253 archivos con 361 reglas. No se generó artifact SARIF porque el paso de carga quedó omitido. No se modificó main ni se reintentó el workflow.

### RSS: errores del reintento completo

El lector web no pudo consumir los XML/RSS. Errores exactos de este corte:

| Fuente | Error |
|---|---|
| ScienceDaily ciencia | `400 Unsupported content-type: application/xml` |
| ScienceDaily salud | `400 Unsupported content-type: application/xml` |
| ScienceDaily espacio | `400 Unsupported content-type: application/xml` |
| Phys.org | `400 Unsupported content-type: text/xml` |
| NASA | `400 Unsupported content-type: application/rss+xml` |
| ESA Space Science | `404 Not Found` |
| Nature RSS | `400 Unsupported content-type: application/rss+xml` |
| EurekAlert | `URL ... is not accessible via this tool` |
| SINC | `URL ... is not accessible via this tool` |
| UNAM Global | `400 Unsupported content-type: application/rss+xml` |
| Google Trends RSS México | `URL ... is not accessible via this tool` |

La vista HTML oficial de [Google Trends México](https://trends.google.com/trending?geo=MX) sigue disponible como respaldo: muestra 197 tendencias de 24 horas; los primeros 25 términos no aportan un candidato científico/natural admisible. El corte previo conserva además los errores DNS exactos del runtime.

### Candidato oficial adicional

- La declaración conjunta de [Lean FRO y Mathlib](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) está accesible y fechada el 21-nov-2026. La comunidad declara haber verificado formalmente el enunciado y la prueba en Lean, con compilación y comprobadores independientes.
- La ficha de [Clay Mathematics Institute](https://www.claymath.org/millennium/riemann-hypothesis/) continúa mostrando la hipótesis como problema activo y mantiene publicadas sus reglas de premio. El ángulo correcto es la verificación formal comunicada por Lean/Mathlib; no afirmar premio concedido ni cambio de estado por Clay.
- Es un candidato de investigación para slot futuro, no un storyboard ni una selección.

## Cierre de este corte

- **VERIFICADO:** HEAD actualizado de main, diff de un solo archivo, worker sin trabajo en cola, Gitleaks SUCCESS, Semgrep con 37 hallazgos, 10 feeds RSS, Trends HTML, fichas oficiales Lean/Clay y estado pendiente de los marcadores de buzón.
- **NO EJECUTADO:** workflows manuales, promoción, redispatch, validador Python local, producción audiovisual y cambios en main/data/secretos.
