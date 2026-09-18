# GI-Vertical-Dental

Dominio dental reutilizable para el Sistema Integral.

Este repositorio no es la aplicación visible de Sonríe+. Su función es
contener reglas y contratos odontológicos que puedan ser consumidos por
`gi-clinicadental` y por futuros productos del mismo dominio.

## Arquitectura

```text
SISTEMA INTEGRAL
        |
        v
GI-PLATFORM-CORE
        |
        v
GI-VERTICAL-DENTAL
        |
        v
GI-CLINICADENTAL
```

En términos de dependencias:

- `gi-platform-core` es el núcleo común y no conoce Dental.
- `gi-vertical-dental` depende de los contratos públicos del Core.
- `gi-clinicadental` compone ambos y mantiene UI/UX, marca, landing y leads.
- Ningún módulo accede directamente a tablas privadas de otro módulo.

## Qué debe vivir aquí

Reglas dentales, capacidades, contratos de casos de uso, eventos, validación
de dominio y políticas propias de la atención odontológica.

## Qué no debe vivir aquí

La interfaz de Sonríe+, `public.leads`, SMTP, la autenticación del proveedor,
las tablas `core.*`, secretos, despliegue de ClínicaDental o reglas de otros
verticales.

## Cómo trabajar

Leer primero [GOAL.md](GOAL.md), [ROADMAP.md](ROADMAP.md), [STATUS.md](STATUS.md)
y [AGENTS.md](AGENTS.md). El circuito agéntico es infraestructura de trabajo;
el objetivo del producto está definido por este repositorio y sus contratos.