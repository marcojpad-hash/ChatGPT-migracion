# Normas de trabajo actualizadas — 2026-11-11

Decisión de Marco (chat aparte, 18:29–18:37 CST). Para ChatGPT y Grok.
Lo que cambió respecto a antes:

## 1. Entrega: solo vale lo verificado en el repo

Nada se da por entregado en chat. Solo vale lo que está verificado en el
repo (archivo + commit). Si algo "no llegó", se revisa el repo primero;
no se reporta no-llegada sin verificar. El bus es buzón, no llamada: la
llamada efectiva es el navegador (Pecas pregunta directo en el chat).

## 2. Voces para los Shorts (no para la microserie)

Tabla en CAPCOT docs/VOCES_POR_TEMA.md (commit 4e422781). Resumen:
- JorgeNeural (Grok/Imaginantes, oficial CAPCOT) = ciencia, física,
  química, astronomía.
- narrador_es (VoxCPM2, seed 51) = historia, historias, biografías.
- narradora_es (VoxCPM2, seed 52) = biología, cocina, hacks, cultura,
  literatura.
- narrador_en (VoxCPM2, seed 53) = canal en inglés, alternando con
  Kokoro am_adam.
- Las 3 VoxCPM2 NO son para la microserie: sus locks son las voces Grok
  (ara, luna, ursa, leo, orion) y no se tocan. La voz la decide el tema.

## 3. Stock: 3 semanas de Grok

Grok crea cápsulas en las 3 semanas que quedan; Grok Bot las monta y las
deja programadas junto con Pecas; Pecas verifica cada una en el repo.
Pecas monta además 1 video viral animado por semana como stock, por si
Grok no se renueva (caro). El saldo de créditos de creación solo lo ve
Marco en su interfaz de Grok (SuperGrok legacy); Grok no tiene acceso a
su propio contador (confirmado 18:31 CST). Sin ese número no se inventa
el stock.

## 4. Montaje: frames + movimiento + subs + MP4

No hay consola de renderización ni CapCut. El montaje es: frames con
transición de cámara, zoom y autodesplazamiento, cortados en planos de
~2.5 s para que se vea movimiento; subtítulos calibrados con el audio;
audio empatado; render completo a MP4 con ffmpeg. Eso ya lo hacen
montar_capsula.py / build_en.py.

## 5. ChatGPT, montador de respaldo

ChatGPT (3 meses gratis según Marco) es el montador de respaldo. Puede
montar vía Actions (tiene acceso al repo y a Workflows), pero el workflow
de montaje no existe todavía: hay que cablearlo.

## 6. No más planeación tal cual

Marco no quiere más documentos de planeación. Ejecución, no planes.
