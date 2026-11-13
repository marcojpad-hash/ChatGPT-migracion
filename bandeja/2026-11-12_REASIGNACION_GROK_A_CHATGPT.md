# REASIGNACIÓN — De Grok a ChatGPT (decisión de Marco, 2026-11-12 ~13:44 CST)

- **De:** Pecas, por decisión de Marco
- **Para:** ChatGPT
- **Fecha:** 2026-11-12
- **Contexto:** Grok reportó hoy 09:27 CST que revisó ESTADO.md y bus/ y que no hay tareas simples cerrables sin riesgo; no tocó nada (sin Engine, catálogo 244, claves, rama ni PR). Marco decide reasignar sus órdenes pendientes a ChatGPT.

## Órdenes reasignadas (repo marcojpad-hash/agente-cero-costo, salvo que se diga otro)

- **Issue #63 (orden maestra):** #36 (PR #62 supervisor-reutilizable.yml: falta guardia agnóstico, guardia.config.json estricto, 5 estados, compuerta, salida de checks y tests), #37 Cancerbero, #38 casos semejantes y A/B Napoleón/Mozart, #47–#49 calibración Z90 y guardián de la Z (motor-u6-storage, rama alterno/cameo-pesos), #50 consulta LLM obligatoria del Caldero.
- **Issue #64:** cerrar punto 2 de la auditoría de trazabilidad — guardián Z90 en correr_estandar + previo_error Mozart (motor-u6-storage, alterno/cameo-pesos). No tocar Engine_V5_CANONICO_SOLO.py ni patterns_final_v14.json (244).
- **Issues #161 y #164:** paquete 2026-11-09_dato-robot-ensambla-orbita sin frames — convertir PNG a JPEG calidad 85 y subir en lotes menores a 10 MiB (cada archivo menor a 5 MiB), o indicar en ESTADO_EJECUCION.md dónde están (COORDINACION §3).
- **Handoff bandeja/2026-11-03_RECUPERACION_MIGRACION.md:** prueba de recuperación de sesión con GitHub como fuente de verdad (criterios de aceptación en el archivo).

## No reasignado

- **bandeja/2026-10-26_claude_entra_al_repo.md:** va para Claude, no para ChatGPT. Sigue pendiente de Claude.
- **PRs de orquestador-central (#1, #3, #4 y otros) sin merge:** el merge lo decide Marco, no se reasigna.

## Criterios de aceptación (los del bus)

- Un PR por orden (o por grupo), con evidencia y tests en verde; sin placeholders ni SyntaxError.
- Responder con un Issue "[BUS] hecho - ChatGPT" o el PR. No hacer merge sin que lo pidan.
- Fecha límite blanda: créditos de ChatGPT caducan ~24-nov-2026 (fecha aproximada, no verificada).

## Acuse

**Fecha:** 2026-11-13  
**Cuenta GitHub:** `marcojpad-hash`  
**Qué tomé primero:** Issue #64 (U6). Revisé el PR #8 existente en lugar de duplicarlo; corregí el código de salida del guardián Z90 a 8 y los campos `previo_error`/`visto_error` a `False` cuando no hay error. GitHub Actions `runner-contract` terminó SUCCESS. Dejé el acuse en el issue. PR #8 permanece abierto y sin merge.

Después atendí la alternativa de ubicación de #161/#164: el registro existente indica que los nueve PNG ASTRA se generaron en la conversación de Grok.com del 9-nov-2026. Verifiqué que no están en GitHub (`frames/` solo contiene `.gitkeep`); actualicé `ESTADO_EJECUCION.md` en CAPCOT y abrí PR #4. La conversión y subida no se declaran hechas. Dejé comentarios en ambos issues.

También abrí PR #9 en U6 con erratas de F003/F004: corrige el recuento de grados, distingue marcadores de datos no clasificados de claves físicamente ausentes y documenta discrepancias entre tabla, manifiesto y recibos. No ejecuté el candado ni declaré aceptada la entrega.

**Pendiente principal:** #36 (PR #62 es solo una plantilla parcial, sin wrappers ni compuerta de fallo), #37, #38 y #47–#50. No hice merge de ningún PR ni toqué los motores canónicos o el catálogo 244.
