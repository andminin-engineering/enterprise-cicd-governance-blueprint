# 01-branching-strategy

## Objetivo
Establecer una estrategia de ramas consistente para desarrollo, estabilizacion y releases con trazabilidad completa.

## Contexto
Sin una branch strategy clara, los equipos mezclan cambios no relacionados, aumentan conflictos de merge y elevan riesgo de regresiones al release.

## Trade-offs
- Trunk-based delivery mejora flujo pero exige alta disciplina de testing.
- GitFlow aporta estructura pero puede agregar costo operativo.
- Release branches dan control pero incrementan mantenimiento paralelo.

## Riesgos
- Ramas largas con drift respecto de main.
- Hotfixes sin trazabilidad ni retroport.
- Promocion de cambios sin criterios uniformes de calidad.

## Buenas practicas
- Mantener main siempre desplegable.
- Limitar vida de ramas de feature.
- Definir politicas de pull request, reviewers y checks obligatorios.
- Estandarizar convenciones de naming y versionado.

## Preguntas de entrevista
1. Cuando elegirias trunk-based sobre GitFlow?
2. Como manejas hotfixes en un modelo multiambiente?
3. Que controles pondrias antes de mergear a main?

## Como responderlas
1. Trunk-based cuando hay alta automatizacion y feedback rapido; GitFlow cuando hay release trains complejos.
2. Creo rama de hotfix corta, aplico quality gates minimos y aseguro forward-merge a main y ramas activas.
3. Exijo tests, analisis estatico, seguridad basica, coverage minimo y aprobacion de reviewers definidos.

## Relacionado
- [00 - Overview](00-overview.md)
- [02 - Release Governance](02-release-governance.md)
- [03 - Quality Gates](03-quality-gates.md)
- [10 - Service Criticality Matrix](10-service-criticality-matrix.md)
