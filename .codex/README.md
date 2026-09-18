# Perfiles de agentes

`AGENTS.md` es la fuente normativa del circuito del vertical. Las definiciones
canónicas de roles viven en `.agentic/roles/`; este directorio solo conserva
la configuración específica de Codex.

Perfiles disponibles:

- `planner`: interpreta el alcance y prepara la estrategia.
- `builder`: implementa dentro del alcance y ejecuta verificaciones.
- `reviewer`: valida de forma independiente intención, diff, tests y evidencia.

Regenerar adaptadores desde la raíz:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\scripts\sync-agentic-adapters.ps1
powershell -NoProfile -ExecutionPolicy Bypass -File .\scripts\sync-agentic-adapters.ps1 -Check
```

No editar perfiles generados manualmente.