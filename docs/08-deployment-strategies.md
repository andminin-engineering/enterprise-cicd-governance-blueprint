# 08-deployment-strategies

## Objetivo
Describir estrategias de despliegue para balancear velocidad, disponibilidad y control de riesgo en distintos contextos de negocio.

## Contexto
No todos los servicios requieren la misma estrategia. Sistemas transaccionales suelen necesitar mecanismos de despliegue progresivo y rollback controlado.

## Trade-offs
- Blue/Green reduce downtime con mayor costo de infraestructura.
- Canary reduce riesgo por impacto gradual, pero requiere observabilidad madura.
- Rolling update es simple, con menor aislamiento ante fallas.

## Riesgos
- Rollback incompleto por cambios de esquema.
- Falta de criterios de abort ante degradacion.
- Despliegues sin smoke tests ni monitoreo activo.

## Buenas practicas
- Elegir estrategia por criticidad y tolerancia al riesgo.
- Definir health checks, smoke tests y runbooks.
- Separar cambios de base de datos con enfoque backward compatible.
- Medir impacto post deployment con ventanas de observacion.

## Preguntas de entrevista
1. Como elegis estrategia de deployment para un servicio critico?
2. Que condiciones definen rollback automatico?
3. Como coordinas cambios de aplicacion y base de datos?

## Como responderlas
1. Analizo criticidad, volumen, RTO/RPO y madurez de observabilidad.
2. Defino umbrales de error rate, latencia y disponibilidad con abort inmediato.
3. Uso migraciones compatibles hacia atras y estrategia expand-and-contract.

## Relacionado
- [02 - Release Governance](02-release-governance.md)
- [03 - Quality Gates](03-quality-gates.md)
- [07 - Security Controls](07-security-controls.md)
- [10 - Service Criticality Matrix](10-service-criticality-matrix.md)
