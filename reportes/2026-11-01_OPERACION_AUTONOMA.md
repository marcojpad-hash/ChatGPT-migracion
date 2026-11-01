# Operación autónoma — 2026-11-01

## Alcance y fuentes consultadas

Se leyeron primero en `ChatGPT-migracion/main`:
- `CONTINUIDAD_CHATGPT.md`
- `ESTILO_DE_TRABAJO.md`
- `BOT_DOT_AUTONOMIA.md`
- `PROYECTOS_Y_ESTADO.md`
- `reportes/2026-10-31_AUDITORIA_IMPLEMENTACION.md`, incluido su contenido adicional hasta el corte del 1-nov.

También se consultaron los historiales de las tres automatizaciones, el contrato Grok, la cola y el workflow CAPCOT, y los documentos de custodia y plan ciego de Motor U6.

## 1. Descubrimiento de cuentas y repositorios

Comprobación de las dos conexiones GitHub disponibles:
- La cuenta conectada `marcojpad-hash` devolvió cuatro repositorios: `ChatGPT-migracion`, `capcot-capsulas-imaginantes`, `motor-u6-storage` y `orquestador-central`.
- La segunda conexión GitHub no devolvió instalaciones ni repositorios.

`orquestador-central` es un repositorio privado adicional verificado, creado el 31-oct. No se declaró inexistente ni se escribió en él. Se clasificó como DESCUBIERTO_ADICIONAL porque no estaba entre los tres repositorios principales expresamente definidos para cambios en este mandato.

## 2. Automatizaciones: estado real

| Automatización | Último run | Estado registrado | Observación |
|---|---|---|---|
| Operador autónomo general | `178fd744-a9ac-8329-94e8-eaa81aaf8b76`, iniciado 1-nov 13:57:24Z | `in_progress` | No tiene `completed_at`; el resultado más reciente pertenece al run anterior del 31-oct. No declarar completado. |
| Agente de investigación CAPCOT | `e0a3713c-7984-832d-a3a4-dfe62b674664`, 31-oct | `completed` | No se observó run del 1-nov después del cambio de horario. |
| Auditor CAPCOT — cola y rotación | `9e484251-38e4-832f-beb6-b1cf21e50f52`, 31-oct 21:06–21:18Z | `completed` | El resultado fue un CONTROL_COLA estático; no ejecutó validadores por falta de runtime. El prompt actual se actualizó 1 minuto después de terminar ese run, así que no se atribuye retrospectivamente a la versión actual. |

Las tres están habilitadas. `next_run_time` aparece nulo en las tres consultas; la programación guardada no prueba por sí sola que el siguiente run esté creado.

### Cambios de automatizaciones ejecutados

- **Investigación CAPCOT:** horario corregido de 08:30 a 08:00 CDMX, diario hasta el 24-nov. La fecha inicial guardada es 1-nov 08:00, pero al corte el último run seguía siendo el del 31-oct; no se atribuye una ejecución del 1-nov.
- **Operador general:** prompt ampliado para comprobar las cuentas e instalaciones GitHub antes de declarar que no existen otros repositorios. Los repositorios adicionales se clasifican como descubiertos y permanecen de solo lectura hasta inclusión expresa del propietario.
- **Auditor CAPCOT:** prompt ampliado para enumerar múltiples paquetes del día, comprobar la profundidad real de la cola frente al workflow, inspeccionar los logs de Actions, comprobar archivos `cola/estado` y detectar `asset_filename` no materializados. Se eliminó la suposición de que solo existe un storyboard diario.

No se creó ninguna automatización nueva ni se duplicaron agentes. El prompt actual del auditor se volvió a reforzar el 1-nov 14:01Z; todavía no hay run posterior que pruebe esa versión.

## 3. CAPCOT — investigación separada de auditoría y producción

Repositorio: [capcot-capsulas-imaginantes](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes), rama `feature/capcot-video-discovery-continuity`.

### Storyboard del 31-oct

Se releyó [2026-10-31_pardelas-jetlag-solar.json](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/cola/entrada/2026-10-31_pardelas-jetlag-solar.json), SHA de blob `018cdca9cc8591fe787601c296b9047291d90b9b`.

Estado mecánico actual:
- 8 escenas, 218 palabras y 84 segundos con cortinilla.
- `approved_assets=[]`.
- `export.render_status=NOT_GENERATED`.
- No hay `export.filename`.
- `publicacion.status=PENDIENTE_DECISION_GROK`.
- El archivo `*_fuentes.md` que figuraba en la entrega anterior ya no existe en la rama actual (404); las fuentes están dentro del JSON.

