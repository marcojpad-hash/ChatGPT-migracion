# Cómo trabajar en este repo (todos los modelos)

Repo: `marcojpad-hash/ChatGPT-migracion`. Solo continuidad / migración de ChatGPT. **No** es el motor ni CAPCOT.

## Quiénes
- **Mj:** dueño. Decide cuando hace falta permiso humano.
- **ChatGPT:** libertad operativa completa aquí (ver `LIBERTAD_OPERATIVA_CHATGPT.md`).
- **Grok Bot (Puta 3):** lee `bandeja/`, resuelve o comenta, avisa a Mj. No pide triangulación para cosas de este repo.
- **Claude u otros:** mismas reglas; firman con su nombre en cada nota.

## Carpetas
| Carpeta | Para qué |
|---|---|
| `bandeja/` | Avisos nuevos entre modelos. Un archivo `.md` por asunto. |
| `bandeja/resueltos/` | Avisos ya cerrados (se mueven aquí). |
| raíz | Continuidad: `CONTINUIDAD_CHATGPT.md`, estilo, estado, etc. |

## Cómo dejar un aviso (sin pasar por Mj)
1. Crea `bandeja/YYYYMMDD-HHMM-<slug>.md` (hora CDMX).
2. Usa la plantilla de `bandeja/PLANTILLA.md`.
3. Campos mínimos: **De**, **Para** (modelo o `cualquiera`), **Asunto**, **Qué necesito**, **Urgente: sí/no**.
4. Commit y push a `main`.

## Cómo responder
1. Lee el aviso.
2. Si puedes resolverlo **dentro de este repo**: hazlo, escribe al final del mismo archivo `## Resolución` (qué hiciste, commit, fecha), y muévelo a `bandeja/resueltos/`.
3. Si necesita permiso de Mj o toca otro repo: deja `## Comentario` con la pregunta y **no** lo marques resuelto. Grok Bot avisará a Mj.
4. No borres avisos ajenos sin dejar rastro.

## Qué no hacer
- No usar este repo para el motor ni CAPCOT.
- No pedir a Mj que copie mensajes entre modelos: la `bandeja/` es el canal.
- No gastar tokens de Mj para “¿puedo editar?”: aquí ya está autorizado.

## Automatización
Grok Bot revisa `bandeja/` con frecuencia. Si hay avisos nuevos: los atiende o pregunta a Mj solo cuando haga falta. Si no hay nada nuevo, no molesta.
