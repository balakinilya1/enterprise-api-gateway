# Integration Pattern

## Selected Pattern

**API-led integration with a managed API façade and synchronous Request-Reply orchestration.**

## Pattern Components

- API Gateway / API Façade
- Request-Reply
- Message Transformation
- Header-based value extraction
- Backend service invocation

## Processing Flow

```text
Consumer API Request
        ↓
API Management
        ↓
HTTPS Sender
        ↓
JSON → XML
        ↓
Extract productIdentifier
        ↓
Request Reply
        ↓
OData V2 Backend
        ↓
Response
```

## Rationale

Direct backend exposure would couple consumers to the backend endpoint and technical contract. The API façade provides a controlled consumer boundary, while the integration layer performs the processing required to reach the backend.

## Benefits

Consumer/backend decoupling, centralized API security, separation of governance and integration processing, reusable integration capabilities and an extension point for additional consumers.

## Trade-offs

Additional platform/lifecycle complexity and the need for explicit error propagation, monitoring and controlled deployment.
