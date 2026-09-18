# Contrato de integración Core–Vertical–ClínicaDental

## Frontera

```text
SISTEMA INTEGRAL
  arquitectura global y contratos modulares
        |
GI-PLATFORM-CORE
  identity, Organization, Site, membership, permisos, aislamiento, auditoría
        |
GI-VERTICAL-DENTAL
  capacidades y reglas odontológicas
        |
GI-CLINICADENTAL
  composición, UI/UX, marca, canales y leads
```

## Reglas

- La vertical consume solo contratos públicos del Core.
- El Core no importa ni conoce tipos dentales.
- ClínicaDental consume la vertical y no copia sus reglas.
- `public.leads` permanece en ClínicaDental.
- La vertical no abre conexiones propias a Supabase.
- La aplicación anfitriona proporciona identidad, persistencia y adaptadores.
- Toda operación dental se evalúa con Organization y Site cuando corresponda.
- Las capacidades y permisos dentales se identifican con namespace propio.
- Los eventos y reintentos deben ser idempotentes.

## Primera tarea funcional

La primera unidad debe convertir este contrato en interfaces y pruebas de
contrato, sin construir todavía pacientes, agenda ni historia clínica. Debe
comprobar que una aplicación anfitriona puede:

1. recibir un `TenantContext` del Core;
2. invocar una capacidad dental versionada;
3. obtener una respuesta y errores estables;
4. registrar autorización y auditoría a través del Core;
5. mantener aisladas dos Organizations.

## Criterio de no acoplamiento

Una prueba válida debe poder sustituir el transporte y el adaptador de datos
sin modificar la regla dental. ClínicaDental podrá cambiar su UI sin cambiar
este contrato.