# Operación autónoma — Run 8
**Fecha:** 20 de noviembre de 2026  
**Corte:** 12:14, Ciudad de México  
**Estado de ejecución:** el run del operador continúa `in_progress`; no hay `completed_at`.

## Resultado

- CAPCOT: cinco cambios documentales confirmados en la rama de trabajo, inventario de 14–20 nov revisado, dos conflictos exactos de slot identificados y ninguna promoción ni redispatch.
- Motor U6: auditoría de solo lectura. No hubo corridas nuevas; se confirmaron bloqueos de separación de funciones, Gate Z90 y autoridad de rama.
- Continuidad: la migración sigue incompleta por falta del acuse de segunda sesión en el archivo de recuperación requerido.
- No se modificaron permisos, secretos, motores canónicos, datos congelados ni ramas protegidas.

## CAPCOT — cambios verificados

Rama `feature/capcot-video-discovery-continuity`:

| Commit | Cambio |
|---|---|
| `2795358cb3c22f8a92caa16772162e2673340a28` | Marea cerebral: corregida la nota de verificación primaria. El intervalo 60–83 corresponde a la muestra analítica final; 60–84 aparece en el resumen del artículo. DOI todavía pendiente de resolución independiente. |
| `f52e57dddf3354eeb00e715ab3779ffc3d52a326` | Sapropeles: retirado el estado falso `VERIFICADO_CROSSREF`; la verificación queda pendiente. |
| `dcc9873dddf10d91d1187078a6f1650029cb777c` | Microplásticos: la página primaria está identificada, pero no se declara resuelto el DOI. |
| `f69fd05dca6fbd13973b3aecfe2663b8f75b4f3a` | Pareja de cuásares: nueva lectura narrativa independiente después de cambios de narración; FAIL 82, dos transiciones no causales, estado fuera de promoción. |
| `7d77b42dae7dc531b8731747215a1ebd19ff4467` | Control de cola actualizado y releído. |

[Control de cola CAPCOT — 20-nov](https://github.com/marcojpad-hash/capcot-capsulas-imaginantes/blob/feature/capcot-video-discovery-continuity/docs/briefs/2026-11-20_CONTROL_COLA.md)

### Auditoría y límites

- Revisados 11 storyboards de 14–20 nov y los 12 IDs del lote 5–7 nov. Los 12 del lote mantienen dos PASS y diez FAIL; su narrativa no cambió desde la revisión independiente del 18-nov, por lo que no se repitió QA.
- Dos colisiones exactas de rama/slot: suelo (17-nov 17:00) frente a Vikingos en main; hidrotermales (18-nov 23:30) frente a Beta Pictoris en main.
- La rama feature conserva un horario del 09-nov; main tiene política del 16-nov. Los datos JSON se inspeccionaron en solo lectura y no se modificaron.
- No hay archivos de estado Grok en feature. El marker pendiente del robot orbital no equivale a recepción. El paquete de robot tiene programación/producción preexistente para el 21-nov 19:00; no se redispatcha.
- La carpeta llamada ratas topo contiene ocho PNG, pero no storyboard ni carpeta de proyecto. Un ID de endscreens no se pudo vincular al tema; se corrigió la atribución previa y se dejó intacta la carpeta.
- El smoke check verde de Kuroshio no ejecutó el validador estructural real ni `--check-doi`. La comprobación estática realizada en este run no se presenta como ejecución del validador oficial.
- En main, Semgrep falló con 32 findings; Gitleaks terminó correctamente. No había artefacto SARIF descargable para clasificar los findings. No se modificó main ni se disparó workflow.

## Motor U6 — solo lectura

- Se leyó el contrato de `alterno/cameo-pesos`, `DELEGACIONES.md`, las instrucciones de main, la memoria compartida obligatoria, el contrato multi-modelo y las capacidades.
- La orden #465 sigue sin cohorte F007 independiente: el lote observado conserva ocho sujetos, dos cortes por sujeto, fuentes secundarias y sin cola/custodia independiente. No se incrementó n ni se simularon corridas.
- La fábrica mezcla semillas y destinos en el mismo proceso; no se invocó. La Gate Z90 no calcula ni verifica todos los límites temporales exigidos. PR #8 continúa abierto/no integrado.
- Un workflow automático de auditoría sigue escribiendo un snapshot en main, pese a que el contrato operativo declara main como solo consulta. El run observado terminó correctamente y produjo el commit `7209c3f`; no se modificó ni deshabilitó el workflow.
- `motor-u6-storage` aparece público aunque su README lo describe como privado. No se escribieron datos operativos en ese repositorio. No se abrieron custodias ni destinos, no se reejecutaron C01–C20 y no se tocaron motores canónicos, pesos, patrones, FREEZE ni evidencia congelada.

## Descubrimiento de cuentas y repositorios

- `marcojpad-hash`: 11 repositorios visibles.
- `marcosabines-hash`: 0 repositorios visibles.
- Ocho repositorios adicionales fueron clasificados como solo lectura: `orquestador-central`, `red-teaming-safety-u6`, `agente-cero-costo`, `baterias-tokens`, `baterias-memoria`, `memoria-compartida`, `microserie-heredera-sadtalker` y `microserie-heredera-voces`.
- `orquestador-central` aparece público aunque `BOT_DOT_AUTONOMIA.md` lo describe como privado; permanece en solo lectura.
- `ChatGPT-migracion` aparece público y su README no lo declara privado; no se sostiene la discrepancia de privacidad atribuida anteriormente a este repositorio.

## Migración y automatizaciones

- `bandeja/2026-11-03_RECUPERACION_MIGRACION.md` sigue sin acuse del destinatario ni resolución. No hay segunda sesión verificable que cierre la migración.
- El último registro transversal disponible sigue siendo `reportes/2026-10-31_AUDITORIA_TRANSVERSAL.md`.
- Dot nativo sigue sin conexión ejecutable según la documentación vigente; no se inventó acceso.
- Investigador CAPCOT: COMPLETED el 20-nov a las 08:40 CDMX.
- Auditor CAPCOT: último COMPLETED el 19-nov a las 15:28 CDMX; siguiente ejecución prevista 20-nov 15:00.
- Operador único: run 8 `in_progress`, sin `completed_at`.
- El monitor diario de Issues de las 09:00 no aparece entre las automatizaciones activas; no se creó otra automatización durante este run.

## Acciones no realizadas

No se generaron medios, no se publicó ni programó contenido, no se consumieron créditos, no se enviaron mensajes externos, no se cambiaron secretos/permisos, no se dispararon Actions, no se modificó main de U6 ni se tocó evidencia protegida.
