# Estado operativo

Versión: v2.0.0  
Estado general: repositorio vertical dental inicializado desde Template v2.0.0 y limpiado de evidencias históricas de la construcción de la plantilla. Se conserva el circuito operativo, el framework `.audit` normativo, la documentación base, los tests y `runs/.gitkeep`.

## Próximas fases

- Definir el alcance funcional de la vertical dental.
- Declarar sus contratos de dominio y dependencia de `gi-platform-core`.
- Integrar los módulos resultantes en `gi-clinicadental`, sin duplicar Core ni UI de producto.

Próximo paso exacto: crear la primera unidad funcional dental con evidencia nueva y reglas de dominio explícitas.

## Evidencia real

- Rama local: `chore/limpieza-historial-template`.
- HEAD local: `b0a83d4` (`chore: remove inherited template history`).
- Remoto Git: no configurado (`origin` inexistente).
- Worktrees: 1.
- Working tree: limpio.
- Limpieza: 346 archivos históricos eliminados; framework `.audit` y `runs/.gitkeep` conservados.
- Validación: 31 tests del circuito pasaron usando una carpeta temporal dentro del repositorio. La ejecución sin esa opción fue bloqueada por permisos de la carpeta temporal global de Python.

## Incidencias

`scripts/update-status.ps1` falla en este checkout sin remoto con un error de valor NULL; este estado se mantiene actualizado manualmente hasta corregir ese caso en una tarea separada.

<!-- STATUS:AUTO:BEGIN -->

## Estado verificado automáticamente

- Actualizado: 2026-09-18T00:00:00Z
- Versión: v2.0.0
- Rama: chore/limpieza-historial-template
- HEAD: b0a83d4
- Remoto: UNKNOWN / sin remoto
- Working tree: clean
- Worktrees: 1
- Worktrees Git: 1
- Unidades activas: ninguna
- PR activa: UNKNOWN / sin PR abierta
- CI: UNKNOWN / sin CI verificable
- CI vigente: UNKNOWN / sin CI verificable
- Última release: UNKNOWN / no disponible

<!-- STATUS:AUTO:END -->