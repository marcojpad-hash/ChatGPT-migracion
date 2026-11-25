# Operador único — CAPCOT — 24 noviembre 2026, 18:00 CDMX

## Fuentes y revisión
- Repositorio: `marcojpad-hash/capcot-capsulas-imaginantes`.
- Rama de trabajo: `feature/capcot-video-discovery-continuity`, HEAD revisado `962178fbf7400638b61ddd1dbde4c3cff23419ff`.
- `main` revisado en solo lectura, HEAD `7acd845aba9949311c6c34ce49895eaa290b5431`.
- Se relevaron los contratos, guía, receta, flujo externo, contrato Grok, contrato narrativo, QA en frío, estilos, plantillas, scripts, datos de solo lectura, briefs, workflow y reportes recientes.

## Cola, slots y auditoría
- El control vigente registra 90 storyboards: 32 auditados (12 PASS y 20 FAIL) y 40 sin `narrative_qa`. En los 12 IDs del lote 5–7 de noviembre hay 2 PASS y 10 FAIL. No se repitió ningún PASS sin cambio narrativo.
- La rama de trabajo no contiene storyboard de proyecto para el 24 de noviembre. La ocupación registrada deja el 24 en 5/5 y del 25 al 28 en 7/5; no hay slot autorizado libre. No se creó storyboard ni se promovió copia a cola.
- En `main` existe el paquete anidado `2026-11-24_magnetismo-p-wave-eusi`. Su `programacion.json` declara `publish_at=2026-11-24T23:15:00Z`, hora local 17:15, y estado `programado_para_publicar`. El storyboard referencia `export.filename=capsula.mp4`, pero no existe salida/MP4 correspondiente en el árbol. El estado Grok individual y `ESTADO_EJECUCION.md` devuelven 404.
- Clasificación del paquete de `main`: `NOT_DISPATCHABLE`, `PROCESAMIENTO_PREEXISTENTE_NO_REDISPATCHAR`, `RECEPCION_GROK_NO_CONFIRMADA` y `MEDIOS_NO_VERIFICADOS_EN_REPOSITORIO`. No se modificó ni canceló. No hay proyecto de la rama de trabajo con el mismo fecha/slot, por lo que no se declara conflicto entre ramas.
- El issue #11 continúa abierto aunque conserva la etiqueta `hecho`. El storyboard de Cuásares mantiene `narrative_qa=FAIL/0` con `REVISION_INDEPENDIENTE_AUSENTE`. La revisión adjunta al PR #13 no acredita lectura en frío solo de la narración; no se elevó a PASS.

## Validador, workflow y fuentes
- PR #15 sigue abierto y usa una base antigua (`d3081499`). La versión vigente de `scripts/validar_storyboard.py` en la rama de trabajo ya rechaza booleanos como coordenadas y contiene el manejo de DOI/Crossref que el PR intentaba aportar. No se portó código redundante ni se cerró el PR.
- El workflow Grok y sus filtros se inspeccionaron; no se disparó ningún workflow ni se envió payload. No se creó ni editó ningún `cola/estado`.
- Los feeds RSS se intentaron de nuevo. El runtime devolvió `curl: (6) Could not resolve host` para `www.sciencedaily.com`, `trends.google.com`, `www.nasa.gov` y `www.nature.com`. El lector web rechazó varios XML con `400 Unsupported content-type`; el HTML de Google Trends tampoco fue accesible en esta pasada. Se conserva el radar existente y sus fuentes oficiales; los DOI que no resolvieron permanecen `PENDING_SOURCE`.
- El radar vigente conserva una lista activa de cinco candidatos. No se eligió tema ni estilo nuevo por falta de slot libre y por DOI sin resolver.

## Integridad
- No se modificó `main`, ningún `data/*.json`, secretos, permisos, publicaciones, programación ni medios.
- No se generaron frames, imágenes, voz, audio, video, renders ni placeholders.
- No se replican aquí detalles operativos de Motor U6 mientras siga abierta la discrepancia de visibilidad/privacidad de ese repositorio. Su estado permanece en su fuente autorizada.

## Siguiente paso mínimo
1. Obtener una revisión narrativa verdaderamente independiente para Cuásares y los storyboards del backlog que aún carecen de QA.
2. Resolver DOI/Crossref de los candidatos pendientes y esperar un slot libre antes de redactar o promover.
3. No redispatchar el paquete preexistente de `main`; exigir evidencia del estado Grok y de los medios antes de cualquier transición.
