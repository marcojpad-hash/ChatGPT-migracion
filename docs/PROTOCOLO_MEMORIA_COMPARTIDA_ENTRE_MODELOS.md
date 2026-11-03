# Protocolo de memoria compartida y trabajo entre modelos
Versión 1.0 — 2026-11-03

## 1. Qué es GitHub
GitHub es la memoria operativa persistente y el espacio común de trabajo: conserva instrucciones, decisiones, datos versionados, código, pruebas, reportes, fuentes, entregables e historial de cambios. No es una copia literal de conversaciones ni sustituye las capacidades propias de cada modelo.

La continuidad no depende de que ChatGPT conserve el historial, créditos o sesión abierta. Depende de que cada agente lea y actualice los repositorios autorizados.

## 2. Autoridad de repositorios
| Repositorio | Función | Autoridad |
|---|---|---|
| ChatGPT-migracion / main | Continuidad transversal, reglas, mapa de herramientas y handoffs. | Contexto operativo común, no código de proyecto. |
| motor-u6-storage / main | Motor U6, contratos, casos, pruebas, hashes, recibos y resultados. | Fuente de verdad exclusiva de U6. |
| capcot-capsulas-imaginantes / feature/capcot-video-discovery-continuity | Línea editorial, investigación, storyboards, cola, producción, QA y publicación. | Fuente de verdad de CAPCOT en la rama vigente. |
| orquestador-central | Prototipo adicional. | Fuera de alcance de escritura hasta autorización expresa; no está desplegado. |

No duplicar código ni entregables de proyecto en el repo de migración. Guardar allí enlaces, decisiones, estado y hashes.

## 3. Arranque para cualquier modelo/sesión
1. Leer README.md, CONTINUIDAD_CHATGPT.md, ESTILO_DE_TRABAJO.md y PROYECTOS_Y_ESTADO.md.
2. Leer docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md y este protocolo.
3. Para U6, abrir FEEDME_ACTUALIZADO.md y seguir el orden de arranque y el protocolo de ejecución/lectura del repositorio.
4. Para CAPCOT, leer Plan Maestro, Receta, Guía externa, flujo y contrato de cola en la rama vigente; revisar fecha y slot antes de producir.
5. Verificar el estado actual en GitHub; los cortes históricos no sustituyen una lectura actual.
6. Confirmar cuenta y permisos disponibles. No asumir que una nueva sesión hereda conexiones anteriores.

## 4. Colaboración sin pisarse
- Leer antes de escribir.
- Usar repositorio y rama autorizados.
- Preservar IDs, hashes, historial y archivos canónicos.
- No reescribir silenciosamente trabajo de otro modelo.
- Releer desde GitHub después de escribir.
- Registrar commit, rutas, pruebas y estado.
- Antes de editar: recuperar SHA actual. Si cambió, recuperar contenido nuevo y reconciliar; nunca forzar una escritura con versión obsoleta.
- Si dos agentes modifican el mismo archivo, detener la escritura y resolver el diff explícitamente.

## 5. Bandeja entre modelos
La bandeja es un protocolo de archivos, no mensajería instantánea. Un modelo deja un handoff; el destinatario debe leerlo y confirmar recepción/ejecución.

Estructura:
- bandeja/pendientes/<fecha>_<id>_<origen>_a_<destino>.md
- bandeja/recibidos/<fecha>_<id>_<modelo>.md
- bandeja/cerrados/<fecha>_<id>.md

Cada handoff incluye ID, proyecto, repo/branch, emisor/destinatario, objetivo, restricciones, fuentes/commits, entregable esperado, pruebas y estado.

Estados: PENDIENTE, RECIBIDO, EN_PROCESO, ENTREGADO, VERIFICADO, BLOQUEADO.

Un archivo creado no demuestra que el destinatario lo leyó. No marcar RECIBIDO sin acuse, ENTREGADO sin artefactos guardados ni VERIFICADO sin leerlos/probarlos.

## 6. Qué compartir
Compartir: instrucciones, contratos, decisiones, código, esquemas, datasets autorizados, resultados reproducibles, storyboards, fuentes, informes, hashes y handoffs.

No compartir: contraseñas, API keys, OAuth tokens, cookies, secretos, .env, datos privados innecesarios ni medios pesados cuando el contrato indique almacenamiento externo. Las credenciales se configuran en el servicio (por ejemplo GitHub Secrets o n8n Credentials), nunca en prompts, JSON, código fuente o handoffs.

## 7. Capacidad y límite de comunicación
GitHub permite que modelos con acceso autorizado lean y escriban en el mismo repositorio, con historial versionado. No despierta a otro modelo, no garantiza que lea un archivo, no crea comunicación en tiempo real y no ejecuta automáticamente el trabajo delegado.

La coordinación requiere emisor, mecanismo de notificación/revisión, destinatario con permisos, acuse observable y verificación de entregable. GitHub Actions ejecuta CI definido en el repositorio; Automations ejecuta tareas programadas dentro de sus límites. Ninguno equivale por sí mismo a un modelo permanentemente activo.

## 8. Cierre de sesión
- Guardar trabajo en el repositorio especializado.
- Releer archivos modificados.
- Registrar commit, hashes, pruebas, estado y bloqueos.
- Actualizar continuidad/estado solo con resumen y enlaces.
- Dejar handoff si otro modelo debe continuar.
- No depender de que el próximo modelo vea el chat actual.

## 9. Meta de migración
Antes de que termine la promoción durante noviembre de 2026, verificar que una sesión nueva puede reconstruir estado y continuar ambos proyectos, que los permisos GitHub están disponibles, que existe al menos un handoff probado y que las conexiones que requieren reautenticación están documentadas. No declarar migración completa solo porque los documentos estén escritos.