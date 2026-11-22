# Operación autónoma — 22 de noviembre de 2026

## CAPCOT

### Cambios ejecutados y verificados

Repositorio `marcojpad-hash/capcot-capsulas-imaginantes`, rama `feature/capcot-video-discovery-continuity`, HEAD final `bbc05765b8c566c8335600bd8aa87d5fd7a1500e`.

- `proyectos/2026-11-22_genes-estatura-etapas/storyboard.json`: DOI `10.1038/s41467-026-79465-x` comprobado en Crossref; fuentes de las dos ubicaciones institucionales corregidas y coordenadas verificadas; campos alineados con `CAPCOT_STORYBOARD_TEXT_V2`; voz corregida a `edge-tts / es-MX-JorgeNeural / +7% / -2Hz`; prompt_base copiado literalmente del catálogo `papel_stop_motion`; conteo corregido a 231 palabras. No se cambió narración, claims, título ni arco.
- Comprobación manual previa a QA: 8 escenas, 78 s de escenas + 6 s de cortinilla = 84 s, mapa con puntos válidos, capa de dato, fuentes completas, cierre exacto, assets vacíos y render no generado. Cero errores en esas comprobaciones. No equivale a ejecutar el validador oficial.
- `narrative_qa` permanece ausente hasta la revisión independiente en frío. No se marcó preparado ni se promovió. `cola/estado/<id>.json` devuelve 404; no existe copia en `cola/entrada`, estado de ejecución ni salida. Clasificación: `NOT_DISPATCHABLE` y `RECEPCION_GROK_NO_CONFIRMADA`.
- `docs/briefs/2026-11-22_RADAR_CAPCOT.md`: shortlist de cinco candidatos y resultados RSS/Trends/Crossref actualizados.
- `docs/briefs/2026-11-22_CONTROL_COLA.md`: reconciliación de inventario, fuentes, CI, PRs y dispatch.

Commits de CAPCOT:
- `809454f7461243a0cd0f2992fc253e5085447752` — metadatos de fuente y coordenadas.
- `d130e72f62b324e44efb475f0c09faff899c7e4c` — prompt_base exacto del catálogo.
- `dabeb4c3ee963931572a8780b09857c17a5057af` — radar.
- `bbc05765b8c566c8335600bd8aa87d5fd7a1500e` — control de cola.

### Inventario y CI

- 26 proyectos en el alcance actual/interdiario: 12 del 5–7 nov, 6 del 18–20 nov, 7 del 21–23 nov y el nuevo borrador de genética de estatura. Los 25 anteriores conservan 9 QA PASS y 16 FAIL; el borrador nuevo queda pendiente de auditor independiente.
- Main: 52 registros en `data/publicaciones.json` y 39 en `data/rotacion.json`. Feature: 22 y 27 respectivamente; son snapshots desfasados y no autoridad de ocupación.
- PR #3: 697 archivos cambiados, 13 archivos data y 145 rutas de cola; OPEN/DRAFT/dirty, sin integrar.
- PR #15: head `30101e9`, base `d308149`; mergeabilidad no estable/no confirmada, sin CI de su head; 14 pruebas sin evidencia de ejecución y 32 hallazgos Semgrep en el run de main.
- La validación de feature disponible (`44951621909`) corresponde al commit antiguo `ed8659ec` y a Kuroshio, no al storyboard nuevo. No se atribuyeron los SUCCESS de main a feature.
- Worker main `45050940152`: SUCCESS con log `sin trabajo en cola.`; Semgrep `45048155842`: FAILURE, 32 hallazgos; Gitleaks `45048155922`: SUCCESS.
- El dispatch sigue limitado a JSON planos de primer nivel en `cola/entrada/*.json`. No se disparó workflow ni se envió payload.

## Motor U6

Repositorio `motor-u6-storage`: main consultado en solo lectura; rama activa consultada `alterno/cameo-pesos`, HEAD `78658535f103d33f30b4814d6cbb0f682af0ac79`.

- La afirmación antigua de que `gate_z90.py` no calcula Z90 desde nacimiento/muerte quedó superada por el código actual: `calcular_z90` existe y la gate comprueba primer corte en nacimiento, último corte en Z90 y orden temporal de ventanas.
- La compuerta todavía no es obligatoria en el runner. `_guardian_z90` permite `NO_CONFIGURADO` sin bloquear; la prueba `test_guardian_z90_no_configurado_sin_disciplina` lo confirma.
- La gate verifica fechas/estructura temporal, no la acumulación semántica efectiva del contenido de evidencia entre cortes.
- No existe ruta entry-only: `fabrica.py preparar_z` importa semillas y destinos en el mismo proceso y escribe entrada y desenlace sellado. No se ejecutó `preparar-z` ni `correr`.
- F007 revalidado solo con el archivo de semillas: 8 sujetos, 16 cortes, referencias Wikipedia, sin fechas de nacimiento/fallecimiento ni Z90 suficiente. No hay custodia independiente entregada. No se ejecutó ni incrementó n.
- CI del runner `45002771468`: 60 pruebas aprobadas. Esto acredita contrato/pruebas, no una corrida del motor ni calibración.
- PR #8 sigue OPEN/dirty y no se fusionó. No se tocaron C01–C20, destinos, custodia, motores canónicos, patrones, pesos, candados ni evidencia congelada.
- La auditoría automática de Actions `45037573857` ejecutó `git push origin HEAD:main` y actualizó snapshots en U6 main, en contradicción con la autoridad `main=SOLO_CONSULTA`. No se modificó el workflow ni se intentó revertir.

## Cuentas, privacidad y límites de escritura

- Instalación `marcojpad-hash`: 11 repositorios visibles. La cuenta `marcosabines-hash` no tiene instalación conectada ni repositorios visibles.
- `ChatGPT-migracion` es público y su README no lo declara privado; no se detectó contradicción de privacidad en ese repositorio. Esta actualización contiene solo estado operativo no sensible.
- `motor-u6-storage` es público aunque su README lo clasifica como privado; `orquestador-central` es público aunque `BOT_DOT_AUTONOMIA.md` lo clasifica como privado. No se escribió en esos repositorios ni se publicaron allí datos operativos adicionales.
- `memoria-compartida` y los demás repositorios adicionales permanecen en solo lectura. Issue #465 se consultó; no se publicó comentario porque el bus se mantiene de solo lectura salvo acuse expresamente debido y autorizado.
- No se modificaron secretos, permisos, ramas, main de U6, datos CAPCOT, publicaciones ni medios. No se abrió ni cerró PR y no se hizo merge.