**Handoff:** no existe `cola/estado/2026-10-31_pardelas-jetlag-solar.json`. Estado exacto: **RECEPCION_GROK_NO_CONFIRMADA**. El contrato [GROK_STATUS_CONTRACT.md](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/GROK_STATUS_CONTRACT.md) reserva la creación de ese archivo a Grok. No se creó ni modificó ningún estado.

### Paquetes vigentes del 1-nov

Se leyeron los dos storyboards anidados:
- [Cebolla](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/cola/entrada/2026-11-01_llorar-cebolla-quimica/storyboard.json), SHA `804c28f5c89b99844ec6cfd2079eb391a022d011`.
- [Pulpo](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/cola/entrada/2026-11-01_pulpo-tres-corazones/storyboard.json), SHA `88447427ae5403c5b04edf68110cef917ec8db5a`.

Comprobación estática:
- Cebolla: 8 escenas, 231 palabras, 78 s de escenas + 12 s de cortinilla.
- Pulpo: 8 escenas, 228 palabras, 78 s de escenas + 12 s de cortinilla.
- Ambos conservan voz `es-MX-JorgeNeural`, rate `+7%`, pitch `-2Hz`, pad `0.3`, `approved_assets=[]`, `NOT_GENERATED` y publicación pendiente.
- Ambos contienen 8 campos `asset_filename` que apuntan a `frames/scene_00X.jpg`; no existen archivos de frame correspondientes en el árbol. Son referencias no materializadas, no medios.
- Ambos están en `cola/entrada/<project_id>/storyboard.json`, no en `cola/entrada/*.json`.
- No hay archivos en `cola/estado/` para esos paquetes. Recepción Grok no confirmada.

### Bloqueo de dispatch

El workflow actual [capcot-grok-dispatch.yml](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/.github/workflows/capcot-grok-dispatch.yml):
- escucha `cola/entrada/*.json`;
- el modo `all` usa búsqueda de archivos de primer nivel (`maxdepth 1`);
- por ello no selecciona los paquetes anidados de cebolla y pulpo.

El addendum de auditoría registra que la prueba real del workflow reparado llegó a checkout y validación de paquete, pero falló en la verificación del receptor con el error literal `Falta configurar el secreto GROK_WEBHOOK_URL.`; el envío quedó `SKIPPED`. No llegó a comprobar `GROK_WEBHOOK_TOKEN`. El modo por lote quedó guardado, pero no tiene prueba real de envío. No se enviaron payloads desde esta operación y no se inspeccionaron ni modificaron secretos.

### Cobertura de datos

Lectura actual de los JSON:
- `data/temas_del_dia.json`: última fecha 28-oct.
- `data/estilos_usados.json`: registros hasta 28-oct.
- `data/rotacion.json`: contiene registros hasta 31-oct.
- `data/publicaciones.json`: contiene registros hasta 31-oct.

En `data/rotacion.json`, el registro de Pardelas conserva `cama: "None"` como texto y Kromdraai mantiene `cama` vacío; no se normalizaron esos valores porque `data/*.json` está protegido. No se modificó ningún `data/*.json`. La auditoría de las 15:00 recibió una instrucción explícita para revisar rutas anidadas, dispatchabilidad, estado Grok y placeholders sin duplicar producción.

## 4. Motor U6 — revisión documental independiente

