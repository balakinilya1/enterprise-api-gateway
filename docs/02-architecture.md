# Architecture

## Architecture Overview

SAP API Management is the governed API boundary and SAP Cloud Integration is the integration processing layer.

```mermaid
flowchart LR
    C[API Consumer] -->|HTTPS / OAuth 2.0| A[SAP API Management]
    A -->|Managed API| I[SAP Cloud Integration]
    I -->|OData V2| B[Webshop OData V2 Service]
    B --> I
    I --> A
    A --> C
```

## Component Responsibilities

### API Consumer
Obtains an OAuth 2.0 access token and invokes the managed API.

### SAP API Management
Provides the external API boundary, authentication/authorization policies, API governance and API-level operational visibility.

### SAP Cloud Integration
Receives the request, transforms the message, extracts the product identifier and invokes the backend.

### OData V2 Backend
Provides product information.

## Trust Boundaries

1. Consumer → API Management
2. API Management → Cloud Integration
3. Cloud Integration → Backend

## Separation of Concerns

```text
API Governance → API Management
Integration Processing → Cloud Integration
Backend Connectivity → OData Service
```

## Runtime Sequence

```mermaid
sequenceDiagram
    participant C as API Consumer
    participant A as API Management
    participant I as Cloud Integration
    participant B as OData Backend
    C->>A: POST /products/details + access token
    A->>A: Validate access token
    A->>I: Forward managed API request
    I->>I: JSON → XML
    I->>I: Extract productIdentifier
    I->>B: OData request
    B-->>I: Product details
    I-->>A: Response
    A-->>C: API response
```

## Architectural Principle

API Management provides the stable consumer-facing boundary; Cloud Integration handles message transformation and backend orchestration. This reduces consumer coupling to backend connectivity details.
