# Security

## Security Architecture

```text
API Consumer
    |
    | HTTPS + OAuth 2.0 access token
    v
SAP API Management
    |
    | Authorized request
    v
SAP Cloud Integration
    |
    v
Backend
```

## Authentication

The API uses **OAuth 2.0 client credentials** for machine-to-machine authentication.

```http
Authorization: Bearer <access_token>
```

## Security Controls

| Layer | Control |
|---|---|
| Transport | HTTPS |
| API authentication | OAuth 2.0 client credentials |
| API authorization | Access-token validation at API boundary |
| Credential storage | Environment/service configuration |
| Backend abstraction | Backend endpoint is not the consumer contract |
| Repository security | No credentials or secrets committed |

## Credential Handling

Never commit client secrets, access tokens, service keys, private keys or sensitive environment configuration.

```text
CLIENT_ID=<managed-secret>
CLIENT_SECRET=<managed-secret>
TOKEN_URL=<environment-specific-url>
```

## Production Security Considerations

Enterprise identity integration, secret rotation, certificate management, rate limiting/quota, threat protection, IP restrictions, audit requirements and least-privilege access should be assessed against actual requirements. These are not claimed as implemented unless supported by evidence.
