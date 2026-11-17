# Resumen comparativo de checkpoints — Motor U6

**Fecha:** 17-nov-2026  
**Propósito:** dejar a Puta3 evidencia de los checkpoints y de la evolución real de Sombrero Blanco, para que pueda trasladar el contrato correcto a Orquestador Central.  
**Inventario completo:** [`2026-11-17_MANIFEST_CHECKPOINTS.json`](2026-11-17_MANIFEST_CHECKPOINTS.json)

## Resultado ejecutivo

1. Se localizaron checkpoints y paquetes entre el 14-sep y el 20-oct. Se materializaron e inspeccionaron **20 ZIPs**; los 20 pasaron `zipfile.testzip()`. Los ZIPs grandes permanecen en la Biblioteca personal; aquí se deja manifiesto con rutas, IDs, tamaños y SHA-256.
2. El ZIP completo del 16-sep existe por metadatos, pero la Biblioteca lo trata como archivo de proyecto y no permitió obtener sus bytes. No se declara su contenido ni integridad.
3. Los checkpoints del 14-sep y 24-sep contienen una copia antigua de `Engine_V5_CANONICO_SOLO.py`. Desde el ZIP del 27-sep, los paquetes accesibles contienen el hash del Engine V5 canónico actual. El catálogo `patterns_final_v14.json` conserva el mismo hash y 244 patrones.
4. El checkpoint unificado del 11-oct y PATCH19 no contienen `sidecar_sombrero_blanco_filtro_v1.py`; el propio `PATCH19_REPAIR_REPORT.md` registra el archivo ausente y el error de salida.
5. El 19-oct aparece una capa distinta, `sombrero_blanco_foto_temporal_v1.py`, con auditoría de fuentes, cobertura, cronología y cortes. No está en la rama activa. Además, el wrapper `correr_u6_sombrero_espectro_v2.py` ejecuta el motor antes de leer la auditoría: no aplica `ready_for_engine=false` como bloqueo previo.
6. Los paquetes R3/R4 del 20-oct sí incluyen el sidecar actual, pero es un filtro por frases. Está conectado a `laterales_unico`; restringe canales de texto y puede cambiar qué texto ven los laterales, pero no equivale al Sombrero Blanco semántico original.

## Contrato que debe preservarse

