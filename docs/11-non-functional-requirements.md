# 11-non-functional-requirements

## Objetivo
Definir requisitos no funcionales (NFRs) por criticidad de servicio para plataformas Fintech/Payments y establecer como el framework de CI/CD protege estos objetivos en cada release.

## Contexto
En ecosistemas transaccionales, una regresion de disponibilidad o latencia tiene impacto directo en revenue, riesgo regulatorio y reputacion. Por eso, los NFRs deben ser contrato de arquitectura y condicion de release.

## Matriz NFR por Tier

| Dimension | Tier 1 (Critico - Core de Pagos/Adquirencia) | Tier 2 (Importante - Backoffice/Saldos) | Tier 3 (Estandar - Reportes/Herramientas internas) |
|---|---|---|---|
| Availability mensual | >= 99.95% | >= 99.90% | >= 99.50% |
| RTO | < 15 minutos | < 30 minutos | < 4 horas |
| RPO | < 5 minutos | < 15 minutos | < 24 horas |
| Latencia API p95 | < 300 ms en endpoints transaccionales | < 500 ms | < 1000 ms |
| Error Rate tolerado | < 0.30% por ventana de 5 minutos | < 0.75% | < 1.50% |
| Auditabilidad | Trazabilidad completa de cambio, aprobacion, artefacto y despliegue | Trazabilidad de release y aprobaciones tecnicas | Trazabilidad basica de cambios y releases |
| Seguridad y cumplimiento | Cifrado en transito/reposo, segregacion de funciones, evidencia auditable y controles regulatorios reforzados | Cifrado en transito/reposo y controles de acceso por rol | Controles base de identidad y hardening de pipeline |

## Como CI/CD protege los NFRs
- Availability: los despliegues Tier 1 exigen estrategia Canary o Blue/Green, health checks y rollback automatico por degradacion de SLO.
- RTO/RPO: los pipelines obligan validacion de runbooks de recuperacion y evidencia de pruebas de restauracion antes de aprobar promotion.
- Latencia p95: los quality gates incorporan performance budget para endpoints criticos y bloqueo de release ante regresion significativa.
- Error Rate: se definen umbrales de abort de despliegue y post-deploy verification con observabilidad activa.
- Auditabilidad: cada promotion requiere evidencia de commit, artefacto firmado, aprobadores y resultado de controles.
- Seguridad: controles SAST/DAST/Dependency y secretos son gates obligatorios por tier, con excepciones de vencimiento limitado.

## Trade-offs
- Endurecer gates en Tier 1 mejora resiliencia sistemica con mayor costo de ciclo.
- Unificar umbrales para todos los tiers simplifica governance pero genera sobrecontrol en servicios de bajo riesgo.
- Exigir evidencia de DR en cada release sube confiabilidad, aunque incrementa overhead operativo.

## Riesgos
- NFRs demasiado ambiciosos sin capacidad real de observabilidad.
- Derogaciones frecuentes de performance o seguridad por presion de negocio.
- Falta de ownership claro para recalibrar objetivos por cambios de arquitectura.

## Buenas practicas
- Tratar los NFRs como contrato de plataforma y no como referencia opcional.
- Versionar objetivos por tier con fecha de vigencia y owner.
- Medir cumplimiento por dominio y revisar gaps en governance board.
- Alinear NFRs con SLOs y error budget para decisiones de release.

## Preguntas de entrevista
1. Como decidis objetivos NFR por tier en una plataforma de pagos?
2. Como evita CI/CD que un release rompa latencia o disponibilidad?
3. Que haces cuando negocio exige release y no se cumple un NFR critico?

## Como responderlas
1. Priorizo impacto en transaccion, riesgo regulatorio, dependencia sistemica y tolerancia de negocio.
2. Implemento gates de performance, despliegue progresivo y rollback automatico con umbrales definidos.
3. Activo politica de excepcion formal con mitigacion inmediata, ventana limitada y aprobacion ejecutiva.

## Relacionado
- [10 - Service Criticality Matrix](10-service-criticality-matrix.md)
- [03 - Quality Gates](03-quality-gates.md)
- [08 - Deployment Strategies](08-deployment-strategies.md)
- [12 - DORA Metrics and Engineering KPIs](12-dora-metrics-and-engineering-kpis.md)
