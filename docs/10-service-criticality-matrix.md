# 10-service-criticality-matrix

## Objetivo
Definir una matriz de criticidad para plataformas transaccionales (Fintech/Payments) que vincule nivel de riesgo con exigencias minimas de calidad, seguridad, despliegue y aprobacion.

## Contexto
En sistemas de pagos no todos los servicios tienen el mismo impacto operativo o regulatorio. Esta matriz evita aplicar controles uniformes donde no corresponden y permite escalar governance por riesgo real.

## Matriz de criticidad

| Criterio | Tier 1 (Critico - Core de Pagos/Adquirencia) | Tier 2 (Importante - Backoffice/Saldos) | Tier 3 (Estandar - Reportes/Herramientas internas) |
|---|---|---|---|
| Cobertura minima de pruebas | >= 85% lineas y >= 75% ramas en modulos criticos | >= 75% lineas y >= 65% ramas | >= 65% lineas y >= 55% ramas |
| Quality Gates SonarQube | Sin issues Blocker/Critical nuevas, coverage y maintainability bloqueantes | Sin issues Blocker nuevas, coverage bloqueante y deuda controlada | Sin issues Blocker nuevas, debt ratio monitoreado |
| Scans de seguridad obligatorios | SAST + DAST + Dependency Check + Secret Scanning en cada release | SAST + Dependency Check + Secret Scanning por merge | SAST + Dependency Check en rama principal |
| Estrategia de despliegue | Canary o Blue/Green con observabilidad en tiempo real y rollback automatico | Blue/Green o Rolling con smoke tests y rollback definido | Rolling con validaciones basicas y ventana de observacion |
| Flujo de aprobaciones | Peer Review (2), Security Review, CAB para cambios de alto impacto | Peer Review (1-2), aprobacion tecnica de delivery lead | Peer Review (1) y aprobacion automatizada por pipeline |
| Politica de cambio en eventos criticos | Change Freeze obligatorio en eventos regulatorios/comerciales | Freeze selectivo por dominio y dependencia | Sin freeze global, control por equipo |

## Trade-offs
- Controles mas estrictos en Tier 1 reducen riesgo sistemico, con mayor costo operativo.
- Flexibilizar Tier 3 acelera experimentacion, pero requiere monitoreo para evitar deuda acumulada.
- Ajustar thresholds por tier mejora foco, aunque aumenta complejidad de gobierno.

## Riesgos
- Clasificar mal un servicio puede subproteger activos criticos.
- Excepciones permanentes degradan disciplina de quality gates.
- Politicas de aprobacion ambiguas generan cuellos de botella o bypass.

## Buenas practicas
- Revisar clasificacion de servicios cada trimestre o ante cambios de arquitectura.
- Exigir evidencia auditable de cumplimiento por tier en cada release.
- Definir due date obligatoria para excepciones y debt de seguridad.
- Publicar scorecard mensual de cumplimiento por dominio.

## Preguntas de entrevista
1. Como decidis el tier de un servicio en una plataforma de pagos?
2. Por que no usar los mismos quality gates para todos los servicios?
3. Como prevenis abuso de excepciones en Tier 1?

## Como responderlas
1. Clasifico por impacto en ingresos, riesgo regulatorio, volumen transaccional y dependencia sistemica.
2. Porque el costo del control debe alinearse al riesgo; estandarizar sin contexto reduce eficiencia.
3. Defino excepciones con aprobacion formal, vencimiento obligatorio y seguimiento en comite de governance.

## Relacionado
- [00 - Overview](00-overview.md)
- [03 - Quality Gates](03-quality-gates.md)
- [06 - SonarQube Governance](06-sonarqube-governance.md)
- [08 - Deployment Strategies](08-deployment-strategies.md)
