# 06-sonarqube-governance

## Objetivo
Establecer gobierno de SonarQube para mantener calidad de codigo, deuda tecnica controlada y gates auditables.

## Contexto
El analisis estatico aporta valor solo cuando sus reglas estan alineadas al negocio y se integran al flujo de entrega. Sin governance, SonarQube se vuelve decorativo.

## Trade-offs
- Reglas estrictas elevan calidad, con potencial impacto en velocidad.
- Perfiles por lenguaje mejoran precision, con mayor costo de gestion.
- Excepciones dinamicas agilizan delivery, con riesgo de normalizar deuda.

## Riesgos
- Umbrales irreales generan bypass sistematico.
- Hallazgos criticos sin SLA de remediacion.
- Inconsistencia entre quality profiles por equipo.

## Buenas practicas
- Definir quality profiles corporativos y ownership claro.
- Establecer quality gate minimo obligatorio por criticidad.
- Versionar y revisar politicas de exclusiones.
- Publicar scorecards simples por dominio.

## Preguntas de entrevista
1. Como definis quality gates de SonarQube por tipo de servicio?
2. Como tratas deuda tecnica historica sin frenar al equipo?
3. Que KPI de SonarQube usas para liderazgo tecnico?

## Como responderlas
1. Segmento por criticidad y riesgo; exijo baseline minimo y niveles mas estrictos para sistemas core.
2. Aislo deuda legacy, bloqueo deuda nueva y planifico remediacion incremental.
3. Uso code smells relevantes, vulnerabilidades, maintainability rating y cumplimiento de gates.

## Relacionado
- [03 - Quality Gates](03-quality-gates.md)
- [07 - Security Controls](07-security-controls.md)
- [09 - Operating Model](09-operating-model.md)
- [10 - Service Criticality Matrix](10-service-criticality-matrix.md)
