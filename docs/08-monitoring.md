# Monitoring

## Monitoring Model

```text
API Management
   ├── API traffic
   ├── authentication failures
   ├── latency
   └── HTTP errors
        ↓
Cloud Integration
   ├── message processing
   ├── integration failures
   └── processing duration
        ↓
Backend
   ├── availability
   ├── response time
   └── service errors
```

## Recommended Metrics

- request count;
- success rate;
- 4xx rate;
- 5xx rate;
- authentication failures;
- latency;
- backend response time;
- integration failures;
- timeout count.

## Correlation

A production implementation should propagate a correlation identifier across:

```text
Consumer → API Management → Cloud Integration → Backend
```

## Alerting

Recommended alerts include sustained 5xx rate, authentication failure spikes, backend availability degradation, integration failures and abnormal latency.

Enterprise alert routing and on-call integration are future-state concerns.
