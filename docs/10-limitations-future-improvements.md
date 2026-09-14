# Limitations / Future Improvements

## Current Limitations

1. The backend is represented by the webshop OData V2 scenario rather than a real enterprise backend.
2. The consumer contract has not been validated against a production consumer.
3. Production SLA/SLO, RPO and RTO values are not established.
4. Enterprise alert routing is not implemented.
5. Production CI/CD and transport governance are not implemented.
6. Complete enterprise field-level mapping is not available.
7. Production retry/reprocessing architecture is not implemented.
8. Enterprise identity federation is outside the demonstrated scope.
9. The repository does not claim a production deployment.

## Future Improvements

### API Governance
API versioning, ownership/lifecycle states, consumer onboarding, products/subscriptions and Developer Hub publication.

### Security
Enterprise identity integration, automated secret rotation, certificate lifecycle management, threat protection and traffic controls where required.

### Operations
Centralized alerting, correlation-ID tracing, operational dashboards, SLO monitoring and incident-management integration.

### Delivery
Automated contract tests, CI/CD, controlled transport and automated deployment verification.

### Resilience
Explicit timeout strategy, bounded retries, controlled recovery and reprocessing mechanisms where appropriate.

## Architectural Maturity

The next maturity step is not adding complexity for its own sake. Enterprise controls should be introduced based on actual business, security, operational and non-functional requirements.
