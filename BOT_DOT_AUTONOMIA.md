# Coordinación autónoma y Dot — vigente 2026-11-01

## Dot nativo

La documentación oficial revisada indica que Dot se habilita gradualmente en planes elegibles y no incluye Go. No hay herramienta desde esta sesión para activar Dot. No afirmar que está conectado.

## Sustituto parcial activo

Automatización: Operador autónomo general.  
ID: `6ae59327d5fc8191b0c9a900ac86e028`.  
Horario guardado: diario 08:00, `America/Mexico_City`.  
Función: revisar repositorios principales, automatizaciones, pendientes y continuidad; ejecutar pasos reversibles y autorizados; registrar reportes materiales en GitHub.

Limitación: una ronda diaria no equivale a Dot 24/7. La ejecución del 1-nov estaba en progreso al corte consultado; no se declara completada.

## Bots CAPCOT

- **Agente de investigación CAPCOT:** diario 08:00 hasta el 24-nov; brief y storyboard textual. No genera medios ni publica.
- **Auditor CAPCOT — cola y rotación:** diario 15:00; valida todos los paquetes del día, rotación, dispatchabilidad y recepción de Grok. No produce cápsulas ni medios.
- **Grok/Imaginantes:** conserva selección editorial, producción audiovisual, QA oficial y publicación. La recepción se confirma exclusivamente con `cola/estado/YYYY-MM-DD_slug.json`; sin ese archivo, la recepción no está confirmada.

## Orquestador Central — adicional descubierto

Repositorio privado: [orquestador-central](https://github.com/marcojpad-hash/orquestador-central). Rama de trabajo `feature/core-mvp-l1`; [PR draft #1](https://github.com/marcojpad-hash/orquestador-central/pull/1).

El prototipo HTTP/SQLite tiene dos checks de CI exitosos: uno sobre el HEAD de la rama (`446d5277b9cc4896ee18d3d5216598835f9b274e`) y otro sobre el merge ref del PR (`aeed8e8d71ecbfc2e5b7c243b18d7ef249fb8023`); cada ejecución pasó 3 pruebas unitarias. No está desplegado ni operativo como coordinador multiagente: faltan adaptadores de proveedores, runtime persistente de workers, entrada móvil universal y retorno entre canales. No se fusionó a `main` ni se desplegó. Se mantiene en observación de solo lectura hasta que el propietario lo incorpore expresamente al alcance.

## Coordinación

- ChatGPT coordina y verifica; no finge que los bots se comunican si no hay evidencia.
- GitHub es el registro de trabajo y entrega.
- Notion conserva contexto histórico; no prevalece sobre los repositorios vigentes.
- No existe conexión directa confirmada con Dot.
- No confundir programación de una automatización con ejecución completada; revisar `last_run`, `latest_result` y `next_run_time`.
