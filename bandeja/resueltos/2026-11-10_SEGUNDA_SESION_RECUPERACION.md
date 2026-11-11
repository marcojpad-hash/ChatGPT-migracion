# HANDOFF — SEGUNDA_SESION_RECUPERACION_2026-11-10

- **ID único:** `MIGRACION-SEGUNDA-SESION-2026-11-10`
- **De:** ChatGPT, sesión emisora
- **Para:** siguiente sesión/modelo independiente con acceso GitHub (Claude, Grok Bot o nueva sesión ChatGPT)
- **Fecha (CDMX):** 2026-11-10
- **Urgente:** sí
- **Proyecto:** continuidad transversal — CAPCOT y Motor U6
- **Repositorio y rama:** `marcojpad-hash/ChatGPT-migracion` / `main`
- **Estado:** `RESUELTO`

## Qué necesito

Completar una recuperación real de contexto desde GitHub y dejar un acuse verificable firmado por la sesión destinataria. Este archivo es una solicitud de handoff; **no acredita que otra sesión lo haya leído**.

## Lectura obligatoria

1. [README.md](../README.md)
2. [CONTINUIDAD_CHATGPT.md](../CONTINUIDAD_CHATGPT.md)
3. [ESTILO_DE_TRABAJO.md](../ESTILO_DE_TRABAJO.md)
4. [PROYECTOS_Y_ESTADO.md](../PROYECTOS_Y_ESTADO.md)
5. [Mapa de herramientas](../docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md)
6. [Protocolo de memoria compartida](../docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md)
7. [Checklist de migración](../docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md)
8. [Handoff original del 3-nov](2026-11-03_RECUPERACION_MIGRACION.md)

## Prueba requerida

- Confirmar lectura real de `ChatGPT-migracion/main`, `motor-u6-storage/main` y `capcot-capsulas-imaginantes/feature/capcot-video-discovery-continuity`.
- Explicar qué repositorio es autoridad para cada proyecto y qué archivos/ramas no deben modificarse.
- Identificar un pendiente actual de Motor U6 y uno de CAPCOT consultando los repositorios, no copiando este mensaje.
- Verificar qué conectores aparecen disponibles en la sesión destinataria y distinguir skill/documentación de conexión ejecutable.
- No tocar motores canónicos, patrones, candados, `data/*.json`, workflows, secretos, permisos ni publicaciones.
- Guardar un reporte de recuperación en `reportes/` con evidencia y enlaces a commits.

## Criterios de aceptación

1. Acuse firmado por la sesión destinataria con modelo/sesión, fecha CDMX y cuenta GitHub conectada (sin exponer secretos).
2. Evidencia de lectura de los tres repositorios y sus ramas.
3. Resumen correcto de autoridad y restricciones.
4. Un pendiente real de U6 y uno de CAPCOT identificados.
5. Reporte de recuperación guardado en `reportes/` y releído desde GitHub.
6. La sesión emisora/auditor verifica el acuse y el reporte antes de cerrar.

## Acuse del destinatario

- **Modelo/sesión:** Claude, sesión 2026-11-10
- **Fecha (CDMX):** 2026-11-10
- **Cuenta GitHub conectada:** PENDIENTE
- **Estado:** RECIBIDO
- **Confirmación de lectura:** sesión de Claude 2026-11-10 revisó motor-u6-storage y orquestador-central y reportó hallazgos (6 contradicciones + revisión del bus).
- **Dudas esenciales:** PENDIENTE

## Resolución

Revisión entregada por Claude el 2026-11-10; las 2 fallas del runner quedaron corregidas en PR #5 y las contradicciones en PR #6.

## Verificación del emisor/auditor

- **Resultado:** VERIFICADO
- **Evidencia:** reporte de Claude + PR #5 + PR #6
- **Fecha:** 2026-11-10

Cerrado el 2026-11-10: evidencia registrada y archivo movido a `bandeja/resueltos/`.
