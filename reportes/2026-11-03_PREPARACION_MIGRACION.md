# Preparación de continuidad y migración — 2026-11-03

## Alcance
Preparar ChatGPT-migracion para que otra sesión/modelo pueda retomar Motor U6 y CAPCOT sin depender del chat actual. Se conservaron repositorios especializados y sus contratos. No se escribió en motor-u6-storage ni en capcot-capsulas-imaginantes durante esta preparación.

## Cambios guardados en ChatGPT-migracion/main
- docs/MAPA_HERRAMIENTAS_POR_PROYECTO.md — capacidades, cuentas, estado y límites de conectores para U6 y CAPCOT.
- docs/PROTOCOLO_MEMORIA_COMPARTIDA_ENTRE_MODELOS.md — autoridad de repositorios, arranque, colaboración, handoff y límites de GitHub como memoria compartida.
- docs/CHECKLIST_MIGRACION_FIN_DE_PROMOCION.md — prueba de recuperación y conexiones que requieren reconexión.
- bandeja/README.md y bandeja/PLANTILLA.md — protocolo y formato ampliado de acuse/entrega/verificación.
- bandeja/2026-11-03_RECUPERACION_MIGRACION.md — handoff pendiente para que la siguiente sesión/modelo haga una prueba real de recuperación.
- README.md, COMO_TRABAJAR_EN_ESTE_REPO.md, CONTINUIDAD_CHATGPT.md y PROYECTOS_Y_ESTADO.md — actualizados para incorporar la memoria compartida y las rutas de arranque.

## Commits
- Mapa herramientas: cb11c31210571d1d7441f5b49dad7afaf2006de9
- Protocolo memoria compartida: 15ddd178a9ca2b961265db58e9c8fcee239d2ded; ajuste posterior de estructura de bandeja: registrado en el historial del repo.
- Checklist migración: 82dbf5860fd2b3a4e6747fb49cef1c00790accd3
- README: 845e28ebfcd032623a25c65eb5593e868e1ad8a1; ajuste posterior de inicio obligatorio: registrado en historial.
- Continuidad: 3b96aa1708e3461b8ed5ebc18fa6bf2e3287c51e
- Estado de proyectos: 713f58d5491825a14532a37986ce32205a4bdc4f; actualización posterior de auditoría CAPCOT: registrada en historial.
- Bandeja: ec9bace50a1875333f360aca11b89973989a3427 y 9bce8e7fc4f6c4061fe1288f2f258340632371a9
- Handoff de recuperación: e5bd18e7693b68a0d1dbde33a0221db51c0e43b0

## Conexiones verificadas
- GitHub marcojpad-hash: repositorios principales accesibles con permisos de lectura/escritura.
- GitHub marcosabines-hash: sin instalaciones/repositorios visibles.
- Dropbox: autenticado como marco.jp@live.com.mx.
- Notion: workspace accesible; owner de un teamspace.
- Floot: cero proyectos.
- Canva: cero Brand Kits.
- Runway: cero workflows guardados.
- vidIQ: autenticado como marcosabines@gmail.com; cero canales.
- Undermind: cero workspaces.
- n8n: skill n8n-workflow-check disponible; conector directo no localizado.
- Automations: operador general, investigador CAPCOT y auditor CAPCOT habilitados. Las consultas devuelven next_run_time null; se actualizó el prompt del operador general para leer los nuevos protocolos, pero no se certifica próxima ejecución.

## Estado de migración
PARCIALMENTE_PREPARADA. Los documentos y el handoff están guardados y se releen desde GitHub. No se ha probado un intercambio real con otro modelo/cuenta ni la recuperación desde una sesión nueva. La transferencia de permisos y conectores no se presume.

## Restricciones preservadas
No se modificó Motor U6 ni CAPCOT. No se tocó código canónico, data, secretos, permisos, publicaciones, workflows de producción ni se consumieron créditos. No se declaró que n8n, Floot, Canva o Runway estén operando como pipelines configurados.

## Siguiente acción obligatoria
La siguiente sesión/modelo debe abrir bandeja/2026-11-03_RECUPERACION_MIGRACION.md, confirmar lectura, verificar los tres repositorios y dejar un reporte de recuperación con evidencia. Solo entonces se podrá marcar la prueba de handoff como completada.
