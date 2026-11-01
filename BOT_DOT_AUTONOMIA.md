# Coordinación autónoma y Dot — vigente 2026-11-01

## Dot nativo

La documentación oficial revisada indica que Dot se habilita gradualmente en planes elegibles y no incluye Go. No hay herramienta desde esta sesión para activar Dot. No afirmar que está conectado.

## Sustituto parcial activo

Automatización: Operador autónomo general.  
ID: `6ae59327d5fc8191b0c9a900ac86e028`.  
Horario guardado: diario 08:00, `America/Mexico_City`, exact_schedule.  
Función: revisar repositorios principales, automatizaciones, pendientes y continuidad; ejecutar pasos reversibles y autorizados; registrar reportes materiales en GitHub.

Limitación: una ronda diaria no equivale a Dot 24/7. El run del 1-nov `7dd18f1e-af70-8331-8d36-64854ab926b3` seguía `in_progress` al último peek. `next_run_time` nulo.


## Bots CAPCOT

- **Agente de investigación CAPCOT (08:00):** entrega brief y borrador textual en `proyectos/<project_id>/storyboard.json`. No escribe en `cola/entrada/`, no se autoevalúa y no crea `narrative_qa`.
- **Auditor CAPCOT (15:00):** revisor distinto del redactor. Oculta título, resumen, arco, notas y `narrative_contract`; lee únicamente la narración concatenada. Registra `narrative_qa` con siete checks, score, basis y flags. Solo PASS (>=85, todos true, flags vacíos) y validador estructural correcto permite promover a `cola/entrada/YYYY-MM-DD_slug.json`; FAIL/no revisión va a `cola/bloqueados/`.
- **Grok/Imaginantes:** conserva selección editorial, producción audiovisual, QA oficial y publicación. Recepción solo se confirma con `cola/estado/YYYY-MM-DD_slug.json`; no crear ni modificar ese archivo desde ChatGPT.

Estado 1-nov: el investigador completó 14:37 y verificó radar y borrador red-electrica en `proyectos/`; el DOI principal está pendiente y el storyboard no tiene QA. El auditor terminó antes de la actualización final del prompt y no revisó este borrador. La cola de entrada está vacía; 33 project_id heredados se conservan en bloqueados.


## Orquestador Central — adicional descubierto

Repositorio privado: [orquestador-central](https://github.com/marcojpad-hash/orquestador-central). Rama de trabajo `feature/core-mvp-l1`; [PR draft #1](https://github.com/marcojpad-hash/orquestador-central/pull/1).

El prototipo HTTP/SQLite tiene dos checks de CI exitosos: uno sobre el HEAD de la rama (`446d5277b9cc4896ee18d3d5216598835f9b274e`) y otro sobre el merge ref del PR (`aeed8e8d71ecbfc2e5b7c243b18d7ef249fb8023`); cada ejecución pasó 3 pruebas unitarias. No está desplegado ni operativo como coordinador multiagente: faltan adaptadores de proveedores, runtime persistente de workers, entrada móvil universal y retorno entre canales. No se fusionó a `main` ni se desplegó. Se mantiene en observación de solo lectura hasta que el propietario lo incorpore expresamente al alcance.

## Coordinación

- ChatGPT coordina y verifica; no finge comunicación entre bots si no hay evidencia.
- GitHub es el registro de trabajo y entrega.
- Notion conserva contexto histórico; no prevalece sobre los repositorios vigentes.
- No existe conexión directa confirmada con Dot.
- Consultar `last_run`, `latest_result` y `next_run_time` antes de atribuir actividad. Un run `in_progress` no es un resultado completado.
