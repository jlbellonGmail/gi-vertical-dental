# Estado operativo

Estado general: GI-Vertical-Dental quedo en su punto inicial propio, limpio de historial y documentacion de producto heredados de la plantilla. El repositorio conserva unicamente el circuito operativo reutilizable, sus pruebas, el framework normativo y la base documental necesaria para construir el dominio dental.

## Alcance inicial

- Proposito y limites del vertical definidos en GOAL.md.
- Arquitectura alineada con gi-platform-core y gi-clinicadental.
- Primer trabajo funcional preparado como 01-contrato-vertical-dental en ROADMAP.md.
- Contrato de integracion documentado en docs/tecnica/contrato-integracion-core.md.
- Sin UI, marca, landing, public.leads, SMTP, autenticacion propia ni persistencia duplicada en este repositorio.

## Evidencia real

- Rama local: chore/limpieza-historial-template.
- HEAD local: fa4433c (chore: establish vertical dental baseline).
- Remoto Git: no configurado; no se hizo push.
- Worktrees: sin unidades de trabajo activas.
- Limpieza historica: eliminados los artefactos fechados de .audit, runs y la documentacion de fases de la plantilla; se conservaron .audit normativo y runs/.gitkeep.
- Repositorios externos: gi-platform-core, gi-clinicadental y template solo fueron consultados; no fueron modificados.

## Validacion

- Suite completa: 257 pasadas, 7 omitidas y 3 fallos heredados del circuito.
- El caso de destino archivo paso de forma aislada.
- Dos fallos restantes son ambientales o de fixture: repositorio Git anidado sin permiso de escritura y prueba que ejecuta dentro de un subdirectorio del repositorio principal.
- git diff --check: correcto.
- MkDocs no esta disponible en el entorno local; queda para el workflow de documentacion cuando se instalen requirements-docs.txt.

## Proximo paso exacto

Iniciar 01-contrato-vertical-dental: declarar contratos publicos, permisos con namespace dental, errores estables, integracion de TenantContext/auditoria de Core y pruebas de aislamiento entre organizaciones. No crear todavia pacientes, agenda ni historia clinica.

## Estado de trabajo

Este archivo se actualiza antes de cada entrega. La evidencia de verdad sigue siendo el contenido del repositorio, Git y las pruebas ejecutadas.