La reconstrucción combina las especificaciones del checkpoint del 14-sep —metacognición, clasificación de pregunta, sidecars y método de rigor— con el contrato vigente en [`SOMBRERO_BLANCO.md`](https://github.com/marcojpad-hash/orquestador-central/blob/main/docs/filtros_operativos/SOMBRERO_BLANCO.md).

El trabajo esperado es **descomponer y trazar unidades**, no borrar texto:

- conservar el texto original y los hechos útiles;
- separar afirmaciones/fuentes, observaciones, interpretaciones, juicios, figuras retóricas, ruido y metadatos de protocolo;
- señalar qué unidad es qué y de dónde procede;
- no convertir la clasificación en evidencia de H ni alterar P/A/C;
- no eliminar una frase factual completa porque contenga una expresión marcada.

El documento de Orquestador [`INVENTARIO_GUARDIANES_PROTOCOLO.md`](https://github.com/marcojpad-hash/orquestador-central/blob/main/docs/filtros_operativos/INVENTARIO_GUARDIANES_PROTOCOLO.md) reconoce que la función original no está cableada.

## Cronología comparada

| Fecha | Artefacto | Qué confirma |
|---|---|---|
| 14-sep | `CHECKPOINT_MOTOR_CLONABLE_20260914.zip` | Especificaciones de metacognición, pregunta detrás, Copi/falacias, Beristáin y Hécate-Holmes-Schopenhauer. El Engine V5 dentro del ZIP es antiguo; patrones sí coinciden. |
| 16-sep | `CHECKPOINT_MOTOR_V15_1_ACTUAL_20260916.zip` | Existe por metadatos; bytes no accesibles. Los paquetes acompañantes PRE-SOURIAU y últimas actualizaciones sí se pudieron inspeccionar. |
| 24-sep | V15.3 V0.7 activo ZIP + TXT | Sigue llevando el Engine V5 antiguo; no debe usarse como copia canónica. |
| 27-sep | `MOTOR_UNICO_UNIFICADO_20260927_STINKBOX_STORAGE.zip` | Ya lleva Engine V5 canónico y patrones 244. Contiene sensor y plugin de tokens, todavía sin el sidecar de filtro. |
| 29-sep | `MOTOR_MODELO_AGNOSTICO_PRE_EJECUTABLE_V15_3.txt` | Dos copias de Biblioteca con bytes idénticos; es un snapshot textual posterior. |
| 11-oct | Patches 14–19 y checkpoint unificado | La secuencia corrige contrato, causas nulas, procedencia, modelos y cableado. El ZIP final sigue sin el sidecar de Sombrero Blanco; PATCH19 lo registra como ausente. |
| 19-oct | `SOMBRERO_BLANCO_FOTO_TEMPORAL_V1` y `SOMBRERO_ESPECTRO_V2` | Prototipo temporal/proveniencia separado; devuelve bloqueos, pero el wrapper no detiene el motor antes de correr. |
| 20-oct | R3, U6 unificado, Tortugas R3, motor limpio y R4 | El sidecar regex ya aparece en R3/R4. R4 es el paquete compacto más reciente de esa secuencia; no contiene la capa Foto Temporal. |

## Qué está conectado en la rama activa U6

Rama revisada: [`alterno/cameo-pesos`](https://github.com/marcojpad-hash/motor-u6-storage/tree/alterno/cameo-pesos). `main` se mantuvo intacta.

- [`sidecar_sombrero_blanco_filtro_v1.py`](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/motor/motor/sidecar_sombrero_blanco_filtro_v1.py): se llama desde `laterales_unico` en entrada/salida. Usa patrones de frases de ruido de protocolo. Si encuentra, por ejemplo, «juicio estético», excluye el texto completo del canal; no separa la parte factual de la parte valorativa ni entrega trazabilidad unidad-por-unidad.
- [`laterales_unico_v1.py`](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/motor/motor/laterales_unico_v1.py): integra el filtro en el hub de laterales. La restricción del canal puede afectar qué texto reciben los laterales, pero el Sombrero no se convierte por sí mismo en voto del predictor central.
- [`plugin_sombrero_blanco_token.py`](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/motor/motor/plugin_sombrero_blanco_token.py): corre después de la apuesta y persiste tokens descubiertos en StinkBox; no devuelve esa salida al predictor de la misma corrida.
- [`sensor_perfil_narrador_v0_1.py`](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/motor/motor/sensor_perfil_narrador_v0_1.py): diagnóstico de perfil/texto; no reemplaza el filtro semántico.
- [`guardianes_control_v1.py`](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/motor/motor/guardianes_control_v1.py): corre después del predictor. Puede retener el cierre como `LATENTE` y disparar tortugas; no cambia H1/H2/top1.
- [`plugin_metodo_rigor.py`](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/motor/motor/plugin_metodo_rigor.py): alarma corta; el controlador agrega comprobaciones contextuales. Las cuatro preguntas completas del método siguen en el protocolo/manual, no como operación automática equivalente.
- [`plugin_pregunta_detras_v2.py`](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/motor/motor/plugin_pregunta_detras_v2.py): marca y explica; no decide H.
- Copi y Beristáin tienen módulos U6 posteriores; no son por sí mismos un runtime transversal de Orquestador.

Además, `MOTOR_V15_3_UNICO` publica `protocol_quality=PASS/ENFORCED` sin que ese sello pruebe que se ejecutó la descomposición semántica original. No debe usarse como evidencia suficiente de Sombrero Blanco.

## Qué está ausente o cambió de función

**No se encontró una implementación equivalente del Sombrero Blanco original.** Lo que hay son piezas distintas:

1. Un filtro conectado pero lexical: excluye el texto entero cuando encuentra frases de protocolo, en vez de preservar hechos y aislar juicio/ruido.
2. Un almacén de tokens posterior a la apuesta.
3. Un sensor diagnóstico.
4. Un prototipo temporal/proveniencia que no está en la rama activa y cuyo wrapper no hace cumplir el bloqueo previo.

La capa Foto Temporal del 19-oct no debe confundirse con el contrato semántico: evalúa fuente/cobertura/cronología/post-Z, no realiza por sí sola la clasificación unidad-por-unidad de hechos, juicios y retórica. Tampoco es un bloqueo efectivo mientras el wrapper ejecute primero el motor.

## Orquestador Central

Repositorio descubierto adicional: [`orquestador-central`](https://github.com/marcojpad-hash/orquestador-central), solo lectura en esta operación.

- [`SOMBRERO_BLANCO.md`](https://github.com/marcojpad-hash/orquestador-central/blob/main/docs/filtros_operativos/SOMBRERO_BLANCO.md) y el inventario describen el contrato, pero no hay runtime semántico conectado.
- [`runtime/README.md`](https://github.com/marcojpad-hash/orquestador-central/blob/main/runtime/README.md) promete capacidad de bloqueo; [`ARCHETYPE-SEQUENTIAL-VERIFIABLE-v1.md`](https://github.com/marcojpad-hash/orquestador-central/blob/main/docs/ARCHETYPE-SEQUENTIAL-VERIFIABLE-v1.md) dice que el motor automático de guardianes aún no está implementado.
- PR #9 es una suite/runner de aceptación: `adapters.json` sigue vacío y los 15 casos quedan `BLOCKED_NO_ADAPTER`. No certifica la conexión semántica.
- Issue #8 sigue abierto.

No se modificó Orquestador ni se fusionó PR alguno: el repositorio fue descubierto como adicional y queda fuera del alcance de escritura de esta operación.

## Pruebas y límites

- **20/20 ZIPs accesibles:** integridad de archivo PASS.
- **No se ejecutó el motor ni se reejecutaron sus pruebas.** Los conteos del 20-oct son reportes históricos, no resultados de esta operación.
- El informe unificado declara 148 PASS/2 SKIP, pero la revisión independiente no reprodujo un único run combinado de 148; encontró motor 102/2 y laterales 46/0 por separado.
- Otros reportes históricos: compactación 77/2; integración StinkBox 84/2; calibrable 92/2 y motor+laterales 163/2; variante de hipótesis abiertas 94/2.
- El checkpoint completo del 16-sep no se pudo materializar. No se infiere su contenido.
- No se copiaron ZIPs grandes al repositorio; se dejó manifiesto con SHA-256, tamaño, IDs y rutas de Biblioteca.

## Uso del handoff

Puta3 puede tomar el contrato y la comparación de aquí para Orquestador. No debe importar el sidecar U6 como si fuera el Sombrero Blanco original, ni declarar implementado el guardián por el hecho de que exista una regex, un sensor, un plugin post-apuesta o una suite de aceptación.

**Fuentes y hashes completos:** [`2026-11-17_MANIFEST_CHECKPOINTS.json`](2026-11-17_MANIFEST_CHECKPOINTS.json).