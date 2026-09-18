@AGENTS.md

# Principios del vertical

1. El dominio dental debe poder consumirse desde más de una interfaz.
2. Las reglas críticas viven en casos de uso server-side, no en la UI.
3. Cada dato tiene un módulo dueño y las integraciones usan contratos.
4. Identity, tenancy, permisos genéricos, aislamiento y auditoría pertenecen
   al Core.
5. La vertical no conoce la marca ni la implementación interna de
   ClínicaDental.
6. Los cambios se mantienen pequeños, verificables y reversibles.
7. No se inventan datos médicos, legales o comerciales.