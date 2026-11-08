# Checklist de continuidad antes del fin de la promoción
Corte inicial: 2026-11-03. Objetivo: una sesión nueva debe poder continuar sin depender de este chat.

## Estado
- [x] Repositorio privado ChatGPT-migracion localizado y accesible.
- [x] README y documentos iniciales conservados.
- [x] Repositorios U6 y CAPCOT localizados con acceso GitHub.
- [x] Ramas de autoridad identificadas: U6 main; CAPCOT feature/capcot-video-discovery-continuity.
- [x] Restricciones canónicas U6 y compuertas CAPCOT recuperadas.
- [x] Mapa operativo de herramientas por proyecto creado.
- [x] Protocolo de memoria compartida entre modelos creado.
- [x] Plantilla de handoff y bandeja documentadas.
- [ ] Probar un handoff real entre dos modelos/cuentas y registrar acuse.
- [ ] Confirmar que la segunda sesión puede leer los tres repositorios con la cuenta GitHub correcta.
- [ ] Revalidar automatizaciones y resolver next_run_time null si persiste.
- [ ] Reconectar vidIQ con la cuenta que administra Datos y ociosidades; ahora devuelve cero canales para marcosabines@gmail.com.
- [ ] Confirmar cuenta/Brand Kit de Canva.
- [ ] Confirmar workspace, workflows y créditos de Runway.
- [ ] Confirmar si Dropbox es parte de continuidad o almacenamiento auxiliar.
- [ ] Decidir si se conecta instancia n8n; actualmente hay skill para JSON, no conector directo.
- [ ] Decidir si orquestador-central entra al alcance; por ahora solo lectura.

## Prueba de recuperación
Una sesión nueva debe poder:
1. Leer este repo y reconstruir reglas/estado.
2. Identificar U6 y CAPCOT como proyectos separados.
3. Encontrar ramas correctas y documentos de arranque.
4. Explicar qué puede ejecutar con las conexiones disponibles.
5. Localizar último reporte, commit y pendientes de cada proyecto.
6. No tocar archivos canónicos, duplicar cápsulas ni atribuir ejecuciones no verificadas.
7. Guardar un reporte de recuperación con evidencia y conectores que requieran reconexión.

## Conexiones observadas el 2026-11-03
| Servicio | Resultado | Acción |
|---|---|---|
| GitHub marcojpad-hash | Acceso a ChatGPT-migracion, motor-u6-storage, capcot-capsulas-imaginantes y orquestador-central. | Reautorizar si no aparece en nueva sesión. |
| GitHub marcosabines-hash | Sin instalaciones/repositorios devueltos. | No usar como cuenta de trabajo hasta corregir. |
| vidIQ | marcosabines@gmail.com; cero canales. | Reconectar cuenta correcta y verificar canal. |
| Dropbox | marco.jp@live.com.mx. | Confirmar que es la cuenta deseada. |
| Notion | Workspace disponible; usuario owner de un teamspace. | Contexto auxiliar; GitHub prevalece. |
| Floot | Cero proyectos. | No hay runner/app configurado. |
| Canva | Cero Brand Kits. | Confirmar cuenta y kit. |
| Runway | Cero workflows guardados. | Confirmar workspace, créditos y recursos antes de gastar. |
| Undermind | Cero workspaces. | Crear solo si sirve a investigación concreta. |
| n8n | Skill disponible; conector directo no localizado. | Conectar instancia para importar/ejecutar remotamente. |

## Criterio de cierre
La migración está lista cuando una sesión nueva reconstruye el estado y continúa ambos proyectos desde GitHub y se comprueban las conexiones esenciales. Documentación no prueba transferencia de permisos ni ejecución de automatizaciones.

## Actualización — 2026-11-07

- [x] Verificado que Contents:write funcionó en `motor-u6-storage`: A5 desde `a5-cableado-20261107` llegó a PR #2 y quedó fusionado.
- [ ] Confirmar Contents:write de Muse en `capcot-capsulas-imaginantes`; no hay rama A5 ni PR verificable.
- [ ] Resolver permiso `Workflows` de Muse o una vía autorizada para actualizar `.github/workflows/test-motor-contracts.yml`; los tres tests nuevos de A5 aún no forman parte del CI.
- [ ] Completar handoff real de segunda sesión/modelo: `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` sigue PENDIENTE y no tiene acuse.
- [ ] Confirmar que una segunda sesión puede leer los tres repositorios principales. El acceso de esta sesión no prueba el de otra.
- Nota: la instalación GitHub ID `174841554` devuelve selección `all`, pero su nombre de App no se expone; no atribuirla a Muse sin evidencia adicional.


## Actualización verificada — 2026-11-08

- [x] Gate de memoria compartida anclado y verificado en `AGENTS.md` y `README.md` de los nueve repositorios visibles.
- [x] Cuentas e inventario GitHub reconsultados: `marcojpad-hash` devuelve nueve repositorios; `marcosabines-hash` devuelve cero instalaciones/repositorios.
- [x] Acceso de esta sesión a las tres fuentes principales y sus ramas de autoridad comprobado.
- [ ] Handoff real de segunda sesión/modelo: `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` continúa `PENDIENTE`, sin acuse. No declarar migración completa.
- [ ] Verificar la conexión MCP viva desde otra sesión/cliente. U6 tiene `.mcp.json` y documentación; CAPCOT solo tiene esa configuración en `main`, no en la rama activa `feature/capcot-video-discovery-continuity`. La sesión actual no expone la herramienta MCP.
- [ ] Reindexar codebase-memory-mcp después de cambios posteriores al snapshot del 7-nov y verificar la rama exacta indexada de CAPCOT.
- [ ] DeepSeek Harness no completó la prueba de humo con Groq gratuito: segundo llamado 429 por 8 000 TPM. No contar DSH como agente de código funcional de punta a punta a costo cero.
- [ ] Reconciliar `main` y `feature/capcot-video-discovery-continuity`: comparación `diverged`, feature 650 commits adelante y 103 detrás. No fusionar sin decisión del propietario.
- [ ] Reconciliar el tablero `ajustes_entre_modelos/DELEGACIONES.md` de CAPCOT/main con la rama activa, donde ese archivo no existe.
- [ ] Resolver el estado del paquete `2026-11-07_dato-clavo-te-cocina`: no tiene QA narrativo ni estado Grok; existe un registro de programación contradictorio con `ESTADO_EJECUCION.md`.
- [ ] Revalidar el estado terminal de los runs de investigador y operador del 8-nov; ambos estaban `in_progress` al corte.
