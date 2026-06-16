# 09-operating-model

## Objetivo
Definir el operating model para sostener CI/CD governance en el tiempo con roles claros, rituales y mejora continua.

## Contexto
Sin operating model, la documentacion pierde vigencia y los equipos vuelven a patrones locales. El modelo operativo conecta estrategia, ejecucion y aprendizaje.

## Trade-offs
- Modelo centralizado mejora consistencia, con riesgo de baja autonomia.
- Modelo federado aumenta ownership local, con riesgo de divergence.
- Cadencias de control frecuentes mejoran calidad, con costo de coordinacion.

## Riesgos
- Falta de responsables por dominio de governance.
- Politicas sin medicion ni enforcement.
- Mejora continua sin backlog priorizado.

## Buenas practicas
- Definir ownership por capability: CI, seguridad, calidad, release.
- Establecer comite liviano de delivery governance.
- Operar con KPIs compartidos y retro semanal.
- Mantener backlog de mejoras con impacto y esfuerzo.

## Preguntas de entrevista
1. Como sostenes governance sin frenar equipos?
2. Que roles son criticos en este operating model?
3. Que indicadores usas para evaluar madurez?

## Como responderlas
1. Automatizo controles, reduzco pasos manuales y reviso politica con feedback real.
2. Platform owner, delivery lead, security champion y representantes de equipos producto.
3. Lead time, deployment frequency, change failure rate, MTTR y cumplimiento de gates.

## Relacionado
- [00 - Overview](00-overview.md)
- [02 - Release Governance](02-release-governance.md)
- [04 - GitHub Actions Reference](04-github-actions-reference.md)
- [05 - GitLab CI Reference](05-gitlab-ci-reference.md)
