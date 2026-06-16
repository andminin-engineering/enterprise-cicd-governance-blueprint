# 02-release-governance

## Objetivo
Definir un modelo de gobierno de releases para controlar riesgo, asegurar calidad y mejorar predictibilidad de entrega.

## Contexto
Muchos incidentes de produccion no ocurren por falta de codigo, sino por falta de governance en promocion entre ambientes, aprobaciones y criterios de salida.

## Trade-offs
- Mayor control de aprobaciones vs menor velocidad.
- Release calendar fijo vs entrega continua.
- Centralizacion del gate final vs autonomia de equipos.

## Riesgos
- Cuellos de botella por aprobadores unicos.
- Releases sin evidencia de testing o validacion funcional.
- Falta de rollback plan y ownership operativo.

## Buenas practicas
- Definir readiness checklist por nivel de riesgo.
- Separar approval tecnico, funcional y de seguridad cuando aplique.
- Exigir plan de rollback y criterios de abort.
- Registrar evidencia de release en un formato auditable.

## Preguntas de entrevista
1. Como diseñas un release process para sistemas transaccionales?
2. Que criterios usas para aprobar una promocion a produccion?
3. Como manejas una emergencia en ventana de release?

## Como responderlas
1. Segmento por riesgo, criticidad y dependencia; defino gates automaticos y aprobaciones puntuales.
2. Verifico calidad, seguridad, performance, observabilidad y plan de reversa.
3. Activo protocolo de emergencia con cambios acotados, aprobacion acelerada y postmortem obligatorio.

## Relacionado
- [00 - Overview](00-overview.md)
- [01 - Branching Strategy](01-branching-strategy.md)
- [08 - Deployment Strategies](08-deployment-strategies.md)
- [10 - Service Criticality Matrix](10-service-criticality-matrix.md)
