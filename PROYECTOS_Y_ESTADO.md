# Proyectos, referencias y estado conocido

## Actualización operativa: autonomía y coordinación (2026-10-31)

- Se integró en `main` la regla transversal: ChatGPT debe ejecutar y cerrar tareas autorizadas de forma proactiva, sin esperar instrucciones intermedias.
- Se actualizaron `README.md`, `CONTINUIDAD_CHATGPT.md` y `ESTILO_DE_TRABAJO.md`.
- Se creó `BOT_DOT_AUTONOMIA.md`, que define responsabilidades de ChatGPT, bots, automatizaciones y Dot; flujo de delegación, verificación, reportes y límites de autorización.
- La documentación establece explícitamente que Dot solo debe considerarse activo cuando su disponibilidad, conexión y ejecución estén comprobadas. La creación de este protocolo no activa Dot ni le concede permisos.
- Los cuatro documentos modificados/creados se releen desde `main` y sus SHA de contenido fueron comprobados. No se modificaron los repositorios Motor U6 ni CAPCOT en esta operación.

**Fecha de elaboración:** 2026-10-25  
**Advertencia:** este documento recoge contexto de conversaciones anteriores. No equivale a una inspección actual de cada repositorio o archivo del motor. Verificar antes de actuar.

## Repositorios
- Migración ChatGPT: https://github.com/marcojpad-hash/ChatGPT-migracion — repositorio privado exclusivo para continuidad entre cuentas. Confirmado en esta sesión: existe en la cuenta marcojpad-hash, rama por defecto main, permisos de lectura/escritura de la conexión actual; README.md fue leído desde main.
- Motor U6: https://github.com/marcojpad-hash/motor-u6-storage — proyecto separado. No modificar desde el repositorio de migración.
- CAPCOT: capcot-capsulas-imaginantes — proyecto separado. No modificar desde el repositorio de migración.

## Motor / Trabajo V15.x: referencias históricas que deben verificarse
- Se ha indicado que Engine_V5_CANONICO_SOLO.py es canónico y no debe modificarse.
- Engine_V15_INTEGRADO.py declara históricamente VERSION = "V15.1_INTEGRADO".
- Se ha trabajado con la referencia V15.3_UNIFICADO_ALTERNO_V0.7, DEFAULT_SEED = 20260924, CANON_HASH = "48333cd11b9234f1", N_CANON = 244, M = 0.998 y PATTERNS_SHA = "d827dcc3882634ec2d21b3a480d0fee811b28d8fa1b73bab04f0af2c2d6667a1". Estos son datos históricos de contexto, no hashes comprobados en esta sesión.
- Archivo de patrones citado: patterns_final_v14.json, descrito como 244 patrones.
- Otros nombres mencionados: traza_campo_244.py, Corpus_Final_Unificado_17_Formulas.txt, plugin_familias_gloria_sacro.py, plugin_otto_numinoso.py, circulo_12_cadenas_enredadas.
- Referencias del modelo vectorial: X_t = [P_t; A_t; C_t] con tres componentes de 244; D = 0.998; hash histórico 48333cd11b9234f1.
- Reglas históricas: no modificar el motor canónico ni los patrones canónicos; documentar plugins/sidecars ON/OFF y Monte Carlo; distinguir coincidencia textual de similitud semántica por embeddings; evitar usar información posterior al corte.
- Se reportó un LOO de 15 biografías y 121 casos con 64.46% top-1 y 97.52% top-3 en el archivo PROPUESTA_GRUPO_B_V0_1_PRUEBA_2026-09-06.txt. Es un resultado reportado previamente; revisar el archivo fuente antes de reutilizarlo como resultado verificado.
- Se mencionó OBSERVATORIO_LUCERNA_001 como caso sintético de ocho cortes, con artefactos y hashes reportados anteriormente. La evaluación predictiva se había descrito como pendiente, con H1 eterno_retorno_02_cosmizacion_fundacion, H2 jaldun_02_institucionalizacion_y_sedentarismo, estado LATENTE y veredicto HIT/MISS/PARCIAL no establecido. No presentar eso como predicción validada sin evidencia posterior.
- Se ha pedido revisar el caso Casanova, sus guardias, los campos sin origen y los archivos de corrida duplicados. Estado actual: pendiente de inspección de archivos actualizados.

