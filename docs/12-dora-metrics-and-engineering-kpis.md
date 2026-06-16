# 12-dora-metrics-and-engineering-kpis

## Objetivo
Definir un sistema de medicion para evaluar el impacto del blueprint de governance usando metricas DORA y KPIs de calidad/seguridad en contexto Fintech/Payments.

## Contexto
Sin medicion consistente, la governance de CI/CD se vuelve declarativa. DORA permite cuantificar velocidad y estabilidad, mientras los KPIs de calidad y seguridad aseguran que la aceleracion no comprometa riesgo operacional.

## DORA: estrategia de medicion

| Metrica | Definicion | Objetivo Tier 1 | Objetivo Tier 2 | Objetivo Tier 3 |
|---|---|---|---|---|
| Deployment Frequency | Frecuencia de despliegues exitosos a produccion | Diario o multiple por dia en dominios estabilizados | 2-5 veces por semana | Semanal o bajo demanda |
| Lead Time for Changes | Tiempo desde commit hasta produccion | < 24 horas | < 48 horas | < 5 dias |
| MTTR | Tiempo medio de restauracion ante incidente | < 30 minutos | < 2 horas | < 8 horas |
| Change Failure Rate (CFR) | Porcentaje de cambios que causan degradacion/incidente | < 5% | < 10% | < 15% |

## KPIs de calidad y seguridad complementarios

### Quality Gates minimos SonarQube
- Tier 1: coverage >= 80%, 0 vulnerabilidades nuevas Blocker/Critical, 0 bugs nuevos Blocker, quality gate obligatorio bloqueante.
- Tier 2: coverage >= 75%, 0 vulnerabilidades nuevas Blocker, deuda tecnica nueva bajo umbral definido.
- Tier 3: coverage >= 65%, 0 vulnerabilidades nuevas Blocker, monitoreo de deuda por release.

### SLAs de remediacion de seguridad
- Critical: mitigacion inmediata, remediacion <= 24 horas.
- High: remediacion <= 72 horas.
- Medium: remediacion <= 14 dias.
- Low: remediacion <= 30 dias o siguiente ciclo planificado.

## Modelo operativo de medicion
- Fuente unica de datos desde pipelines, SonarQube y plataforma de observabilidad.
- Scorecards semanales por dominio con tendencia de 4 semanas.
- Alertas automaticas cuando MTTR o CFR superan umbral de tier.
- Revision quincenal en governance board para acciones correctivas.

## Trade-offs
- Umbrales exigentes de DORA mejoran performance operativa, pero demandan inversion en automatizacion.
- Medir demasiados KPIs puede diluir foco y generar ruido.
- Priorizacion de velocidad sin gates de calidad incrementa CFR a mediano plazo.

## Riesgos
- Gaming de metricas sin mejora real de calidad.
- Inconsistencia de definiciones entre equipos.
- Falta de correlacion entre eventos de incidentes y datos de pipeline.

## Buenas practicas
- Estandarizar definiciones de metricas desde el inicio.
- Publicar scorecards transparentes por tier y dominio.
- Correlacionar DORA con incidentes y costo de no calidad.
- Ajustar objetivos trimestralmente segun madurez real.

## Preguntas de entrevista
1. Como usas DORA sin caer en metricas cosmeticas?
2. Por que combinar DORA con quality gates de SonarQube?
3. Como priorizas mejoras cuando deployment frequency sube pero tambien CFR?

## Como responderlas
1. Conecto metricas a decisiones de release, postmortems y planes de mejora concretos.
2. DORA mide flujo y estabilidad; SonarQube protege calidad estructural y riesgo tecnico.
3. Pauso aceleracion, refuerzo gates y ataco causas raiz hasta recuperar estabilidad.

## Relacionado
- [03 - Quality Gates](03-quality-gates.md)
- [06 - SonarQube Governance](06-sonarqube-governance.md)
- [09 - Operating Model](09-operating-model.md)
- [11 - Non Functional Requirements](11-non-functional-requirements.md)
