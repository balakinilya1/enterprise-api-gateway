# Test Strategy

## Authentication

- request without access token → expected rejection;
- invalid token → expected rejection;
- valid token → request reaches API processing.

## API Contract

Valid request:

```json
{
  "productIdentifier": "HT-2000"
}
```

Negative cases: missing identifier, empty value, malformed JSON and unsupported content type.

## Integration Processing

Verify JSON-to-XML conversion, XPath extraction, `productIdentifier` header creation, backend Request Reply and response propagation.

## Backend Failure

Test backend timeout, backend unavailable, invalid backend response and product not found.

## Non-Functional Testing

Production delivery should additionally consider load, latency, security, resilience, contract compatibility and deployment/rollback testing.
