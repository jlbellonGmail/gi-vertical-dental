# Estado operativo

Estado general: GI-Vertical-Dental quedo en su punto inicial propio, limpio de historial y documentacion de producto heredados de la plantilla. El repositorio conserva unicamente el circuito operativo reutilizable, sus pruebas, el framework normativo y la base documental necesaria para construir el dominio dental.

## Alcance inicial

- Proposito y limites del vertical definidos en GOAL.md.
- Arquitectura alineada con gi-platform-core y gi-clinicadental.
- Primer trabajo funcional preparado como 01-contrato-vertical-dental en ROADMAP.md.
- Contrato de integracion documentado en docs/tecnica/contrato-integracion-core.md.
- Sin UI, marca, landing, public.leads, SMTP, autenticacion propia ni persistencia duplicada en este repositorio.

## Evidencia real

- Rama local: codex/vertical-dental-baseline.
- HEAD local: commit de baseline vigente, verificado por Git.
- Remoto Git: `origin` configurado a
  `https://github.com/jlbellonGmail/gi-vertical-dental.git`; no se hizo push.
- Worktrees: sin unidades de trabajo activas.
- Limpieza historica: eliminados los artefactos fechados de .audit, runs y la documentacion de fases de la plantilla; se conservaron .audit normativo y runs/.gitkeep.
- Repositorios externos: gi-platform-core, gi-clinicadental y template solo fueron consultados; no fueron modificados.

## Validacion

- Suite completa: 255 pasadas y 7 omitidas antes del ajuste final del fixture de status; el fallo era ambiental por repositorio padre. El fixture quedo corregido para aislar una raiz no Git.
- El caso de destino archivo y la auditoria del perfil vertical pasan de forma aislada.
- La validacion de repositorios Git anidados queda limitada por permisos del entorno; el fixture de status ya prueba explicitamente una raiz no Git.
- git diff --check: correcto.
- MkDocs no esta disponible en el entorno local; queda para el workflow de documentacion cuando se instalen requirements-docs.txt.

## Proximo paso exacto

Iniciar 01-contrato-vertical-dental: declarar contratos publicos, permisos con namespace dental, errores estables, integracion de TenantContext/auditoria de Core y pruebas de aislamiento entre organizaciones. No crear todavia pacientes, agenda ni historia clinica.

## Estado de trabajo

Este archivo se actualiza antes de cada entrega. La evidencia de verdad sigue siendo el contenido del repositorio, Git y las pruebas ejecutadas.

<!-- STATUS:AUTO:BEGIN -->
## Estado verificado automaticamente

- Rama: codex/vertical-dental-baseline
- HEAD: d0db39eb7bd9bc1fe942aa592dae8ff16f7b5a64
- Plataforma: ai-native v3.1.1
<!-- STATUS:AUTO:END -->
