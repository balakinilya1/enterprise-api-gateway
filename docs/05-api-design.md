# API Design

## Consumer-Facing API

**API Name:** RequestProductDetails  
**Title:** Product Details API  
**Base Path:** `/products`  
**Operation:** `POST /products/details`

## Request

```json
{
  "productIdentifier": "HT-2000"
}
```

## Authentication

```http
Authorization: Bearer <access_token>
```

The token is validated before the request reaches the integration layer.

## API Boundary

```text
Consumer Contract
POST /products/details
        |
        v
SAP API Management
        |
        v
Internal Integration
        |
        v
OData Backend
```

## Design Principles

### Backend Abstraction
The consumer interacts with a stable API contract rather than directly with the OData endpoint.

### Explicit Contract
The request structure is defined independently from backend implementation.

### Security at the Boundary
Authentication is enforced before backend processing.

## Production Contract Extensions

A production API should additionally define complete response/error schemas, HTTP status semantics, versioning, compatibility policy, correlation ID, ownership, lifecycle state, consumer onboarding and subscription model.
