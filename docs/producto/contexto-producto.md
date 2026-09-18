# Contexto de producto — GI-VERTICAL-DENTAL

## Propósito

Proveer un dominio dental reutilizable para aplicaciones que gestionan una
clínica, sus sedes, profesionales, pacientes, disponibilidad y turnos.

## Usuarios y consumidores

- `gi-clinicadental`: primer consumidor y producto de referencia.
- Futuros productos odontológicos: consumidores potenciales.
- El Core: dependencia técnica, nunca consumidor de reglas dentales.

## Límites

La vertical administra reglas odontológicas. La identidad, tenancy,
Organizations, Sites, memberships, permisos genéricos, aislamiento y
 auditoría transversal pertenecen a `gi-platform-core`.

ClínicaDental conserva la UI, la experiencia de marca, `public.leads`, correo
y despliegue. La vertical no debe exigir que un lead público tenga una
Organization ni convertirlo en paciente automáticamente.

## Reglas adoptadas

- Una clínica se representa como una Organization del Core.
- Una sede se representa como un Site del Core.
- Los roles y permisos dentales usan el mecanismo del Core.
- Toda operación server-side recibe contexto de Organization y Site cuando
  corresponde.
- El dominio clínico y el administrativo se mantienen separados.
- Cada dato tiene un dueño; no se escriben tablas privadas de otro módulo.
- La UI puede cambiar sin cambiar las reglas del dominio.
- La aplicación anfitriona proporciona persistencia, identidad y adaptadores.

## Primera entrega

La primera entrega no intenta construir una clínica completa. Define el
contrato del vertical, sus capacidades y la integración verificable con el
Core para que ClínicaDental pueda avanzar de forma incremental.