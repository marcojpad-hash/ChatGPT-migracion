# Aviso / handoff entre modelos

- **ID único:** CHATGPT-RECUPERACION-2026-11-11
- **De:** ChatGPT (sesión GPT-6)
- **Para:** Mj y siguiente sesión/modelo que audite la recuperación
- **Fecha (CDMX):** 2026-11-11
- **Urgente:** sí
- **Proyecto:** continuidad — Motor U6 y CAPCOT
- **Repositorio y rama:** marcojpad-hash/ChatGPT-migracion / main
- **Estado:** RECIBIDO por esta sesión; migración global INCOMPLETA

## Qué necesito

Registrar el acuse de lectura y recuperación independiente de esta sesión, dejar referencias verificables a un pendiente actual de Motor U6 y otro de CAPCOT, y permitir que un modelo posterior audite el resultado sin depender de este chat.

## Contexto y decisiones vigentes

- Memoria compartida leída antes de los repositorios: protocolo obligatorio, índice y hechos pertinentes.
- Continuidad: [ChatGPT-migracion](https://github.com/marcojpad-hash/ChatGPT-migracion), rama `main`.
- Motor U6: [motor-u6-storage](https://github.com/marcojpad-hash/motor-u6-storage), rama autorizada `alterno/cameo-pesos`; `main` es SOLO_CONSULTA.
- CAPCOT: [capcot-capsulas-imaginantes](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes), rama `feature/capcot-video-discovery-continuity`.
- Preservar motores/catálogos canónicos, datos operativos CAPCOT, workflows, secretos, permisos y publicaciones. No crear estados Grok ni declarar QA audiovisual.

## Alcance y restricciones

No se modificaron los repositorios especializados ni sus archivos operativos. No hubo ejecuciones locales ni Actions. Cualquier decisión que altere el uso de pesos CAMEO o los slots de publicación requiere la autoridad prevista en sus contratos; no se infiere autorización de la mera existencia de un commit.

## Fuentes y artefactos

- [Reporte completo de recuperación](../reportes/2026-11-11_RECUPERACION_CHATGPT.md) — se añadirá/confirmará con el commit del reporte.
- [Contrato U6 — rama vigente](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/CONTRATO_OPERATIVO_RAMA_VIGENTE.md).
- [Informe CAMEO U6](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/informes/2026-11-11_cameo-alterno.md).
- [Radar CAPCOT 11-nov](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-11_RADAR_CAPCOT.md).
- [Horario CAPCOT 11-nov](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/data/horario_2026-11-11.json).
- Handoff original del 3-nov, que permanece sin modificar: [bandeja/2026-11-03_RECUPERACION_MIGRACION.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/bandeja/2026-11-03_RECUPERACION_MIGRACION.md).

## Criterios de aceptación

- [x] Acuse de lectura de esta sesión y fecha registrados.
- [x] Acceso GitHub de lectura comprobado a los tres repositorios/ramas autorizados.
- [x] Autoridad de ramas diferenciada; U6 main no se usa.
- [x] Pendiente vigente de U6 identificado con evidencia.
- [x] Pendiente vigente de CAPCOT identificado con evidencia.
- [x] Límites reales de conectores y ejecución declarados.
- [x] Reporte de recuperación enlazado.
- [ ] Una segunda sesión/cuenta independiente verifica el acuse, reconstruye el estado y registra su propia aceptación.
- [ ] MCP vivo/reindexación y pruebas de ejecución real quedan verificados.

## Acuse del destinatario

- **Fecha:** 2026-11-11
- **Estado:** RECIBIDO
- **Confirmación de lectura:** ChatGPT (sesión GPT-6) leyó los ocho documentos de arranque en el orden indicado, la plantilla, el gate de memoria y los documentos de inicio/contrato de U6 y CAPCOT en las ramas especificadas. Reporte con hashes, enlaces y pendientes: [reportes/2026-11-11_RECUPERACION_CHATGPT.md](../reportes/2026-11-11_RECUPERACION_CHATGPT.md).
- **Dudas esenciales:** ninguna para registrar esta recuperación. La conexión de los pesos CAMEO a `cameo_activity` y la programación pendiente de TikTok/Facebook para el paquete de arroz quedan documentadas. La programación/publicación de esos canales corresponde a Imaginantes; esta sesión no ha ejecutado esas acciones.

## Resolución

Lectura y diagnóstico documentados. No se ejecutaron scripts ni workflows. No se hicieron cambios en U6 o CAPCOT. Acuse y reporte se guardan únicamente en el repositorio de migración. La migración global queda INCOMPLETA hasta auditoría independiente y verificación de runtime/MCP.

## Verificación del emisor/auditor

- **Resultado:** ENTREGADO; aceptación independiente pendiente.
- **Evidencia:** commits de este acuse y reporte; ambos archivos serán releídos desde GitHub tras la escritura.
- **Fecha:** 2026-11-11

Al verificarse, mover este aviso a bandeja/resueltos/. No marcar recibido ni verificado sin evidencia.
