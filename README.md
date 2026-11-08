> **MEMORIA COMPARTIDA OBLIGATORIA:** Antes de cualquier trabajo, cualquier modelo debe leer [AGENTS.md](AGENTS.md), [el protocolo transversal](https://github.com/marcojpad-hash/memoria-compartida/blob/main/PROTOCOLO_MEMORIA_COMPARTIDA_OBLIGATORIA.md) y [el índice de memoria](https://github.com/marcojpad-hash/memoria-compartida/blob/main/INDICE.md); consultar los hechos pertinentes y sincronizar los hechos durables al terminar. No empezar desde la memoria conversacional.

# ChatGPT-migracion

Repositorio de continuidad operativa entre instancias de ChatGPT.

**No** es el motor (`motor-u6-storage`) ni CAPCOT (`capcot-capsulas-imaginantes`). Mantener los proyectos separados.

## Inicio obligatorio

0. Leer el [Contrato de trabajo multi-modelo](https://github.com/marcojpad-hash/orquestador-central/blob/main/docs/CONTRATO_TRABAJO_MULTI_MODELO.md) y revisar [capacidades verificadas](https://github.com/marcojpad-hash/orquestador-central/blob/main/docs/CAPACIDADES_MODELOS.md).

1. Leer [CONTINUIDAD_CHATGPT.md](CONTINUIDAD_CHATGPT.md).
2. Leer [ESTILO_DE_TRABAJO.md](ESTILO_DE_TRABAJO.md).
3. Leer [BOT_DOT_AUTONOMIA.md](BOT_DOT_AUTONOMIA.md).
4. Leer [DOT_EQUIVALENTE_OPERATIVO.md](DOT_EQUIVALENTE_OPERATIVO.md) para conocer el estado real de Dot y el sustituto activo.
5. Revisar [PROYECTOS_Y_ESTADO.md](PROYECTOS_Y_ESTADO.md) y [docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md](docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md).
6. Leer [docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md](docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md) y [docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md](docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md).
7. Después abrir los documentos actuales del proyecto concreto antes de actuar.

## Regla central

El usuario define el objetivo. ChatGPT coordina y ejecuta el trabajo de principio a fin con las herramientas y permisos disponibles. No debe esperar instrucciones intermedias para cada paso, ni convertir verificaciones pendientes en preguntas que pueda resolver por sí mismo. Debe entregar resultados comprobados y reportes útiles. Solo escala decisiones que realmente requieran al usuario.

## Documentos

- [CONTINUIDAD_CHATGPT.md](CONTINUIDAD_CHATGPT.md): instrucciones de arranque y continuidad.
- [ESTILO_DE_TRABAJO.md](ESTILO_DE_TRABAJO.md): reglas de ejecución, comunicación y evidencia.
- [BOT_DOT_AUTONOMIA.md](BOT_DOT_AUTONOMIA.md): coordinación entre ChatGPT, bots, automatizaciones y Dot.
- [DOT_EQUIVALENTE_OPERATIVO.md](DOT_EQUIVALENTE_OPERATIVO.md): estado real de Dot y operador autónomo sustituto.
- [PROYECTOS_Y_ESTADO.md](PROYECTOS_Y_ESTADO.md): proyectos, restricciones y estado conocido.
- [ABRAZO_CHIQUITO.md](ABRAZO_CHIQUITO.md): referencia afectiva compartida.
- [PERFILAMIENTO_PERSONAL_Y_DE_TRABAJO.md](PERFILAMIENTO_PERSONAL_Y_DE_TRABAJO.md): contexto personal y creativo; leer con criterio y sin convertirlo en diagnóstico.

## Libertad operativa

ChatGPT puede crear, corregir y registrar trabajo en este repositorio con la conexión autorizada, sin pedir permiso para cada paso rutinario. Verificar siempre rama, alcance y restricciones. No modificar otros repositorios o sistemas fuera del alcance solicitado.

## Canal entre modelos

Usar la carpeta `bandeja/` cuando exista y esté habilitada para intercambiar entregables entre modelos. Todo mensaje debe incluir objetivo, artefactos, estado, evidencia y siguiente acción. No asumir que otro agente recibió o ejecutó algo sin confirmación observable.


## Auditoría transversal 2026-10-31

[Informe de problemas, correcciones y pendientes](reportes/2026-10-31_AUDITORIA_TRANSVERSAL.md).


## Memoria compartida y operación de proyectos

- [Mapa de herramientas por proyecto](docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md): capacidades y conexiones reales para Motor U6 y CAPCOT.
- [Protocolo de memoria compartida entre modelos](docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md): arranque, colaboración, handoffs, autoridad y verificación.
- [Checklist de migración antes del fin de la promoción](docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md): pruebas pendientes para una sesión nueva.
- [Bandeja entre modelos](bandeja/README.md) y [plantilla base](bandeja/PLANTILLA.md): intercambio persistente con acuse y cierre verificables.

GitHub es la memoria operativa compartida; no es mensajería instantánea ni ejecuta automáticamente al destinatario. Cada modelo debe leer la fuente de verdad y registrar sus entregables en el repositorio especializado.