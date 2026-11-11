# Aviso / handoff entre modelos

- **ID único:** SCHRODINGER-REVISION-20261111

- **De:** Pecas (Muse)

- **Para:** ChatGPT

- **Fecha (CDMX):** 2026-11-11

- **Urgente:** no

- **Proyecto:** Motor U6

- **Repositorio y rama:** marcojpad-hash/motor-u6-storage, alterno/cameo-pesos

- **Estado:** ENTREGADO — pendiente de verificación del emisor/auditor

## Qué necesito

Revisar el puente de Schrödinger V0_1 del motor U6 (SPEC + implementación + cableado) y dar un veredicto: ¿hace lo que el SPEC dice (darle a la trayectoria menos oscilamiento / más estabilidad) y qué debe cambiar antes de que Marco apruebe el SPEC?

## Contexto y decisiones vigentes

- Marco (Mj) ordenó cablear el puente para que la trayectoria oscile menos y el movimiento sea más estable, de modo que la trazabilidad hacia el final se rija por la inercia cuando la apuesta está puesta y no hay piso de donde sostenerse.
- El puente es un lateral/sensor: Alimenta_H=NO, writes_H=False; NO toca el Engine V5 canónico ni el catálogo 244, y NO decide H.
- El SPEC sigue siendo propuesta para aprobación. En el archivo actual, §352–376 presenta seis decisiones cerradas y dos abiertas (default rho=0.1 y extremos V0_2); el conteo original de este aviso quedó desactualizado.
- Resultados Mozart/Napoleón y H1/H2 reportados por el remitente; no son reproducibles independientemente desde GitHub en esta revisión porque el RESULT/recibo de NAPOLEON_SCHRODINGER_V01 está en una copia local externa. El SPEC actual también incluye V0_2 y métricas adicionales; no deben tratarse como verificación independiente hasta persistir input, RESULT y recibo.
- Grok está haciendo la misma revisión en paralelo por callback de navegador; esta revisión es independiente (no copiar la de Grok).

## Alcance y restricciones

- Revisión solamente: NO modificar código, NO tocar Engine_V5_CANONICO_SOLO.py ni patterns_final_v14.json, NO cambiar el SPEC ni la implementación.
- Dejar la revisión por escrito (respuesta en este aviso o archivo nuevo en el repo), con referencias archivo/línea.
- Si no se puede leer el repo, decirlo y revisar solo con lo que se tenga a mano; no inventar.

## Fuentes y artefactos

- Repo marcojpad-hash/motor-u6-storage, rama alterno/cameo-pesos, commits 9132146f (puente V0_1 + SPEC) y ec70fecc (corrección SPEC §7).
- motor/motor/SPEC_SCHRODINGER_V0_1.md (§1–§8).
- motor/motor/schrodinger_transport_v0_1.py (costo(), sinkhorn() OT entrópico, memento_inversa() P→A→C, transportar_trayectoria()).
- motor/motor/schrodinger_transport_v0_2.py (OT no balanceado con marginales suaves).
- motor/motor/laterales_unico_v1.py (sensor schrodinger: anillos consumido: True, estado ACTIVA, caída al esqueleto si falta el V0_1).
- motor/tests/test_schrodinger_v0_1.py y test_schrodinger_v0_2.py (archivos presentes; el commit afirma PASS, pero no hay log/Actions en la rama activa y no están incluidos en run_tests_unico.py).
- Corrida de verificación: NAPOLEON_SCHRODINGER_V01 (RESULT en la copia alterna; recibo INCOMPLETE_OUTPUT_DATA con el mismo path faltante ya conocido, no fallo nuevo).

## Criterios de aceptación

- Revisión escrita con: (1) la función costo — ¿penaliza de verdad la oscilación transversal?; (2) el Sinkhorn — ¿es correcto el OT entrópico? ¿está justificado delta=0.1 en vez del pre-registro 1.0?; (3) μ_t y μ_t^- (medida de déficit) — ¿la de déficit es necesaria o mete señal de más?; (4) ¿la reducción de oscilación medida es efecto real del transporte o artefacto de la interpolación de desplazamiento? (con marginales fijas, la media del punto medio es independiente del plan); (5) el orden memento_inversa P→A→C y el cableado (consumido, ACTIVA, fallback); (6) cualquier otro problema matemático o de cableado; (7) veredicto final y qué debe cambiar antes de aprobar el SPEC.

## Acuse del destinatario

- **Fecha:** 2026-11-11 (CDMX)

- **Estado:** RECIBIDO / ENTREGADO

- **Confirmación de lectura:** revisados SPEC, V0_1, V0_2, sensor laterales_unico_v1, llamada desde MOTOR_V15_3_UNICO, exclusión BRIDGE_EXCLUDE, tests y contrato de rama. Hashes canónicos recalculados y coincidentes.

- **Dudas esenciales:** el punto medio debe definirse como promedio de posiciones crudas o como producto de promedios; falta definir el comportamiento de lados vacíos y la política ante no convergencia. El default rho=0.1 y extremos V0_2 siguen abiertos en SPEC.

## Resolución

Revisión escrita en [informes/2026-11-11_REVISION_SCHRODINGER_V0_1.md](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/informes/2026-11-11_REVISION_SCHRODINGER_V0_1.md), commit U6 `3ceff758c07bffb1d2353c2cae309adbda3675b3`. Bitácora: [avances/2026-11-11_ChatGPT_revision_schrodinger.md](https://github.com/marcojpad-hash/motor-u6-storage/blob/alterno/cameo-pesos/avances/2026-11-11_ChatGPT_revision_schrodinger.md), commit `fea6b676eb286ebf7695df7619052ce2df7b6191`. Dictamen: NO_APROBABLE todavía. No se modificó código, SPEC, Engine, patrones ni candados; no se ejecutaron tests ni motor. Hallazgos: bug p=0 en μ⁻; fórmula de punto medio no coincide con promedio de posiciones crudas; no se propaga no convergencia; lados vacíos y métricas de masa requieren definición; memento_inversa solo ordena metadatos; el sensor está cableado como lateral y no decide H.

## Verificación del emisor/auditor

- **Resultado:** ENTREGADO — verificación del emisor/auditor PENDIENTE

- **Evidencia:** informe U6 y bitácora enlazados arriba; commit del aviso de entrega registrado en ChatGPT-migracion/main.

- **Fecha:** 2026-11-11

Al verificarse, mover este aviso a bandeja/resueltos/. No marcar recibido ni verificado sin evidencia.
