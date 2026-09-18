# Audit Profile - VERTICAL-DENTAL

**Estado:** Activo
**Tipo de proyecto:** dominio vertical reutilizable
**Depende de:** QUALITY_SCORE.md y AUDIT_RULES.md
**Propósito:** validar que este repositorio conserve límites claros, contratos estables e integración segura con GI-Platform-Core y GI-Clinicadental.

## Alcance de la auditoría

La auditoría verifica:

- identidad y propósito del dominio dental;
- dependencia unidireccional `gi-clinicadental -> gi-vertical-dental -> gi-platform-core`;
- separación entre reglas dentales, infraestructura Core y composición de producto;
- contratos públicos, permisos namespaced, contexto Organization/Site, aislamiento y auditoría;
- ausencia de UI, marca, leads, SMTP, autenticación o persistencia duplicada que pertenezcan al producto consumidor;
- documentación, pruebas y evidencias del circuito operativo;
- ausencia de secretos, datos clínicos reales y residuos de otros productos o plantillas.

## Regla de evidencia

Una capacidad se considera presente sólo si existe en el código, documentación, configuración o pruebas del repositorio y puede verificarse sin depender de conversaciones externas. Los elementos planificados permanecen en `ROADMAP.md` y no se presentan como implementados.

## Límites

Este perfil no inventa reglas médicas, legales, clínicas, de privacidad o negocio. Si una decisión material no está respaldada por una instrucción vigente o evidencia del sistema, se registra como pendiente y no se autoaprueba.