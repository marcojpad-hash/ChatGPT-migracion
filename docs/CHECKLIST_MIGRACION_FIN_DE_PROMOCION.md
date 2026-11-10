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

## Actualización verificada — 2026-11-09

- [x] Reconsultadas ambas cuentas GitHub: `marcojpad-hash` devuelve nueve repositorios; `marcosabines-hash` devuelve cero, sin error.
- [x] Revisados metadatos/README de los seis repositorios `DESCUBIERTO_ADICIONAL`; sin escrituras.
- [x] Confirmada autoridad de ramas: U6 `main`; CAPCOT `feature/capcot-video-discovery-continuity`; migración `main`.
- [x] Confirmado que codebase-memory-mcp está documentado/configurado en U6/main y CAPCOT/main, pero ausente en CAPCOT/feature; los índices documentados son del 7-nov.
- [ ] Verificar proceso MCP vivo en la máquina/cliente que lo consume y reindexar U6/CAPCOT tras los cambios posteriores al 7-nov.
- [ ] Integrar codebase-memory-mcp en CAPCOT/feature mediante cambio autorizado; no copiar desde main mientras persista la divergencia.
- [ ] DeepSeek Harness: prueba de humo con Groq gratuito falla al segundo llamado por 429/8 000 TPM; Ollama no se probó. No declararlo agente gratuito de extremo a extremo.
- [ ] Handoff real de segunda sesión/modelo: `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` sigue `PENDIENTE`, sin acuse.
- [ ] Auditor CAPCOT del 9-nov: todavía no hay run del día en la última consulta; horario guardado 15:00 flexible y `next_run_time=null`.
- [ ] Reconciliar el slot CAPCOT 23:30 y su responsable: el horario del 9-nov lo deja sin paquete; el investigador de las 08:00 lo excluye. No crear un paquete duplicado desde el operador general.
- [ ] Investigar la causa de `next_run_time=null` en las tres automatizaciones; no interpretar null como deshabilitación ni como garantía de ejecución futura.

La migración continúa **INCOMPLETA**: falta el acuse verificable de otra sesión/modelo y la comprobación de conexión MCP viva.

## Actualización verificada — 2026-11-10

- [x] Reconsultadas ambas cuentas GitHub e instalaciones: marcojpad-hash devuelve 11 repositorios y una instalación visible (ID 174841554, selección all; nombre de App no expuesto); marcosabines-hash devuelve cero repositorios/instalaciones, sin error.
- [x] Ocho repositorios adicionales clasificados DESCUBIERTO_ADICIONAL; los dos nuevos repositorios microserie fueron revisados solo por README/metadatos y no recibieron escrituras.
- [x] Autoridad de ramas y HEAD actualizados: ChatGPT-migracion/main ff368057 previo al reporte, CAPCOT feature 91003f7c, Motor U6 main d4af4d7.
- [ ] Handoff real de segunda sesión/modelo: bandeja/2026-11-03_RECUPERACION_MIGRACION.md sigue PENDIENTE, sin acuse ni reporte de recuperación.
- [ ] Verificar proceso codebase-memory-mcp vivo en el cliente/máquina que lo consume; U6 conserva índice del 7-nov y CAPCOT/feature carece de configuración.
- [ ] DeepSeek Harness no está integrado en U6/main ni CAPCOT/feature; prueba Groq gratuita previa falló 429/8 000 TPM; Ollama no probado.
- [ ] Reconciliar el slot 23:30: instrucción permanente del dato del día exige paquete diario, pero el prompt del investigador lo excluye; 10-nov continúa sin paquete.
- [ ] Handoff Grok del paquete robot 9-nov: QA almacenado PASS 90, pero estado individual 404 y ruta anidada no despachable por el workflow actual.
- [ ] Revisar el resultado terminal de investigador y operador 10-nov; ambos seguían IN_PROGRESS al corte. Auditor 10-nov aún no había corrido.
- [ ] Resolver next_run_time=null en las tres automatizaciones; la causa no está identificada.
- [ ] Confirmar conexiones de una segunda sesión: el acceso de esta sesión no demuestra recuperación de permisos/conectores en otra.

La migración continúa **INCOMPLETA**.


## Actualización verificada — 2026-11-10, entrega de pendientes

- [x] ASTRA: guion textual separado en [GUION_NARRACION.md](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/main/cola/entrada/2026-11-09_dato-robot-ensambla-orbita/GUION_NARRACION.md). No se regeneraron PNGs. El estado conserva que los nueve frames fueron generados por Grok y están disponibles en el chat; no se afirma que estén subidos a `frames/`.
- [x] Dato 23:30 del 10-nov: paquete textual en CAPCOT/feature, proyecto `2026-11-10_dato-adn-sincroniza-flujo`; 8 escenas, 195 palabras, 84 s, seis campos obligatorios en cada escena y narrative_qa PASS 91/100. Queda en `proyectos/`; no se disparó workflow ni se creó estado Grok. La revisión estructural fue estática contra el validador; el script Python no se ejecutó por falta de runtime del repositorio.
- [ ] Handoff real de segunda sesión: reemitido en `bandeja/2026-11-10_SEGUNDA_SESION_RECUPERACION.md`; continúa PENDIENTE hasta que una sesión destinataria registre su acuse y reporte propios. Este archivo no es un acuse.
- [ ] Cierre de migración: sigue bloqueado por falta de prueba de recuperación independiente y de verificación de conectores en la sesión destinataria.

**Conclusión:** no declarar migración completa. El acceso de esta sesión emisora no demuestra que otra sesión haya recuperado contexto ni permisos.
