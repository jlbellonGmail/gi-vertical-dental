# AGENTS — GI-VERTICAL-DENTAL

## Identidad

Este repositorio contiene el dominio dental reutilizable del Sistema
Integral. No es el template ni la aplicación visible de Sonríe+.

La dependencia válida es:

```text
gi-clinicadental -> gi-vertical-dental -> gi-platform-core
```

`gi-platform-core`, `gi-clinicadental`, `template` y el proyecto de diseño
`SISTEMA INTEGRAL` son fuentes externas de lectura cuando una tarea lo
requiera. Este repositorio es el único espacio de escritura autorizado para
el trabajo del vertical.

## Responsabilidades

La vertical define reglas, contratos, casos de uso, eventos, puertos y
validaciones propios del dominio dental. No define UI de Sonríe+, landing,
SMTP, `public.leads`, infraestructura de Supabase ni tenancy genérico.

El Core es dueño de identidad, Organization, Site, memberships, roles,
permisos genéricos, TenantContext, aislamiento y auditoría transversal. La
vertical consume esas capacidades mediante contratos públicos y nunca las
duplica.

ClínicaDental es dueña de la composición del producto, la experiencia, la
marca, los canales y `public.leads`. La vertical no depende de sus archivos ni
de su UI.

## Reglas de dominio

- No inventar tratamientos, diagnósticos, precios, certificaciones, textos
  legales ni datos clínicos reales.
- No guardar secretos ni credenciales.
- No crear una conexión propia a Supabase dentro del dominio.
- No acceder directamente a tablas privadas del Core o de ClínicaDental.
- No transformar un lead público en paciente sin un caso de uso explícito,
  consentimiento y contrato de integración.
- Separar información administrativa de historia clínica.
- Toda operación sensible debe recibir y validar el contexto Organization/Site
  y el permiso dental correspondiente.

## Arquitectura

La separación mínima es:

```text
contratos -> aplicación -> dominio -> puertos -> adaptadores
```

La UI y los transportes son consumidores. El dominio no depende de ellos.
Cada módulo es dueño de sus datos y se comunica con otros módulos mediante
contratos versionados o eventos idempotentes.

## Circuito de trabajo

Las features siguen el circuito operativo disponible en `scripts/`:

1. definir el item en `ROADMAP.md`;
2. analizar y especificar alcance, plan y tareas;
3. revisar la especificación;
4. implementar código y documentación;
5. ejecutar QA y contrato;
6. revisar el diff final;
7. preparar PR y esperar CI;
8. la decisión humana final es MERGE o NO MERGE.

Los artefactos de una feature nueva viven en `runs/<slug>/` o en la ruta
versionada que indique la configuración vigente. No se copian ejecuciones
históricas de otro repositorio.

## Documentación

- `GOAL.md` define el propósito estable del vertical.
- `ROADMAP.md` define únicamente el backlog dental.
- `STATUS.md` resume el estado verificable de este checkout.
- `docs/producto/contexto-producto.md` contiene reglas funcionales estables.
- `docs/tecnica/arquitectura.md` contiene decisiones técnicas del vertical.
- `.claude/rules/` contiene reglas adicionales de dominio.

## Git y cambios

No hacer push, crear remotos ni modificar repositorios externos salvo pedido
explícito. No commitear directamente a `develop` para una feature; usar una
rama de trabajo y conservar el diff revisable. Antes de devolver control,
actualizar `STATUS.md`, comprobar el estado real de Git y declarar las
limitaciones verificables.

## Calidad

Los tests del circuito se ejecutan con `pytest`. Las pruebas de dominio y de
contrato se agregan junto con cada feature. No declarar una feature terminada
sin evidencia de reglas, permisos, aislamiento, contratos y regresión.