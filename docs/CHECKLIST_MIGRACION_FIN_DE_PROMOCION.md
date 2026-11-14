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

## Corte de aceptación — 2026-11-11

### Evidencia de segunda sesión
- [x] Existe un acuse separado de sesión Claude en `bandeja/resueltos/2026-11-10_SEGUNDA_SESION_RECUPERACION.md`.
- [ ] No satisface la aceptación completa: revisó Motor U6 y orquestador-central, pero CAPCOT no quedó confirmado; cuenta GitHub y dudas esenciales siguen `PENDIENTE`.
- [ ] El acuse de la segunda sesión/modelo en el archivo requerido `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` sigue ausente.
- [ ] La migración permanece INCOMPLETA.

### Autoridad y conexiones
- [x] Contrato de U6 actualizado: `alterno/cameo-pesos` rama vigente; `main` SOLO_CONSULTA.
- [x] GitHub `marcojpad-hash` consultado: 11 repositorios visibles; cuenta `marcosabines-hash` sin instalaciones/repositorios visibles.
- [x] codebase-memory-mcp documentado/configurado en U6/alterno; binario y rutas locales, índice de 7-nov desde main, proceso vivo/reindexación activa no verificados.
- [ ] codebase-memory-mcp en CAPCOT/feature: no hay configuración.
- [ ] DeepSeek Harness en U6/alterno y CAPCOT/feature: no hay configuración; no existe conexión ejecutable en esta sesión.
- [ ] Prueba gratuita DSH de extremo a extremo: Groq falló HTTP 429; Ollama pendiente.

### CAPCOT handoff
- [x] Leído `docs/GROK_STATUS_CONTRACT.md`.
- [ ] Estado Grok del último storyboard 10-nov DNA: ausente; `RECEPCION_GROK_NO_CONFIRMADA`.
- [ ] Estado Grok del robot 9-nov: ausente; paquete anidado.
- [ ] Clavo 7-nov: sin narrative_qa; sigue en entrada anidada, pendiente de auditor.
- [ ] Corregir dispatch: workflow solo escucha `cola/entrada/*.json`, aunque el procesador recorre anidados.
- [ ] Slot 23:30: excluido por el prompt del investigador; sin paquete en horario 11-nov.
- [x] No se creó ni modificó ningún archivo de estado de Grok, no se promovió ni se generó medio.

### Motor U6 / Schrödinger
- [x] Hashes canónicos recalculados y coincidentes en `alterno/cameo-pesos`.
- [x] Informe de revisión documental creado; sin cambios de código/SPEC/Engine/patrones.
- [ ] Aprobación de V0_1/V0_2: pendiente de corregir ceros, ponderación de masa, vacíos, convergencia, pruebas y evidencia reproducible.
- [ ] Tests Schrödinger integrados al runner/CI y ejecutados en la rama activa.



## Actualización verificada — 2026-11-12

- [x] Reconsultadas las dos cuentas GitHub: marcojpad-hash = 1 instalación y 11 repositorios; marcosabines-hash = 0 instalaciones/repositorios, sin error.
- [x] Reconfirmada autoridad de ramas: CAPCOT feature/capcot-video-discovery-continuity; Motor U6 alterno/cameo-pesos (main SOLO_CONSULTA); ChatGPT-migracion main.
- [x] Consultados estados de automatizaciones: investigador y operador IN_PROGRESS sin completed_at; auditor COMPLETED 11-nov antes de la incorporación posterior de ratas topo.
- [ ] CAPCOT: revisar narrativamente y estructuralmente el paquete ratas topo 11-nov en conversación independiente; no promover ni atribuir recepción. Falta cola/estado individual y el workflow no procesa la ruta anidada.
- [ ] CAPCOT: reconciliar el ID de video knAElNo4raI (220 vistas en endscreens) con data/publicaciones.json, data/rotacion.json y evidencia de plataforma.
- [ ] Resolver la contradicción del slot 23:30 entre instrucción permanente y prompt investigador; no generar duplicados.
- [ ] U6: revalidar F003/F004. LECTURA.json tiene cuatro hashes que no coinciden con los documentos actuales; REVISION.md reporta dos rutas ausentes en 20 recibos y falta tabla de mortalidad. El candado no se ejecutó.
- [ ] U6: actualizar la sección §6 obsoleta de CONTRATO_GUARDAR_CORRIDAS.md, que todavía dice que tres documentos siguen pendientes aunque ya fueron actualizados.
- [ ] Migración: el handoff requerido bandeja/2026-11-03_RECUPERACION_MIGRACION.md sigue PENDIENTE; no hay acuse de segunda sesión/modelo que complete CAPCOT y conectores.
- [ ] Verificar proceso codebase-memory-mcp vivo y reindexación en la rama exacta; no hay conector vivo expuesto en esta sesión. DeepSeek Harness no está probado de extremo a extremo.

