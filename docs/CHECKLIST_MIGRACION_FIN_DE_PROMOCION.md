# Checklist de continuidad antes del fin de la promoción
Corte inicial: 2026-11-03. Objetivo: una sesión nueva debe poder continuar sin depender de este chat.

## Estado
- [x] Repositorio privado ChatGPT-migracion localizado y accesible.
- [x] README y documentos iniciales conservados.
- [x] Repositorios U6 y CAPCOT localizados con acceso GitHub.
- [x] Ramas de autoridad identificadas: U6 main; CAPCOT feature/capcot-video-discovery-continuity.
- [x] Restricciones canónicas U6 y compuertas CAPCOT recuperadas.
- [x] Mapa operativo de herramientas por proyecto creado.
- [x] Protocolo de memoria compartida entre modelos creado.
- [x] Plantilla de handoff y bandeja documentadas.
- [ ] Probar un handoff real entre dos modelos/cuentas y registrar acuse.
- [ ] Confirmar que la segunda sesión puede leer los tres repositorios con la cuenta GitHub correcta.
- [ ] Revalidar automatizaciones y resolver next_run_time null si persiste.
- [ ] Reconectar vidIQ con la cuenta que administra Datos y ociosidades; ahora devuelve cero canales para marcosabines@gmail.com.
- [ ] Confirmar cuenta/Brand Kit de Canva.
- [ ] Confirmar workspace, workflows y créditos de Runway.
- [ ] Confirmar si Dropbox es parte de continuidad o almacenamiento auxiliar.
- [ ] Decidir si se conecta instancia n8n; actualmente hay skill para JSON, no conector directo.
- [ ] Decidir si orquestador-central entra al alcance; por ahora solo lectura.

## Prueba de recuperación
Una sesión nueva debe poder:
1. Leer este repo y reconstruir reglas/estado.
2. Identificar U6 y CAPCOT como proyectos separados.
3. Encontrar ramas correctas y documentos de arranque.
4. Explicar qué puede ejecutar con las conexiones disponibles.
5. Localizar último reporte, commit y pendientes de cada proyecto.
6. No tocar archivos canónicos, duplicar cápsulas ni atribuir ejecuciones no verificadas.
7. Guardar un reporte de recuperación con evidencia y conectores que requieran reconexión.

## Conexiones observadas el 2026-11-03
| Servicio | Resultado | Acción |
|---|---|---|
| GitHub marcojpad-hash | Acceso a ChatGPT-migracion, motor-u6-storage, capcot-capsulas-imaginantes y orquestador-central. | Reautorizar si no aparece en nueva sesión. |
| GitHub marcosabines-hash | Sin instalaciones/repositorios devueltos. | No usar como cuenta de trabajo hasta corregir. |
| vidIQ | marcosabines@gmail.com; cero canales. | Reconectar cuenta correcta y verificar canal. |
| Dropbox | marco.jp@live.com.mx. | Confirmar que es la cuenta deseada. |
| Notion | Workspace disponible; usuario owner de un teamspace. | Contexto auxiliar; GitHub prevalece. |
| Floot | Cero proyectos. | No hay runner/app configurado. |
| Canva | Cero Brand Kits. | Confirmar cuenta y kit. |
| Runway | Cero workflows guardados. | Confirmar workspace, créditos y recursos antes de gastar. |
| Undermind | Cero workspaces. | Crear solo si sirve a investigación concreta. |
| n8n | Skill disponible; conector directo no localizado. | Conectar instancia para importar/ejecutar remotamente. |

## Criterio de cierre
La migración está lista cuando una sesión nueva reconstruye el estado y continúa ambos proyectos desde GitHub y se comprueban las conexiones esenciales. Documentación no prueba transferencia de permisos ni ejecución de automatizaciones.