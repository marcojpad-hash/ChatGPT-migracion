# Proyectos y estado — corte 2026-10-31

## Fuente de verdad por proyecto

| Proyecto | Repositorio / ubicación | Estado actual | Pendientes reales |
|---|---|---|---|
| CAPCOT / Datos y ociosidades | capcot-capsulas-imaginantes, rama feature/capcot-video-discovery-continuity | Radar y storyboard diario; plantilla/validador/rotación/handoff corregidos; Grok conserva producción, QA y publicación. | Grok debe adoptar cola/estado/ para confirmar recepción; analítica privada Meta/YouTube/TikTok no conectada. |
| Motor U6 / V15.3 | motor-u6-storage, main | F006 R7 recuperado y registrado; mapa de versiones actualizado; 4 casos ciegos históricos migrados pre-Z; Engine V5 y 244 patrones protegidos. | Miss de destino en Courbet; F006 es reevaluación, no caso nuevo; lote de 20 corridas ciegas independientes aún no existe como paquete. |
| Migración ChatGPT | ChatGPT-migracion, main | Documentación de continuidad, autonomía, coordinación y auditoría transversal. | Mantener registro actualizado de automatizaciones y proyectos. |
| Notion operativo Motor | Workspace Notion | Páginas de septiembre conservadas como archivo histórico. | Workspace alcanzó límite de bloques gratuitos; no se pudieron actualizar ni crear avisos. GitHub prevalece. |
| Analítica social | Conector Windsor.ai sugerido | Sugerencia enviada; no instalado ni conectado. | Requiere que el usuario conecte la aplicación y autorice las fuentes. |

## CAPCOT — correcciones aplicadas

- Catálogo visual sincronizado: 50 estilos canónicos en scripts/estilos.json y 50 entradas en docs/ESTILOS_VISUALES.md.
- Plantilla y validador actualizados a 9:16, 75–90 s, 170–235 palabras, 7–9 escenas, voz y cierre exactos.
- Se retiraron nombres de assets inexistentes y privacidad pública del storyboard textual.
- Se agregó registro editorial de solo lectura que reconcilia data/, cola/, proyectos/ y salidas/.
- La cola ahora filtra por fecha y no consume entradas antiguas.
- Los nombres de assets se asignan solo en la etapa de producción.
- La antigua automatización de tercera cápsula se convirtió en auditor de cola/rotación.
- Se agregó contrato de estado de Grok. Sin archivo cola/estado, la recepción no está confirmada.
- No se modificó data/*.json, main ni se generaron medios.

## Motor U6 — correcciones aplicadas

- Se recuperó el artifact F006 R7 y se persistieron resumen, compromiso, evaluación, registro y hashes.
- Se añadió F006 a resultados.jsonl como reevaluación del mismo caso Courbet.
- No se infló la muestra de calibración ni se modificó el CSV acumulado.
- Se creó mapa de versiones para distinguir Engine V5 canónico, runner V15.3, harness U6 y herramienta U7.
- Se aclaró la regla de unidades numéricas para no confundir soporte relativo con probabilidad.
- Se migraron entradas pre-Z y freezes de B-01, N-02, C-03 y H-01 desde Notion, sin copiar identidades ni desenlaces.
- Se creó plantilla y plan de 20 casos ciegos independientes; no se inventaron entradas.
- Se abrió el problema de destino personal: auge predicho frente a ruptura real. No se ajustó el motor.

## Automatizaciones activas

| Automatización | Horario CDMX | Función |
|---|---:|---|
| Operador autónomo general | 07:00 | Revisión transversal de repositorios, pendientes y continuidad. |
| Agente de investigación CAPCOT | 08:00 | Radar científico y storyboard textual. |
| Auditor CAPCOT — cola y rotación | 15:00 | Validación del handoff, rotación y estado Grok. |

Consultar cada ejecución antes de atribuirle trabajo. Un estado en progreso no es una tarea completada. El operador general del 31-oct seguía en progreso al corte; no se afirma que haya terminado.

## Dot

Dot nativo no está disponible para el plan Go según la documentación oficial revisada. El operador diario es un sustituto parcial, no un agente persistente 24/7 ni una computadora autónoma. No existe conexión directa confirmada con Dot.

## Proyectos sin repositorio confirmado

La búsqueda actual en los repositorios conectados y Notion no encontró un espacio verificable para Cangrejitos. No se creó un repositorio improvisado ni se mezcló el material con Motor o CAPCOT. Si reaparece documentación fuente, se archivará en su propio proyecto.

## Regla de estado

Cada hecho debe marcarse como verificado, ejecutado, inferido o pendiente. Un prompt actualizado no prueba que el bot haya ejecutado; un archivo en cola no prueba recepción; un artifact no equivale a un registro versionado hasta que se incorpore al repositorio.
