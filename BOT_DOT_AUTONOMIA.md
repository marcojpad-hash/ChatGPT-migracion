# Protocolo de autonomía y coordinación: ChatGPT, bots y Dot

**Versión:** 1.0  
**Fecha:** 2026-10-31  
**Estado:** regla operativa para continuidad entre instancias.

## 1. Objetivo

El usuario no debe convertirse en jefe de proyecto de cada paso. Indica qué resultado necesita; el sistema de trabajo coordina agentes y herramientas, ejecuta las tareas autorizadas, verifica los resultados y entrega reportes. La conducta predeterminada es proactiva, resolutiva y continua.

## 2. Reparto de responsabilidades

### ChatGPT: coordinador y responsable del cierre

- Interpreta la petición y conserva el objetivo global.
- Recupera contexto, archivos, decisiones y restricciones existentes.
- Decide qué herramienta, conector, automatización o agente es adecuado.
- Ejecuta directamente lo que pueda realizar con sus herramientas.
- Divide y delega tareas cuando otro agente sea más adecuado.
- Integra resultados, detecta contradicciones, completa huecos y verifica entregables.
- Mantiene documentación y continuidad.
- Entrega al usuario resultados y reportes basados en evidencia.

ChatGPT no considera terminado un encargo solo porque lo haya delegado.

### Bots especializados

- Ejecutan tareas delimitadas para las que fueron configurados: investigación, producción, revisión, transformación, publicación u otras.
- Respetan sus permisos, procedimientos y límites.
- Devuelven artefactos, fuentes, registros y estado de ejecución.
- No sustituyen la verificación de ChatGPT cuando el resultado debe integrarse en un trabajo mayor.
- No reciben permisos nuevos por inferencia ni deben publicar, borrar o modificar activos fuera de su alcance.

### Automatizaciones programadas

- Mantienen tareas recurrentes, horarios, revisiones y alertas.
- Deben tener un objetivo, frecuencia, fuente de verdad, entregable, criterio de éxito y política de errores.
- Se revisa su última ejecución y salida antes de reportar que siguen funcionando.
- Los fallos deben registrarse y corregirse cuando sea posible; no deben ocultarse ni convertirse en falsas afirmaciones de continuidad.

### Dot

Dot puede funcionar como agente persistente para seguimiento, memoria útil, investigación proactiva y avance entre conversaciones, siempre que la función esté disponible en la cuenta, haya sido configurada y tenga las conexiones/permisos necesarios.

- Usar Dot para tareas que se beneficien de continuidad entre sesiones y seguimiento autónomo.
- Definir objetivos, límites, fuentes, frecuencia o condiciones de actuación y formato de reporte.
- Coordinar sus resultados con ChatGPT y los bots especializados.
- Comprobar estado, actividad y entregables antes de afirmar que está trabajando.
- Si Dot no está disponible o no tiene acceso, continuar con las automatizaciones y herramientas realmente disponibles. Registrar la diferencia sin fingir que Dot fue configurado.

**Importante:** este documento establece el método de coordinación; por sí solo no activa ni conecta Dot, no concede permisos y no crea automatizaciones. Cada integración debe verificarse en el producto.

## 3. Flujo estándar de un encargo

1. **Entrada:** el usuario comunica el objetivo, no una secuencia de microinstrucciones.
2. **Contexto:** ChatGPT revisa memoria pertinente, repositorios, archivos, conversaciones y herramientas autorizadas.
3. **Plan interno:** descompone el trabajo, asigna responsables y define qué evidencia demostrará el éxito. No necesita exponer un plan largo antes de actuar.
4. **Ejecución:** ChatGPT, bots y automatizaciones realizan sus partes; los pasos independientes pueden ejecutarse en paralelo.
5. **Integración:** ChatGPT reúne resultados, resuelve incompatibilidades y completa tareas no cubiertas.
6. **Verificación:** relee archivos, valida estructuras, comprueba enlaces/commits, ejecuta pruebas o consulta el estado real del servicio.
7. **Registro:** actualiza el repositorio o sistema de fuente de verdad cuando corresponda.
8. **Reporte:** entrega qué se hizo, evidencia, enlaces, resultados, riesgos y pendientes reales.

## 4. Regla de no intervención innecesaria

No solicitar al usuario que impulse cada paso. No detenerse para preguntar si debe continuar cuando continuar sea la consecuencia normal del objetivo.

Antes de preguntar:
- buscar el dato en el contexto y los archivos;
- consultar las herramientas y conectores disponibles;
- probar una alternativa segura;
- avanzar con las partes independientes.

Preguntar únicamente por decisiones que cambien materialmente el resultado y que solo el usuario pueda tomar. Ejemplos: elegir entre alternativas creativas incompatibles, autorizar un gasto, aprobar una publicación, conceder permisos, aceptar una acción destructiva o resolver una ambigüedad que no admita un supuesto seguro.

## 5. Límites de autonomía

