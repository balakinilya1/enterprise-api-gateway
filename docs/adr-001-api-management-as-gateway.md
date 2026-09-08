# ADR-001: Use API Management as the Enterprise API Gateway

## Status

Accepted

## Context

The backend service should not be exposed directly to API consumers. The architecture also requires a governed API boundary capable of enforcing authentication and supporting API lifecycle and operational controls.

## Decision

Use **SAP API Management** as the consumer-facing API gateway and keep **SAP Cloud Integration** responsible for message transformation and backend orchestration.

## Consequences

### Positive

- centralized API security;
- backend abstraction;
- separation of API governance and integration processing;
- reusable governance capabilities;
- foundation for consumer onboarding and lifecycle management.

### Negative

- additional platform component;
- separate API and integration lifecycle management;
- additional configuration to transport across environments.

## Alternative

### Direct Backend Exposure

Rejected because it couples consumers directly to the backend service and bypasses the intended API governance boundary.

### Cloud Integration Endpoint Without API Management

Not selected as the target architecture because the project requires a dedicated API governance and gateway layer.
