# 13-raci-and-exception-governance

## Objetivo
Formalizar responsabilidades de gobierno (RACI) y establecer una politica estricta de excepciones para bypass de controles de calidad/seguridad en plataformas de pagos de alta criticidad.

## Contexto
La mayoria de fallas graves en delivery no proviene de ausencia de herramientas, sino de ambiguedad de responsabilidad y excepciones no gobernadas. Este documento elimina ambiguedad y fortalece auditabilidad.

## Matriz RACI (Operating Model)

| Accion clave | Platform Team | Architecture Board | Tech Lead | Product Owner |
|---|---|---|---|---|
| Definicion o ajuste de Quality Gate corporativo | R | A | C | I |
| Aprobacion de Deployment Tier 1 a produccion | R | A | C | C |
| Aprobacion de Deployment Tier 2/Tier 3 | R | C | A | C |
| Manejo de incidente critico en produccion | R | C | A | I |
| Clasificacion de servicio por Tier | C | A | R | C |
| Definicion de Change Freeze por evento de riesgo | C | A | R | I |

Leyenda:
- R: Responsible
- A: Accountable
- C: Consulted
- I: Informed

## Politica formal de excepciones (Bypass de calidad)

### Ambito
Aplica a bypass temporal de gates de SonarQube, seguridad o performance en procesos de release, con enfasis en servicios Tier 1.

### Autoridad para aprobar bypass en Tier 1
- Unicamente CTO o VP de Ingenieria, con registro formal de decision.
- Architecture Board valida impacto tecnico y mitigacion requerida antes de elevacion.
- Product Owner documenta impacto de negocio y ventana de necesidad.

### Condiciones validas de negocio
- Riesgo economico o regulatorio mayor por no desplegar (por ejemplo, cumplimiento normativo inminente).
- Incidente severo en produccion que requiere restauracion urgente de capacidad critica.
- Ventana comercial critica con afectacion demostrable de ingresos si no se actua.

### Mitigacion inmediata obligatoria
- Compensating controls activos (monitoreo reforzado, alertas de severidad alta, limitacion de trafico o feature flag).
- Plan de rollback probado y disponible antes del despliegue.
- Ticket de remediacion creado con owner, esfuerzo y fecha comprometida.

### Vencimiento mandatorio de excepcion
- Tier 1: maximo 72 horas calendario.
- Tier 2: maximo 7 dias.
- Tier 3: maximo 14 dias.
- Al vencimiento, el gate vuelve a estado bloqueante sin excepcion automatica.

### Evidencia para auditoria
- Justificacion de negocio y analisis de riesgo.
- Aprobadores nominales con timestamp.
- Controles compensatorios aplicados.
- Fecha de expiracion y evidencia de cierre/remediacion.

## Trade-offs
- Excepciones controladas permiten continuidad de negocio en crisis, pero pueden erosionar disciplina si se abusan.
- Modelo de aprobacion ejecutiva reduce riesgo sistemico, con posible impacto en velocidad.
- Vencimientos cortos aumentan seguridad operativa, con mayor presion de remediacion.

## Riesgos
- Escalada indebida de bypass por presion comercial.
- Ausencia de cierre de excepciones dentro de SLA.
- Falta de observabilidad reforzada durante ventana de excepcion.

## Buenas practicas
- Tratar cada bypass como incidente de governance con postmortem.
- Publicar reporte mensual de excepciones por tier y causa raiz.
- Bloquear nuevas excepciones si existe deuda vencida sin remediar.
- Integrar excepciones al scorecard ejecutivo de riesgo.

## Preguntas de entrevista
1. Quien puede aprobar un bypass en un servicio de pagos Tier 1 y por que?
2. Como evitarias que la excepcion se vuelva la norma?
3. Que evidencia exigis para auditoria en un bypass critico?

## Como responderlas
1. Solo CTO o VP Ingenieria por impacto sistemico y responsabilidad ejecutiva de riesgo.
2. Limito condiciones, impongo vencimiento estricto y exijo cierre con remediacion verificable.
3. Registro de aprobacion, mitigaciones activas, expiracion y evidencia de cierre de hallazgos.

## Relacionado
- [02 - Release Governance](02-release-governance.md)
- [03 - Quality Gates](03-quality-gates.md)
- [09 - Operating Model](09-operating-model.md)
- [12 - DORA Metrics and Engineering KPIs](12-dora-metrics-and-engineering-kpis.md)
