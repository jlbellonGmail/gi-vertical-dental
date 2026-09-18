# Reglas del dominio dental

- No inventar tratamientos, diagnósticos, precios, textos legales ni datos
  clínicos reales.
- No guardar credenciales ni crear conexiones directas a Supabase dentro de
  las reglas del dominio.
- No duplicar identidad, tenancy, roles, permisos, aislamiento o auditoría
  que pertenecen a `gi-platform-core`.
- No incluir UI, branding de Sonríe+ ni comportamiento de landing.
- No transformar leads públicos en pacientes sin un caso de uso explícito,
  consentimiento y contrato con ClínicaDental.
- Separar datos administrativos de historia clínica y restringir cada caso de
  uso al contexto Organization/Site autorizado.