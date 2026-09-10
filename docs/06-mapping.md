# Mapping

## Request Transformation

The integration receives JSON and converts it to XML for downstream processing.

### Input

```json
{
  "productIdentifier": "HT-2000"
}
```

### Processing

1. HTTPS sender receives the request.
2. JSON-to-XML conversion transforms the message.
3. `productIdentifier` is extracted using XPath.
4. The value is stored in a message header.
5. Request Reply invokes the OData V2 backend.

## Field Mapping

| Source | Transformation | Target / Usage |
|---|---|---|
| `productIdentifier` | XPath `//productIdentifier` | Message header `productIdentifier` |

The demonstrated header is a `java.lang.String`.

## Production Mapping Model

For an enterprise backend, the mapping specification should define source/target fields, transformation rules, mandatory/optional status, defaults, validation, code/value conversion and error behavior. The repository does not invent backend fields not supported by the implementation scenario.
