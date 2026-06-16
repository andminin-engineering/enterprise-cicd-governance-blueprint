# 04-github-actions-reference

## Objetivo
Definir una referencia enterprise para pipelines en GitHub Actions con controles de calidad, seguridad y gobernanza.

## Contexto
GitHub Actions facilita adopcion rapida, pero sin estandarizacion puede fragmentar practicas entre repositorios y generar riesgos de supply chain.

## Trade-offs
- Workflows centralizados simplifican governance pero pueden limitar customizacion.
- Reusable workflows reducen duplicacion pero agregan dependencia de plataforma.
- Self-hosted runners dan control, con mayor costo operativo.

## Riesgos
- Secrets mal gestionados en repos.
- Repeticion de jobs sin control de version.
- Permisos excesivos en tokens de workflow.

## Buenas practicas
- Usar reusable workflows versionados.
- Aplicar principio de minimo privilegio en permissions.
- Firmar artefactos y validar procedencia.
- Definir checks obligatorios en branch protection.

## Preguntas de entrevista
1. Como escalas GitHub Actions en una organizacion con muchos repos?
2. Que controles aplicas para hardening de workflows?
3. Como evitas duplicacion entre pipelines?

## Como responderlas
1. Centralizo plantillas y reusable workflows con versionado semantico y guias de adopcion.
2. Restrinjo permisos, gestiono secrets por entorno y valido dependencias de acciones.
3. Creo catalogos comunes de jobs y establezco politicas de composicion por tipo de servicio.

## Relacionado
- [03 - Quality Gates](03-quality-gates.md)
- [05 - GitLab CI Reference](05-gitlab-ci-reference.md)
- [07 - Security Controls](07-security-controls.md)
- [09 - Operating Model](09-operating-model.md)
