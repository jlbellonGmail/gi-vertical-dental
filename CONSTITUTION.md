# Constitución — GI-VERTICAL-DENTAL

## Propósito

Esta constitución fija los principios permanentes del dominio dental
reutilizable. El detalle operativo vive en `AGENTS.md`; el trabajo pendiente,
en `ROADMAP.md`.

## Principios

1. **Contratos antes que acoplamiento.** La vertical expone contratos públicos
   versionados y no depende de una UI concreta.
2. **Core común.** Identity, Organization, Site, memberships, permisos
   genéricos, aislamiento y auditoría se consumen desde `gi-platform-core`.
3. **Datos con dueño.** Ningún módulo escribe directamente tablas privadas de
   otro módulo.
4. **Seguridad server-side.** La UI ayuda; el servidor decide autorización,
   invariantes y estados.
5. **Separación clínica-administrativa.** La historia clínica no se mezcla con
   captación ni con datos operativos sin permisos explícitos.
6. **Privacidad por defecto.** Se solicita y expone la mínima información
   necesaria para cada caso de uso.
7. **MVP incremental.** Cada unidad debe ser pequeña, utilizable y ampliable.
8. **Evidencia real.** No se declara una capacidad implementada sin tests,
   contratos y verificación reproducible.
9. **Independencia de la experiencia.** Branding, navegación y canales son
   responsabilidad de cada producto consumidor.
10. **No invención.** El agente no inventa diagnósticos, tratamientos, precios,
    certificaciones, textos legales ni datos reales.