Repositorio: [motor-u6-storage](https://github.com/marcojpad-hash/motor-u6-storage), rama `main`.

Se releyeron:
- [PROTOCOLO_CUSTODIA_INDEPENDIENTE.md](https://github.com/marcojpad-hash/motor-u6-storage/blob/main/casos/ciegos/PROTOCOLO_CUSTODIA_INDEPENDIENTE.md), SHA `06266e7948bada2c2b2af97a7e3a0cd91ac3160b`.
- [SIGUIENTE_FASE_CASOS_CIEGOS.md](https://github.com/marcojpad-hash/motor-u6-storage/blob/main/informes/2026-10-31_SIGUIENTE_FASE_CASOS_CIEGOS.md), SHA `1d13ede17f44b558920626a04accae256182c3b3`.
- [PLAN_20_CASOS_MOTOR.md](https://github.com/marcojpad-hash/motor-u6-storage/blob/main/casos/ciegos/PLAN_20_CASOS_MOTOR.md), SHA `7933f3b544fdee34f4d0da1130d6ddbfad56d28d`.

Resultado:
- C01–C20 continúan pendientes.
- B-01/N-02/C-03/H-01 son freezes históricos, no corridas del motor.
- F006/Courbet es reevaluación del mismo input; no aumenta n.
- La muestra de peso sigue en n=1; no ajustar pesos ni motor.
- El protocolo exige separar preparador Z y custodio. No se inició ningún caso porque no hay evidencia de custodia independiente asignada.
- No se modificaron Engine V5, `patterns_final_v14.json`, motores canónicos, gate Z ni resultados.

## 5. Orquestador Central — repositorio adicional descubierto

Repositorio privado: [orquestador-central](https://github.com/marcojpad-hash/orquestador-central). No se escribió en él porque no estaba entre los tres repositorios principales autorizados para cambios.

Estado verificado:
- Rama `feature/core-mvp-l1`, HEAD `446d5277b9cc4896ee18d3d5216598835f9b274e`.
- [PR draft #1](https://github.com/marcojpad-hash/orquestador-central/pull/1) abierto, 9 commits, no fusionado.
- Dos checks de GitHub Actions terminaron en éxito: job `124676976487` sobre el HEAD `446d5277b9cc4896ee18d3d5216598835f9b274e` y job `124676989696` sobre el merge ref `aeed8e8d71ecbfc2e5b7c243b18d7ef249fb8023`. Cada uno ejecutó 3 pruebas y terminó `OK`.
- Las tres pruebas cubren creación de instrucción/tarea, idempotencia y rechazo de prioridad inválida; no son pruebas HTTP de extremo a extremo.
- El prototipo es HTTP/SQLite con Bearer de propietario, no un coordinador desplegado. No hay adaptadores de proveedores, worker persistente, entrada móvil universal ni retorno entre canales.

Revisión estática, no corregida:
- La misma `idempotency_key` con texto diferente devuelve `duplicate=true` y conserva la orden anterior; puede ocultar una instrucción distinta retransmitida con la misma clave.
- Las tareas reclamadas no tienen lease, heartbeat ni recuperación automática; una tarea puede permanecer en `running`.
- El registro de implementación todavía afirma que CI no está certificado, aunque los dos checks posteriores sí terminaron en éxito. Se deja pendiente actualizar ese registro dentro del propio repositorio, cuando entre formalmente en el alcance.

## 6. Continuidad documental y commits

Actualizaciones ejecutadas y releídas en `ChatGPT-migracion/main`:

| Archivo | Commit |
|---|---|
| [CONTINUIDAD_CHATGPT.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/CONTINUIDAD_CHATGPT.md) | `a3c3051f51565a7165eaf5d81dfb3e70f851752a` |
| [BOT_DOT_AUTONOMIA.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/BOT_DOT_AUTONOMIA.md) | `dabd5dc242693d69f05983e052b0029d715f0ed1` |
| [PROYECTOS_Y_ESTADO.md](https://github.com/marcojpad-hash/ChatGPT-migracion/blob/main/PROYECTOS_Y_ESTADO.md) | `277ef87c4ee988ed35e54477cc0cfe3ec28aed5e` |

Los tres archivos se releyeron desde GitHub y sus SHA de contenido cambiaron conforme a los commits.

## 7. Bloqueos y decisiones pendientes

1. **CAPCOT:** faltan `GROK_WEBHOOK_URL` y posiblemente `GROK_WEBHOOK_TOKEN` en Actions. La primera ausencia está probada; la segunda no fue alcanzada por el run. Solo el propietario puede configurar secretos. Sin ACK y sin `cola/estado`, no hay recepción confirmada.
2. **CAPCOT:** los paquetes anidados del 1-nov no coinciden con el selector actual del workflow y contienen rutas de frames no materializadas. El auditor recibió mandato explícito para documentar y validar, no para cambiar claims, workflow, secretos o datos.
3. **Motor U6:** falta un custodio independiente distinto del preparador Z. No se inventaron casos ni roles.
4. **Orquestador Central:** PR draft sin fusión ni despliegue; no se tocó por estar fuera de los tres repositorios principales definidos para cambios.
5. **Automatizaciones:** `next_run_time` sigue nulo en las tres. El run actual del operador sigue `in_progress`; no se declara éxito ni se atribuye el resultado anterior a este run.

## 8. Límites de esta operación

- No se generaron cápsulas, imágenes, audio, voz, frames, video ni renders.
- No se publicaron ni programaron publicaciones.
- No se enviaron mensajes externos ni payloads a Grok.
- No se gastaron créditos.
- No se modificaron `data/*.json`, archivos de Motor U6, motores canónicos, patrones, secretos, permisos ni repositorios fuera de la continuidad documental.
- Las verificaciones de CAPCOT y U6 fueron lecturas/parseo estático; no se ejecutaron sus validadores locales.