La migración permanece INCOMPLETA.


## Actualización verificada — 2026-11-13

### Comprobaciones y correcciones ejecutadas
- [x] Reconsultadas las cuentas GitHub: `marcojpad-hash` = 11 repositorios; `marcosabines-hash` = 0 instalaciones/repositorios. Ocho adicionales clasificados DESCUBIERTO_ADICIONAL y revisados solo en metadatos/README; sin escrituras.
- [x] Corregido el prompt del investigador CAPCOT: el slot 23:30 `dato_del_dia` ya no está excluido globalmente; se exige fuente del mismo día CDMX, dentro de 48 h, slot libre y storyboard independiente. El run del 13-nov comenzó antes del cambio; la primera ejecución con el prompt nuevo sigue pendiente.
- [x] Releídos los 20 recibos F003/F004: los campos cuestionados existen, pero ambos llevan `DATO_AUSENTE_REQUIERE_CLASIFICACION`; no se interpretan como verificación exitosa.
- [x] Reconciliados `CONTRATO_GUARDAR_CORRIDAS.md` §5–§6 y el README del lote; añadida corrección en `REVISION.md` y entrada en `avances/`.
- [x] Corregida la fila de autoridad de U6 en este protocolo: rama activa `alterno/cameo-pesos`, `main` SOLO_CONSULTA.

### Pendientes que siguen abiertos
- [ ] Renovar `motor/runs/F003_F004_20261111/LECTURA.json`: 3/4 SHA-256 no coinciden con documentos actuales; el hash del protocolo de ejecución sí coincide. No ejecutar el candado hasta renovar la evidencia por el procedimiento autorizado.
- [ ] Clasificar/resolver los dos valores sentinel de `consulta_dirigida`; no se ejecutó motor ni tests.
- [ ] Resolver ausencia de tabla de mortalidad y calibración predictiva; U6 continúa NO_CALIBRADO.
- [ ] CAPCOT 12-nov: DOI pendiente de resolvedor y estado Grok ausente; RECEPCION_GROK_NO_CONFIRMADA.
- [ ] CAPCOT 11-nov ratas topo: falta narrative_contract y QA narrativo independiente; estado Grok ausente; no redispatchar.
- [ ] Confirmar resultado terminal del investigador CAPCOT del 13-nov y verificar primera ejecución con la nueva regla 23:30.
- [ ] Auditor CAPCOT del 13-nov a las 15:00: pendiente al corte.
- [ ] Handoff original `bandeja/2026-11-03_RECUPERACION_MIGRACION.md`: sin acuse verificable de segunda sesión que cubra CAPCOT y conectores. Migración INCOMPLETA.
- [ ] Verificar proceso vivo y reindexación de codebase-memory-mcp en U6/alterno; CAPCOT/feature sin configuración. DeepSeek Harness sigue sin integración ejecutable en las ramas activas.
- [ ] Dot nativo no conectado ni verificado en esta sesión.

La migración permanece **INCOMPLETA**.

## Actualización verificada — 2026-11-14

- [x] Reconsultadas las dos cuentas GitHub: `marcojpad-hash` = 1 instalación de usuario y 11 repositorios; `marcosabines-hash` = 0 instalaciones y 0 repositorios, sin error.
- [x] Reconfirmadas las ramas: migración/main, CAPCOT/feature/capcot-video-discovery-continuity y U6/alterno/cameo-pesos (main SOLO_CONSULTA).
- [x] Revisados los estados de las tres automatizaciones: investigador y auditor completados el 13-nov; operador del 14-nov IN_PROGRESS sin completed_at. No atribuirle entrega.
- [ ] Handoff original 2026-11-03: sigue sin acuse verificable de segunda sesión; el acuse separado de Claude no cubre CAPCOT ni conectores. Migración INCOMPLETA.
- [ ] Verificar proceso codebase-memory-mcp vivo/reindexación de ramas activas; no hay servidor MCP expuesto en esta sesión.
- [ ] Integración ejecutable de DeepSeek Harness en CAPCOT/feature y U6/alterno: no confirmada.
- [ ] Confirmar conectores esenciales desde una segunda sesión/modelo. La cuenta GitHub y los permisos de esta sesión no prueban recuperación independiente.
- [ ] Dot nativo: no conectado ni expuesto en esta sesión.

Registro de evidencia: [reporte operativo 2026-11-14](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/reportes/2026-11-14_OPERACION_AUTONOMA.md).

### Reconsulta de automatizaciones — 2026-11-14

- [x] Reconsultado el estado terminal: investigador CAPCOT del 14-nov `0eef543a-9448-8324-a68e-a53655e07a92` sigue IN_PROGRESS sin completed_at; operador `31576c4e-c538-8328-b7ea-4220296c6695` también sigue IN_PROGRESS.
- [ ] No atribuir entregables a ninguno hasta que haya estado terminal y archivos verificados.
