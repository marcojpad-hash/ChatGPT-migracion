# Auditoría transversal — 2026-10-31

## Resultado ejecutivo

Se revisaron los tres repositorios activos identificados, los flujos de automatización y la documentación Notion relacionada con Motor. Se aplicaron correcciones materiales en CAPCOT y Motor U6 y se actualizó la continuidad general.

## Problemas resueltos

### CAPCOT
- Catálogo Markdown de estilos incompleto frente a JSON canónico (37 vs 50): sincronizado a 50.
- Plantilla/validador desalineados con contrato textual: actualizados.
- Storyboard con rutas de assets inexistentes y privacidad pública: corregido.
- Fuentes separadas del JSON: archivo extra eliminado, fuentes quedan en JSON.
- Rotación basada en snapshots obsoletos: nueva lectura reconciliada de data, cola, proyectos y salidas.
- Cola seleccionaba entradas históricas: ahora filtra por fecha.
- Producción asumía asset_filename en preproducción: nombres se asignan solo en la etapa Grok.
- No había confirmación verificable de recepción: contrato cola/estado creado.
- La automatización de tercera cápsula podía duplicar producción y generar medios: convertida en auditor.

### Motor U6
- F006 R7 estaba solo en artifact de Actions: recuperado, SHA del ZIP verificado, resumen/compromiso/evaluación/registro persistidos y corrida agregada a resultados.jsonl.
- F006 repetía el mismo caso Courbet: marcado como reevaluación, sin aumentar el tamaño muestral.
- Confusión entre Engine V5, runner V15.3, hash de candado y hash de archivo: mapa de autoridad creado.
- Notion tenía cuatro casos ciegos históricos sin copia pre-Z en GitHub: migradas entradas y freezes de B-01, N-02, C-03 y H-01, excluyendo identidades/desenlaces.
- No había carpeta/plantilla para 20 casos ciegos: creada carpeta, plantilla y plan; no se inventaron casos.
- Error de destino en Courbet sigue abierto: se creó protocolo de casos independientes y calibración sin fuga.

## Problemas aún pendientes

1. **Destino personal:** F006 predijo auge y el desenlace sellado fue ruptura. El caso se repitió; no basta para calibrar peso. Se requiere nueva muestra independiente.
2. **20 casos ciegos:** no se encontró un conjunto dedicado de 20 corridas del motor con entrada Z, salida congelada y desenlace sellado. Se creó el plan, no los datos.
3. **Analítica social privada:** Meta/Instagram/Facebook/YouTube Analytics/TikTok no están conectados. Windsor.ai fue sugerido, pero no está instalado/conectado.
4. **Recepción Grok:** el contrato existe; Grok aún debe adoptar el archivo cola/estado. Sin ese archivo, no se confirma recepción.
5. **Notion:** el workspace alcanzó el límite de bloques gratuitos. No se pudo actualizar ni crear el aviso de vigencia; GitHub es la fuente de verdad.
6. **Dot:** no disponible en Go; el operador diario es sustituto parcial, no agente 24/7.
7. **CAPCOT branch:** feature está divergida de main (61 commits exclusivos de feature y 9 exclusivos de main); no se hizo merge por la restricción del proyecto.
8. **Operador general:** run del 31-oct seguía en progreso al corte; no se reporta como completado.

## Acciones y artefactos
- CAPCOT: docs/briefs/2026-10-31_AUDITORIA_INTEGRIDAD_CAPCOT.md, scripts/registro_editorial.py, scripts/validar_storyboard.py, templates/storyboard_vertical.template.json, docs/GROK_STATUS_CONTRACT.md.
- Motor: informes/2026-10-31_AUDITORIA_CONTINUIDAD_Y_ESTADO.md, docs/MAPA_VERSIONES_Y_AUTORIDAD.md, casos/fabrica/lotes/F006_TRAZA_V2_R7_*, casos/ciegos/.
- Automatizaciones: operador general 07:00, investigador CAPCOT 08:00, auditor CAPCOT 15:00.

## Límites
No se modificaron motores canónicos, patrones, candados, main CAPCOT ni data/*.json. No se publicaron cápsulas ni se generaron medios. No se almacenaron credenciales. Las pruebas Python nuevas se añadieron, pero no se ejecutaron en esta sesión.
