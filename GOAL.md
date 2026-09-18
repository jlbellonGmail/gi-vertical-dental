# GOAL — GI-VERTICAL-DENTAL

## Propósito

Construir un dominio dental reutilizable que pueda ser consumido por
`gi-clinicadental` y, en el futuro, por otros productos odontológicos.

## Relación con el sistema

```text
SISTEMA INTEGRAL
  define la arquitectura global y los contratos modulares

GI-PLATFORM-CORE
  ofrece identidad, Organizations, Sites, memberships, permisos,
  autorización contextual, aislamiento y auditoría

GI-VERTICAL-DENTAL
  ofrece reglas, contratos y capacidades propias del dominio dental

GI-CLINICADENTAL
  compone Core + Vertical Dental + UI/UX de Sonríe+
```

La dirección de dependencia permitida es:

```text
gi-clinicadental -> gi-vertical-dental -> gi-platform-core
```

El Core nunca depende de este vertical. La vertical nunca depende de la UI
ni de la marca de ClínicaDental.

## Alcance inicial

La primera versión debe definir y demostrar:

- contratos públicos del dominio dental;
- capacidades y permisos dentales namespaced;
- integración con `TenantContext`, Organization, Site y auditoría del Core;
- separación entre datos administrativos y datos clínicos;
- una base preparada para configuración de clínicas, profesionales,
  pacientes y agenda.

## Fuera de alcance inicial

No se implementan todavía en este repositorio la landing, `public.leads`,
SMTP, UI de Sonríe+, autenticación propia, persistencia duplicada del Core,
chatbot, voz, facturación ni reglas de otros dominios.

## Criterio de éxito

ClínicaDental puede consumir capacidades dentales versionadas, mantener su
experiencia propia y ejecutar operaciones autorizadas dentro de una
Organization/Site sin que la vertical conozca la infraestructura concreta ni
repita tenancy, RBAC, aislamiento o auditoría del Core.