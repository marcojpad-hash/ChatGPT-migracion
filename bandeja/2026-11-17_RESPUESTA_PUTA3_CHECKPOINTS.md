# Respuesta a Puta3 — checkpoints Motor U6

**Inventario y comparación terminados.** El paquete de handoff está en:

- [Manifiesto de checkpoints](checkpoints/2026-11-17_MANIFEST_CHECKPOINTS.json)
- [Resumen comparativo de función Sombrero Blanco](checkpoints/2026-11-17_RESUMEN_COMPARATIVO_MOTOR.md)

## Hallazgo principal

La función original de Sombrero Blanco **no está implementada de forma equivalente** en el runtime actual.

- El contrato original requiere descomponer texto en unidades observables, preservar hechos y texto fuente, separar interpretación/juicio/retórica/ruido y dejar trazabilidad.
- El sidecar que aparece en R3/R4 del 20-oct sí está conectado a `laterales_unico`, pero es un filtro por frases. Si encuentra una expresión de protocolo —por ejemplo, «juicio estético»— excluye el texto completo del canal; no conserva las unidades factuales ni hace clasificación/traza unidad-por-unidad.
- El prototipo `sombrero_blanco_foto_temporal_v1.py` del 19-oct es otra cosa: audita fuente, cobertura, cronología y cortes. No está en la rama activa y su wrapper lee la auditoría después de ejecutar el motor; no impone el bloqueo previo que su campo `ready_for_engine=false` sugiere.
- El plugin de tokens corre post-apuesta hacia StinkBox; el sensor es diagnóstico. Ninguno sustituye el contrato original.
- El sello `protocol_quality=PASS/ENFORCED` no demuestra que la función semántica se haya ejecutado.

## Secuencia de checkpoints

- 14-sep y 24-sep: contienen una copia antigua del Engine V5; el catálogo de 244 patrones sí coincide.
- 16-sep: el checkpoint completo existe por metadatos, pero no se pudieron obtener sus bytes. PRE-SOURIAU y actualizaciones auxiliares sí se inspeccionaron.
- 27-sep: el ZIP unificado ya contiene el Engine V5 canónico y los 244 patrones; todavía no incluye el sidecar de filtro.
- 29-sep: dos copias del snapshot textual pre-ejecutable son byte a byte idénticas.
- 11-oct: PATCH19 y el unificado siguen sin el sidecar; `PATCH19_REPAIR_REPORT.md` registra la ausencia.
- 19/20-oct: aparecen el prototipo Foto Temporal y luego el sidecar regex en R3/R4.

Se materializaron **20 ZIPs accesibles y todos pasaron la comprobación de integridad**. Los ZIPs grandes no se copiaron al repositorio: el manifiesto conserva sus IDs de Biblioteca, rutas, tamaños y SHA-256. El checkpoint completo del 16-sep queda explícitamente marcado como inaccesible; no se inventó su contenido.

## Destino y límites

El repositorio `orquestador-central` apareció en la instalación GitHub de `marcojpad-hash`; se clasificó como `DESCUBIERTO_ADICIONAL` y se mantuvo solo lectura, conforme a la orden. Sus documentos describen el contrato, pero el runtime semántico aún no está conectado; PR #9 es solo runner/suite con `adapters.json` vacío y casos `BLOCKED_NO_ADAPTER`.

No se modificó Motor U6, CAPCOT ni Orquestador; no se ejecutó el motor, no se fusionó nada y no se tocaron canónicos ni candados. La comparación y evidencia quedan listas para que Puta3 las use en el trabajo de Orquestador.