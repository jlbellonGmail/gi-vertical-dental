# ROADMAP — GI-VERTICAL-DENTAL

Este roadmap pertenece exclusivamente al dominio dental. El circuito
agéntico heredado de la plantilla se usa para trabajar, pero sus fases,
intervenciones y evidencias históricas no forman parte de este producto.

Los estados significan: `[ ]` pendiente, `[-]` listo para PR y `[x]`
completado después del merge a `develop`.

## v0.1.0 — Fundación del vertical

- [ ] 01-contrato-vertical-dental — Definir propósito, límites, dependencias,
  contratos públicos, versionado, eventos y ownership de datos.
- [ ] 02-capacidades-y-permisos-dentales — Definir capacidades namespaced y
  roles iniciales sobre autorización del Core, sin crear un RBAC paralelo.
- [ ] 03-integracion-core — Consumir los contratos públicos del Core para
  identidad, Organization, Site, TenantContext, autorización y auditoría.
- [ ] 04-configuracion-clinica — Modelar la configuración dental mínima:
  servicios, especialidades, sedes operativas y reglas de atención.
- [ ] 05-actores-administrativos — Modelar perfiles administrativos de
  profesionales y pacientes sin incluir todavía historia clínica.
- [ ] 06-agenda-y-disponibilidad — Definir disponibilidad, horarios,
  bloqueos, ausencias y duración como dominio dental reutilizable.
- [ ] 07-turnos — Implementar reservar, confirmar, reprogramar, cancelar y
  trazabilidad usando la disponibilidad definida por el vertical.
- [ ] 08-integracion-clinicadental — Validar que ClínicaDental consume el
  vertical sin copiar reglas ni acoplar UI, conservando `public.leads`.

## Evolución posterior

- [ ] 09-captacion-y-seguimiento — Convertir consultas en tareas, pacientes
  o turnos mediante contratos explícitos.
- [ ] 10-historia-clinica-y-consentimientos — Separar y proteger datos
  clínicos con permisos profesionales y auditoría reforzada.
- [ ] 11-odontograma-y-tratamientos — Agregar odontograma, planes,
  tratamientos y evolución versionada.
- [ ] 12-documentos-clinicos — Gestionar adjuntos y documentos con acceso
  temporal, retención y trazabilidad.

## Reglas del roadmap

- No se marca un item como `[x]` antes de su merge.
- Cada item debe declarar su contrato con Core y su impacto en ClínicaDental.
- La vertical no incorpora UI de producto ni infraestructura de Supabase por
  cuenta propia; la aplicación anfitriona proporciona esos adaptadores.
- Las carencias genéricas se corrigen en `gi-platform-core`, no aquí.