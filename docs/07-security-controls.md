# 07-security-controls

## Objetivo
Definir controles de seguridad en CI/CD para reducir riesgo de supply chain, fuga de secretos y despliegues inseguros.

## Contexto
El pipeline es parte del sistema productivo. Si no se protege, un atacante puede comprometer artefactos, dependencias o credenciales antes de llegar a produccion.

## Trade-offs
- Controles estrictos mejoran seguridad, con mayor tiempo de ejecucion.
- Scans completos en cada commit elevan costo; escaneos selectivos aceleran feedback.
- Rotacion frecuente de secretos aumenta seguridad y complejidad operativa.

## Riesgos
- Dependencias vulnerables no bloqueadas.
- Secretos expuestos en logs o repositorios.
- Artefactos sin firma ni trazabilidad de origen.

## Buenas practicas
- Implementar SAST, dependency scanning y secret scanning.
- Aplicar firma y verificacion de artefactos.
- Limitar permisos de runners y tokens.
- Mantener proceso formal de excepciones con vencimiento.

## Preguntas de entrevista
1. Cuales son los controles minimos de seguridad en pipeline?
2. Como gestionas un hallazgo critico durante release?
3. Como tratas riesgo de dependencias de terceros?

## Como responderlas
1. Escaneo de codigo, dependencias, secretos y politicas de privilegio minimo.
2. Bloqueo release, analisis de impacto, plan de remediacion y excepcion solo con aprobacion ejecutiva.
3. Uso inventario SBOM, politicas de versionado y bloqueo de CVE severas.

## Relacionado
- [03 - Quality Gates](03-quality-gates.md)
- [04 - GitHub Actions Reference](04-github-actions-reference.md)
- [05 - GitLab CI Reference](05-gitlab-ci-reference.md)
- [10 - Service Criticality Matrix](10-service-criticality-matrix.md)
