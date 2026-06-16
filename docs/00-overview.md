# 00-overview

## Objetivo
Definir la vision global del blueprint CI/CD enterprise, su alcance, principios y criterios de adopcion organizacional.

## Contexto
La adopcion de CI/CD sin gobierno suele crear pipelines aislados por equipo, controles inconsistentes y decisiones no trazables. Un overview comun reduce dispersion y acelera alineacion.

## Trade-offs
- Estandarizacion vs autonomia de equipo.
- Gobierno central vs velocidad de experimentacion.
- Politicas comunes vs necesidades especificas por dominio.

## Riesgos
- Exceso de burocracia en aprobaciones.
- Excepciones no gobernadas por urgencia operativa.
- Falta de ownership para mantener la documentacion viva.

## Buenas practicas
- Definir minimo comun obligatorio y zonas de flexibilidad.
- Usar ADRs para decisiones transversales de pipeline.
- Revisar el framework por trimestre con datos reales.
- Medir adopcion por indicadores simples y comparables.

## Preguntas de entrevista
1. Como equilibras estandarizacion y autonomia en CI/CD?
2. Que metrica usas para validar que el gobierno funciona?
3. Como evitas que governance se convierta en friccion?

## Como responderlas
1. Defino controles no negociables y permito extensiones por equipo documentadas.
2. Uso lead time, failure rate, rollback rate y cumplimiento de gates.
3. Mantengo un catalogo minimo, automatizo validaciones y elimino pasos manuales sin valor.

## Glosario Tecnico Operativo
- Promotion: movimiento controlado de un artefacto versionado entre ambientes (por ejemplo, de staging a produccion) bajo politicas de aprobacion y evidencia de cumplimiento.
- Release Train: cadencia predefinida de liberaciones que sincroniza multiples equipos y reduce variabilidad en la entrega.
- Quality Gate: conjunto de criterios tecnicos minimos (calidad, seguridad, testing) que deben cumplirse para permitir merge o release.
- Compliance Pipeline: pipeline obligatorio que aplica controles transversales de seguridad, calidad y trazabilidad sin depender de implementaciones ad hoc por equipo.
- Rollback: estrategia para restaurar rapidamente una version estable ante degradacion de servicio o incumplimiento de SLOs.
- Canary: despliegue progresivo a una porcion acotada de trafico para validar comportamiento antes de habilitar el 100%.
- Blue/Green: estrategia de despliegue con dos entornos equivalentes que permite switch de trafico con baja interrupcion y reversa rapida.
- Hotfix: cambio urgente, de alcance minimo, para mitigar incidentes criticos en produccion con trazabilidad y regularizacion posterior.
- Change Freeze: periodo de restriccion de cambios en sistemas criticos durante ventanas de riesgo operacional o regulatorio.

## Relacionado
- [01 - Branching Strategy](01-branching-strategy.md)
- [02 - Release Governance](02-release-governance.md)
- [03 - Quality Gates](03-quality-gates.md)
- [10 - Service Criticality Matrix](10-service-criticality-matrix.md)
