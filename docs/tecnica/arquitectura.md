# Arquitectura — GI-VERTICAL-DENTAL

## Responsabilidad

Este repositorio implementará el dominio dental como una pieza reutilizable.
No es una aplicación web completa y no es el dueño de la infraestructura de
identidad o persistencia transversal.

## Dependencias

```text
Producto / UI
    -> contratos de ClínicaDental
    -> contratos de GI-Vertical-Dental
    -> contratos de GI-Platform-Core
    -> adaptadores de la aplicación anfitriona
```

La dirección nunca se invierte. El Core no importa Dental y Dental no importa
ClínicaDental.

## Fronteras de datos

- `core.*`: propiedad de `gi-platform-core`.
- `dental.*`: propiedad de este repositorio cuando se incorporen datos
  persistentes.
- `public.leads`: propiedad de `gi-clinicadental`; queda fuera del vertical.

Ningún módulo consulta o actualiza directamente tablas privadas de otro. La
comunicación se realiza mediante contratos de aplicación, APIs o eventos
versionados.

## Seguridad

La vertical recibe identidad y `TenantContext` del Core anfitrión. Todas las
operaciones deben verificar Organization, Site cuando aplique, permiso dental
y estado de la entidad. La vertical no crea un sistema paralelo de roles,
permisos, RLS o auditoría.

## Separación de capas

- Contratos: entradas, salidas, errores y versión pública.
- Aplicación: casos de uso dentales.
- Dominio: entidades e invariantes odontológicas.
- Puertos: interfaces para persistencia, reloj, eventos y servicios externos.
- Adaptadores: responsabilidad de la aplicación anfitriona o de módulos
  explícitamente versionados.
- UI: responsabilidad de ClínicaDental u otro consumidor.

## Evolución

La primera implementación será pequeña y transport-neutral. Las decisiones
sobre Supabase, HTTP, colas o despliegue se documentarán en el consumidor o
en un contrato específico; no se asumen aquí por herencia del template.