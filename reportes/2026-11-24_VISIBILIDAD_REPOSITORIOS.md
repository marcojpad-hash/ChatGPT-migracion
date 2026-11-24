# Inventario de cuentas y visibilidad GitHub — 2026-11-24

## Cuentas e instalaciones consultadas
- Cuenta conectada `marcojpad-hash`: una instalación GitHub con selección `all`; devolvió 11 repositorios visibles.
- Cuenta conectada `marcosabines-hash`: cero cuentas instaladas, cero instalaciones y cero repositorios devueltos. No se infiere que no existan repositorios fuera de esa instalación.
- No hubo error de consulta; el segundo resultado fue una lista vacía.

## Repositorios devueltos

| Repositorio | Visibilidad GitHub | Clasificación |
|---|---|---|
| `marcojpad-hash/ChatGPT-migracion` | public | principal |
| `marcojpad-hash/capcot-capsulas-imaginantes` | public | principal |
| `marcojpad-hash/motor-u6-storage` | public | principal |
| `marcojpad-hash/memoria-compartida` | public | adicional; solo lectura |
| `marcojpad-hash/orquestador-central` | public | adicional; solo lectura |
| `marcojpad-hash/red-teaming-safety-u6` | private | adicional; solo lectura |
| `marcojpad-hash/agente-cero-costo` | public | adicional; solo lectura |
| `marcojpad-hash/baterias-tokens` | public | adicional; solo lectura |
| `marcojpad-hash/baterias-memoria` | public | adicional; solo lectura |
| `marcojpad-hash/microserie-heredera-sadtalker` | public | adicional; solo lectura |
| `marcojpad-hash/microserie-heredera-voces` | public | adicional; solo lectura |

## Discrepancias de privacidad verificadas
La matriz `memoria-compartida/hechos/proyectos.md` clasifica como privados `ChatGPT-migracion`, `motor-u6-storage`, `memoria-compartida`, `baterias-tokens` y `baterias-memoria`. GitHub los devuelve como `public`. Son cinco discrepancias concretas.

Coincidencias observadas:
- `capcot-capsulas-imaginantes`: público, conforme a la clasificación del proyecto.
- `orquestador-central`: público, conforme a la clasificación del proyecto.
- `agente-cero-costo`: público, conforme a la clasificación del proyecto.
- `red-teaming-safety-u6`: privado, conforme a la clasificación del proyecto.
- Los dos repositorios `microserie-heredera-*` se registran como adicionales; no se encontró una clasificación de privacidad explícita en la matriz consultada.

## Acción aplicada
- No se cambiaron permisos ni visibilidad.
- No se escribieron datos operativos en los cinco repositorios con discrepancia.
- Los ocho repositorios adicionales permanecen en solo lectura; no se crearon ramas, issues, PRs ni commits en ellos.
- Este documento contiene solo metadatos públicos de repositorio y el resultado de la consulta de visibilidad; no incluye secretos, valores de webhook, custodias ni datos de casos.