## CAPCOT / cápsulas
- Objetivo histórico: cápsulas académicas e infografías animadas de aproximadamente 1–3 minutos.
- Preferencia: herramientas gratuitas, interfaces web sin API y máxima automatización desde guion hasta video final, verificando límites vigentes.
- No modificar el motor U6 como parte de las tareas CAPCOT. Los videos/correcciones deben revisarse a partir de los archivos reales disponibles, no de supuestos sobre quién los corrigió.

## Continuidad, almacenamiento y automatizaciones
- Se pidió crear un archivo de continuidad para migrar a una cuenta nueva de ChatGPT y guardar el estado en un repositorio dedicado.
- En esta conversación se programó una tarea única para preparar un paquete de continuidad unas tres horas después de la solicitud. No asumir que la tarea ya se ejecutó; comprobar su estado cuando sea necesario.
- Se ha solicitado una revisión diaria a las 8:00 a. m. de elementos nuevos, comparación por bytes y, si hace falta, línea por línea, y clasificación en carpetas. No asumir que ese proceso existe o está activo sin comprobarlo.

## Instrucción para la cuenta nueva
Al retomar, lee los repositorios pertinentes, inspecciona el estado actual y confirma qué archivos y cambios existen antes de continuar. Actualiza este documento solo con resultados observados y marca la fecha de cada revisión.
## Operación autónoma y estado de automatizaciones (2026-10-31)

- **Operador autónomo general:** habilitado; horario actualizado a diario 08:00 America/Mexico_City desde 2026-11-01. La instrucción incluye auditoría de archivos Library, comparación byte a byte/SHA-256, diff de texto, clasificación reversible y reporte diario. Dot nativo sigue sin estar conectado; ver DOT_EQUIVALENTE_OPERATIVO.md.
- **Agente de investigación CAPCOT:** habilitado; ejecución del 2026-10-31 completada. Entregables verificados en la rama `feature/capcot-video-discovery-continuity`: brief, storyboard de pardelas y registro de fuentes. El storyboard tiene 8 escenas, 218 palabras, 84 segundos, cuatro arcos narrativos y cero referencias de fuente rotas. No generó video ni publicó.
- **Tercera cápsula CAPCOT:** habilitada; última ejecución registrada del 2026-10-30 completada. La siguiente ejecución diaria está programada a las 15:00; no se duplicó desde este operador.
- **Datos CAPCOT:** `data/temas_del_dia.json` y `data/rotacion.json` contienen fechas hasta 2026-10-28; `data/publicaciones.json` llega hasta 2026-10-27 (no 2026-10-26 como indicaba el resumen del agente). No se modificaron `data/*.json`.
- **Library:** revisión de los 100 elementos más recientes del directorio raíz, con contenido/metadata profundizados para los grupos identificables. El elemento más antiguo de esa página fue creado el 2026-10-20 01:39:55 UTC; queda backlog más antiguo por revisar. El archivo más reciente visible fue creado el 2026-10-28 21:31:56 UTC. El montaje Dropbox existe, pero `/Dropbox` devolvió cero elementos; el listado recursivo de Dropbox no está soportado por la herramienta.
- **Clasificación:** se movieron de forma reversible 69 archivos a carpetas de CAPCOT, motor U6, reportes, configuración ChatGPT y evidencias de GitHub. Se crearon subcarpetas fechadas. No se alteró el contenido de los archivos ni los motores canónicos.
- **Duplicados exactos:** se verificaron 10 grupos con SHA-256 y comparación binaria; se trasladaron 13 copias redundantes a `/MOTOR_TRASH/02_DUPLICADOS/EXACTOS_2026-10-31`. No se borró ningún archivo. Detalle en `reportes/2026-10-31_OPERACION_AUTONOMA.md`.

- **U6 / recibo de reejecución 2026-10-26:** la huella de mortalidad ausente es esperada porque el paquete de preparación solo contiene un manifiesto y una plantilla vacía. Se preparó y probó en copia temporal un diff candidato para que el runner emita `continuidad_corrida.status=NO_PAUSA_REQUERIDA` cuando la compuerta no solicita reanudación. Suite: 101 passed, 2 skipped, 0 failed. No aplicado al paquete ni al motor; detalle en `reportes/2026-10-31_OPERACION_AUTONOMA.md`.
