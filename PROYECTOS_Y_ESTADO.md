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