# 03-quality-gates

## Objetivo
Definir quality gates estandar para prevenir defectos y asegurar un baseline de calidad antes de merge, release y despliegue.

## Contexto
Sin quality gates, la variabilidad entre equipos permite que cambios sin cobertura, deuda tecnica alta o vulnerabilidades lleguen a entornos criticos.

## Trade-offs
- Gates estrictos elevan calidad pero pueden afectar throughput inicial.
- Gates flexibles aceleran entrega pero aumentan deuda y riesgo.
- Cobertura cuantitativa sola puede ocultar brechas de diseño.

## Riesgos
- Falsos positivos de herramientas que bloquean entrega.
- Excepciones recurrentes sin fecha de vencimiento.
- Umbrales mal calibrados para dominios distintos.

## Buenas practicas
- Definir gates por riesgo y tipo de servicio.
- Versionar politicas de quality gate.
- Exigir explicacion formal para bypass temporal.
- Revisar umbrales periodicamente con datos de incidentes.

## Preguntas de entrevista
1. Que quality gates consideras no negociables?
2. Como manejas excepciones a un gate bloqueante?
3. Como conectas gates tecnicos con riesgo de negocio?

## Como responderlas
1. Compilacion, tests criticos, analisis estatico y vulnerabilidades severas sin excepcion.
2. Permito bypass temporal solo con aprobacion, ticket y fecha de remediacion comprometida.
3. Traduzco cada gate a impacto: disponibilidad, fraude, cumplimiento y reputacion.

## Relacionado
- [00 - Overview](00-overview.md)
- [06 - SonarQube Governance](06-sonarqube-governance.md)
- [07 - Security Controls](07-security-controls.md)
- [10 - Service Criticality Matrix](10-service-criticality-matrix.md)