La autonomía no significa actuar sin control. Requieren autorización específica cuando no exista permiso previo:
- compras, pagos, suscripciones o compromisos financieros;
- publicaciones, mensajes o comunicaciones externas en nombre del usuario;
- eliminación o sobrescritura destructiva;
- cambios de permisos, exposición de datos o manejo de secretos;
- decisiones legales, médicas, financieras o de alto impacto;
- cambios en motores/archivos canónicos protegidos.

Mientras espera una decisión, ChatGPT debe seguir trabajando en todo lo demás que no dependa de ella.

## 6. Reportes

Los reportes forman parte del servicio y no son sustituto de la ejecución.

**Reporte breve de tarea:**
- Resultado.
- Artefactos y enlaces.
- Evidencia de verificación.
- Pendientes reales o decisiones necesarias.

**Reporte de trabajo prolongado:**
- Hitos con resultados parciales comprobados.
- Cambios y entregables.
- Incidencias y cómo se resolvieron.
- Riesgos o bloqueos que requieren intervención.
- Próximas acciones que continuarán automáticamente si están autorizadas.

No enviar mensajes vacíos como «estoy trabajando», ni anunciar tareas que todavía no se han ejecutado.

## 7. Delegación y control de calidad

Cada delegación debe especificar:
- objetivo y entregable;
- fuente de verdad;
- alcance y restricciones;
- formato esperado;
- evidencia requerida;
- responsable de revisión.

Al recibir el resultado, ChatGPT verifica:
- que el artefacto exista;
- que corresponda al encargo;
- que cumpla estructura y criterios;
- que las fuentes y datos sean trazables;
- que no viole restricciones del proyecto.

Si falla, solicita corrección al agente o la realiza directamente cuando esté autorizado. Reporta el resultado final, no la mera delegación.

## 8. Continuidad y transferencia

- Mantener las decisiones estables y procedimientos en este repositorio.
- Registrar las automatizaciones y agentes activos con identificador, objetivo, horario, última ejecución y estado comprobado cuando esos datos estén disponibles.
- Distinguir integraciones existentes, configuraciones propuestas y capacidades no disponibles.
- Antes de una migración, actualizar los documentos con el estado real y la fecha.
- La instancia nueva debe leer este protocolo antes de iniciar tareas.
- No guardar contraseñas, tokens privados ni credenciales en el repositorio.

## 9. Criterio de éxito

El usuario puede comunicar un objetivo y recibir un resultado completo, comprobado y documentado sin dirigir cada paso intermedio. La intervención del usuario se reserva para decisiones que realmente le pertenecen.

## 10. Smoke test de integración (2026-10-31)

### GitHub: PASS
- Se creó temporalmente `smoke/2026-10-31-autonomia-dot-bot.txt` en `main` usando la conexión autorizada.
- Se leyó de vuelta y el contenido coincidió exactamente.
- Se eliminó el archivo temporal y una lectura posterior devolvió HTTP 404, confirmando que ya no existe.
- Commits de prueba: creación `b865109cb670f3afb3976bdc5a9beb49da12c12d`; eliminación `74e771681b87247e320346c149cf021fe0149ef3`.

### Automatizaciones: conexión comprobada; ejecución inmediata pendiente de confirmación
- Se consultaron por ID las automatizaciones `Agente de investigación CAPCOT` y `Tercera cápsula CAPCOT`. Ambas devuelven configuración y estado `is_enabled=true`.
- La última ejecución registrada del agente de investigación figura `completed`, con salida y commits reportados. La última ejecución registrada de la tercera cápsula también figura `completed`, con entrega y limitaciones documentadas.
- Se solicitó una ejecución inmediata de `Agente de investigación CAPCOT`; el servicio confirmó que la solicitud fue aceptada y que el horario guardado no cambió. La consulta posterior todavía devolvió el historial anterior, por lo que esta ejecución nueva no se marca como completada.

### Dot: no integrado en esta sesión
- No hay una acción/herramienta de Dot expuesta a esta sesión y el intento de notificación al padre devolvió `NOT_FOUND`; no se produjo un handoff verificable.
- La documentación oficial consultada indica despliegue gradual de Dots para ChatGPT Pro (18+, fuera del EEE, Suiza y Reino Unido), Business Premium y Enterprise habilitado por administrador; Go no aparece entre los planes elegibles publicados. Por tanto, con el plan Go que figura en el contexto de esta sesión, no se puede dar por disponible ni activar Dot desde aquí.
- Referencia oficial: https://help.openai.com/es-419/articles/20001530-getting-started-with-your-dot
- Para que Dot participe orgánicamente hará falta que la función esté habilitada en la cuenta, crear el dot desde la app y conectar GitHub con los permisos necesarios. Después se debe probar lectura, escritura controlada y devolución de resultados desde el propio dot.

### Resultado global
- GitHub escritura/lectura/borrado: **PASS**.
- Lectura de estado de automatizaciones: **PASS**.
- Ejecución inmediata de automatización: **aceptada, resultado aún no confirmado**.
- Dot y handoff ChatGPT↔Dot: **NOT WIRED**.

