# Revalidación CAPCOT — 24 de noviembre de 2026, 20:00 CDMX

## Alcance y fuentes de verdad

- Rama de trabajo CAPCOT: `feature/capcot-video-discovery-continuity`, HEAD observado `962178fbf7400638b61ddd1dbde4c3cff23419ff`.
- `main` consultada en solo lectura, HEAD `7acd845aba9949311c6c34ce49895eaa290b5431`.
- Se relevaron de nuevo el radar y el control de cola del día, la programación de `main`, las fuentes de ingesta y el estado de los PR abiertos.
- La auditoría independiente de cola del 24-nov terminó antes de este corte y su resultado quedó leído de vuelta en `docs/briefs/2026-11-24_CONTROL_COLA.md`. No se repitió QA narrativo ya registrado.

## Cambios de main desde el corte de auditoría anterior

La comparación de `main` desde `6bce6166d424a8a793a81e1f44cbc71031c88462` hasta `7acd845aba9949311c6c34ce49895eaa290b5431` devuelve cuatro commits y dos archivos modificados:

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
