# 05-gitlab-ci-reference

## Objetivo
Definir una referencia de GitLab CI/CD alineada a gobierno enterprise para equipos que usan GitLab como plataforma de entrega.

## Contexto
Organizaciones hibridas usan GitHub y GitLab en paralelo. Sin equivalencias claras, la governance se rompe y cada plataforma evoluciona con reglas distintas.

## Trade-offs
- Plantillas globales simplifican governance pero requieren mantenimiento central.
- Pipelines por proyecto dan autonomia, con riesgo de dispersion.
- Stages extensos mejoran control, con mayor tiempo de feedback.

## Riesgos
- Drift de politicas entre grupos y proyectos.
- Variables sensibles sin proteccion adecuada.
- Falla de consistencia entre merge request checks y gates de release.

## Buenas practicas
- Estandarizar include templates por tipo de proyecto.
- Definir compliance pipelines para controles comunes.
- Gestionar variables protegidas y mascaradas por entorno.
- Unificar politicas de merge request y aprobaciones.

## Preguntas de entrevista
1. Como armonizas governance entre GitHub Actions y GitLab CI/CD?
2. Que rol cumple un compliance pipeline?
3. Como manejas secretos en GitLab para varios ambientes?

## Como responderlas
1. Defino controles equivalentes por capacidad y documento la trazabilidad entre plataformas.
2. Aplica controles transversales obligatorios sin depender de cada equipo.
3. Segmento variables por entorno, protejo ramas y limito acceso por rol y proyecto.

## Relacionado
- [03 - Quality Gates](03-quality-gates.md)
- [04 - GitHub Actions Reference](04-github-actions-reference.md)
- [07 - Security Controls](07-security-controls.md)
- [09 - Operating Model](09-operating-model.md)
